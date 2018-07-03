---
title: サブスクライバーを警告から削除する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- subscriptions, subscribers
- managing [BAM], deleting alert subscibers
- alerts, subscribers
ms.assetid: d5571863-26e3-4c1b-991f-538cd1fef347
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 74c896eea581b50782e282a9ff5a08db04e8a4e6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37021014"
---
# <a name="how-to-remove-subscribers-from-an-alert"></a>サブスクライバーを警告から削除する方法
管理者を使用して、**削除サブスクリプション**アラートから、サブスクライバーとして、指定されたユーザーを削除するコマンド。  
  
### <a name="to-remove-subscribers-from-an-alert"></a>サブスクライバーを警告から削除するには  
  
1. 次のように、コマンド プロンプトを開きます: をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリックします**OK**。  
  
2. [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking に移動します。  
  
3. 型**bm 削除-サブスクリプション-ビュー:\<ビュー名\>-警告:\<アラート名\>-accountname:\<アカウント名\>** します。  
  
   > [!NOTE]
   >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
4. **Enter**キーを押します。  
  
## <a name="see-also"></a>参照  
 [BAM 動的インフラストラクチャの管理](../core/managing-the-bam-dynamic-infrastructure.md)   
 [BAM 管理ユーティリティ](../core/bam-management-utility.md)   
 [警告にサブスクライバーを追加する方法](../core/how-to-add-subscribers-to-an-alert.md)