---
title: 手順 3 e:用の INTERACT 送信ポートを追加、InterAct リアルタイム シナリオ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d9522386-e980-4ab1-b65a-939ca7936ad9
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9503976d47f70a0077b5a30598d5daa826855e1e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65365464"
---
# <a name="step-3e-add-an-interact-send-port-for-the-interact-real-time-scenario"></a><span data-ttu-id="9c0a0-102">手順 3 e:用の INTERACT 送信ポートを追加、InterAct リアルタイム シナリオ</span><span class="sxs-lookup"><span data-stu-id="9c0a0-102">Step 3E: Add an INTERACT Send Port for the InterAct Real-Time Scenario</span></span>
<span data-ttu-id="9c0a0-103">完全な[手順 3 D:操作のリアルタイム シナリオ用に Sw:HandleResponse メッセージをキャプチャする FILE 送信ポートの追加](../../adapters-and-accelerators/fileact-interact/step-3d-add-file-send-port-to-get-sw-handleresponse-message-for-interact.md)この手順を開始する前にします。</span><span class="sxs-lookup"><span data-stu-id="9c0a0-103">Complete [Step 3D: Add a FILE Send Port to Capture the Sw:HandleResponse Message for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3d-add-file-send-port-to-get-sw-handleresponse-message-for-interact.md) before you begin this step.</span></span>
  
## <a name="add-an-interact-send-port"></a><span data-ttu-id="9c0a0-104">INTERACT 送信ポートを追加します。</span><span class="sxs-lookup"><span data-stu-id="9c0a0-104">Add an INTERACT send port</span></span>  
  
1.  <span data-ttu-id="9c0a0-105">開始**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="9c0a0-105">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="9c0a0-106">コンソール ツリーで、BizTalk グループを展開し、送信ポートを作成する BizTalk アプリケーションを順に展開します。</span><span class="sxs-lookup"><span data-stu-id="9c0a0-106">In the console tree, expand the BizTalk group, and then expand the BizTalk application for which you want to create a send port.</span></span>  
  
3.  <span data-ttu-id="9c0a0-107">右クリック**送信ポート**、 をポイント**新規**、 をクリックし、**静的な送信請求-応答送信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="9c0a0-107">Right-click **Send Ports**, point to **New**, and then click **Static Solicit-Response Send Port**.</span></span>  
  
4.  <span data-ttu-id="9c0a0-108">**送信ポートのプロパティ**ウィンドウで、送信ポート名**Tutorial_IA_SendRequest_RealTime**します。</span><span class="sxs-lookup"><span data-stu-id="9c0a0-108">In the **Send Port Properties** window, name the send port **Tutorial_IA_SendRequest_RealTime**.</span></span>  
  
5.  <span data-ttu-id="9c0a0-109">**送信ポートのプロパティ**ウィンドウから、**トランスポートの種類**ドロップダウン リストで、 **INTERACT**、順にクリックします**構成**します。</span><span class="sxs-lookup"><span data-stu-id="9c0a0-109">In the **Send Port Properties** window, from the **Transport type** drop-down list, select **INTERACT**, and then click **Configure**.</span></span>  
  
6.  <span data-ttu-id="9c0a0-110">**トランスポートのプロパティの対話** ダイアログ ボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="9c0a0-110">In the **INTERACT Transport Properties** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="9c0a0-111">**これを使用して、**</span><span class="sxs-lookup"><span data-stu-id="9c0a0-111">**Use this**</span></span>|<span data-ttu-id="9c0a0-112">**これを行う**</span><span class="sxs-lookup"><span data-stu-id="9c0a0-112">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="9c0a0-113">**Password**</span><span class="sxs-lookup"><span data-stu-id="9c0a0-113">**Password**</span></span>|<span data-ttu-id="9c0a0-114">SAG 接続に応じて、パスワードを設定します。</span><span class="sxs-lookup"><span data-stu-id="9c0a0-114">Set the password as appropriate for SAG connectivity.</span></span>|  
    |<span data-ttu-id="9c0a0-115">**ユーザー名**</span><span class="sxs-lookup"><span data-stu-id="9c0a0-115">**User name**</span></span>|<span data-ttu-id="9c0a0-116">SAG 接続用の適切なユーザー名を設定します。</span><span class="sxs-lookup"><span data-stu-id="9c0a0-116">Set the user name as appropriate for SAG connectivity.</span></span>|  
    |<span data-ttu-id="9c0a0-117">**アダプターのモード**</span><span class="sxs-lookup"><span data-stu-id="9c0a0-117">**Adapter Mode**</span></span>|<span data-ttu-id="9c0a0-118">ドロップダウン リストから選択**リアルタイム**します。</span><span class="sxs-lookup"><span data-stu-id="9c0a0-118">From the drop-down list, select **RealTime**.</span></span>|  
    |<span data-ttu-id="9c0a0-119">**メッセージの形式**</span><span class="sxs-lookup"><span data-stu-id="9c0a0-119">**Message format**</span></span>|<span data-ttu-id="9c0a0-120">**InteractMessage**します。</span><span class="sxs-lookup"><span data-stu-id="9c0a0-120">**InteractMessage**.</span></span>|  
    |<span data-ttu-id="9c0a0-121">**否認不可のインジケーター**</span><span class="sxs-lookup"><span data-stu-id="9c0a0-121">**Non-Repudiation Indicator**</span></span>|<span data-ttu-id="9c0a0-122">**FALSE**。</span><span class="sxs-lookup"><span data-stu-id="9c0a0-122">**FALSE**.</span></span>|  
    |<span data-ttu-id="9c0a0-123">**要求の種類**</span><span class="sxs-lookup"><span data-stu-id="9c0a0-123">**Request Type**</span></span>|<span data-ttu-id="9c0a0-124">適切な入力\<RequestType\> SWIFT で、プロビジョニングに基づく文字列。</span><span class="sxs-lookup"><span data-stu-id="9c0a0-124">Type the appropriate \<RequestType\> string, based on your provisioning with SWIFT.</span></span>|  
    |<span data-ttu-id="9c0a0-125">**ResponseCrypto**</span><span class="sxs-lookup"><span data-stu-id="9c0a0-125">**ResponseCrypto**</span></span>|<span data-ttu-id="9c0a0-126">**FALSE**。</span><span class="sxs-lookup"><span data-stu-id="9c0a0-126">**FALSE**.</span></span>|  
    |<span data-ttu-id="9c0a0-127">**要求元**</span><span class="sxs-lookup"><span data-stu-id="9c0a0-127">**Requestor**</span></span>|<span data-ttu-id="9c0a0-128">適切な設定\<リクエスター\> SWIFT で、プロビジョニングに基づく文字列。</span><span class="sxs-lookup"><span data-stu-id="9c0a0-128">Set it to the appropriate \<Requestor\> string, based on your provisioning with SWIFT.</span></span>|  
    |<span data-ttu-id="9c0a0-129">**応答側**</span><span class="sxs-lookup"><span data-stu-id="9c0a0-129">**Responder**</span></span>|<span data-ttu-id="9c0a0-130">適切な設定\<レスポンダー\> SWIFT で、プロビジョニングに基づく文字列。</span><span class="sxs-lookup"><span data-stu-id="9c0a0-130">Set it to the appropriate \<Responder\> string, based on your provisioning with SWIFT.</span></span>|  
    |<span data-ttu-id="9c0a0-131">**[サービス名]**</span><span class="sxs-lookup"><span data-stu-id="9c0a0-131">**Service Name**</span></span>|<span data-ttu-id="9c0a0-132">適切な設定\<サービス名\>を基に、SWIFT でプロビジョニングします。</span><span class="sxs-lookup"><span data-stu-id="9c0a0-132">Set it to the appropriate \<service name\>, based on your provisioning with SWIFT.</span></span>|  
    |<span data-ttu-id="9c0a0-133">**配信通知**</span><span class="sxs-lookup"><span data-stu-id="9c0a0-133">**Delivery Notification**</span></span>|<span data-ttu-id="9c0a0-134">ドロップダウン リストから選択**FALSE**します。</span><span class="sxs-lookup"><span data-stu-id="9c0a0-134">From the drop-down list, select  **FALSE**.</span></span>|  
    |<span data-ttu-id="9c0a0-135">**通知キュー**</span><span class="sxs-lookup"><span data-stu-id="9c0a0-135">**Notify queue**</span></span>|<span data-ttu-id="9c0a0-136">SWIFT で、プロビジョニングに基づく、適切なキュー名を入力します。</span><span class="sxs-lookup"><span data-stu-id="9c0a0-136">Type the appropriate queue name, based on your provisioning with SWIFT.</span></span>|  
  
    > [!NOTE]
    >  <span data-ttu-id="9c0a0-137">ペイロードは、転送するのには、専用の場合は"Payloadonly"で、対話を MessageFormat をセットの受信ポートと INTERACT 送信ポート。</span><span class="sxs-lookup"><span data-stu-id="9c0a0-137">If only payload is to be transferred, set the MessageFormat to “Payloadonly” in the INTERACT receive port and INTERACT send port.</span></span> <span data-ttu-id="9c0a0-138">受信を設定し、パススルー パイプラインに送信します。</span><span class="sxs-lookup"><span data-stu-id="9c0a0-138">Set the receive and send pipelines to PassThru.</span></span>  
  
7.  <span data-ttu-id="9c0a0-139">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9c0a0-139">Click **OK**.</span></span>  
  
8.  <span data-ttu-id="9c0a0-140">**送信ポートのプロパティ**ウィンドウで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="9c0a0-140">In the **Send Port Properties** window, do the following:</span></span>  
  
    |<span data-ttu-id="9c0a0-141">**これを使用して、**</span><span class="sxs-lookup"><span data-stu-id="9c0a0-141">**Use this**</span></span>|<span data-ttu-id="9c0a0-142">**これを行う**</span><span class="sxs-lookup"><span data-stu-id="9c0a0-142">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="9c0a0-143">**送信ハンドラー**</span><span class="sxs-lookup"><span data-stu-id="9c0a0-143">**Send handler**</span></span>|<span data-ttu-id="9c0a0-144">ドロップダウン リストから、対話するホストを選択します。</span><span class="sxs-lookup"><span data-stu-id="9c0a0-144">From the drop-down list, select the Interact host.</span></span>|  
    |<span data-ttu-id="9c0a0-145">**送信パイプライン**</span><span class="sxs-lookup"><span data-stu-id="9c0a0-145">**Send pipeline**</span></span>|<span data-ttu-id="9c0a0-146">ドロップダウン リストから選択**XMLTransmit**します。</span><span class="sxs-lookup"><span data-stu-id="9c0a0-146">From the drop-down list, select **XMLTransmit**.</span></span>|  
    |<span data-ttu-id="9c0a0-147">**受信パイプライン**</span><span class="sxs-lookup"><span data-stu-id="9c0a0-147">**Receive pipeline**</span></span>|<span data-ttu-id="9c0a0-148">**[Xmlreceive]**</span><span class="sxs-lookup"><span data-stu-id="9c0a0-148">**XMLReceive**</span></span>|  
  
9. <span data-ttu-id="9c0a0-149">**送信ポートのプロパティ**ウィンドウで、**フィルター**  タブで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="9c0a0-149">In the **Send Port Properties** window, on the **Filters** tab, do the following:</span></span>  
  
    |<span data-ttu-id="9c0a0-150">**これを使用して、**</span><span class="sxs-lookup"><span data-stu-id="9c0a0-150">**Use this**</span></span>|<span data-ttu-id="9c0a0-151">**これを行う**</span><span class="sxs-lookup"><span data-stu-id="9c0a0-151">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="9c0a0-152">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="9c0a0-152">**Property**</span></span>|<span data-ttu-id="9c0a0-153">ドロップダウン リストから選択**BTS します。ReceivePortName**します。</span><span class="sxs-lookup"><span data-stu-id="9c0a0-153">From the drop-down list, select **BTS.ReceivePortName**.</span></span>|  
    |<span data-ttu-id="9c0a0-154">**[演算子]**</span><span class="sxs-lookup"><span data-stu-id="9c0a0-154">**Operator**</span></span>|<span data-ttu-id="9c0a0-155">ドロップダウン リストから選択 **==** します。</span><span class="sxs-lookup"><span data-stu-id="9c0a0-155">From the drop-down list, select **==**.</span></span>|  
    |<span data-ttu-id="9c0a0-156">**[値]**</span><span class="sxs-lookup"><span data-stu-id="9c0a0-156">**Value**</span></span>|<span data-ttu-id="9c0a0-157">型**Tutorial_IA_InputRequest_RealTime**します。</span><span class="sxs-lookup"><span data-stu-id="9c0a0-157">Type **Tutorial_IA_InputRequest_RealTime**.</span></span>|  
    |<span data-ttu-id="9c0a0-158">**グループ化**</span><span class="sxs-lookup"><span data-stu-id="9c0a0-158">**Group by**</span></span>|<span data-ttu-id="9c0a0-159">既定値のままにします。</span><span class="sxs-lookup"><span data-stu-id="9c0a0-159">Leave the default value.</span></span>|  
  
10. <span data-ttu-id="9c0a0-160">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9c0a0-160">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c0a0-161">参照</span><span class="sxs-lookup"><span data-stu-id="9c0a0-161">See Also</span></span>  
 <span data-ttu-id="9c0a0-162">[ステップ 3:作成する送信と受信ポートを InterAct リアルタイム シナリオ](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-the-interact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="9c0a0-162">[Step 3: Create Send and Receive Ports for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-the-interact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="9c0a0-163">[手順 3 a:ファイル受信場所を追加、InterAct リアルタイム シナリオ](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-the-interact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="9c0a0-163">[Step 3A: Add a FILE Receive Location for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-the-interact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="9c0a0-164">[手順 3 b:INTERACT の受信場所を追加、InterAct リアルタイム シナリオ](../../adapters-and-accelerators/fileact-interact/step-3b-add-an-interact-receive-location-for-the-interact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="9c0a0-164">[Step 3B: Add an INTERACT Receive Location for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3b-add-an-interact-receive-location-for-the-interact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="9c0a0-165">[手順 3 C:用に Sw:HandleRequest メッセージをキャプチャする FILE 送信ポートを追加、InterAct リアルタイム シナリオ](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlerequest-interact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="9c0a0-165">[Step 3C: Add a FILE Send Port to Capture the Sw:HandleRequest Message for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlerequest-interact-real-time-scenario.md) </span></span>  
 [<span data-ttu-id="9c0a0-166">手順 3 D:用に Sw:HandleResponse メッセージをキャプチャする FILE 送信ポートを追加、InterAct リアルタイム シナリオ</span><span class="sxs-lookup"><span data-stu-id="9c0a0-166">Step 3D: Add a FILE Send Port to Capture the Sw:HandleResponse Message for the InterAct Real-Time Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-3d-add-file-send-port-to-get-sw-handleresponse-message-for-interact.md)