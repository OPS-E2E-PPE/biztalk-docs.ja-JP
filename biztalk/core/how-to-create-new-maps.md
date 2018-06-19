---
title: 新しいマップを作成する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 43b36cd8-f28e-4349-87d5-c94b7d8761bf
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 910d79782f4332ae1d706e12a8c5dda8c399a41b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249874"
---
# <a name="how-to-create-new-maps"></a><span data-ttu-id="16b70-102">新しいマップを作成する方法</span><span class="sxs-lookup"><span data-stu-id="16b70-102">How to Create New Maps</span></span>

## <a name="overview"></a><span data-ttu-id="16b70-103">概要</span><span class="sxs-lookup"><span data-stu-id="16b70-103">Overview</span></span>
<span data-ttu-id="16b70-104">新しい BizTalk マップを作成するための手順は、大きく次の 3 つに分けられます。</span><span class="sxs-lookup"><span data-stu-id="16b70-104">To build a new BizTalk map, there are three high-level steps to perform:</span></span>  
  
1.  <span data-ttu-id="16b70-105">BizTalk プロジェクト内に新しいマップを作成する。</span><span class="sxs-lookup"><span data-stu-id="16b70-105">Create the new map within a BizTalk project.</span></span>  
  
2.  <span data-ttu-id="16b70-106">送信元と送信先スキーマをマップに追加します。</span><span class="sxs-lookup"><span data-stu-id="16b70-106">Add the source and destination schemas to the map.</span></span>  
  
3.  <span data-ttu-id="16b70-107">一連のリンクを構築したり、中間処理を行う Functoid を必要に応じて構築することにより、送信元スキーマと送信先スキーマとのマッピング方法を指定する。</span><span class="sxs-lookup"><span data-stu-id="16b70-107">Build the set of links and, perhaps, intermediate functoids specifying how the source schema maps to the destination schema.</span></span>  
  
 <span data-ttu-id="16b70-108">この説明では、最初の 2 つの手順は、マップを "作成" する手順として扱い、</span><span class="sxs-lookup"><span data-stu-id="16b70-108">In the current context, the first two of these three steps is considered "creating" the map.</span></span> <span data-ttu-id="16b70-109">3 つ目の手順はマップを "構築" する手順として扱っています。</span><span class="sxs-lookup"><span data-stu-id="16b70-109">The third step is considered "building" the map.</span></span> <span data-ttu-id="16b70-110">マップの構築プロセスに関連するタスクの多くの詳しい手順については、「 [Functoid 作成複雑なマッピングを使用した](../core/using-functoids-to-create-more-complex-mappings.md)です。</span><span class="sxs-lookup"><span data-stu-id="16b70-110">For step-by-step instructions on many of the tasks related to the process of building the map, see [Using Functoids to Create More Complex Mappings](../core/using-functoids-to-create-more-complex-mappings.md).</span></span>  
  
## <a name="create-a-new-map"></a><span data-ttu-id="16b70-111">新しいマップを作成します。</span><span class="sxs-lookup"><span data-stu-id="16b70-111">Create a new map</span></span> 
  
1.  <span data-ttu-id="16b70-112">ソリューション エクスプ ローラーで、選択で、BizTalk プロジェクトを右クリックして**追加**、し、**新しい項目の**します。</span><span class="sxs-lookup"><span data-stu-id="16b70-112">Right-click a BizTalk project in Solution Explorer, select **Add**, and then select **New Item**.</span></span>  
  
2.  <span data-ttu-id="16b70-113">**新しい項目の追加** ダイアログ ボックスで、**テンプレート**領域で、**マップ**です。</span><span class="sxs-lookup"><span data-stu-id="16b70-113">In the **Add New Item** dialog box, in the **Templates** area, select **Map**.</span></span>  
  
3.  <span data-ttu-id="16b70-114">テキストを選択、**名前**ボックスに、マップの名前を入力し、選択**追加**です。</span><span class="sxs-lookup"><span data-stu-id="16b70-114">Select the text in the **Name** box, type a name for the map, and then select **Add**.</span></span>  
  
     <span data-ttu-id="16b70-115">Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] の編集ウィンドウに BizTalk マッパーが開き、3 つのペインが隣り合わせに表示されます。</span><span class="sxs-lookup"><span data-stu-id="16b70-115">BizTalk Mapper opens in the Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] editing window, showing three distinct panes, side-by-side.</span></span> <span data-ttu-id="16b70-116">これらのペインに表示される内容は、左から送信元スキーマ、グリッド、および送信先スキーマです。グリッドには、複数のページが表示される場合もあります。</span><span class="sxs-lookup"><span data-stu-id="16b70-116">From left to right, these panes show the source schema, the grid (which may have multiple pages), and the destination schema.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="16b70-117">マップに次の名前を使用することはできません:"XmlContent"、"SourceSchemas"、"TargetSchemas"、または"XsltArgumentListContent"です。</span><span class="sxs-lookup"><span data-stu-id="16b70-117">You cannot use the following names for maps: "XmlContent", "SourceSchemas", "TargetSchemas", or "XsltArgumentListContent".</span></span> <span data-ttu-id="16b70-118">これは、.NET アセンブリへコンパイルするとき、C# コードの生成で名前付けの制限の影響を受けるためです。</span><span class="sxs-lookup"><span data-stu-id="16b70-118">These names cannot be used because compilation into a .NET assembly produces naming restrictions as the result of generated C# code.</span></span>  
  
4.  <span data-ttu-id="16b70-119">BizTalk マッパーで、左ペインで選択**ソース スキーマを開く**です。</span><span class="sxs-lookup"><span data-stu-id="16b70-119">In BizTalk Mapper, in the left pane, select **Open Source Schema**.</span></span>  
  
5.  <span data-ttu-id="16b70-120">**BizTalk 型の選択**] ダイアログ ボックスで、展開、**スキーマ**ノードは、適切な送信元スキーマを選択し、[ **OK**です。</span><span class="sxs-lookup"><span data-stu-id="16b70-120">In the **BizTalk Type Picker** dialog box, expand the **Schemas** node, select the appropriate source schema, and then select **OK**.</span></span>  

    > [!TIP] 
    > <span data-ttu-id="16b70-121">**以降で[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]** スキーマの完全な名前を表示する型の選択 ウィンドウのサイズを変更することができます。</span><span class="sxs-lookup"><span data-stu-id="16b70-121">**Starting with [!INCLUDE[bts2016_md](../includes/bts2016-md.md)]**, you can resize the Type Picker window to see the full name of your schema.</span></span>
  
     <span data-ttu-id="16b70-122">送信元スキーマの単一のルートが存在するかを使用して、スキーマのルート ノードが設定された場合のみ、**ルート参照**のプロパティ、**スキーマ**ノード、送信元スキーマが左側のウィンドウで開きます手順 7. に進むことができます。</span><span class="sxs-lookup"><span data-stu-id="16b70-122">If only a single root exists in the source schema, or a root node has been established for the schema using the **Root Reference** property of the **Schema** node, the source schema opens in the left pane, and you can proceed to step 7.</span></span>  
  
6.  <span data-ttu-id="16b70-123">ソース スキーマに複数のルート ノードと、ソースを使用してスキーマのルート ノードが設定されていないかどうか、**スキーマ**ノードの**ルート参照**プロパティで、**ソースのルート ノードスキーマ**ダイアログ ボックスで、適切なルート ノードを選択し、選択**OK**です。</span><span class="sxs-lookup"><span data-stu-id="16b70-123">If the source schema has multiple root nodes, and no root node has been established for the source schema using the **Schema** node's **Root Reference** property, in the **Root Node for Source Schema** dialog box, select the appropriate root node, and select **OK**.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="16b70-124">BizTalk マッパーでスキーマのルート ノードを選択し、後で変更する場合、**ルート参照**プロパティ スキーマを次に、BizTalk マッパーでスキーマを開いたときに構成されている新しいルート参照 をルート ノードは更新されませんBizTalk エディターです。</span><span class="sxs-lookup"><span data-stu-id="16b70-124">If you choose a root node for a schema in BizTalk Mapper and then later change the **Root Reference** property in the schema, the next time you open the schema in BizTalk Mapper, the root node will not update to the new root reference configured in BizTalk Editor.</span></span>  
  
7.  <span data-ttu-id="16b70-125">BizTalk マッパーの右側のペインで選択**送信先スキーマを開く**です。</span><span class="sxs-lookup"><span data-stu-id="16b70-125">In BizTalk Mapper, in the right pane, select **Open Destination Schema**.</span></span>  
  
8.  <span data-ttu-id="16b70-126">**BizTalk 型の選択**] ダイアログ ボックスで、展開、**スキーマ**ノード ツリーで、必要に応じて、適切な送信先スキーマを選択し、[ **OK**です。</span><span class="sxs-lookup"><span data-stu-id="16b70-126">In the **BizTalk Type Picker** dialog box, expand the **Schema** node in the tree, if necessary, select the appropriate destination schema, and then select **OK**.</span></span>  
  
     <span data-ttu-id="16b70-127">送信先スキーマの単一のルートが存在するか、変換先を使用してスキーマのルート ノードが設定された場合のみ、**ルート参照**のプロパティ、**スキーマ**ノード、送信先スキーマが開きます右側のウィンドウで、手順 9. を実行する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="16b70-127">If only a single root exists in the destination schema, or a root node has been established for the destination schema using the **Root Reference** property of the **Schema** node, the destination schema opens in the right pane, and you will not need to perform step 9.</span></span>  
  
9. <span data-ttu-id="16b70-128">送信先スキーマが複数のルート ノードと、変換先を使用してスキーマのルート ノードが設定されていないかどうか、**ルート参照**のプロパティ、**スキーマ**ノードで、**ルート ノードターゲット スキーマの**ダイアログ ボックスで、適切なルート ノードを選択し、選択**OK**です。</span><span class="sxs-lookup"><span data-stu-id="16b70-128">If the destination schema has multiple root nodes, and no root node has been established for the destination schema using the **Root Reference** property of the **Schema** node, in the **Root Node for Target Schema** dialog box, select the appropriate root node, and select **OK**.</span></span>  
  
     <span data-ttu-id="16b70-129">右ペインに送信先スキーマが開きます。</span><span class="sxs-lookup"><span data-stu-id="16b70-129">The destination schema opens in the right pane.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16b70-130">参照</span><span class="sxs-lookup"><span data-stu-id="16b70-130">See Also</span></span>  
 [<span data-ttu-id="16b70-131">プロジェクト内のマップを管理します。</span><span class="sxs-lookup"><span data-stu-id="16b70-131">Managing Maps Within Projects</span></span>](../core/managing-maps-within-projects.md)