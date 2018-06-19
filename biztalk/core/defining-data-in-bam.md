---
title: BAM でデータを定義する |Microsoft ドキュメント
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
ms.openlocfilehash: e6acbc0ea1d80ec129d691d6c54b6eefd626d0e9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22242938"
---
# <a name="defining-data-in-bam"></a><span data-ttu-id="db7db-102">BAM でのデータの定義</span><span class="sxs-lookup"><span data-stu-id="db7db-102">Defining Data in BAM</span></span>
<span data-ttu-id="db7db-103">BAM Excel アドインを使用すると、BAM で収集するデータの種類と、収集したデータを共有する方法を定義できます。</span><span class="sxs-lookup"><span data-stu-id="db7db-103">You use the BAM Excel Add-in to define the data you want BAM to collect, and define the way in which the data will be shared.</span></span> <span data-ttu-id="db7db-104">データを定義するには BAM アクティビティを使用します。他のユーザーが参照できるデータを定義するには BAM ビューを使用します。</span><span class="sxs-lookup"><span data-stu-id="db7db-104">You use BAM activities to define the data, and you use BAM views to define the data that other users can see.</span></span>  
  
## <a name="activities"></a><span data-ttu-id="db7db-105">アクティビティ</span><span class="sxs-lookup"><span data-stu-id="db7db-105">Activities</span></span>  
 <span data-ttu-id="db7db-106">BAM アクティビティを作成すると、BAM で監視するビジネス プロセスに関する情報を定義できます。</span><span class="sxs-lookup"><span data-stu-id="db7db-106">You create a BAM activity to define information about a business process that you want to monitor with BAM.</span></span> <span data-ttu-id="db7db-107">BAM アクティビティは、注文書の処理や製品の出荷などの特定のビジネス プロセスを表します。</span><span class="sxs-lookup"><span data-stu-id="db7db-107">A BAM activity represents a specific business process in the business, such as handling purchase orders or shipping a product.</span></span> <span data-ttu-id="db7db-108">ビジネス プロセスには、マイルストーンとビジネス データの定義済みのセットが含まれます。</span><span class="sxs-lookup"><span data-stu-id="db7db-108">A business process has a defined set of milestones and business data.</span></span> <span data-ttu-id="db7db-109">たとえば、発注プロセスには、承認済み、拒否、配信済みなどのマイルストーンと、顧客名や製品などのビジネス データを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="db7db-109">For example, a purchase order process might have milestones such as Approved, Denied, and Delivered along with business data like Customer Name and Product.</span></span>  
  
 <span data-ttu-id="db7db-110">BAM アクティビティの目的は、プロセスに関する履歴 (マイルストーン) とデータをインフォメーション ワーカーに提示することです。</span><span class="sxs-lookup"><span data-stu-id="db7db-110">The intention of a BAM activity is to show the history (milestones) and data about a process to information workers.</span></span> <span data-ttu-id="db7db-111">BAM アクティビティは、BizTalk Server の実際の実装から独立した高度な抽象概念です。</span><span class="sxs-lookup"><span data-stu-id="db7db-111">BAM activities are high-level abstractions that are independent of the actual implementation of BizTalk Server.</span></span> <span data-ttu-id="db7db-112">BAM の概念の概要については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプのトピック「ビジネス アクティビティ監視」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="db7db-112">For a conceptual overview of BAM, see the topic "Business Activity Monitoring" in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help.</span></span>  
  
 <span data-ttu-id="db7db-113">BAM アクティビティ ウィザードを使用すると、少なくとも 1 つのアクティビティ項目を含む BAM アクティビティを定義できます。</span><span class="sxs-lookup"><span data-stu-id="db7db-113">You use the BAM Activity Wizard to define BAM activities that contain at least one activity item.</span></span> <span data-ttu-id="db7db-114">アクティビティ内の関連するアクティビティ項目はグループ化できます。また、アクティビティ項目を使用して、ビジネス プロセスで使用できるデータの種類を示すことができます。</span><span class="sxs-lookup"><span data-stu-id="db7db-114">You group related activity items in an activity, and you use activity items to describe the type of data you want to make available from a business process.</span></span>  
  
 <span data-ttu-id="db7db-115">BAM で使用できるアクティビティ項目の種類を次の表で説明します。</span><span class="sxs-lookup"><span data-stu-id="db7db-115">The following table describes the types of activity items BAM provides.</span></span>  
  
|<span data-ttu-id="db7db-116">アイテムの種類</span><span class="sxs-lookup"><span data-stu-id="db7db-116">Item type</span></span>|<span data-ttu-id="db7db-117">Description</span><span class="sxs-lookup"><span data-stu-id="db7db-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="db7db-118">ビジネス マイルス トーン</span><span class="sxs-lookup"><span data-stu-id="db7db-118">Business Milestone</span></span>|<span data-ttu-id="db7db-119">日付/時刻値。</span><span class="sxs-lookup"><span data-stu-id="db7db-119">A date/time value.</span></span> <span data-ttu-id="db7db-120">たとえば、注文書が承認された日付です。</span><span class="sxs-lookup"><span data-stu-id="db7db-120">For example, an approval date for a purchase order.</span></span>|  
|<span data-ttu-id="db7db-121">ビジネス データ - Text</span><span class="sxs-lookup"><span data-stu-id="db7db-121">Business Data - Text</span></span>|<span data-ttu-id="db7db-122">任意の英数字の文字列。</span><span class="sxs-lookup"><span data-stu-id="db7db-122">A string containing any alphanumeric characters.</span></span> <span data-ttu-id="db7db-123">たとえば、出荷先 : 市区町村、都道府県、郵便番号です。</span><span class="sxs-lookup"><span data-stu-id="db7db-123">For example, Ship to: City, State/Province and Zip/Postal code.</span></span>|  
|<span data-ttu-id="db7db-124">ビジネス データ - Integer</span><span class="sxs-lookup"><span data-stu-id="db7db-124">Business Data - Integer</span></span>|<span data-ttu-id="db7db-125">整数値です。</span><span class="sxs-lookup"><span data-stu-id="db7db-125">A whole number value.</span></span> <span data-ttu-id="db7db-126">たとえば、注文の合計数です。</span><span class="sxs-lookup"><span data-stu-id="db7db-126">For example, the total number of purchases.</span></span>|  
|<span data-ttu-id="db7db-127">ビジネス データ - 浮動小数点します。</span><span class="sxs-lookup"><span data-stu-id="db7db-127">Business Data - Float</span></span>|<span data-ttu-id="db7db-128">decimal 値です。</span><span class="sxs-lookup"><span data-stu-id="db7db-128">A decimal value.</span></span> <span data-ttu-id="db7db-129">たとえば、PO の合計金額です。</span><span class="sxs-lookup"><span data-stu-id="db7db-129">For example the total dollar amount of the PO.</span></span>|  
  
 <span data-ttu-id="db7db-130">たとえば、発注アクティビティでは、次の表に示すようなアクティビティ項目を作成できます。</span><span class="sxs-lookup"><span data-stu-id="db7db-130">For example, in a purchase order activity, you might create the activity items in the following table.</span></span>  
  
|<span data-ttu-id="db7db-131">アクティビティ項目</span><span class="sxs-lookup"><span data-stu-id="db7db-131">Activity item</span></span>|<span data-ttu-id="db7db-132">アイテムの種類</span><span class="sxs-lookup"><span data-stu-id="db7db-132">Item type</span></span>|  
|-------------------|---------------|  
|<span data-ttu-id="db7db-133">Product</span><span class="sxs-lookup"><span data-stu-id="db7db-133">Product</span></span>|<span data-ttu-id="db7db-134">ビジネス データ-テキスト</span><span class="sxs-lookup"><span data-stu-id="db7db-134">Business Data — Text</span></span>|  
|<span data-ttu-id="db7db-135">City</span><span class="sxs-lookup"><span data-stu-id="db7db-135">City</span></span>|<span data-ttu-id="db7db-136">ビジネス データ-テキスト</span><span class="sxs-lookup"><span data-stu-id="db7db-136">Business Data — Text</span></span>|  
|<span data-ttu-id="db7db-137">状態</span><span class="sxs-lookup"><span data-stu-id="db7db-137">State</span></span>|<span data-ttu-id="db7db-138">ビジネス データ-テキスト</span><span class="sxs-lookup"><span data-stu-id="db7db-138">Business Data — Text</span></span>|  
|<span data-ttu-id="db7db-139">Amount</span><span class="sxs-lookup"><span data-stu-id="db7db-139">Amount</span></span>|<span data-ttu-id="db7db-140">ビジネス データ - Float</span><span class="sxs-lookup"><span data-stu-id="db7db-140">Business Data — Float</span></span>|  
|<span data-ttu-id="db7db-141">Quantity</span><span class="sxs-lookup"><span data-stu-id="db7db-141">Quantity</span></span>|<span data-ttu-id="db7db-142">ビジネス データ-整数</span><span class="sxs-lookup"><span data-stu-id="db7db-142">Business Data — Integer</span></span>|  
|<span data-ttu-id="db7db-143">承認</span><span class="sxs-lookup"><span data-stu-id="db7db-143">Approved</span></span>|<span data-ttu-id="db7db-144">ビジネス マイルス トーン</span><span class="sxs-lookup"><span data-stu-id="db7db-144">Business Milestone</span></span>|  
|<span data-ttu-id="db7db-145">Delivered</span><span class="sxs-lookup"><span data-stu-id="db7db-145">Delivered</span></span>|<span data-ttu-id="db7db-146">ビジネス マイルス トーン</span><span class="sxs-lookup"><span data-stu-id="db7db-146">Business Milestone</span></span>|  
|<span data-ttu-id="db7db-147">拒否</span><span class="sxs-lookup"><span data-stu-id="db7db-147">Denied</span></span>|<span data-ttu-id="db7db-148">ビジネス マイルス トーン</span><span class="sxs-lookup"><span data-stu-id="db7db-148">Business Milestone</span></span>|  
|<span data-ttu-id="db7db-149">受信しました。</span><span class="sxs-lookup"><span data-stu-id="db7db-149">Received</span></span>|<span data-ttu-id="db7db-150">ビジネス マイルス トーン</span><span class="sxs-lookup"><span data-stu-id="db7db-150">Business Milestone</span></span>|  
  
 <span data-ttu-id="db7db-151">金額は小数値の可能性があるため、浮動小数点を指定しています。</span><span class="sxs-lookup"><span data-stu-id="db7db-151">Note that Amount is a float because it may be a decimal value.</span></span> <span data-ttu-id="db7db-152">数量は、この例では常に整数値なので、整数を指定しています。</span><span class="sxs-lookup"><span data-stu-id="db7db-152">Quantity is an integer because it will always be a whole number in this example.</span></span> <span data-ttu-id="db7db-153">承認、配送、拒否、受信はすべて、発注プロセスのマイルストーンです。</span><span class="sxs-lookup"><span data-stu-id="db7db-153">Approved, Delivered, Denied, and Received are all milestones in the purchase order process.</span></span>  
  
## <a name="views"></a><span data-ttu-id="db7db-154">ビュー</span><span class="sxs-lookup"><span data-stu-id="db7db-154">Views</span></span>  
 <span data-ttu-id="db7db-155">ビューを作成すると、アクティビティのデータをユーザーに公開できます。</span><span class="sxs-lookup"><span data-stu-id="db7db-155">You create views to expose data from an activity to users.</span></span> <span data-ttu-id="db7db-156">発注アクティビティに基づいてビューを作成するときに、アクティビティ項目に含めるデータを定義します。</span><span class="sxs-lookup"><span data-stu-id="db7db-156">When you create a view based on the purchase order activity, you define the data behind the activity items.</span></span> <span data-ttu-id="db7db-157">BAM のビュー データは、ディメンション、メジャー、期間、マイルストーン グループ、進捗ディメンションとして定義します。</span><span class="sxs-lookup"><span data-stu-id="db7db-157">You define view data in BAM as dimensions, measures, durations, milestone groups, and progress dimensions.</span></span>  
  
 <span data-ttu-id="db7db-158">ビューには 1 つ以上のビュー項目が含まれます。</span><span class="sxs-lookup"><span data-stu-id="db7db-158">A view contains one or more view items.</span></span> <span data-ttu-id="db7db-159">次の種類のビュー項目を作成できます。</span><span class="sxs-lookup"><span data-stu-id="db7db-159">You can create the following types of view items:</span></span>  
  
-   <span data-ttu-id="db7db-160">期間</span><span class="sxs-lookup"><span data-stu-id="db7db-160">Durations</span></span>  
  
-   <span data-ttu-id="db7db-161">マイルストーン グループ</span><span class="sxs-lookup"><span data-stu-id="db7db-161">Milestone groups</span></span>  
  
-   <span data-ttu-id="db7db-162">集計</span><span class="sxs-lookup"><span data-stu-id="db7db-162">Aggregations</span></span>  
  
### <a name="durations"></a><span data-ttu-id="db7db-163">期間</span><span class="sxs-lookup"><span data-stu-id="db7db-163">Durations</span></span>  
 <span data-ttu-id="db7db-164">期間は時間間隔です。</span><span class="sxs-lookup"><span data-stu-id="db7db-164">Durations are time intervals.</span></span> <span data-ttu-id="db7db-165">期間は、時間間隔の開始と終了を定義するマイルストーンで表されます。</span><span class="sxs-lookup"><span data-stu-id="db7db-165">Durations are described in terms of the milestones that define the start and end of time intervals.</span></span> <span data-ttu-id="db7db-166">上の表に示されているマイルストーンで作成できる期間を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="db7db-166">The following table shows the durations you can make from the milestones listed in the previous table.</span></span>  
  
|<span data-ttu-id="db7db-167">Duration</span><span class="sxs-lookup"><span data-stu-id="db7db-167">Duration</span></span>|<span data-ttu-id="db7db-168">開始マイルストーン</span><span class="sxs-lookup"><span data-stu-id="db7db-168">Start milestone</span></span>|<span data-ttu-id="db7db-169">終了マイルストーン</span><span class="sxs-lookup"><span data-stu-id="db7db-169">End milestone</span></span>|  
|--------------|---------------------|-------------------|  
|<span data-ttu-id="db7db-170">1</span><span class="sxs-lookup"><span data-stu-id="db7db-170">1</span></span>|<span data-ttu-id="db7db-171">受信しました。</span><span class="sxs-lookup"><span data-stu-id="db7db-171">Received</span></span>|<span data-ttu-id="db7db-172">承認</span><span class="sxs-lookup"><span data-stu-id="db7db-172">Approved</span></span>|  
|<span data-ttu-id="db7db-173">2</span><span class="sxs-lookup"><span data-stu-id="db7db-173">2</span></span>|<span data-ttu-id="db7db-174">受信しました。</span><span class="sxs-lookup"><span data-stu-id="db7db-174">Received</span></span>|<span data-ttu-id="db7db-175">Delivered</span><span class="sxs-lookup"><span data-stu-id="db7db-175">Delivered</span></span>|  
|<span data-ttu-id="db7db-176">3</span><span class="sxs-lookup"><span data-stu-id="db7db-176">3</span></span>|<span data-ttu-id="db7db-177">受信しました。</span><span class="sxs-lookup"><span data-stu-id="db7db-177">Received</span></span>|<span data-ttu-id="db7db-178">拒否</span><span class="sxs-lookup"><span data-stu-id="db7db-178">Denied</span></span>|  
|<span data-ttu-id="db7db-179">4</span><span class="sxs-lookup"><span data-stu-id="db7db-179">4</span></span>|<span data-ttu-id="db7db-180">承認</span><span class="sxs-lookup"><span data-stu-id="db7db-180">Approved</span></span>|<span data-ttu-id="db7db-181">Delivered</span><span class="sxs-lookup"><span data-stu-id="db7db-181">Delivered</span></span>|  
  
 <span data-ttu-id="db7db-182">この表で、最初の期間 (期間 1) は、注文書が BizTalk Server で受信されたときに始まり、承認されたときに終了する時間間隔です。</span><span class="sxs-lookup"><span data-stu-id="db7db-182">In this table, you can see that the first duration (Duration 1) is the time interval that starts when a purchase order is received by BizTalk Server, and ends when the purchase order is approved.</span></span>  
  
### <a name="milestone-groups"></a><span data-ttu-id="db7db-183">マイルストーン グループ</span><span class="sxs-lookup"><span data-stu-id="db7db-183">Milestone groups</span></span>  
 <span data-ttu-id="db7db-184">マイルストーン グループを作成すると、複数のマイルストーンを 1 つのエンティティとして使用できます。たとえば、1 つのプロセスの開始マイルストーンと終了マイルストーンをまとめて、プロセスの期間全体を表す 1 つのマイルストーンを作成できます。</span><span class="sxs-lookup"><span data-stu-id="db7db-184">You create milestone groups to treat a set of milestones as a single entity, for example, the beginning and ending milestones for a process, which creates a single milestone to represent the entire length of the process.</span></span>  
  
### <a name="aggregations"></a><span data-ttu-id="db7db-185">集計</span><span class="sxs-lookup"><span data-stu-id="db7db-185">Aggregations</span></span>  
 <span data-ttu-id="db7db-186">集計を使用すると、データベースからデータを更新するときの応答時間を改善できます。</span><span class="sxs-lookup"><span data-stu-id="db7db-186">You use aggregations to improve the response time for refreshing data from the database.</span></span> <span data-ttu-id="db7db-187">Excel では、集計を事前計算された要約データとして定義し、質問の答えをあらかじめ用意しておくことで、クエリの応答時間を短縮します。</span><span class="sxs-lookup"><span data-stu-id="db7db-187">Excel defines aggregations as pre-calculated summaries of data that improve query response time by having the answers ready before the questions are asked.</span></span> <span data-ttu-id="db7db-188">たとえば、数十万行が格納されているデータ ウェアハウスのファクト テーブルに対して、特定の 2 つの製品の出荷スケジュールを要求するクエリがあるとします。この計算でファクト テーブルをスキャンする必要があると、応答に時間がかかります。</span><span class="sxs-lookup"><span data-stu-id="db7db-188">For example, when a data warehouse fact table contains hundreds of thousands of rows, a query requesting the shipping schedules for two particular products can take a long time to answer if the fact table has to be scanned to compute the answer.</span></span> <span data-ttu-id="db7db-189">ただし、このクエリの回答となる集計データがあらかじめ計算されていれば、即座に応答できます。</span><span class="sxs-lookup"><span data-stu-id="db7db-189">However, the response can be almost immediate if the summarization data to answer this query has been pre-calculated.</span></span>  
  
 <span data-ttu-id="db7db-190">次に、事前に計算された集計データの例を示します。</span><span class="sxs-lookup"><span data-stu-id="db7db-190">The following figure displays an example of pre-calculated aggregation data.</span></span>  
  
 ![](../core/media/bam-olap-cube.gif "bam_olap_cube")  
  
 <span data-ttu-id="db7db-191">この図では、2 か月間に特定の場所への出荷された各製品数の概要を示しています。</span><span class="sxs-lookup"><span data-stu-id="db7db-191">The figure summarizes the numbers of each product shipped to specific locations over a two-month time period.</span></span> <span data-ttu-id="db7db-192">通常、Excel では、このデータをメジャーとして定義し、</span><span class="sxs-lookup"><span data-stu-id="db7db-192">Excel typically defines this data as measure.</span></span> <span data-ttu-id="db7db-193">フィルター選択または分類に使用するデータをディメンションとして定義します。</span><span class="sxs-lookup"><span data-stu-id="db7db-193">The data used for filtering and categorization, Excel defines as dimension.</span></span>  
  
 <span data-ttu-id="db7db-194">BAM ブックでは 2 種類の集計を定義できます。</span><span class="sxs-lookup"><span data-stu-id="db7db-194">You can define two types of aggregations in the BAM workbook:</span></span>  
  
-   <span data-ttu-id="db7db-195">リアルタイム集計</span><span class="sxs-lookup"><span data-stu-id="db7db-195">Real-time aggregations</span></span>  
  
-   <span data-ttu-id="db7db-196">スケジュール済みの集計</span><span class="sxs-lookup"><span data-stu-id="db7db-196">Scheduled aggregations</span></span>  
  
### <a name="real-time-aggregations"></a><span data-ttu-id="db7db-197">リアルタイム集計</span><span class="sxs-lookup"><span data-stu-id="db7db-197">Real-time aggregations</span></span>  
 <span data-ttu-id="db7db-198">リアルタイム集計 (RTA) を使用すると、ビジネス プロセスの現在の状態を確認でき、プロセスのボトルネックを簡単に特定できます。</span><span class="sxs-lookup"><span data-stu-id="db7db-198">Real-time aggregations (RTA) allow you to see the current state of the business process and to easily identify process bottlenecks.</span></span>  
  
 <span data-ttu-id="db7db-199">BAM データはピボットテーブル内に表示されます。</span><span class="sxs-lookup"><span data-stu-id="db7db-199">BAM data is displayed in a pivot table.</span></span> <span data-ttu-id="db7db-200">BAM ピボットテーブルは RTA またはスケジュール済みの集計として定義できます。</span><span class="sxs-lookup"><span data-stu-id="db7db-200">You can define a BAM pivot table as an RTA or a scheduled aggregation.</span></span> <span data-ttu-id="db7db-201">RTA を使用すると、たとえば特定の PO が出荷処理中であるなど、データの現時点のビューを表示できます。</span><span class="sxs-lookup"><span data-stu-id="db7db-201">An RTA gives you an up-to-the-minute view of your data, for example, where a particular PO is in the shipping process.</span></span> <span data-ttu-id="db7db-202">1 日のうちいつでも画面を更新して、データのビューを最新の状態にできます。</span><span class="sxs-lookup"><span data-stu-id="db7db-202">You can refresh your screen to update the view of the data throughout the day.</span></span>  
  
 <span data-ttu-id="db7db-203">多次元集計の特定のスライスでは、時間が重要な要素になる場合があります。このような場合には、スライスをリアルタイムで使用することが必要になります。</span><span class="sxs-lookup"><span data-stu-id="db7db-203">In some cases, specific slices of the multidimensional aggregations are so time-sensitive that you want them to be available in real time.</span></span> <span data-ttu-id="db7db-204">たとえば、生鮮食料品を販売する業者では、配送の各段階での製品数量の集計をリアルタイムで利用できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="db7db-204">For example, your business is selling perishable products and you want the aggregation of product quantity in different stages of delivery to be available in real time.</span></span> <span data-ttu-id="db7db-205">同時に、代表的な顧客の年齢などの他の集計を、ビジネス インテリジェンス分析のために月末にのみ実行する必要がある場合もあります。</span><span class="sxs-lookup"><span data-stu-id="db7db-205">At the same time, you want other aggregations such as the age of your typical customers, but only at the end of the month for business intelligence analysis.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="db7db-206">同じ BAM アクティビティを使用する RTA を複数定義しないでください。</span><span class="sxs-lookup"><span data-stu-id="db7db-206">Do not define multiple RTAs that use the same BAM activity.</span></span> <span data-ttu-id="db7db-207">そのような RTA を複数定義した場合、BAM データをアーカイブしたときに RTA データが不正確になります。</span><span class="sxs-lookup"><span data-stu-id="db7db-207">If you do so, the RTA data will be incorrect when you archive the BAM data.</span></span>  
  
 <span data-ttu-id="db7db-208">多次元データの参照については、Excel のヘルプでピボットテーブルに関するトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="db7db-208">For information about browsing multidimensional data, see the PivotTable topic in Excel Help.</span></span>  
  
### <a name="scheduled-aggregations"></a><span data-ttu-id="db7db-209">スケジュール済みの集計</span><span class="sxs-lookup"><span data-stu-id="db7db-209">Scheduled aggregations</span></span>  
 <span data-ttu-id="db7db-210">既定では、すべての BAM 集計はスケジュール済みの集計です。</span><span class="sxs-lookup"><span data-stu-id="db7db-210">All BAM aggregations are scheduled aggregations by default.</span></span> <span data-ttu-id="db7db-211">スケジュール済みの集計は、今朝の出荷の概要など、指定した期間のビジネス データのスナップショットを表します。</span><span class="sxs-lookup"><span data-stu-id="db7db-211">A scheduled aggregation represents a snapshot of the business at a specific time, for example, a summary of this morning's shipments.</span></span> <span data-ttu-id="db7db-212">集計が処理される時期については、データベース管理者に問い合わせてください。集計が処理されると、履歴データを見ることができます。</span><span class="sxs-lookup"><span data-stu-id="db7db-212">Ask your database administrator when your aggregations are processed, and then you can look at the historical data.</span></span>  
  
### <a name="dimensions-and-measures"></a><span data-ttu-id="db7db-213">ディメンションとメジャー</span><span class="sxs-lookup"><span data-stu-id="db7db-213">Dimensions and Measures</span></span>  
 <span data-ttu-id="db7db-214">ディメンションとメジャーを使用すると、データの集計を作成できます。</span><span class="sxs-lookup"><span data-stu-id="db7db-214">You use dimensions and measures to create data aggregations:</span></span>  
  
-   <span data-ttu-id="db7db-215">ディメンションはファクトの説明です。</span><span class="sxs-lookup"><span data-stu-id="db7db-215">Dimensions describe a fact.</span></span>  
  
-   <span data-ttu-id="db7db-216">メジャーはファクトの値です。</span><span class="sxs-lookup"><span data-stu-id="db7db-216">Measures are fact values.</span></span>  
  
 <span data-ttu-id="db7db-217">たとえばファクトは、在庫にある "3 台の赤い自動車" などになります。</span><span class="sxs-lookup"><span data-stu-id="db7db-217">For example, a fact could be “3 red cars” in inventory.</span></span> <span data-ttu-id="db7db-218">製品の説明:"car"と「赤い」はディメンションです。</span><span class="sxs-lookup"><span data-stu-id="db7db-218">The description of the product: "car" and "red" are dimensions.</span></span> <span data-ttu-id="db7db-219">ファクトの値である "3" はメジャーです。</span><span class="sxs-lookup"><span data-stu-id="db7db-219">The value of the fact "3" is a measure.</span></span> <span data-ttu-id="db7db-220">自動車の価格がファクトに含まれている場合、自動車の価格はディメンションですが、在庫にある自動車の平均価格はメジャーです。</span><span class="sxs-lookup"><span data-stu-id="db7db-220">If the price of each car is included in the fact, the car price is a dimension, but the average price of cars in inventory is a measure.</span></span> <span data-ttu-id="db7db-221">Microsoft SQL Server Books Online では、メジャーを "集計および分析された代表値" と表現しています。</span><span class="sxs-lookup"><span data-stu-id="db7db-221">Microsoft SQL Server Books Online describes a measure as "the central values that are aggregated and analyzed."</span></span> <span data-ttu-id="db7db-222">言い換えれば、数える、平均する、または数学的な関数を適用することで得られるものはメジャーです。</span><span class="sxs-lookup"><span data-stu-id="db7db-222">In other words, if you can count it, average it, or otherwise perform mathematical functions to get it, it is a measure.</span></span>  
  
 <span data-ttu-id="db7db-223">次の種類のディメンションを作成できます。</span><span class="sxs-lookup"><span data-stu-id="db7db-223">You can create the following types of dimensions:</span></span>  
  
-   <span data-ttu-id="db7db-224">進捗ディメンション</span><span class="sxs-lookup"><span data-stu-id="db7db-224">Progress dimension</span></span>  
  
-   <span data-ttu-id="db7db-225">データ ディメンション</span><span class="sxs-lookup"><span data-stu-id="db7db-225">Data dimension</span></span>  
  
-   <span data-ttu-id="db7db-226">時間ディメンション</span><span class="sxs-lookup"><span data-stu-id="db7db-226">Time dimension</span></span>  
  
-   <span data-ttu-id="db7db-227">数値範囲ディメンション</span><span class="sxs-lookup"><span data-stu-id="db7db-227">Numeric range dimension</span></span>  
  
## <a name="progress-dimensions"></a><span data-ttu-id="db7db-228">進捗ディメンション</span><span class="sxs-lookup"><span data-stu-id="db7db-228">Progress dimensions</span></span>  
 <span data-ttu-id="db7db-229">BAM には新しい種類のディメンション: 進捗ディメンションです。</span><span class="sxs-lookup"><span data-stu-id="db7db-229">BAM introduces a new type of dimension: the progress dimension.</span></span> <span data-ttu-id="db7db-230">進捗ディメンションを作成すると、処理中のアクティビティの進捗状況に関する集計を作成できます。</span><span class="sxs-lookup"><span data-stu-id="db7db-230">You create progress dimensions to create aggregations that relate to the progress of activities still in process.</span></span>  
  
 <span data-ttu-id="db7db-231">たとえば、1,000 件の注文を受信する発注ビジネス プロセスがあるとします。</span><span class="sxs-lookup"><span data-stu-id="db7db-231">For example, consider a purchasing business process where you receive 1,000 purchase orders.</span></span> <span data-ttu-id="db7db-232">行に進捗ディメンションを使用すると、次のテーブルを作成できます。</span><span class="sxs-lookup"><span data-stu-id="db7db-232">You can use the progress dimension on rows to create the following table.</span></span>  
  
|<span data-ttu-id="db7db-233">OrderProgress_Level1</span><span class="sxs-lookup"><span data-stu-id="db7db-233">OrderProgress_Level1</span></span>|<span data-ttu-id="db7db-234">Count</span><span class="sxs-lookup"><span data-stu-id="db7db-234">Count</span></span>|  
|---------------------------|-----------|  
|<span data-ttu-id="db7db-235">受信しました。</span><span class="sxs-lookup"><span data-stu-id="db7db-235">Received</span></span>|<span data-ttu-id="db7db-236">1000</span><span class="sxs-lookup"><span data-stu-id="db7db-236">1000</span></span>|  
  
 <span data-ttu-id="db7db-237">受信プロセスを開くと、アクティビティの進捗に関するより詳細な情報を表示できます。以下にその例を示します。</span><span class="sxs-lookup"><span data-stu-id="db7db-237">You can then open the Received process to view further details about the progress of the activities, such as:</span></span>  
  
|||<span data-ttu-id="db7db-238">Count</span><span class="sxs-lookup"><span data-stu-id="db7db-238">Count</span></span>|  
|------|------|-----------|  
|<span data-ttu-id="db7db-239">受信しました。</span><span class="sxs-lookup"><span data-stu-id="db7db-239">Received</span></span>|<span data-ttu-id="db7db-240">評価中</span><span class="sxs-lookup"><span data-stu-id="db7db-240">Evaluating</span></span>|<span data-ttu-id="db7db-241">300</span><span class="sxs-lookup"><span data-stu-id="db7db-241">300</span></span>|  
||<span data-ttu-id="db7db-242">承認</span><span class="sxs-lookup"><span data-stu-id="db7db-242">Approved</span></span>|<span data-ttu-id="db7db-243">500</span><span class="sxs-lookup"><span data-stu-id="db7db-243">500</span></span>|  
||<span data-ttu-id="db7db-244">拒否</span><span class="sxs-lookup"><span data-stu-id="db7db-244">Denied</span></span>|<span data-ttu-id="db7db-245">200</span><span class="sxs-lookup"><span data-stu-id="db7db-245">200</span></span>|  
  
 <span data-ttu-id="db7db-246">このテーブルは、受信した 1,000 件の注文のうち 500 件が承認され、200 件が拒否され、300 件が評価中であることを表しています。</span><span class="sxs-lookup"><span data-stu-id="db7db-246">This means that from the 1000 purchase orders you received, 500 were approved, 200 were denied, and 300 are currently being evaluated.</span></span>  
  
 <span data-ttu-id="db7db-247">受信、承認、拒否はマイルストーンを表します。</span><span class="sxs-lookup"><span data-stu-id="db7db-247">Received, Approved, and Denied represent milestones.</span></span> <span data-ttu-id="db7db-248">"数" 列の対応する数字は、これらのマイルストーンを通過した注文の数を表しています。</span><span class="sxs-lookup"><span data-stu-id="db7db-248">The corresponding numbers in the Count column show how many orders have passed through these milestones.</span></span> <span data-ttu-id="db7db-249">"評価中" は、注文が "受信" マイルストーンから "承認" マイルストーンまたは "拒否" マイルストーンの間で通過する段階です。</span><span class="sxs-lookup"><span data-stu-id="db7db-249">Evaluating is a stage that the orders pass through between the Received and Approved or Denied milestones.</span></span>  
  
 <span data-ttu-id="db7db-250">進捗ディメンションは他の任意のディメンションと組み合わせて使用できます。</span><span class="sxs-lookup"><span data-stu-id="db7db-250">You can use progress dimensions in combination with any other dimensions.</span></span> <span data-ttu-id="db7db-251">たとえば、行に進捗ディメンションである "発注進捗" を使用して、列にデータ ディメンションである "製品" を使用すると、次の結果が得られます。</span><span class="sxs-lookup"><span data-stu-id="db7db-251">For example, by using the progress dimension Order Progress on rows and the data dimension Product on columns, the following results occur:</span></span>  
  
|||<span data-ttu-id="db7db-252">テニス ラケット</span><span class="sxs-lookup"><span data-stu-id="db7db-252">Tennis Racquets</span></span>|<span data-ttu-id="db7db-253">サッカー ボール</span><span class="sxs-lookup"><span data-stu-id="db7db-253">Soccer Balls</span></span>|  
|------|------|---------------------|------------------|  
|<span data-ttu-id="db7db-254">受信しました。</span><span class="sxs-lookup"><span data-stu-id="db7db-254">Received</span></span>|<span data-ttu-id="db7db-255">評価中</span><span class="sxs-lookup"><span data-stu-id="db7db-255">Evaluating</span></span>|<span data-ttu-id="db7db-256">250</span><span class="sxs-lookup"><span data-stu-id="db7db-256">250</span></span>|<span data-ttu-id="db7db-257">50</span><span class="sxs-lookup"><span data-stu-id="db7db-257">50</span></span>|  
||<span data-ttu-id="db7db-258">承認</span><span class="sxs-lookup"><span data-stu-id="db7db-258">Approved</span></span>|<span data-ttu-id="db7db-259">200</span><span class="sxs-lookup"><span data-stu-id="db7db-259">200</span></span>|<span data-ttu-id="db7db-260">300</span><span class="sxs-lookup"><span data-stu-id="db7db-260">300</span></span>|  
||<span data-ttu-id="db7db-261">拒否</span><span class="sxs-lookup"><span data-stu-id="db7db-261">Denied</span></span>|<span data-ttu-id="db7db-262">150</span><span class="sxs-lookup"><span data-stu-id="db7db-262">150</span></span>|<span data-ttu-id="db7db-263">50</span><span class="sxs-lookup"><span data-stu-id="db7db-263">50</span></span>|  
  
 <span data-ttu-id="db7db-264">進捗ディメンションでは、リアルタイム集計 (RTA) に基づくグラフに特に有用な情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="db7db-264">Progress dimensions provide especially useful information for charts based on real-time aggregations (RTA).</span></span> <span data-ttu-id="db7db-265">RTA を使用すると、ビジネス プロセスの現在の状態を確認でき、プロセスのボトルネックを簡単に特定できます。</span><span class="sxs-lookup"><span data-stu-id="db7db-265">RTAs allow you to see the current state of the business process and to easily identify process bottlenecks.</span></span>  
  
 <span data-ttu-id="db7db-266">購入のマイルス トーンが進捗ディメンションをシーケンシャルにすることができますを注文: 次の手順を開始する前に、最初の手順を完了します。</span><span class="sxs-lookup"><span data-stu-id="db7db-266">The milestones in a purchase order progress dimension can be sequential: the first step is completed before the next step is started.</span></span> <span data-ttu-id="db7db-267">また、マイルストーンは平行して完了することもあります。</span><span class="sxs-lookup"><span data-stu-id="db7db-267">Or milestones can be completed in tandem.</span></span> <span data-ttu-id="db7db-268">段階的なステップは子ステップで、平行ステップは兄弟ステップです。</span><span class="sxs-lookup"><span data-stu-id="db7db-268">Sequential steps are child steps, and tandem steps are sibling steps.</span></span> <span data-ttu-id="db7db-269">発注書の処理では、検証は、発注書を受信するとすぐを開始します。</span><span class="sxs-lookup"><span data-stu-id="db7db-269">In the purchase order process, verification begins as soon as the purchase order is received.</span></span> <span data-ttu-id="db7db-270">確認ステップは、"受信" マイルストーンと同時に発生する一時的なステップであるため、"受信" マイルストーンと兄弟になります。</span><span class="sxs-lookup"><span data-stu-id="db7db-270">It is a transitory step that occurs at the same time as the received milestone, and is therefore a sibling to the receive milestone.</span></span> <span data-ttu-id="db7db-271">注文は、注文書の受信後にのみ承認されます。つまり、"承認" マイルストーンは "受信" マイルストーンの子になります。</span><span class="sxs-lookup"><span data-stu-id="db7db-271">A purchase order is approved only after it is received — approved is a child of received.</span></span>  
  
## <a name="data-dimension"></a><span data-ttu-id="db7db-272">データ ディメンション</span><span class="sxs-lookup"><span data-stu-id="db7db-272">Data dimension</span></span>  
 <span data-ttu-id="db7db-273">データ ディメンションを定義すると、BAM アクティビティ内の複数のテキスト項目の値を行または列で使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="db7db-273">You define a data dimension to use the value of some text items in the BAM activity on rows or columns.</span></span> <span data-ttu-id="db7db-274">たとえば、次の表を作成する製品の名前のデータ ディメンションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="db7db-274">For example, a data dimension named Product can be used to create the following table:</span></span>  
  
|<span data-ttu-id="db7db-275">Product</span><span class="sxs-lookup"><span data-stu-id="db7db-275">Product</span></span>|<span data-ttu-id="db7db-276">Count</span><span class="sxs-lookup"><span data-stu-id="db7db-276">Count</span></span>|  
|-------------|-----------|  
|<span data-ttu-id="db7db-277">テニス ラケット</span><span class="sxs-lookup"><span data-stu-id="db7db-277">Tennis racquets</span></span>|<span data-ttu-id="db7db-278">100</span><span class="sxs-lookup"><span data-stu-id="db7db-278">100</span></span>|  
|<span data-ttu-id="db7db-279">サッカー ボール</span><span class="sxs-lookup"><span data-stu-id="db7db-279">Soccer balls</span></span>|<span data-ttu-id="db7db-280">200</span><span class="sxs-lookup"><span data-stu-id="db7db-280">200</span></span>|  
  
 <span data-ttu-id="db7db-281">また、BAM ビュー ウィザードで、1 つ以上のデータ ディメンションを定義できます。</span><span class="sxs-lookup"><span data-stu-id="db7db-281">Also, you can define more than one data dimension in the BAM View Wizard.</span></span> <span data-ttu-id="db7db-282">たとえば、州や市の各レベルが含まれる場所の名前のデータ ディメンションを定義して、次のテーブルを作成できます。</span><span class="sxs-lookup"><span data-stu-id="db7db-282">For example, defining a data dimension named Location with levels for State and City can be used to create the following table:</span></span>  
  
|<span data-ttu-id="db7db-283">Product</span><span class="sxs-lookup"><span data-stu-id="db7db-283">Product</span></span>|<span data-ttu-id="db7db-284">Los Angeles</span><span class="sxs-lookup"><span data-stu-id="db7db-284">Los Angeles</span></span>|<span data-ttu-id="db7db-285">San Francisco</span><span class="sxs-lookup"><span data-stu-id="db7db-285">San Francisco</span></span>|<span data-ttu-id="db7db-286">Seattle</span><span class="sxs-lookup"><span data-stu-id="db7db-286">Seattle</span></span>|  
|-------------|-----------------|-------------------|-------------|  
|<span data-ttu-id="db7db-287">テニス ラケット</span><span class="sxs-lookup"><span data-stu-id="db7db-287">Tennis racquets</span></span>|<span data-ttu-id="db7db-288">50</span><span class="sxs-lookup"><span data-stu-id="db7db-288">50</span></span>|<span data-ttu-id="db7db-289">20</span><span class="sxs-lookup"><span data-stu-id="db7db-289">20</span></span>|<span data-ttu-id="db7db-290">30</span><span class="sxs-lookup"><span data-stu-id="db7db-290">30</span></span>|  
|<span data-ttu-id="db7db-291">サッカー ボール</span><span class="sxs-lookup"><span data-stu-id="db7db-291">Soccer balls</span></span>|<span data-ttu-id="db7db-292">130</span><span class="sxs-lookup"><span data-stu-id="db7db-292">130</span></span>|<span data-ttu-id="db7db-293">50</span><span class="sxs-lookup"><span data-stu-id="db7db-293">50</span></span>|<span data-ttu-id="db7db-294">20</span><span class="sxs-lookup"><span data-stu-id="db7db-294">20</span></span>|  
  
 <span data-ttu-id="db7db-295">このテーブルでは、製品ディメンションは行として使用され、場所ディメンションは列として使用されています。</span><span class="sxs-lookup"><span data-stu-id="db7db-295">In this table, the Product dimension was used as the rows, and the Location dimension was used as the columns.</span></span>  
  
## <a name="time-dimension"></a><span data-ttu-id="db7db-296">時間ディメンション</span><span class="sxs-lookup"><span data-stu-id="db7db-296">Time dimension</span></span>  
 <span data-ttu-id="db7db-297">時間ディメンションを作成すると、時間に関連する集計を作成できます。</span><span class="sxs-lookup"><span data-stu-id="db7db-297">You create a time dimension to create aggregations with respect to time.</span></span> <span data-ttu-id="db7db-298">たとえば、次の表を作成する、時間ディメンションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="db7db-298">For example, a time dimension can be used to create the following table:</span></span>  
  
|<span data-ttu-id="db7db-299">年</span><span class="sxs-lookup"><span data-stu-id="db7db-299">Year</span></span>|<span data-ttu-id="db7db-300">Month</span><span class="sxs-lookup"><span data-stu-id="db7db-300">Month</span></span>|<span data-ttu-id="db7db-301">Count</span><span class="sxs-lookup"><span data-stu-id="db7db-301">Count</span></span>|  
|----------|-----------|-----------|  
|<span data-ttu-id="db7db-302">2003</span><span class="sxs-lookup"><span data-stu-id="db7db-302">2003</span></span>|<span data-ttu-id="db7db-303">January</span><span class="sxs-lookup"><span data-stu-id="db7db-303">January</span></span>|<span data-ttu-id="db7db-304">120</span><span class="sxs-lookup"><span data-stu-id="db7db-304">120</span></span>|  
||<span data-ttu-id="db7db-305">February</span><span class="sxs-lookup"><span data-stu-id="db7db-305">February</span></span>|<span data-ttu-id="db7db-306">230</span><span class="sxs-lookup"><span data-stu-id="db7db-306">230</span></span>|  
||<span data-ttu-id="db7db-307">March</span><span class="sxs-lookup"><span data-stu-id="db7db-307">March</span></span>|<span data-ttu-id="db7db-308">350</span><span class="sxs-lookup"><span data-stu-id="db7db-308">350</span></span>|  
||<span data-ttu-id="db7db-309">April</span><span class="sxs-lookup"><span data-stu-id="db7db-309">April</span></span>|<span data-ttu-id="db7db-310">280</span><span class="sxs-lookup"><span data-stu-id="db7db-310">280</span></span>|  
  
 <span data-ttu-id="db7db-311">時間ディメンションは他の任意のディメンションと組み合わせて使用できます。</span><span class="sxs-lookup"><span data-stu-id="db7db-311">You can combine the time dimension with any other dimension.</span></span> <span data-ttu-id="db7db-312">たとえば、行に時間ディメンションを使用し、列にデータ ディメンションを使用して、次のテーブルを作成できます。</span><span class="sxs-lookup"><span data-stu-id="db7db-312">For example, you can use the time dimension on rows and the data dimension on columns to create the following table:</span></span>  
  
|<span data-ttu-id="db7db-313">Month</span><span class="sxs-lookup"><span data-stu-id="db7db-313">Month</span></span>|<span data-ttu-id="db7db-314">テニス ラケット</span><span class="sxs-lookup"><span data-stu-id="db7db-314">Tennis racquets</span></span>|<span data-ttu-id="db7db-315">サッカー ボール</span><span class="sxs-lookup"><span data-stu-id="db7db-315">Soccer balls</span></span>|  
|-----------|---------------------|------------------|  
|<span data-ttu-id="db7db-316">January</span><span class="sxs-lookup"><span data-stu-id="db7db-316">January</span></span>|<span data-ttu-id="db7db-317">50</span><span class="sxs-lookup"><span data-stu-id="db7db-317">50</span></span>|<span data-ttu-id="db7db-318">70</span><span class="sxs-lookup"><span data-stu-id="db7db-318">70</span></span>|  
|<span data-ttu-id="db7db-319">February</span><span class="sxs-lookup"><span data-stu-id="db7db-319">February</span></span>|<span data-ttu-id="db7db-320">120</span><span class="sxs-lookup"><span data-stu-id="db7db-320">120</span></span>|<span data-ttu-id="db7db-321">110</span><span class="sxs-lookup"><span data-stu-id="db7db-321">110</span></span>|  
|<span data-ttu-id="db7db-322">March</span><span class="sxs-lookup"><span data-stu-id="db7db-322">March</span></span>|<span data-ttu-id="db7db-323">300</span><span class="sxs-lookup"><span data-stu-id="db7db-323">300</span></span>|<span data-ttu-id="db7db-324">50</span><span class="sxs-lookup"><span data-stu-id="db7db-324">50</span></span>|  
|<span data-ttu-id="db7db-325">April</span><span class="sxs-lookup"><span data-stu-id="db7db-325">April</span></span>|<span data-ttu-id="db7db-326">220</span><span class="sxs-lookup"><span data-stu-id="db7db-326">220</span></span>|<span data-ttu-id="db7db-327">60</span><span class="sxs-lookup"><span data-stu-id="db7db-327">60</span></span>|  
  
## <a name="numeric-range-dimension"></a><span data-ttu-id="db7db-328">数値範囲ディメンション</span><span class="sxs-lookup"><span data-stu-id="db7db-328">Numeric range dimension</span></span>  
 <span data-ttu-id="db7db-329">数値範囲ディメンションを使用すると、フレンドリ名で数値範囲を分類した集計を作成できます。</span><span class="sxs-lookup"><span data-stu-id="db7db-329">You use numeric range dimensions to create aggregations that categorize ranges of numbers by friendly names.</span></span> <span data-ttu-id="db7db-330">たとえば、ビジネス アナリストは、次の範囲を設定した "PO サイズ" という名前の数値範囲ディメンションを作成できます。</span><span class="sxs-lookup"><span data-stu-id="db7db-330">For example, a business analyst can define a numeric range dimension named PO Size with the following ranges:</span></span>  
  
 <span data-ttu-id="db7db-331">小 (0 ～ 100 ドルの注文)</span><span class="sxs-lookup"><span data-stu-id="db7db-331">Small, for purchase orders between 0 and $100</span></span>  
  
 <span data-ttu-id="db7db-332">中 (100 ドルを超え、1,000 ドル以下の注文)</span><span class="sxs-lookup"><span data-stu-id="db7db-332">Medium, for purchase orders between $100 and $1,000</span></span>  
  
 <span data-ttu-id="db7db-333">大 (1,000 ドルを超える注文)</span><span class="sxs-lookup"><span data-stu-id="db7db-333">Large, for purchase orders exceeding $1,000</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="db7db-334">注文の合計が 0 より小さいなど、定義した範囲内にない場合は、範囲外のデータを格納する "範囲外" という行が BAM により自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="db7db-334">If a purchase order amount is not in the defined ranges, for example, a purchase order amount is less than 0, then an "Out of range" row will be automatically created by BAM to accommodate the out-of-range data.</span></span>  
  
|<span data-ttu-id="db7db-335">PO サイズ</span><span class="sxs-lookup"><span data-stu-id="db7db-335">PO Size</span></span>|<span data-ttu-id="db7db-336">Count</span><span class="sxs-lookup"><span data-stu-id="db7db-336">Count</span></span>|  
|-------------|-----------|  
|<span data-ttu-id="db7db-337">小</span><span class="sxs-lookup"><span data-stu-id="db7db-337">Small</span></span>|<span data-ttu-id="db7db-338">500</span><span class="sxs-lookup"><span data-stu-id="db7db-338">500</span></span>|  
|<span data-ttu-id="db7db-339">Medium</span><span class="sxs-lookup"><span data-stu-id="db7db-339">Medium</span></span>|<span data-ttu-id="db7db-340">350</span><span class="sxs-lookup"><span data-stu-id="db7db-340">350</span></span>|  
|<span data-ttu-id="db7db-341">大</span><span class="sxs-lookup"><span data-stu-id="db7db-341">Large</span></span>|<span data-ttu-id="db7db-342">225</span><span class="sxs-lookup"><span data-stu-id="db7db-342">225</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="db7db-343">同じデータ エイリアスを参照する複数の数値範囲ディメンションは作成できません。</span><span class="sxs-lookup"><span data-stu-id="db7db-343">You cannot create two numeric range dimensions that reference the same data alias.</span></span>