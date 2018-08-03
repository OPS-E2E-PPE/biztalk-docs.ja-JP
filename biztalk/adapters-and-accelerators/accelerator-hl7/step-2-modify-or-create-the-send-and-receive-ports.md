---
title: '手順 2: 変更または作成、送信と受信ポート |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8d96d02c-b75d-4d18-a127-37002c5ff138
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 42c40652d334fd2c7dec2475edca81b9fc9b1b14
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996523"
---
# <a name="step-2-modify-or-create-the-send-and-receive-ports"></a><span data-ttu-id="90756-102">手順 2: 変更または作成、送信と受信ポート</span><span class="sxs-lookup"><span data-stu-id="90756-102">Step 2: Modify or Create the Send and Receive Ports</span></span>
<span data-ttu-id="90756-103">ファイルの送信と、バッチの受信ポートが必要で/バッチ アウト チュートリアル。</span><span class="sxs-lookup"><span data-stu-id="90756-103">You need FILE send and receive ports for the Batch In/Batch Out tutorial.</span></span> <span data-ttu-id="90756-104">クリックした場合、 **Launch Tutorial**の Enterprise Edition のインストールの最後にあるボタン[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]これらのポートを作成する: Tutorial_BTAHL7Drop、という名前の送信ポートと受信ポート Tutorial_BTAHL7PickUp という名前です。</span><span class="sxs-lookup"><span data-stu-id="90756-104">If you clicked the **Launch Tutorial** button at the end of installing the Enterprise Edition of [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] created these ports for you: a send port named Tutorial_BTAHL7Drop, and a receive port named Tutorial_BTAHL7PickUp.</span></span> <span data-ttu-id="90756-105">これらのポートがあれば、引き続き Tutorial_BTAHL7Drop 送信ポートを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="90756-105">If you have these ports, you still need to modify the send port Tutorial_BTAHL7Drop.</span></span>  

 <span data-ttu-id="90756-106">場合[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]セットアップでしたいない送信を作成の受信ポート、このトピックでは、「を作成する、BIBOTutorialPickup 受信ポート」手順を参照してこのトピックでも「を作成する、BIBOTutorialDrop 送信ポート」の手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="90756-106">If [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] setup did not create the send and receive ports for you, see "To create the BIBOTutorialPickup receive port" procedure in this topic, and then see "To create the BIBOTutorialDrop send port" procedure also in this topic.</span></span>  

### <a name="to-modify-the-tutorialbtahl7drop-send-port"></a><span data-ttu-id="90756-107">Tutorial_BTAHL7Drop 送信ポートを変更するには</span><span class="sxs-lookup"><span data-stu-id="90756-107">To modify the Tutorial_BTAHL7Drop send port</span></span>  

1. <span data-ttu-id="90756-108">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]、順にクリックします**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="90756-108">Click **Start**, point to **All Programs**, point to **Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)], and then click **BizTalk Server Administration**.</span></span>  

2. <span data-ttu-id="90756-109">管理コンソールで  [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]**管理**、展開**BizTalk グループ**、展開**アプリケーション**、順に展開**BizTalk アプリケーション 1**します。</span><span class="sxs-lookup"><span data-stu-id="90756-109">In the Administration Console, expand [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]**Administration**, expand **BizTalk Group**, expand **Applications**, and then expand **BizTalk Application 1**.</span></span>  

3. <span data-ttu-id="90756-110">クリックして**送信ポート**、右クリック**Tutorial_BTAHL7Drop**、順にクリックします**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="90756-110">Click **Send Ports**, right-click **Tutorial_BTAHL7Drop**, and then click **Properties**.</span></span>  

4. <span data-ttu-id="90756-111">コンソール ツリーで、クリックして**フィルター**します。</span><span class="sxs-lookup"><span data-stu-id="90756-111">In the console tree, click **Filters**.</span></span>  

5. <span data-ttu-id="90756-112">**フィルター**ウィンドウの選択の 2 番目の行で、 **BTAHL7Schemas.MessageClass**の**プロパティ**、 **==** の**演算子**、および種類**MessageClass2X**の**値**します。</span><span class="sxs-lookup"><span data-stu-id="90756-112">In the **Filters** pane, in the second row, select **BTAHL7Schemas.MessageClass** for **Properties**, select **==** for **Operator**, and type **MessageClass2X** for **Value**.</span></span> <span data-ttu-id="90756-113">**Enter**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="90756-113">Click **Enter**.</span></span>  

6. <span data-ttu-id="90756-114">設定**Group By**上、 **BTS します。ReceivePortName**の行を**または**、 をクリックし、 **OK**。</span><span class="sxs-lookup"><span data-stu-id="90756-114">Set **Group By** on the **BTS.ReceivePortName** line to **Or**, and then click **OK**.</span></span>  

7. <span data-ttu-id="90756-115">Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理 ウィンドウで展開**プラットフォームの設定**、展開と**ホスト インスタンス**します。</span><span class="sxs-lookup"><span data-stu-id="90756-115">In the Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration window, expand **Platform Settings**, and expand **Host Instances**.</span></span> <span data-ttu-id="90756-116">右クリック**BizTalkServerApplication**、 をクリックし、**再起動**します。</span><span class="sxs-lookup"><span data-stu-id="90756-116">Right-click **BizTalkServerApplication**, and then click **Restart**.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="90756-117">Standard Edition をインストールした場合のみ、次の手順を使用して[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]、しなかった場合、または、 **Launch Tutorial**を設定するときにボタン[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="90756-117">Only use the following procedures if you installed the Standard Edition of [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)], or if you did not click the **Launch Tutorial** button when you set up [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)].</span></span>  

### <a name="to-create-the-tutorialbtahl7pickup-receive-port-and-location"></a><span data-ttu-id="90756-118">Tutorial_BTAHL7Pickup、受信ポートと場所を作成するには</span><span class="sxs-lookup"><span data-stu-id="90756-118">To create the Tutorial_BTAHL7Pickup receive port and location</span></span>  

1. <span data-ttu-id="90756-119">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]、順にクリックします**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="90756-119">Click **Start**, point to **All Programs**, point to **Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)], and then click **BizTalk Server Administration**.</span></span>  

2. <span data-ttu-id="90756-120">管理コンソールで  [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]**管理**、展開**BizTalk グループ**、展開**アプリケーション**、順に展開**BizTalk アプリケーション 1**します。</span><span class="sxs-lookup"><span data-stu-id="90756-120">In the Administration Console, expand [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]**Administration**, expand **BizTalk Group**, expand **Applications**, and then expand **BizTalk Application 1**.</span></span>  

3. <span data-ttu-id="90756-121">右クリック**受信ポート**、 をポイント**新規**、 をクリックし、**一方向の受信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="90756-121">Right-click **Receive Ports**, point to **New**, and then click **One-way Receive Port**.</span></span>  

4. <span data-ttu-id="90756-122">受信ポートのプロパティ ダイアログ ボックスでの**名前**ボックスに「 **Tutorial_BTAHL7PickUp**します。</span><span class="sxs-lookup"><span data-stu-id="90756-122">In the Receive Port Properties dialog box, in the **Name** box, type **Tutorial_BTAHL7PickUp**.</span></span>  

5. <span data-ttu-id="90756-123">をクリックして**適用**をクリックして、ポートのバインド**OK**します。</span><span class="sxs-lookup"><span data-stu-id="90756-123">Click **Apply** to bind the port, and then click **OK**.</span></span>  

6. <span data-ttu-id="90756-124">右クリック**受信場所**、 をポイント**新規**、 をクリックし、**一方向の受信場所**します。</span><span class="sxs-lookup"><span data-stu-id="90756-124">Right-click **Receive Locations**, point to **New**, and then click **One-way Receive Location**.</span></span>  

7. <span data-ttu-id="90756-125">受信ポートのダイアログ ボックスのをクリックして**Tutorial_BTAHL7PickUp**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="90756-125">In the Select a Receive Port dialog box, click **Tutorial_BTAHL7PickUp**, and then click **OK**.</span></span>  

8. <span data-ttu-id="90756-126">受信場所のプロパティ ダイアログ ボックスでの**名前**ボックスに「 **Tutorial_FileReceiveLoc**します。</span><span class="sxs-lookup"><span data-stu-id="90756-126">In the Receive Location Properties dialog box, in the **Name** box, type **Tutorial_FileReceiveLoc**.</span></span>  

9. <span data-ttu-id="90756-127">**トランスポート**セクションの**型**テキスト ボックス、ドロップダウン リストをクリックし、**ファイル**します。</span><span class="sxs-lookup"><span data-stu-id="90756-127">In the **Transport** section, for the **Type** text box, click the drop-down list, and then select **FILE**.</span></span>  

10. <span data-ttu-id="90756-128">をクリックして、**構成**型のドロップダウン リストの右側にボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="90756-128">Click the **Configure** button to the right of the Type drop-down list.</span></span>  

11. <span data-ttu-id="90756-129">ファイル トランスポートのプロパティ ダイアログ ボックスで、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="90756-129">In the FILE Transport Properties dialog box, do the following:</span></span>  


    |      <span data-ttu-id="90756-130">プロパティ</span><span class="sxs-lookup"><span data-stu-id="90756-130">Use this</span></span>      |                                                                                                                                                                         <span data-ttu-id="90756-131">目的</span><span class="sxs-lookup"><span data-stu-id="90756-131">To do this</span></span>                                                                                                                                                                          |
    |--------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    | <span data-ttu-id="90756-132">**受信フォルダー**</span><span class="sxs-lookup"><span data-stu-id="90756-132">**Receive Folder**</span></span> | <span data-ttu-id="90756-133">参照する**\<**<em>ドライブ</em>**\>: \Program Files\Microsoft BizTalk\<バージョン\>HL7\SDK\End ツー エンドのアクセラレータTutorial\Tutorial_BTAHL7PickUp**します。</span><span class="sxs-lookup"><span data-stu-id="90756-133">Browse to **\<**<em>drive</em>**\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\End-to-End Tutorial\Tutorial_BTAHL7PickUp**.</span></span> <span data-ttu-id="90756-134">**注:** 場所からファイル システムまたはパブリック共有上の場所へのパスですこの[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]は、ファイルを取得します。</span><span class="sxs-lookup"><span data-stu-id="90756-134">**Note:**  This is the path to the location on the file system or public share from where [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] will pick up the file.</span></span> |
    |   <span data-ttu-id="90756-135">**ファイル マスク**</span><span class="sxs-lookup"><span data-stu-id="90756-135">**File mask**</span></span>    |                                                                                                                                                                      <span data-ttu-id="90756-136">型 **\*.txt**します。</span><span class="sxs-lookup"><span data-stu-id="90756-136">Type **\*.txt**.</span></span>                                                                                                                                                                       |


12. <span data-ttu-id="90756-137">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="90756-137">Click **OK**.</span></span>  

13. <span data-ttu-id="90756-138">受信場所のプロパティ ダイアログ ボックスで、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="90756-138">In the Receive Location Properties dialog box, do the following:</span></span>  


    |       <span data-ttu-id="90756-139">プロパティ</span><span class="sxs-lookup"><span data-stu-id="90756-139">Use this</span></span>       |                      <span data-ttu-id="90756-140">目的</span><span class="sxs-lookup"><span data-stu-id="90756-140">To do this</span></span>                       |
    |----------------------|-------------------------------------------------------|
    | <span data-ttu-id="90756-141">**受信ハンドラー**</span><span class="sxs-lookup"><span data-stu-id="90756-141">**Receive Handler**</span></span>  |    <span data-ttu-id="90756-142">保持**BizTalkServerApplication**として選択します。</span><span class="sxs-lookup"><span data-stu-id="90756-142">Keep **BizTalkServerApplication** as selected.</span></span>     |
    | <span data-ttu-id="90756-143">**受信パイプライン**</span><span class="sxs-lookup"><span data-stu-id="90756-143">**Receive Pipeline**</span></span> | <span data-ttu-id="90756-144">選択**BTAHL72XPipelines.BTAHL72XReceivePipeline**します。</span><span class="sxs-lookup"><span data-stu-id="90756-144">Select **BTAHL72XPipelines.BTAHL72XReceivePipeline**.</span></span> |


14. <span data-ttu-id="90756-145">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="90756-145">Click **OK**.</span></span>  

15. <span data-ttu-id="90756-146">BizTalk エクスプ ローラーで右クリックして**Tutorial_FileReceiveLoc**、 をクリックし、**を有効にする**します。</span><span class="sxs-lookup"><span data-stu-id="90756-146">In BizTalk Explorer, right-click **Tutorial_FileReceiveLoc**, and then click **Enable**.</span></span>  

### <a name="to-create-the-tutorialbtahl7drop-send-port"></a><span data-ttu-id="90756-147">Tutorial_BTAHL7Drop 送信ポートを作成するには</span><span class="sxs-lookup"><span data-stu-id="90756-147">To create the Tutorial_BTAHL7Drop send port</span></span>  

1. <span data-ttu-id="90756-148">右クリックし、BizTalk Server 管理コンソールで**送信ポート**、 をポイント**新規**、 をクリックし、**静的な一方向送信ポート**。</span><span class="sxs-lookup"><span data-stu-id="90756-148">In the BizTalk Server Administration Console, right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port**.</span></span>  

2. <span data-ttu-id="90756-149">[送信ポートのプロパティ] ダイアログ ボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="90756-149">In the Send Port Properties dialog box, do the following:</span></span>  


   |   <span data-ttu-id="90756-150">プロパティ</span><span class="sxs-lookup"><span data-stu-id="90756-150">Use this</span></span>    |                                <span data-ttu-id="90756-151">目的</span><span class="sxs-lookup"><span data-stu-id="90756-151">To do this</span></span>                                 |
   |---------------|---------------------------------------------------------------------------|
   |   <span data-ttu-id="90756-152">**名前**</span><span class="sxs-lookup"><span data-stu-id="90756-152">**Name**</span></span>    |                       <span data-ttu-id="90756-153">型**Tutorial_BTAHL7Drop**します。</span><span class="sxs-lookup"><span data-stu-id="90756-153">Type **Tutorial_BTAHL7Drop**.</span></span>                       |
   |   <span data-ttu-id="90756-154">**型**</span><span class="sxs-lookup"><span data-stu-id="90756-154">**Type**</span></span>    |                 <span data-ttu-id="90756-155">選択**ファイル**ドロップダウン リストから。</span><span class="sxs-lookup"><span data-stu-id="90756-155">Select **FILE** from the drop-down list.</span></span>                  |
   | <span data-ttu-id="90756-156">**構成**</span><span class="sxs-lookup"><span data-stu-id="90756-156">**Configure**</span></span> | <span data-ttu-id="90756-157">クリックして**構成**を開く、 **FILE トランスポートのプロパティ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="90756-157">Click **Configure** to open the **FILE Transport Properties** dialog box.</span></span> |


3. <span data-ttu-id="90756-158">ファイル トランスポートのプロパティ ダイアログ ボックスで、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="90756-158">In the FILE Transport Properties dialog box, do the following:</span></span>  


   |        <span data-ttu-id="90756-159">プロパティ</span><span class="sxs-lookup"><span data-stu-id="90756-159">Use this</span></span>        |                                                                                                                                                                      <span data-ttu-id="90756-160">目的</span><span class="sxs-lookup"><span data-stu-id="90756-160">To do this</span></span>                                                                                                                                                                       |
   |------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | <span data-ttu-id="90756-161">**コピー先フォルダー**</span><span class="sxs-lookup"><span data-stu-id="90756-161">**Destination folder**</span></span> | <span data-ttu-id="90756-162">参照する**\<**<em>ドライブ</em>**:\>\Program Files\Microsoft BizTalk\<バージョン\>HL7\SDK\End ツー エンドのアクセラレータTutorial\Tutorial_BTAHL7Drop**します。</span><span class="sxs-lookup"><span data-stu-id="90756-162">Browse to **\<**<em>drive</em>**:\>\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\End-to-End Tutorial\Tutorial_BTAHL7Drop**.</span></span> <span data-ttu-id="90756-163">**注:** これは、ファイル システムまたはパブリックの共有上の場所にパス[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ファイルに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="90756-163">**Note:**  This is the path to the location on the file system or public share to which [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] will write the file.</span></span> |
   |     <span data-ttu-id="90756-164">**[ファイル名]**</span><span class="sxs-lookup"><span data-stu-id="90756-164">**File name**</span></span>      |                                                                                                                                          <span data-ttu-id="90756-165">型 **%MessageID%.txt** (拡張機能は、txt、xml ではないことに注意してください)。</span><span class="sxs-lookup"><span data-stu-id="90756-165">Type **%MessageID%.txt** (note that the extension is txt, not xml).</span></span>                                                                                                                                          |


4. <span data-ttu-id="90756-166">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="90756-166">Click **OK**.</span></span>  

5. <span data-ttu-id="90756-167">送信ポートのプロパティ ダイアログ ボックスでの**送信パイプライン**、 **BTAHL72XPipelines.BTAHL72XSendPipeline**ドロップダウン リストから。</span><span class="sxs-lookup"><span data-stu-id="90756-167">In the Send Port Properties dialog box, for **Send pipeline**, select **BTAHL72XPipelines.BTAHL72XSendPipeline** from the drop-down list.</span></span>  

6. <span data-ttu-id="90756-168">コンソール ツリーで、クリックして**フィルター**、し、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="90756-168">In the console tree, click **Filters**, and then do the following:</span></span>  


   |   <span data-ttu-id="90756-169">プロパティ</span><span class="sxs-lookup"><span data-stu-id="90756-169">Use this</span></span>   |                       <span data-ttu-id="90756-170">目的</span><span class="sxs-lookup"><span data-stu-id="90756-170">To do this</span></span>                        |
   |--------------|---------------------------------------------------------|
   | <span data-ttu-id="90756-171">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="90756-171">**Property**</span></span> | <span data-ttu-id="90756-172">選択**BTS します。ReceivePortName**ドロップダウン リストから。</span><span class="sxs-lookup"><span data-stu-id="90756-172">Select **BTS.ReceivePortName** from the drop-down list.</span></span> |
   | <span data-ttu-id="90756-173">**[演算子]**</span><span class="sxs-lookup"><span data-stu-id="90756-173">**Operator**</span></span> |              <span data-ttu-id="90756-174">まま**==** 演算子として。</span><span class="sxs-lookup"><span data-stu-id="90756-174">Leave **==** as the operator.</span></span>              |
   |  <span data-ttu-id="90756-175">**[値]**</span><span class="sxs-lookup"><span data-stu-id="90756-175">**Value**</span></span>   |             <span data-ttu-id="90756-176">型**Tutorial_BTAHL7PickUp**します。</span><span class="sxs-lookup"><span data-stu-id="90756-176">Type **Tutorial_BTAHL7PickUp**.</span></span>             |
   | <span data-ttu-id="90756-177">**グループ化**</span><span class="sxs-lookup"><span data-stu-id="90756-177">**Group By**</span></span> |         <span data-ttu-id="90756-178">選択**または**ドロップダウン リストから。</span><span class="sxs-lookup"><span data-stu-id="90756-178">Select **Or** from the drop-down list.</span></span>          |
   | <span data-ttu-id="90756-179">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="90756-179">**Property**</span></span> |         <span data-ttu-id="90756-180">選択**BTAHL7Schemas.MessageClass**します。</span><span class="sxs-lookup"><span data-stu-id="90756-180">Select **BTAHL7Schemas.MessageClass**.</span></span>          |
   | <span data-ttu-id="90756-181">**[演算子]**</span><span class="sxs-lookup"><span data-stu-id="90756-181">**Operator**</span></span> |              <span data-ttu-id="90756-182">まま**==** 演算子として。</span><span class="sxs-lookup"><span data-stu-id="90756-182">Leave **==** as the operator.</span></span>              |
   |  <span data-ttu-id="90756-183">**[値]**</span><span class="sxs-lookup"><span data-stu-id="90756-183">**Value**</span></span>   |                <span data-ttu-id="90756-184">型**MessageClass2X**します。</span><span class="sxs-lookup"><span data-stu-id="90756-184">Type **MessageClass2X**.</span></span>                 |


7. <span data-ttu-id="90756-185">**Enter**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="90756-185">Click **Enter**.</span></span> <span data-ttu-id="90756-186">ダイアログ ボックスの下部にあるウィンドウで、フィルター式が正しいことを確認します。</span><span class="sxs-lookup"><span data-stu-id="90756-186">Verify in the pane at the bottom of the dialog box that the filter expression is correct.</span></span>  

8. <span data-ttu-id="90756-187">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="90756-187">Click **OK**.</span></span>  

9. <span data-ttu-id="90756-188">管理コンソールで、**送信ポート**を右クリックして**Tutorial_BTAHL7Drop**、順にクリックします**開始**します。</span><span class="sxs-lookup"><span data-stu-id="90756-188">In the Administration Console, click **Send Ports**, right-click **Tutorial_BTAHL7Drop**, and then click **Start**.</span></span>  

10. <span data-ttu-id="90756-189">展開**プラットフォームの設定**、 をクリックし、**ホスト インスタンス**します。</span><span class="sxs-lookup"><span data-stu-id="90756-189">Expand **Platform Settings**, and then click **Host Instances**.</span></span> <span data-ttu-id="90756-190">右クリック**BizTalkServerApplication**、 をクリックし、**再起動**します。</span><span class="sxs-lookup"><span data-stu-id="90756-190">Right-click **BizTalkServerApplication**, and then click **Restart**.</span></span>  

    <span data-ttu-id="90756-191">続行する[手順 3: テストのバッチ処理/バッチ アウト シナリオ](../../adapters-and-accelerators/accelerator-hl7/step-3-test-the-batch-in-batch-out-scenario.md)します。</span><span class="sxs-lookup"><span data-stu-id="90756-191">Proceed to [Step 3: Test the Batch In/Batch Out Scenario](../../adapters-and-accelerators/accelerator-hl7/step-3-test-the-batch-in-batch-out-scenario.md).</span></span>