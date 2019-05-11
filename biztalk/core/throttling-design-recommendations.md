---
title: 制限の設計の推奨事項 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- host throttling, best practices
- best practices, host throttling
ms.assetid: c3332bb4-abfd-4961-9562-5a3a930d4380
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 784953dbc8b9cf33a883997b13e83554666b3488
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65379968"
---
# <a name="throttling-design-recommendations"></a><span data-ttu-id="31ac2-102">制限の設計の推奨事項</span><span class="sxs-lookup"><span data-stu-id="31ac2-102">Throttling Design Recommendations</span></span>
<span data-ttu-id="31ac2-103">このセクションでは、調整を活用するためにソリューションを設計する方法の推奨事項を提供します。</span><span class="sxs-lookup"><span data-stu-id="31ac2-103">This section provides recommendations on how to design a solution to take advantage of throttling.</span></span> <span data-ttu-id="31ac2-104">調整のエンジンの機能強化で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]BizTalk Server のパフォーマンスに大きく影響する可能性があります</span><span class="sxs-lookup"><span data-stu-id="31ac2-104">The throttling engine enhancements in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] may significantly impact the performance of BizTalk Server</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="31ac2-105">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="31ac2-105">In This Section</span></span>  
  
-   [<span data-ttu-id="31ac2-106">関連付けられたメッセージのスロットルを回避する方法</span><span class="sxs-lookup"><span data-stu-id="31ac2-106">How to Avoid Throttling Correlated Messages</span></span>](../core/how-to-avoid-throttling-correlated-messages.md)  
  
-   [<span data-ttu-id="31ac2-107">調整のしきい値の調整。タイミングと理由</span><span class="sxs-lookup"><span data-stu-id="31ac2-107">Adjusting Throttling Thresholds: When and Why</span></span>](../core/adjusting-throttling-thresholds-when-and-why.md)  
  
-   <span data-ttu-id="31ac2-108">[[データベースのメッセージ カウント] の制限のしきい値に含まれる保留メッセージ](../core/suspended-messages-included-in-message-count-in-database-throttling-threshold.md)</span><span class="sxs-lookup"><span data-stu-id="31ac2-108">[Suspended Messages are Included in the Message Count in Database Throttling Threshold](../core/suspended-messages-included-in-message-count-in-database-throttling-threshold.md)</span></span>