---
demo:
  "\_\_ title": Enforce Row-level security in Power BI
  "\_\_ module": Deploy and manage Power BI service items
---
# Power BI で行レベルのセキュリティを適用する

## モデルにセキュリティ テーブルを追加する

1. Power BI Desktop で、Power Query エディター ウィンドウを開きます。

1. `D:\Demo\Data\**ManagerCategory**.xlsx` ファイルに基づいて新しいクエリを追加します。

1. このファイルの **ManagerCategory** テーブルを使います。

1. **[Manager]** 列を削除します。

1. **Category** 列をセミコロン区切り記号で分割し、行に分割します (詳細オプション)。

1. **Email** 列の値 **<ty-johnston@tailspintoys.com>** を (MySettings.txt ファイルの) 受信者アカウントに置き換えます。

1. このユーザーは **Collective pitch、Trainer、Warbird** という 3 つの製品カテゴリを表示できることに注目してください。

1. 閉じてクエリを適用します。

1. モデル ビューで、**ManagerCategory** と Product の各テーブル間に、**Category** 列に関連するリレーションシップを作成します。

1. クロス フィルターの方向を [単一] (**ManagerCategory** が Product をフィルター処理する) に設定します。

1. **[ManagerCategory]** テーブルを非表示にします。

## ロールを追加する

1. レポート ビューで [ロールの​​管理] を開き、「**Manager**」という名前のロールを作成します。

1. ロールで、**[ManagerCategory]** テーブルの [Email] アドレス列を次のようにフィルター処理します。

  ```dax
   [Email] = USERPRINCIPALNAME()
   ```

1. **保存**。

## ロールを検証する

1. [表示方法] を開き、次の設定を行います。

    - その他のユーザー:オンにして、受信者アカウントを入力します。

    - マネージャー ロール:オン

1. フィルター ビジュアルには 3 つの製品カテゴリしか表示されないことを示します。

1. 表示方法オプションを使用してレポートの表示を停止します。

1. Power BI Desktop ファイルを保存します。

1. Power BI Desktop ファイルをワークスペースに発行し、サービスのデータセットとレポートを上書きします。

1. Power BI Desktop を閉じます。

## データセットのセキュリティを構成する

1. 講師用の Power BI サービスで、[ナビゲーション] ウィンドウから **[売上分析]** データセットのセキュリティ ページを開きます。

1. [メンバー] セクションで、(**Ty Johnston** を表す) 受信者アカウントを入力します。

1. [追加] して [保存] します。

## アプリで行レベルのセキュリティをテストする

1. 受信者用の Power BI サービスで、ダッシュボードをリフレッシュします (前回のデモで開いたままになっています)。

1. **Profit Margin** ダッシュボード タイルで、3 つの製品カテゴリのみが表示されていることを確認します。
