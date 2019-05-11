---
title: 付録 B:SharePoint アダプターのインストール |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f44c6e0a-dcce-4444-8cac-bd403c81a233
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e638eaaf4b677c5fc08e08d608a92ecf75345676
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401492"
---
# <a name="appendix-b-install-the-microsoft-sharepoint-adapter"></a>付録 B:Microsoft SharePoint アダプターをインストールします。
BizTalk Server には、メッセージを受信したり、SharePoint にメッセージを送信するための SharePoint アダプターが含まれています。 

ソフトウェア要件[BizTalk Server 2016](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md)と[BizTalk Server 2013 R2/2013](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2013-and-2013-r2.md)サポートされている SharePoint バージョンを一覧表示します。

## <a name="sharepoint-adapter-in-biztalk-server-2016"></a>BizTalk Server 2016 での SharePoint アダプター

BizTalk Server のセットアップには、CSOM 再頒布可能パッケージ、ファイル アダプター、FTP アダプター、およびその他のボックスのアダプターのように自動的にインストールされます。 

SSOM オプションが削除され、ご利用いただけません。


## <a name="sharepoint-adapter-in-biztalk-server-2013-and-r2"></a>BizTalk Server 2013 および R2 での SharePoint アダプター
BizTalk Server 2013 R2 および BizTalk Server 2013、SharePoint アダプターの 2 つのオプションがあります。

|SharePoint オブジェクト モデル|説明|  
|-------------------------|-----------------|  
|CSOM - SharePoint アダプター|**推奨**します。 BizTalk Server のセットアップには、CSOM 再頒布可能パッケージ、ファイル アダプター、FTP アダプター、およびその他のボックスのアダプターのように自動的にインストールされます。 <br/><br/>SharePoint コンピューターに関するインストール要件はありません。|  
|SSOM - SharePoint Web サービス|**非推奨**。 SharePoint コンピューターでは、BizTalk Server のセットアップを実行し、**のみ**SharePoint アダプターを選択します。 このセットアップでは、BizTalk Server 上の SharePoint アダプターへの通信を処理するための IIS web サービスをインストールします。 <br/><br/>ほとんどの環境では、BizTalk Server および SharePoint とは、別のコンピューターには。|  

##  <a name="BKMK_Before"></a> インストールする前に  

*  SharePoint SSOM および CSOM コンポーネントが、どちらもインストールできます BizTalk Server 2013 R2 または 2013 や SharePoint が同じコンピューターにインストールされている場合。  
  
* BAM ポータルは、32 ビット モードでのみ動作します。 BAM ポータルは、64 ビット コンピューターにインストールする場合は、ASP.NET 2.0 の 32 ビットを有効にし、IIS アプリケーション プールが 32 ビット モードでことを確認します。 これを行うには :  
  
    -   **ASP.NET**:IIS マネージャーを開き、をクリックして、 **BAM ポータル**web サイト、し、ダブルクリック**ハンドラー マッピング**します。 **有効**一覧で、確認**PageHandlerFactory-isapi-2.0**が表示されています。  
  
    -   **アプリケーション プール**:IIS マネージャーを開き、**アプリケーション プール**、 をクリックして、 **BAMAppPool**、 をクリックし、**詳細設定**。 **[32 ビット アプリケーションの有効化]** で、**[True]** を選択します。  
  
* SharePoint をインストールするときにをクリックして、**サーバー ファーム**オプションを 1 台のサーバーの BizTalk Server と SharePoint のインストールを作成する場合でもです。 A**サーバー ファーム**インストールでは、SharePoint データベースを構成できます。  
* [CSOM:SharePoint Services アダプター](../core/csom-sharepoint-services-adapter.md) SharePoint の構成に関する情報を提供します。 受信場所とポートを送信します。  
* BizTalk Server 2010 と以前のバージョンは、サーバー側オブジェクト モデル (SSOM) を使用して、SharePoint 2010 に接続します。 

## <a name="csom-and-ssom-supported-versions"></a>CSOM と SSOM のサポートされるバージョン  
SharePoint のサポートは、次の表に記載されています。  
  
||CSOM のサポート|SSOM のサポート|  
|---|---|---|  
|SharePoint 2016|はい|いいえ|  
|SharePoint 2013|はい|いいえ|  
|SharePoint Online|はい|いいえ|  
|SharePoint 2010|はい|はい|  
|SharePoint 2007 |いいえ|はい|  
  
##  <a name="BKMK_CSOM"></a> CSOM の SharePoint アダプターをインストールします。  
  
1.  次の要件に基づく SharePoint コンピューターを使用します。  
  
    ||CSOM のサポート|  
    |---|---|  
    |SharePoint 2016<br /><br /> [SharePoint 2016 をインストールします。](https://technet.microsoft.com/library/cc262957(v=office.16).aspx)|はい|  
    |SharePoint 2013<br /><br /> [SharePoint 2013 をインストールします。](https://technet.microsoft.com/library/cc262957.aspx)|はい|  
    |SharePoint Online<br /><br /> [SharePoint Online の管理](https://technet.microsoft.com/library/gg132908.aspx)|はい|  
    |SharePoint 2010<br /><br /> [SharePoint Server 2010 のインストールと展開](https://technet.microsoft.com/library/cc262957(v=office.14).aspx)|はい|  
    |SharePoint 2007 |いいえ|  
  
2.  BizTalk Server では、Windows Identity Foundation をインストールします。  
  
    | オペレーティング システム | Info |  
    |---|---|  
    |Windows 10、Windows 8.1、Windows Server 2016、Windows Server 2012、および Windows Server 2012 R2|Windows Identity Foundation が機能として、オペレーティング システムに含まれている**オンまたはオフにする Windows 機能**します。|  
    |Windows Vista SP1|ダウンロードできます[Windows Identity Foundation](http://www.microsoft.com/download/details.aspx?id=17331)します。|  
  
3.  BizTalk Server をインストールします。

    | |  |  
    |---|---|  
     | BizTalk Server 2016 | BizTalk セットアップを実行します。 |
    | BizTalk Server 2013 R2 | BizTalk セットアップを実行し、操作を行います**いない**確認**Windows SharePoint Services アダプター**します。 |  
    | BizTalk Server 2013 | BizTalk セットアップを実行し、操作を行います**いない**確認**Windows SharePoint Services アダプター**します。 |
  
##  <a name="BKMK_SSOM"></a> (非推奨) SSOM SharePoint アダプターをインストールします。  
  
1.  次の SSOM 要件に基づく SharePoint コンピューターを使用します。  
  
    ||SSOM のサポート|  
    |---|---|  
    |SharePoint 2016<br /><br /> [SharePoint 2016 をインストールします。](https://technet.microsoft.com/library/cc262957(v=office.16).aspx)|いいえ| 
    |SharePoint 2013<br /><br /> [SharePoint 2013 をインストールします。](http://technet.microsoft.com/library/cc303424.aspx)|いいえ|  
    |SharePoint Online<br /><br /> [SharePoint Online の管理](https://technet.microsoft.com/library/gg132908.aspx)|いいえ|  
    |SharePoint 2010<br /><br /> [SharePoint Server 2010 のインストールと展開](https://technet.microsoft.com/library/cc262957(v=office.14).aspx)|はい|  
    |SharePoint 2007<br /><br /> [SharePoint Server 2007 のインストール](https://technet.microsoft.com/library/cc262957(v=office.12).aspx) |はい|  
  
2.  SharePoint コンピューターでは、SharePoint を構成し、既定の Web サイトを拡張します。 Web サイトを拡張すると、同じコンテンツが含まれていますも一意の URL と認証の種類を提供します。 別の IIS web サイトが作成されます。  
  
     参照してください[SharePoint 2010。Web アプリケーションの拡張](http://go.microsoft.com/fwlink/p/?LinkId=259124)します。  
  
3.  SharePoint コンピューターでは、BizTalk Server のインストールを実行し、**のみ**確認**Windows SharePoint Services アダプター**します。 これには、web サービスがインストールされます。 **BizTalk の構成を実行しないでください**します。  
  
4.  BizTalk Server では、BizTalk Server をインストールします。 **いない**確認**Windows SharePoint Services アダプター**します。  
  
5.  SharePoint Web サービス (SSOM) は、64 ビット モードでのみ実行されます。 ASP.NET と IIS アプリケーション プールは、SharePoint をインストールする前に、SharePoint コンピューターで 64 ビット モードである必要があります。 これを行うには :  
  
    -   **ASP.NET**:IIS マネージャーを開き、web サイト をクリックして をダブルクリック**ハンドラー マッピング**します。 **有効**一覧で、確認**PageHandlerFactory ISAPI 2.0 64**が表示されています。  
  
    -   **アプリケーション プール**:IIS マネージャーを開き、**アプリケーション プール**アプリケーション プールを選択し、クリックして**詳細設定**します。 **を有効にする 32 ビット アプリケーション**、 **False**します。  

