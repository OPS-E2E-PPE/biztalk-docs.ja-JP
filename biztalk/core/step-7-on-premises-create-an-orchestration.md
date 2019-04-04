---
title: '手順 7 (オンプレミス): オーケストレーションの作成 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7c0b6d0e-cf00-4eee-9b89-28210bad46f4
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fc072b664b453a3f10b624f75fe161a515ecc902
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975819"
---
# <a name="step-7-on-premises-create-an-orchestration"></a><span data-ttu-id="ab40c-102">手順 7 (オンプレミス): オーケストレーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="ab40c-102">Step 7 (On Premises): Create an Orchestration</span></span>
<span data-ttu-id="ab40c-103">後に、ビジネス シナリオに従って[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]販売注文メッセージを受信、Service Bus キューからメッセージの注文数量が 100 より大きいかどうかを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab40c-103">According to the business scenario, after [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] receives the sales order message from the Service Bus Queue, it needs to check whether the quantity ordered in the message is greater than 100.</span></span> <span data-ttu-id="ab40c-104">メッセージが挿入された数量が 100 より大きい場合、 **SalesOrder**テーブル。</span><span class="sxs-lookup"><span data-stu-id="ab40c-104">If the quantity is greater than 100, the message is inserted into the **SalesOrder** table.</span></span> <span data-ttu-id="ab40c-105">そうでない場合は、共有ファイルの場所にメッセージが送信されます。</span><span class="sxs-lookup"><span data-stu-id="ab40c-105">Otherwise, the message is sent to a shared file location.</span></span> <span data-ttu-id="ab40c-106">Northwind はオーケストレーションを作成することによってこのビジネス ロジックを実現します。</span><span class="sxs-lookup"><span data-stu-id="ab40c-106">Northwind achieves this business logic by creating an orchestration.</span></span> <span data-ttu-id="ab40c-107">このトピックでは、オーケストレーションの作成方法を、手順を追って説明します。</span><span class="sxs-lookup"><span data-stu-id="ab40c-107">This topic provides step-by-step guidance on how to create the orchestration.</span></span>  
  
### <a name="to-add-an-orchestration-to-the-includebtsbiztalkservernoversionincludesbtsbiztalkservernoversion-mdmd-project"></a><span data-ttu-id="ab40c-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] プロジェクトにオーケストレーションを追加するには</span><span class="sxs-lookup"><span data-stu-id="ab40c-108">To add an orchestration to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] project</span></span>  
  
1. <span data-ttu-id="ab40c-109">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]プロジェクトを右クリックをポイントして、既に作成した、**追加**、順にクリックします**新しい項目の**します。</span><span class="sxs-lookup"><span data-stu-id="ab40c-109">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] you already created, right-click the project, point to **Add**, and then click **New Item**.</span></span>  
  
2. <span data-ttu-id="ab40c-110">**新しい項目の**ダイアログ ボックスで、 **BizTalk オーケストレーション**、マップ名として入力`OrderProcessing.odx`、順にクリックします**追加**。</span><span class="sxs-lookup"><span data-stu-id="ab40c-110">In the **New Item** dialog box, select **BizTalk Orchestration**, enter the map name as `OrderProcessing.odx`, and then click **Add**.</span></span>  
  
## <a name="create-messages-for-the-orchestration"></a><span data-ttu-id="ab40c-111">オーケストレーションのメッセージの作成</span><span class="sxs-lookup"><span data-stu-id="ab40c-111">Create Messages for the Orchestration</span></span>  
 <span data-ttu-id="ab40c-112">先に生成したスキーマは、オーケストレーションのメッセージに求められる "型" を記述します。</span><span class="sxs-lookup"><span data-stu-id="ab40c-112">The schema that you generated earlier describes the “types” required for the messages in the orchestration.</span></span> <span data-ttu-id="ab40c-113">メッセージは通常、対応するスキーマによって定義された型の変数です。</span><span class="sxs-lookup"><span data-stu-id="ab40c-113">A message is typically a variable, the type for which defined by the corresponding schema.</span></span> <span data-ttu-id="ab40c-114">ここで、オーケストレーションのメッセージを作成し、先に生成したスキーマにリンクする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab40c-114">You must now create messages for the orchestration and link them to schemas you generated earlier.</span></span> <span data-ttu-id="ab40c-115">以下の 3 つのメッセージを作成してください。</span><span class="sxs-lookup"><span data-stu-id="ab40c-115">You need to create following three messages:</span></span>  
  
|<span data-ttu-id="ab40c-116">メッセージ名</span><span class="sxs-lookup"><span data-stu-id="ab40c-116">Message Name</span></span>|<span data-ttu-id="ab40c-117">対応するスキーマ</span><span class="sxs-lookup"><span data-stu-id="ab40c-117">Corresponds to schema</span></span>|  
|------------------|---------------------------|  
|<span data-ttu-id="ab40c-118">Message1_SO_Inbound</span><span class="sxs-lookup"><span data-stu-id="ab40c-118">Message1_SO_Inbound</span></span>|<span data-ttu-id="ab40c-119">このメッセージは、のインスタンス、 **ECommerceSalesOrder.xsd**スキーマ。</span><span class="sxs-lookup"><span data-stu-id="ab40c-119">This message is an instance of the **ECommerceSalesOrder.xsd** schema.</span></span>|  
|<span data-ttu-id="ab40c-120">Message2_SO_Inbound</span><span class="sxs-lookup"><span data-stu-id="ab40c-120">Message2_SO_Inbound</span></span>|<span data-ttu-id="ab40c-121">このメッセージのコピーである、 **Message1_SO_Inbound**します。</span><span class="sxs-lookup"><span data-stu-id="ab40c-121">This message is a copy of the **Message1_SO_Inbound**.</span></span> <span data-ttu-id="ab40c-122">ベスト プラクティスとして、メッセージのコピーを作成し、元のメッセージを残したまま、新しいメッセージを修正してください。</span><span class="sxs-lookup"><span data-stu-id="ab40c-122">As a best practice, you must create a copy of the message and then modify the new message, leaving the original message intact.</span></span> <span data-ttu-id="ab40c-123">詳細については、[BizTalk Server メッセージ](http://msdn.microsoft.com/library/aa560436)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ab40c-123">For more information, see [The BizTalk Server Message](http://msdn.microsoft.com/library/aa560436).</span></span>|  
|<span data-ttu-id="ab40c-124">Message1_SO_Outbound</span><span class="sxs-lookup"><span data-stu-id="ab40c-124">Message1_SO_Outbound</span></span>|<span data-ttu-id="ab40c-125">このメッセージは、のインスタンス、 **TableOperations.dbo.SalesOrder (Insert)** スキーマ。</span><span class="sxs-lookup"><span data-stu-id="ab40c-125">This message is an instance of the **TableOperations.dbo.SalesOrder (Insert)** schema.</span></span>|  
  
#### <a name="to-create-the-messages"></a><span data-ttu-id="ab40c-126">メッセージを作成するには</span><span class="sxs-lookup"><span data-stu-id="ab40c-126">To create the messages</span></span>  
  
1.  <span data-ttu-id="ab40c-127">開く、**オーケストレーション**がまだ開いていない場合、BizTalk プロジェクトのウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="ab40c-127">Open the **Orchestration View** window of the BizTalk project, if it is not already open.</span></span> <span data-ttu-id="ab40c-128">これを行うには、次のようにクリックします。**ビュー**、 をポイント**その他の Windows**、順にクリックします**オーケストレーション**します。</span><span class="sxs-lookup"><span data-stu-id="ab40c-128">To do so, click **View**, point to **Other Windows**, and then click **Orchestration View**.</span></span>  
  
2.  <span data-ttu-id="ab40c-129">オーケストレーション ビューで右クリックして**メッセージ**、 をクリックし、**新しいメッセージ**します。</span><span class="sxs-lookup"><span data-stu-id="ab40c-129">In Orchestration View, right-click **Messages**, and then click **New Message**.</span></span>  
  
3.  <span data-ttu-id="ab40c-130">新しく作成されたメッセージを右クリックし、**プロパティ ウィンドウ**します。</span><span class="sxs-lookup"><span data-stu-id="ab40c-130">Right-click the newly created message, and then select **Properties Window**.</span></span>  
  
4.  <span data-ttu-id="ab40c-131">**プロパティ**のウィンドウ、 **Message_1**次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="ab40c-131">In the **Properties** pane for the **Message_1**, do the following:</span></span>  
  
    |<span data-ttu-id="ab40c-132">プロパティ名</span><span class="sxs-lookup"><span data-stu-id="ab40c-132">Property name</span></span>|<span data-ttu-id="ab40c-133">実行するアクション</span><span class="sxs-lookup"><span data-stu-id="ab40c-133">Perform action</span></span>|  
    |-------------------|--------------------|  
    |<span data-ttu-id="ab40c-134">[Identifier]</span><span class="sxs-lookup"><span data-stu-id="ab40c-134">Identifier</span></span>|<span data-ttu-id="ab40c-135">入力します `Message1_SO_Inbound`</span><span class="sxs-lookup"><span data-stu-id="ab40c-135">Enter `Message1_SO_Inbound`</span></span>|  
    |<span data-ttu-id="ab40c-136">メッセージ型</span><span class="sxs-lookup"><span data-stu-id="ab40c-136">Message Type</span></span>|<span data-ttu-id="ab40c-137">ドロップダウン リストから展開**スキーマ**、し、 *OrderProcessingDemo.ECommerceSalesOrder*ここで、 *OrderProcessingDemo* BizTalk の名前を指定しますプロジェクトです。</span><span class="sxs-lookup"><span data-stu-id="ab40c-137">From the drop-down list, expand **Schemas**, and then select *OrderProcessingDemo.ECommerceSalesOrder*, where *OrderProcessingDemo* is the name of your BizTalk project.</span></span> <span data-ttu-id="ab40c-138">*ECommerceSalesOrder*は、Service Bus キューから受信した販売注文メッセージのスキーマです。</span><span class="sxs-lookup"><span data-stu-id="ab40c-138">*ECommerceSalesOrder* is the schema for the sales order message received from the Service Bus Queue.</span></span>|  
  
5.  <span data-ttu-id="ab40c-139">手順を繰り返し、以下の情報を使ってメッセージを作成します。</span><span class="sxs-lookup"><span data-stu-id="ab40c-139">Repeat the steps to create the messages with following details:</span></span>  
  
    |<span data-ttu-id="ab40c-140">メッセージ名</span><span class="sxs-lookup"><span data-stu-id="ab40c-140">Message name</span></span>||  
    |------------------|-|  
    |<span data-ttu-id="ab40c-141">Message2_SO_Inbound</span><span class="sxs-lookup"><span data-stu-id="ab40c-141">Message2_SO_Inbound</span></span>|<span data-ttu-id="ab40c-142">-設定**識別子**に `Message2_SO_Inbound`</span><span class="sxs-lookup"><span data-stu-id="ab40c-142">-   Set **Identifier** to `Message2_SO_Inbound`</span></span><br /><span data-ttu-id="ab40c-143">-設定**メッセージの種類**に*OrderProcessingDemo.ECommerceSalesOrder*</span><span class="sxs-lookup"><span data-stu-id="ab40c-143">-   Set **Message Type** to *OrderProcessingDemo.ECommerceSalesOrder*</span></span>|  
    |<span data-ttu-id="ab40c-144">Message1_SO_Outbound</span><span class="sxs-lookup"><span data-stu-id="ab40c-144">Message1_SO_Outbound</span></span>|<span data-ttu-id="ab40c-145">-設定**識別子**に `Message1_SO_Outound`</span><span class="sxs-lookup"><span data-stu-id="ab40c-145">-   Set **Identifier** to `Message1_SO_Outound`</span></span><br /><span data-ttu-id="ab40c-146">-設定**メッセージの種類**に*OrderProcessingDemo.TableOperation_dbo_SalesOrder.Insert*</span><span class="sxs-lookup"><span data-stu-id="ab40c-146">-   Set **Message Type** to *OrderProcessingDemo.TableOperation_dbo_SalesOrder.Insert*</span></span>|  
  
## <a name="add-shapes-to-the-orchestration"></a><span data-ttu-id="ab40c-147">オーケストレーションへの図形の追加</span><span class="sxs-lookup"><span data-stu-id="ab40c-147">Add Shapes to the Orchestration</span></span>  
 <span data-ttu-id="ab40c-148">オーケストレーション図形は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] アプリケーションのフローを定義します。</span><span class="sxs-lookup"><span data-stu-id="ab40c-148">Orchestration shapes define the flow of a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] application.</span></span> <span data-ttu-id="ab40c-149">このセクションでは、オーケストレーションに必要な図形を追加します。</span><span class="sxs-lookup"><span data-stu-id="ab40c-149">In this section, you add the required shapes to the orchestration.</span></span>  
  
#### <a name="to-add-shapes-to-the-orchestration"></a><span data-ttu-id="ab40c-150">オーケストレーションに図形を追加するには</span><span class="sxs-lookup"><span data-stu-id="ab40c-150">To add shapes to the orchestration</span></span>  
  
1.  <span data-ttu-id="ab40c-151">最初に、追加する必要があります、**受信**図形。</span><span class="sxs-lookup"><span data-stu-id="ab40c-151">To start with, you must add a **Receive** shape.</span></span> <span data-ttu-id="ab40c-152">この図形は、Service Bus キューから送信される販売注文メッセージを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="ab40c-152">This shape receives the incoming sales order message from the Service Bus Queue.</span></span> <span data-ttu-id="ab40c-153">受信図形に以下のプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="ab40c-153">Set the following properties on the receive shape.</span></span>  
  
    1.  <span data-ttu-id="ab40c-154">設定**アクティブ**に**True**します。</span><span class="sxs-lookup"><span data-stu-id="ab40c-154">Set **Activate** to **True**.</span></span>  
  
    2.  <span data-ttu-id="ab40c-155">設定**メッセージ**に**Message1_SO_Inbound**します。</span><span class="sxs-lookup"><span data-stu-id="ab40c-155">Set **Message** to **Message1_SO_Inbound**.</span></span>  
  
    3.  <span data-ttu-id="ab40c-156">設定**名前**に**ReceiveOrder**します。</span><span class="sxs-lookup"><span data-stu-id="ab40c-156">Set **Name** to **ReceiveOrder**.</span></span>  
  
2.  <span data-ttu-id="ab40c-157">先に述べたように、オーケストレーションで受信した元の販売注文メッセージのコピーを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab40c-157">As mentioned earlier, you must create a copy of the original sales order message that is received into the orchestration.</span></span>  
  
    1.  <span data-ttu-id="ab40c-158">ドラッグ アンド ドロップ、**メッセージの構築**図形の下、 **ReceiveOrder**図形。</span><span class="sxs-lookup"><span data-stu-id="ab40c-158">Drag-and-drop a **Construct Message** shape under the **ReceiveOrder** shape.</span></span> <span data-ttu-id="ab40c-159">Message2_SO_Inbound の種類のメッセージを構築するには、この図形を使用するための設定、**構築メッセージ**プロパティを**Message2_SO_Inbound**します。</span><span class="sxs-lookup"><span data-stu-id="ab40c-159">Because you use this shape to construct a message of type Message2_SO_Inbound, set the **Messages Constructed** property to **Message2_SO_Inbound**.</span></span>  
  
    2.  <span data-ttu-id="ab40c-160">追加、**メッセージの割り当て**図形内、**メッセージの構築**図形。</span><span class="sxs-lookup"><span data-stu-id="ab40c-160">Add a **Message Assignment** shape within the **Construct Message** shape.</span></span> <span data-ttu-id="ab40c-161">図形をダブルクリックして式エディターを開き、以下を追加します。</span><span class="sxs-lookup"><span data-stu-id="ab40c-161">Double-click the shape to open the Expression Editor, and add the following:</span></span>  
  
        ```  
        Message2_SO_Inbound = Message1_SO_Inbound; //copy the message  
        Message2_SO_Inbound(*) = Message1_SO_Inbound(*); //copy the context properties on the message  
        ```  
  
         <span data-ttu-id="ab40c-162">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ab40c-162">Click **OK**.</span></span>  
  
3.  <span data-ttu-id="ab40c-163">ビジネス シナリオに従って、注文項目の数量に応じて別の宛先にメッセージを送信しなければならない場合があります。</span><span class="sxs-lookup"><span data-stu-id="ab40c-163">According to the business scenario, the message must be sent to different destinations based on the quantity of ordered items.</span></span> <span data-ttu-id="ab40c-164">このため、受信する販売注文メッセージから、数量の値を抽出する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab40c-164">So, you must now extract the quantity value from the incoming sales order message.</span></span>  
  
    1.  <span data-ttu-id="ab40c-165">**数量**受信メッセージ (ECommerceSalesOrder.xsd) 内の要素には、注文数量の値が含まれています。</span><span class="sxs-lookup"><span data-stu-id="ab40c-165">The **Quantity** element in the inbound message (ECommerceSalesOrder.xsd) contains the value of the ordered quantity.</span></span> <span data-ttu-id="ab40c-166">オーケストレーションの式でその要素を使用できるよう、プロパティを昇格させる必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab40c-166">You must promote that property so that the element can be used within the expressions in the orchestration.</span></span> <span data-ttu-id="ab40c-167">プロパティを昇格するを開き、 **ECommerceSalesOrder.xsd**スキーマを右クリックして**数量**、 をポイント**昇格**、順にクリックします**クイック昇格**.</span><span class="sxs-lookup"><span data-stu-id="ab40c-167">To promote the property, open the **ECommerceSalesOrder.xsd** schema, right-click **Quantity**, point to **Promote**, and then click **Quick Promotions**.</span></span>  
  
    2.  <span data-ttu-id="ab40c-168">数量の値を格納するための変数を作成します。</span><span class="sxs-lookup"><span data-stu-id="ab40c-168">Create a variable to store the quantity value.</span></span> <span data-ttu-id="ab40c-169">変数を作成する、**オーケストレーション**、右クリック**変数**、順にクリックします**新しい変数**します。</span><span class="sxs-lookup"><span data-stu-id="ab40c-169">To create a variable, from the **Orchestration View**, right-click **Variables**, and then click **New Variable**.</span></span> <span data-ttu-id="ab40c-170">変数に以下のプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="ab40c-170">Set the following properties for the variable:</span></span>  
  
        |<span data-ttu-id="ab40c-171">プロパティ名</span><span class="sxs-lookup"><span data-stu-id="ab40c-171">Property name</span></span>|<span data-ttu-id="ab40c-172">値</span><span class="sxs-lookup"><span data-stu-id="ab40c-172">Value</span></span>|  
        |-------------------|-----------|  
        |<span data-ttu-id="ab40c-173">[Identifier]</span><span class="sxs-lookup"><span data-stu-id="ab40c-173">Identifier</span></span>|<span data-ttu-id="ab40c-174">入力します `quantityOrdered`</span><span class="sxs-lookup"><span data-stu-id="ab40c-174">Enter `quantityOrdered`</span></span>|  
        |<span data-ttu-id="ab40c-175">型</span><span class="sxs-lookup"><span data-stu-id="ab40c-175">Type</span></span>|<span data-ttu-id="ab40c-176">選択**Int32**します。</span><span class="sxs-lookup"><span data-stu-id="ab40c-176">Select **Int32**.</span></span>|  
  
    3.  <span data-ttu-id="ab40c-177">値を割り当てる必要があります、**数量**要素を**quantityOrdered**変数。</span><span class="sxs-lookup"><span data-stu-id="ab40c-177">You must now assign the value in the **Quantity** element to the **quantityOrdered** variable.</span></span> <span data-ttu-id="ab40c-178">ドラッグ アンド ドロップ、**式エディター**後、**メッセージの構築**図形。</span><span class="sxs-lookup"><span data-stu-id="ab40c-178">Drag-and-drop an **Expression Editor** after the **Construct Message** shape.</span></span> <span data-ttu-id="ab40c-179">エディターを開き、以下の式を入力します。</span><span class="sxs-lookup"><span data-stu-id="ab40c-179">Open the editor and enter the following expression:</span></span>  
  
        ```  
        quantityOrdered = Message2_SO_Inbound.Quantity;  
        ```  
  
         <span data-ttu-id="ab40c-180">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ab40c-180">Click **OK**.</span></span>  
  
4.  <span data-ttu-id="ab40c-181">注文数量を抽出したら、次に、メッセージ フローがたどる 2 つの異なるパスを配置するための判断ブロックを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab40c-181">After extracting the order quantity, you now need to create a decision block where you layout two separate paths the message flow takes.</span></span> <span data-ttu-id="ab40c-182">追加することで、オーケストレーションで判断ブロックを作成する、**判断**図形。</span><span class="sxs-lookup"><span data-stu-id="ab40c-182">You create the decision block in an orchestration by adding a **Decide** shape.</span></span>  
  
    1.  <span data-ttu-id="ab40c-183">ドラッグ アンド ドロップ、**判断**図形の後に、**式エディター**図形。</span><span class="sxs-lookup"><span data-stu-id="ab40c-183">Drag and drop a **Decide** shape after the **Expression Editor** shape.</span></span>  
  
    2.  <span data-ttu-id="ab40c-184">選択、 **[rule_1]** 図形および、**プロパティ**ウィンドウで、次を指定します。</span><span class="sxs-lookup"><span data-stu-id="ab40c-184">Select the **Rule_1** shape and in the **Properties** window, specify the following:</span></span>  
  
        |<span data-ttu-id="ab40c-185">プロパティ名</span><span class="sxs-lookup"><span data-stu-id="ab40c-185">Property name</span></span>|<span data-ttu-id="ab40c-186">値</span><span class="sxs-lookup"><span data-stu-id="ab40c-186">Value</span></span>|  
        |-------------------|-----------|  
        |<span data-ttu-id="ab40c-187">[Identifier]</span><span class="sxs-lookup"><span data-stu-id="ab40c-187">Identifier</span></span>|<span data-ttu-id="ab40c-188">入力`Yes`します。</span><span class="sxs-lookup"><span data-stu-id="ab40c-188">Enter `Yes`.</span></span> <span data-ttu-id="ab40c-189">**注:** という名前の既定値によって、その他のルートが**Else**します。</span><span class="sxs-lookup"><span data-stu-id="ab40c-189">**Note:**  The other route is by default named **Else**.</span></span>|  
        |<span data-ttu-id="ab40c-190">式</span><span class="sxs-lookup"><span data-stu-id="ab40c-190">Expression</span></span>|<span data-ttu-id="ab40c-191">入力`quantityOrdered > 100`します。</span><span class="sxs-lookup"><span data-stu-id="ab40c-191">Enter `quantityOrdered > 100`.</span></span>|  
  
         <span data-ttu-id="ab40c-192">これで、2 つのルートが利用可能になりました。</span><span class="sxs-lookup"><span data-stu-id="ab40c-192">You now have two routes available.</span></span> <span data-ttu-id="ab40c-193">場合の値、 **quantityOrdered**変数が 100 より大きい場合、メッセージは、**はい**ルート。</span><span class="sxs-lookup"><span data-stu-id="ab40c-193">If the value in the **quantityOrdered** variable is greater than 100, the message takes the **Yes** route.</span></span> <span data-ttu-id="ab40c-194">それ以外の場合、かかる、 **Else**ルート。</span><span class="sxs-lookup"><span data-stu-id="ab40c-194">Otherwise, it takes the **Else** route.</span></span> <span data-ttu-id="ab40c-195">ここで、各ルート内で実行するアクションを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab40c-195">You must now define the actions to be performed within each route.</span></span>  
  
5.  <span data-ttu-id="ab40c-196">ビジネス シナリオに従って、注文数量が 100 を超える場合、メッセージを SalesOrder テーブルに挿入する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab40c-196">According to the business scenario, if the order quantity is greater than 100, the message must be inserted into the SalesOrder table.</span></span> <span data-ttu-id="ab40c-197">そのためで、 **[はい]** ルート、ECommerceSalesOrder.xsd スキーマを TableOperations.SalesOrder.Insert スキーマを変換する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab40c-197">So, in the **Yes** route, you must transform the ECommerceSalesOrder.xsd schema to the TableOperations.SalesOrder.Insert schema.</span></span> <span data-ttu-id="ab40c-198">トピックの挿入スキーマを作成した[手順 5 (オンプレミス): メッセージする SalesOrder テーブルを挿入するためのスキーマを生成](../core/step-5-generate-the-schema-for-inserting-a-message-into-salesorder-table.md)します。</span><span class="sxs-lookup"><span data-stu-id="ab40c-198">You created the Insert schema in the topic [Step 5 (On Premises): Generate the Schema for Inserting a Message inito SalesOrder Table](../core/step-5-generate-the-schema-for-inserting-a-message-into-salesorder-table.md).</span></span> <span data-ttu-id="ab40c-199">スキーマを変換した後、メッセージを、SQL Server データベース テーブルに送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab40c-199">After transforming the schema, you must send the message to the message out to the SQL Server database table.</span></span>  
  
    1.  <span data-ttu-id="ab40c-200">内で、**はい**ルーティングにドラッグ アンド ドロップ、**メッセージの構築**図形。</span><span class="sxs-lookup"><span data-stu-id="ab40c-200">Within the **Yes** route, drag and drop a **Construct Message** shape.</span></span> <span data-ttu-id="ab40c-201">設定、**構築メッセージ**に図形のプロパティ**Message1_SO_Outbound**します。</span><span class="sxs-lookup"><span data-stu-id="ab40c-201">Set the **Messages Constructed** property for the shape to **Message1_SO_Outbound**.</span></span>  
  
    2.  <span data-ttu-id="ab40c-202">内で、**メッセージの構築**図形を追加、**変換**図形。</span><span class="sxs-lookup"><span data-stu-id="ab40c-202">Within the **Construct Message** shape add a **Transform** shape.</span></span> <span data-ttu-id="ab40c-203">図形をダブルクリックして開き、**変換の構成** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="ab40c-203">Double-click the shape to open the **Transform Configuration** dialog box.</span></span> <span data-ttu-id="ab40c-204">次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="ab40c-204">Do the following:</span></span>  
  
        1.  <span data-ttu-id="ab40c-205">選択、**既存のマップ**オプション。</span><span class="sxs-lookup"><span data-stu-id="ab40c-205">Select the **Existing Map** option.</span></span>  
  
        2.  <span data-ttu-id="ab40c-206">**完全修飾マップ名**ドロップダウン リストで選択**OrderProcessingDemo.SalesOrder_SQL**します。</span><span class="sxs-lookup"><span data-stu-id="ab40c-206">From the **Fully Qualified Map Name** drop-down, select **OrderProcessingDemo.SalesOrder_SQL**.</span></span>  
  
        3.  <span data-ttu-id="ab40c-207">**ソース**、 **Message2_SO_Inbound**します。</span><span class="sxs-lookup"><span data-stu-id="ab40c-207">For **Source**, select **Message2_SO_Inbound**.</span></span>  
  
        4.  <span data-ttu-id="ab40c-208">**先**、 **Message1_SO_Outound**します。</span><span class="sxs-lookup"><span data-stu-id="ab40c-208">For **Destination**, select **Message1_SO_Outound**.</span></span>  
  
    3.  <span data-ttu-id="ab40c-209">後に、**メッセージの構築**図形にドラッグ アンド ドロップ、**送信**図形し、設定、**メッセージ**に図形のプロパティ`Message1_SO_Outbound`します。</span><span class="sxs-lookup"><span data-stu-id="ab40c-209">After the **Construct Message** shape, drag and drop a **Send** shape and set the **Message** property for the shape to `Message1_SO_Outbound`.</span></span>  
  
6.  <span data-ttu-id="ab40c-210">ビジネス シナリオに従って、注文数量が 100 を下回る場合、メッセージを共有のファイルの場所に送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab40c-210">According to the business scenario, if the order quantity is less than 100, the message must be sent to a shared file location.</span></span> <span data-ttu-id="ab40c-211">そのためで、 **Else**ルート送信図形を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab40c-211">So, in the **Else** route you must add a send shape.</span></span>  
  
    1.  <span data-ttu-id="ab40c-212">内で、 **Else**ルーティングにドラッグ アンド ドロップ、**送信**図形し、設定、**メッセージ**に図形のプロパティ`Message2_SO_Inbound`します。</span><span class="sxs-lookup"><span data-stu-id="ab40c-212">Within the **Else** route, drag and drop a **Send** shape, and set the **Message** property for the shape to `Message2_SO_Inbound`.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="ab40c-213">[メッセージ] を Message2_SO_Inbound に設定するのは、Service Bus キューから受け取った同じメッセージが、処理されずにファイルの場所に送信されるためです。</span><span class="sxs-lookup"><span data-stu-id="ab40c-213">You set the Message to Message2_SO_Inbound because the same message that is received from the Service Bus Queue is sent to the file location, without any processing.</span></span> <span data-ttu-id="ab40c-214">Message2_SO_Inbound は、Service Bus キューによって受信されたメッセージを表しています。</span><span class="sxs-lookup"><span data-stu-id="ab40c-214">Message2_SO_Inbound represents the message that is received by the Service Bus Queue.</span></span>  
  
## <a name="add-ports-to-the-orchestration"></a><span data-ttu-id="ab40c-215">オーケストレーションへのポートの追加</span><span class="sxs-lookup"><span data-stu-id="ab40c-215">Add Ports to the Orchestration</span></span>  
 <span data-ttu-id="ab40c-216">ポートは、オーケストレーションに関連したメッセージの入力および出力の媒体を表しています。</span><span class="sxs-lookup"><span data-stu-id="ab40c-216">Ports represent the input and output mediums of the message with respect to an orchestration.</span></span> <span data-ttu-id="ab40c-217">メッセージは、受信ポートを使用してオーケストレーションによって処理され、送信ポートを使用して送信されます。</span><span class="sxs-lookup"><span data-stu-id="ab40c-217">Messages are consumed by an orchestration using a receive port and are sent out using a send port.</span></span> <span data-ttu-id="ab40c-218">ビジネス シナリオにおいて、メッセージは 1 つの媒体 (Service Bus キュー) から受信され、その後メッセージの処理に応じて、2 つの異なる場所 (SQL Server データベースまたはファイル共有場所) に送信されます。</span><span class="sxs-lookup"><span data-stu-id="ab40c-218">In the business scenario, a message is received from one medium (Service Bus Queue) and then sent out to two different locations (SQL Server database or a file share location) based on message processing.</span></span> <span data-ttu-id="ab40c-219">このため、オーケストレーションに 1 つの受信ポートと 2 つの送信ポートを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab40c-219">So, you must create one receive port and two send ports as part of the orchestration.</span></span>  
  
#### <a name="to-add-ports"></a><span data-ttu-id="ab40c-220">ポートを追加するには</span><span class="sxs-lookup"><span data-stu-id="ab40c-220">To add ports</span></span>  
  
1.  <span data-ttu-id="ab40c-221">ドラッグ アンド ドロップ、**ポート**図形を**ポート画面**のウィンドウ、**オーケストレーション デザイナー**を起動する、**ポート構成ウィザード**します。</span><span class="sxs-lookup"><span data-stu-id="ab40c-221">Drag and drop a **Port** shape to the **Port Surface** pane of the **Orchestration Designer** to launch the **Port Configuration Wizard**.</span></span> <span data-ttu-id="ab40c-222">**へようこそ**  ページで **次**します。</span><span class="sxs-lookup"><span data-stu-id="ab40c-222">On the **Welcome** page, click **Next**.</span></span>  
  
2.  <span data-ttu-id="ab40c-223">**ポートのプロパティ** ページで、名前とポート`ReceiveSO`順にクリックします**次**します。</span><span class="sxs-lookup"><span data-stu-id="ab40c-223">In the **Port Properties** page, name the port as `ReceiveSO` and then click **Next**.</span></span>  
  
3.  <span data-ttu-id="ab40c-224">**ポートの種類を選択**ページで、選択**新しいポートの種類を作成**オプションを選択、**一方向**通信パターン、アクセスの制限については、既定のままにし、クリックして**次**します。</span><span class="sxs-lookup"><span data-stu-id="ab40c-224">In the **Select a Port Type** page, select **Create a new port type** option, select the **One-Way** communication pattern, leave the default for access restrictions, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="ab40c-225">**ポートのバインド**] ページで、ポート方向を選択します**常にこのポートでメッセージを受信**、既定値には、ポートのバインドのままにし、[クリックして**次**.</span><span class="sxs-lookup"><span data-stu-id="ab40c-225">In the **Port Binding** page, for the port direction, select **I’ll always be receiving messages on this port**, leave the port biding to the default value, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="ab40c-226">最後のページで次のようにクリックします。**完了**します。</span><span class="sxs-lookup"><span data-stu-id="ab40c-226">On the last page, click **Finish**.</span></span>  
  
6.  <span data-ttu-id="ab40c-227">手順を繰り返して 2 つの送信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="ab40c-227">Repeat the steps to create the two send ports.</span></span> <span data-ttu-id="ab40c-228">ポートを作成する際は以下の値を指定します。</span><span class="sxs-lookup"><span data-stu-id="ab40c-228">Specify the following values while creating the ports.</span></span>  
  
    |<span data-ttu-id="ab40c-229">ポート名</span><span class="sxs-lookup"><span data-stu-id="ab40c-229">Port Name</span></span>|<span data-ttu-id="ab40c-230">[プロパティ]</span><span class="sxs-lookup"><span data-stu-id="ab40c-230">Properties</span></span>|  
    |---------------|----------------|  
    |<span data-ttu-id="ab40c-231">SendToSQL</span><span class="sxs-lookup"><span data-stu-id="ab40c-231">SendToSQL</span></span>|<span data-ttu-id="ab40c-232">-設定**名前**に**SendToSQL**</span><span class="sxs-lookup"><span data-stu-id="ab40c-232">-   Set **Name** to **SendToSQL**</span></span><br /><span data-ttu-id="ab40c-233">-**新しいポートの種類の作成**</span><span class="sxs-lookup"><span data-stu-id="ab40c-233">-   Select **Create a new port type**</span></span><br /><span data-ttu-id="ab40c-234">通信パターンのセット**一方向**</span><span class="sxs-lookup"><span data-stu-id="ab40c-234">-   Set communication pattern to **One-way**</span></span><br /><span data-ttu-id="ab40c-235">-ポートの方向に設定**は常にメッセージを送信しますこのポートで**</span><span class="sxs-lookup"><span data-stu-id="ab40c-235">-   Set port direction to **I’ll always be sending messages on this port**</span></span>|  
    |<span data-ttu-id="ab40c-236">SendToFile</span><span class="sxs-lookup"><span data-stu-id="ab40c-236">SendToFile</span></span>|<span data-ttu-id="ab40c-237">-設定**名前**に**SendToFile**</span><span class="sxs-lookup"><span data-stu-id="ab40c-237">-   Set **Name** to **SendToFile**</span></span><br /><span data-ttu-id="ab40c-238">-**新しいポートの種類の作成**</span><span class="sxs-lookup"><span data-stu-id="ab40c-238">-   Select **Create a new port type**</span></span><br /><span data-ttu-id="ab40c-239">通信パターンのセット**一方向**</span><span class="sxs-lookup"><span data-stu-id="ab40c-239">-   Set communication pattern to **One-way**</span></span><br /><span data-ttu-id="ab40c-240">-ポートの方向に設定**は常にメッセージを送信しますこのポートで**</span><span class="sxs-lookup"><span data-stu-id="ab40c-240">-   Set port direction to **I’ll always be sending messages on this port**</span></span>|  
  
## <a name="connect-ports-and-message-shapes"></a><span data-ttu-id="ab40c-241">ポートとメッセージ図形の接続</span><span class="sxs-lookup"><span data-stu-id="ab40c-241">Connect Ports and Message Shapes</span></span>  
 <span data-ttu-id="ab40c-242">次に、ポートとメッセージ図形を接続して、オーケストレーションを完成させます。</span><span class="sxs-lookup"><span data-stu-id="ab40c-242">You must now connect the ports and the message shapes to complete the orchestration.</span></span> <span data-ttu-id="ab40c-243">オーケストレーションの開始、メッセージを受信したときに、 **ReceiveOrder** 2 つの送信図形でメッセージが送信されるときに図形とオーケストレーションが終了します。</span><span class="sxs-lookup"><span data-stu-id="ab40c-243">The orchestration starts when the message is received by the **ReceiveOrder** shape and the orchestration exits when the message is sent out by the two Send shapes.</span></span> <span data-ttu-id="ab40c-244">この基準に基づいて、ポートとメッセージ図形を接続する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab40c-244">You must use this criterion to connect the ports and the message shapes</span></span>  
  
#### <a name="to-connect-ports-with-message-shapes"></a><span data-ttu-id="ab40c-245">ポートをメッセージ図形に接続するには</span><span class="sxs-lookup"><span data-stu-id="ab40c-245">To connect ports with message shapes</span></span>  
  
1.  <span data-ttu-id="ab40c-246">接続、 **ReceiveSO**受信ポートを**ReceiveOrder**図形。</span><span class="sxs-lookup"><span data-stu-id="ab40c-246">Connect the **ReceiveSO** receive port to the **ReceiveOrder** shape.</span></span>  
  
2.  <span data-ttu-id="ab40c-247">送信図形を接続、**はい**へのルーティング、 **SendToSQL**送信ポート。</span><span class="sxs-lookup"><span data-stu-id="ab40c-247">Connect the Send shape under the **Yes** route to the **SendToSQL** send port.</span></span> <span data-ttu-id="ab40c-248">表しますメッセージがこのルートに入る場合 (**quantityOrdered** > 100) に送信される、 **SalesOrder** SQL Server データベースのテーブル。</span><span class="sxs-lookup"><span data-stu-id="ab40c-248">This denotes that if a message enters this route (**quantityOrdered** > 100), it’ll be sent to the **SalesOrder** table in the SQL Server database.</span></span>  
  
3.  <span data-ttu-id="ab40c-249">送信図形を接続、 **Else**へのルーティング、 **SendToFile**送信ポート。</span><span class="sxs-lookup"><span data-stu-id="ab40c-249">Connect the Send shape under the **Else** route to the **SendToFile** send port.</span></span> <span data-ttu-id="ab40c-250">表しますメッセージがこのルートに入る場合 (**quantityOrdered** < = 100)、指定したファイルの場所に送信されます。</span><span class="sxs-lookup"><span data-stu-id="ab40c-250">This denotes that if a message enters this route (**quantityOrdered** <= 100), it’ll be sent to a specified file location.</span></span>  
  
     <span data-ttu-id="ab40c-251">オーケストレーションは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="ab40c-251">The orchestration must resemble the following:</span></span>  
  
     <span data-ttu-id="ab40c-252">![オーケストレーション](../core/media/bts2010r2-tut1-orch.jpg "BTS2010R2_Tut1_Orch")</span><span class="sxs-lookup"><span data-stu-id="ab40c-252">![Orchestration](../core/media/bts2010r2-tut1-orch.jpg "BTS2010R2_Tut1_Orch")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab40c-253">参照</span><span class="sxs-lookup"><span data-stu-id="ab40c-253">See Also</span></span>  
 [<span data-ttu-id="ab40c-254">チュートリアル 4: BizTalk Server 2013 を使用してハイブリッド アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="ab40c-254">Tutorial 4: Creating a Hybrid Application Using BizTalk Server 2013</span></span>](../core/tutorial-4-creating-a-hybrid-application-using-biztalk-server-2013.md)