---
title: Microsoft BizTalk Adapter for SQL Server - 2013 R2 および 2013 インストール |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 56c31d0d-783b-41ee-8265-56c9547e9dca
caps.latest.revision: 31
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 05e2edcd96bd7615da8175282a646b77e16c9759
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65369388"
---
# <a name="install-microsoft-biztalk-adapter-for-sql-server---2013-r2-and-2013"></a>Microsoft BizTalk Adapter for SQL Server - 2013 R2 および 2013 インストールします。
インストール、[!INCLUDE[adaptersql_md](../../includes/adaptersql-md.md)]に含まれている[!INCLUDE[bts2013r2_md](../../includes/bts2013r2-md.md)]、またはに付属[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]2013。

 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]で使用できます。  

- .NET アプリケーション  

- Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]  

  アダプターを使用する方法に基づき、必要なソフトウェアによって異なります。  

<a name="BKMK_Prereqs_NET"></a>   
## <a name="prerequisites-when-using-the-adapter-with-a-net-application"></a>.NET アプリケーション、アダプターを使用する際の前提条件  
次のソフトウェアを使用する .NET アプリケーションを作成するコンピューターにインストール、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。 記載されている順序で、ソフトウェアをインストールします。  


|                                 2013 R2                                 |                                  2013                                   |
|-------------------------------------------------------------------------|-------------------------------------------------------------------------|
|          [!INCLUDE[dotnet451](../../includes/dotnet451-md.md)]          |      Microsoft [!INCLUDE[dotnet45](../../includes/dotnet45-md.md)]      |
|                           Visual Studio 2013                            |                           Visual Studio 2012                            |
| [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] | [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] |
|                   SQL Server のクライアント ライブラリ。 .                    |                    SQL Server のクライアント ライブラリ.                    |

<a name="BKMK_Prereqs_BTS"></a>    
## <a name="prerequisites-when-using-the-adapter-with-biztalk-server"></a>BizTalk Server でアダプターを使用する場合の前提条件  
使用するコンピューターで、次のソフトウェアをインストール、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]します。 ここに示すように同じ順序で、ソフトウェアをインストールすることをお勧めします。  


|                                                                                                                                                                                                                                                               2013 R2                                                                                                                                                                                                                                                               |                                                                                                                                                                                                                                                                2013                                                                                                                                                                                                                                                                 |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                                                                                                                                                                                                                        [!INCLUDE[dotnet451](../../includes/dotnet451-md.md)]                                                                                                                                                                                                                                        |                                                                                                                                                                                                                                    Microsoft [!INCLUDE[dotnet45](../../includes/dotnet45-md.md)]                                                                                                                                                                                                                                    |
|                                                                                                                                                                                                                                                         Visual Studio 2013                                                                                                                                                                                                                                                          |                                                                                                                                                                                                                                                         Visual Studio 2012                                                                                                                                                                                                                                                          |
| [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]<br /><br /> インストール、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]の[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]に含まれている、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]します。 インストールするには、**カスタム**(選択**BizTalk Server アドイン**) または**完了**のインストール、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]します。 | [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]<br /><br /> インストール、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]の[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]に含まれている、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]します。 インストールするには、**カスタム**(選択**BizTalk Server アドイン**) または**完了**のインストール、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]します。 |
|                                                                                                                                                                                                                                                       BizTalk Server 2013 R2                                                                                                                                                                                                                                                        |                                                                                                                                                                                                                                                         BizTalk Server 2013                                                                                                                                                                                                                                                         |
|                                                                                                                                                                                                                                                  SQL Server のクライアント ライブラリ。                                                                                                                                                                                                                                                   |                                                                                                                                                                                                                                                  SQL Server のクライアント ライブラリ。                                                                                                                                                                                                                                                   |

<a name="BKMK_SuppLOB"></a>   
## <a name="supported-sql-server-versions-and-client-libraries"></a>サポートされている SQL Server のバージョンとクライアント ライブラリ  
 次のセクションではサポートされている SQL Server のバージョンと、クライアントで必要なライブラリ、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。  

- **サポートされているサーバー バージョン**:SQL Server 2005、SQL Server 2008 SP1、SQL Server 2008 R2、SQL Server 2012  

- **サポートされているクライアント バージョン**:Microsoft [!INCLUDE[dotnet45](../../includes/dotnet45-md.md)] SQL Server に接続するために必要なクライアント Dll バンドルします。 コンピューターに任意のクライアントの Dll を明示的にインストールする必要はありません。  

- **ドライバーに必要な**:  

  - SQL Server のバージョン、たとえば、geography 型に付属の Udt を使用する場合、次の Dll は SQL Server での操作を実行するアダプターを使用するコンピューター上に存在することを確認します。 たとえば、SQL Server での操作を実行する BizTalk プロジェクトを作成する場合これらの Dll は BizTalk Server が実行されているコンピューター上に存在である必要があります。  

    - Microsoft.SqlServer.Types.dll は GAC に追加することを確認します。  

    - SqlServerSpatial.dll が System32 フォルダーにあることを確認します。  

      コンピューターにこれらの Dll をインストールするには、SQL Server セットアップを実行し、選択**管理ツール-基本**と**管理ツール-完全**で、**機能の選択**ウィザードのページ。  

  - FILESTREAM データ型の列に対する操作を実行するアダプターを使用する場合は、SQL Client Connectivity SDK がインストールされている必要があることを確認してください。 SQL クライアント接続 SDK をインストールするには、SQL Server セットアップを実行し、選択**SQL Client Connectivity SDK**で、**機能の選択**ウィザードのページ。 アダプターは、FILESTREAM 操作を実行するのに SQL クライアント接続 sdk では、インストールされている、sqlncli10.dll を使用します。  

  - SQL Server で、独自の Udt を作成する場合は、Udt のそれぞれのアセンブリを GAC に追加して確認します。  

<a name="BKMK_Compat"></a>   
## <a name="64-bit-support"></a>64 ビットのサポート 

[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] 32 ビットまたは 64 ビット ホスト インスタンスで実行できます。

 32 ビットおよび 64 ビットのサポートされているインストール シナリオの詳細については[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]、します。 

<a name="BKMK_Install_Adap"></a>   
## <a name="install-the-sql-adapter"></a>SQL アダプターをインストールします。  
 インストールする前にインストールされている前提条件があるかどうかを確認、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。  

 インストールすることができます、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]次の 2 つの方法で。  

- **対話モードで**セットアップ ウィザードを使用  

- **サイレント モードで**コマンドで msiexec を使用してリンク  

  > [!IMPORTANT]
  >  インストールするコンピューターの管理者特権が必要、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]のウィザードまたはコマンドラインを使用してインストールするかどうかに関係なく、します。  

<a name="BKMK_Install_Scenarios"></a>   
### <a name="32-bit-and-64-bit-install-scenarios"></a>32 ビットおよび 64 ビット インストール シナリオ
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]に使用できます。  

- [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] デザイン時 (操作のメタデータを生成) するときにします。  

- (物理ポートを作成) するための BizTalk Server 管理コンソールのデザイン時。  

  > [!NOTE]
  >  BizTalk Server 管理コンソールは、32 ビットの Microsoft 管理コンソール (MMC) アプリケーションとして実行されます。  

- BizTalk の実行時間 (LOB アプリケーションからメッセージを送受信) するときにします。  

  同じコンピューターまたは別のコンピューター上のこれらすべてのタスクを実行するインストールしてあることができます。 両方[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]BizTalk MMC は 32 ビット プロセスとは、32 ビットをインストールする必要があります[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]デザイン時のタスクを実行するコンピューター。 インストールするため、次のシナリオがサポートされている、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] 32 ビットおよび 64 ビット プラットフォーム上でします。  

#### <a name="install-scenarios-on-a-32-bit-platform"></a>32 ビット プラットフォームでのインストール シナリオ  
 インストールするときに、次のシナリオがサポートされて、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] 32 ビット プラットフォームで。  


|                                                                                                               Visual Studio のデザイン時                                                                                                                |                                                                                                                デザイン時の BizTalk MMC                                                                                                                 |                                                                                                                    BizTalk ランタイム                                                                                                                    |                                                                                      Visual Studio のデザイン時またはデザイン時の BizTalk MMC + BizTalk ランタイムします。                                                                                      |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| -32 ビットのインストール[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]します。<br /><br /> -32 ビットのインストール[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。<br /><br /> 32 ビット クライアントとその他の必要な Dll をインストールします。 | -32 ビットのインストール[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]します。<br /><br /> -32 ビットのインストール[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。<br /><br /> 32 ビット クライアントとその他の必要な Dll をインストールします。 | -32 ビットのインストール[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]します。<br /><br /> -32 ビットのインストール[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。<br /><br /> 32 ビット クライアントとその他の必要な Dll をインストールします。 | -32 ビットのインストール[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]します。<br /><br /> -32 ビットのインストール[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。<br /><br /> 32 ビット クライアントとその他の必要な Dll をインストールします。 |

#### <a name="install-scenarios-on-a-64-bit-platform"></a>64 ビット プラットフォームでのインストール シナリオ  
 インストールするときに、次のシナリオがサポートされて、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] 64 ビット プラットフォームで。  

> [!NOTE]
>  いずれかを使用して、デザイン時のタスクを実行する任意のコンピューターで[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]BizTalk MMC で、32 ビットをインストールする必要がありますまたは[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。  

|                                                                                                               Visual Studio のデザイン時                                                                                                                |                                                                                                                デザイン時の BizTalk MMC                                                                                                                 |                                                                                                                                                                                                                                                                                                   BizTalk ランタイム                                                                                                                                                                                                                                                                                                    |                                                                                                                                                                                                                                                                                                                                                    Visual Studio のデザイン時またはデザイン時の BizTalk MMC + BizTalk ランタイムします。                                                                                                                                                                                                                                                                                                                                                     |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| -64 ビットのインストール[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]します。<br /><br /> -32 ビットのインストール[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。<br /><br /> 32 ビット クライアントとその他の必要な Dll をインストールします。 | -64 ビットのインストール[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]します。<br /><br /> -32 ビットのインストール[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。<br /><br /> 32 ビット クライアントとその他の必要な Dll をインストールします。 | **32 ビット BizTalk プロセスの**:<br /><br /> -64 ビットのインストール[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]します。<br /><br /> -32 ビットのインストール[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。<br /><br /> 32 ビット クライアントとその他の必要な Dll をインストールします。<br /><br /> **64 ビットの BizTalk プロセスの**:<br /><br /> -64 ビットのインストール[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]します。<br /><br /> -64 ビットのインストール[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。<br /><br /> -64 ビット クライアントとその他の必要な Dll をインストールします。 | **32 ビット BizTalk プロセスの**:<br /><br /> -64 ビットのインストール[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]します。<br /><br /> -32 ビットのインストール[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。<br /><br /> 32 ビット クライアントとその他の必要な Dll をインストールします。<br /><br /> **64 ビットの BizTalk プロセスの**:<br /><br /> -64 ビットのインストール[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]します。<br /><br /> -64 ビットのインストール[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。<br /><br /> -64 ビット クライアントとその他の必要な Dll をインストールします。<br /><br /> -32 ビットのインストール[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。<br /><br /> 32 ビット クライアントとその他の必要な Dll をインストールします。 |

<a name="BKMK_Install_wizard"></a>   
### <a name="install-the-sql-adapter-in-interactive-mode"></a>対話モードで SQL アダプターをインストールします。  

1. インストーラーを実行します。  

   > [!NOTE]
   >  インストールする場合、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]仮想マシンで、セットアップ ウィザードは、セットアップを使用可能なディスク領域にチェックすることを知らせるダイアログ ボックスを超える続行されません可能性があります。 このような場合は、サイレント インストール オプションを使用することをお勧めします。   

2. クリックして、ようこそ画面の情報を読み取る**次**します。  

3. 読み取り、使用許諾契約書 (EULA) に同意し、クリックして**次**します。  

4. **先フォルダー**  ダイアログ ボックスで、インストールする場所を指定、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]、 をクリックして**次**、順にクリックします**インストール**。  

5. **カスタマー エクスペリエンス向上プログラム** ダイアログ ボックスで、カスタマー エクスペリエンス向上プログラム (CEIP) に登録するかどうかを指定します。 CEIP の一部として[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]、次のデータは、Microsoft と共有されます。  

   - インストール先コンピューターのハードウェアに関連するデータ、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。  

   - 関連データを使用して接続を使用している SQL Server のバージョンを[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。  

     選択を指定し、クリックして**OK**します。  

   > [!NOTE]
   >  常に、基本設定を変更することができます、コントロール パネルから修復モードでセットアップを実行して、CEIP の登録に関連します。  

6. **[完了]** をクリックします。  

<a name="BKMK_SilentInst"></a>   
### <a name="install-the-sql-adapter-in-silent-mode"></a>サイレント モードで SQL アダプターをインストールします。  
 次の手順は、のサイレント インストールを実行する方法を示します[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]を使用して、`msiexec`コマンド。  

1. コマンド プロンプトを開き、インストーラーがあるフォルダーに移動します。  

2. インストールするには、次のコマンドを実行、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]:  

   > [!NOTE]
   >  次のコマンドでの x64 ベースのプラットフォームでサイレント インストールを実行するには、SqlAdapterSetup64.msi で SqlAdapterSetup.msi を置き換えます。  

   ```  
   msiexec /i SqlAdapterSetup.msi /qn  
   ```  

    サイレント インストールの一環として、CEIP に登録することもできます。 CEIP の一部として[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]、次のデータは、Microsoft と共有されます。  

   - インストール先コンピューターのハードウェア、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。  

   - 使用して接続を使用している SQL Server のバージョン、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。  

     CEIP を登録するには、次のコマンドを実行します。  

   ```  
   msiexec /i SqlAdapterSetup.msi /qn CEIP_OPTIN=true  
   ```  

    既定では、オプションは false です。  

    詳細については、`msiexec`のコマンドを入力`msiexec`キーを押して、コマンド ラインで`ENTER`を参照してくださいまたは[ https://support.microsoft.com/kb/230781](https://support.microsoft.com/kb/230781)します。  

<a name="BKMK_PostInst"></a>   
## <a name="post-installation-tasks"></a>インストール後のタスク  

<a name="BKMK_Register_Bindings"></a>   
#### <a name="register-the-bindings"></a>バインドを登録します。  
次の手順を完了*のみ*machine.config ファイルでアダプターのバインドを登録するセットアップ ウィザードが失敗した場合。  

1. コンピューターの machine.config ファイルに移動します。 たとえば、32 ビット プラットフォームで、machine.config はで使用可能な\<システム ドライブ\>: \WINDOWS\Microsoft.NET\Framework\\< バージョン\>\CONFIG します。  

   - Microsoft .NET framework 3.5 SP1 では、 \<*バージョン*\>は .NET Framework のバージョン v2.0.50727 します。  

   - Microsoft の[!INCLUDE[netfx40_short](../../includes/netfx40-short-md.md)]、 \<*バージョン*\>は .NET Framework のバージョン v4.0.30319 します。  

2. テキスト エディターを使用してファイルを開きます。  

3. アダプターのバインドを登録するには。  

   1. 要素の"system.serviceModel"を検索し、その下にある、次を追加します。  

      ```  
      <client>  
        <endpoint binding="sqlBinding" contract="IMetadataExchange" name="mssql" />  
      </client>  
      ```  

   2. "BindingElementExtensions"system.serviceModel\extensions 下の要素を検索します。  

   3. "BindingElementExtensions"ノードの下の次のセクションを追加します。  

       [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]を追加します。  

      ```  
      <add name="sqlAdapter" type="Microsoft.Adapters.Sql.SqlAdapterBindingElementExtensionElement,Microsoft.Adapters.Sql, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

   4. "BindingExtensions"system.serviceModel\extensions 下の要素を検索します。  

   5. "BindingExtensions"ノードの下の次のセクションを追加します。  

       [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]を追加します。  

      ```  
      <add name="sqlBinding" type="Microsoft.Adapters.Sql.SqlAdapterBindingCollectionElement,Microsoft.Adapters.Sql, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  



4. machine.config ファイルを保存して閉じます。  

<a name="BKMK_PubKey"></a>   
#### <a name="determining-the-public-key-and-version"></a>公開キーとバージョンを決定します。  
公開キーとバージョンを確認するのには、次の手順を完了、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。  

1. Windows ディレクトリの通常 C:\WINDOWS\assembly に移動します。  

2. DLL を公開キーを必要し、し、選択を右クリックして**プロパティ**します。 次の表に、用の Dll の名前、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。  


   |                              [アダプター]                              |      DLL の名前       |
   |-------------------------------------------------------------------|----------------------------|
   | [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] | Microsoft.Adapters.Sql.dll |


3. **全般**タブの値を比較、**公開キー トークンの**ラベルは、DLL の公開キーを指定します。 に対して同様に、値、**バージョン**ラベルは、DLL のバージョン番号を指定します。  

4. クリックして、公開キーをコピー**キャンセル**します。  

<a name="BKMK_Modify_Adap"></a>   
## <a name="update-or-change-the-sql-adapter-installation"></a>更新または変更する SQL アダプターのインストール  
 変更するのには、次の手順を実行、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]インストールします。 あるかどうかを確認、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]変更には、セットアップ ウィザードを実行する前にインストールされている、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]インストールします。  

 変更することができます、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]次の 2 つの方法でインストールします。  

-   **対話モードで**セットアップ ウィザードを実行しています。  

-   **サイレント モードで**コマンドラインを使用しています。  

#### <a name="update-the-sql-adapter-installation-in-interactive-mode"></a>対話モードで SQL アダプターのインストールを更新します。  

1.  クリックして**開始**、順にクリックします**コントロール パネルの **します。  

2.  コントロール パネルで、ダブルクリック**プログラムと機能**します。  

3.  **プログラムと機能**ウィンドウで、 **Microsoft BizTalk Adapter for SQL Server**、 をクリックし、**変更**します。  

4.  クリックして、ようこそ画面の情報を読み取る**次**します。  

5.  **変更、修復、または削除インストール**ダイアログ ボックスで、をクリックして**修復**。  

6.  **For SQL Server の Microsoft BizTalk Adapter の修復の準備完了**ダイアログ ボックスで、をクリックして**修復**します。  

7.  必要に応じて、設定を変更します。 クリックして、CEIP のオプトインに関する **[ok]** します。  

8.  **[完了]** をクリックします。  

#### <a name="update-the-sql-adapter-installation-in-silent-mode"></a>更新プログラムをサイレント モードで SQL アダプターのインストール  

1. コマンド プロンプトを開きのルート ディレクトリに移動し、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]インストーラー。  

2. 次のコマンドを実行します。  

   > [!NOTE]
   >  変更する、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]次のコマンドでの x64 ベースのプラットフォームでサイレント モードでインストールが SqlAdapterSetup64.msi で SqlAdapterSetup.msi を置き換えます。  

   ```  
   msiexec /i SqlAdapterSetup.msi /qn /f  
   ```  

   > [!IMPORTANT]
   >  変更中に、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]サイレント モードでインストール、または ceip のオプトインの設定を変更することはできません。 環境設定は、同じまま、インストール時に指定した true または false に、CEIP_OPTIN を明示的に設定した場合でもです。  

    詳細については、`msiexec`のコマンドを入力`msiexec`キーを押して、コマンド ラインで`ENTER`を参照してくださいまたは[ https://support.microsoft.com/kb/230781](https://support.microsoft.com/kb/230781)します。   

<a name="BKMK_Remove_Adap"></a>   
## <a name="uninstall-or-remove-the-sql-adapter"></a>アンインストールするか、SQL アダプターを削除します。  
 削除するには、次の手順を実行、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]コンピューターから。 必ず、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]を削除するセットアップ ウィザードを実行する前にインストールされている、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。  

 削除することができます、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]次の 2 つの方法で。  

-   **対話モードで**セットアップ ウィザードを実行しています。  

-   **サイレント モードで**コマンドラインを使用しています。  

#### <a name="uninstall-in-interactive-mode"></a>対話モードでアンインストールします。  

1.  クリックして**開始**、順にクリックします**コントロール パネルの **します。  

2.  コントロール パネルで、ダブルクリック**プログラムと機能**します。  

3.  **プログラム追加と削除**ウィンドウで、 **Microsoft BizTalk Adapter for SQL Server**、 をクリックし、**削除**します。  

4.  ダイアログ ボックスで、次のようにクリックします。**はい**します。  

#### <a name="uninstall-in-silent-mode"></a>サイレント モードでアンインストールします。  

1. コマンド プロンプトを開きのルート ディレクトリに移動し、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]インストーラー。  

2. 次のコマンドを実行します。  

   > [!NOTE]
   >  削除する、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]サイレント モードで、次のコマンドでの x64 ベースのプラットフォームでは、SqlAdapterSetup64.msi で SqlAdapterSetup.msi を置き換えます。  

   ```  
   msiexec /x SqlAdapterSetup.msi /qn  
   ```  

    このコマンドを削除、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]コンピューターから。  

    詳細については、`msiexec`のコマンドを入力`msiexec`キーを押して、コマンド ラインで`ENTER`を参照してくださいまたは[ https://support.microsoft.com/kb/230781](https://support.microsoft.com/kb/230781)します。  

<a name="BKMK_PostRemove"></a>   
### <a name="post-uninstall-task"></a>アンインストール後のタスク  
 場合、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]の削除中に、アダプターのバインドを削除に失敗する、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]、手動で削除する必要があります。 次のセクションのバインドを手動で削除する方法を説明する、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。  

<a name="BKMK_Remove_Binding"></a>   
#### <a name="manually-remove-the-bindings"></a>バインドを手動で削除します。  
 これらの手順に従います*のみ*セットアップ ウィザードが、machine.config ファイルからアダプターのバインドを削除できない場合。  

1. コンピューターの machine.config ファイルに移動します。 たとえば、32 ビット プラットフォームで、machine.config はで使用可能な\<システム ドライブ\>: \WINDOWS\Microsoft.NET\Framework\\< バージョン\>\CONFIG します。  

   - Microsoft .NET framework 3.5 SP1 では、 \<*バージョン*\>は .NET Framework のバージョン v2.0.50727 します。  

   - Microsoft の[!INCLUDE[netfx40_short](../../includes/netfx40-short-md.md)]、 \<*バージョン*\>は .NET Framework のバージョン v4.0.30319 します。  

2. テキスト エディターを使用してファイルを開きます。  

3. アダプターのバインディング登録を削除するには。  

   1. 要素の"system.serviceModel"を検索し、次の要素の下からを削除します。  

      ```  
      <client>  
        <endpoint binding="sqlBinding" contract="IMetadataExchange" name="mssql" />  
      </client>  

      ```  

   2. "BindingElementExtensions"system.serviceModel\extensions 下の要素を検索します。  

   3. "BindingElementExtensions"ノードの下に、次のセクションを削除します。  

       [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]、削除します。  

      ```  
      <add name="sqlAdapter" type="Microsoft.Adapters.Sql.SqlAdapterBindingElementExtensionElement,Microsoft.Adapters.Sql, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

   4. "BindingExtensions"system.serviceModel\extensions 下の要素を検索します。  

   5. "BindingExtensions"ノードの下に、次のセクションを削除します。  

       [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]、削除します。  

      ```  
      <add name="sqlBinding" type="Microsoft.Adapters.Sql.SqlAdapterBindingCollectionElement,Microsoft.Adapters.Sql, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

4. machine.config ファイルを保存して閉じます。  

## <a name="see-also"></a>参照
[SQL アダプターをインストールする](../../adapters-and-accelerators/adapter-sql/install-the-sql-adapter.md)  
[BizTalk Adapter for SQL Server を理解する](../../adapters-and-accelerators/adapter-sql/understand-biztalk-adapter-for-sql-server.md)