---
title: "手順 1: InterAct ストア アンド フォワード (プル) シナリオの迅速な対応アダプターを構成する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4182021c-36c9-4c96-b2fa-e23c87862cfe
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d9de8c569744c5bbf750ef2aa804efbc456cd74a
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="step-1-configure-the-swift-adapter-for-the-interact-store-and-forward-pull-scenario"></a><span data-ttu-id="94424-102">手順 1: InterAct ストア アンド フォワード (プル) シナリオの迅速な対応アダプターを構成します。</span><span class="sxs-lookup"><span data-stu-id="94424-102">Step 1: Configure the SWIFT Adapter for the InterAct Store and Forward (Pull) Scenario</span></span>
<span data-ttu-id="94424-103">この手順を開始する前に行う必要があります[、チュートリアルを使用する準備](../../adapters-and-accelerators/fileact-interact/preparing-to-use-the-tutorial1.md)です。</span><span class="sxs-lookup"><span data-stu-id="94424-103">Before you begin this step, you must complete [Preparing to Use the Tutorial](../../adapters-and-accelerators/fileact-interact/preparing-to-use-the-tutorial1.md).</span></span>  
  
### <a name="to-configure-the-swift-adapter"></a><span data-ttu-id="94424-104">SWIFT のアダプターを構成するには</span><span class="sxs-lookup"><span data-stu-id="94424-104">To configure the SWIFT adapter</span></span>  
  
1.  <span data-ttu-id="94424-105">開始**BizTalk Server 管理**です。</span><span class="sxs-lookup"><span data-stu-id="94424-105">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="94424-106">コンソール ツリーで、BizTalk Server 管理コンソールを展開し、BizTalk グループを展開し、**プラットフォームの設定**、展開**アダプター**を右クリックして**INTERACT**、 をポイント**新規**、クリックして**送信ハンドラー**です。</span><span class="sxs-lookup"><span data-stu-id="94424-106">In the console tree, expand BizTalk Server Administration, expand the BizTalk group, expand **Platform Settings**, expand **Adapter**, right-click **INTERACT**, point to **New**, and then click **Send Handler**.</span></span>  
  
3.  <span data-ttu-id="94424-107">**アダプター ハンドラーのプロパティ-[対話**ダイアログ ボックスの**全般**] タブから、**ホスト名**ドロップダウン リストで、 **interacthost**、クリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="94424-107">In the **INTERACT – Adapter Handler Properties** dialog box, on the **General** tab, from the **Host name** drop-down list, select **interacthost**, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="94424-108">**トランスポートのプロパティの対話** ダイアログ ボックスで、**プロパティ** タブで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="94424-108">In the **INTERACT Transport Properties** dialog box, on the **Properties** tab, do the following:</span></span>  
  
    |<span data-ttu-id="94424-109">**これを使用してください。**</span><span class="sxs-lookup"><span data-stu-id="94424-109">**Use this**</span></span>|<span data-ttu-id="94424-110">**これを行う**</span><span class="sxs-lookup"><span data-stu-id="94424-110">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="94424-111">**引数**</span><span class="sxs-lookup"><span data-stu-id="94424-111">**Arguments**</span></span>|<span data-ttu-id="94424-112">次の引数を入力: – SagMessagePartner \<SAG で対話するクライアントのメッセージのパートナーが作成された\>**注:**引数で、クライアントは SAG で構成されている MessagePartner です。</span><span class="sxs-lookup"><span data-stu-id="94424-112">Type the following argument: –SagMessagePartner \<Interact Client Message Partner created in SAG\> **Note:**  The client in the argument is the MessagePartner you configured in SAG.</span></span>|  
    |<span data-ttu-id="94424-113">**暗号化モード**</span><span class="sxs-lookup"><span data-stu-id="94424-113">**Crypto Mode**</span></span>|<span data-ttu-id="94424-114">ドロップダウン リストから選択**詳細**です。</span><span class="sxs-lookup"><span data-stu-id="94424-114">From the drop-down list, select **Advanced**.</span></span>|  
    |<span data-ttu-id="94424-115">**LogMessageBody**</span><span class="sxs-lookup"><span data-stu-id="94424-115">**LogMessageBody**</span></span>|<span data-ttu-id="94424-116">ドロップダウン リストから選択**FALSE**です。</span><span class="sxs-lookup"><span data-stu-id="94424-116">From the drop-down list, select **FALSE**.</span></span> <span data-ttu-id="94424-117">**注:**を TRUE に設定する場合、BizTalk 追跡データベースでメッセージ本文が保持されます。</span><span class="sxs-lookup"><span data-stu-id="94424-117">**Note:**  If you set to TRUE, it preserves the message body in the BizTalk Tracking database.</span></span> <span data-ttu-id="94424-118">ただし、セキュリティ上の理由から、メッセージの本文見なすことができることはありません、BAM ポータルにします。</span><span class="sxs-lookup"><span data-stu-id="94424-118">However, for security reasons, the message body can never be viewed in the BAM portal.</span></span>|  
    |<span data-ttu-id="94424-119">**し**</span><span class="sxs-lookup"><span data-stu-id="94424-119">**LogMessages**</span></span>|<span data-ttu-id="94424-120">ドロップダウン リストから選択**TRUE**です。</span><span class="sxs-lookup"><span data-stu-id="94424-120">From the drop-down list, select **TRUE**.</span></span> <span data-ttu-id="94424-121">これにより、メッセージ イベントをキャプチャし、BAM ポータルで追跡できます。</span><span class="sxs-lookup"><span data-stu-id="94424-121">This enables the message events to be captured and tracked in the BAM portal.</span></span>|  
    |<span data-ttu-id="94424-122">**[有効化]**</span><span class="sxs-lookup"><span data-stu-id="94424-122">**Enable**</span></span>|<span data-ttu-id="94424-123">False : </span><span class="sxs-lookup"><span data-stu-id="94424-123">False.</span></span>|  
    |<span data-ttu-id="94424-124">**Password**</span><span class="sxs-lookup"><span data-stu-id="94424-124">**Password**</span></span>|<span data-ttu-id="94424-125">SAG への接続に使用するパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="94424-125">Type the password you use to connect to SAG.</span></span> <span data-ttu-id="94424-126">詳細については、SAG のヘルプを参照してください。</span><span class="sxs-lookup"><span data-stu-id="94424-126">See SAG Help for more information.</span></span>|  
    |<span data-ttu-id="94424-127">**ユーザー名**</span><span class="sxs-lookup"><span data-stu-id="94424-127">**Username**</span></span>|<span data-ttu-id="94424-128">SAG への接続に使用するユーザー名を入力します。</span><span class="sxs-lookup"><span data-stu-id="94424-128">Type the user name you use to connect to SAG.</span></span>|  
  
5.  <span data-ttu-id="94424-129">をクリックして**OK**対話トランスポートのプロパティ ダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="94424-129">Click **OK** to close the INTERACT Transport Properties dialog box.</span></span>  
  
6.  <span data-ttu-id="94424-130">をクリックして**OK** INTERACT-アダプター ハンドラーのプロパティ ダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="94424-130">Click **OK** to close the INTERACT – Adapter Handler Properties dialog box.</span></span>  
  
7.  <span data-ttu-id="94424-131">メッセージ ボックスで、をクリックして**OK**、し対話するホスト インスタンスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="94424-131">In the message box, click **OK**, and then restart the InterAct host instance.</span></span>  
  
8.  <span data-ttu-id="94424-132">手順 1. を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="94424-132">Repeat step 1.</span></span>  
  
9. <span data-ttu-id="94424-133">コンソール ツリーで、BizTalk Server 管理コンソールを展開し、 **BizTalk**グループで、[**プラットフォームの設定**、展開**アダプター**対話を選択し、を開く**BizTalkServerApplication** ] をクリックし、**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="94424-133">In the console tree, expand BizTalk Server Administration, expand the **BizTalk** group, expand **Platform Settings**, expand **Adapter**, select INTERACT, open **BizTalkServerApplication** and then, click **Properties**.</span></span>  
  
10. <span data-ttu-id="94424-134">**トランスポートのプロパティの対話** ダイアログ ボックスで、**プロパティ** タブで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="94424-134">In the **INTERACT Transport Properties** dialog box, on the **Properties** tab, do the following:</span></span>  
  
    |<span data-ttu-id="94424-135">**これを使用してください。**</span><span class="sxs-lookup"><span data-stu-id="94424-135">**Use this**</span></span>|<span data-ttu-id="94424-136">**これを行う**</span><span class="sxs-lookup"><span data-stu-id="94424-136">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="94424-137">**引数**</span><span class="sxs-lookup"><span data-stu-id="94424-137">**Arguments**</span></span>|<span data-ttu-id="94424-138">次の引数を入力: – SagMessagePartner \<SAG で対話するクライアントのメッセージのパートナーが作成された\>**注:**引数で、クライアントは SAG で構成されている MessagePartner です。</span><span class="sxs-lookup"><span data-stu-id="94424-138">Type the following argument: –SagMessagePartner \<Interact Client Message Partner created in SAG\> **Note:**  The client in the argument is the MessagePartner you configured in SAG.</span></span>|  
    |<span data-ttu-id="94424-139">**暗号化モード**</span><span class="sxs-lookup"><span data-stu-id="94424-139">**Crypto Mode**</span></span>|<span data-ttu-id="94424-140">ドロップダウン リストから選択**詳細**です。</span><span class="sxs-lookup"><span data-stu-id="94424-140">From the drop-down list, select **Advanced**.</span></span>|  
    |<span data-ttu-id="94424-141">**LogMessageBody**</span><span class="sxs-lookup"><span data-stu-id="94424-141">**LogMessageBody**</span></span>|<span data-ttu-id="94424-142">ドロップダウン リストから選択**FALSE**です。</span><span class="sxs-lookup"><span data-stu-id="94424-142">From the drop-down list, select **FALSE**.</span></span> <span data-ttu-id="94424-143">**注:**を TRUE に設定する場合、BizTalk 追跡データベースでメッセージ本文が保持されます。</span><span class="sxs-lookup"><span data-stu-id="94424-143">**Note:**  If you set to TRUE, it preserves the message body in the BizTalk Tracking database.</span></span> <span data-ttu-id="94424-144">ただし、セキュリティ上の理由から、メッセージの本文見なすことができることはありません、BAM ポータルにします。</span><span class="sxs-lookup"><span data-stu-id="94424-144">However, for security reasons, the message body can never be viewed in the BAM portal.</span></span>|  
    |<span data-ttu-id="94424-145">**し**</span><span class="sxs-lookup"><span data-stu-id="94424-145">**LogMessages**</span></span>|<span data-ttu-id="94424-146">ドロップダウン リストから選択**TRUE**です。</span><span class="sxs-lookup"><span data-stu-id="94424-146">From the drop-down list, select **TRUE**.</span></span> <span data-ttu-id="94424-147">これにより、メッセージ イベントをキャプチャし、BAM ポータルで追跡できます。</span><span class="sxs-lookup"><span data-stu-id="94424-147">This enables the message events to be captured and tracked in the BAM portal.</span></span>|  
    |<span data-ttu-id="94424-148">**[有効化]**</span><span class="sxs-lookup"><span data-stu-id="94424-148">**Enable**</span></span>|<span data-ttu-id="94424-149">True</span><span class="sxs-lookup"><span data-stu-id="94424-149">True</span></span>|  
    |<span data-ttu-id="94424-150">**Password**</span><span class="sxs-lookup"><span data-stu-id="94424-150">**Password**</span></span>|<span data-ttu-id="94424-151">SAG への接続に使用するパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="94424-151">Type the password you use to connect to SAG.</span></span> <span data-ttu-id="94424-152">詳細については、SAG のヘルプを参照してください。</span><span class="sxs-lookup"><span data-stu-id="94424-152">See SAG Help for more information.</span></span>|  
    |<span data-ttu-id="94424-153">**ユーザー名**</span><span class="sxs-lookup"><span data-stu-id="94424-153">**Username**</span></span>|<span data-ttu-id="94424-154">SAG への接続に使用するユーザー名を入力します。</span><span class="sxs-lookup"><span data-stu-id="94424-154">Type the user name you use to connect to SAG.</span></span>|  
  
11. <span data-ttu-id="94424-155">をクリックして**OK**対話トランスポートのプロパティ ダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="94424-155">Click **OK** to close the INTERACT Transport Properties dialog box.</span></span>  
  
12. <span data-ttu-id="94424-156">選択**しやすいように、既定のハンドラー**オプション。</span><span class="sxs-lookup"><span data-stu-id="94424-156">Select **make this the default handler** option.</span></span>  
  
13. <span data-ttu-id="94424-157">をクリックして**OK** INTERACT-アダプター ハンドラーのプロパティ ダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="94424-157">Click **OK** to close the INTERACT– Adapter Handler Properties dialog box.</span></span>  
  
14. <span data-ttu-id="94424-158">メッセージ ボックスで、をクリックして**OK**、し、再起動、 **BizTalkServerApplication**ホスト インスタンス。</span><span class="sxs-lookup"><span data-stu-id="94424-158">In the Message box, click **OK**, and then restart the **BizTalkServerApplication** host instance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94424-159">参照</span><span class="sxs-lookup"><span data-stu-id="94424-159">See Also</span></span>  
 <span data-ttu-id="94424-160">[ステップ 2: 送信ポートを作成し、対話ストア アンド フォワード (プル) シナリオの受信ポート](../../adapters-and-accelerators/fileact-interact/step-2-create-send-ports-and-receive-ports-for-the-interact-store-and-forward.md) </span><span class="sxs-lookup"><span data-stu-id="94424-160">[Step2: Create Send Ports and Receive Ports for the InterAct Store and Forward (Pull) Scenario](../../adapters-and-accelerators/fileact-interact/step-2-create-send-ports-and-receive-ports-for-the-interact-store-and-forward.md) </span></span>  
 <span data-ttu-id="94424-161">[手順 3: InterAct ストア アンド フォワード (プル) シナリオ用の動的送信ポートにオーケストレーションを作成します。](../../adapters-and-accelerators/fileact-interact/step-3-create-orchestration-with-dynamic-send-for-interact-store-and-forward.md) </span><span class="sxs-lookup"><span data-stu-id="94424-161">[Step3: Create an orchestration with  dynamic send port for the InterAct Store and Forward (Pull) Scenario](../../adapters-and-accelerators/fileact-interact/step-3-create-orchestration-with-dynamic-send-for-interact-store-and-forward.md) </span></span>  
 [<span data-ttu-id="94424-162">手順 4: InterAct ストア アンド フォワード (プル) エンド ツー エンド シナリオをテストする</span><span class="sxs-lookup"><span data-stu-id="94424-162">Step 4: Test the InterAct Store and Forward (Pull) End-to-End Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-4-test-the-interact-store-and-forward-pull-end-to-end-scenario.md)