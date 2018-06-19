---
title: いずれかの属性ノード |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fa2d25bc-3a8f-4fd9-acad-341b8e80c737
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 82490a114149e3d4f71e3598900be5599c8a36e2
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25964648"
---
# <a name="any-attribute-nodes"></a>任意の属性ノード
BizTalk エディターで行うこともできます、**すべての属性**ノードを対象の 0 個以上の不明な属性が表示されるインスタンス メッセージ内の (既知の) 要素を示します。 特定の要素がインスタンス メッセージ内の特定の場所に出現することはあらかじめわかっているが、そこにどのような属性が入るかが不確定の場合に使用できます。 配置した場合、**すべての属性**内のノード、**レコード**ノードは関連する要素に関連付けられている、BizTalk で処理する、その要素すべて関連付けられている属性がされている唯一の要件構文的に解決 (attributeName ="attributeValue") です。  
  
> [!NOTE]
>  BizTalk エディターで、**すべての属性**ノードは、文字列で表される\<AnyAttribute\>スキーマ ツリー ビューでします。  
  
> [!NOTE]
>  整形式 XML としてメッセージの未知の部分を検証を使用して内容を制御できます、 **Process Contents**プロパティです。 多くの場合を設定する必要があります、 **Process Contents**プロパティを**Skip**の場所にあるインスタンス メッセージの内容を**すべての属性**に処理するノード. 既定値を保持**Strict**の**Process Contents**プロパティは、インスタンス メッセージの検証の成功をできなくなります。  
>
> このプロパティの詳細について[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。
  
## <a name="xsd-representation"></a>XSD 表記  
 ときに、**すべての属性**ノードに追加された、**レコード**ノードまたは、**属性グループ**、1 つの XML タグにノードが追加、対応する XML スキーマ定義 (XSD) 言語スキーマの表記。 次の例では、新しい**すべての属性**、XSD 表現が示すように、ノードで太字を既存に追加された**レコード**ノードが格納されている、**フィールド要素**ノード。  
  
```  
<xs:element name="ExistingRecord">  
    <xs:complexType>  
        <xs:sequence>  
            <xs:element name="ExistingFieldElement" type="xs:string" />  
        </xs:sequence>  
        <xs:anyAttribute />  
    </xs:complexType>  
</xs:element  
```  
  
 前の例では、新しいの XSD 表記で**すべての属性**ノードを追加、 **anyAttribute**を含むの末尾に要素 (**レコード**ノード) **要素**要素、外部、**シーケンス**要素と内、 **complexType**要素。 ここではすべて**属性**以外でこれらの要素、**属性グループ**ノード、それを含んでいるに追加されます**要素**要素。  
  
 ここでは、およびあると仮定して、 **Process Contents**のプロパティ、**すべての属性**に設定されているノード**Skip**内で、インスタンス メッセージは、このスキーマ フラグメントで、によって左右されます**ExistingRecord**要素が必要とし、適切な形式の XML 構文に関する限り、任意の属性を含めることができます、します。 (この例では XSD に準拠してにも必要があります、 **ExistingFieldElement**要素もします)。  
  
## <a name="see-also"></a>参照  
 [スキーマの BizTalk 表記](../core/biztalk-representation-of-schemas.md)   
 [ノードのプロパティ](../core/node-properties.md)   
 [ノードのプロパティを設定する方法](../core/how-to-set-node-properties.md)   
 [[すべての要素] ノード](../core/any-element-nodes.md)