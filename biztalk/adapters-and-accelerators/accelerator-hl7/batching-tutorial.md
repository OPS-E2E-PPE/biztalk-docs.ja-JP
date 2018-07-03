---
title: バッチ処理のチュートリアル |Microsoft Docs
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
ms.openlocfilehash: 790303ac2026cbbce2fdb1c436e3dc8c7e9ff7f7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980091"
---
# <a name="batching-tutorial"></a><span data-ttu-id="d4587-102">バッチ処理のチュートリアル</span><span class="sxs-lookup"><span data-stu-id="d4587-102">Batching Tutorial</span></span>
<span data-ttu-id="d4587-103">このチュートリアルは、Microsoft の使用に関する詳しい手順を示します[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]を受信し、バッチ処理されたメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="d4587-103">This tutorial provides step-by-step procedures for using Microsoft [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] to receive and send batched messages.</span></span> <span data-ttu-id="d4587-104">バッチ処理と、1 つの複合メッセージとしてグループの個々 のメッセージ (または受信確認) を送受信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d4587-104">Batching involves receiving and/or sending a group of individual messages (or acknowledgments) as a single composite message.</span></span>  
  
 <span data-ttu-id="d4587-105">BTAHL7 サポートする次の 3 つのバッチ処理のシナリオをメッセージします。</span><span class="sxs-lookup"><span data-stu-id="d4587-105">BTAHL7 supports the following three message batching scenarios:</span></span>  
  
- <span data-ttu-id="d4587-106">**断片化した受信バッチ**します。</span><span class="sxs-lookup"><span data-stu-id="d4587-106">**Fragmented inbound batch**.</span></span> <span data-ttu-id="d4587-107">このシナリオでは、BTAHL7 は、HL7 メッセージのバッチを受信し、送信先システムに、個々 のメッセージをルーティングします。</span><span class="sxs-lookup"><span data-stu-id="d4587-107">In this scenario, BTAHL7 receives an HL7 message batch, and then routes the individual messages to the destination system.</span></span>  
  
- <span data-ttu-id="d4587-108">**バッチ処理/バッチ アウト**します。BTAHL7 は、HL7 メッセージのバッチを受信するには、バッチ内の個々 のメッセージを確認します。 および、送信先システムにメッセージのバッチをルーティングします。</span><span class="sxs-lookup"><span data-stu-id="d4587-108">**Batch in/batch out**. BTAHL7 receives an HL7 message batch, verifies the individual messages within the batch, and then routes the message batch to the destination system.</span></span>  
  
- <span data-ttu-id="d4587-109">**バッチ (または、送信バッチ処理) を作成**です。</span><span class="sxs-lookup"><span data-stu-id="d4587-109">**Create batch (or outbound batching)**.</span></span> <span data-ttu-id="d4587-110">BTAHL7 では、個々 のメッセージを受信し、送信先システムにルーティングする前にバッチとしてします。</span><span class="sxs-lookup"><span data-stu-id="d4587-110">BTAHL7 receives individual messages and batches them before routing them to the destination system.</span></span>  
  
  <span data-ttu-id="d4587-111">このチュートリアルには、3 つのバッチ処理のシナリオの各パーツが含まれています。</span><span class="sxs-lookup"><span data-stu-id="d4587-111">This tutorial includes parts for each of the three batching scenarios.</span></span> <span data-ttu-id="d4587-112">指定された順序で、チュートリアルの 3 つの部分を使用して、第 1 部には、第 2 部と第 3 部に必要な手順が含まれています。</span><span class="sxs-lookup"><span data-stu-id="d4587-112">Use the three parts of the tutorial in the order provided; part 1 contains prerequisite steps for part 2 and part 3.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d4587-113">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="d4587-113">In This Section</span></span>  
  
-   [<span data-ttu-id="d4587-114">バッチ処理のチュートリアルを使用するための準備</span><span class="sxs-lookup"><span data-stu-id="d4587-114">Preparing to Use the Batching Tutorial</span></span>](../../adapters-and-accelerators/accelerator-hl7/preparing-to-use-the-batching-tutorial.md)  
  
-   [<span data-ttu-id="d4587-115">パート 1: 断片化した受信バッチのシナリオ</span><span class="sxs-lookup"><span data-stu-id="d4587-115">Part 1: Fragmented Inbound Batch Scenario</span></span>](../../adapters-and-accelerators/accelerator-hl7/part-1-fragmented-inbound-batch-scenario.md)  
  
-   [<span data-ttu-id="d4587-116">パート 2: バッチ イン/バッチ アウトのシナリオ</span><span class="sxs-lookup"><span data-stu-id="d4587-116">Part 2: Batch In/Batch Out Scenario</span></span>](../../adapters-and-accelerators/accelerator-hl7/part-2-batch-in-batch-out-scenario.md)  
  
-   [<span data-ttu-id="d4587-117">パート 3: バッチの作成シナリオ</span><span class="sxs-lookup"><span data-stu-id="d4587-117">Part 3: Create-Batch Scenario</span></span>](../../adapters-and-accelerators/accelerator-hl7/part-3-create-batch-scenario.md)