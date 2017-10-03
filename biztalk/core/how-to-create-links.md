---
title: "リンクを作成する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 670b831f-be03-4612-93d5-a894f7bb3c11
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 01171ddeaab8424087e8f04c29fb747e9479c1eb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-create-links"></a><span data-ttu-id="b2ad0-102">リンクを作成する方法</span><span class="sxs-lookup"><span data-stu-id="b2ad0-102">How to Create Links</span></span>
<span data-ttu-id="b2ad0-103">リンクを作成する、**レコード**または**フィールド**ソース スキーマのノードに、**レコード**または**フィールド**送信先スキーマのノードは最も基本的なマップを作成するアクティビティ。</span><span class="sxs-lookup"><span data-stu-id="b2ad0-103">Creating a link from a **Record** or **Field** node in a source schema to a **Record** or **Field** node in a destination schema is the most basic activity in creating maps.</span></span> <span data-ttu-id="b2ad0-104">このトピックでは、いくつかのバリエーション (Functoid からのリンクや Functoid へのリンクなど) について、この操作の手順を説明します。</span><span class="sxs-lookup"><span data-stu-id="b2ad0-104">This topic provides step-by-step instructions for several variations of this activity, including creating links to and from functoids.</span></span> <span data-ttu-id="b2ad0-105">Functoid の使用に関する詳細については、次を参照してください。 [Functoid 作成複雑なマッピングを使用した](../core/using-functoids-to-create-more-complex-mappings.md)です。</span><span class="sxs-lookup"><span data-stu-id="b2ad0-105">For additional information about working with functoids, see [Using Functoids to Create More Complex Mappings](../core/using-functoids-to-create-more-complex-mappings.md).</span></span>  
  
 <span data-ttu-id="b2ad0-106">このトピックの手順は、BizTalk マップが既に開かれ、マップの送信元スキーマと送信先スキーマが選択されていることを前提にしています。</span><span class="sxs-lookup"><span data-stu-id="b2ad0-106">The instructions in this topic assume you already have a BizTalk map open, and that you have chosen source and destination schemas for the map.</span></span> <span data-ttu-id="b2ad0-107">詳細については、マップを開くと、マップのスキーマを選択する、次を参照してください。[マップ内でプロジェクトを管理する](../core/managing-maps-within-projects.md)です。</span><span class="sxs-lookup"><span data-stu-id="b2ad0-107">For more information about opening maps and choosing schemas for the map, see [Managing Maps Within Projects](../core/managing-maps-within-projects.md).</span></span>  
  
### <a name="to-create-links-between-field-and-record-nodes"></a><span data-ttu-id="b2ad0-108">[フィールド] ノードと [レコード] ノードの間のリンクを作成するには</span><span class="sxs-lookup"><span data-stu-id="b2ad0-108">To create links between Field and Record nodes</span></span>  
  
1.  <span data-ttu-id="b2ad0-109">BizTalk マッパーで、ドラッグ、**フィールド**または**レコード**する送信元スキーマ ツリーからノードを**フィールド**または**レコード**送信先スキーマのノードツリー。</span><span class="sxs-lookup"><span data-stu-id="b2ad0-109">In BizTalk Mapper, drag a **Field** or **Record** node from the source schema tree to a **Field** or **Record** node in the destination schema tree.</span></span>  
  
     <span data-ttu-id="b2ad0-110">**- または -**</span><span class="sxs-lookup"><span data-stu-id="b2ad0-110">**- Or -**</span></span>  
  
2.  <span data-ttu-id="b2ad0-111">BizTalk マッパーで、ドラッグ、**フィールド**または**レコード**を送信先スキーマ ツリーからノードを**フィールド**または**レコード**送信元スキーマ内のノードツリー。</span><span class="sxs-lookup"><span data-stu-id="b2ad0-111">In BizTalk Mapper, drag a **Field** or **Record** node from the destination schema tree to a **Field** or **Record** node in the source schema tree.</span></span>  
  
 <span data-ttu-id="b2ad0-112">リンクを作成するときは、次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="b2ad0-112">There are several things to consider when creating links:</span></span>  
  
-   <span data-ttu-id="b2ad0-113">データ型、**フィールド**または**レコード**送信元スキーマ ツリー内のノードのデータ型と一致する必要があります、**フィールド**または**レコード**先ノード送信先スキーマ ツリーにリンクされます。</span><span class="sxs-lookup"><span data-stu-id="b2ad0-113">The data type of a **Field** or **Record** node in the source schema tree should match the data type of a **Field** or **Record** node to which it is linked in the destination schema tree.</span></span>  
  
-   <span data-ttu-id="b2ad0-114">場合、**フィールド**または**レコード**送信元スキーマのノードは省略可能、および対応する要素または属性を含まない、特定の送信元インスタンス メッセージ、BizTalk マッパーは作成されません、送信先インスタンス メッセージの対応する要素または属性場合でも、**フィールド**または**レコード**ノード マップでそれらの間の直接リンクを設定します。</span><span class="sxs-lookup"><span data-stu-id="b2ad0-114">If a **Field** or **Record** node in the source schema is optional, and a particular source instance message does not contain the corresponding element or attribute, BizTalk Mapper will not create a corresponding element or attribute in the destination instance message, even if the **Field** or **Record** nodes have a direct link between them in the map.</span></span>  
  
-   <span data-ttu-id="b2ad0-115">リンクすることはできません、**フィールド**または**レコード**関連付けられている定数値を持つ送信先スキーマのノードです。</span><span class="sxs-lookup"><span data-stu-id="b2ad0-115">You cannot link to a **Field** or **Record** node in the destination schema that has a constant value associated with it.</span></span> <span data-ttu-id="b2ad0-116">その一方で、必要なにリンクできます**フィールド**または**レコード**関連付けられている既定値を持つ送信先スキーマのノードです。</span><span class="sxs-lookup"><span data-stu-id="b2ad0-116">On the other hand, you can link to a required **Field** or **Record** node in the destination schema that has a default value associated with it.</span></span> <span data-ttu-id="b2ad0-117">マップをテストする場合、既定値が使用されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="b2ad0-117">Note, however, that when you test the map, the default value will be used.</span></span>  
  
-   <span data-ttu-id="b2ad0-118">またはからには、リンクを作成することはできません、 **Any 要素**、**すべての属性**、**シーケンス グループ**、または**選択肢グループ**ノード。</span><span class="sxs-lookup"><span data-stu-id="b2ad0-118">You cannot create a link to or from the **Any Element**, **Any Attribute**, **Sequence Group**, or **Choice Group** nodes.</span></span> <span data-ttu-id="b2ad0-119">これらの種類のノードの詳細については、次のトピックを参照して、参照してください[任意の要素ノード](../core/any-element-nodes.md)、[シーケンス グループ ノード](../core/sequence-group-nodes.md)または[選択肢グループ ノード](../core/choice-group-nodes.md)です。</span><span class="sxs-lookup"><span data-stu-id="b2ad0-119">For more information about these types of nodes, see the following topics, see [Any Element Nodes](../core/any-element-nodes.md), [Sequence Group Nodes](../core/sequence-group-nodes.md) or [Choice Group Nodes](../core/choice-group-nodes.md).</span></span>  
  
-   <span data-ttu-id="b2ad0-120">必要に応じて、スキーマ ツリーを展開し、マップするフィールドを表示します。</span><span class="sxs-lookup"><span data-stu-id="b2ad0-120">You may need to expand the schema trees to view the fields that you want to map.</span></span> <span data-ttu-id="b2ad0-121">詳細については、次を参照してください。[を展開して、スキーマ ツリーを折りたたむ方法](https://msdn.microsoft.com/library/ee253802(v=bts.10).aspx)です。</span><span class="sxs-lookup"><span data-stu-id="b2ad0-121">For more information, see [How to Expand and Collapse the Schema Trees](https://msdn.microsoft.com/library/ee253802(v=bts.10).aspx).</span></span>  
  
#### <a name="to-create-links-between-record-or-field-nodes-and-functoids"></a><span data-ttu-id="b2ad0-122">[レコード] ノードまたは [フィールド] ノードと Functoid の間のリンクを作成するには</span><span class="sxs-lookup"><span data-stu-id="b2ad0-122">To create links between Record or Field nodes and functoids</span></span>  
  
1.  <span data-ttu-id="b2ad0-123">BizTalk マッパーで、ドラッグ、**レコード**または**フィールド**グリッド ページの functoid に送信元または送信先スキーマのノードです。</span><span class="sxs-lookup"><span data-stu-id="b2ad0-123">In BizTalk Mapper, drag a **Record** or **Field** node from the source or destination schema to a functoid in a grid page.</span></span>  
  
     <span data-ttu-id="b2ad0-124">**- または -**</span><span class="sxs-lookup"><span data-stu-id="b2ad0-124">**- Or -**</span></span>  
  
2.  <span data-ttu-id="b2ad0-125">グリッド ページで、functoid をドラッグ、**レコード**または**フィールド**送信元または送信先スキーマのノードです。</span><span class="sxs-lookup"><span data-stu-id="b2ad0-125">Drag the functoid from a grid page to a **Record** or **Field** node in the source or destination schema.</span></span>  
  
     <span data-ttu-id="b2ad0-126">間のリンクを作成する場合、**レコード**または**フィールド**ノードで、送信元スキーマと、functoid、functoid への入力を作成します。</span><span class="sxs-lookup"><span data-stu-id="b2ad0-126">When you create a link between a **Record** or **Field** node in the source schema and a functoid, you are creating an input to that functoid.</span></span> <span data-ttu-id="b2ad0-127">間のリンクを作成する場合、**レコード**または**フィールド**ノードで、送信先スキーマと、functoid、functoid からの出力を作成します。</span><span class="sxs-lookup"><span data-stu-id="b2ad0-127">When you create a link between a **Record** or **Field** node in the destination schema and a functoid, you are creating an output from that functoid.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="b2ad0-128">Functoid 間にリンクすることはできませんと**Any 要素**ノードまたは**すべての属性**ノード。</span><span class="sxs-lookup"><span data-stu-id="b2ad0-128">You cannot link between a functoid and an **Any Element** node or an **Any Attribute** node.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b2ad0-129">間のリンクを追加する前に、グリッド ページに functoid に追加すること最初にする必要があります、**レコード**または**フィールド**ノードとその functoid です。</span><span class="sxs-lookup"><span data-stu-id="b2ad0-129">You must first add a functoid to a grid page before you can add a link between a **Record** or **Field** node and that functoid.</span></span> <span data-ttu-id="b2ad0-130">グリッド ページに functoid を追加する方法の詳細については、次を参照してください。[マップに基本 Functoid を追加する方法](../core/how-to-add-basic-functoids-to-a-map.md)です。</span><span class="sxs-lookup"><span data-stu-id="b2ad0-130">For more information about adding functoids to a grid page, see [How to Add Basic Functoids to a Map](../core/how-to-add-basic-functoids-to-a-map.md).</span></span> <span data-ttu-id="b2ad0-131">参照してください[マップに高度な Functoid を追加する](../core/adding-advanced-functoids-to-a-map.md)です。</span><span class="sxs-lookup"><span data-stu-id="b2ad0-131">Also see [Adding Advanced Functoids to a Map](../core/adding-advanced-functoids-to-a-map.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b2ad0-132">リンクすることはできません、**フィールド**関連付けられている定数値を持つ送信先スキーマのノードです。</span><span class="sxs-lookup"><span data-stu-id="b2ad0-132">You cannot link to a **Field** node in the destination schema that has a constant value associated with it.</span></span> <span data-ttu-id="b2ad0-133">その一方で、必要なにリンクできます**フィールド**関連付けられている既定値を持つ送信先スキーマのノードです。</span><span class="sxs-lookup"><span data-stu-id="b2ad0-133">On the other hand, you can link to a required **Field** node in the destination schema that has a default value associated with it.</span></span> <span data-ttu-id="b2ad0-134">マップをテストする場合、既定値が使用されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="b2ad0-134">Note, however, that when you test the map, the default value will be used.</span></span>  
  
#### <a name="to-create-links-between-functoids"></a><span data-ttu-id="b2ad0-135">Functoid 間のリンクを作成するには</span><span class="sxs-lookup"><span data-stu-id="b2ad0-135">To create links between functoids</span></span>  
  
-   <span data-ttu-id="b2ad0-136">BizTalk マッパーのグリッド ページで、対象の Functoid を別の Functoid にドラッグします。</span><span class="sxs-lookup"><span data-stu-id="b2ad0-136">In BizTalk Mapper, drag one functoid to another functoid in a grid page.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b2ad0-137">リンクは、グリッド ページ内で左から右へと処理されます。</span><span class="sxs-lookup"><span data-stu-id="b2ad0-137">Links are processed left-to-right in a grid page.</span></span> <span data-ttu-id="b2ad0-138">対象の Functoid のすぐ上、またはすぐ下にある Functoid とのリンクは作成できません。</span><span class="sxs-lookup"><span data-stu-id="b2ad0-138">You cannot make a link from one functoid to another functoid directly above or below it.</span></span> <span data-ttu-id="b2ad0-139">Functoid 間のリンクは、Functoid の左へのリンクが出力、右へのリンクが入力と見なされます。</span><span class="sxs-lookup"><span data-stu-id="b2ad0-139">Links between functoids are interpreted such that a link signifies output from the functoid to the left and input to the functoid to the right.</span></span>  
  
### <a name="to-change-the-endpoint-of-a-link"></a><span data-ttu-id="b2ad0-140">リンクのエンドポイントを変更するには</span><span class="sxs-lookup"><span data-stu-id="b2ad0-140">To change the endpoint of a link</span></span>  
 <span data-ttu-id="b2ad0-141">マップでは、リンクのエンドポイントをドラッグして、別のノードまたは Functoid にドロップできます。</span><span class="sxs-lookup"><span data-stu-id="b2ad0-141">In a map, you can drag an endpoint of a link and drop it over another node or functoid.</span></span>  
  
 <span data-ttu-id="b2ad0-142">リンクのエンドポイントを変更するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="b2ad0-142">To change the endpoint of a link:</span></span>  
  
1.  <span data-ttu-id="b2ad0-143">送信元または送信先のノード/Functoid を変更するリンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="b2ad0-143">Click the link for which you want to change the source or destination node/functoid.</span></span> <span data-ttu-id="b2ad0-144">リンクのエンドポイントが太く表示されます。</span><span class="sxs-lookup"><span data-stu-id="b2ad0-144">The endpoints of the link become bold.</span></span>  
  
2.  <span data-ttu-id="b2ad0-145">太く表示されているエンドポイントのいずれかをマウス キーで押しながら、リンクを目的のノード/Functoid にドラッグします。</span><span class="sxs-lookup"><span data-stu-id="b2ad0-145">Hold down the mouse key on any of the bold endpoints and drag the link to the desired node/functoid.</span></span> <span data-ttu-id="b2ad0-146">これにより、リンクが以前のノード/Functoid から新しいノード/Functoid に変わります。</span><span class="sxs-lookup"><span data-stu-id="b2ad0-146">This changes the linking from the previous node/functoid to the new node/functoid.</span></span>  
  
 <span data-ttu-id="b2ad0-147">ただし、次のような無効なリンクに対してこの操作を実行することはできません。</span><span class="sxs-lookup"><span data-stu-id="b2ad0-147">However, you cannot perform this operation for invalid linking, such as:</span></span>  
  
-   <span data-ttu-id="b2ad0-148">日付/時刻 Functoid への入力としてのリンクの追加。</span><span class="sxs-lookup"><span data-stu-id="b2ad0-148">Adding a link as an input to Date/Time functoids.</span></span> <span data-ttu-id="b2ad0-149">日付/時刻 Functoid には、入力リンクは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="b2ad0-149">The Date/Time functoids do not need any input links.</span></span>  
  
-   <span data-ttu-id="b2ad0-150">中間 Functoid からのリンクの複製。</span><span class="sxs-lookup"><span data-stu-id="b2ad0-150">Duplicating links from intermediate functoids.</span></span>  
  
     <span data-ttu-id="b2ad0-151">Node1 を Node2 にリンクし、Node1 から Node3 にもリンクしている場合、Node2 のリンクのエンドポイントをドラッグして変更し、Node3 にリンクすることはできません。</span><span class="sxs-lookup"><span data-stu-id="b2ad0-151">If you link Node1 to Node2, and also from Node1 to Node3, you cannot drag the endpoint of the link at Node2 to change and link to Node3.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2ad0-152">参照</span><span class="sxs-lookup"><span data-stu-id="b2ad0-152">See Also</span></span>  
 [<span data-ttu-id="b2ad0-153">リンクを使用してレコードを指定してフィールドのマッピング</span><span class="sxs-lookup"><span data-stu-id="b2ad0-153">Using Links to Specify Record and Field Mappings</span></span>](../core/using-links-to-specify-record-and-field-mappings.md)