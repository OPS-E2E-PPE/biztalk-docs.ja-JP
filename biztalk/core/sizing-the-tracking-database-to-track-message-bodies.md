---
title: "メッセージ本文の追跡に追跡データベースのサイジング |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Tracking database, database size
- message variables [Tracking database], MsgNum
- HAT, ports
- Tracking database, messages
- tracking, orchestrations
- tracking, messages
- HAT, orchestrations
- tracking, ports
ms.assetid: ee75e530-f15d-4ceb-ba67-0b0b24d9df6b
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1b5abc3f2a48f2baea5d158e1a0268a7eede51c2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="sizing-the-tracking-database-to-track-message-bodies"></a><span data-ttu-id="f049d-102">メッセージの本文を追跡するための追跡データベースのサイズ設定</span><span class="sxs-lookup"><span data-stu-id="f049d-102">Sizing the Tracking Database to Track Message Bodies</span></span>
<span data-ttu-id="f049d-103">BizTalk 追跡データベースのメッセージ本文を追跡する場合は、メッセージ本文のサイズも考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f049d-103">If you plan to track the message bodies in the BizTalk Tracking database, then you will also need to account for the size of these bodies in your calculation.</span></span> <span data-ttu-id="f049d-104">次の式を使用します。</span><span class="sxs-lookup"><span data-stu-id="f049d-104">Use the following equation:</span></span>  
  
```  
[Msgs * MsgNum * (MsgSize)]/1024 = Data size in MB  
```  
  
 <span data-ttu-id="f049d-105">メッセージ コンテキストの平均サイズがメッセージ サイズと比べて非常に大きい場合は、上の式の MsgSize にメッセージ コンテキストの平均サイズを追加することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="f049d-105">Consider adding the average size of the message context to MsgSize above if it is significant compared to the message size.</span></span>  
  
 <span data-ttu-id="f049d-106">[グループ ハブ] ページでメッセージ イベントおよびサービス インスタンスの追跡を使用し、ポート レベルまたはオーケストレーション レベルの追跡機能を有効にすることで、MsgNum 変数が決まります。</span><span class="sxs-lookup"><span data-stu-id="f049d-106">The MsgNum variable is determined by turning on the tracking features at the port level or at the orchestration level using the message event and service instance tracking in the Group Hub page.</span></span> <span data-ttu-id="f049d-107">この式は、各メッセージ プロセスにも適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f049d-107">You must apply this formula to each message process as well.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f049d-108">参照</span><span class="sxs-lookup"><span data-stu-id="f049d-108">See Also</span></span>  
 <span data-ttu-id="f049d-109">[追跡データベースのサイズをメッセージ変数を使用](../core/using-message-variables-to-size-the-tracking-database.md) </span><span class="sxs-lookup"><span data-stu-id="f049d-109">[Using Message Variables to Size the Tracking Database](../core/using-message-variables-to-size-the-tracking-database.md) </span></span>  
 <span data-ttu-id="f049d-110">[シナリオ 1: 単純な BizTalk メッセージの追跡データベースのサイズ変更](../core/scenario-1-sizing-the-tracking-database-for-simple-biztalk-messages.md) </span><span class="sxs-lookup"><span data-stu-id="f049d-110">[Scenario 1: Sizing the Tracking Database  for Simple BizTalk Messages](../core/scenario-1-sizing-the-tracking-database-for-simple-biztalk-messages.md) </span></span>  
 <span data-ttu-id="f049d-111">[シナリオ 2: オーケストレーションでメッセージの追跡データベースのサイズ変更](../core/scenario-2-sizing-the-tracking-database-for-messages-in-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="f049d-111">[Scenario 2: Sizing the Tracking Database  for Messages in Orchestrations](../core/scenario-2-sizing-the-tracking-database-for-messages-in-orchestrations.md) </span></span>  
 <span data-ttu-id="f049d-112">[シナリオ 4: すべてのメッセージの追跡データベースのサイズ変更](../core/scenario-4-sizing-the-tracking-database-for-all-messages.md) </span><span class="sxs-lookup"><span data-stu-id="f049d-112">[Scenario 4: Sizing the Tracking Database for all Messages](../core/scenario-4-sizing-the-tracking-database-for-all-messages.md) </span></span>  
 [<span data-ttu-id="f049d-113">シナリオ 3: 同報リストに送信されるメッセージの追跡データベースのサイズ変更</span><span class="sxs-lookup"><span data-stu-id="f049d-113">Scenario 3: Sizing the Tracking Database  for Messages Sent Out to Distribution Lists</span></span>](../core/scenario-3-size-the-tracking-database-for-messages-sent-to-distribution-lists.md)