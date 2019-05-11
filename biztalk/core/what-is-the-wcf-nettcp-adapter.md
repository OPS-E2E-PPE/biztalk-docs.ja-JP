---
title: Wcf-nettcp アダプターとは何ですか。 | Microsoft Docs
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
ms.openlocfilehash: da209ab45dbb9458cd6be0d2e988fac7ea9270f9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65242846"
---
# <a name="what-is-the-wcf-nettcp-adapter"></a><span data-ttu-id="71f5d-103">Wcf-nettcp アダプターとは何ですか。</span><span class="sxs-lookup"><span data-stu-id="71f5d-103">What Is the WCF-NetTcp Adapter?</span></span>
<span data-ttu-id="71f5d-104">Wcf-nettcp アダプターは、環境でサービスとクライアントの両方が WCF ベースで接続されているコンピュータ間またはプロセス間の通信を提供します。</span><span class="sxs-lookup"><span data-stu-id="71f5d-104">The WCF-NetTcp adapter provides connected cross-computer or cross-process communication in an environment in which both services and clients are WCF based.</span></span> <span data-ttu-id="71f5d-105">このアダプタからは、SOAP セキュリティ、信頼性、およびトランザクションの各機能にフル アクセスできます。</span><span class="sxs-lookup"><span data-stu-id="71f5d-105">It provides full access to SOAP security, reliability, and transaction features.</span></span> <span data-ttu-id="71f5d-106">このアダプタは、TCP トランスポートを使用し、メッセージではバイナリ エンコードを使用します。</span><span class="sxs-lookup"><span data-stu-id="71f5d-106">This adapter uses the TCP transport, and messages have binary encoding.</span></span>  
  
 <span data-ttu-id="71f5d-107">次の表では、Wcf-nettcp アダプタの特性をまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="71f5d-107">The following table summarizes the characteristics of the WCF-NetTcp adapter.</span></span>  
  
|<span data-ttu-id="71f5d-108">説明</span><span class="sxs-lookup"><span data-stu-id="71f5d-108">Description</span></span>|<span data-ttu-id="71f5d-109">特性</span><span class="sxs-lookup"><span data-stu-id="71f5d-109">Characteristic</span></span>|  
|-----------------|--------------------|  
|<span data-ttu-id="71f5d-110">相互運用性レベル</span><span class="sxs-lookup"><span data-stu-id="71f5d-110">Interoperability level</span></span>|<span data-ttu-id="71f5d-111">.NET プロファイル</span><span class="sxs-lookup"><span data-stu-id="71f5d-111">.NET-Profile</span></span>|  
|<span data-ttu-id="71f5d-112">[メッセージ エンコード]</span><span class="sxs-lookup"><span data-stu-id="71f5d-112">Message encoding</span></span>|<span data-ttu-id="71f5d-113">Binary</span><span class="sxs-lookup"><span data-stu-id="71f5d-113">Binary</span></span>|  
|<span data-ttu-id="71f5d-114">[境界]</span><span class="sxs-lookup"><span data-stu-id="71f5d-114">Boundary</span></span>|<span data-ttu-id="71f5d-115">コンピュータ間またはプロセス間</span><span class="sxs-lookup"><span data-stu-id="71f5d-115">Cross-computer or cross-process</span></span>|  
|<span data-ttu-id="71f5d-116">トランスポート プロトコル</span><span class="sxs-lookup"><span data-stu-id="71f5d-116">Transport protocol</span></span>|<span data-ttu-id="71f5d-117">TCP</span><span class="sxs-lookup"><span data-stu-id="71f5d-117">TCP</span></span>|  
|<span data-ttu-id="71f5d-118">[セキュリティ モード]</span><span class="sxs-lookup"><span data-stu-id="71f5d-118">Security mode</span></span>|<span data-ttu-id="71f5d-119">None、メッセージ、トランスポート、および TransportWithMessageCredential します。</span><span class="sxs-lookup"><span data-stu-id="71f5d-119">None, Message, Transport, and TransportWithMessageCredential.</span></span>|  
|<span data-ttu-id="71f5d-120">クライアント認証のメカニズム</span><span class="sxs-lookup"><span data-stu-id="71f5d-120">Client authentication mechanism</span></span>|<span data-ttu-id="71f5d-121">トランスポート セキュリティとメッセージ セキュリティ</span><span class="sxs-lookup"><span data-stu-id="71f5d-121">Transport Security and Message Security</span></span>|  
|<span data-ttu-id="71f5d-122">WS-ReliableMessaging のサポート</span><span class="sxs-lookup"><span data-stu-id="71f5d-122">Support for WS-ReliableMessaging</span></span>|<span data-ttu-id="71f5d-123">いいえ</span><span class="sxs-lookup"><span data-stu-id="71f5d-123">No</span></span>|  
|<span data-ttu-id="71f5d-124">WS-AtomicTransaction のサポート</span><span class="sxs-lookup"><span data-stu-id="71f5d-124">Support for WS-AtomicTransaction</span></span>|<span data-ttu-id="71f5d-125">はい</span><span class="sxs-lookup"><span data-stu-id="71f5d-125">Yes</span></span>|  
|<span data-ttu-id="71f5d-126">一方向メッセージングのサポート</span><span class="sxs-lookup"><span data-stu-id="71f5d-126">Support for one-way messaging</span></span>|<span data-ttu-id="71f5d-127">はい</span><span class="sxs-lookup"><span data-stu-id="71f5d-127">Yes</span></span>|  
|<span data-ttu-id="71f5d-128">双方向メッセージングのサポート</span><span class="sxs-lookup"><span data-stu-id="71f5d-128">Support for two-way messaging</span></span>|<span data-ttu-id="71f5d-129">はい</span><span class="sxs-lookup"><span data-stu-id="71f5d-129">Yes</span></span>|  
|<span data-ttu-id="71f5d-130">受信アダプタのホストの種類</span><span class="sxs-lookup"><span data-stu-id="71f5d-130">Host type for receive adapter</span></span>|<span data-ttu-id="71f5d-131">インプロセス</span><span class="sxs-lookup"><span data-stu-id="71f5d-131">In-process</span></span>|  
|<span data-ttu-id="71f5d-132">送信アダプタのホストの種類</span><span class="sxs-lookup"><span data-stu-id="71f5d-132">Host type for send adapter</span></span>|<span data-ttu-id="71f5d-133">インプロセス</span><span class="sxs-lookup"><span data-stu-id="71f5d-133">In-process</span></span>|  
  
 <span data-ttu-id="71f5d-134">Wcf-nettcp アダプターは、2 つのアダプターで構成されます-受信アダプタと送信アダプター。</span><span class="sxs-lookup"><span data-stu-id="71f5d-134">The WCF-NetTcp adapter consists of two adapters—a receive adapter and a send adapter.</span></span>  
  
 <span data-ttu-id="71f5d-135">**Wcf-nettcp 受信アダプター**</span><span class="sxs-lookup"><span data-stu-id="71f5d-135">**WCF-NetTcp Receive Adapter**</span></span>  
  
 <span data-ttu-id="71f5d-136">WCF-NetTcp を使用する受信アダプタは、TCP プロトコルを介して WCF サービス要求を受信します。</span><span class="sxs-lookup"><span data-stu-id="71f5d-136">You use the WCF-NetTcp receive adapter to receive WCF service requests through the TCP protocol.</span></span> <span data-ttu-id="71f5d-137">Wcf-nettcp 受信アダプタを使用する受信場所は、一方向として構成できますまたは要求-応答 (双方向)。</span><span class="sxs-lookup"><span data-stu-id="71f5d-137">A receive location that uses the WCF-NetTcp receive adapter can be configured as one-way or request-response (two-way).</span></span>  
  
 <span data-ttu-id="71f5d-138">**Wcf-nettcp 送信アダプター**</span><span class="sxs-lookup"><span data-stu-id="71f5d-138">**WCF-NetTcp Send Adapter**</span></span>  
  
 <span data-ttu-id="71f5d-139">Wcf-nettcp 送信アダプターを使用して、TCP プロトコルを使用して、型宣言不要なコントラクトを介して WCF サービスを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="71f5d-139">You use the WCF-NetTcp send adapter to call a WCF service through the typeless contract by using the TCP protocol.</span></span>  
  
 <span data-ttu-id="71f5d-140">WCF の詳細については、受信し送信アダプターを参照してください[WCF アダプタは何ですか?](../core/what-are-the-wcf-adapters.md)します。</span><span class="sxs-lookup"><span data-stu-id="71f5d-140">For more information about WCF receive and send adapters, see [What Are the WCF Adapters?](../core/what-are-the-wcf-adapters.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71f5d-141">参照</span><span class="sxs-lookup"><span data-stu-id="71f5d-141">See Also</span></span>  
 <span data-ttu-id="71f5d-142">[Wcf-nettcp アダプターを構成します。](../core/configuring-the-wcf-nettcp-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="71f5d-142">[Configuring the WCF-NetTcp Adapter](../core/configuring-the-wcf-nettcp-adapter.md) </span></span>  
 [<span data-ttu-id="71f5d-143">WCF アダプター</span><span class="sxs-lookup"><span data-stu-id="71f5d-143">WCF Adapters</span></span>](../core/wcf-adapters.md)