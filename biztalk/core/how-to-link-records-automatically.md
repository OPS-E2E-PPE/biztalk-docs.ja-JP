---
title: レコードを自動的にリンクする方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: dc2926c7-07c2-45d1-afde-d3f894f6b88d
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dc5ab4e18a291321247655101d32d2bf7e35ff92
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254850"
---
# <a name="how-to-link-records-automatically"></a><span data-ttu-id="a08ed-102">レコードを自動的にリンクする方法</span><span class="sxs-lookup"><span data-stu-id="a08ed-102">How to Link Records Automatically</span></span>
<span data-ttu-id="a08ed-103">BizTalk マッパーでは、ショートカットを使用して、送信元スキーマと送信先スキーマの 2 つのレコード要素間のリンクを効率的に作成することができます。</span><span class="sxs-lookup"><span data-stu-id="a08ed-103">The BizTalk Mapper provides you with just-in-time assistance, through a shortcut menu, when you create links between two record elements of source and destination schemas.</span></span> <span data-ttu-id="a08ed-104">このトピックでは、ショートカット メニューを使用してリンク操作を実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a08ed-104">This topic provides information about how to use the shortcut menu to perform the linking operations.</span></span>  
  
 <span data-ttu-id="a08ed-105">レコード間のリンクは、次の方法で自動的に作成できます。</span><span class="sxs-lookup"><span data-stu-id="a08ed-105">You can create record-to-record links automatically in the following ways:</span></span>  
  
-   <span data-ttu-id="a08ed-106">**直接リンクです。**</span><span class="sxs-lookup"><span data-stu-id="a08ed-106">**Direct Link.**</span></span> <span data-ttu-id="a08ed-107">この方法を使用すると、BizTalk マッパーは送信元スキーマのレコードを送信先スキーマの選択されたレコードにリンクします。</span><span class="sxs-lookup"><span data-stu-id="a08ed-107">Using this technique, the BizTalk Mapper links the record from source schema to the selected record in the destination schema.</span></span>  
  
-   <span data-ttu-id="a08ed-108">**構造によるリンクします。**</span><span class="sxs-lookup"><span data-stu-id="a08ed-108">**Link by Structure.**</span></span> <span data-ttu-id="a08ed-109">この手法を使用して、BizTalk マッパーに一致する、**レコード**と**フィールド**内のノード、**レコード**これらの構造に従って、リンクされているノード**レコード**その構造内の対応するノードの名前に関係なく、ノード。</span><span class="sxs-lookup"><span data-stu-id="a08ed-109">Using this technique, the BizTalk Mapper attempts to match the **Record** and **Field** nodes within the **Record** nodes being linked according to the structures of those **Record** nodes, regardless of names of the corresponding nodes within those structures.</span></span>  
  
-   <span data-ttu-id="a08ed-110">**名前によるリンクします。**</span><span class="sxs-lookup"><span data-stu-id="a08ed-110">**Link By Name.**</span></span> <span data-ttu-id="a08ed-111">この手法を使用して、BizTalk マッパーに一致する、**レコード**と**フィールド**内のノード、**レコード**ノードの名前に従って、リンクされている、内の構造に関係なく、ノードを対応する、**レコード**リンクされているノードです。</span><span class="sxs-lookup"><span data-stu-id="a08ed-111">Using this technique, the BizTalk Mapper attempts to match the **Record** and **Field** nodes within the **Record** nodes being linked according to the names of the corresponding nodes, regardless of their structure, within the **Record** nodes being linked.</span></span>  
  
-   <span data-ttu-id="a08ed-112">**一括コピーします。**</span><span class="sxs-lookup"><span data-stu-id="a08ed-112">**Mass Copy.**</span></span> <span data-ttu-id="a08ed-113">**一括コピー** functoid を含むスキーマを使用して、マップを有効に**任意**と**anyAttribute**要素。</span><span class="sxs-lookup"><span data-stu-id="a08ed-113">The **Mass Copy** functoid enables your maps to use schemas that include **any** and **anyAttribute** elements.</span></span> <span data-ttu-id="a08ed-114">BizTalk マッパーで使用できる functoid の詳細については、次を参照してください。 [Functoid 作成複雑なマッピングを使用した](../core/using-functoids-to-create-more-complex-mappings.md)です。</span><span class="sxs-lookup"><span data-stu-id="a08ed-114">For information about the functoids available in BizTalk Mapper, see [Using Functoids to Create More Complex Mappings](../core/using-functoids-to-create-more-complex-mappings.md).</span></span>  
  
 <span data-ttu-id="a08ed-115">ショートカット メニューを使用するには、リンクがサブ階層親ノードから開始され、別のサブ階層親ノードで終了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a08ed-115">To use the shortcut menu, a link must originate from a sub-hierarchy parent node and must end on another sub-hierarchy parent node.</span></span> <span data-ttu-id="a08ed-116">ショートカット メニューを使用すると、2 つのスキーマ ノード間でどの種類のリンクを作成すべきかがわかります。</span><span class="sxs-lookup"><span data-stu-id="a08ed-116">The shortcut menu assists in what type of links should be created between the two schema nodes.</span></span> <span data-ttu-id="a08ed-117">次に、ショートカット メニューで使用できるオプションの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="a08ed-117">The following is a list of options available on the shortcut menu.</span></span>  
  
|<span data-ttu-id="a08ed-118">マップ元</span><span class="sxs-lookup"><span data-stu-id="a08ed-118">Map from</span></span>|<span data-ttu-id="a08ed-119">マップ先</span><span class="sxs-lookup"><span data-stu-id="a08ed-119">Map to</span></span>|<span data-ttu-id="a08ed-120">リンク動作</span><span class="sxs-lookup"><span data-stu-id="a08ed-120">Link Behavior</span></span>|  
|--------------|------------|-------------------|  
|<span data-ttu-id="a08ed-121">フィールド</span><span class="sxs-lookup"><span data-stu-id="a08ed-121">Field</span></span>|<span data-ttu-id="a08ed-122">フィールド</span><span class="sxs-lookup"><span data-stu-id="a08ed-122">Field</span></span>|<span data-ttu-id="a08ed-123">直接リンク</span><span class="sxs-lookup"><span data-stu-id="a08ed-123">Direct link</span></span>|  
|<span data-ttu-id="a08ed-124">レコード</span><span class="sxs-lookup"><span data-stu-id="a08ed-124">Record</span></span>|<span data-ttu-id="a08ed-125">フィールド</span><span class="sxs-lookup"><span data-stu-id="a08ed-125">Field</span></span>|<span data-ttu-id="a08ed-126">直接リンク</span><span class="sxs-lookup"><span data-stu-id="a08ed-126">Direct link</span></span>|  
|<span data-ttu-id="a08ed-127">フィールド</span><span class="sxs-lookup"><span data-stu-id="a08ed-127">Field</span></span>|<span data-ttu-id="a08ed-128">レコード</span><span class="sxs-lookup"><span data-stu-id="a08ed-128">Record</span></span>|<span data-ttu-id="a08ed-129">直接リンク</span><span class="sxs-lookup"><span data-stu-id="a08ed-129">Direct link</span></span>|  
|<span data-ttu-id="a08ed-130">レコード</span><span class="sxs-lookup"><span data-stu-id="a08ed-130">Record</span></span>|<span data-ttu-id="a08ed-131">レコード</span><span class="sxs-lookup"><span data-stu-id="a08ed-131">Record</span></span>|<span data-ttu-id="a08ed-132">ショートカット メニューが表示される</span><span class="sxs-lookup"><span data-stu-id="a08ed-132">Shortcut menu appears</span></span>|  
  
## <a name="prerequisites"></a><span data-ttu-id="a08ed-133">前提条件</span><span class="sxs-lookup"><span data-stu-id="a08ed-133">Prerequisites</span></span>  
 <span data-ttu-id="a08ed-134">これらの操作では、BizTalk マッパーが実行されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="a08ed-134">These operations require that the BizTalk Mapper is running.</span></span>  
  
### <a name="to-link-the-record-elements-directly"></a><span data-ttu-id="a08ed-135">レコード要素を直接リンクするには</span><span class="sxs-lookup"><span data-stu-id="a08ed-135">To link the record elements directly</span></span>  
  
1.  <span data-ttu-id="a08ed-136">ソース スキーマのサブ階層の親ノードからマウスをドラッグし、ターゲット スキーマのサブ階層の親ノードのところでドロップします。</span><span class="sxs-lookup"><span data-stu-id="a08ed-136">Drag the mouse from a sub-hierarchy parent node in source schema, and then drop it to the sub-hierarchy parent node in the target schema.</span></span>  
  
2.  <span data-ttu-id="a08ed-137">ショートカット メニューをクリックして**直接リンク**です。</span><span class="sxs-lookup"><span data-stu-id="a08ed-137">On the shortcut menu, click **Direct Link**.</span></span> <span data-ttu-id="a08ed-138">次の図に、選択した送信元ノードからターゲット ノードへの直接リンクを示します。</span><span class="sxs-lookup"><span data-stu-id="a08ed-138">The following figure shows a direct link appearing from the selected source node to the target node.</span></span>  
  
     <span data-ttu-id="a08ed-139">![送信元ノードからターゲット ノードへの直接リンク](../core/media/linkrecordelements-directly.gif "Linkrecordelements_directly")</span><span class="sxs-lookup"><span data-stu-id="a08ed-139">![Direct link from source node to target node](../core/media/linkrecordelements-directly.gif "Linkrecordelements_directly")</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="a08ed-140">直接リンクは、送信元スキーマのサブ階層親ノードからターゲット スキーマの非サブ階層親ノードに適用できます。</span><span class="sxs-lookup"><span data-stu-id="a08ed-140">You can place a direct link from a sub-hierarchy parent node in source schema to a non-sub-hierarchy parent node in target schema.</span></span> <span data-ttu-id="a08ed-141">次の図に、送信元スキーマの親ノードである "Root" からターゲット スキーマの "Root" の子ノードである "Record1" への直接リンクを示します。</span><span class="sxs-lookup"><span data-stu-id="a08ed-141">The following figure shows a direct link from “Root” that is a parent node in source schema to “Record1” that is a child to “Root” in target schema.</span></span>  
  
     <span data-ttu-id="a08ed-142">![レコード要素の直接リンク](../core/media/linkrecordelements-directly2.gif "Linkrecordelements_directly2")</span><span class="sxs-lookup"><span data-stu-id="a08ed-142">![Linking record elements directly](../core/media/linkrecordelements-directly2.gif "Linkrecordelements_directly2")</span></span>  
  
### <a name="to-link-the-record-elements-by-structure"></a><span data-ttu-id="a08ed-143">レコード要素を構造によってリンクするには</span><span class="sxs-lookup"><span data-stu-id="a08ed-143">To link the record elements by structure</span></span>  
  
1.  <span data-ttu-id="a08ed-144">ソース スキーマのサブ階層の親ノードからマウスをドラッグし、ターゲット スキーマのサブ階層の親ノードのところでドロップします。</span><span class="sxs-lookup"><span data-stu-id="a08ed-144">Drag the mouse from a sub-hierarchy parent node in source schema, and then drop it to the sub-hierarchy parent node in the target schema.</span></span>  
  
2.  <span data-ttu-id="a08ed-145">ショートカット メニューをクリックして**構造によるリンク**です。</span><span class="sxs-lookup"><span data-stu-id="a08ed-145">On the shortcut menu, click **Link by Structure**.</span></span> <span data-ttu-id="a08ed-146">BizTalk マッパーが一致する、**レコード**と**フィールド**内のノード、**レコード**の構造に従って、リンクされているノード**レコード**その構造内の対応するノードの名前に関係なく、ノード。</span><span class="sxs-lookup"><span data-stu-id="a08ed-146">The BizTalk Mapper matches the **Record** and **Field** nodes within the **Record** nodes being linked according to the structure of those **Record** nodes, regardless of names of the corresponding nodes within those structures.</span></span>  
  
     <span data-ttu-id="a08ed-147">![リンクのレコード要素 &#95; 構造体で](../core/media/linkrecordelements-bystructure.gif "Linkrecordelements_bystructure")</span><span class="sxs-lookup"><span data-stu-id="a08ed-147">![Link record elements&#95;by structure](../core/media/linkrecordelements-bystructure.gif "Linkrecordelements_bystructure")</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="a08ed-148">送信元スキーマのサブ階層親ノードからターゲット スキーマの非サブ階層親ノードを、構造によってリンクすると、BizTalk マッパーは送信元の親ノードの子ノードをターゲットの親ノードの子ノードにそれぞれマップします。</span><span class="sxs-lookup"><span data-stu-id="a08ed-148">When you try to link a sub-hierarchy parent node in source schema to a non-sub-hierarchy parent node in target schema, by structure, the BizTalk Mapper maps the children of the source parent node to the children of the target parent node, respectively.</span></span> <span data-ttu-id="a08ed-149">次の図に、構造によるリンクを示します。</span><span class="sxs-lookup"><span data-stu-id="a08ed-149">The following figure shows the linking by structure.</span></span>  
  
     <span data-ttu-id="a08ed-150">![構造によるレコード要素のリンク](../core/media/linkrecordelements-bystructure2.gif "Linkrecordelements_bystructure2")</span><span class="sxs-lookup"><span data-stu-id="a08ed-150">![Linking record elements by structure](../core/media/linkrecordelements-bystructure2.gif "Linkrecordelements_bystructure2")</span></span>  
  
### <a name="to-link-the-record-elements-by-name"></a><span data-ttu-id="a08ed-151">レコード要素を名前によってリンクするには</span><span class="sxs-lookup"><span data-stu-id="a08ed-151">To link the record elements by name</span></span>  
  
1.  <span data-ttu-id="a08ed-152">ソース スキーマのサブ階層の親ノードからマウスをドラッグし、ターゲット スキーマのサブ階層の親ノードのところでドロップします。</span><span class="sxs-lookup"><span data-stu-id="a08ed-152">Drag the mouse from a sub-hierarchy parent node in source schema, and then drop it to the sub-hierarchy parent node in the target schema.</span></span>  
  
2.  <span data-ttu-id="a08ed-153">ショートカット メニューをクリックして**名前によるリンク**です。</span><span class="sxs-lookup"><span data-stu-id="a08ed-153">On the shortcut menu, click **Link by Name**.</span></span> <span data-ttu-id="a08ed-154">BizTalk マッパーが一致するように、**レコード**と**フィールド**内のノード、**レコード**に関係なく、対応するノードの名前に従って、リンクされているノードその構造内で、**レコード**リンクしているノード。</span><span class="sxs-lookup"><span data-stu-id="a08ed-154">The BizTalk Mapper attempts to match the **Record** and **Field** nodes within the **Record** nodes being linked according to the names of the corresponding nodes, regardless of their structure, within the **Record** nodes to which you are linking.</span></span>  
  
     <span data-ttu-id="a08ed-155">![名前によるレコード要素のリンク](../core/media/linkrecordelements-byname.gif "Linkrecordelements_byname")</span><span class="sxs-lookup"><span data-stu-id="a08ed-155">![Linking record elements by name](../core/media/linkrecordelements-byname.gif "Linkrecordelements_byname")</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="a08ed-156">名前によるリンクは、送信元スキーマのサブ階層親ノードからターゲット スキーマの非サブ階層親ノードに適用できます。</span><span class="sxs-lookup"><span data-stu-id="a08ed-156">You can link a sub-hierarchy parent node in source schema to a non-sub-hierarchy parent node in target schema, by name.</span></span> <span data-ttu-id="a08ed-157">BizTalk マッパーは、送信元ノードの子ノードの名前とターゲット ノードの子ノードの名前を照合します。</span><span class="sxs-lookup"><span data-stu-id="a08ed-157">The BizTalk Mapper matches the names of the children of source node with the children of target node.</span></span> <span data-ttu-id="a08ed-158">一致する子ノードが検出されると、それぞれの子ノード間にリンクが確立されます。</span><span class="sxs-lookup"><span data-stu-id="a08ed-158">If it finds identical children, then a link is established between the respective children.</span></span> <span data-ttu-id="a08ed-159">次の図に、この概念を示します。</span><span class="sxs-lookup"><span data-stu-id="a08ed-159">The following figure explains this concept.</span></span>  
  
## <a name="to-link-using-a-mass-copy-functoid"></a><span data-ttu-id="a08ed-160">一括コピー Functoid を使用してリンクするには</span><span class="sxs-lookup"><span data-stu-id="a08ed-160">To link using a mass copy functoid</span></span>  
 <span data-ttu-id="a08ed-161">**一括コピー** functoid を含むスキーマを使用して、マップを有効に**任意**と**anyAttribute**要素。</span><span class="sxs-lookup"><span data-stu-id="a08ed-161">The **Mass Copy** functoid enables your maps to use schemas that include **any** and **anyAttribute** elements.</span></span> <span data-ttu-id="a08ed-162">これらの要素は、基本的に XML スキーマ定義言語に提供されているワイルドカードで、不明な構造や属性に一致します。</span><span class="sxs-lookup"><span data-stu-id="a08ed-162">These elements are, in essence, wildcards provided in the XML Schema definition language to match unknown structures or attributes.</span></span>  
  
 <span data-ttu-id="a08ed-163">不明な構造体を使用してデータを処理できることに加えて、**一括コピー** functoid では、スキーマ開発を簡略化することができます: 処理されるスキーマの部分のみを詳細に指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a08ed-163">In addition to handling data with unknown structure, the **Mass Copy** functoid enables you to simplify schema development: only the portions of a schema that will be processed need to be specified in detail.</span></span>  
  
 <span data-ttu-id="a08ed-164">![一括コピー functoid によるレコード要素のリンク](../core/media/linkrecordelements-masscopyfunctoid.gif "Linkrecordelements_MassCopyfunctoid")</span><span class="sxs-lookup"><span data-stu-id="a08ed-164">![Linking record elements by Mass Copy functoid](../core/media/linkrecordelements-masscopyfunctoid.gif "Linkrecordelements_MassCopyfunctoid")</span></span>  
  
 <span data-ttu-id="a08ed-165">詳細については、**一括コピー** functoid を参照してください[一括コピー Functoid](../core/mass-copy-functoid.md)です。</span><span class="sxs-lookup"><span data-stu-id="a08ed-165">For more information about the **Mass Copy** functoid, see [Mass Copy Functoid](../core/mass-copy-functoid.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a08ed-166">参照</span><span class="sxs-lookup"><span data-stu-id="a08ed-166">See Also</span></span>  
 <span data-ttu-id="a08ed-167">[リンクを使用してレコードを指定してフィールドのマッピング](../core/using-links-to-specify-record-and-field-mappings.md) </span><span class="sxs-lookup"><span data-stu-id="a08ed-167">[Using Links to Specify Record and Field Mappings](../core/using-links-to-specify-record-and-field-mappings.md) </span></span>  
 [<span data-ttu-id="a08ed-168">マップに一括コピー Functoid を追加する方法</span><span class="sxs-lookup"><span data-stu-id="a08ed-168">How to Add Mass Copy Functoids to a Map</span></span>](../core/how-to-add-mass-copy-functoids-to-a-map.md)