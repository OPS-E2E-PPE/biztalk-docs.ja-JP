---
title: 環境トークンと変数の作成 |Microsoft Docs"
description: 環境のトークンを使用するバインド ファイルを更新して、BizTalk Server アプリケーションの展開を自動化する VSTS での変数を作成
ms.custom: ''
ms.date: 11/08/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.prod: biztalk-server
ms.topic: article
ms.assetid: 28bb2d4a-f45c-466d-ba65-0ca8cad0bffd
caps.latest.revision: 4
author: tordgladnordahl
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2d3af4817e2974d1196fb08acf94195b997b0c67
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65356434"
---
# <a name="configure-environmental-tokens-and-variables-for-automatic-deployment"></a><span data-ttu-id="d29de-103">環境トークンと自動展開用の変数を構成します。</span><span class="sxs-lookup"><span data-stu-id="d29de-103">Configure environmental tokens and variables for automatic deployment</span></span>
<span data-ttu-id="d29de-104">Visual Studio Team Services (VSTS) の変数を使用して、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]バインド ファイル。</span><span class="sxs-lookup"><span data-stu-id="d29de-104">Use Visual Studio Team Services (VSTS) variables in your [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] binding files.</span></span>

## <a name="overview"></a><span data-ttu-id="d29de-105">概要</span><span class="sxs-lookup"><span data-stu-id="d29de-105">Overview</span></span>
<span data-ttu-id="d29de-106">VSTS 環境では、変数を追加し、それらの値に設定します。</span><span class="sxs-lookup"><span data-stu-id="d29de-106">In a VSTS environment, you can add variables, and set them to a value.</span></span> <span data-ttu-id="d29de-107">たとえば、作成、 *sendPortPath*変数で、物理フォルダーにその値を設定、 [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="d29de-107">For example, you can create a *sendPortPath* variable, and set its value to a physical folder on your [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)].</span></span> 

<span data-ttu-id="d29de-108">内で、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]アプリケーションのバインド ファイル、構成可能な変数受信場所の名前などの XML タグ内のすべて、ホスト、送信ポート、URI でき具合です。</span><span class="sxs-lookup"><span data-stu-id="d29de-108">Within the [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] application binding file, the configurable variables can be anything within an XML tag, such as the receive location name, host, send port URI, and so on.</span></span> 

<span data-ttu-id="d29de-109">これらの変数は、VSTS の環境に固有であり、同じアプリケーションを複数のデプロイに使用できる[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]環境。</span><span class="sxs-lookup"><span data-stu-id="d29de-109">These variables are specific to your VSTS environment, and can be used to deploy the same application to multiple [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] environments.</span></span> 

<span data-ttu-id="d29de-110">紹介する VSTS 内の変数を作成する方法と、バインド ファイルに、VSTS の変数を追加する方法。</span><span class="sxs-lookup"><span data-stu-id="d29de-110">We show you how to add the VSTS variable in your binding file, and how to create the variable within VSTS.</span></span> 

## <a name="add-variables-to-the-binding-file"></a><span data-ttu-id="d29de-111">変数をバインド ファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="d29de-111">Add variables to the binding file</span></span>

1. <span data-ttu-id="d29de-112">アプリケーションのバインド ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="d29de-112">Open the application binding file:</span></span>

    ![バインド ファイルを開く](../core/media/biztalk-feature-pack-1-binding-1.png)

2. <span data-ttu-id="d29de-114">変更する要素を検索するには。</span><span class="sxs-lookup"><span data-stu-id="d29de-114">Find the element you want to change:</span></span>

    ![要素を選択します。](../core/media/biztalk-feature-pack-1-binding-2.png)
    
3. <span data-ttu-id="d29de-116">設定の値を削除し、変数で置き換えます:`$(YourValue)`します。</span><span class="sxs-lookup"><span data-stu-id="d29de-116">Remove the populated value, and replace it with you variables: `$(YourValue)`.</span></span> <span data-ttu-id="d29de-117">たとえば、入力`$(SendPort1)`:</span><span class="sxs-lookup"><span data-stu-id="d29de-117">For example, enter `$(SendPort1)`:</span></span> 

    ![バインド ファイル](../core/media/biztalk-feature-pack-1-binding-3.png)

4. <span data-ttu-id="d29de-119">完了したら、バインド ファイルを保存し、JSON のビルド テンプレートに追加 (手順[手順 1。アプリケーションの追加のプロジェクトと更新プログラムの .json テンプレート](feature-pack-add-application-project.md))。</span><span class="sxs-lookup"><span data-stu-id="d29de-119">When done, save the binding file, and add it to your JSON build template (steps in [Step 1: Add Application project & update .json template](feature-pack-add-application-project.md)).</span></span>

## <a name="create-the-variables-in-vsts"></a><span data-ttu-id="d29de-120">VSTS での変数を作成します。</span><span class="sxs-lookup"><span data-stu-id="d29de-120">Create the variables in VSTS</span></span>

1. <span data-ttu-id="d29de-121">VSTS アカウントに次のように選択します。**ビルドとリリース**、を選択し**リリース**します。</span><span class="sxs-lookup"><span data-stu-id="d29de-121">In your VSTS account, select **Build and release**, and select **Releases**.</span></span>

2. <span data-ttu-id="d29de-122">選択、**リリース定義**、選び**変数**:</span><span class="sxs-lookup"><span data-stu-id="d29de-122">Select your **Release definition**, and select **Variables**:</span></span>  

    ![バインド ファイル](../core/media/vsts-release-variables.png)

3. <span data-ttu-id="d29de-124">選択**追加**、変数の名前と値を作成します。</span><span class="sxs-lookup"><span data-stu-id="d29de-124">Select **Add**, and create the variable names and values:</span></span>   

    ![変数を構成します。](../core/media/environment-specific-variables.png)

4. <span data-ttu-id="d29de-126">**保存**変更します。</span><span class="sxs-lookup"><span data-stu-id="d29de-126">**Save** your changes.</span></span> <span data-ttu-id="d29de-127">デプロイが開始されると、バインド ファイルから値が追加されます。</span><span class="sxs-lookup"><span data-stu-id="d29de-127">When the deploy is initiated, the values are added from the binding file.</span></span>

## <a name="see-also"></a><span data-ttu-id="d29de-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="d29de-128">See also</span></span>
[<span data-ttu-id="d29de-129">Visual Studio Team Services での自動展開を構成します。</span><span class="sxs-lookup"><span data-stu-id="d29de-129">Configure automatic deployment with Visual Studio Team Services</span></span>](configure-automatic-deployment-with-visual-studio-team-services-in-biztalk.md)  
[<span data-ttu-id="d29de-130">Feature pack を構成します。</span><span class="sxs-lookup"><span data-stu-id="d29de-130">Configure the feature pack</span></span>](configure-the-feature-pack.md)