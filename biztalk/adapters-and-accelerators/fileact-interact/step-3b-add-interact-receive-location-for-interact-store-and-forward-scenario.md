---
title: "手順 3 b: 対話の受信場所が、対話ストアと転送シナリオの追加 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: da077518-b2ee-4b5f-88d0-fe73af2baa7a
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5f6f0ffd20dba192a038981469164f63cdd7593f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-3b-add-an-interact-receive-location-for-the-interact-store-and-forward-scenario"></a><span data-ttu-id="25d96-102">手順 3 b: 追加、対話の受信場所が、対話ストアと転送シナリオ</span><span class="sxs-lookup"><span data-stu-id="25d96-102">Step 3B: Add an INTERACT Receive Location for the InterAct Store and Forward Scenario</span></span>
<span data-ttu-id="25d96-103">完全な[手順 3A: InterAct ストア アンド フォワードのシナリオのファイルの受信場所を追加](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-interact-store-and-forward-scenario.md)この手順を開始する前にします。</span><span class="sxs-lookup"><span data-stu-id="25d96-103">Complete [Step 3A: Add a FILE Receive Location for the InterAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-interact-store-and-forward-scenario.md) before you begin this step.</span></span>
  
## <a name="add-an-interact-receive-location"></a><span data-ttu-id="25d96-104">受信場所が、対話を追加します。</span><span class="sxs-lookup"><span data-stu-id="25d96-104">Add an INTERACT receive location</span></span>  
  
1.  <span data-ttu-id="25d96-105">開始**BizTalk Server 管理**です。</span><span class="sxs-lookup"><span data-stu-id="25d96-105">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="25d96-106">コンソール ツリーで、BizTalk グループを展開し、受信ポートを作成する BizTalk アプリケーションの順に展開します。</span><span class="sxs-lookup"><span data-stu-id="25d96-106">In the console tree, expand the BizTalk group, and then expand the BizTalk application for which you want to create a receive port.</span></span>  
  
3.  <span data-ttu-id="25d96-107">右クリック**受信ポート**、 をポイント**新規**、クリックして**一方向の受信ポート。**</span><span class="sxs-lookup"><span data-stu-id="25d96-107">Right-click **Receive Ports**, point to **New**, and then click **One-way Receive Port.**</span></span>  
  
4.  <span data-ttu-id="25d96-108">**受信ポートのプロパティ**ウィンドウで、受信ポート名 Tutorial_IA_HandleRequestOneWay_SnF です。</span><span class="sxs-lookup"><span data-stu-id="25d96-108">In the **Receive Port Properties** window, name the receive port, Tutorial_IA_HandleRequestOneWay_SnF.</span></span>  
  
5.  <span data-ttu-id="25d96-109">**受信ポートのプロパティ** ウィンドウで、**受信場所** タブで、をクリックして**新規**です。</span><span class="sxs-lookup"><span data-stu-id="25d96-109">In the **Receive Port Properties** window, on the **Receive Locations** tab, click **New**.</span></span>  
  
6.  <span data-ttu-id="25d96-110">**受信場所のプロパティ**ウィンドウの**全般** タブから、**トランスポートの種類**ドロップダウン リストで、 **INTERACT**、クリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="25d96-110">In the **Receive Location Properties** window, on the **General** tab, from the **Transport type** drop-down list, select **INTERACT**, and then click **Configure**.</span></span>  
  
7.  <span data-ttu-id="25d96-111">**トランスポートのプロパティの対話** ダイアログ ボックスで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="25d96-111">In the **INTERACT Transport Properties** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="25d96-112">**これを使用してください。**</span><span class="sxs-lookup"><span data-stu-id="25d96-112">**Use this**</span></span>|<span data-ttu-id="25d96-113">**これを行う**</span><span class="sxs-lookup"><span data-stu-id="25d96-113">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="25d96-114">**Password**</span><span class="sxs-lookup"><span data-stu-id="25d96-114">**Password**</span></span>|<span data-ttu-id="25d96-115">SAG への接続に使用するパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="25d96-115">Type the password you use to connect to SAG.</span></span> <span data-ttu-id="25d96-116">詳細については、SAG のヘルプを参照してください。</span><span class="sxs-lookup"><span data-stu-id="25d96-116">See SAG Help for more information.</span></span>|  
    |<span data-ttu-id="25d96-117">**ユーザー名**</span><span class="sxs-lookup"><span data-stu-id="25d96-117">**User name**</span></span>|<span data-ttu-id="25d96-118">SAG への接続に使用するユーザー名を入力します。</span><span class="sxs-lookup"><span data-stu-id="25d96-118">Type the user name you use to connect to SAG.</span></span>|  
    |<span data-ttu-id="25d96-119">**アプリケーション名**</span><span class="sxs-lookup"><span data-stu-id="25d96-119">**Application name**</span></span>|<span data-ttu-id="25d96-120">サーバーを入力\<アプリケーション インターフェイス名 >、SAG のボックス ルーティング セット。</span><span class="sxs-lookup"><span data-stu-id="25d96-120">Type the Server \<Application Interface Name> for the SAG box routing set.</span></span>|  
    |<span data-ttu-id="25d96-121">**暗号化モード**</span><span class="sxs-lookup"><span data-stu-id="25d96-121">**Crypto Mode**</span></span>|<span data-ttu-id="25d96-122">ドロップダウン リストから選択**詳細**です。</span><span class="sxs-lookup"><span data-stu-id="25d96-122">From the drop-down list, select **Advanced**.</span></span>|  
    |<span data-ttu-id="25d96-123">**LogMessageBody**</span><span class="sxs-lookup"><span data-stu-id="25d96-123">**LogMessageBody**</span></span>|<span data-ttu-id="25d96-124">ドロップダウン リストから選択**FALSE**です。</span><span class="sxs-lookup"><span data-stu-id="25d96-124">From the drop-down list, select **FALSE**.</span></span> <span data-ttu-id="25d96-125">**注:**を TRUE に設定する場合、BizTalk 追跡データベースでメッセージ本文が保持されます。</span><span class="sxs-lookup"><span data-stu-id="25d96-125">**Note:**  If you set to TRUE, it preserves the message body in the BizTalk Tracking database.</span></span> <span data-ttu-id="25d96-126">ただし、セキュリティ上の理由から、メッセージの本文見なすことができることはありません、BAM ポータルにします。</span><span class="sxs-lookup"><span data-stu-id="25d96-126">However, for security reasons, the message body can never be viewed in the BAM portal.</span></span>|  
    |<span data-ttu-id="25d96-127">**し**</span><span class="sxs-lookup"><span data-stu-id="25d96-127">**LogMessages**</span></span>|<span data-ttu-id="25d96-128">ドロップダウン リストから選択**TRUE**です。</span><span class="sxs-lookup"><span data-stu-id="25d96-128">From the drop-down list, select **TRUE**.</span></span> <span data-ttu-id="25d96-129">これにより、メッセージ イベントをキャプチャし、BAM ポータルで追跡できます。</span><span class="sxs-lookup"><span data-stu-id="25d96-129">This enables the message events to be captured and tracked in the BAM portal.</span></span>|  
    |<span data-ttu-id="25d96-130">**メッセージの形式**</span><span class="sxs-lookup"><span data-stu-id="25d96-130">**Message format**</span></span>|<span data-ttu-id="25d96-131">ドロップダウン リストから選択**InterActMessage**です。</span><span class="sxs-lookup"><span data-stu-id="25d96-131">From the drop-down list, select **InterActMessage**.</span></span>|  
    |<span data-ttu-id="25d96-132">**MemberRef**</span><span class="sxs-lookup"><span data-stu-id="25d96-132">**MemberRef**</span></span>|<span data-ttu-id="25d96-133">ドロップダウン リストから選択**ResponseHeader**です。</span><span class="sxs-lookup"><span data-stu-id="25d96-133">From the drop-down list, select **ResponseHeader**.</span></span>|  
    |<span data-ttu-id="25d96-134">**否認不可インジケーター**</span><span class="sxs-lookup"><span data-stu-id="25d96-134">**Non-Repudiation Indicator**</span></span>|<span data-ttu-id="25d96-135">ドロップダウン リストから選択**FALSE**です。</span><span class="sxs-lookup"><span data-stu-id="25d96-135">From the drop-down list, select **FALSE**.</span></span>|  
    |<span data-ttu-id="25d96-136">**応答側**</span><span class="sxs-lookup"><span data-stu-id="25d96-136">**Responder**</span></span>|<span data-ttu-id="25d96-137">適切な入力\<レスポンダー > SWIFT でのプロビジョニングに基づく文字列。</span><span class="sxs-lookup"><span data-stu-id="25d96-137">Type the appropriate \<Responder> string, based on your provisioning with SWIFT.</span></span>|  
    |<span data-ttu-id="25d96-138">**ResponseCrypto**</span><span class="sxs-lookup"><span data-stu-id="25d96-138">**ResponseCrypto**</span></span>|<span data-ttu-id="25d96-139">ドロップダウン リストから選択**FALSE**です。</span><span class="sxs-lookup"><span data-stu-id="25d96-139">From the drop-down list, select **FALSE**.</span></span>|  
    |<span data-ttu-id="25d96-140">**Timeout**</span><span class="sxs-lookup"><span data-stu-id="25d96-140">**Timeout**</span></span>|<span data-ttu-id="25d96-141">適切なタイムアウトが発生するまでの秒数を入力します。</span><span class="sxs-lookup"><span data-stu-id="25d96-141">Type an appropriate number of seconds before timeout should occur.</span></span>|  
    |<span data-ttu-id="25d96-142">**キューを取得します。**</span><span class="sxs-lookup"><span data-stu-id="25d96-142">**Acquire queue**</span></span>|<span data-ttu-id="25d96-143">SWIFT でのプロビジョニングに基づく、キュー名を入力します。</span><span class="sxs-lookup"><span data-stu-id="25d96-143">Type the queue name, based on your provisioning with SWIFT.</span></span>|  
    |<span data-ttu-id="25d96-144">**ForceAcquire**</span><span class="sxs-lookup"><span data-stu-id="25d96-144">**ForceAcquire**</span></span>|<span data-ttu-id="25d96-145">ドロップダウン リストから選択**TRUE**です。</span><span class="sxs-lookup"><span data-stu-id="25d96-145">From the drop-down list, select **TRUE**.</span></span>|  
    |<span data-ttu-id="25d96-146">**Order by**</span><span class="sxs-lookup"><span data-stu-id="25d96-146">**Order by**</span></span>|<span data-ttu-id="25d96-147">ドロップダウン リストから選択**Interact**です。</span><span class="sxs-lookup"><span data-stu-id="25d96-147">From the drop-down list, select **Interact**.</span></span>|  
    |<span data-ttu-id="25d96-148">**プッシュ セッション**</span><span class="sxs-lookup"><span data-stu-id="25d96-148">**Push session**</span></span>|<span data-ttu-id="25d96-149">ドロップダウン リストから選択**TRUE**です。</span><span class="sxs-lookup"><span data-stu-id="25d96-149">From the drop-down list, select **TRUE**.</span></span>|  
    |<span data-ttu-id="25d96-150">**回復モード**</span><span class="sxs-lookup"><span data-stu-id="25d96-150">**Recovery mode**</span></span>|<span data-ttu-id="25d96-151">ドロップダウン リストから選択**TRUE**です。</span><span class="sxs-lookup"><span data-stu-id="25d96-151">From the drop-down list, select **TRUE**.</span></span>|  
    |<span data-ttu-id="25d96-152">**SNL エンドポイント**</span><span class="sxs-lookup"><span data-stu-id="25d96-152">**SNL end-point**</span></span>|<span data-ttu-id="25d96-153">SAG ルーティング セットの適切なエンドポイントを入力します。</span><span class="sxs-lookup"><span data-stu-id="25d96-153">Type the appropriate end-point for the SAG routing set.</span></span> <span data-ttu-id="25d96-154">この値は、SAG で構成されている SnL エンドポイントと一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="25d96-154">This value should match the SnL endpoint you configured in SAG.</span></span>|  
  
8.  <span data-ttu-id="25d96-155">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="25d96-155">Click **OK**.</span></span>  
  
9. <span data-ttu-id="25d96-156">**受信場所のプロパティ** ウィンドウで、**全般** タブで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="25d96-156">In the **Receive Location Properties** window, on the **General** tab, do the following:</span></span>  
  
    |<span data-ttu-id="25d96-157">**これを使用してください。**</span><span class="sxs-lookup"><span data-stu-id="25d96-157">**Use this**</span></span>|<span data-ttu-id="25d96-158">**これを行う**</span><span class="sxs-lookup"><span data-stu-id="25d96-158">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="25d96-159">**受信ハンドラー**</span><span class="sxs-lookup"><span data-stu-id="25d96-159">**Receive handler**</span></span>|<span data-ttu-id="25d96-160">ドロップダウン リストから選択**BizTalkServerIsolatedHost**です。</span><span class="sxs-lookup"><span data-stu-id="25d96-160">From the drop-down list, select **BizTalkServerIsolatedHost**.</span></span>|  
    |<span data-ttu-id="25d96-161">**受信パイプライン**</span><span class="sxs-lookup"><span data-stu-id="25d96-161">**Receive pipeline**</span></span>|<span data-ttu-id="25d96-162">ドロップダウン リストから選択**XMLReceive**です。</span><span class="sxs-lookup"><span data-stu-id="25d96-162">From the drop-down list, select **XMLReceive**.</span></span>|  
  
10. <span data-ttu-id="25d96-163">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="25d96-163">Click **OK**.</span></span>  
  
## <a name="complete-steps"></a><span data-ttu-id="25d96-164">詳細な手順</span><span class="sxs-lookup"><span data-stu-id="25d96-164">Complete steps</span></span>
 <span data-ttu-id="25d96-165">[手順 3: 送信ポートを作成し、対話ストアと転送シナリオの受信ポート](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-interact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="25d96-165">[Step 3: Create Send Ports and Receive Ports for the InterAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-interact-store-and-forward-scenario.md) </span></span>  
 <span data-ttu-id="25d96-166">[手順 3: ファイルの受信場所が、対話ストアと転送シナリオの追加](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-interact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="25d96-166">[Step 3A: Add a FILE Receive Location for the InterAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-interact-store-and-forward-scenario.md) </span></span>  
 [<span data-ttu-id="25d96-167">手順 3 C: InterAct ストアと転送シナリオ Sw:HandleRequest メッセージをキャプチャする FILE 送信ポートの追加</span><span class="sxs-lookup"><span data-stu-id="25d96-167">Step 3C: Add a FILE Send Port to Capture the Sw:HandleRequest Message for the InterAct Store and Forward Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlerequest-interact-store-and-forward.md)  
 [<span data-ttu-id="25d96-168">ステップ 3 D: InterAct ストアと転送シナリオの対話の送信ポートの追加</span><span class="sxs-lookup"><span data-stu-id="25d96-168">Step 3D: Add an INTERACT Send Port for the InterAct Store and Forward Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-3d-add-an-interact-send-port-for-the-interact-store-and-forward-scenario.md)