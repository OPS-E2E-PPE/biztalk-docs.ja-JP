---
title: '手順 2: ポートの構成 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e804da96-26ae-482d-b6e1-67af24d639d9
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7c9aaefe0cff41365a587079d0c82629ddddc586
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25967288"
---
# <a name="step-2-configure-the-ports"></a><span data-ttu-id="b470b-102">手順 2: ポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="b470b-102">Step 2: Configure the Ports</span></span>
<span data-ttu-id="b470b-103">![手順 4 2](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-2of4.gif "Step_2of4")</span><span class="sxs-lookup"><span data-stu-id="b470b-103">![Step 2 of 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-2of4.gif "Step_2of4")</span></span>  
  
 <span data-ttu-id="b470b-104">**所要時間:** 15 分</span><span class="sxs-lookup"><span data-stu-id="b470b-104">**Time to complete:** 15 minutes</span></span>  
  
 <span data-ttu-id="b470b-105">**目標:** で物理ポートを作成するこの手順で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="b470b-105">**Objective:** In this step, you create the physical ports in [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="b470b-106">オーケストレーションで作成した各論理ポートに対する物理ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="b470b-106">You create a physical port for each logical port you created in the orchestration.</span></span> <span data-ttu-id="b470b-107">次のポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="b470b-107">You will create the following ports:</span></span>  
  
-   <span data-ttu-id="b470b-108">一方向の WCF カスタム受信する受信ポートの変更を通知メッセージ**従業員**SQL Server データベースのテーブルにします。</span><span class="sxs-lookup"><span data-stu-id="b470b-108">A one-way WCF-Custom receive port to receive notification messages for changes to **Employee** table in a SQL Server database.</span></span>  
  
-   <span data-ttu-id="b470b-109">要求-応答の WCF カスタム送信要求メッセージを送信しを起動するための応答を受信ポート、 **UPDATE_EMPLOYEE**ストアド プロシージャに対して、挿入操作を実行して、 **Purchase_Order**テーブル。</span><span class="sxs-lookup"><span data-stu-id="b470b-109">A request-response WCF-Custom send port to send request messages and receive response for invoking the **UPDATE_EMPLOYEE** stored procedure and for performing the Insert operation on the **Purchase_Order** table.</span></span> <span data-ttu-id="b470b-110">オーケストレーションでは、同じ送信ポートを使用して、両方の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="b470b-110">In the orchestration, you used the same send port to perform both the operations.</span></span> <span data-ttu-id="b470b-111">同様に、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、両方の操作の単一の送信ポートが使用されます。</span><span class="sxs-lookup"><span data-stu-id="b470b-111">Similarly, in the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console, you will use a single send port for both operations.</span></span>  
  
-   <span data-ttu-id="b470b-112">挿入操作の応答を送信する一方向の送信ポートです。</span><span class="sxs-lookup"><span data-stu-id="b470b-112">A one-way send port to send the response for the Insert operation.</span></span> <span data-ttu-id="b470b-113">このチュートリアルでは、電子メールを通じて購買部門に通知する必要があるため、この送信ポートとして作成 SMTP ポートします。</span><span class="sxs-lookup"><span data-stu-id="b470b-113">In this tutorial, because you need to inform the Purchases department through an e-mail, you create this send port as an SMTP port.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="b470b-114">前提条件</span><span class="sxs-lookup"><span data-stu-id="b470b-114">Prerequisites</span></span>  
 <span data-ttu-id="b470b-115">完了する必要があります[手順 1: オーケストレーションを展開](../../adapters-and-accelerators/adapter-sql/step-1-deploy-the-orchestration.md))。</span><span class="sxs-lookup"><span data-stu-id="b470b-115">You must have completed [Step 1: Deploy the Orchestration](../../adapters-and-accelerators/adapter-sql/step-1-deploy-the-orchestration.md)).</span></span>  
  
### <a name="to-create-a-physical-one-way-receive-port"></a><span data-ttu-id="b470b-116">物理的な一方向の受信ポートを作成するには</span><span class="sxs-lookup"><span data-stu-id="b470b-116">To create a physical one-way receive port</span></span>  
  
1.  <span data-ttu-id="b470b-117">開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="b470b-117">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="b470b-118">コンソール ツリーで、左側で、展開**BizTalk Server 管理コンソール**を右クリックして**BizTalk グループ**、順にクリック**更新**です。</span><span class="sxs-lookup"><span data-stu-id="b470b-118">In the console tree on the left hand side, expand **BizTalk Server Administration**, right-click **BizTalk Group**, and then click **Refresh**.</span></span>  
  
3.  <span data-ttu-id="b470b-119">展開**BizTalk グループ**、展開**アプリケーション**、展開と**SampleApplication**です。</span><span class="sxs-lookup"><span data-stu-id="b470b-119">Expand **BizTalk Group**, expand **Applications**, and expand **SampleApplication**.</span></span> <span data-ttu-id="b470b-120">このチュートリアルでは、すべてのポートと SampleApplication アプリケーション内でアプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="b470b-120">For this tutorial, you create all the ports and application within the SampleApplication application.</span></span>  
  
4.  <span data-ttu-id="b470b-121">"を展開するアダプターの受信メッセージから SQL Server"セクションの指示に従います[wcf-custom アダプタと SQL アダプタを使用してポートを構成する](../../adapters-and-accelerators/adapter-sql/configure-a-port-using-the-wcf-custom-adapter-and-sql-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="b470b-121">Follow the instructions under the “Deploying Adapters for Receiving Messages from SQL Server” section of [Configure a port using the WCF-custom adapter and SQL adapter](../../adapters-and-accelerators/adapter-sql/configure-a-port-using-the-wcf-custom-adapter-and-sql-adapter.md).</span></span> <span data-ttu-id="b470b-122">名前とポート**NotifyReceivePort**です。</span><span class="sxs-lookup"><span data-stu-id="b470b-122">Name the port as **NotifyReceivePort**.</span></span>  
  
5.  <span data-ttu-id="b470b-123">変更の通知を受信するアダプターを構成する次のバインドのプロパティを設定するかどうかを確認、**従業員**テーブル。</span><span class="sxs-lookup"><span data-stu-id="b470b-123">Make sure you set the following binding properties to configure the adapter to receive notifications for changes to the **Employee** table.</span></span>  
  
    |<span data-ttu-id="b470b-124">プロパティのバインド</span><span class="sxs-lookup"><span data-stu-id="b470b-124">Binding property</span></span>|<span data-ttu-id="b470b-125">値</span><span class="sxs-lookup"><span data-stu-id="b470b-125">Value</span></span>|  
    |----------------------|-----------|  
    |<span data-ttu-id="b470b-126">**InboundOperationType**</span><span class="sxs-lookup"><span data-stu-id="b470b-126">**InboundOperationType**</span></span>|<span data-ttu-id="b470b-127">これを設定して**通知**です。</span><span class="sxs-lookup"><span data-stu-id="b470b-127">Set this to **Notification**.</span></span>|  
    |<span data-ttu-id="b470b-128">**NotificationStatement**</span><span class="sxs-lookup"><span data-stu-id="b470b-128">**NotificationStatement**</span></span>|<span data-ttu-id="b470b-129">これを設定します。</span><span class="sxs-lookup"><span data-stu-id="b470b-129">Set this to:</span></span><br /><br /> `SELECT Employee_ID, Name FROM dbo.Employee WHERE Status=0`<br /><br /> <span data-ttu-id="b470b-130">**注:** する必要があります具体的には、列名を指定、ステートメントで次の Select ステートメントで示すようにします。</span><span class="sxs-lookup"><span data-stu-id="b470b-130">**Note:** You must specifically specify the column names in the statement as shown in this Select statement.</span></span> <span data-ttu-id="b470b-131">また、必要があります常を指定すると、スキーマ名、テーブル名など、`dbo.Employee`です。</span><span class="sxs-lookup"><span data-stu-id="b470b-131">Also, you must always specify the table name along with the schema name, for example, `dbo.Employee`.</span></span>|  
    |<span data-ttu-id="b470b-132">**NotifyOnListenerStart**</span><span class="sxs-lookup"><span data-stu-id="b470b-132">**NotifyOnListenerStart**</span></span>|<span data-ttu-id="b470b-133">これを設定して**True**です。</span><span class="sxs-lookup"><span data-stu-id="b470b-133">Set this to **True**.</span></span>|  
  
     <span data-ttu-id="b470b-134">異なるバインディングのプロパティの詳細については、次を参照してください。 [SQL Server のアダプターのバインド プロパティの BizTalk アダプターの説明を読む](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)です。</span><span class="sxs-lookup"><span data-stu-id="b470b-134">For more information about the different binding properties, see [Read about the BizTalk Adapter for SQL Server adapter binding properties](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md).</span></span>  
  
### <a name="to-create-a-request-response-send-port-for-two-operations"></a><span data-ttu-id="b470b-135">要求-応答送信の 2 つの操作用のポートを作成するには</span><span class="sxs-lookup"><span data-stu-id="b470b-135">To create a request-response send port for two operations</span></span>  
  
1.  <span data-ttu-id="b470b-136">"を展開するアダプターの送信メッセージを SQL Server"セクションの指示に従います[wcf-custom アダプタと SQL アダプタを使用してポートを構成する](../../adapters-and-accelerators/adapter-sql/configure-a-port-using-the-wcf-custom-adapter-and-sql-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="b470b-136">Follow the instructions under the “Deploying Adapters for Sending Messages to SQL Server” section of [Configure a port using the WCF-custom adapter and SQL adapter](../../adapters-and-accelerators/adapter-sql/configure-a-port-using-the-wcf-custom-adapter-and-sql-adapter.md).</span></span> <span data-ttu-id="b470b-137">名前とポート**SQLOutboundPort**です。</span><span class="sxs-lookup"><span data-stu-id="b470b-137">Name the port as **SQLOutboundPort**.</span></span>  
  
2.  <span data-ttu-id="b470b-138">実行しているため、2 つの操作を使用して、同じ送信ポート、動的アクション マッピングを使用して、操作のアクションを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b470b-138">Because you are performing two operations using the same send port, you must use dynamic action mapping to specify the action for the operation.</span></span> <span data-ttu-id="b470b-139">ポートを構成するときに、**アクション**ボックスで、次のように、アクション マッピングを指定します。</span><span class="sxs-lookup"><span data-stu-id="b470b-139">While configuring the port, in the **Action** box, specify the action mapping in the following manner:</span></span>  
  
    ```  
    <BtsActionMapping xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
      <Operation Name="UpdateEmp" Action="TypedProcedure/dbo/UPDATE_EMPLOYEE" />  
      <Operation Name="InsertPO" Action="TableOp/Insert/dbo/Purchase_Order" />  
    </BtsActionMapping>  
    ```  
  
     <span data-ttu-id="b470b-140">オーケストレーションで要求-応答送信ポートの 2 つの操作を作成することに注意してください: **UpdateEmp**と**InsertPO**です。</span><span class="sxs-lookup"><span data-stu-id="b470b-140">Note that in the orchestration, you created two operations for the request-response send port: **UpdateEmp** and **InsertPO**.</span></span> <span data-ttu-id="b470b-141">そのため、物理ポートの構成では、動的アクション マッピングの同じ操作名を提供します。</span><span class="sxs-lookup"><span data-stu-id="b470b-141">So, in the physical port configuration you provide the same operation names in the dynamic action mapping.</span></span> <span data-ttu-id="b470b-142">上記の例では、アクションを**UpdateEmp**操作が`TypedProcedure/dbo/UPDATE_EMPLOYEE`です。</span><span class="sxs-lookup"><span data-stu-id="b470b-142">In the above excerpt, the action for **UpdateEmp** operation is `TypedProcedure/dbo/UPDATE_EMPLOYEE`.</span></span> <span data-ttu-id="b470b-143">同様に、アクションを**InsertPO**操作が`TableOp/Insert/dbo/Purchase_Order`です。</span><span class="sxs-lookup"><span data-stu-id="b470b-143">Similarly, the action for **InsertPO** operation is `TableOp/Insert/dbo/Purchase_Order`.</span></span>  
  
3.  <span data-ttu-id="b470b-144">応答メッセージにマップするオーケストレーションで作成したマッパーを使用する送信ポートを構成することも必要があります**UPDATE_EMPLOYEE**でストアド プロシージャの挿入操作の要求メッセージを**Purchase_。順序**テーブル。</span><span class="sxs-lookup"><span data-stu-id="b470b-144">You must also configure the send port to use the Mapper you created in the orchestration to map the response message of **UPDATE_EMPLOYEE** stored procedure to the request message for the Insert operation on **Purchase_Order** table.</span></span> <span data-ttu-id="b470b-145">そのためには次を行います。</span><span class="sxs-lookup"><span data-stu-id="b470b-145">To do so:</span></span>  
  
    1.  <span data-ttu-id="b470b-146">SQLOutboundPort を右クリックして[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、クリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="b470b-146">Right-click the SQLOutboundPort in [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console, and then click **Properties**.</span></span>  
  
    2.  <span data-ttu-id="b470b-147">**SQLOutboundPort – 送信ポートのプロパティ**ダイアログ ボックスで、左側のウィンドウからをクリックして**送信マップ**です。</span><span class="sxs-lookup"><span data-stu-id="b470b-147">From the **SQLOutboundPort – Send Port Properties** dialog box, from the left pane, click **Outbound Maps**.</span></span>  
  
    3.  <span data-ttu-id="b470b-148">右側のウィンドウからの**送信マップ**ボックスで、下のセルをクリックして、**マップ**列で、ドロップダウン リストから選択し、**変換 _ 1**です。</span><span class="sxs-lookup"><span data-stu-id="b470b-148">From the right-pane, in the **Outbound Maps** box, click the cell under the **Map** column, and from the drop-down list, select **Transform_1**.</span></span> <span data-ttu-id="b470b-149">これは、BizTalk のオーケストレーションで作成したマップの名前を[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="b470b-149">This is the name of the map you created in the BizTalk orchestration in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span>  
  
         <span data-ttu-id="b470b-150">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b470b-150">Click **OK**.</span></span>  
  
         <span data-ttu-id="b470b-151">![送信マップを構成する](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-010-map-ports.gif "sql_adap_tut_010_map_ports")</span><span class="sxs-lookup"><span data-stu-id="b470b-151">![Configure outbound map](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-010-map-ports.gif "sql_adap_tut_010_map_ports")</span></span>  
  
### <a name="to-create-an-smtp-send-port"></a><span data-ttu-id="b470b-152">SMTP 送信ポートを作成するには</span><span class="sxs-lookup"><span data-stu-id="b470b-152">To create an SMTP send port</span></span>  
  
1.  <span data-ttu-id="b470b-153">説明に従い、"の SMTP 送信ポートを構成する方法、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール」セクションで[http://go.microsoft.com/fwlink/?LinkId=141549](http://go.microsoft.com/fwlink/?LinkId=141549)です。</span><span class="sxs-lookup"><span data-stu-id="b470b-153">Follow the instructions under the “How to Configure an SMTP Send Port with the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration Console” section at [http://go.microsoft.com/fwlink/?LinkId=141549](http://go.microsoft.com/fwlink/?LinkId=141549).</span></span> <span data-ttu-id="b470b-154">名前とポート**EmailResponse**です。</span><span class="sxs-lookup"><span data-stu-id="b470b-154">Name the port as **EmailResponse**.</span></span>  
  
2.  <span data-ttu-id="b470b-155">ポートの構成の一環として、指定の購買部門の電子メール アドレス、**に**プロパティです。</span><span class="sxs-lookup"><span data-stu-id="b470b-155">As part of the port configuration, specify the e-mail address for the Purchases department for the **To** property.</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="b470b-156">でしただけは何ですか。</span><span class="sxs-lookup"><span data-stu-id="b470b-156">What did I just do?</span></span>  
 <span data-ttu-id="b470b-157">作成したこのステップでは、WCF カスタムは、SQL Server から通知を受信ポート、SQL Server での操作を実行するための Wcf-custom 送信ポートに送信するため、応答から SQL Server を電子メールとしては購買部門の SMTP ポートを受信します。</span><span class="sxs-lookup"><span data-stu-id="b470b-157">In this step you created a WCF-Custom receive port for receiving notifications from SQL Server, WCF-Custom send port for performing operations on SQL Server, and an SMTP port for sending the response from SQL Server as an e-mail to the Purchases department.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="b470b-158">次の手順</span><span class="sxs-lookup"><span data-stu-id="b470b-158">Next Steps</span></span>  
 <span data-ttu-id="b470b-159">構成し、」の説明に従って、BizTalk アプリケーションを開始する[手順 3: 構成し、アプリケーションを起動](../../adapters-and-accelerators/adapter-sql/step-3-configure-and-start-the-application.md)です。</span><span class="sxs-lookup"><span data-stu-id="b470b-159">You configure and start the BizTalk application, as described in [Step 3: Configure and Start the Application](../../adapters-and-accelerators/adapter-sql/step-3-configure-and-start-the-application.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b470b-160">参照</span><span class="sxs-lookup"><span data-stu-id="b470b-160">See Also</span></span>  
 <span data-ttu-id="b470b-161">[手順 1: オーケストレーションを展開します。](../../adapters-and-accelerators/adapter-sql/step-1-deploy-the-orchestration.md) </span><span class="sxs-lookup"><span data-stu-id="b470b-161">[Step 1: Deploy the Orchestration](../../adapters-and-accelerators/adapter-sql/step-1-deploy-the-orchestration.md) </span></span>  
 <span data-ttu-id="b470b-162">[手順 3: を構成し、アプリケーションを起動](../../adapters-and-accelerators/adapter-sql/step-3-configure-and-start-the-application.md) </span><span class="sxs-lookup"><span data-stu-id="b470b-162">[Step 3: Configure and Start the Application](../../adapters-and-accelerators/adapter-sql/step-3-configure-and-start-the-application.md) </span></span>  
 [<span data-ttu-id="b470b-163">レッスン 5: ソリューションを展開する</span><span class="sxs-lookup"><span data-stu-id="b470b-163">Lesson 5: Deploy the Solution</span></span>](../../adapters-and-accelerators/adapter-sql/lesson-5-deploy-the-solution.md)