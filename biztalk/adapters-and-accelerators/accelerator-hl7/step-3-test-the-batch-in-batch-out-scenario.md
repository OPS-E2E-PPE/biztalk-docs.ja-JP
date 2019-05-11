---
title: 手順 3:テスト シナリオをバッチ内に Batch |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c487d39d-b2be-41d4-963e-d0ee9ba169fb
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2c619c6f6ba1ee874c6b6eb54b9e499957d1dcee
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65288190"
---
# <a name="step-3-test-the-batch-inbatch-out-scenario"></a><span data-ttu-id="bf555-102">手順 3:テストのバッチ処理/バッチ アウト シナリオ</span><span class="sxs-lookup"><span data-stu-id="bf555-102">Step 3: Test the Batch In/Batch Out Scenario</span></span>
<span data-ttu-id="bf555-103">この手順では、バッチをテストで/バッチ アウト チュートリアル で、バッチ内のテスト インスタンスを削除/フォルダーにメッセージをバッチ処理します。</span><span class="sxs-lookup"><span data-stu-id="bf555-103">In this step, you test the Batch In/Batch Out tutorial by dropping a test instance of the batch in/batch out message into a folder.</span></span> <span data-ttu-id="bf555-104">送信ポートを設定することは、メッセージを送信、受信ポートによって受信されます、および受信パイプラインが処理され、コピー先のフォルダーにドロップします。</span><span class="sxs-lookup"><span data-stu-id="bf555-104">The send port that you set up will send the message, the receive port will receive it, and the receive pipeline will process it and drop it into the destination folder.</span></span>  
  
### <a name="to-test-the-batch-inbatch-out-scenario"></a><span data-ttu-id="bf555-105">バッチをテストするで/バッチ アウト シナリオ</span><span class="sxs-lookup"><span data-stu-id="bf555-105">To test the Batch In/Batch Out scenario</span></span>  
  
1. <span data-ttu-id="bf555-106">使用して[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]エクスプ ローラーで、参照、  **\<*ドライブ*\>: \Batching Tutorial\Instances**フォルダー。</span><span class="sxs-lookup"><span data-stu-id="bf555-106">Using [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Explorer, browse to the **\<*drive*\>:\Batching Tutorial\Instances** folder.</span></span>  
  
2. <span data-ttu-id="bf555-107">右クリックして**BatchInBatchOut.txt**、 をクリックし、**コピー**します。</span><span class="sxs-lookup"><span data-stu-id="bf555-107">Right click **BatchInBatchOut.txt**, and then click **Copy**.</span></span>  
  
3. <span data-ttu-id="bf555-108">参照、  **\<*ドライブ*\>: \Program Files\Microsoft BizTalk\<バージョン\>Accelerator HL7\SDK\End ツー エンド Tutorial\Tutorial_BTAHL7PickUp for**フォルダー。</span><span class="sxs-lookup"><span data-stu-id="bf555-108">Browse to the **\<*drive*\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\End-to-End Tutorial\Tutorial_BTAHL7PickUp** folder.</span></span>  
  
4. <span data-ttu-id="bf555-109">フォルダーを右クリックし、**貼り付け**します。</span><span class="sxs-lookup"><span data-stu-id="bf555-109">Right-click the folder, and then click **Paste**.</span></span>  
  
### <a name="to-verify-the-results-of-the-batch-inbatch-out-tutorial"></a><span data-ttu-id="bf555-110">バッチの結果を確認するに/バッチ アウトのチュートリアル</span><span class="sxs-lookup"><span data-stu-id="bf555-110">To verify the results of the Batch In/Batch Out Tutorial</span></span>  
  
- <span data-ttu-id="bf555-111">使用して[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]エクスプ ローラーで、参照、  **\<*ドライブ*\>: \Program Files\Microsoft BizTalk\<バージョン\>HL7\SDK\End ツー エンドのアクセラレータTutorial\Tutorial_BTAHL7Drop**フォルダー。</span><span class="sxs-lookup"><span data-stu-id="bf555-111">Using [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Explorer, browse to the **\<*drive*\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\End-to-End Tutorial\Tutorial_BTAHL7Drop** folder.</span></span> <span data-ttu-id="bf555-112">短時間では後は、必要があります、バッチ メッセージおよび受信確認の処理済みのインスタンスを参照してください、フォルダーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="bf555-112">After a short period, you should see the processed instance of the batch message, and an acknowledgment, appear in the folder.</span></span> <span data-ttu-id="bf555-113">確認して、表示されない場合、[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]イベント ビューアーにエラー メッセージ。</span><span class="sxs-lookup"><span data-stu-id="bf555-113">If they do not appear, check the [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Event Viewer for an error message.</span></span> <span data-ttu-id="bf555-114">各ファイルが別の名前をフォーム\< *Guid*\>.txt します。</span><span class="sxs-lookup"><span data-stu-id="bf555-114">Each file should have a different name in the form \<*Guid*\>.txt.</span></span>  
  
   <span data-ttu-id="bf555-115">2 つのメッセージで構成されるバッチの最初のメッセージがあります。</span><span class="sxs-lookup"><span data-stu-id="bf555-115">The first message should be the batch consisting of two messages.</span></span> <span data-ttu-id="bf555-116">BizTalk Accelerator 用 HL7 (BTAHL7) は .txt ファイルでこれら 2 つのメッセージを順番に含めるは。</span><span class="sxs-lookup"><span data-stu-id="bf555-116">BizTalk Accelerator for HL7 (BTAHL7) has included these two messages sequentially in the .txt file.</span></span> <span data-ttu-id="bf555-117">このバッチは FHS/FTS と BHS/BTS タグは含まれません。</span><span class="sxs-lookup"><span data-stu-id="bf555-117">This batch does not contain FHS/FTS and BHS/BTS tags.</span></span> <span data-ttu-id="bf555-118">バッチは、タグを含む、すべて FHS/FTS および BHS/BTS、かなどのバッチ メッセージをこの、FHS/FTS BHS/BTS タグがありません必要があります。</span><span class="sxs-lookup"><span data-stu-id="bf555-118">A batch must contain either all FHS/FTS and BHS/BTS tags, or like this batch message, no FHS/FTS and no BHS/BTS tags.</span></span>  
  
  |<span data-ttu-id="bf555-119">MSH.9</span><span class="sxs-lookup"><span data-stu-id="bf555-119">MSH.9</span></span>|<span data-ttu-id="bf555-120">MSH.10</span><span class="sxs-lookup"><span data-stu-id="bf555-120">MSH.10</span></span>|<span data-ttu-id="bf555-121">MSH.3</span><span class="sxs-lookup"><span data-stu-id="bf555-121">MSH.3</span></span>|<span data-ttu-id="bf555-122">MSH.5</span><span class="sxs-lookup"><span data-stu-id="bf555-122">MSH.5</span></span>|  
  |-----------|------------|-----------|-----------|  
  |<span data-ttu-id="bf555-123">ADT^A03</span><span class="sxs-lookup"><span data-stu-id="bf555-123">ADT^A03</span></span>|<span data-ttu-id="bf555-124">000001</span><span class="sxs-lookup"><span data-stu-id="bf555-124">000001</span></span>|<span data-ttu-id="bf555-125">Tutorial_BatchSource</span><span class="sxs-lookup"><span data-stu-id="bf555-125">Tutorial_BatchSource</span></span>|<span data-ttu-id="bf555-126">MESA_IS</span><span class="sxs-lookup"><span data-stu-id="bf555-126">MESA_IS</span></span>|  
  |<span data-ttu-id="bf555-127">ADT^A03</span><span class="sxs-lookup"><span data-stu-id="bf555-127">ADT^A03</span></span>|<span data-ttu-id="bf555-128">000002</span><span class="sxs-lookup"><span data-stu-id="bf555-128">000002</span></span>|<span data-ttu-id="bf555-129">Tutorial_BatchSource</span><span class="sxs-lookup"><span data-stu-id="bf555-129">Tutorial_BatchSource</span></span>|<span data-ttu-id="bf555-130">MESA_IS</span><span class="sxs-lookup"><span data-stu-id="bf555-130">MESA_IS</span></span>|  
  
   <span data-ttu-id="bf555-131">2 番目のメッセージは、次のフィールドで、バッチ メッセージへの応答で送信される 1 つのアプリケーションの受信確認をする必要があります。</span><span class="sxs-lookup"><span data-stu-id="bf555-131">The second message should be a single application acknowledgment sent in response to the batch message, with the following fields:</span></span>  
  
  |<span data-ttu-id="bf555-132">MSH.9</span><span class="sxs-lookup"><span data-stu-id="bf555-132">MSH.9</span></span>|<span data-ttu-id="bf555-133">MSH.3</span><span class="sxs-lookup"><span data-stu-id="bf555-133">MSH.3</span></span>|<span data-ttu-id="bf555-134">MSH.5</span><span class="sxs-lookup"><span data-stu-id="bf555-134">MSH.5</span></span>|<span data-ttu-id="bf555-135">MSA.1</span><span class="sxs-lookup"><span data-stu-id="bf555-135">MSA.1</span></span>|<span data-ttu-id="bf555-136">MSA.2</span><span class="sxs-lookup"><span data-stu-id="bf555-136">MSA.2</span></span>|  
  |-----------|-----------|-----------|-----------|-----------|  
  |<span data-ttu-id="bf555-137">ACK^A03^ACK</span><span class="sxs-lookup"><span data-stu-id="bf555-137">ACK^A03^ACK</span></span>|<span data-ttu-id="bf555-138">MESA_IS</span><span class="sxs-lookup"><span data-stu-id="bf555-138">MESA_IS</span></span>|<span data-ttu-id="bf555-139">Tutorial_BatchSource</span><span class="sxs-lookup"><span data-stu-id="bf555-139">Tutorial_BatchSource</span></span>|<span data-ttu-id="bf555-140">AA</span><span class="sxs-lookup"><span data-stu-id="bf555-140">AA</span></span>|<span data-ttu-id="bf555-141">000001</span><span class="sxs-lookup"><span data-stu-id="bf555-141">000001</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bf555-142">参照</span><span class="sxs-lookup"><span data-stu-id="bf555-142">See Also</span></span>  
 <span data-ttu-id="bf555-143">[パート 1: 断片化した受信バッチのシナリオ](../../adapters-and-accelerators/accelerator-hl7/part-1-fragmented-inbound-batch-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="bf555-143">[Part 1: Fragmented Inbound Batch Scenario](../../adapters-and-accelerators/accelerator-hl7/part-1-fragmented-inbound-batch-scenario.md) </span></span>  
 [<span data-ttu-id="bf555-144">パート 3: バッチの作成シナリオ</span><span class="sxs-lookup"><span data-stu-id="bf555-144">Part 3: Create-Batch Scenario</span></span>](../../adapters-and-accelerators/accelerator-hl7/part-3-create-batch-scenario.md)