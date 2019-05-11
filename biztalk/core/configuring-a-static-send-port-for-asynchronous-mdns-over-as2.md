---
title: AS2 経由で非同期 Mdn の静的送信ポートの構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cc43e767-d9d7-4b02-b3fc-0cfdfd6e61c4
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 24119db6566207455867b0a2e6b998870d445d74
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65391406"
---
# <a name="configuring-a-static-send-port-for-asynchronous-mdns-over-as2"></a><span data-ttu-id="75e79-102">AS2 経由での非同期 Mdn の静的送信ポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="75e79-102">Configuring a Static Send Port for Asynchronous MDNs over AS2</span></span>
<span data-ttu-id="75e79-103">このトピックでは、構成する方法を説明[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]静的経由での非同期の MDN の EDIINT/AS2 でエンコードされたメッセージを送信するポートを送信します。</span><span class="sxs-lookup"><span data-stu-id="75e79-103">This topic describes how to configure [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to send an asynchronous EDIINT/AS2-encoded MDN message over a static send port.</span></span> <span data-ttu-id="75e79-104">この構成には、静的な送信ポートとかどうか、必要な暗号化を設定する証明書の送信ポートで使用する作成が含まれています。</span><span class="sxs-lookup"><span data-stu-id="75e79-104">This configuration includes creating the static send port and if required, setting up an encryption certificate to be used by the send port.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="75e79-105">MDN メッセージを送信するには、送信ポートの静的ではなく動的送信ポートを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="75e79-105">You can configure a dynamic send port to send MDN messages, instead of a static send port.</span></span> <span data-ttu-id="75e79-106">詳細については、次を参照してください。 [AS2 経由での非同期 Mdn の動的送信ポートを構成する](../core/configuring-a-dynamic-send-port-for-asynchronous-mdns-over-as2.md)します。</span><span class="sxs-lookup"><span data-stu-id="75e79-106">For more information, see [Configuring a Dynamic Send Port for Asynchronous MDNs over AS2](../core/configuring-a-dynamic-send-port-for-asynchronous-mdns-over-as2.md).</span></span>  
  
 <span data-ttu-id="75e79-107">MDN メッセージを送信するには、次の構成で一方向 HTTP 送信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="75e79-107">To send an MDN message, create a one-way HTTP send port with the following configuration:</span></span>  
  
|<span data-ttu-id="75e79-108">場所</span><span class="sxs-lookup"><span data-stu-id="75e79-108">Location</span></span>|<span data-ttu-id="75e79-109">プロパティ</span><span class="sxs-lookup"><span data-stu-id="75e79-109">Property</span></span>|<span data-ttu-id="75e79-110">設定</span><span class="sxs-lookup"><span data-stu-id="75e79-110">Setting</span></span>|  
|--------------|--------------|-------------|  
|<span data-ttu-id="75e79-111">**送信ポートのプロパティ:[全般]**</span><span class="sxs-lookup"><span data-stu-id="75e79-111">**Send Port Properties: General**</span></span>|<span data-ttu-id="75e79-112">ポートの種類</span><span class="sxs-lookup"><span data-stu-id="75e79-112">Port Type</span></span>|<span data-ttu-id="75e79-113">静的な一方向送信ポート</span><span class="sxs-lookup"><span data-stu-id="75e79-113">Static One-way Send Port</span></span>|  
|<span data-ttu-id="75e79-114">**送信ポートのプロパティ:[全般]**</span><span class="sxs-lookup"><span data-stu-id="75e79-114">**Send Port Properties: General**</span></span>|<span data-ttu-id="75e79-115">トランスポートの種類</span><span class="sxs-lookup"><span data-stu-id="75e79-115">Transport Type</span></span>|<span data-ttu-id="75e79-116">HTTP**に注意してください。** EDIINT/AS2 でエンコードされたメッセージには、HTTP アダプタのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="75e79-116">HTTP **Note:**  Only the HTTP adapter can be used for transporting EDIINT/AS2-encoded messages.</span></span> <span data-ttu-id="75e79-117">このトランスポートは、HTTP アダプタ以外のアダプタでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="75e79-117">This transport will not work with an adapter other than the HTTP adapter.</span></span>|  
|<span data-ttu-id="75e79-118">**送信ポートのプロパティ:[全般]**</span><span class="sxs-lookup"><span data-stu-id="75e79-118">**Send Port Properties: General**</span></span>|<span data-ttu-id="75e79-119">送信ハンドラー</span><span class="sxs-lookup"><span data-stu-id="75e79-119">Send handler</span></span>|<span data-ttu-id="75e79-120">BizTalkServerApplication</span><span class="sxs-lookup"><span data-stu-id="75e79-120">BizTalkServerApplication</span></span>|  
|<span data-ttu-id="75e79-121">**送信ポートのプロパティ:[全般]**</span><span class="sxs-lookup"><span data-stu-id="75e79-121">**Send Port Properties: General**</span></span>|<span data-ttu-id="75e79-122">[送信パイプライン]</span><span class="sxs-lookup"><span data-stu-id="75e79-122">Send pipeline</span></span>|<span data-ttu-id="75e79-123">AS2Send</span><span class="sxs-lookup"><span data-stu-id="75e79-123">AS2Send</span></span>|  
|<span data-ttu-id="75e79-124">**HTTP トランスポートのプロパティ**</span><span class="sxs-lookup"><span data-stu-id="75e79-124">**HTTP Transport Properties**</span></span>|<span data-ttu-id="75e79-125">送信先 URL</span><span class="sxs-lookup"><span data-stu-id="75e79-125">Destination URL</span></span>|<span data-ttu-id="75e79-126">\<送信先 URL の文字列\></span><span class="sxs-lookup"><span data-stu-id="75e79-126">\<Destination URL string\></span></span>|  
|<span data-ttu-id="75e79-127">**HTTP トランスポートのプロパティ**</span><span class="sxs-lookup"><span data-stu-id="75e79-127">**HTTP Transport Properties**</span></span>|<span data-ttu-id="75e79-128">[チャンク エンコードを有効にする]</span><span class="sxs-lookup"><span data-stu-id="75e79-128">Enable chunked encoding</span></span>|<span data-ttu-id="75e79-129">クリア</span><span class="sxs-lookup"><span data-stu-id="75e79-129">Cleared</span></span>|  
|<span data-ttu-id="75e79-130">**送信ポートのプロパティ:フィルター**</span><span class="sxs-lookup"><span data-stu-id="75e79-130">**Send Port Properties: Filters**</span></span>|<span data-ttu-id="75e79-131">プロパティ</span><span class="sxs-lookup"><span data-stu-id="75e79-131">Property</span></span>|<span data-ttu-id="75e79-132">EdiIntAS.IsAS2AsynchronousMdn**に注意してください。** この送信ポートで指定したアドレス宛ての MDN メッセージだけがこのサブスクリプション フィルターによって取り出されることを確認する追加のフィルター式を指定することも必要があります。</span><span class="sxs-lookup"><span data-stu-id="75e79-132">EdiIntAS.IsAS2AsynchronousMdn **Note:**  You should also specify additional filter expressions to ensure that only MDN messages destined to the address specified in this send port are picked up by this subscription filter.</span></span>|  
|<span data-ttu-id="75e79-133">**送信ポートのプロパティ:フィルター**</span><span class="sxs-lookup"><span data-stu-id="75e79-133">**Send Port Properties: Filters**</span></span>|<span data-ttu-id="75e79-134">演算子</span><span class="sxs-lookup"><span data-stu-id="75e79-134">Operator</span></span>|==|  
|<span data-ttu-id="75e79-135">**送信ポートのプロパティ:フィルター**</span><span class="sxs-lookup"><span data-stu-id="75e79-135">**Send Port Properties: Filters**</span></span>|<span data-ttu-id="75e79-136">値</span><span class="sxs-lookup"><span data-stu-id="75e79-136">Value</span></span>|<span data-ttu-id="75e79-137">True</span><span class="sxs-lookup"><span data-stu-id="75e79-137">True</span></span>|  
|<span data-ttu-id="75e79-138">**送信ポートのプロパティ:証明書**</span><span class="sxs-lookup"><span data-stu-id="75e79-138">**Send Port Properties: Certificates**</span></span>|<span data-ttu-id="75e79-139">"一般名" および "拇印"</span><span class="sxs-lookup"><span data-stu-id="75e79-139">Common Name  and thumbprint</span></span>|<span data-ttu-id="75e79-140">送信 MDN メッセージの暗号化証明書を使用する場合は、証明書名と拇印を入力します。</span><span class="sxs-lookup"><span data-stu-id="75e79-140">Enter the certificate name and thumbprint if using an encryption certificate for the outbound MDN message.</span></span>|  
  
 <span data-ttu-id="75e79-141">指定されたアドレスに非同期 MDN を送信する必要があります、 **- Receipt-delivery-option**受信 AS2 メッセージのヘッダー。</span><span class="sxs-lookup"><span data-stu-id="75e79-141">An asynchronous MDN should be sent to the address specified in the **Receipt-Delivery-Option** header of the received AS2 message.</span></span> <span data-ttu-id="75e79-142">動的送信ポートのためには、自動的に対し、静的な送信ポートがメッセージを送信、**送信先 URL**で送信ポートのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="75e79-142">A dynamic send port will do so automatically, whereas a static send port will send the message to the **Destination URL** in the send port properties.</span></span> <span data-ttu-id="75e79-143">非同期 MDN では、静的な送信ポートを送信する場合に送信する URL が正しいことを確認します。</span><span class="sxs-lookup"><span data-stu-id="75e79-143">When sending an asynchronous MDN with a static send port, ensure that the URL you are sending to is correct.</span></span>  
  
## <a name="functionality"></a><span data-ttu-id="75e79-144">機能</span><span class="sxs-lookup"><span data-stu-id="75e79-144">Functionality</span></span>  
 <span data-ttu-id="75e79-145">送信ポートとパイプラインは MDN を送信するには、次を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="75e79-145">The send port and pipeline must do the following to send an MDN:</span></span>  
  
-   <span data-ttu-id="75e79-146">フィルタ リングして、MDN を取得、`EdiIntAS.IsAS2AsynchronousMdn==True`プロパティ。</span><span class="sxs-lookup"><span data-stu-id="75e79-146">Pick up the MDN by filtering on the `EdiIntAS.IsAS2AsynchronousMdn==True` property.</span></span>  
  
-   <span data-ttu-id="75e79-147">AS2 メッセージを構築します。</span><span class="sxs-lookup"><span data-stu-id="75e79-147">Build an AS2 message.</span></span> <span data-ttu-id="75e79-148">このプロセスの詳細については、次を参照してください。[送信 AS2 メッセージを生成する](../core/generating-an-outgoing-as2-message.md)します。</span><span class="sxs-lookup"><span data-stu-id="75e79-148">For more information about this process, see [Generating an Outgoing AS2 Message](../core/generating-an-outgoing-as2-message.md).</span></span>  
  
-   <span data-ttu-id="75e79-149">送信ポートで定義されているアドレスに MDN をルーティングします。</span><span class="sxs-lookup"><span data-stu-id="75e79-149">Route the MDN to the address defined in the send port.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75e79-150">参照</span><span class="sxs-lookup"><span data-stu-id="75e79-150">See Also</span></span>  
 [<span data-ttu-id="75e79-151">AS2 ソリューションのポートの構成</span><span class="sxs-lookup"><span data-stu-id="75e79-151">Configuring Ports for an AS2 Solution</span></span>](../core/configuring-ports-for-an-as2-solution.md)