---
title: "手順 2 C: InterAct ストア アンド フォワード (プル) シナリオの対話の送信ポートを追加 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 57038f77-85c3-4811-ab3d-df6e2da8fbcf
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e2fe383d80c467376852067026a7c5a4fe4640ba
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-2c-add-an-interact-send-port-for-the-interact-store-and-forward-pull-scenario"></a><span data-ttu-id="7467f-102">手順 2 C: InterAct ストア アンド フォワード (プル) シナリオの対話の送信ポートを追加</span><span class="sxs-lookup"><span data-stu-id="7467f-102">Step 2C: Add an INTERACT Send Port for the InterAct Store and Forward (Pull) Scenario</span></span>
<span data-ttu-id="7467f-103">この手順を開始する前に行う必要があります[Step 2B: InterAct ストア アンド フォワード (プル) シナリオの Sw:HandleRequest メッセージをキャプチャする FILE 送信ポートの追加](../../adapters-and-accelerators/fileact-interact/step-2b-add-file-send-ports-to-get-sw-handlerequest-message-for-interact.md)です。</span><span class="sxs-lookup"><span data-stu-id="7467f-103">Before you begin this step, you must complete [Step 2B: Add FILE Send Ports to Capture the Sw:HandleRequest Message for the InterAct Store and Forward (Pull) Scenario](../../adapters-and-accelerators/fileact-interact/step-2b-add-file-send-ports-to-get-sw-handlerequest-message-for-interact.md).</span></span>  
  
### <a name="to-add-an-interact-send-port"></a><span data-ttu-id="7467f-104">対話する送信ポートを追加するには</span><span class="sxs-lookup"><span data-stu-id="7467f-104">To add an INTERACT send port</span></span>  
  
1.  <span data-ttu-id="7467f-105">開始**BizTalk Server 管理**です。</span><span class="sxs-lookup"><span data-stu-id="7467f-105">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="7467f-106">コンソール ツリーで、BizTalk グループを展開し、送信ポートを作成する BizTalk アプリケーションの順に展開します。</span><span class="sxs-lookup"><span data-stu-id="7467f-106">In the console tree, expand the BizTalk group, and then expand the BizTalk application for which you want to create a send port.</span></span>  
  
3.  <span data-ttu-id="7467f-107">右クリック**送信ポート**、 をポイント**新規**、クリックして**静的な送信請求-応答送信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="7467f-107">Right-click **Send Ports**, point to **New**, and then click **Static Solicit-Response Send Port**.</span></span>  
  
4.  <span data-ttu-id="7467f-108">**送信ポートのプロパティ**ウィンドウで、名前、送信ポートを**Tutorial_IA_SendRequest_SnF**です。</span><span class="sxs-lookup"><span data-stu-id="7467f-108">In the **Send Port Properties** window, name the send port, **Tutorial_IA_SendRequest_SnF**.</span></span>  
  
5.  <span data-ttu-id="7467f-109">**送信ポートのプロパティ** ウィンドウから、**トランスポートの種類**ドロップダウン リストで、 **INTERACT**、順にクリック**構成**です。</span><span class="sxs-lookup"><span data-stu-id="7467f-109">In the **Send Port Properties** window, from the **Transport type** drop-down list, select **INTERACT**, and then click **Configure**.</span></span>  
  
6.  <span data-ttu-id="7467f-110">**トランスポートのプロパティの対話** ダイアログ ボックスで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="7467f-110">In the **INTERACT Transport Properties** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="7467f-111">**これを使用してください。**</span><span class="sxs-lookup"><span data-stu-id="7467f-111">**Use this**</span></span>|<span data-ttu-id="7467f-112">**これを行う**</span><span class="sxs-lookup"><span data-stu-id="7467f-112">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="7467f-113">**Password**</span><span class="sxs-lookup"><span data-stu-id="7467f-113">**Password**</span></span>|<span data-ttu-id="7467f-114">SAG 接続適切なパスワードを設定します。</span><span class="sxs-lookup"><span data-stu-id="7467f-114">Set the password as appropriate for SAG connectivity.</span></span>|  
    |<span data-ttu-id="7467f-115">**ユーザー名**</span><span class="sxs-lookup"><span data-stu-id="7467f-115">**User name**</span></span>|<span data-ttu-id="7467f-116">SAG 接続を適切なユーザー名を設定します。</span><span class="sxs-lookup"><span data-stu-id="7467f-116">Set the user name as appropriate for SAG connectivity.</span></span>|  
    |<span data-ttu-id="7467f-117">**メッセージの形式**</span><span class="sxs-lookup"><span data-stu-id="7467f-117">**Message format**</span></span>|<span data-ttu-id="7467f-118">**InteractMessage**</span><span class="sxs-lookup"><span data-stu-id="7467f-118">**InteractMessage**</span></span>|  
    |<span data-ttu-id="7467f-119">**否認不可インジケーター**</span><span class="sxs-lookup"><span data-stu-id="7467f-119">**Non-Repudiation Indicator**</span></span>|<span data-ttu-id="7467f-120">**FALSE**</span><span class="sxs-lookup"><span data-stu-id="7467f-120">**FALSE**</span></span>|  
    |<span data-ttu-id="7467f-121">**要求の種類**</span><span class="sxs-lookup"><span data-stu-id="7467f-121">**Request Type**</span></span>|<span data-ttu-id="7467f-122">適切な入力\<RequestType > SWIFT でのプロビジョニングに基づく文字列。</span><span class="sxs-lookup"><span data-stu-id="7467f-122">Type the appropriate \<RequestType> string, based on your provisioning with SWIFT.</span></span>|  
    |<span data-ttu-id="7467f-123">**ResponseCrypto**</span><span class="sxs-lookup"><span data-stu-id="7467f-123">**ResponseCrypto**</span></span>|<span data-ttu-id="7467f-124">**FALSE**</span><span class="sxs-lookup"><span data-stu-id="7467f-124">**FALSE**</span></span>|  
    |<span data-ttu-id="7467f-125">**要求元**</span><span class="sxs-lookup"><span data-stu-id="7467f-125">**Requestor**</span></span>|<span data-ttu-id="7467f-126">適切な入力\<RequestorDN > SWIFT でのプロビジョニングに基づく文字列。</span><span class="sxs-lookup"><span data-stu-id="7467f-126">Type the appropriate \<RequestorDN> string, based on your provisioning with SWIFT.</span></span>|  
    |<span data-ttu-id="7467f-127">**応答側**</span><span class="sxs-lookup"><span data-stu-id="7467f-127">**Responder**</span></span>|<span data-ttu-id="7467f-128">適切な入力\<ResponderDN > SWIFT でのプロビジョニングに基づく文字列。</span><span class="sxs-lookup"><span data-stu-id="7467f-128">Type the appropriate \<ResponderDN> string, based on your provisioning with SWIFT.</span></span>|  
    |<span data-ttu-id="7467f-129">**サービス名**</span><span class="sxs-lookup"><span data-stu-id="7467f-129">**Service Name**</span></span>|<span data-ttu-id="7467f-130">適切な入力\<サービス名 > SWIFT でのプロビジョニングに基づきます。</span><span class="sxs-lookup"><span data-stu-id="7467f-130">Type the appropriate \<service name>, based on your provisioning with SWIFT.</span></span>|  
    |<span data-ttu-id="7467f-131">**配信通知**</span><span class="sxs-lookup"><span data-stu-id="7467f-131">**Delivery Notification**</span></span>|<span data-ttu-id="7467f-132">ドロップダウン リストから選択**FALSE**です。</span><span class="sxs-lookup"><span data-stu-id="7467f-132">From the drop-down list, select **FALSE**.</span></span>|  
    |<span data-ttu-id="7467f-133">**通知キュー**</span><span class="sxs-lookup"><span data-stu-id="7467f-133">**Notify queue**</span></span>|<span data-ttu-id="7467f-134">SWIFT でのプロビジョニングに基づく、適切なキュー名を入力します。</span><span class="sxs-lookup"><span data-stu-id="7467f-134">Type the appropriate queue name, based on your provisioning with SWIFT.</span></span>|  
  
    > [!NOTE]
    >  <span data-ttu-id="7467f-135">ペイロードは、転送するのには、専用の場合は、ポートと対話する送信ポートが受信の対話で「ペイロード」に MessageFormat を設定します。</span><span class="sxs-lookup"><span data-stu-id="7467f-135">If only payload is to be transferred, set the MessageFormat to “Payload” in the INTERACT receive port and INTERACT send port.</span></span> <span data-ttu-id="7467f-136">PassThru に、受信パイプラインと送信パイプラインを設定します。</span><span class="sxs-lookup"><span data-stu-id="7467f-136">Set the Receive and Send pipelines to PassThru.</span></span>  
  
7.  <span data-ttu-id="7467f-137">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7467f-137">Click **OK**.</span></span>  
  
8.  <span data-ttu-id="7467f-138">**送信ポートのプロパティ** ウィンドウで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="7467f-138">In the **Send Port Properties** window, do the following:</span></span>  
  
    |<span data-ttu-id="7467f-139">**これを使用してください。**</span><span class="sxs-lookup"><span data-stu-id="7467f-139">**Use this**</span></span>|<span data-ttu-id="7467f-140">**これを行う**</span><span class="sxs-lookup"><span data-stu-id="7467f-140">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="7467f-141">**送信ハンドラー**</span><span class="sxs-lookup"><span data-stu-id="7467f-141">**Send handler**</span></span>|<span data-ttu-id="7467f-142">ドロップダウン リストから、対話ホストを選択します。</span><span class="sxs-lookup"><span data-stu-id="7467f-142">From the drop-down list, select the Interact host.</span></span>|  
    |<span data-ttu-id="7467f-143">**送信パイプライン**</span><span class="sxs-lookup"><span data-stu-id="7467f-143">**Send pipeline**</span></span>|<span data-ttu-id="7467f-144">ドロップダウン リストから選択**XMLTransmit**です。</span><span class="sxs-lookup"><span data-stu-id="7467f-144">From the drop-down list, select **XMLTransmit**.</span></span>|  
    |<span data-ttu-id="7467f-145">**受信パイプライン**</span><span class="sxs-lookup"><span data-stu-id="7467f-145">**Receive pipeline**</span></span>|<span data-ttu-id="7467f-146">ドロップダウン リストから選択**XMLReceive**です。</span><span class="sxs-lookup"><span data-stu-id="7467f-146">From the drop-down list, select **XMLReceive**.</span></span>|  
  
9. <span data-ttu-id="7467f-147">**送信ポートのプロパティ** ウィンドウで、**フィルター**  タブで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="7467f-147">In the **Send Port Properties** window, on the **Filters** tab, do the following:</span></span>  
  
    |<span data-ttu-id="7467f-148">**これを使用してください。**</span><span class="sxs-lookup"><span data-stu-id="7467f-148">**Use this**</span></span>|<span data-ttu-id="7467f-149">**これを行う**</span><span class="sxs-lookup"><span data-stu-id="7467f-149">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="7467f-150">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="7467f-150">**Property**</span></span>|<span data-ttu-id="7467f-151">ドロップダウン リストから選択**BTS です。ReceivePortName**です。</span><span class="sxs-lookup"><span data-stu-id="7467f-151">From the drop-down list, select **BTS.ReceivePortName**.</span></span>|  
    |<span data-ttu-id="7467f-152">**演算子**</span><span class="sxs-lookup"><span data-stu-id="7467f-152">**Operator**</span></span>|<span data-ttu-id="7467f-153">ドロップダウン リストから選択 **==**です。</span><span class="sxs-lookup"><span data-stu-id="7467f-153">From the drop-down list, select **==**.</span></span>|  
    |<span data-ttu-id="7467f-154">**値**</span><span class="sxs-lookup"><span data-stu-id="7467f-154">**Value**</span></span>|<span data-ttu-id="7467f-155">型**Tutorial_IA_InputRequest_SnF**です。</span><span class="sxs-lookup"><span data-stu-id="7467f-155">Type **Tutorial_IA_InputRequest_SnF**.</span></span>|  
    |<span data-ttu-id="7467f-156">**グループ化**</span><span class="sxs-lookup"><span data-stu-id="7467f-156">**Group by**</span></span>|<span data-ttu-id="7467f-157">既定値を使用します。</span><span class="sxs-lookup"><span data-stu-id="7467f-157">Leave the default value.</span></span>|  
  
10. <span data-ttu-id="7467f-158">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7467f-158">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7467f-159">参照</span><span class="sxs-lookup"><span data-stu-id="7467f-159">See Also</span></span>  
 <span data-ttu-id="7467f-160">[手順 2 a: ファイルの受信場所 InterAct ストア アンド フォワード (プル) シナリオの追加](../../adapters-and-accelerators/fileact-interact/step-2a-add-file-receive-locations-for-interact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="7467f-160">[Step 2A: Add FILE Receive Locations for the InterAct Store and Forward (Pull) Scenario](../../adapters-and-accelerators/fileact-interact/step-2a-add-file-receive-locations-for-interact-store-and-forward-scenario.md) </span></span>  
 [<span data-ttu-id="7467f-161">手順 2 b: InterAct ストア アンド フォワード (プル) シナリオの Sw:HandleRequest メッセージをキャプチャするファイルの送信ポートの追加</span><span class="sxs-lookup"><span data-stu-id="7467f-161">Step 2B: Add FILE Send Ports to Capture the Sw:HandleRequest Message for the InterAct Store and Forward (Pull) Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-2b-add-file-send-ports-to-get-sw-handlerequest-message-for-interact.md)