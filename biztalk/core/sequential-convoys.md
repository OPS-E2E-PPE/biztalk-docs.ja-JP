---
title: シーケンシャルなコンボイ |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- convoy sets
- correlation sets, sequential receive tasks
ms.assetid: f05ff42c-2236-42a3-8166-19700e0c3d97
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 329d0f56d9f092cd146a900c42ed48d5206a6393
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22271586"
---
# <a name="sequential-convoys"></a><span data-ttu-id="df57d-102">シーケンシャルなコンボイ</span><span class="sxs-lookup"><span data-stu-id="df57d-102">Sequential Convoys</span></span>
<span data-ttu-id="df57d-103">シーケンシャルなコンボイを使用すると、複数の単一メッセージを結合して必要とされる結果を実現することが可能になります。</span><span class="sxs-lookup"><span data-stu-id="df57d-103">A sequential convoy enables multiple single messages to join together to achieve a required result.</span></span> <span data-ttu-id="df57d-104">シーケンシャルなコンボイは、事前定義された順序を持つ、一連の関連するメッセージです。</span><span class="sxs-lookup"><span data-stu-id="df57d-104">A sequential convoy is a set of related messages that have a predefined order.</span></span> <span data-ttu-id="df57d-105">これらのメッセージが完全に同一である必要はありませんが、BizTalk Server は各メッセージを順番に受け取る必要があります。</span><span class="sxs-lookup"><span data-stu-id="df57d-105">Although the messages do not have to be exactly the same, BizTalk Server must receive them in a sequential order.</span></span>  
  
 <span data-ttu-id="df57d-106">たとえば、あるオンライン小売企業が、1 日中、直接のクライアントや販売店から新規注文を受けているとします。</span><span class="sxs-lookup"><span data-stu-id="df57d-106">For example, suppose that an online retail company receives new orders from direct clients and from dealers throughout the course of the day.</span></span> <span data-ttu-id="df57d-107">午後 2 時までに受けたすべての注文は単一のバッチとして倉庫に送る必要があり、注文を受けた順序も保持する必要があります。</span><span class="sxs-lookup"><span data-stu-id="df57d-107">All orders received before 2:00 PM must go to the warehouse in a single batch, and the sequence of the receipt of the orders must be preserved.</span></span> <span data-ttu-id="df57d-108">順序を保持することによって、倉庫で在庫切れの品目がある場合に、先に受けた注文を優先することができます。</span><span class="sxs-lookup"><span data-stu-id="df57d-108">This enables earlier orders to have priority in case any items are out of stock in the warehouse.</span></span> <span data-ttu-id="df57d-109">バッチ へッダー情報を持つ単一のファイルに、その日のすべての注文をまとめることによって、このバッチを作成します。</span><span class="sxs-lookup"><span data-stu-id="df57d-109">You build this batch order by assembling all orders for the day in a single file that has batch header information.</span></span> <span data-ttu-id="df57d-110">午後 2 時に、その日のすべての注文が処理のために倉庫に送られます。</span><span class="sxs-lookup"><span data-stu-id="df57d-110">At 2:00 PM, all orders for the day go to the warehouse for processing.</span></span> <span data-ttu-id="df57d-111">午後 2 時以降に受けた注文は、次の日に処理される新しいバッチに入れられます。</span><span class="sxs-lookup"><span data-stu-id="df57d-111">All orders received after 2:00 PM are put into a new batch for processing on the following day.</span></span>  
  
 <span data-ttu-id="df57d-112">上記のシナリオは、受信メッセージのシーケンシャルなコンボイ処理を必要とするビジネス プロセスの例です。</span><span class="sxs-lookup"><span data-stu-id="df57d-112">The preceding scenario is an example of a business process that requires sequential convoy processing of incoming messages.</span></span> <span data-ttu-id="df57d-113">このビジネス要件では、その日の午後 2 時までに受けたすべての注文をまとめてバッチ処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="df57d-113">The business requirements state that all single orders received before 2:00 PM for a specific day should batch together.</span></span> <span data-ttu-id="df57d-114">そのため、最初に受信したメッセージで新しいオーケストレーション インスタンスを開始し、関連付けセットを初期化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="df57d-114">This requires the first message received to start a new orchestration instance and initialize a correlation set.</span></span> <span data-ttu-id="df57d-115">その時点で、受信した同じ種類のメッセージのその他のすべての注文を、既に実行されているオーケストレーション インスタンスにルーティングします。</span><span class="sxs-lookup"><span data-stu-id="df57d-115">At that point, all other orders received of that message type route to the already-running orchestration instance.</span></span> <span data-ttu-id="df57d-116">配置するためには、**リッスン**図形 (を含む、**受信**図形および**遅延**図形) 内、**ループ**図形です。</span><span class="sxs-lookup"><span data-stu-id="df57d-116">To accomplish this, you position a **Listen** shape (containing a **Receive** shape and a **Delay** shape) inside a **Loop** shape.</span></span> <span data-ttu-id="df57d-117">遅延に到達すると、ループが終了します。</span><span class="sxs-lookup"><span data-stu-id="df57d-117">After reaching the delay, the loop ends.</span></span> <span data-ttu-id="df57d-118">これによって、同じビジネス プロセスで不定数の注文を受けることができます。</span><span class="sxs-lookup"><span data-stu-id="df57d-118">This allows for the receipt of an unknown number of orders in the same business process.</span></span>  
  
## <a name="implementing-sequential-convoys"></a><span data-ttu-id="df57d-119">シーケンシャルなコンボイの実装</span><span class="sxs-lookup"><span data-stu-id="df57d-119">Implementing Sequential Convoys</span></span>  
 <span data-ttu-id="df57d-120">シーケンシャルなコンボイは、BizTalk Server の "シーケンシャルな相関受信" というメッセージング デザイン パターンを使用して実装できます。</span><span class="sxs-lookup"><span data-stu-id="df57d-120">You can implement sequential convoys by using the "sequential correlated receives" messaging design pattern in BizTalk Server.</span></span> <span data-ttu-id="df57d-121">シーケンシャルな相関受信は、前の受信に関連付けられている受信です。</span><span class="sxs-lookup"><span data-stu-id="df57d-121">Sequential correlated receives are receives that are correlated to previous receives.</span></span>  
  
 <span data-ttu-id="df57d-122">コンボイ処理は、受信に対する関連付けセットが別の受信によって初期化される場合に行われます。</span><span class="sxs-lookup"><span data-stu-id="df57d-122">Convoy processing takes place for cases in which the correlation sets for a receive are initialized by another receive.</span></span>  
  
 <span data-ttu-id="df57d-123">コンボイ処理を必要とする受信では、次の制限が適用されます。</span><span class="sxs-lookup"><span data-stu-id="df57d-123">For receives that require convoy processing, the following restrictions apply:</span></span>  
  
-   <span data-ttu-id="df57d-124">前の 1 つで、特定の受信を初期化する必要がありますのシーケンシャルなコンボイ セットを構成する関連付けセットが表示されます。</span><span class="sxs-lookup"><span data-stu-id="df57d-124">The correlation sets that constitute a sequential convoy set for a particular receive must be initialized by one preceding receive.</span></span>  
  
-   <span data-ttu-id="df57d-125">シーケンシャルなコンボイ処理を必要とする受信のポートは、コンボイ セットを初期化する受信のポートと同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="df57d-125">The port for a receive that requires sequential convoy processing must be the same as the port for the receive initializing the convoy set.</span></span> <span data-ttu-id="df57d-126">複数ポート間のコンボイはサポートされません。</span><span class="sxs-lookup"><span data-stu-id="df57d-126">Cross-port convoys are not supported.</span></span>  
  
-   <span data-ttu-id="df57d-127">受信ステートメントが順次配送ポートで実行されている場合を除き、コンボイ処理を必要とする受信のメッセージの種類は、コンボイ セットを初期化する受信のメッセージの種類と一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="df57d-127">Message types for a receive that requires convoy processing must match the message type for the receive initializing the convoy set, unless the receive statement is operating on an ordered delivery port.</span></span>  
  
-   <span data-ttu-id="df57d-128">順次配送ポートで実行されている場合を除き、シーケンシャルなコンボイに参加しているすべての受信は、初期化を行う受信によって初期化 (または準拠) されているすべての関連付けセットに従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="df57d-128">All receives participating in a sequential convoy must follow all the correlation sets that are initialized (or followed) by the initializing receive, unless operating on an ordered delivery port.</span></span>  
  
-   <span data-ttu-id="df57d-129">シーケンシャルなコンボイがアクティブ化受信ステートメントによって初期化される場合、順次配送ポートで実行されている場合を除き、そのアクティブ化受信ではフィルター式を使用できません。</span><span class="sxs-lookup"><span data-stu-id="df57d-129">If a sequential convoy is initialized by an activate receive statement, then the activate receive cannot have a filter expression unless operating on an ordered delivery port.</span></span>  
  
-   <span data-ttu-id="df57d-130">シーケンシャルなコンボイがアクティブ化受信によって初期化される場合、後続の受信をネストされているオーケストレーションの内側に入れることはできません。</span><span class="sxs-lookup"><span data-stu-id="df57d-130">If a sequential convoy is initialized by an activate receive, the following receives cannot be inside a nested orchestration.</span></span>  
  
 <span data-ttu-id="df57d-131">シーケンシャルなコンボイの実装の例は、次を参照してください。[アグリゲーター (BizTalk Server サンプル)](../core/aggregator-biztalk-server-sample.md)です。</span><span class="sxs-lookup"><span data-stu-id="df57d-131">For an example of sequential convoy implementation, see [Aggregator (BizTalk Server Sample)](../core/aggregator-biztalk-server-sample.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df57d-132">参照</span><span class="sxs-lookup"><span data-stu-id="df57d-132">See Also</span></span>  
 <span data-ttu-id="df57d-133">[コンボイ シナリオの](../core/working-with-convoy-scenarios.md) </span><span class="sxs-lookup"><span data-stu-id="df57d-133">[Working with Convoy Scenarios](../core/working-with-convoy-scenarios.md) </span></span>  
 [<span data-ttu-id="df57d-134">パラレルなコンボイ</span><span class="sxs-lookup"><span data-stu-id="df57d-134">Parallel Convoys</span></span>](../core/parallel-convoys.md)