---
title: BAM ポータルでのアクティビティの検索 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b97f9577d43552ad51766ccc4178bb2d73fb7107
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65361585"
---
# <a name="activity-searches-in-the-bam-portal"></a><span data-ttu-id="8ab18-102">BAM ポータルでのアクティビティの検索</span><span class="sxs-lookup"><span data-stu-id="8ab18-102">Activity Searches in the BAM Portal</span></span>
<span data-ttu-id="8ab18-103">アクティビティの検索を使用し、これに基づいて、BAM ビューで、その編集や、アラートを作成できるように、これらのアクティビティを表示して、追跡対象の値に基づいて、使用可能な項目を指定した条件に一致するアクティビティを検索する BAM データに対して検索を実行することができます。</span><span class="sxs-lookup"><span data-stu-id="8ab18-103">An activity search allows you to perform searches against BAM data to find activities that match the criteria you specify based on tracked values and items available in a BAM view, and to display these activities so that you can edit them or create alerts based on them.</span></span>  
  
## <a name="parts-of-the-query-builder"></a><span data-ttu-id="8ab18-104">クエリ ビルダーのパーツ</span><span class="sxs-lookup"><span data-stu-id="8ab18-104">Parts of the Query Builder</span></span>  
 <span data-ttu-id="8ab18-105">アクティビティの検索のクエリを作成するには、関心のあるデータを抽出するブール型の比較を作成する対象となるビジネス データ項目を選択します。</span><span class="sxs-lookup"><span data-stu-id="8ab18-105">You build queries for your activity search by selecting items of business data against which you will create Boolean comparisons to extract data of interest.</span></span> <span data-ttu-id="8ab18-106">BAM ビューを選択して開始する、**マイ ビュー**ポータルのフレーム。</span><span class="sxs-lookup"><span data-stu-id="8ab18-106">You start by selecting a BAM view from the **My Views** frame of the portal.</span></span> <span data-ttu-id="8ab18-107">選択したビューからクエリを構築するためのアクティビティを選択します。</span><span class="sxs-lookup"><span data-stu-id="8ab18-107">From the selected view you select an activity on which to build the query.</span></span>  
  
 <span data-ttu-id="8ab18-108">![](../core/media/bamportalviewschooser.gif "BAMPortalViewsChooser")</span><span class="sxs-lookup"><span data-stu-id="8ab18-108">![](../core/media/bamportalviewschooser.gif "BAMPortalViewsChooser")</span></span>  
  
 <span data-ttu-id="8ab18-109">アクティビティを選択したら、ポータルのコンテンツ フレームには、クエリ ビルダー、列の選択、および結果のボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8ab18-109">When you have selected the activity, the content frame of the portal displays the Query builder, Column Chooser, and Results boxes.</span></span> <span data-ttu-id="8ab18-110">既存のクエリを開くか、新しいゲートウェイを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="8ab18-110">You can open an existing query or you can build a new one.</span></span>  
  
 <span data-ttu-id="8ab18-111">![](../core/media/activitysearchquerybuilder.gif "ActivitySearchQueryBuilder")</span><span class="sxs-lookup"><span data-stu-id="8ab18-111">![](../core/media/activitysearchquerybuilder.gif "ActivitySearchQueryBuilder")</span></span>  
  
 <span data-ttu-id="8ab18-112">ビジネス データ項目を選択して開始する新しいクエリを作成する、**ビジネス データ**ドロップダウン リスト。</span><span class="sxs-lookup"><span data-stu-id="8ab18-112">To build a new query you start by selecting a business data item from the **Business Data** drop-down list.</span></span>  
  
 <span data-ttu-id="8ab18-113">![](../core/media/activitysearchquerybuilderbusinessdatadropdown.gif "ActivitySearchQueryBuilderBusinessDataDropdown")</span><span class="sxs-lookup"><span data-stu-id="8ab18-113">![](../core/media/activitysearchquerybuilderbusinessdatadropdown.gif "ActivitySearchQueryBuilderBusinessDataDropdown")</span></span>  
  
 <span data-ttu-id="8ab18-114">次に、演算子のドロップダウン リストで、比較演算子を選択します。</span><span class="sxs-lookup"><span data-stu-id="8ab18-114">Next, you select your comparison operator in the Operator drop-down list.</span></span> <span data-ttu-id="8ab18-115">比較演算子を使用すると、クエリの結果を絞り込むことができます。</span><span class="sxs-lookup"><span data-stu-id="8ab18-115">The comparison operator allows you to refine the results of the query.</span></span>  
  
 <span data-ttu-id="8ab18-116">![](../core/media/activitysearchcomparisonoperatordropdown.gif "ActivitySearchComparisonOperatorDropDown")</span><span class="sxs-lookup"><span data-stu-id="8ab18-116">![](../core/media/activitysearchcomparisonoperatordropdown.gif "ActivitySearchComparisonOperatorDropDown")</span></span>  
  
 <span data-ttu-id="8ab18-117">値のドロップダウン リストは、ビジネス データ項目によって表されるデータの種類に基づく状況依存します。</span><span class="sxs-lookup"><span data-stu-id="8ab18-117">The Value drop-down list is context-sensitive based on the type of data represented by the business data item.</span></span> <span data-ttu-id="8ab18-118">許可されているデータ変更の種類として、ユーザー インターフェイス (UI) を変更します。</span><span class="sxs-lookup"><span data-stu-id="8ab18-118">The user interface (UI) changes as the type of permitted data changes.</span></span>  
  
 <span data-ttu-id="8ab18-119">使用したクエリの句を結合することができますとまたは OR 演算子をクリックしてより複雑なクエリを形成する、**追加**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="8ab18-119">You can join clauses of the query with AND or OR operators to form more complex queries by clicking the **Add** button.</span></span>  
  
 <span data-ttu-id="8ab18-120">![](../core/media/activitysearchjoiningclauses.gif "ActivitySearchJoiningClauses")</span><span class="sxs-lookup"><span data-stu-id="8ab18-120">![](../core/media/activitysearchjoiningclauses.gif "ActivitySearchJoiningClauses")</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8ab18-121">句をグループ化することはできません。</span><span class="sxs-lookup"><span data-stu-id="8ab18-121">You cannot group clauses.</span></span> <span data-ttu-id="8ab18-122">クエリは、参加させる個々 の句の単純な文字列や演算子。</span><span class="sxs-lookup"><span data-stu-id="8ab18-122">A query is a simple string of individual clauses joined by AND/OR operators.</span></span>  
  
 <span data-ttu-id="8ab18-123">次の表では、日付と時刻のフィールドについて説明します。</span><span class="sxs-lookup"><span data-stu-id="8ab18-123">The following table describes the date and time fields.</span></span>  
  
|<span data-ttu-id="8ab18-124">演算子</span><span class="sxs-lookup"><span data-stu-id="8ab18-124">Operator</span></span>|<span data-ttu-id="8ab18-125">説明</span><span class="sxs-lookup"><span data-stu-id="8ab18-125">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="8ab18-126">**で**</span><span class="sxs-lookup"><span data-stu-id="8ab18-126">**At**</span></span>|<span data-ttu-id="8ab18-127">完全一致を指定します。</span><span class="sxs-lookup"><span data-stu-id="8ab18-127">Specifies an exact match.</span></span> <span data-ttu-id="8ab18-128">ブール値に等しい (=) の操作と同じです。</span><span class="sxs-lookup"><span data-stu-id="8ab18-128">Equivalent to a Boolean Equals (=) operation.</span></span> <span data-ttu-id="8ab18-129">**注:** 選択した場合、**で**演算子をポータルは既定値として午前 0 時を使用ない時刻の部分で日付を指定します。</span><span class="sxs-lookup"><span data-stu-id="8ab18-129">**Note:**  If you select the **At** operator and specify a date with no time part the portal uses midnight as the default value.</span></span> <span data-ttu-id="8ab18-130">場合は、意図でない場合を使用して、**以前**または**以降**目的の結果を取得する演算子。</span><span class="sxs-lookup"><span data-stu-id="8ab18-130">If this is not your intent, use the **At or before** or the **At or after** operators to obtain the desired results.</span></span>|  
|<span data-ttu-id="8ab18-131">**以前**</span><span class="sxs-lookup"><span data-stu-id="8ab18-131">**On or before**</span></span>|<span data-ttu-id="8ab18-132">指定した日付より前に、のトランザクションのみが一致することを指定します。</span><span class="sxs-lookup"><span data-stu-id="8ab18-132">Specifies that only transactions on or before the specified date are matched.</span></span> <span data-ttu-id="8ab18-133">ブール値に相当より小さいまたは等しい (≤) 操作。</span><span class="sxs-lookup"><span data-stu-id="8ab18-133">Equivalent to a Boolean less than or equals (≤) operation.</span></span>|  
|<span data-ttu-id="8ab18-134">**以降**</span><span class="sxs-lookup"><span data-stu-id="8ab18-134">**On or after**</span></span>|<span data-ttu-id="8ab18-135">指定した日付以降のトランザクションのみが一致することを指定します。</span><span class="sxs-lookup"><span data-stu-id="8ab18-135">Specifies that only transactions on or after the specified date are matched.</span></span> <span data-ttu-id="8ab18-136">ブール値より大きいまたは等しい (≥) 操作と同じです。</span><span class="sxs-lookup"><span data-stu-id="8ab18-136">Equivalent to a Boolean greater than or equals (≥) operation.</span></span>|  
|<span data-ttu-id="8ab18-137">**[指定日付より前]**</span><span class="sxs-lookup"><span data-stu-id="8ab18-137">**Before**</span></span>|<span data-ttu-id="8ab18-138">指定した日付より前に、のトランザクションのみが一致することを指定します。</span><span class="sxs-lookup"><span data-stu-id="8ab18-138">Specifies that only transactions before the specified date are matched.</span></span> <span data-ttu-id="8ab18-139">ブール値 (<) の操作よりも小さいと等価です。</span><span class="sxs-lookup"><span data-stu-id="8ab18-139">Equivalent to a Boolean less than (<) operation.</span></span>|  
|<span data-ttu-id="8ab18-140">**After**</span><span class="sxs-lookup"><span data-stu-id="8ab18-140">**After**</span></span>|<span data-ttu-id="8ab18-141">指定日付より後のトランザクションのみが一致することを指定します。</span><span class="sxs-lookup"><span data-stu-id="8ab18-141">Specifies that only transactions after the specified date are matched.</span></span> <span data-ttu-id="8ab18-142">ブール型の大なり (>) 演算子と同じです。</span><span class="sxs-lookup"><span data-stu-id="8ab18-142">Equivalent to a Boolean greater than (>) operation.</span></span>|  
|<span data-ttu-id="8ab18-143">**最後に**</span><span class="sxs-lookup"><span data-stu-id="8ab18-143">**In the last**</span></span>|<span data-ttu-id="8ab18-144">期間を指定する前に発生したトランザクションのみが一致することを指定します。</span><span class="sxs-lookup"><span data-stu-id="8ab18-144">Specifies that only transactions that occurred in the previous specified time period are matched.</span></span> <span data-ttu-id="8ab18-145">期間は、秒、分、時間、または日数で指定できます。</span><span class="sxs-lookup"><span data-stu-id="8ab18-145">The time period can be specified in seconds, minutes, hours, or days.</span></span>|  
|<span data-ttu-id="8ab18-146">**最後の前に**</span><span class="sxs-lookup"><span data-stu-id="8ab18-146">**Before the last**</span></span>|<span data-ttu-id="8ab18-147">指定した期間の前に発生したトランザクションのみが一致することを指定します。</span><span class="sxs-lookup"><span data-stu-id="8ab18-147">Specifies that only transactions that occurred prior to the specified time period are matched.</span></span> <span data-ttu-id="8ab18-148">期間は、秒、分、時間、または日数で指定できます。</span><span class="sxs-lookup"><span data-stu-id="8ab18-148">The time period can be specified in seconds, minutes, hours, or days.</span></span>|  
|<span data-ttu-id="8ab18-149">**空です。**</span><span class="sxs-lookup"><span data-stu-id="8ab18-149">**Is empty**</span></span>|<span data-ttu-id="8ab18-150">対象のビジネス データ項目が含まれていないデータに (データ フィールドの値は NULL) のトランザクションのみが返されることを指定します。</span><span class="sxs-lookup"><span data-stu-id="8ab18-150">Specifies that only transactions for which the business data item contains no data (the value of data field is NULL) are returned.</span></span>|  
|<span data-ttu-id="8ab18-151">**空でないです。**</span><span class="sxs-lookup"><span data-stu-id="8ab18-151">**Is not empty**</span></span>|<span data-ttu-id="8ab18-152">ビジネス データ項目が (データ フィールドの値が NULL でない) データが含まれますトランザクションのみが返されることを指定します。</span><span class="sxs-lookup"><span data-stu-id="8ab18-152">Specifies that only transactions for which the business data item contains data (the value of data field is not NULL) are returned.</span></span>|  
  
 <span data-ttu-id="8ab18-153">次の表では、数値フィールドおよび期間フィールドについて説明します。</span><span class="sxs-lookup"><span data-stu-id="8ab18-153">The following table describes the numeric fields and the duration fields.</span></span> <span data-ttu-id="8ab18-154">数値フィールドには、数量や金額などのデータが含まれます。</span><span class="sxs-lookup"><span data-stu-id="8ab18-154">Numeric fields contain data such as quantities or currency amounts.</span></span> <span data-ttu-id="8ab18-155">期間フィールドでは、期間を指定します。</span><span class="sxs-lookup"><span data-stu-id="8ab18-155">Duration fields specify a time period.</span></span>  
  
|<span data-ttu-id="8ab18-156">演算子</span><span class="sxs-lookup"><span data-stu-id="8ab18-156">Operator</span></span>|<span data-ttu-id="8ab18-157">説明</span><span class="sxs-lookup"><span data-stu-id="8ab18-157">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="8ab18-158">**[等しい]**</span><span class="sxs-lookup"><span data-stu-id="8ab18-158">**Equals**</span></span>|<span data-ttu-id="8ab18-159">完全一致を指定します。</span><span class="sxs-lookup"><span data-stu-id="8ab18-159">Specifies an exact match.</span></span> <span data-ttu-id="8ab18-160">ブール値に等しい (=) の操作と同じです。</span><span class="sxs-lookup"><span data-stu-id="8ab18-160">Equivalent to a Boolean Equals (=) operation.</span></span>|  
|<span data-ttu-id="8ab18-161">**より大きい**</span><span class="sxs-lookup"><span data-stu-id="8ab18-161">**Greater than**</span></span>|<span data-ttu-id="8ab18-162">完全一致を指定します。</span><span class="sxs-lookup"><span data-stu-id="8ab18-162">Specifies an exact match.</span></span> <span data-ttu-id="8ab18-163">ブール型の値より大きい (>) 操作と同じです。</span><span class="sxs-lookup"><span data-stu-id="8ab18-163">Equivalent to a Boolean Greater Than (>) operation.</span></span>|  
|<span data-ttu-id="8ab18-164">**[次の値以上]**</span><span class="sxs-lookup"><span data-stu-id="8ab18-164">**Greater than or equal**</span></span>|<span data-ttu-id="8ab18-165">完全一致を指定します。</span><span class="sxs-lookup"><span data-stu-id="8ab18-165">Specifies an exact match.</span></span> <span data-ttu-id="8ab18-166">ブール型の値より大きいまたは等しい (≥) 操作と同じです。</span><span class="sxs-lookup"><span data-stu-id="8ab18-166">Equivalent to a Boolean Greater Than or Equals (≥) operation.</span></span>|  
|<span data-ttu-id="8ab18-167">**より小さい**</span><span class="sxs-lookup"><span data-stu-id="8ab18-167">**Less than**</span></span>|<span data-ttu-id="8ab18-168">完全一致を指定します。</span><span class="sxs-lookup"><span data-stu-id="8ab18-168">Specifies an exact match.</span></span> <span data-ttu-id="8ab18-169">ブール値より小さい (<) 演算子と同じです。</span><span class="sxs-lookup"><span data-stu-id="8ab18-169">Equivalent to a Boolean Less Than (<) operation.</span></span>|  
|<span data-ttu-id="8ab18-170">**[次の値以下]**</span><span class="sxs-lookup"><span data-stu-id="8ab18-170">**Less than or equal**</span></span>|<span data-ttu-id="8ab18-171">完全一致を指定します。</span><span class="sxs-lookup"><span data-stu-id="8ab18-171">Specifies an exact match.</span></span> <span data-ttu-id="8ab18-172">小なりに相当よりまたは等しい (≤) 操作。</span><span class="sxs-lookup"><span data-stu-id="8ab18-172">Equivalent to a Less Than or Equals (≤) operation.</span></span>|  
|<span data-ttu-id="8ab18-173">**等しくないです。**</span><span class="sxs-lookup"><span data-stu-id="8ab18-173">**Not Equal**</span></span>|<span data-ttu-id="8ab18-174">完全一致を指定します。</span><span class="sxs-lookup"><span data-stu-id="8ab18-174">Specifies an exact match.</span></span> <span data-ttu-id="8ab18-175">いない Equals (≠) 操作と同じです。</span><span class="sxs-lookup"><span data-stu-id="8ab18-175">Equivalent to a Not Equals (≠) operation.</span></span>|  
|<span data-ttu-id="8ab18-176">**空です。**</span><span class="sxs-lookup"><span data-stu-id="8ab18-176">**Is empty**</span></span>|<span data-ttu-id="8ab18-177">対象のビジネス データ項目が含まれていないデータに (データ フィールドの値は NULL) のトランザクションのみが返されることを指定します。</span><span class="sxs-lookup"><span data-stu-id="8ab18-177">Specifies that only transactions for which the business data item contains no data (the value of data field is NULL) are returned.</span></span>|  
|<span data-ttu-id="8ab18-178">**空でないです。**</span><span class="sxs-lookup"><span data-stu-id="8ab18-178">**Is not empty**</span></span>|<span data-ttu-id="8ab18-179">ビジネス データ項目が (データ フィールドの値が NULL でない) データが含まれますトランザクションのみが返されることを指定します。</span><span class="sxs-lookup"><span data-stu-id="8ab18-179">Specifies that only transactions for which the business data item contains data (the value of data field is not NULL) are returned.</span></span>|  
  
 <span data-ttu-id="8ab18-180">次の表では、テキスト フィールドについて説明します。</span><span class="sxs-lookup"><span data-stu-id="8ab18-180">The following table describes the text fields.</span></span>  
  
|<span data-ttu-id="8ab18-181">演算子</span><span class="sxs-lookup"><span data-stu-id="8ab18-181">Operator</span></span>|<span data-ttu-id="8ab18-182">説明</span><span class="sxs-lookup"><span data-stu-id="8ab18-182">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="8ab18-183">**正確には**</span><span class="sxs-lookup"><span data-stu-id="8ab18-183">**Is Exactly**</span></span>|<span data-ttu-id="8ab18-184">完全一致を指定します。</span><span class="sxs-lookup"><span data-stu-id="8ab18-184">Specifies an exact match.</span></span> <span data-ttu-id="8ab18-185">ブール値に等しい (=) の操作と同じです。</span><span class="sxs-lookup"><span data-stu-id="8ab18-185">Equivalent to a Boolean Equals (=) operation.</span></span>|  
|<span data-ttu-id="8ab18-186">**[値を含む]**</span><span class="sxs-lookup"><span data-stu-id="8ab18-186">**Contains**</span></span>|<span data-ttu-id="8ab18-187">ビジネス データ項目のテキストに指定した値が含まれているを指定します。</span><span class="sxs-lookup"><span data-stu-id="8ab18-187">Specifies that the text in the business data item contains the specified value.</span></span> <span data-ttu-id="8ab18-188">これにより、データの部分的な一致を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="8ab18-188">This allows you to do partial matches on the data.</span></span>|  
|<span data-ttu-id="8ab18-189">**[次を含まない]**</span><span class="sxs-lookup"><span data-stu-id="8ab18-189">**Does not contain**</span></span>|<span data-ttu-id="8ab18-190">ビジネス データ項目のテキストに指定した値が含まれていないことを指定します。</span><span class="sxs-lookup"><span data-stu-id="8ab18-190">Specifies that the text in the business data item does not contain the specified value.</span></span>|  
|<span data-ttu-id="8ab18-191">**空です。**</span><span class="sxs-lookup"><span data-stu-id="8ab18-191">**Is empty**</span></span>|<span data-ttu-id="8ab18-192">対象のビジネス データ項目が含まれていないデータに (データ フィールドの値は NULL) のトランザクションのみが返されることを指定します。</span><span class="sxs-lookup"><span data-stu-id="8ab18-192">Specifies that only transactions for which the business data item contains no data (the value of data field is NULL) are returned.</span></span>|  
|<span data-ttu-id="8ab18-193">**空でないです。**</span><span class="sxs-lookup"><span data-stu-id="8ab18-193">**Is not empty**</span></span>|<span data-ttu-id="8ab18-194">ビジネス データ項目が (データ フィールドの値が NULL でない) データが含まれますトランザクションのみが返されることを指定します。</span><span class="sxs-lookup"><span data-stu-id="8ab18-194">Specifies that only transactions for which the business data item contains data (the value of data field is not NULL) are returned.</span></span>|  
  
## <a name="in-this-section"></a><span data-ttu-id="8ab18-195">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="8ab18-195">In This Section</span></span>  
  
-   [<span data-ttu-id="8ab18-196">アクティビティの検索でクエリを作成する方法</span><span class="sxs-lookup"><span data-stu-id="8ab18-196">How to Create a Query in Activity Search</span></span>](../core/how-to-create-a-query-in-activity-search.md)  
  
-   [<span data-ttu-id="8ab18-197">アラートを設定する方法</span><span class="sxs-lookup"><span data-stu-id="8ab18-197">How to Set an Alert</span></span>](../core/how-to-set-an-alert.md)  
  
-   [<span data-ttu-id="8ab18-198">アクティビティの検索の結果を表示する方法</span><span class="sxs-lookup"><span data-stu-id="8ab18-198">How to View the Results of an Activity Search</span></span>](../core/how-to-view-the-results-of-an-activity-search.md)  
  
## <a name="see-also"></a><span data-ttu-id="8ab18-199">参照</span><span class="sxs-lookup"><span data-stu-id="8ab18-199">See Also</span></span>  
 [<span data-ttu-id="8ab18-200">BAM ポータル</span><span class="sxs-lookup"><span data-stu-id="8ab18-200">BAM Portal</span></span>](../core/bam-portal.md)