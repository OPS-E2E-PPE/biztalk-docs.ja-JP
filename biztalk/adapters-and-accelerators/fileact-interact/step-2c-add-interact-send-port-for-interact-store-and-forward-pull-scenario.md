---
title: 手順 2 C:InterAct ストア アンド フォワード (プル) シナリオ用に INTERACT 送信ポートの追加 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 57038f77-85c3-4811-ab3d-df6e2da8fbcf
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3373f7653856800c3cb8a64ca07afe88eb86d192
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65366109"
---
# <a name="step-2c-add-an-interact-send-port-for-the-interact-store-and-forward-pull-scenario"></a><span data-ttu-id="02651-102">手順 2 C:InterAct ストア アンド フォワード (プル) シナリオ用に INTERACT 送信ポートを追加します。</span><span class="sxs-lookup"><span data-stu-id="02651-102">Step 2C: Add an INTERACT Send Port for the InterAct Store and Forward (Pull) Scenario</span></span>
<span data-ttu-id="02651-103">この手順を開始する前に行う必要があります[手順 2 b:InterAct ストア アンド フォワード (プル) シナリオ用に Sw:HandleRequest メッセージをキャプチャするファイルの送信ポートを追加](../../adapters-and-accelerators/fileact-interact/step-2b-add-file-send-ports-to-get-sw-handlerequest-message-for-interact.md)します。</span><span class="sxs-lookup"><span data-stu-id="02651-103">Before you begin this step, you must complete [Step 2B: Add FILE Send Ports to Capture the Sw:HandleRequest Message for the InterAct Store and Forward (Pull) Scenario](../../adapters-and-accelerators/fileact-interact/step-2b-add-file-send-ports-to-get-sw-handlerequest-message-for-interact.md).</span></span>  
  
### <a name="to-add-an-interact-send-port"></a><span data-ttu-id="02651-104">INTERACT 送信ポートを追加するには</span><span class="sxs-lookup"><span data-stu-id="02651-104">To add an INTERACT send port</span></span>  
  
1.  <span data-ttu-id="02651-105">開始**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="02651-105">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="02651-106">コンソール ツリーで、BizTalk グループを展開し、送信ポートを作成する BizTalk アプリケーションを順に展開します。</span><span class="sxs-lookup"><span data-stu-id="02651-106">In the console tree, expand the BizTalk group, and then expand the BizTalk application for which you want to create a send port.</span></span>  
  
3.  <span data-ttu-id="02651-107">右クリック**送信ポート**、 をポイント**新規**、 をクリックし、**静的な送信請求-応答送信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="02651-107">Right-click **Send Ports**, point to **New**, and then click **Static Solicit-Response Send Port**.</span></span>  
  
4.  <span data-ttu-id="02651-108">**送信ポートのプロパティ**ウィンドウで、送信ポート名**Tutorial_IA_SendRequest_SnF**します。</span><span class="sxs-lookup"><span data-stu-id="02651-108">In the **Send Port Properties** window, name the send port, **Tutorial_IA_SendRequest_SnF**.</span></span>  
  
5.  <span data-ttu-id="02651-109">**送信ポートのプロパティ**ウィンドウから、**トランスポートの種類**ドロップダウン リストで、 **INTERACT**、順にクリックします**構成**します。</span><span class="sxs-lookup"><span data-stu-id="02651-109">In the **Send Port Properties** window, from the **Transport type** drop-down list, select **INTERACT**, and then click **Configure**.</span></span>  
  
6.  <span data-ttu-id="02651-110">**トランスポートのプロパティの対話** ダイアログ ボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="02651-110">In the **INTERACT Transport Properties** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="02651-111">**これを使用して、**</span><span class="sxs-lookup"><span data-stu-id="02651-111">**Use this**</span></span>|<span data-ttu-id="02651-112">**これを行う**</span><span class="sxs-lookup"><span data-stu-id="02651-112">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="02651-113">**Password**</span><span class="sxs-lookup"><span data-stu-id="02651-113">**Password**</span></span>|<span data-ttu-id="02651-114">SAG 接続に応じて、パスワードを設定します。</span><span class="sxs-lookup"><span data-stu-id="02651-114">Set the password as appropriate for SAG connectivity.</span></span>|  
    |<span data-ttu-id="02651-115">**ユーザー名**</span><span class="sxs-lookup"><span data-stu-id="02651-115">**User name**</span></span>|<span data-ttu-id="02651-116">SAG 接続用の適切なユーザー名を設定します。</span><span class="sxs-lookup"><span data-stu-id="02651-116">Set the user name as appropriate for SAG connectivity.</span></span>|  
    |<span data-ttu-id="02651-117">**メッセージの形式**</span><span class="sxs-lookup"><span data-stu-id="02651-117">**Message format**</span></span>|<span data-ttu-id="02651-118">**InteractMessage**</span><span class="sxs-lookup"><span data-stu-id="02651-118">**InteractMessage**</span></span>|  
    |<span data-ttu-id="02651-119">**否認不可のインジケーター**</span><span class="sxs-lookup"><span data-stu-id="02651-119">**Non-Repudiation Indicator**</span></span>|<span data-ttu-id="02651-120">**FALSE**</span><span class="sxs-lookup"><span data-stu-id="02651-120">**FALSE**</span></span>|  
    |<span data-ttu-id="02651-121">**要求の種類**</span><span class="sxs-lookup"><span data-stu-id="02651-121">**Request Type**</span></span>|<span data-ttu-id="02651-122">適切な入力\<RequestType\> SWIFT で、プロビジョニングに基づく文字列。</span><span class="sxs-lookup"><span data-stu-id="02651-122">Type the appropriate \<RequestType\> string, based on your provisioning with SWIFT.</span></span>|  
    |<span data-ttu-id="02651-123">**ResponseCrypto**</span><span class="sxs-lookup"><span data-stu-id="02651-123">**ResponseCrypto**</span></span>|<span data-ttu-id="02651-124">**FALSE**</span><span class="sxs-lookup"><span data-stu-id="02651-124">**FALSE**</span></span>|  
    |<span data-ttu-id="02651-125">**要求元**</span><span class="sxs-lookup"><span data-stu-id="02651-125">**Requestor**</span></span>|<span data-ttu-id="02651-126">適切な入力\<RequestorDN\> SWIFT で、プロビジョニングに基づく文字列。</span><span class="sxs-lookup"><span data-stu-id="02651-126">Type the appropriate \<RequestorDN\> string, based on your provisioning with SWIFT.</span></span>|  
    |<span data-ttu-id="02651-127">**応答側**</span><span class="sxs-lookup"><span data-stu-id="02651-127">**Responder**</span></span>|<span data-ttu-id="02651-128">適切な入力\<ResponderDN\> SWIFT で、プロビジョニングに基づく文字列。</span><span class="sxs-lookup"><span data-stu-id="02651-128">Type the appropriate \<ResponderDN\> string, based on your provisioning with SWIFT.</span></span>|  
    |<span data-ttu-id="02651-129">**[サービス名]**</span><span class="sxs-lookup"><span data-stu-id="02651-129">**Service Name**</span></span>|<span data-ttu-id="02651-130">適切な入力\<サービス名\>を基に、SWIFT でプロビジョニングします。</span><span class="sxs-lookup"><span data-stu-id="02651-130">Type the appropriate \<service name\>, based on your provisioning with SWIFT.</span></span>|  
    |<span data-ttu-id="02651-131">**配信通知**</span><span class="sxs-lookup"><span data-stu-id="02651-131">**Delivery Notification**</span></span>|<span data-ttu-id="02651-132">ドロップダウン リストから選択**FALSE**します。</span><span class="sxs-lookup"><span data-stu-id="02651-132">From the drop-down list, select **FALSE**.</span></span>|  
    |<span data-ttu-id="02651-133">**通知キュー**</span><span class="sxs-lookup"><span data-stu-id="02651-133">**Notify queue**</span></span>|<span data-ttu-id="02651-134">SWIFT で、プロビジョニングに基づく、適切なキュー名を入力します。</span><span class="sxs-lookup"><span data-stu-id="02651-134">Type the appropriate queue name, based on your provisioning with SWIFT.</span></span>|  
  
    > [!NOTE]
    >  <span data-ttu-id="02651-135">ペイロードは、転送するのには、専用の場合、INTERACT で「ペイロード」MessageFormat をセットの受信ポートと INTERACT 送信ポート。</span><span class="sxs-lookup"><span data-stu-id="02651-135">If only payload is to be transferred, set the MessageFormat to “Payload” in the INTERACT receive port and INTERACT send port.</span></span> <span data-ttu-id="02651-136">PassThru には、受信と送信パイプラインを設定します。</span><span class="sxs-lookup"><span data-stu-id="02651-136">Set the Receive and Send pipelines to PassThru.</span></span>  
  
7.  <span data-ttu-id="02651-137">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="02651-137">Click **OK**.</span></span>  
  
8.  <span data-ttu-id="02651-138">**送信ポートのプロパティ**ウィンドウで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="02651-138">In the **Send Port Properties** window, do the following:</span></span>  
  
    |<span data-ttu-id="02651-139">**これを使用して、**</span><span class="sxs-lookup"><span data-stu-id="02651-139">**Use this**</span></span>|<span data-ttu-id="02651-140">**これを行う**</span><span class="sxs-lookup"><span data-stu-id="02651-140">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="02651-141">**送信ハンドラー**</span><span class="sxs-lookup"><span data-stu-id="02651-141">**Send handler**</span></span>|<span data-ttu-id="02651-142">ドロップダウン リストから、対話するホストを選択します。</span><span class="sxs-lookup"><span data-stu-id="02651-142">From the drop-down list, select the Interact host.</span></span>|  
    |<span data-ttu-id="02651-143">**送信パイプライン**</span><span class="sxs-lookup"><span data-stu-id="02651-143">**Send pipeline**</span></span>|<span data-ttu-id="02651-144">ドロップダウン リストから選択**XMLTransmit**します。</span><span class="sxs-lookup"><span data-stu-id="02651-144">From the drop-down list, select **XMLTransmit**.</span></span>|  
    |<span data-ttu-id="02651-145">**受信パイプライン**</span><span class="sxs-lookup"><span data-stu-id="02651-145">**Receive pipeline**</span></span>|<span data-ttu-id="02651-146">ドロップダウン リストから選択**XMLReceive**します。</span><span class="sxs-lookup"><span data-stu-id="02651-146">From the drop-down list, select **XMLReceive**.</span></span>|  
  
9. <span data-ttu-id="02651-147">**送信ポートのプロパティ**ウィンドウで、**フィルター**  タブで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="02651-147">In the **Send Port Properties** window, on the **Filters** tab, do the following:</span></span>  
  
    |<span data-ttu-id="02651-148">**これを使用して、**</span><span class="sxs-lookup"><span data-stu-id="02651-148">**Use this**</span></span>|<span data-ttu-id="02651-149">**これを行う**</span><span class="sxs-lookup"><span data-stu-id="02651-149">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="02651-150">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="02651-150">**Property**</span></span>|<span data-ttu-id="02651-151">ドロップダウン リストから選択**BTS します。ReceivePortName**します。</span><span class="sxs-lookup"><span data-stu-id="02651-151">From the drop-down list, select **BTS.ReceivePortName**.</span></span>|  
    |<span data-ttu-id="02651-152">**[演算子]**</span><span class="sxs-lookup"><span data-stu-id="02651-152">**Operator**</span></span>|<span data-ttu-id="02651-153">ドロップダウン リストから選択 **==** します。</span><span class="sxs-lookup"><span data-stu-id="02651-153">From the drop-down list, select **==**.</span></span>|  
    |<span data-ttu-id="02651-154">**[値]**</span><span class="sxs-lookup"><span data-stu-id="02651-154">**Value**</span></span>|<span data-ttu-id="02651-155">型**Tutorial_IA_InputRequest_SnF**します。</span><span class="sxs-lookup"><span data-stu-id="02651-155">Type **Tutorial_IA_InputRequest_SnF**.</span></span>|  
    |<span data-ttu-id="02651-156">**グループ化**</span><span class="sxs-lookup"><span data-stu-id="02651-156">**Group by**</span></span>|<span data-ttu-id="02651-157">既定値のままにします。</span><span class="sxs-lookup"><span data-stu-id="02651-157">Leave the default value.</span></span>|  
  
10. <span data-ttu-id="02651-158">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="02651-158">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02651-159">参照</span><span class="sxs-lookup"><span data-stu-id="02651-159">See Also</span></span>  
 <span data-ttu-id="02651-160">[手順 2 a:ファイル受信 InterAct ストア アンド フォワード (プル) シナリオ用の場所を追加します。](../../adapters-and-accelerators/fileact-interact/step-2a-add-file-receive-locations-for-interact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="02651-160">[Step 2A: Add FILE Receive Locations for the InterAct Store and Forward (Pull) Scenario](../../adapters-and-accelerators/fileact-interact/step-2a-add-file-receive-locations-for-interact-store-and-forward-scenario.md) </span></span>  
 [<span data-ttu-id="02651-161">手順 2 b:InterAct ストア アンド フォワード (プル) シナリオ用に Sw:HandleRequest メッセージをキャプチャするファイルの送信ポートの追加します。</span><span class="sxs-lookup"><span data-stu-id="02651-161">Step 2B: Add FILE Send Ports to Capture the Sw:HandleRequest Message for the InterAct Store and Forward (Pull) Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-2b-add-file-send-ports-to-get-sw-handlerequest-message-for-interact.md)