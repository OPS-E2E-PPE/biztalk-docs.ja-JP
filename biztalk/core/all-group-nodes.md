---
title: ノードのすべてのグループ |Microsoft ドキュメント
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
ms.openlocfilehash: f51d6420b7d754ffb8706e2bc729a02df00b4338
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22230650"
---
# <a name="all-group-nodes"></a>[すべてのグループ] ノード
BizTalk エディターで、挿入できる、**すべてのグループ**を任意の順序で、0 個または 1 つの時間が表示される他のノードを含むノードです。 XML スキーマ定義 (XSD) 言語で、**すべてグループ**よりも使用上の制限を持つ**シーケンス**と**選択肢**グループ内のいくつかの状況に変換します。ここでことができますを作成する BizTalk エディター、**すべてのグループ**ノード。  
  
 使用する、**すべてのグループ**ノード BizTalk エディターで、追加の手順に従う必要があります: を作成する最も簡単な方法、**すべてのグループ**の値を変更するのには、ノード、 **Group Order Type**親のプロパティ**レコード**ノード**すべて**です。 これにより、すべての下位ノードの**レコード**ノードに含まれる、**すべてのグループ**ノード。  参照してください**Group Order Type** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。
  
 使用する別の方法、**すべてのグループ**BizTalk エディターでノードが新しい挿入で始まる**レコード**ノード。 新しく挿入した後に**レコード**ノード、変更、**コンテンツ タイプ**プロパティを**ComplexContent**です。 挿入することができ、**すべてのグループ**ノードの子として、**レコード**ノード。 これが必要な**すべてのグループ**継承が関係しているときにのみ挿入できます。 指定する格納している**レコード**ノードには、複雑なコンテンツが含まれています、そのデータ型は、データ型に基づくなります**xs:anyType**、拡張機能によって派生します。  
  
> [!NOTE]
>  BizTalk エディターで、**すべてのグループ**ノードは、文字列で表される\<すべて > スキーマ ツリー ビューでします。 参照を設定した場合、**すべてのグループ**ノードなど、x、として表されます\<グループ:x > スキーマ ツリー ビューでします。  
  
## <a name="xsd-representation"></a>XSD 表記  
 **すべてのグループ**にノードを挿入できる、**レコード**のみ場合は、属性なしの子ノードですが、ノード**レコード**ノード。 次の例を示していますの手順で、新しい方法**すべてのグループ**と XML スキーマ定義 (XSD) 言語で表されるノード、**すべて**(という名前のノードの要素として BizTalk エディターでの手順が実行されます明確にする、id)。  
  
```  
<xs:element name="NewRecord">  
    <xs:complexType />   
</xs:element>  
```  
  
 前の XSD フラグメントで示すように、新しいレコードを追加した後、**コンテンツ タイプ**にプロパティが変更された**ComplexContent**、その結果、次の XSD の変更にします。  
  
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
  
 最後に、新しい子として適切なノードを挿入できる**すべてのグループ**ノード。 次の例は、**レコード**ノードおよび**フィールド要素**の新しい子ノードとして挿入ノード**すべてのグループ**ノード。  
  
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
-  [スキーマの BizTalk 表記](../core/biztalk-representation-of-schemas.md)   
-  [ノードのプロパティ](../core/node-properties.md)   
-  **シーケンス グループ ノードのプロパティ**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)] 
-  [ノードのプロパティを設定する方法](../core/how-to-set-node-properties.md)