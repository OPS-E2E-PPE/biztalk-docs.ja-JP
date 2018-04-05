---
title: サンプルの BizTalk Server アーキテクチャ |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- architecture, examples
ms.assetid: 3e371771-55cf-4826-89cd-76b5537dd042
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 17f512015d5f2c1fd1a3bedc002140628fde4969
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="sample-biztalk-server-architectures"></a><span data-ttu-id="29edd-102">BizTalk Server のサンプル アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="29edd-102">Sample BizTalk Server Architectures</span></span>
<span data-ttu-id="29edd-103">Microsoft® BizTalk® Server 環境に最大限のセキュリティを提供するために、BizTalk Server に含まれているデータとサービスの重要度、および攻撃者がサーバーに侵入した場合に生じる影響に基づいて、BizTalk Server を分散するアーキテクチャを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="29edd-103">To provide the greatest possible security to your Microsoft® BizTalk® Server environment, it is recommended that you use an architecture where you distribute the BizTalk Servers based on the criticality of the data and services that they contain, and the implication if an attacker compromises the server.</span></span>  
  
 <span data-ttu-id="29edd-104">このセクションでは、企業および環境の特定のニーズや課題に合うように、BizTalk Server をセキュリティで保護された独自の方法で展開するために役立つ情報を示します。</span><span class="sxs-lookup"><span data-stu-id="29edd-104">This section provides information to help you derive your own secure deployment of BizTalk Server to meet the particular needs and challenges of your company and environment.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="29edd-105">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="29edd-105">In This Section</span></span>  
  
-   [<span data-ttu-id="29edd-106">大規模な分散アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="29edd-106">Large Distributed Architecture</span></span>](../core/large-distributed-architecture.md)  
  
-   [<span data-ttu-id="29edd-107">インフォメーション ワーカー サービスで大規模な分散アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="29edd-107">Large Distributed Architecture with Information Worker Services</span></span>](../core/large-distributed-architecture-with-information-worker-services.md)  
  
-   [<span data-ttu-id="29edd-108">サーバーの名前付け規則</span><span class="sxs-lookup"><span data-stu-id="29edd-108">Server Naming Conventions</span></span>](../core/server-naming-conventions.md)  
  
-   [<span data-ttu-id="29edd-109">縮小されたアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="29edd-109">Scaled Down Architecture</span></span>](../core/scaled-down-architecture.md)  
  
-   [<span data-ttu-id="29edd-110">縮小されたインフォメーション ワーカー サービスのアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="29edd-110">Scaled Down Architecture with Information Worker Services</span></span>](../core/scaled-down-architecture-with-information-worker-services.md)  
  
-   [<span data-ttu-id="29edd-111">セキュリティで保護された Windows アカウントは、BizTalk Server の展開を分散</span><span class="sxs-lookup"><span data-stu-id="29edd-111">Windows Accounts for a Secure Distributed BizTalk Server Deployment</span></span>](../core/windows-accounts-for-a-secure-distributed-biztalk-server-deployment.md)  
  
-   [<span data-ttu-id="29edd-112">BizTalk Server に必要なポート</span><span class="sxs-lookup"><span data-stu-id="29edd-112">Required Ports for BizTalk Server</span></span>](../core/required-ports-for-biztalk-server.md)