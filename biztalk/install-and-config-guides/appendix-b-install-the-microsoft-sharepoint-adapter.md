---
title: "付録 b: Microsoft SharePoint アダプターのインストール |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f44c6e0a-dcce-4444-8cac-bd403c81a233
caps.latest.revision: "19"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f67c888d844182daa6ecdc8e65e13487b8b337f1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="appendix-b-install-the-microsoft-sharepoint-adapter"></a>付録 B: Microsoft SharePoint アダプターのインストール
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] には、[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] との間でメッセージを送受信できる [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] アダプターが含まれています。 

このトピックでは、SharePoint アダプターについて説明します。  [BizTalk Server 2016](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md) および [BizTalk Server 2013 R2 / 2013](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2013-and-2013-r2.md) のソフトウェア要件には、サポートされている SharePoint バージョンがリストされています。

## <a name="sharepoint-adapter-in-biztalk-server-2016"></a>BizTalk Server 2016 の SharePoint アダプター

BizTalk Server セットアップでは、ファイル アダプター、FTP アダプター、および他の既定のアダプターなど、CSOM 再頒布可能パッケージが自動的にインストールされます。 

SSOM オプションは削除されており、使用できません。


## <a name="sharepoint-adapter-in-biztalk-server-2013-and-r2"></a>BizTalk Server 2013 および R2 の SharePoint アダプター
[!INCLUDE[bts2013r2_md](../includes/bts2013r2-md.md)] および [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 2013 には、SharePoint アダプターの 2 つのオプションがあります。

|SharePoint オブジェクト モデル|説明|  
|-------------------------|-----------------|  
|CSOM - [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] アダプター|**推奨**。 BizTalk Server セットアップでは、ファイル アダプター、FTP アダプター、および他の既定のアダプターなど、CSOM 再頒布可能パッケージが自動的にインストールされます。 <br/><br/>SharePoint コンピューターに関するインストール要件はありません。|  
|SSOM - [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] Web サービス|**非推奨**。 SharePoint コンピューターで、BizTalk Server セットアップを実行し、[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] アダプター**のみ**を選択します。 このセットアップでは、BizTalk Server の SharePoint アダプターへの通信を処理する IIS Web サービスをインストールします。 <br/><br/>多くの環境では、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] と [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] は別のコンピューターにインストールされます。|  

##  <a name="BKMK_Before"></a> インストールの準備  

*  [!INCLUDE[bts2013r2_md](../includes/bts2013r2-md.md)] または 2013 および [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] が同じコンピューターにインストールされていれば、[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] の SSOM と CSOM コンポーネントの両方をインストールできます。  
  
* BAM ポータルは、32 ビット モードでのみ動作します。 BAM ポータルを 64 ビット コンピューターにインストールする場合は、ASP.NET 2.0 が 32 ビットで有効になっていて、IIS アプリケーション プールが 32 ビット モードであることを確認します。 これを行うには :  
  
    -   **ASP.NET**: IIS マネージャーを開き、**BAM ポータル** Web サイトをクリックし、**[ハンドラー マッピング]** をダブルクリックします。 **[有効]** の一覧に、**PageHandlerFactory-ISAPI-2.0** があることを確認します。  
  
    -   **アプリケーション プール**: IIS マネージャーを開き、**[アプリケーション プール]**、**[BAMAppPool]**、**[詳細設定]** の順にクリックします。 **[32 ビット アプリケーションの有効化]** で、**[True]** を選択します。  
  
* 単一サーバーの [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] と [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] インストールを作成する場合でも、[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] をインストールするときに、**[サーバー ファーム]** オプションをクリックします。 インストールの種類として **[サーバー ファーム]** を指定することで、[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] データベースを構成できます。  
* 「[CSOM:SharePoint Services アダプター](../core/csom-sharepoint-services-adapter.md)」に、SharePoint の受信場所と送信ポートの構成に関する情報が記載されています。  
* BizTalk Server 2010 以前のバージョンでは、Server Side Object Model (SSOM) を使用して SharePoint 2010 に接続します。 

## <a name="csom-and-ssom-supported-versions"></a>CSOM と SSOM のサポートされるバージョン  
[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] のサポートを次の表に示します。  
  
||CSOM のサポート|SSOM のサポート|  
|-|-------------------|-------------------|  
|[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] 2016|可|不可|  
|[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] 2013|可|不可|  
|[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] オンライン|可|不可|  
|[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] 2010|可|可|  
|[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] 2007 |不可|可|  
  
##  <a name="BKMK_CSOM"></a> SharePoint アダプターのインストール  
  
1.  次の要件に基づく SharePoint コンピューターを使用します。  
  
    ||CSOM のサポート|  
    |-|------------------|  
        |[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] 2016<br /><br /> [SharePoint 2016 のインストール](https://technet.microsoft.com/library/cc262957(v=office.16).aspx)|可|  
    |[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] 2013<br /><br /> [SharePoint 2013 のインストール](https://technet.microsoft.com/library/cc262957.aspx)|可|  
    |[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] オンライン<br /><br /> [SharePoint Online の管理](https://technet.microsoft.com/library/gg132908.aspx)|可|  
    |[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] 2010<br /><br /> [SharePoint Server 2010 のインストールと展開](https://technet.microsoft.com/library/cc262957(v=office.14).aspx)|可|  
    |[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] 2007 |不可|  
  
2.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 上に Windows Identity Foundation をインストールします。  
  
    | オペレーティング システム | Info |  
    |-|-|  
    |[!INCLUDE[btsWinNoVersion](../includes/btswinnoversion-md.md)] 10、[!INCLUDE[btsWinNoVersion](../includes/btswinnoversion-md.md)] 8.1、[!INCLUDE[btsWinNoVersion](../includes/btswinnoversion-md.md)] Server 2016、[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]、および [!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)] R2|Windows Identity Foundation は **[Windows の機能の有効化または無効化]** に表示される機能としてオペレーティング システムに含まれています。|  
    |[!INCLUDE[btsWinVista](../includes/btswinvista-md.md)] SP1|[Windows Identity Foundation](http://www.microsoft.com/download/details.aspx?id=17331) からダウンロードできます。|  
  
3.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] をインストールします。

    | |  |  
    |-|-|  
     | [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] | BizTalk セットアップを実行します。 |
    | [!INCLUDE[bts2013r2_md](../includes/bts2013r2-md.md)] | BizTalk セットアップを実行し、**[Windows SharePoint Services アダプター]** のチェック ボックスはオンに**しない**でください。 |  
    | BizTalk Server 2013 | BizTalk セットアップを実行し、**[Windows SharePoint Services アダプター]** のチェック ボックスはオンに**しない**でください。 |
  
##  <a name="BKMK_SSOM"></a> SSOM SharePoint アダプターのインストール (非推奨)  
  
1.  次の SSOM 要件に基づく [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] コンピューターを使用します。  
  
    ||SSOM のサポート|  
    |-|------------------|  
    |[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] 2016<br /><br /> [SharePoint 2016 のインストール](https://technet.microsoft.com/library/cc262957(v=office.16).aspx)|不可| 
    |[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] 2013<br /><br /> [SharePoint 2013 のインストール](http://technet.microsoft.com/library/cc303424.aspx)|不可|  
    |[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] オンライン<br /><br /> [SharePoint Online の管理](https://technet.microsoft.com/library/gg132908.aspx)|不可|  
    |[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] 2010<br /><br /> [SharePoint Server 2010 のインストールと展開](https://technet.microsoft.com/library/cc262957(v=office.14).aspx)|可|  
    |[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] 2007<br /><br /> [SharePoint Server 2007 のインストール](https://technet.microsoft.com/library/cc262957(v=office.12).aspx) |可|  
  
2.  [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] コンピューターで、SharePoint を構成し、既定の Web サイトを拡張します。 Web サイトを拡張すると、別の IIS Web サイトが作成されます。この Web サイトのコンテンツは同じですが、URL と認証の種類は固有のものです。  
  
     「[SharePoint 2010: Web アプリケーションを拡張する](http://go.microsoft.com/fwlink/p/?LinkId=259124)」を参照してください。  
  
3.  [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] コンピューターで、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] インストールを実行し、**[Windows SharePoint Services アダプター]** のチェック ボックス**のみ**をオンにします。 これで Web サービスがインストールされます。 **BizTalk の構成は実行しないでください**。  
  
4.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] をインストールします。 **[Windows SharePoint Services アダプター]** のチェック ボックスをオンに**しない**でください。  
  
5.  [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] Web サービス (SSOM) は、64 ビット モードでのみ動作します。 SharePoint をインストールする前に、SharePoint コンピューターで ASP.NET と IIS アプリケーション プールを 64 ビット モードで実行するようにしておく必要があります。 これを行うには :  
  
    -   **ASP.NET**: IIS マネージャーを開き、Web サイトをクリックし、**[ハンドラー マッピング]** をダブルクリックします。 **[有効]** の一覧に、**PageHandlerFactory-ISAPI-2.0-64** があることを確認します。  
  
    -   **アプリケーション プール**: IIS マネージャーを開き、**[アプリケーション プール]** をクリックし、アプリケーション プールを選択し、**[詳細設定]** をクリックします。 **[32 ビット アプリケーションの有効化]** で、**[False]** を選択します。  

