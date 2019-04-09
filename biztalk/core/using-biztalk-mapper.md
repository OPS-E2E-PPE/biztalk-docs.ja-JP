---
title: BizTalk マッパーを使用して |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.mapper.grid
ms.assetid: 07c69603-ee79-44b2-80b1-6ae4e4c8fb4e
caps.latest.revision: 29
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dfa3ac3d03e5f9537284ea4e4371ab5a443d2b42
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967531"
---
# <a name="using-biztalk-mapper"></a><span data-ttu-id="68b5c-102">BizTalk マッパーの使用</span><span class="sxs-lookup"><span data-stu-id="68b5c-102">Using BizTalk Mapper</span></span>

## <a name="overview"></a><span data-ttu-id="68b5c-103">概要</span><span class="sxs-lookup"><span data-stu-id="68b5c-103">Overview</span></span>
<span data-ttu-id="68b5c-104">BizTalk マッパーは [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] シェルに格納されており、</span><span class="sxs-lookup"><span data-stu-id="68b5c-104">The BizTalk Mapper resides in the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] shell.</span></span> <span data-ttu-id="68b5c-105">BizTalk マッパーの機能の一部のユーザー インターフェイス要素に依存しています、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]シェルです。</span><span class="sxs-lookup"><span data-stu-id="68b5c-105">Some of the functionality in the BizTalk Mapper relies on the user interface elements of the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] shell.</span></span> <span data-ttu-id="68b5c-106">たとえば、使用する、**ファイル**、**編集**と**ビュー**で他の開発の場合と同様のメニューは[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="68b5c-106">For example, you use the **File**, **Edit**, and **View** menus just as you would for other development in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="68b5c-107">この共通の機能についての情報は、**ヘルプ**メニュー。</span><span class="sxs-lookup"><span data-stu-id="68b5c-107">Information about this common functionality is available from the **Help** menu.</span></span>  
  
 <span data-ttu-id="68b5c-108">既存のマップ (.btm ファイル) を開くと、BizTalk プロジェクトに新しいマップを追加するとき、または、メインのタブをクリックしてマップを再アクティブ化するとき、BizTalk マッパーがアクティブになった[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ウィンドウを編集します。</span><span class="sxs-lookup"><span data-stu-id="68b5c-108">The BizTalk Mapper becomes active when you add a new map to a BizTalk project, when you open an existing map (a .btm file), or when you reactivate a map by clicking its tab in the main [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] editing window.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="68b5c-109">BizTalk マッパーでは、UTF-16 文字エンコードを使用してマップ ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="68b5c-109">The BizTalk Mapper saves map files using UTF-16 character encoding.</span></span>  
>
>  <span data-ttu-id="68b5c-110">ビルド アクションは常に設定するときに、既存のアーティファクトを BizTalk プロジェクトに追加すると、 **BtsCompile**します。</span><span class="sxs-lookup"><span data-stu-id="68b5c-110">When you add an existing artifact to a BizTalk project, the build action is always set to **BtsCompile**.</span></span> <span data-ttu-id="68b5c-111">そのビルド アクションが既定値に設定されて既存のアーティファクトの名前を変更する場合でも**BtsCompile**します。</span><span class="sxs-lookup"><span data-stu-id="68b5c-111">Even when you rename an existing artifact, its build action is set to the default value **BtsCompile**.</span></span> <span data-ttu-id="68b5c-112">したがって、既存のアイテムを追加または名前変更する場合は、その特定のアイテムをビルドするかどうかによって、ビルド アクションを適切に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="68b5c-112">Hence, while adding or renaming an existing artifact, you need to set the build action appropriately depending on whether you want to build that particular artifact or not.</span></span>  

## <a name="parts-of-the-biztalk-mapper"></a><span data-ttu-id="68b5c-113">BizTalk マッパーのパーツ</span><span class="sxs-lookup"><span data-stu-id="68b5c-113">Parts of the BizTalk Mapper</span></span>  
 <span data-ttu-id="68b5c-114">次の図は、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] に含まれる BizTalk マッパーのさまざまな部分を示しています。</span><span class="sxs-lookup"><span data-stu-id="68b5c-114">The following figure shows various parts of BizTalk Mapper within [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
 <span data-ttu-id="68b5c-115">![BizTalk マッパー](../core/media/mapper-views.gif "Mapper_Views")</span><span class="sxs-lookup"><span data-stu-id="68b5c-115">![BizTalk Mapper](../core/media/mapper-views.gif "Mapper_Views")</span></span>  
  
 <span data-ttu-id="68b5c-116">各ビューの機能は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="68b5c-116">The functionality of each of the views is as follows:</span></span>  
  
- <span data-ttu-id="68b5c-117">**Visual Studio マッパー ユーティリティ リボン**</span><span class="sxs-lookup"><span data-stu-id="68b5c-117">**Visual Studio Mapper Utility Ribbon.**</span></span> <span data-ttu-id="68b5c-118">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]マッパーはマッパー関連コマンドを表示するユーティリティ リボンを提供します。</span><span class="sxs-lookup"><span data-stu-id="68b5c-118">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Mapper provides a utility ribbon to surface Mapper-related commands.</span></span> <span data-ttu-id="68b5c-119">リボンには送信元スキーマ情報、送信元スキーマと送信先スキーマの関連性ビューを切り替えるボタン、完全にスコープ外のリンクの表示と非表示を切り替えるボタン、自動スクロールのオンとオフを切り替えるトグル スイッチ、マッパー画面を左右に移動するボタン、ズームインとズームアウトのコントロール、検索テキスト ボックスが登録されています。</span><span class="sxs-lookup"><span data-stu-id="68b5c-119">The ribbon provides source schema information, toggle button for relevance view for source and destination schemas, toggle button to show or hide totally out of scope links, toggle switch to turn auto-scrolling on or off, button to pan the Mapper surface, controls to zoom in or zoom out, and the search text box.</span></span> <span data-ttu-id="68b5c-120">次の図は、グリッド ページの上部に表示されるユーティリティ リボンを示しています。</span><span class="sxs-lookup"><span data-stu-id="68b5c-120">The following figure shows the utility ribbon you can see at the top of the grid page.</span></span>  
  
   <span data-ttu-id="68b5c-121">![マッパー リボン](../core/media/mapper-ribbon.gif "Mapper_Ribbon")</span><span class="sxs-lookup"><span data-stu-id="68b5c-121">![Mapper ribbon](../core/media/mapper-ribbon.gif "Mapper_Ribbon")</span></span>  
  
- <span data-ttu-id="68b5c-122">**送信元スキーマ ツリー ビュー。**</span><span class="sxs-lookup"><span data-stu-id="68b5c-122">**Source schema tree view.**</span></span> <span data-ttu-id="68b5c-123">: このビューは、送信先スキーマ ツリー ビューおよびグリッド ビューと [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] のメイン編集ウィンドウを共有します。</span><span class="sxs-lookup"><span data-stu-id="68b5c-123">This view shares the main [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] editing window with the destination schema tree view and the grid view.</span></span>  
  
   <span data-ttu-id="68b5c-124">名前が示すように、このビューには、マッピングの送信元であるインスタンス メッセージを記述するスキーマが表示されます。</span><span class="sxs-lookup"><span data-stu-id="68b5c-124">As the name suggests, this view displays the schema that describes the instance messages that are the source of mapping.</span></span> <span data-ttu-id="68b5c-125">マッピングを定義するリンクは、グリッド ビューと、最終的には、送信先スキーマ ツリー ビューに、送信元スキーマのツリー ビューがあります。</span><span class="sxs-lookup"><span data-stu-id="68b5c-125">The links that define the mapping lead from the source schema tree view to the grid view, and, ultimately, to the destination schema tree view.</span></span>  
  
   <span data-ttu-id="68b5c-126">スキーマ ツリー ビューでの BizTalk スキーマの表現方法の詳細については、[スキーマの BizTalk 表記](../core/biztalk-representation-of-schemas.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="68b5c-126">For more information about how BizTalk schemas are represented in a schema tree view, see [BizTalk Representation of Schemas](../core/biztalk-representation-of-schemas.md).</span></span>  
  
- <span data-ttu-id="68b5c-127">**送信先スキーマ ツリー ビュー。**</span><span class="sxs-lookup"><span data-stu-id="68b5c-127">**Destination schema tree view.**</span></span> <span data-ttu-id="68b5c-128">: このビューは、送信元スキーマ ツリー ビューおよびグリッド ビューと [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] のメイン編集ウィンドウを共有します。</span><span class="sxs-lookup"><span data-stu-id="68b5c-128">This view shares the main [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] editing window with the source schema tree view and the grid view.</span></span>  
  
   <span data-ttu-id="68b5c-129">名前が示すように、このビューには、マッピングの送信先であるインスタンス メッセージを記述するスキーマが表示されます。</span><span class="sxs-lookup"><span data-stu-id="68b5c-129">As the name suggests, this view displays the schema that describes the instance messages that are the destination of the mapping.</span></span> <span data-ttu-id="68b5c-130">マッピングを定義するリンクは、グリッド ビューから送信先スキーマ ツリー ビューに接続されており、送信元スキーマ ツリー ビューが始点となります。</span><span class="sxs-lookup"><span data-stu-id="68b5c-130">The links that define the mapping lead into the destination schema tree view from the grid view, and ultimately from the source schema tree view.</span></span>  
  
   <span data-ttu-id="68b5c-131">スキーマ ツリー ビューでの BizTalk スキーマの表現方法の詳細については、[スキーマの BizTalk 表記](../core/biztalk-representation-of-schemas.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="68b5c-131">For more information about how BizTalk schemas are represented in a schema tree view, see [BizTalk Representation of Schemas](../core/biztalk-representation-of-schemas.md).</span></span>  
  
- <span data-ttu-id="68b5c-132">**グリッドを表示します。**</span><span class="sxs-lookup"><span data-stu-id="68b5c-132">**Grid view.**</span></span> <span data-ttu-id="68b5c-133">: 左側の送信元スキーマ ツリー ビューと右側の送信先スキーマ ツリー ビューの間にあるビューです。送信元スキーマ ツリー ビュー、送信先スキーマ ツリー ビュー、およびグリッド ビューは、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] のメイン編集ウィンドウを共有します。</span><span class="sxs-lookup"><span data-stu-id="68b5c-133">This view shares the main [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] editing window with the source schema tree view and the destination schema tree view, with the source schema tree view to the left and the destination schema tree view to the right.</span></span>  
  
   <span data-ttu-id="68b5c-134">名前が示すように、このビューはマップの定義で重要な役割を果たし、リンクと Functoid が表示されます。リンクと Functoid は、送信元インスタンス メッセージのデータを送信先スキーマに準拠するインスタンス メッセージに変換する方法を制御します。</span><span class="sxs-lookup"><span data-stu-id="68b5c-134">As the name suggests, this view plays a critical role in the definition of maps, containing the links and functoids that control how data in a source instance message is transformed into an instance message that conforms to the destination schema.</span></span>  
  
   <span data-ttu-id="68b5c-135">グリッド ビューは、グリッド ページと呼ばれる複数の層を持つ場合があります。この層によって、複雑なマップを細分して論理的なマッピングに構成できます。</span><span class="sxs-lookup"><span data-stu-id="68b5c-135">The grid view can have multiple layers, called grid pages, allowing you to organize complex maps into logical subdivisions of mappings.</span></span> <span data-ttu-id="68b5c-136">通常は、グリッド ページは一度に表示できないため、グリッド ページのスクロールを行うための効率的な方法がいくつか用意されています。</span><span class="sxs-lookup"><span data-stu-id="68b5c-136">Grid pages generally use more space than can be displayed at one time, and there are several effective ways to scroll within a grid page.</span></span>  
  
   <span data-ttu-id="68b5c-137">マップを構築するには、このビューをアクティブ状態にして操作します。</span><span class="sxs-lookup"><span data-stu-id="68b5c-137">You actively work in this view to construct your map.</span></span>  
  
- <span data-ttu-id="68b5c-138">**Visual Studio ツールボックス ウィンドウ**</span><span class="sxs-lookup"><span data-stu-id="68b5c-138">**Visual Studio Toolbox window.**</span></span> <span data-ttu-id="68b5c-139">: このビューには BizTalk マップで使用可能な Functoid が表示され、ここから Functoid をドラッグ アンド ドロップして、グリッド ページに配置できます。</span><span class="sxs-lookup"><span data-stu-id="68b5c-139">You use this view to display the functoids available for use in BizTalk maps, and as the source of the drag-and-drop operations to place functoids in a grid page.</span></span>  
  
   <span data-ttu-id="68b5c-140">ツールボックスに表示される Functoid は、カテゴリに応じて分けられています。</span><span class="sxs-lookup"><span data-stu-id="68b5c-140">The functoids shown in the Toolbox are organized according to their categories.</span></span> <span data-ttu-id="68b5c-141">使用可能な functoid の詳細については、[マップの Functoid](../core/functoids-in-maps.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="68b5c-141">For more information about the available functoids, see [Functoids in Maps](../core/functoids-in-maps.md).</span></span> <span data-ttu-id="68b5c-142">また、 **Functoid リファレンス**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。</span><span class="sxs-lookup"><span data-stu-id="68b5c-142">Also see the **Functoid Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span> 
  
- <span data-ttu-id="68b5c-143">**Visual Studio プロパティ ウィンドウ。**</span><span class="sxs-lookup"><span data-stu-id="68b5c-143">**Visual Studio Properties window.**</span></span> <span data-ttu-id="68b5c-144">: このビューおよび関連付けられたダイアログ ボックスを使用して、マップを定義するために作成したリンクおよび Functoid のプロパティの確認と設定を行います。</span><span class="sxs-lookup"><span data-stu-id="68b5c-144">You use this view, and its associated dialog boxes, to examine and set the properties of the links and functoids that you create to define your map.</span></span>  
  
   <span data-ttu-id="68b5c-145">グリッド ビューでグリッド ページでリンクまたは functoid を選択すると送信元または送信先スキーマ ツリー ビュー、スキーマのノードを選択するかでマップを選択、**ソリューション エクスプ ローラー**ウィンドウ; のリンク、functoid の対応するプロパティスキーマ ノード、またはマップに表示されます、**プロパティ**ウィンドウが Visual Studio の標準の規則を使用します。</span><span class="sxs-lookup"><span data-stu-id="68b5c-145">When you select a link or functoid in a grid page in the Grid view, select a schema node in the source or destination schema tree views, or select a map in the **Solution Explorer** window; the corresponding properties of that link, functoid, schema node, or map appear in the **Properties** window using the standard Visual Studio conventions.</span></span> <span data-ttu-id="68b5c-146">たとえば、プロパティは、カテゴリごとにグループ化されていたり、カテゴリ順またはアルファベット順に従って表示されたりします。</span><span class="sxs-lookup"><span data-stu-id="68b5c-146">For example, the properties are grouped into categories, and can be displayed according to these categories or alphabetically.</span></span>  
  
   <span data-ttu-id="68b5c-147">異なるリンク、functoid、スキーマのノードまたはマップ自体で利用可能なプロパティのセットの詳細については、次を参照してください、**マップ プロパティ参照**と**スキーマ プロパティのリファレンス**。[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].  </span><span class="sxs-lookup"><span data-stu-id="68b5c-147">For detailed information about the different sets of properties that are available for links, functoids, schema nodes, or the map itself, see the **Map Property Reference** and the **Schema Property Reference**  [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
- <span data-ttu-id="68b5c-148">**Visual Studio タスク一覧ウィンドウと出力ウィンドウ。**</span><span class="sxs-lookup"><span data-stu-id="68b5c-148">**Visual Studio Task List and Output windows.**</span></span> <span data-ttu-id="68b5c-149">: これらのビューは、BizTalk マップの検証、コンパイルおよびテストの結果を確認するために使用します。使用方法は、ソース コードのコンパイル時や、その他の種類のプロジェクトのビルド時にこれらのビューを使用する方法とほぼ同じです。</span><span class="sxs-lookup"><span data-stu-id="68b5c-149">You use these views to examine the results of validating, compiling, and testing your BizTalk maps in much the same way that these views are used when compiling source code and building other types of projects.</span></span>  
  
  <span data-ttu-id="68b5c-150">これらのビュー以外にも、いくつかのダイアログ ボックスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="68b5c-150">In addition to these views, you can interact with several dialog boxes.</span></span> <span data-ttu-id="68b5c-151">通常は、Functoid の入力パラメーターなど複雑なプロパティを編集する場合に、これらのダイアログ ボックスが開きます。</span><span class="sxs-lookup"><span data-stu-id="68b5c-151">You usually open these dialog boxes when you are editing a complex property such as the input parameters to a functoid.</span></span>  
  
  <span data-ttu-id="68b5c-152">BizTalk マッパーと共に、[ソリューション エクスプローラー] ウィンドウを使用する場合があります。</span><span class="sxs-lookup"><span data-stu-id="68b5c-152">You often use the Solution Explorer window in conjunction with BizTalk Mapper.</span></span> <span data-ttu-id="68b5c-153">たとえば、新しいマップを作成するで BizTalk プロジェクトを右クリックし、**ソリューション エクスプ ローラー**ウィンドウで、をクリックして**追加**、 をクリックして**新しい項目の追加**、しを使用して、 **新しい項目の追加** ダイアログ ボックスに名前を付けて、新しいマップを作成します。</span><span class="sxs-lookup"><span data-stu-id="68b5c-153">For example, to create a new map, right-click the BizTalk project in the **Solution Explorer** window, click **Add**, click **Add New Item**, and then use the **Add New Item** dialog box to name and create a new map.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="68b5c-154">次のステップ</span><span class="sxs-lookup"><span data-stu-id="68b5c-154">Next steps</span></span>
  
-   [<span data-ttu-id="68b5c-155">BizTalk マッパー コマンドの使用</span><span class="sxs-lookup"><span data-stu-id="68b5c-155">Using BizTalk Mapper Commands</span></span>](../core/using-biztalk-mapper-commands.md)  
  
-   [<span data-ttu-id="68b5c-156">グリッド ページの操作</span><span class="sxs-lookup"><span data-stu-id="68b5c-156">Working with Grid Pages</span></span>](../core/working-with-grid-pages.md)  
  
-   [<span data-ttu-id="68b5c-157">ビューを管理する方法</span><span class="sxs-lookup"><span data-stu-id="68b5c-157">How to Manage Views</span></span>](../core/how-to-manage-views.md)  
  
-   [<span data-ttu-id="68b5c-158">色とフォントの BizTalk マッパーをカスタマイズする方法</span><span class="sxs-lookup"><span data-stu-id="68b5c-158">How to Customize Colors and Font in BizTalk Mapper</span></span>](../core/how-to-customize-colors-and-font-in-biztalk-mapper.md)  
  
-   [<span data-ttu-id="68b5c-159">展開し、スキーマ ツリーを折りたたむ方法</span><span class="sxs-lookup"><span data-stu-id="68b5c-159">How to Expand and Collapse the Schema Trees</span></span>](../core/how-to-resize-the-schema-picker-and-expand-and-collapse-the-schema-trees.md)  
  
-   [<span data-ttu-id="68b5c-160">元に戻すまたはユーザーの操作を再実行する方法</span><span class="sxs-lookup"><span data-stu-id="68b5c-160">How to Undo or Redo User Operations</span></span>](../core/how-to-undo-or-redo-user-operations.md)  
  
-   [<span data-ttu-id="68b5c-161">マップ項目を検索する方法</span><span class="sxs-lookup"><span data-stu-id="68b5c-161">How to Search for Map Items</span></span>](../core/how-to-search-for-map-items.md)  
  
-   [<span data-ttu-id="68b5c-162">BizTalk マッパーの強化された機能の使用</span><span class="sxs-lookup"><span data-stu-id="68b5c-162">Using Enhanced Features in BizTalk Mapper</span></span>](../core/using-enhanced-features-in-biztalk-mapper.md)  
  
-   [<span data-ttu-id="68b5c-163">ヒントとツールヒントを表示する方法</span><span class="sxs-lookup"><span data-stu-id="68b5c-163">How to View Infotip and Tooltip</span></span>](../core/how-to-view-infotip-and-tooltip.md)  
  
## <a name="see-also"></a><span data-ttu-id="68b5c-164">参照</span><span class="sxs-lookup"><span data-stu-id="68b5c-164">See Also</span></span>  
 [<span data-ttu-id="68b5c-165">リンクの表示を最適化する方法</span><span class="sxs-lookup"><span data-stu-id="68b5c-165">How to Optimize the Display of Links</span></span>](../core/how-to-optimize-the-display-of-links.md)