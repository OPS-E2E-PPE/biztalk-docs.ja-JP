---
title: レッスン 1:スキーマおよびマップの定義 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- enterprise application integration tutorial, creating solutions
ms.assetid: 4fe7720d-722e-4fa0-a556-477fc66ffa12
caps.latest.revision: 35
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 02069f45a537a645dc0c3948e13d1f9208a8e5b3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65380769"
---
# <a name="lesson-1-define-schemas-and-a-map"></a><span data-ttu-id="e9c23-102">レッスン 1:スキーマおよびマップを定義します。</span><span class="sxs-lookup"><span data-stu-id="e9c23-102">Lesson 1: Define Schemas and a Map</span></span>
<span data-ttu-id="e9c23-103">このレッスンでは、作成し、エンタープライズ アプリケーション統合 (EAI) ソリューションの最初のプロジェクトをビルドします。</span><span class="sxs-lookup"><span data-stu-id="e9c23-103">In this lesson, you create and build the first project in the enterprise application integration (EAI) solution.</span></span> <span data-ttu-id="e9c23-104">プロジェクトには、2 つのメッセージ スキーマおよびマップが含まれています。</span><span class="sxs-lookup"><span data-stu-id="e9c23-104">The project contains two message schemas, and a map.</span></span>  
  
 <span data-ttu-id="e9c23-105">EAI ソリューションで倉庫システムに送信する在庫補充要求メッセージを[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]処理します。</span><span class="sxs-lookup"><span data-stu-id="e9c23-105">In the EAI solution, a warehouse system sends a request message for inventory replenishment to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] for processing.</span></span> <span data-ttu-id="e9c23-106">このレッスンでは、次の項目を作成します。</span><span class="sxs-lookup"><span data-stu-id="e9c23-106">In this lesson, you create the following items:</span></span>  
  
- <span data-ttu-id="e9c23-107">EAI ソリューション、プロジェクトを保持するためにします。</span><span class="sxs-lookup"><span data-stu-id="e9c23-107">The EAI solution, to hold the project.</span></span>  
  
- <span data-ttu-id="e9c23-108">スキーマとマップを保持するプロジェクトです。</span><span class="sxs-lookup"><span data-stu-id="e9c23-108">The project, to hold the schemas and the map.</span></span>  
  
- <span data-ttu-id="e9c23-109">倉庫に送信メッセージのスキーマ、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]在庫の補充を要求します。</span><span class="sxs-lookup"><span data-stu-id="e9c23-109">The schema, for the message the warehouse sends to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to request inventory replenishment.</span></span>  
  
- <span data-ttu-id="e9c23-110">要求が拒否されたときに倉庫で予期されるメッセージのスキーマです。</span><span class="sxs-lookup"><span data-stu-id="e9c23-110">The schema, for the message that the warehouse is expecting when a request is rejected.</span></span>  
  
- <span data-ttu-id="e9c23-111">要求拒否メッセージを作成する要求メッセージを再フォーマットのマップ。</span><span class="sxs-lookup"><span data-stu-id="e9c23-111">A map, for reformatting a request message to create a request decline message.</span></span>  
  
  <span data-ttu-id="e9c23-112">最後に開始する前にプロジェクトをビルドする[レッスン 2。ビジネス プロセスの定義](../core/lesson-2-define-the-business-process.md)します。</span><span class="sxs-lookup"><span data-stu-id="e9c23-112">Finally you build the project before starting [Lesson 2: Define the Business Process](../core/lesson-2-define-the-business-process.md).</span></span> <span data-ttu-id="e9c23-113">レッスン 2 では、メッセージをルーティングし、承認基準に照らし合わせて、在庫補充要求メッセージの内容を評価するビジネス プロセスを作成します。</span><span class="sxs-lookup"><span data-stu-id="e9c23-113">In Lesson 2, you create the business process that routes the messages and evaluates the contents of the inventory replenishment request message against approval criteria.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e9c23-114">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="e9c23-114">In This Section</span></span>  
  
-   [<span data-ttu-id="e9c23-115">ステップ 1: EAISchemas プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="e9c23-115">Step 1: Create EAISchemas Project</span></span>](../core/step-1-create-eaischemas-project.md)  
  
-   [<span data-ttu-id="e9c23-116">手順 2:在庫要求スキーマを作成します。</span><span class="sxs-lookup"><span data-stu-id="e9c23-116">Step 2: Create the Inventory Request Schema</span></span>](../core/step-2-create-the-inventory-request-schema.md)  
  
-   [<span data-ttu-id="e9c23-117">ステップ 3:要求拒否スキーマを作成します。</span><span class="sxs-lookup"><span data-stu-id="e9c23-117">Step 3: Create the Request Decline Schema</span></span>](../core/step-3-create-the-request-decline-schema.md)  
  
-   [<span data-ttu-id="e9c23-118">手順 4:マップを作成します。</span><span class="sxs-lookup"><span data-stu-id="e9c23-118">Step 4: Create the Map</span></span>](../core/step-4-create-the-map.md)  
  
-   [<span data-ttu-id="e9c23-119">手順 5:EAISchemas プロジェクトをビルドします。</span><span class="sxs-lookup"><span data-stu-id="e9c23-119">Step 5: Build the EAISchemas Project</span></span>](../core/step-5-build-the-eaischemas-project.md)  
  
## <a name="see-also"></a><span data-ttu-id="e9c23-120">参照</span><span class="sxs-lookup"><span data-stu-id="e9c23-120">See Also</span></span>  
 <span data-ttu-id="e9c23-121">[このチュートリアルを開始する前に](../core/before-you-begin-the-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="e9c23-121">[Before You Begin the Tutorial](../core/before-you-begin-the-tutorial.md) </span></span>  
 <span data-ttu-id="e9c23-122">[レッスン 2:ビジネス プロセスを定義します。](../core/lesson-2-define-the-business-process.md) </span><span class="sxs-lookup"><span data-stu-id="e9c23-122">[Lesson 2: Define the Business Process](../core/lesson-2-define-the-business-process.md) </span></span>  
 [<span data-ttu-id="e9c23-123">レッスン 3:ソリューションを展開する</span><span class="sxs-lookup"><span data-stu-id="e9c23-123">Lesson 3: Deploy the Solution</span></span>](../core/lesson-3-deploy-the-solution.md)