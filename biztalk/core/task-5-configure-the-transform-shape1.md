---
title: "タスク 5: 構成変換 Shape1 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 93a73fd2-0f34-4681-8aed-7d54d69c86d3
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e76313ca87ad3138da83480b46a38a802d89ff15
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="task-5-configure-the-transform-shape"></a><span data-ttu-id="e53ad-102">タスク 5: 変換図形を構成します。</span><span class="sxs-lookup"><span data-stu-id="e53ad-102">Task 5: Configure the Transform Shape</span></span>
<span data-ttu-id="e53ad-103">変換図形を構成するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="e53ad-103">Use the following procedure to configure the Transform shape.</span></span>  
  
### <a name="to-configure-the-transform-shape"></a><span data-ttu-id="e53ad-104">変換図形を構成するには</span><span class="sxs-lookup"><span data-stu-id="e53ad-104">To configure the Transform shape</span></span>  
  
1.  <span data-ttu-id="e53ad-105">メッセージの構築図形を ReceiveBeginDocResponse の後へドラッグします。</span><span class="sxs-lookup"><span data-stu-id="e53ad-105">Drag a Construct Message shape after ReceiveBeginDocResponse.</span></span>  
  
    -   <span data-ttu-id="e53ad-106">**構築メッセージ:** editlinemsg</span><span class="sxs-lookup"><span data-stu-id="e53ad-106">**Messages Constructed:** EditLineMsg</span></span>  
  
    -   <span data-ttu-id="e53ad-107">**[名前]:** ConstructEditLineMessageWithData</span><span class="sxs-lookup"><span data-stu-id="e53ad-107">**Name:** ConstructEditLineMessageWithData</span></span>  
  
     <span data-ttu-id="e53ad-108">中央で、選択を右クリックして**図形の挿入**、し、**変換**です。</span><span class="sxs-lookup"><span data-stu-id="e53ad-108">Right-click in the middle, select **Insert Shape**, and then select **Transform**.</span></span>  
  
     ![](../core/media/jde-insert-shape-transform.gif "JDE_insert_shape_transform")  
  
     <span data-ttu-id="e53ad-109">変換を使用して、送信データと受信データをマップします。</span><span class="sxs-lookup"><span data-stu-id="e53ad-109">Using Transform, map data from the data you are sending to the data that is sent.</span></span>  
  
     <span data-ttu-id="e53ad-110">作業環境では、(BeginDoc の代わりに) ドキュメントを、すべてのメッセージを構築するために使用できるすべての値、BeginDoc、EditLine、および EndDoc と共に送信する場合があります。</span><span class="sxs-lookup"><span data-stu-id="e53ad-110">For your work environment you would send a document (instead of BeginDoc) with all values possible allowing you to construct all possible messages, BeginDoc, EditLine, and EndDoc.</span></span> <span data-ttu-id="e53ad-111">ただし、この例ではハードコードされたデータが使用されています。</span><span class="sxs-lookup"><span data-stu-id="e53ad-111">For this example, however, there is only hard coded data.</span></span>  
  
2.  <span data-ttu-id="e53ad-112">ダブルクリックして**変換 _ 1**を開きます。</span><span class="sxs-lookup"><span data-stu-id="e53ad-112">Double-click **Transform_1** to open.</span></span>  
  
    1.  <span data-ttu-id="e53ad-113">ソースを選択し、下の追加行をクリックして**変数名**選択**[begindocresponsemsg]**です。</span><span class="sxs-lookup"><span data-stu-id="e53ad-113">Select Source and click in the Add row under **Variable Name** and select **BeginDocResponseMsg**.</span></span>  
  
         ![](../core/media/jde-transform-source.gif "JDE_transform_source")  
  
    2.  <span data-ttu-id="e53ad-114">選択**先**下にある行の追加 をクリック**変数名**を選択**editlinemsg**、 をクリック**ok**です。</span><span class="sxs-lookup"><span data-stu-id="e53ad-114">Select **Destination** and click in the Add row under **Variable Name**, select **EditLineMsg**, and click **OK**.</span></span>  
  
         ![](../core/media/jde-transform-destination.gif "JDE_transform_destination")  
  
3.  <span data-ttu-id="e53ad-115">ソリューション エクスプ ローラーでダブルクリック**[transform_1.btm]**マッピング ツールを開きます。</span><span class="sxs-lookup"><span data-stu-id="e53ad-115">In the Solution Explorer, double-click **Transform_1.btm** to open the mapping tool.</span></span> <span data-ttu-id="e53ad-116">次の 4 つのアイテムをリンクします。</span><span class="sxs-lookup"><span data-stu-id="e53ad-116">Link the following four items:</span></span>  
  
    -   <span data-ttu-id="e53ad-117">mnCMJobNo</span><span class="sxs-lookup"><span data-stu-id="e53ad-117">mnCMJobNo</span></span>  
  
    -   <span data-ttu-id="e53ad-118">szCMComputerID</span><span class="sxs-lookup"><span data-stu-id="e53ad-118">szCMComputerID</span></span>  
  
    -   <span data-ttu-id="e53ad-119">mnProcessID</span><span class="sxs-lookup"><span data-stu-id="e53ad-119">mnProcessID</span></span>  
  
    -   <span data-ttu-id="e53ad-120">mnTransactionID</span><span class="sxs-lookup"><span data-stu-id="e53ad-120">mnTransactionID</span></span>  
  
     ![](../core/media/jde-example-transformmapping.gif "JDE_example_transformmapping")  
  
     <span data-ttu-id="e53ad-121">使いやすいように、この例では値がハードコードされています。</span><span class="sxs-lookup"><span data-stu-id="e53ad-121">For ease of use, this example has hardcoded values.</span></span> <span data-ttu-id="e53ad-122">送信先スキーマでアイテムをクリックし、次の値を設定します。</span><span class="sxs-lookup"><span data-stu-id="e53ad-122">Click the item in the Destination Schema and set the following Value.</span></span>  
  
     ![](../core/media/jde-hardcoded-mapping-example.gif "JDE_hardcoded_mapping_example")  
  
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
  
4.  <span data-ttu-id="e53ad-123">メッセージの構築図形を [ReceiveEditLine] の後へドラッグします。</span><span class="sxs-lookup"><span data-stu-id="e53ad-123">Drag a Construct Message after ReceiveEditLine.</span></span>  
  
    -   <span data-ttu-id="e53ad-124">**構築メッセージ:** enddocmsg</span><span class="sxs-lookup"><span data-stu-id="e53ad-124">**Messages Constructed:** EndDocMsg</span></span>  
  
    -   <span data-ttu-id="e53ad-125">**[名前]:** ConstructEndDocMessageWithData</span><span class="sxs-lookup"><span data-stu-id="e53ad-125">**Name:** ConstructEndDocMessageWithData</span></span>  
  
     <span data-ttu-id="e53ad-126">クリックし、中央で右クリック**図形の挿入**、し、**変換**です。</span><span class="sxs-lookup"><span data-stu-id="e53ad-126">Right-click in the middle and select **Insert Shape**, and then select **Transform**.</span></span>  
  
5.  <span data-ttu-id="e53ad-127">ダブルクリックして**[transform_2]**を開きます。</span><span class="sxs-lookup"><span data-stu-id="e53ad-127">Double-click **Transform_2** to open.</span></span>  
  
    1.  <span data-ttu-id="e53ad-128">選択**ソース**下にある行の追加 をクリック**変数名**選択**begindocresponsemsg**です。</span><span class="sxs-lookup"><span data-stu-id="e53ad-128">Select **Source** and click in the Add row under **Variable Name** and select **BeginDocResponseMsg**.</span></span>  
  
    2.  <span data-ttu-id="e53ad-129">選択**先**下にある行の追加 をクリック**変数名**を選択**enddocmsg**、 をクリック**ok**です。</span><span class="sxs-lookup"><span data-stu-id="e53ad-129">Select **Destination** and click in the Add row under **Variable Name**, select **EndDocMsg**, and click **OK**.</span></span>  
  
6.  <span data-ttu-id="e53ad-130">ソリューション エクスプ ローラーでダブルクリック**[transform_2.btm]**マッピング ツールを開きます。</span><span class="sxs-lookup"><span data-stu-id="e53ad-130">In the Solution Explorer, double-click **Transform_2.btm** to open the mapping tool.</span></span> <span data-ttu-id="e53ad-131">次の 4 つのアイテムをリンクします。</span><span class="sxs-lookup"><span data-stu-id="e53ad-131">Link the following four items:</span></span>  
  
    -   <span data-ttu-id="e53ad-132">mnCMJobNo</span><span class="sxs-lookup"><span data-stu-id="e53ad-132">mnCMJobNo</span></span>  
  
    -   <span data-ttu-id="e53ad-133">szCMComputerID</span><span class="sxs-lookup"><span data-stu-id="e53ad-133">szCMComputerID</span></span>  
  
    -   <span data-ttu-id="e53ad-134">mnProcessID</span><span class="sxs-lookup"><span data-stu-id="e53ad-134">mnProcessID</span></span>  
  
    -   <span data-ttu-id="e53ad-135">mnTransactionID</span><span class="sxs-lookup"><span data-stu-id="e53ad-135">mnTransactionID</span></span>  
  
     <span data-ttu-id="e53ad-136">使いやすいように、この例では値がハードコードされています。</span><span class="sxs-lookup"><span data-stu-id="e53ad-136">For ease of use, this example has hardcoded values.</span></span> <span data-ttu-id="e53ad-137">送信先スキーマでアイテムをクリックし、次の値を設定します。</span><span class="sxs-lookup"><span data-stu-id="e53ad-137">Click the item in the Destination Schema and set the following Value.</span></span>  
  
    ```  
    <?xml version="1.0" encoding="utf-8"?>  
    <ns0:F4211FSEndDoc xmlns:ns0="http://schemas.microsoft.com/  
        [JDE://CSALES/B4200310]">  
       <ns0:szCMProgramID>XMLInterop</ns0:szCMProgramID>  
       <ns0:szCMVersion>ZJDE0001</ns0:szCMVersion>  
       <ns0:cCMUseWorkFiles>2</ns0:cCMUseWorkFiles>  
    </ns0:F4211FSEndDoc>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="e53ad-138">参照</span><span class="sxs-lookup"><span data-stu-id="e53ad-138">See Also</span></span>  
 <span data-ttu-id="e53ad-139">[タスク 1: ポートを作成します。](../core/task-1-create-the-ports2.md) </span><span class="sxs-lookup"><span data-stu-id="e53ad-139">[Task 1: Create the Ports](../core/task-1-create-the-ports2.md) </span></span>  
 <span data-ttu-id="e53ad-140">[タスク 2: メッセージを作成します。](../core/task-2-create-the-messages1.md) </span><span class="sxs-lookup"><span data-stu-id="e53ad-140">[Task 2: Create the Messages](../core/task-2-create-the-messages1.md) </span></span>  
 <span data-ttu-id="e53ad-141">[タスク 3: 送信、受信図形と構成](../core/task-3-configure-the-send-and-receive-shapes1.md) </span><span class="sxs-lookup"><span data-stu-id="e53ad-141">[Task 3: Configure the Send and Receive Shapes](../core/task-3-configure-the-send-and-receive-shapes1.md) </span></span>  
 [<span data-ttu-id="e53ad-142">タスク 4: メッセージの構築図形を構成します。</span><span class="sxs-lookup"><span data-stu-id="e53ad-142">Task 4: Configure the Construct Message Shape</span></span>](../core/task-4-configure-the-construct-message-shape2.md)