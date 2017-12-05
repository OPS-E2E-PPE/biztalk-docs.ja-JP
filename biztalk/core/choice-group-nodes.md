---
title: "グループの選択ノード |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 466b525d-4d8c-4b8e-830d-eee27845c0dc
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 21d3007897343b7d517c11599a271b72e92d3710
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="choice-group-nodes"></a>選択肢グループ ノード
挿入できる BizTalk エディターで、**選択肢グループ**を他のノード (またはノードのサブツリー全体) を含むノード インスタンス メッセージにうちの 1 つだけ表示されることができます。 この場合、インスタンス メッセージには、選択されたいずれかのノードだけが含まれます。 取り込むノードは、XML 要素に対応するノードであることが必要です。ただし、XML 属性に対応するノードではありません。  
  
> [!NOTE]
>  BizTalk エディターで、**選択肢グループ**ノードは、文字列で表されます\<選択肢\>スキーマ ツリー ビューでします。 参照を設定した場合、**選択肢グループ**x などのノードとして表されます\<グループ:x\>スキーマ ツリー ビューでします。  
  
## <a name="xsd-representation"></a>XSD 表記  
 ときに、**グループの選択**ノードが挿入、**レコード**ノード内の他の子ノードの最後に挿入されます、**シーケンス**、**選択肢**、または**すべて**内の要素、**レコード**ノード。 次の例を示しています、太字で新しい方法**選択肢グループ**と XML スキーマ定義 (XSD) 言語で表されるノード、**選択肢**の最後に挿入される要素、**シーケンス**内の要素、**レコード**(ノードが自身の id を明確にするという名前) を持つノード。  
  
```  
<xs:element name="ContainingRecord">  
    <xs:complexType>  
        <xs:sequence>  
            <xs:element name="ExistingFieldElement" type="xs:string" />  
        </xs:sequence>  
    </xs:complexType>  
</xs:element>  
  
```  
  
 既定では、**選択肢**要素が指定された、 **minOccurs**属性ゼロ (0)、オプションがない、発生する必要があることを示す値を指定します。 Visual Studio プロパティ ウィンドウでこの値を変更することができる場合、**グループの選択**スキーマ ツリー ビューでノードを選択します。  
  
 次の例は、同じ**選択肢**XSD を持つ要素**要素**2 つの下位に対応する要素**レコード**ノード。  
  
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
  
 この例では、2 つの兄弟で**レコード**ノードは、インスタンス メッセージは、米国の住所情報を持つレコード、またはその国際的な住所情報を持つレコードにあるか、ファクトの記述に使用します。 さらに、 **minOccurs**と**maxOccurs**のプロパティ、**選択肢グループ**ノード両方設定されている (1) 1 つに、Visual Studio プロパティ ウィンドウで、その結果、 *minOccurs*と*maxOccurs*の属性、**選択肢**XSD 表記で 1 つ (1) に設定されている要素です。  
  
## <a name="see-also"></a>参照  
-  [スキーマの BizTalk 表記](../core/biztalk-representation-of-schemas.md)   
-  [ノードのプロパティ](../core/node-properties.md)   
-  **シーケンス グループ ノードのプロパティ**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]     
-  [ノードのプロパティを設定する方法](../core/how-to-set-node-properties.md)