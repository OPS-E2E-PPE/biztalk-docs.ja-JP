---
title: "レッスン 2: ビジネス プロセスの定義 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: enterprise application integration tutorial, defining business processes
ms.assetid: 644aa049-4dd7-4392-b97f-31b1f29e12bd
caps.latest.revision: "26"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c5a2a9512fe847fdf50957456ec3d3eeff087c33
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="lesson-2-define-the-business-process"></a><span data-ttu-id="f765b-102">レッスン 2: ビジネス プロセスの定義</span><span class="sxs-lookup"><span data-stu-id="f765b-102">Lesson 2: Define the Business Process</span></span>
<span data-ttu-id="f765b-103">このレッスンでは、エンタープライズ アプリケーション Integration(EAI) ソリューション内の 2 つ目のプロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="f765b-103">In this lesson, you create the second project in the Enterprise Application Integration(EAI) solution.</span></span> <span data-ttu-id="f765b-104">このプロジェクトには、オーケストレーションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="f765b-104">This project contains an orchestration.</span></span>  
  
 <span data-ttu-id="f765b-105">EAI シナリオでは、倉庫アプリケーション送信に在庫補充メッセージ[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]処理します。</span><span class="sxs-lookup"><span data-stu-id="f765b-105">In the EAI scenario, the warehouse application sends an inventory replenishment message to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] for processing.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="f765b-106">ビジネス プロセスを自動化を作成するオーケストレーションを使用します。</span><span class="sxs-lookup"><span data-stu-id="f765b-106"> uses the orchestration you create to automate the business process.</span></span> <span data-ttu-id="f765b-107">オーケストレーションでは、ワークフロー、アクション、および式が提供され、これらに従ってメッセージがシステム内で転送され、内容が処理されます。</span><span class="sxs-lookup"><span data-stu-id="f765b-107">The orchestration provides the workflow, actions, and expressions to move messages through the system and process their contents.</span></span>  
  
 <span data-ttu-id="f765b-108">最後に開始する前にプロジェクトをビルドする[レッスン 3: ソリューションの配置](../core/lesson-3-deploy-the-solution.md)です。</span><span class="sxs-lookup"><span data-stu-id="f765b-108">Finally you build the project before starting [Lesson 3: Deploy the Solution](../core/lesson-3-deploy-the-solution.md).</span></span>  
  
 <span data-ttu-id="f765b-109">詳細については、次を参照してください。[オーケストレーション デザイナーを使用してオーケストレーションを作成する](../core/creating-orchestrations-using-orchestration-designer.md)です。</span><span class="sxs-lookup"><span data-stu-id="f765b-109">For more information, see [Creating Orchestrations Using Orchestration Designer](../core/creating-orchestrations-using-orchestration-designer.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f765b-110">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="f765b-110">In This Section</span></span>  
  
-   [<span data-ttu-id="f765b-111">手順 1: EAIOrchestration プロジェクトをソリューションに追加します。</span><span class="sxs-lookup"><span data-stu-id="f765b-111">Step 1: Add EAIOrchestration Project to the Solution</span></span>](../core/step-1-add-eaiorchestration-project-to-the-solution.md)  
  
-   [<span data-ttu-id="f765b-112">手順 2: ビジネス プロセスを定義します。</span><span class="sxs-lookup"><span data-stu-id="f765b-112">Step 2: Define the Business Process</span></span>](../core/step-2-define-the-business-process.md)  
  
-   [<span data-ttu-id="f765b-113">手順 3: オーケストレーションのポートを追加します。</span><span class="sxs-lookup"><span data-stu-id="f765b-113">Step 3: Add Ports to the Orchestration</span></span>](../core/step-3-add-ports-to-the-orchestration.md)  
  
-   [<span data-ttu-id="f765b-114">手順 4: EAIOrchestration プロジェクトをビルドします。</span><span class="sxs-lookup"><span data-stu-id="f765b-114">Step 4: Build the EAIOrchestration Project</span></span>](../core/step-4-build-the-eaiorchestration-project.md)  
  
## <a name="see-also"></a><span data-ttu-id="f765b-115">参照</span><span class="sxs-lookup"><span data-stu-id="f765b-115">See Also</span></span>  
 <span data-ttu-id="f765b-116">[このチュートリアルを開始する前に](../core/before-you-begin-the-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="f765b-116">[Before You Begin the Tutorial](../core/before-you-begin-the-tutorial.md) </span></span>  
 <span data-ttu-id="f765b-117">[レッスン 1: 定義のスキーマとマップ](../core/lesson-1-define-schemas-and-a-map.md) </span><span class="sxs-lookup"><span data-stu-id="f765b-117">[Lesson 1: Define Schemas and a Map](../core/lesson-1-define-schemas-and-a-map.md) </span></span>  
 [<span data-ttu-id="f765b-118">レッスン 3: ソリューションを配置します。</span><span class="sxs-lookup"><span data-stu-id="f765b-118">Lesson 3: Deploy the Solution</span></span>](../core/lesson-3-deploy-the-solution.md)