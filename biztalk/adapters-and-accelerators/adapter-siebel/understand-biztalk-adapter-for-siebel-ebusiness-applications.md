---
title: BizTalk Adapter for Siebel eBusiness Applications について |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- adapter features
- features of Siebel adapters
- adapters, features
- adapter, overview
ms.assetid: 3249fb74-9ca1-4b81-971d-5151a2e354fe
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 788db9ba048141256cfaa3cc5017fa48bd6ec7de
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999235"
---
# <a name="understand-biztalk-adapter-for-siebel-ebusiness-applications"></a><span data-ttu-id="6aaf8-102">BizTalk Adapter for Siebel eBusiness Applications についてください。</span><span class="sxs-lookup"><span data-stu-id="6aaf8-102">Understand BizTalk Adapter for Siebel eBusiness Applications</span></span>
<span data-ttu-id="6aaf8-103">[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]外部システムと対話するためにサービス指向のプログラムによるアクセスを使用します。</span><span class="sxs-lookup"><span data-stu-id="6aaf8-103">The [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] enables service-oriented programmatic access in order to interact with an external system.</span></span> <span data-ttu-id="6aaf8-104">アダプターは、次の利点をクライアントに提供します。</span><span class="sxs-lookup"><span data-stu-id="6aaf8-104">The adapters provide the following advantages to clients:</span></span>  
  
- <span data-ttu-id="6aaf8-105">**デザイン時エクスペリエンスの一貫性のある**します。</span><span class="sxs-lookup"><span data-stu-id="6aaf8-105">**Consistent design-time experience**.</span></span> <span data-ttu-id="6aaf8-106">アダプターは、参照、検索、および LOB アーティファクトのメタデータを取得するための一般的な使いやすいもののデザイン時のエクスペリエンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="6aaf8-106">The adapters provide a common and user-friendly design time experience for browsing, searching, and retrieving metadata of LOB artifacts.</span></span>  
  
- <span data-ttu-id="6aaf8-107">**プログラミングのオプションをさまざまな**します。</span><span class="sxs-lookup"><span data-stu-id="6aaf8-107">**Varied programming options**.</span></span> <span data-ttu-id="6aaf8-108">アダプターは、Windows Communication Foundation (WCF) などのプログラミング モデルの選択肢を提供するチャネル モデルでは、WCF サービス モデルでは、ADO.NET、Web サービス、または BizTalk には、モデルがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="6aaf8-108">The adapters provide a choice of programming model including Windows Communication Foundation (WCF) channel model, WCF service model, ADO.NET, Web services, or BizTalk supported models.</span></span>  
  
- <span data-ttu-id="6aaf8-109">**Lob の間でのエクスペリエンス、統一された**します。</span><span class="sxs-lookup"><span data-stu-id="6aaf8-109">**Uniform experience across LOBs**.</span></span> <span data-ttu-id="6aaf8-110">アダプターが、WCF を使用して標準と[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]し、そのため、LOB システムへのアクセスのエクスペリエンスの一貫性を提供します。</span><span class="sxs-lookup"><span data-stu-id="6aaf8-110">The adapters standardize on using the WCF and [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)] and hence provide a uniform experience of gaining access to any LOB system.</span></span>  
  
  <span data-ttu-id="6aaf8-111">前述のように、アダプターは WCF LOB Adapter SDK の上に構築されます。</span><span class="sxs-lookup"><span data-stu-id="6aaf8-111">As mentioned, the adapters are built on top of the WCF LOB Adapter SDK.</span></span> <span data-ttu-id="6aaf8-112">WCF LOB Adapter SDK は、さまざまな BizTalk Server および Microsoft Office などのクライアント アプリケーションが使用できる統合アダプターを構築するための共通の基盤を提供します。</span><span class="sxs-lookup"><span data-stu-id="6aaf8-112">The WCF LOB Adapter SDK provides a common basis for building integration adapters that a variety of client applications such as BizTalk Server and Microsoft Office can consume.</span></span> <span data-ttu-id="6aaf8-113">WCF LOB Adapter SDK は、Windows Communication Foundation (WCF) チャネルとしての統合アダプターを公開することで、Microsoft のサービスを使用したアダプターの戦略を配置します。</span><span class="sxs-lookup"><span data-stu-id="6aaf8-113">The WCF LOB Adapter SDK aligns the adapter strategy with the Microsoft Services strategy by exposing integration adapters as Windows Communication Foundation (WCF) channels.</span></span> <span data-ttu-id="6aaf8-114">WCF LOB Adapter SDK の詳細については、次を参照してください。 [WCF LOB Adapter SDK ドキュメント](../../adapters-and-accelerators/wcf-lob-adapter-sdk/microsoft-wcf-line-of-business-adapter-sdk-documentation.md)します。</span><span class="sxs-lookup"><span data-stu-id="6aaf8-114">For more information about the WCF LOB Adapter SDK, see [WCF LOB Adapter SDK documentation](../../adapters-and-accelerators/wcf-lob-adapter-sdk/microsoft-wcf-line-of-business-adapter-sdk-documentation.md).</span></span>
  
  <span data-ttu-id="6aaf8-115">Siebel システムの操作を実行するには、アダプター クライアントは、Siebel システムによって公開されるビジネス サービスにアクセスする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6aaf8-115">To perform operations on a Siebel system, adapter clients must have access to business services exposed by the Siebel system.</span></span> <span data-ttu-id="6aaf8-116">Siebel アプリケーションでは、ビジネス コンポーネントおよびビジネス オブジェクトとしてデータを公開します。</span><span class="sxs-lookup"><span data-stu-id="6aaf8-116">A Siebel application exposes data as business components and business objects.</span></span> <span data-ttu-id="6aaf8-117">Siebel*ビジネス コンポーネント*を 1 つまたは複数のテーブルの列を 1 つの構造に関連付ける論理エンティティです。</span><span class="sxs-lookup"><span data-stu-id="6aaf8-117">A Siebel *business component* is a logical entity that associates columns from one or more tables into a single structure.</span></span> <span data-ttu-id="6aaf8-118">Siebel*ビジネス オブジェクト*一連の相互に関連するビジネス コンポーネントの連携により、ビジネス モデルを実装します。</span><span class="sxs-lookup"><span data-stu-id="6aaf8-118">A Siebel *business object* implements a business model by tying together a set of interrelated business components.</span></span> <span data-ttu-id="6aaf8-119">[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]、アダプター クライアントは、Siebel ビジネス オブジェクトおよびビジネス コンポーネントを表示できます。</span><span class="sxs-lookup"><span data-stu-id="6aaf8-119">With the [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)], adapter clients can surface Siebel business objects and business components.</span></span>  
  
  <span data-ttu-id="6aaf8-120">[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]も含まれています、 [!INCLUDE[adoprovidersiebellong](../../includes/adoprovidersiebellong-md.md)] ([!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)])。</span><span class="sxs-lookup"><span data-stu-id="6aaf8-120">The [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] also includes the [!INCLUDE[adoprovidersiebellong](../../includes/adoprovidersiebellong-md.md)] ([!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]).</span></span> <span data-ttu-id="6aaf8-121">[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] ADO.NET インターフェイスを拡張することで Siebel システムへの ADO インターフェイスを提供します。</span><span class="sxs-lookup"><span data-stu-id="6aaf8-121">The [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] provides an ADO interface to a Siebel system by extending ADO.NET interfaces.</span></span>  
  
  <span data-ttu-id="6aaf8-122">このセクションには、機能がについて説明します、 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] 、[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="6aaf8-122">This section discusses the features of the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] and the [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6aaf8-123">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="6aaf8-123">In This Section</span></span>  
  
-   [<span data-ttu-id="6aaf8-124">BizTalk Adapter for Siebel eBusiness Applications の概要</span><span class="sxs-lookup"><span data-stu-id="6aaf8-124">Overview of BizTalk Adapter for Siebel eBusiness Applications</span></span>](../../adapters-and-accelerators/adapter-siebel/overview-of-biztalk-adapter-for-siebel-ebusiness-applications.md)  
  
-   [<span data-ttu-id="6aaf8-125">Siebel アダプターの主要な機能</span><span class="sxs-lookup"><span data-stu-id="6aaf8-125">Key Features in the Siebel Adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/key-features-in-the-siebel-adapter.md) 
  
-   [<span data-ttu-id="6aaf8-126">BizTalk Adapter for Siebel eBusiness Applications の制限事項</span><span class="sxs-lookup"><span data-stu-id="6aaf8-126">Limitations of BizTalk Adapter for Siebel eBusiness Applications</span></span>](../../adapters-and-accelerators/adapter-siebel/limitations-of-biztalk-adapter-for-siebel-ebusiness-applications.md)  
  
-   [<span data-ttu-id="6aaf8-127">Data Provider for Siebel について</span><span class="sxs-lookup"><span data-stu-id="6aaf8-127">About the Data Provider for Siebel</span></span>](../../adapters-and-accelerators/adapter-siebel/about-the-data-provider-for-siebel.md)