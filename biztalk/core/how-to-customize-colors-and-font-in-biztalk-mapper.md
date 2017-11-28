---
title: "色と BizTalk マッパーでフォントをカスタマイズする方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.mapper.options.colors
ms.assetid: 494e4d70-8159-4721-9378-85bfc3c3d6f2
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 724d9e3c118afc4ef0ca369be17b36f439c5885e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-customize-colors-and-font-in-biztalk-mapper"></a><span data-ttu-id="3c8c4-102">BizTalk マッパーの色とフォントをカスタマイズする方法</span><span class="sxs-lookup"><span data-stu-id="3c8c4-102">How to Customize Colors and Font in BizTalk Mapper</span></span>
<span data-ttu-id="3c8c4-103">各種のリンクに関連付けられた色やグリッド ビューで選択されたオブジェクトの色は、必要に応じて変更できます。</span><span class="sxs-lookup"><span data-stu-id="3c8c4-103">You can change the colors associated with various types of links and the color of selected objects in the Grid view.</span></span> <span data-ttu-id="3c8c4-104">また、スキーマのツリー ノードを表示するときに使用されるフォントを変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="3c8c4-104">You can also change the font used to display the schema tree nodes.</span></span> <span data-ttu-id="3c8c4-105">このトピックでは、こうした変更を行うための手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="3c8c4-105">This topic provides step-by-step instructions for making such changes.</span></span>  
  
 <span data-ttu-id="3c8c4-106">また、BizTalk マッパーの全般設定をカスタマイズすることもできます。</span><span class="sxs-lookup"><span data-stu-id="3c8c4-106">You can also choose to customize the general settings for BizTalk Mapper.</span></span> <span data-ttu-id="3c8c4-107">詳細設定を選択する方法については、次を参照してください。 [BizTalk マッパーの全般的な設定をカスタマイズする方法](../core/how-to-customize-general-settings-in-biztalk-mapper.md)です。</span><span class="sxs-lookup"><span data-stu-id="3c8c4-107">For information on how to choose the settings, see [How to Customize General Settings in BizTalk Mapper](../core/how-to-customize-general-settings-in-biztalk-mapper.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3c8c4-108">これらの手順では、BizTalk マッパーが実行されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="3c8c4-108">These instructions require that BizTalk Mapper is running.</span></span>  
  
### <a name="to-change-the-colors-and-font-used-in-biztalk-mapper"></a><span data-ttu-id="3c8c4-109">BizTalk マッパーで使用される色やフォントを変更するには</span><span class="sxs-lookup"><span data-stu-id="3c8c4-109">To change the colors and font used in BizTalk Mapper</span></span>  
  
1.  <span data-ttu-id="3c8c4-110">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]で、 **[ツール]** メニューの **[オプション]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3c8c4-110">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], on the **Tools** menu, click **Options**.</span></span>  
  
2.  <span data-ttu-id="3c8c4-111">**オプション** ダイアログ ボックスで、展開、 **BizTalk マッパー**ノードをクリックして**色とフォント**です。</span><span class="sxs-lookup"><span data-stu-id="3c8c4-111">In the **Options** dialog box, expand the **BizTalk Mapper** node, and then click **Colors & Fonts**.</span></span>  
  
     <span data-ttu-id="3c8c4-112">![色とフォントの選択](../core/media/colorsfonts-options.gif "ColorsFonts_Options")</span><span class="sxs-lookup"><span data-stu-id="3c8c4-112">![Select colors and fonts](../core/media/colorsfonts-options.gif "ColorsFonts_Options")</span></span>  
  
3.  <span data-ttu-id="3c8c4-113">ドロップダウン リストから目的の色を選択して、各種のリンク、コンパイラ警告、グリッドの前景色、グリッドの背景色などを変更します。</span><span class="sxs-lookup"><span data-stu-id="3c8c4-113">Change the colors for the various types of links, compiler warnings, grid foreground, and grid background by using the drop-down color picker associated with each color property.</span></span>  
  
     <span data-ttu-id="3c8c4-114">色に関して選択できる項目は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="3c8c4-114">The following color choices are available:</span></span>  
  
    -   <span data-ttu-id="3c8c4-115">**子ノード リンク。**</span><span class="sxs-lookup"><span data-stu-id="3c8c4-115">**Child Node Links.**</span></span> <span data-ttu-id="3c8c4-116">折りたたまれた親の子のリンクを表示するために使用される色。</span><span class="sxs-lookup"><span data-stu-id="3c8c4-116">The color used for drawing links of collapsed parent’s children.</span></span>  
  
    -   <span data-ttu-id="3c8c4-117">**コンパイラ エラーです。**</span><span class="sxs-lookup"><span data-stu-id="3c8c4-117">**Compiler Errors.**</span></span> <span data-ttu-id="3c8c4-118">コンパイラ エラーの表示に使用される色。</span><span class="sxs-lookup"><span data-stu-id="3c8c4-118">The color used for drawing the compiler error.</span></span>  
  
    -   <span data-ttu-id="3c8c4-119">**コンパイラ リンクを示します。**</span><span class="sxs-lookup"><span data-stu-id="3c8c4-119">**Compiler Links.**</span></span> <span data-ttu-id="3c8c4-120">コンパイラ リンクの色。コンパイラ リンクとは、コンパイラ ディレクティブ リンクです。</span><span class="sxs-lookup"><span data-stu-id="3c8c4-120">The color of compiler links, which are the compiler directive links.</span></span> <span data-ttu-id="3c8c4-121">これは、送信元スキーマ ツリーのフィールドから送信先スキーマ ツリーのフィールドへのリンクを設定するときに自動的に作成されるリンクです。</span><span class="sxs-lookup"><span data-stu-id="3c8c4-121">They are links that are automatically created when a link is set from a field in the source schema tree to a field in the destination schema tree.</span></span>  
  
    -   <span data-ttu-id="3c8c4-122">**選択不可リンク。**</span><span class="sxs-lookup"><span data-stu-id="3c8c4-122">**Dimmed Links.**</span></span> <span data-ttu-id="3c8c4-123">選択または強調表示されていないリンクを表示するために使用される色。</span><span class="sxs-lookup"><span data-stu-id="3c8c4-123">The color used to draw links that are not selected or highlighted.</span></span>  
  
    -   <span data-ttu-id="3c8c4-124">**柔軟なリンク。**</span><span class="sxs-lookup"><span data-stu-id="3c8c4-124">**Elastic Links.**</span></span> <span data-ttu-id="3c8c4-125">柔軟なリンクの色。柔軟なリンクとは、送信元スキーマ ツリーから送信先スキーマ ツリーにドラッグされた単純な値コピーのリンクです。</span><span class="sxs-lookup"><span data-stu-id="3c8c4-125">The color of elastic links, which are simple value-copy links that are dragged from the source schema tree to the destination schema tree.</span></span> <span data-ttu-id="3c8c4-126">このリンクが確立されると、リンクの色は固定リンク用に定義した色に変更されます。</span><span class="sxs-lookup"><span data-stu-id="3c8c4-126">After the link is made, the color of the link changes to the color for fixed links.</span></span>  
  
    -   <span data-ttu-id="3c8c4-127">**[全般] リンクを示します。**</span><span class="sxs-lookup"><span data-stu-id="3c8c4-127">**General Links.**</span></span> <span data-ttu-id="3c8c4-128">何も選択されていないときに、ビュー内に両端を持つリンクを表示するために使用される色。</span><span class="sxs-lookup"><span data-stu-id="3c8c4-128">The color used to draw links that have both the ends in the view, when nothing is selected.</span></span>  
  
    -   <span data-ttu-id="3c8c4-129">**グリッドの背景色。**</span><span class="sxs-lookup"><span data-stu-id="3c8c4-129">**Grid Background.**</span></span> <span data-ttu-id="3c8c4-130">グリッド ページの背景色。</span><span class="sxs-lookup"><span data-stu-id="3c8c4-130">The color of the background in grid pages.</span></span>  
  
    -   <span data-ttu-id="3c8c4-131">**グリッド線。**</span><span class="sxs-lookup"><span data-stu-id="3c8c4-131">**Grid Lines.**</span></span> <span data-ttu-id="3c8c4-132">グリッド線の表示に使用される色。</span><span class="sxs-lookup"><span data-stu-id="3c8c4-132">The color used for drawing the grid lines.</span></span>  
  
    -   <span data-ttu-id="3c8c4-133">**強調表示されたリンクを示します。**</span><span class="sxs-lookup"><span data-stu-id="3c8c4-133">**Highlighted Links.**</span></span> <span data-ttu-id="3c8c4-134">リンクの強調表示に使用される色。</span><span class="sxs-lookup"><span data-stu-id="3c8c4-134">The color used for highlighting links.</span></span>  
  
    -   <span data-ttu-id="3c8c4-135">**指示一致リンクを示します。**</span><span class="sxs-lookup"><span data-stu-id="3c8c4-135">**Indicative Match Links.**</span></span> <span data-ttu-id="3c8c4-136">指示一致リンクを表示するために使用される色。</span><span class="sxs-lookup"><span data-stu-id="3c8c4-136">The color used to draw indicative matches.</span></span>  
  
    -   <span data-ttu-id="3c8c4-137">**部分的にスコープ外のリンク。**</span><span class="sxs-lookup"><span data-stu-id="3c8c4-137">**Partially Out of Scope Links.**</span></span> <span data-ttu-id="3c8c4-138">一端のみをビュー内に持つリンクを表示するために使用される色。</span><span class="sxs-lookup"><span data-stu-id="3c8c4-138">The color used to draw links that have only one end in view.</span></span>  
  
    -   <span data-ttu-id="3c8c4-139">**スキーマ ノードのフォントの色です。**</span><span class="sxs-lookup"><span data-stu-id="3c8c4-139">**Schema Node Font Color.**</span></span> <span data-ttu-id="3c8c4-140">スキーマ ツリー ノードに使用される色。</span><span class="sxs-lookup"><span data-stu-id="3c8c4-140">The color used for schema tree nodes.</span></span>  
  
    -   <span data-ttu-id="3c8c4-141">**検索結果。**</span><span class="sxs-lookup"><span data-stu-id="3c8c4-141">**Search Results.**</span></span> <span data-ttu-id="3c8c4-142">スキーマ ツリーでの検索一致の表示に使用される色。</span><span class="sxs-lookup"><span data-stu-id="3c8c4-142">The color used for drawing search matches on the schema tree.</span></span>  
  
    -   <span data-ttu-id="3c8c4-143">**選択したグリッド オブジェクト。**</span><span class="sxs-lookup"><span data-stu-id="3c8c4-143">**Selected Grid Objects.**</span></span> <span data-ttu-id="3c8c4-144">グリッド画面での選択の表示に使用される色。</span><span class="sxs-lookup"><span data-stu-id="3c8c4-144">The color used for drawing the selection in the grid surface.</span></span>  
  
    -   <span data-ttu-id="3c8c4-145">**完全にスコープ外のリンク。**</span><span class="sxs-lookup"><span data-stu-id="3c8c4-145">**Totally Out of Scope Links.**</span></span> <span data-ttu-id="3c8c4-146">両端がビュー内にないリンクを表示するために使用される色。</span><span class="sxs-lookup"><span data-stu-id="3c8c4-146">The color used to draw links that have both ends out of the view.</span></span>  
  
4.  <span data-ttu-id="3c8c4-147">省略記号ボタン (**.**) ボタンの右端にある、**スキーマ ノードのフォント**プロパティ値ボックスです。</span><span class="sxs-lookup"><span data-stu-id="3c8c4-147">Click the ellipsis (**…**) button located at the right end of the **Schema node font** property value box.</span></span>  
  
5.  <span data-ttu-id="3c8c4-148">**フォント**メイン編集ウィンドウのビューで使用するフォントをダイアログ ボックスで、変更します。</span><span class="sxs-lookup"><span data-stu-id="3c8c4-148">In the **Font** dialog box, change the font used in the views in the main editing window.</span></span>  
  
6.  <span data-ttu-id="3c8c4-149">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3c8c4-149">Click **OK**.</span></span> <span data-ttu-id="3c8c4-150">設定が選択済みとして適用されます。</span><span class="sxs-lookup"><span data-stu-id="3c8c4-150">The settings are applied as chosen.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="3c8c4-151">カスタマイズした設定を使用しない場合は、クリックして**既定値に戻す**で、**オプション** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="3c8c4-151">If you do not want to use the customized settings, click **Restore Defaults** in the **Options** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c8c4-152">参照</span><span class="sxs-lookup"><span data-stu-id="3c8c4-152">See Also</span></span>  
 [<span data-ttu-id="3c8c4-153">BizTalk マッパーの使用</span><span class="sxs-lookup"><span data-stu-id="3c8c4-153">Using BizTalk Mapper</span></span>](../core/using-biztalk-mapper.md)