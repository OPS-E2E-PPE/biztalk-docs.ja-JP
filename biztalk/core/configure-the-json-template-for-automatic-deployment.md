---
title: "自動展開用の JSON テンプレートの構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.prod: biztalk-server
ms.topic: article
ms.assetid: 0b7755a6-5a5a-4a6b-8f99-ac12a5fbf3d4
caps.latest.revision: "4"
author: tordgladnordahl
ms.author: tonordah
manager: anneta
ms.openlocfilehash: dba2870a2a7f9aeaaa627dba00afca85f3ca71c5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="configure-the-json-template-for-automatic-deployment"></a><span data-ttu-id="dabc9-102">自動展開用の JSON テンプレートを構成します。</span><span class="sxs-lookup"><span data-stu-id="dabc9-102">Configure the JSON template for automatic deployment</span></span>


<span data-ttu-id="dabc9-103">Visual Studio Team Services を使用してアプリケーションをビルドすると、新しい BizTalk プロジェクト ファイルが作成 – (.btaproj)。</span><span class="sxs-lookup"><span data-stu-id="dabc9-103">When you build your applications using Visual Studio Team Services, a new BizTalk project file is created – (.btaproj).</span></span> <span data-ttu-id="dabc9-104">この新しいプロジェクトでは、VSTS を使用してビルドするすべての BizTalk アプリケーションを保持します。</span><span class="sxs-lookup"><span data-stu-id="dabc9-104">This new project holds all the BizTalk applications that you build using VSTS.</span></span> 

<span data-ttu-id="dabc9-105">プロジェクトに含まれる、`BizTalkServerInventory.json`ファイル。</span><span class="sxs-lookup"><span data-stu-id="dabc9-105">Your project includes the `BizTalkServerInventory.json` file.</span></span> <span data-ttu-id="dabc9-106">このファイルで、BizTalk アセンブリを追加、BizTalk アプリケーションのバインド ファイルを追加して配置シーケンスを設定します。</span><span class="sxs-lookup"><span data-stu-id="dabc9-106">In this file, add your BizTalk assemblies, add the binding files for your BizTalk application, and set a deployment sequence.</span></span> 

<span data-ttu-id="dabc9-107">このトピックでは、json ファイルを更新する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="dabc9-107">This topic shows you how to update the json file.</span></span> 

## <a name="add-assemblies-binding-files-and-deployment-sequence"></a><span data-ttu-id="dabc9-108">アセンブリ、バインド ファイル、および配置シーケンスを追加します。</span><span class="sxs-lookup"><span data-stu-id="dabc9-108">Add assemblies, binding files, and deployment sequence</span></span>

1. <span data-ttu-id="dabc9-109">開く、`BizTalkServerInventory.json`ファイルで、 **BizTalk Server アプリケーション**プロジェクト (.btaproj)。</span><span class="sxs-lookup"><span data-stu-id="dabc9-109">Open the `BizTalkServerInventory.json` file in your **BizTalk Server Application** project (.btaproj).</span></span>

2. <span data-ttu-id="dabc9-110">テンプレートには、次のセクションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="dabc9-110">The template includes the following sections:</span></span> 

    | | |
    |---|---|
    |<span data-ttu-id="dabc9-111">BizTalkAssemblies</span><span class="sxs-lookup"><span data-stu-id="dabc9-111">BizTalkAssemblies</span></span> | <span data-ttu-id="dabc9-112">アプリケーションで使用するアセンブリ</span><span class="sxs-lookup"><span data-stu-id="dabc9-112">The assemblies used in your applications</span></span> |
    |<span data-ttu-id="dabc9-113">BindingFiles</span><span class="sxs-lookup"><span data-stu-id="dabc9-113">BindingFiles</span></span> | <span data-ttu-id="dabc9-114">バインド ファイルを参照しています</span><span class="sxs-lookup"><span data-stu-id="dabc9-114">The binding files you are referencing</span></span>|
    | <span data-ttu-id="dabc9-115">DeploymentSequence</span><span class="sxs-lookup"><span data-stu-id="dabc9-115">DeploymentSequence</span></span> | <span data-ttu-id="dabc9-116">インストールする要素の順序</span><span class="sxs-lookup"><span data-stu-id="dabc9-116">The sequence for the elements to be installed</span></span>|
    
    <span data-ttu-id="dabc9-117">テンプレートのサンプル:</span><span class="sxs-lookup"><span data-stu-id="dabc9-117">Sample template:</span></span> 
    
    ![FP1 Json テンプレート イメージ 1](../core/media/fp1-json-template-image-1.png)

    > [!IMPORTANT]
    > <span data-ttu-id="dabc9-119">複雑さによっては、ソリューションのこの JSON テンプレート ファイルでビルドに必要な要素を参照する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dabc9-119">Depending on the complexity of your solution, the elements you want in the build must be referenced in this JSON template file.</span></span>

3. <span data-ttu-id="dabc9-120">`BizTalkAssemblies`、BizTalk アプリケーションで使用するアセンブリを追加します。</span><span class="sxs-lookup"><span data-stu-id="dabc9-120">In `BizTalkAssemblies`, add the assemblies used by your BizTalk applications:</span></span> 

    ```
    "BizTalkAssemblies": [
        {
            "Name": "AssemblyName"
            "Path": "PathToAssembly
        }
    ]
    ```

4. <span data-ttu-id="dabc9-121">`BindingsFiles`、BizTalk アプリケーションのバインド ファイルを追加します。</span><span class="sxs-lookup"><span data-stu-id="dabc9-121">In `BindingsFiles`, add the binding files for your BizTalk applications:</span></span> 

    ```
    "BindingsFiles": [
        {
            "Name": "Binding File Name"
            "Path": "PathToBindingFile
        }
    ]
    ```

5. <span data-ttu-id="dabc9-122">`DeploymentSequence`、アプリケーション名を展開しをインストールし順序で追加、 [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="dabc9-122">In `DeploymentSequence`, add the application names in the order you want them deployed and installed on the [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]:</span></span> 

    ```
    "DeploymentSequence": [
        {
            "NameOfFirst", "NameOfSecond", "NameOfThird"
        }
    ]
    ```
    
6. <span data-ttu-id="dabc9-123">**保存**変更します。</span><span class="sxs-lookup"><span data-stu-id="dabc9-123">**Save** your changes.</span></span> 

<span data-ttu-id="dabc9-124">完了すると、Visual Studio チームのサービスの展開タスクは、必要なファイルと、インストールの順序は使用されます。</span><span class="sxs-lookup"><span data-stu-id="dabc9-124">Once completed, the Visual Studio Team Service deployment task honors the required files and the install sequence.</span></span> 

## <a name="next-step"></a><span data-ttu-id="dabc9-125">次の手順</span><span class="sxs-lookup"><span data-stu-id="dabc9-125">Next step</span></span>
<span data-ttu-id="dabc9-126">[トークンと変数を構成する](../core/configure-environmental-tokens-and-variables-for-automatic-deployment.md)倍数に同じ BizTalk アプリケーションを展開する、バインド ファイルに[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]s。</span><span class="sxs-lookup"><span data-stu-id="dabc9-126">[Configure tokens and variables](../core/configure-environmental-tokens-and-variables-for-automatic-deployment.md) in your binding file to deploy the same BizTalk application to multiple [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]s.</span></span>

 