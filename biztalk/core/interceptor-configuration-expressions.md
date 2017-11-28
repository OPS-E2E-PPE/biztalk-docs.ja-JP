---
title: "インターセプタ構成式 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2695f509-fece-40b8-aa00-fa3c0c0f19c5
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a28af058ac4750426f66dc6e290bc6a02bf2efd6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="interceptor-configuration-expressions"></a><span data-ttu-id="086e2-102">インターセプタ構成式</span><span class="sxs-lookup"><span data-stu-id="086e2-102">Interceptor Configuration Expressions</span></span>
<span data-ttu-id="086e2-103">BAM インターセプタ構成ファイルは、フィルタ式を使用してアクティビティを識別し、データ式を使用してストレージのデータ要素を作成して、そのデータ要素を関連付け ID または継続トークンとして使用したり、同様の目的で使用します。</span><span class="sxs-lookup"><span data-stu-id="086e2-103">The BAM interceptor configuraton file uses filter expressions to identify an activity and uses data expressions to construct a data element for storage, use as a correlation ID or continuation token, or similar purpose.</span></span> <span data-ttu-id="086e2-104">その目的に関係なく、個々の式は `expression` 要素によってインターセプタ構成ファイル内に指定され、式には後置表記法とも呼ばれる逆ポーランド表記法 (RPN: Reverse Polish Notation) を使用した 1 つまたは複数の演算子が含まれています。</span><span class="sxs-lookup"><span data-stu-id="086e2-104">Regardless of the purpose, individual expressions are identified in the interceptor configuration file by the `expression` element and contain one or more operations using Reverse Polish Notation, also known as postfix notation.</span></span>  
  
## <a name="about-reverse-polish-notation"></a><span data-ttu-id="086e2-105">逆ポーランド表記法について</span><span class="sxs-lookup"><span data-stu-id="086e2-105">About Reverse Polish Notation</span></span>  
 <span data-ttu-id="086e2-106">逆ポーランド表記法では、演算子の前にオペランドを記述するため、かっこを前置演算子として使用する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="086e2-106">In Reverse Polish Notation (RPN), operands precede the operator, thereby removing the need to use parentheses as precedence operators.</span></span> <span data-ttu-id="086e2-107">スタックは、スタックへの値のプッシュ、スタックからの値のポップ (削除)、またはプッシュとポップを組み合わせた操作の実行における各値とすべての操作の保持に使用されます。</span><span class="sxs-lookup"><span data-stu-id="086e2-107">A stack is used to hold values and all operations either push values onto the stack, pop (remove) values from the stack, or perform a combination of pushes and pops to complete an operation.</span></span>  
  
 <span data-ttu-id="086e2-108">たとえば、次の式の評価を行うとします。</span><span class="sxs-lookup"><span data-stu-id="086e2-108">For example, if you wanted to evaluate the expression</span></span>  
  
 `5 + (10 - 2)`  
  
 <span data-ttu-id="086e2-109">この式を同等の RPN に変換すると次のようになります。</span><span class="sxs-lookup"><span data-stu-id="086e2-109">Converting this to the equivalent RPN results in</span></span>  
  
 `5 10 2 - +`  
  
 <span data-ttu-id="086e2-110">この式は、次のように評価されます。</span><span class="sxs-lookup"><span data-stu-id="086e2-110">This would be evaluated as follows:</span></span>  
  
|<span data-ttu-id="086e2-111">入力</span><span class="sxs-lookup"><span data-stu-id="086e2-111">Input</span></span>|<span data-ttu-id="086e2-112">操作</span><span class="sxs-lookup"><span data-stu-id="086e2-112">Operation</span></span>|<span data-ttu-id="086e2-113">スタック</span><span class="sxs-lookup"><span data-stu-id="086e2-113">Stack</span></span>|  
|-----------|---------------|-----------|  
|<span data-ttu-id="086e2-114">5</span><span class="sxs-lookup"><span data-stu-id="086e2-114">5</span></span>|<span data-ttu-id="086e2-115">プッシュ</span><span class="sxs-lookup"><span data-stu-id="086e2-115">Push</span></span>|<span data-ttu-id="086e2-116">5</span><span class="sxs-lookup"><span data-stu-id="086e2-116">5</span></span>|  
|<span data-ttu-id="086e2-117">10</span><span class="sxs-lookup"><span data-stu-id="086e2-117">10</span></span>|<span data-ttu-id="086e2-118">プッシュ</span><span class="sxs-lookup"><span data-stu-id="086e2-118">Push</span></span>|<span data-ttu-id="086e2-119">5, 10</span><span class="sxs-lookup"><span data-stu-id="086e2-119">5, 10</span></span>|  
|<span data-ttu-id="086e2-120">2</span><span class="sxs-lookup"><span data-stu-id="086e2-120">2</span></span>|<span data-ttu-id="086e2-121">プッシュ</span><span class="sxs-lookup"><span data-stu-id="086e2-121">Push</span></span>|<span data-ttu-id="086e2-122">5, 10, 2</span><span class="sxs-lookup"><span data-stu-id="086e2-122">5, 10, 2</span></span>|  
|-|<span data-ttu-id="086e2-123">減算</span><span class="sxs-lookup"><span data-stu-id="086e2-123">Subtract</span></span>|<span data-ttu-id="086e2-124">5, 8</span><span class="sxs-lookup"><span data-stu-id="086e2-124">5, 8</span></span>|  
|+|<span data-ttu-id="086e2-125">[追加]</span><span class="sxs-lookup"><span data-stu-id="086e2-125">Add</span></span>|<span data-ttu-id="086e2-126">13</span><span class="sxs-lookup"><span data-stu-id="086e2-126">13</span></span>|  
  
 <span data-ttu-id="086e2-127">RPN システムで文字列連結操作がサポートされると仮定した場合、次の式を評価することもできます。</span><span class="sxs-lookup"><span data-stu-id="086e2-127">Assuming the RPN system supported the string concatenate operation, you could also evaluate the expression</span></span>  
  
 `"The quick brown " + "fox " + "jumped over the lazy " + "dog."`  
  
 <span data-ttu-id="086e2-128">この式を同等の RPN 表記法に変換すると次のようになります。</span><span class="sxs-lookup"><span data-stu-id="086e2-128">Converting this to the equivalent RPN notation yields:</span></span>  
  
 `"The quick brown " "fox " "jumped over the lazy " "dog" + + +`  
  
 <span data-ttu-id="086e2-129">この式は、次のように評価されます。</span><span class="sxs-lookup"><span data-stu-id="086e2-129">This would be evaluated as follows:</span></span>  
  
|<span data-ttu-id="086e2-130">入力</span><span class="sxs-lookup"><span data-stu-id="086e2-130">Input</span></span>|<span data-ttu-id="086e2-131">操作</span><span class="sxs-lookup"><span data-stu-id="086e2-131">Operation</span></span>|<span data-ttu-id="086e2-132">スタック</span><span class="sxs-lookup"><span data-stu-id="086e2-132">Stack</span></span>|  
|-----------|---------------|-----------|  
|<span data-ttu-id="086e2-133">"The quick brown"</span><span class="sxs-lookup"><span data-stu-id="086e2-133">"The quick brown"</span></span>|<span data-ttu-id="086e2-134">プッシュ</span><span class="sxs-lookup"><span data-stu-id="086e2-134">Push</span></span>|<span data-ttu-id="086e2-135">"クイック brown"</span><span class="sxs-lookup"><span data-stu-id="086e2-135">"The quick brown "</span></span>|  
|<span data-ttu-id="086e2-136">"fox"</span><span class="sxs-lookup"><span data-stu-id="086e2-136">"fox"</span></span>|<span data-ttu-id="086e2-137">プッシュ</span><span class="sxs-lookup"><span data-stu-id="086e2-137">Push</span></span>|<span data-ttu-id="086e2-138">"The quick brown ", "fox "</span><span class="sxs-lookup"><span data-stu-id="086e2-138">"The quick brown ", "fox "</span></span>|  
|<span data-ttu-id="086e2-139">"jumped over the lazy"</span><span class="sxs-lookup"><span data-stu-id="086e2-139">"jumped over the lazy"</span></span>|<span data-ttu-id="086e2-140">プッシュ</span><span class="sxs-lookup"><span data-stu-id="086e2-140">Push</span></span>|<span data-ttu-id="086e2-141">"The quick brown ", "fox ", "jumped over the lazy "</span><span class="sxs-lookup"><span data-stu-id="086e2-141">"The quick brown ", "fox ", "jumped over the lazy "</span></span>|  
|<span data-ttu-id="086e2-142">"dog."</span><span class="sxs-lookup"><span data-stu-id="086e2-142">"dog."</span></span>|<span data-ttu-id="086e2-143">プッシュ</span><span class="sxs-lookup"><span data-stu-id="086e2-143">Push</span></span>|<span data-ttu-id="086e2-144">"The quick brown ", "fox ", "jumped over the lazy ", "dog."</span><span class="sxs-lookup"><span data-stu-id="086e2-144">"The quick brown ", "fox ", "jumped over the lazy ", "dog."</span></span>|  
|+|<span data-ttu-id="086e2-145">連結</span><span class="sxs-lookup"><span data-stu-id="086e2-145">Concatenate</span></span>|<span data-ttu-id="086e2-146">"The quick brown ", "fox ", "jumped over the lazy dog."</span><span class="sxs-lookup"><span data-stu-id="086e2-146">"The quick brown ", "fox ", "jumped over the lazy dog."</span></span>|  
|+|<span data-ttu-id="086e2-147">連結</span><span class="sxs-lookup"><span data-stu-id="086e2-147">Concatenate</span></span>|<span data-ttu-id="086e2-148">"The quick brown ", "fox jumped over the lazy dog."</span><span class="sxs-lookup"><span data-stu-id="086e2-148">"The quick brown ", "fox jumped over the lazy dog."</span></span>|  
|+|<span data-ttu-id="086e2-149">連結</span><span class="sxs-lookup"><span data-stu-id="086e2-149">Concatenate</span></span>|<span data-ttu-id="086e2-150">"The quick brown fox jumped over the lazy dog."</span><span class="sxs-lookup"><span data-stu-id="086e2-150">"The quick brown fox jumped over the lazy dog."</span></span>|  
  
 <span data-ttu-id="086e2-151">この例でわかるように、比較、ブール演算、関与する演算に適した値を取得するカスタム操作など、任意の数の操作をサポートできます。</span><span class="sxs-lookup"><span data-stu-id="086e2-151">As you can see, an arbitrary number of operations can be supported, including comparison, Boolean operations, and custom operations that retrieve values appropriate for the operations in which they participate.</span></span> <span data-ttu-id="086e2-152">スタックに値が累積され、個々の操作に従ってプッシュまたはポップされます。</span><span class="sxs-lookup"><span data-stu-id="086e2-152">Values accumulate on the stack and are pushed and popped according to individual operations.</span></span>  
  
## <a name="reverse-polish-notation-in-the-interceptor-configuration-file"></a><span data-ttu-id="086e2-153">インターセプタ構成ファイル内での逆ポーランド表記法</span><span class="sxs-lookup"><span data-stu-id="086e2-153">Reverse Polish Notation in the Interceptor Configuration File</span></span>  
 <span data-ttu-id="086e2-154">2 つの式で作成、インターセプター構成ファイル: 式とデータ式をフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="086e2-154">You will write two kinds of expressions in the interceptor configuration file: filter expressions and data expressions.</span></span> <span data-ttu-id="086e2-155">フィルタ式は RPN 式の結果を処理してブール値 `true` または `false` を返すのに対し、データ式はスタック上の単一の値を処理します。</span><span class="sxs-lookup"><span data-stu-id="086e2-155">Filter expressions expect the result of the RPN expression to be a Boolean `true` or `false` while data expressions expect a single value on the stack.</span></span>  
  
### <a name="filter-expressions"></a><span data-ttu-id="086e2-156">フィルタ式</span><span class="sxs-lookup"><span data-stu-id="086e2-156">Filter Expressions</span></span>  
 <span data-ttu-id="086e2-157">フィルタ式はブール値 `true` または `false` を評価し、特定のイベントを識別して WF アプリケーションまたは WFC アプリケーションを追跡するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="086e2-157">Filter expressions evaluate to Boolean `true` or `false` and are used to identify a specific event to track in the WF or WFC application.</span></span> <span data-ttu-id="086e2-158">WF アプリケーションでは、一般にアクティビティ名とイベントに基づいてフィルタ処理します。</span><span class="sxs-lookup"><span data-stu-id="086e2-158">In WF applications, it is common to filter based on activity name and event.</span></span> <span data-ttu-id="086e2-159">たとえばを選択することがあります、 **FoodAndDrinksPolicy**アクティビティであるときに**Closed**です。</span><span class="sxs-lookup"><span data-stu-id="086e2-159">For example, you may want to select the **FoodAndDrinksPolicy** activity when it is **Closed**.</span></span> <span data-ttu-id="086e2-160">WF 操作を使用すると、フィルタを次のように表現できます。</span><span class="sxs-lookup"><span data-stu-id="086e2-160">Using WF operations, you could express the filter as:</span></span>  
  
 `(GetActivityName = "FoodAndDrinksPolicy") && (GetActivityEvent = "Closed")`  
  
 <span data-ttu-id="086e2-161">この式を RPN に変換すると次のようになります。</span><span class="sxs-lookup"><span data-stu-id="086e2-161">Converting this to RPN yields:</span></span>  
  
 `GetActivityName "FoodAndDrinksPolicy" == GetActivityEvent "Closed" == &&`  
  
 <span data-ttu-id="086e2-162">この式をインターセプタ構成ファイル用の同等の式に変換すると、次の XML になります。</span><span class="sxs-lookup"><span data-stu-id="086e2-162">Converting this expression to the equivalent expression for the interceptor configuration file results in the following XML:</span></span>  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityName"/>  
    <ic:Operation Name="Constant">  
      <ic:Argument>FoodAndDrinksPolicy</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals"/>  
    <wf:Operation Name="GetActivityEvent"/>  
    <ic:Operation Name="Constant">  
      <ic:Argument>Closed</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals"/>  
    <ic:Operation Name="And"/>  
  </ic:Expression>  
</ic:Filter>  
```  
  
 <span data-ttu-id="086e2-163">最後に、この式の評価と仮定すると次のように**GetActivityName** "dessertpolicy"と**GetActivityEvent** "Closed"が返されます。</span><span class="sxs-lookup"><span data-stu-id="086e2-163">Finally, this expression would be evaluated as follows assuming **GetActivityName** returned "DessertPolicy" and **GetActivityEvent** returned "Closed":</span></span>  
  
|<span data-ttu-id="086e2-164">入力</span><span class="sxs-lookup"><span data-stu-id="086e2-164">Input</span></span>|<span data-ttu-id="086e2-165">操作</span><span class="sxs-lookup"><span data-stu-id="086e2-165">Operation</span></span>|<span data-ttu-id="086e2-166">スタック</span><span class="sxs-lookup"><span data-stu-id="086e2-166">Stack</span></span>|  
|-----------|---------------|-----------|  
||<span data-ttu-id="086e2-167">GetActivityName</span><span class="sxs-lookup"><span data-stu-id="086e2-167">GetActivityName</span></span>|<span data-ttu-id="086e2-168">"DessertPolicy"</span><span class="sxs-lookup"><span data-stu-id="086e2-168">"DessertPolicy"</span></span>|  
|<span data-ttu-id="086e2-169">"FoodAndDrinksPolicy"</span><span class="sxs-lookup"><span data-stu-id="086e2-169">"FoodAndDrinksPolicy"</span></span>|<span data-ttu-id="086e2-170">定数</span><span class="sxs-lookup"><span data-stu-id="086e2-170">Constant</span></span>|<span data-ttu-id="086e2-171">"DessertPolicy", "FoodAndDrinksPolicy"</span><span class="sxs-lookup"><span data-stu-id="086e2-171">"DessertPolicy", "FoodAndDrinksPolicy"</span></span>|  
|<span data-ttu-id="086e2-172">[等しい]</span><span class="sxs-lookup"><span data-stu-id="086e2-172">Equals</span></span>|<span data-ttu-id="086e2-173">比較</span><span class="sxs-lookup"><span data-stu-id="086e2-173">Comparison</span></span>|<span data-ttu-id="086e2-174">False</span><span class="sxs-lookup"><span data-stu-id="086e2-174">False</span></span>|  
||<span data-ttu-id="086e2-175">GetActivityEvent</span><span class="sxs-lookup"><span data-stu-id="086e2-175">GetActivityEvent</span></span>|<span data-ttu-id="086e2-176">False, Closed</span><span class="sxs-lookup"><span data-stu-id="086e2-176">False, Closed</span></span>|  
|<span data-ttu-id="086e2-177">"Closed"</span><span class="sxs-lookup"><span data-stu-id="086e2-177">"Closed"</span></span>|<span data-ttu-id="086e2-178">定数</span><span class="sxs-lookup"><span data-stu-id="086e2-178">Constant</span></span>|<span data-ttu-id="086e2-179">False, "Closed", "Closed"</span><span class="sxs-lookup"><span data-stu-id="086e2-179">False, "Closed", "Closed"</span></span>|  
|<span data-ttu-id="086e2-180">[等しい]</span><span class="sxs-lookup"><span data-stu-id="086e2-180">Equals</span></span>|<span data-ttu-id="086e2-181">比較</span><span class="sxs-lookup"><span data-stu-id="086e2-181">Comparison</span></span>|<span data-ttu-id="086e2-182">False, True</span><span class="sxs-lookup"><span data-stu-id="086e2-182">False, True</span></span>|  
|<span data-ttu-id="086e2-183">And</span><span class="sxs-lookup"><span data-stu-id="086e2-183">And</span></span>|<span data-ttu-id="086e2-184">論理と</span><span class="sxs-lookup"><span data-stu-id="086e2-184">Logical And</span></span>|<span data-ttu-id="086e2-185">False</span><span class="sxs-lookup"><span data-stu-id="086e2-185">False</span></span>|  
  
 <span data-ttu-id="086e2-186">スタックに残される値はブール値 `False` です。</span><span class="sxs-lookup"><span data-stu-id="086e2-186">The value left on the stack is Boolean `False`.</span></span> <span data-ttu-id="086e2-187">したがって、対応するイベントは発生しません。</span><span class="sxs-lookup"><span data-stu-id="086e2-187">This will cause the corresponding event to not fire.</span></span> <span data-ttu-id="086e2-188">アクティビティ名が "FoodAndDrinksPolicy" であった場合、この式はブール値 `True` として評価されます。</span><span class="sxs-lookup"><span data-stu-id="086e2-188">If the activity name were "FoodAndDrinksPolicy" then it would have evaluated to Boolean `True`.</span></span>  
  
 <span data-ttu-id="086e2-189">WCF 操作 `GetEndpointName` および `GetOperationName` を使用すると、同様の評価を行う式を作成できます。</span><span class="sxs-lookup"><span data-stu-id="086e2-189">You can construct a similar expression (with a similar evaluation) by using the WCF operations `GetEndpointName` and `GetOperationName`.</span></span>  
  
### <a name="data-expressions"></a><span data-ttu-id="086e2-190">データ式</span><span class="sxs-lookup"><span data-stu-id="086e2-190">Data Expressions</span></span>  
 <span data-ttu-id="086e2-191">データ式は、単一の文字列データ値を定義するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="086e2-191">Data expressions are used to define a single string data value.</span></span> <span data-ttu-id="086e2-192">データ式は、`Filter` 要素で囲まれていない任意の式です。</span><span class="sxs-lookup"><span data-stu-id="086e2-192">A data expression is any expression that is not enclosed by a `Filter` element.</span></span> <span data-ttu-id="086e2-193">データ式は、`OnEvent` 要素の `CorrelationID`、`ContinuationToken`、`Reference`、および `Update` で使用されます。</span><span class="sxs-lookup"><span data-stu-id="086e2-193">Data expressions are used by the `OnEvent` elements `CorrelationID`, `ContinuationToken`, `Reference`, and `Update`.</span></span>  
  
 <span data-ttu-id="086e2-194">これは、BAM アクティビティ データベースをラベル付きタイム スタンプで更新するための一般的な要件です。</span><span class="sxs-lookup"><span data-stu-id="086e2-194">It is a common requirement to update the BAM activity database with a labeled time stamp.</span></span> <span data-ttu-id="086e2-195">イベントの設定として書式設定文字列が開始された時刻をキャプチャするたとえば、"開始: \<EventTime >"です。</span><span class="sxs-lookup"><span data-stu-id="086e2-195">For example, you might want to capture the time an event starts with a string formatted as "Start: \<EventTime>".</span></span> <span data-ttu-id="086e2-196">これを行うには、次のような式を使用する必要があります (+ は連結を表します)。</span><span class="sxs-lookup"><span data-stu-id="086e2-196">To do this, you need to use an expression similar to the following (where + represents concatenation):</span></span>  
  
 `"Start: " + GetContextProperty(EventTime)`  
  
 <span data-ttu-id="086e2-197">この式を RPN に変換すると次のようになります。</span><span class="sxs-lookup"><span data-stu-id="086e2-197">Converting this to RPN yields:</span></span>  
  
 `"Start: " GetContextProperty(EventTime) +`  
  
 <span data-ttu-id="086e2-198">この式をインターセプタ構成ファイルの `Update` 要素用の同等の式に変換すると、次の XML になります。</span><span class="sxs-lookup"><span data-stu-id="086e2-198">Converting this expression to the equivalent expression for an `Update` element in the interceptor configuration file results in the following XML:</span></span>  
  
```  
<ic:Update DataItemName="NewOrderCreateTime" Type="NVARCHAR">  
  <ic:Expression>  
    <ic:Operation Name="Constant">  
      <ic:Argument>Start:</ic:Argument>  
    </ic:Operation>  
    <wf:Operation Name="GetContextProperty">  
      <wf:Argument>EventTime</wf:Argument>  
    </wf:Operation>  
    <ic:Operation Name="Concatenate" />  
  </ic:Expression>  
</ic:Update>  
```  
  
 <span data-ttu-id="086e2-199">次の表は、イベント時刻が "12:00 PM" の場合に、この式がどのように解釈されるかを示しています。</span><span class="sxs-lookup"><span data-stu-id="086e2-199">The following table shows how this expression would be interpreted if the event time was "12:00 PM".</span></span>  
  
|<span data-ttu-id="086e2-200">入力</span><span class="sxs-lookup"><span data-stu-id="086e2-200">Input</span></span>|<span data-ttu-id="086e2-201">操作</span><span class="sxs-lookup"><span data-stu-id="086e2-201">Operation</span></span>|<span data-ttu-id="086e2-202">スタック</span><span class="sxs-lookup"><span data-stu-id="086e2-202">Stack</span></span>|  
|-----------|---------------|-----------|  
|<span data-ttu-id="086e2-203">"を開始します"。</span><span class="sxs-lookup"><span data-stu-id="086e2-203">"Start: "</span></span>|<span data-ttu-id="086e2-204">定数</span><span class="sxs-lookup"><span data-stu-id="086e2-204">Constant</span></span>|<span data-ttu-id="086e2-205">"を開始します"。</span><span class="sxs-lookup"><span data-stu-id="086e2-205">"Start: "</span></span>|  
|<span data-ttu-id="086e2-206">GetContextProperty(EventTime)</span><span class="sxs-lookup"><span data-stu-id="086e2-206">GetContextProperty(EventTime)</span></span>|<span data-ttu-id="086e2-207">プッシュ</span><span class="sxs-lookup"><span data-stu-id="086e2-207">Push</span></span>|<span data-ttu-id="086e2-208">"開始:"、"2006-09-27T12:00:34.000Z"</span><span class="sxs-lookup"><span data-stu-id="086e2-208">"Start: ", "2006-09-27T12:00:34.000Z"</span></span>|  
|<span data-ttu-id="086e2-209">連結</span><span class="sxs-lookup"><span data-stu-id="086e2-209">Concatenate</span></span>|<span data-ttu-id="086e2-210">連結</span><span class="sxs-lookup"><span data-stu-id="086e2-210">Concatenate</span></span>|<span data-ttu-id="086e2-211">"開始: 2006-09-27T12:00:34.000Z"</span><span class="sxs-lookup"><span data-stu-id="086e2-211">"Start: 2006-09-27T12:00:34.000Z"</span></span>|  
  
 <span data-ttu-id="086e2-212">更新コマンドで使用される値になります"開始: 2006-09-27T12:00:34.000Z"です。</span><span class="sxs-lookup"><span data-stu-id="086e2-212">The value used by the update command would be "Start: 2006-09-27T12:00:34.000Z".</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="086e2-213">データ式では比較演算 "And" および "Equals" は使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="086e2-213">Do not use the comparison operations "And" or "Equals" in data expressions.</span></span> <span data-ttu-id="086e2-214">この演算を使用すると、インターセプタ構成ファイルを展開するときにエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="086e2-214">If you do, you will receive an error when deploying your interceptor configuration file.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="086e2-215">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="086e2-215">In This Section</span></span>  
 [<span data-ttu-id="086e2-216">インターセプタの操作</span><span class="sxs-lookup"><span data-stu-id="086e2-216">Interceptor Operations</span></span>](../core/interceptor-operations.md)  
  
## <a name="see-also"></a><span data-ttu-id="086e2-217">参照</span><span class="sxs-lookup"><span data-stu-id="086e2-217">See Also</span></span>  
 [<span data-ttu-id="086e2-218">インターセプタ構成ファイルの構造</span><span class="sxs-lookup"><span data-stu-id="086e2-218">Structure of an Interceptor Configuration File</span></span>](../core/structure-of-an-interceptor-configuration-file.md)