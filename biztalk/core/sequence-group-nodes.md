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
ms.openlocfilehash: e0a8343fe49f104cc00622e6489237fde48d0f7c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393343"
---
# <a name="sequence-group-nodes"></a>シーケンス グループ ノード

## <a name="overview"></a>概要
BizTalk エディターでは、挿入できる、**シーケンス グループ**をする必要があります内に表示される同じ順序で、インスタンス メッセージ内に表示される他のノードを含むノード、**シーケンス グループ**ノード。 含まれているノードは、XML 要素に対応するノードである必要がありますが、XML 属性に対応するノードをすることはできません。  

> [!NOTE]
>  BizTalk エディターで、**シーケンス グループ**ノードが既定では、文字列で表される\<シーケンス\>スキーマ ツリー ビューで。 参照を設定した場合、**シーケンス グループ**x などのノードとして表されます\<グループ: x\>スキーマ ツリー ビューで。  

 追加することも、**シーケンス グループ**グローバル要素グループを宣言します。  

 次のように、XML のスキーマを作成する必要があります。  

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

 GroupItem1 と GroupItem2 がどちらの場合も存在するため、Record1 と Record2 の子であるグローバル シーケンス グループを宣言することがあります。 グローバル シーケンス グループを宣言する方法の詳しい手順については、「[別のノードまたは種類への参照の作成](../core/how-to-create-references-to-another-node-or-type.md)です。  

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
