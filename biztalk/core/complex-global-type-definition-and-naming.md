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
# <a name="complex-global-type-definition-and-naming"></a><span data-ttu-id="282d0-102">複合グローバル型の定義と名前付け</span><span class="sxs-lookup"><span data-stu-id="282d0-102">Complex Global Type Definition and Naming</span></span>
<span data-ttu-id="282d0-103">BizTalk エディターで複合グローバル型を定義する場合、グローバル型を使用する場所のいずれかで最初に出現する複合型を定義してから、これをグローバル型に変換します。</span><span class="sxs-lookup"><span data-stu-id="282d0-103">Within BizTalk Editor, you begin to define a complex global type by defining the first occurrence of the complex type in one of the locations where the global type will be used, after it has been converted to a global type.</span></span> <span data-ttu-id="282d0-104">たとえば住所の場合、スキーマ内の発送先住所を定義するときは、複合型の住所を定義します。</span><span class="sxs-lookup"><span data-stu-id="282d0-104">Continuing with the address example, you might define the complex address type in the course of defining a shipping address within the schema.</span></span>  
  
 <span data-ttu-id="282d0-105">複合型を定義してから、型名を付けて、これを複合グローバル型に変換できます。</span><span class="sxs-lookup"><span data-stu-id="282d0-105">After the complex type is defined, you can convert it to a global complex type by giving it a type name.</span></span> <span data-ttu-id="282d0-106">通常、複合型に対応するノードを選択してこれを行う、**レコード**ノードを展開し、新しい型名を入力することで、 **Data Structure Type**そのノードのプロパティです。</span><span class="sxs-lookup"><span data-stu-id="282d0-106">You do this by selecting the node that corresponds to the complex type, which will generally be a **Record** node, and then typing a new type name into the **Data Structure Type** property of that node.</span></span> <span data-ttu-id="282d0-107">表示されている変更は行われません、スキーマ ツリーでこのプロパティ名を指定するときに (など、 **GlobalAddrType**次の例のように、)、スキーマの基になる XSD 表記内での動作を確認する場合は、します。次の (省略形) の変更が表示されます。</span><span class="sxs-lookup"><span data-stu-id="282d0-107">Although no visible changes occur in the schema tree when you give this property a name (such as, **GlobalAddrType**, as in the following example), if you examine what happens within the underlying XSD representation of the schema, you would see the following (abbreviated) change.</span></span>  
  
 <span data-ttu-id="282d0-108">前に、アドレスの構造を持つ最初定義のコンテキスト内で、 **ShippingAddress**要素を次が発生しました。</span><span class="sxs-lookup"><span data-stu-id="282d0-108">Before, with the address structure first defined within the context of the **ShippingAddress** element, the following occurred.</span></span>  
  
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
  
 <span data-ttu-id="282d0-109">後に、 **ShippingAddress**ノードが指定されて一意の名前その**Data Structure Type**プロパティ、および内の複数の場所で再利用できる複合グローバル型として使用可能になるため、スキーマでは、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="282d0-109">After the **ShippingAddress** node has been given a unique name in its **Data Structure Type** property, causing it to become available as a complex global type and subject to reuse in multiple places within the schema, the following occurs.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="282d0-110">参照</span><span class="sxs-lookup"><span data-stu-id="282d0-110">See Also</span></span>  
 <span data-ttu-id="282d0-111">[型の再利用と派生](../core/type-reuse-and-derivations.md) </span><span class="sxs-lookup"><span data-stu-id="282d0-111">[Type Reuse and Derivations](../core/type-reuse-and-derivations.md) </span></span>  
 [<span data-ttu-id="282d0-112">別のノードまたは種類への参照を作成する方法</span><span class="sxs-lookup"><span data-stu-id="282d0-112">How to Create References to Another Node or Type</span></span>](../core/how-to-create-references-to-another-node-or-type.md)