---
demo:
  title: Power BI でデータ モデルを設計する
  module: Design a data model in Power BI
---
# Power BI でデータ モデルを設計する

## モデルを確認する

1. [データ] ペインで、すべてのテーブルを展開してすべてのフィールドを表示します。

1. [Sales] テーブルで、自動的に作成された [OrderDate] 階層を示します。

1. 次のデモで Date テーブルが作成されることを説明します。

1. モデル ビューで、2 つのテーブル間に自動的に作成されたリレーションシップにカーソルを合わせます。

1. フィルターが [Product] テーブルから [Sales] テーブルにどのように伝達するかを説明します。

## 階層の作成

1. [Product] テーブルの [Category] 列に基づいて階層を作成します。

1. 階層の名前を [Products] に変更します。

1. 第 2 レベルとして [Product] 列を追加します。

## モデル プロパティを設定する

1. 両方の [ProductID] 列を非表示にします。

1. 桁区切り記号を使用するように [Quantity] 列を書式設定します。

1. [Sales] 列と [Unit Price] 列を複数選択し、小数点以下 2 桁を使用するように書式設定します。

## マトリックス ビジュアルによるモデル設計を検証する

1. レポート ビューで、ページにマトリックス ビジュアルを追加し、ページ全体に表示されるようにサイズを変更します。

1. [Products] 階層を行に追加し、[Quantity]、[Sales]、[Unit Price] の各フィールドを追加します。

1. [Products] 階層のすべてのレベルを展開します。

1. [Unit Price] 値は価格の合計であり、正しくないことを示してください。

1. [データ] ペインで、[Unit Price] フィールドを選び、[平均] を使うように集計を構成します。

1. マトリックス ビジュアルから [Sum of Unit Price] 列を削除し、[Unit Price] フィールドを再度追加します。

1. Power BI Desktop ファイルを保存します。

1. Power BI Desktop ファイルは、次のデモ用に開いたままにしておきます。
