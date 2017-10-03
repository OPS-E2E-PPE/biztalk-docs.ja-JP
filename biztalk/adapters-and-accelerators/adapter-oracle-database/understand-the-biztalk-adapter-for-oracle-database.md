---
title: "Oracle データベースの BizTalk アダプターを理解する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aee5761ad466f755e2eb944dcfb2526729bea07c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="understand-the-biztalk-adapter-for-oracle-database"></a><span data-ttu-id="45710-102">Oracle データベースの BizTalk アダプターを理解します。</span><span class="sxs-lookup"><span data-stu-id="45710-102">Understand the BizTalk Adapter for Oracle Database</span></span>
<span data-ttu-id="45710-103">[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]外部システムと対話するためにサービス指向のプログラムによるアクセスを有効にします。</span><span class="sxs-lookup"><span data-stu-id="45710-103">The [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] enables service-oriented programmatic access in order to interact with an external system.</span></span> <span data-ttu-id="45710-104">アダプターでは、次の利点をクライアントに使用します。</span><span class="sxs-lookup"><span data-stu-id="45710-104">The adapters provide the following advantages to clients:</span></span>  
  
-   <span data-ttu-id="45710-105">**デザイン時のエクスペリエンスを一貫した**です。</span><span class="sxs-lookup"><span data-stu-id="45710-105">**Consistent design-time experience**.</span></span> <span data-ttu-id="45710-106">アダプターは、参照、検索、および LOB アーティファクトのメタデータを取得するために共通で使いやすいデザイン時機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="45710-106">The adapters provide a common and user-friendly design-time experience for browsing, searching, and retrieving metadata of LOB artifacts.</span></span>  
  
-   <span data-ttu-id="45710-107">**さまざまなプログラミング オプション**です。</span><span class="sxs-lookup"><span data-stu-id="45710-107">**Varied programming options**.</span></span> <span data-ttu-id="45710-108">など、Windows Communication Foundation (WCF) チャネル モデルを WCF プログラミング モデルの選択肢のサービス モデルでは、ADO.NET、Web サービス、または BizTalk には、モデルがサポートされているアダプターを提供します。</span><span class="sxs-lookup"><span data-stu-id="45710-108">The adapters provide a choice of programming model including the Windows Communication Foundation (WCF) channel model, WCF service model, ADO.NET, Web services, or BizTalk supported models.</span></span>  
  
-   <span data-ttu-id="45710-109">**Lob の間でのエクスペリエンス、統一された**です。</span><span class="sxs-lookup"><span data-stu-id="45710-109">**Uniform experience across LOBs**.</span></span> <span data-ttu-id="45710-110">アダプターは、WCF を使用して標準化および[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]、でき、したがって一貫した環境での任意の LOB システムへのアクセスを取得します。</span><span class="sxs-lookup"><span data-stu-id="45710-110">The adapters standardize on using WCF and [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)], and hence provide a uniform experience of gaining access to any LOB system.</span></span>  
  
 <span data-ttu-id="45710-111">前述のように、アダプターは、上に組み込ま、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="45710-111">As mentioned, the adapters are built on top of the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span> <span data-ttu-id="45710-112">[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]のさまざまな BizTalk Server および Microsoft Office などのクライアント アプリケーションで使用できる統合アダプターを構築するための共通の基本を提供します。</span><span class="sxs-lookup"><span data-stu-id="45710-112">The [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] provides a common basis for building integration adapters that a variety of client applications such as BizTalk Server and Microsoft Office can consume.</span></span> <span data-ttu-id="45710-113">[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]が Windows Communication Foundation (WCF) チャネルとの統合アダプターを公開することにより、アダプター戦略の Microsoft サービスの戦略を揃えて配置します。</span><span class="sxs-lookup"><span data-stu-id="45710-113">The [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] aligns the adapter strategy with the Microsoft Services strategy by exposing integration adapters as Windows Communication Foundation (WCF) channels.</span></span> <span data-ttu-id="45710-114">詳細については、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]を参照してください、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]ドキュメント。</span><span class="sxs-lookup"><span data-stu-id="45710-114">For more information about the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], see the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] documentation.</span></span> <span data-ttu-id="45710-115">[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]と共にドキュメントがインストールされている、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]通常 \<インストール ドライブ >: \Program Files\\[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]\Documents です。</span><span class="sxs-lookup"><span data-stu-id="45710-115">The [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] documentation is installed along with the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], typically under \<installation drive>:\Program Files\\[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]\Documents.</span></span>  
  
 <span data-ttu-id="45710-116">Oracle データベースでの操作を実行するには、アダプターのクライアントは、関連するテーブル、関数、およびプロシージャへのアクセスが必要です。</span><span class="sxs-lookup"><span data-stu-id="45710-116">To perform operations on an Oracle database, adapter clients must have access to relevant tables, functions, and procedures.</span></span> <span data-ttu-id="45710-117">データベース テーブルとは、Oracle データベースでの記憶域の基本単位です。</span><span class="sxs-lookup"><span data-stu-id="45710-117">Database tables are the basic unit of storage in the Oracle database.</span></span> <span data-ttu-id="45710-118">外部アプリケーションでは、追加したり、SQL ステートメントを使用してテーブルからデータを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="45710-118">External applications can add or remove data from a table by using SQL statements.</span></span> <span data-ttu-id="45710-119">アプリケーションは、ビュー、関数、およびプロシージャを使用して、テーブル内のデータもアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="45710-119">Applications can also access data in the tables by using views, functions, and procedures.</span></span> <span data-ttu-id="45710-120">[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]アダプターのクライアントは、テーブル、プロシージャ、パッケージ、ビュー、および Oracle データベースでこのようなその他の項目などの成果物を参照できます。</span><span class="sxs-lookup"><span data-stu-id="45710-120">With [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)], adapter clients can browse the artifacts such as tables, procedures, packages, views, and other such items in an Oracle database.</span></span> <span data-ttu-id="45710-121">アダプターのクライアントは、成果物がソリューションの必要があり、それらの成果物のメタデータを取得を選択できます。</span><span class="sxs-lookup"><span data-stu-id="45710-121">Adapter clients can select the artifacts they require for their solution and retrieve metadata for those artifacts.</span></span> <span data-ttu-id="45710-122">これにより、ユーザーにアクセスし、Oracle データベースでのアイテムでは、操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="45710-122">This enables users to access and execute the operations on the artifacts in the Oracle database.</span></span>  
  
 <span data-ttu-id="45710-123">このセクションの機能の一覧、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="45710-123">This section lists the features of the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="45710-124">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="45710-124">In This Section</span></span>  
  
-   [<span data-ttu-id="45710-125">BizTalk Adapter 用 Oracle Database の概要</span><span class="sxs-lookup"><span data-stu-id="45710-125">Overview of BizTalk Adapter for Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/overview-of-biztalk-adapter-for-oracle-database.md)  
  
-   [<span data-ttu-id="45710-126">BizTalk Adapter 用 Oracle Database の主要な機能</span><span class="sxs-lookup"><span data-stu-id="45710-126">Key Features in BizTalk Adapter for Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/key-features-in-biztalk-adapter-for-oracle-database.md)  
  
-   [<span data-ttu-id="45710-127">Oracle Database の BizTalk アダプターの制限事項</span><span class="sxs-lookup"><span data-stu-id="45710-127">Limitations of BizTalk Adapter for Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/limitations-of-biztalk-adapter-for-oracle-database.md)  
  
## <a name="see-also"></a><span data-ttu-id="45710-128">参照</span><span class="sxs-lookup"><span data-stu-id="45710-128">See Also</span></span>  
[<span data-ttu-id="45710-129">BizTalk Server の概要</span><span class="sxs-lookup"><span data-stu-id="45710-129">Getting started with BizTalk Server</span></span>](../../core/getting-started-with-biztalk-server.md)