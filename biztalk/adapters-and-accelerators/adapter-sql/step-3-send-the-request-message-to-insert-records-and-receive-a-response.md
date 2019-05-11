---
title: 手順 3:レコードを挿入し、応答を受信する要求メッセージの送信 |Microsoft Docs
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
ms.openlocfilehash: f0db2560d1ef8db10e68b67eeb34e6531e03afd6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65367691"
---
# <a name="step-3-send-the-request-message-to-insert-records-and-receive-a-response"></a><span data-ttu-id="13102-102">手順 3:レコードを挿入し、応答を受信する要求メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="13102-102">Step 3: Send the Request Message to Insert Records and Receive a Response</span></span>
<span data-ttu-id="13102-103">![手順 4 の 3](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-3of4.gif "Step_3of4")</span><span class="sxs-lookup"><span data-stu-id="13102-103">![Step 3 of 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-3of4.gif "Step_3of4")</span></span>  
  
 <span data-ttu-id="13102-104">**所要時間:** 10 分</span><span class="sxs-lookup"><span data-stu-id="13102-104">**Time to complete:** 10 minutes</span></span>  
  
 <span data-ttu-id="13102-105">**目標:** レコードを挿入する要求メッセージを送信するこの手順で、 **Purchase_Order**テーブルし、応答を受信します。</span><span class="sxs-lookup"><span data-stu-id="13102-105">**Objective:** In this step, you send the request message to insert records into the **Purchase_Order** table and receive a response.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="13102-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="13102-106">Prerequisites</span></span>  
 <span data-ttu-id="13102-107">完了する必要があります[手順 2。操作要求メッセージを挿入する UPDATE_EMPLOYEE 応答メッセージにマップ](../../adapters-and-accelerators/adapter-sql/step-2-map-update_employee-response-to-insert-operation-request.md)します。</span><span class="sxs-lookup"><span data-stu-id="13102-107">You must have completed [Step 2: Map the UPDATE_EMPLOYEE Response Message to Insert Operation Request Message](../../adapters-and-accelerators/adapter-sql/step-2-map-update_employee-response-to-insert-operation-request.md).</span></span>  
  
### <a name="to-send-the-request-message-and-receive-a-response"></a><span data-ttu-id="13102-108">要求メッセージを送信し、応答を受信するには</span><span class="sxs-lookup"><span data-stu-id="13102-108">To send the request message and receive a response</span></span>  
  
1.  <span data-ttu-id="13102-109">次の図形 オーケストレーションを追加、**メッセージの構築**図形。</span><span class="sxs-lookup"><span data-stu-id="13102-109">Add the following shapes to the orchestration under the **Construct Message** shape.</span></span>  
  
    |<span data-ttu-id="13102-110">図形</span><span class="sxs-lookup"><span data-stu-id="13102-110">Shape</span></span>|<span data-ttu-id="13102-111">図形の種類</span><span class="sxs-lookup"><span data-stu-id="13102-111">Shape Type</span></span>|<span data-ttu-id="13102-112">プロパティ</span><span class="sxs-lookup"><span data-stu-id="13102-112">Properties</span></span>|  
    |-----------|----------------|----------------|  
    |<span data-ttu-id="13102-113">SendInsertMessage</span><span class="sxs-lookup"><span data-stu-id="13102-113">SendInsertMessage</span></span>|<span data-ttu-id="13102-114">Send</span><span class="sxs-lookup"><span data-stu-id="13102-114">Send</span></span>|<span data-ttu-id="13102-115">-設定**メッセージ**に*InsertPO*</span><span class="sxs-lookup"><span data-stu-id="13102-115">-   Set **Message** to *InsertPO*</span></span><br /><span data-ttu-id="13102-116">-設定**名前**に*SendInsertMessage*</span><span class="sxs-lookup"><span data-stu-id="13102-116">-   Set **Name** to *SendInsertMessage*</span></span>|  
    |<span data-ttu-id="13102-117">ReceiveInsertResponse</span><span class="sxs-lookup"><span data-stu-id="13102-117">ReceiveInsertResponse</span></span>|<span data-ttu-id="13102-118">Receive</span><span class="sxs-lookup"><span data-stu-id="13102-118">Receive</span></span>|<span data-ttu-id="13102-119">-設定**アクティブ**に*False*</span><span class="sxs-lookup"><span data-stu-id="13102-119">-   Set **Activate** to *False*</span></span><br /><span data-ttu-id="13102-120">-設定**メッセージ**に*InsertPOResponse*</span><span class="sxs-lookup"><span data-stu-id="13102-120">-   Set **Message** to *InsertPOResponse*</span></span><br /><span data-ttu-id="13102-121">-設定**名前**に*ReceiveInsertResponse*</span><span class="sxs-lookup"><span data-stu-id="13102-121">-   Set **Name** to *ReceiveInsertResponse*</span></span>|  
    |<span data-ttu-id="13102-122">SaveInsertResponse</span><span class="sxs-lookup"><span data-stu-id="13102-122">SaveInsertResponse</span></span>|<span data-ttu-id="13102-123">Send</span><span class="sxs-lookup"><span data-stu-id="13102-123">Send</span></span>|<span data-ttu-id="13102-124">-設定**メッセージ**に*InsertPOResponse*</span><span class="sxs-lookup"><span data-stu-id="13102-124">-   Set **Message** to *InsertPOResponse*</span></span><br /><span data-ttu-id="13102-125">-設定**名前**に*SaveInsertResponse*</span><span class="sxs-lookup"><span data-stu-id="13102-125">-   Set **Name** to *SaveInsertResponse*</span></span>|  
  
2.  <span data-ttu-id="13102-126">変更、 **SQLOutboundPort**で作成した[手順 2。SQL Server への要求メッセージの送信し、応答受信](../../adapters-and-accelerators/adapter-sql/step-2-send-the-request-message-to-sql-server-and-receive-response.md)します。</span><span class="sxs-lookup"><span data-stu-id="13102-126">Modify the **SQLOutboundPort** you created in [Step 2: Send the Request Message to SQL Server and Receive Response](../../adapters-and-accelerators/adapter-sql/step-2-send-the-request-message-to-sql-server-and-receive-response.md).</span></span>  
  
    1.  <span data-ttu-id="13102-127">オーケストレーション デザイナでポートを右クリックし、をクリックし、**新しい操作**します。</span><span class="sxs-lookup"><span data-stu-id="13102-127">Right-click the port in the Orchestration Designer, and then click **New Operation**.</span></span> <span data-ttu-id="13102-128">ポート シェイプの変更、新しい操作を追加する**Operation_1**します。</span><span class="sxs-lookup"><span data-stu-id="13102-128">The port shape changes to add a new operation, **Operation_1**.</span></span>  
  
    2.  <span data-ttu-id="13102-129">クリックして**Operation_1**プロパティ ウィンドウで変更する識別子の値と**InsertPO**します。</span><span class="sxs-lookup"><span data-stu-id="13102-129">Click **Operation_1** and in the properties window, change the value of Identifier to **InsertPO**.</span></span>  
  
3.  <span data-ttu-id="13102-130">一方向の送信ポートをオーケストレーションに追加します。</span><span class="sxs-lookup"><span data-stu-id="13102-130">Add a one-way send port to the orchestration.</span></span> <span data-ttu-id="13102-131">挿入操作の応答メッセージを送信するのににはこのポートを使用します。</span><span class="sxs-lookup"><span data-stu-id="13102-131">You will use this port to send the response message for the Insert operation.</span></span> <span data-ttu-id="13102-132">次のポートのプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="13102-132">Set the following properties for the port.</span></span>  
  
    |<span data-ttu-id="13102-133">このプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="13102-133">Set this property</span></span>|<span data-ttu-id="13102-134">この値を</span><span class="sxs-lookup"><span data-stu-id="13102-134">To this value</span></span>|  
    |-----------------------|-------------------|  
    |<span data-ttu-id="13102-135">**通信方向**</span><span class="sxs-lookup"><span data-stu-id="13102-135">**Communication Direction**</span></span>|<span data-ttu-id="13102-136">Send</span><span class="sxs-lookup"><span data-stu-id="13102-136">Send</span></span>|  
    |<span data-ttu-id="13102-137">**通信方式**</span><span class="sxs-lookup"><span data-stu-id="13102-137">**Communication Pattern**</span></span>|<span data-ttu-id="13102-138">一方向</span><span class="sxs-lookup"><span data-stu-id="13102-138">One-Way</span></span>|  
    |<span data-ttu-id="13102-139">**[Identifier]**</span><span class="sxs-lookup"><span data-stu-id="13102-139">**Identifier**</span></span>|<span data-ttu-id="13102-140">SaveResponsePort</span><span class="sxs-lookup"><span data-stu-id="13102-140">SaveResponsePort</span></span>|  
  
     <span data-ttu-id="13102-141">また、変更操作名に Operation_1 **InsertPO**します。</span><span class="sxs-lookup"><span data-stu-id="13102-141">Also, change the operation name from Operation_1 to **InsertPO**.</span></span>  
  
4.  <span data-ttu-id="13102-142">アクション図形にポートを接続します。</span><span class="sxs-lookup"><span data-stu-id="13102-142">Connect the port to action shapes.</span></span> <span data-ttu-id="13102-143">オーケストレーション デザイナのデザイン画面で、アクション図形の緑、対応するポート ハンドルのために、緑色の矢印ハンドルをドラッグします。</span><span class="sxs-lookup"><span data-stu-id="13102-143">In Orchestration Designer, on the design surface, drag the green arrow-shaped handle for the port to the corresponding green handle of the action shape.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="13102-144">この手順では、ドラッグ アンド ドロップを使用するポートをアクション図形に接続します。</span><span class="sxs-lookup"><span data-stu-id="13102-144">In this step, you use the drag-and-drop method to connect ports to action shapes.</span></span> <span data-ttu-id="13102-145">アクション図形の操作のプロパティは、アクション図形をポートに接続するのに代わりに使用できます。</span><span class="sxs-lookup"><span data-stu-id="13102-145">You could instead use the operation property of an action shape to connect the action shape to a port.</span></span>  
  
     <span data-ttu-id="13102-146">次のように、ポートとアクション図形を接続します。</span><span class="sxs-lookup"><span data-stu-id="13102-146">Connect the ports and action shapes as follows:</span></span>  
  
    -   <span data-ttu-id="13102-147">接続、 **SendInsertMessage**アクション図形を**要求**の処理、 **InsertPO**の操作、 **SQLOutboundPort**します。</span><span class="sxs-lookup"><span data-stu-id="13102-147">Connect the **SendInsertMessage** action shape to the **Request** handle of the **InsertPO** operation of the **SQLOutboundPort**.</span></span>  
  
    -   <span data-ttu-id="13102-148">接続、 **ReceiveInsertResponse**アクション図形を**応答**の処理、 **InsertPO**の操作、 **SQLOutboundPort**します。</span><span class="sxs-lookup"><span data-stu-id="13102-148">Connect the **ReceiveInsertResponse** action shape to the **Response** handle of the **InsertPO** operation of the **SQLOutboundPort**.</span></span>  
  
    -   <span data-ttu-id="13102-149">接続、 **SaveInsertResponse**アクション図形を**要求**の処理、 **SaveResponsePort**します。</span><span class="sxs-lookup"><span data-stu-id="13102-149">Connect the **SaveInsertResponse** action shape to the **Request** handle of the **SaveResponsePort**.</span></span>  
  
5.  <span data-ttu-id="13102-150">次の図は、実行中のオーケストレーションを示します。</span><span class="sxs-lookup"><span data-stu-id="13102-150">The following figure shows the in-progress orchestration.</span></span>  
  
     <span data-ttu-id="13102-151">![完成したオーケストレーション](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-09-comp-orch.gif "sql_adap_tut_09_comp_orch")</span><span class="sxs-lookup"><span data-stu-id="13102-151">![Complete orchestration](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-09-comp-orch.gif "sql_adap_tut_09_comp_orch")</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="13102-152">でしただけ何か。</span><span class="sxs-lookup"><span data-stu-id="13102-152">What did I just do?</span></span>  
 <span data-ttu-id="13102-153">レコードを挿入する要求を送信した、 **Purchase_Order**テーブルし、応答を受信します。</span><span class="sxs-lookup"><span data-stu-id="13102-153">You sent the request to insert records into the **Purchase_Order** table and receive a response.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="13102-154">次の手順</span><span class="sxs-lookup"><span data-stu-id="13102-154">Next Steps</span></span>  
 <span data-ttu-id="13102-155">」の説明に従って、プロジェクトをビルドする[手順 4。プロジェクトをビルド](../../adapters-and-accelerators/adapter-sql/step-4-build-the-project.md)します。</span><span class="sxs-lookup"><span data-stu-id="13102-155">You build the project, as described in [Step 4: Build the Project](../../adapters-and-accelerators/adapter-sql/step-4-build-the-project.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13102-156">参照</span><span class="sxs-lookup"><span data-stu-id="13102-156">See Also</span></span>  
 <span data-ttu-id="13102-157">[手順 2:操作要求メッセージを挿入する UPDATE_EMPLOYEE 応答メッセージをマップします。](../../adapters-and-accelerators/adapter-sql/step-2-map-update_employee-response-to-insert-operation-request.md) </span><span class="sxs-lookup"><span data-stu-id="13102-157">[Step 2: Map the UPDATE_EMPLOYEE Response Message to Insert Operation Request Message](../../adapters-and-accelerators/adapter-sql/step-2-map-update_employee-response-to-insert-operation-request.md) </span></span>  
 <span data-ttu-id="13102-158">[手順 4:プロジェクトをビルドします](../../adapters-and-accelerators/adapter-sql/step-4-build-the-project.md) </span><span class="sxs-lookup"><span data-stu-id="13102-158">[Step 4: Build the Project](../../adapters-and-accelerators/adapter-sql/step-4-build-the-project.md) </span></span>  
 [<span data-ttu-id="13102-159">レッスン 4:注文テーブルに対して挿入操作を実行する</span><span class="sxs-lookup"><span data-stu-id="13102-159">Lesson 4: Perform an Insert Operation on the Purchase Order Table</span></span>](../../adapters-and-accelerators/adapter-sql/lesson-4-perform-an-insert-operation-on-the-purchase-order-table.md)