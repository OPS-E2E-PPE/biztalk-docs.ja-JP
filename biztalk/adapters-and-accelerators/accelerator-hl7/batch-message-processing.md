---
title: バッチ メッセージの処理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- examples, batching
- batching, examples
- batching, batch types
ms.assetid: 264f91b5-3e33-4b87-9da3-866eaa464b0f
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 75cde12720ac67d74396c22282bddaf53e015960
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972371"
---
# <a name="batch-message-processing"></a><span data-ttu-id="294b6-102">バッチ メッセージの処理</span><span class="sxs-lookup"><span data-stu-id="294b6-102">Batch Message Processing</span></span>
<span data-ttu-id="294b6-103">Microsoft BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 処理する 3 種類の HL7 2.X の batch シナリオ。</span><span class="sxs-lookup"><span data-stu-id="294b6-103">Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) handles three types of HL7 2.X batch scenarios:</span></span>  
  
- <span data-ttu-id="294b6-104">断片化した受信バッチのシナリオです。</span><span class="sxs-lookup"><span data-stu-id="294b6-104">Fragmented inbound batch scenario.</span></span> [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="294b6-105"> 別の出力メッセージには、これらのバッチを解析します。</span><span class="sxs-lookup"><span data-stu-id="294b6-105"> parses these batches into separate output messages.</span></span> [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="294b6-106"> 断片化したバッチでは、各メッセージの受信確認 (Ack) を送信します。</span><span class="sxs-lookup"><span data-stu-id="294b6-106"> sends acknowledgments (ACKs) for each message in a fragmented batch.</span></span>  
  
- <span data-ttu-id="294b6-107">バッチ処理/バッチ アウト シナリオ。</span><span class="sxs-lookup"><span data-stu-id="294b6-107">Batch in/batch out scenario.</span></span> <span data-ttu-id="294b6-108">これらは、バインドでバッチを[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]を断片化しますが、渡され、そのままのバッチとして送信します。</span><span class="sxs-lookup"><span data-stu-id="294b6-108">These are in-bound batches that [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] does not fragment, but passes through and sends as an intact batch.</span></span> <span data-ttu-id="294b6-109">場合[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]バッチでは、ACK ACK の送信には、バージョン ID が含まれています。</span><span class="sxs-lookup"><span data-stu-id="294b6-109">If [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] sends an ACK for the batch, the ACK includes a version ID.</span></span>  
  
- <span data-ttu-id="294b6-110">バッチの作成シナリオです。</span><span class="sxs-lookup"><span data-stu-id="294b6-110">Create-batch scenario.</span></span> <span data-ttu-id="294b6-111">このシナリオで[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]結合は、入力メッセージを出力バッチに分割します。</span><span class="sxs-lookup"><span data-stu-id="294b6-111">In this scenario, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] combines separate input messages into an output batch.</span></span>  
  
  <span data-ttu-id="294b6-112">2 つの方法のいずれかでバッチの書式を設定できます。</span><span class="sxs-lookup"><span data-stu-id="294b6-112">You can format batches in either of two ways:</span></span>  
  
- <span data-ttu-id="294b6-113">でファイルのヘッダーとトレーラー (FHS/FTS) バッチ ヘッダーとトレーラー (BHS/BTS)。</span><span class="sxs-lookup"><span data-stu-id="294b6-113">With a file header and trailer (FHS/FTS) and a batch header and trailer (BHS/BTS).</span></span>  
  
- <span data-ttu-id="294b6-114">でないファイルまたはバッチ ヘッダー/トレーラです。</span><span class="sxs-lookup"><span data-stu-id="294b6-114">With no file or batch headers/trailers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="294b6-115">参照</span><span class="sxs-lookup"><span data-stu-id="294b6-115">See Also</span></span>  
 <span data-ttu-id="294b6-116">[メッセージのバッチ処理](../../adapters-and-accelerators/accelerator-hl7/message-batching.md) </span><span class="sxs-lookup"><span data-stu-id="294b6-116">[Message Batching](../../adapters-and-accelerators/accelerator-hl7/message-batching.md) </span></span>  
 <span data-ttu-id="294b6-117">[バッチ処理のチュートリアル](../../adapters-and-accelerators/accelerator-hl7/batching-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="294b6-117">[Batching Tutorial](../../adapters-and-accelerators/accelerator-hl7/batching-tutorial.md) </span></span>  
 <span data-ttu-id="294b6-118">[パート 1: 断片化した受信バッチのシナリオ](../../adapters-and-accelerators/accelerator-hl7/part-1-fragmented-inbound-batch-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="294b6-118">[Part 1: Fragmented Inbound Batch Scenario](../../adapters-and-accelerators/accelerator-hl7/part-1-fragmented-inbound-batch-scenario.md) </span></span>  
 <span data-ttu-id="294b6-119">[パート 2: 内のバッチ/バッチ アウト シナリオ](../../adapters-and-accelerators/accelerator-hl7/part-2-batch-in-batch-out-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="294b6-119">[Part 2: Batch In/Batch Out Scenario](../../adapters-and-accelerators/accelerator-hl7/part-2-batch-in-batch-out-scenario.md) </span></span>  
 <span data-ttu-id="294b6-120">[パート 3: バッチの作成シナリオ](../../adapters-and-accelerators/accelerator-hl7/part-3-create-batch-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="294b6-120">[Part 3: Create-Batch Scenario](../../adapters-and-accelerators/accelerator-hl7/part-3-create-batch-scenario.md) </span></span>  
 [<span data-ttu-id="294b6-121">メッセージ処理</span><span class="sxs-lookup"><span data-stu-id="294b6-121">Message Processing</span></span>](../../adapters-and-accelerators/accelerator-hl7/message-processing.md)