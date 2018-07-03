---
title: アプリケーション展開タスク |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- applications, deploying
- applications, tasks
- deploying [applications], tasks
ms.assetid: 8cb29292-9868-41fa-9f2c-d1c20dfdddbb
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1bffe3490571d838f9b6995ff0919fd9c0d6383a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999619"
---
# <a name="application-deployment-tasks"></a><span data-ttu-id="6895e-102">アプリケーション展開作業</span><span class="sxs-lookup"><span data-stu-id="6895e-102">Application Deployment Tasks</span></span>
<span data-ttu-id="6895e-103">このセクションのトピックでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] におけるアプリケーション展開プロセスの各フェーズに関連する次の作業の詳細について説明します。</span><span class="sxs-lookup"><span data-stu-id="6895e-103">The topics in this section provide details about the following tasks involved in each phase of the application deployment process for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span></span>  
  
1. <span data-ttu-id="6895e-104">**開発します。**</span><span class="sxs-lookup"><span data-stu-id="6895e-104">**Development.**</span></span> <span data-ttu-id="6895e-105">開発者から、BizTalk アプリケーションに含まれる BizTalk アセンブリを展開する[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]に[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]開発用コンピューターで実行されています。</span><span class="sxs-lookup"><span data-stu-id="6895e-105">The developer deploys the BizTalk assemblies that are to be included in the BizTalk application from [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] into [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] running on the development computer.</span></span> <span data-ttu-id="6895e-106">これにより、自動的にアプリケーションが作成され、アセンブリに含まれているアイテムがこのアプリケーションに設定されます。</span><span class="sxs-lookup"><span data-stu-id="6895e-106">This automatically creates the application and populates it with the artifacts contained in the assemblies.</span></span> <span data-ttu-id="6895e-107">アイテムは、BizTalk アセンブリ、.NET アセンブリ、スキーマ、マップ、バインド、証明書など、BizTalk ビジネス ソリューションを構成するすべての項目です。</span><span class="sxs-lookup"><span data-stu-id="6895e-107">Artifacts are all of the items that comprise a BizTalk business solution, including BizTalk assemblies, .NET assemblies, schemas, maps, bindings, certificates, and so forth.</span></span> <span data-ttu-id="6895e-108">開発者は、アプリケーションに追加可能なアイテムを追加したり、追加の構成を実行して、アプリケーションを完了させます。</span><span class="sxs-lookup"><span data-stu-id="6895e-108">The developer completes the application by adding any additional artifacts to it or performing additional configuration.</span></span> <span data-ttu-id="6895e-109">続いて、.msi ファイルからアプリケーションをインストールし、機能を検証するためのテストを実行して問題を修正し、.msi ファイルとして [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] からアプリケーションをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="6895e-109">The developer then installs the application from the .msi file, tests it to verify functionality, fixes any issues, and then exports the application from [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] as an .msi file.</span></span>  
  
2. <span data-ttu-id="6895e-110">**テストします。**</span><span class="sxs-lookup"><span data-stu-id="6895e-110">**Testing.**</span></span> <span data-ttu-id="6895e-111">テスターは、.msi ファイルをインポートします[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]でアプリケーションを作成します。 テスト コンピューターで実行されている[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="6895e-111">The tester imports the .msi file into [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] running on a test computer, which creates the application in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="6895e-112">また、テスターは、ホスト コンピューターにも .msi ファイルからアプリケーションをインストールします。</span><span class="sxs-lookup"><span data-stu-id="6895e-112">The tester also installs the application on the host computers from the .msi file.</span></span> <span data-ttu-id="6895e-113">テストを実行してバグの修正が完了すると、テスターはアプリケーションを .msi ファイルとして [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] からエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="6895e-113">After testing and bug-fixing is complete, the tester exports the application from [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] as an .msi file.</span></span>  
  
3. <span data-ttu-id="6895e-114">**ステージングします。**</span><span class="sxs-lookup"><span data-stu-id="6895e-114">**Staging.**</span></span> <span data-ttu-id="6895e-115">IT 管理者に .msi ファイルをインポートする[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]実稼働環境用に構成します、ホスト コンピューターにインストール、機能を検証および完成したアプリケーションを .msi ファイルとしてエクスポートします、ステージング サーバーで実行されています。</span><span class="sxs-lookup"><span data-stu-id="6895e-115">The IT administrator imports the .msi file into [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] running on a staging server, configures it for the production environment, installs it on host computers, verifies the functionality, and then exports the finished application as an .msi file.</span></span>  
  
4. <span data-ttu-id="6895e-116">**実稼働します。**</span><span class="sxs-lookup"><span data-stu-id="6895e-116">**Production.**</span></span> <span data-ttu-id="6895e-117">IT 管理者に .msi ファイルをインポートする[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]運用環境で実行されている、ホスト コンピューターにアプリケーションをインストールし、アプリケーションを起動します。</span><span class="sxs-lookup"><span data-stu-id="6895e-117">The IT administrator imports the .msi file into [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] running in a production environment, installs the application on the host computers, and then starts the application.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6895e-118">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="6895e-118">In This Section</span></span>  
  
-   [<span data-ttu-id="6895e-119">BizTalk アプリケーション展開の開発作業</span><span class="sxs-lookup"><span data-stu-id="6895e-119">Development Tasks for BizTalk Application Deployment</span></span>](../core/development-tasks-for-biztalk-application-deployment.md)  
  
-   [<span data-ttu-id="6895e-120">BizTalk アプリケーション展開のテスト作業</span><span class="sxs-lookup"><span data-stu-id="6895e-120">Testing Tasks for BizTalk Application Deployment</span></span>](../core/testing-tasks-for-biztalk-application-deployment.md)  
  
-   [<span data-ttu-id="6895e-121">BizTalk アプリケーション展開のステージング作業</span><span class="sxs-lookup"><span data-stu-id="6895e-121">Staging Tasks for BizTalk Application Deployment</span></span>](../core/staging-tasks-for-biztalk-application-deployment.md)  
  
-   [<span data-ttu-id="6895e-122">BizTalk アプリケーション展開の実稼働作業</span><span class="sxs-lookup"><span data-stu-id="6895e-122">Production Tasks for BizTalk Application Deployment</span></span>](../core/production-tasks-for-biztalk-application-deployment.md)