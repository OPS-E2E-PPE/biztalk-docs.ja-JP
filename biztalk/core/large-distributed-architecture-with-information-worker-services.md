---
title: 大規模な分散、インフォメーション ワーカー サービス アーキテクチャ |Microsoft Docs
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
ms.openlocfilehash: 54bb036868202c153fef2405a6f26d977e823b40
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65328930"
---
# <a name="large-distributed-architecture-with-information-worker-services"></a><span data-ttu-id="0608f-102">インフォメーション ワーカー サービスを使用した大規模な分散アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="0608f-102">Large Distributed Architecture with Information Worker Services</span></span>
<span data-ttu-id="0608f-103">BizTalk Server の展開のシステム アーキテクチャを設計する方法の詳細については、次を参照してください。 [Sample BizTalk Server Architectures](../core/sample-biztalk-server-architectures.md)します。</span><span class="sxs-lookup"><span data-stu-id="0608f-103">For complete information about designing the system architecture for BizTalk Server deployment, see [Sample BizTalk Server Architectures](../core/sample-biztalk-server-architectures.md).</span></span>  
  
 <span data-ttu-id="0608f-104">ビジネス アクティビティ監視 (BAM) は、ビジネス プロセスやパートナーと直接通信の可視性をインフォメーション ワーカーに提供します。</span><span class="sxs-lookup"><span data-stu-id="0608f-104">Business Activity Monitoring (BAM) gives information workers visibility into the business processes and direct communication with partners.</span></span> <span data-ttu-id="0608f-105">これは、これらのサービスをセキュリティで保護するための要件の異なるセットを表示します。</span><span class="sxs-lookup"><span data-stu-id="0608f-105">This presents a different set of requirements for securing these services.</span></span> <span data-ttu-id="0608f-106">インフォメーション ワーカーが企業のドメイン内およびデータ ドメインではなく、アカウントを持っている可能性がありますし、BizTalk Server が生成するデータの一部にアクセスするアクセス サービス インターフェイス ドメインを必要な。</span><span class="sxs-lookup"><span data-stu-id="0608f-106">Information workers are likely to have accounts in the corporate domain and not in the data domain, and they need access service interfaces domain to access to some of the data BizTalk Server generates.</span></span>  
  
 <span data-ttu-id="0608f-107">次の図は、BAM を含む分散型 BizTalk Server アーキテクチャを示しています。</span><span class="sxs-lookup"><span data-stu-id="0608f-107">The following figure shows a distributed BizTalk Server architecture that includes BAM.</span></span>  
  
 <span data-ttu-id="0608f-108">![分散アーキテクチャ](../core/media/5aa6ab88-45ee-4b75-8e51-0ba0dd3fb4d2.gif "5aa6ab88-45ee-4b75-8e51-0ba0dd3fb4d2")</span><span class="sxs-lookup"><span data-stu-id="0608f-108">![Distributed Architecture](../core/media/5aa6ab88-45ee-4b75-8e51-0ba0dd3fb4d2.gif "5aa6ab88-45ee-4b75-8e51-0ba0dd3fb4d2")</span></span>  
<span data-ttu-id="0608f-109">インフォメーション ワーカー サービスを分散型 BizTalk Server アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="0608f-109">Distributed BizTalk Server Architecture with Information Worker Services</span></span>  
  
 <span data-ttu-id="0608f-110">」に示すアーキテクチャと比較して[大規模な分散アーキテクチャ](../core/large-distributed-architecture.md)、インフォメーション ワーカー サービスの分散アーキテクチャには、BAM ポータルなどの追加のインフォメーション ワーカー サービスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="0608f-110">Compared to the architecture shown in [Large Distributed Architecture](../core/large-distributed-architecture.md), the distributed architecture for the information worker services contains an additional information worker services such as BAM Portal.</span></span> <span data-ttu-id="0608f-111">インフォメーション ワーカー サービスのコンテナーには、次のサーバーとサービスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="0608f-111">The information worker services container includes the following servers and services:</span></span>  
  
-   <span data-ttu-id="0608f-112">BAM ポータル サーバー。</span><span class="sxs-lookup"><span data-stu-id="0608f-112">A BAM Portal server.</span></span> <span data-ttu-id="0608f-113">ビジネス エンドユーザーは、BAM ポータルを使用して、主要業績評価指標 (Kpi)、ビジネス プロセスに関するその他の情報と、ビジネス目標に向けた進行状況を測定するを監視する BAM データベースにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="0608f-113">Business end users use the BAM portal to access the BAM databases to monitor Key Performance Indicators (KPIs), which measure progress toward a business goal, as well as other information about their business process.</span></span> <span data-ttu-id="0608f-114">このサーバーは、BAM クエリ Web サービスと BAM 管理 Web サービスにもあります。</span><span class="sxs-lookup"><span data-stu-id="0608f-114">This server also has the BAM Query Web service and BAM Management Web service.</span></span>  
  
-   <span data-ttu-id="0608f-115">BAM 用の SQL Server: BAM プライマリ インポート データベース、BAM アーカイブ データベース、BAM スター スキーマ データベース、および BAM 分析データベース。</span><span class="sxs-lookup"><span data-stu-id="0608f-115">A SQL Server for BAM: the BAM Primary Import database, BAM Archive database, BAM Star Schema database, and BAM Analysis database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0608f-116">参照</span><span class="sxs-lookup"><span data-stu-id="0608f-116">See Also</span></span>  
 <span data-ttu-id="0608f-117">[大規模な分散アーキテクチャ](../core/large-distributed-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="0608f-117">[Large Distributed Architecture](../core/large-distributed-architecture.md) </span></span>  
 <span data-ttu-id="0608f-118">[縮小されたアーキテクチャ情報ワーカー サービスを使用](../core/scaled-down-architecture-with-information-worker-services.md) </span><span class="sxs-lookup"><span data-stu-id="0608f-118">[Scaled Down Architecture with Information Worker Services](../core/scaled-down-architecture-with-information-worker-services.md) </span></span>  
 <span data-ttu-id="0608f-119">[BAM のセキュリティに関する推奨事項](../core/bam-security-recommendations.md) </span><span class="sxs-lookup"><span data-stu-id="0608f-119">[BAM Security Recommendations](../core/bam-security-recommendations.md) </span></span>  
 [<span data-ttu-id="0608f-120">BizTalk Server のサンプル アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="0608f-120">Sample BizTalk Server Architectures</span></span>](../core/sample-biztalk-server-architectures.md)