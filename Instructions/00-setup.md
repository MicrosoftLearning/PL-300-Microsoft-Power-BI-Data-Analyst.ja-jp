---
lab:
  title: 独自の環境のセットアップ
  module: Set up your own environment
---

# <a name="setup-local-lab-environment"></a>ローカル ラボ環境のセットアップ

- すべてのセットアップとリソースのファイルは、[GitHub からダウンロード](https://github.com/MicrosoftLearning/PL-300-Microsoft-Power-BI-Data-Analyst/raw/Main/AllfilesDownload.zip)できます。
- 'AllFiles' を D:/ に抽出し、名前を PL300 に変更します。

これらのラボは、ホストされているラボ環境で実行することをお勧めします。 ご自分のコンピューターで実行する場合は、次のソフトウェアをインストールしてください。

***独自の環境を使用すると、予期しないダイアログと動作が発生する可能性があります。可能なローカル構成の範囲が広いため、コース チームは、独自の環境で発生する可能性のある問題をサポートできません。***

## <a name="instructions-using-windows-11"></a>Windows 11 を使用する手順

> &#128221; 以下の手順は、Windows 11 コンピューター用です。 別の OS から接続しても、同じエクスペリエンスが得られない場合があります。

### <a name="sql-server-database-engine"></a>SQL Server データベース エンジン

1. このラボは localhost SQL Server インスタンスに接続します。 次の手順は、SQL Server のインストールと既定のオプションの構成に役立ちます。 データベース エンジン機能をインストールする必要があるだけです。

    - [インストール メディアの無料の開発者用コピー](https://www.microsoft.com/sql-server/sql-server-downloads?SilentAuth=1&f=255&MSPPError=-2147217396&rtc=1)をダウンロードする
    - [SQL Server をインストール ウィザードからインストールする (セットアップ)](https://learn.microsoft.com/sql/database-engine/install-windows/install-sql-server-from-the-installation-wizard-setup)

> &#128221; ローカル バージョンをインストールする代わりに、アクセス権がある場合は、既存の SQL Server インスタンスを使用できます。 しかし、接続文字列を "localhost" からご利用のインスタンス名に変更する必要があります。

### <a name="power-bi-desktop"></a>Power BI Desktop

1. Microsoft Store からダウンロードしてインストールします。 Microsoft ストアにアクセスできない場合は、[Web](https://www.microsoft.com/download/details.aspx?id=58494) からダウンロードします。 Power BI Desktop は、これらのラボにおけるプライマリ アプリケーションです。

    - インストーラーで既定のオプションを使用します。

### <a name="microsoft-edge"></a>Microsoft Edge

1. 最新バージョンの [Microsoft Edge](https://microsoft.com/edge) をインストールして、Power BI サービスにオンラインでアクセスします。

### <a name="m365-developer-account"></a>M365 開発者アカウント

一部の演習では、組織アカウントを使用して Power BI にログインする必要があります。 独自のものを使用できますが、アクセス権がない場合は、無料の [M365 開発者アカウント](https://developer.microsoft.com/en-us/microsoft-365/dev-program)を作成できます。

