---
title: "レッスン 4: のビルドと、アセンブリの展開 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- building assemblies
- deploying, assemblies
- assemblies, building
- assemblies, deploying
ms.assetid: 58397c35-6048-4ac9-a8b8-a528dd1cb82a
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3ca5a539fdaea9026a7c18cae6f076e72df9efe2
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/17/2018
---
# <a name="lesson-4-building-and-deploying-the-assembly"></a><span data-ttu-id="28b4e-102">レッスン 4: のビルドと、アセンブリの展開</span><span class="sxs-lookup"><span data-stu-id="28b4e-102">Lesson 4: Building and Deploying the Assembly</span></span>
<span data-ttu-id="28b4e-103">このレッスンでは、ビルドし、前のレッスンで作成したスキーマを含むアセンブリを生成するプロジェクトを配置します。</span><span class="sxs-lookup"><span data-stu-id="28b4e-103">In this lesson, you build and deploy the project to generate an assembly that contains the schemas you created in the previous lessons.</span></span> <span data-ttu-id="28b4e-104">このタスクにより、これまでに作成した作業ではコンパイル エラーがないです。</span><span class="sxs-lookup"><span data-stu-id="28b4e-104">This task ensures there are no compilation errors in the work you created so far.</span></span>  
  
 <span data-ttu-id="28b4e-105">アセンブリを展開する構成データベースにアセンブリのコピーを格納し、グローバル アセンブリ キャッシュ (GAC) にインストールします。</span><span class="sxs-lookup"><span data-stu-id="28b4e-105">Deploying an assembly places a copy of the assembly in the Configuration database and installs it in the global assembly cache (GAC).</span></span> <span data-ttu-id="28b4e-106">次の手順では、ソリューション エクスプ ローラーから直接展開します。</span><span class="sxs-lookup"><span data-stu-id="28b4e-106">In the following procedure, you deploy directly from Solution Explorer.</span></span>  
  
 <span data-ttu-id="28b4e-107">アセンブリ (DLL ファイル) に、プロジェクトがコンパイル時に[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]で DLL を保存、 \<*ドライブ*\>: \Program Files\\ [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk Accelerator forプロジェクト フォルダー内に SWIFT\bin\Development フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="28b4e-107">When the project compiles into an assembly (DLL file), [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] saves the DLL in the \<*drive*\>:\Program Files\\[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk Accelerator for SWIFT\bin\Development folder within the project folder.</span></span>  
  
### <a name="to-build-and-deploy-the-project"></a><span data-ttu-id="28b4e-108">プロジェクトをビルドして展開するには</span><span class="sxs-lookup"><span data-stu-id="28b4e-108">To build and deploy the project</span></span>  
  
1.  <span data-ttu-id="28b4e-109">ソリューション エクスプ ローラーで右クリック**SWIFTSchemas**、クリックして**ビルド**です。</span><span class="sxs-lookup"><span data-stu-id="28b4e-109">In Solution Explorer, right-click **SWIFTSchemas**, and then click **Build**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="28b4e-110">いることを確認**ビルドに成功した**画面の左下隅に表示されます。</span><span class="sxs-lookup"><span data-stu-id="28b4e-110">Verify that **Build Succeeded** appears in the lower left-hand corner of the screen.</span></span> <span data-ttu-id="28b4e-111">コンパイル時に、一部のステータス メッセージを参照してください可能性があります。</span><span class="sxs-lookup"><span data-stu-id="28b4e-111">During the compilation process, you may see some status messages.</span></span> <span data-ttu-id="28b4e-112">SWIFT のスキーマを処理する場合、これらのメッセージは正常です。</span><span class="sxs-lookup"><span data-stu-id="28b4e-112">These messages are normal when dealing with the SWIFT schemas.</span></span> <span data-ttu-id="28b4e-113">すべてのエラーが表示されない場合は、ツールをクリックし、[BizTalk Server 管理を開くには、BizTalk Server 管理コンソール] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="28b4e-113">If any errors appear, click Tools, and then click BizTalk Server Administration to open the BizTalk Server Administration Console.</span></span> <span data-ttu-id="28b4e-114">BizTalk 管理コンソールで、イベント ビューアーと正常性と動作状況の追跡 (HAT) 機能を使用して、、エラーを修正して再構築します。</span><span class="sxs-lookup"><span data-stu-id="28b4e-114">Use the Event Viewer and the Health and Activity Tracking (HAT) feature in the BizTalk Administration Console to correct your errors and rebuild.</span></span>  
  
2.  <span data-ttu-id="28b4e-115">使用して[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]エクスプ ローラーで、参照、  **\<*ドライブ*\>: \labs\SWIFTProject\SWIFTSchemas\bin\Development**フォルダー、いることを確認し、 **SWIFTSchemas.dll**このフォルダーにファイルが存在します。</span><span class="sxs-lookup"><span data-stu-id="28b4e-115">Using [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Explorer, browse to the **\<*drive*\>:\labs\SWIFTProject\SWIFTSchemas\bin\Development** folder, and verify that the **SWIFTSchemas.dll** file exists in this folder.</span></span>  
  
3.  <span data-ttu-id="28b4e-116">ソリューション エクスプ ローラーで右クリック**SWIFTSchemas**、クリックして**展開**です。</span><span class="sxs-lookup"><span data-stu-id="28b4e-116">In Solution Explorer, right-click **SWIFTSchemas**, and then click **Deploy**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="28b4e-117">いることを確認**配置正常終了**画面の左下隅に表示されます。</span><span class="sxs-lookup"><span data-stu-id="28b4e-117">Verify that **Deploy Succeeded** appears in the lower left corner of the screen.</span></span>  
  
### <a name="to-confirm-deployment-success"></a><span data-ttu-id="28b4e-118">展開の成功を確認するには</span><span class="sxs-lookup"><span data-stu-id="28b4e-118">To confirm deployment success</span></span>  
  
1.  <span data-ttu-id="28b4e-119">をクリックして**ビュー**  をクリックし、 **BizTalk エクスプ ローラー**です。</span><span class="sxs-lookup"><span data-stu-id="28b4e-119">Click **View** and then click **BizTalk Explorer**.</span></span>  
  
2.  <span data-ttu-id="28b4e-120">展開、**アセンブリ**ノードいることを確認および**SWIFTSchemas (1.0.0.0)**一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="28b4e-120">Expand the **Assemblies** node and confirm that **SWIFTSchemas (1.0.0.0)** appears in the list.</span></span>  
  
     <span data-ttu-id="28b4e-121">SWIFTSchemas が一覧に表示された場合、アセンブリが正常に展開されていると参照および使用できるを他の[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]プロジェクト。</span><span class="sxs-lookup"><span data-stu-id="28b4e-121">If SWIFTSchemas appears in the list, the assembly deployed successfully and can be referenced and used from other [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] projects.</span></span>  
  
 <span data-ttu-id="28b4e-122">進みます[第 3 章: パイプライン プロジェクトを追加する](../../adapters-and-accelerators/accelerator-swift/module-3-adding-a-pipeline-project.md)です。</span><span class="sxs-lookup"><span data-stu-id="28b4e-122">Proceed to [Module 3: Adding a Pipeline Project](../../adapters-and-accelerators/accelerator-swift/module-3-adding-a-pipeline-project.md).</span></span>