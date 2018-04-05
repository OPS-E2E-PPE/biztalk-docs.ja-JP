---
title: WCF-WSHttp アダプタについて | Microsoft Docs
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
ms.openlocfilehash: eb5d244dcfe26cf10bc4ae10c63374eef0824444
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="what-is-the-wcf-wshttp-adapter"></a><span data-ttu-id="ed355-103">WCF-WSHttp アダプタについて</span><span class="sxs-lookup"><span data-stu-id="ed355-103">What Is the WCF-WSHttp Adapter?</span></span>
<span data-ttu-id="ed355-104">WCF-WSHttp アダプタを使用すると、テキストまたは Message Transmission Optimization Mechanism (MTOM) エンコードによる HTTP または HTTPS トランスポートを使用して、次世代 Web サービス標準を理解できるサービスおよびクライアントとコンピュータ間通信を実行できます。</span><span class="sxs-lookup"><span data-stu-id="ed355-104">You can use the WCF-WSHttp adapter to do cross-computer communication with services and clients that can understand the next-generation Web service standards, using either the HTTP or HTTPS transport with text or Message Transmission Optimization Mechanism (MTOM) encoding.</span></span> <span data-ttu-id="ed355-105">WCF-WSHttp アダプタにより、SOAP セキュリティ、信頼性、およびトランザクションの各機能にフル アクセスできます。</span><span class="sxs-lookup"><span data-stu-id="ed355-105">The WCF-WSHttp adapter provides full access to the SOAP security, reliability, and transaction features.</span></span>  
  
 <span data-ttu-id="ed355-106">次の表に、WCF-WSHttp アダプタの特性をまとめます。</span><span class="sxs-lookup"><span data-stu-id="ed355-106">The following table summarizes the characteristics of the WCF-WSHttp adapter.</span></span>  
  
|<span data-ttu-id="ed355-107">Description</span><span class="sxs-lookup"><span data-stu-id="ed355-107">Description</span></span>|<span data-ttu-id="ed355-108">特性</span><span class="sxs-lookup"><span data-stu-id="ed355-108">Characteristic</span></span>|  
|-----------------|--------------------|  
|<span data-ttu-id="ed355-109">相互運用性レベル</span><span class="sxs-lookup"><span data-stu-id="ed355-109">Interoperability level</span></span>|<span data-ttu-id="ed355-110">WS-Profile</span><span class="sxs-lookup"><span data-stu-id="ed355-110">WS-Profile</span></span>|  
|<span data-ttu-id="ed355-111">[メッセージ エンコード]</span><span class="sxs-lookup"><span data-stu-id="ed355-111">Message encoding</span></span>|<span data-ttu-id="ed355-112">テキストまたは MTOM</span><span class="sxs-lookup"><span data-stu-id="ed355-112">Text or MTOM</span></span>|  
|<span data-ttu-id="ed355-113">[境界]</span><span class="sxs-lookup"><span data-stu-id="ed355-113">Boundary</span></span>|<span data-ttu-id="ed355-114">コンピュータ間</span><span class="sxs-lookup"><span data-stu-id="ed355-114">Cross-computer</span></span>|  
|<span data-ttu-id="ed355-115">トランスポート プロトコル</span><span class="sxs-lookup"><span data-stu-id="ed355-115">Transport protocol</span></span>|<span data-ttu-id="ed355-116">HTTP または HTTPS</span><span class="sxs-lookup"><span data-stu-id="ed355-116">HTTP or HTTPS</span></span>|  
|<span data-ttu-id="ed355-117">[セキュリティ モード]</span><span class="sxs-lookup"><span data-stu-id="ed355-117">Security mode</span></span>|<span data-ttu-id="ed355-118">None、Message、Transport、および TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="ed355-118">None, Message, Transport, and TransportWithMessageCredential.</span></span>|  
|<span data-ttu-id="ed355-119">クライアント認証のメカニズム</span><span class="sxs-lookup"><span data-stu-id="ed355-119">Client authentication mechanism</span></span>|<span data-ttu-id="ed355-120">トランスポート セキュリティとメッセージ セキュリティ</span><span class="sxs-lookup"><span data-stu-id="ed355-120">Transport Security and Message Security</span></span>|  
|<span data-ttu-id="ed355-121">WS-ReliableMessaging のサポート</span><span class="sxs-lookup"><span data-stu-id="ed355-121">Support for WS-ReliableMessaging</span></span>|<span data-ttu-id="ed355-122">不可</span><span class="sxs-lookup"><span data-stu-id="ed355-122">No</span></span>|  
|<span data-ttu-id="ed355-123">WS-AtomicTransaction のサポート</span><span class="sxs-lookup"><span data-stu-id="ed355-123">Support for WS-AtomicTransaction</span></span>|<span data-ttu-id="ed355-124">はい</span><span class="sxs-lookup"><span data-stu-id="ed355-124">Yes</span></span>|  
|<span data-ttu-id="ed355-125">一方向メッセージングのサポート</span><span class="sxs-lookup"><span data-stu-id="ed355-125">Support for one-way messaging</span></span>|<span data-ttu-id="ed355-126">はい</span><span class="sxs-lookup"><span data-stu-id="ed355-126">Yes</span></span>|  
|<span data-ttu-id="ed355-127">双方向メッセージングのサポート</span><span class="sxs-lookup"><span data-stu-id="ed355-127">Support for two-way messaging</span></span>|<span data-ttu-id="ed355-128">はい</span><span class="sxs-lookup"><span data-stu-id="ed355-128">Yes</span></span>|  
|<span data-ttu-id="ed355-129">受信アダプタのホストの種類</span><span class="sxs-lookup"><span data-stu-id="ed355-129">Host type for receive adapter</span></span>|<span data-ttu-id="ed355-130">分離されます。</span><span class="sxs-lookup"><span data-stu-id="ed355-130">Isolated</span></span>|  
|<span data-ttu-id="ed355-131">送信アダプタのホストの種類</span><span class="sxs-lookup"><span data-stu-id="ed355-131">Host type for send adapter</span></span>|<span data-ttu-id="ed355-132">インプロセス</span><span class="sxs-lookup"><span data-stu-id="ed355-132">In-process</span></span>|  
  
 <span data-ttu-id="ed355-133">WCF-WSHttp アダプタは、受信アダプタと送信アダプタの 2 つのアダプタで構成されます。</span><span class="sxs-lookup"><span data-stu-id="ed355-133">The WCF-WSHttp adapter consists of two adapters—a receive adapter and a send adapter.</span></span>  
  
 <span data-ttu-id="ed355-134">**Wcf-wshttp 受信アダプター**</span><span class="sxs-lookup"><span data-stu-id="ed355-134">**WCF-WSHttp Receive Adapter**</span></span>  
  
 <span data-ttu-id="ed355-135">WCF-WSHttp 受信アダプタを使用すると、HTTP プロトコルまたは HTTPS プロトコルを介して WCF サービス要求を受信できます。</span><span class="sxs-lookup"><span data-stu-id="ed355-135">You use the WCF-WSHttp receive adapter to receive WCF service requests through the HTTP or HTTPS protocol.</span></span> <span data-ttu-id="ed355-136">WCF-WSHttp 受信アダプタを使用する受信場所は、一方向または要求 - 応答 (双方向) として構成できます。</span><span class="sxs-lookup"><span data-stu-id="ed355-136">A receive location that uses the WCF-WSHttp receive adapter can be configured as one-way or request-response (two-way).</span></span>  
  
 <span data-ttu-id="ed355-137">**Wcf-wshttp 送信アダプター**</span><span class="sxs-lookup"><span data-stu-id="ed355-137">**WCF-WSHttp Send Adapter**</span></span>  
  
 <span data-ttu-id="ed355-138">WCF-WSHttp 送信アダプタを使用すると、HTTP プロトコルまたは HTTPS プロトコルを使用して、型宣言が不要なコントラクトを介して WCF サービスを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="ed355-138">You use the WCF-WSHttp send adapter to call a WCF service through the typeless contract by using the HTTP or HTTPS protocol.</span></span>  
  
 <span data-ttu-id="ed355-139">WCF の詳細については、受信し送信アダプターを参照してください[WCF アダプタは何ですか?](../core/what-are-the-wcf-adapters.md)です。</span><span class="sxs-lookup"><span data-stu-id="ed355-139">For more information about WCF receive and send adapters, see [What Are the WCF Adapters?](../core/what-are-the-wcf-adapters.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed355-140">参照</span><span class="sxs-lookup"><span data-stu-id="ed355-140">See Also</span></span>  
 <span data-ttu-id="ed355-141">[Wcf-wshttp アダプタを構成します。](../core/configuring-the-wcf-wshttp-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="ed355-141">[Configuring the WCF-WSHttp Adapter](../core/configuring-the-wcf-wshttp-adapter.md) </span></span>  
 [<span data-ttu-id="ed355-142">WCF アダプタ</span><span class="sxs-lookup"><span data-stu-id="ed355-142">WCF Adapters</span></span>](../core/wcf-adapters.md)