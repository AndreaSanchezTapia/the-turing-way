(rr-testing-challenges)=
# 检验方面的挑战和特殊情况

(rr-testing-challenges-stocastic-code)=
## 测试恒星代码

有时，代码包含随机性元素，常见的例子是使用 [Monte Carlo 方法](https://en.wikipedia.org/wiki/Monte_Carlo_method) 的代码。 测试这种代码可能非常困难，因为如果它多次运行，它将产生不同的答案， 所有这些都可能是“正确的”，即使它没有包含bug。 有两种主要方法来处理测试炉子塑料代码：

### 使用随机数的种子

随机数种子有点难以解释，这就是一个例子。 这里有一个能打印三个随机数字的 Python 脚本。

```python
导入随机

# 打印三个随机数字
打印(random.random())
打印(random.random())
打印(random.random.random())
```

这个脚本没有漏洞，但如果你一再运行它，你每次都会得到不同的答案。 现在让我们随机设置一个随机的种子。

```python
导入随机

# 设置随机的种子
随机种子
 随机种子

# 打印三个随机数
打印机(随机随机数)
打印机(随机数.随机数)
打印机(随机数.随机数) 
 打印(随机数)
```

现在，如果您运行此脚本，它将输出

```python
0.134364244112
0.8474333736937
0.763774618977
```

每次运行此脚本时，您都会得到 *相同的* 输出。它将打印相同的 ** 三个随机数。 如果随机数种子被更改，你将会获得不同的三个随机数字：

```python
0.956034271889
0.947827487059
0.0565513677268
```
但每当脚本在未来运行时，你都会得到相同的数字。

随机数种子是使事情变得可靠随机的一种方式。 然而，依靠随机数种子进行测试的风险是很小的。 说你有一个像这样的函数：

```python
def my_function():
  a = calculation_that_uses_two_random_numbers()
  b = calculation_that_uses_fiv_random_numbers()
  c = a + b
```

如果您设置了随机的种子，您将永远得到相同的 `c`, 以便可以进行测试。 但是，说模型已经改变，计算函数 `a` 使用了它以前做过的不同数量的随机数字。 现在不仅 `一个` 是不同的，而且 `b` 也是不同的。 因为上面显示的随机数输出给定的随机数种子是按固定顺序排列。 因此，为计算 `b` 所产生的随机数字将会改变。 这可能导致测试失败，如果实际上没有bug。

#### 测量结果的分布

测试随机输出代码的另一种方式是运行它多次并测试结果的分布。 也许结果可能起伏不定，但在某种容忍程度上总是期望约有10个结果。 这可以受到考验。 代码运行的次数越多，平均值就越可靠，结果也就越可靠。 然而，运行代码的时间越长，您的测试将越长。 如果要取得可靠的结果，测试可能会使得进行的时间过于耗时。 此外， 那里总是有一个不确定性元素，如果随机数字以某种方式下降，那么即使代码是正确的，你可能会在预期容忍度之外获得结果。

这两种测试炉灶代码的办法仍然非常有用，但也必须认识到其潜在的陷井。

(rr-testing-challenges-difficult-quatify)=
## 难以量化的测试

有时(特别是在研究中)测试代码的输出是否“外观”。 例如，我们有一种逐渐模拟水库水位的代码。

结果可能看起来像这样：

```{figure} ../../figures/eyeball-test1.jpg
---
名称：eyeball测试1
备选案文：
-
```

在有雨的日子里，它可能看起来像这样：

```{figure} ../../figures/eyeball-test2.jpg
---
name: eyeball-test2
alt:
---
```

在干燥的日子里，它可能看起来像这样：

```{figure} ../../figures/eyeball-test3.jpg
---
名称：eyeball测试3
备选案文：
---
```

所有这些产出看起来都非常不同，但都是有效的。 然而，如果研究人员认为这样的结果：

```{figure} ../../figures/eyeball-test-error.jpg
----
名称: eyeball-test-errer
alt:
---
```

他们可以轻易地得出错误，因为湖泊不大可能将其体积增加两倍，然后在几个小时内再次失去它。 像这样的“Eyeballing”测试是耗费时间的，因为它们必须由人来完成。 然而，通过创建基本的“健康检查”，这一过程可以部分或完全自动化。 例如，一次性水位应该是在水位范围内，例如，在前一阶段应该是10%的水量。 另一个检查可能是没有负值，因为湖泊不能满30%。 这些测试不能覆盖所有可能出现错误的东西， 但它们更容易自动化，在大多数情况下就足够了。

(rr-testing-challenges-non-integrger)=
## 如果非整数数字等于，则测试

### 当0.1 + 0.2 不等于 0.3

如果回答的代码输出等于当数字不是整数时的预期答案，这样的测试会遇到复杂的问题。 让我们看看这个Python例子，但注意这个问题不是Python唯一的问题。

如果我们将0.1分配给 `a` a 和 0.2分配给 `b` 并打印它们的金额，我们将按预期得到0.3。

```python
>>> a = 0.1
>>> b = 0.2
>>> print(a+b)
0.3
```

但是，如果我们比较 `a` plus `b` 到 0.3 的结果，我们就会得到False。

```python
>>> 打印(a+b == 0.3)
错误
```

如果我们直接显示 `a` plus `b` 的值, 我们可以看到一个微小的差错。

```python
>>> a + b
0.3000000000004
```

这是因为浮点数是实际数字的近似值。 浮点数计算的结果可能取决于编译器或解释器、处理器或系统结构以及正在使用的 CPU 或进程的数量。 这可能是写入测试的主要障碍。

### 浮点世界中的平等

在比较浮点数的均等性时，我们必须在给定的宽度内进行比较，也可以称之为阈值或三角洲。 例如， 如果其差异的绝对值在我们容忍的绝对值之内，我们也许会认为某些数字的计算值和预期值是等值的。

许多测试框架提供了将浮点数与特定容忍度范围内的均等值进行比较的功能。 例如，对于框架pest：

```python
导入pytest

a = 0.1
b = 0.2
c = a + b
sectc == pytest.approx(0.3)
```

这种情况已经过去，但如果0.3改为0.4，就会失败。

其他语文的股测试框架也常常提供类似的功能：

- C单元：CU_ASSERT_DOUBLE_EQUAL(实际，预期，粒度)
- CPPUnit for C++: CPPUNT_ASSERT_DOUBLES_EQUAL(预期, actual, delta)
- C++的谷歌测试：ASSERT_NEAR(val1, val2, abs_error)
- FRUIT for Fortran: sub-regular assert_eq_double_in_range_(var1, var2, delta, message)
- JUnit for Java : org.junit.Assert.assertEquals(双倍预期、双倍实际、双倍三角洲)
- 测试为 R：
  - 期望等价(实际, 预期, 容忍=DELTA) - 绝对错误
  - 期望等价(实际，预期，比例=预期，容忍度=DELTA) - DEL T A中的相对错误
