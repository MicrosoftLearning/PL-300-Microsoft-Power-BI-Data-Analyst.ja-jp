---
demo:
  course: 'PL-300, DP-605'
  title: Power BI でのデータのクリーン化、変換、読み込み
  module: 'Clean, transform, and load data in Power BI'
---

# Power BI でのデータのクリーン化、変換、読み込み

## クエリに変換を適用する

1. 最初に、Product クエリに変換を適用します。

1. [RetailPrice]、[Photo]、[Sales] 列を削除します。

1. [Channels] 列のデータ型を [整数] に変更します。

1. 次の列の名前を変更します。

    - ProductSKU → SKU

    - ProductName → Product

    - ProductCategory → Category

    - ItemGroup → Item Group

    - KitType → Kit Type

1. 次に、Sales クエリに変換を適用します。

1. 以下を除くすべての列を削除します。

    - OrderDate

    - ProductID

    - Quantity

    - UnitPrice

1. [UnitPrice] 列のデータ型を [固定小数点数] に変更します。

1. [UnitPrice] 列の名前を [Unit Price] に変更します。

1. [Quantity] と [Unit Price] 列を複数選択し、それらの乗算に基づいて新しい列を追加します。

1. 新しい列の名前を [Sales] に変更します。

## クエリの統合

1. Excel コネクタを使用して新しいクエリを作成し、D:\Allfiles\Demo\Data\ProductCost.xlsx ファイルに接続します。

1. [Product] 列を削除します。

1. [ProductCost] 列のデータ型を [固定小数点数] に変更します。

1. Product クエリを選択したら、SKU 列に関連する ProductCost クエリと結合します。

1. [プライバシー レベル] ウィンドウで、[D:\] のプライバシー レベルを [組織] に設定します。

1. ProductCost 列を展開して、ProductCost 列を含めます (ProductCost クエリから)。

1. 新しい列の名前を [Cost] に変更します。

## データ モデルへのクエリーを無効化してロードする

1. [クエリ] ペインで、[ProductCost] クエリを無効にします。

1. [ホーム] リボン タブで、[閉じて適用] アイコンをクリックします。

1. Power BI Desktop で、[データ] ペインの 2 つのテーブルを指定します。

1. Power BI Desktop ファイルを保存します。

1. Power BI Desktop ファイルは、次のデモ用に開いたままにしておきます。
