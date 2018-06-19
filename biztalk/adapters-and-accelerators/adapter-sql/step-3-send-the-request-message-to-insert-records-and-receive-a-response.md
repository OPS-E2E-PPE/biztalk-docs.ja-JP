---
title: '手順 3: レコードを挿入し、応答を受信する要求メッセージの送信 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6a8a8906-7c7d-437c-9f04-345ad4ac460e
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: db97afa0de19e15e5005e5647279365ea6ba023b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22224090"
---
# <a name="step-3-send-the-request-message-to-insert-records-and-receive-a-response"></a><span data-ttu-id="92700-102">手順 3: レコードを挿入し、応答を受信する要求メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="92700-102">Step 3: Send the Request Message to Insert Records and Receive a Response</span></span>
<span data-ttu-id="92700-103">![手順 4 の 3](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-3of4.gif "Step_3of4")</span><span class="sxs-lookup"><span data-stu-id="92700-103">![Step 3 of 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-3of4.gif "Step_3of4")</span></span>  
  
 <span data-ttu-id="92700-104">**所要時間:** 10 分</span><span class="sxs-lookup"><span data-stu-id="92700-104">**Time to complete:** 10 minutes</span></span>  
  
 <span data-ttu-id="92700-105">**目標:** にレコードを挿入する要求メッセージを送信するこの手順で、 **Purchase_Order**テーブルが表示され、応答を受信します。</span><span class="sxs-lookup"><span data-stu-id="92700-105">**Objective:** In this step, you send the request message to insert records into the **Purchase_Order** table and receive a response.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="92700-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="92700-106">Prerequisites</span></span>  
 <span data-ttu-id="92700-107">完了する必要があります[手順 2: 挿入操作の要求メッセージに UPDATE_EMPLOYEE 応答メッセージをマップ](../../adapters-and-accelerators/adapter-sql/step-2-map-update_employee-response-to-insert-operation-request.md)です。</span><span class="sxs-lookup"><span data-stu-id="92700-107">You must have completed [Step 2: Map the UPDATE_EMPLOYEE Response Message to Insert Operation Request Message](../../adapters-and-accelerators/adapter-sql/step-2-map-update_employee-response-to-insert-operation-request.md).</span></span>  
  
### <a name="to-send-the-request-message-and-receive-a-response"></a><span data-ttu-id="92700-108">要求メッセージの送信し、応答を受信するには</span><span class="sxs-lookup"><span data-stu-id="92700-108">To send the request message and receive a response</span></span>  
  
1.  <span data-ttu-id="92700-109">次の図形 オーケストレーションを追加、**メッセージの構築**図形です。</span><span class="sxs-lookup"><span data-stu-id="92700-109">Add the following shapes to the orchestration under the **Construct Message** shape.</span></span>  
  
    |<span data-ttu-id="92700-110">図形</span><span class="sxs-lookup"><span data-stu-id="92700-110">Shape</span></span>|<span data-ttu-id="92700-111">図形の種類</span><span class="sxs-lookup"><span data-stu-id="92700-111">Shape Type</span></span>|<span data-ttu-id="92700-112">[プロパティ]</span><span class="sxs-lookup"><span data-stu-id="92700-112">Properties</span></span>|  
    |-----------|----------------|----------------|  
    |<span data-ttu-id="92700-113">SendInsertMessage</span><span class="sxs-lookup"><span data-stu-id="92700-113">SendInsertMessage</span></span>|<span data-ttu-id="92700-114">Send</span><span class="sxs-lookup"><span data-stu-id="92700-114">Send</span></span>|<span data-ttu-id="92700-115">-設定**メッセージ**に*InsertPO*</span><span class="sxs-lookup"><span data-stu-id="92700-115">-   Set **Message** to *InsertPO*</span></span><br /><span data-ttu-id="92700-116">-設定**名前**に*SendInsertMessage*</span><span class="sxs-lookup"><span data-stu-id="92700-116">-   Set **Name** to *SendInsertMessage*</span></span>|  
    |<span data-ttu-id="92700-117">ReceiveInsertResponse</span><span class="sxs-lookup"><span data-stu-id="92700-117">ReceiveInsertResponse</span></span>|<span data-ttu-id="92700-118">Receive</span><span class="sxs-lookup"><span data-stu-id="92700-118">Receive</span></span>|<span data-ttu-id="92700-119">-設定**アクティブ**に*False*</span><span class="sxs-lookup"><span data-stu-id="92700-119">-   Set **Activate** to *False*</span></span><br /><span data-ttu-id="92700-120">-設定**メッセージ**に*InsertPOResponse*</span><span class="sxs-lookup"><span data-stu-id="92700-120">-   Set **Message** to *InsertPOResponse*</span></span><br /><span data-ttu-id="92700-121">-設定**名前**に*ReceiveInsertResponse*</span><span class="sxs-lookup"><span data-stu-id="92700-121">-   Set **Name** to *ReceiveInsertResponse*</span></span>|  
    |<span data-ttu-id="92700-122">SaveInsertResponse</span><span class="sxs-lookup"><span data-stu-id="92700-122">SaveInsertResponse</span></span>|<span data-ttu-id="92700-123">Send</span><span class="sxs-lookup"><span data-stu-id="92700-123">Send</span></span>|<span data-ttu-id="92700-124">-設定**メッセージ**に*InsertPOResponse*</span><span class="sxs-lookup"><span data-stu-id="92700-124">-   Set **Message** to *InsertPOResponse*</span></span><br /><span data-ttu-id="92700-125">-設定**名前**に*SaveInsertResponse*</span><span class="sxs-lookup"><span data-stu-id="92700-125">-   Set **Name** to *SaveInsertResponse*</span></span>|  
  
2.  <span data-ttu-id="92700-126">変更、 **SQLOutboundPort**で作成した[手順 2: SQL Server と応答の受信要求メッセージを送信](../../adapters-and-accelerators/adapter-sql/step-2-send-the-request-message-to-sql-server-and-receive-response.md)です。</span><span class="sxs-lookup"><span data-stu-id="92700-126">Modify the **SQLOutboundPort** you created in [Step 2: Send the Request Message to SQL Server and Receive Response](../../adapters-and-accelerators/adapter-sql/step-2-send-the-request-message-to-sql-server-and-receive-response.md).</span></span>  
  
    1.  <span data-ttu-id="92700-127">オーケストレーション デザイナーでポートを右クリックし、をクリックして**新しい操作**です。</span><span class="sxs-lookup"><span data-stu-id="92700-127">Right-click the port in the Orchestration Designer, and then click **New Operation**.</span></span> <span data-ttu-id="92700-128">新しい操作を追加するポートの形状変更**Operation_1**です。</span><span class="sxs-lookup"><span data-stu-id="92700-128">The port shape changes to add a new operation, **Operation_1**.</span></span>  
  
    2.  <span data-ttu-id="92700-129">をクリックして**Operation_1**プロパティ ウィンドウで、識別子の値を変更して**InsertPO**です。</span><span class="sxs-lookup"><span data-stu-id="92700-129">Click **Operation_1** and in the properties window, change the value of Identifier to **InsertPO**.</span></span>  
  
3.  <span data-ttu-id="92700-130">一方向の送信ポートをオーケストレーションに追加します。</span><span class="sxs-lookup"><span data-stu-id="92700-130">Add a one-way send port to the orchestration.</span></span> <span data-ttu-id="92700-131">挿入操作の応答メッセージを送信するのににはこのポートを使用します。</span><span class="sxs-lookup"><span data-stu-id="92700-131">You will use this port to send the response message for the Insert operation.</span></span> <span data-ttu-id="92700-132">ポートの次のプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="92700-132">Set the following properties for the port.</span></span>  
  
    |<span data-ttu-id="92700-133">このプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="92700-133">Set this property</span></span>|<span data-ttu-id="92700-134">この値を</span><span class="sxs-lookup"><span data-stu-id="92700-134">To this value</span></span>|  
    |-----------------------|-------------------|  
    |<span data-ttu-id="92700-135">**通信方向**</span><span class="sxs-lookup"><span data-stu-id="92700-135">**Communication Direction**</span></span>|<span data-ttu-id="92700-136">Send</span><span class="sxs-lookup"><span data-stu-id="92700-136">Send</span></span>|  
    |<span data-ttu-id="92700-137">**通信方式**</span><span class="sxs-lookup"><span data-stu-id="92700-137">**Communication Pattern**</span></span>|<span data-ttu-id="92700-138">一方向</span><span class="sxs-lookup"><span data-stu-id="92700-138">One-Way</span></span>|  
    |<span data-ttu-id="92700-139">**[Identifier]**</span><span class="sxs-lookup"><span data-stu-id="92700-139">**Identifier**</span></span>|<span data-ttu-id="92700-140">SaveResponsePort</span><span class="sxs-lookup"><span data-stu-id="92700-140">SaveResponsePort</span></span>|  
  
     <span data-ttu-id="92700-141">また、"operation_1"にから、操作名を変更**InsertPO**です。</span><span class="sxs-lookup"><span data-stu-id="92700-141">Also, change the operation name from Operation_1 to **InsertPO**.</span></span>  
  
4.  <span data-ttu-id="92700-142">アクション図形にポートを接続します。</span><span class="sxs-lookup"><span data-stu-id="92700-142">Connect the port to action shapes.</span></span> <span data-ttu-id="92700-143">オーケストレーション デザイナーでのデザイン画面で、アクション図形のポートを対応する緑色のハンドルの緑色の矢印の形のハンドルをドラッグします。</span><span class="sxs-lookup"><span data-stu-id="92700-143">In Orchestration Designer, on the design surface, drag the green arrow-shaped handle for the port to the corresponding green handle of the action shape.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="92700-144">このステップでは、ドラッグ アンド ドロップを使用して、アクション図形にポートを接続します。</span><span class="sxs-lookup"><span data-stu-id="92700-144">In this step, you use the drag-and-drop method to connect ports to action shapes.</span></span> <span data-ttu-id="92700-145">アクション図形の操作プロパティを使用して、アクション図形をポートに接続することもできます。</span><span class="sxs-lookup"><span data-stu-id="92700-145">You could instead use the operation property of an action shape to connect the action shape to a port.</span></span>  
  
     <span data-ttu-id="92700-146">次のようにポートとアクション図形を接続します。</span><span class="sxs-lookup"><span data-stu-id="92700-146">Connect the ports and action shapes as follows:</span></span>  
  
    -   <span data-ttu-id="92700-147">接続、 **SendInsertMessage**にアクション図形、**要求**のハンドル、 **InsertPO**の操作、 **SQLOutboundPort**です。</span><span class="sxs-lookup"><span data-stu-id="92700-147">Connect the **SendInsertMessage** action shape to the **Request** handle of the **InsertPO** operation of the **SQLOutboundPort**.</span></span>  
  
    -   <span data-ttu-id="92700-148">接続、 **ReceiveInsertResponse**にアクション図形、**応答**のハンドル、 **InsertPO**の操作、 **SQLOutboundPort**です。</span><span class="sxs-lookup"><span data-stu-id="92700-148">Connect the **ReceiveInsertResponse** action shape to the **Response** handle of the **InsertPO** operation of the **SQLOutboundPort**.</span></span>  
  
    -   <span data-ttu-id="92700-149">接続、 **SaveInsertResponse**にアクション図形、**要求**のハンドル、 **SaveResponsePort**です。</span><span class="sxs-lookup"><span data-stu-id="92700-149">Connect the **SaveInsertResponse** action shape to the **Request** handle of the **SaveResponsePort**.</span></span>  
  
5.  <span data-ttu-id="92700-150">次の図では、実行中のオーケストレーションを示します。</span><span class="sxs-lookup"><span data-stu-id="92700-150">The following figure shows the in-progress orchestration.</span></span>  
  
     <span data-ttu-id="92700-151">![完成したオーケストレーション](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-09-comp-orch.gif "sql_adap_tut_09_comp_orch")</span><span class="sxs-lookup"><span data-stu-id="92700-151">![Complete orchestration](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-09-comp-orch.gif "sql_adap_tut_09_comp_orch")</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="92700-152">でしただけは何ですか。</span><span class="sxs-lookup"><span data-stu-id="92700-152">What did I just do?</span></span>  
 <span data-ttu-id="92700-153">レコードの挿入要求を送信する、 **Purchase_Order**テーブルが表示され、応答を受信します。</span><span class="sxs-lookup"><span data-stu-id="92700-153">You sent the request to insert records into the **Purchase_Order** table and receive a response.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="92700-154">次の手順</span><span class="sxs-lookup"><span data-stu-id="92700-154">Next Steps</span></span>  
 <span data-ttu-id="92700-155">」の説明に従って、プロジェクトをビルドする[手順 4: プロジェクトをビルド](../../adapters-and-accelerators/adapter-sql/step-4-build-the-project.md)です。</span><span class="sxs-lookup"><span data-stu-id="92700-155">You build the project, as described in [Step 4: Build the Project](../../adapters-and-accelerators/adapter-sql/step-4-build-the-project.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92700-156">参照</span><span class="sxs-lookup"><span data-stu-id="92700-156">See Also</span></span>  
 <span data-ttu-id="92700-157">[手順 2: マップ操作の要求メッセージを挿入する UPDATE_EMPLOYEE 応答メッセージ](../../adapters-and-accelerators/adapter-sql/step-2-map-update_employee-response-to-insert-operation-request.md) </span><span class="sxs-lookup"><span data-stu-id="92700-157">[Step 2: Map the UPDATE_EMPLOYEE Response Message to Insert Operation Request Message](../../adapters-and-accelerators/adapter-sql/step-2-map-update_employee-response-to-insert-operation-request.md) </span></span>  
 <span data-ttu-id="92700-158">[手順 4: プロジェクトをビルドします](../../adapters-and-accelerators/adapter-sql/step-4-build-the-project.md) </span><span class="sxs-lookup"><span data-stu-id="92700-158">[Step 4: Build the Project](../../adapters-and-accelerators/adapter-sql/step-4-build-the-project.md) </span></span>  
 [<span data-ttu-id="92700-159">レッスン 4: Purchase Order テーブルで挿入操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="92700-159">Lesson 4: Perform an Insert Operation on the Purchase Order Table</span></span>](../../adapters-and-accelerators/adapter-sql/lesson-4-perform-an-insert-operation-on-the-purchase-order-table.md)