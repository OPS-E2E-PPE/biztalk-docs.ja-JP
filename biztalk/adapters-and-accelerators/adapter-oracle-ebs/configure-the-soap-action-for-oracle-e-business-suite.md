---
title: BizTalk Server での Oracle E-business Suite の SOAP アクションの構成 |Microsoft Docs
description: Visual Studio での SOAP アクションの入力または BizTalk アダプター パック (BAP) で、Wcf-custom または Wcf-oracleebs アダプターを使用して、
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
ms.openlocfilehash: 29a829ced566e5a969cce5257a64da0999cce7be
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968108"
---
# <a name="configure-the-soap-action-for-oracle-e-business-suite"></a><span data-ttu-id="7131d-103">Oracle E-business Suite の SOAP アクションを構成します。</span><span class="sxs-lookup"><span data-stu-id="7131d-103">Configure the SOAP action for Oracle E-Business Suite</span></span>
<span data-ttu-id="7131d-104">WCF ベースを使用して Oracle E-business Suite の操作を実行する[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]、SOAP アクションを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7131d-104">To perform any operation on Oracle E-Business Suite using the WCF-based [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)], you must specify a SOAP action.</span></span> <span data-ttu-id="7131d-105">SOAP アクションは、どのようなアクションが実行されるアダプターに通信します。</span><span class="sxs-lookup"><span data-stu-id="7131d-105">The SOAP action communicates to the adapter what action should be performed.</span></span> <span data-ttu-id="7131d-106">いずれかから SOAP アクションを指定できます[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]またはから、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="7131d-106">You can specify the SOAP action either from [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] or from the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="7131d-107">ただし、両方の場所からの SOAP アクションを指定する場合、アクションから指定した[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]オーバーライドされます。</span><span class="sxs-lookup"><span data-stu-id="7131d-107">However, if you specify the SOAP action from both locations, the action you specified from [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] is overridden.</span></span>  
  
 <span data-ttu-id="7131d-108">SOAP アクションを指定する方法については、次を参照してください。 [WCF 送信アダプター用の SOAP アクションを指定する](../../core/specifying-soap-actions-for-wcf-send-adapters.md)します。</span><span class="sxs-lookup"><span data-stu-id="7131d-108">For more information about specifying SOAP action, see [Specifying SOAP Actions for WCF Send Adapters](../../core/specifying-soap-actions-for-wcf-send-adapters.md).</span></span>  
  
## <a name="enter-soap-action-from-visual-studio"></a><span data-ttu-id="7131d-109">Visual Studio からの SOAP アクションを入力します。</span><span class="sxs-lookup"><span data-stu-id="7131d-109">Enter SOAP Action from Visual Studio</span></span>  
 <span data-ttu-id="7131d-110">[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]を使用して、オーケストレーションの一部として SOAP アクションを指定する必要があります、**式**図形。</span><span class="sxs-lookup"><span data-stu-id="7131d-110">From [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], you must specify the SOAP action as part of the orchestration by using an **Expression** shape.</span></span>  
  
1.  <span data-ttu-id="7131d-111">BizTalk オーケストレーションで含める、**式**図形からドラッグすることで、 **BizTalk オーケストレーション**ツールボックス。</span><span class="sxs-lookup"><span data-stu-id="7131d-111">In the BizTalk orchestration, include an **Expression** shape by dragging it from the **BizTalk Orchestration** toolbox.</span></span>  
  
2.  <span data-ttu-id="7131d-112">ダブルクリックして、**式**図形を BizTalk 式エディタを開きます。</span><span class="sxs-lookup"><span data-stu-id="7131d-112">Double-click the **Expression** shape to open BizTalk Expression Editor.</span></span>  
  
3.  <span data-ttu-id="7131d-113">BizTalk 式エディタで、アクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="7131d-113">Specify the action in BizTalk Expression Editor.</span></span> <span data-ttu-id="7131d-114">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="7131d-114">For example:</span></span>  
  
    ```  
    OutboundMessage(WCF.Action)="InterfaceTables/Insert/SQLGL/GL/GL_ALLOC_HISTORY"  
    ```  
  
     <span data-ttu-id="7131d-115">詳細については、**式**図形と BizTalk 式エディターを参照してください[式を作成する方法](../../core/how-to-create-expressions.md)します。</span><span class="sxs-lookup"><span data-stu-id="7131d-115">For more information about the **Expression** shape and BizTalk Expression Editor, see [How to Create Expressions](../../core/how-to-create-expressions.md).</span></span>  
  
## <a name="enter-soap-action-from-biztalk-server-administration"></a><span data-ttu-id="7131d-116">BizTalk Server 管理からの SOAP アクションを入力します。</span><span class="sxs-lookup"><span data-stu-id="7131d-116">Enter SOAP Action from BizTalk Server Administration</span></span>  
 <span data-ttu-id="7131d-117">[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、Wcf-custom または Wcf-oracleebs ポートの構成の一部として SOAP アクションを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7131d-117">From the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console, you must specify the SOAP action as part of the WCF-Custom or WCF-OracleEBS port configuration.</span></span>  
  
#### <a name="enter-a-soap-action-for-the-wcf-custom-port"></a><span data-ttu-id="7131d-118">WCF カスタム ポートの SOAP アクションを入力します。</span><span class="sxs-lookup"><span data-stu-id="7131d-118">Enter a SOAP action for the WCF-Custom port</span></span>  
  
1. <span data-ttu-id="7131d-119">開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="7131d-119">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2. <span data-ttu-id="7131d-120">コンソール ツリーで、展開**BizTalk グループ**の順に展開**アプリケーション**、 をクリックし、**送信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="7131d-120">In the console tree, expand **BizTalk Group**, then expand **Applications**, and then click **Send Ports**.</span></span> <span data-ttu-id="7131d-121">右側のウィンドウでは、ポートを作成または既存のポートを選択できます。</span><span class="sxs-lookup"><span data-stu-id="7131d-121">In the right pane, you can choose to create a port or select an existing port.</span></span>  
  
3. <span data-ttu-id="7131d-122">ポートのプロパティ ダイアログ ボックスから、**型**ドロップダウン リストで、 **Wcf-custom**、 をクリックし、**構成**します。</span><span class="sxs-lookup"><span data-stu-id="7131d-122">In the port properties dialog box, from the **Type** drop-down list, select **WCF-Custom**, and then click **Configure**.</span></span>  
  
4. <span data-ttu-id="7131d-123">**Wcf-custom トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**全般**タブ。</span><span class="sxs-lookup"><span data-stu-id="7131d-123">In the **WCF-Custom Transport Properties** dialog box, click the **General** tab.</span></span>  
  
5. <span data-ttu-id="7131d-124">**アクション**テキスト ボックスで、操作の SOAP アクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="7131d-124">In the **Action** text box, specify the SOAP action for the operation.</span></span> <span data-ttu-id="7131d-125">次の方法では、アクションを指定できます。</span><span class="sxs-lookup"><span data-stu-id="7131d-125">You can specify the action in the following ways:</span></span>  
  
   -   <span data-ttu-id="7131d-126">**シングル アクション形式を使用して**します。</span><span class="sxs-lookup"><span data-stu-id="7131d-126">**By using the single action format**.</span></span> <span data-ttu-id="7131d-127">Wcf-custom 送信ポートし、1 つの操作のメッセージを受信する場合は、この形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="7131d-127">Use this format if the WCF-Custom port sends and receive messages for a single operation.</span></span> <span data-ttu-id="7131d-128">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="7131d-128">For example:</span></span>  
  
       ```  
       InterfaceTables/Insert/SQLGL/GL/GL_ALLOC_HISTORY  
       ```  
  
   -   <span data-ttu-id="7131d-129">**アクション マッピング形式を使用して**します。</span><span class="sxs-lookup"><span data-stu-id="7131d-129">**By using the action mapping format**.</span></span> <span data-ttu-id="7131d-130">1 つの WCF カスタム ポートが 1 つ以上の操作のメッセージを送受信する場合は、この形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="7131d-130">Use this format if a single WCF-Custom port sends and receives messages for more than one operation.</span></span> <span data-ttu-id="7131d-131">たとえば、送受信 (GL_ALLOC_HISTORY テーブルにレコードを挿入) するための Op1 と Op2 (GL_ALLOC_HISTORY テーブル内のレコードを更新) するメッセージを受信する 1 つの WCF カスタム ポートを SOAP アクションは次のように指定できます。</span><span class="sxs-lookup"><span data-stu-id="7131d-131">For example, if a single WCF-Custom port sends and receives messages for Op1 (to insert records in the GL_ALLOC_HISTORY table) and Op2 (to update records in the GL_ALLOC_HISTORY table), the SOAP action can be specified in the following manner:</span></span>  
  
       ```  
       <BtsActionMapping>  
         <Operation Name="Op1" Action="InterfaceTables/Insert/SQLGL/GL/GL_ALLOC_HISTORY" />  
         <Operation Name="Op2" Action="InterfaceTables/Update/SQLGL/GL/GL_ALLOC_HISTORY " />  
       </BtsActionMapping>  
       ```  
  
        <span data-ttu-id="7131d-132">アクション マッピングのアプローチは、アクションのセットを指定して、そのため、同じポートを経由するさまざまなアクションの種類に属しているメッセージの有効化の観点からの柔軟性を提供します。</span><span class="sxs-lookup"><span data-stu-id="7131d-132">The action mapping approach provides greater flexibility in terms of specifying a set of actions, and hence enabling messages that belong to different action types to flow through the same port.</span></span>  
  
        <span data-ttu-id="7131d-133">SOAP アクションの形式は操作ごとに異なります。</span><span class="sxs-lookup"><span data-stu-id="7131d-133">The format for the SOAP action is different for each operation.</span></span> <span data-ttu-id="7131d-134">各操作のアクションの形式の詳細については、次を参照してください。[メッセージと Oracle EBS アダプターのメッセージ スキーマ](messages-and-message-schemas-for-biztalk-adapter-for-oracle-e-business-suite.md)します。</span><span class="sxs-lookup"><span data-stu-id="7131d-134">For more information about the action format for each operation, see [Messages and Message Schemas for Oracle EBS adapter](messages-and-message-schemas-for-biztalk-adapter-for-oracle-e-business-suite.md).</span></span>
  
#### <a name="enter-a-soap-action-for-the-wcf-oracleebs-port"></a><span data-ttu-id="7131d-135">Wcf-oracleebs ポートの SOAP アクションを入力します。</span><span class="sxs-lookup"><span data-stu-id="7131d-135">Enter a SOAP action for the WCF-OracleEBS port</span></span>  
  
1. <span data-ttu-id="7131d-136">開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="7131d-136">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2. <span data-ttu-id="7131d-137">Wcf-oracleebs アダプターの追加、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="7131d-137">Add the WCF-OracleEBS adapter to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="7131d-138">手順については、次を参照してください。 [、Oracle E-business Suite アダプターを BizTalk Server 管理コンソールに追加する](../../adapters-and-accelerators/adapter-oracle-ebs/add-the-oracle-ebs-adapter-to-biztalk-server-administration-console.md)します。</span><span class="sxs-lookup"><span data-stu-id="7131d-138">For instructions, see [Adding the Oracle E-Business Suite Adapter to BizTalk Server Administration Console](../../adapters-and-accelerators/adapter-oracle-ebs/add-the-oracle-ebs-adapter-to-biztalk-server-administration-console.md).</span></span>  
  
3. <span data-ttu-id="7131d-139">コンソール ツリーで、展開**BizTalk グループ**の順に展開**アプリケーション**、 をクリックし、**送信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="7131d-139">In the console tree, expand **BizTalk Group**, then expand **Applications**, and then click **Send Ports**.</span></span> <span data-ttu-id="7131d-140">右側のウィンドウでは、ポートを作成または既存のポートを選択できます。</span><span class="sxs-lookup"><span data-stu-id="7131d-140">In the right pane, you can choose to create a port or select an existing port.</span></span>  
  
4. <span data-ttu-id="7131d-141">ポートのプロパティ ダイアログ ボックスから、**型**一覧から、以前では、追加し、をクリックし、選択、Wcf-oracleebs アダプター**構成**します。</span><span class="sxs-lookup"><span data-stu-id="7131d-141">In the port properties dialog box, from the **Type** drop-down list, select the WCF-OracleEBS adapter you add earlier, and then click **Configure**.</span></span>  
  
5. <span data-ttu-id="7131d-142">トランスポートのプロパティ ダイアログ ボックスでをクリックして、**全般**タブ。</span><span class="sxs-lookup"><span data-stu-id="7131d-142">In the transport properties dialog box, click the **General** tab.</span></span>  
  
6. <span data-ttu-id="7131d-143">**アクション**テキスト ボックスで、操作の SOAP アクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="7131d-143">In the **Action** text box, specify the SOAP action for the operation.</span></span> <span data-ttu-id="7131d-144">次の方法では、アクションを指定できます。</span><span class="sxs-lookup"><span data-stu-id="7131d-144">You can specify the action in the following ways:</span></span>  
  
   -   <span data-ttu-id="7131d-145">**シングル アクション形式を使用して**します。</span><span class="sxs-lookup"><span data-stu-id="7131d-145">**By using the single action format**.</span></span> <span data-ttu-id="7131d-146">Wcf-oracleebs、送信ポートし、1 つの操作のメッセージを受信する場合は、この形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="7131d-146">Use this format if the WCF-OracleEBS port sends and receive messages for a single operation.</span></span> <span data-ttu-id="7131d-147">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="7131d-147">For example:</span></span>  
  
       ```  
       InterfaceTables/Insert/SQLGL/GL/GL_ALLOC_HISTORY  
       ```  
  
   -   <span data-ttu-id="7131d-148">**アクション マッピング形式を使用して**します。</span><span class="sxs-lookup"><span data-stu-id="7131d-148">**By using the action mapping format**.</span></span> <span data-ttu-id="7131d-149">1 つの Wcf-oracleebs ポートが 1 つ以上の操作のメッセージを送受信する場合は、この形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="7131d-149">Use this format if a single WCF-OracleEBS port sends and receives messages for more than one operation.</span></span> <span data-ttu-id="7131d-150">たとえば、送受信 (GL_ALLOC_HISTORY テーブルにレコードを挿入) するための Op1 と Op2 (GL_ALLOC_HISTORY テーブル内のレコードを更新) するメッセージを受信する 1 つの Wcf-oracleebs ポート、SOAP アクションは次のように指定できます。</span><span class="sxs-lookup"><span data-stu-id="7131d-150">For example, if a single WCF-OracleEBS port sends and receives messages for Op1 (to insert records in the GL_ALLOC_HISTORY table) and Op2 (to update records in the GL_ALLOC_HISTORY table), the SOAP action can be specified in the following manner:</span></span>  
  
       ```  
       <BtsActionMapping>  
         <Operation Name="Op1" Action="InterfaceTables/Insert/SQLGL/GL/GL_ALLOC_HISTORY" />  
         <Operation Name="Op2" Action="InterfaceTables/Update/SQLGL/GL/GL_ALLOC_HISTORY " />  
       </BtsActionMapping>  
       ```  
  
        <span data-ttu-id="7131d-151">アクション マッピングのアプローチは、アクションのセットを指定して、そのため、同じポートを経由するさまざまなアクションの種類に属しているメッセージの有効化の観点からの柔軟性を提供します。</span><span class="sxs-lookup"><span data-stu-id="7131d-151">The action mapping approach provides greater flexibility in terms of specifying a set of actions, and hence enabling messages that belong to different action types to flow through the same port.</span></span>  
  
        <span data-ttu-id="7131d-152">SOAP アクションの形式は操作ごとに異なります。</span><span class="sxs-lookup"><span data-stu-id="7131d-152">The format for the SOAP action is different for each operation.</span></span> <span data-ttu-id="7131d-153">各操作のアクションの形式の詳細については、次を参照してください。[メッセージと Oracle EBS アダプターのメッセージ スキーマ](messages-and-message-schemas-for-biztalk-adapter-for-oracle-e-business-suite.md)します。</span><span class="sxs-lookup"><span data-stu-id="7131d-153">For more information about the action format for each operation, see [Messages and Message Schemas for Oracle EBS adapter](messages-and-message-schemas-for-biztalk-adapter-for-oracle-e-business-suite.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="7131d-154">参照</span><span class="sxs-lookup"><span data-stu-id="7131d-154">See Also</span></span>  
 [<span data-ttu-id="7131d-155">Oracle E-business Suite のアプリケーションを作成する構成要素</span><span class="sxs-lookup"><span data-stu-id="7131d-155">Building blocks to create Oracle E-Business Suite applications</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/building-blocks-to-create-oracle-e-business-suite-applications.md)