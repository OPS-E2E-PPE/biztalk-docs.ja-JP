---
title: ノードのグループの選択 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 466b525d-4d8c-4b8e-830d-eee27845c0dc
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c61dc6e070e6dd4832cdba999c44b74d9e80e05f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357335"
---
# <a name="choice-group-nodes"></a>ノードのグループの選択
BizTalk エディターでは、挿入できる、**グループの選択**を他のノード (またはノードのサブツリー全体) を含むノード インスタンス メッセージにうちの 1 つだけ表示されることができます。 指定されたインスタンス メッセージでは、有効な場合、必要があります存在の選択肢の 1 つだけです。 含まれているノードは、XML 要素に対応するノードである必要がありますが、XML 属性に対応するノードをすることはできません。  

> [!NOTE]
>  BizTalk エディターで、**グループの選択**ノードが文字列で表される\<選択肢\>スキーマ ツリー ビューで。 参照を設定した場合、**グループの選択**x などのノードとして表されます\<グループ: x\>スキーマ ツリー ビューで。  

## <a name="xsd-representation"></a>XSD 表記  
 ときに、**グループの選択**ノードが挿入、**レコード**ノード内の他の子ノードの最後に挿入されます、**シーケンス**、**選択肢**、または**すべて**内の要素、**レコード**ノード。 次の例を示しています、太字で、新しい**グループの選択**と XML スキーマ定義 (XSD) 言語で表されるノードを**選択肢**の末尾に挿入される要素、**シーケンス**内の要素を**レコード**ノード (ノードが自身の id を明確にするという名前) が使用されます。  

```  
<xs:element name="ContainingRecord">  
    <xs:complexType>  
        <xs:sequence>  
            <xs:element name="ExistingFieldElement" type="xs:string" />  
        </xs:sequence>  
    </xs:complexType>  
</xs:element>  

```  

 既定で、**選択肢**の要素を指定、 **minOccurs**属性のオプションがない、発生する必要があることを示すゼロ (0) の値。 Visual Studio のプロパティ ウィンドウでこの値を変更することができる場合、**グループの選択**スキーマ ツリー ビューでノードを選択します。  

 次の例は、同じ**選択肢**xsd 要素**要素**要素が 2 つの下位に対応する**レコード**ノード。  

```  
<xs:element name="ContainingRecord">  
    <xs:complexType>  
        <xs:sequence>  
            <xs:element name="ExistingFieldElement" type="xs:string" />  
            <xs:choice minOccurs="1" maxOccurs="1">  
                <xs:element name="usAddress">  
                    <xs:complexType>  
                        <xs:sequence>  
                        </xs:sequence>  
                    </xs:complexType>  
                </xs:element>  
                <xs:element name="foreignAddress">  
                    <xs:complexType>  
                        <xs:sequence>  
                        </xs:sequence>  
                    </xs:complexType>  
                </xs:element>  
            </xs:choice>  
        </xs:sequence>  
    </xs:complexType>  
</xs:element>  
```  

 この例では、2 つの兄弟で**レコード**ノードを使用して、インスタンス メッセージは、a レコードで、米国の住所情報または世界中の住所情報を持つレコードがかことについて説明します。 さらに、 **minOccurs**と**maxOccurs**のプロパティ、**グループの選択**ノード両方に設定されている 1 つ (1) Visual Studio のプロパティ ウィンドウでその結果、 *minOccurs*と*maxOccurs*の属性、**選択肢**XSD 表記で 1 つ (1) に設定されている要素。  

## <a name="see-also"></a>参照  
- [スキーマの BizTalk 表記](../core/biztalk-representation-of-schemas.md)   
- [ノードのプロパティ](../core/node-properties.md)   
- **シーケンス グループ ノードのプロパティ** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]     
- [ノードのプロパティを設定する方法](../core/how-to-set-node-properties.md)
