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
# <a name="complex-global-type-definition-and-naming"></a><span data-ttu-id="ce01d-102">複合グローバル型の定義と名前付け</span><span class="sxs-lookup"><span data-stu-id="ce01d-102">Complex Global Type Definition and Naming</span></span>
<span data-ttu-id="ce01d-103">グローバル型が使用できる場所がグローバル型に変換された後に場所のいずれかで最初に出現する複合型を定義することで、複合グローバル型を定義する開始するための BizTalk エディター内で。</span><span class="sxs-lookup"><span data-stu-id="ce01d-103">Within BizTalk Editor, you begin to define a complex global type by defining the first occurrence of the complex type in one of the locations where the global type will be used, after it has been converted to a global type.</span></span> <span data-ttu-id="ce01d-104">アドレスの例を続行すると、スキーマ内で出荷先住所を定義するとき、複雑なアドレスの種類を定義する場合があります。</span><span class="sxs-lookup"><span data-stu-id="ce01d-104">Continuing with the address example, you might define the complex address type in the course of defining a shipping address within the schema.</span></span>  
  
 <span data-ttu-id="ce01d-105">複合型を定義した後、型名を指定することによって変換グローバル複合型にできます。</span><span class="sxs-lookup"><span data-stu-id="ce01d-105">After the complex type is defined, you can convert it to a global complex type by giving it a type name.</span></span> <span data-ttu-id="ce01d-106">一般に、複合型に対応するノードを選択してこれを行う、**レコード**ノード、およびに新しい型名を入力し、 **Data Structure Type**そのノードのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="ce01d-106">You do this by selecting the node that corresponds to the complex type, which will generally be a **Record** node, and then typing a new type name into the **Data Structure Type** property of that node.</span></span> <span data-ttu-id="ce01d-107">表示されている変更が発生しないスキーマ ツリーでこのプロパティに名前を付けるときは (次のように、 **GlobalAddrType**次の例のように、)、スキーマの基になる XSD 表記内での動作を確認する場合は、します。(省略形)、次の変更が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ce01d-107">Although no visible changes occur in the schema tree when you give this property a name (such as, **GlobalAddrType**, as in the following example), if you examine what happens within the underlying XSD representation of the schema, you would see the following (abbreviated) change.</span></span>  
  
 <span data-ttu-id="ce01d-108">前に、アドレス構造をまず定義のコンテキスト内で、 **ShippingAddress**要素では、次が発生しました。</span><span class="sxs-lookup"><span data-stu-id="ce01d-108">Before, with the address structure first defined within the context of the **ShippingAddress** element, the following occurred.</span></span>  
  
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
  
 <span data-ttu-id="ce01d-109">後に、 **ShippingAddress**ノードが指定されて一意の名前その**Data Structure Type**に内で複数の場所で再利用する対象となる複合グローバル型として使用可能になる原因となる、プロパティ、スキーマを次に発生します。</span><span class="sxs-lookup"><span data-stu-id="ce01d-109">After the **ShippingAddress** node has been given a unique name in its **Data Structure Type** property, causing it to become available as a complex global type and subject to reuse in multiple places within the schema, the following occurs.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ce01d-110">参照</span><span class="sxs-lookup"><span data-stu-id="ce01d-110">See Also</span></span>  
 <span data-ttu-id="ce01d-111">[型の再利用と派生](../core/type-reuse-and-derivations.md) </span><span class="sxs-lookup"><span data-stu-id="ce01d-111">[Type Reuse and Derivations](../core/type-reuse-and-derivations.md) </span></span>  
 [<span data-ttu-id="ce01d-112">別のノードまたは種類への参照を作成する方法</span><span class="sxs-lookup"><span data-stu-id="ce01d-112">How to Create References to Another Node or Type</span></span>](../core/how-to-create-references-to-another-node-or-type.md)