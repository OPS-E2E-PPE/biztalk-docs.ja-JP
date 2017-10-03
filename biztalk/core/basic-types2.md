---
title: "基本的な Types2 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- JD Edwards EnterpriseOne adapters, data types
- adapters [JD Edwards EnterpriseOne adapters], data types
- data types, JD Edwards EnterpriseOne adapters
ms.assetid: 96a70f0d-f7f8-4e3b-9511-59b330910ead
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a7e5c47d8760e9743ec11a62598581d9d20b3e53
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="basic-types"></a><span data-ttu-id="2814e-102">基本型</span><span class="sxs-lookup"><span data-stu-id="2814e-102">Basic Types</span></span>
<span data-ttu-id="2814e-103">Microsoft BizTalk Adapter for JD Edwards EnterpriseOne では、JD Edwards EnterpriseOne のビジネス関数にのみアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="2814e-103">Microsoft BizTalk Adapter for JD Edwards EnterpriseOne provides access only to JD Edwards EnterpriseOne business functions.</span></span> <span data-ttu-id="2814e-104">ビジネス関数メタデータは、ビジネス関数インターフェイスをとおして読み取られ、ビジネス関数の一覧および関連するデータ構造の検索に使用されます。</span><span class="sxs-lookup"><span data-stu-id="2814e-104">Business function metadata is read using a business function interface and used to find a list of business functions and associated data structures.</span></span> <span data-ttu-id="2814e-105">メタデータは、すべてのビジネス関数メソッドのすべてのケースで厳密に型指定されます。</span><span class="sxs-lookup"><span data-stu-id="2814e-105">Metadata is strongly typed in all cases for all business function methods.</span></span>  
  
 <span data-ttu-id="2814e-106">すべてのビジネス関数メソッドがある同じ呼び出し規約: 派生は、システムは、3 つのパラメーターとデータ構造体へのポインター。</span><span class="sxs-lookup"><span data-stu-id="2814e-106">All business function methods have the same calling convention: three parameters that are system derived, and a pointer to a data structure.</span></span> <span data-ttu-id="2814e-107">次の表に、ビジネス関数のデータ型がどのように表されるかを示します。</span><span class="sxs-lookup"><span data-stu-id="2814e-107">The following table shows how business function data types are represented.</span></span>  
  
|<span data-ttu-id="2814e-108">JD Edwards EnterpriseOne のデータ型</span><span class="sxs-lookup"><span data-stu-id="2814e-108">JD Edwards EnterpriseOne Data Type</span></span>|<span data-ttu-id="2814e-109">Description</span><span class="sxs-lookup"><span data-stu-id="2814e-109">Description</span></span>|<span data-ttu-id="2814e-110">WDSL 変換</span><span class="sxs-lookup"><span data-stu-id="2814e-110">WDSL Conversion</span></span>|  
|----------------------------------------|-----------------|---------------------|  
|<span data-ttu-id="2814e-111">char</span><span class="sxs-lookup"><span data-stu-id="2814e-111">char</span></span>|<span data-ttu-id="2814e-112">文字の文字列。</span><span class="sxs-lookup"><span data-stu-id="2814e-112">Character string.</span></span>|<span data-ttu-id="2814e-113">xsd:string の 1</span><span class="sxs-lookup"><span data-stu-id="2814e-113">xsd:string of 1</span></span>|  
|<span data-ttu-id="2814e-114">int</span><span class="sxs-lookup"><span data-stu-id="2814e-114">int</span></span>|<span data-ttu-id="2814e-115">短整数。</span><span class="sxs-lookup"><span data-stu-id="2814e-115">Short integer.</span></span>|<span data-ttu-id="2814e-116">xsd:short</span><span class="sxs-lookup"><span data-stu-id="2814e-116">xsd:short</span></span>|  
|<span data-ttu-id="2814e-117">long</span><span class="sxs-lookup"><span data-stu-id="2814e-117">long</span></span>|<span data-ttu-id="2814e-118">長整数。</span><span class="sxs-lookup"><span data-stu-id="2814e-118">Long integer.</span></span>|<span data-ttu-id="2814e-119">xsd:short</span><span class="sxs-lookup"><span data-stu-id="2814e-119">xsd:short</span></span>|  
|<span data-ttu-id="2814e-120">文字列</span><span class="sxs-lookup"><span data-stu-id="2814e-120">String</span></span>|<span data-ttu-id="2814e-121">参照してください[文字列値の処理](../core/handling-string-values2.md)です。</span><span class="sxs-lookup"><span data-stu-id="2814e-121">See [Handling String Values](../core/handling-string-values2.md).</span></span>|<span data-ttu-id="2814e-122">xsd:string</span><span class="sxs-lookup"><span data-stu-id="2814e-122">xsd:string</span></span>|  
|<span data-ttu-id="2814e-123">JDEDATE</span><span class="sxs-lookup"><span data-stu-id="2814e-123">JDEDATE</span></span>|<span data-ttu-id="2814e-124">日付の特殊な実装。</span><span class="sxs-lookup"><span data-stu-id="2814e-124">Special implementation of dates.</span></span>|<span data-ttu-id="2814e-125">xsd:date</span><span class="sxs-lookup"><span data-stu-id="2814e-125">xsd:date</span></span>|  
|<span data-ttu-id="2814e-126">MATH_NUMERIC</span><span class="sxs-lookup"><span data-stu-id="2814e-126">MATH_NUMERIC</span></span>|<span data-ttu-id="2814e-127">浮動小数点数の特殊な実装 (通貨の値を含む)。</span><span class="sxs-lookup"><span data-stu-id="2814e-127">Special implementation of floating point numbers, including currency values.</span></span>|<span data-ttu-id="2814e-128">32 の xsd:string</span><span class="sxs-lookup"><span data-stu-id="2814e-128">xsd:string of 32</span></span>|  
|<span data-ttu-id="2814e-129">Byte</span><span class="sxs-lookup"><span data-stu-id="2814e-129">Byte</span></span>|<span data-ttu-id="2814e-130">単一の符号なし文字。</span><span class="sxs-lookup"><span data-stu-id="2814e-130">Single unsigned character.</span></span>|<span data-ttu-id="2814e-131">xsd:string の 1</span><span class="sxs-lookup"><span data-stu-id="2814e-131">xsd:string of 1</span></span>|  
|<span data-ttu-id="2814e-132">JDEUTIME</span><span class="sxs-lookup"><span data-stu-id="2814e-132">JDEUTIME</span></span>|<span data-ttu-id="2814e-133">日付と時刻の両方のコンポーネントが含まれます。</span><span class="sxs-lookup"><span data-stu-id="2814e-133">Includes both date and time components.</span></span><br /><br /> <span data-ttu-id="2814e-134">データ型はすべての日付と時刻を格納し、日付と時刻の計算をすべて協定世界時 (UTC) で実行します。</span><span class="sxs-lookup"><span data-stu-id="2814e-134">The data type stores all dates/times and performs all date/time calculations in Coordinated Universal Time (UTC).</span></span>|<span data-ttu-id="2814e-135">xsd:dateTime</span><span class="sxs-lookup"><span data-stu-id="2814e-135">xsd:dateTime</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2814e-136">参照</span><span class="sxs-lookup"><span data-stu-id="2814e-136">See Also</span></span>  
 <span data-ttu-id="2814e-137">[MATH_NUMERIC 型の使用](../core/using-the-math-numeric-type1.md) </span><span class="sxs-lookup"><span data-stu-id="2814e-137">[Using the MATH_NUMERIC Type](../core/using-the-math-numeric-type1.md) </span></span>  
 <span data-ttu-id="2814e-138">[文字列値の処理](../core/handling-string-values2.md) </span><span class="sxs-lookup"><span data-stu-id="2814e-138">[Handling String Values](../core/handling-string-values2.md) </span></span>  
 [<span data-ttu-id="2814e-139">付録 b: データ型</span><span class="sxs-lookup"><span data-stu-id="2814e-139">Appendix B: Data Types</span></span>](../core/appendix-b-data-types.md)