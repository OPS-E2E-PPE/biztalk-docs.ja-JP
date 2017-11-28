---
title: "手順 2: ビジネス プロセスの定義 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b37bd9f1-5ee2-434d-950a-cf12967b6fc2
caps.latest.revision: "49"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 17f181933daac5170c517a23f809eb97b54f2900
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-2-define-the-business-process"></a><span data-ttu-id="83f96-102">ステップ 2: ビジネス プロセスの定義</span><span class="sxs-lookup"><span data-stu-id="83f96-102">Step 2: Define the Business Process</span></span>
<span data-ttu-id="83f96-103">![手順 4 2](../adapters-and-accelerators/adapter-oracle-ebs/media/step-2of4.gif "Step_2of4")</span><span class="sxs-lookup"><span data-stu-id="83f96-103">![Step 2 of 4](../adapters-and-accelerators/adapter-oracle-ebs/media/step-2of4.gif "Step_2of4")</span></span>  
  
 <span data-ttu-id="83f96-104">**所要時間:** 8 分</span><span class="sxs-lookup"><span data-stu-id="83f96-104">**Time to complete:** 8 minutes</span></span>  
  
 <span data-ttu-id="83f96-105">**目標:**このステップで、ビジネス プロセスを定義するオーケストレーション デザイナーを使用しています。</span><span class="sxs-lookup"><span data-stu-id="83f96-105">**Objective:** In this step, you use Orchestration Designer to define your business process.</span></span>  
  
 <span data-ttu-id="83f96-106">**目的:**オーケストレーションのワークフローが表し、在庫補充要求を承認するため、会社のビジネス プロセスを自動化します。</span><span class="sxs-lookup"><span data-stu-id="83f96-106">**Purpose:** The workflow of the orchestration represents and automates your company's business process for approving inventory replenishment requests.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="83f96-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="83f96-107">Prerequisites</span></span>  
 <span data-ttu-id="83f96-108">このステップを開始する前に、以下の要件を確認してください。</span><span class="sxs-lookup"><span data-stu-id="83f96-108">Note the following requirements before you begin this step:</span></span>  
  
-   <span data-ttu-id="83f96-109">この手順を開始する前に行う必要があります[手順 1: EAIOrchestration プロジェクトがソリューションに追加](../core/step-1-add-eaiorchestration-project-to-the-solution.md)です。</span><span class="sxs-lookup"><span data-stu-id="83f96-109">Before you begin this step you must complete [Step 1: Add EAIOrchestration Project to the Solution](../core/step-1-add-eaiorchestration-project-to-the-solution.md).</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="83f96-110">手順</span><span class="sxs-lookup"><span data-stu-id="83f96-110">Procedures</span></span>  
 <span data-ttu-id="83f96-111">オーケストレーションの開発のための最初の手順は、アクション図形を使用してビジネス プロセスを表すことです。</span><span class="sxs-lookup"><span data-stu-id="83f96-111">The first step for developing an orchestration is to use action shapes to represent the business process.</span></span>  
  
#### <a name="to-create-the-eai-business-process-workflow"></a><span data-ttu-id="83f96-112">EAI ビジネス プロセスのワークフローを作成するには</span><span class="sxs-lookup"><span data-stu-id="83f96-112">To create the EAI business process workflow</span></span>  
  
1.  <span data-ttu-id="83f96-113">ソリューション エクスプ ローラーで、Visual Studio からダブルクリック**EAIProcess.odx**オーケストレーションを開きます。</span><span class="sxs-lookup"><span data-stu-id="83f96-113">From Visual Studio, in Solution Explorer, double-click **EAIProcess.odx** to open the orchestration.</span></span>  
  
2.  <span data-ttu-id="83f96-114">オーケストレーション デザイナで、オーケストレーション ツールボックスからドラッグして、**受信**図形し、の間にドロップ、**開始**(緑色の円) と**終了**図形 (赤色の八角形)。</span><span class="sxs-lookup"><span data-stu-id="83f96-114">In Orchestration Designer, from the orchestration Toolbox, drag the **Receive** shape, and drop it between the **Begin** (green circle) and **End** (red octagon) shapes.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="83f96-115">ツールボックスを開いた状態でない場合、**ビュー**  メニューのをクリックして**ツールボックス**です。</span><span class="sxs-lookup"><span data-stu-id="83f96-115">If the Toolbox is not open, in the **View** menu, click **Toolbox**.</span></span> <span data-ttu-id="83f96-116">ツールボックスを画面上に固定するには、画鋲のアイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="83f96-116">To anchor it on the screen, click the thumbtack icon.</span></span>  
  
3.  <span data-ttu-id="83f96-117">ツールボックスからドラッグして、**判断**図形、受信図形の下にします。</span><span class="sxs-lookup"><span data-stu-id="83f96-117">From the toolbox, drag the **Decide** shape beneath the Receive shape.</span></span>  
  
4.  <span data-ttu-id="83f96-118">ツールボックスからドラッグして、**変換**決定図形の左側の分岐に図形です。</span><span class="sxs-lookup"><span data-stu-id="83f96-118">From the toolbox, drag the **Transform** shape to the left branch of the Decide shape.</span></span> <span data-ttu-id="83f96-119">変換図形は メッセージの構築図形で入れ子になっています。</span><span class="sxs-lookup"><span data-stu-id="83f96-119">The Transform shape is nested inside the Construct Message shape.</span></span>  
  
5.  <span data-ttu-id="83f96-120">ツールボックスからドラッグして、**送信**図形、変換図形の下にします。</span><span class="sxs-lookup"><span data-stu-id="83f96-120">From the toolbox, drag the **Send** shape beneath the Transform shape.</span></span>  
  
6.  <span data-ttu-id="83f96-121">ツールボックスからドラッグして、**送信**決定図形の右分岐に図形です。</span><span class="sxs-lookup"><span data-stu-id="83f96-121">From the toolbox, drag the **Send** shape to the right branch of the Decide shape.</span></span>  <span data-ttu-id="83f96-122">操作図形を追加すると、オーケストレーションは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="83f96-122">The orchestration looks like the following after you added the action shapes:</span></span>  
  
     <span data-ttu-id="83f96-123">![EAI プロセス](../core/media/eaiprocess.gif "EAIProcess")</span><span class="sxs-lookup"><span data-stu-id="83f96-123">![EAI process](../core/media/eaiprocess.gif "EAIProcess")</span></span>  
  
 <span data-ttu-id="83f96-124">次の手順では、メッセージ変数を定義します。</span><span class="sxs-lookup"><span data-stu-id="83f96-124">The next step is to define message variables.</span></span>  <span data-ttu-id="83f96-125">操作によっては、メッセージ プロパティを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="83f96-125">Several action shapes have a message property that needs to be specified.</span></span>  
  
#### <a name="to-define-message-variables"></a><span data-ttu-id="83f96-126">メッセージ変数を定義するには</span><span class="sxs-lookup"><span data-stu-id="83f96-126">To define message variables</span></span>  
  
1.  <span data-ttu-id="83f96-127">Visual Studio から、をクリックして、**ビュー**  メニューのをクリックして**その他のウィンドウ**、クリックして**オーケストレーション ビュー**です。</span><span class="sxs-lookup"><span data-stu-id="83f96-127">From Visual Studio, click the **View** menu, click **Other Windows**, and then click **Orchestration View**.</span></span>  
  
2.  <span data-ttu-id="83f96-128">オーケストレーション ビューを右クリックして**メッセージ**、クリックして**新しいメッセージ**です。</span><span class="sxs-lookup"><span data-stu-id="83f96-128">From Orchestration View, right-click **Messages**, and then click **New Message**.</span></span>  
  
3.  <span data-ttu-id="83f96-129">[プロパティ ウィンドウ] で、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="83f96-129">In the Properties window, do the following:</span></span>  
  
    |<span data-ttu-id="83f96-130">プロパティ</span><span class="sxs-lookup"><span data-stu-id="83f96-130">Use this</span></span>|<span data-ttu-id="83f96-131">目的</span><span class="sxs-lookup"><span data-stu-id="83f96-131">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="83f96-132">**[Identifier]**</span><span class="sxs-lookup"><span data-stu-id="83f96-132">**Identifier**</span></span>|<span data-ttu-id="83f96-133">型**RequestMessage**です。</span><span class="sxs-lookup"><span data-stu-id="83f96-133">Type **RequestMessage**.</span></span>|  
    |<span data-ttu-id="83f96-134">**メッセージの種類**</span><span class="sxs-lookup"><span data-stu-id="83f96-134">**Message Type**</span></span>|<span data-ttu-id="83f96-135">をクリックして**スキーマ**、クリックして**\<参照されるアセンブリの選択 >**です。</span><span class="sxs-lookup"><span data-stu-id="83f96-135">Click **Schemas**, and then click **\<Select from referenced assembly …>**.</span></span> <span data-ttu-id="83f96-136">[アイテムの種類] ウィンドウからをクリックして**EAISchemas**、クリックして**要求**です。</span><span class="sxs-lookup"><span data-stu-id="83f96-136">From the Select Artifact Type window, click **EAISchemas**, and then click **Request**.</span></span> <span data-ttu-id="83f96-137">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="83f96-137">Click **OK**</span></span>|  
  
4.  <span data-ttu-id="83f96-138">オーケストレーション ビューを右クリックして**メッセージ**、クリックして**新しいメッセージ**です。</span><span class="sxs-lookup"><span data-stu-id="83f96-138">From Orchestration View, right-click **Messages**, and then click **New Message**.</span></span>  
  
5.  <span data-ttu-id="83f96-139">[プロパティ ウィンドウ] で、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="83f96-139">In the Properties window, do the following:</span></span>  
  
    |<span data-ttu-id="83f96-140">プロパティ</span><span class="sxs-lookup"><span data-stu-id="83f96-140">Use this</span></span>|<span data-ttu-id="83f96-141">目的</span><span class="sxs-lookup"><span data-stu-id="83f96-141">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="83f96-142">**[Identifier]**</span><span class="sxs-lookup"><span data-stu-id="83f96-142">**Identifier**</span></span>|<span data-ttu-id="83f96-143">型**RequestDeclineMessage**です。</span><span class="sxs-lookup"><span data-stu-id="83f96-143">Type **RequestDeclineMessage**.</span></span>|  
    |<span data-ttu-id="83f96-144">**メッセージの種類**</span><span class="sxs-lookup"><span data-stu-id="83f96-144">**Message Type**</span></span>|<span data-ttu-id="83f96-145">をクリックして**スキーマ**、クリックして**\<参照されるアセンブリの選択 >**です。</span><span class="sxs-lookup"><span data-stu-id="83f96-145">Click **Schemas**, and then click **\<Select from referenced assembly …>**.</span></span> <span data-ttu-id="83f96-146">[アイテムの種類] ウィンドウからをクリックして**EAISchemas**、クリックして**RequestDecline**です。</span><span class="sxs-lookup"><span data-stu-id="83f96-146">From the Select Artifact Type window, click **EAISchemas**, and then click **RequestDecline**.</span></span> <span data-ttu-id="83f96-147">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="83f96-147">Click **OK**</span></span>|  
  
#### <a name="to-configure-the-properties-of-the-shapes"></a><span data-ttu-id="83f96-148">図形のプロパティを構成するには</span><span class="sxs-lookup"><span data-stu-id="83f96-148">To configure the properties of the shapes</span></span>  
  
1.  <span data-ttu-id="83f96-149">デザイン画面でクリックして、**受信**図形を選択します。</span><span class="sxs-lookup"><span data-stu-id="83f96-149">On the design surface, click the **Receive** shape to select it.</span></span>  
  
2.  <span data-ttu-id="83f96-150">[プロパティ ウィンドウ] で、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="83f96-150">In the Properties window, do the following:</span></span>  
  
    |<span data-ttu-id="83f96-151">プロパティ</span><span class="sxs-lookup"><span data-stu-id="83f96-151">Use this</span></span>|<span data-ttu-id="83f96-152">目的</span><span class="sxs-lookup"><span data-stu-id="83f96-152">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="83f96-153">**名前**</span><span class="sxs-lookup"><span data-stu-id="83f96-153">**Name**</span></span>|<span data-ttu-id="83f96-154">型**ReceiveRequest**です。</span><span class="sxs-lookup"><span data-stu-id="83f96-154">Type **ReceiveRequest**.</span></span>|  
    |<span data-ttu-id="83f96-155">**メッセージ**</span><span class="sxs-lookup"><span data-stu-id="83f96-155">**Message**</span></span>|<span data-ttu-id="83f96-156">選択**RequestMessage**です。</span><span class="sxs-lookup"><span data-stu-id="83f96-156">Select **RequestMessage**.</span></span>|  
    |<span data-ttu-id="83f96-157">**Activate**</span><span class="sxs-lookup"><span data-stu-id="83f96-157">**Activate**</span></span>|<span data-ttu-id="83f96-158">ドロップダウン リストから選択**True**です。</span><span class="sxs-lookup"><span data-stu-id="83f96-158">From the drop-down list, select **True**.</span></span>|  
  
    > [!NOTE]
    >  <span data-ttu-id="83f96-159">プロパティ ウィンドウが開いた状態でない場合、**ビュー**  メニューのをクリックして**プロパティ ウィンドウ**します。</span><span class="sxs-lookup"><span data-stu-id="83f96-159">If the Property window is not open, in the **View** menu, click **Properties Window**.</span></span>  
  
3.  <span data-ttu-id="83f96-160">デザイン画面でクリックして、**判断**図形です。</span><span class="sxs-lookup"><span data-stu-id="83f96-160">On the design surface, click the **Decide** shape.</span></span>  
  
4.  <span data-ttu-id="83f96-161">[プロパティ ウィンドウ] で、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="83f96-161">In the Properties window, do the following:</span></span>  
  
    |<span data-ttu-id="83f96-162">プロパティ</span><span class="sxs-lookup"><span data-stu-id="83f96-162">Use this</span></span>|<span data-ttu-id="83f96-163">目的</span><span class="sxs-lookup"><span data-stu-id="83f96-163">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="83f96-164">**名前**</span><span class="sxs-lookup"><span data-stu-id="83f96-164">**Name**</span></span>|<span data-ttu-id="83f96-165">型**CheckGrandTotal**です。</span><span class="sxs-lookup"><span data-stu-id="83f96-165">Type **CheckGrandTotal**.</span></span>|  
  
    > [!NOTE]
    >  <span data-ttu-id="83f96-166">プロパティ ウィンドウが開いた状態でない場合、**ビュー**  メニューのをクリックして**プロパティ ウィンドウ**します。</span><span class="sxs-lookup"><span data-stu-id="83f96-166">If the Property window is not open, in the **View** menu, click **Properties Window**.</span></span>  
  
5.  <span data-ttu-id="83f96-167">デザイン画面でクリックして、 **Rule_1**図形です。</span><span class="sxs-lookup"><span data-stu-id="83f96-167">On the design surface, click the **Rule_1** shape.</span></span>  
  
6.  <span data-ttu-id="83f96-168">[プロパティ ウィンドウ] で、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="83f96-168">In the Properties window, do the following:</span></span>  
  
    |<span data-ttu-id="83f96-169">プロパティ</span><span class="sxs-lookup"><span data-stu-id="83f96-169">Use this</span></span>|<span data-ttu-id="83f96-170">目的</span><span class="sxs-lookup"><span data-stu-id="83f96-170">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="83f96-171">**名前**</span><span class="sxs-lookup"><span data-stu-id="83f96-171">**Name**</span></span>|<span data-ttu-id="83f96-172">型**DeclineRule**です。</span><span class="sxs-lookup"><span data-stu-id="83f96-172">Type **DeclineRule**.</span></span>|  
    |<span data-ttu-id="83f96-173">**[式]**</span><span class="sxs-lookup"><span data-stu-id="83f96-173">**Expression**</span></span>|<span data-ttu-id="83f96-174">省略記号ボタン (**.**)、し、入力`RequestMessage(EAISchemas.PropertySchema.GrandTotal ) > 10000`です。</span><span class="sxs-lookup"><span data-stu-id="83f96-174">Click the ellipses (**…**), and then type `RequestMessage(EAISchemas.PropertySchema.GrandTotal ) > 10000`.</span></span> <span data-ttu-id="83f96-175">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="83f96-175">Click **OK**.</span></span>|  
  
7.  <span data-ttu-id="83f96-176">デザイン画面でクリックして、 **ConstructMessage_1**図形です。</span><span class="sxs-lookup"><span data-stu-id="83f96-176">On the design surface, click the **ConstructMessage_1** shape.</span></span>  
  
8.  <span data-ttu-id="83f96-177">[プロパティ ウィンドウ] で、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="83f96-177">In the Properties window, do the following:</span></span>  
  
    |<span data-ttu-id="83f96-178">プロパティ</span><span class="sxs-lookup"><span data-stu-id="83f96-178">Use this</span></span>|<span data-ttu-id="83f96-179">目的</span><span class="sxs-lookup"><span data-stu-id="83f96-179">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="83f96-180">**名前**</span><span class="sxs-lookup"><span data-stu-id="83f96-180">**Name**</span></span>|<span data-ttu-id="83f96-181">型**ConstructRequestDeclineMessage**です。</span><span class="sxs-lookup"><span data-stu-id="83f96-181">Type **ConstructRequestDeclineMessage**.</span></span>|  
    |<span data-ttu-id="83f96-182">**構築メッセージ**</span><span class="sxs-lookup"><span data-stu-id="83f96-182">**Messages Constructed**</span></span>|<span data-ttu-id="83f96-183">選択**RequestDeclineMessage**です。</span><span class="sxs-lookup"><span data-stu-id="83f96-183">Select **RequestDeclineMessage**.</span></span>|  
  
9. <span data-ttu-id="83f96-184">デザイン画面でクリックして、**変換 _ 1**図形です。</span><span class="sxs-lookup"><span data-stu-id="83f96-184">On the design surface, click the **Transform_1** shape.</span></span>  
  
10. <span data-ttu-id="83f96-185">[プロパティ ウィンドウ] で、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="83f96-185">In the Properties window, do the following:</span></span>  
  
    |<span data-ttu-id="83f96-186">プロパティ</span><span class="sxs-lookup"><span data-stu-id="83f96-186">Use this</span></span>|<span data-ttu-id="83f96-187">目的</span><span class="sxs-lookup"><span data-stu-id="83f96-187">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="83f96-188">**名前**</span><span class="sxs-lookup"><span data-stu-id="83f96-188">**Name**</span></span>|<span data-ttu-id="83f96-189">型**TransformRequestToRequestDeclineMessage**です。</span><span class="sxs-lookup"><span data-stu-id="83f96-189">Type **TransformRequestToRequestDeclineMessage**.</span></span>|  
    |<span data-ttu-id="83f96-190">**マップ名**</span><span class="sxs-lookup"><span data-stu-id="83f96-190">**Map Name**</span></span>|<span data-ttu-id="83f96-191">をクリック**しています.**.</span><span class="sxs-lookup"><span data-stu-id="83f96-191">Click **…**.</span></span> <span data-ttu-id="83f96-192">[変換の構成] で、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="83f96-192">From Transform Configuration, do the following:</span></span><br /><br /> <span data-ttu-id="83f96-193">構成情報の入力</span><span class="sxs-lookup"><span data-stu-id="83f96-193">Enter the configuration information:</span></span><br /><br /> <span data-ttu-id="83f96-194">-**既存のマップ**です。</span><span class="sxs-lookup"><span data-stu-id="83f96-194">- Click **Existing Map**.</span></span><br /><br /> <span data-ttu-id="83f96-195">完全修飾マップ名:</span><span class="sxs-lookup"><span data-stu-id="83f96-195">Fully Qualified Map Name:</span></span><br /><br /> <span data-ttu-id="83f96-196">- **\<参照されたアセンブリから選択 >**です。</span><span class="sxs-lookup"><span data-stu-id="83f96-196">- Select **\<Select from referenced assembly>**.</span></span>  <span data-ttu-id="83f96-197">左側のウィンドウから次のように選択します。 **EAISchemas**です。</span><span class="sxs-lookup"><span data-stu-id="83f96-197">From the left pane, select **EAISchemas**.</span></span>  <span data-ttu-id="83f96-198">右ペインで、[EAISchemas.MapToReqDecline] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="83f96-198">From the right pane, select EAISchemas.MapToReqDecline.</span></span>  <span data-ttu-id="83f96-199">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="83f96-199">Click **OK**.</span></span><br /><br /> <span data-ttu-id="83f96-200">ソース</span><span class="sxs-lookup"><span data-stu-id="83f96-200">Source</span></span><br /><br /> <span data-ttu-id="83f96-201">-RequestMessage</span><span class="sxs-lookup"><span data-stu-id="83f96-201">- RequestMessage</span></span><br /><br /> <span data-ttu-id="83f96-202">転送先</span><span class="sxs-lookup"><span data-stu-id="83f96-202">Destination</span></span><br /><br /> <span data-ttu-id="83f96-203">-RequestDeclineMessage</span><span class="sxs-lookup"><span data-stu-id="83f96-203">- RequestDeclineMessage</span></span>|  
  
11. <span data-ttu-id="83f96-204">デザイン画面でクリックして、 **Send_1**図形です。</span><span class="sxs-lookup"><span data-stu-id="83f96-204">On the design surface, click the **Send_1** shape.</span></span>  
  
12. <span data-ttu-id="83f96-205">[プロパティ ウィンドウ] で、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="83f96-205">In the Properties window, do the following:</span></span>  
  
    |<span data-ttu-id="83f96-206">プロパティ</span><span class="sxs-lookup"><span data-stu-id="83f96-206">Use this</span></span>|<span data-ttu-id="83f96-207">目的</span><span class="sxs-lookup"><span data-stu-id="83f96-207">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="83f96-208">**名前**</span><span class="sxs-lookup"><span data-stu-id="83f96-208">**Name**</span></span>|<span data-ttu-id="83f96-209">型**SendRequestDecline**です。</span><span class="sxs-lookup"><span data-stu-id="83f96-209">Type **SendRequestDecline**.</span></span>|  
    |<span data-ttu-id="83f96-210">**メッセージ**</span><span class="sxs-lookup"><span data-stu-id="83f96-210">**Message**</span></span>|<span data-ttu-id="83f96-211">選択**RequestDeclineMessage**です。</span><span class="sxs-lookup"><span data-stu-id="83f96-211">Select **RequestDeclineMessage**.</span></span>|  
  
13. <span data-ttu-id="83f96-212">デザイン画面でクリックして、 **[send_2]**図形です。</span><span class="sxs-lookup"><span data-stu-id="83f96-212">On the design surface, click the **Send_2** shape.</span></span>  
  
14. <span data-ttu-id="83f96-213">[プロパティ ウィンドウ] で、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="83f96-213">In the Properties window, do the following:</span></span>  
  
    |<span data-ttu-id="83f96-214">プロパティ</span><span class="sxs-lookup"><span data-stu-id="83f96-214">Use this</span></span>|<span data-ttu-id="83f96-215">目的</span><span class="sxs-lookup"><span data-stu-id="83f96-215">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="83f96-216">**名前**</span><span class="sxs-lookup"><span data-stu-id="83f96-216">**Name**</span></span>|<span data-ttu-id="83f96-217">型**SendRequestToERP**です。</span><span class="sxs-lookup"><span data-stu-id="83f96-217">Type **SendRequestToERP**.</span></span>|  
    |<span data-ttu-id="83f96-218">**メッセージ**</span><span class="sxs-lookup"><span data-stu-id="83f96-218">**Message**</span></span>|<span data-ttu-id="83f96-219">選択**RequestMessage**です。</span><span class="sxs-lookup"><span data-stu-id="83f96-219">Select **RequestMessage**.</span></span>|  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="83f96-220">でしただけは何ですか。</span><span class="sxs-lookup"><span data-stu-id="83f96-220">What did I just do?</span></span>  
 <span data-ttu-id="83f96-221">このステップでは、オーケストレーション デザイナーを使用して、ビジネス プロセスを定義しました。</span><span class="sxs-lookup"><span data-stu-id="83f96-221">In this step, you used Orchestration Designer to define your business process.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="83f96-222">次の手順</span><span class="sxs-lookup"><span data-stu-id="83f96-222">Next Steps</span></span>  
 <span data-ttu-id="83f96-223">オーケストレーションに論理ポートを追加する[手順 3: 追加のポートをオーケストレーションに](../core/step-3-add-ports-to-the-orchestration.md)です。</span><span class="sxs-lookup"><span data-stu-id="83f96-223">You add logical ports to the orchestration in [Step 3: Add Ports to the Orchestration](../core/step-3-add-ports-to-the-orchestration.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83f96-224">参照</span><span class="sxs-lookup"><span data-stu-id="83f96-224">See Also</span></span>  
 <span data-ttu-id="83f96-225">[手順 1: EAIOrchestration プロジェクトをソリューションに追加します。](../core/step-1-add-eaiorchestration-project-to-the-solution.md) </span><span class="sxs-lookup"><span data-stu-id="83f96-225">[Step 1: Add EAIOrchestration Project to the Solution](../core/step-1-add-eaiorchestration-project-to-the-solution.md) </span></span>  
 <span data-ttu-id="83f96-226">[手順 3: オーケストレーションのポートを追加します。](../core/step-3-add-ports-to-the-orchestration.md) </span><span class="sxs-lookup"><span data-stu-id="83f96-226">[Step 3: Add Ports to the Orchestration](../core/step-3-add-ports-to-the-orchestration.md) </span></span>  
 [<span data-ttu-id="83f96-227">手順 4: EAIOrchestration プロジェクトをビルドします。</span><span class="sxs-lookup"><span data-stu-id="83f96-227">Step 4: Build the EAIOrchestration Project</span></span>](../core/step-4-build-the-eaiorchestration-project.md)