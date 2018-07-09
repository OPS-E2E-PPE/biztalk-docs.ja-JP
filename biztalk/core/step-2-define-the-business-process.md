---
title: '手順 2: ビジネス プロセスの定義 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b37bd9f1-5ee2-434d-950a-cf12967b6fc2
caps.latest.revision: 49
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 850b8b98764bc782dc62c6ebe792ace2d80ef0a8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998107"
---
# <a name="step-2-define-the-business-process"></a><span data-ttu-id="eb4ba-102">ステップ 2: ビジネス プロセスの定義</span><span class="sxs-lookup"><span data-stu-id="eb4ba-102">Step 2: Define the Business Process</span></span>
<span data-ttu-id="eb4ba-103">![手順 4 2](../adapters-and-accelerators/adapter-oracle-ebs/media/step-2of4.gif "Step_2of4")</span><span class="sxs-lookup"><span data-stu-id="eb4ba-103">![Step 2 of 4](../adapters-and-accelerators/adapter-oracle-ebs/media/step-2of4.gif "Step_2of4")</span></span>  
  
 <span data-ttu-id="eb4ba-104">**所要時間:** 8 分</span><span class="sxs-lookup"><span data-stu-id="eb4ba-104">**Time to complete:** 8 minutes</span></span>  
  
 <span data-ttu-id="eb4ba-105">**目標:** この手順で、ビジネス プロセスを定義するオーケストレーション デザイナーを使用します。</span><span class="sxs-lookup"><span data-stu-id="eb4ba-105">**Objective:** In this step, you use Orchestration Designer to define your business process.</span></span>  
  
 <span data-ttu-id="eb4ba-106">**目的:** オーケストレーションのワークフローを表すし、在庫補充要求を承認するため、会社のビジネス プロセスを自動化します。</span><span class="sxs-lookup"><span data-stu-id="eb4ba-106">**Purpose:** The workflow of the orchestration represents and automates your company's business process for approving inventory replenishment requests.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="eb4ba-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="eb4ba-107">Prerequisites</span></span>  
 <span data-ttu-id="eb4ba-108">このステップを開始する前に、以下の要件を確認してください。</span><span class="sxs-lookup"><span data-stu-id="eb4ba-108">Note the following requirements before you begin this step:</span></span>  
  
-   <span data-ttu-id="eb4ba-109">この手順を開始する前に行う必要があります[手順 1: EAIOrchestration プロジェクトをソリューションに追加](../core/step-1-add-eaiorchestration-project-to-the-solution.md)します。</span><span class="sxs-lookup"><span data-stu-id="eb4ba-109">Before you begin this step you must complete [Step 1: Add EAIOrchestration Project to the Solution](../core/step-1-add-eaiorchestration-project-to-the-solution.md).</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="eb4ba-110">手順</span><span class="sxs-lookup"><span data-stu-id="eb4ba-110">Procedures</span></span>  
 <span data-ttu-id="eb4ba-111">オーケストレーションの開発のための最初の手順は、アクション図形を使用してビジネス プロセスを表すことです。</span><span class="sxs-lookup"><span data-stu-id="eb4ba-111">The first step for developing an orchestration is to use action shapes to represent the business process.</span></span>  
  
#### <a name="to-create-the-eai-business-process-workflow"></a><span data-ttu-id="eb4ba-112">EAI ビジネス プロセスのワークフローを作成するには</span><span class="sxs-lookup"><span data-stu-id="eb4ba-112">To create the EAI business process workflow</span></span>  
  
1. <span data-ttu-id="eb4ba-113">Visual studio で、ソリューション エクスプ ローラーでダブルクリック**EAIProcess.odx**オーケストレーションを開きます。</span><span class="sxs-lookup"><span data-stu-id="eb4ba-113">From Visual Studio, in Solution Explorer, double-click **EAIProcess.odx** to open the orchestration.</span></span>  
  
2. <span data-ttu-id="eb4ba-114">オーケストレーション デザイナで、オーケストレーション ツールボックスからドラッグして、**受信**図形し、の間にドロップ、**開始**(緑色の円) と**エンド**図形 (赤色の八角形)。</span><span class="sxs-lookup"><span data-stu-id="eb4ba-114">In Orchestration Designer, from the orchestration Toolbox, drag the **Receive** shape, and drop it between the **Begin** (green circle) and **End** (red octagon) shapes.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="eb4ba-115">ツールボックスが開かれていない場合、**ビュー**  メニューのをクリックして**ツールボックス**します。</span><span class="sxs-lookup"><span data-stu-id="eb4ba-115">If the Toolbox is not open, in the **View** menu, click **Toolbox**.</span></span> <span data-ttu-id="eb4ba-116">ツールボックスを画面上に固定するには、画鋲のアイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="eb4ba-116">To anchor it on the screen, click the thumbtack icon.</span></span>  
  
3. <span data-ttu-id="eb4ba-117">ツールボックスからドラッグして、**判断**図形、受信図形の下にします。</span><span class="sxs-lookup"><span data-stu-id="eb4ba-117">From the toolbox, drag the **Decide** shape beneath the Receive shape.</span></span>  
  
4. <span data-ttu-id="eb4ba-118">ツールボックスからドラッグして、**変換**決定図形の左の分岐に図形。</span><span class="sxs-lookup"><span data-stu-id="eb4ba-118">From the toolbox, drag the **Transform** shape to the left branch of the Decide shape.</span></span> <span data-ttu-id="eb4ba-119">変換図形は メッセージの構築図形で入れ子になっています。</span><span class="sxs-lookup"><span data-stu-id="eb4ba-119">The Transform shape is nested inside the Construct Message shape.</span></span>  
  
5. <span data-ttu-id="eb4ba-120">ツールボックスからドラッグして、**送信**図形、変換図形の下にします。</span><span class="sxs-lookup"><span data-stu-id="eb4ba-120">From the toolbox, drag the **Send** shape beneath the Transform shape.</span></span>  
  
6. <span data-ttu-id="eb4ba-121">ツールボックスからドラッグして、**送信**決定図形の右の分岐に図形。</span><span class="sxs-lookup"><span data-stu-id="eb4ba-121">From the toolbox, drag the **Send** shape to the right branch of the Decide shape.</span></span>  <span data-ttu-id="eb4ba-122">操作図形を追加すると、オーケストレーションは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="eb4ba-122">The orchestration looks like the following after you added the action shapes:</span></span>  
  
    <span data-ttu-id="eb4ba-123">![EAI プロセス](../core/media/eaiprocess.gif "EAIProcess")</span><span class="sxs-lookup"><span data-stu-id="eb4ba-123">![EAI process](../core/media/eaiprocess.gif "EAIProcess")</span></span>  
  
   <span data-ttu-id="eb4ba-124">次の手順では、メッセージ変数を定義します。</span><span class="sxs-lookup"><span data-stu-id="eb4ba-124">The next step is to define message variables.</span></span>  <span data-ttu-id="eb4ba-125">操作によっては、メッセージ プロパティを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="eb4ba-125">Several action shapes have a message property that needs to be specified.</span></span>  
  
#### <a name="to-define-message-variables"></a><span data-ttu-id="eb4ba-126">メッセージ変数を定義するには</span><span class="sxs-lookup"><span data-stu-id="eb4ba-126">To define message variables</span></span>  
  
1.  <span data-ttu-id="eb4ba-127">Visual studio で、をクリックして、**ビュー**  メニューのをクリックして**その他の Windows**、順にクリックします**オーケストレーション**します。</span><span class="sxs-lookup"><span data-stu-id="eb4ba-127">From Visual Studio, click the **View** menu, click **Other Windows**, and then click **Orchestration View**.</span></span>  
  
2.  <span data-ttu-id="eb4ba-128">オーケストレーションの種類を右クリックして**メッセージ**、 をクリックし、**新しいメッセージ**します。</span><span class="sxs-lookup"><span data-stu-id="eb4ba-128">From Orchestration View, right-click **Messages**, and then click **New Message**.</span></span>  
  
3.  <span data-ttu-id="eb4ba-129">[プロパティ ウィンドウ] で、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="eb4ba-129">In the Properties window, do the following:</span></span>  
  
    |<span data-ttu-id="eb4ba-130">プロパティ</span><span class="sxs-lookup"><span data-stu-id="eb4ba-130">Use this</span></span>|<span data-ttu-id="eb4ba-131">目的</span><span class="sxs-lookup"><span data-stu-id="eb4ba-131">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="eb4ba-132">**[Identifier]**</span><span class="sxs-lookup"><span data-stu-id="eb4ba-132">**Identifier**</span></span>|<span data-ttu-id="eb4ba-133">型**RequestMessage**します。</span><span class="sxs-lookup"><span data-stu-id="eb4ba-133">Type **RequestMessage**.</span></span>|  
    |<span data-ttu-id="eb4ba-134">**メッセージの種類**</span><span class="sxs-lookup"><span data-stu-id="eb4ba-134">**Message Type**</span></span>|<span data-ttu-id="eb4ba-135">をクリックして**スキーマ**、 をクリックし、 **\<参照されたアセンブリから選択しています.\>**.</span><span class="sxs-lookup"><span data-stu-id="eb4ba-135">Click **Schemas**, and then click **\<Select from referenced assembly …\>**.</span></span> <span data-ttu-id="eb4ba-136">成果物の種類の選択 ウィンドウで、 **EAISchemas**、 をクリックし、**要求**します。</span><span class="sxs-lookup"><span data-stu-id="eb4ba-136">From the Select Artifact Type window, click **EAISchemas**, and then click **Request**.</span></span> <span data-ttu-id="eb4ba-137">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="eb4ba-137">Click **OK**</span></span>|  
  
4.  <span data-ttu-id="eb4ba-138">オーケストレーションの種類を右クリックして**メッセージ**、 をクリックし、**新しいメッセージ**します。</span><span class="sxs-lookup"><span data-stu-id="eb4ba-138">From Orchestration View, right-click **Messages**, and then click **New Message**.</span></span>  
  
5.  <span data-ttu-id="eb4ba-139">[プロパティ ウィンドウ] で、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="eb4ba-139">In the Properties window, do the following:</span></span>  
  
    |<span data-ttu-id="eb4ba-140">プロパティ</span><span class="sxs-lookup"><span data-stu-id="eb4ba-140">Use this</span></span>|<span data-ttu-id="eb4ba-141">目的</span><span class="sxs-lookup"><span data-stu-id="eb4ba-141">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="eb4ba-142">**[Identifier]**</span><span class="sxs-lookup"><span data-stu-id="eb4ba-142">**Identifier**</span></span>|<span data-ttu-id="eb4ba-143">型**RequestDeclineMessage**します。</span><span class="sxs-lookup"><span data-stu-id="eb4ba-143">Type **RequestDeclineMessage**.</span></span>|  
    |<span data-ttu-id="eb4ba-144">**メッセージの種類**</span><span class="sxs-lookup"><span data-stu-id="eb4ba-144">**Message Type**</span></span>|<span data-ttu-id="eb4ba-145">をクリックして**スキーマ**、 をクリックし、 **\<参照されたアセンブリから選択しています.\>**.</span><span class="sxs-lookup"><span data-stu-id="eb4ba-145">Click **Schemas**, and then click **\<Select from referenced assembly …\>**.</span></span> <span data-ttu-id="eb4ba-146">アイテムの種類 ウィンドウで、 **EAISchemas**、 をクリックし、 **RequestDecline**します。</span><span class="sxs-lookup"><span data-stu-id="eb4ba-146">From the Select Artifact Type window, click **EAISchemas**, and then click **RequestDecline**.</span></span> <span data-ttu-id="eb4ba-147">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="eb4ba-147">Click **OK**</span></span>|  
  
#### <a name="to-configure-the-properties-of-the-shapes"></a><span data-ttu-id="eb4ba-148">図形のプロパティを構成するには</span><span class="sxs-lookup"><span data-stu-id="eb4ba-148">To configure the properties of the shapes</span></span>  
  
1.  <span data-ttu-id="eb4ba-149">デザイン画面でクリックして、**受信**図形を選択します。</span><span class="sxs-lookup"><span data-stu-id="eb4ba-149">On the design surface, click the **Receive** shape to select it.</span></span>  
  
2.  <span data-ttu-id="eb4ba-150">[プロパティ ウィンドウ] で、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="eb4ba-150">In the Properties window, do the following:</span></span>  
  
    |<span data-ttu-id="eb4ba-151">プロパティ</span><span class="sxs-lookup"><span data-stu-id="eb4ba-151">Use this</span></span>|<span data-ttu-id="eb4ba-152">目的</span><span class="sxs-lookup"><span data-stu-id="eb4ba-152">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="eb4ba-153">**名前**</span><span class="sxs-lookup"><span data-stu-id="eb4ba-153">**Name**</span></span>|<span data-ttu-id="eb4ba-154">型**ReceiveRequest**します。</span><span class="sxs-lookup"><span data-stu-id="eb4ba-154">Type **ReceiveRequest**.</span></span>|  
    |<span data-ttu-id="eb4ba-155">**メッセージ**</span><span class="sxs-lookup"><span data-stu-id="eb4ba-155">**Message**</span></span>|<span data-ttu-id="eb4ba-156">選択**RequestMessage**します。</span><span class="sxs-lookup"><span data-stu-id="eb4ba-156">Select **RequestMessage**.</span></span>|  
    |<span data-ttu-id="eb4ba-157">**Activate**</span><span class="sxs-lookup"><span data-stu-id="eb4ba-157">**Activate**</span></span>|<span data-ttu-id="eb4ba-158">ドロップダウン リストから選択**True**します。</span><span class="sxs-lookup"><span data-stu-id="eb4ba-158">From the drop-down list, select **True**.</span></span>|  
  
    > [!NOTE]
    >  <span data-ttu-id="eb4ba-159">プロパティ ウィンドウが開いていない場合、**ビュー**  メニューのをクリックして**プロパティ ウィンドウ**します。</span><span class="sxs-lookup"><span data-stu-id="eb4ba-159">If the Property window is not open, in the **View** menu, click **Properties Window**.</span></span>  
  
3.  <span data-ttu-id="eb4ba-160">デザイン画面でクリックして、**判断**図形。</span><span class="sxs-lookup"><span data-stu-id="eb4ba-160">On the design surface, click the **Decide** shape.</span></span>  
  
4.  <span data-ttu-id="eb4ba-161">[プロパティ ウィンドウ] で、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="eb4ba-161">In the Properties window, do the following:</span></span>  
  
    |<span data-ttu-id="eb4ba-162">プロパティ</span><span class="sxs-lookup"><span data-stu-id="eb4ba-162">Use this</span></span>|<span data-ttu-id="eb4ba-163">目的</span><span class="sxs-lookup"><span data-stu-id="eb4ba-163">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="eb4ba-164">**名前**</span><span class="sxs-lookup"><span data-stu-id="eb4ba-164">**Name**</span></span>|<span data-ttu-id="eb4ba-165">型**CheckGrandTotal**します。</span><span class="sxs-lookup"><span data-stu-id="eb4ba-165">Type **CheckGrandTotal**.</span></span>|  
  
    > [!NOTE]
    >  <span data-ttu-id="eb4ba-166">プロパティ ウィンドウが開いていない場合、**ビュー**  メニューのをクリックして**プロパティ ウィンドウ**します。</span><span class="sxs-lookup"><span data-stu-id="eb4ba-166">If the Property window is not open, in the **View** menu, click **Properties Window**.</span></span>  
  
5.  <span data-ttu-id="eb4ba-167">デザイン画面でクリックして、 **[rule_1]** 図形。</span><span class="sxs-lookup"><span data-stu-id="eb4ba-167">On the design surface, click the **Rule_1** shape.</span></span>  
  
6.  <span data-ttu-id="eb4ba-168">[プロパティ ウィンドウ] で、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="eb4ba-168">In the Properties window, do the following:</span></span>  
  
    |<span data-ttu-id="eb4ba-169">プロパティ</span><span class="sxs-lookup"><span data-stu-id="eb4ba-169">Use this</span></span>|<span data-ttu-id="eb4ba-170">目的</span><span class="sxs-lookup"><span data-stu-id="eb4ba-170">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="eb4ba-171">**名前**</span><span class="sxs-lookup"><span data-stu-id="eb4ba-171">**Name**</span></span>|<span data-ttu-id="eb4ba-172">型**DeclineRule**します。</span><span class="sxs-lookup"><span data-stu-id="eb4ba-172">Type **DeclineRule**.</span></span>|  
    |<span data-ttu-id="eb4ba-173">**[式]**</span><span class="sxs-lookup"><span data-stu-id="eb4ba-173">**Expression**</span></span>|<span data-ttu-id="eb4ba-174">省略記号をクリックします (**.**)、し、入力`RequestMessage(EAISchemas.PropertySchema.GrandTotal ) > 10000`します。</span><span class="sxs-lookup"><span data-stu-id="eb4ba-174">Click the ellipses (**…**), and then type `RequestMessage(EAISchemas.PropertySchema.GrandTotal ) > 10000`.</span></span> <span data-ttu-id="eb4ba-175">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="eb4ba-175">Click **OK**.</span></span>|  
  
7.  <span data-ttu-id="eb4ba-176">デザイン画面でクリックして、 **ConstructMessage_1**図形。</span><span class="sxs-lookup"><span data-stu-id="eb4ba-176">On the design surface, click the **ConstructMessage_1** shape.</span></span>  
  
8.  <span data-ttu-id="eb4ba-177">[プロパティ ウィンドウ] で、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="eb4ba-177">In the Properties window, do the following:</span></span>  
  
    |<span data-ttu-id="eb4ba-178">プロパティ</span><span class="sxs-lookup"><span data-stu-id="eb4ba-178">Use this</span></span>|<span data-ttu-id="eb4ba-179">目的</span><span class="sxs-lookup"><span data-stu-id="eb4ba-179">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="eb4ba-180">**名前**</span><span class="sxs-lookup"><span data-stu-id="eb4ba-180">**Name**</span></span>|<span data-ttu-id="eb4ba-181">型**ConstructRequestDeclineMessage**します。</span><span class="sxs-lookup"><span data-stu-id="eb4ba-181">Type **ConstructRequestDeclineMessage**.</span></span>|  
    |<span data-ttu-id="eb4ba-182">**構築メッセージ**</span><span class="sxs-lookup"><span data-stu-id="eb4ba-182">**Messages Constructed**</span></span>|<span data-ttu-id="eb4ba-183">選択**RequestDeclineMessage**します。</span><span class="sxs-lookup"><span data-stu-id="eb4ba-183">Select **RequestDeclineMessage**.</span></span>|  
  
9. <span data-ttu-id="eb4ba-184">デザイン画面でクリックして、**変換 _ 1**図形。</span><span class="sxs-lookup"><span data-stu-id="eb4ba-184">On the design surface, click the **Transform_1** shape.</span></span>  
  
10. <span data-ttu-id="eb4ba-185">[プロパティ ウィンドウ] で、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="eb4ba-185">In the Properties window, do the following:</span></span>  
  
    |<span data-ttu-id="eb4ba-186">プロパティ</span><span class="sxs-lookup"><span data-stu-id="eb4ba-186">Use this</span></span>|<span data-ttu-id="eb4ba-187">目的</span><span class="sxs-lookup"><span data-stu-id="eb4ba-187">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="eb4ba-188">**名前**</span><span class="sxs-lookup"><span data-stu-id="eb4ba-188">**Name**</span></span>|<span data-ttu-id="eb4ba-189">型**TransformRequestToRequestDeclineMessage**します。</span><span class="sxs-lookup"><span data-stu-id="eb4ba-189">Type **TransformRequestToRequestDeclineMessage**.</span></span>|  
    |<span data-ttu-id="eb4ba-190">**マップ名**</span><span class="sxs-lookup"><span data-stu-id="eb4ba-190">**Map Name**</span></span>|<span data-ttu-id="eb4ba-191">クリックして **.**.</span><span class="sxs-lookup"><span data-stu-id="eb4ba-191">Click **…**.</span></span> <span data-ttu-id="eb4ba-192">[変換の構成] で、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="eb4ba-192">From Transform Configuration, do the following:</span></span><br /><br /> <span data-ttu-id="eb4ba-193">構成情報の入力</span><span class="sxs-lookup"><span data-stu-id="eb4ba-193">Enter the configuration information:</span></span><br /><br /> <span data-ttu-id="eb4ba-194">-**既存のマップ**します。</span><span class="sxs-lookup"><span data-stu-id="eb4ba-194">- Click **Existing Map**.</span></span><br /><br /> <span data-ttu-id="eb4ba-195">完全修飾マップ名:</span><span class="sxs-lookup"><span data-stu-id="eb4ba-195">Fully Qualified Map Name:</span></span><br /><br /> <span data-ttu-id="eb4ba-196">- **\<参照されたアセンブリから選択\>** します。</span><span class="sxs-lookup"><span data-stu-id="eb4ba-196">- Select **\<Select from referenced assembly\>**.</span></span>  <span data-ttu-id="eb4ba-197">左側のウィンドウから次のように選択します。 **EAISchemas**します。</span><span class="sxs-lookup"><span data-stu-id="eb4ba-197">From the left pane, select **EAISchemas**.</span></span>  <span data-ttu-id="eb4ba-198">右ペインで、[EAISchemas.MapToReqDecline] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="eb4ba-198">From the right pane, select EAISchemas.MapToReqDecline.</span></span>  <span data-ttu-id="eb4ba-199">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="eb4ba-199">Click **OK**.</span></span><br /><br /> <span data-ttu-id="eb4ba-200">Source</span><span class="sxs-lookup"><span data-stu-id="eb4ba-200">Source</span></span><br /><br /> <span data-ttu-id="eb4ba-201">-RequestMessage</span><span class="sxs-lookup"><span data-stu-id="eb4ba-201">- RequestMessage</span></span><br /><br /> <span data-ttu-id="eb4ba-202">[Destination]</span><span class="sxs-lookup"><span data-stu-id="eb4ba-202">Destination</span></span><br /><br /> <span data-ttu-id="eb4ba-203">-RequestDeclineMessage</span><span class="sxs-lookup"><span data-stu-id="eb4ba-203">- RequestDeclineMessage</span></span>|  
  
11. <span data-ttu-id="eb4ba-204">デザイン画面でクリックして、 **Send_1**図形。</span><span class="sxs-lookup"><span data-stu-id="eb4ba-204">On the design surface, click the **Send_1** shape.</span></span>  
  
12. <span data-ttu-id="eb4ba-205">[プロパティ ウィンドウ] で、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="eb4ba-205">In the Properties window, do the following:</span></span>  
  
    |<span data-ttu-id="eb4ba-206">プロパティ</span><span class="sxs-lookup"><span data-stu-id="eb4ba-206">Use this</span></span>|<span data-ttu-id="eb4ba-207">目的</span><span class="sxs-lookup"><span data-stu-id="eb4ba-207">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="eb4ba-208">**名前**</span><span class="sxs-lookup"><span data-stu-id="eb4ba-208">**Name**</span></span>|<span data-ttu-id="eb4ba-209">型**SendRequestDecline**します。</span><span class="sxs-lookup"><span data-stu-id="eb4ba-209">Type **SendRequestDecline**.</span></span>|  
    |<span data-ttu-id="eb4ba-210">**メッセージ**</span><span class="sxs-lookup"><span data-stu-id="eb4ba-210">**Message**</span></span>|<span data-ttu-id="eb4ba-211">選択**RequestDeclineMessage**します。</span><span class="sxs-lookup"><span data-stu-id="eb4ba-211">Select **RequestDeclineMessage**.</span></span>|  
  
13. <span data-ttu-id="eb4ba-212">デザイン画面でクリックして、 **[send_2]** 図形。</span><span class="sxs-lookup"><span data-stu-id="eb4ba-212">On the design surface, click the **Send_2** shape.</span></span>  
  
14. <span data-ttu-id="eb4ba-213">[プロパティ ウィンドウ] で、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="eb4ba-213">In the Properties window, do the following:</span></span>  
  
    |<span data-ttu-id="eb4ba-214">プロパティ</span><span class="sxs-lookup"><span data-stu-id="eb4ba-214">Use this</span></span>|<span data-ttu-id="eb4ba-215">目的</span><span class="sxs-lookup"><span data-stu-id="eb4ba-215">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="eb4ba-216">**名前**</span><span class="sxs-lookup"><span data-stu-id="eb4ba-216">**Name**</span></span>|<span data-ttu-id="eb4ba-217">型**SendRequestToERP**します。</span><span class="sxs-lookup"><span data-stu-id="eb4ba-217">Type **SendRequestToERP**.</span></span>|  
    |<span data-ttu-id="eb4ba-218">**メッセージ**</span><span class="sxs-lookup"><span data-stu-id="eb4ba-218">**Message**</span></span>|<span data-ttu-id="eb4ba-219">選択**RequestMessage**します。</span><span class="sxs-lookup"><span data-stu-id="eb4ba-219">Select **RequestMessage**.</span></span>|  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="eb4ba-220">でしただけ何か。</span><span class="sxs-lookup"><span data-stu-id="eb4ba-220">What did I just do?</span></span>  
 <span data-ttu-id="eb4ba-221">このステップでは、オーケストレーション デザイナーを使用して、ビジネス プロセスを定義しました。</span><span class="sxs-lookup"><span data-stu-id="eb4ba-221">In this step, you used Orchestration Designer to define your business process.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="eb4ba-222">次の手順</span><span class="sxs-lookup"><span data-stu-id="eb4ba-222">Next Steps</span></span>  
 <span data-ttu-id="eb4ba-223">では、オーケストレーションに論理ポートを追加する[手順 3: 追加のポートをオーケストレーションに](../core/step-3-add-ports-to-the-orchestration.md)。</span><span class="sxs-lookup"><span data-stu-id="eb4ba-223">You add logical ports to the orchestration in [Step 3: Add Ports to the Orchestration](../core/step-3-add-ports-to-the-orchestration.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb4ba-224">参照</span><span class="sxs-lookup"><span data-stu-id="eb4ba-224">See Also</span></span>  
 <span data-ttu-id="eb4ba-225">[手順 1: EAIOrchestration プロジェクトをソリューションに追加します。](../core/step-1-add-eaiorchestration-project-to-the-solution.md) </span><span class="sxs-lookup"><span data-stu-id="eb4ba-225">[Step 1: Add EAIOrchestration Project to the Solution](../core/step-1-add-eaiorchestration-project-to-the-solution.md) </span></span>  
 <span data-ttu-id="eb4ba-226">[手順 3: オーケストレーションのポートを追加します。](../core/step-3-add-ports-to-the-orchestration.md) </span><span class="sxs-lookup"><span data-stu-id="eb4ba-226">[Step 3: Add Ports to the Orchestration](../core/step-3-add-ports-to-the-orchestration.md) </span></span>  
 [<span data-ttu-id="eb4ba-227">手順 4: EAIOrchestration プロジェクトのビルド</span><span class="sxs-lookup"><span data-stu-id="eb4ba-227">Step 4: Build the EAIOrchestration Project</span></span>](../core/step-4-build-the-eaiorchestration-project.md)