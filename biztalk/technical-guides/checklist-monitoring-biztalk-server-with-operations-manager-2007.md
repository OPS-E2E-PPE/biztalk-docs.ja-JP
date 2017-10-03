---
title: "チェックリスト: Operations Manager 2007 の BizTalk Server の監視 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2e1f7f57-1501-473f-af5f-15f3e1ddaf8e
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 810ede830f7142181c4bec1f727cbc496049ce03
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="checklist-monitoring-biztalk-server-with-operations-manager-2007"></a>チェックリスト: Operations Manager 2007 の BizTalk Server の監視
このトピックは、監視を準備する場合に行うことができる手順の概要を示します、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境。  
  
|手順|リファレンス|  
|----------|---------------|  
|インストールし、ソフトウェアを構成するには、適切なアクセス許可があることを確認、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]コンピューター。|[セキュリティの最小ユーザー権限](http://go.microsoft.com/fwlink/?LinkID=154374)(http://go.microsoft.com/fwlink/?LinkID=154374)|  
|各 Operations Manager 2007 エージェントをインストール[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]コンピューターを監視し、Operations Manager 2007 サーバーをポイントします。|参照してください[Operations Manager 2007 の展開](http://go.microsoft.com/fwlink/?LinkId=110030)(http://go.microsoft.com/fwlink/?LinkId=110030)|  
|次のような適切なバージョンの管理パックのダウンロードとインポート。<br /><br /> -   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)](必須)<br />エンタープライズ シングル サインオン (必須)<br />Windows ベース OS (サーバー) (省略可能)<br />Microsoft Windows Server クラスター (クラスターが場合に使用される、省略可能)<br />SQL Server 2008、SQL Server 2005 (省略可能)<br />-インターネット インフォメーション サービス (IIS) 2008 では、IIS 2003 (省略可能)<br />メッセージ キュー (MSMQ) 3.0 (省略可能)|-から、管理パックをダウンロードする[System Center 管理パック カタログ](http://go.microsoft.com/fwlink/?LinkId=203227)(http://go.microsoft.com/fwlink/?LinkId=203227)。<br />-での手順に従って、管理パックをインポートする[Operations Manager 2007 で管理パックをインポートする方法](http://go.microsoft.com/fwlink/?LinkID=98348)(http://go.microsoft.com/fwlink/?LinkID=98348)。|  
|Operations Manager 2010 を使用して監視するためのベスト プラクティスを読み取る[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]です。|[Operations Manager 2007 で監視のベスト プラクティス](../technical-guides/best-practices-for-monitoring-with-operations-manager-2007.md)|  
|有効または無効にする、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理パックのルールをクリックします。|[Operations Manager 2007 で監視のベスト プラクティス](../technical-guides/best-practices-for-monitoring-with-operations-manager-2007.md)|  
|スタンドアロンのエンタープライズ シングル サインオン (SSO) コンピューターを BizTalk Server 管理パックによって監視されるコンピューターの一覧に追加します。|[BizTalk Server 管理パックで監視するコンピューターの一覧にエンタープライズ シングル サインオン コンピューターを追加する方法](http://go.microsoft.com/fwlink/?LinkId=157263)(http://go.microsoft.com/fwlink/?LinkId=157263)。|  
  
## <a name="see-also"></a>参照  
 [System Center Operations Manager 2007 での BizTalk Server の監視](../technical-guides/monitoring-biztalk-server-with-system-center-operations-manager-2007.md)