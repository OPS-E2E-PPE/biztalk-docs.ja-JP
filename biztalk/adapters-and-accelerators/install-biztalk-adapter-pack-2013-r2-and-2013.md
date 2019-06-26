---
title: BizTalk Adapter Pack 2013 R2 および 2013 のインストール |Microsoft Docs
description: 前提条件と BAP 2013 R2 および BizTalk Server に含まれている BAP 2013 をインストールする手順
ms.custom: ''
ms.date: 2015-12-09
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9980953a-8d38-476f-af38-4f4214ba61f2
caps.latest.revision: 107
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2f7cb4d3e7f2f5cdf1cd48df8cf0927e888e81c6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65364057"
---
# <a name="install-biztalk-adapter-pack-2013-r2-and-2013"></a>BizTalk Adapter Pack 2013 R2 および 2013 をインストールします。
このドキュメントは、Microsoft をインストールするには、ソフトウェアの要件と手順を示します[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)](BAP) は、BizTalk Server 2013 に含まれているまたは[!INCLUDE[bts2013r2](../includes/bts2013r2-md.md)]します。  

## <a name="change-log"></a>変更ログ  

|date|[変更]|  
|---|---|  
|2016 年 3 月|**インストール後に.** 、新しい Oracle.DataAccess.dll バージョンを使用する Oracle データベース アダプターを構成する手順を追加します。|  

<a name="BKMK_Prereqs"></a>   
## <a name="software-prerequisites"></a>ソフトウェアの前提条件  
 [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]から使用できます。  

- .NET アプリケーション  

- Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]  

- ADO インターフェイス  

- Microsoft SharePoint portal  

  アダプターを使用する方法に基づき、必要なソフトウェアによって異なります。  

### <a name="prerequisites-when-using-a-net-application"></a>.NET アプリケーションを使用する場合の前提条件  
アダプターを使用する .NET アプリケーションを使用する場合は、開発用コンピューター (.NET アプリケーションを作成しているコンピューター) で、次のソフトウェアが必要です。 表示された順に、ソフトウェアをインストールします。


|                                                             BizTalk Adapter Pack 2013 R2                                                              |                                                               BizTalk Adapter Pack 2013                                                                |
|-------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------|
| [!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)] R2 では、 [!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]、Windows 8.1、Windows 7 SP1 | [!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]、 [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] SP1、Windows 8、Windows 7 SP1 |
|                                                  [!INCLUDE[dotnet451](../includes/dotnet451-md.md)]                                                   |                                               Microsoft [!INCLUDE[dotnet45](../includes/dotnet45-md.md)]                                               |
|                                                                  Visual Studio 2013                                                                   |                                                                   Visual Studio 2012                                                                   |
|                                         [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]                                          |                                          [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]                                          |
|              エンタープライズ アプリケーションのクライアントと関連付けられているソフトウェア。 参照してください[エンタープライズ アプリケーションのバージョンがサポートされている](#BKMK_SuppLOB)します。              |              エンタープライズ アプリケーションのクライアントと関連付けられているソフトウェア。 参照してください[エンタープライズ アプリケーションのバージョンがサポートされている](#BKMK_SuppLOB)します。               |

### <a name="prerequisites-when-using-a-biztalk-server"></a>BizTalk Server を使用する場合の前提条件  
BizTalk Server を使用して、アダプターを使用する、BizTalk Server で、次のソフトウェアが必要です。 表示された順に、ソフトウェアをインストールします。


|                                                                                                                                                                                                                                             BizTalk Adapter Pack 2013 R2                                                                                                                                                                                                                                             |                                                                                                                                                                                                                                              BizTalk Adapter Pack 2013                                                                                                                                                                                                                                               |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                                                                                                                                                                [!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)] R2 では、 [!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]、Windows 8.1、Windows 7 SP1                                                                                                                                                                                 |                                                                                                                                                                                [!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]、 [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] SP1、Windows 8、Windows 7 SP1                                                                                                                                                                                |
|                                                                                                                                                                                                                                  [!INCLUDE[dotnet451](../includes/dotnet451-md.md)]                                                                                                                                                                                                                                  |                                                                                                                                                                                                                              Microsoft [!INCLUDE[dotnet45](../includes/dotnet45-md.md)]                                                                                                                                                                                                                              |
|                                                                                                                                                                                                                                                  Visual Studio 2013                                                                                                                                                                                                                                                  |                                                                                                                                                                                                                                                  Visual Studio 2012                                                                                                                                                                                                                                                  |
| [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]<br /><br /> インストール、[!INCLUDE[consumeadapterservlong](../includes/consumeadapterservlong-md.md)]の[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]に含まれている、[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]します。 インストールするには、**カスタム**(選択**BizTalk Server アドイン**) または**完了**のインストール、[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]します。 | [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]<br /><br /> インストール、[!INCLUDE[consumeadapterservlong](../includes/consumeadapterservlong-md.md)]の[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]に含まれている、[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]します。 インストールするには、**カスタム**(選択**BizTalk Server アドイン**) または**完了**のインストール、[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]します。 |
|                                                                                                                                                                                                                                                BizTalk Server 2013 R2                                                                                                                                                                                                                                                |                                                                                                                                                                                                                                                 BizTalk Server 2013                                                                                                                                                                                                                                                  |
|                                                                                                                                                                                             エンタープライズ アプリケーションのクライアントと関連付けられているソフトウェア。 参照してください[エンタープライズ アプリケーションのバージョンがサポートされている](#BKMK_SuppLOB)します。                                                                                                                                                                                              |                                                                                                                                                                                             エンタープライズ アプリケーションのクライアントと関連付けられているソフトウェア。 参照してください[エンタープライズ アプリケーションのバージョンがサポートされている](#BKMK_SuppLOB)します。                                                                                                                                                                                              |

### <a name="prerequisites-when-using-ado"></a>ADO を使用する場合の前提条件  
 **[!INCLUDE[adaptersap](../includes/adaptersap-md.md)]** と **[!INCLUDE[adaptersiebel](../includes/adaptersiebel-md.md)]** 、ADO レイヤーが含まれます ( *[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]* と *[!INCLUDE[adoprovidersiebelshort](../includes/adoprovidersiebelshort-md.md)]* )。 この ADO レイヤーは、SAP システムまたは Siebel システムへの接続に、ADO.NET クライアントを記述するができます。 使用することできますも ADO レイヤー SQL Server Integration Services (SSIS) でインポートしてから、LOB アプリケーション、および SQL Server Reporting Services (SSRS) レポートを生成する LOB システムからデータを表示するデータをエクスポートします。  

> [!NOTE]
>  Ssrs では、ADO プロバイダーを使用してのみサポートされています、  *[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]* します。  

使用するコンピューターで、次のソフトウェアが必要な[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]ADO インターフェイスを使用します。 表示された順に、ソフトウェアをインストールします。


|                                                             BizTalk Adapter Pack 2013 R2                                                              |                                                               BizTalk Adapter Pack 2013                                                                |
|-------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------|
| [!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)] R2 では、 [!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]、Windows 8.1、Windows 7 SP1 | [!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]、 [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] SP1、Windows 8、Windows 7 SP1 |
|                                                  [!INCLUDE[dotnet451](../includes/dotnet451-md.md)]                                                   |                                               Microsoft [!INCLUDE[dotnet45](../includes/dotnet45-md.md)]                                               |
|                                                                  Visual Studio 2013                                                                   |                                                                   Visual Studio 2012                                                                   |
|                                         [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]                                          |                                          [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]                                          |
|                [!INCLUDE[sqlserver2014](../includes/sqlserver2014-md.md)], [!INCLUDE[sqlserver2012](../includes/sqlserver2012-md.md)]                 |            [!INCLUDE[sqlserver2012](../includes/sqlserver2012-md.md)], [!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)]            |
|              エンタープライズ アプリケーションのクライアントと関連付けられているソフトウェア。 参照してください[エンタープライズ アプリケーションのバージョンがサポートされている](#BKMK_SuppLOB)します。              |              エンタープライズ アプリケーションのクライアントと関連付けられているソフトウェア。 参照してください[エンタープライズ アプリケーションのバージョンがサポートされている](#BKMK_SuppLOB)します。               |

### <a name="prerequisites-when-using-microsoft-sharepoint"></a>Microsoft SharePoint を使用する場合の前提条件  
 Microsoft sharepoint アダプターを使用する目的では、SharePoint ポータルの LOB アプリケーションからデータを説明します。  

使用する一般的なセットアップ、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]および SharePoint は、1 台のコンピューターであるか、別のコンピューターを使用して、さまざまなタスク。 次の表では、各コンピューターのソフトウェアの前提条件を示します。 1 台のコンピューターを使用している場合は、そのコンピューターのすべてのソフトウェアが必要です。 表示された順に、ソフトウェアをインストールします。  


|                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             WCF アダプター サービス開発ウィザードを実行するコンピューター                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      WCF サービスをホストするコンピューター                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       | コンピューターの外部コンテンツ タイプを定義する、SharePoint Designer を使用できます。 |                                    LOB アプリケーションから情報を表示する SharePoint を使用するコンピューター                                     |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **BAP 2013 R2**:<ul><li>[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)] R2<br/>[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]<br/>Windows 8.1<br/>Windows 7 SP1</li><li>[!INCLUDE[dotnet451](../includes/dotnet451-md.md)]</li><li> Visual Studio 2013</li><li>[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]</li><li>Microsoft [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]</li><li>それぞれのエンタープライズ アプリケーションのクライアントと関連付けられているソフトウェア。 参照してください[エンタープライズ アプリケーションのバージョンがサポートされている](#BKMK_SuppLOB)します。</li></ul> **BAP 2013**:<ul><li>[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]<br/>[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] SP1<br/>Windows 8<br/>Windows 7 SP1</li><li>Microsoft [!INCLUDE[dotnet45](../includes/dotnet45-md.md)]</li><li>Visual Studio 2012</li><li>[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]</li><li>Microsoft [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]</li><li>それぞれのエンタープライズ アプリケーションのクライアントと関連付けられているソフトウェア。 参照してください[エンタープライズ アプリケーションのバージョンがサポートされている](#BKMK_SuppLOB)します。</li></ul> | **BAP 2013 R2**:<ul><li>[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)] R2<br/>[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]<br/>Windows 8.1<br/>Windows 7 SP1</li><li>[!INCLUDE[dotnet451](../includes/dotnet451-md.md)]</li><li>[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]</li><li>Microsoft [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]</li><li>それぞれのエンタープライズ アプリケーションのクライアントと関連付けられているソフトウェア。 参照してください[エンタープライズ アプリケーションのバージョンがサポートされている](#BKMK_SuppLOB)します。</li><li>オペレーティング システムに付属しているインターネット インフォメーション サービス (IIS) バージョン。 KB 224609 バージョンを一覧表示します。</li></ul>**BAP 2013**:<ul><li>[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]<br/>[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] SP1<br/>Windows 8<br/>Windows 7 SP1</li><li>Microsoft [!INCLUDE[dotnet45](../includes/dotnet45-md.md)]</li><li>[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]</li><li>Microsoft [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]</li><li>それぞれのエンタープライズ アプリケーションのクライアントと関連付けられているソフトウェア。 参照してください[エンタープライズ アプリケーションのバージョンがサポートされている](#BKMK_SuppLOB)します。</li><li>オペレーティング システムに付属しているインターネット インフォメーション サービス (IIS) バージョン。 KB 224609 バージョンを一覧表示します。</li></ul> |            Microsoft Office SharePoint Server ソフトウェア開発キット (SDK)             | Microsoft Office サーバー インフラストラクチャの更新。 ダウンロード[ http://go.microsoft.com/fwlink/?LinkId=128344](http://go.microsoft.com/fwlink/?LinkId=128344)します。 |

<a name="BKMK_SuppLOB"></a>   
## <a name="supported-enterprise-application-versions"></a>サポートされているエンタープライズ アプリケーションのバージョン  

サポートされている特定の LOB システムのバージョンを表示する、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]を参照してください **[サポートされている基幹業務 (LOB) システム](http://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-systems.aspx)** します。 

このセクションでは、各アダプターに必要なすべてのクライアントの Dll など、アダプターごとに、追加の情報が一覧表示します。  

### <a name="oracle-database-adapter"></a>Oracle Database アダプター  

-   省略可能:分散トランザクションを使用して Oracle データベースがある場合は、インストール**Microsoft Transaction Server 用の Oracle サービス**(Oracle クライアントのインストールの一部) アダプター クライアントを実行しているコンピューター。  

-   ODP.NET の最新バージョンで動作するアプリケーションのインストール、**ポリシー Dll** GAC に Dll を登録します。 参照してください[Oracle Data Provider for .NET に関する FAQ](http://www.oracle.com/technetwork/database/windows/faq-093106.html)します。  

### <a name="oracle-e-business-adapter"></a>Oracle E-Business アダプター  

-   省略可能:Oracle データベースでは、分散トランザクションを使用するには、インストール**Microsoft Transaction Server 用の Oracle サービス**(Oracle クライアントのインストールの一部) アダプター クライアントを実行しているコンピューター。  

-   ODP.NET の最新バージョンで動作するアプリケーションのインストール、**ポリシー Dll** GAC に Dll を登録します。 参照してください[Oracle Data Provider for .NET に関する FAQ](http://www.oracle.com/technetwork/database/windows/faq-093106.html)します。  

### <a name="sap-adapter"></a>SAP アダプター  

- [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)] SAP システムは、Unicode または Unicode でないかどうかに関係なく、RFC SDK の Unicode バージョンが必要です。  

- **ドライバーに必要な**:次の表に、必要な Dll、 [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] SAP システムとのインターフェイス。 これらの Dll が含まれているパッケージのほとんどは、SAP Service Marketplace からダウンロードする必要があります。 取得するには、SAP サービス マーケットプ レースからダウンロードします。 

  1. SAP サービス マーケットプ レースから利用可能なダウンロード マネージャーをインストールします。  

  2. ダウンロード マネージャーを構成するには、SAP サービス マーケットプ レースの資格情報を使用します。  

  3. SAP サービスの web サイトからソフトウェアをダウンロードする、組織内の SAP の管理者によって承認されます。 ソフトウェアのダウンロード ' 承認オブジェクトによって、SAP ソフトウェアの配布センターへのアクセスが制限されているために必要です。 これにより、ソフトウェアのダウンロードが承認されたユーザーのみであります。  

  4. SAP サービス マーケットプ レースからダウンロードしたパッケージからファイルを抽出するために必要な最初に見つかったプログラムをインストールします。 最初に見つかったは、SAP Service Marketplace からも使用できます。  

     32 ビットおよび 64 ビット バージョンの[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]、これらのそれぞれの 32 ビットおよび 64 ビット バージョンの Dll をいる必要があります。  

  -   32 ビット コンピューターでは、Dll の 32 ビット バージョンを C:\Windows\System32 フォルダーに追加する必要があります。  

  -   64 ビット コンピューターでは、Dll の 32 ビット バージョンを C:\Windows\SysWow64 フォルダーに追加する必要があります。 Dll の 64 ビット バージョンは、C:\Windows\System32 フォルダーに追加する必要があります。  

  | SAP クライアント バージョン |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  必要なドライバー                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
  |--------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
  |        6.4         |                                                                                                                                                                                                                       **BizTalk Adapter Pack 2013 のみ**<br /><br /> - **SAP の RFC SDK 6.40 UNICODE**します。 これは、使用可能な SNOTE の一部として<sup>* </sup> 27517 します。SDK をダウンロードする手順については、「 [ http://go.microsoft.com/fwlink/?LinkId=94691](http://go.microsoft.com/fwlink/?LinkId=94691)します。ダウンロードが、SDK を抽出して後、は、次の表の前に説明した関連する場所を \rfcsdk\bin および \rfcsdk\lib フォルダーからすべての Dll をコピーします。<br /> <br /> -Dll には SAP からの一部として\* \* R3DLLINST.zip*<em> します。 これにより、Microsoft ランタイム Dll が含まれています、SAP サイトからダウンロードできます。 SNOTE を参照してください。<sup> </em> </sup> 684106 詳細についてはします。 .Zip ファイルをダウンロードする[ http://go.microsoft.com/fwlink/?LinkId=94693](http://go.microsoft.com/fwlink/?LinkId=94693)します。 このリンクには、"Attachments"からパッケージをダウンロードするオプションがあります。<br /><br /> -SAP システムに接続する SAP セキュリティで保護されたネットワーク通信 (SNC) を使用する場合は、SAP から関連する Dll を必要もあります。 これらの Dll が 32 ビットおよび 64 ビット プラットフォーム用に異なると SNOTE で使用可能な<sup>* </sup> 352295 します。Dll をダウンロードする[ http://go.microsoft.com/fwlink/?LinkId=104032](http://go.microsoft.com/fwlink/?LinkId=104032)します。このリンクには、"Attachments"からパッケージをダウンロードするオプションがあります。Dll の名前が:<br /><br /> - \*\* の 32 ビット*<em>: gsskrb5.dll、gssntlm.dll<br /><br /> -  \*\*64 ビット x86 用</em>\*: gx64krb5.dll、gx64ntlm.dll                                                                                                                                                                                                                       |
  |        7.0         |                                                                                                                                                                                                                                             - **SAP の RFC SDK 7.00 UNICODE**します。 これは、使用可能な SNOTE の一部として<sup>* </sup> 27517 します。SDK をダウンロードする手順については、「 [ http://go.microsoft.com/fwlink/?LinkId=94691](http://go.microsoft.com/fwlink/?LinkId=94691)します。ダウンロードした SDK を抽出後 \rfcsdk\bin および \rfcsdk\lib フォルダーから、次の表の前に説明した関連する場所をすべての Dll をコピーします。<br /> <br /> -Dll には SAP からの一部として\* \* R3DLLINST.zip*<em> します。 これにより、Microsoft ランタイム Dll が含まれています、SAP サイトからダウンロードできます。 SNOTE を参照してください。<sup> </em> </sup> 684106 詳細についてはします。 .Zip ファイルをダウンロードする[ http://go.microsoft.com/fwlink/?LinkId=94693](http://go.microsoft.com/fwlink/?LinkId=94693)します。 このリンクには、"Attachments"からパッケージをダウンロードするオプションがあります。<br /><br /> -SAP システムに接続する SAP セキュリティで保護されたネットワーク通信 (SNC) を使用する場合は、SAP から関連する Dll を必要もあります。 これらの Dll が 32 ビットおよび 64 ビット プラットフォーム用に異なると SNOTE で使用可能な<sup>* </sup> 352295 します。Dll をダウンロードする[ http://go.microsoft.com/fwlink/?LinkId=104032](http://go.microsoft.com/fwlink/?LinkId=104032)します。このリンクには、"Attachments"からパッケージをダウンロードするオプションがあります。Dll の名前が:<br /><br /> - \*\* の 32 ビット*<em>: gsskrb5.dll、gssntlm.dll<br /><br /> - \*\*64 ビット x86 用</em>\*: gx64krb5.dll、gx64ntlm.dll                                                                                                                                                                                                                                             |
  |        7.1         | - **SAP の RFC SDK 7.10 UNICODE**します。 これは、使用可能な SNOTE の一部として<sup>* </sup> 27517 します。SDK をダウンロードする手順については、「 [ http://go.microsoft.com/fwlink/?LinkId=94691](http://go.microsoft.com/fwlink/?LinkId=94691)します。ダウンロードが、SDK を抽出して後、は、次の表の前に説明した関連する場所を \rfcsdk\bin および \rfcsdk\lib フォルダーからすべての Dll をコピーします。<br /> <br /> -Dll には SAP からの一部として\* \* R3DLLINST.zip*<em> します。 これにより、Microsoft ランタイム Dll が含まれています、SAP サイトからダウンロードできます。 SNOTE を参照してください。<sup> </em> </sup> 684106 詳細についてはします。 .Zip ファイルをダウンロードする[ http://go.microsoft.com/fwlink/?LinkId=94693](http://go.microsoft.com/fwlink/?LinkId=94693)します。 このリンクには、"Attachments"からパッケージをダウンロードするオプションがあります。<br /><br /> Microsoft Visual C SAP 7.1 クライアントに必要なランタイム Dll は、次のリンクから入手できます。<br /><br /> - **32 ビット SAP 7.1 クライアント**:Vcredist_x86.exe [ http://go.microsoft.com/fwlink/?LinkId=107086](http://go.microsoft.com/fwlink/?LinkId=107086)します。<br /><br /> -                                 **64 ビット SAP 7.1 クライアント**:Vcredist_x64.exe [ http://go.microsoft.com/fwlink/?LinkId=107087](http://go.microsoft.com/fwlink/?LinkId=107087)します。<br /><br /> -SAP システムに接続する SAP セキュリティで保護されたネットワーク通信 (SNC) を使用する場合は、SAP から関連する Dll を必要もあります。 これらの Dll が 32 ビットおよび 64 ビット プラットフォーム用に異なると SNOTE で使用可能な<sup>* </sup> 352295 します。Dll をダウンロードする[ http://go.microsoft.com/fwlink/?LinkId=104032](http://go.microsoft.com/fwlink/?LinkId=104032)します。このリンクには、"Attachments"からパッケージをダウンロードするオプションがあります。Dll の名前が:<br /><br /> - \*\* の 32 ビット*<em>: gsskrb5.dll、gssntlm.dll<br /><br /> - \*\*64 ビット x86 用</em>\*: gx64krb5.dll、gx64ntlm.dll |

   * SNOTEs は、SAP でリリースされた修正プログラムに付随するリリース ノートです。  

### <a name="siebel-adapter"></a>Siebel アダプター  
追加の手順はありません。

### <a name="sql-adapter"></a>SQL アダプター  

**ドライバーに必要な**:  

-   **SQL Server 2005 の**:SQL Server でユーザー定義型 (Udt) を作成する場合は、Udt のそれぞれのアセンブリを GAC に追加して確認します。  

-   **SQL Server 2014、SQL Server 2012、SQL Server 2008 R2、SQL Server 2008 SP1 の**:  

    -   SQL Server のバージョン、たとえば、geography 型に付属の Udt を使用する場合、次の Dll は SQL Server での操作を実行するアダプターを使用するコンピューター上に存在することを確認します。 たとえば、SQL Server での操作を実行する BizTalk プロジェクトを作成する場合これらの Dll は BizTalk Server が実行されているコンピューター上に存在である必要があります。  

        -   Microsoft.SqlServer.Types.dll は GAC に追加することを確認します。  

        -   SqlServerSpatial.dll が System32 フォルダーにあることを確認します。    

        コンピューターにこれらの Dll をインストールするには、SQL Server セットアップを実行し、選択**管理ツール-基本**と**管理ツール-完全**で、**機能の選択**ウィザードのページ。          

    -   FILESTREAM データ型の列に対する操作を実行するアダプターを使用する場合は、SQL Client Connectivity SDK がインストールされている必要があることを確認してください。 SQL クライアント接続 SDK をインストールするには、SQL Server セットアップを実行し、選択**SQL Client Connectivity SDK**で、**機能の選択**ウィザードのページ。 アダプターは、FILESTREAM 操作を実行するのに SQL クライアント接続 sdk では、インストールされている、sqlncli10.dll を使用します。  

    -   SQL Server で、独自の Udt を作成する場合は、Udt のそれぞれのアセンブリを GAC に追加して確認します。

## <a name="64-bit-support"></a>64 ビットのサポート

Siebel アダプターは、32 ビット ホスト インスタンスでサポートされます。 Siebel アダプターを 64 ビット ホスト インスタンスで実行することはできません。 

他のすべてのアダプターは、32 ビットまたは 64 ビット ホスト インスタンスで実行できます。 



 32 ビットおよび 64 ビットのインストール、サポートされているインストール シナリオの詳細については[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]を参照してください[32 ビットおよび 64 ビット プラットフォーム上で BizTalk Adapter Pack のインストール シナリオ](#BKMK_Install_Scenarios)します。  

<a name="BKMK_Install_Adap"></a>   
## <a name="installing-the-biztalk-adapter-pack"></a>BizTalk Adapter Pack をインストールします。  
 すべてのことを確認、[ソフトウェアの前提条件](#BKMK_Prereqs)がインストールする前にインストールされている、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]します。 インストールすることができます、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]次の 2 つの方法で。  

- **対話モードで**:セットアップ ウィザードを実行します。  

- **サイレント モードで**:コマンドラインを使用してください。  

  > [!IMPORTANT]
  >  インストールするコンピューターで管理者特権が必要、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]ウィザードまたはコマンドラインを使用してをインストールするかどうかに関係なく、します。  

### <a name="typical-vs-custom-installation"></a>一般的な vs カスタム インストール  
このセクションでは、インストールの種類と各オプションでインストールされている機能を示します。  

- **標準**と**完了**オプションは、関連付けられているデータ プロバイダーを使用したすべてのアダプターをインストールします。 特定のアダプターを選択するをインストールするオプションはありません。  

- **カスタム**オプションは、関連付けられているデータ プロバイダーを使用した 1 つまたは複数のアダプターをインストールします。 インストールするアダプターを選択できます。 データ プロバイダーをインストールする場合は、対応するアダプターをインストールする必要もあります。 ただし、対応するデータ プロバイダーをインストールしなくても、アダプターをインストールすることができます。 これには、展開、 **ADO プロバイダー**ノードを展開し、インストールしないプロバイダーを選択します。 参照してください[BizTalk アダプターのインストール、対話モードでパック](#BKMK_Install_wizard)します。  

   たとえばをインストールする場合、[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]もインストールする必要があります、[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]します。 ただし、インストールすることができます、[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]インストールしなくても、[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]します。  

<a name="BKMK_Install_Scenarios"></a>   
### <a name="scenarios-for-installing-the-biztalk-adapter-pack-on-32-bit-and-64-bit-platforms"></a>32 ビットおよび 64 ビット プラットフォーム上で BizTalk Adapter Pack をインストールするためのシナリオ  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]に使用できます。 

- [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] デザイン時 (場合、LOB アプリケーションでの操作のメタデータの生成)

- BizTalk Server 管理コンソールのデザイン時 (を物理ポートを作成)

  > [!NOTE]
  >  BizTalk Server 管理コンソールは、32 ビットの Microsoft 管理コンソール (MMC) アプリケーションとして実行されます。  

- BizTalk の実行時間 (LOB アプリケーションからメッセージを送受信) するときに

1 台のコンピューターを使用して、これらすべての検索のまたは異なるコンピューターを使用できます。 両方[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]BizTalk MMC は 32 ビット プロセスとは、32 ビットをインストールする必要があります[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]デザイン時の作業を実行するコンピューター。 

#### <a name="scenarios-for-installing-the-biztalk-adapter-pack-on-a-32-bit-platform"></a>32 ビット プラットフォームで、BizTalk Adapter Pack をインストールするためのシナリオ  
 32 ビット プラットフォームでサポートされるシナリオは次のとおりです。  


|                                                                                                                 Visual Studio のデザイン時の                                                                                                                  |                                                                                                                  BizTalk MMC のデザイン時                                                                                                                   |                                                                                                                      Biztalk ランタイム                                                                                                                      |                                                                                        Visual Studio のデザイン時またはデザイン時の BizTalk MMC + BizTalk 実行時間                                                                                         |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| -32 ビットのインストール[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]します。<br /><br /> -32 ビットのインストール[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]します。<br /><br /> 32 ビット LOB クライアントとその他の必要な Dll をインストールします。 | -32 ビットのインストール[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]します。<br /><br /> -32 ビットのインストール[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]します。<br /><br /> 32 ビット LOB クライアントとその他の必要な Dll をインストールします。 | -32 ビットのインストール[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]します。<br /><br /> -32 ビットのインストール[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]します。<br /><br /> 32 ビット LOB クライアントとその他の必要な Dll をインストールします。 | -32 ビットのインストール[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]します。<br /><br /> -32 ビットのインストール[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]します。<br /><br /> 32 ビット LOB クライアントとその他の必要な Dll をインストールします。 |

#### <a name="scenarios-for-installing-the-biztalk-adapter-pack-on-a-64-bit-platform"></a>64 ビット プラットフォームで、BizTalk Adapter Pack をインストールするためのシナリオ  
 64 ビット プラットフォームでサポートされるシナリオは次のとおりです。  


|                                                                                                                 Visual Studio のデザイン時の                                                                                                                  |                                                                                                                  BizTalk MMC のデザイン時                                                                                                                   |                                                                                                                                                                                                                                                                                                         Biztalk ランタイム                                                                                                                                                                                                                                                                                                          |                                                                                                                                                                                                                                                                                                                                                                Visual Studio のデザイン時またはデザイン時の BizTalk MMC + BizTalk 実行時間                                                                                                                                                                                                                                                                                                                                                                |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| -64 ビットのインストール[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]します。<br /><br /> -32 ビットのインストール[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]します。<br /><br /> 32 ビット LOB クライアントとその他の必要な Dll をインストールします。 | -64 ビットのインストール[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]します。<br /><br /> -32 ビットのインストール[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]します。<br /><br /> 32 ビット LOB クライアントとその他の必要な Dll をインストールします。 | **32 ビット BizTalk プロセスの**:<br /><br /> -64 ビットのインストール[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]します。<br /><br /> -32 ビットのインストール[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]します。<br /><br /> 32 ビット LOB クライアントとその他の必要な Dll をインストールします。<br /><br /> **64 ビットの BizTalk プロセスの**:<br /><br /> -64 ビットのインストール[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]します。<br /><br /> -64 ビットのインストール[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]します。<br /><br /> -64 ビットの LOB クライアントとその他の必要な Dll をインストールします。 | **32 ビット BizTalk プロセスの**:<br /><br /> -64 ビットのインストール[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]します。<br /><br /> -32 ビットのインストール[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]します。<br /><br /> 32 ビット LOB クライアントとその他の必要な Dll をインストールします。<br /><br /> **64 ビットの BizTalk プロセスの**:<br /><br /> -64 ビットのインストール[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]します。<br /><br /> -64 ビットのインストール[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]します。<br /><br /> -64 ビットの LOB クライアントとその他の必要な Dll をインストールします。<br /><br /> -32 ビットのインストール[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]します。<br /><br /> 32 ビット LOB クライアントとその他の必要な Dll をインストールします。 |

> [!NOTE]
>  デザイン時のタスクを実行する任意のコンピューターにいずれかを使用して[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]BizTalk MMC で、32 ビットをインストールする必要がありますまたは[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]します。  

<a name="BKMK_Install_wizard"></a>   
### <a name="installing-the-biztalk-adapter-pack-in-interactive-mode"></a>対話モードで BizTalk Adapter Pack をインストールします。  
インストールするには、次の手順を完了、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]セットアップ ウィザードを使用します。  

1. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]インストール メディアで、実行**Setup.exe**します。  

2. 選択**Microsoft BizTalk Adapters インストール**します。 次のウィンドウで次のように選択します。 **Microsoft BizTalk Adapter Pack のインストール**または**インストール Microsoft BizTalk Adapter Pack (x64)** 、お使いのプラットフォームによって異なります。  

   > [!NOTE]
   >  インストールする場合、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]仮想マシンで、セットアップ ウィザードは、セットアップを使用可能なディスク領域にチェックすることを知らせるダイアログ ボックスを超える続行されません可能性があります。 このような場合は、サイレント インストール オプションを使用することをお勧めします。 参照してください[サイレント モードで BizTalk Adapter Pack をインストールする](#BKMK_SilentInst)(」を参照)。  

3. [ようこそ] 画面で、次のように選択します。**次**します。  

4. 使用許諾契約書 (EULA) に同意し、**次**します。  

5. **セットアップの種類を選択**:  

   -   最も一般的な機能をインストールする選択**標準**します。  

   -   インストールするアダプターを選択するには、次のように選択します。**カスタム**、し、次の手順に進んでください。  

   -   すべての機能をインストールする選択**完了**します。  

       > [!IMPORTANT]
       >  エンタープライズ アプリケーションとのインターフェイスを選択し、使用するアダプターのみをインストールする、**カスタム**インストールします。  

6. **必要な**カスタム インストールを選択した場合のみです。 選択した場合、**標準**または**完了**インストールでは、次に、この手順をスキップし、手順 7. に進みます。  

    1.  **カスタム セットアップ**、展開**ベース アダプター**に使用可能なアダプターを参照してください。  

    2.  しないようにするアダプターの場合、アダプターの横にあるアイコンを選択し、**全体の機能は使用できません**します。  

    3.  展開**ADO プロバイダー**、し、インストールしないプロバイダーを選択します。  

    4.  **[次へ]** を選択します。  

7. **[インストール]** を選択します。  

8. **カスタマー エクスペリエンス向上プログラム**、登録することもできます。 を登録する場合は、Microsoft と、次のデータを共有できます。  

   - インストール先コンピューターのハードウェアに関連するデータ、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]します。  

   - 関連データを使用するエンタープライズ アプリケーションのバージョンを[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]します。  

     **[OK]** を選択します。 [CEIP](http://go.microsoft.com/fwlink/p/?LinkId=144699)詳細に説明します。  

   > [!NOTE]
   >  修復モードでセットアップを実行して、この設定を変更することが常に**プログラム**します。  

9. **[完了]** を選択します。  

<a name="BKMK_SilentInst"></a>   
### <a name="installing-the-biztalk-adapter-pack-in-silent-mode"></a>サイレント モードで BizTalk Adapter Pack をインストールします。  
 使用して、 **msiexec**サイレント インストールを実行するコマンド。 Msiexec コマンドの一部として、インストールする個々 のコンポーネントを入力します。 次の表に、内の各コンポーネントの値、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]します。 特定のコンポーネントをインストール (または削除) するのにには、これらの値を使用します。 1 つ以上のコンポーネントをインストール (または削除)、コンマで区切られたこれらの値の組み合わせを使用できます。  


|                                    コンポーネント名                                    |                                                                コマンド ライン プロパティの対応する値                                                                 |
|--------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|        [!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)]        |                                                                                   DbFeature                                                                                    |
| [!INCLUDE[adapteroraclebusinessshort](../includes/adapteroraclebusinessshort-md.md)] |                                                                                OracleEBSFeature                                                                                |
|           [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]           |                                                                             SapBaseAdapterFeature                                                                              |
|        [!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)]        |                                                                            SiebelBaseAdapterFeature                                                                            |
|            [!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)]            |                                                                                   SqlFeature                                                                                   |
|        [!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]        |     SapAdoFeature<br /><br /> **注**:インストールする場合にのみ、この値を指定する必要があります、[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]もします。      |
|     [!INCLUDE[adoprovidersiebelshort](../includes/adoprovidersiebelshort-md.md)]     | SiebelAdoFeature<br /><br /> **注**:インストールする場合にのみ、この値を指定する必要があります、[!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)]もします。 |
|                                    すべてのコンポーネント                                    |                                                                                      ALL                                                                                       |

> [!IMPORTANT]
>  機能名は大文字小文字を区別します。  

 次の手順は、のサイレント インストールを完了する方法を説明[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]さまざまなコンポーネントです。  

##### <a name="install-in-silent-mode"></a>サイレント モードでインストールします。  

1. コマンド プロンプトを開きに移動、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]でルート、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]インストールします。  

2. インストールする内容に基づいて、次のコマンドを実行します。  

   > [!NOTE]
   >  X64 ベースのプラットフォームでサイレント インストールには、置換`AdaptersSetup.msi`で`AdaptersSetup64.msi`で、次のコマンド。  

   - アダプターは、.NET Framework データ プロバイダーを含む、すべてをインストールする完全なインストールを実行するには、次のように入力します。  

     ```  
     msiexec /i AdaptersSetup.msi /qn ADDLOCAL=ALL  
     ```  

   - のみをインストールする、[!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)]種類。  

     ```  
     msiexec /i AdaptersSetup.msi /qn ADDLOCAL=DbFeature  
     ```  

   - のみをインストールする、[!INCLUDE[adapteroraclebusinessshort](../includes/adapteroraclebusinessshort-md.md)]種類。  

     ```  
     msiexec /i AdaptersSetup.msi /qn ADDLOCAL=OracleEBSFeature  
     ```  

   - のみをインストールする、[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]種類。  

     ```  
     msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SapBaseAdapterFeature  
     ```  

   - インストールする、[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]と共に[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]種類。  

     ```  
     msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SapBaseAdapterFeature,SapAdoFeature  
     ```  

   - のみをインストールする、[!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)]種類。  

     ```  
     msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SiebelBaseAdapterFeature  
     ```  

   - インストールする、[!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)]と共に[!INCLUDE[adoprovidersiebelshort](../includes/adoprovidersiebelshort-md.md)]種類。  

     ```  
     msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SiebelBaseAdapterFeature,SiebelAdoFeature  
     ```  

   - のみをインストールする、[!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)]種類。  

     ```  
     msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SqlFeature  
     ```  

   - 基本のすべてのアダプターをインストールするには、次のように入力します。  

     ```  
     msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SapBaseAdapterFeature,SiebelBaseAdapterFeature,DbFeature,OracleEBSFeature,SqlFeature  
     ```  

   - 2 つの .NET Framework データ プロバイダーをインストールするには、次のように入力します。  

     ```  
     msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SapAdoFeature,SiebelAdoFeature  
     ```  

   - コンマでコンポーネントを分離することで、カスタム インストールの任意の型。 たとえば、インストールするため、[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]で、 [!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]、および[!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)]型。  

     ```  
     msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SapBaseAdapterFeature,SapAdoFeature,SiebelBaseAdapterFeature  
     ```  

   - サイレント インストールの一環として、CEIP に登録することもできます。 型:  

     ```  
     msiexec /i AdaptersSetup.msi /qn CEIP_OPTIN=true  
     ```  

      既定では、オプションは false です。 

     > [!IMPORTANT]
     >  インストール中に、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]サイレント モードでの評価版、CEIP の既定のオプションは true。  

     Msiexec コマンドの種類の詳細については`msiexec`キーを押して、コマンド ラインで`ENTER`します。 移動または[ http://go.microsoft.com/fwlink/p/?LinkId=103199](http://go.microsoft.com/fwlink/p/?LinkId=103199)します。

<a name="BKMK_PostInst"></a>   
### <a name="after-installing-the-biztalk-adapter-pack"></a>BizTalk Adapter Pack をインストールした後  
 インストールした後、次のタスクを実行する必要があります、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]を各アダプターで行いたい操作に基づいて。  

- [新しい Oracle.DataAccess.dll バージョンを使用する Oracle データベース アダプターの構成](#BKMK_ConfigNewOracleDLL)OracleDB 構成ファイルにします。  

- [SQL Server データベース オブジェクトを作成 (SAP アダプター) に対してのみ](#BKMK_CreateSQLServer)を SAP システムでトランザクションの Rfc (Trfc) を呼び出します。  

- [アダプターのバインドを登録](#BKMK_Register_Bindings)とそのためには、セットアップ ウィザードが失敗した場合に、.NET Framework データ プロバイダー。  

- [公開キーとバージョン特定](#BKMK_PubKey)異なるアダプター ファイルの。  

- [カスタム Rfc をインストール](#BKMK_InstallCustomRFC)をインストールした場合、[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]します。  

<a name="BKMK_ConfigNewOracleDLL"></a>   
#### <a name="configure-the-oracle-database-adapter-to-use-a-newer-oracledataaccessdll-version"></a>新しい Oracle.DataAccess.dll バージョンを使用する Oracle データベース アダプターを構成します。  
 Wcf-oracledb アダプターを使用または生成されたアダプターを使用する Visual Studio を使用するポートを構成するときに、アダプターが Oracle.DataAccess.dll バージョン 2.111.7.0 必要があることをメッセージが表示されます。 このメッセージを解決するには、サポートされている Oracle.DataAccess.dll バージョンをインストールします (を参照してください[サポート対象バージョン一覧](https://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-and-enterprise-systems.aspx))、し、更新、 `bindingRedirect` OracleDB 構成ファイル内の要素。 手順:  

1.  BizTalk Server では、次のフォルダーに移動します。  

     *drive*:\Program Files\Microsoft BizTalk Adapter Pack(x64)\bin  

     *ドライブ*: \Program Files (x86) \Microsoft BizTalk Adapter Pack\bin  

2.  Microsoft.Adapters.OracleDB.config ファイルを開きます。  

3.  次のセクションを検索して、コピー/貼り付け、次。  

    ```  
    <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
              <dependentAssembly>  
                        <assemblyIdentity name="Oracle.DataAccess" publicKeyToken="89b483f429c47342" culture="neutral" />  
                        <bindingRedirect oldVersion="2.111.7.00" newVersion="2.112.1.00"/>  
              </dependentAssembly>  
    </assemblyBinding>  

    ```  

    > [!NOTE]
    >  この例では設定*newVersion* 2.112.1.00 にします。 この値は、インストールしたバージョンに設定します。  

> [!IMPORTANT]
> - このグループに複数の BizTalk Server がある場合は、グループ内のすべての BizTalk サーバー上でこの変更を加えます。  
>   -   *NewVersion* Oracle.DataAccess.dll ファイルをコンピューターにインストールされているのバージョンに基づいて更新する値が必要です。  Oracle.DataAccess.dll は、Oracle からインストールする Oracle クライアントと共に含まれます。  Oracle クライアント バージョンをインストールする必要がありますのみ[BizTalk Adapter Pack でサポートされている](http://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-and-enterprise-systems.aspx)します。  

<a name="BKMK_CreateSQLServer"></a>   
#### <a name="create-sql-server-database-objects-only-for-the-sap-adapter"></a>(SAP アダプター) の場合のみ SQL Server データベース オブジェクトを作成します。  
 SAP システムで Trfc を呼び出すには、実行、 *SapAdapter-DbScript-Install.sql* SQL スクリプト。 このスクリプトがインストールされている、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]インストールでは、SQL Server のデータベース オブジェクトを作成します。 スクリプトは通常にインストールされて\<インストール ドライブ\>: \Program Files\Microsoft[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]します。 Trfc を呼び出すため、アダプターを使用しているときにそのデータベース名を入力する場合に限り、任意の SQL Server データベースに対してこのスクリプトを実行できます。  

<a name="BKMK_Register_Bindings"></a>   
#### <a name="register-the-adapter-bindings"></a>アダプターのバインドを登録します。  
 中に、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]インストールでは、セットアップ ウィザードはアダプター バインドまたは、.NET Framework Data Provider for mySAP Business Suite、登録に失敗する可能性がありますが、アダプターのインストールとセットアップが続行されます。 Windows Communication Foundation (WCF) のインストールに問題があります[!INCLUDE[afproductnamelong](../includes/afproductnamelong-md.md)]インストール、または壊れている machine.config ファイル。  

次の手順を完了*のみ*machine.config ファイルで、アダプターのバインドまたは .NET Framework データ プロバイダーを登録するセットアップ ウィザードが失敗した場合。  

###### <a name="register-the-adapter-bindings-or-the-net-framework-data-providers"></a>アダプター バインドまたは .NET Framework データ プロバイダーを登録します。  

1. コンピューターの machine.config ファイルに移動します。 たとえば、32 ビット プラットフォームで、machine.config はで使用可能な\<システム ドライブ\>: \WINDOWS\Microsoft.NET\Framework\\< バージョン\>\CONFIG します。  

2. テキスト エディターを使用してファイルを開きます。  

3. アダプターのバインドを登録します。  

   1. 検索、`system.serviceModel`要素、およびその下にある次の追加。  

      ```  
      <client>  
        <endpoint binding="sapBinding" contract="IMetadataExchange" name="sap" />  
        <endpoint binding="siebelBinding" contract="IMetadataExchange" name="siebel" />  
        <endpoint binding="oracleDBBinding" contract="IMetadataExchange" name="oracleDb" />  
        <endpoint binding="oracleEBSBinding" contract="IMetadataExchange" name="oracleEBS" />  
        <endpoint binding="sqlBinding" contract="IMetadataExchange" name="mssql" />  
      </client>  
      ```  

   2. 検索、 `bindingElementExtensions` system.serviceModel\extensions の下の要素。  

   3. 不足しているアダプターのバインドを探します。 次のセクションを追加、`bindingElementExtensions`ノード、不足しているアダプターのバインドによって異なります。 セットアップ ウィザードは、いずれかの登録が失敗した場合は、すべてのバインドを登録する必要があります。  

       [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]を追加します。  

      ```  
      <add name="sapAdapter" type="Microsoft.Adapters.SAP.SAPAdapterExtensionElement,Microsoft.Adapters.SAP, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

       [!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)]を追加します。  

      ```  
      <add name="siebelAdapter" type="Microsoft.Adapters.Siebel.SiebelAdapterExtensionElement,Microsoft.Adapters.Siebel, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

       [!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)]を追加します。  

      ```  
      <add name="oracleDBAdapter" type="Microsoft.Adapters.OracleDB.OracleDBAdapterExtensionElement,Microsoft.Adapters.OracleDB, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

       [!INCLUDE[adapteroraclebusinessshort](../includes/adapteroraclebusinessshort-md.md)]を追加します。  

      ```  
      <add name="OracleEBSAdapter" type="Microsoft.Adapters.OracleEBS.OracleEBSBindingElementExtensionElement, Microsoft.Adapters.OracleEBS, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

       [!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)]を追加します。  

      ```  
      <add name="sqlAdapter" type="Microsoft.Adapters.Sql.SqlAdapterBindingElementExtensionElement,Microsoft.Adapters.Sql, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

   4. 検索、 `bindingExtensions` system.serviceModel\extensions の下の要素。  

   5. 不足しているアダプターのバインドを探します。 次のセクションを追加、`bindingExtensions`ノード、不足しているアダプターのバインドによって異なります。 セットアップ ウィザードは、いずれかの登録が失敗した場合は、すべてのバインドを登録する必要があります。  

       [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]を追加します。  

      ```  
      <add name="sapBinding" type="Microsoft.Adapters.SAP.SAPAdapterBindingSection,Microsoft.Adapters.SAP, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

       [!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)]を追加します。  

      ```  
      <add name="siebelBinding" type="Microsoft.Adapters.Siebel.SiebelAdapterBindingSection,Microsoft.Adapters.Siebel, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

       [!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)]を追加します。  

      ```  
      <add name="oracleDBBinding" type="Microsoft.Adapters.OracleDB.OracleDBAdapterBindingSection,Microsoft.Adapters.OracleDB, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

       [!INCLUDE[adapteroraclebusinessshort](../includes/adapteroraclebusinessshort-md.md)]を追加します。  

      ```  
      <add name="OracleEBSBinding" type="Microsoft.Adapters.OracleEBS.OracleEBSBindingCollectionElement, Microsoft.Adapters.OracleEBS,Microsoft.Adapters.OracleEBS, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

       [!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)]を追加します。  

      ```  
      <add name="sqlBinding" type="Microsoft.Adapters.Sql.SqlAdapterBindingCollectionElement,Microsoft.Adapters.Sql, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

   > [!NOTE]
   >  公開キーを確認する方法については、次を参照してください。[公開キーとバージョン特定](#BKMK_PubKey)します。  

4. .NET Framework データ プロバイダーを登録します。  

   1. 検索、 `DbProviderFactories` system.data ノードの下の要素。  

   2. 不足している .NET Framework データ プロバイダーを探します。 次のセクションを追加、`DbProviderFactories`不足しているプロバイダーによって、ノード。 セットアップ ウィザードは、いずれかの登録が失敗した場合は、すべてのプロバイダーを登録する必要があります。  

       [!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]を追加します。  

      ```  
      <add name="SAPClient Data Provider" invariant="Microsoft.Data.SAPClient"   
          description=".NET Framework Data Provider for mySAP Business Suite"    type="Microsoft.Data.SAPClient.SAPClientFactory,Microsoft.Data.SAPClient, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

       [!INCLUDE[adoprovidersiebelshort](../includes/adoprovidersiebelshort-md.md)]を追加します。  

      ```  
      <add name="SiebelClient Data Provider" invariant="Microsoft.Data.SiebelClient"  
          description=".NET Framework Data Provider for Siebel eBusiness Applications"  
          type="Microsoft.Data.SiebelClient.SiebelProviderFactory,Microsoft.Data.SiebelClient, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

5. machine.config ファイルを保存して閉じます。  

<a name="BKMK_PubKey"></a>   
#### <a name="determine-the-public-key-and-version"></a>公開キーとバージョンを決定します。  
 公開キーと、アダプターまたは .NET Framework Data Provider のバージョンを確認するのには、次の手順を完了します。  

###### <a name="determine-the-public-key"></a>公開キーを確認します。  

1. Windows ディレクトリの通常 C:\WINDOWS\assembly に移動します。  

2. DLL を公開キーを必要し、し、選択を右クリックして**プロパティ**します。 次の表では、各アダプターおよびプロバイダーの Dll の名前を示します。  


   |                         アダプターおよび .NET Framework データ プロバイダー                         |       DLL の名前        |
   |--------------------------------------------------------------------------------------|------------------------------|
   |           [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]           |    Microsoft.Adapters.SAP    |
   |        [!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)]        |  Microsoft.Adapters.Siebel   |
   |        [!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)]        | Microsoft.Adapters.OracleDB  |
   | [!INCLUDE[adapteroraclebusinessshort](../includes/adapteroraclebusinessshort-md.md)] | Microsoft.Adapters.OracleEBS |
   |            [!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)]            |  Microsoft.Adapters.Sql.dll  |
   |        [!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]        |   Microsoft.Data.SAPClient   |
   |     [!INCLUDE[adoprovidersiebelshort](../includes/adoprovidersiebelshort-md.md)]     | Microsoft.Data.SiebelClient  |


3. **全般** タブで、**公開キー トークンの**値は、DLL の公開キー。 **バージョン**値は、DLL のバージョン番号。  

4. 公開キーをコピーし、**キャンセル**します。  

<a name="BKMK_InstallCustomRFC"></a>   
#### <a name="install-the-custom-rfcs"></a>カスタム Rfc をインストールします。  
 のみを使用する場合は、このタスクを実行する必要があります、[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]します。 カスタム Rfc をインストールする方法の詳細については、次を参照してください。[インストールのカスタム Rfc](../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md)で、[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]ドキュメント。 

> [!IMPORTANT]
>  提供されるカスタム Rfc の以前のバージョンを使用しているかどうか、 [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]、このリリースで提供する Rfc にアップグレードする必要があります。 これには、以前の Rfc を削除して、このリリースに付属し、Rfc をインストールします。  

## <a name="installing-the-enterprise-applications"></a>エンタープライズ アプリケーションをインストールします。  
」の手順と、さまざまなエンタープライズ LOB システムをインストールするためのガイダンスその特定のインストールを使用する recommendnd ガイドします。 存在する場合は、特定の構成の変更は、アダプターのドキュメントを参照してください。   

## <a name="installation-and-post-installation-checklist"></a>インストールとインストール後のチェックリスト  

- すべてをインストールすることを確認、[ソフトウェアの前提条件](#BKMK_Prereqs)正しいインストール オプションを使用します。

- インストールされているコンピューターにインストールされているエンタープライズ LOB アプリケーションのサポートされているバージョンがあるかどうかを確認、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]します。 参照してください[エンタープライズ アプリケーションのバージョンがサポートされている](#BKMK_SuppLOB)します。  

- エンタープライズに接続する LOB システムのアダプターのみをインストールすることをインストールしたことを確認して、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]を使用して、**カスタム**インストール オプションです。 インストールしていないことを確認、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]を使用して、**完了**インストール オプションです。 参照してください[BizTalk Adapter Pack をインストールする](#BKMK_Install_Adap)します。  

- TRFC の呼び出しを使用して、SAP システムを作成するかどうか、 [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]、SQL Server データベースで必要なテーブルを作成するかどうかを確認します。 参照してください[BizTalk Adapter Pack をインストールした後](#BKMK_PostInst)します。

- 実行中に、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]セットアップ ウィザードでは、バインドを登録できませんでしたというエラー メッセージが表示可能性があります。 場合は、手動で登録します。 参照してください[BizTalk Adapter Pack をインストールした後](#BKMK_PostInst)します。  

- インストールした場合、[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]の一部として、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]インストールでは、SAP システムにカスタム Rfc をインストールするかどうかを確認します。 参照してください[BizTalk Adapter Pack をインストールした後](#BKMK_PostInst)します。  

<a name="BKMK_Modify_Adap"></a>   
## <a name="change-the-biztalk-adapter-pack-installation"></a>BizTalk Adapter Pack のインストールを変更します。  
 変更するのには、次の手順を完了、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]インストールします。 あるかどうかを確認、[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]変更には、セットアップ ウィザードを実行する前にインストールされている、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]インストールします。  

 変更することができます、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]対話モード (セットアップ ウィザード) で、またはサイレント モード (コマンドライン) でインストールします。

#### <a name="change-the-bap-installation-in-interactive-mode"></a>対話モードで BAP インストールを変更します。  

1. BizTalk Server 管理者グループのメンバーであるアカウントを使用してサインインします。  

2. **プログラムと機能**、**プログラムのアンインストール**します。  

3. 右クリックして**Microsoft BizTalk Adapter Pack**、し、**変更**します。  

4. [ようこそ] 画面で、次のように選択します。**次**します。  

5. **変更、修復、または削除インストール**:  

   - インストールするコンポーネントを選択する**変更**し、手順 6. に進みます。  

   - 最新のインストールのエラーを修復するには、選択**修復**手順 7. に進みます。  

   - Microsoft を削除する[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]、コンピューターから次のように選択します。**削除**し、手順 10 に進みます。  

6. インストールを変更する場合。  

   -   展開、 **Microsoft BizTalk Adapter Pack**ノード ベース アダプター、.NET Framework データ プロバイダー、またはその両方をインストールするかを選択します。  

   -   展開、**ベース アダプター**ノードをすべてのアダプターまたは特定のアダプターのインストールを選択します。  

   -   展開、 **ADO プロバイダー**ノードすべてのプロバイダーまたは特定のプロバイダーをインストールするかを選択します。  

   -   **[次へ]** を選択します。  

   -   選択**変更**、し、**完了**します。  

7. インストールを修復することを選んだ場合、 **Microsoft BizTalk Adapter Pack の修復の準備完了**ダイアログ ボックスで、**修復**します。 ウィザードでは、インストールの修復を開始します。  

8. 必要な場合、基本設定を変更、CEIP のオプトインに関連し、 **OK**。 

9. **[完了]** を選択します。  

10. アダプターを削除した場合、 **Microsoft BizTalk Adapter Pack を削除する準備ができて**ダイアログ ボックスで、**削除**、し、**完了**。  

#### <a name="change-the-bap-installation-in-silent-mode"></a>サイレント モードで BAP インストールを変更します。  

1. コマンド プロンプトを開きのルート ディレクトリに移動、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]インストーラー。  

2. 次のようなコマンドを実行します。  

   > [!NOTE]
   >  変更する、 [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] 、次のコマンドでの x64 ベースのプラットフォームでサイレント モードでインストールを交換して`AdaptersSetup.msi`で`AdaptersSetup64.msi`。  

   ```  
   msiexec /i AdaptersSetup.msi /qn REMOVE=DbFeature ADDLOCAL=SapBaseAdapterFeature  
   ```  

    このコマンドを削除、[!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)]をインストールし、[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]します。  

    別の値を使用して、`REMOVE`と`ADDLOCAL`プロパティを追加または特定のコンポーネントを削除することができます。 内のテーブルを参照してください[サイレント モードで BizTalk Adapter Pack をインストールする](#BKMK_SilentInst)(このトピック) でこれらのプロパティを使用できる値についてはします。  

    Msiexec コマンドの一部として、/f オプションを使用して、サイレントの修復を実行することもできます。 以下に例を示します。  

   ```  
   msiexec /i AdaptersSetup.msi /qn /f  
   ```  

    /F オプションを使用して、さまざまなさまざまな組み合わせを使用できます。 Msiexec コマンドの種類の詳細については`msiexec`コマンドライン、およびキーを押して`ENTER`します。 移動または[ http://go.microsoft.com/fwlink/p/?LinkId=103199](http://go.microsoft.com/fwlink/p/?LinkId=103199)します。  

   > [!IMPORTANT]
   >  変更中に、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]サイレント モードでインストール、または ceip のオプトインの設定を変更することはできません。 True または false に、CEIP_OPTIN を明示的に設定した場合でも、インストールは残りの中に選択した環境を設定します。  

<a name="BKMK_Remove_Adap"></a>   
## <a name="removing-the-biztalk-adapter-pack"></a>BizTalk アダプター パックを削除します。  

> [!IMPORTANT]
>  TRFC 機能を使用する SQL Server データベースでテーブルを作成した場合、 [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]、削除する前に削除する必要があります手動で、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]します。 [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]インストールは、通常は SapAdapter-DbScript-Uninstall.sql ファイルをコピー\<インストール ドライブ\>: \Program Files\Microsoft[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]します。 作成したテーブルを削除するには、このファイルを実行します。  

削除するには、次の手順を完了、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]コンピューターから。 必ず、[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]アダプターを削除するセットアップ ウィザードを実行する前にインストールされています。  

 削除することができます、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]対話モード (セットアップ ウィザード)、またはサイレント モード (コマンドライン)。

#### <a name="uninstall-the-biztalk-adapter-pack-in-interactive-mode"></a>対話モードで BizTalk Adapter Pack をアンインストールします。  

1.  **プログラムと機能**、**プログラムのアンインストール**します。  

2.  右クリックして**Microsoft BizTalk Adapter Pack**、し、**アンインストール**します。  

#### <a name="uninstall-the-biztalk-adapter-pack-in-silent-mode"></a>サイレント モードで BizTalk Adapter Pack をアンインストールします。  

1. コマンド プロンプトを開きのルート ディレクトリに移動、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]インストーラー。  

2. 次のコマンドを実行します。  

   > [!NOTE]
   >  削除する、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]サイレント モードで、次のコマンドでの x64 ベースのプラットフォームで置き換える`AdaptersSetup.msi`で`AdaptersSetup64.msi`。  

   ```  
   msiexec /i AdaptersSetup.msi /qn REMOVE=DbFeature  
   ```  

    このコマンドを削除、[!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)]から、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]インストールします。  

    さまざまな値を提供することで、`REMOVE`プロパティから特定のコンポーネントを削除することができます、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]インストールします。 内のテーブルを参照してください[サイレント モードで BizTalk Adapter Pack をインストールする](#BKMK_SilentInst)(このトピック) でこのプロパティの使用できる値についてはします。  

    完全に削除する、 [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]、次のコマンドを実行します。  

   ```  
   msiexec /x AdaptersSetup.msi /qn  
   ```  

    Msiexec コマンドの種類の詳細については`msiexec`コマンドライン、およびキーを押して`ENTER`します。 移動または[ http://go.microsoft.com/fwlink/p/?LinkId=103199](http://go.microsoft.com/fwlink/p/?LinkId=103199)します。

<a name="BKMK_PostRemove"></a>   
### <a name="after-removing-the-biztalk-adapter-pack"></a>BizTalk Adapter Pack を削除した後  
 削除した後、次の手順を実行する必要があります、 [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]:  

- そのためには、セットアップ ウィザードが失敗した場合、アダプターのバインドまたは .NET Framework Data Provider の登録を削除します。

- インストールした場合は、カスタムの Rfc を削除します [!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]

<a name="BKMK_Remove_Binding"></a>   
#### <a name="remove-the-bindings-or-the-net-framework-data-provider-registration"></a>バインドまたは .NET Framework Data Provider の登録を削除します。  
 次の手順を完了*のみ*アダプター バインドまたは .NET Framework データ プロバイダーの登録、machine.config ファイルから削除するセットアップ ウィザードが失敗した場合。  

###### <a name="remove-the-adapter-bindings-or-net-framework-data-provider-registration"></a>アダプター バインドまたは .NET Framework データ プロバイダーの登録を削除します。  

1. コンピューターの machine.config ファイルに移動します。 たとえば、32 ビット プラットフォームで、machine.config はで使用可能な\<システム ドライブ\>: \WINDOWS\Microsoft.NET\Framework\\< バージョン\>\CONFIG します。  

2. テキスト エディターを使用してファイルを開きます。  

3. アダプターのバインドの登録を削除します。  

   1. 検索、`system.serviceModel`要素、および次の要素の下から削除します。  

      ```  
      <client>  
        <endpoint binding="sapBinding" contract="IMetadataExchange" name="sap" />  
        <endpoint binding="siebelBinding" contract="IMetadataExchange" name="siebel" />  
        <endpoint binding="oracleDBBinding" contract="IMetadataExchange" name="oracleDb" />  
        <endpoint binding="OracleEBSBinding" contract="IMetadataExchange" name="oracleEBS" />  
        <endpoint binding="sqlBinding" contract="IMetadataExchange" name="mssql" />  
      </client>  

      ```  

   2. 検索、 `bindingElementExtensions` system.serviceModel\extensions の下の要素。  

   3. 次のセクションでは、削除、`bindingElementExtensions`ノードで、使用可能なアダプターのバインドによって異なります。 セットアップ ウィザードは、削除が失敗した場合、すべてのバインドを削除する必要があります。  

       [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]、削除します。  

      ```  
      <add name="sapAdapter" type="Microsoft.Adapters.SAP.SAPAdapterExtensionElement,Microsoft.Adapters.SAP, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

       [!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)]、削除します。  

      ```  
      <add name="siebelAdapter" type="Microsoft.Adapters.Siebel.SiebelAdapterExtensionElement,Microsoft.Adapters.Siebel, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

       [!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)]、削除します。  

      ```  
      <add name="oracleDBAdapter" type="Microsoft.Adapters.OracleDB.OracleDBAdapterExtensionElement,Microsoft.Adapters.OracleDB, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

       [!INCLUDE[adapteroraclebusinessshort](../includes/adapteroraclebusinessshort-md.md)]、削除します。  

      ```  
      <add name="OracleEBSAdapter" type="Microsoft.Adapters.OracleEBS.OracleEBSBindingElementExtensionElement, Microsoft.Adapters.OracleEBS, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

       [!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)]、削除します。  

      ```  
      <add name="sqlAdapter" type="Microsoft.Adapters.Sql.SqlAdapterBindingElementExtensionElement,Microsoft.Adapters.Sql, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

   4. 検索、 `bindingExtensions` system.serviceModel\extensions の下の要素。  

   5. 次のセクションでは、削除、`bindingExtensions`ノードで、使用可能なアダプターのバインドによって異なります。 セットアップ ウィザードは、削除が失敗した場合、すべてのバインドを削除する必要があります。  

       [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]、削除します。  

      ```  
      <add name="sapBinding" type="Microsoft.Adapters.SAP.SAPAdapterBindingSection,Microsoft.Adapters.SAP, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

       [!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)]、削除します。  

      ```  
      <add name="siebelBinding" type="Microsoft.Adapters.Siebel.SiebelAdapterBindingSection,Microsoft.Adapters.Siebel, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

       [!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)]、削除します。  

      ```  
      <add name="oracleDBBinding" type="Microsoft.Adapters.OracleDB.OracleDBAdapterBindingSection,Microsoft.Adapters.OracleDB, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

       [!INCLUDE[adapteroraclebusinessshort](../includes/adapteroraclebusinessshort-md.md)]、削除します。  

      ```  
      <add name="OracleEBSBinding" type="Microsoft.Adapters.OracleEBS.OracleEBSBindingCollectionElement, Microsoft.Adapters.OracleEBS, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

       [!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)]、削除します。  

      ```  
      <add name="sqlBinding" type="Microsoft.Adapters.Sql.SqlAdapterBindingCollectionElement,Microsoft.Adapters.Sql, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

4. .NET Framework Data Provider の登録を削除します。  

   - 検索、 `DbProviderFactories` system.data ノードの下の要素。  

   - まだ登録されている .NET Framework データ プロバイダーを探します。 次のセクションでは、削除、`DbProviderFactories`によっては、既存の .NET Framework データ プロバイダーのノード。 存在する場合は、すべてのプロバイダーを削除する必要があります。  

      [!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]、削除します。  

     ```  
     <add name="SAPClient Data Provider" invariant="Microsoft.Data.SAPClient"   
         description=".NET Framework Data Provider for mySAP Business Suite"    type="Microsoft.Data.SAPClient.SAPClientFactory,Microsoft.Data.SAPClient, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
     ```  

      [!INCLUDE[adoprovidersiebelshort](../includes/adoprovidersiebelshort-md.md)]、削除します。  

     ```  
     <add name="SiebelClient Data Provider" invariant="Microsoft.Data.SiebelClient"  
         description=".NET Framework Data Provider for Siebel eBusiness Applications"  
         type="Microsoft.Data.SiebelClient.SiebelProviderFactory,Microsoft.Data.SiebelClient, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
     ```  

5. machine.config ファイルを保存して閉じます。  

<a name="BKMK_Remove_SAP_Pro"></a>   
#### <a name="remove-the-custom-rfcs"></a>カスタム Rfc を削除します。  
SAP システムがインストールされているカスタム Rfc を削除するには、この手順を完了します。 参照してください[インストールまたは削除のカスタム Rfc](../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md)します。  

## <a name="troubleshoot-biztalk-adapter-pack-installation"></a>BizTalk Adapter Pack のインストールをトラブルシューティングします。  
 次のいくつかインストールするときに考慮しなければならない問題が[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]します。 インストールに関連する問題の包括的な一覧を参照してください**トラブルシューティング**アダプターごとにトピック。  

- **64 ビット コンピューターでセットアップを実行してはスキーマ ファイルにアクセス中にエラーをスローする可能性があります。**  

   [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]セットアップへのアクセス中にエラーをスローする、 **Microsoft.Adapters *。\<AdapterName\>* _schema.xml**が、アダプターのインストールを続行します。  

   **原因**  

   場合の 32 ビットと 64 ビットの両方のバージョン、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]がインストールされている両方で使用されるターゲットのスキーマ ファイルでは、同じコンピューターでは同じです。 32 ビットでファイルがインストールされている結果として、 [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] 64 ビットのインストーラーが、アクセスしようとしています。 IIS で使用されている可能性があります。  

   **解決方法**  

   手動でコピー、 **Microsoft.Adapters *。\<AdapterName\>* _schema.xml**ファイルから`C:\Program Files\Microsoft BizTalk Adapter Pack(x64)\IIS Schemas`"に`C:\Windows\System32\inetsrv\config\schema`します。  