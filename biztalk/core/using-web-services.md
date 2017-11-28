---
title: "Web サービスの使用 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Web services
- Web services, about Web services
- orchestrations, Web services
- Web services, orchestrations
ms.assetid: a54261e3-d8ef-4770-8d9a-147685846051
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 236acb42c010effe5c3d45cde1daaf9a7097ede5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="using-web-services"></a><span data-ttu-id="02b9a-102">Web サービスの使用</span><span class="sxs-lookup"><span data-stu-id="02b9a-102">Using Web Services</span></span>
<span data-ttu-id="02b9a-103">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、Web サービスの組み込みサポートが提供されています。</span><span class="sxs-lookup"><span data-stu-id="02b9a-103">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] provides built-in support for Web services.</span></span> <span data-ttu-id="02b9a-104">BizTalk Server は、既存のすべての Web サービスを再利用し、オーケストレーション内に集約できます。</span><span class="sxs-lookup"><span data-stu-id="02b9a-104">BizTalk Server enables the reuse and aggregation of all your existing Web services within your orchestrations.</span></span> <span data-ttu-id="02b9a-105">また、オーケストレーションを Web サービスとして公開し、Web サービス ロジックとビジネス プロセス ロジックを区別することもできます。</span><span class="sxs-lookup"><span data-stu-id="02b9a-105">You can also publish (expose) your orchestrations as Web services to separate the Web service logic from the business process logic.</span></span>  
  
 <span data-ttu-id="02b9a-106">BizTalk Server は、Web サービスのネイティブ アダプタのサポートを実装しています。</span><span class="sxs-lookup"><span data-stu-id="02b9a-106">BizTalk Server implements support for native adapters in Web services.</span></span> <span data-ttu-id="02b9a-107">ネイティブ アダプタのサポートにより、コードを記述しなくても、Web サービスのスケーラビリティ、フォールト トレランス、および追跡の機能を利用できます。</span><span class="sxs-lookup"><span data-stu-id="02b9a-107">Native adapter support provides scalability, fault tolerance, and tracking capabilities for Web services without writing a single line of code.</span></span> <span data-ttu-id="02b9a-108">SOAP アダプタについては、次を参照してください。 [SOAP アダプター](../core/soap-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="02b9a-108">For information about the SOAP adapter, see [SOAP Adapter](../core/soap-adapter.md).</span></span>  
  
 <span data-ttu-id="02b9a-109">BizTalk Server での Web サービスのサポートは、Web サービスの使用または呼び出しと、Web サービスの公開または作成の 2 つのカテゴリに分類されます。</span><span class="sxs-lookup"><span data-stu-id="02b9a-109">The Web services support in BizTalk Server falls into two categories: consuming or calling Web services and publishing or creating Web services.</span></span>  
  
 <span data-ttu-id="02b9a-110">Web サービスを利用または公開する前に、ASP.NET の XML Web サービスについて理解しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="02b9a-110">Before you consume or publish a Web service, you should have an understanding of XML Web services in ASP.NET.</span></span> <span data-ttu-id="02b9a-111">XML Web サービスの基本についての説明についてにある「XML Web サービスの基本事項」の記事を参照してください。 [http://go.microsoft.com/fwlink/?LinkId=193057](http://go.microsoft.com/fwlink/?LinkId=193057)です。</span><span class="sxs-lookup"><span data-stu-id="02b9a-111">For information about the basics of XML Web services, see the article "XML Web Services Basics" at [http://go.microsoft.com/fwlink/?LinkId=193057](http://go.microsoft.com/fwlink/?LinkId=193057).</span></span>  
  
 <span data-ttu-id="02b9a-112">**Web サービスの使用**</span><span class="sxs-lookup"><span data-stu-id="02b9a-112">**Consuming Web services**</span></span>  
  
 <span data-ttu-id="02b9a-113">Web サービスは、オーケストレーション内から利用 (呼び出し) できます。</span><span class="sxs-lookup"><span data-stu-id="02b9a-113">You can consume (call) Web services from within an orchestration.</span></span> <span data-ttu-id="02b9a-114">複数の Web サービスを 1 つのオーケストレーションに集約して、ビジネス プロセス全体を完了できます。</span><span class="sxs-lookup"><span data-stu-id="02b9a-114">You can aggregate several Web services into single orchestration to complete an entire business process.</span></span>  
  
 <span data-ttu-id="02b9a-115">**Web サービスの公開**</span><span class="sxs-lookup"><span data-stu-id="02b9a-115">**Publishing Web services**</span></span>  
  
 <span data-ttu-id="02b9a-116">BizTalk Web サービス公開ウィザードを使用して、Web サービスを公開できます。</span><span class="sxs-lookup"><span data-stu-id="02b9a-116">You can publish Web services using the BizTalk Web Services Publishing Wizard.</span></span> <span data-ttu-id="02b9a-117">オーケストレーションおよび送信アダプタでは、これらの公開された Web サービスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="02b9a-117">Orchestrations and send adapters can use these published Web services.</span></span>  
  
 <span data-ttu-id="02b9a-118">**SOAP ヘッダーの使用**</span><span class="sxs-lookup"><span data-stu-id="02b9a-118">**Using SOAP headers**</span></span>  
  
 <span data-ttu-id="02b9a-119">BizTalk Server では、定義済みの SOAP ヘッダーと不明な SOAP ヘッダーがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="02b9a-119">BizTalk Server provides support for defined and unknown SOAP headers.</span></span> <span data-ttu-id="02b9a-120">定義済みの各 SOAP ヘッダーのコンテキスト プロパティが BizTalk Server によって Web サービス内に作成されます。</span><span class="sxs-lookup"><span data-stu-id="02b9a-120">BizTalk Server creates a context property for each defined SOAP header in the Web service.</span></span>  
  
 <span data-ttu-id="02b9a-121">**Web サービス標準**</span><span class="sxs-lookup"><span data-stu-id="02b9a-121">**Web Services standards**</span></span>  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="02b9a-122"> は、送受信の際に任意の Web サービス標準に対応して動作します。</span><span class="sxs-lookup"><span data-stu-id="02b9a-122"> should work with any Web Services standards when sending and receiving.</span></span> <span data-ttu-id="02b9a-123">すべての標準がテストされているわけではありません。</span><span class="sxs-lookup"><span data-stu-id="02b9a-123">Not all standards have been tested.</span></span> <span data-ttu-id="02b9a-124">一般的に、WCF によってサポートされる標準は [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] でもサポートされます。</span><span class="sxs-lookup"><span data-stu-id="02b9a-124">Typically, the standards supported by WCF are also supported by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="02b9a-125">サポートされる標準には、次のものがあります。</span><span class="sxs-lookup"><span data-stu-id="02b9a-125">Sample standards include:</span></span>  
  
-   <span data-ttu-id="02b9a-126">WS-ReliableMessaging</span><span class="sxs-lookup"><span data-stu-id="02b9a-126">WS-ReliableMessaging</span></span>  
  
-   <span data-ttu-id="02b9a-127">WS-Security</span><span class="sxs-lookup"><span data-stu-id="02b9a-127">WS-Security</span></span>  
  
-   <span data-ttu-id="02b9a-128">WS-SecureConversation</span><span class="sxs-lookup"><span data-stu-id="02b9a-128">WS-SecureConversation</span></span>  
  
-   <span data-ttu-id="02b9a-129">WS-Trust</span><span class="sxs-lookup"><span data-stu-id="02b9a-129">WS-Trust</span></span>  
  
-   <span data-ttu-id="02b9a-130">WS-Federation</span><span class="sxs-lookup"><span data-stu-id="02b9a-130">WS-Federation</span></span>  
  
-   <span data-ttu-id="02b9a-131">WS-Addressing</span><span class="sxs-lookup"><span data-stu-id="02b9a-131">WS-Addressing</span></span>  
  
-   <span data-ttu-id="02b9a-132">WS-Policy</span><span class="sxs-lookup"><span data-stu-id="02b9a-132">WS-Policy</span></span>  
  
-   <span data-ttu-id="02b9a-133">WS-MetadataExchange</span><span class="sxs-lookup"><span data-stu-id="02b9a-133">WS-MetadataExchange</span></span>  
  
-   <span data-ttu-id="02b9a-134">WS-Coordination</span><span class="sxs-lookup"><span data-stu-id="02b9a-134">WS-Coordination</span></span>  
  
-   <span data-ttu-id="02b9a-135">WS-Atomic</span><span class="sxs-lookup"><span data-stu-id="02b9a-135">WS-Atomic</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="02b9a-136">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="02b9a-136">In This Section</span></span>  
  
-   [<span data-ttu-id="02b9a-137">Web サービスの使用</span><span class="sxs-lookup"><span data-stu-id="02b9a-137">Consuming Web Services</span></span>](../core/consuming-web-services.md)  
  
-   [<span data-ttu-id="02b9a-138">Web サービスの公開</span><span class="sxs-lookup"><span data-stu-id="02b9a-138">Publishing Web Services</span></span>](../core/publishing-web-services.md)  
  
-   [<span data-ttu-id="02b9a-139">SOAP ヘッダーの使用</span><span class="sxs-lookup"><span data-stu-id="02b9a-139">Using SOAP Headers</span></span>](../core/using-soap-headers.md)