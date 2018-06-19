---
title: レコード、フィールド要素、またはフィールド属性 ノードを挿入する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c26f2281-f1b8-4788-8593-8d6ad29a53f0
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1341a0f2d89070d42620396a8c86d497b5d646ef
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22255098"
---
# <a name="how-to-insert-a-record-field-element-or-field-attribute-node"></a><span data-ttu-id="30c1a-102">レコード、フィールド要素、またはフィールド属性 ノードを挿入する方法</span><span class="sxs-lookup"><span data-stu-id="30c1a-102">How to Insert a Record, Field Element, or Field Attribute Node</span></span>
<span data-ttu-id="30c1a-103">**レコード**ノード (など、**ルート**ノード)、**フィールド属性**ノード、および**フィールド要素**ノードは、一意な名前を変更できるように、名前は、対応するインスタンス メッセージに、カスタム名前付きの実際の要素の名前を表します。</span><span class="sxs-lookup"><span data-stu-id="30c1a-103">**Record** nodes (including the **Root** node), **Field Attribute** nodes, and **Field Element** nodes are unique in that they can be renamed so that their names represent the names of the actual, custom-named elements in a corresponding instance message.</span></span> <span data-ttu-id="30c1a-104">たとえば、名前を付ける場合、**レコード**ノードに FullName という XML 要素が必要と、インスタンス メッセージ内の対応する位置に、FullName。</span><span class="sxs-lookup"><span data-stu-id="30c1a-104">For example, if you name a **Record** node FullName, at the corresponding location in an instance message an XML element named FullName is expected.</span></span> <span data-ttu-id="30c1a-105">場合は、その**レコード**FullName という名前のノードが子**フィールド属性**RequireFullMiddleName という名前のノード (とその**Min Occurs**と**Max Occurs**プロパティに設定**1**) では、 **FullName**対応するインスタンス メッセージ内の要素をという名前の属性である必要があります**RequireFullMiddleName**関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="30c1a-105">If that **Record** node named FullName has a child **Field Attribute** node named RequireFullMiddleName (with its **Min Occurs** and **Max Occurs** properties set to **1**), the **FullName** element in a corresponding instance message will need to have an attribute named **RequireFullMiddleName** associated with it.</span></span>  
  
 <span data-ttu-id="30c1a-106">すべて**レコード**最初に挿入すると、ノードは、XSD ので表されます、 **complexType**要素が、それ以降ではなく**シーケンス**、**選択肢**、または**すべて**要素。</span><span class="sxs-lookup"><span data-stu-id="30c1a-106">All **Record** nodes, when initially inserted, are represented in the XSD as with a **complexType** element, but not with a subsequent **sequence**, **choice**, or **all** element.</span></span> <span data-ttu-id="30c1a-107">このため、 **Group Order Type**、 **Group Max Occurs**、および**Group Min Occurs**のプロパティ、**レコード**ノードが利用できません。変更。</span><span class="sxs-lookup"><span data-stu-id="30c1a-107">For this reason, the **Group Order Type**, **Group Max Occurs**, and **Group Min Occurs** properties of the **Record** node are not available for modification.</span></span>  
  
 <span data-ttu-id="30c1a-108">子を追加するとすぐに**レコード**または**フィールド要素**ノードを**レコード** ノード、**シーケンス**XSD には、要素を追加してください。内の表現、 **complexType**この最初の子ノードを格納する要素と**Group Order Type**のプロパティ、**レコード**ノードは値を示します**シーケンス**です。</span><span class="sxs-lookup"><span data-stu-id="30c1a-108">As soon as you add a child **Record** or **Field Element** node to the **Record** node, a **sequence** element is added to the XSD representation within the **complexType** element to contain this first child node, and the **Group Order Type** property of the **Record** node shows a value of **Sequence**.</span></span> <span data-ttu-id="30c1a-109">ほとんどの状況で変更することができます、 **Group Order Type**プロパティから**シーケンス**に**選択肢**、および制限が多くの状況でから**シーケンス**に**すべて**これにより、いずれかに対応する子ノードを含む要素のペアを変更する**complexType/選択肢**または**complexType またはすべて**、それぞれします。</span><span class="sxs-lookup"><span data-stu-id="30c1a-109">In most circumstances, you can change the **Group Order Type** property from **Sequence** to **Choice**, and in more limited circumstances, from **Sequence** to **All**, thereby changing the element pair that contains the corresponding child nodes to either **complexType/choice** or **complexType/all**, respectively.</span></span>  
  
 <span data-ttu-id="30c1a-110">**フィールド属性**ノードは、同じスコープ内に重複したノード名を持つことはできません。</span><span class="sxs-lookup"><span data-stu-id="30c1a-110">**Field Attribute** nodes cannot have the same node names while in the same scope.</span></span>  
  
 <span data-ttu-id="30c1a-111">**レコード**と**フィールド要素**ノードは、次の条件が満たされた場合にのみ、同じスコープ内に重複したノード名を持つことができます。</span><span class="sxs-lookup"><span data-stu-id="30c1a-111">**Record** and **Field Element** nodes can have the same node names while in the same scope only if the following conditions are met:</span></span>  
  
-   <span data-ttu-id="30c1a-112">同じデータ型である。</span><span class="sxs-lookup"><span data-stu-id="30c1a-112">They have the same data type.</span></span>  
  
-   <span data-ttu-id="30c1a-113">いない内、**すべてのグループ**ノード。</span><span class="sxs-lookup"><span data-stu-id="30c1a-113">They are not within an **All Group** node.</span></span>  
  
### <a name="to-insert-a-new-child-record-node-field-element-node-or-field-attribute-node-within-the-schema-node-or-an-existing-record-node"></a><span data-ttu-id="30c1a-114">[スキーマ] ノードまたは既存の [レコード] ノード内に新しい子の [レコード] ノード、[フィールド要素] ノード、または [フィールド属性] ノードを挿入するには</span><span class="sxs-lookup"><span data-stu-id="30c1a-114">To insert a new child Record node, Field Element node, or Field Attribute node within the Schema node or an existing Record node</span></span>  
  
1.  <span data-ttu-id="30c1a-115">選択、**スキーマ**ノードまたは既存**レコード**ノード。</span><span class="sxs-lookup"><span data-stu-id="30c1a-115">Select the **Schema** node or an existing **Record** node.</span></span>  
  
2.  <span data-ttu-id="30c1a-116">**BizTalk**  メニューのをポイント**スキーマ ノードの挿入**、クリックして**子レコード**、**子フィールド要素**、または**子フィールド属性** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="30c1a-116">On the **BizTalk** menu, point to **Insert Schema Node**, and then click **Child Record**, **Child Field Element**, or **Child Field Attribute**, as appropriate.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="30c1a-117">選択した型の子ノードが後に追加するか最後のノード、スキーマ ツリー内 (内に挿入するときに、**スキーマ**ノード) または既存最後の子ノードの選択した後に**レコード**ノード (場合内で、既存の挿入**レコード**ノード)。</span><span class="sxs-lookup"><span data-stu-id="30c1a-117">A child node of the chosen type is added after either the last node in the schema tree (when inserting within the **Schema** node) or after the last existing child node of the selected **Record** node (when inserting within an existing **Record** node).</span></span>  
  
3.  <span data-ttu-id="30c1a-118">新しく挿入されるの名前を入力**レコード**、**フィールド要素**、または**フィールド属性**ノード、および、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="30c1a-118">Type a name for the newly inserted **Record**, **Field Element**, or **Field Attribute** node, and then press ENTER.</span></span>  
  
### <a name="to-insert-a-sibling-record-node-field-attribute-node-or-field-element-node-within-an-existing-record-node"></a><span data-ttu-id="30c1a-119">既存の [レコード] ノード内に兄弟の [レコード] ノード、[フィールド属性] ノード、または [フィールド要素] ノードを挿入するには</span><span class="sxs-lookup"><span data-stu-id="30c1a-119">To insert a sibling Record node, Field Attribute node, or Field Element node within an existing Record node</span></span>  
  
1.  <span data-ttu-id="30c1a-120">子ノードを選択、**レコード**ノードの兄弟を挿入する**レコード**、**フィールド属性**、または**フィールド要素**ノードです。</span><span class="sxs-lookup"><span data-stu-id="30c1a-120">Select any child node of the **Record** node into which you want to insert the sibling **Record**, **Field Attribute**, or **Field Element** node.</span></span>  
  
2.  <span data-ttu-id="30c1a-121">**BizTalk**  メニューのをポイント**スキーマ ノードの挿入**、クリックして**兄弟レコード**、**兄弟フィールド属性**、または**兄弟フィールド要素** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="30c1a-121">On the **BizTalk** menu, point to **Insert Schema Node**, and then click **Sibling Record**, **Sibling Field Attribute**, or **Sibling Field Element**, as appropriate.</span></span>  
  
     <span data-ttu-id="30c1a-122">選択された種類の兄弟ノードは、選択されたノードの兄弟の最後に挿入されます。</span><span class="sxs-lookup"><span data-stu-id="30c1a-122">A sibling node of the chosen type is inserted at the end of the siblings of the selected node.</span></span>  
  
3.  <span data-ttu-id="30c1a-123">新しく挿入されるの名前を入力**レコード**、**フィールド属性**、または**フィールド要素**ノード、および、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="30c1a-123">Type a name for the newly inserted **Record**, **Field Attribute**, or **Field Element** node, and then press ENTER.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30c1a-124">参照</span><span class="sxs-lookup"><span data-stu-id="30c1a-124">See Also</span></span>  
 [<span data-ttu-id="30c1a-125">スキーマにノードを挿入</span><span class="sxs-lookup"><span data-stu-id="30c1a-125">Inserting Nodes into a Schema</span></span>](../core/inserting-nodes-into-a-schema.md)