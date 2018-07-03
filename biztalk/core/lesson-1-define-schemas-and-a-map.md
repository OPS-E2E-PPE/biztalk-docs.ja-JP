---
title: 'レッスン 1: スキーマおよびマップの定義 |Microsoft Docs'
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
ms.openlocfilehash: b1e017239fc70186660812ea941fe11209506b1f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980371"
---
# <a name="lesson-1-define-schemas-and-a-map"></a><span data-ttu-id="b0491-102">レッスン 1: スキーマおよびマップの定義</span><span class="sxs-lookup"><span data-stu-id="b0491-102">Lesson 1: Define Schemas and a Map</span></span>
<span data-ttu-id="b0491-103">このレッスンでは、エンタープライズ アプリケーション統合 (EAI) ソリューションに、最初のプロジェクトを作成してビルドします。</span><span class="sxs-lookup"><span data-stu-id="b0491-103">In this lesson, you create and build the first project in the enterprise application integration (EAI) solution.</span></span> <span data-ttu-id="b0491-104">このプロジェクトには、2 つのメッセージ スキーマと 1 つのマップが含まれます。</span><span class="sxs-lookup"><span data-stu-id="b0491-104">The project contains two message schemas, and a map.</span></span>  
  
 <span data-ttu-id="b0491-105">EAI ソリューションでは、倉庫システムから [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に在庫補充要求メッセージが送信され、処理に充てられます。</span><span class="sxs-lookup"><span data-stu-id="b0491-105">In the EAI solution, a warehouse system sends a request message for inventory replenishment to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] for processing.</span></span> <span data-ttu-id="b0491-106">このレッスンでは、次の項目を作成します。</span><span class="sxs-lookup"><span data-stu-id="b0491-106">In this lesson, you create the following items:</span></span>  
  
- <span data-ttu-id="b0491-107">EAI ソリューション (プロジェクトを格納)。</span><span class="sxs-lookup"><span data-stu-id="b0491-107">The EAI solution, to hold the project.</span></span>  
  
- <span data-ttu-id="b0491-108">プロジェクト (スキーマおよびマップを格納)。</span><span class="sxs-lookup"><span data-stu-id="b0491-108">The project, to hold the schemas and the map.</span></span>  
  
- <span data-ttu-id="b0491-109">スキーマ (倉庫から [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に送信される在庫補充要求メッセージ用)。</span><span class="sxs-lookup"><span data-stu-id="b0491-109">The schema, for the message the warehouse sends to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to request inventory replenishment.</span></span>  
  
- <span data-ttu-id="b0491-110">スキーマ (要求が拒否されたときに倉庫で予期されるメッセージ用)。</span><span class="sxs-lookup"><span data-stu-id="b0491-110">The schema, for the message that the warehouse is expecting when a request is rejected.</span></span>  
  
- <span data-ttu-id="b0491-111">マップ (要求拒否メッセージを作成するための要求メッセージの再フォーマット用)。</span><span class="sxs-lookup"><span data-stu-id="b0491-111">A map, for reformatting a request message to create a request decline message.</span></span>  
  
  <span data-ttu-id="b0491-112">最後に開始する前にプロジェクトをビルドする[レッスン 2: ビジネス プロセスの定義](../core/lesson-2-define-the-business-process.md)します。</span><span class="sxs-lookup"><span data-stu-id="b0491-112">Finally you build the project before starting [Lesson 2: Define the Business Process](../core/lesson-2-define-the-business-process.md).</span></span> <span data-ttu-id="b0491-113">レッスン 2 では、メッセージをルーティングし、在庫補充要求メッセージの内容が承認条件を満たすかどうかを評価するビジネス プロセスを作成します。</span><span class="sxs-lookup"><span data-stu-id="b0491-113">In Lesson 2, you create the business process that routes the messages and evaluates the contents of the inventory replenishment request message against approval criteria.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b0491-114">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="b0491-114">In This Section</span></span>  
  
-   [<span data-ttu-id="b0491-115">手順 1: EAISchemas プロジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="b0491-115">Step 1: Create EAISchemas Project</span></span>](../core/step-1-create-eaischemas-project.md)  
  
-   [<span data-ttu-id="b0491-116">手順 2: 在庫要求スキーマの作成</span><span class="sxs-lookup"><span data-stu-id="b0491-116">Step 2: Create the Inventory Request Schema</span></span>](../core/step-2-create-the-inventory-request-schema.md)  
  
-   [<span data-ttu-id="b0491-117">手順 3: 要求拒否スキーマの作成</span><span class="sxs-lookup"><span data-stu-id="b0491-117">Step 3: Create the Request Decline Schema</span></span>](../core/step-3-create-the-request-decline-schema.md)  
  
-   [<span data-ttu-id="b0491-118">手順 4: マップの作成</span><span class="sxs-lookup"><span data-stu-id="b0491-118">Step 4: Create the Map</span></span>](../core/step-4-create-the-map.md)  
  
-   [<span data-ttu-id="b0491-119">手順 5: EAISchemas プロジェクトのビルド</span><span class="sxs-lookup"><span data-stu-id="b0491-119">Step 5: Build the EAISchemas Project</span></span>](../core/step-5-build-the-eaischemas-project.md)  
  
## <a name="see-also"></a><span data-ttu-id="b0491-120">参照</span><span class="sxs-lookup"><span data-stu-id="b0491-120">See Also</span></span>  
 <span data-ttu-id="b0491-121">[このチュートリアルを開始する前に](../core/before-you-begin-the-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="b0491-121">[Before You Begin the Tutorial](../core/before-you-begin-the-tutorial.md) </span></span>  
 <span data-ttu-id="b0491-122">[レッスン 2: ビジネス プロセスを定義します。](../core/lesson-2-define-the-business-process.md) </span><span class="sxs-lookup"><span data-stu-id="b0491-122">[Lesson 2: Define the Business Process](../core/lesson-2-define-the-business-process.md) </span></span>  
 [<span data-ttu-id="b0491-123">レッスン 3: ソリューションの展開</span><span class="sxs-lookup"><span data-stu-id="b0491-123">Lesson 3: Deploy the Solution</span></span>](../core/lesson-3-deploy-the-solution.md)