---
title: 別のノードまたは種類への参照を作成する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c60be9ad-01a9-40e7-b43b-8c3d09bbb32f
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 643f39b9a42e2566f77371096d7305f56e11a328
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22250354"
---
# <a name="create-references-to-another-node-or-type"></a><span data-ttu-id="0c938-102">別のノードまたは種類への参照を作成します。</span><span class="sxs-lookup"><span data-stu-id="0c938-102">Create References to Another Node or Type</span></span>
<span data-ttu-id="0c938-103">グローバル ノードを使用するには再利用可能なデータ型を作成する — 構造の一部分-その構造が適切な場所で、スキーマ全体で使用できます。</span><span class="sxs-lookup"><span data-stu-id="0c938-103">You can use global nodes to create reusable data types—fragments of structure—that you can use throughout the schema wherever that structure is appropriate.</span></span> <span data-ttu-id="0c938-104">直接の子であるノードのみを使用できます、**スキーマ**グローバル型を作成するノードです。</span><span class="sxs-lookup"><span data-stu-id="0c938-104">You can only use nodes that are direct children of the **Schema** node to create global types.</span></span>  
  
 <span data-ttu-id="0c938-105">直接の子孫ではないノードのデータ型を使用して、循環参照を作成することも、**スキーマ**ノード。</span><span class="sxs-lookup"><span data-stu-id="0c938-105">You can also create cyclical references using the data types of nodes that are not direct descendants of the **Schema** node.</span></span> <span data-ttu-id="0c938-106">これは、スキーマの再帰構造を表す場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="0c938-106">This is useful for representing recursive structures in schemas.</span></span>  
  
 <span data-ttu-id="0c938-107">このトピックでは、さまざまな種類のグローバル ノードの操作手順とノードの参照方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="0c938-107">This topic provides step-by-step instructions for various types of global nodes and how to refer to them to use them.</span></span>  
  
 <span data-ttu-id="0c938-108">**グローバル宣言を作成します。**</span><span class="sxs-lookup"><span data-stu-id="0c938-108">**Creating Global Declarations**</span></span>  
  
 <span data-ttu-id="0c938-109">レコード、フィールド、または属性を使用して、グローバル型を作成できます。</span><span class="sxs-lookup"><span data-stu-id="0c938-109">You can create global types using records, fields or attributes.</span></span> <span data-ttu-id="0c938-110">レコードから作成されたグローバル型は、レコード内でのみ使用できます。フィールドから作成された型はフィールド内でのみ、属性から作成された型は属性内でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="0c938-110">Global types created from records may only be used in records, types created from fields only in fields, attribute types only in attributes.</span></span> <span data-ttu-id="0c938-111">次の手順は、グローバル宣言を定義して使用する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="0c938-111">The following procedures describe how to define and use global declarations.</span></span>  
  
## <a name="create-a-global-declaration-from-a-node"></a><span data-ttu-id="0c938-112">ノードからグローバル宣言を作成します。</span><span class="sxs-lookup"><span data-stu-id="0c938-112">Create a global declaration from a node</span></span>  
  
1.  <span data-ttu-id="0c938-113">選択、**レコード**、**フィールド属性**、または**フィールド要素**ノードの型をグローバルに使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="0c938-113">Select the **Record** , **Field Attribute**,or **Field Element** node whose type you want to make globally available.</span></span>  
  
2.  <span data-ttu-id="0c938-114">**プロパティ** ウィンドウに名前を入力、 **Data Structure Type**リストを複合型のグローバル名として使用され、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="0c938-114">In the **Properties** window, type a name in the **Data Structure Type** list that will be used as the global name for the complex type, and then press ENTER.</span></span>  
  
## <a name="create-a-globally-defined-sequence-group-node-choice-group-node-or-all-group-node"></a><span data-ttu-id="0c938-115">グローバルに定義されたシーケンス グループ ノード、グループの選択 ノードまたはすべてのグループ ノードを作成します。</span><span class="sxs-lookup"><span data-stu-id="0c938-115">Create a globally defined Sequence Group node, Choice Group node, or All Group node</span></span>  
  
1.  <span data-ttu-id="0c938-116">選択、**レコード**グローバル定義グループ ノードを挿入するノードです。</span><span class="sxs-lookup"><span data-stu-id="0c938-116">Select the **Record** node into which you want to insert the globally defined group node.</span></span>  
  
2.  <span data-ttu-id="0c938-117">**BizTalk**  メニューのをポイント**スキーマ ノードの挿入**、クリックして**シーケンス グループ**、**選択肢グループ**、または**すべてグループ** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0c938-117">On the **BizTalk** menu, point to **Insert Schema Node**, and then click **Sequence Group**, **Choice Group**, or **All Group**, as appropriate.</span></span>  
  
3.  <span data-ttu-id="0c938-118">新しく挿入したグループの構造を作成します。</span><span class="sxs-lookup"><span data-stu-id="0c938-118">Create a structure in the newly inserted group.</span></span> <span data-ttu-id="0c938-119">たとえば、挿入**レコード**または**フィールド要素**ノード グループ ノード内のデータの構造を表します。</span><span class="sxs-lookup"><span data-stu-id="0c938-119">For example, insert **Record** or **Field Element** nodes to express the structure of the data within the group node.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0c938-120">シーケンス グループ、**選択肢グループ**、および**すべてのグループ**ノードが XML 要素に対応し、そのため、含めることはできませんノードを含めることができますのみ**フィールド属性**ノード。</span><span class="sxs-lookup"><span data-stu-id="0c938-120">Sequence Group, **Choice Group**, and **All Group** nodes can only contain nodes that correspond to XML elements and therefore cannot contain **Field Attribute** nodes.</span></span>  
  
4.  <span data-ttu-id="0c938-121">手順 2. で挿入されたグループ ノードを選択します。</span><span class="sxs-lookup"><span data-stu-id="0c938-121">Select the group node inserted in step 2.</span></span>  
  
5.  <span data-ttu-id="0c938-122">[プロパティ] ウィンドウでをクリックして**Group Reference**値フィールドに名前を入力して、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="0c938-122">In the Properties window, click **Group Reference**, type a name into the value field, and then press ENTER.</span></span>  
  
     <span data-ttu-id="0c938-123">名前を提供することによって、 **Group Reference**プロパティ、グローバルに定義したグループ ノード、その後、このグローバルに定義された型 (構造) に、他のグループ ノードを関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="0c938-123">By providing a name in the **Group Reference** property, you have globally defined group node, after which you can associate other group nodes with this globally defined type (structure).</span></span>  
  
## <a name="create-a-globally-defined-attribute-group-node"></a><span data-ttu-id="0c938-124">グローバルに定義された属性グループ ノードを作成します。</span><span class="sxs-lookup"><span data-stu-id="0c938-124">Create a globally defined Attribute Group node</span></span>  
  
1.  <span data-ttu-id="0c938-125">選択、**レコード**グローバルに定義されたを挿入するノード**属性グループ**ノード。</span><span class="sxs-lookup"><span data-stu-id="0c938-125">Select the **Record** node into which you want to insert the globally defined **Attribute Group** node.</span></span>  
  
2.  <span data-ttu-id="0c938-126">**BizTalk**  メニューのをポイント**スキーマ ノードの挿入**、クリックして**属性グループ**です。</span><span class="sxs-lookup"><span data-stu-id="0c938-126">On the **BizTalk** menu, point to **Insert Schema Node**, and then click **Attribute Group**.</span></span>  
  
     <span data-ttu-id="0c938-127">これを追加、**属性グループ**ノードで選択した子ノードの最後を**レコード**ノード。</span><span class="sxs-lookup"><span data-stu-id="0c938-127">This adds an **Attribute Group** node to the end of the child nodes in the selected **Record** node.</span></span>  
  
3.  <span data-ttu-id="0c938-128">適切な追加**フィールド属性**または**属性グループ**ノード、**属性グループ**です。</span><span class="sxs-lookup"><span data-stu-id="0c938-128">Add the appropriate **Field Attribute** or **Attribute Group** nodes to your **Attribute Group**.</span></span>  
  
4.  <span data-ttu-id="0c938-129">必要に応じて、名前を変更する場合、**属性グループ**ノードで、選択、**属性グループ**ノードと変更、**グループ参照**プロパティを独自の新しい名前にします。</span><span class="sxs-lookup"><span data-stu-id="0c938-129">Optionally, if you want to rename the **Attribute Group** node, select the **Attribute Group** node and change its **Group Reference** property to a new name of your choosing.</span></span>  
  
     <span data-ttu-id="0c938-130">属性グループは、常にグローバルで、使用時に参照されます。</span><span class="sxs-lookup"><span data-stu-id="0c938-130">Attribute groups are always global and referenced from their point of use.</span></span>  
  
## <a name="use-a-type-or-group-that-has-been-globally-defined"></a><span data-ttu-id="0c938-131">種類またはグローバルに定義されているグループを使用します。</span><span class="sxs-lookup"><span data-stu-id="0c938-131">Use a type or group that has been globally defined</span></span>  
  
1.  <span data-ttu-id="0c938-132">グローバルに定義された型を使用するノードを選択します。</span><span class="sxs-lookup"><span data-stu-id="0c938-132">Select the node for which you want to use a globally defined type.</span></span>  
  
2.  <span data-ttu-id="0c938-133">[プロパティ] ウィンドウでのドロップダウン リストから、グローバルに定義された型を選択、 **Data Structure Type**プロパティ (**レコード**ノード)、**データ型**プロパティ (**フィールド要素**と**フィールド属性**ノード)、または**Group Reference** (**シーケンス グループ**、**選択肢グループ**、**すべてのグループ**、および**属性グループ**ノード)。</span><span class="sxs-lookup"><span data-stu-id="0c938-133">In the Properties window, select the globally defined type from the drop-down list for the **Data Structure Type** property (**Record** nodes), **Data Type** property (**Field Element** and **Field Attribute** nodes), or **Group Reference** (**Sequence Group**, **Choice Group**, **All Group**, and **Attribute Group** nodes).</span></span> <span data-ttu-id="0c938-134">これらのプロパティの詳細について[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。</span><span class="sxs-lookup"><span data-stu-id="0c938-134">More details on these properties [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
    > [!NOTE]
    >  <span data-ttu-id="0c938-135">グローバルに定義された型またはグループに対して後で変更を行う場合、グローバルに定義された型またはグループが表示される任意のスキーマの場所で変更できます。</span><span class="sxs-lookup"><span data-stu-id="0c938-135">Subsequent changes to the globally defined type or group can be made in any of the schema locations in which it appears.</span></span> <span data-ttu-id="0c938-136">1 つの任意の場所で変更を行うと、その変更内容は、グローバルに定義された型またはグループが表示される、すべての場所に適用されます。</span><span class="sxs-lookup"><span data-stu-id="0c938-136">These changes will be applied in all such locations as you make them in the single, arbitrary location.</span></span>  
  
 <span data-ttu-id="0c938-137">作成されたグローバル宣言は、1 回の手順では削除できません。</span><span class="sxs-lookup"><span data-stu-id="0c938-137">After you have created a global declaration, you cannot delete it in a single step.</span></span> <span data-ttu-id="0c938-138">ただしを使用して削除することができます、**グローバル データ型のクリーンアップ** ダイアログ ボックスで、次の手順を使用してスキーマを保存するとします。</span><span class="sxs-lookup"><span data-stu-id="0c938-138">However, you can delete it by using the **Cleanup Global DataTypes** dialog box when the schema is saved, using the following procedure.</span></span>  
  
## <a name="delete-a-global-declaration"></a><span data-ttu-id="0c938-139">グローバル宣言を削除します。</span><span class="sxs-lookup"><span data-stu-id="0c938-139">Delete a global declaration</span></span>  
  
1.  <span data-ttu-id="0c938-140">グローバル型またはグループが使用されるすべてのノードを削除するか、これらすべてのノードで別の型またはグループ (あるいはその組み合わせ) を使用するように指定します。</span><span class="sxs-lookup"><span data-stu-id="0c938-140">Delete all of the nodes where this global type or group is used, or specify a different type or group to be used in all of those nodes, or some combination thereof.</span></span> <span data-ttu-id="0c938-141">手順については、ノードを削除すると、次を参照してください。[ノードの削除](../core/how-to-delete-nodes.md)です。</span><span class="sxs-lookup"><span data-stu-id="0c938-141">For step-by-step instructions for deleting a node, see [Deleting Nodes](../core/how-to-delete-nodes.md).</span></span>  
  
2.  <span data-ttu-id="0c938-142">仕様を保存するときに、**グローバル データ型のクリーンアップ** ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0c938-142">Upon saving your specification, the **Cleanup Global DataTypes** dialog box appears.</span></span> <span data-ttu-id="0c938-143">クリックして、仕様から完全に削除するグローバル宣言を選択して**OK**です。</span><span class="sxs-lookup"><span data-stu-id="0c938-143">Select the global declaration you want to completely delete from your specification, and then click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0c938-144">**グローバル データ型のクリーンアップ**未使用のデータ型を持つスキーマを保存するたびに、ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0c938-144">The **Cleanup Global DataTypes** dialog box appears every time you save a schema with unused data types.</span></span> <span data-ttu-id="0c938-145">このダイアログ ボックスは、すべてのデータ型がスキーマで使用されている場合、またはスキーマを開いた以降にスキーマに変更を加えていない場合には、表示されません。後者の場合は、以前に保存した未使用のデータ型が含まれている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0c938-145">If this dialog box does not appear, either all data types are used somewhere in the schema or the schema has not been modified since it was opened (in the latter case, it might still contain unused data types that were previously retained.</span></span>  
  
## <a name="create-cyclical-references-to-another-node"></a><span data-ttu-id="0c938-146">別のノードに対する循環参照を作成します。</span><span class="sxs-lookup"><span data-stu-id="0c938-146">Create Cyclical References to Another Node</span></span>  
 <span data-ttu-id="0c938-147">ノードに対する循環参照を作成して、再帰的なスキーマ要素を表すことができます。</span><span class="sxs-lookup"><span data-stu-id="0c938-147">You can create cyclical references to a node to represent recursive schema elements.</span></span> <span data-ttu-id="0c938-148">これを行うには、囲みレコードによって型が定義されるノードを作成します。</span><span class="sxs-lookup"><span data-stu-id="0c938-148">You do this by creating a node whose type is defined by an enclosing record.</span></span> <span data-ttu-id="0c938-149">たとえば、同じ構造を持つ任意の数のエンベロープでラップされるインスタンス メッセージが必要な場合、</span><span class="sxs-lookup"><span data-stu-id="0c938-149">For example, consider an instance message that is wrapped in an arbitrary number of envelopes having the same structure.</span></span> <span data-ttu-id="0c938-150">循環参照を使用することにより、このようなインスタンス メッセージを定義するスキーマを作成できます。</span><span class="sxs-lookup"><span data-stu-id="0c938-150">Using cyclical references, you can create a schema that defines such instance messages.</span></span>  
  
### <a name="create-a-cyclical-reference"></a><span data-ttu-id="0c938-151">循環参照を作成します。</span><span class="sxs-lookup"><span data-stu-id="0c938-151">Create a cyclical reference</span></span>  
  
1.  <span data-ttu-id="0c938-152">選択、**レコード**再帰参照を作成するノードです。</span><span class="sxs-lookup"><span data-stu-id="0c938-152">Select a **Record** node for which you want to create a recursive reference.</span></span> <span data-ttu-id="0c938-153">このノードは、再帰構造の最上位を表します。</span><span class="sxs-lookup"><span data-stu-id="0c938-153">This is the node representing the top of the recursive structure.</span></span>  
  
2.  <span data-ttu-id="0c938-154">[プロパティ] ウィンドウであることを確認、 **Data Structure Type**値を持ちます。</span><span class="sxs-lookup"><span data-stu-id="0c938-154">In the Properties window, verify that the **Data Structure Type** has a value.</span></span>  
  
     <span data-ttu-id="0c938-155">ことを確認、**レコード**ノードに名前付き型には、それ自体が含まれている場合に、再帰的な構造が定義されているために、関連付けられている型が必要です。</span><span class="sxs-lookup"><span data-stu-id="0c938-155">Verifying that the **Record** node has a named type associated with it is necessary because recursive structures are defined when a type contains itself.</span></span> <span data-ttu-id="0c938-156">名前付きのグローバル型を入れ子構造で使用する場合のみ、型に型自体を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="0c938-156">Types can only contain themselves through nested use of named global types.</span></span>  
  
3.  <span data-ttu-id="0c938-157">子を選択して**レコード**ノード、または insert 子**レコード**ノード。</span><span class="sxs-lookup"><span data-stu-id="0c938-157">Select a child **Record** node or insert a child **Record** node.</span></span>  
  
4.  <span data-ttu-id="0c938-158">子の**レコード**[プロパティ] ウィンドウ内のノードで、 **Data Structure Type**一覧で、手順 2. で識別されるデータ構造を選択します。</span><span class="sxs-lookup"><span data-stu-id="0c938-158">For the child **Record** node, in the Properties window, in the **Data Structure Type** list, select the data structure identified in step 2.</span></span>  
  
> [!IMPORTANT]
>  - <span data-ttu-id="0c938-159">**Min Occurs**繰り返しノードのプロパティを 0 に設定する必要があります (**0**)。</span><span class="sxs-lookup"><span data-stu-id="0c938-159">The **Min Occurs** property for the repeating node must be set to zero (**0**).</span></span> <span data-ttu-id="0c938-160">いずれかに設定すると (**1**) 無限ループが発生します。</span><span class="sxs-lookup"><span data-stu-id="0c938-160">Setting it to one (**1**) causes an infinite loop.</span></span>  
>
>  - <span data-ttu-id="0c938-161">再帰要素を含むスキーマをインポートする場合、BizTalk エディターは、再帰要素が有効かどうかを自動的に確認しません。</span><span class="sxs-lookup"><span data-stu-id="0c938-161">If you import a schema that contains a recursive element, BizTalk Editor does not automatically check to ensure that the recursive element is valid.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c938-162">参照</span><span class="sxs-lookup"><span data-stu-id="0c938-162">See Also</span></span>  
 [<span data-ttu-id="0c938-163">スキーマ内のノードを管理します。</span><span class="sxs-lookup"><span data-stu-id="0c938-163">Managing the Nodes Within a Schema</span></span>](../core/managing-the-nodes-within-a-schema.md)