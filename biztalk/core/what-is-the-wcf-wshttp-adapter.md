---
title: Wcf-wshttp アダプターとは何ですか。 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF-WSHttp adapters, about WCF-WSHttp adapters
ms.assetid: 183a19e3-10b1-403f-b274-34a441e774d1
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d3d82d26e03163d856bc4ce9d0cc8d948d07e54a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65242803"
---
# <a name="what-is-the-wcf-wshttp-adapter"></a><span data-ttu-id="1c309-103">Wcf-wshttp アダプターとは何ですか。</span><span class="sxs-lookup"><span data-stu-id="1c309-103">What Is the WCF-WSHttp Adapter?</span></span>
<span data-ttu-id="1c309-104">Wcf-wshttp アダプターを使用してサービスとクライアントは、テキストまたは Message Transmission Optimization Mechanism (HTTP または HTTPS トランスポートを使用して、次世代 Web サービス標準が理解できると、コンピューター間の通信を行うことができます。MTOM) エンコードです。</span><span class="sxs-lookup"><span data-stu-id="1c309-104">You can use the WCF-WSHttp adapter to do cross-computer communication with services and clients that can understand the next-generation Web service standards, using either the HTTP or HTTPS transport with text or Message Transmission Optimization Mechanism (MTOM) encoding.</span></span> <span data-ttu-id="1c309-105">Wcf-wshttp アダプタは、SOAP セキュリティ、信頼性、およびトランザクションの各機能へのフル アクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="1c309-105">The WCF-WSHttp adapter provides full access to the SOAP security, reliability, and transaction features.</span></span>  
  
 <span data-ttu-id="1c309-106">次の表では、Wcf-wshttp アダプタの特性をまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="1c309-106">The following table summarizes the characteristics of the WCF-WSHttp adapter.</span></span>  
  
|<span data-ttu-id="1c309-107">説明</span><span class="sxs-lookup"><span data-stu-id="1c309-107">Description</span></span>|<span data-ttu-id="1c309-108">特性</span><span class="sxs-lookup"><span data-stu-id="1c309-108">Characteristic</span></span>|  
|-----------------|--------------------|  
|<span data-ttu-id="1c309-109">相互運用性レベル</span><span class="sxs-lookup"><span data-stu-id="1c309-109">Interoperability level</span></span>|<span data-ttu-id="1c309-110">WS プロファイル</span><span class="sxs-lookup"><span data-stu-id="1c309-110">WS-Profile</span></span>|  
|<span data-ttu-id="1c309-111">[メッセージ エンコード]</span><span class="sxs-lookup"><span data-stu-id="1c309-111">Message encoding</span></span>|<span data-ttu-id="1c309-112">テキストまたは MTOM</span><span class="sxs-lookup"><span data-stu-id="1c309-112">Text or MTOM</span></span>|  
|<span data-ttu-id="1c309-113">[境界]</span><span class="sxs-lookup"><span data-stu-id="1c309-113">Boundary</span></span>|<span data-ttu-id="1c309-114">コンピュータ間</span><span class="sxs-lookup"><span data-stu-id="1c309-114">Cross-computer</span></span>|  
|<span data-ttu-id="1c309-115">トランスポート プロトコル</span><span class="sxs-lookup"><span data-stu-id="1c309-115">Transport protocol</span></span>|<span data-ttu-id="1c309-116">HTTP または HTTPS</span><span class="sxs-lookup"><span data-stu-id="1c309-116">HTTP or HTTPS</span></span>|  
|<span data-ttu-id="1c309-117">[セキュリティ モード]</span><span class="sxs-lookup"><span data-stu-id="1c309-117">Security mode</span></span>|<span data-ttu-id="1c309-118">None、メッセージ、トランスポート、および TransportWithMessageCredential します。</span><span class="sxs-lookup"><span data-stu-id="1c309-118">None, Message, Transport, and TransportWithMessageCredential.</span></span>|  
|<span data-ttu-id="1c309-119">クライアント認証のメカニズム</span><span class="sxs-lookup"><span data-stu-id="1c309-119">Client authentication mechanism</span></span>|<span data-ttu-id="1c309-120">トランスポート セキュリティとメッセージ セキュリティ</span><span class="sxs-lookup"><span data-stu-id="1c309-120">Transport Security and Message Security</span></span>|  
|<span data-ttu-id="1c309-121">WS-ReliableMessaging のサポート</span><span class="sxs-lookup"><span data-stu-id="1c309-121">Support for WS-ReliableMessaging</span></span>|<span data-ttu-id="1c309-122">いいえ</span><span class="sxs-lookup"><span data-stu-id="1c309-122">No</span></span>|  
|<span data-ttu-id="1c309-123">WS-AtomicTransaction のサポート</span><span class="sxs-lookup"><span data-stu-id="1c309-123">Support for WS-AtomicTransaction</span></span>|<span data-ttu-id="1c309-124">はい</span><span class="sxs-lookup"><span data-stu-id="1c309-124">Yes</span></span>|  
|<span data-ttu-id="1c309-125">一方向メッセージングのサポート</span><span class="sxs-lookup"><span data-stu-id="1c309-125">Support for one-way messaging</span></span>|<span data-ttu-id="1c309-126">はい</span><span class="sxs-lookup"><span data-stu-id="1c309-126">Yes</span></span>|  
|<span data-ttu-id="1c309-127">双方向メッセージングのサポート</span><span class="sxs-lookup"><span data-stu-id="1c309-127">Support for two-way messaging</span></span>|<span data-ttu-id="1c309-128">はい</span><span class="sxs-lookup"><span data-stu-id="1c309-128">Yes</span></span>|  
|<span data-ttu-id="1c309-129">受信アダプタのホストの種類</span><span class="sxs-lookup"><span data-stu-id="1c309-129">Host type for receive adapter</span></span>|<span data-ttu-id="1c309-130">分離されます。</span><span class="sxs-lookup"><span data-stu-id="1c309-130">Isolated</span></span>|  
|<span data-ttu-id="1c309-131">送信アダプタのホストの種類</span><span class="sxs-lookup"><span data-stu-id="1c309-131">Host type for send adapter</span></span>|<span data-ttu-id="1c309-132">インプロセス</span><span class="sxs-lookup"><span data-stu-id="1c309-132">In-process</span></span>|  
  
 <span data-ttu-id="1c309-133">Wcf-wshttp アダプターは、2 つのアダプターで構成されます-受信アダプタと送信アダプター。</span><span class="sxs-lookup"><span data-stu-id="1c309-133">The WCF-WSHttp adapter consists of two adapters—a receive adapter and a send adapter.</span></span>  
  
 <span data-ttu-id="1c309-134">**Wcf-wshttp 受信アダプター**</span><span class="sxs-lookup"><span data-stu-id="1c309-134">**WCF-WSHttp Receive Adapter**</span></span>  
  
 <span data-ttu-id="1c309-135">Wcf-wshttp を使用する受信アダプタは、HTTP または HTTPS プロトコルを介して WCF サービス要求を受信します。</span><span class="sxs-lookup"><span data-stu-id="1c309-135">You use the WCF-WSHttp receive adapter to receive WCF service requests through the HTTP or HTTPS protocol.</span></span> <span data-ttu-id="1c309-136">Wcf-wshttp 受信アダプタを使用する受信場所は、一方向として構成できますまたは要求-応答 (双方向)。</span><span class="sxs-lookup"><span data-stu-id="1c309-136">A receive location that uses the WCF-WSHttp receive adapter can be configured as one-way or request-response (two-way).</span></span>  
  
 <span data-ttu-id="1c309-137">**Wcf-wshttp 送信アダプター**</span><span class="sxs-lookup"><span data-stu-id="1c309-137">**WCF-WSHttp Send Adapter**</span></span>  
  
 <span data-ttu-id="1c309-138">Wcf-wshttp 送信アダプターを使用すると、HTTP または HTTPS プロトコルを使用して、型宣言不要なコントラクトを介して WCF サービスを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="1c309-138">You use the WCF-WSHttp send adapter to call a WCF service through the typeless contract by using the HTTP or HTTPS protocol.</span></span>  
  
 <span data-ttu-id="1c309-139">WCF の詳細については、受信し送信アダプターを参照してください[WCF アダプタは何ですか?](../core/what-are-the-wcf-adapters.md)します。</span><span class="sxs-lookup"><span data-stu-id="1c309-139">For more information about WCF receive and send adapters, see [What Are the WCF Adapters?](../core/what-are-the-wcf-adapters.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c309-140">参照</span><span class="sxs-lookup"><span data-stu-id="1c309-140">See Also</span></span>  
 <span data-ttu-id="1c309-141">[Wcf-wshttp アダプタの構成](../core/configuring-the-wcf-wshttp-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="1c309-141">[Configuring the WCF-WSHttp Adapter](../core/configuring-the-wcf-wshttp-adapter.md) </span></span>  
 [<span data-ttu-id="1c309-142">WCF アダプター</span><span class="sxs-lookup"><span data-stu-id="1c309-142">WCF Adapters</span></span>](../core/wcf-adapters.md)