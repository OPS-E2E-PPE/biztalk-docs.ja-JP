---
title: フィールド要素 ノード |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 65b5e1f6-283f-4172-9bc2-f04a0ea6753d
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6c06a3f2fd55dc720fd0d37beaea49de76cbf101
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004227"
---
# <a name="field-element-nodes"></a><span data-ttu-id="7833b-102">[フィールド要素] ノード</span><span class="sxs-lookup"><span data-stu-id="7833b-102">Field Element Nodes</span></span>

## <a name="overview"></a><span data-ttu-id="7833b-103">概要</span><span class="sxs-lookup"><span data-stu-id="7833b-103">Overview</span></span>
<span data-ttu-id="7833b-104">BizTalk エディターを使用する**フィールド要素**ノードは、単純な文字列や数値などの情報項目を表すため。</span><span class="sxs-lookup"><span data-stu-id="7833b-104">In BizTalk Editor, you use **Field Element** nodes to describe items of information that are simple in nature, such as strings and numbers.</span></span> <span data-ttu-id="7833b-105">また、このノードは、目的の情報が XML 要素に関連付けられた属性の値としてではなく、実際のメッセージ インスタンスに XML 要素の内容として現れる場合に使用されます。</span><span class="sxs-lookup"><span data-stu-id="7833b-105">Further, they are used when the information in question appears as the content of an XML element in an actual instance of a message, as opposed to appearing as the value of an attribute associated with an XML element.</span></span> <span data-ttu-id="7833b-106">属性値として格納されている情報の詳細については、[フィールド属性 ノード](../core/field-attribute-nodes.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7833b-106">For additional information about information that is stored as attribute values, see [Field Attribute Nodes](../core/field-attribute-nodes.md).</span></span>  

> [!NOTE]
>  <span data-ttu-id="7833b-107">BizTalk エディターでは、要素と属性要素の両方で表現できる、**フィールド**ノードが、スキーマ ツリー ビューで、XSD ウィンドウにおける XML 表記で、それらに関連付けられている別のアイコン、およびVisual Studio のプロパティ ウィンドウでさまざまなプロパティ。</span><span class="sxs-lookup"><span data-stu-id="7833b-107">In BizTalk Editor, both the element and attribute elements can be represented by a **Field** node, although they have different icons associated with them in the schema tree view, a different XML representation in the XSD window, and different properties in the Visual Studio Properties window.</span></span>  

 <span data-ttu-id="7833b-108">XML メッセージに含まれる特定の情報項目 (ここでいう情報項目とは、文字列や数値など、1 つの独立した単純型のこと) では、その情報を要素の属性として表すべきか、要素のサブ要素として表すべきかという問題があります。</span><span class="sxs-lookup"><span data-stu-id="7833b-108">For any given item of information in an XML message, where item of information means a single discrete simple type, such as a string or number, there is always a question regarding whether that information should be represented as the attribute of an element, or as a subelement of that element.</span></span> <span data-ttu-id="7833b-109">一般に、格納される値が不連続であり、数が少なく、要素そのもののセマンティクスが変わりやすい場合は、情報項目を属性として表します。</span><span class="sxs-lookup"><span data-stu-id="7833b-109">As a general rule, representing an item of information as an attribute tends to be more appropriate when the possible values are discrete, few in number, and tend to modify the semantics of the element itself.</span></span> <span data-ttu-id="7833b-110">同じ値が繰り返し出現する場合、取りうる値の範囲が大きい場合、(文字列などが) 長くなってしまう場合、順序に関連性のある複数の兄弟値のいずれかが格納される場合などは、情報項目をサブ要素として表した方が適切な結果が得られる傾向があります。</span><span class="sxs-lookup"><span data-stu-id="7833b-110">Representing an item of information as a subelement tends to be more appropriate when the possible values can repeat a variable number of times, are likely to have more widely ranging values, might be long, as in long strings, and are one of several sibling values where their order is relevant.</span></span> <span data-ttu-id="7833b-111">既存の XML の種類のスキーマを作成するだけの場合を文書化を使用して選択した、**フィールド要素**ノードまたは**フィールド属性**特定の情報項目のノードは既に行われましたXML に一致するノードを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7833b-111">If you are just creating a schema for an existing type of XML document, your choice of using a **Field Element** node or a **Field Attribute** node for a particular item of information has already been made for you, and you must use the node that matches the XML.</span></span>  

## <a name="xsd-representation"></a><span data-ttu-id="7833b-112">XSD 表記</span><span class="sxs-lookup"><span data-stu-id="7833b-112">XSD representation</span></span>  
 <span data-ttu-id="7833b-113">ときに、**フィールド要素**ノードの挿入、**レコード**ノード内の他の子ノードの最後に挿入されます、**シーケンス**内の要素、 **レコード**ノード。</span><span class="sxs-lookup"><span data-stu-id="7833b-113">When a **Field Element** node is inserted into a **Record** node, it is inserted at the end of any other child nodes within the **sequence** element in the **Record** node.</span></span> <span data-ttu-id="7833b-114">次の例は、新しい**フィールド要素**太字内のノードの最後に挿入された、**シーケンス**内の要素を**レコード**(自分の id を明確にするという名前のノードを持つノード).</span><span class="sxs-lookup"><span data-stu-id="7833b-114">The following example shows a new **Field Element** node, in bold, inserted at the end of the **sequence** element in a **Record** node (with nodes named to clarify their identity).</span></span>  

```  
<xs:element name="ContainingRecord">  
    <xs:complexType>  
        <xs:sequence>  
            <xs:element name="ExistingFieldElement" type="xs:string" />  
            <xs:element name="EmptyNestedRecord">  
                <xs:complexType />  
            </xs:element>  

        </xs:sequence>  
        <xs:attribute name="ExistingFieldAttribute" type="xs:string" />  
    </xs:complexType>  
</xs:element>  

```  

## <a name="see-also"></a><span data-ttu-id="7833b-115">参照</span><span class="sxs-lookup"><span data-stu-id="7833b-115">See Also</span></span>  
- [<span data-ttu-id="7833b-116">スキーマの BizTalk 表記</span><span class="sxs-lookup"><span data-stu-id="7833b-116">BizTalk Representation of Schemas</span></span>](../core/biztalk-representation-of-schemas.md)   
- [<span data-ttu-id="7833b-117">ノードのプロパティ</span><span class="sxs-lookup"><span data-stu-id="7833b-117">Node Properties</span></span>](../core/node-properties.md)   
- <span data-ttu-id="7833b-118">**[フィールド要素] ノード プロパティ** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="7833b-118">**Field Element Node Properties** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
- [<span data-ttu-id="7833b-119">ノードのプロパティを設定する方法</span><span class="sxs-lookup"><span data-stu-id="7833b-119">How to Set Node Properties</span></span>](../core/how-to-set-node-properties.md)
