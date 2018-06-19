---
title: FIN 応答タイプ |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, response types
- deploying, schemas
- FIN Response Reconciliation, message types
- FRR, deploying schemas
- schemas, deploying
- FIN Response Reconciliation, response types
- messages, message types
- response types [FIN Response Reconciliation]
ms.assetid: a6ef2f20-08ab-40d3-a0a5-cc4048ce0987
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 54c890a5e0f51207cce1897b10095a87ae438793
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22208066"
---
# <a name="fin-response-types"></a><span data-ttu-id="9599a-102">FIN 応答の種類</span><span class="sxs-lookup"><span data-stu-id="9599a-102">FIN Response Types</span></span>
<span data-ttu-id="9599a-103">FIN 対応調整 (FRR) は、カテゴリ、0 ~ 9 SWIFT FIN メッセージに応答を調整します。</span><span class="sxs-lookup"><span data-stu-id="9599a-103">FIN Response Reconciliation (FRR) reconciles responses to any Category 0 to 9 SWIFT FIN message.</span></span> <span data-ttu-id="9599a-104">SWIFT FIN アプリケーションは常に、少なくとも 1 つと、複数の可能性のあるいずれかの確認 (ACK) の送信、これらの FIN メッセージに応答または否定受信確認 (NAK)。</span><span class="sxs-lookup"><span data-stu-id="9599a-104">In response to one of these FIN messages, the SWIFT FIN application always sends at least one, and possibly more than one, acknowledgment (ACK) or negative acknowledgment (NAK).</span></span> <span data-ttu-id="9599a-105">次の表に、メッセージの送信および受信の種類を (応答) FRR によって処理されるメッセージ。</span><span class="sxs-lookup"><span data-stu-id="9599a-105">The following table shows the message types of the outbound and inbound (response) messages processed by FRR.</span></span>  
  
|<span data-ttu-id="9599a-106">送信/</span><span class="sxs-lookup"><span data-stu-id="9599a-106">Outbound/</span></span><br /><br /> <span data-ttu-id="9599a-107">受信</span><span class="sxs-lookup"><span data-stu-id="9599a-107">inbound</span></span>|<span data-ttu-id="9599a-108">メッセージ型</span><span class="sxs-lookup"><span data-stu-id="9599a-108">Message type</span></span>|<span data-ttu-id="9599a-109">メッセージの状態</span><span class="sxs-lookup"><span data-stu-id="9599a-109">Message status</span></span>|  
|----------------------------|------------------|--------------------|  
|<span data-ttu-id="9599a-110">送信</span><span class="sxs-lookup"><span data-stu-id="9599a-110">Outbound</span></span>|<span data-ttu-id="9599a-111">すべてのカテゴリ、0 ~ 9 SWIFT FIN メッセージ型</span><span class="sxs-lookup"><span data-stu-id="9599a-111">All Category 0 to 9 SWIFT FIN message types</span></span>|<span data-ttu-id="9599a-112">なし</span><span class="sxs-lookup"><span data-stu-id="9599a-112">N/A</span></span>|  
|<span data-ttu-id="9599a-113">受信</span><span class="sxs-lookup"><span data-stu-id="9599a-113">Inbound</span></span>|<span data-ttu-id="9599a-114">MQ 系列パン/NAN (MQ Series トランスポート レベル ACK/NAK)</span><span class="sxs-lookup"><span data-stu-id="9599a-114">MQ Series PAN/NAN (MQ Series transport-level ACK/NAK)</span></span>|<span data-ttu-id="9599a-115">MQSeries トランスポートの受信確認</span><span class="sxs-lookup"><span data-stu-id="9599a-115">MQSeries transport acknowledgment</span></span>|  
||<span data-ttu-id="9599a-116">MT010 (配信不能警告)</span><span class="sxs-lookup"><span data-stu-id="9599a-116">MT010 (Non-Delivery Warning)</span></span>|<span data-ttu-id="9599a-117">SWIFT が正常に送信元は、取引先、メッセージ、パートナーがメッセージを受信することを示す値がありません。</span><span class="sxs-lookup"><span data-stu-id="9599a-117">SWIFT successfully sent the original message to the partner, but has no indication that the partner received the message.</span></span> <span data-ttu-id="9599a-118">場合[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]は複数の配信不能の警告 (NDW) メッセージを受信ループを実行し、次の予期されるメッセージを待ちます。</span><span class="sxs-lookup"><span data-stu-id="9599a-118">If [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] receives multiple Non-Delivery Warning (NDW) messages, it loops and waits for the next expected message.</span></span>|  
||<span data-ttu-id="9599a-119">MT011 (配信通知)</span><span class="sxs-lookup"><span data-stu-id="9599a-119">MT011 (Delivery Notification)</span></span>|<span data-ttu-id="9599a-120">SWIFT が正常に送信元は、パートナーにメッセージの送受信、パートナーがメッセージを受信することを示す値です。</span><span class="sxs-lookup"><span data-stu-id="9599a-120">SWIFT successfully sent the original message to the partner, and received an indication that the partner received the message.</span></span>|  
||<span data-ttu-id="9599a-121">MT012 (送信者 Notification)</span><span class="sxs-lookup"><span data-stu-id="9599a-121">MT012 (Sender Notification)</span></span>|<span data-ttu-id="9599a-122">SWIFT から元のメッセージを正常に受信された[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="9599a-122">SWIFT successfully received the original message from [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)].</span></span>|  
||<span data-ttu-id="9599a-123">MT015 (DNK、または遅延 NAK)</span><span class="sxs-lookup"><span data-stu-id="9599a-123">MT015 (DNK, or Delayed NAK)</span></span>|<span data-ttu-id="9599a-124">SWIFT が、パートナーに、元のメッセージを正常に送信していないがします。</span><span class="sxs-lookup"><span data-stu-id="9599a-124">SWIFT has not successfully sent the original message to the partner.</span></span>|  
||<span data-ttu-id="9599a-125">MT019 (通知を中止)</span><span class="sxs-lookup"><span data-stu-id="9599a-125">MT019 (Abort Notification)</span></span>|<span data-ttu-id="9599a-126">SWIFT のメッセージ転送が中止されました。</span><span class="sxs-lookup"><span data-stu-id="9599a-126">Message transmission aborted at SWIFT.</span></span>|  
||<span data-ttu-id="9599a-127">MTS21_FIN_ACKNAK (受信確認メッセージまたは否定受信確認 (ACK/NAK)、LT によって送信された FIN メッセージの)</span><span class="sxs-lookup"><span data-stu-id="9599a-127">MTS21_FIN_ACKNAK (Acknowledgment or negative acknowledgment of a FIN message sent by an LT (ACK/NAK))</span></span>|<span data-ttu-id="9599a-128">SWIFT 成功と失敗からのメッセージを受信した[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="9599a-128">SWIFT successfully or unsuccessfully received the message from [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)].</span></span> <span data-ttu-id="9599a-129">このメッセージは、このような場合の両方について説明します。</span><span class="sxs-lookup"><span data-stu-id="9599a-129">This message covers both of these cases.</span></span> <span data-ttu-id="9599a-130">ACK と NAK であるかは、メッセージ (ACK 用の「0」) と NAK の「1」の 451 フィールドの値によって決まります。</span><span class="sxs-lookup"><span data-stu-id="9599a-130">Whether it is an ACK or a NAK is determined by the value in the 451 field of the message ("0" for ACK and "1" for NAK).</span></span> <span data-ttu-id="9599a-131">これに配信された最初の応答になります[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="9599a-131">This will be the first response delivered back to [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)].</span></span>|  
  
## <a name="deployment-of-schemas-for-frr"></a><span data-ttu-id="9599a-132">FRR 用にスキーマの展開</span><span class="sxs-lookup"><span data-stu-id="9599a-132">Deployment of Schemas for FRR</span></span>  
 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]<span data-ttu-id="9599a-133">セットアップでは、(上記の表に示すように) として FrrSchemas.dll でシステム レベルのすべてのメッセージのスキーマが配置されます。</span><span class="sxs-lookup"><span data-stu-id="9599a-133"> setup deploys schemas in FrrSchemas.dll for all system-level messages (as shown in the table above).</span></span> <span data-ttu-id="9599a-134">FRR オーケストレーションでは、これらのスキーマを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9599a-134">The FRR orchestration requires these schemas to be deployed.</span></span> <span data-ttu-id="9599a-135">[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]セットアップ FrrSchemas.dll でこれらのスキーマを配置するには、する必要はありませんしてする必要がある別のプロジェクトでこれらのスキーマを展開します。</span><span class="sxs-lookup"><span data-stu-id="9599a-135">Because [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] setup deploys these schemas in FrrSchemas.dll, you do not have to, and must not, deploy these schemas in another project.</span></span> <span data-ttu-id="9599a-136">そうと、エラーが生成されます。</span><span class="sxs-lookup"><span data-stu-id="9599a-136">Doing so will generate an error.</span></span>  
  
 <span data-ttu-id="9599a-137">FRRSchemas.dll には、次のスキーマが含まれています。</span><span class="sxs-lookup"><span data-stu-id="9599a-137">FRRSchemas.dll includes the following schemas:</span></span>  
  
-   <span data-ttu-id="9599a-138">TransportAck</span><span class="sxs-lookup"><span data-stu-id="9599a-138">TransportAck</span></span>  
  
-   <span data-ttu-id="9599a-139">MT010</span><span class="sxs-lookup"><span data-stu-id="9599a-139">MT010</span></span>  
  
-   <span data-ttu-id="9599a-140">MT011</span><span class="sxs-lookup"><span data-stu-id="9599a-140">MT011</span></span>  
  
-   <span data-ttu-id="9599a-141">MT012</span><span class="sxs-lookup"><span data-stu-id="9599a-141">MT012</span></span>  
  
-   <span data-ttu-id="9599a-142">MT015</span><span class="sxs-lookup"><span data-stu-id="9599a-142">MT015</span></span>  
  
-   <span data-ttu-id="9599a-143">MT019</span><span class="sxs-lookup"><span data-stu-id="9599a-143">MT019</span></span>  
  
-   <span data-ttu-id="9599a-144">MTS21_FIN_ACKNAK</span><span class="sxs-lookup"><span data-stu-id="9599a-144">MTS21_FIN_ACKNAK</span></span>