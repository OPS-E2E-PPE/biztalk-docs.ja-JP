---
title: 手順 3 - ビルドとリリース定義を作成 |Microsoft ドキュメント
description: Vsts、git または TFS リポジトリ内のプロジェクトをビルドし、BizTalk Server アプリケーションを配置するリリース定義を作成するビルド定義を作成します。
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
ms.openlocfilehash: 37928509c255dbb2720ad393dfc0f1cee0386a85
ms.sourcegitcommit: ba3c4876acc1bf3ee2961ca80c18d930a42c6696
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32320946"
---
# <a name="step-3-create-the-build-and-release-definition"></a><span data-ttu-id="ef9ed-103">手順 3: ビルドを作成し、リリース定義</span><span class="sxs-lookup"><span data-stu-id="ef9ed-103">Step 3: Create the build and release definition</span></span>

<span data-ttu-id="ef9ed-104">ビルドとリリース定義 Visual Studio Team Services となる作業は、おそらく VSTS 管理者が行う必要があります。ビルド定義が、git リポジトリ内で、プロジェクトをビルドし、リリース定義は、BizTalk Server 環境に展開します。</span><span class="sxs-lookup"><span data-stu-id="ef9ed-104">The build and release definitions are Visual Studio Team Services tasks, and should probably be done by a VSTS admin. The build definition builds your project within your git repository, and the release definitions deploys it to your BizTalk Server environment.</span></span> 

## <a name="before-you-begin"></a><span data-ttu-id="ef9ed-105">アンインストールの準備</span><span class="sxs-lookup"><span data-stu-id="ef9ed-105">Before you begin</span></span>
<span data-ttu-id="ef9ed-106">完全な[エージェントをインストールして、手順 2 - 作成 VSTS トークン](feature-pack-create-vsts-token.md)です。</span><span class="sxs-lookup"><span data-stu-id="ef9ed-106">Complete [Step 2 - Create VSTS token and install agent](feature-pack-create-vsts-token.md).</span></span>

## <a name="add-the-build-tasks"></a><span data-ttu-id="ef9ed-107">ビルド タスクを追加します。</span><span class="sxs-lookup"><span data-stu-id="ef9ed-107">Add the Build tasks</span></span>
1. <span data-ttu-id="ef9ed-108">プロジェクトで、次のように選択します。**ビルドとリリースの**します。</span><span class="sxs-lookup"><span data-stu-id="ef9ed-108">In your project, select **Build and release**.</span></span> <span data-ttu-id="ef9ed-109">[ビルド] タブを開きます。</span><span class="sxs-lookup"><span data-stu-id="ef9ed-109">The Builds tab opens.</span></span> <span data-ttu-id="ef9ed-110">作成、**新規**定義。</span><span class="sxs-lookup"><span data-stu-id="ef9ed-110">Create a **New** definition:</span></span>

    ![新しいビルド定義](../core/media/vsts-new-definition.png)

2. <span data-ttu-id="ef9ed-112">選択、**空**テンプレート、および選択**適用**:</span><span class="sxs-lookup"><span data-stu-id="ef9ed-112">Select the **Empty** template, and select **Apply**:</span></span>  

    ![空のテンプレートを選択します。](../core/media/vsts-emtpy-template.png)
 
3. <span data-ttu-id="ef9ed-114">設定、**エージェント キュー**既定値にします。</span><span class="sxs-lookup"><span data-stu-id="ef9ed-114">Set the **Agent Queue** to Default:</span></span> 

    ![既定のキューを選択します。](../core/media/vsts-select-agent-queue.png)

4. <span data-ttu-id="ef9ed-116">**フェーズ 1**、タスクを追加、選択**Visual Studio ビルド**を選択して**追加**:</span><span class="sxs-lookup"><span data-stu-id="ef9ed-116">In **Phase 1**, add a task, select **Visual Studio Build**, and select **Add**:</span></span>

    ![VS ビルド タスクを追加します。](../core/media/vsts-add-visual-studio-task.png)

5. <span data-ttu-id="ef9ed-118">Visual Studio ビルド タスクだけに追加され、次のプロパティの設定をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ef9ed-118">Click the Visual Studio Build task you just added, and set the following properties:</span></span>  

    | <span data-ttu-id="ef9ed-119">プロパティ</span><span class="sxs-lookup"><span data-stu-id="ef9ed-119">Property</span></span> | <span data-ttu-id="ef9ed-120">を設定します。</span><span class="sxs-lookup"><span data-stu-id="ef9ed-120">Set to</span></span> |
    | --- | --- | 
    | <span data-ttu-id="ef9ed-121">表示名</span><span class="sxs-lookup"><span data-stu-id="ef9ed-121">Display name</span></span> | <span data-ttu-id="ef9ed-122">*YourProjectName*ソリューションをビルド \* \*\*.sln</span><span class="sxs-lookup"><span data-stu-id="ef9ed-122">*YourProjectName* Build solution \*\*\*.sln</span></span> | 
    | <span data-ttu-id="ef9ed-123">Visual Studio のバージョン</span><span class="sxs-lookup"><span data-stu-id="ef9ed-123">Visual Studio version</span></span> | <span data-ttu-id="ef9ed-124">Visual Studio 2015</span><span class="sxs-lookup"><span data-stu-id="ef9ed-124">Visual Studio 2015</span></span> | 
    | <span data-ttu-id="ef9ed-125">MSBuild のアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="ef9ed-125">MSBuild Architecture</span></span> | <span data-ttu-id="ef9ed-126">MSBuild x86</span><span class="sxs-lookup"><span data-stu-id="ef9ed-126">MSBuild x86</span></span> | 

6. <span data-ttu-id="ef9ed-127">**フェーズ 1**、タスクを追加、選択**ビルド成果物の発行**を選択して**追加**:</span><span class="sxs-lookup"><span data-stu-id="ef9ed-127">In **Phase 1**, add a task, select **Publish Build Artifacts**, and select **Add**:</span></span> 

    ![VS ビルド タスクを追加します。](../core/media/vsts-add-publish-build-task.png)

7. <span data-ttu-id="ef9ed-129">選択、**成果物の発行**タスク、および優先入力**表示名**です。</span><span class="sxs-lookup"><span data-stu-id="ef9ed-129">Select the **Publish Artifact** task, and enter your preferred **Display name**.</span></span> <span data-ttu-id="ef9ed-130">**を発行するパス**、select、**しています.** ボタンをクリックし、アプリケーションのプロジェクト フォルダー (例: appProjectHelloWorld) を選択します。</span><span class="sxs-lookup"><span data-stu-id="ef9ed-130">For **Path to publish**, select the **...**  button, and choose the application project folder (e.g. appProjectHelloWorld).</span></span> <span data-ttu-id="ef9ed-131">**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ef9ed-131">Select **OK**.</span></span>

8. <span data-ttu-id="ef9ed-132">**成果物名**任意に指定することができます。</span><span class="sxs-lookup"><span data-stu-id="ef9ed-132">The **Artifact Name** can be anything you want.</span></span> <span data-ttu-id="ef9ed-133">選択**保存**です。</span><span class="sxs-lookup"><span data-stu-id="ef9ed-133">Select **Save**.</span></span> 

9. <span data-ttu-id="ef9ed-134">移動して**トリガー**、設定と、**状態のトリガー**に**有効**:</span><span class="sxs-lookup"><span data-stu-id="ef9ed-134">Go to **Triggers**, and set the **Trigger status** to **Enabled**:</span></span>  

    ![VS ビルド タスクを追加します。](../core/media/vsts-continuous-integration.png)

10. <span data-ttu-id="ef9ed-136">**保存 (&) キュー**ビルド定義をテストします。</span><span class="sxs-lookup"><span data-stu-id="ef9ed-136">**Save & Queue** to test your build definition.</span></span> <span data-ttu-id="ef9ed-137">キューに配置し、ときに、エージェント キューと、分岐を求められます。</span><span class="sxs-lookup"><span data-stu-id="ef9ed-137">When you queue, you are prompted for the agent queue and your branch.</span></span> <span data-ttu-id="ef9ed-138">選択、**既定**エージェント キュー、および自分の分岐を選択します。</span><span class="sxs-lookup"><span data-stu-id="ef9ed-138">Select the **Default** agent queue, and choose your branch.</span></span> <span data-ttu-id="ef9ed-139">選択**キュー**です。</span><span class="sxs-lookup"><span data-stu-id="ef9ed-139">Select **Queue**.</span></span>  

11. <span data-ttu-id="ef9ed-140">新しいビルドを開始し、成功または失敗を確認することを選択できます。</span><span class="sxs-lookup"><span data-stu-id="ef9ed-140">A new build is started, and you can select it to check for a success or failure.</span></span> 

## <a name="add-the-release-tasks"></a><span data-ttu-id="ef9ed-141">リリース タスクを追加します。</span><span class="sxs-lookup"><span data-stu-id="ef9ed-141">Add the release tasks</span></span>

<span data-ttu-id="ef9ed-142">ビルドが成功した場合、リリース定義は、BizTalk Server にアプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="ef9ed-142">When the build succeeds, the release definition deploys your application to your BizTalk Server.</span></span> 

1. <span data-ttu-id="ef9ed-143">選択、**リリース**] タブで [**新しい定義**です。</span><span class="sxs-lookup"><span data-stu-id="ef9ed-143">Select the **Releases** tab, select **New definition**.</span></span> 

2. <span data-ttu-id="ef9ed-144">選択、**空**テンプレート、および選択**適用**:</span><span class="sxs-lookup"><span data-stu-id="ef9ed-144">Select the **Empty** template, and select **Apply**:</span></span>

    ![空のテンプレートを追加します。](../core/media/vsts-empty-release-template.png)

3. <span data-ttu-id="ef9ed-146">変更、**環境名**に**デベロッパー**、またはそれを呼び出すものです。</span><span class="sxs-lookup"><span data-stu-id="ef9ed-146">Change the **Environment name** to **Dev**, or whatever you want to call it.</span></span> 

4. <span data-ttu-id="ef9ed-147">選択**追加の成果物**、プロジェクトのビルド定義を選択し、**追加**:</span><span class="sxs-lookup"><span data-stu-id="ef9ed-147">Select **Add artifact**, select your project, your build definition, and select **Add**:</span></span> 

5. <span data-ttu-id="ef9ed-148">移動して、**タスク** タブで、新しいタスクを追加します。</span><span class="sxs-lookup"><span data-stu-id="ef9ed-148">Go to the **Tasks** tab, add a new task:</span></span> 

    ![リリース タスクを追加します。](../core/media/vsts-new-release-tasks.png)

6. <span data-ttu-id="ef9ed-150">リストから、結果をフィルター処理で、選択、 **BizTalk Server アプリケーションの展開**タスク、および選択**追加**:</span><span class="sxs-lookup"><span data-stu-id="ef9ed-150">From the list, filter the results, select the **BizTalk Server Application Deployment** task, and select **Add**:</span></span>  

    ![BizTalk 展開のタスクを追加します。](../core/media/vsts-biztalk-application-deployment-task.png)

    <span data-ttu-id="ef9ed-152">場合**BizTalk Server アプリケーションの展開**ins't 一覧に表示し、インストールで[BizTalk アプリケーションの展開](https://marketplace.visualstudio.com/items?itemName=ms-biztalk.deploy-biztalk-application)です。</span><span class="sxs-lookup"><span data-stu-id="ef9ed-152">If **BizTalk Server Application Deployment** ins't listed, then install it at [Deploy BizTalk Application](https://marketplace.visualstudio.com/items?itemName=ms-biztalk.deploy-biztalk-application).</span></span>

7. <span data-ttu-id="ef9ed-153">選択、**展開**タスク、および値を入力します。</span><span class="sxs-lookup"><span data-stu-id="ef9ed-153">Select the **Deploy** task, and enter the values:</span></span> 

    <span data-ttu-id="ef9ed-154">**操作名**: オプション。</span><span class="sxs-lookup"><span data-stu-id="ef9ed-154">**Operation Name**: Your options:</span></span>   
        <span data-ttu-id="ef9ed-155">- **新しい BizTalk アプリケーションを作成する**: 新しいアプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="ef9ed-155">- **Create new BizTalk Application**: Deploys a new application.</span></span> <span data-ttu-id="ef9ed-156">アプリケーションが既に存在する場合、その (完全に停止)、現在のアプリケーションをアンインストールし、新しいアプリケーションをインストールします。</span><span class="sxs-lookup"><span data-stu-id="ef9ed-156">If the application already exists, it uninstalls the current applications (full stop), and installs the new application.</span></span> <span data-ttu-id="ef9ed-157">継続的な統合が有効になっているでは、リポジトリで更新されるときに、そのアプリケーションが自動的に再です。</span><span class="sxs-lookup"><span data-stu-id="ef9ed-157">If continuous integration is enabled, it automatically redeploys the application when it is updated in the repository.</span></span>   
        <span data-ttu-id="ef9ed-158">- **既存の BizTalk アプリケーションを更新して**: スキーマなどの変更を既に実行中のアプリケーションに追加します。</span><span class="sxs-lookup"><span data-stu-id="ef9ed-158">- **Update an existing BizTalk Application**: Appends changes, such as schemas, to an already running application.</span></span> <span data-ttu-id="ef9ed-159">アプリケーションの完全再展開は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="ef9ed-159">It does not require a full redeploy of the application.</span></span>  
        <span data-ttu-id="ef9ed-160">- **BizTalk Server アプリケーションをインストール**:[アプリケーションをインストールする](../core/how-to-install-a-biztalk-application.md)、BizTalk 管理のコンピューター名、および展開パッケージのパスを入力するとします。</span><span class="sxs-lookup"><span data-stu-id="ef9ed-160">- **Install BizTalk Server Application**: [Install the applications](../core/how-to-install-a-biztalk-application.md), and you enter the BizTalk management computer name, and the deployment package path.</span></span>  

     ![配置操作](../core/media/vsts-deploy-operations.png)

    <span data-ttu-id="ef9ed-162">**アプリケーション名**: 入力したテキストが BizTalk 管理コンソールでアプリケーション名になります。</span><span class="sxs-lookup"><span data-stu-id="ef9ed-162">**Application Name**: The text you enter will be the application name in BizTalk Administration.</span></span> <span data-ttu-id="ef9ed-163">**いない**BizTalk アプリケーション 1 を入力します。</span><span class="sxs-lookup"><span data-stu-id="ef9ed-163">Do **not** enter BizTalk Application 1.</span></span>

    <span data-ttu-id="ef9ed-164">**展開パッケージ**: アプリケーション プロジェクトに zip ファイルを選択し、選択**OK**です。</span><span class="sxs-lookup"><span data-stu-id="ef9ed-164">**Deployment package**: Select the zip file to your application project, and select **OK**.</span></span> 

8. <span data-ttu-id="ef9ed-165">選択、**エージェント フェーズ**タスク。</span><span class="sxs-lookup"><span data-stu-id="ef9ed-165">Select the **Agent phase** task.</span></span> <span data-ttu-id="ef9ed-166">選択、**既定**エージェント キュー。</span><span class="sxs-lookup"><span data-stu-id="ef9ed-166">Select the **Default** Agent queue.</span></span> <span data-ttu-id="ef9ed-167">**保存** 変更します。</span><span class="sxs-lookup"><span data-stu-id="ef9ed-167">**Save** your changes.</span></span>

9. <span data-ttu-id="ef9ed-168">選択**リリース** > **リリース作成**:</span><span class="sxs-lookup"><span data-stu-id="ef9ed-168">Select **Release** > **Create release**:</span></span>  

    ![リリースでは、リリースを作成します。](../core/media/vsts-create-release.png)

10. <span data-ttu-id="ef9ed-170">選択**キュー**です。</span><span class="sxs-lookup"><span data-stu-id="ef9ed-170">Select **Queue**.</span></span> <span data-ttu-id="ef9ed-171">リリースのリンクをクリックして、状態を確認します。</span><span class="sxs-lookup"><span data-stu-id="ef9ed-171">Check the status by clicking the release link.</span></span> <span data-ttu-id="ef9ed-172">失敗した場合、エラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ef9ed-172">If it fails, the error displays.</span></span> <span data-ttu-id="ef9ed-173">成功した場合は、アプリケーションが BizTalk 管理コンソールに追加されます。</span><span class="sxs-lookup"><span data-stu-id="ef9ed-173">If it succeeds, the application is added to the BizTalk Administration console.</span></span> 

## <a name="what-you-did"></a><span data-ttu-id="ef9ed-174">どのような</span><span class="sxs-lookup"><span data-stu-id="ef9ed-174">What you did</span></span>

<span data-ttu-id="ef9ed-175">VSTS では、Git または Team Foundation バージョン管理 (指定した内容) 内で、アプリケーションを構築するビルド定義を作成します。</span><span class="sxs-lookup"><span data-stu-id="ef9ed-175">In VSTS, you created a build definition that builds your application within Git or Team Foundation Version Control (whatever you chose).</span></span> <span data-ttu-id="ef9ed-176">ソース コントロール内の変更を加えるし、変更が自動的に検出されると、プッシュすることができます。</span><span class="sxs-lookup"><span data-stu-id="ef9ed-176">When changes are made within the source control, the changes are automatically detected, and you can push them.</span></span> <span data-ttu-id="ef9ed-177">ビルドが完了したら、BizTalk Server は、BizTalk Server 管理コンソールに表示するアプリケーションを展開するリリース定義を作成します。</span><span class="sxs-lookup"><span data-stu-id="ef9ed-177">After the build completes, you created a release definition that deploys the application to BizTalk Server, which you can see in BizTalk Server Administration.</span></span> 

## <a name="next-step"></a><span data-ttu-id="ef9ed-178">次の手順</span><span class="sxs-lookup"><span data-stu-id="ef9ed-178">Next step</span></span>
<span data-ttu-id="ef9ed-179">この手順では、次の完了しています。</span><span class="sxs-lookup"><span data-stu-id="ef9ed-179">At this step, you're done.</span></span> <span data-ttu-id="ef9ed-180">を使用する場合、BizTalk XML バインド ファイル内で環境のトークンを作成でき環境のトークンと一致する VSTS 内の変数を作成できます。</span><span class="sxs-lookup"><span data-stu-id="ef9ed-180">If you prefer, you can create environmental tokens within your BizTalk XML binding file, and create variables within VSTS that match the environmental tokens.</span></span> <span data-ttu-id="ef9ed-181">参照してください[環境トークンと変数を構成する](configure-environmental-tokens-and-variables-for-automatic-deployment.md)詳細については、します。</span><span class="sxs-lookup"><span data-stu-id="ef9ed-181">See [Configure environmental tokens and variables](configure-environmental-tokens-and-variables-for-automatic-deployment.md) for the details.</span></span> 
