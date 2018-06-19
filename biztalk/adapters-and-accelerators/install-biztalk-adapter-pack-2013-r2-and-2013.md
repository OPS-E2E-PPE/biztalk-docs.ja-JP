---
title: BizTalk Adapter Pack 2013 R2 と 2013 のインストール |Microsoft ドキュメント
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
ms.openlocfilehash: c8bc1ebbdaf2973f4749da6c0832d49204588b6c
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
ms.locfileid: "25968032"
---
# <a name="install-biztalk-adapter-pack-2013-r2-and-2013"></a>BizTalk Adapter Pack 2013 R2 と 2013 をインストールします。
このドキュメントには、Microsoft をインストールするには、ソフトウェア要件、および手順[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)](BAP) は、BizTalk Server 2013 に含まれているか、[!INCLUDE[bts2013r2](../includes/bts2013r2-md.md)]です。  
  
## <a name="change-log"></a>変更ログ  
  
|日付|変更|  
|---|---|  
|2016 年 3 月|**インストール後にしています.** Oracle.DataAccess.dll の新しいバージョンを使用する Oracle データベース アダプターを構成する手順を追加します。|  
  
<a name="BKMK_Prereqs"></a>   
## <a name="software-prerequisites"></a>ソフトウェアの前提条件  
 [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]から使用されることができます。  
  
-   .NET アプリケーション  
  
-   Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]  
  
-   ADO インターフェイス  
  
-   Microsoft SharePoint ポータル  
  
 アダプターを使用する方法に基づき、必要なソフトウェアによって異なります。  
  
### <a name="prerequisites-when-using-a-net-application"></a>.NET アプリケーションを使用する場合の前提条件  
アダプターを使用する .NET アプリケーションの使用、開発用コンピューター (.NET アプリケーションを作成しているコンピューター) で、次のソフトウェアが必要です。 この順で、ソフトウェアをインストールします。
  
|BizTalk Adapter Pack 2013 R2|BizTalk Adapter Pack 2013|  
|---|---|  
|[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)] R2 [!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]、Windows 8.1、Windows 7 SP1|[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]、 [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] SP1、Windows 8、Windows 7 SP1|  
|[!INCLUDE[dotnet451](../includes/dotnet451-md.md)]|Microsoft [!INCLUDE[dotnet45](../includes/dotnet45-md.md)]|  
|Visual Studio 2013|Visual Studio 2012|  
|[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]|[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]|  
|エンタープライズ アプリケーションのクライアントと関連付けられているソフトウェア。 参照してください[エンタープライズ アプリケーションのバージョンがサポートされている](#BKMK_SuppLOB)です。|エンタープライズ アプリケーションのクライアントと関連付けられているソフトウェア。 参照してください[エンタープライズ アプリケーションのバージョンがサポートされている](#BKMK_SuppLOB)です。|  

### <a name="prerequisites-when-using-a-biztalk-server"></a>BizTalk Server を使用する場合の前提条件  
BizTalk Server を使用して、アダプターを使用する、BizTalk Server で、次のソフトウェアが必要です。 この順で、ソフトウェアをインストールします。
  
|BizTalk Adapter Pack 2013 R2|BizTalk Adapter Pack 2013|  
|---|---|  
|[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)] R2 [!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]、Windows 8.1、Windows 7 SP1|[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]、 [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] SP1、Windows 8、Windows 7 SP1|  
|[!INCLUDE[dotnet451](../includes/dotnet451-md.md)]|Microsoft [!INCLUDE[dotnet45](../includes/dotnet45-md.md)]|  
|Visual Studio 2013|Visual Studio 2012|  
|[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]<br /><br /> インストール、[!INCLUDE[consumeadapterservlong](../includes/consumeadapterservlong-md.md)]の[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]に含まれている、[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]です。 インストールするには、**カスタム**(選択**BizTalk Server アドイン**) または**完了**のインストール、[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]です。|[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]<br /><br /> インストール、[!INCLUDE[consumeadapterservlong](../includes/consumeadapterservlong-md.md)]の[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]に含まれている、[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]です。 インストールするには、**カスタム**(選択**BizTalk Server アドイン**) または**完了**のインストール、[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]です。|  
|BizTalk Server 2013 R2|BizTalk Server 2013|  
|エンタープライズ アプリケーションのクライアントと関連付けられているソフトウェア。 参照してください[エンタープライズ アプリケーションのバージョンがサポートされている](#BKMK_SuppLOB)です。|エンタープライズ アプリケーションのクライアントと関連付けられているソフトウェア。 参照してください[エンタープライズ アプリケーションのバージョンがサポートされている](#BKMK_SuppLOB)です。|  

### <a name="prerequisites-when-using-ado"></a>ADO を使用する場合の前提条件  
 **[!INCLUDE[adaptersap](../includes/adaptersap-md.md)]** と**[!INCLUDE[adaptersiebel](../includes/adaptersiebel-md.md)]** ADO レイヤーが含まれます (*[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]* と*[!INCLUDE[adoprovidersiebelshort](../includes/adoprovidersiebelshort-md.md)]*)。 この ADO レイヤーは、SAP システムまたは Siebel システムへの接続に、ADO.NET クライアントを記述する使用できます。 行えます ADO レイヤーで SQL Server Integration Services (SSIS) のインポートし、エクスポートのデータ、LOB アプリケーション、および SQL Server Reporting Services (SSRS) レポートを生成するデータ、LOB システムの表示にします。  
  
> [!NOTE]
>  ADO プロバイダーを使用して、SSRS でのみサポートされて、  *[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]* です。  
  
使用するコンピューターで、次のソフトウェアが必要な[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]ADO インターフェイスを使用します。 この順で、ソフトウェアをインストールします。
  
|BizTalk Adapter Pack 2013 R2|BizTalk Adapter Pack 2013|  
|---|---|  
|[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)] R2 [!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]、Windows 8.1、Windows 7 SP1|[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]、 [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] SP1、Windows 8、Windows 7 SP1|  
|[!INCLUDE[dotnet451](../includes/dotnet451-md.md)]|Microsoft [!INCLUDE[dotnet45](../includes/dotnet45-md.md)]|  
|Visual Studio 2013|Visual Studio 2012|  
|[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]|[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]|  
|[!INCLUDE[sqlserver2014](../includes/sqlserver2014-md.md)], [!INCLUDE[sqlserver2012](../includes/sqlserver2012-md.md)]|[!INCLUDE[sqlserver2012](../includes/sqlserver2012-md.md)], [!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)]|  
|エンタープライズ アプリケーションのクライアントと関連付けられているソフトウェア。 参照してください[エンタープライズ アプリケーションのバージョンがサポートされている](#BKMK_SuppLOB)です。|エンタープライズ アプリケーションのクライアントと関連付けられているソフトウェア。 参照してください[エンタープライズ アプリケーションのバージョンがサポートされている](#BKMK_SuppLOB)です。|  

### <a name="prerequisites-when-using-microsoft-sharepoint"></a>Microsoft SharePoint を使用する場合の前提条件  
 Microsoft SharePoint で、アダプターの使用の目的は、SharePoint portal の LOB アプリケーションからデータを表示です。  
  
一般的なセットアップで、 [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] SharePoint 1 台のコンピューターまたはできるさまざまなタスクの別のコンピューターを使用するとします。 次の表は、各コンピューターのソフトウェアの前提条件をまとめたものです。 1 台のコンピューターを使用している場合は、そのコンピューターのすべてのソフトウェアが必要です。 この順で、ソフトウェアをインストールします。  
  
|WCF アダプター サービス開発ウィザードを実行するコンピューター|WCF サービスをホストするコンピューター|コンピューターの外部コンテンツ タイプを定義する SharePoint Designer を使用できます。|LOB アプリケーションからの情報を提示する SharePoint を使用するコンピューター|  
|---|---|---|---|  
|**BAP 2013 R2**:<ul><li>[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)] R2<br/>[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]<br/>Windows 8.1<br/>Windows 7 SP1</li><li>[!INCLUDE[dotnet451](../includes/dotnet451-md.md)]</li><li> Visual Studio 2013</li><li>[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]</li><li>Microsoft [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]</li><li>それぞれのエンタープライズ アプリケーションのクライアントと関連付けられているソフトウェア。 参照してください[エンタープライズ アプリケーションのバージョンがサポートされている](#BKMK_SuppLOB)です。</li></ul> **BAP 2013**:<ul><li>[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]<br/>[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] SP1<br/>Windows 8<br/>Windows 7 SP1</li><li>Microsoft [!INCLUDE[dotnet45](../includes/dotnet45-md.md)]</li><li>Visual Studio 2012</li><li>[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]</li><li>Microsoft [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]</li><li>それぞれのエンタープライズ アプリケーションのクライアントと関連付けられているソフトウェア。 参照してください[エンタープライズ アプリケーションのバージョンがサポートされている](#BKMK_SuppLOB)です。</li></ul>|**BAP 2013 R2**:<ul><li>[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)] R2<br/>[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]<br/>Windows 8.1<br/>Windows 7 SP1</li><li>[!INCLUDE[dotnet451](../includes/dotnet451-md.md)]</li><li>[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]</li><li>Microsoft [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]</li><li>それぞれのエンタープライズ アプリケーションのクライアントと関連付けられているソフトウェア。 参照してください[エンタープライズ アプリケーションのバージョンがサポートされている](#BKMK_SuppLOB)です。</li><li>オペレーティング システムに付属しているインターネット インフォメーション サービス (IIS) バージョン。 KB 224609 は、バージョンを一覧表示します。</li></ul>**BAP 2013**:<ul><li>[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]<br/>[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] SP1<br/>Windows 8<br/>Windows 7 SP1</li><li>Microsoft [!INCLUDE[dotnet45](../includes/dotnet45-md.md)]</li><li>[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]</li><li>Microsoft [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]</li><li>それぞれのエンタープライズ アプリケーションのクライアントと関連付けられているソフトウェア。 参照してください[エンタープライズ アプリケーションのバージョンがサポートされている](#BKMK_SuppLOB)です。</li><li>オペレーティング システムに付属しているインターネット インフォメーション サービス (IIS) バージョン。 KB 224609 は、バージョンを一覧表示します。</li></ul>|Microsoft Office SharePoint Server ソフトウェア開発キット (SDK)|Microsoft Office のサーバー インフラストラクチャを更新します。 ダウンロード[ http://go.microsoft.com/fwlink/?LinkId=128344](http://go.microsoft.com/fwlink/?LinkId=128344)です。|  
  
<a name="BKMK_SuppLOB"></a>   
## <a name="supported-enterprise-application-versions"></a>サポートされているエンタープライズ アプリケーションのバージョン  

サポートされている特定の LOB システムのバージョンを表示する、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]を参照してください**[サポートされている行の基幹業務 (LOB) システム](http://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-systems.aspx)** です。 

ここでは、各アダプターに必要なすべてのクライアント Dll など、各アダプターの追加情報を示します。  
  
### <a name="oracle-database-adapter"></a>Oracle Database アダプター  
  
-   省略可能: 分散トランザクションを使用して Oracle データベースがある場合はインストール**Oracle Services for Microsoft Transaction Server** (Oracle クライアントのインストールの一部) アダプターのクライアントを実行している、コンピューター。  
  
-   ODP.NET の最新バージョンで動作するアプリケーションをインストール、**ポリシー Dll**および GAC の Dll を登録します。 参照してください[.NET に関する FAQ の Oracle データ プロバイダー](http://www.oracle.com/technetwork/database/windows/faq-093106.html)です。  

### <a name="oracle-e-business-adapter"></a>Oracle E-Business アダプター  
  
-   省略可能: Oracle データベースに分散トランザクションを使用するインストール**Oracle Services for Microsoft Transaction Server** (Oracle クライアントのインストールの一部) アダプターのクライアントを実行している、コンピューター。  
  
-   ODP.NET の最新バージョンで動作するアプリケーションをインストール、**ポリシー Dll**および GAC の Dll を登録します。 参照してください[.NET に関する FAQ の Oracle データ プロバイダー](http://www.oracle.com/technetwork/database/windows/faq-093106.html)です。  
  
### <a name="sap-adapter"></a>SAP アダプター  
  
-   [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)] SAP システムは、Unicode または unicode 対応でないかどうかに関係なく、RFC SDK の Unicode バージョンが必要です。  
  
-   **必要なドライバー**: 次の表に、必要な Dll、 [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] SAP システムとやり取りします。 これらの Dll を含むパッケージのほとんどは、SAP サービス Marketplace からダウンロードする必要があります。 SAP サービス Marketplace からダウンロードを取得します。 
  
    1.  SAP サービス Marketplace から、ダウンロード マネージャーをインストールします。  
  
    2.  SAP サービス Marketplace 用の資格情報を使用して、ダウンロード マネージャーを構成します。  
  
    3.  SAP のサービスの web サイトからソフトウェアをダウンロードする、組織内の SAP 管理者によって承認されます。 これは、機能は、' ソフトウェアのダウンロード ' 認証オブジェクトを SAP Software Distribution Center へのアクセスが制限されているため必要です。 これにより、ソフトウェアのダウンロードが承認されたユーザーのみであります。  
  
    4.  SAP サービス Marketplace からダウンロードしたパッケージからファイルを抽出するために必要な最初に見つかったプログラムをインストールします。 最初に見つかったは SAP サービス マーケットプ レースからも使用できます。  
  
     32 ビットおよび 64 ビット バージョンの[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]、これらの各 32 ビットおよび 64 ビット バージョンは Dll である必要があります。  
  
    -   32 ビット コンピューターで C:\Windows\System32 フォルダーに、Dll の 32 ビット バージョンを追加する必要があります。  
  
    -   64 ビット コンピューターで 32 ビット バージョンの Dll の C:\Windows\SysWow64 フォルダーに追加する必要があります。 Dll の 64 ビット バージョンは、C:\Windows\System32 フォルダーに追加する必要があります。  
  
    |SAP クライアント バージョン|必要なドライバー|  
    |------------------------|----------------------|  
    |6.4|**BizTalk Adapter Pack 2013 のみ**<br /><br /> - **SAP RFC SDK 6.40 UNICODE**. これは、使用可能な SNOTE の一部として<sup>* </sup> 27517 です。SDK をダウンロードする手順は[ http://go.microsoft.com/fwlink/?LinkId=94691](http://go.microsoft.com/fwlink/?LinkId=94691)です。ダウンロードして、SDK を展開したら、\rfcsdk\bin および \rfcsdk\lib フォルダーから、関連する場所に記載されている次の表の前のすべての Dll をコピーします。<br /> <br /> -Dll には SAP からの一部として**R3DLLINST.zip**です。これは、は、Microsoft ランタイム Dll を含んでおり、SAP サイトからダウンロードできます。SNOTE を参照してください<sup>* </sup> 684106 詳細についてはします。 .Zip ファイルをダウンロードする[ http://go.microsoft.com/fwlink/?LinkId=94693](http://go.microsoft.com/fwlink/?LinkId=94693)です。 このリンクには、"Attachments"からパッケージをダウンロードするオプションがあります。<br /><br /> -SAP システムへの接続に SAP セキュリティで保護されたネットワーク通信 (SNC) を使用する場合は、SAP から関連する Dll を必要もあります。 これらの Dll は、32 ビットおよび 64 ビット プラットフォーム用に異なる、SNOTE で利用可能な<sup>* </sup> 352295 です。 Dll をダウンロードする[ http://go.microsoft.com/fwlink/?LinkId=104032](http://go.microsoft.com/fwlink/?LinkId=104032)です。 このリンクには、"Attachments"からパッケージをダウンロードするオプションがあります。 Dll の名前は次のとおりです。<br /><br /> - **32 ビット**: gsskrb5.dll、gssntlm.dll<br /><br /> -  **64 ビット x86 用**: gx64krb5.dll、gx64ntlm.dll|  
    |7.0|- **SAP RFC SDK 7.00 UNICODE**. これは、使用可能な SNOTE の一部として<sup>* </sup> 27517 です。SDK をダウンロードする手順は[ http://go.microsoft.com/fwlink/?LinkId=94691](http://go.microsoft.com/fwlink/?LinkId=94691)です。ダウンロードし、SDK を抽出した後は、\rfcsdk\bin および \rfcsdk\lib フォルダーからと、関連する場所に記載されている次の表の前に、すべての Dll をコピーします。<br /> <br /> -Dll には SAP からの一部として**R3DLLINST.zip**です。これは、は、Microsoft ランタイム Dll を含んでおり、SAP サイトからダウンロードできます。SNOTE を参照してください<sup>* </sup> 684106 詳細についてはします。 .Zip ファイルをダウンロードする[ http://go.microsoft.com/fwlink/?LinkId=94693](http://go.microsoft.com/fwlink/?LinkId=94693)です。 このリンクには、"Attachments"からパッケージをダウンロードするオプションがあります。<br /><br /> -SAP システムへの接続に SAP セキュリティで保護されたネットワーク通信 (SNC) を使用する場合は、SAP から関連する Dll を必要もあります。 これらの Dll は、32 ビットおよび 64 ビット プラットフォーム用に異なる、SNOTE で利用可能な<sup>* </sup> 352295 です。 Dll をダウンロードする[ http://go.microsoft.com/fwlink/?LinkId=104032](http://go.microsoft.com/fwlink/?LinkId=104032)です。 このリンクには、"Attachments"からパッケージをダウンロードするオプションがあります。 Dll の名前は次のとおりです。<br /><br /> - **32 ビット**: gsskrb5.dll、gssntlm.dll<br /><br /> - **64 ビット x86 用**: gx64krb5.dll、gx64ntlm.dll|  
    |7.1|- **SAP RFC SDK 7.10 UNICODE**. これは、使用可能な SNOTE の一部として<sup>* </sup> 27517 です。SDK をダウンロードする手順は[ http://go.microsoft.com/fwlink/?LinkId=94691](http://go.microsoft.com/fwlink/?LinkId=94691)です。ダウンロードして、SDK を展開したら、\rfcsdk\bin および \rfcsdk\lib フォルダーから、関連する場所に記載されている次の表の前のすべての Dll をコピーします。<br /> <br /> -Dll には SAP からの一部として**R3DLLINST.zip**です。これは、は、Microsoft ランタイム Dll を含んでおり、SAP サイトからダウンロードできます。SNOTE を参照してください<sup>* </sup> 684106 詳細についてはします。 .Zip ファイルをダウンロードする[ http://go.microsoft.com/fwlink/?LinkId=94693](http://go.microsoft.com/fwlink/?LinkId=94693)です。 このリンクには、"Attachments"からパッケージをダウンロードするオプションがあります。<br /><br /> Microsoft Visual C ランタイム Dll SAP 7.1 クライアントに必要なには、次のリンクからです。<br /><br /> - **32 ビット SAP 7.1 クライアントを**: から Vcredist_x86.exe [ http://go.microsoft.com/fwlink/?LinkId=107086](http://go.microsoft.com/fwlink/?LinkId=107086)です。<br /><br /> -                                 **64 ビット SAP 7.1 クライアントを**: から Vcredist_x64.exe [ http://go.microsoft.com/fwlink/?LinkId=107087](http://go.microsoft.com/fwlink/?LinkId=107087)です。<br /><br /> -SAP システムへの接続に SAP セキュリティで保護されたネットワーク通信 (SNC) を使用する場合は、SAP から関連する Dll を必要もあります。 これらの Dll は、32 ビットおよび 64 ビット プラットフォーム用に異なる、SNOTE で利用可能な<sup>* </sup> 352295 です。 Dll をダウンロードする[ http://go.microsoft.com/fwlink/?LinkId=104032](http://go.microsoft.com/fwlink/?LinkId=104032)です。 このリンクには、"Attachments"からパッケージをダウンロードするオプションがあります。 Dll の名前は次のとおりです。<br /><br /> - **32 ビット**: gsskrb5.dll、gssntlm.dll<br /><br /> - **64 ビット x86 用**: gx64krb5.dll、gx64ntlm.dll|  
  
     * SNOTEs は、SAP でリリースされた修正プログラムに付属のリリース ノートです。  

### <a name="siebel-adapter"></a>Siebel アダプター  
余分な手順はありません。
  
### <a name="sql-adapter"></a>SQL アダプター  
  
**必要なドライバー**:  
  
-   **SQL Server 2005 の**: SQL Server でユーザー定義型 (Udt) を作成する場合は、Udt のそれぞれのアセンブリが GAC に追加を確認してください。  
  
-   **SQL Server 2014、SQL Server 2012、SQL Server 2008 R2、SQL Server 2008 SP1 の**:  
  
    -   SQL Server のバージョン、たとえば、Geography に付属して Udt を使用する場合は、次の Dll は、SQL Server 上の操作を実行するアダプターを使用するコンピューター上に存在を確認します。 など、SQL Server 上の操作を実行する BizTalk プロジェクトを作成する場合は、これらの Dll が BizTalk Server が実行されているコンピューター上に存在する必要があります。  
  
        -   Microsoft.SqlServer.Types.dll は GAC に追加することを確認します。  
  
        -   SqlServerSpatial.dll が System32 フォルダーにあることを確認してください。    
        
        SQL Server セットアップを実行しを選択すると、コンピューターにこれらの Dll をインストールできます**管理ツール-基本**と**管理ツール-完全**で、**機能の選択**ウィザードのページです。          
  
    -   FILESTREAM データ型の列に対して操作を実行するアダプターを使用する場合は、SQL クライアント接続 SDK がインストールされている必要があることを確認してください。 SQL Server セットアップを実行しを選択すると、SQL クライアント接続 SDK をインストールすることができます**SQL クライアント接続 SDK**で、**機能の選択**ウィザードのページです。 アダプターは、FILESTREAM 操作を実行するのに、SQL クライアント接続 SDK と共にインストールされる、sqlncli10.dll を使用します。  

    -   SQL Server で、独自の Udt を作成する場合は、Udt のそれぞれのアセンブリが GAC に追加を確認します。

## <a name="64-bit-support"></a>64 ビットのサポート

Siebel アダプターは、32 ビット ホスト インスタンスでサポートされています。 Siebel アダプターを 64 ビット ホスト インスタンスで実行することはできません。 

他のすべてのアダプターは、32 ビットまたは 64 ビット ホスト インスタンスで実行できます。 


  
 32 ビットおよび 64 ビットのインストールのサポートされているインストール シナリオの詳細については[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]を参照してください[32 ビットおよび 64 ビット プラットフォームでは、BizTalk Adapter Pack のインストール シナリオ](#BKMK_Install_Scenarios)です。  
  
<a name="BKMK_Install_Adap"></a>   
## <a name="installing-the-biztalk-adapter-pack"></a>BizTalk Adapter Pack をインストールします。  
 すべてを確認して、[ソフトウェアの前提条件](#BKMK_Prereqs)がインストールする前にインストールされている、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]です。 インストールすることができます、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]次の 2 つの方法で。  
  
-   **対話モードで**: セットアップ ウィザードを実行  
  
-   **サイレント モードで**: コマンドラインを使用して  
  
    > [!IMPORTANT]
    >  インストールするコンピューターで管理者特権を持つ必要があります、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]ウィザードまたはコマンドラインを使用してをインストールするかどうかのあるかにかかわらず、します。  

### <a name="typical-vs-custom-installation"></a>標準セットアップとカスタム インストール  
このセクションには、インストールの種類と各オプションでインストールされている機能が一覧表示します。  
  
-   **標準**と**完了**オプションは、関連付けられているデータ プロバイダーとすべてのアダプターをインストールします。 インストールする特定のアダプターを選択するオプションがありません。  
  
-   **カスタム**オプションは、関連付けられているデータ プロバイダーと 1 つまたは複数のアダプターをインストールします。 インストールするには、どのアダプターを選択できます。 データ プロバイダーをインストールする場合は、また、対応するアダプターをインストールする必要があります。 ただし、対応するデータ プロバイダーをインストールしなくても、アダプターをインストールすることができます。 これには、展開、 **ADO プロバイダー**ノード、およびインストールしたくないプロバイダーを選択します。 参照してください[対話モードで BizTalk Adapter をインストールするパック](#BKMK_Install_wizard)です。  
  
     たとえば、インストールする場合、[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]もインストールする必要があります、[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]です。 ただし、インストールすることができます、[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]インストールしなくても、[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]です。  
  
<a name="BKMK_Install_Scenarios"></a>   
### <a name="scenarios-for-installing-the-biztalk-adapter-pack-on-32-bit-and-64-bit-platforms"></a>32 ビットおよび 64 ビット プラットフォームでは、BizTalk Adapter Pack をインストールするためのシナリオ  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]に使用できます。 
  
-   [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] デザイン時 (場合、LOB アプリケーションでの操作のメタデータの生成)
  
-   BizTalk Server 管理コンソール デザイン時 (物理ポートの作成)
  
    > [!NOTE]
    >  BizTalk Server 管理コンソールは、32 ビット Microsoft 管理コンソール (MMC) アプリケーションとして実行されます。  
  
-   BizTalk ランタイム (ときに送信し、LOB アプリケーションからメッセージを受信)

これらすべての検索の 1 台のコンピューターを使用したり、別のコンピューターを使用することができます。 両方[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]と BizTalk MMC は 32 ビット プロセスが、32 ビットをインストールする必要があります[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]デザイン時のタスクを完了するコンピューターにします。 

#### <a name="scenarios-for-installing-the-biztalk-adapter-pack-on-a-32-bit-platform"></a>32 ビット プラットフォーム上で、BizTalk Adapter Pack をインストールするためのシナリオ  
 32 ビット プラットフォームでサポートされるシナリオは次のとおりです。  
  
|Visual Studio のデザイン時の|MMC の BizTalk のデザイン時|Biztalk ランタイム|Visual Studio のデザイン時およびデザイン時の BizTalk MMC + BizTalk 実行時間|  
|---|---|---|---|  
|がインストール 32 ビット[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]です。<br /><br /> がインストール 32 ビット[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]です。<br /><br /> 32 ビット LOB クライアントとその他の必要な Dll をインストールします。|がインストール 32 ビット[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]です。<br /><br /> がインストール 32 ビット[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]です。<br /><br /> 32 ビット LOB クライアントとその他の必要な Dll をインストールします。|がインストール 32 ビット[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]です。<br /><br /> がインストール 32 ビット[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]です。<br /><br /> 32 ビット LOB クライアントとその他の必要な Dll をインストールします。|がインストール 32 ビット[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]です。<br /><br /> がインストール 32 ビット[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]です。<br /><br /> 32 ビット LOB クライアントとその他の必要な Dll をインストールします。|  
  
#### <a name="scenarios-for-installing-the-biztalk-adapter-pack-on-a-64-bit-platform"></a>64 ビット プラットフォーム上で、BizTalk Adapter Pack をインストールするためのシナリオ  
 64 ビット プラットフォームでサポートされるシナリオは次のとおりです。  
  
|Visual Studio のデザイン時の|MMC の BizTalk のデザイン時|Biztalk ランタイム|Visual Studio のデザイン時およびデザイン時の BizTalk MMC + BizTalk 実行時間|  
|---|---|---|---|  
|がインストール 64 ビット[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]です。<br /><br /> がインストール 32 ビット[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]です。<br /><br /> 32 ビット LOB クライアントとその他の必要な Dll をインストールします。|がインストール 64 ビット[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]です。<br /><br /> がインストール 32 ビット[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]です。<br /><br /> 32 ビット LOB クライアントとその他の必要な Dll をインストールします。|**32 ビット BizTalk プロセス**:<br /><br /> がインストール 64 ビット[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]です。<br /><br /> がインストール 32 ビット[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]です。<br /><br /> 32 ビット LOB クライアントとその他の必要な Dll をインストールします。<br /><br /> **64 ビットの BizTalk プロセス**:<br /><br /> がインストール 64 ビット[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]です。<br /><br /> がインストール 64 ビット[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]です。<br /><br /> -64 ビット LOB クライアントとその他の必要な Dll をインストールします。|**32 ビット BizTalk プロセス**:<br /><br /> がインストール 64 ビット[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]です。<br /><br /> がインストール 32 ビット[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]です。<br /><br /> 32 ビット LOB クライアントとその他の必要な Dll をインストールします。<br /><br /> **64 ビットの BizTalk プロセス**:<br /><br /> がインストール 64 ビット[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]です。<br /><br /> がインストール 64 ビット[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]です。<br /><br /> -64 ビット LOB クライアントとその他の必要な Dll をインストールします。<br /><br /> がインストール 32 ビット[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]です。<br /><br /> 32 ビット LOB クライアントとその他の必要な Dll をインストールします。|  
  
> [!NOTE]
>  デザイン時のタスクを実行する任意のコンピューターでいずれかの操作を使用して[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]BizTalk MMC で、32 ビットをインストールする必要がありますまたは[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]です。  
  
<a name="BKMK_Install_wizard"></a>   
### <a name="installing-the-biztalk-adapter-pack-in-interactive-mode"></a>対話モードで BizTalk Adapter Pack をインストールします。  
次の手順に従って、インストールを完了、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]セットアップ ウィザードを使用します。  
  
1.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]インストール メディアで、実行**Setup.exe**です。  
  
2.  選択**Microsoft BizTalk Adapters インストール**です。 次のウィンドウで次のように選択します。 **Microsoft BizTalk Adapter Pack のインストール**または**インストール Microsoft BizTalk Adapter Pack (x64)** プラットフォームに応じて、します。  
  
    > [!NOTE]
    >  インストールする場合、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]バーチャル マシンで、セットアップ ウィザードは使用可能なディスク容量については、セットアップがチェックされることを通知 ダイアログ ボックス続行されません可能性があります。 このような場合、サイレント インストール オプションを使用することをお勧めします。 参照してください[サイレント モードで BizTalk Adapter Pack をインストールする](#BKMK_SilentInst)(」を参照)。  
  
3.  [ようこそ] 画面で、次のように選択します。**次**です。  
  
4.  使用許諾契約書 (EULA) に同意し、**次**です。  
  
5.  **セットアップの種類を選択して**:  
  
    -   最も一般的な機能をインストールする選択**標準**です。  
  
    -   インストールするアダプターを選択するには、次のように選択します。**カスタム**、し、次の手順に進みます。  
  
    -   すべての機能をインストールする選択**完了**です。  
  
        > [!IMPORTANT]
        >  エンタープライズ アプリケーションとのインターフェイスで、選択に使用するアダプターのみをインストールする、**カスタム**インストールします。  
  
6. **必要な**カスタム インストールを選択した場合のみです。 選択した場合、**標準**または**完了**インストールし、この手順をスキップし、手順 7. に進みます。  
  
    1.  **カスタム セットアップ**、展開**ベース アダプター**に利用可能なアダプターを参照してください。  
  
    2.  必要のないアダプターの場合、アダプターの横にあるアイコンを選択し、**全体の機能は使用できません**です。  
  
    3.  展開**ADO プロバイダー**、しをインストールしたくないプロバイダーを選択します。  
  
    4.  **[次へ]** を選択します。  
  
7.  **[インストール]** を選択します。  
  
8.  **カスタマー エクスペリエンス向上プログラム**、登録することもできます。 登録する場合は、Microsoft と、次のデータを共有できます。  
  
    -   インストールしているコンピューターのハードウェアに関連するデータ、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]です。  
  
    -   使用するエンタープライズ アプリケーションのバージョンに関連するデータ、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]です。  
  
     **[OK]** を選択します。 [CEIP](http://go.microsoft.com/fwlink/p/?LinkId=144699)詳しく説明します。  
  
    > [!NOTE]
    >  修復モードで、セットアップを実行して、この設定を変更することが常に**プログラム**です。  
  
9. **[完了]** を選択します。  
  
<a name="BKMK_SilentInst"></a>   
### <a name="installing-the-biztalk-adapter-pack-in-silent-mode"></a>サイレント モードで BizTalk Adapter Pack をインストールします。  
 使用して、 **msiexec**サイレント インストールを実行するコマンド。 Msiexec コマンドの一部としてインストールする個々 のコンポーネントを入力します。 次の表に、内の各コンポーネントの値、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]です。 特定のコンポーネントをインストール (または削除) するのにには、これらの値を使用します。 ホスト インスタンスをインストール (または削除) するには、複数のコンポーネントは、コンマ区切りでこれらの値の組み合わせを使用できます。  
  
|コンポーネント名|コマンド ライン プロパティの対応する値|  
|---|---|  
|[!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)]|DbFeature|  
|[!INCLUDE[adapteroraclebusinessshort](../includes/adapteroraclebusinessshort-md.md)]|OracleEBSFeature|  
|[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]|SapBaseAdapterFeature|  
|[!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)]|SiebelBaseAdapterFeature|  
|[!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)]|SqlFeature|  
|[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]|SapAdoFeature<br /><br /> **注**: インストールする場合にのみ、この値を指定する必要があります、[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]もします。|  
|[!INCLUDE[adoprovidersiebelshort](../includes/adoprovidersiebelshort-md.md)]|SiebelAdoFeature<br /><br /> **注**: インストールする場合にのみ、この値を指定する必要があります、[!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)]もします。|  
|すべてのコンポーネント|ALL|  
  
> [!IMPORTANT]
>  機能名は大文字小文字を区別します。  
  
 次の手順は、のサイレント インストールを完了する方法を示します[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]さまざまなコンポーネントです。  
  
##### <a name="install-in-silent-mode"></a>サイレント モードでインストールします。  
  
1.  コマンド プロンプトを開きに移動、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]でルート、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]インストールします。  
  
2.  インストールする内容に基づいて、次のコマンドを実行します。  
  
    > [!NOTE]
    >  X64 ベースのプラットフォームでのサイレント インストールには、置換`AdaptersSetup.msi`で`AdaptersSetup64.msi`次のコマンドにします。  
  
    -   アダプターは、.NET Framework データ プロバイダーを含む、すべてをインストールする完全なインストールを実行するには、次のように入力します。  
  
        ```  
        msiexec /i AdaptersSetup.msi /qn ADDLOCAL=ALL  
        ```  
  
    -   のみをインストールする、[!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)]種類。  
  
        ```  
        msiexec /i AdaptersSetup.msi /qn ADDLOCAL=DbFeature  
        ```  
  
    -   のみをインストールする、[!INCLUDE[adapteroraclebusinessshort](../includes/adapteroraclebusinessshort-md.md)]種類。  
  
        ```  
        msiexec /i AdaptersSetup.msi /qn ADDLOCAL=OracleEBSFeature  
        ```  
  
    -   のみをインストールする、[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]種類。  
  
        ```  
        msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SapBaseAdapterFeature  
        ```  
  
    -   インストールする、[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]と共に[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]種類。  
  
        ```  
        msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SapBaseAdapterFeature,SapAdoFeature  
        ```  
  
    -   のみをインストールする、[!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)]種類。  
  
        ```  
        msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SiebelBaseAdapterFeature  
        ```  
  
    -   インストールする、[!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)]と共に[!INCLUDE[adoprovidersiebelshort](../includes/adoprovidersiebelshort-md.md)]種類。  
  
        ```  
        msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SiebelBaseAdapterFeature,SiebelAdoFeature  
        ```  
  
    -   のみをインストールする、[!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)]種類。  
  
        ```  
        msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SqlFeature  
        ```  
  
    -   すべてのベース アダプターをインストールするには、次のように入力します。  
  
        ```  
        msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SapBaseAdapterFeature,SiebelBaseAdapterFeature,DbFeature,OracleEBSFeature,SqlFeature  
        ```  
  
    -   2 つの .NET Framework データ プロバイダーをインストールするには、次のように入力します。  
  
        ```  
        msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SapAdoFeature,SiebelAdoFeature  
        ```  
  
    -   コンマで区切って、コンポーネントでカスタム インストールのすべての型。 たとえば、インストールするため、[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]で、 [!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]、および[!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)]型。  
  
        ```  
        msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SapBaseAdapterFeature,SapAdoFeature,SiebelBaseAdapterFeature  
        ```  
  
    -   CEIP をサイレント インストールの一部として登録することもできます。 型:  
  
        ```  
        msiexec /i AdaptersSetup.msi /qn CEIP_OPTIN=true  
        ```  
  
         既定では、オプションは false です。 
  
        > [!IMPORTANT]
        >  インストール中に、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]サイレント モードでの評価版、CEIP の既定のオプションが true です。  
  
     Msiexec コマンドの種類の詳細については`msiexec`キーを押して、コマンド ライン`ENTER`です。 移動または[ http://go.microsoft.com/fwlink/p/?LinkId=103199](http://go.microsoft.com/fwlink/p/?LinkId=103199)です。
  
<a name="BKMK_PostInst"></a>   
### <a name="after-installing-the-biztalk-adapter-pack"></a>BizTalk Adapter Pack をインストールした後  
 インストールした後、次のタスクを実行する必要があります、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]と、各アダプターを実行する操作に基づきます。  
  
-   [新しい Oracle.DataAccess.dll バージョンを使用する Oracle データベース アダプター構成](#BKMK_ConfigNewOracleDLL)OracleDB 構成ファイルにします。  
  
-   [SQL Server データベース オブジェクトを作成する (SAP アダプター) の場合のみ](#BKMK_CreateSQLServer)を SAP システムでトランザクションの Rfc (tRFCs) を呼び出します。  
  
-   [アダプターのバインドを登録](#BKMK_Register_Bindings)とそのためには、セットアップ ウィザードが失敗した場合に、.NET Framework データ プロバイダー。  
  
-   [公開キーとバージョン特定](#BKMK_PubKey)異なるアダプター ファイルのです。  
  
-   [インストールのカスタム Rfc](#BKMK_InstallCustomRFC)をインストールする場合、[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]です。  
  
<a name="BKMK_ConfigNewOracleDLL"></a>   
#### <a name="configure-the-oracle-database-adapter-to-use-a-newer-oracledataaccessdll-version"></a>新しい Oracle.DataAccess.dll バージョンを使用する Oracle データベース アダプターを構成します。  
 Wcf-oracledb アダプターを使用または生成されたアダプターを使用する Visual Studio を使用するためのポートを構成するときに、アダプターが Oracle.DataAccess.dll バージョン 2.111.7.0 必要があること、メッセージが表示されます。 このメッセージを解決するには、サポートされている Oracle.DataAccess.dll バージョンをインストール (を参照してください[バージョンのリストをサポート](https://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-and-enterprise-systems.aspx))、し、更新、 `bindingRedirect` OracleDB 構成ファイル内の要素。 手順を実行します。  
  
1.  BizTalk Server では、次のフォルダーに移動します。  
  
     *ドライブ*: \Program Files\Microsoft BizTalk Adapter Pack (x64) \bin  
  
     *ドライブ*: \Program Files (x86) \Microsoft BizTalk Adapter Pack\bin  
  
2.  Microsoft.Adapters.OracleDB.config ファイルを開きます。  
  
3.  次のセクションを見つけて次コピー/貼り付け。  
  
    ```  
    <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
              <dependentAssembly>  
                        <assemblyIdentity name="Oracle.DataAccess" publicKeyToken="89b483f429c47342" culture="neutral" />  
                        <bindingRedirect oldVersion="2.111.7.00" newVersion="2.112.1.00"/>  
              </dependentAssembly>  
    </assemblyBinding>  
  
    ```  
  
    > [!NOTE]
    >  この例では設定*newVersion* 2.112.1.00 にします。 この値をインストールしたバージョンに設定します。  
  
> [!IMPORTANT]
>  -   このグループに複数の BizTalk Server がある場合は、グループ内のすべての BizTalk サーバーでこの変更を行います。  
> -   *NewVersion* Oracle.DataAccess.dll ファイルをコンピューターにインストールされているのバージョンに基づく更新する値が必要です。  Oracle.DataAccess.dll は、Oracle からインストールする Oracle クライアントに含まれています。  される Oracle クライアント バージョンをインストールする必要がありますのみ[BizTalk Adapter Pack でサポートされている](http://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-and-enterprise-systems.aspx)です。  
  
<a name="BKMK_CreateSQLServer"></a>   
#### <a name="create-sql-server-database-objects-only-for-the-sap-adapter"></a>(SAP アダプター) の場合のみ SQL Server データベース オブジェクトを作成します。  
 SAP システムで tRFCs を呼び出し、実行、 *SapAdapter DbScript-Install.sql* SQL スクリプト。 このスクリプトがインストールされている、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]インストールし、SQL Server でデータベース オブジェクトを作成します。 インストールされている通常の\<インストール ドライブ\>: \Program Files\Microsoft[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]です。 TRFCs を呼び出すため、アダプターを使用しているときにそのデータベース名を入力する限り、任意の SQL Server データベースに対してこのスクリプトを実行できます。  
  
<a name="BKMK_Register_Bindings"></a>   
#### <a name="register-the-adapter-bindings"></a>アダプターのバインドを登録します。  
 中に、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]インストール、セットアップ ウィザードがアダプターのバインドが、または、.NET Framework Data Provider for mySAP Business Suite を登録に失敗する可能性がありますが、アダプターのインストールがセットアップが続行されます。 Windows Communication Foundation (WCF) のインストールに問題があります[!INCLUDE[afproductnamelong](../includes/afproductnamelong-md.md)]インストール、または壊れている可能性が machine.config ファイルです。  
  
次の手順を完了*のみ*machine.config ファイルに、アダプターのバインドまたは .NET Framework データ プロバイダーを登録するセットアップ ウィザードが失敗した場合。  
  
###### <a name="register-the-adapter-bindings-or-the-net-framework-data-providers"></a>アダプターのバインドまたは .NET Framework データ プロバイダーを登録します。  
  
1.  コンピューター上の machine.config ファイルに移動します。 たとえば、32 ビット プラットフォームで、machine.config は下にある使用可能な\<システム ドライブ\>: \WINDOWS\Microsoft.NET\Framework\\< バージョン\>\CONFIG です。  
  
2.  テキスト エディターを使用してファイルを開きます。  
  
3.  アダプターのバインドを登録します。  
  
    1.  検索、`system.serviceModel`要素、およびその下にある次の追加。  
  
        ```  
        <client>  
          <endpoint binding="sapBinding" contract="IMetadataExchange" name="sap" />  
          <endpoint binding="siebelBinding" contract="IMetadataExchange" name="siebel" />  
          <endpoint binding="oracleDBBinding" contract="IMetadataExchange" name="oracleDb" />  
          <endpoint binding="oracleEBSBinding" contract="IMetadataExchange" name="oracleEBS" />  
          <endpoint binding="sqlBinding" contract="IMetadataExchange" name="mssql" />  
        </client>  
        ```  
  
    2.  検索、 `bindingElementExtensions` system.serviceModel\extensions 下にある要素。  
  
    3.  不足しているアダプターのバインドを探します。 次のセクションを追加、`bindingElementExtensions`バインドに応じて、不足しているアダプターのノードです。 セットアップ ウィザードに任意登録に失敗した場合、すべてのバインドを登録する必要があります。  
  
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
  
    4.  検索、 `bindingExtensions` system.serviceModel\extensions 下にある要素。  
  
    5.  不足しているアダプターのバインドを探します。 次のセクションを追加、`bindingExtensions`バインドに応じて、不足しているアダプターのノードです。 セットアップ ウィザードに任意登録に失敗した場合、すべてのバインドを登録する必要があります。  
  
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
    >  公開キーを確認する方法については、次を参照してください。[公開キーとバージョン特定](#BKMK_PubKey)です。  
  
4.  .NET Framework データ プロバイダーを登録します。  
  
    1.  検索、 `DbProviderFactories` system.data ノードの下の要素。  
  
    2.  不足している .NET Framework データ プロバイダーを探します。 下にある次のセクションを追加、`DbProviderFactories`ノード、不足しているプロバイダーによっても異なります。 セットアップ ウィザードに任意登録に失敗した場合は、すべてのプロバイダーを登録する必要があります。  
  
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
  
5.  machine.config ファイルを保存して閉じます。  
  
<a name="BKMK_PubKey"></a>   
#### <a name="determine-the-public-key-and-version"></a>公開キーとバージョンを決定します。  
 公開キーと、アダプターまたは .NET Framework Data Provider のバージョンを確認するのには、次の手順を実行します。  
  
###### <a name="determine-the-public-key"></a>公開キーを確認します。  
  
1.  Windows ディレクトリの通常 C:\WINDOWS\assembly に移動します。  
  
2.  対象の公開キーを指定してを選択し、DLL を右クリックして**プロパティ**です。 次の表は、各アダプターおよびプロバイダーの Dll の名前を示します。  
  
    |アダプターと .NET Framework データ プロバイダー|DLL の名前|  
    |---|---|  
    |[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]|Microsoft.Adapters.SAP|  
    |[!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)]|Microsoft.Adapters.Siebel|  
    |[!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)]|Microsoft.Adapters.OracleDB|  
    |[!INCLUDE[adapteroraclebusinessshort](../includes/adapteroraclebusinessshort-md.md)]|Microsoft.Adapters.OracleEBS|  
    |[!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)]|Microsoft.Adapters.Sql.dll|  
    |[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]|Microsoft.Data.SAPClient|  
    |[!INCLUDE[adoprovidersiebelshort](../includes/adoprovidersiebelshort-md.md)]|Microsoft.Data.SiebelClient|  
  
3.  **全般** タブで、**公開キー トークンの**値は、DLL の公開キー。 **バージョン**値は、DLL のバージョン番号。  
  
4.  公開キーをコピーし、**キャンセル**です。  
  
<a name="BKMK_InstallCustomRFC"></a>   
#### <a name="install-the-custom-rfcs"></a>カスタム Rfc をインストールします。  
 のみを使用する場合は、このタスクを実行する必要があります、[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]です。 カスタムの Rfc をインストールする方法の詳細については、次を参照してください。[カスタム Rfc のインストール](../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md)で、[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]ドキュメント。 
  
> [!IMPORTANT]
>  提供されるカスタム Rfc の以前のバージョンを使用しているかどうか、 [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]、このリリースで提供、Rfc にアップグレードする必要があります。 以前の Rfc を削除することで、このリリースに付属し、Rfc をインストールします。  

## <a name="installing-the-enterprise-applications"></a>エンタープライズ アプリケーションをインストールします。  
手順と、別のエンタープライズの LOB システムをインストールするガイダンスお recommendnd、特定のインストールを使用する手順について説明します。 存在する場合は、特定の構成の変更は、アダプターのドキュメントを参照してください。   

## <a name="installation-and-post-installation-checklist"></a>インストールおよびインストール後のチェックリスト  
  
-   すべてをインストールするかどうかを確認、[ソフトウェアの前提条件](#BKMK_Prereqs)正しいインストール オプションを使用します。
  
-   サポートされている、企業の LOB アプリケーションをインストールしたコンピューターにインストールされているバージョンであることを確認してください、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]です。 参照してください[エンタープライズ アプリケーションのバージョンがサポートされている](#BKMK_SuppLOB)です。  
  
-   LOB システム接続するエンタープライズ用のアダプターのみをインストールするには、インストールしたを確認してください、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]を使用して、**カスタム**インストール オプションです。 インストールしていないことを確認、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]を使用して、**完了**インストール オプションです。 参照してください[BizTalk Adapter Pack をインストールする](#BKMK_Install_Adap)です。  
  
-   SAP システムを使用して、tRFC の呼び出しを作成するかどうか、 [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]、SQL Server データベースで、必要なテーブルを作成するかどうかを確認します。 参照してください[BizTalk Adapter Pack をインストールした後](#BKMK_PostInst)です。
  
-   実行中に、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]セットアップ ウィザードで、バインドを登録できませんでしたを示すエラー メッセージを取得可能性があります。 場合は、手動で登録します。 参照してください[BizTalk Adapter Pack をインストールした後](#BKMK_PostInst)です。  
  
-   インストールする場合、[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]の一部として、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]インストール、SAP システムにカスタムの Rfc をインストールするかどうかを確認します。 参照してください[BizTalk Adapter Pack をインストールした後](#BKMK_PostInst)です。  
  
<a name="BKMK_Modify_Adap"></a>   
## <a name="change-the-biztalk-adapter-pack-installation"></a>BizTalk Adapter Pack のインストールを変更します。  
 変更するのには、次の手順を完了、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]インストールします。 あるかどうかを確認、[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]を変更するセットアップ ウィザードを実行する前にインストールされている、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]インストールします。  
  
 変更することができます、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]対話モード (セットアップ ウィザード) で、またはサイレント モード (コマンド ライン) でインストールします。
  
#### <a name="change-the-bap-installation-in-interactive-mode"></a>対話モードで BAP インストールを変更します。  
  
1.  BizTalk Server 管理者グループのメンバーであるアカウントを使用してサインインします。  
  
2.  **プログラムと機能****プログラムのアンインストール**です。  
  
3.  右クリック**Microsoft BizTalk Adapter Pack**、し、**変更**です。  
  
4.  [ようこそ] 画面で、次のように選択します。**次**です。  
  
5.  **変更、修復、または削除インストール**:  
  
    -   インストールするコンポーネントを選択する**変更**し、手順 6. に進みます。  
  
    -   最新のインストールのエラーを修復するには、次のように選択します。**修復**手順 7. に進みます。  
  
    -   Microsoft を削除する[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]、コンピューターから選択**削除**し、手順 10 に進みます。  
  
6.  場合は、インストールを変更することを選択します。  
  
    -   展開して、 **Microsoft BizTalk Adapter Pack**ノード ベース アダプター、.NET Framework データ プロバイダー、またはその両方をインストールするかを選択します。  
  
    -   展開して、**ベース アダプター**ノードすべてのアダプターまたは特定のアダプターをインストールするかを選択します。  
  
    -   展開して、 **ADO プロバイダー**ノードすべてのプロバイダーまたは特定のプロバイダーをインストールするかを選択します。  
  
    -   **[次へ]** を選択します。  
  
    -   選択**変更**、し、**完了**です。  
  
7.  インストールを修復して、選択した場合、 **Microsoft BizTalk Adapter Pack の修復の準備完了**ダイアログ ボックスで、**修復**です。 ウィザードでは、インストールの修復を開始します。  
  
8.  必要に応じて、ユーザーの設定を変更、CEIP のオプトインに関連し、 **OK**です。 
  
9. **[完了]** を選択します。  
  
10. アダプターを削除した場合、 **Microsoft BizTalk Adapter Pack を削除する準備ができて**ダイアログ ボックスで、**削除**、し、**完了**です。  
  
#### <a name="change-the-bap-installation-in-silent-mode"></a>サイレント モードで BAP インストールを変更します。  
  
1.  コマンド プロンプトを開きのルート ディレクトリに移動、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]インストーラーです。  
  
2.  次のようなコマンドを実行します。  
  
    > [!NOTE]
    >  変更する、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]次のコマンドでの x64 ベースのプラットフォームにサイレント モードでインストールを交換して`AdaptersSetup.msi`で`AdaptersSetup64.msi`です。  
  
    ```  
    msiexec /i AdaptersSetup.msi /qn REMOVE=DbFeature ADDLOCAL=SapBaseAdapterFeature  
    ```  
  
     このコマンドを削除、[!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)]をインストールし、[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]です。  
  
     別の値を使用して、`REMOVE`と`ADDLOCAL`プロパティを追加または特定のコンポーネントを削除することができます。 内のテーブルを参照してください[サイレント モードで BizTalk Adapter Pack をインストールする](#BKMK_SilentInst)(このトピック) でこれらのプロパティを使用できる値についてはします。  
  
     Msiexec コマンドの一部として、/f オプションを使用して、サイレントの修復を実行することもできます。 以下に例を示します。  
  
    ```  
    msiexec /i AdaptersSetup.msi /qn /f  
    ```  
  
     さまざまなさまざまな組み合わせを使用するには、/f オプションを使用します。 Msiexec コマンドの種類の詳細については`msiexec`キーを押して、コマンド ライン`ENTER`です。 移動または[ http://go.microsoft.com/fwlink/p/?LinkId=103199](http://go.microsoft.com/fwlink/p/?LinkId=103199)です。  
  
    > [!IMPORTANT]
    >  変更中に、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]サイレント モードでインストールで CEIP を有効または無効にするための設定を変更することはできません。 True または false に、CEIP_OPTIN を明示的に設定した場合でも、インストールは残りの中に選択した環境を設定します。  
  
<a name="BKMK_Remove_Adap"></a>   
## <a name="removing-the-biztalk-adapter-pack"></a>BizTalk アダプター パックを削除します。  
  
> [!IMPORTANT]
>  TRFC 機能を使用する SQL Server データベースでテーブルを作成した場合、 [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]、削除する前に手動で削除する必要があります、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]です。 [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]インストールは、通常は SapAdapter DbScript-Uninstall.sql ファイルをコピー\<インストール ドライブ\>: \Program Files\Microsoft[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]です。 作成したテーブルを削除するには、このファイルを実行します。  
  
次の手順を削除する、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]コンピューターからです。 あるかどうかを確認、[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]アダプターを削除するセットアップ ウィザードを実行する前にインストールします。  
  
 削除することができます、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]対話モード (セットアップ ウィザード) またはサイレント モード (コマンド ライン)。
  
#### <a name="uninstall-the-biztalk-adapter-pack-in-interactive-mode"></a>対話モードで BizTalk Adapter Pack をアンインストールします。  
  
1.  **プログラムと機能****プログラムのアンインストール**です。  
  
2.  右クリック**Microsoft BizTalk Adapter Pack**、し、**アンインストール**です。  
  
#### <a name="uninstall-the-biztalk-adapter-pack-in-silent-mode"></a>サイレント モードで BizTalk Adapter Pack をアンインストールします。  
  
1.  コマンド プロンプトを開きのルート ディレクトリに移動、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]インストーラーです。  
  
2.  次のコマンドを実行します。  
  
    > [!NOTE]
    >  削除する、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]サイレント モードで、次のコマンドの x64 ベースのプラットフォーム上で置き換える`AdaptersSetup.msi`で`AdaptersSetup64.msi`です。  
  
    ```  
    msiexec /i AdaptersSetup.msi /qn REMOVE=DbFeature  
    ```  
  
     このコマンドを削除、[!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)]から、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]インストールします。  
  
     異なる値を提供することによって、`REMOVE`プロパティから特定のコンポーネントを削除することができます、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]インストールします。 内のテーブルを参照してください[サイレント モードで BizTalk Adapter Pack をインストールする](#BKMK_SilentInst)(このトピック) でこのプロパティの使用できる値についてはします。  
  
     完全に削除する、 [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]、次のコマンドを実行します。  
  
    ```  
    msiexec /x AdaptersSetup.msi /qn  
    ```  
  
     Msiexec コマンドの種類の詳細については`msiexec`キーを押して、コマンド ライン`ENTER`です。 移動または[ http://go.microsoft.com/fwlink/p/?LinkId=103199](http://go.microsoft.com/fwlink/p/?LinkId=103199)です。
  
<a name="BKMK_PostRemove"></a>   
### <a name="after-removing-the-biztalk-adapter-pack"></a>BizTalk Adapter Pack を削除した後  
 削除した後、次の手順を実行する必要があります、 [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]:  
  
-   そのためには、セットアップ ウィザードが失敗した場合、アダプターのバインドまたは .NET Framework Data Provider の登録を削除します。
  
-   インストールする場合は、カスタムの Rfc を削除します [!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]
  
<a name="BKMK_Remove_Binding"></a>   
#### <a name="remove-the-bindings-or-the-net-framework-data-provider-registration"></a>バインドまたは .NET Framework データ プロバイダーの登録を削除します。  
 次の手順を完了*のみ*machine.config ファイルから、アダプターのバインドまたは .NET Framework Data Provider の登録を削除するセットアップ ウィザードが失敗した場合。  
  
###### <a name="remove-the-adapter-bindings-or-net-framework-data-provider-registration"></a>アダプターのバインドまたは .NET Framework Data Provider の登録を削除します。  
  
1.  コンピューター上の machine.config ファイルに移動します。 たとえば、32 ビット プラットフォームで、machine.config は下にある使用可能な\<システム ドライブ\>: \WINDOWS\Microsoft.NET\Framework\\< バージョン\>\CONFIG です。  
  
2.  テキスト エディターを使用してファイルを開きます。  
  
3.  アダプターのバインドの登録を削除します。  
  
    1.  検索、`system.serviceModel`要素、および要素の下には、次の削除。  
  
        ```  
        <client>  
          <endpoint binding="sapBinding" contract="IMetadataExchange" name="sap" />  
          <endpoint binding="siebelBinding" contract="IMetadataExchange" name="siebel" />  
          <endpoint binding="oracleDBBinding" contract="IMetadataExchange" name="oracleDb" />  
          <endpoint binding="OracleEBSBinding" contract="IMetadataExchange" name="oracleEBS" />  
          <endpoint binding="sqlBinding" contract="IMetadataExchange" name="mssql" />  
        </client>  
  
        ```  
  
    2.  検索、 `bindingElementExtensions` system.serviceModel\extensions 下にある要素。  
  
    3.  次のセクションでは、削除、`bindingElementExtensions`バインドに応じて、使用可能なアダプターのノードです。 セットアップ ウィザードをすべて削除に失敗する場合は、すべてのバインディングを削除する必要があります。  
  
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
  
    4.  検索、 `bindingExtensions` system.serviceModel\extensions 下にある要素。  
  
    5.  次のセクションでは、削除、`bindingExtensions`バインドに応じて、使用可能なアダプターのノードです。 セットアップ ウィザードをすべて削除に失敗する場合は、すべてのバインディングを削除する必要があります。  
  
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
  
4.  .NET Framework データ プロバイダーの登録を削除します。  
  
    -   検索、 `DbProviderFactories` system.data ノードの下の要素。  
  
    -   まだ登録されている .NET Framework データ プロバイダーを探します。 次のセクションでは、削除、`DbProviderFactories`によっては、既存の .NET Framework データ プロバイダーのノード。 存在する場合は、すべてのプロバイダーを削除する必要があります。  
  
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
  
5.  machine.config ファイルを保存して閉じます。  
  
<a name="BKMK_Remove_SAP_Pro"></a>   
#### <a name="remove-the-custom-rfcs"></a>カスタム Rfc を削除します。  
SAP システムにインストールされているカスタム Rfc を削除するには、この手順を完了します。 参照してください[インストールまたは削除するカスタム Rfc](../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md)です。  
  
## <a name="troubleshoot-biztalk-adapter-pack-installation"></a>BizTalk Adapter Pack のインストールをトラブルシューティングします。  
 インストールするときに直面する問題のいくつかは次のとおり[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]です。 包括のインストールに関連する問題の一覧を表示するを参照してください**トラブルシューティング**アダプターごとにトピックです。  
  
-   **64 ビット コンピューターでセットアップを実行してエラーが発生するスキーマ ファイルへのアクセス中には**  
  
     [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]セットアップへのアクセス中にエラーをスローする、 **Microsoft.Adapters *。\<AdapterName\>*_schema.xml**ファイルが、アダプターのインストールを続行します。  
  
     **原因**  
  
     場合は 32 ビットと 64 ビットの両方のバージョン、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]がインストールされている同じコンピューター両方で使用されるターゲットのスキーマ ファイルは同じです。 その結果、ファイルは、32 ビットでインストール[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]64 ビットのインストーラーが、アクセスしようとするときに、IIS によって使用されている可能性があります。  
  
     **解決方法**  
  
     手動でコピー、 **Microsoft.Adapters *。\<AdapterName\>*_schema.xml**ファイルから`C:\Program Files\Microsoft BizTalk Adapter Pack(x64)\IIS Schemas`"に`C:\Windows\System32\inetsrv\config\schema`です。  