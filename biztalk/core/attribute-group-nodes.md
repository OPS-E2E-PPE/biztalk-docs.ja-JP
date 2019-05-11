---
title: 属性グループ ノード |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ea02fae8-4e03-486a-8d9d-185ae230d3a0
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 11bfc51f2a7ec1d4b8c7a856028e4d6b00ba8d22
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65359122"
---
# <a name="attribute-group-nodes"></a>属性グループ ノード

## <a name="overview"></a>概要
追加する BizTalk エディターで、**属性グループ**にノードを**レコード**ノードまたは別**属性グループ**をさらに使用する属性のグループを含むノード1 よりも**レコード**ノード。 追加、**属性グループ**別のノード**属性グループ**ノードは、属性グループの入れ子を実現します。 これにより、複数の使用できる 1 つの場所で属性のグループを定義する**レコード**または**属性グループ**ノード。 属性グループに対して行った変更は、すべての属性グループが関連付けられているノードに反映されます。 これは、変更が行われるノードのコンテキストに関係なく当てはまります。  

> [!NOTE]
>  BizTalk エディターで、 **AttributeGroup**ノードが既定では、文字列で表される\<AttribGroup:attribGroup*N* \>スキーマ ツリー ビューで、 *N*単調に増加する数字を指定します。 AttribGroup を変更する*N*に新しい一意の名前を入力して、その名前の部分の**グループ参照**プロパティ。  

 最初に作成するときに、**属性グループ**ノード、単に挿入することの 1 つ、**レコード**または**属性グループ**ノードが使用され、し必要に応じて変更その名前でその**グループ参照**プロパティ。 別の同じ属性グループを使用する 2 つの方法がある**レコード**または**属性グループ**ノード。  

- 既存をコピーする**属性グループ**ノードを他に貼り付けます**レコード**ノード。  

- 新しいを挿入する**属性グループ**を他のノード**レコード**ノード、および設定して、**グループ参照**プロパティの新しい**属性グループ**ノード、既存の参照を**属性グループ**ノード。  

  その後、変更することができます、**属性グループ**ノード: などの追加や削除、**フィールド属性**ノード-いずれかのコンテキストで**レコード**または**属性グループ**貼り付け先のノード。 変更が他のすべてに反映されます**レコード**または**属性グループ**属性グループが関連付けられているノード。  

  追加するには、無意味、**属性グループ**が関連するノードが含まれてに少なくとも 1 つのノードを追加せずにノード**フィールド属性**ノード、 **Any 属性**ノードと (入れ子になった)**属性グループ**ノード。 実際には、1 つの属性のみを含む属性グループ、あまり意味は、ポイントの詳細属性の追加、将来の計画を行っている場合を除き、します。  

  **属性グループ**属性のグループを構築および結合する方法に多くの可能性を許可するノードをネストできます。 **属性グループ**ノードを含めることも、**すべての属性**ノード、属性グループに対応できる属性のインスタンスに関して、ワイルドカード文字機能を格納することができます。  

## <a name="xsd-representation"></a>XSD 表記  
 ときに、**属性グループ**ノードが最初に追加、**レコード**ノードまたは別**属性グループ**ノード、対応する XML スキーマ定義 (XSD) の 2 つの領域言語表記のスキーマの影響を受けます。 次の例では、新しい**属性グループ**ノードで太字を既存に追加された**レコード**を既に含む既存のノード**フィールド要素**ノード。  

```  
        ...  
        <xs:element name="ExistingRecord">  
            <xs:complexType>  
                <xs:sequence>  
                    <xs:element name="ExistingFieldElement" type="xs:string" />  
                </xs:sequence>  
                <xs:attributeGroup ref="attrGroup0" />  
            </xs:complexType>  
        </xs:element>  
        ...   
    <xs:attributeGroup name="attrGroup0" />  
</xs:schema>  
```  

 注方法、 **attributeGroup**の XSD 表記内の要素、**レコード**ノードが参照するグローバル**attributeGroup**要素の子として追加される、**スキーマ**要素。 このグローバル定義のスキーマの XSD 表記内の属性グループは、属性グループをスキーマ全体で複数の場所で参照できます。  

> [!NOTE]
>  自動的に提供される既定の属性グループ名があるフォーム attrGroup*N*ここで、 *N*単調に増加する数字を指定します。 新しい一意の名前を提供することで属性グループの名前を変更することができます、**グループ参照**プロパティ。 属性グループ、スキーマ ツリー内で名前を変更できません。  

## <a name="see-also"></a>参照  
- [スキーマの BizTalk 表記](../core/biztalk-representation-of-schemas.md)   
- [ノードのプロパティ](../core/node-properties.md)   
- **シーケンス グループ ノードのプロパティ** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]  
- [ノードのプロパティを設定する方法](../core/how-to-set-node-properties.md)   
- [[フィールド属性] ノード](../core/field-attribute-nodes.md)   
- [[すべての属性] ノード](../core/any-attribute-nodes.md)
