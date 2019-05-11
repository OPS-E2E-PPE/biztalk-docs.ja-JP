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
ms.openlocfilehash: 519605c89cc808c91e1045c191dc01ec46739ae8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396007"
---
# <a name="using-the-mathnumeric-type"></a><span data-ttu-id="381af-102">MATH_NUMERIC 型の使用</span><span class="sxs-lookup"><span data-stu-id="381af-102">Using the MATH_NUMERIC Type</span></span>
<span data-ttu-id="381af-103">このトピックでは、MATH_NUMERIC 型および指数の処理方法の詳細、桁の数字の最大数および 10 進数字の最大数について説明します。</span><span class="sxs-lookup"><span data-stu-id="381af-103">This topic describes the MATH_NUMERIC type and details how exponents are handled, the maximum number of digits, and the maximum number of decimal digits.</span></span> <span data-ttu-id="381af-104">詳細についてでも含まれます。</span><span class="sxs-lookup"><span data-stu-id="381af-104">It also includes a discussion on:</span></span>  
  
- <span data-ttu-id="381af-105">指数</span><span class="sxs-lookup"><span data-stu-id="381af-105">Exponents</span></span>  
  
- <span data-ttu-id="381af-106">無効な値</span><span class="sxs-lookup"><span data-stu-id="381af-106">Invalid Values</span></span>  
  
- <span data-ttu-id="381af-107">操作の有効桁数</span><span class="sxs-lookup"><span data-stu-id="381af-107">Precision for Operations</span></span>  
  
- <span data-ttu-id="381af-108">通貨</span><span class="sxs-lookup"><span data-stu-id="381af-108">Currency</span></span>  
  
  <span data-ttu-id="381af-109">MATH_NUMERIC 型は、数値の文字列型です。</span><span class="sxs-lookup"><span data-stu-id="381af-109">The MATH_NUMERIC type is a numeric string type.</span></span> <span data-ttu-id="381af-110">これを使用するには、次の形式のパラメーター値を入力します。</span><span class="sxs-lookup"><span data-stu-id="381af-110">To use it, enter parameter values of the following format:</span></span>  
  
```  
<OptionalSign><IntegerAndFractionalPart><OptionalExponentPart>  
  
```  
  
 <span data-ttu-id="381af-111">場所</span><span class="sxs-lookup"><span data-stu-id="381af-111">Where</span></span>  
  
 <span data-ttu-id="381af-112">`<OptionalSign>` には、`+` または `-` を指定できます。</span><span class="sxs-lookup"><span data-stu-id="381af-112">`<OptionalSign>` can be `+` or `-`.</span></span> <span data-ttu-id="381af-113">`+` 既定値です。</span><span class="sxs-lookup"><span data-stu-id="381af-113">`+` is the default.</span></span>  
  
 <span data-ttu-id="381af-114">`<IntegerAndFractionalPart>` 最大 32 桁で小数点の記号を含みません。</span><span class="sxs-lookup"><span data-stu-id="381af-114">`<IntegerAndFractionalPart>` is a maximum of 32 significant digits, not counting the decimal symbol.</span></span> <span data-ttu-id="381af-115">小数点の記号はロケール固有 JD Edwards EnterpriseOne のインストールに、通常はピリオド (.) またはコンマ (,) です。</span><span class="sxs-lookup"><span data-stu-id="381af-115">The decimal symbol is locale-specific to the JD Edwards EnterpriseOne installation—typically a period (.) or a comma (,).</span></span> <span data-ttu-id="381af-116">数字の中にすべての整数、すべて小数、または一部整数および一部の分数を使用できますが、32 を超えることはできません。</span><span class="sxs-lookup"><span data-stu-id="381af-116">The digits may be all integer, all fraction, or part integer and part fraction, but they cannot exceed 32.</span></span>  
  
 <span data-ttu-id="381af-117">`<OptionalExponentPart>` 等価です。</span><span class="sxs-lookup"><span data-stu-id="381af-117">`<OptionalExponentPart>` is equivalent to:</span></span>  
  
```  
'e' <OptionalSign><ExponentDigits>  
```  
  
 <span data-ttu-id="381af-118">場所</span><span class="sxs-lookup"><span data-stu-id="381af-118">Where</span></span>  
  
 <span data-ttu-id="381af-119">`<OptionalSign>` には、`+` または `-` を指定できます。</span><span class="sxs-lookup"><span data-stu-id="381af-119">`<OptionalSign>` can be `+` or `-`.</span></span> <span data-ttu-id="381af-120">`+` 既定値です。</span><span class="sxs-lookup"><span data-stu-id="381af-120">`+` is the default.</span></span>  
  
 <span data-ttu-id="381af-121">`<ExponentDigits>` 2 桁の数字は最大です。</span><span class="sxs-lookup"><span data-stu-id="381af-121">`<ExponentDigits>` are at most two digits.</span></span> <span data-ttu-id="381af-122">63 ~ 0 を除く-63 の値が許可されます。</span><span class="sxs-lookup"><span data-stu-id="381af-122">You are permitted values between 63 and -63 excluding zero.</span></span>  
  
## <a name="valid-values"></a><span data-ttu-id="381af-123">有効な値</span><span class="sxs-lookup"><span data-stu-id="381af-123">Valid Values</span></span>  
 <span data-ttu-id="381af-124">例の**有効**MATH_NUMERIC 値。</span><span class="sxs-lookup"><span data-stu-id="381af-124">Examples of **valid** MATH_NUMERIC values:</span></span>  
  
-   <span data-ttu-id="381af-125">123.045</span><span class="sxs-lookup"><span data-stu-id="381af-125">123.045</span></span>  
  
-   <span data-ttu-id="381af-126">4089 (数千にコンマがない場合に注意してください)</span><span class="sxs-lookup"><span data-stu-id="381af-126">4089 (note there is no comma for thousands)</span></span>  
  
-   <span data-ttu-id="381af-127">-9084</span><span class="sxs-lookup"><span data-stu-id="381af-127">-9084</span></span>  
  
-   <span data-ttu-id="381af-128">-230.75</span><span class="sxs-lookup"><span data-stu-id="381af-128">-230.75</span></span>  
  
-   <span data-ttu-id="381af-129">0.010503</span><span class="sxs-lookup"><span data-stu-id="381af-129">0.010503</span></span>  
  
-   <span data-ttu-id="381af-130">1.023e-10 では、これは 0.0000000001023 に相当</span><span class="sxs-lookup"><span data-stu-id="381af-130">1.023e-10, which is equivalent to 0.0000000001023</span></span>  
  
-   <span data-ttu-id="381af-131">0.097 e 5 または 0.097 e + 5 は、9700 と同じです。</span><span class="sxs-lookup"><span data-stu-id="381af-131">0.097e5 or 0.097e+5, which is equivalent to 9700</span></span>  
  
-   <span data-ttu-id="381af-132">数が 1.0 e-32、0.00000000000000000000000000000001 と同じになります (この場合、整数 '0' は無視されます、ため、これは有効な 32 小数点以下の桁数)。</span><span class="sxs-lookup"><span data-stu-id="381af-132">1.0e-32, which is equivalent to 0.00000000000000000000000000000001 (This is valid because in this case, the integral '0' is ignored, 32 significant fractional digits.)</span></span>  
  
## <a name="invalid-values"></a><span data-ttu-id="381af-133">無効な値</span><span class="sxs-lookup"><span data-stu-id="381af-133">Invalid Values</span></span>  
 <span data-ttu-id="381af-134">無効な値は、値の種類によって異なります。</span><span class="sxs-lookup"><span data-stu-id="381af-134">Invalid values depend on the kind of value.</span></span> <span data-ttu-id="381af-135">小さすぎる小数部は 0 として解釈されます (すべての有効桁数が失われます)。</span><span class="sxs-lookup"><span data-stu-id="381af-135">A decimal fraction that is too small is interpreted as zero (all significant digits are lost).</span></span> <span data-ttu-id="381af-136">有効桁が多すぎますが整数には、予期しない結果をによりします。</span><span class="sxs-lookup"><span data-stu-id="381af-136">An integer that has too many significant digits causes unexpected results.</span></span> <span data-ttu-id="381af-137">JD Edwards EnterpriseOne 常には発生しませんエラー条件は、この場合。</span><span class="sxs-lookup"><span data-stu-id="381af-137">JD Edwards EnterpriseOne does not always raise an error condition in this case.</span></span> <span data-ttu-id="381af-138">指数が大きすぎるか小さすぎるは、無効な値も返します。</span><span class="sxs-lookup"><span data-stu-id="381af-138">An exponent that is too large or too small also returns as an invalid value.</span></span>  
  
 <span data-ttu-id="381af-139">例の**無効な**MATH_NUMERIC 値。</span><span class="sxs-lookup"><span data-stu-id="381af-139">Examples of **invalid** MATH_NUMERIC values:</span></span>  
  
- <span data-ttu-id="381af-140">1034.00000000000000000000000000001023 - 有効桁が多すぎます</span><span class="sxs-lookup"><span data-stu-id="381af-140">1034.00000000000000000000000000001023 - too many significant digits</span></span>  
  
- <span data-ttu-id="381af-141">1.023e-64 - 指数部が小さすぎます</span><span class="sxs-lookup"><span data-stu-id="381af-141">1.023e-64 - exponent too small</span></span>  
  
- <span data-ttu-id="381af-142">0.00317 e 64 - 指数部が大きすぎます</span><span class="sxs-lookup"><span data-stu-id="381af-142">0.00317e64 - exponent too large</span></span>  
  
  <span data-ttu-id="381af-143">記号と小数点の記号の適切なもの以外の数字以外の文字と、値が無効です。</span><span class="sxs-lookup"><span data-stu-id="381af-143">Any non-numeric characters other than those appropriate for signs and decimal symbols result in an invalid value.</span></span>  
  
## <a name="exponents"></a><span data-ttu-id="381af-144">指数</span><span class="sxs-lookup"><span data-stu-id="381af-144">Exponents</span></span>  
 <span data-ttu-id="381af-145">指数は、値を入力するため便利なように、JD Edwards EnterpriseOne MATH_NUMERIC によって提供されます。</span><span class="sxs-lookup"><span data-stu-id="381af-145">Exponents are provided by the JD Edwards EnterpriseOne MATH_NUMERIC as a convenience for entering values.</span></span> <span data-ttu-id="381af-146">ただし、ほとんどの値は指数せず (すべて 32 桁で表示される) に戻ります。</span><span class="sxs-lookup"><span data-stu-id="381af-146">However, most values return without exponents (with all 32 significant digits visible).</span></span>  
  
## <a name="precision-for-operations"></a><span data-ttu-id="381af-147">操作の有効桁数</span><span class="sxs-lookup"><span data-stu-id="381af-147">Precision for Operations</span></span>  
 <span data-ttu-id="381af-148">有効桁数が失われる演算によって、丸め処理に発生します。</span><span class="sxs-lookup"><span data-stu-id="381af-148">If an operation results in loss of precision, rounding occurs.</span></span> <span data-ttu-id="381af-149">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="381af-149">For example:</span></span>  
  
 <span data-ttu-id="381af-150">1.9e-31/10.0 = 0.00000000000000000000000000000002 します。</span><span class="sxs-lookup"><span data-stu-id="381af-150">1.9e-31 / 10.0 = 0.00000000000000000000000000000002.</span></span>  
  
 <span data-ttu-id="381af-151">1.9e-31 / 100.0 = 0.00000000000000000000000000000000</span><span class="sxs-lookup"><span data-stu-id="381af-151">1.9e-31 / 100.0 = 0.00000000000000000000000000000000</span></span>  
  
 <span data-ttu-id="381af-152">その他の場合は、予期しない結果が発生をもう 1 つ非常に大きい正の値を乗算する場合。</span><span class="sxs-lookup"><span data-stu-id="381af-152">In other cases, unpredictable results occur, as when a very large positive value is multiplied by another.</span></span> <span data-ttu-id="381af-153">1.01e32 \* 2.053e32 信頼性の高い結果を生成しないと、エラーは発生しません。</span><span class="sxs-lookup"><span data-stu-id="381af-153">1.01e32 \* 2.053e32 does not yield reliable results and does not raise an error.</span></span> <span data-ttu-id="381af-154">ほとんどのビジネス シナリオでは、これらの範囲が超過していません。</span><span class="sxs-lookup"><span data-stu-id="381af-154">For most business scenarios, these ranges are not exceeded.</span></span>  
  
## <a name="currency"></a><span data-ttu-id="381af-155">通貨</span><span class="sxs-lookup"><span data-stu-id="381af-155">Currency</span></span>  
 <span data-ttu-id="381af-156">JD Edwards EnterpriseOne のビジネス関数には、通貨の値が必要ですが、ときに、ビジネス関数は常に 4 文字の通貨コード用の個別のパラメーターを持ちます。</span><span class="sxs-lookup"><span data-stu-id="381af-156">When a JD Edwards EnterpriseOne business function expects a currency value, the business function always has a separate parameter for a four-character currency code.</span></span> <span data-ttu-id="381af-157">JD Edwards EnterpriseOne システム用に構成された既定値以外の通貨を使用している場合を除き、このコードに渡す必要はありません。</span><span class="sxs-lookup"><span data-stu-id="381af-157">It is not necessary to pass in this code unless you are using a currency other than the default configured for the JD Edwards EnterpriseOne system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="381af-158">参照</span><span class="sxs-lookup"><span data-stu-id="381af-158">See Also</span></span>  
 [<span data-ttu-id="381af-159">付録 b:データ型</span><span class="sxs-lookup"><span data-stu-id="381af-159">Appendix B: Data Types</span></span>](../core/appendix-b-data-types.md)