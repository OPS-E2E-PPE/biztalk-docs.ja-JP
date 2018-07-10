---
title: '手順 1: プロジェクトの配置 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0467c140-1f4c-4cfa-b46f-dc1d0f8755d4
caps.latest.revision: 44
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b25af8ee1095a5365fabd955f7185acbc79254db
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007555"
---
# <a name="step-1-deploy-the-projects"></a><span data-ttu-id="e9f48-102">ステップ 1: プロジェクトの配置</span><span class="sxs-lookup"><span data-stu-id="e9f48-102">Step 1: Deploy the Projects</span></span>
<span data-ttu-id="e9f48-103">![ステップ 1/3](../adapters-and-accelerators/adapter-oracle-database/media/step-1of3.gif "Step_1of3")</span><span class="sxs-lookup"><span data-stu-id="e9f48-103">![Step 1 of 3](../adapters-and-accelerators/adapter-oracle-database/media/step-1of3.gif "Step_1of3")</span></span>  
  
 <span data-ttu-id="e9f48-104">**所要時間:** 5 分</span><span class="sxs-lookup"><span data-stu-id="e9f48-104">**Time to complete:** 5 minutes</span></span>  
  
 <span data-ttu-id="e9f48-105">**目標:** この手順では、EAISchemas および EAIOrchestration プロジェクトを展開します。</span><span class="sxs-lookup"><span data-stu-id="e9f48-105">**Objective:** In this step, you deploy the EAISchemas and EAIOrchestration projects.</span></span>  
  
 <span data-ttu-id="e9f48-106">**目的:** アセンブリが自動的に構築され、指定したアプリケーションに展開されているプロジェクトまたは Visual Studio でソリューションを展開するときにします。</span><span class="sxs-lookup"><span data-stu-id="e9f48-106">**Purpose:** When you deploy a project or solution in Visual Studio, the assemblies are automatically built and deployed into the specified application.</span></span> <span data-ttu-id="e9f48-107">このプロセスの一部として、アセンブリは、アセンブリに含まれるオーケストレーション、スキーマ、およびマップ (これらは "アイテム" と呼ばれます) と共にローカルの BizTalk 管理データベースにインポートされ、データベース内で指定したアプリケーションに関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="e9f48-107">As part of this process, the assembly along with the orchestrations, schemas, and maps that it contains (called "artifacts") are imported into the local BizTalk Management database and associated in the database with the specified application.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="e9f48-108">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="e9f48-108">Prerequisites</span></span>  
  
- [<span data-ttu-id="e9f48-109">レッスン 1: スキーマおよびマップの定義</span><span class="sxs-lookup"><span data-stu-id="e9f48-109">Lesson 1: Define Schemas and a Map</span></span>](../core/lesson-1-define-schemas-and-a-map.md)  
  
- [<span data-ttu-id="e9f48-110">レッスン 2: ビジネス プロセスの定義</span><span class="sxs-lookup"><span data-stu-id="e9f48-110">Lesson 2: Define the Business Process</span></span>](../core/lesson-2-define-the-business-process.md)  
  
- <span data-ttu-id="e9f48-111">メンバーとしてサインイン、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators グループ</span><span class="sxs-lookup"><span data-stu-id="e9f48-111">Sign in as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group</span></span>

- <span data-ttu-id="e9f48-112">Visual Studio を管理者特権で実行します。</span><span class="sxs-lookup"><span data-stu-id="e9f48-112">Run Visual Studio with Administrative privileges</span></span>

> [!TIP]
> <span data-ttu-id="e9f48-113">必要なチュートリアル ファイルをダウンロードする[チュートリアル 1: エンタープライズ アプリケーション統合](https://www.microsoft.com/download/details.aspx?id=22793)します。</span><span class="sxs-lookup"><span data-stu-id="e9f48-113">You can download the required tutorial files at [Tutorial 1: Enterprise Application Integration](https://www.microsoft.com/download/details.aspx?id=22793).</span></span>

## <a name="open-the-solution-with-administrative-rights"></a><span data-ttu-id="e9f48-114">管理者権限を持つソリューションを開きます</span><span class="sxs-lookup"><span data-stu-id="e9f48-114">Open the solution with administrative rights</span></span>  
  
1. <span data-ttu-id="e9f48-115">BizTalk Server 管理者グループのメンバーとして Windows にサインインします。</span><span class="sxs-lookup"><span data-stu-id="e9f48-115">Sign in to Windows as a member of the BizTalk Server Administrators group.</span></span>  
  
2. <span data-ttu-id="e9f48-116">開始**Microsoft Visual Studio**に管理者として。</span><span class="sxs-lookup"><span data-stu-id="e9f48-116">Start **Microsoft Visual Studio** as an administrator.</span></span>  
  
3. <span data-ttu-id="e9f48-117">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]の**ファイル**メニューで、**オープン**、] をクリックし、**プロジェクト/ソリューション**。</span><span class="sxs-lookup"><span data-stu-id="e9f48-117">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], on the **File** menu, point to **Open**, and then click **Project/Solution**.</span></span>  
  
4. <span data-ttu-id="e9f48-118">**プロジェクトを開く** ダイアログ ボックスを参照、 **EAISolution.sln**プロジェクト ソリューション ファイル、およびクリックして**オープン**します。</span><span class="sxs-lookup"><span data-stu-id="e9f48-118">In the **Open Project** dialog box, browse to the **EAISolution.sln** project solution file, and then click **Open**.</span></span>  
  
   <span data-ttu-id="e9f48-119">展開プロセスでは、アセンブリが厳密に署名されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e9f48-119">The deployment process requires that assembly is strongly signed.</span></span>  <span data-ttu-id="e9f48-120">アセンブリに署名を行うには、厳密な名前のアセンブリ キー ファイルをプロジェクトに関連付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="e9f48-120">You must sign your assemblies by associating the project with a strong name assembly key file.</span></span>  <span data-ttu-id="e9f48-121">このファイルは、チュートリアル ファイルに含まれます。</span><span class="sxs-lookup"><span data-stu-id="e9f48-121">This file is included in the tutorial files.</span></span>  
  
   <span data-ttu-id="e9f48-122">BizTalk アプリケーションは、BizTalk Server ビジネス ソリューションの展開、管理、およびトラブルシューティングをすばやく簡単に行えるようにする BizTalk Server の機能です。</span><span class="sxs-lookup"><span data-stu-id="e9f48-122">The BizTalk application is a feature of BizTalk Server that makes it quicker and easier to deploy, manage, and troubleshoot BizTalk Server business solutions.</span></span> <span data-ttu-id="e9f48-123">BizTalk アプリケーションは、BizTalk Server ビジネス ソリューションで使用される "アイテム" の論理グループです。</span><span class="sxs-lookup"><span data-stu-id="e9f48-123">A BizTalk application is a logical grouping of the items, called "artifacts," used in a BizTalk Server business solution.</span></span> <span data-ttu-id="e9f48-124">プロジェクトのアプリケーション名を指定できます。</span><span class="sxs-lookup"><span data-stu-id="e9f48-124">We can specify an application name for a project.</span></span>  <span data-ttu-id="e9f48-125">展開プロセスには、存在しない場合は、指定の名前を持つ新しいアプリケーションを自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="e9f48-125">The deployment process automatically creates a new application having the specified name if it doesn’t exist.</span></span>  
  
## <a name="configure-and-deploy-the-projects"></a><span data-ttu-id="e9f48-126">構成し、プロジェクトの配置</span><span class="sxs-lookup"><span data-stu-id="e9f48-126">Configure and deploy the projects</span></span>  
  
1.  <span data-ttu-id="e9f48-127">ソリューション エクスプ ローラーで右クリックし、 **EAISchemas**プロジェクトをクリックして**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="e9f48-127">In Solution Explorer, right-click the **EAISchemas** project, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="e9f48-128">をクリックして、**署名**] タブで [**アセンブリに署名**します。</span><span class="sxs-lookup"><span data-stu-id="e9f48-128">Click the **Signing** tab, select **Sign the assembly**.</span></span>  
  
3.  <span data-ttu-id="e9f48-129">ドロップダウン リストから、**厳密な名前キー ファイルを選択して**ボックスで、 **\<を参照しています.\>**.</span><span class="sxs-lookup"><span data-stu-id="e9f48-129">From the drop-down list in the **Choose a strong name key file** box, select **\<Browse…\>**.</span></span>  
  
4.  <span data-ttu-id="e9f48-130">**ファイルの選択** ダイアログ ボックスに移動**C:\BTStutorials**、 をクリックして**btstutorials.snk**、順にクリックします**オープン**します。</span><span class="sxs-lookup"><span data-stu-id="e9f48-130">In the **Select File** dialog box, navigate to **C:\BTStutorials**, click **btsTutorials.snk**, and then click **Open**.</span></span> 
  
5.  <span data-ttu-id="e9f48-131">をクリックして、**展開**タブの右側にボックスで、**アプリケーション名**、型`EAISolution`します。</span><span class="sxs-lookup"><span data-stu-id="e9f48-131">Click the **Deployment** tab, in the box to the right of **Application Name**, type `EAISolution`.</span></span>  
  
6.  <span data-ttu-id="e9f48-132">ボックスの右側にドロップダウン リストから**再デプロイ**を選択します**True**します。</span><span class="sxs-lookup"><span data-stu-id="e9f48-132">From the drop-down list in the box to the right of **Redeploy**, select **True**.</span></span>  
  
7.  <span data-ttu-id="e9f48-133">ソリューション エクスプ ローラーで右クリックして**EAISchemas**、 をクリックし、**デプロイ**します。</span><span class="sxs-lookup"><span data-stu-id="e9f48-133">In Solution Explorer, right-click **EAISchemas**, and then click **Deploy**.</span></span>  <span data-ttu-id="e9f48-134">出力ウィンドウが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e9f48-134">The Output window should display:</span></span>  
  
    ```  
    ========== Build: 1 succeeded or up-to-date, 0 failed, 0 skipped ==========  
    ========== Deploy: 1 succeeded, 0 failed, 0 skipped ==========  
  
    ```  
  
8.  <span data-ttu-id="e9f48-135">手順 1 ~ 7 EAIOrchestration プロジェクトを配置する.</span><span class="sxs-lookup"><span data-stu-id="e9f48-135">Repeat steps 1 through 7 to deploy the EAIOrchestration project.</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="e9f48-136">でしただけ何か。</span><span class="sxs-lookup"><span data-stu-id="e9f48-136">What did I just do?</span></span>  
 <span data-ttu-id="e9f48-137">このステップでは、EAISchemas プロジェクトおよび EAIOrchestration プロジェクトを配置しました。</span><span class="sxs-lookup"><span data-stu-id="e9f48-137">In this step, you deployed the EAISchemas and EAIOrchestration projects.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="e9f48-138">次の手順</span><span class="sxs-lookup"><span data-stu-id="e9f48-138">Next Steps</span></span>  
 <span data-ttu-id="e9f48-139">物理ポートを作成し、オーケストレーションの論理ポートにバインドします。</span><span class="sxs-lookup"><span data-stu-id="e9f48-139">You create the physical ports, and bind them to the logical ports of the orchestration.</span></span>  
  
 <span data-ttu-id="e9f48-140">[手順 2: 構成し、アプリケーションを起動します](../core/step-2-configure-and-start-the-application1.md) </span><span class="sxs-lookup"><span data-stu-id="e9f48-140">[Step 2: Configure and Start the Application](../core/step-2-configure-and-start-the-application1.md) </span></span>  
 [<span data-ttu-id="e9f48-141">手順 3: ソリューションのテスト</span><span class="sxs-lookup"><span data-stu-id="e9f48-141">Step 3: Test the Solution</span></span>](../core/step-3-test-the-solution2.md)
