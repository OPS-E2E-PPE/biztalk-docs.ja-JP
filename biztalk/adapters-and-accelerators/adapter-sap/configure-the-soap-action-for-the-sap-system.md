---
title: "BizTalk で、SAP システムの SOAP アクションの構成 |Microsoft ドキュメント"
description: "式図形に SOAP アクションを入力または BizTalk アダプター パック (BAP) で、Wcf-custom アダプターまたは WCF SAP アダプターを使用します。"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 76084bc5-7a10-4c4c-be22-bee83779a011
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 36a474d53d3fcaf61668800094a1d98d0e061aa5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="configure-the-soap-action-for-the-sap-system"></a><span data-ttu-id="6fccd-103">SAP システムの SOAP アクションを構成します。</span><span class="sxs-lookup"><span data-stu-id="6fccd-103">Configure the SOAP action for the SAP system</span></span>
<span data-ttu-id="6fccd-104">WCF ベースを使用して SAP システムで操作を実行する[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]アダプターのユーザーは、SOAP アクションを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6fccd-104">To perform any operation on the SAP system using the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], adapter users must specify a SOAP action.</span></span> <span data-ttu-id="6fccd-105">SOAP アクションは、どのようなアクションを実行する必要があります、アダプターに通信します。</span><span class="sxs-lookup"><span data-stu-id="6fccd-105">The SOAP action communicates to the adapter what action should be performed.</span></span> <span data-ttu-id="6fccd-106">デザイン時に、または実行時に SOAP アクションを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="6fccd-106">You can specify the SOAP action either at design time or at run time.</span></span> <span data-ttu-id="6fccd-107">ただし、SOAP アクション両方デザイン時に指定し、実行時、デザイン時に指定されたアクションがオーバーライドされます。</span><span class="sxs-lookup"><span data-stu-id="6fccd-107">However, if you specify the SOAP action both at design time and run time, the action you specified at design time will be overridden.</span></span>  
  
 <span data-ttu-id="6fccd-108">SOAP アクションを指定する方法の詳細については、次を参照してください。 [WCF 送信アダプタ用の SOAP アクションの指定](../../core/specifying-soap-actions-for-wcf-send-adapters.md)です。</span><span class="sxs-lookup"><span data-stu-id="6fccd-108">For more information about specifying SOAP action, see [Specifying SOAP Actions for WCF Send Adapters](../../core/specifying-soap-actions-for-wcf-send-adapters.md).</span></span>
  
## <a name="enter-soap-action-at-design-time"></a><span data-ttu-id="6fccd-109">デザイン時に SOAP アクションを入力します。</span><span class="sxs-lookup"><span data-stu-id="6fccd-109">Enter SOAP Action at Design Time</span></span>  
 <span data-ttu-id="6fccd-110">デザイン時の式図形を含めることによって、オーケストレーションの一部として SOAP アクションを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6fccd-110">For design time, you must specify the SOAP action as part of orchestration by including an expression shape.</span></span>  
  
 
1.  <span data-ttu-id="6fccd-111">BizTalk オーケストレーションが含まれる式図形からドラッグすることで、 **BizTalk オーケストレーション**ツールボックスします。</span><span class="sxs-lookup"><span data-stu-id="6fccd-111">In the BizTalk orchestration, include an Expression shape by dragging it from the **BizTalk Orchestration** toolbox.</span></span>  
  
2.  <span data-ttu-id="6fccd-112">ダブルクリックして、**式**図形を BizTalk 式エディタを開きます。</span><span class="sxs-lookup"><span data-stu-id="6fccd-112">Double-click the **Expression** shape to open the BizTalk Expression Editor.</span></span>  
  
3.  <span data-ttu-id="6fccd-113">BizTalk 式エディターで、アクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="6fccd-113">Specify the action in the BizTalk Expression Editor.</span></span> <span data-ttu-id="6fccd-114">例:</span><span class="sxs-lookup"><span data-stu-id="6fccd-114">For example:</span></span>  
  
    ```  
    OutboundMessage(WCF.Action)="http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_CUSTOMER_GET"  
    ```  
  
     <span data-ttu-id="6fccd-115">詳細については、**式**図形と、BizTalk 式エディターを参照してください[式を作成する方法](../../core/how-to-create-expressions.md)です。</span><span class="sxs-lookup"><span data-stu-id="6fccd-115">For more information about the **Expression** shape and the BizTalk Expression Editor, see [How to Create Expressions](../../core/how-to-create-expressions.md).</span></span>
  
## <a name="enter-soap-action-at-run-time"></a><span data-ttu-id="6fccd-116">実行時に SOAP アクションを入力します。</span><span class="sxs-lookup"><span data-stu-id="6fccd-116">Enter SOAP Action at Run Time</span></span>  
 <span data-ttu-id="6fccd-117">実行時に、Wcf-custom または WCF SAP ポートの構成の一部として SOAP アクションを指定できます。</span><span class="sxs-lookup"><span data-stu-id="6fccd-117">For run time, you can specify the SOAP action as part of the WCF-Custom or WCF-SAP port configuration.</span></span>  
  
### <a name="enter-a-soap-action-for-the-wcf-custom-port"></a><span data-ttu-id="6fccd-118">WCF カスタム ポートの SOAP アクションを入力します。</span><span class="sxs-lookup"><span data-stu-id="6fccd-118">Enter a SOAP action for the WCF-Custom port</span></span>  
  
1.  <span data-ttu-id="6fccd-119">開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="6fccd-119">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="6fccd-120">コンソール ツリーで  **BizTalk グループ**の順に展開**アプリケーション**、順にクリック**送信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="6fccd-120">In the console tree, expand **BizTalk Group**, then expand **Applications**, and then click **Send Ports**.</span></span> <span data-ttu-id="6fccd-121">右側のウィンドウでは、ポートを作成または既存のポートを選択できます。</span><span class="sxs-lookup"><span data-stu-id="6fccd-121">In the right pane, you can choose to create a port or select an existing port.</span></span>  
  
3.  <span data-ttu-id="6fccd-122">ポートのプロパティ ダイアログ ボックスから、**型**ドロップダウン リストで、 **Wcf-custom**、クリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="6fccd-122">In the port properties dialog box, from the **Type** drop-down list, select **WCF-Custom**, and then click **Configure**.</span></span>  
  
4.  <span data-ttu-id="6fccd-123">**Wcf-custom トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**全般**タブです。</span><span class="sxs-lookup"><span data-stu-id="6fccd-123">In the **WCF-Custom Transport Properties** dialog box, click the **General** tab.</span></span>  
  
5.  <span data-ttu-id="6fccd-124">**アクション**テキスト ボックスで、操作の SOAP アクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="6fccd-124">In the **Action** text box, specify the SOAP action for the operation.</span></span> <span data-ttu-id="6fccd-125">次の方法では、アクションを指定できます。</span><span class="sxs-lookup"><span data-stu-id="6fccd-125">You can specify the action in the following ways:</span></span>  
  
    -   <span data-ttu-id="6fccd-126">**シングル アクション形式を使用して、**です。</span><span class="sxs-lookup"><span data-stu-id="6fccd-126">**By using the single action format**.</span></span> <span data-ttu-id="6fccd-127">Wcf-custom 送信ポートし、1 つの操作のメッセージを受信する場合は、この形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="6fccd-127">Use this format if the WCF-Custom port sends and receive messages for a single operation.</span></span> <span data-ttu-id="6fccd-128">例:</span><span class="sxs-lookup"><span data-stu-id="6fccd-128">For example:</span></span>  
  
        ```  
        http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_CUSTOMER_GET  
        ```  
  
    -   <span data-ttu-id="6fccd-129">**アクション マッピング形式を使用して、**です。</span><span class="sxs-lookup"><span data-stu-id="6fccd-129">**By using the action mapping format**.</span></span> <span data-ttu-id="6fccd-130">1 つの WCF カスタム ポートを送信し、1 つ以上の操作のメッセージを受け取る場合は、この形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="6fccd-130">Use this format if a single WCF-Custom port sends and receives messages for more than one operation.</span></span> <span data-ttu-id="6fccd-131">たとえば、1 つの WCF カスタム ポートを送信および (RFC_CUSTOMER_GET RFC を呼び出し) する Op1、Op2 (BAPI_SALESORDER_CREATEFROMDAT2 BAPI を呼び出し) するためのメッセージを受信する場合、SOAP アクションは次のように指定できます。</span><span class="sxs-lookup"><span data-stu-id="6fccd-131">For example, if a single WCF-Custom port sends and receives messages for Op1 (to invoke RFC_CUSTOMER_GET RFC) and Op2 (to invoke BAPI_SALESORDER_CREATEFROMDAT2 BAPI), the SOAP action can be specified in the following manner:</span></span>  
  
        ```  
        <BtsActionMapping>  
          <Operation Name="Op1" Action="http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_CUSTOMER_GET " />  
          <Operation Name="Op2" Action="http://Microsoft.LobServices.Sap/2007/03/Bapi/BUS2032/CREATEFROMDAT2/BAPI_SALESORDER_CREATEFROMDAT2" />  
        </BtsActionMapping>  
        ```  
  
         <span data-ttu-id="6fccd-132">このアプローチには、一連のアクションを指定して、そのため、同じポートを通過するさまざまなアクションの種類に属するメッセージの有効化の観点から高い柔軟性が実現します。</span><span class="sxs-lookup"><span data-stu-id="6fccd-132">This approach provides greater flexibility in terms of specifying a set of actions and hence enabling messages belonging to different action types to flow through the same port.</span></span>  
  
         <span data-ttu-id="6fccd-133">SOAP アクションの形式は操作ごとに異なります。</span><span class="sxs-lookup"><span data-stu-id="6fccd-133">The format for the SOAP action is different for each operation.</span></span> <span data-ttu-id="6fccd-134">各操作のアクションの形式の詳細については、次を参照してください。[メッセージおよびメッセージ スキーマ](messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md)です。</span><span class="sxs-lookup"><span data-stu-id="6fccd-134">For more information about action format for each operation, see [Messages and message schemas](messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md).</span></span>
  
### <a name="enter-a-soap-action-for-the-wcf-sap-port"></a><span data-ttu-id="6fccd-135">WCF SAP ポートの SOAP アクションを入力します。</span><span class="sxs-lookup"><span data-stu-id="6fccd-135">Enter a SOAP action for the WCF-SAP port</span></span>  
  
1.  <span data-ttu-id="6fccd-136">開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="6fccd-136">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="6fccd-137">WCF SAP アダプターを追加、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="6fccd-137">Add the WCF-SAP adapter to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="6fccd-138">手順については、次を参照してください。 [SAP アダプターを BizTalk Server 管理コンソールに追加](../../adapters-and-accelerators/adapter-sap/add-the-sap-adapter-to-biztalk-server-administration-console.md)です。</span><span class="sxs-lookup"><span data-stu-id="6fccd-138">For instructions, see [Add the SAP Adapter to BizTalk Server Administration Console](../../adapters-and-accelerators/adapter-sap/add-the-sap-adapter-to-biztalk-server-administration-console.md).</span></span>  
  
3.  <span data-ttu-id="6fccd-139">コンソール ツリーで  **BizTalk グループ**の順に展開**アプリケーション**、順にクリック**送信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="6fccd-139">In the console tree, expand **BizTalk Group**, then expand **Applications**, and then click **Send Ports**.</span></span> <span data-ttu-id="6fccd-140">右側のウィンドウでは、ポートを作成または既存のポートを選択できます。</span><span class="sxs-lookup"><span data-stu-id="6fccd-140">In the right pane, you can choose to create a port or select an existing port.</span></span>  
  
4.  <span data-ttu-id="6fccd-141">ポートのプロパティ ダイアログ ボックスから、**型**ドロップダウン リストは、前に追加する WCF SAP アダプターを選択し、をクリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="6fccd-141">In the port properties dialog box, from the **Type** drop-down list, select the WCF-SAP adapter you added earlier, and then click **Configure**.</span></span>  
  
5.  <span data-ttu-id="6fccd-142">トランスポートのプロパティ ダイアログ ボックスをクリックして、**全般**タブです。</span><span class="sxs-lookup"><span data-stu-id="6fccd-142">In the transport properties dialog box, click the **General** tab.</span></span>  
  
6.  <span data-ttu-id="6fccd-143">**アクション**テキスト ボックスで、操作の SOAP アクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="6fccd-143">In the **Action** text box, specify the SOAP action for the operation.</span></span> <span data-ttu-id="6fccd-144">次の方法では、アクションを指定できます。</span><span class="sxs-lookup"><span data-stu-id="6fccd-144">You can specify the action in the following ways:</span></span>  
  
    -   <span data-ttu-id="6fccd-145">**シングル アクション形式を使用して、**です。</span><span class="sxs-lookup"><span data-stu-id="6fccd-145">**By using the single action format**.</span></span> <span data-ttu-id="6fccd-146">Wcf-custom 送信ポートし、1 つの操作のメッセージを受信する場合は、この形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="6fccd-146">Use this format if the WCF-Custom port sends and receive messages for a single operation.</span></span> <span data-ttu-id="6fccd-147">例:</span><span class="sxs-lookup"><span data-stu-id="6fccd-147">For example:</span></span>  
  
        ```  
        http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_CUSTOMER_GET  
        ```  
  
    -   <span data-ttu-id="6fccd-148">**アクション マッピング形式を使用して、**です。</span><span class="sxs-lookup"><span data-stu-id="6fccd-148">**By using the action mapping format**.</span></span> <span data-ttu-id="6fccd-149">1 つの WCF カスタム ポートを送信し、1 つ以上の操作のメッセージを受け取る場合は、この形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="6fccd-149">Use this format if a single WCF-Custom port sends and receives messages for more than one operation.</span></span> <span data-ttu-id="6fccd-150">たとえば、1 つの WCF カスタム ポートを送信および (RFC_CUSTOMER_GET RFC を呼び出し) する Op1、Op2 (BAPI_SALESORDER_CREATEFROMDAT2 BAPI を呼び出し) するためのメッセージを受信する場合、SOAP アクションは次のように指定できます。</span><span class="sxs-lookup"><span data-stu-id="6fccd-150">For example, if a single WCF-Custom port sends and receives messages for Op1 (to invoke RFC_CUSTOMER_GET RFC) and Op2 (to invoke BAPI_SALESORDER_CREATEFROMDAT2 BAPI), the SOAP action can be specified in the following manner:</span></span>  
  
        ```  
        <BtsActionMapping>  
          <Operation Name="Op1" Action="http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_CUSTOMER_GET " />  
          <Operation Name="Op2" Action="http://Microsoft.LobServices.Sap/2007/03/Bapi/BUS2032/CREATEFROMDAT2/BAPI_SALESORDER_CREATEFROMDAT2" />  
        </BtsActionMapping>  
        ```  
  
         <span data-ttu-id="6fccd-151">このアプローチには、一連のアクションを指定して、そのため、同じポートを通過するさまざまなアクションの種類に属するメッセージの有効化の観点から高い柔軟性が実現します。</span><span class="sxs-lookup"><span data-stu-id="6fccd-151">This approach provides greater flexibility in terms of specifying a set of actions and hence enabling messages belonging to different action types to flow through the same port.</span></span>  
  
         <span data-ttu-id="6fccd-152">SOAP アクションの形式は操作ごとに異なります。</span><span class="sxs-lookup"><span data-stu-id="6fccd-152">The format for the SOAP action is different for each operation.</span></span> <span data-ttu-id="6fccd-153">各操作のアクションの形式の詳細については、次を参照してください。[メッセージおよびメッセージ スキーマ](messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md)です。</span><span class="sxs-lookup"><span data-stu-id="6fccd-153">For more information about action format for each operation, see [Messages and message schemas](messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="6fccd-154">参照</span><span class="sxs-lookup"><span data-stu-id="6fccd-154">See Also</span></span>  
[<span data-ttu-id="6fccd-155">SAP アプリケーションを作成する構成要素</span><span class="sxs-lookup"><span data-stu-id="6fccd-155">Building blocks to create SAP applications</span></span>](../../adapters-and-accelerators/adapter-sap/building-blocks-to-create-sap-applications.md)