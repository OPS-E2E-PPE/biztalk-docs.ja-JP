---
redirect_url: /biztalk/core/feature-pack-add-build-release-definitions/
redirect_document_id: true
ROBOTS: NOINDEX
title: BizTalk Server ソリューションまたはプロジェクトをデプロイする、Visual Studio Team Services の構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2555712a-dfe4-420e-9a61-1d1a6d98c322
caps.latest.revision: 6
author: tordgladnordahl
ms.author: tonordah
manager: anneta
ms.openlocfilehash: 8b13ef6f56e892bb3598096272d876c5f0a865f3
ms.sourcegitcommit: be6273d612669adfbb9dc9208aaae0a8437d4017
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/04/2018
ms.locfileid: "52826306"
---
# <a name="configure-visual-studio-team-services-to-deploy-biztalk-server-solutions-or-projects"></a><span data-ttu-id="7e402-102">BizTalk Server ソリューションまたはプロジェクトをデプロイする、Visual Studio Team Services の構成します。</span><span class="sxs-lookup"><span data-stu-id="7e402-102">Configure Visual Studio Team Services to deploy BizTalk Server solutions or projects</span></span>
<span data-ttu-id="7e402-103">自動的に展開する VSTS セットアップ[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]プロジェクト。</span><span class="sxs-lookup"><span data-stu-id="7e402-103">Set up VSTS to automatically deploy [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] projects.</span></span> 

<span data-ttu-id="7e402-104">**以降で[!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]** 、自動的にビルドすることができます、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]ソリューションが Visual Studio Team Services (VSTS) を使用します。</span><span class="sxs-lookup"><span data-stu-id="7e402-104">**Starting with [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]**, you can automatically build your [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] solutions using Visual Studio Team Services (VSTS).</span></span> 

<span data-ttu-id="7e402-105">このトピックを設定して、BizTalk の自動展開を使用する Visual Studio Team Service (VSTS) を構成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="7e402-105">This topic shows you how to set up and configure Visual Studio Team Service (VSTS) to use automatic deployment for BizTalk.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="7e402-106">VSTS エージェントは、1 つにのみインストールできます[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]グループ。</span><span class="sxs-lookup"><span data-stu-id="7e402-106">The VSTS agent can only be installed on one [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] in the group.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="7e402-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="7e402-107">Prerequisites</span></span>

* <span data-ttu-id="7e402-108">インストール[Feature Pack 1](https://www.microsoft.com/download/details.aspx?id=55100)で、 [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7e402-108">Install [Feature Pack 1](https://www.microsoft.com/download/details.aspx?id=55100) on your [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]</span></span>
* <span data-ttu-id="7e402-109">一部のエクスペリエンスと VSTS での定義の作成と操作の情報が提供します。</span><span class="sxs-lookup"><span data-stu-id="7e402-109">Some experience and knowledge with creating and working with definitions in VSTS.</span></span> <span data-ttu-id="7e402-110">VSTS にまったく新しい場合は、これらの優れたリソースがあります。</span><span class="sxs-lookup"><span data-stu-id="7e402-110">If you're brand new to VSTS, these may be good resources:</span></span> 

  [<span data-ttu-id="7e402-111">Visual Studio Team Services の概要</span><span class="sxs-lookup"><span data-stu-id="7e402-111">Visual Studio Team Services overview</span></span>](https://www.visualstudio.com/docs/overview)  
  [<span data-ttu-id="7e402-112">初心者の CI/CD</span><span class="sxs-lookup"><span data-stu-id="7e402-112">CI/CD for newbies</span></span>](https://www.visualstudio.com/docs/build/get-started/ci-cd-part-1)
  

## <a name="create-a-vsts-account-and-create-a-definition"></a><span data-ttu-id="7e402-113">VSTS アカウントを作成し、定義を作成します。</span><span class="sxs-lookup"><span data-stu-id="7e402-113">Create a VSTS account and create a definition</span></span>

1. <span data-ttu-id="7e402-114">Web ブラウザーでに移動、 [Visual Studio online プロファイル](https://app.vsaex.visualstudio.com/go/profile)、サインイン、および選択を**新しいアカウントを作成する**:</span><span class="sxs-lookup"><span data-stu-id="7e402-114">In a web browser, go to your [Visual Studio online profile](https://app.vsaex.visualstudio.com/go/profile), sign in, and select a **Create new account**:</span></span>

    ![[新しいアカウントを作成する]](../core/media/create-a-new-account.png)

2. <span data-ttu-id="7e402-116">アカウントの名前を入力、優先されるソース コード リポジトリを選択および選択**続行**:</span><span class="sxs-lookup"><span data-stu-id="7e402-116">Enter a name for the account, select your preferred source code repository, and select **Continue**:</span></span>

    ![新しいプロジェクトを作成する](../core/media/create-a-new-project.png)

3. <span data-ttu-id="7e402-118">新しいアカウントを作成し、サイトのような`https://YourAccountName.visualstudio.com/MyFirstProject`が開きます。</span><span class="sxs-lookup"><span data-stu-id="7e402-118">Your new account is created, and a site similar to `https://YourAccountName.visualstudio.com/MyFirstProject` opens.</span></span>
    
4. <span data-ttu-id="7e402-119">インストール、 [BizTalk アプリケーションのデプロイ サービス](https://marketplace.visualstudio.com/items?itemName=ms-biztalk.deploy-biztalk-application)作成したアカウントにします。</span><span class="sxs-lookup"><span data-stu-id="7e402-119">Install the [Deploy BizTalk Application service](https://marketplace.visualstudio.com/items?itemName=ms-biztalk.deploy-biztalk-application) to the account you just created.</span></span>

    ![新しいリリースをビルドします。](../core/media/build-new-release.png)

5. <span data-ttu-id="7e402-121">いくつかのメッセージを取得する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7e402-121">You may get some prompts.</span></span> <span data-ttu-id="7e402-122">続行することを確認します。</span><span class="sxs-lookup"><span data-stu-id="7e402-122">Confirm to continue.</span></span> <span data-ttu-id="7e402-123">VSTS でプロジェクトにサインインしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="7e402-123">Be sure you're signed in to your project in VSTS.</span></span>

6. <span data-ttu-id="7e402-124">選択**ビルドとリリース**、作成し、**新規**ビルド定義。</span><span class="sxs-lookup"><span data-stu-id="7e402-124">Select **Build and release**, and create a **New** build definition:</span></span>

    ![ビルドとリリースを選択します。](../core/media/select-build-and-release.png)

    > [!TIP]
    > <span data-ttu-id="7e402-126">あなたは仕事を必ず`https://YourAccountName.visualstudio.com/MyFirstProject`します。</span><span class="sxs-lookup"><span data-stu-id="7e402-126">Be sure you're at `https://YourAccountName.visualstudio.com/MyFirstProject`.</span></span> <span data-ttu-id="7e402-127">それ以外の場合、**新規**または**新しい定義**ボタンが不要であります。</span><span class="sxs-lookup"><span data-stu-id="7e402-127">Otherwise, the **New** or **New definition** buttons may not be there.</span></span> 
    
7. <span data-ttu-id="7e402-128">選択、 **Visual Studio**テンプレート、および選択**次**:</span><span class="sxs-lookup"><span data-stu-id="7e402-128">Select the **Visual Studio** template, and select **Next**:</span></span>

    ![Visual studio を選択し、[次へ] をクリックしてください](../core/media/select-visual-studio-and-click-next.png)

8. <span data-ttu-id="7e402-130">設定を確認し、選択**作成**です。</span><span class="sxs-lookup"><span data-stu-id="7e402-130">Review your settings, and select **Create**.</span></span>

9. <span data-ttu-id="7e402-131">不要な手順を削除します。</span><span class="sxs-lookup"><span data-stu-id="7e402-131">Delete the steps you don't need.</span></span> <span data-ttu-id="7e402-132">このチュートリアルでは、次のように削除できます。</span><span class="sxs-lookup"><span data-stu-id="7e402-132">For this tutorial, you can delete the following:</span></span> 
10. <span data-ttu-id="7e402-133">NuGet の復元</span><span class="sxs-lookup"><span data-stu-id="7e402-133">NuGet Restore</span></span>
11. <span data-ttu-id="7e402-134">テスト アセンブリ</span><span class="sxs-lookup"><span data-stu-id="7e402-134">Test assemblies</span></span>
12. <span data-ttu-id="7e402-135">シンボル パスを発行します。</span><span class="sxs-lookup"><span data-stu-id="7e402-135">Publish symbols path</span></span> 

      ![削除の手順は必要ありません。](../core/media/delete-steps-not-needed.png)

13. <span data-ttu-id="7e402-137">**省略可能な**します。</span><span class="sxs-lookup"><span data-stu-id="7e402-137">**Optional**.</span></span> <span data-ttu-id="7e402-138">継続的インテグレーション (CI) を有効にする場合は、選択**トリガー**チェックし、メニューで**継続的インテグレーション (CI)** します。</span><span class="sxs-lookup"><span data-stu-id="7e402-138">If you want to enable Continuous Integration (CI), select **Triggers** in the menu, and check **Continuous integration (CI)**.</span></span>

<span data-ttu-id="7e402-139">次に、エージェントをインストール、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="7e402-139">Next, install the agent on your [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)].</span></span> 

## <a name="install-the-agent"></a><span data-ttu-id="7e402-140">エージェントをインストールします。</span><span class="sxs-lookup"><span data-stu-id="7e402-140">Install the Agent</span></span>

<span data-ttu-id="7e402-141">ソリューションが機能するには、ローカル コンピューターにプライベートの Windows エージェントを有効にします。</span><span class="sxs-lookup"><span data-stu-id="7e402-141">For the solution to work, enable a private Windows Agent on your local machine.</span></span> <span data-ttu-id="7e402-142">忘れないでください**1 つのみで、エージェントをインストールする必要があります[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]グループ**します。</span><span class="sxs-lookup"><span data-stu-id="7e402-142">Remember, **the agent must be installed on only one [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] in the group**.</span></span> 

1. <span data-ttu-id="7e402-143">定義に、選択、**全般**(上部) にあるタブ。</span><span class="sxs-lookup"><span data-stu-id="7e402-143">In your definition, select the **General** tab (at the top).</span></span>
2. <span data-ttu-id="7e402-144">**既定のエージェント キュー**プロパティを選択、**既定**一覧からエージェント。</span><span class="sxs-lookup"><span data-stu-id="7e402-144">For the **Default agent queue** property, select the **Default** agent from the list.</span></span> 
3. <span data-ttu-id="7e402-145">選択**管理**横に、**既定のエージェント キュー**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="7e402-145">Select **Manage** next to the **Default agent queue** property.</span></span> <span data-ttu-id="7e402-146">新しいブラウザー タブが開きます。</span><span class="sxs-lookup"><span data-stu-id="7e402-146">A new browser tab opens.</span></span>

    ![新しい管理エージェントを作成します。](../core/media/create-new-management-agent.png)

4. <span data-ttu-id="7e402-148">左側のウィンドウで、既定のキューが選択されます。</span><span class="sxs-lookup"><span data-stu-id="7e402-148">In the left pane, the Default queue is selected.</span></span> <span data-ttu-id="7e402-149">完了したら、オンラインで、エージェントが既に表示されている場合。</span><span class="sxs-lookup"><span data-stu-id="7e402-149">If an agent is already listed, and online, then you're done.</span></span> <span data-ttu-id="7e402-150">エージェントをインストールし、実行があります。</span><span class="sxs-lookup"><span data-stu-id="7e402-150">You have an agent installed, and running.</span></span> 

    <span data-ttu-id="7e402-151">エージェントが表示されない場合は選択し、**エージェントのダウンロード**のインストールを続行し、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="7e402-151">If an agent is not listed, then select **Download agent**, and continue with the installation on your [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="7e402-152">**移動して[Windows エージェントを展開](https://www.visualstudio.com/docs/build/actions/agents/v2-windows)完全な手順について**エージェントをインストールして、エージェントを開始します。</span><span class="sxs-lookup"><span data-stu-id="7e402-152">**Go to [Deploy an agent on Windows](https://www.visualstudio.com/docs/build/actions/agents/v2-windows) for the complete steps** to install the agent, and start an agent.</span></span> 

    > [!IMPORTANT]
    > <span data-ttu-id="7e402-153">すべての手順に従う[Windows エージェントを展開](https://www.visualstudio.com/docs/build/actions/agents/v2-windows)します。</span><span class="sxs-lookup"><span data-stu-id="7e402-153">Follow all the steps at [Deploy an agent on Windows](https://www.visualstudio.com/docs/build/actions/agents/v2-windows).</span></span> <span data-ttu-id="7e402-154">この手順は省略しないでください。</span><span class="sxs-lookup"><span data-stu-id="7e402-154">Do not skip this step.</span></span> 

5. <span data-ttu-id="7e402-155">既定のエージェントで**オンライン**に戻り、**全般**定義に、タブを確認します**既定**が選択されている、 **既定のエージェントキュー**.</span><span class="sxs-lookup"><span data-stu-id="7e402-155">With the default agent **Online**, go back to the **General** tab in your definition, and confirm **Default** is selected for the **Default agent queue**.</span></span>
6. <span data-ttu-id="7e402-156">**保存**と**新しいビルドをキュー**します。</span><span class="sxs-lookup"><span data-stu-id="7e402-156">**Save** and **Queue new build**.</span></span>

<span data-ttu-id="7e402-157">次に、BizTalk Server アプリケーションの展開の定義を作成します。</span><span class="sxs-lookup"><span data-stu-id="7e402-157">Next, create the BizTalk Server Application Deployment definition.</span></span>

## <a name="create-the-biztalk-deployment-definition"></a><span data-ttu-id="7e402-158">BizTalk 展開の定義を作成します。</span><span class="sxs-lookup"><span data-stu-id="7e402-158">Create the BizTalk deployment definition</span></span>

1. <span data-ttu-id="7e402-159">選択、**ビルド**] タブで [**すべて定義**、選択と**新規**:</span><span class="sxs-lookup"><span data-stu-id="7e402-159">Select the **Builds** tab, select **All Definitions**, and select **New**:</span></span>

    ![新しいリリース定義を作成します。](../core/media/create-new-release-definition.png)

2. <span data-ttu-id="7e402-161">選択、**空**テンプレート、および選択**次**:</span><span class="sxs-lookup"><span data-stu-id="7e402-161">Select the **Empty** template, and select **Next**:</span></span>

    ![空のテンプレートから新しい定義を作成します。](../core/media/create-new-definition-from-an-empty-template.png)

3. <span data-ttu-id="7e402-163">選択、**リポジトリ**ソースと**ブランチ**定義については、します。</span><span class="sxs-lookup"><span data-stu-id="7e402-163">Select your **Repository** source and **Branch** for the definition.</span></span>
4. <span data-ttu-id="7e402-164">**省略可能な**します。</span><span class="sxs-lookup"><span data-stu-id="7e402-164">**Optional**.</span></span> <span data-ttu-id="7e402-165">選択**継続的インテグレーション**します。</span><span class="sxs-lookup"><span data-stu-id="7e402-165">Select **Continuous Integration**.</span></span>
5. <span data-ttu-id="7e402-166">選択、**既定**エージェントを選択し、キューの一覧から**作成**です。</span><span class="sxs-lookup"><span data-stu-id="7e402-166">Select the **Default** agent from the queue list, and select **Create**.</span></span>
6. <span data-ttu-id="7e402-167">**ビルド ステップの追加**を選択、 **BizTalk Server アプリケーションの展開**タスク、および選択**追加**します。</span><span class="sxs-lookup"><span data-stu-id="7e402-167">**Add build step**, select the **BizTalk Server Application Deployment** task, and select **Add**.</span></span> <span data-ttu-id="7e402-168">**閉じる**タスク カタログ。</span><span class="sxs-lookup"><span data-stu-id="7e402-168">**Close** the task catalog.</span></span>

    ![追加する新しい定義の展開](../core/media/add-new-deploy-definition.png)

7. <span data-ttu-id="7e402-170">選択、**操作名**を使用します。</span><span class="sxs-lookup"><span data-stu-id="7e402-170">Select the **Operation Name** you want to use:</span></span>

    * <span data-ttu-id="7e402-171">**新しい BizTalk アプリケーションを作成する**新しいアプリケーションをデプロイします。</span><span class="sxs-lookup"><span data-stu-id="7e402-171">**Create new BizTalk Application** deploys a new application.</span></span> <span data-ttu-id="7e402-172">アプリケーションが既に存在する場合、現在のアプリケーション (完全停止) をアンインストールし、新しいアプリケーションをインストールします。</span><span class="sxs-lookup"><span data-stu-id="7e402-172">If the application already exist, it uninstalls the current applications (full stop), and installs the new application.</span></span> <span data-ttu-id="7e402-173">継続的インテグレーションを有効にするでは、リポジトリで更新されるときに、そのアプリケーションが自動的に再します。</span><span class="sxs-lookup"><span data-stu-id="7e402-173">If continous integration is enabled, it automatically redeploys the application when it is updated in the repository.</span></span>
    * <span data-ttu-id="7e402-174">**既存の BizTalk アプリケーションを更新**など、変更を追加します**スキーマ**を既に実行されているアプリケーションにします。</span><span class="sxs-lookup"><span data-stu-id="7e402-174">**Update an existing BizTalk Application** appends changes, such as **Schemas** to an already running application.</span></span> <span data-ttu-id="7e402-175">アプリケーションの完全な再デプロイは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="7e402-175">It does not require a full redeploy of the application.</span></span>

8. <span data-ttu-id="7e402-176">入力、**アプリケーション名**で、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]環境。</span><span class="sxs-lookup"><span data-stu-id="7e402-176">Enter the **Application name** in your [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] environment.</span></span>
9. <span data-ttu-id="7e402-177">**デプロイ パッケージのパス**リポジトリに zip ファイルへのパスを選択します。</span><span class="sxs-lookup"><span data-stu-id="7e402-177">In **Deployment package path**, select the path to the zip file in your repository.</span></span>
10. <span data-ttu-id="7e402-178">選択**トリガー**メニューから、有効にする**継続的インテグレーション**、正しい選択と**ブランチ**ビルドの。</span><span class="sxs-lookup"><span data-stu-id="7e402-178">Select **Triggers** from the menu, enable **Continuous Integration**, and select the correct **Branch** for the build.</span></span>
11. <span data-ttu-id="7e402-179">選択**保存**:</span><span class="sxs-lookup"><span data-stu-id="7e402-179">Select **Save**:</span></span>

    ![新しいビルド定義を保存します。](../core/media/save-the-new-build-definition.png)

12. <span data-ttu-id="7e402-181">新しい名前**定義**、し、正しいパスを設定します。</span><span class="sxs-lookup"><span data-stu-id="7e402-181">Name the new **Definition**, and set the correct path.</span></span> 
13. <span data-ttu-id="7e402-182">定義が保存されると、選択**新しいビルドをキュー**します。</span><span class="sxs-lookup"><span data-stu-id="7e402-182">Once the definition is saved, select **Queue the new build**.</span></span> <span data-ttu-id="7e402-183">次に、選択、**キュー エージェント**コミットにコメントを追加します。</span><span class="sxs-lookup"><span data-stu-id="7e402-183">Then, select the **Queue agent**, and add a comment to the commit.</span></span>
