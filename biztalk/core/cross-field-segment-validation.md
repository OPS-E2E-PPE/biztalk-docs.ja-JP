---
title: クロス フィールド/セグメント検証 |Microsoft Docs
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
ms.openlocfilehash: e842c9376a6f143bb0979930c3d4239a355904c2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389839"
---
# <a name="cross-field-segment-validation"></a>クロス フィールド/セグメント検証
EDI 受信パイプラインと EDI 送信パイプラインが X12 でエンコードされたメッセージのトランザクション セット データ要素に対してクロス フィールド/セグメント検証を実行できます。 この検証には、X12 の関係条件は呼び出されます。 クロス フィールド検証が、注釈を使って表されます、その結果、EDI の検証に関連しています。  
  
> [!NOTE]
>  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDIFACT 依存ルールをサポートしません。  
  
 X12 でエンコードされたメッセージでは"Yes"にメッセージ スキーマの X12ConditionDesignator_Check フラグを設定して、この検証を有効にします。 このフラグは、スキーマの"appinfo"セクションの注釈です。 既定でこのフラグが"No"に設定され、クロス フィールド/セグメント検証が有効でない x12 スキーマです。 HIPAA スキーマに対して既定値が「はい」に設定し、クロス フィールド/セグメント検証を有効にします。  
  
> [!NOTE]
>  クロス フィールド/セグメント検証は、EDI データ要素検証および拡張された (BTS-XSD) 検証の両方からは異なります。 EDI データ要素検証または拡張された検証は、クロス フィールド/セグメント検証を実行することがなく実行できるし、クロス フィールド/セグメント検証は、EDI データ要素検証または拡張された検証を実行しなくても実行できます。  
  
 X12 の選択肢は、必須 (M)、省略可能な (O)、および関係 (R) (クロス フィールド検証) で構成されます。 選択肢が必須の場合は、複合型内の少なくとも 1 つのコンポーネント データ要素が値を持つ場合があります。  
  
## <a name="x12-optionality"></a>X12 の選択肢  
 X12 場合、にはクロス フィールド/セグメント リレーショナル optionality の検証により、一連ルール スキーマに記載のチェックにはが含まれます。 各ルールは、次の要素で識別される、 \<xs:annotation\>要素。  
  
```  
<b:Rule subjects="X12ConditionDesignatorX_<relational_condition>"…>  
```  
  
 「ルール」要素の関係条件では、そのルールで検証される内容を示します。 この要素には、クロス フィールド検証を実行する時にサブジェクトの一覧が含まれています。 次のノードでは、サブジェクトが含まれています。  
  
```  
<b:Subject name="<subject>"/>  
```  
  
 次の表示します X12 リレーショナルの条件:  
  
|補助分類|関係条件|説明|  
|-----------------------|--------------------------|-----------------|  
|ペアになっています。|X12ConditionDesignatorX_Paired|関係条件で指定されたサブジェクト要素のいずれかが存在する場合、すべて指定されたサブジェクト要素の必要がありますが存在します。|  
|必須|X12ConditionDesignatorX_Required|関係条件で指定されたサブジェクト要素の少なくとも 1 つが存在する必要があります。|  
|除外|X12ConditionDesignatorX_Exclusion|関係条件で指定されたサブジェクト要素の 1 つが存在する可能性があります。|  
|条件付き|X12ConditionDesignatorX_Conditional|関係条件で指定された最初のサブジェクト要素が存在する場合は、その他のすべてのサブジェクト要素が存在する必要があります。 最初の要素が存在することを必要とせず、条件の最初の要素として指定されていない要素の一部またはすべてがあります。 条件内の要素の順序は、データ セグメント内のデータ要素の順序と同じにするのにはありません。|  
|リストの条件付き|X12ConditionDesignatorX_List 条件|関係条件で指定された最初のサブジェクト要素が存在する場合、残りのサブジェクト要素の少なくとも 1 つあります。 最初の要素が存在することを必要とせず、条件の最初の要素として指定されていない要素の一部またはすべてがあります。 条件内の要素の順序は、データ セグメント内のデータ要素の順序と同じにするのにはありません。|  
  
## <a name="see-also"></a>参照  
 [EDI メッセージの検証](../core/edi-message-validation.md)