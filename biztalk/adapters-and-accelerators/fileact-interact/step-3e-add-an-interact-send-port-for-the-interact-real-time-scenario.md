---
title: "ステップ 3 e: 対話する送信ポートの追加、リアルタイムのシナリオを対話 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d9522386-e980-4ab1-b65a-939ca7936ad9
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ec380c088f27fe09f518c385990e3801b5c019dd
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="step-3e-add-an-interact-send-port-for-the-interact-real-time-scenario"></a><span data-ttu-id="6cb31-102">ステップ 3 e: 対話する送信ポートの追加、リアルタイムのシナリオの対話</span><span class="sxs-lookup"><span data-stu-id="6cb31-102">Step 3E: Add an INTERACT Send Port for the InterAct Real-Time Scenario</span></span>
<span data-ttu-id="6cb31-103">完全な[ステップ 3 D: リアルタイム シナリオでは対話 Sw:HandleResponse メッセージをキャプチャする FILE 送信ポートを追加](../../adapters-and-accelerators/fileact-interact/step-3d-add-file-send-port-to-get-sw-handleresponse-message-for-interact.md)この手順を開始する前にします。</span><span class="sxs-lookup"><span data-stu-id="6cb31-103">Complete [Step 3D: Add a FILE Send Port to Capture the Sw:HandleResponse Message for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3d-add-file-send-port-to-get-sw-handleresponse-message-for-interact.md) before you begin this step.</span></span>
  
## <a name="add-an-interact-send-port"></a><span data-ttu-id="6cb31-104">対話する送信ポートを追加します。</span><span class="sxs-lookup"><span data-stu-id="6cb31-104">Add an INTERACT send port</span></span>  
  
1.  <span data-ttu-id="6cb31-105">開始**BizTalk Server 管理**です。</span><span class="sxs-lookup"><span data-stu-id="6cb31-105">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="6cb31-106">コンソール ツリーで、BizTalk グループを展開し、送信ポートを作成する BizTalk アプリケーションの順に展開します。</span><span class="sxs-lookup"><span data-stu-id="6cb31-106">In the console tree, expand the BizTalk group, and then expand the BizTalk application for which you want to create a send port.</span></span>  
  
3.  <span data-ttu-id="6cb31-107">右クリック**送信ポート**、 をポイント**新規**、クリックして**静的な送信請求-応答送信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="6cb31-107">Right-click **Send Ports**, point to **New**, and then click **Static Solicit-Response Send Port**.</span></span>  
  
4.  <span data-ttu-id="6cb31-108">**送信ポートのプロパティ**ウィンドウで、送信ポートの名前**Tutorial_IA_SendRequest_RealTime**です。</span><span class="sxs-lookup"><span data-stu-id="6cb31-108">In the **Send Port Properties** window, name the send port **Tutorial_IA_SendRequest_RealTime**.</span></span>  
  
5.  <span data-ttu-id="6cb31-109">**送信ポートのプロパティ** ウィンドウから、**トランスポートの種類**ドロップダウン リストで、 **INTERACT**、順にクリック**構成**です。</span><span class="sxs-lookup"><span data-stu-id="6cb31-109">In the **Send Port Properties** window, from the **Transport type** drop-down list, select **INTERACT**, and then click **Configure**.</span></span>  
  
6.  <span data-ttu-id="6cb31-110">**トランスポートのプロパティの対話** ダイアログ ボックスで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="6cb31-110">In the **INTERACT Transport Properties** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="6cb31-111">**これを使用してください。**</span><span class="sxs-lookup"><span data-stu-id="6cb31-111">**Use this**</span></span>|<span data-ttu-id="6cb31-112">**これを行う**</span><span class="sxs-lookup"><span data-stu-id="6cb31-112">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="6cb31-113">**Password**</span><span class="sxs-lookup"><span data-stu-id="6cb31-113">**Password**</span></span>|<span data-ttu-id="6cb31-114">SAG 接続適切なパスワードを設定します。</span><span class="sxs-lookup"><span data-stu-id="6cb31-114">Set the password as appropriate for SAG connectivity.</span></span>|  
    |<span data-ttu-id="6cb31-115">**ユーザー名**</span><span class="sxs-lookup"><span data-stu-id="6cb31-115">**User name**</span></span>|<span data-ttu-id="6cb31-116">SAG 接続を適切なユーザー名を設定します。</span><span class="sxs-lookup"><span data-stu-id="6cb31-116">Set the user name as appropriate for SAG connectivity.</span></span>|  
    |<span data-ttu-id="6cb31-117">**アダプターのモード**</span><span class="sxs-lookup"><span data-stu-id="6cb31-117">**Adapter Mode**</span></span>|<span data-ttu-id="6cb31-118">ドロップダウン リストから選択**リアルタイム**です。</span><span class="sxs-lookup"><span data-stu-id="6cb31-118">From the drop-down list, select **RealTime**.</span></span>|  
    |<span data-ttu-id="6cb31-119">**メッセージの形式**</span><span class="sxs-lookup"><span data-stu-id="6cb31-119">**Message format**</span></span>|<span data-ttu-id="6cb31-120">**InteractMessage**です。</span><span class="sxs-lookup"><span data-stu-id="6cb31-120">**InteractMessage**.</span></span>|  
    |<span data-ttu-id="6cb31-121">**否認不可インジケーター**</span><span class="sxs-lookup"><span data-stu-id="6cb31-121">**Non-Repudiation Indicator**</span></span>|<span data-ttu-id="6cb31-122">**FALSE**。</span><span class="sxs-lookup"><span data-stu-id="6cb31-122">**FALSE**.</span></span>|  
    |<span data-ttu-id="6cb31-123">**要求の種類**</span><span class="sxs-lookup"><span data-stu-id="6cb31-123">**Request Type**</span></span>|<span data-ttu-id="6cb31-124">適切な入力\<RequestType\> SWIFT でのプロビジョニングに基づく文字列。</span><span class="sxs-lookup"><span data-stu-id="6cb31-124">Type the appropriate \<RequestType\> string, based on your provisioning with SWIFT.</span></span>|  
    |<span data-ttu-id="6cb31-125">**ResponseCrypto**</span><span class="sxs-lookup"><span data-stu-id="6cb31-125">**ResponseCrypto**</span></span>|<span data-ttu-id="6cb31-126">**FALSE**。</span><span class="sxs-lookup"><span data-stu-id="6cb31-126">**FALSE**.</span></span>|  
    |<span data-ttu-id="6cb31-127">**要求元**</span><span class="sxs-lookup"><span data-stu-id="6cb31-127">**Requestor**</span></span>|<span data-ttu-id="6cb31-128">適切な設定\<リクエスター\> SWIFT でのプロビジョニングに基づく文字列。</span><span class="sxs-lookup"><span data-stu-id="6cb31-128">Set it to the appropriate \<Requestor\> string, based on your provisioning with SWIFT.</span></span>|  
    |<span data-ttu-id="6cb31-129">**応答側**</span><span class="sxs-lookup"><span data-stu-id="6cb31-129">**Responder**</span></span>|<span data-ttu-id="6cb31-130">適切な設定\<レスポンダー\> SWIFT でのプロビジョニングに基づく文字列。</span><span class="sxs-lookup"><span data-stu-id="6cb31-130">Set it to the appropriate \<Responder\> string, based on your provisioning with SWIFT.</span></span>|  
    |<span data-ttu-id="6cb31-131">**サービス名**</span><span class="sxs-lookup"><span data-stu-id="6cb31-131">**Service Name**</span></span>|<span data-ttu-id="6cb31-132">適切な設定\<サービス名\>SWIFT でのプロビジョニングに基づきます。</span><span class="sxs-lookup"><span data-stu-id="6cb31-132">Set it to the appropriate \<service name\>, based on your provisioning with SWIFT.</span></span>|  
    |<span data-ttu-id="6cb31-133">**配信通知**</span><span class="sxs-lookup"><span data-stu-id="6cb31-133">**Delivery Notification**</span></span>|<span data-ttu-id="6cb31-134">ドロップダウン リストから選択**FALSE**です。</span><span class="sxs-lookup"><span data-stu-id="6cb31-134">From the drop-down list, select  **FALSE**.</span></span>|  
    |<span data-ttu-id="6cb31-135">**通知キュー**</span><span class="sxs-lookup"><span data-stu-id="6cb31-135">**Notify queue**</span></span>|<span data-ttu-id="6cb31-136">SWIFT でのプロビジョニングに基づく、適切なキュー名を入力します。</span><span class="sxs-lookup"><span data-stu-id="6cb31-136">Type the appropriate queue name, based on your provisioning with SWIFT.</span></span>|  
  
    > [!NOTE]
    >  <span data-ttu-id="6cb31-137">ペイロードは、転送するのには、専用の場合は、ポートと対話する送信ポートが受信"Payloadonly"で、対話する MessageFormat を設定します。</span><span class="sxs-lookup"><span data-stu-id="6cb31-137">If only payload is to be transferred, set the MessageFormat to “Payloadonly” in the INTERACT receive port and INTERACT send port.</span></span> <span data-ttu-id="6cb31-138">受信の設定し、送信パイプラインをパススルーします。</span><span class="sxs-lookup"><span data-stu-id="6cb31-138">Set the receive and send pipelines to PassThru.</span></span>  
  
7.  <span data-ttu-id="6cb31-139">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6cb31-139">Click **OK**.</span></span>  
  
8.  <span data-ttu-id="6cb31-140">**送信ポートのプロパティ** ウィンドウで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="6cb31-140">In the **Send Port Properties** window, do the following:</span></span>  
  
    |<span data-ttu-id="6cb31-141">**これを使用してください。**</span><span class="sxs-lookup"><span data-stu-id="6cb31-141">**Use this**</span></span>|<span data-ttu-id="6cb31-142">**これを行う**</span><span class="sxs-lookup"><span data-stu-id="6cb31-142">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="6cb31-143">**送信ハンドラー**</span><span class="sxs-lookup"><span data-stu-id="6cb31-143">**Send handler**</span></span>|<span data-ttu-id="6cb31-144">ドロップダウン リストから、対話ホストを選択します。</span><span class="sxs-lookup"><span data-stu-id="6cb31-144">From the drop-down list, select the Interact host.</span></span>|  
    |<span data-ttu-id="6cb31-145">**送信パイプライン**</span><span class="sxs-lookup"><span data-stu-id="6cb31-145">**Send pipeline**</span></span>|<span data-ttu-id="6cb31-146">ドロップダウン リストから選択**XMLTransmit**です。</span><span class="sxs-lookup"><span data-stu-id="6cb31-146">From the drop-down list, select **XMLTransmit**.</span></span>|  
    |<span data-ttu-id="6cb31-147">**受信パイプライン**</span><span class="sxs-lookup"><span data-stu-id="6cb31-147">**Receive pipeline**</span></span>|<span data-ttu-id="6cb31-148">**[Xmlreceive]**</span><span class="sxs-lookup"><span data-stu-id="6cb31-148">**XMLReceive**</span></span>|  
  
9. <span data-ttu-id="6cb31-149">**送信ポートのプロパティ** ウィンドウで、**フィルター**  タブで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="6cb31-149">In the **Send Port Properties** window, on the **Filters** tab, do the following:</span></span>  
  
    |<span data-ttu-id="6cb31-150">**これを使用してください。**</span><span class="sxs-lookup"><span data-stu-id="6cb31-150">**Use this**</span></span>|<span data-ttu-id="6cb31-151">**これを行う**</span><span class="sxs-lookup"><span data-stu-id="6cb31-151">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="6cb31-152">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="6cb31-152">**Property**</span></span>|<span data-ttu-id="6cb31-153">ドロップダウン リストから選択**BTS です。ReceivePortName**です。</span><span class="sxs-lookup"><span data-stu-id="6cb31-153">From the drop-down list, select **BTS.ReceivePortName**.</span></span>|  
    |<span data-ttu-id="6cb31-154">**演算子**</span><span class="sxs-lookup"><span data-stu-id="6cb31-154">**Operator**</span></span>|<span data-ttu-id="6cb31-155">ドロップダウン リストから選択 **==**です。</span><span class="sxs-lookup"><span data-stu-id="6cb31-155">From the drop-down list, select **==**.</span></span>|  
    |<span data-ttu-id="6cb31-156">**値**</span><span class="sxs-lookup"><span data-stu-id="6cb31-156">**Value**</span></span>|<span data-ttu-id="6cb31-157">型**Tutorial_IA_InputRequest_RealTime**です。</span><span class="sxs-lookup"><span data-stu-id="6cb31-157">Type **Tutorial_IA_InputRequest_RealTime**.</span></span>|  
    |<span data-ttu-id="6cb31-158">**グループ化**</span><span class="sxs-lookup"><span data-stu-id="6cb31-158">**Group by**</span></span>|<span data-ttu-id="6cb31-159">既定値を使用します。</span><span class="sxs-lookup"><span data-stu-id="6cb31-159">Leave the default value.</span></span>|  
  
10. <span data-ttu-id="6cb31-160">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6cb31-160">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6cb31-161">参照</span><span class="sxs-lookup"><span data-stu-id="6cb31-161">See Also</span></span>  
 <span data-ttu-id="6cb31-162">[手順 3: が送信を作成し、受信のポート、リアルタイムのシナリオの対話](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-the-interact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="6cb31-162">[Step 3: Create Send and Receive Ports for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-the-interact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="6cb31-163">[手順 3: ファイルの受信場所を追加、リアルタイムのシナリオの対話](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-the-interact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="6cb31-163">[Step 3A: Add a FILE Receive Location for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-the-interact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="6cb31-164">[手順 3 b: 対話の受信場所を追加、リアルタイムのシナリオの対話](../../adapters-and-accelerators/fileact-interact/step-3b-add-an-interact-receive-location-for-the-interact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="6cb31-164">[Step 3B: Add an INTERACT Receive Location for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3b-add-an-interact-receive-location-for-the-interact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="6cb31-165">[手順 3 C: の Sw:HandleRequest メッセージをキャプチャする FILE 送信ポートを追加、リアルタイムのシナリオの対話](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlerequest-interact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="6cb31-165">[Step 3C: Add a FILE Send Port to Capture the Sw:HandleRequest Message for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlerequest-interact-real-time-scenario.md) </span></span>  
 [<span data-ttu-id="6cb31-166">手順 3D: InterAct リアルタイム シナリオ用に Sw:HandleResponse メッセージをキャプチャするためにファイルの送信ポートを追加する</span><span class="sxs-lookup"><span data-stu-id="6cb31-166">Step 3D: Add a FILE Send Port to Capture the Sw:HandleResponse Message for the InterAct Real-Time Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-3d-add-file-send-port-to-get-sw-handleresponse-message-for-interact.md)