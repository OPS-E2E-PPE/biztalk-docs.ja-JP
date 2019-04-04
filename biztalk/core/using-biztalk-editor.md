---
title: BizTalk エディターを使用して |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 22021272-f028-4db3-ad8a-fb89a5340910
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2f1f85fa69e07f252aa732d868353609ed065fbf
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007163"
---
# <a name="using-biztalk-editor"></a><span data-ttu-id="f4fe2-102">BizTalk エディターの使用</span><span class="sxs-lookup"><span data-stu-id="f4fe2-102">Using BizTalk Editor</span></span>

## <a name="overview"></a><span data-ttu-id="f4fe2-103">概要</span><span class="sxs-lookup"><span data-stu-id="f4fe2-103">Overview</span></span>
<span data-ttu-id="f4fe2-104">BizTalk エディターは、Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] シェルの一部です。</span><span class="sxs-lookup"><span data-stu-id="f4fe2-104">BizTalk Editor resides within the Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] shell.</span></span> <span data-ttu-id="f4fe2-105">BizTalk エディターの一部の機能は、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] シェルの既存のユーザー インターフェイス要素を利用しています。</span><span class="sxs-lookup"><span data-stu-id="f4fe2-105">Some of the functionality within BizTalk Editor relies upon existing user interface elements within the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] shell.</span></span> <span data-ttu-id="f4fe2-106">たとえば、使用する、**ファイル**、**編集**と**ビュー**で他の開発の場合と同様のメニューは[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="f4fe2-106">For example, you use the **File**, **Edit**, and **View** menus just as you would for other development within [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="f4fe2-107">この共通の機能についての情報は、**ヘルプ**メニュー。</span><span class="sxs-lookup"><span data-stu-id="f4fe2-107">Information about this common functionality is available from the **Help** menu.</span></span>  
  
 <span data-ttu-id="f4fe2-108">BizTalk エディターは、新しいスキーマを BizTalk プロジェクトに追加した場合、BizTalk プロジェクトで既存のスキーマ (.xsd ファイル) を開いた場合、または [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] のメイン編集ウィンドウでスキーマのタブをクリックしてスキーマを再アクティブ化した場合にアクティブになります。</span><span class="sxs-lookup"><span data-stu-id="f4fe2-108">BizTalk Editor becomes active when you add a new schema to a BizTalk project, when you open an existing schema (an .xsd file) within a BizTalk project, or when you reactivate a schema by clicking its tab in the main [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] editing window.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f4fe2-109">BizTalk エディターでは、UTF-16 文字エンコードを使用してスキーマ ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="f4fe2-109">BizTalk Editor saves schema files using utf-16 character encoding.</span></span>  

## <a name="views"></a><span data-ttu-id="f4fe2-110">ビュー</span><span class="sxs-lookup"><span data-stu-id="f4fe2-110">Views</span></span>  
 <span data-ttu-id="f4fe2-111">次の図は、BizTalk エディターの一部である Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] シェルのさまざまなビューを示しています。</span><span class="sxs-lookup"><span data-stu-id="f4fe2-111">The following figure shows the various views within the Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] shell that are part of BizTalk Editor.</span></span>  
  
 <span data-ttu-id="f4fe2-112">![BizTalk プロジェクトのさまざまな部分](../core/media/differentpartsofbiztalkserver.gif "DifferentpartsofBizTalkServer")</span><span class="sxs-lookup"><span data-stu-id="f4fe2-112">![Different Parts of BizTalk Project](../core/media/differentpartsofbiztalkserver.gif "DifferentpartsofBizTalkServer")</span></span>  
  
 <span data-ttu-id="f4fe2-113">BizTalk エディターは、Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] シェルの次のビューと関連するダイアログ ボックスで構成されます。</span><span class="sxs-lookup"><span data-stu-id="f4fe2-113">BizTalk Editor consists of the following views within the Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] shell and their associated dialog boxes:</span></span>  
  
- <span data-ttu-id="f4fe2-114">**スキーマ ツリー。**</span><span class="sxs-lookup"><span data-stu-id="f4fe2-114">**Schema Tree.**</span></span> <span data-ttu-id="f4fe2-115">このビューは、メインの左側にある[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ウィンドウを編集します。</span><span class="sxs-lookup"><span data-stu-id="f4fe2-115">This view is on the left side of the main [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] editing window.</span></span> <span data-ttu-id="f4fe2-116">スキーマで定義されるメッセージの構造を示すツリー構造を構築すると、このビューでスキーマがアクティブに作成されます。</span><span class="sxs-lookup"><span data-stu-id="f4fe2-116">You actively construct your schema in this view by building up the tree structure that describes the structure of the message that the schema defines.</span></span> <span data-ttu-id="f4fe2-117">スキーマ ツリー ビューでの BizTalk スキーマの表現方法の詳細については、[スキーマの BizTalk 表記](../core/biztalk-representation-of-schemas.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f4fe2-117">For more information about how BizTalk schemas are represented in the schema tree view, see [BizTalk Representation of Schemas](../core/biztalk-representation-of-schemas.md).</span></span>  
  
- <span data-ttu-id="f4fe2-118">**XSD を表示します。**</span><span class="sxs-lookup"><span data-stu-id="f4fe2-118">**XSD View.**</span></span> <span data-ttu-id="f4fe2-119">このビューは、メインの右側にある[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ウィンドウを編集します。</span><span class="sxs-lookup"><span data-stu-id="f4fe2-119">This view is on the right side of the main [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] editing window.</span></span> <span data-ttu-id="f4fe2-120">スキーマ ツリー ビューに構築されているスキーマを表す XSD (XML Schema Definition ) 言語構造を示します。</span><span class="sxs-lookup"><span data-stu-id="f4fe2-120">It shows the XML Schema definition (XSD) language structure that represents the schema you are constructing in the schema tree view.</span></span> <span data-ttu-id="f4fe2-121">このビューは読み取り専用で、作成するスキーマの XSD 構文を理解するためのものです。</span><span class="sxs-lookup"><span data-stu-id="f4fe2-121">This view is read-only and is provided to help you become accustomed to the XSD syntax of the schema you are creating.</span></span> <span data-ttu-id="f4fe2-122">必要に応じて、ビューの分割機能を使用して、XSD ビューの表示を調整できます。</span><span class="sxs-lookup"><span data-stu-id="f4fe2-122">If you prefer, you can adjust the view splitter so that the XSD view only barely visible.</span></span>  
  
- <span data-ttu-id="f4fe2-123">**ソリューション エクスプ ローラー。**</span><span class="sxs-lookup"><span data-stu-id="f4fe2-123">**Solution Explorer.**</span></span> <span data-ttu-id="f4fe2-124">このビューが右側にあるは、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]シェルです。</span><span class="sxs-lookup"><span data-stu-id="f4fe2-124">This view is on the right side of the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] shell.</span></span> <span data-ttu-id="f4fe2-125">BizTalk プロジェクトと BizTalk プロジェクトに含まれるさまざまな項目が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f4fe2-125">It shows the BizTalk project and the various items it contains.</span></span> <span data-ttu-id="f4fe2-126">ソリューション エクスプローラーを使用して、新しいスキーマおよび既存のスキーマをプロジェクトに追加したり、プロジェクトの一部であるスキーマを開いたりできます。</span><span class="sxs-lookup"><span data-stu-id="f4fe2-126">Use Solution Explorer to add new and existing schemas to the project, and to open schemas that are already part of the project.</span></span> <span data-ttu-id="f4fe2-127">たとえば、新しいスキーマを作成するソリューション エクスプ ローラー ウィンドウで、BizTalk プロジェクトを右クリックし、 をクリックして**追加**、 をクリックして**新しい項目の**、しを使用して、**新しい項目の追加**ダイアログ新しいスキーマを作成して名前をボックスです。</span><span class="sxs-lookup"><span data-stu-id="f4fe2-127">For example, to create a new schema, right-click the BizTalk project in the Solution Explorer window, click **Add**, click **New Item**, and then use the **Add New Item** dialog box to name and create a new schema.</span></span>  
  
- [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]  <span data-ttu-id="f4fe2-128">**プロパティ ウィンドウ。**</span><span class="sxs-lookup"><span data-stu-id="f4fe2-128">**Properties window.**</span></span> <span data-ttu-id="f4fe2-129">: このビューを使用して、ほとんどのスキーマ プロパティおよびノード プロパティの確認および設定を行います。</span><span class="sxs-lookup"><span data-stu-id="f4fe2-129">You use this view to examine and set most of the schema and node properties.</span></span> <span data-ttu-id="f4fe2-130">スキーマ ツリー ビューのノードまたは [ソリューション エクスプローラー] ウィンドウのスキーマを選択すると、ノードやスキーマに対応するプロパティが標準の Visual Studio パラダイムで [プロパティ] ウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="f4fe2-130">When you select a node in the schema tree view, or select a schema in the Solution Explorer window, the corresponding properties of that node or schema are displayed in the Properties window using the standard Visual Studio paradigms.</span></span> <span data-ttu-id="f4fe2-131">たとえば、プロパティは、カテゴリごとにグループ化されていたり、カテゴリ順またはアルファベット順に従って表示されたりします。</span><span class="sxs-lookup"><span data-stu-id="f4fe2-131">For example, the properties are grouped into categories, and can be displayed according to these categories or alphabetically.</span></span> <span data-ttu-id="f4fe2-132">異なるさまざまな種類のノード、または、スキーマが選択されているときに使用できるプロパティのセットの詳細については、、**スキーマ プロパティのリファレンス**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f4fe2-132">For detailed information about the different sets of properties that are available when different types of nodes, or the schema, are selected, see the **Schema Property Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
  <span data-ttu-id="f4fe2-133">これらのビュー以外にも、いくつかのダイアログ ボックスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="f4fe2-133">In addition to these views, you can interact with several dialog boxes.</span></span> <span data-ttu-id="f4fe2-134">通常、このようなダイアログ ボックスは、コレクションなど複雑なプロパティを編集する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="f4fe2-134">You usually open these dialog boxes when you are editing a complex property such as a collection.</span></span>  
  
  <span data-ttu-id="f4fe2-135">このセクションでは、BizTalk エディターで使用できるビュー、コマンド、およびショートカット キーに関する情報について説明します。</span><span class="sxs-lookup"><span data-stu-id="f4fe2-135">This section provides information about the views, commands, and shortcut keys available in BizTalk Editor.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="f4fe2-136">次のステップ</span><span class="sxs-lookup"><span data-stu-id="f4fe2-136">Next steps</span></span> 
  
-   [<span data-ttu-id="f4fe2-137">スキーマ ツリー ビューを管理する方法</span><span class="sxs-lookup"><span data-stu-id="f4fe2-137">How to Manage the Schema Tree View</span></span>](../core/how-to-manage-the-schema-tree-view.md)  
  
-   [<span data-ttu-id="f4fe2-138">XSD ビューを管理する方法</span><span class="sxs-lookup"><span data-stu-id="f4fe2-138">How to Manage the XSD View</span></span>](../core/how-to-manage-the-xsd-view.md)  
  
-   <span data-ttu-id="f4fe2-139">[[プロパティ] ウィンドウを管理する方法](../core/how-to-manage-the-properties-window.md)</span><span class="sxs-lookup"><span data-stu-id="f4fe2-139">[How to Manage the Properties Window](../core/how-to-manage-the-properties-window.md)</span></span>  
  
-   [<span data-ttu-id="f4fe2-140">その他の Visual Studio の Windows を管理する方法</span><span class="sxs-lookup"><span data-stu-id="f4fe2-140">How to Manage Other Visual Studio Windows</span></span>](../core/how-to-manage-other-visual-studio-windows.md)  
  
-   [<span data-ttu-id="f4fe2-141">BizTalk エディター コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="f4fe2-141">Using BizTalk Editor Commands</span></span>](../core/using-biztalk-editor-commands.md)  
  
-   [<span data-ttu-id="f4fe2-142">大きなスキーマの操作</span><span class="sxs-lookup"><span data-stu-id="f4fe2-142">Working with Large Schemas</span></span>](../core/working-with-large-schemas.md)