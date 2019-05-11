---
title: メッセージのバッチ処理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- batching
- batching, about batching
- messages, batching
- batching, messages
ms.assetid: d852cf00-3882-4f0f-a4c3-2a39483710ee
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f487d479036f9946dbd32ff9444d8cd714a0a1f1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65303825"
---
# <a name="message-batching"></a><span data-ttu-id="980d0-102">メッセージのバッチ処理</span><span class="sxs-lookup"><span data-stu-id="980d0-102">Message Batching</span></span>
<span data-ttu-id="980d0-103">プロトコルの標準、スケジュールの問題またはメッセージ サイズの制限は、メッセージのバッチの必要を起こさ可能性があります。</span><span class="sxs-lookup"><span data-stu-id="980d0-103">Protocol standards, scheduling issues, or message size limitations may motivate the need to batch messages.</span></span> <span data-ttu-id="980d0-104">正常性レベル 7 (HL7) のバッチは、HL7 バッチ ヘッダーとトレーラーのバッチで囲まれたメッセージで構成されます。</span><span class="sxs-lookup"><span data-stu-id="980d0-104">A Health Level Seven (HL7) batch consists of messages enclosed by an HL7 batch header and batch trailer.</span></span> <span data-ttu-id="980d0-105">メッセージの区切り記号は、バッチ内の個々 のメッセージを区切ります。</span><span class="sxs-lookup"><span data-stu-id="980d0-105">Message separators separate the individual messages within the batch.</span></span>  
  
 <span data-ttu-id="980d0-106">Microsoft[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]バッチ処理のシナリオでは、次の 3 つのメッセージ。</span><span class="sxs-lookup"><span data-stu-id="980d0-106">Microsoft [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] supports the following three message batching scenarios:</span></span>  
  
-   <span data-ttu-id="980d0-107">**断片化した受信バッチ**します。</span><span class="sxs-lookup"><span data-stu-id="980d0-107">**Fragmented inbound batch**.</span></span> <span data-ttu-id="980d0-108">このシナリオでは、BTAHL7 は、HL7 メッセージのバッチを受信し、送信先システムに、個々 のメッセージをルーティングします。</span><span class="sxs-lookup"><span data-stu-id="980d0-108">In this scenario, BTAHL7 receives an HL7 message batch, and then routes the individual messages to the destination system.</span></span>  
  
-   <span data-ttu-id="980d0-109">**バッチ処理/バッチ アウト**します。このシナリオでは、BTAHL7 は HL7 メッセージのバッチを受信、バッチ内の個々 のメッセージを確認し、送信先システムにメッセージのバッチをルーティングします。</span><span class="sxs-lookup"><span data-stu-id="980d0-109">**Batch in/batch out**. In this scenario, BTAHL7 receives an HL7 message batch, verifies the individual messages within the batch, and then routes the message batch to the destination system.</span></span>  
  
-   <span data-ttu-id="980d0-110">**バッチまたは送信バッチ処理を作成する**します。</span><span class="sxs-lookup"><span data-stu-id="980d0-110">**Create batch or outbound batching**.</span></span> <span data-ttu-id="980d0-111">このシナリオでは、BTAHL7 は個々 のメッセージを受信し、送信先システムにルーティングする前にバッチとしてします。</span><span class="sxs-lookup"><span data-stu-id="980d0-111">In this scenario, BTAHL7 receives individual messages and batches them before routing them to the destination system.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="980d0-112">BTAHL7 では、既定では、送信バッチ処理用メッセージのバッチ処理は有効にしません。</span><span class="sxs-lookup"><span data-stu-id="980d0-112">BTAHL7 does not enable message batching for outbound batching by default.</span></span> <span data-ttu-id="980d0-113">BizTalk エクスプ ローラーを使用して、まず、BTAHL7 バッチ オーケストレーションを参加させると、バッチ オーケストレーションを開始する必要があります。</span><span class="sxs-lookup"><span data-stu-id="980d0-113">You must use BizTalk Explorer to first enlist the BTAHL7 batch orchestration, and then start the batch orchestration.</span></span> <span data-ttu-id="980d0-114">メッセージのバッチ処理を有効にする方法の詳細については、次を参照してください。[バッチ処理構成](../../adapters-and-accelerators/accelerator-hl7/configuring-batching.md)します。</span><span class="sxs-lookup"><span data-stu-id="980d0-114">For more information about enabling message batching, see [Configuring Batching](../../adapters-and-accelerators/accelerator-hl7/configuring-batching.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="980d0-115">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="980d0-115">In This Section</span></span>  
  
-   [<span data-ttu-id="980d0-116">断片化した受信バッチ</span><span class="sxs-lookup"><span data-stu-id="980d0-116">Fragmented Inbound Batch</span></span>](../../adapters-and-accelerators/accelerator-hl7/fragmented-inbound-batch.md)  
  
-   [<span data-ttu-id="980d0-117">バッチ処理の構成</span><span class="sxs-lookup"><span data-stu-id="980d0-117">Configuring Batching</span></span>](../../adapters-and-accelerators/accelerator-hl7/configuring-batching.md)  
  
-   [<span data-ttu-id="980d0-118">バッチ処理のスケジュール</span><span class="sxs-lookup"><span data-stu-id="980d0-118">Scheduling Batching</span></span>](../../adapters-and-accelerators/accelerator-hl7/scheduling-batching.md)  
  
-   [<span data-ttu-id="980d0-119">受信確認のバッチ処理の構成</span><span class="sxs-lookup"><span data-stu-id="980d0-119">Configuring Batching Acknowledgments</span></span>](../../adapters-and-accelerators/accelerator-hl7/configuring-batching-acknowledgments.md)