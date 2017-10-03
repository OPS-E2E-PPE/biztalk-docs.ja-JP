---
title: "複合グローバル型の定義と名前付け |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b5a12956-7b77-4be8-b323-38363d04fcbc
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: afe00c68f22dde956279f2dd5ac06d03bf9cb84d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="complex-global-type-definition-and-naming"></a>複合グローバル型の定義と名前付け
BizTalk エディターで複合グローバル型を定義する場合、グローバル型を使用する場所のいずれかで最初に出現する複合型を定義してから、これをグローバル型に変換します。 たとえば住所の場合、スキーマ内の発送先住所を定義するときは、複合型の住所を定義します。  
  
 複合型を定義してから、型名を付けて、これを複合グローバル型に変換できます。 通常、複合型に対応するノードを選択してこれを行う、**レコード**ノードを展開し、新しい型名を入力することで、 **Data Structure Type**そのノードのプロパティです。 表示されている変更は行われません、スキーマ ツリーでこのプロパティ名を指定するときに (など、 **GlobalAddrType**次の例のように、)、スキーマの基になる XSD 表記内での動作を確認する場合は、します。次の (省略形) の変更が表示されます。  
  
 前に、アドレスの構造を持つ最初定義のコンテキスト内で、 **ShippingAddress**要素を次が発生しました。  
  
```  
<xs:schema>  
  <xs:element name="Root">  
    <xs:complexType>  
      <xs:sequence>  
        <xs:element name="ShippingAddress">  
        [address structure initially defined here.]  
        </xs:element>  
      </xs:sequence>  
    </xs:complexType>  
  </xs:element>  
</xs:schema>  
```  
  
 後に、 **ShippingAddress**ノードが指定されて一意の名前その**Data Structure Type**プロパティ、および内の複数の場所で再利用できる複合グローバル型として使用可能になるため、スキーマでは、次のようにします。  
  
```  
<xs:schema>  
  <xs:element name="Root">  
    <xs:complexType>  
      <xs:sequence>  
        <xs:element name="ShippingAddress" type="GlobalAddrType" />  
      </xs:sequence>  
    </xs:complexType>  
  </xs:element>  
  <xs:complexType name="GlobalAddrType">  
  [address structure now defined globally here.]  
  </xs:complexType>  
</xs:schema>  
```  
  
## <a name="see-also"></a>参照  
 [型の再利用と派生](../core/type-reuse-and-derivations.md)   
 [別のノードまたは種類への参照を作成する方法](../core/how-to-create-references-to-another-node-or-type.md)