---
title: 手順 6:受信確認のバッチの送信ポートの作成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f2a0f1ee-e060-4fb9-923e-ebe8168777d9
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 960e05afa424adf4d23980618170f82987a192ab
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65287954"
---
# <a name="step-6-create-the-send-port-for-the-acknowledgment-batch"></a><span data-ttu-id="1f0c0-102">手順 6:受信確認のバッチの送信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="1f0c0-102">Step 6: Create the Send Port for the Acknowledgment Batch</span></span>
<span data-ttu-id="1f0c0-103">この手順では、送信元パーティを作成する受信確認のバッチを配信する送信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="1f0c0-103">In this step, you create a send port to deliver the acknowledgment batch that you create to the source party.</span></span> <span data-ttu-id="1f0c0-104">これは、ファイル アダプターの種類を静的な一方向のポートです。</span><span class="sxs-lookup"><span data-stu-id="1f0c0-104">This is a static one-way port with a FILE adapter type.</span></span> <span data-ttu-id="1f0c0-105">場所のソース (\Tutorial_BatchACKDrop) ファイルのフォルダーを指定する[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]受信確認のバッチ ファイルが削除されます。</span><span class="sxs-lookup"><span data-stu-id="1f0c0-105">You designate a file folder for the source (\Tutorial_BatchACKDrop), where [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] will drop the acknowledgment batch file.</span></span> <span data-ttu-id="1f0c0-106">ポートで送信する受信確認のバッチの種類を示すポートのフィルターを定義します。</span><span class="sxs-lookup"><span data-stu-id="1f0c0-106">You define a filter for the port indicating what type of acknowledgment batches the ports will send.</span></span> <span data-ttu-id="1f0c0-107">フィルターには、Tutorial_BatchSource と OutboundBatch のメッセージの種類のソースを指定します。</span><span class="sxs-lookup"><span data-stu-id="1f0c0-107">The filter specifies the source of Tutorial_BatchSource and the message type of OutboundBatch.</span></span>  

### <a name="to-create-the-send-port-for-the-acknowledgment-batch"></a><span data-ttu-id="1f0c0-108">受信確認のバッチの送信ポートを作成するには</span><span class="sxs-lookup"><span data-stu-id="1f0c0-108">To create the send port for the acknowledgment batch</span></span>  

1. <span data-ttu-id="1f0c0-109">右クリックし、BizTalk Server 管理コンソールで**送信ポート**、 をポイント**新規**、 をクリックし、**静的な一方向送信ポート**。</span><span class="sxs-lookup"><span data-stu-id="1f0c0-109">In the BizTalk Server Administration Console, right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port**.</span></span>  

2. <span data-ttu-id="1f0c0-110">[送信ポートのプロパティ] ダイアログ ボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="1f0c0-110">In the Send Port Properties dialog box, do the following:</span></span>  


   |   <span data-ttu-id="1f0c0-111">プロパティ</span><span class="sxs-lookup"><span data-stu-id="1f0c0-111">Use this</span></span>    |                              <span data-ttu-id="1f0c0-112">目的</span><span class="sxs-lookup"><span data-stu-id="1f0c0-112">To do this</span></span>                               |
   |---------------|-----------------------------------------------------------------------|
   |   <span data-ttu-id="1f0c0-113">**名前**</span><span class="sxs-lookup"><span data-stu-id="1f0c0-113">**Name**</span></span>    |                    <span data-ttu-id="1f0c0-114">型**Tutorial_BatchSource**します。</span><span class="sxs-lookup"><span data-stu-id="1f0c0-114">Type **Tutorial_BatchSource**.</span></span>                     |
   |   <span data-ttu-id="1f0c0-115">**型**</span><span class="sxs-lookup"><span data-stu-id="1f0c0-115">**Type**</span></span>    |               <span data-ttu-id="1f0c0-116">選択**ファイル**ドロップダウン リストから。</span><span class="sxs-lookup"><span data-stu-id="1f0c0-116">Select **FILE** from the drop-down list.</span></span>                |
   | <span data-ttu-id="1f0c0-117">**構成**</span><span class="sxs-lookup"><span data-stu-id="1f0c0-117">**Configure**</span></span> | <span data-ttu-id="1f0c0-118">クリックして**構成**FILE トランスポートのプロパティ ダイアログ ボックスを開きます。</span><span class="sxs-lookup"><span data-stu-id="1f0c0-118">Click **Configure** to open the FILE Transport Properties dialog box.</span></span> |


3. <span data-ttu-id="1f0c0-119">ファイル トランスポートのプロパティ ダイアログ ボックスで、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="1f0c0-119">In the FILE Transport Properties dialog box, do the following:</span></span>  


   |        <span data-ttu-id="1f0c0-120">プロパティ</span><span class="sxs-lookup"><span data-stu-id="1f0c0-120">Use this</span></span>        |                                                                                                                                                                              <span data-ttu-id="1f0c0-121">目的</span><span class="sxs-lookup"><span data-stu-id="1f0c0-121">To do this</span></span>                                                                                                                                                                               |
   |------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | <span data-ttu-id="1f0c0-122">**コピー先フォルダー**</span><span class="sxs-lookup"><span data-stu-id="1f0c0-122">**Destination folder**</span></span> | <span data-ttu-id="1f0c0-123">参照する **\<*ドライブ*:\>\Program Files\Microsoft BizTalk\<バージョン\>HL7\SDK\End ツー エンド Tutorial\Tutorial_BatchACKDropのアクセラレータ**.</span><span class="sxs-lookup"><span data-stu-id="1f0c0-123">Browse to **\<*drive*:\>\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\End-to-End Tutorial\Tutorial_BatchACKDrop**.</span></span> <span data-ttu-id="1f0c0-124">これは、ファイル システムまたはパブリックの共有上の場所にパス[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]受信確認のバッチを含んでいるファイルに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="1f0c0-124">This is the path to the location on the file system or public share to which [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] will write the file containing the acknowledgment batch.</span></span> |
   |     <span data-ttu-id="1f0c0-125">**[ファイル名]**</span><span class="sxs-lookup"><span data-stu-id="1f0c0-125">**File name**</span></span>      |                                                                                                                                            <span data-ttu-id="1f0c0-126">型 **%MessageID%.txt** (.txt 拡張子 .xml 拡張子を置き換えます)。</span><span class="sxs-lookup"><span data-stu-id="1f0c0-126">Type **%MessageID%.txt** (replace the .xml extension with the .txt extension).</span></span>                                                                                                                                             |
   |     <span data-ttu-id="1f0c0-127">**コピー モード**</span><span class="sxs-lookup"><span data-stu-id="1f0c0-127">**Copy mode**</span></span>      |                                                                                                                                                                        <span data-ttu-id="1f0c0-128">選択**新規作成**です。</span><span class="sxs-lookup"><span data-stu-id="1f0c0-128">Select **Create New**.</span></span>                                                                                                                                                                         |


4. <span data-ttu-id="1f0c0-129">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1f0c0-129">Click **OK**.</span></span>  

5. <span data-ttu-id="1f0c0-130">送信ポートのプロパティ ダイアログ ボックスでの**送信パイプライン**、 **BTAHL72XPipelines.BTAHL72XSendPipeline**します。</span><span class="sxs-lookup"><span data-stu-id="1f0c0-130">In the Send Port Properties dialog box, for **Send pipeline**, select **BTAHL72XPipelines.BTAHL72XSendPipeline**.</span></span>  

6. <span data-ttu-id="1f0c0-131">コンソール ツリーで、クリックして**フィルター**、し、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="1f0c0-131">In the console tree, click **Filters**, and then do the following:</span></span>  


   |   <span data-ttu-id="1f0c0-132">プロパティ</span><span class="sxs-lookup"><span data-stu-id="1f0c0-132">Use this</span></span>   |                                                              <span data-ttu-id="1f0c0-133">目的</span><span class="sxs-lookup"><span data-stu-id="1f0c0-133">To do this</span></span>                                                              |
   |--------------|--------------------------------------------------------------------------------------------------------------------------------------|
   | <span data-ttu-id="1f0c0-134">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="1f0c0-134">**Property**</span></span> | <span data-ttu-id="1f0c0-135">下のフィールドをクリックします。**プロパティ**、し、 **Microsoft.Solutions.BTAHL7.BatchOrchestration.Party**ドロップダウン リストから。</span><span class="sxs-lookup"><span data-stu-id="1f0c0-135">Click the field under **Property**, and then select **Microsoft.Solutions.BTAHL7.BatchOrchestration.Party** from the drop-down list.</span></span> |
   | <span data-ttu-id="1f0c0-136">**[演算子]**</span><span class="sxs-lookup"><span data-stu-id="1f0c0-136">**Operator**</span></span> |                                                    <span data-ttu-id="1f0c0-137">まま**==** 演算子として。</span><span class="sxs-lookup"><span data-stu-id="1f0c0-137">Leave **==** as the operator.</span></span>                                                     |
   |  <span data-ttu-id="1f0c0-138">**[値]**</span><span class="sxs-lookup"><span data-stu-id="1f0c0-138">**Value**</span></span>   |                                                    <span data-ttu-id="1f0c0-139">型**Tutorial_BatchSource**します。</span><span class="sxs-lookup"><span data-stu-id="1f0c0-139">Type **Tutorial_BatchSource**.</span></span>                                                    |
   | <span data-ttu-id="1f0c0-140">**グループ化**</span><span class="sxs-lookup"><span data-stu-id="1f0c0-140">**Group By**</span></span> |                                               <span data-ttu-id="1f0c0-141">選択**と**ドロップダウン リストから。</span><span class="sxs-lookup"><span data-stu-id="1f0c0-141">Select **And** from the drop-down list.</span></span>                                                |
   | <span data-ttu-id="1f0c0-142">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="1f0c0-142">**Property**</span></span> |                                             <span data-ttu-id="1f0c0-143">選択**BTAHL7Schemas.BTAHL7MessageType**します。</span><span class="sxs-lookup"><span data-stu-id="1f0c0-143">Select **BTAHL7Schemas.BTAHL7MessageType**.</span></span>                                              |
   | <span data-ttu-id="1f0c0-144">**[演算子]**</span><span class="sxs-lookup"><span data-stu-id="1f0c0-144">**Operator**</span></span> |                                                    <span data-ttu-id="1f0c0-145">まま**==** 演算子として。</span><span class="sxs-lookup"><span data-stu-id="1f0c0-145">Leave **==** as the operator.</span></span>                                                     |
   |  <span data-ttu-id="1f0c0-146">**[値]**</span><span class="sxs-lookup"><span data-stu-id="1f0c0-146">**Value**</span></span>   |                                                       <span data-ttu-id="1f0c0-147">型**OutboundBatch**します。</span><span class="sxs-lookup"><span data-stu-id="1f0c0-147">Type **OutboundBatch**.</span></span>                                                        |


7. <span data-ttu-id="1f0c0-148">**Enter**キーを押します。</span><span class="sxs-lookup"><span data-stu-id="1f0c0-148">Press **Enter**.</span></span> <span data-ttu-id="1f0c0-149">クリックしてダイアログ ボックスの下部にあるウィンドウで、フィルター式の入力が正しいことを確認します**OK**します。</span><span class="sxs-lookup"><span data-stu-id="1f0c0-149">In the pane at the bottom of the dialog box, verify that you entered the filter expression correctly, and then click **OK**.</span></span>  

8. <span data-ttu-id="1f0c0-150">BizTalk 管理コンソールで、次のように選択します。**送信ポート**、を右クリック**Tutorial_BatchSource**、 をクリックし、**開始**。</span><span class="sxs-lookup"><span data-stu-id="1f0c0-150">In the BizTalk Administration Console, select **Send Ports**, right-click **Tutorial_BatchSource**, and then click **Start**.</span></span>  

### <a name="to-associate-the-send-port-with-the-source-party"></a><span data-ttu-id="1f0c0-151">送信元パーティに送信ポートを関連付ける</span><span class="sxs-lookup"><span data-stu-id="1f0c0-151">To associate the send port with the source party</span></span>  

1. <span data-ttu-id="1f0c0-152">BizTalk 管理コンソールで、次のようにクリックします。**パーティ**します。</span><span class="sxs-lookup"><span data-stu-id="1f0c0-152">In the BizTalk Administration Console, click **Parties**.</span></span> <span data-ttu-id="1f0c0-153">右クリックして**Tutorial_BatchSource**、 をクリックし、**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="1f0c0-153">Right-click **Tutorial_BatchSource**, and then click **Properties**.</span></span>  

2. <span data-ttu-id="1f0c0-154">パーティのプロパティ] ダイアログ ボックスで、[**送信ポート**コンソール ツリーでします。</span><span class="sxs-lookup"><span data-stu-id="1f0c0-154">In the Party Properties dialog box, click **Send Ports** in the console tree.</span></span> <span data-ttu-id="1f0c0-155">**送信ポート**を選択します**Tutorial_BatchSource**クリックしてドロップダウン リストから**OK**します。</span><span class="sxs-lookup"><span data-stu-id="1f0c0-155">For **Send Ports**, select **Tutorial_BatchSource** from the drop-down list, and then click **OK**.</span></span>  

   <span data-ttu-id="1f0c0-156">続行する[手順 7。オーケストレーションの開始し、BizTalk Server の再起動](../../adapters-and-accelerators/accelerator-hl7/step-7-start-the-orchestration-and-restart-biztalk-server.md)します。</span><span class="sxs-lookup"><span data-stu-id="1f0c0-156">Proceed to [Step 7: Start the Orchestration and Restart BizTalk Server](../../adapters-and-accelerators/accelerator-hl7/step-7-start-the-orchestration-and-restart-biztalk-server.md).</span></span>