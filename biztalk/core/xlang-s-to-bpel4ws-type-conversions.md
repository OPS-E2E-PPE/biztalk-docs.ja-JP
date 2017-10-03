---
title: "XLANG の BPEL4WS への変換の入力 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- XLANG/s
- XLANG/s, warning
- XLANG/s, BPEL4WS
- XLANG/s, converting
ms.assetid: a35d4dba-9344-43c8-86e6-a373a4452579
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2a9451d1f156bf98b3e8fd7da177937cd4492b0b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="xlang-s-to-bpel4ws-type-conversions"></a><span data-ttu-id="df311-102">XLANG-s BPEL4WS 型への変換から</span><span class="sxs-lookup"><span data-stu-id="df311-102">XLANG-s to BPEL4WS Type Conversions</span></span>
<span data-ttu-id="df311-103">次の表は、さまざまな XLANG/s 構成要素と BPEL4WS 構成要素間の変換の詳細を示しています。</span><span class="sxs-lookup"><span data-stu-id="df311-103">The following tables detail the conversions between various XLANG/s constructs and BPEL4WS constructs.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="df311-104">XPath 1.1 は、指数形式または double 形式の数値をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="df311-104">XPath 1.1 does not support numbers in exponential or double formats.</span></span> <span data-ttu-id="df311-105">XLANG/s オーケストレーションにおけるこれらの形式のリテラル値は、%f 形式を使用して BPEL4WS にエクスポートされますが、精度が低下する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="df311-105">Literal values in these formats in XLANG/s orchestrations are exported to BPEL4WS using the %f format, and a loss of precision might result.</span></span>  
  
## <a name="literals-if-the-literal-is-part-of-an-expression"></a><span data-ttu-id="df311-106">リテラル (リテラルが式の一部である場合)</span><span class="sxs-lookup"><span data-stu-id="df311-106">Literals (if the literal is part of an expression)</span></span>  
  
|<span data-ttu-id="df311-107">XLANG/s</span><span class="sxs-lookup"><span data-stu-id="df311-107">XLANG/s</span></span>|<span data-ttu-id="df311-108">BPEL4WS</span><span class="sxs-lookup"><span data-stu-id="df311-108">BPEL4WS</span></span>|  
|--------------|-------------|  
|<span data-ttu-id="df311-109">文字列、文字</span><span class="sxs-lookup"><span data-stu-id="df311-109">String, character</span></span>|<span data-ttu-id="df311-110">XPath 文字列</span><span class="sxs-lookup"><span data-stu-id="df311-110">XPath string</span></span>|  
|<span data-ttu-id="df311-111">整数、実数</span><span class="sxs-lookup"><span data-stu-id="df311-111">Integer, real</span></span>|<span data-ttu-id="df311-112">XPath 数値</span><span class="sxs-lookup"><span data-stu-id="df311-112">XPath number</span></span>|  
|<span data-ttu-id="df311-113">ブール値 "true"、"false"</span><span class="sxs-lookup"><span data-stu-id="df311-113">Boolean "true", "false"</span></span>|<span data-ttu-id="df311-114">XPath true() 関数、false() 関数</span><span class="sxs-lookup"><span data-stu-id="df311-114">XPath true(), false() functions</span></span>|  
  
## <a name="literals-standalone-assignment"></a><span data-ttu-id="df311-115">リテラル (スタンドアロン代入)</span><span class="sxs-lookup"><span data-stu-id="df311-115">Literals (standalone assignment)</span></span>  
  
|<span data-ttu-id="df311-116">XLANG/s</span><span class="sxs-lookup"><span data-stu-id="df311-116">XLANG/s</span></span>|<span data-ttu-id="df311-117">BPEL4WS</span><span class="sxs-lookup"><span data-stu-id="df311-117">BPEL4WS</span></span>|  
|--------------|-------------|  
|<span data-ttu-id="df311-118">リテラル定数</span><span class="sxs-lookup"><span data-stu-id="df311-118">Literal constant</span></span>|<span data-ttu-id="df311-119">XSD に相当</span><span class="sxs-lookup"><span data-stu-id="df311-119">XSD equivalent</span></span>|  
  
## <a name="variables"></a><span data-ttu-id="df311-120">変数</span><span class="sxs-lookup"><span data-stu-id="df311-120">Variables</span></span>  
  
|<span data-ttu-id="df311-121">XLANG/s</span><span class="sxs-lookup"><span data-stu-id="df311-121">XLANG/s</span></span>|<span data-ttu-id="df311-122">BPEL4WS</span><span class="sxs-lookup"><span data-stu-id="df311-122">BPEL4WS</span></span>|  
|--------------|-------------|  
|<span data-ttu-id="df311-123">変数の参照</span><span class="sxs-lookup"><span data-stu-id="df311-123">Variable reference</span></span>|<span data-ttu-id="df311-124">bpws:getContainerData(%varName%,  part, %locationPath%)</span><span class="sxs-lookup"><span data-stu-id="df311-124">bpws:getContainerData(%varName%,  part, %locationPath%)</span></span>|  
|<span data-ttu-id="df311-125">メッセージの参照 (.NET 型)</span><span class="sxs-lookup"><span data-stu-id="df311-125">Message reference (.NET type)</span></span>|<span data-ttu-id="df311-126">bpws:getContainerData(%msgName%, part, %locationPath%)</span><span class="sxs-lookup"><span data-stu-id="df311-126">bpws:getContainerData(%msgName%, part, %locationPath%)</span></span>|  
|<span data-ttu-id="df311-127">メッセージ部分の参照</span><span class="sxs-lookup"><span data-stu-id="df311-127">Message-part reference</span></span>|<span data-ttu-id="df311-128">bpws:getContainerData(%msgName%, %locationPath%)</span><span class="sxs-lookup"><span data-stu-id="df311-128">bpws:getContainerData(%msgName%, %locationPath%)</span></span>|  
|<span data-ttu-id="df311-129">識別フィールドの参照</span><span class="sxs-lookup"><span data-stu-id="df311-129">Distinguished-field reference</span></span>|<span data-ttu-id="df311-130">bpws:getContainerData(%msgName%, %partName%, %locationPath%)</span><span class="sxs-lookup"><span data-stu-id="df311-130">bpws:getContainerData(%msgName%, %partName%, %locationPath%)</span></span>|  
|<span data-ttu-id="df311-131">メッセージ データ プロパティの参照</span><span class="sxs-lookup"><span data-stu-id="df311-131">Message data-property reference</span></span>|<span data-ttu-id="df311-132">bpws:getContainerProperty(%msgName%, %propertyQName%)</span><span class="sxs-lookup"><span data-stu-id="df311-132">bpws:getContainerProperty(%msgName%, %propertyQName%)</span></span>|  
  
## <a name="operators"></a><span data-ttu-id="df311-133">演算子</span><span class="sxs-lookup"><span data-stu-id="df311-133">Operators</span></span>  
  
|<span data-ttu-id="df311-134">XLANG/s</span><span class="sxs-lookup"><span data-stu-id="df311-134">XLANG/s</span></span>|<span data-ttu-id="df311-135">BPEL4WS</span><span class="sxs-lookup"><span data-stu-id="df311-135">BPEL4WS</span></span>|  
|--------------|-------------|  
|<span data-ttu-id="df311-136">単項演算子 +</span><span class="sxs-lookup"><span data-stu-id="df311-136">Unary +</span></span>|<span data-ttu-id="df311-137">無視</span><span class="sxs-lookup"><span data-stu-id="df311-137">Ignored</span></span>|  
|<span data-ttu-id="df311-138">単項 -</span><span class="sxs-lookup"><span data-stu-id="df311-138">Unary -</span></span>|<span data-ttu-id="df311-139">XPath 単項演算子 -</span><span class="sxs-lookup"><span data-stu-id="df311-139">XPath unary -</span></span>|  
|<span data-ttu-id="df311-140">単項演算子 !</span><span class="sxs-lookup"><span data-stu-id="df311-140">Unary !</span></span>|<span data-ttu-id="df311-141">XPath not() 関数</span><span class="sxs-lookup"><span data-stu-id="df311-141">XPath not() function</span></span>|  
|<span data-ttu-id="df311-142">バイナリ & &、&#124; & #124 です。</span><span class="sxs-lookup"><span data-stu-id="df311-142">Binary &&, &#124;&#124;</span></span>|<span data-ttu-id="df311-143">XPath "and" 演算子、"or" 演算子</span><span class="sxs-lookup"><span data-stu-id="df311-143">XPath 'and', 'or' operators</span></span>|  
|<span data-ttu-id="df311-144">バイナリ = =、! =、< =、 \<、> =、></span><span class="sxs-lookup"><span data-stu-id="df311-144">Binary ==, !=, <=, \<, >=, ></span></span>|<span data-ttu-id="df311-145">XPath "="、"!</span><span class="sxs-lookup"><span data-stu-id="df311-145">XPath '=', '!</span></span> <span data-ttu-id="df311-146">='、' < = '、'\<'、' > ='、' >' の演算子</span><span class="sxs-lookup"><span data-stu-id="df311-146">=', '<=', '\<', '>=', '>' operators</span></span>|  
|<span data-ttu-id="df311-147">両方の整数オペランドのバイナリ +、-、*、%</span><span class="sxs-lookup"><span data-stu-id="df311-147">Binary +, -, *, % with both integral operands</span></span>|<span data-ttu-id="df311-148">XPath "+"、"-"、"*"、"mod" 演算子</span><span class="sxs-lookup"><span data-stu-id="df311-148">XPath '+', '-', '*', 'mod' operators</span></span>|  
  
## <a name="xlangs-constructs-that-are-disallowed-in-bpel4ws"></a><span data-ttu-id="df311-149">BPEL4WS で使用できない XLANG/s 構成要素</span><span class="sxs-lookup"><span data-stu-id="df311-149">XLANG/s constructs that are disallowed in BPEL4WS</span></span>  
  
-   <span data-ttu-id="df311-150">メッセージ コンテキスト プロパティの参照</span><span class="sxs-lookup"><span data-stu-id="df311-150">Message context-property reference</span></span>  
  
-   <span data-ttu-id="df311-151">サービス プロパティの参照</span><span class="sxs-lookup"><span data-stu-id="df311-151">Service-property reference</span></span>  
  
-   <span data-ttu-id="df311-152">部分プロパティの参照</span><span class="sxs-lookup"><span data-stu-id="df311-152">Port-property reference</span></span>  
  
-   <span data-ttu-id="df311-153">サービス リンク プロパティの参照</span><span class="sxs-lookup"><span data-stu-id="df311-153">Service link-property reference</span></span>  
  
-   <span data-ttu-id="df311-154">整数以外の型の単項演算子 –</span><span class="sxs-lookup"><span data-stu-id="df311-154">Unary – with non-integral type</span></span>  
  
-   <span data-ttu-id="df311-155">単項演算子 ~</span><span class="sxs-lookup"><span data-stu-id="df311-155">Unary ~</span></span>  
  
-   <span data-ttu-id="df311-156">キャスト演算子</span><span class="sxs-lookup"><span data-stu-id="df311-156">Cast operator</span></span>  
  
-   <span data-ttu-id="df311-157">整数オペランドのバイナリ / </span><span class="sxs-lookup"><span data-stu-id="df311-157">Binary / with integral operands</span></span>  
  
-   <span data-ttu-id="df311-158">整数以外のオペランドのバイナリ +、-、*、%</span><span class="sxs-lookup"><span data-stu-id="df311-158">Binary +, -, *, %, / with non-integral operands</span></span>  
  
-   <span data-ttu-id="df311-159">バイナリ < =、 \<、> =、> 文字列以外のオペランドを持つ</span><span class="sxs-lookup"><span data-stu-id="df311-159">Binary <=, \<, >=, > with non-string operands</span></span>  
  
-   <span data-ttu-id="df311-160">ビット処理演算子 &、^、& #124 です。</span><span class="sxs-lookup"><span data-stu-id="df311-160">Bitwise operators &, ^, &#124;</span></span>  
  
-   <span data-ttu-id="df311-161">シフト演算子 <\<、>></span><span class="sxs-lookup"><span data-stu-id="df311-161">Shift operators <\<, >></span></span>  
  
-   <span data-ttu-id="df311-162">checked 式</span><span class="sxs-lookup"><span data-stu-id="df311-162">Checked expression</span></span>  
  
-   <span data-ttu-id="df311-163">intrinsic 式</span><span class="sxs-lookup"><span data-stu-id="df311-163">Intrinsic expression</span></span>  
  
-   <span data-ttu-id="df311-164">前置および後置インクリメントおよびデクリメント ++、--</span><span class="sxs-lookup"><span data-stu-id="df311-164">Pre- and post- increment and decrement ++, --</span></span>  
  
-   <span data-ttu-id="df311-165">オブジェクト呼び出し (out や ref のパラメーターの有無にかかわらず)</span><span class="sxs-lookup"><span data-stu-id="df311-165">Object invocation (with our without out and/or ref params)</span></span>  
  
-   <span data-ttu-id="df311-166">"new" 演算子</span><span class="sxs-lookup"><span data-stu-id="df311-166">'new' operator</span></span>