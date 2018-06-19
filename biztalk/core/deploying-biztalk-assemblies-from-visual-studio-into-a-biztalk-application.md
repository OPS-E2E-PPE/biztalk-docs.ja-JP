---
title: BizTalk アプリケーションに Visual Studio から BizTalk アセンブリを展開する |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: accef4b8-acdf-4043-8fd7-2db9ea752074
caps.latest.revision: 36
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e1165fb461d5d54419ea56a42f7fe428ab027089
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22240090"
---
# <a name="deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application"></a><span data-ttu-id="f8e8a-102">Visual Studio から BizTalk アプリケーションへの BizTalk アセンブリの展開</span><span class="sxs-lookup"><span data-stu-id="f8e8a-102">Deploying BizTalk Assemblies from Visual Studio into a BizTalk Application</span></span>
<span data-ttu-id="f8e8a-103">およびから BizTalk アセンブリを再展開[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]BizTalk アプリケーションにします。</span><span class="sxs-lookup"><span data-stu-id="f8e8a-103">Deploy and redeploy BizTalk assemblies from [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] into a BizTalk application.</span></span> <span data-ttu-id="f8e8a-104">この処理を使用して、開発したアセンブリの機能をテストし、ハンドオフ用にパッケージすることができます。</span><span class="sxs-lookup"><span data-stu-id="f8e8a-104">You may want to do this to test the functionality of the assemblies that you have been developing and package them for handoff.</span></span>  

## <a name="overview"></a><span data-ttu-id="f8e8a-105">概要</span><span class="sxs-lookup"><span data-stu-id="f8e8a-105">Overview</span></span>  
 <span data-ttu-id="f8e8a-106">BizTalk アプリケーションは、BizTalk ビジネス ソリューションを構成する "アイテム" を表示して管理する手段を提供します。</span><span class="sxs-lookup"><span data-stu-id="f8e8a-106">BizTalk applications provide a way to view and manage the items, called "artifacts," that comprise a BizTalk business solution.</span></span> <span data-ttu-id="f8e8a-107">アイテムに含まれる BizTalk アセンブリ (オーケストレーション、スキーマ、マップ、パイプラインなど) は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] から [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] に展開できます。</span><span class="sxs-lookup"><span data-stu-id="f8e8a-107">Artifacts include BizTalk assemblies (containing orchestrations, schemas, maps, and pipelines), which you can deploy into [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] from [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="f8e8a-108">また、アイテムには .NET アセンブリ、証明書、スクリプト、Readme ファイル、ポリシーなども含まれます。これらは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールまたは BTSTask コマンドライン ツールを使用して BizTalk アプリケーションに追加します。</span><span class="sxs-lookup"><span data-stu-id="f8e8a-108">Artifacts also include items such as .NET assemblies, certificates, scripts, Readme files, and policies, which you add to your BizTalk application by using the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console or the BTSTask command-line tool.</span></span> <span data-ttu-id="f8e8a-109">その後、ソリューション開発者や IT 管理者は、アプリケーションとそのアイテムを 1 つのエンティティとして表示、パッケージ化、展開、および管理できます。</span><span class="sxs-lookup"><span data-stu-id="f8e8a-109">The solution developer or IT administrator can then view, package, deploy, and manage the application and its artifacts as a single entity.</span></span> <span data-ttu-id="f8e8a-110">作成の詳細については、配置、および BizTalk アプリケーションの管理について[を管理する BizTalk アプリケーションの展開と](../core/deploying-and-managing-biztalk-applications.md)です。</span><span class="sxs-lookup"><span data-stu-id="f8e8a-110">For more information about creating, deploying, and managing BizTalk applications, see [Deploying and Managing BizTalk Applications](../core/deploying-and-managing-biztalk-applications.md).</span></span>  
  
 <span data-ttu-id="f8e8a-111">BizTalk アセンブリをビルドおよび展開するには、まず [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] でプロジェクトを作成し、アセンブリに組み込むアイテムを作成または追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f8e8a-111">Before you can build and deploy a BizTalk assembly, you must create a project in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] and either create or add the items that you want to include in the assembly.</span></span> <span data-ttu-id="f8e8a-112">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] でソリューションを作成して、複数のプロジェクトを組み込んだ後、アセンブリをビルドし、すべてのアセンブリをまとめて同じアプリケーションまたは異なるアプリケーションに展開できます。</span><span class="sxs-lookup"><span data-stu-id="f8e8a-112">You can create a solution in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] to contain multiple projects and then build and deploy their assemblies all at once into the same application or different applications.</span></span> <span data-ttu-id="f8e8a-113">これらのタスクの実行方法の詳細については、次を参照してください。 [BizTalk プロジェクトを作成する方法](../core/how-to-create-biztalk-projects.md)です。</span><span class="sxs-lookup"><span data-stu-id="f8e8a-113">For instructions on performing these tasks, see [How to Create BizTalk Projects](../core/how-to-create-biztalk-projects.md).</span></span>  
  
 <span data-ttu-id="f8e8a-114">これらの作業が完了した後は、このセクションの各トピックで説明されている手順に従って、BizTalk アセンブリのビルド、展開、および展開解除を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="f8e8a-114">After completing these tasks, you can build, deploy, and undeploy the BizTalk assemblies by taking the following steps, as described in the topics in this section:</span></span>  
  
-   <span data-ttu-id="f8e8a-115">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] プロジェクトごとに厳密な名前のアセンブリ キー ファイルを構成します。</span><span class="sxs-lookup"><span data-stu-id="f8e8a-115">Configure a strong name assembly key file for each [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] project.</span></span>  
  
-   <span data-ttu-id="f8e8a-116">アセンブリを簡単に再展開するための再展開オプションの構成など、プロジェクトの展開プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="f8e8a-116">Set deployment properties for the project, including configuring the Redeploy option to easily redeploy the assembly.</span></span>  
  
-   <span data-ttu-id="f8e8a-117">ソリューションに含まれる BizTalk アセンブリをビルドし、BizTalk アプリケーションに展開するには、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] の展開コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="f8e8a-117">Use the Deploy command in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] to build the BizTalk assemblies contained in a solution and deploy them into a BizTalk application.</span></span> <span data-ttu-id="f8e8a-118">または、展開コマンドを使用してアセンブリをビルドし、単一のプロジェクトに展開することもできますが、この方法はお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="f8e8a-118">Alternatively, you can use the Deploy command to build and deploy an assembly in a single project, although we do not recommend doing this.</span></span>  
  
-   <span data-ttu-id="f8e8a-119">アプリケーションをテストし、必要な変更を行った後、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] の展開コマンドを使用して、アセンブリのリビルドと再展開を行います。</span><span class="sxs-lookup"><span data-stu-id="f8e8a-119">After testing the application and making necessary changes, use the Deploy command in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] to rebuild and redeploy the assembly.</span></span>  
  
-   <span data-ttu-id="f8e8a-120">必要に応じて、グローバル アセンブリ キャッシュ (GAC) にアセンブリをインストール、または GAC からアセンブリを削除します。</span><span class="sxs-lookup"><span data-stu-id="f8e8a-120">Install the assembly in the global assembly cache (GAC), if necessary, or remove the assembly from the GAC.</span></span>  
  
-   <span data-ttu-id="f8e8a-121">アセンブリを展開解除します。</span><span class="sxs-lookup"><span data-stu-id="f8e8a-121">Undeploy the assembly.</span></span>  
  
 <span data-ttu-id="f8e8a-122">BizTalk アプリケーションに 1 つ以上のアセンブリを展開した後は、アプリケーションの構成を完了し、テスト環境に展開し、さらに実稼働環境に展開できます。</span><span class="sxs-lookup"><span data-stu-id="f8e8a-122">After deploying one or more assemblies into a BizTalk application, you can complete the configuration of the application and deploy it into a test and then production environment.</span></span> <span data-ttu-id="f8e8a-123">詳細については、次を参照してください。 [BizTalk アプリケーション展開の開発タスク](../core/development-tasks-for-biztalk-application-deployment.md)です。</span><span class="sxs-lookup"><span data-stu-id="f8e8a-123">For more information, see [Development Tasks for BizTalk Application Deployment](../core/development-tasks-for-biztalk-application-deployment.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f8e8a-124">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="f8e8a-124">In This Section</span></span>  
  
-   [<span data-ttu-id="f8e8a-125">Visual Studio からアセンブリを展開するときの動作します。</span><span class="sxs-lookup"><span data-stu-id="f8e8a-125">What Happens When You Deploy an Assembly from Visual Studio</span></span>](../core/what-happens-when-you-deploy-an-assembly-from-visual-studio.md)  
  
-   [<span data-ttu-id="f8e8a-126">GAC にアセンブリのインストール</span><span class="sxs-lookup"><span data-stu-id="f8e8a-126">Assembly Installation in the GAC</span></span>](../core/assembly-installation-in-the-gac.md)  
  
-   [<span data-ttu-id="f8e8a-127">厳密な名前のアセンブリ キー ファイルを構成する方法</span><span class="sxs-lookup"><span data-stu-id="f8e8a-127">How to Configure a Strong Name Assembly Key File</span></span>](../core/how-to-configure-a-strong-name-assembly-key-file.md)  
  
-   [<span data-ttu-id="f8e8a-128">Visual Studio での展開のプロパティを設定する方法</span><span class="sxs-lookup"><span data-stu-id="f8e8a-128">How to Set Deployment Properties in Visual Studio</span></span>](../core/how-to-set-deployment-properties-in-visual-studio.md)  
  
-   [<span data-ttu-id="f8e8a-129">Visual Studio から BizTalk アセンブリを展開する方法</span><span class="sxs-lookup"><span data-stu-id="f8e8a-129">How to Deploy a BizTalk Assembly from Visual Studio</span></span>](../core/how-to-deploy-a-biztalk-assembly-from-visual-studio.md)  
  
-   [<span data-ttu-id="f8e8a-130">Visual Studio から BizTalk アセンブリを再展開する方法</span><span class="sxs-lookup"><span data-stu-id="f8e8a-130">How to Redeploy a BizTalk Assembly from Visual Studio</span></span>](../core/how-to-redeploy-a-biztalk-assembly-from-visual-studio.md)  
  
-   [<span data-ttu-id="f8e8a-131">インストールする方法または GAC にアセンブリをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="f8e8a-131">How to Install or uninstall an Assembly in the GAC</span></span>](../core/how-to-install-an-assembly-in-the-gac.md)  