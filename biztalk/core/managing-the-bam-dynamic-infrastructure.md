---
title: BAM 動的インフラストラクチャの管理 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- infrastructure, managing [BAM]
- managing [BAM], infrastructure
ms.assetid: af8a76b5-407a-484d-aff4-0d911f88313e
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 98cf9c3513a4fbd4a55a752233c9f0d704c59ecf
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
ms.locfileid: "26007515"
---
# <a name="managing-the-bam-dynamic-infrastructure"></a><span data-ttu-id="7b6ba-102">BAM 動的インフラストラクチャの管理</span><span class="sxs-lookup"><span data-stu-id="7b6ba-102">Managing the BAM Dynamic Infrastructure</span></span>
<span data-ttu-id="7b6ba-103">ビジネス アクティビティの監視 (BAM) 機能では、SQL とオンライン分析処理 (OLAP) のインフラストラクチャに動的に生成されるインフラストラクチャを使用します。</span><span class="sxs-lookup"><span data-stu-id="7b6ba-103">Business Activity Monitoring (BAM) features use a dynamically generated SQL and online analytical processing (OLAP) infrastructure.</span></span> <span data-ttu-id="7b6ba-104">管理者は、BAM 管理ユーティリティを使用して、ビジネス アナリストが作成する BAM 定義ブックまたは XML ファイルを展開します。</span><span class="sxs-lookup"><span data-stu-id="7b6ba-104">Administrators use the BAM Management utility to deploy the BAM definition workbook or XML file, which the business analyst develops.</span></span>  
  
 <span data-ttu-id="7b6ba-105">BAM 動的インフラストラクチャは、BAM ブック ビュー、BAM の展開、BAM データ変換サービス (DTS) パッケージ、および BAM データベースで構成されています。</span><span class="sxs-lookup"><span data-stu-id="7b6ba-105">The BAM dynamic infrastructure consists of the BAM workbook views, BAM deployments, the BAM Data Transformation Services (DTS) packages, and the BAM databases.</span></span> <span data-ttu-id="7b6ba-106">BAM 動的インフラストラクチャの詳細については、次を参照してください。 [BAM 動的インフラストラクチャ](../core/bam-dynamic-infrastructure.md)です。</span><span class="sxs-lookup"><span data-stu-id="7b6ba-106">For more information about the BAM dynamic infrastructure, see [BAM Dynamic Infrastructure](../core/bam-dynamic-infrastructure.md).</span></span>  
  
 <span data-ttu-id="7b6ba-107">BizTalk Server を構成するときに、BizTalk Server は、次の BAM データベースを作成します。</span><span class="sxs-lookup"><span data-stu-id="7b6ba-107">BizTalk Server creates the following BAM databases when you configure BizTalk Server:</span></span>  
  
-   <span data-ttu-id="7b6ba-108">BAM プライマリ インポート (BAMPrimaryImport) データベース</span><span class="sxs-lookup"><span data-stu-id="7b6ba-108">BAM Primary Import (BAMPrimaryImport) database</span></span>  
  
-   <span data-ttu-id="7b6ba-109">BAM スター スキーマ (BAMStarSchema) データベース (オプション)</span><span class="sxs-lookup"><span data-stu-id="7b6ba-109">BAM Star Schema (BAMStarSchema) database (optional)</span></span>  
  
-   <span data-ttu-id="7b6ba-110">BAM 分析 (BAMAnalysis) データベース (オプション)</span><span class="sxs-lookup"><span data-stu-id="7b6ba-110">BAM Analysis (BAMAnalysis) database (optional)</span></span>  
  
-   <span data-ttu-id="7b6ba-111">BAM アーカイブ (BAMArchive) データベース</span><span class="sxs-lookup"><span data-stu-id="7b6ba-111">BAM Archive (BAMArchive) database</span></span>  
  
 <span data-ttu-id="7b6ba-112">BAM データベースについては、次を参照してください。 [BAM データベースを管理する](../core/managing-bam-databases.md)です。</span><span class="sxs-lookup"><span data-stu-id="7b6ba-112">For information about the BAM databases, see [Managing BAM Databases](../core/managing-bam-databases.md).</span></span>  
  
 <span data-ttu-id="7b6ba-113">管理者は、このセクションで説明している BAM インフラストラクチャの次の管理作業を行います。</span><span class="sxs-lookup"><span data-stu-id="7b6ba-113">Administrators perform the following management tasks for the BAM infrastructure, which are described in this section:</span></span>  
  
-   <span data-ttu-id="7b6ba-114">BAM 定義と BAM ビューの展開および展開解除</span><span class="sxs-lookup"><span data-stu-id="7b6ba-114">Deploy and undeploy BAM definitions and views</span></span>  
  
-   <span data-ttu-id="7b6ba-115">BAS ビューへのユーザー アクセスの管理</span><span class="sxs-lookup"><span data-stu-id="7b6ba-115">Manage user access to BAM views</span></span>  
  
-   <span data-ttu-id="7b6ba-116">BAM DTS パッケージの実行</span><span class="sxs-lookup"><span data-stu-id="7b6ba-116">Run the BAM DTS packages</span></span>  
  
-   <span data-ttu-id="7b6ba-117">BAM データベースのバックアップ</span><span class="sxs-lookup"><span data-stu-id="7b6ba-117">Back up the BAM databases</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7b6ba-118">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="7b6ba-118">In This Section</span></span>  
  
-   [<span data-ttu-id="7b6ba-119">BAM 定義の管理</span><span class="sxs-lookup"><span data-stu-id="7b6ba-119">Managing BAM Definitions</span></span>](../core/managing-bam-definitions.md)
  
-   [<span data-ttu-id="7b6ba-120">BAM セキュリティの管理</span><span class="sxs-lookup"><span data-stu-id="7b6ba-120">Managing BAM Security</span></span>](../core/managing-bam-security.md)  
  
-   [<span data-ttu-id="7b6ba-121">集計の管理</span><span class="sxs-lookup"><span data-stu-id="7b6ba-121">Managing Aggregations</span></span>](../core/managing-aggregations.md) 
  
-   [<span data-ttu-id="7b6ba-122">BAM データベースの管理</span><span class="sxs-lookup"><span data-stu-id="7b6ba-122">Managing BAM Databases</span></span>](../core/managing-bam-databases.md)
  
## <a name="see-also"></a><span data-ttu-id="7b6ba-123">参照</span><span class="sxs-lookup"><span data-stu-id="7b6ba-123">See Also</span></span>  
 [<span data-ttu-id="7b6ba-124">BAM の管理</span><span class="sxs-lookup"><span data-stu-id="7b6ba-124">Managing BAM</span></span>](../core/managing-bam.md)