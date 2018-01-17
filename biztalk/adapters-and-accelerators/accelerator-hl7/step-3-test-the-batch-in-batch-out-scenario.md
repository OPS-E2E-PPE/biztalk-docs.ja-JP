---
title: "手順 3: テストのシナリオをバッチ内にバッチ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c487d39d-b2be-41d4-963e-d0ee9ba169fb
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d84c34eb3019f83ecd28f30425a93708affcecb2
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/17/2018
---
# <a name="step-3-test-the-batch-inbatch-out-scenario"></a><span data-ttu-id="4dd15-102">手順 3: テストのバッチ処理/シナリオをバッチ処理</span><span class="sxs-lookup"><span data-stu-id="4dd15-102">Step 3: Test the Batch In/Batch Out Scenario</span></span>
<span data-ttu-id="4dd15-103">この手順では、バッチをテストでバッチをチュートリアルでのバッチ処理のテスト インスタンスの削除/フォルダーにメッセージをバッチ処理/です。</span><span class="sxs-lookup"><span data-stu-id="4dd15-103">In this step, you test the Batch In/Batch Out tutorial by dropping a test instance of the batch in/batch out message into a folder.</span></span> <span data-ttu-id="4dd15-104">送信ポートを設定するにはメッセージを送信、受信ポートによって受信されます、および受信パイプラインが処理され、コピー先のフォルダーにドロップします。</span><span class="sxs-lookup"><span data-stu-id="4dd15-104">The send port that you set up will send the message, the receive port will receive it, and the receive pipeline will process it and drop it into the destination folder.</span></span>  
  
### <a name="to-test-the-batch-inbatch-out-scenario"></a><span data-ttu-id="4dd15-105">バッチのテストでシナリオをバッチ処理/</span><span class="sxs-lookup"><span data-stu-id="4dd15-105">To test the Batch In/Batch Out scenario</span></span>  
  
1.  <span data-ttu-id="4dd15-106">使用して[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]エクスプ ローラーで、参照、  **\<*ドライブ*\>: \Batching Tutorial\Instances**フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="4dd15-106">Using [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Explorer, browse to the **\<*drive*\>:\Batching Tutorial\Instances** folder.</span></span>  
  
2.  <span data-ttu-id="4dd15-107">右クリックして**BatchInBatchOut.txt**、クリックして**コピー**です。</span><span class="sxs-lookup"><span data-stu-id="4dd15-107">Right click **BatchInBatchOut.txt**, and then click **Copy**.</span></span>  
  
3.  <span data-ttu-id="4dd15-108">参照、  **\<*ドライブ*\>: \Program Files\Microsoft BizTalk\<バージョン\>Accelerator HL7\SDK\End エンドツー エンド Tutorial\Tutorial_BTAHL7PickUp for**フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="4dd15-108">Browse to the **\<*drive*\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\End-to-End Tutorial\Tutorial_BTAHL7PickUp** folder.</span></span>  
  
4.  <span data-ttu-id="4dd15-109">フォルダーを右クリックし、をクリックして**貼り付け**です。</span><span class="sxs-lookup"><span data-stu-id="4dd15-109">Right-click the folder, and then click **Paste**.</span></span>  
  
### <a name="to-verify-the-results-of-the-batch-inbatch-out-tutorial"></a><span data-ttu-id="4dd15-110">バッチの結果を確認するでチュートリアルをバッチ処理/</span><span class="sxs-lookup"><span data-stu-id="4dd15-110">To verify the results of the Batch In/Batch Out Tutorial</span></span>  
  
-   <span data-ttu-id="4dd15-111">使用して[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]エクスプ ローラーで、参照、  **\<*ドライブ*\>: \Program Files\Microsoft BizTalk\<バージョン\>HL7\SDK\End エンドツー エンドのアクセラレータTutorial\Tutorial_BTAHL7Drop**フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="4dd15-111">Using [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Explorer, browse to the **\<*drive*\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\End-to-End Tutorial\Tutorial_BTAHL7Drop** folder.</span></span> <span data-ttu-id="4dd15-112">短時間後に、バッチ メッセージおよび受信確認の処理済みのインスタンスを参照してください、フォルダーに表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4dd15-112">After a short period, you should see the processed instance of the batch message, and an acknowledgment, appear in the folder.</span></span> <span data-ttu-id="4dd15-113">これらが表示されない場合は、確認、[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]イベント ビューアで、エラー メッセージ。</span><span class="sxs-lookup"><span data-stu-id="4dd15-113">If they do not appear, check the [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Event Viewer for an error message.</span></span> <span data-ttu-id="4dd15-114">各ファイル形式で別の名前を持つ必要があります\< *Guid*\>.txt です。</span><span class="sxs-lookup"><span data-stu-id="4dd15-114">Each file should have a different name in the form \<*Guid*\>.txt.</span></span>  
  
     <span data-ttu-id="4dd15-115">最初のメッセージは、2 つのメッセージで構成されるバッチにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4dd15-115">The first message should be the batch consisting of two messages.</span></span> <span data-ttu-id="4dd15-116">BizTalk Accelerator 用 HL7 (BTAHL7) は .txt ファイルでこれら 2 つのメッセージを順番に含まれます。</span><span class="sxs-lookup"><span data-stu-id="4dd15-116">BizTalk Accelerator for HL7 (BTAHL7) has included these two messages sequentially in the .txt file.</span></span> <span data-ttu-id="4dd15-117">このバッチでは、FHS/FTS と BHS/BTS タグは含まれません。</span><span class="sxs-lookup"><span data-stu-id="4dd15-117">This batch does not contain FHS/FTS and BHS/BTS tags.</span></span> <span data-ttu-id="4dd15-118">バッチは、タグを含めるかすべて FHS/FTS および BHS/BTS、か、このバッチ メッセージ、FHS/FTS、BHS/BTS タグがないなどの必要があります。</span><span class="sxs-lookup"><span data-stu-id="4dd15-118">A batch must contain either all FHS/FTS and BHS/BTS tags, or like this batch message, no FHS/FTS and no BHS/BTS tags.</span></span>  
  
    |<span data-ttu-id="4dd15-119">MSH.9</span><span class="sxs-lookup"><span data-stu-id="4dd15-119">MSH.9</span></span>|<span data-ttu-id="4dd15-120">MSH.10</span><span class="sxs-lookup"><span data-stu-id="4dd15-120">MSH.10</span></span>|<span data-ttu-id="4dd15-121">MSH.3</span><span class="sxs-lookup"><span data-stu-id="4dd15-121">MSH.3</span></span>|<span data-ttu-id="4dd15-122">MSH.5</span><span class="sxs-lookup"><span data-stu-id="4dd15-122">MSH.5</span></span>|  
    |-----------|------------|-----------|-----------|  
    |<span data-ttu-id="4dd15-123">ADT^A03</span><span class="sxs-lookup"><span data-stu-id="4dd15-123">ADT^A03</span></span>|<span data-ttu-id="4dd15-124">000001</span><span class="sxs-lookup"><span data-stu-id="4dd15-124">000001</span></span>|<span data-ttu-id="4dd15-125">Tutorial_BatchSource</span><span class="sxs-lookup"><span data-stu-id="4dd15-125">Tutorial_BatchSource</span></span>|<span data-ttu-id="4dd15-126">MESA_IS</span><span class="sxs-lookup"><span data-stu-id="4dd15-126">MESA_IS</span></span>|  
    |<span data-ttu-id="4dd15-127">ADT^A03</span><span class="sxs-lookup"><span data-stu-id="4dd15-127">ADT^A03</span></span>|<span data-ttu-id="4dd15-128">000002</span><span class="sxs-lookup"><span data-stu-id="4dd15-128">000002</span></span>|<span data-ttu-id="4dd15-129">Tutorial_BatchSource</span><span class="sxs-lookup"><span data-stu-id="4dd15-129">Tutorial_BatchSource</span></span>|<span data-ttu-id="4dd15-130">MESA_IS</span><span class="sxs-lookup"><span data-stu-id="4dd15-130">MESA_IS</span></span>|  
  
     <span data-ttu-id="4dd15-131">2 番目のメッセージは、バッチ メッセージと、次のフィールドへの応答で送信される 1 つのアプリケーションの受信確認をする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4dd15-131">The second message should be a single application acknowledgment sent in response to the batch message, with the following fields:</span></span>  
  
    |<span data-ttu-id="4dd15-132">MSH.9</span><span class="sxs-lookup"><span data-stu-id="4dd15-132">MSH.9</span></span>|<span data-ttu-id="4dd15-133">MSH.3</span><span class="sxs-lookup"><span data-stu-id="4dd15-133">MSH.3</span></span>|<span data-ttu-id="4dd15-134">MSH.5</span><span class="sxs-lookup"><span data-stu-id="4dd15-134">MSH.5</span></span>|<span data-ttu-id="4dd15-135">MSA.1</span><span class="sxs-lookup"><span data-stu-id="4dd15-135">MSA.1</span></span>|<span data-ttu-id="4dd15-136">MSA.2</span><span class="sxs-lookup"><span data-stu-id="4dd15-136">MSA.2</span></span>|  
    |-----------|-----------|-----------|-----------|-----------|  
    |<span data-ttu-id="4dd15-137">ACK^A03^ACK</span><span class="sxs-lookup"><span data-stu-id="4dd15-137">ACK^A03^ACK</span></span>|<span data-ttu-id="4dd15-138">MESA_IS</span><span class="sxs-lookup"><span data-stu-id="4dd15-138">MESA_IS</span></span>|<span data-ttu-id="4dd15-139">Tutorial_BatchSource</span><span class="sxs-lookup"><span data-stu-id="4dd15-139">Tutorial_BatchSource</span></span>|<span data-ttu-id="4dd15-140">AA</span><span class="sxs-lookup"><span data-stu-id="4dd15-140">AA</span></span>|<span data-ttu-id="4dd15-141">000001</span><span class="sxs-lookup"><span data-stu-id="4dd15-141">000001</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4dd15-142">参照</span><span class="sxs-lookup"><span data-stu-id="4dd15-142">See Also</span></span>  
 <span data-ttu-id="4dd15-143">[パート 1: 断片化した受信バッチのシナリオ](../../adapters-and-accelerators/accelerator-hl7/part-1-fragmented-inbound-batch-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="4dd15-143">[Part 1: Fragmented Inbound Batch Scenario](../../adapters-and-accelerators/accelerator-hl7/part-1-fragmented-inbound-batch-scenario.md) </span></span>  
 [<span data-ttu-id="4dd15-144">パート 3: バッチの作成シナリオ</span><span class="sxs-lookup"><span data-stu-id="4dd15-144">Part 3: Create-Batch Scenario</span></span>](../../adapters-and-accelerators/accelerator-hl7/part-3-create-batch-scenario.md)