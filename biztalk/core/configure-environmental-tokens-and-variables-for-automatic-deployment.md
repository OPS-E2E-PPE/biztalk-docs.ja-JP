---
title: "環境のトークンと変数を作成 |Microsoft ドキュメント\""
description: "環境のトークンを使用するバインド ファイルを更新し、BizTalk Server アプリケーションの展開を自動化する VSTS で変数を作成"
ms.custom: 
ms.date: 11/08/2017
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.prod: biztalk-server
ms.topic: article
ms.assetid: 28bb2d4a-f45c-466d-ba65-0ca8cad0bffd
caps.latest.revision: "4"
author: tordgladnordahl
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6d84fa393410e3084c87e762140530a45b0b78b5
ms.sourcegitcommit: a0165ec2f1e8b58545638666b7bfa2bf440036fd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/09/2017
---
# <a name="configure-environmental-tokens-and-variables-for-automatic-deployment"></a><span data-ttu-id="8cd11-103">環境のトークンと自動展開用の変数を構成します。</span><span class="sxs-lookup"><span data-stu-id="8cd11-103">Configure environmental tokens and variables for automatic deployment</span></span>
<span data-ttu-id="8cd11-104">Visual Studio Team Services (VSTS) の変数を使用して、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]バインド ファイルです。</span><span class="sxs-lookup"><span data-stu-id="8cd11-104">Use Visual Studio Team Services (VSTS) variables in your [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] binding files.</span></span>

## <a name="overview"></a><span data-ttu-id="8cd11-105">概要</span><span class="sxs-lookup"><span data-stu-id="8cd11-105">Overview</span></span>
<span data-ttu-id="8cd11-106">環境では、VSTS は、変数を追加したり、値に設定します。</span><span class="sxs-lookup"><span data-stu-id="8cd11-106">In a VSTS environment, you can add variables, and set them to a value.</span></span> <span data-ttu-id="8cd11-107">たとえば、作成することができます、 *sendPortPath*変数で物理フォルダーにその値を設定、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="8cd11-107">For example, you can create a *sendPortPath* variable, and set its value to a physical folder on your [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)].</span></span> 

<span data-ttu-id="8cd11-108">内で、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]アプリケーション バインド ファイル、構成可能な変数できます受信場所の名前などの XML タグ内で何もするホスト、送信ポート、URI に表示され、します。</span><span class="sxs-lookup"><span data-stu-id="8cd11-108">Within the [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] application binding file, the configurable variables can be anything within an XML tag, such as the receive location name, host, send port URI, and so on.</span></span> 

<span data-ttu-id="8cd11-109">これらの変数は、VSTS の環境に固有であり、同じアプリケーションを複数の展開に使用できる[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]環境。</span><span class="sxs-lookup"><span data-stu-id="8cd11-109">These variables are specific to your VSTS environment, and can be used to deploy the same application to multiple [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] environments.</span></span> 

<span data-ttu-id="8cd11-110">VSTS 内の変数を作成する方法と、バインド ファイルに、VSTS 変数を追加する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="8cd11-110">We show you how to add the VSTS variable in your binding file, and how to create the variable within VSTS.</span></span> 

## <a name="add-variables-to-the-binding-file"></a><span data-ttu-id="8cd11-111">バインド ファイルに変数を追加します。</span><span class="sxs-lookup"><span data-stu-id="8cd11-111">Add variables to the binding file</span></span>

1. <span data-ttu-id="8cd11-112">アプリケーションのバインド ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="8cd11-112">Open the application binding file:</span></span>

    ![バインド ファイルを開く](../core/media/biztalk-feature-pack-1-binding-1.png)

2. <span data-ttu-id="8cd11-114">変更する要素を検索します。</span><span class="sxs-lookup"><span data-stu-id="8cd11-114">Find the element you want to change:</span></span>

    ![要素を選択します。](../core/media/biztalk-feature-pack-1-binding-2.png)
    
3. <span data-ttu-id="8cd11-116">設定済みの値を削除して、変数で置き換えます:`$(YourValue)`です。</span><span class="sxs-lookup"><span data-stu-id="8cd11-116">Remove the populated value, and replace it with you variables: `$(YourValue)`.</span></span> <span data-ttu-id="8cd11-117">たとえば、入力`$(SendPort1)`:</span><span class="sxs-lookup"><span data-stu-id="8cd11-117">For example, enter `$(SendPort1)`:</span></span> 

    ![バインド ファイル](../core/media/biztalk-feature-pack-1-binding-3.png)

4. <span data-ttu-id="8cd11-119">完了したら、バインド ファイルを保存し、JSON のビルド テンプレートに追加 (ステップの[手順 1: アプリケーションの追加の更新 (&)、プロジェクトの .json テンプレート](feature-pack-add-application-project.md))。</span><span class="sxs-lookup"><span data-stu-id="8cd11-119">When done, save the binding file, and add it to your JSON build template (steps in [Step 1: Add Application project & update .json template](feature-pack-add-application-project.md)).</span></span>

## <a name="create-the-variables-in-vsts"></a><span data-ttu-id="8cd11-120">VSTS で変数を作成します。</span><span class="sxs-lookup"><span data-stu-id="8cd11-120">Create the variables in VSTS</span></span>

1. <span data-ttu-id="8cd11-121">VSTS アカウントに次のように選択します。**ビルドとリリースの**、を選択して**リリース**です。</span><span class="sxs-lookup"><span data-stu-id="8cd11-121">In your VSTS account, select **Build and release**, and select **Releases**.</span></span>

2. <span data-ttu-id="8cd11-122">選択、**リリース定義**を選択して**変数**:</span><span class="sxs-lookup"><span data-stu-id="8cd11-122">Select your **Release definition**, and select **Variables**:</span></span>  

    ![バインド ファイル](../core/media/vsts-release-variables.png)

3. <span data-ttu-id="8cd11-124">選択**追加**、変数の名前と値を作成します。</span><span class="sxs-lookup"><span data-stu-id="8cd11-124">Select **Add**, and create the variable names and values:</span></span>   

    ![変数を構成します。](../core/media/environment-specific-variables.png)

4. <span data-ttu-id="8cd11-126">**保存**変更します。</span><span class="sxs-lookup"><span data-stu-id="8cd11-126">**Save** your changes.</span></span> <span data-ttu-id="8cd11-127">展開が開始されると、値は、バインド ファイルから追加されます。</span><span class="sxs-lookup"><span data-stu-id="8cd11-127">When the deploy is initiated, the values are added from the binding file.</span></span>

## <a name="see-also"></a><span data-ttu-id="8cd11-128">参照</span><span class="sxs-lookup"><span data-stu-id="8cd11-128">See also</span></span>
[<span data-ttu-id="8cd11-129">Visual Studio Team Services の自動展開を構成します。</span><span class="sxs-lookup"><span data-stu-id="8cd11-129">Configure automatic deployment with Visual Studio Team Services</span></span>](configure-automatic-deployment-with-visual-studio-team-services-in-biztalk.md)  
[<span data-ttu-id="8cd11-130">Feature Pack の構成</span><span class="sxs-lookup"><span data-stu-id="8cd11-130">Configure the feature pack</span></span>](configure-the-feature-pack.md)