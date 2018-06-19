---
title: チュートリアルをバッチ処理 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- batching tutorial
- tutorials, batching tutorial
- batching tutorial, about the tutorial
- batching, tutorial
ms.assetid: e9010638-74cf-47cd-8cc9-9d6fd08a1b8d
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 27e2aff66468c697c92adb4c452250b70dae2e59
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22204386"
---
# <a name="batching-tutorial"></a><span data-ttu-id="4a594-102">バッチ処理のチュートリアル</span><span class="sxs-lookup"><span data-stu-id="4a594-102">Batching Tutorial</span></span>
<span data-ttu-id="4a594-103">このチュートリアルを使用するための手順の説明[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]を受け取り、バッチ処理されたメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="4a594-103">This tutorial provides step-by-step procedures for using [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] to receive and send batched messages.</span></span> <span data-ttu-id="4a594-104">バッチ処理と、1 つの複合メッセージとして、個々 のメッセージ (または受信確認) のグループの送受信が含まれます。</span><span class="sxs-lookup"><span data-stu-id="4a594-104">Batching involves receiving and/or sending a group of individual messages (or acknowledgments) as a single composite message.</span></span>  
  
 <span data-ttu-id="4a594-105">BTAHL7 では次の 3 つは、バッチ処理のシナリオをメッセージします。</span><span class="sxs-lookup"><span data-stu-id="4a594-105">BTAHL7 supports the following three message batching scenarios:</span></span>  
  
-   <span data-ttu-id="4a594-106">**断片化された受信バッチ**です。</span><span class="sxs-lookup"><span data-stu-id="4a594-106">**Fragmented inbound batch**.</span></span> <span data-ttu-id="4a594-107">このシナリオでは、BTAHL7 は、HL7 メッセージ バッチを受信し、送信先システムに個々 のメッセージをルーティングします。</span><span class="sxs-lookup"><span data-stu-id="4a594-107">In this scenario, BTAHL7 receives an HL7 message batch, and then routes the individual messages to the destination system.</span></span>  
  
-   <span data-ttu-id="4a594-108">**バッチ/アウト バッチ**です。BTAHL7 は、HL7 メッセージ バッチを受信、バッチ内の個々 のメッセージを確認し、送信先システムに、メッセージ バッチをルーティングします。</span><span class="sxs-lookup"><span data-stu-id="4a594-108">**Batch in/batch out**. BTAHL7 receives an HL7 message batch, verifies the individual messages within the batch, and then routes the message batch to the destination system.</span></span>  
  
-   <span data-ttu-id="4a594-109">**バッチ (または、送信バッチ処理) を作成**です。</span><span class="sxs-lookup"><span data-stu-id="4a594-109">**Create batch (or outbound batching)**.</span></span> <span data-ttu-id="4a594-110">BTAHL7 では、個々 のメッセージを受信し、送信先システムにルーティングする前にそれらをバッチ処理します。</span><span class="sxs-lookup"><span data-stu-id="4a594-110">BTAHL7 receives individual messages and batches them before routing them to the destination system.</span></span>  
  
 <span data-ttu-id="4a594-111">このチュートリアルには、3 つのバッチ処理のシナリオの各部分が含まれています。</span><span class="sxs-lookup"><span data-stu-id="4a594-111">This tutorial includes parts for each of the three batching scenarios.</span></span> <span data-ttu-id="4a594-112">指定された順序で、チュートリアルの 3 つの部分を使用します。第 1 部には、第 2 部と第 3 部の前提条件となる手順が含まれています。</span><span class="sxs-lookup"><span data-stu-id="4a594-112">Use the three parts of the tutorial in the order provided; part 1 contains prerequisite steps for part 2 and part 3.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4a594-113">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="4a594-113">In This Section</span></span>  
  
-   [<span data-ttu-id="4a594-114">バッチ処理のチュートリアルを使用する準備をしています</span><span class="sxs-lookup"><span data-stu-id="4a594-114">Preparing to Use the Batching Tutorial</span></span>](../../adapters-and-accelerators/accelerator-hl7/preparing-to-use-the-batching-tutorial.md)  
  
-   [<span data-ttu-id="4a594-115">パート 1: 断片化した受信バッチのシナリオ</span><span class="sxs-lookup"><span data-stu-id="4a594-115">Part 1: Fragmented Inbound Batch Scenario</span></span>](../../adapters-and-accelerators/accelerator-hl7/part-1-fragmented-inbound-batch-scenario.md)  
  
-   [<span data-ttu-id="4a594-116">パート 2: バッチのシナリオをバッチ処理/</span><span class="sxs-lookup"><span data-stu-id="4a594-116">Part 2: Batch In/Batch Out Scenario</span></span>](../../adapters-and-accelerators/accelerator-hl7/part-2-batch-in-batch-out-scenario.md)  
  
-   [<span data-ttu-id="4a594-117">パート 3: 作成するバッチのシナリオ</span><span class="sxs-lookup"><span data-stu-id="4a594-117">Part 3: Create-Batch Scenario</span></span>](../../adapters-and-accelerators/accelerator-hl7/part-3-create-batch-scenario.md)