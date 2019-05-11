---
title: BizTalk Adapter Pack 2016 のソフトウェアの前提条件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 65a063ca-37ae-420b-9d48-e6730caf17e3
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7980760c3a99363449e18f0315fdeddac0626bca
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65364010"
---
# <a name="software-prerequisites-for-biztalk-adapter-pack-2016"></a>BizTalk Adapter Pack 2016 のソフトウェアの前提条件
Microsoft のソフトウェア要件[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)](BAP) に含まれる[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]します。

[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]から使用できます。  

- .NET アプリケーション  

- Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]  

- ADO インターフェイス  

- Microsoft SharePoint portal  

  アダプターを使用する方法に基づき、必要なソフトウェアによって異なります。  

## <a name="prerequisites-when-using-a-net-application"></a>.NET アプリケーションを使用する場合の前提条件  
アダプターを使用する .NET アプリケーションを使用する場合は、開発用コンピューター (.NET アプリケーションを作成しているコンピューター) で、次のソフトウェアが必要です。 表示された順に、ソフトウェアをインストールします。


|                                                   BizTalk Adapter Pack 2016                                                    |
|--------------------------------------------------------------------------------------------------------------------------------|
|         <ul><li>Windows Server 2016</li><li>Windows Server 2012 R2</li><li>Windows 10</li><li>Windows 8.1  </li></ul>          |
|                                                     .NET Framework 4.6.*x*                                                     |
|                                                       Visual Studio 2015                                                       |
|                              [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]                              |
| エンタープライズ アプリケーションのクライアントと関連付けられているソフトウェア。 参照してください**エンタープライズ アプリケーションのバージョンがサポートされている**(」を参照)。 |

## <a name="prerequisites-when-using-biztalk-server"></a>BizTalk Server を使用する場合の前提条件  
使用する場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]でアダプターを使用するには、次のソフトウェアが必要な[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。 表示された順に、ソフトウェアをインストールします。


|                                                                                                                                                                                                                                              BizTalk Adapter Pack 2016                                                                                                                                                                                                                                               |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                                                                                                                                                                                    <ul><li>Windows Server 2016</li><li>Windows Server 2012 R2</li><li>Windows 10</li><li>Windows 8.1  </li></ul>                                                                                                                                                                                                     |
|                                                                                                                                                                                                                                                .NET Framework 4.6.*x*                                                                                                                                                                                                                                                |
|                                                                                                                                                                                                                                                  Visual Studio 2015                                                                                                                                                                                                                                                  |
| [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]<br /><br /> インストール、[!INCLUDE[consumeadapterservlong](../includes/consumeadapterservlong-md.md)]の[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]に含まれている、[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]します。 インストールするには、**カスタム**(選択**BizTalk Server アドイン**) または**完了**のインストール、[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]します。 |
|                                                                                                                                                                                                                                  [!INCLUDE[bts2016_md](../includes/bts2016-md.md)]                                                                                                                                                                                                                                   |
|                                                                                                                                                                                            エンタープライズ アプリケーションのクライアントと関連付けられているソフトウェア。 参照してください**エンタープライズ アプリケーションのバージョンがサポートされている**(」を参照)。                                                                                                                                                                                            |

## <a name="prerequisites-when-using-ado"></a>ADO を使用する場合の前提条件  
 **[!INCLUDE[adaptersap](../includes/adaptersap-md.md)]** と**[!INCLUDE[adaptersiebel](../includes/adaptersiebel-md.md)]** 、ADO レイヤーが含まれます (*[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]* と*[!INCLUDE[adoprovidersiebelshort](../includes/adoprovidersiebelshort-md.md)]*) することができますSAP システムまたは Siebel システムへの接続に、ADO.NET クライアントの書き込みに使用します。 使用することできますも ADO レイヤー SQL Server Integration Services (SSIS) でインポートしてから、LOB アプリケーション、および SQL Server Reporting Services (SSRS) レポートを生成する LOB システムからデータを表示するデータをエクスポートします。  

> [!NOTE]
>  Ssrs では、ADO プロバイダーを使用してのみサポートされています、[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]します。  

使用するコンピューターで、次のソフトウェアが必要な[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]ADO インターフェイスを使用します。 表示された順に、ソフトウェアをインストールします。  


|                                                   BizTalk Adapter Pack 2016                                                    |
|--------------------------------------------------------------------------------------------------------------------------------|
|         <ul><li>Windows Server 2016</li><li>Windows Server 2012 R2</li><li>Windows 10</li><li>Windows 8.1  </li></ul>          |
|                                                     .NET Framework 4.6.*x*                                                     |
|                                                       Visual Studio 2015                                                       |
|                              [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]                              |
|                       <ul><li>Microsoft SQL Server 2016</li><li>Microsoft SQL Server 2014 SP1</li></ul>                        |
| エンタープライズ アプリケーションのクライアントと関連付けられているソフトウェア。 参照してください**エンタープライズ アプリケーションのバージョンがサポートされている**(」を参照)。 |

## <a name="prerequisites-when-using-sharepoint"></a>SharePoint を使用する場合の前提条件  
Microsoft sharepoint アダプターを使用する目的では、SharePoint ポータルの LOB アプリケーションからデータを説明します。  

一般的なセットアップ、 [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] SharePoint で 1 台のコンピューターを使用して、または別のコンピューターを使用して、さまざまなタスクのことができます。 次の表では、各コンピューターのソフトウェアの前提条件を示します。 1 台のコンピューターを使用している場合、そのコンピューターにすべてのソフトウェアをインストールする必要があります。 表示された順に、ソフトウェアをインストールします。  


|                                                                                                                                                                                                                                             WCF アダプター サービス開発ウィザードを実行するコンピューター                                                                                                                                                                                                                                              |                                                                                                                                                                                                                                                                                                                                                  WCF サービスをホストするコンピューター                                                                                                                                                                                                                                                                                                                                                   | コンピューターの外部コンテンツ タイプを定義する、SharePoint Designer を使用できます。 |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------|
| <ul><li>Windows Server 2016</li><li>Windows Server 2012 R2</li><li>Windows 10</li><li>Windows 8.1</li><br/><br/><li>.NET Framework 4.6.<em>x</em></li><br/><br/><li>Visual Studio 2015</li><br/><br/><li>[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]</li><br/><br/><li>Microsoft [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]</li><br/><br/><li>エンタープライズ アプリケーションのクライアントと関連付けられているソフトウェア。 参照してください<strong>エンタープライズ アプリケーションのバージョンがサポートされている</strong>(」を参照)。</li></ul> | <ul><li>Windows Server 2016</li><li>Windows Server 2012 R2</li><li>Windows 10</li><li>Windows 8.1</li><br/><br/><li>.NET Framework 4.6.<em>x</em></li><br/><br/><li>Visual Studio 2015</li><br/><br/><li>[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]</li><br/><br/><li>Microsoft [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]</li><br/><br/><li>エンタープライズ アプリケーションのクライアントと関連付けられているソフトウェア。 参照してください<strong>エンタープライズ アプリケーションのバージョンがサポートされている</strong>(」を参照)。</li><br /><br /><li>オペレーティング システムに付属しているインターネット インフォメーション サービス (IIS) バージョン。 [KB 224609](https://support.microsoft.com/kb/224609)バージョンを一覧表示します。</li> </ul> |                   Microsoft SharePoint のソフトウェア開発キット (SDK)                    |

<a name="BKMK_SuppLOB"></a>   
## <a name="supported-enterprise-application-versions"></a>サポートされているエンタープライズ アプリケーションのバージョン  
BizTalk Adapter Pack でサポートされている特定の LOB システムのバージョンを表示するには、次を参照してください。 **[サポートされている基幹業務 (LOB) システム](http://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-systems.aspx)** します。

このセクションでは、各アダプターに必要なすべてのクライアントの Dll など、アダプターごとに、追加の情報が一覧表示します。  

### <a name="oracle-database-adapter"></a>Oracle Database アダプター  

-   省略可能:分散トランザクションを使用して Oracle データベースがある場合は、インストール**Microsoft Transaction Server 用の Oracle サービス**(Oracle クライアントのインストールの一部) アダプター クライアントを実行しているコンピューター。  

-   ODP.NET の最新バージョンで動作するアプリケーションのインストール、**ポリシー Dll** GAC に Dll を登録します。 参照してください[Oracle Data Provider for .NET に関する FAQ](http://www.oracle.com/technetwork/database/windows/faq-093106.html)します。  

### <a name="oracle-e-business-adapter"></a>Oracle E-Business アダプター  

-   省略可能:Oracle データベースでは、分散トランザクションを使用するには、インストール**Microsoft Transaction Server 用の Oracle サービス**(Oracle クライアントのインストールの一部) アダプター クライアントを実行しているコンピューター。  

-   ODP.NET の最新バージョンで動作するアプリケーションのインストール、**ポリシー Dll** GAC に Dll を登録します。 参照してください[Oracle Data Provider for .NET に関する FAQ](http://www.oracle.com/technetwork/database/windows/faq-093106.html)します。  

### <a name="sap-adapter"></a>SAP アダプター  

- [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)] SAP システムは、Unicode または Unicode でないかどうかに関係なく、RFC SDK の Unicode バージョンが必要です。  

- **ドライバーに必要な**:次の表に、必要な Dll、 [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] SAP システムとのインターフェイス。  


  | SAP クライアント バージョン |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  必要なドライバー                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
  |--------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
  |        7.2         | - **SAP の RFC SDK 7.10 UNICODE**します。 これは、使用可能な SNOTE の一部として<sup>* </sup> 27517 します。SDK をダウンロードする手順については、「 [ http://go.microsoft.com/fwlink/?LinkId=94691](http://go.microsoft.com/fwlink/?LinkId=94691)します。ダウンロードが、SDK を抽出して後、は、次の表の前に説明した関連する場所を \rfcsdk\bin および \rfcsdk\lib フォルダーからすべての Dll をコピーします。<br /> <br /> -Dll には SAP からの一部として\* \*R3DLLINST.zip*<em>します。 これにより、Microsoft ランタイム Dll が含まれています、SAP サイトからダウンロードできます。 SNOTE を参照してください。<sup> </em> </sup> 684106 詳細についてはします。 .Zip ファイルをダウンロードする[ http://go.microsoft.com/fwlink/?LinkId=94693](http://go.microsoft.com/fwlink/?LinkId=94693)します。 このリンクには、"Attachments"からパッケージをダウンロードするオプションがあります。<br /><br /> Microsoft Visual C SAP 7.1 クライアントに必要なランタイム Dll は、次のリンクから入手できます。<br /><br /> - **32 ビット SAP 7.1 クライアント**:Vcredist_x86.exe [ http://go.microsoft.com/fwlink/?LinkId=107086](http://go.microsoft.com/fwlink/?LinkId=107086)します。<br /><br /> -                                 **64 ビット SAP 7.1 クライアント**:Vcredist_x64.exe [ http://go.microsoft.com/fwlink/?LinkId=107087](http://go.microsoft.com/fwlink/?LinkId=107087)します。<br /><br /> -SAP システムに接続する SAP セキュリティで保護されたネットワーク通信 (SNC) を使用する場合は、SAP から関連する Dll を必要もあります。 これらの Dll が 32 ビットおよび 64 ビット プラットフォーム用に異なると SNOTE で使用可能な<sup>* </sup> 352295 します。Dll をダウンロードする[ http://go.microsoft.com/fwlink/?LinkId=104032](http://go.microsoft.com/fwlink/?LinkId=104032)します。このリンクには、"Attachments"からパッケージをダウンロードするオプションがあります。Dll の名前が:<br /><br /> - \*\*の 32 ビット*<em>: gsskrb5.dll、gssntlm.dll<br /><br /> - \*\*64 ビット x86 用</em>\*: gx64krb5.dll、gx64ntlm.dll |

   > [!TIP]
   > SNOTEs は、SAP でリリースされた修正プログラムに付随するリリース ノートです。  

  これらの Dll が含まれているパッケージのほとんどは、SAP Service Marketplace からダウンロードする必要があります。 取得するには、SAP サービス マーケットプ レースからダウンロードします。 

  1. SAP サービス マーケットプ レースから利用可能なダウンロード マネージャーをインストールします。  

  2. ダウンロード マネージャーを構成するには、SAP サービス マーケットプ レースの資格情報を使用します。  

  3. SAP サービスの web サイトからソフトウェアをダウンロードする、組織内の SAP の管理者によって承認されます。 ソフトウェアのダウンロード ' 承認オブジェクトによって、SAP ソフトウェアの配布センターへのアクセスが制限されているために必要です。 これにより、ソフトウェアのダウンロードが承認されたユーザーのみであります。  

  4. SAP サービス マーケットプ レースからダウンロードしたパッケージからファイルを抽出するために必要な最初に見つかったプログラムをインストールします。 最初に見つかったは、SAP Service Marketplace からも使用できます。  

     32 ビットおよび 64 ビット バージョンの[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]、これらのそれぞれの 32 ビットおよび 64 ビット バージョンの Dll をいる必要があります。  

  -   32 ビット コンピューターでは、Dll の 32 ビット バージョンを C:\Windows\System32 フォルダーに追加する必要があります。  

  -   64 ビット コンピューターでは、Dll の 32 ビット バージョンを C:\Windows\SysWow64 フォルダーに追加する必要があります。 Dll の 64 ビット バージョンは、C:\Windows\System32 フォルダーに追加する必要があります。  


### <a name="siebel-adapter"></a>Siebel アダプター  
追加の手順はありません。

### <a name="sql-adapter"></a>SQL アダプター  

**ドライバーに必要な**SQL Server 2014 用。  

-   SQL Server のバージョン、たとえば、geography 型に付属の Udt を使用する場合、次の Dll は SQL Server での操作を実行するアダプターを使用するコンピューター上に存在することを確認します。 たとえば、SQL Server での操作を実行する BizTalk プロジェクトを作成する場合これらの Dll は BizTalk Server が実行されているコンピューター上に存在である必要があります。  

    -   Microsoft.SqlServer.Types.dll は GAC に追加することを確認します。  

    -   SqlServerSpatial.dll が System32 フォルダーにあることを確認します。    

    コンピューターにこれらの Dll をインストールするには、SQL Server セットアップを実行し、選択**管理ツール-基本**と**管理ツール-完全**で、**機能の選択**ウィザードのページ。          

-   FILESTREAM データ型の列に対する操作を実行するアダプターを使用する場合は、SQL Client Connectivity SDK がインストールされている必要があることを確認してください。 SQL クライアント接続 SDK をインストールするには、SQL Server セットアップを実行し、選択**SQL Client Connectivity SDK**で、**機能の選択**ウィザードのページ。 アダプターは、FILESTREAM 操作を実行するのに SQL クライアント接続 sdk では、インストールされている、sqlncli10.dll を使用します。  

-   SQL Server で、独自の Udt を作成する場合は、Udt のそれぞれのアセンブリを GAC に追加して確認します。

## <a name="64-bit-host-instance-support"></a>64 ビット ホスト インスタンスのサポート

Siebel アダプターは、32 ビット ホスト インスタンスでサポートされます。 Siebel アダプターを 64 ビット ホスト インスタンスで実行することはできません。 

他のすべてのアダプターは、32 ビットまたは 64 ビット ホスト インスタンスで実行できます。 

 32 ビットおよび 64 ビットのインストール、サポートされているインストール シナリオの詳細については[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]を参照してください**32 ビットおよび 64 ビット インストール シナリオ**で[インストール BAP](../adapters-and-accelerators/installing-the-biztalk-adapter-pack-2016.md)します。  

## <a name="next-step"></a>次の手順
[BizTalk Adapter Pack をインストールします。](../adapters-and-accelerators/installing-the-biztalk-adapter-pack-2016.md)  
