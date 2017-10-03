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
ms.openlocfilehash: 55db4fcd1a6a65ac9058a69f9c315de593181a65
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-2c-add-a-fileact-send-port-for-the-fileact-store-and-forward-pull-scenario"></a><span data-ttu-id="f06a5-102">手順 2 C: FileAct ストア アンド フォワード (プル) シナリオの FILEACT 送信ポートの追加</span><span class="sxs-lookup"><span data-stu-id="f06a5-102">Step 2C: Add a FILEACT Send Port for the FileAct Store and Forward (Pull) Scenario</span></span>
<span data-ttu-id="f06a5-103">この手順を開始する前に行う必要があります[Step 2B: Sw:HandleFileRequest と FileAct ストア アンド フォワード (プル) シナリオの Sw:HandleSnFRequest メッセージをキャプチャする FILE 送信ポートの追加](../../adapters-and-accelerators/fileact-interact/step-2b-add-file-send-ports--get-sw-handlefilerequest-and-sw-handlesnfrequest.md)です。</span><span class="sxs-lookup"><span data-stu-id="f06a5-103">Before you begin this step, you must complete [Step 2B: Add FILE Send Ports to Capture the Sw:HandleFileRequest and Sw:HandleSnFRequest Messages for the FileAct Store and Forward (Pull) Scenario](../../adapters-and-accelerators/fileact-interact/step-2b-add-file-send-ports--get-sw-handlefilerequest-and-sw-handlesnfrequest.md).</span></span>  
  
### <a name="to-add-a-fileact-send-port"></a><span data-ttu-id="f06a5-104">FileACT 送信ポートを追加するには</span><span class="sxs-lookup"><span data-stu-id="f06a5-104">To add a FileACT send port</span></span>  
  
1.  <span data-ttu-id="f06a5-105">開始**BizTalk Server 管理**です。</span><span class="sxs-lookup"><span data-stu-id="f06a5-105">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="f06a5-106">コンソール ツリーで、BizTalk グループを展開し、送信ポートを作成する BizTalk アプリケーションの順に展開します。</span><span class="sxs-lookup"><span data-stu-id="f06a5-106">In the console tree, expand the BizTalk group, and then expand the BizTalk application for which you want to create a send port.</span></span>  
  
3.  <span data-ttu-id="f06a5-107">右クリック**送信ポート**、 をポイント**新規**、クリックして**静的な送信請求-応答送信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="f06a5-107">Right-click **Send Ports**, point to **New**, and then click **Static Solicit-Response Send Port**.</span></span>  
  
4.  <span data-ttu-id="f06a5-108">**送信ポートのプロパティ**ウィンドウで、名前、送信ポートを**Tutorial_FA_SendRequest_SnF**です。</span><span class="sxs-lookup"><span data-stu-id="f06a5-108">In the **Send Port Properties** window, name the send port, **Tutorial_FA_SendRequest_SnF**.</span></span>  
  
5.  <span data-ttu-id="f06a5-109">**送信ポートのプロパティ** ウィンドウから、**トランスポートの種類**ドロップダウン リストで、 **FILEACT**、順にクリック**構成**です。</span><span class="sxs-lookup"><span data-stu-id="f06a5-109">In the **Send Port Properties** window, from the **Transport type** drop-down list, select **FILEACT**, and then click **Configure**.</span></span>  
  
6.  <span data-ttu-id="f06a5-110">**FILEACT トランスポートのプロパティ** ダイアログ ボックスで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="f06a5-110">In the **FILEACT Transport Properties** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="f06a5-111">**これを使用してください。**</span><span class="sxs-lookup"><span data-stu-id="f06a5-111">**Use this**</span></span>|<span data-ttu-id="f06a5-112">**これを行う**</span><span class="sxs-lookup"><span data-stu-id="f06a5-112">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="f06a5-113">**Password**</span><span class="sxs-lookup"><span data-stu-id="f06a5-113">**Password**</span></span>|<span data-ttu-id="f06a5-114">SAG 接続適切なパスワードを設定します。</span><span class="sxs-lookup"><span data-stu-id="f06a5-114">Set the password as appropriate for SAG connectivity.</span></span>|  
    |<span data-ttu-id="f06a5-115">**ユーザー名**</span><span class="sxs-lookup"><span data-stu-id="f06a5-115">**User name**</span></span>|<span data-ttu-id="f06a5-116">SAG 接続を適切なユーザー名を設定します。</span><span class="sxs-lookup"><span data-stu-id="f06a5-116">Set the user name as appropriate for SAG connectivity.</span></span>|  
    |<span data-ttu-id="f06a5-117">**アダプターのモード**</span><span class="sxs-lookup"><span data-stu-id="f06a5-117">**Adapter Mode**</span></span>|<span data-ttu-id="f06a5-118">ドロップダウン リストから選択**ストア アンド フォワード**です。</span><span class="sxs-lookup"><span data-stu-id="f06a5-118">From the drop-down list, select **Store and Forward**.</span></span>|  
    |<span data-ttu-id="f06a5-119">**否認不可インジケーター**</span><span class="sxs-lookup"><span data-stu-id="f06a5-119">**Non-Repudiation Indicator**</span></span>|<span data-ttu-id="f06a5-120">ドロップダウン リストから選択**FALSE**です。</span><span class="sxs-lookup"><span data-stu-id="f06a5-120">From the drop-down list, select **FALSE**.</span></span>|  
    |<span data-ttu-id="f06a5-121">**要求の種類**</span><span class="sxs-lookup"><span data-stu-id="f06a5-121">**Request Type**</span></span>|<span data-ttu-id="f06a5-122">適切な設定\<RequestType > SWIFT でのプロビジョニングに基づく文字列。</span><span class="sxs-lookup"><span data-stu-id="f06a5-122">Set to the appropriate \<RequestType> string, based on your provisioning with SWIFT.</span></span>|  
    |<span data-ttu-id="f06a5-123">**RequestCrypto**</span><span class="sxs-lookup"><span data-stu-id="f06a5-123">**RequestCrypto**</span></span>|<span data-ttu-id="f06a5-124">ドロップダウン リストから選択**FALSE**です。</span><span class="sxs-lookup"><span data-stu-id="f06a5-124">From the drop-down list, select **FALSE**.</span></span>|  
    |<span data-ttu-id="f06a5-125">**要求元**</span><span class="sxs-lookup"><span data-stu-id="f06a5-125">**Requestor**</span></span>|<span data-ttu-id="f06a5-126">適切な設定\<リクエスター > SWIFT でのプロビジョニングに基づく文字列。</span><span class="sxs-lookup"><span data-stu-id="f06a5-126">Set to the appropriate \<Requestor> string, based on your provisioning with SWIFT.</span></span>|  
    |<span data-ttu-id="f06a5-127">**応答側**</span><span class="sxs-lookup"><span data-stu-id="f06a5-127">**Responder**</span></span>|<span data-ttu-id="f06a5-128">適切な設定\<レスポンダー > 文字列。</span><span class="sxs-lookup"><span data-stu-id="f06a5-128">Set to the appropriate \<Responder> string.</span></span>|  
    |<span data-ttu-id="f06a5-129">**サービス名**</span><span class="sxs-lookup"><span data-stu-id="f06a5-129">**Service Name**</span></span>|<span data-ttu-id="f06a5-130">適切な設定**\<サービス名 >**です。</span><span class="sxs-lookup"><span data-stu-id="f06a5-130">Set to the appropriate **\<service name>**.</span></span>|  
    |<span data-ttu-id="f06a5-131">**受信確認のインジケーター**</span><span class="sxs-lookup"><span data-stu-id="f06a5-131">**Acknowledgement Indicator**</span></span>|<span data-ttu-id="f06a5-132">ドロップダウン リストから選択**FALSE**です。</span><span class="sxs-lookup"><span data-stu-id="f06a5-132">From the drop-down list, select **FALSE**.</span></span>|  
    |<span data-ttu-id="f06a5-133">**イベントのエンドポイント**</span><span class="sxs-lookup"><span data-stu-id="f06a5-133">**Event end-point**</span></span>|<span data-ttu-id="f06a5-134">ドロップダウン リストから選択**FALSE**です。</span><span class="sxs-lookup"><span data-stu-id="f06a5-134">From the drop-down list, select **FALSE**.</span></span>|  
    |<span data-ttu-id="f06a5-135">**ファイルの圧縮**</span><span class="sxs-lookup"><span data-stu-id="f06a5-135">**File Compression**</span></span>|<span data-ttu-id="f06a5-136">ドロップダウン リストから選択**None**です。</span><span class="sxs-lookup"><span data-stu-id="f06a5-136">From the drop-down list, select **None**.</span></span>|  
    |<span data-ttu-id="f06a5-137">**物理的なフォルダー名**</span><span class="sxs-lookup"><span data-stu-id="f06a5-137">**Physical Folder Name**</span></span>|<span data-ttu-id="f06a5-138">C:\SWIFTAdapterTutorial\Fileact\ClientLocation を入力します。</span><span class="sxs-lookup"><span data-stu-id="f06a5-138">Type C:\SWIFTAdapterTutorial\Fileact\ClientLocation.</span></span>|  
    |<span data-ttu-id="f06a5-139">**エンドポイントを転送します。**</span><span class="sxs-lookup"><span data-stu-id="f06a5-139">**Transfer end-point**</span></span>|<span data-ttu-id="f06a5-140">SAG ルーティング セットの適切なエンドポイントを入力します。</span><span class="sxs-lookup"><span data-stu-id="f06a5-140">Type the appropriate end-point for the SAG routing set.</span></span> <span data-ttu-id="f06a5-141">この値は、SAG で構成されている SNL エンドポイントと一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f06a5-141">This value should match the SNL endpoint you configured in SAG.</span></span>|  
    |<span data-ttu-id="f06a5-142">**ServiceProfile**</span><span class="sxs-lookup"><span data-stu-id="f06a5-142">**ServiceProfile**</span></span>|<span data-ttu-id="f06a5-143">ドロップダウン リストから選択**トランザクション カウント**です。</span><span class="sxs-lookup"><span data-stu-id="f06a5-143">From the drop-down list, select **Transaction Count**.</span></span>|  
    |<span data-ttu-id="f06a5-144">**配信通知**</span><span class="sxs-lookup"><span data-stu-id="f06a5-144">**Delivery notification**</span></span>|<span data-ttu-id="f06a5-145">ドロップダウン リストから選択**FALSE**です。</span><span class="sxs-lookup"><span data-stu-id="f06a5-145">From the drop-down list, select **FALSE**.</span></span>|  
    |<span data-ttu-id="f06a5-146">**通知キュー**</span><span class="sxs-lookup"><span data-stu-id="f06a5-146">**Notify queue**</span></span>|<span data-ttu-id="f06a5-147">SWIFT でのプロビジョニングに基づく、キュー名を入力します。</span><span class="sxs-lookup"><span data-stu-id="f06a5-147">Type the queue name, based on your provisioning with SWIFT.</span></span>|  
  
    > [!NOTE]
    >  <span data-ttu-id="f06a5-148">メッセージでのトランザクション数を転送する場合は、サービスのプロファイルでモードを設定「トランザクション数」に、FileAct 送信ポート。</span><span class="sxs-lookup"><span data-stu-id="f06a5-148">If message with Transaction Count is to be transferred, set the Service Profile Mode to “Transaction Count” in the FileAct send port.</span></span>  
  
7.  <span data-ttu-id="f06a5-149">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f06a5-149">Click **OK**.</span></span>  
  
8.  <span data-ttu-id="f06a5-150">**送信ポートのプロパティ** ウィンドウで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="f06a5-150">In the **Send Port Properties** window, do the following:</span></span>  
  
    |<span data-ttu-id="f06a5-151">**これを使用してください。**</span><span class="sxs-lookup"><span data-stu-id="f06a5-151">**Use this**</span></span>|<span data-ttu-id="f06a5-152">**これを行う**</span><span class="sxs-lookup"><span data-stu-id="f06a5-152">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="f06a5-153">**送信ハンドラー**</span><span class="sxs-lookup"><span data-stu-id="f06a5-153">**Send handler**</span></span>|<span data-ttu-id="f06a5-154">ドロップダウン リストから選択、 **FileActHost**です。</span><span class="sxs-lookup"><span data-stu-id="f06a5-154">From the drop-down list, select the **FileActHost**.</span></span>|  
    |<span data-ttu-id="f06a5-155">**送信パイプライン**</span><span class="sxs-lookup"><span data-stu-id="f06a5-155">**Send pipeline**</span></span>|<span data-ttu-id="f06a5-156">ドロップダウン リストから選択**XMLTransmit**です。</span><span class="sxs-lookup"><span data-stu-id="f06a5-156">From the drop-down list, select **XMLTransmit**.</span></span>|  
    |<span data-ttu-id="f06a5-157">**受信パイプライン**</span><span class="sxs-lookup"><span data-stu-id="f06a5-157">**Receive pipeline**</span></span>|<span data-ttu-id="f06a5-158">ドロップダウン リストから選択**XMLReceive**です。</span><span class="sxs-lookup"><span data-stu-id="f06a5-158">From the drop-down list, select **XMLReceive**.</span></span>|  
  
9. <span data-ttu-id="f06a5-159">**送信ポートのプロパティ** ウィンドウで、**フィルター**  タブで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="f06a5-159">In the **Send Port Properties** window, on the **Filters** tab, do the following:</span></span>  
  
    |<span data-ttu-id="f06a5-160">**これを使用してください。**</span><span class="sxs-lookup"><span data-stu-id="f06a5-160">**Use this**</span></span>|<span data-ttu-id="f06a5-161">**これを行う**</span><span class="sxs-lookup"><span data-stu-id="f06a5-161">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="f06a5-162">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="f06a5-162">**Property**</span></span>|<span data-ttu-id="f06a5-163">ドロップダウン リストから選択**BTS です。ReceivePortName**です。</span><span class="sxs-lookup"><span data-stu-id="f06a5-163">From the drop-down list, select **BTS.ReceivePortName**.</span></span>|  
    |<span data-ttu-id="f06a5-164">**演算子**</span><span class="sxs-lookup"><span data-stu-id="f06a5-164">**Operator**</span></span>|<span data-ttu-id="f06a5-165">ドロップダウン リストから選択 **==**です。</span><span class="sxs-lookup"><span data-stu-id="f06a5-165">From the drop-down list, select **==**.</span></span>|  
    |<span data-ttu-id="f06a5-166">**値**</span><span class="sxs-lookup"><span data-stu-id="f06a5-166">**Value**</span></span>|<span data-ttu-id="f06a5-167">型**Tutorial_IA_InputRequest_SnF**です。</span><span class="sxs-lookup"><span data-stu-id="f06a5-167">Type **Tutorial_IA_InputRequest_SnF**.</span></span>|  
    |<span data-ttu-id="f06a5-168">**グループ化**</span><span class="sxs-lookup"><span data-stu-id="f06a5-168">**Group by**</span></span>|<span data-ttu-id="f06a5-169">既定値を使用します。</span><span class="sxs-lookup"><span data-stu-id="f06a5-169">Leave the default value.</span></span>|  
  
10. <span data-ttu-id="f06a5-170">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f06a5-170">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f06a5-171">参照</span><span class="sxs-lookup"><span data-stu-id="f06a5-171">See Also</span></span>  
 <span data-ttu-id="f06a5-172">[手順 2 a: ファイルの受信場所 FileAct ストア アンド フォワード (プル) シナリオの追加](../../adapters-and-accelerators/fileact-interact/step-2a-add-file-receive-locations-for-fileact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="f06a5-172">[Step 2A: Add FILE Receive Locations for the FileAct Store and Forward (Pull) Scenario](../../adapters-and-accelerators/fileact-interact/step-2a-add-file-receive-locations-for-fileact-store-and-forward-scenario.md) </span></span>  
 [<span data-ttu-id="f06a5-173">手順 2 b: Sw:HandleFileRequest をキャプチャするファイルの送信ポートを追加し、FileAct ストア アンド フォワードの Sw:HandleSnFRequest メッセージ (プル) のシナリオ</span><span class="sxs-lookup"><span data-stu-id="f06a5-173">Step 2B: Add FILE Send Ports to Capture the Sw:HandleFileRequest and Sw:HandleSnFRequest Messages for the FileAct Store and Forward (Pull) Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-2b-add-file-send-ports--get-sw-handlefilerequest-and-sw-handlesnfrequest.md)