---
title: シーケンス グループ ノード |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 139c3daa-a682-4bf7-bbb7-b5694ced0431
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c113d0cfd0f6055d55b0329bba3c1ec60bf835e8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37019744"
---
# <a name="sequence-group-nodes"></a>[シーケンス グループ] ノード

## <a name="overview"></a>概要
BizTalk エディターでは、挿入できる、**シーケンス グループ**をする必要があります内に表示される同じ順序で、インスタンス メッセージ内に表示される他のノードを含むノード、**シーケンス グループ**ノード。 取り込むノードは、XML 要素に対応するノードであることが必要です。ただし、XML 属性に対応するノードではありません。  

> [!NOTE]
>  BizTalk エディターで、**シーケンス グループ**ノードが既定では、文字列で表される\<シーケンス\>スキーマ ツリー ビューで。 参照を設定した場合、**シーケンス グループ**x などのノードとして表されます\<グループ: x\>スキーマ ツリー ビューで。  

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

 GroupItem1 と GroupItem2 は両方の場合に存在するので、Record1 および Record2 の両方の子であるグローバル シーケンス グループを宣言することができます。 グローバル シーケンス グループを宣言する方法の詳しい手順については、「[別のノードまたは種類への参照の作成](../core/how-to-create-references-to-another-node-or-type.md)です。  

 ユーザー グループを非表示を変更できる、**グループの選択**ノードまたは**すべてのグループ**ノード (とは限りませんため、**シーケンス グループ**ノード) を変更して、 **Group Order Type**プロパティ。 このプロパティについて詳しく[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。

## <a name="xsd-representation"></a>XSD 表記  
 ときに、**シーケンス グループ**ノードが挿入、**レコード**ノード内の他の子ノードの最後に挿入されます、**シーケンス**、 **の選択**、または**すべて**内の要素、**レコード**ノード。 次の例は、新しい**シーケンス グループ**太字の末尾に挿入でのノード、**シーケンス**内の要素を**レコード**ノード (ノードを明確にすると、id) です。  

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
- [スキーマの BizTalk 表記](../core/biztalk-representation-of-schemas.md)   
- [ノードのプロパティ](../core/node-properties.md)   
- **シーケンス グループ ノードのプロパティ** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
- [ノードのプロパティを設定する方法](../core/how-to-set-node-properties.md)
