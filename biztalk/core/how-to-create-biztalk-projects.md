---
title: BizTalk プロジェクトを作成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating, projects
- projects, creating
- solutions
- solutions, adding projects
ms.assetid: a6900234-f989-4601-96c5-41d435c2f8b4
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0c21d98c829f98c321902a4431bc19ab03a79293
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385503"
---
# <a name="how-to-create-biztalk-projects"></a><span data-ttu-id="13c93-102">BizTalk プロジェクトを作成する方法</span><span class="sxs-lookup"><span data-stu-id="13c93-102">How to Create BizTalk Projects</span></span>
<span data-ttu-id="13c93-103">BizTalk Server で実行するアプリケーションを作成するには、まずソリューションに 1 つ以上の BizTalk プロジェクトを追加します。</span><span class="sxs-lookup"><span data-stu-id="13c93-103">To create an application that runs on BizTalk Server, you start by adding one or more BizTalk projects to a solution.</span></span> <span data-ttu-id="13c93-104">このセクションでは、BizTalk プロジェクトの操作で行われる作業について説明します。</span><span class="sxs-lookup"><span data-stu-id="13c93-104">This section describes some of the tasks that you might perform when you work with BizTalk projects.</span></span>  
  
 <span data-ttu-id="13c93-105">ソリューションとプロジェクトの作成に関する詳細については、「ソリューション、プロジェクト、および項目の概要」を参照してください、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]連結ヘルプ コレクション[ http://go.microsoft.com/fwlink/?LinkId=124069](http://go.microsoft.com/fwlink/?LinkId=124069)します。</span><span class="sxs-lookup"><span data-stu-id="13c93-105">For more information about creating solutions and projects, see "Introduction to Solutions, Projects, and Items" in the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Combined Collection at [http://go.microsoft.com/fwlink/?LinkId=124069](http://go.microsoft.com/fwlink/?LinkId=124069).</span></span>  
  
### <a name="to-create-a-biztalk-project"></a><span data-ttu-id="13c93-106">BizTalk プロジェクトを作成するには</span><span class="sxs-lookup"><span data-stu-id="13c93-106">To create a BizTalk project</span></span>  
  
1. <span data-ttu-id="13c93-107">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], の **ファイル** メニューをポイント **新規**, 、クリックして **プロジェクト**します。</span><span class="sxs-lookup"><span data-stu-id="13c93-107">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], on the **File** menu, point to **New**, and then click **Project**.</span></span>  
  
2. <span data-ttu-id="13c93-108">**新しいプロジェクト**] ダイアログ ボックスで、**プロジェクトの種類**領域で、[ **BizTalk プロジェクト**します。</span><span class="sxs-lookup"><span data-stu-id="13c93-108">In the **New Project** dialog box, in the **Project Types** area, select **BizTalk Projects**.</span></span>  
  
3. <span data-ttu-id="13c93-109">**テンプレート**領域で、BizTalk Server プロジェクト テンプレートのいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="13c93-109">In the **Templates** area, select one of the BizTalk Server Project templates.</span></span>  
  
4. <span data-ttu-id="13c93-110">プロジェクトの名前と場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="13c93-110">Specify project name and its location.</span></span>  
  
5. <span data-ttu-id="13c93-111">選択**新しいソリューションを作成する** をクリック**OK**します。</span><span class="sxs-lookup"><span data-stu-id="13c93-111">Select **Create New Solution** and click **OK**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="13c93-112">[ユーザー構成可能なプロパティの一部、**新しいプロジェクト**] ダイアログ ボックスでは、BizTalk プロジェクト システムを使用する場合にのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="13c93-112">Some of the user configurable properties in the **New Projects** dialog box appear only when you are working with the BizTalk project system.</span></span> <span data-ttu-id="13c93-113">別の BizTalk Server プロジェクト テンプレートとその使用の詳細については、次を参照してください。 [BizTalk Server プロジェクト テンプレート](../core/biztalk-server-project-templates.md)します。</span><span class="sxs-lookup"><span data-stu-id="13c93-113">For more information about the different BizTalk Server project templates and their use, see [BizTalk Server Project Templates](../core/biztalk-server-project-templates.md).</span></span>  
  
### <a name="to-add-a-new-biztalk-project-to-a-solution"></a><span data-ttu-id="13c93-114">ソリューションに新しい BizTalk プロジェクトを追加するには</span><span class="sxs-lookup"><span data-stu-id="13c93-114">To add a new BizTalk project to a solution</span></span>  
  
1. <span data-ttu-id="13c93-115">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]で、ソリューションを開きます。</span><span class="sxs-lookup"><span data-stu-id="13c93-115">Open the solution in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
2. <span data-ttu-id="13c93-116">ソリューション名を右クリックし、[**追加**、] をクリック**新しいプロジェクト**します。</span><span class="sxs-lookup"><span data-stu-id="13c93-116">Right-click the solution name, point to **Add**, and click **New Project**.</span></span>  
  
3. <span data-ttu-id="13c93-117">**プロジェクトの種類**領域で、 **BizTalk プロジェクト**、し、**テンプレート**領域で、BizTalk Server プロジェクト テンプレートのいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="13c93-117">In the **Project Types** area, select **BizTalk Projects**, and in the **Templates** area, select one of the BizTalk Server Project templates.</span></span>  
  
4. <span data-ttu-id="13c93-118">選択**ソリューションに追加** をクリック**OK**します。</span><span class="sxs-lookup"><span data-stu-id="13c93-118">Select **Add to Solution** and click **OK**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="13c93-119">次のメニュー コマンドがサポートされていない、**オープン**のサブメニューで開く、**ファイル**メニュー。**Web からプロジェクトを**と**Web からファイルを**します。</span><span class="sxs-lookup"><span data-stu-id="13c93-119">The following menu commands are not supported on the **Open** submenu of the **File** menu: **Project From Web** and **File From Web**.</span></span> <span data-ttu-id="13c93-120">詳細については、次を参照してください。 [Visual Studio を使って](../core/using-visual-studio.md)します。</span><span class="sxs-lookup"><span data-stu-id="13c93-120">For more information, see [Using Visual Studio](../core/using-visual-studio.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="13c93-121">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="13c93-121">In This Section</span></span>  
  
-   [<span data-ttu-id="13c93-122">BizTalk プロジェクトを作成する際の考慮事項</span><span class="sxs-lookup"><span data-stu-id="13c93-122">Considerations When Creating BizTalk Projects</span></span>](../core/considerations-when-creating-biztalk-projects.md)  
  
-   [<span data-ttu-id="13c93-123">プロジェクト項目の追加</span><span class="sxs-lookup"><span data-stu-id="13c93-123">Adding Project Items</span></span>](../core/adding-project-items.md)  
  
-   [<span data-ttu-id="13c93-124">ソリューション ビルドの構成</span><span class="sxs-lookup"><span data-stu-id="13c93-124">Solution Build Configurations</span></span>](../core/solution-build-configurations.md)