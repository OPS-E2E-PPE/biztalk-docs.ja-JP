---
title: 手順 1 - アプリケーションのプロジェクトと更新プログラムの json の追加 |Microsoft ドキュメント
description: Visual Studio で、BizTalk Server アプリケーション プロジェクトを追加し、Dll、バインド ファイル、およびアプリケーションの Visual Studio Team Services の配置シーケンスで BizTalkServerInventory.json ファイルを更新
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
ms.openlocfilehash: da1c4bb3cb12cf67e84bab7aa7f38c1a893eca00
ms.sourcegitcommit: 770523695b34cc54db81f7ab7eba46f2bc19baec
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/26/2018
ms.locfileid: "31817015"
---
# <a name="step-1-add-the-biztalk-server-application-project-in-visual-studio"></a>手順 1: Visual Studio での BizTalk Server アプリケーション プロジェクトを追加します。

Visual Studio Team Services を使用してアプリケーションをビルドすると、新しい BizTalk プロジェクト ファイルが作成 – .btaproj です。 この新しいプロジェクトでは、すべての BizTalk アプリケーションをビルドおよび VSTS ビルドを使用して展開して機能のリリースを保持します。 

BizTalk アプリケーション プロジェクトに含まれる、`BizTalkServerInventory.json`ファイル。 このファイルで、BizTalk アセンブリを追加、BizTalk アプリケーションのバインド ファイルを追加して配置シーケンスを設定します。 

## <a name="before-you-begin"></a>アンインストールの準備

* 次の手順では、既存の BizTalk プロジェクトがあると仮定します。 、HelloWorld SDK サンプルを使用することができる場合 (\Program Files (x86) \Microsoft BizTalk Server *yourVersion*\SDK\Samples\Orchestrations\HelloWorld)。 
* 準備ができて、BizTalk プロジェクトに、XML バインド ファイルにパスがあります。 
* VSTS アカウントや、コレクション、チーム プロジェクトの詳細を確認します。
* 複製のリポジトリの操作など、git の概念を理解します。 
* 必ず[Feature Pack 2](https://aka.ms/bts2016fp2)がインストールされています。

## <a name="add-the-application-project"></a>アプリケーション プロジェクトを追加します。

1. BizTalk Server では、Visual Studio のソリューション (ProjectName.sln) を開きます。 Visual Studio Blend は選択しません。

2. ソリューション エクスプ ローラーで、プロジェクトを右クリックし、**ビルド**です。 ビルドが成功したことを確認します。 プロジェクトを右クリックし **展開**です。 展開が成功したことを確認します。

3. ソリューションを右クリックし、選択**追加**を選択して**新しいプロジェクトの追加**です。

4. 選択、 **BizTalk プロジェクト**] タブで [ **.NET Framework 4.6.1**クリックし、ドロップダウン リストから**アプリケーション用の BizTalk Server プロジェクト**です。 名前 (例: appProjectHelloWorld) を入力し、選択**OK**:  

    ![アプリケーション プロジェクトを追加します。](../core/media/add-application-project.png)

5. ソリューション エクスプ ローラーで、新しく追加したアプリケーション プロジェクト (.btaproj) を右クリックし、選択 **追加** **参照** です。 展開して、**プロジェクト**タブをクリックし、BizTalk プロジェクト (VSTS を使用して配置するプロジェクト) を確認します。 **[OK]** を選択します。  
    追加されると、展開**参照**追加したばかりの BizTalk プロジェクトを表示するアプリケーション プロジェクト (例: appProjectHelloWorld) の下。 

6. ソリューション エクスプ ローラーで、アプリケーション プロジェクト (.btaproj) を右クリックし、選択 **追加** **既存項目の** と **追加** バインディングは、XML ファイルです。

7. Binding.xml のプロパティを開き、設定**出力ディレクトリにコピー**に**常にコピー**です。 **保存**変更内容。  

    ![バインド ファイルのプロパティ](../core/media/xml-binding-file-properties.png)

8. 省略可。 新しく追加したアプリケーション プロジェクトを右クリックし **プロパティ**です。 カスタマイズ、**アプリケーション名**BizTalk 管理コンソールに表示します。  

    ![アプリケーション名](../core/media/application-project-name.png)

## <a name="configure-the-json-template"></a>JSON テンプレートを構成します。

1. Visual Studio で、アプリケーション プロジェクト (.btaproj) で開く、`BizTalkServerInventory.json`ファイル。 

2. テンプレートには、次のセクションが含まれています。 

    | | |
    |---|---|
    |BizTalkAssemblies | アプリケーションで使用するアセンブリ |
    |BindingFiles | バインド ファイルを参照しています|
    |DeploymentSequence | インストールする要素の順序|
    
    テンプレートのサンプル: 
    
    ![FP1 Json テンプレート イメージ 1](../core/media/fp1-json-template-image-1.png)

    > [!IMPORTANT]
    > 複雑さによっては、ソリューションのこの JSON テンプレート ファイルでビルドに必要な要素を参照する必要があります。

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


6. **保存** 変更します。 完了したら、.json ファイルは、次のようになります。 

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

7. **省略可能な**です。 アプリケーション プロジェクト (例: appProjectHelloWorld) を右クリックし **プロパティ**です。 デバッグまたはリリース バージョンは、新しい値に設定できます。 次の手順でないはこれを行うことができますに注意してください。  

    ![デバッグまたはリリース バージョンを設定します。](../core/media/application-project-version.png)

8. アプリケーション プロジェクト (例: appProjectHelloWorld) を右クリックし **ビルド**です。 Zip ファイルがで作成が成功した場合 ***yourApplicationProject * \bin\debug**フォルダー。  

    ![Zip ファイルをビルドします。](../core/media/application-project-zip-file.png)

9. ソリューションを選択し、選択、**チーム エクスプ ローラー**タブです。VSTS、で **接続**です。  

    ![Team Services に接続します。](../core/media/connect-team-services.png)

10. VSTS アカウントをコレクションとチーム プロジェクトを選択します。 **[OK]** を選択します。 VSTS アカウントをまだ作成していない場合、作成 ([手順 2: VSTS トークンを作成する](feature-pack-create-vsts-token.md)のガイダンスを示します)。 作成後は、この手順に戻って、接続します。  

    ![コレクションとプロジェクトを選択します。](../core/media/team-collections-projects.png)

11. 接続すると、このリポジトリを複製するのには、プロンプトが表示可能性があります。 選択、**このリポジトリを複製する**リンクします。  

    ![リポジトリを複製します。](../core/media/vsts-clone-repository.png)

12. URL と、パスをメモし、選択**クローン**:  

    ![リポジトリのパス](../core/media/clone-repo-paths.png)

完了すると、Visual Studio チームのサービスの展開タスクは、必要なファイルと、インストールの順序は使用されます。 

> [!TIP]
> Git でのクローンを作成した後に、プロジェクトに変更を加えた場合は**ステージ**、変更し、**プッシュ**、Visual Studio 内ですべてです。 

## <a name="what-you-did"></a>どのような

BizTalk プロジェクトでは、BizTalk アプリケーション プロジェクト (.btaproj) を追加します。 このプロジェクトは、VSTS を使用して、BizTalk Server プロジェクトの配置の自動化に使用されます。 アプリケーション プロジェクトを作成した後、BizTalk プロジェクトへの参照が追加されます。 次に、どのような Dll を使用するにはバインド ファイルを展開して、アプリケーションを展開する順序は、自動展開を指示する JSON ファイルを更新します。 

## <a name="next-steps"></a>次の手順
[手順 2: VSTS トークンを作成します。](feature-pack-create-vsts-token.md)  
[手順 3: ビルドの作成し、定義のリリース](feature-pack-add-build-release-definitions.md)  
[環境のトークンと変数を構成します。](configure-environmental-tokens-and-variables-for-automatic-deployment.md)
