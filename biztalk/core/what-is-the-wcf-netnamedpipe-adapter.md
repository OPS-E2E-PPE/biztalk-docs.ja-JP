---
title: Wcf-netnamedpipe アダプタとは何ですか。 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF-NetNamedPipe adapters, about WCF-NetNamedPipe adapters
ms.assetid: b9f84256-e49d-4ee2-b0fa-d3f692ade1d4
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 43c73a670139690c4a27d4784c6ad23225492f17
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="what-is-the-wcf-netnamedpipe-adapter"></a><span data-ttu-id="02373-103">Wcf-netnamedpipe アダプタとは何ですか。</span><span class="sxs-lookup"><span data-stu-id="02373-103">What Is the WCF-NetNamedPipe Adapter?</span></span>
<span data-ttu-id="02373-104">WCF-NetNamedPipe アダプタは、サービスとクライアントの両方が WCF ベースである環境において、同一コンピュータ上でのプロセス間通信を可能にします。</span><span class="sxs-lookup"><span data-stu-id="02373-104">The WCF-NetNamedPipe adapter provides cross-process communication on the same computer in an environment in which both services and clients are WCF based.</span></span> <span data-ttu-id="02373-105">このアダプタからは、SOAP の信頼性機能とトランザクション機能にフル アクセスできます。</span><span class="sxs-lookup"><span data-stu-id="02373-105">It provides full access to SOAP reliability and transaction features.</span></span> <span data-ttu-id="02373-106">このアダプタでは名前付きパイプ トランスポートが使用され、メッセージではバイナリ エンコードが使用されます。</span><span class="sxs-lookup"><span data-stu-id="02373-106">The adapter uses the named pipe transport, and messages have binary encoding.</span></span> <span data-ttu-id="02373-107">コンピュータ間通信ではこのアダプタを使用できません。</span><span class="sxs-lookup"><span data-stu-id="02373-107">This adapter cannot be used in cross-computer communication.</span></span>  
  
 <span data-ttu-id="02373-108">次の表に、WCF-NetNamedPipe アダプタの特性をまとめます。</span><span class="sxs-lookup"><span data-stu-id="02373-108">The following table summarizes the characteristics for the WCF-NetNamedPipe adapter.</span></span>  
  
|<span data-ttu-id="02373-109">Description</span><span class="sxs-lookup"><span data-stu-id="02373-109">Description</span></span>|<span data-ttu-id="02373-110">特性</span><span class="sxs-lookup"><span data-stu-id="02373-110">Characteristic</span></span>|  
|-----------------|--------------------|  
|<span data-ttu-id="02373-111">相互運用性レベル</span><span class="sxs-lookup"><span data-stu-id="02373-111">Interoperability level</span></span>|<span data-ttu-id="02373-112">.NET プロファイル</span><span class="sxs-lookup"><span data-stu-id="02373-112">.NET-Profile</span></span>|  
|<span data-ttu-id="02373-113">[メッセージ エンコード]</span><span class="sxs-lookup"><span data-stu-id="02373-113">Message encoding</span></span>|<span data-ttu-id="02373-114">Binary</span><span class="sxs-lookup"><span data-stu-id="02373-114">Binary</span></span>|  
|<span data-ttu-id="02373-115">[境界]</span><span class="sxs-lookup"><span data-stu-id="02373-115">Boundary</span></span>|<span data-ttu-id="02373-116">プロセス間</span><span class="sxs-lookup"><span data-stu-id="02373-116">Cross-process</span></span>|  
|<span data-ttu-id="02373-117">トランスポート プロトコル</span><span class="sxs-lookup"><span data-stu-id="02373-117">Transport protocol</span></span>|<span data-ttu-id="02373-118">名前付きパイプ</span><span class="sxs-lookup"><span data-stu-id="02373-118">Named pipe</span></span>|  
|<span data-ttu-id="02373-119">[セキュリティ モード]</span><span class="sxs-lookup"><span data-stu-id="02373-119">Security mode</span></span>|<span data-ttu-id="02373-120">なしおよびトランスポート</span><span class="sxs-lookup"><span data-stu-id="02373-120">None and Transport</span></span>|  
|<span data-ttu-id="02373-121">クライアント認証のメカニズム</span><span class="sxs-lookup"><span data-stu-id="02373-121">Client authentication mechanism</span></span>|<span data-ttu-id="02373-122">トランスポート セキュリティとメッセージ セキュリティ</span><span class="sxs-lookup"><span data-stu-id="02373-122">Transport Security and Message Security</span></span>|  
|<span data-ttu-id="02373-123">WS-ReliableMessaging のサポート</span><span class="sxs-lookup"><span data-stu-id="02373-123">Support for WS-ReliableMessaging</span></span>|<span data-ttu-id="02373-124">不可</span><span class="sxs-lookup"><span data-stu-id="02373-124">No</span></span>|  
|<span data-ttu-id="02373-125">WS-AtomicTransaction のサポート</span><span class="sxs-lookup"><span data-stu-id="02373-125">Support for WS-AtomicTransaction</span></span>|<span data-ttu-id="02373-126">はい</span><span class="sxs-lookup"><span data-stu-id="02373-126">Yes</span></span>|  
|<span data-ttu-id="02373-127">一方向メッセージングのサポート</span><span class="sxs-lookup"><span data-stu-id="02373-127">Support for one-way messaging</span></span>|<span data-ttu-id="02373-128">はい</span><span class="sxs-lookup"><span data-stu-id="02373-128">Yes</span></span>|  
|<span data-ttu-id="02373-129">双方向メッセージングのサポート</span><span class="sxs-lookup"><span data-stu-id="02373-129">Support for two-way messaging</span></span>|<span data-ttu-id="02373-130">はい</span><span class="sxs-lookup"><span data-stu-id="02373-130">Yes</span></span>|  
|<span data-ttu-id="02373-131">受信アダプタのホストの種類</span><span class="sxs-lookup"><span data-stu-id="02373-131">Host type for receive adapter</span></span>|<span data-ttu-id="02373-132">インプロセス</span><span class="sxs-lookup"><span data-stu-id="02373-132">In-process</span></span>|  
|<span data-ttu-id="02373-133">送信アダプタのホストの種類</span><span class="sxs-lookup"><span data-stu-id="02373-133">Host type for send adapter</span></span>|<span data-ttu-id="02373-134">インプロセス</span><span class="sxs-lookup"><span data-stu-id="02373-134">In-process</span></span>|  
  
 <span data-ttu-id="02373-135">WCF-NetNamedPipe アダプタは、受信アダプタと送信アダプタの 2 つのアダプタで構成されます。</span><span class="sxs-lookup"><span data-stu-id="02373-135">The WCF-NetNamedPipe adapter consists of two adapters—a receive adapter and a send adapter.</span></span>  
  
 <span data-ttu-id="02373-136">**Wcf-netnamedpipe 受信アダプター**</span><span class="sxs-lookup"><span data-stu-id="02373-136">**WCF-NetNamedPipe Receive Adapter**</span></span>  
  
 <span data-ttu-id="02373-137">WCF-NetNamedPipe 受信アダプタは、名前付きパイプ トランスポート経由で WCF サービス要求を受信するのに使用します。</span><span class="sxs-lookup"><span data-stu-id="02373-137">You use the WCF-NetNamedPipe receive adapter to receive WCF service requests over the named pipe transport.</span></span> <span data-ttu-id="02373-138">WCF-NetNamedPipe 受信アダプタを使用する受信場所は、一方向または要求 - 応答 (双方向) として構成できます。</span><span class="sxs-lookup"><span data-stu-id="02373-138">A receive location that uses the WCF-NetNamedPipe receive adapter can be configured as one-way or request-response (two-way).</span></span>  
  
 <span data-ttu-id="02373-139">**Wcf-netnamedpipe 送信アダプター**</span><span class="sxs-lookup"><span data-stu-id="02373-139">**WCF-NetNamedPipe Send Adapter**</span></span>  
  
 <span data-ttu-id="02373-140">WCF-NetNamedPipe 送信アダプタは、名前付きパイプ トランスポート経由で型宣言が不要なコントラクトを使用して WCF サービスを呼び出すのに使用します。</span><span class="sxs-lookup"><span data-stu-id="02373-140">You use the WCF-NetNamedPipe send adapter to call a WCF service through the typeless contract over the named pipe transport.</span></span>  
  
 <span data-ttu-id="02373-141">WCF の詳細については、受信し送信アダプターを参照してください[WCF アダプタは何ですか?](../core/what-are-the-wcf-adapters.md)です。</span><span class="sxs-lookup"><span data-stu-id="02373-141">For more information about WCF receive and send adapters, see [What Are the WCF Adapters?](../core/what-are-the-wcf-adapters.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02373-142">参照</span><span class="sxs-lookup"><span data-stu-id="02373-142">See Also</span></span>  
 <span data-ttu-id="02373-143">[Wcf-netnamedpipe アダプタを構成します。](../core/configuring-the-wcf-netnamedpipe-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="02373-143">[Configuring the WCF-NetNamedPipe Adapter](../core/configuring-the-wcf-netnamedpipe-adapter.md) </span></span>  
 [<span data-ttu-id="02373-144">WCF アダプタ</span><span class="sxs-lookup"><span data-stu-id="02373-144">WCF Adapters</span></span>](../core/wcf-adapters.md)