---
redirect_url: /biztalk/core/feature-pack-add-application-project/
redirect_document_id: true
ROBOTS: NOINDEX
title: Visual Studio Team Services への BizTalk Server アプリケーションの追加 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b2c7a1ff-0f26-45f3-9a9b-4c99a67b51a9
caps.latest.revision: 4
author: tordgladnordahl
ms.author: tonordah
manager: anneta
ms.openlocfilehash: a5ab2e23c4ccca6154334af234acdbd3f1847b26
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65360979"
---
# <a name="add-a-biztalk-server-application-to-visual-studio-team-services"></a><span data-ttu-id="9c548-102">Visual Studio Team Services への BizTalk Server アプリケーションを追加します。</span><span class="sxs-lookup"><span data-stu-id="9c548-102">Add a BizTalk Server application to Visual Studio Team Services</span></span>
<span data-ttu-id="9c548-103">追加、 [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] vsts 継続的インテグレーションを使用してを自動的にデプロイするプロジェクト。</span><span class="sxs-lookup"><span data-stu-id="9c548-103">Add a [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] project to VSTS to automatically deploy using continuous integration.</span></span>  

<span data-ttu-id="9c548-104">**以降で[!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]** 、自動的にするようにアプリケーションをデプロイすることができます、 [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] Visual Studio Team Services (VSTS) を使用する環境。</span><span class="sxs-lookup"><span data-stu-id="9c548-104">**Starting with [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]**, you can automatically deploy your applications to your [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] environments using Visual Studio Team Services (VSTS).</span></span> 

<span data-ttu-id="9c548-105">このトピックは、概要し、Visual Studio からソリューションを配置する主な手順を一覧表示、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="9c548-105">This topics provides an overview, and lists the key steps to deploy your solution from Visual Studio to your [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)].</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="9c548-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="9c548-106">Prerequisites</span></span>
* <span data-ttu-id="9c548-107">インストール[Feature Pack 1](https://www.microsoft.com/download/details.aspx?id=55100)で、 [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9c548-107">Install [Feature Pack 1](https://www.microsoft.com/download/details.aspx?id=55100) on your [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]</span></span>
* [<span data-ttu-id="9c548-108">ステップ 3:ビルドとリリース定義を作成します。</span><span class="sxs-lookup"><span data-stu-id="9c548-108">Step 3: Create the build and release definitions</span></span>](../core/feature-pack-add-build-release-definitions.md)
* <span data-ttu-id="9c548-109">知識と経験 Git と Visual Studio でリポジトリを使用します。</span><span class="sxs-lookup"><span data-stu-id="9c548-109">Knowledge and experience working with Git and repositories in Visual Studio.</span></span> <span data-ttu-id="9c548-110">新しいリポジトリとバージョン管理する場合は、これらの優れたリソースがあります。</span><span class="sxs-lookup"><span data-stu-id="9c548-110">If you're brand new to repositories and version control, these may be good resources:</span></span> 

    [<span data-ttu-id="9c548-111">Git についての情報します。</span><span class="sxs-lookup"><span data-stu-id="9c548-111">Learn Git</span></span>](https://www.visualstudio.com/learn-git/)  
    [<span data-ttu-id="9c548-112">Git と Team Services</span><span class="sxs-lookup"><span data-stu-id="9c548-112">Git and Team Services</span></span>](https://www.visualstudio.com/docs/git/overview)
* <span data-ttu-id="9c548-113">知識と経験で BizTalk プロジェクトでの作業 [!INCLUDE[btsVStudioNoVersion_md](../includes/btsvstudionoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9c548-113">Knowledge and experience working with BizTalk projects in [!INCLUDE[btsVStudioNoVersion_md](../includes/btsvstudionoversion-md.md)]</span></span>

## <a name="add-biztalk-project-to-vsts"></a><span data-ttu-id="9c548-114">BizTalk プロジェクトを VSTS に追加します。</span><span class="sxs-lookup"><span data-stu-id="9c548-114">Add BizTalk project to VSTS</span></span>
1. <span data-ttu-id="9c548-115">**Visual Studio**への接続、**ソース リポジトリ**、および**複製**コンピューターにします。</span><span class="sxs-lookup"><span data-stu-id="9c548-115">In **Visual Studio**, connect to your **Source repository**, and **Clone** it to your machine.</span></span>
2. <span data-ttu-id="9c548-116">開くか作成、 **BizTalk プロジェクト**(.btproj)。</span><span class="sxs-lookup"><span data-stu-id="9c548-116">Open or Create a **BizTalk Project** (.btproj).</span></span>

   > [!NOTE]
   > <span data-ttu-id="9c548-117">複数のプロジェクトは、同じソリューションに追加できます。</span><span class="sxs-lookup"><span data-stu-id="9c548-117">You can add multiple project into the same solution.</span></span>
   
3. <span data-ttu-id="9c548-118">新しい追加**アプリケーション用の BizTalk Server プロジェクト**(.btaproj)。</span><span class="sxs-lookup"><span data-stu-id="9c548-118">Add a new **BizTalk Server Application Project** (.btaproj).</span></span>
4. <span data-ttu-id="9c548-119">プロジェクトを右クリックし、**ソリューション エクスプ ローラー**、選択および**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="9c548-119">Right-click the project in the **Solution Explorer**, and select **Properties**.</span></span>
5. <span data-ttu-id="9c548-120">構成、**バージョン**への接続プロパティと、 **Visual Studio Team Services**アカウント。</span><span class="sxs-lookup"><span data-stu-id="9c548-120">Configure the **Version** and the connection properties to your **Visual Studio Team Services** account.</span></span>

    ![Visual Studio 構成 FP1 BizTalk](../core/media/visual-studio-configuration-fp1-biztalk.png)

6. <span data-ttu-id="9c548-122">すべてのアセンブリとアプリケーションに必要なアイテムを追加します。</span><span class="sxs-lookup"><span data-stu-id="9c548-122">Add all the assemblies and artifacts needed by your application.</span></span>
7. <span data-ttu-id="9c548-123">更新プログラム、 **binding.xml**正しいバインド情報を含むファイル。</span><span class="sxs-lookup"><span data-stu-id="9c548-123">Update the **binding.xml** file with the correct binding information.</span></span>
8. <span data-ttu-id="9c548-124">更新プログラム、 **BizTalkServerInventory.json**にインストールされる成果物を正しい順序ですべての成果物を[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="9c548-124">Update the **BizTalkServerInventory.json** with all the artifacts, and the correct order for the artifacts to be installed on the [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)].</span></span>
9. <span data-ttu-id="9c548-125">右クリックし、**ビルド**エラーの有無を確認するソリューションです。</span><span class="sxs-lookup"><span data-stu-id="9c548-125">Right-click and **build** your solution to check for any errors.</span></span> 
10. <span data-ttu-id="9c548-126">ビルドが正常に完了すると、ソリューションを右クリックし **デプロイ**します。</span><span class="sxs-lookup"><span data-stu-id="9c548-126">When the build completes successfully, right-click your solution, and select **Deploy**.</span></span>
11. <span data-ttu-id="9c548-127">アプリケーションに自動的にデプロイする必要があります、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="9c548-127">Your application should automatically deploy to your [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)].</span></span>

## <a name="see-also"></a><span data-ttu-id="9c548-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="9c548-128">See also</span></span>
[<span data-ttu-id="9c548-129">Feature Pack を構成します。</span><span class="sxs-lookup"><span data-stu-id="9c548-129">Configure the Feature Pack</span></span>](../core/configure-the-feature-pack.md)