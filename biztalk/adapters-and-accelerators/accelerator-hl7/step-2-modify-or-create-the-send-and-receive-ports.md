---
title: "手順 2: 変更または作成、送信および受信ポート |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8d96d02c-b75d-4d18-a127-37002c5ff138
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 61f201f8b20d5824b1b037cc61edaa1d64729135
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-2-modify-or-create-the-send-and-receive-ports"></a><span data-ttu-id="48db0-102">手順 2: 変更または作成、送信および受信ポート</span><span class="sxs-lookup"><span data-stu-id="48db0-102">Step 2: Modify or Create the Send and Receive Ports</span></span>
<span data-ttu-id="48db0-103">ファイルの送信ポートと受信ポートをバッチにする必要がありますでチュートリアルをバッチ処理/です。</span><span class="sxs-lookup"><span data-stu-id="48db0-103">You need FILE send and receive ports for the Batch In/Batch Out tutorial.</span></span> <span data-ttu-id="48db0-104">クリックした場合、 **Launch Tutorial**の Enterprise Edition のインストールの最後にあるボタン[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]これらのポートが自動的に作成: Tutorial_BTAHL7Drop をという名前の送信ポートと受信ポートを Tutorial_BTAHL7PickUp をという名前です。</span><span class="sxs-lookup"><span data-stu-id="48db0-104">If you clicked the **Launch Tutorial** button at the end of installing the Enterprise Edition of [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] created these ports for you: a send port named Tutorial_BTAHL7Drop, and a receive port named Tutorial_BTAHL7PickUp.</span></span> <span data-ttu-id="48db0-105">これらのポートがあれば、Tutorial_BTAHL7Drop の送信ポートを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="48db0-105">If you have these ports, you still need to modify the send port Tutorial_BTAHL7Drop.</span></span>  
  
 <span data-ttu-id="48db0-106">場合[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]セットアップしなかったいない作成、送信および受信ポート、このトピックでは「を作成する、BIBOTutorialPickup 受信ポート」の手順を参照しておよびし、このトピックでも「を作成する、BIBOTutorialDrop 送信ポート」の手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="48db0-106">If [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] setup did not create the send and receive ports for you, see "To create the BIBOTutorialPickup receive port" procedure in this topic, and then see "To create the BIBOTutorialDrop send port" procedure also in this topic.</span></span>  
  
### <a name="to-modify-the-tutorialbtahl7drop-send-port"></a><span data-ttu-id="48db0-107">Tutorial_BTAHL7Drop 送信ポートを変更するには</span><span class="sxs-lookup"><span data-stu-id="48db0-107">To modify the Tutorial_BTAHL7Drop send port</span></span>  
  
1.  <span data-ttu-id="48db0-108">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="48db0-108">Click **Start**, point to **All Programs**, point to **Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="48db0-109">管理コンソールで  [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]**管理**、展開**BizTalk グループ**、展開**アプリケーション**、順に展開**BizTalk アプリケーション 1**です。</span><span class="sxs-lookup"><span data-stu-id="48db0-109">In the Administration Console, expand [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]**Administration**, expand **BizTalk Group**, expand **Applications**, and then expand **BizTalk Application 1**.</span></span>  
  
3.  <span data-ttu-id="48db0-110">をクリックして**送信ポート**を右クリックして**Tutorial_BTAHL7Drop**、クリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="48db0-110">Click **Send Ports**, right-click **Tutorial_BTAHL7Drop**, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="48db0-111">コンソール ツリーでクリックして**フィルター**です。</span><span class="sxs-lookup"><span data-stu-id="48db0-111">In the console tree, click **Filters**.</span></span>  
  
5.  <span data-ttu-id="48db0-112">**フィルター**ウィンドウの選択] の 2 番目の行で、 **BTAHL7Schemas.MessageClass**の**プロパティ**[  **==** の**演算子**、および種類**MessageClass2X**の**値**です。</span><span class="sxs-lookup"><span data-stu-id="48db0-112">In the **Filters** pane, in the second row, select **BTAHL7Schemas.MessageClass** for **Properties**, select **==** for **Operator**, and type **MessageClass2X** for **Value**.</span></span> <span data-ttu-id="48db0-113">**Enter**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="48db0-113">Click **Enter**.</span></span>  
  
6.  <span data-ttu-id="48db0-114">設定**Group By**上、 **BTS です。ReceivePortName**の行を**または**、順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="48db0-114">Set **Group By** on the **BTS.ReceivePortName** line to **Or**, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="48db0-115">[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理 ウィンドウで展開**プラットフォームの設定**、展開と**ホスト インスタンス**です。</span><span class="sxs-lookup"><span data-stu-id="48db0-115">In the [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration window, expand **Platform Settings**, and expand **Host Instances**.</span></span> <span data-ttu-id="48db0-116">右クリック**BizTalkServerApplication**、クリックして**再起動**です。</span><span class="sxs-lookup"><span data-stu-id="48db0-116">Right-click **BizTalkServerApplication**, and then click **Restart**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="48db0-117">Standard Edition をインストールした場合のみ、次の手順を使用して[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]、しなかった場合、または、 **Launch Tutorial**を設定するときにボタン[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="48db0-117">Only use the following procedures if you installed the Standard Edition of [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)], or if you did not click the **Launch Tutorial** button when you set up [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)].</span></span>  
  
### <a name="to-create-the-tutorialbtahl7pickup-receive-port-and-location"></a><span data-ttu-id="48db0-118">Tutorial_BTAHL7Pickup 受信ポートと受信場所を作成するには</span><span class="sxs-lookup"><span data-stu-id="48db0-118">To create the Tutorial_BTAHL7Pickup receive port and location</span></span>  
  
1.  <span data-ttu-id="48db0-119">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="48db0-119">Click **Start**, point to **All Programs**, point to **Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="48db0-120">管理コンソールで  [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]**管理**、展開**BizTalk グループ**、展開**アプリケーション**、順に展開**BizTalk アプリケーション 1**です。</span><span class="sxs-lookup"><span data-stu-id="48db0-120">In the Administration Console, expand [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]**Administration**, expand **BizTalk Group**, expand **Applications**, and then expand **BizTalk Application 1**.</span></span>  
  
3.  <span data-ttu-id="48db0-121">右クリック**受信ポート**、 をポイント**新規**、クリックして**一方向の受信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="48db0-121">Right-click **Receive Ports**, point to **New**, and then click **One-way Receive Port**.</span></span>  
  
4.  <span data-ttu-id="48db0-122">受信ポートのプロパティ ダイアログ ボックスで、**名前**ボックスに、入力**Tutorial_BTAHL7PickUp**です。</span><span class="sxs-lookup"><span data-stu-id="48db0-122">In the Receive Port Properties dialog box, in the **Name** box, type **Tutorial_BTAHL7PickUp**.</span></span>  
  
5.  <span data-ttu-id="48db0-123">をクリックして**適用**をクリックして、ポートのバインド**OK**です。</span><span class="sxs-lookup"><span data-stu-id="48db0-123">Click **Apply** to bind the port, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="48db0-124">右クリック**受信場所**、 をポイント**新規**、クリックして**一方向の受信場所**です。</span><span class="sxs-lookup"><span data-stu-id="48db0-124">Right-click **Receive Locations**, point to **New**, and then click **One-way Receive Location**.</span></span>  
  
7.  <span data-ttu-id="48db0-125">[受信ポート] ダイアログ ボックスのをクリックして**Tutorial_BTAHL7PickUp**、クリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="48db0-125">In the Select a Receive Port dialog box, click **Tutorial_BTAHL7PickUp**, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="48db0-126">受信場所のプロパティ ダイアログ ボックスで、**名前**ボックスに、入力**Tutorial_FileReceiveLoc**です。</span><span class="sxs-lookup"><span data-stu-id="48db0-126">In the Receive Location Properties dialog box, in the **Name** box, type **Tutorial_FileReceiveLoc**.</span></span>  
  
9. <span data-ttu-id="48db0-127">**トランスポート**] セクションの**型**テキスト ボックスがドロップダウン リストをクリックし、[**ファイル**です。</span><span class="sxs-lookup"><span data-stu-id="48db0-127">In the **Transport** section, for the **Type** text box, click the drop-down list, and then select **FILE**.</span></span>  
  
10. <span data-ttu-id="48db0-128">クリックして、**構成**型のドロップダウン リストの右側にあるボタンです。</span><span class="sxs-lookup"><span data-stu-id="48db0-128">Click the **Configure** button to the right of the Type drop-down list.</span></span>  
  
11. <span data-ttu-id="48db0-129">ファイル トランスポートのプロパティ ダイアログ ボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="48db0-129">In the FILE Transport Properties dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="48db0-130">プロパティ</span><span class="sxs-lookup"><span data-stu-id="48db0-130">Use this</span></span>|<span data-ttu-id="48db0-131">目的</span><span class="sxs-lookup"><span data-stu-id="48db0-131">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="48db0-132">**受信フォルダー**</span><span class="sxs-lookup"><span data-stu-id="48db0-132">**Receive Folder**</span></span>|<span data-ttu-id="48db0-133">参照 **\<** *ドライブ***>: \Program Files\Microsoft BizTalk\<バージョン > Accelerator for HL7\SDK\End エンドツー エンド Tutorial\Tutorial_BTAHL7PickUp**.</span><span class="sxs-lookup"><span data-stu-id="48db0-133">Browse to **\<***drive***>:\Program Files\Microsoft BizTalk \<version> Accelerator for HL7\SDK\End-to-End Tutorial\Tutorial_BTAHL7PickUp**.</span></span> <span data-ttu-id="48db0-134">**注:**これは、パス、ファイル システムまたはパブリック共有上の場所にどこから[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]は、ファイルを取得します。</span><span class="sxs-lookup"><span data-stu-id="48db0-134">**Note:**  This is the path to the location on the file system or public share from where [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] will pick up the file.</span></span>|  
    |<span data-ttu-id="48db0-135">**ファイル マスク**</span><span class="sxs-lookup"><span data-stu-id="48db0-135">**File mask**</span></span>|<span data-ttu-id="48db0-136">型 **\*.txt**です。</span><span class="sxs-lookup"><span data-stu-id="48db0-136">Type **\*.txt**.</span></span>|  
  
12. <span data-ttu-id="48db0-137">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="48db0-137">Click **OK**.</span></span>  
  
13. <span data-ttu-id="48db0-138">受信場所のプロパティ ダイアログ ボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="48db0-138">In the Receive Location Properties dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="48db0-139">プロパティ</span><span class="sxs-lookup"><span data-stu-id="48db0-139">Use this</span></span>|<span data-ttu-id="48db0-140">目的</span><span class="sxs-lookup"><span data-stu-id="48db0-140">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="48db0-141">**受信ハンドラー**</span><span class="sxs-lookup"><span data-stu-id="48db0-141">**Receive Handler**</span></span>|<span data-ttu-id="48db0-142">保持**BizTalkServerApplication**として選択します。</span><span class="sxs-lookup"><span data-stu-id="48db0-142">Keep **BizTalkServerApplication** as selected.</span></span>|  
    |<span data-ttu-id="48db0-143">**受信パイプライン**</span><span class="sxs-lookup"><span data-stu-id="48db0-143">**Receive Pipeline**</span></span>|<span data-ttu-id="48db0-144">選択**BTAHL72XPipelines.BTAHL72XReceivePipeline**です。</span><span class="sxs-lookup"><span data-stu-id="48db0-144">Select **BTAHL72XPipelines.BTAHL72XReceivePipeline**.</span></span>|  
  
14. <span data-ttu-id="48db0-145">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="48db0-145">Click **OK**.</span></span>  
  
15. <span data-ttu-id="48db0-146">BizTalk エクスプ ローラーで右クリック**Tutorial_FileReceiveLoc**、クリックして**を有効にする**です。</span><span class="sxs-lookup"><span data-stu-id="48db0-146">In BizTalk Explorer, right-click **Tutorial_FileReceiveLoc**, and then click **Enable**.</span></span>  
  
### <a name="to-create-the-tutorialbtahl7drop-send-port"></a><span data-ttu-id="48db0-147">Tutorial_BTAHL7Drop 送信ポートを作成するには</span><span class="sxs-lookup"><span data-stu-id="48db0-147">To create the Tutorial_BTAHL7Drop send port</span></span>  
  
1.  <span data-ttu-id="48db0-148">[!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)]管理コンソールを右クリックして**送信ポート**、 をポイント**新規**、クリックして**静的な一方向送信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="48db0-148">In the [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] Administration Console, right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port**.</span></span>  
  
2.  <span data-ttu-id="48db0-149">[送信ポートのプロパティ] ダイアログ ボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="48db0-149">In the Send Port Properties dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="48db0-150">プロパティ</span><span class="sxs-lookup"><span data-stu-id="48db0-150">Use this</span></span>|<span data-ttu-id="48db0-151">目的</span><span class="sxs-lookup"><span data-stu-id="48db0-151">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="48db0-152">**名前**</span><span class="sxs-lookup"><span data-stu-id="48db0-152">**Name**</span></span>|<span data-ttu-id="48db0-153">型**Tutorial_BTAHL7Drop**です。</span><span class="sxs-lookup"><span data-stu-id="48db0-153">Type **Tutorial_BTAHL7Drop**.</span></span>|  
    |<span data-ttu-id="48db0-154">**型**</span><span class="sxs-lookup"><span data-stu-id="48db0-154">**Type**</span></span>|<span data-ttu-id="48db0-155">選択**ファイル**ドロップダウン リストからです。</span><span class="sxs-lookup"><span data-stu-id="48db0-155">Select **FILE** from the drop-down list.</span></span>|  
    |<span data-ttu-id="48db0-156">**構成**</span><span class="sxs-lookup"><span data-stu-id="48db0-156">**Configure**</span></span>|<span data-ttu-id="48db0-157">をクリックして**構成**を開くには、 **FILE トランスポートのプロパティ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="48db0-157">Click **Configure** to open the **FILE Transport Properties** dialog box.</span></span>|  
  
3.  <span data-ttu-id="48db0-158">ファイル トランスポートのプロパティ ダイアログ ボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="48db0-158">In the FILE Transport Properties dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="48db0-159">プロパティ</span><span class="sxs-lookup"><span data-stu-id="48db0-159">Use this</span></span>|<span data-ttu-id="48db0-160">目的</span><span class="sxs-lookup"><span data-stu-id="48db0-160">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="48db0-161">**コピー先フォルダー**</span><span class="sxs-lookup"><span data-stu-id="48db0-161">**Destination folder**</span></span>|<span data-ttu-id="48db0-162">参照 **\<** *ドライブ***: > \Program Files\Microsoft BizTalk\<バージョン > Accelerator for HL7\SDK\End エンドツー エンド Tutorial\Tutorial_BTAHL7Drop**.</span><span class="sxs-lookup"><span data-stu-id="48db0-162">Browse to **\<***drive***:>\Program Files\Microsoft BizTalk \<version> Accelerator for HL7\SDK\End-to-End Tutorial\Tutorial_BTAHL7Drop**.</span></span> <span data-ttu-id="48db0-163">**注:**これは、ファイル システムまたはパブリックの共有の場所にパス[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ファイルを記述します。</span><span class="sxs-lookup"><span data-stu-id="48db0-163">**Note:**  This is the path to the location on the file system or public share to which [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] will write the file.</span></span>|  
    |<span data-ttu-id="48db0-164">**ファイル名**</span><span class="sxs-lookup"><span data-stu-id="48db0-164">**File name**</span></span>|<span data-ttu-id="48db0-165">型**%MessageID%.txt** (拡張機能は、txt、xml ではないことに注意してください)。</span><span class="sxs-lookup"><span data-stu-id="48db0-165">Type **%MessageID%.txt** (note that the extension is txt, not xml).</span></span>|  
  
4.  <span data-ttu-id="48db0-166">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="48db0-166">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="48db0-167">送信ポートのプロパティ] ダイアログ ボックスの**送信パイプライン**[ **BTAHL72XPipelines.BTAHL72XSendPipeline**ドロップダウン リストからです。</span><span class="sxs-lookup"><span data-stu-id="48db0-167">In the Send Port Properties dialog box, for **Send pipeline**, select **BTAHL72XPipelines.BTAHL72XSendPipeline** from the drop-down list.</span></span>  
  
6.  <span data-ttu-id="48db0-168">コンソール ツリーでクリックして**フィルター**、し、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="48db0-168">In the console tree, click **Filters**, and then do the following:</span></span>  
  
    |<span data-ttu-id="48db0-169">プロパティ</span><span class="sxs-lookup"><span data-stu-id="48db0-169">Use this</span></span>|<span data-ttu-id="48db0-170">目的</span><span class="sxs-lookup"><span data-stu-id="48db0-170">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="48db0-171">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="48db0-171">**Property**</span></span>|<span data-ttu-id="48db0-172">選択**BTS です。ReceivePortName**ドロップダウン リストからです。</span><span class="sxs-lookup"><span data-stu-id="48db0-172">Select **BTS.ReceivePortName** from the drop-down list.</span></span>|  
    |<span data-ttu-id="48db0-173">**演算子**</span><span class="sxs-lookup"><span data-stu-id="48db0-173">**Operator**</span></span>|<span data-ttu-id="48db0-174">ままにして **==** 演算子とします。</span><span class="sxs-lookup"><span data-stu-id="48db0-174">Leave **==** as the operator.</span></span>|  
    |<span data-ttu-id="48db0-175">**値**</span><span class="sxs-lookup"><span data-stu-id="48db0-175">**Value**</span></span>|<span data-ttu-id="48db0-176">型**Tutorial_BTAHL7PickUp**です。</span><span class="sxs-lookup"><span data-stu-id="48db0-176">Type **Tutorial_BTAHL7PickUp**.</span></span>|  
    |<span data-ttu-id="48db0-177">**グループ化**</span><span class="sxs-lookup"><span data-stu-id="48db0-177">**Group By**</span></span>|<span data-ttu-id="48db0-178">選択**または**ドロップダウン リストからです。</span><span class="sxs-lookup"><span data-stu-id="48db0-178">Select **Or** from the drop-down list.</span></span>|  
    |<span data-ttu-id="48db0-179">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="48db0-179">**Property**</span></span>|<span data-ttu-id="48db0-180">選択**BTAHL7Schemas.MessageClass**です。</span><span class="sxs-lookup"><span data-stu-id="48db0-180">Select **BTAHL7Schemas.MessageClass**.</span></span>|  
    |<span data-ttu-id="48db0-181">**演算子**</span><span class="sxs-lookup"><span data-stu-id="48db0-181">**Operator**</span></span>|<span data-ttu-id="48db0-182">ままにして **==** 演算子とします。</span><span class="sxs-lookup"><span data-stu-id="48db0-182">Leave **==** as the operator.</span></span>|  
    |<span data-ttu-id="48db0-183">**値**</span><span class="sxs-lookup"><span data-stu-id="48db0-183">**Value**</span></span>|<span data-ttu-id="48db0-184">型**MessageClass2X**です。</span><span class="sxs-lookup"><span data-stu-id="48db0-184">Type **MessageClass2X**.</span></span>|  
  
7.  <span data-ttu-id="48db0-185">**Enter**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="48db0-185">Click **Enter**.</span></span> <span data-ttu-id="48db0-186">ダイアログ ボックスの下部にあるペインでフィルター式が正しいことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="48db0-186">Verify in the pane at the bottom of the dialog box that the filter expression is correct.</span></span>  
  
8.  <span data-ttu-id="48db0-187">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="48db0-187">Click **OK**.</span></span>  
  
9. <span data-ttu-id="48db0-188">管理コンソールで、をクリックして**送信ポート**を右クリックして**Tutorial_BTAHL7Drop**、クリックして**開始**です。</span><span class="sxs-lookup"><span data-stu-id="48db0-188">In the Administration Console, click **Send Ports**, right-click **Tutorial_BTAHL7Drop**, and then click **Start**.</span></span>  
  
10. <span data-ttu-id="48db0-189">展開**プラットフォームの設定**、クリックして**ホスト インスタンス**です。</span><span class="sxs-lookup"><span data-stu-id="48db0-189">Expand **Platform Settings**, and then click **Host Instances**.</span></span> <span data-ttu-id="48db0-190">右クリック**BizTalkServerApplication**、クリックして**再起動**です。</span><span class="sxs-lookup"><span data-stu-id="48db0-190">Right-click **BizTalkServerApplication**, and then click **Restart**.</span></span>  
  
 <span data-ttu-id="48db0-191">進みます[手順 3: バッチ処理をテスト/シナリオをバッチ](../../adapters-and-accelerators/accelerator-hl7/step-3-test-the-batch-in-batch-out-scenario.md)です。</span><span class="sxs-lookup"><span data-stu-id="48db0-191">Proceed to [Step 3: Test the Batch In/Batch Out Scenario](../../adapters-and-accelerators/accelerator-hl7/step-3-test-the-batch-in-batch-out-scenario.md).</span></span>