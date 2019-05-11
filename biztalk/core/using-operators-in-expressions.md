---
title: 式における演算子の使用 |Microsoft Docs
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
ms.openlocfilehash: acb471fd12ad41776b116b1ed2f27fcfb6ea6f8f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395430"
---
# <a name="using-operators-in-expressions"></a><span data-ttu-id="3ea85-102">式における演算子の使用</span><span class="sxs-lookup"><span data-stu-id="3ea85-102">Using Operators in Expressions</span></span>
<span data-ttu-id="3ea85-103">次の xlang/s 演算子は、オーケストレーションの式で使用可能な。</span><span class="sxs-lookup"><span data-stu-id="3ea85-103">The following XLANG/s operators are available for use in orchestration expressions.</span></span> <span data-ttu-id="3ea85-104">C# の対応する演算子の機能にほぼ準拠します。</span><span class="sxs-lookup"><span data-stu-id="3ea85-104">They adhere closely to the functionality of the corresponding operators in C#.</span></span>  
  
|<span data-ttu-id="3ea85-105">演算子</span><span class="sxs-lookup"><span data-stu-id="3ea85-105">Operator</span></span>|<span data-ttu-id="3ea85-106">説明</span><span class="sxs-lookup"><span data-stu-id="3ea85-106">Description</span></span>|<span data-ttu-id="3ea85-107">例</span><span class="sxs-lookup"><span data-stu-id="3ea85-107">Example</span></span>|  
|--------------|-----------------|-------------|  
|<span data-ttu-id="3ea85-108">checked()</span><span class="sxs-lookup"><span data-stu-id="3ea85-108">checked()</span></span>|<span data-ttu-id="3ea85-109">算術オーバーフローでエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="3ea85-109">raise error on arithmetic overflow</span></span>|<span data-ttu-id="3ea85-110">checked(x = y \* 1000)</span><span class="sxs-lookup"><span data-stu-id="3ea85-110">checked(x = y \* 1000)</span></span>|  
|<span data-ttu-id="3ea85-111">unchecked()</span><span class="sxs-lookup"><span data-stu-id="3ea85-111">unchecked()</span></span>|<span data-ttu-id="3ea85-112">算術オーバーフローを無視します。</span><span class="sxs-lookup"><span data-stu-id="3ea85-112">ignore arithmetic overflow</span></span>|<span data-ttu-id="3ea85-113">unchecked(x = y \* 1000)</span><span class="sxs-lookup"><span data-stu-id="3ea85-113">unchecked(x = y \* 1000)</span></span>|  
|<span data-ttu-id="3ea85-114">新機能</span><span class="sxs-lookup"><span data-stu-id="3ea85-114">new</span></span>|<span data-ttu-id="3ea85-115">クラスのインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="3ea85-115">create an instance of a class</span></span>|<span data-ttu-id="3ea85-116">myObject 新しい MyClass; を =</span><span class="sxs-lookup"><span data-stu-id="3ea85-116">myObject = new MyClass;</span></span>|  
|<span data-ttu-id="3ea85-117">typeof</span><span class="sxs-lookup"><span data-stu-id="3ea85-117">typeof</span></span>|<span data-ttu-id="3ea85-118">型の取得</span><span class="sxs-lookup"><span data-stu-id="3ea85-118">Type retrieval</span></span>|<span data-ttu-id="3ea85-119">myMapType typeof(myMap) を =</span><span class="sxs-lookup"><span data-stu-id="3ea85-119">myMapType = typeof(myMap)</span></span>|  
|<span data-ttu-id="3ea85-120">succeeded()</span><span class="sxs-lookup"><span data-stu-id="3ea85-120">succeeded()</span></span>|<span data-ttu-id="3ea85-121">トランザクション スコープまたはオーケストレーションが正常に完了のテスト</span><span class="sxs-lookup"><span data-stu-id="3ea85-121">test for successful completion of transactional scope or orchestration</span></span>|<span data-ttu-id="3ea85-122">成功した (\<子トランザクションの現在のスコープまたはサービスのトランザクション ID\>)</span><span class="sxs-lookup"><span data-stu-id="3ea85-122">succeeded(\<transaction ID for child transaction of current scope or service\>)</span></span>|  
|<span data-ttu-id="3ea85-123">存在します。</span><span class="sxs-lookup"><span data-stu-id="3ea85-123">exists</span></span>|<span data-ttu-id="3ea85-124">メッセージ コンテキスト プロパティの存在をテストします。</span><span class="sxs-lookup"><span data-stu-id="3ea85-124">test for the existence of a message context property</span></span>|<span data-ttu-id="3ea85-125">BTS します。RetryCount Message_In が存在します。</span><span class="sxs-lookup"><span data-stu-id="3ea85-125">BTS.RetryCount exists Message_In</span></span>|  
|+|<span data-ttu-id="3ea85-126">単項プラス</span><span class="sxs-lookup"><span data-stu-id="3ea85-126">unary plus</span></span>|<span data-ttu-id="3ea85-127">+(int x)</span><span class="sxs-lookup"><span data-stu-id="3ea85-127">+(int x)</span></span>|  
|-|<span data-ttu-id="3ea85-128">単項マイナス</span><span class="sxs-lookup"><span data-stu-id="3ea85-128">unary minus</span></span>|<span data-ttu-id="3ea85-129">-(int x)</span><span class="sxs-lookup"><span data-stu-id="3ea85-129">-(int x)</span></span>|  
|<span data-ttu-id="3ea85-130">!</span><span class="sxs-lookup"><span data-stu-id="3ea85-130">!</span></span>|<span data-ttu-id="3ea85-131">論理否定</span><span class="sxs-lookup"><span data-stu-id="3ea85-131">logical negation</span></span>|<span data-ttu-id="3ea85-132">!myBool</span><span class="sxs-lookup"><span data-stu-id="3ea85-132">!myBool</span></span>|  
|~|<span data-ttu-id="3ea85-133">ビットごとの補数</span><span class="sxs-lookup"><span data-stu-id="3ea85-133">bitwise complement</span></span>|<span data-ttu-id="3ea85-134">x = ~y</span><span class="sxs-lookup"><span data-stu-id="3ea85-134">x = ~y</span></span>|  
|<span data-ttu-id="3ea85-135">()</span><span class="sxs-lookup"><span data-stu-id="3ea85-135">()</span></span>|<span data-ttu-id="3ea85-136">キャスト</span><span class="sxs-lookup"><span data-stu-id="3ea85-136">cast</span></span>|<span data-ttu-id="3ea85-137">たとえば、myInt (bool)</span><span class="sxs-lookup"><span data-stu-id="3ea85-137">(bool) myInt</span></span>|  
|*|<span data-ttu-id="3ea85-138">times</span><span class="sxs-lookup"><span data-stu-id="3ea85-138">times</span></span>|<span data-ttu-id="3ea85-139">Weight = MyMsg.numOrders \* 20</span><span class="sxs-lookup"><span data-stu-id="3ea85-139">Weight = MyMsg.numOrders \* 20</span></span>|  
|/|<span data-ttu-id="3ea85-140">割った値</span><span class="sxs-lookup"><span data-stu-id="3ea85-140">divided by</span></span>|<span data-ttu-id="3ea85-141">x / y</span><span class="sxs-lookup"><span data-stu-id="3ea85-141">x / y</span></span>|  
|+|<span data-ttu-id="3ea85-142">プラス</span><span class="sxs-lookup"><span data-stu-id="3ea85-142">plus</span></span>|<span data-ttu-id="3ea85-143">x + y</span><span class="sxs-lookup"><span data-stu-id="3ea85-143">x + y</span></span>|  
|-|<span data-ttu-id="3ea85-144">マイナス</span><span class="sxs-lookup"><span data-stu-id="3ea85-144">minus</span></span>|<span data-ttu-id="3ea85-145">x - y</span><span class="sxs-lookup"><span data-stu-id="3ea85-145">x - y</span></span>|  
|<<|<span data-ttu-id="3ea85-146">左シフト</span><span class="sxs-lookup"><span data-stu-id="3ea85-146">shift left</span></span>|<span data-ttu-id="3ea85-147">x << 2</span><span class="sxs-lookup"><span data-stu-id="3ea85-147">x << 2</span></span>|  
|>>|<span data-ttu-id="3ea85-148">右シフトします。</span><span class="sxs-lookup"><span data-stu-id="3ea85-148">shift right</span></span>|<span data-ttu-id="3ea85-149">x >> 2</span><span class="sxs-lookup"><span data-stu-id="3ea85-149">x >> 2</span></span>|  
|<|<span data-ttu-id="3ea85-150">小さい</span><span class="sxs-lookup"><span data-stu-id="3ea85-150">less than</span></span>|<span data-ttu-id="3ea85-151">場合 (MyMsg.numOrders < 10).</span><span class="sxs-lookup"><span data-stu-id="3ea85-151">If (MyMsg.numOrders < 10)...</span></span>|  
|>|<span data-ttu-id="3ea85-152">大きい</span><span class="sxs-lookup"><span data-stu-id="3ea85-152">greater than</span></span>|<span data-ttu-id="3ea85-153">場合 (MyMsg.numOrders > 10).</span><span class="sxs-lookup"><span data-stu-id="3ea85-153">If (MyMsg.numOrders > 10)...</span></span>|  
|<=|<span data-ttu-id="3ea85-154">等しいまたはそれよりも小さい</span><span class="sxs-lookup"><span data-stu-id="3ea85-154">less than or equal to</span></span>|<span data-ttu-id="3ea85-155">場合 (MyMsg.numOrders < = 10).</span><span class="sxs-lookup"><span data-stu-id="3ea85-155">If (MyMsg.numOrders <= 10)...</span></span>|  
|>=|<span data-ttu-id="3ea85-156">大きいまたは等しい</span><span class="sxs-lookup"><span data-stu-id="3ea85-156">greater than or equal to</span></span>|<span data-ttu-id="3ea85-157">場合 (MyMsg.numOrders > = 10).</span><span class="sxs-lookup"><span data-stu-id="3ea85-157">If (MyMsg.numOrders >= 10)...</span></span>|  
|==|<span data-ttu-id="3ea85-158">等しい</span><span class="sxs-lookup"><span data-stu-id="3ea85-158">equal to</span></span>|<span data-ttu-id="3ea85-159">If (MyMsg.numOrders == 10)...</span><span class="sxs-lookup"><span data-stu-id="3ea85-159">If (MyMsg.numOrders == 10)...</span></span>|  
|<span data-ttu-id="3ea85-160">!=</span><span class="sxs-lookup"><span data-stu-id="3ea85-160">!=</span></span>|<span data-ttu-id="3ea85-161">等しくないです。</span><span class="sxs-lookup"><span data-stu-id="3ea85-161">not equal to</span></span>|<span data-ttu-id="3ea85-162">場合 (MyMsg.numOrders! = 10).</span><span class="sxs-lookup"><span data-stu-id="3ea85-162">If (MyMsg.numOrders != 10)...</span></span>|  
|&|<span data-ttu-id="3ea85-163">、</span><span class="sxs-lookup"><span data-stu-id="3ea85-163">and</span></span>|<span data-ttu-id="3ea85-164">場合 (myByte & 255).</span><span class="sxs-lookup"><span data-stu-id="3ea85-164">If (myByte & 255)...</span></span>|  
|^|<span data-ttu-id="3ea85-165">排他または</span><span class="sxs-lookup"><span data-stu-id="3ea85-165">exclusive or</span></span>|<span data-ttu-id="3ea85-166">場合 (myByte ^1).</span><span class="sxs-lookup"><span data-stu-id="3ea85-166">If (myByte ^ 1)...</span></span>|  
|<span data-ttu-id="3ea85-167">&#124;</span><span class="sxs-lookup"><span data-stu-id="3ea85-167">&#124;</span></span>|<span data-ttu-id="3ea85-168">または</span><span class="sxs-lookup"><span data-stu-id="3ea85-168">or</span></span>|<span data-ttu-id="3ea85-169">場合 (myByte &#124; 1).</span><span class="sxs-lookup"><span data-stu-id="3ea85-169">If (myByte &#124; 1)...</span></span>|  
|&&|<span data-ttu-id="3ea85-170">条件付きと</span><span class="sxs-lookup"><span data-stu-id="3ea85-170">conditional and</span></span>|<span data-ttu-id="3ea85-171">If (MyMsg.numOrders > 10) && (MyMsg.numOrders < 100)</span><span class="sxs-lookup"><span data-stu-id="3ea85-171">If (MyMsg.numOrders > 10) && (MyMsg.numOrders < 100)</span></span>|  
|<span data-ttu-id="3ea85-172">&#124;&#124;</span><span class="sxs-lookup"><span data-stu-id="3ea85-172">&#124;&#124;</span></span>|<span data-ttu-id="3ea85-173">条件付きまたは</span><span class="sxs-lookup"><span data-stu-id="3ea85-173">conditional or</span></span>|<span data-ttu-id="3ea85-174">If (MyMsg.numOrders < 10) &#124;&#124; (MyMsg.numOrders > 100)</span><span class="sxs-lookup"><span data-stu-id="3ea85-174">If (MyMsg.numOrders < 10) &#124;&#124; (MyMsg.numOrders > 100)</span></span>|  
|//|<span data-ttu-id="3ea85-175">コメント</span><span class="sxs-lookup"><span data-stu-id="3ea85-175">commenting</span></span>|<span data-ttu-id="3ea85-176">これはコメントです。</span><span class="sxs-lookup"><span data-stu-id="3ea85-176">//This is the comment</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="3ea85-177">一般的な式とフィルター式で使用される規則とは異なる、**受信**図形。</span><span class="sxs-lookup"><span data-stu-id="3ea85-177">The rules differ between general expressions and filter expressions that are used with the **Receive** shape.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ea85-178">参照</span><span class="sxs-lookup"><span data-stu-id="3ea85-178">See Also</span></span>  
 [<span data-ttu-id="3ea85-179">フィルターと受信メッセージ図形の使用</span><span class="sxs-lookup"><span data-stu-id="3ea85-179">Using Filters With the Receive Message Shape</span></span>](../core/using-filters-with-the-receive-message-shape.md)