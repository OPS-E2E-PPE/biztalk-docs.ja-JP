---
title: BizTalk Server オーケストレーションを作成 |Microsoft ドキュメント
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
ms.openlocfilehash: d6223ab8d8aa3c8d1c20559a88257dd0dccaa22e
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
ms.locfileid: "26008990"
---
# <a name="create-a-biztalk-server-orchestration"></a><span data-ttu-id="e079d-102">BizTalk Server のオーケストレーションの作成</span><span class="sxs-lookup"><span data-stu-id="e079d-102">Create a BizTalk Server orchestration</span></span>
> [!NOTE]
>  <span data-ttu-id="e079d-103">このチュートリアルは、BizTalk Server にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="e079d-103">This tutorial applies to BizTalk Server only.</span></span>  
  
 <span data-ttu-id="e079d-104">配置時に JSON 注文書メッセージを受信し、XML 請求書に変換して JSON 請求書を送信する [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] オーケストレーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="e079d-104">Create a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] orchestration that, when deployed, receives a JSON purchase order message, transforms it to an XML invoice, and then sends out a JSON invoice.</span></span>  
  
## <a name="define-message-and-message-types"></a><span data-ttu-id="e079d-105">メッセージとメッセージの種類を定義します。</span><span class="sxs-lookup"><span data-stu-id="e079d-105">Define message and message types</span></span>  
 <span data-ttu-id="e079d-106">このソリューションは、注文書と請求書の 2 つの基本メッセージで機能します。</span><span class="sxs-lookup"><span data-stu-id="e079d-106">This solution works with two basic messages – purchase order and invoice.</span></span> <span data-ttu-id="e079d-107">JSON スキーマ ウィザードを使用して、JSON メッセージから注文書のスキーマをすでに生成しました。</span><span class="sxs-lookup"><span data-stu-id="e079d-107">We already generated the schema of the purchase order from a JSON message using the JSON schema wizard.</span></span> <span data-ttu-id="e079d-108">このチュートリアルに用意されているサンプルには、すでに請求書メッセージのスキーマが含まれています。</span><span class="sxs-lookup"><span data-stu-id="e079d-108">The sample provided for this tutorial already has the schema for the invoice message.</span></span> <span data-ttu-id="e079d-109">これらのスキーマを使用して、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] アプリのメッセージの種類を作成します。</span><span class="sxs-lookup"><span data-stu-id="e079d-109">We use these schemas to create the message types in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] application.</span></span>  
  
1.  <span data-ttu-id="e079d-110">オーケストレーションを BizTalk プロジェクトに追加して、オーケストレーション ビューを開きます。</span><span class="sxs-lookup"><span data-stu-id="e079d-110">Add an orchestration to the BizTalk project and open the Orchestration view.</span></span>  
  
2.  <span data-ttu-id="e079d-111">オーケストレーション ビューで右クリック**メッセージ**、クリックして**新しいメッセージ**です。</span><span class="sxs-lookup"><span data-stu-id="e079d-111">In the Orchestration View, right-click **Messages**, and then click **New Message**.</span></span>  
  
3.  <span data-ttu-id="e079d-112">新しく作成されたメッセージを右クリックし [**プロパティ] ウィンドウ**します。</span><span class="sxs-lookup"><span data-stu-id="e079d-112">Right-click the newly created message, and then select **Properties Window**.</span></span>  
  
4.  <span data-ttu-id="e079d-113">**プロパティ**のウィンドウ、 **Message_1**を次の操作します。</span><span class="sxs-lookup"><span data-stu-id="e079d-113">In the **Properties** pane for the **Message_1**, do the following:</span></span>  
  
    |<span data-ttu-id="e079d-114">プロパティ</span><span class="sxs-lookup"><span data-stu-id="e079d-114">Use this</span></span>|<span data-ttu-id="e079d-115">目的</span><span class="sxs-lookup"><span data-stu-id="e079d-115">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="e079d-116">[Identifier]</span><span class="sxs-lookup"><span data-stu-id="e079d-116">Identifier</span></span>|<span data-ttu-id="e079d-117">「`PurchaseOrder`」と入力します。</span><span class="sxs-lookup"><span data-stu-id="e079d-117">Type `PurchaseOrder`</span></span>|  
    |<span data-ttu-id="e079d-118">メッセージの種類</span><span class="sxs-lookup"><span data-stu-id="e079d-118">Message Type</span></span>|<span data-ttu-id="e079d-119">ドロップダウン リストから、展開**スキーマ**、し、 *BTSJSON です。PO*ここで、 *BTSJSON* BizTalk プロジェクトの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="e079d-119">From the drop-down list, expand **Schemas**, and then select *BTSJSON.PO*, where *BTSJSON* is the name of your BizTalk project.</span></span>|  
  
5.  <span data-ttu-id="e079d-120">前の手順を繰り返して請求書メッセージの新しいメッセージの種類を作成します。</span><span class="sxs-lookup"><span data-stu-id="e079d-120">Repeat the previous step to create a new message type for the invoice message.</span></span> <span data-ttu-id="e079d-121">**プロパティ**新しいメッセージ ウィンドウ、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="e079d-121">In the **Properties** pane for the new message, do the following:</span></span>  
  
    |<span data-ttu-id="e079d-122">プロパティ</span><span class="sxs-lookup"><span data-stu-id="e079d-122">Use this</span></span>|<span data-ttu-id="e079d-123">目的</span><span class="sxs-lookup"><span data-stu-id="e079d-123">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="e079d-124">[Identifier]</span><span class="sxs-lookup"><span data-stu-id="e079d-124">Identifier</span></span>|<span data-ttu-id="e079d-125">「`InvoiceMsg`」と入力します。</span><span class="sxs-lookup"><span data-stu-id="e079d-125">Type `InvoiceMsg`</span></span>|  
    |<span data-ttu-id="e079d-126">メッセージの種類</span><span class="sxs-lookup"><span data-stu-id="e079d-126">Message Type</span></span>|<span data-ttu-id="e079d-127">ドロップダウン リストから、展開**スキーマ**、し、 *BTSJSON です。請求書*です。</span><span class="sxs-lookup"><span data-stu-id="e079d-127">From the drop-down list, expand **Schemas**, and then select *BTSJSON.Invoice*.</span></span>|  
  
## <a name="set-up-the-orchestration"></a><span data-ttu-id="e079d-128">オーケストレーションのセットアップ</span><span class="sxs-lookup"><span data-stu-id="e079d-128">Set up the orchestration</span></span>  
 <span data-ttu-id="e079d-129">この手順では、メッセージの構築図形とポートを追加してオーケストレーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="e079d-129">In this step, you add message shapes and ports to create an orchestration.</span></span>  
  
### <a name="add-message-shapes"></a><span data-ttu-id="e079d-130">メッセージの構築図形の追加</span><span class="sxs-lookup"><span data-stu-id="e079d-130">Add message shapes</span></span>  
 <span data-ttu-id="e079d-131">ソリューション エクスプローラーからオーケストレーション ファイルを開いて、次のメッセージの構築図形を追加します。</span><span class="sxs-lookup"><span data-stu-id="e079d-131">Open the orchestration file from Solution Explorer, and add the following message shapes.</span></span>  
  
-   <span data-ttu-id="e079d-132">受信図形を追加、その名前を設定**ReceivePO**、およびメッセージの種類を**PurchaseOrder**です。</span><span class="sxs-lookup"><span data-stu-id="e079d-132">Add a Receive shape, set its name to **ReceivePO**, and message type to **PurchaseOrder**.</span></span>  
  
-   <span data-ttu-id="e079d-133">送信図形の追加、その名前を設定**SendInvoice**、およびメッセージの種類を**InvoiceMsg**です。</span><span class="sxs-lookup"><span data-stu-id="e079d-133">Add a Send shape, set its name to **SendInvoice**, and message type to **InvoiceMsg**.</span></span>  
  
-   <span data-ttu-id="e079d-134">メッセージの構築図形を追加し、設定、**構築メッセージ**にメッセージの構築図形のプロパティ**InvoiceMsg**です。</span><span class="sxs-lookup"><span data-stu-id="e079d-134">Add a Construct Message shape and set the **Messages Constructed** property of the Construct Message shape to **InvoiceMsg**.</span></span>  
  
-   <span data-ttu-id="e079d-135">メッセージの構築図形に変換図形を追加します。</span><span class="sxs-lookup"><span data-stu-id="e079d-135">Add a Transform shape within the Construct Message shape.</span></span> <span data-ttu-id="e079d-136">変換図形をダブルクリックし、、**変換の構成**ダイアログ ボックスで、**既存のマップ**オプションをクリックし  **BTSJSON です。POToInvoice**マップします。</span><span class="sxs-lookup"><span data-stu-id="e079d-136">Double-click the Transform shape and in the **Transform Configuration** dialog box, select the **Existing Map** option, and then select **BTSJSON.POToInvoice** map.</span></span> <span data-ttu-id="e079d-137">このマップはサンプルに含まれています。</span><span class="sxs-lookup"><span data-stu-id="e079d-137">This map is provided as part of the sample.</span></span> <span data-ttu-id="e079d-138">ダイアログ ボックスで、次のように設定します。**ソース**に**PurchaseOrder**設定と**先**に**InvoiceMsg**です。</span><span class="sxs-lookup"><span data-stu-id="e079d-138">In the dialog box, set **Source** to **PurchaseOrder** and set **Destination** to **InvoiceMsg**.</span></span> <span data-ttu-id="e079d-139">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e079d-139">Click **OK**.</span></span>  
  
### <a name="add-ports"></a><span data-ttu-id="e079d-140">ポートを追加します。</span><span class="sxs-lookup"><span data-stu-id="e079d-140">Add ports</span></span>  
 <span data-ttu-id="e079d-141">オーケストレーションに、メッセージの受信用と送信用の 2 つのポートを追加します。</span><span class="sxs-lookup"><span data-stu-id="e079d-141">Add two ports to the orchestration – one for receiving messages and one for sending messages.</span></span> <span data-ttu-id="e079d-142">ポートに以下のプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="e079d-142">Use the following properties for the ports.</span></span>  
  
|<span data-ttu-id="e079d-143">ポート</span><span class="sxs-lookup"><span data-stu-id="e079d-143">Port</span></span>|<span data-ttu-id="e079d-144">[プロパティ]</span><span class="sxs-lookup"><span data-stu-id="e079d-144">Properties</span></span>|  
|----------|----------------|  
|<span data-ttu-id="e079d-145">MessageIn</span><span class="sxs-lookup"><span data-stu-id="e079d-145">MessageIn</span></span>|<span data-ttu-id="e079d-146">-設定**識別子**に*ReceiveJSONPO*</span><span class="sxs-lookup"><span data-stu-id="e079d-146">-   Set **Identifier** to *ReceiveJSONPO*</span></span><br /><span data-ttu-id="e079d-147">-設定**通信パターン**に*一方向*</span><span class="sxs-lookup"><span data-stu-id="e079d-147">-   Set **Communication Pattern** to *One-Way*</span></span><br /><span data-ttu-id="e079d-148">-設定**通信方向**に*受信*</span><span class="sxs-lookup"><span data-stu-id="e079d-148">-   Set **Communication Direction** to *Receive*</span></span>|  
|<span data-ttu-id="e079d-149">ResponseOut</span><span class="sxs-lookup"><span data-stu-id="e079d-149">ResponseOut</span></span>|<span data-ttu-id="e079d-150">-設定**識別子**に*SendJSONInvoice*</span><span class="sxs-lookup"><span data-stu-id="e079d-150">-   Set **Identifier** to *SendJSONInvoice*</span></span><br /><span data-ttu-id="e079d-151">-設定**通信パターン**に*一方向*</span><span class="sxs-lookup"><span data-stu-id="e079d-151">-   Set **Communication Pattern** to *One-Way*</span></span><br /><span data-ttu-id="e079d-152">-設定**通信方向**に*送信*</span><span class="sxs-lookup"><span data-stu-id="e079d-152">-   Set **Communication Direction** to *Send*</span></span>|  
  
 <span data-ttu-id="e079d-153">以下のスクリーンショットのようにポートとメッセージの図形を接続し、プロジェクトへの変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="e079d-153">Connect the ports and message shape, as shown in the screenshot below, and save changes to the project.</span></span>  
  
 <span data-ttu-id="e079d-154">![JSON メッセージを処理するオーケストレーション](../core/media/btsjson-orchestration.png "BTSJSON_Orchestration")</span><span class="sxs-lookup"><span data-stu-id="e079d-154">![Orchestration to process JSON messages](../core/media/btsjson-orchestration.png "BTSJSON_Orchestration")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e079d-155">参照</span><span class="sxs-lookup"><span data-stu-id="e079d-155">See Also</span></span>  
 [<span data-ttu-id="e079d-156">BizTalk Server を使用して JSON メッセージの処理</span><span class="sxs-lookup"><span data-stu-id="e079d-156">Processing JSON messages using BizTalk Server</span></span>](../core/processing-json-messages-using-biztalk-server.md)