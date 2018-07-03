---
title: 論理演算 Functoid |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e37cdfc3-66de-4333-84eb-a8765afa8407
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 873e2b0ea1189586f9cabfbcb43c6ef276f34e0f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007595"
---
# <a name="logical-functoids"></a><span data-ttu-id="5393d-102">論理演算 Functoid</span><span class="sxs-lookup"><span data-stu-id="5393d-102">Logical Functoids</span></span>

## <a name="overview"></a><span data-ttu-id="5393d-103">概要</span><span class="sxs-lookup"><span data-stu-id="5393d-103">Overview</span></span>
<span data-ttu-id="5393d-104">**論理**functoid は、次の種類の操作の実行に使用されます。</span><span class="sxs-lookup"><span data-stu-id="5393d-104">**Logical** functoids are used to perform the following types of operations:</span></span>  

- <span data-ttu-id="5393d-105">実行時に特定の論理テストを実行します。</span><span class="sxs-lookup"><span data-stu-id="5393d-105">Perform specific logical tests at run time.</span></span> <span data-ttu-id="5393d-106">**論理和**、**論理否定**と**論理的かつ**次などの送信先インスタンス メッセージにレコードを作成するかどうかを判断する functoid を使用できます。</span><span class="sxs-lookup"><span data-stu-id="5393d-106">The **Logical OR**, **Logical NOT** and **Logical AND** functoids can be used to determine whether a record is created in a destination instance message, such as the following:</span></span>  

   <span data-ttu-id="5393d-107">場合 ShipTo**または**OrderedBy が存在する、BillTo address レコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="5393d-107">If ShipTo **OR** OrderedBy are present, create BillTo address record.</span></span>  

   <span data-ttu-id="5393d-108">これらの functoid と組み合わせて使用することもできます、**ループ**functoid を何回、レコードのループを構成します。</span><span class="sxs-lookup"><span data-stu-id="5393d-108">You can also use these functoids in conjunction with the **Looping** functoid to configure how many times a record loops.</span></span>  

- <span data-ttu-id="5393d-109">実行時に特定のレコードを送信先インスタンス メッセージに作成するかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="5393d-109">Control whether a specific record is created in a destination instance message at run time.</span></span> <span data-ttu-id="5393d-110">などの Functoid **IsNil**、**数値検査**、**未満**、および**より大きい**レコードが作成されたかどうか、コントロールを使用できます。</span><span class="sxs-lookup"><span data-stu-id="5393d-110">Functoids such as **IsNil**, **Logical Numeric**, **Less Than**, and **Greater Than** can be used to control whether a record is created.</span></span>  

   <span data-ttu-id="5393d-111">これらの論理演算 functoid のいずれかの結果が**True**、送信先インスタンス メッセージに対応するレコードが生成されます。</span><span class="sxs-lookup"><span data-stu-id="5393d-111">If the result of one of these logical functoids is **True**, the corresponding record in the destination instance message is generated.</span></span> <span data-ttu-id="5393d-112">結果は場合**False**を送信先インスタンス メッセージに対応するレコードは生成されません。</span><span class="sxs-lookup"><span data-stu-id="5393d-112">If the result is **False**, the corresponding record in the destination instance message is not generated.</span></span>  

  <span data-ttu-id="5393d-113">Functoid **IsNil**、**論理日付**、**論理的な実体**、**論理否定**、**論理数値**、および**文字列検査**のみ 1 つのパラメーターをそのまま使用します。</span><span class="sxs-lookup"><span data-stu-id="5393d-113">The functoids **IsNil**, **Logical Date**, **Logical Existence**, **Logical NOT**, **Logical Numeric**, and **Logical String** accept only one parameter.</span></span> <span data-ttu-id="5393d-114">Functoid**等しい**、**より大きい**、**より大きいまたは等しい**、**未満**、 **未満**、および**等しく**2 つの入力パラメーターをそのまま使用します。</span><span class="sxs-lookup"><span data-stu-id="5393d-114">The functoids **Equal**, **Greater Than**, **Greater Than or Equal To**, **Less Than**, **Less Than or Equal To**, and **Not Equal** accept two input parameters.</span></span> <span data-ttu-id="5393d-115">一方、**論理的かつ**と**論理和**functoid は 2 ~ 100 の入力パラメーターを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="5393d-115">Whereas, the **Logical AND** and **Logical OR** functoids accept input parameters between 2 and 100.</span></span>  

  <span data-ttu-id="5393d-116">出力を**論理**functoid は、マップ内の他の functoid への入力としても使用できます。</span><span class="sxs-lookup"><span data-stu-id="5393d-116">The output of a **Logical** functoid can also be accepted as input to other functoids in a map.</span></span> <span data-ttu-id="5393d-117">両方の場合、**論理**ループ functoid の使用、および、functoid およびループ functoid が相互にリンクし、送信先スキーマ内のレコードにリンクされている場合にのみ、**論理**functoid の出力が**True**します。</span><span class="sxs-lookup"><span data-stu-id="5393d-117">If both a **Logical** functoid and a looping functoid are linked together, and then linked to a record in the destination schema, the looping functoid is used only when the **Logical** functoid output is **True**.</span></span>  

  <span data-ttu-id="5393d-118">使用することも**論理**functoid と、**値のマッピング**または**値のマッピング (フラット化)** 送信先インスタンス メッセージ内のレコードかどうかを制御する functoid作成されます。</span><span class="sxs-lookup"><span data-stu-id="5393d-118">You can also use **Logical** functoids with the **Value Mapping** or **Value Mapping (Flattening)** functoids to control whether a record in the destination instance message is created.</span></span>  

> [!IMPORTANT]
>  <span data-ttu-id="5393d-119">2 つの異なる 2 つのレコードまたは送信元スキーマ内のフィールドをリンクする場合**論理**functoid、し、それぞれのリンク、**論理**functoid を送信先スキーマで同じレコード最初のみ**論理**functoid ので、生成された XSLT Extensible Stylesheet Language Transformations () を使用します。</span><span class="sxs-lookup"><span data-stu-id="5393d-119">If you link two records or fields in the source schema to two different **Logical** functoids, and then link each of the **Logical** functoids to the same record in the destination schema, only the first **Logical** functoid is used in the generated Extensible Stylesheet Language Transformations (XSLT).</span></span> <span data-ttu-id="5393d-120">2 番目のリンクの 2 番目の**論理**functoid は無視されます。</span><span class="sxs-lookup"><span data-stu-id="5393d-120">The second link, from the second **Logical** functoid, is ignored.</span></span>  

> [!NOTE]
>  <span data-ttu-id="5393d-121">論理演算 functoid は、2 つの文字列を比較するときに大文字小文字を区別します。</span><span class="sxs-lookup"><span data-stu-id="5393d-121">Logical functoids are case-sensitive when comparing two strings.</span></span> <span data-ttu-id="5393d-122">たとえば、"Abc" と "abc" は、同じではありません。</span><span class="sxs-lookup"><span data-stu-id="5393d-122">For example, "Abc" and "abc" are not equal.</span></span> <span data-ttu-id="5393d-123">このルールの例外は**論理**functoid は、ブール値を表す文字列を比較**True**と**False**します。</span><span class="sxs-lookup"><span data-stu-id="5393d-123">The exception to this rule is when **Logical** functoids compare strings that represent the Boolean values **True** and **False**.</span></span> <span data-ttu-id="5393d-124">たとえば、"True" と "true" は同じです。</span><span class="sxs-lookup"><span data-stu-id="5393d-124">For example, "True" and "true" are equal.</span></span>  

## <a name="available-functoids"></a><span data-ttu-id="5393d-125">使用可能な functoid</span><span class="sxs-lookup"><span data-stu-id="5393d-125">Available functoids</span></span>  
 <span data-ttu-id="5393d-126">**論理**functoid には。</span><span class="sxs-lookup"><span data-stu-id="5393d-126">The **Logical** functoids are:</span></span> 

* <span data-ttu-id="5393d-127">等号</span><span class="sxs-lookup"><span data-stu-id="5393d-127">Equal</span></span>
* <span data-ttu-id="5393d-128">より大きい</span><span class="sxs-lookup"><span data-stu-id="5393d-128">Greater Than</span></span>
* <span data-ttu-id="5393d-129">大きいまたは等しい</span><span class="sxs-lookup"><span data-stu-id="5393d-129">Greater Than or Equal To</span></span>
* <span data-ttu-id="5393d-130">IsNil</span><span class="sxs-lookup"><span data-stu-id="5393d-130">IsNil</span></span>
* <span data-ttu-id="5393d-131">小さい</span><span class="sxs-lookup"><span data-stu-id="5393d-131">Less Than</span></span>
* <span data-ttu-id="5393d-132">等しいまたはそれよりも小さい</span><span class="sxs-lookup"><span data-stu-id="5393d-132">Less Than or Equal To</span></span>
* <span data-ttu-id="5393d-133">論理積</span><span class="sxs-lookup"><span data-stu-id="5393d-133">Logical AND</span></span>
* <span data-ttu-id="5393d-134">日付検査</span><span class="sxs-lookup"><span data-stu-id="5393d-134">Logical Date</span></span>
* <span data-ttu-id="5393d-135">論理的な実体</span><span class="sxs-lookup"><span data-stu-id="5393d-135">Logical Existence</span></span>
* <span data-ttu-id="5393d-136">論理否定</span><span class="sxs-lookup"><span data-stu-id="5393d-136">Logical NOT</span></span>
* <span data-ttu-id="5393d-137">数値検査</span><span class="sxs-lookup"><span data-stu-id="5393d-137">Logical Numeric</span></span>
* <span data-ttu-id="5393d-138">論理和</span><span class="sxs-lookup"><span data-stu-id="5393d-138">Logical OR</span></span>
* <span data-ttu-id="5393d-139">文字列検査</span><span class="sxs-lookup"><span data-stu-id="5393d-139">Logical String</span></span>
* <span data-ttu-id="5393d-140">不等号</span><span class="sxs-lookup"><span data-stu-id="5393d-140">Not Equal</span></span>

<span data-ttu-id="5393d-141">これらの関数の詳細については、[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。</span><span class="sxs-lookup"><span data-stu-id="5393d-141">More details on these functions are [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>

## <a name="see-also"></a><span data-ttu-id="5393d-142">参照</span><span class="sxs-lookup"><span data-stu-id="5393d-142">See Also</span></span>  
- [<span data-ttu-id="5393d-143">マップに基本 Functoid を追加する方法</span><span class="sxs-lookup"><span data-stu-id="5393d-143">How to Add Basic Functoids to a Map</span></span>](../core/how-to-add-basic-functoids-to-a-map.md)   
- <span data-ttu-id="5393d-144">**論理演算 Functoid のリファレンス** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="5393d-144">**Logical Functoids Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
