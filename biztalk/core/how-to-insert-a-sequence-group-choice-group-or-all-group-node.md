---
title: "シーケンス グループ、グループの選択、またはすべてのグループ ノードを挿入する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 19aee400-1369-4310-b1b4-1bfeb2643236
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e498eb5ec8e7aa1398cfb58732f978faa9d0b415
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-insert-a-sequence-group-choice-group-or-all-group-node"></a><span data-ttu-id="f01f1-102">シーケンス グループ、グループの選択、またはすべてのグループ ノードを挿入する方法</span><span class="sxs-lookup"><span data-stu-id="f01f1-102">How to Insert a Sequence Group, Choice Group, or All Group Node</span></span>
<span data-ttu-id="f01f1-103">BizTalk エディターは、要素の次の 3 つの種類のグループ ノードをサポートしています:**シーケンス グループ**、**選択肢グループ**、および**すべてのグループ**です。</span><span class="sxs-lookup"><span data-stu-id="f01f1-103">BizTalk Editor supports three types of group nodes for elements: **Sequence Group**, **Choice Group**, and **All Group**.</span></span> <span data-ttu-id="f01f1-104">これらの異なるグループ ノードを使用して、対応するインスタンス メッセージのグループの子ノードにさまざまな制約を適用できます。</span><span class="sxs-lookup"><span data-stu-id="f01f1-104">These different types of group nodes establish different constraints on the child nodes of the group in corresponding instance messages.</span></span> <span data-ttu-id="f01f1-105">これらの各グループにおける制約の詳細については、Web 上で XSD (XML Schema Definition) に関する情報を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f01f1-105">For information about the constraints of these different types of groups, you should refer directly to information about the XML Schema definition (XSD) language on the Web.</span></span> <span data-ttu-id="f01f1-106">この情報へのリンクを参照してください。 [Web 上の XSD リソース](../core/xsd-resources-on-the-web.md)です。</span><span class="sxs-lookup"><span data-stu-id="f01f1-106">For links to this information, see [XSD Resources on the Web](../core/xsd-resources-on-the-web.md).</span></span>  
  
 <span data-ttu-id="f01f1-107">BizTalk エディターでは、属性の場合、[グループ] ノードもがサポートしています、**属性グループ**ノード。</span><span class="sxs-lookup"><span data-stu-id="f01f1-107">BizTalk Editor also supports a group node for attributes, the **Attribute Group** node.</span></span> <span data-ttu-id="f01f1-108">この種類のノードは、一連の属性を 1 回、定義して、複数のいずれかに関連付ける**レコード**スキーマ内のノードです。</span><span class="sxs-lookup"><span data-stu-id="f01f1-108">This type of node allows a set of attributes to be defined once, and then be associated with more than one **Record** node within the schema.</span></span>  
  
 <span data-ttu-id="f01f1-109">スキーマ構造を作成するときに**レコード**ノードは既定では、子ノードの順序付けられたシーケンスを格納すると見なされを使用して表される**シーケンス**の XSD 表記内の要素スキーマです。</span><span class="sxs-lookup"><span data-stu-id="f01f1-109">When you build structure into your schema, **Record** nodes are assumed to contain ordered sequences of child nodes by default, and are represented by using **sequence** elements in the XSD representation of the schema.</span></span> <span data-ttu-id="f01f1-110">変更することで、[グループ] ノードの型を変更することができます、 **Order Type**プロパティです。</span><span class="sxs-lookup"><span data-stu-id="f01f1-110">You can change the type of a group node by changing its **Order Type** property.</span></span>  
  
### <a name="to-insert-a-sequence-group-node-or-a-choice-group-node"></a><span data-ttu-id="f01f1-111">[シーケンス グループ] ノードまたは [グループの選択] ノードを挿入するには</span><span class="sxs-lookup"><span data-stu-id="f01f1-111">To insert a Sequence Group node or a Choice Group node</span></span>  
  
1.  <span data-ttu-id="f01f1-112">スキーマ ツリー ビューで、選択、**レコード**ノードを挿入する、**シーケンス グループ**ノードまたは**選択肢グループ**ノード。</span><span class="sxs-lookup"><span data-stu-id="f01f1-112">In the schema tree view, select the **Record** node in which you want to insert the **Sequence Group** node or the **Choice Group** node.</span></span>  
  
2.  <span data-ttu-id="f01f1-113">**BizTalk**  メニューのをポイント**スキーマ ノードの挿入**、順にクリック**シーケンス グループ**または**選択肢グループ**、必要に応じて。</span><span class="sxs-lookup"><span data-stu-id="f01f1-113">On the **BizTalk** menu, point to **Insert Schema Node**, and then click **Sequence Group** or **Choice Group**, as appropriate.</span></span>  
  
### <a name="to-insert-an-all-group-node"></a><span data-ttu-id="f01f1-114">[すべてのグループ] ノードを挿入するには</span><span class="sxs-lookup"><span data-stu-id="f01f1-114">To insert an All Group node</span></span>  
  
1.  <span data-ttu-id="f01f1-115">スキーマ ツリー ビューで、新しい選択**レコード**ノードを挿入する、**すべてのグループ**ノード。</span><span class="sxs-lookup"><span data-stu-id="f01f1-115">In the schema tree view, select the new **Record** node in which you want to insert the **All Group** node.</span></span>  
  
2.  <span data-ttu-id="f01f1-116">**BizTalk**  メニューのをポイント**スキーマ ノードの挿入**、クリックして**すべてのグループ**です。</span><span class="sxs-lookup"><span data-stu-id="f01f1-116">On the **BizTalk** menu, point to **Insert Schema Node**, and then click **All Group**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f01f1-117">**すべてのグループ**選択は、BizTalk (またはショートカット) メニューで使用できるときに、関連する親**レコード**ノードは XSD での使用には、制約を満たしている、**すべて**要素。</span><span class="sxs-lookup"><span data-stu-id="f01f1-117">The **All Group** choice is only available on the BizTalk (or shortcut) menu when the relevant parent **Record** node meets the constraints that XSD imposes on the use of the **all** element.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f01f1-118">**すべてのグループ**選択肢では、する必要があります、**レコード**基本データ型であるノード。</span><span class="sxs-lookup"><span data-stu-id="f01f1-118">The **All Group** choice requires that the **Record** node have a base data type.</span></span> <span data-ttu-id="f01f1-119">設定するノードのデータ型を提供する簡単な方法は、その**コンテンツ タイプ**に**複雑な**します。</span><span class="sxs-lookup"><span data-stu-id="f01f1-119">A quick way to give the node a data type is to set its **Content Type** to **Complex**.</span></span>  
  
### <a name="to-insert-an-attribute-group-node"></a><span data-ttu-id="f01f1-120">[属性グループ] ノードを挿入するには</span><span class="sxs-lookup"><span data-stu-id="f01f1-120">To insert an Attribute Group node</span></span>  
  
1.  <span data-ttu-id="f01f1-121">スキーマ ツリー ビューで、選択、**レコード**ノードを挿入する、**属性グループ**ノード。</span><span class="sxs-lookup"><span data-stu-id="f01f1-121">In the schema tree view, select the **Record** node in which you want to insert the **Attribute Group** node.</span></span>  
  
2.  <span data-ttu-id="f01f1-122">**BizTalk**  メニューのをポイント**スキーマ ノードの挿入**、クリックして**属性グループ**です。</span><span class="sxs-lookup"><span data-stu-id="f01f1-122">On the **BizTalk** menu, point to **Insert Schema Node**, and then click **Attribute Group**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f01f1-123">新しく挿入されるの名前を変更する場合**属性グループ** ノードに新しい名前を入力、**グループ参照**プロパティです。</span><span class="sxs-lookup"><span data-stu-id="f01f1-123">If you want to change the name of the newly inserted **Attribute Group** node, type the new name in its **Group Reference** property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f01f1-124">参照</span><span class="sxs-lookup"><span data-stu-id="f01f1-124">See Also</span></span>  
 [<span data-ttu-id="f01f1-125">スキーマにノードを挿入</span><span class="sxs-lookup"><span data-stu-id="f01f1-125">Inserting Nodes into a Schema</span></span>](../core/inserting-nodes-into-a-schema.md)