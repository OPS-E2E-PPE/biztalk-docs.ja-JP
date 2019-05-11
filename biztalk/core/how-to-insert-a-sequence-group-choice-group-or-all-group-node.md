---
title: シーケンス グループ、グループの選択、またはすべてのグループ ノードを挿入する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 19aee400-1369-4310-b1b4-1bfeb2643236
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bfc4b4f244c0a265a0b65efaf2f8f7bbd25e9ebd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384952"
---
# <a name="how-to-insert-a-sequence-group-choice-group-or-all-group-node"></a><span data-ttu-id="e4b8f-102">シーケンス グループ、グループの選択、またはすべてのグループ ノードを挿入する方法</span><span class="sxs-lookup"><span data-stu-id="e4b8f-102">How to Insert a Sequence Group, Choice Group, or All Group Node</span></span>
<span data-ttu-id="e4b8f-103">BizTalk エディターには、要素グループ ノードの 3 種類がサポートされています。**シーケンス グループ**、**グループの選択**、および**すべてのグループ**します。</span><span class="sxs-lookup"><span data-stu-id="e4b8f-103">BizTalk Editor supports three types of group nodes for elements: **Sequence Group**, **Choice Group**, and **All Group**.</span></span> <span data-ttu-id="e4b8f-104">さまざまな種類のグループ ノードでは、対応するインスタンス メッセージで、グループの子ノードでさまざまな制約を確立します。</span><span class="sxs-lookup"><span data-stu-id="e4b8f-104">These different types of group nodes establish different constraints on the child nodes of the group in corresponding instance messages.</span></span> <span data-ttu-id="e4b8f-105">これらのさまざまな種類のグループの制約については、Web 上の XML スキーマ定義 (XSD) 言語に関する情報を直接参照してください。</span><span class="sxs-lookup"><span data-stu-id="e4b8f-105">For information about the constraints of these different types of groups, you should refer directly to information about the XML Schema definition (XSD) language on the Web.</span></span> <span data-ttu-id="e4b8f-106">この情報へのリンクを参照してください。 [Web 上の XSD リソース](../core/xsd-resources-on-the-web.md)します。</span><span class="sxs-lookup"><span data-stu-id="e4b8f-106">For links to this information, see [XSD Resources on the Web](../core/xsd-resources-on-the-web.md).</span></span>  
  
 <span data-ttu-id="e4b8f-107">BizTalk エディターでは、属性の場合、グループ ノードもがサポートしています、**属性グループ**ノード。</span><span class="sxs-lookup"><span data-stu-id="e4b8f-107">BizTalk Editor also supports a group node for attributes, the **Attribute Group** node.</span></span> <span data-ttu-id="e4b8f-108">この種類のノードは、一連の属性から 1 回、定義して、1 つ以上に関連付けられます**レコード**スキーマ内のノード。</span><span class="sxs-lookup"><span data-stu-id="e4b8f-108">This type of node allows a set of attributes to be defined once, and then be associated with more than one **Record** node within the schema.</span></span>  
  
 <span data-ttu-id="e4b8f-109">構造体をスキーマに組み込むとき**レコード**ノードは既定では、子ノードの順序付けられたシーケンスを格納すると見なされを使用して表されます**シーケンス**の XSD 表記内の要素スキーマです。</span><span class="sxs-lookup"><span data-stu-id="e4b8f-109">When you build structure into your schema, **Record** nodes are assumed to contain ordered sequences of child nodes by default, and are represented by using **sequence** elements in the XSD representation of the schema.</span></span> <span data-ttu-id="e4b8f-110">グループ ノードの種類を変更するには変更することでその**Order Type**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="e4b8f-110">You can change the type of a group node by changing its **Order Type** property.</span></span>  
  
### <a name="to-insert-a-sequence-group-node-or-a-choice-group-node"></a><span data-ttu-id="e4b8f-111">シーケンス グループ ノードまたはグループの選択ノードを挿入するには</span><span class="sxs-lookup"><span data-stu-id="e4b8f-111">To insert a Sequence Group node or a Choice Group node</span></span>  
  
1.  <span data-ttu-id="e4b8f-112">スキーマ ツリー ビューで、選択、**レコード**ノードを挿入する、**シーケンス グループ**ノードまたは**グループの選択**ノード。</span><span class="sxs-lookup"><span data-stu-id="e4b8f-112">In the schema tree view, select the **Record** node in which you want to insert the **Sequence Group** node or the **Choice Group** node.</span></span>  
  
2.  <span data-ttu-id="e4b8f-113">**BizTalk**メニューで、**スキーマ ノードの挿入**、 をクリックし、**シーケンス グループ**または**グループの選択**必要に応じて、します。</span><span class="sxs-lookup"><span data-stu-id="e4b8f-113">On the **BizTalk** menu, point to **Insert Schema Node**, and then click **Sequence Group** or **Choice Group**, as appropriate.</span></span>  
  
### <a name="to-insert-an-all-group-node"></a><span data-ttu-id="e4b8f-114">すべてのグループ ノードを挿入するには</span><span class="sxs-lookup"><span data-stu-id="e4b8f-114">To insert an All Group node</span></span>  
  
1.  <span data-ttu-id="e4b8f-115">スキーマ ツリー ビューで選択、新しい**レコード**ノードを挿入する、**すべてのグループ**ノード。</span><span class="sxs-lookup"><span data-stu-id="e4b8f-115">In the schema tree view, select the new **Record** node in which you want to insert the **All Group** node.</span></span>  
  
2.  <span data-ttu-id="e4b8f-116">**BizTalk**メニューで、**スキーマ ノードの挿入**、 をクリックし、**すべてのグループ**します。</span><span class="sxs-lookup"><span data-stu-id="e4b8f-116">On the **BizTalk** menu, point to **Insert Schema Node**, and then click **All Group**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e4b8f-117">**すべてのグループ**選択は、BizTalk (またはショートカット) メニューで使用できるときに、関連する親**レコード**ノードは XSD での使用には、制約を満たしている、**すべて**要素。</span><span class="sxs-lookup"><span data-stu-id="e4b8f-117">The **All Group** choice is only available on the BizTalk (or shortcut) menu when the relevant parent **Record** node meets the constraints that XSD imposes on the use of the **all** element.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e4b8f-118">**すべてのグループ**選択肢である必要があります、**レコード**ノードがある基本データ型。</span><span class="sxs-lookup"><span data-stu-id="e4b8f-118">The **All Group** choice requires that the **Record** node have a base data type.</span></span> <span data-ttu-id="e4b8f-119">ノードのデータ型を提供する簡単な方法は、設定することです。 その**コンテンツの種類**に**複雑な**します。</span><span class="sxs-lookup"><span data-stu-id="e4b8f-119">A quick way to give the node a data type is to set its **Content Type** to **Complex**.</span></span>  
  
### <a name="to-insert-an-attribute-group-node"></a><span data-ttu-id="e4b8f-120">属性グループ ノードを挿入するには</span><span class="sxs-lookup"><span data-stu-id="e4b8f-120">To insert an Attribute Group node</span></span>  
  
1.  <span data-ttu-id="e4b8f-121">スキーマ ツリー ビューで、選択、**レコード**ノードを挿入する、**属性グループ**ノード。</span><span class="sxs-lookup"><span data-stu-id="e4b8f-121">In the schema tree view, select the **Record** node in which you want to insert the **Attribute Group** node.</span></span>  
  
2.  <span data-ttu-id="e4b8f-122">**BizTalk**メニューで、**スキーマ ノードの挿入**、 をクリックし、**属性グループ**します。</span><span class="sxs-lookup"><span data-stu-id="e4b8f-122">On the **BizTalk** menu, point to **Insert Schema Node**, and then click **Attribute Group**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e4b8f-123">新しく挿入の名前を変更する場合**属性グループ**ノードに新しい名前を入力、**グループ参照**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="e4b8f-123">If you want to change the name of the newly inserted **Attribute Group** node, type the new name in its **Group Reference** property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4b8f-124">参照</span><span class="sxs-lookup"><span data-stu-id="e4b8f-124">See Also</span></span>  
 [<span data-ttu-id="e4b8f-125">スキーマへのノードの挿入</span><span class="sxs-lookup"><span data-stu-id="e4b8f-125">Inserting Nodes into a Schema</span></span>](../core/inserting-nodes-into-a-schema.md)