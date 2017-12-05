---
title: "AS2 経由で Mdn が非同期の静的送信ポートの構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cc43e767-d9d7-4b02-b3fc-0cfdfd6e61c4
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3e023dc6f2165e9427fa57e109715dda6cdb258f
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="configuring-a-static-send-port-for-asynchronous-mdns-over-as2"></a><span data-ttu-id="7e3b4-102">AS2 経由の非同期 MDN の静的送信ポートの構成</span><span class="sxs-lookup"><span data-stu-id="7e3b4-102">Configuring a Static Send Port for Asynchronous MDNs over AS2</span></span>
<span data-ttu-id="7e3b4-103">このトピックでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を構成して、EDIINT/AS2 でエンコードされた非同期 MDN メッセージを静的送信ポート経由で送信する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7e3b4-103">This topic describes how to configure [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to send an asynchronous EDIINT/AS2-encoded MDN message over a static send port.</span></span> <span data-ttu-id="7e3b4-104">構成では、静的送信ポートを作成し、必要に応じて、送信ポートで使用される暗号化証明書のセットアップを行います。</span><span class="sxs-lookup"><span data-stu-id="7e3b4-104">This configuration includes creating the static send port and if required, setting up an encryption certificate to be used by the send port.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7e3b4-105">静的送信ポートの代わりに、動的送信ポートを構成して MDN メッセージを送信することもできます。</span><span class="sxs-lookup"><span data-stu-id="7e3b4-105">You can configure a dynamic send port to send MDN messages, instead of a static send port.</span></span> <span data-ttu-id="7e3b4-106">詳細については、次を参照してください。 [AS2 経由で Mdn が非同期の動的送信ポートを構成する](../core/configuring-a-dynamic-send-port-for-asynchronous-mdns-over-as2.md)です。</span><span class="sxs-lookup"><span data-stu-id="7e3b4-106">For more information, see [Configuring a Dynamic Send Port for Asynchronous MDNs over AS2](../core/configuring-a-dynamic-send-port-for-asynchronous-mdns-over-as2.md).</span></span>  
  
 <span data-ttu-id="7e3b4-107">MDN メッセージを送信するには、次の構成を使用して一方向の HTTP 送信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="7e3b4-107">To send an MDN message, create a one-way HTTP send port with the following configuration:</span></span>  
  
|<span data-ttu-id="7e3b4-108">場所</span><span class="sxs-lookup"><span data-stu-id="7e3b4-108">Location</span></span>|<span data-ttu-id="7e3b4-109">プロパティ</span><span class="sxs-lookup"><span data-stu-id="7e3b4-109">Property</span></span>|<span data-ttu-id="7e3b4-110">設定</span><span class="sxs-lookup"><span data-stu-id="7e3b4-110">Setting</span></span>|  
|--------------|--------------|-------------|  
|<span data-ttu-id="7e3b4-111">**送信ポートのプロパティ: 全般**</span><span class="sxs-lookup"><span data-stu-id="7e3b4-111">**Send Port Properties: General**</span></span>|<span data-ttu-id="7e3b4-112">ポートの種類</span><span class="sxs-lookup"><span data-stu-id="7e3b4-112">Port Type</span></span>|<span data-ttu-id="7e3b4-113">静的な一方向送信ポート</span><span class="sxs-lookup"><span data-stu-id="7e3b4-113">Static One-way Send Port</span></span>|  
|<span data-ttu-id="7e3b4-114">**送信ポートのプロパティ: 全般**</span><span class="sxs-lookup"><span data-stu-id="7e3b4-114">**Send Port Properties: General**</span></span>|<span data-ttu-id="7e3b4-115">トランスポートの種類</span><span class="sxs-lookup"><span data-stu-id="7e3b4-115">Transport Type</span></span>|<span data-ttu-id="7e3b4-116">HTTP**注:** EDIINT/AS2 でエンコードされたメッセージを転送するため、HTTP アダプタのみを使用できます。</span><span class="sxs-lookup"><span data-stu-id="7e3b4-116">HTTP **Note:**  Only the HTTP adapter can be used for transporting EDIINT/AS2-encoded messages.</span></span> <span data-ttu-id="7e3b4-117">このトランスポートは、HTTP アダプタ以外のアダプタでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="7e3b4-117">This transport will not work with an adapter other than the HTTP adapter.</span></span>|  
|<span data-ttu-id="7e3b4-118">**送信ポートのプロパティ: 全般**</span><span class="sxs-lookup"><span data-stu-id="7e3b4-118">**Send Port Properties: General**</span></span>|<span data-ttu-id="7e3b4-119">送信ハンドラー</span><span class="sxs-lookup"><span data-stu-id="7e3b4-119">Send handler</span></span>|<span data-ttu-id="7e3b4-120">BizTalkServerApplication</span><span class="sxs-lookup"><span data-stu-id="7e3b4-120">BizTalkServerApplication</span></span>|  
|<span data-ttu-id="7e3b4-121">**送信ポートのプロパティ: 全般**</span><span class="sxs-lookup"><span data-stu-id="7e3b4-121">**Send Port Properties: General**</span></span>|<span data-ttu-id="7e3b4-122">[送信パイプライン]</span><span class="sxs-lookup"><span data-stu-id="7e3b4-122">Send pipeline</span></span>|<span data-ttu-id="7e3b4-123">AS2Send</span><span class="sxs-lookup"><span data-stu-id="7e3b4-123">AS2Send</span></span>|  
|<span data-ttu-id="7e3b4-124">**HTTP トランスポートのプロパティ**</span><span class="sxs-lookup"><span data-stu-id="7e3b4-124">**HTTP Transport Properties**</span></span>|<span data-ttu-id="7e3b4-125">送信先 URL</span><span class="sxs-lookup"><span data-stu-id="7e3b4-125">Destination URL</span></span>|<span data-ttu-id="7e3b4-126">\<送信先 URL の文字列\></span><span class="sxs-lookup"><span data-stu-id="7e3b4-126">\<Destination URL string\></span></span>|  
|<span data-ttu-id="7e3b4-127">**HTTP トランスポートのプロパティ**</span><span class="sxs-lookup"><span data-stu-id="7e3b4-127">**HTTP Transport Properties**</span></span>|<span data-ttu-id="7e3b4-128">[チャンク エンコードを有効にする]</span><span class="sxs-lookup"><span data-stu-id="7e3b4-128">Enable chunked encoding</span></span>|<span data-ttu-id="7e3b4-129">クリア</span><span class="sxs-lookup"><span data-stu-id="7e3b4-129">Cleared</span></span>|  
|<span data-ttu-id="7e3b4-130">**送信ポートのプロパティ: フィルター**</span><span class="sxs-lookup"><span data-stu-id="7e3b4-130">**Send Port Properties: Filters**</span></span>|<span data-ttu-id="7e3b4-131">プロパティ</span><span class="sxs-lookup"><span data-stu-id="7e3b4-131">Property</span></span>|<span data-ttu-id="7e3b4-132">EdiIntAS.IsAS2AsynchronousMdn**注:**で指定されたアドレス宛ての MDN メッセージだけが送信ポートであることを確認する追加のフィルター式がこのサブスクリプション フィルターによって選択されても指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7e3b4-132">EdiIntAS.IsAS2AsynchronousMdn **Note:**  You should also specify additional filter expressions to ensure that only MDN messages destined to the address specified in this send port are picked up by this subscription filter.</span></span>|  
|<span data-ttu-id="7e3b4-133">**送信ポートのプロパティ: フィルター**</span><span class="sxs-lookup"><span data-stu-id="7e3b4-133">**Send Port Properties: Filters**</span></span>|<span data-ttu-id="7e3b4-134">演算子</span><span class="sxs-lookup"><span data-stu-id="7e3b4-134">Operator</span></span>|==|  
|<span data-ttu-id="7e3b4-135">**送信ポートのプロパティ: フィルター**</span><span class="sxs-lookup"><span data-stu-id="7e3b4-135">**Send Port Properties: Filters**</span></span>|<span data-ttu-id="7e3b4-136">値</span><span class="sxs-lookup"><span data-stu-id="7e3b4-136">Value</span></span>|<span data-ttu-id="7e3b4-137">True</span><span class="sxs-lookup"><span data-stu-id="7e3b4-137">True</span></span>|  
|<span data-ttu-id="7e3b4-138">**送信ポートのプロパティ: 証明書**</span><span class="sxs-lookup"><span data-stu-id="7e3b4-138">**Send Port Properties: Certificates**</span></span>|<span data-ttu-id="7e3b4-139">"一般名" および "拇印"</span><span class="sxs-lookup"><span data-stu-id="7e3b4-139">Common Name  and thumbprint</span></span>|<span data-ttu-id="7e3b4-140">送信 MDN メッセージで暗号化証明書を使用する場合は、証明書の名前および拇印を入力します。</span><span class="sxs-lookup"><span data-stu-id="7e3b4-140">Enter the certificate name and thumbprint if using an encryption certificate for the outbound MDN message.</span></span>|  
  
 <span data-ttu-id="7e3b4-141">非同期 MDN で指定されたアドレスに送信する必要があります、 **- Receipt-delivery-option**受信した AS2 メッセージのヘッダー。</span><span class="sxs-lookup"><span data-stu-id="7e3b4-141">An asynchronous MDN should be sent to the address specified in the **Receipt-Delivery-Option** header of the received AS2 message.</span></span> <span data-ttu-id="7e3b4-142">動的送信ポートのためには、自動的に対し、静的な送信ポートがメッセージを送信、**送信先 URL**送信ポートのプロパティにします。</span><span class="sxs-lookup"><span data-stu-id="7e3b4-142">A dynamic send port will do so automatically, whereas a static send port will send the message to the **Destination URL** in the send port properties.</span></span> <span data-ttu-id="7e3b4-143">静的送信ポートを使用して非同期 MDN を送信するときは、送信先の URL が正しいことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="7e3b4-143">When sending an asynchronous MDN with a static send port, ensure that the URL you are sending to is correct.</span></span>  
  
## <a name="functionality"></a><span data-ttu-id="7e3b4-144">機能</span><span class="sxs-lookup"><span data-stu-id="7e3b4-144">Functionality</span></span>  
 <span data-ttu-id="7e3b4-145">送信ポートとパイプラインは、MDN を送信する際に次の処理を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="7e3b4-145">The send port and pipeline must do the following to send an MDN:</span></span>  
  
-   <span data-ttu-id="7e3b4-146">`EdiIntAS.IsAS2AsynchronousMdn==True` プロパティに基づいてフィルター処理を行い、MDN を取得します。</span><span class="sxs-lookup"><span data-stu-id="7e3b4-146">Pick up the MDN by filtering on the `EdiIntAS.IsAS2AsynchronousMdn==True` property.</span></span>  
  
-   <span data-ttu-id="7e3b4-147">AS2 メッセージを生成します。</span><span class="sxs-lookup"><span data-stu-id="7e3b4-147">Build an AS2 message.</span></span> <span data-ttu-id="7e3b4-148">このプロセスの詳細については、次を参照してください。[送信 AS2 メッセージを生成する](../core/generating-an-outgoing-as2-message.md)です。</span><span class="sxs-lookup"><span data-stu-id="7e3b4-148">For more information about this process, see [Generating an Outgoing AS2 Message](../core/generating-an-outgoing-as2-message.md).</span></span>  
  
-   <span data-ttu-id="7e3b4-149">送信ポートで定義されたアドレスに MDN をルーティングする。</span><span class="sxs-lookup"><span data-stu-id="7e3b4-149">Route the MDN to the address defined in the send port.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e3b4-150">参照</span><span class="sxs-lookup"><span data-stu-id="7e3b4-150">See Also</span></span>  
 [<span data-ttu-id="7e3b4-151">AS2 ソリューションのポートの構成</span><span class="sxs-lookup"><span data-stu-id="7e3b4-151">Configuring Ports for an AS2 Solution</span></span>](../core/configuring-ports-for-an-as2-solution.md)