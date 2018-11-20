---
title: 新しいパイプラインを作成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating, pipelines
- pipelines, warnings
- Pipeline Designer, warnings
- pipelines, creating
ms.assetid: bd95325e-1a72-4705-80f6-37ac092d11a3
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 00f19818dd5df6cafaf51298a0463ea745736ab5
ms.sourcegitcommit: c3070a7a3f332857357f056dc632829b43869c17
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/14/2018
ms.locfileid: "51630391"
---
# <a name="how-to-create-a-new-pipeline"></a><span data-ttu-id="6e899-102">新しいパイプラインを作成する方法</span><span class="sxs-lookup"><span data-stu-id="6e899-102">How to Create a New Pipeline</span></span>
<span data-ttu-id="6e899-103">プロジェクトにパイプライン テンプレートを追加して、新しいパイプラインを作成できます。</span><span class="sxs-lookup"><span data-stu-id="6e899-103">You can add a pipeline template to your project to create a new pipeline.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="6e899-104">また、そのパイプライン コンポーネントを使用してプロジェクトを含むソリューションにカスタム パイプライン コンポーネントの実装を含むプロジェクトを追加する必要がありますできません。</span><span class="sxs-lookup"><span data-stu-id="6e899-104">You should not add a project that contains an implementation of a custom pipeline component to a solution that contains a project that uses that pipeline component.</span></span> <span data-ttu-id="6e899-105">このような状況でプロジェクトを追加すると、次回のソリューションの再ビルド時に、出力 dll が他のプロセスにより使用されていることを示すエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="6e899-105">If you do, the next time you rebuild the solution you will get an error saying the output dll is being used by another process.</span></span>  
  
### <a name="to-create-a-new-pipeline"></a><span data-ttu-id="6e899-106">新しいパイプラインを作成するには</span><span class="sxs-lookup"><span data-stu-id="6e899-106">To create a new pipeline</span></span>  
  
1. <span data-ttu-id="6e899-107">ソリューション エクスプローラーで、パイプラインを作成するプロジェクトを選択します。</span><span class="sxs-lookup"><span data-stu-id="6e899-107">In Solution Explorer, select the project in which you want to create the pipeline.</span></span>  
  
2. <span data-ttu-id="6e899-108">**[プロジェクト]** メニューの **[新しい項目の追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6e899-108">On the **Project** menu, click **Add New Item**.</span></span>  
  
3. <span data-ttu-id="6e899-109">**新しい項目の追加**ダイアログ ボックスで、**受信パイプライン**または**送信パイプライン**テンプレートで 1 回クリックします。</span><span class="sxs-lookup"><span data-stu-id="6e899-109">In the **Add New Item** dialog box, select a **Receive Pipeline** or **Send Pipeline** template by clicking it once.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="6e899-110">パイプラインに表示される既定の名前を自動的に作成されます、テンプレートをダブルクリックした場合、**名前**フィールド。</span><span class="sxs-lookup"><span data-stu-id="6e899-110">If you double-click the template, the pipeline will automatically be created with the default name that appears in the **Name** field.</span></span>  
  
4. <span data-ttu-id="6e899-111">**名前**フィールドに、パイプラインの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="6e899-111">In the **Name** field, type a name for the pipeline.</span></span>  
  
5. <span data-ttu-id="6e899-112">**[開く]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6e899-112">Click **Open**.</span></span>  
  
    <span data-ttu-id="6e899-113">新しいパイプラインがソリューション エクスプローラーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="6e899-113">The new pipeline appears in Solution Explorer.</span></span> <span data-ttu-id="6e899-114">デザイン画面に、パイプラインのステージおよび既定のコンポーネントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6e899-114">The design surface displays pipeline stages and a default set of components.</span></span>  
  
   <span data-ttu-id="6e899-115">パイプライン コンポーネントをパイプラインに追加する方法の詳細については、次を参照してください。[パイプラインにコンポーネントを追加する方法](../core/how-to-add-a-component-to-a-pipeline.md)します。</span><span class="sxs-lookup"><span data-stu-id="6e899-115">For information about adding pipeline components to the pipeline, see [How to Add a Component to a Pipeline](../core/how-to-add-a-component-to-a-pipeline.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e899-116">参照</span><span class="sxs-lookup"><span data-stu-id="6e899-116">See Also</span></span>  
 <span data-ttu-id="6e899-117">[パイプラインを開く方法](../core/how-to-open-a-pipeline.md) </span><span class="sxs-lookup"><span data-stu-id="6e899-117">[How to Open a Pipeline](../core/how-to-open-a-pipeline.md) </span></span>  
 <span data-ttu-id="6e899-118">[パイプラインを保存する方法](../core/how-to-save-a-pipeline.md) </span><span class="sxs-lookup"><span data-stu-id="6e899-118">[How to Save a Pipeline](../core/how-to-save-a-pipeline.md) </span></span>  
 <span data-ttu-id="6e899-119">[ツールボックスの使用方法](../core/how-to-use-the-toolbox.md) </span><span class="sxs-lookup"><span data-stu-id="6e899-119">[How to Use the Toolbox](../core/how-to-use-the-toolbox.md) </span></span>  
 <span data-ttu-id="6e899-120">[キーボードで移動する方法](../core/how-to-navigate-with-the-keyboard.md) </span><span class="sxs-lookup"><span data-stu-id="6e899-120">[How to Navigate with the Keyboard](../core/how-to-navigate-with-the-keyboard.md) </span></span>  
 [<span data-ttu-id="6e899-121">パイプライン デザイナーでのパイプラインの作成</span><span class="sxs-lookup"><span data-stu-id="6e899-121">Creating Pipelines with Pipeline Designer</span></span>](../core/creating-pipelines-with-pipeline-designer.md)