---
title: Xlang-s から BPEL4WS への変換の入力 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- XLANG/s
- XLANG/s, warning
- XLANG/s, BPEL4WS
- XLANG/s, converting
ms.assetid: a35d4dba-9344-43c8-86e6-a373a4452579
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 84a184251428568305c553b63bbb164785758aca
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65244062"
---
# <a name="xlang-s-to-bpel4ws-type-conversions"></a><span data-ttu-id="c28f6-102">Xlang-s BPEL4WS 型への変換から</span><span class="sxs-lookup"><span data-stu-id="c28f6-102">XLANG-s to BPEL4WS Type Conversions</span></span>
<span data-ttu-id="c28f6-103">次の表では、さまざまな xlang/s 構成要素と BPEL4WS 構成要素の間の変換について説明します。</span><span class="sxs-lookup"><span data-stu-id="c28f6-103">The following tables detail the conversions between various XLANG/s constructs and BPEL4WS constructs.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="c28f6-104">XPath 1.1 は、指数関数的または double 形式の数字をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="c28f6-104">XPath 1.1 does not support numbers in exponential or double formats.</span></span> <span data-ttu-id="c28f6-105">Xlang/s オーケストレーションにおけるこれらの形式のリテラル値をエクスポートする BPEL4WS、%f 形式と精度の損失を使用してなる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c28f6-105">Literal values in these formats in XLANG/s orchestrations are exported to BPEL4WS using the %f format, and a loss of precision might result.</span></span>  
  
## <a name="literals-if-the-literal-is-part-of-an-expression"></a><span data-ttu-id="c28f6-106">リテラル (リテラルが式の一部である場合)</span><span class="sxs-lookup"><span data-stu-id="c28f6-106">Literals (if the literal is part of an expression)</span></span>  
  
|<span data-ttu-id="c28f6-107">XLANG/秒</span><span class="sxs-lookup"><span data-stu-id="c28f6-107">XLANG/s</span></span>|<span data-ttu-id="c28f6-108">BPEL4WS</span><span class="sxs-lookup"><span data-stu-id="c28f6-108">BPEL4WS</span></span>|  
|--------------|-------------|  
|<span data-ttu-id="c28f6-109">文字の文字列</span><span class="sxs-lookup"><span data-stu-id="c28f6-109">String, character</span></span>|<span data-ttu-id="c28f6-110">XPath 文字列</span><span class="sxs-lookup"><span data-stu-id="c28f6-110">XPath string</span></span>|  
|<span data-ttu-id="c28f6-111">整数、実数</span><span class="sxs-lookup"><span data-stu-id="c28f6-111">Integer, real</span></span>|<span data-ttu-id="c28f6-112">XPath 数値</span><span class="sxs-lookup"><span data-stu-id="c28f6-112">XPath number</span></span>|  
|<span data-ttu-id="c28f6-113">ブール値"true"、"false"</span><span class="sxs-lookup"><span data-stu-id="c28f6-113">Boolean "true", "false"</span></span>|<span data-ttu-id="c28f6-114">XPath true() 関数、false() 関数</span><span class="sxs-lookup"><span data-stu-id="c28f6-114">XPath true(), false() functions</span></span>|  
  
## <a name="literals-standalone-assignment"></a><span data-ttu-id="c28f6-115">リテラル (スタンドアロン代入)</span><span class="sxs-lookup"><span data-stu-id="c28f6-115">Literals (standalone assignment)</span></span>  
  
|<span data-ttu-id="c28f6-116">XLANG/秒</span><span class="sxs-lookup"><span data-stu-id="c28f6-116">XLANG/s</span></span>|<span data-ttu-id="c28f6-117">BPEL4WS</span><span class="sxs-lookup"><span data-stu-id="c28f6-117">BPEL4WS</span></span>|  
|--------------|-------------|  
|<span data-ttu-id="c28f6-118">リテラル定数</span><span class="sxs-lookup"><span data-stu-id="c28f6-118">Literal constant</span></span>|<span data-ttu-id="c28f6-119">XSD に相当</span><span class="sxs-lookup"><span data-stu-id="c28f6-119">XSD equivalent</span></span>|  
  
## <a name="variables"></a><span data-ttu-id="c28f6-120">変数:</span><span class="sxs-lookup"><span data-stu-id="c28f6-120">Variables</span></span>  
  
|<span data-ttu-id="c28f6-121">XLANG/秒</span><span class="sxs-lookup"><span data-stu-id="c28f6-121">XLANG/s</span></span>|<span data-ttu-id="c28f6-122">BPEL4WS</span><span class="sxs-lookup"><span data-stu-id="c28f6-122">BPEL4WS</span></span>|  
|--------------|-------------|  
|<span data-ttu-id="c28f6-123">変数参照</span><span class="sxs-lookup"><span data-stu-id="c28f6-123">Variable reference</span></span>|<span data-ttu-id="c28f6-124">bpws:getContainerData(%varName%, part, %locationPath%)</span><span class="sxs-lookup"><span data-stu-id="c28f6-124">bpws:getContainerData(%varName%,  part, %locationPath%)</span></span>|  
|<span data-ttu-id="c28f6-125">メッセージのリファレンス (.NET 型)</span><span class="sxs-lookup"><span data-stu-id="c28f6-125">Message reference (.NET type)</span></span>|<span data-ttu-id="c28f6-126">bpws:getContainerData(%msgName%, part, %locationPath%)</span><span class="sxs-lookup"><span data-stu-id="c28f6-126">bpws:getContainerData(%msgName%, part, %locationPath%)</span></span>|  
|<span data-ttu-id="c28f6-127">メッセージ部分の参照</span><span class="sxs-lookup"><span data-stu-id="c28f6-127">Message-part reference</span></span>|<span data-ttu-id="c28f6-128">bpws:getContainerData(%msgName%, %locationPath%)</span><span class="sxs-lookup"><span data-stu-id="c28f6-128">bpws:getContainerData(%msgName%, %locationPath%)</span></span>|  
|<span data-ttu-id="c28f6-129">識別フィールドの参照</span><span class="sxs-lookup"><span data-stu-id="c28f6-129">Distinguished-field reference</span></span>|<span data-ttu-id="c28f6-130">bpws:getContainerData(%msgName%, %partName%, %locationPath%)</span><span class="sxs-lookup"><span data-stu-id="c28f6-130">bpws:getContainerData(%msgName%, %partName%, %locationPath%)</span></span>|  
|<span data-ttu-id="c28f6-131">メッセージ データ プロパティの参照</span><span class="sxs-lookup"><span data-stu-id="c28f6-131">Message data-property reference</span></span>|<span data-ttu-id="c28f6-132">bpws:getContainerProperty(%msgName%, %propertyQName%)</span><span class="sxs-lookup"><span data-stu-id="c28f6-132">bpws:getContainerProperty(%msgName%, %propertyQName%)</span></span>|  
  
## <a name="operators"></a><span data-ttu-id="c28f6-133">演算子</span><span class="sxs-lookup"><span data-stu-id="c28f6-133">Operators</span></span>  
  
|<span data-ttu-id="c28f6-134">XLANG/秒</span><span class="sxs-lookup"><span data-stu-id="c28f6-134">XLANG/s</span></span>|<span data-ttu-id="c28f6-135">BPEL4WS</span><span class="sxs-lookup"><span data-stu-id="c28f6-135">BPEL4WS</span></span>|  
|--------------|-------------|  
|<span data-ttu-id="c28f6-136">単項 +</span><span class="sxs-lookup"><span data-stu-id="c28f6-136">Unary +</span></span>|<span data-ttu-id="c28f6-137">無視</span><span class="sxs-lookup"><span data-stu-id="c28f6-137">Ignored</span></span>|  
|<span data-ttu-id="c28f6-138">単項演算子-</span><span class="sxs-lookup"><span data-stu-id="c28f6-138">Unary -</span></span>|<span data-ttu-id="c28f6-139">XPath 単項演算子-</span><span class="sxs-lookup"><span data-stu-id="c28f6-139">XPath unary -</span></span>|  
|<span data-ttu-id="c28f6-140">単項!</span><span class="sxs-lookup"><span data-stu-id="c28f6-140">Unary !</span></span>|<span data-ttu-id="c28f6-141">XPath not() 関数</span><span class="sxs-lookup"><span data-stu-id="c28f6-141">XPath not() function</span></span>|  
|<span data-ttu-id="c28f6-142">バイナリ & &、&#124;&#124;</span><span class="sxs-lookup"><span data-stu-id="c28f6-142">Binary &&, &#124;&#124;</span></span>|<span data-ttu-id="c28f6-143">XPath"and"、"or"演算子</span><span class="sxs-lookup"><span data-stu-id="c28f6-143">XPath 'and', 'or' operators</span></span>|  
|<span data-ttu-id="c28f6-144">バイナリ = =、! =、< =、<>、=、></span><span class="sxs-lookup"><span data-stu-id="c28f6-144">Binary ==, !=, <=, <, >=, ></span></span>|<span data-ttu-id="c28f6-145">XPath '='、'!</span><span class="sxs-lookup"><span data-stu-id="c28f6-145">XPath '=', '!</span></span> <span data-ttu-id="c28f6-146">=', '<=', '<', '>=', '>' operators</span><span class="sxs-lookup"><span data-stu-id="c28f6-146">=', '<=', '<', '>=', '>' operators</span></span>|  
|<span data-ttu-id="c28f6-147">バイナリ +、-、\*、両方の整数オペランド %</span><span class="sxs-lookup"><span data-stu-id="c28f6-147">Binary +, -, \*, % with both integral operands</span></span>|<span data-ttu-id="c28f6-148">XPath '+'、'-'、' \*'、"mod"演算子</span><span class="sxs-lookup"><span data-stu-id="c28f6-148">XPath '+', '-', '\*', 'mod' operators</span></span>|  
  
## <a name="xlangs-constructs-that-are-disallowed-in-bpel4ws"></a><span data-ttu-id="c28f6-149">BPEL4WS で使用できない xlang/s 構成要素</span><span class="sxs-lookup"><span data-stu-id="c28f6-149">XLANG/s constructs that are disallowed in BPEL4WS</span></span>  
  
-   <span data-ttu-id="c28f6-150">メッセージ コンテキスト プロパティの参照</span><span class="sxs-lookup"><span data-stu-id="c28f6-150">Message context-property reference</span></span>  
  
-   <span data-ttu-id="c28f6-151">サービス プロパティの参照</span><span class="sxs-lookup"><span data-stu-id="c28f6-151">Service-property reference</span></span>  
  
-   <span data-ttu-id="c28f6-152">ポート プロパティの参照</span><span class="sxs-lookup"><span data-stu-id="c28f6-152">Port-property reference</span></span>  
  
-   <span data-ttu-id="c28f6-153">サービス リンク プロパティの参照</span><span class="sxs-lookup"><span data-stu-id="c28f6-153">Service link-property reference</span></span>  
  
-   <span data-ttu-id="c28f6-154">単項演算子 – 整数型以外の種類</span><span class="sxs-lookup"><span data-stu-id="c28f6-154">Unary – with non-integral type</span></span>  
  
-   <span data-ttu-id="c28f6-155">単項 ~</span><span class="sxs-lookup"><span data-stu-id="c28f6-155">Unary ~</span></span>  
  
-   <span data-ttu-id="c28f6-156">キャスト演算子</span><span class="sxs-lookup"><span data-stu-id="c28f6-156">Cast operator</span></span>  
  
-   <span data-ttu-id="c28f6-157">バイナリ/整数オペランドを</span><span class="sxs-lookup"><span data-stu-id="c28f6-157">Binary / with integral operands</span></span>  
  
-   <span data-ttu-id="c28f6-158">バイナリ +、-、\*、%、/整数以外のオペランドを</span><span class="sxs-lookup"><span data-stu-id="c28f6-158">Binary +, -, \*, %, / with non-integral operands</span></span>  
  
-   <span data-ttu-id="c28f6-159">バイナリ < =、<>、=、> の非文字列オペランド</span><span class="sxs-lookup"><span data-stu-id="c28f6-159">Binary <=, <, >=, > with non-string operands</span></span>  
  
-   <span data-ttu-id="c28f6-160">ビット処理演算子 &、^、&#124;</span><span class="sxs-lookup"><span data-stu-id="c28f6-160">Bitwise operators &, ^, &#124;</span></span>  
  
-   <span data-ttu-id="c28f6-161">シフト演算子 <<>>,</span><span class="sxs-lookup"><span data-stu-id="c28f6-161">Shift operators <<, >></span></span>  
  
-   <span data-ttu-id="c28f6-162">Checked 式</span><span class="sxs-lookup"><span data-stu-id="c28f6-162">Checked expression</span></span>  
  
-   <span data-ttu-id="c28f6-163">Intrinsic 式</span><span class="sxs-lookup"><span data-stu-id="c28f6-163">Intrinsic expression</span></span>  
  
-   <span data-ttu-id="c28f6-164">前と後のインクリメントおよびデクリメント + +、-</span><span class="sxs-lookup"><span data-stu-id="c28f6-164">Pre- and post- increment and decrement ++, --</span></span>  
  
-   <span data-ttu-id="c28f6-165">オブジェクト呼び出し (で、せず out や ref パラメーター)</span><span class="sxs-lookup"><span data-stu-id="c28f6-165">Object invocation (with our without out and/or ref params)</span></span>  
  
-   <span data-ttu-id="c28f6-166">'new' 演算子</span><span class="sxs-lookup"><span data-stu-id="c28f6-166">'new' operator</span></span>