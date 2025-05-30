---
lab:
  title: Power BI Desktop でレポートを強化する
  module: Create Reports in Power BI desktop
---

# Power BI Desktop でレポートを強化する

## ラボのストーリー

このラボでは、高度なデザイン機能を使用して **Sales Analysis** を強化します。

このラボでは、次の作業を行う方法について説明します。

- スライサーを同期する
- ドリルスルー ページを作成する
- 条件付き書式の適用
- ブックマークとボタンを作成して使用する

**この配信には約 45 分かかります。**

## 作業の開始

この演習を完了するには、まず Web ブラウザーを開き、次の URL を入力して zip フォルダーをダウンロードします。

`https://github.com/MicrosoftLearning/PL-300-Microsoft-Power-BI-Data-Analyst/raw/Main/Allfiles/Labs/07-design-report-in-power-bi-desktop-enhanced/07-enhanced-report.zip`

フォルダーを **C:\Users\Student\Downloads\07-enhanced-report** フォルダーに展開します。

**07-Starter-Sales Analysis.pbix** ファイルを開きます。

> ***注**: **[キャンセル]** を選択すると、サインインを閉じることができます。 他のすべての情報ウィンドウを閉じます。 変更の適用を求めるメッセージが表示されたら、**[後で適用]** を選択します。

## スライサーを同期する

このタスクでは、**Year** と **Region** スライサーを同期し、「**Power BI Desktop でレポートをデザインする**」ラボで作成されたレポートの開発を続けます。

1. Power BI Desktop の **[概要]** ページで、**[年]** スライサーを **FY2018**に設定します。

1. **[My Performance]** ページに移動すると、**[Year]** スライサーの値が異なっていることがわかります。

    > "スライサーが同期されていないと、データが誤って表示され、レポート ユーザーのフラストレーションにつながる可能性があります。ここで、レポート スライサーを同期します。"**

1. **[概要]** ページに戻り、**[年]** スライサーを選択します。

1. **[表示]** リボン タブの **[ペインを表示する]** グループ内の **[スライサーの同期]** を選択します。

     ![画像 1](Linked_image_Files/08-design-report-in-power-bi-desktop-enhanced_image13.png)

1. **[スライサーの同期]** ペイン (**[視覚化]** ペインの左側) の 2 番目の列 (同期中を表します) で、**[Overview]** ページと **[My Performance]** ページのチェックボックスをオンにします。

     ![画像 93](Linked_image_Files/08-design-report-in-power-bi-desktop-enhanced_image14.png)

1. **[Overview]** ページで、**[Region]** スライサーを選択します。

1. スライサーを **[Overview]** ページおよび **[Profit]** ページと同期します。

     ![画像 94](Linked_image_Files/08-design-report-in-power-bi-desktop-enhanced_image15.png)

1. さまざまなフィルター オプションを選択してスライサーの同期をテストし、同期されたスライサーが同じ選択でフィルター処理されることを確認します。

1. **[スライサーの同期]** ページを閉じるには、**[ビュー]** リボン タブにある **[スライサーの同期]** オプションを選択します。

## ドリルスルーページを構成する

この演習では、新しいページを作成し、ドリルスルー ページとして構成します。 設計が完了すると、ページは次のようになります。

![カード ビジュアルとテーブル ビジュアルで構成される新しいページのイメージ。](Linked_image_Files/08-design-report-in-power-bi-desktop-enhanced_image17.png)

1. **"Product Details"** という名前の新しいレポート ページを追加します。

1. **[Product Details]** ページ タブを右クリックし、**[ページを非表示にする]** を選択します。

    > "レポート ユーザーがドリルスルー ページに直接アクセスすることはできません。*他のページのビジュアルからアクセスする必要があります。このラボの最後の演習では、このページにドリルスルーする方法を学習します。"*

1. **[視覚化]** ペインの下にある **[ドリルスルー]** セクションで、**Product \| Category** フィールドを **[Add Drill-Through Fields Here](ドリルスルー フィールドをここに追加します)** ボックスに追加します。

    > "このラボでは、フィールドを参照するために簡略表記を使用します。*次のようになります。**Product \| Category**。この例では、**Product** はテーブル名、**Category** はフィールド名です。"*

     ![画像 96](Linked_image_Files/08-design-report-in-power-bi-desktop-enhanced_image20.png)

1. ドリルスルー ページをテストするには、ドリルスルー フィルター カードで **[Bikes]** を選択します。

     ![画像 99](Linked_image_Files/08-design-report-in-power-bi-desktop-enhanced_image21.png)

1. レポート ページの左上にある矢印ボタンにお気付きでしょうか。

    > "フィールドがドリル スルー ウェルまたは領域に追加されると、矢印ボタンが自動的に追加されます。これを使うと、レポート ユーザーがドリルスルー元のページに戻ることができます。"**

1. ページに**カード** ビジュアルを追加し、サイズを変更して、ボタンの右側に配置し、ページの残りの幅を埋めるようにします。

    ![画像 13](Linked_image_Files/08-design-report-in-power-bi-desktop-enhanced_image23.png)

    ![画像 101](Linked_image_Files/08-design-report-in-power-bi-desktop-enhanced_image24.png)

1. カードのビジュアルに **Product \| Category** フィールドをドラッグします。

1. 視覚化の書式オプションを構成してから、**[カテゴリ ラベル]** プロパティを **[オフ]** にします。

     ![画像 103](Linked_image_Files/07-design-report-in-power-bi-desktop_image36b.png)

1. **[効果] > [背景色]** プロパティを、''白、20% 暗い'' などの灰色の薄い網掛けに設定します。**

     ![画像 103](Linked_image_Files/07-design-report-in-power-bi-desktop_image36c.png)

1. ページに **[テーブル]** ビジュアルを追加し、サイズを変更して、カード ビジュアルの下に配置し、ページ上の残りの領域を埋めます。

     ![画像 14](Linked_image_Files/08-design-report-in-power-bi-desktop-enhanced_image26.png)

     ![画像 105](Linked_image_Files/08-design-report-in-power-bi-desktop-enhanced_image27.png)

1. 視覚化に次のフィールドを追加します。

     - **Product \| Subcategory**
     - **Product \| Color**
     - **Sales \| Quantity**
     - **Sales \| Sales**
     - **Sales \| Profit Margin**

1. ビジュアルの書式オプションを構成し、**[値]** セクションと **[列見出し]** セクションで、**[文字のサイズ]** プロパティを **[20pt]** に設定します。

"ドリル スルー ページの設計はほぼ完了です。*次の演習では、条件付き書式を使用してページを拡張します。"*

## 条件付き書式を追加する

この演習では、条件付き書式を使用してドリル スルー ページを拡張します。 設計が完了すると、ページは次のようになります。

![色付きの値とアイコンが表示されている、更新されたページのイメージ。](Linked_image_Files/08-design-report-in-power-bi-desktop-enhanced_image28.png)

1. テーブル視覚化を選択します。 [視覚化] ペインで、 **[Profit Margin]** 値の上の下矢印を選択してから、 **[条件付き書式] \| [アイコン]** を選びます。

    ![画像 107](Linked_image_Files/08-design-report-in-power-bi-desktop-enhanced_image29.png)

1. **[アイコン - Profit Margin]** ウィンドウの **[アイコン レイアウト]** ドロップダウン リストで、**[データの右側]** を選択します。

    ![画像 108](Linked_image_Files/08-design-report-in-power-bi-desktop-enhanced_image30.png)

1. 中央のルールを削除するには、黄色の三角形の右側にある **[X]** を選択します。

    ![画像 109](Linked_image_Files/08-design-report-in-power-bi-desktop-enhanced_image31.png)

1. 次のように、最初のルール (赤色のひし形) を構成します。

    - 2 つ目のコントロールで値を削除します
    - 3 つ目のコントロールで **[番号]** を選択します
    - 5 つ目のコントロールに「**0**」と入力します
    - 6 つ目のコントロールで **[番号]** を選択します

1. 次のように、2 つ目のルール (緑色の円) を構成してから、 **[OK]** を選択します。

    > *ルールは次のように解釈できます。利益率の値が 0 未満の場合は赤いひし形を表示します。それ以外の場合は、値が 0 以上であれば、緑の円を表示します。*

    - 2 つ目のコントロールに「**0**」と入力します
    - 3 つ目のコントロールで **[番号]** を選択します
    - 5 つ目のコントロールで値を削除します
    - 6 つ目のコントロールで **[番号]** を選択します

    ![画像 110](Linked_image_Files/08-design-report-in-power-bi-desktop-enhanced_image32.png)

1. テーブル視覚化で、正しいアイコンが表示されていることを確認します。

    ![画像 112](Linked_image_Files/08-design-report-in-power-bi-desktop-enhanced_image34.png)

1. **[色]** フィールドの背景色の条件付き書式を構成します。

1. **[背景色 -- 色]** ウィンドウの **[書式設定スタイル]** ドロップダウン リストで、 **[フィールド値]** を選択します。

1. **[基準にするフィールド]** ドロップダウン リストで、 **[製品] \| [書式設定] \| [背景の書式]** を選んでから、 **[OK]** を選択します。

    ![画像 114](Linked_image_Files/08-design-report-in-power-bi-desktop-enhanced_image36.png)

1. 前の手順を繰り返し、**Product \| Formatting \| Font Color Format** フィールドを使用して、 **[Color]** フィールドのフォント色の条件付き書式を設定します

"背景とフォントの色を、「**Power BI Desktop でのデータの準備**」ラボで **ColorFormats.csv** ファイルから取得し、「**Power BI Desktop にデータを読み込む**」ラボで **Product** クエリに統合したことを思い出すかもしれません。"**

## ブックマークとボタンを追加する

この演習では、 **[マイ パフォーマンス]** ページをボタンを使用して拡張し、レポート ユーザーが表示する視覚化の種類を選択できるようにします。 設計が完了すると、ページは次のようになります。

![更新されたページ 3 のイメージ。2 つのボタンが表示され、ビジュアルが 2 つだけになっています。](Linked_image_Files/08-design-report-in-power-bi-desktop-enhanced_image38.png)

1. **[My Performance](マイ パフォーマンス)** ページに移動します。 **[表示]** リボン タブの **[ペインを表示する]** グループ内の **[ブックマーク]** を選択します。

    ![画像 118](Linked_image_Files/08-design-report-in-power-bi-desktop-enhanced_image39.png)

1. **[表示]** リボン タブの **[ペインを表示する]** グループ内の **[Selection](選択範囲)** を選択します。

1. **[選択]** ペインで、**[Sales and Target by Month](月別売上高と目標)** 項目の横にある視覚化を非表示にするには、目のアイコンを選択します。

    ![画像 120](Linked_image_Files/08-design-report-in-power-bi-desktop-enhanced_image41.png)

1. **[ブックマーク]** ペインで、**[追加]** を選択します。

    > *ブックマークの名前を変更するには、ブックマークをダブルクリックします。*

    ![画像 121](Linked_image_Files/08-design-report-in-power-bi-desktop-enhanced_image42.png)

1. 表示されているグラフが横棒グラフの場合は、ブックマークの名前を **[Bar Chart ON]** に変更します。それ以外の場合は、ブックマークの名前を **[Column Chart ON]** に変更します。

1. ブックマークを編集するには、 **[ブックマーク]** ペインでブックマークにカーソルを合わせて省略記号を選んでから **[データ]** を選択します。

    > " **[データ]** オプションを無効にすると、ブックマークで現在のフィルターの状態が使用されなくなります。*これが重要である理由は、そのようにしないと、現在 **[Year]** スライサーによって適用されているフィルターがブックマークによって永久にロックされるからです。"*

     ![画像 16](Linked_image_Files/08-design-report-in-power-bi-desktop-enhanced_image43.png)

1. ブックマークを更新するには、省略記号をもう一度選んでから **[更新]** を選択します。

    > *次の手順では、2 つ目のブックマークを作成および構成して、2 つ目の視覚化を表示します。*

1. **[選択項目]** ペインで、2 つの **[Sales and Target by Month](月別売上高と目標)** 項目の表示を切り替えます。

    > *つまり、表示されている視覚化を非表示にし、非表示の視覚化を表示します。*

     ![画像 122](Linked_image_Files/08-design-report-in-power-bi-desktop-enhanced_image45.png)

1. 2 つ目のブックマークを作成し、適切な名前を付けます (**[Column Chart ON]** または **[Bar Chart ON]**)。

     ![画像 123](Linked_image_Files/08-design-report-in-power-bi-desktop-enhanced_image46.png)

1. 2 つ目のブックマークを構成してフィルターを無視し (**[データ]** オプションをオフ)、ブックマークを更新します。

1. **[選択項目]** ウィンドウで両方のビジュアルを表示するには、非表示のビジュアルを表示するだけです。

1. 両方の視覚化のサイズと位置を変更して、マルチカード視覚化の下のページ全体に表示し、互いに完全に重なり合うようにします。

    ''隠れている視覚化を選ぶ場合は、 **[選択]** ペインで選びます。''**

    ![画像 124](Linked_image_Files/08-design-report-in-power-bi-desktop-enhanced_image47.png)

1. **[ブックマーク]** ペインで各ブックマークを選択します。1 つの視覚化のみが表示されることに注目してください。

*デザインの次の段階は、ページに 2 つのボタンを追加することです。これで、レポート ユーザーはブックマークを選択できるようになります。*

1. **[挿入]** リボンの **[要素]** グループ内の **[ボタン]** を選択し、**[空白]** を選択します。

     ![画像 125](Linked_image_Files/08-design-report-in-power-bi-desktop-enhanced_image48.png)

1. **Year** スライサーの真下にボタンを配置します。

1. ボタンを選択し、 **[ボタンの書式設定]** ペインで、 **[ボタン]** を選び、 **[スタイル]** セクションを展開し、 **[テキスト]** プロパティを **[オン]** にします。

     ![画像 126](Linked_image_Files/08-design-report-in-power-bi-desktop-enhanced_image49b.png)

1. **[テキスト]** セクションを展開し、 **[テキスト]** ボックスに「**Bar Chart**」と入力します。

1. **[塗りつぶし]** セクションを展開してから、補完的な色を使用して塗りつぶしの色を設定します。

1. **[ボタン]** を選択し、 **[アクション]** プロパティを **[オン]** にします。

    ![画像 127](Linked_image_Files/08-design-report-in-power-bi-desktop-enhanced_image50.png)

1. **[アクション]** セクションを展開し、**[種類]** ドロップダウン リストを **[ブックマーク]** に設定します。

1. **[ブックマーク]** ドロップダウン リストで、**[Bar Chart ON](横棒グラフ オン)** を選択します。

    ![画像 128](Linked_image_Files/08-design-report-in-power-bi-desktop-enhanced_image51.png)

1. コピーと貼り付けを使用してボタンのコピーを作成し、次のように新しいボタンを構成します。

    *ヒント:コピーと貼り付けのショートカット コマンドは、**Ctrl+C** キーに続いて **Ctrl+V** キーです。"*

    - **[ボタン テキスト]** プロパティを **[縦棒グラフ]** に設定します
    - **[アクション]** セクションで、**[ブックマーク]** ドロップダウン リストを **[Column Chart ON](横棒グラフ オン)** に設定します

*これで、Sales Analysis レポートのデザインが完成しました。*

## レポートを発行して調べる

この演習では、レポートを Power BI サービスに発行し、発行したレポートの動作を調べます。

> **注**: タスクを直接実行するオンライン Power BI サービスにアクセスできない場合でも、演習の残りの部分を確認できます。

1. **[概要]** ページを選択します。

1. **[年]** スライサーで、**[FY2020]** を選択します。

1. **[地域]** スライサーで、**[すべて選択]** を選択します。

1. Power BI Desktop ファイルを保存します。

1. **[ホーム]** リボン タブで、**[共有]** グループの **[発行]** を選択します。

    > ''まだ Power BI Desktop にサインインしていない場合は、サインインして発行する必要があります。''**

     ![画像 21](Linked_image_Files/08-design-report-in-power-bi-desktop-enhanced_image52.png)

1. **[Power BI に発行]** ウィンドウで、**[マイ ワークスペース]** が選択されていることを確認します。

1. レポートを発行するには、 **[選択]** を選びます。
    1. セマンティックの置換を求めるメッセージが表示されたら、**[置き換える]** を選択します。
    1. 発行が成功したら、**[了解]** を選択します。

1. Power BI Desktop を閉じます。

1. Microsoft Edge ブラウザー ウィンドウで、Power BI サービス > **[マイ ワークスペース]** の順に移動してから、 **[Sales Analysis]** レポートを選択します。

1. ドリルスルー機能をテストするには、 **[概要]** ページ > **[カテゴリ別数量]** 視覚化の順に移動します。 その後、 **[Clothing]** バーを右クリックし、 **[ドリルスルー] \| [製品の詳細]** を選択します。

     ![画像 130](Linked_image_Files/08-design-report-in-power-bi-desktop-enhanced_image55.png)

1. **[製品の詳細]** ページが **[Clothing](衣類)** 用であることに注目してください。

1. ソース ページに戻るには、ページの左上隅の矢印ボタンを選択します。

1. **My Performance** ページを選択します。

     > *各ボタンを選択すると、別の視覚化が表示されることに注目してください。*

## ラボが完了しました
