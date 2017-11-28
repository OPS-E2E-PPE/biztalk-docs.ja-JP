---
title: "チュートリアル: モジュール 3 - オーケストレーションからの SharePoint プロパティへのアクセス |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- orchestrations, Windows SharePoint Services adapters
- tutorials, Windows SharePoint Services adapters
- Windows SharePoint Services adapters, orchestrations
- Windows SharePoint Services adapter tutorials, accessing SharePoint properties
ms.assetid: 310c4002-3416-44c6-b409-1d5467063e28
caps.latest.revision: "45"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a44fd7e30bf511ee77cc1f3e79f6ba63908259ff
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="walkthrough-module-3---accessing-sharepoint-properties-from-an-orchestration"></a><span data-ttu-id="6d1f6-102">チュートリアル: モジュール 3 - オーケストレーションからの SharePoint プロパティへのアクセス</span><span class="sxs-lookup"><span data-stu-id="6d1f6-102">Walkthrough: Module 3 - Accessing SharePoint Properties from an Orchestration</span></span>
<span data-ttu-id="6d1f6-103">このチュートリアルでは、継続の[チュートリアル: モジュール 2 - Windows SharePoint Services アダプターと Office の統合](../core/walkthrough-module-2--integrate-office-with-the-sharepoint-adapter-in-biztalk.md)し、受信メッセージでの Windows SharePoint Services コンテキスト プロパティにアクセスする方法を示します実行時間とし、動的ポート、オーケストレーションでのプロパティに基づいてメッセージの送信先を判断します。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-103">This walkthrough is a continuation of [Walkthrough: Module 2 - Integrating Office with the Windows SharePoint Services Adapter](../core/walkthrough-module-2--integrate-office-with-the-sharepoint-adapter-in-biztalk.md) and shows you how to access the Windows SharePoint Services context properties of an incoming message at run time and then determine the destination of that message based on a property using dynamic ports in an orchestration.</span></span> <span data-ttu-id="6d1f6-104">概要については、Windows SharePoint Services アダプターを参照してください。 [Windows SharePoint Services アダプターは何ですか。](../core/what-is-the-windows-sharepoint-services-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-104">For an introduction to the Windows SharePoint Services adapter see [What Is the Windows SharePoint Services Adapter?](../core/what-is-the-windows-sharepoint-services-adapter.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="6d1f6-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="6d1f6-105">Prerequisites</span></span>  
 <span data-ttu-id="6d1f6-106">このトピックの手順を実行するための前提条件は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-106">The following are prerequisites for performing the procedures in this topic:</span></span>  
  
-   <span data-ttu-id="6d1f6-107">[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] または [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] で完全インストール済みの [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] が稼働している形のシングル サーバー展開が必要です。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-107">You must have a single server deployment with a complete installation of [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] running on [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] or [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)].</span></span>  
  
-   <span data-ttu-id="6d1f6-108">次のチュートリアルを完了する必要があります:[チュートリアル: モジュール 1 - Windows SharePoint Services アダプターでメッセージを送受信する](../core/walkthrough-module-1--send-and-receive-messages-with-the-sharepoint-adapter.md)と[チュートリアル: モジュール 2 - Windows と Office の統合SharePoint Services アダプター](../core/walkthrough-module-2--integrate-office-with-the-sharepoint-adapter-in-biztalk.md)</span><span class="sxs-lookup"><span data-stu-id="6d1f6-108">You must complete the following walkthroughs: [Walkthrough: Module 1 - Sending and Receiving Messages with the Windows SharePoint Services Adapter](../core/walkthrough-module-1--send-and-receive-messages-with-the-sharepoint-adapter.md) and [Walkthrough: Module 2 - Integrating Office with the Windows SharePoint Services Adapter](../core/walkthrough-module-2--integrate-office-with-the-sharepoint-adapter-in-biztalk.md)</span></span>  
  
 <span data-ttu-id="6d1f6-109">複数のサーバーの展開で Windows SharePoint Services アダプターを使用する方法については、次を参照してください。[の設定と Windows SharePoint Services アダプターを展開する](../core/setting-up-and-deploying-the-windows-sharepoint-services-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-109">For information about using the Windows SharePoint Services Adapter in a multi server deployment, see [Setting Up and Deploying the Windows SharePoint Services Adapter](../core/setting-up-and-deploying-the-windows-sharepoint-services-adapter.md).</span></span>  
  
## <a name="modify-the-biztalk-project"></a><span data-ttu-id="6d1f6-110">BizTalk プロジェクトの変更</span><span class="sxs-lookup"><span data-stu-id="6d1f6-110">Modify the BizTalk project</span></span>  
 <span data-ttu-id="6d1f6-111">PurchaseOrder スキーマを変更するこの手順で[チュートリアル: モジュール 2 - Windows SharePoint Services アダプターと Office の統合](../core/walkthrough-module-2--integrate-office-with-the-sharepoint-adapter-in-biztalk.md)です。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-111">In this procedure you modify the PurchaseOrder schema from [Walkthrough: Module 2 - Integrating Office with the Windows SharePoint Services Adapter](../core/walkthrough-module-2--integrate-office-with-the-sharepoint-adapter-in-biztalk.md).</span></span> <span data-ttu-id="6d1f6-112">この手順は、スキーマ プロパティを昇格させ、BizTalk オーケストレーションで容易にアクセスできるようにする方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-112">This procedure illustrates how to promote a schema property for easy access in a BizTalk orchestration.</span></span>  
  
#### <a name="modify-the-purchaseorderxsd-schema"></a><span data-ttu-id="6d1f6-113">PurchaseOrder.xsd スキーマの変更</span><span class="sxs-lookup"><span data-stu-id="6d1f6-113">Modify the PurchaseOrder.xsd schema</span></span>  
  
1.  <span data-ttu-id="6d1f6-114">開始**Microsoft Visual Studio**です。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-114">Start **Microsoft Visual Studio**.</span></span>  
  
2.  <span data-ttu-id="6d1f6-115">をクリックして**ファイル**、 をクリックして**開く**、順にクリック**プロジェクト/ソリューション**です。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-115">Click **File**, click **Open**, and then click **Project/Solution**.</span></span>  
  
3.  <span data-ttu-id="6d1f6-116">参照、`OrderProcess.sln`ファイルを開き、をクリックして**開く**です。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-116">Browse to the `OrderProcess.sln` file, and then click **Open**.</span></span>  
  
4.  <span data-ttu-id="6d1f6-117">**ソリューション エクスプ ローラー**を右クリックし、`OrderProcessSchema.xsd`ファイルを開き、をクリックして**開く**です。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-117">In **Solution Explorer**, right-click the `OrderProcessSchema.xsd` file, and then click **Open**.</span></span>  
  
5.  <span data-ttu-id="6d1f6-118">**BizTalk エディター**、展開`PurchaseOrder`です。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-118">In **BizTalk Editor**, expand `PurchaseOrder`.</span></span>  
  
6.  <span data-ttu-id="6d1f6-119">右クリック`Amount`をクリックして**昇格**、順にクリック**クイック昇格**です。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-119">Right-click `Amount`, click **Promote**, and then click **Quick Promotion**.</span></span>  
  
7.  <span data-ttu-id="6d1f6-120">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-120">Click **OK**.</span></span>  
  
    > [!NOTE]
    >  [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]<span data-ttu-id="6d1f6-121"> で、これに対応するプロパティ スキーマが現在のプロジェクト内に作成されます。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-121"> creates a property schema for this in the current project.</span></span>  
  
8.  <span data-ttu-id="6d1f6-122">`PurchaseOrder.xsd` を保存します。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-122">Save `PurchaseOrder.xsd`.</span></span>  
  
## <a name="create-an-orchestration"></a><span data-ttu-id="6d1f6-123">オーケストレーションの作成</span><span class="sxs-lookup"><span data-stu-id="6d1f6-123">Create an orchestration</span></span>  
 <span data-ttu-id="6d1f6-124">ここでは、新しい BizTalk オーケストレーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-124">In this procedure you create a new BizTalk orchestration.</span></span> <span data-ttu-id="6d1f6-125">この手順により、Windows SharePoint Services アダプターが受信したメッセージを処理するためのオーケストレーションが作成されます。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-125">This procedure creates the orchestration that is used to process a message received by the Windows Sharepoint Services adapter.</span></span>  
  
#### <a name="add-a-biztalk-orchestration"></a><span data-ttu-id="6d1f6-126">BizTalk オーケストレーションの追加</span><span class="sxs-lookup"><span data-stu-id="6d1f6-126">Add a BizTalk orchestration</span></span>  
  
1.  <span data-ttu-id="6d1f6-127">**ソリューション エクスプ ローラー**を右クリックし、`OrderProcess`プロジェクトで、をクリックして**追加**、クリックして**新しい項目の**します。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-127">In **Solution Explorer**, right-click the `OrderProcess` project, click **Add**, and then click **New Item**.</span></span>  
  
2.  <span data-ttu-id="6d1f6-128">**カテゴリ****オーケストレーション ファイル**です。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-128">Under **Categories**, select **Orchestration Files**.</span></span>  
  
3.  <span data-ttu-id="6d1f6-129">**テンプレート** **BizTalk オーケストレーション**です。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-129">Under **Templates**, select **BizTalk Orchestration**.</span></span>  
  
4.  <span data-ttu-id="6d1f6-130">型`MyCompanyOrderProcessing`で、**名前**フィールドをクリックして**追加**です。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-130">Type `MyCompanyOrderProcessing` in the **Name** field, and then click **Add**.</span></span>  
  
## <a name="create-receive-information"></a><span data-ttu-id="6d1f6-131">受信情報の作成</span><span class="sxs-lookup"><span data-stu-id="6d1f6-131">Create receive information</span></span>  
 <span data-ttu-id="6d1f6-132">ここでは、オーケストレーションの新しいメッセージ、受信ポート、受信図形を作成します。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-132">In this procedure you create a new message, receive port, and receive shape for the orchestration.</span></span> <span data-ttu-id="6d1f6-133">この手順は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] からメッセージを受信するオーケストレーションの構成方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-133">This procedure illustrates how to configure an orchestration to receive a message from [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
#### <a name="create-a-new-message"></a><span data-ttu-id="6d1f6-134">新しいメッセージの作成</span><span class="sxs-lookup"><span data-stu-id="6d1f6-134">Create a new message</span></span>  
  
1.  <span data-ttu-id="6d1f6-135">**オーケストレーション ビュー**を右クリックして**メッセージ**、クリックして**新しいメッセージ**です。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-135">In **Orchestration View**, right-click **Messages**, and then click **New Message**.</span></span> <span data-ttu-id="6d1f6-136">`Message_1` という名前の新しいメッセージが生成されます。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-136">This will generate a new message with the name `Message_1`.</span></span>  
  
2.  <span data-ttu-id="6d1f6-137">右クリック`Message_1`をクリックして**の名前を変更**、し、入力`Message_PO`です。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-137">Right-click `Message_1`, click **Rename**, and then type `Message_PO`.</span></span>  
  
3.  <span data-ttu-id="6d1f6-138">右クリック`Message_PO`、クリックして**プロパティ ウィンドウ**します。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-138">Right-click `Message_PO`, and then click **Properties Window**.</span></span>  
  
4.  <span data-ttu-id="6d1f6-139">**メッセージの種類**プロパティ、展開**スキーマ**、し、`OrderProcess.OrderProcessSchema`スキーマです。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-139">In the **Message Type** property, expand **Schemas**, and then select `OrderProcess.OrderProcessSchema` schema.</span></span>  
  
#### <a name="add-a-receive-port-to-the-orchestration"></a><span data-ttu-id="6d1f6-140">オーケストレーションへの受信ポートの追加</span><span class="sxs-lookup"><span data-stu-id="6d1f6-140">Add a receive port to the orchestration</span></span>  
  
1.  <span data-ttu-id="6d1f6-141">**BizTalk オーケストレーション**、ツールボックスのドラッグ、**ポート**図形をポート画面にします。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-141">Under **BizTalk Orchestrations** in the Toolbox, drag a **Port** shape to the Port Surface.</span></span> <span data-ttu-id="6d1f6-142">ポート構成ウィザードが起動します。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-142">The Port Configuration Wizard will start.</span></span>  
  
2.  <span data-ttu-id="6d1f6-143">[ようこそ] 画面で、をクリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-143">On the Welcome screen, click **Next**.</span></span>  
  
3.  <span data-ttu-id="6d1f6-144">型`ReceivePurchaseOrder`で、**名前**フィールド、およびをクリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-144">Type `ReceivePurchaseOrder` in the **Name** field, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="6d1f6-145">選択**新しいポートの種類を作成する**です。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-145">Select **Create a new Port Type**.</span></span>  
  
5.  <span data-ttu-id="6d1f6-146">型`PurchaseOrderPT`で、**ポートの種類名**フィールドをクリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-146">Type `PurchaseOrderPT` in the **Port Type Name** field, and then click **Next**.</span></span>  
  
6.  <span data-ttu-id="6d1f6-147">**画面のポートのバインド**で、既定値のままにし、クリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-147">On the **Port Binding screen**, leave the default values, and then click **Next**.</span></span>  
  
7.  <span data-ttu-id="6d1f6-148">**[完了]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-148">Click **Finish**.</span></span>  
  
8.  <span data-ttu-id="6d1f6-149">**オーケストレーション****ポートの種類**、展開、`PurchaseOrderPT`ポートの種類。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-149">In **Orchestration View**, under **Port Types**, expand the `PurchaseOrderPT` port type.</span></span>  
  
9. <span data-ttu-id="6d1f6-150">右クリック`Operation_1`をクリックして**の名前を変更**、し、入力`PurchaseOrderOperation`です。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-150">Right-click `Operation_1`, click **Rename**, and then type `PurchaseOrderOperation`.</span></span>  
  
#### <a name="add-a-receive-shape-to-the-orchestration"></a><span data-ttu-id="6d1f6-151">オーケストレーションへの受信図形の追加</span><span class="sxs-lookup"><span data-stu-id="6d1f6-151">Add a Receive shape to the orchestration</span></span>  
  
1.  <span data-ttu-id="6d1f6-152">**BizTalk オーケストレーション**、ツールボックスのドラッグ、**受信**オーケストレーションへの図形です。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-152">Under **BizTalk Orchestrations** in the Toolbox, drag a **Receive** shape to the Orchestration.</span></span>  
  
2.  <span data-ttu-id="6d1f6-153">受信図形を右クリックし、をクリックして**プロパティ ウィンドウ**します。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-153">Right-click the Receive shape, and then click **Properties Window**.</span></span>  
  
3.  <span data-ttu-id="6d1f6-154">設定、 **Activate**プロパティを`True`です。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-154">Set the **Activate** property to `True`.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6d1f6-155">"アクティブ化" プロパティを false に設定すると、"エラー X2214: 自己関連付けを行わないポート上での非アクティベーション受信に対して、既に初期化されている関連付けセットを少なくとも 1 つ指定する必要があります" というエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-155">If the activate property is set to false, you will get the following error: "error X2214: you must specify at least one already-initialized correlation set for a non-activation receive that is on a non-selfcorrelating port"</span></span>  
  
4.  <span data-ttu-id="6d1f6-156">型`Receive_PO`で、**名前**フィールドです。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-156">Type `Receive_PO` in the **Name** field.</span></span>  
  
5.  <span data-ttu-id="6d1f6-157">**プロパティ] ウィンドウ**[`Message_PO`メッセージ プロパティのです。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-157">In the **Properties Window**, select `Message_PO` for the Message property.</span></span>  
  
6.  <span data-ttu-id="6d1f6-158">選択`ReceivePurchaseOrder.PurchaseOrderOperation.Request`の**操作**プロパティです。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-158">Select `ReceivePurchaseOrder.PurchaseOrderOperation.Request` for the **Operation** property.</span></span> <span data-ttu-id="6d1f6-159">オーケストレーション デザイナの受信図形にポートが連結されます。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-159">This will tie the port to the Receive shape in the Orchestration Designer.</span></span>  
  
## <a name="create-send-information"></a><span data-ttu-id="6d1f6-160">送信情報の作成</span><span class="sxs-lookup"><span data-stu-id="6d1f6-160">Create send information</span></span>  
 <span data-ttu-id="6d1f6-161">ここでは、オーケストレーションに新しいメッセージ、送信ポート、判断構造を作成します。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-161">In this procedure you create a new message, send ports, and decision structure to the orchestration.</span></span> <span data-ttu-id="6d1f6-162">この手順は、判断ロジックを使ったオーケストレーションの構成方法、および、メッセージを送信ポートに送るようにオーケストレーションを構成する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-162">This procedure illustrates how to configure an orchestration with decision logic and how to configure an orchestration to send a message to a send port.</span></span>  
  
#### <a name="create-a-new-message"></a><span data-ttu-id="6d1f6-163">新しいメッセージの作成</span><span class="sxs-lookup"><span data-stu-id="6d1f6-163">Create a new message</span></span>  
  
1.  <span data-ttu-id="6d1f6-164">**オーケストレーション ビュー**を右クリックして**メッセージ**、クリックして**新しいメッセージ**です。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-164">In **Orchestration View**, right-click **Messages**, and then click **New Message**.</span></span> <span data-ttu-id="6d1f6-165">`Message_1` という名前の新しいメッセージが生成されます。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-165">This will generate a new message with the name `Message_1`.</span></span>  
  
2.  <span data-ttu-id="6d1f6-166">右クリック`Message_1`をクリックして**の名前を変更**、し、入力`Message_Task`です。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-166">Right-click `Message_1`, click **Rename**, and then type `Message_Task`.</span></span>  
  
3.  <span data-ttu-id="6d1f6-167">右クリック`Message_Task`、クリックして**プロパティ ウィンドウ**します。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-167">Right-click `Message_Task`, and then click **Properties Window**.</span></span>  
  
4.  <span data-ttu-id="6d1f6-168">**メッセージの種類**プロパティ、展開**スキーマ**、し、`OrderProcess.OrderProcessSchema`スキーマです。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-168">In the **Message Type** property, expand **Schemas**, and then select `OrderProcess.OrderProcessSchema` schema.</span></span>  
  
#### <a name="add-a-send-port-to-the-orchestration"></a><span data-ttu-id="6d1f6-169">オーケストレーションへの送信ポートの追加</span><span class="sxs-lookup"><span data-stu-id="6d1f6-169">Add a send port to the orchestration</span></span>  
  
1.  <span data-ttu-id="6d1f6-170">**BizTalk オーケストレーション**、ツールボックスのドラッグ、**ポート**図形をポート画面にします。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-170">Under **BizTalk Orchestrations** in the Toolbox, drag a **Port** shape to the Port Surface.</span></span> <span data-ttu-id="6d1f6-171">ポート構成ウィザードが起動します。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-171">The Port Configuration Wizard will start.</span></span>  
  
2.  <span data-ttu-id="6d1f6-172">[ようこそ] 画面で、をクリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-172">On the Welcome screen, click **Next**.</span></span>  
  
3.  <span data-ttu-id="6d1f6-173">型`SendPurchaseOrder`で、**名前**フィールド、およびをクリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-173">Type `SendPurchaseOrder` in the **Name** field, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="6d1f6-174">選択**既存のポートの種類を使用して**です。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-174">Select **Use an existing Port Type**.</span></span>  
  
5.  <span data-ttu-id="6d1f6-175">**使用可能なポートの種類** `OrderProcess.PurchaseOrderPT`、順にクリック**次へ**です。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-175">Under **Available Port Types**, select `OrderProcess.PurchaseOrderPT`, and then click **Next**.</span></span>  
  
6.  <span data-ttu-id="6d1f6-176">**画面のポートのバインド****ポートの通信方向** `I'll always be sending messages on this port`、順にクリック**次へ**です。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-176">On the **Port Binding screen**, under **Port direction of communication**, select `I'll always be sending messages on this port`, and then click **Next**.</span></span>  
  
7.  <span data-ttu-id="6d1f6-177">**[完了]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-177">Click **Finish**.</span></span>  
  
#### <a name="add-a-send-shape-to-the-orchestration"></a><span data-ttu-id="6d1f6-178">オーケストレーションへの送信図形の追加</span><span class="sxs-lookup"><span data-stu-id="6d1f6-178">Add a Send shape to the orchestration</span></span>  
  
1.  <span data-ttu-id="6d1f6-179">**BizTalk オーケストレーション**、ツールボックスのドラッグ、**送信**図形をオーケストレーション デザイナにします。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-179">Under **BizTalk Orchestrations** in the Toolbox, drag a **Send** shape to the Orchestration Designer.</span></span> <span data-ttu-id="6d1f6-180">`Receive_PO` 受信図形の下に配置します。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-180">Place it below the `Receive_PO` Receive shape.</span></span>  
  
2.  <span data-ttu-id="6d1f6-181">送信図形を右クリックし、をクリックして**プロパティ ウィンドウ**します。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-181">Right-click the Send shape, and then click **Properties Window**.</span></span>  
  
3.  <span data-ttu-id="6d1f6-182">型`Send_PO`で、**名前**フィールドです。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-182">Type `Send_PO` in the **Name** field.</span></span>  
  
4.  <span data-ttu-id="6d1f6-183">選択`Message_PO`の**メッセージ**プロパティです。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-183">Select `Message_PO` for the **Message** property.</span></span>  
  
5.  <span data-ttu-id="6d1f6-184">選択`SendPurchaseOrder.PurchaseOrderOperation.Request`の**操作**プロパティです。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-184">Select `SendPurchaseOrder.PurchaseOrderOperation.Request` for the **Operation** property.</span></span> <span data-ttu-id="6d1f6-185">オーケストレーション デザイナの送信図形にポートが連結されます。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-185">This will tie the port to the Send shape in the Orchestration Designer.</span></span>  
  
#### <a name="add-a-decide-shape-to-the-orchestration"></a><span data-ttu-id="6d1f6-186">オーケストレーションへの判断図形の追加</span><span class="sxs-lookup"><span data-stu-id="6d1f6-186">Add a Decide shape to the orchestration</span></span>  
  
1.  <span data-ttu-id="6d1f6-187">**BizTalk オーケストレーション**、ツールボックスのドラッグ、**判断**図形をオーケストレーション デザイナにします。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-187">Under **BizTalk Orchestrations** in the Toolbox, drag a **Decide** shape to the Orchestration Designer.</span></span> <span data-ttu-id="6d1f6-188">`Send_PO` 送信図形の下に配置します。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-188">Place it below the `Send_PO` Send shape.</span></span>  
  
2.  <span data-ttu-id="6d1f6-189">判断図形を右クリックし、をクリックして**プロパティ ウィンドウ。**</span><span class="sxs-lookup"><span data-stu-id="6d1f6-189">Right-click the Decide shape, and then click **Properties Window.**</span></span>  
  
3.  <span data-ttu-id="6d1f6-190">型`NeedsApproval`で、**名前**フィールドです。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-190">Type `NeedsApproval` in the **Name** field.</span></span>  
  
4.  <span data-ttu-id="6d1f6-191">オーケストレーション デザイナーで、をクリックして**Rule_1**判断図形にします。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-191">In Orchestration Designer, click **Rule_1** on the Decide shape.</span></span>  
  
5.  <span data-ttu-id="6d1f6-192">プロパティ ウィンドウで、次のように入力します。`ApprovalRequired`の、**名前**プロパティです。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-192">In the Properties Windows, type `ApprovalRequired` for the **Name** property.</span></span>  
  
6.  <span data-ttu-id="6d1f6-193">クリックして、**式**プロパティ フィールドに、クリックして、省略記号 (**.**) ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-193">Click the **Expression** property field, and then click the ellipsis (**…**) button.</span></span>  
  
7.  <span data-ttu-id="6d1f6-194">BizTalk 式エディターに、以下の式を入力またはコピーします。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-194">In the BizTalk Expression Editor, type or copy the following:</span></span>  
  
    ```  
    Message_PO(OrderProcess.PropertySchema.Amount) > 1000  
    ```  
  
8.  <span data-ttu-id="6d1f6-195">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-195">Click **OK**.</span></span>  
  
#### <a name="add-another-send-port-to-the-orchestration"></a><span data-ttu-id="6d1f6-196">オーケストレーションへの別の送信ポートの追加</span><span class="sxs-lookup"><span data-stu-id="6d1f6-196">Add another send port to the orchestration</span></span>  
  
1.  <span data-ttu-id="6d1f6-197">**BizTalk オーケストレーション**、ツールボックスのドラッグ、**ポート**図形をポート画面にします。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-197">Under **BizTalk Orchestrations** in the Toolbox, drag a **Port** shape to the Port Surface.</span></span> <span data-ttu-id="6d1f6-198">ポート構成ウィザードが起動します。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-198">The Port Configuration Wizard will start.</span></span>  
  
2.  <span data-ttu-id="6d1f6-199">[ようこそ] 画面で、をクリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-199">On the Welcome screen, click **Next**.</span></span>  
  
3.  <span data-ttu-id="6d1f6-200">型`SendToTasksList`で、**名前**フィールド、およびをクリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-200">Type `SendToTasksList` in the **Name** field, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="6d1f6-201">選択**既存のポートの種類を使用して**です。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-201">Select **Use an existing Port Type**.</span></span>  
  
5.  <span data-ttu-id="6d1f6-202">**使用可能なポートの種類** `OrderProcess.PurchaseOrderPT`、順にクリック**次へ**です。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-202">Under **Available Port Types**, select `OrderProcess.PurchaseOrderPT`, and then click **Next**.</span></span>  
  
6.  <span data-ttu-id="6d1f6-203">**画面のポートのバインド****ポートの通信方向**`I'll always be sending messages on this port`です。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-203">On the **Port Binding screen**, under **Port direction of communication**, select `I'll always be sending messages on this port`.</span></span>  
  
7.  <span data-ttu-id="6d1f6-204">**ポートのバインド** `Dynamic`、順にクリック**次へ**です。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-204">Under **Port binding**, select `Dynamic`, and then click **Next**.</span></span>  
  
8.  <span data-ttu-id="6d1f6-205">**[完了]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-205">Click **Finish**.</span></span>  
  
#### <a name="add-a-send-shape-to-the-decide-shape"></a><span data-ttu-id="6d1f6-206">判断図形への送信図形の追加</span><span class="sxs-lookup"><span data-stu-id="6d1f6-206">Add a Send shape to the Decide shape</span></span>  
  
1.  <span data-ttu-id="6d1f6-207">**BizTalk オーケストレーション**、ツールボックスのドラッグ、**送信**図形をオーケストレーション デザイナにします。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-207">Under **BizTalk Orchestrations** in the Toolbox, drag a **Send** shape to the Orchestration Designer.</span></span> <span data-ttu-id="6d1f6-208">`ApprovalRequired` 図形の下に配置します。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-208">Place it below the `ApprovalRequired` shape.</span></span>  
  
2.  <span data-ttu-id="6d1f6-209">送信図形を右クリックし、をクリックして**プロパティ ウィンドウ**</span><span class="sxs-lookup"><span data-stu-id="6d1f6-209">Right-click the Send shape, and then click **Properties Window**</span></span>  
  
3.  <span data-ttu-id="6d1f6-210">型`CreateApprovalTask`で、**名前**フィールドです。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-210">Type `CreateApprovalTask` in the **Name** field.</span></span>  
  
4.  <span data-ttu-id="6d1f6-211">選択`Message_Task`の**メッセージ**プロパティです。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-211">Select `Message_Task` for the **Message** property.</span></span>  
  
5.  <span data-ttu-id="6d1f6-212">選択`SendToTasksList.PurchaseOrderOperation.Request`の**操作**プロパティです。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-212">Select `SendToTasksList.PurchaseOrderOperation.Request` for the **Operation** property.</span></span> <span data-ttu-id="6d1f6-213">オーケストレーション デザイナの送信図形にポートが連結されます。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-213">This will tie the port to the Send shape in the Orchestration Designer.</span></span>  
  
## <a name="create-an-expression"></a><span data-ttu-id="6d1f6-214">式の作成</span><span class="sxs-lookup"><span data-stu-id="6d1f6-214">Create an expression</span></span>  
 <span data-ttu-id="6d1f6-215">ここでは、To Do パス値を変数に代入する式図形をソリューションに追加します。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-215">In this procedure you add an Expression shape to your solution which assigns the Tasks path value to a variable.</span></span> <span data-ttu-id="6d1f6-216">この手順は、動的送信ポートのプロパティを変更するためのロジックをオーケストレーションに追加する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-216">This procedure illustrates how to add logic to an orchestration to modify the properties of a dynamic send port.</span></span>  
  
#### <a name="create-a-new-expression"></a><span data-ttu-id="6d1f6-217">新しい式の作成</span><span class="sxs-lookup"><span data-stu-id="6d1f6-217">Create a new expression</span></span>  
  
1.  <span data-ttu-id="6d1f6-218">**BizTalk オーケストレーション**、ツールボックスのドラッグ、**式**図形の前に、`CreateApprovalTask`送信図形。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-218">Under **BizTalk Orchestrations** in the Toolbox, drag an **Expression** shape before the `CreateApprovalTask` Send shape.</span></span>  
  
2.  <span data-ttu-id="6d1f6-219">式図形を右クリックし、をクリックして**プロパティ ウィンドウ。**</span><span class="sxs-lookup"><span data-stu-id="6d1f6-219">Right-click the Expression shape, and then click **Properties Window.**</span></span>  
  
3.  <span data-ttu-id="6d1f6-220">型`SetPortDestination`で、**名前**フィールドです。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-220">Type `SetPortDestination` in the **Name** field.</span></span>  
  
4.  <span data-ttu-id="6d1f6-221">クリックして、**式**プロパティ フィールドに、クリックして、省略記号 (**.**) ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-221">Click the **Expression** property field, and then click the ellipsis (**…**) button.</span></span>  
  
5.  <span data-ttu-id="6d1f6-222">**BizTalk 式エディタ**次を入力します。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-222">In the **BizTalk Expression Editor**, type the following:</span></span>  
  
    ```  
    SendToTasksList(Microsoft.XLANGs.BaseTypes.Address) = "wss://localhost/sites/WSSAdapterWalkthrough/Lists/Tasks/";  
    ```  
  
6.  <span data-ttu-id="6d1f6-223">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-223">Click **OK**.</span></span>  
  
## <a name="construct-a-new-message"></a><span data-ttu-id="6d1f6-224">新しいメッセージの構築</span><span class="sxs-lookup"><span data-stu-id="6d1f6-224">Construct a new message</span></span>  
 <span data-ttu-id="6d1f6-225">ここでは、ある種類のメッセージの新しいインスタンスをオーケストレーションに構築する、メッセージ構築図形をソリューションに追加します。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-225">In this procedure you add a Construct shape to the solution which will construct a new instance of a message type within the orchestration.</span></span> <span data-ttu-id="6d1f6-226">この手順は、受信メッセージをコピーして新しいメッセージを作成し、そのコンテキスト プロパティを変更する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-226">This procedure illustrates how to create a new message that is a copy of the inbound message and then modify the context properties of the new message.</span></span> <span data-ttu-id="6d1f6-227">BizTalk 内ではメッセージは不変である、つまり、作成した後に元のメッセージに変更を加えることはできないため、この手順が必要になります。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-227">This step is required because messages are immutable in BizTalk; that is, once you have constructed it, you cannot modify the original.</span></span>  
  
#### <a name="add-a-construct-shape"></a><span data-ttu-id="6d1f6-228">メッセージ構築図形の追加</span><span class="sxs-lookup"><span data-stu-id="6d1f6-228">Add a Construct Shape</span></span>  
  
1.  <span data-ttu-id="6d1f6-229">**BizTalk オーケストレーション**、ツールボックスのドラッグ、**メッセージの構築**図形の前に、`SetPortDestination`式図形です。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-229">Under **BizTalk Orchestrations** in the Toolbox, drag a **Construct Message** shape before the `SetPortDestination` Expression shape.</span></span>  
  
2.  <span data-ttu-id="6d1f6-230">メッセージの構築図形を右クリックし、をクリックして**プロパティ ウィンドウ。**</span><span class="sxs-lookup"><span data-stu-id="6d1f6-230">Right-click the Construct Message shape, and then click **Properties Window.**</span></span>  
  
3.  <span data-ttu-id="6d1f6-231">型`ConstructTaskMessage`で、**名前**フィールドです。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-231">Type `ConstructTaskMessage`in the **Name** field.</span></span>  
  
4.  <span data-ttu-id="6d1f6-232">選択`Message_Task`の**構築メッセージ**プロパティです。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-232">Select `Message_Task` for the **Messages Constructed** property.</span></span>  
  
5.  <span data-ttu-id="6d1f6-233">**BizTalk オーケストレーション**、ツールボックスのドラッグ、**メッセージの割り当て**図形を`ConstructTaskMessage`**メッセージの構築**図形です。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-233">Under **BizTalk Orchestrations** in the Toolbox, drag a **Message Assignment** shape into the `ConstructTaskMessage`**Construct Message** shape.</span></span>  
  
6.  <span data-ttu-id="6d1f6-234">**プロパティ ウィンドウ**、型`InitTaskMessage`で、**名前**フィールドです。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-234">In the **Properties Window**, type `InitTaskMessage` in the **Name** field.</span></span>  
  
7.  <span data-ttu-id="6d1f6-235">クリックして、**式**プロパティ フィールドに、クリックして、省略記号 (**.**) ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-235">Click the **Expression** property field, and then click the ellipsis (**…**) button.</span></span>  
  
8.  <span data-ttu-id="6d1f6-236">**BizTalk 式エディタ**を入力するか、以下をコピーします。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-236">In the **BizTalk Expression Editor**, type or copy the following:</span></span>  
  
    ```  
    Message_Task = Message_PO;  
    Message_Task(WSS.ConfigOverwrite) = "no";  
    Message_Task(WSS.ConfigNamespaceAliases)= "orchns='http://OrderProcess.PurchaseOrder'";  
    Message_Task(WSS.ConfigPropertiesXml) = "<ConfigPropertiesXml><PropertyName1>Title</PropertyName1><PropertySource1>Approve %XPATH=//orchns:PurchaseOrder/orchns:PurchaseOrderID%</PropertySource1><PropertyName3>Status</PropertyName3><PropertySource3>Not Started</PropertySource3><PropertyName4>Priority</PropertyName4><PropertySource4>(1) High</PropertySource4></ConfigPropertiesXml>";  
    ```  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="6d1f6-237">上記のコンテキスト プロパティに指定する値は、大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-237">These values supplied for these context properties are case sensitive.</span></span> <span data-ttu-id="6d1f6-238">コンテキスト プロパティと動的なポートの構成値を設定するときに正しい大文字小文字を使用するか、送信ポートを BizTalk の試行を指定したドキュメントをルーティングする場合は、エラーが発生することを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-238">When setting configuration values for a dynamic port with context properties you must ensure that you use the proper case or an error will occur when BizTalk attempts to route the document to the designated send port.</span></span>  
  
9. <span data-ttu-id="6d1f6-239">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-239">Click **OK**.</span></span>  
  
10. <span data-ttu-id="6d1f6-240">をクリックして**ファイル**、クリックして**すべてを保存**です。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-240">Click **File**, and then click **Save All**.</span></span>  
  
## <a name="build-the-biztalk-project"></a><span data-ttu-id="6d1f6-241">BizTalk プロジェクトのビルド</span><span class="sxs-lookup"><span data-stu-id="6d1f6-241">Build the BizTalk project</span></span>  
 <span data-ttu-id="6d1f6-242">ここでは、BizTalk プロジェクトをビルドして配置します。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-242">In this procedure you build and deploy the BizTalk project.</span></span> <span data-ttu-id="6d1f6-243">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] によって実行時に使用されるアセンブリを作成および配置するために、この手順が必要になります。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-243">This step is required to create and deploy the assembly that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] uses at runtime.</span></span>  
  
#### <a name="build-and-deploy-the-solution"></a><span data-ttu-id="6d1f6-244">ソリューションのビルドおよび配置</span><span class="sxs-lookup"><span data-stu-id="6d1f6-244">Build and deploy the solution</span></span>  
  
1.  <span data-ttu-id="6d1f6-245">をクリックして**ビルド**、クリックして**orderprocess のビルド**です。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-245">Click **Build**, and then click **Build OrderProcess**.</span></span>  
  
2.  <span data-ttu-id="6d1f6-246">をクリックして**ビルド**、クリックして**orderprocess の配置**です。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-246">Click **Build**, and then click **Deploy OrderProcess**.</span></span>  
  
3.  <span data-ttu-id="6d1f6-247">[Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]] を閉じます。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-247">Close Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
## <a name="modify-the-receive-location-and-send-port"></a><span data-ttu-id="6d1f6-248">受信場所と送信ポートの変更</span><span class="sxs-lookup"><span data-stu-id="6d1f6-248">Modify the receive location and send port</span></span>  
 <span data-ttu-id="6d1f6-249">ここでは、既存の受信場所と送信ポートを、パイプラインで XML 処理を行うように変更します。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-249">In this procedure you modify the existing receive location and send port to use XML processing for the pipelines.</span></span> <span data-ttu-id="6d1f6-250">受信 XML パイプラインでは、オーケストレーション処理中に使用されたメッセージ プロパティが保持されます。また、送信 XML パイプラインでは、オーケストレーションで適用されたメッセージ プロパティ (後でメッセージ ルーティングに使用される) が保持されます。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-250">The receive XML pipeline persists message properties used during orchestration processing and the send XML pipeline persists the message properties that were applied in the orchestration which are subsequently used for message routing.</span></span>  
  
#### <a name="modify-the-receive-location"></a><span data-ttu-id="6d1f6-251">受信場所を変更します。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-251">Modify the receive location</span></span>  
  
1.  <span data-ttu-id="6d1f6-252">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]、順にクリック**BizTalk Server 管理コンソールです。**</span><span class="sxs-lookup"><span data-stu-id="6d1f6-252">Click **Start**, point to **All Programs**, point to **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)], and then click **BizTalk Server Administration.**</span></span>  
  
2.  <span data-ttu-id="6d1f6-253">展開**Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **管理スナップイン**、展開**BizTalk グループ**、展開**アプリケーション**の展開**BizTalk アプリケーション 1**、をクリックし、**受信場所**ノード。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-253">Expand **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **Administration SnapIn**, expand **BizTalk Group**, expand **Applications**, expand **BizTalk Application 1**, and then click the **Receive Locations** node.</span></span>  
  
3.  <span data-ttu-id="6d1f6-254">右クリック`SourceLocation`、クリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-254">Right-click `SourceLocation`, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="6d1f6-255">**受信場所のプロパティ**ダイアログ ボックスで、**全般**`XMLReceive`の**受信パイプライン**プロパティです。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-255">In the **Receive Location Properties** dialog box, under **General**, select `XMLReceive` for the **Receive pipeline** property.</span></span>  
  
5.  <span data-ttu-id="6d1f6-256">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-256">Click **OK**.</span></span>  
  
#### <a name="modify-the-send-port"></a><span data-ttu-id="6d1f6-257">送信ポートの変更</span><span class="sxs-lookup"><span data-stu-id="6d1f6-257">Modify the send port</span></span>  
  
1.  <span data-ttu-id="6d1f6-258">クリックして、**送信ポート**ノード。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-258">Click the **Send Ports** node.</span></span>  
  
2.  <span data-ttu-id="6d1f6-259">右クリック`SendToDestination`、クリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-259">Right-click `SendToDestination`, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="6d1f6-260">**送信ポートのプロパティ**ダイアログ ボックスで、**全般**`XMLTransmit`の**送信パイプライン**プロパティです。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-260">In the **Send Port Properties** dialog box, under **General**, select `XMLTransmit` for the **Send pipeline** property.</span></span>  
  
4.  <span data-ttu-id="6d1f6-261">選択、**フィルター**タブです。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-261">Select the **Filters** tab.</span></span>  
  
5.  <span data-ttu-id="6d1f6-262">既存の条件を選択して、del キー、およびをクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-262">Select the existing condition, press DELETE, and then click **OK**.</span></span>  
  
#### <a name="start-a-new-send-port"></a><span data-ttu-id="6d1f6-263">新しい送信ポートの開始</span><span class="sxs-lookup"><span data-stu-id="6d1f6-263">Start a new send port</span></span>  
  
1.  <span data-ttu-id="6d1f6-264">クリックして、**送信ポート**ノード。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-264">Click the **Send Ports** node.</span></span>  
  
2.  <span data-ttu-id="6d1f6-265">右クリック`OrderProcess_1.0.0.0_OrderProcess.MyCompanyOrderProcess_SendToTasksList_<GUID>`、クリックして**開始**です。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-265">Right-click `OrderProcess_1.0.0.0_OrderProcess.MyCompanyOrderProcess_SendToTasksList_<GUID>`, and then click **Start**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6d1f6-266">これが表示されない場合は、コンソールを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-266">You may have to refresh the console if this is not visible.</span></span>  
  
## <a name="bind-the-orchestration"></a><span data-ttu-id="6d1f6-267">オーケストレーションをバインドします</span><span class="sxs-lookup"><span data-stu-id="6d1f6-267">Bind the orchestration</span></span>  
 <span data-ttu-id="6d1f6-268">ここでは、指定したポートにオーケストレーションをバインドします。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-268">In this procedure you bind the orchestration to the specified ports.</span></span> <span data-ttu-id="6d1f6-269">ビルドと配置が済んだオーケストレーションに対し、物理ポートを関連付けるために、この手順が必要になります。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-269">This procedure is required to tie physical ports to the orchestration that you built and deployed.</span></span>  
  
#### <a name="bind-the-orchestration"></a><span data-ttu-id="6d1f6-270">オーケストレーションをバインドします</span><span class="sxs-lookup"><span data-stu-id="6d1f6-270">Bind the orchestration</span></span>  
  
1.  <span data-ttu-id="6d1f6-271">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、をクリックして、**オーケストレーション**ノード。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-271">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, click the **Orchestrations** node.</span></span>  
  
2.  <span data-ttu-id="6d1f6-272">右クリックし、`OrderProcess.MyCompanyOrderProcessing`オーケストレーション、およびクリック**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-272">Right-click the `OrderProcess.MyCompanyOrderProcessing` orchestration, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="6d1f6-273">選択、**バインド**タブです。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-273">Select the **Bindings** tab.</span></span>  
  
4.  <span data-ttu-id="6d1f6-274">**ホスト**`BizTalkServerApplication`で、**ホスト**フィールドです。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-274">Under **Host**, select `BizTalkServerApplication` in the **Host** field.</span></span>  
  
5.  <span data-ttu-id="6d1f6-275">**バインド**`FromSource`の`ReceivePurchaseOrder`受信論理ポートです。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-275">Under **Bindings**, select `FromSource` for the `ReceivePurchaseOrder` Inbound Logical Port.</span></span>  
  
6.  <span data-ttu-id="6d1f6-276">**バインド**`SendToDestination`の`SendPurchaseOrder`論理送信ポート。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-276">Under **Bindings**, select `SendToDestination` for the `SendPurchaseOrder` Outbound Logical Port.</span></span>  
  
7.  <span data-ttu-id="6d1f6-277">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-277">Click **OK**.</span></span>  
  
8.  <span data-ttu-id="6d1f6-278">右クリックして`OrderProcess.MyCompanyOrderProcessing`オーケストレーション、およびクリック**開始**です。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-278">Right click `OrderProcess.MyCompanyOrderProcessing` orchestration, and then click **Start**.</span></span>  
  
## <a name="send-a-message-through-the-system"></a><span data-ttu-id="6d1f6-279">システムからのメッセージ送信</span><span class="sxs-lookup"><span data-stu-id="6d1f6-279">Send a message through the system</span></span>  
 <span data-ttu-id="6d1f6-280">ここでは、InfoPath フォームを作成し、Windows SharePoint Services Web サイトにアップロードします。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-280">In this procedure you create an InfoPath form and upload it to the Windows SharePoint Services Web site.</span></span> <span data-ttu-id="6d1f6-281">そのメッセージは Windows SharePoint Services アダプターによって取得され、アーカイブ ドキュメント ライブラリにアーカイブされた後、アップロード先のドキュメント ライブラリに送信されます。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-281">The Windows SharePoint Services adapter will take that message, archive it in the Archive document library, and then send it to the Destination document library.</span></span> <span data-ttu-id="6d1f6-282">このメッセージを処理する間、送信先を判断するために Windows SharePoint Services のコンテキスト プロパティにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-282">During the processing of this message, Windows SharePoint Services context properties will be accessed that help determine the destination.</span></span>  
  
#### <a name="create-an-infopath-form-to-send-through-the-system"></a><span data-ttu-id="6d1f6-283">システムから送信する InfoPath フォームの作成</span><span class="sxs-lookup"><span data-stu-id="6d1f6-283">Create an InfoPath form to send through the system</span></span>  
  
1.  <span data-ttu-id="6d1f6-284">Web ブラウザを開き、作成したサイトの URL に移動します。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-284">Open a Web browser and navigate to the URL of the site you created.</span></span> <span data-ttu-id="6d1f6-285">たとえば、 `http://<server_name>/sites/WSSAdapterWalkthrough`のようにします。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-285">For example, `http://<server_name>/sites/WSSAdapterWalkthrough`.</span></span>  
  
2.  <span data-ttu-id="6d1f6-286">クイック起動メニューの `InfoPathSolutions` をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-286">In the Quick Launch menu, click `InfoPathSolutions`.</span></span>  
  
3.  <span data-ttu-id="6d1f6-287">クリックして、`PurchaseOrder`に表示されるファイル、**ファイルのダウンロード**クリックしてダイアログ ボックスで、**開く**です。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-287">Click the `PurchaseOrder` file to display the **File Download** dialog box, and then click **Open**.</span></span> <span data-ttu-id="6d1f6-288">フォームが読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-288">InfoPath will load the form.</span></span>  
  
4.  <span data-ttu-id="6d1f6-289">**Purchase Order ID**フィールドに「`1003`です。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-289">In the **Purchase Order ID** field, type `1003`.</span></span>  
  
5.  <span data-ttu-id="6d1f6-290">**請求先**フィールドに「`John Doe`です。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-290">In the **Bill To** field, type `John Doe`.</span></span>  
  
6.  <span data-ttu-id="6d1f6-291">**量**フィールドに「`1750`です。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-291">In the **Amount** field, type `1750`.</span></span>  
  
7.  <span data-ttu-id="6d1f6-292">**Purchase Order Date**フィールドに「`1/3/2005`です。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-292">In the **Purchase Order Date** field, type `1/3/2005`.</span></span>  
  
8.  <span data-ttu-id="6d1f6-293">**[保存]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-293">Click **Save**.</span></span>  
  
9. <span data-ttu-id="6d1f6-294">**名前を付けて保存** ダイアログ ボックスで、「`http://<server_name>/sites/WSSAdapterWalkthrough/Source`で、**ファイル名**フィールド、および ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-294">In the **Save As** dialog box, type `http://<server_name>/sites/WSSAdapterWalkthrough/Source`in the **file name** field, and then press ENTER.</span></span>  
  
10. <span data-ttu-id="6d1f6-295">型`PurchaseOrder3.xml`で、**ファイル名**フィールドをクリックして**保存**です。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-295">Type `PurchaseOrder3.xml` in the **file name** field, and then click **Save**.</span></span>  
  
11. <span data-ttu-id="6d1f6-296">InfoPath を終了します。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-296">Close InfoPath.</span></span>  
  
12. <span data-ttu-id="6d1f6-297">Web ブラウザーで、をクリックして**ドキュメントし、リスト**です。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-297">In the Web browser, click **Documents and Lists**.</span></span>  
  
13. <span data-ttu-id="6d1f6-298">**ドキュメント ライブラリ**をクリックして**先**です。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-298">Under **Document Libraries**, click **Destination**.</span></span>  
  
14. <span data-ttu-id="6d1f6-299">移行先ドキュメント ライブラリに表示されます、メッセージのこのライブラリの一覧です。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-299">In the Destination document library, you will now see your message listed in this library.</span></span> <span data-ttu-id="6d1f6-300">アーカイブ ドキュメント ライブラリにアーカイブされたコピーも紹介します。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-300">You will also find a copy archived in the Archive document library.</span></span>  
  
15. <span data-ttu-id="6d1f6-301">**[ホーム]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-301">Click **Home**.</span></span>  
  
16. <span data-ttu-id="6d1f6-302">**を一覧表示**をクリックして**タスク**です。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-302">Under **Lists**, click **Tasks**.</span></span>  
  
17. <span data-ttu-id="6d1f6-303">To Do リストに、新しく作成した承認済みのアイテムが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-303">In the Tasks list you will see the newly created approval task.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6d1f6-304">注文書の総額が $1,000.00 を超えていたので、タスクが作成されます。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-304">Since the amount of the purchase order was over $1,000.00, the task was created.</span></span>  
  
## <a name="summary"></a><span data-ttu-id="6d1f6-305">概要</span><span class="sxs-lookup"><span data-stu-id="6d1f6-305">Summary</span></span>  
 <span data-ttu-id="6d1f6-306">このチュートリアルでは、Windows SharePoint Services のコンテキスト プロパティにアクセスする方法、および動的ポートを経由してメッセージの送信先を判断する方法を確認しました。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-306">In this walkthrough you have seen how to access the Windows SharePoint Services context properties and how to determine the destination of messages going through dynamic ports.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="6d1f6-307">次の手順</span><span class="sxs-lookup"><span data-stu-id="6d1f6-307">Next Steps</span></span>  
 <span data-ttu-id="6d1f6-308">Windows SharePoint Services アダプター セクションの残りの部分に進んでください。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-308">Continue to review the rest of the Windows SharePoint Services adapter section.</span></span> <span data-ttu-id="6d1f6-309">詳細については、「関連項目」の該当するトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6d1f6-309">For more information, see the topics in See Also.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d1f6-310">参照</span><span class="sxs-lookup"><span data-stu-id="6d1f6-310">See Also</span></span>  
 <span data-ttu-id="6d1f6-311">[Windows SharePoint Services アダプターとは何ですか。](../core/what-is-the-windows-sharepoint-services-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="6d1f6-311">[What Is the Windows SharePoint Services Adapter?](../core/what-is-the-windows-sharepoint-services-adapter.md) </span></span>  
 [<span data-ttu-id="6d1f6-312">Windows SharePoint Services アダプタのチュートリアル</span><span class="sxs-lookup"><span data-stu-id="6d1f6-312">Windows SharePoint Services Adapter Walkthroughs</span></span>](../core/windows-sharepoint-services-adapter-walkthroughs.md)