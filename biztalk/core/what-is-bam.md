---
title: "BAM とは何ですか。 | Microsoft Docs"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- aggregations [BAM], monitoring
- profiles, monitoring
- monitoring, alerts
- KPIs, BAM
- BAM, alerts
- profiles
- BAM, KPIs
- BAM
- alerts, monitoring
- BAM, aggregations
- BAM, about BAM
- monitoring, profiles
- KPIs, monitoring
- monitoring, KPIs
- alerts, BAM
- monitoring, BAM
- profiles, BAM
ms.assetid: 5160026a-1ffe-457e-8b75-35ed9bb3457c
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 81eb5a228bb5183c9f57c671424bad5e5be05088
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="what-is-bam"></a><span data-ttu-id="88121-103">BAM とは何ですか。</span><span class="sxs-lookup"><span data-stu-id="88121-103">What Is BAM?</span></span>
<span data-ttu-id="88121-104">ビジネス アクティビティの監視 (BAM) は、集計、警告、およびプロファイルを管理して、関連するビジネス指標 (主要業績評価指標または KPI) を監視できるツールのコレクションです。</span><span class="sxs-lookup"><span data-stu-id="88121-104">Business Activity Monitoring (BAM) is a collection of tools that allow you to manage aggregations, alerts, and profiles to monitor relevant business metrics (called Key Performance Indicators, or KPIs).</span></span> <span data-ttu-id="88121-105">BAM によって、ビジネス プロセスを詳細に表示できるようになり、さまざまな操作、処理、およびトランザクションの状態と結果に関する正確な情報が提供されます。そのため、ビジネスで問題がある領域を見つけて、その問題を解決できます。</span><span class="sxs-lookup"><span data-stu-id="88121-105">It gives you end-to-end visibility into your business processes, providing accurate information about the status and results of various operations, processes, and transactions so you can address problem areas and resolve issues within your business.</span></span>  
  
 <span data-ttu-id="88121-106">BAM フレームワークでは、異種ビジネス アプリケーションを監視するため、および SQL クエリや集計レポート用のデータを提示する (OLAP を利用) ための、リアルタイムで、トランザクションとしての一貫性がある容易な方法が提供されます。</span><span class="sxs-lookup"><span data-stu-id="88121-106">The BAM Framework provides an easy, real-time, transaction-consistent way to monitor heterogeneous business applications, and to present data for SQL queries and aggregated reports (OLAP).</span></span> <span data-ttu-id="88121-107">クエリや集計を使用すると、ビジネスの自動化方法とは無関係に、ビジネス プロセスの運用中に存在するデータだけでなく、運用中のビジネス プロセスの状態やダイナミクスを取得することができます。</span><span class="sxs-lookup"><span data-stu-id="88121-107">Through queries and aggregations you can include not only the data that is present during the running business process, but also the state and the dynamics of the running business process, independent of how the business is automated.</span></span>  
  
 <span data-ttu-id="88121-108">BAM では、稼働中のビジネス インテリジェンスおよびアプリケーション統合テクノロジを自動化されたプロセスに適用し、稼働中のイベントから直接返されるフィードバックに基づいて、これらのプロセスを継続的に調整します。</span><span class="sxs-lookup"><span data-stu-id="88121-108">BAM applies operational business intelligence and application integration technologies to automated processes to continually refine them based on feedback that comes directly from knowledge of operational events.</span></span> <span data-ttu-id="88121-109">また、ビジネス プロセス (およびビジネス プロセス管理システム) を監査することに加えて、イベント ドリブンの警告を送信できます。イベント ドリブンの警告は、ビジネスに対してアクションを伴うような変更が加えられた場合に、意思決定者に警告するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="88121-109">In addition to auditing business processes (and business process management systems), BAM can send event-driven alerts that can be used to alert decision makers to changes in the business that may require action.</span></span>  
  
## <a name="why-use-bam"></a><span data-ttu-id="88121-110">BAM を使用する理由</span><span class="sxs-lookup"><span data-stu-id="88121-110">Why use BAM?</span></span>  
 <span data-ttu-id="88121-111">現在の一般的な企業では、顧客間関係管理 (CRM)、SAP、および発注管理など、社内で購入したか長い年月をかけて開発した、さまざまなビジネス アプリケーションを使用しています。</span><span class="sxs-lookup"><span data-stu-id="88121-111">The typical enterprise today uses a variety of business applications, such as customer relationship management (CRM), SAP, and order management, purchased or developed internally over time.</span></span> <span data-ttu-id="88121-112">これらのアプリケーションの多くは、COM や COM+ を使用する COBOL プログラムから、C# や Java に至るまで、さまざまなテクノロジによって開発されており、異種のオペレーティング システムで実行されます。</span><span class="sxs-lookup"><span data-stu-id="88121-112">These applications frequently use disparate technologies and run as heterogeneous operating systems, ranging from COBOL programs using COM and COM+, to C# and Java.</span></span>  
  
 <span data-ttu-id="88121-113">また、一般的な企業のさまざまな活動は、電話、FAX、電子メールなど、人間の行為に基づいています。</span><span class="sxs-lookup"><span data-stu-id="88121-113">At the same time, many aspects of a typical enterprise are based on human actions, such as phone calls, faxes, and e-mail.</span></span> <span data-ttu-id="88121-114">このような複雑な環境では "ビジネスで起こっていること" を把握することがますます困難になっています。</span><span class="sxs-lookup"><span data-stu-id="88121-114">It becomes increasingly difficult to see “what is going on in the business” in such a complex environment.</span></span> <span data-ttu-id="88121-115">それにもかかわらず、市場の高速化に伴い、企業にとって、市場機会を利用したり損失を防ぐために迅速な意思決定を行うことがさらに重要になっています。</span><span class="sxs-lookup"><span data-stu-id="88121-115">Nevertheless, with the increasing speed of the market, it is more crucial for enterprises to make quick decisions to take advantage of market opportunities or to prevent losses.</span></span>  
  
 <span data-ttu-id="88121-116">サービスの品質を向上させつつ、分散された IT 環境のコストを削減する必要のある IT マネージャーは、BAM を監視ソリューションとして使用できます。</span><span class="sxs-lookup"><span data-stu-id="88121-116">BAM can be used as a monitoring solution by IT managers who want to cut the cost of their distributed IT environments while improving service quality.</span></span> <span data-ttu-id="88121-117">BAM では、企業全体にわたって、ビジネスで重要な位置を占めるサーバーやアプリケーションの管理を監視できます。また、エンジニアリング、設計、および製造といった部門ごとに、パフォーマンスに優れたワークステーションとアプリケーションを監視することもできます。</span><span class="sxs-lookup"><span data-stu-id="88121-117">BAM provides management oversight of the business-critical servers and applications across your company and offers a vertical view of high-performance workstations and applications within engineering, design, and production divisions.</span></span>  
  
 <span data-ttu-id="88121-118">BAM では、すべてのビジネス プロセスで必要とされる情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="88121-118">BAM exposes the visibility requirements of the end-to-end business process.</span></span> <span data-ttu-id="88121-119">ビジネス アナリストは、ビジネス内のさまざまなロールがビジネス プロセスとどのように連携するかを理解し、連携に必要なデータを把握したうえで、BAM ウィザードを使用して Microsoft Office Excel の BAM のデザイン時画面を操作します。これにより、アクティビティやビューの定義を作成することができ、さまざまなロールで必要とされる情報の表示を実現できます。</span><span class="sxs-lookup"><span data-stu-id="88121-119">Using an understanding of how the various roles within the business interact with the business process as well as an understanding of the data requirements for the interactions, the business analyst interacts with the BAM design-time surface in Microsoft Office Excel through the BAM wizards to create activity and view definitions to support these visibility needs of the various roles.</span></span>  
  
 <span data-ttu-id="88121-120">具体的には、企業が直面する次のような課題に対処しています。</span><span class="sxs-lookup"><span data-stu-id="88121-120">More specifically, BAM addresses challenges facing enterprises as follows:</span></span>  
  
-   <span data-ttu-id="88121-121">BAM ポータルによるビジネス エンド ユーザーへの権限付与</span><span class="sxs-lookup"><span data-stu-id="88121-121">Business end user empowerment through the BAM portal</span></span>  
  
-   <span data-ttu-id="88121-122">ビジネスの警告および通知</span><span class="sxs-lookup"><span data-stu-id="88121-122">Business alerts and notifications</span></span>  
  
-   <span data-ttu-id="88121-123">理解しやすい表示形式を作成し、利用するための操作性</span><span class="sxs-lookup"><span data-stu-id="88121-123">Better visibility creation and consumption experience</span></span>  
  
-   <span data-ttu-id="88121-124">ビジネス プロセスに関する詳細な情報の表示</span><span class="sxs-lookup"><span data-stu-id="88121-124">End-to-end visibility of the business process</span></span>  
  
-   <span data-ttu-id="88121-125">パイプラインのサポート (間接的にはアダプターおよび Web サービスのサポートも含む)</span><span class="sxs-lookup"><span data-stu-id="88121-125">Support for pipelines (and indirectly, adapters and Web services)</span></span>  
  
-   <span data-ttu-id="88121-126">アクティビティの迅速な変更</span><span class="sxs-lookup"><span data-stu-id="88121-126">Immediate Activity change-on-the-fly</span></span>  
  
-   <span data-ttu-id="88121-127">インターセプターおよび追跡プロファイルのガイドライン</span><span class="sxs-lookup"><span data-stu-id="88121-127">Interceptor and tracking profile guidelines</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88121-128">参照</span><span class="sxs-lookup"><span data-stu-id="88121-128">See Also</span></span>  
 <span data-ttu-id="88121-129">[BAM アクティビティのイベント ストリームの実装](../core/implementing-bam-activities-with-event-streams.md) </span><span class="sxs-lookup"><span data-stu-id="88121-129">[Implementing BAM Activities with Event Streams](../core/implementing-bam-activities-with-event-streams.md) </span></span>  
 <span data-ttu-id="88121-130">[BAM 動的インフラストラクチャ](../core/bam-dynamic-infrastructure.md) </span><span class="sxs-lookup"><span data-stu-id="88121-130">[BAM Dynamic Infrastructure](../core/bam-dynamic-infrastructure.md) </span></span>  
 <span data-ttu-id="88121-131">[追跡プロファイル エディター](../core/tracking-profile-editor.md) </span><span class="sxs-lookup"><span data-stu-id="88121-131">[Tracking Profile Editor](../core/tracking-profile-editor.md) </span></span>  
 <span data-ttu-id="88121-132">[BAM ポータル](../core/bam-portal.md) </span><span class="sxs-lookup"><span data-stu-id="88121-132">[BAM Portal](../core/bam-portal.md) </span></span>  
 [<span data-ttu-id="88121-133">ビジネス アクティビティの使用の監視</span><span class="sxs-lookup"><span data-stu-id="88121-133">Using Business Activity Monitoring</span></span>](../core/using-business-activity-monitoring.md)