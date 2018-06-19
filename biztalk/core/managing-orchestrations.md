---
title: オーケストレーションの管理 |Microsoft ドキュメント
description: BizTalk server の開始を含むオーケストレーションを使用、停止、バインド、構成、追跡を有効にする、中断へのリンクと詳細
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2553eec3-b863-45fb-90af-7eddcfa7add7
caps.latest.revision: 31
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 18cd12c202822c4d9ff849cc762b55e8f4880d80
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262650"
---
# <a name="manage-orchestrations"></a><span data-ttu-id="dd3f7-103">オーケストレーションを管理します。</span><span class="sxs-lookup"><span data-stu-id="dd3f7-103">Manage Orchestrations</span></span>

## <a name="overview"></a><span data-ttu-id="dd3f7-104">概要</span><span class="sxs-lookup"><span data-stu-id="dd3f7-104">Overview</span></span>
<span data-ttu-id="dd3f7-105">ここでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールを使ってオーケストレーションを管理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="dd3f7-105">This section provides instructions on using the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console to manage orchestrations.</span></span> <span data-ttu-id="dd3f7-106">オーケストレーションとは、実行可能なビジネス プロセスのことです。</span><span class="sxs-lookup"><span data-stu-id="dd3f7-106">An orchestration is an executable business process.</span></span> <span data-ttu-id="dd3f7-107">オーケストレーションの背景については、次を参照してください。[オーケストレーション](../core/orchestrations.md)です。</span><span class="sxs-lookup"><span data-stu-id="dd3f7-107">For background information about orchestrations, see [Orchestrations](../core/orchestrations.md).</span></span>  

## <a name="add-to-application"></a><span data-ttu-id="dd3f7-108">アプリケーションに追加します。</span><span class="sxs-lookup"><span data-stu-id="dd3f7-108">Add to application</span></span>  
 <span data-ttu-id="dd3f7-109">オーケストレーションは、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] で、BizTalk アセンブリとしてビルドおよびコンパイルされます。</span><span class="sxs-lookup"><span data-stu-id="dd3f7-109">Orchestrations are built in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] and compiled into BizTalk assemblies.</span></span> <span data-ttu-id="dd3f7-110">オーケストレーションを個別にアプリケーションへ追加することはできません。オーケストレーションは次のようにしてアプリケーションに追加されます。</span><span class="sxs-lookup"><span data-stu-id="dd3f7-110">You cannot add an orchestration to an application individually; an orchestration is added to an application as follows:</span></span>  
  
-   <span data-ttu-id="dd3f7-111">」の説明に従って、アプリケーションにオーケストレーションを含む BizTalk アセンブリを追加すると[BizTalk アセンブリをアプリケーションに追加する方法](../core/how-to-add-a-biztalk-assembly-to-an-application.md)です。</span><span class="sxs-lookup"><span data-stu-id="dd3f7-111">When you add a BizTalk assembly containing an orchestration to the application, as described in [How to Add a BizTalk Assembly to an Application](../core/how-to-add-a-biztalk-assembly-to-an-application.md).</span></span>  
  
-   <span data-ttu-id="dd3f7-112">」の説明に従って、オーケストレーションを含む BizTalk アセンブリを含むアプリケーションを .msi ファイルをインポートしたとき[を BizTalk アプリケーションをインポートする方法](../core/how-to-import-a-biztalk-application.md)です。</span><span class="sxs-lookup"><span data-stu-id="dd3f7-112">When you import an .msi file into an application that includes a BizTalk assembly containing an orchestration, as described in [How to Import a BizTalk Application](../core/how-to-import-a-biztalk-application.md).</span></span>  
  
-   <span data-ttu-id="dd3f7-113">開発者が展開したときに、アプリケーションからオーケストレーションを含むアセンブリ[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]」の説明に従って、 [BizTalk アプリケーションに Visual Studio から BizTalk アセンブリを展開する](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)です。</span><span class="sxs-lookup"><span data-stu-id="dd3f7-113">When a developer deploys into an application an assembly containing an orchestration from [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], as described in [Deploying BizTalk Assemblies from Visual Studio into a BizTalk Application](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md).</span></span>  

## <a name="biztalk-administration-tasks"></a><span data-ttu-id="dd3f7-114">BizTalk 管理コンソール タスク</span><span class="sxs-lookup"><span data-stu-id="dd3f7-114">BizTalk Administration tasks</span></span>  
 <span data-ttu-id="dd3f7-115">管理コンソールでは、次のアクションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="dd3f7-115">You use the administration console to perform the following actions, as described in this section:</span></span>  
  
-   <span data-ttu-id="dd3f7-116">オーケストレーションのバインドを構成 (つまり、オーケストレーションを適切な送信/受信ポートおよびホストにバインド) したり、これらのバインドをオーケストレーションから削除する。</span><span class="sxs-lookup"><span data-stu-id="dd3f7-116">Configure bindings for the orchestration by binding the orchestration to the appropriate send and receive ports and host, or remove these bindings from the orchestration.</span></span>  
  
-   <span data-ttu-id="dd3f7-117">オーケストレーションのメッセージ追跡を構成する。</span><span class="sxs-lookup"><span data-stu-id="dd3f7-117">Configure message tracking for the orchestration.</span></span>  
  
-   <span data-ttu-id="dd3f7-118">オーケストレーションのインスタンス情報を表示する。</span><span class="sxs-lookup"><span data-stu-id="dd3f7-118">View instance information for the orchestration.</span></span>  
  
-   <span data-ttu-id="dd3f7-119">オーケストレーションを適切なホストに参加させる/オーケストレーションをホストから参加解除する。</span><span class="sxs-lookup"><span data-stu-id="dd3f7-119">Enlist the orchestration to the appropriate host or unenlist the orchestration from the host.</span></span>  
  
-   <span data-ttu-id="dd3f7-120">オーケストレーションによるメッセージの処理を開始/中止する。</span><span class="sxs-lookup"><span data-stu-id="dd3f7-120">Start or stop the orchestration so that it starts or stops processing messages.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dd3f7-121">Microsoft Windows Management Instrumentation (WMI) のオブジェクト モデルを使用して、管理タスクを自動化するスクリプトを作成および実行できます。</span><span class="sxs-lookup"><span data-stu-id="dd3f7-121">You can use Microsoft Windows Management Instrumentation (WMI) Object Model to create and run scripts that automate administrative tasks.</span></span> <span data-ttu-id="dd3f7-122">WMI の使用については、次を参照してください。、 **WMI クラス参照**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。</span><span class="sxs-lookup"><span data-stu-id="dd3f7-122">For information about using WMI, see the **WMI Class Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span> 
  
> [!NOTE]
>  <span data-ttu-id="dd3f7-123">開発者は、デザイナーを使用するオーケストレーション、オーケストレーションを作成する」の説明に従って[オーケストレーション デザイナーを使用してオーケストレーションを作成する](../core/creating-orchestrations-using-orchestration-designer.md)です。</span><span class="sxs-lookup"><span data-stu-id="dd3f7-123">The developer uses Orchestration Designer to create orchestrations, as described in [Creating Orchestrations Using Orchestration Designer](../core/creating-orchestrations-using-orchestration-designer.md).</span></span> <span data-ttu-id="dd3f7-124">開発者は、このセクションで説明する管理コンソールを使用して、開発プロセス中にオーケストレーションを管理できます。</span><span class="sxs-lookup"><span data-stu-id="dd3f7-124">The developer can manage orchestrations during the development process by using the administration console, as described in this section.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="dd3f7-125">次の手順</span><span class="sxs-lookup"><span data-stu-id="dd3f7-125">Next steps</span></span>
  
-   [<span data-ttu-id="dd3f7-126">オーケストレーションのバインドを構成します。</span><span class="sxs-lookup"><span data-stu-id="dd3f7-126">Configure Bindings for an Orchestration</span></span>](../core/how-to-configure-bindings-for-an-orchestration.md)  
  
-   [<span data-ttu-id="dd3f7-127">オーケストレーションをバインド解除します。</span><span class="sxs-lookup"><span data-stu-id="dd3f7-127">Unbind an Orchestration</span></span>](../core/how-to-unbind-an-orchestration.md)  
  
-   [<span data-ttu-id="dd3f7-128">オーケストレーションの追跡を構成します。</span><span class="sxs-lookup"><span data-stu-id="dd3f7-128">Configure Tracking for an Orchestration</span></span>](../core/how-to-configure-tracking-for-an-orchestration.md)  
  
-   [<span data-ttu-id="dd3f7-129">オーケストレーションのインスタンス情報の表示</span><span class="sxs-lookup"><span data-stu-id="dd3f7-129">View Instance Information for an Orchestration</span></span>](../core/how-to-view-instance-information-for-an-orchestration.md)  
  
-   [<span data-ttu-id="dd3f7-130">オーケストレーションをアプリケーションから削除します。</span><span class="sxs-lookup"><span data-stu-id="dd3f7-130">Remove an Orchestration from an Application</span></span>](../core/how-to-remove-an-orchestration-from-an-application.md)  
  
-   [<span data-ttu-id="dd3f7-131">オーケストレーションを参加させる</span><span class="sxs-lookup"><span data-stu-id="dd3f7-131">Enlist an Orchestration</span></span>](../core/how-to-enlist-an-orchestration.md)  
  
-   [<span data-ttu-id="dd3f7-132">オーケストレーションを参加解除します。</span><span class="sxs-lookup"><span data-stu-id="dd3f7-132">Unenlist an Orchestration</span></span>](../core/how-to-unenlist-an-orchestration.md)  
  
-   [<span data-ttu-id="dd3f7-133">オーケストレーションを開始します。</span><span class="sxs-lookup"><span data-stu-id="dd3f7-133">Start an Orchestration</span></span>](../core/how-to-start-an-orchestration.md)  
  
-   [<span data-ttu-id="dd3f7-134">オーケストレーションを停止します。</span><span class="sxs-lookup"><span data-stu-id="dd3f7-134">Stop an Orchestration</span></span>](../core/how-to-stop-an-orchestration.md)  
  
-   [<span data-ttu-id="dd3f7-135">中断、再開、およびオーケストレーション インスタンスの終了</span><span class="sxs-lookup"><span data-stu-id="dd3f7-135">Suspend, Resume, and Terminate Orchestration Instances</span></span>](../core/how-to-suspend-resume-and-terminate-orchestration-instances.md)  
  
-   [<span data-ttu-id="dd3f7-136">オーケストレーションをアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="dd3f7-136">Upgrade an Orchestration</span></span>](../core/how-to-upgrade-an-orchestration.md)