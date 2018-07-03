---
title: ノードを記録 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 43af077d-5db8-43ca-8bd0-e3a9e3ebe2b0
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7ec23dcf604e1bd454ba7e69a57c250cf3b1872f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36982347"
---
# <a name="record-nodes"></a>[レコード] ノード
BizTalk エディターを使用する、**レコード**を個々 の項目は、情報のコレクションを表すノード。  

- 単純型の情報 (文字列や数値など)。子フィールド ノードとして表されます。 これらの子フィールド ノードには、いずれかを指定できる**フィールド要素**ノードまたは**フィールド属性**ノード。 これらの 2 種類のフィールド ノードの詳細については、次を参照してください。[フィールド要素 ノード](../core/field-element-nodes.md)と[フィールド属性 ノード](../core/field-attribute-nodes.md)します。  

- 子として表される複合型の情報、**レコード**ノードまたはグループ ノードとして (**シーケンス グループ**ノード、**グループの選択**ノード、または**すべてのグループ**ノード)。  

- 子として表される吟味については、各種**Any 要素**または**すべての属性**ノード。  

- によって表される属性のグループ、**属性グループ**ノード。  

  新しい子ノードを挿入すると、**レコード**ノード、子ノードが常に現在の子ノードの最後に挿入します。 内の XML スキーマ定義 (XSD) 言語表記で、新しい要素を追加して、要素の属性が内の要素の末尾に追加されたことを意味する、対応する領域の末尾に、**シーケンス**、 **選択肢**、**すべて**、または**グループ**要素と属性要素の後に出現する、他の属性要素の末尾に追加されます、**シーケンス**、**選択肢**、**すべて**、または**グループ**要素。  

## <a name="xsd-representation"></a>XSD 表記  
 最初に挿入される、新しいの XSD 表記と**レコード**次の例に示すように、3 行だけのノードで構成されます。  

```  
<xs:element name="Record">  
      <xs:complexType />  
</xs:element>  
```  

 ときに 1 つの 3 つの属性ノード以外の任意の子ノード (**フィールド属性**、**属性グループ**、および**すべての属性**) に追加されます、 **レコード**内に配置が既定では、ノード、**シーケンス**内の要素、 **complexType**要素。 **シーケンス**属性の最初の子ノードが追加、非属性のすべての子ノードが削除された場合に削除されたときに要素が追加されます。 内で 3 つすべての種類の属性ノードを追加、 **complexType**要素が外側と後に**シーケンス**要素。  

 **シーケンス**要素の属性には、子ノードが追加されたことができます、**選択肢**または**すべて**要素を変更する場合、 **Group Order Type (ノードすべてのスキーマのプロパティ)** をスキーマ ツリー内の対応するノードのプロパティ**選択肢**または**すべて**、それぞれします。  

 次の例では、**レコード**ノードが shipTo に変更されました。 内の場所、**レコード**属性と属性のノードが追加されるノードは、角かっこで表示されます。  

```  
<xs:element name="">  
    <xs:complexType>  
        <xs:sequence>  
            [Nonattribute child nodes of the record go here.]  
            [Always add new nonattribute child nodes to the end.]  
        </xs:sequence>  
            [Attribute child nodes of the record go here.]  
            [Always add new attribute child nodes to the end.]  
    </xs:complexType>  
</xs:element>  

```  

## <a name="see-also"></a>参照  
- [スキーマの BizTalk 表記](../core/biztalk-representation-of-schemas.md)   
- [ノードのプロパティ](../core/node-properties.md)   
- **ノードのプロパティを記録する**と**Group Order Type (すべてのスキーマのノード プロパティ)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
- [ノードのプロパティを設定する方法](../core/how-to-set-node-properties.md)
