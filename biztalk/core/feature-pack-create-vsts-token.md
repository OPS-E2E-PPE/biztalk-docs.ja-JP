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
# <a name="step-2-create-the-token--install-the-agent"></a>手順 2: トークンの作成し、エージェントのインストール

個人用アクセス トークン (PAT) は、Visual Studio Team Services で作成されます。 このトークンは、パスワードし、VSTS のビルド エージェントでの認証に使用します。 トークンが作成するときにのみ表示されます。 その後、表示されないできなくなります。 これを作成すると、保存できる場所に別のファイルに保存します。 

PAT の詳細については[VSTS と TFS の個人用アクセス トークンによるアクセスの認証](https://docs.microsoft.com/vsts/accounts/use-personal-access-tokens-to-authenticate)します。 

トークンを作成した後は、ビルド エージェントをインストールし、このトークンを使用するように構成します。 

## <a name="before-you-begin"></a>アンインストールの準備
完全な[手順 1 - アプリケーションの追加のプロジェクトと json の更新](feature-pack-add-application-project.md)します。

## <a name="sign-into-vsts-and-create-the-token"></a>VSTS にサインインし、トークンの作成
1. 移動して[ https://app.vsaex.visualstudio.com/go/profile ](https://app.vsaex.visualstudio.com/go/profile)、および職場または学校のアカウントでサインインします。 サインインした後、VSTS アカウントが表示されます。 次の例では、アカウントは**mandiaprojects.visualstudio.com**します。  

    ![VSTS アカウント](../core/media/team-services-accounts.png)

    アカウントを持っていない場合は、選択**新しいアカウントを作成する**名前を入力します。 コードを管理する選択間個人的な好み**Git または Team Foundation バージョン管理**します。 新しいアカウントを作成したらとのようなサイト *https://YourAccountName.visualstudio.com/MyFirstProject* が開きます。  

    ![Git または TFS](../core/media/git-or-team-foundation.png)

2. VSTS アカウントを開き (https://<em>YourAccountName</em>。 visualstudio.com)。 右側の隅で、アイコンを選択し、選択**セキュリティ**: 

    ![アカウントのセキュリティを開く](../core/media/vsts-account-security.png)

3. **個人用アクセス トークン**が自動的に開きます。 既存のエージェントがあれば、選択し、確認**エージェント プール (読み取り、管理)** が選択されています。

    ![エージェント プールの読み取りし、管理](../core/media/agent-pools-read-manage.png)

    > [!IMPORTANT]
    > アクセス トークンが必要です。 して任意の場所注記していない場合は取得できません。 このような状況では、新しいエージェントを作成します。 

    既存のエージェントを持っていない場合は、選択**追加**説明を入力します、有効期限の日付を設定およびアカウントを選択します。 **スコープを選択した**、**エージェント プール (読み取り、管理)**: 

    ![新しいエージェントを作成する - 読み取りし、管理](../core/media/vsts-new-build-agent.png)

    選択**トークン作成**です。 **トークンの値に注意してください。必要があります将来の手順を実行します。**

4. 選択**コード**、選び**Visual Studio で複製**:  

    ![プロジェクトでコードを選択します。](../core/media/vsts-project-code.png)  

    ![Visual Studio での複製します。](../core/media/vsts-clone-in-visual-studio.png)

5. Visual Studio を開きます。 Visual Studio で、BizTalk ソリューションを開きます。 

## <a name="install-the-build-agent"></a>ビルド エージェントをインストールします。

ビルド エージェントは、BizTalk 開発用コンピューターにインストールされます。 配置グループを使用する場合、ビルド エージェントを展開するすべての BizTalk server にインストールされます。 次の手順では、1 台のコンピューターにビルド エージェントをインストールする方法を説明します。 配置グループの使用に関する詳細については、次を参照してください。[配置グループ](https://docs.microsoft.com/vsts/build-release/concepts/definitions/release/deployment-groups/index)します。

1. VSTS アカウントとは何か、プロジェクトを開くなどの *https://YourAccountName.visualstudio.com/MyFirstProject* します。 設定アイコンを選択し、選択**エージェント キュー**:  

    ![設定 > エージェント キュー](../core/media/vsts-settings-agent-queues.png)

2. 選択、**既定**エージェント、および選択**エージェントのダウンロード**します。 選択、**ダウンロード**ボタンをクリックし、ファイルの保存、**ダウンロード**フォルダー。

3. インストールの手順は自動的に開きます。 詳細については、最新のこれらの手順に従います。 いくつかのガイダンスを次に示します。 

   1. Windows PowerShell を管理者として開きます。

   2. エージェントを作成するには、次のように入力します。 

       ```powershell
       PS C:\> mkdir agent ; cd agent  

       PS C:\agent> Add-Type -AssemblyName System.IO.Compression.FileSystem ; [System.IO.Compression.ZipFile]::ExtractToDirectory("$HOME\Downloads\vsts-agent-win7-x64-2.124.0.zip", "$PWD")
       ```

       Vsts エージェント ファイルのバージョンの変更。 したがって固有の詳細については、VSTS インストールの手順に従ってください。 ヒットした後は、入力を返すプロンプトの数分がかかる場合があります。 

   3. エージェントを構成するには、次のように入力します。 

       ```powershell
       PS C:\agent> .\config.cmd
       ```

   4. 次の詳細を入力します。  


      |        プロパティ        |                                                                      値                                                                       |
      |------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------|
      |       [サーバー URL]       |                                                     https://{your-account}.visualstudio.com                                                      |
      |  [認証の種類]   |                                                                       PAT                                                                        |
      | 個人用アクセス トークン  |                                                              VSTS トークンを貼り付ける                                                               |
      |       エージェント プール       |                                                              既定値を入力します。                                                               |
      |       エージェント名       |                                                              既定値を入力します。                                                               |
      |        [置換]         |                                                  *既存のエージェントがある場合のみ表示されます。*                                                   |
      |      作業フォルダー       |                                                              既定値を入力します。                                                               |
      | エージェントをサービスとして実行します。 |                                                                        Y                                                                         |
      |      ユーザー アカウント      | これは、開発者が、アクセス許可の問題に実行する可能性があります。 <br/><br/>現在ログオンしているアカウント、ローカル管理者である入力することを検討してください。 |


   5. 完了したら、PowerShell ウィンドウは次のようになります。  

       ![エージェントのインストール](../core/media/vsts-agent-powershell-install.png)

4. 新しいサービスを表示する services.msc を開きます。 実行する必要があります。  

    ![サービスが実行されています。](../core/media/vsts-service.png)

    開始するには、サービスが失敗した場合[を削除し、エージェントを再構成して](https://docs.microsoft.com/vsts/build-release/actions/agents/v2-windows)詳細特権を持つアカウントを使用します。


## <a name="what-you-did"></a>どのような

VSTS アカウントにサインインし、セキュリティ トークンを作成します。 このセキュリティ トークンは、パスワードのように、VSTS プロジェクトにアクセスできます。 のでことを確認する、保存、1 回のみ表示されます。 またに Visual Studio、VSTS プロジェクトを複製し、BizTalk 開発用コンピューターでサービスとして実行されているエージェントを作成します。 このエージェントは、セキュリティ トークンを使用します。 

## <a name="next-steps"></a>次のステップ
[手順 3: 作成、ビルドとリリース定義](feature-pack-add-build-release-definitions.md)  
[環境トークンと変数を構成します。](configure-environmental-tokens-and-variables-for-automatic-deployment.md)