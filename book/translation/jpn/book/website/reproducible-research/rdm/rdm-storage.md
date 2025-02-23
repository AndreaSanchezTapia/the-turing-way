(rr-rdm-storage)=
# データの保存と組織

データ損失はあなたの研究プロジェクトにとって壊滅的なものであり、頻繁に起こる可能性があります。 適切なストレージソリューションを選択し、データを頻繁にバックアップすることで、データの損失を防ぐことができます。

```{figure} ../../figures/version-control.jpg
---
height: 500px
name: version-control
alt: バージョン管理の利点を表す2つの画像が表示されます。 左側にテーブルの上に青い箱の中を２人の人が揺れている様子が映っています 箱は入り乱れた文書でいっぱいで、人々は混乱し、イライラして見えます。 ドキュメント名は「final 2」、「これをfinal」とします。 右側では、同じ2人は幸せに見えると青いファイリングキャビネットに明確に整理されたファイルを検索しています。 ファイルを整理する "V1、V2、V3、V4" の区切りがあります。
---
_Scriberiaによるチューリング方法_プロジェクトのイラスト。 善王堂原本。 [http://doi.org/10.5281/zenodo.3695300](http://doi.org/10.5281/zenodo.3695300)
```

(rr-rdm-storage-where)=
## データを保存する場所

- ほとんどの教育機関は、データを保存するために使用できる _ネットワークドライブ_ を提供します。
- _メモリスティック(USBスティック)などのポータブル記憶媒体_ は、より危険であり、損失や損傷に対して脆弱です。
- _クラウドストレージ_ は、データの保存、バックアップ、取得に便利な方法を提供します。 研究データに使用する前に利用規約を確認してください。

特に個人データや機密データを扱っている場合は クラウドオプションがデータ保護規則に準拠していることを確認する必要があります セキュリティの追加層を追加するには、必要に応じてデバイスとファイルを暗号化する必要があります。

教育機関が、使用できるものを制限するローカルストレージソリューションやポリシーやガイドラインを提供する場合があります。 したがって、私たちはあなたのローカルポリシーと推奨事項を理解することをお勧めします。

より広いコミュニティにデータを公開する準備ができたら。 [FAIRsharing](https://fairsharing.org/databases)で適切なデータベースやリポジトリを検索することもできます。 データの種類とデータへのアクセスの種類によって異なります これについての詳細は、 {ref}`rr-rdm-sharing` のサブ章を参照してください。

(rr-rdm-storage-organization)=
## データ組織

データを整理するには、フォルダ構造を作成できます。 または以前の構造 (下の例を参照) を再利用して、ファイルを確実に見つけることができます。

-   ファイルが正しいフォルダに保存され、それらが属していないフォルダに散在しないように、十分な(サブ)フォルダがあることを確認してください。 1つのフォルダに大量に保存されています
-   明確なフォルダ構造を使用します。 データ/フォルダを生成した人に基づいてフォルダを構成できます(月、年、年)。 セッション)、プロジェクト毎(以下の例で行う)、または分析方法/機器またはデータタイプに基づいています。

(rr-rdm-storage-organization-examples)=
### データ組織の例

- Nikola Vukovicによるこの [](http://nikola.me/folder_structure.html) フォルダ構造をダウンロード
- You can pull/download folder structures using GitHub: [This template](https://github.com/bvreede/good-enough-project) by Barbara Vreede, based on [cookiecutter](https://github.com/cookiecutter/cookiecutter), follows recommended practices for scientific computing by [Wilson et al. (2017)](https://doi.org/10.1371/journal.pcbi.1005510).
- [Open Science Framework](https://osf.io/4sdn3/) のファイル組織については、Chris Hartgerink による [このテンプレート](https://osf.io/) を参照してください。

(rr-rdm-storage-conventions)=
## ファイル命名規則

ファイル名を構成し、このためのテンプレートを設定します。 例えば、各ファイルが生成された日付( `YYYYMMDD` など)でファイルの名前を付け始めることが有利です。 これは、ファイルを時系列にソートし、各ファイルの一意の識別子を作成します。 上書きを避けるためにバージョン化する必要がある同じ日に複数のファイルを生成するとき、このプロセスのユーティリティは明らかです.


ファイル名を指定するためのその他のヒント:
- 実験の日付または日付の範囲を使用してください: `YYYYMMDD`
- ファイルの種類を使用
- 研究者の名前/イニシャルを使用
- ドキュメントで使用されているファイルのバージョン番号(v001、v002)または言語(ENG)を使用してください
- ファイル名が長すぎないようにします（ファイル転送が複雑になる可能性があります）
- 特殊文字（?\!@\*%{[<>]）とスペースを避けてください

ファイルの命名規則をREADME.txtファイルで説明すると、ファイル名が何を意味するのか他の人にも明らかになります。

(rr-rdm-storage-backups)=
## バックアップ

データを失うことを避けるためには、適切なバックアッププラクティスに従ってください。

- 2つまたは3つのファイルのコピーが保存されている必要があります。
- 少なくとも2つの異なる記憶媒体があります
- 様々な場所で行われています

データが重要になり、データセットが変更される頻度が増えるほど、データをバックアップする頻度が増えます。 あなたのファイルが大量のスペースを占有し、それらのすべてをバックアップすることが困難であるか、または高価であることが証明されます。 データをバックアップする際の基準を作成したいと思うかもしれません これは、データ管理計画(DMP)の一部になります。
