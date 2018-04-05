---
title: WCF-NetTcp アダプタについて | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF-NetTcp adapters, about WCF-NetTcp adapters
ms.assetid: 94dc24df-19a1-4701-9012-59d05b0c8abd
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a741d3a4d7b7bcc80405d0fc25e37a31860523b9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="what-is-the-wcf-nettcp-adapter"></a><span data-ttu-id="65a5f-103">WCF-NetTcp アダプタについて</span><span class="sxs-lookup"><span data-stu-id="65a5f-103">What Is the WCF-NetTcp Adapter?</span></span>
<span data-ttu-id="65a5f-104">WCF-NetTcp アダプタは、サービスとクライアントの両方が WCF ベースである環境において、コンピュータ間またはプロセス間の接続通信を実現します。</span><span class="sxs-lookup"><span data-stu-id="65a5f-104">The WCF-NetTcp adapter provides connected cross-computer or cross-process communication in an environment in which both services and clients are WCF based.</span></span> <span data-ttu-id="65a5f-105">このアダプタからは、SOAP セキュリティ、信頼性、およびトランザクションの各機能にフル アクセスできます。</span><span class="sxs-lookup"><span data-stu-id="65a5f-105">It provides full access to SOAP security, reliability, and transaction features.</span></span> <span data-ttu-id="65a5f-106">このアダプタは、TCP トランスポートを使用し、メッセージではバイナリ エンコードを使用します。</span><span class="sxs-lookup"><span data-stu-id="65a5f-106">This adapter uses the TCP transport, and messages have binary encoding.</span></span>  
  
 <span data-ttu-id="65a5f-107">次の表に、WCF-NetTcp アダプタの特性をまとめます。</span><span class="sxs-lookup"><span data-stu-id="65a5f-107">The following table summarizes the characteristics of the WCF-NetTcp adapter.</span></span>  
  
|<span data-ttu-id="65a5f-108">Description</span><span class="sxs-lookup"><span data-stu-id="65a5f-108">Description</span></span>|<span data-ttu-id="65a5f-109">特性</span><span class="sxs-lookup"><span data-stu-id="65a5f-109">Characteristic</span></span>|  
|-----------------|--------------------|  
|<span data-ttu-id="65a5f-110">相互運用性レベル</span><span class="sxs-lookup"><span data-stu-id="65a5f-110">Interoperability level</span></span>|<span data-ttu-id="65a5f-111">.NET プロファイル</span><span class="sxs-lookup"><span data-stu-id="65a5f-111">.NET-Profile</span></span>|  
|<span data-ttu-id="65a5f-112">[メッセージ エンコード]</span><span class="sxs-lookup"><span data-stu-id="65a5f-112">Message encoding</span></span>|<span data-ttu-id="65a5f-113">Binary</span><span class="sxs-lookup"><span data-stu-id="65a5f-113">Binary</span></span>|  
|<span data-ttu-id="65a5f-114">[境界]</span><span class="sxs-lookup"><span data-stu-id="65a5f-114">Boundary</span></span>|<span data-ttu-id="65a5f-115">コンピュータ間またはプロセス間</span><span class="sxs-lookup"><span data-stu-id="65a5f-115">Cross-computer or cross-process</span></span>|  
|<span data-ttu-id="65a5f-116">トランスポート プロトコル</span><span class="sxs-lookup"><span data-stu-id="65a5f-116">Transport protocol</span></span>|<span data-ttu-id="65a5f-117">TCP</span><span class="sxs-lookup"><span data-stu-id="65a5f-117">TCP</span></span>|  
|<span data-ttu-id="65a5f-118">[セキュリティ モード]</span><span class="sxs-lookup"><span data-stu-id="65a5f-118">Security mode</span></span>|<span data-ttu-id="65a5f-119">None、Message、Transport、および TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="65a5f-119">None, Message, Transport, and TransportWithMessageCredential.</span></span>|  
|<span data-ttu-id="65a5f-120">クライアント認証のメカニズム</span><span class="sxs-lookup"><span data-stu-id="65a5f-120">Client authentication mechanism</span></span>|<span data-ttu-id="65a5f-121">トランスポート セキュリティとメッセージ セキュリティ</span><span class="sxs-lookup"><span data-stu-id="65a5f-121">Transport Security and Message Security</span></span>|  
|<span data-ttu-id="65a5f-122">WS-ReliableMessaging のサポート</span><span class="sxs-lookup"><span data-stu-id="65a5f-122">Support for WS-ReliableMessaging</span></span>|<span data-ttu-id="65a5f-123">不可</span><span class="sxs-lookup"><span data-stu-id="65a5f-123">No</span></span>|  
|<span data-ttu-id="65a5f-124">WS-AtomicTransaction のサポート</span><span class="sxs-lookup"><span data-stu-id="65a5f-124">Support for WS-AtomicTransaction</span></span>|<span data-ttu-id="65a5f-125">はい</span><span class="sxs-lookup"><span data-stu-id="65a5f-125">Yes</span></span>|  
|<span data-ttu-id="65a5f-126">一方向メッセージングのサポート</span><span class="sxs-lookup"><span data-stu-id="65a5f-126">Support for one-way messaging</span></span>|<span data-ttu-id="65a5f-127">はい</span><span class="sxs-lookup"><span data-stu-id="65a5f-127">Yes</span></span>|  
|<span data-ttu-id="65a5f-128">双方向メッセージングのサポート</span><span class="sxs-lookup"><span data-stu-id="65a5f-128">Support for two-way messaging</span></span>|<span data-ttu-id="65a5f-129">はい</span><span class="sxs-lookup"><span data-stu-id="65a5f-129">Yes</span></span>|  
|<span data-ttu-id="65a5f-130">受信アダプタのホストの種類</span><span class="sxs-lookup"><span data-stu-id="65a5f-130">Host type for receive adapter</span></span>|<span data-ttu-id="65a5f-131">インプロセス</span><span class="sxs-lookup"><span data-stu-id="65a5f-131">In-process</span></span>|  
|<span data-ttu-id="65a5f-132">送信アダプタのホストの種類</span><span class="sxs-lookup"><span data-stu-id="65a5f-132">Host type for send adapter</span></span>|<span data-ttu-id="65a5f-133">インプロセス</span><span class="sxs-lookup"><span data-stu-id="65a5f-133">In-process</span></span>|  
  
 <span data-ttu-id="65a5f-134">WCF-NetTcp アダプタは、2 つのアダプタ (受信アダプタと送信アダプタ) で構成されます。</span><span class="sxs-lookup"><span data-stu-id="65a5f-134">The WCF-NetTcp adapter consists of two adapters—a receive adapter and a send adapter.</span></span>  
  
 <span data-ttu-id="65a5f-135">**Wcf-nettcp 受信アダプター**</span><span class="sxs-lookup"><span data-stu-id="65a5f-135">**WCF-NetTcp Receive Adapter**</span></span>  
  
 <span data-ttu-id="65a5f-136">WCF-NetTcp 受信アダプタを使用すると、TCP プロトコルを介して WCF サービス要求を受信できます。</span><span class="sxs-lookup"><span data-stu-id="65a5f-136">You use the WCF-NetTcp receive adapter to receive WCF service requests through the TCP protocol.</span></span> <span data-ttu-id="65a5f-137">WCF-NetTcp 受信アダプタを使用する受信場所は、一方向または要求 - 応答 (双方向) として構成できます。</span><span class="sxs-lookup"><span data-stu-id="65a5f-137">A receive location that uses the WCF-NetTcp receive adapter can be configured as one-way or request-response (two-way).</span></span>  
  
 <span data-ttu-id="65a5f-138">**Wcf-nettcp 送信アダプター**</span><span class="sxs-lookup"><span data-stu-id="65a5f-138">**WCF-NetTcp Send Adapter**</span></span>  
  
 <span data-ttu-id="65a5f-139">WCF-NetTcp 送信アダプタを使用すると、TCP プロトコルを使用して、型宣言が不要なコントラクトを介して WCF サービスを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="65a5f-139">You use the WCF-NetTcp send adapter to call a WCF service through the typeless contract by using the TCP protocol.</span></span>  
  
 <span data-ttu-id="65a5f-140">WCF の詳細については、受信し送信アダプターを参照してください[WCF アダプタは何ですか?](../core/what-are-the-wcf-adapters.md)です。</span><span class="sxs-lookup"><span data-stu-id="65a5f-140">For more information about WCF receive and send adapters, see [What Are the WCF Adapters?](../core/what-are-the-wcf-adapters.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65a5f-141">参照</span><span class="sxs-lookup"><span data-stu-id="65a5f-141">See Also</span></span>  
 <span data-ttu-id="65a5f-142">[Wcf-nettcp アダプターを構成します。](../core/configuring-the-wcf-nettcp-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="65a5f-142">[Configuring the WCF-NetTcp Adapter](../core/configuring-the-wcf-nettcp-adapter.md) </span></span>  
 [<span data-ttu-id="65a5f-143">WCF アダプタ</span><span class="sxs-lookup"><span data-stu-id="65a5f-143">WCF Adapters</span></span>](../core/wcf-adapters.md)