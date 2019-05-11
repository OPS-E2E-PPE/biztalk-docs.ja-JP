---
title: いずれかの属性ノード |Microsoft Docs
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
ms.openlocfilehash: 7f20f3b9977331826b758eb89f7a1ae936f682d2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65359169"
---
# <a name="any-attribute-nodes"></a>任意の属性ノード
使用できる BizTalk エディターで、**すべての属性**ノードが 0 個以上の不明な属性が表示される対象のインスタンス メッセージ内の (既知の) 要素を示すことです。 不確定の場合に、特定の要素は、インスタンス メッセージ内の特定の場所に存在するが、その要素を正確にどのような属性が不明されているを含む可能性があります。 配置した場合、**すべての属性**内のノード、**レコード**関連する要素に関連付けられているノードでは、BizTalk を処理できます、その要素に関連付けられたすべての属性がされている唯一の要件構文を修正 (attributeName ="attributeValue")。  
  
> [!NOTE]
>  BizTalk エディターで、**すべての属性**ノードが文字列で表される\<AnyAttribute\>スキーマ ツリー ビューで。  
> 
> [!NOTE]
>  整形式 XML として、メッセージの未知の部分を検証を使用して程度を制御することができます、 **Process Contents**プロパティ。 多くの場合は、設定する必要があります、 **Process Contents**プロパティを**スキップ**の位置にあるインスタンス メッセージの内容として、**すべての属性**処理するノード. 既定値を保持**Strict**の**Process Contents**プロパティがインスタンス メッセージの検証の成功を防ぐためです。  
> 
> このプロパティについて詳しく[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。
  
## <a name="xsd-representation"></a>XSD 表記  
 ときに、**すべての属性**にノードを追加、**レコード**ノードまたは、**属性グループ**ノード、1 つの XML タグが、対応する XML スキーマ定義 (XSD) 言語に追加スキーマの表現。 次の例では、新しい**すべての属性**XSD 表現が示すように、ノードで太字を既存に追加された**レコード**既に含まれているノード、**フィールド要素**ノード。  
  
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
  
 前の例では、新しいの XSD 表記で**すべての属性**ノードを追加、 **anyAttribute**含むの末尾に要素 (**レコード**ノード) **要素**要素、外部、**シーケンス**要素内で、 **complexType**要素。 ここではすべて**属性**要素を除く、**属性グループ**ノード、それを含んでいるに追加されます**要素**要素。  
  
 ここでは、およびあると仮定して、 **Process Contents**のプロパティ、**すべての属性**にノードが設定されている**スキップ**内でこのスキーマのフラグメントをによって管理されるインスタンスメッセージ**ExistingRecord**要素が必要ですが、XML 構文に関して適切な形式である限り、任意の属性を含めることができます。 (この例では XSD に準拠している、含める必要があります、 **ExistingFieldElement**要素もします)。  
  
## <a name="see-also"></a>参照  
 [スキーマの BizTalk 表記](../core/biztalk-representation-of-schemas.md)   
 [ノードのプロパティ](../core/node-properties.md)   
 [ノードのプロパティを設定する方法](../core/how-to-set-node-properties.md)   
 [[すべての要素] ノード](../core/any-element-nodes.md)