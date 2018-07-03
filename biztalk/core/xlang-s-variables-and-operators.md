---
title: Xlang-s の変数および演算子 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 02512789-2cb9-4ba9-aa78-e59b248e6b24
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f47ee6f69c1a69d0686bdb75b5dcaffc4a7c60a4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023848"
---
# <a name="xlang-s-variables-and-operators"></a><span data-ttu-id="ab8e5-102">Xlang-s の変数および演算子</span><span class="sxs-lookup"><span data-stu-id="ab8e5-102">XLANG-s Variables and Operators</span></span>
<span data-ttu-id="ab8e5-103">このセクションでは、XLANG/s 言語で使用される変数および演算子について説明します。</span><span class="sxs-lookup"><span data-stu-id="ab8e5-103">This section discusses the variables and operators used in the XLANG/s language.</span></span>  
  
## <a name="xlangs-variables"></a><span data-ttu-id="ab8e5-104">XLANG/s の変数</span><span class="sxs-lookup"><span data-stu-id="ab8e5-104">XLANG/s Variables</span></span>  
 <span data-ttu-id="ab8e5-105">変数は格納場所を表します。</span><span class="sxs-lookup"><span data-stu-id="ab8e5-105">Variables represent storage locations.</span></span> <span data-ttu-id="ab8e5-106">各変数には型があり、この型によってその変数に格納できる値が決まります。</span><span class="sxs-lookup"><span data-stu-id="ab8e5-106">Every variable has a type that determines what values can be stored in that variable.</span></span> <span data-ttu-id="ab8e5-107">XLANG/s はタイプ セーフであり、コンパイラによって変数に格納された値が常に適切な型であることが保証されます。</span><span class="sxs-lookup"><span data-stu-id="ab8e5-107">XLANG/s is type-safe, and its compiler guarantees that values stored in variables are always of the appropriate type.</span></span> <span data-ttu-id="ab8e5-108">XLANG/s は、次の変数の型をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="ab8e5-108">XLANG/s supports the following variable types:</span></span>  
  
- <span data-ttu-id="ab8e5-109">メッセージ</span><span class="sxs-lookup"><span data-stu-id="ab8e5-109">Messages</span></span>  
  
- <span data-ttu-id="ab8e5-110">関連付けセット</span><span class="sxs-lookup"><span data-stu-id="ab8e5-110">Correlation sets</span></span>  
  
- <span data-ttu-id="ab8e5-111">サービス リンク</span><span class="sxs-lookup"><span data-stu-id="ab8e5-111">Service links</span></span>  
  
- <span data-ttu-id="ab8e5-112">[ポート]</span><span class="sxs-lookup"><span data-stu-id="ab8e5-112">Ports</span></span>  
  
- <span data-ttu-id="ab8e5-113">組み込みの値の型を識別:**ブール**、**バイト**、 **Char**、 **Decimal**、**二重**、 **Int16**、 **Int32**、 **Int64**、 **SByte**、**単一**、**文字列**、**UInt16**、 **UInt32**、および**UInt64**</span><span class="sxs-lookup"><span data-stu-id="ab8e5-113">Distinguished built-in value types: **Boolean**, **Byte**, **Char**, **Decimal**, **Double**, **Int16**, **Int32**, **Int64**, **SByte**, **Single**, **String**, **UInt16**, **UInt32**, and **UInt64**</span></span>  
  
- <span data-ttu-id="ab8e5-114">オブジェクト</span><span class="sxs-lookup"><span data-stu-id="ab8e5-114">Objects</span></span>  
  
- <span data-ttu-id="ab8e5-115">列挙型</span><span class="sxs-lookup"><span data-stu-id="ab8e5-115">Enumeration types</span></span>  
  
  <span data-ttu-id="ab8e5-116">XLANG/s には、上記の各型について初期化のセマンティクスが用意されています。</span><span class="sxs-lookup"><span data-stu-id="ab8e5-116">XLANG/s provides initialization semantics for each of the preceding types.</span></span> <span data-ttu-id="ab8e5-117">これらの初期化は、その型の変数への代入と見なすことができます。</span><span class="sxs-lookup"><span data-stu-id="ab8e5-117">Such initialization can be viewed as an assignment to a variable of that type.</span></span> <span data-ttu-id="ab8e5-118">XLANG/s では、変数に明示的に代入しないと、その値を取得または使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="ab8e5-118">In XLANG/s, a variable must be definitely assigned before its value can be obtained or used.</span></span>  
  
## <a name="xlangs-operators"></a><span data-ttu-id="ab8e5-119">XLANG/s の演算子</span><span class="sxs-lookup"><span data-stu-id="ab8e5-119">XLANG/s Operators</span></span>  
 <span data-ttu-id="ab8e5-120">XLANG/s は、次の演算子をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="ab8e5-120">XLANG/s supports the following operators.</span></span> <span data-ttu-id="ab8e5-121">C# の対応する演算子の機能にほぼ準拠しています。</span><span class="sxs-lookup"><span data-stu-id="ab8e5-121">They adhere closely to the functionality of the corresponding operators in C#.</span></span>  
  
|<span data-ttu-id="ab8e5-122">演算子</span><span class="sxs-lookup"><span data-stu-id="ab8e5-122">Operator</span></span>|<span data-ttu-id="ab8e5-123">説明</span><span class="sxs-lookup"><span data-stu-id="ab8e5-123">Description</span></span>|<span data-ttu-id="ab8e5-124">例</span><span class="sxs-lookup"><span data-stu-id="ab8e5-124">Example</span></span>|  
|--------------|-----------------|-------------|  
|<span data-ttu-id="ab8e5-125">オン</span><span class="sxs-lookup"><span data-stu-id="ab8e5-125">checked</span></span>|<span data-ttu-id="ab8e5-126">算術オーバーフローでエラーを発生させます。</span><span class="sxs-lookup"><span data-stu-id="ab8e5-126">Raises error on arithmetic overflow</span></span>|<span data-ttu-id="ab8e5-127">checked(x = y \* 1000)</span><span class="sxs-lookup"><span data-stu-id="ab8e5-127">checked(x = y \* 1000)</span></span>|  
|<span data-ttu-id="ab8e5-128">オフ</span><span class="sxs-lookup"><span data-stu-id="ab8e5-128">unchecked</span></span>|<span data-ttu-id="ab8e5-129">算術オーバーフローを無視</span><span class="sxs-lookup"><span data-stu-id="ab8e5-129">Ignores arithmetic overflow</span></span>|<span data-ttu-id="ab8e5-130">unchecked(x = y \* 1000)</span><span class="sxs-lookup"><span data-stu-id="ab8e5-130">unchecked(x = y \* 1000)</span></span>|  
|<span data-ttu-id="ab8e5-131">新機能</span><span class="sxs-lookup"><span data-stu-id="ab8e5-131">new</span></span>|<span data-ttu-id="ab8e5-132">クラスのインスタンスを作成</span><span class="sxs-lookup"><span data-stu-id="ab8e5-132">Creates an instance of a class</span></span>|<span data-ttu-id="ab8e5-133">myObject = new MyClass;</span><span class="sxs-lookup"><span data-stu-id="ab8e5-133">myObject = new MyClass;</span></span>|  
|<span data-ttu-id="ab8e5-134">typeof</span><span class="sxs-lookup"><span data-stu-id="ab8e5-134">typeof</span></span>|<span data-ttu-id="ab8e5-135">型を取得</span><span class="sxs-lookup"><span data-stu-id="ab8e5-135">Retrieves a type</span></span>|<span data-ttu-id="ab8e5-136">myMapType = typeof(myMap)</span><span class="sxs-lookup"><span data-stu-id="ab8e5-136">myMapType = typeof(myMap)</span></span>|  
|<span data-ttu-id="ab8e5-137">succeeded</span><span class="sxs-lookup"><span data-stu-id="ab8e5-137">succeeded</span></span>|<span data-ttu-id="ab8e5-138">トランザクション スコープまたはオーケストレーションが正常に完了するかどうかをテスト</span><span class="sxs-lookup"><span data-stu-id="ab8e5-138">Tests for successful completion of transactional scope or orchestration</span></span>|<span data-ttu-id="ab8e5-139">成功した (\<子トランザクションの現在のスコープまたはサービスのトランザクション ID\>)</span><span class="sxs-lookup"><span data-stu-id="ab8e5-139">succeeded(\<transaction ID for child transaction of current scope or service\>)</span></span>|  
|<span data-ttu-id="ab8e5-140">存在する</span><span class="sxs-lookup"><span data-stu-id="ab8e5-140">exists</span></span>|<span data-ttu-id="ab8e5-141">メッセージ コンテキスト プロパティの存在のテスト</span><span class="sxs-lookup"><span data-stu-id="ab8e5-141">Tests for the existence of a message context property</span></span>|<span data-ttu-id="ab8e5-142">BTS.RetryCount exists Message_In</span><span class="sxs-lookup"><span data-stu-id="ab8e5-142">BTS.RetryCount exists Message_In</span></span>|  
|+|<span data-ttu-id="ab8e5-143">単項プラス</span><span class="sxs-lookup"><span data-stu-id="ab8e5-143">Unary plus</span></span>|<span data-ttu-id="ab8e5-144">+(int x)</span><span class="sxs-lookup"><span data-stu-id="ab8e5-144">+(int x)</span></span>|  
|-|<span data-ttu-id="ab8e5-145">単項マイナス</span><span class="sxs-lookup"><span data-stu-id="ab8e5-145">Unary minus</span></span>|<span data-ttu-id="ab8e5-146">-(int x)</span><span class="sxs-lookup"><span data-stu-id="ab8e5-146">-(int x)</span></span>|  
|<span data-ttu-id="ab8e5-147">!</span><span class="sxs-lookup"><span data-stu-id="ab8e5-147">!</span></span>|<span data-ttu-id="ab8e5-148">論理否定</span><span class="sxs-lookup"><span data-stu-id="ab8e5-148">Logical negation</span></span>|<span data-ttu-id="ab8e5-149">!myBool</span><span class="sxs-lookup"><span data-stu-id="ab8e5-149">!myBool</span></span>|  
|~|<span data-ttu-id="ab8e5-150">ビットごとの補数</span><span class="sxs-lookup"><span data-stu-id="ab8e5-150">Bitwise complement</span></span>|<span data-ttu-id="ab8e5-151">x = ~y</span><span class="sxs-lookup"><span data-stu-id="ab8e5-151">x = ~y</span></span>|  
|<span data-ttu-id="ab8e5-152">()</span><span class="sxs-lookup"><span data-stu-id="ab8e5-152">()</span></span>|<span data-ttu-id="ab8e5-153">キャスト</span><span class="sxs-lookup"><span data-stu-id="ab8e5-153">Cast</span></span>|<span data-ttu-id="ab8e5-154">(bool) myInt</span><span class="sxs-lookup"><span data-stu-id="ab8e5-154">(bool) myInt</span></span>|  
|*|<span data-ttu-id="ab8e5-155">時間</span><span class="sxs-lookup"><span data-stu-id="ab8e5-155">Times</span></span>|<span data-ttu-id="ab8e5-156">Weight = MyMsg.numOrders \* 20</span><span class="sxs-lookup"><span data-stu-id="ab8e5-156">Weight = MyMsg.numOrders \* 20</span></span>|  
|/|<span data-ttu-id="ab8e5-157">割った値</span><span class="sxs-lookup"><span data-stu-id="ab8e5-157">Divided by</span></span>|<span data-ttu-id="ab8e5-158">x / y</span><span class="sxs-lookup"><span data-stu-id="ab8e5-158">x / y</span></span>|  
|+|<span data-ttu-id="ab8e5-159">プラス</span><span class="sxs-lookup"><span data-stu-id="ab8e5-159">Plus</span></span>|<span data-ttu-id="ab8e5-160">x + y</span><span class="sxs-lookup"><span data-stu-id="ab8e5-160">x + y</span></span>|  
|-|<span data-ttu-id="ab8e5-161">マイナス</span><span class="sxs-lookup"><span data-stu-id="ab8e5-161">Minus</span></span>|<span data-ttu-id="ab8e5-162">x - y</span><span class="sxs-lookup"><span data-stu-id="ab8e5-162">x - y</span></span>|  
|<<|<span data-ttu-id="ab8e5-163">左シフト</span><span class="sxs-lookup"><span data-stu-id="ab8e5-163">Shift left</span></span>|<span data-ttu-id="ab8e5-164">x << 2</span><span class="sxs-lookup"><span data-stu-id="ab8e5-164">x << 2</span></span>|  
|>>|<span data-ttu-id="ab8e5-165">右シフト</span><span class="sxs-lookup"><span data-stu-id="ab8e5-165">Shift right</span></span>|<span data-ttu-id="ab8e5-166">x >> 2</span><span class="sxs-lookup"><span data-stu-id="ab8e5-166">x >> 2</span></span>|  
|<|<span data-ttu-id="ab8e5-167">より小さい</span><span class="sxs-lookup"><span data-stu-id="ab8e5-167">Less than</span></span>|<span data-ttu-id="ab8e5-168">If (MyMsg.numOrders < 10)...</span><span class="sxs-lookup"><span data-stu-id="ab8e5-168">If (MyMsg.numOrders < 10)...</span></span>|  
|>|<span data-ttu-id="ab8e5-169">より大きい</span><span class="sxs-lookup"><span data-stu-id="ab8e5-169">Greater than</span></span>|<span data-ttu-id="ab8e5-170">場合 (MyMsg.numOrders > 10).</span><span class="sxs-lookup"><span data-stu-id="ab8e5-170">If (MyMsg.numOrders > 10)...</span></span>|  
|<=|<span data-ttu-id="ab8e5-171">以下</span><span class="sxs-lookup"><span data-stu-id="ab8e5-171">Less than or equal to</span></span>|<span data-ttu-id="ab8e5-172">If (MyMsg.numOrders <= 10)...</span><span class="sxs-lookup"><span data-stu-id="ab8e5-172">If (MyMsg.numOrders <= 10)...</span></span>|  
|>=|<span data-ttu-id="ab8e5-173">以上</span><span class="sxs-lookup"><span data-stu-id="ab8e5-173">Greater than or equal to</span></span>|<span data-ttu-id="ab8e5-174">場合 (MyMsg.numOrders > = 10).</span><span class="sxs-lookup"><span data-stu-id="ab8e5-174">If (MyMsg.numOrders >= 10)...</span></span>|  
|==|<span data-ttu-id="ab8e5-175">等しい</span><span class="sxs-lookup"><span data-stu-id="ab8e5-175">Equal to</span></span>|<span data-ttu-id="ab8e5-176">If (MyMsg.numOrders == 10)...</span><span class="sxs-lookup"><span data-stu-id="ab8e5-176">If (MyMsg.numOrders == 10)...</span></span>|  
|<span data-ttu-id="ab8e5-177">!=</span><span class="sxs-lookup"><span data-stu-id="ab8e5-177">!=</span></span>|<span data-ttu-id="ab8e5-178">等しくない</span><span class="sxs-lookup"><span data-stu-id="ab8e5-178">Not equal to</span></span>|<span data-ttu-id="ab8e5-179">If (MyMsg.numOrders != 10)...</span><span class="sxs-lookup"><span data-stu-id="ab8e5-179">If (MyMsg.numOrders != 10)...</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ab8e5-180">参照</span><span class="sxs-lookup"><span data-stu-id="ab8e5-180">See Also</span></span>  
 <span data-ttu-id="ab8e5-181">[Xlang-s データ型](../core/xlang-s-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="ab8e5-181">[XLANG-s Data Types](../core/xlang-s-data-types.md) </span></span>  
 <span data-ttu-id="ab8e5-182">[Xlang-s ステートメント](../core/xlang-s-statements.md) </span><span class="sxs-lookup"><span data-stu-id="ab8e5-182">[XLANG-s Statements](../core/xlang-s-statements.md) </span></span>  
 <span data-ttu-id="ab8e5-183">[Xlang-s 式](../core/xlang-s-expressions.md) </span><span class="sxs-lookup"><span data-stu-id="ab8e5-183">[XLANG-s Expressions](../core/xlang-s-expressions.md) </span></span>  
 <span data-ttu-id="ab8e5-184">[Xlang-s の予約語](../core/xlang-s-reserved-words.md) </span><span class="sxs-lookup"><span data-stu-id="ab8e5-184">[XLANG-s Reserved Words](../core/xlang-s-reserved-words.md) </span></span>  
 [<span data-ttu-id="ab8e5-185">XLANG-s から BPEL4WS への種類の変換</span><span class="sxs-lookup"><span data-stu-id="ab8e5-185">XLANG-s to BPEL4WS Type Conversions</span></span>](../core/xlang-s-to-bpel4ws-type-conversions.md)