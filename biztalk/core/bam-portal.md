---
title: BAM ポータル |Microsoft ドキュメント
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
ms.openlocfilehash: 6f86aad2a183653f00f1f7fc2533ac6956b2a85f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22232082"
---
# <a name="bam-portal"></a><span data-ttu-id="3ab23-102">BAM ポータル</span><span class="sxs-lookup"><span data-stu-id="3ab23-102">BAM Portal</span></span>
<span data-ttu-id="3ab23-103">ビジネス エンド ユーザーは、BAM ポータルを使用すると、ビジネス目標に対する進捗状況を測定する主要業績評価指標 (KPI) や、ビジネス プロセスに関するその他の情報を監視できます。</span><span class="sxs-lookup"><span data-stu-id="3ab23-103">Business end users use the BAM portal to monitor Key Performance Indicators (KPIs), which measure progress toward a business goal, as well as other information about their business process.</span></span> <span data-ttu-id="3ab23-104">また、ビジネス アナリストは、BAM ポータルを使用して監視モデルの作成を監視します。監視モデルとは、ビジネス プロセス内の表示要件の概要定義といえます。</span><span class="sxs-lookup"><span data-stu-id="3ab23-104">Business analysts use the BAM portal to oversee the creation of observation models, which are high-level definitions of the visibility requirements within the business process.</span></span> <span data-ttu-id="3ab23-105">管理者は、ビジネス プロセス管理システムの状態の監視など、さまざまな監視作業で BAM ポータルを使用します。</span><span class="sxs-lookup"><span data-stu-id="3ab23-105">Administrators use it for a variety of monitoring activities, including monitoring the health of the business process management system.</span></span>  
  
## <a name="what-is-the-bam-portal"></a><span data-ttu-id="3ab23-106">BAM ポータルとは何ですか。</span><span class="sxs-lookup"><span data-stu-id="3ab23-106">What is the BAM portal?</span></span>  
 <span data-ttu-id="3ab23-107">BAM ポータルでは、ビジネス プロセスをリアルタイムで詳しく表示できます。</span><span class="sxs-lookup"><span data-stu-id="3ab23-107">The BAM portal provides real-time, end-to-end visibility into a business process.</span></span> <span data-ttu-id="3ab23-108">これは一連の ASP.NET ページで構成される Web ベースの機能です。</span><span class="sxs-lookup"><span data-stu-id="3ab23-108">It is a Web-based feature that consists of a collection of ASP.NET pages.</span></span> <span data-ttu-id="3ab23-109">BAM をカスタマイズすることにより、パフォーマンスとユーザー エクスペリエンスが向上します。</span><span class="sxs-lookup"><span data-stu-id="3ab23-109">You can customize BAM to enhance the performance and experience for your users.</span></span>  
  
## <a name="why-use-the-bam-portal"></a><span data-ttu-id="3ab23-110">BAM ポータルを使用する理由</span><span class="sxs-lookup"><span data-stu-id="3ab23-110">Why use the BAM portal?</span></span>  
 <span data-ttu-id="3ab23-111">BAM ポータルでは、BAM ビューに対して検索を実行したり、データを集計したり、警告を設定することができます。BAM ビューは、ビジネス データの 1 側面です。</span><span class="sxs-lookup"><span data-stu-id="3ab23-111">The BAM portal allows you to perform searches, aggregate data, and set alerts on a BAM view, which is a perspective on your business data.</span></span> <span data-ttu-id="3ab23-112">BAM ポータルの表示により、ビジネスに必要な KPI 情報が提供されます。また、Microsoft Office Excel スプレッドシートの拡張、SQL レポートの使用、カスタム ユーザー インターフェイス (UI) の構築などの別のソリューションを実装する前に、BAM ポータルの表示を利用してビジネスの概念を実証することもできます。</span><span class="sxs-lookup"><span data-stu-id="3ab23-112">This visibility can provide the necessary KPI information for your business, or it can be used as proof of concept before you implement another solution such as extending a Microsoft Office Excel spreadsheet, using SQL Reporting, or building a custom user interface (UI).</span></span>  
  
## <a name="bam-portal-components"></a><span data-ttu-id="3ab23-113">BAM ポータル コンポーネント</span><span class="sxs-lookup"><span data-stu-id="3ab23-113">BAM portal components</span></span>  
 <span data-ttu-id="3ab23-114">ここでは、BAM ポータル コンポーネントについて簡単に説明します。</span><span class="sxs-lookup"><span data-stu-id="3ab23-114">Following is a brief description of the BAM portal components.</span></span> <span data-ttu-id="3ab23-115">より詳細な説明については、「関連項目」のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3ab23-115">For a more detailed description, see the topics in See Also.</span></span>  
  
### <a name="activity-searches"></a><span data-ttu-id="3ab23-116">アクティビティの検索</span><span class="sxs-lookup"><span data-stu-id="3ab23-116">Activity searches</span></span>  
 <span data-ttu-id="3ab23-117">特定の BAM アクティビティを見つけるには、BAM ポータルを使用して BAM データに対して検索を実行します。</span><span class="sxs-lookup"><span data-stu-id="3ab23-117">You use the BAM portal to perform searches against BAM data to find a specific BAM activity.</span></span> <span data-ttu-id="3ab23-118">検索句の追加や削除によって、クエリを作成します。これらの句を使用することにより、警告の通知条件に一致するアクティビティを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="3ab23-118">You create queries by adding and removing search clauses that allow you to display those activities that match criteria for which you want to be alerted.</span></span>  
  
 <span data-ttu-id="3ab23-119">クエリは保存して再利用できます。</span><span class="sxs-lookup"><span data-stu-id="3ab23-119">Queries can be saved and reused.</span></span> <span data-ttu-id="3ab23-120">また、"特定の顧客からの注文書が到着したときに通知を受け取る" など、警告の基準としてクエリを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="3ab23-120">They can also be the basis for an alert, such as a notification when a purchase order arrives from a specific customer.</span></span>  
  
### <a name="aggregations"></a><span data-ttu-id="3ab23-121">集計</span><span class="sxs-lookup"><span data-stu-id="3ab23-121">Aggregations</span></span>  
 <span data-ttu-id="3ab23-122">BAM ポータルでは、データのスナップショットをキャプチャし、グラフィカルなグラフや付属のピボットテーブル グラフの形式で表示できます。</span><span class="sxs-lookup"><span data-stu-id="3ab23-122">The portal allows you to capture a snapshot of data and display it in the form of a graphical chart and accompanying PivotTable chart.</span></span> <span data-ttu-id="3ab23-123">このデータにより、特定のプロセスやビジネス全体の状態を確認できます。</span><span class="sxs-lookup"><span data-stu-id="3ab23-123">This data gives you visibility into the health of that process or the overall business.</span></span> <span data-ttu-id="3ab23-124">たとえば、1 日に受け取った 1,000 件の請求書の内訳を、各請求書の現在の処理段階という観点から示す ("評価中" が 400 件、拒否が 400 件、支払済みが 100 件、"資金割当中" が 100 件など) 簡単な円グラフをユーザーが参照する場合があります。</span><span class="sxs-lookup"><span data-stu-id="3ab23-124">For example, a user may wish to see a simple pie chart that shows a breakdown of the 1,000 invoices received in a day in terms of what stage of processing has been reached by each invoice (400 still in "evaluation," 400 rejected, 100 paid, and 100 still in "fund allocation").</span></span>  
  
 <span data-ttu-id="3ab23-125">提供されるデータを基にして、"プロセスの評価段階に達した請求書が 500 件を超えた場合に通知する" など、警告を作成する際の条件を設定することができます。</span><span class="sxs-lookup"><span data-stu-id="3ab23-125">The data presented can be the basis for creating an alert, such as "Notify me if there are ever more than 500 invoices in the 'evaluation' stage of the process."</span></span>  
  
### <a name="alert-manager"></a><span data-ttu-id="3ab23-126">警告マネージャー</span><span class="sxs-lookup"><span data-stu-id="3ab23-126">Alert Manager</span></span>  
 <span data-ttu-id="3ab23-127">BAM ポータルでは、警告の作成と既存の警告の編集用のインターフェイスを提供します。</span><span class="sxs-lookup"><span data-stu-id="3ab23-127">The portal provides a user interface for the creation of alerts and the editing of existing alerts.</span></span> <span data-ttu-id="3ab23-128">警告では、監視する条件として、[アクティビティの検索] ページまたは [集計] ページのデータを使用します。</span><span class="sxs-lookup"><span data-stu-id="3ab23-128">Alerts take the conditions that are to be monitored from either the Activity Search or Aggregations page.</span></span> <span data-ttu-id="3ab23-129">警告マネージャーでは、警告に関連する情報を入力できます。これらの情報には、通知先、通知方法 (電子メールなど)、他のユーザーが警告を参照およびサブスクライブできるようにするかなどの情報があります。</span><span class="sxs-lookup"><span data-stu-id="3ab23-129">The Alert Manager is where you fill in the relevant parts of an alert, such as who to notify, how (for example, through e-mail), and whether others can see and subscribe to the alert.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3ab23-130">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="3ab23-130">In This Section</span></span>  
  
-   [<span data-ttu-id="3ab23-131">BAM ポータルのコンポーネント</span><span class="sxs-lookup"><span data-stu-id="3ab23-131">Components of the BAM Portal</span></span>](../core/components-of-the-bam-portal.md)  
  
-   [<span data-ttu-id="3ab23-132">BAM ポータルの計画</span><span class="sxs-lookup"><span data-stu-id="3ab23-132">Planning for the BAM Portal</span></span>](../core/planning-for-the-bam-portal.md)  
  
-   [<span data-ttu-id="3ab23-133">BAM ポータルでのアクティビティの検索</span><span class="sxs-lookup"><span data-stu-id="3ab23-133">Activity Searches in the BAM Portal</span></span>](../core/activity-searches-in-the-bam-portal.md)  
  
-   [<span data-ttu-id="3ab23-134">BAM ポータルでの集計</span><span class="sxs-lookup"><span data-stu-id="3ab23-134">Aggregations in the BAM Portal</span></span>](../core/aggregations-in-the-bam-portal.md)  
  
-   [<span data-ttu-id="3ab23-135">BAM ポータルでのアラート</span><span class="sxs-lookup"><span data-stu-id="3ab23-135">Alerts in the BAM Portal</span></span>](../core/alerts-in-the-bam-portal.md)  
  
-   [<span data-ttu-id="3ab23-136">BAM ポータルのユーザー補助機能</span><span class="sxs-lookup"><span data-stu-id="3ab23-136">Accessibility for the BAM Portal</span></span>](../core/accessibility-for-the-bam-portal.md)  
  
-   [<span data-ttu-id="3ab23-137">BAM ポータルのセキュリティに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="3ab23-137">Security Considerations for the BAM Portal</span></span>](../core/security-considerations-for-the-bam-portal.md)  
  
-   [<span data-ttu-id="3ab23-138">BAM ポータルでの既知の問題</span><span class="sxs-lookup"><span data-stu-id="3ab23-138">Known Issues in the BAM Portal</span></span>](../core/known-issues-in-the-bam-portal.md)  
  
## <a name="see-also"></a><span data-ttu-id="3ab23-139">参照</span><span class="sxs-lookup"><span data-stu-id="3ab23-139">See Also</span></span>  
 <span data-ttu-id="3ab23-140">[BAM ポータルにアクティビティの検索 ページ](../core/activity-search-on-the-bam-portal-page.md) </span><span class="sxs-lookup"><span data-stu-id="3ab23-140">[Activity Search on the BAM Portal Page](../core/activity-search-on-the-bam-portal-page.md) </span></span>  
 <span data-ttu-id="3ab23-141">[BAM ポータルの集計 ページ](../core/aggregations-on-the-bam-portal-page.md) </span><span class="sxs-lookup"><span data-stu-id="3ab23-141">[Aggregations on the BAM Portal Page](../core/aggregations-on-the-bam-portal-page.md) </span></span>  
 [<span data-ttu-id="3ab23-142">警告マネージャーで、BAM ポータル ページ</span><span class="sxs-lookup"><span data-stu-id="3ab23-142">Alert Manager on the BAM Portal Page</span></span>](../core/alert-manager-on-the-bam-portal-page.md)