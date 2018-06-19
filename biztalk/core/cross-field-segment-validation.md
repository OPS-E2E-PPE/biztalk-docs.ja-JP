---
title: クロス フィールド セグメント検証 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6e757b4f-71fe-44d5-9580-c8b1c8eb2366
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: efd3a0b5f68ded39fbf5cc88a4ba8aac6725602e
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25969404"
---
# <a name="cross-field-segment-validation"></a><span data-ttu-id="4257b-102">クロス フィールド セグメント検証</span><span class="sxs-lookup"><span data-stu-id="4257b-102">Cross Field-Segment Validation</span></span>
<span data-ttu-id="4257b-103">EDI 受信パイプラインと EDI 送信パイプラインは、X12 エンコード メッセージのトランザクション セット データ要素に対してクロスフィールド/セグメント検証を実行できます。</span><span class="sxs-lookup"><span data-stu-id="4257b-103">The EDI receive pipeline and EDI send pipeline can perform cross field/segment validation on transaction-set data elements in X12-encoded messages.</span></span> <span data-ttu-id="4257b-104">この検証は、X12 では関係条件と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="4257b-104">This validation is called relational conditions in X12.</span></span> <span data-ttu-id="4257b-105">クロス フィールド検証は、注釈を表現し、その結果、EDI 検証に関連しています。</span><span class="sxs-lookup"><span data-stu-id="4257b-105">Cross field validation is expressed through annotations, and as a result, it is related to EDI validation.</span></span>  
  
> [!NOTE]
>  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="4257b-106"> は、EDIFACT 依存ルールをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="4257b-106"> does not support EDIFACT dependency rules.</span></span>  
  
 <span data-ttu-id="4257b-107">X12 エンコード メッセージの場合、メッセージ スキーマの X12ConditionDesignator_Check フラグを "Yes" に設定することで、この検証を有効にできます。</span><span class="sxs-lookup"><span data-stu-id="4257b-107">For X12-encoded messages, you enable this validation by setting the X12ConditionDesignator_Check flag in the message schema to "Yes".</span></span> <span data-ttu-id="4257b-108">このフラグは、スキーマの "appinfo" セクションの注釈にあります。</span><span class="sxs-lookup"><span data-stu-id="4257b-108">This flag is in an annotation in the “appinfo” section of the schema.</span></span> <span data-ttu-id="4257b-109">既定では、このフラグは "No" に設定され、クロスフィールド/セグメント検証は X12 スキーマに対して有効になりません。</span><span class="sxs-lookup"><span data-stu-id="4257b-109">By default this flag is set to "No" and cross field\segment validation is not enabled for X12 schemas.</span></span> <span data-ttu-id="4257b-110">HIPAA スキーマに対しては、既定値は "Yes" に設定され、クロスフィールド/セグメント検証が有効になります。</span><span class="sxs-lookup"><span data-stu-id="4257b-110">For HIPAA schemas the default is set to “Yes” and cross field\segment validation is enabled.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4257b-111">クロスフィールド/セグメント検証は、EDI データ要素検証および拡張された (BTS-XSD) 検証とは異なります。</span><span class="sxs-lookup"><span data-stu-id="4257b-111">Cross-field/segment validation is distinct from both EDI data element validation and extended (BTS-XSD) validation.</span></span> <span data-ttu-id="4257b-112">EDI データ要素検証または拡張された検証は、クロスフィールド/セグメント検証を実行しなくても実行できます。また、クロスフィールド/セグメント検証は、EDI データ要素検証または拡張された検証を実行しなくても実行できます。</span><span class="sxs-lookup"><span data-stu-id="4257b-112">EDI data element validation and/or extended validation can be performed without performing cross-field/segment validation, and cross-field/segment validation can be performed without performing EDI data element validation and/or extended validation.</span></span>  
  
 <span data-ttu-id="4257b-113">X12 の選択肢は、必須 (M)、オプション (O)、および関係 (R) で構成されます (クロスフィールド検証)。</span><span class="sxs-lookup"><span data-stu-id="4257b-113">Optionality in X12 consists of Mandatory (M), Optional (O), and Relational (R) (cross field validation).</span></span> <span data-ttu-id="4257b-114">オプションが必須の場合、複合型の 1 つ以上のコンポーネント データ要素に値が格納されていることが必要です。</span><span class="sxs-lookup"><span data-stu-id="4257b-114">When the optionality is Mandatory, at least one component data element in composite types must be valued.</span></span>  
  
## <a name="x12-optionality"></a><span data-ttu-id="4257b-115">X12 の選択肢</span><span class="sxs-lookup"><span data-stu-id="4257b-115">X12 Optionality</span></span>  
 <span data-ttu-id="4257b-116">X12 では、関係が選択されたクロスフィールド/セグメント検証には、スキーマのルールに記載されている一連のチェックが含まれます。</span><span class="sxs-lookup"><span data-stu-id="4257b-116">In X12, cross field/segment validation for Relational optionality includes a series of checks listed in rules in the schema.</span></span> <span data-ttu-id="4257b-117">各ルールは、の次の要素によって識別される、 \<xs:annotation\>要素。</span><span class="sxs-lookup"><span data-stu-id="4257b-117">Each rule is identified by the following element in an \<xs:annotation\> element:</span></span>  
  
```  
<b:Rule subjects="X12ConditionDesignatorX_<relational_condition>"…>  
```  
  
 <span data-ttu-id="4257b-118">"ルール" 要素の関係条件は、そのルールで検証される内容を示します。</span><span class="sxs-lookup"><span data-stu-id="4257b-118">The relational condition in the “Rule” element indicates what is being validated by that rule.</span></span> <span data-ttu-id="4257b-119">この要素には、クロスフィールド検証が実行されるサブジェクトの一覧が含まれます。</span><span class="sxs-lookup"><span data-stu-id="4257b-119">This element includes a list of subjects upon which the cross field validation is executed.</span></span> <span data-ttu-id="4257b-120">サブジェクトは、次のノードに含まれています。</span><span class="sxs-lookup"><span data-stu-id="4257b-120">The subjects are included in the following node:</span></span>  
  
```  
<b:Subject name="<subject>"/>  
```  
  
 <span data-ttu-id="4257b-121">次の表に、X12 の関係条件を示します。</span><span class="sxs-lookup"><span data-stu-id="4257b-121">The following table shows the X12 relational conditions:</span></span>  
  
|<span data-ttu-id="4257b-122">下位分類</span><span class="sxs-lookup"><span data-stu-id="4257b-122">Subclassification</span></span>|<span data-ttu-id="4257b-123">関係条件</span><span class="sxs-lookup"><span data-stu-id="4257b-123">Relational Condition</span></span>|<span data-ttu-id="4257b-124">Description</span><span class="sxs-lookup"><span data-stu-id="4257b-124">Description</span></span>|  
|-----------------------|--------------------------|-----------------|  
|<span data-ttu-id="4257b-125">Paired</span><span class="sxs-lookup"><span data-stu-id="4257b-125">Paired</span></span>|<span data-ttu-id="4257b-126">X12ConditionDesignatorX_Paired</span><span class="sxs-lookup"><span data-stu-id="4257b-126">X12ConditionDesignatorX_Paired</span></span>|<span data-ttu-id="4257b-127">関係条件で指定されたサブジェクト要素のいずれかが存在する場合、指定されたすべてのサブジェクト要素が存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4257b-127">If any of the subject elements specified in the relational condition is present, then all of the subject elements specified must be present.</span></span>|  
|<span data-ttu-id="4257b-128">必須</span><span class="sxs-lookup"><span data-stu-id="4257b-128">Required</span></span>|<span data-ttu-id="4257b-129">X12ConditionDesignatorX_Required</span><span class="sxs-lookup"><span data-stu-id="4257b-129">X12ConditionDesignatorX_Required</span></span>|<span data-ttu-id="4257b-130">関係条件で指定された少なくとも 1 つのサブジェクト要素が存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4257b-130">At least one of the subject elements specified in the relational condition must be present.</span></span>|  
|<span data-ttu-id="4257b-131">Exclusion</span><span class="sxs-lookup"><span data-stu-id="4257b-131">Exclusion</span></span>|<span data-ttu-id="4257b-132">X12ConditionDesignatorX_Exclusion</span><span class="sxs-lookup"><span data-stu-id="4257b-132">X12ConditionDesignatorX_Exclusion</span></span>|<span data-ttu-id="4257b-133">関係条件で指定されたサブジェクト要素のうち、1 つだけが存在する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4257b-133">Not more than one of the subject elements specified in the relational condition may be present.</span></span>|  
|<span data-ttu-id="4257b-134">条件付き</span><span class="sxs-lookup"><span data-stu-id="4257b-134">Conditional</span></span>|<span data-ttu-id="4257b-135">X12ConditionDesignatorX_Conditional</span><span class="sxs-lookup"><span data-stu-id="4257b-135">X12ConditionDesignatorX_Conditional</span></span>|<span data-ttu-id="4257b-136">関係条件で指定された最初のサブジェクト要素が存在する場合、その他のすべてのサブジェクト要素が存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4257b-136">If the first subject element specified in the relational condition is present, then all other subject elements must be present.</span></span> <span data-ttu-id="4257b-137">条件の最初の要素として指定されていない要素のいずれかまたはすべてが、最初の要素が存在しなくても表示される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4257b-137">Any or all of the elements not specified as the first element in the condition may appear without requiring that the first element be present.</span></span> <span data-ttu-id="4257b-138">条件の要素の順序は、データ セグメントのデータ要素の順序と同じである必要はありません。</span><span class="sxs-lookup"><span data-stu-id="4257b-138">The order of the elements in the condition does not have to be the same as the order of the data elements in the data segments.</span></span>|  
|<span data-ttu-id="4257b-139">List Conditional</span><span class="sxs-lookup"><span data-stu-id="4257b-139">List Conditional</span></span>|<span data-ttu-id="4257b-140">X12ConditionDesignatorX_Exclusion</span><span class="sxs-lookup"><span data-stu-id="4257b-140">X12ConditionDesignatorX_List Conditional</span></span>|<span data-ttu-id="4257b-141">関係条件で指定された最初のサブジェクト要素が存在する場合、残りのサブジェクト要素の少なくとも 1 つが存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4257b-141">If the first subject element specified in the relational condition is present, then at least one of the remaining subject elements must be present.</span></span> <span data-ttu-id="4257b-142">条件の最初の要素として指定されていない要素のいずれかまたはすべてが、最初の要素が存在しなくても表示される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4257b-142">Any or all of the elements not specified as the first element in the condition may appear without requiring that the first element be present.</span></span> <span data-ttu-id="4257b-143">条件の要素の順序は、データ セグメントのデータ要素の順序と同じである必要はありません。</span><span class="sxs-lookup"><span data-stu-id="4257b-143">The order of the elements in the condition does not have to be the same as the order of the data elements in the data segments.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4257b-144">参照</span><span class="sxs-lookup"><span data-stu-id="4257b-144">See Also</span></span>  
 [<span data-ttu-id="4257b-145">EDI メッセージの検証</span><span class="sxs-lookup"><span data-stu-id="4257b-145">EDI Message Validation</span></span>](../core/edi-message-validation.md)