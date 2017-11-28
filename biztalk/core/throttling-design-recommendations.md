---
title: "設計の推奨事項を調整 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- host throttling, best practices
- best practices, host throttling
ms.assetid: c3332bb4-abfd-4961-9562-5a3a930d4380
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ebc5fff27bf634480c1de3c5e28f1184e0a8d046
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="throttling-design-recommendations"></a><span data-ttu-id="6c41c-102">制限の設計時の推奨事項</span><span class="sxs-lookup"><span data-stu-id="6c41c-102">Throttling Design Recommendations</span></span>
<span data-ttu-id="6c41c-103">このセクションでは、制限を利用する場合のソリューションの設計方法に関する推奨事項について説明します。</span><span class="sxs-lookup"><span data-stu-id="6c41c-103">This section provides recommendations on how to design a solution to take advantage of throttling.</span></span> <span data-ttu-id="6c41c-104">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の制限エンジンの機能強化は、BizTalk Server のパフォーマンスに大きな影響を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6c41c-104">The throttling engine enhancements in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] may significantly impact the performance of BizTalk Server</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6c41c-105">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="6c41c-105">In This Section</span></span>  
  
-   [<span data-ttu-id="6c41c-106">関連付けられたメッセージの制限を回避する方法</span><span class="sxs-lookup"><span data-stu-id="6c41c-106">How to Avoid Throttling Correlated Messages</span></span>](../core/how-to-avoid-throttling-correlated-messages.md)  
  
-   [<span data-ttu-id="6c41c-107">制限のしきい値の調整: タイミングと理由</span><span class="sxs-lookup"><span data-stu-id="6c41c-107">Adjusting Throttling Thresholds: When and Why</span></span>](../core/adjusting-throttling-thresholds-when-and-why.md)  
  
-   <span data-ttu-id="6c41c-108">[[メッセージ カウント] データベースの制限のしきい値に含まれる保留メッセージ](../core/suspended-messages-included-in-message-count-in-database-throttling-threshold.md)</span><span class="sxs-lookup"><span data-stu-id="6c41c-108">[Suspended Messages are Included in the Message Count in Database Throttling Threshold](../core/suspended-messages-included-in-message-count-in-database-throttling-threshold.md)</span></span>