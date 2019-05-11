---
title: Web サービスの使用 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Web services
- Web services, about Web services
- orchestrations, Web services
- Web services, orchestrations
ms.assetid: a54261e3-d8ef-4770-8d9a-147685846051
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 24af6961e888f8cda21e8d280451382160e2b5af
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65262114"
---
# <a name="using-web-services"></a><span data-ttu-id="a9941-102">Web サービスの使用</span><span class="sxs-lookup"><span data-stu-id="a9941-102">Using Web Services</span></span>
<span data-ttu-id="a9941-103">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Web サービスの組み込みサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="a9941-103">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] provides built-in support for Web services.</span></span> <span data-ttu-id="a9941-104">BizTalk Server は、再利用とすべての既存の Web サービス、オーケストレーション内で集計できます。</span><span class="sxs-lookup"><span data-stu-id="a9941-104">BizTalk Server enables the reuse and aggregation of all your existing Web services within your orchestrations.</span></span> <span data-ttu-id="a9941-105">(公開) を公開することも、オーケストレーションを Web を分離する Web サービスとしてのサービス ロジックとビジネス プロセス ロジック。</span><span class="sxs-lookup"><span data-stu-id="a9941-105">You can also publish (expose) your orchestrations as Web services to separate the Web service logic from the business process logic.</span></span>  
  
 <span data-ttu-id="a9941-106">BizTalk Server では、Web サービスのネイティブ アダプターのサポートを実装します。</span><span class="sxs-lookup"><span data-stu-id="a9941-106">BizTalk Server implements support for native adapters in Web services.</span></span> <span data-ttu-id="a9941-107">ネイティブ アダプタのサポートは、スケーラビリティ、フォールト トレランス、および Web サービスの機能を 1 行のコードを記述することがなく追跡を提供します。</span><span class="sxs-lookup"><span data-stu-id="a9941-107">Native adapter support provides scalability, fault tolerance, and tracking capabilities for Web services without writing a single line of code.</span></span> <span data-ttu-id="a9941-108">SOAP アダプターについては、次を参照してください。 [SOAP アダプター](../core/soap-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="a9941-108">For information about the SOAP adapter, see [SOAP Adapter](../core/soap-adapter.md).</span></span>  
  
 <span data-ttu-id="a9941-109">BizTalk Server での Web サービスのサポートが 2 つのカテゴリに分類されます。 Web サービスの使用または Web サービスを呼び出すと公開または作成します。</span><span class="sxs-lookup"><span data-stu-id="a9941-109">The Web services support in BizTalk Server falls into two categories: consuming or calling Web services and publishing or creating Web services.</span></span>  
  
 <span data-ttu-id="a9941-110">利用または Web サービスを発行する前に、asp.net XML Web サービスの理解が必要です。</span><span class="sxs-lookup"><span data-stu-id="a9941-110">Before you consume or publish a Web service, you should have an understanding of XML Web services in ASP.NET.</span></span> <span data-ttu-id="a9941-111">XML Web サービスの基本についてにある「XML Web サービスの基本事項」の記事を参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=193057](http://go.microsoft.com/fwlink/?LinkId=193057)します。</span><span class="sxs-lookup"><span data-stu-id="a9941-111">For information about the basics of XML Web services, see the article "XML Web Services Basics" at [http://go.microsoft.com/fwlink/?LinkId=193057](http://go.microsoft.com/fwlink/?LinkId=193057).</span></span>  
  
 <span data-ttu-id="a9941-112">**Web サービスの使用**</span><span class="sxs-lookup"><span data-stu-id="a9941-112">**Consuming Web services**</span></span>  
  
 <span data-ttu-id="a9941-113">オーケストレーション内から (呼び出し) Web サービスを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="a9941-113">You can consume (call) Web services from within an orchestration.</span></span> <span data-ttu-id="a9941-114">複数の Web サービスは、ビジネス プロセス全体を完了する 1 つのオーケストレーションに集計できます。</span><span class="sxs-lookup"><span data-stu-id="a9941-114">You can aggregate several Web services into single orchestration to complete an entire business process.</span></span>  
  
 <span data-ttu-id="a9941-115">**Web サービスの公開**</span><span class="sxs-lookup"><span data-stu-id="a9941-115">**Publishing Web services**</span></span>  
  
 <span data-ttu-id="a9941-116">BizTalk Web サービス公開ウィザードを使用して Web サービスを発行することができます。</span><span class="sxs-lookup"><span data-stu-id="a9941-116">You can publish Web services using the BizTalk Web Services Publishing Wizard.</span></span> <span data-ttu-id="a9941-117">オーケストレーションや送信アダプターは、これらの公開済み Web サービスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="a9941-117">Orchestrations and send adapters can use these published Web services.</span></span>  
  
 <span data-ttu-id="a9941-118">**SOAP ヘッダーの使用**</span><span class="sxs-lookup"><span data-stu-id="a9941-118">**Using SOAP headers**</span></span>  
  
 <span data-ttu-id="a9941-119">BizTalk Server では、定義されていると、不明な SOAP ヘッダーのサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="a9941-119">BizTalk Server provides support for defined and unknown SOAP headers.</span></span> <span data-ttu-id="a9941-120">BizTalk Server では、Web サービスで定義されている各 SOAP ヘッダー コンテキスト プロパティを作成します。</span><span class="sxs-lookup"><span data-stu-id="a9941-120">BizTalk Server creates a context property for each defined SOAP header in the Web service.</span></span>  
  
 <span data-ttu-id="a9941-121">**Web サービス標準**</span><span class="sxs-lookup"><span data-stu-id="a9941-121">**Web Services standards**</span></span>  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="a9941-122">送受信するときに任意の Web サービス標準を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a9941-122">should work with any Web Services standards when sending and receiving.</span></span> <span data-ttu-id="a9941-123">すべての標準がテストされています。</span><span class="sxs-lookup"><span data-stu-id="a9941-123">Not all standards have been tested.</span></span> <span data-ttu-id="a9941-124">通常、WCF によってサポートされる標準でサポートされても[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="a9941-124">Typically, the standards supported by WCF are also supported by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="a9941-125">サンプルの標準は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="a9941-125">Sample standards include:</span></span>  
  
-   <span data-ttu-id="a9941-126">WS-ReliableMessaging</span><span class="sxs-lookup"><span data-stu-id="a9941-126">WS-ReliableMessaging</span></span>  
  
-   <span data-ttu-id="a9941-127">WS-Security</span><span class="sxs-lookup"><span data-stu-id="a9941-127">WS-Security</span></span>  
  
-   <span data-ttu-id="a9941-128">Ws-secureconversation</span><span class="sxs-lookup"><span data-stu-id="a9941-128">WS-SecureConversation</span></span>  
  
-   <span data-ttu-id="a9941-129">Ws-trust</span><span class="sxs-lookup"><span data-stu-id="a9941-129">WS-Trust</span></span>  
  
-   <span data-ttu-id="a9941-130">WS フェデレーション</span><span class="sxs-lookup"><span data-stu-id="a9941-130">WS-Federation</span></span>  
  
-   <span data-ttu-id="a9941-131">WS-Addressing</span><span class="sxs-lookup"><span data-stu-id="a9941-131">WS-Addressing</span></span>  
  
-   <span data-ttu-id="a9941-132">Ws-policy</span><span class="sxs-lookup"><span data-stu-id="a9941-132">WS-Policy</span></span>  
  
-   <span data-ttu-id="a9941-133">WS-MetadataExchange</span><span class="sxs-lookup"><span data-stu-id="a9941-133">WS-MetadataExchange</span></span>  
  
-   <span data-ttu-id="a9941-134">Ws-coordination</span><span class="sxs-lookup"><span data-stu-id="a9941-134">WS-Coordination</span></span>  
  
-   <span data-ttu-id="a9941-135">Ws-atomic</span><span class="sxs-lookup"><span data-stu-id="a9941-135">WS-Atomic</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a9941-136">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="a9941-136">In This Section</span></span>  
  
-   [<span data-ttu-id="a9941-137">Web サービスの利用</span><span class="sxs-lookup"><span data-stu-id="a9941-137">Consuming Web Services</span></span>](../core/consuming-web-services.md)  
  
-   [<span data-ttu-id="a9941-138">Web サービスの公開</span><span class="sxs-lookup"><span data-stu-id="a9941-138">Publishing Web Services</span></span>](../core/publishing-web-services.md)  
  
-   [<span data-ttu-id="a9941-139">SOAP ヘッダーの使用</span><span class="sxs-lookup"><span data-stu-id="a9941-139">Using SOAP Headers</span></span>](../core/using-soap-headers.md)