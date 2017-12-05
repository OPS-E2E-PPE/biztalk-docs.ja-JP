---
title: "シーケンス グループ ノード |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 139c3daa-a682-4bf7-bbb7-b5694ced0431
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b92c2165a84e5d539eac434ab140389c145b24b4
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="sequence-group-nodes"></a>[シーケンス グループ] ノード

## <a name="overview"></a>概要
BizTalk エディターで、挿入できる、**シーケンス グループ**を他のノードに、インスタンス メッセージ内で表示される同じ順序で表示することを含むノード、**シーケンス グループ**ノード。 取り込むノードは、XML 要素に対応するノードであることが必要です。ただし、XML 属性に対応するノードではありません。  
  
> [!NOTE]
>  BizTalk エディターで、**シーケンス グループ**ノードが既定では、文字列で表される\<シーケンス\>スキーマ ツリー ビューでします。 参照を設定した場合、**シーケンス グループ**x などのノードとして表されます\<グループ:x\>スキーマ ツリー ビューでします。  
  
 追加することも、**シーケンス グループ**グローバル要素グループを宣言します。  
  
 このような場合は、次の例に示す XML のスキーマを作成します。  
  
```  
<Root>  
    <Record1>  
        <GroupItem1/>  
        <GroupItem2/>  
        <NotAGroupItem>  
    </Record1>  
    <Record2>  
        <GroupItem1/>  
        <GroupItem2/>  
    </Record2>  
</Root>  
  
```  
  
 GroupItem1 と GroupItem2 は両方の場合に存在するので、Record1 および Record2 の両方の子であるグローバル シーケンス グループを宣言することができます。 グローバル シーケンス グループを宣言する方法の詳細な手順については、次を参照してください。[別のノードまたは種類への参照の作成](../core/how-to-create-references-to-another-node-or-type.md)です。  
  
 ユーザー グループを非表示を変更することができます、**選択肢グループ**ノードまたは**すべてのグループ**ノード (とは限りませんように、**シーケンス グループ**ノード) を変更して、 **Group Order Type**プロパティです。 このプロパティの詳細について[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。
  
## <a name="xsd-representation"></a>XSD 表記  
 ときに、**シーケンス グループ**ノードが挿入、**レコード**ノード内の他の子ノードの最後に挿入されます、**シーケンス**、**選択肢**、または**すべて**内の要素、**レコード**ノード。 次の例は、新しい**シーケンス グループ**ノードにある太字の末尾に挿入で、**シーケンス**内の要素、**レコード**ノード (ノードを明確にすると、id) です。  
  
```  
<xs:element name="ContainingRecord">  
    <xs:complexType>  
        <xs:sequence>  
            <xs:element name="ExistingFieldElement" type="xs:string" />  
        </xs:sequence>  
    </xs:complexType>  
</xs:element>  
  
```  
  
## <a name="see-also"></a>参照  
-  [スキーマの BizTalk 表記](../core/biztalk-representation-of-schemas.md)   
-  [ノードのプロパティ](../core/node-properties.md)   
-  **シーケンス グループ ノードのプロパティ**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
-  [ノードのプロパティを設定する方法](../core/how-to-set-node-properties.md)