---
title: "AS2 経由で Mdn が非同期の動的送信ポートの構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 72646c90-89db-4884-824b-6921bb824f8d
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 754917ed1a089e3182c8543e8a132a9eff73615e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-a-dynamic-send-port-for-asynchronous-mdns-over-as2"></a><span data-ttu-id="df3be-102">AS2 経由の非同期 MDN の動的送信ポートの構成</span><span class="sxs-lookup"><span data-stu-id="df3be-102">Configuring a Dynamic Send Port for Asynchronous MDNs over AS2</span></span>
<span data-ttu-id="df3be-103">EDIINT/AS2 でエンコードされた非同期 MDN メッセージを HTTP/HTTPS 経由で送信するには、次のように構成された動的な HTTP 送信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="df3be-103">To send an asynchronous EDIINT/AS2-encoded MDN message over HTTP/HTTPS, create a dynamic HTTP send port with the following configuration:</span></span>  
  
|<span data-ttu-id="df3be-104">場所</span><span class="sxs-lookup"><span data-stu-id="df3be-104">Location</span></span>|<span data-ttu-id="df3be-105">プロパティ</span><span class="sxs-lookup"><span data-stu-id="df3be-105">Property</span></span>|<span data-ttu-id="df3be-106">設定</span><span class="sxs-lookup"><span data-stu-id="df3be-106">Setting</span></span>|  
|--------------|--------------|-------------|  
|<span data-ttu-id="df3be-107">**送信ポートのプロパティ: 全般**</span><span class="sxs-lookup"><span data-stu-id="df3be-107">**Send Port Properties: General**</span></span>|<span data-ttu-id="df3be-108">ポートの種類</span><span class="sxs-lookup"><span data-stu-id="df3be-108">Port Type</span></span>|<span data-ttu-id="df3be-109">動的な一方向</span><span class="sxs-lookup"><span data-stu-id="df3be-109">Dynamic One-Way</span></span>|  
|<span data-ttu-id="df3be-110">**送信ポートのプロパティ: 全般**</span><span class="sxs-lookup"><span data-stu-id="df3be-110">**Send Port Properties: General**</span></span>|<span data-ttu-id="df3be-111">[送信パイプライン]</span><span class="sxs-lookup"><span data-stu-id="df3be-111">Send pipeline</span></span>|<span data-ttu-id="df3be-112">AS2Send</span><span class="sxs-lookup"><span data-stu-id="df3be-112">AS2Send</span></span>|  
|<span data-ttu-id="df3be-113">**送信ポートのプロパティ: フィルター**</span><span class="sxs-lookup"><span data-stu-id="df3be-113">**Send Port Properties: Filters**</span></span>|<span data-ttu-id="df3be-114">プロパティ</span><span class="sxs-lookup"><span data-stu-id="df3be-114">Property</span></span>|<span data-ttu-id="df3be-115">EdiIntAS.IsAS2AsynchronousMdn</span><span class="sxs-lookup"><span data-stu-id="df3be-115">EdiIntAS.IsAS2AsynchronousMdn</span></span>|  
|<span data-ttu-id="df3be-116">**送信ポートのプロパティ: フィルター**</span><span class="sxs-lookup"><span data-stu-id="df3be-116">**Send Port Properties: Filters**</span></span>|<span data-ttu-id="df3be-117">演算子</span><span class="sxs-lookup"><span data-stu-id="df3be-117">Operator</span></span>|==|  
|<span data-ttu-id="df3be-118">**送信ポートのプロパティ: フィルター**</span><span class="sxs-lookup"><span data-stu-id="df3be-118">**Send Port Properties: Filters**</span></span>|<span data-ttu-id="df3be-119">値</span><span class="sxs-lookup"><span data-stu-id="df3be-119">Value</span></span>|<span data-ttu-id="df3be-120">True</span><span class="sxs-lookup"><span data-stu-id="df3be-120">True</span></span>|  
  
 <span data-ttu-id="df3be-121">非同期 MDN に含まれているアドレスに送信する必要があります、 **- Receipt-delivery-option**受信した AS2 メッセージのヘッダー。</span><span class="sxs-lookup"><span data-stu-id="df3be-121">An asynchronous MDN should be sent to the address contained in the **Receipt-Delivery-Option** header of the received AS2 message.</span></span> <span data-ttu-id="df3be-122">動的送信ポートのためには、静的な送信ポートがメッセージを送信する一方、**送信先 URL**送信ポートの定義にします。</span><span class="sxs-lookup"><span data-stu-id="df3be-122">A dynamic send port will do so, whereas a static send port will send the message to the **Destination URL** in the send port definition.</span></span> <span data-ttu-id="df3be-123">この例外は場合、**検証および MDN に対してメッセージ ヘッダーの代わりにアグリーメントの設定を使用して**プロパティ設定されて**検証**の一方向アグリーメント タブのページ、**アグリーメントプロパティ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="df3be-123">The exception to this is if the **Use agreement settings for validation and MDN instead of message header** property is set in **Validation** page of the one-way agreement tab of the **Agreement Properties** dialog box.</span></span> <span data-ttu-id="df3be-124">送信ポートに入力された URL に MDN メッセージを送信できる場合は、 **- Receipt-delivery-option**アグリーメントのプロパティです。</span><span class="sxs-lookup"><span data-stu-id="df3be-124">In that case, the send port will send the MDN message to the URL entered into the **Receipt-Delivery-Option** agreement property.</span></span> <span data-ttu-id="df3be-125">ただし、その際に使用される送信ポートは、静的送信ポートではなく動的送信ポートである必要があります。</span><span class="sxs-lookup"><span data-stu-id="df3be-125">However, the send port used to do so must still be a dynamic send port, not a static send port.</span></span>  
  
 <span data-ttu-id="df3be-126">この送信ポートは、MDN と EDI 受信確認の両方を返すように構成できます。</span><span class="sxs-lookup"><span data-stu-id="df3be-126">You can configure this send port to return both MDNs and EDI acknowledgments.</span></span> <span data-ttu-id="df3be-127">インスタンスで、EDIINT/AS2 でエンコードされたメッセージが HTTP/HTTPS 経由で正常に送信されたが、EDI でエンコードされたペイロードの処理が失敗した場合、元のメッセージの送信者は、AS2 が正常に処理されたことを示す MDN と EDI の処理が失敗したことを示す EDI 受信確認の両方を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="df3be-127">In the instance, if an EDIINT/AS2-encoded message is transported over HTTP/HTTPS successfully, but processing of the EDI-encoded payload fails, the sender of the original message would receive both an MDN indicating successful AS2 processing and an EDI acknowledgment indicating a failure in EDI processing.</span></span> <span data-ttu-id="df3be-128">EDI でエンコードされたペイロードは中断され、エラー通知です。</span><span class="sxs-lookup"><span data-stu-id="df3be-128">The EDI-encoded payload would be suspended and an error posted.</span></span>  
  
## <a name="functionality"></a><span data-ttu-id="df3be-129">機能</span><span class="sxs-lookup"><span data-stu-id="df3be-129">Functionality</span></span>  
 <span data-ttu-id="df3be-130">送信ポートとパイプラインは、MDN を送信する際に次の処理を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="df3be-130">The send port and pipeline must do the following to send an MDN:</span></span>  
  
-   <span data-ttu-id="df3be-131">`EdiIntAS.IsAS2AsynchronousMdn==True` プロパティに基づいてフィルター処理を行い、MDN を取得します。</span><span class="sxs-lookup"><span data-stu-id="df3be-131">Pick up the MDN by filtering on the `EdiIntAS.IsAS2AsynchronousMdn==True` property.</span></span>  
  
-   <span data-ttu-id="df3be-132">AS2 メッセージを生成します。</span><span class="sxs-lookup"><span data-stu-id="df3be-132">Build an AS2 message.</span></span> <span data-ttu-id="df3be-133">このプロセスの詳細については、次を参照してください。[送信 AS2 メッセージを生成する](../core/generating-an-outgoing-as2-message.md)です。</span><span class="sxs-lookup"><span data-stu-id="df3be-133">For more information about this process, see [Generating an Outgoing AS2 Message](../core/generating-an-outgoing-as2-message.md).</span></span>  
  
-   <span data-ttu-id="df3be-134">アドレスに MDN をルーティングする、 **- Receipt-delivery-option**メッセージのヘッダー行にします。</span><span class="sxs-lookup"><span data-stu-id="df3be-134">Route the MDN to the address in the **Receipt-Delivery-Option** line in the header of the message.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="df3be-135">場合、**検証および MDN に対してメッセージ ヘッダーの代わりにアグリーメントの設定を使用して**プロパティ設定されて**検証**の一方向アグリーメント タブのページ、**アグリーメントのプロパティ** ダイアログ ボックスで、送信ポートから送信 MDN メッセージに入力された URL に、 **- Receipt-delivery-option**アグリーメントのプロパティに記載されているアドレスがない**-Receipt-delivery-option**受信した AS2 メッセージのヘッダー。</span><span class="sxs-lookup"><span data-stu-id="df3be-135">If the **Use agreement settings for validation and MDN instead of message header** property is set in **Validation** page of the one-way agreement tab of the **Agreement Properties** dialog box, the send port will send the MDN message to the URL entered into the **Receipt-Delivery-Option** agreement property, not to the address mentioned in **Receipt-Delivery-Option** header of the received AS2 message.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df3be-136">参照</span><span class="sxs-lookup"><span data-stu-id="df3be-136">See Also</span></span>  
 [<span data-ttu-id="df3be-137">AS2 ソリューションのポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="df3be-137">Configuring Ports for an AS2 Solution</span></span>](../core/configuring-ports-for-an-as2-solution.md)