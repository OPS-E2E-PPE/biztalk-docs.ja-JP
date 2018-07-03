---
title: パイプライン デザイナーの使用 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Pipeline Designer, how to
- pipelines, Pipeline Designer
ms.assetid: bdb2f5c7-f8a2-4bd6-a8d8-8b7a64f97bd0
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0f5a3e2d9d3dad37372fc01f6446f0c06272589a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37019024"
---
# <a name="using-pipeline-designer"></a><span data-ttu-id="5f935-102">パイプライン デザイナーの使用</span><span class="sxs-lookup"><span data-stu-id="5f935-102">Using Pipeline Designer</span></span>
<span data-ttu-id="5f935-103">パイプライン デザイナーとは、Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] でホストされるグラフィカル エディターのことで、パイプラインの新規作成、Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に付属するパイプライン テンプレートの表示、パイプライン内でのパイプライン コンポーネントの移動のほか、パイプライン、ステージ、パイプライン コンポーネントの構成などを実行できます。</span><span class="sxs-lookup"><span data-stu-id="5f935-103">Pipeline Designer is a graphical editor, hosted in Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], which enables you to create new pipelines; view the pipeline templates included with Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]; move pipeline components within a pipeline; and configure pipelines, stages, and pipeline components.</span></span>  
  
 <span data-ttu-id="5f935-104">パイプライン デザイナーは、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] シェルが備える 3 つのツールを使ってデザイン作業をサポートします。</span><span class="sxs-lookup"><span data-stu-id="5f935-104">Pipeline Designer uses three key tools of the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] shell as part of the design experience:</span></span>  
  
- <span data-ttu-id="5f935-105">プロパティ ウィンドウ。パイプライン オブジェクトの特性の多くは、このウィンドウで表示したり変更したりできます。</span><span class="sxs-lookup"><span data-stu-id="5f935-105">The Properties window, where most of the characteristics of pipeline objects are viewed and modified.</span></span>  
  
- <span data-ttu-id="5f935-106">ツールボックス。デザイン画面のソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="5f935-106">The Toolbox, which is used as a source for the design surface.</span></span>  
  
- <span data-ttu-id="5f935-107">デザイン画面。ツールボックスのコンポーネントはデザイン画面にドラッグ アンド ドロップされます。</span><span class="sxs-lookup"><span data-stu-id="5f935-107">The design surface, where components from the Toolbox are dragged and dropped.</span></span>  
  
  <span data-ttu-id="5f935-108">次の図は、パイプライン デザイナーの環境を示しています。</span><span class="sxs-lookup"><span data-stu-id="5f935-108">The following figure shows the Pipeline Designer environment.</span></span>  
  
  <span data-ttu-id="5f935-109">![パイプライン デザイナー編集環境](../core/media/ebiz-prog-usepipe.gif "ebiz_prog_usepipe")</span><span class="sxs-lookup"><span data-stu-id="5f935-109">![The Pipeline Designer editing environment](../core/media/ebiz-prog-usepipe.gif "ebiz_prog_usepipe")</span></span>  
  <span data-ttu-id="5f935-110">パイプライン デザイナーの環境</span><span class="sxs-lookup"><span data-stu-id="5f935-110">Depicts the Pipeline Designer environment.</span></span>  
  
  <span data-ttu-id="5f935-111">開発作業をより効率化するため、パイプライン デザイナーは、BizTalk プロジェクト テンプレートと統合されます。</span><span class="sxs-lookup"><span data-stu-id="5f935-111">Pipeline Designer is integrated with the BizTalk project template to enhance your development experience.</span></span> <span data-ttu-id="5f935-112">新しい BizTalk プロジェクトを作成するプロジェクト システムを使用して後で使用できます、**新しい項目の追加**コマンドを**ファイル**パイプラインをソリューションに追加するメニュー。</span><span class="sxs-lookup"><span data-stu-id="5f935-112">After using the project system to create a new BizTalk project, you can use the **Add New Item** command on the **File** menu to add a pipeline to your solution.</span></span> <span data-ttu-id="5f935-113">BizTalk プロジェクト テンプレートの詳細については、次を参照してください。 [BizTalk プロジェクト システムを使用して](../core/using-the-biztalk-project-system.md)します。</span><span class="sxs-lookup"><span data-stu-id="5f935-113">For more information about the BizTalk project template, see [Using the BizTalk Project System](../core/using-the-biztalk-project-system.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5f935-114">以前のバージョンの [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、パイプラインの概念が、メッセージ チャネルおよびポートとしてカプセル化され、ドキュメントに適用される特定のコンポーネントの順序も、このメッセージ チャネルとポートによって定義されていました。</span><span class="sxs-lookup"><span data-stu-id="5f935-114">In previous versions of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], the concept of a pipeline was encapsulated in message channels and ports, which defined a set order of specific components that were applied to a document.</span></span> <span data-ttu-id="5f935-115">新しいバージョンでは、パイプラインによって柔軟性が向上しています。パイプラインの各ステージに含まれるコンポーネントの順序を自由に変更できるほか、パイプラインのいたるところにカスタム コンポーネントを容易に挿入できます。</span><span class="sxs-lookup"><span data-stu-id="5f935-115">In this version, the pipeline is flexible because you are free to reorder the components in each stage of the pipeline and can easily insert multiple custom components throughout the pipeline.</span></span>  
  
 <span data-ttu-id="5f935-116">パイプライン デザイナーのデザイン画面では、パイプラインをグラフィカルに表現できます。</span><span class="sxs-lookup"><span data-stu-id="5f935-116">The Pipeline Designer design surface enables you to draw a graphical representation of a pipeline.</span></span> <span data-ttu-id="5f935-117">デザイン画面は、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] ウィンドウのメイン セクションに表示され、この画面を使って、BizTalk プロジェクトに含まれるパイプラインを編集できます。</span><span class="sxs-lookup"><span data-stu-id="5f935-117">The design surface occupies the main section of the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] window and enables you to edit the pipelines belonging to a BizTalk project.</span></span> <span data-ttu-id="5f935-118">またデザイン画面のタブをクリックすることにより、複数のパイプラインを切り替えて表示できます。</span><span class="sxs-lookup"><span data-stu-id="5f935-118">You can navigate between pipelines by clicking the tabs above the design surface.</span></span>  
  
 <span data-ttu-id="5f935-119">各パイプラインはステージで構成され、各ステージには、少なくとも 1 つのコンポーネントが含まれます。</span><span class="sxs-lookup"><span data-stu-id="5f935-119">Each pipeline is composed of stages, with each stage containing one or more components.</span></span> <span data-ttu-id="5f935-120">ステージにコンポーネントが存在しない場合は、ツールボックスから図形を挿入するよう促す警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5f935-120">If there are no components in a stage, a watermark with text indicates that shapes can be inserted from the Toolbox.</span></span> <span data-ttu-id="5f935-121">この警告は、1 つ目の図形をステージに挿入した時点で消えます。</span><span class="sxs-lookup"><span data-stu-id="5f935-121">When the first shape is inserted into a stage, the initial text disappears.</span></span> <span data-ttu-id="5f935-122">デザイン画面には、パイプラインが上 (始点) から下 (終点) へと縦方向に表示されます。</span><span class="sxs-lookup"><span data-stu-id="5f935-122">The design surface shows the pipeline vertically, running from top (start) to bottom (end).</span></span>  
  
 <span data-ttu-id="5f935-123">他の一般的な Microsoft Windows プログラムとを実行すると、いくつかのタスクなど**オープン**と**保存**から、**ファイル**メニュー。</span><span class="sxs-lookup"><span data-stu-id="5f935-123">As with other common Microsoft Windows programs, you can perform several tasks, such as **Open** and **Save** from the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f935-124">参照</span><span class="sxs-lookup"><span data-stu-id="5f935-124">See Also</span></span>  
 <span data-ttu-id="5f935-125">[パイプライン デザイナーでパイプラインを作成します。](../core/creating-pipelines-with-pipeline-designer.md) </span><span class="sxs-lookup"><span data-stu-id="5f935-125">[Creating Pipelines with Pipeline Designer](../core/creating-pipelines-with-pipeline-designer.md) </span></span>  
 [<span data-ttu-id="5f935-126">パイプライン デザイナーを使用したパイプラインの作成</span><span class="sxs-lookup"><span data-stu-id="5f935-126">Creating Pipelines Using Pipeline Designer</span></span>](../core/creating-pipelines-using-pipeline-designer.md)