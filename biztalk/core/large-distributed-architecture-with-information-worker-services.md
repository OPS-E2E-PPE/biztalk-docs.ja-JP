---
title: Large Distributed Architecture インフォメーション ワーカー サービスと共に |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- architecture, examples
- architecture, large distributions
ms.assetid: 92f2d55c-3f51-42ca-99ef-60b23464691e
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c6b9b1729411e089566988714b83778abac80eb0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262194"
---
# <a name="large-distributed-architecture-with-information-worker-services"></a><span data-ttu-id="aae97-102">インフォメーション ワーカー サービスを使用した大規模な分散アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="aae97-102">Large Distributed Architecture with Information Worker Services</span></span>
<span data-ttu-id="aae97-103">BizTalk Server の展開のシステム アーキテクチャの設計の詳細については、次を参照してください。[サンプル BizTalk Server アーキテクチャ](../core/sample-biztalk-server-architectures.md)です。</span><span class="sxs-lookup"><span data-stu-id="aae97-103">For complete information about designing the system architecture for BizTalk Server deployment, see [Sample BizTalk Server Architectures](../core/sample-biztalk-server-architectures.md).</span></span>  
  
 <span data-ttu-id="aae97-104">ビジネス アクティビティの監視 (BAM) は、インフォメーション ワーカーがビジネス プロセスを表示し、パートナーと直接通信できるようにします。</span><span class="sxs-lookup"><span data-stu-id="aae97-104">Business Activity Monitoring (BAM) gives information workers visibility into the business processes and direct communication with partners.</span></span> <span data-ttu-id="aae97-105">ここでは、これらのサービスをセキュリティで保護するための各種の要件を示します。</span><span class="sxs-lookup"><span data-stu-id="aae97-105">This presents a different set of requirements for securing these services.</span></span> <span data-ttu-id="aae97-106">インフォメーション ワーカーは通常、データ ドメインではなく企業ドメイン内のアカウントを持っています。また、BizTalk Server によって生成されるデータの一部にアクセスするためのアクセス サービス インターフェイス ドメインを必要とします。</span><span class="sxs-lookup"><span data-stu-id="aae97-106">Information workers are likely to have accounts in the corporate domain and not in the data domain, and they need access service interfaces domain to access to some of the data BizTalk Server generates.</span></span>  
  
 <span data-ttu-id="aae97-107">次の図は、BAM を含む分散型 BizTalk Server アーキテクチャを示しています。</span><span class="sxs-lookup"><span data-stu-id="aae97-107">The following figure shows a distributed BizTalk Server architecture that includes BAM.</span></span>  
  
 <span data-ttu-id="aae97-108">![分散アーキテクチャ](../core/media/5aa6ab88-45ee-4b75-8e51-0ba0dd3fb4d2.gif "5aa6ab88-45ee-4b75-8e51-0ba0dd3fb4d2")</span><span class="sxs-lookup"><span data-stu-id="aae97-108">![Distributed Architecture](../core/media/5aa6ab88-45ee-4b75-8e51-0ba0dd3fb4d2.gif "5aa6ab88-45ee-4b75-8e51-0ba0dd3fb4d2")</span></span>  
<span data-ttu-id="aae97-109">インフォメーション ワーカー サービスを使用した分散型 BizTalk Server アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="aae97-109">Distributed BizTalk Server Architecture with Information Worker Services</span></span>  
  
 <span data-ttu-id="aae97-110">」に示すアーキテクチャと比較して[大規模な分散アーキテクチャ](../core/large-distributed-architecture.md)、インフォメーション ワーカー サービスの分散アーキテクチャには、BAM ポータルなどの追加のインフォメーション ワーカー サービスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="aae97-110">Compared to the architecture shown in [Large Distributed Architecture](../core/large-distributed-architecture.md), the distributed architecture for the information worker services contains an additional information worker services such as BAM Portal.</span></span> <span data-ttu-id="aae97-111">インフォメーション ワーカー サービスには次のサーバーとサービスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="aae97-111">The information worker services container includes the following servers and services:</span></span>  
  
-   <span data-ttu-id="aae97-112">BAM ポータル サーバー :</span><span class="sxs-lookup"><span data-stu-id="aae97-112">A BAM Portal server.</span></span> <span data-ttu-id="aae97-113">ビジネス エンド ユーザーは、BAM ポータルを使用して BAM データベースにアクセスし、ビジネス目標に対する進捗状況を測定する主要業績評価指標 (KPI) や、ビジネス プロセスに関するその他の情報を監視します。</span><span class="sxs-lookup"><span data-stu-id="aae97-113">Business end users use the BAM portal to access the BAM databases to monitor Key Performance Indicators (KPIs), which measure progress toward a business goal, as well as other information about their business process.</span></span> <span data-ttu-id="aae97-114">また、このサーバーには BAM クエリ Web サービスと BAM 管理 Web サービスも含まれています。</span><span class="sxs-lookup"><span data-stu-id="aae97-114">This server also has the BAM Query Web service and BAM Management Web service.</span></span>  
  
-   <span data-ttu-id="aae97-115">BAM 用の SQL Server: BAM プライマリ インポート データベース、BAM アーカイブ データベース、BAM スター スキーマ データベース、および BAM 分析データベース。</span><span class="sxs-lookup"><span data-stu-id="aae97-115">A SQL Server for BAM: the BAM Primary Import database, BAM Archive database, BAM Star Schema database, and BAM Analysis database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aae97-116">参照</span><span class="sxs-lookup"><span data-stu-id="aae97-116">See Also</span></span>  
 <span data-ttu-id="aae97-117">[大規模な分散アーキテクチャ](../core/large-distributed-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="aae97-117">[Large Distributed Architecture](../core/large-distributed-architecture.md) </span></span>  
 <span data-ttu-id="aae97-118">[縮小されたインフォメーション ワーカー サービスのアーキテクチャ](../core/scaled-down-architecture-with-information-worker-services.md) </span><span class="sxs-lookup"><span data-stu-id="aae97-118">[Scaled Down Architecture with Information Worker Services](../core/scaled-down-architecture-with-information-worker-services.md) </span></span>  
 <span data-ttu-id="aae97-119">[BAM のセキュリティに関する推奨事項](../core/bam-security-recommendations.md) </span><span class="sxs-lookup"><span data-stu-id="aae97-119">[BAM Security Recommendations](../core/bam-security-recommendations.md) </span></span>  
 [<span data-ttu-id="aae97-120">BizTalk Server のサンプル アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="aae97-120">Sample BizTalk Server Architectures</span></span>](../core/sample-biztalk-server-architectures.md)