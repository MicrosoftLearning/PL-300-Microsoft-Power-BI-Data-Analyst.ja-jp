---
lab:
  title: Power BI Desktop で DAX 計算を作成する
  module: Create Model Calculations using DAX in Power BI
---


# Power BI Desktop で DAX 計算を作成する

## **ラボのストーリー**

このラボでは、Data Analysis Expressions (DAX) を使用して、計算テーブル、計算列、およびシンプルなメジャーを作成します。

このラボでは、次の作業を行う方法について説明します。

- 計算テーブルを作成する
- 計算列を作成する
- メジャーを作成する

**この配信には約 45 分かかります。**

## 作業の開始

この演習を完了するには、まず Web ブラウザーを開き、次の URL を入力して zip フォルダーをダウンロードします。

`https://github.com/MicrosoftLearning/PL-300-Microsoft-Power-BI-Data-Analyst/raw/Main/Allfiles/Labs/04-create-dax-calculations-in-power-bi-desktop\04-intro-dax.zip`

フォルダーを **C:\Users\Student\Downloads\04-intro-dax** フォルダーに展開します。

**04-Starter-Sales Analysis.pbix** ファイルを開きます。

> ***注**: **[キャンセル]** を選択すると、サインインを閉じることができます。 他のすべての情報ウィンドウを閉じます。 変更の適用を求めるメッセージが表示されたら、**[後で適用]** を選択します。

## Salesperson 計算テーブルを作成する

このタスクでは、**Salesperson** 計算テーブル (**Sales** との直接的なリレーションシップ) を作成します。

計算テーブルを作成するには、最初にテーブル名を入力し、続けて等号 (=) と、テーブルが返される DAX 式を入力します。 データ モデル内に既に存在しているテーブル名は使用できません。

数式バーでは、有効な DAX 式の入力がサポートされています。 オートコンプリート、Intellisense、色分けなどの機能が用意されているため、すばやく正確に数式を入力できます。

1. Power BI Desktop のレポート ビューで、**[モデリング]** リボンの **[計算]** グループの中から、**[新しいテーブル]** を選択します。

     ![画像 1](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image9.png)

2. 数式バー (計算の作成または編集時に、リボンのすぐ下に表示されます) に、「**Salesperson =**」と入力して **Shift + Enter** キーを押し、「**'Salesperson (Performance)'**」と入力して **Enter** キーを押します。

    > **注**: *便宜上、このラボのすべての DAX 定義は **04-intro-dax\Snippets.txt** にあるスニペット ファイルからコピーできます。*

     ![画像 4](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image10.png)

    > "このテーブル定義では、**Salesperson (Performance)** テーブルのコピーが作成されます。コピーされるのはデータのみで、表示や書式設定などのモデル プロパティはコピーされません。"**

1. **[データ]** ペインで、テーブル アイコンに追加の電卓アイコンも含まれている (計算テーブルを示す) ことに注目してください。

    ![画像 10](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image11.png)

    > ***注**: 計算テーブルは、テーブルを返す DAX 式を使用して定義します。 計算テーブルでは、値が具体化されて格納されるため、データ モデルのサイズが大きくなることを理解しておくことが重要です。 新しい (将来の) 日付値がテーブルに読み込まれるこのデータ モデルの場合のように、数式の依存関係が更新されるたびに再計算されます。*
    >
    > "Power Query に由来するテーブルとは異なり、計算テーブルを使用して外部データ ソースからデータを読み込むことはできません。*既にデータ モデルに読み込まれている内容に基づいてのみ変換できます。"*

1. [モデル] ビューに切り替え、**Salesperson** テーブルが使用可能であることに注目してください (テーブルを見つけるにはビューをリセットする必要がある場合があります)。

1. **Salesperson \| EmployeeKey** 列から **Sales \| EmployeeKey** 列へのリレーションシップを作成します。

1. **Salesperson (Performance)** テーブルと **Sales** テーブルの間の非アクティブなリレーションシップを右クリックし、**[削除]** を選択します。 削除するかどうかを確認するメッセージが表示されたら、 **[はい]** を選択します。

1. **Salesperson** テーブルで、次の列を複数選択し、非表示にします (**Is Hidden**プロパティを **[はい]** に設定します)。

    - EmployeeID
    - EmployeeKey
    - UPN

1. モデル ダイアグラムで、**Salesperson** テーブルを選択します。

1. **[プロパティ]** ペインの **[説明]** ボックスに、次のように入力します。**売上に関連する営業担当者**
    
    > "ユーザーがカーソルをテーブルまたはフィールドの上に置くと、説明が **[データ]** ペインにヒントとして表示されることを思い出すかもしれません。"**

1. **Salesperson (Performance)** テーブルに対しては、次の説明を設定します。**地域に関連する営業担当者**

"これで、販売員を分析するときに、データ モデルによって 2 つの代替手段が提供されるようになりました。***Salesperson** テーブルを使用すると、販売員による売上を分析できます。一方、**Salesperson (Performance)** テーブルでは、販売員に割り当てられた販売地域での売上を分析できます。"*

## Date テーブルを作成する

このタスクでは、**Date** テーブルを作成します。

1. データ ビューに切り替えます。 **[ホーム]** リボン タブの **[計算]** グループの中から、**[新しいテーブル]** を選択します。

    ![画像 5](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image15.png)

1. 数式バーに次の DAX を入力します。

    ```DAX
    Date =  
    CALENDARAUTO(6)
    ```

    ![画像 6](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image16.png)

    > "CALENDARAUTO() 関数では、日付値で構成される単一列のテーブルが返されます。 *"自動的な" 動作により、すべてのデータ モデルの日付列がスキャンされ、データ モデルに格納されている最も古い日付値と最も新しい日付値が決定されます。次に、この範囲内の各日付に対して 1 つの行が作成されます。範囲をいずれかの方向に拡張して、すべての年のデータが格納されるようにします。"*
    >
    > "この関数は、1 年の最後の月数である 1 つの省略可能な引数を受け取ることができます。*省略した場合、その値は 12 になります。12 月が年度の最終月であるという意味です。この場合は "6" が入力されています。6 月が年度の最終月であるという意味です。"*

1. 米国の地域設定 (mm/dd/yyyy) を使用して書式設定されている日付値の列に注意してください。

    ![画像 7](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image17.png)

1. 左下隅のステータス バーに、テーブルの統計情報が表示されているのがわかります。1826 行のデータが生成されていることを確認します。これは 5 年間全体のデータを表します。

    ![画像 9](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image18.png)

## 計算列を作成する

このタスクでは、列をさらに追加して、さまざまな期間によるフィルター処理とグループ化を可能にします。 また、計算列を作成して、他の列の並べ替え順序の制御も行います。

> **注**: *便宜上、このラボのすべての DAX 定義は **Snippets.txt** ファイルからコピーできます。*

1. **[テーブル ツール]** コンテキスト リボンの **[計算]** グループ内から、**[新しい列]** を選択します。

    > "計算列を作成するには、最初に列名を入力し、続けて等号 (=) と、単一値の結果が返される DAX 式を入力します。テーブル内に既に存在している列名は使用できません。"**

    ![画像 11](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image19.png)

1. 数式バーに次のように入力 (またはスニペット ファイルからコピー) して、**Enter** キーを押します。
    > "この数式では日付の年の値が使用されますが、月が 6 月よりも後の場合は、年の値に 1 が加算されます。*このようにして、Adventure Works 社の会計年度が計算されます。"*

   ```DAX
   Year =
   "FY" & YEAR('Date'[Date]) + IF(MONTH('Date'[Date]) > 6, 1)
   ```



1. スニペットのファイル定義を使用して、**Date** テーブルに対して次の 2 つの計算列を作成します。

    - Quarter
    - Month

1. 新しい列が追加されたことを確認します。

    ![画像 14](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image21.png)

1. 計算を確認するために、レポート ビューに切り替えます。

1. 新しいレポート ページを作成するには、[ページ 1] の横にあるプラス アイコンを選択します。

    ![画像 15](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image22.png)

1. 新しいレポート ページに行列の視覚エフェクトを追加するには、**[視覚化]** ペインで、行列の視覚エフェクトの種類を選択します。

    > *ヒント:各アイコンの上にカーソルを置くと、視覚エフェクトの種類について説明するヒントが表示されます。"*

    ![画像 51](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image23.png)

1. **[データ]** ペインの **Date** テーブル内から **Year** フィールドを **Rows** ウェル/領域にドラッグします。

    ![画像 17](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image24.png)

1. **[月]** フィールドを **[年]** フィールドのすぐ下にある **[行]** ウェル/領域にドラッグします。

1. マトリックス ビジュアルの右上 (またはビジュアルの場所によっては下部) にある、分岐した二重矢印アイコンを選択します (すべての年を 1 レベル下に展開します)。

    ![画像 19](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image26.png)

1. 年が月に展開され、月が時系列順ではなくアルファベット順に並べ替えられていることがわかります。

    ![画像 20](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image27.png)

    > *既定では、テキスト値はアルファベット順に、数値は昇順に、日付は最も古いものから最も新しいものの順に並べ替えられます。*

1. **"Month"** フィールドの並べ替え順序をカスタマイズするために、テーブル ビューに切り替えます。

1. **Date** テーブルに **MonthKey** 列を追加します。

    ```DAX
    MonthKey =
    (YEAR('Date'[Date]) * 100) + MONTH('Date'[Date])
    ```

    > *この数式により、年と月の各組み合わせに対する数値が計算されます。*

1. テーブル ビューで、新しい列に数値が含まれていることを確認します (たとえば、2017 年 7 月に対して 201707、など)。

    ![画像 21](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image28.png)

1. もう一度レポート ビューに切り替えます。 **[データ]** ペインで、**[月]** を選択します。

1. **[列ツール]** コンテキスト リボンで、**[並べ替え]** グループ内から **[列で並べ替え]** を選択して、**[MonthKey]** を選択します。

    ![画像 22](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image29.png)

1. 行列の視覚エフェクト内で、月が時系列順に並べ替えられるようになったことがわかります。

    ![画像 23](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image30.png)

## Date テーブルを完成させる

このタスクでは、1 つの列を非表示にし、階層を作成することで、**Date** テーブルのデザインを完成させます。 その後、**Sales** テーブルと **Targets** テーブルに対するリレーションシップを作成します。

1. モデル ビューに切り替えます。 **Date** テーブルで、**MonthKey** 列を非表示にします (**Is Hidden**を **[はい]** に設定します)。

1. 右側の **[データ]** ペインで **Date** テーブルを選択し、**Year** 列で右クリックし、 **[階層の作成]** を選択します。

1. 新しく作成した階層を右クリックして **[名前を変更]** をクリックし、**Fiscal** という名前に変更します。

1. 次の 2 つの残りのフィールドを Fiscal 階層に追加します。これを行うには、 **[データ]** ペインでこれらを選択してから右クリックし、 **[階層の追加]**  -> **Fiscal** の順に選択します。

    - Quarter
    - Month

    ![画像 24](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image31.png)

1. 次の 2 つのモデル リレーションシップを作成します。

    - **Date \| Date** から **Sales \| OrderDate** へ
    - **Date \| Date** から **Targets \| TargetMonth** へ


    > "このラボでは、フィールドを参照するために簡略表記を使用します。*次のようになります。**Sales \| Unit Price**。この例では、**Sales** はテーブル名、**Unit Price** はフィールド名です。"*

1. 次の 2 つの列を非表示にします。

    - Sales \| OrderDate
    - Targets \| TargetMonth

## Date テーブルをマークする

このタスクでは、**Date** テーブルを日付テーブルとしてマークします。

1. レポート ビューに切り替えます。 **[データ]** ペインで、**Date** テーブル (**Date** フィールドではありません) を選択します。

1. **[テーブル ツール]** コンテキスト リボンの **[カレンダー]** グループ内から、**[日付テーブルとしてマーク]** を選択します。

1. **[日付テーブルとしてマーク]** ウィンドウで、**[日付テーブルとしてマーク]** プロパティを **[Yes]** にスライドし、**[日付列を選択]** ドロップダウン リストで **[Date]** を選択します。 **[保存]** を選択します。

    ![日付テーブルとしてマーク](Linked_image_Files/04-create-dax-calculations-in-power-bi-desktop_date-table.png)

1. Power BI Desktop ファイルを保存します。

> *Power BI Desktop では、このテーブルで日付 (時刻) が定義されていることを把握できるようになりました。データ ソースに日付テーブルがない場合は、日付テーブルに対してこの設計方法が適しています。データ ウェアハウスをお持ちの場合は、データ モデルで日付ロジックを "再定義" するのではなく、日付ディメンション テーブルから日付データをロードするのが適切です。*

## 単純なメジャーを作成する

このタスクでは、シンプルなメジャーを作成します。 単純なメジャーは、単一の列の値を集計するか、テーブルの行をカウントします。

1. レポート ビューの**ページ 2** の **[データ]** ペインで、**Sales \| Unit Price** フィールドを行列の視覚エフェクトにドラッグします。

    ![画像 27](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image35.png)

1. (**[視覚化]** ウィンドウの下にある) ビジュアル フィールド ウィンドウの **[値]** フィールドのウェル/領域に、**[Unit Price]** が**単価の平均値**として一覧表示されていることに注目してください。 **[Unit Price]** の下向き矢印を選択して、使用可能なメニュー オプションを確認します。

    ![画像 30](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image37.png)

    > "表示可能な数値列を使用すると、レポートの作成者は、レポートの設計時に列の値をどのように集計するか (またはしないか) を決定できます。これにより、不適切な報告が発生する可能性があります。ただし、一部のデータ モデル作成者は、物事を偶然に任せたくないので、これらの列を非表示にし、メジャーで定義された集計ロジックを公開することを選択します。これは、このラボで採用するアプローチです。"**

1. メジャーを作成するには、 **[データ]** ペインで **Sales** テーブルを右クリックして、 **[新しいメジャー]** を選択します。

1. 数式バーに、次のメジャーの定義を追加します。

    ```DAX
    Avg Price =  
    AVERAGE(Sales[Unit Price])
    ```

1. マトリックス ビジュアルに **Avg Price** メジャーを追加して、**Unit Price** 列と同じ結果が生成される (ただし、書式設定は異なる) ことに注目してください。

1. **[値]** ウエルで、 **[Avg Price]** フィールドのコンテキスト メニューを開き、集計手法を変更できないことに注目してください。

    ![画像 32](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image39.png)

    > "メジャーの集計動作を変更することはできません。"**

1. スニペットのファイル定義を使用して、**Sales** テーブルに対して次の 5 つのメジャーを作成します。

    - Median Price
    - Min Price
    - Max Price
    - Orders
    - Order Lines

    > "**Orders** メジャーで使用される DISTINCTCOUNT() 関数では、各注文が 1 回だけカウントされます (重複は無視されます)。***Order Lines** メジャーで使用される COUNTROWS() 関数は、テーブルに対して動作します。"*
    >
    > "この場合、注文数は、**SalesOrderNumber** 列の一意の値をカウントすることによって計算されますが、注文の行の数は、単純にテーブルの行の数になります (各行が 1 つの注文の 1 行になります)。"**

1. モデル ビューに切り替えて、価格の 4 つのメジャーを複数選択します。**Avg Price**、**Max Price**、**Median Price**、および **Min Price** です。

11. 複数選択したメジャーに対して、次の要件を構成します。

    - 書式を小数点以下 2 桁に設定する

    - **Pricing** という名前の表示フォルダーに割り当てる

    ![画像 33](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image40.png)

12. **Unit Price** 列を非表示にします。

    > "これで、レポート作成者が **Unit Price** 列を使用できなくなりました。*モデルに追加した価格メジャーを使用する必要があります。この設計方法では、レポート作成者が不適切に (たとえば、価格を合計して) 価格を集計することができなくなります。"*

13. **[Order Lines]** メジャーと **[Orders]** メジャーを複数選択して、次の要件を設定します。

    - 桁区切り記号を使用するように書式を設定する

    - **Counts** という名前の表示フォルダーに割り当てる

    ![画像 36](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image41.png)

14. レポート ビューにあるマトリックス ビジュアルの **[値]** ウエル/領域で、 **[Unit Price]** フィールドの **[X]** を選択して削除します。

15. ページの幅と高さに合わせて、行列の視覚エフェクトのサイズを大きくします。

16. マトリックス ビジュアルに次の 5 つのメジャーを追加します。

    - Median Price
    - Min Price
    - Max Price
    - Orders
    - Order Lines

17. 結果が適切に表示され、正しく書式設定されていることを確認します。

    ![画像 39](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image43.png)

## 追加のメジャーを作成する

このタスクでは、より複雑な数式を使用するメジャーをさらに作成します。

1. [レポート] ビューで **[ページ 1]** を選択し、テーブル ビジュアルを確認し、 **[Target]** 列の合計に注目してください。

    ![画像 41](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image45.png)

1. テーブル ビジュアルを選択し、**[視覚化]** ウィンドウで **[Target]** フィールドを削除します。

1. **Targets \| Target** 列の名前を、**Targets \| TargetAmount** に変更します。

    > "*ヒント: レポート ビューで列の名前を変更するには、いくつかの方法があります。 **[データ]** ペインで、列を右クリックしてから **[名前の変更]** を選択するか、列をダブルクリックするか、**F2** キーを押します。* "

1. **Targets** テーブルに対して、次のメジャーを作成します。

    ```DAX
    Target =
    IF(
    HASONEVALUE('Salesperson (Performance)'[Salesperson]),
    SUM(Targets[TargetAmount])
    )
    ```

    > *HASONEVALUE() 関数によって、**Salesperson** 列内の単一の値がフィルター処理されているかどうかがテストされます。true の場合は、式によって (その販売員のみの) 目標金額の合計が返されます。false の場合は、空白が返されます。*

1. **Target** メジャーを、小数点以下 0 桁に書式設定します。

    > *ヒント: **[メジャー ツール]** コンテキスト リボンを使用できます。*

1. **TargetAmount** 列を非表示にします。

    > "*ヒント: **[データ]** ペインで列を右クリックして **[非表示]** を選択することができます。* "

1. テーブルの視覚エフェクトに **Target** メジャーを追加します。

1. **Target** 列の合計が空白になっていることがわかります。

    ![画像 43](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image47.png)

1. スニペットのファイル定義を使用して、**Targets** テーブルに対して次の 2 つのメジャーを作成します。

    - Variance
    - Variance Margin

1. **Variance** メジャーを、小数点以下 0 桁に書式設定します。

1. **Variance Margin** メジャーを、小数点以下 2 桁のパーセンテージとして書式設定します。

1. テーブルの視覚エフェクトに、**Variance** メジャーと **Variance Margin** メジャーを追加します。

1. すべての列と行が表示されるように、テーブル ビジュアルのサイズを変更します。

    ![画像 44](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image48.png)

    > ''すべての営業担当者が目標を達成していないように見えますが、テーブル ビジュアルはまだ特定の期間でフィルタリングされていないことに注意してください。「**Power BI Desktop でレポートをデザインする**」ラボでは、ユーザーが選択した期間でフィルター処理を行う販売実績レポートを生成します。''**

1. **[データ]** ペインの右上隅で、ペインを折りたたんでから展開します。

    > ''ペインを折りたたんで再び開くと、内容がリセットされます。''**

1. 一覧の先頭に **[Targets]** テーブルが表示されるようになったことがわかります。

    ![画像 46](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image50.png)

    *表示されるメジャーのみを含むテーブルは、自動的に一覧の先頭に表示されます。*

## ラボが完了しました
