---
title: 手順 1:InterAct ストア アンド フォワード (プル) シナリオ用に SWIFT アダプターを構成する |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4182021c-36c9-4c96-b2fa-e23c87862cfe
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a609ad94e6d8b0dcafb50d1025159b1dfcdde5af
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65366493"
---
# <a name="step-1-configure-the-swift-adapter-for-the-interact-store-and-forward-pull-scenario"></a><span data-ttu-id="dd136-102">手順 1:InterAct ストア アンド フォワード (プル) シナリオ用に SWIFT アダプターを構成します。</span><span class="sxs-lookup"><span data-stu-id="dd136-102">Step 1: Configure the SWIFT Adapter for the InterAct Store and Forward (Pull) Scenario</span></span>
<span data-ttu-id="dd136-103">この手順を開始する前に行う必要があります[チュートリアルを使用する準備](../../adapters-and-accelerators/fileact-interact/preparing-to-use-the-tutorial1.md)します。</span><span class="sxs-lookup"><span data-stu-id="dd136-103">Before you begin this step, you must complete [Preparing to Use the Tutorial](../../adapters-and-accelerators/fileact-interact/preparing-to-use-the-tutorial1.md).</span></span>  
  
### <a name="to-configure-the-swift-adapter"></a><span data-ttu-id="dd136-104">SWIFT アダプターを構成するには</span><span class="sxs-lookup"><span data-stu-id="dd136-104">To configure the SWIFT adapter</span></span>  
  
1.  <span data-ttu-id="dd136-105">開始**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="dd136-105">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="dd136-106">コンソール ツリーで、BizTalk Server 管理コンソールを展開し、BizTalk グループを展開し、**プラットフォームの設定**、展開**アダプター**、右クリックして**INTERACT**、 をポイント**新規**、 をクリックし、**送信ハンドラー**します。</span><span class="sxs-lookup"><span data-stu-id="dd136-106">In the console tree, expand BizTalk Server Administration, expand the BizTalk group, expand **Platform Settings**, expand **Adapter**, right-click **INTERACT**, point to **New**, and then click **Send Handler**.</span></span>  
  
3.  <span data-ttu-id="dd136-107">**アダプター ハンドラーのプロパティ-対話** ダイアログ ボックスで、**全般** タブから、**ホスト名**ドロップダウン リストで、 **interacthost**、 をクリックし、**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="dd136-107">In the **INTERACT – Adapter Handler Properties** dialog box, on the **General** tab, from the **Host name** drop-down list, select **interacthost**, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="dd136-108">**トランスポートのプロパティの対話** ダイアログ ボックスで、**プロパティ** タブで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="dd136-108">In the **INTERACT Transport Properties** dialog box, on the **Properties** tab, do the following:</span></span>  
  
    |<span data-ttu-id="dd136-109">**これを使用して、**</span><span class="sxs-lookup"><span data-stu-id="dd136-109">**Use this**</span></span>|<span data-ttu-id="dd136-110">**これを行う**</span><span class="sxs-lookup"><span data-stu-id="dd136-110">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="dd136-111">**引数**</span><span class="sxs-lookup"><span data-stu-id="dd136-111">**Arguments**</span></span>|<span data-ttu-id="dd136-112">次の引数を入力: – SagMessagePartner \<SAG で対話するクライアントのメッセージのパートナーが作成された\>**に注意してください。** 引数のクライアントは、SAG で構成した MessagePartner です。</span><span class="sxs-lookup"><span data-stu-id="dd136-112">Type the following argument: –SagMessagePartner \<Interact Client Message Partner created in SAG\> **Note:**  The client in the argument is the MessagePartner you configured in SAG.</span></span>|  
    |<span data-ttu-id="dd136-113">**暗号モード**</span><span class="sxs-lookup"><span data-stu-id="dd136-113">**Crypto Mode**</span></span>|<span data-ttu-id="dd136-114">ドロップダウン リストから選択**詳細**します。</span><span class="sxs-lookup"><span data-stu-id="dd136-114">From the drop-down list, select **Advanced**.</span></span>|  
    |<span data-ttu-id="dd136-115">**LogMessageBody**</span><span class="sxs-lookup"><span data-stu-id="dd136-115">**LogMessageBody**</span></span>|<span data-ttu-id="dd136-116">ドロップダウン リストから選択**FALSE**します。</span><span class="sxs-lookup"><span data-stu-id="dd136-116">From the drop-down list, select **FALSE**.</span></span> <span data-ttu-id="dd136-117">**注:** TRUE に設定した場合は、BizTalk 追跡データベースでメッセージの本文を保持します。</span><span class="sxs-lookup"><span data-stu-id="dd136-117">**Note:**  If you set to TRUE, it preserves the message body in the BizTalk Tracking database.</span></span> <span data-ttu-id="dd136-118">ただし、セキュリティ上の理由から、メッセージ本文は、BAM ポータルでは表示ことはありませんすることができます。</span><span class="sxs-lookup"><span data-stu-id="dd136-118">However, for security reasons, the message body can never be viewed in the BAM portal.</span></span>|  
    |<span data-ttu-id="dd136-119">**し**</span><span class="sxs-lookup"><span data-stu-id="dd136-119">**LogMessages**</span></span>|<span data-ttu-id="dd136-120">ドロップダウン リストから選択**TRUE**します。</span><span class="sxs-lookup"><span data-stu-id="dd136-120">From the drop-down list, select **TRUE**.</span></span> <span data-ttu-id="dd136-121">これにより、メッセージ イベントをキャプチャし、BAM ポータルで追跡できます。</span><span class="sxs-lookup"><span data-stu-id="dd136-121">This enables the message events to be captured and tracked in the BAM portal.</span></span>|  
    |<span data-ttu-id="dd136-122">**[有効化]**</span><span class="sxs-lookup"><span data-stu-id="dd136-122">**Enable**</span></span>|<span data-ttu-id="dd136-123">False です。</span><span class="sxs-lookup"><span data-stu-id="dd136-123">False.</span></span>|  
    |<span data-ttu-id="dd136-124">**Password**</span><span class="sxs-lookup"><span data-stu-id="dd136-124">**Password**</span></span>|<span data-ttu-id="dd136-125">SAG への接続に使用するパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="dd136-125">Type the password you use to connect to SAG.</span></span> <span data-ttu-id="dd136-126">詳細については、SAG ヘルプを参照してください。</span><span class="sxs-lookup"><span data-stu-id="dd136-126">See SAG Help for more information.</span></span>|  
    |<span data-ttu-id="dd136-127">**ユーザー名**</span><span class="sxs-lookup"><span data-stu-id="dd136-127">**Username**</span></span>|<span data-ttu-id="dd136-128">SAG への接続に使用するユーザー名を入力します。</span><span class="sxs-lookup"><span data-stu-id="dd136-128">Type the user name you use to connect to SAG.</span></span>|  
  
5.  <span data-ttu-id="dd136-129">クリックして**OK**対話トランスポートのプロパティのダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="dd136-129">Click **OK** to close the INTERACT Transport Properties dialog box.</span></span>  
  
6.  <span data-ttu-id="dd136-130">クリックして**OK** INTERACT-アダプター ハンドラーのプロパティ ダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="dd136-130">Click **OK** to close the INTERACT – Adapter Handler Properties dialog box.</span></span>  
  
7.  <span data-ttu-id="dd136-131">メッセージ ボックスで、次のようにクリックします。 **OK**、し、対話のホスト インスタンスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="dd136-131">In the message box, click **OK**, and then restart the InterAct host instance.</span></span>  
  
8.  <span data-ttu-id="dd136-132">手順 1. を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="dd136-132">Repeat step 1.</span></span>  
  
9. <span data-ttu-id="dd136-133">コンソール ツリーで、BizTalk Server 管理コンソールを展開し、展開、 **BizTalk**グループで、[**プラットフォームの設定**、展開**アダプター**を開き、操作を選択 **[Biztalkserverapplication]** ] をクリックし、**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="dd136-133">In the console tree, expand BizTalk Server Administration, expand the **BizTalk** group, expand **Platform Settings**, expand **Adapter**, select INTERACT, open **BizTalkServerApplication** and then, click **Properties**.</span></span>  
  
10. <span data-ttu-id="dd136-134">**トランスポートのプロパティの対話** ダイアログ ボックスで、**プロパティ** タブで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="dd136-134">In the **INTERACT Transport Properties** dialog box, on the **Properties** tab, do the following:</span></span>  
  
    |<span data-ttu-id="dd136-135">**これを使用して、**</span><span class="sxs-lookup"><span data-stu-id="dd136-135">**Use this**</span></span>|<span data-ttu-id="dd136-136">**これを行う**</span><span class="sxs-lookup"><span data-stu-id="dd136-136">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="dd136-137">**引数**</span><span class="sxs-lookup"><span data-stu-id="dd136-137">**Arguments**</span></span>|<span data-ttu-id="dd136-138">次の引数を入力: – SagMessagePartner \<SAG で対話するクライアントのメッセージのパートナーが作成された\>**に注意してください。** 引数のクライアントは、SAG で構成した MessagePartner です。</span><span class="sxs-lookup"><span data-stu-id="dd136-138">Type the following argument: –SagMessagePartner \<Interact Client Message Partner created in SAG\> **Note:**  The client in the argument is the MessagePartner you configured in SAG.</span></span>|  
    |<span data-ttu-id="dd136-139">**暗号モード**</span><span class="sxs-lookup"><span data-stu-id="dd136-139">**Crypto Mode**</span></span>|<span data-ttu-id="dd136-140">ドロップダウン リストから選択**詳細**します。</span><span class="sxs-lookup"><span data-stu-id="dd136-140">From the drop-down list, select **Advanced**.</span></span>|  
    |<span data-ttu-id="dd136-141">**LogMessageBody**</span><span class="sxs-lookup"><span data-stu-id="dd136-141">**LogMessageBody**</span></span>|<span data-ttu-id="dd136-142">ドロップダウン リストから選択**FALSE**します。</span><span class="sxs-lookup"><span data-stu-id="dd136-142">From the drop-down list, select **FALSE**.</span></span> <span data-ttu-id="dd136-143">**注:** TRUE に設定した場合は、BizTalk 追跡データベースでメッセージの本文を保持します。</span><span class="sxs-lookup"><span data-stu-id="dd136-143">**Note:**  If you set to TRUE, it preserves the message body in the BizTalk Tracking database.</span></span> <span data-ttu-id="dd136-144">ただし、セキュリティ上の理由から、メッセージ本文は、BAM ポータルでは表示ことはありませんすることができます。</span><span class="sxs-lookup"><span data-stu-id="dd136-144">However, for security reasons, the message body can never be viewed in the BAM portal.</span></span>|  
    |<span data-ttu-id="dd136-145">**し**</span><span class="sxs-lookup"><span data-stu-id="dd136-145">**LogMessages**</span></span>|<span data-ttu-id="dd136-146">ドロップダウン リストから選択**TRUE**します。</span><span class="sxs-lookup"><span data-stu-id="dd136-146">From the drop-down list, select **TRUE**.</span></span> <span data-ttu-id="dd136-147">これにより、メッセージ イベントをキャプチャし、BAM ポータルで追跡できます。</span><span class="sxs-lookup"><span data-stu-id="dd136-147">This enables the message events to be captured and tracked in the BAM portal.</span></span>|  
    |<span data-ttu-id="dd136-148">**[有効化]**</span><span class="sxs-lookup"><span data-stu-id="dd136-148">**Enable**</span></span>|<span data-ttu-id="dd136-149">True</span><span class="sxs-lookup"><span data-stu-id="dd136-149">True</span></span>|  
    |<span data-ttu-id="dd136-150">**Password**</span><span class="sxs-lookup"><span data-stu-id="dd136-150">**Password**</span></span>|<span data-ttu-id="dd136-151">SAG への接続に使用するパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="dd136-151">Type the password you use to connect to SAG.</span></span> <span data-ttu-id="dd136-152">詳細については、SAG ヘルプを参照してください。</span><span class="sxs-lookup"><span data-stu-id="dd136-152">See SAG Help for more information.</span></span>|  
    |<span data-ttu-id="dd136-153">**ユーザー名**</span><span class="sxs-lookup"><span data-stu-id="dd136-153">**Username**</span></span>|<span data-ttu-id="dd136-154">SAG への接続に使用するユーザー名を入力します。</span><span class="sxs-lookup"><span data-stu-id="dd136-154">Type the user name you use to connect to SAG.</span></span>|  
  
11. <span data-ttu-id="dd136-155">クリックして**OK**対話トランスポートのプロパティのダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="dd136-155">Click **OK** to close the INTERACT Transport Properties dialog box.</span></span>  
  
12. <span data-ttu-id="dd136-156">選択**既定のハンドラーをこのように**オプション。</span><span class="sxs-lookup"><span data-stu-id="dd136-156">Select **make this the default handler** option.</span></span>  
  
13. <span data-ttu-id="dd136-157">クリックして**OK** INTERACT-アダプター ハンドラーのプロパティのダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="dd136-157">Click **OK** to close the INTERACT– Adapter Handler Properties dialog box.</span></span>  
  
14. <span data-ttu-id="dd136-158">メッセージ ボックスで、次のようにクリックします。 **OK**、し、再起動、 **BizTalkServerApplication**ホスト インスタンス。</span><span class="sxs-lookup"><span data-stu-id="dd136-158">In the Message box, click **OK**, and then restart the **BizTalkServerApplication** host instance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd136-159">参照</span><span class="sxs-lookup"><span data-stu-id="dd136-159">See Also</span></span>  
 <span data-ttu-id="dd136-160">[ステップ 2:送信ポートの作成し、InterAct ストア アンド フォワード (プル) シナリオ用の受信ポート](../../adapters-and-accelerators/fileact-interact/step-2-create-send-ports-and-receive-ports-for-the-interact-store-and-forward.md) </span><span class="sxs-lookup"><span data-stu-id="dd136-160">[Step2: Create Send Ports and Receive Ports for the InterAct Store and Forward (Pull) Scenario](../../adapters-and-accelerators/fileact-interact/step-2-create-send-ports-and-receive-ports-for-the-interact-store-and-forward.md) </span></span>  
 <span data-ttu-id="dd136-161">[手順 3:InterAct ストア アンド フォワード (プル) シナリオ用の動的送信ポートとオーケストレーションを作成します。](../../adapters-and-accelerators/fileact-interact/step-3-create-orchestration-with-dynamic-send-for-interact-store-and-forward.md) </span><span class="sxs-lookup"><span data-stu-id="dd136-161">[Step3: Create an orchestration with  dynamic send port for the InterAct Store and Forward (Pull) Scenario](../../adapters-and-accelerators/fileact-interact/step-3-create-orchestration-with-dynamic-send-for-interact-store-and-forward.md) </span></span>  
 [<span data-ttu-id="dd136-162">手順 4:InterAct ストア アンド フォワード (プル) エンド ツー エンドのシナリオをテストします。</span><span class="sxs-lookup"><span data-stu-id="dd136-162">Step 4: Test the InterAct Store and Forward (Pull) End-to-End Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-4-test-the-interact-store-and-forward-pull-end-to-end-scenario.md)