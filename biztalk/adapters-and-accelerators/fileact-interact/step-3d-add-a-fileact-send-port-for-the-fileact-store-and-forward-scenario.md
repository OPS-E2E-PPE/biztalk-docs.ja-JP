---
title: "ステップ 3 D: FileAct ストア アンド フォワードのシナリオの FILEACT 送信ポートの追加 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7366140b-ab89-4bea-9cdb-aa27e8dea8a0
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a3944c58aecda3d9ea984e0ef0ce9a2bf168ea80
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="step-3d-add-a-fileact-send-port-for-the-fileact-store-and-forward-scenario"></a><span data-ttu-id="5f060-102">ステップ 3 D: FileAct ストア アンド フォワードのシナリオの FILEACT 送信ポートの追加</span><span class="sxs-lookup"><span data-stu-id="5f060-102">Step 3D: Add a FILEACT Send Port for the FileAct Store and Forward Scenario</span></span>
<span data-ttu-id="5f060-103">この手順を開始する前に行う必要があります[手順 3 C: Sw:HandleFileRequest をキャプチャする FILE 送信ポートおよび Sw:HandleSnFRequest メッセージ FileAct ストア アンド フォワードのシナリオを追加](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlefilerequest-and-sw-handlesnfrequest.md)です。</span><span class="sxs-lookup"><span data-stu-id="5f060-103">Before you begin this step, you must complete [Step 3C: Add a FILE Send Port to Capture the Sw:HandleFileRequest and Sw:HandleSnFRequest Messages for the FileAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlefilerequest-and-sw-handlesnfrequest.md).</span></span>  
  
### <a name="to-add-a-fileact-send-port"></a><span data-ttu-id="5f060-104">FILEACT 送信ポートを追加するには</span><span class="sxs-lookup"><span data-stu-id="5f060-104">To add a FILEACT send port</span></span>  
  
1.  <span data-ttu-id="5f060-105">開始**BizTalk Server 管理**です。</span><span class="sxs-lookup"><span data-stu-id="5f060-105">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="5f060-106">コンソール ツリーで、BizTalk グループを展開し、送信ポートを作成する BizTalk アプリケーションの順に展開します。</span><span class="sxs-lookup"><span data-stu-id="5f060-106">In the console tree, expand the BizTalk group, and then expand the BizTalk application for which you want to create a send port.</span></span>  
  
3.  <span data-ttu-id="5f060-107">右クリック**送信ポート**、 をポイント**新規**、クリックして**静的な送信請求-応答送信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="5f060-107">Right-click **Send Ports**, point to **New**, and then click **Static Solicit-Response Send Port**.</span></span>  
  
4.  <span data-ttu-id="5f060-108">**送信ポートのプロパティ**ウィンドウで、名前、送信ポートを Tutorial_FA_SendRequest_SnF です。</span><span class="sxs-lookup"><span data-stu-id="5f060-108">In the **Send Port Properties** window, name the send port, Tutorial_FA_SendRequest_SnF.</span></span>  
  
5.  <span data-ttu-id="5f060-109">**送信ポートのプロパティ** ウィンドウから、**トランスポートの種類**ドロップダウン リストで、 **FILEACT**、順にクリック**構成**です。</span><span class="sxs-lookup"><span data-stu-id="5f060-109">In the **Send Port Properties** window, from the **Transport type** drop-down list, select **FILEACT**, and then click **Configure**.</span></span>  
  
6.  <span data-ttu-id="5f060-110">**FILEACT トランスポートのプロパティ** ダイアログ ボックスで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="5f060-110">In the **FILEACT Transport Properties** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="5f060-111">**これを使用してください。**</span><span class="sxs-lookup"><span data-stu-id="5f060-111">**Use this**</span></span>|<span data-ttu-id="5f060-112">**これを行う**</span><span class="sxs-lookup"><span data-stu-id="5f060-112">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="5f060-113">**Password**</span><span class="sxs-lookup"><span data-stu-id="5f060-113">**Password**</span></span>|<span data-ttu-id="5f060-114">SAG 接続適切なパスワードを設定します。</span><span class="sxs-lookup"><span data-stu-id="5f060-114">Set the password as appropriate for SAG connectivity.</span></span>|  
    |<span data-ttu-id="5f060-115">**ユーザー名**</span><span class="sxs-lookup"><span data-stu-id="5f060-115">**User name**</span></span>|<span data-ttu-id="5f060-116">SAG 接続を適切なユーザー名を設定します。</span><span class="sxs-lookup"><span data-stu-id="5f060-116">Set the user name as appropriate for SAG connectivity.</span></span>|  
    |<span data-ttu-id="5f060-117">**アダプターのモード**</span><span class="sxs-lookup"><span data-stu-id="5f060-117">**Adapter Mode**</span></span>|<span data-ttu-id="5f060-118">ドロップダウン リストから選択**ストア アンド フォワード**です。</span><span class="sxs-lookup"><span data-stu-id="5f060-118">From the drop-down list, select **Store and Forward**.</span></span>|  
    |<span data-ttu-id="5f060-119">**否認不可インジケーター**</span><span class="sxs-lookup"><span data-stu-id="5f060-119">**Non-Repudiation Indicator**</span></span>|<span data-ttu-id="5f060-120">ドロップダウン リストから選択**FALSE**です。</span><span class="sxs-lookup"><span data-stu-id="5f060-120">From the drop-down list, select **FALSE**.</span></span>|  
    |<span data-ttu-id="5f060-121">**要求の種類**</span><span class="sxs-lookup"><span data-stu-id="5f060-121">**Request Type**</span></span>|<span data-ttu-id="5f060-122">適切な設定\<RequestType\> SWIFT でのプロビジョニングに基づく文字列。</span><span class="sxs-lookup"><span data-stu-id="5f060-122">Set to the appropriate \<RequestType\> string, based on your provisioning with SWIFT.</span></span>|  
    |<span data-ttu-id="5f060-123">**ResponseCrypto**</span><span class="sxs-lookup"><span data-stu-id="5f060-123">**ResponseCrypto**</span></span>|<span data-ttu-id="5f060-124">ドロップダウン リストから選択**FALSE**です。</span><span class="sxs-lookup"><span data-stu-id="5f060-124">From the drop-down list, select **FALSE**.</span></span>|  
    |<span data-ttu-id="5f060-125">**要求元**</span><span class="sxs-lookup"><span data-stu-id="5f060-125">**Requestor**</span></span>|<span data-ttu-id="5f060-126">適切な設定\<リクエスター\> SWIFT でのプロビジョニングに基づく文字列。</span><span class="sxs-lookup"><span data-stu-id="5f060-126">Set to the appropriate \<Requestor\> string, based on your provisioning with SWIFT.</span></span>|  
    |<span data-ttu-id="5f060-127">**応答側**</span><span class="sxs-lookup"><span data-stu-id="5f060-127">**Responder**</span></span>|<span data-ttu-id="5f060-128">適切な設定\<レスポンダー\>文字列。</span><span class="sxs-lookup"><span data-stu-id="5f060-128">Set to the appropriate \<Responder\> string.</span></span>|  
    |<span data-ttu-id="5f060-129">**サービス名**</span><span class="sxs-lookup"><span data-stu-id="5f060-129">**Service Name**</span></span>|<span data-ttu-id="5f060-130">適切な設定\<サービス名\>です。</span><span class="sxs-lookup"><span data-stu-id="5f060-130">Set to the appropriate \<service name\>.</span></span>|  
    |<span data-ttu-id="5f060-131">**受信確認のインジケーター**</span><span class="sxs-lookup"><span data-stu-id="5f060-131">**Acknowledgement Indicator**</span></span>|<span data-ttu-id="5f060-132">ドロップダウン リストから選択**FALSE**です。</span><span class="sxs-lookup"><span data-stu-id="5f060-132">From the drop-down list, select **FALSE**.</span></span>|  
    |<span data-ttu-id="5f060-133">**FileCompression**</span><span class="sxs-lookup"><span data-stu-id="5f060-133">**FileCompression**</span></span>|<span data-ttu-id="5f060-134">ドロップダウン リストから選択**None**です。</span><span class="sxs-lookup"><span data-stu-id="5f060-134">From the drop-down list, select **None**.</span></span>|  
    |<span data-ttu-id="5f060-135">**イベントのエンドポイント**</span><span class="sxs-lookup"><span data-stu-id="5f060-135">**Event end-point**</span></span>|<span data-ttu-id="5f060-136">適切な SAG エンドポイントを入力します。</span><span class="sxs-lookup"><span data-stu-id="5f060-136">Type the appropriate SAG end-point.</span></span>|  
    |<span data-ttu-id="5f060-137">**物理的なフォルダー名**</span><span class="sxs-lookup"><span data-stu-id="5f060-137">**Physical Folder Name**</span></span>|<span data-ttu-id="5f060-138">C:\SWIFTAdapterTutorial\Fileact\ClientLocation を入力します。</span><span class="sxs-lookup"><span data-stu-id="5f060-138">Type C:\SWIFTAdapterTutorial\Fileact\ClientLocation.</span></span>|  
    |<span data-ttu-id="5f060-139">**エンドポイントを転送します。**</span><span class="sxs-lookup"><span data-stu-id="5f060-139">**Transfer end-point**</span></span>|<span data-ttu-id="5f060-140">SAG ルーティング セットの適切なエンドポイントを入力します。</span><span class="sxs-lookup"><span data-stu-id="5f060-140">Type the appropriate end-point for the SAG routing set.</span></span> <span data-ttu-id="5f060-141">この値は、SAG で構成されている SnL エンドポイントと一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5f060-141">This value should match the SnL endpoint you configured in SAG.</span></span>|  
    |<span data-ttu-id="5f060-142">**ServiceProfile**</span><span class="sxs-lookup"><span data-stu-id="5f060-142">**ServiceProfile**</span></span>|<span data-ttu-id="5f060-143">ドロップダウン リストから選択**トランザクション カウント**です。</span><span class="sxs-lookup"><span data-stu-id="5f060-143">From the drop-down list, select **Transaction Count**.</span></span>|  
    |<span data-ttu-id="5f060-144">**配信通知**</span><span class="sxs-lookup"><span data-stu-id="5f060-144">**Delivery notification**</span></span>|<span data-ttu-id="5f060-145">ドロップダウン リストから選択**FALSE**です。</span><span class="sxs-lookup"><span data-stu-id="5f060-145">From the drop-down list, select **FALSE**.</span></span>|  
    |<span data-ttu-id="5f060-146">**通知キュー**</span><span class="sxs-lookup"><span data-stu-id="5f060-146">**Notify queue**</span></span>|<span data-ttu-id="5f060-147">SWIFT でのプロビジョニングに基づく、キュー名を入力します。</span><span class="sxs-lookup"><span data-stu-id="5f060-147">Type the queue name, based on your provisioning with SWIFT.</span></span>|  
  
    > [!WARNING]
    >  <span data-ttu-id="5f060-148">メッセージでのトランザクション数を転送する場合は、サービスのプロファイルでモードを設定「トランザクション数」に、FileAct 送信ポート。</span><span class="sxs-lookup"><span data-stu-id="5f060-148">If message with Transaction Count is to be transferred, set the Service Profile Mode to “Transaction Count” in the FileAct send port.</span></span>  
  
7.  <span data-ttu-id="5f060-149">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5f060-149">Click **OK**.</span></span>  
  
8.  <span data-ttu-id="5f060-150">**送信ポートのプロパティ** ウィンドウで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="5f060-150">In the **Send Port Properties** window, do the following:</span></span>  
  
    |<span data-ttu-id="5f060-151">**これを使用してください。**</span><span class="sxs-lookup"><span data-stu-id="5f060-151">**Use this**</span></span>|<span data-ttu-id="5f060-152">**これを行う**</span><span class="sxs-lookup"><span data-stu-id="5f060-152">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="5f060-153">**送信ハンドラー**</span><span class="sxs-lookup"><span data-stu-id="5f060-153">**Send handler**</span></span>|<span data-ttu-id="5f060-154">ドロップダウン リストから、Fileact ホストを選択します。</span><span class="sxs-lookup"><span data-stu-id="5f060-154">From the drop-down list, select the Fileact host.</span></span>|  
    |<span data-ttu-id="5f060-155">**送信パイプライン**</span><span class="sxs-lookup"><span data-stu-id="5f060-155">**Send pipeline**</span></span>|<span data-ttu-id="5f060-156">ドロップダウン リストから選択**XMLTransmit**です。</span><span class="sxs-lookup"><span data-stu-id="5f060-156">From the drop-down list, select **XMLTransmit**.</span></span>|  
    |<span data-ttu-id="5f060-157">**受信パイプライン**</span><span class="sxs-lookup"><span data-stu-id="5f060-157">**Receive pipeline**</span></span>|<span data-ttu-id="5f060-158">ドロップダウン リストから選択**XMLReceive**です。</span><span class="sxs-lookup"><span data-stu-id="5f060-158">From the drop-down list, select **XMLReceive**.</span></span>|  
  
9. <span data-ttu-id="5f060-159">**送信ポートのプロパティ** ウィンドウで、**フィルター**  タブで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="5f060-159">In the **Send Port Properties** window, on the **Filters** tab, do the following:</span></span>  
  
    |<span data-ttu-id="5f060-160">**これを使用してください。**</span><span class="sxs-lookup"><span data-stu-id="5f060-160">**Use this**</span></span>|<span data-ttu-id="5f060-161">**これを行う**</span><span class="sxs-lookup"><span data-stu-id="5f060-161">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="5f060-162">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="5f060-162">**Property**</span></span>|<span data-ttu-id="5f060-163">ドロップダウン リストから選択**BTS です。ReceivePortName**です。</span><span class="sxs-lookup"><span data-stu-id="5f060-163">From the drop-down list, select **BTS.ReceivePortName**.</span></span>|  
    |<span data-ttu-id="5f060-164">**演算子**</span><span class="sxs-lookup"><span data-stu-id="5f060-164">**Operator**</span></span>|<span data-ttu-id="5f060-165">ドロップダウン リストから選択 **==**です。</span><span class="sxs-lookup"><span data-stu-id="5f060-165">From the drop-down list, select **==**.</span></span>|  
    |<span data-ttu-id="5f060-166">**値**</span><span class="sxs-lookup"><span data-stu-id="5f060-166">**Value**</span></span>|<span data-ttu-id="5f060-167">型 Tutorial_FA_InputRequest_SnF です。</span><span class="sxs-lookup"><span data-stu-id="5f060-167">Type Tutorial_FA_InputRequest_SnF.</span></span>|  
    |<span data-ttu-id="5f060-168">**グループ化**</span><span class="sxs-lookup"><span data-stu-id="5f060-168">**Group by**</span></span>|<span data-ttu-id="5f060-169">既定値を使用します。</span><span class="sxs-lookup"><span data-stu-id="5f060-169">Leave the default value.</span></span>|  
  
10. <span data-ttu-id="5f060-170">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5f060-170">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f060-171">参照</span><span class="sxs-lookup"><span data-stu-id="5f060-171">See Also</span></span>  
 <span data-ttu-id="5f060-172">[手順 3: 送信ポートを作成し、FileAct ストア アンド フォワードのシナリオの受信ポート](../../adapters-and-accelerators/fileact-interact/step-3-create-send-ports-and-receive-ports-for-the-fileact-store-and-forward.md) </span><span class="sxs-lookup"><span data-stu-id="5f060-172">[Step 3: Create Send Ports and Receive Ports for the FileAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-3-create-send-ports-and-receive-ports-for-the-fileact-store-and-forward.md) </span></span>  
 <span data-ttu-id="5f060-173">[手順 3: ファイルの受信場所が FileAct ストア アンド フォワードのシナリオを追加](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-the-fileact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="5f060-173">[Step 3A: Add a FILE Receive Location for the FileAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-the-fileact-store-and-forward-scenario.md) </span></span>  
 <span data-ttu-id="5f060-174">[手順 3 b: FILEACT の受信場所が FileAct ストア アンド フォワードのシナリオを追加](../../adapters-and-accelerators/fileact-interact/step-3b-add-a-fileact-receive-location-for-fileact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="5f060-174">[Step 3B: Add a FILEACT Receive Location for the FileAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-3b-add-a-fileact-receive-location-for-fileact-store-and-forward-scenario.md) </span></span>  
 [<span data-ttu-id="5f060-175">手順 3C: FileAct ストア アンド フォワード シナリオ用に Sw:HandleFileRequest および Sw:HandleSnFRequest メッセージをキャプチャするためにファイルの送信ポートを追加する</span><span class="sxs-lookup"><span data-stu-id="5f060-175">Step 3C: Add a FILE Send Port to Capture the Sw:HandleFileRequest and Sw:HandleSnFRequest Messages for the FileAct Store and Forward Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlefilerequest-and-sw-handlesnfrequest.md)