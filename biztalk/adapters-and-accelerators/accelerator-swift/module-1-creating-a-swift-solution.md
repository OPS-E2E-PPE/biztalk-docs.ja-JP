---
title: "第 1 章: SWIFT ソリューションを作成する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SWIFT solutions
- tutorial, creating SWIFT solutions
ms.assetid: 550af497-abd2-4044-8c6f-15f9dba0ac5d
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ea84c244d0219043a2b68c1e08fbd647a5002009
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="module-1-creating-a-swift-solution"></a><span data-ttu-id="238ba-102">第 1 章: SWIFT ソリューションを作成します。</span><span class="sxs-lookup"><span data-stu-id="238ba-102">Module 1: Creating a SWIFT Solution</span></span>
<span data-ttu-id="238ba-103">このモジュールでは、空の BizTalk ソリューションを作成します。</span><span class="sxs-lookup"><span data-stu-id="238ba-103">In this module, you create a blank BizTalk solution.</span></span> <span data-ttu-id="238ba-104">使用して新しいソリューションを作成する最初のレッスンで[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)][!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="238ba-104">In the first lesson, you create a new solution by using [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)][!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)].</span></span> <span data-ttu-id="238ba-105">また、スキーマ、マップ、オーケストレーション、パイプライン コンポーネントなど、BizTalk ソリューションのコンポーネントを含む個々 のプロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="238ba-105">You also create the individual projects that contain your BizTalk solution components such as schema, maps, orchestrations, and pipeline components.</span></span>  
  
 <span data-ttu-id="238ba-106">ソリューションが 1 つだけの BizTalk プロジェクトを含めることがありますまたは (ソリューションは、個別を開発して統合するには、この後で、多数のプロジェクトで構成されています) 場合、多くの BizTalk プロジェクトを含めることがある注意してください。</span><span class="sxs-lookup"><span data-stu-id="238ba-106">Note that a solution may include only one BizTalk project, or it may include many BizTalk projects (if the solution consists of numerous projects, which you develop independently and which you must integrate later).</span></span>  
  
### <a name="to-create-a-blank-biztalk-solution"></a><span data-ttu-id="238ba-107">空の BizTalk ソリューションを作成するには</span><span class="sxs-lookup"><span data-stu-id="238ba-107">To create a blank BizTalk solution</span></span>  
  
1.  <span data-ttu-id="238ba-108">開始 **[!INCLUDE[vs2012](../../includes/vs2012-md.md)]**です。</span><span class="sxs-lookup"><span data-stu-id="238ba-108">Start **[!INCLUDE[vs2012](../../includes/vs2012-md.md)]**.</span></span>  
  
2.  <span data-ttu-id="238ba-109">**[ファイル]** メニューの **[新規作成]**をポイントし、 **[プロジェクト]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="238ba-109">On the **File** menu, point to **New**, and then click **Project**.</span></span>  
  
3.  <span data-ttu-id="238ba-110">**プロジェクトの種類**選択、新しいプロジェクト ダイアログ ボックスのウィンドウ、 **BizTalk プロジェクト**です。</span><span class="sxs-lookup"><span data-stu-id="238ba-110">In the **Project Types** pane of the New Project dialog box, select the **BizTalk Projects**.</span></span> <span data-ttu-id="238ba-111">[テンプレート] ペインで選択**空の BizTalk Server プロジェクト**です。</span><span class="sxs-lookup"><span data-stu-id="238ba-111">In the Templates pane, select **Empty BizTalk Server Project**.</span></span>  
  
4.  <span data-ttu-id="238ba-112">**名前**ボックスに、入力**SWIFTProject**ソリューション名として。</span><span class="sxs-lookup"><span data-stu-id="238ba-112">In the **Name** box, type **SWIFTProject** as the solution name.</span></span>  
  
5.  <span data-ttu-id="238ba-113">**場所**ボックスに、入力  **\<*ドライブ*>: \labs** です。</span><span class="sxs-lookup"><span data-stu-id="238ba-113">In the **Location** box, type **\<*drive*>:\labs**.</span></span>  
  
6.  <span data-ttu-id="238ba-114">をクリックして**OK**新しいプロジェクトを開きます。</span><span class="sxs-lookup"><span data-stu-id="238ba-114">Click **OK** to open the new project.</span></span>  
  
     [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]<span data-ttu-id="238ba-115">ソリューション エクスプ ローラーと新しい空のソリューション内に空のソリューションを作成、 \<*ドライブ*: > \labs フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="238ba-115"> creates an empty solution in Solution Explorer and a new blank solution in the \<*drive*:>\labs folder.</span></span>  
  
 <span data-ttu-id="238ba-116">進みます[モジュール 2: 新しいスキーマ プロジェクトに追加する](../../adapters-and-accelerators/accelerator-swift/module-2-adding-a-new-schemas-project.md)です。</span><span class="sxs-lookup"><span data-stu-id="238ba-116">Proceed to [Module 2: Adding a New Schemas Project](../../adapters-and-accelerators/accelerator-swift/module-2-adding-a-new-schemas-project.md).</span></span>