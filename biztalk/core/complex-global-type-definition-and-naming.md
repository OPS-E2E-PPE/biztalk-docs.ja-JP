---
title: 複合グローバル型の定義と名前付け |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b5a12956-7b77-4be8-b323-38363d04fcbc
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ead0eac56b44a5fe4c6488800717e76cb09a4615
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65356834"
---
# <a name="complex-global-type-definition-and-naming"></a>複合グローバル型の定義と名前付け
グローバル型が使用できる場所がグローバル型に変換された後に場所のいずれかで最初に出現する複合型を定義することで、複合グローバル型を定義する開始するための BizTalk エディター内で。 アドレスの例を続行すると、スキーマ内で出荷先住所を定義するとき、複雑なアドレスの種類を定義する場合があります。  
  
 複合型を定義した後、型名を指定することによって変換グローバル複合型にできます。 一般に、複合型に対応するノードを選択してこれを行う、**レコード**ノード、およびに新しい型名を入力し、 **Data Structure Type**そのノードのプロパティ。 表示されている変更が発生しないスキーマ ツリーでこのプロパティに名前を付けるときは (次のように、 **GlobalAddrType**次の例のように、)、スキーマの基になる XSD 表記内での動作を確認する場合は、します。(省略形)、次の変更が表示されます。  
  
 前に、アドレス構造をまず定義のコンテキスト内で、 **ShippingAddress**要素では、次が発生しました。  
  
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
  
 後に、 **ShippingAddress**ノードが指定されて一意の名前その**Data Structure Type**に内で複数の場所で再利用する対象となる複合グローバル型として使用可能になる原因となる、プロパティ、スキーマを次に発生します。  
  
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