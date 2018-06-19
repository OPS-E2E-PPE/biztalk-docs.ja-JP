---
title: サーバーを展開する |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deploying, servers
- servers, deploying
ms.assetid: 6036e42b-59b8-4092-addd-288e9c4b91d6
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8fc3da3798e78e9b5fcf1ce09180c43e10417997
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
ms.locfileid: "26005404"
---
# <a name="deploying-your-servers"></a><span data-ttu-id="c2459-102">サーバーを展開します。</span><span class="sxs-lookup"><span data-stu-id="c2459-102">Deploying Your Servers</span></span>
<span data-ttu-id="c2459-103">このセクションでは、の各サーバーを構成するための説明、[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]展開します。</span><span class="sxs-lookup"><span data-stu-id="c2459-103">This section provides instructions for configuring each of the servers in your [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] deployment.</span></span> <span data-ttu-id="c2459-104">ネットワークを構成した後は、次の手順を使用して、各サーバー上のソフトウェアを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c2459-104">After you configure the network you deploy the software on each server by using the following steps.</span></span>  
  
 <span data-ttu-id="c2459-105">サーバーの展開を開始する前に確認しておくことで手順を説明する展開の準備を行う[の展開の準備](../../adapters-and-accelerators/accelerator-swift/preparing-for-deployment.md)です。</span><span class="sxs-lookup"><span data-stu-id="c2459-105">Before starting server deployment, make sure that you read and perform the deployment preparation steps described in [Preparing for Deployment](../../adapters-and-accelerators/accelerator-swift/preparing-for-deployment.md).</span></span> <span data-ttu-id="c2459-106">前のセクションで規範的なガイダンスに従うできない場合があります、展開の不明およびサポートされていない構成で (およびそれ以降のステップが失敗する可能性があります)。</span><span class="sxs-lookup"><span data-stu-id="c2459-106">Failing to adhere to the prescriptive guidance in the previous section might result in an unknown and unsupported configuration of the deployment (and subsequent steps might fail).</span></span>  
  
 <span data-ttu-id="c2459-107">詳細については、BizTalk Server の展開ガイドを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c2459-107">For more information, see the BizTalk Server Deployment Guide.</span></span>  
  
 <span data-ttu-id="c2459-108">このセクションには、次のトピックが含まれています。</span><span class="sxs-lookup"><span data-stu-id="c2459-108">This section contains:</span></span>  
  
-   [<span data-ttu-id="c2459-109">手順 1: 基本プラットフォームのインストール</span><span class="sxs-lookup"><span data-stu-id="c2459-109">Step 1: Installing the Base Platform</span></span>](../../adapters-and-accelerators/accelerator-swift/step-1-installing-the-base-platform.md)  
  
-   [<span data-ttu-id="c2459-110">手順 2: サーバー上での NLB の構成</span><span class="sxs-lookup"><span data-stu-id="c2459-110">Step 2: Configuring NLB on the Servers</span></span>](../../adapters-and-accelerators/accelerator-swift/step-2-configuring-nlb-on-the-servers.md)  
  
-   [<span data-ttu-id="c2459-111">手順 3: ドメイン コントローラーの構成</span><span class="sxs-lookup"><span data-stu-id="c2459-111">Step 3: Configuring the Domain Controller</span></span>](../../adapters-and-accelerators/accelerator-swift/step-3-configuring-the-domain-controller.md)  
  
-   [<span data-ttu-id="c2459-112">手順 4: データベース サーバーの構成</span><span class="sxs-lookup"><span data-stu-id="c2459-112">Step 4: Configuring the Database Servers</span></span>](../../adapters-and-accelerators/accelerator-swift/step-4-configuring-the-database-servers.md)  
  
-   [<span data-ttu-id="c2459-113">手順 5: BizTalk メッセージング サーバーの構成</span><span class="sxs-lookup"><span data-stu-id="c2459-113">Step 5: Configuring the BizTalk Messaging Servers</span></span>](../../adapters-and-accelerators/accelerator-swift/step-5-configuring-the-biztalk-messaging-servers.md)  
  
-   [<span data-ttu-id="c2459-114">手順 6: BizTalk オーケストレーション サーバーの構成</span><span class="sxs-lookup"><span data-stu-id="c2459-114">Step 6: Configuring the BizTalk Orchestration Servers</span></span>](../../adapters-and-accelerators/accelerator-swift/step-6-configuring-the-biztalk-orchestration-servers.md)  
  
-   [<span data-ttu-id="c2459-115">手順 7: BizTalk HTTP フロントエンド サーバーの構成</span><span class="sxs-lookup"><span data-stu-id="c2459-115">Step 7: Configuring the BizTalk HTTP Front-End Servers</span></span>](../../adapters-and-accelerators/accelerator-swift/step-7-configuring-the-biztalk-http-front-end-servers.md)  
  
-   [<span data-ttu-id="c2459-116">手順 8: 構成後の変更</span><span class="sxs-lookup"><span data-stu-id="c2459-116">Step 8: Post-Configuration Changes</span></span>](../../adapters-and-accelerators/accelerator-swift/step-8-post-configuration-changes.md)