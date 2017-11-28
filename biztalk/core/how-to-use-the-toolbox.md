---
title: "ツールボックスを使用する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- creating, pipelines
- pipeline components, deleting from toolbox
- pipeline components, Pipeline Designer
- pipeline components, adding to toolbox
- Pipeline Designer, toolbox
- pipelines, creating
ms.assetid: 7a60c590-1a38-46fe-addf-0aa2c8b63cf9
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3965a063aebcc932f07937fd19c3998412591ea1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-use-the-toolbox"></a><span data-ttu-id="31786-102">ツールボックスの使用方法</span><span class="sxs-lookup"><span data-stu-id="31786-102">How to Use the Toolbox</span></span>
<span data-ttu-id="31786-103">パイプラインを作成する場合は、コンポーネント (図形) をツールボックスからデザイン画面にドラッグします。</span><span class="sxs-lookup"><span data-stu-id="31786-103">You create a pipeline by dragging components (shapes) from the Toolbox to the design surface.</span></span> <span data-ttu-id="31786-104">パイプライン デザイナーでは、作成プロセスに特定の制限を設けることによって、有効なパイプラインをアセンブルできます。</span><span class="sxs-lookup"><span data-stu-id="31786-104">Pipeline Designer helps you assemble valid pipelines by placing certain restrictions on the creation process.</span></span> <span data-ttu-id="31786-105">作成しているパイプラインの種類に適用できるツールボックス コンポーネントのみ選択できます。</span><span class="sxs-lookup"><span data-stu-id="31786-105">You can only select Toolbox components that apply to the pipeline type you are creating.</span></span> <span data-ttu-id="31786-106">たとえば、受信パイプラインの場合は有効なツールボックス コンポーネントとしてデコーダー、逆アセンブラー、および検証が示されますが、エンコードとアセンブラーは無効 (淡色表示) になります。</span><span class="sxs-lookup"><span data-stu-id="31786-106">For example, a receive pipeline will show decoders, disassemblers, and validators as valid Toolbox components, while encoders and assemblers will be disabled (dimmed).</span></span>  
  
 <span data-ttu-id="31786-107">さらに、ステージは有効なコンポーネントのみを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="31786-107">In addition, stages can accept only valid components.</span></span> <span data-ttu-id="31786-108">たとえば、エンコーダー コンポーネントをアセンブル ステータスにドラッグすることはできません。</span><span class="sxs-lookup"><span data-stu-id="31786-108">For example, you cannot drag an encoder component to an Assemble stage.</span></span> <span data-ttu-id="31786-109">ドロップ先として有効な場所の付近までコンポーネントをドラッグすると、矢印が表示され、コンポーネントを挿入できるポイントが示されます。</span><span class="sxs-lookup"><span data-stu-id="31786-109">When you drag a component near a valid drop location, an arrow appears, indicating the point where the component can be inserted.</span></span>  
  
 <span data-ttu-id="31786-110">折りたたまれたステージの場合は、有効なコンポーネントをドラッグし、マウスをステージ上で静止させると、数秒後にステージが展開され、コンポーネントをドロップできます。</span><span class="sxs-lookup"><span data-stu-id="31786-110">If you drag a valid component onto a stage that is collapsed, pause the mouse over the stage for a few seconds to expand it, and then drop the component into the stage.</span></span>  
  
 <span data-ttu-id="31786-111">パイプライン デザイナーのツールボックスにカスタム コンポーネントを追加する手順は、Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] の標準的な手順と同様です。</span><span class="sxs-lookup"><span data-stu-id="31786-111">Adding a custom component to the Toolbox in Pipeline Designer is similar to the standard Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] procedure.</span></span>  
  
 <span data-ttu-id="31786-112">**開始および終了の図形**</span><span class="sxs-lookup"><span data-stu-id="31786-112">**Start and End Shapes**</span></span>  
  
 <span data-ttu-id="31786-113">**開始**と**終了**図形のすべてのパイプラインに行頭文字として表示されます。</span><span class="sxs-lookup"><span data-stu-id="31786-113">**Start** and **End** shapes appear as bullets on all pipelines.</span></span> <span data-ttu-id="31786-114">これらは、構成を視覚的にわかりやすくするために、デザイン画面上に表示されます。</span><span class="sxs-lookup"><span data-stu-id="31786-114">They are provided on the design surface for visual organization only.</span></span> <span data-ttu-id="31786-115">開始および終了図形はそれぞれ 1 つのみが表示され、追加や削除はできません。</span><span class="sxs-lookup"><span data-stu-id="31786-115">There is only one of each, and they can neither be added nor deleted.</span></span> <span data-ttu-id="31786-116">**開始**と**終了**図形がツールボックスに表示されません。</span><span class="sxs-lookup"><span data-stu-id="31786-116">The **Start** and **End** shapes do not appear in the Toolbox.</span></span>  
  
### <a name="to-add-a-pipeline-component-to-the-toolbox"></a><span data-ttu-id="31786-117">パイプライン コンポーネントをツールボックスに追加するには</span><span class="sxs-lookup"><span data-stu-id="31786-117">To add a pipeline component to the Toolbox</span></span>  
  
1.  <span data-ttu-id="31786-118">**[ツール]** メニューで **[ツールボックス アイテムの選択]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="31786-118">On the **Tools** menu, click **Choose Toolbox Items**.</span></span>  
  
     <span data-ttu-id="31786-119">- または -</span><span class="sxs-lookup"><span data-stu-id="31786-119">—Or—</span></span>  
  
     <span data-ttu-id="31786-120">ツールボックスを右クリックし、をクリックして**アイテムの選択**です。</span><span class="sxs-lookup"><span data-stu-id="31786-120">Right-click the Toolbox and then click **Choose Items**.</span></span>  
  
2.  <span data-ttu-id="31786-121">**ツールボックスのカスタマイズ**ダイアログ ボックスで、をクリックして、 **BizTalk パイプライン コンポーネント**タブです。</span><span class="sxs-lookup"><span data-stu-id="31786-121">In the **Customize Toolbox** dialog box, click the **BizTalk Pipeline Components** tab.</span></span>  
  
     <span data-ttu-id="31786-122">ダイアログ ボックスには、互換性のあるパイプライン コンポーネントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="31786-122">A dialog box displays the compatible pipeline components.</span></span> <span data-ttu-id="31786-123">ダイアログ ボックスの上部にあるタブをクリックすると、カテゴリ間を移動できます。</span><span class="sxs-lookup"><span data-stu-id="31786-123">You can navigate through the categories by clicking the tabs at the top of the dialog box.</span></span>  
  
3.  <span data-ttu-id="31786-124">ツールボックスに追加するコンポーネントを選択します。</span><span class="sxs-lookup"><span data-stu-id="31786-124">Select the component you want to add to the Toolbox.</span></span>  
  
4.  <span data-ttu-id="31786-125">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="31786-125">Click **OK**.</span></span> <span data-ttu-id="31786-126">コンポーネントが表示されます、 **BizTalk パイプライン コンポーネント**ツールボックス タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="31786-126">The component will appear on the **BizTalk Pipeline Components** tab of the Toolbox.</span></span>  
  
### <a name="to-remove-a-pipeline-component-from-the-toolbox"></a><span data-ttu-id="31786-127">パイプライン コンポーネントをツールボックスから削除するには</span><span class="sxs-lookup"><span data-stu-id="31786-127">To remove a pipeline component from the Toolbox</span></span>  
  
-   <span data-ttu-id="31786-128">開く、**ツールボックスのカスタマイズ** ダイアログ ボックス (上記の手順と、削除するコンポーネントをクリアします。</span><span class="sxs-lookup"><span data-stu-id="31786-128">Open the **Customize Toolbox** dialog box (as in the preceding procedure) and clear the component to be removed.</span></span>  
  
     <span data-ttu-id="31786-129">ツールボックスから削除した後も、コンポーネントは登録されたままの状態です。</span><span class="sxs-lookup"><span data-stu-id="31786-129">A component remains registered even after it has been removed from the Toolbox.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31786-130">参照</span><span class="sxs-lookup"><span data-stu-id="31786-130">See Also</span></span>  
 <span data-ttu-id="31786-131">[新しいパイプラインを作成する方法](../core/how-to-create-a-new-pipeline.md) </span><span class="sxs-lookup"><span data-stu-id="31786-131">[How to Create a New Pipeline](../core/how-to-create-a-new-pipeline.md) </span></span>  
 <span data-ttu-id="31786-132">[パイプラインを開く方法](../core/how-to-open-a-pipeline.md) </span><span class="sxs-lookup"><span data-stu-id="31786-132">[How to Open a Pipeline](../core/how-to-open-a-pipeline.md) </span></span>  
 <span data-ttu-id="31786-133">[キーボードで移動する方法](../core/how-to-navigate-with-the-keyboard.md) </span><span class="sxs-lookup"><span data-stu-id="31786-133">[How to Navigate with the Keyboard](../core/how-to-navigate-with-the-keyboard.md) </span></span>  
 [<span data-ttu-id="31786-134">パイプライン デザイナーでパイプラインの作成</span><span class="sxs-lookup"><span data-stu-id="31786-134">Creating Pipelines with Pipeline Designer</span></span>](../core/creating-pipelines-with-pipeline-designer.md)