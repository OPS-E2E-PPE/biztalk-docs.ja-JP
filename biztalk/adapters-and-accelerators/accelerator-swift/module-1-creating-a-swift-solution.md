---
title: モジュール 1:SWIFT ソリューションの作成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SWIFT solutions
- tutorial, creating SWIFT solutions
ms.assetid: 550af497-abd2-4044-8c6f-15f9dba0ac5d
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f16a40fb32b67c6960f673218d24d3324d4e2222
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530255"
---
# <a name="module-1-creating-a-swift-solution"></a><span data-ttu-id="c3f17-102">モジュール 1:SWIFT ソリューションの作成</span><span class="sxs-lookup"><span data-stu-id="c3f17-102">Module 1: Creating a SWIFT Solution</span></span>
<span data-ttu-id="c3f17-103">このモジュールでは、空の BizTalk ソリューションを作成します。</span><span class="sxs-lookup"><span data-stu-id="c3f17-103">In this module, you create a blank BizTalk solution.</span></span> <span data-ttu-id="c3f17-104">最初のレッスンでは、Microsoft を使用して新しいソリューションを作成する[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)][!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="c3f17-104">In the first lesson, you create a new solution by using Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)][!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)].</span></span> <span data-ttu-id="c3f17-105">スキーマ、マップ、オーケストレーション、パイプライン コンポーネントなど、BizTalk ソリューションのコンポーネントが含まれている個々 のプロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="c3f17-105">You also create the individual projects that contain your BizTalk solution components such as schema, maps, orchestrations, and pipeline components.</span></span>  
  
 <span data-ttu-id="c3f17-106">ソリューションは、1 つだけの BizTalk プロジェクトを含めることができますか、(ソリューションは、個別にした開発と統合するには、この後で多数のプロジェクトで構成されています) 場合、多くの BizTalk プロジェクトを含めることことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="c3f17-106">Note that a solution may include only one BizTalk project, or it may include many BizTalk projects (if the solution consists of numerous projects, which you develop independently and which you must integrate later).</span></span>  
  
### <a name="to-create-a-blank-biztalk-solution"></a><span data-ttu-id="c3f17-107">空の BizTalk ソリューションを作成するには</span><span class="sxs-lookup"><span data-stu-id="c3f17-107">To create a blank BizTalk solution</span></span>  
  
1. <span data-ttu-id="c3f17-108">開始**Visual Studio**します。</span><span class="sxs-lookup"><span data-stu-id="c3f17-108">Start **Visual Studio**.</span></span>  
  
2. <span data-ttu-id="c3f17-109">**[ファイル]** メニューの **[新規作成]** をポイントし、 **[プロジェクト]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c3f17-109">On the **File** menu, point to **New**, and then click **Project**.</span></span>  
  
3. <span data-ttu-id="c3f17-110">**プロジェクトの種類**選択 [新しいプロジェクト] ダイアログ ボックスのウィンドウ、 **BizTalk プロジェクト**します。</span><span class="sxs-lookup"><span data-stu-id="c3f17-110">In the **Project Types** pane of the New Project dialog box, select the **BizTalk Projects**.</span></span> <span data-ttu-id="c3f17-111">[テンプレート] ペインで選択**空の BizTalk Server プロジェクト**します。</span><span class="sxs-lookup"><span data-stu-id="c3f17-111">In the Templates pane, select **Empty BizTalk Server Project**.</span></span>  
  
4. <span data-ttu-id="c3f17-112">**名前**ボックスに「 **SWIFTProject**ソリューション名として。</span><span class="sxs-lookup"><span data-stu-id="c3f17-112">In the **Name** box, type **SWIFTProject** as the solution name.</span></span>  
  
5. <span data-ttu-id="c3f17-113">**場所**ボックスに「  **\<*ドライブ*\>: \labs**します。</span><span class="sxs-lookup"><span data-stu-id="c3f17-113">In the **Location** box, type **\<*drive*\>:\labs**.</span></span>  
  
6. <span data-ttu-id="c3f17-114">をクリックして**OK**を新しいプロジェクトを開きます。</span><span class="sxs-lookup"><span data-stu-id="c3f17-114">Click **OK** to open the new project.</span></span>  
  
    [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] <span data-ttu-id="c3f17-115">ソリューション エクスプ ローラーで新しい空のソリューションで空のソリューションを作成し、 \<*ドライブ*:\>\labs フォルダー。</span><span class="sxs-lookup"><span data-stu-id="c3f17-115">creates an empty solution in Solution Explorer and a new blank solution in the \<*drive*:\>\labs folder.</span></span>  
  
   <span data-ttu-id="c3f17-116">続行する[モジュール 2。新しいスキーマ プロジェクトの追加](../../adapters-and-accelerators/accelerator-swift/module-2-adding-a-new-schemas-project.md)します。</span><span class="sxs-lookup"><span data-stu-id="c3f17-116">Proceed to [Module 2: Adding a New Schemas Project](../../adapters-and-accelerators/accelerator-swift/module-2-adding-a-new-schemas-project.md).</span></span>