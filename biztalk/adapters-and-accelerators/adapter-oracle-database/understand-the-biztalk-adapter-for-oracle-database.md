---
title: Oracle データベースの BizTalk アダプターの理解 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF LOB Adapter SDK
- features of Oracle database adapter
- table
- adapter client
- service model
- WCF
- artifacts
- database tables
- adapters, features
- Windows Communication Foundation
- adapter features
- channel model
ms.assetid: a8691957-0430-4cba-83f8-b60c21a86849
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6233044306df0ae03d3d1dd6b1a65b75129d1c37
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65375879"
---
# <a name="understand-the-biztalk-adapter-for-oracle-database"></a><span data-ttu-id="a7c41-102">Oracle データベースの BizTalk アダプターを理解します。</span><span class="sxs-lookup"><span data-stu-id="a7c41-102">Understand the BizTalk Adapter for Oracle Database</span></span>
<span data-ttu-id="a7c41-103">[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]外部システムと対話するためにサービス指向のプログラムによるアクセスを使用します。</span><span class="sxs-lookup"><span data-stu-id="a7c41-103">The [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] enables service-oriented programmatic access in order to interact with an external system.</span></span> <span data-ttu-id="a7c41-104">アダプターは、次の利点をクライアントに提供します。</span><span class="sxs-lookup"><span data-stu-id="a7c41-104">The adapters provide the following advantages to clients:</span></span>  
  
- <span data-ttu-id="a7c41-105">**デザイン時エクスペリエンスの一貫性のある**します。</span><span class="sxs-lookup"><span data-stu-id="a7c41-105">**Consistent design-time experience**.</span></span> <span data-ttu-id="a7c41-106">アダプターでは、参照、検索、および LOB アーティファクトのメタデータを取得するため、一般的な使いやすいもののデザイン時エクスペリエンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="a7c41-106">The adapters provide a common and user-friendly design-time experience for browsing, searching, and retrieving metadata of LOB artifacts.</span></span>  
  
- <span data-ttu-id="a7c41-107">**プログラミングのオプションをさまざまな**します。</span><span class="sxs-lookup"><span data-stu-id="a7c41-107">**Varied programming options**.</span></span> <span data-ttu-id="a7c41-108">アダプターは、WCF、Windows Communication Foundation (WCF) チャネル モデルなどのプログラミング モデルの選択したサービス モデルでは、ADO.NET、Web サービス、または BizTalk には、モデルがサポートされているを提供します。</span><span class="sxs-lookup"><span data-stu-id="a7c41-108">The adapters provide a choice of programming model including the Windows Communication Foundation (WCF) channel model, WCF service model, ADO.NET, Web services, or BizTalk supported models.</span></span>  
  
- <span data-ttu-id="a7c41-109">**Lob の間でのエクスペリエンス、統一された**します。</span><span class="sxs-lookup"><span data-stu-id="a7c41-109">**Uniform experience across LOBs**.</span></span> <span data-ttu-id="a7c41-110">WCF を使用して、アダプターを標準化および[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]、し、そのため、LOB システムへのアクセスのエクスペリエンスの一貫性を提供します。</span><span class="sxs-lookup"><span data-stu-id="a7c41-110">The adapters standardize on using WCF and [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)], and hence provide a uniform experience of gaining access to any LOB system.</span></span>  
  
  <span data-ttu-id="a7c41-111">前述のように、アダプターは WCF LOB Adapter SDK の上に構築されます。</span><span class="sxs-lookup"><span data-stu-id="a7c41-111">As mentioned, the adapters are built on top of the WCF LOB Adapter SDK.</span></span> <span data-ttu-id="a7c41-112">WCF LOB Adapter SDK は、さまざまな BizTalk Server および Microsoft Office などのクライアント アプリケーションが使用できる統合アダプターを構築するための共通の基盤を提供します。</span><span class="sxs-lookup"><span data-stu-id="a7c41-112">The WCF LOB Adapter SDK provides a common basis for building integration adapters that a variety of client applications such as BizTalk Server and Microsoft Office can consume.</span></span> <span data-ttu-id="a7c41-113">WCF LOB Adapter SDK は、Windows Communication Foundation (WCF) チャネルとしての統合アダプターを公開することで、Microsoft のサービスを使用したアダプターの戦略を配置します。</span><span class="sxs-lookup"><span data-stu-id="a7c41-113">The WCF LOB Adapter SDK aligns the adapter strategy with the Microsoft Services strategy by exposing integration adapters as Windows Communication Foundation (WCF) channels.</span></span> <span data-ttu-id="a7c41-114">WCF LOB Adapter SDK の詳細については、次を参照してください。 [WCF LOB Adapter SDK ドキュメント](../../adapters-and-accelerators/wcf-lob-adapter-sdk/microsoft-wcf-line-of-business-adapter-sdk-documentation.md)します。</span><span class="sxs-lookup"><span data-stu-id="a7c41-114">For more information about the WCF LOB Adapter SDK, see [WCF LOB Adapter SDK documentation](../../adapters-and-accelerators/wcf-lob-adapter-sdk/microsoft-wcf-line-of-business-adapter-sdk-documentation.md).</span></span>
  
  <span data-ttu-id="a7c41-115">Oracle データベースで操作を実行するには、アダプター クライアントは、関連するテーブル、関数、およびプロシージャにアクセスする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a7c41-115">To perform operations on an Oracle database, adapter clients must have access to relevant tables, functions, and procedures.</span></span> <span data-ttu-id="a7c41-116">データベース テーブルとは、Oracle データベース内のストレージの基本単位です。</span><span class="sxs-lookup"><span data-stu-id="a7c41-116">Database tables are the basic unit of storage in the Oracle database.</span></span> <span data-ttu-id="a7c41-117">外部のアプリケーションでは、追加したり、SQL ステートメントを使用してテーブルからデータを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="a7c41-117">External applications can add or remove data from a table by using SQL statements.</span></span> <span data-ttu-id="a7c41-118">アプリケーションは、ビュー、関数、およびプロシージャを使用して、テーブル内のデータをアクセスもできます。</span><span class="sxs-lookup"><span data-stu-id="a7c41-118">Applications can also access data in the tables by using views, functions, and procedures.</span></span> <span data-ttu-id="a7c41-119">[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]、アダプター クライアントは、テーブル、プロシージャ、パッケージ、ビュー、および Oracle データベースでこのようなその他の項目などの成果物を参照できます。</span><span class="sxs-lookup"><span data-stu-id="a7c41-119">With [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)], adapter clients can browse the artifacts such as tables, procedures, packages, views, and other such items in an Oracle database.</span></span> <span data-ttu-id="a7c41-120">アダプター クライアントは、成果物がソリューションの必要があり、それらの成果物のメタデータの取得を選択できます。</span><span class="sxs-lookup"><span data-stu-id="a7c41-120">Adapter clients can select the artifacts they require for their solution and retrieve metadata for those artifacts.</span></span> <span data-ttu-id="a7c41-121">これにより、ユーザーにアクセスし、Oracle データベースで、成果物の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="a7c41-121">This enables users to access and execute the operations on the artifacts in the Oracle database.</span></span>  
  
  <span data-ttu-id="a7c41-122">このセクションの機能の一覧、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="a7c41-122">This section lists the features of the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a7c41-123">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="a7c41-123">In This Section</span></span>  
  
-   [<span data-ttu-id="a7c41-124">BizTalk Adapter for Oracle Database の概要</span><span class="sxs-lookup"><span data-stu-id="a7c41-124">Overview of BizTalk Adapter for Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/overview-of-biztalk-adapter-for-oracle-database.md)  
  
-   [<span data-ttu-id="a7c41-125">BizTalk Adapter for Oracle Database の主要な機能</span><span class="sxs-lookup"><span data-stu-id="a7c41-125">Key Features in BizTalk Adapter for Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/key-features-in-biztalk-adapter-for-oracle-database.md)  
  
-   [<span data-ttu-id="a7c41-126">Oracle Database の BizTalk アダプターの制限事項</span><span class="sxs-lookup"><span data-stu-id="a7c41-126">Limitations of BizTalk Adapter for Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/limitations-of-biztalk-adapter-for-oracle-database.md)  
  
## <a name="see-also"></a><span data-ttu-id="a7c41-127">参照</span><span class="sxs-lookup"><span data-stu-id="a7c41-127">See Also</span></span>  
[<span data-ttu-id="a7c41-128">BizTalk Server の概要</span><span class="sxs-lookup"><span data-stu-id="a7c41-128">Getting started with BizTalk Server</span></span>](../../core/getting-started-with-biztalk-server.md)