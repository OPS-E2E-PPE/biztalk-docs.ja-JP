---
title: "BizTalk プロジェクトを作成する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- creating, projects
- projects, creating
- solutions
- solutions, adding projects
ms.assetid: a6900234-f989-4601-96c5-41d435c2f8b4
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f8fa1315055b3ad48ccbe1a15911cdafcf242ced
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-create-biztalk-projects"></a><span data-ttu-id="7517d-102">BizTalk プロジェクトを作成する方法</span><span class="sxs-lookup"><span data-stu-id="7517d-102">How to Create BizTalk Projects</span></span>
<span data-ttu-id="7517d-103">BizTalk Server で実行するアプリケーションを作成するには、まずソリューションに 1 つ以上の BizTalk プロジェクトを追加します。</span><span class="sxs-lookup"><span data-stu-id="7517d-103">To create an application that runs on BizTalk Server, you start by adding one or more BizTalk projects to a solution.</span></span> <span data-ttu-id="7517d-104">このセクションでは、BizTalk プロジェクトの操作で行われる作業について説明します。</span><span class="sxs-lookup"><span data-stu-id="7517d-104">This section describes some of the tasks that you might perform when you work with BizTalk projects.</span></span>  
  
 <span data-ttu-id="7517d-105">ソリューションとプロジェクトの作成に関する詳細については、「ソリューション、プロジェクト、および項目の概要」を参照してください、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]連結ヘルプ コレクション[http://go.microsoft.com/fwlink/?LinkId=124069](http://go.microsoft.com/fwlink/?LinkId=124069)です。</span><span class="sxs-lookup"><span data-stu-id="7517d-105">For more information about creating solutions and projects, see "Introduction to Solutions, Projects, and Items" in the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Combined Collection at [http://go.microsoft.com/fwlink/?LinkId=124069](http://go.microsoft.com/fwlink/?LinkId=124069).</span></span>  
  
### <a name="to-create-a-biztalk-project"></a><span data-ttu-id="7517d-106">BizTalk プロジェクトを作成するには</span><span class="sxs-lookup"><span data-stu-id="7517d-106">To create a BizTalk project</span></span>  
  
1.  <span data-ttu-id="7517d-107">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]の**ファイル**メニューのをポイント**新規**、クリックして**プロジェクト**です。</span><span class="sxs-lookup"><span data-stu-id="7517d-107">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], on the **File** menu, point to **New**, and then click **Project**.</span></span>  
  
2.  <span data-ttu-id="7517d-108">**新しいプロジェクト** ダイアログ ボックスで、**プロジェクトの種類**領域で、 **BizTalk プロジェクト**です。</span><span class="sxs-lookup"><span data-stu-id="7517d-108">In the **New Project** dialog box, in the **Project Types** area, select **BizTalk Projects**.</span></span>  
  
3.  <span data-ttu-id="7517d-109">**テンプレート**領域で、BizTalk Server プロジェクト テンプレートのいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="7517d-109">In the **Templates** area, select one of the BizTalk Server Project templates.</span></span>  
  
4.  <span data-ttu-id="7517d-110">プロジェクトの名前と場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="7517d-110">Specify project name and its location.</span></span>  
  
5.  <span data-ttu-id="7517d-111">選択**新しいソリューションを作成する** をクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="7517d-111">Select **Create New Solution** and click **OK**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7517d-112">一部のユーザー構成可能なプロパティの**新しいプロジェクト** ダイアログ ボックスでは、BizTalk プロジェクト システムで作業する場合にのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="7517d-112">Some of the user configurable properties in the **New Projects** dialog box appear only when you are working with the BizTalk project system.</span></span> <span data-ttu-id="7517d-113">別の BizTalk Server プロジェクト テンプレートおよびその使用に関する詳細については、次を参照してください。 [BizTalk Server プロジェクト テンプレート](../core/biztalk-server-project-templates.md)です。</span><span class="sxs-lookup"><span data-stu-id="7517d-113">For more information about the different BizTalk Server project templates and their use, see [BizTalk Server Project Templates](../core/biztalk-server-project-templates.md).</span></span>  
  
### <a name="to-add-a-new-biztalk-project-to-a-solution"></a><span data-ttu-id="7517d-114">ソリューションに新しい BizTalk プロジェクトを追加するには</span><span class="sxs-lookup"><span data-stu-id="7517d-114">To add a new BizTalk project to a solution</span></span>  
  
1.  <span data-ttu-id="7517d-115">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]で、ソリューションを開きます。</span><span class="sxs-lookup"><span data-stu-id="7517d-115">Open the solution in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
2.  <span data-ttu-id="7517d-116">ソリューション名を右クリックし、[**追加**、] をクリック**新しいプロジェクト**です。</span><span class="sxs-lookup"><span data-stu-id="7517d-116">Right-click the solution name, point to **Add**, and click **New Project**.</span></span>  
  
3.  <span data-ttu-id="7517d-117">**プロジェクトの種類**領域で、 **BizTalk プロジェクト**、し、、**テンプレート**領域で、BizTalk Server プロジェクト テンプレートのいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="7517d-117">In the **Project Types** area, select **BizTalk Projects**, and in the **Templates** area, select one of the BizTalk Server Project templates.</span></span>  
  
4.  <span data-ttu-id="7517d-118">選択**ソリューションに追加** をクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="7517d-118">Select **Add to Solution** and click **OK**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7517d-119">は、次のメニュー コマンドはサポートされていない、**開く**サブメニューの**ファイル**メニュー:**プロジェクトから Web**と**ファイルから Web**です。</span><span class="sxs-lookup"><span data-stu-id="7517d-119">The following menu commands are not supported on the **Open** submenu of the **File** menu: **Project From Web** and **File From Web**.</span></span> <span data-ttu-id="7517d-120">詳細については、次を参照してください。 [Visual Studio を使って](../core/using-visual-studio.md)です。</span><span class="sxs-lookup"><span data-stu-id="7517d-120">For more information, see [Using Visual Studio](../core/using-visual-studio.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7517d-121">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="7517d-121">In This Section</span></span>  
  
-   [<span data-ttu-id="7517d-122">BizTalk プロジェクトを作成する際の考慮事項</span><span class="sxs-lookup"><span data-stu-id="7517d-122">Considerations When Creating BizTalk Projects</span></span>](../core/considerations-when-creating-biztalk-projects.md)  
  
-   [<span data-ttu-id="7517d-123">プロジェクト項目の追加</span><span class="sxs-lookup"><span data-stu-id="7517d-123">Adding Project Items</span></span>](../core/adding-project-items.md)  
  
-   [<span data-ttu-id="7517d-124">ソリューション ビルド構成</span><span class="sxs-lookup"><span data-stu-id="7517d-124">Solution Build Configurations</span></span>](../core/solution-build-configurations.md)