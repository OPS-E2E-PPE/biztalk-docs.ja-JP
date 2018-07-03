---
title: 手順 2 - VSTS トークンを作成し、エージェントのインストール |Microsoft Docs
description: Visual Studio に VSTS のセキュリティのアクセス トークン、複製、VSTS プロジェクトを作成し、BizTalk Server プロジェクトの展開を自動化するビルド エージェントのインストール
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
ms.openlocfilehash: 1d26a218b6de83b1ab2e5a2dd46be215dcbb0f49
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979347"
---
# <a name="step-2-create-the-token--install-the-agent"></a><span data-ttu-id="07542-103">手順 2: トークンの作成し、エージェントのインストール</span><span class="sxs-lookup"><span data-stu-id="07542-103">Step 2: Create the token & install the agent</span></span>

<span data-ttu-id="07542-104">個人用アクセス トークン (PAT) は、Visual Studio Team Services で作成されます。</span><span class="sxs-lookup"><span data-stu-id="07542-104">A personal access token (PAT) is created in Visual Studio Team Services.</span></span> <span data-ttu-id="07542-105">このトークンは、パスワードし、VSTS のビルド エージェントでの認証に使用します。</span><span class="sxs-lookup"><span data-stu-id="07542-105">This token is your password, and is used by the VSTS build agent to authenticate.</span></span> <span data-ttu-id="07542-106">トークンが作成するときにのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="07542-106">The token is only displayed when you create it.</span></span> <span data-ttu-id="07542-107">その後、表示されないできなくなります。</span><span class="sxs-lookup"><span data-stu-id="07542-107">After that, it isn't displayed anymore.</span></span> <span data-ttu-id="07542-108">これを作成すると、保存できる場所に別のファイルに保存します。</span><span class="sxs-lookup"><span data-stu-id="07542-108">So once you create it, save it to another file in a remember-able location.</span></span> 

<span data-ttu-id="07542-109">PAT の詳細については[VSTS と TFS の個人用アクセス トークンによるアクセスの認証](https://docs.microsoft.com/vsts/accounts/use-personal-access-tokens-to-authenticate)します。</span><span class="sxs-lookup"><span data-stu-id="07542-109">More info on PAT at [Authenticate access with personal access tokens for VSTS and TFS](https://docs.microsoft.com/vsts/accounts/use-personal-access-tokens-to-authenticate).</span></span> 

<span data-ttu-id="07542-110">トークンを作成した後は、ビルド エージェントをインストールし、このトークンを使用するように構成します。</span><span class="sxs-lookup"><span data-stu-id="07542-110">After you create the token, you install the build agent, and configure it to use this token.</span></span> 

## <a name="before-you-begin"></a><span data-ttu-id="07542-111">アンインストールの準備</span><span class="sxs-lookup"><span data-stu-id="07542-111">Before you begin</span></span>
<span data-ttu-id="07542-112">完全な[手順 1 - アプリケーションの追加のプロジェクトと json の更新](feature-pack-add-application-project.md)します。</span><span class="sxs-lookup"><span data-stu-id="07542-112">Complete [Step 1 - Add Application project and update json](feature-pack-add-application-project.md).</span></span>

## <a name="sign-into-vsts-and-create-the-token"></a><span data-ttu-id="07542-113">VSTS にサインインし、トークンの作成</span><span class="sxs-lookup"><span data-stu-id="07542-113">Sign into VSTS, and create the token</span></span>
1. <span data-ttu-id="07542-114">移動して[ https://app.vsaex.visualstudio.com/go/profile ](https://app.vsaex.visualstudio.com/go/profile)、および職場または学校のアカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="07542-114">Go to [https://app.vsaex.visualstudio.com/go/profile](https://app.vsaex.visualstudio.com/go/profile), and sign-in with your work or school account.</span></span> <span data-ttu-id="07542-115">サインインした後、VSTS アカウントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="07542-115">After you sign in, your VSTS account is listed.</span></span> <span data-ttu-id="07542-116">次の例では、アカウントは**mandiaprojects.visualstudio.com**します。</span><span class="sxs-lookup"><span data-stu-id="07542-116">In the following example, the account is **mandiaprojects.visualstudio.com**.</span></span>  

    ![VSTS アカウント](../core/media/team-services-accounts.png)

    <span data-ttu-id="07542-118">アカウントを持っていない場合は、選択**新しいアカウントを作成する**名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="07542-118">If you don’t have an account, select **Create new account**, and enter a name.</span></span> <span data-ttu-id="07542-119">コードを管理する選択間個人的な好み**Git または Team Foundation バージョン管理**します。</span><span class="sxs-lookup"><span data-stu-id="07542-119">To manage your code, choose your personal preference between **Git or Team Foundation Version Control**.</span></span> <span data-ttu-id="07542-120">新しいアカウントを作成したらとのようなサイト*https://YourAccountName.visualstudio.com/MyFirstProject*が開きます。</span><span class="sxs-lookup"><span data-stu-id="07542-120">When finished, your new account is created, and a site similar to *https://YourAccountName.visualstudio.com/MyFirstProject* opens:</span></span>  

    ![Git または TFS](../core/media/git-or-team-foundation.png)

2. <span data-ttu-id="07542-122">VSTS アカウントを開き (https://<em>YourAccountName</em>。 visualstudio.com)。</span><span class="sxs-lookup"><span data-stu-id="07542-122">Open your VSTS account (https://<em>YourAccountName</em>.visualstudio.com).</span></span> <span data-ttu-id="07542-123">右側の隅で、アイコンを選択し、選択**セキュリティ**:</span><span class="sxs-lookup"><span data-stu-id="07542-123">Select your icon in the top right-side corner, and select **Security**:</span></span> 

    ![アカウントのセキュリティを開く](../core/media/vsts-account-security.png)

3. <span data-ttu-id="07542-125">**個人用アクセス トークン**が自動的に開きます。</span><span class="sxs-lookup"><span data-stu-id="07542-125">**Personal access tokens** automatically opens.</span></span> <span data-ttu-id="07542-126">既存のエージェントがあれば、選択し、確認**エージェント プール (読み取り、管理)** が選択されています。</span><span class="sxs-lookup"><span data-stu-id="07542-126">If you have an existing agent, select it, and confirm **Agent Pools (read, manage)** is selected:</span></span>

    ![エージェント プールの読み取りし、管理](../core/media/agent-pools-read-manage.png)

    > [!IMPORTANT]
    > <span data-ttu-id="07542-128">アクセス トークンが必要です。</span><span class="sxs-lookup"><span data-stu-id="07542-128">You must know the access token.</span></span> <span data-ttu-id="07542-129">して任意の場所注記していない場合は取得できません。</span><span class="sxs-lookup"><span data-stu-id="07542-129">If you don’t, and didn’t note it anywhere, it cannot be retrieved.</span></span> <span data-ttu-id="07542-130">このような状況では、新しいエージェントを作成します。</span><span class="sxs-lookup"><span data-stu-id="07542-130">In this situation, create a new agent.</span></span> 

    <span data-ttu-id="07542-131">既存のエージェントを持っていない場合は、選択**追加**説明を入力します、有効期限の日付を設定およびアカウントを選択します。</span><span class="sxs-lookup"><span data-stu-id="07542-131">If you don’t have an existing agent, select **Add**, enter a description, set the expiration date, and select your account.</span></span> <span data-ttu-id="07542-132">**スコープを選択した**、**エージェント プール (読み取り、管理)**:</span><span class="sxs-lookup"><span data-stu-id="07542-132">In **Selected scopes**, select **Agent Pools (read, manage)**:</span></span> 

    ![新しいエージェントを作成する - 読み取りし、管理](../core/media/vsts-new-build-agent.png)

    <span data-ttu-id="07542-134">選択**トークン作成**です。</span><span class="sxs-lookup"><span data-stu-id="07542-134">Select **Create Token**.</span></span> <span data-ttu-id="07542-135">**トークンの値に注意してください。必要があります将来の手順を実行します。**</span><span class="sxs-lookup"><span data-stu-id="07542-135">**Note the token value; you need in future steps.**</span></span>

4. <span data-ttu-id="07542-136">選択**コード**、選び**Visual Studio で複製**:</span><span class="sxs-lookup"><span data-stu-id="07542-136">Select **Code**, and select **Clone in Visual Studio**:</span></span>  

    ![プロジェクトでコードを選択します。](../core/media/vsts-project-code.png)  

    ![Visual Studio での複製します。](../core/media/vsts-clone-in-visual-studio.png)

5. <span data-ttu-id="07542-139">Visual Studio を開きます。</span><span class="sxs-lookup"><span data-stu-id="07542-139">Visual Studio opens.</span></span> <span data-ttu-id="07542-140">Visual Studio で、BizTalk ソリューションを開きます。</span><span class="sxs-lookup"><span data-stu-id="07542-140">Within Visual Studio, open your BizTalk solution.</span></span> 

## <a name="install-the-build-agent"></a><span data-ttu-id="07542-141">ビルド エージェントをインストールします。</span><span class="sxs-lookup"><span data-stu-id="07542-141">Install the Build Agent</span></span>

<span data-ttu-id="07542-142">ビルド エージェントは、BizTalk 開発用コンピューターにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="07542-142">The build agent is installed on the BizTalk development computer.</span></span> <span data-ttu-id="07542-143">配置グループを使用する場合、ビルド エージェントを展開するすべての BizTalk server にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="07542-143">If using deployment groups, the build agent is installed on all the BizTalk servers you want to deploy to.</span></span> <span data-ttu-id="07542-144">次の手順では、1 台のコンピューターにビルド エージェントをインストールする方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="07542-144">The following steps show you how to install the build agent on a single computer.</span></span> <span data-ttu-id="07542-145">配置グループの使用に関する詳細については、次を参照してください。[配置グループ](https://docs.microsoft.com/vsts/build-release/concepts/definitions/release/deployment-groups/index)します。</span><span class="sxs-lookup"><span data-stu-id="07542-145">For details on using deployment groups, see [Deployment groups](https://docs.microsoft.com/vsts/build-release/concepts/definitions/release/deployment-groups/index).</span></span>

1. <span data-ttu-id="07542-146">VSTS アカウントとは何か、プロジェクトを開くなどの *https://YourAccountName.visualstudio.com/MyFirstProject*します。</span><span class="sxs-lookup"><span data-stu-id="07542-146">Open your VSTS account and project, which is something like *https://YourAccountName.visualstudio.com/MyFirstProject*.</span></span> <span data-ttu-id="07542-147">設定アイコンを選択し、選択**エージェント キュー**:</span><span class="sxs-lookup"><span data-stu-id="07542-147">Select the settings icon, and select **Agent Queues**:</span></span>  

    ![設定 > エージェント キュー](../core/media/vsts-settings-agent-queues.png)

2. <span data-ttu-id="07542-149">選択、**既定**エージェント、および選択**エージェントのダウンロード**します。</span><span class="sxs-lookup"><span data-stu-id="07542-149">Select the **Default** agent, and select **Download Agent**.</span></span> <span data-ttu-id="07542-150">選択、**ダウンロード**ボタンをクリックし、ファイルの保存、**ダウンロード**フォルダー。</span><span class="sxs-lookup"><span data-stu-id="07542-150">Select the **Download** button, and save the file to your **Downloads** folders.</span></span>

3. <span data-ttu-id="07542-151">インストールの手順は自動的に開きます。</span><span class="sxs-lookup"><span data-stu-id="07542-151">The install steps automatically open.</span></span> <span data-ttu-id="07542-152">詳細については、最新のこれらの手順に従います。</span><span class="sxs-lookup"><span data-stu-id="07542-152">Follow those steps for the most up-to-date details.</span></span> <span data-ttu-id="07542-153">いくつかのガイダンスを次に示します。</span><span class="sxs-lookup"><span data-stu-id="07542-153">Here is some guidance:</span></span> 

   1. <span data-ttu-id="07542-154">Windows PowerShell を管理者として開きます。</span><span class="sxs-lookup"><span data-stu-id="07542-154">Open Windows PowerShell as Administrator.</span></span>

   2. <span data-ttu-id="07542-155">エージェントを作成するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="07542-155">To create the agent, enter:</span></span> 

       ```powershell
       PS C:\> mkdir agent ; cd agent  

       PS C:\agent> Add-Type -AssemblyName System.IO.Compression.FileSystem ; [System.IO.Compression.ZipFile]::ExtractToDirectory("$HOME\Downloads\vsts-agent-win7-x64-2.124.0.zip", "$PWD")
       ```

       <span data-ttu-id="07542-156">Vsts エージェント ファイルのバージョンの変更。</span><span class="sxs-lookup"><span data-stu-id="07542-156">The vsts-agent file version changes.</span></span> <span data-ttu-id="07542-157">したがって固有の詳細については、VSTS インストールの手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="07542-157">So follow the VSTS install steps for specific details.</span></span> <span data-ttu-id="07542-158">ヒットした後は、入力を返すプロンプトの数分がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="07542-158">After you hit enter, it may take a couple of minutes for the prompt to return.</span></span> 

   3. <span data-ttu-id="07542-159">エージェントを構成するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="07542-159">To configure the agent, enter:</span></span> 

       ```powershell
       PS C:\agent> .\config.cmd
       ```

   4. <span data-ttu-id="07542-160">次の詳細を入力します。</span><span class="sxs-lookup"><span data-stu-id="07542-160">Enter the following details:</span></span>  


      |        <span data-ttu-id="07542-161">プロパティ</span><span class="sxs-lookup"><span data-stu-id="07542-161">Property</span></span>        |                                                                      <span data-ttu-id="07542-162">値</span><span class="sxs-lookup"><span data-stu-id="07542-162">Value</span></span>                                                                       |
      |------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------|
      |       <span data-ttu-id="07542-163">[サーバー URL]</span><span class="sxs-lookup"><span data-stu-id="07542-163">Server URL</span></span>       |                                                     <span data-ttu-id="07542-164">https://{your-account}.visualstudio.com</span><span class="sxs-lookup"><span data-stu-id="07542-164">https://{your-account}.visualstudio.com</span></span>                                                      |
      |  <span data-ttu-id="07542-165">[認証の種類]</span><span class="sxs-lookup"><span data-stu-id="07542-165">Authentication Type</span></span>   |                                                                       <span data-ttu-id="07542-166">PAT</span><span class="sxs-lookup"><span data-stu-id="07542-166">PAT</span></span>                                                                        |
      | <span data-ttu-id="07542-167">個人用アクセス トークン</span><span class="sxs-lookup"><span data-stu-id="07542-167">Personal access token</span></span>  |                                                              <span data-ttu-id="07542-168">VSTS トークンを貼り付ける</span><span class="sxs-lookup"><span data-stu-id="07542-168">Paste your VSTS token</span></span>                                                               |
      |       <span data-ttu-id="07542-169">エージェント プール</span><span class="sxs-lookup"><span data-stu-id="07542-169">Agent pool</span></span>       |                                                              <span data-ttu-id="07542-170">既定値を入力します。</span><span class="sxs-lookup"><span data-stu-id="07542-170">Enter for the default</span></span>                                                               |
      |       <span data-ttu-id="07542-171">エージェント名</span><span class="sxs-lookup"><span data-stu-id="07542-171">Agent name</span></span>       |                                                              <span data-ttu-id="07542-172">既定値を入力します。</span><span class="sxs-lookup"><span data-stu-id="07542-172">Enter for the default</span></span>                                                               |
      |        <span data-ttu-id="07542-173">[置換]</span><span class="sxs-lookup"><span data-stu-id="07542-173">Replace</span></span>         |                                                  <span data-ttu-id="07542-174">*既存のエージェントがある場合のみ表示されます。*</span><span class="sxs-lookup"><span data-stu-id="07542-174">*Only displays if you have an existing agent*</span></span>                                                   |
      |      <span data-ttu-id="07542-175">作業フォルダー</span><span class="sxs-lookup"><span data-stu-id="07542-175">Work folder</span></span>       |                                                              <span data-ttu-id="07542-176">既定値を入力します。</span><span class="sxs-lookup"><span data-stu-id="07542-176">Enter for the default</span></span>                                                               |
      | <span data-ttu-id="07542-177">エージェントをサービスとして実行します。</span><span class="sxs-lookup"><span data-stu-id="07542-177">Run agent as a service</span></span> |                                                                        <span data-ttu-id="07542-178">Y</span><span class="sxs-lookup"><span data-stu-id="07542-178">Y</span></span>                                                                         |
      |      <span data-ttu-id="07542-179">ユーザー アカウント</span><span class="sxs-lookup"><span data-stu-id="07542-179">User account</span></span>      | <span data-ttu-id="07542-180">これは、開発者が、アクセス許可の問題に実行する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="07542-180">This is up to you, but you may run into a permissions issue.</span></span> <br/><br/><span data-ttu-id="07542-181">現在ログオンしているアカウント、ローカル管理者である入力することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="07542-181">Consider entering your current logged-on account, which is a local Admin.</span></span> |


   5. <span data-ttu-id="07542-182">完了したら、PowerShell ウィンドウは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="07542-182">When finished, your PowerShell window looks like the following:</span></span>  

       ![エージェントのインストール](../core/media/vsts-agent-powershell-install.png)

4. <span data-ttu-id="07542-184">新しいサービスを表示する services.msc を開きます。</span><span class="sxs-lookup"><span data-stu-id="07542-184">Open services.msc to see the new service.</span></span> <span data-ttu-id="07542-185">実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="07542-185">It should be running:</span></span>  

    ![サービスが実行されています。](../core/media/vsts-service.png)

    <span data-ttu-id="07542-187">開始するには、サービスが失敗した場合[を削除し、エージェントを再構成して](https://docs.microsoft.com/vsts/build-release/actions/agents/v2-windows)詳細特権を持つアカウントを使用します。</span><span class="sxs-lookup"><span data-stu-id="07542-187">If the service fails to start, [remove and re-configure an agent](https://docs.microsoft.com/vsts/build-release/actions/agents/v2-windows) using an account with more privilages.</span></span>


## <a name="what-you-did"></a><span data-ttu-id="07542-188">どのような</span><span class="sxs-lookup"><span data-stu-id="07542-188">What you did</span></span>

<span data-ttu-id="07542-189">VSTS アカウントにサインインし、セキュリティ トークンを作成します。</span><span class="sxs-lookup"><span data-stu-id="07542-189">You signed into your VSTS account, and created a security token.</span></span> <span data-ttu-id="07542-190">このセキュリティ トークンは、パスワードのように、VSTS プロジェクトにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="07542-190">This security token is like a password, and gives you access to your VSTS project.</span></span> <span data-ttu-id="07542-191">のでことを確認する、保存、1 回のみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="07542-191">It's only displayed once, so be sure you saved it.</span></span> <span data-ttu-id="07542-192">またに Visual Studio、VSTS プロジェクトを複製し、BizTalk 開発用コンピューターでサービスとして実行されているエージェントを作成します。</span><span class="sxs-lookup"><span data-stu-id="07542-192">You also cloned your VSTS project into Visual Studio, and created an agent that runs as a service on your BizTalk development computer.</span></span> <span data-ttu-id="07542-193">このエージェントは、セキュリティ トークンを使用します。</span><span class="sxs-lookup"><span data-stu-id="07542-193">This agent uses the security token.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="07542-194">次のステップ</span><span class="sxs-lookup"><span data-stu-id="07542-194">Next steps</span></span>
[<span data-ttu-id="07542-195">手順 3: 作成、ビルドとリリース定義</span><span class="sxs-lookup"><span data-stu-id="07542-195">Step 3: Create the build and release definitions</span></span>](feature-pack-add-build-release-definitions.md)  
[<span data-ttu-id="07542-196">環境トークンと変数を構成します。</span><span class="sxs-lookup"><span data-stu-id="07542-196">Configure environmental tokens and variables</span></span>](configure-environmental-tokens-and-variables-for-automatic-deployment.md)