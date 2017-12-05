---
title: "レッスン 1: 新しい BizTalk プロジェクトの追加 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- schemas, adding to projects
- projects
ms.assetid: 874d2f9e-36e2-4c7b-970c-76417a536a97
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 942ef00948920cd19e2a34e0be52d61a8f492786
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="lesson-1-adding-a-new-biztalk-project"></a><span data-ttu-id="597a8-102">レッスン 1: 新しい BizTalk プロジェクトの追加</span><span class="sxs-lookup"><span data-stu-id="597a8-102">Lesson 1: Adding a New BizTalk Project</span></span>
<span data-ttu-id="597a8-103">このレッスンでは、ソリューションに新しい BizTalk プロジェクトを追加します。</span><span class="sxs-lookup"><span data-stu-id="597a8-103">In this lesson, you add a new BizTalk project to your solution.</span></span> <span data-ttu-id="597a8-104">このチュートリアルで使用するプロジェクトでスキーマを作成します。</span><span class="sxs-lookup"><span data-stu-id="597a8-104">You create schemas in this project that you use throughout the tutorial.</span></span>  
  
 <span data-ttu-id="597a8-105">BizTalk マッパー, など、BizTalk ツール内で公開する BizTalk プロジェクト テンプレートを選択する、 [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] [!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)]開発環境です。</span><span class="sxs-lookup"><span data-stu-id="597a8-105">Selecting the BizTalk project template exposes the BizTalk tools, such as BizTalk Mapper, within the [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)][!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] development environment.</span></span>  
  
### <a name="to-add-a-new-biztalk-project"></a><span data-ttu-id="597a8-106">新しい BizTalk プロジェクトに追加するには</span><span class="sxs-lookup"><span data-stu-id="597a8-106">To add a new BizTalk project</span></span>  
  
1.  <span data-ttu-id="597a8-107">Visual Studio で、[**ファイル**、] をポイント**新規**、クリックして**プロジェクト**です。</span><span class="sxs-lookup"><span data-stu-id="597a8-107">In Visual Studio, click **File**, point to **New**, and then click **Project**.</span></span>  
  
2.  <span data-ttu-id="597a8-108">新しいプロジェクト ダイアログ ボックスで、**プロジェクトの種類**ペインで、 **BizTalk プロジェクト**フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="597a8-108">In the New Project dialog box, in the **Project types** pane, select the **BizTalk Projects** folder.</span></span>  
  
3.  <span data-ttu-id="597a8-109">**テンプレート**ペインで、**空の BizTalk Server プロジェクト**です。</span><span class="sxs-lookup"><span data-stu-id="597a8-109">In the **Templates** pane, select **Empty BizTalk Server Project**.</span></span>  
  
4.  <span data-ttu-id="597a8-110">**名前**ボックスに、入力**SWIFTSchemas**プロジェクト名として。</span><span class="sxs-lookup"><span data-stu-id="597a8-110">In the **Name** box, type **SWIFTSchemas** as the project name.</span></span>  
  
5.  <span data-ttu-id="597a8-111">**ソリューション**ボックスで、**ソリューションに追加**です。</span><span class="sxs-lookup"><span data-stu-id="597a8-111">In the **Solution** box, select **Add to Solution**.</span></span> <span data-ttu-id="597a8-112">**場所**ボックスしていることを確認するには、   **\<*ドライブ*:\>\labs\SWIFTProject** が選択されています。</span><span class="sxs-lookup"><span data-stu-id="597a8-112">In the **Location** box, ensure that **\<*drive*:\>\labs\SWIFTProject** is selected.</span></span>  
  
6.  <span data-ttu-id="597a8-113">をクリックして**OK**新しいプロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="597a8-113">Click **OK** to create the new project.</span></span>  
  
     [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]<span data-ttu-id="597a8-114">ソリューション エクスプ ローラーに新しいプロジェクトを追加し、プロジェクト フォルダーが作成され、内のファイル、 \<*ドライブ*:\>\labs\SWIFTProject\SWIFTSchemas フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="597a8-114"> adds a new project to Solution Explorer and creates the project folder and files in the \<*drive*:\>\labs\SWIFTProject\SWIFTSchemas folder.</span></span>  
  
 <span data-ttu-id="597a8-115">進みます[レッスン 2: SWIFTSchemas プロジェクトの厳密な名前の BizTalk アセンブリを作成する](../../adapters-and-accelerators/accelerator-swift/lesson-2-creating-a-strong-named-biztalk-assembly-for-the-swiftschemas-project.md)です。</span><span class="sxs-lookup"><span data-stu-id="597a8-115">Proceed to [Lesson 2: Creating a Strong-Named BizTalk Assembly for the SWIFTSchemas Project](../../adapters-and-accelerators/accelerator-swift/lesson-2-creating-a-strong-named-biztalk-assembly-for-the-swiftschemas-project.md).</span></span>