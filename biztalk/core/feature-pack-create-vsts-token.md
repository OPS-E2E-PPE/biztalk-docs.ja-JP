---
title: "手順 2 - VSTS トークンを作成してエージェントのインストール |Microsoft ドキュメント"
description: "複製を作成、VSTS セキュリティのアクセス トークン、VSTS プロジェクトを Visual Studio にし、BizTalk Server プロジェクトの展開を自動化するビルド エージェントをインストール"
ms.custom: 
ms.date: 11/20/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 77296d9f2325bebaba4f4fa1ce7c55034ef1ead6
ms.sourcegitcommit: f65e8ed2b8c18cded26b9d60868fb6a56bcc1205
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2017
---
# <a name="step-2-create-the-token--install-the-agent"></a><span data-ttu-id="9ede1-103">手順 2: トークンを作成して (&)、エージェントのインストール</span><span class="sxs-lookup"><span data-stu-id="9ede1-103">Step 2: Create the token & install the agent</span></span>

<span data-ttu-id="9ede1-104">個人用アクセス トークン (PAT) は、Visual Studio Team Services で作成されます。</span><span class="sxs-lookup"><span data-stu-id="9ede1-104">A personal access token (PAT) is created in Visual Studio Team Services.</span></span> <span data-ttu-id="9ede1-105">このトークンは、パスワードを指定するために、され、認証に VSTS ビルド エージェントによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="9ede1-105">This token is your password, and is used by the VSTS build agent to authenticate.</span></span> <span data-ttu-id="9ede1-106">トークンが作成するときにのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="9ede1-106">The token is only displayed when you create it.</span></span> <span data-ttu-id="9ede1-107">その後、それが表示されていないされなくなります。</span><span class="sxs-lookup"><span data-stu-id="9ede1-107">After that, it isn't displayed anymore.</span></span> <span data-ttu-id="9ede1-108">これを作成すると、別のファイルを保存できる場所に保存します。</span><span class="sxs-lookup"><span data-stu-id="9ede1-108">So once you create it, save it to another file in a remember-able location.</span></span> 

<span data-ttu-id="9ede1-109">PAT について詳しくは[VSTS と TFS の個人用アクセス トークンによるアクセスの認証](https://docs.microsoft.com/vsts/accounts/use-personal-access-tokens-to-authenticate)です。</span><span class="sxs-lookup"><span data-stu-id="9ede1-109">More info on PAT at [Authenticate access with personal access tokens for VSTS and TFS](https://docs.microsoft.com/vsts/accounts/use-personal-access-tokens-to-authenticate).</span></span> 

<span data-ttu-id="9ede1-110">トークンを作成した後は、ビルド エージェントをインストールして、このトークンを使用するように構成します。</span><span class="sxs-lookup"><span data-stu-id="9ede1-110">After you create the token, you install the build agent, and configure it to use this token.</span></span> 

## <a name="before-you-begin"></a><span data-ttu-id="9ede1-111">アンインストールの準備</span><span class="sxs-lookup"><span data-stu-id="9ede1-111">Before you begin</span></span>
<span data-ttu-id="9ede1-112">完全な[ステップ 1 - 追加のアプリケーション プロジェクトと json を更新](feature-pack-add-application-project.md)です。</span><span class="sxs-lookup"><span data-stu-id="9ede1-112">Complete [Step 1 - Add Application project and update json](feature-pack-add-application-project.md).</span></span>

## <a name="sign-into-vsts-and-create-the-token"></a><span data-ttu-id="9ede1-113">VSTS にサインインし、トークンの作成</span><span class="sxs-lookup"><span data-stu-id="9ede1-113">Sign into VSTS, and create the token</span></span>
1. <span data-ttu-id="9ede1-114">移動して[https://app.vsaex.visualstudio.com/go/profile](https://app.vsaex.visualstudio.com/go/profile)、および職場または学校のアカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="9ede1-114">Go to [https://app.vsaex.visualstudio.com/go/profile](https://app.vsaex.visualstudio.com/go/profile), and sign-in with your work or school account.</span></span> <span data-ttu-id="9ede1-115">サインインした後、VSTS アカウントが一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="9ede1-115">After you sign in, your VSTS account is listed.</span></span> <span data-ttu-id="9ede1-116">次の例では、アカウントは**mandiaprojects.visualstudio.com**です。</span><span class="sxs-lookup"><span data-stu-id="9ede1-116">In the following example, the account is **mandiaprojects.visualstudio.com**.</span></span>  

    ![VSTS アカウント](../core/media/team-services-accounts.png)

    <span data-ttu-id="9ede1-118">アカウントを持っていない場合は、選択**新しいアカウントを作成**名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="9ede1-118">If you don’t have an account, select **Create new account**, and enter a name.</span></span> <span data-ttu-id="9ede1-119">コードを管理するため、希望個人間**Git または Team Foundation バージョン管理**です。</span><span class="sxs-lookup"><span data-stu-id="9ede1-119">To manage your code, choose your personal preference between **Git or Team Foundation Version Control**.</span></span> <span data-ttu-id="9ede1-120">完了したら、新しいアカウントを作成、およびのようなサイト*https://YourAccountName.visualstudio.com/MyFirstProject*が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9ede1-120">When finished, your new account is created, and a site similar to *https://YourAccountName.visualstudio.com/MyFirstProject* opens:</span></span>  

    ![Git または TFS](../core/media/git-or-team-foundation.png)

2. <span data-ttu-id="9ede1-122">VSTS アカウントを開き (https://*YourAccountName*。 visualstudio.com)。</span><span class="sxs-lookup"><span data-stu-id="9ede1-122">Open your VSTS account (https://*YourAccountName*.visualstudio.com).</span></span> <span data-ttu-id="9ede1-123">右側の隅のアイコンを選択して選択、**セキュリティ**:</span><span class="sxs-lookup"><span data-stu-id="9ede1-123">Select your icon in the top right-side corner, and select **Security**:</span></span> 

    ![アカウントのセキュリティを開く](../core/media/vsts-account-security.png)

3. <span data-ttu-id="9ede1-125">**個人用アクセス トークン**が自動的に開きます。</span><span class="sxs-lookup"><span data-stu-id="9ede1-125">**Personal access tokens** automatically opens.</span></span> <span data-ttu-id="9ede1-126">既存のエージェントがあれば、選択し、確認**エージェント プール (読み取り、管理)**が選択されています。</span><span class="sxs-lookup"><span data-stu-id="9ede1-126">If you have an existing agent, select it, and confirm **Agent Pools (read, manage)** is selected:</span></span>

    ![エージェント プールの読み取りし、管理](../core/media/agent-pools-read-manage.png)

    > [!IMPORTANT]
    > <span data-ttu-id="9ede1-128">アクセス トークンを知る必要があります。</span><span class="sxs-lookup"><span data-stu-id="9ede1-128">You must know the access token.</span></span> <span data-ttu-id="9ede1-129">いない場合、しなかったに注意してください、任意の場所、取得できません。</span><span class="sxs-lookup"><span data-stu-id="9ede1-129">If you don’t, and didn’t note it anywhere, it cannot be retrieved.</span></span> <span data-ttu-id="9ede1-130">このような状況では、新しいエージェントを作成します。</span><span class="sxs-lookup"><span data-stu-id="9ede1-130">In this situation, create a new agent.</span></span> 

    <span data-ttu-id="9ede1-131">既存のエージェントを持っていない場合は、選択**追加**説明を入力、有効期限の日付を設定およびアカウントを選択します。</span><span class="sxs-lookup"><span data-stu-id="9ede1-131">If you don’t have an existing agent, select **Add**, enter a description, set the expiration date, and select your account.</span></span> <span data-ttu-id="9ede1-132">**スコープを選択した****エージェント プール (読み取り、管理)**:</span><span class="sxs-lookup"><span data-stu-id="9ede1-132">In **Selected scopes**, select **Agent Pools (read, manage)**:</span></span> 

    ![新しいエージェントを作成する - 読み取りし、管理](../core/media/vsts-new-build-agent.png)

    <span data-ttu-id="9ede1-134">選択**トークンを作成する**です。</span><span class="sxs-lookup"><span data-stu-id="9ede1-134">Select **Create Token**.</span></span> <span data-ttu-id="9ede1-135">**トークンの値に注意してください。必要があります将来の手順を実行します。**</span><span class="sxs-lookup"><span data-stu-id="9ede1-135">**Note the token value; you need in future steps.**</span></span>

4. <span data-ttu-id="9ede1-136">選択**コード**を選択して**Visual Studio での複製**:</span><span class="sxs-lookup"><span data-stu-id="9ede1-136">Select **Code**, and select **Clone in Visual Studio**:</span></span>  

    ![プロジェクトでコードを選択します.](../core/media/vsts-project-code.png)  

    ![Visual Studio での複製します。](../core/media/vsts-clone-in-visual-studio.png)

5. <span data-ttu-id="9ede1-139">Visual Studio が開きます。</span><span class="sxs-lookup"><span data-stu-id="9ede1-139">Visual Studio opens.</span></span> <span data-ttu-id="9ede1-140">Visual Studio 内では、BizTalk ソリューションを開きます。</span><span class="sxs-lookup"><span data-stu-id="9ede1-140">Within Visual Studio, open your BizTalk solution.</span></span> 

## <a name="install-the-build-agent"></a><span data-ttu-id="9ede1-141">ビルド エージェントをインストールします。</span><span class="sxs-lookup"><span data-stu-id="9ede1-141">Install the Build Agent</span></span>

<span data-ttu-id="9ede1-142">ビルド エージェントは、BizTalk 開発用コンピューターにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="9ede1-142">The build agent is installed on the BizTalk development computer.</span></span> <span data-ttu-id="9ede1-143">展開グループを使用する場合を展開するすべての BizTalk server でビルド エージェントがインストールされています。</span><span class="sxs-lookup"><span data-stu-id="9ede1-143">If using deployment groups, the build agent is installed on all the BizTalk servers you want to deploy to.</span></span> <span data-ttu-id="9ede1-144">次の手順では、1 台のコンピューターにビルド エージェントをインストールする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="9ede1-144">The following steps show you how to install the build agent on a single computer.</span></span> <span data-ttu-id="9ede1-145">展開グループの使用に関する詳細については、「[展開グループ](https://docs.microsoft.com/vsts/build-release/concepts/definitions/release/deployment-groups/index)です。</span><span class="sxs-lookup"><span data-stu-id="9ede1-145">For details on using deployment groups, see [Deployment groups](https://docs.microsoft.com/vsts/build-release/concepts/definitions/release/deployment-groups/index).</span></span>

1. <span data-ttu-id="9ede1-146">VSTS アカウントとは何か、プロジェクトを開くなどの*https://YourAccountName.visualstudio.com/MyFirstProject*です。</span><span class="sxs-lookup"><span data-stu-id="9ede1-146">Open your VSTS account and project, which is something like *https://YourAccountName.visualstudio.com/MyFirstProject*.</span></span> <span data-ttu-id="9ede1-147">設定アイコンを選択し、選択**エージェント キュー**:</span><span class="sxs-lookup"><span data-stu-id="9ede1-147">Select the settings icon, and select **Agent Queues**:</span></span>  

    ![設定 > エージェント キュー](../core/media/vsts-settings-agent-queues.png)

2. <span data-ttu-id="9ede1-149">選択、**既定**エージェント、および選択**エージェントのダウンロード**です。</span><span class="sxs-lookup"><span data-stu-id="9ede1-149">Select the **Default** agent, and select **Download Agent**.</span></span> <span data-ttu-id="9ede1-150">選択、**ダウンロード**ボタンをクリックし、ファイルを保存して、**ダウンロード**フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="9ede1-150">Select the **Download** button, and save the file to your **Downloads** folders.</span></span>

3. <span data-ttu-id="9ede1-151">インストールの手順は自動的に開きます。</span><span class="sxs-lookup"><span data-stu-id="9ede1-151">The install steps automatically open.</span></span> <span data-ttu-id="9ede1-152">詳細については、最新のこれらの手順に従います。</span><span class="sxs-lookup"><span data-stu-id="9ede1-152">Follow those steps for the most up-to-date details.</span></span> <span data-ttu-id="9ede1-153">次にいくつかのガイダンスを示します。</span><span class="sxs-lookup"><span data-stu-id="9ede1-153">Here is some guidance:</span></span> 

    1. <span data-ttu-id="9ede1-154">管理者として Windows PowerShell を開きます。</span><span class="sxs-lookup"><span data-stu-id="9ede1-154">Open Windows PowerShell as Administrator.</span></span>

    2. <span data-ttu-id="9ede1-155">エージェントを作成するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="9ede1-155">To create the agent, enter:</span></span> 

        ```powershell
        PS C:\> mkdir agent ; cd agent  

        PS C:\agent> Add-Type -AssemblyName System.IO.Compression.FileSystem ; [System.IO.Compression.ZipFile]::ExtractToDirectory("$HOME\Downloads\vsts-agent-win7-x64-2.124.0.zip", "$PWD")
        ```
    
        <span data-ttu-id="9ede1-156">Vsts エージェント ファイルのバージョンの変更。</span><span class="sxs-lookup"><span data-stu-id="9ede1-156">The vsts-agent file version changes.</span></span> <span data-ttu-id="9ede1-157">したがって固有の詳細について VSTS のインストール手順に従います。</span><span class="sxs-lookup"><span data-stu-id="9ede1-157">So follow the VSTS install steps for specific details.</span></span> <span data-ttu-id="9ede1-158">ヒットした後は、入力を返すには、プロンプトに数分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="9ede1-158">After you hit enter, it may take a couple of minutes for the prompt to return.</span></span> 

    3. <span data-ttu-id="9ede1-159">エージェントを構成するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="9ede1-159">To configure the agent, enter:</span></span> 

        ```powershell
        PS C:\agent> .\config.cmd
        ```

    4. <span data-ttu-id="9ede1-160">次の詳細を入力します。</span><span class="sxs-lookup"><span data-stu-id="9ede1-160">Enter the following details:</span></span>  
        
        | <span data-ttu-id="9ede1-161">プロパティ</span><span class="sxs-lookup"><span data-stu-id="9ede1-161">Property</span></span> | <span data-ttu-id="9ede1-162">値</span><span class="sxs-lookup"><span data-stu-id="9ede1-162">Value</span></span> |
        | --- | --- |
        | <span data-ttu-id="9ede1-163">[サーバー URL]</span><span class="sxs-lookup"><span data-stu-id="9ede1-163">Server URL</span></span>| <span data-ttu-id="9ede1-164">https://{your-account}.visualstudio.com</span><span class="sxs-lookup"><span data-stu-id="9ede1-164">https://{your-account}.visualstudio.com</span></span> |
        | <span data-ttu-id="9ede1-165">[認証の種類]</span><span class="sxs-lookup"><span data-stu-id="9ede1-165">Authentication Type</span></span> | <span data-ttu-id="9ede1-166">PAT</span><span class="sxs-lookup"><span data-stu-id="9ede1-166">PAT</span></span> |
        | <span data-ttu-id="9ede1-167">個人用アクセス トークン</span><span class="sxs-lookup"><span data-stu-id="9ede1-167">Personal access token</span></span> | <span data-ttu-id="9ede1-168">VSTS トークンを貼り付けます</span><span class="sxs-lookup"><span data-stu-id="9ede1-168">Paste your VSTS token</span></span> |
        | <span data-ttu-id="9ede1-169">エージェント プール</span><span class="sxs-lookup"><span data-stu-id="9ede1-169">Agent pool</span></span> | <span data-ttu-id="9ede1-170">既定値を入力します。</span><span class="sxs-lookup"><span data-stu-id="9ede1-170">Enter for the default</span></span> |
        | <span data-ttu-id="9ede1-171">エージェント名</span><span class="sxs-lookup"><span data-stu-id="9ede1-171">Agent name</span></span> | <span data-ttu-id="9ede1-172">既定値を入力します。</span><span class="sxs-lookup"><span data-stu-id="9ede1-172">Enter for the default</span></span> |
        | <span data-ttu-id="9ede1-173">[置換]</span><span class="sxs-lookup"><span data-stu-id="9ede1-173">Replace</span></span> | <span data-ttu-id="9ede1-174">*既存のエージェントがある場合のみ表示されます。*</span><span class="sxs-lookup"><span data-stu-id="9ede1-174">*Only displays if you have an existing agent*</span></span> |
        | <span data-ttu-id="9ede1-175">作業フォルダー</span><span class="sxs-lookup"><span data-stu-id="9ede1-175">Work folder</span></span> | <span data-ttu-id="9ede1-176">既定値を入力します。</span><span class="sxs-lookup"><span data-stu-id="9ede1-176">Enter for the default</span></span> |
        | <span data-ttu-id="9ede1-177">エージェントをサービスとして実行します。</span><span class="sxs-lookup"><span data-stu-id="9ede1-177">Run agent as a service</span></span> | <span data-ttu-id="9ede1-178">Y</span><span class="sxs-lookup"><span data-stu-id="9ede1-178">Y</span></span> |
        | <span data-ttu-id="9ede1-179">ユーザー アカウント</span><span class="sxs-lookup"><span data-stu-id="9ede1-179">User account</span></span> | <span data-ttu-id="9ede1-180">これかは、開発者が、アクセス許可の問題が発生した可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9ede1-180">This is up to you, but you may run into a permissions issue.</span></span> <br/><br/><span data-ttu-id="9ede1-181">現在のログオン アカウント、ローカル管理者である入力を検討してください。</span><span class="sxs-lookup"><span data-stu-id="9ede1-181">Consider entering your current logged-on account, which is a local Admin.</span></span> |

    5. <span data-ttu-id="9ede1-182">完了したら、PowerShell ウィンドウは、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="9ede1-182">When finished, your PowerShell window looks like the following:</span></span>  
    
        ![エージェントのインストール](../core/media/vsts-agent-powershell-install.png)

4. <span data-ttu-id="9ede1-184">新しいサービスを表示する services.msc を開きます。</span><span class="sxs-lookup"><span data-stu-id="9ede1-184">Open services.msc to see the new service.</span></span> <span data-ttu-id="9ede1-185">実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9ede1-185">It should be running:</span></span>  

    ![サービスが実行されています。](../core/media/vsts-service.png)

    <span data-ttu-id="9ede1-187">開始するには、サービスが失敗した場合は[削除し、再構成エージェント](https://docs.microsoft.com/vsts/build-release/actions/agents/v2-windows)詳細特権を持つアカウントを使用します。</span><span class="sxs-lookup"><span data-stu-id="9ede1-187">If the service fails to start, [remove and re-configure an agent](https://docs.microsoft.com/vsts/build-release/actions/agents/v2-windows) using an account with more privilages.</span></span>


## <a name="what-you-did"></a><span data-ttu-id="9ede1-188">どのような</span><span class="sxs-lookup"><span data-stu-id="9ede1-188">What you did</span></span>

<span data-ttu-id="9ede1-189">VSTS アカウントにサインインし、セキュリティ トークンを作成します。</span><span class="sxs-lookup"><span data-stu-id="9ede1-189">You signed into your VSTS account, and created a security token.</span></span> <span data-ttu-id="9ede1-190">このセキュリティ トークンが、パスワードのような VSTS プロジェクトに対するアクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="9ede1-190">This security token is like a password, and gives you access to your VSTS project.</span></span> <span data-ttu-id="9ede1-191">ようにすることを確認して、保存された 1 回のみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="9ede1-191">It's only displayed once, so be sure you saved it.</span></span> <span data-ttu-id="9ede1-192">Visual studio は、VSTS プロジェクトを複製して BizTalk 開発用コンピューターでサービスとして実行されているエージェントを作成します。</span><span class="sxs-lookup"><span data-stu-id="9ede1-192">You also cloned your VSTS project into Visual Studio, and created an agent that runs as a service on your BizTalk development computer.</span></span> <span data-ttu-id="9ede1-193">このエージェントは、セキュリティ トークンを使用します。</span><span class="sxs-lookup"><span data-stu-id="9ede1-193">This agent uses the security token.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="9ede1-194">次の手順</span><span class="sxs-lookup"><span data-stu-id="9ede1-194">Next steps</span></span>
[<span data-ttu-id="9ede1-195">手順 3: ビルドの作成し、定義のリリース</span><span class="sxs-lookup"><span data-stu-id="9ede1-195">Step 3: Create the build and release definitions</span></span>](feature-pack-add-build-release-definitions.md)  
[<span data-ttu-id="9ede1-196">環境のトークンと変数を構成します。</span><span class="sxs-lookup"><span data-stu-id="9ede1-196">Configure environmental tokens and variables</span></span>](configure-environmental-tokens-and-variables-for-automatic-deployment.md)