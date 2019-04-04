---
title: ノードを記録 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 43af077d-5db8-43ca-8bd0-e3a9e3ebe2b0
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7ec23dcf604e1bd454ba7e69a57c250cf3b1872f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36982347"
---
# <a name="record-nodes"></a><span data-ttu-id="f41b8-102">[レコード] ノード</span><span class="sxs-lookup"><span data-stu-id="f41b8-102">Record Nodes</span></span>
<span data-ttu-id="f41b8-103">BizTalk エディターを使用する、**レコード**を個々 の項目は、情報のコレクションを表すノード。</span><span class="sxs-lookup"><span data-stu-id="f41b8-103">In BizTalk Editor, you use a **Record** node to represent a collection of information, the individual items of which can be:</span></span>  

- <span data-ttu-id="f41b8-104">単純型の情報 (文字列や数値など)。子フィールド ノードとして表されます。</span><span class="sxs-lookup"><span data-stu-id="f41b8-104">Simple types of information, such as strings and numbers, represented as child field nodes.</span></span> <span data-ttu-id="f41b8-105">これらの子フィールド ノードには、いずれかを指定できる**フィールド要素**ノードまたは**フィールド属性**ノード。</span><span class="sxs-lookup"><span data-stu-id="f41b8-105">These child field nodes can be either **Field Element** nodes or **Field Attribute** nodes.</span></span> <span data-ttu-id="f41b8-106">これらの 2 種類のフィールド ノードの詳細については、[フィールド要素 ノード](../core/field-element-nodes.md)と[フィールド属性 ノード](../core/field-attribute-nodes.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f41b8-106">For additional information about these two types of field nodes, see [Field Element Nodes](../core/field-element-nodes.md) and [Field Attribute Nodes](../core/field-attribute-nodes.md).</span></span>  

- <span data-ttu-id="f41b8-107">子として表される複合型の情報、**レコード**ノードまたはグループ ノードとして (**シーケンス グループ**ノード、**グループの選択**ノード、または**すべてのグループ**ノード)。</span><span class="sxs-lookup"><span data-stu-id="f41b8-107">Complex types of information, represented as child **Record** nodes or as a group node (**Sequence Group** node, **Choice Group** node, or **All Group** node).</span></span>  

- <span data-ttu-id="f41b8-108">子として表される吟味については、各種**Any 要素**または**すべての属性**ノード。</span><span class="sxs-lookup"><span data-stu-id="f41b8-108">Any unexamined type of information, represented as child **Any Element** or **Any Attribute** nodes.</span></span>  

- <span data-ttu-id="f41b8-109">によって表される属性のグループ、**属性グループ**ノード。</span><span class="sxs-lookup"><span data-stu-id="f41b8-109">Groups of attributes represented by an **Attribute Group** node.</span></span>  

  <span data-ttu-id="f41b8-110">新しい子ノードを挿入すると、**レコード**ノード、子ノードが常に現在の子ノードの最後に挿入します。</span><span class="sxs-lookup"><span data-stu-id="f41b8-110">When you insert a new child node into a **Record** node, the child node is always inserted at the end of the current child nodes.</span></span> <span data-ttu-id="f41b8-111">内の XML スキーマ定義 (XSD) 言語表記で、新しい要素を追加して、要素の属性が内の要素の末尾に追加されたことを意味する、対応する領域の末尾に、**シーケンス**、 **選択肢**、**すべて**、または**グループ**要素と属性要素の後に出現する、他の属性要素の末尾に追加されます、**シーケンス**、**選択肢**、**すべて**、または**グループ**要素。</span><span class="sxs-lookup"><span data-stu-id="f41b8-111">Within the XML Schema definition (XSD) language representation, new elements are added to the end of their corresponding areas, meaning that nonattribute elements are added to the end of the elements within the **sequence**, **choice**, **all**, or **group** element, and attribute elements are added to the end of any other attribute elements, all of which occur after the **sequence**, **choice**, **all**, or **group** element.</span></span>  

## <a name="xsd-representation"></a><span data-ttu-id="f41b8-112">XSD 表記</span><span class="sxs-lookup"><span data-stu-id="f41b8-112">XSD representation</span></span>  
 <span data-ttu-id="f41b8-113">最初に挿入される、新しいの XSD 表記と**レコード**次の例に示すように、3 行だけのノードで構成されます。</span><span class="sxs-lookup"><span data-stu-id="f41b8-113">When first inserted, the XSD representation of a new **Record** node consists of only three lines, as shown in the following example.</span></span>  

```  
<xs:element name="Record">  
      <xs:complexType />  
</xs:element>  
```  

 <span data-ttu-id="f41b8-114">ときに 1 つの 3 つの属性ノード以外の任意の子ノード (**フィールド属性**、**属性グループ**、および**すべての属性**) に追加されます、 **レコード**内に配置が既定では、ノード、**シーケンス**内の要素、 **complexType**要素。</span><span class="sxs-lookup"><span data-stu-id="f41b8-114">When any child node other than one of the three attribute nodes (**Field Attribute**, **Attribute Group**, and **Any Attribute**) is added to a **Record** node, by default it is placed within a **sequence** element within the **complexType** element.</span></span> <span data-ttu-id="f41b8-115">**シーケンス**属性の最初の子ノードが追加、非属性のすべての子ノードが削除された場合に削除されたときに要素が追加されます。</span><span class="sxs-lookup"><span data-stu-id="f41b8-115">The **sequence** element is added when the first nonattribute child node is added, and removed if all the nonattribute child nodes are deleted.</span></span> <span data-ttu-id="f41b8-116">内で 3 つすべての種類の属性ノードを追加、 **complexType**要素が外側と後に**シーケンス**要素。</span><span class="sxs-lookup"><span data-stu-id="f41b8-116">All three types of attribute nodes are added within the **complexType** element, but outside and after any **sequence** element.</span></span>  

 <span data-ttu-id="f41b8-117">**シーケンス**要素の属性には、子ノードが追加されたことができます、**選択肢**または**すべて**要素を変更する場合、 **Group Order Type (ノードすべてのスキーマのプロパティ)** をスキーマ ツリー内の対応するノードのプロパティ**選択肢**または**すべて**、それぞれします。</span><span class="sxs-lookup"><span data-stu-id="f41b8-117">The **sequence** element within which nonattribute child nodes are added can also be a **choice** or **all** element if you change the **Group Order Type (Node Property of All Schemas)** property of the corresponding node in the schema tree to **Choice** or **All**, respectively.</span></span>  

 <span data-ttu-id="f41b8-118">次の例では、**レコード**ノードが shipTo に変更されました。</span><span class="sxs-lookup"><span data-stu-id="f41b8-118">In the following example, the **Record** node has been renamed shipTo.</span></span> <span data-ttu-id="f41b8-119">内の場所、**レコード**属性と属性のノードが追加されるノードは、角かっこで表示されます。</span><span class="sxs-lookup"><span data-stu-id="f41b8-119">The locations within the **Record** node where attribute and nonattribute nodes are added are shown in brackets.</span></span>  

```  
<xs:element name="">  
    <xs:complexType>  
        <xs:sequence>  
            [Nonattribute child nodes of the record go here.]  
            [Always add new nonattribute child nodes to the end.]  
        </xs:sequence>  
            [Attribute child nodes of the record go here.]  
            [Always add new attribute child nodes to the end.]  
    </xs:complexType>  
</xs:element>  

```  

## <a name="see-also"></a><span data-ttu-id="f41b8-120">参照</span><span class="sxs-lookup"><span data-stu-id="f41b8-120">See Also</span></span>  
- [<span data-ttu-id="f41b8-121">スキーマの BizTalk 表記</span><span class="sxs-lookup"><span data-stu-id="f41b8-121">BizTalk Representation of Schemas</span></span>](../core/biztalk-representation-of-schemas.md)   
- [<span data-ttu-id="f41b8-122">ノードのプロパティ</span><span class="sxs-lookup"><span data-stu-id="f41b8-122">Node Properties</span></span>](../core/node-properties.md)   
- <span data-ttu-id="f41b8-123">**ノードのプロパティを記録する**と**Group Order Type (すべてのスキーマのノード プロパティ)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="f41b8-123">**Record Node Properties** and **Group Order Type (Node Property of All Schemas)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
- [<span data-ttu-id="f41b8-124">ノードのプロパティを設定する方法</span><span class="sxs-lookup"><span data-stu-id="f41b8-124">How to Set Node Properties</span></span>](../core/how-to-set-node-properties.md)
