---
title: Visual Studio Team Services での自動展開の構成 |Microsoft Docs
description: VSTS とアプリケーション ライフ サイクル管理を使用して、さまざまな BizTalk 環境にアプリケーションをデプロイする BizTalk Feature Pack のインストールします。
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
ms.openlocfilehash: 99d321e4f5987fe642b8a2dd4babc2c67093aad9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65356444"
---
# <a name="configure-automatic-deployment-with-visual-studio-team-services-in-biztalk-server"></a><span data-ttu-id="b0abf-103">BizTalk Server での Visual Studio Team Services での自動展開を構成します。</span><span class="sxs-lookup"><span data-stu-id="b0abf-103">Configure automatic deployment with Visual Studio Team Services in BizTalk Server</span></span>

## <a name="overview"></a><span data-ttu-id="b0abf-104">概要</span><span class="sxs-lookup"><span data-stu-id="b0abf-104">Overview</span></span>

<span data-ttu-id="b0abf-105">**以降で[!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]** 、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]強化された自動展開とアプリケーション ライフ サイクル管理 (ALM) のエクスペリエンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="b0abf-105">**Starting with [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]**, [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] provides an improved automatic deployment and application lifecycle management (ALM) experience.</span></span> 

<span data-ttu-id="b0abf-106">**以降で[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]Feature Pack 2**、この機能が強化されました。</span><span class="sxs-lookup"><span data-stu-id="b0abf-106">**Starting with [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] Feature Pack 2**, we've improved this feature:</span></span>

* <span data-ttu-id="b0abf-107">Visual Studio で、設定、**アプリケーション名**BizTalk アプリケーションの</span><span class="sxs-lookup"><span data-stu-id="b0abf-107">Within Visual Studio, set the **Application Name** of your BizTalk application</span></span>
* <span data-ttu-id="b0abf-108">エージェント ベースの展開だけでなく、使用することも[配置グループ](https://docs.microsoft.com/vsts/build-release/concepts/definitions/release/deployment-groups/index)複数のサーバーに BizTalk アプリケーションをデプロイするには</span><span class="sxs-lookup"><span data-stu-id="b0abf-108">In addition to using an agent-based deployment, you can also use [deployment groups](https://docs.microsoft.com/vsts/build-release/concepts/definitions/release/deployment-groups/index) to deploy your BizTalk applications to multiple servers</span></span>
* <span data-ttu-id="b0abf-109">リリース タスクで、BizTalk アプリケーションをインストールおよび展開パッケージに、BizTalk 管理コンピューターと、パスを入力します。</span><span class="sxs-lookup"><span data-stu-id="b0abf-109">In the release task, you can install the BizTalk application, and enter the BizTalk management computer, and the path to the deployment package</span></span>

<span data-ttu-id="b0abf-110">Visual Studio Team Services を使用して、自動的に展開できます[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]さまざまな BizTalk 環境へのアプリケーション。</span><span class="sxs-lookup"><span data-stu-id="b0abf-110">Using Visual Studio Team Services, you can automatically deploy [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] applications to different BizTalk environments.</span></span> 

<span data-ttu-id="b0abf-111">通常、ある 2 つのロール関連します。</span><span class="sxs-lookup"><span data-stu-id="b0abf-111">Typically, there are two roles involved:</span></span>

- <span data-ttu-id="b0abf-112">BizTalk 開発者は、アプリケーションを作成し、ローカルで構築します。</span><span class="sxs-lookup"><span data-stu-id="b0abf-112">BizTalk developer creates the application, and builds it locally.</span></span> <span data-ttu-id="b0abf-113">次に、Git または Team Foundation バージョン管理にアプリケーションを確認します。</span><span class="sxs-lookup"><span data-stu-id="b0abf-113">Then, checks the application into Git or Team Foundation Version Control.</span></span>
- <span data-ttu-id="b0abf-114">VSTS 管理者は、ビルドとリリースの定義を作成し、さまざまな環境 (開発、UAT、運用環境) への BizTalk アプリケーションをデプロイします。</span><span class="sxs-lookup"><span data-stu-id="b0abf-114">VSTS admin creates the build and release definitions, and deploys to the BizTalk application to different environments (Dev, UAT, Production).</span></span>

<span data-ttu-id="b0abf-115">VSTS を初めて使用する、このチュートリアルが困難な可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b0abf-115">If you’ve never used VSTS, this walkthrough may be challenging.</span></span> <span data-ttu-id="b0abf-116">Git、クローン作成、変更のプッシュなどのいくつかの理解は必要です。</span><span class="sxs-lookup"><span data-stu-id="b0abf-116">It does require some understanding of git, including cloning, and pushing changes.</span></span> 

<span data-ttu-id="b0abf-117">使用した VSTS をセットアップする方法を紹介[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]、展開する最初のアプリケーションを追加します。</span><span class="sxs-lookup"><span data-stu-id="b0abf-117">We show you how to setup VSTS with [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)], and add your first application to deploy.</span></span> <span data-ttu-id="b0abf-118">参照することをお勧め、 [VSTS ガイダンス](https://docs.microsoft.com/vsts/user-guide/)VSTS UI を変更すると、します。</span><span class="sxs-lookup"><span data-stu-id="b0abf-118">We recommend you refer to the [VSTS guidance](https://docs.microsoft.com/vsts/user-guide/), as the VSTS UI changes.</span></span> 

## <a name="before-you-begin"></a><span data-ttu-id="b0abf-119">アンインストールの準備</span><span class="sxs-lookup"><span data-stu-id="b0abf-119">Before you begin</span></span>

* <span data-ttu-id="b0abf-120">準備ができて、Visual Studio Team Services (VSTS) アカウントがあります。</span><span class="sxs-lookup"><span data-stu-id="b0abf-120">Have your Visual Studio Team Services (VSTS) account ready.</span></span> <span data-ttu-id="b0abf-121">ないでしょうか。</span><span class="sxs-lookup"><span data-stu-id="b0abf-121">Don't have one?</span></span> <span data-ttu-id="b0abf-122">[Visual Studio Team Services にサインアップ](https://www.visualstudio.com/docs/setup-admin/team-services/sign-up-for-visual-studio-team-services)します。</span><span class="sxs-lookup"><span data-stu-id="b0abf-122">[Sign up for Visual Studio Team Services](https://www.visualstudio.com/docs/setup-admin/team-services/sign-up-for-visual-studio-team-services).</span></span>
* <span data-ttu-id="b0abf-123">BizTalk コンピューターにインストールされている VSTS エージェント既にある場合、既存のエージェントは、VSTS の最新のエージェントで上書きされます。</span><span class="sxs-lookup"><span data-stu-id="b0abf-123">If you already have a VSTS Agent installed on your BizTalk computer, then the existing agent is overwritten with the latest VSTS Agent.</span></span> <span data-ttu-id="b0abf-124">更新する必要があります、[新しいエージェントの連携を VSTS サービス](https://www.visualstudio.com/docs/build/actions/agents/v2-windows#replace-an-agent)します。</span><span class="sxs-lookup"><span data-stu-id="b0abf-124">You may have to update your [VSTS service to align with the new agent](https://www.visualstudio.com/docs/build/actions/agents/v2-windows#replace-an-agent).</span></span>
* <span data-ttu-id="b0abf-125">1 つで VSTS を使用した自動展開を行う機能パック 1、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]グループ。</span><span class="sxs-lookup"><span data-stu-id="b0abf-125">With Feature Pack 1, automatic deployment with VSTS is done on one [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] in the group.</span></span> <span data-ttu-id="b0abf-126">コンピューターに Visual Studio があることを確認して、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]開発者用ツールと SDK をインストールします。</span><span class="sxs-lookup"><span data-stu-id="b0abf-126">Be sure the computer has Visual Studio and the [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] Developer Tools and SDK installed.</span></span> <span data-ttu-id="b0abf-127">参照してください、 [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] [ハードウェアおよびソフトウェア要件](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md)します。</span><span class="sxs-lookup"><span data-stu-id="b0abf-127">See the [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] [hardware and software requirements](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md).</span></span>
* <span data-ttu-id="b0abf-128">Feature Pack 2 と VSTS を使用した自動展開の実行に使用できますを使用して[配置グループ](https://docs.microsoft.com/vsts/build-release/concepts/definitions/release/deployment-groups/howto-deployment-groups)します。</span><span class="sxs-lookup"><span data-stu-id="b0abf-128">With Feature Pack 2, automatic deployment with VSTS can be done using [deployment groups](https://docs.microsoft.com/vsts/build-release/concepts/definitions/release/deployment-groups/howto-deployment-groups).</span></span> <span data-ttu-id="b0abf-129">配置グループを使用して、配置グループ内の複数の BizTalk Server アプリケーションをデプロイできます。</span><span class="sxs-lookup"><span data-stu-id="b0abf-129">Using deployment groups, you can deploy your applications to multiple BizTalk Servers within the deployment group.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b0abf-130">前提条件</span><span class="sxs-lookup"><span data-stu-id="b0abf-130">Prerequisites</span></span>

* <span data-ttu-id="b0abf-131">インストール[Feature Pack 2](https://aka.ms/bts2016fp2)で、 [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b0abf-131">Install [Feature Pack 2](https://aka.ms/bts2016fp2) on your [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]</span></span>
* <span data-ttu-id="b0abf-132">一部のエクスペリエンスと VSTS での定義の作成と操作の情報が提供します。</span><span class="sxs-lookup"><span data-stu-id="b0abf-132">Some experience and knowledge with creating and working with definitions in VSTS.</span></span> <span data-ttu-id="b0abf-133">VSTS にまったく新しい場合は、これらの優れたリソースがあります。</span><span class="sxs-lookup"><span data-stu-id="b0abf-133">If you're brand new to VSTS, these may be good resources:</span></span> 

  [<span data-ttu-id="b0abf-134">Visual Studio Team Services の概要</span><span class="sxs-lookup"><span data-stu-id="b0abf-134">Visual Studio Team Services overview</span></span>](https://www.visualstudio.com/docs/overview)  
  [<span data-ttu-id="b0abf-135">初心者の CI/CD</span><span class="sxs-lookup"><span data-stu-id="b0abf-135">CI/CD for newbies</span></span>](https://www.visualstudio.com/docs/build/get-started/ci-cd-part-1)

## <a name="get-started"></a><span data-ttu-id="b0abf-136">作業開始</span><span class="sxs-lookup"><span data-stu-id="b0abf-136">Get started</span></span>
[<span data-ttu-id="b0abf-137">ステップ 1: アプリケーションのプロジェクトと更新プログラムの .json テンプレートを追加します。</span><span class="sxs-lookup"><span data-stu-id="b0abf-137">Step 1: Add Application project & update .json template</span></span>](feature-pack-add-application-project.md)  

[<span data-ttu-id="b0abf-138">手順 2:VSTS トークンの作成し、ビルド エージェントのインストール</span><span class="sxs-lookup"><span data-stu-id="b0abf-138">Step 2: Create the VSTS token & install the build agent</span></span>](feature-pack-create-vsts-token.md)

[<span data-ttu-id="b0abf-139">ステップ 3:ビルドとリリース定義を作成します。</span><span class="sxs-lookup"><span data-stu-id="b0abf-139">Step 3: Create the build and release definitions</span></span>](feature-pack-add-build-release-definitions.md)

[<span data-ttu-id="b0abf-140">環境トークンと変数を構成します。</span><span class="sxs-lookup"><span data-stu-id="b0abf-140">Configure environmental tokens and variables</span></span>](configure-environmental-tokens-and-variables-for-automatic-deployment.md)