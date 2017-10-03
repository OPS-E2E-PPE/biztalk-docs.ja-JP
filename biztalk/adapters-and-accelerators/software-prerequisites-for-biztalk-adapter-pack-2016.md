---
title: "BizTalk アダプター パック 2016 でのソフトウェアの前提条件 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 65a063ca-37ae-420b-9d48-e6730caf17e3
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d0b33203d1e8e5b36c9fb8a54167c111a427b244
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="software-prerequisites-for-biztalk-adapter-pack-2016"></a>BizTalk アダプター パック 2016 でのソフトウェアの前提条件
Microsoft のソフトウェア要件を一覧表示[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)](BAP) に含まれる[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]です。
  
[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]から使用されることができます。  
  
-   .NET アプリケーション  
  
-   Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]  
  
-   ADO インターフェイス  
  
-   Microsoft SharePoint ポータル  
  
 アダプターを使用する方法に基づき、必要なソフトウェアによって異なります。  
  
## <a name="prerequisites-when-using-a-net-application"></a>.NET アプリケーションを使用する場合の前提条件  
アダプターを使用する .NET アプリケーションの使用、開発用コンピューター (.NET アプリケーションを作成しているコンピューター) で、次のソフトウェアが必要です。 この順で、ソフトウェアをインストールします。
  
|BizTalk Adapter Pack 2016|
|---|
|<ul><li>Windows Server 2016</li><li>Windows Server 2012 R2</li><li>Windows 10</li><li>Windows 8.1  </li></ul>|
|.NET Framework 4.6.*x*|
|Visual Studio 2015|
|[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]|
|エンタープライズ アプリケーションのクライアントと関連付けられているソフトウェア。 参照してください**エンタープライズ アプリケーションのバージョンがサポートされている**(」を参照)。|

## <a name="prerequisites-when-using-biztalk-server"></a>BizTalk Server を使用する場合の前提条件  
使用する場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]でアダプターを使用する、次のソフトウェアが必要な[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]です。 この順で、ソフトウェアをインストールします。
 
|BizTalk Adapter Pack 2016|
|---|
|<ul><li>Windows Server 2016</li><li>Windows Server 2012 R2</li><li>Windows 10</li><li>Windows 8.1  </li></ul>|
|.NET Framework 4.6.*x*|
|Visual Studio 2015|
|[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]<br /><br /> インストール、[!INCLUDE[consumeadapterservlong](../includes/consumeadapterservlong-md.md)]の[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]に含まれている、[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]です。 インストールするには、**カスタム**(選択**BizTalk Server アドイン**) または**完了**のインストール、[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]です。|
|[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]|
|エンタープライズ アプリケーションのクライアントと関連付けられているソフトウェア。 参照してください**エンタープライズ アプリケーションのバージョンがサポートされている**(」を参照)。|

## <a name="prerequisites-when-using-ado"></a>ADO を使用する場合の前提条件  
  **[!INCLUDE[adaptersap](../includes/adaptersap-md.md)]** と **[!INCLUDE[adaptersiebel](../includes/adaptersiebel-md.md)]**  ADO レイヤーが含まれます ( *[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]* と *[!INCLUDE[adoprovidersiebelshort](../includes/adoprovidersiebelshort-md.md)]* ) することができますSAP システムまたは Siebel システムへの接続に、ADO.NET クライアントの書き込みに使用します。 行えます ADO レイヤーで SQL Server Integration Services (SSIS) のインポートし、エクスポートのデータ、LOB アプリケーション、および SQL Server Reporting Services (SSRS) レポートを生成するデータ、LOB システムの表示にします。  
  
> [!NOTE]
>  ADO プロバイダーを使用して、SSRS でのみサポートされて、[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]です。  
  
使用するコンピューターで、次のソフトウェアが必要な[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]ADO インターフェイスを使用します。 この順で、ソフトウェアをインストールします。  

|BizTalk Adapter Pack 2016|
|---|
|<ul><li>Windows Server 2016</li><li>Windows Server 2012 R2</li><li>Windows 10</li><li>Windows 8.1  </li></ul>|
|.NET Framework 4.6.*x*|
|Visual Studio 2015|
|[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]|
|<ul><li>Microsoft SQL Server 2016</li><li>Microsoft SQL Server 2014 SP1</li></ul> |
|エンタープライズ アプリケーションのクライアントと関連付けられているソフトウェア。 参照してください**エンタープライズ アプリケーションのバージョンがサポートされている**(」を参照)。|

## <a name="prerequisites-when-using-sharepoint"></a>SharePoint を使用する場合の前提条件  
Microsoft SharePoint で、アダプターの使用の目的は、SharePoint portal の LOB アプリケーションからデータを表示です。  
  
一般的なセットアップで、 [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] SharePoint は 1 台のコンピューターを使用したり、さまざまなタスクの別のコンピューターを使用するとします。 次の表は、各コンピューターのソフトウェアの前提条件を一覧表示します。 1 台のコンピューターを使用している場合、そのコンピューターにすべてのソフトウェアをインストールする必要があります。 この順で、ソフトウェアをインストールします。  
  
|WCF アダプター サービス開発ウィザードを実行するコンピューター|WCF サービスをホストするコンピューター|コンピューターの外部コンテンツ タイプを定義する SharePoint Designer を使用できます。| 
|---|---|---|  
|<ul><li>Windows Server 2016</li><li>Windows Server 2012 R2</li><li>Windows 10</li><li>Windows 8.1</li><br/><br/><li>.NET Framework 4.6.*x*</li><br/><br/><li>Visual Studio 2015</li><br/><br/><li>[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]</li><br/><br/><li>Microsoft [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]</li><br/><br/><li>エンタープライズ アプリケーションのクライアントと関連付けられているソフトウェア。 参照してください**エンタープライズ アプリケーションのバージョンがサポートされている**(」を参照)。</li></ul> | <ul><li>Windows Server 2016</li><li>Windows Server 2012 R2</li><li>Windows 10</li><li>Windows 8.1</li><br/><br/><li>.NET Framework 4.6.*x*</li><br/><br/><li>Visual Studio 2015</li><br/><br/><li>[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]</li><br/><br/><li>Microsoft [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]</li><br/><br/><li>エンタープライズ アプリケーションのクライアントと関連付けられているソフトウェア。 参照してください**エンタープライズ アプリケーションのバージョンがサポートされている**(」を参照)。</li><br /><br /><li>オペレーティング システムに付属しているインターネット インフォメーション サービス (IIS) バージョン。 [KB 224609](https://support.microsoft.com/kb/224609)バージョンを一覧表示します。</li> </ul>| Microsoft SharePoint のソフトウェア開発キット (SDK)|
  
<a name="BKMK_SuppLOB"></a>   
## <a name="supported-enterprise-application-versions"></a>サポートされているエンタープライズ アプリケーションのバージョン  
BizTalk Adapter Pack でサポートされている特定の LOB システムのバージョンを表示するには、次を参照してください。 **[サポートされている行の基幹業務 (LOB) システム](http://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-systems.aspx)**です。

ここでは、各アダプターに必要なすべてのクライアント Dll など、各アダプターの追加情報を示します。  
  
### <a name="oracle-database-adapter"></a>Oracle Database アダプター  
  
-   省略可能: 分散トランザクションを使用して Oracle データベースがある場合はインストール**Oracle Services for Microsoft Transaction Server** (Oracle クライアントのインストールの一部) アダプターのクライアントを実行している、コンピューター。  
  
-   ODP.NET の最新バージョンで動作するアプリケーションをインストール、**ポリシー Dll**および GAC の Dll を登録します。 参照してください[.NET に関する FAQ の Oracle データ プロバイダー](http://www.oracle.com/technetwork/database/windows/faq-093106.html)です。  

### <a name="oracle-e-business-adapter"></a>Oracle E-Business アダプター  
  
-   省略可能: Oracle データベースに分散トランザクションを使用するインストール**Oracle Services for Microsoft Transaction Server** (Oracle クライアントのインストールの一部) アダプターのクライアントを実行している、コンピューター。  
  
-   ODP.NET の最新バージョンで動作するアプリケーションをインストール、**ポリシー Dll**および GAC の Dll を登録します。 参照してください[.NET に関する FAQ の Oracle データ プロバイダー](http://www.oracle.com/technetwork/database/windows/faq-093106.html)です。  
  
### <a name="sap-adapter"></a>SAP アダプター  
  
-   [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)] SAP システムは、Unicode または unicode 対応でないかどうかに関係なく、RFC SDK の Unicode バージョンが必要です。  
  
-   **ドライバーに必要な**: 次の表に、必要な Dll、 [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] SAP システムとやり取りします。  
  
    |SAP クライアント バージョン|必要なドライバー|  
    |---|---|  
    |7.2|- **SAP RFC SDK 7.10 UNICODE**です。 これは、使用可能な SNOTE の一部として<sup>* </sup> 27517 です。SDK をダウンロードする手順は[http://go.microsoft.com/fwlink/?LinkId=94691](http://go.microsoft.com/fwlink/?LinkId=94691)です。ダウンロードして、SDK を展開したら、\rfcsdk\bin および \rfcsdk\lib フォルダーから、関連する場所に記載されている次の表の前のすべての Dll をコピーします。<br /> <br /> -Dll には SAP からの一部として**R3DLLINST.zip**です。これは、は、Microsoft ランタイム Dll を含んでおり、SAP サイトからダウンロードできます。SNOTE を参照してください<sup>* </sup> 684106 詳細についてはします。 .Zip ファイルをダウンロードする[http://go.microsoft.com/fwlink/?LinkId=94693](http://go.microsoft.com/fwlink/?LinkId=94693)です。 このリンクには、"Attachments"からパッケージをダウンロードするオプションがあります。<br /><br /> Microsoft Visual C ランタイム Dll SAP 7.1 クライアントに必要なには、次のリンクからです。<br /><br /> - **32 ビット SAP 7.1 クライアントを**: から Vcredist_x86.exe [http://go.microsoft.com/fwlink/?LinkId=107086](http://go.microsoft.com/fwlink/?LinkId=107086)です。<br /><br /> -                                 **64 ビット SAP 7.1 クライアントを**: から Vcredist_x64.exe [http://go.microsoft.com/fwlink/?LinkId=107087](http://go.microsoft.com/fwlink/?LinkId=107087)です。<br /><br /> -SAP システムへの接続に SAP セキュリティで保護されたネットワーク通信 (SNC) を使用する場合は、SAP から関連する Dll を必要もあります。 これらの Dll は、32 ビットおよび 64 ビット プラットフォーム用に異なる、SNOTE で利用可能な<sup>* </sup> 352295 です。 Dll をダウンロードする[http://go.microsoft.com/fwlink/?LinkId=104032](http://go.microsoft.com/fwlink/?LinkId=104032)です。 このリンクには、"Attachments"からパッケージをダウンロードするオプションがあります。 Dll の名前は次のとおりです。<br /><br /> - **32 ビット**: gsskrb5.dll、gssntlm.dll<br /><br /> - **64 ビット x86 用**: gx64krb5.dll、gx64ntlm.dll|  
  
     > [!TIP]
     > SNOTEs は、SAP でリリースされた修正プログラムに付属のリリース ノートです。  

    これらの Dll を含むパッケージのほとんどは、SAP サービス Marketplace からダウンロードする必要があります。 SAP サービス Marketplace からダウンロードを取得します。 
  
    1.  SAP サービス Marketplace から、ダウンロード マネージャーをインストールします。  
  
    2.  SAP サービス Marketplace 用の資格情報を使用して、ダウンロード マネージャーを構成します。  
  
    3.  SAP のサービスの web サイトからソフトウェアをダウンロードする、組織内の SAP 管理者によって承認されます。 これは、機能は、' ソフトウェアのダウンロード ' 認証オブジェクトを SAP Software Distribution Center へのアクセスが制限されているため必要です。 これにより、ソフトウェアのダウンロードが承認されたユーザーのみであります。  
  
    4.  SAP サービス Marketplace からダウンロードしたパッケージからファイルを抽出するために必要な最初に見つかったプログラムをインストールします。 最初に見つかったは SAP サービス マーケットプ レースからも使用できます。  
  
     32 ビットおよび 64 ビット バージョンの[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]、これらの各 32 ビットおよび 64 ビット バージョンは Dll である必要があります。  
  
    -   32 ビット コンピューターで C:\Windows\System32 フォルダーに、Dll の 32 ビット バージョンを追加する必要があります。  
  
    -   64 ビット コンピューターで 32 ビット バージョンの Dll の C:\Windows\SysWow64 フォルダーに追加する必要があります。 Dll の 64 ビット バージョンは、C:\Windows\System32 フォルダーに追加する必要があります。  
    
    
### <a name="siebel-adapter"></a>Siebel アダプター  
余分な手順はありません。
  
### <a name="sql-adapter"></a>SQL アダプター  
  
**必要なドライバー** SQL Server 2014 用。  
  
-   SQL Server のバージョン、たとえば、Geography に付属して Udt を使用する場合は、次の Dll は、SQL Server 上の操作を実行するアダプターを使用するコンピューター上に存在を確認します。 など、SQL Server 上の操作を実行する BizTalk プロジェクトを作成する場合は、これらの Dll が BizTalk Server が実行されているコンピューター上に存在する必要があります。  
  
    -   Microsoft.SqlServer.Types.dll は GAC に追加することを確認します。  
  
    -   SqlServerSpatial.dll が System32 フォルダーにあることを確認してください。    
        
    SQL Server セットアップを実行しを選択すると、コンピューターにこれらの Dll をインストールできます**管理ツール-基本**と**管理ツール-完全**で、**機能の選択**ウィザードのページです。          
  
-   FILESTREAM データ型の列に対して操作を実行するアダプターを使用する場合は、SQL クライアント接続 SDK がインストールされている必要があることを確認してください。 SQL Server セットアップを実行しを選択すると、SQL クライアント接続 SDK をインストールすることができます**SQL クライアント接続 SDK**で、**機能の選択**ウィザードのページです。 アダプターは、FILESTREAM 操作を実行するのに、SQL クライアント接続 SDK と共にインストールされる、sqlncli10.dll を使用します。  

-   SQL Server で、独自の Udt を作成する場合は、Udt のそれぞれのアセンブリが GAC に追加を確認します。

## <a name="64-bit-host-instance-support"></a>64 ビット ホスト インスタンスのサポート

Siebel アダプターは、32 ビット ホスト インスタンスでサポートされています。 Siebel アダプターを 64 ビット ホスト インスタンスで実行することはできません。 

他のすべてのアダプターは、32 ビットまたは 64 ビット ホスト インスタンスで実行できます。 
  
 32 ビットおよび 64 ビットのインストールのサポートされているインストール シナリオの詳細については[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]を参照してください**32 ビットおよび 64 ビット インストール シナリオ**で[インストール BAP](../adapters-and-accelerators/installing-the-biztalk-adapter-pack-2016.md)です。  
 
## <a name="next-step"></a>次の手順
[BizTalk Adapter Pack をインストールします。](../adapters-and-accelerators/installing-the-biztalk-adapter-pack-2016.md)  
