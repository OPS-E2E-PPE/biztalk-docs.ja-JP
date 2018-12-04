---
title: 手順 1 -、application/json プロジェクトと更新プログラムの追加 |Microsoft Docs
description: Visual Studio で、BizTalk Server アプリケーション プロジェクトを追加して、Dll、バインド ファイル、アプリケーションの Visual Studio Team Services の配置シーケンスと BizTalkServerInventory.json ファイルを更新
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
ms.openlocfilehash: e0230d0b280be412e3138ffbafd83d3810cf1163
ms.sourcegitcommit: be6273d612669adfbb9dc9208aaae0a8437d4017
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/04/2018
ms.locfileid: "52826362"
---
# <a name="step-1-add-the-biztalk-server-application-project-in-visual-studio"></a>手順 1: Visual Studio での BizTalk Server アプリケーション プロジェクトを追加します。

Visual Studio Team Services を使用してアプリケーションをビルドすると、新しい BizTalk プロジェクト ファイルが作成 – .btaproj。 この新しいプロジェクトでは、すべての BizTalk アプリケーションを構築し、VSTS のビルドを使用してデプロイを機能をリリースを保持します。 

BizTalk アプリケーションのプロジェクトが含まれています、`BizTalkServerInventory.json`ファイル。 このファイルで、BizTalk アセンブリを追加、BizTalk アプリケーションのバインド ファイルを追加および展開シーケンスを設定します。 

## <a name="before-you-begin"></a>アンインストールの準備

* 次の手順では、既存の BizTalk プロジェクトがあるとします。 HelloWorld SDK サンプルを使用するそうでない場合 (\Program Files (x86) \Microsoft BizTalk Server *yourVersion*\SDK\Samples\Orchestrations\HelloWorld)。 
* 準備ができて、BizTalk プロジェクトに XML バインド ファイルにパスがあります。 
* VSTS アカウント、コレクション、およびチーム プロジェクトの詳細を確認します。
* 複製リポジトリを操作など、git の概念を理解します。 
* 必ず[Feature Pack 2](https://aka.ms/bts2016fp2)がインストールされています。

## <a name="add-the-application-project"></a>アプリケーション プロジェクトを追加します。

1. BizTalk Server では、Visual Studio でソリューション (ProjectName.sln) を開きます。 Visual Studio Blend は選択しないでください。

2. ソリューション エクスプ ローラーで、プロジェクトを右クリックし、選択**ビルド**します。 ビルドが成功したことを確認します。 プロジェクトを右クリックして**デプロイ**します。 デプロイが成功するとしてください。

3. ソリューションを右クリックして**追加**、選び**新しいプロジェクトの追加**します。

4. 選択、 **BizTalk プロジェクト**] タブで [ **.NET Framework 4.6.1**クリックし、ドロップダウン リストから**アプリケーション用の BizTalk Server プロジェクト**します。 名前 (例: appProjectHelloWorld) を入力し、選択**OK**:  

    ![アプリケーション プロジェクトを追加します。](../core/media/add-application-project.png)

5. ソリューション エクスプ ローラーで、新しく追加したアプリケーション プロジェクト (.btaproj) を右クリックし、選択 **追加** **参照** です。 展開、**プロジェクト**タブをクリックし、BizTalk プロジェクト (プロジェクトで VSTS を使用してデプロイする) を確認します。 **[OK]** を選択します。  
    追加されると、展開**参照**追加したばかりのアプリケーション プロジェクト (例: appProjectHelloWorld) を BizTalk プロジェクトを参照してください。 

6. ソリューション エクスプ ローラーで、アプリケーション プロジェクト (.btaproj) を右クリックし、選択 **追加** **既存項目の** と **追加** バインディングは、XML ファイルです。

7. Binding.xml のプロパティを開き、設定**出力ディレクトリにコピー**に**常にコピー**します。 **保存**変更。  

    ![バインド ファイルのプロパティ](../core/media/xml-binding-file-properties.png)

8. 任意。 新しく追加されたアプリケーション プロジェクトを右クリックして**プロパティ**します。 カスタマイズ、**アプリケーション名**BizTalk 管理コンソールに表示します。  

    ![アプリケーション名](../core/media/application-project-name.png)

## <a name="configure-the-json-template"></a>JSON テンプレートを構成します。

1. Visual Studio で、アプリケーション プロジェクト (.btaproj) で開く、`BizTalkServerInventory.json`ファイル。 

2. テンプレートには、次のセクションが含まれています。 

    | | |
    |---|---|
    |BizTalkAssemblies | アプリケーションで使用されるアセンブリ |
    |BindingFiles | バインド ファイルを参照します。|
    |DeploymentSequence | インストールする要素のシーケンス|
    
    サンプル テンプレート: 
    
    ![FP1 Json テンプレート イメージ 1](../core/media/fp1-json-template-image-1.png)

    > [!IMPORTANT]
    > によっては、ソリューションの複雑さ、ビルドに必要な要素は、この JSON テンプレート ファイルで参照する必要があります。

3. `BizTalkAssemblies`、BizTalk プロジェクトで使用するアセンブリを追加します。 

    ```
    "BizTalkAssemblies": [
        {
            "Name": "AssemblyName",
            "Path": "PathToAssembly
        }
    ]
    ```

4. `BindingsFiles`、BizTalk プロジェクトのバインド ファイルを追加します。 

    ```
    "BindingsFiles": [
        {
            "Name": "Binding File Name",
            "Path": "PathToBindingFile
        }
    ]
    ```

5. `DeploymentSequence`にインストールされているし、配置し順序で、アプリケーション名を追加、 [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]: 

    ```
    "DeploymentSequence": [
        {
            "NameOfFirst", "NameOfSecond", "NameOfThird"
        }
    ]
    ```


6. **保存**変更します。 完了すると、.json ファイルは、次のようになります。 

    ```
    {
      "$schema": "C:\\Program Files (x86)\\Microsoft BizTalk Server 2016\\Developer Tools\\BizTalkServerAppplicationSchema.json",
      "BizTalkAssemblies": [
        {
          "Name": "HelloWorld",
          "Path": "HelloWorld\\bin\\Release\\HelloWorld.dll"
        }
      ],
      "BindingsFiles": [
        {
          "Name": "HelloWorldBinding",
          "Path": "HelloWorld\\HelloWorldBinding.xml"
        }
      ],
      "DeploymentSequence": [
        "HelloWorld", "HelloWorldBinding"
      ]
    }
    ```

7. **省略可能な**します。 アプリケーション プロジェクト (例: appProjectHelloWorld) を右クリックして**プロパティ**します。 デバッグまたはリリース バージョンは、新しい値に設定できます。 私たちは次の手順ではありませんが、これを行うことができますに注意してください。  

    ![デバッグまたはリリース バージョンを設定します。](../core/media/application-project-version.png)

8. アプリケーション プロジェクト (例: appProjectHelloWorld) を右クリックして**ビルド**します。 Zip ファイルを作成する場合は成功すると、  **_yourApplicationProject_\bin\debug**フォルダー。  

    ![Zip ファイルをビルドします。](../core/media/application-project-zip-file.png)

9. ソリューションを選択し、選択、**チーム エクスプ ローラー**タブ。VSTS では、選択**Connect**します。  

    ![Team Services に接続します。](../core/media/connect-team-services.png)

10. VSTS アカウント、コレクション、およびチーム プロジェクトを選択します。 **[OK]** を選択します。 場合は、VSTS アカウントをまだ作成していない、作成し、1 つ ([手順 2: VSTS トークンの作成](feature-pack-create-vsts-token.md)いくつかのガイダンスを提供します)。 作成した後、この手順に戻って、接続します。  

    ![コレクションとプロジェクトを選択します。](../core/media/team-collections-projects.png)

11. 接続すると、このリポジトリを複製するプロンプトを表示があります。 選択、**このリポジトリを複製**リンク。  

    ![リポジトリを複製します](../core/media/vsts-clone-repository.png)

12. URL とパスをメモして選択、**複製**:  

    ![リポジトリのパス](../core/media/clone-repo-paths.png)

完了すると、Visual Studio Team Service デプロイ タスクは、必要なファイルとインストール シーケンスを優先します。 

> [!TIP]
> Git で複製した後に、プロジェクトに変更を行った場合は、**ステージ**、変更し、**プッシュ**、すべて Visual Studio 内で。 

## <a name="what-you-did"></a>どのような

BizTalk プロジェクトでは、BizTalk アプリケーション プロジェクト (.btaproj) が追加されます。 このプロジェクトは、VSTS を使用して、BizTalk Server プロジェクトの配置の自動化に使用されます。 アプリケーション プロジェクトを作成した後、BizTalk プロジェクトへの参照を追加します。 次に、どのような Dll を使用するバインド ファイルを展開して、アプリケーションを展開する順序は、自動展開を指示する JSON ファイルを更新します。 

## <a name="next-steps"></a>次の手順
[手順 2: VSTS トークンを作成します。](feature-pack-create-vsts-token.md)  
[手順 3: 作成、ビルドとリリース定義](feature-pack-add-build-release-definitions.md)  
[環境トークンと変数を構成します。](configure-environmental-tokens-and-variables-for-automatic-deployment.md)
