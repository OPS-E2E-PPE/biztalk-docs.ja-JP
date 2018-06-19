---
title: Microsoft BizTalk Adapter for SQL Server - 2016 のインストール |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bcc6b94e-1cac-4b90-8567-05b33caa9bf3
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bab2a1edc7f3f19a8f76a041472a8c6d01b7743d
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25967912"
---
# <a name="install-microsoft-biztalk-adapter-for-sql-server---2016"></a>Microsoft BizTalk Adapter for SQL Server - 2016 のインストールします。
インストール、[!INCLUDE[adaptersql_md](../../includes/adaptersql-md.md)]に含まれている[!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]です。

 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]で使用できます。  
  
-   .NET アプリケーション  
  
-   Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]  
  
 アダプターを使用する方法に基づき、必要なソフトウェアによって異なります。  
 
  
<a name="BKMK_prereq_NET"></a>   
## <a name="prerequisites-when-using-the-adapter-with-a-net-application"></a>.NET アプリケーションで、アダプターを使用する場合の前提条件  
次のソフトウェアを使用する .NET アプリケーションを作成するコンピューターにインストール、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。 示されている順序で、ソフトウェアをインストールします。  

||
|---|
|Windows Server 2016 <br />Windows Server 2012 R2 <br />Windows 10 <br />-Windows 8.1    |
|.NET Framework 4.6.*x*|
|Visual Studio 2015|
|[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]|
|SQL Server のクライアント ライブラリです。 参照してください、[サポートされているバージョン](#BKMK_SuppLOB)(」を参照)。|

<a name="BKMK_prereq_BTS"></a>     
## <a name="prerequisites-when-using-the-adapter-with-biztalk-server"></a>BizTalk Server でアダプターを使用する場合の前提条件  
次のソフトウェアを使用しているコンピューターにインストール、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]です。 この順で、ソフトウェアをインストールします。  

||
|---|
|Windows Server 2016 <br />Windows Server 2012 R2 <br />Windows 10 <br />-Windows 8.1    |
|.NET Framework 4.6.*x*|
|Visual Studio 2015|
|[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]<br /><br /> インストール、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]の[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]に含まれている、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]です。 インストールするには、**カスタム**(選択**BizTalk Server アドイン**) または**完了**のインストール、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]です。|
|[!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]|
|SQL Server のクライアント ライブラリです。 参照してください、[サポートされているバージョン](#BKMK_SuppLOB)(」を参照)。|

<a name="BKMK_SuppLOB"></a>   
## <a name="supported-sql-server-versions-and-client-libraries"></a>サポートされている SQL Server のバージョンとクライアント ライブラリ  
 次のセクションではサポートされている SQL Server のバージョンと、クライアントで必要なライブラリ、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。  
  
-   **サポートされているサーバー バージョン**: SQL Server 2016、SQL Server 2014
  
-   **サポートされているクライアント バージョン**: Microsoft[!INCLUDE[btsDotNetFramework_md](../../includes/btsdotnetframework-md.md)]バンドルの SQL Server に接続するクライアント Dll が必要です。 お使いのコンピューターに明示的に任意のクライアント Dll をインストールする必要はありません。  
  
-   **必要なドライバー**:  
  
    -   SQL Server のバージョン、たとえば、Geography に付属して Udt を使用する場合は、次の Dll は、SQL Server 上の操作を実行するアダプターを使用するコンピューター上に存在を確認します。 など、SQL Server 上の操作を実行する BizTalk プロジェクトを作成する場合は、これらの Dll が BizTalk Server が実行されているコンピューター上に存在する必要があります。  
  
        -   Microsoft.SqlServer.Types.dll は GAC に追加することを確認します。  
  
        -   SqlServerSpatial.dll が System32 フォルダーにあることを確認してください。  
  
         SQL Server セットアップを実行しを選択すると、コンピューターにこれらの Dll をインストールできます**管理ツール-基本**と**管理ツール-完全**で、**機能の選択**ウィザードのページです。  
  
    -   FILESTREAM データ型の列に対して操作を実行するアダプターを使用する場合は、SQL クライアント接続 SDK がインストールされている必要があることを確認してください。 SQL Server セットアップを実行しを選択すると、SQL クライアント接続 SDK をインストールすることができます**SQL クライアント接続 SDK**で、**機能の選択**ウィザードのページです。 アダプターは、FILESTREAM 操作を実行するのに、SQL クライアント接続 SDK と共にインストールされる、sqlncli10.dll を使用します。  
  
    -   SQL Server で、独自の Udt を作成する場合は、Udt のそれぞれのアセンブリが GAC に追加を確認します。  
  
<a name="BKMK_Compat"></a>   
## <a name="64-bit-support"></a>64 ビットのサポート 

[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] 32 ビットまたは 64 ビット ホスト インスタンスで実行できます。

 32 ビットおよび 64 ビットのサポートされているインストール シナリオについては[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]を参照してください[32 ビットおよび 64 ビット インストール シナリオ](#BKMK_Install_Scenarios)(」を参照)。
  
<a name="BKMK_Install_Adap"></a>   
## <a name="install-the-sql-adapter"></a>SQL アダプターをインストールします。  
 インストールする前にインストールされている前提条件があるかどうかを確認、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。 参照してください[.NET の前提条件](#BKMK_prereq_NET)(このトピックの)、または[BizTalk Server の前提条件](#BKMK_prereq_BTS)(」を参照)。
  
 インストールすることができます、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]次の 2 つの方法で。  
  
-   **対話モードで**セットアップ ウィザードを使用します。
  
-   **サイレント モードで**コマンド ラインで msiexec を使用します。  
  
    > [!IMPORTANT]
    >  インストールするコンピューターで管理者特権を持つ必要があります、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]ウィザードまたはコマンドラインを使用してインストールするかどうかのあるかにかかわらず、します。    

### <a name="BKMK_Install_Scenarios"></a>32 ビットおよび 64 ビット インストール シナリオ
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]に使用できます。  
  
-   [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]デザイン時 (操作のメタデータを生成する) ときにします。  
  
-   BizTalk Server 管理コンソール デザイン時 (物理ポートの作成) します。  
  
    > [!NOTE]
    >  BizTalk Server 管理コンソールは、32 ビット Microsoft 管理コンソール (MMC) アプリケーションとして実行されます。  
  
-   BizTalk ランタイム (ときに送信し、LOB アプリケーションからメッセージを受信)。  
  
 同じコンピューターまたは別のコンピューターでこれらすべてのタスクを実行するインストールことができます。 両方[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]と BizTalk MMC は 32 ビット プロセスが、32 ビットをインストールする必要があります[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]デザイン時のタスクを実行するコンピューターにします。 インストールするため、次のシナリオがサポートされている、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] 32 ビットおよび 64 ビット プラットフォーム上でします。  
  
#### <a name="32-bit-install-scenarios"></a>32 ビット インストール シナリオ  
 インストールするときに、次のシナリオがサポートされて、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] 32 ビット プラットフォーム上でします。  
  
|Visual Studio のデザイン時|デザイン時の BizTalk MMC|BizTalk ランタイム|Visual Studio デザイン時またはデザイン時の BizTalk MMC + BizTalk ランタイムします。|  
|---|---|---|---|  
|がインストール 32 ビット[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]です。<br /><br /> がインストール 32 ビット[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。<br /><br /> 32 ビット クライアントとその他の必要な Dll をインストールします。|がインストール 32 ビット[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]です。<br /><br /> がインストール 32 ビット[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。<br /><br /> 32 ビット クライアントとその他の必要な Dll をインストールします。|がインストール 32 ビット[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]です。<br /><br /> がインストール 32 ビット[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。<br /><br /> 32 ビット クライアントとその他の必要な Dll をインストールします。|がインストール 32 ビット[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]です。<br /><br /> がインストール 32 ビット[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。<br /><br /> 32 ビット クライアントとその他の必要な Dll をインストールします。|  
  
#### <a name="64-bit-install-scenarios"></a>64 ビット インストール シナリオ  
 インストールするときに、次のシナリオがサポートされて、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] 64 ビット プラットフォーム上でします。  
  
> [!NOTE]
>  いずれかを使用してデザイン時のタスクを実行する任意のコンピューターで[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]BizTalk MMC で、32 ビットをインストールする必要がありますまたは[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。  
  
|Visual Studio のデザイン時|デザイン時の BizTalk MMC|BizTalk ランタイム|Visual Studio デザイン時またはデザイン時の BizTalk MMC + BizTalk ランタイムします。|  
|---|---|---|---|  
|がインストール 64 ビット[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]です。<br /><br /> がインストール 32 ビット[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。<br /><br /> 32 ビット クライアントとその他の必要な Dll をインストールします。|がインストール 64 ビット[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]です。<br /><br /> がインストール 32 ビット[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。<br /><br /> 32 ビット クライアントとその他の必要な Dll をインストールします。|**32 ビット BizTalk プロセス**:<br /><br /> がインストール 64 ビット[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]です。<br /><br /> がインストール 32 ビット[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。<br /><br /> 32 ビット クライアントとその他の必要な Dll をインストールします。<br /><br /> **64 ビットの BizTalk プロセス**:<br /><br /> がインストール 64 ビット[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]です。<br /><br /> がインストール 64 ビット[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。<br /><br /> -64 ビット クライアントとその他の必要な Dll をインストールします。|**32 ビット BizTalk プロセス**:<br /><br /> がインストール 64 ビット[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]です。<br /><br /> がインストール 32 ビット[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。<br /><br /> 32 ビット クライアントとその他の必要な Dll をインストールします。<br /><br /> **64 ビットの BizTalk プロセス**:<br /><br /> がインストール 64 ビット[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]です。<br /><br /> がインストール 64 ビット[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。<br /><br /> -64 ビット クライアントとその他の必要な Dll をインストールします。<br /><br /> がインストール 32 ビット[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。<br /><br /> 32 ビット クライアントとその他の必要な Dll をインストールします。|  
  
<a name="BKMK_Install_wizard"></a>   
### <a name="install-the-adapter-in-interactive-mode"></a>対話モードでのアダプターをインストールします。  
次の手順に従って、インストールを完了、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]セットアップ ウィザードを使用します。  
  
1.  インストーラーを実行します。  
  
    > [!NOTE]
    >  インストールする場合、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]バーチャル マシンで、セットアップ ウィザードは使用可能なディスク容量については、セットアップがチェックされることを通知 ダイアログ ボックス続行されません可能性があります。 このような場合、サイレント インストール オプションを使用することをお勧めします。 詳細については、次を参照してください。[サイレント モードで、SQL アダプターをインストール](#BKMK_SilentInst)(」を参照)。
  
2.  [ようこそ] 画面で、情報を参照し、をクリックして**次**です。  
  
3.  読み取り、使用許諾契約書 (EULA) に同意し、クリックして**次**です。  
  
4.  **コピー先フォルダー**  ダイアログ ボックスで、インストールする場所を指定、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]、 をクリックして **[次へ]**、クリックして**インストール**です。  
  
5.  **カスタマー エクスペリエンス向上プログラム** ダイアログ ボックスで、カスタマー エクスペリエンス向上プログラム (CEIP) に登録するかどうかを指定します。 CEIP 用の一部として[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]、次のデータは、Microsoft と共有されます。  
  
    -   インストールしているコンピューターのハードウェアに関連するデータ、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。  
  
    -   使用して接続を使用している SQL Server のバージョンに関連するデータ、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。  
  
     指定し、をクリックして**OK**です。  
  
    > [!NOTE]
    >  常に、基本設定を変更することができます修復モードで、コントロール パネルから、セットアップを実行して、CEIP の登録に関連します。  
  
6.  **[完了]** をクリックします。  
  
<a name="BKMK_SilentInst"></a>   
### <a name="install-the-sql-adapter-in-silent-mode"></a>サイレント モードでの SQL アダプターをインストールします。 
サイレント インストールを行うには、次の手順を完了[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]を使用して、`msiexec`コマンド。  
  
1.  コマンド プロンプトを開き、および、インストーラーを持っているフォルダーに移動します。  
  
2.  インストールするには、次のコマンドを実行、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]:  
  
    > [!NOTE]
    >  次のコマンドでの x64 ベースのプラットフォームでサイレント インストールを実行するには、SqlAdapterSetup64.msi で SqlAdapterSetup.msi を置き換えます。  
  
    ```  
    msiexec /i SqlAdapterSetup.msi /qn  
    ```  
  
     CEIP をサイレント インストールの一部として登録することもできます。 CEIP 用の一部として[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]、次のデータは、Microsoft と共有されます。  
  
    -   インストールしているコンピューターのハードウェア、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。  
  
    -   使用して接続を使用している SQL Server のバージョン、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。  
  
     CEIP の登録には、するには、次のコマンドを実行します。  
  
    ```  
    msiexec /i SqlAdapterSetup.msi /qn CEIP_OPTIN=true  
    ```  
  
     既定では、このオプションは false です。  
  
     詳細については、`msiexec`コマンドを入力`msiexec`キーを押して、コマンド ライン`ENTER`を参照してくださいまたは[https://support.microsoft.com/kb/230781](https://support.microsoft.com/kb/230781)です。  
  
<a name="BKMK_PostInst"></a>   
## <a name="post-installation-tasks"></a>インストール後のタスク  
  
<a name="BKMK_Register_Bindings"></a>   
#### <a name="register-the-bindings"></a>バインドを登録します。  
次の手順を完了*のみ*machine.config ファイルにアダプターのバインドを登録するセットアップ ウィザードが失敗した場合。  
  
1.  コンピューター上の machine.config ファイルに移動します。 たとえば、32 ビット プラットフォームで、machine.config は下にある使用可能な\<システム ドライブ\>: \WINDOWS\Microsoft.NET\Framework\\< バージョン\>\CONFIG です。  
  
2.  テキスト エディターを使用してファイルを開きます。  
  
3.  アダプターのバインドを登録します。  
  
    1.  要素"system.serviceModel"を検索し、その下にある、次を追加します。  
  
        ```  
        <client>  
          <endpoint binding="sqlBinding" contract="IMetadataExchange" name="mssql" />  
        </client>  
        ```  
  
    2.  "BindingElementExtensions"system.serviceModel\extensions 下にある要素を検索します。  
  
    3.  "BindingElementExtensions"ノードの下の次のセクションを追加します。  
  
         [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]を追加します。  
  
        ```  
        <add name="sqlAdapter" type="Microsoft.Adapters.Sql.SqlAdapterBindingElementExtensionElement,Microsoft.Adapters.Sql, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
    4.  "BindingExtensions"system.serviceModel\extensions 下にある要素を検索します。  
  
    5.  "BindingExtensions"ノードの下の次のセクションを追加します。  
  
         [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]を追加します。  
  
        ```  
        <add name="sqlBinding" type="Microsoft.Adapters.Sql.SqlAdapterBindingCollectionElement,Microsoft.Adapters.Sql, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
    > [!NOTE]
    >  公開キーを確認する方法については、次を参照してください。[公開キーとバージョンを決定する](#BKMK_PubKey)です。  
  
4.  machine.config ファイルを保存して閉じます。  
  
<a name="BKMK_PubKey"></a>   
#### <a name="determining-the-public-key-and-version"></a>公開キーとバージョンを決定します。  
公開キーとバージョンを確認するのには、次の手順を完了、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。  
  
1.  Windows ディレクトリの通常 C:\WINDOWS\assembly に移動します。  
  
2.  対象の公開キーを指定してを選択し、DLL を右クリックして**プロパティ**です。 次の表の Dll の名前、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。  
  
    |[アダプター]|DLL の名前|  
    |---|---|  
    |[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]|Microsoft.Adapters.Sql.dll|  
  
3.  **全般** タブの値と比較、**公開キー トークンの**ラベルは、DLL の公開キーを指定します。 同様の値と比較、**バージョン**ラベルは、DLL のバージョン番号を指定します。  
  
4.  公開キーをコピーし、をクリックして**キャンセル**です。  
  
<a name="BKMK_Modify_Adap"></a>   
## <a name="update-or-change-the-sql-adapter-installation"></a>更新または変更する SQL アダプターのインストール  
 変更するのには、次の手順を実行、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]インストールします。 あるかどうかを確認、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]を変更するセットアップ ウィザードを実行する前にインストールされている、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]インストールします。  
  
 変更することができます、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]次の 2 つの方法でインストールします。  
  
-   **対話モードで**セットアップ ウィザードを実行しています。  
  
-   **サイレント モードで**コマンドラインを使用しています。  
  
#### <a name="update-the-sql-adapter-installation-in-interactive-mode"></a>対話モードで SQL アダプターのインストールを更新します。  
  
1.  をクリックして**開始**、順にクリック**コントロール パネルの** です。  
  
2.  コントロール パネルで、ダブルクリック**プログラムと機能**します。  
  
3.  **プログラムと機能**ウィンドウで、 **Microsoft BizTalk Adapter for SQL Server**、クリックして**変更**です。  
  
4.  [ようこそ] 画面で、情報を参照し、をクリックして**次**です。  
  
5.  **変更、修復、または削除インストール**ダイアログ ボックスで、をクリックして**修復**です。  
  
6.  **SQL Server 用 Microsoft BizTalk Adapter を修復する準備が**ダイアログ ボックスで、をクリックして**修復**です。  
  
7.  必要に応じて、ユーザーの設定を変更に関して、CEIP を無効にして、をクリックして**OK**です。  
  
8.  **[完了]** をクリックします。  
  
#### <a name="update-the-sql-adapter-installation-in-silent-mode"></a>更新プログラムのサイレント モードで SQL アダプターのインストール  
  
1.  コマンド プロンプトを開きのルート ディレクトリに移動、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]インストーラーです。  
  
2.  次のコマンドを実行します。  
  
    > [!NOTE]
    >  変更する、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] SqlAdapterSetup64.msi で次のコマンドでの x64 ベースのプラットフォームにサイレント モードでインストールが SqlAdapterSetup.msi を置き換えます。  
  
    ```  
    msiexec /i SqlAdapterSetup.msi /qn /f  
    ```  
  
    > [!IMPORTANT]
    >  変更中に、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]サイレント モードでインストールで CEIP を有効または無効にするための設定を変更することはできません。 環境設定は変わりません、インストール時に指定したとおり、CEIP_OPTIN を true または false に明示的に設定した場合でもです。  
  
     詳細については、`msiexec`コマンドの種類を`msiexec`キーを押して、コマンド ライン`ENTER`を参照してくださいまたは[https://support.microsoft.com/kb/230781](https://support.microsoft.com/kb/230781)です。  
  
<a name="BKMK_Remove_Adap"></a>   
## <a name="uninstall-or-remove-the-sql-adapter"></a>アンインストールするか、SQL アダプターを削除します。  
 削除するには、次の手順を実行、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]コンピューターからです。 あるかどうかを確認、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]を削除するセットアップ ウィザードを実行する前にインストールされている、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。  
  
 削除することができます、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]次の 2 つの方法で。  
  
-   **対話モードで**セットアップ ウィザードを実行しています。  
  
-   **サイレント モードで**コマンドラインを使用しています。  
  
#### <a name="uninstall-the-sql-adapter-in-interactive-mode"></a>対話モードで SQL アダプターをアンインストールします。  
  
1.  をクリックして**開始**、順にクリック**コントロール パネルの** です。  
  
2.  コントロール パネルで、ダブルクリック**プログラムと機能**します。  
  
3.  **プログラム追加と削除**ウィンドウで、 **Microsoft BizTalk Adapter for SQL Server**、クリックして**削除**です。  
  
4.  ダイアログ ボックスで、**はい**です。  
  
#### <a name="uninstall-the-sql-adapter-in-silent-mode"></a>サイレント モードで SQL アダプターをアンインストールします。  
  
1.  コマンド プロンプトを開きのルート ディレクトリに移動、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]インストーラーです。  
  
2.  次のコマンドを実行します。  
  
    > [!NOTE]
    >  削除する、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]サイレント モードで、次のコマンドの x64 ベースのプラットフォーム上で SqlAdapterSetup64.msi で SqlAdapterSetup.msi を置き換えます。  
  
    ```  
    msiexec /x SqlAdapterSetup.msi /qn  
    ```  
  
     このコマンドを削除、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]コンピューターからです。  
  
     詳細については、`msiexec`コマンドを入力`msiexec`キーを押して、コマンド ライン`ENTER`を参照してくださいまたは[https://support.microsoft.com/kb/230781](https://support.microsoft.com/kb/230781)です。  
  
<a name="BKMK_PostRemove"></a>   
### <a name="post-uninstall-task"></a>アンインストール後のタスク  
 場合、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]バインドを削除する、アダプターの削除中にセットアップが失敗した、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]、それらを手動で削除する必要があります。 次のセクションのバインドを手動で削除する方法について説明、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。  
  
次の手順を完了*のみ*バインドを削除する、アダプター、machine.config ファイルから、セットアップ ウィザードが失敗した場合。  
  
1.  コンピューター上の machine.config ファイルに移動します。 たとえば、32 ビット プラットフォームで、machine.config は下にある使用可能な\<システム ドライブ\>: \WINDOWS\Microsoft.NET\Framework\\< バージョン\>\CONFIG です。  
  
    -   Microsoft .NET framework 3.5 SP1、 \<*バージョン*\> .NET Framework のバージョン v2.0.50727 がします。  
  
    -   Microsoft の[!INCLUDE[netfx40_short](../../includes/netfx40-short-md.md)]、 \<*バージョン*\>は、.NET Framework のバージョン v4.0.30319 します。  
  
2.  テキスト エディターを使用してファイルを開きます。  
  
3.  アダプターのバインドの登録を削除します。  
  
    1.  要素"system.serviceModel"を検索し、次の要素の下を削除します。  
  
        ```  
        <client>  
          <endpoint binding="sqlBinding" contract="IMetadataExchange" name="mssql" />  
        </client>  
  
        ```  
  
    2.  "BindingElementExtensions"system.serviceModel\extensions 下にある要素を検索します。  
  
    3.  "BindingElementExtensions"ノードの下に、次のセクションを削除します。  
  
         [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]、削除します。  
  
        ```  
        <add name="sqlAdapter" type="Microsoft.Adapters.Sql.SqlAdapterBindingElementExtensionElement,Microsoft.Adapters.Sql, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
    4.  "BindingExtensions"system.serviceModel\extensions 下にある要素を検索します。  
  
    5.  "BindingExtensions"ノードの下に、次のセクションを削除します。  
  
         [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]、削除します。  
  
        ```  
        <add name="sqlBinding" type="Microsoft.Adapters.Sql.SqlAdapterBindingCollectionElement,Microsoft.Adapters.Sql, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
4.  machine.config ファイルを保存して閉じます。  
  
## <a name="see-also"></a>参照
[SQL アダプターをインストールする](../../adapters-and-accelerators/adapter-sql/install-the-sql-adapter.md)  
[BizTalk Adapter for SQL Server を理解する](../../adapters-and-accelerators/adapter-sql/understand-biztalk-adapter-for-sql-server.md)