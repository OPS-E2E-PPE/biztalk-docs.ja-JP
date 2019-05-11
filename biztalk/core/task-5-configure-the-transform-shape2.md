---
title: タスク 5:変換 Shape2 の構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3e92874e-9021-4cf6-bab6-d4173308c469
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4a41921914c2018da9e43442dfa94763fb4dc4f2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65299805"
---
# <a name="task-5-configure-the-transform-shape"></a><span data-ttu-id="d6203-102">タスク 5:変換図形を構成します。</span><span class="sxs-lookup"><span data-stu-id="d6203-102">Task 5: Configure the Transform Shape</span></span>
<span data-ttu-id="d6203-103">変換図形を構成するのにには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="d6203-103">Use the following procedure to configure the Transform shape.</span></span>  
  
### <a name="to-configure-the-transform-shape"></a><span data-ttu-id="d6203-104">変換図形を構成するには</span><span class="sxs-lookup"><span data-stu-id="d6203-104">To configure the Transform shape</span></span>  
  
1. <span data-ttu-id="d6203-105">メッセージの構築図形を ReceiveBeginDocResponse の後へドラッグします。</span><span class="sxs-lookup"><span data-stu-id="d6203-105">Drag a Construct Message shape after ReceiveBeginDocResponse.</span></span>  
  
   -   <span data-ttu-id="d6203-106">**構築メッセージ:** EditLineMsg</span><span class="sxs-lookup"><span data-stu-id="d6203-106">**Messages Constructed:** EditLineMsg</span></span>  
  
   -   <span data-ttu-id="d6203-107">**名:** ConstructEditLineMessageWithData</span><span class="sxs-lookup"><span data-stu-id="d6203-107">**Name:** ConstructEditLineMessageWithData</span></span>  
  
   1. <span data-ttu-id="d6203-108">右クリックし、真ん中の**図形の挿入**、し、**変換**します。</span><span class="sxs-lookup"><span data-stu-id="d6203-108">Right-click in the middle, select **Insert Shape**, and then select **Transform**.</span></span>  
  
       <span data-ttu-id="d6203-109">![変換図形の挿入](../core/media/insert-shape-transform.gif "insert_shape_transform")</span><span class="sxs-lookup"><span data-stu-id="d6203-109">![Insert Shape Transform](../core/media/insert-shape-transform.gif "insert_shape_transform")</span></span>  
  
   2. <span data-ttu-id="d6203-110">変換を使用して送信されるデータを送信するデータからデータをマップします。</span><span class="sxs-lookup"><span data-stu-id="d6203-110">Using Transform, map data from the data you are sending to the data that is sent.</span></span>  
  
      <span data-ttu-id="d6203-111">作業環境にはドキュメントを送信する (BeginDoc) ではなくすべての値を持つことのすべての可能なメッセージ、BeginDoc、EditLine、および EndDoc を構築することができます。</span><span class="sxs-lookup"><span data-stu-id="d6203-111">For your work environment you would send a document (instead of BeginDoc) with all values possible allowing you to construct all possible messages, BeginDoc, EditLine, and EndDoc.</span></span> <span data-ttu-id="d6203-112">この例では、ただし、データがあるのみハード コード化されました。</span><span class="sxs-lookup"><span data-stu-id="d6203-112">For this example, however, there is only hard coded data.</span></span>  
  
2. <span data-ttu-id="d6203-113">[Transform_1] を開くをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="d6203-113">Double-click Transform_1 to open.</span></span>  
  
   1.  <span data-ttu-id="d6203-114">ソースを選択し、下の追加行をクリックして**変数名**選択**BeginDocResponseMsg**します。</span><span class="sxs-lookup"><span data-stu-id="d6203-114">Select Source and click in the Add row under **Variable Name** and select **BeginDocResponseMsg**.</span></span>  
  
        <span data-ttu-id="d6203-115">![ソースの変換](../core/media/transform-source.gif "transform_source")</span><span class="sxs-lookup"><span data-stu-id="d6203-115">![Transform Source](../core/media/transform-source.gif "transform_source")</span></span>  
  
   2.  <span data-ttu-id="d6203-116">選択**先**行の追加 をクリック**変数名**を選択します**EditLineMsg**、 をクリック**ok**します。</span><span class="sxs-lookup"><span data-stu-id="d6203-116">Select **Destination** and click in the Add row under **Variable Name**, select **EditLineMsg**, and click **OK**.</span></span>  
  
        <span data-ttu-id="d6203-117">![変換先](../core/media/transform-destination.gif "transform_destination")</span><span class="sxs-lookup"><span data-stu-id="d6203-117">![Transform Destination](../core/media/transform-destination.gif "transform_destination")</span></span>  
  
3. <span data-ttu-id="d6203-118">ソリューション エクスプ ローラーでダブルクリック **[transform_1.btm]** マッピング ツールを開きます。</span><span class="sxs-lookup"><span data-stu-id="d6203-118">In the Solution Explorer, double-click **Transform_1.btm** to open the mapping tool.</span></span> <span data-ttu-id="d6203-119">次の 4 つの項目をリンクするには。</span><span class="sxs-lookup"><span data-stu-id="d6203-119">Link the following four items:</span></span>  
  
   - <span data-ttu-id="d6203-120">mnCMJobNo</span><span class="sxs-lookup"><span data-stu-id="d6203-120">mnCMJobNo</span></span>  
  
   - <span data-ttu-id="d6203-121">szCMComputerID</span><span class="sxs-lookup"><span data-stu-id="d6203-121">szCMComputerID</span></span>  
  
   - <span data-ttu-id="d6203-122">mnProcessID</span><span class="sxs-lookup"><span data-stu-id="d6203-122">mnProcessID</span></span>  
  
   - <span data-ttu-id="d6203-123">mnTransactionID</span><span class="sxs-lookup"><span data-stu-id="d6203-123">mnTransactionID</span></span>  
  
     <span data-ttu-id="d6203-124">![変換マッピングの例](../core/media/example-transformmapping.gif "example_transformmapping")</span><span class="sxs-lookup"><span data-stu-id="d6203-124">![Example Transform Mapping](../core/media/example-transformmapping.gif "example_transformmapping")</span></span>  
  
     <span data-ttu-id="d6203-125">この例では、使いやすさのハードコーディングされた値があります。</span><span class="sxs-lookup"><span data-stu-id="d6203-125">For ease of use, this example has hardcoded values.</span></span> <span data-ttu-id="d6203-126">送信先スキーマ内の項目をクリックし、次の値を設定します。</span><span class="sxs-lookup"><span data-stu-id="d6203-126">Click the item in the Destination Schema and set the following Value.</span></span>  
  
     <span data-ttu-id="d6203-127">![ハードコードされたマッピング](../core/media/hardcoded-mapping-example.gif "hardcoded_mapping_example")</span><span class="sxs-lookup"><span data-stu-id="d6203-127">![Hard Coded Mapping](../core/media/hardcoded-mapping-example.gif "hardcoded_mapping_example")</span></span>  
  
   ```  
   <?xml version="1.0" encoding="utf-8"?>  
   <ns0:F4211FSEditLine xmlns:ns0="http://schemas.microsoft.com/  
         [JDE://CSALES/B4200310]">  
      <ns0:cCMLineAction>A</ns0:cCMLineAction>  
      <ns0:cCMProcessEdits>1</ns0:cCMProcessEdits>  
      <ns0:cCMWriteToWFFlag>2</ns0:cCMWriteToWFFlag>  
      <ns0:szItemNo>210</ns0:szItemNo>  
      <ns0:mnQtyOrdered>1</ns0:mnQtyOrdered>  
      <ns0:cSalesTaxableYN>N</ns0:cSalesTaxableYN>  
      <ns0:szTransactionUOM>EA</ns0:szTransactionUOM>  
      <ns0:szCMProgramID>XMLInterop</ns0:szCMProgramID>  
      <ns0:szCMVersion>ZJDE0001</ns0:szCMVersion>  
   </ns0:F4211FSEditLine>  
   ```  
  
4. <span data-ttu-id="d6203-128">ReceiveEditLine の後に、メッセージの構築をドラッグします。</span><span class="sxs-lookup"><span data-stu-id="d6203-128">Drag a Construct Message after ReceiveEditLine.</span></span>  
  
   -   <span data-ttu-id="d6203-129">**構築メッセージ:** EndDocMsg</span><span class="sxs-lookup"><span data-stu-id="d6203-129">**Messages Constructed:** EndDocMsg</span></span>  
  
   -   <span data-ttu-id="d6203-130">**名:** ConstructEndDocMessageWithData</span><span class="sxs-lookup"><span data-stu-id="d6203-130">**Name:** ConstructEndDocMessageWithData</span></span>  
  
        <span data-ttu-id="d6203-131">クリックし、中央で右クリックして**図形の挿入**、し、**変換**します。</span><span class="sxs-lookup"><span data-stu-id="d6203-131">Right-click in the middle and select **Insert Shape**, and then select **Transform**.</span></span>  
  
5. <span data-ttu-id="d6203-132">開くには、[transform_2] をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="d6203-132">Double-click Transform_2 to open.</span></span>  
  
   1.  <span data-ttu-id="d6203-133">選択**ソース**[行の追加] をクリック**変数名**選択と**BeginDocResponseMsg**します。</span><span class="sxs-lookup"><span data-stu-id="d6203-133">Select **Source** and click in the Add row under **Variable Name** and select **BeginDocResponseMsg**.</span></span>  
  
   2.  <span data-ttu-id="d6203-134">選択**先**行の追加 をクリック**変数名**を選択します**EndDocMsg**、 をクリック**ok**します。</span><span class="sxs-lookup"><span data-stu-id="d6203-134">Select **Destination** and click in the Add row under **Variable Name**, select **EndDocMsg**, and click **OK**.</span></span>  
  
6. <span data-ttu-id="d6203-135">ソリューション エクスプ ローラーでダブルクリック **[transform_2.btm]** マッピング ツールを開きます。</span><span class="sxs-lookup"><span data-stu-id="d6203-135">In the Solution Explorer, double-click **Transform_2.btm** to open the mapping tool.</span></span> <span data-ttu-id="d6203-136">次の 4 つの項目をリンクするには。</span><span class="sxs-lookup"><span data-stu-id="d6203-136">Link the following four items:</span></span>  
  
   - <span data-ttu-id="d6203-137">mnCMJobNo</span><span class="sxs-lookup"><span data-stu-id="d6203-137">mnCMJobNo</span></span>  
  
   - <span data-ttu-id="d6203-138">szCMComputerID</span><span class="sxs-lookup"><span data-stu-id="d6203-138">szCMComputerID</span></span>  
  
   - <span data-ttu-id="d6203-139">mnProcessID</span><span class="sxs-lookup"><span data-stu-id="d6203-139">mnProcessID</span></span>  
  
   - <span data-ttu-id="d6203-140">mnTransactionID</span><span class="sxs-lookup"><span data-stu-id="d6203-140">mnTransactionID</span></span>  
  
     <span data-ttu-id="d6203-141">この例では、使いやすさのハードコーディングされた値があります。</span><span class="sxs-lookup"><span data-stu-id="d6203-141">For ease of use, this example has hardcoded values.</span></span> <span data-ttu-id="d6203-142">送信先スキーマ内の項目をクリックし、次の値を設定します。</span><span class="sxs-lookup"><span data-stu-id="d6203-142">Click the item in the Destination Schema and set the following Value.</span></span>  
  
   ```  
   <?xml version="1.0" encoding="utf-8"?>  
   <ns0:F4211FSEndDoc xmlns:ns0="http://schemas.microsoft.com/  
       [JDE://CSALES/B4200310]">  
      <ns0:szCMProgramID>XMLInterop</ns0:szCMProgramID>  
      <ns0:szCMVersion>ZJDE0001</ns0:szCMVersion>  
      <ns0:cCMUseWorkFiles>2</ns0:cCMUseWorkFiles>  
   </ns0:F4211FSEndDoc>  
   ```  
  
## <a name="see-also"></a><span data-ttu-id="d6203-143">参照</span><span class="sxs-lookup"><span data-stu-id="d6203-143">See Also</span></span>  
 <span data-ttu-id="d6203-144">[タスク 1:ポートを作成します。](../core/task-1-create-the-ports1.md) </span><span class="sxs-lookup"><span data-stu-id="d6203-144">[Task 1: Create the Ports](../core/task-1-create-the-ports1.md) </span></span>  
 <span data-ttu-id="d6203-145">[タスク 2:メッセージを作成します。](../core/task-2-create-the-messages2.md) </span><span class="sxs-lookup"><span data-stu-id="d6203-145">[Task 2: Create the Messages](../core/task-2-create-the-messages2.md) </span></span>  
 <span data-ttu-id="d6203-146">[タスク 3:受信図形と送信の構成](../core/task-3-configure-the-send-and-receive-shapes2.md) </span><span class="sxs-lookup"><span data-stu-id="d6203-146">[Task 3: Configure the Send and Receive Shapes](../core/task-3-configure-the-send-and-receive-shapes2.md) </span></span>  
 [<span data-ttu-id="d6203-147">タスク 4:メッセージの構築図形を構成します。</span><span class="sxs-lookup"><span data-stu-id="d6203-147">Task 4: Configure the Construct Message Shape</span></span>](../core/task-4-configure-the-construct-message-shape1.md)