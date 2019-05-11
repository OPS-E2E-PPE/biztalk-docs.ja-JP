---
title: BizTalk アプリケーションについて | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BizTalk.System application, about BizTalk.System application
- applications, default
- BizTalk.System application
- artifacts, about artifacts
- applications
- applications, about applications
- applications, warnings
- applications, BizTalk.System
- what's new, applications
- BizTalk.System application, warnings
ms.assetid: 68b5527c-d5e1-453b-a51b-3fc1a1d5dce2
caps.latest.revision: 28
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bf72f7508444e456d938c4157e25cc9869e93e36
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395195"
---
# <a name="what-is-a-biztalk-application"></a><span data-ttu-id="cf096-103">BizTalk アプリケーションについて</span><span class="sxs-lookup"><span data-stu-id="cf096-103">What Is a BizTalk Application?</span></span>
<span data-ttu-id="cf096-104">BizTalk アプリケーションは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ビジネス ソリューションの展開、管理、およびトラブルシューティングをすばやく簡単に行えるようにする [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の新機能です。</span><span class="sxs-lookup"><span data-stu-id="cf096-104">The BizTalk application is a feature of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] that makes it quicker and easier to deploy, manage, and troubleshoot [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] business solutions.</span></span> <span data-ttu-id="cf096-105">BizTalk アプリケーションは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ビジネス ソリューションで使用される "アイテム" の論理グループです。</span><span class="sxs-lookup"><span data-stu-id="cf096-105">A BizTalk application is a logical grouping of the items, called "artifacts," used in a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] business solution.</span></span> <span data-ttu-id="cf096-106">アイテムについては後で詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="cf096-106">Artifacts are described in more detail later in this topic.</span></span>  
  
 <span data-ttu-id="cf096-107">新しく設計された管理と監視ツールを BizTalk Server の管理および構成できるように、この新しい概念を活用がかかる[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アプリケーション レベル、および個々 のアイテム レベルだけでなく、ビジネス ソリューションです。</span><span class="sxs-lookup"><span data-stu-id="cf096-107">The newly designed administration and monitoring tools of BizTalk Server take advantage of this new concept, so that you can manage and configure [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] business solutions at the application level, and not just at the individual artifact level.</span></span> <span data-ttu-id="cf096-108">アプリケーションを作成してアイテムを追加することで、ソリューション内の複数のアイテムをまとめて 1 つのエンティティとして表示、パッケージ化、展開、および管理できます。</span><span class="sxs-lookup"><span data-stu-id="cf096-108">By creating an application and adding artifacts to it, you can view, package, deploy, and manage a group of artifacts in a solution as a single entity.</span></span> <span data-ttu-id="cf096-109">このため、複雑なアプリケーションの数が増えても、容易かつ直観的に個別管理することができます。</span><span class="sxs-lookup"><span data-stu-id="cf096-109">Therefore, as the number of complex applications increases you can still manage them individually in a simple and intuitive manner.</span></span>  
  
 <span data-ttu-id="cf096-110">作成して管理されているアプリケーションは、使用できるいくつかのツールがある[アプリケーションの展開と管理ツール](../core/application-deployment-and-management-tools.md)します。</span><span class="sxs-lookup"><span data-stu-id="cf096-110">There are several tools you can use to create and manage applications, which are described in [Application Deployment and Management Tools](../core/application-deployment-and-management-tools.md).</span></span>  
  
 <span data-ttu-id="cf096-111">次の図に、2 つの BizTalk アプリケーションと、各アプリケーションに含まれるアイテムを示します。</span><span class="sxs-lookup"><span data-stu-id="cf096-111">The following diagram depicts two BizTalk applications and the artifacts that they contain.</span></span>  
  
 <span data-ttu-id="cf096-112">![BizTalk アプリケーションとアイテム](../core/media/biztalkapplication.gif "BizTalkApplication")</span><span class="sxs-lookup"><span data-stu-id="cf096-112">![BizTalk applications and artifacts](../core/media/biztalkapplication.gif "BizTalkApplication")</span></span>  
  
## <a name="artifacts"></a><span data-ttu-id="cf096-113">成果物</span><span class="sxs-lookup"><span data-stu-id="cf096-113">Artifacts</span></span>  
 <span data-ttu-id="cf096-114">アイテムには、次のものがあります。</span><span class="sxs-lookup"><span data-stu-id="cf096-114">Artifacts include the following:</span></span>  
  
- <span data-ttu-id="cf096-115">BizTalk アセンブリ、およびアセンブリに含まれる BizTalk 固有のリソース (オーケストレーション、パイプライン、スキーマ、およびマップ)</span><span class="sxs-lookup"><span data-stu-id="cf096-115">BizTalk assemblies and the BizTalk-specific resources that they contain – orchestrations, pipelines, schemas, and maps</span></span>  
  
- <span data-ttu-id="cf096-116">BizTalk 固有のリソースを含まない .NET アセンブリ</span><span class="sxs-lookup"><span data-stu-id="cf096-116">.NET assemblies that do not contain BizTalk-specific resources</span></span>  
  
- <span data-ttu-id="cf096-117">ポリシー</span><span class="sxs-lookup"><span data-stu-id="cf096-117">Policies</span></span>  
  
- <span data-ttu-id="cf096-118">送信ポート、送信ポート グループ、受信場所、および受信ポート</span><span class="sxs-lookup"><span data-stu-id="cf096-118">Send ports, send port groups, receive locations, and receive ports</span></span>  
  
- <span data-ttu-id="cf096-119">ソリューションで使用されるその他のアイテム (証明書、COM コンポーネント、スクリプトなど)</span><span class="sxs-lookup"><span data-stu-id="cf096-119">Other items that are used by the solution, such as certificates, COM components, and scripts</span></span>  
  
  <span data-ttu-id="cf096-120">成果物の種類ごとの背景については、次を参照してください。[ランタイム アーキテクチャ](../core/runtime-architecture.md)します。</span><span class="sxs-lookup"><span data-stu-id="cf096-120">For background information about each type of artifact, see [Runtime Architecture](../core/runtime-architecture.md).</span></span> <span data-ttu-id="cf096-121">追加の詳細については、削除、およびアーティファクトの構成を参照してください[管理成果物](../core/managing-artifacts.md)します。</span><span class="sxs-lookup"><span data-stu-id="cf096-121">For more information about adding, removing, and configuring artifacts, see [Managing Artifacts](../core/managing-artifacts.md).</span></span>  
  
  <span data-ttu-id="cf096-122">アプリケーションには、ビジネス ソリューションで使用されているすべてのアイテムを含めることも、一部のみを含めることもできます。</span><span class="sxs-lookup"><span data-stu-id="cf096-122">An application can contain all of the artifacts used in a business solution or only some of them.</span></span> <span data-ttu-id="cf096-123">アイテムを 1 つのアプリケーションに配置した方がよいか、2 つ以上のアプリケーションに分けた方がよいかは、アイテムの展開方法によって異なります。</span><span class="sxs-lookup"><span data-stu-id="cf096-123">Depending on how you want to deploy the artifacts, you may want to place them into a single application or into two or more applications.</span></span> <span data-ttu-id="cf096-124">成果物をグループ化する方法を決定する方法の詳細については、次を参照してください。 [BizTalk アプリケーションの展開のベスト プラクティス](../core/best-practices-for-deploying-a-biztalk-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="cf096-124">For more information about deciding how to group artifacts, see [Best Practices for Deploying a BizTalk Application](../core/best-practices-for-deploying-a-biztalk-application.md).</span></span>  
  
## <a name="the-default-application"></a><span data-ttu-id="cf096-125">既定のアプリケーション</span><span class="sxs-lookup"><span data-stu-id="cf096-125">The default application</span></span>  
 <span data-ttu-id="cf096-126">BizTalk Server は、次のインストールが構成されて、BizTalk アプリケーション 1 という名前の既定のアプリケーションが自動的に作成します。</span><span class="sxs-lookup"><span data-stu-id="cf096-126">When BizTalk Server is configured following installation, a default application named BizTalk Application 1 is automatically created.</span></span> <span data-ttu-id="cf096-127">異なるアプリケーションにアイテムをグループ化のベスト プラクティスについては、次を参照してください。 [BizTalk アプリケーションの展開のベスト プラクティス](../core/best-practices-for-deploying-a-biztalk-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="cf096-127">For information about best practices for grouping artifacts into different applications, see [Best Practices for Deploying a BizTalk Application](../core/best-practices-for-deploying-a-biztalk-application.md).</span></span> <span data-ttu-id="cf096-128">既定のアプリケーションを変更したり、既定のアプリケーションの名前を変更したりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="cf096-128">You can also change the default application or rename the default application.</span></span>  
  
 <span data-ttu-id="cf096-129">次のシナリオでは、アイテムは自動的に既定のアプリケーションに追加されます。</span><span class="sxs-lookup"><span data-stu-id="cf096-129">In the following scenarios, artifacts are automatically added to the default application:</span></span>  
  
- <span data-ttu-id="cf096-130">アプリケーション名を指定せずに、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] から [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] にアセンブリを展開する場合。</span><span class="sxs-lookup"><span data-stu-id="cf096-130">When you deploy an assembly from [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] into [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] without specifying an application name.</span></span> <span data-ttu-id="cf096-131">詳細については、次を参照してください。 [Visual Studio から BizTalk アセンブリを展開する方法](../core/how-to-deploy-a-biztalk-assembly-from-visual-studio.md)します。</span><span class="sxs-lookup"><span data-stu-id="cf096-131">For more information, see [How to Deploy a BizTalk Assembly from Visual Studio](../core/how-to-deploy-a-biztalk-assembly-from-visual-studio.md).</span></span>  
  
- <span data-ttu-id="cf096-132">BTSTask を使用して、アプリケーション名を指定せずにアイテムをアプリケーションに追加する場合。</span><span class="sxs-lookup"><span data-stu-id="cf096-132">When you use BTSTask to add an artifact to an application without specifying an application name.</span></span> <span data-ttu-id="cf096-133">詳細については、次を参照してください。 [AddResource コマンド](../core/addresource-command.md)します。</span><span class="sxs-lookup"><span data-stu-id="cf096-133">For more information, see [AddResource Command](../core/addresource-command.md).</span></span>  
  
- <span data-ttu-id="cf096-134">BTSTask を使用して、アプリケーション名を指定せずにアプリケーションの .msi ファイルをインポートする場合。</span><span class="sxs-lookup"><span data-stu-id="cf096-134">When you use BTSTask to import an application .msi file without specifying an application name.</span></span> <span data-ttu-id="cf096-135">詳細については、次を参照してください。 [ImportApp コマンド](../core/importapp-command.md)します。</span><span class="sxs-lookup"><span data-stu-id="cf096-135">For more information, see [ImportApp Command](../core/importapp-command.md).</span></span>  
  
## <a name="the-biztalksystem-application"></a><span data-ttu-id="cf096-136">BizTalk.System アプリケーション</span><span class="sxs-lookup"><span data-stu-id="cf096-136">The BizTalk.System application</span></span>  
 <span data-ttu-id="cf096-137">BizTalk サーバーが構成されている次のインストールの場合は、BizTalk.System という名前のアプリケーションが自動的に作成し、既定のスキーマやパイプラインなど、すべての BizTalk アプリケーションで使用される一般的なアイテムを格納します。</span><span class="sxs-lookup"><span data-stu-id="cf096-137">When BizTalk Server is configured following installation, an application named BizTalk.System is automatically created and populated with common artifacts that are used by all BizTalk applications, such as the default schemas and pipelines.</span></span> <span data-ttu-id="cf096-138">BizTalk.System とそのアイテムは読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="cf096-138">BizTalk.System and its artifacts are read-only.</span></span> <span data-ttu-id="cf096-139">BizTalk.System を削除したり、名前を変更したりすることはできません。また、BizTalk.System に含まれるアイテムを削除したり、名前を変更したり、移動したりすることもできません。</span><span class="sxs-lookup"><span data-stu-id="cf096-139">You cannot delete or rename BizTalk.System, nor can you delete, rename, or move any of the artifacts that it contains.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="cf096-140">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のすべてのアプリケーションには、自動的に BizTalk.System アプリケーションへの参照が含まれています。</span><span class="sxs-lookup"><span data-stu-id="cf096-140">Every application in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] automatically contains a reference to the BizTalk.System application.</span></span> <span data-ttu-id="cf096-141">これは、BizTalk.System 内のアイテムがすべての BizTalk アプリケーションで使用されるためです。</span><span class="sxs-lookup"><span data-stu-id="cf096-141">This is because the artifacts in BizTalk.System are used by every BizTalk application.</span></span> <span data-ttu-id="cf096-142">BizTalk.System アプリケーションへの参照は削除しないでください。</span><span class="sxs-lookup"><span data-stu-id="cf096-142">You should never remove a reference to the BizTalk.System application.</span></span> <span data-ttu-id="cf096-143">削除すると、アプリケーションが正しく機能しなくなる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="cf096-143">If you do, your application may not function correctly.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf096-144">参照</span><span class="sxs-lookup"><span data-stu-id="cf096-144">See Also</span></span>  
 [<span data-ttu-id="cf096-145">BizTalk アプリケーションの展開と管理について</span><span class="sxs-lookup"><span data-stu-id="cf096-145">Understanding BizTalk Application Deployment and Management</span></span>](../core/understanding-biztalk-application-deployment-and-management.md)