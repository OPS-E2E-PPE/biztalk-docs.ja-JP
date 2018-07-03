---
title: BizTalk での SAP システムの SOAP アクションの構成 |Microsoft Docs
description: 式図形に SOAP アクションを入力するか、BizTalk アダプター パック (BAP) で、Wcf-custom または WCF-SAP アダプターを使用して、
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 76084bc5-7a10-4c4c-be22-bee83779a011
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 963c4b3c8d8287b430774813487e924837880a01
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004875"
---
# <a name="configure-the-soap-action-for-the-sap-system"></a><span data-ttu-id="8effe-103">SAP システムの SOAP アクションを構成します。</span><span class="sxs-lookup"><span data-stu-id="8effe-103">Configure the SOAP action for the SAP system</span></span>
<span data-ttu-id="8effe-104">WCF ベースを使用して SAP システムの操作を実行する[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]アダプターのユーザーは、SOAP アクションを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8effe-104">To perform any operation on the SAP system using the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], adapter users must specify a SOAP action.</span></span> <span data-ttu-id="8effe-105">SOAP アクションは、どのようなアクションが実行されるアダプターに通信します。</span><span class="sxs-lookup"><span data-stu-id="8effe-105">The SOAP action communicates to the adapter what action should be performed.</span></span> <span data-ttu-id="8effe-106">デザイン時または実行時に SOAP アクションを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="8effe-106">You can specify the SOAP action either at design time or at run time.</span></span> <span data-ttu-id="8effe-107">ただし、SOAP アクション両方デザイン時に指定する時間を実行すると、デザイン時に指定されたアクションは上書きされます。</span><span class="sxs-lookup"><span data-stu-id="8effe-107">However, if you specify the SOAP action both at design time and run time, the action you specified at design time will be overridden.</span></span>  
  
 <span data-ttu-id="8effe-108">SOAP アクションを指定する方法については、次を参照してください。 [WCF 送信アダプター用の SOAP アクションを指定する](../../core/specifying-soap-actions-for-wcf-send-adapters.md)します。</span><span class="sxs-lookup"><span data-stu-id="8effe-108">For more information about specifying SOAP action, see [Specifying SOAP Actions for WCF Send Adapters](../../core/specifying-soap-actions-for-wcf-send-adapters.md).</span></span>
  
## <a name="enter-soap-action-at-design-time"></a><span data-ttu-id="8effe-109">デザイン時に SOAP アクションを入力します。</span><span class="sxs-lookup"><span data-stu-id="8effe-109">Enter SOAP Action at Design Time</span></span>  
 <span data-ttu-id="8effe-110">式図形を含めることによって、デザイン時のオーケストレーションの一部として SOAP アクションを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8effe-110">For design time, you must specify the SOAP action as part of orchestration by including an expression shape.</span></span>  
  
 
1.  <span data-ttu-id="8effe-111">BizTalk オーケストレーションで式図形を含めるからドラッグすることで、 **BizTalk オーケストレーション**ツールボックスです。</span><span class="sxs-lookup"><span data-stu-id="8effe-111">In the BizTalk orchestration, include an Expression shape by dragging it from the **BizTalk Orchestration** toolbox.</span></span>  
  
2.  <span data-ttu-id="8effe-112">ダブルクリックして、**式**図形、BizTalk 式エディターを開きます。</span><span class="sxs-lookup"><span data-stu-id="8effe-112">Double-click the **Expression** shape to open the BizTalk Expression Editor.</span></span>  
  
3.  <span data-ttu-id="8effe-113">BizTalk 式エディタで、アクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="8effe-113">Specify the action in the BizTalk Expression Editor.</span></span> <span data-ttu-id="8effe-114">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="8effe-114">For example:</span></span>  
  
    ```  
    OutboundMessage(WCF.Action)="http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_CUSTOMER_GET"  
    ```  
  
     <span data-ttu-id="8effe-115">詳細については、**式**図形と、BizTalk 式エディタでを参照してください[式を作成する方法](../../core/how-to-create-expressions.md)します。</span><span class="sxs-lookup"><span data-stu-id="8effe-115">For more information about the **Expression** shape and the BizTalk Expression Editor, see [How to Create Expressions](../../core/how-to-create-expressions.md).</span></span>
  
## <a name="enter-soap-action-at-run-time"></a><span data-ttu-id="8effe-116">実行時に SOAP アクションを入力します。</span><span class="sxs-lookup"><span data-stu-id="8effe-116">Enter SOAP Action at Run Time</span></span>  
 <span data-ttu-id="8effe-117">実行時に、Wcf-custom または WCF SAP ポートの構成の一部として SOAP アクションを指定できます。</span><span class="sxs-lookup"><span data-stu-id="8effe-117">For run time, you can specify the SOAP action as part of the WCF-Custom or WCF-SAP port configuration.</span></span>  
  
### <a name="enter-a-soap-action-for-the-wcf-custom-port"></a><span data-ttu-id="8effe-118">WCF カスタム ポートの SOAP アクションを入力します。</span><span class="sxs-lookup"><span data-stu-id="8effe-118">Enter a SOAP action for the WCF-Custom port</span></span>  
  
1. <span data-ttu-id="8effe-119">開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="8effe-119">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2. <span data-ttu-id="8effe-120">コンソール ツリーで、展開**BizTalk グループ**の順に展開**アプリケーション**、 をクリックし、**送信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="8effe-120">In the console tree, expand **BizTalk Group**, then expand **Applications**, and then click **Send Ports**.</span></span> <span data-ttu-id="8effe-121">右側のウィンドウでは、ポートを作成または既存のポートを選択できます。</span><span class="sxs-lookup"><span data-stu-id="8effe-121">In the right pane, you can choose to create a port or select an existing port.</span></span>  
  
3. <span data-ttu-id="8effe-122">ポートのプロパティ ダイアログ ボックスから、**型**ドロップダウン リストで、 **Wcf-custom**、 をクリックし、**構成**します。</span><span class="sxs-lookup"><span data-stu-id="8effe-122">In the port properties dialog box, from the **Type** drop-down list, select **WCF-Custom**, and then click **Configure**.</span></span>  
  
4. <span data-ttu-id="8effe-123">**Wcf-custom トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**全般**タブ。</span><span class="sxs-lookup"><span data-stu-id="8effe-123">In the **WCF-Custom Transport Properties** dialog box, click the **General** tab.</span></span>  
  
5. <span data-ttu-id="8effe-124">**アクション**テキスト ボックスで、操作の SOAP アクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="8effe-124">In the **Action** text box, specify the SOAP action for the operation.</span></span> <span data-ttu-id="8effe-125">次の方法では、アクションを指定できます。</span><span class="sxs-lookup"><span data-stu-id="8effe-125">You can specify the action in the following ways:</span></span>  
  
   -   <span data-ttu-id="8effe-126">**シングル アクション形式を使用して**します。</span><span class="sxs-lookup"><span data-stu-id="8effe-126">**By using the single action format**.</span></span> <span data-ttu-id="8effe-127">Wcf-custom 送信ポートし、1 つの操作のメッセージを受信する場合は、この形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="8effe-127">Use this format if the WCF-Custom port sends and receive messages for a single operation.</span></span> <span data-ttu-id="8effe-128">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="8effe-128">For example:</span></span>  
  
       ```  
       http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_CUSTOMER_GET  
       ```  
  
   -   <span data-ttu-id="8effe-129">**アクション マッピング形式を使用して**します。</span><span class="sxs-lookup"><span data-stu-id="8effe-129">**By using the action mapping format**.</span></span> <span data-ttu-id="8effe-130">1 つの WCF カスタム ポートが 1 つ以上の操作のメッセージを送受信する場合は、この形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="8effe-130">Use this format if a single WCF-Custom port sends and receives messages for more than one operation.</span></span> <span data-ttu-id="8effe-131">たとえば、送受信 (RFC_CUSTOMER_GET RFC を呼び出す) を Op1 と Op2 (BAPI_SALESORDER_CREATEFROMDAT2 BAPI を呼び出す) へのメッセージを受け取る 1 つの WCF カスタム ポートを SOAP アクションは次のように指定できます。</span><span class="sxs-lookup"><span data-stu-id="8effe-131">For example, if a single WCF-Custom port sends and receives messages for Op1 (to invoke RFC_CUSTOMER_GET RFC) and Op2 (to invoke BAPI_SALESORDER_CREATEFROMDAT2 BAPI), the SOAP action can be specified in the following manner:</span></span>  
  
       ```  
       <BtsActionMapping>  
         <Operation Name="Op1" Action="http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_CUSTOMER_GET " />  
         <Operation Name="Op2" Action="http://Microsoft.LobServices.Sap/2007/03/Bapi/BUS2032/CREATEFROMDAT2/BAPI_SALESORDER_CREATEFROMDAT2" />  
       </BtsActionMapping>  
       ```  
  
        <span data-ttu-id="8effe-132">このアプローチには、一連のアクションを指定して、そのため、同じポートを経由するさまざまなアクションの種類に属するメッセージの有効化の観点から高い柔軟性が提供されます。</span><span class="sxs-lookup"><span data-stu-id="8effe-132">This approach provides greater flexibility in terms of specifying a set of actions and hence enabling messages belonging to different action types to flow through the same port.</span></span>  
  
        <span data-ttu-id="8effe-133">SOAP アクションの形式は操作ごとに異なります。</span><span class="sxs-lookup"><span data-stu-id="8effe-133">The format for the SOAP action is different for each operation.</span></span> <span data-ttu-id="8effe-134">各操作のアクションの形式の詳細については、次を参照してください。[メッセージとメッセージ スキーマ](messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md)します。</span><span class="sxs-lookup"><span data-stu-id="8effe-134">For more information about action format for each operation, see [Messages and message schemas](messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md).</span></span>
  
### <a name="enter-a-soap-action-for-the-wcf-sap-port"></a><span data-ttu-id="8effe-135">WCF SAP ポートの SOAP アクションを入力します。</span><span class="sxs-lookup"><span data-stu-id="8effe-135">Enter a SOAP action for the WCF-SAP port</span></span>  
  
1. <span data-ttu-id="8effe-136">開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="8effe-136">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2. <span data-ttu-id="8effe-137">WCF-SAP アダプターの追加、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="8effe-137">Add the WCF-SAP adapter to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="8effe-138">手順については、次を参照してください。 [SAP アダプターを BizTalk Server 管理コンソールに追加](../../adapters-and-accelerators/adapter-sap/add-the-sap-adapter-to-biztalk-server-administration-console.md)します。</span><span class="sxs-lookup"><span data-stu-id="8effe-138">For instructions, see [Add the SAP Adapter to BizTalk Server Administration Console](../../adapters-and-accelerators/adapter-sap/add-the-sap-adapter-to-biztalk-server-administration-console.md).</span></span>  
  
3. <span data-ttu-id="8effe-139">コンソール ツリーで、展開**BizTalk グループ**の順に展開**アプリケーション**、 をクリックし、**送信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="8effe-139">In the console tree, expand **BizTalk Group**, then expand **Applications**, and then click **Send Ports**.</span></span> <span data-ttu-id="8effe-140">右側のウィンドウでは、ポートを作成または既存のポートを選択できます。</span><span class="sxs-lookup"><span data-stu-id="8effe-140">In the right pane, you can choose to create a port or select an existing port.</span></span>  
  
4. <span data-ttu-id="8effe-141">ポートのプロパティ ダイアログ ボックスから、**型**ドロップダウン リストでは、先ほど追加した WCF-SAP アダプターを選択し、順にクリックします**構成**します。</span><span class="sxs-lookup"><span data-stu-id="8effe-141">In the port properties dialog box, from the **Type** drop-down list, select the WCF-SAP adapter you added earlier, and then click **Configure**.</span></span>  
  
5. <span data-ttu-id="8effe-142">トランスポートのプロパティ ダイアログ ボックスでをクリックして、**全般**タブ。</span><span class="sxs-lookup"><span data-stu-id="8effe-142">In the transport properties dialog box, click the **General** tab.</span></span>  
  
6. <span data-ttu-id="8effe-143">**アクション**テキスト ボックスで、操作の SOAP アクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="8effe-143">In the **Action** text box, specify the SOAP action for the operation.</span></span> <span data-ttu-id="8effe-144">次の方法では、アクションを指定できます。</span><span class="sxs-lookup"><span data-stu-id="8effe-144">You can specify the action in the following ways:</span></span>  
  
   -   <span data-ttu-id="8effe-145">**シングル アクション形式を使用して**します。</span><span class="sxs-lookup"><span data-stu-id="8effe-145">**By using the single action format**.</span></span> <span data-ttu-id="8effe-146">Wcf-custom 送信ポートし、1 つの操作のメッセージを受信する場合は、この形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="8effe-146">Use this format if the WCF-Custom port sends and receive messages for a single operation.</span></span> <span data-ttu-id="8effe-147">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="8effe-147">For example:</span></span>  
  
       ```  
       http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_CUSTOMER_GET  
       ```  
  
   -   <span data-ttu-id="8effe-148">**アクション マッピング形式を使用して**します。</span><span class="sxs-lookup"><span data-stu-id="8effe-148">**By using the action mapping format**.</span></span> <span data-ttu-id="8effe-149">1 つの WCF カスタム ポートが 1 つ以上の操作のメッセージを送受信する場合は、この形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="8effe-149">Use this format if a single WCF-Custom port sends and receives messages for more than one operation.</span></span> <span data-ttu-id="8effe-150">たとえば、送受信 (RFC_CUSTOMER_GET RFC を呼び出す) を Op1 と Op2 (BAPI_SALESORDER_CREATEFROMDAT2 BAPI を呼び出す) へのメッセージを受け取る 1 つの WCF カスタム ポートを SOAP アクションは次のように指定できます。</span><span class="sxs-lookup"><span data-stu-id="8effe-150">For example, if a single WCF-Custom port sends and receives messages for Op1 (to invoke RFC_CUSTOMER_GET RFC) and Op2 (to invoke BAPI_SALESORDER_CREATEFROMDAT2 BAPI), the SOAP action can be specified in the following manner:</span></span>  
  
       ```  
       <BtsActionMapping>  
         <Operation Name="Op1" Action="http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_CUSTOMER_GET " />  
         <Operation Name="Op2" Action="http://Microsoft.LobServices.Sap/2007/03/Bapi/BUS2032/CREATEFROMDAT2/BAPI_SALESORDER_CREATEFROMDAT2" />  
       </BtsActionMapping>  
       ```  
  
        <span data-ttu-id="8effe-151">このアプローチには、一連のアクションを指定して、そのため、同じポートを経由するさまざまなアクションの種類に属するメッセージの有効化の観点から高い柔軟性が提供されます。</span><span class="sxs-lookup"><span data-stu-id="8effe-151">This approach provides greater flexibility in terms of specifying a set of actions and hence enabling messages belonging to different action types to flow through the same port.</span></span>  
  
        <span data-ttu-id="8effe-152">SOAP アクションの形式は操作ごとに異なります。</span><span class="sxs-lookup"><span data-stu-id="8effe-152">The format for the SOAP action is different for each operation.</span></span> <span data-ttu-id="8effe-153">各操作のアクションの形式の詳細については、次を参照してください。[メッセージとメッセージ スキーマ](messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md)します。</span><span class="sxs-lookup"><span data-stu-id="8effe-153">For more information about action format for each operation, see [Messages and message schemas](messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="8effe-154">参照</span><span class="sxs-lookup"><span data-stu-id="8effe-154">See Also</span></span>  
[<span data-ttu-id="8effe-155">SAP アプリケーションを作成するための構成要素</span><span class="sxs-lookup"><span data-stu-id="8effe-155">Building blocks to create SAP applications</span></span>](../../adapters-and-accelerators/adapter-sap/building-blocks-to-create-sap-applications.md)