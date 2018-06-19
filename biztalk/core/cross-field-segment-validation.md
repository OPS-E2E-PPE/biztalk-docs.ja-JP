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
# <a name="cross-field-segment-validation"></a>クロス フィールド セグメント検証
EDI 受信パイプラインと EDI 送信パイプラインは、X12 エンコード メッセージのトランザクション セット データ要素に対してクロスフィールド/セグメント検証を実行できます。 この検証は、X12 では関係条件と呼ばれます。 クロス フィールド検証は、注釈を表現し、その結果、EDI 検証に関連しています。  
  
> [!NOTE]
>  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は、EDIFACT 依存ルールをサポートしていません。  
  
 X12 エンコード メッセージの場合、メッセージ スキーマの X12ConditionDesignator_Check フラグを "Yes" に設定することで、この検証を有効にできます。 このフラグは、スキーマの "appinfo" セクションの注釈にあります。 既定では、このフラグは "No" に設定され、クロスフィールド/セグメント検証は X12 スキーマに対して有効になりません。 HIPAA スキーマに対しては、既定値は "Yes" に設定され、クロスフィールド/セグメント検証が有効になります。  
  
> [!NOTE]
>  クロスフィールド/セグメント検証は、EDI データ要素検証および拡張された (BTS-XSD) 検証とは異なります。 EDI データ要素検証または拡張された検証は、クロスフィールド/セグメント検証を実行しなくても実行できます。また、クロスフィールド/セグメント検証は、EDI データ要素検証または拡張された検証を実行しなくても実行できます。  
  
 X12 の選択肢は、必須 (M)、オプション (O)、および関係 (R) で構成されます (クロスフィールド検証)。 オプションが必須の場合、複合型の 1 つ以上のコンポーネント データ要素に値が格納されていることが必要です。  
  
## <a name="x12-optionality"></a>X12 の選択肢  
 X12 では、関係が選択されたクロスフィールド/セグメント検証には、スキーマのルールに記載されている一連のチェックが含まれます。 各ルールは、の次の要素によって識別される、 \<xs:annotation\>要素。  
  
```  
<b:Rule subjects="X12ConditionDesignatorX_<relational_condition>"…>  
```  
  
 "ルール" 要素の関係条件は、そのルールで検証される内容を示します。 この要素には、クロスフィールド検証が実行されるサブジェクトの一覧が含まれます。 サブジェクトは、次のノードに含まれています。  
  
```  
<b:Subject name="<subject>"/>  
```  
  
 次の表に、X12 の関係条件を示します。  
  
|下位分類|関係条件|Description|  
|-----------------------|--------------------------|-----------------|  
|Paired|X12ConditionDesignatorX_Paired|関係条件で指定されたサブジェクト要素のいずれかが存在する場合、指定されたすべてのサブジェクト要素が存在する必要があります。|  
|必須|X12ConditionDesignatorX_Required|関係条件で指定された少なくとも 1 つのサブジェクト要素が存在する必要があります。|  
|Exclusion|X12ConditionDesignatorX_Exclusion|関係条件で指定されたサブジェクト要素のうち、1 つだけが存在する可能性があります。|  
|条件付き|X12ConditionDesignatorX_Conditional|関係条件で指定された最初のサブジェクト要素が存在する場合、その他のすべてのサブジェクト要素が存在する必要があります。 条件の最初の要素として指定されていない要素のいずれかまたはすべてが、最初の要素が存在しなくても表示される可能性があります。 条件の要素の順序は、データ セグメントのデータ要素の順序と同じである必要はありません。|  
|List Conditional|X12ConditionDesignatorX_Exclusion|関係条件で指定された最初のサブジェクト要素が存在する場合、残りのサブジェクト要素の少なくとも 1 つが存在する必要があります。 条件の最初の要素として指定されていない要素のいずれかまたはすべてが、最初の要素が存在しなくても表示される可能性があります。 条件の要素の順序は、データ セグメントのデータ要素の順序と同じである必要はありません。|  
  
## <a name="see-also"></a>参照  
 [EDI メッセージの検証](../core/edi-message-validation.md)