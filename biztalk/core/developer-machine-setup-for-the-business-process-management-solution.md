---
title: ビジネス プロセス管理ソリューションに対する開発者のマシンの設定 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- developer servers
- process management solution tutorial, developer servers
- process management solution tutorial, deploying
ms.assetid: cf975323-53ec-45a8-9f68-80ad423f298b
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 35249beb37b648ee730532d27df50e7e50fa210d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65351564"
---
# <a name="developer-machine-setup-for-the-business-process-management-solution"></a><span data-ttu-id="99167-102">ビジネス プロセス管理ソリューションに対する開発者のマシンの設定</span><span class="sxs-lookup"><span data-stu-id="99167-102">Developer Machine Setup for the Business Process Management Solution</span></span>
<span data-ttu-id="99167-103">ビジネス プロセス管理 (BPM) ソリューションは、BizTalk アプリケーションでプロセス マネージャを構築する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="99167-103">The Business Process Management (BPM) solution shows one way to construct a process manager in a BizTalk application.</span></span> <span data-ttu-id="99167-104">ソリューションを選択し、注文処理ステージの順序を制御するコンポーネントを使用します。</span><span class="sxs-lookup"><span data-stu-id="99167-104">The solution uses a component to select and control the sequence of stages in order processing.</span></span> <span data-ttu-id="99167-105">ソリューションが注文を取得: 新しいサービス、アップグレード、またはサービスの終了になる可能性があるなど、ログに記録し、処理のため渡す前に、順序を確認します。</span><span class="sxs-lookup"><span data-stu-id="99167-105">The solution takes an order—which may be for new service, an upgrade, or termination of service—logs it, and acknowledges the order before passing it on for processing.</span></span> <span data-ttu-id="99167-106">処理は、注文を処理する 1 つまたは複数のステージで構成されます。</span><span class="sxs-lookup"><span data-stu-id="99167-106">The processing consists of one or more stages that handle the order.</span></span> <span data-ttu-id="99167-107">最後に、ソリューションは、元の注文要求に応答を返します。</span><span class="sxs-lookup"><span data-stu-id="99167-107">Finally, the solution returns a response to the original order request.</span></span>  
  
 <span data-ttu-id="99167-108">開発者は、まず 1 台のコンピューターで実行されているシナリオを取得します。</span><span class="sxs-lookup"><span data-stu-id="99167-108">As a developer, you first get the scenario running on a single computer.</span></span> <span data-ttu-id="99167-109">1 台のコンピューター上で機能をテストした後は、IT プロフェッショナルと実稼働サーバー上にあるソリューションをデプロイする方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="99167-109">After testing functionalities on the single computer, you will discuss how to deploy the solution on production servers with IT professionals.</span></span> <span data-ttu-id="99167-110">高可用性、パフォーマンスの向上、およびメンテナンスの簡素化などのサービス要件を満たすシステム アーキテクチャを設計するために必要があります。</span><span class="sxs-lookup"><span data-stu-id="99167-110">You need to help them to design the system architecture to satisfy service requirements such as high availability, better performance, and easier maintenance.</span></span> <span data-ttu-id="99167-111">設計に基づく運用環境のデプロイのリソースを準備します。</span><span class="sxs-lookup"><span data-stu-id="99167-111">You will then prepare resources for production deployment based on the design.</span></span>  
  
 <span data-ttu-id="99167-112">このデプロイ ガイドでは、インストールし、1 台のコンピューターでは、ビジネス プロセス管理ソリューションをテストする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="99167-112">This deployment guide describes how to install and test the business process management solution on a single computer.</span></span>  
  
 <span data-ttu-id="99167-113">ビジネス プロセス管理ソリューションの詳細については、次を参照してください。 [、ビジネス プロセス管理ソリューションを理解する](../core/understanding-the-business-process-management-solution.md)します。</span><span class="sxs-lookup"><span data-stu-id="99167-113">For more information about the business process management solution, see [Understanding the Business Process Management Solution](../core/understanding-the-business-process-management-solution.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="99167-114">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="99167-114">In This Section</span></span>  
  
-   [<span data-ttu-id="99167-115">ビジネス プロセス管理ソリューションをインストールする前に</span><span class="sxs-lookup"><span data-stu-id="99167-115">Before Installing the Business Process Management Solution</span></span>](../core/before-installing-the-business-process-management-solution.md)  
  
-   [<span data-ttu-id="99167-116">ビジネス プロセス管理ソリューションをインストールする方法</span><span class="sxs-lookup"><span data-stu-id="99167-116">How to Install the Business Process Management Solution</span></span>](../core/how-to-install-the-business-process-management-solution.md)  
  
-   [<span data-ttu-id="99167-117">ビジネス プロセス管理ソリューションを実行する方法</span><span class="sxs-lookup"><span data-stu-id="99167-117">How to Run the Business Process Management Solution</span></span>](../core/how-to-run-the-business-process-management-solution.md)