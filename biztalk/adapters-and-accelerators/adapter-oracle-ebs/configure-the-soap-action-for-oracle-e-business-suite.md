---
title: BizTalk Server で Oracle E-business Suite の SOAP アクションの構成 |Microsoft ドキュメント
description: Visual Studio で SOAP アクションを入力するか、Wcf-custom アダプターまたは Wcf-oracleebs アダプターの BizTalk アダプター パック (BAP) でを使用
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ca799d96-66e4-4d4e-a632-cb5505e999b4
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6c29cb5ce17f0a80e42ceae908639bed48e99e3a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22218282"
---
# <a name="configure-the-soap-action-for-oracle-e-business-suite"></a><span data-ttu-id="923a5-103">Oracle E-business Suite の SOAP アクションを構成します。</span><span class="sxs-lookup"><span data-stu-id="923a5-103">Configure the SOAP action for Oracle E-Business Suite</span></span>
<span data-ttu-id="923a5-104">WCF ベースを使用して Oracle E-business Suite で操作を実行する[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]、SOAP アクションを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="923a5-104">To perform any operation on Oracle E-Business Suite using the WCF-based [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)], you must specify a SOAP action.</span></span> <span data-ttu-id="923a5-105">SOAP アクションは、どのようなアクションを実行する必要があります、アダプターに通信します。</span><span class="sxs-lookup"><span data-stu-id="923a5-105">The SOAP action communicates to the adapter what action should be performed.</span></span> <span data-ttu-id="923a5-106">SOAP アクションのいずれかを指定する[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]またはから、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="923a5-106">You can specify the SOAP action either from [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] or from the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="923a5-107">ただし、両方の場所からの SOAP アクションを指定する場合、アクション指定したから[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]はオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="923a5-107">However, if you specify the SOAP action from both locations, the action you specified from [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] is overridden.</span></span>  
  
 <span data-ttu-id="923a5-108">SOAP アクションを指定する方法の詳細については、次を参照してください。 [WCF 送信アダプタ用の SOAP アクションの指定](../../core/specifying-soap-actions-for-wcf-send-adapters.md)です。</span><span class="sxs-lookup"><span data-stu-id="923a5-108">For more information about specifying SOAP action, see [Specifying SOAP Actions for WCF Send Adapters](../../core/specifying-soap-actions-for-wcf-send-adapters.md).</span></span>  
  
## <a name="enter-soap-action-from-visual-studio"></a><span data-ttu-id="923a5-109">Visual Studio からの SOAP アクションを入力します。</span><span class="sxs-lookup"><span data-stu-id="923a5-109">Enter SOAP Action from Visual Studio</span></span>  
 <span data-ttu-id="923a5-110">[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]、オーケストレーションの一部として使用して SOAP アクションを指定する必要があります、**式**図形です。</span><span class="sxs-lookup"><span data-stu-id="923a5-110">From [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], you must specify the SOAP action as part of the orchestration by using an **Expression** shape.</span></span>  
  
1.  <span data-ttu-id="923a5-111">BizTalk オーケストレーションが含まれる、**式**図形からドラッグすることで、 **BizTalk オーケストレーション**ツールボックスします。</span><span class="sxs-lookup"><span data-stu-id="923a5-111">In the BizTalk orchestration, include an **Expression** shape by dragging it from the **BizTalk Orchestration** toolbox.</span></span>  
  
2.  <span data-ttu-id="923a5-112">ダブルクリックして、**式**図形を BizTalk 式エディタを開きます。</span><span class="sxs-lookup"><span data-stu-id="923a5-112">Double-click the **Expression** shape to open BizTalk Expression Editor.</span></span>  
  
3.  <span data-ttu-id="923a5-113">BizTalk 式エディタで、アクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="923a5-113">Specify the action in BizTalk Expression Editor.</span></span> <span data-ttu-id="923a5-114">例:</span><span class="sxs-lookup"><span data-stu-id="923a5-114">For example:</span></span>  
  
    ```  
    OutboundMessage(WCF.Action)="InterfaceTables/Insert/SQLGL/GL/GL_ALLOC_HISTORY"  
    ```  
  
     <span data-ttu-id="923a5-115">詳細については、**式**図形および BizTalk 式エディターを参照してください[式を作成する方法](../../core/how-to-create-expressions.md)です。</span><span class="sxs-lookup"><span data-stu-id="923a5-115">For more information about the **Expression** shape and BizTalk Expression Editor, see [How to Create Expressions](../../core/how-to-create-expressions.md).</span></span>  
  
## <a name="enter-soap-action-from-biztalk-server-administration"></a><span data-ttu-id="923a5-116">BizTalk Server 管理コンソールからの SOAP アクションを入力します。</span><span class="sxs-lookup"><span data-stu-id="923a5-116">Enter SOAP Action from BizTalk Server Administration</span></span>  
 <span data-ttu-id="923a5-117">[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、Wcf-custom または Wcf-oracleebs ポートの構成の一部として SOAP アクションを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="923a5-117">From the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console, you must specify the SOAP action as part of the WCF-Custom or WCF-OracleEBS port configuration.</span></span>  
  
#### <a name="enter-a-soap-action-for-the-wcf-custom-port"></a><span data-ttu-id="923a5-118">WCF カスタム ポートの SOAP アクションを入力します。</span><span class="sxs-lookup"><span data-stu-id="923a5-118">Enter a SOAP action for the WCF-Custom port</span></span>  
  
1.  <span data-ttu-id="923a5-119">開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="923a5-119">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="923a5-120">コンソール ツリーで  **BizTalk グループ**の順に展開**アプリケーション**、順にクリック**送信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="923a5-120">In the console tree, expand **BizTalk Group**, then expand **Applications**, and then click **Send Ports**.</span></span> <span data-ttu-id="923a5-121">右側のウィンドウでは、ポートを作成または既存のポートを選択できます。</span><span class="sxs-lookup"><span data-stu-id="923a5-121">In the right pane, you can choose to create a port or select an existing port.</span></span>  
  
3.  <span data-ttu-id="923a5-122">ポートのプロパティ ダイアログ ボックスから、**型**ドロップダウン リストで、 **Wcf-custom**、クリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="923a5-122">In the port properties dialog box, from the **Type** drop-down list, select **WCF-Custom**, and then click **Configure**.</span></span>  
  
4.  <span data-ttu-id="923a5-123">**Wcf-custom トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**全般**タブです。</span><span class="sxs-lookup"><span data-stu-id="923a5-123">In the **WCF-Custom Transport Properties** dialog box, click the **General** tab.</span></span>  
  
5.  <span data-ttu-id="923a5-124">**アクション**テキスト ボックスで、操作の SOAP アクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="923a5-124">In the **Action** text box, specify the SOAP action for the operation.</span></span> <span data-ttu-id="923a5-125">次の方法では、アクションを指定できます。</span><span class="sxs-lookup"><span data-stu-id="923a5-125">You can specify the action in the following ways:</span></span>  
  
    -   <span data-ttu-id="923a5-126">**シングル アクション形式を使用して、** です。</span><span class="sxs-lookup"><span data-stu-id="923a5-126">**By using the single action format**.</span></span> <span data-ttu-id="923a5-127">Wcf-custom 送信ポートし、1 つの操作のメッセージを受信する場合は、この形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="923a5-127">Use this format if the WCF-Custom port sends and receive messages for a single operation.</span></span> <span data-ttu-id="923a5-128">例:</span><span class="sxs-lookup"><span data-stu-id="923a5-128">For example:</span></span>  
  
        ```  
        InterfaceTables/Insert/SQLGL/GL/GL_ALLOC_HISTORY  
        ```  
  
    -   <span data-ttu-id="923a5-129">**アクション マッピング形式を使用して、** です。</span><span class="sxs-lookup"><span data-stu-id="923a5-129">**By using the action mapping format**.</span></span> <span data-ttu-id="923a5-130">1 つの WCF カスタム ポートを送信し、1 つ以上の操作のメッセージを受け取る場合は、この形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="923a5-130">Use this format if a single WCF-Custom port sends and receives messages for more than one operation.</span></span> <span data-ttu-id="923a5-131">たとえば、1 つの WCF カスタム ポートを送信および (レコードを挿入する GL_ALLOC_HISTORY テーブル) Op1、Op2 (レコードを更新する GL_ALLOC_HISTORY テーブル) のメッセージを受け取る場合、SOAP アクションは、次のように指定できます。</span><span class="sxs-lookup"><span data-stu-id="923a5-131">For example, if a single WCF-Custom port sends and receives messages for Op1 (to insert records in the GL_ALLOC_HISTORY table) and Op2 (to update records in the GL_ALLOC_HISTORY table), the SOAP action can be specified in the following manner:</span></span>  
  
        ```  
        <BtsActionMapping>  
          <Operation Name="Op1" Action="InterfaceTables/Insert/SQLGL/GL/GL_ALLOC_HISTORY" />  
          <Operation Name="Op2" Action="InterfaceTables/Update/SQLGL/GL/GL_ALLOC_HISTORY " />  
        </BtsActionMapping>  
        ```  
  
         <span data-ttu-id="923a5-132">アクション マッピングのアプローチでは、アクションのセットを指定して、そのため、同じポートを通過するさまざまなアクションの種類に属しているメッセージの有効化に関して柔軟性を提供します。</span><span class="sxs-lookup"><span data-stu-id="923a5-132">The action mapping approach provides greater flexibility in terms of specifying a set of actions, and hence enabling messages that belong to different action types to flow through the same port.</span></span>  
  
         <span data-ttu-id="923a5-133">SOAP アクションの形式は操作ごとに異なります。</span><span class="sxs-lookup"><span data-stu-id="923a5-133">The format for the SOAP action is different for each operation.</span></span> <span data-ttu-id="923a5-134">各操作の操作の形式の詳細については、次を参照してください。[メッセージと Oracle EBS アダプターのメッセージ スキーマを](messages-and-message-schemas-for-biztalk-adapter-for-oracle-e-business-suite.md)です。</span><span class="sxs-lookup"><span data-stu-id="923a5-134">For more information about the action format for each operation, see [Messages and Message Schemas for Oracle EBS adapter](messages-and-message-schemas-for-biztalk-adapter-for-oracle-e-business-suite.md).</span></span>
  
#### <a name="enter-a-soap-action-for-the-wcf-oracleebs-port"></a><span data-ttu-id="923a5-135">Wcf-oracleebs ポートの SOAP アクションを入力します。</span><span class="sxs-lookup"><span data-stu-id="923a5-135">Enter a SOAP action for the WCF-OracleEBS port</span></span>  
  
1.  <span data-ttu-id="923a5-136">開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="923a5-136">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="923a5-137">Wcf-oracleebs アダプターの追加、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="923a5-137">Add the WCF-OracleEBS adapter to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="923a5-138">手順については、次を参照してください。 [、Oracle E-business Suite アダプターを BizTalk Server 管理コンソールに追加する](../../adapters-and-accelerators/adapter-oracle-ebs/add-the-oracle-ebs-adapter-to-biztalk-server-administration-console.md)です。</span><span class="sxs-lookup"><span data-stu-id="923a5-138">For instructions, see [Adding the Oracle E-Business Suite Adapter to BizTalk Server Administration Console](../../adapters-and-accelerators/adapter-oracle-ebs/add-the-oracle-ebs-adapter-to-biztalk-server-administration-console.md).</span></span>  
  
3.  <span data-ttu-id="923a5-139">コンソール ツリーで  **BizTalk グループ**の順に展開**アプリケーション**、順にクリック**送信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="923a5-139">In the console tree, expand **BizTalk Group**, then expand **Applications**, and then click **Send Ports**.</span></span> <span data-ttu-id="923a5-140">右側のウィンドウでは、ポートを作成または既存のポートを選択できます。</span><span class="sxs-lookup"><span data-stu-id="923a5-140">In the right pane, you can choose to create a port or select an existing port.</span></span>  
  
4.  <span data-ttu-id="923a5-141">ポートのプロパティ ダイアログ ボックスから、**型**一覧から、以前に追加しをクリックし、選択、Wcf-oracleebs アダプター**構成**です。</span><span class="sxs-lookup"><span data-stu-id="923a5-141">In the port properties dialog box, from the **Type** drop-down list, select the WCF-OracleEBS adapter you add earlier, and then click **Configure**.</span></span>  
  
5.  <span data-ttu-id="923a5-142">トランスポートのプロパティ ダイアログ ボックスをクリックして、**全般**タブです。</span><span class="sxs-lookup"><span data-stu-id="923a5-142">In the transport properties dialog box, click the **General** tab.</span></span>  
  
6.  <span data-ttu-id="923a5-143">**アクション**テキスト ボックスで、操作の SOAP アクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="923a5-143">In the **Action** text box, specify the SOAP action for the operation.</span></span> <span data-ttu-id="923a5-144">次の方法では、アクションを指定できます。</span><span class="sxs-lookup"><span data-stu-id="923a5-144">You can specify the action in the following ways:</span></span>  
  
    -   <span data-ttu-id="923a5-145">**シングル アクション形式を使用して、** です。</span><span class="sxs-lookup"><span data-stu-id="923a5-145">**By using the single action format**.</span></span> <span data-ttu-id="923a5-146">Wcf-oracleebs、送信ポートし、1 つの操作のメッセージを受信する場合は、この形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="923a5-146">Use this format if the WCF-OracleEBS port sends and receive messages for a single operation.</span></span> <span data-ttu-id="923a5-147">例:</span><span class="sxs-lookup"><span data-stu-id="923a5-147">For example:</span></span>  
  
        ```  
        InterfaceTables/Insert/SQLGL/GL/GL_ALLOC_HISTORY  
        ```  
  
    -   <span data-ttu-id="923a5-148">**アクション マッピング形式を使用して、** です。</span><span class="sxs-lookup"><span data-stu-id="923a5-148">**By using the action mapping format**.</span></span> <span data-ttu-id="923a5-149">1 つの Wcf-oracleebs ポートを送信および複数の操作のメッセージを受け取る場合は、この形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="923a5-149">Use this format if a single WCF-OracleEBS port sends and receives messages for more than one operation.</span></span> <span data-ttu-id="923a5-150">たとえば、1 つの Wcf-oracleebs ポートは、(レコードを挿入する GL_ALLOC_HISTORY テーブル) Op1、Op2 (レコードを更新する GL_ALLOC_HISTORY テーブル) のメッセージを送受信場合、SOAP アクションは次のように指定できます。</span><span class="sxs-lookup"><span data-stu-id="923a5-150">For example, if a single WCF-OracleEBS port sends and receives messages for Op1 (to insert records in the GL_ALLOC_HISTORY table) and Op2 (to update records in the GL_ALLOC_HISTORY table), the SOAP action can be specified in the following manner:</span></span>  
  
        ```  
        <BtsActionMapping>  
          <Operation Name="Op1" Action="InterfaceTables/Insert/SQLGL/GL/GL_ALLOC_HISTORY" />  
          <Operation Name="Op2" Action="InterfaceTables/Update/SQLGL/GL/GL_ALLOC_HISTORY " />  
        </BtsActionMapping>  
        ```  
  
         <span data-ttu-id="923a5-151">アクション マッピングのアプローチでは、アクションのセットを指定して、そのため、同じポートを通過するさまざまなアクションの種類に属しているメッセージの有効化に関して柔軟性を提供します。</span><span class="sxs-lookup"><span data-stu-id="923a5-151">The action mapping approach provides greater flexibility in terms of specifying a set of actions, and hence enabling messages that belong to different action types to flow through the same port.</span></span>  
  
         <span data-ttu-id="923a5-152">SOAP アクションの形式は操作ごとに異なります。</span><span class="sxs-lookup"><span data-stu-id="923a5-152">The format for the SOAP action is different for each operation.</span></span> <span data-ttu-id="923a5-153">各操作の操作の形式の詳細については、次を参照してください。[メッセージと Oracle EBS アダプターのメッセージ スキーマを](messages-and-message-schemas-for-biztalk-adapter-for-oracle-e-business-suite.md)です。</span><span class="sxs-lookup"><span data-stu-id="923a5-153">For more information about the action format for each operation, see [Messages and Message Schemas for Oracle EBS adapter](messages-and-message-schemas-for-biztalk-adapter-for-oracle-e-business-suite.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="923a5-154">参照</span><span class="sxs-lookup"><span data-stu-id="923a5-154">See Also</span></span>  
 [<span data-ttu-id="923a5-155">Oracle E-business Suite アプリケーションを作成する構成要素</span><span class="sxs-lookup"><span data-stu-id="923a5-155">Building blocks to create Oracle E-Business Suite applications</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/building-blocks-to-create-oracle-e-business-suite-applications.md)