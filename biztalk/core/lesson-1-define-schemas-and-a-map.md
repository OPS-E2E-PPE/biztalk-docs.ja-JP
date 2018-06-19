---
title: 'レッスン 1: 定義のスキーマとマップ |Microsoft ドキュメント'
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
ms.openlocfilehash: ce6411a7a4ffa80b72bad2d84766bf773bbfb42f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262010"
---
# <a name="lesson-1-define-schemas-and-a-map"></a><span data-ttu-id="e94c2-102">レッスン 1: スキーマおよびマップの定義</span><span class="sxs-lookup"><span data-stu-id="e94c2-102">Lesson 1: Define Schemas and a Map</span></span>
<span data-ttu-id="e94c2-103">このレッスンでは、エンタープライズ アプリケーション統合 (EAI) ソリューションに、最初のプロジェクトを作成してビルドします。</span><span class="sxs-lookup"><span data-stu-id="e94c2-103">In this lesson, you create and build the first project in the enterprise application integration (EAI) solution.</span></span> <span data-ttu-id="e94c2-104">このプロジェクトには、2 つのメッセージ スキーマと 1 つのマップが含まれます。</span><span class="sxs-lookup"><span data-stu-id="e94c2-104">The project contains two message schemas, and a map.</span></span>  
  
 <span data-ttu-id="e94c2-105">EAI ソリューションでは、倉庫システムから [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に在庫補充要求メッセージが送信され、処理に充てられます。</span><span class="sxs-lookup"><span data-stu-id="e94c2-105">In the EAI solution, a warehouse system sends a request message for inventory replenishment to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] for processing.</span></span> <span data-ttu-id="e94c2-106">このレッスンでは、次の項目を作成します。</span><span class="sxs-lookup"><span data-stu-id="e94c2-106">In this lesson, you create the following items:</span></span>  
  
-   <span data-ttu-id="e94c2-107">EAI ソリューション (プロジェクトを格納)。</span><span class="sxs-lookup"><span data-stu-id="e94c2-107">The EAI solution, to hold the project.</span></span>  
  
-   <span data-ttu-id="e94c2-108">プロジェクト (スキーマおよびマップを格納)。</span><span class="sxs-lookup"><span data-stu-id="e94c2-108">The project, to hold the schemas and the map.</span></span>  
  
-   <span data-ttu-id="e94c2-109">スキーマ (倉庫から [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に送信される在庫補充要求メッセージ用)。</span><span class="sxs-lookup"><span data-stu-id="e94c2-109">The schema, for the message the warehouse sends to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to request inventory replenishment.</span></span>  
  
-   <span data-ttu-id="e94c2-110">スキーマ (要求が拒否されたときに倉庫で予期されるメッセージ用)。</span><span class="sxs-lookup"><span data-stu-id="e94c2-110">The schema, for the message that the warehouse is expecting when a request is rejected.</span></span>  
  
-   <span data-ttu-id="e94c2-111">マップ (要求拒否メッセージを作成するための要求メッセージの再フォーマット用)。</span><span class="sxs-lookup"><span data-stu-id="e94c2-111">A map, for reformatting a request message to create a request decline message.</span></span>  
  
 <span data-ttu-id="e94c2-112">最後に開始する前にプロジェクトをビルドする[レッスン 2: ビジネス プロセスの定義](../core/lesson-2-define-the-business-process.md)です。</span><span class="sxs-lookup"><span data-stu-id="e94c2-112">Finally you build the project before starting [Lesson 2: Define the Business Process](../core/lesson-2-define-the-business-process.md).</span></span> <span data-ttu-id="e94c2-113">レッスン 2 では、メッセージをルーティングし、在庫補充要求メッセージの内容が承認条件を満たすかどうかを評価するビジネス プロセスを作成します。</span><span class="sxs-lookup"><span data-stu-id="e94c2-113">In Lesson 2, you create the business process that routes the messages and evaluates the contents of the inventory replenishment request message against approval criteria.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e94c2-114">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="e94c2-114">In This Section</span></span>  
  
-   [<span data-ttu-id="e94c2-115">手順 1: EAISchemas プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="e94c2-115">Step 1: Create EAISchemas Project</span></span>](../core/step-1-create-eaischemas-project.md)  
  
-   [<span data-ttu-id="e94c2-116">手順 2: 在庫要求スキーマを作成します。</span><span class="sxs-lookup"><span data-stu-id="e94c2-116">Step 2: Create the Inventory Request Schema</span></span>](../core/step-2-create-the-inventory-request-schema.md)  
  
-   [<span data-ttu-id="e94c2-117">手順 3: 要求拒否スキーマを作成します。</span><span class="sxs-lookup"><span data-stu-id="e94c2-117">Step 3: Create the Request Decline Schema</span></span>](../core/step-3-create-the-request-decline-schema.md)  
  
-   [<span data-ttu-id="e94c2-118">手順 4: マップを作成します。</span><span class="sxs-lookup"><span data-stu-id="e94c2-118">Step 4: Create the Map</span></span>](../core/step-4-create-the-map.md)  
  
-   [<span data-ttu-id="e94c2-119">手順 5: EAISchemas プロジェクトをビルドします。</span><span class="sxs-lookup"><span data-stu-id="e94c2-119">Step 5: Build the EAISchemas Project</span></span>](../core/step-5-build-the-eaischemas-project.md)  
  
## <a name="see-also"></a><span data-ttu-id="e94c2-120">参照</span><span class="sxs-lookup"><span data-stu-id="e94c2-120">See Also</span></span>  
 <span data-ttu-id="e94c2-121">[このチュートリアルを開始する前に](../core/before-you-begin-the-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="e94c2-121">[Before You Begin the Tutorial](../core/before-you-begin-the-tutorial.md) </span></span>  
 <span data-ttu-id="e94c2-122">[レッスン 2: ビジネス プロセスを定義します。](../core/lesson-2-define-the-business-process.md) </span><span class="sxs-lookup"><span data-stu-id="e94c2-122">[Lesson 2: Define the Business Process](../core/lesson-2-define-the-business-process.md) </span></span>  
 [<span data-ttu-id="e94c2-123">レッスン 3: ソリューションを配置します。</span><span class="sxs-lookup"><span data-stu-id="e94c2-123">Lesson 3: Deploy the Solution</span></span>](../core/lesson-3-deploy-the-solution.md)