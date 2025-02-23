(rr-vcs-git-branches)=
# 吉特分支

当单独或合作开展一个项目时，您可能会遇到以下场景：

- 如果您为您的项目添加了一个新功能，您可能会在测试功能时意外地破坏您的工作代码。 这将给您项目的活跃用户带来意外的问题，即使您是唯一活跃的用户。
- 当你与他人合作并且每个人同时在主要分支工作时，可能会出现许多混乱和相互矛盾的变化。
- 有些代码/功能可能对每个人都不感兴趣。 也许需要有一种方法，允许就一个项目开展新的工作，同时保护已经完成的工作。

吉特分支机构在处理任何这些问题时都是极其宝贵的。 对于每个Git项目，默认情况下，你有一个名为 'main' 的分支，所有提交都被记录。 Git的分支功能使我们能够创建一个我们能够工作并继续承诺的项目副本，而不会马上将它们纳入主分支。 同时，人们可以继续在主要分支机构做出承诺，但其他分支机构的变动并未触及。 一旦你对你正在从事的分支工作感到满意， 你可以将它合并到你的主分支(或任何其他分支)。 Merging will be covered in the {ref}`rr-vcs-git-merge` subchapter.

如果您在一个分支上测试一个功能不正常，您可以删除或放弃它(例如) 下面图表中的B功能，而不是花费时间去选择您的更改，如果您在主分支上做了所有的工作。 您可以随意从分支中获得最多的分支(例如功能A-1)。

使用分支机构保证工作代码安全，特别是协作中的工作代码。 每个捐助方都可以有自己的分支机构或分支机构，而这些分支机构只有在准备就绪时才合并到主项目中。

```{figure} ../../figures/sub-branch.png
---
名称：子分支
备选案文：Git中分支的图示. 有四个分支显示的名称为主角，精英A，精英B和精英A-1。 特征A和特征B是主要分支的分支，而特征A-1则是由特征A制成的分支。
---
在Git中显示分支的示例
```

您可以使用以下方式创建分支并切换到它：
```
git 签出-b name_of_your_new_branch
```

要在分支之间进行更改，请使用以下命令：
```
git 签出名称_of_the_branch
```

您必须提交您正在进行的任何工作才能切换到另一个分支。

您可以看到项目的所有分支使用：

```
git 分支
```
这给出了一个列表，带星号在您开启的分支旁边。 如果你忘了开启哪个分支，你也可以使用 `git 状态`。

如果您决定去除分支，您可以通过以下方式删除它：

```
git branch -D name_of_the_branch
```
(rr-vcs-branches-practice)=
## 良好做法

分支应该用于 **保持主分支的净化**。 也就是说，主体只应包含完整、经过测试的工作，正确地属于项目的主要版本。 同样，您应该尝试尽可能保持各个分支的干净，只需要 **为分支添加一个新功能**。 这是因为您正在使用多个功能。 一些项目可能已经完成，准备合并为主项目，而另一些项目仍在开发之中。 保持分支干净意味着只在功能分支上做出与功能相关的更改。 给你的分支 **智能名称**, "新功能" 很好，直到你开始在另一个分支开发一个新的功能。

## 交互式教程

[学习 Git 分支](https://learngitbranching.js.org/) 是一个提供交互方式学习Git 的项目。 通过 通过他们的教程将提供最常用的 git 命令和分支操作技术的丰富经验。
