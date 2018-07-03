---
title: ノードのすべてのグループ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0e28d98c-746a-44d8-bed2-ba539b8432aa
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 084b12f16e72507a7d5568bdee022925eca52c0e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989235"
---
# <a name="all-group-nodes"></a>[すべてのグループ] ノード
BizTalk エディターでは、挿入できる、**すべてのグループ**を任意の順序で、0 個または 1 時間に表示される他のノードを含むノードです。 XML スキーマ定義 (XSD) 言語で、**すべてグループ**よりも使用上の制限が**シーケンス**と**選択肢**グループで、内のいくつかの状況に変換します作成することをするは、BizTalk エディター、**すべてのグループ**ノード。  

 使用する、**すべてのグループ**ノード BizTalk エディターで、いくつか追加の手順に従う必要があります: を作成する最も簡単な方法、**すべてのグループ**ノードがの値を変更するには、 **Group Order Type**親のプロパティ**レコード**ノード**すべて**します。 これにより、すべての下位ノードの**レコード**内に含まれるノード、**すべてのグループ**ノード。  参照してください**Group Order Type** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。

 使用する別の方法、**すべてのグループ**BizTalk エディターでノードが新しい挿入で始まる**レコード**ノード。 新しく挿入した後に**レコード**ノードで、変更、**コンテンツの種類**プロパティを**ComplexContent**します。 挿入することができ、**すべてのグループ**ノードの子として、**レコード**ノード。 これは、必要なため、**すべてのグループ**継承が関係する場合にのみ挿入できます。 指定することで、格納している**レコード**ノードは、複雑なコンテンツを含む、データ型に基づいてそのデータ型になります**xs:anyType**、拡張機能によって派生します。  

> [!NOTE]
>  BizTalk エディターで、**すべてのグループ**ノードが文字列で表される\<すべて > スキーマ ツリー ビューで。 参照を設定した場合、**すべてのグループ**ノードなど、x として表されます\<グループ: x > スキーマ ツリー ビューで。  

## <a name="xsd-representation"></a>XSD 表記  
 **すべてのグループ**にノードを挿入できる、**レコード**のみ場合はその属性なしの子ノードが、ノード**レコード**ノード。 次の例を示していますの手順では、新しい**すべてのグループ**と XML スキーマ定義 (XSD) 言語で表されるノード、**すべて**要素を BizTalk エディターでの手順としては、(という名前のノードで実行されます明確にする id)。  

```  
<xs:element name="NewRecord">  
    <xs:complexType />   
</xs:element>  
```  

 前の XSD フラグメントで示すように、新しいレコードを追加した後、**コンテンツの種類**にプロパティが変更された**ComplexContent**、次の XSD の変更の結果として得られる。  

```  
<xs:element name="NewRecord">  
    <xs:complexType>  
        <xs:complexContent mixed="false">  
             <xs:extension base="xs:anyType" />  
        </xs:complexContent>  
    </xs:complexType>  
</xs:element>  
```  

 これで、**すべてのグループ**ノードは、次の XSD フラグメントで示すように、新しいレコードの子として挿入できます。  

```  
<xs:element name="NewRecord">  
    <xs:complexType>  
        <xs:complexContent mixed="false">  
            <xs:extension base="xs:anyType">  
                <xs:all />   
             </xs:extension>  
          </xs:complexContent>  
     </xs:complexType>  
</xs:element>  
```  

 最後に、新しい子として適切なノードを挿入できます**すべてのグループ**ノード。 次の例は、**レコード**ノードと**フィールド要素**ノードの新しい子ノードとして挿入**すべてのグループ**ノード。  

```  
<xs:element name="NewRecord">  
    <xs:complexType>  
        <xs:complexContent mixed="false">  
            <xs:extension base="xs:anyType">  
                <xs:all>  
                    <xs:element name="RecordChildOfAllGroup">  
                        <xs:complexType />  
                    </xs:element>  
                    <xs:element name="FieldElementChildOfAllGroup" type="xs:string" />  
                </xs:all>  
            </xs:extension>  
        </xs:complexContent>  
    </xs:complexType>  
</xs:element>  
```  

## <a name="see-also"></a>参照  
- [スキーマの BizTalk 表記](../core/biztalk-representation-of-schemas.md)   
- [ノードのプロパティ](../core/node-properties.md)   
- **シーケンス グループ ノードのプロパティ** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)] 
- [ノードのプロパティを設定する方法](../core/how-to-set-node-properties.md)
