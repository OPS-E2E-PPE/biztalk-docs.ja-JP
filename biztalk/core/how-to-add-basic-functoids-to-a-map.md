---
title: "マップに基本 Functoid を追加する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6a81fb73-cccf-4f74-af92-39e4af13e255
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 23a6748a5ce128ef13ce012412e36570e4e01eba
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-add-basic-functoids-to-a-map"></a><span data-ttu-id="2fcbd-102">マップに基本 Functoid を追加する方法</span><span class="sxs-lookup"><span data-stu-id="2fcbd-102">How to Add Basic Functoids to a Map</span></span>
<span data-ttu-id="2fcbd-103">簡単に使用できる Functoid が多数用意されています。</span><span class="sxs-lookup"><span data-stu-id="2fcbd-103">Many functoids are very simple to use.</span></span> <span data-ttu-id="2fcbd-104">これらと呼ばれるここまでで functoid と区別するための基本 functoid、**詳細**カテゴリ。</span><span class="sxs-lookup"><span data-stu-id="2fcbd-104">These are referred to here as basic functoids to distinguish them from the functoids in the **Advanced** category.</span></span> <span data-ttu-id="2fcbd-105">基本 Functoid では、変換、データベース、日時、論理、関数、文字列などのカテゴリを対象としています。</span><span class="sxs-lookup"><span data-stu-id="2fcbd-105">Basic functoids comprise the remaining categories of functoids such as Conversion, Cumulative, Database, Date and Time, Logical, Mathematical, Scientific, and String.</span></span>  
  
 <span data-ttu-id="2fcbd-106">通常、基本 Functoid の入力リンクおよび出力リンクの型は数値や文字列などの単純な型です。</span><span class="sxs-lookup"><span data-stu-id="2fcbd-106">Basic functoids, in general, have simple types, such as numbers and strings, as their input and output links.</span></span>  
  
 <span data-ttu-id="2fcbd-107">基本 Functoid を使用する場合、グリッド ページへの追加、Functoid への入力リンクの作成 (左側からのリンク)、および Functoid からの出力リンクの作成 (右側へのリンク) を行います。</span><span class="sxs-lookup"><span data-stu-id="2fcbd-107">Using a basic functoid involves adding it to a grid page, creating input links to the functoid, coming from the left, and creating output link from the functoid, leaving to the right.</span></span> <span data-ttu-id="2fcbd-108">このトピックでは、これらの作業の手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="2fcbd-108">This topic provides step-by-step instructions for these operations.</span></span>  
  
## <a name="add-a-basic-functoid-to-a-map"></a><span data-ttu-id="2fcbd-109">マップに基本 functoid を追加します。</span><span class="sxs-lookup"><span data-stu-id="2fcbd-109">Add a basic functoid to a map</span></span>  
  
1.  <span data-ttu-id="2fcbd-110">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] ツールボックスをアクティブにして、該当するタブをクリックし、使用する Functoid のカテゴリを選択します。</span><span class="sxs-lookup"><span data-stu-id="2fcbd-110">With the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Toolbox active, click the appropriate tab to select the category of the functoid you want to use.</span></span>  
  
     <span data-ttu-id="2fcbd-111">選択したカテゴリで使用可能な Functoid の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="2fcbd-111">The list of available functoids in the chosen category appears.</span></span>  
  
2.  <span data-ttu-id="2fcbd-112">ツールボックスから使用する Functoid をグリッド ページの該当する位置にドラッグします。</span><span class="sxs-lookup"><span data-stu-id="2fcbd-112">Drag the functoid you want to use from the Toolbox to the appropriate location on a grid page.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2fcbd-113">Functoid は表示されているグリッド ページに配置されます。</span><span class="sxs-lookup"><span data-stu-id="2fcbd-113">The functoid will be placed on the displayed grid page.</span></span> <span data-ttu-id="2fcbd-114">別のグリッド ページに functoid を配置する場合は、その他のグリッド ページを最初に表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2fcbd-114">If you want to put the functoid onto a different grid page, you need to display that other grid page first.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2fcbd-115">複数の Functoid を同時に使用するマップを構築する場合は、相対的な位置 (左右) に注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2fcbd-115">If you are constructing a map using more than one functoid together, you need to consider their relative left to right placement.</span></span> <span data-ttu-id="2fcbd-116">Functoids は左から順に実行されます。</span><span class="sxs-lookup"><span data-stu-id="2fcbd-116">Functoids are executed from left to right.</span></span> <span data-ttu-id="2fcbd-117">1 つの Functoid からの出力は、これよりも右にある Functoid にのみ入力することができます。</span><span class="sxs-lookup"><span data-stu-id="2fcbd-117">The output of a functoid can only be input to another functoid that is farther to the right.</span></span>  
  
## <a name="create-input-links-to-a-basic-functoid"></a><span data-ttu-id="2fcbd-118">基本 functoid への入力リンクを作成します。</span><span class="sxs-lookup"><span data-stu-id="2fcbd-118">Create input links to a basic functoid</span></span>  
  
1.  <span data-ttu-id="2fcbd-119">送信元スキーマ内のレコード ノードまたはフィールド ノードを、表示されているグリッド ページ内の基本 Functoid にドラッグします。</span><span class="sxs-lookup"><span data-stu-id="2fcbd-119">Drag a record or field node from the source schema to the basic functoid in the displayed grid page.</span></span>  
  
     <span data-ttu-id="2fcbd-120">**- または -**</span><span class="sxs-lookup"><span data-stu-id="2fcbd-120">**- Or -**</span></span>  
  
     <span data-ttu-id="2fcbd-121">表示されているグリッド ページで、入力リンクの対象となる基本 Functoid に、この Functoid よりも左にある別の Functoid をドラッグします。</span><span class="sxs-lookup"><span data-stu-id="2fcbd-121">In the displayed grid page, drag another functoid, which is located farther to the left, to the basic functoid to which you want to create an input link.</span></span>  
  
     <span data-ttu-id="2fcbd-122">**- または -**</span><span class="sxs-lookup"><span data-stu-id="2fcbd-122">**- Or -**</span></span>  
  
     <span data-ttu-id="2fcbd-123">表示されているグリッド ページ内の基本 Functoid を、送信元スキーマ内のレコード ノードまたはフィールド ノードにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="2fcbd-123">Drag the basic functoid in the displayed grid page to a record or field node in the source schema.</span></span>  
  
     <span data-ttu-id="2fcbd-124">**- または -**</span><span class="sxs-lookup"><span data-stu-id="2fcbd-124">**- Or -**</span></span>  
  
     <span data-ttu-id="2fcbd-125">表示されているグリッド ページで、入力リンクの対象となる基本 Functoid を、この Functoid よりも左に位置している別の Functoid にドラッグします。</span><span class="sxs-lookup"><span data-stu-id="2fcbd-125">In the displayed grid page, drag the basic functoid to which you want to create an input link to another functoid that is located farther to the left.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2fcbd-126">ドラッグ中には、リンクの固定されたエンドポイントではなく、リンクの移動のエンドポイントより正確な対象とした 2 番目のエンドポイントの使用できるように十字カーソル アイコンに変わります。</span><span class="sxs-lookup"><span data-stu-id="2fcbd-126">While dragging, the moving endpoint of the link, as opposed to the anchored endpoint of the link, changes to a crosshair icon to allow more accurate targeting of the second endpoint.</span></span> <span data-ttu-id="2fcbd-127">リンクの移動、エンドポイント、リンクの適切な 2 番目のエンドポイントではなくなど、発生する可能性がデータ型の不一致がある場合にオブジェクトをポイントする場合、十字カーソル アイコンは、斜めのスラッシュを含む円を示すアイコンに変わります。</span><span class="sxs-lookup"><span data-stu-id="2fcbd-127">If you hover the moving endpoint of the link over an object that is not an appropriate second endpoint for the link, such as might occur when there is a data type mismatch, the crosshair icon changes to an icon showing a circle with a diagonal slash through it.</span></span>  
  
2.  <span data-ttu-id="2fcbd-128">必要に応じて手順 1. を繰り返して、基本 Functoid への入力リンクのセットを完成します (ただし、入力パラメーターのすべてのセットが完成するわけではありません)。</span><span class="sxs-lookup"><span data-stu-id="2fcbd-128">Repeat step 1 as necessary to establish the complete set of input links (though perhaps not the entire set of input parameters) to the basic functoid.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2fcbd-129">一部の Functoid は、入力リンクを必要としません。</span><span class="sxs-lookup"><span data-stu-id="2fcbd-129">There are a few functoids that do not require any input links.</span></span> <span data-ttu-id="2fcbd-130">たとえば、**日付**、**時間**、および**日付と時刻**functoid を**日付と時刻**functoid カテゴリは、現在の日付を指定時間、または日付と時刻、インスタンス メッセージを処理中に、それぞれします。</span><span class="sxs-lookup"><span data-stu-id="2fcbd-130">For example, the **Date**, **Time**, and **Date and Time** functoids in the **Date and Time** functoid category provide the current date, time, or date and time, respectively, at which an instance message is being processed.</span></span> <span data-ttu-id="2fcbd-131">したがって、送信元スキーマからの入力パラメーターは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="2fcbd-131">Thus, they do not require any input parameters from the source schema.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2fcbd-132">多くの functoid への入力パラメーターの順序は、重要では、対応する functoid のリファレンス トピックに記載されている (を参照してください**Functoid リファレンス** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)])。</span><span class="sxs-lookup"><span data-stu-id="2fcbd-132">The order of input parameters to many functoids is significant, as indicated in the corresponding functoid reference topic (see **Functoid Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]).</span></span> <span data-ttu-id="2fcbd-133">リンクの作成順序により、Functoid への入力パラメーターの順序が設定されます。</span><span class="sxs-lookup"><span data-stu-id="2fcbd-133">The order in which you create links sets the order of input parameters to the functoid.</span></span> <span data-ttu-id="2fcbd-134">Functoid のプロパティおよび functoid の入力パラメーターの順序の指定の詳細については、次を参照してください。 [Functoid プロパティの編集および入力パラメーター](../core/editing-functoid-properties-and-input-parameters.md)です。</span><span class="sxs-lookup"><span data-stu-id="2fcbd-134">For more information about functoid properties and specifying the order of functoid input parameters, see [Editing Functoid Properties and Input Parameters](../core/editing-functoid-properties-and-input-parameters.md).</span></span> <span data-ttu-id="2fcbd-135">Functoid の入力パラメーターを構成する方法については、次を参照してください。 [Functoid の入力パラメーターを構成する方法](../core/how-to-configure-functoid-input-parameters.md)です。</span><span class="sxs-lookup"><span data-stu-id="2fcbd-135">For information about how to configure the input parameters of a functoid, see [How to Configure Functoid Input Parameters](../core/how-to-configure-functoid-input-parameters.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2fcbd-136">リンクを作成する前に、リンクの対象となる Functoid や送信元スキーマ ノードが、グリッド ページまたは送信元スキーマ ウィンドウに表示されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="2fcbd-136">Ensure the functoids or source schema node you want to link are visible in the displayed grid page or source schema window before you begin linking.</span></span>  
  
## <a name="create-the-output-link-from-a-basic-functoid"></a><span data-ttu-id="2fcbd-137">基本 functoid からの出力リンクを作成します。</span><span class="sxs-lookup"><span data-stu-id="2fcbd-137">Create the output link from a basic functoid</span></span>  
  
1.  <span data-ttu-id="2fcbd-138">送信先スキーマ内のレコード ノードまたはフィールド ノードを、表示されているグリッド ページ内の基本 Functoid にドラッグします。</span><span class="sxs-lookup"><span data-stu-id="2fcbd-138">Drag a record or field node from the destination schema to the basic functoid in the displayed grid page.</span></span>  
  
     <span data-ttu-id="2fcbd-139">**- または -**</span><span class="sxs-lookup"><span data-stu-id="2fcbd-139">**- Or -**</span></span>  
  
     <span data-ttu-id="2fcbd-140">表示されているグリッド ページで、出力リンクの対象となる基本 Functoid に、その Functoid よりも右に位置している別の Functoid をドラッグします。</span><span class="sxs-lookup"><span data-stu-id="2fcbd-140">In the displayed grid page, drag another functoid, which is located farther to the right, to the basic functoid to which you want to create the output link.</span></span>  
  
     <span data-ttu-id="2fcbd-141">**- または -**</span><span class="sxs-lookup"><span data-stu-id="2fcbd-141">**- Or -**</span></span>  
  
     <span data-ttu-id="2fcbd-142">表示されているグリッド ページ内の基本 Functoid を、送信先スキーマ内のレコード ノードまたはフィールド ノードにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="2fcbd-142">Drag the basic functoid in the displayed grid page to a record or field node in the destination schema.</span></span>  
  
     <span data-ttu-id="2fcbd-143">**- または -**</span><span class="sxs-lookup"><span data-stu-id="2fcbd-143">**- Or -**</span></span>  
  
2.  <span data-ttu-id="2fcbd-144">表示されているグリッド ページで、出力リンクの対象となる基本 Functoid を、この Functoid よりも右に位置している別の Functoid にドラッグします。</span><span class="sxs-lookup"><span data-stu-id="2fcbd-144">In the displayed grid page, drag the basic functoid to which you want to create the output link to another functoid that is located farther to the right.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2fcbd-145">リンクを作成する前に、リンクの対象となる Functoid や送信元スキーマ ノードが、グリッド ページまたは送信元スキーマ ウィンドウにそれぞれ表示されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="2fcbd-145">Ensure the functoids and source schema node that you want to link are already visible in the displayed grid page and source schema window, respectively, before you begin the linking operation.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2fcbd-146">Functoid のリンクの作成では、送信元と送信先のデータ型が一致しない場合など不適切なリンクは必ず拒否されます。</span><span class="sxs-lookup"><span data-stu-id="2fcbd-146">Functoid linking always attempts to disallow inappropriate linking, such as links where source and target data types do not match.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2fcbd-147">ドラッグしているときは、リンクの移動する側のエンドポイント (固定されたエンドポイントの反対側のポイント) が十字型に変わり、移動するエンドポイントが明確になるため、リンク先へ適切に接続することができます。</span><span class="sxs-lookup"><span data-stu-id="2fcbd-147">While dragging, the moving end point of the link, as opposed to the anchored endpoint of the link, changes to a crosshair icon to allow more accurate targeting of the second endpoint.</span></span> <span data-ttu-id="2fcbd-148">リンクの移動、エンドポイント、リンクの適切な 2 番目のエンドポイントではなくなど、発生する可能性がデータ型の不一致がある場合にオブジェクトをポイントする場合、十字カーソル アイコンは、斜めのスラッシュを含む円を示すアイコンに変わります。</span><span class="sxs-lookup"><span data-stu-id="2fcbd-148">If you hover the moving endpoint of the link over an object that is not an appropriate second endpoint for the link, such as might occur when there is a data type mismatch, the crosshair icon changes to an icon showing a circle with a diagonal slash through it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2fcbd-149">参照</span><span class="sxs-lookup"><span data-stu-id="2fcbd-149">See Also</span></span>  
<span data-ttu-id="2fcbd-150">**Functoid のリファレンス**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="2fcbd-150">**Functoid Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>