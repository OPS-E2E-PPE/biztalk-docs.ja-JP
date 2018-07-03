---
title: 拡張機能のメカニズムを使用して複合型の派生 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7125fb5b-f77a-47c9-8000-f2332940df89
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2addaf540407c7b899cc81a7512fead9bb205ad5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37022232"
---
# <a name="complex-type-derivation-using-the-extension-mechanism"></a><span data-ttu-id="5f60a-102">拡張メカニズムを使用した複合型の派生</span><span class="sxs-lookup"><span data-stu-id="5f60a-102">Complex Type Derivation Using the Extension Mechanism</span></span>
<span data-ttu-id="5f60a-103">拡張機能によって派生する複合型は、基本データ型の機能的なスーパーセットです。</span><span class="sxs-lookup"><span data-stu-id="5f60a-103">A complex type derived by extension is a functional superset of its base data type.</span></span> <span data-ttu-id="5f60a-104">名前が示すように、基本データ型に基づいて、拡張する型を定義します。</span><span class="sxs-lookup"><span data-stu-id="5f60a-104">As the name implies, its base data type is the basis for the type being defined, where the differences from the base type are additive.</span></span> <span data-ttu-id="5f60a-105">このトピックでは、2 つの要素**ShippingAddress**と**BillingAddress**複合グローバル型に基づきます**GlobalAddrType**します。</span><span class="sxs-lookup"><span data-stu-id="5f60a-105">This topic provides an example in which the two elements **ShippingAddress** and **BillingAddress** are based on the complex global type **GlobalAddrType**.</span></span> <span data-ttu-id="5f60a-106">**ShippingAddress**に型の定義は**GlobalAddrType**であるのに対し**BillingAddress**型を拡張するように定義**GlobalAddrType**します。</span><span class="sxs-lookup"><span data-stu-id="5f60a-106">**ShippingAddress** is simply defined to be of type **GlobalAddrType**, whereas **BillingAddress** is defined to extend the type **GlobalAddrType**.</span></span> <span data-ttu-id="5f60a-107">別の要素を追加の例では、最後に、 **BillingAddress**、名前付き**部門**文字列型および Accounts Payable の既定値を指定しています。</span><span class="sxs-lookup"><span data-stu-id="5f60a-107">At the end of the example, an additional element is added to **BillingAddress**, named **Department**, with a type of string and a default value of Accounts Payable.</span></span>  
  
 <span data-ttu-id="5f60a-108">拡張メカニズムを使用して新規の複合型を派生させる情報の概要については、W3C Web サイトを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5f60a-108">For comprehensive information about deriving new complex types by using the extension mechanism, refer to the W3C website.</span></span> <span data-ttu-id="5f60a-109">これと他の web サイトへのさまざまなリンクは、次を参照してください。 [Web 上の XSD リソース](../core/xsd-resources-on-the-web.md)します。</span><span class="sxs-lookup"><span data-stu-id="5f60a-109">For various links to this and other websites, see [XSD Resources on the Web](../core/xsd-resources-on-the-web.md).</span></span>  
  
 <span data-ttu-id="5f60a-110">スキーマ ツリーの別の場所での拡張機能によって複合グローバル型から派生する新しい挿入することで開始**レコード**目的の場所にあるノード。</span><span class="sxs-lookup"><span data-stu-id="5f60a-110">To derive from a complex global type by extension, in another location in the schema tree, begin by inserting a new **Record** node at the desired location.</span></span> <span data-ttu-id="5f60a-111">設定し、その**Base Data Type**プロパティを複合グローバル型の名前にします。</span><span class="sxs-lookup"><span data-stu-id="5f60a-111">Then set its **Base Data Type** property to the name of a complex global type.</span></span>  
  
 <span data-ttu-id="5f60a-112">次の例では、 **BillingAddress**新しく挿入の名前を指定**レコード**ノード、および**GlobalAddrType**元である場合は、複合グローバル型の名前を指定します派生元および拡張します。</span><span class="sxs-lookup"><span data-stu-id="5f60a-112">In the following example, **BillingAddress** is the name of the newly inserted **Record** node, and **GlobalAddrType** is the name of the complex global type from which it derives, and intends to extend.</span></span> <span data-ttu-id="5f60a-113">スキーマ ツリー ビューで後**Base Data Type**に設定されている**GlobalAddrType**、重複するノード構造がという名前のノードの下に表示**BillingAddress**、という名前のノードの下の隣接するノード構造と同じ**ShippingAddress**します。</span><span class="sxs-lookup"><span data-stu-id="5f60a-113">In the schema tree view, after **Base Data Type** has been set to **GlobalAddrType**, a duplicate node structure would be displayed below the node named **BillingAddress**, identical to the adjacent node structure under the node named **ShippingAddress**.</span></span> <span data-ttu-id="5f60a-114">これらの相違点は、 **BillingAddress**されるノードの構造は基本データ型よりも拡張可能な**GlobalAddrType**、および**ShippingAddress**構造体を基本データ型と同じままになります**GlobalAddrType**します。</span><span class="sxs-lookup"><span data-stu-id="5f60a-114">The difference between them is that the **BillingAddress** node structure will be extensible beyond the base data type **GlobalAddrType**, and the **ShippingAddress** structure will remain identical to the base data type **GlobalAddrType**.</span></span>  
  
- <span data-ttu-id="5f60a-115">前に、新しく挿入されたノードを持つという**BillingAddress**します。</span><span class="sxs-lookup"><span data-stu-id="5f60a-115">Before, with a newly inserted node named **BillingAddress**.</span></span>  
  
  ```  
  <xs:schema>  
      <xs:element name="Root">  
          <xs:complexType>  
              <xs:sequence>  
                  <xs:element name="ShippingAddress" type="GlobalAddrType" />  
                  <xs:element name="BillingAddress">  
                      <xs:sequence />  
                  </xs:element>  
              </xs:sequence>  
          </xs:complexType>  
      </xs:element>  
      <xs:complexType name="GlobalAddrType">  
      [Address structure defined globally here.]  
      </xs:complexType>  
  </xs:schema>  
  ```  
  
- <span data-ttu-id="5f60a-116">複合基本型から派生させた後**GlobalAddrType**、拡張機能で。</span><span class="sxs-lookup"><span data-stu-id="5f60a-116">After deriving from the complex base type **GlobalAddrType**, by extension.</span></span>  
  
  ```  
  <xs:schema>  
      <xs:element name="Root">  
          <xs:complexType>  
              <xs:sequence>  
                  <xs:element name="ShippingAddress" type="GlobalAddrType" />  
                  <xs:element name="BillingAddress">  
                      <xs:complexType>  
                          <xs:complexContent mixed="false">  
                              <xs:extension base="GlobalAddrType" />  
                          </xs:complexContent>  
                      </xs:complexType>  
                  </xs:element>  
              </xs:sequence>  
          </xs:complexType>  
      </xs:element>  
      <xs:complexType name="GlobalAddrType">  
      [Address structure defined globally here.]   
      </xs:complexType>  
  </xs:schema>  
  ```  
  
  <span data-ttu-id="5f60a-117">ノードを挿入して拡張機能を基本データ型を指定する、 **BillingAddress**スキーマ ツリー内のノード。</span><span class="sxs-lookup"><span data-stu-id="5f60a-117">You specify extensions to the base data type by inserting nodes into the **BillingAddress** node in the schema tree.</span></span> <span data-ttu-id="5f60a-118">次の XSD フラグメントは、ときに空の拡張機能の要素が展開された方法を示しています、**シーケンス グループ**の新しい子ノードを挿入、 **BillingAddress**ノードをクリックし、**フィールド要素**という名前のノード**PaymentType**の子ノードとして挿入されます、**シーケンス グループ**ノード。</span><span class="sxs-lookup"><span data-stu-id="5f60a-118">The following XSD fragment shows how the empty extension element is expanded when a **Sequence Group** node is inserted as a new child of the **BillingAddress** node and then a **Field Element** node, named **PaymentType**, is inserted as a child node of the **Sequence Group** node.</span></span>  
  
```  
<xs:extension base="GlobalAddrType">  
    <xs:sequence>  
        <xs:element default="Accounts Payable"  
            name="Department" type="xs:string" />  
    </xs:sequence>  
</xs:extension>  
```  
  
## <a name="see-also"></a><span data-ttu-id="5f60a-119">参照</span><span class="sxs-lookup"><span data-stu-id="5f60a-119">See Also</span></span>  
 [<span data-ttu-id="5f60a-120">複合グローバル型の派生</span><span class="sxs-lookup"><span data-stu-id="5f60a-120">Complex Global Type Derivation</span></span>](../core/complex-global-type-derivation.md)