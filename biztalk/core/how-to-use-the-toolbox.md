---
title: ツールボックスを使用する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating, pipelines
- pipeline components, deleting from toolbox
- pipeline components, Pipeline Designer
- pipeline components, adding to toolbox
- Pipeline Designer, toolbox
- pipelines, creating
ms.assetid: 7a60c590-1a38-46fe-addf-0aa2c8b63cf9
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2990cdf576f1678078da564932542081512d09dd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65383177"
---
# <a name="how-to-use-the-toolbox"></a><span data-ttu-id="1c5f7-102">ツールボックスの使用方法</span><span class="sxs-lookup"><span data-stu-id="1c5f7-102">How to Use the Toolbox</span></span>
<span data-ttu-id="1c5f7-103">パイプラインを作成するには、コンポーネント (図形) をツールボックスからデザイン画面にドラッグします。</span><span class="sxs-lookup"><span data-stu-id="1c5f7-103">You create a pipeline by dragging components (shapes) from the Toolbox to the design surface.</span></span> <span data-ttu-id="1c5f7-104">パイプライン デザイナーを使用して、作成プロセスを特定の制限を配置することで有効なパイプラインをアセンブルできます。</span><span class="sxs-lookup"><span data-stu-id="1c5f7-104">Pipeline Designer helps you assemble valid pipelines by placing certain restrictions on the creation process.</span></span> <span data-ttu-id="1c5f7-105">作成するパイプラインの種類に適用できるツールボックス コンポーネントのみ選択できます。</span><span class="sxs-lookup"><span data-stu-id="1c5f7-105">You can only select Toolbox components that apply to the pipeline type you are creating.</span></span> <span data-ttu-id="1c5f7-106">たとえば、受信パイプラインは表示デコーダー、逆アセンブラー、および検証コントロール ツールボックス コンポーネントの有効なものとして、エンコードとアセンブラーが無効にするときに (淡色表示になります)。</span><span class="sxs-lookup"><span data-stu-id="1c5f7-106">For example, a receive pipeline will show decoders, disassemblers, and validators as valid Toolbox components, while encoders and assemblers will be disabled (dimmed).</span></span>  
  
 <span data-ttu-id="1c5f7-107">さらに、ステージでは、有効なコンポーネントのみを受け入れることができます。</span><span class="sxs-lookup"><span data-stu-id="1c5f7-107">In addition, stages can accept only valid components.</span></span> <span data-ttu-id="1c5f7-108">たとえば、アセンブル ステージにエンコーダー コンポーネントをドラッグすることはできません。</span><span class="sxs-lookup"><span data-stu-id="1c5f7-108">For example, you cannot drag an encoder component to an Assemble stage.</span></span> <span data-ttu-id="1c5f7-109">有効なドロップ位置の近くのコンポーネントをドラッグするときに、コンポーネントを挿入できるポイントを示す矢印が表示されます。</span><span class="sxs-lookup"><span data-stu-id="1c5f7-109">When you drag a component near a valid drop location, an arrow appears, indicating the point where the component can be inserted.</span></span>  
  
 <span data-ttu-id="1c5f7-110">折りたたまれたステージに有効なコンポーネントをドラッグした場合は、数秒を展開して、ステージにコンポーネントをドロップ ステージ上でマウス ポインターを置きます。</span><span class="sxs-lookup"><span data-stu-id="1c5f7-110">If you drag a valid component onto a stage that is collapsed, pause the mouse over the stage for a few seconds to expand it, and then drop the component into the stage.</span></span>  
  
 <span data-ttu-id="1c5f7-111">カスタム コンポーネントをパイプライン デザイナーのツールボックスに追加するには、標準の Microsoft と似ています[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]プロシージャ。</span><span class="sxs-lookup"><span data-stu-id="1c5f7-111">Adding a custom component to the Toolbox in Pipeline Designer is similar to the standard Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] procedure.</span></span>  
  
 <span data-ttu-id="1c5f7-112">**開始および終了の図形**</span><span class="sxs-lookup"><span data-stu-id="1c5f7-112">**Start and End Shapes**</span></span>  
  
 <span data-ttu-id="1c5f7-113">**開始**と**エンド**図形のすべてのパイプラインの行頭文字として表示されます。</span><span class="sxs-lookup"><span data-stu-id="1c5f7-113">**Start** and **End** shapes appear as bullets on all pipelines.</span></span> <span data-ttu-id="1c5f7-114">デザイン サーフェイスで視覚的に整理だけに提供されます。</span><span class="sxs-lookup"><span data-stu-id="1c5f7-114">They are provided on the design surface for visual organization only.</span></span> <span data-ttu-id="1c5f7-115">それぞれ、1 つだけを使用する必要があると、それらはする追加も削除します。</span><span class="sxs-lookup"><span data-stu-id="1c5f7-115">There is only one of each, and they can neither be added nor deleted.</span></span> <span data-ttu-id="1c5f7-116">**開始**と**エンド**図形がツールボックスに表示されません。</span><span class="sxs-lookup"><span data-stu-id="1c5f7-116">The **Start** and **End** shapes do not appear in the Toolbox.</span></span>  
  
### <a name="to-add-a-pipeline-component-to-the-toolbox"></a><span data-ttu-id="1c5f7-117">パイプライン コンポーネントをツールボックスに追加するには</span><span class="sxs-lookup"><span data-stu-id="1c5f7-117">To add a pipeline component to the Toolbox</span></span>  
  
1.  <span data-ttu-id="1c5f7-118">**[ツール]** メニューで **[ツールボックス アイテムの選択]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1c5f7-118">On the **Tools** menu, click **Choose Toolbox Items**.</span></span>  
  
     <span data-ttu-id="1c5f7-119">- または -</span><span class="sxs-lookup"><span data-stu-id="1c5f7-119">—Or—</span></span>  
  
     <span data-ttu-id="1c5f7-120">ツールボックスを右クリックし、をクリックし、**アイテムの選択**します。</span><span class="sxs-lookup"><span data-stu-id="1c5f7-120">Right-click the Toolbox and then click **Choose Items**.</span></span>  
  
2.  <span data-ttu-id="1c5f7-121">**ツールボックスのカスタマイズ**ダイアログ ボックスで、をクリックして、 **BizTalk パイプライン コンポーネント**タブ。</span><span class="sxs-lookup"><span data-stu-id="1c5f7-121">In the **Customize Toolbox** dialog box, click the **BizTalk Pipeline Components** tab.</span></span>  
  
     <span data-ttu-id="1c5f7-122">ダイアログ ボックスには、互換性のあるパイプライン コンポーネントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1c5f7-122">A dialog box displays the compatible pipeline components.</span></span> <span data-ttu-id="1c5f7-123">ダイアログ ボックスの上部にあるタブをクリックして、カテゴリを移動できます。</span><span class="sxs-lookup"><span data-stu-id="1c5f7-123">You can navigate through the categories by clicking the tabs at the top of the dialog box.</span></span>  
  
3.  <span data-ttu-id="1c5f7-124">ツールボックスに追加するコンポーネントを選択します。</span><span class="sxs-lookup"><span data-stu-id="1c5f7-124">Select the component you want to add to the Toolbox.</span></span>  
  
4.  <span data-ttu-id="1c5f7-125">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1c5f7-125">Click **OK**.</span></span> <span data-ttu-id="1c5f7-126">コンポーネントが表示されます、 **BizTalk パイプライン コンポーネント**ツールボックス タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="1c5f7-126">The component will appear on the **BizTalk Pipeline Components** tab of the Toolbox.</span></span>  
  
### <a name="to-remove-a-pipeline-component-from-the-toolbox"></a><span data-ttu-id="1c5f7-127">ツールボックスからパイプライン コンポーネントを削除するには</span><span class="sxs-lookup"><span data-stu-id="1c5f7-127">To remove a pipeline component from the Toolbox</span></span>  
  
-   <span data-ttu-id="1c5f7-128">開く、**ツールボックスのカスタマイズ**(上記の手順のようにダイアログ ボックスおよび削除するコンポーネントをクリアします。</span><span class="sxs-lookup"><span data-stu-id="1c5f7-128">Open the **Customize Toolbox** dialog box (as in the preceding procedure) and clear the component to be removed.</span></span>  
  
     <span data-ttu-id="1c5f7-129">ツールボックスから削除された後でも、コンポーネントは登録済みのままになります。</span><span class="sxs-lookup"><span data-stu-id="1c5f7-129">A component remains registered even after it has been removed from the Toolbox.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c5f7-130">参照</span><span class="sxs-lookup"><span data-stu-id="1c5f7-130">See Also</span></span>  
 <span data-ttu-id="1c5f7-131">[新しいパイプラインを作成する方法](../core/how-to-create-a-new-pipeline.md) </span><span class="sxs-lookup"><span data-stu-id="1c5f7-131">[How to Create a New Pipeline](../core/how-to-create-a-new-pipeline.md) </span></span>  
 <span data-ttu-id="1c5f7-132">[パイプラインを開く方法](../core/how-to-open-a-pipeline.md) </span><span class="sxs-lookup"><span data-stu-id="1c5f7-132">[How to Open a Pipeline](../core/how-to-open-a-pipeline.md) </span></span>  
 <span data-ttu-id="1c5f7-133">[キーボードで移動する方法](../core/how-to-navigate-with-the-keyboard.md) </span><span class="sxs-lookup"><span data-stu-id="1c5f7-133">[How to Navigate with the Keyboard](../core/how-to-navigate-with-the-keyboard.md) </span></span>  
 [<span data-ttu-id="1c5f7-134">パイプライン デザイナーでのパイプラインの作成</span><span class="sxs-lookup"><span data-stu-id="1c5f7-134">Creating Pipelines with Pipeline Designer</span></span>](../core/creating-pipelines-with-pipeline-designer.md)