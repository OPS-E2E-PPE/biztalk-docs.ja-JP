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
# <a name="step-1-add-the-biztalk-server-application-project-in-visual-studio"></a><span data-ttu-id="65a06-103">手順 1: Visual Studio での BizTalk Server アプリケーション プロジェクトを追加します。</span><span class="sxs-lookup"><span data-stu-id="65a06-103">Step 1: Add the BizTalk Server Application project in Visual Studio</span></span>

<span data-ttu-id="65a06-104">Visual Studio Team Services を使用してアプリケーションをビルドすると、新しい BizTalk プロジェクト ファイルが作成 – .btaproj。</span><span class="sxs-lookup"><span data-stu-id="65a06-104">When you build your applications using Visual Studio Team Services, a new BizTalk project file is created – .btaproj.</span></span> <span data-ttu-id="65a06-105">この新しいプロジェクトでは、すべての BizTalk アプリケーションを構築し、VSTS のビルドを使用してデプロイを機能をリリースを保持します。</span><span class="sxs-lookup"><span data-stu-id="65a06-105">This new project holds all the BizTalk applications that you build and deploy using the VSTS build and release features.</span></span> 

<span data-ttu-id="65a06-106">BizTalk アプリケーションのプロジェクトが含まれています、`BizTalkServerInventory.json`ファイル。</span><span class="sxs-lookup"><span data-stu-id="65a06-106">The BizTalk Application Project includes the `BizTalkServerInventory.json` file.</span></span> <span data-ttu-id="65a06-107">このファイルで、BizTalk アセンブリを追加、BizTalk アプリケーションのバインド ファイルを追加および展開シーケンスを設定します。</span><span class="sxs-lookup"><span data-stu-id="65a06-107">In this file, add your BizTalk assemblies, add the binding files for your BizTalk application, and then set a deployment sequence.</span></span> 

## <a name="before-you-begin"></a><span data-ttu-id="65a06-108">アンインストールの準備</span><span class="sxs-lookup"><span data-stu-id="65a06-108">Before you begin</span></span>

* <span data-ttu-id="65a06-109">次の手順では、既存の BizTalk プロジェクトがあるとします。</span><span class="sxs-lookup"><span data-stu-id="65a06-109">These steps assume you have an existing BizTalk project.</span></span> <span data-ttu-id="65a06-110">HelloWorld SDK サンプルを使用するそうでない場合 (\Program Files (x86) \Microsoft BizTalk Server *yourVersion*\SDK\Samples\Orchestrations\HelloWorld)。</span><span class="sxs-lookup"><span data-stu-id="65a06-110">If not, you can use the HelloWorld SDK sample (\Program Files (x86)\Microsoft BizTalk Server *yourVersion*\SDK\Samples\Orchestrations\HelloWorld).</span></span> 
* <span data-ttu-id="65a06-111">準備ができて、BizTalk プロジェクトに XML バインド ファイルにパスがあります。</span><span class="sxs-lookup"><span data-stu-id="65a06-111">Have the path to the XML binding file to your BizTalk project ready.</span></span> 
* <span data-ttu-id="65a06-112">VSTS アカウント、コレクション、およびチーム プロジェクトの詳細を確認します。</span><span class="sxs-lookup"><span data-stu-id="65a06-112">Know your VSTS account, your collection, and your team project details.</span></span>
* <span data-ttu-id="65a06-113">複製リポジトリを操作など、git の概念を理解します。</span><span class="sxs-lookup"><span data-stu-id="65a06-113">Be familiar with git concepts, including cloning and working with repositories.</span></span> 
* <span data-ttu-id="65a06-114">必ず[Feature Pack 2](https://aka.ms/bts2016fp2)がインストールされています。</span><span class="sxs-lookup"><span data-stu-id="65a06-114">Be sure [Feature Pack 2](https://aka.ms/bts2016fp2) is installed.</span></span>

## <a name="add-the-application-project"></a><span data-ttu-id="65a06-115">アプリケーション プロジェクトを追加します。</span><span class="sxs-lookup"><span data-stu-id="65a06-115">Add the application project</span></span>

1. <span data-ttu-id="65a06-116">BizTalk Server では、Visual Studio でソリューション (ProjectName.sln) を開きます。</span><span class="sxs-lookup"><span data-stu-id="65a06-116">On the BizTalk Server, open your solution (ProjectName.sln) in Visual Studio.</span></span> <span data-ttu-id="65a06-117">Visual Studio Blend は選択しないでください。</span><span class="sxs-lookup"><span data-stu-id="65a06-117">Do not select Visual Studio Blend.</span></span>

2. <span data-ttu-id="65a06-118">ソリューション エクスプ ローラーで、プロジェクトを右クリックし、選択**ビルド**します。</span><span class="sxs-lookup"><span data-stu-id="65a06-118">In solution explorer, right-click your project, and select **Build**.</span></span> <span data-ttu-id="65a06-119">ビルドが成功したことを確認します。</span><span class="sxs-lookup"><span data-stu-id="65a06-119">Be sure your build succeeds.</span></span> <span data-ttu-id="65a06-120">プロジェクトを右クリックして**デプロイ**します。</span><span class="sxs-lookup"><span data-stu-id="65a06-120">Right-click your project, and select **Deploy**.</span></span> <span data-ttu-id="65a06-121">デプロイが成功するとしてください。</span><span class="sxs-lookup"><span data-stu-id="65a06-121">Be sure your deploy succeeds.</span></span>

3. <span data-ttu-id="65a06-122">ソリューションを右クリックして**追加**、選び**新しいプロジェクトの追加**します。</span><span class="sxs-lookup"><span data-stu-id="65a06-122">Right-click your solution, select **Add**, and select **Add New Project**.</span></span>

4. <span data-ttu-id="65a06-123">選択、 **BizTalk プロジェクト**] タブで [ **.NET Framework 4.6.1**クリックし、ドロップダウン リストから**アプリケーション用の BizTalk Server プロジェクト**します。</span><span class="sxs-lookup"><span data-stu-id="65a06-123">Select the **BizTalk Projects** tab, select **.NET Framework 4.6.1** from the drop-down list, and select **BizTalk Server Application Project**.</span></span> <span data-ttu-id="65a06-124">名前 (例: appProjectHelloWorld) を入力し、選択**OK**:</span><span class="sxs-lookup"><span data-stu-id="65a06-124">Enter a name (e.g. appProjectHelloWorld), and select **OK**:</span></span>  

    ![アプリケーション プロジェクトを追加します。](../core/media/add-application-project.png)

5. <span data-ttu-id="65a06-126">ソリューション エクスプ ローラーで、新しく追加したアプリケーション プロジェクト (.btaproj) を右クリックし、選択 **追加** **参照** です。</span><span class="sxs-lookup"><span data-stu-id="65a06-126">In Solution Explorer, right-click your newly-added application project (.btaproj), select **Add**, select **Reference**.</span></span> <span data-ttu-id="65a06-127">展開、**プロジェクト**タブをクリックし、BizTalk プロジェクト (プロジェクトで VSTS を使用してデプロイする) を確認します。</span><span class="sxs-lookup"><span data-stu-id="65a06-127">Expand the **Projects** tab, and check your BizTalk project (the project you are deploying using VSTS).</span></span> <span data-ttu-id="65a06-128">**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="65a06-128">Select **OK**.</span></span>  
    <span data-ttu-id="65a06-129">追加されると、展開**参照**追加したばかりのアプリケーション プロジェクト (例: appProjectHelloWorld) を BizTalk プロジェクトを参照してください。</span><span class="sxs-lookup"><span data-stu-id="65a06-129">Once added, expand **References** under your application project (e.g. appProjectHelloWorld) to see the BizTalk project you just added.</span></span> 

6. <span data-ttu-id="65a06-130">ソリューション エクスプ ローラーで、アプリケーション プロジェクト (.btaproj) を右クリックし、選択 **追加** **既存項目の** と **追加** バインディングは、XML ファイルです。</span><span class="sxs-lookup"><span data-stu-id="65a06-130">In Solution Explorer, right-click your application project (.btaproj), select **Add**, select **Existing Item**, and **Add** your binding XML file.</span></span>

7. <span data-ttu-id="65a06-131">Binding.xml のプロパティを開き、設定**出力ディレクトリにコピー**に**常にコピー**します。</span><span class="sxs-lookup"><span data-stu-id="65a06-131">Open the properties of binding.xml, and set **Copy to Output Directory** to **Copy always**.</span></span> <span data-ttu-id="65a06-132">**保存**変更。</span><span class="sxs-lookup"><span data-stu-id="65a06-132">**Save** your changes:</span></span>  

    ![バインド ファイルのプロパティ](../core/media/xml-binding-file-properties.png)

8. <span data-ttu-id="65a06-134">任意。</span><span class="sxs-lookup"><span data-stu-id="65a06-134">Optional.</span></span> <span data-ttu-id="65a06-135">新しく追加されたアプリケーション プロジェクトを右クリックして**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="65a06-135">Right-click your newly-added application project, and select **Properties**.</span></span> <span data-ttu-id="65a06-136">カスタマイズ、**アプリケーション名**BizTalk 管理コンソールに表示します。</span><span class="sxs-lookup"><span data-stu-id="65a06-136">Customize the **Application Name** you want displayed in BizTalk Administration:</span></span>  

    ![アプリケーション名](../core/media/application-project-name.png)

## <a name="configure-the-json-template"></a><span data-ttu-id="65a06-138">JSON テンプレートを構成します。</span><span class="sxs-lookup"><span data-stu-id="65a06-138">Configure the JSON template</span></span>

1. <span data-ttu-id="65a06-139">Visual Studio で、アプリケーション プロジェクト (.btaproj) で開く、`BizTalkServerInventory.json`ファイル。</span><span class="sxs-lookup"><span data-stu-id="65a06-139">In Visual Studio, in your application project (.btaproj), open the `BizTalkServerInventory.json` file.</span></span> 

2. <span data-ttu-id="65a06-140">テンプレートには、次のセクションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="65a06-140">The template includes the following sections:</span></span> 

    | | |
    |---|---|
    |<span data-ttu-id="65a06-141">BizTalkAssemblies</span><span class="sxs-lookup"><span data-stu-id="65a06-141">BizTalkAssemblies</span></span> | <span data-ttu-id="65a06-142">アプリケーションで使用されるアセンブリ</span><span class="sxs-lookup"><span data-stu-id="65a06-142">The assemblies used in your applications</span></span> |
    |<span data-ttu-id="65a06-143">BindingFiles</span><span class="sxs-lookup"><span data-stu-id="65a06-143">BindingFiles</span></span> | <span data-ttu-id="65a06-144">バインド ファイルを参照します。</span><span class="sxs-lookup"><span data-stu-id="65a06-144">The binding files you are referencing</span></span>|
    |<span data-ttu-id="65a06-145">DeploymentSequence</span><span class="sxs-lookup"><span data-stu-id="65a06-145">DeploymentSequence</span></span> | <span data-ttu-id="65a06-146">インストールする要素のシーケンス</span><span class="sxs-lookup"><span data-stu-id="65a06-146">The sequence for the elements to be installed</span></span>|
    
    <span data-ttu-id="65a06-147">サンプル テンプレート:</span><span class="sxs-lookup"><span data-stu-id="65a06-147">Sample template:</span></span> 
    
    ![FP1 Json テンプレート イメージ 1](../core/media/fp1-json-template-image-1.png)

    > [!IMPORTANT]
    > <span data-ttu-id="65a06-149">によっては、ソリューションの複雑さ、ビルドに必要な要素は、この JSON テンプレート ファイルで参照する必要があります。</span><span class="sxs-lookup"><span data-stu-id="65a06-149">Depending on the complexity of your solution, the elements you want in the build must be referenced in this JSON template file.</span></span>

3. <span data-ttu-id="65a06-150">`BizTalkAssemblies`、BizTalk プロジェクトで使用するアセンブリを追加します。</span><span class="sxs-lookup"><span data-stu-id="65a06-150">In `BizTalkAssemblies`, add the assemblies used by your BizTalk project:</span></span> 

    ```
    "BizTalkAssemblies": [
        {
            "Name": "AssemblyName",
            "Path": "PathToAssembly
        }
    ]
    ```

4. <span data-ttu-id="65a06-151">`BindingsFiles`、BizTalk プロジェクトのバインド ファイルを追加します。</span><span class="sxs-lookup"><span data-stu-id="65a06-151">In `BindingsFiles`, add the binding files for your BizTalk project:</span></span> 

    ```
    "BindingsFiles": [
        {
            "Name": "Binding File Name",
            "Path": "PathToBindingFile
        }
    ]
    ```

5. <span data-ttu-id="65a06-152">`DeploymentSequence`にインストールされているし、配置し順序で、アプリケーション名を追加、 [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="65a06-152">In `DeploymentSequence`, add the application names in the order you want them deployed, and installed on the [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]:</span></span> 

    ```
    "DeploymentSequence": [
        {
            "NameOfFirst", "NameOfSecond", "NameOfThird"
        }
    ]
    ```


6. <span data-ttu-id="65a06-153">**保存**変更します。</span><span class="sxs-lookup"><span data-stu-id="65a06-153">**Save** your changes.</span></span> <span data-ttu-id="65a06-154">完了すると、.json ファイルは、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="65a06-154">When finished, your .json file looks like the following:</span></span> 

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

7. <span data-ttu-id="65a06-155">**省略可能な**します。</span><span class="sxs-lookup"><span data-stu-id="65a06-155">**Optional**.</span></span> <span data-ttu-id="65a06-156">アプリケーション プロジェクト (例: appProjectHelloWorld) を右クリックして**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="65a06-156">Right-click your application project (e.g. appProjectHelloWorld), and select **Properties**.</span></span> <span data-ttu-id="65a06-157">デバッグまたはリリース バージョンは、新しい値に設定できます。</span><span class="sxs-lookup"><span data-stu-id="65a06-157">You can set the Debug or Release version to a new value.</span></span> <span data-ttu-id="65a06-158">私たちは次の手順ではありませんが、これを行うことができますに注意してください。</span><span class="sxs-lookup"><span data-stu-id="65a06-158">We don’t in these steps, but be aware you can do this.</span></span>  

    ![デバッグまたはリリース バージョンを設定します。](../core/media/application-project-version.png)

8. <span data-ttu-id="65a06-160">アプリケーション プロジェクト (例: appProjectHelloWorld) を右クリックして**ビルド**します。</span><span class="sxs-lookup"><span data-stu-id="65a06-160">Right-click your application project (e.g. appProjectHelloWorld), and select **Build**.</span></span> <span data-ttu-id="65a06-161">Zip ファイルを作成する場合は成功すると、  **_yourApplicationProject_\bin\debug**フォルダー。</span><span class="sxs-lookup"><span data-stu-id="65a06-161">If it succeeds, a zip file is created in **_yourApplicationProject_\bin\debug** folder:</span></span>  

    ![Zip ファイルをビルドします。](../core/media/application-project-zip-file.png)

9. <span data-ttu-id="65a06-163">ソリューションを選択し、選択、**チーム エクスプ ローラー**タブ。VSTS では、選択**Connect**します。</span><span class="sxs-lookup"><span data-stu-id="65a06-163">Select your solution, and select the **Team Explorer** tab. Under VSTS, select **Connect**.</span></span>  

    ![Team Services に接続します。](../core/media/connect-team-services.png)

10. <span data-ttu-id="65a06-165">VSTS アカウント、コレクション、およびチーム プロジェクトを選択します。</span><span class="sxs-lookup"><span data-stu-id="65a06-165">Select your VSTS account, your collection, and your team project.</span></span> <span data-ttu-id="65a06-166">**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="65a06-166">Select **OK**.</span></span> <span data-ttu-id="65a06-167">場合は、VSTS アカウントをまだ作成していない、作成し、1 つ ([手順 2: VSTS トークンの作成](feature-pack-create-vsts-token.md)いくつかのガイダンスを提供します)。</span><span class="sxs-lookup"><span data-stu-id="65a06-167">If you didn’t create a VSTS account yet, then create one ([Step 2: Create the VSTS token](feature-pack-create-vsts-token.md) provides some guidance).</span></span> <span data-ttu-id="65a06-168">作成した後、この手順に戻って、接続します。</span><span class="sxs-lookup"><span data-stu-id="65a06-168">Once it's created, come back to this step, and connect.</span></span>  

    ![コレクションとプロジェクトを選択します。](../core/media/team-collections-projects.png)

11. <span data-ttu-id="65a06-170">接続すると、このリポジトリを複製するプロンプトを表示があります。</span><span class="sxs-lookup"><span data-stu-id="65a06-170">When you connect, you may get a prompt to clone this repository.</span></span> <span data-ttu-id="65a06-171">選択、**このリポジトリを複製**リンク。</span><span class="sxs-lookup"><span data-stu-id="65a06-171">Select the **Clone this repository** link.</span></span>  

    ![リポジトリを複製します](../core/media/vsts-clone-repository.png)

12. <span data-ttu-id="65a06-173">URL とパスをメモして選択、**複製**:</span><span class="sxs-lookup"><span data-stu-id="65a06-173">Note the URL and paths, and select **Clone**:</span></span>  

    ![リポジトリのパス](../core/media/clone-repo-paths.png)

<span data-ttu-id="65a06-175">完了すると、Visual Studio Team Service デプロイ タスクは、必要なファイルとインストール シーケンスを優先します。</span><span class="sxs-lookup"><span data-stu-id="65a06-175">Once completed, the Visual Studio Team Service deployment task honors the required files and the install sequence.</span></span> 

> [!TIP]
> <span data-ttu-id="65a06-176">Git で複製した後に、プロジェクトに変更を行った場合は、**ステージ**、変更し、**プッシュ**、すべて Visual Studio 内で。</span><span class="sxs-lookup"><span data-stu-id="65a06-176">If you make changes to your project after you clone in git, you can **Stage** your changes, and then **Push**, all within Visual Studio.</span></span> 

## <a name="what-you-did"></a><span data-ttu-id="65a06-177">どのような</span><span class="sxs-lookup"><span data-stu-id="65a06-177">What you did</span></span>

<span data-ttu-id="65a06-178">BizTalk プロジェクトでは、BizTalk アプリケーション プロジェクト (.btaproj) が追加されます。</span><span class="sxs-lookup"><span data-stu-id="65a06-178">In your BizTalk project, you added a BizTalk Application project (.btaproj).</span></span> <span data-ttu-id="65a06-179">このプロジェクトは、VSTS を使用して、BizTalk Server プロジェクトの配置の自動化に使用されます。</span><span class="sxs-lookup"><span data-stu-id="65a06-179">This project is used to automate deployments of your BizTalk Server projects using VSTS.</span></span> <span data-ttu-id="65a06-180">アプリケーション プロジェクトを作成した後、BizTalk プロジェクトへの参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="65a06-180">After you created the application project, you added a reference to your BizTalk project.</span></span> <span data-ttu-id="65a06-181">次に、どのような Dll を使用するバインド ファイルを展開して、アプリケーションを展開する順序は、自動展開を指示する JSON ファイルを更新します。</span><span class="sxs-lookup"><span data-stu-id="65a06-181">Then, you updated a JSON file that tells the automated deployment what DLLs to deploy, which binding file to use, and the order to deploy the applications.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="65a06-182">次の手順</span><span class="sxs-lookup"><span data-stu-id="65a06-182">Next steps</span></span>
[<span data-ttu-id="65a06-183">手順 2: VSTS トークンを作成します。</span><span class="sxs-lookup"><span data-stu-id="65a06-183">Step 2: Create the VSTS token</span></span>](feature-pack-create-vsts-token.md)  
[<span data-ttu-id="65a06-184">手順 3: 作成、ビルドとリリース定義</span><span class="sxs-lookup"><span data-stu-id="65a06-184">Step 3: Create the build and release definitions</span></span>](feature-pack-add-build-release-definitions.md)  
[<span data-ttu-id="65a06-185">環境トークンと変数を構成します。</span><span class="sxs-lookup"><span data-stu-id="65a06-185">Configure environmental tokens and variables</span></span>](configure-environmental-tokens-and-variables-for-automatic-deployment.md)
