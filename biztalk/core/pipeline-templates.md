---
title: "パイプライン テンプレート |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- pipelines, templates
- Pipeline Designer, templates
- send pipelines, templates
- receive pipelines, templates
ms.assetid: b9779159-e49d-47fb-aa1c-06be5d604c67
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 92cff5e945fad7716f31aa666731fe5d6a365146
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="pipeline-templates"></a><span data-ttu-id="a97e1-102">パイプライン テンプレート</span><span class="sxs-lookup"><span data-stu-id="a97e1-102">Pipeline Templates</span></span>
<span data-ttu-id="a97e1-103">既定のパイプラインだけでなく[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]2 つのパイプライン テンプレートが含まれています: 受信パイプライン テンプレートと送信パイプライン テンプレート。</span><span class="sxs-lookup"><span data-stu-id="a97e1-103">In addition to the default pipelines, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] includes two pipeline templates: a receive pipeline template and a send pipeline template.</span></span> <span data-ttu-id="a97e1-104">Microsoft では、BizTalk プロジェクトから[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]、パイプライン テンプレートをプロジェクトに追加するにを使用して、**新しい項目の追加**コマンドを**プロジェクト**メニュー。</span><span class="sxs-lookup"><span data-stu-id="a97e1-104">From a BizTalk project in Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], you can add a pipeline template to your project by using the **Add New Item** command on the **Project** menu.</span></span> <span data-ttu-id="a97e1-105">各テンプレートにはポリシー ファイルが関連付けられ、このポリシー ファイルによって、パイプラインに含まれるステージと、パイプラインで許可されるパイプライン コンポーネントが決まります。</span><span class="sxs-lookup"><span data-stu-id="a97e1-105">Each template has an associated policy file, which determines the pipeline's stages and indicates which pipeline components are allowed in the pipeline.</span></span> <span data-ttu-id="a97e1-106">ポリシー ファイルにおけるステージの順序を変えることはできませんが、パイプライン デザイナーを使って、ステージにおけるコンポーネントの順序を変えることはできます。</span><span class="sxs-lookup"><span data-stu-id="a97e1-106">While you cannot reorder the stages in a policy file, you can use Pipeline Designer to reorder the components within a stage.</span></span>  
  
 <span data-ttu-id="a97e1-107">ポリシー ファイルでは、次の情報が指定されます。</span><span class="sxs-lookup"><span data-stu-id="a97e1-107">A policy file specifies:</span></span>  
  
-   <span data-ttu-id="a97e1-108">ステージの順序</span><span class="sxs-lookup"><span data-stu-id="a97e1-108">The sequence of stages.</span></span>  
  
-   <span data-ttu-id="a97e1-109">ステージあたりの最大コンポーネント数</span><span class="sxs-lookup"><span data-stu-id="a97e1-109">The number of components allowed per stage.</span></span>  
  
-   <span data-ttu-id="a97e1-110">各ステージの実行モード</span><span class="sxs-lookup"><span data-stu-id="a97e1-110">The execution mode of each stage.</span></span>  
  
 <span data-ttu-id="a97e1-111">パイプライン テンプレートのポリシー ファイルが格納されている *\<BizTalk Server のインストール ディレクトリ\>*\Developer Tools\Pipeline ポリシー ファイルです。</span><span class="sxs-lookup"><span data-stu-id="a97e1-111">The policy files for the pipeline templates are stored in *\<BizTalk Server installation directory\>*\Developer Tools\Pipeline Policy Files.</span></span> <span data-ttu-id="a97e1-112">ポリシー ファイルは編集しないでください。</span><span class="sxs-lookup"><span data-stu-id="a97e1-112">Do not modify the policy files.</span></span> <span data-ttu-id="a97e1-113">パイプラインに変更を加える場合は、パイプライン テンプレートを開き、パイプライン デザイナーを使って編集します。</span><span class="sxs-lookup"><span data-stu-id="a97e1-113">To make changes to a pipeline, open the pipeline template and use Pipeline Designer to modify it.</span></span> <span data-ttu-id="a97e1-114">パイプライン デザイナーの使用の詳細については、次を参照してください。[パイプライン デザイナーの使用](../core/using-pipeline-designer.md)です。</span><span class="sxs-lookup"><span data-stu-id="a97e1-114">For more information about using Pipeline Designer, see [Using Pipeline Designer](../core/using-pipeline-designer.md).</span></span>  
  
 <span data-ttu-id="a97e1-115">空のパイプライン テンプレート ファイルが格納されている *\<BizTalk Server のインストール ディレクトリ\>*\Developer Tools\BizTalkProjectItems であり、名前付き BTSReceivePipeline.btp および BTSTransmitPipeline.btp.</span><span class="sxs-lookup"><span data-stu-id="a97e1-115">The empty pipeline template files are stored in *\<BizTalk Server installation directory\>*\Developer Tools\BizTalkProjectItems, and are named BTSReceivePipeline.btp and BTSTransmitPipeline.btp.</span></span> <span data-ttu-id="a97e1-116">ファイル名拡張子 .btp は、ファイルが BizTalk Server パイプラインは、パイプライン デザイナーで編集できることを示します。</span><span class="sxs-lookup"><span data-stu-id="a97e1-116">The file name extension .btp indicates that the file is a BizTalk Server pipeline and can be edited in Pipeline Designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a97e1-117">参照</span><span class="sxs-lookup"><span data-stu-id="a97e1-117">See Also</span></span>  
 <span data-ttu-id="a97e1-118">[パイプラインの種類](../core/types-of-pipelines.md) </span><span class="sxs-lookup"><span data-stu-id="a97e1-118">[Types of Pipelines](../core/types-of-pipelines.md) </span></span>  
 <span data-ttu-id="a97e1-119">[パイプライン コンポーネントの種類](../core/types-of-pipeline-components.md) </span><span class="sxs-lookup"><span data-stu-id="a97e1-119">[Types of Pipeline Components](../core/types-of-pipeline-components.md) </span></span>  
 <span data-ttu-id="a97e1-120">[既定のパイプライン](../core/default-pipelines.md) </span><span class="sxs-lookup"><span data-stu-id="a97e1-120">[Default Pipelines](../core/default-pipelines.md) </span></span>  
 <span data-ttu-id="a97e1-121">[パイプライン コンポーネント](../core/pipeline-components.md) </span><span class="sxs-lookup"><span data-stu-id="a97e1-121">[Pipeline Components](../core/pipeline-components.md) </span></span>  
 [<span data-ttu-id="a97e1-122">パイプライン、ステージ、およびコンポーネントについて</span><span class="sxs-lookup"><span data-stu-id="a97e1-122">About Pipelines, Stages, and Components</span></span>](../core/about-pipelines-stages-and-components.md)