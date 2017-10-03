---
title: "式における演算子の使用 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- orchestrations, operators
- XLANG/s, operators
- orchestrations, XLANG/s
ms.assetid: f0948ce2-c508-48aa-af79-d207f577b22f
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 155aad11ecddd021b8e16892b5a5294087fedd4d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="using-operators-in-expressions"></a><span data-ttu-id="1d9ff-102">式における演算子の使用</span><span class="sxs-lookup"><span data-stu-id="1d9ff-102">Using Operators in Expressions</span></span>
<span data-ttu-id="1d9ff-103">オーケストレーションの式では次の XLANG/s 演算子を使用できます。</span><span class="sxs-lookup"><span data-stu-id="1d9ff-103">The following XLANG/s operators are available for use in orchestration expressions.</span></span> <span data-ttu-id="1d9ff-104">C# の対応する演算子の機能にほぼ準拠しています。</span><span class="sxs-lookup"><span data-stu-id="1d9ff-104">They adhere closely to the functionality of the corresponding operators in C#.</span></span>  
  
|<span data-ttu-id="1d9ff-105">演算子</span><span class="sxs-lookup"><span data-stu-id="1d9ff-105">Operator</span></span>|<span data-ttu-id="1d9ff-106">Description</span><span class="sxs-lookup"><span data-stu-id="1d9ff-106">Description</span></span>|<span data-ttu-id="1d9ff-107">例</span><span class="sxs-lookup"><span data-stu-id="1d9ff-107">Example</span></span>|  
|--------------|-----------------|-------------|  
|<span data-ttu-id="1d9ff-108">checked()</span><span class="sxs-lookup"><span data-stu-id="1d9ff-108">checked()</span></span>|<span data-ttu-id="1d9ff-109">算術オーバーフローでエラーを発生</span><span class="sxs-lookup"><span data-stu-id="1d9ff-109">raise error on arithmetic overflow</span></span>|<span data-ttu-id="1d9ff-110">checked(x = y * 1000)</span><span class="sxs-lookup"><span data-stu-id="1d9ff-110">checked(x = y * 1000)</span></span>|  
|<span data-ttu-id="1d9ff-111">unchecked()</span><span class="sxs-lookup"><span data-stu-id="1d9ff-111">unchecked()</span></span>|<span data-ttu-id="1d9ff-112">算術オーバーフローを無視します。</span><span class="sxs-lookup"><span data-stu-id="1d9ff-112">ignore arithmetic overflow</span></span>|<span data-ttu-id="1d9ff-113">unchecked(x = y * 1000)</span><span class="sxs-lookup"><span data-stu-id="1d9ff-113">unchecked(x = y * 1000)</span></span>|  
|<span data-ttu-id="1d9ff-114">新機能</span><span class="sxs-lookup"><span data-stu-id="1d9ff-114">new</span></span>|<span data-ttu-id="1d9ff-115">クラスのインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="1d9ff-115">create an instance of a class</span></span>|<span data-ttu-id="1d9ff-116">myObject = new MyClass;</span><span class="sxs-lookup"><span data-stu-id="1d9ff-116">myObject = new MyClass;</span></span>|  
|<span data-ttu-id="1d9ff-117">typeof</span><span class="sxs-lookup"><span data-stu-id="1d9ff-117">typeof</span></span>|<span data-ttu-id="1d9ff-118">型の取得</span><span class="sxs-lookup"><span data-stu-id="1d9ff-118">Type retrieval</span></span>|<span data-ttu-id="1d9ff-119">myMapType = typeof(myMap)</span><span class="sxs-lookup"><span data-stu-id="1d9ff-119">myMapType = typeof(myMap)</span></span>|  
|<span data-ttu-id="1d9ff-120">succeeded()</span><span class="sxs-lookup"><span data-stu-id="1d9ff-120">succeeded()</span></span>|<span data-ttu-id="1d9ff-121">トランザクションのスコープまたはオーケストレーションが正常に完了のテスト</span><span class="sxs-lookup"><span data-stu-id="1d9ff-121">test for successful completion of transactional scope or orchestration</span></span>|<span data-ttu-id="1d9ff-122">成功した (\<子トランザクションの現在のスコープまたはサービスのトランザクション ID >)</span><span class="sxs-lookup"><span data-stu-id="1d9ff-122">succeeded(\<transaction ID for child transaction of current scope or service>)</span></span>|  
|<span data-ttu-id="1d9ff-123">存在する</span><span class="sxs-lookup"><span data-stu-id="1d9ff-123">exists</span></span>|<span data-ttu-id="1d9ff-124">メッセージ コンテキスト プロパティの存在をテスト</span><span class="sxs-lookup"><span data-stu-id="1d9ff-124">test for the existence of a message context property</span></span>|<span data-ttu-id="1d9ff-125">BTS.RetryCount exists Message_In</span><span class="sxs-lookup"><span data-stu-id="1d9ff-125">BTS.RetryCount exists Message_In</span></span>|  
|+|<span data-ttu-id="1d9ff-126">単項プラス</span><span class="sxs-lookup"><span data-stu-id="1d9ff-126">unary plus</span></span>|<span data-ttu-id="1d9ff-127">+(int x)</span><span class="sxs-lookup"><span data-stu-id="1d9ff-127">+(int x)</span></span>|  
|-|<span data-ttu-id="1d9ff-128">単項マイナス</span><span class="sxs-lookup"><span data-stu-id="1d9ff-128">unary minus</span></span>|<span data-ttu-id="1d9ff-129">-(int x)</span><span class="sxs-lookup"><span data-stu-id="1d9ff-129">-(int x)</span></span>|  
|<span data-ttu-id="1d9ff-130">!</span><span class="sxs-lookup"><span data-stu-id="1d9ff-130">!</span></span>|<span data-ttu-id="1d9ff-131">論理否定</span><span class="sxs-lookup"><span data-stu-id="1d9ff-131">logical negation</span></span>|<span data-ttu-id="1d9ff-132">!myBool</span><span class="sxs-lookup"><span data-stu-id="1d9ff-132">!myBool</span></span>|  
|~|<span data-ttu-id="1d9ff-133">ビットごとの補数</span><span class="sxs-lookup"><span data-stu-id="1d9ff-133">bitwise complement</span></span>|<span data-ttu-id="1d9ff-134">x = ~y</span><span class="sxs-lookup"><span data-stu-id="1d9ff-134">x = ~y</span></span>|  
|<span data-ttu-id="1d9ff-135">()</span><span class="sxs-lookup"><span data-stu-id="1d9ff-135">()</span></span>|<span data-ttu-id="1d9ff-136">キャスト</span><span class="sxs-lookup"><span data-stu-id="1d9ff-136">cast</span></span>|<span data-ttu-id="1d9ff-137">(bool) myInt</span><span class="sxs-lookup"><span data-stu-id="1d9ff-137">(bool) myInt</span></span>|  
|*|<span data-ttu-id="1d9ff-138">times</span><span class="sxs-lookup"><span data-stu-id="1d9ff-138">times</span></span>|<span data-ttu-id="1d9ff-139">Weight = MyMsg.numOrders * 20</span><span class="sxs-lookup"><span data-stu-id="1d9ff-139">Weight = MyMsg.numOrders * 20</span></span>|  
|/|<span data-ttu-id="1d9ff-140">割った値</span><span class="sxs-lookup"><span data-stu-id="1d9ff-140">divided by</span></span>|<span data-ttu-id="1d9ff-141">x / y</span><span class="sxs-lookup"><span data-stu-id="1d9ff-141">x / y</span></span>|  
|+|<span data-ttu-id="1d9ff-142">加算</span><span class="sxs-lookup"><span data-stu-id="1d9ff-142">plus</span></span>|<span data-ttu-id="1d9ff-143">x + y</span><span class="sxs-lookup"><span data-stu-id="1d9ff-143">x + y</span></span>|  
|-|<span data-ttu-id="1d9ff-144">負符号</span><span class="sxs-lookup"><span data-stu-id="1d9ff-144">minus</span></span>|<span data-ttu-id="1d9ff-145">x - y</span><span class="sxs-lookup"><span data-stu-id="1d9ff-145">x - y</span></span>|  
|<<|<span data-ttu-id="1d9ff-146">左シフト</span><span class="sxs-lookup"><span data-stu-id="1d9ff-146">shift left</span></span>|<span data-ttu-id="1d9ff-147">x <\< 2</span><span class="sxs-lookup"><span data-stu-id="1d9ff-147">x <\< 2</span></span>|  
|>>|<span data-ttu-id="1d9ff-148">右シフトします。</span><span class="sxs-lookup"><span data-stu-id="1d9ff-148">shift right</span></span>|<span data-ttu-id="1d9ff-149">x >> 2</span><span class="sxs-lookup"><span data-stu-id="1d9ff-149">x >> 2</span></span>|  
|<|<span data-ttu-id="1d9ff-150">小さい</span><span class="sxs-lookup"><span data-stu-id="1d9ff-150">less than</span></span>|<span data-ttu-id="1d9ff-151">場合 (MyMsg.numOrders \< 10).</span><span class="sxs-lookup"><span data-stu-id="1d9ff-151">If (MyMsg.numOrders \< 10)...</span></span>|  
|>|<span data-ttu-id="1d9ff-152">大きい</span><span class="sxs-lookup"><span data-stu-id="1d9ff-152">greater than</span></span>|<span data-ttu-id="1d9ff-153">場合 (MyMsg.numOrders > 10).</span><span class="sxs-lookup"><span data-stu-id="1d9ff-153">If (MyMsg.numOrders > 10)...</span></span>|  
|<=|<span data-ttu-id="1d9ff-154">以下に</span><span class="sxs-lookup"><span data-stu-id="1d9ff-154">less than or equal to</span></span>|<span data-ttu-id="1d9ff-155">場合 (MyMsg.numOrders \<= 10).</span><span class="sxs-lookup"><span data-stu-id="1d9ff-155">If (MyMsg.numOrders \<= 10)...</span></span>|  
|>=|<span data-ttu-id="1d9ff-156">大きいまたは等しい</span><span class="sxs-lookup"><span data-stu-id="1d9ff-156">greater than or equal to</span></span>|<span data-ttu-id="1d9ff-157">場合 (MyMsg.numOrders > = 10).</span><span class="sxs-lookup"><span data-stu-id="1d9ff-157">If (MyMsg.numOrders >= 10)...</span></span>|  
|==|<span data-ttu-id="1d9ff-158">一致します。</span><span class="sxs-lookup"><span data-stu-id="1d9ff-158">equal to</span></span>|<span data-ttu-id="1d9ff-159">If (MyMsg.numOrders == 10)...</span><span class="sxs-lookup"><span data-stu-id="1d9ff-159">If (MyMsg.numOrders == 10)...</span></span>|  
|<span data-ttu-id="1d9ff-160">!=</span><span class="sxs-lookup"><span data-stu-id="1d9ff-160">!=</span></span>|<span data-ttu-id="1d9ff-161">等しくないです。</span><span class="sxs-lookup"><span data-stu-id="1d9ff-161">not equal to</span></span>|<span data-ttu-id="1d9ff-162">If (MyMsg.numOrders != 10)...</span><span class="sxs-lookup"><span data-stu-id="1d9ff-162">If (MyMsg.numOrders != 10)...</span></span>|  
|&|<span data-ttu-id="1d9ff-163">クエリと</span><span class="sxs-lookup"><span data-stu-id="1d9ff-163">and</span></span>|<span data-ttu-id="1d9ff-164">If (myByte & 255)...</span><span class="sxs-lookup"><span data-stu-id="1d9ff-164">If (myByte & 255)...</span></span>|  
|^|<span data-ttu-id="1d9ff-165">排他的 OR</span><span class="sxs-lookup"><span data-stu-id="1d9ff-165">exclusive or</span></span>|<span data-ttu-id="1d9ff-166">If (myByte ^ 1)...</span><span class="sxs-lookup"><span data-stu-id="1d9ff-166">If (myByte ^ 1)...</span></span>|  
|<span data-ttu-id="1d9ff-167">&#124;</span><span class="sxs-lookup"><span data-stu-id="1d9ff-167">&#124;</span></span>|<span data-ttu-id="1d9ff-168">または</span><span class="sxs-lookup"><span data-stu-id="1d9ff-168">or</span></span>|<span data-ttu-id="1d9ff-169">場合 (myByte (& a) #124; 1).</span><span class="sxs-lookup"><span data-stu-id="1d9ff-169">If (myByte &#124; 1)...</span></span>|  
|&&|<span data-ttu-id="1d9ff-170">条件 AND</span><span class="sxs-lookup"><span data-stu-id="1d9ff-170">conditional and</span></span>|<span data-ttu-id="1d9ff-171">If (MyMsg.numOrders > 10) && (MyMsg.numOrders < 100)</span><span class="sxs-lookup"><span data-stu-id="1d9ff-171">If (MyMsg.numOrders > 10) && (MyMsg.numOrders < 100)</span></span>|  
|<span data-ttu-id="1d9ff-172">&#124;&#124;</span><span class="sxs-lookup"><span data-stu-id="1d9ff-172">&#124;&#124;</span></span>|<span data-ttu-id="1d9ff-173">条件 OR</span><span class="sxs-lookup"><span data-stu-id="1d9ff-173">conditional or</span></span>|<span data-ttu-id="1d9ff-174">場合 (MyMsg.numOrders \< 10) (& m); #124 & #124 です。(MyMsg.numOrders > 100)</span><span class="sxs-lookup"><span data-stu-id="1d9ff-174">If (MyMsg.numOrders \< 10) &#124;&#124; (MyMsg.numOrders > 100)</span></span>|  
|//|<span data-ttu-id="1d9ff-175">コメントを付ける</span><span class="sxs-lookup"><span data-stu-id="1d9ff-175">commenting</span></span>|<span data-ttu-id="1d9ff-176">//これはコメントです。</span><span class="sxs-lookup"><span data-stu-id="1d9ff-176">//This is the comment</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="1d9ff-177">一般式とフィルター式で使用されるとが異なるルール、**受信**図形です。</span><span class="sxs-lookup"><span data-stu-id="1d9ff-177">The rules differ between general expressions and filter expressions that are used with the **Receive** shape.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d9ff-178">参照</span><span class="sxs-lookup"><span data-stu-id="1d9ff-178">See Also</span></span>  
 [<span data-ttu-id="1d9ff-179">受信メッセージ図形にフィルターを使用します。</span><span class="sxs-lookup"><span data-stu-id="1d9ff-179">Using Filters With the Receive Message Shape</span></span>](../core/using-filters-with-the-receive-message-shape.md)