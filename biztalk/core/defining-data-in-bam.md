---
title: Bam データの定義 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- aggregations [BAM], dimensions
- monitoring business activities [BAM], BAM Activity Wizard
- monitoring business activities [BAM], time intervals
- aggregations [BAM], measurements
- monitoring business activities [BAM], views
- monitoring business activities [BAM], aggregations
- Excel add-in [BAM], collecting data
- aggregations [BAM], scheduling
- monitoring business activities [BAM], milestone groups
- aggregations [BAM], real-time data
ms.assetid: 501a1c08-3979-4a99-94d9-0d1b5ec4266b
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 86b40c37f0f0f71a119dcb55465e1c22f30e6267
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390278"
---
# <a name="defining-data-in-bam"></a><span data-ttu-id="f28e0-102">BAM でのデータの定義</span><span class="sxs-lookup"><span data-stu-id="f28e0-102">Defining Data in BAM</span></span>
<span data-ttu-id="f28e0-103">BAM Excel アドインを使用して、収集する BAM データを定義し、データを共有する方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="f28e0-103">You use the BAM Excel Add-in to define the data you want BAM to collect, and define the way in which the data will be shared.</span></span> <span data-ttu-id="f28e0-104">BAM アクティビティを使用して、データを定義し、他のユーザーに表示されるデータを定義する BAM ビューを使用します。</span><span class="sxs-lookup"><span data-stu-id="f28e0-104">You use BAM activities to define the data, and you use BAM views to define the data that other users can see.</span></span>  
  
## <a name="activities"></a><span data-ttu-id="f28e0-105">アクティビティ</span><span class="sxs-lookup"><span data-stu-id="f28e0-105">Activities</span></span>  
 <span data-ttu-id="f28e0-106">BAM を使用して監視するビジネス プロセスに関する情報を定義する BAM アクティビティを作成します。</span><span class="sxs-lookup"><span data-stu-id="f28e0-106">You create a BAM activity to define information about a business process that you want to monitor with BAM.</span></span> <span data-ttu-id="f28e0-107">BAM アクティビティは、ビジネスで特定のビジネス プロセスを表す、処理などの発注書または製品を出荷します。</span><span class="sxs-lookup"><span data-stu-id="f28e0-107">A BAM activity represents a specific business process in the business, such as handling purchase orders or shipping a product.</span></span> <span data-ttu-id="f28e0-108">ビジネス プロセスには、マイルス トーンとビジネス データの定義済みセットがあります。</span><span class="sxs-lookup"><span data-stu-id="f28e0-108">A business process has a defined set of milestones and business data.</span></span> <span data-ttu-id="f28e0-109">たとえば、発注プロセスには、承認済み、拒否、および配信済みなどのマイルス トーン顧客名や製品などのビジネス データとがあります。</span><span class="sxs-lookup"><span data-stu-id="f28e0-109">For example, a purchase order process might have milestones such as Approved, Denied, and Delivered along with business data like Customer Name and Product.</span></span>  
  
 <span data-ttu-id="f28e0-110">BAM アクティビティの目的では、インフォメーション ワーカーに履歴 (マイルス トーン) とプロセスに関するデータを説明します。</span><span class="sxs-lookup"><span data-stu-id="f28e0-110">The intention of a BAM activity is to show the history (milestones) and data about a process to information workers.</span></span> <span data-ttu-id="f28e0-111">BAM アクティビティは、BizTalk Server の実際の実装に依存しない高レベルの抽象化です。</span><span class="sxs-lookup"><span data-stu-id="f28e0-111">BAM activities are high-level abstractions that are independent of the actual implementation of BizTalk Server.</span></span> <span data-ttu-id="f28e0-112">BAM の概念的概要については、「ビジネス アクティビティ監視」トピックを参照してください[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。</span><span class="sxs-lookup"><span data-stu-id="f28e0-112">For a conceptual overview of BAM, see the topic "Business Activity Monitoring" in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help.</span></span>  
  
 <span data-ttu-id="f28e0-113">BAM アクティビティ ウィザードを使用すると、少なくとも 1 つのアクティビティ項目を含む BAM アクティビティを定義できます。</span><span class="sxs-lookup"><span data-stu-id="f28e0-113">You use the BAM Activity Wizard to define BAM activities that contain at least one activity item.</span></span> <span data-ttu-id="f28e0-114">活動に関連するアクティビティ項目をグループ化して、アクティビティ項目を使用して、ビジネス プロセスから使用できるようにしデータの種類を記述します。</span><span class="sxs-lookup"><span data-stu-id="f28e0-114">You group related activity items in an activity, and you use activity items to describe the type of data you want to make available from a business process.</span></span>  
  
 <span data-ttu-id="f28e0-115">次の表に、種類のアクティビティ項目の BAM を提供します。</span><span class="sxs-lookup"><span data-stu-id="f28e0-115">The following table describes the types of activity items BAM provides.</span></span>  
  
|<span data-ttu-id="f28e0-116">アイテムの種類</span><span class="sxs-lookup"><span data-stu-id="f28e0-116">Item type</span></span>|<span data-ttu-id="f28e0-117">説明</span><span class="sxs-lookup"><span data-stu-id="f28e0-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f28e0-118">ビジネス マイルス トーン</span><span class="sxs-lookup"><span data-stu-id="f28e0-118">Business Milestone</span></span>|<span data-ttu-id="f28e0-119">日付/時刻値。</span><span class="sxs-lookup"><span data-stu-id="f28e0-119">A date/time value.</span></span> <span data-ttu-id="f28e0-120">たとえば、注文書が承認された日付です。</span><span class="sxs-lookup"><span data-stu-id="f28e0-120">For example, an approval date for a purchase order.</span></span>|  
|<span data-ttu-id="f28e0-121">ビジネス データ - Text</span><span class="sxs-lookup"><span data-stu-id="f28e0-121">Business Data - Text</span></span>|<span data-ttu-id="f28e0-122">任意の英数字の文字列。</span><span class="sxs-lookup"><span data-stu-id="f28e0-122">A string containing any alphanumeric characters.</span></span> <span data-ttu-id="f28e0-123">たとえば、出荷先。市区町村、都道府県、郵便コードです。</span><span class="sxs-lookup"><span data-stu-id="f28e0-123">For example, Ship to: City, State/Province and Zip/Postal code.</span></span>|  
|<span data-ttu-id="f28e0-124">ビジネス データ - Integer</span><span class="sxs-lookup"><span data-stu-id="f28e0-124">Business Data - Integer</span></span>|<span data-ttu-id="f28e0-125">整数値。</span><span class="sxs-lookup"><span data-stu-id="f28e0-125">A whole number value.</span></span> <span data-ttu-id="f28e0-126">たとえば、注文の合計数です。</span><span class="sxs-lookup"><span data-stu-id="f28e0-126">For example, the total number of purchases.</span></span>|  
|<span data-ttu-id="f28e0-127">ビジネス データ - 浮動小数点します。</span><span class="sxs-lookup"><span data-stu-id="f28e0-127">Business Data - Float</span></span>|<span data-ttu-id="f28e0-128">decimal 値です。</span><span class="sxs-lookup"><span data-stu-id="f28e0-128">A decimal value.</span></span> <span data-ttu-id="f28e0-129">たとえば、PO の合計金額です。</span><span class="sxs-lookup"><span data-stu-id="f28e0-129">For example the total dollar amount of the PO.</span></span>|  
  
 <span data-ttu-id="f28e0-130">たとえば、発注アクティビティで、次の表のアクティビティ項目を作成する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f28e0-130">For example, in a purchase order activity, you might create the activity items in the following table.</span></span>  
  
|<span data-ttu-id="f28e0-131">アクティビティ項目</span><span class="sxs-lookup"><span data-stu-id="f28e0-131">Activity item</span></span>|<span data-ttu-id="f28e0-132">アイテムの種類</span><span class="sxs-lookup"><span data-stu-id="f28e0-132">Item type</span></span>|  
|-------------------|---------------|  
|<span data-ttu-id="f28e0-133">製品</span><span class="sxs-lookup"><span data-stu-id="f28e0-133">Product</span></span>|<span data-ttu-id="f28e0-134">ビジネス データ-テキスト</span><span class="sxs-lookup"><span data-stu-id="f28e0-134">Business Data — Text</span></span>|  
|<span data-ttu-id="f28e0-135">City</span><span class="sxs-lookup"><span data-stu-id="f28e0-135">City</span></span>|<span data-ttu-id="f28e0-136">ビジネス データ-テキスト</span><span class="sxs-lookup"><span data-stu-id="f28e0-136">Business Data — Text</span></span>|  
|<span data-ttu-id="f28e0-137">状態</span><span class="sxs-lookup"><span data-stu-id="f28e0-137">State</span></span>|<span data-ttu-id="f28e0-138">ビジネス データ-テキスト</span><span class="sxs-lookup"><span data-stu-id="f28e0-138">Business Data — Text</span></span>|  
|<span data-ttu-id="f28e0-139">Amount</span><span class="sxs-lookup"><span data-stu-id="f28e0-139">Amount</span></span>|<span data-ttu-id="f28e0-140">ビジネス データ-Float</span><span class="sxs-lookup"><span data-stu-id="f28e0-140">Business Data — Float</span></span>|  
|<span data-ttu-id="f28e0-141">Quantity</span><span class="sxs-lookup"><span data-stu-id="f28e0-141">Quantity</span></span>|<span data-ttu-id="f28e0-142">ビジネス データ-Integer</span><span class="sxs-lookup"><span data-stu-id="f28e0-142">Business Data — Integer</span></span>|  
|<span data-ttu-id="f28e0-143">承認</span><span class="sxs-lookup"><span data-stu-id="f28e0-143">Approved</span></span>|<span data-ttu-id="f28e0-144">ビジネス マイルス トーン</span><span class="sxs-lookup"><span data-stu-id="f28e0-144">Business Milestone</span></span>|  
|<span data-ttu-id="f28e0-145">配信</span><span class="sxs-lookup"><span data-stu-id="f28e0-145">Delivered</span></span>|<span data-ttu-id="f28e0-146">ビジネス マイルス トーン</span><span class="sxs-lookup"><span data-stu-id="f28e0-146">Business Milestone</span></span>|  
|<span data-ttu-id="f28e0-147">拒否</span><span class="sxs-lookup"><span data-stu-id="f28e0-147">Denied</span></span>|<span data-ttu-id="f28e0-148">ビジネス マイルス トーン</span><span class="sxs-lookup"><span data-stu-id="f28e0-148">Business Milestone</span></span>|  
|<span data-ttu-id="f28e0-149">受信しました。</span><span class="sxs-lookup"><span data-stu-id="f28e0-149">Received</span></span>|<span data-ttu-id="f28e0-150">ビジネス マイルス トーン</span><span class="sxs-lookup"><span data-stu-id="f28e0-150">Business Milestone</span></span>|  
  
 <span data-ttu-id="f28e0-151">金額は、10 進値可能性があるため、float に注意してください。</span><span class="sxs-lookup"><span data-stu-id="f28e0-151">Note that Amount is a float because it may be a decimal value.</span></span> <span data-ttu-id="f28e0-152">数量は、この例では、整数は常に整数です。</span><span class="sxs-lookup"><span data-stu-id="f28e0-152">Quantity is an integer because it will always be a whole number in this example.</span></span> <span data-ttu-id="f28e0-153">すべてのマイルス トーン、発注プロセスでは、承認されると、配信済み、拒否、および受信済みからです。</span><span class="sxs-lookup"><span data-stu-id="f28e0-153">Approved, Delivered, Denied, and Received are all milestones in the purchase order process.</span></span>  
  
## <a name="views"></a><span data-ttu-id="f28e0-154">ビュー</span><span class="sxs-lookup"><span data-stu-id="f28e0-154">Views</span></span>  
 <span data-ttu-id="f28e0-155">アクティビティからのデータをユーザーに公開するビューを作成します。</span><span class="sxs-lookup"><span data-stu-id="f28e0-155">You create views to expose data from an activity to users.</span></span> <span data-ttu-id="f28e0-156">発注アクティビティに基づいてビューを作成するときに、アクティビティ項目の背後にあるデータを定義します。</span><span class="sxs-lookup"><span data-stu-id="f28e0-156">When you create a view based on the purchase order activity, you define the data behind the activity items.</span></span> <span data-ttu-id="f28e0-157">ディメンション、メジャー、期間、マイルス トーン グループ、および進捗ディメンションとして bam データの表示を定義します。</span><span class="sxs-lookup"><span data-stu-id="f28e0-157">You define view data in BAM as dimensions, measures, durations, milestone groups, and progress dimensions.</span></span>  
  
 <span data-ttu-id="f28e0-158">ビューには、1 つまたは複数のアイテム表示にはが含まれています。</span><span class="sxs-lookup"><span data-stu-id="f28e0-158">A view contains one or more view items.</span></span> <span data-ttu-id="f28e0-159">次の種類のアイテムの表示を作成できます。</span><span class="sxs-lookup"><span data-stu-id="f28e0-159">You can create the following types of view items:</span></span>  
  
-   <span data-ttu-id="f28e0-160">期間</span><span class="sxs-lookup"><span data-stu-id="f28e0-160">Durations</span></span>  
  
-   <span data-ttu-id="f28e0-161">マイルス トーン グループ</span><span class="sxs-lookup"><span data-stu-id="f28e0-161">Milestone groups</span></span>  
  
-   <span data-ttu-id="f28e0-162">集計</span><span class="sxs-lookup"><span data-stu-id="f28e0-162">Aggregations</span></span>  
  
### <a name="durations"></a><span data-ttu-id="f28e0-163">期間</span><span class="sxs-lookup"><span data-stu-id="f28e0-163">Durations</span></span>  
 <span data-ttu-id="f28e0-164">期間は、時間間隔です。</span><span class="sxs-lookup"><span data-stu-id="f28e0-164">Durations are time intervals.</span></span> <span data-ttu-id="f28e0-165">期間は、開始と終了の時間間隔を定義するマイルス トーンの観点から説明します。</span><span class="sxs-lookup"><span data-stu-id="f28e0-165">Durations are described in terms of the milestones that define the start and end of time intervals.</span></span> <span data-ttu-id="f28e0-166">次の表では、前の表に示すマイルス トーンから作成できる期間を示します。</span><span class="sxs-lookup"><span data-stu-id="f28e0-166">The following table shows the durations you can make from the milestones listed in the previous table.</span></span>  
  
|<span data-ttu-id="f28e0-167">Duration</span><span class="sxs-lookup"><span data-stu-id="f28e0-167">Duration</span></span>|<span data-ttu-id="f28e0-168">マイルス トーンを開始します。</span><span class="sxs-lookup"><span data-stu-id="f28e0-168">Start milestone</span></span>|<span data-ttu-id="f28e0-169">マイルス トーンの終了</span><span class="sxs-lookup"><span data-stu-id="f28e0-169">End milestone</span></span>|  
|--------------|---------------------|-------------------|  
|<span data-ttu-id="f28e0-170">1</span><span class="sxs-lookup"><span data-stu-id="f28e0-170">1</span></span>|<span data-ttu-id="f28e0-171">受信しました。</span><span class="sxs-lookup"><span data-stu-id="f28e0-171">Received</span></span>|<span data-ttu-id="f28e0-172">承認</span><span class="sxs-lookup"><span data-stu-id="f28e0-172">Approved</span></span>|  
|<span data-ttu-id="f28e0-173">2</span><span class="sxs-lookup"><span data-stu-id="f28e0-173">2</span></span>|<span data-ttu-id="f28e0-174">受信しました。</span><span class="sxs-lookup"><span data-stu-id="f28e0-174">Received</span></span>|<span data-ttu-id="f28e0-175">配信</span><span class="sxs-lookup"><span data-stu-id="f28e0-175">Delivered</span></span>|  
|<span data-ttu-id="f28e0-176">3</span><span class="sxs-lookup"><span data-stu-id="f28e0-176">3</span></span>|<span data-ttu-id="f28e0-177">受信しました。</span><span class="sxs-lookup"><span data-stu-id="f28e0-177">Received</span></span>|<span data-ttu-id="f28e0-178">拒否</span><span class="sxs-lookup"><span data-stu-id="f28e0-178">Denied</span></span>|  
|<span data-ttu-id="f28e0-179">4</span><span class="sxs-lookup"><span data-stu-id="f28e0-179">4</span></span>|<span data-ttu-id="f28e0-180">承認</span><span class="sxs-lookup"><span data-stu-id="f28e0-180">Approved</span></span>|<span data-ttu-id="f28e0-181">配信</span><span class="sxs-lookup"><span data-stu-id="f28e0-181">Delivered</span></span>|  
  
 <span data-ttu-id="f28e0-182">この表では、最初の期間 (期間 1) は、注文書は、BizTalk Server によって受信され、注文書が承認されたときに終了したときに起動する時間間隔がわかります。</span><span class="sxs-lookup"><span data-stu-id="f28e0-182">In this table, you can see that the first duration (Duration 1) is the time interval that starts when a purchase order is received by BizTalk Server, and ends when the purchase order is approved.</span></span>  
  
### <a name="milestone-groups"></a><span data-ttu-id="f28e0-183">マイルス トーン グループ</span><span class="sxs-lookup"><span data-stu-id="f28e0-183">Milestone groups</span></span>  
 <span data-ttu-id="f28e0-184">マイルス トーン グループ一連のマイルス トーンをたとえば 1 つのエンティティとして扱うには、開始日と終了、プロセスの全体の長さを表す 1 つのマイルス トーンを作成するプロセスのマイルス トーンを作成します。</span><span class="sxs-lookup"><span data-stu-id="f28e0-184">You create milestone groups to treat a set of milestones as a single entity, for example, the beginning and ending milestones for a process, which creates a single milestone to represent the entire length of the process.</span></span>  
  
### <a name="aggregations"></a><span data-ttu-id="f28e0-185">集計</span><span class="sxs-lookup"><span data-stu-id="f28e0-185">Aggregations</span></span>  
 <span data-ttu-id="f28e0-186">データベースからデータを更新するための応答時間を短縮するのにには、集計を使用します。</span><span class="sxs-lookup"><span data-stu-id="f28e0-186">You use aggregations to improve the response time for refreshing data from the database.</span></span> <span data-ttu-id="f28e0-187">Excel では、集計を事前計算された要約データとして定義し、質問の答えをあらかじめ用意しておくことで、クエリの応答時間を短縮します。</span><span class="sxs-lookup"><span data-stu-id="f28e0-187">Excel defines aggregations as pre-calculated summaries of data that improve query response time by having the answers ready before the questions are asked.</span></span> <span data-ttu-id="f28e0-188">たとえば、数十万行が格納されているデータ ウェアハウスのファクト テーブルに対して、特定の 2 つの製品の出荷スケジュールを要求するクエリがあるとします。この計算でファクト テーブルをスキャンする必要があると、応答に時間がかかります。</span><span class="sxs-lookup"><span data-stu-id="f28e0-188">For example, when a data warehouse fact table contains hundreds of thousands of rows, a query requesting the shipping schedules for two particular products can take a long time to answer if the fact table has to be scanned to compute the answer.</span></span> <span data-ttu-id="f28e0-189">ただし、このクエリの回答となる集計データがあらかじめ計算されていれば、即座に応答できます。</span><span class="sxs-lookup"><span data-stu-id="f28e0-189">However, the response can be almost immediate if the summarization data to answer this query has been pre-calculated.</span></span>  
  
 <span data-ttu-id="f28e0-190">次に、事前に計算された集計データの例を示します。</span><span class="sxs-lookup"><span data-stu-id="f28e0-190">The following figure displays an example of pre-calculated aggregation data.</span></span>  
  
 <span data-ttu-id="f28e0-191">![](../core/media/bam-olap-cube.gif "bam_olap_cube")</span><span class="sxs-lookup"><span data-stu-id="f28e0-191">![](../core/media/bam-olap-cube.gif "bam_olap_cube")</span></span>  
  
 <span data-ttu-id="f28e0-192">図 2 か月の期間にわたって特定の場所に出荷された各製品の数をまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="f28e0-192">The figure summarizes the numbers of each product shipped to specific locations over a two-month time period.</span></span> <span data-ttu-id="f28e0-193">通常、Excel では、このデータをメジャーとして定義し、</span><span class="sxs-lookup"><span data-stu-id="f28e0-193">Excel typically defines this data as measure.</span></span> <span data-ttu-id="f28e0-194">フィルター選択または分類に使用するデータをディメンションとして定義します。</span><span class="sxs-lookup"><span data-stu-id="f28e0-194">The data used for filtering and categorization, Excel defines as dimension.</span></span>  
  
 <span data-ttu-id="f28e0-195">BAM ブックでは、2 種類の集計を定義できます。</span><span class="sxs-lookup"><span data-stu-id="f28e0-195">You can define two types of aggregations in the BAM workbook:</span></span>  
  
-   <span data-ttu-id="f28e0-196">リアルタイム集計</span><span class="sxs-lookup"><span data-stu-id="f28e0-196">Real-time aggregations</span></span>  
  
-   <span data-ttu-id="f28e0-197">スケジュール済みの集計</span><span class="sxs-lookup"><span data-stu-id="f28e0-197">Scheduled aggregations</span></span>  
  
### <a name="real-time-aggregations"></a><span data-ttu-id="f28e0-198">リアルタイム集計</span><span class="sxs-lookup"><span data-stu-id="f28e0-198">Real-time aggregations</span></span>  
 <span data-ttu-id="f28e0-199">リアルタイム集計 (RTA) では、ビジネス プロセスの現在の状態を確認し、プロセスのボトルネックを簡単に識別するためにできます。</span><span class="sxs-lookup"><span data-stu-id="f28e0-199">Real-time aggregations (RTA) allow you to see the current state of the business process and to easily identify process bottlenecks.</span></span>  
  
 <span data-ttu-id="f28e0-200">BAM データは、ピボット テーブルに表示されます。</span><span class="sxs-lookup"><span data-stu-id="f28e0-200">BAM data is displayed in a pivot table.</span></span> <span data-ttu-id="f28e0-201">BAM ピボット テーブルは RTA またはスケジュール済み集計として定義できます。</span><span class="sxs-lookup"><span data-stu-id="f28e0-201">You can define a BAM pivot table as an RTA or a scheduled aggregation.</span></span> <span data-ttu-id="f28e0-202">RTA を使用すると、たとえば特定の PO が出荷処理中であるなど、データの現時点のビューを表示できます。</span><span class="sxs-lookup"><span data-stu-id="f28e0-202">An RTA gives you an up-to-the-minute view of your data, for example, where a particular PO is in the shipping process.</span></span> <span data-ttu-id="f28e0-203">1 日のうちいつでも画面を更新して、データのビューを最新の状態にできます。</span><span class="sxs-lookup"><span data-stu-id="f28e0-203">You can refresh your screen to update the view of the data throughout the day.</span></span>  
  
 <span data-ttu-id="f28e0-204">場合によっては、多次元集計の特定のスライスは時間を区別するためにリアルタイムで使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="f28e0-204">In some cases, specific slices of the multidimensional aggregations are so time-sensitive that you want them to be available in real time.</span></span> <span data-ttu-id="f28e0-205">たとえば、使い捨ての製品を販売しているお客様のビジネスとをリアルタイムで使用できる配信のさまざまな段階での製品の数量の集計します。</span><span class="sxs-lookup"><span data-stu-id="f28e0-205">For example, your business is selling perishable products and you want the aggregation of product quantity in different stages of delivery to be available in real time.</span></span> <span data-ttu-id="f28e0-206">同時に、必要なその他の集計、年齢などの一般的な顧客がビジネス インテリジェンス分析の月の最後にのみです。</span><span class="sxs-lookup"><span data-stu-id="f28e0-206">At the same time, you want other aggregations such as the age of your typical customers, but only at the end of the month for business intelligence analysis.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="f28e0-207">同じ BAM アクティビティを使用する RTA を複数定義しないでください。</span><span class="sxs-lookup"><span data-stu-id="f28e0-207">Do not define multiple RTAs that use the same BAM activity.</span></span> <span data-ttu-id="f28e0-208">そのような RTA を複数定義した場合、BAM データをアーカイブしたときに RTA データが不正確になります。</span><span class="sxs-lookup"><span data-stu-id="f28e0-208">If you do so, the RTA data will be incorrect when you archive the BAM data.</span></span>  
  
 <span data-ttu-id="f28e0-209">多次元データについては、Excel のヘルプでピボット テーブルに関するトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f28e0-209">For information about browsing multidimensional data, see the PivotTable topic in Excel Help.</span></span>  
  
### <a name="scheduled-aggregations"></a><span data-ttu-id="f28e0-210">スケジュール済みの集計</span><span class="sxs-lookup"><span data-stu-id="f28e0-210">Scheduled aggregations</span></span>  
 <span data-ttu-id="f28e0-211">すべての BAM 集計とは、既定ではスケジュール済みの集計です。</span><span class="sxs-lookup"><span data-stu-id="f28e0-211">All BAM aggregations are scheduled aggregations by default.</span></span> <span data-ttu-id="f28e0-212">スケジュール済みの集計は、今朝の出荷の概要など、指定した期間のビジネス データのスナップショットを表します。</span><span class="sxs-lookup"><span data-stu-id="f28e0-212">A scheduled aggregation represents a snapshot of the business at a specific time, for example, a summary of this morning's shipments.</span></span> <span data-ttu-id="f28e0-213">集計が処理される時期については、データベース管理者に問い合わせてください。集計が処理されると、履歴データを見ることができます。</span><span class="sxs-lookup"><span data-stu-id="f28e0-213">Ask your database administrator when your aggregations are processed, and then you can look at the historical data.</span></span>  
  
### <a name="dimensions-and-measures"></a><span data-ttu-id="f28e0-214">ディメンションとメジャー</span><span class="sxs-lookup"><span data-stu-id="f28e0-214">Dimensions and Measures</span></span>  
 <span data-ttu-id="f28e0-215">ディメンションとメジャーを使用してデータの集計を作成します。</span><span class="sxs-lookup"><span data-stu-id="f28e0-215">You use dimensions and measures to create data aggregations:</span></span>  
  
- <span data-ttu-id="f28e0-216">ディメンションはファクトを説明します。</span><span class="sxs-lookup"><span data-stu-id="f28e0-216">Dimensions describe a fact.</span></span>  
  
- <span data-ttu-id="f28e0-217">メジャーは、ファクトの値です。</span><span class="sxs-lookup"><span data-stu-id="f28e0-217">Measures are fact values.</span></span>  
  
  <span data-ttu-id="f28e0-218">たとえば、ファクトには、「3 赤い自動車」インベントリに可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f28e0-218">For example, a fact could be “3 red cars” in inventory.</span></span> <span data-ttu-id="f28e0-219">製品の説明:"car"と「赤い」はディメンションです。</span><span class="sxs-lookup"><span data-stu-id="f28e0-219">The description of the product: "car" and "red" are dimensions.</span></span> <span data-ttu-id="f28e0-220">ファクト「3」の値は、メジャーです。</span><span class="sxs-lookup"><span data-stu-id="f28e0-220">The value of the fact "3" is a measure.</span></span> <span data-ttu-id="f28e0-221">実際には、自動車の価格が含まれる場合、自動車の価格は、ディメンションが、インベントリにある自動車の平均価格はメジャーです。</span><span class="sxs-lookup"><span data-stu-id="f28e0-221">If the price of each car is included in the fact, the car price is a dimension, but the average price of cars in inventory is a measure.</span></span> <span data-ttu-id="f28e0-222">Microsoft SQL Server オンライン ブックに「中央値は集計され、分析します」として、メジャーについて説明します</span><span class="sxs-lookup"><span data-stu-id="f28e0-222">Microsoft SQL Server Books Online describes a measure as "the central values that are aggregated and analyzed."</span></span> <span data-ttu-id="f28e0-223">つまり、それをカウント、平均する、またはそれ以外の場合に数学関数を実行できる場合、は、メジャーです。</span><span class="sxs-lookup"><span data-stu-id="f28e0-223">In other words, if you can count it, average it, or otherwise perform mathematical functions to get it, it is a measure.</span></span>  
  
  <span data-ttu-id="f28e0-224">次の種類のディメンションを作成できます。</span><span class="sxs-lookup"><span data-stu-id="f28e0-224">You can create the following types of dimensions:</span></span>  
  
- <span data-ttu-id="f28e0-225">進捗ディメンション</span><span class="sxs-lookup"><span data-stu-id="f28e0-225">Progress dimension</span></span>  
  
- <span data-ttu-id="f28e0-226">データ ディメンション</span><span class="sxs-lookup"><span data-stu-id="f28e0-226">Data dimension</span></span>  
  
- <span data-ttu-id="f28e0-227">時間ディメンション</span><span class="sxs-lookup"><span data-stu-id="f28e0-227">Time dimension</span></span>  
  
- <span data-ttu-id="f28e0-228">数値範囲ディメンション</span><span class="sxs-lookup"><span data-stu-id="f28e0-228">Numeric range dimension</span></span>  
  
## <a name="progress-dimensions"></a><span data-ttu-id="f28e0-229">進捗ディメンション</span><span class="sxs-lookup"><span data-stu-id="f28e0-229">Progress dimensions</span></span>  
 <span data-ttu-id="f28e0-230">BAM には新しい種類のディメンションが導入されています。 進行状況ディメンション。</span><span class="sxs-lookup"><span data-stu-id="f28e0-230">BAM introduces a new type of dimension: the progress dimension.</span></span> <span data-ttu-id="f28e0-231">進捗ディメンションを作成プロセス中のアクティビティの進行状況に関連する集計を作成します。</span><span class="sxs-lookup"><span data-stu-id="f28e0-231">You create progress dimensions to create aggregations that relate to the progress of activities still in process.</span></span>  
  
 <span data-ttu-id="f28e0-232">たとえば、1,000 件の注文を受信する発注ビジネス プロセスを検討してください。</span><span class="sxs-lookup"><span data-stu-id="f28e0-232">For example, consider a purchasing business process where you receive 1,000 purchase orders.</span></span> <span data-ttu-id="f28e0-233">行に進捗ディメンションを使用すると、次の表を作成します。</span><span class="sxs-lookup"><span data-stu-id="f28e0-233">You can use the progress dimension on rows to create the following table.</span></span>  
  
|<span data-ttu-id="f28e0-234">OrderProgress_Level1</span><span class="sxs-lookup"><span data-stu-id="f28e0-234">OrderProgress_Level1</span></span>|<span data-ttu-id="f28e0-235">Count</span><span class="sxs-lookup"><span data-stu-id="f28e0-235">Count</span></span>|  
|---------------------------|-----------|  
|<span data-ttu-id="f28e0-236">受信しました。</span><span class="sxs-lookup"><span data-stu-id="f28e0-236">Received</span></span>|<span data-ttu-id="f28e0-237">1000</span><span class="sxs-lookup"><span data-stu-id="f28e0-237">1000</span></span>|  
  
 <span data-ttu-id="f28e0-238">詳細を表示するさらに、アクティビティの進行状況などの受信プロセスを開くことができます。</span><span class="sxs-lookup"><span data-stu-id="f28e0-238">You can then open the Received process to view further details about the progress of the activities, such as:</span></span>  
  
|||<span data-ttu-id="f28e0-239">Count</span><span class="sxs-lookup"><span data-stu-id="f28e0-239">Count</span></span>|  
|------|------|-----------|  
|<span data-ttu-id="f28e0-240">受信しました。</span><span class="sxs-lookup"><span data-stu-id="f28e0-240">Received</span></span>|<span data-ttu-id="f28e0-241">評価します。</span><span class="sxs-lookup"><span data-stu-id="f28e0-241">Evaluating</span></span>|<span data-ttu-id="f28e0-242">300</span><span class="sxs-lookup"><span data-stu-id="f28e0-242">300</span></span>|  
||<span data-ttu-id="f28e0-243">承認</span><span class="sxs-lookup"><span data-stu-id="f28e0-243">Approved</span></span>|<span data-ttu-id="f28e0-244">500</span><span class="sxs-lookup"><span data-stu-id="f28e0-244">500</span></span>|  
||<span data-ttu-id="f28e0-245">拒否</span><span class="sxs-lookup"><span data-stu-id="f28e0-245">Denied</span></span>|<span data-ttu-id="f28e0-246">200</span><span class="sxs-lookup"><span data-stu-id="f28e0-246">200</span></span>|  
  
 <span data-ttu-id="f28e0-247">つまり、受信した 1000 の発注書から 500 が承認された、200 件が拒否されると、300 は現在評価されています。</span><span class="sxs-lookup"><span data-stu-id="f28e0-247">This means that from the 1000 purchase orders you received, 500 were approved, 200 were denied, and 300 are currently being evaluated.</span></span>  
  
 <span data-ttu-id="f28e0-248">Received、Approved、Denied マイルス トーンを表します.</span><span class="sxs-lookup"><span data-stu-id="f28e0-248">Received, Approved, and Denied represent milestones.</span></span> <span data-ttu-id="f28e0-249">カウント列の対応する数値は、注文の数は、これらのマイルス トーンを通過しているを表示します。</span><span class="sxs-lookup"><span data-stu-id="f28e0-249">The corresponding numbers in the Count column show how many orders have passed through these milestones.</span></span> <span data-ttu-id="f28e0-250">評価は、注文を受信し、承認または拒否マイルス トーンの間で通過する段階です。</span><span class="sxs-lookup"><span data-stu-id="f28e0-250">Evaluating is a stage that the orders pass through between the Received and Approved or Denied milestones.</span></span>  
  
 <span data-ttu-id="f28e0-251">進行状況ディメンションは、他のすべてのディメンションと組み合わせて使用できます。</span><span class="sxs-lookup"><span data-stu-id="f28e0-251">You can use progress dimensions in combination with any other dimensions.</span></span> <span data-ttu-id="f28e0-252">たとえば、進捗ディメンションの注文の進捗状況を行と、データを使用してディメンション製品列で、次の結果が発生します。</span><span class="sxs-lookup"><span data-stu-id="f28e0-252">For example, by using the progress dimension Order Progress on rows and the data dimension Product on columns, the following results occur:</span></span>  
  
|||<span data-ttu-id="f28e0-253">テニス ラケット</span><span class="sxs-lookup"><span data-stu-id="f28e0-253">Tennis Racquets</span></span>|<span data-ttu-id="f28e0-254">サッカー ボール</span><span class="sxs-lookup"><span data-stu-id="f28e0-254">Soccer Balls</span></span>|  
|------|------|---------------------|------------------|  
|<span data-ttu-id="f28e0-255">受信しました。</span><span class="sxs-lookup"><span data-stu-id="f28e0-255">Received</span></span>|<span data-ttu-id="f28e0-256">評価します。</span><span class="sxs-lookup"><span data-stu-id="f28e0-256">Evaluating</span></span>|<span data-ttu-id="f28e0-257">250</span><span class="sxs-lookup"><span data-stu-id="f28e0-257">250</span></span>|<span data-ttu-id="f28e0-258">50</span><span class="sxs-lookup"><span data-stu-id="f28e0-258">50</span></span>|  
||<span data-ttu-id="f28e0-259">承認</span><span class="sxs-lookup"><span data-stu-id="f28e0-259">Approved</span></span>|<span data-ttu-id="f28e0-260">200</span><span class="sxs-lookup"><span data-stu-id="f28e0-260">200</span></span>|<span data-ttu-id="f28e0-261">300</span><span class="sxs-lookup"><span data-stu-id="f28e0-261">300</span></span>|  
||<span data-ttu-id="f28e0-262">拒否</span><span class="sxs-lookup"><span data-stu-id="f28e0-262">Denied</span></span>|<span data-ttu-id="f28e0-263">150</span><span class="sxs-lookup"><span data-stu-id="f28e0-263">150</span></span>|<span data-ttu-id="f28e0-264">50</span><span class="sxs-lookup"><span data-stu-id="f28e0-264">50</span></span>|  
  
 <span data-ttu-id="f28e0-265">進捗ディメンションでは、リアルタイム集計 (RTA) に基づくグラフ特に有用な情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="f28e0-265">Progress dimensions provide especially useful information for charts based on real-time aggregations (RTA).</span></span> <span data-ttu-id="f28e0-266">Rta では、ビジネス プロセスの現在の状態を確認し、プロセスのボトルネックを簡単に識別するためにできます。</span><span class="sxs-lookup"><span data-stu-id="f28e0-266">RTAs allow you to see the current state of the business process and to easily identify process bottlenecks.</span></span>  
  
 <span data-ttu-id="f28e0-267">購入のマイルス トーンが進捗ディメンションをシーケンシャルにすることができますを注文: 次の手順を開始する前に、最初の手順が完了しました。</span><span class="sxs-lookup"><span data-stu-id="f28e0-267">The milestones in a purchase order progress dimension can be sequential: the first step is completed before the next step is started.</span></span> <span data-ttu-id="f28e0-268">または、マイルス トーンが連携して行うことができます。</span><span class="sxs-lookup"><span data-stu-id="f28e0-268">Or milestones can be completed in tandem.</span></span> <span data-ttu-id="f28e0-269">一連のステップは子ステップと平行ステップは兄弟ステップです。</span><span class="sxs-lookup"><span data-stu-id="f28e0-269">Sequential steps are child steps, and tandem steps are sibling steps.</span></span> <span data-ttu-id="f28e0-270">発注書の処理では、検証は、注文書を受信するとすぐを開始します。</span><span class="sxs-lookup"><span data-stu-id="f28e0-270">In the purchase order process, verification begins as soon as the purchase order is received.</span></span> <span data-ttu-id="f28e0-271">受信マイルス トーンと同時に発生し、受信マイルス トーンに兄弟ではそのため、一時的なステップになります。</span><span class="sxs-lookup"><span data-stu-id="f28e0-271">It is a transitory step that occurs at the same time as the received milestone, and is therefore a sibling to the receive milestone.</span></span> <span data-ttu-id="f28e0-272">受信後にのみ発注書が承認された-がの子の受信を承認します。</span><span class="sxs-lookup"><span data-stu-id="f28e0-272">A purchase order is approved only after it is received — approved is a child of received.</span></span>  
  
## <a name="data-dimension"></a><span data-ttu-id="f28e0-273">データ ディメンション</span><span class="sxs-lookup"><span data-stu-id="f28e0-273">Data dimension</span></span>  
 <span data-ttu-id="f28e0-274">行または列の BAM アクティビティ内のテキスト項目の値を使用するデータ ディメンションを定義します。</span><span class="sxs-lookup"><span data-stu-id="f28e0-274">You define a data dimension to use the value of some text items in the BAM activity on rows or columns.</span></span> <span data-ttu-id="f28e0-275">たとえば、次の表を作成する製品の名前のデータ ディメンションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="f28e0-275">For example, a data dimension named Product can be used to create the following table:</span></span>  
  
|<span data-ttu-id="f28e0-276">製品</span><span class="sxs-lookup"><span data-stu-id="f28e0-276">Product</span></span>|<span data-ttu-id="f28e0-277">Count</span><span class="sxs-lookup"><span data-stu-id="f28e0-277">Count</span></span>|  
|-------------|-----------|  
|<span data-ttu-id="f28e0-278">テニス ラケット</span><span class="sxs-lookup"><span data-stu-id="f28e0-278">Tennis racquets</span></span>|<span data-ttu-id="f28e0-279">100</span><span class="sxs-lookup"><span data-stu-id="f28e0-279">100</span></span>|  
|<span data-ttu-id="f28e0-280">サッカー ボール</span><span class="sxs-lookup"><span data-stu-id="f28e0-280">Soccer balls</span></span>|<span data-ttu-id="f28e0-281">200</span><span class="sxs-lookup"><span data-stu-id="f28e0-281">200</span></span>|  
  
 <span data-ttu-id="f28e0-282">また、BAM ビュー ウィザードでは、複数のデータ ディメンションを定義できます。</span><span class="sxs-lookup"><span data-stu-id="f28e0-282">Also, you can define more than one data dimension in the BAM View Wizard.</span></span> <span data-ttu-id="f28e0-283">たとえば、次の表を作成するには、都道府県と市区町村レベルの場所をという名前のデータ ディメンションの定義を使用できます。</span><span class="sxs-lookup"><span data-stu-id="f28e0-283">For example, defining a data dimension named Location with levels for State and City can be used to create the following table:</span></span>  
  
|<span data-ttu-id="f28e0-284">製品</span><span class="sxs-lookup"><span data-stu-id="f28e0-284">Product</span></span>|<span data-ttu-id="f28e0-285">Los Angeles</span><span class="sxs-lookup"><span data-stu-id="f28e0-285">Los Angeles</span></span>|<span data-ttu-id="f28e0-286">San Francisco</span><span class="sxs-lookup"><span data-stu-id="f28e0-286">San Francisco</span></span>|<span data-ttu-id="f28e0-287">Seattle</span><span class="sxs-lookup"><span data-stu-id="f28e0-287">Seattle</span></span>|  
|-------------|-----------------|-------------------|-------------|  
|<span data-ttu-id="f28e0-288">テニス ラケット</span><span class="sxs-lookup"><span data-stu-id="f28e0-288">Tennis racquets</span></span>|<span data-ttu-id="f28e0-289">50</span><span class="sxs-lookup"><span data-stu-id="f28e0-289">50</span></span>|<span data-ttu-id="f28e0-290">20</span><span class="sxs-lookup"><span data-stu-id="f28e0-290">20</span></span>|<span data-ttu-id="f28e0-291">30</span><span class="sxs-lookup"><span data-stu-id="f28e0-291">30</span></span>|  
|<span data-ttu-id="f28e0-292">サッカー ボール</span><span class="sxs-lookup"><span data-stu-id="f28e0-292">Soccer balls</span></span>|<span data-ttu-id="f28e0-293">130</span><span class="sxs-lookup"><span data-stu-id="f28e0-293">130</span></span>|<span data-ttu-id="f28e0-294">50</span><span class="sxs-lookup"><span data-stu-id="f28e0-294">50</span></span>|<span data-ttu-id="f28e0-295">20</span><span class="sxs-lookup"><span data-stu-id="f28e0-295">20</span></span>|  
  
 <span data-ttu-id="f28e0-296">この表で、Product ディメンションは、行として使用され、場所ディメンションは列として使用されました。</span><span class="sxs-lookup"><span data-stu-id="f28e0-296">In this table, the Product dimension was used as the rows, and the Location dimension was used as the columns.</span></span>  
  
## <a name="time-dimension"></a><span data-ttu-id="f28e0-297">時間ディメンション</span><span class="sxs-lookup"><span data-stu-id="f28e0-297">Time dimension</span></span>  
 <span data-ttu-id="f28e0-298">時間を基準として集計を作成する時間ディメンションを作成します。</span><span class="sxs-lookup"><span data-stu-id="f28e0-298">You create a time dimension to create aggregations with respect to time.</span></span> <span data-ttu-id="f28e0-299">たとえば、次の表を作成する時間ディメンションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="f28e0-299">For example, a time dimension can be used to create the following table:</span></span>  
  
|<span data-ttu-id="f28e0-300">年</span><span class="sxs-lookup"><span data-stu-id="f28e0-300">Year</span></span>|<span data-ttu-id="f28e0-301">Month</span><span class="sxs-lookup"><span data-stu-id="f28e0-301">Month</span></span>|<span data-ttu-id="f28e0-302">Count</span><span class="sxs-lookup"><span data-stu-id="f28e0-302">Count</span></span>|  
|----------|-----------|-----------|  
|<span data-ttu-id="f28e0-303">2003</span><span class="sxs-lookup"><span data-stu-id="f28e0-303">2003</span></span>|<span data-ttu-id="f28e0-304">January</span><span class="sxs-lookup"><span data-stu-id="f28e0-304">January</span></span>|<span data-ttu-id="f28e0-305">120</span><span class="sxs-lookup"><span data-stu-id="f28e0-305">120</span></span>|  
||<span data-ttu-id="f28e0-306">February</span><span class="sxs-lookup"><span data-stu-id="f28e0-306">February</span></span>|<span data-ttu-id="f28e0-307">230</span><span class="sxs-lookup"><span data-stu-id="f28e0-307">230</span></span>|  
||<span data-ttu-id="f28e0-308">March</span><span class="sxs-lookup"><span data-stu-id="f28e0-308">March</span></span>|<span data-ttu-id="f28e0-309">350</span><span class="sxs-lookup"><span data-stu-id="f28e0-309">350</span></span>|  
||<span data-ttu-id="f28e0-310">April</span><span class="sxs-lookup"><span data-stu-id="f28e0-310">April</span></span>|<span data-ttu-id="f28e0-311">280</span><span class="sxs-lookup"><span data-stu-id="f28e0-311">280</span></span>|  
  
 <span data-ttu-id="f28e0-312">その他の任意の次元を持つ時間ディメンションを組み合わせることができます。</span><span class="sxs-lookup"><span data-stu-id="f28e0-312">You can combine the time dimension with any other dimension.</span></span> <span data-ttu-id="f28e0-313">たとえば、次の表を作成するのに行と列のデータ ディメンションで時間ディメンションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="f28e0-313">For example, you can use the time dimension on rows and the data dimension on columns to create the following table:</span></span>  
  
|<span data-ttu-id="f28e0-314">Month</span><span class="sxs-lookup"><span data-stu-id="f28e0-314">Month</span></span>|<span data-ttu-id="f28e0-315">テニス ラケット</span><span class="sxs-lookup"><span data-stu-id="f28e0-315">Tennis racquets</span></span>|<span data-ttu-id="f28e0-316">サッカー ボール</span><span class="sxs-lookup"><span data-stu-id="f28e0-316">Soccer balls</span></span>|  
|-----------|---------------------|------------------|  
|<span data-ttu-id="f28e0-317">January</span><span class="sxs-lookup"><span data-stu-id="f28e0-317">January</span></span>|<span data-ttu-id="f28e0-318">50</span><span class="sxs-lookup"><span data-stu-id="f28e0-318">50</span></span>|<span data-ttu-id="f28e0-319">70</span><span class="sxs-lookup"><span data-stu-id="f28e0-319">70</span></span>|  
|<span data-ttu-id="f28e0-320">February</span><span class="sxs-lookup"><span data-stu-id="f28e0-320">February</span></span>|<span data-ttu-id="f28e0-321">120</span><span class="sxs-lookup"><span data-stu-id="f28e0-321">120</span></span>|<span data-ttu-id="f28e0-322">110</span><span class="sxs-lookup"><span data-stu-id="f28e0-322">110</span></span>|  
|<span data-ttu-id="f28e0-323">March</span><span class="sxs-lookup"><span data-stu-id="f28e0-323">March</span></span>|<span data-ttu-id="f28e0-324">300</span><span class="sxs-lookup"><span data-stu-id="f28e0-324">300</span></span>|<span data-ttu-id="f28e0-325">50</span><span class="sxs-lookup"><span data-stu-id="f28e0-325">50</span></span>|  
|<span data-ttu-id="f28e0-326">April</span><span class="sxs-lookup"><span data-stu-id="f28e0-326">April</span></span>|<span data-ttu-id="f28e0-327">220</span><span class="sxs-lookup"><span data-stu-id="f28e0-327">220</span></span>|<span data-ttu-id="f28e0-328">60</span><span class="sxs-lookup"><span data-stu-id="f28e0-328">60</span></span>|  
  
## <a name="numeric-range-dimension"></a><span data-ttu-id="f28e0-329">数値範囲ディメンション</span><span class="sxs-lookup"><span data-stu-id="f28e0-329">Numeric range dimension</span></span>  
 <span data-ttu-id="f28e0-330">数値範囲ディメンションを使用して、数値の範囲のフレンドリ名で分類する集計を作成します。</span><span class="sxs-lookup"><span data-stu-id="f28e0-330">You use numeric range dimensions to create aggregations that categorize ranges of numbers by friendly names.</span></span> <span data-ttu-id="f28e0-331">たとえば、ビジネス アナリストは、PO サイズを次の範囲という数値範囲ディメンションを定義できます。</span><span class="sxs-lookup"><span data-stu-id="f28e0-331">For example, a business analyst can define a numeric range dimension named PO Size with the following ranges:</span></span>  
  
 <span data-ttu-id="f28e0-332">0 ~ 100 ドルの注文の小</span><span class="sxs-lookup"><span data-stu-id="f28e0-332">Small, for purchase orders between 0 and $100</span></span>  
  
 <span data-ttu-id="f28e0-333">100 ドルと 1,000 ドルの注文書の中</span><span class="sxs-lookup"><span data-stu-id="f28e0-333">Medium, for purchase orders between $100 and $1,000</span></span>  
  
 <span data-ttu-id="f28e0-334">注文が 1,000 ドル超えている大規模です。</span><span class="sxs-lookup"><span data-stu-id="f28e0-334">Large, for purchase orders exceeding $1,000</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f28e0-335">注文の合計が定義した範囲にない場合は、たとえば、注文の合計が 0 より小さいし、「範囲外」行が範囲外のデータに合わせて BAM により自動的に作成します。</span><span class="sxs-lookup"><span data-stu-id="f28e0-335">If a purchase order amount is not in the defined ranges, for example, a purchase order amount is less than 0, then an "Out of range" row will be automatically created by BAM to accommodate the out-of-range data.</span></span>  
  
|<span data-ttu-id="f28e0-336">PO サイズ</span><span class="sxs-lookup"><span data-stu-id="f28e0-336">PO Size</span></span>|<span data-ttu-id="f28e0-337">Count</span><span class="sxs-lookup"><span data-stu-id="f28e0-337">Count</span></span>|  
|-------------|-----------|  
|<span data-ttu-id="f28e0-338">小さな</span><span class="sxs-lookup"><span data-stu-id="f28e0-338">Small</span></span>|<span data-ttu-id="f28e0-339">500</span><span class="sxs-lookup"><span data-stu-id="f28e0-339">500</span></span>|  
|<span data-ttu-id="f28e0-340">Medium</span><span class="sxs-lookup"><span data-stu-id="f28e0-340">Medium</span></span>|<span data-ttu-id="f28e0-341">350</span><span class="sxs-lookup"><span data-stu-id="f28e0-341">350</span></span>|  
|<span data-ttu-id="f28e0-342">大規模です</span><span class="sxs-lookup"><span data-stu-id="f28e0-342">Large</span></span>|<span data-ttu-id="f28e0-343">225</span><span class="sxs-lookup"><span data-stu-id="f28e0-343">225</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="f28e0-344">同じデータ エイリアスを参照する 2 つの数値範囲ディメンションを作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="f28e0-344">You cannot create two numeric range dimensions that reference the same data alias.</span></span>