---
demo:
  course: 'PL-300, DP-605'
  title: Power BI で DAX を使ってメジャーを作成する
  module: Create measures using DAX in Power BI
---
# Power BI で DAX を使ってメジャーを作成する

> **ヒント**: すべての計算は、D:\Allfiles\Demo\Resources\Snippets-Demo-05.txt ファイルからコピーできます。

## 計算テーブルを作成する

1. 次の式を使用して、計算テーブルを作成します。

```dax
Date = CALENDARAUTO()
```

1. データ ビューに切り替え、単一の日付列で構成されるテーブルを確認します。

計算列の作成

1. [Date] テーブルに計算列を追加します。

```dax
Year = "CY" & YEAR('Date'[Date])
```

1. [Date] テーブルに別の計算列を追加します。

```dax
Month = FORMAT('Date'[Date], "YYYY-MM")
```

1. モデル ビューで、[Date] テーブルの [Date] 列を [Sales] テーブルの [OrderDate] 列にドラッグしてリレーションシップを作成します。

1. [Sales] テーブルの [OrderDate] 列を非表示にします。

1. Date テーブルで、Year と Month のレベルを持つ Calendar 階層を作成します。

1. レポート ビューで、Date 列を使用して Date テーブルを日付テーブルとしてマークします。

1. マトリックス ビジュアルで、[Products] 階層を削除し、[Calendar] 階層に置き換えます。

1. [Sales] テーブルに計算列を追加します。

```dax
Cost = 'Sales'[Quantity] * RELATED('Product'[Cost])
```

1. [Cost] 列を小数点以下 2 桁に書式設定します。

## クイック メジャーを作成する

1. Sales テーブルにクイック メジャーを追加し、Cost 列を Profit 列から減算します。

1. メジャーの名前を [Profit] に変更します。

1. メジャーがモデルにデータを保存しないことを説明します。

標準メジャーを作成する

1. [Sales] テーブルにメジャーを追加します。

```dax
Profit Margin = DIVIDE([Profit], SUM('Sales'[Sales]))
```

1. [Profit Margin] 列をパーセンテージとして書式設定します。

1. Sales テーブルに別のメジャーを追加します。

```dax
Sales YTD = TOTALYTD(SUM('Sales'[Sales]), 'Date'[Date])
```

1. [Sales YTD] 列を小数点以下 2 桁に書式設定します。

## マトリックス ビジュアルを使用して計算を検証する

1. [Cost]、[Profit]、[Profit Margin]、[Sales YTD] の各フィールドをマトリックス ビジュアルに追加します。

1. Power BI Desktop ファイルを保存します。

1. Power BI Desktop ファイルは、後のデモ用に開いたままにしておきます。
