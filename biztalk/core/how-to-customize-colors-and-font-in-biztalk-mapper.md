---
title: 色とフォントの BizTalk マッパーをカスタマイズする方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.mapper.options.colors
ms.assetid: 494e4d70-8159-4721-9378-85bfc3c3d6f2
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 25c4981e083352bbba24a6579083dc4023605cba
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65338905"
---
# <a name="how-to-customize-colors-and-font-in-biztalk-mapper"></a><span data-ttu-id="3dfe3-102">BizTalk マッパーの色とフォントをカスタマイズする方法</span><span class="sxs-lookup"><span data-stu-id="3dfe3-102">How to Customize Colors and Font in BizTalk Mapper</span></span>
<span data-ttu-id="3dfe3-103">各種のリンクに関連付けられた色やグリッド ビューで選択されたオブジェクトの色は、必要に応じて変更できます。</span><span class="sxs-lookup"><span data-stu-id="3dfe3-103">You can change the colors associated with various types of links and the color of selected objects in the Grid view.</span></span> <span data-ttu-id="3dfe3-104">また、スキーマのツリー ノードを表示するときに使用されるフォントを変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="3dfe3-104">You can also change the font used to display the schema tree nodes.</span></span> <span data-ttu-id="3dfe3-105">このトピックでは、こうした変更を行うための手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="3dfe3-105">This topic provides step-by-step instructions for making such changes.</span></span>  
  
 <span data-ttu-id="3dfe3-106">また、BizTalk マッパーの全般設定をカスタマイズすることもできます。</span><span class="sxs-lookup"><span data-stu-id="3dfe3-106">You can also choose to customize the general settings for BizTalk Mapper.</span></span> <span data-ttu-id="3dfe3-107">設定を選択する方法については、次を参照してください。 [BizTalk マッパーの全般設定をカスタマイズする方法](../core/how-to-customize-general-settings-in-biztalk-mapper.md)します。</span><span class="sxs-lookup"><span data-stu-id="3dfe3-107">For information on how to choose the settings, see [How to Customize General Settings in BizTalk Mapper](../core/how-to-customize-general-settings-in-biztalk-mapper.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3dfe3-108">これらの手順では、BizTalk マッパーが実行されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="3dfe3-108">These instructions require that BizTalk Mapper is running.</span></span>  
  
### <a name="to-change-the-colors-and-font-used-in-biztalk-mapper"></a><span data-ttu-id="3dfe3-109">BizTalk マッパーで使用される色やフォントを変更するには</span><span class="sxs-lookup"><span data-stu-id="3dfe3-109">To change the colors and font used in BizTalk Mapper</span></span>  
  
1. <span data-ttu-id="3dfe3-110">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]で、 **[ツール]** メニューの **[オプション]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3dfe3-110">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], on the **Tools** menu, click **Options**.</span></span>  
  
2. <span data-ttu-id="3dfe3-111">**オプション** ダイアログ ボックスで、展開、 **BizTalk マッパー**ノード、およびクリック**色とフォント**します。</span><span class="sxs-lookup"><span data-stu-id="3dfe3-111">In the **Options** dialog box, expand the **BizTalk Mapper** node, and then click **Colors & Fonts**.</span></span>  
  
    <span data-ttu-id="3dfe3-112">![色とフォントの選択](../core/media/colorsfonts-options.gif "ColorsFonts_Options")</span><span class="sxs-lookup"><span data-stu-id="3dfe3-112">![Select colors and fonts](../core/media/colorsfonts-options.gif "ColorsFonts_Options")</span></span>  
  
3. <span data-ttu-id="3dfe3-113">ドロップダウン リストから目的の色を選択して、各種のリンク、コンパイラ警告、グリッドの前景色、グリッドの背景色などを変更します。</span><span class="sxs-lookup"><span data-stu-id="3dfe3-113">Change the colors for the various types of links, compiler warnings, grid foreground, and grid background by using the drop-down color picker associated with each color property.</span></span>  
  
    <span data-ttu-id="3dfe3-114">色に関して選択できる項目は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="3dfe3-114">The following color choices are available:</span></span>  
  
   -   <span data-ttu-id="3dfe3-115">**子ノード リンク。**</span><span class="sxs-lookup"><span data-stu-id="3dfe3-115">**Child Node Links.**</span></span> <span data-ttu-id="3dfe3-116">折りたたまれた親の子のリンクを表示するために使用される色。</span><span class="sxs-lookup"><span data-stu-id="3dfe3-116">The color used for drawing links of collapsed parent’s children.</span></span>  
  
   -   <span data-ttu-id="3dfe3-117">**コンパイラ エラー。**</span><span class="sxs-lookup"><span data-stu-id="3dfe3-117">**Compiler Errors.**</span></span> <span data-ttu-id="3dfe3-118">コンパイラ エラーの表示に使用される色。</span><span class="sxs-lookup"><span data-stu-id="3dfe3-118">The color used for drawing the compiler error.</span></span>  
  
   -   <span data-ttu-id="3dfe3-119">**コンパイラ リンクを示します。**</span><span class="sxs-lookup"><span data-stu-id="3dfe3-119">**Compiler Links.**</span></span> <span data-ttu-id="3dfe3-120">コンパイラ リンクの色。コンパイラ リンクとは、コンパイラ ディレクティブ リンクです。</span><span class="sxs-lookup"><span data-stu-id="3dfe3-120">The color of compiler links, which are the compiler directive links.</span></span> <span data-ttu-id="3dfe3-121">これは、送信元スキーマ ツリーのフィールドから送信先スキーマ ツリーのフィールドへのリンクを設定するときに自動的に作成されるリンクです。</span><span class="sxs-lookup"><span data-stu-id="3dfe3-121">They are links that are automatically created when a link is set from a field in the source schema tree to a field in the destination schema tree.</span></span>  
  
   -   <span data-ttu-id="3dfe3-122">**選択不可リンク。**</span><span class="sxs-lookup"><span data-stu-id="3dfe3-122">**Dimmed Links.**</span></span> <span data-ttu-id="3dfe3-123">選択または強調表示されていないリンクを表示するために使用される色。</span><span class="sxs-lookup"><span data-stu-id="3dfe3-123">The color used to draw links that are not selected or highlighted.</span></span>  
  
   -   <span data-ttu-id="3dfe3-124">**柔軟なリンク。**</span><span class="sxs-lookup"><span data-stu-id="3dfe3-124">**Elastic Links.**</span></span> <span data-ttu-id="3dfe3-125">柔軟なリンクの色。柔軟なリンクとは、送信元スキーマ ツリーから送信先スキーマ ツリーにドラッグされた単純な値コピーのリンクです。</span><span class="sxs-lookup"><span data-stu-id="3dfe3-125">The color of elastic links, which are simple value-copy links that are dragged from the source schema tree to the destination schema tree.</span></span> <span data-ttu-id="3dfe3-126">このリンクが確立されると、リンクの色は固定リンク用に定義した色に変更されます。</span><span class="sxs-lookup"><span data-stu-id="3dfe3-126">After the link is made, the color of the link changes to the color for fixed links.</span></span>  
  
   -   <span data-ttu-id="3dfe3-127">**[全般] リンクを示します。**</span><span class="sxs-lookup"><span data-stu-id="3dfe3-127">**General Links.**</span></span> <span data-ttu-id="3dfe3-128">何も選択されていないときに、ビュー内に両端を持つリンクを表示するために使用される色。</span><span class="sxs-lookup"><span data-stu-id="3dfe3-128">The color used to draw links that have both the ends in the view, when nothing is selected.</span></span>  
  
   -   <span data-ttu-id="3dfe3-129">**グリッドの背景色。**</span><span class="sxs-lookup"><span data-stu-id="3dfe3-129">**Grid Background.**</span></span> <span data-ttu-id="3dfe3-130">グリッド ページの背景色。</span><span class="sxs-lookup"><span data-stu-id="3dfe3-130">The color of the background in grid pages.</span></span>  
  
   -   <span data-ttu-id="3dfe3-131">**グリッド線。**</span><span class="sxs-lookup"><span data-stu-id="3dfe3-131">**Grid Lines.**</span></span> <span data-ttu-id="3dfe3-132">グリッド線の表示に使用される色。</span><span class="sxs-lookup"><span data-stu-id="3dfe3-132">The color used for drawing the grid lines.</span></span>  
  
   -   <span data-ttu-id="3dfe3-133">**強調表示されているリンクを示します。**</span><span class="sxs-lookup"><span data-stu-id="3dfe3-133">**Highlighted Links.**</span></span> <span data-ttu-id="3dfe3-134">リンクの強調表示に使用される色。</span><span class="sxs-lookup"><span data-stu-id="3dfe3-134">The color used for highlighting links.</span></span>  
  
   -   <span data-ttu-id="3dfe3-135">**指示一致リンクを示します。**</span><span class="sxs-lookup"><span data-stu-id="3dfe3-135">**Indicative Match Links.**</span></span> <span data-ttu-id="3dfe3-136">指示一致リンクを表示するために使用される色。</span><span class="sxs-lookup"><span data-stu-id="3dfe3-136">The color used to draw indicative matches.</span></span>  
  
   -   <span data-ttu-id="3dfe3-137">**部分的にスコープ外のリンク。**</span><span class="sxs-lookup"><span data-stu-id="3dfe3-137">**Partially Out of Scope Links.**</span></span> <span data-ttu-id="3dfe3-138">一端のみをビュー内に持つリンクを表示するために使用される色。</span><span class="sxs-lookup"><span data-stu-id="3dfe3-138">The color used to draw links that have only one end in view.</span></span>  
  
   -   <span data-ttu-id="3dfe3-139">**スキーマ ノードのフォントの色。**</span><span class="sxs-lookup"><span data-stu-id="3dfe3-139">**Schema Node Font Color.**</span></span> <span data-ttu-id="3dfe3-140">スキーマ ツリー ノードに使用される色。</span><span class="sxs-lookup"><span data-stu-id="3dfe3-140">The color used for schema tree nodes.</span></span>  
  
   -   <span data-ttu-id="3dfe3-141">**検索結果。**</span><span class="sxs-lookup"><span data-stu-id="3dfe3-141">**Search Results.**</span></span> <span data-ttu-id="3dfe3-142">スキーマ ツリーでの検索一致の表示に使用される色。</span><span class="sxs-lookup"><span data-stu-id="3dfe3-142">The color used for drawing search matches on the schema tree.</span></span>  
  
   -   <span data-ttu-id="3dfe3-143">**選択したグリッド オブジェクト。**</span><span class="sxs-lookup"><span data-stu-id="3dfe3-143">**Selected Grid Objects.**</span></span> <span data-ttu-id="3dfe3-144">グリッド画面での選択の表示に使用される色。</span><span class="sxs-lookup"><span data-stu-id="3dfe3-144">The color used for drawing the selection in the grid surface.</span></span>  
  
   -   <span data-ttu-id="3dfe3-145">**完全にスコープ外のリンク。**</span><span class="sxs-lookup"><span data-stu-id="3dfe3-145">**Totally Out of Scope Links.**</span></span> <span data-ttu-id="3dfe3-146">両端がビュー内にないリンクを表示するために使用される色。</span><span class="sxs-lookup"><span data-stu-id="3dfe3-146">The color used to draw links that have both ends out of the view.</span></span>  
  
4. <span data-ttu-id="3dfe3-147">省略記号をクリックします (**.**) ボタンの右端にある、**スキーマ ノードのフォント**プロパティ値ボックス。</span><span class="sxs-lookup"><span data-stu-id="3dfe3-147">Click the ellipsis (**…**) button located at the right end of the **Schema node font** property value box.</span></span>  
  
5. <span data-ttu-id="3dfe3-148">**フォント**メイン編集ウィンドウ内のビューで使用する、フォント ダイアログ ボックスで、変更します。</span><span class="sxs-lookup"><span data-stu-id="3dfe3-148">In the **Font** dialog box, change the font used in the views in the main editing window.</span></span>  
  
6. <span data-ttu-id="3dfe3-149">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3dfe3-149">Click **OK**.</span></span> <span data-ttu-id="3dfe3-150">設定が選択済みとして適用されます。</span><span class="sxs-lookup"><span data-stu-id="3dfe3-150">The settings are applied as chosen.</span></span>  
  
   > [!IMPORTANT]
   >  <span data-ttu-id="3dfe3-151">カスタマイズした設定を使用しない場合はクリックして**既定値に戻す**で、**オプション** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="3dfe3-151">If you do not want to use the customized settings, click **Restore Defaults** in the **Options** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3dfe3-152">参照</span><span class="sxs-lookup"><span data-stu-id="3dfe3-152">See Also</span></span>  
 [<span data-ttu-id="3dfe3-153">BizTalk マッパーの使用</span><span class="sxs-lookup"><span data-stu-id="3dfe3-153">Using BizTalk Mapper</span></span>](../core/using-biztalk-mapper.md)