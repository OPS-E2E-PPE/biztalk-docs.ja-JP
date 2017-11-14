---
title: "手順 3 - ビルドとリリース定義を作成 |Microsoft ドキュメント"
description: "Vsts、git または TFS リポジトリ内のプロジェクトをビルドし、BizTalk Server アプリケーションを配置するリリース定義を作成するビルド定義を作成します。"
ms.custom: 
ms.date: 11/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: de86d35fd615d8c0f1eee1127804645067c4bf6e
ms.sourcegitcommit: a0165ec2f1e8b58545638666b7bfa2bf440036fd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/09/2017
---
# <a name="step-3-create-the-build-and-release-definition"></a><span data-ttu-id="fca41-103">手順 3: ビルドを作成し、リリース定義</span><span class="sxs-lookup"><span data-stu-id="fca41-103">Step 3: Create the build and release definition</span></span>

<span data-ttu-id="fca41-104">ビルドとリリース定義 Visual Studio Team Services となる作業は、おそらく VSTS 管理者が行う必要があります。ビルド定義が、git リポジトリ内で、プロジェクトをビルドし、リリース定義は、BizTalk Server 環境に展開します。</span><span class="sxs-lookup"><span data-stu-id="fca41-104">The build and release definitions are Visual Studio Team Services tasks, and should probably be done by a VSTS admin. The build definition builds your project within your git repository, and the release definitions deploys it to your BizTalk Server environment.</span></span> 

## <a name="add-the-build-tasks"></a><span data-ttu-id="fca41-105">ビルド タスクを追加します。</span><span class="sxs-lookup"><span data-stu-id="fca41-105">Add the Build tasks</span></span>
1. <span data-ttu-id="fca41-106">プロジェクトで、次のように選択します。**ビルドとリリースの**します。</span><span class="sxs-lookup"><span data-stu-id="fca41-106">In your project, select **Build and release**.</span></span> <span data-ttu-id="fca41-107">[ビルド] タブを開きます。</span><span class="sxs-lookup"><span data-stu-id="fca41-107">The Builds tab opens.</span></span> <span data-ttu-id="fca41-108">作成、**新規**定義。</span><span class="sxs-lookup"><span data-stu-id="fca41-108">Create a **New** definition:</span></span>

    ![新しいビルド定義](../core/media/vsts-new-definition.png)

2. <span data-ttu-id="fca41-110">選択、**空**テンプレート、および選択**適用**:</span><span class="sxs-lookup"><span data-stu-id="fca41-110">Select the **Empty** template, and select **Apply**:</span></span>  

    ![空のテンプレートを選択します。](../core/media/vsts-emtpy-template.png)
 
3. <span data-ttu-id="fca41-112">設定、**エージェント キュー**既定値にします。</span><span class="sxs-lookup"><span data-stu-id="fca41-112">Set the **Agent Queue** to Default:</span></span> 

    ![既定のキューを選択します。](../core/media/vsts-select-agent-queue.png)

4. <span data-ttu-id="fca41-114">**フェーズ 1**、タスクを追加、選択**Visual Studio ビルド**を選択して**追加**:</span><span class="sxs-lookup"><span data-stu-id="fca41-114">In **Phase 1**, add a task, select **Visual Studio Build**, and select **Add**:</span></span>

    ![VS ビルド タスクを追加します。](../core/media/vsts-add-visual-studio-task.png)

5. <span data-ttu-id="fca41-116">Visual Studio ビルド タスクだけに追加され、次のプロパティの設定をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fca41-116">Click the Visual Studio Build task you just added, and set the following properties:</span></span>  

    | <span data-ttu-id="fca41-117">プロパティ</span><span class="sxs-lookup"><span data-stu-id="fca41-117">Property</span></span> | <span data-ttu-id="fca41-118">を設定します。</span><span class="sxs-lookup"><span data-stu-id="fca41-118">Set to</span></span> |
    | --- | --- | 
    | <span data-ttu-id="fca41-119">表示名</span><span class="sxs-lookup"><span data-stu-id="fca41-119">Display name</span></span> | <span data-ttu-id="fca41-120">*YourProjectName*ソリューションをビルド * *\*.sln</span><span class="sxs-lookup"><span data-stu-id="fca41-120">*YourProjectName* Build solution **\*.sln</span></span> | 
    | <span data-ttu-id="fca41-121">Visual Studio のバージョン</span><span class="sxs-lookup"><span data-stu-id="fca41-121">Visual Studio version</span></span> | <span data-ttu-id="fca41-122">Visual Studio 2015</span><span class="sxs-lookup"><span data-stu-id="fca41-122">Visual Studio 2015</span></span> | 
    | <span data-ttu-id="fca41-123">MSBuild のアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="fca41-123">MSBuild Architecture</span></span> | <span data-ttu-id="fca41-124">MSBuild x86</span><span class="sxs-lookup"><span data-stu-id="fca41-124">MSBuild x86</span></span> | 

6. <span data-ttu-id="fca41-125">**フェーズ 1**、タスクを追加、選択**ビルド成果物の発行**を選択して**追加**:</span><span class="sxs-lookup"><span data-stu-id="fca41-125">In **Phase 1**, add a task, select **Publish Build Artifacts**, and select **Add**:</span></span> 

    ![VS ビルド タスクを追加します。](../core/media/vsts-add-publish-build-task.png)

7. <span data-ttu-id="fca41-127">選択、**成果物の発行**タスク、および優先入力**表示名**です。</span><span class="sxs-lookup"><span data-stu-id="fca41-127">Select the **Publish Artifact** task, and enter your preferred **Display name**.</span></span> <span data-ttu-id="fca41-128">**を発行するパス**、select、**しています.**ボタンをクリックし、アプリケーションのプロジェクト フォルダー (例: appProjectHelloWorld) を選択します。</span><span class="sxs-lookup"><span data-stu-id="fca41-128">For **Path to publish**, select the **...**  button, and choose the application project folder (e.g. appProjectHelloWorld).</span></span> <span data-ttu-id="fca41-129">**[ OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="fca41-129">Select **OK**.</span></span>

8. <span data-ttu-id="fca41-130">**成果物名**任意に指定することができます。</span><span class="sxs-lookup"><span data-stu-id="fca41-130">The **Artifact Name** can be anything you want.</span></span> <span data-ttu-id="fca41-131">選択**保存**です。</span><span class="sxs-lookup"><span data-stu-id="fca41-131">Select **Save**.</span></span> 

9. <span data-ttu-id="fca41-132">移動して**トリガー**、設定と、**状態のトリガー**に**有効**:</span><span class="sxs-lookup"><span data-stu-id="fca41-132">Go to **Triggers**, and set the **Trigger status** to **Enabled**:</span></span>  

    ![VS ビルド タスクを追加します。](../core/media/vsts-continuous-integration.png)

10. <span data-ttu-id="fca41-134">**保存 (&) キュー**ビルド定義をテストします。</span><span class="sxs-lookup"><span data-stu-id="fca41-134">**Save & Queue** to test your build definition.</span></span> <span data-ttu-id="fca41-135">キューに配置し、ときに、エージェント キューと、分岐を求められます。</span><span class="sxs-lookup"><span data-stu-id="fca41-135">When you queue, you are prompted for the agent queue and your branch.</span></span> <span data-ttu-id="fca41-136">選択、**既定**エージェント キュー、および自分の分岐を選択します。</span><span class="sxs-lookup"><span data-stu-id="fca41-136">Select the **Default** agent queue, and choose your branch.</span></span> <span data-ttu-id="fca41-137">選択**キュー**です。</span><span class="sxs-lookup"><span data-stu-id="fca41-137">Select **Queue**.</span></span>  

11. <span data-ttu-id="fca41-138">新しいビルドを開始し、成功または失敗を確認することを選択できます。</span><span class="sxs-lookup"><span data-stu-id="fca41-138">A new build is started, and you can select it to check for a success or failure.</span></span> 

## <a name="add-the-release-tasks"></a><span data-ttu-id="fca41-139">リリース タスクを追加します。</span><span class="sxs-lookup"><span data-stu-id="fca41-139">Add the release tasks</span></span>

<span data-ttu-id="fca41-140">ビルドが成功した場合、リリース定義は、BizTalk Server にアプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="fca41-140">When the build succeeds, the release definition deploys your application to your BizTalk Server.</span></span> 

1. <span data-ttu-id="fca41-141">選択、**リリース**] タブで [**新しい定義**です。</span><span class="sxs-lookup"><span data-stu-id="fca41-141">Select the **Releases** tab, select **New definition**.</span></span> 

2. <span data-ttu-id="fca41-142">選択、**空**テンプレート、および選択**適用**:</span><span class="sxs-lookup"><span data-stu-id="fca41-142">Select the **Empty** template, and select **Apply**:</span></span>

    ![空のテンプレートを追加します。](../core/media/vsts-empty-release-template.png)

3. <span data-ttu-id="fca41-144">変更、**環境名**に**デベロッパー**、またはそれを呼び出すものです。</span><span class="sxs-lookup"><span data-stu-id="fca41-144">Change the **Environment name** to **Dev**, or whatever you want to call it.</span></span> 

4. <span data-ttu-id="fca41-145">選択**追加の成果物**、プロジェクトのビルド定義を選択し、**追加**:</span><span class="sxs-lookup"><span data-stu-id="fca41-145">Select **Add artifact**, select your project, your build definition, and select **Add**:</span></span> 

5. <span data-ttu-id="fca41-146">移動して、**タスク** タブで、新しいタスクを追加します。</span><span class="sxs-lookup"><span data-stu-id="fca41-146">Go to the **Tasks** tab, add a new task:</span></span> 

    ![リリース タスクを追加します。](../core/media/vsts-new-release-tasks.png)

6. <span data-ttu-id="fca41-148">リストから、結果をフィルター処理で、選択、 **BizTalk Server アプリケーションの展開**タスク、および選択**追加**:</span><span class="sxs-lookup"><span data-stu-id="fca41-148">From the list, filter the results, select the **BizTalk Server Application Deployment** task, and select **Add**:</span></span>  

    ![BizTalk 展開のタスクを追加します。](../core/media/vsts-biztalk-application-deployment-task.png)

    <span data-ttu-id="fca41-150">場合**BizTalk Server アプリケーションの展開**ins't 一覧に表示し、インストールで[BizTalk アプリケーションの展開](https://marketplace.visualstudio.com/items?itemName=ms-biztalk.deploy-biztalk-application)です。</span><span class="sxs-lookup"><span data-stu-id="fca41-150">If **BizTalk Server Application Deployment** ins't listed, then install it at [Deploy BizTalk Application](https://marketplace.visualstudio.com/items?itemName=ms-biztalk.deploy-biztalk-application).</span></span>

7. <span data-ttu-id="fca41-151">選択、**展開**タスク、および値を入力します。</span><span class="sxs-lookup"><span data-stu-id="fca41-151">Select the **Deploy** task, and enter the values:</span></span> 

    <span data-ttu-id="fca41-152">**操作名**: 選択**新しい BizTalk アプリケーションを作成する**です。</span><span class="sxs-lookup"><span data-stu-id="fca41-152">**Operation Name**: Select **Create new BizTalk Application**.</span></span> <span data-ttu-id="fca41-153">このオプションは、新しいアプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="fca41-153">This option deploys a new application.</span></span> <span data-ttu-id="fca41-154">アプリケーションが既に存在する場合、その (完全に停止)、現在のアプリケーションをアンインストールし、新しいアプリケーションをインストールします。</span><span class="sxs-lookup"><span data-stu-id="fca41-154">If the application already exists, it uninstalls the current applications (full stop), and installs the new application.</span></span> <span data-ttu-id="fca41-155">継続的な統合が有効になっているでは、リポジトリで更新されるときに、そのアプリケーションが自動的に再です。</span><span class="sxs-lookup"><span data-stu-id="fca41-155">If continuous integration is enabled, it automatically redeploys the application when it is updated in the repository.</span></span> <span data-ttu-id="fca41-156">**既存の BizTalk アプリケーションを更新して**スキーマなどの変更を既に実行中のアプリケーションに追加します。</span><span class="sxs-lookup"><span data-stu-id="fca41-156">**Update an existing BizTalk Application** appends changes, such as schemas, to an already running application.</span></span> <span data-ttu-id="fca41-157">アプリケーションの完全再展開は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="fca41-157">It does not require a full redeploy of the application.</span></span>

    <span data-ttu-id="fca41-158">**アプリケーション名**: 入力したテキストが BizTalk 管理コンソールでアプリケーション名になります。</span><span class="sxs-lookup"><span data-stu-id="fca41-158">**Application Name**: The text you enter will be the application name in BizTalk Administration.</span></span> <span data-ttu-id="fca41-159">**いない**BizTalk アプリケーション 1 を入力します。</span><span class="sxs-lookup"><span data-stu-id="fca41-159">Do **not** enter BizTalk Application 1.</span></span>

    <span data-ttu-id="fca41-160">**展開パッケージ**: アプリケーション プロジェクトに zip ファイルを選択し、選択**OK**です。</span><span class="sxs-lookup"><span data-stu-id="fca41-160">**Deployment package**: Select the zip file to your application project, and select **OK**.</span></span> 

8. <span data-ttu-id="fca41-161">選択、**エージェント フェーズ**タスク。</span><span class="sxs-lookup"><span data-stu-id="fca41-161">Select the **Agent phase** task.</span></span> <span data-ttu-id="fca41-162">選択、**既定**エージェント キュー。</span><span class="sxs-lookup"><span data-stu-id="fca41-162">Select the **Default** Agent queue.</span></span> <span data-ttu-id="fca41-163">**保存**変更します。</span><span class="sxs-lookup"><span data-stu-id="fca41-163">**Save** your changes.</span></span>

9. <span data-ttu-id="fca41-164">選択**リリース** > **リリース作成**:</span><span class="sxs-lookup"><span data-stu-id="fca41-164">Select **Release** > **Create release**:</span></span>  

    ![リリースでは、リリースを作成します。](../core/media/vsts-create-release.png)

10. <span data-ttu-id="fca41-166">選択**キュー**です。</span><span class="sxs-lookup"><span data-stu-id="fca41-166">Select **Queue**.</span></span> <span data-ttu-id="fca41-167">リリースのリンクをクリックして、状態を確認します。</span><span class="sxs-lookup"><span data-stu-id="fca41-167">Check the status by clicking the release link.</span></span> <span data-ttu-id="fca41-168">失敗した場合、エラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="fca41-168">If it fails, the error displays.</span></span> <span data-ttu-id="fca41-169">成功した場合は、アプリケーションが BizTalk 管理コンソールに追加されます。</span><span class="sxs-lookup"><span data-stu-id="fca41-169">If it succeeds, the application is added to the BizTalk Administration console.</span></span> 

## <a name="what-you-did"></a><span data-ttu-id="fca41-170">どのような</span><span class="sxs-lookup"><span data-stu-id="fca41-170">What you did</span></span>

<span data-ttu-id="fca41-171">VSTS では、Git または Team Foundation バージョン管理 (指定した内容) 内で、アプリケーションを構築するビルド定義を作成します。</span><span class="sxs-lookup"><span data-stu-id="fca41-171">In VSTS, you created a build definition that builds your application within Git or Team Foundation Version Control (whatever you chose).</span></span> <span data-ttu-id="fca41-172">ソース コントロール内の変更を加えるし、変更が自動的に検出されると、プッシュすることができます。</span><span class="sxs-lookup"><span data-stu-id="fca41-172">When changes are made within the source control, the changes are automatically detected, and you can push them.</span></span> <span data-ttu-id="fca41-173">ビルドが完了したら、BizTalk Server は、BizTalk Server 管理コンソールに表示するアプリケーションを展開するリリース定義を作成します。</span><span class="sxs-lookup"><span data-stu-id="fca41-173">After the build completes, you created a release definition that deploys the application to BizTalk Server, which you can see in BizTalk Server Administration.</span></span> 

## <a name="next-step"></a><span data-ttu-id="fca41-174">次の手順</span><span class="sxs-lookup"><span data-stu-id="fca41-174">Next step</span></span>
<span data-ttu-id="fca41-175">この手順では、次の完了しています。</span><span class="sxs-lookup"><span data-stu-id="fca41-175">At this step, you're done.</span></span> <span data-ttu-id="fca41-176">を使用する場合、BizTalk XML バインド ファイル内で環境のトークンを作成でき環境のトークンと一致する VSTS 内の変数を作成できます。</span><span class="sxs-lookup"><span data-stu-id="fca41-176">If you prefer, you can create environmental tokens within your BizTalk XML binding file, and create variables within VSTS that match the environmental tokens.</span></span> <span data-ttu-id="fca41-177">参照してください[環境トークンと変数を構成する](configure-environmental-tokens-and-variables-for-automatic-deployment.md)詳細については、します。</span><span class="sxs-lookup"><span data-stu-id="fca41-177">See [Configure environmental tokens and variables](configure-environmental-tokens-and-variables-for-automatic-deployment.md) for the details.</span></span> 