---
title: "属性グループ ノード |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ea02fae8-4e03-486a-8d9d-185ae230d3a0
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 04db816f1209b7cd503b9a162cdd2a030ba86292
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="attribute-group-nodes"></a>[属性グループ] ノード

## <a name="overview"></a>概要
追加する BizTalk エディターで、**属性グループ**ノードを**レコード**ノードまたは別**属性グループ**をより詳細に使用すると予想される属性のグループを含むノード1 よりも**レコード**ノード。 追加する、**属性グループ**別のノード**属性グループ**ノードは、属性グループの入れ子を実現します。 これにより、1 か所で複数使用できる属性のグループを定義する**レコード**または**属性グループ**ノード。 それ以降、属性グループに対して行った変更は、その属性グループに関連付けられたすべてのノードに反映されます。 このしくみは、修正を加えたノードのコンテキストに依存しません。  
  
> [!NOTE]
>  BizTalk エディターで、 **AttributeGroup**ノードが既定では、文字列で表される\<AttribGroup:attribGroup*N*> スキーマ ツリー ビューで、 *N*単調に増加する数字を指定します。 AttribGroup を変更することができます*N*に新しい一意の名前を入力してその名前の部分の**Group Reference**プロパティです。  
  
 最初に作成するときに、**属性グループ**ノード、単に挿入することのいずれか、**レコード**または**属性グループ**ノードをそのが使用され、必要に応じて変更その名前でその**Group Reference**プロパティです。 別の同じ属性グループを使用する 2 つの方法がある**レコード**または**属性グループ**ノード。  
  
-   既存をコピーする**属性グループ**ノードを他に貼り付けると**レコード**ノード。  
  
-   新しいを挿入する**属性グループ**を他のノード**レコード**ノードを展開し、セット、 **Group Reference**新しいプロパティ**属性グループ**ノードを既存の参照**属性グループ**ノード。  
  
 その後、変更することができます、**属性グループ**ノード — などの追加や削除、**フィールド属性**ノード: いずれかのコンテキストで**レコード**または**属性グループ**貼り付け先のノードです。 変更は他のすべてに反映されますを**レコード**または**属性グループ**属性グループが関連付けられているノードです。  
  
 追加するには、無意味な**属性グループ**関連するノードが含まれている、少なくとも 1 つの関連するノードを追加することがなくノード**フィールド属性**ノード、 **Any 属性**ノード、および (入れ子になった)**属性グループ**ノード。 属性を 1 つしか持たないような属性グループを作成しても、将来、さらに多くの属性を追加することを想定しているのでなければ、あまり意味はありません。  
  
 **属性グループ**属性のグループを構築および結合する方法に多くの可能性を許可する、ノードをネストすることができます。 **属性グループ**ノードを含めることも、**すべての属性**ノードに対応できるインスタンスの属性に関するワイルドカード文字機能を含む属性グループ。  
  
## <a name="xsd-representation"></a>XSD 表記  
 ときに、**属性グループ**ノードが最初に追加される、**レコード**ノードまたは別**属性グループ**ノード、対応する XML スキーマ定義 (XSD) の 2 つの領域言語表記のスキーマが影響を受けます。 次の例では、新しい**属性グループ** ノードで太字を既存に追加された**レコード**既存が格納されているノード**フィールド要素**ノード。  
  
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
  
 注方法、 **attributeGroup**の XSD 表記内の要素、**レコード**ノードが参照するグローバル**attributeGroup**要素の子として追加される、**スキーマ**要素。 このように、スキーマの XSD 内で、属性グループをグローバルとして定義することで、スキーマ内の任意の場所から属性グループを参照できるようにしています。  
  
> [!NOTE]
>  既定の属性グループ名は自動的に提供されているあるフォーム attrGroup*N*ここで、 *N*単調に増加する数字を指定します。 新しい一意の名前を提供することで属性グループの名前を変更することができます、 **Group Reference**プロパティです。 スキーマ ツリー内で属性グループの名前を変更することはできません。  
  
## <a name="see-also"></a>参照  
-  [スキーマの BizTalk 表記](../core/biztalk-representation-of-schemas.md)   
-  [ノードのプロパティ](../core/node-properties.md)   
-  **シーケンス グループ ノードのプロパティ**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]  
-  [ノードのプロパティを設定する方法](../core/how-to-set-node-properties.md)   
-  [フィールド属性 ノード](../core/field-attribute-nodes.md)   
-  [任意の属性ノード](../core/any-attribute-nodes.md)