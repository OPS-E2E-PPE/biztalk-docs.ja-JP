---
title: 手順 3 D:InterAct ストア アンド フォワード シナリオ用に INTERACT 送信ポートの追加 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cd126d9a-f4e4-429e-bab0-8b4c9c555e36
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 55dcfb21444cfdd38faf6e9100d9ff4c9307450b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65365539"
---
# <a name="step-3d-add-an-interact-send-port-for-the-interact-store-and-forward-scenario"></a><span data-ttu-id="a9e59-102">手順 3 D:InterAct ストア アンド フォワード シナリオ用に INTERACT 送信ポートを追加します。</span><span class="sxs-lookup"><span data-stu-id="a9e59-102">Step 3D: Add an INTERACT Send Port for the InterAct Store and Forward Scenario</span></span>
<span data-ttu-id="a9e59-103">完全な[手順 3 C:InterAct ストア アンド フォワード シナリオ用に Sw:HandleRequest メッセージをキャプチャする FILE 送信ポートの追加](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlerequest-interact-store-and-forward.md)この手順を開始する前にします。</span><span class="sxs-lookup"><span data-stu-id="a9e59-103">Complete [Step 3C: Add a FILE Send Port to Capture the Sw:HandleRequest Message for the InterAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlerequest-interact-store-and-forward.md) before you begin this step.</span></span>
  
## <a name="add-an-interact-send-port"></a><span data-ttu-id="a9e59-104">INTERACT 送信ポートを追加します。</span><span class="sxs-lookup"><span data-stu-id="a9e59-104">Add an INTERACT send port</span></span>  
  
1.  <span data-ttu-id="a9e59-105">開始**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="a9e59-105">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="a9e59-106">コンソール ツリーで、BizTalk グループを展開し、送信ポートを作成する BizTalk アプリケーションを順に展開します。</span><span class="sxs-lookup"><span data-stu-id="a9e59-106">In the console tree, expand the BizTalk group, and then expand the BizTalk application for which you want to create a send port.</span></span>  
  
3.  <span data-ttu-id="a9e59-107">右クリック**送信ポート**、 をポイント**新規**、 をクリックし、**静的な送信請求-応答送信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="a9e59-107">Right-click **Send Ports**, point to **New**, and then click **Static Solicit-Response Send Port**.</span></span>  
  
4.  <span data-ttu-id="a9e59-108">**送信ポートのプロパティ**ウィンドウで、名前、送信ポート Tutorial_IA_SendRequest_SnF します。</span><span class="sxs-lookup"><span data-stu-id="a9e59-108">In the **Send Port Properties** window, name the send port, Tutorial_IA_SendRequest_SnF.</span></span>  
  
5.  <span data-ttu-id="a9e59-109">**送信ポートのプロパティ**ウィンドウから、**トランスポートの種類**ドロップダウン リストで、 **INTERACT**、順にクリックします**構成**します。</span><span class="sxs-lookup"><span data-stu-id="a9e59-109">In the **Send Port Properties** window, from the **Transport type** drop-down list, select **INTERACT**, and then click **Configure**.</span></span>  
  
6.  <span data-ttu-id="a9e59-110">**トランスポートのプロパティの対話** ダイアログ ボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="a9e59-110">In the **INTERACT Transport Properties** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="a9e59-111">**これを使用して、**</span><span class="sxs-lookup"><span data-stu-id="a9e59-111">**Use this**</span></span>|<span data-ttu-id="a9e59-112">**これを行う**</span><span class="sxs-lookup"><span data-stu-id="a9e59-112">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="a9e59-113">**Password**</span><span class="sxs-lookup"><span data-stu-id="a9e59-113">**Password**</span></span>|<span data-ttu-id="a9e59-114">SAG 接続に応じて、パスワードを設定します。</span><span class="sxs-lookup"><span data-stu-id="a9e59-114">Set the password as appropriate for SAG connectivity.</span></span>|  
    |<span data-ttu-id="a9e59-115">**ユーザー名**</span><span class="sxs-lookup"><span data-stu-id="a9e59-115">**User name**</span></span>|<span data-ttu-id="a9e59-116">SAG 接続用の適切なユーザー名を設定します。</span><span class="sxs-lookup"><span data-stu-id="a9e59-116">Set the user name as appropriate for SAG connectivity.</span></span>|  
    |<span data-ttu-id="a9e59-117">**メッセージの形式**</span><span class="sxs-lookup"><span data-stu-id="a9e59-117">**Message format**</span></span>|<span data-ttu-id="a9e59-118">**InteractMessage**</span><span class="sxs-lookup"><span data-stu-id="a9e59-118">**InteractMessage**</span></span>|  
    |<span data-ttu-id="a9e59-119">**否認不可のインジケーター**</span><span class="sxs-lookup"><span data-stu-id="a9e59-119">**Non-Repudiation Indicator**</span></span>|<span data-ttu-id="a9e59-120">**FALSE**</span><span class="sxs-lookup"><span data-stu-id="a9e59-120">**FALSE**</span></span>|  
    |<span data-ttu-id="a9e59-121">**要求の種類**</span><span class="sxs-lookup"><span data-stu-id="a9e59-121">**Request Type**</span></span>|<span data-ttu-id="a9e59-122">適切な入力\<RequestType\> SWIFT で、プロビジョニングに基づく文字列。</span><span class="sxs-lookup"><span data-stu-id="a9e59-122">Type the appropriate \<RequestType\> string, based on your provisioning with SWIFT.</span></span>|  
    |<span data-ttu-id="a9e59-123">**ResponseCrypto**</span><span class="sxs-lookup"><span data-stu-id="a9e59-123">**ResponseCrypto**</span></span>|<span data-ttu-id="a9e59-124">**FALSE**</span><span class="sxs-lookup"><span data-stu-id="a9e59-124">**FALSE**</span></span>|  
    |<span data-ttu-id="a9e59-125">**要求元**</span><span class="sxs-lookup"><span data-stu-id="a9e59-125">**Requestor**</span></span>|<span data-ttu-id="a9e59-126">適切な入力\<RequestorDN\> SWIFT で、プロビジョニングに基づく文字列。</span><span class="sxs-lookup"><span data-stu-id="a9e59-126">Type the appropriate \<RequestorDN\> string, based on your provisioning with SWIFT.</span></span>|  
    |<span data-ttu-id="a9e59-127">**応答側**</span><span class="sxs-lookup"><span data-stu-id="a9e59-127">**Responder**</span></span>|<span data-ttu-id="a9e59-128">適切な入力\<ResponderDN\> SWIFT で、プロビジョニングに基づく文字列。</span><span class="sxs-lookup"><span data-stu-id="a9e59-128">Type the appropriate \<ResponderDN\> string, based on your provisioning with SWIFT.</span></span>|  
    |<span data-ttu-id="a9e59-129">**[サービス名]**</span><span class="sxs-lookup"><span data-stu-id="a9e59-129">**Service Name**</span></span>|<span data-ttu-id="a9e59-130">適切な入力\<サービス名\>を基に、SWIFT でプロビジョニングします。</span><span class="sxs-lookup"><span data-stu-id="a9e59-130">Type the appropriate \<service name\>, based on your provisioning with SWIFT.</span></span>|  
    |<span data-ttu-id="a9e59-131">**配信通知**</span><span class="sxs-lookup"><span data-stu-id="a9e59-131">**Delivery Notification**</span></span>|<span data-ttu-id="a9e59-132">ドロップダウン リストから選択**FALSE**します。</span><span class="sxs-lookup"><span data-stu-id="a9e59-132">From the drop-down list, select **FALSE**.</span></span>|  
    |<span data-ttu-id="a9e59-133">**通知キュー**</span><span class="sxs-lookup"><span data-stu-id="a9e59-133">**Notify queue**</span></span>|<span data-ttu-id="a9e59-134">SWIFT で、プロビジョニングに基づく、適切なキュー名を入力します。</span><span class="sxs-lookup"><span data-stu-id="a9e59-134">Type the appropriate queue name, based on your provisioning with SWIFT.</span></span>|  
  
    > [!NOTE]
    >  <span data-ttu-id="a9e59-135">ペイロードは、転送するのには、専用の場合、INTERACT で「ペイロード」MessageFormat をセットの受信ポートと INTERACT 送信ポート。</span><span class="sxs-lookup"><span data-stu-id="a9e59-135">If only payload is to be transferred, set the MessageFormat to “Payload” in the INTERACT receive port and INTERACT send port.</span></span> <span data-ttu-id="a9e59-136">PassThru には、受信と送信パイプラインを設定します。</span><span class="sxs-lookup"><span data-stu-id="a9e59-136">Set the Receive and Send pipelines to PassThru.</span></span>  
  
7.  <span data-ttu-id="a9e59-137">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a9e59-137">Click **OK**.</span></span>  
  
8.  <span data-ttu-id="a9e59-138">**送信ポートのプロパティ**ウィンドウで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="a9e59-138">In the **Send Port Properties** window, do the following:</span></span>  
  
    |<span data-ttu-id="a9e59-139">**これを使用して、**</span><span class="sxs-lookup"><span data-stu-id="a9e59-139">**Use this**</span></span>|<span data-ttu-id="a9e59-140">**これを行う**</span><span class="sxs-lookup"><span data-stu-id="a9e59-140">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="a9e59-141">**送信ハンドラー**</span><span class="sxs-lookup"><span data-stu-id="a9e59-141">**Send handler**</span></span>|<span data-ttu-id="a9e59-142">ドロップダウン リストから、対話するホストを選択します。</span><span class="sxs-lookup"><span data-stu-id="a9e59-142">From the drop-down list, select the Interact host.</span></span>|  
    |<span data-ttu-id="a9e59-143">**送信パイプライン**</span><span class="sxs-lookup"><span data-stu-id="a9e59-143">**Send pipeline**</span></span>|<span data-ttu-id="a9e59-144">ドロップダウン リストから選択**XMLTransmit**します。</span><span class="sxs-lookup"><span data-stu-id="a9e59-144">From the drop-down list, select **XMLTransmit**.</span></span>|  
    |<span data-ttu-id="a9e59-145">**受信パイプライン**</span><span class="sxs-lookup"><span data-stu-id="a9e59-145">**Receive pipeline**</span></span>|<span data-ttu-id="a9e59-146">ドロップダウン リストから選択**XMLReceive**します。</span><span class="sxs-lookup"><span data-stu-id="a9e59-146">From the drop-down list, select **XMLReceive**.</span></span>|  
  
9. <span data-ttu-id="a9e59-147">**送信ポートのプロパティ**ウィンドウで、**フィルター**  タブで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="a9e59-147">In the **Send Port Properties** window, on the **Filters** tab, do the following:</span></span>  
  
    |<span data-ttu-id="a9e59-148">**これを使用して、**</span><span class="sxs-lookup"><span data-stu-id="a9e59-148">**Use this**</span></span>|<span data-ttu-id="a9e59-149">**これを行う**</span><span class="sxs-lookup"><span data-stu-id="a9e59-149">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="a9e59-150">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="a9e59-150">**Property**</span></span>|<span data-ttu-id="a9e59-151">ドロップダウン リストから選択**BTS します。ReceivePortName**します。</span><span class="sxs-lookup"><span data-stu-id="a9e59-151">From the drop-down list, select **BTS.ReceivePortName**.</span></span>|  
    |<span data-ttu-id="a9e59-152">**[演算子]**</span><span class="sxs-lookup"><span data-stu-id="a9e59-152">**Operator**</span></span>|<span data-ttu-id="a9e59-153">ドロップダウン リストから選択 **==** します。</span><span class="sxs-lookup"><span data-stu-id="a9e59-153">From the drop-down list, select **==**.</span></span>|  
    |<span data-ttu-id="a9e59-154">**[値]**</span><span class="sxs-lookup"><span data-stu-id="a9e59-154">**Value**</span></span>|<span data-ttu-id="a9e59-155">型 Tutorial_IA_InputRequest_SnF します。</span><span class="sxs-lookup"><span data-stu-id="a9e59-155">Type Tutorial_IA_InputRequest_SnF.</span></span>|  
    |<span data-ttu-id="a9e59-156">**グループ化**</span><span class="sxs-lookup"><span data-stu-id="a9e59-156">**Group by**</span></span>|<span data-ttu-id="a9e59-157">既定値のままにします。</span><span class="sxs-lookup"><span data-stu-id="a9e59-157">Leave the default value.</span></span>|  
  
10. <span data-ttu-id="a9e59-158">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a9e59-158">Click **OK**.</span></span>  
  
## <a name="complete-steps"></a><span data-ttu-id="a9e59-159">手順を完了します</span><span class="sxs-lookup"><span data-stu-id="a9e59-159">Complete steps</span></span>
 <span data-ttu-id="a9e59-160">[ステップ 3:送信ポートの作成し、InterAct ストア アンド フォワード シナリオ用の受信ポート](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-interact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="a9e59-160">[Step 3: Create Send Ports and Receive Ports for the InterAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-interact-store-and-forward-scenario.md) </span></span>  
 <span data-ttu-id="a9e59-161">[手順 3 a:InterAct ストア アンド フォワード シナリオ用の場所の受信ファイルを追加します。](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-interact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="a9e59-161">[Step 3A: Add a FILE Receive Location for the InterAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-interact-store-and-forward-scenario.md) </span></span>  
 <span data-ttu-id="a9e59-162">[手順 3 b:INTERACT の受信場所 InterAct ストア アンド フォワード シナリオ用の追加します。](../../adapters-and-accelerators/fileact-interact/step-3b-add-interact-receive-location-for-interact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="a9e59-162">[Step 3B: Add an INTERACT Receive Location for the InterAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-3b-add-interact-receive-location-for-interact-store-and-forward-scenario.md) </span></span>  
 [<span data-ttu-id="a9e59-163">手順 3 C:InterAct ストア アンド フォワード シナリオ用に Sw:HandleRequest メッセージをキャプチャする FILE 送信ポートの追加します。</span><span class="sxs-lookup"><span data-stu-id="a9e59-163">Step 3C: Add a FILE Send Port to Capture the Sw:HandleRequest Message for the InterAct Store and Forward Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlerequest-interact-store-and-forward.md)  