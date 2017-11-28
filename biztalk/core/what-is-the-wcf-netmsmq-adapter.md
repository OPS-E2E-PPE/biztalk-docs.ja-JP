---
title: "WCF-NetMsmq アダプタについて | Microsoft Docs"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: WCF-NetMsmq adapters, about WCF-NetMsmq adapters
ms.assetid: 506c5e2d-6cbe-4788-8e37-49d009dc559a
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1008cc7178c38532f1781890080eacf4b5dfb56c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="what-is-the-wcf-netmsmq-adapter"></a><span data-ttu-id="e3968-103">WCF-NetMsmq アダプタについて</span><span class="sxs-lookup"><span data-stu-id="e3968-103">What Is the WCF-NetMsmq Adapter?</span></span>
<span data-ttu-id="e3968-104">WCF-NetMsmq アダプタは、サービスとクライアントの両方が WCF ベースである環境でキュー テクノロジを使用して、接続が切断されたコンピュータ間の通信を実現します。</span><span class="sxs-lookup"><span data-stu-id="e3968-104">The WCF-NetMsmq adapter provides disconnected cross-computer communication by using queuing technology in an environment where both the services and clients are WCF based.</span></span> <span data-ttu-id="e3968-105">このアダプタはメッセージ キュー (MSMQ) トランスポートを使用し、メッセージではバイナリ エンコードを使用します。</span><span class="sxs-lookup"><span data-stu-id="e3968-105">It uses the Message Queuing (MSMQ) transport, and messages have binary encoding.</span></span>  
  
 <span data-ttu-id="e3968-106">次の表に、WCF-NetMsmq アダプタの特性をまとめます。</span><span class="sxs-lookup"><span data-stu-id="e3968-106">The following table summarizes the characteristics for the WCF-NetMsmq adapter.</span></span>  
  
|<span data-ttu-id="e3968-107">Description</span><span class="sxs-lookup"><span data-stu-id="e3968-107">Description</span></span>|<span data-ttu-id="e3968-108">特性</span><span class="sxs-lookup"><span data-stu-id="e3968-108">Characteristic</span></span>|  
|-----------------|--------------------|  
|<span data-ttu-id="e3968-109">相互運用性レベル</span><span class="sxs-lookup"><span data-stu-id="e3968-109">Interoperability level</span></span>|<span data-ttu-id="e3968-110">.NET プロファイル</span><span class="sxs-lookup"><span data-stu-id="e3968-110">.NET-Profile</span></span>|  
|<span data-ttu-id="e3968-111">[メッセージ エンコード]</span><span class="sxs-lookup"><span data-stu-id="e3968-111">Message encoding</span></span>|<span data-ttu-id="e3968-112">Binary</span><span class="sxs-lookup"><span data-stu-id="e3968-112">Binary</span></span>|  
|<span data-ttu-id="e3968-113">[境界]</span><span class="sxs-lookup"><span data-stu-id="e3968-113">Boundary</span></span>|<span data-ttu-id="e3968-114">コンピュータ間</span><span class="sxs-lookup"><span data-stu-id="e3968-114">Cross-computer</span></span>|  
|<span data-ttu-id="e3968-115">トランスポート プロトコル</span><span class="sxs-lookup"><span data-stu-id="e3968-115">Transport protocol</span></span>|<span data-ttu-id="e3968-116">MSMQ (MSMQ)</span><span class="sxs-lookup"><span data-stu-id="e3968-116">MSMQ</span></span>|  
|<span data-ttu-id="e3968-117">[セキュリティ モード]</span><span class="sxs-lookup"><span data-stu-id="e3968-117">Security mode</span></span>|<span data-ttu-id="e3968-118">なし、メッセージ、トランスポート、および両方</span><span class="sxs-lookup"><span data-stu-id="e3968-118">None, Message, Transport, and Both.</span></span>|  
|<span data-ttu-id="e3968-119">クライアント認証のメカニズム</span><span class="sxs-lookup"><span data-stu-id="e3968-119">Client authentication mechanism</span></span>|<span data-ttu-id="e3968-120">トランスポート セキュリティとメッセージ セキュリティ</span><span class="sxs-lookup"><span data-stu-id="e3968-120">Transport Security and Message Security</span></span>|  
|<span data-ttu-id="e3968-121">WS-ReliableMessaging のサポート</span><span class="sxs-lookup"><span data-stu-id="e3968-121">Support for WS-ReliableMessaging</span></span>|<span data-ttu-id="e3968-122">適用なし</span><span class="sxs-lookup"><span data-stu-id="e3968-122">Not applicable</span></span>|  
|<span data-ttu-id="e3968-123">WS-AtomicTransaction のサポート</span><span class="sxs-lookup"><span data-stu-id="e3968-123">Support for WS-AtomicTransaction</span></span>|<span data-ttu-id="e3968-124">はい</span><span class="sxs-lookup"><span data-stu-id="e3968-124">Yes</span></span>|  
|<span data-ttu-id="e3968-125">一方向メッセージングのサポート</span><span class="sxs-lookup"><span data-stu-id="e3968-125">Support for one-way messaging</span></span>|<span data-ttu-id="e3968-126">はい</span><span class="sxs-lookup"><span data-stu-id="e3968-126">Yes</span></span>|  
|<span data-ttu-id="e3968-127">双方向メッセージングのサポート</span><span class="sxs-lookup"><span data-stu-id="e3968-127">Support for two-way messaging</span></span>|<span data-ttu-id="e3968-128">不可</span><span class="sxs-lookup"><span data-stu-id="e3968-128">No</span></span>|  
|<span data-ttu-id="e3968-129">受信アダプタのホストの種類</span><span class="sxs-lookup"><span data-stu-id="e3968-129">Host type for receive adapter</span></span>|<span data-ttu-id="e3968-130">インプロセス</span><span class="sxs-lookup"><span data-stu-id="e3968-130">In-process</span></span>|  
|<span data-ttu-id="e3968-131">送信アダプタのホストの種類</span><span class="sxs-lookup"><span data-stu-id="e3968-131">Host type for send adapter</span></span>|<span data-ttu-id="e3968-132">インプロセス</span><span class="sxs-lookup"><span data-stu-id="e3968-132">In-process</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="e3968-133">WCF-NetMsmq 受信アダプタによるメッセージの抽出元のキューを事前に作成しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="e3968-133">The queues from which the WCF-NetMsmq receive adapter pulls messages must be created in advance.</span></span> <span data-ttu-id="e3968-134">キュー内のメッセージは WCF ベースである必要があります。それ以外の場合、これらのメッセージは配信不能キューに送信されます。</span><span class="sxs-lookup"><span data-stu-id="e3968-134">The messages in the queues must be WCF based; otherwise, these messages will be sent to the dead-letter queue.</span></span>  
  
 <span data-ttu-id="e3968-135">WCF-NetMsmq アダプタは、2 つのアダプタ (受信アダプタと送信アダプタ) で構成されます。</span><span class="sxs-lookup"><span data-stu-id="e3968-135">The WCF-NetMsmq adapter consists of two adapters—a receive adapter and a send adapter.</span></span>  
  
 <span data-ttu-id="e3968-136">**Wcf-netmsmq 受信アダプター**</span><span class="sxs-lookup"><span data-stu-id="e3968-136">**WCF-NetMsmq Receive Adapter**</span></span>  
  
 <span data-ttu-id="e3968-137">WCF-NetMsmq 受信アダプタは、MSMQ 経由で WCF サービス要求を受信するために使用します。</span><span class="sxs-lookup"><span data-stu-id="e3968-137">You use the WCF-NetMsmq receive adapter to receive WCF service requests over MSMQ.</span></span> <span data-ttu-id="e3968-138">WCF-NetMsmq 受信アダプタを使用する受信場所は、一方向の受信場所としてのみ構成できます。</span><span class="sxs-lookup"><span data-stu-id="e3968-138">A receive location that uses the WCF-NetMsmq receive adapter can only be configured as one-way receive.</span></span>  
  
 <span data-ttu-id="e3968-139">**Wcf-netmsmq 送信アダプター**</span><span class="sxs-lookup"><span data-stu-id="e3968-139">**WCF-NetMsmq Send Adapter**</span></span>  
  
 <span data-ttu-id="e3968-140">WCF-NetMsmq 送信アダプタは、MSMQ 経由で型宣言が不要なコントラクトを使用して WCF サービスを呼び出すために使用します。</span><span class="sxs-lookup"><span data-stu-id="e3968-140">You use the WCF-NetMsmq send adapter to call a WCF service through the typeless contract over MSMQ.</span></span>  
  
 <span data-ttu-id="e3968-141">WCF の詳細については、受信し送信アダプターを参照してください[WCF アダプタは何ですか?](../core/what-are-the-wcf-adapters.md)です。</span><span class="sxs-lookup"><span data-stu-id="e3968-141">For more information about WCF receive and send adapters, see [What Are the WCF Adapters?](../core/what-are-the-wcf-adapters.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3968-142">参照</span><span class="sxs-lookup"><span data-stu-id="e3968-142">See Also</span></span>  
 <span data-ttu-id="e3968-143">[Wcf-netmsmq アダプタを構成します。](../core/configuring-the-wcf-netmsmq-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="e3968-143">[Configuring the WCF-NetMsmq Adapter](../core/configuring-the-wcf-netmsmq-adapter.md) </span></span>  
 [<span data-ttu-id="e3968-144">WCF アダプタ</span><span class="sxs-lookup"><span data-stu-id="e3968-144">WCF Adapters</span></span>](../core/wcf-adapters.md)