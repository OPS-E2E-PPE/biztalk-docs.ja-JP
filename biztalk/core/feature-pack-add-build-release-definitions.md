---
title: "手順 3 - ビルドとリリース定義を作成 |Microsoft ドキュメント"
description: "Vsts、git または TFS リポジトリ内のプロジェクトをビルドし、BizTalk Server アプリケーションを配置するリリース定義を作成するビルド定義を作成します。"
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
ms.openlocfilehash: 5ce84071fbc105fd9faddd794792273aae2e76b9
ms.sourcegitcommit: f65e8ed2b8c18cded26b9d60868fb6a56bcc1205
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2017
---
# <a name="step-3-create-the-build-and-release-definition"></a>手順 3: ビルドを作成し、リリース定義

ビルドとリリース定義 Visual Studio Team Services となる作業は、おそらく VSTS 管理者が行う必要があります。ビルド定義が、git リポジトリ内で、プロジェクトをビルドし、リリース定義は、BizTalk Server 環境に展開します。 

## <a name="before-you-begin"></a>アンインストールの準備
完全な[エージェントをインストールして、手順 2 - 作成 VSTS トークン](feature-pack-create-vsts-token.md)です。

## <a name="add-the-build-tasks"></a>ビルド タスクを追加します。
1. プロジェクトで、次のように選択します。**ビルドとリリースの**します。 [ビルド] タブを開きます。 作成、**新規**定義。

    ![新しいビルド定義](../core/media/vsts-new-definition.png)

2. 選択、**空**テンプレート、および選択**適用**:  

    ![空のテンプレートを選択します。](../core/media/vsts-emtpy-template.png)
 
3. 設定、**エージェント キュー**既定値にします。 

    ![既定のキューを選択します。](../core/media/vsts-select-agent-queue.png)

4. **フェーズ 1**、タスクを追加、選択**Visual Studio ビルド**を選択して**追加**:

    ![VS ビルド タスクを追加します。](../core/media/vsts-add-visual-studio-task.png)

5. Visual Studio ビルド タスクだけに追加され、次のプロパティの設定をクリックします。  

    | プロパティ | を設定します。 |
    | --- | --- | 
    | 表示名 | *YourProjectName*ソリューションをビルド * *\*.sln | 
    | Visual Studio のバージョン | Visual Studio 2015 | 
    | MSBuild のアーキテクチャ | MSBuild x86 | 

6. **フェーズ 1**、タスクを追加、選択**ビルド成果物の発行**を選択して**追加**: 

    ![VS ビルド タスクを追加します。](../core/media/vsts-add-publish-build-task.png)

7. 選択、**成果物の発行**タスク、および優先入力**表示名**です。 **を発行するパス**、select、**しています.**ボタンをクリックし、アプリケーションのプロジェクト フォルダー (例: appProjectHelloWorld) を選択します。 **[OK]** を選択します。

8. **成果物名**任意に指定することができます。 選択**保存**です。 

9. 移動して**トリガー**、設定と、**状態のトリガー**に**有効**:  

    ![VS ビルド タスクを追加します。](../core/media/vsts-continuous-integration.png)

10. **保存 (&) キュー**ビルド定義をテストします。 キューに配置し、ときに、エージェント キューと、分岐を求められます。 選択、**既定**エージェント キュー、および自分の分岐を選択します。 選択**キュー**です。  

11. 新しいビルドを開始し、成功または失敗を確認することを選択できます。 

## <a name="add-the-release-tasks"></a>リリース タスクを追加します。

ビルドが成功した場合、リリース定義は、BizTalk Server にアプリケーションを展開します。 

1. 選択、**リリース**] タブで [**新しい定義**です。 

2. 選択、**空**テンプレート、および選択**適用**:

    ![空のテンプレートを追加します。](../core/media/vsts-empty-release-template.png)

3. 変更、**環境名**に**デベロッパー**、またはそれを呼び出すものです。 

4. 選択**追加の成果物**、プロジェクトのビルド定義を選択し、**追加**: 

5. 移動して、**タスク** タブで、新しいタスクを追加します。 

    ![リリース タスクを追加します。](../core/media/vsts-new-release-tasks.png)

6. リストから、結果をフィルター処理で、選択、 **BizTalk Server アプリケーションの展開**タスク、および選択**追加**:  

    ![BizTalk 展開のタスクを追加します。](../core/media/vsts-biztalk-application-deployment-task.png)

    場合**BizTalk Server アプリケーションの展開**ins't 一覧に表示し、インストールで[BizTalk アプリケーションの展開](https://marketplace.visualstudio.com/items?itemName=ms-biztalk.deploy-biztalk-application)です。

7. 選択、**展開**タスク、および値を入力します。 

    **操作名**: オプション: ***新しい BizTalk アプリケーションを作成する**: 新しいアプリケーションを展開します。 アプリケーションが既に存在する場合、その (完全に停止)、現在のアプリケーションをアンインストールし、新しいアプリケーションをインストールします。 継続的な統合が有効になっているでは、リポジトリで更新されるときに、そのアプリケーションが自動的に再です。 
        * **既存の BizTalk アプリケーションを更新して**: スキーマなどの変更を既に実行中のアプリケーションに追加します。 アプリケーションの完全再展開は必要ありません。
        * **BizTalk Server アプリケーションをインストール**:[アプリケーションをインストールする](../core/how-to-install-a-biztalk-application.md)、BizTalk 管理のコンピューター名、および展開パッケージのパスを入力するとします。

        ![Deploy operations](../core/media/vsts-deploy-operations.png)

    **アプリケーション名**: 入力したテキストが BizTalk 管理コンソールでアプリケーション名になります。 **いない**BizTalk アプリケーション 1 を入力します。

    **展開パッケージ**: アプリケーション プロジェクトに zip ファイルを選択し、選択**OK**です。 

8. 選択、**エージェント フェーズ**タスク。 選択、**既定**エージェント キュー。 **保存**変更します。

9. 選択**リリース** > **リリース作成**:  

    ![リリースでは、リリースを作成します。](../core/media/vsts-create-release.png)

10. 選択**キュー**です。 リリースのリンクをクリックして、状態を確認します。 失敗した場合、エラーが表示されます。 成功した場合は、アプリケーションが BizTalk 管理コンソールに追加されます。 

## <a name="what-you-did"></a>どのような

VSTS では、Git または Team Foundation バージョン管理 (指定した内容) 内で、アプリケーションを構築するビルド定義を作成します。 ソース コントロール内の変更を加えるし、変更が自動的に検出されると、プッシュすることができます。 ビルドが完了したら、BizTalk Server は、BizTalk Server 管理コンソールに表示するアプリケーションを展開するリリース定義を作成します。 

## <a name="next-step"></a>次の手順
この手順では、次の完了しています。 を使用する場合、BizTalk XML バインド ファイル内で環境のトークンを作成でき環境のトークンと一致する VSTS 内の変数を作成できます。 参照してください[環境トークンと変数を構成する](configure-environmental-tokens-and-variables-for-automatic-deployment.md)詳細については、します。 