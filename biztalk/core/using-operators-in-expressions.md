---
title: 式における演算子の使用 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, operators
- XLANG/s, operators
- orchestrations, XLANG/s
ms.assetid: f0948ce2-c508-48aa-af79-d207f577b22f
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5aec9ed6ebecb0b151dbfe9d5c09707b954fdf45
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25974304"
---
# <a name="using-operators-in-expressions"></a><span data-ttu-id="a255f-102">式における演算子の使用</span><span class="sxs-lookup"><span data-stu-id="a255f-102">Using Operators in Expressions</span></span>
<span data-ttu-id="a255f-103">オーケストレーションの式では次の XLANG/s 演算子を使用できます。</span><span class="sxs-lookup"><span data-stu-id="a255f-103">The following XLANG/s operators are available for use in orchestration expressions.</span></span> <span data-ttu-id="a255f-104">C# の対応する演算子の機能にほぼ準拠しています。</span><span class="sxs-lookup"><span data-stu-id="a255f-104">They adhere closely to the functionality of the corresponding operators in C#.</span></span>  
  
|<span data-ttu-id="a255f-105">演算子</span><span class="sxs-lookup"><span data-stu-id="a255f-105">Operator</span></span>|<span data-ttu-id="a255f-106">Description</span><span class="sxs-lookup"><span data-stu-id="a255f-106">Description</span></span>|<span data-ttu-id="a255f-107">例</span><span class="sxs-lookup"><span data-stu-id="a255f-107">Example</span></span>|  
|--------------|-----------------|-------------|  
|<span data-ttu-id="a255f-108">checked()</span><span class="sxs-lookup"><span data-stu-id="a255f-108">checked()</span></span>|<span data-ttu-id="a255f-109">算術オーバーフローでエラーを発生</span><span class="sxs-lookup"><span data-stu-id="a255f-109">raise error on arithmetic overflow</span></span>|<span data-ttu-id="a255f-110">checked(x = y \* 1000)</span><span class="sxs-lookup"><span data-stu-id="a255f-110">checked(x = y \* 1000)</span></span>|  
|<span data-ttu-id="a255f-111">unchecked()</span><span class="sxs-lookup"><span data-stu-id="a255f-111">unchecked()</span></span>|<span data-ttu-id="a255f-112">算術オーバーフローを無視します。</span><span class="sxs-lookup"><span data-stu-id="a255f-112">ignore arithmetic overflow</span></span>|<span data-ttu-id="a255f-113">unchecked(x = y \* 1000)</span><span class="sxs-lookup"><span data-stu-id="a255f-113">unchecked(x = y \* 1000)</span></span>|  
|<span data-ttu-id="a255f-114">新機能</span><span class="sxs-lookup"><span data-stu-id="a255f-114">new</span></span>|<span data-ttu-id="a255f-115">クラスのインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="a255f-115">create an instance of a class</span></span>|<span data-ttu-id="a255f-116">myObject = new MyClass;</span><span class="sxs-lookup"><span data-stu-id="a255f-116">myObject = new MyClass;</span></span>|  
|<span data-ttu-id="a255f-117">typeof</span><span class="sxs-lookup"><span data-stu-id="a255f-117">typeof</span></span>|<span data-ttu-id="a255f-118">型の取得</span><span class="sxs-lookup"><span data-stu-id="a255f-118">Type retrieval</span></span>|<span data-ttu-id="a255f-119">myMapType = typeof(myMap)</span><span class="sxs-lookup"><span data-stu-id="a255f-119">myMapType = typeof(myMap)</span></span>|  
|<span data-ttu-id="a255f-120">succeeded()</span><span class="sxs-lookup"><span data-stu-id="a255f-120">succeeded()</span></span>|<span data-ttu-id="a255f-121">トランザクションのスコープまたはオーケストレーションが正常に完了のテスト</span><span class="sxs-lookup"><span data-stu-id="a255f-121">test for successful completion of transactional scope or orchestration</span></span>|<span data-ttu-id="a255f-122">成功した (\<子トランザクションの現在のスコープまたはサービスのトランザクション ID\>)</span><span class="sxs-lookup"><span data-stu-id="a255f-122">succeeded(\<transaction ID for child transaction of current scope or service\>)</span></span>|  
|<span data-ttu-id="a255f-123">存在する</span><span class="sxs-lookup"><span data-stu-id="a255f-123">exists</span></span>|<span data-ttu-id="a255f-124">メッセージ コンテキスト プロパティの存在をテスト</span><span class="sxs-lookup"><span data-stu-id="a255f-124">test for the existence of a message context property</span></span>|<span data-ttu-id="a255f-125">BTS.RetryCount exists Message_In</span><span class="sxs-lookup"><span data-stu-id="a255f-125">BTS.RetryCount exists Message_In</span></span>|  
|+|<span data-ttu-id="a255f-126">単項プラス</span><span class="sxs-lookup"><span data-stu-id="a255f-126">unary plus</span></span>|<span data-ttu-id="a255f-127">+(int x)</span><span class="sxs-lookup"><span data-stu-id="a255f-127">+(int x)</span></span>|  
|-|<span data-ttu-id="a255f-128">単項マイナス</span><span class="sxs-lookup"><span data-stu-id="a255f-128">unary minus</span></span>|<span data-ttu-id="a255f-129">-(int x)</span><span class="sxs-lookup"><span data-stu-id="a255f-129">-(int x)</span></span>|  
|<span data-ttu-id="a255f-130">!</span><span class="sxs-lookup"><span data-stu-id="a255f-130">!</span></span>|<span data-ttu-id="a255f-131">論理否定</span><span class="sxs-lookup"><span data-stu-id="a255f-131">logical negation</span></span>|<span data-ttu-id="a255f-132">!myBool</span><span class="sxs-lookup"><span data-stu-id="a255f-132">!myBool</span></span>|  
|~|<span data-ttu-id="a255f-133">ビットごとの補数</span><span class="sxs-lookup"><span data-stu-id="a255f-133">bitwise complement</span></span>|<span data-ttu-id="a255f-134">x = ~y</span><span class="sxs-lookup"><span data-stu-id="a255f-134">x = ~y</span></span>|  
|<span data-ttu-id="a255f-135">()</span><span class="sxs-lookup"><span data-stu-id="a255f-135">()</span></span>|<span data-ttu-id="a255f-136">キャスト</span><span class="sxs-lookup"><span data-stu-id="a255f-136">cast</span></span>|<span data-ttu-id="a255f-137">(bool) myInt</span><span class="sxs-lookup"><span data-stu-id="a255f-137">(bool) myInt</span></span>|  
|*|<span data-ttu-id="a255f-138">times</span><span class="sxs-lookup"><span data-stu-id="a255f-138">times</span></span>|<span data-ttu-id="a255f-139">Weight = MyMsg.numOrders \* 20</span><span class="sxs-lookup"><span data-stu-id="a255f-139">Weight = MyMsg.numOrders \* 20</span></span>|  
|/|<span data-ttu-id="a255f-140">割った値</span><span class="sxs-lookup"><span data-stu-id="a255f-140">divided by</span></span>|<span data-ttu-id="a255f-141">x / y</span><span class="sxs-lookup"><span data-stu-id="a255f-141">x / y</span></span>|  
|+|<span data-ttu-id="a255f-142">加算</span><span class="sxs-lookup"><span data-stu-id="a255f-142">plus</span></span>|<span data-ttu-id="a255f-143">x + y</span><span class="sxs-lookup"><span data-stu-id="a255f-143">x + y</span></span>|  
|-|<span data-ttu-id="a255f-144">負符号</span><span class="sxs-lookup"><span data-stu-id="a255f-144">minus</span></span>|<span data-ttu-id="a255f-145">x - y</span><span class="sxs-lookup"><span data-stu-id="a255f-145">x - y</span></span>|  
|<<|<span data-ttu-id="a255f-146">左シフト</span><span class="sxs-lookup"><span data-stu-id="a255f-146">shift left</span></span>|<span data-ttu-id="a255f-147">x << 2</span><span class="sxs-lookup"><span data-stu-id="a255f-147">x << 2</span></span>|  
|>>|<span data-ttu-id="a255f-148">右シフトします。</span><span class="sxs-lookup"><span data-stu-id="a255f-148">shift right</span></span>|<span data-ttu-id="a255f-149">x >> 2</span><span class="sxs-lookup"><span data-stu-id="a255f-149">x >> 2</span></span>|  
|<|<span data-ttu-id="a255f-150">小さい</span><span class="sxs-lookup"><span data-stu-id="a255f-150">less than</span></span>|<span data-ttu-id="a255f-151">If (MyMsg.numOrders < 10)...</span><span class="sxs-lookup"><span data-stu-id="a255f-151">If (MyMsg.numOrders < 10)...</span></span>|  
|>|<span data-ttu-id="a255f-152">大きい</span><span class="sxs-lookup"><span data-stu-id="a255f-152">greater than</span></span>|<span data-ttu-id="a255f-153">場合 (MyMsg.numOrders > 10).</span><span class="sxs-lookup"><span data-stu-id="a255f-153">If (MyMsg.numOrders > 10)...</span></span>|  
|<=|<span data-ttu-id="a255f-154">以下に</span><span class="sxs-lookup"><span data-stu-id="a255f-154">less than or equal to</span></span>|<span data-ttu-id="a255f-155">If (MyMsg.numOrders <= 10)...</span><span class="sxs-lookup"><span data-stu-id="a255f-155">If (MyMsg.numOrders <= 10)...</span></span>|  
|>=|<span data-ttu-id="a255f-156">大きいまたは等しい</span><span class="sxs-lookup"><span data-stu-id="a255f-156">greater than or equal to</span></span>|<span data-ttu-id="a255f-157">場合 (MyMsg.numOrders > = 10).</span><span class="sxs-lookup"><span data-stu-id="a255f-157">If (MyMsg.numOrders >= 10)...</span></span>|  
|==|<span data-ttu-id="a255f-158">一致します。</span><span class="sxs-lookup"><span data-stu-id="a255f-158">equal to</span></span>|<span data-ttu-id="a255f-159">If (MyMsg.numOrders == 10)...</span><span class="sxs-lookup"><span data-stu-id="a255f-159">If (MyMsg.numOrders == 10)...</span></span>|  
|<span data-ttu-id="a255f-160">!=</span><span class="sxs-lookup"><span data-stu-id="a255f-160">!=</span></span>|<span data-ttu-id="a255f-161">等しくないです。</span><span class="sxs-lookup"><span data-stu-id="a255f-161">not equal to</span></span>|<span data-ttu-id="a255f-162">If (MyMsg.numOrders != 10)...</span><span class="sxs-lookup"><span data-stu-id="a255f-162">If (MyMsg.numOrders != 10)...</span></span>|  
|&|<span data-ttu-id="a255f-163">クエリと</span><span class="sxs-lookup"><span data-stu-id="a255f-163">and</span></span>|<span data-ttu-id="a255f-164">If (myByte & 255)...</span><span class="sxs-lookup"><span data-stu-id="a255f-164">If (myByte & 255)...</span></span>|  
|^|<span data-ttu-id="a255f-165">排他的 OR</span><span class="sxs-lookup"><span data-stu-id="a255f-165">exclusive or</span></span>|<span data-ttu-id="a255f-166">If (myByte ^ 1)...</span><span class="sxs-lookup"><span data-stu-id="a255f-166">If (myByte ^ 1)...</span></span>|  
|<span data-ttu-id="a255f-167">&#124;</span><span class="sxs-lookup"><span data-stu-id="a255f-167">&#124;</span></span>|<span data-ttu-id="a255f-168">または</span><span class="sxs-lookup"><span data-stu-id="a255f-168">or</span></span>|<span data-ttu-id="a255f-169">場合 (myByte (& a) #124; 1).</span><span class="sxs-lookup"><span data-stu-id="a255f-169">If (myByte &#124; 1)...</span></span>|  
|&&|<span data-ttu-id="a255f-170">条件 AND</span><span class="sxs-lookup"><span data-stu-id="a255f-170">conditional and</span></span>|<span data-ttu-id="a255f-171">If (MyMsg.numOrders > 10) && (MyMsg.numOrders < 100)</span><span class="sxs-lookup"><span data-stu-id="a255f-171">If (MyMsg.numOrders > 10) && (MyMsg.numOrders < 100)</span></span>|  
|<span data-ttu-id="a255f-172">&#124;&#124;</span><span class="sxs-lookup"><span data-stu-id="a255f-172">&#124;&#124;</span></span>|<span data-ttu-id="a255f-173">条件 OR</span><span class="sxs-lookup"><span data-stu-id="a255f-173">conditional or</span></span>|<span data-ttu-id="a255f-174">場合 (MyMsg.numOrders < 10) (& m); #124 &#124;です。(MyMsg.numOrders > 100)</span><span class="sxs-lookup"><span data-stu-id="a255f-174">If (MyMsg.numOrders < 10) &#124;&#124; (MyMsg.numOrders > 100)</span></span>|  
|//|<span data-ttu-id="a255f-175">コメントを付ける</span><span class="sxs-lookup"><span data-stu-id="a255f-175">commenting</span></span>|<span data-ttu-id="a255f-176">//これはコメントです。</span><span class="sxs-lookup"><span data-stu-id="a255f-176">//This is the comment</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="a255f-177">一般式とフィルター式で使用されるとが異なるルール、**受信**図形です。</span><span class="sxs-lookup"><span data-stu-id="a255f-177">The rules differ between general expressions and filter expressions that are used with the **Receive** shape.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a255f-178">参照</span><span class="sxs-lookup"><span data-stu-id="a255f-178">See Also</span></span>  
 [<span data-ttu-id="a255f-179">フィルターと受信メッセージ図形の使用</span><span class="sxs-lookup"><span data-stu-id="a255f-179">Using Filters With the Receive Message Shape</span></span>](../core/using-filters-with-the-receive-message-shape.md)