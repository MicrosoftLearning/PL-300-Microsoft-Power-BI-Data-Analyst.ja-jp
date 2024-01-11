---
lab:
  "\_\_ title": (Optional) Optimize model performance in Power BI
  "\_\_ module": Optimize model performance in Power BI
---

# (省略可能) モデル パフォーマンスを最適化する

## DirectQuery モデル設計を確認する

> **注**: このデモでは、別の Power BI Desktop ファイルを使用します。

1. D:\PL300\Demo\Resources\AW Sales Analysis.pbix ファイルを開きます。

1. データ ソースに接続するかどうかを確認するメッセージが表示されたら、[接続] をクリックします。

1. 右下隅で、データ モデルが DirectQuery テーブルで構成されていることを示します。

1. Power BI Desktop ファイルを D:\PL300\Demo\MySolution フォルダーに保存します。

1. モデル ビューで、2 つの関連するテーブルを含むモデル設計を紹介します。

1. レポート ビューで、[Fiscal Year] スライサーでさまざまな項目を選択してレポートを操作します。

1. 任意の月の列でドリルスルーして、注文の詳細を表示します。

1. [売上概要] ページに戻ります。

## クエリ パフォーマンスを確認する

1. [表示] リボン タブで、[パフォーマンス アナライザー] ペインを表示します。

1. ビジュアルを更新した後、スライサーと Sales by Month ビジュアルを展開します。

1. DirectQuery モードを使用したこと (データがデータ ソースから要求されたこと) を指摘します。

## デュアル ストレージ テーブルを構成する

1. モデル ビューで、[Date] テーブルを選択し、ストレージ モードとして [デュアル] を選択します。

1. データがインポートされたら、レポート ビューに切り替え、[パフォーマンス アナライザー] ペインでビジュアルを更新します。

1. [Date] テーブルがモデル キャッシュから照会されるようになったことを示します。

## 集計の作成

1. Power Query エディター ウィンドウを開き、[Queries] ペインで [Reseller Sales] クエリを複製します。

1. 新しいクエリの名前を [Reseller Sales Agg] に変更します。

1. 次のように、変換によるグループ化を適用します。

    - [OrderDate] でグループ化。

    - 新しい列: SalesAmount 列の合計である Sales。

1. 閉じてクエリを適用します。

1. モデル ビューで、[Reseller Sales Agg] テーブルのストレージ モードを [インポート] に設定します。

1. Date テーブルの Date 列から Reseller Sales Agg テーブルの OrderDate 列へのリレーションシップを作成します。列のカーディナリティが 1 対多で、Date テーブルが片側にあることを確認します。

1. [Reseller Sales Agg] テーブルで集計を管理します。

    - [OrderDate]: [Reseller Sales] テーブルの [OrderDate] 列でグループ化します。

    - [Sales]: [Reseller Sales] テーブルの [SalesAmount] 列を合計します。

1. 集計テーブルが非表示になったことを示します。

1. レポート ビューに切り替え、パフォーマンス アナライザー ペインでビジュアルを更新します。

1. [Sales by Month] テーブルがモデル キャッシュから照会されるようになったことを示します。

1. 任意の月からドリル スルーし、テーブルの詳細がデータ ソースから DirectQuery として要求されていることを示します。

1. Power BI Desktop ファイルを保存します。

1. Power BI Desktop を閉じます。

> **注**: この Power BI Desktop ソリューションを再使用することはありません。
