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
ms.openlocfilehash: c98a12c11ae735945f4e69631e7211c05c0b9186
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37022368"
---
# <a name="sso-deployment-overview"></a><span data-ttu-id="da4de-102">SSO 展開の概要</span><span class="sxs-lookup"><span data-stu-id="da4de-102">SSO Deployment Overview</span></span>
<span data-ttu-id="da4de-103">この例では、システムは次のコンピュータを含む 3 つのドメインに展開されています。</span><span class="sxs-lookup"><span data-stu-id="da4de-103">The system in this example is deployed over three domains, containing the following computers:</span></span>  
  
 <span data-ttu-id="da4de-104">**ドメイン ORCH.com**</span><span class="sxs-lookup"><span data-stu-id="da4de-104">**Domain ORCH.com**</span></span>  
  
- <span data-ttu-id="da4de-105">ORCH ドメイン コントローラ</span><span class="sxs-lookup"><span data-stu-id="da4de-105">ORCH domain controller</span></span>  
  
- <span data-ttu-id="da4de-106">HIS1、HISSO サーバー</span><span class="sxs-lookup"><span data-stu-id="da4de-106">HIS1, the HISSO server</span></span>  
  
- <span data-ttu-id="da4de-107">HIS2、マスタ シークレット サーバー</span><span class="sxs-lookup"><span data-stu-id="da4de-107">HIS2, the Master Secret Server</span></span>  
  
- <span data-ttu-id="da4de-108">HIS3、管理データベース</span><span class="sxs-lookup"><span data-stu-id="da4de-108">HIS3, the Admin database</span></span>  
  
  <span data-ttu-id="da4de-109">**ドメイン SQL.com**</span><span class="sxs-lookup"><span data-stu-id="da4de-109">**Domain SQL.com**</span></span>  
  
- <span data-ttu-id="da4de-110">SQL ドメイン コントローラ</span><span class="sxs-lookup"><span data-stu-id="da4de-110">SQL domain controller</span></span>  
  
- <span data-ttu-id="da4de-111">SQL2、SSO データベース</span><span class="sxs-lookup"><span data-stu-id="da4de-111">SQL2, the SSO database</span></span>  
  
  <span data-ttu-id="da4de-112">**ドメイン HIS.com**</span><span class="sxs-lookup"><span data-stu-id="da4de-112">**Domain HIS.com**</span></span>  
  
- <span data-ttu-id="da4de-113">HIS ドメイン コントローラ</span><span class="sxs-lookup"><span data-stu-id="da4de-113">HIS domain controller</span></span>  
  
- <span data-ttu-id="da4de-114">HIS4 データベース</span><span class="sxs-lookup"><span data-stu-id="da4de-114">HIS4 database</span></span>  
  
  <span data-ttu-id="da4de-115">この展開の定義について重要な点は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="da4de-115">The key points defining this deployment are as follows:</span></span>  
  
- <span data-ttu-id="da4de-116">ドメイン ORCH.com とドメイン SQL.com には、双方向の信頼関係があり、どちらの方向を使用するかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="da4de-116">Domain ORCH.com and domain SQL.com have a two-way selective trust relationship.</span></span>  
  
- <span data-ttu-id="da4de-117">ドメイン ORCH.com は、[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] または [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] のネイティブの機能レベルとして構成されています。</span><span class="sxs-lookup"><span data-stu-id="da4de-117">Domain ORCH.com is configured as native [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] or [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] functional level.</span></span>  
  
- <span data-ttu-id="da4de-118">すべての SSO サービスは、ORCH.com のドメイン ユーザー アカウント (Orch\SSOSvcUser) で実行されています。</span><span class="sxs-lookup"><span data-stu-id="da4de-118">All SSO services are running on an ORCH.com domain user account (Orch\SSOSvcUser).</span></span> <span data-ttu-id="da4de-119">ユーザーは、SQL.com ドメイン内の SQL2 コンピュータに対するアクセス許可を持つように構成されています。</span><span class="sxs-lookup"><span data-stu-id="da4de-119">The user is configured to have access permission on the SQL2 machine in the SQL.com domain.</span></span> <span data-ttu-id="da4de-120">ユーザーは、ORCH.com ドメイン内のプロトコル遷移および制約付き委任用に構成されています。</span><span class="sxs-lookup"><span data-stu-id="da4de-120">The user is configured for protocol transition and constrain delegation within the ORCH.com domain.</span></span>  
  
- <span data-ttu-id="da4de-121">ORCH.com のもう 1 つのドメイン ユーザー (Orch\TestAppUser) は、テスト プログラムの実行用に設定されています。</span><span class="sxs-lookup"><span data-stu-id="da4de-121">Another ORCH.com domain user (Orch\TestAppUser) is set for running test programs.</span></span> <span data-ttu-id="da4de-122">このユーザーも、プロトコル遷移および制約付き委任用に構成されています。</span><span class="sxs-lookup"><span data-stu-id="da4de-122">This user is also configured for protocol transition and constrain delegation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da4de-123">参照</span><span class="sxs-lookup"><span data-stu-id="da4de-123">See Also</span></span>  
 [<span data-ttu-id="da4de-124">展開プロセス</span><span class="sxs-lookup"><span data-stu-id="da4de-124">Deployment Process</span></span>](../core/deployment-process.md)