---
title: "Biztalk SQL アダプターの SOAP アクションの構成 |Microsoft ドキュメント"
description: "Visual Studio で SOAP アクションを入力または BizTalk アダプター パック (BAP) で、Wcf-custom アダプターまたは WCF SQL アダプターを使用してください"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: acd7f60b-c27f-4988-a67c-e56ef8d38f66
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d4e342353b13848cca1c332d4568f541e59924cc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="configure-the-soap-action-for-the-sql-adapter"></a><span data-ttu-id="a223f-103">SQL アダプタの SOAP アクションを構成します。</span><span class="sxs-lookup"><span data-stu-id="a223f-103">Configure the SOAP action for the SQL adapter</span></span>
<span data-ttu-id="a223f-104">WCF ベースを使用して SQL Server で操作を実行する[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]、SOAP アクションを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a223f-104">To perform any operation on SQL Server using the WCF-based [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], you must specify a SOAP action.</span></span> <span data-ttu-id="a223f-105">SOAP アクションは、どのようなアクションを実行する必要があります、アダプターに通信します。</span><span class="sxs-lookup"><span data-stu-id="a223f-105">The SOAP action communicates to the adapter what action should be performed.</span></span> <span data-ttu-id="a223f-106">SOAP アクションのいずれかを指定する[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]またはから、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="a223f-106">You can specify the SOAP action either from [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] or from the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="a223f-107">ただし、両方の場所からの SOAP アクションを指定する場合、アクション指定したから[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]は上書きされます。</span><span class="sxs-lookup"><span data-stu-id="a223f-107">However, if you specify the SOAP action from both locations, the action you specified from [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] will be overridden.</span></span>  
  
 <span data-ttu-id="a223f-108">SOAP アクションを指定する方法の詳細については、次を参照してください。 [WCF 送信アダプタ用の SOAP アクションの指定](../../core/specifying-soap-actions-for-wcf-send-adapters.md)です。</span><span class="sxs-lookup"><span data-stu-id="a223f-108">For more information about specifying SOAP action, see [Specifying SOAP Actions for WCF Send Adapters](../../core/specifying-soap-actions-for-wcf-send-adapters.md).</span></span>
  
## <a name="enter-the-soap-action-in-visual-studio"></a><span data-ttu-id="a223f-109">Visual Studio での SOAP アクションを入力します。</span><span class="sxs-lookup"><span data-stu-id="a223f-109">Enter the SOAP action in Visual Studio</span></span>  
 <span data-ttu-id="a223f-110">[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]、オーケストレーションの一部として使用して SOAP アクションを指定する必要があります、**式**図形です。</span><span class="sxs-lookup"><span data-stu-id="a223f-110">From [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], you must specify the SOAP action as part of the orchestration by using an **Expression** shape.</span></span>  
  
1.  <span data-ttu-id="a223f-111">BizTalk オーケストレーションが含まれる、**式**図形からドラッグすることで、 **BizTalk オーケストレーション**ツールボックスします。</span><span class="sxs-lookup"><span data-stu-id="a223f-111">In the BizTalk orchestration, include an **Expression** shape by dragging it from the **BizTalk Orchestration** toolbox.</span></span>  
  
2.  <span data-ttu-id="a223f-112">ダブルクリックして、**式**図形を BizTalk 式エディタを開きます。</span><span class="sxs-lookup"><span data-stu-id="a223f-112">Double-click the **Expression** shape to open BizTalk Expression Editor.</span></span>  
  
3.  <span data-ttu-id="a223f-113">BizTalk 式エディタで、アクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="a223f-113">Specify the action in BizTalk Expression Editor.</span></span> <span data-ttu-id="a223f-114">例:</span><span class="sxs-lookup"><span data-stu-id="a223f-114">For example:</span></span>  
  
    ```  
    OutboundMessage(WCF.Action)="TableOp/Insert/dbo/Employee"  
    ```  
  
     <span data-ttu-id="a223f-115">詳細については、**式**図形および BizTalk 式エディターを参照してください[式を作成する方法](../../core/how-to-create-expressions.md)です。</span><span class="sxs-lookup"><span data-stu-id="a223f-115">For more information about the **Expression** shape and BizTalk Expression Editor, see [How to Create Expressions](../../core/how-to-create-expressions.md).</span></span>
  
## <a name="enter-the-soap-action-from-the-biztalk-server-administration-console"></a><span data-ttu-id="a223f-116">BizTalk Server 管理コンソールからの SOAP アクションを入力します。</span><span class="sxs-lookup"><span data-stu-id="a223f-116">Enter the SOAP action from the BizTalk Server Administration console</span></span>  
 <span data-ttu-id="a223f-117">[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、Wcf-custom または WCF SQL ポートの構成の一部として SOAP アクションを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="a223f-117">From the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console, you can specify the SOAP action as part of the WCF-Custom or WCF-SQL port configuration.</span></span>  
  
### <a name="enter-a-soap-action-for-the-wcf-custom-port"></a><span data-ttu-id="a223f-118">WCF カスタム ポートの SOAP アクションを入力します。</span><span class="sxs-lookup"><span data-stu-id="a223f-118">Enter a SOAP action for the WCF-Custom port</span></span>  
  
1.  <span data-ttu-id="a223f-119">開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="a223f-119">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="a223f-120">コンソール ツリーで  **BizTalk グループ**の順に展開**アプリケーション**、順にクリック**送信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="a223f-120">In the console tree, expand **BizTalk Group**, then expand **Applications**, and then click **Send Ports**.</span></span> <span data-ttu-id="a223f-121">右側のウィンドウでは、ポートを作成または既存のポートを選択できます。</span><span class="sxs-lookup"><span data-stu-id="a223f-121">In the right pane, you can choose to create a port or select an existing port.</span></span>  
  
3.  <span data-ttu-id="a223f-122">ポートのプロパティ ダイアログ ボックスから、**型**ドロップダウン リストで、 **Wcf-custom**、クリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="a223f-122">In the port properties dialog box, from the **Type** drop-down list, select **WCF-Custom**, and then click **Configure**.</span></span>  
  
4.  <span data-ttu-id="a223f-123">**Wcf-custom トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**全般**タブです。</span><span class="sxs-lookup"><span data-stu-id="a223f-123">In the **WCF-Custom Transport Properties** dialog box, click the **General** tab.</span></span>  
  
5.  <span data-ttu-id="a223f-124">**アクション**テキスト ボックスで、操作の SOAP アクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="a223f-124">In the **Action** text box, specify the SOAP action for the operation.</span></span> <span data-ttu-id="a223f-125">次の方法では、アクションを指定できます。</span><span class="sxs-lookup"><span data-stu-id="a223f-125">You can specify the action in the following ways:</span></span>  
  
    -   <span data-ttu-id="a223f-126">**シングル アクション形式を使用して、**です。</span><span class="sxs-lookup"><span data-stu-id="a223f-126">**By using the single action format**.</span></span> <span data-ttu-id="a223f-127">Wcf-custom 送信ポートし、1 つの操作のメッセージを受信する場合は、この形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="a223f-127">Use this format if the WCF-Custom port sends and receive messages for a single operation.</span></span> <span data-ttu-id="a223f-128">例:</span><span class="sxs-lookup"><span data-stu-id="a223f-128">For example:</span></span>  
  
        ```  
        TableOp/Insert/dbo/Employee  
        ```  
  
    -   <span data-ttu-id="a223f-129">**アクション マッピング形式を使用して、**です。</span><span class="sxs-lookup"><span data-stu-id="a223f-129">**By using the action mapping format**.</span></span> <span data-ttu-id="a223f-130">1 つの WCF カスタム ポートを送信し、1 つ以上の操作のメッセージを受け取る場合は、この形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="a223f-130">Use this format if a single WCF-Custom port sends and receives messages for more than one operation.</span></span> <span data-ttu-id="a223f-131">たとえば、1 つの WCF カスタム ポートを送信および (レコードを挿入する Employee テーブルの) Op1、Op2 (レコードを更新する Employee テーブル) のメッセージを受け取る場合、SOAP アクションは、次のように指定できます。</span><span class="sxs-lookup"><span data-stu-id="a223f-131">For example, if a single WCF-Custom port sends and receives messages for Op1 (to insert records in the Employee table) and Op2 (to update records in the Employee table), the SOAP action can be specified in the following manner:</span></span>  
  
        ```  
        <BtsActionMapping>  
          <Operation Name="Op1" Action="TableOp/Insert/dbo/Employee" />  
          <Operation Name="Op2" Action="TableOp/Update/dbo/Employee" />  
        </BtsActionMapping>  
        ```  
  
         <span data-ttu-id="a223f-132">アクション マッピングのアプローチでは、アクションのセットを指定して、そのため、同じポートを通過するさまざまなアクションの種類に属しているメッセージの有効化に関して柔軟性を提供します。</span><span class="sxs-lookup"><span data-stu-id="a223f-132">The action mapping approach provides greater flexibility in terms of specifying a set of actions, and hence enabling messages that belong to different action types to flow through the same port.</span></span>  
  
         <span data-ttu-id="a223f-133">SOAP アクションの形式は操作ごとに異なります。</span><span class="sxs-lookup"><span data-stu-id="a223f-133">The format for the SOAP action is different for each operation.</span></span> <span data-ttu-id="a223f-134">各操作の操作の形式の詳細については、次を参照してください。[メッセージおよびメッセージ スキーマ](messages-and-message-schemas-for-biztalk-adapter-for-sql-server.md)です。</span><span class="sxs-lookup"><span data-stu-id="a223f-134">For more information about the action format for each operation, see [Messages and message schemas](messages-and-message-schemas-for-biztalk-adapter-for-sql-server.md).</span></span>
  
### <a name="enter-a-soap-action-for-the-wcf-sql-port"></a><span data-ttu-id="a223f-135">WCF SQL ポートの SOAP アクションを入力します。</span><span class="sxs-lookup"><span data-stu-id="a223f-135">Enter a SOAP action for the WCF-SQL port</span></span>  
  
1.  <span data-ttu-id="a223f-136">開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="a223f-136">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="a223f-137">WCF-SQL アダプターの追加、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="a223f-137">Add the WCF-SQL adapter to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="a223f-138">手順については、次を参照してください。 [SQL アダプタを BizTalk Server 管理コンソールに追加する](../../adapters-and-accelerators/adapter-sql/adding-the-sql-adapter-to-biztalk-server-administration-console.md)です。</span><span class="sxs-lookup"><span data-stu-id="a223f-138">For instructions, see [Adding the SQL Adapter to BizTalk Server Administration Console](../../adapters-and-accelerators/adapter-sql/adding-the-sql-adapter-to-biztalk-server-administration-console.md).</span></span>  
  
3.  <span data-ttu-id="a223f-139">コンソール ツリーで  **BizTalk グループ**の順に展開**アプリケーション**、順にクリック**送信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="a223f-139">In the console tree, expand **BizTalk Group**, then expand **Applications**, and then click **Send Ports**.</span></span> <span data-ttu-id="a223f-140">右側のウィンドウでは、ポートを作成または既存のポートを選択できます。</span><span class="sxs-lookup"><span data-stu-id="a223f-140">In the right pane, you can choose to create a port or select an existing port.</span></span>  
  
4.  <span data-ttu-id="a223f-141">ポートのプロパティ ダイアログ ボックスから、**型**ドロップダウン リストは、前に追加する WCF-SQL アダプターを選択し、をクリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="a223f-141">In the port properties dialog box, from the **Type** drop-down list, select the WCF-SQL adapter you added earlier, and then click **Configure**.</span></span>  
  
5.  <span data-ttu-id="a223f-142">トランスポートのプロパティ ダイアログ ボックスをクリックして、**全般**タブです。</span><span class="sxs-lookup"><span data-stu-id="a223f-142">In the transport properties dialog box, click the **General** tab.</span></span>  
  
6.  <span data-ttu-id="a223f-143">**アクション**テキスト ボックスで、操作の SOAP アクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="a223f-143">In the **Action** text box, specify the SOAP action for the operation.</span></span> <span data-ttu-id="a223f-144">次の方法では、アクションを指定できます。</span><span class="sxs-lookup"><span data-stu-id="a223f-144">You can specify the action in the following ways:</span></span>  
  
    -   <span data-ttu-id="a223f-145">**シングル アクション形式を使用して、**です。</span><span class="sxs-lookup"><span data-stu-id="a223f-145">**By using the single action format**.</span></span> <span data-ttu-id="a223f-146">WCF SQL 送信ポートし、1 つの操作のメッセージが表示される場合は、この形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="a223f-146">Use this format if the WCF-SQL port sends and receive messages for a single operation.</span></span> <span data-ttu-id="a223f-147">例:</span><span class="sxs-lookup"><span data-stu-id="a223f-147">For example:</span></span>  
  
        ```  
        TableOp/Insert/dbo/Employee  
        ```  
  
    -   <span data-ttu-id="a223f-148">**アクション マッピング形式を使用して、**です。</span><span class="sxs-lookup"><span data-stu-id="a223f-148">**By using the action mapping format**.</span></span> <span data-ttu-id="a223f-149">1 つの WCF SQL ポートが 1 つ以上の操作のメッセージを送受信する場合は、この形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="a223f-149">Use this format if a single WCF-SQL port sends and receives messages for more than one operation.</span></span> <span data-ttu-id="a223f-150">たとえば、1 つの WCF SQL ポートは、(レコードを挿入する Employee テーブルの) Op1、Op2 (レコードを更新する Employee テーブル) のメッセージを送受信場合、SOAP アクションは次のように指定できます。</span><span class="sxs-lookup"><span data-stu-id="a223f-150">For example, if a single WCF-SQL port sends and receives messages for Op1 (to insert records in the Employee table) and Op2 (to update records in the Employee table), the SOAP action can be specified in the following manner:</span></span>  
  
        ```  
        <BtsActionMapping>  
          <Operation Name="Op1" Action="TableOp/Insert/dbo/Employee" />  
          <Operation Name="Op2" Action="TableOp/Update/dbo/Employee" />  
        </BtsActionMapping>  
        ```  
  
         <span data-ttu-id="a223f-151">アクション マッピングのアプローチでは、アクションのセットを指定して、そのため、同じポートを通過するさまざまなアクションの種類に属しているメッセージの有効化に関して柔軟性を提供します。</span><span class="sxs-lookup"><span data-stu-id="a223f-151">The action mapping approach provides greater flexibility in terms of specifying a set of actions, and hence enabling messages that belong to different action types to flow through the same port.</span></span>  
  
         <span data-ttu-id="a223f-152">SOAP アクションの形式は操作ごとに異なります。</span><span class="sxs-lookup"><span data-stu-id="a223f-152">The format for the SOAP action is different for each operation.</span></span> <span data-ttu-id="a223f-153">各操作の操作の形式の詳細については、次を参照してください。[メッセージおよびメッセージ スキーマ](messages-and-message-schemas-for-biztalk-adapter-for-sql-server.md)です。</span><span class="sxs-lookup"><span data-stu-id="a223f-153">For more information about the action format for each operation, see [Messages and message schemas](messages-and-message-schemas-for-biztalk-adapter-for-sql-server.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a223f-154">参照</span><span class="sxs-lookup"><span data-stu-id="a223f-154">See Also</span></span>  
[<span data-ttu-id="a223f-155">SQL アダプタを BizTalk アプリケーションを開発する構成要素</span><span class="sxs-lookup"><span data-stu-id="a223f-155">Building blocks to develop BizTalk applications with the SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/building-blocks-to-develop-biztalk-applications-with-the-sql-adapter.md)