---
title: BizTalk Adapter for SQL Server について |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 302a7f20-ffa2-49f1-a4c4-dd713adc23e1
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ea21a06ad5d87e94118aaa45e2f6f541627aae9b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996935"
---
# <a name="understand-biztalk-adapter-for-sql-server"></a><span data-ttu-id="c8723-102">BizTalk Adapter for SQL Server についてください。</span><span class="sxs-lookup"><span data-stu-id="c8723-102">Understand BizTalk Adapter for SQL Server</span></span>
<span data-ttu-id="c8723-103">[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]外部システムと対話することを行うサービス指向のプログラムでアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="c8723-103">The [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] enables service-oriented programmatic access making it possible to interact with an external system.</span></span> <span data-ttu-id="c8723-104">アダプターは、次の利点をクライアントに提供します。</span><span class="sxs-lookup"><span data-stu-id="c8723-104">The adapters provide the following advantages to clients:</span></span>  
  
- <span data-ttu-id="c8723-105">**デザイン時エクスペリエンスの一貫性のある**します。</span><span class="sxs-lookup"><span data-stu-id="c8723-105">**Consistent design-time experience**.</span></span> <span data-ttu-id="c8723-106">アダプターでは、参照、検索、および LOB アーティファクトのメタデータを取得するため、一般的な使いやすいもののデザイン時エクスペリエンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="c8723-106">The adapters provide a common and user-friendly design-time experience for browsing, searching, and retrieving metadata of LOB artifacts.</span></span>  
  
- <span data-ttu-id="c8723-107">**プログラミングのオプションをさまざまな**します。</span><span class="sxs-lookup"><span data-stu-id="c8723-107">**Varied programming options**.</span></span> <span data-ttu-id="c8723-108">アダプターは、WCF、Windows Communication Foundation (WCF) チャネル モデルなどのプログラミング モデルの選択したサービス モデルでは、ADO.NET、Web サービス、または BizTalk には、モデルがサポートされているを提供します。</span><span class="sxs-lookup"><span data-stu-id="c8723-108">The adapters provide a choice of programming model including the Windows Communication Foundation (WCF) channel model, WCF service model, ADO.NET, Web services, or BizTalk supported models.</span></span>  
  
- <span data-ttu-id="c8723-109">**Lob の間でのエクスペリエンス、統一された**します。</span><span class="sxs-lookup"><span data-stu-id="c8723-109">**Uniform experience across LOBs**.</span></span> <span data-ttu-id="c8723-110">WCF を使用して、アダプターを標準化、 [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]、し、そのため、LOB システムへのアクセスのエクスペリエンスの一貫性を提供します。</span><span class="sxs-lookup"><span data-stu-id="c8723-110">The adapters standardize on using WCF and the [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)], and hence provide a uniform experience of gaining access to any LOB system.</span></span>  
  
  <span data-ttu-id="c8723-111">前述のように、アダプターは WCF LOB Adapter SDK の上に構築されます。</span><span class="sxs-lookup"><span data-stu-id="c8723-111">As mentioned, the adapters are built on top of the WCF LOB Adapter SDK.</span></span> <span data-ttu-id="c8723-112">WCF LOB Adapter SDK は、さまざまな BizTalk Server および Microsoft Office などのクライアント アプリケーションが使用できる統合アダプターを構築するための共通の基盤を提供します。</span><span class="sxs-lookup"><span data-stu-id="c8723-112">The WCF LOB Adapter SDK provides a common basis for building integration adapters that a variety of client applications such as BizTalk Server and Microsoft Office can consume.</span></span> <span data-ttu-id="c8723-113">WCF LOB Adapter SDK は、Windows Communication Foundation (WCF) チャネルとしての統合アダプターを公開することで、Microsoft のサービスを使用したアダプターの戦略を配置します。</span><span class="sxs-lookup"><span data-stu-id="c8723-113">The WCF LOB Adapter SDK aligns the adapter strategy with the Microsoft Services strategy by exposing integration adapters as Windows Communication Foundation (WCF) channels.</span></span> <span data-ttu-id="c8723-114">WCF LOB Adapter SDK の詳細については、[WCF LOB Adapter SDK ドキュメント](../../adapters-and-accelerators/wcf-lob-adapter-sdk/microsoft-wcf-line-of-business-adapter-sdk-documentation.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8723-114">For more information about the WCF LOB Adapter SDK, see [WCF LOB Adapter SDK documentation](../../adapters-and-accelerators/wcf-lob-adapter-sdk/microsoft-wcf-line-of-business-adapter-sdk-documentation.md).</span></span>
  
  <span data-ttu-id="c8723-115">SQL Server データベースで操作を実行するには、アダプター クライアントに関連するテーブル、プロシージャ、ビュー、スカラー関数は、アクセスし、テーブル値関数する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c8723-115">To perform operations on a SQL Server database, adapter clients must have access to relevant tables, procedures, views, scalar functions, and table valued functions.</span></span> <span data-ttu-id="c8723-116">データベース テーブルとは、SQL Server データベース内のストレージの基本単位です。</span><span class="sxs-lookup"><span data-stu-id="c8723-116">Database tables are the basic unit of storage in the SQL Server database.</span></span> <span data-ttu-id="c8723-117">外部アプリケーションは、選択、挿入、削除、および SQL ステートメントを使用して、テーブルからデータを更新できます。</span><span class="sxs-lookup"><span data-stu-id="c8723-117">External applications can select, insert, delete, and update data from a table by using SQL statements.</span></span> <span data-ttu-id="c8723-118">アプリケーションは、プロシージャ、ビュー、スカラー関数、およびテーブル値関数を使用して、テーブル内のデータをアクセスもできます。</span><span class="sxs-lookup"><span data-stu-id="c8723-118">Applications can also access data in the tables by using procedures, views, scalar functions, and table valued functions.</span></span> <span data-ttu-id="c8723-119">[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]、アダプター クライアントは、テーブル、プロシージャ、ビュー、および SQL Server データベースのような他のアイテムなどの成果物を参照できます。</span><span class="sxs-lookup"><span data-stu-id="c8723-119">With [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)], adapter clients can browse artifacts such as tables, procedures, views, and other such items in a SQL Server database.</span></span> <span data-ttu-id="c8723-120">アダプター クライアントでは、そのソリューションでは、必要な成果物を選択でき、それらの成果物のメタデータを取得することができます。</span><span class="sxs-lookup"><span data-stu-id="c8723-120">Adapter clients can select the artifacts they require for their solution, and retrieve metadata for those artifacts.</span></span> <span data-ttu-id="c8723-121">これにより、ユーザーにアクセスし、SQL Server データベースで、成果物の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="c8723-121">This enables users to access and execute the operations on the artifacts in the SQL Server database.</span></span>  
  
  <span data-ttu-id="c8723-122">このセクションの機能の一覧、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="c8723-122">This section lists the features of the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c8723-123">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="c8723-123">In This Section</span></span>  
  
-   [<span data-ttu-id="c8723-124">BizTalk Adapter for SQL Server の概要</span><span class="sxs-lookup"><span data-stu-id="c8723-124">Overview of BizTalk Adapter for SQL Server</span></span>](../../adapters-and-accelerators/adapter-sql/overview-of-biztalk-adapter-for-sql-server.md)  
  
-   [<span data-ttu-id="c8723-125">BizTalk Adapter for SQL Server の主要な機能</span><span class="sxs-lookup"><span data-stu-id="c8723-125">Key features in BizTalk Adapter for SQL Server</span></span>](../../adapters-and-accelerators/adapter-sql/key-features-in-biztalk-adapter-for-sql-server.md) 
  
-   [<span data-ttu-id="c8723-126">SQL Server 用 BizTalk アダプターの制限事項</span><span class="sxs-lookup"><span data-stu-id="c8723-126">Limitations of BizTalk Adapter for SQL Server</span></span>](../../adapters-and-accelerators/adapter-sql/limitations-of-biztalk-adapter-for-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="c8723-127">参照</span><span class="sxs-lookup"><span data-stu-id="c8723-127">See Also</span></span>  
[<span data-ttu-id="c8723-128">SQL 用 BizTalk アダプターを概要します。</span><span class="sxs-lookup"><span data-stu-id="c8723-128">Get started with the BizTalk adapter for SQL</span></span>](../../adapters-and-accelerators/adapter-sql/get-started-with-the-biztalk-adapter-for-sql.md)