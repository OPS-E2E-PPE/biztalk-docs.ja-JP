---
title: Wcf-netmsmq アダプターとは何ですか。 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF-NetMsmq adapters, about WCF-NetMsmq adapters
ms.assetid: 506c5e2d-6cbe-4788-8e37-49d009dc559a
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ba6cfcba8858e894b83b5ec45fcd51406db93fcc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65242787"
---
# <a name="what-is-the-wcf-netmsmq-adapter"></a><span data-ttu-id="21ded-103">Wcf-netmsmq アダプターとは何ですか。</span><span class="sxs-lookup"><span data-stu-id="21ded-103">What Is the WCF-NetMsmq Adapter?</span></span>
<span data-ttu-id="21ded-104">Wcf-netmsmq アダプタは、サービスとクライアントの両方が WCF ベースの環境でキュー テクノロジを使用して、切断されているコンピュータ間の通信を提供します。</span><span class="sxs-lookup"><span data-stu-id="21ded-104">The WCF-NetMsmq adapter provides disconnected cross-computer communication by using queuing technology in an environment where both the services and clients are WCF based.</span></span> <span data-ttu-id="21ded-105">メッセージ キュー (MSMQ) トランスポートを使用して、メッセージはバイナリ エンコードします。</span><span class="sxs-lookup"><span data-stu-id="21ded-105">It uses the Message Queuing (MSMQ) transport, and messages have binary encoding.</span></span>  
  
 <span data-ttu-id="21ded-106">次の表では、Wcf-netmsmq アダプタの特性をまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="21ded-106">The following table summarizes the characteristics for the WCF-NetMsmq adapter.</span></span>  
  
|<span data-ttu-id="21ded-107">説明</span><span class="sxs-lookup"><span data-stu-id="21ded-107">Description</span></span>|<span data-ttu-id="21ded-108">特性</span><span class="sxs-lookup"><span data-stu-id="21ded-108">Characteristic</span></span>|  
|-----------------|--------------------|  
|<span data-ttu-id="21ded-109">相互運用性レベル</span><span class="sxs-lookup"><span data-stu-id="21ded-109">Interoperability level</span></span>|<span data-ttu-id="21ded-110">.NET プロファイル</span><span class="sxs-lookup"><span data-stu-id="21ded-110">.NET-Profile</span></span>|  
|<span data-ttu-id="21ded-111">[メッセージ エンコード]</span><span class="sxs-lookup"><span data-stu-id="21ded-111">Message encoding</span></span>|<span data-ttu-id="21ded-112">Binary</span><span class="sxs-lookup"><span data-stu-id="21ded-112">Binary</span></span>|  
|<span data-ttu-id="21ded-113">[境界]</span><span class="sxs-lookup"><span data-stu-id="21ded-113">Boundary</span></span>|<span data-ttu-id="21ded-114">コンピュータ間</span><span class="sxs-lookup"><span data-stu-id="21ded-114">Cross-computer</span></span>|  
|<span data-ttu-id="21ded-115">トランスポート プロトコル</span><span class="sxs-lookup"><span data-stu-id="21ded-115">Transport protocol</span></span>|<span data-ttu-id="21ded-116">MSMQ (MSMQ)</span><span class="sxs-lookup"><span data-stu-id="21ded-116">MSMQ</span></span>|  
|<span data-ttu-id="21ded-117">[セキュリティ モード]</span><span class="sxs-lookup"><span data-stu-id="21ded-117">Security mode</span></span>|<span data-ttu-id="21ded-118">None、メッセージ、トランスポート、および両方。</span><span class="sxs-lookup"><span data-stu-id="21ded-118">None, Message, Transport, and Both.</span></span>|  
|<span data-ttu-id="21ded-119">クライアント認証のメカニズム</span><span class="sxs-lookup"><span data-stu-id="21ded-119">Client authentication mechanism</span></span>|<span data-ttu-id="21ded-120">トランスポート セキュリティとメッセージ セキュリティ</span><span class="sxs-lookup"><span data-stu-id="21ded-120">Transport Security and Message Security</span></span>|  
|<span data-ttu-id="21ded-121">WS-ReliableMessaging のサポート</span><span class="sxs-lookup"><span data-stu-id="21ded-121">Support for WS-ReliableMessaging</span></span>|<span data-ttu-id="21ded-122">適用なし</span><span class="sxs-lookup"><span data-stu-id="21ded-122">Not applicable</span></span>|  
|<span data-ttu-id="21ded-123">WS-AtomicTransaction のサポート</span><span class="sxs-lookup"><span data-stu-id="21ded-123">Support for WS-AtomicTransaction</span></span>|<span data-ttu-id="21ded-124">はい</span><span class="sxs-lookup"><span data-stu-id="21ded-124">Yes</span></span>|  
|<span data-ttu-id="21ded-125">一方向メッセージングのサポート</span><span class="sxs-lookup"><span data-stu-id="21ded-125">Support for one-way messaging</span></span>|<span data-ttu-id="21ded-126">はい</span><span class="sxs-lookup"><span data-stu-id="21ded-126">Yes</span></span>|  
|<span data-ttu-id="21ded-127">双方向メッセージングのサポート</span><span class="sxs-lookup"><span data-stu-id="21ded-127">Support for two-way messaging</span></span>|<span data-ttu-id="21ded-128">いいえ</span><span class="sxs-lookup"><span data-stu-id="21ded-128">No</span></span>|  
|<span data-ttu-id="21ded-129">受信アダプタのホストの種類</span><span class="sxs-lookup"><span data-stu-id="21ded-129">Host type for receive adapter</span></span>|<span data-ttu-id="21ded-130">インプロセス</span><span class="sxs-lookup"><span data-stu-id="21ded-130">In-process</span></span>|  
|<span data-ttu-id="21ded-131">送信アダプタのホストの種類</span><span class="sxs-lookup"><span data-stu-id="21ded-131">Host type for send adapter</span></span>|<span data-ttu-id="21ded-132">インプロセス</span><span class="sxs-lookup"><span data-stu-id="21ded-132">In-process</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="21ded-133">Wcf-netmsmq 受信アダプターによるメッセージの抽出を元のキューは、事前に作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="21ded-133">The queues from which the WCF-NetMsmq receive adapter pulls messages must be created in advance.</span></span> <span data-ttu-id="21ded-134">キュー内のメッセージが WCF ベース; にある必要があります。それ以外の場合、これらのメッセージを配信不能キューに送信されます。</span><span class="sxs-lookup"><span data-stu-id="21ded-134">The messages in the queues must be WCF based; otherwise, these messages will be sent to the dead-letter queue.</span></span>  
  
 <span data-ttu-id="21ded-135">Wcf-netmsmq アダプターは、2 つのアダプターで構成されます-受信アダプタと送信アダプター。</span><span class="sxs-lookup"><span data-stu-id="21ded-135">The WCF-NetMsmq adapter consists of two adapters—a receive adapter and a send adapter.</span></span>  
  
 <span data-ttu-id="21ded-136">**Wcf-netmsmq 受信アダプター**</span><span class="sxs-lookup"><span data-stu-id="21ded-136">**WCF-NetMsmq Receive Adapter**</span></span>  
  
 <span data-ttu-id="21ded-137">Wcf-netmsmq を使用する受信アダプターを MSMQ 経由で WCF サービス要求を受信します。</span><span class="sxs-lookup"><span data-stu-id="21ded-137">You use the WCF-NetMsmq receive adapter to receive WCF service requests over MSMQ.</span></span> <span data-ttu-id="21ded-138">Wcf-netmsmq 受信アダプタを使用する受信場所は、一方向の受信としてのみ構成できます。</span><span class="sxs-lookup"><span data-stu-id="21ded-138">A receive location that uses the WCF-NetMsmq receive adapter can only be configured as one-way receive.</span></span>  
  
 <span data-ttu-id="21ded-139">**Wcf-netmsmq 送信アダプター**</span><span class="sxs-lookup"><span data-stu-id="21ded-139">**WCF-NetMsmq Send Adapter**</span></span>  
  
 <span data-ttu-id="21ded-140">Wcf-netmsmq 送信アダプターを使用して、MSMQ 経由で型宣言不要なコントラクトを介して WCF サービスを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="21ded-140">You use the WCF-NetMsmq send adapter to call a WCF service through the typeless contract over MSMQ.</span></span>  
  
 <span data-ttu-id="21ded-141">WCF の詳細については、受信し送信アダプターを参照してください[WCF アダプタは何ですか?](../core/what-are-the-wcf-adapters.md)します。</span><span class="sxs-lookup"><span data-stu-id="21ded-141">For more information about WCF receive and send adapters, see [What Are the WCF Adapters?](../core/what-are-the-wcf-adapters.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21ded-142">参照</span><span class="sxs-lookup"><span data-stu-id="21ded-142">See Also</span></span>  
 <span data-ttu-id="21ded-143">[Wcf-netmsmq アダプターを構成します。](../core/configuring-the-wcf-netmsmq-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="21ded-143">[Configuring the WCF-NetMsmq Adapter](../core/configuring-the-wcf-netmsmq-adapter.md) </span></span>  
 [<span data-ttu-id="21ded-144">WCF アダプター</span><span class="sxs-lookup"><span data-stu-id="21ded-144">WCF Adapters</span></span>](../core/wcf-adapters.md)