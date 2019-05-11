---
title: 手順 3 - ビルドとリリース定義の作成 |Microsoft Docs
description: Vsts では、git または TFS リポジトリ内のプロジェクトをビルドし、BizTalk Server アプリケーションを配置するリリース定義を作成するビルド定義を作成します。
ms.custom: ''
ms.date: 11/20/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fd25c92b7b9abea02bb7366c9c4cc83e68dff3aa
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65345837"
---
# <a name="step-3-create-the-build-and-release-definition"></a><span data-ttu-id="ceed4-103">手順 3:ビルドとリリース定義を作成します。</span><span class="sxs-lookup"><span data-stu-id="ceed4-103">Step 3: Create the build and release definition</span></span>

<span data-ttu-id="ceed4-104">ビルドとリリース定義のタスクが Visual Studio Team Services とおそらく VSTS 管理者が行う必要があります。ビルド定義は、git リポジトリ内でプロジェクトをビルドおよびリリース定義は、BizTalk Server 環境にデプロイします。</span><span class="sxs-lookup"><span data-stu-id="ceed4-104">The build and release definitions are Visual Studio Team Services tasks, and should probably be done by a VSTS admin. The build definition builds your project within your git repository, and the release definitions deploys it to your BizTalk Server environment.</span></span> 

## <a name="before-you-begin"></a><span data-ttu-id="ceed4-105">アンインストールの準備</span><span class="sxs-lookup"><span data-stu-id="ceed4-105">Before you begin</span></span>
<span data-ttu-id="ceed4-106">完全な[手順 2 - 作成 VSTS トークンと、エージェントをインストール](feature-pack-create-vsts-token.md)します。</span><span class="sxs-lookup"><span data-stu-id="ceed4-106">Complete [Step 2 - Create VSTS token and install agent](feature-pack-create-vsts-token.md).</span></span>

## <a name="add-the-build-tasks"></a><span data-ttu-id="ceed4-107">ビルド タスクを追加します。</span><span class="sxs-lookup"><span data-stu-id="ceed4-107">Add the Build tasks</span></span>
1. <span data-ttu-id="ceed4-108">プロジェクトで、次のように選択します。**ビルドとリリース**します。</span><span class="sxs-lookup"><span data-stu-id="ceed4-108">In your project, select **Build and release**.</span></span> <span data-ttu-id="ceed4-109">[ビルド] タブを開きます。</span><span class="sxs-lookup"><span data-stu-id="ceed4-109">The Builds tab opens.</span></span> <span data-ttu-id="ceed4-110">作成、**新規**定義。</span><span class="sxs-lookup"><span data-stu-id="ceed4-110">Create a **New** definition:</span></span>

    ![新しいビルド定義](../core/media/vsts-new-definition.png)

2. <span data-ttu-id="ceed4-112">選択、**空**テンプレート、および選択**適用**:</span><span class="sxs-lookup"><span data-stu-id="ceed4-112">Select the **Empty** template, and select **Apply**:</span></span>  

    ![空のテンプレートを選択します。](../core/media/vsts-emtpy-template.png)
 
3. <span data-ttu-id="ceed4-114">設定、**エージェント キュー**既定値にします。</span><span class="sxs-lookup"><span data-stu-id="ceed4-114">Set the **Agent Queue** to Default:</span></span> 

    ![既定のキューを選択します。](../core/media/vsts-select-agent-queue.png)

4. <span data-ttu-id="ceed4-116">**フェーズ 1**、タスクを追加、選択**Visual Studio ビルド**、選び**追加**:</span><span class="sxs-lookup"><span data-stu-id="ceed4-116">In **Phase 1**, add a task, select **Visual Studio Build**, and select **Add**:</span></span>

    ![VS のビルド タスクを追加します。](../core/media/vsts-add-visual-studio-task.png)

5. <span data-ttu-id="ceed4-118">Visual Studio のビルド タスクだけに追加され、次のプロパティの設定をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ceed4-118">Click the Visual Studio Build task you just added, and set the following properties:</span></span>  

    | <span data-ttu-id="ceed4-119">プロパティ</span><span class="sxs-lookup"><span data-stu-id="ceed4-119">Property</span></span> | <span data-ttu-id="ceed4-120">を設定します。</span><span class="sxs-lookup"><span data-stu-id="ceed4-120">Set to</span></span> |
    | --- | --- | 
    | <span data-ttu-id="ceed4-121">表示名</span><span class="sxs-lookup"><span data-stu-id="ceed4-121">Display name</span></span> | <span data-ttu-id="ceed4-122">*YourProjectName*ソリューションをビルド \* \*\*.sln</span><span class="sxs-lookup"><span data-stu-id="ceed4-122">*YourProjectName* Build solution \*\*\*.sln</span></span> | 
    | <span data-ttu-id="ceed4-123">Visual Studio バージョン</span><span class="sxs-lookup"><span data-stu-id="ceed4-123">Visual Studio version</span></span> | <span data-ttu-id="ceed4-124">Visual Studio 2015</span><span class="sxs-lookup"><span data-stu-id="ceed4-124">Visual Studio 2015</span></span> | 
    | <span data-ttu-id="ceed4-125">MSBuild アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="ceed4-125">MSBuild Architecture</span></span> | <span data-ttu-id="ceed4-126">MSBuild x86</span><span class="sxs-lookup"><span data-stu-id="ceed4-126">MSBuild x86</span></span> | 

6. <span data-ttu-id="ceed4-127">**フェーズ 1**、タスクを追加、選択**ビルド成果物の発行**、選び**追加**:</span><span class="sxs-lookup"><span data-stu-id="ceed4-127">In **Phase 1**, add a task, select **Publish Build Artifacts**, and select **Add**:</span></span> 

    ![VS のビルド タスクを追加します。](../core/media/vsts-add-publish-build-task.png)

7. <span data-ttu-id="ceed4-129">選択、**成果物の発行**タスク、および、推奨される入力**表示名**します。</span><span class="sxs-lookup"><span data-stu-id="ceed4-129">Select the **Publish Artifact** task, and enter your preferred **Display name**.</span></span> <span data-ttu-id="ceed4-130">**を発行するパス**を選択、 **.** ボタンをクリックし、アプリケーションのプロジェクト フォルダー (例: appProjectHelloWorld) を選択します。</span><span class="sxs-lookup"><span data-stu-id="ceed4-130">For **Path to publish**, select the **...**  button, and choose the application project folder (e.g. appProjectHelloWorld).</span></span> <span data-ttu-id="ceed4-131">**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ceed4-131">Select **OK**.</span></span>

8. <span data-ttu-id="ceed4-132">**成果物名**必要なものにすることができます。</span><span class="sxs-lookup"><span data-stu-id="ceed4-132">The **Artifact Name** can be anything you want.</span></span> <span data-ttu-id="ceed4-133">選択**保存**します。</span><span class="sxs-lookup"><span data-stu-id="ceed4-133">Select **Save**.</span></span> 

9. <span data-ttu-id="ceed4-134">移動して**トリガー**、設定、**トリガーの状態**に**有効**:</span><span class="sxs-lookup"><span data-stu-id="ceed4-134">Go to **Triggers**, and set the **Trigger status** to **Enabled**:</span></span>  

    ![VS のビルド タスクを追加します。](../core/media/vsts-continuous-integration.png)

10. <span data-ttu-id="ceed4-136">**保存 (&) キュー**ビルド定義をテストします。</span><span class="sxs-lookup"><span data-stu-id="ceed4-136">**Save & Queue** to test your build definition.</span></span> <span data-ttu-id="ceed4-137">キューを配置するときに、エージェント キューと独自のブランチを求められます。</span><span class="sxs-lookup"><span data-stu-id="ceed4-137">When you queue, you are prompted for the agent queue and your branch.</span></span> <span data-ttu-id="ceed4-138">選択、**既定**エージェント キュー、および独自のブランチを選択します。</span><span class="sxs-lookup"><span data-stu-id="ceed4-138">Select the **Default** agent queue, and choose your branch.</span></span> <span data-ttu-id="ceed4-139">選択**キュー**します。</span><span class="sxs-lookup"><span data-stu-id="ceed4-139">Select **Queue**.</span></span>  

11. <span data-ttu-id="ceed4-140">新しいビルドが開始され、成功または失敗を確認することを選択することができます。</span><span class="sxs-lookup"><span data-stu-id="ceed4-140">A new build is started, and you can select it to check for a success or failure.</span></span> 

## <a name="add-the-release-tasks"></a><span data-ttu-id="ceed4-141">リリース タスクを追加します。</span><span class="sxs-lookup"><span data-stu-id="ceed4-141">Add the release tasks</span></span>

<span data-ttu-id="ceed4-142">ビルドが成功すると、リリース定義は、BizTalk Server にアプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="ceed4-142">When the build succeeds, the release definition deploys your application to your BizTalk Server.</span></span> 

1. <span data-ttu-id="ceed4-143">選択、**リリース**] タブで [**新しい定義**します。</span><span class="sxs-lookup"><span data-stu-id="ceed4-143">Select the **Releases** tab, select **New definition**.</span></span> 

2. <span data-ttu-id="ceed4-144">選択、**空**テンプレート、および選択**適用**:</span><span class="sxs-lookup"><span data-stu-id="ceed4-144">Select the **Empty** template, and select **Apply**:</span></span>

    ![空のテンプレートを追加します。](../core/media/vsts-empty-release-template.png)

3. <span data-ttu-id="ceed4-146">変更、**環境名**に**Dev**、または何でもを付けます。</span><span class="sxs-lookup"><span data-stu-id="ceed4-146">Change the **Environment name** to **Dev**, or whatever you want to call it.</span></span> 

4. <span data-ttu-id="ceed4-147">選択**成果物を追加**プロジェクト、ビルド定義を選択し、選択、**追加**:</span><span class="sxs-lookup"><span data-stu-id="ceed4-147">Select **Add artifact**, select your project, your build definition, and select **Add**:</span></span> 

5. <span data-ttu-id="ceed4-148">移動して、**タスク** タブで、新しいタスクを追加します。</span><span class="sxs-lookup"><span data-stu-id="ceed4-148">Go to the **Tasks** tab, add a new task:</span></span> 

    ![リリース タスクを追加します。](../core/media/vsts-new-release-tasks.png)

6. <span data-ttu-id="ceed4-150">一覧から、結果をフィルターで、選択、 **BizTalk Server アプリケーションの展開**タスク、および選択**追加**:</span><span class="sxs-lookup"><span data-stu-id="ceed4-150">From the list, filter the results, select the **BizTalk Server Application Deployment** task, and select **Add**:</span></span>  

    ![BizTalk 展開のタスクを追加します。](../core/media/vsts-biztalk-application-deployment-task.png)

    <span data-ttu-id="ceed4-152">場合**BizTalk Server アプリケーションの展開**ins't 一覧にインストールし[BizTalk アプリケーションのデプロイ](https://marketplace.visualstudio.com/items?itemName=ms-biztalk.deploy-biztalk-application)します。</span><span class="sxs-lookup"><span data-stu-id="ceed4-152">If **BizTalk Server Application Deployment** ins't listed, then install it at [Deploy BizTalk Application](https://marketplace.visualstudio.com/items?itemName=ms-biztalk.deploy-biztalk-application).</span></span>

7. <span data-ttu-id="ceed4-153">選択、**デプロイ**タスク、および値を入力します。</span><span class="sxs-lookup"><span data-stu-id="ceed4-153">Select the **Deploy** task, and enter the values:</span></span> 

    <span data-ttu-id="ceed4-154">**操作名**:オプションがあります。</span><span class="sxs-lookup"><span data-stu-id="ceed4-154">**Operation Name**: Your options:</span></span>   
        <span data-ttu-id="ceed4-155">- **新しい BizTalk アプリケーションを作成する**:新しいアプリケーションをデプロイします。</span><span class="sxs-lookup"><span data-stu-id="ceed4-155">- **Create new BizTalk Application**: Deploys a new application.</span></span> <span data-ttu-id="ceed4-156">アプリケーションが既に存在する場合に、現在のアプリケーション (完全停止) をアンインストールし、新しいアプリケーションをインストールします。</span><span class="sxs-lookup"><span data-stu-id="ceed4-156">If the application already exists, it uninstalls the current applications (full stop), and installs the new application.</span></span> <span data-ttu-id="ceed4-157">継続的インテグレーションを有効にするでは、リポジトリで更新されるときに、そのアプリケーションが自動的に再します。</span><span class="sxs-lookup"><span data-stu-id="ceed4-157">If continuous integration is enabled, it automatically redeploys the application when it is updated in the repository.</span></span>   
        <span data-ttu-id="ceed4-158">- **既存の BizTalk アプリケーションを更新**:既に実行中のアプリケーションには、スキーマなどの変更を追加します。</span><span class="sxs-lookup"><span data-stu-id="ceed4-158">- **Update an existing BizTalk Application**: Appends changes, such as schemas, to an already running application.</span></span> <span data-ttu-id="ceed4-159">アプリケーションの完全な再デプロイは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="ceed4-159">It does not require a full redeploy of the application.</span></span>  
        <span data-ttu-id="ceed4-160">- **BizTalk Server アプリケーションをインストールする**:[アプリケーションをインストールする](../core/how-to-install-a-biztalk-application.md)、BizTalk 管理のコンピューター名、および展開パッケージのパスを入力します。</span><span class="sxs-lookup"><span data-stu-id="ceed4-160">- **Install BizTalk Server Application**: [Install the applications](../core/how-to-install-a-biztalk-application.md), and you enter the BizTalk management computer name, and the deployment package path.</span></span>  

     ![デプロイ操作](../core/media/vsts-deploy-operations.png)

    <span data-ttu-id="ceed4-162">**アプリケーション名**:入力したテキストは、BizTalk 管理コンソールでアプリケーション名になります。</span><span class="sxs-lookup"><span data-stu-id="ceed4-162">**Application Name**: The text you enter will be the application name in BizTalk Administration.</span></span> <span data-ttu-id="ceed4-163">**いない**BizTalk アプリケーション 1 を入力します。</span><span class="sxs-lookup"><span data-stu-id="ceed4-163">Do **not** enter BizTalk Application 1.</span></span>

    <span data-ttu-id="ceed4-164">**展開パッケージ**:アプリケーション プロジェクトに zip ファイルを選択し、選択**OK**します。</span><span class="sxs-lookup"><span data-stu-id="ceed4-164">**Deployment package**: Select the zip file to your application project, and select **OK**.</span></span> 

8. <span data-ttu-id="ceed4-165">選択、**エージェント フェーズ**タスク。</span><span class="sxs-lookup"><span data-stu-id="ceed4-165">Select the **Agent phase** task.</span></span> <span data-ttu-id="ceed4-166">選択、**既定**エージェント キュー。</span><span class="sxs-lookup"><span data-stu-id="ceed4-166">Select the **Default** Agent queue.</span></span> <span data-ttu-id="ceed4-167">**保存**変更します。</span><span class="sxs-lookup"><span data-stu-id="ceed4-167">**Save** your changes.</span></span>

9. <span data-ttu-id="ceed4-168">選択**リリース** > **リリース作成**:</span><span class="sxs-lookup"><span data-stu-id="ceed4-168">Select **Release** > **Create release**:</span></span>  

    ![リリースでは、リリースの作成](../core/media/vsts-create-release.png)

10. <span data-ttu-id="ceed4-170">選択**キュー**します。</span><span class="sxs-lookup"><span data-stu-id="ceed4-170">Select **Queue**.</span></span> <span data-ttu-id="ceed4-171">リリースのリンクをクリックして、状態を確認します。</span><span class="sxs-lookup"><span data-stu-id="ceed4-171">Check the status by clicking the release link.</span></span> <span data-ttu-id="ceed4-172">失敗した場合、エラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ceed4-172">If it fails, the error displays.</span></span> <span data-ttu-id="ceed4-173">成功した場合は、アプリケーションが BizTalk 管理コンソールに追加されます。</span><span class="sxs-lookup"><span data-stu-id="ceed4-173">If it succeeds, the application is added to the BizTalk Administration console.</span></span> 

## <a name="what-you-did"></a><span data-ttu-id="ceed4-174">どのような</span><span class="sxs-lookup"><span data-stu-id="ceed4-174">What you did</span></span>

<span data-ttu-id="ceed4-175">Vsts では、Git または Team Foundation バージョン管理が (自分で選択した) 内でアプリケーションを構築するビルド定義を作成します。</span><span class="sxs-lookup"><span data-stu-id="ceed4-175">In VSTS, you created a build definition that builds your application within Git or Team Foundation Version Control (whatever you chose).</span></span> <span data-ttu-id="ceed4-176">ソース管理内の変更を加えるし、変更が自動的に検出されると、それらをプッシュすることができます。</span><span class="sxs-lookup"><span data-stu-id="ceed4-176">When changes are made within the source control, the changes are automatically detected, and you can push them.</span></span> <span data-ttu-id="ceed4-177">ビルドが完了すると、BizTalk Server は、BizTalk Server 管理コンソールに表示するアプリケーションをデプロイするリリース定義を作成します。</span><span class="sxs-lookup"><span data-stu-id="ceed4-177">After the build completes, you created a release definition that deploys the application to BizTalk Server, which you can see in BizTalk Server Administration.</span></span> 

## <a name="next-step"></a><span data-ttu-id="ceed4-178">次の手順</span><span class="sxs-lookup"><span data-stu-id="ceed4-178">Next step</span></span>
<span data-ttu-id="ceed4-179">この段階で終了しました。</span><span class="sxs-lookup"><span data-stu-id="ceed4-179">At this step, you're done.</span></span> <span data-ttu-id="ceed4-180">場合は、環境トークンを BizTalk XML バインド ファイル内で作成し、環境トークンと一致する VSTS 内の変数を作成します。</span><span class="sxs-lookup"><span data-stu-id="ceed4-180">If you prefer, you can create environmental tokens within your BizTalk XML binding file, and create variables within VSTS that match the environmental tokens.</span></span> <span data-ttu-id="ceed4-181">参照してください[環境トークンと変数を構成](configure-environmental-tokens-and-variables-for-automatic-deployment.md)詳細については、します。</span><span class="sxs-lookup"><span data-stu-id="ceed4-181">See [Configure environmental tokens and variables](configure-environmental-tokens-and-variables-for-automatic-deployment.md) for the details.</span></span> 
