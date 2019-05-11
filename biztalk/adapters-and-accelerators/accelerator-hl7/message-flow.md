---
title: メッセージ フロー |Microsoft Docs
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
ms.openlocfilehash: 9d53c1038653a411666af4891a542e90fe988519
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65303701"
---
# <a name="message-flow"></a><span data-ttu-id="216dd-102">メッセージ フロー</span><span class="sxs-lookup"><span data-stu-id="216dd-102">Message Flow</span></span>
<span data-ttu-id="216dd-103">次のセクションでは、を通じて Microsoft BizTalk Accelerator for HL7 ケアのヘルス メッセージのフローについて説明します ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)])、どのように[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]メッセージングのルーティングのしくみ。</span><span class="sxs-lookup"><span data-stu-id="216dd-103">The following sections describe how health care messages flow through Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]), and how [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] messaging routing works.</span></span> <span data-ttu-id="216dd-104">このルーティングで Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]プランには、データの検証、メッセージ ヘッダーの上書き、および受信確認の機能が強化されています。</span><span class="sxs-lookup"><span data-stu-id="216dd-104">Through this routing, Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] offers enhanced functionality for data validation, message-header override, and acknowledgments.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="216dd-105">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="216dd-105">In This Section</span></span>  
  
-   [<span data-ttu-id="216dd-106">BTAHL7 内のメッセージのフロー</span><span class="sxs-lookup"><span data-stu-id="216dd-106">How Messages Flow through BTAHL7</span></span>](../../adapters-and-accelerators/accelerator-hl7/how-messages-flow-through-btahl7.md)  
  
-   [<span data-ttu-id="216dd-107">BTAHL7 によるメッセージのルーティング方法</span><span class="sxs-lookup"><span data-stu-id="216dd-107">How BTAHL7 Routes Messages</span></span>](../../adapters-and-accelerators/accelerator-hl7/how-btahl7-routes-messages.md)  
  
-   [<span data-ttu-id="216dd-108">メッセージの検証</span><span class="sxs-lookup"><span data-stu-id="216dd-108">Message Validation</span></span>](../../adapters-and-accelerators/accelerator-hl7/message-validation.md)  
  
-   [<span data-ttu-id="216dd-109">MSH のオーバーライド</span><span class="sxs-lookup"><span data-stu-id="216dd-109">MSH Override</span></span>](../../adapters-and-accelerators/accelerator-hl7/msh-override.md)  
  
-   [<span data-ttu-id="216dd-110">受信確認</span><span class="sxs-lookup"><span data-stu-id="216dd-110">Acknowledgments</span></span>](../../adapters-and-accelerators/accelerator-hl7/acknowledgments.md)