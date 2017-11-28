---
title: "制約メカニズムを使用する複合型の派生 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c3003d88-6b75-4dcb-834f-1babcf7449cb
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ddbd9d8266d9c289b9b4bae9dd7060906e01ebd7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="complex-type-derivation-using-the-restriction-mechanism"></a><span data-ttu-id="6f34a-102">制約メカニズムを使用した複合型の派生</span><span class="sxs-lookup"><span data-stu-id="6f34a-102">Complex Type Derivation Using the Restriction Mechanism</span></span>
<span data-ttu-id="6f34a-103">制約による派生は、BizTalk エディターの機能では、拡張による派生と類似しています。</span><span class="sxs-lookup"><span data-stu-id="6f34a-103">Derivation by restriction is similar to derivation by extension, in terms of BizTalk Editor functionality.</span></span> <span data-ttu-id="6f34a-104">制約機能によって派生した複合型は、基本データ型と似ています。ただし、基本データ型の宣言よりも複合型の宣言の方が制限が多くあります。</span><span class="sxs-lookup"><span data-stu-id="6f34a-104">A complex type derived by restriction is similar to its base data type, except that its declarations are more limited than the corresponding declarations in the base data type.</span></span> <span data-ttu-id="6f34a-105">実際には、新しい型で表される値は、単純型の制約と同様に、基本データ型で表される値のサブセットです。</span><span class="sxs-lookup"><span data-stu-id="6f34a-105">In fact, the values represented by the new type are a subset of the values represented by the base data type (as is the case with restriction of simple types).</span></span> <span data-ttu-id="6f34a-106">基本データ型の値を対象として作成されるアプリケーションには、制限された型の任意の値を正常に処理する機能が必要になります。</span><span class="sxs-lookup"><span data-stu-id="6f34a-106">An application prepared for the values of the base data type ought to be able to successfully process any of the values of the restricted type.</span></span>  
  
 <span data-ttu-id="6f34a-107">制約メカニズムを使用して新規の複合型を派生する方法の概要については、W3C Web サイトを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6f34a-107">For comprehensive information about deriving new complex types by using the restriction mechanism, refer to the W3C website.</span></span> <span data-ttu-id="6f34a-108">これを他の web サイトのさまざまなリンクは、次を参照してください。 [Web 上の XSD リソース](../core/xsd-resources-on-the-web.md)です。</span><span class="sxs-lookup"><span data-stu-id="6f34a-108">For various links to this and other websites, see [XSD Resources on the Web](../core/xsd-resources-on-the-web.md).</span></span>  
  
 <span data-ttu-id="6f34a-109">スキーマ ツリーで、別の場所での制限によって複合グローバル型から派生する新しい挿入することによって開始**レコード**目的の場所にあるノード。</span><span class="sxs-lookup"><span data-stu-id="6f34a-109">To derive from a complex global type by restriction, in another location in the schema tree, begin by inserting a new **Record** node at the desired location.</span></span> <span data-ttu-id="6f34a-110">設定し、その**Base Data Type**プロパティ、複合グローバル型の名前にします。</span><span class="sxs-lookup"><span data-stu-id="6f34a-110">Then set its **Base Data Type** property to the name of a complex global type.</span></span> <span data-ttu-id="6f34a-111">最後の設定を変更、 **Derived By**プロパティの既定値から**拡張子**(少なくとも基本データ型設定されている場合) に**制限**です。</span><span class="sxs-lookup"><span data-stu-id="6f34a-111">Finally, change the setting of the **Derived By** property from its default value of **Extension** (at least when a base data type is set) to **Restriction**.</span></span>  
  
 <span data-ttu-id="6f34a-112">次の例では、 **BillingAddress**新しく挿入されるの名前を指定**レコード**ノード、および**GlobalAddrType**元である場合は、複合グローバル型の名前を指定します派生元およびを制限します。</span><span class="sxs-lookup"><span data-stu-id="6f34a-112">In the following example, **BillingAddress** is the name of the newly inserted **Record** node, and **GlobalAddrType** is the name of the complex global type from which it derives, and intends to restrict.</span></span> <span data-ttu-id="6f34a-113">名前付きノードの下に、スキーマ ツリー ビューで、重複するノード構造が表示されます**BillingAddress**、という名前のノードの下にある隣接するノード構造と同一**ShippingAddress**です。</span><span class="sxs-lookup"><span data-stu-id="6f34a-113">In the schema tree view, a duplicate node structure would be displayed below the node named **BillingAddress**, identical to the adjacent node structure under the node named **ShippingAddress**.</span></span> <span data-ttu-id="6f34a-114">これらの違いは、 **BillingAddress**されるノードの構造は基本データ型に対する制約が**GlobalAddrType**、および**ShippingAddress**構造は常に同じ基本データ型に**GlobalAddrType**です。</span><span class="sxs-lookup"><span data-stu-id="6f34a-114">The difference between them is that the **BillingAddress** node structure will be subject to possible restrictions to the base data type **GlobalAddrType**, and the **ShippingAddress** structure will remain identical to the base data type **GlobalAddrType**.</span></span>  
  
 <span data-ttu-id="6f34a-115">基本データ型を制限すると、新しいノードを挿入できません。ただし、既存のノードのプロパティを変更すると、指定できる値または動作をさらに制限できます。</span><span class="sxs-lookup"><span data-stu-id="6f34a-115">Because you have chosen to restrict the base data type, you are not allowed to insert any new nodes, but you can change the properties of the existing nodes to further restrict their possible values or behavior.</span></span>  
  
-   <span data-ttu-id="6f34a-116">前で、 **Derived By**にプロパティがまだ設定**拡張子**です。</span><span class="sxs-lookup"><span data-stu-id="6f34a-116">Before, with the **Derived By** property still set to **Extension**.</span></span>  
  
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
  
-   <span data-ttu-id="6f34a-117">切り替え後、 **Derived By**プロパティから**拡張子**に**制限**です。</span><span class="sxs-lookup"><span data-stu-id="6f34a-117">After switching the **Derived By** property from **Extension** to **Restriction**.</span></span>  
  
    ```  
    <xs:schema>  
        <xs:element name="Root">  
            <xs:complexType>  
                <xs:sequence>  
                    <xs:element name="ShippingAddress" type="GlobalAddrType" />  
                    <xs:element name="BillingAddress">  
                        <xs:complexType>  
                            <xs:complexContent mixed="false">  
                                <xs:restriction base="GlobalAddrType">  
                   [Duplicate of address structure now appears  
                   here, ready to be restricted with additional  
                   attributes, set using the properties of the  
                   relevant nodes in the schema tree.]  
                                </xs:restriction>  
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
  
## <a name="see-also"></a><span data-ttu-id="6f34a-118">参照</span><span class="sxs-lookup"><span data-stu-id="6f34a-118">See Also</span></span>  
 [<span data-ttu-id="6f34a-119">複合グローバル型の派生</span><span class="sxs-lookup"><span data-stu-id="6f34a-119">Complex Global Type Derivation</span></span>](../core/complex-global-type-derivation.md)