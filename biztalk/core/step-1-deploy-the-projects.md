---
title: "手順 1: 配置プロジェクト |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0467c140-1f4c-4cfa-b46f-dc1d0f8755d4
caps.latest.revision: "44"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eb4262b2bb424a339f866f3b4a14ae03c2e507f6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-1-deploy-the-projects"></a><span data-ttu-id="b87da-102">ステップ 1: プロジェクトの配置</span><span class="sxs-lookup"><span data-stu-id="b87da-102">Step 1: Deploy the Projects</span></span>
<span data-ttu-id="b87da-103">![手順 1/3](../adapters-and-accelerators/adapter-oracle-database/media/step-1of3.gif "Step_1of3")</span><span class="sxs-lookup"><span data-stu-id="b87da-103">![Step 1 of 3](../adapters-and-accelerators/adapter-oracle-database/media/step-1of3.gif "Step_1of3")</span></span>  
  
 <span data-ttu-id="b87da-104">**所要時間:** 5 分</span><span class="sxs-lookup"><span data-stu-id="b87da-104">**Time to complete:** 5 minutes</span></span>  
  
 <span data-ttu-id="b87da-105">**目標:** EAISchemas および EAIOrchestration プロジェクトを配置するこの手順でします。</span><span class="sxs-lookup"><span data-stu-id="b87da-105">**Objective:** In this step, you deploy the EAISchemas and EAIOrchestration projects.</span></span>  
  
 <span data-ttu-id="b87da-106">**目的:**プロジェクトまたは Visual Studio でソリューションを展開するときに、アセンブリに自動的に構築され、指定されたアプリケーションに展開します。</span><span class="sxs-lookup"><span data-stu-id="b87da-106">**Purpose:** When you deploy a project or solution in Visual Studio, the assemblies are automatically built and deployed into the specified application.</span></span> <span data-ttu-id="b87da-107">このプロセスの一部として、アセンブリは、アセンブリに含まれるオーケストレーション、スキーマ、およびマップ (これらは "アイテム" と呼ばれます) と共にローカルの BizTalk 管理データベースにインポートされ、データベース内で指定したアプリケーションに関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="b87da-107">As part of this process, the assembly along with the orchestrations, schemas, and maps that it contains (called "artifacts") are imported into the local BizTalk Management database and associated in the database with the specified application.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="b87da-108">前提条件</span><span class="sxs-lookup"><span data-stu-id="b87da-108">Prerequisites</span></span>  
 <span data-ttu-id="b87da-109">このステップを開始する前に、以下の要件を確認してください。</span><span class="sxs-lookup"><span data-stu-id="b87da-109">Note the following requirements before you begin this step:</span></span>  
  
-   <span data-ttu-id="b87da-110">このステップを開始する前に、次のレッスンを完了しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="b87da-110">Before you begin this step you must complete the following lessons:</span></span>  
  
    -   [<span data-ttu-id="b87da-111">レッスン 1: 定義のスキーマとマップ</span><span class="sxs-lookup"><span data-stu-id="b87da-111">Lesson 1: Define Schemas and a Map</span></span>](../core/lesson-1-define-schemas-and-a-map.md)  
  
    -   [<span data-ttu-id="b87da-112">レッスン 2: ビジネス プロセスを定義します。</span><span class="sxs-lookup"><span data-stu-id="b87da-112">Lesson 2: Define the Business Process</span></span>](../core/lesson-2-define-the-business-process.md)  
  
-   <span data-ttu-id="b87da-113">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループのメンバーとしてログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b87da-113">You must log on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
-   <span data-ttu-id="b87da-114">ユーザー アカウント制御 (UAC) をサポートするシステムでは、Visual Studio を管理者特権で実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b87da-114">On a system that supports User Account Control (UAC), you must run Visual Studio with Administrative privileges.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="b87da-115">手順</span><span class="sxs-lookup"><span data-stu-id="b87da-115">Procedures</span></span>  
 <span data-ttu-id="b87da-116">Visual Studio を使用してアプリケーションを展開するには、BizTalk Server 管理者グループのメンバーとして Windows にログオンして Visual Studio を管理者として実行します。</span><span class="sxs-lookup"><span data-stu-id="b87da-116">To deploy the application using Visual Studio, you must log on Windows as a member of the BizTalk Server Administrators group and run Visual Studio as administrator.</span></span>  <span data-ttu-id="b87da-117">そのようにしない場合は、"アクセスは拒否されました" というエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b87da-117">Otherwise you will get the “Access is denied” error.</span></span>  
  
#### <a name="to-open-the-solution-with-administrative-privileges"></a><span data-ttu-id="b87da-118">管理特権でソリューションを開くには</span><span class="sxs-lookup"><span data-stu-id="b87da-118">To open the solution with administrative privileges</span></span>  
  
1.  <span data-ttu-id="b87da-119">BizTalk Server 管理者グループのメンバーとして Windows にログオンします。</span><span class="sxs-lookup"><span data-stu-id="b87da-119">Log on Windows as a member of the BizTalk Server Administrators group.</span></span>  
  
2.  <span data-ttu-id="b87da-120">開始**Microsoft Visual Studio**を管理者として。</span><span class="sxs-lookup"><span data-stu-id="b87da-120">Start **Microsoft Visual Studio** as an administrator.</span></span>  
  
3.  <span data-ttu-id="b87da-121">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]の**ファイル**メニューのをポイント**開く**、クリックして**プロジェクト/ソリューション**です。</span><span class="sxs-lookup"><span data-stu-id="b87da-121">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], on the **File** menu, point to **Open**, and then click **Project/Solution**.</span></span>  
  
4.  <span data-ttu-id="b87da-122">**プロジェクトを開く** ダイアログ ボックスを参照、 **EAISolution.sln**プロジェクト ソリューション ファイルをクリックして**開く**です。</span><span class="sxs-lookup"><span data-stu-id="b87da-122">In the **Open Project** dialog box, browse to the **EAISolution.sln** project solution file, and then click **Open**.</span></span>  
  
 <span data-ttu-id="b87da-123">展開プロセスでは、アセンブリが厳密に署名されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="b87da-123">The deployment process requires that assembly is strongly signed.</span></span>  <span data-ttu-id="b87da-124">アセンブリに署名を行うには、厳密な名前のアセンブリ キー ファイルをプロジェクトに関連付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="b87da-124">You must sign your assemblies by associating the project with a strong name assembly key file.</span></span>  <span data-ttu-id="b87da-125">このファイルは、チュートリアル ファイルによって提供されます。</span><span class="sxs-lookup"><span data-stu-id="b87da-125">This file is provided by the tutorial files.</span></span>  
  
 <span data-ttu-id="b87da-126">BizTalk アプリケーションは、BizTalk Server ビジネス ソリューションの展開、管理、およびトラブルシューティングをすばやく簡単に行えるようにする BizTalk Server の機能です。</span><span class="sxs-lookup"><span data-stu-id="b87da-126">The BizTalk application is a feature of BizTalk Server that makes it quicker and easier to deploy, manage, and troubleshoot BizTalk Server business solutions.</span></span> <span data-ttu-id="b87da-127">BizTalk アプリケーションは、BizTalk Server ビジネス ソリューションで使用される "アイテム" の論理グループです。</span><span class="sxs-lookup"><span data-stu-id="b87da-127">A BizTalk application is a logical grouping of the items, called "artifacts," used in a BizTalk Server business solution.</span></span> <span data-ttu-id="b87da-128">プロジェクトのアプリケーション名を指定できます。</span><span class="sxs-lookup"><span data-stu-id="b87da-128">We can specify an application name for a project.</span></span>  <span data-ttu-id="b87da-129">展開プロセスでは、指定された名前を持つアプリケーションが存在しない場合、その新しいアプリケーションが自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="b87da-129">The deployment process will automatically create a new application having the specified name if it doesn’t exist.</span></span>  
  
#### <a name="to-configure-and-deploy-the-projects"></a><span data-ttu-id="b87da-130">プロジェクトを構成して展開するには</span><span class="sxs-lookup"><span data-stu-id="b87da-130">To configure and deploy the projects</span></span>  
  
1.  <span data-ttu-id="b87da-131">ソリューション エクスプ ローラーで右クリックし、 **EAISchemas**プロジェクトをクリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="b87da-131">In Solution Explorer, right-click the **EAISchemas** project, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="b87da-132">クリックして、**署名**] タブで [**アセンブリに署名**です。</span><span class="sxs-lookup"><span data-stu-id="b87da-132">Click the **Signing** tab, select **Sign the assembly**.</span></span>  
  
3.  <span data-ttu-id="b87da-133">ドロップダウン リストから、**厳密な名前キー ファイルを選択して**ボックスで、  **\<[参照...] >**です。</span><span class="sxs-lookup"><span data-stu-id="b87da-133">From the drop-down list in the **Choose a strong name key file** box, select **\<Browse…>**.</span></span>  
  
4.  <span data-ttu-id="b87da-134">**ファイルの選択** ダイアログ ボックスに移動**C:\BTStutorials**、 をクリックして**btstutorials.snk**、クリックして**開く**です。</span><span class="sxs-lookup"><span data-stu-id="b87da-134">In the **Select File** dialog box, navigate to **C:\BTStutorials**, click **btsTutorials.snk**, and then click **Open**.</span></span>  
  
5.  <span data-ttu-id="b87da-135">クリックして、**展開** タブで、ボックスの右側に**アプリケーション名**、型`EAISolution`です。</span><span class="sxs-lookup"><span data-stu-id="b87da-135">Click the **Deployment** tab, in the box to the right of **Application Name**, type `EAISolution`.</span></span>  
  
6.  <span data-ttu-id="b87da-136">ボックスの右側にドロップダウン リストから**再展開** **True**です。</span><span class="sxs-lookup"><span data-stu-id="b87da-136">From the drop-down list in the box to the right of **Redeploy**, select **True**.</span></span>  
  
7.  <span data-ttu-id="b87da-137">ソリューション エクスプ ローラーで右クリック**EAISchemas**、クリックして**展開**です。</span><span class="sxs-lookup"><span data-stu-id="b87da-137">In Solution Explorer, right-click **EAISchemas**, and then click **Deploy**.</span></span>  <span data-ttu-id="b87da-138">出力ウィンドウが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b87da-138">The Output window should display:</span></span>  
  
    ```  
    ========== Build: 1 succeeded or up-to-date, 0 failed, 0 skipped ==========  
    ========== Deploy: 1 succeeded, 0 failed, 0 skipped ==========  
  
    ```  
  
8.  <span data-ttu-id="b87da-139">手順 1. ～ 7. を繰り返して、EAIOrchestration プロジェクトを展開します。</span><span class="sxs-lookup"><span data-stu-id="b87da-139">Repeat step 1 through 7 to deploy the EAIOrchestration project.</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="b87da-140">でしただけは何ですか。</span><span class="sxs-lookup"><span data-stu-id="b87da-140">What did I just do?</span></span>  
 <span data-ttu-id="b87da-141">このステップでは、EAISchemas プロジェクトおよび EAIOrchestration プロジェクトを配置しました。</span><span class="sxs-lookup"><span data-stu-id="b87da-141">In this step, you deployed the EAISchemas and EAIOrchestration projects.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="b87da-142">次の手順</span><span class="sxs-lookup"><span data-stu-id="b87da-142">Next Steps</span></span>  
 <span data-ttu-id="b87da-143">物理ポートを作成し、オーケストレーションの論理ポートにバインドします。</span><span class="sxs-lookup"><span data-stu-id="b87da-143">You create the physical ports, and bind them to the logical ports of the orchestration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b87da-144">参照</span><span class="sxs-lookup"><span data-stu-id="b87da-144">See Also</span></span>  
 <span data-ttu-id="b87da-145">[手順 2: を構成し、アプリケーションを起動](../core/step-2-configure-and-start-the-application1.md) </span><span class="sxs-lookup"><span data-stu-id="b87da-145">[Step 2: Configure and Start the Application](../core/step-2-configure-and-start-the-application1.md) </span></span>  
 [<span data-ttu-id="b87da-146">手順 3: ソリューションをテストします。</span><span class="sxs-lookup"><span data-stu-id="b87da-146">Step 3: Test the Solution</span></span>](../core/step-3-test-the-solution2.md)