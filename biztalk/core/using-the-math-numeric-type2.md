---
title: MATH_NUMERIC 型 2 を使用して |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- exponents, JD Edwards OneWorld adapters
- currency, JD Edwards OneWorld adapters
- MATH_NUMERIC type
- adapters [JD Edwards OneWorld adapters], currency
ms.assetid: 14d04576-0028-4af4-84bd-92c4ca492126
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 13de687f158bc18f4fa6a036ab239a25774d02ba
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998907"
---
# <a name="using-the-mathnumeric-type"></a><span data-ttu-id="3dd0a-102">MATH_NUMERIC 型の使用</span><span class="sxs-lookup"><span data-stu-id="3dd0a-102">Using the MATH_NUMERIC Type</span></span>
<span data-ttu-id="3dd0a-103">ここでは、MATH_NUMERIC 型および指数の処理方法、最大桁数、および最大 10 進桁数の詳細について説明します。</span><span class="sxs-lookup"><span data-stu-id="3dd0a-103">This topic describes the MATH_NUMERIC type and details how exponents are handled, the maximum number of digits, and the maximum number of decimal digits.</span></span> <span data-ttu-id="3dd0a-104">次の項目についても説明します。</span><span class="sxs-lookup"><span data-stu-id="3dd0a-104">It also includes a discussion on the following:</span></span>  
  
- <span data-ttu-id="3dd0a-105">指数</span><span class="sxs-lookup"><span data-stu-id="3dd0a-105">Exponents</span></span>  
  
- <span data-ttu-id="3dd0a-106">無効な値</span><span class="sxs-lookup"><span data-stu-id="3dd0a-106">Invalid Values</span></span>  
  
- <span data-ttu-id="3dd0a-107">演算の精度</span><span class="sxs-lookup"><span data-stu-id="3dd0a-107">Precision for Operations</span></span>  
  
- <span data-ttu-id="3dd0a-108">通貨</span><span class="sxs-lookup"><span data-stu-id="3dd0a-108">Currency</span></span>  
  
  <span data-ttu-id="3dd0a-109">MATH_NUMERIC 型は数値文字列型です。</span><span class="sxs-lookup"><span data-stu-id="3dd0a-109">The MATH_NUMERIC type is a numeric string type.</span></span> <span data-ttu-id="3dd0a-110">この型を使用するには、次の形式のパラメーター値を入力します。</span><span class="sxs-lookup"><span data-stu-id="3dd0a-110">To use it, enter parameter values of the following format:</span></span>  
  
```  
<OptionalSign><IntegerAndFractionalPart><OptionalExponentPart>  
```  
  
 <span data-ttu-id="3dd0a-111">場所</span><span class="sxs-lookup"><span data-stu-id="3dd0a-111">Where</span></span>  
  
- <span data-ttu-id="3dd0a-112">`<OptionalSign>` `+`または`-`します。</span><span class="sxs-lookup"><span data-stu-id="3dd0a-112">`<OptionalSign>` can be `+` or `-`.</span></span> <span data-ttu-id="3dd0a-113">`+` 既定値です。</span><span class="sxs-lookup"><span data-stu-id="3dd0a-113">`+` is the default.</span></span>  
  
- <span data-ttu-id="3dd0a-114">`<IntegerAndFractionalPart>` は最大 32 桁で、小数点記号は含みません。</span><span class="sxs-lookup"><span data-stu-id="3dd0a-114">`<IntegerAndFractionalPart>` is a maximum of 32 significant digits, not counting the decimal symbol.</span></span> <span data-ttu-id="3dd0a-115">この小数点の記号は JD Edwards OneWorld インストールのロケールに固有であり、通常はピリオド (.) またはコンマ (,) となります。</span><span class="sxs-lookup"><span data-stu-id="3dd0a-115">The decimal symbol is locale-specific to the JD Edwards OneWorld installation—typically a period (.) or a comma (,).</span></span> <span data-ttu-id="3dd0a-116">値はすべて整数、すべて小数、または整数と小数の組み合わせのいずれでもかまいませんが、32 桁を超えることはできません。</span><span class="sxs-lookup"><span data-stu-id="3dd0a-116">The digits may be all integer, all fraction, or part integer and part fraction, but they cannot exceed 32.</span></span>  
  
- <span data-ttu-id="3dd0a-117">`<OptionalExponentPart>` は次の記述と同じです。</span><span class="sxs-lookup"><span data-stu-id="3dd0a-117">`<OptionalExponentPart>` is equivalent to:</span></span>  
  
  ```  
  'e' <OptionalSign><ExponentDigits>  
  ```  
  
  <span data-ttu-id="3dd0a-118">場所</span><span class="sxs-lookup"><span data-stu-id="3dd0a-118">Where</span></span>  
  
- <span data-ttu-id="3dd0a-119">`<OptionalSign>` `+`またはします。</span><span class="sxs-lookup"><span data-stu-id="3dd0a-119">`<OptionalSign>` can be `+` or -.</span></span> <span data-ttu-id="3dd0a-120">`+` 既定値です。</span><span class="sxs-lookup"><span data-stu-id="3dd0a-120">`+` is the default.</span></span>  
  
- <span data-ttu-id="3dd0a-121">`<ExponentDigits>` は最大 2 桁です。</span><span class="sxs-lookup"><span data-stu-id="3dd0a-121">`<ExponentDigits>` are at most two digits.</span></span> <span data-ttu-id="3dd0a-122">指定できる値は、-63 ～ 63 です (0 は除く)。</span><span class="sxs-lookup"><span data-stu-id="3dd0a-122">You are permitted values between 63 and -63 excluding zero.</span></span>  
  
## <a name="valid-values"></a><span data-ttu-id="3dd0a-123">有効な値</span><span class="sxs-lookup"><span data-stu-id="3dd0a-123">Valid Values</span></span>  
 <span data-ttu-id="3dd0a-124">有効な MATH_NUMERIC 値の例は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="3dd0a-124">Examples of valid MATH_NUMERIC values:</span></span>  
  
-   <span data-ttu-id="3dd0a-125">123.045</span><span class="sxs-lookup"><span data-stu-id="3dd0a-125">123.045</span></span>  
  
-   <span data-ttu-id="3dd0a-126">4089 (3 桁ごとのコンマがないことに注意してください)</span><span class="sxs-lookup"><span data-stu-id="3dd0a-126">4089 (note there is no comma for thousands)</span></span>  
  
-   <span data-ttu-id="3dd0a-127">-9084</span><span class="sxs-lookup"><span data-stu-id="3dd0a-127">-9084</span></span>  
  
-   <span data-ttu-id="3dd0a-128">-230.75</span><span class="sxs-lookup"><span data-stu-id="3dd0a-128">-230.75</span></span>  
  
-   <span data-ttu-id="3dd0a-129">0.010503</span><span class="sxs-lookup"><span data-stu-id="3dd0a-129">0.010503</span></span>  
  
-   <span data-ttu-id="3dd0a-130">1.023e-10 は、0.0000000001023 と同じです</span><span class="sxs-lookup"><span data-stu-id="3dd0a-130">1.023e-10, which is equivalent to 0.0000000001023</span></span>  
  
-   <span data-ttu-id="3dd0a-131">0.097e5 または 0.097e+5 は、9700 と同じです</span><span class="sxs-lookup"><span data-stu-id="3dd0a-131">0.097e5 or 0.097e+5, which is equivalent to 9700</span></span>  
  
-   <span data-ttu-id="3dd0a-132">1.0e-32 (0.00000000000000000000000000000001 に等しい)</span><span class="sxs-lookup"><span data-stu-id="3dd0a-132">1.0e-32, which is equivalent to 0.00000000000000000000000000000001</span></span>  
  
     <span data-ttu-id="3dd0a-133">(この値が有効なのは、整数 '0' が無視され、小数点以下の桁数が 32 であるためです。)</span><span class="sxs-lookup"><span data-stu-id="3dd0a-133">(This is valid because in this case the integral '0' is ignored, 32 significant fractional digits.)</span></span>  
  
## <a name="invalid-values"></a><span data-ttu-id="3dd0a-134">無効な値</span><span class="sxs-lookup"><span data-stu-id="3dd0a-134">Invalid Values</span></span>  
 <span data-ttu-id="3dd0a-135">無効な値は値の種類に依存します。</span><span class="sxs-lookup"><span data-stu-id="3dd0a-135">Invalid values depend on the kind of value.</span></span> <span data-ttu-id="3dd0a-136">小さすぎる小数部はゼロと解釈されます (すべての有効桁が失われます)。</span><span class="sxs-lookup"><span data-stu-id="3dd0a-136">A decimal fraction that is too small is interpreted as zero (all significant digits are lost).</span></span> <span data-ttu-id="3dd0a-137">有効桁が多すぎる整数は、予期しない結果になります。</span><span class="sxs-lookup"><span data-stu-id="3dd0a-137">An integer that has too many significant digits causes unexpected results.</span></span> <span data-ttu-id="3dd0a-138">こ場合、必ずしもエラー状態が発生するとは限りません。</span><span class="sxs-lookup"><span data-stu-id="3dd0a-138">JD Edwards OneWorld does not always raise an error condition in this case.</span></span>  
  
 <span data-ttu-id="3dd0a-139">指数が大きすぎるか小さは、無効な値として返します。</span><span class="sxs-lookup"><span data-stu-id="3dd0a-139">An exponent that is too large or small returns as an invalid value.</span></span>  
  
 <span data-ttu-id="3dd0a-140">無効な MATH_NUMERIC 値の例は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="3dd0a-140">Examples of invalid MATH_NUMERIC values:</span></span>  
  
- <span data-ttu-id="3dd0a-141">1034.00000000000000000000000000001023 - 有効桁が多すぎます</span><span class="sxs-lookup"><span data-stu-id="3dd0a-141">1034.00000000000000000000000000001023 - too many significant digits</span></span>  
  
- <span data-ttu-id="3dd0a-142">1.023e-64 - 指数部が小さすぎます</span><span class="sxs-lookup"><span data-stu-id="3dd0a-142">1.023e-64 - exponent too small</span></span>  
  
- <span data-ttu-id="3dd0a-143">0.00317e64 - 指数部が大きすぎます</span><span class="sxs-lookup"><span data-stu-id="3dd0a-143">0.00317e64 - exponent too large</span></span>  
  
  <span data-ttu-id="3dd0a-144">符合と小数点記号以外に数字以外の文字が含まれていると、無効な値になります。</span><span class="sxs-lookup"><span data-stu-id="3dd0a-144">Any non-numeric characters other than those appropriate for signs and decimal symbols result in an invalid value.</span></span>  
  
## <a name="exponents"></a><span data-ttu-id="3dd0a-145">指数</span><span class="sxs-lookup"><span data-stu-id="3dd0a-145">Exponents</span></span>  
 <span data-ttu-id="3dd0a-146">値を入力しやすくするために、JD Edwards OneWorld MATH_NUMERIC により、指数が指定されます。</span><span class="sxs-lookup"><span data-stu-id="3dd0a-146">Exponents are provided by the JD Edwards OneWorld MATH_NUMERIC as a convenience for entering values.</span></span> <span data-ttu-id="3dd0a-147">ただし、ほとんどの値は指数なしで返ります (32 有効桁がすべて示されます)。</span><span class="sxs-lookup"><span data-stu-id="3dd0a-147">However, most values return without exponents (with all 32 significant digits visible).</span></span>  
  
## <a name="precision-for-operations"></a><span data-ttu-id="3dd0a-148">演算の精度</span><span class="sxs-lookup"><span data-stu-id="3dd0a-148">Precision for Operations</span></span>  
 <span data-ttu-id="3dd0a-149">演算によって精度が失われると、丸めが行われます。</span><span class="sxs-lookup"><span data-stu-id="3dd0a-149">If an operation results in loss of precision, rounding occurs.</span></span> <span data-ttu-id="3dd0a-150">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="3dd0a-150">For example:</span></span>  
  
 <span data-ttu-id="3dd0a-151">1.9e-31 / 10.0 = 0.00000000000000000000000000000002</span><span class="sxs-lookup"><span data-stu-id="3dd0a-151">1.9e-31 / 10.0 = 0.00000000000000000000000000000002</span></span>  
  
 <span data-ttu-id="3dd0a-152">1.9e-31/100.0 = 0.00000000000000000000000000000000</span><span class="sxs-lookup"><span data-stu-id="3dd0a-152">1.9e-31 / 100.0 = 0.00000000000000000000000000000000</span></span>  
  
 <span data-ttu-id="3dd0a-153">それ以外では、非常に大きい正の値どうしを乗算した場合に、予期しない結果が発生します。</span><span class="sxs-lookup"><span data-stu-id="3dd0a-153">In other cases, unpredictable results occur, as when a very large positive value is multiplied by another.</span></span>  
  
 <span data-ttu-id="3dd0a-154">1.01e32 \* 2.053e32 信頼性の高い結果を生成しないと、エラーは発生しません。</span><span class="sxs-lookup"><span data-stu-id="3dd0a-154">1.01e32 \* 2.053e32 does not yield reliable results and does not raise an error.</span></span>  
  
 <span data-ttu-id="3dd0a-155">実際に使用する場合には、通常、これらの範囲を超えることはありません。</span><span class="sxs-lookup"><span data-stu-id="3dd0a-155">For most business scenarios, these ranges are not exceeded.</span></span>  
  
## <a name="currency"></a><span data-ttu-id="3dd0a-156">通貨</span><span class="sxs-lookup"><span data-stu-id="3dd0a-156">Currency</span></span>  
 <span data-ttu-id="3dd0a-157">JD Edwards OneWorld のビジネス関数が通貨値を予期している場合、常に 4 文字の通貨コード用の別のパラメーターがあります。</span><span class="sxs-lookup"><span data-stu-id="3dd0a-157">When a JD Edwards OneWorld business function expects a currency value, the business function always has a separate parameter for a four-character currency code.</span></span> <span data-ttu-id="3dd0a-158">JD Edwards OneWorld システム用に構成された既定値とは異なる通貨を使用しない限り、このコードを渡す必要はありません。</span><span class="sxs-lookup"><span data-stu-id="3dd0a-158">It is not necessary to pass in this code unless you are using a currency other than the default configured for the JD Edwards OneWorld system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3dd0a-159">参照</span><span class="sxs-lookup"><span data-stu-id="3dd0a-159">See Also</span></span>  
 [<span data-ttu-id="3dd0a-160">付録 A: データ型</span><span class="sxs-lookup"><span data-stu-id="3dd0a-160">Appendix A: Data Types</span></span>](../core/appendix-a-data-types.md)