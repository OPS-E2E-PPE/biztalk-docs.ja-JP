---
title: 手順 3 b:INTERACT の受信場所 InterAct ストア アンド フォワード シナリオ用の追加 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: da077518-b2ee-4b5f-88d0-fe73af2baa7a
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0dd50d40c033fa319e2690ea1a3c6773f694bec5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65365634"
---
# <a name="step-3b-add-an-interact-receive-location-for-the-interact-store-and-forward-scenario"></a><span data-ttu-id="be2f6-102">手順 3 b:INTERACT の受信場所 InterAct ストア アンド フォワード シナリオ用の追加します。</span><span class="sxs-lookup"><span data-stu-id="be2f6-102">Step 3B: Add an INTERACT Receive Location for the InterAct Store and Forward Scenario</span></span>
<span data-ttu-id="be2f6-103">完全な[手順 3 a:InterAct ストア アンド フォワード シナリオ用のファイルの受信場所を追加](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-interact-store-and-forward-scenario.md)この手順を開始する前にします。</span><span class="sxs-lookup"><span data-stu-id="be2f6-103">Complete [Step 3A: Add a FILE Receive Location for the InterAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-interact-store-and-forward-scenario.md) before you begin this step.</span></span>
  
## <a name="add-an-interact-receive-location"></a><span data-ttu-id="be2f6-104">INTERACT の受信場所を追加します。</span><span class="sxs-lookup"><span data-stu-id="be2f6-104">Add an INTERACT receive location</span></span>  
  
1.  <span data-ttu-id="be2f6-105">開始**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="be2f6-105">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="be2f6-106">コンソール ツリーで、BizTalk グループを展開し、受信ポートを作成する BizTalk アプリケーションを順に展開します。</span><span class="sxs-lookup"><span data-stu-id="be2f6-106">In the console tree, expand the BizTalk group, and then expand the BizTalk application for which you want to create a receive port.</span></span>  
  
3.  <span data-ttu-id="be2f6-107">右クリック**受信ポート**、 をポイント**新規**、 をクリックし、**一方向の受信ポート。**</span><span class="sxs-lookup"><span data-stu-id="be2f6-107">Right-click **Receive Ports**, point to **New**, and then click **One-way Receive Port.**</span></span>  
  
4.  <span data-ttu-id="be2f6-108">**受信ポートのプロパティ**ウィンドウで、名前、受信ポート Tutorial_IA_HandleRequestOneWay_SnF します。</span><span class="sxs-lookup"><span data-stu-id="be2f6-108">In the **Receive Port Properties** window, name the receive port, Tutorial_IA_HandleRequestOneWay_SnF.</span></span>  
  
5.  <span data-ttu-id="be2f6-109">**受信ポートのプロパティ**ウィンドウで、**受信場所**] タブで [**新規**します。</span><span class="sxs-lookup"><span data-stu-id="be2f6-109">In the **Receive Port Properties** window, on the **Receive Locations** tab, click **New**.</span></span>  
  
6.  <span data-ttu-id="be2f6-110">**受信場所のプロパティ**ウィンドウの**全般** タブから、**トランスポートの種類**ドロップダウン リストで、 **INTERACT**、クリックして**構成**します。</span><span class="sxs-lookup"><span data-stu-id="be2f6-110">In the **Receive Location Properties** window, on the **General** tab, from the **Transport type** drop-down list, select **INTERACT**, and then click **Configure**.</span></span>  
  
7.  <span data-ttu-id="be2f6-111">**トランスポートのプロパティの対話** ダイアログ ボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="be2f6-111">In the **INTERACT Transport Properties** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="be2f6-112">**これを使用して、**</span><span class="sxs-lookup"><span data-stu-id="be2f6-112">**Use this**</span></span>|<span data-ttu-id="be2f6-113">**これを行う**</span><span class="sxs-lookup"><span data-stu-id="be2f6-113">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="be2f6-114">**Password**</span><span class="sxs-lookup"><span data-stu-id="be2f6-114">**Password**</span></span>|<span data-ttu-id="be2f6-115">SAG への接続に使用するパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="be2f6-115">Type the password you use to connect to SAG.</span></span> <span data-ttu-id="be2f6-116">詳細については、SAG ヘルプを参照してください。</span><span class="sxs-lookup"><span data-stu-id="be2f6-116">See SAG Help for more information.</span></span>|  
    |<span data-ttu-id="be2f6-117">**ユーザー名**</span><span class="sxs-lookup"><span data-stu-id="be2f6-117">**User name**</span></span>|<span data-ttu-id="be2f6-118">SAG への接続に使用するユーザー名を入力します。</span><span class="sxs-lookup"><span data-stu-id="be2f6-118">Type the user name you use to connect to SAG.</span></span>|  
    |<span data-ttu-id="be2f6-119">**アプリケーション名**</span><span class="sxs-lookup"><span data-stu-id="be2f6-119">**Application name**</span></span>|<span data-ttu-id="be2f6-120">サーバーの入力\<アプリケーション インターフェイス名\>SAG のボックス ルーティング セット。</span><span class="sxs-lookup"><span data-stu-id="be2f6-120">Type the Server \<Application Interface Name\> for the SAG box routing set.</span></span>|  
    |<span data-ttu-id="be2f6-121">**暗号モード**</span><span class="sxs-lookup"><span data-stu-id="be2f6-121">**Crypto Mode**</span></span>|<span data-ttu-id="be2f6-122">ドロップダウン リストから選択**詳細**します。</span><span class="sxs-lookup"><span data-stu-id="be2f6-122">From the drop-down list, select **Advanced**.</span></span>|  
    |<span data-ttu-id="be2f6-123">**LogMessageBody**</span><span class="sxs-lookup"><span data-stu-id="be2f6-123">**LogMessageBody**</span></span>|<span data-ttu-id="be2f6-124">ドロップダウン リストから選択**FALSE**します。</span><span class="sxs-lookup"><span data-stu-id="be2f6-124">From the drop-down list, select **FALSE**.</span></span> <span data-ttu-id="be2f6-125">**注:** TRUE に設定した場合は、BizTalk 追跡データベースでメッセージの本文を保持します。</span><span class="sxs-lookup"><span data-stu-id="be2f6-125">**Note:**  If you set to TRUE, it preserves the message body in the BizTalk Tracking database.</span></span> <span data-ttu-id="be2f6-126">ただし、セキュリティ上の理由から、メッセージ本文は、BAM ポータルでは表示ことはありませんすることができます。</span><span class="sxs-lookup"><span data-stu-id="be2f6-126">However, for security reasons, the message body can never be viewed in the BAM portal.</span></span>|  
    |<span data-ttu-id="be2f6-127">**し**</span><span class="sxs-lookup"><span data-stu-id="be2f6-127">**LogMessages**</span></span>|<span data-ttu-id="be2f6-128">ドロップダウン リストから選択**TRUE**します。</span><span class="sxs-lookup"><span data-stu-id="be2f6-128">From the drop-down list, select **TRUE**.</span></span> <span data-ttu-id="be2f6-129">これにより、メッセージ イベントをキャプチャし、BAM ポータルで追跡できます。</span><span class="sxs-lookup"><span data-stu-id="be2f6-129">This enables the message events to be captured and tracked in the BAM portal.</span></span>|  
    |<span data-ttu-id="be2f6-130">**メッセージの形式**</span><span class="sxs-lookup"><span data-stu-id="be2f6-130">**Message format**</span></span>|<span data-ttu-id="be2f6-131">ドロップダウン リストから選択**InterActMessage**します。</span><span class="sxs-lookup"><span data-stu-id="be2f6-131">From the drop-down list, select **InterActMessage**.</span></span>|  
    |<span data-ttu-id="be2f6-132">**MemberRef**</span><span class="sxs-lookup"><span data-stu-id="be2f6-132">**MemberRef**</span></span>|<span data-ttu-id="be2f6-133">ドロップダウン リストから選択**ResponseHeader**します。</span><span class="sxs-lookup"><span data-stu-id="be2f6-133">From the drop-down list, select **ResponseHeader**.</span></span>|  
    |<span data-ttu-id="be2f6-134">**否認不可のインジケーター**</span><span class="sxs-lookup"><span data-stu-id="be2f6-134">**Non-Repudiation Indicator**</span></span>|<span data-ttu-id="be2f6-135">ドロップダウン リストから選択**FALSE**します。</span><span class="sxs-lookup"><span data-stu-id="be2f6-135">From the drop-down list, select **FALSE**.</span></span>|  
    |<span data-ttu-id="be2f6-136">**応答側**</span><span class="sxs-lookup"><span data-stu-id="be2f6-136">**Responder**</span></span>|<span data-ttu-id="be2f6-137">適切な入力\<レスポンダー\> SWIFT で、プロビジョニングに基づく文字列。</span><span class="sxs-lookup"><span data-stu-id="be2f6-137">Type the appropriate \<Responder\> string, based on your provisioning with SWIFT.</span></span>|  
    |<span data-ttu-id="be2f6-138">**ResponseCrypto**</span><span class="sxs-lookup"><span data-stu-id="be2f6-138">**ResponseCrypto**</span></span>|<span data-ttu-id="be2f6-139">ドロップダウン リストから選択**FALSE**します。</span><span class="sxs-lookup"><span data-stu-id="be2f6-139">From the drop-down list, select **FALSE**.</span></span>|  
    |<span data-ttu-id="be2f6-140">**Timeout**</span><span class="sxs-lookup"><span data-stu-id="be2f6-140">**Timeout**</span></span>|<span data-ttu-id="be2f6-141">適切なタイムアウトが発生するまでの秒数を入力します。</span><span class="sxs-lookup"><span data-stu-id="be2f6-141">Type an appropriate number of seconds before timeout should occur.</span></span>|  
    |<span data-ttu-id="be2f6-142">**キューを取得します。**</span><span class="sxs-lookup"><span data-stu-id="be2f6-142">**Acquire queue**</span></span>|<span data-ttu-id="be2f6-143">SWIFT で、プロビジョニングに基づく、キュー名を入力します。</span><span class="sxs-lookup"><span data-stu-id="be2f6-143">Type the queue name, based on your provisioning with SWIFT.</span></span>|  
    |<span data-ttu-id="be2f6-144">**ForceAcquire**</span><span class="sxs-lookup"><span data-stu-id="be2f6-144">**ForceAcquire**</span></span>|<span data-ttu-id="be2f6-145">ドロップダウン リストから選択**TRUE**します。</span><span class="sxs-lookup"><span data-stu-id="be2f6-145">From the drop-down list, select **TRUE**.</span></span>|  
    |<span data-ttu-id="be2f6-146">**並べ替え**</span><span class="sxs-lookup"><span data-stu-id="be2f6-146">**Order by**</span></span>|<span data-ttu-id="be2f6-147">ドロップダウン リストから選択**Interact**します。</span><span class="sxs-lookup"><span data-stu-id="be2f6-147">From the drop-down list, select **Interact**.</span></span>|  
    |<span data-ttu-id="be2f6-148">**プッシュ セッション**</span><span class="sxs-lookup"><span data-stu-id="be2f6-148">**Push session**</span></span>|<span data-ttu-id="be2f6-149">ドロップダウン リストから選択**TRUE**します。</span><span class="sxs-lookup"><span data-stu-id="be2f6-149">From the drop-down list, select **TRUE**.</span></span>|  
    |<span data-ttu-id="be2f6-150">**回復モード**</span><span class="sxs-lookup"><span data-stu-id="be2f6-150">**Recovery mode**</span></span>|<span data-ttu-id="be2f6-151">ドロップダウン リストから選択**TRUE**します。</span><span class="sxs-lookup"><span data-stu-id="be2f6-151">From the drop-down list, select **TRUE**.</span></span>|  
    |<span data-ttu-id="be2f6-152">**SNL エンドポイント**</span><span class="sxs-lookup"><span data-stu-id="be2f6-152">**SNL end-point**</span></span>|<span data-ttu-id="be2f6-153">SAG ルーティング セットの適切なエンドポイントを入力します。</span><span class="sxs-lookup"><span data-stu-id="be2f6-153">Type the appropriate end-point for the SAG routing set.</span></span> <span data-ttu-id="be2f6-154">この値は、SAG で構成した SnL エンドポイントと一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="be2f6-154">This value should match the SnL endpoint you configured in SAG.</span></span>|  
  
8.  <span data-ttu-id="be2f6-155">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="be2f6-155">Click **OK**.</span></span>  
  
9. <span data-ttu-id="be2f6-156">**受信場所のプロパティ**ウィンドウの**全般** タブで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="be2f6-156">In the **Receive Location Properties** window, on the **General** tab, do the following:</span></span>  
  
    |<span data-ttu-id="be2f6-157">**これを使用して、**</span><span class="sxs-lookup"><span data-stu-id="be2f6-157">**Use this**</span></span>|<span data-ttu-id="be2f6-158">**これを行う**</span><span class="sxs-lookup"><span data-stu-id="be2f6-158">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="be2f6-159">**受信ハンドラー**</span><span class="sxs-lookup"><span data-stu-id="be2f6-159">**Receive handler**</span></span>|<span data-ttu-id="be2f6-160">ドロップダウン リストから選択**BizTalkServerIsolatedHost**します。</span><span class="sxs-lookup"><span data-stu-id="be2f6-160">From the drop-down list, select **BizTalkServerIsolatedHost**.</span></span>|  
    |<span data-ttu-id="be2f6-161">**受信パイプライン**</span><span class="sxs-lookup"><span data-stu-id="be2f6-161">**Receive pipeline**</span></span>|<span data-ttu-id="be2f6-162">ドロップダウン リストから選択**XMLReceive**します。</span><span class="sxs-lookup"><span data-stu-id="be2f6-162">From the drop-down list, select **XMLReceive**.</span></span>|  
  
10. <span data-ttu-id="be2f6-163">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="be2f6-163">Click **OK**.</span></span>  
  
## <a name="complete-steps"></a><span data-ttu-id="be2f6-164">手順を完了します</span><span class="sxs-lookup"><span data-stu-id="be2f6-164">Complete steps</span></span>
 <span data-ttu-id="be2f6-165">[ステップ 3:送信ポートの作成し、InterAct ストア アンド フォワード シナリオ用の受信ポート](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-interact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="be2f6-165">[Step 3: Create Send Ports and Receive Ports for the InterAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-interact-store-and-forward-scenario.md) </span></span>  
 <span data-ttu-id="be2f6-166">[手順 3 a:InterAct ストア アンド フォワード シナリオ用の場所の受信ファイルを追加します。](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-interact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="be2f6-166">[Step 3A: Add a FILE Receive Location for the InterAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-interact-store-and-forward-scenario.md) </span></span>  
 [<span data-ttu-id="be2f6-167">手順 3 C:InterAct ストア アンド フォワード シナリオ用に Sw:HandleRequest メッセージをキャプチャする FILE 送信ポートの追加します。</span><span class="sxs-lookup"><span data-stu-id="be2f6-167">Step 3C: Add a FILE Send Port to Capture the Sw:HandleRequest Message for the InterAct Store and Forward Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlerequest-interact-store-and-forward.md)  
 [<span data-ttu-id="be2f6-168">手順 3 D:InterAct ストア アンド フォワード シナリオ用に INTERACT 送信ポートを追加します。</span><span class="sxs-lookup"><span data-stu-id="be2f6-168">Step 3D: Add an INTERACT Send Port for the InterAct Store and Forward Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-3d-add-an-interact-send-port-for-the-interact-store-and-forward-scenario.md)