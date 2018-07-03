---
title: BAM 動的インフラストラクチャの管理 |Microsoft Docs
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
ms.openlocfilehash: 861390d71c7cd16815ae7f3d446e956f0ae3bb74
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004707"
---
# <a name="managing-the-bam-dynamic-infrastructure"></a><span data-ttu-id="398cd-102">BAM 動的インフラストラクチャの管理</span><span class="sxs-lookup"><span data-stu-id="398cd-102">Managing the BAM Dynamic Infrastructure</span></span>
<span data-ttu-id="398cd-103">ビジネス アクティビティの監視 (BAM) 機能では、SQL とオンライン分析処理 (OLAP) のインフラストラクチャに動的に生成されるインフラストラクチャを使用します。</span><span class="sxs-lookup"><span data-stu-id="398cd-103">Business Activity Monitoring (BAM) features use a dynamically generated SQL and online analytical processing (OLAP) infrastructure.</span></span> <span data-ttu-id="398cd-104">管理者は、BAM 管理ユーティリティを使用して、ビジネス アナリストが作成する BAM 定義ブックまたは XML ファイルを展開します。</span><span class="sxs-lookup"><span data-stu-id="398cd-104">Administrators use the BAM Management utility to deploy the BAM definition workbook or XML file, which the business analyst develops.</span></span>  
  
 <span data-ttu-id="398cd-105">BAM 動的インフラストラクチャは、BAM ブック ビュー、BAM の展開、BAM データ変換サービス (DTS) パッケージ、および BAM データベースで構成されています。</span><span class="sxs-lookup"><span data-stu-id="398cd-105">The BAM dynamic infrastructure consists of the BAM workbook views, BAM deployments, the BAM Data Transformation Services (DTS) packages, and the BAM databases.</span></span> <span data-ttu-id="398cd-106">BAM 動的インフラストラクチャの詳細については、次を参照してください。 [BAM 動的インフラストラクチャ](../core/bam-dynamic-infrastructure.md)します。</span><span class="sxs-lookup"><span data-stu-id="398cd-106">For more information about the BAM dynamic infrastructure, see [BAM Dynamic Infrastructure](../core/bam-dynamic-infrastructure.md).</span></span>  
  
 <span data-ttu-id="398cd-107">BizTalk Server では、BizTalk Server を構成するときに、次の BAM データベースが作成されます。</span><span class="sxs-lookup"><span data-stu-id="398cd-107">BizTalk Server creates the following BAM databases when you configure BizTalk Server:</span></span>  
  
- <span data-ttu-id="398cd-108">BAM プライマリ インポート (BAMPrimaryImport) データベース</span><span class="sxs-lookup"><span data-stu-id="398cd-108">BAM Primary Import (BAMPrimaryImport) database</span></span>  
  
- <span data-ttu-id="398cd-109">BAM スター スキーマ (BAMStarSchema) データベース (オプション)</span><span class="sxs-lookup"><span data-stu-id="398cd-109">BAM Star Schema (BAMStarSchema) database (optional)</span></span>  
  
- <span data-ttu-id="398cd-110">BAM 分析 (BAMAnalysis) データベース (オプション)</span><span class="sxs-lookup"><span data-stu-id="398cd-110">BAM Analysis (BAMAnalysis) database (optional)</span></span>  
  
- <span data-ttu-id="398cd-111">BAM アーカイブ (BAMArchive) データベース</span><span class="sxs-lookup"><span data-stu-id="398cd-111">BAM Archive (BAMArchive) database</span></span>  
  
  <span data-ttu-id="398cd-112">BAM データベースについては、次を参照してください。 [BAM データベースを管理する](../core/managing-bam-databases.md)します。</span><span class="sxs-lookup"><span data-stu-id="398cd-112">For information about the BAM databases, see [Managing BAM Databases](../core/managing-bam-databases.md).</span></span>  
  
  <span data-ttu-id="398cd-113">管理者は、このセクションで説明している BAM インフラストラクチャの次の管理作業を行います。</span><span class="sxs-lookup"><span data-stu-id="398cd-113">Administrators perform the following management tasks for the BAM infrastructure, which are described in this section:</span></span>  
  
- <span data-ttu-id="398cd-114">BAM 定義と BAM ビューの展開および展開解除</span><span class="sxs-lookup"><span data-stu-id="398cd-114">Deploy and undeploy BAM definitions and views</span></span>  
  
- <span data-ttu-id="398cd-115">BAS ビューへのユーザー アクセスの管理</span><span class="sxs-lookup"><span data-stu-id="398cd-115">Manage user access to BAM views</span></span>  
  
- <span data-ttu-id="398cd-116">BAM DTS パッケージの実行</span><span class="sxs-lookup"><span data-stu-id="398cd-116">Run the BAM DTS packages</span></span>  
  
- <span data-ttu-id="398cd-117">BAM データベースのバックアップ</span><span class="sxs-lookup"><span data-stu-id="398cd-117">Back up the BAM databases</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="398cd-118">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="398cd-118">In This Section</span></span>  
  
-   [<span data-ttu-id="398cd-119">BAM 定義の管理</span><span class="sxs-lookup"><span data-stu-id="398cd-119">Managing BAM Definitions</span></span>](../core/managing-bam-definitions.md)
  
-   [<span data-ttu-id="398cd-120">BAM セキュリティの管理</span><span class="sxs-lookup"><span data-stu-id="398cd-120">Managing BAM Security</span></span>](../core/managing-bam-security.md)  
  
-   [<span data-ttu-id="398cd-121">集計の管理</span><span class="sxs-lookup"><span data-stu-id="398cd-121">Managing Aggregations</span></span>](../core/managing-aggregations.md) 
  
-   [<span data-ttu-id="398cd-122">BAM データベースの管理</span><span class="sxs-lookup"><span data-stu-id="398cd-122">Managing BAM Databases</span></span>](../core/managing-bam-databases.md)
  
## <a name="see-also"></a><span data-ttu-id="398cd-123">参照</span><span class="sxs-lookup"><span data-stu-id="398cd-123">See Also</span></span>  
 [<span data-ttu-id="398cd-124">BAM の管理</span><span class="sxs-lookup"><span data-stu-id="398cd-124">Managing BAM</span></span>](../core/managing-bam.md)