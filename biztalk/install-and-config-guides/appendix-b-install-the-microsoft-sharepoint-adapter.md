---
title: "付録 b: SharePoint アダプターをインストールする |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f44c6e0a-dcce-4444-8cac-bd403c81a233
caps.latest.revision: 
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1d0766eabdad71546090b703e41a00f496629d83
ms.sourcegitcommit: 32f380810b90b70e5df7be72a6a14988a747868e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2018
---
# <a name="appendix-b-install-the-microsoft-sharepoint-adapter"></a>付録 B: Microsoft SharePoint アダプターのインストール
BizTalk Server には、メッセージを受信したり、SharePoint にメッセージを送信できる SharePoint アダプターが含まれています。 

[BizTalk Server 2016](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md) および [BizTalk Server 2013 R2 / 2013](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2013-and-2013-r2.md) のソフトウェア要件には、サポートされている SharePoint バージョンがリストされています。

## <a name="sharepoint-adapter-in-biztalk-server-2016"></a>BizTalk Server 2016 の SharePoint アダプター

BizTalk Server セットアップでは、ファイル アダプター、FTP アダプター、および他の既定のアダプターなど、CSOM 再頒布可能パッケージが自動的にインストールされます。 

SSOM オプションは削除されており、使用できません。


## <a name="sharepoint-adapter-in-biztalk-server-2013-and-r2"></a>BizTalk Server 2013 および R2 の SharePoint アダプター
BizTalk Server 2013 R2 および BizTalk Server 2013、SharePoint アダプターの 2 つのオプションがあります。

|SharePoint オブジェクト モデル|Description|  
|-------------------------|-----------------|  
|CSOM の SharePoint アダプター|**推奨**します。 BizTalk Server セットアップでは、ファイル アダプター、FTP アダプター、および他の既定のアダプターなど、CSOM 再頒布可能パッケージが自動的にインストールされます。 <br/><br/>SharePoint コンピューターに関するインストール要件はありません。|  
|SSOM - SharePoint Web サービス|**使用しません**。 SharePoint コンピューターで BizTalk Server のセットアップを実行し、**のみ**SharePoint アダプターを選択します。 このセットアップでは、BizTalk Server の SharePoint アダプターへの通信を処理する IIS Web サービスをインストールします。 <br/><br/>ほとんどの環境で BizTalk Server と SharePoint は別のコンピューターです。|  

##  <a name="BKMK_Before"></a> インストールの準備  

*  SharePoint SSOM および CSOM コンポーネントが、両方ともインストールできます BizTalk Server 2013 R2 または 2013 と SharePoint が、同じコンピューターにインストールされている場合。  
  
* BAM ポータルは、32 ビット モードでのみ動作します。 BAM ポータルを 64 ビット コンピューターにインストールする場合は、ASP.NET 2.0 が 32 ビットで有効になっていて、IIS アプリケーション プールが 32 ビット モードであることを確認します。 これを行うには :  
  
    -   **ASP.NET**: IIS マネージャーを開き、**BAM ポータル** Web サイトをクリックし、**[ハンドラー マッピング]** をダブルクリックします。 **[有効]** の一覧に、**PageHandlerFactory-ISAPI-2.0** があることを確認します。  
  
    -   **アプリケーション プール**: IIS マネージャーを開き、**[アプリケーション プール]**、**[BAMAppPool]**、**[詳細設定]** の順にクリックします。 **を有効にする 32 ビット アプリケーション**,  **True**します。  
  
* SharePoint をインストールするをクリックして、**サーバー ファーム**オプション、サーバー 1 台の BizTalk Server と SharePoint のインストールを作成するときにもします。 A**サーバー ファーム**インストールでは、SharePoint データベースを構成することができます。  
* 「[CSOM:SharePoint Services アダプター](../core/csom-sharepoint-services-adapter.md)」に、SharePoint の受信場所と送信ポートの構成に関する情報が記載されています。  
* BizTalk Server 2010 以前のバージョンでは、Server Side Object Model (SSOM) を使用して SharePoint 2010 に接続します。 

## <a name="csom-and-ssom-supported-versions"></a>CSOM と SSOM のサポートされるバージョン  
SharePoint のサポートは、次の表に表示されます。  
  
||CSOM のサポート|SSOM のサポート|  
|---|---|---|  
|SharePoint 2016|はい|いいえ|  
|SharePoint 2013|はい|いいえ|  
|SharePoint Online|はい|いいえ|  
|SharePoint 2010|はい|はい|  
|SharePoint 2007 |いいえ|はい|  
  
##  <a name="BKMK_CSOM"></a> SharePoint アダプターのインストール  
  
1.  次の要件に基づく SharePoint コンピューターを使用します。  
  
    ||CSOM のサポート|  
    |---|---|  
    |SharePoint 2016<br /><br /> [SharePoint 2016 のインストール](https://technet.microsoft.com/library/cc262957(v=office.16).aspx)|はい|  
    |SharePoint 2013<br /><br /> [SharePoint 2013 のインストール](https://technet.microsoft.com/library/cc262957.aspx)|はい|  
    |SharePoint Online<br /><br /> [SharePoint Online の管理](https://technet.microsoft.com/library/gg132908.aspx)|はい|  
    |SharePoint 2010<br /><br /> [SharePoint Server 2010 のインストールと展開](https://technet.microsoft.com/library/cc262957(v=office.14).aspx)|はい|  
    |SharePoint 2007 |いいえ|  
  
2.  BizTalk Server では、Windows Identity Foundation をインストールします。  
  
    | オペレーティング システム | Info |  
    |---|---|  
    |Windows 10、Windows 8.1、Windows Server 2016、Windows Server 2012、および Windows Server 2012 R2|Windows Identity Foundation は **[Windows の機能の有効化または無効化]** に表示される機能としてオペレーティング システムに含まれています。|  
    |Windows Vista SP1|[Windows Identity Foundation](http://www.microsoft.com/download/details.aspx?id=17331) からダウンロードできます。|  
  
3.  BizTalk Server をインストールします。

    | |  |  
    |---|---|  
     | BizTalk Server 2016 | BizTalk セットアップを実行します。 |
    | BizTalk Server 2013 R2 | BizTalk セットアップを実行し、**[Windows SharePoint Services アダプター]** のチェック ボックスはオンに**しない**でください。 |  
    | BizTalk Server 2013 | BizTalk セットアップを実行し、**[Windows SharePoint Services アダプター]** のチェック ボックスはオンに**しない**でください。 |
  
##  <a name="BKMK_SSOM"></a> SSOM SharePoint アダプターのインストール (非推奨)  
  
1.  次の SSOM 要件に基づく SharePoint コンピューターを使用します。  
  
    ||SSOM のサポート|  
    |---|---|  
    |SharePoint 2016<br /><br /> [SharePoint 2016 のインストール](https://technet.microsoft.com/library/cc262957(v=office.16).aspx)|いいえ| 
    |SharePoint 2013<br /><br /> [SharePoint 2013 のインストール](http://technet.microsoft.com/library/cc303424.aspx)|いいえ|  
    |SharePoint Online<br /><br /> [SharePoint Online の管理](https://technet.microsoft.com/library/gg132908.aspx)|いいえ|  
    |SharePoint 2010<br /><br /> [SharePoint Server 2010 のインストールと展開](https://technet.microsoft.com/library/cc262957(v=office.14).aspx)|はい|  
    |SharePoint 2007<br /><br /> [SharePoint Server 2007 のインストール](https://technet.microsoft.com/library/cc262957(v=office.12).aspx) |はい|  
  
2.  SharePoint コンピューターで、SharePoint を構成し、既定の Web サイトを拡張します。 Web サイトを拡張すると、別の IIS Web サイトが作成されます。この Web サイトのコンテンツは同じですが、URL と認証の種類は固有のものです。  
  
     「[SharePoint 2010: Web アプリケーションを拡張する](http://go.microsoft.com/fwlink/p/?LinkId=259124)」を参照してください。  
  
3.  SharePoint コンピューターで BizTalk Server のインストールを実行し、**のみ**確認**Windows SharePoint Services アダプター**です。 これで Web サービスがインストールされます。 **BizTalk の構成は実行しないでください**。  
  
4.  BizTalk Server には、BizTalk Server をインストールします。 **[Windows SharePoint Services アダプター]** のチェック ボックスをオンに**しない**でください。  
  
5.  SharePoint Web サービス (SSOM) は、64 ビット モードでのみ実行されます。 SharePoint をインストールする前に、SharePoint コンピューターで ASP.NET と IIS アプリケーション プールを 64 ビット モードで実行するようにしておく必要があります。 これを行うには :  
  
    -   **ASP.NET**: IIS マネージャーを開き、Web サイトをクリックし、**[ハンドラー マッピング]** をダブルクリックします。 **[有効]** の一覧に、**PageHandlerFactory-ISAPI-2.0-64** があることを確認します。  
  
    -   **アプリケーション プール**: IIS マネージャーを開き、**[アプリケーション プール]** をクリックし、アプリケーション プールを選択し、**[詳細設定]** をクリックします。 **[32 ビット アプリケーションの有効化]** で、**[False]** を選択します。  

