---
title: AS2 ソリューションのポートの構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 715358b1-4226-476b-b0de-2b91434aa24c
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b045a18893153d6c2982b7b6214b7eea6e1852fb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390860"
---
# <a name="configuring-ports-for-an-as2-solution"></a><span data-ttu-id="2fc7a-102">AS2 ソリューションのポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="2fc7a-102">Configuring Ports for an AS2 Solution</span></span>
<span data-ttu-id="2fc7a-103">次の受信に使用でき、AS2 経由で EDI および非 EDI メッセージを送信する送信ポート。</span><span class="sxs-lookup"><span data-stu-id="2fc7a-103">You can use the following receive and send ports to transmit EDI and non-EDI messages over AS2:</span></span>  
  
 <span data-ttu-id="2fc7a-104">**受信ポート**</span><span class="sxs-lookup"><span data-stu-id="2fc7a-104">**Receive Ports**</span></span>  
  
|<span data-ttu-id="2fc7a-105">受信するには</span><span class="sxs-lookup"><span data-stu-id="2fc7a-105">To Receive</span></span>|<span data-ttu-id="2fc7a-106">送信するには</span><span class="sxs-lookup"><span data-stu-id="2fc7a-106">To Send</span></span>|<span data-ttu-id="2fc7a-107">ポートの種類</span><span class="sxs-lookup"><span data-stu-id="2fc7a-107">Type of Port</span></span>|  
|----------------|-------------|------------------|  
|<span data-ttu-id="2fc7a-108">EDI または非 EDI メッセージまたは確認</span><span class="sxs-lookup"><span data-stu-id="2fc7a-108">An EDI or non-EDI message or acknowledgment</span></span>|<span data-ttu-id="2fc7a-109">MDN 応答 (同期モードの場合) または HTTP 応答 (非同期モードの場合)</span><span class="sxs-lookup"><span data-stu-id="2fc7a-109">An MDN response (if in synchronous mode) or an HTTP response (if in asynchronous mode)</span></span>|<span data-ttu-id="2fc7a-110">双方向の要求-応答の HTTP 受信ポート</span><span class="sxs-lookup"><span data-stu-id="2fc7a-110">Two-way request-response HTTP receive port</span></span>|  
|<span data-ttu-id="2fc7a-111">MDN 応答</span><span class="sxs-lookup"><span data-stu-id="2fc7a-111">An MDN response</span></span>|-|<span data-ttu-id="2fc7a-112">一方向 HTTP 受信ポート</span><span class="sxs-lookup"><span data-stu-id="2fc7a-112">One-way HTTP receive port</span></span>|  
  
 <span data-ttu-id="2fc7a-113">**送信ポート**</span><span class="sxs-lookup"><span data-stu-id="2fc7a-113">**Send Ports**</span></span>  
  
|<span data-ttu-id="2fc7a-114">送信するには</span><span class="sxs-lookup"><span data-stu-id="2fc7a-114">To Send</span></span>|<span data-ttu-id="2fc7a-115">受信するには</span><span class="sxs-lookup"><span data-stu-id="2fc7a-115">To Receive</span></span>|<span data-ttu-id="2fc7a-116">ポートの種類</span><span class="sxs-lookup"><span data-stu-id="2fc7a-116">Type of Port</span></span>|  
|-------------|----------------|------------------|  
|<span data-ttu-id="2fc7a-117">EDI または非 EDI メッセージまたは確認</span><span class="sxs-lookup"><span data-stu-id="2fc7a-117">An EDI or non-EDI message or acknowledgment</span></span><br /><br /> <span data-ttu-id="2fc7a-118">(アグリーメント ベースのルーティング)</span><span class="sxs-lookup"><span data-stu-id="2fc7a-118">(agreement-based routing)</span></span>|-|<span data-ttu-id="2fc7a-119">静的な一方向の HTTP 送信ポート</span><span class="sxs-lookup"><span data-stu-id="2fc7a-119">Static one-way HTTP send port</span></span>|  
|<span data-ttu-id="2fc7a-120">EDI または非 EDI メッセージまたは確認</span><span class="sxs-lookup"><span data-stu-id="2fc7a-120">An EDI or non-EDI message or acknowledgment</span></span><br /><br /> <span data-ttu-id="2fc7a-121">(コンテンツ ベースのルーティング)</span><span class="sxs-lookup"><span data-stu-id="2fc7a-121">(content-based routing)</span></span>|<span data-ttu-id="2fc7a-122">MDN 応答</span><span class="sxs-lookup"><span data-stu-id="2fc7a-122">An MDN response</span></span>|<span data-ttu-id="2fc7a-123">動的な双方向送信請求-応答 HTTP 送信ポート</span><span class="sxs-lookup"><span data-stu-id="2fc7a-123">Dynamic two-way solicit-response HTTP send port</span></span>|  
|<span data-ttu-id="2fc7a-124">EDI または非 EDI メッセージまたは確認</span><span class="sxs-lookup"><span data-stu-id="2fc7a-124">An EDI or non-EDI message or acknowledgment</span></span><br /><br /> <span data-ttu-id="2fc7a-125">(コンテンツ ベースのルーティング)</span><span class="sxs-lookup"><span data-stu-id="2fc7a-125">(content-based routing)</span></span>|-|<span data-ttu-id="2fc7a-126">動的な一方向の HTTP 送信ポート</span><span class="sxs-lookup"><span data-stu-id="2fc7a-126">Dynamic one-way HTTP send port</span></span>|  
|<span data-ttu-id="2fc7a-127">非同期の MDN 応答</span><span class="sxs-lookup"><span data-stu-id="2fc7a-127">An asynchronous MDN response</span></span><br /><br /> <span data-ttu-id="2fc7a-128">(コンテンツ ベースのルーティング)</span><span class="sxs-lookup"><span data-stu-id="2fc7a-128">(content-based routing)</span></span>|-|<span data-ttu-id="2fc7a-129">動的な一方向送信ポート</span><span class="sxs-lookup"><span data-stu-id="2fc7a-129">Dynamic one-way send port</span></span>|  
|<span data-ttu-id="2fc7a-130">非同期の MDN 応答</span><span class="sxs-lookup"><span data-stu-id="2fc7a-130">An asynchronous MDN response</span></span>|-|<span data-ttu-id="2fc7a-131">静的な一方向送信ポート</span><span class="sxs-lookup"><span data-stu-id="2fc7a-131">Static one-way send port</span></span>|  
  
## <a name="in-this-section"></a><span data-ttu-id="2fc7a-132">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="2fc7a-132">In This Section</span></span>  
  
-   [<span data-ttu-id="2fc7a-133">AS2 経由でのメッセージの受信ポートの構成</span><span class="sxs-lookup"><span data-stu-id="2fc7a-133">Configuring a Receive Port for Messages over AS2</span></span>](../core/configuring-a-receive-port-for-messages-over-as2.md)  
  
-   [<span data-ttu-id="2fc7a-134">受信 MDN の受信ポートの構成</span><span class="sxs-lookup"><span data-stu-id="2fc7a-134">Configuring a Receive Port for Incoming MDNs</span></span>](../core/configuring-a-receive-port-for-incoming-mdns.md)  
  
-   [<span data-ttu-id="2fc7a-135">AS2 経由でのメッセージの静的送信ポートの構成</span><span class="sxs-lookup"><span data-stu-id="2fc7a-135">Configuring a Static Send Port for Messages over AS2</span></span>](../core/configuring-a-static-send-port-for-messages-over-as2.md)  
  
-   [<span data-ttu-id="2fc7a-136">AS2 経由でのメッセージの動的送信ポートの構成</span><span class="sxs-lookup"><span data-stu-id="2fc7a-136">Configuring a Dynamic Send Port for Messages over AS2</span></span>](../core/configuring-a-dynamic-send-port-for-messages-over-as2.md)  
  
-   [<span data-ttu-id="2fc7a-137">AS2 経由の非同期 MDN の静的送信ポートの構成</span><span class="sxs-lookup"><span data-stu-id="2fc7a-137">Configuring a Static Send Port for Asynchronous MDNs over AS2</span></span>](../core/configuring-a-static-send-port-for-asynchronous-mdns-over-as2.md)  
  
-   [<span data-ttu-id="2fc7a-138">AS2 経由の非同期 MDN の動的送信ポートの構成</span><span class="sxs-lookup"><span data-stu-id="2fc7a-138">Configuring a Dynamic Send Port for Asynchronous MDNs over AS2</span></span>](../core/configuring-a-dynamic-send-port-for-asynchronous-mdns-over-as2.md)  
  
## <a name="see-also"></a><span data-ttu-id="2fc7a-139">参照</span><span class="sxs-lookup"><span data-stu-id="2fc7a-139">See Also</span></span>  
 [<span data-ttu-id="2fc7a-140">BizTalk Server AS2 ソリューションの開発と構成</span><span class="sxs-lookup"><span data-stu-id="2fc7a-140">Developing and Configuring BizTalk Server AS2 Solutions</span></span>](../core/developing-and-configuring-biztalk-server-as2-solutions.md)