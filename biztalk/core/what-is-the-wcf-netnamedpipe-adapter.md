---
title: Wcf-netnamedpipe アダプターとは何ですか。 | Microsoft Docs
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
ms.openlocfilehash: 01672c8babf30c99b8ba4d31069c836a46b18630
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65242745"
---
# <a name="what-is-the-wcf-netnamedpipe-adapter"></a><span data-ttu-id="7e847-103">Wcf-netnamedpipe アダプターとは何ですか。</span><span class="sxs-lookup"><span data-stu-id="7e847-103">What Is the WCF-NetNamedPipe Adapter?</span></span>
<span data-ttu-id="7e847-104">Wcf-netnamedpipe アダプターは、環境でサービスとクライアントの両方が WCF ベースで同じコンピューター上のプロセス間通信を提供します。</span><span class="sxs-lookup"><span data-stu-id="7e847-104">The WCF-NetNamedPipe adapter provides cross-process communication on the same computer in an environment in which both services and clients are WCF based.</span></span> <span data-ttu-id="7e847-105">SOAP の信頼性とトランザクションの機能へのフル アクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="7e847-105">It provides full access to SOAP reliability and transaction features.</span></span> <span data-ttu-id="7e847-106">アダプターが、名前付きパイプ トランスポートを使用し、メッセージはバイナリ エンコードします。</span><span class="sxs-lookup"><span data-stu-id="7e847-106">The adapter uses the named pipe transport, and messages have binary encoding.</span></span> <span data-ttu-id="7e847-107">このアダプターは、コンピュータ間通信で使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="7e847-107">This adapter cannot be used in cross-computer communication.</span></span>  
  
 <span data-ttu-id="7e847-108">次の表では、Wcf-netnamedpipe アダプタの特性をまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="7e847-108">The following table summarizes the characteristics for the WCF-NetNamedPipe adapter.</span></span>  
  
|<span data-ttu-id="7e847-109">説明</span><span class="sxs-lookup"><span data-stu-id="7e847-109">Description</span></span>|<span data-ttu-id="7e847-110">特性</span><span class="sxs-lookup"><span data-stu-id="7e847-110">Characteristic</span></span>|  
|-----------------|--------------------|  
|<span data-ttu-id="7e847-111">相互運用性レベル</span><span class="sxs-lookup"><span data-stu-id="7e847-111">Interoperability level</span></span>|<span data-ttu-id="7e847-112">.NET プロファイル</span><span class="sxs-lookup"><span data-stu-id="7e847-112">.NET-Profile</span></span>|  
|<span data-ttu-id="7e847-113">[メッセージ エンコード]</span><span class="sxs-lookup"><span data-stu-id="7e847-113">Message encoding</span></span>|<span data-ttu-id="7e847-114">Binary</span><span class="sxs-lookup"><span data-stu-id="7e847-114">Binary</span></span>|  
|<span data-ttu-id="7e847-115">[境界]</span><span class="sxs-lookup"><span data-stu-id="7e847-115">Boundary</span></span>|<span data-ttu-id="7e847-116">プロセス間</span><span class="sxs-lookup"><span data-stu-id="7e847-116">Cross-process</span></span>|  
|<span data-ttu-id="7e847-117">トランスポート プロトコル</span><span class="sxs-lookup"><span data-stu-id="7e847-117">Transport protocol</span></span>|<span data-ttu-id="7e847-118">名前付きパイプ</span><span class="sxs-lookup"><span data-stu-id="7e847-118">Named pipe</span></span>|  
|<span data-ttu-id="7e847-119">[セキュリティ モード]</span><span class="sxs-lookup"><span data-stu-id="7e847-119">Security mode</span></span>|<span data-ttu-id="7e847-120">[なし] とトランスポート</span><span class="sxs-lookup"><span data-stu-id="7e847-120">None and Transport</span></span>|  
|<span data-ttu-id="7e847-121">クライアント認証のメカニズム</span><span class="sxs-lookup"><span data-stu-id="7e847-121">Client authentication mechanism</span></span>|<span data-ttu-id="7e847-122">トランスポート セキュリティとメッセージ セキュリティ</span><span class="sxs-lookup"><span data-stu-id="7e847-122">Transport Security and Message Security</span></span>|  
|<span data-ttu-id="7e847-123">WS-ReliableMessaging のサポート</span><span class="sxs-lookup"><span data-stu-id="7e847-123">Support for WS-ReliableMessaging</span></span>|<span data-ttu-id="7e847-124">いいえ</span><span class="sxs-lookup"><span data-stu-id="7e847-124">No</span></span>|  
|<span data-ttu-id="7e847-125">WS-AtomicTransaction のサポート</span><span class="sxs-lookup"><span data-stu-id="7e847-125">Support for WS-AtomicTransaction</span></span>|<span data-ttu-id="7e847-126">はい</span><span class="sxs-lookup"><span data-stu-id="7e847-126">Yes</span></span>|  
|<span data-ttu-id="7e847-127">一方向メッセージングのサポート</span><span class="sxs-lookup"><span data-stu-id="7e847-127">Support for one-way messaging</span></span>|<span data-ttu-id="7e847-128">はい</span><span class="sxs-lookup"><span data-stu-id="7e847-128">Yes</span></span>|  
|<span data-ttu-id="7e847-129">双方向メッセージングのサポート</span><span class="sxs-lookup"><span data-stu-id="7e847-129">Support for two-way messaging</span></span>|<span data-ttu-id="7e847-130">はい</span><span class="sxs-lookup"><span data-stu-id="7e847-130">Yes</span></span>|  
|<span data-ttu-id="7e847-131">受信アダプタのホストの種類</span><span class="sxs-lookup"><span data-stu-id="7e847-131">Host type for receive adapter</span></span>|<span data-ttu-id="7e847-132">インプロセス</span><span class="sxs-lookup"><span data-stu-id="7e847-132">In-process</span></span>|  
|<span data-ttu-id="7e847-133">送信アダプタのホストの種類</span><span class="sxs-lookup"><span data-stu-id="7e847-133">Host type for send adapter</span></span>|<span data-ttu-id="7e847-134">インプロセス</span><span class="sxs-lookup"><span data-stu-id="7e847-134">In-process</span></span>|  
  
 <span data-ttu-id="7e847-135">Wcf-netnamedpipe アダプターは、2 つのアダプターで構成されます-受信アダプタと送信アダプター。</span><span class="sxs-lookup"><span data-stu-id="7e847-135">The WCF-NetNamedPipe adapter consists of two adapters—a receive adapter and a send adapter.</span></span>  
  
 <span data-ttu-id="7e847-136">**Wcf-netnamedpipe 受信アダプター**</span><span class="sxs-lookup"><span data-stu-id="7e847-136">**WCF-NetNamedPipe Receive Adapter**</span></span>  
  
 <span data-ttu-id="7e847-137">使用して、Wcf-netnamedpipe 受信アダプタは、名前付きパイプ トランスポート経由で WCF サービス要求を受信します。</span><span class="sxs-lookup"><span data-stu-id="7e847-137">You use the WCF-NetNamedPipe receive adapter to receive WCF service requests over the named pipe transport.</span></span> <span data-ttu-id="7e847-138">Wcf-netnamedpipe 受信アダプタを使用する受信場所は、一方向として構成できますまたは要求-応答 (双方向)。</span><span class="sxs-lookup"><span data-stu-id="7e847-138">A receive location that uses the WCF-NetNamedPipe receive adapter can be configured as one-way or request-response (two-way).</span></span>  
  
 <span data-ttu-id="7e847-139">**Wcf-netnamedpipe 送信アダプター**</span><span class="sxs-lookup"><span data-stu-id="7e847-139">**WCF-NetNamedPipe Send Adapter**</span></span>  
  
 <span data-ttu-id="7e847-140">Wcf-netnamedpipe 送信アダプターを使用して、名前付きパイプ トランスポート経由で型宣言不要なコントラクトを介して WCF サービスを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="7e847-140">You use the WCF-NetNamedPipe send adapter to call a WCF service through the typeless contract over the named pipe transport.</span></span>  
  
 <span data-ttu-id="7e847-141">WCF の詳細については、受信し送信アダプターを参照してください[WCF アダプタは何ですか?](../core/what-are-the-wcf-adapters.md)します。</span><span class="sxs-lookup"><span data-stu-id="7e847-141">For more information about WCF receive and send adapters, see [What Are the WCF Adapters?](../core/what-are-the-wcf-adapters.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e847-142">参照</span><span class="sxs-lookup"><span data-stu-id="7e847-142">See Also</span></span>  
 <span data-ttu-id="7e847-143">[Wcf-netnamedpipe アダプターの構成](../core/configuring-the-wcf-netnamedpipe-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="7e847-143">[Configuring the WCF-NetNamedPipe Adapter](../core/configuring-the-wcf-netnamedpipe-adapter.md) </span></span>  
 [<span data-ttu-id="7e847-144">WCF アダプター</span><span class="sxs-lookup"><span data-stu-id="7e847-144">WCF Adapters</span></span>](../core/wcf-adapters.md)