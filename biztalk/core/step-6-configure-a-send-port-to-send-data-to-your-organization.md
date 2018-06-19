---
title: '手順 6: 組織にデータを送信する送信ポートの構成 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 796570ca-8178-4679-9213-d67a2a189bf9
caps.latest.revision: 26
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3b513725024aec755515ccac998745220ee5dfa7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22277010"
---
# <a name="step-6-configure-a-send-port-to-send-data-to-your-organization"></a><span data-ttu-id="70f1d-102">手順 6: 組織にデータを送信する送信ポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="70f1d-102">Step 6: Configure a Send Port to Send Data to Your Organization</span></span>
<span data-ttu-id="70f1d-103">![手順 9 の 6](../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-6of9.gif "Step_6of9")</span><span class="sxs-lookup"><span data-stu-id="70f1d-103">![Step 6 of 9](../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-6of9.gif "Step_6of9")</span></span>  
  
 <span data-ttu-id="70f1d-104">このステップでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] から組織を表す OrderSystem パーティに 850 メッセージを送信するように送信ポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="70f1d-104">In this step you configure a send port to send the 850 message from [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to the OrderSystem party that represents your organization.</span></span> <span data-ttu-id="70f1d-105">この送信ポートが適用されます、 **Inbound4010850_to_OrderFile**出力メッセージを入力メッセージの形式からマップで指定された形式を変換するマップです。</span><span class="sxs-lookup"><span data-stu-id="70f1d-105">This send port applies the **Inbound4010850_to_OrderFile** map, transforming the output message from the format of the input message to the format specified in the map.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="70f1d-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="70f1d-106">Prerequisites</span></span>  
 <span data-ttu-id="70f1d-107">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="70f1d-107">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
### <a name="to-configure-a-send-port-for-the-850-message"></a><span data-ttu-id="70f1d-108">850 メッセージの送信ポートを構成するには</span><span class="sxs-lookup"><span data-stu-id="70f1d-108">To configure a send port for the 850 message</span></span>  
  
1.  <span data-ttu-id="70f1d-109">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールを右クリックして**パイプライン**、クリックして**更新**です。</span><span class="sxs-lookup"><span data-stu-id="70f1d-109">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click **Pipelines**, and then click **Refresh**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="70f1d-110">作成する送信ポートに SendOrderFilePipeline を選択できるようにするには、パイプラインの一覧の更新が必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="70f1d-110">Refreshing the pipelines list may be necessary to be able to select the SendOrderFilePipeline for the send port that you will create.</span></span>  
  
2.  <span data-ttu-id="70f1d-111">右クリック**送信ポート**、 をポイント**新規**、クリックして**静的な一方向送信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="70f1d-111">Right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port**.</span></span>  
  
3.  <span data-ttu-id="70f1d-112">**送信ポートのプロパティ** ダイアログ ボックスで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="70f1d-112">In the **Send Port Properties** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="70f1d-113">プロパティ</span><span class="sxs-lookup"><span data-stu-id="70f1d-113">Use this</span></span>|<span data-ttu-id="70f1d-114">目的</span><span class="sxs-lookup"><span data-stu-id="70f1d-114">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="70f1d-115">**名前**</span><span class="sxs-lookup"><span data-stu-id="70f1d-115">**Name**</span></span>|<span data-ttu-id="70f1d-116">入力`toOrderSystem`です。</span><span class="sxs-lookup"><span data-stu-id="70f1d-116">Enter `toOrderSystem`.</span></span>|  
    |<span data-ttu-id="70f1d-117">**型**</span><span class="sxs-lookup"><span data-stu-id="70f1d-117">**Type**</span></span>|<span data-ttu-id="70f1d-118">選択**ファイル**です。</span><span class="sxs-lookup"><span data-stu-id="70f1d-118">Select **FILE**.</span></span>|  
    |<span data-ttu-id="70f1d-119">**構成**</span><span class="sxs-lookup"><span data-stu-id="70f1d-119">**Configure**</span></span>|<span data-ttu-id="70f1d-120">をクリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="70f1d-120">Click **Configure**.</span></span>|  
  
    > [!NOTE]
    >  <span data-ttu-id="70f1d-121">テスト メッセージはフォルダに配信されるフラット ファイルであるため、送信ポートのトランスポートの種類は FILE です。</span><span class="sxs-lookup"><span data-stu-id="70f1d-121">The transport type of the send port is FILE because the test message is a flat file to be delivered into a folder.</span></span>  
  
4.  <span data-ttu-id="70f1d-122">**FILE トランスポートのプロパティ** ダイアログ ボックスで、次の操作をクリックして**OK**:</span><span class="sxs-lookup"><span data-stu-id="70f1d-122">In the **FILE Transport Properties** dialog box, do the following and then click **OK**:</span></span>  
  
    |<span data-ttu-id="70f1d-123">プロパティ</span><span class="sxs-lookup"><span data-stu-id="70f1d-123">Use this</span></span>|<span data-ttu-id="70f1d-124">目的</span><span class="sxs-lookup"><span data-stu-id="70f1d-124">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="70f1d-125">**コピー先フォルダー**</span><span class="sxs-lookup"><span data-stu-id="70f1d-125">**Destination folder**</span></span>|<span data-ttu-id="70f1d-126">をクリックして**参照**、し、[、**フォルダーの参照**] ダイアログ ボックスに移動[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]sdk \edi インターフェイス Developer tutorial \processedi_testlocations\ シナリオ a \toordersystem</span><span class="sxs-lookup"><span data-stu-id="70f1d-126">Click **Browse**, and in the **Browse for Folder** dialog box, move to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial\ProcessEDI_TestLocations\ Scenario A\toOrderSystem</span></span>|  
    |<span data-ttu-id="70f1d-127">**ファイル名**</span><span class="sxs-lookup"><span data-stu-id="70f1d-127">**File name**</span></span>|<span data-ttu-id="70f1d-128">入力`%MessageID%.txt`、順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="70f1d-128">Enter `%MessageID%.txt`, and then click **OK**.</span></span>|  
  
    > [!NOTE]
    >  <span data-ttu-id="70f1d-129">値を設定、**ファイル名**プロパティ出力ファイルが .txt 拡張子を持つことを確認します。</span><span class="sxs-lookup"><span data-stu-id="70f1d-129">The value set for the **File name** property ensures that the output file will have a .txt extension.</span></span>  
  
5.  <span data-ttu-id="70f1d-130">**送信ポートのプロパティ**] ダイアログ ボックスの**送信パイプライン**[ **SendOrderFilePipeline**です。</span><span class="sxs-lookup"><span data-stu-id="70f1d-130">In the **Send Port Properties** dialog box, for **Send pipeline**, select **SendOrderFilePipeline**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="70f1d-131">**SendOrderFilePipeline**送信パイプラインには、入力 850 メッセージからマップされたデータを使用して .txt 出力ファイルをアセンブル フラット ファイル アセンブラーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="70f1d-131">The **SendOrderFilePipeline** send pipeline includes a flat-file assembler that assembles the .txt output file, using data mapped from the input 850 message.</span></span> <span data-ttu-id="70f1d-132">出力ファイルは .txt ファイルのため、インターチェンジ/確認の状態レポートには表示されません。</span><span class="sxs-lookup"><span data-stu-id="70f1d-132">Since the output file is a .txt file, it will not show up in the Interchange/ACK status report.</span></span>  
  
6.  <span data-ttu-id="70f1d-133">コンソール ツリーでクリックして**フィルター**、し、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="70f1d-133">In the console tree, click **Filters**, and then do the following:</span></span>  
  
    |<span data-ttu-id="70f1d-134">プロパティ</span><span class="sxs-lookup"><span data-stu-id="70f1d-134">Use this</span></span>|<span data-ttu-id="70f1d-135">目的</span><span class="sxs-lookup"><span data-stu-id="70f1d-135">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="70f1d-136">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="70f1d-136">**Property**</span></span>|<span data-ttu-id="70f1d-137">選択**BTS です。ReceivePortName**です。</span><span class="sxs-lookup"><span data-stu-id="70f1d-137">Select **BTS.ReceivePortName**.</span></span>|  
    |<span data-ttu-id="70f1d-138">**演算子**</span><span class="sxs-lookup"><span data-stu-id="70f1d-138">**Operator**</span></span>|<span data-ttu-id="70f1d-139">選択 **==** です。</span><span class="sxs-lookup"><span data-stu-id="70f1d-139">Select **==**.</span></span>|  
    |<span data-ttu-id="70f1d-140">**値**</span><span class="sxs-lookup"><span data-stu-id="70f1d-140">**Value**</span></span>|<span data-ttu-id="70f1d-141">入力`ReceiveEDI_fromTHEM_A`です。</span><span class="sxs-lookup"><span data-stu-id="70f1d-141">Enter `ReceiveEDI_fromTHEM_A`.</span></span>|  
    |<span data-ttu-id="70f1d-142">**グループ化**</span><span class="sxs-lookup"><span data-stu-id="70f1d-142">**Group by**</span></span>|<span data-ttu-id="70f1d-143">選択**と**です。</span><span class="sxs-lookup"><span data-stu-id="70f1d-143">Select **And**.</span></span>|  
    |<span data-ttu-id="70f1d-144">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="70f1d-144">**Property**</span></span>|<span data-ttu-id="70f1d-145">次の行では、次のように選択します。 **BTS です。MessageType**です。</span><span class="sxs-lookup"><span data-stu-id="70f1d-145">On the next line, select **BTS.MessageType**.</span></span>|  
    |<span data-ttu-id="70f1d-146">**演算子**</span><span class="sxs-lookup"><span data-stu-id="70f1d-146">**Operator**</span></span>|<span data-ttu-id="70f1d-147">選択 **! =** です。</span><span class="sxs-lookup"><span data-stu-id="70f1d-147">Select **!=**.</span></span>|  
    |<span data-ttu-id="70f1d-148">**値**</span><span class="sxs-lookup"><span data-stu-id="70f1d-148">**Value**</span></span>|<span data-ttu-id="70f1d-149">入力`http://schemas.microsoft.com/Edi/X12#X12_997_Root`です。</span><span class="sxs-lookup"><span data-stu-id="70f1d-149">Enter `http://schemas.microsoft.com/Edi/X12#X12_997_Root`.</span></span>|  
  
    > [!NOTE]
    >  <span data-ttu-id="70f1d-150">フィルターにより、送信ポートは Receive_EDI_fromTHEM_A 受信場所で受信されたメッセージを取得し、997 受信確認ではなく 850 メッセージのみを取得します。</span><span class="sxs-lookup"><span data-stu-id="70f1d-150">The filter ensures that the send port will pick up messages that were received by the Receive_EDI_fromTHEM_A receive location, and that the send port will not pick up 997 acknowledgments, but will pick only 850 messages.</span></span>  
  
7.  <span data-ttu-id="70f1d-151">コンソール ツリーでクリックして **[outboundmaps]** です。</span><span class="sxs-lookup"><span data-stu-id="70f1d-151">In the console tree, click **OutboundMaps**.</span></span> <span data-ttu-id="70f1d-152">**送信マップ** ウィンドウで、**マップ**select の最初の行で、列**Inbound4010850_to_OrderFile**です。</span><span class="sxs-lookup"><span data-stu-id="70f1d-152">In the **Outbound Maps** pane, in the **Map** column, on the first row, select **Inbound4010850_to_OrderFile**.</span></span> <span data-ttu-id="70f1d-153">(内のエントリ、**ソース ドキュメント**列は X12_00401_850 になります)。</span><span class="sxs-lookup"><span data-stu-id="70f1d-153">(The entry in the **Source Document** column will be X12_00401_850.)</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="70f1d-154">この手順により、出力メッセージはに従って入力メッセージからマップされたデータののみで構成されること、 **Inbound4010850_to_OrderFile**マップします。</span><span class="sxs-lookup"><span data-stu-id="70f1d-154">This step ensures that the output message will consist only of the data mapped from the input message according to the **Inbound4010850_to_OrderFile** map.</span></span>  
  
8.  <span data-ttu-id="70f1d-155">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="70f1d-155">Click **OK**.</span></span>  
  
9. <span data-ttu-id="70f1d-156">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、をクリックして**送信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="70f1d-156">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, click **Send Ports**.</span></span> <span data-ttu-id="70f1d-157">右クリック**toOrderSystem**、クリックして**開始**を参加させて、ポートを開始します。</span><span class="sxs-lookup"><span data-stu-id="70f1d-157">Right-click **toOrderSystem**, and then click **Start** to enlist and start the port.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="70f1d-158">次の手順</span><span class="sxs-lookup"><span data-stu-id="70f1d-158">Next Steps</span></span>  
 <span data-ttu-id="70f1d-159">送信ポートを構成する (**toTHEM_997**) 送信 997 受信確認を Fabrikam に返信」の説明に従って[手順 7:、取引先に、受信確認を送信する送信ポートを構成する](../core/step-7-configure-a-send-port-to-send-the-acknowledgment-to-trading-partner.md)です。</span><span class="sxs-lookup"><span data-stu-id="70f1d-159">You configure the send port (**toTHEM_997**) to send the 997 acknowledgment back to Fabrikam, as described in [Step 7: Configure a Send Port to Send the Acknowledgment to Your Trading Partner](../core/step-7-configure-a-send-port-to-send-the-acknowledgment-to-trading-partner.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70f1d-160">参照</span><span class="sxs-lookup"><span data-stu-id="70f1d-160">See Also</span></span>  
 [<span data-ttu-id="70f1d-161">EDI インターチェンジと確認を送信する静的な送信ポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="70f1d-161">Configuring a Static Send Port to Send EDI Interchanges and Acknowledgments</span></span>](../core/configuring-a-static-send-port-to-send-edi-interchanges-and-acknowledgments.md)