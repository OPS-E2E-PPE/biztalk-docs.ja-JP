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
# <a name="step-3-create-the-build-and-release-definition"></a>手順 3:ビルドとリリース定義を作成します。

ビルドとリリース定義のタスクが Visual Studio Team Services とおそらく VSTS 管理者が行う必要があります。ビルド定義は、git リポジトリ内でプロジェクトをビルドおよびリリース定義は、BizTalk Server 環境にデプロイします。 

## <a name="before-you-begin"></a>アンインストールの準備
完全な[手順 2 - 作成 VSTS トークンと、エージェントをインストール](feature-pack-create-vsts-token.md)します。

## <a name="add-the-build-tasks"></a>ビルド タスクを追加します。
1. プロジェクトで、次のように選択します。**ビルドとリリース**します。 [ビルド] タブを開きます。 作成、**新規**定義。

    ![新しいビルド定義](../core/media/vsts-new-definition.png)

2. 選択、**空**テンプレート、および選択**適用**:  

    ![空のテンプレートを選択します。](../core/media/vsts-emtpy-template.png)
 
3. 設定、**エージェント キュー**既定値にします。 

    ![既定のキューを選択します。](../core/media/vsts-select-agent-queue.png)

4. **フェーズ 1**、タスクを追加、選択**Visual Studio ビルド**、選び**追加**:

    ![VS のビルド タスクを追加します。](../core/media/vsts-add-visual-studio-task.png)

5. Visual Studio のビルド タスクだけに追加され、次のプロパティの設定をクリックします。  

    | プロパティ | を設定します。 |
    | --- | --- | 
    | 表示名 | *YourProjectName*ソリューションをビルド * *\*.sln | 
    | Visual Studio バージョン | Visual Studio 2015 | 
    | MSBuild アーキテクチャ | MSBuild x86 | 

6. **フェーズ 1**、タスクを追加、選択**ビルド成果物の発行**、選び**追加**: 

    ![VS のビルド タスクを追加します。](../core/media/vsts-add-publish-build-task.png)

7. 選択、**成果物の発行**タスク、および、推奨される入力**表示名**します。 **を発行するパス**を選択、 **.** ボタンをクリックし、アプリケーションのプロジェクト フォルダー (例: appProjectHelloWorld) を選択します。 **[OK]** を選択します。

8. **成果物名**必要なものにすることができます。 選択**保存**します。 

9. 移動して**トリガー**、設定、**トリガーの状態**に**有効**:  

    ![VS のビルド タスクを追加します。](../core/media/vsts-continuous-integration.png)

10. **保存 (&) キュー**ビルド定義をテストします。 キューを配置するときに、エージェント キューと独自のブランチを求められます。 選択、**既定**エージェント キュー、および独自のブランチを選択します。 選択**キュー**します。  

11. 新しいビルドが開始され、成功または失敗を確認することを選択することができます。 

## <a name="add-the-release-tasks"></a>リリース タスクを追加します。

ビルドが成功すると、リリース定義は、BizTalk Server にアプリケーションを展開します。 

1. 選択、**リリース**] タブで [**新しい定義**します。 

2. 選択、**空**テンプレート、および選択**適用**:

    ![空のテンプレートを追加します。](../core/media/vsts-empty-release-template.png)

3. 変更、**環境名**に**Dev**、または何でもを付けます。 

4. 選択**成果物を追加**プロジェクト、ビルド定義を選択し、選択、**追加**: 

5. 移動して、**タスク** タブで、新しいタスクを追加します。 

    ![リリース タスクを追加します。](../core/media/vsts-new-release-tasks.png)

6. 一覧から、結果をフィルターで、選択、 **BizTalk Server アプリケーションの展開**タスク、および選択**追加**:  

    ![BizTalk 展開のタスクを追加します。](../core/media/vsts-biztalk-application-deployment-task.png)

    場合**BizTalk Server アプリケーションの展開**ins't 一覧にインストールし[BizTalk アプリケーションのデプロイ](https://marketplace.visualstudio.com/items?itemName=ms-biztalk.deploy-biztalk-application)します。

7. 選択、**デプロイ**タスク、および値を入力します。 

    **操作名**:オプションがあります。   
        - **新しい BizTalk アプリケーションを作成する**:新しいアプリケーションをデプロイします。 アプリケーションが既に存在する場合に、現在のアプリケーション (完全停止) をアンインストールし、新しいアプリケーションをインストールします。 継続的インテグレーションを有効にするでは、リポジトリで更新されるときに、そのアプリケーションが自動的に再します。   
        - **既存の BizTalk アプリケーションを更新**:既に実行中のアプリケーションには、スキーマなどの変更を追加します。 アプリケーションの完全な再デプロイは必要ありません。  
        - **BizTalk Server アプリケーションをインストールする**:[アプリケーションをインストールする](../core/how-to-install-a-biztalk-application.md)、BizTalk 管理のコンピューター名、および展開パッケージのパスを入力します。  

     ![デプロイ操作](../core/media/vsts-deploy-operations.png)

    **アプリケーション名**:入力したテキストは、BizTalk 管理コンソールでアプリケーション名になります。 **いない**BizTalk アプリケーション 1 を入力します。

    **展開パッケージ**:アプリケーション プロジェクトに zip ファイルを選択し、選択**OK**します。 

8. 選択、**エージェント フェーズ**タスク。 選択、**既定**エージェント キュー。 **保存**変更します。

9. 選択**リリース** > **リリース作成**:  

    ![リリースでは、リリースの作成](../core/media/vsts-create-release.png)

10. 選択**キュー**します。 リリースのリンクをクリックして、状態を確認します。 失敗した場合、エラーが表示されます。 成功した場合は、アプリケーションが BizTalk 管理コンソールに追加されます。 

## <a name="what-you-did"></a>どのような

Vsts では、Git または Team Foundation バージョン管理が (自分で選択した) 内でアプリケーションを構築するビルド定義を作成します。 ソース管理内の変更を加えるし、変更が自動的に検出されると、それらをプッシュすることができます。 ビルドが完了すると、BizTalk Server は、BizTalk Server 管理コンソールに表示するアプリケーションをデプロイするリリース定義を作成します。 

## <a name="next-step"></a>次の手順
この段階で終了しました。 場合は、環境トークンを BizTalk XML バインド ファイル内で作成し、環境トークンと一致する VSTS 内の変数を作成します。 参照してください[環境トークンと変数を構成](configure-environmental-tokens-and-variables-for-automatic-deployment.md)詳細については、します。 
