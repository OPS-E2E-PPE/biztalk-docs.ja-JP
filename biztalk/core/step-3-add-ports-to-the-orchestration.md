---
title: '手順 3: オーケストレーション ポートを追加、|Microsoft ドキュメント'
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
ms.openlocfilehash: 13af336b2162e0f784195bf7c789c0dff984cb04
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22279834"
---
# <a name="step-3-add-ports-to-the-orchestration"></a><span data-ttu-id="8279a-102">ステップ 3: オーケストレーションへのポートの追加</span><span class="sxs-lookup"><span data-stu-id="8279a-102">Step 3: Add Ports to the Orchestration</span></span>
<span data-ttu-id="8279a-103">![手順 4 の 3](../adapters-and-accelerators/adapter-oracle-ebs/media/step-3of4.gif "Step_3of4")</span><span class="sxs-lookup"><span data-stu-id="8279a-103">![Step 3 of 4](../adapters-and-accelerators/adapter-oracle-ebs/media/step-3of4.gif "Step_3of4")</span></span>  
  
 <span data-ttu-id="8279a-104">**所要時間:** 10 分</span><span class="sxs-lookup"><span data-stu-id="8279a-104">**Time to complete:** 10 minutes</span></span>  
  
 <span data-ttu-id="8279a-105">**目標:** このステップで、EAIProcess オーケストレーションに 3 つのポートを追加してそれらを構成します。</span><span class="sxs-lookup"><span data-stu-id="8279a-105">**Objective:** In this step, you add three ports to the EAIProcess orchestration and configure them.</span></span>  
  
 <span data-ttu-id="8279a-106">**目的:** ポート、オーケストレーションはメッセージを送信し、他のビジネス プロセスからメッセージを受信方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="8279a-106">**Purpose:** Ports specify how your orchestration will send messages to and receive messages from other business processes.</span></span> <span data-ttu-id="8279a-107">各ポートは、種類、方向、バインドを保持しています。これらの組み合わせによって、通信方向、通信方式、メッセージの送信先場所と送信元場所、および通信の実行方法が決まります。</span><span class="sxs-lookup"><span data-stu-id="8279a-107">Each port has a type, a direction, and a binding, which together determine the direction of communication, the pattern of communication, the location to or from which the message is sent or received, and how the communication takes place.</span></span> <span data-ttu-id="8279a-108">このステップで作成および構成する 3 つのポートには、それぞれ次の役割があります。</span><span class="sxs-lookup"><span data-stu-id="8279a-108">The three ports you create and configure in this step fulfill the following roles:</span></span>  
  
-   <span data-ttu-id="8279a-109">**ReceiveRequestPort**倉庫から在庫補充要求メッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="8279a-109">**ReceiveRequestPort** receives inventory replenishment request messages from the warehouse.</span></span>  
  
-   <span data-ttu-id="8279a-110">**[Sendtoerp]** ERP システムに要求メッセージを転送します。</span><span class="sxs-lookup"><span data-stu-id="8279a-110">**SendToERP** forwards the request messages to the ERP system.</span></span>  
  
-   <span data-ttu-id="8279a-111">**SendDeclinePort**要求拒否メッセージ倉庫に返送します。</span><span class="sxs-lookup"><span data-stu-id="8279a-111">**SendDeclinePort** sends request decline messages back to the warehouse.</span></span>  
  
 <span data-ttu-id="8279a-112">詳細については、次を参照してください。[オーケストレーションで使用するポート](../core/using-ports-in-orchestrations.md)です。</span><span class="sxs-lookup"><span data-stu-id="8279a-112">For more information, see [Using Ports in Orchestrations](../core/using-ports-in-orchestrations.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="8279a-113">前提条件</span><span class="sxs-lookup"><span data-stu-id="8279a-113">Prerequisites</span></span>  
 <span data-ttu-id="8279a-114">このステップを開始する前に、以下の要件を確認してください。</span><span class="sxs-lookup"><span data-stu-id="8279a-114">Note the following requirements before you begin this step:</span></span>  
  
-   <span data-ttu-id="8279a-115">この手順を開始する前に行う必要があります[手順 2: ビジネス プロセスの定義](../core/step-2-define-the-business-process.md)です。</span><span class="sxs-lookup"><span data-stu-id="8279a-115">Before you begin this step you must complete [Step 2: Define the Business Process](../core/step-2-define-the-business-process.md).</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="8279a-116">手順</span><span class="sxs-lookup"><span data-stu-id="8279a-116">Procedures</span></span>  
  
#### <a name="to-create-and-configure-receiverequestport"></a><span data-ttu-id="8279a-117">ReceiveRequestPort を作成および構成するには</span><span class="sxs-lookup"><span data-stu-id="8279a-117">To create and configure ReceiveRequestPort</span></span>  
  
1.  <span data-ttu-id="8279a-118">ソリューション エクスプ ローラーで、 **EAIProcess.odx**です。</span><span class="sxs-lookup"><span data-stu-id="8279a-118">In Solution Explorer, double-click **EAIProcess.odx**.</span></span>  
  
2.  <span data-ttu-id="8279a-119">オーケストレーション デザイナで、オーケストレーション ツールボックスからドラッグして、**ポート**図形を左側の**ポート画面**並列に、 **ReceiveRequest**図形です。</span><span class="sxs-lookup"><span data-stu-id="8279a-119">In Orchestration Designer, from the orchestration Toolbox, drag the **Port** shape to the left-side **Port Surface**, parallel to the **ReceiveRequest** shape.</span></span> <span data-ttu-id="8279a-120">ポート構成ウィザードが自動的に起動します。</span><span class="sxs-lookup"><span data-stu-id="8279a-120">The Port Configuration Wizard starts automatically.</span></span>  
  
3.  <span data-ttu-id="8279a-121">**[ポート構成ウィザードへようこそ]** ページで、 **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8279a-121">On the **Welcome to the Port Configuration Wizard** page, click **Next**.</span></span>  
  
4.  <span data-ttu-id="8279a-122">**ポートのプロパティ** ページで、次の操作をクリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="8279a-122">On the **Port Properties** page, do the following, and then click **Next**.</span></span>  
  
    |<span data-ttu-id="8279a-123">プロパティ</span><span class="sxs-lookup"><span data-stu-id="8279a-123">Use this</span></span>|<span data-ttu-id="8279a-124">目的</span><span class="sxs-lookup"><span data-stu-id="8279a-124">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="8279a-125">**名前**</span><span class="sxs-lookup"><span data-stu-id="8279a-125">**Name**</span></span>|<span data-ttu-id="8279a-126">型**ReceiveRequestPort**です。</span><span class="sxs-lookup"><span data-stu-id="8279a-126">Type **ReceiveRequestPort**.</span></span>|  
  
5.  <span data-ttu-id="8279a-127">**ポートの種類を選択して** ページで、次の操作をクリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="8279a-127">On the **Select a Port Type** page, do the following, and then click **Next**.</span></span>  
  
    |<span data-ttu-id="8279a-128">プロパティ</span><span class="sxs-lookup"><span data-stu-id="8279a-128">Use this</span></span>|<span data-ttu-id="8279a-129">目的</span><span class="sxs-lookup"><span data-stu-id="8279a-129">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="8279a-130">**このポートに使用するポートの種類を選択します。**</span><span class="sxs-lookup"><span data-stu-id="8279a-130">**Select the port type to be used for this port**</span></span>|<span data-ttu-id="8279a-131">選択、**新しいポートの種類を作成する**オプション。</span><span class="sxs-lookup"><span data-stu-id="8279a-131">Select the **Create a new Port Type** option.</span></span>|  
    |<span data-ttu-id="8279a-132">**ポートの種類名:**</span><span class="sxs-lookup"><span data-stu-id="8279a-132">**Port Type Name:**</span></span>|<span data-ttu-id="8279a-133">型**ReceiveRequestPortType**です。</span><span class="sxs-lookup"><span data-stu-id="8279a-133">Type **ReceiveRequestPortType**.</span></span>|  
    |<span data-ttu-id="8279a-134">**通信方式**</span><span class="sxs-lookup"><span data-stu-id="8279a-134">**Communication Pattern**</span></span>|<span data-ttu-id="8279a-135">選択**一方向**です。</span><span class="sxs-lookup"><span data-stu-id="8279a-135">Select **One-Way**.</span></span>|  
    |<span data-ttu-id="8279a-136">**アクセスの制限**</span><span class="sxs-lookup"><span data-stu-id="8279a-136">**Access Restrictions**</span></span>|<span data-ttu-id="8279a-137">選択**内部 - このプロジェクト限定**です。</span><span class="sxs-lookup"><span data-stu-id="8279a-137">Select **Internal - limited to this project**.</span></span>|  
  
6.  <span data-ttu-id="8279a-138">**ポートのバインド** ページで、次の操作をクリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="8279a-138">On the **Port Binding** page, do the following, and then click **Next**.</span></span>  
  
    |<span data-ttu-id="8279a-139">プロパティ</span><span class="sxs-lookup"><span data-stu-id="8279a-139">Use this</span></span>|<span data-ttu-id="8279a-140">目的</span><span class="sxs-lookup"><span data-stu-id="8279a-140">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="8279a-141">**ポートの通信方向**</span><span class="sxs-lookup"><span data-stu-id="8279a-141">**Port direction of communication**</span></span>|<span data-ttu-id="8279a-142">選択**常にこのポートでメッセージを受信**です。</span><span class="sxs-lookup"><span data-stu-id="8279a-142">Select **I'll always be receiving messages on this port**.</span></span>|  
    |<span data-ttu-id="8279a-143">**ポートのバインド**</span><span class="sxs-lookup"><span data-stu-id="8279a-143">**Port binding**</span></span>|<span data-ttu-id="8279a-144">選択から**後指定**です。</span><span class="sxs-lookup"><span data-stu-id="8279a-144">From select **Specify later**.</span></span>|  
  
7.  <span data-ttu-id="8279a-145">**ポート ウィザードの完了**] ページで [**完了**です。</span><span class="sxs-lookup"><span data-stu-id="8279a-145">On the **Completing the Port Wizard** page, click **Finish**.</span></span>  
  
#### <a name="to-create-and-configure-senddeclineport"></a><span data-ttu-id="8279a-146">SendDeclinePort を作成および構成するには</span><span class="sxs-lookup"><span data-stu-id="8279a-146">To create and configure SendDeclinePort</span></span>  
  
1.  <span data-ttu-id="8279a-147">オーケストレーション ツールボックスからドラッグして、**ポート**図形を左側の**ポート画面**並列に、 **SendRequestDecline**図形です。</span><span class="sxs-lookup"><span data-stu-id="8279a-147">From the orchestration Toolbox, drag the **Port** shape to the left-side **Port Surface**, parallel to the **SendRequestDecline** shape.</span></span>  
  
2.  <span data-ttu-id="8279a-148">次の表に、情報を使用して、作成、 **SendDeclinePort**ポートを送信します。</span><span class="sxs-lookup"><span data-stu-id="8279a-148">Use the information in the following table to create the **SendDeclinePort** send port.</span></span>  
  
    |<span data-ttu-id="8279a-149">プロパティ</span><span class="sxs-lookup"><span data-stu-id="8279a-149">Property</span></span>|<span data-ttu-id="8279a-150">値</span><span class="sxs-lookup"><span data-stu-id="8279a-150">Value</span></span>|  
    |--------------|-----------|  
    |<span data-ttu-id="8279a-151">**名前**</span><span class="sxs-lookup"><span data-stu-id="8279a-151">**Name**</span></span>|<span data-ttu-id="8279a-152">型**SendDeclinePort**です。</span><span class="sxs-lookup"><span data-stu-id="8279a-152">Type **SendDeclinePort**.</span></span>|  
    |<span data-ttu-id="8279a-153">**このポートに使用するポートの種類を選択します。**</span><span class="sxs-lookup"><span data-stu-id="8279a-153">**Select the port type to be used for this port**</span></span>|<span data-ttu-id="8279a-154">選択**新しいポートの種類を作成する**です。</span><span class="sxs-lookup"><span data-stu-id="8279a-154">Select **Create a new Port Type**.</span></span>|  
    |<span data-ttu-id="8279a-155">**ポートの種類名**</span><span class="sxs-lookup"><span data-stu-id="8279a-155">**Port Type Name**</span></span>|<span data-ttu-id="8279a-156">型**SendDeclinePortType**です。</span><span class="sxs-lookup"><span data-stu-id="8279a-156">Type **SendDeclinePortType**.</span></span>|  
    |<span data-ttu-id="8279a-157">**通信方式**</span><span class="sxs-lookup"><span data-stu-id="8279a-157">**Communication Pattern**</span></span>|<span data-ttu-id="8279a-158">選択**一方向**です。</span><span class="sxs-lookup"><span data-stu-id="8279a-158">Select **One-Way**.</span></span>|  
    |<span data-ttu-id="8279a-159">**アクセスの制限**</span><span class="sxs-lookup"><span data-stu-id="8279a-159">**Access Restrictions**</span></span>|<span data-ttu-id="8279a-160">選択**内部 - このプロジェクト限定**です。</span><span class="sxs-lookup"><span data-stu-id="8279a-160">Select **Internal - limited to this project**.</span></span>|  
    |<span data-ttu-id="8279a-161">**ポートの通信方向**</span><span class="sxs-lookup"><span data-stu-id="8279a-161">**Port direction of communication**</span></span>|<span data-ttu-id="8279a-162">ドロップダウン リストから選択**すればを常にメッセージを送信するこのポートで**です。</span><span class="sxs-lookup"><span data-stu-id="8279a-162">From the drop-down list, select **I'll always be sending messages on this port**.</span></span>|  
    |<span data-ttu-id="8279a-163">**ポートのバインド**</span><span class="sxs-lookup"><span data-stu-id="8279a-163">**Port bindings**</span></span>|<span data-ttu-id="8279a-164">ドロップダウン リストから選択**後指定**です。</span><span class="sxs-lookup"><span data-stu-id="8279a-164">From the drop-down list, select **Specify later**.</span></span>|  
  
#### <a name="to-create-and-configure-sendtoerpport"></a><span data-ttu-id="8279a-165">SendToERPPort を作成および構成するには</span><span class="sxs-lookup"><span data-stu-id="8279a-165">To create and configure SendToERPPort</span></span>  
  
1.  <span data-ttu-id="8279a-166">オーケストレーション ツールボックスからドラッグして、**ポート**図形を右側にある**ポート画面**並列に、 **SendToERP**図形です。</span><span class="sxs-lookup"><span data-stu-id="8279a-166">From the orchestration Toolbox, drag the **Port** shape to the right-side **Port Surface**, parallel to the **SendToERP** shape.</span></span>  
  
2.  <span data-ttu-id="8279a-167">次の表に、情報を使用して、ポート構成ウィザードを完了、 **SendToERP**ポートを送信します。</span><span class="sxs-lookup"><span data-stu-id="8279a-167">Use the information in the following table to complete the Port Configuration Wizard for the **SendToERP** send port.</span></span>  
  
    |<span data-ttu-id="8279a-168">プロパティ</span><span class="sxs-lookup"><span data-stu-id="8279a-168">Property</span></span>|<span data-ttu-id="8279a-169">値</span><span class="sxs-lookup"><span data-stu-id="8279a-169">Value</span></span>|  
    |--------------|-----------|  
    |<span data-ttu-id="8279a-170">**名前**</span><span class="sxs-lookup"><span data-stu-id="8279a-170">**Name**</span></span>|<span data-ttu-id="8279a-171">型**SendToERPPort**です。</span><span class="sxs-lookup"><span data-stu-id="8279a-171">Type **SendToERPPort**.</span></span>|  
    |<span data-ttu-id="8279a-172">**このポートに使用するポートの種類を選択します。**</span><span class="sxs-lookup"><span data-stu-id="8279a-172">**Select the port type to be used for this port**</span></span>|<span data-ttu-id="8279a-173">選択**新しいポートの種類を作成する**です。</span><span class="sxs-lookup"><span data-stu-id="8279a-173">Select **Create a new Port Type**.</span></span>|  
    |<span data-ttu-id="8279a-174">**ポートの種類名**</span><span class="sxs-lookup"><span data-stu-id="8279a-174">**Port Type Name**</span></span>|<span data-ttu-id="8279a-175">型**SendToERPPortType**です。</span><span class="sxs-lookup"><span data-stu-id="8279a-175">Type **SendToERPPortType**.</span></span>|  
    |<span data-ttu-id="8279a-176">**通信方式**</span><span class="sxs-lookup"><span data-stu-id="8279a-176">**Communication Pattern**</span></span>|<span data-ttu-id="8279a-177">選択、**一方向**オプション。</span><span class="sxs-lookup"><span data-stu-id="8279a-177">Select the **One-Way** option.</span></span>|  
    |<span data-ttu-id="8279a-178">**アクセスの制限**</span><span class="sxs-lookup"><span data-stu-id="8279a-178">**Access Restrictions**</span></span>|<span data-ttu-id="8279a-179">選択、**内部 - このプロジェクト限定**オプション。</span><span class="sxs-lookup"><span data-stu-id="8279a-179">Select the **Internal - limited to this project** option.</span></span>|  
    |<span data-ttu-id="8279a-180">**ポートの通信方向**</span><span class="sxs-lookup"><span data-stu-id="8279a-180">**Port direction of communication**</span></span>|<span data-ttu-id="8279a-181">ドロップダウン リストから選択**すればを常にメッセージを送信するこのポートで**です。</span><span class="sxs-lookup"><span data-stu-id="8279a-181">From the drop-down list, select **I'll always be sending messages on this port**.</span></span>|  
    |<span data-ttu-id="8279a-182">**ポートのバインド**</span><span class="sxs-lookup"><span data-stu-id="8279a-182">**Port binding**</span></span>|<span data-ttu-id="8279a-183">ドロップダウン リストから選択**後指定**です。</span><span class="sxs-lookup"><span data-stu-id="8279a-183">From the drop-down list, select **Specify later**.</span></span>|  
  
#### <a name="to-connect-the-ports-to-the-action-shapes"></a><span data-ttu-id="8279a-184">ポートをアクション図形に接続するには</span><span class="sxs-lookup"><span data-stu-id="8279a-184">To connect the ports to the action shapes</span></span>  
  
-   <span data-ttu-id="8279a-185">オーケストレーション デザイナーのデザイン画面で、各ポートに表示されている緑色の矢印のハンドルをドラッグし、アクション図形の対応する緑色のハンドルにドロップします。</span><span class="sxs-lookup"><span data-stu-id="8279a-185">In Orchestration Designer, on the design surface, drag the green arrow-shaped handle for each port to the corresponding green handle of the action shape:</span></span>  
  
    |<span data-ttu-id="8279a-186">このポートを接続します。</span><span class="sxs-lookup"><span data-stu-id="8279a-186">Connect this port</span></span>|<span data-ttu-id="8279a-187">接続先のアクション図形</span><span class="sxs-lookup"><span data-stu-id="8279a-187">To this action shape</span></span>|  
    |-----------------------|--------------------------|  
    |<span data-ttu-id="8279a-188">**ReceiveReqPort**</span><span class="sxs-lookup"><span data-stu-id="8279a-188">**ReceiveReqPort**</span></span>|<span data-ttu-id="8279a-189">**Receive_Request**</span><span class="sxs-lookup"><span data-stu-id="8279a-189">**Receive_Request**</span></span>|  
    |<span data-ttu-id="8279a-190">**SendDeclinePort**</span><span class="sxs-lookup"><span data-stu-id="8279a-190">**SendDeclinePort**</span></span>|<span data-ttu-id="8279a-191">**Send_ReqDenied**</span><span class="sxs-lookup"><span data-stu-id="8279a-191">**Send_ReqDenied**</span></span>|  
    |<span data-ttu-id="8279a-192">**[Sendtoerp]**</span><span class="sxs-lookup"><span data-stu-id="8279a-192">**SendToERP**</span></span>|<span data-ttu-id="8279a-193">**Send_ReqToERP**</span><span class="sxs-lookup"><span data-stu-id="8279a-193">**Send_ReqToERP**</span></span>|  
  
     <span data-ttu-id="8279a-194">すべてのポートが接続された EAIProcess オーケストレーションを次に示します。</span><span class="sxs-lookup"><span data-stu-id="8279a-194">The following figure shows the EAIProcess orchestration with all of the ports connected.</span></span>  
  
     <span data-ttu-id="8279a-195">![ポートが接続された EAIProcess オーケストレーションです。] (../core/media/tut1-eaiprocessportsconnected.gif "Tut1_EAIProcessPortsConnected")</span><span class="sxs-lookup"><span data-stu-id="8279a-195">![EAIProcess orchestration with connected ports.](../core/media/tut1-eaiprocessportsconnected.gif "Tut1_EAIProcessPortsConnected")</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="8279a-196">でしただけは何ですか。</span><span class="sxs-lookup"><span data-stu-id="8279a-196">What did I just do?</span></span>  
 <span data-ttu-id="8279a-197">このステップでは、EAIProcess オーケストレーションに 3 つのポートを追加し、それらを構成しました。</span><span class="sxs-lookup"><span data-stu-id="8279a-197">In this step, you added three ports to the EAIProcess orchestration and configured them.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="8279a-198">次の手順</span><span class="sxs-lookup"><span data-stu-id="8279a-198">Next Steps</span></span>  
 <span data-ttu-id="8279a-199">プロジェクトをビルドする[手順 4: EAIOrchestration プロジェクトをビルド](../core/step-4-build-the-eaiorchestration-project.md)です。</span><span class="sxs-lookup"><span data-stu-id="8279a-199">You build the project in [Step 4: Build the EAIOrchestration Project](../core/step-4-build-the-eaiorchestration-project.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8279a-200">参照</span><span class="sxs-lookup"><span data-stu-id="8279a-200">See Also</span></span>  
 <span data-ttu-id="8279a-201">[手順 1: EAIOrchestration プロジェクトをソリューションに追加します。](../core/step-1-add-eaiorchestration-project-to-the-solution.md) </span><span class="sxs-lookup"><span data-stu-id="8279a-201">[Step 1: Add EAIOrchestration Project to the Solution](../core/step-1-add-eaiorchestration-project-to-the-solution.md) </span></span>  
 <span data-ttu-id="8279a-202">[手順 2: ビジネス プロセスを定義します。](../core/step-2-define-the-business-process.md) </span><span class="sxs-lookup"><span data-stu-id="8279a-202">[Step 2: Define the Business Process](../core/step-2-define-the-business-process.md) </span></span>  
 [<span data-ttu-id="8279a-203">手順 4: EAIOrchestration プロジェクトをビルドします。</span><span class="sxs-lookup"><span data-stu-id="8279a-203">Step 4: Build the EAIOrchestration Project</span></span>](../core/step-4-build-the-eaiorchestration-project.md)