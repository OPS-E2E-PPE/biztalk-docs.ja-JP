---
title: 手順 2:操作要求メッセージを挿入する UPDATE_EMPLOYEE 応答メッセージのマップ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8d12014a-0147-4227-88fa-0b290eff4cce
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 825eea8ba60d6b7767f9ea9b7536f8ed65470928
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65367793"
---
# <a name="step-2-map-the-updateemployee-response-message-to-insert-operation-request-message"></a><span data-ttu-id="73972-102">手順 2:操作要求メッセージを挿入する UPDATE_EMPLOYEE 応答メッセージをマップします。</span><span class="sxs-lookup"><span data-stu-id="73972-102">Step 2: Map the UPDATE_EMPLOYEE Response Message to Insert Operation Request Message</span></span>
<span data-ttu-id="73972-103">![手順 4 2](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-2of4.gif "Step_2of4")</span><span class="sxs-lookup"><span data-stu-id="73972-103">![Step 2 of 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-2of4.gif "Step_2of4")</span></span>  

 <span data-ttu-id="73972-104">**所要時間:** 10 分</span><span class="sxs-lookup"><span data-stu-id="73972-104">**Time to complete:** 10 minutes</span></span>  

 <span data-ttu-id="73972-105">**目標:** この手順で、挿入操作を実行する要求メッセージを作成する、 **Purchase_Order**テーブルし、の応答メッセージをマップし、 **UPDATE_EMPLOYEE**ストアド プロシージャを要求する挿入操作のメッセージ。</span><span class="sxs-lookup"><span data-stu-id="73972-105">**Objective:** In this step, you create the request message to perform an Insert operation on the **Purchase_Order** table and then map the response message for the **UPDATE_EMPLOYEE** stored procedure to the request message for the Insert operation.</span></span> <span data-ttu-id="73972-106">これにより、挿入する応答メッセージの値で渡す、 **Purchase_Order**テーブル。</span><span class="sxs-lookup"><span data-stu-id="73972-106">By doing so, you pass on the values in the response message to be inserted in the **Purchase_Order** table.</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="73972-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="73972-107">Prerequisites</span></span>  
 <span data-ttu-id="73972-108">完了する必要があります[手順 1。Purchase_Order テーブルに対する挿入操作の要求メッセージを作成](../../adapters-and-accelerators/adapter-sql/step-1-create-the-request-message-for-insert-operation-on-purchase-order-table.md)です。</span><span class="sxs-lookup"><span data-stu-id="73972-108">You must have completed [Step 1: Create the Request Message for Insert Operation on Purchase_Order Table](../../adapters-and-accelerators/adapter-sql/step-1-create-the-request-message-for-insert-operation-on-purchase-order-table.md).</span></span>  

### <a name="to-map-the-messages"></a><span data-ttu-id="73972-109">メッセージにマップするには</span><span class="sxs-lookup"><span data-stu-id="73972-109">To map the messages</span></span>  

1. <span data-ttu-id="73972-110">既存のオーケストレーションで、**挿入**のブロック、**判断**図形の下、 **ReceiveUpdateResponse**図形を追加、 **メッセージの割り当て**図形。</span><span class="sxs-lookup"><span data-stu-id="73972-110">To the existing orchestration, in the **Insert** block of the **Decide** shape, under the **ReceiveUpdateResponse** shape, add a **Message Assignment** shape.</span></span> <span data-ttu-id="73972-111">ツールボックスからドラッグして、**メッセージの割り当て**領域に図形が示されます。</span><span class="sxs-lookup"><span data-stu-id="73972-111">From the Toolbox, drag the **Message Assignment** shape to the space indicated.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="73972-112">ドロップすると、**メッセージの割り当て**オーケストレーション デザイナー、デザイン画面に図形を作成、それを囲む**メッセージの構築**図形。</span><span class="sxs-lookup"><span data-stu-id="73972-112">When you drop the **Message Assignment** shape onto the design surface, Orchestration Designer creates the enclosing **Construct Message** shape for you.</span></span>  

2. <span data-ttu-id="73972-113">デザイン サーフェイスを右クリックし、 **ConstructMessage_1**図形をクリックして**プロパティ ウィンドウ**します。</span><span class="sxs-lookup"><span data-stu-id="73972-113">On the design surface, right-click the **ConstructMessage_1** shape, and then click **Properties Window**.</span></span>  

3. <span data-ttu-id="73972-114">**プロパティ**のウィンドウ、 **ConstructMessage_1**図形で次の値を指定します。</span><span class="sxs-lookup"><span data-stu-id="73972-114">In the **Properties** pane for the **ConstructMessage_1** shape, specify the following values.</span></span>  


   |    <span data-ttu-id="73972-115">このプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="73972-115">Set this property</span></span>     |     <span data-ttu-id="73972-116">この値を</span><span class="sxs-lookup"><span data-stu-id="73972-116">To this value</span></span>      |
   |--------------------------|------------------------|
   | <span data-ttu-id="73972-117">**構築メッセージ**</span><span class="sxs-lookup"><span data-stu-id="73972-117">**Messages Constructed**</span></span> |        <span data-ttu-id="73972-118">InsertPO</span><span class="sxs-lookup"><span data-stu-id="73972-118">InsertPO</span></span>        |
   |         <span data-ttu-id="73972-119">**名前**</span><span class="sxs-lookup"><span data-stu-id="73972-119">**Name**</span></span>         | <span data-ttu-id="73972-120">ConstructInsertMessage</span><span class="sxs-lookup"><span data-stu-id="73972-120">ConstructInsertMessage</span></span> |


4. <span data-ttu-id="73972-121">ダブルクリックして、 **MessageAssignment**  図形を**BizTalk 式エディタ**します。</span><span class="sxs-lookup"><span data-stu-id="73972-121">Double-click the **MessageAssignment** shape to open the **BizTalk Expression Editor**.</span></span>  

5. <span data-ttu-id="73972-122">**BizTalk 式エディタ**以下を追加します。</span><span class="sxs-lookup"><span data-stu-id="73972-122">In the **BizTalk Expression Editor**, add the following:</span></span>  

   ```  
   InsertPO = UpdatePOMessageCreator.UpdatePOMessageCreator.XMLMessageCreator();  
   InsertPO(WCF.Action) = "TableOp/Insert/dbo/Purchase_Order";  
   ```  

    <span data-ttu-id="73972-123">ここでは、 **InsertPO**で作成したメッセージは、[手順 2。BizTalk オーケストレーションのメッセージを作成する](../../adapters-and-accelerators/adapter-sql/step-2-create-messages-for-biztalk-orchestrations.md)挿入操作の要求メッセージを送信するため、 **Purchase_Order**テーブル。</span><span class="sxs-lookup"><span data-stu-id="73972-123">Here, **InsertPO** is the message you created in [Step 2: Create Messages for BizTalk Orchestrations](../../adapters-and-accelerators/adapter-sql/step-2-create-messages-for-biztalk-orchestrations.md) for sending request messages for Insert operation on the **Purchase_Order** table.</span></span> <span data-ttu-id="73972-124">**MessageAssignment**図形を呼び出す、 **UpdatePOMessageCreator**要求メッセージを作成するクラス。</span><span class="sxs-lookup"><span data-stu-id="73972-124">In the **MessageAssignment** shape, you invoke the **UpdatePOMessageCreator** class to create a request message.</span></span> <span data-ttu-id="73972-125">また、要求メッセージの WCF アクションを設定します。</span><span class="sxs-lookup"><span data-stu-id="73972-125">Also, you set the WCF action for the request message.</span></span>  

6. <span data-ttu-id="73972-126">内で、**メッセージの構築**図形以降、**メッセージの割り当て**図形を追加、**変換**図形。</span><span class="sxs-lookup"><span data-stu-id="73972-126">Within the **Construct Message** shape and after the **Message Assignment** shape, add a **Transform** shape.</span></span>  

7. <span data-ttu-id="73972-127">**変換の構成**] ダイアログ ボックスで、左側のウィンドウから、**変換**ラベルで、[**ソース**します。</span><span class="sxs-lookup"><span data-stu-id="73972-127">In the **Transform Configuration** dialog box, from the left pane, under the **Transform** label, click **Source**.</span></span>  

8. <span data-ttu-id="73972-128">**送信元の変換**右側のボックスに、下の空白部分をクリックして、**変数名**、し、 **UpdateEmployeeResponse**します。</span><span class="sxs-lookup"><span data-stu-id="73972-128">From the **Source Transform** box on the right, click the space under the **Variable Name**, and then select **UpdateEmployeeResponse**.</span></span>  

    <span data-ttu-id="73972-129">![ソース スキーマのマッピングの選択](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-05-source-map.gif "sql_adap_tut_05_source_map")</span><span class="sxs-lookup"><span data-stu-id="73972-129">![Pick the source schema for the mapping](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-05-source-map.gif "sql_adap_tut_05_source_map")</span></span>  

9. <span data-ttu-id="73972-130">**変換の構成** ダイアログ ボックスで、左側のウィンドウから、**変換**ラベルで、をクリックして**先**します。</span><span class="sxs-lookup"><span data-stu-id="73972-130">In the **Transform Configuration** dialog box, from the left pane, under the **Transform** label, click **Destination**.</span></span>  

10. <span data-ttu-id="73972-131">**送信先の変換**右側のボックスに、下の空白部分をクリックして、**変数名**、し、 **InsertPO**します。</span><span class="sxs-lookup"><span data-stu-id="73972-131">From the **Destination Transform** box on the right, click the space under the **Variable Name**, and then select **InsertPO**.</span></span>  

     <span data-ttu-id="73972-132">![変換先スキーマのマッピングの選択](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-05-dest-map.gif "sql_adap_tut_05_dest_map")</span><span class="sxs-lookup"><span data-stu-id="73972-132">![Pick the destination schema for mapping](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-05-dest-map.gif "sql_adap_tut_05_dest_map")</span></span>  

11. <span data-ttu-id="73972-133">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="73972-133">Click **OK**.</span></span> <span data-ttu-id="73972-134">マップ ファイルが開きます。</span><span class="sxs-lookup"><span data-stu-id="73972-134">The map file opens.</span></span>  

12. <span data-ttu-id="73972-135">元と送信先スキーマ内のノードを展開します。</span><span class="sxs-lookup"><span data-stu-id="73972-135">Expand the nodes in the source and destination schemas.</span></span>  

13. <span data-ttu-id="73972-136">Employee_ID をマップし、両方のスキーマのフィールドの名前します。</span><span class="sxs-lookup"><span data-stu-id="73972-136">Map the Employee_ID and name fields in both the schemas.</span></span>  

    - <span data-ttu-id="73972-137">マップ、 **Employee_ID**をソース スキーマ (UPDATE_EMPLOYEEResponse) 内のノード、 **Employee_ID**送信先スキーマ (挿入) 内のノード。</span><span class="sxs-lookup"><span data-stu-id="73972-137">Map the **Employee_ID** node in the source schema (UPDATE_EMPLOYEEResponse) to the **Employee_ID** node in the destination schema (Insert).</span></span>  

    - <span data-ttu-id="73972-138">マップ、**名前**ソース スキーマのノードに、 **Employee_Name**送信先スキーマです。</span><span class="sxs-lookup"><span data-stu-id="73972-138">Map the **Name** node in the source schema to the **Employee_Name** in the destination schema.</span></span>  

      <span data-ttu-id="73972-139">次の図は、マップされたスキーマを示します。</span><span class="sxs-lookup"><span data-stu-id="73972-139">The following figure shows the mapped schemas.</span></span>  

      <span data-ttu-id="73972-140">![マップ元と送信先スキーマ](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-07-dest-map.gif "sql_adap_tut_07_dest_map")</span><span class="sxs-lookup"><span data-stu-id="73972-140">![Map the source and destination schemas](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-07-dest-map.gif "sql_adap_tut_07_dest_map")</span></span>  

      <span data-ttu-id="73972-141">保存して、マップを閉じます。</span><span class="sxs-lookup"><span data-stu-id="73972-141">Save and close the map.</span></span>  

14. <span data-ttu-id="73972-142">次の図は、実行中のオーケストレーションを示します。</span><span class="sxs-lookup"><span data-stu-id="73972-142">The following figure shows the in-progress orchestration.</span></span>  

     <span data-ttu-id="73972-143">![変換図形をオーケストレーション](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-08-map-orch.gif "sql_adap_tut_08_map_orch")</span><span class="sxs-lookup"><span data-stu-id="73972-143">![Orchestration with the transform shape](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-08-map-orch.gif "sql_adap_tut_08_map_orch")</span></span>  

## <a name="what-did-i-just-do"></a><span data-ttu-id="73972-144">でしただけ何か。</span><span class="sxs-lookup"><span data-stu-id="73972-144">What did I just do?</span></span>  
 <span data-ttu-id="73972-145">この手順では、レコードの挿入先のメッセージを作成、 **Purchase_Order**テーブルし、からの応答メッセージをマップし、 **UPDATE_EMPLOYEE**挿入ストアド プロシージャ、要求メッセージを操作です。</span><span class="sxs-lookup"><span data-stu-id="73972-145">In this step, you created a message to insert records into the **Purchase_Order** table and then mapped the response message from the **UPDATE_EMPLOYEE** stored procedure to the request message for the Insert operation.</span></span>  

## <a name="next-steps"></a><span data-ttu-id="73972-146">次の手順</span><span class="sxs-lookup"><span data-stu-id="73972-146">Next Steps</span></span>  
 <span data-ttu-id="73972-147">挿入操作を実行する要求メッセージを送信する、 **Purchase_Order**テーブルし、」の説明に従って、応答を受信[手順 3。レコードを挿入し、応答を受信する要求メッセージの送信](../../adapters-and-accelerators/adapter-sql/step-3-send-the-request-message-to-insert-records-and-receive-a-response.md)します。</span><span class="sxs-lookup"><span data-stu-id="73972-147">You send the request message to perform an Insert operation on the **Purchase_Order** table and receive a response, as described in [Step 3: Send the Request Message to Insert Records and Receive a Response](../../adapters-and-accelerators/adapter-sql/step-3-send-the-request-message-to-insert-records-and-receive-a-response.md).</span></span>  

## <a name="see-also"></a><span data-ttu-id="73972-148">参照</span><span class="sxs-lookup"><span data-stu-id="73972-148">See Also</span></span>  
 <span data-ttu-id="73972-149">[ステップ 1: Purchase_Order テーブルに対する挿入操作の要求メッセージを作成します。](../../adapters-and-accelerators/adapter-sql/step-1-create-the-request-message-for-insert-operation-on-purchase-order-table.md) </span><span class="sxs-lookup"><span data-stu-id="73972-149">[Step 1: Create the Request Message for Insert Operation on Purchase_Order Table](../../adapters-and-accelerators/adapter-sql/step-1-create-the-request-message-for-insert-operation-on-purchase-order-table.md) </span></span>  
 [<span data-ttu-id="73972-150">レッスン 4:注文テーブルに対して挿入操作を実行する</span><span class="sxs-lookup"><span data-stu-id="73972-150">Lesson 4: Perform an Insert Operation on the Purchase Order Table</span></span>](../../adapters-and-accelerators/adapter-sql/lesson-4-perform-an-insert-operation-on-the-purchase-order-table.md)