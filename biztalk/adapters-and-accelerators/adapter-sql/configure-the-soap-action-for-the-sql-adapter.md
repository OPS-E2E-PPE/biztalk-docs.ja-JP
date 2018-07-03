---
title: Biztalk SQL アダプターの SOAP アクションの構成 |Microsoft Docs
description: Visual Studio での SOAP アクションの入力または BizTalk アダプター パック (BAP) で、Wcf-custom または WCF-SQL アダプターを使用して、
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: acd7f60b-c27f-4988-a67c-e56ef8d38f66
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a927740ba04a0fd1b080e73ef60892ffdc9bf385
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980523"
---
# <a name="configure-the-soap-action-for-the-sql-adapter"></a><span data-ttu-id="28f5f-103">SQL アダプタの SOAP アクションを構成します。</span><span class="sxs-lookup"><span data-stu-id="28f5f-103">Configure the SOAP action for the SQL adapter</span></span>
<span data-ttu-id="28f5f-104">WCF ベースを使用して SQL Server 上の任意の操作を実行する[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]、SOAP アクションを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="28f5f-104">To perform any operation on SQL Server using the WCF-based [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], you must specify a SOAP action.</span></span> <span data-ttu-id="28f5f-105">SOAP アクションは、どのようなアクションが実行されるアダプターに通信します。</span><span class="sxs-lookup"><span data-stu-id="28f5f-105">The SOAP action communicates to the adapter what action should be performed.</span></span> <span data-ttu-id="28f5f-106">いずれかから SOAP アクションを指定できます[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]またはから、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="28f5f-106">You can specify the SOAP action either from [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] or from the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="28f5f-107">ただし、両方の場所からの SOAP アクションを指定する場合、アクションから指定した[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]は上書きされます。</span><span class="sxs-lookup"><span data-stu-id="28f5f-107">However, if you specify the SOAP action from both locations, the action you specified from [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] will be overridden.</span></span>  
  
 <span data-ttu-id="28f5f-108">SOAP アクションを指定する方法については、次を参照してください。 [WCF 送信アダプター用の SOAP アクションを指定する](../../core/specifying-soap-actions-for-wcf-send-adapters.md)します。</span><span class="sxs-lookup"><span data-stu-id="28f5f-108">For more information about specifying SOAP action, see [Specifying SOAP Actions for WCF Send Adapters](../../core/specifying-soap-actions-for-wcf-send-adapters.md).</span></span>
  
## <a name="enter-the-soap-action-in-visual-studio"></a><span data-ttu-id="28f5f-109">Visual Studio での SOAP アクションを入力します。</span><span class="sxs-lookup"><span data-stu-id="28f5f-109">Enter the SOAP action in Visual Studio</span></span>  
 <span data-ttu-id="28f5f-110">[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]を使用して、オーケストレーションの一部として SOAP アクションを指定する必要があります、**式**図形。</span><span class="sxs-lookup"><span data-stu-id="28f5f-110">From [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], you must specify the SOAP action as part of the orchestration by using an **Expression** shape.</span></span>  
  
1.  <span data-ttu-id="28f5f-111">BizTalk オーケストレーションで含める、**式**図形からドラッグすることで、 **BizTalk オーケストレーション**ツールボックス。</span><span class="sxs-lookup"><span data-stu-id="28f5f-111">In the BizTalk orchestration, include an **Expression** shape by dragging it from the **BizTalk Orchestration** toolbox.</span></span>  
  
2.  <span data-ttu-id="28f5f-112">ダブルクリックして、**式**図形を BizTalk 式エディタを開きます。</span><span class="sxs-lookup"><span data-stu-id="28f5f-112">Double-click the **Expression** shape to open BizTalk Expression Editor.</span></span>  
  
3.  <span data-ttu-id="28f5f-113">BizTalk 式エディタで、アクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="28f5f-113">Specify the action in BizTalk Expression Editor.</span></span> <span data-ttu-id="28f5f-114">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="28f5f-114">For example:</span></span>  
  
    ```  
    OutboundMessage(WCF.Action)="TableOp/Insert/dbo/Employee"  
    ```  
  
     <span data-ttu-id="28f5f-115">詳細については、**式**図形と BizTalk 式エディターを参照してください[式を作成する方法](../../core/how-to-create-expressions.md)します。</span><span class="sxs-lookup"><span data-stu-id="28f5f-115">For more information about the **Expression** shape and BizTalk Expression Editor, see [How to Create Expressions](../../core/how-to-create-expressions.md).</span></span>
  
## <a name="enter-the-soap-action-from-the-biztalk-server-administration-console"></a><span data-ttu-id="28f5f-116">BizTalk Server 管理コンソールからの SOAP アクションを入力します。</span><span class="sxs-lookup"><span data-stu-id="28f5f-116">Enter the SOAP action from the BizTalk Server Administration console</span></span>  
 <span data-ttu-id="28f5f-117">[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、Wcf-custom または WCF SQL ポートの構成の一部として SOAP アクションを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="28f5f-117">From the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console, you can specify the SOAP action as part of the WCF-Custom or WCF-SQL port configuration.</span></span>  
  
### <a name="enter-a-soap-action-for-the-wcf-custom-port"></a><span data-ttu-id="28f5f-118">WCF カスタム ポートの SOAP アクションを入力します。</span><span class="sxs-lookup"><span data-stu-id="28f5f-118">Enter a SOAP action for the WCF-Custom port</span></span>  
  
1. <span data-ttu-id="28f5f-119">開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="28f5f-119">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2. <span data-ttu-id="28f5f-120">コンソール ツリーで、展開**BizTalk グループ**の順に展開**アプリケーション**、 をクリックし、**送信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="28f5f-120">In the console tree, expand **BizTalk Group**, then expand **Applications**, and then click **Send Ports**.</span></span> <span data-ttu-id="28f5f-121">右側のウィンドウでは、ポートを作成または既存のポートを選択できます。</span><span class="sxs-lookup"><span data-stu-id="28f5f-121">In the right pane, you can choose to create a port or select an existing port.</span></span>  
  
3. <span data-ttu-id="28f5f-122">ポートのプロパティ ダイアログ ボックスから、**型**ドロップダウン リストで、 **Wcf-custom**、 をクリックし、**構成**します。</span><span class="sxs-lookup"><span data-stu-id="28f5f-122">In the port properties dialog box, from the **Type** drop-down list, select **WCF-Custom**, and then click **Configure**.</span></span>  
  
4. <span data-ttu-id="28f5f-123">**Wcf-custom トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**全般**タブ。</span><span class="sxs-lookup"><span data-stu-id="28f5f-123">In the **WCF-Custom Transport Properties** dialog box, click the **General** tab.</span></span>  
  
5. <span data-ttu-id="28f5f-124">**アクション**テキスト ボックスで、操作の SOAP アクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="28f5f-124">In the **Action** text box, specify the SOAP action for the operation.</span></span> <span data-ttu-id="28f5f-125">次の方法では、アクションを指定できます。</span><span class="sxs-lookup"><span data-stu-id="28f5f-125">You can specify the action in the following ways:</span></span>  
  
   -   <span data-ttu-id="28f5f-126">**シングル アクション形式を使用して**します。</span><span class="sxs-lookup"><span data-stu-id="28f5f-126">**By using the single action format**.</span></span> <span data-ttu-id="28f5f-127">Wcf-custom 送信ポートし、1 つの操作のメッセージを受信する場合は、この形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="28f5f-127">Use this format if the WCF-Custom port sends and receive messages for a single operation.</span></span> <span data-ttu-id="28f5f-128">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="28f5f-128">For example:</span></span>  
  
       ```  
       TableOp/Insert/dbo/Employee  
       ```  
  
   -   <span data-ttu-id="28f5f-129">**アクション マッピング形式を使用して**します。</span><span class="sxs-lookup"><span data-stu-id="28f5f-129">**By using the action mapping format**.</span></span> <span data-ttu-id="28f5f-130">1 つの WCF カスタム ポートが 1 つ以上の操作のメッセージを送受信する場合は、この形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="28f5f-130">Use this format if a single WCF-Custom port sends and receives messages for more than one operation.</span></span> <span data-ttu-id="28f5f-131">たとえば、送受信 (Employee テーブルにレコードを挿入) するための Op1 と Op2 (従業員テーブル内のレコードを更新) するメッセージを受信する 1 つの WCF カスタム ポートを SOAP アクションは次のように指定できます。</span><span class="sxs-lookup"><span data-stu-id="28f5f-131">For example, if a single WCF-Custom port sends and receives messages for Op1 (to insert records in the Employee table) and Op2 (to update records in the Employee table), the SOAP action can be specified in the following manner:</span></span>  
  
       ```  
       <BtsActionMapping>  
         <Operation Name="Op1" Action="TableOp/Insert/dbo/Employee" />  
         <Operation Name="Op2" Action="TableOp/Update/dbo/Employee" />  
       </BtsActionMapping>  
       ```  
  
        <span data-ttu-id="28f5f-132">アクション マッピングのアプローチは、アクションのセットを指定して、そのため、同じポートを経由するさまざまなアクションの種類に属しているメッセージの有効化の観点からの柔軟性を提供します。</span><span class="sxs-lookup"><span data-stu-id="28f5f-132">The action mapping approach provides greater flexibility in terms of specifying a set of actions, and hence enabling messages that belong to different action types to flow through the same port.</span></span>  
  
        <span data-ttu-id="28f5f-133">SOAP アクションの形式は操作ごとに異なります。</span><span class="sxs-lookup"><span data-stu-id="28f5f-133">The format for the SOAP action is different for each operation.</span></span> <span data-ttu-id="28f5f-134">各操作のアクションの形式の詳細については、次を参照してください。[メッセージとメッセージ スキーマ](messages-and-message-schemas-for-biztalk-adapter-for-sql-server.md)します。</span><span class="sxs-lookup"><span data-stu-id="28f5f-134">For more information about the action format for each operation, see [Messages and message schemas](messages-and-message-schemas-for-biztalk-adapter-for-sql-server.md).</span></span>
  
### <a name="enter-a-soap-action-for-the-wcf-sql-port"></a><span data-ttu-id="28f5f-135">WCF SQL ポートの SOAP アクションを入力します。</span><span class="sxs-lookup"><span data-stu-id="28f5f-135">Enter a SOAP action for the WCF-SQL port</span></span>  
  
1. <span data-ttu-id="28f5f-136">開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="28f5f-136">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2. <span data-ttu-id="28f5f-137">WCF-SQL アダプターを追加、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="28f5f-137">Add the WCF-SQL adapter to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="28f5f-138">手順については、次を参照してください。 [SQL アダプタを BizTalk Server 管理コンソールに追加する](../../adapters-and-accelerators/adapter-sql/adding-the-sql-adapter-to-biztalk-server-administration-console.md)します。</span><span class="sxs-lookup"><span data-stu-id="28f5f-138">For instructions, see [Adding the SQL Adapter to BizTalk Server Administration Console](../../adapters-and-accelerators/adapter-sql/adding-the-sql-adapter-to-biztalk-server-administration-console.md).</span></span>  
  
3. <span data-ttu-id="28f5f-139">コンソール ツリーで、展開**BizTalk グループ**の順に展開**アプリケーション**、 をクリックし、**送信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="28f5f-139">In the console tree, expand **BizTalk Group**, then expand **Applications**, and then click **Send Ports**.</span></span> <span data-ttu-id="28f5f-140">右側のウィンドウでは、ポートを作成または既存のポートを選択できます。</span><span class="sxs-lookup"><span data-stu-id="28f5f-140">In the right pane, you can choose to create a port or select an existing port.</span></span>  
  
4. <span data-ttu-id="28f5f-141">ポートのプロパティ ダイアログ ボックスから、**型**ドロップダウン リストでは、先ほど追加した WCF-SQL アダプターを選択し、順にクリックします**構成**します。</span><span class="sxs-lookup"><span data-stu-id="28f5f-141">In the port properties dialog box, from the **Type** drop-down list, select the WCF-SQL adapter you added earlier, and then click **Configure**.</span></span>  
  
5. <span data-ttu-id="28f5f-142">トランスポートのプロパティ ダイアログ ボックスでをクリックして、**全般**タブ。</span><span class="sxs-lookup"><span data-stu-id="28f5f-142">In the transport properties dialog box, click the **General** tab.</span></span>  
  
6. <span data-ttu-id="28f5f-143">**アクション**テキスト ボックスで、操作の SOAP アクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="28f5f-143">In the **Action** text box, specify the SOAP action for the operation.</span></span> <span data-ttu-id="28f5f-144">次の方法では、アクションを指定できます。</span><span class="sxs-lookup"><span data-stu-id="28f5f-144">You can specify the action in the following ways:</span></span>  
  
   -   <span data-ttu-id="28f5f-145">**シングル アクション形式を使用して**します。</span><span class="sxs-lookup"><span data-stu-id="28f5f-145">**By using the single action format**.</span></span> <span data-ttu-id="28f5f-146">WCF SQL 送信ポートし、1 つの操作のメッセージを受信する場合は、この形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="28f5f-146">Use this format if the WCF-SQL port sends and receive messages for a single operation.</span></span> <span data-ttu-id="28f5f-147">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="28f5f-147">For example:</span></span>  
  
       ```  
       TableOp/Insert/dbo/Employee  
       ```  
  
   -   <span data-ttu-id="28f5f-148">**アクション マッピング形式を使用して**します。</span><span class="sxs-lookup"><span data-stu-id="28f5f-148">**By using the action mapping format**.</span></span> <span data-ttu-id="28f5f-149">1 つの WCF SQL ポートが 1 つ以上の操作のメッセージを送受信する場合は、この形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="28f5f-149">Use this format if a single WCF-SQL port sends and receives messages for more than one operation.</span></span> <span data-ttu-id="28f5f-150">たとえば、送受信 (Employee テーブルにレコードを挿入) するための Op1 と Op2 (従業員テーブル内のレコードを更新) するメッセージを受信する 1 つの WCF SQL ポートを SOAP アクションは次のように指定できます。</span><span class="sxs-lookup"><span data-stu-id="28f5f-150">For example, if a single WCF-SQL port sends and receives messages for Op1 (to insert records in the Employee table) and Op2 (to update records in the Employee table), the SOAP action can be specified in the following manner:</span></span>  
  
       ```  
       <BtsActionMapping>  
         <Operation Name="Op1" Action="TableOp/Insert/dbo/Employee" />  
         <Operation Name="Op2" Action="TableOp/Update/dbo/Employee" />  
       </BtsActionMapping>  
       ```  
  
        <span data-ttu-id="28f5f-151">アクション マッピングのアプローチは、アクションのセットを指定して、そのため、同じポートを経由するさまざまなアクションの種類に属しているメッセージの有効化の観点からの柔軟性を提供します。</span><span class="sxs-lookup"><span data-stu-id="28f5f-151">The action mapping approach provides greater flexibility in terms of specifying a set of actions, and hence enabling messages that belong to different action types to flow through the same port.</span></span>  
  
        <span data-ttu-id="28f5f-152">SOAP アクションの形式は操作ごとに異なります。</span><span class="sxs-lookup"><span data-stu-id="28f5f-152">The format for the SOAP action is different for each operation.</span></span> <span data-ttu-id="28f5f-153">各操作のアクションの形式の詳細については、次を参照してください。[メッセージとメッセージ スキーマ](messages-and-message-schemas-for-biztalk-adapter-for-sql-server.md)します。</span><span class="sxs-lookup"><span data-stu-id="28f5f-153">For more information about the action format for each operation, see [Messages and message schemas](messages-and-message-schemas-for-biztalk-adapter-for-sql-server.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="28f5f-154">参照</span><span class="sxs-lookup"><span data-stu-id="28f5f-154">See Also</span></span>  
[<span data-ttu-id="28f5f-155">SQL アダプターを使用した BizTalk アプリケーションを開発する構成要素</span><span class="sxs-lookup"><span data-stu-id="28f5f-155">Building blocks to develop BizTalk applications with the SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/building-blocks-to-develop-biztalk-applications-with-the-sql-adapter.md)