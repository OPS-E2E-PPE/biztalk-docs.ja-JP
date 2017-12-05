---
title: "BAM ポータルでのアクティビティの検索 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- activities [BAM], searching
- queries [BAM], field descriptions
- Query Builder [BAM portal], creating queries
- queries [BAM], activity searches
- Query Builder [BAM portal], about Query Builder
- Query Builder [BAM portal], activity searches
- Query Builder [BAM portal]
- Query Builder [BAM portal], field descriptions
- BAM portal, Query Builder
- BAM portal, activity searches
ms.assetid: 60ab8deb-ebe2-4959-97fd-261ff64d500c
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 723848f61294cc710bd2292758383cf674093265
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="activity-searches-in-the-bam-portal"></a><span data-ttu-id="f1953-102">BAM ポータルでのアクティビティの検索</span><span class="sxs-lookup"><span data-stu-id="f1953-102">Activity Searches in the BAM Portal</span></span>
<span data-ttu-id="f1953-103">アクティビティの検索では、BAM データが検索され、追跡する値および BAM ビューで使用可能な項目に基づいて指定した条件に一致するアクティビティを見つけることができます。また、アクティビティを編集したり、アクティビティに基づいて警告を作成できるように、アクティビティを表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="f1953-103">An activity search allows you to perform searches against BAM data to find activities that match the criteria you specify based on tracked values and items available in a BAM view, and to display these activities so that you can edit them or create alerts based on them.</span></span>  
  
## <a name="parts-of-the-query-builder"></a><span data-ttu-id="f1953-104">クエリ ビルダーでの操作</span><span class="sxs-lookup"><span data-stu-id="f1953-104">Parts of the Query Builder</span></span>  
 <span data-ttu-id="f1953-105">アクティビティを検索するためのクエリを作成するには、ビジネス データの項目を選択します。これらの項目は、必要なデータを取得するために、ブール値の比較演算の対象として使用されます。</span><span class="sxs-lookup"><span data-stu-id="f1953-105">You build queries for your activity search by selecting items of business data against which you will create Boolean comparisons to extract data of interest.</span></span> <span data-ttu-id="f1953-106">BAM ビューを選択して、起動する、**マイ ビュー**ポータルのフレームです。</span><span class="sxs-lookup"><span data-stu-id="f1953-106">You start by selecting a BAM view from the **My Views** frame of the portal.</span></span> <span data-ttu-id="f1953-107">選択したビューから、作成するクエリの対象となるアクティビティを選択します。</span><span class="sxs-lookup"><span data-stu-id="f1953-107">From the selected view you select an activity on which to build the query.</span></span>  
  
 <span data-ttu-id="f1953-108">![](../core/media/bamportalviewschooser.gif "BAMPortalViewsChooser")</span><span class="sxs-lookup"><span data-stu-id="f1953-108">![](../core/media/bamportalviewschooser.gif "BAMPortalViewsChooser")</span></span>  
  
 <span data-ttu-id="f1953-109">アクティビティを選択すると、ポータルのコンテンツ フレームには、[クエリ]、[列の選択]、および [結果] ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f1953-109">When you have selected the activity, the content frame of the portal displays the Query builder, Column Chooser, and Results boxes.</span></span> <span data-ttu-id="f1953-110">既存のクエリを開くか、新しいクエリを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="f1953-110">You can open an existing query or you can build a new one.</span></span>  
  
 <span data-ttu-id="f1953-111">![](../core/media/activitysearchquerybuilder.gif "ActivitySearchQueryBuilder")</span><span class="sxs-lookup"><span data-stu-id="f1953-111">![](../core/media/activitysearchquerybuilder.gif "ActivitySearchQueryBuilder")</span></span>  
  
 <span data-ttu-id="f1953-112">ビジネス データ項目を選択して開始する新しいクエリを構築する、**ビジネス データ**ドロップダウン リスト。</span><span class="sxs-lookup"><span data-stu-id="f1953-112">To build a new query you start by selecting a business data item from the **Business Data** drop-down list.</span></span>  
  
 <span data-ttu-id="f1953-113">![](../core/media/activitysearchquerybuilderbusinessdatadropdown.gif "ActivitySearchQueryBuilderBusinessDataDropdown")</span><span class="sxs-lookup"><span data-stu-id="f1953-113">![](../core/media/activitysearchquerybuilderbusinessdatadropdown.gif "ActivitySearchQueryBuilderBusinessDataDropdown")</span></span>  
  
 <span data-ttu-id="f1953-114">次に、[演算子] ボックスの一覧で比較演算子を選択します。</span><span class="sxs-lookup"><span data-stu-id="f1953-114">Next, you select your comparison operator in the Operator drop-down list.</span></span> <span data-ttu-id="f1953-115">比較演算子を使用すると、クエリの結果を絞り込むことができます。</span><span class="sxs-lookup"><span data-stu-id="f1953-115">The comparison operator allows you to refine the results of the query.</span></span>  
  
 <span data-ttu-id="f1953-116">![](../core/media/activitysearchcomparisonoperatordropdown.gif "ActivitySearchComparisonOperatorDropDown")</span><span class="sxs-lookup"><span data-stu-id="f1953-116">![](../core/media/activitysearchcomparisonoperatordropdown.gif "ActivitySearchComparisonOperatorDropDown")</span></span>  
  
 <span data-ttu-id="f1953-117">[値] ボックスの一覧は、ビジネス データ項目が表すデータの種類に基づき、状況に応じて変化します。</span><span class="sxs-lookup"><span data-stu-id="f1953-117">The Value drop-down list is context-sensitive based on the type of data represented by the business data item.</span></span> <span data-ttu-id="f1953-118">ユーザー インターフェイス (UI) は、許可されたデータ変更の種類によって変わります。</span><span class="sxs-lookup"><span data-stu-id="f1953-118">The user interface (UI) changes as the type of permitted data changes.</span></span>  
  
 <span data-ttu-id="f1953-119">使用してクエリの句を結合してまたは OR 演算子をクリックしてより複雑なクエリを作成する、**追加**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="f1953-119">You can join clauses of the query with AND or OR operators to form more complex queries by clicking the **Add** button.</span></span>  
  
 <span data-ttu-id="f1953-120">![](../core/media/activitysearchjoiningclauses.gif "ActivitySearchJoiningClauses")</span><span class="sxs-lookup"><span data-stu-id="f1953-120">![](../core/media/activitysearchjoiningclauses.gif "ActivitySearchJoiningClauses")</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f1953-121">句をグループ化することはできません。</span><span class="sxs-lookup"><span data-stu-id="f1953-121">You cannot group clauses.</span></span> <span data-ttu-id="f1953-122">クエリは、個別の句を AND 演算子または OR 演算子で結合した単純な文字列です。</span><span class="sxs-lookup"><span data-stu-id="f1953-122">A query is a simple string of individual clauses joined by AND/OR operators.</span></span>  
  
 <span data-ttu-id="f1953-123">次の表では、日付と時刻のフィールドについて説明します。</span><span class="sxs-lookup"><span data-stu-id="f1953-123">The following table describes the date and time fields.</span></span>  
  
|<span data-ttu-id="f1953-124">演算子</span><span class="sxs-lookup"><span data-stu-id="f1953-124">Operator</span></span>|<span data-ttu-id="f1953-125">Description</span><span class="sxs-lookup"><span data-stu-id="f1953-125">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="f1953-126">**At**</span><span class="sxs-lookup"><span data-stu-id="f1953-126">**At**</span></span>|<span data-ttu-id="f1953-127">完全一致を指定します。</span><span class="sxs-lookup"><span data-stu-id="f1953-127">Specifies an exact match.</span></span> <span data-ttu-id="f1953-128">ブール値の "=" (等号) 演算子と同じです。</span><span class="sxs-lookup"><span data-stu-id="f1953-128">Equivalent to a Boolean Equals (=) operation.</span></span> <span data-ttu-id="f1953-129">**注:**を選択した場合、**で**演算子し、ポータルは、既定値として午前 0 時を使用して時刻部分と日付を指定します。</span><span class="sxs-lookup"><span data-stu-id="f1953-129">**Note:**  If you select the **At** operator and specify a date with no time part the portal uses midnight as the default value.</span></span> <span data-ttu-id="f1953-130">ユーザーの意図でない場合場合を使用して、**以前**または**以降の**オペレーターは、目的の結果を取得します。</span><span class="sxs-lookup"><span data-stu-id="f1953-130">If this is not your intent, use the **At or before** or the **At or after** operators to obtain the desired results.</span></span>|  
|<span data-ttu-id="f1953-131">**以前**</span><span class="sxs-lookup"><span data-stu-id="f1953-131">**On or before**</span></span>|<span data-ttu-id="f1953-132">指定した日付以前のトランザクションのみが一致するように指定します。</span><span class="sxs-lookup"><span data-stu-id="f1953-132">Specifies that only transactions on or before the specified date are matched.</span></span> <span data-ttu-id="f1953-133">ブール値の "≤" (以下) 演算子と同じです。</span><span class="sxs-lookup"><span data-stu-id="f1953-133">Equivalent to a Boolean less than or equals (≤) operation.</span></span>|  
|<span data-ttu-id="f1953-134">**以降**</span><span class="sxs-lookup"><span data-stu-id="f1953-134">**On or after**</span></span>|<span data-ttu-id="f1953-135">指定した日付以降のトランザクションのみが一致するように指定します。</span><span class="sxs-lookup"><span data-stu-id="f1953-135">Specifies that only transactions on or after the specified date are matched.</span></span> <span data-ttu-id="f1953-136">ブール値の "≥" (以上) 演算子と同じです。</span><span class="sxs-lookup"><span data-stu-id="f1953-136">Equivalent to a Boolean greater than or equals (≥) operation.</span></span>|  
|<span data-ttu-id="f1953-137">**[指定日付より前]**</span><span class="sxs-lookup"><span data-stu-id="f1953-137">**Before**</span></span>|<span data-ttu-id="f1953-138">指定した日付より前のトランザクションのみが一致するように指定します。</span><span class="sxs-lookup"><span data-stu-id="f1953-138">Specifies that only transactions before the specified date are matched.</span></span> <span data-ttu-id="f1953-139">ブール値の "<" (より小さい) 演算子と同じです。</span><span class="sxs-lookup"><span data-stu-id="f1953-139">Equivalent to a Boolean less than (<) operation.</span></span>|  
|<span data-ttu-id="f1953-140">**After**</span><span class="sxs-lookup"><span data-stu-id="f1953-140">**After**</span></span>|<span data-ttu-id="f1953-141">指定した日付より後のトランザクションのみが一致するように指定します。</span><span class="sxs-lookup"><span data-stu-id="f1953-141">Specifies that only transactions after the specified date are matched.</span></span> <span data-ttu-id="f1953-142">ブール値より大きい (>) 操作に相当します。</span><span class="sxs-lookup"><span data-stu-id="f1953-142">Equivalent to a Boolean greater than (>) operation.</span></span>|  
|<span data-ttu-id="f1953-143">**最後に**</span><span class="sxs-lookup"><span data-stu-id="f1953-143">**In the last**</span></span>|<span data-ttu-id="f1953-144">指定した過去の期間に発生したトランザクションのみが一致するように指定します。</span><span class="sxs-lookup"><span data-stu-id="f1953-144">Specifies that only transactions that occurred in the previous specified time period are matched.</span></span> <span data-ttu-id="f1953-145">期間は、秒、分、時間、または日数で指定できます。</span><span class="sxs-lookup"><span data-stu-id="f1953-145">The time period can be specified in seconds, minutes, hours, or days.</span></span>|  
|<span data-ttu-id="f1953-146">**最後の前に**</span><span class="sxs-lookup"><span data-stu-id="f1953-146">**Before the last**</span></span>|<span data-ttu-id="f1953-147">指定した期間より前に発生したトランザクションのみが一致するように指定します。</span><span class="sxs-lookup"><span data-stu-id="f1953-147">Specifies that only transactions that occurred prior to the specified time period are matched.</span></span> <span data-ttu-id="f1953-148">期間は、秒、分、時間、または日数で指定できます。</span><span class="sxs-lookup"><span data-stu-id="f1953-148">The time period can be specified in seconds, minutes, hours, or days.</span></span>|  
|<span data-ttu-id="f1953-149">**空です。**</span><span class="sxs-lookup"><span data-stu-id="f1953-149">**Is empty**</span></span>|<span data-ttu-id="f1953-150">ビジネス データ項目にデータが含まれていない (データ フィールドの値が NULL の) トランザクションのみが返されるように指定します。</span><span class="sxs-lookup"><span data-stu-id="f1953-150">Specifies that only transactions for which the business data item contains no data (the value of data field is NULL) are returned.</span></span>|  
|<span data-ttu-id="f1953-151">**空でないです。**</span><span class="sxs-lookup"><span data-stu-id="f1953-151">**Is not empty**</span></span>|<span data-ttu-id="f1953-152">ビジネス データ項目にデータが含まれている (データ フィールドの値が NULL ではない) トランザクションのみが返されるように指定します。</span><span class="sxs-lookup"><span data-stu-id="f1953-152">Specifies that only transactions for which the business data item contains data (the value of data field is not NULL) are returned.</span></span>|  
  
 <span data-ttu-id="f1953-153">次の表では、数値フィールドおよび期間フィールドについて説明します。</span><span class="sxs-lookup"><span data-stu-id="f1953-153">The following table describes the numeric fields and the duration fields.</span></span> <span data-ttu-id="f1953-154">数値フィールドには、数量や金額などのデータが含まれます。</span><span class="sxs-lookup"><span data-stu-id="f1953-154">Numeric fields contain data such as quantities or currency amounts.</span></span> <span data-ttu-id="f1953-155">期間フィールドでは、期間を指定します。</span><span class="sxs-lookup"><span data-stu-id="f1953-155">Duration fields specify a time period.</span></span>  
  
|<span data-ttu-id="f1953-156">演算子</span><span class="sxs-lookup"><span data-stu-id="f1953-156">Operator</span></span>|<span data-ttu-id="f1953-157">Description</span><span class="sxs-lookup"><span data-stu-id="f1953-157">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="f1953-158">**[等しい]**</span><span class="sxs-lookup"><span data-stu-id="f1953-158">**Equals**</span></span>|<span data-ttu-id="f1953-159">完全一致を指定します。</span><span class="sxs-lookup"><span data-stu-id="f1953-159">Specifies an exact match.</span></span> <span data-ttu-id="f1953-160">ブール値の "=" (等号) 演算子と同じです。</span><span class="sxs-lookup"><span data-stu-id="f1953-160">Equivalent to a Boolean Equals (=) operation.</span></span>|  
|<span data-ttu-id="f1953-161">**より大きい**</span><span class="sxs-lookup"><span data-stu-id="f1953-161">**Greater than**</span></span>|<span data-ttu-id="f1953-162">完全一致を指定します。</span><span class="sxs-lookup"><span data-stu-id="f1953-162">Specifies an exact match.</span></span> <span data-ttu-id="f1953-163">ブール値の ">" (より大きい) 演算子と同じです。</span><span class="sxs-lookup"><span data-stu-id="f1953-163">Equivalent to a Boolean Greater Than (>) operation.</span></span>|  
|<span data-ttu-id="f1953-164">**[次の値以上]**</span><span class="sxs-lookup"><span data-stu-id="f1953-164">**Greater than or equal**</span></span>|<span data-ttu-id="f1953-165">完全一致を指定します。</span><span class="sxs-lookup"><span data-stu-id="f1953-165">Specifies an exact match.</span></span> <span data-ttu-id="f1953-166">ブール型の値より大きいまたは等しい (≥) 操作に相当します。</span><span class="sxs-lookup"><span data-stu-id="f1953-166">Equivalent to a Boolean Greater Than or Equals (≥) operation.</span></span>|  
|<span data-ttu-id="f1953-167">**より小さい**</span><span class="sxs-lookup"><span data-stu-id="f1953-167">**Less than**</span></span>|<span data-ttu-id="f1953-168">完全一致を指定します。</span><span class="sxs-lookup"><span data-stu-id="f1953-168">Specifies an exact match.</span></span> <span data-ttu-id="f1953-169">ブール値より小さい (<) 操作に相当します。</span><span class="sxs-lookup"><span data-stu-id="f1953-169">Equivalent to a Boolean Less Than (<) operation.</span></span>|  
|<span data-ttu-id="f1953-170">**[次の値以下]**</span><span class="sxs-lookup"><span data-stu-id="f1953-170">**Less than or equal**</span></span>|<span data-ttu-id="f1953-171">完全一致を指定します。</span><span class="sxs-lookup"><span data-stu-id="f1953-171">Specifies an exact match.</span></span> <span data-ttu-id="f1953-172">"≤" (以下) 演算子と同じです。</span><span class="sxs-lookup"><span data-stu-id="f1953-172">Equivalent to a Less Than or Equals (≤) operation.</span></span>|  
|<span data-ttu-id="f1953-173">**等しくないです。**</span><span class="sxs-lookup"><span data-stu-id="f1953-173">**Not Equal**</span></span>|<span data-ttu-id="f1953-174">完全一致を指定します。</span><span class="sxs-lookup"><span data-stu-id="f1953-174">Specifies an exact match.</span></span> <span data-ttu-id="f1953-175">ブール値の "≠" (不等号) 演算子と同じです。</span><span class="sxs-lookup"><span data-stu-id="f1953-175">Equivalent to a Not Equals (≠) operation.</span></span>|  
|<span data-ttu-id="f1953-176">**空です。**</span><span class="sxs-lookup"><span data-stu-id="f1953-176">**Is empty**</span></span>|<span data-ttu-id="f1953-177">ビジネス データ項目にデータが含まれていない (データ フィールドの値が NULL の) トランザクションのみが返されるように指定します。</span><span class="sxs-lookup"><span data-stu-id="f1953-177">Specifies that only transactions for which the business data item contains no data (the value of data field is NULL) are returned.</span></span>|  
|<span data-ttu-id="f1953-178">**空でないです。**</span><span class="sxs-lookup"><span data-stu-id="f1953-178">**Is not empty**</span></span>|<span data-ttu-id="f1953-179">ビジネス データ項目にデータが含まれている (データ フィールドの値が NULL ではない) トランザクションのみが返されるように指定します。</span><span class="sxs-lookup"><span data-stu-id="f1953-179">Specifies that only transactions for which the business data item contains data (the value of data field is not NULL) are returned.</span></span>|  
  
 <span data-ttu-id="f1953-180">次の表では、テキスト フィールドについて説明します。</span><span class="sxs-lookup"><span data-stu-id="f1953-180">The following table describes the text fields.</span></span>  
  
|<span data-ttu-id="f1953-181">演算子</span><span class="sxs-lookup"><span data-stu-id="f1953-181">Operator</span></span>|<span data-ttu-id="f1953-182">Description</span><span class="sxs-lookup"><span data-stu-id="f1953-182">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="f1953-183">**正確には**</span><span class="sxs-lookup"><span data-stu-id="f1953-183">**Is Exactly**</span></span>|<span data-ttu-id="f1953-184">完全一致を指定します。</span><span class="sxs-lookup"><span data-stu-id="f1953-184">Specifies an exact match.</span></span> <span data-ttu-id="f1953-185">ブール値の "=" (等号) 演算子と同じです。</span><span class="sxs-lookup"><span data-stu-id="f1953-185">Equivalent to a Boolean Equals (=) operation.</span></span>|  
|<span data-ttu-id="f1953-186">**[値を含む]**</span><span class="sxs-lookup"><span data-stu-id="f1953-186">**Contains**</span></span>|<span data-ttu-id="f1953-187">指定した値がビジネス データ項目のテキストに含まれるように指定します。</span><span class="sxs-lookup"><span data-stu-id="f1953-187">Specifies that the text in the business data item contains the specified value.</span></span> <span data-ttu-id="f1953-188">これにより、データの部分的な一致を指定できます。</span><span class="sxs-lookup"><span data-stu-id="f1953-188">This allows you to do partial matches on the data.</span></span>|  
|<span data-ttu-id="f1953-189">**[次を含まない]**</span><span class="sxs-lookup"><span data-stu-id="f1953-189">**Does not contain**</span></span>|<span data-ttu-id="f1953-190">指定した値がビジネス データ項目のテキストに含まれないように指定します。</span><span class="sxs-lookup"><span data-stu-id="f1953-190">Specifies that the text in the business data item does not contain the specified value.</span></span>|  
|<span data-ttu-id="f1953-191">**空です。**</span><span class="sxs-lookup"><span data-stu-id="f1953-191">**Is empty**</span></span>|<span data-ttu-id="f1953-192">ビジネス データ項目にデータが含まれていない (データ フィールドの値が NULL の) トランザクションのみが返されるように指定します。</span><span class="sxs-lookup"><span data-stu-id="f1953-192">Specifies that only transactions for which the business data item contains no data (the value of data field is NULL) are returned.</span></span>|  
|<span data-ttu-id="f1953-193">**空でないです。**</span><span class="sxs-lookup"><span data-stu-id="f1953-193">**Is not empty**</span></span>|<span data-ttu-id="f1953-194">ビジネス データ項目にデータが含まれている (データ フィールドの値が NULL ではない) トランザクションのみが返されるように指定します。</span><span class="sxs-lookup"><span data-stu-id="f1953-194">Specifies that only transactions for which the business data item contains data (the value of data field is not NULL) are returned.</span></span>|  
  
## <a name="in-this-section"></a><span data-ttu-id="f1953-195">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="f1953-195">In This Section</span></span>  
  
-   [<span data-ttu-id="f1953-196">アクティビティの検索でクエリを作成する方法</span><span class="sxs-lookup"><span data-stu-id="f1953-196">How to Create a Query in Activity Search</span></span>](../core/how-to-create-a-query-in-activity-search.md)  
  
-   [<span data-ttu-id="f1953-197">警告を設定する方法</span><span class="sxs-lookup"><span data-stu-id="f1953-197">How to Set an Alert</span></span>](../core/how-to-set-an-alert.md)  
  
-   [<span data-ttu-id="f1953-198">アクティビティの検索の結果を表示する方法</span><span class="sxs-lookup"><span data-stu-id="f1953-198">How to View the Results of an Activity Search</span></span>](../core/how-to-view-the-results-of-an-activity-search.md)  
  
## <a name="see-also"></a><span data-ttu-id="f1953-199">参照</span><span class="sxs-lookup"><span data-stu-id="f1953-199">See Also</span></span>  
 [<span data-ttu-id="f1953-200">BAM ポータル</span><span class="sxs-lookup"><span data-stu-id="f1953-200">BAM Portal</span></span>](../core/bam-portal.md)