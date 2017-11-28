---
title: "属性グループ ノード |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ea02fae8-4e03-486a-8d9d-185ae230d3a0
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 04db816f1209b7cd503b9a162cdd2a030ba86292
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="attribute-group-nodes"></a><span data-ttu-id="a4930-102">[属性グループ] ノード</span><span class="sxs-lookup"><span data-stu-id="a4930-102">Attribute Group Nodes</span></span>

## <a name="overview"></a><span data-ttu-id="a4930-103">概要</span><span class="sxs-lookup"><span data-stu-id="a4930-103">Overview</span></span>
<span data-ttu-id="a4930-104">追加する BizTalk エディターで、**属性グループ**ノードを**レコード**ノードまたは別**属性グループ**をより詳細に使用すると予想される属性のグループを含むノード1 よりも**レコード**ノード。</span><span class="sxs-lookup"><span data-stu-id="a4930-104">In BizTalk Editor, you can add an **Attribute Group** node to a **Record** node or to another **Attribute Group** node to contain a group of attributes that you expect to use in more than one **Record** node.</span></span> <span data-ttu-id="a4930-105">追加する、**属性グループ**別のノード**属性グループ**ノードは、属性グループの入れ子を実現します。</span><span class="sxs-lookup"><span data-stu-id="a4930-105">Adding an **Attribute Group** node to another **Attribute Group** node achieves attribute group nesting.</span></span> <span data-ttu-id="a4930-106">これにより、1 か所で複数使用できる属性のグループを定義する**レコード**または**属性グループ**ノード。</span><span class="sxs-lookup"><span data-stu-id="a4930-106">This allows you to define a group of attributes in one place that can be used in multiple **Record** or **Attribute Group** nodes.</span></span> <span data-ttu-id="a4930-107">それ以降、属性グループに対して行った変更は、その属性グループに関連付けられたすべてのノードに反映されます。</span><span class="sxs-lookup"><span data-stu-id="a4930-107">Subsequent modifications to the attribute group will propagate to all of the nodes with which that attribute group is associated.</span></span> <span data-ttu-id="a4930-108">このしくみは、修正を加えたノードのコンテキストに依存しません。</span><span class="sxs-lookup"><span data-stu-id="a4930-108">This is true regardless of the node context in which the modifications are made.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a4930-109">BizTalk エディターで、 **AttributeGroup**ノードが既定では、文字列で表される\<AttribGroup:attribGroup*N*> スキーマ ツリー ビューで、 *N*単調に増加する数字を指定します。</span><span class="sxs-lookup"><span data-stu-id="a4930-109">In BizTalk Editor, the **AttributeGroup** node is represented by default with the string \<AttribGroup:attribGroup*N*> in the schema tree view, where *N* is a monotonically increasing numeral.</span></span> <span data-ttu-id="a4930-110">AttribGroup を変更することができます*N*に新しい一意の名前を入力してその名前の部分の**Group Reference**プロパティです。</span><span class="sxs-lookup"><span data-stu-id="a4930-110">You can change the attribGroup*N* portion of its name by typing a new unique name in its **Group Reference** property.</span></span>  
  
 <span data-ttu-id="a4930-111">最初に作成するときに、**属性グループ**ノード、単に挿入することのいずれか、**レコード**または**属性グループ**ノードをそのが使用され、必要に応じて変更その名前でその**Group Reference**プロパティです。</span><span class="sxs-lookup"><span data-stu-id="a4930-111">When initially creating an **Attribute Group** node, you simply insert it into one of the **Record** or **Attribute Group** nodes in which it will be used, and optionally change its name in its **Group Reference** property.</span></span> <span data-ttu-id="a4930-112">別の同じ属性グループを使用する 2 つの方法がある**レコード**または**属性グループ**ノード。</span><span class="sxs-lookup"><span data-stu-id="a4930-112">There are two ways to use the same attribute group in another **Record** or **Attribute Group** node:</span></span>  
  
-   <span data-ttu-id="a4930-113">既存をコピーする**属性グループ**ノードを他に貼り付けると**レコード**ノード。</span><span class="sxs-lookup"><span data-stu-id="a4930-113">You can copy the existing **Attribute Group** node and then paste it into that other **Record** node.</span></span>  
  
-   <span data-ttu-id="a4930-114">新しいを挿入する**属性グループ**を他のノード**レコード**ノードを展開し、セット、 **Group Reference**新しいプロパティ**属性グループ**ノードを既存の参照**属性グループ**ノード。</span><span class="sxs-lookup"><span data-stu-id="a4930-114">You can insert a new **Attribute Group** node into that other **Record** node, and then set the **Group Reference** property of the new **Attribute Group** node to reference an existing **Attribute Group** node.</span></span>  
  
 <span data-ttu-id="a4930-115">その後、変更することができます、**属性グループ**ノード — などの追加や削除、**フィールド属性**ノード: いずれかのコンテキストで**レコード**または**属性グループ**貼り付け先のノードです。</span><span class="sxs-lookup"><span data-stu-id="a4930-115">Thereafter, you can modify the **Attribute Group** node—for example, by adding or deleting a **Field Attribute** node—in the context of any **Record** or **Attribute Group** node into which you pasted it.</span></span> <span data-ttu-id="a4930-116">変更は他のすべてに反映されますを**レコード**または**属性グループ**属性グループが関連付けられているノードです。</span><span class="sxs-lookup"><span data-stu-id="a4930-116">That change will propagate to all other **Record** or **Attribute Group** nodes with which the attribute group is associated.</span></span>  
  
 <span data-ttu-id="a4930-117">追加するには、無意味な**属性グループ**関連するノードが含まれている、少なくとも 1 つの関連するノードを追加することがなくノード**フィールド属性**ノード、 **Any 属性**ノード、および (入れ子になった)**属性グループ**ノード。</span><span class="sxs-lookup"><span data-stu-id="a4930-117">It would be pointless to add an **Attribute Group** node without adding at least one relevant node to it, where relevant nodes include **Field Attribute** nodes, **Any Attribute** nodes, and (nested) **Attribute Group** nodes.</span></span> <span data-ttu-id="a4930-118">属性を 1 つしか持たないような属性グループを作成しても、将来、さらに多くの属性を追加することを想定しているのでなければ、あまり意味はありません。</span><span class="sxs-lookup"><span data-stu-id="a4930-118">In fact, an attribute group that contains only a single attribute is somewhat ill-conceived, unless you are making a point of planning for the addition of more attributes in the future.</span></span>  
  
 <span data-ttu-id="a4930-119">**属性グループ**属性のグループを構築および結合する方法に多くの可能性を許可する、ノードをネストすることができます。</span><span class="sxs-lookup"><span data-stu-id="a4930-119">**Attribute Group** nodes can be nested, allowing more possibilities in how groups of attributes can be constructed and combined.</span></span> <span data-ttu-id="a4930-120">**属性グループ**ノードを含めることも、**すべての属性**ノードに対応できるインスタンスの属性に関するワイルドカード文字機能を含む属性グループ。</span><span class="sxs-lookup"><span data-stu-id="a4930-120">**Attribute Group** nodes can also contain the **Any Attribute** node, allowing an attribute group to contain wildcard character capabilities with respect to the attribute instances it can accommodate.</span></span>  
  
## <a name="xsd-representation"></a><span data-ttu-id="a4930-121">XSD 表記</span><span class="sxs-lookup"><span data-stu-id="a4930-121">XSD representation</span></span>  
 <span data-ttu-id="a4930-122">ときに、**属性グループ**ノードが最初に追加される、**レコード**ノードまたは別**属性グループ**ノード、対応する XML スキーマ定義 (XSD) の 2 つの領域言語表記のスキーマが影響を受けます。</span><span class="sxs-lookup"><span data-stu-id="a4930-122">When an **Attribute Group** node is first added to a **Record** node or to another **Attribute Group** node, two distinct areas of the corresponding XML Schema definition (XSD) language representation of the schema are affected.</span></span> <span data-ttu-id="a4930-123">次の例では、新しい**属性グループ** ノードで太字を既存に追加された**レコード**既存が格納されているノード**フィールド要素**ノード。</span><span class="sxs-lookup"><span data-stu-id="a4930-123">In the following example, a new **Attribute Group** node, in bold, has been added to an existing **Record** node that already contains an existing **Field Element** node.</span></span>  
  
```  
        ...  
        <xs:element name="ExistingRecord">  
            <xs:complexType>  
                <xs:sequence>  
                    <xs:element name="ExistingFieldElement" type="xs:string" />  
                </xs:sequence>  
                <xs:attributeGroup ref="attrGroup0" />  
            </xs:complexType>  
        </xs:element>  
        ...   
    <xs:attributeGroup name="attrGroup0" />  
</xs:schema>  
```  
  
 <span data-ttu-id="a4930-124">注方法、 **attributeGroup**の XSD 表記内の要素、**レコード**ノードが参照するグローバル**attributeGroup**要素の子として追加される、**スキーマ**要素。</span><span class="sxs-lookup"><span data-stu-id="a4930-124">Note how the **attributeGroup** element within the XSD representation of the **Record** node references a global **attributeGroup** element that is added as a child of the **schema** element.</span></span> <span data-ttu-id="a4930-125">このように、スキーマの XSD 内で、属性グループをグローバルとして定義することで、スキーマ内の任意の場所から属性グループを参照できるようにしています。</span><span class="sxs-lookup"><span data-stu-id="a4930-125">This global definition of the attribute group within the XSD representation of the schema allows the attribute group to be referenced in multiple locations throughout the schema.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a4930-126">既定の属性グループ名は自動的に提供されているあるフォーム attrGroup*N*ここで、 *N*単調に増加する数字を指定します。</span><span class="sxs-lookup"><span data-stu-id="a4930-126">Default attribute group names that are supplied automatically have the form attrGroup*N*, where *N* is a monotonically increasing numeral.</span></span> <span data-ttu-id="a4930-127">新しい一意の名前を提供することで属性グループの名前を変更することができます、 **Group Reference**プロパティです。</span><span class="sxs-lookup"><span data-stu-id="a4930-127">You can rename an attribute group by providing a new, unique name in its **Group Reference** property.</span></span> <span data-ttu-id="a4930-128">スキーマ ツリー内で属性グループの名前を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="a4930-128">An attribute group cannot be renamed in place within the schema tree.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4930-129">参照</span><span class="sxs-lookup"><span data-stu-id="a4930-129">See Also</span></span>  
-  [<span data-ttu-id="a4930-130">スキーマの BizTalk 表記</span><span class="sxs-lookup"><span data-stu-id="a4930-130">BizTalk Representation of Schemas</span></span>](../core/biztalk-representation-of-schemas.md)   
-  [<span data-ttu-id="a4930-131">ノードのプロパティ</span><span class="sxs-lookup"><span data-stu-id="a4930-131">Node Properties</span></span>](../core/node-properties.md)   
-  <span data-ttu-id="a4930-132">**シーケンス グループ ノードのプロパティ**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="a4930-132">**Sequence Group Node Properties** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>  
-  [<span data-ttu-id="a4930-133">ノードのプロパティを設定する方法</span><span class="sxs-lookup"><span data-stu-id="a4930-133">How to Set Node Properties</span></span>](../core/how-to-set-node-properties.md)   
-  [<span data-ttu-id="a4930-134">フィールド属性 ノード</span><span class="sxs-lookup"><span data-stu-id="a4930-134">Field Attribute Nodes</span></span>](../core/field-attribute-nodes.md)   
-  [<span data-ttu-id="a4930-135">任意の属性ノード</span><span class="sxs-lookup"><span data-stu-id="a4930-135">Any Attribute Nodes</span></span>](../core/any-attribute-nodes.md)