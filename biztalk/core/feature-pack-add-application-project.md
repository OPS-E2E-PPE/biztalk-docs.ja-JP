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
---
# <a name="step-1-add-the-biztalk-server-application-project-in-visual-studio"></a><span data-ttu-id="04a7f-103">手順 1: Visual Studio での BizTalk Server アプリケーション プロジェクトを追加します。</span><span class="sxs-lookup"><span data-stu-id="04a7f-103">Step 1: Add the BizTalk Server Application project in Visual Studio</span></span>

<span data-ttu-id="04a7f-104">Visual Studio Team Services を使用してアプリケーションをビルドすると、新しい BizTalk プロジェクト ファイルが作成 – .btaproj です。</span><span class="sxs-lookup"><span data-stu-id="04a7f-104">When you build your applications using Visual Studio Team Services, a new BizTalk project file is created – .btaproj.</span></span> <span data-ttu-id="04a7f-105">この新しいプロジェクトでは、すべての BizTalk アプリケーションをビルドおよび VSTS ビルドを使用して展開して機能のリリースを保持します。</span><span class="sxs-lookup"><span data-stu-id="04a7f-105">This new project holds all the BizTalk applications that you build and deploy using the VSTS build and release features.</span></span> 

<span data-ttu-id="04a7f-106">BizTalk アプリケーション プロジェクトに含まれる、`BizTalkServerInventory.json`ファイル。</span><span class="sxs-lookup"><span data-stu-id="04a7f-106">The BizTalk Application Project includes the `BizTalkServerInventory.json` file.</span></span> <span data-ttu-id="04a7f-107">このファイルで、BizTalk アセンブリを追加、BizTalk アプリケーションのバインド ファイルを追加して配置シーケンスを設定します。</span><span class="sxs-lookup"><span data-stu-id="04a7f-107">In this file, add your BizTalk assemblies, add the binding files for your BizTalk application, and then set a deployment sequence.</span></span> 

## <a name="before-you-begin"></a><span data-ttu-id="04a7f-108">アンインストールの準備</span><span class="sxs-lookup"><span data-stu-id="04a7f-108">Before you begin</span></span>

* <span data-ttu-id="04a7f-109">次の手順では、既存の BizTalk プロジェクトがあると仮定します。</span><span class="sxs-lookup"><span data-stu-id="04a7f-109">These steps assume you have an existing BizTalk project.</span></span> <span data-ttu-id="04a7f-110">、HelloWorld SDK サンプルを使用することができる場合 (\Program Files (x86) \Microsoft BizTalk Server *yourVersion*\SDK\Samples\Orchestrations\HelloWorld)。</span><span class="sxs-lookup"><span data-stu-id="04a7f-110">If not, you can use the HelloWorld SDK sample (\Program Files (x86)\Microsoft BizTalk Server *yourVersion*\SDK\Samples\Orchestrations\HelloWorld).</span></span> 
* <span data-ttu-id="04a7f-111">準備ができて、BizTalk プロジェクトに、XML バインド ファイルにパスがあります。</span><span class="sxs-lookup"><span data-stu-id="04a7f-111">Have the path to the XML binding file to your BizTalk project ready.</span></span> 
* <span data-ttu-id="04a7f-112">VSTS アカウントや、コレクション、チーム プロジェクトの詳細を確認します。</span><span class="sxs-lookup"><span data-stu-id="04a7f-112">Know your VSTS account, your collection, and your team project details.</span></span>
* <span data-ttu-id="04a7f-113">複製のリポジトリの操作など、git の概念を理解します。</span><span class="sxs-lookup"><span data-stu-id="04a7f-113">Be familiar with git concepts, including cloning and working with repositories.</span></span> 
* <span data-ttu-id="04a7f-114">必ず[Feature Pack 2](https://aka.ms/bts2016fp2)がインストールされています。</span><span class="sxs-lookup"><span data-stu-id="04a7f-114">Be sure [Feature Pack 2](https://aka.ms/bts2016fp2) is installed.</span></span>

## <a name="add-the-application-project"></a><span data-ttu-id="04a7f-115">アプリケーション プロジェクトを追加します。</span><span class="sxs-lookup"><span data-stu-id="04a7f-115">Add the application project</span></span>

1. <span data-ttu-id="04a7f-116">BizTalk Server では、Visual Studio のソリューション (ProjectName.sln) を開きます。</span><span class="sxs-lookup"><span data-stu-id="04a7f-116">On the BizTalk Server, open your solution (ProjectName.sln) in Visual Studio.</span></span> <span data-ttu-id="04a7f-117">Visual Studio Blend は選択しません。</span><span class="sxs-lookup"><span data-stu-id="04a7f-117">Do not select Visual Studio Blend.</span></span>

2. <span data-ttu-id="04a7f-118">ソリューション エクスプ ローラーで、プロジェクトを右クリックし、**ビルド**です。</span><span class="sxs-lookup"><span data-stu-id="04a7f-118">In solution explorer, right-click your project, and select **Build**.</span></span> <span data-ttu-id="04a7f-119">ビルドが成功したことを確認します。</span><span class="sxs-lookup"><span data-stu-id="04a7f-119">Be sure your build succeeds.</span></span> <span data-ttu-id="04a7f-120">プロジェクトを右クリックし **展開**です。</span><span class="sxs-lookup"><span data-stu-id="04a7f-120">Right-click your project, and select **Deploy**.</span></span> <span data-ttu-id="04a7f-121">展開が成功したことを確認します。</span><span class="sxs-lookup"><span data-stu-id="04a7f-121">Be sure your deploy succeeds.</span></span>

3. <span data-ttu-id="04a7f-122">ソリューションを右クリックし、選択**追加**を選択して**新しいプロジェクトの追加**です。</span><span class="sxs-lookup"><span data-stu-id="04a7f-122">Right-click your solution, select **Add**, and select **Add New Project**.</span></span>

4. <span data-ttu-id="04a7f-123">選択、 **BizTalk プロジェクト**] タブで [ **.NET Framework 4.6.1**クリックし、ドロップダウン リストから**アプリケーション用の BizTalk Server プロジェクト**です。</span><span class="sxs-lookup"><span data-stu-id="04a7f-123">Select the **BizTalk Projects** tab, select **.NET Framework 4.6.1** from the drop-down list, and select **BizTalk Server Application Project**.</span></span> <span data-ttu-id="04a7f-124">名前 (例: appProjectHelloWorld) を入力し、選択**OK**:</span><span class="sxs-lookup"><span data-stu-id="04a7f-124">Enter a name (e.g. appProjectHelloWorld), and select **OK**:</span></span>  

    ![アプリケーション プロジェクトを追加します。](../core/media/add-application-project.png)

5. <span data-ttu-id="04a7f-126">ソリューション エクスプ ローラーで、新しく追加したアプリケーション プロジェクト (.btaproj) を右クリックし、選択**追加****参照**です。</span><span class="sxs-lookup"><span data-stu-id="04a7f-126">In Solution Explorer, right-click your newly-added application project (.btaproj), select **Add**, select **Reference**.</span></span> <span data-ttu-id="04a7f-127">展開して、**プロジェクト**タブをクリックし、BizTalk プロジェクト (VSTS を使用して配置するプロジェクト) を確認します。</span><span class="sxs-lookup"><span data-stu-id="04a7f-127">Expand the **Projects** tab, and check your BizTalk project (the project you are deploying using VSTS).</span></span> <span data-ttu-id="04a7f-128">**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="04a7f-128">Select **OK**.</span></span>  
    <span data-ttu-id="04a7f-129">追加されると、展開**参照**追加したばかりの BizTalk プロジェクトを表示するアプリケーション プロジェクト (例: appProjectHelloWorld) の下。</span><span class="sxs-lookup"><span data-stu-id="04a7f-129">Once added, expand **References** under your application project (e.g. appProjectHelloWorld) to see the BizTalk project you just added.</span></span> 

6. <span data-ttu-id="04a7f-130">ソリューション エクスプ ローラーで、アプリケーション プロジェクト (.btaproj) を右クリックし、選択**追加****既存項目の**と**追加**バインディングは、XML ファイルです。</span><span class="sxs-lookup"><span data-stu-id="04a7f-130">In Solution Explorer, right-click your application project (.btaproj), select **Add**, select **Existing Item**, and **Add** your binding XML file.</span></span>

7. <span data-ttu-id="04a7f-131">Binding.xml のプロパティを開き、設定**出力ディレクトリにコピー**に**常にコピー**です。</span><span class="sxs-lookup"><span data-stu-id="04a7f-131">Open the properties of binding.xml, and set **Copy to Output Directory** to **Copy always**.</span></span> <span data-ttu-id="04a7f-132">**保存**変更内容。</span><span class="sxs-lookup"><span data-stu-id="04a7f-132">**Save** your changes:</span></span>  

    ![バインド ファイルのプロパティ](../core/media/xml-binding-file-properties.png)

8. <span data-ttu-id="04a7f-134">省略可。</span><span class="sxs-lookup"><span data-stu-id="04a7f-134">Optional.</span></span> <span data-ttu-id="04a7f-135">新しく追加したアプリケーション プロジェクトを右クリックし **プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="04a7f-135">Right-click your newly-added application project, and select **Properties**.</span></span> <span data-ttu-id="04a7f-136">カスタマイズ、**アプリケーション名**BizTalk 管理コンソールに表示します。</span><span class="sxs-lookup"><span data-stu-id="04a7f-136">Customize the **Application Name** you want displayed in BizTalk Administration:</span></span>  

    ![アプリケーション名](../core/media/application-project-name.png)

## <a name="configure-the-json-template"></a><span data-ttu-id="04a7f-138">JSON テンプレートを構成します。</span><span class="sxs-lookup"><span data-stu-id="04a7f-138">Configure the JSON template</span></span>

1. <span data-ttu-id="04a7f-139">Visual Studio で、アプリケーション プロジェクト (.btaproj) で開く、`BizTalkServerInventory.json`ファイル。</span><span class="sxs-lookup"><span data-stu-id="04a7f-139">In Visual Studio, in your application project (.btaproj), open the `BizTalkServerInventory.json` file.</span></span> 

2. <span data-ttu-id="04a7f-140">テンプレートには、次のセクションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="04a7f-140">The template includes the following sections:</span></span> 

    | | |
    |---|---|
    |<span data-ttu-id="04a7f-141">BizTalkAssemblies</span><span class="sxs-lookup"><span data-stu-id="04a7f-141">BizTalkAssemblies</span></span> | <span data-ttu-id="04a7f-142">アプリケーションで使用するアセンブリ</span><span class="sxs-lookup"><span data-stu-id="04a7f-142">The assemblies used in your applications</span></span> |
    |<span data-ttu-id="04a7f-143">BindingFiles</span><span class="sxs-lookup"><span data-stu-id="04a7f-143">BindingFiles</span></span> | <span data-ttu-id="04a7f-144">バインド ファイルを参照しています</span><span class="sxs-lookup"><span data-stu-id="04a7f-144">The binding files you are referencing</span></span>|
    |<span data-ttu-id="04a7f-145">DeploymentSequence</span><span class="sxs-lookup"><span data-stu-id="04a7f-145">DeploymentSequence</span></span> | <span data-ttu-id="04a7f-146">インストールする要素の順序</span><span class="sxs-lookup"><span data-stu-id="04a7f-146">The sequence for the elements to be installed</span></span>|
    
    <span data-ttu-id="04a7f-147">テンプレートのサンプル:</span><span class="sxs-lookup"><span data-stu-id="04a7f-147">Sample template:</span></span> 
    
    ![FP1 Json テンプレート イメージ 1](../core/media/fp1-json-template-image-1.png)

    > [!IMPORTANT]
    > <span data-ttu-id="04a7f-149">複雑さによっては、ソリューションのこの JSON テンプレート ファイルでビルドに必要な要素を参照する必要があります。</span><span class="sxs-lookup"><span data-stu-id="04a7f-149">Depending on the complexity of your solution, the elements you want in the build must be referenced in this JSON template file.</span></span>

3. <span data-ttu-id="04a7f-150">`BizTalkAssemblies`、BizTalk プロジェクトで使用するアセンブリを追加します。</span><span class="sxs-lookup"><span data-stu-id="04a7f-150">In `BizTalkAssemblies`, add the assemblies used by your BizTalk project:</span></span> 

    ```
    "BizTalkAssemblies": [
        {
            "Name": "AssemblyName",
            "Path": "PathToAssembly
        }
    ]
    ```

4. <span data-ttu-id="04a7f-151">`BindingsFiles`、BizTalk プロジェクトのバインド ファイルを追加します。</span><span class="sxs-lookup"><span data-stu-id="04a7f-151">In `BindingsFiles`, add the binding files for your BizTalk project:</span></span> 

    ```
    "BindingsFiles": [
        {
            "Name": "Binding File Name",
            "Path": "PathToBindingFile
        }
    ]
    ```

5. <span data-ttu-id="04a7f-152">`DeploymentSequence`にインストールされているし、配置し順序で、アプリケーション名を追加、 [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="04a7f-152">In `DeploymentSequence`, add the application names in the order you want them deployed, and installed on the [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]:</span></span> 

    ```
    "DeploymentSequence": [
        {
            "NameOfFirst", "NameOfSecond", "NameOfThird"
        }
    ]
    ```


6. <span data-ttu-id="04a7f-153">**保存** 変更します。</span><span class="sxs-lookup"><span data-stu-id="04a7f-153">**Save** your changes.</span></span> <span data-ttu-id="04a7f-154">完了したら、.json ファイルは、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="04a7f-154">When finished, your .json file looks like the following:</span></span> 

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

7. <span data-ttu-id="04a7f-155">**省略可能な**です。</span><span class="sxs-lookup"><span data-stu-id="04a7f-155">**Optional**.</span></span> <span data-ttu-id="04a7f-156">アプリケーション プロジェクト (例: appProjectHelloWorld) を右クリックし **プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="04a7f-156">Right-click your application project (e.g. appProjectHelloWorld), and select **Properties**.</span></span> <span data-ttu-id="04a7f-157">デバッグまたはリリース バージョンは、新しい値に設定できます。</span><span class="sxs-lookup"><span data-stu-id="04a7f-157">You can set the Debug or Release version to a new value.</span></span> <span data-ttu-id="04a7f-158">次の手順でないはこれを行うことができますに注意してください。</span><span class="sxs-lookup"><span data-stu-id="04a7f-158">We don’t in these steps, but be aware you can do this.</span></span>  

    ![デバッグまたはリリース バージョンを設定します。](../core/media/application-project-version.png)

8. <span data-ttu-id="04a7f-160">アプリケーション プロジェクト (例: appProjectHelloWorld) を右クリックし **ビルド**です。</span><span class="sxs-lookup"><span data-stu-id="04a7f-160">Right-click your application project (e.g. appProjectHelloWorld), and select **Build**.</span></span> <span data-ttu-id="04a7f-161">Zip ファイルがで作成が成功した場合 ***yourApplicationProject * \bin\debug**フォルダー。</span><span class="sxs-lookup"><span data-stu-id="04a7f-161">If it succeeds, a zip file is created in ***yourApplicationProject*\bin\debug** folder:</span></span>  

    ![Zip ファイルをビルドします。](../core/media/application-project-zip-file.png)

9. <span data-ttu-id="04a7f-163">ソリューションを選択し、選択、**チーム エクスプ ローラー**タブです。VSTS、で **接続**です。</span><span class="sxs-lookup"><span data-stu-id="04a7f-163">Select your solution, and select the **Team Explorer** tab. Under VSTS, select **Connect**.</span></span>  

    ![Team Services に接続します。](../core/media/connect-team-services.png)

10. <span data-ttu-id="04a7f-165">VSTS アカウントをコレクションとチーム プロジェクトを選択します。</span><span class="sxs-lookup"><span data-stu-id="04a7f-165">Select your VSTS account, your collection, and your team project.</span></span> <span data-ttu-id="04a7f-166">**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="04a7f-166">Select **OK**.</span></span> <span data-ttu-id="04a7f-167">VSTS アカウントをまだ作成していない場合、作成 ([手順 2: VSTS トークンを作成する](feature-pack-create-vsts-token.md)のガイダンスを示します)。</span><span class="sxs-lookup"><span data-stu-id="04a7f-167">If you didn’t create a VSTS account yet, then create one ([Step 2: Create the VSTS token](feature-pack-create-vsts-token.md) provides some guidance).</span></span> <span data-ttu-id="04a7f-168">作成後は、この手順に戻って、接続します。</span><span class="sxs-lookup"><span data-stu-id="04a7f-168">Once it's created, come back to this step, and connect.</span></span>  

    ![コレクションとプロジェクトを選択します。](../core/media/team-collections-projects.png)

11. <span data-ttu-id="04a7f-170">接続すると、このリポジトリを複製するのには、プロンプトが表示可能性があります。</span><span class="sxs-lookup"><span data-stu-id="04a7f-170">When you connect, you may get a prompt to clone this repository.</span></span> <span data-ttu-id="04a7f-171">選択、**このリポジトリを複製する**リンクします。</span><span class="sxs-lookup"><span data-stu-id="04a7f-171">Select the **Clone this repository** link.</span></span>  

    ![リポジトリを複製します。](../core/media/vsts-clone-repository.png)

12. <span data-ttu-id="04a7f-173">URL と、パスをメモし、選択**クローン**:</span><span class="sxs-lookup"><span data-stu-id="04a7f-173">Note the URL and paths, and select **Clone**:</span></span>  

    ![リポジトリのパス](../core/media/clone-repo-paths.png)

<span data-ttu-id="04a7f-175">完了すると、Visual Studio チームのサービスの展開タスクは、必要なファイルと、インストールの順序は使用されます。</span><span class="sxs-lookup"><span data-stu-id="04a7f-175">Once completed, the Visual Studio Team Service deployment task honors the required files and the install sequence.</span></span> 

> [!TIP]
> <span data-ttu-id="04a7f-176">Git でのクローンを作成した後に、プロジェクトに変更を加えた場合は**ステージ**、変更し、**プッシュ**、Visual Studio 内ですべてです。</span><span class="sxs-lookup"><span data-stu-id="04a7f-176">If you make changes to your project after you clone in git, you can **Stage** your changes, and then **Push**, all within Visual Studio.</span></span> 

## <a name="what-you-did"></a><span data-ttu-id="04a7f-177">どのような</span><span class="sxs-lookup"><span data-stu-id="04a7f-177">What you did</span></span>

<span data-ttu-id="04a7f-178">BizTalk プロジェクトでは、BizTalk アプリケーション プロジェクト (.btaproj) を追加します。</span><span class="sxs-lookup"><span data-stu-id="04a7f-178">In your BizTalk project, you added a BizTalk Application project (.btaproj).</span></span> <span data-ttu-id="04a7f-179">このプロジェクトは、VSTS を使用して、BizTalk Server プロジェクトの配置の自動化に使用されます。</span><span class="sxs-lookup"><span data-stu-id="04a7f-179">This project is used to automate deployments of your BizTalk Server projects using VSTS.</span></span> <span data-ttu-id="04a7f-180">アプリケーション プロジェクトを作成した後、BizTalk プロジェクトへの参照が追加されます。</span><span class="sxs-lookup"><span data-stu-id="04a7f-180">After you created the application project, you added a reference to your BizTalk project.</span></span> <span data-ttu-id="04a7f-181">次に、どのような Dll を使用するにはバインド ファイルを展開して、アプリケーションを展開する順序は、自動展開を指示する JSON ファイルを更新します。</span><span class="sxs-lookup"><span data-stu-id="04a7f-181">Then, you updated a JSON file that tells the automated deployment what DLLs to deploy, which binding file to use, and the order to deploy the applications.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="04a7f-182">次の手順</span><span class="sxs-lookup"><span data-stu-id="04a7f-182">Next steps</span></span>
[<span data-ttu-id="04a7f-183">手順 2: VSTS トークンを作成します。</span><span class="sxs-lookup"><span data-stu-id="04a7f-183">Step 2: Create the VSTS token</span></span>](feature-pack-create-vsts-token.md)  
[<span data-ttu-id="04a7f-184">手順 3: ビルドの作成し、定義のリリース</span><span class="sxs-lookup"><span data-stu-id="04a7f-184">Step 3: Create the build and release definitions</span></span>](feature-pack-add-build-release-definitions.md)  
[<span data-ttu-id="04a7f-185">環境のトークンと変数を構成します。</span><span class="sxs-lookup"><span data-stu-id="04a7f-185">Configure environmental tokens and variables</span></span>](configure-environmental-tokens-and-variables-for-automatic-deployment.md)
