---
title: MATH_NUMERIC 型 1 を使用して |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- adapters [JD Edwards EnterpriseOne adapters], currency
- JD Edwards EnterpriseOne adapters, exponents
- adapters [JD Edwards EnterpriseOne adapters], exponents
- MATH_NUMERIC type
- currency, values [JD Edwards EnterpriseOne adapters]
- JD Edwards EnterpriseOne adapters, currency
- exponents, values [JD Edwards EnterpriseOne adapters]
ms.assetid: 2a302216-f0a6-4afb-8f7d-bb1475ea1c57
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dba376c1bbbb6e5219969b97393f72380c75d9fa
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007531"
---
# <a name="using-the-mathnumeric-type"></a><span data-ttu-id="b547d-102">MATH_NUMERIC 型の使用</span><span class="sxs-lookup"><span data-stu-id="b547d-102">Using the MATH_NUMERIC Type</span></span>
<span data-ttu-id="b547d-103">ここでは、MATH_NUMERIC 型および指数の処理方法、最大桁数、および最大 10 進桁数の詳細について説明します。</span><span class="sxs-lookup"><span data-stu-id="b547d-103">This topic describes the MATH_NUMERIC type and details how exponents are handled, the maximum number of digits, and the maximum number of decimal digits.</span></span> <span data-ttu-id="b547d-104">また、次のものに関する説明も含まれています。</span><span class="sxs-lookup"><span data-stu-id="b547d-104">It also includes a discussion on:</span></span>  
  
- <span data-ttu-id="b547d-105">指数</span><span class="sxs-lookup"><span data-stu-id="b547d-105">Exponents</span></span>  
  
- <span data-ttu-id="b547d-106">無効な値</span><span class="sxs-lookup"><span data-stu-id="b547d-106">Invalid Values</span></span>  
  
- <span data-ttu-id="b547d-107">演算の精度</span><span class="sxs-lookup"><span data-stu-id="b547d-107">Precision for Operations</span></span>  
  
- <span data-ttu-id="b547d-108">通貨</span><span class="sxs-lookup"><span data-stu-id="b547d-108">Currency</span></span>  
  
  <span data-ttu-id="b547d-109">MATH_NUMERIC 型は数値文字列型です。</span><span class="sxs-lookup"><span data-stu-id="b547d-109">The MATH_NUMERIC type is a numeric string type.</span></span> <span data-ttu-id="b547d-110">この型を使用するには、次の形式のパラメーター値を入力します。</span><span class="sxs-lookup"><span data-stu-id="b547d-110">To use it, enter parameter values of the following format:</span></span>  
  
```  
<OptionalSign><IntegerAndFractionalPart><OptionalExponentPart>  
  
```  
  
 <span data-ttu-id="b547d-111">場所</span><span class="sxs-lookup"><span data-stu-id="b547d-111">Where</span></span>  
  
 <span data-ttu-id="b547d-112">`<OptionalSign>` `+`または`-`します。</span><span class="sxs-lookup"><span data-stu-id="b547d-112">`<OptionalSign>` can be `+` or `-`.</span></span> <span data-ttu-id="b547d-113">`+` 既定値です。</span><span class="sxs-lookup"><span data-stu-id="b547d-113">`+` is the default.</span></span>  
  
 <span data-ttu-id="b547d-114">`<IntegerAndFractionalPart>` は最大 32 桁で、小数点記号は含みません。</span><span class="sxs-lookup"><span data-stu-id="b547d-114">`<IntegerAndFractionalPart>` is a maximum of 32 significant digits, not counting the decimal symbol.</span></span> <span data-ttu-id="b547d-115">小数点の記号はロケール固有 JD Edwards EnterpriseOne のインストールに、通常はピリオド (.) またはコンマ (,) です。</span><span class="sxs-lookup"><span data-stu-id="b547d-115">The decimal symbol is locale-specific to the JD Edwards EnterpriseOne installation—typically a period (.) or a comma (,).</span></span> <span data-ttu-id="b547d-116">値はすべて整数、すべて小数、または整数と小数の組み合わせのいずれでもかまいませんが、32 桁を超えることはできません。</span><span class="sxs-lookup"><span data-stu-id="b547d-116">The digits may be all integer, all fraction, or part integer and part fraction, but they cannot exceed 32.</span></span>  
  
 <span data-ttu-id="b547d-117">`<OptionalExponentPart>` は次の記述と同じです。</span><span class="sxs-lookup"><span data-stu-id="b547d-117">`<OptionalExponentPart>` is equivalent to:</span></span>  
  
```  
'e' <OptionalSign><ExponentDigits>  
```  
  
 <span data-ttu-id="b547d-118">場所</span><span class="sxs-lookup"><span data-stu-id="b547d-118">Where</span></span>  
  
 <span data-ttu-id="b547d-119">`<OptionalSign>` `+`または`-`します。</span><span class="sxs-lookup"><span data-stu-id="b547d-119">`<OptionalSign>` can be `+` or `-`.</span></span> <span data-ttu-id="b547d-120">`+` 既定値です。</span><span class="sxs-lookup"><span data-stu-id="b547d-120">`+` is the default.</span></span>  
  
 <span data-ttu-id="b547d-121">`<ExponentDigits>` は最大 2 桁です。</span><span class="sxs-lookup"><span data-stu-id="b547d-121">`<ExponentDigits>` are at most two digits.</span></span> <span data-ttu-id="b547d-122">指定できる値は、-63 ～ 63 です (0 は除く)。</span><span class="sxs-lookup"><span data-stu-id="b547d-122">You are permitted values between 63 and -63 excluding zero.</span></span>  
  
## <a name="valid-values"></a><span data-ttu-id="b547d-123">有効な値</span><span class="sxs-lookup"><span data-stu-id="b547d-123">Valid Values</span></span>  
 <span data-ttu-id="b547d-124">例の**有効**MATH_NUMERIC 値。</span><span class="sxs-lookup"><span data-stu-id="b547d-124">Examples of **valid** MATH_NUMERIC values:</span></span>  
  
-   <span data-ttu-id="b547d-125">123.045</span><span class="sxs-lookup"><span data-stu-id="b547d-125">123.045</span></span>  
  
-   <span data-ttu-id="b547d-126">4089 (3 桁ごとのコンマがないことに注意してください)</span><span class="sxs-lookup"><span data-stu-id="b547d-126">4089 (note there is no comma for thousands)</span></span>  
  
-   <span data-ttu-id="b547d-127">-9084</span><span class="sxs-lookup"><span data-stu-id="b547d-127">-9084</span></span>  
  
-   <span data-ttu-id="b547d-128">-230.75</span><span class="sxs-lookup"><span data-stu-id="b547d-128">-230.75</span></span>  
  
-   <span data-ttu-id="b547d-129">0.010503</span><span class="sxs-lookup"><span data-stu-id="b547d-129">0.010503</span></span>  
  
-   <span data-ttu-id="b547d-130">1.023e-10 は、0.0000000001023 と同じです</span><span class="sxs-lookup"><span data-stu-id="b547d-130">1.023e-10, which is equivalent to 0.0000000001023</span></span>  
  
-   <span data-ttu-id="b547d-131">0.097e5 または 0.097e+5 は、9700 と同じです</span><span class="sxs-lookup"><span data-stu-id="b547d-131">0.097e5 or 0.097e+5, which is equivalent to 9700</span></span>  
  
-   <span data-ttu-id="b547d-132">1.0e-32 (0.00000000000000000000000000000001 と同じ。この値が有効なのは、整数 "0" が無視され、小数点以下の桁数が 32 であるためです)</span><span class="sxs-lookup"><span data-stu-id="b547d-132">1.0e-32, which is equivalent to 0.00000000000000000000000000000001 (This is valid because in this case, the integral '0' is ignored, 32 significant fractional digits.)</span></span>  
  
## <a name="invalid-values"></a><span data-ttu-id="b547d-133">無効な値</span><span class="sxs-lookup"><span data-stu-id="b547d-133">Invalid Values</span></span>  
 <span data-ttu-id="b547d-134">無効な値は値の種類に依存します。</span><span class="sxs-lookup"><span data-stu-id="b547d-134">Invalid values depend on the kind of value.</span></span> <span data-ttu-id="b547d-135">小さすぎる小数部はゼロと解釈されます (すべての有効桁が失われます)。</span><span class="sxs-lookup"><span data-stu-id="b547d-135">A decimal fraction that is too small is interpreted as zero (all significant digits are lost).</span></span> <span data-ttu-id="b547d-136">有効桁が多すぎる整数は、予期しない結果になります。</span><span class="sxs-lookup"><span data-stu-id="b547d-136">An integer that has too many significant digits causes unexpected results.</span></span> <span data-ttu-id="b547d-137">この場合、必ずしもエラー状態が発生するとは限りません。</span><span class="sxs-lookup"><span data-stu-id="b547d-137">JD Edwards EnterpriseOne does not always raise an error condition in this case.</span></span> <span data-ttu-id="b547d-138">指数が長すぎるか短すぎても、無効な値が返されます。</span><span class="sxs-lookup"><span data-stu-id="b547d-138">An exponent that is too large or too small also returns as an invalid value.</span></span>  
  
 <span data-ttu-id="b547d-139">例の**無効な**MATH_NUMERIC 値。</span><span class="sxs-lookup"><span data-stu-id="b547d-139">Examples of **invalid** MATH_NUMERIC values:</span></span>  
  
- <span data-ttu-id="b547d-140">1034.00000000000000000000000000001023 - 有効桁が多すぎます</span><span class="sxs-lookup"><span data-stu-id="b547d-140">1034.00000000000000000000000000001023 - too many significant digits</span></span>  
  
- <span data-ttu-id="b547d-141">1.023e-64 - 指数部が小さすぎます</span><span class="sxs-lookup"><span data-stu-id="b547d-141">1.023e-64 - exponent too small</span></span>  
  
- <span data-ttu-id="b547d-142">0.00317e64 - 指数部が大きすぎます</span><span class="sxs-lookup"><span data-stu-id="b547d-142">0.00317e64 - exponent too large</span></span>  
  
  <span data-ttu-id="b547d-143">符合と小数点記号以外に数字以外の文字が含まれていると、無効な値になります。</span><span class="sxs-lookup"><span data-stu-id="b547d-143">Any non-numeric characters other than those appropriate for signs and decimal symbols result in an invalid value.</span></span>  
  
## <a name="exponents"></a><span data-ttu-id="b547d-144">指数</span><span class="sxs-lookup"><span data-stu-id="b547d-144">Exponents</span></span>  
 <span data-ttu-id="b547d-145">指数は、値を入力するため便利なように、JD Edwards EnterpriseOne MATH_NUMERIC によって提供されます。</span><span class="sxs-lookup"><span data-stu-id="b547d-145">Exponents are provided by the JD Edwards EnterpriseOne MATH_NUMERIC as a convenience for entering values.</span></span> <span data-ttu-id="b547d-146">ただし、ほとんどの値は指数なしで返ります (32 有効桁がすべて示されます)。</span><span class="sxs-lookup"><span data-stu-id="b547d-146">However, most values return without exponents (with all 32 significant digits visible).</span></span>  
  
## <a name="precision-for-operations"></a><span data-ttu-id="b547d-147">演算の精度</span><span class="sxs-lookup"><span data-stu-id="b547d-147">Precision for Operations</span></span>  
 <span data-ttu-id="b547d-148">演算によって精度が失われると、丸めが行われます。</span><span class="sxs-lookup"><span data-stu-id="b547d-148">If an operation results in loss of precision, rounding occurs.</span></span> <span data-ttu-id="b547d-149">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="b547d-149">For example:</span></span>  
  
 <span data-ttu-id="b547d-150">1.9e-31/10.0 = 0.00000000000000000000000000000002 します。</span><span class="sxs-lookup"><span data-stu-id="b547d-150">1.9e-31 / 10.0 = 0.00000000000000000000000000000002.</span></span>  
  
 <span data-ttu-id="b547d-151">1.9e-31/100.0 = 0.00000000000000000000000000000000</span><span class="sxs-lookup"><span data-stu-id="b547d-151">1.9e-31 / 100.0 = 0.00000000000000000000000000000000</span></span>  
  
 <span data-ttu-id="b547d-152">それ以外では、非常に大きい正の値どうしを乗算した場合に、予期しない結果が発生します。</span><span class="sxs-lookup"><span data-stu-id="b547d-152">In other cases, unpredictable results occur, as when a very large positive value is multiplied by another.</span></span> <span data-ttu-id="b547d-153">1.01e32 \* 2.053e32 信頼性の高い結果を生成しないと、エラーは発生しません。</span><span class="sxs-lookup"><span data-stu-id="b547d-153">1.01e32 \* 2.053e32 does not yield reliable results and does not raise an error.</span></span> <span data-ttu-id="b547d-154">実際に使用する場合には、通常、これらの範囲を超えることはありません。</span><span class="sxs-lookup"><span data-stu-id="b547d-154">For most business scenarios, these ranges are not exceeded.</span></span>  
  
## <a name="currency"></a><span data-ttu-id="b547d-155">通貨</span><span class="sxs-lookup"><span data-stu-id="b547d-155">Currency</span></span>  
 <span data-ttu-id="b547d-156">JD Edwards EnterpriseOne のビジネス関数が通貨値を予期している場合、常に 4 文字の通貨コード用の別のパラメーターがあります。</span><span class="sxs-lookup"><span data-stu-id="b547d-156">When a JD Edwards EnterpriseOne business function expects a currency value, the business function always has a separate parameter for a four-character currency code.</span></span> <span data-ttu-id="b547d-157">JD Edwards EnterpriseOne システム用に構成された既定値とは異なる通貨を使用しない限り、このコードを渡す必要はありません。</span><span class="sxs-lookup"><span data-stu-id="b547d-157">It is not necessary to pass in this code unless you are using a currency other than the default configured for the JD Edwards EnterpriseOne system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b547d-158">参照</span><span class="sxs-lookup"><span data-stu-id="b547d-158">See Also</span></span>  
 [<span data-ttu-id="b547d-159">付録 B: データ型</span><span class="sxs-lookup"><span data-stu-id="b547d-159">Appendix B: Data Types</span></span>](../core/appendix-b-data-types.md)