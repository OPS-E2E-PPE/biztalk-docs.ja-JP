---
title: すべての要素ノード |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c7e30fcf-31bc-4d48-9bc7-0be90e927127
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 905d6c25c5c2021840f4257c29df015d4bcb374e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37002435"
---
# <a name="any-element-nodes"></a>すべての要素ノード
使用できる BizTalk エディターで、 **Any 要素**ノードが、不明な要素が表示されるインスタンス メッセージ内の場所を示すことです。 これにより、特定の要素がインスタンス メッセージ内の特定の場所に出現することはあらかじめわかっているが、要素の名前や複雑さの程度が不確定な状況にも対応できます。 配置した場合、 **Any 要素**ノードのスキーマでは、BizTalk 内で適切な位置には、メッセージのような未知の部分を処理できます。 唯一の要件は、対応する XML が整形式であることです。  
  
> [!NOTE]
>  BizTalk エディターで、**すべての要素**ノードが文字列で表される\<任意\>スキーマ ツリー ビューで。  
> 
> [!NOTE]
>  整形式 XML として、メッセージの未知の部分を検証を使用して程度を制御することができます、 **Process Contents**プロパティ。 多くの場合は、設定する必要があります、 **Process Contents**プロパティを**スキップ**の位置にあるインスタンス メッセージの内容として、 **Any 要素**処理するノード。 既定値を保持**Strict**の**Process Contents**プロパティがインスタンス メッセージの検証の成功を防ぐためです。  
> 
> このプロパティについて詳しく[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。
  
## <a name="xsd-representation"></a>XSD 表記  
 ときに、 **Any 要素**にノードを追加、**レコード**ノード、または別のノードを追加するように、**シーケンス グループ**、 **グループの選択**、または**すべてのグループ**ノード、1 つの XML タグが、対応する XML スキーマ定義 (XSD) 言語表記のスキーマに追加します。 次の例では、新しい**Any 要素**を既存の XSD 表記が太字で表示されているノードが追加されました**レコード**既に含まれているノード、**フィールド要素**ノード。  
  
```  
<xs:element name="ExistingRecord">  
    <xs:complexType>  
        <xs:sequence>  
             <xs:element name="ExistingFieldElement" type="xs:string" />  
            <xs:any />  
        </xs:sequence>  
    </xs:complexType>  
</xs:element>  
```  
  
 仮定すると、 **Process Contents**のプロパティ、 **Any 要素**にノードが設定されている**スキップ**内でこのスキーマのフラグメントをによって管理されるインスタンスメッセージ**ExistingRecord**要素が格納する必要があります、 **ExistingFieldElement**任意の複雑さの任意の 1 つの要素の後に、文字列データを含む要素。  
  
## <a name="see-also"></a>参照  
 [スキーマの BizTalk 表記](../core/biztalk-representation-of-schemas.md)   
 [ノードのプロパティ](../core/node-properties.md)   
 [ノードのプロパティを設定する方法](../core/how-to-set-node-properties.md)   
 [[すべての属性] ノード](../core/any-attribute-nodes.md)