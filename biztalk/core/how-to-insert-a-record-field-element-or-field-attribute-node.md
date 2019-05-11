---
title: レコード、フィールド要素、またはフィールド属性 ノードを挿入する方法 |Microsoft Docs
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
ms.openlocfilehash: 8f63693877d9cfdc4cbb519515f64fd07a0e2510
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384938"
---
# <a name="how-to-insert-a-record-field-element-or-field-attribute-node"></a><span data-ttu-id="bea5f-102">レコード、フィールド要素、またはフィールド属性 ノードを挿入する方法</span><span class="sxs-lookup"><span data-stu-id="bea5f-102">How to Insert a Record, Field Element, or Field Attribute Node</span></span>
<span data-ttu-id="bea5f-103">**レコード**ノード (など、**ルート**ノード)、**フィールド属性**ノード、および**フィールド要素**名前を変更することで、ノードが一意ようにの名前対応するインスタンス メッセージ内の実際、という名前のカスタム要素の名前を表します。</span><span class="sxs-lookup"><span data-stu-id="bea5f-103">**Record** nodes (including the **Root** node), **Field Attribute** nodes, and **Field Element** nodes are unique in that they can be renamed so that their names represent the names of the actual, custom-named elements in a corresponding instance message.</span></span> <span data-ttu-id="bea5f-104">たとえば、名前を付ける場合、**レコード**ノードに FullName という XML 要素が必要です、インスタンス メッセージ内の対応する位置に、FullName。</span><span class="sxs-lookup"><span data-stu-id="bea5f-104">For example, if you name a **Record** node FullName, at the corresponding location in an instance message an XML element named FullName is expected.</span></span> <span data-ttu-id="bea5f-105">その場合**レコード**FullName という名前のノードが子**フィールド属性**RequireFullMiddleName という名前のノード (とその**Min Occurs**と**Max Occurs**プロパティを設定**1**)、 **FullName**という名前の属性に対応するインスタンス メッセージ内の要素が必要があります**RequireFullMiddleName**関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="bea5f-105">If that **Record** node named FullName has a child **Field Attribute** node named RequireFullMiddleName (with its **Min Occurs** and **Max Occurs** properties set to **1**), the **FullName** element in a corresponding instance message will need to have an attribute named **RequireFullMiddleName** associated with it.</span></span>  
  
 <span data-ttu-id="bea5f-106">すべて**レコード**XSD ので最初に挿入されるときに、ノードの表現、 **complexType**要素、それ以降ではなく**シーケンス**、**選択肢**、または**すべて**要素。</span><span class="sxs-lookup"><span data-stu-id="bea5f-106">All **Record** nodes, when initially inserted, are represented in the XSD as with a **complexType** element, but not with a subsequent **sequence**, **choice**, or **all** element.</span></span> <span data-ttu-id="bea5f-107">このため、 **Group Order Type**、 **Group Max Occurs**、および**Group Min Occurs**のプロパティ、**レコード**ノードは使用できません変更。</span><span class="sxs-lookup"><span data-stu-id="bea5f-107">For this reason, the **Group Order Type**, **Group Max Occurs**, and **Group Min Occurs** properties of the **Record** node are not available for modification.</span></span>  
  
 <span data-ttu-id="bea5f-108">子を追加するとすぐに**レコード**または**フィールド要素**ノードを**レコード**ノード、**シーケンス**は xsd 要素を追加内の表現、 **complexType**この最初の子ノードを格納する要素と**Group Order Type**のプロパティ、**レコード**ノードには、値が表示されます。**シーケンス**します。</span><span class="sxs-lookup"><span data-stu-id="bea5f-108">As soon as you add a child **Record** or **Field Element** node to the **Record** node, a **sequence** element is added to the XSD representation within the **complexType** element to contain this first child node, and the **Group Order Type** property of the **Record** node shows a value of **Sequence**.</span></span> <span data-ttu-id="bea5f-109">ほとんどの状況で変更することができます、 **Group Order Type**プロパティから**シーケンス**に**選択肢**、およびより限定的な状況から**シーケンス**に**すべて**ため、いずれかに対応する子ノードを含む要素のペアを変更する**complexType choice**または**complexType/すべて**、それぞれします。</span><span class="sxs-lookup"><span data-stu-id="bea5f-109">In most circumstances, you can change the **Group Order Type** property from **Sequence** to **Choice**, and in more limited circumstances, from **Sequence** to **All**, thereby changing the element pair that contains the corresponding child nodes to either **complexType/choice** or **complexType/all**, respectively.</span></span>  
  
 <span data-ttu-id="bea5f-110">**フィールド属性**ノードが同じスコープ内に同じノード名を含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="bea5f-110">**Field Attribute** nodes cannot have the same node names while in the same scope.</span></span>  
  
 <span data-ttu-id="bea5f-111">**レコード**と**フィールド要素**次の条件が満たされた場合にのみ、ノードは、同じスコープ内に同じノード名には。</span><span class="sxs-lookup"><span data-stu-id="bea5f-111">**Record** and **Field Element** nodes can have the same node names while in the same scope only if the following conditions are met:</span></span>  
  
-   <span data-ttu-id="bea5f-112">同じデータ型があります。</span><span class="sxs-lookup"><span data-stu-id="bea5f-112">They have the same data type.</span></span>  
  
-   <span data-ttu-id="bea5f-113">いない内、**すべてのグループ**ノード。</span><span class="sxs-lookup"><span data-stu-id="bea5f-113">They are not within an **All Group** node.</span></span>  
  
### <a name="to-insert-a-new-child-record-node-field-element-node-or-field-attribute-node-within-the-schema-node-or-an-existing-record-node"></a><span data-ttu-id="bea5f-114">新しい子レコード ノード、フィールド要素 ノード、またはスキーマ ノードまたは既存のレコード ノード内でフィールド属性 ノードを挿入するには</span><span class="sxs-lookup"><span data-stu-id="bea5f-114">To insert a new child Record node, Field Element node, or Field Attribute node within the Schema node or an existing Record node</span></span>  
  
1.  <span data-ttu-id="bea5f-115">選択、**スキーマ**ノードまたは既存**レコード**ノード。</span><span class="sxs-lookup"><span data-stu-id="bea5f-115">Select the **Schema** node or an existing **Record** node.</span></span>  
  
2.  <span data-ttu-id="bea5f-116">**BizTalk**メニューで、**スキーマ ノードの挿入**、 をクリックし、**子レコード**、**子フィールド要素**、または**子フィールド属性**必要に応じて、します。</span><span class="sxs-lookup"><span data-stu-id="bea5f-116">On the **BizTalk** menu, point to **Insert Schema Node**, and then click **Child Record**, **Child Field Element**, or **Child Field Attribute**, as appropriate.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="bea5f-117">選択された種類の子ノードが追加後にいずれかの最後のノード スキーマ ツリーで (内で挿入するときに、**スキーマ**ノード) または選択した既存最後の子ノードの後に**レコード**ノード (場合内で、既存の挿入**レコード**ノード)。</span><span class="sxs-lookup"><span data-stu-id="bea5f-117">A child node of the chosen type is added after either the last node in the schema tree (when inserting within the **Schema** node) or after the last existing child node of the selected **Record** node (when inserting within an existing **Record** node).</span></span>  
  
3.  <span data-ttu-id="bea5f-118">新しく挿入の名前を入力**レコード**、**フィールド要素**、または**フィールド属性**ノード、および ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="bea5f-118">Type a name for the newly inserted **Record**, **Field Element**, or **Field Attribute** node, and then press ENTER.</span></span>  
  
### <a name="to-insert-a-sibling-record-node-field-attribute-node-or-field-element-node-within-an-existing-record-node"></a><span data-ttu-id="bea5f-119">兄弟レコード ノード、フィールド属性 ノード、または既存のレコード ノード内でフィールド要素 ノードを挿入するには</span><span class="sxs-lookup"><span data-stu-id="bea5f-119">To insert a sibling Record node, Field Attribute node, or Field Element node within an existing Record node</span></span>  
  
1.  <span data-ttu-id="bea5f-120">子ノードを選択、**レコード**ノードの兄弟を挿入する**レコード**、**フィールド属性**、または**フィールド要素**ノードです。</span><span class="sxs-lookup"><span data-stu-id="bea5f-120">Select any child node of the **Record** node into which you want to insert the sibling **Record**, **Field Attribute**, or **Field Element** node.</span></span>  
  
2.  <span data-ttu-id="bea5f-121">**BizTalk**メニューで、**スキーマ ノードの挿入**、 をクリックし、**兄弟レコード**、**兄弟フィールド属性**、または**兄弟フィールド要素**必要に応じて、します。</span><span class="sxs-lookup"><span data-stu-id="bea5f-121">On the **BizTalk** menu, point to **Insert Schema Node**, and then click **Sibling Record**, **Sibling Field Attribute**, or **Sibling Field Element**, as appropriate.</span></span>  
  
     <span data-ttu-id="bea5f-122">選択された種類の兄弟ノードは、選択したノードの兄弟の最後に挿入されます。</span><span class="sxs-lookup"><span data-stu-id="bea5f-122">A sibling node of the chosen type is inserted at the end of the siblings of the selected node.</span></span>  
  
3.  <span data-ttu-id="bea5f-123">新しく挿入の名前を入力**レコード**、**フィールド属性**、または**フィールド要素**ノード、および ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="bea5f-123">Type a name for the newly inserted **Record**, **Field Attribute**, or **Field Element** node, and then press ENTER.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bea5f-124">参照</span><span class="sxs-lookup"><span data-stu-id="bea5f-124">See Also</span></span>  
 [<span data-ttu-id="bea5f-125">スキーマへのノードの挿入</span><span class="sxs-lookup"><span data-stu-id="bea5f-125">Inserting Nodes into a Schema</span></span>](../core/inserting-nodes-into-a-schema.md)