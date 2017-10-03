---
title: "手順 2: SQL Server に要求メッセージを送信し、応答を受信 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 864d2174-d54b-4383-92bf-f6808a2a904b
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ce820ab6a1914e44239313588eaaefeb696e61d6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-2-send-the-request-message-to-sql-server-and-receive-response"></a><span data-ttu-id="5a8e7-102">手順 2: SQL Server に要求メッセージを送信し、応答を受信</span><span class="sxs-lookup"><span data-stu-id="5a8e7-102">Step 2: Send the Request Message to SQL Server and Receive Response</span></span>
<span data-ttu-id="5a8e7-103">![手順 2 の 2](../../adapters-and-accelerators/adapter-sql/media/step-2of2.gif "Step_2of2")</span><span class="sxs-lookup"><span data-stu-id="5a8e7-103">![Step 2 of 2](../../adapters-and-accelerators/adapter-sql/media/step-2of2.gif "Step_2of2")</span></span>  
  
 <span data-ttu-id="5a8e7-104">**所要時間:** 10 分</span><span class="sxs-lookup"><span data-stu-id="5a8e7-104">**Time to complete:** 10 minutes</span></span>  
  
 <span data-ttu-id="5a8e7-105">**目標:**を実行する要求メッセージを送信するこの手順で、 **UPDATE_EMPLOYEE**ストアド プロシージャと、応答を受信します。</span><span class="sxs-lookup"><span data-stu-id="5a8e7-105">**Objective:** In this step, you send the request message to execute the **UPDATE_EMPLOYEE** stored procedure and receive the response.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="5a8e7-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="5a8e7-106">Prerequisites</span></span>  
 <span data-ttu-id="5a8e7-107">完了する必要があります[手順 1: UPDATE_EMPLOYEE ストアド プロシージャ用の要求メッセージを作成する](../../adapters-and-accelerators/adapter-sql/step-1-create-the-request-message-for-update-employee-stored-procedure.md)です。</span><span class="sxs-lookup"><span data-stu-id="5a8e7-107">You must have completed [Step 1: Create the Request Message for UPDATE_EMPLOYEE Stored Procedure](../../adapters-and-accelerators/adapter-sql/step-1-create-the-request-message-for-update-employee-stored-procedure.md).</span></span>  
  
### <a name="to-send-the-request-message-and-receive-a-response"></a><span data-ttu-id="5a8e7-108">要求メッセージの送信し、応答を受信するには</span><span class="sxs-lookup"><span data-stu-id="5a8e7-108">To send the request message and receive a response</span></span>  
  
1.  <span data-ttu-id="5a8e7-109">既存のオーケストレーションを下にある、**挿入**のブロック、**判断**図形を追加、**メッセージの割り当て**図形です。</span><span class="sxs-lookup"><span data-stu-id="5a8e7-109">To the existing orchestration, under the **Insert** block of the **Decide** shape, add a **Message Assignment** shape.</span></span> <span data-ttu-id="5a8e7-110">ツールボックスからドラッグして、**メッセージの割り当て**スペースに図形が示されます。</span><span class="sxs-lookup"><span data-stu-id="5a8e7-110">From the Toolbox, drag the **Message Assignment** shape to the space indicated.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5a8e7-111">ドロップすると、**メッセージの割り当て**オーケストレーション デザイナー、デザイン サーフェイスに図形を作成、外側にある**メッセージの構築**図形です。</span><span class="sxs-lookup"><span data-stu-id="5a8e7-111">When you drop the **Message Assignment** shape onto the design surface, Orchestration Designer creates the enclosing **Construct Message** shape for you.</span></span>  
  
2.  <span data-ttu-id="5a8e7-112">デザイン サーフェイスを右クリックし、 **ConstructMessage_1**図形をクリックして**プロパティ ウィンドウ**します。</span><span class="sxs-lookup"><span data-stu-id="5a8e7-112">On the design surface, right-click the **ConstructMessage_1** shape, and then click **Properties Window**.</span></span>  
  
3.  <span data-ttu-id="5a8e7-113">**プロパティ**のウィンドウ、 **ConstructMessage_1**図形で次の値を指定します。</span><span class="sxs-lookup"><span data-stu-id="5a8e7-113">In the **Properties** pane for the **ConstructMessage_1** shape, specify the following values.</span></span>  
  
    |<span data-ttu-id="5a8e7-114">このプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="5a8e7-114">Set this property</span></span>|<span data-ttu-id="5a8e7-115">この値を</span><span class="sxs-lookup"><span data-stu-id="5a8e7-115">To this value</span></span>|  
    |-----------------------|-------------------|  
    |<span data-ttu-id="5a8e7-116">**構築メッセージ**</span><span class="sxs-lookup"><span data-stu-id="5a8e7-116">**Messages Constructed**</span></span>|<span data-ttu-id="5a8e7-117">更新</span><span class="sxs-lookup"><span data-stu-id="5a8e7-117">UpdateEmployee</span></span>|  
    |<span data-ttu-id="5a8e7-118">**名前**</span><span class="sxs-lookup"><span data-stu-id="5a8e7-118">**Name**</span></span>|<span data-ttu-id="5a8e7-119">ConstructRequestMessage</span><span class="sxs-lookup"><span data-stu-id="5a8e7-119">ConstructRequestMessage</span></span>|  
  
4.  <span data-ttu-id="5a8e7-120">ダブルクリックして、 **MessageAssignment**図形を開くには、 **BizTalk 式エディタ**です。</span><span class="sxs-lookup"><span data-stu-id="5a8e7-120">Double-click the **MessageAssignment** shape to open the **BizTalk Expression Editor**.</span></span>  
  
5.  <span data-ttu-id="5a8e7-121">**BizTalk 式エディタ**以下を追加します。</span><span class="sxs-lookup"><span data-stu-id="5a8e7-121">In the **BizTalk Expression Editor**, add the following:</span></span>  
  
    ```  
    UpdateEmployee = UpdateEmployeeMessageCreator.UpdateEmployeeMessageCreator.XMLMessageCreator();  
    UpdateEmployee(WCF.Action) = "TypedProcedure/dbo/UPDATE_EMPLOYEE";  
    ```  
  
     <span data-ttu-id="5a8e7-122">ここでは、**更新**で作成したメッセージは、[手順 2: BizTalk オーケストレーションのメッセージの作成](../../adapters-and-accelerators/adapter-sql/step-2-create-messages-for-biztalk-orchestrations.md)要求メッセージを送信するため**UPDATE_EMPLOYEE**格納されています。プロシージャです。</span><span class="sxs-lookup"><span data-stu-id="5a8e7-122">Here, **UpdateEmployee** is the message you created in [Step 2: Create Messages for BizTalk Orchestrations](../../adapters-and-accelerators/adapter-sql/step-2-create-messages-for-biztalk-orchestrations.md) for sending request messages for **UPDATE_EMPLOYEE** stored procedure.</span></span> <span data-ttu-id="5a8e7-123">**MessageAssignment**図形を呼び出す、 **UpdateEmployeeMessageCreator**要求メッセージを作成するクラス。</span><span class="sxs-lookup"><span data-stu-id="5a8e7-123">In the **MessageAssignment** shape, you invoke the **UpdateEmployeeMessageCreator** class to create a request message.</span></span> <span data-ttu-id="5a8e7-124">また、要求メッセージの WCF アクションを設定します。</span><span class="sxs-lookup"><span data-stu-id="5a8e7-124">Also, you set the WCF action for the request message.</span></span>  
  
6.  <span data-ttu-id="5a8e7-125">次の図形 オーケストレーションを追加、**メッセージの割り当て**図形です。</span><span class="sxs-lookup"><span data-stu-id="5a8e7-125">Add the following shapes to the orchestration under the **Message Assignment** shape.</span></span>  
  
    |<span data-ttu-id="5a8e7-126">図形</span><span class="sxs-lookup"><span data-stu-id="5a8e7-126">Shape</span></span>|<span data-ttu-id="5a8e7-127">図形の種類</span><span class="sxs-lookup"><span data-stu-id="5a8e7-127">Shape Type</span></span>|<span data-ttu-id="5a8e7-128">[プロパティ]</span><span class="sxs-lookup"><span data-stu-id="5a8e7-128">Properties</span></span>|  
    |-----------|----------------|----------------|  
    |<span data-ttu-id="5a8e7-129">SendUpdateMessage</span><span class="sxs-lookup"><span data-stu-id="5a8e7-129">SendUpdateMessage</span></span>|<span data-ttu-id="5a8e7-130">Send</span><span class="sxs-lookup"><span data-stu-id="5a8e7-130">Send</span></span>|<span data-ttu-id="5a8e7-131">-設定**メッセージ**に*更新*</span><span class="sxs-lookup"><span data-stu-id="5a8e7-131">-   Set **Message** to *UpdateEmployee*</span></span><br /><span data-ttu-id="5a8e7-132">-設定**名前**に*SendUpdateMessage*</span><span class="sxs-lookup"><span data-stu-id="5a8e7-132">-   Set **Name** to *SendUpdateMessage*</span></span>|  
    |<span data-ttu-id="5a8e7-133">ReceiveUpdateResponse</span><span class="sxs-lookup"><span data-stu-id="5a8e7-133">ReceiveUpdateResponse</span></span>|<span data-ttu-id="5a8e7-134">Receive</span><span class="sxs-lookup"><span data-stu-id="5a8e7-134">Receive</span></span>|<span data-ttu-id="5a8e7-135">-設定**アクティブ**に*False*</span><span class="sxs-lookup"><span data-stu-id="5a8e7-135">-   Set **Activate** to *False*</span></span><br /><span data-ttu-id="5a8e7-136">-設定**メッセージ**に*UpdateEmployeeResponse*</span><span class="sxs-lookup"><span data-stu-id="5a8e7-136">-   Set **Message** to *UpdateEmployeeResponse*</span></span><br /><span data-ttu-id="5a8e7-137">-設定**名前**に*ReceiveUpdateResponse*</span><span class="sxs-lookup"><span data-stu-id="5a8e7-137">-   Set **Name** to *ReceiveUpdateResponse*</span></span>|  
  
7.  <span data-ttu-id="5a8e7-138">要求-応答送信ポートをオーケストレーションに追加します。</span><span class="sxs-lookup"><span data-stu-id="5a8e7-138">Add a request-response send port to the orchestration.</span></span> <span data-ttu-id="5a8e7-139">SQL Server に要求メッセージを送信し、応答を受信するにはこのポートを使用します。</span><span class="sxs-lookup"><span data-stu-id="5a8e7-139">You will use this port to send request messages to the SQL Server and receive response.</span></span> <span data-ttu-id="5a8e7-140">ポートの次のプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="5a8e7-140">Set the following properties for the port.</span></span>  
  
    |<span data-ttu-id="5a8e7-141">このプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="5a8e7-141">Set this property</span></span>|<span data-ttu-id="5a8e7-142">この値を</span><span class="sxs-lookup"><span data-stu-id="5a8e7-142">To this value</span></span>|  
    |-----------------------|-------------------|  
    |<span data-ttu-id="5a8e7-143">**通信方向**</span><span class="sxs-lookup"><span data-stu-id="5a8e7-143">**Communication Direction**</span></span>|<span data-ttu-id="5a8e7-144">送信 - 受信</span><span class="sxs-lookup"><span data-stu-id="5a8e7-144">Send-Receive</span></span>|  
    |<span data-ttu-id="5a8e7-145">**通信方式**</span><span class="sxs-lookup"><span data-stu-id="5a8e7-145">**Communication Pattern**</span></span>|<span data-ttu-id="5a8e7-146">要求-応答</span><span class="sxs-lookup"><span data-stu-id="5a8e7-146">Request-Response</span></span>|  
    |<span data-ttu-id="5a8e7-147">**[Identifier]**</span><span class="sxs-lookup"><span data-stu-id="5a8e7-147">**Identifier**</span></span>|<span data-ttu-id="5a8e7-148">SQLOutboundPort</span><span class="sxs-lookup"><span data-stu-id="5a8e7-148">SQLOutboundPort</span></span>|  
  
     <span data-ttu-id="5a8e7-149">また、"operation_1"にから、操作名を変更**UpdateEmp**です。</span><span class="sxs-lookup"><span data-stu-id="5a8e7-149">Also, change the operation name from Operation_1 to **UpdateEmp**.</span></span>  
  
8.  <span data-ttu-id="5a8e7-150">アクション図形にポートを接続します。</span><span class="sxs-lookup"><span data-stu-id="5a8e7-150">Connect the port to action shapes.</span></span> <span data-ttu-id="5a8e7-151">オーケストレーション デザイナーでのデザイン画面で、アクション図形のポートを対応する緑色のハンドルの緑色の矢印の形のハンドルをドラッグします。</span><span class="sxs-lookup"><span data-stu-id="5a8e7-151">In Orchestration Designer, on the design surface, drag the green arrow-shaped handle for the port to the corresponding green handle of the action shape.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5a8e7-152">このステップでは、ドラッグ アンド ドロップを使用して、アクション図形にポートを接続します。</span><span class="sxs-lookup"><span data-stu-id="5a8e7-152">In this step, you use the drag-and-drop method to connect ports to action shapes.</span></span> <span data-ttu-id="5a8e7-153">アクション図形の操作プロパティを使用して、アクション図形をポートに接続することもできます。</span><span class="sxs-lookup"><span data-stu-id="5a8e7-153">You could instead use the operation property of an action shape to connect the action shape to a port.</span></span>  
  
     <span data-ttu-id="5a8e7-154">次のようにポートとアクション図形を接続します。</span><span class="sxs-lookup"><span data-stu-id="5a8e7-154">Connect the ports and action shapes as follows:</span></span>  
  
    -   <span data-ttu-id="5a8e7-155">接続、 **SendUpdateMessage**にアクション図形、**要求**のハンドル、 **SQLOutboundPort**です。</span><span class="sxs-lookup"><span data-stu-id="5a8e7-155">Connect the **SendUpdateMessage** action shape to the **Request** handle of the **SQLOutboundPort**.</span></span>  
  
    -   <span data-ttu-id="5a8e7-156">接続、 **ReceiveUpdateResponse**にアクション図形、**応答**のハンドル、 **SQLOutboundPort**です。</span><span class="sxs-lookup"><span data-stu-id="5a8e7-156">Connect the **ReceiveUpdateResponse** action shape to the **Response** handle of the **SQLOutboundPort**.</span></span>  
  
9. <span data-ttu-id="5a8e7-157">次の図では、実行中のオーケストレーションを示します。</span><span class="sxs-lookup"><span data-stu-id="5a8e7-157">The following figure shows the in-progress orchestration.</span></span>  
  
     <span data-ttu-id="5a8e7-158">![更新メッセージを送信するオーケストレーションを更新](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-04-update-msg-orch.gif "sql_adap_tut_04_update_msg_orch")</span><span class="sxs-lookup"><span data-stu-id="5a8e7-158">![Updated orchestration to send update message](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-04-update-msg-orch.gif "sql_adap_tut_04_update_msg_orch")</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="5a8e7-159">でしただけは何ですか。</span><span class="sxs-lookup"><span data-stu-id="5a8e7-159">What did I just do?</span></span>  
 <span data-ttu-id="5a8e7-160">この手順で追加することによって、オーケストレーションを更新した、 **MessageAssignment**図形、**送信**と**受信**図形、およびポートです。</span><span class="sxs-lookup"><span data-stu-id="5a8e7-160">In this step, you updated the orchestration by adding a **MessageAssignment** shape, **Send** and **Receive** shapes, and a port.</span></span> <span data-ttu-id="5a8e7-161">図形を接続して、UDPATE_EMPLOYEE を実行する要求メッセージを送信ポートが要求メッセージと応答を受信します。</span><span class="sxs-lookup"><span data-stu-id="5a8e7-161">You connected the shapes and ports to send request message to execute the UDPATE_EMPLOYEE request message and receive the response.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="5a8e7-162">次の手順</span><span class="sxs-lookup"><span data-stu-id="5a8e7-162">Next Steps</span></span>  
 <span data-ttu-id="5a8e7-163">次の手順でに対して挿入操作を呼び出すオーケストレーション図形を追加する、 **Purchase_Order** 」の説明に従っての表に、[レッスン 4: Purchase Order テーブルに対して挿入操作を実行](../../adapters-and-accelerators/adapter-sql/lesson-4-perform-an-insert-operation-on-the-purchase-order-table.md)です。</span><span class="sxs-lookup"><span data-stu-id="5a8e7-163">In the next step, you add orchestration shapes to invoke the Insert operation on the **Purchase_Order** table, as described in [Lesson 4: Perform an Insert Operation on the Purchase Order Table](../../adapters-and-accelerators/adapter-sql/lesson-4-perform-an-insert-operation-on-the-purchase-order-table.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a8e7-164">参照</span><span class="sxs-lookup"><span data-stu-id="5a8e7-164">See Also</span></span>  
 <span data-ttu-id="5a8e7-165">[手順 1: UPDATE_EMPLOYEE の要求メッセージを作成するストアド プロシージャ](../../adapters-and-accelerators/adapter-sql/step-1-create-the-request-message-for-update-employee-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="5a8e7-165">[Step 1: Create the Request Message for UPDATE_EMPLOYEE Stored Procedure](../../adapters-and-accelerators/adapter-sql/step-1-create-the-request-message-for-update-employee-stored-procedure.md) </span></span>  
 [<span data-ttu-id="5a8e7-166">レッスン 3: 追加された新しい従業員を選択するストアド プロシージャを実行します。</span><span class="sxs-lookup"><span data-stu-id="5a8e7-166">Lesson 3: Execute a Stored Procedure to Select New Employees Added</span></span>](../../adapters-and-accelerators/adapter-sql/lesson-3-execute-a-stored-procedure-to-select-new-employees-added.md)