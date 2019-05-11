---
title: メッセージ本文の追跡を追跡データベースのサイズ調整 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9d25a93548cdf98db3a40156bcd0dd0aff4d11b9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401865"
---
# <a name="sizing-the-tracking-database-to-track-message-bodies"></a><span data-ttu-id="13255-102">メッセージ本文を追跡する追跡データベースのサイズ調整</span><span class="sxs-lookup"><span data-stu-id="13255-102">Sizing the Tracking Database to Track Message Bodies</span></span>
<span data-ttu-id="13255-103">BizTalk 追跡データベースでメッセージ本文を追跡する場合は、計算でこれらの本文のサイズを考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="13255-103">If you plan to track the message bodies in the BizTalk Tracking database, then you will also need to account for the size of these bodies in your calculation.</span></span> <span data-ttu-id="13255-104">次の式を使用します。</span><span class="sxs-lookup"><span data-stu-id="13255-104">Use the following equation:</span></span>  
  
```  
[Msgs * MsgNum * (MsgSize)]/1024 = Data size in MB  
```  
  
 <span data-ttu-id="13255-105">メッセージのサイズと比較したことが重要な場合は、上記の式の MsgSize にメッセージ コンテキストの平均サイズを追加することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="13255-105">Consider adding the average size of the message context to MsgSize above if it is significant compared to the message size.</span></span>  
  
 <span data-ttu-id="13255-106">MsgNum 変数は、ポート レベルまたはメッセージ イベントおよびグループ ハブ ページでサービス インスタンスの追跡を使用してオーケストレーション レベルの追跡機能を有効にして決まります。</span><span class="sxs-lookup"><span data-stu-id="13255-106">The MsgNum variable is determined by turning on the tracking features at the port level or at the orchestration level using the message event and service instance tracking in the Group Hub page.</span></span> <span data-ttu-id="13255-107">次の数式を適用すると、各メッセージ プロセスもあります。</span><span class="sxs-lookup"><span data-stu-id="13255-107">You must apply this formula to each message process as well.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13255-108">参照</span><span class="sxs-lookup"><span data-stu-id="13255-108">See Also</span></span>  
 <span data-ttu-id="13255-109">[追跡データベースのサイズにメッセージ変数を使用します。](../core/using-message-variables-to-size-the-tracking-database.md) </span><span class="sxs-lookup"><span data-stu-id="13255-109">[Using Message Variables to Size the Tracking Database](../core/using-message-variables-to-size-the-tracking-database.md) </span></span>  
 <span data-ttu-id="13255-110">[シナリオ 1: 単純な BizTalk メッセージの追跡データベースのサイズ調整](../core/scenario-1-sizing-the-tracking-database-for-simple-biztalk-messages.md) </span><span class="sxs-lookup"><span data-stu-id="13255-110">[Scenario 1: Sizing the Tracking Database  for Simple BizTalk Messages](../core/scenario-1-sizing-the-tracking-database-for-simple-biztalk-messages.md) </span></span>  
 <span data-ttu-id="13255-111">[シナリオ 2: オーケストレーション内のメッセージの追跡データベースのサイズ調整](../core/scenario-2-sizing-the-tracking-database-for-messages-in-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="13255-111">[Scenario 2: Sizing the Tracking Database  for Messages in Orchestrations](../core/scenario-2-sizing-the-tracking-database-for-messages-in-orchestrations.md) </span></span>  
 <span data-ttu-id="13255-112">[シナリオ 4:すべてのメッセージの追跡データベースのサイズ調整](../core/scenario-4-sizing-the-tracking-database-for-all-messages.md) </span><span class="sxs-lookup"><span data-stu-id="13255-112">[Scenario 4: Sizing the Tracking Database for all Messages](../core/scenario-4-sizing-the-tracking-database-for-all-messages.md) </span></span>  
 [<span data-ttu-id="13255-113">シナリオ 3:配布リストに送信されるメッセージの追跡データベースのサイズ調整</span><span class="sxs-lookup"><span data-stu-id="13255-113">Scenario 3: Sizing the Tracking Database  for Messages Sent Out to Distribution Lists</span></span>](../core/scenario-3-size-the-tracking-database-for-messages-sent-to-distribution-lists.md)