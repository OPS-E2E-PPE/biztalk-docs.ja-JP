---
title: 基本的な Types1 |Microsoft ドキュメント
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
ms.openlocfilehash: e90cda6259567adf5236d0c28e576900d8b25271
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22231858"
---
# <a name="basic-types"></a><span data-ttu-id="49d3b-102">基本型</span><span class="sxs-lookup"><span data-stu-id="49d3b-102">Basic Types</span></span>
<span data-ttu-id="49d3b-103">Microsoft BizTalk Adapter for JD Edwards OneWorld は、JD Edwards OneWorld ビジネス関数へのアクセスのみ提供します。</span><span class="sxs-lookup"><span data-stu-id="49d3b-103">Microsoft BizTalk Adapter for JD Edwards OneWorld provides access only to JD Edwards OneWorld business functions.</span></span> <span data-ttu-id="49d3b-104">ビジネス関数メタデータは、ビジネス関数インターフェイスをとおして読み取られ、ビジネス関数の一覧および関連するデータ構造の検索に使用されます。</span><span class="sxs-lookup"><span data-stu-id="49d3b-104">Business function metadata is read using a business function interface and used to find a list of business functions and associated data structures.</span></span> <span data-ttu-id="49d3b-105">メタデータは、すべてのビジネス関数メソッドのすべてのケースで厳密に型指定されます。</span><span class="sxs-lookup"><span data-stu-id="49d3b-105">Metadata is strongly typed in all cases for all business function methods.</span></span>  
  
 <span data-ttu-id="49d3b-106">すべてのビジネス関数メソッドがある同じ呼び出し規約: 派生は、システムは、3 つのパラメーターとデータ構造体へのポインター。</span><span class="sxs-lookup"><span data-stu-id="49d3b-106">All business function methods have the same calling convention: three parameters that are system derived, and a pointer to a data structure.</span></span> <span data-ttu-id="49d3b-107">次の表に、ビジネス関数のデータ型がどのように表現されるかを示します。</span><span class="sxs-lookup"><span data-stu-id="49d3b-107">The following table shows how the business function data types are represented.</span></span>  
  
 <span data-ttu-id="49d3b-108">**ビジネス関数のデータ型**</span><span class="sxs-lookup"><span data-stu-id="49d3b-108">**Business function data types**</span></span>  
  
|<span data-ttu-id="49d3b-109">JD Edwards OneWorld のデータ型</span><span class="sxs-lookup"><span data-stu-id="49d3b-109">JD Edwards OneWorld Data Type</span></span>|<span data-ttu-id="49d3b-110">Description</span><span class="sxs-lookup"><span data-stu-id="49d3b-110">Description</span></span>|<span data-ttu-id="49d3b-111">WDSL 変換</span><span class="sxs-lookup"><span data-stu-id="49d3b-111">WDSL Conversion</span></span>|  
|-----------------------------------|-----------------|---------------------|  
|<span data-ttu-id="49d3b-112">char</span><span class="sxs-lookup"><span data-stu-id="49d3b-112">char</span></span>|<span data-ttu-id="49d3b-113">文字の文字列。</span><span class="sxs-lookup"><span data-stu-id="49d3b-113">Character string.</span></span>|<span data-ttu-id="49d3b-114">xsd:string の 1</span><span class="sxs-lookup"><span data-stu-id="49d3b-114">xsd:string of 1</span></span>|  
|<span data-ttu-id="49d3b-115">int</span><span class="sxs-lookup"><span data-stu-id="49d3b-115">int</span></span>|<span data-ttu-id="49d3b-116">短整数。</span><span class="sxs-lookup"><span data-stu-id="49d3b-116">Short integer.</span></span>|<span data-ttu-id="49d3b-117">xsd:short</span><span class="sxs-lookup"><span data-stu-id="49d3b-117">xsd:short</span></span>|  
|<span data-ttu-id="49d3b-118">long</span><span class="sxs-lookup"><span data-stu-id="49d3b-118">long</span></span>|<span data-ttu-id="49d3b-119">長整数。</span><span class="sxs-lookup"><span data-stu-id="49d3b-119">Long integer.</span></span>|<span data-ttu-id="49d3b-120">xsd:short</span><span class="sxs-lookup"><span data-stu-id="49d3b-120">xsd:short</span></span>|  
|<span data-ttu-id="49d3b-121">文字列</span><span class="sxs-lookup"><span data-stu-id="49d3b-121">String</span></span>|<span data-ttu-id="49d3b-122">参照してください[文字列値の処理](../core/handling-string-values1.md)です。</span><span class="sxs-lookup"><span data-stu-id="49d3b-122">See [Handling String Values](../core/handling-string-values1.md).</span></span>|<span data-ttu-id="49d3b-123">xsd:string</span><span class="sxs-lookup"><span data-stu-id="49d3b-123">xsd:string</span></span>|  
|<span data-ttu-id="49d3b-124">JDEDATE</span><span class="sxs-lookup"><span data-stu-id="49d3b-124">JDEDATE</span></span>|<span data-ttu-id="49d3b-125">日付の特殊な実装。</span><span class="sxs-lookup"><span data-stu-id="49d3b-125">Special implementation of dates.</span></span>|<span data-ttu-id="49d3b-126">xsd:date</span><span class="sxs-lookup"><span data-stu-id="49d3b-126">xsd:date</span></span>|  
|<span data-ttu-id="49d3b-127">MATH_NUMERIC</span><span class="sxs-lookup"><span data-stu-id="49d3b-127">MATH_NUMERIC</span></span>|<span data-ttu-id="49d3b-128">浮動小数点数の特殊な実装 (通貨の値を含む)。</span><span class="sxs-lookup"><span data-stu-id="49d3b-128">Special implementation of floating point numbers, including currency values.</span></span>|<span data-ttu-id="49d3b-129">32 の xsd:string</span><span class="sxs-lookup"><span data-stu-id="49d3b-129">xsd:string of 32</span></span>|  
|<span data-ttu-id="49d3b-130">Byte</span><span class="sxs-lookup"><span data-stu-id="49d3b-130">Byte</span></span>|<span data-ttu-id="49d3b-131">単一の符号なし文字。</span><span class="sxs-lookup"><span data-stu-id="49d3b-131">Single unsigned character.</span></span>|<span data-ttu-id="49d3b-132">xsd:string の 1</span><span class="sxs-lookup"><span data-stu-id="49d3b-132">xsd:string of 1</span></span>|  
  
 <span data-ttu-id="49d3b-133">次の表に、JD Edwards OneWorld の基本データ型の一覧と、これらのデータ型が Microsoft .NET Framework にどのようにマップされるかを示します。</span><span class="sxs-lookup"><span data-stu-id="49d3b-133">The following table contains the list of basic types in JD Edwards OneWorld and how they map to the Microsoft .NET Framework.</span></span>  
  
 <span data-ttu-id="49d3b-134">**基本データ型と、Microsoft .NET Framework のマップ**</span><span class="sxs-lookup"><span data-stu-id="49d3b-134">**Basic types and how they map to the Microsoft .NET Framework**</span></span>  
  
|<span data-ttu-id="49d3b-135">JD Edwards OneWorld XE</span><span class="sxs-lookup"><span data-stu-id="49d3b-135">JD Edwards OneWorld XE</span></span>|<span data-ttu-id="49d3b-136">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="49d3b-136">.NET Framework</span></span>|  
|----------------------------|--------------------|  
|<span data-ttu-id="49d3b-137">char</span><span class="sxs-lookup"><span data-stu-id="49d3b-137">char</span></span>|<span data-ttu-id="49d3b-138">文字列</span><span class="sxs-lookup"><span data-stu-id="49d3b-138">String</span></span>|  
|<span data-ttu-id="49d3b-139">int</span><span class="sxs-lookup"><span data-stu-id="49d3b-139">int</span></span>|<span data-ttu-id="49d3b-140">Short</span><span class="sxs-lookup"><span data-stu-id="49d3b-140">Short</span></span>|  
|<span data-ttu-id="49d3b-141">long</span><span class="sxs-lookup"><span data-stu-id="49d3b-141">long</span></span>|<span data-ttu-id="49d3b-142">Short</span><span class="sxs-lookup"><span data-stu-id="49d3b-142">Short</span></span>|  
|<span data-ttu-id="49d3b-143">文字列</span><span class="sxs-lookup"><span data-stu-id="49d3b-143">String</span></span>|<span data-ttu-id="49d3b-144">文字列</span><span class="sxs-lookup"><span data-stu-id="49d3b-144">String</span></span>|  
|<span data-ttu-id="49d3b-145">JDEDATE</span><span class="sxs-lookup"><span data-stu-id="49d3b-145">JDEDATE</span></span>|<span data-ttu-id="49d3b-146">System.DateTime</span><span class="sxs-lookup"><span data-stu-id="49d3b-146">System.DateTime</span></span>|  
|<span data-ttu-id="49d3b-147">MATH_NUMERIC</span><span class="sxs-lookup"><span data-stu-id="49d3b-147">MATH_NUMERIC</span></span>|<span data-ttu-id="49d3b-148">文字列</span><span class="sxs-lookup"><span data-stu-id="49d3b-148">String</span></span>|  
|<span data-ttu-id="49d3b-149">Byte</span><span class="sxs-lookup"><span data-stu-id="49d3b-149">Byte</span></span>|<span data-ttu-id="49d3b-150">文字列</span><span class="sxs-lookup"><span data-stu-id="49d3b-150">String</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="49d3b-151">引数が 1 つだけで、引数の戻り値の型が void である場合、ホルダーはクラスに置き換えられ、出力部分は戻り値になります。</span><span class="sxs-lookup"><span data-stu-id="49d3b-151">If there is only one argument, and the return argument is void, the holder is replaced by the class, and the out portion becomes the return value.</span></span> <span data-ttu-id="49d3b-152">例:</span><span class="sxs-lookup"><span data-stu-id="49d3b-152">For example:</span></span>  
  
```  
org.apache.axis.holders.DateHolder becomes a java.util.Date.   
```  
  
 <span data-ttu-id="49d3b-153">次はメソッド シグネチャの例です。</span><span class="sxs-lookup"><span data-stu-id="49d3b-153">The following is an example of method signatures:</span></span>  
  
```  
void testDate1(org.apache.axis.holders.DateHolder date1  
        org.apache.axis.holders.DateHolder date2);  
  
java.util.Date testDate2(java.util.Date date);  
```  
  
## <a name="character-limited-strings"></a><span data-ttu-id="49d3b-154">文字数制限のある文字列</span><span class="sxs-lookup"><span data-stu-id="49d3b-154">Character-Limited Strings</span></span>  
 <span data-ttu-id="49d3b-155">JD Edwards OneWorld では、一部の文字列に文字数制限があります。</span><span class="sxs-lookup"><span data-stu-id="49d3b-155">In JD Edwards OneWorld, some strings are character-limited.</span></span> <span data-ttu-id="49d3b-156">文字数制限を超えると、エラーになります。</span><span class="sxs-lookup"><span data-stu-id="49d3b-156">Any extra character causes an error.</span></span> <span data-ttu-id="49d3b-157">文字列の文字数の制限を確認するには、Microsoft アダプター ウィザードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="49d3b-157">To see the limit of characters in the strings, you can use the Microsoft Adapter Wizard.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49d3b-158">参照</span><span class="sxs-lookup"><span data-stu-id="49d3b-158">See Also</span></span>  
 <span data-ttu-id="49d3b-159">[MATH_NUMERIC 型の使用](../core/using-the-math-numeric-type2.md) </span><span class="sxs-lookup"><span data-stu-id="49d3b-159">[Using the MATH_NUMERIC Type](../core/using-the-math-numeric-type2.md) </span></span>  
 <span data-ttu-id="49d3b-160">[文字列値の処理](../core/handling-string-values1.md) </span><span class="sxs-lookup"><span data-stu-id="49d3b-160">[Handling String Values](../core/handling-string-values1.md) </span></span>  
 [<span data-ttu-id="49d3b-161">付録 a: データ型</span><span class="sxs-lookup"><span data-stu-id="49d3b-161">Appendix A: Data Types</span></span>](../core/appendix-a-data-types.md)