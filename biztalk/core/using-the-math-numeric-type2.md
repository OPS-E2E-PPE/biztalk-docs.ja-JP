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
ms.openlocfilehash: ba2390cb20b053fa20c460f670975702772d0ab3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396020"
---
# <a name="using-the-mathnumeric-type"></a><span data-ttu-id="6de9b-102">MATH_NUMERIC 型の使用</span><span class="sxs-lookup"><span data-stu-id="6de9b-102">Using the MATH_NUMERIC Type</span></span>
<span data-ttu-id="6de9b-103">このトピックでは、MATH_NUMERIC 型および指数の処理方法の詳細、桁の数字の最大数および 10 進数字の最大数について説明します。</span><span class="sxs-lookup"><span data-stu-id="6de9b-103">This topic describes the MATH_NUMERIC type and details how exponents are handled, the maximum number of digits, and the maximum number of decimal digits.</span></span> <span data-ttu-id="6de9b-104">次のディスカッションも含まれています。</span><span class="sxs-lookup"><span data-stu-id="6de9b-104">It also includes a discussion on the following:</span></span>  
  
- <span data-ttu-id="6de9b-105">指数</span><span class="sxs-lookup"><span data-stu-id="6de9b-105">Exponents</span></span>  
  
- <span data-ttu-id="6de9b-106">無効な値</span><span class="sxs-lookup"><span data-stu-id="6de9b-106">Invalid Values</span></span>  
  
- <span data-ttu-id="6de9b-107">操作の有効桁数</span><span class="sxs-lookup"><span data-stu-id="6de9b-107">Precision for Operations</span></span>  
  
- <span data-ttu-id="6de9b-108">通貨</span><span class="sxs-lookup"><span data-stu-id="6de9b-108">Currency</span></span>  
  
  <span data-ttu-id="6de9b-109">MATH_NUMERIC 型は、数値の文字列型です。</span><span class="sxs-lookup"><span data-stu-id="6de9b-109">The MATH_NUMERIC type is a numeric string type.</span></span> <span data-ttu-id="6de9b-110">これを使用するには、次の形式のパラメーター値を入力します。</span><span class="sxs-lookup"><span data-stu-id="6de9b-110">To use it, enter parameter values of the following format:</span></span>  
  
```  
<OptionalSign><IntegerAndFractionalPart><OptionalExponentPart>  
```  
  
 <span data-ttu-id="6de9b-111">場所</span><span class="sxs-lookup"><span data-stu-id="6de9b-111">Where</span></span>  
  
- <span data-ttu-id="6de9b-112">`<OptionalSign>` には、`+` または `-` を指定できます。</span><span class="sxs-lookup"><span data-stu-id="6de9b-112">`<OptionalSign>` can be `+` or `-`.</span></span> <span data-ttu-id="6de9b-113">`+` 既定値です。</span><span class="sxs-lookup"><span data-stu-id="6de9b-113">`+` is the default.</span></span>  
  
- <span data-ttu-id="6de9b-114">`<IntegerAndFractionalPart>` 最大 32 桁で小数点の記号を含みません。</span><span class="sxs-lookup"><span data-stu-id="6de9b-114">`<IntegerAndFractionalPart>` is a maximum of 32 significant digits, not counting the decimal symbol.</span></span> <span data-ttu-id="6de9b-115">小数点の記号はロケール固有 JD Edwards OneWorld のインストールに、通常はピリオド (.) またはコンマ (,) です。</span><span class="sxs-lookup"><span data-stu-id="6de9b-115">The decimal symbol is locale-specific to the JD Edwards OneWorld installation—typically a period (.) or a comma (,).</span></span> <span data-ttu-id="6de9b-116">数字の中にすべての整数、すべて小数、または一部整数および一部の分数を使用できますが、32 を超えることはできません。</span><span class="sxs-lookup"><span data-stu-id="6de9b-116">The digits may be all integer, all fraction, or part integer and part fraction, but they cannot exceed 32.</span></span>  
  
- <span data-ttu-id="6de9b-117">`<OptionalExponentPart>` 等価です。</span><span class="sxs-lookup"><span data-stu-id="6de9b-117">`<OptionalExponentPart>` is equivalent to:</span></span>  
  
  ```  
  'e' <OptionalSign><ExponentDigits>  
  ```  
  
  <span data-ttu-id="6de9b-118">場所</span><span class="sxs-lookup"><span data-stu-id="6de9b-118">Where</span></span>  
  
- <span data-ttu-id="6de9b-119">`<OptionalSign>` `+`またはします。</span><span class="sxs-lookup"><span data-stu-id="6de9b-119">`<OptionalSign>` can be `+` or -.</span></span> <span data-ttu-id="6de9b-120">`+` 既定値です。</span><span class="sxs-lookup"><span data-stu-id="6de9b-120">`+` is the default.</span></span>  
  
- <span data-ttu-id="6de9b-121">`<ExponentDigits>` 2 桁の数字は最大です。</span><span class="sxs-lookup"><span data-stu-id="6de9b-121">`<ExponentDigits>` are at most two digits.</span></span> <span data-ttu-id="6de9b-122">63 ~ 0 を除く-63 の値が許可されます。</span><span class="sxs-lookup"><span data-stu-id="6de9b-122">You are permitted values between 63 and -63 excluding zero.</span></span>  
  
## <a name="valid-values"></a><span data-ttu-id="6de9b-123">有効な値</span><span class="sxs-lookup"><span data-stu-id="6de9b-123">Valid Values</span></span>  
 <span data-ttu-id="6de9b-124">有効な MATH_NUMERIC 値の例:</span><span class="sxs-lookup"><span data-stu-id="6de9b-124">Examples of valid MATH_NUMERIC values:</span></span>  
  
-   <span data-ttu-id="6de9b-125">123.045</span><span class="sxs-lookup"><span data-stu-id="6de9b-125">123.045</span></span>  
  
-   <span data-ttu-id="6de9b-126">4089 (数千にコンマがない場合に注意してください)</span><span class="sxs-lookup"><span data-stu-id="6de9b-126">4089 (note there is no comma for thousands)</span></span>  
  
-   <span data-ttu-id="6de9b-127">-9084</span><span class="sxs-lookup"><span data-stu-id="6de9b-127">-9084</span></span>  
  
-   <span data-ttu-id="6de9b-128">-230.75</span><span class="sxs-lookup"><span data-stu-id="6de9b-128">-230.75</span></span>  
  
-   <span data-ttu-id="6de9b-129">0.010503</span><span class="sxs-lookup"><span data-stu-id="6de9b-129">0.010503</span></span>  
  
-   <span data-ttu-id="6de9b-130">1.023e-10 では、これは 0.0000000001023 に相当</span><span class="sxs-lookup"><span data-stu-id="6de9b-130">1.023e-10, which is equivalent to 0.0000000001023</span></span>  
  
-   <span data-ttu-id="6de9b-131">0.097 e 5 または 0.097 e + 5 は、9700 と同じです。</span><span class="sxs-lookup"><span data-stu-id="6de9b-131">0.097e5 or 0.097e+5, which is equivalent to 9700</span></span>  
  
-   <span data-ttu-id="6de9b-132">数が 1.0 e-32、0.00000000000000000000000000000001 と同じになります</span><span class="sxs-lookup"><span data-stu-id="6de9b-132">1.0e-32, which is equivalent to 0.00000000000000000000000000000001</span></span>  
  
     <span data-ttu-id="6de9b-133">(この場合、整数 '0' は無視されます、ため、これは有効な 32 小数点以下の桁数)。</span><span class="sxs-lookup"><span data-stu-id="6de9b-133">(This is valid because in this case the integral '0' is ignored, 32 significant fractional digits.)</span></span>  
  
## <a name="invalid-values"></a><span data-ttu-id="6de9b-134">無効な値</span><span class="sxs-lookup"><span data-stu-id="6de9b-134">Invalid Values</span></span>  
 <span data-ttu-id="6de9b-135">無効な値は、値の種類によって異なります。</span><span class="sxs-lookup"><span data-stu-id="6de9b-135">Invalid values depend on the kind of value.</span></span> <span data-ttu-id="6de9b-136">小さすぎる小数部は 0 として解釈されます (すべての有効桁数が失われます)。</span><span class="sxs-lookup"><span data-stu-id="6de9b-136">A decimal fraction that is too small is interpreted as zero (all significant digits are lost).</span></span> <span data-ttu-id="6de9b-137">有効桁が多すぎますが整数には、予期しない結果をによりします。</span><span class="sxs-lookup"><span data-stu-id="6de9b-137">An integer that has too many significant digits causes unexpected results.</span></span> <span data-ttu-id="6de9b-138">JD Edwards OneWorld 常には発生しませんエラー条件は、この場合。</span><span class="sxs-lookup"><span data-stu-id="6de9b-138">JD Edwards OneWorld does not always raise an error condition in this case.</span></span>  
  
 <span data-ttu-id="6de9b-139">指数が大きすぎるか小さは、無効な値として返します。</span><span class="sxs-lookup"><span data-stu-id="6de9b-139">An exponent that is too large or small returns as an invalid value.</span></span>  
  
 <span data-ttu-id="6de9b-140">無効な MATH_NUMERIC 値の例:</span><span class="sxs-lookup"><span data-stu-id="6de9b-140">Examples of invalid MATH_NUMERIC values:</span></span>  
  
- <span data-ttu-id="6de9b-141">1034.00000000000000000000000000001023 - 有効桁が多すぎます</span><span class="sxs-lookup"><span data-stu-id="6de9b-141">1034.00000000000000000000000000001023 - too many significant digits</span></span>  
  
- <span data-ttu-id="6de9b-142">1.023e-64 - 指数部が小さすぎます</span><span class="sxs-lookup"><span data-stu-id="6de9b-142">1.023e-64 - exponent too small</span></span>  
  
- <span data-ttu-id="6de9b-143">0.00317 e 64 - 指数部が大きすぎます</span><span class="sxs-lookup"><span data-stu-id="6de9b-143">0.00317e64 - exponent too large</span></span>  
  
  <span data-ttu-id="6de9b-144">記号と小数点の記号の適切なもの以外の数字以外の文字と、値が無効です。</span><span class="sxs-lookup"><span data-stu-id="6de9b-144">Any non-numeric characters other than those appropriate for signs and decimal symbols result in an invalid value.</span></span>  
  
## <a name="exponents"></a><span data-ttu-id="6de9b-145">指数</span><span class="sxs-lookup"><span data-stu-id="6de9b-145">Exponents</span></span>  
 <span data-ttu-id="6de9b-146">指数は、値を入力するため便利なように、JD Edwards OneWorld MATH_NUMERIC によって提供されます。</span><span class="sxs-lookup"><span data-stu-id="6de9b-146">Exponents are provided by the JD Edwards OneWorld MATH_NUMERIC as a convenience for entering values.</span></span> <span data-ttu-id="6de9b-147">ただし、ほとんどの値は指数せず (すべて 32 桁で表示される) に戻ります。</span><span class="sxs-lookup"><span data-stu-id="6de9b-147">However, most values return without exponents (with all 32 significant digits visible).</span></span>  
  
## <a name="precision-for-operations"></a><span data-ttu-id="6de9b-148">操作の有効桁数</span><span class="sxs-lookup"><span data-stu-id="6de9b-148">Precision for Operations</span></span>  
 <span data-ttu-id="6de9b-149">有効桁数が失われる演算によって、丸め処理に発生します。</span><span class="sxs-lookup"><span data-stu-id="6de9b-149">If an operation results in loss of precision, rounding occurs.</span></span> <span data-ttu-id="6de9b-150">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="6de9b-150">For example:</span></span>  
  
 <span data-ttu-id="6de9b-151">1.9e-31 / 10.0 = 0.00000000000000000000000000000002</span><span class="sxs-lookup"><span data-stu-id="6de9b-151">1.9e-31 / 10.0 = 0.00000000000000000000000000000002</span></span>  
  
 <span data-ttu-id="6de9b-152">1.9e-31 / 100.0 = 0.00000000000000000000000000000000</span><span class="sxs-lookup"><span data-stu-id="6de9b-152">1.9e-31 / 100.0 = 0.00000000000000000000000000000000</span></span>  
  
 <span data-ttu-id="6de9b-153">その他の場合は、予期しない結果が発生をもう 1 つ非常に大きい正の値を乗算する場合。</span><span class="sxs-lookup"><span data-stu-id="6de9b-153">In other cases, unpredictable results occur, as when a very large positive value is multiplied by another.</span></span>  
  
 <span data-ttu-id="6de9b-154">1.01e32 \* 2.053e32 信頼性の高い結果を生成しないと、エラーは発生しません。</span><span class="sxs-lookup"><span data-stu-id="6de9b-154">1.01e32 \* 2.053e32 does not yield reliable results and does not raise an error.</span></span>  
  
 <span data-ttu-id="6de9b-155">ほとんどのビジネス シナリオでは、これらの範囲が超過していません。</span><span class="sxs-lookup"><span data-stu-id="6de9b-155">For most business scenarios, these ranges are not exceeded.</span></span>  
  
## <a name="currency"></a><span data-ttu-id="6de9b-156">通貨</span><span class="sxs-lookup"><span data-stu-id="6de9b-156">Currency</span></span>  
 <span data-ttu-id="6de9b-157">JD Edwards OneWorld ビジネス関数には、通貨の値が必要ですが、ときに、ビジネス関数は常に 4 文字の通貨コード用の個別のパラメーターを持ちます。</span><span class="sxs-lookup"><span data-stu-id="6de9b-157">When a JD Edwards OneWorld business function expects a currency value, the business function always has a separate parameter for a four-character currency code.</span></span> <span data-ttu-id="6de9b-158">JD Edwards OneWorld システム用に構成された既定値以外の通貨を使用している場合を除き、このコードに渡す必要はありません。</span><span class="sxs-lookup"><span data-stu-id="6de9b-158">It is not necessary to pass in this code unless you are using a currency other than the default configured for the JD Edwards OneWorld system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6de9b-159">参照</span><span class="sxs-lookup"><span data-stu-id="6de9b-159">See Also</span></span>  
 [<span data-ttu-id="6de9b-160">付録 a:データ型</span><span class="sxs-lookup"><span data-stu-id="6de9b-160">Appendix A: Data Types</span></span>](../core/appendix-a-data-types.md)