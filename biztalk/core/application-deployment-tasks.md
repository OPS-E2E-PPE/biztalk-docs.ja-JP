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
ms.openlocfilehash: da4c55063132a7115eba0f81efb5ede5c4f24df6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65359059"
---
# <a name="application-deployment-tasks"></a><span data-ttu-id="515ed-102">アプリケーション展開作業</span><span class="sxs-lookup"><span data-stu-id="515ed-102">Application Deployment Tasks</span></span>
<span data-ttu-id="515ed-103">このセクションのトピックでのアプリケーションの展開プロセスの各フェーズに関連する次のタスクについて詳しく説明[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="515ed-103">The topics in this section provide details about the following tasks involved in each phase of the application deployment process for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span></span>  
  
1. <span data-ttu-id="515ed-104">**開発します。**</span><span class="sxs-lookup"><span data-stu-id="515ed-104">**Development.**</span></span> <span data-ttu-id="515ed-105">開発者から、BizTalk アプリケーションに含まれる BizTalk アセンブリを展開する[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]に[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]開発用コンピューターで実行されています。</span><span class="sxs-lookup"><span data-stu-id="515ed-105">The developer deploys the BizTalk assemblies that are to be included in the BizTalk application from [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] into [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] running on the development computer.</span></span> <span data-ttu-id="515ed-106">これは自動的に、アプリケーションが作成され、アセンブリに含まれるアイテムを設定します。</span><span class="sxs-lookup"><span data-stu-id="515ed-106">This automatically creates the application and populates it with the artifacts contained in the assemblies.</span></span> <span data-ttu-id="515ed-107">アーティファクトは、すべての BizTalk アセンブリ、.NET アセンブリ、スキーマ、マップ、バインド、証明書、およびなどを含む、BizTalk ビジネス ソリューションを構成する項目。</span><span class="sxs-lookup"><span data-stu-id="515ed-107">Artifacts are all of the items that comprise a BizTalk business solution, including BizTalk assemblies, .NET assemblies, schemas, maps, bindings, certificates, and so forth.</span></span> <span data-ttu-id="515ed-108">開発者は、任意の他のアイテムを追加したり、追加の構成を実行して、アプリケーションを完了します。</span><span class="sxs-lookup"><span data-stu-id="515ed-108">The developer completes the application by adding any additional artifacts to it or performing additional configuration.</span></span> <span data-ttu-id="515ed-109">開発者、.msi ファイルからアプリケーションをインストール、機能を検証するためのテストを、問題を修正しからアプリケーションをエクスポートし、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] .msi ファイルとして。</span><span class="sxs-lookup"><span data-stu-id="515ed-109">The developer then installs the application from the .msi file, tests it to verify functionality, fixes any issues, and then exports the application from [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] as an .msi file.</span></span>  
  
2. <span data-ttu-id="515ed-110">**テストします。**</span><span class="sxs-lookup"><span data-stu-id="515ed-110">**Testing.**</span></span> <span data-ttu-id="515ed-111">テスターは、.msi ファイルをインポートします[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]でアプリケーションを作成します。 テスト コンピューターで実行されている[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="515ed-111">The tester imports the .msi file into [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] running on a test computer, which creates the application in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="515ed-112">テスト担当者には、.msi ファイルからのホスト コンピューター上のアプリケーションもインストールされます。</span><span class="sxs-lookup"><span data-stu-id="515ed-112">The tester also installs the application on the host computers from the .msi file.</span></span> <span data-ttu-id="515ed-113">テストおよびバグの修正が完了した後、テスト担当者がからアプリケーションをエクスポートします[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].msi ファイルとして。</span><span class="sxs-lookup"><span data-stu-id="515ed-113">After testing and bug-fixing is complete, the tester exports the application from [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] as an .msi file.</span></span>  
  
3. <span data-ttu-id="515ed-114">**ステージングします。**</span><span class="sxs-lookup"><span data-stu-id="515ed-114">**Staging.**</span></span> <span data-ttu-id="515ed-115">IT 管理者に .msi ファイルをインポートする[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]実稼働環境用に構成します、ホスト コンピューターにインストール、機能を検証および完成したアプリケーションを .msi ファイルとしてエクスポートします、ステージング サーバーで実行されています。</span><span class="sxs-lookup"><span data-stu-id="515ed-115">The IT administrator imports the .msi file into [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] running on a staging server, configures it for the production environment, installs it on host computers, verifies the functionality, and then exports the finished application as an .msi file.</span></span>  
  
4. <span data-ttu-id="515ed-116">**実稼働します。**</span><span class="sxs-lookup"><span data-stu-id="515ed-116">**Production.**</span></span> <span data-ttu-id="515ed-117">IT 管理者に .msi ファイルをインポートする[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]運用環境で実行されている、ホスト コンピューターにアプリケーションをインストールし、アプリケーションを起動します。</span><span class="sxs-lookup"><span data-stu-id="515ed-117">The IT administrator imports the .msi file into [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] running in a production environment, installs the application on the host computers, and then starts the application.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="515ed-118">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="515ed-118">In This Section</span></span>  
  
-   [<span data-ttu-id="515ed-119">BizTalk アプリケーション展開の開発作業</span><span class="sxs-lookup"><span data-stu-id="515ed-119">Development Tasks for BizTalk Application Deployment</span></span>](../core/development-tasks-for-biztalk-application-deployment.md)  
  
-   [<span data-ttu-id="515ed-120">BizTalk アプリケーション展開のテスト作業</span><span class="sxs-lookup"><span data-stu-id="515ed-120">Testing Tasks for BizTalk Application Deployment</span></span>](../core/testing-tasks-for-biztalk-application-deployment.md)  
  
-   [<span data-ttu-id="515ed-121">BizTalk アプリケーション展開のステージング作業</span><span class="sxs-lookup"><span data-stu-id="515ed-121">Staging Tasks for BizTalk Application Deployment</span></span>](../core/staging-tasks-for-biztalk-application-deployment.md)  
  
-   [<span data-ttu-id="515ed-122">BizTalk アプリケーション展開の実稼働作業</span><span class="sxs-lookup"><span data-stu-id="515ed-122">Production Tasks for BizTalk Application Deployment</span></span>](../core/production-tasks-for-biztalk-application-deployment.md)