(rr-rdm-personal)=

## 個人データ管理
このセクションでは、個人データを扱う際に考慮すべき事項の概要を説明します。 再現性を促進するツールと実践に関するより実用的な概要については、 {ref}`機密データプロジェクト<pd-sdp>` 章を参照してください。

### 個人データ

個人情報とは、あなたが処理しているデータを使用して特定できる **生きている人** に関する情報です。 直接的または間接的に(例えば、個人の名前、住所、またはその社会保障番号などの他の一意の識別子)。 "[故人に関連するデータは、GDPRの下でほとんどの場合、個人データとはみなされません](https://gdpr.eu/eu-gdpr-personal-data/)。 間接的な識別子には、健康、経済、文化または社会的特性が含まれます。 特に、これらの識別子の特定の組み合わせを使用して個人を識別する場合、データを適切に管理するように注意する必要があります。 特に機密性の高いデータには、個人に関するデータが含まれます:
* 人種/<unk>
* 政治的な意見は
* 宗教/哲学的信仰format@@0
* 労働組合のメンバー
* 遺伝的および生体メトリックデータは
* 身体的または精神的な健康
* 性的指向は

### 個人データポリシー
個人データに関する個人の権利を保護するために、さまざまな国でさまざまなポリシーが実施されています。 たとえば、オーストラリアでは、 [オーストラリアプライバシー法](https://www.oaic.gov.au/privacy/the-privacy-act/)に基づいて個人データが規制されています。 欧州連合では、 **GDPR** (General Data Protection Regulation) が個人データの処理に適用され、データ保護影響評価 ([DPIA](https://youtu.be/YRiCb3unz3g?t=988)) を実施する必要があります。 処理とは、収集、保存、分析、共有、削除、破壊など、個人の情報に対して何でも行うことを意味します。 機密データの管理の要件が最新であることを確認するには、研究に適用される国/機関の方針を確認してください。 臨床試験データを共有するための推奨プラクティスについては、 {cite}`Smith2015participantdata` を参照してください。


(rr-rdm-informated-consent)=

### Informationed consent

研究に参加するための情報, 任意かつ公正な同意は、人間の参加者を含む任意の研究プロジェクトにとって非常に重要です. この同意プロセスにより、研究者は特定の研究に参加することが彼らにとってどのような意味を持つのかを理解することができます。 それぞれの人は、同意フォームを使用して参加するかどうかを選択できます。 倫理的研究のための {ref}`ガイド<er>` も参照してください。

インフォームドコンセントフォームは個人データとみなされるため、他の個人データと同じ注意を払って処理する必要があることに注意してください。 収集した残りのデータを保存する同意フォームを保存しないでください。 たとえば、別のロックされたキャビネットや暗号化されたフォルダを使用します。

書面による同意書を使用できない場合は、同意書の記録を行ってください。

**同意したドキュメントは次のとおりです:**

* 参加者情報シートと

* 参加者が署名した同意書。

**参加者情報シート** は、研究について参加者に知らせるために使用されます。 情報は明確で理解しやすく、次の内容をカバーする必要があります:
* プロジェクトは何についてです。
* 彼らの参加が関与するもの。
* これらのリスクを最小限に抑えるために参加者や安全対策にかかわるリスク。
* データセキュリティと参加者の守秘性に関する保証。
   * データにアクセスできるユーザーのコメント
* 研究でデータがどのように使用されるか(公開された記事、レポート、プレゼンテーション用)。
* 研究の終わりにデータをアーカイブするための提案された計画とデータの将来の二次的な再利用の可能性.
    * 段階的な同意は、参加者が公開される情報の種類を選択できるようにすることで、ここで解決策になるかもしれません。
* 研究を統括する組織の詳細。
* 研究についての詳細については、誰に連絡するか。

**同意フォーム** は、研究参加者が研究に理解し、同意することを検証するために使用されます。 同意フォームは、以下の点を最小限に抑える必要があります。
* 参加者
    * 参加者情報シートを読んで理解しました
    * 質問する機会が与えられています
    * 参加が自主的であることを理解し
    * 理由も罰もなしにいつでも退学することを理解しています
    * (情報シートに詳述されているように) データの管理、共有、アーカイブ方法を理解しています
       * データが再利用される可能性を高めるために データを削除することを約束するのではなく、データを保持し共有することへの同意を求めます（ {cite}`Meyer2018personaldata` を参照）
* 参加者と研究者の署名と締切日時

先に考えて、あなたがどのようにするかを計画してください:

* データの収集、保存、管理（ {ref}`データストレージと組織<rr-rdm-storage>` を参照）

* アクセス権限の制御

* 可能であれば、プロジェクトの最後にアーカイブ/共有のためのデータを準備します ( {ref}`データの共有とアーカイブ<rr-rdm-sharing>` を参照してください)


(rr-rdm-privacy)=

研究対象のプライバシーを **保護する** ために採用できる戦略はいくつかあります。

**1. データの最小化**

* 個人情報が必要でない場合は、収集しないでください。
* 不要な識別情報を保持しているかどうかを定期的に確認します。
* 識別情報が不要になった場合は、安全に削除、削除または破棄します。

**2. データ保持制限**
* 直接識別子を削除する前に識別可能なデータを保持する時間、より複雑な匿名化技術を適用する時間、またはデータを完全に削除する時間を決定します。
* 機密データを削除する場合、ファイルを削除するための標準的な方法(例えば、ファイルをごみ箱に移動し、空にするなど)は安全ではないことに注意する必要があります。 これらの削除されたファイルは回復することができます。 BleachBitのようなソフトウェアを使用して、データを安全に削除します。

**3. セキュアなデータ転送**
* 個人データを転送することを決定する前に、識別可能なデータの転送が必要かどうかを検討する必要があります。 たとえば、データは識別されない、または匿名化される可能性がありますか?
* データが特定できない場合は、個人データを転送する権限を持っていることを確認する必要があります。 輸送前と輸送後のデータを保護するための適切な保護手段が用意されています
* 多くの場合、あなたの大学や研究所は安全なファイル転送のためのソリューションを提供します。 調査データ、プライバシーまたはITサポートチームにお問い合わせください。

**4. 暗号化**
* 暗号化は、関連する暗号化キー(またはパスワード)を持つ人だけがコンテンツにアクセスできるようにすることによって保護を提供します。
    * ディスクレベルで保護: Windows用のBitlocker、MacOS用のFileVault
    * 「コンテナ」レベル（複数のファイルを含むフォルダ）で保護: Veracrypt (または Archive for MacOS)
    * ポータブルストレージ: Bitlocker
    * ファイル レベル / 交換情報:
      * 簡単な方法：7zipを使用し、パスワードを詰めてください
      * より複雑な設定：PGP ツールを使用（安全にメールを送信することもできます）
    * 詳細およびステップバイステップガイド [Ghent University Encryption for Research manual](https://osf.io/nx8km/) をご覧ください。

**5. アクセス許可**
* 共有フォルダの権限の管理。
* パスワード保護。


**6. Anonymisation**

匿名化は、データセット内の識別情報が削除されるプロセスです。 主に、情報の損失を制限しながら、機密情報を明らかにすることなくデータを共有または公開できるようにするために使用されます。
* 可能な場合、直接識別子（名前、住所など） 識別情報が不要になったらすぐに電話番号と口座番号を削除する必要があります。 データを削除するか、仮名で置き換えることができます。 定性的なデータについては、インタビューを転写する際に、特定の特性を置き換えるか、一般化する必要があります。
* リンクファイル(たとえば、データ主体を識別可能な個人にリンクさせる情報)を使用して再度識別されるデータは、偽名データと呼ばれます。 注意: この場合、リンクファイルは暗号化され、特定されていない研究データとは別に安全に保存される必要があります。
  * 匿名化されたデータまたは識別されていないデータにおける個人の識別は、間接的な識別子の組み合わせ(年齢など)を使用しても可能です。 教育、雇用、地理的領域および医療条件)。 さらに、小さなセル数を含むデータと出力は、潜在的に開示される可能性があります。 特に、小集団からサンプルを採取したり、極端な値または比較的まれな特性を持つケースを含む場合。
   * そのため、潜在的に識別可能なデータまたはデータから生成された出力を共有しようとする場合。 統計的開示管理(SDC、詳細については [このハンドブック](https://securedatagroup.org/sdc-handbook/) を参照してください)など、より高度な匿名化技術を考慮する必要があるかもしれません。
* For more information about anonymisation you can watch [this webinar by Enrico Glerean](https://www.youtube.com/watch?v=ILXeA4fx3cI).

**7. 機密データの共有**

データを共有または公開する場合は、データが適切で安全に共有できることを確認する必要があります。 たとえば、データが適切に匿名化されるかどうかを検討する必要があります。 匿名化されたデータが役に立つかどうか( {ref}`データ共有の障壁も<rr-rdm-sharing>`オープンリサーチチャプターを参照)。 機密データの識別と匿名化を解除する方法を適用した後でも、再同定のリスクが残る可能性があります( {cite}`Meyer2018personaldata` を参照)。

追加の安全対策、すなわち匿名化に代わるものとして、データが適切かつ安全に共有されるようにアクセス制御を適用しています。 This may involve finding a data repository which can provide suitable access controls (see [here](https://osf.io/tvyxz/wiki/8.%20Approved%20Protected%20Access%20Repositories/) for a list of protected Access Repositories). これらのリポジトリは、プロジェクトのメタデータへのアクセスを提供することができます。これにより、他のリポジトリは見つけることができ、 {ref}`はデータ<cm-citable-cite>` を引用できます。 制限付き/条件付きアクセスは、データにアクセスするために必要な情報を再利用者に提供し、データ {ref}`FAIR <rr-rdm-fair>` を作成します。 たとえば、データにアクセスする条件には、次のような潜在的なデータが必要になる可能性があります。
  * 登録および/または連絡先の詳細を提供して、再利用者が本物であることを確認し、その責任を認識します。
  * データの使用方法に関する情報を提供する
  * 条件に同意します (データセキュリティ、プライバシー、同意フォームに含まれる制限)

**リソース**
* [](https://mantra.edina.ac.uk/protectionrightsandaccess) MANTRA [による機密データコース](https://mantra.edina.ac.uk) の保護
* {cite}`Meyer2018personaldata`.
* [Presentations](https://www.youtube.com/watch?v=J9kWkzK83i4&list=PLyeHH3bEQqIbgbw75gheV27nFF2ctPPpR&index=1) by [Zosia Beckles](https://youtu.be/J9kWkzK83i4), [Michele Voznick](https://youtu.be/w5v5d6r6irs) and [Tessa Darbyshire](https://youtu.be/jEFu1ykVI_I) on Responsible Data Management: Legal & Ethical Aspects as part of the [Fail to Nail it sessions](https://www.youtube.com/c/AI4ScientificDiscovery).
* [プレゼンテーション](https://www.youtube.com/watch?v=H2mv6q4WwOU&) Rob GommansによるGDPRおよび科学的研究目的のための(識別可能な)画像の処理、オーディオ、およびビデオデータ。
* [プレゼンテーション](https://youtu.be/_3bufely0c0) 脳の研究データと個人データプライバシーに関するスティーヴン・ヒューニスによるプレゼンテーション:共有し、保護するための実用的なヒント。
* [プレゼンテーション](https://youtu.be/eAKhI0qde2w?t=1104) format@@2 GDPRでインフォームドコンセントテンプレート(18:30 - 38:50)などのリソースを使用します。
* [プレゼンテーション](https://www.youtube.com/watch?v=PSe2V1KTQ8w&) アアルト大学のエンリコ・グレリアンとPa<unk> Lindstro<unk> m による個人データの取り扱いに関する。 詳細はこちら [をご覧ください](https://www.aalto.fi/en/services/rdm-training)。
* [プレゼンテーション](https://www.youtube.com/watch?v=J457qBdQ3xo) ロザリー・サラームによるGDPR.
* [プレゼンテーション](https://vimeo.com/362161972) と [記事](https://www.smashingmagazine.com/2017/07/privacy-by-design-framework/) をデザインで **プライバシーについて**。
* [Hina Zahidによるデータ共有における倫理的および法的問題に関するプレゼンテーション](https://www.youtube.com/watch?v=2WebuDlzEIw&list=PLG87Imnep1Sln3F69_kBROUrIbT5iderf&index=2)。
* [Hanne ElsenによるプライバシーとリサーチライフサイクルにおけるGDPRのスライド](https://osf.io/5xhya/)。
* [データ共有のためのデータデ識別手順に関するワークショップ資料](https://osf.io/em3da/)。
