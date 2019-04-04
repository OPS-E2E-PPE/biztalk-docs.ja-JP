---
title: '手順 6: 受信確認を配信する送信ポートの作成 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 739b3e60-db56-46e9-a6b1-0acbe0c08f55
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 47e30db70d67cb70ba87cf661e46ca325de1f3cc
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37003619"
---
# <a name="step-6-create-a-send-port-to-deliver-acknowledgments"></a><span data-ttu-id="b2b07-102">手順 6: 受信確認を配信する送信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="b2b07-102">Step 6: Create a Send Port to Deliver Acknowledgments</span></span>
<span data-ttu-id="b2b07-103">この手順では、バッチのソースへの受信確認を返信するポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="b2b07-103">In this step, you create a port to send acknowledgments back to the source of the batch.</span></span>  

 <span data-ttu-id="b2b07-104">MLLP アダプターでは、関連付けられているのみなります、、特定の宛先 (バッチのソース) にのみ送信されるように静的であるには、このポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="b2b07-104">You create this port to be static, so that it will only be associated with an MLLP adapter, and it will only send to a specific destination (the source of the batch).</span></span> <span data-ttu-id="b2b07-105">このチュートリアルでは、ソースは、Tutorial_BatchSource パーティに関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="b2b07-105">In this tutorial, the source is associated with the party Tutorial_BatchSource.</span></span> <span data-ttu-id="b2b07-106">この送信元パーティは、個々 のメッセージと FHS3 MSH3 と元のバッチの BHS3 に含まれます。</span><span class="sxs-lookup"><span data-stu-id="b2b07-106">This source party is contained in MSH3 of the individual messages and FHS3 and BHS3 of the original batch.</span></span>  

 <span data-ttu-id="b2b07-107">受信確認をしないデータ メッセージの送信にポートを制限するフィルターを使用してポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="b2b07-107">You create the port with filters that restrict the port to sending acknowledgments, not data messages.</span></span> <span data-ttu-id="b2b07-108">これらのフィルターは、ACK_024_GLO_DEF および Tutorial_BatchSource の変換先のメッセージの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="b2b07-108">These filters specify a message type of ACK_024_GLO_DEF and a destination of Tutorial_BatchSource.</span></span>  

 <span data-ttu-id="b2b07-109">この送信ポート構成受信確認を宛先からという名前の受信ポートと送信ポートを関連付けることによって**TwoWayAckReceivePort**します。</span><span class="sxs-lookup"><span data-stu-id="b2b07-109">You configure this send port to receive acknowledgments from the destination, by associating the send port with a receive port named **TwoWayAckReceivePort**.</span></span> [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] <span data-ttu-id="b2b07-110">セットアップ、このポートを作成してに付属の受信場所の**TwoWayAckReceiveLocation**します。</span><span class="sxs-lookup"><span data-stu-id="b2b07-110">setup creates this port, and the accompanying receive location of **TwoWayAckReceiveLocation**.</span></span> <span data-ttu-id="b2b07-111">設定して、このポートを使用する送信ポートを設定する**送信請求-応答を有効にする**に**いいえ**と設定、**受信場所の URI を送信**に**127.0.0.1:65535** (Ack をそのまま使用するために必要な設定)。</span><span class="sxs-lookup"><span data-stu-id="b2b07-111">You set the send port up to work with this port by setting **Solicit Response Enable** to **No** and setting the **Submit Receive Location URI** to **127.0.0.1:65535** (the settings required to accept ACKs).</span></span> <span data-ttu-id="b2b07-112">詳細については、[設定を、送信ポートの受信確認の](../../adapters-and-accelerators/accelerator-hl7/setting-up-a-send-port-for-receiving-acks.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b2b07-112">For more information, see [Setting Up a Send Port for Receiving ACKs](../../adapters-and-accelerators/accelerator-hl7/setting-up-a-send-port-for-receiving-acks.md).</span></span>  

### <a name="to-create-a-send-port-to-deliver-acknowledgments"></a><span data-ttu-id="b2b07-113">確認を配信する送信ポートを作成するには</span><span class="sxs-lookup"><span data-stu-id="b2b07-113">To create a send port to deliver acknowledgments</span></span>  

1. <span data-ttu-id="b2b07-114">右クリックし、BizTalk Server 管理コンソールで**送信ポート**、 をポイント**新規**、 をクリックし、**静的な一方向送信ポート**。</span><span class="sxs-lookup"><span data-stu-id="b2b07-114">In the BizTalk Server Administration Console, right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port**.</span></span>  

2. <span data-ttu-id="b2b07-115">[送信ポートのプロパティ] ダイアログ ボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="b2b07-115">In the Send Port Properties dialog box, do the following:</span></span>  


   |      <span data-ttu-id="b2b07-116">プロパティ</span><span class="sxs-lookup"><span data-stu-id="b2b07-116">Use this</span></span>      |                                <span data-ttu-id="b2b07-117">目的</span><span class="sxs-lookup"><span data-stu-id="b2b07-117">To do this</span></span>                                 |
   |--------------------|---------------------------------------------------------------------------|
   |      <span data-ttu-id="b2b07-118">**名前**</span><span class="sxs-lookup"><span data-stu-id="b2b07-118">**Name**</span></span>      |                        <span data-ttu-id="b2b07-119">型**Tutorial_2wayAck**します。</span><span class="sxs-lookup"><span data-stu-id="b2b07-119">Type **Tutorial_2wayAck**.</span></span>                         |
   | <span data-ttu-id="b2b07-120">**トランスポートの種類**</span><span class="sxs-lookup"><span data-stu-id="b2b07-120">**Transport type**</span></span> |                 <span data-ttu-id="b2b07-121">選択**MLLP**ドロップダウン リストから。</span><span class="sxs-lookup"><span data-stu-id="b2b07-121">Select **MLLP** from the drop-down list.</span></span>                  |
   |   <span data-ttu-id="b2b07-122">**構成**</span><span class="sxs-lookup"><span data-stu-id="b2b07-122">**Configure**</span></span>    | <span data-ttu-id="b2b07-123">クリックして**構成**を開く、 **MLLP トランスポート プロパティ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="b2b07-123">Click **Configure** to open the **MLLP Transport Properties** dialog box.</span></span> |


3. <span data-ttu-id="b2b07-124">MLLP トランスポートのプロパティ ダイアログ ボックスで、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="b2b07-124">In the MLLP Transport Properties dialog box, do the following:</span></span>  


   |                 <span data-ttu-id="b2b07-125">プロパティ</span><span class="sxs-lookup"><span data-stu-id="b2b07-125">Use this</span></span>                  |        <span data-ttu-id="b2b07-126">目的</span><span class="sxs-lookup"><span data-stu-id="b2b07-126">To do this</span></span>         |
   |-------------------------------------------|---------------------------|
   |            <span data-ttu-id="b2b07-127">**接続名**</span><span class="sxs-lookup"><span data-stu-id="b2b07-127">**Connection Name**</span></span>            |     <span data-ttu-id="b2b07-128">型**2wayAck**します。</span><span class="sxs-lookup"><span data-stu-id="b2b07-128">Type **2wayAck**.</span></span>     |
   |                 <span data-ttu-id="b2b07-129">**ホスト**</span><span class="sxs-lookup"><span data-stu-id="b2b07-129">**Host**</span></span>                  |    <span data-ttu-id="b2b07-130">型**localhost**します。</span><span class="sxs-lookup"><span data-stu-id="b2b07-130">Type **localhost**.</span></span>    |
   |                 <span data-ttu-id="b2b07-131">**[ポート]**</span><span class="sxs-lookup"><span data-stu-id="b2b07-131">**Port**</span></span>                  |      <span data-ttu-id="b2b07-132">型**41002**します。</span><span class="sxs-lookup"><span data-stu-id="b2b07-132">Type **41002**.</span></span>      |
   |       <span data-ttu-id="b2b07-133">**有効になっている応答を送信請求します。**</span><span class="sxs-lookup"><span data-stu-id="b2b07-133">**Solicit Response Enabled**</span></span>        | <span data-ttu-id="b2b07-134">フィールドとして保持**いいえ**します。</span><span class="sxs-lookup"><span data-stu-id="b2b07-134">Keep the field as **No**.</span></span> |
   | <span data-ttu-id="b2b07-135">**送信の受信確認の場所 (URI)**</span><span class="sxs-lookup"><span data-stu-id="b2b07-135">**Submit Receive Location (URI) for ACK**</span></span> | <span data-ttu-id="b2b07-136">型**127.0.0.1:65535**</span><span class="sxs-lookup"><span data-stu-id="b2b07-136">Type **127.0.0.1:65535**</span></span>  |


4. <span data-ttu-id="b2b07-137">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b2b07-137">Click **OK**.</span></span>  

5. <span data-ttu-id="b2b07-138">送信ポートのプロパティ ダイアログ ボックスでの**送信パイプライン**、 **BTAHL72XPipelines.BTAHL72XSendPipeline**します。</span><span class="sxs-lookup"><span data-stu-id="b2b07-138">In the Send Port Properties dialog box, for **Send pipeline**, select **BTAHL72XPipelines.BTAHL72XSendPipeline**.</span></span>  

6. <span data-ttu-id="b2b07-139">コンソール ツリーで、クリックして**フィルター**、し、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="b2b07-139">In the console tree, click **Filters**, and then do the following:</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="b2b07-140">次のデータを示すとおりに入力することを確認します。</span><span class="sxs-lookup"><span data-stu-id="b2b07-140">Ensure that you enter the following data exactly as shown.</span></span> <span data-ttu-id="b2b07-141">このデータは、大文字小文字を区別します。</span><span class="sxs-lookup"><span data-stu-id="b2b07-141">This data is case-sensitive.</span></span>  

   |          <span data-ttu-id="b2b07-142">プロパティ</span><span class="sxs-lookup"><span data-stu-id="b2b07-142">Use this</span></span>          |                                            <span data-ttu-id="b2b07-143">目的</span><span class="sxs-lookup"><span data-stu-id="b2b07-143">To do this</span></span>                                            |
   |----------------------------|--------------------------------------------------------------------------------------------------|
   | <span data-ttu-id="b2b07-144">**プロパティ**(1 行目)</span><span class="sxs-lookup"><span data-stu-id="b2b07-144">**Property** (first line)</span></span>  |   <span data-ttu-id="b2b07-145">下のフィールドをクリックします。**プロパティ**を選択し、 **BTS します。MessageType**ドロップダウン リストから。</span><span class="sxs-lookup"><span data-stu-id="b2b07-145">Click the field under **Property**, then select **BTS.MessageType** from the drop-down list.</span></span>   |
   |        <span data-ttu-id="b2b07-146">**[演算子]**</span><span class="sxs-lookup"><span data-stu-id="b2b07-146">**Operator**</span></span>        |                              <span data-ttu-id="b2b07-147">選択**==** ドロップダウン リストから。</span><span class="sxs-lookup"><span data-stu-id="b2b07-147">Select **==** from the drop-down list.</span></span>                              |
   |         <span data-ttu-id="b2b07-148">**[値]**</span><span class="sxs-lookup"><span data-stu-id="b2b07-148">**Value**</span></span>          |                <span data-ttu-id="b2b07-149">型 **<http://microsoft.com/HealthCare/HL7/2X#ACK_24_GLO_DEF>** します。</span><span class="sxs-lookup"><span data-stu-id="b2b07-149">Type **<http://microsoft.com/HealthCare/HL7/2X#ACK_24_GLO_DEF>**.</span></span>                 |
   |        <span data-ttu-id="b2b07-150">**グループ化**</span><span class="sxs-lookup"><span data-stu-id="b2b07-150">**Group By**</span></span>        |                              <span data-ttu-id="b2b07-151">選択**または**ドロップダウン リストから。</span><span class="sxs-lookup"><span data-stu-id="b2b07-151">Select **OR** from the drop-down list.</span></span>                              |
   | <span data-ttu-id="b2b07-152">**プロパティ**(2 行目)</span><span class="sxs-lookup"><span data-stu-id="b2b07-152">**Property** (second line)</span></span> | <span data-ttu-id="b2b07-153">下のフィールドをクリックします。**プロパティ**、し、 **BTS します。MessageType**ドロップダウン リストから。</span><span class="sxs-lookup"><span data-stu-id="b2b07-153">Click the field under **Property**, and then select **BTS.MessageType** from the drop-down list.</span></span> |
   |        <span data-ttu-id="b2b07-154">**[演算子]**</span><span class="sxs-lookup"><span data-stu-id="b2b07-154">**Operator**</span></span>        |                              <span data-ttu-id="b2b07-155">選択**==** ドロップダウン リストから。</span><span class="sxs-lookup"><span data-stu-id="b2b07-155">Select **==** from the drop-down list.</span></span>                              |
   |         <span data-ttu-id="b2b07-156">**[値]**</span><span class="sxs-lookup"><span data-stu-id="b2b07-156">**Value**</span></span>          |                <span data-ttu-id="b2b07-157">型**<http://microsoft.com/HealthCare/HL7/2X#ACK_25_GLO_DEF>します。**</span><span class="sxs-lookup"><span data-stu-id="b2b07-157">Type **<http://microsoft.com/HealthCare/HL7/2X#ACK_25_GLO_DEF>.**</span></span>                 |
   |        <span data-ttu-id="b2b07-158">**グループ化**</span><span class="sxs-lookup"><span data-stu-id="b2b07-158">**Group By**</span></span>        |                             <span data-ttu-id="b2b07-159">選択**と**ドロップダウン リストから。</span><span class="sxs-lookup"><span data-stu-id="b2b07-159">Select **And** from the drop-down list.</span></span>                              |
   | <span data-ttu-id="b2b07-160">**プロパティ**(3 行目)</span><span class="sxs-lookup"><span data-stu-id="b2b07-160">**Property** (third line)</span></span>  |   <span data-ttu-id="b2b07-161">下にある 2 番目の行のフィールドをクリックします。**プロパティ**を選択し、 **BTAHL7Schemas.MSH5_1**します。</span><span class="sxs-lookup"><span data-stu-id="b2b07-161">Click the field on the second line under **Property**, then select **BTAHL7Schemas.MSH5_1**.</span></span>   |
   |        <span data-ttu-id="b2b07-162">**[演算子]**</span><span class="sxs-lookup"><span data-stu-id="b2b07-162">**Operator**</span></span>        |                              <span data-ttu-id="b2b07-163">選択**==** ドロップダウン リストから。</span><span class="sxs-lookup"><span data-stu-id="b2b07-163">Select **==** from the drop-down list.</span></span>                              |
   |         <span data-ttu-id="b2b07-164">**[値]**</span><span class="sxs-lookup"><span data-stu-id="b2b07-164">**Value**</span></span>          |                                  <span data-ttu-id="b2b07-165">型**Tutorial_BatchSource**します。</span><span class="sxs-lookup"><span data-stu-id="b2b07-165">Type **Tutorial_BatchSource**.</span></span>                                  |

   > [!NOTE]
   >  <span data-ttu-id="b2b07-166">最初のフィルターは、受信確認メッセージをサブスクライブしていることを意味します。</span><span class="sxs-lookup"><span data-stu-id="b2b07-166">The first filter means that you are subscribing to the acknowledgment message.</span></span> <span data-ttu-id="b2b07-167">2 番目のフィルターは、発行元の変換先を含む受信確認をすることを意味**Tutorial_BatchSource**します。</span><span class="sxs-lookup"><span data-stu-id="b2b07-167">The second filter means that you want the acknowledgment that has the destination of the publisher, **Tutorial_BatchSource**.</span></span>  

7. <span data-ttu-id="b2b07-168">**Enter**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b2b07-168">Click **Enter**.</span></span> <span data-ttu-id="b2b07-169">クリックしてダイアログ ボックスの下部にあるウィンドウで、フィルター式の入力が正しいことを確認します**OK**します。</span><span class="sxs-lookup"><span data-stu-id="b2b07-169">In the pane at the bottom of the dialog box, verify that you entered the filter expression correctly, and then click **OK**.</span></span>  

8. <span data-ttu-id="b2b07-170">管理コンソールで、**送信ポート**を右クリックして**Tutorial_2wayAck**、し、**開始**します。</span><span class="sxs-lookup"><span data-stu-id="b2b07-170">In the Administration Console, click **Send Ports**, right-click **Tutorial_2wayAck**, and then select **Start**.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="b2b07-171">TwoWayAckReceivePort を有効にする必要があります、Tutorial_2wayAck ご送信ポートが正しく機能する、受信場所。</span><span class="sxs-lookup"><span data-stu-id="b2b07-171">For the Tutorial_2wayAck send port to function properly, you must enable the TwoWayAckReceivePort receive location.</span></span>  

9. <span data-ttu-id="b2b07-172">クリックして**受信場所**します。</span><span class="sxs-lookup"><span data-stu-id="b2b07-172">Click **Receive Locations**.</span></span> <span data-ttu-id="b2b07-173">TwoWayAckReceiveLocation の状態が有効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="b2b07-173">Verify that the status for the TwoWayAckReceiveLocation is enabled.</span></span> <span data-ttu-id="b2b07-174">ない場合を右クリックして**TwoWayAckReceiveLocation**、 をクリックし、**を有効にする**します。</span><span class="sxs-lookup"><span data-stu-id="b2b07-174">If not, right-click **TwoWayAckReceiveLocation**, and then click **Enable**.</span></span>  

   <span data-ttu-id="b2b07-175">進みます[手順 7: を作成し、送信元パーティを構成する](../../adapters-and-accelerators/accelerator-hl7/step-7-create-and-configure-a-source-party.md)します。</span><span class="sxs-lookup"><span data-stu-id="b2b07-175">Proceed to [Step 7: Create and Configure a Source Party](../../adapters-and-accelerators/accelerator-hl7/step-7-create-and-configure-a-source-party.md).</span></span>