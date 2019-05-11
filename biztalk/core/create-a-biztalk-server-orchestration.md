---
title: BizTalk Server オーケストレーションの作成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 16c637ae-f94f-40f8-8ce7-73a7b7df9f8f
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5ae4a8b8f2c70143d1b9969bdcd7537911a99cc6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390162"
---
# <a name="create-a-biztalk-server-orchestration"></a><span data-ttu-id="51b7e-102">BizTalk Server オーケストレーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="51b7e-102">Create a BizTalk Server orchestration</span></span>
> [!NOTE]
>  <span data-ttu-id="51b7e-103">このチュートリアルは、BizTalk Server にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="51b7e-103">This tutorial applies to BizTalk Server only.</span></span>  
  
 <span data-ttu-id="51b7e-104">作成、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]オーケストレーションを展開するときは、JSON 注文書メッセージを受信し、XML 請求書に変換して JSON 請求書を送信します。</span><span class="sxs-lookup"><span data-stu-id="51b7e-104">Create a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] orchestration that, when deployed, receives a JSON purchase order message, transforms it to an XML invoice, and then sends out a JSON invoice.</span></span>  
  
## <a name="define-message-and-message-types"></a><span data-ttu-id="51b7e-105">メッセージおよびメッセージの種類を定義します。</span><span class="sxs-lookup"><span data-stu-id="51b7e-105">Define message and message types</span></span>  
 <span data-ttu-id="51b7e-106">このソリューションでは、2 つの基本的なメッセージは – 発注書と請求書。</span><span class="sxs-lookup"><span data-stu-id="51b7e-106">This solution works with two basic messages – purchase order and invoice.</span></span> <span data-ttu-id="51b7e-107">既に JSON スキーマ ウィザードを使用して JSON メッセージから注文書のスキーマを生成しました。</span><span class="sxs-lookup"><span data-stu-id="51b7e-107">We already generated the schema of the purchase order from a JSON message using the JSON schema wizard.</span></span> <span data-ttu-id="51b7e-108">このチュートリアルで既に提供されたサンプルは、請求書メッセージのスキーマを持ちます。</span><span class="sxs-lookup"><span data-stu-id="51b7e-108">The sample provided for this tutorial already has the schema for the invoice message.</span></span> <span data-ttu-id="51b7e-109">これらのスキーマを使用してメッセージの種類を作成、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アプリケーション。</span><span class="sxs-lookup"><span data-stu-id="51b7e-109">We use these schemas to create the message types in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] application.</span></span>  
  
1.  <span data-ttu-id="51b7e-110">オーケストレーションを BizTalk プロジェクトに追加し、オーケストレーション ビューを開きます。</span><span class="sxs-lookup"><span data-stu-id="51b7e-110">Add an orchestration to the BizTalk project and open the Orchestration view.</span></span>  
  
2.  <span data-ttu-id="51b7e-111">オーケストレーション ビューで右クリックして**メッセージ**、 をクリックし、**新しいメッセージ**します。</span><span class="sxs-lookup"><span data-stu-id="51b7e-111">In the Orchestration View, right-click **Messages**, and then click **New Message**.</span></span>  
  
3.  <span data-ttu-id="51b7e-112">新しく作成されたメッセージを右クリックし、**プロパティ ウィンドウ**します。</span><span class="sxs-lookup"><span data-stu-id="51b7e-112">Right-click the newly created message, and then select **Properties Window**.</span></span>  
  
4.  <span data-ttu-id="51b7e-113">**プロパティ**のウィンドウ、 **Message_1**次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="51b7e-113">In the **Properties** pane for the **Message_1**, do the following:</span></span>  
  
    |<span data-ttu-id="51b7e-114">プロパティ</span><span class="sxs-lookup"><span data-stu-id="51b7e-114">Use this</span></span>|<span data-ttu-id="51b7e-115">目的</span><span class="sxs-lookup"><span data-stu-id="51b7e-115">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="51b7e-116">[Identifier]</span><span class="sxs-lookup"><span data-stu-id="51b7e-116">Identifier</span></span>|<span data-ttu-id="51b7e-117">「`PurchaseOrder`」と入力します。</span><span class="sxs-lookup"><span data-stu-id="51b7e-117">Type `PurchaseOrder`</span></span>|  
    |<span data-ttu-id="51b7e-118">メッセージ型</span><span class="sxs-lookup"><span data-stu-id="51b7e-118">Message Type</span></span>|<span data-ttu-id="51b7e-119">ドロップダウン リストから展開**スキーマ**、し、 *BTSJSON します。PO*ここで、 *BTSJSON* BizTalk プロジェクトの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="51b7e-119">From the drop-down list, expand **Schemas**, and then select *BTSJSON.PO*, where *BTSJSON* is the name of your BizTalk project.</span></span>|  
  
5.  <span data-ttu-id="51b7e-120">請求書メッセージの新しいメッセージの種類を作成する前の手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="51b7e-120">Repeat the previous step to create a new message type for the invoice message.</span></span> <span data-ttu-id="51b7e-121">**プロパティ**ウィンドウで、新しいメッセージの場合は、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="51b7e-121">In the **Properties** pane for the new message, do the following:</span></span>  
  
    |<span data-ttu-id="51b7e-122">プロパティ</span><span class="sxs-lookup"><span data-stu-id="51b7e-122">Use this</span></span>|<span data-ttu-id="51b7e-123">目的</span><span class="sxs-lookup"><span data-stu-id="51b7e-123">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="51b7e-124">[Identifier]</span><span class="sxs-lookup"><span data-stu-id="51b7e-124">Identifier</span></span>|<span data-ttu-id="51b7e-125">「`InvoiceMsg`」と入力します。</span><span class="sxs-lookup"><span data-stu-id="51b7e-125">Type `InvoiceMsg`</span></span>|  
    |<span data-ttu-id="51b7e-126">メッセージ型</span><span class="sxs-lookup"><span data-stu-id="51b7e-126">Message Type</span></span>|<span data-ttu-id="51b7e-127">ドロップダウン リストから展開**スキーマ**、し、 *BTSJSON します。請求書*します。</span><span class="sxs-lookup"><span data-stu-id="51b7e-127">From the drop-down list, expand **Schemas**, and then select *BTSJSON.Invoice*.</span></span>|  
  
## <a name="set-up-the-orchestration"></a><span data-ttu-id="51b7e-128">オーケストレーションをセットアップします。</span><span class="sxs-lookup"><span data-stu-id="51b7e-128">Set up the orchestration</span></span>  
 <span data-ttu-id="51b7e-129">この手順では、メッセージの構築図形とオーケストレーションを作成するポートを追加します。</span><span class="sxs-lookup"><span data-stu-id="51b7e-129">In this step, you add message shapes and ports to create an orchestration.</span></span>  
  
### <a name="add-message-shapes"></a><span data-ttu-id="51b7e-130">メッセージの構築図形を追加します。</span><span class="sxs-lookup"><span data-stu-id="51b7e-130">Add message shapes</span></span>  
 <span data-ttu-id="51b7e-131">ソリューション エクスプ ローラーからオーケストレーション ファイルを開き、次のメッセージの構築図形を追加します。</span><span class="sxs-lookup"><span data-stu-id="51b7e-131">Open the orchestration file from Solution Explorer, and add the following message shapes.</span></span>  
  
-   <span data-ttu-id="51b7e-132">受信図形を追加、その名前を設定**ReceivePO**、およびメッセージの種類を**PurchaseOrder**します。</span><span class="sxs-lookup"><span data-stu-id="51b7e-132">Add a Receive shape, set its name to **ReceivePO**, and message type to **PurchaseOrder**.</span></span>  
  
-   <span data-ttu-id="51b7e-133">送信図形を追加、その名前を設定**SendInvoice**、およびメッセージの種類を**InvoiceMsg**します。</span><span class="sxs-lookup"><span data-stu-id="51b7e-133">Add a Send shape, set its name to **SendInvoice**, and message type to **InvoiceMsg**.</span></span>  
  
-   <span data-ttu-id="51b7e-134">メッセージの構築図形を追加し、設定、**構築メッセージ**プロパティをメッセージの構築図形の**InvoiceMsg**します。</span><span class="sxs-lookup"><span data-stu-id="51b7e-134">Add a Construct Message shape and set the **Messages Constructed** property of the Construct Message shape to **InvoiceMsg**.</span></span>  
  
-   <span data-ttu-id="51b7e-135">メッセージの構築図形内での変換図形を追加します。</span><span class="sxs-lookup"><span data-stu-id="51b7e-135">Add a Transform shape within the Construct Message shape.</span></span> <span data-ttu-id="51b7e-136">変換図形をダブルクリックし、**変換の構成**ダイアログ ボックスで、**既存のマップ**、オプションを選択して**BTSJSON します。POToInvoice**マップします。</span><span class="sxs-lookup"><span data-stu-id="51b7e-136">Double-click the Transform shape and in the **Transform Configuration** dialog box, select the **Existing Map** option, and then select **BTSJSON.POToInvoice** map.</span></span> <span data-ttu-id="51b7e-137">このマップは、サンプルの一部として提供されます。</span><span class="sxs-lookup"><span data-stu-id="51b7e-137">This map is provided as part of the sample.</span></span> <span data-ttu-id="51b7e-138">ダイアログ ボックスで、次のように設定します。**ソース**に**PurchaseOrder**設定と**先**に**InvoiceMsg**します。</span><span class="sxs-lookup"><span data-stu-id="51b7e-138">In the dialog box, set **Source** to **PurchaseOrder** and set **Destination** to **InvoiceMsg**.</span></span> <span data-ttu-id="51b7e-139">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="51b7e-139">Click **OK**.</span></span>  
  
### <a name="add-ports"></a><span data-ttu-id="51b7e-140">ポートを追加します。</span><span class="sxs-lookup"><span data-stu-id="51b7e-140">Add ports</span></span>  
 <span data-ttu-id="51b7e-141">– オーケストレーションのメッセージとメッセージを送信するための 1 つの受信用に 2 つのポートを追加します。</span><span class="sxs-lookup"><span data-stu-id="51b7e-141">Add two ports to the orchestration – one for receiving messages and one for sending messages.</span></span> <span data-ttu-id="51b7e-142">ポートに対して、次のプロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="51b7e-142">Use the following properties for the ports.</span></span>  
  
|<span data-ttu-id="51b7e-143">Port</span><span class="sxs-lookup"><span data-stu-id="51b7e-143">Port</span></span>|<span data-ttu-id="51b7e-144">[プロパティ]</span><span class="sxs-lookup"><span data-stu-id="51b7e-144">Properties</span></span>|  
|----------|----------------|  
|<span data-ttu-id="51b7e-145">MessageIn</span><span class="sxs-lookup"><span data-stu-id="51b7e-145">MessageIn</span></span>|<span data-ttu-id="51b7e-146">-設定**識別子**に*ReceiveJSONPO*</span><span class="sxs-lookup"><span data-stu-id="51b7e-146">-   Set **Identifier** to *ReceiveJSONPO*</span></span><br /><span data-ttu-id="51b7e-147">-設定**通信パターン**に*一方向*</span><span class="sxs-lookup"><span data-stu-id="51b7e-147">-   Set **Communication Pattern** to *One-Way*</span></span><br /><span data-ttu-id="51b7e-148">-設定**通信方向**に*受信*</span><span class="sxs-lookup"><span data-stu-id="51b7e-148">-   Set **Communication Direction** to *Receive*</span></span>|  
|<span data-ttu-id="51b7e-149">ResponseOut</span><span class="sxs-lookup"><span data-stu-id="51b7e-149">ResponseOut</span></span>|<span data-ttu-id="51b7e-150">-設定**識別子**に*SendJSONInvoice*</span><span class="sxs-lookup"><span data-stu-id="51b7e-150">-   Set **Identifier** to *SendJSONInvoice*</span></span><br /><span data-ttu-id="51b7e-151">-設定**通信パターン**に*一方向*</span><span class="sxs-lookup"><span data-stu-id="51b7e-151">-   Set **Communication Pattern** to *One-Way*</span></span><br /><span data-ttu-id="51b7e-152">-設定**通信方向**に*送信*</span><span class="sxs-lookup"><span data-stu-id="51b7e-152">-   Set **Communication Direction** to *Send*</span></span>|  
  
 <span data-ttu-id="51b7e-153">、次のスクリーン ショットのように、ポートとメッセージ図形を接続し、プロジェクトに変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="51b7e-153">Connect the ports and message shape, as shown in the screenshot below, and save changes to the project.</span></span>  
  
 <span data-ttu-id="51b7e-154">![JSON メッセージを処理するオーケストレーション](../core/media/btsjson-orchestration.png "BTSJSON_Orchestration")</span><span class="sxs-lookup"><span data-stu-id="51b7e-154">![Orchestration to process JSON messages](../core/media/btsjson-orchestration.png "BTSJSON_Orchestration")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51b7e-155">参照</span><span class="sxs-lookup"><span data-stu-id="51b7e-155">See Also</span></span>  
 [<span data-ttu-id="51b7e-156">BizTalk Server を使用して JSON メッセージの処理</span><span class="sxs-lookup"><span data-stu-id="51b7e-156">Processing JSON messages using BizTalk Server</span></span>](../core/processing-json-messages-using-biztalk-server.md)