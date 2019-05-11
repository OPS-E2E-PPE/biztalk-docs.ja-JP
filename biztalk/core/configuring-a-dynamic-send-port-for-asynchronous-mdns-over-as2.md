---
title: AS2 経由で非同期 Mdn の動的送信ポートの構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 72646c90-89db-4884-824b-6921bb824f8d
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3c6d8c962e1a417e1b97fd6fe8224718785133fd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65391421"
---
# <a name="configuring-a-dynamic-send-port-for-asynchronous-mdns-over-as2"></a><span data-ttu-id="e15e2-102">AS2 経由での非同期 Mdn の動的送信ポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="e15e2-102">Configuring a Dynamic Send Port for Asynchronous MDNs over AS2</span></span>
<span data-ttu-id="e15e2-103">非同期 MDN の EDIINT/AS2 でエンコードされたメッセージを HTTP/HTTPS 経由で送信するには、次の構成で動的な HTTP 送信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="e15e2-103">To send an asynchronous EDIINT/AS2-encoded MDN message over HTTP/HTTPS, create a dynamic HTTP send port with the following configuration:</span></span>  
  
|<span data-ttu-id="e15e2-104">場所</span><span class="sxs-lookup"><span data-stu-id="e15e2-104">Location</span></span>|<span data-ttu-id="e15e2-105">プロパティ</span><span class="sxs-lookup"><span data-stu-id="e15e2-105">Property</span></span>|<span data-ttu-id="e15e2-106">設定</span><span class="sxs-lookup"><span data-stu-id="e15e2-106">Setting</span></span>|  
|--------------|--------------|-------------|  
|<span data-ttu-id="e15e2-107">**送信ポートのプロパティ:[全般]**</span><span class="sxs-lookup"><span data-stu-id="e15e2-107">**Send Port Properties: General**</span></span>|<span data-ttu-id="e15e2-108">ポートの種類</span><span class="sxs-lookup"><span data-stu-id="e15e2-108">Port Type</span></span>|<span data-ttu-id="e15e2-109">動的な一方向</span><span class="sxs-lookup"><span data-stu-id="e15e2-109">Dynamic One-Way</span></span>|  
|<span data-ttu-id="e15e2-110">**送信ポートのプロパティ:[全般]**</span><span class="sxs-lookup"><span data-stu-id="e15e2-110">**Send Port Properties: General**</span></span>|<span data-ttu-id="e15e2-111">[送信パイプライン]</span><span class="sxs-lookup"><span data-stu-id="e15e2-111">Send pipeline</span></span>|<span data-ttu-id="e15e2-112">AS2Send</span><span class="sxs-lookup"><span data-stu-id="e15e2-112">AS2Send</span></span>|  
|<span data-ttu-id="e15e2-113">**送信ポートのプロパティ:フィルター**</span><span class="sxs-lookup"><span data-stu-id="e15e2-113">**Send Port Properties: Filters**</span></span>|<span data-ttu-id="e15e2-114">プロパティ</span><span class="sxs-lookup"><span data-stu-id="e15e2-114">Property</span></span>|<span data-ttu-id="e15e2-115">EdiIntAS.IsAS2AsynchronousMdn</span><span class="sxs-lookup"><span data-stu-id="e15e2-115">EdiIntAS.IsAS2AsynchronousMdn</span></span>|  
|<span data-ttu-id="e15e2-116">**送信ポートのプロパティ:フィルター**</span><span class="sxs-lookup"><span data-stu-id="e15e2-116">**Send Port Properties: Filters**</span></span>|<span data-ttu-id="e15e2-117">演算子</span><span class="sxs-lookup"><span data-stu-id="e15e2-117">Operator</span></span>|==|  
|<span data-ttu-id="e15e2-118">**送信ポートのプロパティ:フィルター**</span><span class="sxs-lookup"><span data-stu-id="e15e2-118">**Send Port Properties: Filters**</span></span>|<span data-ttu-id="e15e2-119">値</span><span class="sxs-lookup"><span data-stu-id="e15e2-119">Value</span></span>|<span data-ttu-id="e15e2-120">True</span><span class="sxs-lookup"><span data-stu-id="e15e2-120">True</span></span>|  
  
 <span data-ttu-id="e15e2-121">非同期 MDN に含まれるアドレスに送信する必要があります、 **- Receipt-delivery-option**受信 AS2 メッセージのヘッダー。</span><span class="sxs-lookup"><span data-stu-id="e15e2-121">An asynchronous MDN should be sent to the address contained in the **Receipt-Delivery-Option** header of the received AS2 message.</span></span> <span data-ttu-id="e15e2-122">動的送信ポートのためには、静的な送信ポートがメッセージを送信する一方、**送信先 URL**で送信ポートの定義。</span><span class="sxs-lookup"><span data-stu-id="e15e2-122">A dynamic send port will do so, whereas a static send port will send the message to the **Destination URL** in the send port definition.</span></span> <span data-ttu-id="e15e2-123">この例外は場合、**検証および MDN に対してメッセージ ヘッダーの代わりにアグリーメントの設定を使用して**プロパティで設定されて**検証**の一方向アグリーメント タブのページ、**アグリーメントプロパティ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="e15e2-123">The exception to this is if the **Use agreement settings for validation and MDN instead of message header** property is set in **Validation** page of the one-way agreement tab of the **Agreement Properties** dialog box.</span></span> <span data-ttu-id="e15e2-124">送信ポートに入力された URL に MDN メッセージを送信できる場合、 **- Receipt-delivery-option**アグリーメントのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="e15e2-124">In that case, the send port will send the MDN message to the URL entered into the **Receipt-Delivery-Option** agreement property.</span></span> <span data-ttu-id="e15e2-125">ただし、これを行うために使用する送信ポートには、動的送信ポートをする必要があります、しない静的な送信ポート。</span><span class="sxs-lookup"><span data-stu-id="e15e2-125">However, the send port used to do so must still be a dynamic send port, not a static send port.</span></span>  
  
 <span data-ttu-id="e15e2-126">Mdn と EDI の両方を返すには、この送信ポートを構成する受信確認。</span><span class="sxs-lookup"><span data-stu-id="e15e2-126">You can configure this send port to return both MDNs and EDI acknowledgments.</span></span> <span data-ttu-id="e15e2-127">EDIINT/AS2 でエンコードされたメッセージは正常に HTTP または HTTPS 経由で転送が EDI でエンコードされたペイロードの処理が失敗した場合、元のメッセージの送信者は MDN の受信両方、成功の AS2 処理と EDI を示す場合は、インスタンスのEDI の処理の失敗を示す受信確認。</span><span class="sxs-lookup"><span data-stu-id="e15e2-127">In the instance, if an EDIINT/AS2-encoded message is transported over HTTP/HTTPS successfully, but processing of the EDI-encoded payload fails, the sender of the original message would receive both an MDN indicating successful AS2 processing and an EDI acknowledgment indicating a failure in EDI processing.</span></span> <span data-ttu-id="e15e2-128">EDI でエンコードされたペイロードは中断され、エラー通知されます。</span><span class="sxs-lookup"><span data-stu-id="e15e2-128">The EDI-encoded payload would be suspended and an error posted.</span></span>  
  
## <a name="functionality"></a><span data-ttu-id="e15e2-129">機能</span><span class="sxs-lookup"><span data-stu-id="e15e2-129">Functionality</span></span>  
 <span data-ttu-id="e15e2-130">送信ポートとパイプラインは MDN を送信するには、次を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="e15e2-130">The send port and pipeline must do the following to send an MDN:</span></span>  
  
-   <span data-ttu-id="e15e2-131">フィルタ リングして、MDN を取得、`EdiIntAS.IsAS2AsynchronousMdn==True`プロパティ。</span><span class="sxs-lookup"><span data-stu-id="e15e2-131">Pick up the MDN by filtering on the `EdiIntAS.IsAS2AsynchronousMdn==True` property.</span></span>  
  
-   <span data-ttu-id="e15e2-132">AS2 メッセージを構築します。</span><span class="sxs-lookup"><span data-stu-id="e15e2-132">Build an AS2 message.</span></span> <span data-ttu-id="e15e2-133">このプロセスの詳細については、次を参照してください。[送信 AS2 メッセージを生成する](../core/generating-an-outgoing-as2-message.md)します。</span><span class="sxs-lookup"><span data-stu-id="e15e2-133">For more information about this process, see [Generating an Outgoing AS2 Message](../core/generating-an-outgoing-as2-message.md).</span></span>  
  
-   <span data-ttu-id="e15e2-134">内のアドレスに MDN をルーティング、 **- Receipt-delivery-option**メッセージのヘッダー内の行。</span><span class="sxs-lookup"><span data-stu-id="e15e2-134">Route the MDN to the address in the **Receipt-Delivery-Option** line in the header of the message.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e15e2-135">場合、**検証および MDN に対してメッセージ ヘッダーの代わりにアグリーメントの設定を使用して**プロパティで設定されて**検証**の一方向アグリーメント タブのページ、**アグリーメントのプロパティ** ダイアログ ボックスで、送信ポートは送信 MDN メッセージに入力された URL に、 **- Receipt-delivery-option**アグリーメントのプロパティに記載されているアドレスがない **-Receipt-delivery-option**受信 AS2 メッセージのヘッダー。</span><span class="sxs-lookup"><span data-stu-id="e15e2-135">If the **Use agreement settings for validation and MDN instead of message header** property is set in **Validation** page of the one-way agreement tab of the **Agreement Properties** dialog box, the send port will send the MDN message to the URL entered into the **Receipt-Delivery-Option** agreement property, not to the address mentioned in **Receipt-Delivery-Option** header of the received AS2 message.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e15e2-136">参照</span><span class="sxs-lookup"><span data-stu-id="e15e2-136">See Also</span></span>  
 [<span data-ttu-id="e15e2-137">AS2 ソリューションのポートの構成</span><span class="sxs-lookup"><span data-stu-id="e15e2-137">Configuring Ports for an AS2 Solution</span></span>](../core/configuring-ports-for-an-as2-solution.md)