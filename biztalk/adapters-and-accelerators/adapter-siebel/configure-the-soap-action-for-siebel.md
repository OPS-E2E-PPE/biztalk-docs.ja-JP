---
title: BizTalk での Siebel アダプターの SOAP アクションの構成 |Microsoft Docs
description: Visual Studio での SOAP アクションの入力または BizTalk アダプター パック (BAP) で、Wcf-custom または Wcf-siebel アダプターを使用して、
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f22a4691-0355-4f08-a14e-e90a3c987ac0
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fb945aba089e0c57e42e846cec765ae48b10d433
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37022248"
---
# <a name="configure-the-soap-action-for-siebel"></a><span data-ttu-id="7b96d-103">Siebel の SOAP アクションを構成します。</span><span class="sxs-lookup"><span data-stu-id="7b96d-103">Configure the SOAP action for Siebel</span></span>
<span data-ttu-id="7b96d-104">WCF ベースを使用して Siebel システムに対して任意の操作を実行する[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]アダプターのユーザーは、SOAP アクションを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7b96d-104">To perform any operation on the Siebel system using the WCF-based [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)], adapter users must specify a SOAP action.</span></span> <span data-ttu-id="7b96d-105">SOAP アクションは、どのようなアクションが実行されるアダプターに通信します。</span><span class="sxs-lookup"><span data-stu-id="7b96d-105">The SOAP action communicates to the adapter what action should be performed.</span></span> <span data-ttu-id="7b96d-106">デザイン時または実行時に SOAP アクションを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="7b96d-106">You can specify the SOAP action either at design time or at run time.</span></span> <span data-ttu-id="7b96d-107">ただし、SOAP アクション両方デザイン時に指定する時間を実行すると、デザイン時に指定されたアクションは上書きされます。</span><span class="sxs-lookup"><span data-stu-id="7b96d-107">However, if you specify the SOAP action both at design time and run time, the action you specified at design time will be overridden.</span></span>  
  
 <span data-ttu-id="7b96d-108">SOAP アクションを指定する方法については、次を参照してください。 [WCF 送信アダプター用の SOAP アクションを指定する](../../core/specifying-soap-actions-for-wcf-send-adapters.md)します。</span><span class="sxs-lookup"><span data-stu-id="7b96d-108">For more information about specifying SOAP action, see [Specifying SOAP Actions for WCF Send Adapters](../../core/specifying-soap-actions-for-wcf-send-adapters.md).</span></span>
  
## <a name="enter-soap-action-at-design-time"></a><span data-ttu-id="7b96d-109">デザイン時に SOAP アクションを入力します。</span><span class="sxs-lookup"><span data-stu-id="7b96d-109">Enter SOAP Action at Design Time</span></span>  
 <span data-ttu-id="7b96d-110">式図形を含めることによって、デザイン時のオーケストレーションの一部として SOAP アクションを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7b96d-110">For design time, you must specify the SOAP action as part of orchestration by including an expression shape.</span></span>  
  
1.  <span data-ttu-id="7b96d-111">Biztalk オーケストレーションはからドラッグすることで、式図形を含める、 **BizTalk オーケストレーション**ツールボックスです。</span><span class="sxs-lookup"><span data-stu-id="7b96d-111">In the BizTalk orchestration include an Expression shape by dragging it from the **BizTalk Orchestration** toolbox.</span></span>  
  
2.  <span data-ttu-id="7b96d-112">ダブルクリックして、**式**図形、BizTalk 式エディターを開きます。</span><span class="sxs-lookup"><span data-stu-id="7b96d-112">Double-click the **Expression** shape to open the BizTalk Expression Editor.</span></span>  
  
3.  <span data-ttu-id="7b96d-113">BizTalk 式エディタで、アクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="7b96d-113">Specify the action in the BizTalk Expression Editor.</span></span> <span data-ttu-id="7b96d-114">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="7b96d-114">For example:</span></span>  
  
    ```  
    OutboundMessage(WCF.Action)="http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Insert"  
    ```  
  
     <span data-ttu-id="7b96d-115">詳細については**式**図形と、BizTalk 式エディタでを参照してください[式を作成する方法](../../core/how-to-create-expressions.md)します。</span><span class="sxs-lookup"><span data-stu-id="7b96d-115">For more information about **Expression** shape and the BizTalk Expression Editor, see [How to Create Expressions](../../core/how-to-create-expressions.md).</span></span>  
  
## <a name="enter-soap-action-at-run-time"></a><span data-ttu-id="7b96d-116">実行時に SOAP アクションを入力します。</span><span class="sxs-lookup"><span data-stu-id="7b96d-116">Enter SOAP Action at run time</span></span>  
 <span data-ttu-id="7b96d-117">実行時に、Wcf-custom または Wcf-siebel ポートのプロパティ ダイアログ ボックスの一部として SOAP アクションを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7b96d-117">For run time, you must specify the SOAP action as part of the WCF-Custom or WCF-Siebel port properties dialog box.</span></span>  
  
#### <a name="enter-a-soap-action-for-the-wcf-custom-port"></a><span data-ttu-id="7b96d-118">WCF カスタム ポートの SOAP アクションを入力します。</span><span class="sxs-lookup"><span data-stu-id="7b96d-118">Enter a SOAP action for the WCF-Custom port</span></span>  
  
1. <span data-ttu-id="7b96d-119">開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="7b96d-119">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2. <span data-ttu-id="7b96d-120">コンソール ツリーで、展開**BizTalk グループ**の順に展開**アプリケーション**、 をクリックし、**送信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="7b96d-120">In the console tree, expand **BizTalk Group**, then expand **Applications**, and then click **Send Ports**.</span></span> <span data-ttu-id="7b96d-121">右側のウィンドウでは、ポートを作成または既存のポートを選択できます。</span><span class="sxs-lookup"><span data-stu-id="7b96d-121">In the right pane, you can choose to create a port or select an existing port.</span></span>  
  
3. <span data-ttu-id="7b96d-122">ポートのプロパティ ダイアログ ボックスから、**型**ドロップダウン リストで、 **Wcf-custom**、 をクリックし、**構成**します。</span><span class="sxs-lookup"><span data-stu-id="7b96d-122">In the port properties dialog box, from the **Type** drop-down list, select **WCF-Custom**, and then click **Configure**.</span></span>  
  
4. <span data-ttu-id="7b96d-123">**Wcf-custom トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**全般**タブ。</span><span class="sxs-lookup"><span data-stu-id="7b96d-123">In the **WCF-Custom Transport Properties** dialog box, click the **General** tab.</span></span>  
  
5. <span data-ttu-id="7b96d-124">**アクション**テキスト ボックスで、操作の SOAP アクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="7b96d-124">In the **Action** text box, specify the SOAP action for the operation.</span></span> <span data-ttu-id="7b96d-125">次の方法では、アクションを指定できます。</span><span class="sxs-lookup"><span data-stu-id="7b96d-125">You can specify the action in the following ways:</span></span>  
  
   -   <span data-ttu-id="7b96d-126">**シングル アクション形式を使用して**します。</span><span class="sxs-lookup"><span data-stu-id="7b96d-126">**By using the single action format**.</span></span> <span data-ttu-id="7b96d-127">Wcf-custom 送信ポートし、1 つの操作のメッセージを受信する場合は、この形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="7b96d-127">Use this format if the WCF-Custom port sends and receive messages for a single operation.</span></span> <span data-ttu-id="7b96d-128">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="7b96d-128">For example:</span></span>  
  
       ```  
       http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Insert  
       ```  
  
   -   <span data-ttu-id="7b96d-129">**アクション マッピング形式を使用して**します。</span><span class="sxs-lookup"><span data-stu-id="7b96d-129">**By using the action mapping format**.</span></span> <span data-ttu-id="7b96d-130">1 つの WCF カスタム ポートが 1 つ以上の操作のメッセージを送受信する場合は、この形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="7b96d-130">Use this format if a single WCF-Custom port sends and receives messages for more than one operation.</span></span> <span data-ttu-id="7b96d-131">たとえば、送受信 (アカウントのビジネス コンポーネントに対して、挿入操作を実行) を Op1 と Op2 (アカウントのビジネス コンポーネントに対する更新操作を実行) にメッセージを受け取る 1 つの WCF カスタム ポートを SOAP アクションで指定できます、次方法:</span><span class="sxs-lookup"><span data-stu-id="7b96d-131">For example, if a single WCF-Custom port sends and receives messages for Op1 (to perform an Insert operation on Account business component) and Op2 (to perform an Update operation on Account business component), the SOAP action can be specified in the following manner:</span></span>  
  
       ```  
       <BtsActionMapping>  
         <Operation Name="Op1" Action="http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Insert " />  
         <Operation Name="Op2" Action="http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Update " />  
       </BtsActionMapping>  
       ```  
  
        <span data-ttu-id="7b96d-132">このアプローチには、一連のアクションを指定して、そのため、同じポートを経由するさまざまなアクションの種類に属するメッセージの有効化の観点から高い柔軟性が提供されます。</span><span class="sxs-lookup"><span data-stu-id="7b96d-132">This approach provides greater flexibility in terms of specifying a set of actions and hence enabling messages belonging to different action types to flow through the same port.</span></span>  
  
        <span data-ttu-id="7b96d-133">SOAP アクションの形式は操作ごとに異なります。</span><span class="sxs-lookup"><span data-stu-id="7b96d-133">The format for the SOAP action is different for each operation.</span></span> <span data-ttu-id="7b96d-134">各操作のアクションの形式の詳細については、次を参照してください。[メッセージとメッセージ スキーマ](messages-and-message-schemas-for-siebel-adapter-in-biztalk.md)します。</span><span class="sxs-lookup"><span data-stu-id="7b96d-134">For more information about action format for each operation, see [Messages and message schemas](messages-and-message-schemas-for-siebel-adapter-in-biztalk.md).</span></span>
  
#### <a name="enter-a-soap-action-for-the-wcf-siebel-port"></a><span data-ttu-id="7b96d-135">Wcf-siebel ポートの SOAP アクションを入力します。</span><span class="sxs-lookup"><span data-stu-id="7b96d-135">Enter a SOAP action for the WCF-Siebel port</span></span>  
  
1. <span data-ttu-id="7b96d-136">開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="7b96d-136">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2. <span data-ttu-id="7b96d-137">Wcf-siebel アダプターの追加、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="7b96d-137">Add the WCF-Siebel adapter to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="7b96d-138">手順については、次を参照してください。 [Siebel アダプターを BizTalk Server 管理コンソールに追加](../../adapters-and-accelerators/adapter-siebel/add-the-siebel-adapter-to-biztalk-server-administration-console.md)します。</span><span class="sxs-lookup"><span data-stu-id="7b96d-138">For instructions, see [Add the Siebel Adapter to BizTalk Server Administration Console](../../adapters-and-accelerators/adapter-siebel/add-the-siebel-adapter-to-biztalk-server-administration-console.md).</span></span>  
  
3. <span data-ttu-id="7b96d-139">コンソール ツリーで、展開**BizTalk グループ**の順に展開**アプリケーション**、 をクリックし、**送信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="7b96d-139">In the console tree, expand **BizTalk Group**, then expand **Applications**, and then click **Send Ports**.</span></span> <span data-ttu-id="7b96d-140">右側のウィンドウでは、ポートを作成または既存のポートを選択できます。</span><span class="sxs-lookup"><span data-stu-id="7b96d-140">In the right pane, you can choose to create a port or select an existing port.</span></span>  
  
4. <span data-ttu-id="7b96d-141">ポートのプロパティ ダイアログ ボックスから、**型**ドロップダウン リスト、選択、Wcf-siebel アダプター以前では、追加し、をクリックし、**構成**します。</span><span class="sxs-lookup"><span data-stu-id="7b96d-141">In the port properties dialog box, from the **Type** drop-down list, select the WCF-Siebel adapter you add earlier, and then click **Configure**.</span></span>  
  
5. <span data-ttu-id="7b96d-142">ポートのプロパティ ダイアログ ボックスでをクリックして、**全般**タブ。</span><span class="sxs-lookup"><span data-stu-id="7b96d-142">In the port properties dialog box, click the **General** tab.</span></span>  
  
6. <span data-ttu-id="7b96d-143">**アクション**テキスト ボックスで、操作の SOAP アクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="7b96d-143">In the **Action** text box, specify the SOAP action for the operation.</span></span> <span data-ttu-id="7b96d-144">次の方法では、アクションを指定できます。</span><span class="sxs-lookup"><span data-stu-id="7b96d-144">You can specify the action in the following ways:</span></span>  
  
   -   <span data-ttu-id="7b96d-145">**シングル アクション形式を使用して**します。</span><span class="sxs-lookup"><span data-stu-id="7b96d-145">**By using the single action format**.</span></span> <span data-ttu-id="7b96d-146">Wcf-custom 送信ポートし、1 つの操作のメッセージを受信する場合は、この形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="7b96d-146">Use this format if the WCF-Custom port sends and receive messages for a single operation.</span></span> <span data-ttu-id="7b96d-147">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="7b96d-147">For example:</span></span>  
  
       ```  
       http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Insert  
       ```  
  
   -   <span data-ttu-id="7b96d-148">**アクション マッピング形式を使用して**します。</span><span class="sxs-lookup"><span data-stu-id="7b96d-148">**By using the action mapping format**.</span></span> <span data-ttu-id="7b96d-149">1 つの WCF カスタム ポートが 1 つ以上の操作のメッセージを送受信する場合は、この形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="7b96d-149">Use this format if a single WCF-Custom port sends and receives messages for more than one operation.</span></span> <span data-ttu-id="7b96d-150">たとえば、送受信 (アカウントのビジネス コンポーネントに対して、挿入操作を実行) を Op1 と Op2 (アカウントのビジネス コンポーネントに対する更新操作を実行) にメッセージを受け取る 1 つの WCF カスタム ポートを SOAP アクションで指定できます、次方法:</span><span class="sxs-lookup"><span data-stu-id="7b96d-150">For example, if a single WCF-Custom port sends and receives messages for Op1 (to perform an Insert operation on Account business component) and Op2 (to perform an Update operation on Account business component), the SOAP action can be specified in the following manner:</span></span>  
  
       ```  
       <BtsActionMapping>  
         <Operation Name="Op1" Action="http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Insert " />  
         <Operation Name="Op2" Action="http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Update " />  
       </BtsActionMapping>  
       ```  
  
        <span data-ttu-id="7b96d-151">このアプローチには、一連のアクションを指定して、そのため、同じポートを経由するさまざまなアクションの種類に属するメッセージの有効化の観点から高い柔軟性が提供されます。</span><span class="sxs-lookup"><span data-stu-id="7b96d-151">This approach provides greater flexibility in terms of specifying a set of actions and hence enabling messages belonging to different action types to flow through the same port.</span></span>  
  
        <span data-ttu-id="7b96d-152">SOAP アクションの形式は操作ごとに異なります。</span><span class="sxs-lookup"><span data-stu-id="7b96d-152">The format for the SOAP action is different for each operation.</span></span> <span data-ttu-id="7b96d-153">各操作のアクションの形式の詳細については、次を参照してください。[メッセージとメッセージ スキーマ](messages-and-message-schemas-for-siebel-adapter-in-biztalk.md)します。</span><span class="sxs-lookup"><span data-stu-id="7b96d-153">For more information about action format for each operation, see [Messages and message schemas](messages-and-message-schemas-for-siebel-adapter-in-biztalk.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="7b96d-154">参照</span><span class="sxs-lookup"><span data-stu-id="7b96d-154">See Also</span></span>  
[<span data-ttu-id="7b96d-155">Siebel アダプターを使用した BizTalk アプリケーションを作成する構成要素</span><span class="sxs-lookup"><span data-stu-id="7b96d-155">Building blocks to create BizTalk applications with the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/building-blocks-to-create-biztalk-applications-with-the-siebel-adapter.md)