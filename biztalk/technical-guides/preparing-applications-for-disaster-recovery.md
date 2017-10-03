---
title: "アプリケーションの災害復旧の準備 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0ef93099-aa6b-424a-a4ce-87d855c6afe3
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7028b1386f71f653dfc41b9de2522cdbd8d02126
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="preparing-applications-for-disaster-recovery"></a>アプリケーションの災害復旧の準備
BizTalk アプリケーション (バイナリと構成アイテムなどの受信場所と送信ポート) は、障害復旧サイトで、グループを復元するときに、実稼働の BizTalk グループに展開されます。 この構成がかどうかに応じてを変更する必要がありますは構成の場所はなどの受信場所や、実稼働環境に固有のポートを送信します。  
  
 災害復旧サイトにアプリケーションの復元を高速化する、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]にバイナリをインストールする .msi ファイル、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ランタイム サーバー必要がありますに最新に維持災害復旧[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]実行時のサーバー。 障害復旧サイトで、運用環境の BizTalk グループが復元される場合、災害復旧固有のアプリケーション構成の .msi ファイルならない場合がありますなど、障害回復に固有の成果物のため、アプリケーションを構成するためにインストールします。受信場所と、必要に応じて、ポートを送信します。  
  
## <a name="see-also"></a>参照  
 [アプリケーションを展開します。](../technical-guides/deploying-an-application.md)