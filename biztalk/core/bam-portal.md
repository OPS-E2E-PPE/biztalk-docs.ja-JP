---
title: BAM ポータル |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BAM portal, alerts
- activities [BAM], searching
- BAM portal
- BAM portal, features
- aggregations [BAM], BAM portal
- BAM portal, activity searches
- alerts, Alert Manager
- BAM portal, about BAM portal
- BAM, portals
- BAM portal, aggregations
ms.assetid: 593c9637-6b97-4ad8-8af7-2b49325acf10
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 322eb5e2fa2ba59f3f839768fd21e2fb3683970a
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65528695"
---
# <a name="bam-portal"></a><span data-ttu-id="02440-102">BAM ポータル</span><span class="sxs-lookup"><span data-stu-id="02440-102">BAM Portal</span></span>
<span data-ttu-id="02440-103">ビジネス エンドユーザーは、BAM ポータルを使用して、主要業績評価指標 (Kpi)、ビジネス プロセスに関するその他の情報と、ビジネス目標に向けた進行状況を測定します。</span><span class="sxs-lookup"><span data-stu-id="02440-103">Business end users use the BAM portal to monitor Key Performance Indicators (KPIs), which measure progress toward a business goal, as well as other information about their business process.</span></span> <span data-ttu-id="02440-104">ビジネス アナリストは、BAM ポータルを使用して、ビジネス プロセス内での表示要件の高度な定義である監視モデルの作成を監視します。</span><span class="sxs-lookup"><span data-stu-id="02440-104">Business analysts use the BAM portal to oversee the creation of observation models, which are high-level definitions of the visibility requirements within the business process.</span></span> <span data-ttu-id="02440-105">管理者は、さまざまなビジネス プロセス管理システムの正常性の監視などのアクティビティの監視の使用します。</span><span class="sxs-lookup"><span data-stu-id="02440-105">Administrators use it for a variety of monitoring activities, including monitoring the health of the business process management system.</span></span>  
  
## <a name="what-is-the-bam-portal"></a><span data-ttu-id="02440-106">BAM ポータルとは何ですか。</span><span class="sxs-lookup"><span data-stu-id="02440-106">What is the BAM portal?</span></span>  
 <span data-ttu-id="02440-107">BAM ポータルでは、ビジネス プロセスをリアルタイムでエンド ツー エンドの可視性を提供します。</span><span class="sxs-lookup"><span data-stu-id="02440-107">The BAM portal provides real-time, end-to-end visibility into a business process.</span></span> <span data-ttu-id="02440-108">これは、ASP.NET ページのコレクションで構成される Web ベースの機能です。</span><span class="sxs-lookup"><span data-stu-id="02440-108">It is a Web-based feature that consists of a collection of ASP.NET pages.</span></span> <span data-ttu-id="02440-109">BAM をカスタマイズすることにより、パフォーマンスとユーザー エクスペリエンスが向上します。</span><span class="sxs-lookup"><span data-stu-id="02440-109">You can customize BAM to enhance the performance and experience for your users.</span></span>  
  
## <a name="why-use-the-bam-portal"></a><span data-ttu-id="02440-110">BAM ポータルを使用する理由</span><span class="sxs-lookup"><span data-stu-id="02440-110">Why use the BAM portal?</span></span>  
 <span data-ttu-id="02440-111">BAM ポータルを使用すると、検索、集計データを実行して、ビジネス データのパースペクティブは、BAM ビューにアラートを設定できます。</span><span class="sxs-lookup"><span data-stu-id="02440-111">The BAM portal allows you to perform searches, aggregate data, and set alerts on a BAM view, which is a perspective on your business data.</span></span> <span data-ttu-id="02440-112">この可視性は、ビジネスに必要な KPI 情報を提供できます。 または、Microsoft Office Excel スプレッドシートの拡張、SQL レポートを使用して、カスタム ユーザー インターフェイス (の構築などの別のソリューションを実装する前には、概念実証として使用することができます。UI の場合)。</span><span class="sxs-lookup"><span data-stu-id="02440-112">This visibility can provide the necessary KPI information for your business, or it can be used as proof of concept before you implement another solution such as extending a Microsoft Office Excel spreadsheet, using SQL Reporting, or building a custom user interface (UI).</span></span>  
  
## <a name="bam-portal-components"></a><span data-ttu-id="02440-113">BAM ポータル コンポーネント</span><span class="sxs-lookup"><span data-stu-id="02440-113">BAM portal components</span></span>  
 <span data-ttu-id="02440-114">BAM ポータル コンポーネントの簡単な説明を次に示します。</span><span class="sxs-lookup"><span data-stu-id="02440-114">Following is a brief description of the BAM portal components.</span></span> <span data-ttu-id="02440-115">詳細については、「参照」トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="02440-115">For a more detailed description, see the topics in See Also.</span></span>  
  
### <a name="activity-searches"></a><span data-ttu-id="02440-116">アクティビティの検索</span><span class="sxs-lookup"><span data-stu-id="02440-116">Activity searches</span></span>  
 <span data-ttu-id="02440-117">BAM ポータルを使用して、特定の BAM アクティビティを検出する BAM データに対して検索を実行します。</span><span class="sxs-lookup"><span data-stu-id="02440-117">You use the BAM portal to perform searches against BAM data to find a specific BAM activity.</span></span> <span data-ttu-id="02440-118">クエリを作成するを追加して、警告を表示する条件に一致するアクティビティを表示できるようにする検索句を削除します。</span><span class="sxs-lookup"><span data-stu-id="02440-118">You create queries by adding and removing search clauses that allow you to display those activities that match criteria for which you want to be alerted.</span></span>  
  
 <span data-ttu-id="02440-119">クエリの保存および再利用できます。</span><span class="sxs-lookup"><span data-stu-id="02440-119">Queries can be saved and reused.</span></span> <span data-ttu-id="02440-120">アラートは、特定の顧客から注文書が到着したときの通知など、基礎こともできます。</span><span class="sxs-lookup"><span data-stu-id="02440-120">They can also be the basis for an alert, such as a notification when a purchase order arrives from a specific customer.</span></span>  
  
### <a name="aggregations"></a><span data-ttu-id="02440-121">集計</span><span class="sxs-lookup"><span data-stu-id="02440-121">Aggregations</span></span>  
 <span data-ttu-id="02440-122">ポータルを使用すると、データのスナップショットをキャプチャし、グラフィカルなグラフや付属のピボット テーブル グラフの形式で表示できます。</span><span class="sxs-lookup"><span data-stu-id="02440-122">The portal allows you to capture a snapshot of data and display it in the form of a graphical chart and accompanying PivotTable chart.</span></span> <span data-ttu-id="02440-123">このデータでは、そのプロセスまたはビジネス全体の正常性を表示します。</span><span class="sxs-lookup"><span data-stu-id="02440-123">This data gives you visibility into the health of that process or the overall business.</span></span> <span data-ttu-id="02440-124">たとえば、ユーザーは、各請求書 (「評価、」400 が拒否されると、「資金割当中」で、有料と 100 の 100 件でも 400) による処理の段階に達している観点からは 1 日に受け取った 1,000 の請求書の内訳を表示する単純な円グラフを表示する可能性があります.</span><span class="sxs-lookup"><span data-stu-id="02440-124">For example, a user may wish to see a simple pie chart that shows a breakdown of the 1,000 invoices received in a day in terms of what stage of processing has been reached by each invoice (400 still in "evaluation," 400 rejected, 100 paid, and 100 still in "fund allocation").</span></span>  
  
 <span data-ttu-id="02440-125">表示されるデータは、「通知を受け取るプロセスの評価段階に 500 件を超えた請求書がある場合」など、アラートを作成するための基礎</span><span class="sxs-lookup"><span data-stu-id="02440-125">The data presented can be the basis for creating an alert, such as "Notify me if there are ever more than 500 invoices in the 'evaluation' stage of the process."</span></span>  
  
### <a name="alert-manager"></a><span data-ttu-id="02440-126">警告マネージャー</span><span class="sxs-lookup"><span data-stu-id="02440-126">Alert Manager</span></span>  
 <span data-ttu-id="02440-127">ポータルでは、アラートの作成と既存のアラートの編集のユーザー インターフェイスを提供します。</span><span class="sxs-lookup"><span data-stu-id="02440-127">The portal provides a user interface for the creation of alerts and the editing of existing alerts.</span></span> <span data-ttu-id="02440-128">アラートは、アクティビティの検索または集計のいずれかのページから監視する条件を取得します。</span><span class="sxs-lookup"><span data-stu-id="02440-128">Alerts take the conditions that are to be monitored from either the Activity Search or Aggregations page.</span></span> <span data-ttu-id="02440-129">警告マネージャーでは、通知するなど、アラートに関連する部分で入力方法 (電子メール) を使用して他のユーザーを参照してくださいかどうか、および警告をサブスクライブするとします。</span><span class="sxs-lookup"><span data-stu-id="02440-129">The Alert Manager is where you fill in the relevant parts of an alert, such as who to notify, how (for example, through e-mail), and whether others can see and subscribe to the alert.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="02440-130">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="02440-130">In This Section</span></span>  
  
-   [<span data-ttu-id="02440-131">BAM ポータルのコンポーネント</span><span class="sxs-lookup"><span data-stu-id="02440-131">Components of the BAM Portal</span></span>](../core/components-of-the-bam-portal.md)  
  
-   [<span data-ttu-id="02440-132">BAM ポータルの計画</span><span class="sxs-lookup"><span data-stu-id="02440-132">Planning for the BAM Portal</span></span>](../core/planning-for-the-bam-portal.md)  
  
-   [<span data-ttu-id="02440-133">BAM ポータルでのアクティビティの検索</span><span class="sxs-lookup"><span data-stu-id="02440-133">Activity Searches in the BAM Portal</span></span>](../core/activity-searches-in-the-bam-portal.md)  
  
-   [<span data-ttu-id="02440-134">BAM ポータルでの集計</span><span class="sxs-lookup"><span data-stu-id="02440-134">Aggregations in the BAM Portal</span></span>](../core/aggregations-in-the-bam-portal.md)  
  
-   [<span data-ttu-id="02440-135">BAM ポータルの警告</span><span class="sxs-lookup"><span data-stu-id="02440-135">Alerts in the BAM Portal</span></span>](../core/alerts-in-the-bam-portal.md)  
  
-   [<span data-ttu-id="02440-136">BAM ポータルのユーザー補助機能</span><span class="sxs-lookup"><span data-stu-id="02440-136">Accessibility for the BAM Portal</span></span>](../core/accessibility-for-the-bam-portal.md)  
  
-   [<span data-ttu-id="02440-137">BAM ポータルのセキュリティに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="02440-137">Security Considerations for the BAM Portal</span></span>](../core/security-considerations-for-the-bam-portal.md)  
  
-   [<span data-ttu-id="02440-138">BAM ポータルでの既知の問題</span><span class="sxs-lookup"><span data-stu-id="02440-138">Known Issues in the BAM Portal</span></span>](../core/known-issues-in-the-bam-portal.md)  
  
## <a name="see-also"></a><span data-ttu-id="02440-139">参照</span><span class="sxs-lookup"><span data-stu-id="02440-139">See Also</span></span>  
 <span data-ttu-id="02440-140">[BAM ポータルのアクティビティの検索ページ](../core/activity-search-on-the-bam-portal-page.md) </span><span class="sxs-lookup"><span data-stu-id="02440-140">[Activity Search on the BAM Portal Page](../core/activity-search-on-the-bam-portal-page.md) </span></span>  
 <span data-ttu-id="02440-141">[BAM ポータルでの集計 ページ](../core/aggregations-on-the-bam-portal-page.md) </span><span class="sxs-lookup"><span data-stu-id="02440-141">[Aggregations on the BAM Portal Page](../core/aggregations-on-the-bam-portal-page.md) </span></span>  
 [<span data-ttu-id="02440-142">BAM ポータル ページの警告マネージャー</span><span class="sxs-lookup"><span data-stu-id="02440-142">Alert Manager on the BAM Portal Page</span></span>](../core/alert-manager-on-the-bam-portal-page.md)