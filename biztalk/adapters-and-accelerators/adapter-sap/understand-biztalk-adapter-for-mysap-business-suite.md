---
title: BizTalk Adapter for mySAP Business Suite について |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- adapter features
- adapters, features
- .NET Framework Data Provider for mySAP Business Suite
- Data Provider for SAP
- features of SAP adapter
- adapters, about SAP ADO Provider
ms.assetid: 136ca828-2724-454b-9d4d-a491d45e1eda
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c2a4b611184962138c102dfadc6f33250ce16a29
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65372235"
---
# <a name="understand-biztalk-adapter-for-mysap-business-suite"></a><span data-ttu-id="7ec44-102">BizTalk Adapter for mySAP Business Suite についてください。</span><span class="sxs-lookup"><span data-stu-id="7ec44-102">Understand BizTalk Adapter for mySAP Business Suite</span></span>
<span data-ttu-id="7ec44-103">[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]外部システムと対話するためにサービス指向のプログラムによるアクセスを使用します。</span><span class="sxs-lookup"><span data-stu-id="7ec44-103">The [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] enables service-oriented programmatic access in order to interact with an external system.</span></span> <span data-ttu-id="7ec44-104">アダプターは、次の利点をクライアントに提供します。</span><span class="sxs-lookup"><span data-stu-id="7ec44-104">The adapters provide the following advantages to clients:</span></span>  
  
- <span data-ttu-id="7ec44-105">**デザイン時エクスペリエンスの一貫性のある**します。</span><span class="sxs-lookup"><span data-stu-id="7ec44-105">**Consistent design-time experience**.</span></span> <span data-ttu-id="7ec44-106">アダプターは、参照、検索、および LOB アーティファクトのメタデータを取得するための一般的な使いやすいもののデザイン時のエクスペリエンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="7ec44-106">The adapters provide a common and user-friendly design time experience for browsing, searching, and retrieving metadata of LOB artifacts.</span></span>  
  
- <span data-ttu-id="7ec44-107">**プログラミングのオプションをさまざまな**します。</span><span class="sxs-lookup"><span data-stu-id="7ec44-107">**Varied programming options**.</span></span> <span data-ttu-id="7ec44-108">アダプターは、さまざまなプログラミング モデルの Windows Communication Foundation (WCF) チャネル モデルを含む、WCF サービス モデル、ADO.NET、web サービス、または BizTalk がサポートされているモデルを提供します。</span><span class="sxs-lookup"><span data-stu-id="7ec44-108">The adapters provide a choice of programming model including Windows Communication Foundation (WCF) channel model, WCF service model, ADO.NET, web services, or BizTalk supported models.</span></span>  
  
- <span data-ttu-id="7ec44-109">**Lob の間でのエクスペリエンス、統一された**します。</span><span class="sxs-lookup"><span data-stu-id="7ec44-109">**Uniform experience across LOBs**.</span></span> <span data-ttu-id="7ec44-110">アダプターが、WCF を使用して標準と[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]し、そのため、LOB システムへのアクセスのエクスペリエンスの一貫性を提供します。</span><span class="sxs-lookup"><span data-stu-id="7ec44-110">The adapters standardize on using the WCF and [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)] and hence provide a uniform experience of gaining access to any LOB system.</span></span>  
  
  <span data-ttu-id="7ec44-111">前述のように、アダプターは WCF LOB Adapter SDK の上に構築されます。</span><span class="sxs-lookup"><span data-stu-id="7ec44-111">As mentioned, the adapters are built on top of the WCF LOB Adapter SDK.</span></span> <span data-ttu-id="7ec44-112">WCF LOB Adapter SDK は、さまざまな BizTalk Server および Microsoft Office などのクライアント アプリケーションが使用できる統合アダプターを構築するための共通の基盤を提供します。</span><span class="sxs-lookup"><span data-stu-id="7ec44-112">The WCF LOB Adapter SDK provides a common basis for building integration adapters that a variety of client applications such as BizTalk Server and Microsoft Office can consume.</span></span> <span data-ttu-id="7ec44-113">WCF LOB Adapter SDK は、Windows Communication Foundation (WCF) チャネルとしての統合アダプターを公開することで、Microsoft のサービスを使用したアダプターの戦略を配置します。</span><span class="sxs-lookup"><span data-stu-id="7ec44-113">The WCF LOB Adapter SDK aligns the adapter strategy with the Microsoft Services strategy by exposing integration adapters as Windows Communication Foundation (WCF) channels.</span></span> <span data-ttu-id="7ec44-114">WCF LOB Adapter SDK の詳細については、次を参照してください。 [WCF LOB Adapter SDK ドキュメント](../../adapters-and-accelerators/wcf-lob-adapter-sdk/microsoft-wcf-line-of-business-adapter-sdk-documentation.md)します。</span><span class="sxs-lookup"><span data-stu-id="7ec44-114">For more information about the WCF LOB Adapter SDK, see [WCF LOB Adapter SDK documentation](../../adapters-and-accelerators/wcf-lob-adapter-sdk/microsoft-wcf-line-of-business-adapter-sdk-documentation.md).</span></span>
  
  <span data-ttu-id="7ec44-115">SAP システムの操作を実行するには、アダプター クライアントは、関連するリモート関数呼び出し (Rfc)、ビジネス アプリケーション プログラミング インターフェイス (Bapi)、および Idoc (または中間ドキュメント) にアクセスする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7ec44-115">To perform operations on an SAP system, adapter clients must have access to the relevant Remote Function Calls (RFCs), Business Application Programming Interfaces (BAPIs), and IDOCs (or intermediate documents).</span></span> <span data-ttu-id="7ec44-116">SAP R/3 システムでは、ビジネスの統合の Rfc、Bapi、Idoc を公開します。</span><span class="sxs-lookup"><span data-stu-id="7ec44-116">An SAP R/3 system exposes RFCs, BAPIs, and IDOCs for business integration.</span></span> <span data-ttu-id="7ec44-117">Rfc は、特定のビジネス ロジックを実装するリモート関数モジュールです。</span><span class="sxs-lookup"><span data-stu-id="7ec44-117">RFCs are remote function modules that implement specific business logic.</span></span> <span data-ttu-id="7ec44-118">このロジックは、BizTalk Server などの外部アプリケーションまたは .NET アプリケーションから呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="7ec44-118">This logic can be invoked from an external application such as BizTalk Server or a .NET application.</span></span> <span data-ttu-id="7ec44-119">Bapi は、標準の RFC インターフェイスを通じて公開されるさらに、SAP ビジネス オブジェクトにメソッドのインターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="7ec44-119">BAPIs are method interfaces to SAP business objects, which are in turn exposed through standard RFC interfaces.</span></span> <span data-ttu-id="7ec44-120">Idoc は、SAP と SAP 以外のシステム間の通信には、電子データ交換 (EDI) 通信レイヤーを抽象化するメカニズムです。</span><span class="sxs-lookup"><span data-stu-id="7ec44-120">IDOCs are a mechanism to abstract the electronic data interchange (EDI) communication layer for communication between SAP and non-SAP systems.</span></span> <span data-ttu-id="7ec44-121">[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]Idoc が SAP システムによって公開される、Rfc、Bapi にアクセスすることができます。</span><span class="sxs-lookup"><span data-stu-id="7ec44-121">With [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)], you can access the RFCs, BAPIs, and IDOCs exposed by an SAP system.</span></span>  
  
  <span data-ttu-id="7ec44-122">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]も含まれています[!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)]、SAP システムへの ADO インターフェイスを提供します。</span><span class="sxs-lookup"><span data-stu-id="7ec44-122">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] also includes [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)], which provides an ADO interface to the SAP system.</span></span>  
  
  <span data-ttu-id="7ec44-123">このセクションの機能の一覧、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] 、[!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="7ec44-123">This section lists the features for the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] and the [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7ec44-124">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="7ec44-124">In This Section</span></span>  
  
-   [<span data-ttu-id="7ec44-125">BizTalk Adapter 用 mySAP Business Suite のアーキテクチャの概要</span><span class="sxs-lookup"><span data-stu-id="7ec44-125">Architecture overview of BizTalk Adapter for mySAP Business Suite</span></span>](../../adapters-and-accelerators/adapter-sap/architecture-overview-of-the-biztalk-adapter-for-mysap-business-suite.md)  
  
-   [<span data-ttu-id="7ec44-126">SAP アダプターの主な機能</span><span class="sxs-lookup"><span data-stu-id="7ec44-126">Key Features in the SAP Adapter</span></span>](../../adapters-and-accelerators/adapter-sap/key-features-in-the-sap-adapter.md)  
  
-   [<span data-ttu-id="7ec44-127">BizTalk Adapter for mySAP Business Suite の制限事項</span><span class="sxs-lookup"><span data-stu-id="7ec44-127">Limitations of BizTalk Adapter for mySAP Business Suite</span></span>](../../adapters-and-accelerators/adapter-sap/limitations-of-biztalk-adapter-for-mysap-business-suite.md)  
  
-   [<span data-ttu-id="7ec44-128">.NET Framework Data Provider for mySAP Business Suite について</span><span class="sxs-lookup"><span data-stu-id="7ec44-128">About the .NET Framework Data Provider for mySAP Business Suite</span></span>](../../adapters-and-accelerators/adapter-sap/about-the-net-framework-data-provider-for-mysap-business-suite.md)  
  
## <a name="see-also"></a><span data-ttu-id="7ec44-129">参照</span><span class="sxs-lookup"><span data-stu-id="7ec44-129">See Also</span></span>  
[<span data-ttu-id="7ec44-130">BizTalk Adapter for mySAP Business Suite の概要します。</span><span class="sxs-lookup"><span data-stu-id="7ec44-130">Get started with the BizTalk Adapter for mySAP Business Suite</span></span>](../../adapters-and-accelerators/adapter-sap/get-started-with-the-biztalk-adapter-for-mysap-business-suite.md)