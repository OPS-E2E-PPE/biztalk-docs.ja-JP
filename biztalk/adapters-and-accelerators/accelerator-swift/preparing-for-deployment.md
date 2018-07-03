---
title: 展開の準備 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deploying, planning
ms.assetid: 437caa31-f7f8-42e0-af1f-13aaee0955cd
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4d7b6f0677b542ad03b2109eddb3352924f6b59c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966499"
---
# <a name="preparing-for-deployment"></a><span data-ttu-id="1bacd-102">展開の準備</span><span class="sxs-lookup"><span data-stu-id="1bacd-102">Preparing for Deployment</span></span>
<span data-ttu-id="1bacd-103">このセクションでは、展開の計画と準備の段階についてを説明します。</span><span class="sxs-lookup"><span data-stu-id="1bacd-103">This section provides information about the planning and preparation phase of the deployment.</span></span> <span data-ttu-id="1bacd-104">展開を実装する前に次の準備を行います。</span><span class="sxs-lookup"><span data-stu-id="1bacd-104">Before implementing a deployment, make the following preparations:</span></span>  
  
1. <span data-ttu-id="1bacd-105">読み取りと、既知の問題を理解し、機器を準備します。</span><span class="sxs-lookup"><span data-stu-id="1bacd-105">Read and understand any known issues, and prepare the equipment:</span></span>  
  
   -   <span data-ttu-id="1bacd-106">ハードウェアとソフトウェアの展開とネットワーク ダイアグラムとデプロイ ワークシート (ネットワークの図と選択した展開アーキテクチャに基づいて) 展開のバリエーションを反映するために必要なチェックリストを作成します。</span><span class="sxs-lookup"><span data-stu-id="1bacd-106">Create a checklist of the hardware and software required for your deployment, and a network diagram and deployment worksheet that reflect your variation of the deployment (based on the network diagram and for the deployment architecture you have selected).</span></span>  
  
   -   <span data-ttu-id="1bacd-107">ハードウェアおよびソフトウェアのチェックリストを取得します。</span><span class="sxs-lookup"><span data-stu-id="1bacd-107">Acquire the hardware and software on your checklist.</span></span> <span data-ttu-id="1bacd-108">この買収には、すべてのサービス パック、修正プログラム、および展開に必要なソフトウェア更新プログラムのダウンロードが含まれています。</span><span class="sxs-lookup"><span data-stu-id="1bacd-108">This acquisition includes downloading all of the service packs, hotfixes, and software updates that are required for your deployment.</span></span>  
  
        <span data-ttu-id="1bacd-109">インターネットにアクセスできるコンピューターを使用してこれらのソフトウェア コンポーネントをダウンロードして、これらのソフトウェア コンポーネントを簡単に配布の CD-ROM にコピーします。</span><span class="sxs-lookup"><span data-stu-id="1bacd-109">Download these software components using a computer with Internet access and then copy these software components onto a CD-ROM for easier distribution.</span></span>  
  
2. <span data-ttu-id="1bacd-110">さまざまな段階に、デプロイを分離し、各ステージに関連付けられているタスクを識別します。</span><span class="sxs-lookup"><span data-stu-id="1bacd-110">Separate your deployment into different stages and identify the tasks associated with each stage.</span></span> <span data-ttu-id="1bacd-111">この戦略では、特定の展開の段階に従ってタスクを整理することによって、展開プロセスを簡略化します。</span><span class="sxs-lookup"><span data-stu-id="1bacd-111">This strategy simplifies the deployment process by organizing the tasks according to a specific deployment stage.</span></span> <span data-ttu-id="1bacd-112">たとえば、所定の展開には、次のサーバー展開の段階が含まれています。</span><span class="sxs-lookup"><span data-stu-id="1bacd-112">For example, the prescribed deployment includes the following server deployment stages:</span></span>  
  
3. <span data-ttu-id="1bacd-113">ドメイン コント ローラーを構成します。</span><span class="sxs-lookup"><span data-stu-id="1bacd-113">Configuring the domain controller.</span></span>  
  
4. <span data-ttu-id="1bacd-114">データベースの構成 (実行時間を含む[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]クラスターおよびデザイン時のデータベース サーバー)。</span><span class="sxs-lookup"><span data-stu-id="1bacd-114">Configuring the databases (including the run-time [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] cluster and design-time database server).</span></span>  
  
5. <span data-ttu-id="1bacd-115">BizTalk server を構成します。</span><span class="sxs-lookup"><span data-stu-id="1bacd-115">Configuring the BizTalk servers.</span></span>  
  
   <span data-ttu-id="1bacd-116">このセクションには、次のトピックが含まれています。</span><span class="sxs-lookup"><span data-stu-id="1bacd-116">This section contains:</span></span>  
  
-   [<span data-ttu-id="1bacd-117">ネットワーク要件</span><span class="sxs-lookup"><span data-stu-id="1bacd-117">Network Requirements</span></span>](../../adapters-and-accelerators/accelerator-swift/network-requirements.md)  
  
-   [<span data-ttu-id="1bacd-118">展開のためのハードウェア要件とソフトウェア要件</span><span class="sxs-lookup"><span data-stu-id="1bacd-118">Hardware and Software Requirements for Deployment</span></span>](../../adapters-and-accelerators/accelerator-swift/hardware-and-software-requirements-for-deployment.md)