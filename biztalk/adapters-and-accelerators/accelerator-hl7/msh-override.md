---
title: "MSH 上書き |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, MSH segments
- routing, messages
- subscriptions
- messages, routing
- routing, MSH segments
- send ports, subscriptions
- MSH segments
- send ports, multiple ports
ms.assetid: 4f5700bc-c8f4-40c9-9c9c-2220fa2627ba
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6ed4111e2fdb925740d248c9f751f7a80b9f046f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="msh-override"></a><span data-ttu-id="8a93c-102">MSH 上書き</span><span class="sxs-lookup"><span data-stu-id="8a93c-102">MSH Override</span></span>
<span data-ttu-id="8a93c-103">前に[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) MSH セグメント内の特定の値を置換する場合は、送信ポートに送信 HL7 メッセージをルーティングします。</span><span class="sxs-lookup"><span data-stu-id="8a93c-103">Before [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) routes an outbound HL7 message to a send port, you may want to replace certain values within the MSH segment.</span></span> <span data-ttu-id="8a93c-104">これを行うときに、メッセージのサブスクリプションには、複数の送信ポートが含まれているし、各送信ポートが受信アプリケーション フィールドに別の値を確認することがあります。</span><span class="sxs-lookup"><span data-stu-id="8a93c-104">You may want to do this when the subscription for a message contains multiple send ports, and each send port should see a different value in the receiving-application field.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a93c-105">参照</span><span class="sxs-lookup"><span data-stu-id="8a93c-105">See Also</span></span>  
 <span data-ttu-id="8a93c-106">[MSH フィールドの上書き](../../adapters-and-accelerators/accelerator-hl7/msh-field-overrides.md) </span><span class="sxs-lookup"><span data-stu-id="8a93c-106">[MSH Field Overrides](../../adapters-and-accelerators/accelerator-hl7/msh-field-overrides.md) </span></span>  
 [<span data-ttu-id="8a93c-107">受信確認</span><span class="sxs-lookup"><span data-stu-id="8a93c-107">Acknowledgments</span></span>](../../adapters-and-accelerators/accelerator-hl7/acknowledgments.md)