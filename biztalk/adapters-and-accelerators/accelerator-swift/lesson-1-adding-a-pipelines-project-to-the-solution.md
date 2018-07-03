---
title: 'レッスン 1: パイプライン プロジェクトをソリューションに追加する |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- projects, adding pipelines
- pipelines, adding to projects
ms.assetid: ae058b52-e2ea-406c-9f9f-6cb1b72413d2
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cc2d7081b7f07cb50200d16415394f48651f525e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36982979"
---
# <a name="lesson-1-adding-a-pipelines-project-to-the-solution"></a><span data-ttu-id="02511-102">レッスン 1: パイプライン プロジェクトをソリューションに追加します。</span><span class="sxs-lookup"><span data-stu-id="02511-102">Lesson 1: Adding a Pipelines Project to the Solution</span></span>
<span data-ttu-id="02511-103">このレッスンでは、for SWIFT の新しい BizTalk プロジェクトをソリューションにパイプラインを送信をカスタマイズし、受信パイプラインを追加します。</span><span class="sxs-lookup"><span data-stu-id="02511-103">In this lesson, you add a new BizTalk project for SWIFT pipelines to the solution so you can customize your send and receive pipelines.</span></span>  
  
### <a name="to-add-a-new-swift-pipelines-project-to-the-solution"></a><span data-ttu-id="02511-104">新しい SWIFT パイプライン プロジェクトをソリューションに追加するには</span><span class="sxs-lookup"><span data-stu-id="02511-104">To add a new SWIFT pipelines project to the solution</span></span>  
  
1. <span data-ttu-id="02511-105">Visual Studio で、次のようにクリックします。**ファイル**、 をポイント**新規**、 をクリックし、**プロジェクト**します。</span><span class="sxs-lookup"><span data-stu-id="02511-105">In Visual Studio, click **File**, point to **New**, and then click **Project**.</span></span>  
  
2. <span data-ttu-id="02511-106">新しいプロジェクト ダイアログ ボックスで、**プロジェクトの種類**ペインで、 **BizTalk プロジェクト**フォルダー。</span><span class="sxs-lookup"><span data-stu-id="02511-106">In the New Project dialog box, in the **Project types** pane, select the **BizTalk Projects** folder.</span></span>  
  
3. <span data-ttu-id="02511-107">**テンプレート**ペインで、**空の BizTalk Server プロジェクト**します。</span><span class="sxs-lookup"><span data-stu-id="02511-107">In the **Templates** pane, select **Empty BizTalk Server Project**.</span></span>  
  
4. <span data-ttu-id="02511-108">**名前**ボックスに「 **SWIFTPipelines**プロジェクト名として。</span><span class="sxs-lookup"><span data-stu-id="02511-108">In the **Name** box, type **SWIFTPipelines** as the project name.</span></span>  
  
5. <span data-ttu-id="02511-109">**ソリューション**ボックスで、**ソリューションに追加**します。</span><span class="sxs-lookup"><span data-stu-id="02511-109">In the **Solution** box, select **Add to Solution**.</span></span> <span data-ttu-id="02511-110">**場所**ボックスで、[参照] を選択する **\<*ドライブ*:\>\labs\SWIFTProject**が選択されています。</span><span class="sxs-lookup"><span data-stu-id="02511-110">In the **Location** box, browse to select **\<*drive*:\>\labs\SWIFTProject** is selected.</span></span>  
  
6. <span data-ttu-id="02511-111">をクリックして**OK**を新しいプロジェクトを開きます。</span><span class="sxs-lookup"><span data-stu-id="02511-111">Click **OK** to open the new project.</span></span>  
  
    [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]<span data-ttu-id="02511-112"> ソリューション エクスプ ローラーに新しいプロジェクトを追加し、プロジェクト フォルダーを作成し、ファイル、 \<*ドライブ*\>: \Labs\SWIFTProject フォルダー。</span><span class="sxs-lookup"><span data-stu-id="02511-112"> adds a new project to Solution Explorer, and creates the project folder and files in the \<*drive*\>:\Labs\SWIFTProject folder.</span></span>  
  
7. <span data-ttu-id="02511-113">モジュール 2 SWIFTPipelines プロジェクトへのレッスン 2 で作成したアセンブリ キー ファイルを適用します。</span><span class="sxs-lookup"><span data-stu-id="02511-113">Apply the assembly key file that you created in lesson 2 of module 2 to the SWIFTPipelines project.</span></span> <span data-ttu-id="02511-114">詳細については、次を参照してください。[レッスン 2: SWIFTSchemas プロジェクト用の厳密な名前付きの BizTalk アセンブリを作成する](../../adapters-and-accelerators/accelerator-swift/lesson-2-creating-a-strong-named-biztalk-assembly-for-the-swiftschemas-project.md)します。</span><span class="sxs-lookup"><span data-stu-id="02511-114">For more information, see [Lesson 2: Creating a Strong-Named BizTalk Assembly for the SWIFTSchemas Project](../../adapters-and-accelerators/accelerator-swift/lesson-2-creating-a-strong-named-biztalk-assembly-for-the-swiftschemas-project.md).</span></span>  
  
   <span data-ttu-id="02511-115">続行する[レッスン 2: プロジェクト参照の追加](../../adapters-and-accelerators/accelerator-swift/lesson-2-adding-project-references.md)します。</span><span class="sxs-lookup"><span data-stu-id="02511-115">Proceed to [Lesson 2: Adding Project References](../../adapters-and-accelerators/accelerator-swift/lesson-2-adding-project-references.md).</span></span>