---
title: レッスン 2:ビジネス プロセスの定義 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- enterprise application integration tutorial, defining business processes
ms.assetid: 644aa049-4dd7-4392-b97f-31b1f29e12bd
caps.latest.revision: 26
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0c5f31b31ffc4a9f0ff1e7534456aac7f005b474
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65331306"
---
# <a name="lesson-2-define-the-business-process"></a><span data-ttu-id="df966-102">レッスン 2:ビジネス プロセスを定義します。</span><span class="sxs-lookup"><span data-stu-id="df966-102">Lesson 2: Define the Business Process</span></span>
<span data-ttu-id="df966-103">このレッスンでは、エンタープライズ アプリケーション Integration(EAI) ソリューションでは、2 番目のプロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="df966-103">In this lesson, you create the second project in the Enterprise Application Integration(EAI) solution.</span></span> <span data-ttu-id="df966-104">このプロジェクトには、オーケストレーションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="df966-104">This project contains an orchestration.</span></span>  
  
 <span data-ttu-id="df966-105">EAI シナリオでは、倉庫アプリケーションの送信に在庫補充メッセージ[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]処理します。</span><span class="sxs-lookup"><span data-stu-id="df966-105">In the EAI scenario, the warehouse application sends an inventory replenishment message to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] for processing.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="df966-106">ビジネス プロセスの自動化を作成するオーケストレーションを使用します。</span><span class="sxs-lookup"><span data-stu-id="df966-106">uses the orchestration you create to automate the business process.</span></span> <span data-ttu-id="df966-107">オーケストレーションでは、ワークフロー、アクション、およびシステムを介してメッセージを移動し、その内容を処理する式を提供します。</span><span class="sxs-lookup"><span data-stu-id="df966-107">The orchestration provides the workflow, actions, and expressions to move messages through the system and process their contents.</span></span>  
  
 <span data-ttu-id="df966-108">最後に開始する前にプロジェクトをビルドする[レッスン 3。ソリューションの配置](../core/lesson-3-deploy-the-solution.md)します。</span><span class="sxs-lookup"><span data-stu-id="df966-108">Finally you build the project before starting [Lesson 3: Deploy the Solution](../core/lesson-3-deploy-the-solution.md).</span></span>  
  
 <span data-ttu-id="df966-109">詳細については、次を参照してください。[オーケストレーション デザイナーを使用してオーケストレーションを作成](../core/creating-orchestrations-using-orchestration-designer.md)です。</span><span class="sxs-lookup"><span data-stu-id="df966-109">For more information, see [Creating Orchestrations Using Orchestration Designer](../core/creating-orchestrations-using-orchestration-designer.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="df966-110">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="df966-110">In This Section</span></span>  
  
-   [<span data-ttu-id="df966-111">ステップ 1: EAIOrchestration プロジェクトをソリューションに追加します。</span><span class="sxs-lookup"><span data-stu-id="df966-111">Step 1: Add EAIOrchestration Project to the Solution</span></span>](../core/step-1-add-eaiorchestration-project-to-the-solution.md)  
  
-   [<span data-ttu-id="df966-112">手順 2:ビジネス プロセスを定義します。</span><span class="sxs-lookup"><span data-stu-id="df966-112">Step 2: Define the Business Process</span></span>](../core/step-2-define-the-business-process.md)  
  
-   [<span data-ttu-id="df966-113">ステップ 3:ポートをオーケストレーションに追加します。</span><span class="sxs-lookup"><span data-stu-id="df966-113">Step 3: Add Ports to the Orchestration</span></span>](../core/step-3-add-ports-to-the-orchestration.md)  
  
-   [<span data-ttu-id="df966-114">手順 4:EAIOrchestration プロジェクトをビルドします。</span><span class="sxs-lookup"><span data-stu-id="df966-114">Step 4: Build the EAIOrchestration Project</span></span>](../core/step-4-build-the-eaiorchestration-project.md)  
  
## <a name="see-also"></a><span data-ttu-id="df966-115">参照</span><span class="sxs-lookup"><span data-stu-id="df966-115">See Also</span></span>  
 <span data-ttu-id="df966-116">[このチュートリアルを開始する前に](../core/before-you-begin-the-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="df966-116">[Before You Begin the Tutorial](../core/before-you-begin-the-tutorial.md) </span></span>  
 <span data-ttu-id="df966-117">[レッスン 1:スキーマおよびマップを定義します。](../core/lesson-1-define-schemas-and-a-map.md) </span><span class="sxs-lookup"><span data-stu-id="df966-117">[Lesson 1: Define Schemas and a Map](../core/lesson-1-define-schemas-and-a-map.md) </span></span>  
 [<span data-ttu-id="df966-118">レッスン 3:ソリューションを展開する</span><span class="sxs-lookup"><span data-stu-id="df966-118">Lesson 3: Deploy the Solution</span></span>](../core/lesson-3-deploy-the-solution.md)