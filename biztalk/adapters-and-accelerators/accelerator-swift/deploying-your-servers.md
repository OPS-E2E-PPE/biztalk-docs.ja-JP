---
title: "サーバーを展開する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- deploying, servers
- servers, deploying
ms.assetid: 6036e42b-59b8-4092-addd-288e9c4b91d6
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f0c158e3c14a5a695e7c1e042cd3dfb0277260b7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="deploying-your-servers"></a><span data-ttu-id="be768-102">サーバーを展開します。</span><span class="sxs-lookup"><span data-stu-id="be768-102">Deploying Your Servers</span></span>
<span data-ttu-id="be768-103">このセクションでは、の各サーバーを構成するための説明、[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]展開します。</span><span class="sxs-lookup"><span data-stu-id="be768-103">This section provides instructions for configuring each of the servers in your [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] deployment.</span></span> <span data-ttu-id="be768-104">ネットワークを構成した後は、次の手順を使用して、各サーバー上のソフトウェアを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="be768-104">After you configure the network you deploy the software on each server by using the following steps.</span></span>  
  
 <span data-ttu-id="be768-105">サーバーの展開を開始する前に確認しておくことで手順を説明する展開の準備を行う[の展開の準備](../../adapters-and-accelerators/accelerator-swift/preparing-for-deployment.md)です。</span><span class="sxs-lookup"><span data-stu-id="be768-105">Before starting server deployment, make sure that you read and perform the deployment preparation steps described in [Preparing for Deployment](../../adapters-and-accelerators/accelerator-swift/preparing-for-deployment.md).</span></span> <span data-ttu-id="be768-106">前のセクションで規範的なガイダンスに従うできない場合があります、展開の不明およびサポートされていない構成で (およびそれ以降のステップが失敗する可能性があります)。</span><span class="sxs-lookup"><span data-stu-id="be768-106">Failing to adhere to the prescriptive guidance in the previous section might result in an unknown and unsupported configuration of the deployment (and subsequent steps might fail).</span></span>  
  
 <span data-ttu-id="be768-107">詳細については、次を参照してください。、[!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)]デプロイメント ガイド 』。</span><span class="sxs-lookup"><span data-stu-id="be768-107">For more information, see the [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] Deployment Guide.</span></span>  
  
 <span data-ttu-id="be768-108">このセクションには、次のトピックが含まれています。</span><span class="sxs-lookup"><span data-stu-id="be768-108">This section contains:</span></span>  
  
-   [<span data-ttu-id="be768-109">手順 1: 基本プラットフォームをインストールします。</span><span class="sxs-lookup"><span data-stu-id="be768-109">Step 1: Installing the Base Platform</span></span>](../../adapters-and-accelerators/accelerator-swift/step-1-installing-the-base-platform.md)  
  
-   [<span data-ttu-id="be768-110">手順 2: サーバーで NLB を構成します。</span><span class="sxs-lookup"><span data-stu-id="be768-110">Step 2: Configuring NLB on the Servers</span></span>](../../adapters-and-accelerators/accelerator-swift/step-2-configuring-nlb-on-the-servers.md)  
  
-   [<span data-ttu-id="be768-111">手順 3: ドメイン コント ローラーの構成</span><span class="sxs-lookup"><span data-stu-id="be768-111">Step 3: Configuring the Domain Controller</span></span>](../../adapters-and-accelerators/accelerator-swift/step-3-configuring-the-domain-controller.md)  
  
-   [<span data-ttu-id="be768-112">手順 4: データベース サーバーの構成</span><span class="sxs-lookup"><span data-stu-id="be768-112">Step 4: Configuring the Database Servers</span></span>](../../adapters-and-accelerators/accelerator-swift/step-4-configuring-the-database-servers.md)  
  
-   [<span data-ttu-id="be768-113">手順 5: 構成の BizTalk メッセージング サーバー</span><span class="sxs-lookup"><span data-stu-id="be768-113">Step 5: Configuring the BizTalk Messaging Servers</span></span>](../../adapters-and-accelerators/accelerator-swift/step-5-configuring-the-biztalk-messaging-servers.md)  
  
-   [<span data-ttu-id="be768-114">手順 6: オーケストレーションの BizTalk Server を構成します。</span><span class="sxs-lookup"><span data-stu-id="be768-114">Step 6: Configuring the BizTalk Orchestration Servers</span></span>](../../adapters-and-accelerators/accelerator-swift/step-6-configuring-the-biztalk-orchestration-servers.md)  
  
-   [<span data-ttu-id="be768-115">手順 7: BizTalk HTTP フロント エンド サーバーを構成します。</span><span class="sxs-lookup"><span data-stu-id="be768-115">Step 7: Configuring the BizTalk HTTP Front-End Servers</span></span>](../../adapters-and-accelerators/accelerator-swift/step-7-configuring-the-biztalk-http-front-end-servers.md)  
  
-   [<span data-ttu-id="be768-116">手順 8: インストール後の構成の変更</span><span class="sxs-lookup"><span data-stu-id="be768-116">Step 8: Post-Configuration Changes</span></span>](../../adapters-and-accelerators/accelerator-swift/step-8-post-configuration-changes.md)