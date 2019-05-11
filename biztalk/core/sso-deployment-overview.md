---
title: SSO 展開の概要 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SSO, deploying example
- SSO, deploying
- deploying, SSO
- SSO, multiple computers
- examples, deploying
ms.assetid: 6eccee26-c392-41fe-97fb-3afe1685540f
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c942bf7f7fd0853164e2cf2b8fdadbfced2fe33d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401753"
---
# <a name="sso-deployment-overview"></a><span data-ttu-id="d5296-102">SSO 展開の概要</span><span class="sxs-lookup"><span data-stu-id="d5296-102">SSO Deployment Overview</span></span>
<span data-ttu-id="d5296-103">この例では、システムは、次のコンピューターを含む、3 つのドメインに展開されます。</span><span class="sxs-lookup"><span data-stu-id="d5296-103">The system in this example is deployed over three domains, containing the following computers:</span></span>  
  
 <span data-ttu-id="d5296-104">**ドメイン ORCH.com**</span><span class="sxs-lookup"><span data-stu-id="d5296-104">**Domain ORCH.com**</span></span>  
  
- <span data-ttu-id="d5296-105">ORCH ドメイン コントローラ</span><span class="sxs-lookup"><span data-stu-id="d5296-105">ORCH domain controller</span></span>  
  
- <span data-ttu-id="d5296-106">HIS1、HISSO サーバー</span><span class="sxs-lookup"><span data-stu-id="d5296-106">HIS1, the HISSO server</span></span>  
  
- <span data-ttu-id="d5296-107">HIS2、マスタ シークレット サーバー</span><span class="sxs-lookup"><span data-stu-id="d5296-107">HIS2, the Master Secret Server</span></span>  
  
- <span data-ttu-id="d5296-108">HIS3、管理データベース</span><span class="sxs-lookup"><span data-stu-id="d5296-108">HIS3, the Admin database</span></span>  
  
  <span data-ttu-id="d5296-109">**ドメイン SQL.com**</span><span class="sxs-lookup"><span data-stu-id="d5296-109">**Domain SQL.com**</span></span>  
  
- <span data-ttu-id="d5296-110">SQL ドメイン コント ローラー</span><span class="sxs-lookup"><span data-stu-id="d5296-110">SQL domain controller</span></span>  
  
- <span data-ttu-id="d5296-111">SQL2、SSO データベース</span><span class="sxs-lookup"><span data-stu-id="d5296-111">SQL2, the SSO database</span></span>  
  
  <span data-ttu-id="d5296-112">**ドメイン HIS.com**</span><span class="sxs-lookup"><span data-stu-id="d5296-112">**Domain HIS.com**</span></span>  
  
- <span data-ttu-id="d5296-113">自分のドメイン コントローラ</span><span class="sxs-lookup"><span data-stu-id="d5296-113">HIS domain controller</span></span>  
  
- <span data-ttu-id="d5296-114">HIS4 データベース</span><span class="sxs-lookup"><span data-stu-id="d5296-114">HIS4 database</span></span>  
  
  <span data-ttu-id="d5296-115">この配置を定義する重要な点は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d5296-115">The key points defining this deployment are as follows:</span></span>  
  
- <span data-ttu-id="d5296-116">ドメイン ORCH.com とドメイン SQL.com 選択的な双方向の信頼関係があります。</span><span class="sxs-lookup"><span data-stu-id="d5296-116">Domain ORCH.com and domain SQL.com have a two-way selective trust relationship.</span></span>  
  
- <span data-ttu-id="d5296-117">ドメイン ORCH.com はネイティブとして構成されている[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]または[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]の機能レベル。</span><span class="sxs-lookup"><span data-stu-id="d5296-117">Domain ORCH.com is configured as native [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] or [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] functional level.</span></span>  
  
- <span data-ttu-id="d5296-118">ORCH.com ドメイン ユーザー アカウント (orch \ssosvcuser) では、すべての SSO サービスが実行されています。</span><span class="sxs-lookup"><span data-stu-id="d5296-118">All SSO services are running on an ORCH.com domain user account (Orch\SSOSvcUser).</span></span> <span data-ttu-id="d5296-119">ユーザーは、SQL.com ドメイン内の SQL2 コンピュータに対するアクセス許可が構成されます。</span><span class="sxs-lookup"><span data-stu-id="d5296-119">The user is configured to have access permission on the SQL2 machine in the SQL.com domain.</span></span> <span data-ttu-id="d5296-120">ユーザーは、プロトコル遷移用に構成され、ORCH.com ドメイン内での委任を制限します。</span><span class="sxs-lookup"><span data-stu-id="d5296-120">The user is configured for protocol transition and constrain delegation within the ORCH.com domain.</span></span>  
  
- <span data-ttu-id="d5296-121">ORCH.com のもう 1 つのドメイン ユーザー (orch \testappuser) は、テスト プログラムを実行するために設定されています。</span><span class="sxs-lookup"><span data-stu-id="d5296-121">Another ORCH.com domain user (Orch\TestAppUser) is set for running test programs.</span></span> <span data-ttu-id="d5296-122">このユーザーは、プロトコル遷移用に設定し、制約付き委任します。</span><span class="sxs-lookup"><span data-stu-id="d5296-122">This user is also configured for protocol transition and constrain delegation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5296-123">参照</span><span class="sxs-lookup"><span data-stu-id="d5296-123">See Also</span></span>  
 [<span data-ttu-id="d5296-124">展開プロセス</span><span class="sxs-lookup"><span data-stu-id="d5296-124">Deployment Process</span></span>](../core/deployment-process.md)