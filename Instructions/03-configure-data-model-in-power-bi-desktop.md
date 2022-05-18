---
lab:
  title: Power BI Desktop でデータをモデル化する (パート 1)
  module: Module 4 - Design a Data Model in Power BI
ms.openlocfilehash: cbec1e2dc3bb7738b2e78de88e30b1d56cb79b60
ms.sourcegitcommit: 3520e7d016e94549d408464207c1b91cd47867c2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2022
ms.locfileid: "139273652"
---
# <a name="model-data-in-power-bi-desktop-part-1"></a>**Power BI Desktop でデータをモデル化する (パート 1)**

**このラボの推定所要時間: 45 分**

このラボでは、データ モデルの開発を開始します。 テーブル間のリレーションシップを作成してから、データ モデルのわかりやすさと使いやすさを向上させるために、テーブルと列のプロパティを構成します。 また、階層を作成し、クイック メジャーを作成します。

このラボでは、次の作業を行う方法について説明します。

- モデル リレーションシップを作成する

- テーブルと列のプロパティを構成する

- 階層を作成する


### <a name="lab-story"></a>**ラボのストーリー**

このラボは、データの準備に始まり、レポートおよびダッシュボードとして発行するまでの完全なストーリーとして設計されたラボ シリーズの 1 つです。 ラボは任意の順序で完了できます。 しかしながら、複数のラボに取り組む場合は、最初の 10 のラボについては、次の順序で行うことをお勧めします。

1. Power BI Desktop でのデータの準備

2. Power BI Desktop にデータを読み込む

3. **Power BI Desktop でデータをモデル化する**

5. Power BI Desktop での DAX 計算の作成、パート 1

6. Power BI Desktop で DAX 計算を作成する (パート 2)

7. Power BI Desktop でレポートを設計する (パート 1)

8. Power BI Desktop でレポートを設計する (パート 2)

9. Power BI ダッシュボードを作成する

10. Power BI Desktop でデータ分析を実行する

11. 行レベルのセキュリティを実行する

## <a name="exercise-1-create-model-relationships"></a>**演習 1: モデル リレーションシップを作成する**

この演習では、モデル リレーションシップを作成します。

### <a name="task-1-get-started"></a>**タスク 1: 開始する**

このタスクではこのラボ用の環境を設定します。

*重要:前のラボから継続している (および、そのラボを正常に完了した) 場合は、このタスクを完了させず、次のタスクから続行してください。*

1. Power BI Desktop を開くには、タスク バーにある Microsoft Power BI Desktop のショートカットをクリックします。

    ![画像 12](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image1.png)

1. 「はじめに」ウィンドウを閉じるには、ウィンドウの左上にある「**X**」をクリックします。

    ![画像 11](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image2.png)

1. スターター Power BI Desktop ファイルを開くには、「**ファイル**」リボン タブをクリックして、バックステージ ビューを開きます。

1. **[レポートを開く]** を選択します。

    ![画像 10](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image3.png)

1. 「**レポートを参照**」をクリックします。

    ![画像 8](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image4.png)

1. **[開く]** ウィンドウで、**D:\PL300\Labs\03-configure-data-model-in-power-bi-desktop\Starter** フォルダーに移動します。

1. **Sales Analysis** ファイルを選択します。

1. **[開く]** をクリックします。

    ![画像 7](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image5.png)

1. 情報ウィンドウが開いている場合はすべて閉じます。

1. ファイルのコピーを作成するには、「**ファイル**」リボン タブをクリックして、バックステージ ビューを開きます。

1. **[名前を付けて保存]** を選択します。

    ![画像 5](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image6.png)

1. 変更を適用するかどうかを確認するメッセージが表示されたら、「**適用**」をクリックします。

    ![画像 15](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image7.png)

1. **[名前を付けて保存]** ウィンドウで、**D:\PL300\MySolution** フォルダーに移動します。

1. **[保存]** をクリックします。

    ![図 3](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image8.png)

### <a name="task-2-create-model-relationships"></a>**タスク 2: モデル リレーションシップを作成する**

このタスクでは、モデルのリレーションシップを作成します。

1. Power BI Desktop で、左側の **[モデル ビュー]** アイコンをクリックします。

    ![画像 1](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image9.png)

2. 7 つのテーブルがすべて表示されていない場合は、水平方向に右へスクロールし、テーブルをドラッグして、すべてを同時に表示できるように、より近づけて配置します。

    *ヒント:ウィンドウの最下部にあるズーム コントロールも使用できます。"*

    "モデル ビューでは、各テーブルとリレーションシップ (テーブル間のコネクタ) を表示できます。*この時点では、リレーションシップはありません。「**Power BI Desktop でのデータの準備**」のラボで、データ読み込みリレーションシップのオプションを無効にしたためです。"*

3. レポート ビューに戻るには、左側の **[レポート ビュー]** アイコンをクリックします。

    ![画像 327](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image10.png)

4. すべてのテーブル フィールドを表示するには、**[フィールド]** ペインで何も表示されていない領域を右クリックし、**[すべて展開]** を選択します。

    ![画像 328](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image11.png)

5. テーブル ビジュアルを作成するには、**[フィールド]** ペインの **Product** テーブルにある、**Category** フィールドをオンにします。

    ![画像 329](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image12.png)

    "このラボでは、フィールドを参照するために簡略表記を使用します。*次のようになります。**Product \| Category**。この例では、**Product** はテーブル名、**Category** はフィールド名です。"*

6. テーブルに列を追加するには、 **[フィールド]** ウィンドウで、**Sales \| Sales** フィールドを選択します。

7. テーブル ビジュアルに 4 つの製品カテゴリが一覧表示され、それぞれの Sales 値が同じで、Total も同じであることに注意してください。

    ![画像 330](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image13.png)

    *問題は、このテーブルが異なる複数のテーブルのフィールドに基づいていることです。各製品カテゴリには、そのカテゴリの売上が表示されることが想定されています。ただし、これらのテーブル間にはモデルのリレーションシップがないため、**Sales** テーブルはフィルタリングされません。そこで、リレーションシップを追加してテーブル間のフィルターを反映します。"*

8. **[モデリング]** リボン タブの **[リレーションシップ]** グループの中から、**[リレーションシップの管理]** をクリックします。

    ![画像 331](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image14.png)

9. **[リレーションシップの管理]** ウィンドウで、リレーションシップがまだ定義されていないことを確認します。

10. リレーションシップを作成するには、**[新規]** をクリックします。

    ![画像 332](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image15.png)

11. **[リレーションシップの作成]** ウィンドウの最初のドロップダウン リストで、**Product** テーブルを選択します。

    ![画像 333](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image16.png)

12. 2 番目のドロップダウンリスト (**Product** テーブル グリッドの下) で、**Sales** テーブルを選択します。

    ![画像 334](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image17.png)

13. 各テーブルの **ProductKey** 列が自動的に選択されていることに注意してください。

    *これらの列は同じ名前とデータ型を共有しているため、選択されました。*

14. **[カーディナリティ]** のドロップダウン リストで、**[一対多(1:*)]** が選択されていることを確認します。

    "このカーディナリティは、**Product** テーブルの **ProductKey** 列に一意の値が含まれていることが Power BI によって認識されているため、自動的に検出されました。*一対多リレーションシップは最も一般的なカーディナリティで、このラボで作成するすべてのリレーションシップがこの種類になります。多対多のカーディナリティについては、「**Power BI Desktop でデータをモデル化する (パート 2)** 」のラボで扱います。"*

15. **[クロス フィルターの方向]** のドロップダウンリストで、**[単一]** が選択されていることを確認します。

    "単一というフィルターの方向は、フィルターが "一の側" から "多の側" に反映されることを意味します。*この場合、**Product** テーブルに適用されたフィルターは **Sales** テーブルに伝達しますが、逆方向には伝達しません。双方向のリレーションシップについては、「**Power BI Desktop でデータをモデル化する (パート 2)** 」のラボで扱います。"*

16. 「**このリレーションシップをアクティブにする**」がオンになっていることを確認します。

    "アクティブなリレーションシップは、フィルターを伝達します。*リレーションシップを非アクティブとしてマークして、フィルターが伝達しないようにすることができます。テーブル間に複数のリレーションシップ パスがある場合、非アクティブなリレーションシップが存在する可能性があります。この場合、モデル計算は特別な関数を使用してアクティブ化できます。非アクティブなリレーションシップについては、「**Power BI Desktop でデータをモデル化する (パート 2)** 」のラボで扱います。"*

17. **[OK]** をクリックします。

    ![画像 335](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image18.png)

18. **[リレーションシップの管理]** ウィンドウで、新しいリレーションシップが表示されていることを確認し、**[閉じる]** をクリックします。

    ![画像 336](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image19.png)

19. レポートでは、テーブル ビジュアルが更新され、製品カテゴリごとに異なる値が表示されていることを確認します。

    ![画像 337](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image20.png)

    ***Product** テーブルに適用されたフィルターが、**Sales** テーブルに反映されるようになりました。*

20. モデル ビューに切り替えて、2 つのテーブルの間にコネクタがあることを確認します(テーブルが互いに隣接しているかどうかは問題になりません)。

    ![画像 338](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image21.png)

21. この図では、**1** および*****インジケーターで表されるカーディナリティーを解釈できることに注意してください。

    "フィルターの方向は、矢印の向きによって表されます。*実線はアクティブなリレーションシップを表し、破線は非アクティブなリレーションシップを表します。"*

22. リレーションシップにカーソルを合わせると、関連する列が強調表示されます。

    "もっと簡単にリレーションシップを作成する方法があります。*モデル ダイアグラムで、列をドラッグ アンド ドロップして新しいリレーションシップを作成できます。* "

23. 別の方法を使用して新しいリレーションシップを作成するには、**Reseller** テーブルから、**ResellerKey** 列を **Sales** テーブルの **ResellerKey** 列にドラッグします。

    ![画像 339](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image22.png)

    *ヒント:列をドラッグしたくない場合があります。このような状況が発生した場合は、別の列を選択し、もう一度ドラッグする列を選択して、もう一度やり直してください。図に新しいリレーションシップが追加されていることを確認します。"*

24. 新しい方法を使用して、次の 2 つのモデル リレーションシップを作成します。

    - **Region \| SalesTerritoryKey** から **Sales \| SalesTerritoryKey**

    - **Salesperson \| EmployeeKey** から **Sales \| EmployeeKey**

    "このラボでは、テーブル **SalespersonRegion** と **Targets** は接続しないままにします。*営業担当者と地域の間には多対多のリレーションシップがあり、「**Power BI Desktop でのデータのモデル化 (パート 2)** 」のラボでは、この高度なシナリオを使用して作業します。"*

25. 図では、**Sales** テーブルが図の中央に配置され、関連するテーブルがその周りに配置されるようにテーブルを配置します。 切断されたテーブルを横に配置します。

    ![画像 340](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image23.png)

26. Power BI Desktop ファイルを保存します。

## <a name="exercise-2-configure-tables"></a>**演習 2:テーブルを構成する**

この演習では、階層を作成し、列の非表示、書式設定、分類を行うことによって、各テーブルを構成します。

### <a name="task-1-configure-the-product-table"></a>**タスク 1: Product テーブルを構成する**

このタスクでは、**Product** テーブルを構成します。

1. モデル ビューの「**フィールド**」ウィンドウで、必要に応じて **Product** テーブルを展開してすべてのフィールドを表示します。

2. 階層を作成するには、**[フィールド]** ペインで **Category** 列を右クリックし、次に **[階層の作成]** を選択します。

    ![画像 341](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image24.png)

3. **[プロパティ]** ペイン (**[フィールド]** ペインの左側) で、**[名前]** ボックスのテキストを **Products** に置き換えます。

    ![画像 344](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image25.png)

4. 階層に 2 つ目のレベルを追加するには、「**プロパティ**」ウィンドウの「**階層**」ドロップダウン リストで「**サブカテゴリ**」を選択します (ウィンドウ内で下にスクロールする必要がある場合があります)。

5. 階層に 3 番目のレベルを追加するには、**[階層]** のドロップダウン リストで **[Product]** を選択します。

6. 階層の設計を完了するには、**[レベルの変更を適用します]** をクリックします。

    ![画像 343](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image26.png)

    *ヒント: **[レベル変更の適用]** をクリックすることを忘れないでください。この手順を見落とすことはよくある間違いです。"*

7. **[フィールド]** ペインで、**Products** 階層に注目します。

    ![画像 347](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image27.png)

8. 階層レベルを表示するには、**Products** 階層を展開します。

    ![画像 346](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image28.png)

9. 列を表示フォルダーに整理するには、**[フィールド]** ペインで、最初に **Background Color Format** 列を選択します。

10. **Ctrl** キーを押しながら、**[Font Color Format]** 列を選択します。

11. **[プロパティ]** ペインの **[フォルダーの表示]** ボックスに「**Formatting**」と入力します。

    ![画像 348](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image29.png)

12. **[フィールド]** ペインで、2 つの列がフォルダー内に表示されるようになったことを確認します。

    ![画像 349](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image30.png)

    *表示フォルダーは、特に多数のフィールドで構成されるテーブルを整理するのに最適な方法です。*

### <a name="task-2-configure-the-region-table"></a>**タスク 2: Region テーブルを構成する**

このタスクでは、**Region** テーブルを構成します。

1. **Region** テーブルで、次の 3 つのレベルを持つ **Regions** という名前の階層を作成します。

    - Group

    - Country

    - リージョン

    ![画像 350](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image31.png)

2. **Country** 列 (**Country** 階層レベルではありません) を選択します。

3. 「**プロパティ**」ウィンドウで「**詳細**」セクション (ウィンドウの下部) を展開し、「**データ カテゴリ**」ドロップダウン リストから「**国/地域**」を選択します。

    ![画像 352](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image32.png)

    "データ分類によってレポート デザイナーにヒントを提供できます。*この場合、列を国または地域に分類すると、マップ ビジュアライゼーションをレンダリングするときに、Power BI はより正確な情報を得られます。"*

### <a name="task-3-configure-the-reseller-table"></a>**タスク 3: Reseller テーブルを構成する**

このタスクでは、**Reseller** テーブルを構成します。

1. **Reseller** テーブルに、次の 2 つのレベルを持つ **Resellers** という名前の階層を作成します。

    - Business Type

    - Reseller

    ![画像 351](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image33.png)

2. 次の 4 つのレベルを持つ **Geography** という名前の 2 番目の階層を作成します。

    - Country-Region

    - State-Province

    - City

    - Reseller

    ![画像 353](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image34.png)

3. 次の 3 つの列を分類します。

    - **Country-Region** を **[国/地域]** として

    - **State-Province** を **[都道府県]** として

    - **City** を **[市区町村]** として

### <a name="task-4-configure-the-sales-table"></a>**タスク 4: Sales テーブルを構成する**

このタスクでは、**Sales** テーブルを構成します。

1. **Sales** テーブルで、**Cost** 列を選択します。

2. **[プロパティ]** ペインの **[説明]** ボックスに、次のように入力します。**Based on standard cost**

    ![画像 358](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image35.png)

    "説明は、テーブル、列、階層、またはメジャーに適用できます。***[フィールド]** ペインでレポート作成者がフィールドの上にカーソルを置いたとき、説明のテキストがヒントに表示されます。* "

3. **Quantity** 列を選択します。

4. **[プロパティ]** ペインの **[書式設定]** セクションで、**[桁区切り記号]** を **[オン]** にスライドします。

    ![画像 357](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image36.png)

5. **Unit Price** 列を選択します。

6. **[プロパティ]** ペインの **[書式設定]** セクションで、**[小数点以下の桁数]** プロパティを **2** にスライドします。

7. **[詳細]** グループ (下にスクロールして見つける必要がある場合があります) の **[集計の方法]** のドロップダウン リストで、**[平均]** を選択します。

    ![画像 354](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image37.png)

    "*既定では、数値型の列は、値を合計して集計されます。この既定の動作は、レートを表す **Unit Price** のような列には適していません。既定の集計を平均に設定すると、有用な結果が得られます。"*

### <a name="task-5-bulk-update-properties"></a>**タスク 5: プロパティを一括更新する**

このタスクでは、1 回の一括更新で複数の列を更新します。 この方法を使用して列を非表示にし、列の値を書式設定します。

1. **[フィールド]** ウィンドウで、**Product \| ProductKey** 列を選択します。

2. **Ctrl** キーを押しながら、次の 13 個の列 (複数のテーブルにまたがる) を選択します。

    - Region \| SalesTerritoryKey

    - Reseller \| ResellerKey

    - Sales \| EmployeeKey
    
    - Sales \| ProductKey

    - Sales \| ResellerKey

    - Sales \| SalesOrderNumber

    - Sales \| SalesTerritoryKey

    - Salesperson \| EmployeeID

    - Salesperson \| EmployeeKey

    - Salesperson \| UPN

    - SalespersonRegion \| EmployeeKey

    - SalespersonRegion \| SalesTerritoryKey

    - Targets \| EmployeeID

3. **[プロパティ]** ペインで、**[非表示]** プロパティを **[オン]** にスライドします。

    ![画像 355](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image38.png)

    *列はリレーションシップによって使用されるか、行レベルのセキュリティ構成または計算ロジックで使用されるため、非表示に設定されました。*

    "「**Power BI Desktop でデータをモデル化する (パート 2)** 」のラボでは、**UPN** 列を使用して、行レベルのセキュリティを定義します。*「**Power BI Desktop で DAX 計算を作成する (パート 1)** 」のラボでは、**SalesOrderNumber** を計算に使用します。"*

4. 次の 3 列を複数選択します。

    - Product \| Standard Cost

    - Sales \| Cost

    - Sales \| Sales

5. **[プロパティ]** ペインの **[書式設定]** セクションで、**[小数点以下の桁数]** プロパティを **0** (ゼロ) に設定します。

    ![画像 356](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image39.png)

## <a name="exercise-3-review-the-model-interface"></a>**演習 3: モデル インターフェイスを確認する**

この演習では、レポート ビューに切り替えて、モデル インターフェイスを確認します。

### <a name="task-1-review-the-model-interface"></a>**タスク 1: モデル インターフェイスを確認する**

このタスクでは、レポート ビューに切り替えて、モデル インターフェイスを確認します。

1. レポート ビューに切り替えます。

2. **[フィールド]** ペインで、次の点に注目してください。

    - 列、階層、およびそれらのレベルはフィールドであり、レポートのビジュアルを構成するために使用できます

    - レポート作成に関連するフィールドのみが表示されます

    - **SalespersonRegion** テーブルは表示されません。そのフィールドがすべて非表示になっているためです

    - **Region** および **Reseller** テーブルの Spatial フィールドには、空間アイコンが付きます

    - 既定では、シグマ記号 (Ʃ) の付いたフィールドが集計されます

    - **Sales \| Cost** フィールド上にカーソルを置くと、ヒントが表示されます

3. **Sales \| OrderDate** フィールドを展開し、日付階層が表示されることを確認します。

    ![画像 359](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image40.png)

    "**Targets \| TargetMonth** フィールドも同様の階層を提供します。*これらの階層は自分で作成したものではありません。自動的に作成されました。ただし、問題があります。Adventure Works の会計年度は、毎年 7 月 1 日に始まります。ただし、この自動的に作成された日付階層では、日付階層の年は毎年 1 月 1 日に始まります。"*

    "この自動動作をオフにすることにします。*「**Power BI Desktop での DAX 計算の作成 (パート 1)** 」のラボでは、DAX を使用して日付テーブルを作成し、Adventure Works 社のカレンダーを定義するように構成します。"*

4. 自動日時をオフにするには、**[ファイル]** リボン タブをクリックして Backstage ビューを開きます。

5. 左側の **[オプションと設定]** を選択してから、**[オプション]** を選択します。

    ![画像 360](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image41.png)

6. **[オプション]** ウィンドウの左側にある **[現在のファイル]** グループで、**[データの読み込み]** を選択します。

    ![画像 361](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image42.png)

7. **[タイム インテリジェンス]** セクションで、**[自動の日付/時刻]** チェック ボックスをオフにします。

    ![画像 362](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image43.png)

8. **[OK]** をクリックします。

    ![画像 9](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image44.png)

9. **[フィールド]** ペインで、日付階層がなくなっていることを確認します。

    ![画像 363](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image45.png)



### <a name="task-2-finish-up"></a>**タスク 2: 完了**

このタスクでは、ラボを完了します。

1. Power BI Desktop ファイルを保存します。

2. クエリの適用を確認するメッセージが表示された場合は、**[後で適用]** をクリックします。

3. 次のラボを開始する場合は、Power BI Desktop を開いたままにしておきます。

    *「**Power BI Desktop でデータをモデル化する (パート 2)** 」のラボでは、多対多のリレーションシップと行レベルのセキュリティを構成することによってデータ モデルを強化します。*
