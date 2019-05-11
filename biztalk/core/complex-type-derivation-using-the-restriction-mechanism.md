---
title: 制約メカニズムを使用して複合型の派生 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c3003d88-6b75-4dcb-834f-1babcf7449cb
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a9b1b4234f4bb39da70f1e59719e1f145440a0b6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65356806"
---
# <a name="complex-type-derivation-using-the-restriction-mechanism"></a><span data-ttu-id="b3580-102">制約メカニズムを使用して複合型の派生</span><span class="sxs-lookup"><span data-stu-id="b3580-102">Complex Type Derivation Using the Restriction Mechanism</span></span>
<span data-ttu-id="b3580-103">制限による派生は、BizTalk エディターの機能では、拡張による派生と似ています。</span><span class="sxs-lookup"><span data-stu-id="b3580-103">Derivation by restriction is similar to derivation by extension, in terms of BizTalk Editor functionality.</span></span> <span data-ttu-id="b3580-104">制限による派生複合型は、基本データ型に似ていますが、その宣言は、基本データ型の宣言よりも制限。</span><span class="sxs-lookup"><span data-stu-id="b3580-104">A complex type derived by restriction is similar to its base data type, except that its declarations are more limited than the corresponding declarations in the base data type.</span></span> <span data-ttu-id="b3580-105">実際には、新しい型で表される値は、(単純型の制約の場合と同様)、基本データ型によって表される値のサブセットです。</span><span class="sxs-lookup"><span data-stu-id="b3580-105">In fact, the values represented by the new type are a subset of the values represented by the base data type (as is the case with restriction of simple types).</span></span> <span data-ttu-id="b3580-106">基本データ型の値として作成されるアプリケーションは、制限付きの型の値のいずれかを正常に処理できるはずです。</span><span class="sxs-lookup"><span data-stu-id="b3580-106">An application prepared for the values of the base data type ought to be able to successfully process any of the values of the restricted type.</span></span>  
  
 <span data-ttu-id="b3580-107">制約メカニズムを使用して、新しい複合型の派生について包括的な情報は、W3C web サイトを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b3580-107">For comprehensive information about deriving new complex types by using the restriction mechanism, refer to the W3C website.</span></span> <span data-ttu-id="b3580-108">これと他の web サイトへのさまざまなリンクは、次を参照してください。 [Web 上の XSD リソース](../core/xsd-resources-on-the-web.md)します。</span><span class="sxs-lookup"><span data-stu-id="b3580-108">For various links to this and other websites, see [XSD Resources on the Web](../core/xsd-resources-on-the-web.md).</span></span>  
  
 <span data-ttu-id="b3580-109">スキーマ ツリーの別の場所の制約機能によって複合グローバル型から派生する新しいを挿入することから始めます**レコード**目的の場所にあるノード。</span><span class="sxs-lookup"><span data-stu-id="b3580-109">To derive from a complex global type by restriction, in another location in the schema tree, begin by inserting a new **Record** node at the desired location.</span></span> <span data-ttu-id="b3580-110">設定し、その**Base Data Type**プロパティを複合グローバル型の名前にします。</span><span class="sxs-lookup"><span data-stu-id="b3580-110">Then set its **Base Data Type** property to the name of a complex global type.</span></span> <span data-ttu-id="b3580-111">設定が最後に、変更、 **Derived By**プロパティの既定値から**拡張子**(少なくとも基本データ型を設定されている場合) に**制限**します。</span><span class="sxs-lookup"><span data-stu-id="b3580-111">Finally, change the setting of the **Derived By** property from its default value of **Extension** (at least when a base data type is set) to **Restriction**.</span></span>  
  
 <span data-ttu-id="b3580-112">次の例では、 **BillingAddress**新しく挿入の名前を指定**レコード**ノード、および**GlobalAddrType**元である場合は、複合グローバル型の名前を指定します派生元および制限します。</span><span class="sxs-lookup"><span data-stu-id="b3580-112">In the following example, **BillingAddress** is the name of the newly inserted **Record** node, and **GlobalAddrType** is the name of the complex global type from which it derives, and intends to restrict.</span></span> <span data-ttu-id="b3580-113">という名前のノードの下で、スキーマ ツリー ビューでは、重複するノード構造が表示されます**BillingAddress**という名前のノードの下の隣接するノード構造と同じ、 **ShippingAddress**します。</span><span class="sxs-lookup"><span data-stu-id="b3580-113">In the schema tree view, a duplicate node structure would be displayed below the node named **BillingAddress**, identical to the adjacent node structure under the node named **ShippingAddress**.</span></span> <span data-ttu-id="b3580-114">これらの相違点は、 **BillingAddress**されるノードの構造は基本データ型に対する制約が**GlobalAddrType**、および**ShippingAddress**構造は常に同じ基本データ型に**GlobalAddrType**します。</span><span class="sxs-lookup"><span data-stu-id="b3580-114">The difference between them is that the **BillingAddress** node structure will be subject to possible restrictions to the base data type **GlobalAddrType**, and the **ShippingAddress** structure will remain identical to the base data type **GlobalAddrType**.</span></span>  
  
 <span data-ttu-id="b3580-115">基本データ型を制限することを選択してため、新しいノードを挿入することはできませんが、さらに、使用可能な値や動作を制限する既存のノードのプロパティを変更することができます。</span><span class="sxs-lookup"><span data-stu-id="b3580-115">Because you have chosen to restrict the base data type, you are not allowed to insert any new nodes, but you can change the properties of the existing nodes to further restrict their possible values or behavior.</span></span>  
  
-   <span data-ttu-id="b3580-116">前に、使用、 **Derived By**プロパティに設定**拡張子**。</span><span class="sxs-lookup"><span data-stu-id="b3580-116">Before, with the **Derived By** property still set to **Extension**.</span></span>  
  
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
  
-   <span data-ttu-id="b3580-117">切り替え後、 **Derived By**プロパティから**拡張子**に**制限**します。</span><span class="sxs-lookup"><span data-stu-id="b3580-117">After switching the **Derived By** property from **Extension** to **Restriction**.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b3580-118">参照</span><span class="sxs-lookup"><span data-stu-id="b3580-118">See Also</span></span>  
 [<span data-ttu-id="b3580-119">複合グローバル型の派生</span><span class="sxs-lookup"><span data-stu-id="b3580-119">Complex Global Type Derivation</span></span>](../core/complex-global-type-derivation.md)