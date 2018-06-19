---
redirect_url: /biztalk/core/feature-pack-add-application-project/
redirect_document_id: true
ROBOTS: NOINDEX
title: Visual Studio Team Services への BizTalk Server アプリケーションの追加 |Microsoft ドキュメント
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
ms.openlocfilehash: 1a6b7ba32c0077b3df107b00525bb34ef011e483
ms.sourcegitcommit: a0165ec2f1e8b58545638666b7bfa2bf440036fd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/09/2017
ms.locfileid: "24054578"
---
# <a name="add-a-biztalk-server-application-to-visual-studio-team-services"></a><span data-ttu-id="db0c5-102">Visual Studio Team Services への BizTalk Server アプリケーションを追加します。</span><span class="sxs-lookup"><span data-stu-id="db0c5-102">Add a BizTalk Server application to Visual Studio Team Services</span></span>
<span data-ttu-id="db0c5-103">追加、 [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] VSTS 継続的インテグレーションを使用して自動的に展開するプロジェクトです。</span><span class="sxs-lookup"><span data-stu-id="db0c5-103">Add a [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] project to VSTS to automatically deploy using continuous integration.</span></span>  

<span data-ttu-id="db0c5-104">**以降で[!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]** 、するようにアプリケーションを自動的に展開することができます、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]を Visual Studio Team Services (VSTS) を使用する環境です。</span><span class="sxs-lookup"><span data-stu-id="db0c5-104">**Starting with [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]**, you can automatically deploy your applications to your [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] environments using Visual Studio Team Services (VSTS).</span></span> 

<span data-ttu-id="db0c5-105">このトピックでは、概要を説明し、Visual Studio からソリューションを展開する主な手順を一覧表示、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="db0c5-105">This topics provides an overview, and lists the key steps to deploy your solution from Visual Studio to your [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)].</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="db0c5-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="db0c5-106">Prerequisites</span></span>
* <span data-ttu-id="db0c5-107">インストール[機能パック 1](https://www.microsoft.com/download/details.aspx?id=55100)で、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="db0c5-107">Install [Feature Pack 1](https://www.microsoft.com/download/details.aspx?id=55100) on your [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]</span></span>
* [<span data-ttu-id="db0c5-108">手順 3: ビルドの作成し、定義のリリース</span><span class="sxs-lookup"><span data-stu-id="db0c5-108">Step 3: Create the build and release definitions</span></span>](../core/feature-pack-add-build-release-definitions.md)
* <span data-ttu-id="db0c5-109">知識と経験 Git と Visual Studio でリポジトリを使用します。</span><span class="sxs-lookup"><span data-stu-id="db0c5-109">Knowledge and experience working with Git and repositories in Visual Studio.</span></span> <span data-ttu-id="db0c5-110">新しいリポジトリとバージョン管理する場合は、これら優れたリソースがあります。</span><span class="sxs-lookup"><span data-stu-id="db0c5-110">If you're brand new to repositories and version control, these may be good resources:</span></span> 

    [<span data-ttu-id="db0c5-111">Git を説明します。</span><span class="sxs-lookup"><span data-stu-id="db0c5-111">Learn Git</span></span>](https://www.visualstudio.com/learn-git/)  
    [<span data-ttu-id="db0c5-112">Git および Team Services</span><span class="sxs-lookup"><span data-stu-id="db0c5-112">Git and Team Services</span></span>](https://www.visualstudio.com/docs/git/overview)
* <span data-ttu-id="db0c5-113">知識と経験に BizTalk プロジェクトの操作[!INCLUDE[btsVStudioNoVersion_md](../includes/btsvstudionoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="db0c5-113">Knowledge and experience working with BizTalk projects in [!INCLUDE[btsVStudioNoVersion_md](../includes/btsvstudionoversion-md.md)]</span></span>

## <a name="add-biztalk-project-to-vsts"></a><span data-ttu-id="db0c5-114">VSTS を BizTalk プロジェクトを追加します。</span><span class="sxs-lookup"><span data-stu-id="db0c5-114">Add BizTalk project to VSTS</span></span>
1. <span data-ttu-id="db0c5-115">**Visual Studio**への接続、**ソース リポジトリ**、および**クローン**コンピューターにします。</span><span class="sxs-lookup"><span data-stu-id="db0c5-115">In **Visual Studio**, connect to your **Source repository**, and **Clone** it to your machine.</span></span>
2. <span data-ttu-id="db0c5-116">開くか作成、 **BizTalk プロジェクト**(.btproj)。</span><span class="sxs-lookup"><span data-stu-id="db0c5-116">Open or Create a **BizTalk Project** (.btproj).</span></span>

   > [!NOTE]
   > <span data-ttu-id="db0c5-117">複数のプロジェクトは、同じソリューションに追加できます。</span><span class="sxs-lookup"><span data-stu-id="db0c5-117">You can add multiple project into the same solution.</span></span>
   
3. <span data-ttu-id="db0c5-118">新しい**アプリケーション用の BizTalk Server プロジェクト**(.btaproj)。</span><span class="sxs-lookup"><span data-stu-id="db0c5-118">Add a new **BizTalk Server Application Project** (.btaproj).</span></span>
4. <span data-ttu-id="db0c5-119">プロジェクトを右クリックし、**ソリューション エクスプ ローラー**を選択して**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="db0c5-119">Right-click the project in the **Solution Explorer**, and select **Properties**.</span></span>
5. <span data-ttu-id="db0c5-120">構成、**バージョン**と接続プロパティを**Visual Studio Team Services**アカウント。</span><span class="sxs-lookup"><span data-stu-id="db0c5-120">Configure the **Version** and the connection properties to your **Visual Studio Team Services** account.</span></span>

    ![Visual Studio 構成 FP1 BizTalk](../core/media/visual-studio-configuration-fp1-biztalk.png)

6. <span data-ttu-id="db0c5-122">すべてのアセンブリと、アプリケーションで必要な成果物を追加します。</span><span class="sxs-lookup"><span data-stu-id="db0c5-122">Add all the assemblies and artifacts needed by your application.</span></span>
7. <span data-ttu-id="db0c5-123">更新プログラム、 **binding.xml**正しいバインド情報を含むファイルです。</span><span class="sxs-lookup"><span data-stu-id="db0c5-123">Update the **binding.xml** file with the correct binding information.</span></span>
8. <span data-ttu-id="db0c5-124">更新プログラム、 **BizTalkServerInventory.json** 、すべての成果物、およびにインストールされている成果物用に正しい順序で、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="db0c5-124">Update the **BizTalkServerInventory.json** with all the artifacts, and the correct order for the artifacts to be installed on the [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)].</span></span>
9. <span data-ttu-id="db0c5-125">右クリックし、**ビルド**ソリューションのすべてのエラーを確認します。</span><span class="sxs-lookup"><span data-stu-id="db0c5-125">Right-click and **build** your solution to check for any errors.</span></span> 
10. <span data-ttu-id="db0c5-126">ビルドが正常に完了すると、ソリューションを右クリックし **展開**です。</span><span class="sxs-lookup"><span data-stu-id="db0c5-126">When the build completes successfully, right-click your solution, and select **Deploy**.</span></span>
11. <span data-ttu-id="db0c5-127">自動的に展開する必要があります、アプリケーション、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="db0c5-127">Your application should automatically deploy to your [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)].</span></span>

## <a name="see-also"></a><span data-ttu-id="db0c5-128">参照</span><span class="sxs-lookup"><span data-stu-id="db0c5-128">See also</span></span>
[<span data-ttu-id="db0c5-129">この機能パックを構成します。</span><span class="sxs-lookup"><span data-stu-id="db0c5-129">Configure the Feature Pack</span></span>](../core/configure-the-feature-pack.md)