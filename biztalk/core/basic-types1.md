---
title: 基本的な Types1 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- JD Edwards OneWorld adapters, data types
- JD Edwards OneWorld adapters, business functions
- .NET Framework, mapping [JD Edwards OneWorld adapters]
- adapters [JD Edwards OneWorld adapters], data types
- adapters [JD Edwards OneWorld adapters], .NET Framework
- JD Edwards OneWorld adapters, .NET Framework
- adapters [JD Edwards OneWorld adapters], business functions
ms.assetid: d306ea1b-fb74-4fa3-9681-405252928df1
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1c1cfd31eacd56c19e5b1daf2288be098d9448c3
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65529141"
---
# <a name="basic-types"></a><span data-ttu-id="c63e7-102">基本的な型</span><span class="sxs-lookup"><span data-stu-id="c63e7-102">Basic Types</span></span>
<span data-ttu-id="c63e7-103">Microsoft の BizTalk Adapter for JD Edwards OneWorld では、JD Edwards OneWorld ビジネス関数にのみアクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="c63e7-103">Microsoft BizTalk Adapter for JD Edwards OneWorld provides access only to JD Edwards OneWorld business functions.</span></span> <span data-ttu-id="c63e7-104">ビジネス関数メタデータは読み取り専用ビジネス関数のインターフェイスを使用してビジネス関数の一覧を検索するために使用し、関連するデータ構造。</span><span class="sxs-lookup"><span data-stu-id="c63e7-104">Business function metadata is read using a business function interface and used to find a list of business functions and associated data structures.</span></span> <span data-ttu-id="c63e7-105">メタデータはすべてのビジネス関数メソッドのすべてのケースで厳密に型指定します。</span><span class="sxs-lookup"><span data-stu-id="c63e7-105">Metadata is strongly typed in all cases for all business function methods.</span></span>  
  
 <span data-ttu-id="c63e7-106">すべてのビジネス関数メソッドと同じ呼び出し規約がある: システムから派生している 3 つのパラメーターとデータ構造体へのポインター。</span><span class="sxs-lookup"><span data-stu-id="c63e7-106">All business function methods have the same calling convention: three parameters that are system derived, and a pointer to a data structure.</span></span> <span data-ttu-id="c63e7-107">次の表では、ビジネス関数のデータ型の表現方法を示します。</span><span class="sxs-lookup"><span data-stu-id="c63e7-107">The following table shows how the business function data types are represented.</span></span>  
  
 <span data-ttu-id="c63e7-108">**ビジネス関数のデータ型**</span><span class="sxs-lookup"><span data-stu-id="c63e7-108">**Business function data types**</span></span>  
  
|<span data-ttu-id="c63e7-109">JD Edwards OneWorld のデータ型</span><span class="sxs-lookup"><span data-stu-id="c63e7-109">JD Edwards OneWorld Data Type</span></span>|<span data-ttu-id="c63e7-110">説明</span><span class="sxs-lookup"><span data-stu-id="c63e7-110">Description</span></span>|<span data-ttu-id="c63e7-111">WDSL 変換</span><span class="sxs-lookup"><span data-stu-id="c63e7-111">WDSL Conversion</span></span>|  
|-----------------------------------|-----------------|---------------------|  
|<span data-ttu-id="c63e7-112">char</span><span class="sxs-lookup"><span data-stu-id="c63e7-112">char</span></span>|<span data-ttu-id="c63e7-113">文字の文字列。</span><span class="sxs-lookup"><span data-stu-id="c63e7-113">Character string.</span></span>|<span data-ttu-id="c63e7-114">xsd:string の 1</span><span class="sxs-lookup"><span data-stu-id="c63e7-114">xsd:string of 1</span></span>|  
|<span data-ttu-id="c63e7-115">ssNoversion</span><span class="sxs-lookup"><span data-stu-id="c63e7-115">int</span></span>|<span data-ttu-id="c63e7-116">短整数。</span><span class="sxs-lookup"><span data-stu-id="c63e7-116">Short integer.</span></span>|<span data-ttu-id="c63e7-117">xsd:short</span><span class="sxs-lookup"><span data-stu-id="c63e7-117">xsd:short</span></span>|  
|<span data-ttu-id="c63e7-118">long</span><span class="sxs-lookup"><span data-stu-id="c63e7-118">long</span></span>|<span data-ttu-id="c63e7-119">長整数。</span><span class="sxs-lookup"><span data-stu-id="c63e7-119">Long integer.</span></span>|<span data-ttu-id="c63e7-120">xsd:short</span><span class="sxs-lookup"><span data-stu-id="c63e7-120">xsd:short</span></span>|  
|<span data-ttu-id="c63e7-121">String</span><span class="sxs-lookup"><span data-stu-id="c63e7-121">String</span></span>|<span data-ttu-id="c63e7-122">参照してください[文字列値を処理する](../core/handling-string-values1.md)します。</span><span class="sxs-lookup"><span data-stu-id="c63e7-122">See [Handling String Values](../core/handling-string-values1.md).</span></span>|<span data-ttu-id="c63e7-123">xsd:string</span><span class="sxs-lookup"><span data-stu-id="c63e7-123">xsd:string</span></span>|  
|<span data-ttu-id="c63e7-124">JDEDATE</span><span class="sxs-lookup"><span data-stu-id="c63e7-124">JDEDATE</span></span>|<span data-ttu-id="c63e7-125">日付の特殊な実装。</span><span class="sxs-lookup"><span data-stu-id="c63e7-125">Special implementation of dates.</span></span>|<span data-ttu-id="c63e7-126">xsd:date</span><span class="sxs-lookup"><span data-stu-id="c63e7-126">xsd:date</span></span>|  
|<span data-ttu-id="c63e7-127">MATH_NUMERIC</span><span class="sxs-lookup"><span data-stu-id="c63e7-127">MATH_NUMERIC</span></span>|<span data-ttu-id="c63e7-128">浮動小数点数、通貨値などの特殊な実装。</span><span class="sxs-lookup"><span data-stu-id="c63e7-128">Special implementation of floating point numbers, including currency values.</span></span>|<span data-ttu-id="c63e7-129">32 の xsd:string</span><span class="sxs-lookup"><span data-stu-id="c63e7-129">xsd:string of 32</span></span>|  
|<span data-ttu-id="c63e7-130">バイト</span><span class="sxs-lookup"><span data-stu-id="c63e7-130">Byte</span></span>|<span data-ttu-id="c63e7-131">1 つの符号なし文字。</span><span class="sxs-lookup"><span data-stu-id="c63e7-131">Single unsigned character.</span></span>|<span data-ttu-id="c63e7-132">xsd:string の 1</span><span class="sxs-lookup"><span data-stu-id="c63e7-132">xsd:string of 1</span></span>|  
  
 <span data-ttu-id="c63e7-133">次の表には、JD Edwards OneWorld と Microsoft .NET Framework への割り当て方法の基本型の一覧が含まれています。</span><span class="sxs-lookup"><span data-stu-id="c63e7-133">The following table contains the list of basic types in JD Edwards OneWorld and how they map to the Microsoft .NET Framework.</span></span>  
  
 <span data-ttu-id="c63e7-134">**基本的な型および Microsoft .NET Framework への割り当て方法**</span><span class="sxs-lookup"><span data-stu-id="c63e7-134">**Basic types and how they map to the Microsoft .NET Framework**</span></span>  
  
|<span data-ttu-id="c63e7-135">JD Edwards OneWorld XE</span><span class="sxs-lookup"><span data-stu-id="c63e7-135">JD Edwards OneWorld XE</span></span>|<span data-ttu-id="c63e7-136">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="c63e7-136">.NET Framework</span></span>|  
|----------------------------|--------------------|  
|<span data-ttu-id="c63e7-137">char</span><span class="sxs-lookup"><span data-stu-id="c63e7-137">char</span></span>|<span data-ttu-id="c63e7-138">String</span><span class="sxs-lookup"><span data-stu-id="c63e7-138">String</span></span>|  
|<span data-ttu-id="c63e7-139">ssNoversion</span><span class="sxs-lookup"><span data-stu-id="c63e7-139">int</span></span>|<span data-ttu-id="c63e7-140">Short</span><span class="sxs-lookup"><span data-stu-id="c63e7-140">Short</span></span>|  
|<span data-ttu-id="c63e7-141">long</span><span class="sxs-lookup"><span data-stu-id="c63e7-141">long</span></span>|<span data-ttu-id="c63e7-142">Short</span><span class="sxs-lookup"><span data-stu-id="c63e7-142">Short</span></span>|  
|<span data-ttu-id="c63e7-143">String</span><span class="sxs-lookup"><span data-stu-id="c63e7-143">String</span></span>|<span data-ttu-id="c63e7-144">String</span><span class="sxs-lookup"><span data-stu-id="c63e7-144">String</span></span>|  
|<span data-ttu-id="c63e7-145">JDEDATE</span><span class="sxs-lookup"><span data-stu-id="c63e7-145">JDEDATE</span></span>|<span data-ttu-id="c63e7-146">System.DateTime</span><span class="sxs-lookup"><span data-stu-id="c63e7-146">System.DateTime</span></span>|  
|<span data-ttu-id="c63e7-147">MATH_NUMERIC</span><span class="sxs-lookup"><span data-stu-id="c63e7-147">MATH_NUMERIC</span></span>|<span data-ttu-id="c63e7-148">String</span><span class="sxs-lookup"><span data-stu-id="c63e7-148">String</span></span>|  
|<span data-ttu-id="c63e7-149">バイト</span><span class="sxs-lookup"><span data-stu-id="c63e7-149">Byte</span></span>|<span data-ttu-id="c63e7-150">String</span><span class="sxs-lookup"><span data-stu-id="c63e7-150">String</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="c63e7-151">1 つの引数があるし、void 戻り値の引数では、クラスによって所有者が置き換えられ、出力の部分が戻り値になります。</span><span class="sxs-lookup"><span data-stu-id="c63e7-151">If there is only one argument, and the return argument is void, the holder is replaced by the class, and the out portion becomes the return value.</span></span> <span data-ttu-id="c63e7-152">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="c63e7-152">For example:</span></span>  
  
```  
org.apache.axis.holders.DateHolder becomes a java.util.Date.   
```  
  
 <span data-ttu-id="c63e7-153">メソッドのシグネチャの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="c63e7-153">The following is an example of method signatures:</span></span>  
  
```  
void testDate1(org.apache.axis.holders.DateHolder date1  
        org.apache.axis.holders.DateHolder date2);  
  
java.util.Date testDate2(java.util.Date date);  
```  
  
## <a name="character-limited-strings"></a><span data-ttu-id="c63e7-154">文字列の文字制限</span><span class="sxs-lookup"><span data-stu-id="c63e7-154">Character-Limited Strings</span></span>  
 <span data-ttu-id="c63e7-155">JD Edwards OneWorld では、一部の文字列は文字は限定されています。</span><span class="sxs-lookup"><span data-stu-id="c63e7-155">In JD Edwards OneWorld, some strings are character-limited.</span></span> <span data-ttu-id="c63e7-156">任意の余分な文字には、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="c63e7-156">Any extra character causes an error.</span></span> <span data-ttu-id="c63e7-157">文字列の文字の制限を表示するには、Microsoft アダプター ウィザードを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="c63e7-157">To see the limit of characters in the strings, you can use the Microsoft Adapter Wizard.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c63e7-158">参照</span><span class="sxs-lookup"><span data-stu-id="c63e7-158">See Also</span></span>  
 <span data-ttu-id="c63e7-159">[MATH_NUMERIC 型の使用](../core/using-the-math-numeric-type2.md) </span><span class="sxs-lookup"><span data-stu-id="c63e7-159">[Using the MATH_NUMERIC Type](../core/using-the-math-numeric-type2.md) </span></span>  
 <span data-ttu-id="c63e7-160">[文字列値の処理](../core/handling-string-values1.md) </span><span class="sxs-lookup"><span data-stu-id="c63e7-160">[Handling String Values](../core/handling-string-values1.md) </span></span>  
 [<span data-ttu-id="c63e7-161">付録 a:データ型</span><span class="sxs-lookup"><span data-stu-id="c63e7-161">Appendix A: Data Types</span></span>](../core/appendix-a-data-types.md)