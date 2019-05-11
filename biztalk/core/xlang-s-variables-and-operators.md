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
ms.openlocfilehash: 4eace5d4a30f8cac80403143a5dc3cfb887c0bc5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65246442"
---
# <a name="xlang-s-variables-and-operators"></a><span data-ttu-id="01f9d-102">Xlang-s の変数および演算子</span><span class="sxs-lookup"><span data-stu-id="01f9d-102">XLANG-s Variables and Operators</span></span>
<span data-ttu-id="01f9d-103">このセクションでは、変数と、xlang/s 言語で使用される演算子について説明します。</span><span class="sxs-lookup"><span data-stu-id="01f9d-103">This section discusses the variables and operators used in the XLANG/s language.</span></span>  
  
## <a name="xlangs-variables"></a><span data-ttu-id="01f9d-104">Xlang/s の変数</span><span class="sxs-lookup"><span data-stu-id="01f9d-104">XLANG/s Variables</span></span>  
 <span data-ttu-id="01f9d-105">変数は、記憶域の場所を表します。</span><span class="sxs-lookup"><span data-stu-id="01f9d-105">Variables represent storage locations.</span></span> <span data-ttu-id="01f9d-106">すべての変数ができる値を指定する型で変数に格納されています。</span><span class="sxs-lookup"><span data-stu-id="01f9d-106">Every variable has a type that determines what values can be stored in that variable.</span></span> <span data-ttu-id="01f9d-107">Xlang/s はタイプ セーフ、およびそのコンパイラでは、変数に格納されている値は常に適切な型のことが保証されます。</span><span class="sxs-lookup"><span data-stu-id="01f9d-107">XLANG/s is type-safe, and its compiler guarantees that values stored in variables are always of the appropriate type.</span></span> <span data-ttu-id="01f9d-108">XLANG/秒には、次の変数の型がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="01f9d-108">XLANG/s supports the following variable types:</span></span>  
  
- <span data-ttu-id="01f9d-109">メッセージ</span><span class="sxs-lookup"><span data-stu-id="01f9d-109">Messages</span></span>  
  
- <span data-ttu-id="01f9d-110">関連付けセット</span><span class="sxs-lookup"><span data-stu-id="01f9d-110">Correlation sets</span></span>  
  
- <span data-ttu-id="01f9d-111">サービスへのリンク</span><span class="sxs-lookup"><span data-stu-id="01f9d-111">Service links</span></span>  
  
- <span data-ttu-id="01f9d-112">ポート</span><span class="sxs-lookup"><span data-stu-id="01f9d-112">Ports</span></span>  
  
- <span data-ttu-id="01f9d-113">識別の組み込み値型:**ブール**、**バイト**、 **Char**、 **Decimal**、**二重**、 **Int16**、 **Int32**、 **Int64**、 **SByte**、**単一**、**文字列**、 **UInt16**、 **UInt32**、および**UInt64**</span><span class="sxs-lookup"><span data-stu-id="01f9d-113">Distinguished built-in value types: **Boolean**, **Byte**, **Char**, **Decimal**, **Double**, **Int16**, **Int32**, **Int64**, **SByte**, **Single**, **String**, **UInt16**, **UInt32**, and **UInt64**</span></span>  
  
- <span data-ttu-id="01f9d-114">オブジェクト</span><span class="sxs-lookup"><span data-stu-id="01f9d-114">Objects</span></span>  
  
- <span data-ttu-id="01f9d-115">列挙型</span><span class="sxs-lookup"><span data-stu-id="01f9d-115">Enumeration types</span></span>  
  
  <span data-ttu-id="01f9d-116">XLANG/秒では、これらの型のそれぞれの初期化のセマンティクスを提供します。</span><span class="sxs-lookup"><span data-stu-id="01f9d-116">XLANG/s provides initialization semantics for each of the preceding types.</span></span> <span data-ttu-id="01f9d-117">このような初期化は、その型の変数への代入として表示できます。</span><span class="sxs-lookup"><span data-stu-id="01f9d-117">Such initialization can be viewed as an assignment to a variable of that type.</span></span> <span data-ttu-id="01f9d-118">Xlang/s では、変数を割り当てる必要があります間違いなく前に、その値を取得または使用することができます。</span><span class="sxs-lookup"><span data-stu-id="01f9d-118">In XLANG/s, a variable must be definitely assigned before its value can be obtained or used.</span></span>  
  
## <a name="xlangs-operators"></a><span data-ttu-id="01f9d-119">Xlang/s の演算子</span><span class="sxs-lookup"><span data-stu-id="01f9d-119">XLANG/s Operators</span></span>  
 <span data-ttu-id="01f9d-120">XLANG/秒では、次の演算子をサポートします。</span><span class="sxs-lookup"><span data-stu-id="01f9d-120">XLANG/s supports the following operators.</span></span> <span data-ttu-id="01f9d-121">C# の対応する演算子の機能にほぼ準拠します。</span><span class="sxs-lookup"><span data-stu-id="01f9d-121">They adhere closely to the functionality of the corresponding operators in C#.</span></span>  
  
|<span data-ttu-id="01f9d-122">演算子</span><span class="sxs-lookup"><span data-stu-id="01f9d-122">Operator</span></span>|<span data-ttu-id="01f9d-123">説明</span><span class="sxs-lookup"><span data-stu-id="01f9d-123">Description</span></span>|<span data-ttu-id="01f9d-124">例</span><span class="sxs-lookup"><span data-stu-id="01f9d-124">Example</span></span>|  
|--------------|-----------------|-------------|  
|<span data-ttu-id="01f9d-125">オン</span><span class="sxs-lookup"><span data-stu-id="01f9d-125">checked</span></span>|<span data-ttu-id="01f9d-126">算術オーバーフローでエラーを発生させます。</span><span class="sxs-lookup"><span data-stu-id="01f9d-126">Raises error on arithmetic overflow</span></span>|<span data-ttu-id="01f9d-127">checked(x = y \* 1000)</span><span class="sxs-lookup"><span data-stu-id="01f9d-127">checked(x = y \* 1000)</span></span>|  
|<span data-ttu-id="01f9d-128">unchecked</span><span class="sxs-lookup"><span data-stu-id="01f9d-128">unchecked</span></span>|<span data-ttu-id="01f9d-129">算術オーバーフローを無視します。</span><span class="sxs-lookup"><span data-stu-id="01f9d-129">Ignores arithmetic overflow</span></span>|<span data-ttu-id="01f9d-130">unchecked(x = y \* 1000)</span><span class="sxs-lookup"><span data-stu-id="01f9d-130">unchecked(x = y \* 1000)</span></span>|  
|<span data-ttu-id="01f9d-131">新機能</span><span class="sxs-lookup"><span data-stu-id="01f9d-131">new</span></span>|<span data-ttu-id="01f9d-132">クラスのインスタンスを作成します</span><span class="sxs-lookup"><span data-stu-id="01f9d-132">Creates an instance of a class</span></span>|<span data-ttu-id="01f9d-133">myObject 新しい MyClass; を =</span><span class="sxs-lookup"><span data-stu-id="01f9d-133">myObject = new MyClass;</span></span>|  
|<span data-ttu-id="01f9d-134">typeof</span><span class="sxs-lookup"><span data-stu-id="01f9d-134">typeof</span></span>|<span data-ttu-id="01f9d-135">型を取得します。</span><span class="sxs-lookup"><span data-stu-id="01f9d-135">Retrieves a type</span></span>|<span data-ttu-id="01f9d-136">myMapType typeof(myMap) を =</span><span class="sxs-lookup"><span data-stu-id="01f9d-136">myMapType = typeof(myMap)</span></span>|  
|<span data-ttu-id="01f9d-137">succeeded</span><span class="sxs-lookup"><span data-stu-id="01f9d-137">succeeded</span></span>|<span data-ttu-id="01f9d-138">トランザクション スコープまたはオーケストレーションが正常に完了のテスト</span><span class="sxs-lookup"><span data-stu-id="01f9d-138">Tests for successful completion of transactional scope or orchestration</span></span>|<span data-ttu-id="01f9d-139">成功した (\<子トランザクションの現在のスコープまたはサービスのトランザクション ID\>)</span><span class="sxs-lookup"><span data-stu-id="01f9d-139">succeeded(\<transaction ID for child transaction of current scope or service\>)</span></span>|  
|<span data-ttu-id="01f9d-140">存在します。</span><span class="sxs-lookup"><span data-stu-id="01f9d-140">exists</span></span>|<span data-ttu-id="01f9d-141">メッセージ コンテキスト プロパティの存在のテスト</span><span class="sxs-lookup"><span data-stu-id="01f9d-141">Tests for the existence of a message context property</span></span>|<span data-ttu-id="01f9d-142">BTS します。RetryCount Message_In が存在します。</span><span class="sxs-lookup"><span data-stu-id="01f9d-142">BTS.RetryCount exists Message_In</span></span>|  
|+|<span data-ttu-id="01f9d-143">単項プラス</span><span class="sxs-lookup"><span data-stu-id="01f9d-143">Unary plus</span></span>|<span data-ttu-id="01f9d-144">+(int x)</span><span class="sxs-lookup"><span data-stu-id="01f9d-144">+(int x)</span></span>|  
|-|<span data-ttu-id="01f9d-145">単項マイナス</span><span class="sxs-lookup"><span data-stu-id="01f9d-145">Unary minus</span></span>|<span data-ttu-id="01f9d-146">-(int x)</span><span class="sxs-lookup"><span data-stu-id="01f9d-146">-(int x)</span></span>|  
|<span data-ttu-id="01f9d-147">!</span><span class="sxs-lookup"><span data-stu-id="01f9d-147">!</span></span>|<span data-ttu-id="01f9d-148">論理否定</span><span class="sxs-lookup"><span data-stu-id="01f9d-148">Logical negation</span></span>|<span data-ttu-id="01f9d-149">!myBool</span><span class="sxs-lookup"><span data-stu-id="01f9d-149">!myBool</span></span>|  
|~|<span data-ttu-id="01f9d-150">ビットごとの補数</span><span class="sxs-lookup"><span data-stu-id="01f9d-150">Bitwise complement</span></span>|<span data-ttu-id="01f9d-151">x = ~y</span><span class="sxs-lookup"><span data-stu-id="01f9d-151">x = ~y</span></span>|  
|<span data-ttu-id="01f9d-152">()</span><span class="sxs-lookup"><span data-stu-id="01f9d-152">()</span></span>|<span data-ttu-id="01f9d-153">キャスト</span><span class="sxs-lookup"><span data-stu-id="01f9d-153">Cast</span></span>|<span data-ttu-id="01f9d-154">たとえば、myInt (bool)</span><span class="sxs-lookup"><span data-stu-id="01f9d-154">(bool) myInt</span></span>|  
|*|<span data-ttu-id="01f9d-155">時間</span><span class="sxs-lookup"><span data-stu-id="01f9d-155">Times</span></span>|<span data-ttu-id="01f9d-156">Weight = MyMsg.numOrders \* 20</span><span class="sxs-lookup"><span data-stu-id="01f9d-156">Weight = MyMsg.numOrders \* 20</span></span>|  
|/|<span data-ttu-id="01f9d-157">割った値</span><span class="sxs-lookup"><span data-stu-id="01f9d-157">Divided by</span></span>|<span data-ttu-id="01f9d-158">x / y</span><span class="sxs-lookup"><span data-stu-id="01f9d-158">x / y</span></span>|  
|+|<span data-ttu-id="01f9d-159">プラス</span><span class="sxs-lookup"><span data-stu-id="01f9d-159">Plus</span></span>|<span data-ttu-id="01f9d-160">x + y</span><span class="sxs-lookup"><span data-stu-id="01f9d-160">x + y</span></span>|  
|-|<span data-ttu-id="01f9d-161">マイナス</span><span class="sxs-lookup"><span data-stu-id="01f9d-161">Minus</span></span>|<span data-ttu-id="01f9d-162">x - y</span><span class="sxs-lookup"><span data-stu-id="01f9d-162">x - y</span></span>|  
|<<|<span data-ttu-id="01f9d-163">左シフト</span><span class="sxs-lookup"><span data-stu-id="01f9d-163">Shift left</span></span>|<span data-ttu-id="01f9d-164">x << 2</span><span class="sxs-lookup"><span data-stu-id="01f9d-164">x << 2</span></span>|  
|>>|<span data-ttu-id="01f9d-165">右シフトします。</span><span class="sxs-lookup"><span data-stu-id="01f9d-165">Shift right</span></span>|<span data-ttu-id="01f9d-166">x >> 2</span><span class="sxs-lookup"><span data-stu-id="01f9d-166">x >> 2</span></span>|  
|<|<span data-ttu-id="01f9d-167">次の値未満</span><span class="sxs-lookup"><span data-stu-id="01f9d-167">Less than</span></span>|<span data-ttu-id="01f9d-168">場合 (MyMsg.numOrders < 10).</span><span class="sxs-lookup"><span data-stu-id="01f9d-168">If (MyMsg.numOrders < 10)...</span></span>|  
|>|<span data-ttu-id="01f9d-169">より大きい</span><span class="sxs-lookup"><span data-stu-id="01f9d-169">Greater than</span></span>|<span data-ttu-id="01f9d-170">場合 (MyMsg.numOrders > 10).</span><span class="sxs-lookup"><span data-stu-id="01f9d-170">If (MyMsg.numOrders > 10)...</span></span>|  
|<=|<span data-ttu-id="01f9d-171">以下</span><span class="sxs-lookup"><span data-stu-id="01f9d-171">Less than or equal to</span></span>|<span data-ttu-id="01f9d-172">場合 (MyMsg.numOrders < = 10).</span><span class="sxs-lookup"><span data-stu-id="01f9d-172">If (MyMsg.numOrders <= 10)...</span></span>|  
|>=|<span data-ttu-id="01f9d-173">以上</span><span class="sxs-lookup"><span data-stu-id="01f9d-173">Greater than or equal to</span></span>|<span data-ttu-id="01f9d-174">場合 (MyMsg.numOrders > = 10).</span><span class="sxs-lookup"><span data-stu-id="01f9d-174">If (MyMsg.numOrders >= 10)...</span></span>|  
|==|<span data-ttu-id="01f9d-175">等しい</span><span class="sxs-lookup"><span data-stu-id="01f9d-175">Equal to</span></span>|<span data-ttu-id="01f9d-176">If (MyMsg.numOrders == 10)...</span><span class="sxs-lookup"><span data-stu-id="01f9d-176">If (MyMsg.numOrders == 10)...</span></span>|  
|<span data-ttu-id="01f9d-177">!=</span><span class="sxs-lookup"><span data-stu-id="01f9d-177">!=</span></span>|<span data-ttu-id="01f9d-178">次の値に等しくない</span><span class="sxs-lookup"><span data-stu-id="01f9d-178">Not equal to</span></span>|<span data-ttu-id="01f9d-179">場合 (MyMsg.numOrders! = 10).</span><span class="sxs-lookup"><span data-stu-id="01f9d-179">If (MyMsg.numOrders != 10)...</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="01f9d-180">参照</span><span class="sxs-lookup"><span data-stu-id="01f9d-180">See Also</span></span>  
 <span data-ttu-id="01f9d-181">[Xlang-s データ型](../core/xlang-s-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="01f9d-181">[XLANG-s Data Types](../core/xlang-s-data-types.md) </span></span>  
 <span data-ttu-id="01f9d-182">[Xlang-s ステートメント](../core/xlang-s-statements.md) </span><span class="sxs-lookup"><span data-stu-id="01f9d-182">[XLANG-s Statements](../core/xlang-s-statements.md) </span></span>  
 <span data-ttu-id="01f9d-183">[Xlang-s 式](../core/xlang-s-expressions.md) </span><span class="sxs-lookup"><span data-stu-id="01f9d-183">[XLANG-s Expressions](../core/xlang-s-expressions.md) </span></span>  
 <span data-ttu-id="01f9d-184">[Xlang-s の予約語](../core/xlang-s-reserved-words.md) </span><span class="sxs-lookup"><span data-stu-id="01f9d-184">[XLANG-s Reserved Words](../core/xlang-s-reserved-words.md) </span></span>  
 [<span data-ttu-id="01f9d-185">XLANG-s から BPEL4WS への種類の変換</span><span class="sxs-lookup"><span data-stu-id="01f9d-185">XLANG-s to BPEL4WS Type Conversions</span></span>](../core/xlang-s-to-bpel4ws-type-conversions.md)