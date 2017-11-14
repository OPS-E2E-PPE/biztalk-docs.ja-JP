---
title: "手順 2 - VSTS トークンを作成してエージェントのインストール |Microsoft ドキュメント"
description: "複製を作成、VSTS セキュリティのアクセス トークン、VSTS プロジェクトを Visual Studio にし、BizTalk Server プロジェクトの展開を自動化するビルド エージェントをインストール"
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
ms.openlocfilehash: 46047f0bb6a536642d503d68bb4f9161ecdf7fc5
ms.sourcegitcommit: a0165ec2f1e8b58545638666b7bfa2bf440036fd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/09/2017
---
# <a name="step-2-create-the-token--install-the-agent"></a><span data-ttu-id="df127-103">手順 2: トークンを作成して (&)、エージェントのインストール</span><span class="sxs-lookup"><span data-stu-id="df127-103">Step 2: Create the token & install the agent</span></span>

<span data-ttu-id="df127-104">個人用アクセス トークン (PAT) は、Visual Studio Team Services で作成されます。</span><span class="sxs-lookup"><span data-stu-id="df127-104">A personal access token (PAT) is created in Visual Studio Team Services.</span></span> <span data-ttu-id="df127-105">このトークンは、パスワードを指定するために、され、認証に VSTS ビルド エージェントによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="df127-105">This token is your password, and is used by the VSTS build agent to authenticate.</span></span> <span data-ttu-id="df127-106">トークンが作成するときにのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="df127-106">The token is only displayed when you create it.</span></span> <span data-ttu-id="df127-107">その後、それが表示されていないされなくなります。</span><span class="sxs-lookup"><span data-stu-id="df127-107">After that, it isn't displayed anymore.</span></span> <span data-ttu-id="df127-108">これを作成すると、別のファイルを保存できる場所に保存します。</span><span class="sxs-lookup"><span data-stu-id="df127-108">So once you create it, save it to another file in a remember-able location.</span></span> 

<span data-ttu-id="df127-109">PAT について詳しくは[VSTS と TFS の個人用アクセス トークンによるアクセスの認証](https://docs.microsoft.com/vsts/accounts/use-personal-access-tokens-to-authenticate)です。</span><span class="sxs-lookup"><span data-stu-id="df127-109">More info on PAT at [Authenticate access with personal access tokens for VSTS and TFS](https://docs.microsoft.com/vsts/accounts/use-personal-access-tokens-to-authenticate).</span></span> 

<span data-ttu-id="df127-110">トークンを作成した後は、ビルド エージェントをインストールして、このトークンを使用するように構成します。</span><span class="sxs-lookup"><span data-stu-id="df127-110">After you create the token, you install the build agent, and configure it to use this token.</span></span> 

## <a name="sign-into-vsts-and-create-the-token"></a><span data-ttu-id="df127-111">VSTS にサインインし、トークンの作成</span><span class="sxs-lookup"><span data-stu-id="df127-111">Sign into VSTS, and create the token</span></span>
1. <span data-ttu-id="df127-112">移動して[https://app.vsaex.visualstudio.com/go/profile](https://app.vsaex.visualstudio.com/go/profile)、および職場または学校のアカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="df127-112">Go to [https://app.vsaex.visualstudio.com/go/profile](https://app.vsaex.visualstudio.com/go/profile), and sign-in with your work or school account.</span></span> <span data-ttu-id="df127-113">サインインした後、VSTS アカウントが一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="df127-113">After you sign in, your VSTS account is listed.</span></span> <span data-ttu-id="df127-114">次の例では、アカウントは**mandiaprojects.visualstudio.com**です。</span><span class="sxs-lookup"><span data-stu-id="df127-114">In the following example, the account is **mandiaprojects.visualstudio.com**.</span></span>  

    ![VSTS アカウント](../core/media/team-services-accounts.png)

    <span data-ttu-id="df127-116">アカウントを持っていない場合は、選択**新しいアカウントを作成**名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="df127-116">If you don’t have an account, select **Create new account**, and enter a name.</span></span> <span data-ttu-id="df127-117">コードを管理するため、希望個人間**Git または Team Foundation バージョン管理**です。</span><span class="sxs-lookup"><span data-stu-id="df127-117">To manage your code, choose your personal preference between **Git or Team Foundation Version Control**.</span></span> <span data-ttu-id="df127-118">完了したら、新しいアカウントを作成、およびのようなサイト*https://YourAccountName.visualstudio.com/MyFirstProject*が表示されます。</span><span class="sxs-lookup"><span data-stu-id="df127-118">When finished, your new account is created, and a site similar to *https://YourAccountName.visualstudio.com/MyFirstProject* opens:</span></span>  

    ![Git または TFS](../core/media/git-or-team-foundation.png)

2. <span data-ttu-id="df127-120">VSTS アカウントを開き (https://*YourAccountName*。 visualstudio.com)。</span><span class="sxs-lookup"><span data-stu-id="df127-120">Open your VSTS account (https://*YourAccountName*.visualstudio.com).</span></span> <span data-ttu-id="df127-121">右側の隅のアイコンを選択して選択、**セキュリティ**:</span><span class="sxs-lookup"><span data-stu-id="df127-121">Select your icon in the top right-side corner, and select **Security**:</span></span> 

    ![アカウントのセキュリティを開く](../core/media/vsts-account-security.png)

3. <span data-ttu-id="df127-123">**個人用アクセス トークン**が自動的に開きます。</span><span class="sxs-lookup"><span data-stu-id="df127-123">**Personal access tokens** automatically opens.</span></span> <span data-ttu-id="df127-124">既存のエージェントがあれば、選択し、確認**エージェント プール (読み取り、管理)**が選択されています。</span><span class="sxs-lookup"><span data-stu-id="df127-124">If you have an existing agent, select it, and confirm **Agent Pools (read, manage)** is selected:</span></span>

    ![エージェント プールの読み取りし、管理](../core/media/agent-pools-read-manage.png)

    > [!IMPORTANT]
    > <span data-ttu-id="df127-126">アクセス トークンを知る必要があります。</span><span class="sxs-lookup"><span data-stu-id="df127-126">You must know the access token.</span></span> <span data-ttu-id="df127-127">いない場合、しなかったに注意してください、任意の場所、取得できません。</span><span class="sxs-lookup"><span data-stu-id="df127-127">If you don’t, and didn’t note it anywhere, it cannot be retrieved.</span></span> <span data-ttu-id="df127-128">このような状況では、新しいエージェントを作成します。</span><span class="sxs-lookup"><span data-stu-id="df127-128">In this situation, create a new agent.</span></span> 

    <span data-ttu-id="df127-129">既存のエージェントを持っていない場合は、選択**追加**説明を入力、有効期限の日付を設定およびアカウントを選択します。</span><span class="sxs-lookup"><span data-stu-id="df127-129">If you don’t have an existing agent, select **Add**, enter a description, set the expiration date, and select your account.</span></span> <span data-ttu-id="df127-130">**スコープを選択した****エージェント プール (読み取り、管理)**:</span><span class="sxs-lookup"><span data-stu-id="df127-130">In **Selected scopes**, select **Agent Pools (read, manage)**:</span></span> 

    ![新しいエージェントを作成する - 読み取りし、管理](../core/media/vsts-new-build-agent.png)

    <span data-ttu-id="df127-132">選択**トークンを作成する**です。</span><span class="sxs-lookup"><span data-stu-id="df127-132">Select **Create Token**.</span></span> <span data-ttu-id="df127-133">**トークンの値に注意してください。必要があります将来の手順を実行します。**</span><span class="sxs-lookup"><span data-stu-id="df127-133">**Note the token value; you need in future steps.**</span></span>

4. <span data-ttu-id="df127-134">選択**コード**を選択して**Visual Studio での複製**:</span><span class="sxs-lookup"><span data-stu-id="df127-134">Select **Code**, and select **Clone in Visual Studio**:</span></span>  

    ![プロジェクトでコードを選択します.](../core/media/vsts-project-code.png)  

    ![Visual Studio での複製します。](../core/media/vsts-clone-in-visual-studio.png)

5. <span data-ttu-id="df127-137">Visual Studio が開きます。</span><span class="sxs-lookup"><span data-stu-id="df127-137">Visual Studio opens.</span></span> <span data-ttu-id="df127-138">Visual Studio 内では、BizTalk ソリューションを開きます。</span><span class="sxs-lookup"><span data-stu-id="df127-138">Within Visual Studio, open your BizTalk solution.</span></span> 

## <a name="install-the-build-agent"></a><span data-ttu-id="df127-139">ビルド エージェントをインストールします。</span><span class="sxs-lookup"><span data-stu-id="df127-139">Install the Build Agent</span></span>

<span data-ttu-id="df127-140">ビルド エージェントは、BizTalk 開発用コンピューターにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="df127-140">The build agent is installed on the BizTalk development computer.</span></span> 

1. <span data-ttu-id="df127-141">VSTS アカウントとは何か、プロジェクトを開くなどの*https://YourAccountName.visualstudio.com/MyFirstProject*です。</span><span class="sxs-lookup"><span data-stu-id="df127-141">Open your VSTS account and project, which is something like *https://YourAccountName.visualstudio.com/MyFirstProject*.</span></span> <span data-ttu-id="df127-142">設定アイコンを選択し、選択**エージェント キュー**:</span><span class="sxs-lookup"><span data-stu-id="df127-142">Select the settings icon, and select **Agent Queues**:</span></span>  

    ![設定 > エージェント キュー](../core/media/vsts-settings-agent-queues.png)

2. <span data-ttu-id="df127-144">選択、**既定**エージェント、および選択**エージェントのダウンロード**です。</span><span class="sxs-lookup"><span data-stu-id="df127-144">Select the **Default** agent, and select **Download Agent**.</span></span> <span data-ttu-id="df127-145">選択、**ダウンロード**ボタンをクリックし、ファイルを保存して、**ダウンロード**フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="df127-145">Select the **Download** button, and save the file to your **Downloads** folders.</span></span>

3. <span data-ttu-id="df127-146">インストールの手順は自動的に開きます。</span><span class="sxs-lookup"><span data-stu-id="df127-146">The install steps automatically open.</span></span> <span data-ttu-id="df127-147">詳細については、最新のこれらの手順に従います。</span><span class="sxs-lookup"><span data-stu-id="df127-147">Follow those steps for the most up-to-date details.</span></span> <span data-ttu-id="df127-148">次にいくつかのガイダンスを示します。</span><span class="sxs-lookup"><span data-stu-id="df127-148">Here is some guidance:</span></span> 

    1. <span data-ttu-id="df127-149">管理者として Windows PowerShell を開きます。</span><span class="sxs-lookup"><span data-stu-id="df127-149">Open Windows PowerShell as Administrator.</span></span>

    2. <span data-ttu-id="df127-150">エージェントを作成するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="df127-150">To create the agent, enter:</span></span> 

        ```powershell
        PS C:\> mkdir agent ; cd agent  

        PS C:\agent> Add-Type -AssemblyName System.IO.Compression.FileSystem ; [System.IO.Compression.ZipFile]::ExtractToDirectory("$HOME\Downloads\vsts-agent-win7-x64-2.124.0.zip", "$PWD")
        ```
    
        <span data-ttu-id="df127-151">Vsts エージェント ファイルのバージョンの変更。</span><span class="sxs-lookup"><span data-stu-id="df127-151">The vsts-agent file version changes.</span></span> <span data-ttu-id="df127-152">したがって固有の詳細について VSTS のインストール手順に従います。</span><span class="sxs-lookup"><span data-stu-id="df127-152">So follow the VSTS install steps for specific details.</span></span> <span data-ttu-id="df127-153">ヒットした後は、入力を返すには、プロンプトに数分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="df127-153">After you hit enter, it may take a couple of minutes for the prompt to return.</span></span> 

    3. <span data-ttu-id="df127-154">エージェントを構成するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="df127-154">To configure the agent, enter:</span></span> 

        ```powershell
        PS C:\agent> .\config.cmd
        ```

    4. <span data-ttu-id="df127-155">次の詳細を入力します。</span><span class="sxs-lookup"><span data-stu-id="df127-155">Enter the following details:</span></span>  
        
        | <span data-ttu-id="df127-156">プロパティ</span><span class="sxs-lookup"><span data-stu-id="df127-156">Property</span></span> | <span data-ttu-id="df127-157">値</span><span class="sxs-lookup"><span data-stu-id="df127-157">Value</span></span> |
        | --- | --- |
        | <span data-ttu-id="df127-158">[サーバー URL]</span><span class="sxs-lookup"><span data-stu-id="df127-158">Server URL</span></span>| <span data-ttu-id="df127-159">https://{your-account}.visualstudio.com</span><span class="sxs-lookup"><span data-stu-id="df127-159">https://{your-account}.visualstudio.com</span></span> |
        | <span data-ttu-id="df127-160">[認証の種類]</span><span class="sxs-lookup"><span data-stu-id="df127-160">Authentication Type</span></span> | <span data-ttu-id="df127-161">PAT</span><span class="sxs-lookup"><span data-stu-id="df127-161">PAT</span></span> |
        | <span data-ttu-id="df127-162">個人用アクセス トークン</span><span class="sxs-lookup"><span data-stu-id="df127-162">Personal access token</span></span> | <span data-ttu-id="df127-163">VSTS トークンを貼り付けます</span><span class="sxs-lookup"><span data-stu-id="df127-163">Paste your VSTS token</span></span> |
        | <span data-ttu-id="df127-164">エージェント プール</span><span class="sxs-lookup"><span data-stu-id="df127-164">Agent pool</span></span> | <span data-ttu-id="df127-165">既定値を入力します。</span><span class="sxs-lookup"><span data-stu-id="df127-165">Enter for the default</span></span> |
        | <span data-ttu-id="df127-166">エージェント名</span><span class="sxs-lookup"><span data-stu-id="df127-166">Agent name</span></span> | <span data-ttu-id="df127-167">既定値を入力します。</span><span class="sxs-lookup"><span data-stu-id="df127-167">Enter for the default</span></span> |
        | <span data-ttu-id="df127-168">[置換]</span><span class="sxs-lookup"><span data-stu-id="df127-168">Replace</span></span> | <span data-ttu-id="df127-169">*既存のエージェントがある場合のみ表示されます。*</span><span class="sxs-lookup"><span data-stu-id="df127-169">*Only displays if you have an existing agent*</span></span> |
        | <span data-ttu-id="df127-170">作業フォルダー</span><span class="sxs-lookup"><span data-stu-id="df127-170">Work folder</span></span> | <span data-ttu-id="df127-171">既定値を入力します。</span><span class="sxs-lookup"><span data-stu-id="df127-171">Enter for the default</span></span> |
        | <span data-ttu-id="df127-172">エージェントをサービスとして実行します。</span><span class="sxs-lookup"><span data-stu-id="df127-172">Run agent as a service</span></span> | <span data-ttu-id="df127-173">Y</span><span class="sxs-lookup"><span data-stu-id="df127-173">Y</span></span> |
        | <span data-ttu-id="df127-174">ユーザー アカウント</span><span class="sxs-lookup"><span data-stu-id="df127-174">User account</span></span> | <span data-ttu-id="df127-175">これかは、開発者が、アクセス許可の問題が発生した可能性があります。</span><span class="sxs-lookup"><span data-stu-id="df127-175">This is up to you, but you may run into a permissions issue.</span></span> <br/><br/><span data-ttu-id="df127-176">現在のログオン アカウント、ローカル管理者である入力を検討してください。</span><span class="sxs-lookup"><span data-stu-id="df127-176">Consider entering your current logged-on account, which is a local Admin.</span></span> |

    5. <span data-ttu-id="df127-177">完了したら、PowerShell ウィンドウは、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="df127-177">When finished, your PowerShell window looks like the following:</span></span>  
    
        ![エージェントのインストール](../core/media/vsts-agent-powershell-install.png)

4. <span data-ttu-id="df127-179">新しいサービスを表示する services.msc を開きます。</span><span class="sxs-lookup"><span data-stu-id="df127-179">Open services.msc to see the new service.</span></span> <span data-ttu-id="df127-180">実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="df127-180">It should be running:</span></span>  

    ![サービスが実行されています。](../core/media/vsts-service.png)

    <span data-ttu-id="df127-182">開始するには、サービスが失敗した場合は[削除し、再構成エージェント](https://docs.microsoft.com/vsts/build-release/actions/agents/v2-windows)詳細特権を持つアカウントを使用します。</span><span class="sxs-lookup"><span data-stu-id="df127-182">If the service fails to start, [remove and re-configure an agent](https://docs.microsoft.com/vsts/build-release/actions/agents/v2-windows) using an account with more privilages.</span></span>


## <a name="what-you-did"></a><span data-ttu-id="df127-183">どのような</span><span class="sxs-lookup"><span data-stu-id="df127-183">What you did</span></span>

<span data-ttu-id="df127-184">VSTS アカウントにサインインし、セキュリティ トークンを作成します。</span><span class="sxs-lookup"><span data-stu-id="df127-184">You signed into your VSTS account, and created a security token.</span></span> <span data-ttu-id="df127-185">このセキュリティ トークンが、パスワードのような VSTS プロジェクトに対するアクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="df127-185">This security token is like a password, and gives you access to your VSTS project.</span></span> <span data-ttu-id="df127-186">ようにすることを確認して、保存された 1 回のみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="df127-186">It's only displayed once, so be sure you saved it.</span></span> <span data-ttu-id="df127-187">Visual studio は、VSTS プロジェクトを複製して BizTalk 開発用コンピューターでサービスとして実行されているエージェントを作成します。</span><span class="sxs-lookup"><span data-stu-id="df127-187">You also cloned your VSTS project into Visual Studio, and created an agent that runs as a service on your BizTalk development computer.</span></span> <span data-ttu-id="df127-188">このエージェントは、セキュリティ トークンを使用します。</span><span class="sxs-lookup"><span data-stu-id="df127-188">This agent uses the security token.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="df127-189">次の手順</span><span class="sxs-lookup"><span data-stu-id="df127-189">Next steps</span></span>
[<span data-ttu-id="df127-190">手順 3: ビルドの作成し、定義のリリース</span><span class="sxs-lookup"><span data-stu-id="df127-190">Step 3: Create the build and release definitions</span></span>](feature-pack-add-build-release-definitions.md)  
[<span data-ttu-id="df127-191">環境のトークンと変数を構成します。</span><span class="sxs-lookup"><span data-stu-id="df127-191">Configure environmental tokens and variables</span></span>](configure-environmental-tokens-and-variables-for-automatic-deployment.md)