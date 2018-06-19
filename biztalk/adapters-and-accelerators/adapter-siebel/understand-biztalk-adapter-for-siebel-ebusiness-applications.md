---
title: Siebel eBusiness Applications の BizTalk アダプターを理解する |Microsoft ドキュメント
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
ms.openlocfilehash: 51c3576df5f62a0350f85d79b603c9f1cbda8a60
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25962616"
---
# <a name="understand-biztalk-adapter-for-siebel-ebusiness-applications"></a><span data-ttu-id="aa944-102">Siebel eBusiness Applications の BizTalk アダプターを理解します。</span><span class="sxs-lookup"><span data-stu-id="aa944-102">Understand BizTalk Adapter for Siebel eBusiness Applications</span></span>
<span data-ttu-id="aa944-103">[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]外部システムと対話するためにサービス指向のプログラムによるアクセスを有効にします。</span><span class="sxs-lookup"><span data-stu-id="aa944-103">The [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] enables service-oriented programmatic access in order to interact with an external system.</span></span> <span data-ttu-id="aa944-104">アダプターでは、次の利点をクライアントに使用します。</span><span class="sxs-lookup"><span data-stu-id="aa944-104">The adapters provide the following advantages to clients:</span></span>  
  
-   <span data-ttu-id="aa944-105">**デザイン時のエクスペリエンスを一貫した**です。</span><span class="sxs-lookup"><span data-stu-id="aa944-105">**Consistent design-time experience**.</span></span> <span data-ttu-id="aa944-106">アダプターは、参照、検索、および LOB アーティファクトのメタデータを取得するための一般的なとわかりやすいデザイン時のエクスペリエンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="aa944-106">The adapters provide a common and user-friendly design time experience for browsing, searching, and retrieving metadata of LOB artifacts.</span></span>  
  
-   <span data-ttu-id="aa944-107">**さまざまなプログラミング オプション**です。</span><span class="sxs-lookup"><span data-stu-id="aa944-107">**Varied programming options**.</span></span> <span data-ttu-id="aa944-108">アダプターは、Windows Communication Foundation (WCF) などのプログラミング モデルの選択肢を提供するチャネル モデルを WCF サービス モデルでは、ADO.NET、Web サービス、または BizTalk は、モデルをサポートします。</span><span class="sxs-lookup"><span data-stu-id="aa944-108">The adapters provide a choice of programming model including Windows Communication Foundation (WCF) channel model, WCF service model, ADO.NET, Web services, or BizTalk supported models.</span></span>  
  
-   <span data-ttu-id="aa944-109">**Lob の間でのエクスペリエンス、統一された**です。</span><span class="sxs-lookup"><span data-stu-id="aa944-109">**Uniform experience across LOBs**.</span></span> <span data-ttu-id="aa944-110">使用して、WCF アダプターを標準化および[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]でき、したがって一貫した環境での任意の LOB システムへのアクセスを取得します。</span><span class="sxs-lookup"><span data-stu-id="aa944-110">The adapters standardize on using the WCF and [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)] and hence provide a uniform experience of gaining access to any LOB system.</span></span>  
  
 <span data-ttu-id="aa944-111">前述のように、アダプターは、上に組み込ま、[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="aa944-111">As mentioned, the adapters are built on top of the [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)].</span></span> <span data-ttu-id="aa944-112">[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]のさまざまな BizTalk Server および Microsoft Office などのクライアント アプリケーションで使用できる統合アダプターを構築するための共通の基本を提供します。</span><span class="sxs-lookup"><span data-stu-id="aa944-112">The [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] provides a common basis for building integration adapters that a variety of client applications such as BizTalk Server and Microsoft Office can consume.</span></span> <span data-ttu-id="aa944-113">[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]が Windows Communication Foundation (WCF) チャネルとの統合アダプターを公開することにより、アダプター戦略の Microsoft サービスの戦略を揃えて配置します。</span><span class="sxs-lookup"><span data-stu-id="aa944-113">The [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] aligns the adapter strategy with the Microsoft Services strategy by exposing integration adapters as Windows Communication Foundation (WCF) channels.</span></span> <span data-ttu-id="aa944-114">詳細については、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]を参照してください、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]ドキュメント。</span><span class="sxs-lookup"><span data-stu-id="aa944-114">For more information about the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], see the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] documentation.</span></span> <span data-ttu-id="aa944-115">と共に、ドキュメントがインストールされている、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]通常 \<インストール ドライブ\>: \Program Files\\[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]\Documents です。</span><span class="sxs-lookup"><span data-stu-id="aa944-115">The documentation is installed along with the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], typically under \<installation drive\>:\Program Files\\[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]\Documents.</span></span>  
  
 <span data-ttu-id="aa944-116">Siebel システムでの操作を行うには、Siebel システムによって公開されるビジネス サービスへのアクセスがアダプターのクライアントに必要です。</span><span class="sxs-lookup"><span data-stu-id="aa944-116">To perform operations on a Siebel system, adapter clients must have access to business services exposed by the Siebel system.</span></span> <span data-ttu-id="aa944-117">Siebel アプリケーションでは、ビジネス コンポーネントとビジネス オブジェクト データを公開します。</span><span class="sxs-lookup"><span data-stu-id="aa944-117">A Siebel application exposes data as business components and business objects.</span></span> <span data-ttu-id="aa944-118">Siebel*ビジネス コンポーネント*を 1 つの構造に 1 つまたは複数のテーブルの列を関連付ける論理エンティティです。</span><span class="sxs-lookup"><span data-stu-id="aa944-118">A Siebel *business component* is a logical entity that associates columns from one or more tables into a single structure.</span></span> <span data-ttu-id="aa944-119">Siebel*ビジネス オブジェクト*一連の相互に関連するビジネス コンポーネントの連携により、ビジネス モデルを実装します。</span><span class="sxs-lookup"><span data-stu-id="aa944-119">A Siebel *business object* implements a business model by tying together a set of interrelated business components.</span></span> <span data-ttu-id="aa944-120">[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]アダプターのクライアントは、Siebel ビジネス オブジェクトとビジネス コンポーネントを表示できます。</span><span class="sxs-lookup"><span data-stu-id="aa944-120">With the [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)], adapter clients can surface Siebel business objects and business components.</span></span>  
  
 <span data-ttu-id="aa944-121">[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]も含まれています、 [!INCLUDE[adoprovidersiebellong](../../includes/adoprovidersiebellong-md.md)] ([!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)])。</span><span class="sxs-lookup"><span data-stu-id="aa944-121">The [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] also includes the [!INCLUDE[adoprovidersiebellong](../../includes/adoprovidersiebellong-md.md)] ([!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]).</span></span> <span data-ttu-id="aa944-122">[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] ADO.NET インターフェイスを拡張することによって、Siebel システムへの ADO インターフェイスを提供します。</span><span class="sxs-lookup"><span data-stu-id="aa944-122">The [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] provides an ADO interface to a Siebel system by extending ADO.NET interfaces.</span></span>  
  
 <span data-ttu-id="aa944-123">このセクションでの機能について説明します、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]と[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="aa944-123">This section discusses the features of the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] and the [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="aa944-124">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="aa944-124">In This Section</span></span>  
  
-   [<span data-ttu-id="aa944-125">BizTalk Adapter for Siebel eBusiness Applications の概要</span><span class="sxs-lookup"><span data-stu-id="aa944-125">Overview of BizTalk Adapter for Siebel eBusiness Applications</span></span>](../../adapters-and-accelerators/adapter-siebel/overview-of-biztalk-adapter-for-siebel-ebusiness-applications.md)  
  
-   [<span data-ttu-id="aa944-126">Siebel アダプターの主要な機能</span><span class="sxs-lookup"><span data-stu-id="aa944-126">Key Features in the Siebel Adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/key-features-in-the-siebel-adapter.md) 
  
-   [<span data-ttu-id="aa944-127">BizTalk Adapter for Siebel eBusiness Applications の制限事項</span><span class="sxs-lookup"><span data-stu-id="aa944-127">Limitations of BizTalk Adapter for Siebel eBusiness Applications</span></span>](../../adapters-and-accelerators/adapter-siebel/limitations-of-biztalk-adapter-for-siebel-ebusiness-applications.md)  
  
-   [<span data-ttu-id="aa944-128">Data Provider for Siebel について</span><span class="sxs-lookup"><span data-stu-id="aa944-128">About the Data Provider for Siebel</span></span>](../../adapters-and-accelerators/adapter-siebel/about-the-data-provider-for-siebel.md)