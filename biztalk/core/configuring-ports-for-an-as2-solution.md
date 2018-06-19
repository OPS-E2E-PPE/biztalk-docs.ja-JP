---
title: AS2 ソリューションのポートの構成 |Microsoft ドキュメント
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
ms.openlocfilehash: f8f02c5de0edd7956f00e10ce8782e4865033076
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22233586"
---
# <a name="configuring-ports-for-an-as2-solution"></a><span data-ttu-id="c05ac-102">AS2 ソリューションのポートの構成</span><span class="sxs-lookup"><span data-stu-id="c05ac-102">Configuring Ports for an AS2 Solution</span></span>
<span data-ttu-id="c05ac-103">AS2 経由で EDI メッセージおよび非 EDI メッセージを転送するには、次の受信ポートと送信ポートを使用します。</span><span class="sxs-lookup"><span data-stu-id="c05ac-103">You can use the following receive and send ports to transmit EDI and non-EDI messages over AS2:</span></span>  
  
 <span data-ttu-id="c05ac-104">**受信ポート**</span><span class="sxs-lookup"><span data-stu-id="c05ac-104">**Receive Ports**</span></span>  
  
|<span data-ttu-id="c05ac-105">受信対象</span><span class="sxs-lookup"><span data-stu-id="c05ac-105">To Receive</span></span>|<span data-ttu-id="c05ac-106">送信対象</span><span class="sxs-lookup"><span data-stu-id="c05ac-106">To Send</span></span>|<span data-ttu-id="c05ac-107">ポートの種類</span><span class="sxs-lookup"><span data-stu-id="c05ac-107">Type of Port</span></span>|  
|----------------|-------------|------------------|  
|<span data-ttu-id="c05ac-108">EDI メッセージ、非 EDI メッセージ、または受信確認</span><span class="sxs-lookup"><span data-stu-id="c05ac-108">An EDI or non-EDI message or acknowledgment</span></span>|<span data-ttu-id="c05ac-109">MDN 応答 (同期モードの場合) または HTTP 応答 (非同期モードの場合)</span><span class="sxs-lookup"><span data-stu-id="c05ac-109">An MDN response (if in synchronous mode) or an HTTP response (if in asynchronous mode)</span></span>|<span data-ttu-id="c05ac-110">双方向 (要求 - 応答) の HTTP 受信ポート</span><span class="sxs-lookup"><span data-stu-id="c05ac-110">Two-way request-response HTTP receive port</span></span>|  
|<span data-ttu-id="c05ac-111">MDN 応答</span><span class="sxs-lookup"><span data-stu-id="c05ac-111">An MDN response</span></span>|-|<span data-ttu-id="c05ac-112">一方向の HTTP 受信ポート</span><span class="sxs-lookup"><span data-stu-id="c05ac-112">One-way HTTP receive port</span></span>|  
  
 <span data-ttu-id="c05ac-113">**送信ポート**</span><span class="sxs-lookup"><span data-stu-id="c05ac-113">**Send Ports**</span></span>  
  
|<span data-ttu-id="c05ac-114">送信対象</span><span class="sxs-lookup"><span data-stu-id="c05ac-114">To Send</span></span>|<span data-ttu-id="c05ac-115">受信対象</span><span class="sxs-lookup"><span data-stu-id="c05ac-115">To Receive</span></span>|<span data-ttu-id="c05ac-116">ポートの種類</span><span class="sxs-lookup"><span data-stu-id="c05ac-116">Type of Port</span></span>|  
|-------------|----------------|------------------|  
|<span data-ttu-id="c05ac-117">EDI メッセージ、非 EDI メッセージ、または受信確認</span><span class="sxs-lookup"><span data-stu-id="c05ac-117">An EDI or non-EDI message or acknowledgment</span></span><br /><br /> <span data-ttu-id="c05ac-118">(アグリーメント ベースのルーティング)</span><span class="sxs-lookup"><span data-stu-id="c05ac-118">(agreement-based routing)</span></span>|-|<span data-ttu-id="c05ac-119">静的な一方向の HTTP 送信ポート</span><span class="sxs-lookup"><span data-stu-id="c05ac-119">Static one-way HTTP send port</span></span>|  
|<span data-ttu-id="c05ac-120">EDI メッセージ、非 EDI メッセージ、または受信確認</span><span class="sxs-lookup"><span data-stu-id="c05ac-120">An EDI or non-EDI message or acknowledgment</span></span><br /><br /> <span data-ttu-id="c05ac-121">(コンテンツ ベースのルーティング)</span><span class="sxs-lookup"><span data-stu-id="c05ac-121">(content-based routing)</span></span>|<span data-ttu-id="c05ac-122">MDN 応答</span><span class="sxs-lookup"><span data-stu-id="c05ac-122">An MDN response</span></span>|<span data-ttu-id="c05ac-123">動的な双方向 (送信請求 - 応答) の HTTP 送信ポート</span><span class="sxs-lookup"><span data-stu-id="c05ac-123">Dynamic two-way solicit-response HTTP send port</span></span>|  
|<span data-ttu-id="c05ac-124">EDI メッセージ、非 EDI メッセージ、または受信確認</span><span class="sxs-lookup"><span data-stu-id="c05ac-124">An EDI or non-EDI message or acknowledgment</span></span><br /><br /> <span data-ttu-id="c05ac-125">(コンテンツ ベースのルーティング)</span><span class="sxs-lookup"><span data-stu-id="c05ac-125">(content-based routing)</span></span>|-|<span data-ttu-id="c05ac-126">動的な一方向の HTTP 送信ポート</span><span class="sxs-lookup"><span data-stu-id="c05ac-126">Dynamic one-way HTTP send port</span></span>|  
|<span data-ttu-id="c05ac-127">非同期の MDN 応答</span><span class="sxs-lookup"><span data-stu-id="c05ac-127">An asynchronous MDN response</span></span><br /><br /> <span data-ttu-id="c05ac-128">(コンテンツ ベースのルーティング)</span><span class="sxs-lookup"><span data-stu-id="c05ac-128">(content-based routing)</span></span>|-|<span data-ttu-id="c05ac-129">動的な一方向の送信ポート</span><span class="sxs-lookup"><span data-stu-id="c05ac-129">Dynamic one-way send port</span></span>|  
|<span data-ttu-id="c05ac-130">非同期の MDN 応答</span><span class="sxs-lookup"><span data-stu-id="c05ac-130">An asynchronous MDN response</span></span>|-|<span data-ttu-id="c05ac-131">静的な一方向の送信ポート</span><span class="sxs-lookup"><span data-stu-id="c05ac-131">Static one-way send port</span></span>|  
  
## <a name="in-this-section"></a><span data-ttu-id="c05ac-132">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="c05ac-132">In This Section</span></span>  
  
-   [<span data-ttu-id="c05ac-133">構成、AS2 経由でメッセージの受信ポート</span><span class="sxs-lookup"><span data-stu-id="c05ac-133">Configuring a Receive Port for Messages over AS2</span></span>](../core/configuring-a-receive-port-for-messages-over-as2.md)  
  
-   [<span data-ttu-id="c05ac-134">構成、着信 Mdn の受信ポート</span><span class="sxs-lookup"><span data-stu-id="c05ac-134">Configuring a Receive Port for Incoming MDNs</span></span>](../core/configuring-a-receive-port-for-incoming-mdns.md)  
  
-   [<span data-ttu-id="c05ac-135">AS2 経由でメッセージの静的送信ポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="c05ac-135">Configuring a Static Send Port for Messages over AS2</span></span>](../core/configuring-a-static-send-port-for-messages-over-as2.md)  
  
-   [<span data-ttu-id="c05ac-136">AS2 経由でメッセージの動的送信ポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="c05ac-136">Configuring a Dynamic Send Port for Messages over AS2</span></span>](../core/configuring-a-dynamic-send-port-for-messages-over-as2.md)  
  
-   [<span data-ttu-id="c05ac-137">AS2 経由で Mdn が非同期の静的送信ポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="c05ac-137">Configuring a Static Send Port for Asynchronous MDNs over AS2</span></span>](../core/configuring-a-static-send-port-for-asynchronous-mdns-over-as2.md)  
  
-   [<span data-ttu-id="c05ac-138">AS2 経由で Mdn が非同期の動的送信ポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="c05ac-138">Configuring a Dynamic Send Port for Asynchronous MDNs over AS2</span></span>](../core/configuring-a-dynamic-send-port-for-asynchronous-mdns-over-as2.md)  
  
## <a name="see-also"></a><span data-ttu-id="c05ac-139">参照</span><span class="sxs-lookup"><span data-stu-id="c05ac-139">See Also</span></span>  
 [<span data-ttu-id="c05ac-140">開発と BizTalk Server AS2 ソリューションの構成</span><span class="sxs-lookup"><span data-stu-id="c05ac-140">Developing and Configuring BizTalk Server AS2 Solutions</span></span>](../core/developing-and-configuring-biztalk-server-as2-solutions.md)