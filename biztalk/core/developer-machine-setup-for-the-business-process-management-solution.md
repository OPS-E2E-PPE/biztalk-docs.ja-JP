---
title: ビジネス プロセス管理ソリューションに対する開発者のマシンの設定 |Microsoft ドキュメント
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
ms.openlocfilehash: 1e2491d755062828a3204d895fa7be7552ef06d5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22238882"
---
# <a name="developer-machine-setup-for-the-business-process-management-solution"></a><span data-ttu-id="14c80-102">ビジネス プロセス管理ソリューションに対する開発者のコンピュータ設定</span><span class="sxs-lookup"><span data-stu-id="14c80-102">Developer Machine Setup for the Business Process Management Solution</span></span>
<span data-ttu-id="14c80-103">ビジネス プロセス管理 (BPM) ソリューションは、BizTalk アプリケーションのプロセス マネージャを構築する方法の 1 つです。</span><span class="sxs-lookup"><span data-stu-id="14c80-103">The Business Process Management (BPM) solution shows one way to construct a process manager in a BizTalk application.</span></span> <span data-ttu-id="14c80-104">このソリューションでは、1 つのコンポーネントを使用して、注文処理に含まれる一連のステージを選択および制御します。</span><span class="sxs-lookup"><span data-stu-id="14c80-104">The solution uses a component to select and control the sequence of stages in order processing.</span></span> <span data-ttu-id="14c80-105">ソリューションが注文を取得: 新しいサービス、アップグレード、またはサービスの終了になる可能性があります: ログの記録、および処理するため渡す前に、順序を確認します。</span><span class="sxs-lookup"><span data-stu-id="14c80-105">The solution takes an order—which may be for new service, an upgrade, or termination of service—logs it, and acknowledges the order before passing it on for processing.</span></span> <span data-ttu-id="14c80-106">注文処理は、注文を扱う 1 つ以上のステージで構成されます。</span><span class="sxs-lookup"><span data-stu-id="14c80-106">The processing consists of one or more stages that handle the order.</span></span> <span data-ttu-id="14c80-107">処理が終わったら、元の注文要求に応答を返します。</span><span class="sxs-lookup"><span data-stu-id="14c80-107">Finally, the solution returns a response to the original order request.</span></span>  
  
 <span data-ttu-id="14c80-108">開発者は、最初に単一のコンピュータで実行するシナリオを取得します。</span><span class="sxs-lookup"><span data-stu-id="14c80-108">As a developer, you first get the scenario running on a single computer.</span></span> <span data-ttu-id="14c80-109">単一のコンピュータ上で機能をテストした後、IT プロフェッショナルと一緒に、実稼働サーバーでソリューションを展開する方法を検討します。</span><span class="sxs-lookup"><span data-stu-id="14c80-109">After testing functionalities on the single computer, you will discuss how to deploy the solution on production servers with IT professionals.</span></span> <span data-ttu-id="14c80-110">IT プロフェッショナルをサポートし、高可用性、パフォーマンス向上、および保守の簡易化などのサービス要件を満たすシステム アーキテクチャを設計する必要があります。</span><span class="sxs-lookup"><span data-stu-id="14c80-110">You need to help them to design the system architecture to satisfy service requirements such as high availability, better performance, and easier maintenance.</span></span> <span data-ttu-id="14c80-111">次に、デザインに基づいて実稼働環境を展開するリソースを準備します。</span><span class="sxs-lookup"><span data-stu-id="14c80-111">You will then prepare resources for production deployment based on the design.</span></span>  
  
 <span data-ttu-id="14c80-112">この展開ガイドでは、単一のコンピュータにビジネス プロセス管理ソリューションをインストールしてテストする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="14c80-112">This deployment guide describes how to install and test the business process management solution on a single computer.</span></span>  
  
 <span data-ttu-id="14c80-113">ビジネス プロセス管理ソリューションの詳細については、次を参照してください。[ビジネス プロセス管理ソリューションを理解する](../core/understanding-the-business-process-management-solution.md)です。</span><span class="sxs-lookup"><span data-stu-id="14c80-113">For more information about the business process management solution, see [Understanding the Business Process Management Solution](../core/understanding-the-business-process-management-solution.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="14c80-114">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="14c80-114">In This Section</span></span>  
  
-   [<span data-ttu-id="14c80-115">ビジネス プロセス管理ソリューションをインストールする前に</span><span class="sxs-lookup"><span data-stu-id="14c80-115">Before Installing the Business Process Management Solution</span></span>](../core/before-installing-the-business-process-management-solution.md)  
  
-   [<span data-ttu-id="14c80-116">ビジネス プロセス管理ソリューションをインストールする方法</span><span class="sxs-lookup"><span data-stu-id="14c80-116">How to Install the Business Process Management Solution</span></span>](../core/how-to-install-the-business-process-management-solution.md)  
  
-   [<span data-ttu-id="14c80-117">ビジネス プロセス管理ソリューションを実行する方法</span><span class="sxs-lookup"><span data-stu-id="14c80-117">How to Run the Business Process Management Solution</span></span>](../core/how-to-run-the-business-process-management-solution.md)