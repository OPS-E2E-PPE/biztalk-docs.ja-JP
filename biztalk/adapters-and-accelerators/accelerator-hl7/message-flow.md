---
title: メッセージ フロー |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, message flow
- BTAHL7, message flow
ms.assetid: 976d230f-942b-4c80-b03d-0b991a713ebe
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 318f4fe89e230aecfa53ddda1861cae2a56b717f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22205042"
---
# <a name="message-flow"></a><span data-ttu-id="adc0f-102">メッセージ フロー</span><span class="sxs-lookup"><span data-stu-id="adc0f-102">Message Flow</span></span>
<span data-ttu-id="adc0f-103">次のセクションからの注意のヘルス メッセージのフローについて説明[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)])、およびどのように[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]メッセージングのルーティングのしくみです。</span><span class="sxs-lookup"><span data-stu-id="adc0f-103">The following sections describe how health care messages flow through [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]), and how [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] messaging routing works.</span></span> <span data-ttu-id="adc0f-104">このルーティングを通じて[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]提供には、データの検証、メッセージ ヘッダーの上書き、および受信確認の機能が強化されています。</span><span class="sxs-lookup"><span data-stu-id="adc0f-104">Through this routing, [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] offers enhanced functionality for data validation, message-header override, and acknowledgments.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="adc0f-105">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="adc0f-105">In This Section</span></span>  
  
-   [<span data-ttu-id="adc0f-106">BTAHL7 内のメッセージのフロー</span><span class="sxs-lookup"><span data-stu-id="adc0f-106">How Messages Flow through BTAHL7</span></span>](../../adapters-and-accelerators/accelerator-hl7/how-messages-flow-through-btahl7.md)  
  
-   [<span data-ttu-id="adc0f-107">BTAHL7 でメッセージをルーティングする方法</span><span class="sxs-lookup"><span data-stu-id="adc0f-107">How BTAHL7 Routes Messages</span></span>](../../adapters-and-accelerators/accelerator-hl7/how-btahl7-routes-messages.md)  
  
-   [<span data-ttu-id="adc0f-108">メッセージの検証</span><span class="sxs-lookup"><span data-stu-id="adc0f-108">Message Validation</span></span>](../../adapters-and-accelerators/accelerator-hl7/message-validation.md)  
  
-   [<span data-ttu-id="adc0f-109">MSH 上書き</span><span class="sxs-lookup"><span data-stu-id="adc0f-109">MSH Override</span></span>](../../adapters-and-accelerators/accelerator-hl7/msh-override.md)  
  
-   [<span data-ttu-id="adc0f-110">受信確認</span><span class="sxs-lookup"><span data-stu-id="adc0f-110">Acknowledgments</span></span>](../../adapters-and-accelerators/accelerator-hl7/acknowledgments.md)