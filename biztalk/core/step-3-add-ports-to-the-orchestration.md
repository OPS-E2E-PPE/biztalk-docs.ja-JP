---
title: '手順 3: オーケストレーションのポートの追加 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 245df16e-d327-4c79-be85-004134d5ea6f
caps.latest.revision: 45
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9b42c91be94663f1061d3bbda31267db21988157
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968619"
---
# <a name="step-3-add-ports-to-the-orchestration"></a><span data-ttu-id="43676-102">ステップ 3: オーケストレーションへのポートの追加</span><span class="sxs-lookup"><span data-stu-id="43676-102">Step 3: Add Ports to the Orchestration</span></span>
<span data-ttu-id="43676-103">![手順 4 の 3](../adapters-and-accelerators/adapter-oracle-ebs/media/step-3of4.gif "Step_3of4")</span><span class="sxs-lookup"><span data-stu-id="43676-103">![Step 3 of 4](../adapters-and-accelerators/adapter-oracle-ebs/media/step-3of4.gif "Step_3of4")</span></span>  
  
 <span data-ttu-id="43676-104">**所要時間:** 10 分</span><span class="sxs-lookup"><span data-stu-id="43676-104">**Time to complete:** 10 minutes</span></span>  
  
 <span data-ttu-id="43676-105">**目標:** ここでは、EAIProcess オーケストレーションに 3 つのポートを追加およびそれらを構成します。</span><span class="sxs-lookup"><span data-stu-id="43676-105">**Objective:** In this step, you add three ports to the EAIProcess orchestration and configure them.</span></span>  
  
 <span data-ttu-id="43676-106">**目的:** ポートをオーケストレーションはメッセージを送信し、他のビジネス プロセスからメッセージを受信する方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="43676-106">**Purpose:** Ports specify how your orchestration will send messages to and receive messages from other business processes.</span></span> <span data-ttu-id="43676-107">各ポートは、種類、方向、バインドを保持しています。これらの組み合わせによって、通信方向、通信方式、メッセージの送信先場所と送信元場所、および通信の実行方法が決まります。</span><span class="sxs-lookup"><span data-stu-id="43676-107">Each port has a type, a direction, and a binding, which together determine the direction of communication, the pattern of communication, the location to or from which the message is sent or received, and how the communication takes place.</span></span> <span data-ttu-id="43676-108">このステップで作成および構成する 3 つのポートには、それぞれ次の役割があります。</span><span class="sxs-lookup"><span data-stu-id="43676-108">The three ports you create and configure in this step fulfill the following roles:</span></span>  
  
- <span data-ttu-id="43676-109">**ReceiveRequestPort**倉庫から在庫補充要求メッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="43676-109">**ReceiveRequestPort** receives inventory replenishment request messages from the warehouse.</span></span>  
  
- <span data-ttu-id="43676-110">**SendToERP**要求メッセージを ERP システムに転送します。</span><span class="sxs-lookup"><span data-stu-id="43676-110">**SendToERP** forwards the request messages to the ERP system.</span></span>  
  
- <span data-ttu-id="43676-111">**SendDeclinePort**要求拒否メッセージを倉庫に返送します。</span><span class="sxs-lookup"><span data-stu-id="43676-111">**SendDeclinePort** sends request decline messages back to the warehouse.</span></span>  
  
  <span data-ttu-id="43676-112">詳細については、次を参照してください。[オーケストレーションで使用するポート](../core/using-ports-in-orchestrations.md)します。</span><span class="sxs-lookup"><span data-stu-id="43676-112">For more information, see [Using Ports in Orchestrations](../core/using-ports-in-orchestrations.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="43676-113">前提条件</span><span class="sxs-lookup"><span data-stu-id="43676-113">Prerequisites</span></span>  
 <span data-ttu-id="43676-114">このステップを開始する前に、以下の要件を確認してください。</span><span class="sxs-lookup"><span data-stu-id="43676-114">Note the following requirements before you begin this step:</span></span>  
  
-   <span data-ttu-id="43676-115">この手順を開始する前に行う必要があります[手順 2: ビジネス プロセスの定義](../core/step-2-define-the-business-process.md)します。</span><span class="sxs-lookup"><span data-stu-id="43676-115">Before you begin this step you must complete [Step 2: Define the Business Process](../core/step-2-define-the-business-process.md).</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="43676-116">手順</span><span class="sxs-lookup"><span data-stu-id="43676-116">Procedures</span></span>  
  
#### <a name="to-create-and-configure-receiverequestport"></a><span data-ttu-id="43676-117">ReceiveRequestPort を作成および構成するには</span><span class="sxs-lookup"><span data-stu-id="43676-117">To create and configure ReceiveRequestPort</span></span>  
  
1.  <span data-ttu-id="43676-118">ソリューション エクスプ ローラーでダブルクリック**EAIProcess.odx**します。</span><span class="sxs-lookup"><span data-stu-id="43676-118">In Solution Explorer, double-click **EAIProcess.odx**.</span></span>  
  
2.  <span data-ttu-id="43676-119">オーケストレーション デザイナで、オーケストレーション ツールボックスからドラッグして、**ポート**図形を左側にある**ポート画面**並列に、 **ReceiveRequest**図形。</span><span class="sxs-lookup"><span data-stu-id="43676-119">In Orchestration Designer, from the orchestration Toolbox, drag the **Port** shape to the left-side **Port Surface**, parallel to the **ReceiveRequest** shape.</span></span> <span data-ttu-id="43676-120">ポート構成ウィザードが自動的に起動します。</span><span class="sxs-lookup"><span data-stu-id="43676-120">The Port Configuration Wizard starts automatically.</span></span>  
  
3.  <span data-ttu-id="43676-121">**[ポート構成ウィザードへようこそ]** ページで、 **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="43676-121">On the **Welcome to the Port Configuration Wizard** page, click **Next**.</span></span>  
  
4.  <span data-ttu-id="43676-122">**ポートのプロパティ** ページで、以下を実行してをクリックし、**次**。</span><span class="sxs-lookup"><span data-stu-id="43676-122">On the **Port Properties** page, do the following, and then click **Next**.</span></span>  
  
    |<span data-ttu-id="43676-123">プロパティ</span><span class="sxs-lookup"><span data-stu-id="43676-123">Use this</span></span>|<span data-ttu-id="43676-124">目的</span><span class="sxs-lookup"><span data-stu-id="43676-124">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="43676-125">**名前**</span><span class="sxs-lookup"><span data-stu-id="43676-125">**Name**</span></span>|<span data-ttu-id="43676-126">型**ReceiveRequestPort**します。</span><span class="sxs-lookup"><span data-stu-id="43676-126">Type **ReceiveRequestPort**.</span></span>|  
  
5.  <span data-ttu-id="43676-127">**ポートの種類を選択します。**  ページで、以下を実行して順にクリックします**次**します。</span><span class="sxs-lookup"><span data-stu-id="43676-127">On the **Select a Port Type** page, do the following, and then click **Next**.</span></span>  
  
    |<span data-ttu-id="43676-128">プロパティ</span><span class="sxs-lookup"><span data-stu-id="43676-128">Use this</span></span>|<span data-ttu-id="43676-129">目的</span><span class="sxs-lookup"><span data-stu-id="43676-129">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="43676-130">**このポートに使用するポートの種類を選択します。**</span><span class="sxs-lookup"><span data-stu-id="43676-130">**Select the port type to be used for this port**</span></span>|<span data-ttu-id="43676-131">選択、**新しいポートの種類を作成する**オプション。</span><span class="sxs-lookup"><span data-stu-id="43676-131">Select the **Create a new Port Type** option.</span></span>|  
    |<span data-ttu-id="43676-132">**ポートの種類名:**</span><span class="sxs-lookup"><span data-stu-id="43676-132">**Port Type Name:**</span></span>|<span data-ttu-id="43676-133">型**ReceiveRequestPortType**します。</span><span class="sxs-lookup"><span data-stu-id="43676-133">Type **ReceiveRequestPortType**.</span></span>|  
    |<span data-ttu-id="43676-134">**通信方式**</span><span class="sxs-lookup"><span data-stu-id="43676-134">**Communication Pattern**</span></span>|<span data-ttu-id="43676-135">選択**一方向**します。</span><span class="sxs-lookup"><span data-stu-id="43676-135">Select **One-Way**.</span></span>|  
    |<span data-ttu-id="43676-136">**アクセスの制限**</span><span class="sxs-lookup"><span data-stu-id="43676-136">**Access Restrictions**</span></span>|<span data-ttu-id="43676-137">選択**内部 - このプロジェクト限定**します。</span><span class="sxs-lookup"><span data-stu-id="43676-137">Select **Internal - limited to this project**.</span></span>|  
  
6.  <span data-ttu-id="43676-138">**ポートのバインド** ページで、以下を実行してをクリックし、**次**します。</span><span class="sxs-lookup"><span data-stu-id="43676-138">On the **Port Binding** page, do the following, and then click **Next**.</span></span>  
  
    |<span data-ttu-id="43676-139">プロパティ</span><span class="sxs-lookup"><span data-stu-id="43676-139">Use this</span></span>|<span data-ttu-id="43676-140">目的</span><span class="sxs-lookup"><span data-stu-id="43676-140">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="43676-141">**ポートの通信方向**</span><span class="sxs-lookup"><span data-stu-id="43676-141">**Port direction of communication**</span></span>|<span data-ttu-id="43676-142">選択**常にこのポートでメッセージを受信**します。</span><span class="sxs-lookup"><span data-stu-id="43676-142">Select **I'll always be receiving messages on this port**.</span></span>|  
    |<span data-ttu-id="43676-143">**ポートのバインド**</span><span class="sxs-lookup"><span data-stu-id="43676-143">**Port binding**</span></span>|<span data-ttu-id="43676-144">選択から**後で指定する**します。</span><span class="sxs-lookup"><span data-stu-id="43676-144">From select **Specify later**.</span></span>|  
  
7.  <span data-ttu-id="43676-145">**ポート ウィザードの完了**] ページで [**完了**します。</span><span class="sxs-lookup"><span data-stu-id="43676-145">On the **Completing the Port Wizard** page, click **Finish**.</span></span>  
  
#### <a name="to-create-and-configure-senddeclineport"></a><span data-ttu-id="43676-146">SendDeclinePort を作成および構成するには</span><span class="sxs-lookup"><span data-stu-id="43676-146">To create and configure SendDeclinePort</span></span>  
  
1.  <span data-ttu-id="43676-147">オーケストレーション ツールボックスからドラッグして、**ポート**図形を左側にある**ポート画面**並列に、 **SendRequestDecline**図形。</span><span class="sxs-lookup"><span data-stu-id="43676-147">From the orchestration Toolbox, drag the **Port** shape to the left-side **Port Surface**, parallel to the **SendRequestDecline** shape.</span></span>  
  
2.  <span data-ttu-id="43676-148">次の表の情報を使用して、作成、 **SendDeclinePort**ポートを送信します。</span><span class="sxs-lookup"><span data-stu-id="43676-148">Use the information in the following table to create the **SendDeclinePort** send port.</span></span>  
  
    |<span data-ttu-id="43676-149">プロパティ</span><span class="sxs-lookup"><span data-stu-id="43676-149">Property</span></span>|<span data-ttu-id="43676-150">値</span><span class="sxs-lookup"><span data-stu-id="43676-150">Value</span></span>|  
    |--------------|-----------|  
    |<span data-ttu-id="43676-151">**名前**</span><span class="sxs-lookup"><span data-stu-id="43676-151">**Name**</span></span>|<span data-ttu-id="43676-152">型**SendDeclinePort**します。</span><span class="sxs-lookup"><span data-stu-id="43676-152">Type **SendDeclinePort**.</span></span>|  
    |<span data-ttu-id="43676-153">**このポートに使用するポートの種類を選択します。**</span><span class="sxs-lookup"><span data-stu-id="43676-153">**Select the port type to be used for this port**</span></span>|<span data-ttu-id="43676-154">選択**新しいポートの種類を作成する**します。</span><span class="sxs-lookup"><span data-stu-id="43676-154">Select **Create a new Port Type**.</span></span>|  
    |<span data-ttu-id="43676-155">**ポートの種類名**</span><span class="sxs-lookup"><span data-stu-id="43676-155">**Port Type Name**</span></span>|<span data-ttu-id="43676-156">型**SendDeclinePortType**します。</span><span class="sxs-lookup"><span data-stu-id="43676-156">Type **SendDeclinePortType**.</span></span>|  
    |<span data-ttu-id="43676-157">**通信方式**</span><span class="sxs-lookup"><span data-stu-id="43676-157">**Communication Pattern**</span></span>|<span data-ttu-id="43676-158">選択**一方向**します。</span><span class="sxs-lookup"><span data-stu-id="43676-158">Select **One-Way**.</span></span>|  
    |<span data-ttu-id="43676-159">**アクセスの制限**</span><span class="sxs-lookup"><span data-stu-id="43676-159">**Access Restrictions**</span></span>|<span data-ttu-id="43676-160">選択**内部 - このプロジェクト限定**します。</span><span class="sxs-lookup"><span data-stu-id="43676-160">Select **Internal - limited to this project**.</span></span>|  
    |<span data-ttu-id="43676-161">**ポートの通信方向**</span><span class="sxs-lookup"><span data-stu-id="43676-161">**Port direction of communication**</span></span>|<span data-ttu-id="43676-162">ドロップダウン リストから選択**は常にメッセージを送信しますこのポートで**します。</span><span class="sxs-lookup"><span data-stu-id="43676-162">From the drop-down list, select **I'll always be sending messages on this port**.</span></span>|  
    |<span data-ttu-id="43676-163">**ポートのバインド**</span><span class="sxs-lookup"><span data-stu-id="43676-163">**Port bindings**</span></span>|<span data-ttu-id="43676-164">ドロップダウン リストから選択**後で指定する**します。</span><span class="sxs-lookup"><span data-stu-id="43676-164">From the drop-down list, select **Specify later**.</span></span>|  
  
#### <a name="to-create-and-configure-sendtoerpport"></a><span data-ttu-id="43676-165">SendToERPPort を作成および構成するには</span><span class="sxs-lookup"><span data-stu-id="43676-165">To create and configure SendToERPPort</span></span>  
  
1.  <span data-ttu-id="43676-166">オーケストレーション ツールボックスからドラッグして、**ポート**図形を右側にある**ポート画面**並列に、 **SendToERP**図形。</span><span class="sxs-lookup"><span data-stu-id="43676-166">From the orchestration Toolbox, drag the **Port** shape to the right-side **Port Surface**, parallel to the **SendToERP** shape.</span></span>  
  
2.  <span data-ttu-id="43676-167">次の表に、情報を使用して、ポート構成ウィザードを完了、 **SendToERP**ポートを送信します。</span><span class="sxs-lookup"><span data-stu-id="43676-167">Use the information in the following table to complete the Port Configuration Wizard for the **SendToERP** send port.</span></span>  
  
    |<span data-ttu-id="43676-168">プロパティ</span><span class="sxs-lookup"><span data-stu-id="43676-168">Property</span></span>|<span data-ttu-id="43676-169">値</span><span class="sxs-lookup"><span data-stu-id="43676-169">Value</span></span>|  
    |--------------|-----------|  
    |<span data-ttu-id="43676-170">**名前**</span><span class="sxs-lookup"><span data-stu-id="43676-170">**Name**</span></span>|<span data-ttu-id="43676-171">型**SendToERPPort**します。</span><span class="sxs-lookup"><span data-stu-id="43676-171">Type **SendToERPPort**.</span></span>|  
    |<span data-ttu-id="43676-172">**このポートに使用するポートの種類を選択します。**</span><span class="sxs-lookup"><span data-stu-id="43676-172">**Select the port type to be used for this port**</span></span>|<span data-ttu-id="43676-173">選択**新しいポートの種類を作成する**します。</span><span class="sxs-lookup"><span data-stu-id="43676-173">Select **Create a new Port Type**.</span></span>|  
    |<span data-ttu-id="43676-174">**ポートの種類名**</span><span class="sxs-lookup"><span data-stu-id="43676-174">**Port Type Name**</span></span>|<span data-ttu-id="43676-175">型**SendToERPPortType**します。</span><span class="sxs-lookup"><span data-stu-id="43676-175">Type **SendToERPPortType**.</span></span>|  
    |<span data-ttu-id="43676-176">**通信方式**</span><span class="sxs-lookup"><span data-stu-id="43676-176">**Communication Pattern**</span></span>|<span data-ttu-id="43676-177">選択、**一方向**オプション。</span><span class="sxs-lookup"><span data-stu-id="43676-177">Select the **One-Way** option.</span></span>|  
    |<span data-ttu-id="43676-178">**アクセスの制限**</span><span class="sxs-lookup"><span data-stu-id="43676-178">**Access Restrictions**</span></span>|<span data-ttu-id="43676-179">選択、**内部 - このプロジェクト限定**オプション。</span><span class="sxs-lookup"><span data-stu-id="43676-179">Select the **Internal - limited to this project** option.</span></span>|  
    |<span data-ttu-id="43676-180">**ポートの通信方向**</span><span class="sxs-lookup"><span data-stu-id="43676-180">**Port direction of communication**</span></span>|<span data-ttu-id="43676-181">ドロップダウン リストから選択**は常にメッセージを送信しますこのポートで**します。</span><span class="sxs-lookup"><span data-stu-id="43676-181">From the drop-down list, select **I'll always be sending messages on this port**.</span></span>|  
    |<span data-ttu-id="43676-182">**ポートのバインド**</span><span class="sxs-lookup"><span data-stu-id="43676-182">**Port binding**</span></span>|<span data-ttu-id="43676-183">ドロップダウン リストから選択**後で指定する**します。</span><span class="sxs-lookup"><span data-stu-id="43676-183">From the drop-down list, select **Specify later**.</span></span>|  
  
#### <a name="to-connect-the-ports-to-the-action-shapes"></a><span data-ttu-id="43676-184">ポートをアクション図形に接続するには</span><span class="sxs-lookup"><span data-stu-id="43676-184">To connect the ports to the action shapes</span></span>  
  
-   <span data-ttu-id="43676-185">オーケストレーション デザイナーのデザイン画面で、各ポートに表示されている緑色の矢印のハンドルをドラッグし、アクション図形の対応する緑色のハンドルにドロップします。</span><span class="sxs-lookup"><span data-stu-id="43676-185">In Orchestration Designer, on the design surface, drag the green arrow-shaped handle for each port to the corresponding green handle of the action shape:</span></span>  
  
    |<span data-ttu-id="43676-186">このポートを接続します。</span><span class="sxs-lookup"><span data-stu-id="43676-186">Connect this port</span></span>|<span data-ttu-id="43676-187">接続先のアクション図形</span><span class="sxs-lookup"><span data-stu-id="43676-187">To this action shape</span></span>|  
    |-----------------------|--------------------------|  
    |<span data-ttu-id="43676-188">**ReceiveReqPort**</span><span class="sxs-lookup"><span data-stu-id="43676-188">**ReceiveReqPort**</span></span>|<span data-ttu-id="43676-189">**Receive_Request**</span><span class="sxs-lookup"><span data-stu-id="43676-189">**Receive_Request**</span></span>|  
    |<span data-ttu-id="43676-190">**SendDeclinePort**</span><span class="sxs-lookup"><span data-stu-id="43676-190">**SendDeclinePort**</span></span>|<span data-ttu-id="43676-191">**Send_ReqDenied**</span><span class="sxs-lookup"><span data-stu-id="43676-191">**Send_ReqDenied**</span></span>|  
    |<span data-ttu-id="43676-192">**SendToERP**</span><span class="sxs-lookup"><span data-stu-id="43676-192">**SendToERP**</span></span>|<span data-ttu-id="43676-193">**Send_ReqToERP**</span><span class="sxs-lookup"><span data-stu-id="43676-193">**Send_ReqToERP**</span></span>|  
  
     <span data-ttu-id="43676-194">すべてのポートが接続された EAIProcess オーケストレーションを次に示します。</span><span class="sxs-lookup"><span data-stu-id="43676-194">The following figure shows the EAIProcess orchestration with all of the ports connected.</span></span>  
  
     <span data-ttu-id="43676-195">![ポートが接続された EAIProcess オーケストレーションです。](../core/media/tut1-eaiprocessportsconnected.gif "Tut1_EAIProcessPortsConnected")</span><span class="sxs-lookup"><span data-stu-id="43676-195">![EAIProcess orchestration with connected ports.](../core/media/tut1-eaiprocessportsconnected.gif "Tut1_EAIProcessPortsConnected")</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="43676-196">でしただけ何か。</span><span class="sxs-lookup"><span data-stu-id="43676-196">What did I just do?</span></span>  
 <span data-ttu-id="43676-197">このステップでは、EAIProcess オーケストレーションに 3 つのポートを追加し、それらを構成しました。</span><span class="sxs-lookup"><span data-stu-id="43676-197">In this step, you added three ports to the EAIProcess orchestration and configured them.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="43676-198">次の手順</span><span class="sxs-lookup"><span data-stu-id="43676-198">Next Steps</span></span>  
 <span data-ttu-id="43676-199">プロジェクトをビルドする[手順 4: EAIOrchestration プロジェクトのビルド](../core/step-4-build-the-eaiorchestration-project.md)します。</span><span class="sxs-lookup"><span data-stu-id="43676-199">You build the project in [Step 4: Build the EAIOrchestration Project](../core/step-4-build-the-eaiorchestration-project.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43676-200">参照</span><span class="sxs-lookup"><span data-stu-id="43676-200">See Also</span></span>  
 <span data-ttu-id="43676-201">[手順 1: EAIOrchestration プロジェクトをソリューションに追加します。](../core/step-1-add-eaiorchestration-project-to-the-solution.md) </span><span class="sxs-lookup"><span data-stu-id="43676-201">[Step 1: Add EAIOrchestration Project to the Solution](../core/step-1-add-eaiorchestration-project-to-the-solution.md) </span></span>  
 <span data-ttu-id="43676-202">[手順 2: ビジネス プロセスを定義します。](../core/step-2-define-the-business-process.md) </span><span class="sxs-lookup"><span data-stu-id="43676-202">[Step 2: Define the Business Process](../core/step-2-define-the-business-process.md) </span></span>  
 [<span data-ttu-id="43676-203">手順 4: EAIOrchestration プロジェクトのビルド</span><span class="sxs-lookup"><span data-stu-id="43676-203">Step 4: Build the EAIOrchestration Project</span></span>](../core/step-4-build-the-eaiorchestration-project.md)