---
title: バッチ メッセージの処理 |Microsoft ドキュメント
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
ms.openlocfilehash: aad80bb8fe9a59163ee17e7862bece728fdc52b3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22204762"
---
# <a name="batch-message-processing"></a><span data-ttu-id="f060e-102">バッチ メッセージの処理</span><span class="sxs-lookup"><span data-stu-id="f060e-102">Batch Message Processing</span></span>
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]<span data-ttu-id="f060e-103">BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) HL7 の 3 種類の処理 2.X バッチ シナリオ。</span><span class="sxs-lookup"><span data-stu-id="f060e-103"> BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) handles three types of HL7 2.X batch scenarios:</span></span>  
  
-   <span data-ttu-id="f060e-104">受信バッチの断片化されたシナリオです。</span><span class="sxs-lookup"><span data-stu-id="f060e-104">Fragmented inbound batch scenario.</span></span> [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="f060e-105">これらのバッチを別々 の出力メッセージに解析します。</span><span class="sxs-lookup"><span data-stu-id="f060e-105"> parses these batches into separate output messages.</span></span> [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="f060e-106">断片化されたバッチの各メッセージの受信確認 (Ack) を送信します。</span><span class="sxs-lookup"><span data-stu-id="f060e-106"> sends acknowledgments (ACKs) for each message in a fragmented batch.</span></span>  
  
-   <span data-ttu-id="f060e-107">バッチ/バッチ シナリオ アウトします。</span><span class="sxs-lookup"><span data-stu-id="f060e-107">Batch in/batch out scenario.</span></span> <span data-ttu-id="f060e-108">これらは、バインドでバッチを[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]を断片化します、を通過し、そのままのバッチとして送信します。</span><span class="sxs-lookup"><span data-stu-id="f060e-108">These are in-bound batches that [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] does not fragment, but passes through and sends as an intact batch.</span></span> <span data-ttu-id="f060e-109">場合[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]バッチ、ACK の ACK の送信には、バージョン ID が含まれています。</span><span class="sxs-lookup"><span data-stu-id="f060e-109">If [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] sends an ACK for the batch, the ACK includes a version ID.</span></span>  
  
-   <span data-ttu-id="f060e-110">作成するバッチのシナリオです。</span><span class="sxs-lookup"><span data-stu-id="f060e-110">Create-batch scenario.</span></span> <span data-ttu-id="f060e-111">このシナリオで[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]を組み合わせたものが、出力のバッチに入力メッセージを区別します。</span><span class="sxs-lookup"><span data-stu-id="f060e-111">In this scenario, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] combines separate input messages into an output batch.</span></span>  
  
 <span data-ttu-id="f060e-112">2 つの方法のいずれかでバッチの書式を設定することができます。</span><span class="sxs-lookup"><span data-stu-id="f060e-112">You can format batches in either of two ways:</span></span>  
  
-   <span data-ttu-id="f060e-113">でファイルのヘッダーとトレーラー (FHS/FTS) バッチ ヘッダーとトレーラー (BHS/BTS)。</span><span class="sxs-lookup"><span data-stu-id="f060e-113">With a file header and trailer (FHS/FTS) and a batch header and trailer (BHS/BTS).</span></span>  
  
-   <span data-ttu-id="f060e-114">でないファイルまたはバッチ ヘッダー/トレーラです。</span><span class="sxs-lookup"><span data-stu-id="f060e-114">With no file or batch headers/trailers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f060e-115">参照</span><span class="sxs-lookup"><span data-stu-id="f060e-115">See Also</span></span>  
 <span data-ttu-id="f060e-116">[メッセージのバッチ処理](../../adapters-and-accelerators/accelerator-hl7/message-batching.md) </span><span class="sxs-lookup"><span data-stu-id="f060e-116">[Message Batching](../../adapters-and-accelerators/accelerator-hl7/message-batching.md) </span></span>  
 <span data-ttu-id="f060e-117">[バッチ処理のチュートリアル](../../adapters-and-accelerators/accelerator-hl7/batching-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="f060e-117">[Batching Tutorial](../../adapters-and-accelerators/accelerator-hl7/batching-tutorial.md) </span></span>  
 <span data-ttu-id="f060e-118">[パート 1: 断片化した受信バッチのシナリオ](../../adapters-and-accelerators/accelerator-hl7/part-1-fragmented-inbound-batch-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="f060e-118">[Part 1: Fragmented Inbound Batch Scenario](../../adapters-and-accelerators/accelerator-hl7/part-1-fragmented-inbound-batch-scenario.md) </span></span>  
 <span data-ttu-id="f060e-119">[パート 2: バッチのシナリオをバッチ処理/](../../adapters-and-accelerators/accelerator-hl7/part-2-batch-in-batch-out-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="f060e-119">[Part 2: Batch In/Batch Out Scenario](../../adapters-and-accelerators/accelerator-hl7/part-2-batch-in-batch-out-scenario.md) </span></span>  
 <span data-ttu-id="f060e-120">[パート 3: 作成するバッチのシナリオ](../../adapters-and-accelerators/accelerator-hl7/part-3-create-batch-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="f060e-120">[Part 3: Create-Batch Scenario](../../adapters-and-accelerators/accelerator-hl7/part-3-create-batch-scenario.md) </span></span>  
 [<span data-ttu-id="f060e-121">メッセージの処理</span><span class="sxs-lookup"><span data-stu-id="f060e-121">Message Processing</span></span>](../../adapters-and-accelerators/accelerator-hl7/message-processing.md)