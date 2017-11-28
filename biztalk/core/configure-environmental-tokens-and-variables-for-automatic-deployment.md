---
title: "環境のトークンと自動展開用の変数の構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.prod: biztalk-server
ms.topic: article
ms.assetid: 28bb2d4a-f45c-466d-ba65-0ca8cad0bffd
caps.latest.revision: "4"
author: tordgladnordahl
ms.author: tonordah
manager: anneta
ms.openlocfilehash: 7d148f79fceb68b24feb45882ab89767369ed7e6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="configure-environmental-tokens-and-variables-for-automatic-deployment"></a><span data-ttu-id="41f99-102">環境のトークンと自動展開用の変数を構成します。</span><span class="sxs-lookup"><span data-stu-id="41f99-102">Configure environmental tokens and variables for automatic deployment</span></span>
<span data-ttu-id="41f99-103">Visual Studio Team Services (VSTS) の変数を使用して、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]バインド ファイルです。</span><span class="sxs-lookup"><span data-stu-id="41f99-103">Use Visual Studio Team Services (VSTS) variables in your [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] binding files.</span></span>

## <a name="overview"></a><span data-ttu-id="41f99-104">概要</span><span class="sxs-lookup"><span data-stu-id="41f99-104">Overview</span></span>
<span data-ttu-id="41f99-105">環境では、VSTS は、変数を追加したり、値に設定します。</span><span class="sxs-lookup"><span data-stu-id="41f99-105">In a VSTS environment, you can add variables, and set them to a value.</span></span> <span data-ttu-id="41f99-106">たとえば、作成することができます、 *sendPortPath*変数で物理フォルダーにその値を設定、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="41f99-106">For example, you can create a *sendPortPath* variable, and set its value to a physical folder on your [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)].</span></span> 

<span data-ttu-id="41f99-107">内で、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]アプリケーション バインド ファイル、構成可能な変数できます受信場所の名前などの XML タグ内で何もするホスト、送信ポート、URI に表示され、します。</span><span class="sxs-lookup"><span data-stu-id="41f99-107">Within the [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] application binding file, the configurable variables can be anything within an XML tag, such as the receive location name, host, send port URI, and so on.</span></span> 

<span data-ttu-id="41f99-108">これらの変数は、VSTS の環境に固有であり、同じアプリケーションを複数の展開に使用できる[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]環境。</span><span class="sxs-lookup"><span data-stu-id="41f99-108">These variables are specific to your VSTS environment, and can be used to deploy the same application to multiple [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] environments.</span></span> 

<span data-ttu-id="41f99-109">このトピックでは、VSTS ファイル内の変数、バインディング、および VSTS 内の変数を作成する方法追加する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="41f99-109">In this topic, we show you how add the VSTS variable in your binding file, and how to create the variable within VSTS.</span></span> 

## <a name="configure-the-variables-in-your-biztalk-binding-file"></a><span data-ttu-id="41f99-110">BizTalk バインド ファイル内の変数を構成します。</span><span class="sxs-lookup"><span data-stu-id="41f99-110">Configure the variables in your BizTalk Binding file</span></span>

<span data-ttu-id="41f99-111">次の例の一部、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]バインド ファイルの場合は、トークンを適用する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="41f99-111">The following example is a part of a [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] binding file, and shows how to apply the tokens.</span></span>

1. <span data-ttu-id="41f99-112">アプリケーションのバインド ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="41f99-112">Open the application binding file:</span></span>

    ![BizTalk Feature Pack 1 をバインド 1](../core/media/biztalk-feature-pack-1-binding-1.png)

2. <span data-ttu-id="41f99-114">変更する要素を検索します。</span><span class="sxs-lookup"><span data-stu-id="41f99-114">Find the element you want to change:</span></span>

    ![BizTalk Feature Pack 2 をバインド 1](../core/media/biztalk-feature-pack-1-binding-2.png)
    
3. <span data-ttu-id="41f99-116">設定済みの値を削除して、変数で置き換えます:`$(YourValue)`です。</span><span class="sxs-lookup"><span data-stu-id="41f99-116">Remove the populated value, and replace it with you variables: `$(YourValue)`.</span></span> <span data-ttu-id="41f99-117">たとえば、入力`$(SendPort1)`:</span><span class="sxs-lookup"><span data-stu-id="41f99-117">For example, enter `$(SendPort1)`:</span></span> 

    ![BizTalk Feature Pack 1 が 3 のバインド](../core/media/biztalk-feature-pack-1-binding-3.png)


4. <span data-ttu-id="41f99-119">終了したら、バインド ファイルを保存し、JSON ビルド テンプレートに適用します。</span><span class="sxs-lookup"><span data-stu-id="41f99-119">When done, save the binding file, and apply it to your JSON build template.</span></span>
5. <span data-ttu-id="41f99-120">Visual Studio チーム サービス、ソリューションにサインインし、選択**ビルドし、リリースの**します。</span><span class="sxs-lookup"><span data-stu-id="41f99-120">Sign in to your Visual Studio Team Service solution, and select **Build and release**.</span></span>
6. <span data-ttu-id="41f99-121">移動して**リリース**です。</span><span class="sxs-lookup"><span data-stu-id="41f99-121">Go to **Release**.</span></span> <span data-ttu-id="41f99-122">選択、**リリース定義**、新規に作成します。</span><span class="sxs-lookup"><span data-stu-id="41f99-122">Select your **Release definition**, or create a new one.</span></span>
7. <span data-ttu-id="41f99-123">**環境****新しい環境を追加**、または既存の環境に変更します。</span><span class="sxs-lookup"><span data-stu-id="41f99-123">Under **Environments**, select **Add a new environment**, or change to an existing environment:</span></span> 

    ![新しい環境を追加します。](../core/media/add-a-new-environment.png)

8. <span data-ttu-id="41f99-125">省略記号ボタンをクリックし、選択**変数構成**:</span><span class="sxs-lookup"><span data-stu-id="41f99-125">Click the ellipses, and select **configure variables**:</span></span>

    ![変数を構成します。](../core/media/configure-variables.png)

9. <span data-ttu-id="41f99-127">バインド ファイルに作成されたトークンの名前を使用して、各環境の変数を追加することで、値が異なる複数の環境にアプリケーションを展開できます。</span><span class="sxs-lookup"><span data-stu-id="41f99-127">By adding the variables for each environment, using the token names created in the binding file, you can deploy your applications to multiple environments with different values:</span></span>

    ![特定の環境変数](../core/media/environment-specific-variables.png)
    
10. <span data-ttu-id="41f99-129">選択**OK**を新しい変数を保存します。</span><span class="sxs-lookup"><span data-stu-id="41f99-129">Select **OK** to save the new variables.</span></span>
11. <span data-ttu-id="41f99-130">ビルドが開始されると、値は、バインド ファイルから追加されます。</span><span class="sxs-lookup"><span data-stu-id="41f99-130">Once the build is initiated, the values are added from binding file.</span></span>

## <a name="next-step"></a><span data-ttu-id="41f99-131">次の手順</span><span class="sxs-lookup"><span data-stu-id="41f99-131">Next step</span></span>
[<span data-ttu-id="41f99-132">VSTS を BizTalk アプリケーションを追加します。</span><span class="sxs-lookup"><span data-stu-id="41f99-132">Add a BizTalk application to VSTS</span></span>](../core/add-a-biztalk-server-application-to-visual-studio-team-services.md)