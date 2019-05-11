---
title: オーケストレーションを構築する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- building, orchestrations
- building, solutions
- building, projects
- solutions, building
- projects, building
- orchestrations, building
ms.assetid: f12d5da0-fbae-4f0e-85bf-1ca2e9bf7d62
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f755ea3b2aa01919d7f5d40a9eca92fd3529c629
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387075"
---
# <a name="how-to-build-orchestrations"></a><span data-ttu-id="5572e-102">オーケストレーションを構築する方法</span><span class="sxs-lookup"><span data-stu-id="5572e-102">How to Build Orchestrations</span></span>
<span data-ttu-id="5572e-103">描画オーケストレーションを完了すると後、は、実行可能ファイルのオーケストレーションをカプセル化するアセンブリに、BizTalk プロジェクトをビルドします。</span><span class="sxs-lookup"><span data-stu-id="5572e-103">After you have completed an orchestration drawing, you build your BizTalk project into an assembly that encapsulates an executable orchestration.</span></span>  
  
 <span data-ttu-id="5572e-104">ビルド プロセス中には、BizTalk オーケストレーション デザイナーが完全で正しい、しでない場合は、タスク一覧のエラーを報告するかどうかを判断するには、各図形を調べます。</span><span class="sxs-lookup"><span data-stu-id="5572e-104">During the build process, BizTalk Orchestration Designer examines each shape to determine whether it is complete and correct, and reports an error in the task list if it is not.</span></span>  
  
 <span data-ttu-id="5572e-105">Visual Studio で構築するためのいくつかのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="5572e-105">You have several options for building in Visual Studio:</span></span>  
  
- <span data-ttu-id="5572e-106">オーケストレーションが存在するソリューション全体をビルドすることができます。</span><span class="sxs-lookup"><span data-stu-id="5572e-106">You can build the entire solution in which your orchestration resides.</span></span>  
  
- <span data-ttu-id="5572e-107">ソリューション内の 1 つのプロジェクトをビルドすることができます。</span><span class="sxs-lookup"><span data-stu-id="5572e-107">You can build a single project within the solution.</span></span>  
  
- <span data-ttu-id="5572e-108">プロジェクトまたはソリューションを構築するときに、オーケストレーションをスキップできます。</span><span class="sxs-lookup"><span data-stu-id="5572e-108">You can skip the orchestration when building the project or solution.</span></span>  
  
  <span data-ttu-id="5572e-109">他のオーケストレーションを含む、他のコンポーネントを作成する場合、特定のオーケストレーションをビルドしたくない場合は、ビルドしたくないとはスキップされるオーケストレーションの .odx ファイルのファイルのプロパティで指定できます。</span><span class="sxs-lookup"><span data-stu-id="5572e-109">If you want to build other components, including other orchestrations, but do not want to build a particular orchestration, you can indicate in the file properties for the orchestration's .odx file that you do not want to build it, and it will be skipped.</span></span>  
  
### <a name="to-build-an-orchestration"></a><span data-ttu-id="5572e-110">オーケストレーションを構築するには</span><span class="sxs-lookup"><span data-stu-id="5572e-110">To build an orchestration</span></span>  
  
-   <span data-ttu-id="5572e-111">オーケストレーションを作成した後は、テストしたり、オーケストレーションを使用する前に、それを含んでいる BizTalk プロジェクトをビルドする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5572e-111">After creating your orchestration, you need to build the BizTalk project that contains it before you can test or use the orchestration.</span></span> <span data-ttu-id="5572e-112">ソリューション全体、またはソリューション内の 1 つのプロジェクトをビルドすることができます。</span><span class="sxs-lookup"><span data-stu-id="5572e-112">You can build the entire solution, or a single project within the solution.</span></span>  
  
### <a name="to-build-a-solution"></a><span data-ttu-id="5572e-113">ソリューションを構築するには</span><span class="sxs-lookup"><span data-stu-id="5572e-113">To build a solution</span></span>  
  
-   <span data-ttu-id="5572e-114">ソリューション エクスプ ローラーでソリューションを右クリックし、選択**ソリューションのビルド**します。</span><span class="sxs-lookup"><span data-stu-id="5572e-114">In Solution Explorer, right-click the solution and select **Build Solution**.</span></span>  
  
### <a name="to-build-a-project"></a><span data-ttu-id="5572e-115">プロジェクトをビルドします。</span><span class="sxs-lookup"><span data-stu-id="5572e-115">To build a project</span></span>  
  
-   <span data-ttu-id="5572e-116">プロジェクトを右クリックして**ビルド**します。</span><span class="sxs-lookup"><span data-stu-id="5572e-116">Right-click a project and select **Build**.</span></span>  
  
### <a name="to-build-a-project-or-solution-without-compiling-a-particular-orchestration"></a><span data-ttu-id="5572e-117">特定のオーケストレーションをコンパイルせずに、プロジェクトまたはソリューションを構築するには</span><span class="sxs-lookup"><span data-stu-id="5572e-117">To build a project or solution without compiling a particular orchestration</span></span>  
  
-   <span data-ttu-id="5572e-118">対応する .odx ファイルとプロパティ ウィンドウで、オーケストレーションをクリックし、**ビルド アクション**プロパティと選択**None**します。</span><span class="sxs-lookup"><span data-stu-id="5572e-118">Click the .odx file corresponding to the orchestration, and in the Properties window, click the **Build Action** property and select **None**.</span></span>