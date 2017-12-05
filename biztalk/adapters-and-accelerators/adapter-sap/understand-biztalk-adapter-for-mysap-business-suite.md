---
title: "MySAP Business Suite の BizTalk アダプターを理解する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- adapter features
- adapters, features
- .NET Framework Data Provider for mySAP Business Suite
- Data Provider for SAP
- features of SAP adapter
- adapters, about SAP ADO Provider
ms.assetid: 136ca828-2724-454b-9d4d-a491d45e1eda
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b5d04c435208e316c343ac7b307943e0f91b8af7
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="understand-biztalk-adapter-for-mysap-business-suite"></a><span data-ttu-id="63239-102">MySAP Business Suite の BizTalk アダプターを理解します。</span><span class="sxs-lookup"><span data-stu-id="63239-102">Understand BizTalk Adapter for mySAP Business Suite</span></span>
<span data-ttu-id="63239-103">[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]外部システムと対話するためにサービス指向のプログラムによるアクセスを有効にします。</span><span class="sxs-lookup"><span data-stu-id="63239-103">The [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] enables service-oriented programmatic access in order to interact with an external system.</span></span> <span data-ttu-id="63239-104">アダプターでは、次の利点をクライアントに使用します。</span><span class="sxs-lookup"><span data-stu-id="63239-104">The adapters provide the following advantages to clients:</span></span>  
  
-   <span data-ttu-id="63239-105">**デザイン時のエクスペリエンスを一貫した**です。</span><span class="sxs-lookup"><span data-stu-id="63239-105">**Consistent design-time experience**.</span></span> <span data-ttu-id="63239-106">アダプターは、参照、検索、および LOB アーティファクトのメタデータを取得するための一般的なとわかりやすいデザイン時のエクスペリエンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="63239-106">The adapters provide a common and user-friendly design time experience for browsing, searching, and retrieving metadata of LOB artifacts.</span></span>  
  
-   <span data-ttu-id="63239-107">**さまざまなプログラミング オプション**です。</span><span class="sxs-lookup"><span data-stu-id="63239-107">**Varied programming options**.</span></span> <span data-ttu-id="63239-108">アダプターは、プログラミング モデル Windows Communication Foundation (WCF) チャネル モデルを含む、WCF サービスのモデル、ADO.NET、web サービス、またはサポートされている BizTalk モデルの選択肢を提供します。</span><span class="sxs-lookup"><span data-stu-id="63239-108">The adapters provide a choice of programming model including Windows Communication Foundation (WCF) channel model, WCF service model, ADO.NET, web services, or BizTalk supported models.</span></span>  
  
-   <span data-ttu-id="63239-109">**Lob の間でのエクスペリエンス、統一された**です。</span><span class="sxs-lookup"><span data-stu-id="63239-109">**Uniform experience across LOBs**.</span></span> <span data-ttu-id="63239-110">使用して、WCF アダプターを標準化および[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]でき、したがって一貫した環境での任意の LOB システムへのアクセスを取得します。</span><span class="sxs-lookup"><span data-stu-id="63239-110">The adapters standardize on using the WCF and [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)] and hence provide a uniform experience of gaining access to any LOB system.</span></span>  
  
 <span data-ttu-id="63239-111">前述のように、アダプターは、上に組み込ま、[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="63239-111">As mentioned, the adapters are built on top of the [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)].</span></span> <span data-ttu-id="63239-112">[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]のさまざまな BizTalk Server および Microsoft Office などのクライアント アプリケーションで使用できる統合アダプターを構築するための共通の基本を提供します。</span><span class="sxs-lookup"><span data-stu-id="63239-112">The [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] provides a common basis for building integration adapters that a variety of client applications such as BizTalk Server and Microsoft Office can consume.</span></span> <span data-ttu-id="63239-113">[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]が Windows Communication Foundation (WCF) チャネルとの統合アダプターを公開することにより、アダプター戦略の Microsoft サービスの戦略を揃えて配置します。</span><span class="sxs-lookup"><span data-stu-id="63239-113">The [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] aligns the adapter strategy with the Microsoft Services strategy by exposing integration adapters as Windows Communication Foundation (WCF) channels.</span></span> <span data-ttu-id="63239-114">詳細については、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]を参照してください、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]ドキュメント。</span><span class="sxs-lookup"><span data-stu-id="63239-114">For more information about the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], see the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] documentation.</span></span> <span data-ttu-id="63239-115">と共に、ドキュメントがインストールされている、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]通常 \<インストール ドライブ\>: \Program Files\\[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]\Documents です。</span><span class="sxs-lookup"><span data-stu-id="63239-115">The documentation is installed along with the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], typically under \<installation drive\>:\Program Files\\[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]\Documents.</span></span>  
  
 <span data-ttu-id="63239-116">SAP システムに対して操作を実行するには、アダプターのクライアントは、関連するリモート関数呼び出し (Rfc)、ビジネス アプリケーション プログラミング インターフェイス (Bapi) と Idoc (中級者向けのドキュメント) へのアクセスが必要です。</span><span class="sxs-lookup"><span data-stu-id="63239-116">To perform operations on an SAP system, adapter clients must have access to the relevant Remote Function Calls (RFCs), Business Application Programming Interfaces (BAPIs), and IDOCs (or intermediate documents).</span></span> <span data-ttu-id="63239-117">SAP R/3 システムは、ビジネスの統合の Rfc、Bapi、および Idoc を公開します。</span><span class="sxs-lookup"><span data-stu-id="63239-117">An SAP R/3 system exposes RFCs, BAPIs, and IDOCs for business integration.</span></span> <span data-ttu-id="63239-118">Rfc は、特定のビジネス ロジックを実装しているリモート関数モジュールです。</span><span class="sxs-lookup"><span data-stu-id="63239-118">RFCs are remote function modules that implement specific business logic.</span></span> <span data-ttu-id="63239-119">このロジックは、BizTalk Server など、外部アプリケーションまたは .NET アプリケーションから呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="63239-119">This logic can be invoked from an external application such as BizTalk Server or a .NET application.</span></span> <span data-ttu-id="63239-120">Bapi は、標準の RFC インターフェイスを介して公開されるさらに、SAP ビジネス オブジェクトをメソッドのインターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="63239-120">BAPIs are method interfaces to SAP business objects, which are in turn exposed through standard RFC interfaces.</span></span> <span data-ttu-id="63239-121">Idoc は、SAP および SAP 以外のシステム間の通信には、電子データ交換 (EDI) 通信レイヤーを抽象化するメカニズムです。</span><span class="sxs-lookup"><span data-stu-id="63239-121">IDOCs are a mechanism to abstract the electronic data interchange (EDI) communication layer for communication between SAP and non-SAP systems.</span></span> <span data-ttu-id="63239-122">[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]Idoc が SAP システムによって公開される、Rfc、Bapi にアクセスすることができます。</span><span class="sxs-lookup"><span data-stu-id="63239-122">With [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)], you can access the RFCs, BAPIs, and IDOCs exposed by an SAP system.</span></span>  
  
 <span data-ttu-id="63239-123">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]も含まれています[!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)]、SAP システムの ADO インターフェイスを提供します。</span><span class="sxs-lookup"><span data-stu-id="63239-123">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] also includes [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)], which provides an ADO interface to the SAP system.</span></span>  
  
 <span data-ttu-id="63239-124">このセクションの機能の一覧、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]と[!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="63239-124">This section lists the features for the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] and the [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="63239-125">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="63239-125">In This Section</span></span>  
  
-   [<span data-ttu-id="63239-126">BizTalk adapter 用 mySAP Business Suite のアーキテクチャの概要</span><span class="sxs-lookup"><span data-stu-id="63239-126">Architecture overview of BizTalk Adapter for mySAP Business Suite</span></span>](../../adapters-and-accelerators/adapter-sap/architecture-overview-of-the-biztalk-adapter-for-mysap-business-suite.md)  
  
-   [<span data-ttu-id="63239-127">SAP アダプターの主要な機能</span><span class="sxs-lookup"><span data-stu-id="63239-127">Key Features in the SAP Adapter</span></span>](../../adapters-and-accelerators/adapter-sap/key-features-in-the-sap-adapter.md)  
  
-   [<span data-ttu-id="63239-128">BizTalk Adapter for mySAP Business Suite の制限事項</span><span class="sxs-lookup"><span data-stu-id="63239-128">Limitations of BizTalk Adapter for mySAP Business Suite</span></span>](../../adapters-and-accelerators/adapter-sap/limitations-of-biztalk-adapter-for-mysap-business-suite.md)  
  
-   [<span data-ttu-id="63239-129">.NET Framework Data Provider for mySAP Business Suite について</span><span class="sxs-lookup"><span data-stu-id="63239-129">About the .NET Framework Data Provider for mySAP Business Suite</span></span>](../../adapters-and-accelerators/adapter-sap/about-the-net-framework-data-provider-for-mysap-business-suite.md)  
  
## <a name="see-also"></a><span data-ttu-id="63239-130">参照</span><span class="sxs-lookup"><span data-stu-id="63239-130">See Also</span></span>  
[<span data-ttu-id="63239-131">BizTalk Adapter 用 mySAP Business Suite の概要します。</span><span class="sxs-lookup"><span data-stu-id="63239-131">Get started with the BizTalk Adapter for mySAP Business Suite</span></span>](../../adapters-and-accelerators/adapter-sap/get-started-with-the-biztalk-adapter-for-mysap-business-suite.md)