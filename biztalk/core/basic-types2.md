---
title: 基本的な Types2 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- JD Edwards EnterpriseOne adapters, data types
- adapters [JD Edwards EnterpriseOne adapters], data types
- data types, JD Edwards EnterpriseOne adapters
ms.assetid: 96a70f0d-f7f8-4e3b-9511-59b330910ead
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 51caed0e57b6b1869fb5e921b5a660293d71840d
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530501"
---
# <a name="basic-types"></a><span data-ttu-id="4f2bd-102">基本的な型</span><span class="sxs-lookup"><span data-stu-id="4f2bd-102">Basic Types</span></span>
<span data-ttu-id="4f2bd-103">Microsoft の BizTalk Adapter for JD Edwards EnterpriseOne では、JD Edwards EnterpriseOne のビジネス関数にのみアクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="4f2bd-103">Microsoft BizTalk Adapter for JD Edwards EnterpriseOne provides access only to JD Edwards EnterpriseOne business functions.</span></span> <span data-ttu-id="4f2bd-104">ビジネス関数メタデータは読み取り専用ビジネス関数のインターフェイスを使用してビジネス関数の一覧を検索するために使用し、関連するデータ構造。</span><span class="sxs-lookup"><span data-stu-id="4f2bd-104">Business function metadata is read using a business function interface and used to find a list of business functions and associated data structures.</span></span> <span data-ttu-id="4f2bd-105">メタデータはすべてのビジネス関数メソッドのすべてのケースで厳密に型指定します。</span><span class="sxs-lookup"><span data-stu-id="4f2bd-105">Metadata is strongly typed in all cases for all business function methods.</span></span>  
  
 <span data-ttu-id="4f2bd-106">すべてのビジネス関数メソッドと同じ呼び出し規約がある: システムから派生している 3 つのパラメーターとデータ構造体へのポインター。</span><span class="sxs-lookup"><span data-stu-id="4f2bd-106">All business function methods have the same calling convention: three parameters that are system derived, and a pointer to a data structure.</span></span> <span data-ttu-id="4f2bd-107">次の表では、ビジネス関数のデータ型の表現方法を示します。</span><span class="sxs-lookup"><span data-stu-id="4f2bd-107">The following table shows how business function data types are represented.</span></span>  
  
|<span data-ttu-id="4f2bd-108">JD Edwards EnterpriseOne のデータ型</span><span class="sxs-lookup"><span data-stu-id="4f2bd-108">JD Edwards EnterpriseOne Data Type</span></span>|<span data-ttu-id="4f2bd-109">説明</span><span class="sxs-lookup"><span data-stu-id="4f2bd-109">Description</span></span>|<span data-ttu-id="4f2bd-110">WDSL 変換</span><span class="sxs-lookup"><span data-stu-id="4f2bd-110">WDSL Conversion</span></span>|  
|----------------------------------------|-----------------|---------------------|  
|<span data-ttu-id="4f2bd-111">char</span><span class="sxs-lookup"><span data-stu-id="4f2bd-111">char</span></span>|<span data-ttu-id="4f2bd-112">文字の文字列。</span><span class="sxs-lookup"><span data-stu-id="4f2bd-112">Character string.</span></span>|<span data-ttu-id="4f2bd-113">xsd:string の 1</span><span class="sxs-lookup"><span data-stu-id="4f2bd-113">xsd:string of 1</span></span>|  
|<span data-ttu-id="4f2bd-114">ssNoversion</span><span class="sxs-lookup"><span data-stu-id="4f2bd-114">int</span></span>|<span data-ttu-id="4f2bd-115">短整数。</span><span class="sxs-lookup"><span data-stu-id="4f2bd-115">Short integer.</span></span>|<span data-ttu-id="4f2bd-116">xsd:short</span><span class="sxs-lookup"><span data-stu-id="4f2bd-116">xsd:short</span></span>|  
|<span data-ttu-id="4f2bd-117">long</span><span class="sxs-lookup"><span data-stu-id="4f2bd-117">long</span></span>|<span data-ttu-id="4f2bd-118">長整数。</span><span class="sxs-lookup"><span data-stu-id="4f2bd-118">Long integer.</span></span>|<span data-ttu-id="4f2bd-119">xsd:short</span><span class="sxs-lookup"><span data-stu-id="4f2bd-119">xsd:short</span></span>|  
|<span data-ttu-id="4f2bd-120">String</span><span class="sxs-lookup"><span data-stu-id="4f2bd-120">String</span></span>|<span data-ttu-id="4f2bd-121">参照してください[文字列値を処理する](../core/handling-string-values2.md)します。</span><span class="sxs-lookup"><span data-stu-id="4f2bd-121">See [Handling String Values](../core/handling-string-values2.md).</span></span>|<span data-ttu-id="4f2bd-122">xsd:string</span><span class="sxs-lookup"><span data-stu-id="4f2bd-122">xsd:string</span></span>|  
|<span data-ttu-id="4f2bd-123">JDEDATE</span><span class="sxs-lookup"><span data-stu-id="4f2bd-123">JDEDATE</span></span>|<span data-ttu-id="4f2bd-124">日付の特殊な実装。</span><span class="sxs-lookup"><span data-stu-id="4f2bd-124">Special implementation of dates.</span></span>|<span data-ttu-id="4f2bd-125">xsd:date</span><span class="sxs-lookup"><span data-stu-id="4f2bd-125">xsd:date</span></span>|  
|<span data-ttu-id="4f2bd-126">MATH_NUMERIC</span><span class="sxs-lookup"><span data-stu-id="4f2bd-126">MATH_NUMERIC</span></span>|<span data-ttu-id="4f2bd-127">浮動小数点数、通貨値などの特殊な実装。</span><span class="sxs-lookup"><span data-stu-id="4f2bd-127">Special implementation of floating point numbers, including currency values.</span></span>|<span data-ttu-id="4f2bd-128">32 の xsd:string</span><span class="sxs-lookup"><span data-stu-id="4f2bd-128">xsd:string of 32</span></span>|  
|<span data-ttu-id="4f2bd-129">バイト</span><span class="sxs-lookup"><span data-stu-id="4f2bd-129">Byte</span></span>|<span data-ttu-id="4f2bd-130">1 つの符号なし文字。</span><span class="sxs-lookup"><span data-stu-id="4f2bd-130">Single unsigned character.</span></span>|<span data-ttu-id="4f2bd-131">xsd:string の 1</span><span class="sxs-lookup"><span data-stu-id="4f2bd-131">xsd:string of 1</span></span>|  
|<span data-ttu-id="4f2bd-132">JDEUTIME</span><span class="sxs-lookup"><span data-stu-id="4f2bd-132">JDEUTIME</span></span>|<span data-ttu-id="4f2bd-133">日付と時刻の両方のコンポーネントが含まれます。</span><span class="sxs-lookup"><span data-stu-id="4f2bd-133">Includes both date and time components.</span></span><br /><br /> <span data-ttu-id="4f2bd-134">データ型は、すべての日付を保存/時刻し、世界協定時刻 (UTC) ですべての日付/時刻計算を実行します。</span><span class="sxs-lookup"><span data-stu-id="4f2bd-134">The data type stores all dates/times and performs all date/time calculations in Coordinated Universal Time (UTC).</span></span>|<span data-ttu-id="4f2bd-135">xsd:dateTime</span><span class="sxs-lookup"><span data-stu-id="4f2bd-135">xsd:dateTime</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4f2bd-136">参照</span><span class="sxs-lookup"><span data-stu-id="4f2bd-136">See Also</span></span>  
 <span data-ttu-id="4f2bd-137">[MATH_NUMERIC 型の使用](../core/using-the-math-numeric-type1.md) </span><span class="sxs-lookup"><span data-stu-id="4f2bd-137">[Using the MATH_NUMERIC Type](../core/using-the-math-numeric-type1.md) </span></span>  
 <span data-ttu-id="4f2bd-138">[文字列値の処理](../core/handling-string-values2.md) </span><span class="sxs-lookup"><span data-stu-id="4f2bd-138">[Handling String Values](../core/handling-string-values2.md) </span></span>  
 [<span data-ttu-id="4f2bd-139">付録 b:データ型</span><span class="sxs-lookup"><span data-stu-id="4f2bd-139">Appendix B: Data Types</span></span>](../core/appendix-b-data-types.md)