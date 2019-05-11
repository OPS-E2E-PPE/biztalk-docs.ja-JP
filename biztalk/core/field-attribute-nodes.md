---
title: フィールド属性 ノード |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9e964c07-53e5-473f-84f2-05af4796cbbe
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b804223622a197f9de0b18cce34f8ab57d6a6fc3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65345628"
---
# <a name="field-attribute-nodes"></a><span data-ttu-id="3dfea-102">[フィールド属性] ノード</span><span class="sxs-lookup"><span data-stu-id="3dfea-102">Field Attribute Nodes</span></span>

## <a name="overview"></a><span data-ttu-id="3dfea-103">概要</span><span class="sxs-lookup"><span data-stu-id="3dfea-103">Overview</span></span>
<span data-ttu-id="3dfea-104">BizTalk エディターを使用する**フィールド属性**ノードは、単純な文字列や数値などの情報項目を表すため。</span><span class="sxs-lookup"><span data-stu-id="3dfea-104">In BizTalk Editor, you use **Field Attribute** nodes to describe items of information that are simple in nature, such as strings and numbers.</span></span> <span data-ttu-id="3dfea-105">また、このノードは、目的の情報が、XML 要素の内容としてではなく、実際のメッセージ インスタンスに属性の値として現れる場合に使用されます。</span><span class="sxs-lookup"><span data-stu-id="3dfea-105">Further, they are used when the information in question appears as the value of an attribute in an actual instance of a message, as opposed to appearing as the content of an XML element.</span></span> <span data-ttu-id="3dfea-106">要素の内容として格納されている情報の詳細については、次を参照してください。[フィールド要素 ノード](../core/field-element-nodes.md)します。</span><span class="sxs-lookup"><span data-stu-id="3dfea-106">For additional information about information that is stored as element content, see [Field Element Nodes](../core/field-element-nodes.md).</span></span>  

 <span data-ttu-id="3dfea-107">最も基本的な用途の**フィールド属性**の子ノードとしてノードの場合は**レコード**、ノードの子ノードとしても使用**属性グループ**ノード。</span><span class="sxs-lookup"><span data-stu-id="3dfea-107">Although the most straightforward use of **Field Attribute** nodes is as child nodes of **Record** nodes, they can also be used as child nodes of **Attribute Group** nodes.</span></span> <span data-ttu-id="3dfea-108">後者の場合、**フィールド属性**ノードの子である、**属性グループ**ノードは、いずれかの属性として使用**レコード**そのを含むノード**属性グループ**ノード。</span><span class="sxs-lookup"><span data-stu-id="3dfea-108">In the latter case, the **Field Attribute** nodes that are children of an **Attribute Group** node are available as attributes of any **Record** node that includes that **Attribute Group** node.</span></span> <span data-ttu-id="3dfea-109">詳細については**属性グループ**ノードを参照してください[属性グループ ノード](../core/attribute-group-nodes.md)します。</span><span class="sxs-lookup"><span data-stu-id="3dfea-109">For more information about **Attribute Group** nodes, see [Attribute Group Nodes](../core/attribute-group-nodes.md).</span></span>  

> [!NOTE]
>  <span data-ttu-id="3dfea-110">BizTalk エディターでは、要素と属性要素の両方で表現できる、**フィールド**ノードがスキーマ ツリー ビューで、XSD ウィンドウにおける XML 表記で、それらに関連付けられている別のアイコン、およびVisual Studio のプロパティ ウィンドウでさまざまなプロパティ。</span><span class="sxs-lookup"><span data-stu-id="3dfea-110">In BizTalk Editor, both the element and attribute elements can be represented by a **Field** node, though they have different icons associated with them in the schema tree view, a different XML representation in the XSD window, and different properties in the Visual Studio Properties window.</span></span>  

 <span data-ttu-id="3dfea-111">XML メッセージに含まれる特定の情報項目 (ここでいう情報項目とは、文字列や数値など、1 つの独立した単純型のこと) では、その情報を要素の属性として表すべきか、要素のサブ要素として表すべきかという問題があります。</span><span class="sxs-lookup"><span data-stu-id="3dfea-111">For any given item of information in an XML message, where item of information means a single discrete simple type, such as a string or number, there is always a question regarding whether that information should be represented as the attribute of an element, or as a subelement of that element.</span></span> <span data-ttu-id="3dfea-112">一般に、格納される値が不連続であり、数が少なく、要素そのもののセマンティクスが変わりやすい場合は、情報項目を属性として表します。</span><span class="sxs-lookup"><span data-stu-id="3dfea-112">As a general rule, representing an item of information as an attribute tends to be more appropriate when the possible values are discrete, few in number, and tend to modify the semantics of the element itself.</span></span> <span data-ttu-id="3dfea-113">同じ値が繰り返し出現する場合、取りうる値の範囲が大きい場合、(文字列などが) 長くなってしまう場合、順序に関連性のある複数の兄弟値のいずれかが格納される場合などは、情報項目をサブ要素として表した方が適切な結果が得られる傾向があります。</span><span class="sxs-lookup"><span data-stu-id="3dfea-113">Representing an item of information as a subelement tends to be more appropriate when the possible values can repeat a variable number of times, are likely to have more widely ranging values, might be long, as in long strings, and are one of several sibling values where their order is relevant.</span></span> <span data-ttu-id="3dfea-114">既存の XML の種類のスキーマを作成する場合を文書化を使用して選択した、**フィールド要素**ノードまたは**フィールド属性**特定の情報項目のノードは既に行われましたとXML に一致するノードを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3dfea-114">If you are creating a schema for an existing type of XML document, your choice of using a **Field Element** node or a **Field Attribute** node for a particular item of information has already been made for you, and you must use the node that matches the XML.</span></span>  

> [!NOTE]
>  <span data-ttu-id="3dfea-115">ルート ノードがない可能性があります**フィールド**属性。</span><span class="sxs-lookup"><span data-stu-id="3dfea-115">Root nodes may not have **Field** attributes.</span></span> <span data-ttu-id="3dfea-116">**フィールド**にアタッチされている属性、**ルート**ノードは、スキーマには保存されません。</span><span class="sxs-lookup"><span data-stu-id="3dfea-116">**Field** attributes attached to the **Root** node are not saved with the schema.</span></span>  

## <a name="xsd-representation"></a><span data-ttu-id="3dfea-117">XSD 表記</span><span class="sxs-lookup"><span data-stu-id="3dfea-117">XSD representation</span></span>  
 <span data-ttu-id="3dfea-118">ときに、**フィールド属性**ノードの挿入、**レコード**ノードで他の子ノードの最後に挿入されます、**レコード**ノード。</span><span class="sxs-lookup"><span data-stu-id="3dfea-118">When a **Field Attribute** node is inserted into a **Record** node, it is inserted at the end of any other child nodes in the **Record** node.</span></span> <span data-ttu-id="3dfea-119">これは、後に挿入されているが含まれています、**シーケンス**、**選択肢**、または**すべて**要素、属性ノードを含む前後にあったすべての属性ノード。挿入されます。</span><span class="sxs-lookup"><span data-stu-id="3dfea-119">This includes being inserted after the **sequence**, **choice**, or **all** element containing any nonattribute nodes, and after any attribute nodes that were previously inserted.</span></span> <span data-ttu-id="3dfea-120">次の例は、新しい**フィールド属性**太字内のノードの最後に挿入された、**レコード**ノード (ノードが自身の id を明確にするという名前) が使用します。</span><span class="sxs-lookup"><span data-stu-id="3dfea-120">The following example shows a new **Field Attribute** node, in bold, inserted at the end of a **Record** node (with nodes named to clarify their identity).</span></span>  

```  
<xs:element name="ContainingRecord">  
    <xs:complexType>  
        <xs:sequence>  
            <xs:element name="FieldElement" type="xs:string" />  
            <xs:element name="EmptyNestedRecord">  
                <xs:complexType />  
            </xs:element>  
        </xs:sequence>  
        <xs:attribute name="ExistingFieldAttribute" type="xs:string" />  

    </xs:complexType>  
</xs:element>  

```  

## <a name="see-also"></a><span data-ttu-id="3dfea-121">参照</span><span class="sxs-lookup"><span data-stu-id="3dfea-121">See Also</span></span>  
- [<span data-ttu-id="3dfea-122">スキーマの BizTalk 表記</span><span class="sxs-lookup"><span data-stu-id="3dfea-122">BizTalk Representation of Schemas</span></span>](../core/biztalk-representation-of-schemas.md)   
- [<span data-ttu-id="3dfea-123">ノードのプロパティ</span><span class="sxs-lookup"><span data-stu-id="3dfea-123">Node Properties</span></span>](../core/node-properties.md)   
- <span data-ttu-id="3dfea-124">**[フィールド要素] ノード プロパティ** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="3dfea-124">**Field Element Node Properties** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>  
- [<span data-ttu-id="3dfea-125">ノードのプロパティを設定する方法</span><span class="sxs-lookup"><span data-stu-id="3dfea-125">How to Set Node Properties</span></span>](../core/how-to-set-node-properties.md)   
- <span data-ttu-id="3dfea-126">[[属性グループ] ノード](../core/attribute-group-nodes.md)</span><span class="sxs-lookup"><span data-stu-id="3dfea-126">[Attribute Group Nodes](../core/attribute-group-nodes.md)</span></span>
