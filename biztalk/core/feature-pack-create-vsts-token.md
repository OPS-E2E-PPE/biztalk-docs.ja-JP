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
# <a name="step-2-create-the-token--install-the-agent"></a>手順 2: トークンを作成して (&)、エージェントのインストール

個人用アクセス トークン (PAT) は、Visual Studio Team Services で作成されます。 このトークンは、パスワードを指定するために、され、認証に VSTS ビルド エージェントによって使用されます。 トークンが作成するときにのみ表示されます。 その後、それが表示されていないされなくなります。 これを作成すると、別のファイルを保存できる場所に保存します。 

PAT について詳しくは[VSTS と TFS の個人用アクセス トークンによるアクセスの認証](https://docs.microsoft.com/vsts/accounts/use-personal-access-tokens-to-authenticate)です。 

トークンを作成した後は、ビルド エージェントをインストールして、このトークンを使用するように構成します。 

## <a name="before-you-begin"></a>アンインストールの準備
完全な[ステップ 1 - 追加のアプリケーション プロジェクトと json を更新](feature-pack-add-application-project.md)です。

## <a name="sign-into-vsts-and-create-the-token"></a>VSTS にサインインし、トークンの作成
1. 移動して[https://app.vsaex.visualstudio.com/go/profile](https://app.vsaex.visualstudio.com/go/profile)、および職場または学校のアカウントでサインインします。 サインインした後、VSTS アカウントが一覧表示します。 次の例では、アカウントは**mandiaprojects.visualstudio.com**です。  

    ![VSTS アカウント](../core/media/team-services-accounts.png)

    アカウントを持っていない場合は、選択**新しいアカウントを作成**名前を入力します。 コードを管理するため、希望個人間**Git または Team Foundation バージョン管理**です。 完了したら、新しいアカウントを作成、およびのようなサイト*https://YourAccountName.visualstudio.com/MyFirstProject*が表示されます。  

    ![Git または TFS](../core/media/git-or-team-foundation.png)

2. VSTS アカウントを開き (https://*YourAccountName*。 visualstudio.com)。 右側の隅のアイコンを選択して選択、**セキュリティ**: 

    ![アカウントのセキュリティを開く](../core/media/vsts-account-security.png)

3. **個人用アクセス トークン**が自動的に開きます。 既存のエージェントがあれば、選択し、確認**エージェント プール (読み取り、管理)**が選択されています。

    ![エージェント プールの読み取りし、管理](../core/media/agent-pools-read-manage.png)

    > [!IMPORTANT]
    > アクセス トークンを知る必要があります。 いない場合、しなかったに注意してください、任意の場所、取得できません。 このような状況では、新しいエージェントを作成します。 

    既存のエージェントを持っていない場合は、選択**追加**説明を入力、有効期限の日付を設定およびアカウントを選択します。 **スコープを選択した****エージェント プール (読み取り、管理)**: 

    ![新しいエージェントを作成する - 読み取りし、管理](../core/media/vsts-new-build-agent.png)

    選択**トークンを作成する**です。 **トークンの値に注意してください。必要があります将来の手順を実行します。**

4. 選択**コード**を選択して**Visual Studio での複製**:  

    ![プロジェクトでコードを選択します.](../core/media/vsts-project-code.png)  

    ![Visual Studio での複製します。](../core/media/vsts-clone-in-visual-studio.png)

5. Visual Studio が開きます。 Visual Studio 内では、BizTalk ソリューションを開きます。 

## <a name="install-the-build-agent"></a>ビルド エージェントをインストールします。

ビルド エージェントは、BizTalk 開発用コンピューターにインストールされます。 展開グループを使用する場合を展開するすべての BizTalk server でビルド エージェントがインストールされています。 次の手順では、1 台のコンピューターにビルド エージェントをインストールする方法を示します。 展開グループの使用に関する詳細については、「[展開グループ](https://docs.microsoft.com/vsts/build-release/concepts/definitions/release/deployment-groups/index)です。

1. VSTS アカウントとは何か、プロジェクトを開くなどの*https://YourAccountName.visualstudio.com/MyFirstProject*です。 設定アイコンを選択し、選択**エージェント キュー**:  

    ![設定 > エージェント キュー](../core/media/vsts-settings-agent-queues.png)

2. 選択、**既定**エージェント、および選択**エージェントのダウンロード**です。 選択、**ダウンロード**ボタンをクリックし、ファイルを保存して、**ダウンロード**フォルダーです。

3. インストールの手順は自動的に開きます。 詳細については、最新のこれらの手順に従います。 次にいくつかのガイダンスを示します。 

    1. 管理者として Windows PowerShell を開きます。

    2. エージェントを作成するには、次のように入力します。 

        ```powershell
        PS C:\> mkdir agent ; cd agent  

        PS C:\agent> Add-Type -AssemblyName System.IO.Compression.FileSystem ; [System.IO.Compression.ZipFile]::ExtractToDirectory("$HOME\Downloads\vsts-agent-win7-x64-2.124.0.zip", "$PWD")
        ```
    
        Vsts エージェント ファイルのバージョンの変更。 したがって固有の詳細について VSTS のインストール手順に従います。 ヒットした後は、入力を返すには、プロンプトに数分かかる場合があります。 

    3. エージェントを構成するには、次のように入力します。 

        ```powershell
        PS C:\agent> .\config.cmd
        ```

    4. 次の詳細を入力します。  
        
        | プロパティ | 値 |
        | --- | --- |
        | [サーバー URL]| https://{your-account}.visualstudio.com |
        | [認証の種類] | PAT |
        | 個人用アクセス トークン | VSTS トークンを貼り付けます |
        | エージェント プール | 既定値を入力します。 |
        | エージェント名 | 既定値を入力します。 |
        | [置換] | *既存のエージェントがある場合のみ表示されます。* |
        | 作業フォルダー | 既定値を入力します。 |
        | エージェントをサービスとして実行します。 | Y |
        | ユーザー アカウント | これかは、開発者が、アクセス許可の問題が発生した可能性があります。 <br/><br/>現在のログオン アカウント、ローカル管理者である入力を検討してください。 |

    5. 完了したら、PowerShell ウィンドウは、次のようになります。  
    
        ![エージェントのインストール](../core/media/vsts-agent-powershell-install.png)

4. 新しいサービスを表示する services.msc を開きます。 実行する必要があります。  

    ![サービスが実行されています。](../core/media/vsts-service.png)

    開始するには、サービスが失敗した場合は[削除し、再構成エージェント](https://docs.microsoft.com/vsts/build-release/actions/agents/v2-windows)詳細特権を持つアカウントを使用します。


## <a name="what-you-did"></a>どのような

VSTS アカウントにサインインし、セキュリティ トークンを作成します。 このセキュリティ トークンが、パスワードのような VSTS プロジェクトに対するアクセスを提供します。 ようにすることを確認して、保存された 1 回のみ表示されます。 Visual studio は、VSTS プロジェクトを複製して BizTalk 開発用コンピューターでサービスとして実行されているエージェントを作成します。 このエージェントは、セキュリティ トークンを使用します。 

## <a name="next-steps"></a>次の手順
[手順 3: ビルドの作成し、定義のリリース](feature-pack-add-build-release-definitions.md)  
[環境のトークンと変数を構成します。](configure-environmental-tokens-and-variables-for-automatic-deployment.md)