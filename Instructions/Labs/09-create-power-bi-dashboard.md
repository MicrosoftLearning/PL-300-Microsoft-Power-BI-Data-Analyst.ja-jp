---
lab:
  title: Power BI ダッシュボードを作成する
  module: Create Dashboards
---

# Power BI ダッシュボードを作成する

## ラボのストーリー

このラボでは、既存のレポートを使用して、Power BI サービスで **Sales Monitoring** ダッシュボードを作成します。

このラボでは、次の作業を行う方法について説明します。

- ダッシュボードに視覚化をピン留め
- Q&A を使用してダッシュボード タイルを作成する

**この配信には約 30 分かかります。**

## 作業の開始

この演習を完了するには、まず Web ブラウザーを開き、次の URL を入力して zip フォルダーをダウンロードします。

`https://github.com/MicrosoftLearning/PL-300-Microsoft-Power-BI-Data-Analyst/raw/Main/Allfiles/Labs/09-create-power-bi-dashboard/09-create-dashboard.zip`

フォルダーを **C:\Users\Student\Downloads\09-create-dashboard** フォルダーに展開します。

## **レポートを発行する**

このタスクでは、セマンティック モデルを作成してラボの環境を設定します。

1. Microsoft Edge ブラウザー ウィンドウで、Power BI サービスの **[マイ ワークスペース]** に移動します。

1. **[インポート]、[レポート] または [改ページ対応レポート]、[このコンピューターから]** の順に選択します。

1. **C:\Users\Student\Downloads\09-create-dashboard** フォルダーに移動します。

1. **09-Starter-Sales Analysis.pbix** ファイルを選択し、**[開く]** を選択します。

    > *セマンティック モデルの置換を求めるメッセージが表示されたら、**[置き換える]** を選択します。*

## **ダッシュボードを作成する**

このタスクでは、**Sales Monitoring** ダッシュボードを作成します。 レポートから視覚化をピン留めし、画像データの URI に基づいてタイルを追加し、Q&A を使用してタイルを作成します。

1. Power BI サービスで、**09-Starter-Sales Analysis** レポートを開きます。

1. **[概要]** ページで、**[年]** スライサーを **FY2020** に設定します。

    ![画像 4](Linked_image_Files/09-create-power-bi-dashboard_image17.png)

1. **[リージョン]** スライサーを **[すべて選択]** に設定します。

    > ''ピン留めされたビジュアルは、ピン留め時にフィルター コンテキストで設定されます。基になるビジュアルが変更された場合は、ダッシュボード タイルも更新する必要があります。時間ベースのフィルターの場合は、相対日付スライサー (または、相対時間ベースの質問を使用した Q&A) を使用することをお勧めします。''**

1. ダッシュボードを作成してビジュアルをピン留めするには、 **[月別売上と利益率]** (列/行) 視覚化にカーソルを合わせ、プッシュピンを選択します。

    ![画像 43](Linked_image_Files/09-create-power-bi-dashboard_image18.png)

1. **[ダッシュボードにピン留めする]** ウィンドウで、 **[ダッシュボード名]** ボックスに「**Sales Monitoring**」と入力してから、 **[ピン留め]** を選択します。

    ![図 3](Linked_image_Files/09-create-power-bi-dashboard_image19.png)

1. **[マイ ワークスペース]** を開き、**Sales Monitoring** ダッシュボードを開きます。

1. ダッシュボードに 1 つのタイルがあることがわかります。

    ![画像 45](Linked_image_Files/09-create-power-bi-dashboard_image22.png)

1. 質問に基づいてタイルを追加するには、ダッシュボードの左上にある **[データについて質問する]** を選択します。 

    *Q&A 機能を使用して質問することができ、Power BI はビジュアルを使用して応答します。*

    ![画像 7](Linked_image_Files/09-create-power-bi-dashboard_image23.png)

1. Q&A ボックスの下に提案された質問のいずれかを選択し、応答を確認します。

1. [Q&A] ボックスからすべてのテキストを削除し、「**Sales YTD**」と入力します

1. **(空白)** の応答に注目します。

    > *「**Power BI Desktop で高度な DAX 計算を作成する**」ラボで **[Sales YTD]** メジャーを追加したことを思い出してください。このメジャーはタイム インテリジェンス式であり、結果を生成するには **[Date]** テーブルにフィルターを適用する必要があります。*

    ![画像 14](Linked_image_Files/09-create-power-bi-dashboard_image25.png)

1. 質問を **in year FY2020** (FY2020 年度の) で拡張します。

1. 応答が **$33M** になったことに注意してください。

    ![画像 13](Linked_image_Files/09-create-power-bi-dashboard_image27.png)

1. 応答をダッシュボードにピン留めするには、右上隅にある **[ビジュアルをピン留めする]** を選択します。

    ![画像 15](Linked_image_Files/09-create-power-bi-dashboard_image28.png)

1. **Sales Monitoring** ダッシュボードにタイルをピン留めするように求めるメッセージが表示されたら、**[ピン留めする]** を選択します。

1. ダッシュボードに戻るには、左上隅にある **[Q&amp;A の終了]** を選択します。

1. 会社のロゴを追加するには、メニュー バーの **[編集]** を選択してから、 **[タイルの追加]** を選びます。
    
    > ''この手法を使用してダッシュボード タイルを追加すると、Web コンテンツ、画像、リッチな書式設定のテキスト ボックス、ビデオ (YouTube または Vimeo リンクを使用) などのメディアを使ってダッシュボードを強化できます。''**

1. (右側にある) **[タイルの追加]** ペインで、 **[画像]** タイルを選んでから、 **[次へ]** 選択します。

1. **[画像タイルの追加]** ペインの **[URL]** ボックスに、**C:\Users\Student\Downloads\09-create-dashboard\AdventureWorksLogo_DataURL.txt** ファイルにある完全な URL を入力してから、**[適用]** を選択します。
    
    > *その URL を使用して画像を埋め込むことも、データ URL を使用してコンテンツをインラインで埋め込むこともできます。*

1. ロゴ タイルのサイズを変更するには、右下隅をドラッグし、タイルのサイズを 1 単位の幅、1 単位の高さに変更します。
    
    > ''タイルのサイズは、長方形に制限されます。''**

1. ロゴが左上に、**[Sales YTD](売上 YTD)** タイルがその下に、**[Sales, Profit Margin](売上、利益率)** タイルが右側に表示されるようにタイルを整頓します。

    ![画像 52](Linked_image_Files/09-create-power-bi-dashboard_image35.png)

## **タイルの詳細を編集する**

このタスクでは、2 つのタイルの詳細を編集します。

1. **[Sales YTD](売上 YTD)** タイルにカーソルを合わせ、タイルの右上にある省略記号を選択してから、**[詳細の編集]** を選択します。

    ![画像 50](Linked_image_Files/09-create-power-bi-dashboard_image36.png)

1. (右側にある) **[タイルの詳細]** ペインで、 **[サブタイトル]** ボックスに「**FY2020**」と入力してから、 **[適用]** を選択します。

1. **[Sales YTD](売上 YTD)** タイルにサブタイトルが表示されていることに注意してください。

    ![画像 21](Linked_image_Files/09-create-power-bi-dashboard_image39.png)

1. **[Sales, Profit Margin](売上、利益率)** タイルのタイル詳細を編集します。

1. **[タイルの詳細]** ペインの **[機能]** セクションで、 **[最終更新日時の表示]** をオンにしてから、 **[適用]** を選択します。

    ![画像 22](Linked_image_Files/09-create-power-bi-dashboard_image40.png)

1. タイルに最終更新日時 (Power BI Desktop でデータ モデルを読み込むときに行ったもの) が表示されていることに注意してください。

*次の演習では、セマンティック モデルを更新します。データとレポートに応じて、いつでもアドホック データ更新を実行したり、スケジュールを設定したりできます。しかし、スケジュールされた更新には、このラボ用に構成できないゲートウェイが必要です。そのため、Power BI Desktop から手動でデータ更新を実行し、ファイルをワークスペースにアップロードします。*

## **セマンティック モデルを更新する**

この演習では、最初に 2020 年 6 月の販売注文データを **AdventureWorksDW2020** データベースに読み込みます。 次に、Power BI Desktop ファイルを開き、データ更新を実行し、ワークスペースにファイルをアップロードします。

> ***注**: データベースに接続できない場合は、**09-Solution-Sales-Analysis.pbix** ファイルを使用できます。 データベースを更新してセマンティック モデルを更新するのではなく、ソリューション ファイルを **[マイ ワークスペース]** にアップロードし、次のタスクで参照されている変更内容を確認してください。*

## **ラボ データベースを更新する**

このタスクでは、PowerShell スクリプトを実行して、**AdventureWorksDW2020** データベース内のデータを更新します。

1. エクスプローラーで、**C:\Users\Student\Downloads\09-create-dashboard** フォルダー内の **UpdateDatabase-2-AddSales.ps1** ファイルを右クリックし、**[PowerShell で実行]** を選択します。

    ![画像 28](Linked_image_Files/09-create-power-bi-dashboard_image46.png)

1. 実行ポリシーを変更するよう求められた場合は、**A** キーを押します。

1. キーを押して閉じるように求められたら、**Enter** をもう一度押します。

"**AdventureWorksDW2020** データベースに、2020 年 6 月に行われた販売注文が含まれるようになりました。"**

## **Power BI Desktop ファイルを最新の情報に更新する**

このタスクでは、**09-Starter-Sales Analysis** Power BI Desktop ファイルを開き、データ更新を実行して、そのファイルを **Sales Analysis** ワークスペースにアップロードします。

1. Power BI Desktop ファイルの **[データ]** ペインで、**Sales** テーブルを右クリックして **[データの更新]** を選択します。

    ![画像 55](Linked_image_Files/09-create-power-bi-dashboard_image47.png)

1. 更新が完了したら、Power BI Desktop ファイルを保存します。

1. ファイルをワークスペースに発行するには、 **[ホーム]** リボン タブの **[共有]** グループ内から、 **[発行]** を選択し、 **[選択]** を選んで発行します。

    ![画像 59](Linked_image_Files/09-create-power-bi-dashboard_image48.png)

1. セマンティック モデルの置換を求めるメッセージが表示されたら、**[置き換える]** を選択します。

1. Power BI Desktop を閉じます。

*Power BI サービス内のセマンティック モデルには、2020 年 6 月の売上データが含まれるようになりました。*

### **ダッシュボードを確認する**

このタスクでは、ダッシュボードを確認して、売上が最新の情報に更新されたことに注目します。

1. Microsoft Edge ブラウザー ウィンドウで、Power BI サービスを開き、 **[マイ ワークスペース]** の **Sales Monitoring** ダッシュボードを確認します。

2. **[Sales, Profit Margin]** タイルのサブタイトルで、データが **Refreshed: NOW** となっていることに注目してください。

3. **2020 Jun** の列があることにも注目してください。

    > "2020 年 6 月のデータがない場合は、**F5** キーを押して Web ブラウザーをもう一度読み込む必要があります。"**

    ![画像 33](Linked_image_Files/09-create-power-bi-dashboard_image50.png)

## ラボが完了しました
