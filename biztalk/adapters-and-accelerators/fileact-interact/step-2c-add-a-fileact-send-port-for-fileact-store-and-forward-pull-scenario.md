---
title: "手順 2 C: FileAct ストア アンド フォワード (プル) シナリオの FILEACT 送信ポートの追加 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8743a868-9625-477b-a7da-673bfa262723
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 803a8c671081afd3ba18b81d4770b80b26205eaf
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="step-2c-add-a-fileact-send-port-for-the-fileact-store-and-forward-pull-scenario"></a><span data-ttu-id="617e7-102">手順 2 C: FileAct ストア アンド フォワード (プル) シナリオの FILEACT 送信ポートの追加</span><span class="sxs-lookup"><span data-stu-id="617e7-102">Step 2C: Add a FILEACT Send Port for the FileAct Store and Forward (Pull) Scenario</span></span>
<span data-ttu-id="617e7-103">この手順を開始する前に行う必要があります[Step 2B: Sw:HandleFileRequest と FileAct ストア アンド フォワード (プル) シナリオの Sw:HandleSnFRequest メッセージをキャプチャする FILE 送信ポートの追加](../../adapters-and-accelerators/fileact-interact/step-2b-add-file-send-ports--get-sw-handlefilerequest-and-sw-handlesnfrequest.md)です。</span><span class="sxs-lookup"><span data-stu-id="617e7-103">Before you begin this step, you must complete [Step 2B: Add FILE Send Ports to Capture the Sw:HandleFileRequest and Sw:HandleSnFRequest Messages for the FileAct Store and Forward (Pull) Scenario](../../adapters-and-accelerators/fileact-interact/step-2b-add-file-send-ports--get-sw-handlefilerequest-and-sw-handlesnfrequest.md).</span></span>  
  
### <a name="to-add-a-fileact-send-port"></a><span data-ttu-id="617e7-104">FileACT 送信ポートを追加するには</span><span class="sxs-lookup"><span data-stu-id="617e7-104">To add a FileACT send port</span></span>  
  
1.  <span data-ttu-id="617e7-105">開始**BizTalk Server 管理**です。</span><span class="sxs-lookup"><span data-stu-id="617e7-105">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="617e7-106">コンソール ツリーで、BizTalk グループを展開し、送信ポートを作成する BizTalk アプリケーションの順に展開します。</span><span class="sxs-lookup"><span data-stu-id="617e7-106">In the console tree, expand the BizTalk group, and then expand the BizTalk application for which you want to create a send port.</span></span>  
  
3.  <span data-ttu-id="617e7-107">右クリック**送信ポート**、 をポイント**新規**、クリックして**静的な送信請求-応答送信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="617e7-107">Right-click **Send Ports**, point to **New**, and then click **Static Solicit-Response Send Port**.</span></span>  
  
4.  <span data-ttu-id="617e7-108">**送信ポートのプロパティ**ウィンドウで、名前、送信ポートを**Tutorial_FA_SendRequest_SnF**です。</span><span class="sxs-lookup"><span data-stu-id="617e7-108">In the **Send Port Properties** window, name the send port, **Tutorial_FA_SendRequest_SnF**.</span></span>  
  
5.  <span data-ttu-id="617e7-109">**送信ポートのプロパティ** ウィンドウから、**トランスポートの種類**ドロップダウン リストで、 **FILEACT**、順にクリック**構成**です。</span><span class="sxs-lookup"><span data-stu-id="617e7-109">In the **Send Port Properties** window, from the **Transport type** drop-down list, select **FILEACT**, and then click **Configure**.</span></span>  
  
6.  <span data-ttu-id="617e7-110">**FILEACT トランスポートのプロパティ** ダイアログ ボックスで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="617e7-110">In the **FILEACT Transport Properties** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="617e7-111">**これを使用してください。**</span><span class="sxs-lookup"><span data-stu-id="617e7-111">**Use this**</span></span>|<span data-ttu-id="617e7-112">**これを行う**</span><span class="sxs-lookup"><span data-stu-id="617e7-112">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="617e7-113">**Password**</span><span class="sxs-lookup"><span data-stu-id="617e7-113">**Password**</span></span>|<span data-ttu-id="617e7-114">SAG 接続適切なパスワードを設定します。</span><span class="sxs-lookup"><span data-stu-id="617e7-114">Set the password as appropriate for SAG connectivity.</span></span>|  
    |<span data-ttu-id="617e7-115">**ユーザー名**</span><span class="sxs-lookup"><span data-stu-id="617e7-115">**User name**</span></span>|<span data-ttu-id="617e7-116">SAG 接続を適切なユーザー名を設定します。</span><span class="sxs-lookup"><span data-stu-id="617e7-116">Set the user name as appropriate for SAG connectivity.</span></span>|  
    |<span data-ttu-id="617e7-117">**アダプターのモード**</span><span class="sxs-lookup"><span data-stu-id="617e7-117">**Adapter Mode**</span></span>|<span data-ttu-id="617e7-118">ドロップダウン リストから選択**ストア アンド フォワード**です。</span><span class="sxs-lookup"><span data-stu-id="617e7-118">From the drop-down list, select **Store and Forward**.</span></span>|  
    |<span data-ttu-id="617e7-119">**否認不可インジケーター**</span><span class="sxs-lookup"><span data-stu-id="617e7-119">**Non-Repudiation Indicator**</span></span>|<span data-ttu-id="617e7-120">ドロップダウン リストから選択**FALSE**です。</span><span class="sxs-lookup"><span data-stu-id="617e7-120">From the drop-down list, select **FALSE**.</span></span>|  
    |<span data-ttu-id="617e7-121">**要求の種類**</span><span class="sxs-lookup"><span data-stu-id="617e7-121">**Request Type**</span></span>|<span data-ttu-id="617e7-122">適切な設定\<RequestType\> SWIFT でのプロビジョニングに基づく文字列。</span><span class="sxs-lookup"><span data-stu-id="617e7-122">Set to the appropriate \<RequestType\> string, based on your provisioning with SWIFT.</span></span>|  
    |<span data-ttu-id="617e7-123">**RequestCrypto**</span><span class="sxs-lookup"><span data-stu-id="617e7-123">**RequestCrypto**</span></span>|<span data-ttu-id="617e7-124">ドロップダウン リストから選択**FALSE**です。</span><span class="sxs-lookup"><span data-stu-id="617e7-124">From the drop-down list, select **FALSE**.</span></span>|  
    |<span data-ttu-id="617e7-125">**要求元**</span><span class="sxs-lookup"><span data-stu-id="617e7-125">**Requestor**</span></span>|<span data-ttu-id="617e7-126">適切な設定\<リクエスター\> SWIFT でのプロビジョニングに基づく文字列。</span><span class="sxs-lookup"><span data-stu-id="617e7-126">Set to the appropriate \<Requestor\> string, based on your provisioning with SWIFT.</span></span>|  
    |<span data-ttu-id="617e7-127">**応答側**</span><span class="sxs-lookup"><span data-stu-id="617e7-127">**Responder**</span></span>|<span data-ttu-id="617e7-128">適切な設定\<レスポンダー\>文字列。</span><span class="sxs-lookup"><span data-stu-id="617e7-128">Set to the appropriate \<Responder\> string.</span></span>|  
    |<span data-ttu-id="617e7-129">**サービス名**</span><span class="sxs-lookup"><span data-stu-id="617e7-129">**Service Name**</span></span>|<span data-ttu-id="617e7-130">適切な設定**\<サービス名\>**です。</span><span class="sxs-lookup"><span data-stu-id="617e7-130">Set to the appropriate **\<service name\>**.</span></span>|  
    |<span data-ttu-id="617e7-131">**受信確認のインジケーター**</span><span class="sxs-lookup"><span data-stu-id="617e7-131">**Acknowledgement Indicator**</span></span>|<span data-ttu-id="617e7-132">ドロップダウン リストから選択**FALSE**です。</span><span class="sxs-lookup"><span data-stu-id="617e7-132">From the drop-down list, select **FALSE**.</span></span>|  
    |<span data-ttu-id="617e7-133">**イベントのエンドポイント**</span><span class="sxs-lookup"><span data-stu-id="617e7-133">**Event end-point**</span></span>|<span data-ttu-id="617e7-134">ドロップダウン リストから選択**FALSE**です。</span><span class="sxs-lookup"><span data-stu-id="617e7-134">From the drop-down list, select **FALSE**.</span></span>|  
    |<span data-ttu-id="617e7-135">**ファイルの圧縮**</span><span class="sxs-lookup"><span data-stu-id="617e7-135">**File Compression**</span></span>|<span data-ttu-id="617e7-136">ドロップダウン リストから選択**None**です。</span><span class="sxs-lookup"><span data-stu-id="617e7-136">From the drop-down list, select **None**.</span></span>|  
    |<span data-ttu-id="617e7-137">**物理的なフォルダー名**</span><span class="sxs-lookup"><span data-stu-id="617e7-137">**Physical Folder Name**</span></span>|<span data-ttu-id="617e7-138">C:\SWIFTAdapterTutorial\Fileact\ClientLocation を入力します。</span><span class="sxs-lookup"><span data-stu-id="617e7-138">Type C:\SWIFTAdapterTutorial\Fileact\ClientLocation.</span></span>|  
    |<span data-ttu-id="617e7-139">**エンドポイントを転送します。**</span><span class="sxs-lookup"><span data-stu-id="617e7-139">**Transfer end-point**</span></span>|<span data-ttu-id="617e7-140">SAG ルーティング セットの適切なエンドポイントを入力します。</span><span class="sxs-lookup"><span data-stu-id="617e7-140">Type the appropriate end-point for the SAG routing set.</span></span> <span data-ttu-id="617e7-141">この値は、SAG で構成されている SNL エンドポイントと一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="617e7-141">This value should match the SNL endpoint you configured in SAG.</span></span>|  
    |<span data-ttu-id="617e7-142">**ServiceProfile**</span><span class="sxs-lookup"><span data-stu-id="617e7-142">**ServiceProfile**</span></span>|<span data-ttu-id="617e7-143">ドロップダウン リストから選択**トランザクション カウント**です。</span><span class="sxs-lookup"><span data-stu-id="617e7-143">From the drop-down list, select **Transaction Count**.</span></span>|  
    |<span data-ttu-id="617e7-144">**配信通知**</span><span class="sxs-lookup"><span data-stu-id="617e7-144">**Delivery notification**</span></span>|<span data-ttu-id="617e7-145">ドロップダウン リストから選択**FALSE**です。</span><span class="sxs-lookup"><span data-stu-id="617e7-145">From the drop-down list, select **FALSE**.</span></span>|  
    |<span data-ttu-id="617e7-146">**通知キュー**</span><span class="sxs-lookup"><span data-stu-id="617e7-146">**Notify queue**</span></span>|<span data-ttu-id="617e7-147">SWIFT でのプロビジョニングに基づく、キュー名を入力します。</span><span class="sxs-lookup"><span data-stu-id="617e7-147">Type the queue name, based on your provisioning with SWIFT.</span></span>|  
  
    > [!NOTE]
    >  <span data-ttu-id="617e7-148">メッセージでのトランザクション数を転送する場合は、サービスのプロファイルでモードを設定「トランザクション数」に、FileAct 送信ポート。</span><span class="sxs-lookup"><span data-stu-id="617e7-148">If message with Transaction Count is to be transferred, set the Service Profile Mode to “Transaction Count” in the FileAct send port.</span></span>  
  
7.  <span data-ttu-id="617e7-149">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="617e7-149">Click **OK**.</span></span>  
  
8.  <span data-ttu-id="617e7-150">**送信ポートのプロパティ** ウィンドウで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="617e7-150">In the **Send Port Properties** window, do the following:</span></span>  
  
    |<span data-ttu-id="617e7-151">**これを使用してください。**</span><span class="sxs-lookup"><span data-stu-id="617e7-151">**Use this**</span></span>|<span data-ttu-id="617e7-152">**これを行う**</span><span class="sxs-lookup"><span data-stu-id="617e7-152">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="617e7-153">**送信ハンドラー**</span><span class="sxs-lookup"><span data-stu-id="617e7-153">**Send handler**</span></span>|<span data-ttu-id="617e7-154">ドロップダウン リストから選択、 **FileActHost**です。</span><span class="sxs-lookup"><span data-stu-id="617e7-154">From the drop-down list, select the **FileActHost**.</span></span>|  
    |<span data-ttu-id="617e7-155">**送信パイプライン**</span><span class="sxs-lookup"><span data-stu-id="617e7-155">**Send pipeline**</span></span>|<span data-ttu-id="617e7-156">ドロップダウン リストから選択**XMLTransmit**です。</span><span class="sxs-lookup"><span data-stu-id="617e7-156">From the drop-down list, select **XMLTransmit**.</span></span>|  
    |<span data-ttu-id="617e7-157">**受信パイプライン**</span><span class="sxs-lookup"><span data-stu-id="617e7-157">**Receive pipeline**</span></span>|<span data-ttu-id="617e7-158">ドロップダウン リストから選択**XMLReceive**です。</span><span class="sxs-lookup"><span data-stu-id="617e7-158">From the drop-down list, select **XMLReceive**.</span></span>|  
  
9. <span data-ttu-id="617e7-159">**送信ポートのプロパティ** ウィンドウで、**フィルター**  タブで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="617e7-159">In the **Send Port Properties** window, on the **Filters** tab, do the following:</span></span>  
  
    |<span data-ttu-id="617e7-160">**これを使用してください。**</span><span class="sxs-lookup"><span data-stu-id="617e7-160">**Use this**</span></span>|<span data-ttu-id="617e7-161">**これを行う**</span><span class="sxs-lookup"><span data-stu-id="617e7-161">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="617e7-162">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="617e7-162">**Property**</span></span>|<span data-ttu-id="617e7-163">ドロップダウン リストから選択**BTS です。ReceivePortName**です。</span><span class="sxs-lookup"><span data-stu-id="617e7-163">From the drop-down list, select **BTS.ReceivePortName**.</span></span>|  
    |<span data-ttu-id="617e7-164">**演算子**</span><span class="sxs-lookup"><span data-stu-id="617e7-164">**Operator**</span></span>|<span data-ttu-id="617e7-165">ドロップダウン リストから選択 **==**です。</span><span class="sxs-lookup"><span data-stu-id="617e7-165">From the drop-down list, select **==**.</span></span>|  
    |<span data-ttu-id="617e7-166">**値**</span><span class="sxs-lookup"><span data-stu-id="617e7-166">**Value**</span></span>|<span data-ttu-id="617e7-167">型**Tutorial_IA_InputRequest_SnF**です。</span><span class="sxs-lookup"><span data-stu-id="617e7-167">Type **Tutorial_IA_InputRequest_SnF**.</span></span>|  
    |<span data-ttu-id="617e7-168">**グループ化**</span><span class="sxs-lookup"><span data-stu-id="617e7-168">**Group by**</span></span>|<span data-ttu-id="617e7-169">既定値を使用します。</span><span class="sxs-lookup"><span data-stu-id="617e7-169">Leave the default value.</span></span>|  
  
10. <span data-ttu-id="617e7-170">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="617e7-170">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="617e7-171">参照</span><span class="sxs-lookup"><span data-stu-id="617e7-171">See Also</span></span>  
 <span data-ttu-id="617e7-172">[手順 2 a: ファイルの受信場所 FileAct ストア アンド フォワード (プル) シナリオの追加](../../adapters-and-accelerators/fileact-interact/step-2a-add-file-receive-locations-for-fileact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="617e7-172">[Step 2A: Add FILE Receive Locations for the FileAct Store and Forward (Pull) Scenario](../../adapters-and-accelerators/fileact-interact/step-2a-add-file-receive-locations-for-fileact-store-and-forward-scenario.md) </span></span>  
 [<span data-ttu-id="617e7-173">手順 2B: FileAct ストア アンド フォワード (プル) シナリオ用に Sw:HandleFileRequest および Sw:HandleSnFRequest メッセージをキャプチャするためにファイルの送信ポートを追加する</span><span class="sxs-lookup"><span data-stu-id="617e7-173">Step 2B: Add FILE Send Ports to Capture the Sw:HandleFileRequest and Sw:HandleSnFRequest Messages for the FileAct Store and Forward (Pull) Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-2b-add-file-send-ports--get-sw-handlefilerequest-and-sw-handlesnfrequest.md)