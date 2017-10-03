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
ms.openlocfilehash: 617461b104f3188c14bb7c5b6eb5eb0bd329693f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="activity-searches-in-the-bam-portal"></a><span data-ttu-id="f0d99-102">BAM ポータルでのアクティビティの検索</span><span class="sxs-lookup"><span data-stu-id="f0d99-102">Activity Searches in the BAM Portal</span></span>
<span data-ttu-id="f0d99-103">アクティビティの検索では、BAM データが検索され、追跡する値および BAM ビューで使用可能な項目に基づいて指定した条件に一致するアクティビティを見つけることができます。また、アクティビティを編集したり、アクティビティに基づいて警告を作成できるように、アクティビティを表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="f0d99-103">An activity search allows you to perform searches against BAM data to find activities that match the criteria you specify based on tracked values and items available in a BAM view, and to display these activities so that you can edit them or create alerts based on them.</span></span>  
  
## <a name="parts-of-the-query-builder"></a><span data-ttu-id="f0d99-104">クエリ ビルダーでの操作</span><span class="sxs-lookup"><span data-stu-id="f0d99-104">Parts of the Query Builder</span></span>  
 <span data-ttu-id="f0d99-105">アクティビティを検索するためのクエリを作成するには、ビジネス データの項目を選択します。これらの項目は、必要なデータを取得するために、ブール値の比較演算の対象として使用されます。</span><span class="sxs-lookup"><span data-stu-id="f0d99-105">You build queries for your activity search by selecting items of business data against which you will create Boolean comparisons to extract data of interest.</span></span> <span data-ttu-id="f0d99-106">BAM ビューを選択して、起動する、**マイ ビュー**ポータルのフレームです。</span><span class="sxs-lookup"><span data-stu-id="f0d99-106">You start by selecting a BAM view from the **My Views** frame of the portal.</span></span> <span data-ttu-id="f0d99-107">選択したビューから、作成するクエリの対象となるアクティビティを選択します。</span><span class="sxs-lookup"><span data-stu-id="f0d99-107">From the selected view you select an activity on which to build the query.</span></span>  
  
 ![](../core/media/bamportalviewschooser.gif "BAMPortalViewsChooser")  
  
 <span data-ttu-id="f0d99-108">アクティビティを選択すると、ポータルのコンテンツ フレームには、[クエリ]、[列の選択]、および [結果] ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f0d99-108">When you have selected the activity, the content frame of the portal displays the Query builder, Column Chooser, and Results boxes.</span></span> <span data-ttu-id="f0d99-109">既存のクエリを開くか、新しいクエリを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="f0d99-109">You can open an existing query or you can build a new one.</span></span>  
  
 ![](../core/media/activitysearchquerybuilder.gif "ActivitySearchQueryBuilder")  
  
 <span data-ttu-id="f0d99-110">ビジネス データ項目を選択して開始する新しいクエリを構築する、**ビジネス データ**ドロップダウン リスト。</span><span class="sxs-lookup"><span data-stu-id="f0d99-110">To build a new query you start by selecting a business data item from the **Business Data** drop-down list.</span></span>  
  
 ![](../core/media/activitysearchquerybuilderbusinessdatadropdown.gif "ActivitySearchQueryBuilderBusinessDataDropdown")  
  
 <span data-ttu-id="f0d99-111">次に、[演算子] ボックスの一覧で比較演算子を選択します。</span><span class="sxs-lookup"><span data-stu-id="f0d99-111">Next, you select your comparison operator in the Operator drop-down list.</span></span> <span data-ttu-id="f0d99-112">比較演算子を使用すると、クエリの結果を絞り込むことができます。</span><span class="sxs-lookup"><span data-stu-id="f0d99-112">The comparison operator allows you to refine the results of the query.</span></span>  
  
 ![](../core/media/activitysearchcomparisonoperatordropdown.gif "ActivitySearchComparisonOperatorDropDown")  
  
 <span data-ttu-id="f0d99-113">[値] ボックスの一覧は、ビジネス データ項目が表すデータの種類に基づき、状況に応じて変化します。</span><span class="sxs-lookup"><span data-stu-id="f0d99-113">The Value drop-down list is context-sensitive based on the type of data represented by the business data item.</span></span> <span data-ttu-id="f0d99-114">ユーザー インターフェイス (UI) は、許可されたデータ変更の種類によって変わります。</span><span class="sxs-lookup"><span data-stu-id="f0d99-114">The user interface (UI) changes as the type of permitted data changes.</span></span>  
  
 <span data-ttu-id="f0d99-115">使用してクエリの句を結合してまたは OR 演算子をクリックしてより複雑なクエリを作成する、**追加**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="f0d99-115">You can join clauses of the query with AND or OR operators to form more complex queries by clicking the **Add** button.</span></span>  
  
 ![](../core/media/activitysearchjoiningclauses.gif "ActivitySearchJoiningClauses")  
  
> [!NOTE]
>  <span data-ttu-id="f0d99-116">句をグループ化することはできません。</span><span class="sxs-lookup"><span data-stu-id="f0d99-116">You cannot group clauses.</span></span> <span data-ttu-id="f0d99-117">クエリは、個別の句を AND 演算子または OR 演算子で結合した単純な文字列です。</span><span class="sxs-lookup"><span data-stu-id="f0d99-117">A query is a simple string of individual clauses joined by AND/OR operators.</span></span>  
  
 <span data-ttu-id="f0d99-118">次の表では、日付と時刻のフィールドについて説明します。</span><span class="sxs-lookup"><span data-stu-id="f0d99-118">The following table describes the date and time fields.</span></span>  
  
|<span data-ttu-id="f0d99-119">演算子</span><span class="sxs-lookup"><span data-stu-id="f0d99-119">Operator</span></span>|<span data-ttu-id="f0d99-120">Description</span><span class="sxs-lookup"><span data-stu-id="f0d99-120">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="f0d99-121">**At**</span><span class="sxs-lookup"><span data-stu-id="f0d99-121">**At**</span></span>|<span data-ttu-id="f0d99-122">完全一致を指定します。</span><span class="sxs-lookup"><span data-stu-id="f0d99-122">Specifies an exact match.</span></span> <span data-ttu-id="f0d99-123">ブール値の "=" (等号) 演算子と同じです。</span><span class="sxs-lookup"><span data-stu-id="f0d99-123">Equivalent to a Boolean Equals (=) operation.</span></span> <span data-ttu-id="f0d99-124">**注:**を選択した場合、**で**演算子し、ポータルは、既定値として午前 0 時を使用して時刻部分と日付を指定します。</span><span class="sxs-lookup"><span data-stu-id="f0d99-124">**Note:**  If you select the **At** operator and specify a date with no time part the portal uses midnight as the default value.</span></span> <span data-ttu-id="f0d99-125">ユーザーの意図でない場合場合を使用して、**以前**または**以降の**オペレーターは、目的の結果を取得します。</span><span class="sxs-lookup"><span data-stu-id="f0d99-125">If this is not your intent, use the **At or before** or the **At or after** operators to obtain the desired results.</span></span>|  
|<span data-ttu-id="f0d99-126">**以前**</span><span class="sxs-lookup"><span data-stu-id="f0d99-126">**On or before**</span></span>|<span data-ttu-id="f0d99-127">指定した日付以前のトランザクションのみが一致するように指定します。</span><span class="sxs-lookup"><span data-stu-id="f0d99-127">Specifies that only transactions on or before the specified date are matched.</span></span> <span data-ttu-id="f0d99-128">ブール値の "≤" (以下) 演算子と同じです。</span><span class="sxs-lookup"><span data-stu-id="f0d99-128">Equivalent to a Boolean less than or equals (≤) operation.</span></span>|  
|<span data-ttu-id="f0d99-129">**以降**</span><span class="sxs-lookup"><span data-stu-id="f0d99-129">**On or after**</span></span>|<span data-ttu-id="f0d99-130">指定した日付以降のトランザクションのみが一致するように指定します。</span><span class="sxs-lookup"><span data-stu-id="f0d99-130">Specifies that only transactions on or after the specified date are matched.</span></span> <span data-ttu-id="f0d99-131">ブール値の "≥" (以上) 演算子と同じです。</span><span class="sxs-lookup"><span data-stu-id="f0d99-131">Equivalent to a Boolean greater than or equals (≥) operation.</span></span>|  
|<span data-ttu-id="f0d99-132">**[指定日付より前]**</span><span class="sxs-lookup"><span data-stu-id="f0d99-132">**Before**</span></span>|<span data-ttu-id="f0d99-133">指定した日付より前のトランザクションのみが一致するように指定します。</span><span class="sxs-lookup"><span data-stu-id="f0d99-133">Specifies that only transactions before the specified date are matched.</span></span> <span data-ttu-id="f0d99-134">ブール値を等価より小さい (\<) 操作です。</span><span class="sxs-lookup"><span data-stu-id="f0d99-134">Equivalent to a Boolean less than (\<) operation.</span></span>|  
|<span data-ttu-id="f0d99-135">**After**</span><span class="sxs-lookup"><span data-stu-id="f0d99-135">**After**</span></span>|<span data-ttu-id="f0d99-136">指定した日付より後のトランザクションのみが一致するように指定します。</span><span class="sxs-lookup"><span data-stu-id="f0d99-136">Specifies that only transactions after the specified date are matched.</span></span> <span data-ttu-id="f0d99-137">ブール値より大きい (>) 操作に相当します。</span><span class="sxs-lookup"><span data-stu-id="f0d99-137">Equivalent to a Boolean greater than (>) operation.</span></span>|  
|<span data-ttu-id="f0d99-138">**最後に**</span><span class="sxs-lookup"><span data-stu-id="f0d99-138">**In the last**</span></span>|<span data-ttu-id="f0d99-139">指定した過去の期間に発生したトランザクションのみが一致するように指定します。</span><span class="sxs-lookup"><span data-stu-id="f0d99-139">Specifies that only transactions that occurred in the previous specified time period are matched.</span></span> <span data-ttu-id="f0d99-140">期間は、秒、分、時間、または日数で指定できます。</span><span class="sxs-lookup"><span data-stu-id="f0d99-140">The time period can be specified in seconds, minutes, hours, or days.</span></span>|  
|<span data-ttu-id="f0d99-141">**最後の前に**</span><span class="sxs-lookup"><span data-stu-id="f0d99-141">**Before the last**</span></span>|<span data-ttu-id="f0d99-142">指定した期間より前に発生したトランザクションのみが一致するように指定します。</span><span class="sxs-lookup"><span data-stu-id="f0d99-142">Specifies that only transactions that occurred prior to the specified time period are matched.</span></span> <span data-ttu-id="f0d99-143">期間は、秒、分、時間、または日数で指定できます。</span><span class="sxs-lookup"><span data-stu-id="f0d99-143">The time period can be specified in seconds, minutes, hours, or days.</span></span>|  
|<span data-ttu-id="f0d99-144">**空です。**</span><span class="sxs-lookup"><span data-stu-id="f0d99-144">**Is empty**</span></span>|<span data-ttu-id="f0d99-145">ビジネス データ項目にデータが含まれていない (データ フィールドの値が NULL の) トランザクションのみが返されるように指定します。</span><span class="sxs-lookup"><span data-stu-id="f0d99-145">Specifies that only transactions for which the business data item contains no data (the value of data field is NULL) are returned.</span></span>|  
|<span data-ttu-id="f0d99-146">**空でないです。**</span><span class="sxs-lookup"><span data-stu-id="f0d99-146">**Is not empty**</span></span>|<span data-ttu-id="f0d99-147">ビジネス データ項目にデータが含まれている (データ フィールドの値が NULL ではない) トランザクションのみが返されるように指定します。</span><span class="sxs-lookup"><span data-stu-id="f0d99-147">Specifies that only transactions for which the business data item contains data (the value of data field is not NULL) are returned.</span></span>|  
  
 <span data-ttu-id="f0d99-148">次の表では、数値フィールドおよび期間フィールドについて説明します。</span><span class="sxs-lookup"><span data-stu-id="f0d99-148">The following table describes the numeric fields and the duration fields.</span></span> <span data-ttu-id="f0d99-149">数値フィールドには、数量や金額などのデータが含まれます。</span><span class="sxs-lookup"><span data-stu-id="f0d99-149">Numeric fields contain data such as quantities or currency amounts.</span></span> <span data-ttu-id="f0d99-150">期間フィールドでは、期間を指定します。</span><span class="sxs-lookup"><span data-stu-id="f0d99-150">Duration fields specify a time period.</span></span>  
  
|<span data-ttu-id="f0d99-151">演算子</span><span class="sxs-lookup"><span data-stu-id="f0d99-151">Operator</span></span>|<span data-ttu-id="f0d99-152">Description</span><span class="sxs-lookup"><span data-stu-id="f0d99-152">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="f0d99-153">**[等しい]**</span><span class="sxs-lookup"><span data-stu-id="f0d99-153">**Equals**</span></span>|<span data-ttu-id="f0d99-154">完全一致を指定します。</span><span class="sxs-lookup"><span data-stu-id="f0d99-154">Specifies an exact match.</span></span> <span data-ttu-id="f0d99-155">ブール値の "=" (等号) 演算子と同じです。</span><span class="sxs-lookup"><span data-stu-id="f0d99-155">Equivalent to a Boolean Equals (=) operation.</span></span>|  
|<span data-ttu-id="f0d99-156">**より大きい**</span><span class="sxs-lookup"><span data-stu-id="f0d99-156">**Greater than**</span></span>|<span data-ttu-id="f0d99-157">完全一致を指定します。</span><span class="sxs-lookup"><span data-stu-id="f0d99-157">Specifies an exact match.</span></span> <span data-ttu-id="f0d99-158">ブール値の ">" (より大きい) 演算子と同じです。</span><span class="sxs-lookup"><span data-stu-id="f0d99-158">Equivalent to a Boolean Greater Than (>) operation.</span></span>|  
|<span data-ttu-id="f0d99-159">**[次の値以上]**</span><span class="sxs-lookup"><span data-stu-id="f0d99-159">**Greater than or equal**</span></span>|<span data-ttu-id="f0d99-160">完全一致を指定します。</span><span class="sxs-lookup"><span data-stu-id="f0d99-160">Specifies an exact match.</span></span> <span data-ttu-id="f0d99-161">ブール型の値より大きいまたは等しい (≥) 操作に相当します。</span><span class="sxs-lookup"><span data-stu-id="f0d99-161">Equivalent to a Boolean Greater Than or Equals (≥) operation.</span></span>|  
|<span data-ttu-id="f0d99-162">**より小さい**</span><span class="sxs-lookup"><span data-stu-id="f0d99-162">**Less than**</span></span>|<span data-ttu-id="f0d99-163">完全一致を指定します。</span><span class="sxs-lookup"><span data-stu-id="f0d99-163">Specifies an exact match.</span></span> <span data-ttu-id="f0d99-164">ブール値より小さい (<) 操作に相当します。</span><span class="sxs-lookup"><span data-stu-id="f0d99-164">Equivalent to a Boolean Less Than (<) operation.</span></span>|  
|<span data-ttu-id="f0d99-165">**[次の値以下]**</span><span class="sxs-lookup"><span data-stu-id="f0d99-165">**Less than or equal**</span></span>|<span data-ttu-id="f0d99-166">完全一致を指定します。</span><span class="sxs-lookup"><span data-stu-id="f0d99-166">Specifies an exact match.</span></span> <span data-ttu-id="f0d99-167">"≤" (以下) 演算子と同じです。</span><span class="sxs-lookup"><span data-stu-id="f0d99-167">Equivalent to a Less Than or Equals (≤) operation.</span></span>|  
|<span data-ttu-id="f0d99-168">**等しくないです。**</span><span class="sxs-lookup"><span data-stu-id="f0d99-168">**Not Equal**</span></span>|<span data-ttu-id="f0d99-169">完全一致を指定します。</span><span class="sxs-lookup"><span data-stu-id="f0d99-169">Specifies an exact match.</span></span> <span data-ttu-id="f0d99-170">ブール値の "≠" (不等号) 演算子と同じです。</span><span class="sxs-lookup"><span data-stu-id="f0d99-170">Equivalent to a Not Equals (≠) operation.</span></span>|  
|<span data-ttu-id="f0d99-171">**空です。**</span><span class="sxs-lookup"><span data-stu-id="f0d99-171">**Is empty**</span></span>|<span data-ttu-id="f0d99-172">ビジネス データ項目にデータが含まれていない (データ フィールドの値が NULL の) トランザクションのみが返されるように指定します。</span><span class="sxs-lookup"><span data-stu-id="f0d99-172">Specifies that only transactions for which the business data item contains no data (the value of data field is NULL) are returned.</span></span>|  
|<span data-ttu-id="f0d99-173">**空でないです。**</span><span class="sxs-lookup"><span data-stu-id="f0d99-173">**Is not empty**</span></span>|<span data-ttu-id="f0d99-174">ビジネス データ項目にデータが含まれている (データ フィールドの値が NULL ではない) トランザクションのみが返されるように指定します。</span><span class="sxs-lookup"><span data-stu-id="f0d99-174">Specifies that only transactions for which the business data item contains data (the value of data field is not NULL) are returned.</span></span>|  
  
 <span data-ttu-id="f0d99-175">次の表では、テキスト フィールドについて説明します。</span><span class="sxs-lookup"><span data-stu-id="f0d99-175">The following table describes the text fields.</span></span>  
  
|<span data-ttu-id="f0d99-176">演算子</span><span class="sxs-lookup"><span data-stu-id="f0d99-176">Operator</span></span>|<span data-ttu-id="f0d99-177">Description</span><span class="sxs-lookup"><span data-stu-id="f0d99-177">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="f0d99-178">**正確には**</span><span class="sxs-lookup"><span data-stu-id="f0d99-178">**Is Exactly**</span></span>|<span data-ttu-id="f0d99-179">完全一致を指定します。</span><span class="sxs-lookup"><span data-stu-id="f0d99-179">Specifies an exact match.</span></span> <span data-ttu-id="f0d99-180">ブール値の "=" (等号) 演算子と同じです。</span><span class="sxs-lookup"><span data-stu-id="f0d99-180">Equivalent to a Boolean Equals (=) operation.</span></span>|  
|<span data-ttu-id="f0d99-181">**[値を含む]**</span><span class="sxs-lookup"><span data-stu-id="f0d99-181">**Contains**</span></span>|<span data-ttu-id="f0d99-182">指定した値がビジネス データ項目のテキストに含まれるように指定します。</span><span class="sxs-lookup"><span data-stu-id="f0d99-182">Specifies that the text in the business data item contains the specified value.</span></span> <span data-ttu-id="f0d99-183">これにより、データの部分的な一致を指定できます。</span><span class="sxs-lookup"><span data-stu-id="f0d99-183">This allows you to do partial matches on the data.</span></span>|  
|<span data-ttu-id="f0d99-184">**[次を含まない]**</span><span class="sxs-lookup"><span data-stu-id="f0d99-184">**Does not contain**</span></span>|<span data-ttu-id="f0d99-185">指定した値がビジネス データ項目のテキストに含まれないように指定します。</span><span class="sxs-lookup"><span data-stu-id="f0d99-185">Specifies that the text in the business data item does not contain the specified value.</span></span>|  
|<span data-ttu-id="f0d99-186">**空です。**</span><span class="sxs-lookup"><span data-stu-id="f0d99-186">**Is empty**</span></span>|<span data-ttu-id="f0d99-187">ビジネス データ項目にデータが含まれていない (データ フィールドの値が NULL の) トランザクションのみが返されるように指定します。</span><span class="sxs-lookup"><span data-stu-id="f0d99-187">Specifies that only transactions for which the business data item contains no data (the value of data field is NULL) are returned.</span></span>|  
|<span data-ttu-id="f0d99-188">**空でないです。**</span><span class="sxs-lookup"><span data-stu-id="f0d99-188">**Is not empty**</span></span>|<span data-ttu-id="f0d99-189">ビジネス データ項目にデータが含まれている (データ フィールドの値が NULL ではない) トランザクションのみが返されるように指定します。</span><span class="sxs-lookup"><span data-stu-id="f0d99-189">Specifies that only transactions for which the business data item contains data (the value of data field is not NULL) are returned.</span></span>|  
  
## <a name="in-this-section"></a><span data-ttu-id="f0d99-190">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="f0d99-190">In This Section</span></span>  
  
-   [<span data-ttu-id="f0d99-191">アクティビティの検索でクエリを作成する方法</span><span class="sxs-lookup"><span data-stu-id="f0d99-191">How to Create a Query in Activity Search</span></span>](../core/how-to-create-a-query-in-activity-search.md)  
  
-   [<span data-ttu-id="f0d99-192">警告を設定する方法</span><span class="sxs-lookup"><span data-stu-id="f0d99-192">How to Set an Alert</span></span>](../core/how-to-set-an-alert.md)  
  
-   [<span data-ttu-id="f0d99-193">アクティビティの検索の結果を表示する方法</span><span class="sxs-lookup"><span data-stu-id="f0d99-193">How to View the Results of an Activity Search</span></span>](../core/how-to-view-the-results-of-an-activity-search.md)  
  
## <a name="see-also"></a><span data-ttu-id="f0d99-194">参照</span><span class="sxs-lookup"><span data-stu-id="f0d99-194">See Also</span></span>  
 [<span data-ttu-id="f0d99-195">BAM ポータル</span><span class="sxs-lookup"><span data-stu-id="f0d99-195">BAM Portal</span></span>](../core/bam-portal.md)