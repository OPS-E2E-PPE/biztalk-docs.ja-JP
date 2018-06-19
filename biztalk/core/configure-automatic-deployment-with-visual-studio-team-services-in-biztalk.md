---
title: Visual Studio Team Services での自動展開の構成 |Microsoft ドキュメント
description: Vsts アプリケーション ライフ サイクル管理を使用して、別の BizTalk 環境にアプリケーションを展開する BizTalk Feature Pack をインストールします。
ms.custom: ''
ms.date: 11/20/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 57f769bb-5105-43e2-9096-ed54cdf82b90
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d135960143fed33d1ce4847c681f5b1134489b65
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/17/2018
ms.locfileid: "25497883"
---
# <a name="configure-automatic-deployment-with-visual-studio-team-services-in-biztalk-server"></a><span data-ttu-id="03786-103">BizTalk Server での Visual Studio Team Services の自動展開を構成します。</span><span class="sxs-lookup"><span data-stu-id="03786-103">Configure automatic deployment with Visual Studio Team Services in BizTalk Server</span></span>

## <a name="overview"></a><span data-ttu-id="03786-104">概要</span><span class="sxs-lookup"><span data-stu-id="03786-104">Overview</span></span>

<span data-ttu-id="03786-105">**以降で[!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]** 、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]強化された自動展開とアプリケーション ライフ サイクル管理 (ALM) のエクスペリエンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="03786-105">**Starting with [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]**, [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] provides an improved automatic deployment and application lifecycle management (ALM) experience.</span></span> 

<span data-ttu-id="03786-106">**以降で[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]Feature Pack 2**、この機能を改良しました。</span><span class="sxs-lookup"><span data-stu-id="03786-106">**Starting with [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] Feature Pack 2**, we've improved this feature:</span></span>

* <span data-ttu-id="03786-107">Visual Studio 内で、設定、**アプリケーション名**BizTalk アプリケーションの</span><span class="sxs-lookup"><span data-stu-id="03786-107">Within Visual Studio, set the **Application Name** of your BizTalk application</span></span>
* <span data-ttu-id="03786-108">エージェント ベースの展開を使用して、に加えて使用することも[展開グループ](https://docs.microsoft.com/vsts/build-release/concepts/definitions/release/deployment-groups/index)複数のサーバーに、BizTalk アプリケーションを展開するには</span><span class="sxs-lookup"><span data-stu-id="03786-108">In addition to using an agent-based deployment, you can also use [deployment groups](https://docs.microsoft.com/vsts/build-release/concepts/definitions/release/deployment-groups/index) to deploy your BizTalk applications to multiple servers</span></span>
* <span data-ttu-id="03786-109">リリース タスクで、BizTalk アプリケーションをインストールおよび展開パッケージに、BizTalk 管理コンピューターとパスを入力してください。</span><span class="sxs-lookup"><span data-stu-id="03786-109">In the release task, you can install the BizTalk application, and enter the BizTalk management computer, and the path to the deployment package</span></span>

<span data-ttu-id="03786-110">Visual Studio Team Services を使用して、自動的に展開できます[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]別の BizTalk 環境にアプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="03786-110">Using Visual Studio Team Services, you can automatically deploy [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] applications to different BizTalk environments.</span></span> 

<span data-ttu-id="03786-111">通常は 2 つのロールです。</span><span class="sxs-lookup"><span data-stu-id="03786-111">Typically, there are two roles involved:</span></span>

- <span data-ttu-id="03786-112">BizTalk 開発者は、アプリケーションを作成し、それをローカルでビルドします。</span><span class="sxs-lookup"><span data-stu-id="03786-112">BizTalk developer creates the application, and builds it locally.</span></span> <span data-ttu-id="03786-113">次に、アプリケーションを Git または Team Foundation バージョン管理を確認します。</span><span class="sxs-lookup"><span data-stu-id="03786-113">Then, checks the application into Git or Team Foundation Version Control.</span></span>
- <span data-ttu-id="03786-114">VSTS 管理者は、ビルドとリリースの定義を作成し、(Dev、UAT、実稼働) の別の環境に BizTalk アプリケーションに展開します。</span><span class="sxs-lookup"><span data-stu-id="03786-114">VSTS admin creates the build and release definitions, and deploys to the BizTalk application to different environments (Dev, UAT, Production).</span></span>

<span data-ttu-id="03786-115">VSTS を初めて使用する場合は、このチュートリアルが困難な可能性があります。</span><span class="sxs-lookup"><span data-stu-id="03786-115">If you’ve never used VSTS, this walkthrough may be challenging.</span></span> <span data-ttu-id="03786-116">Git、クローン作成、変更のプッシュなどに関する一定の知識は必要です。</span><span class="sxs-lookup"><span data-stu-id="03786-116">It does require some understanding of git, including cloning, and pushing changes.</span></span> 

<span data-ttu-id="03786-117">VSTS をセットアップする方法を説明[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]を展開する、最初のアプリケーションを追加します。</span><span class="sxs-lookup"><span data-stu-id="03786-117">We show you how to setup VSTS with [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)], and add your first application to deploy.</span></span> <span data-ttu-id="03786-118">参照することをお勧め、 [VSTS ガイダンス](https://docs.microsoft.com/vsts/user-guide/)、VSTS UI が変更されました。</span><span class="sxs-lookup"><span data-stu-id="03786-118">We recommend you refer to the [VSTS guidance](https://docs.microsoft.com/vsts/user-guide/), as the VSTS UI changes.</span></span> 

## <a name="before-you-begin"></a><span data-ttu-id="03786-119">アンインストールの準備</span><span class="sxs-lookup"><span data-stu-id="03786-119">Before you begin</span></span>

* <span data-ttu-id="03786-120">準備ができて、Visual Studio Team Services (VSTS) アカウントがあります。</span><span class="sxs-lookup"><span data-stu-id="03786-120">Have your Visual Studio Team Services (VSTS) account ready.</span></span> <span data-ttu-id="03786-121">1 つを持っていない場合</span><span class="sxs-lookup"><span data-stu-id="03786-121">Don't have one?</span></span> <span data-ttu-id="03786-122">[Visual Studio Team Services にサインアップする](https://www.visualstudio.com/docs/setup-admin/team-services/sign-up-for-visual-studio-team-services)です。</span><span class="sxs-lookup"><span data-stu-id="03786-122">[Sign up for Visual Studio Team Services](https://www.visualstudio.com/docs/setup-admin/team-services/sign-up-for-visual-studio-team-services).</span></span>
* <span data-ttu-id="03786-123">BizTalk コンピューターにインストールされている VSTS エージェントがある場合、既存のエージェントは、最新のエージェントが VSTS で上書きされます。</span><span class="sxs-lookup"><span data-stu-id="03786-123">If you already have a VSTS Agent installed on your BizTalk computer, then the existing agent is overwritten with the latest VSTS Agent.</span></span> <span data-ttu-id="03786-124">更新する必要があります、[新しいエージェントに合うように VSTS サービス](https://www.visualstudio.com/docs/build/actions/agents/v2-windows#replace-an-agent)です。</span><span class="sxs-lookup"><span data-stu-id="03786-124">You may have to update your [VSTS service to align with the new agent](https://www.visualstudio.com/docs/build/actions/agents/v2-windows#replace-an-agent).</span></span>
* <span data-ttu-id="03786-125">機能パック 1 では、VSTS で自動展開がいずれかで行われる[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]グループにします。</span><span class="sxs-lookup"><span data-stu-id="03786-125">With Feature Pack 1, automatic deployment with VSTS is done on one [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] in the group.</span></span> <span data-ttu-id="03786-126">コンピューターに Visual Studio があることを確認して、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]開発ツールおよび SDK をインストールします。</span><span class="sxs-lookup"><span data-stu-id="03786-126">Be sure the computer has Visual Studio and the [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] Developer Tools and SDK installed.</span></span> <span data-ttu-id="03786-127">参照してください、 [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] [ハードウェアおよびソフトウェア要件](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md)です。</span><span class="sxs-lookup"><span data-stu-id="03786-127">See the [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] [hardware and software requirements](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md).</span></span>
* <span data-ttu-id="03786-128">VSTS を自動配置の行われる Feature Pack 2 を使用して[展開グループ](https://docs.microsoft.com/vsts/build-release/concepts/definitions/release/deployment-groups/howto-deployment-groups)です。</span><span class="sxs-lookup"><span data-stu-id="03786-128">With Feature Pack 2, automatic deployment with VSTS can be done using [deployment groups](https://docs.microsoft.com/vsts/build-release/concepts/definitions/release/deployment-groups/howto-deployment-groups).</span></span> <span data-ttu-id="03786-129">展開グループを使用して、展開グループ内の複数の BizTalk サーバーにアプリケーションを展開できます。</span><span class="sxs-lookup"><span data-stu-id="03786-129">Using deployment groups, you can deploy your applications to multiple BizTalk Servers within the deployment group.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="03786-130">前提条件</span><span class="sxs-lookup"><span data-stu-id="03786-130">Prerequisites</span></span>

* <span data-ttu-id="03786-131">インストール[Feature Pack 2](https://aka.ms/bts2016fp2)で、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="03786-131">Install [Feature Pack 2](https://aka.ms/bts2016fp2) on your [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]</span></span>
* <span data-ttu-id="03786-132">一部のエクスペリエンスと知識 VSTS 内の定義の作成と操作をします。</span><span class="sxs-lookup"><span data-stu-id="03786-132">Some experience and knowledge with creating and working with definitions in VSTS.</span></span> <span data-ttu-id="03786-133">VSTS をまったく新しい場合は、これら優れたリソースがあります。</span><span class="sxs-lookup"><span data-stu-id="03786-133">If you're brand new to VSTS, these may be good resources:</span></span> 

  [<span data-ttu-id="03786-134">Visual Studio Team Services の概要</span><span class="sxs-lookup"><span data-stu-id="03786-134">Visual Studio Team Services overview</span></span>](https://www.visualstudio.com/docs/overview)  
  [<span data-ttu-id="03786-135">初心者の CI/CD</span><span class="sxs-lookup"><span data-stu-id="03786-135">CI/CD for newbies</span></span>](https://www.visualstudio.com/docs/build/get-started/ci-cd-part-1)

## <a name="get-started"></a><span data-ttu-id="03786-136">概要します。</span><span class="sxs-lookup"><span data-stu-id="03786-136">Get started</span></span>
[<span data-ttu-id="03786-137">手順 1: アプリケーション プロジェクトの追加および.json テンプレートの更新</span><span class="sxs-lookup"><span data-stu-id="03786-137">Step 1: Add Application project & update .json template</span></span>](feature-pack-add-application-project.md)  

[<span data-ttu-id="03786-138">手順 2: VSTS トークンの作成およびビルド エージェントのインストール</span><span class="sxs-lookup"><span data-stu-id="03786-138">Step 2: Create the VSTS token & install the build agent</span></span>](feature-pack-create-vsts-token.md)

[<span data-ttu-id="03786-139">手順 3: ビルドの作成し、定義のリリース</span><span class="sxs-lookup"><span data-stu-id="03786-139">Step 3: Create the build and release definitions</span></span>](feature-pack-add-build-release-definitions.md)

[<span data-ttu-id="03786-140">環境のトークンと変数を構成します。</span><span class="sxs-lookup"><span data-stu-id="03786-140">Configure environmental tokens and variables</span></span>](configure-environmental-tokens-and-variables-for-automatic-deployment.md)