---
title: "永続化し、オーケストレーション エンジン |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- orchestration engine, persistence
- persistence
- orchestration engine, serialization
ms.assetid: 088230ef-13b3-440b-9875-6449f29dd5c6
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5e9e1c8b158d313681a6e1374a586ca957b1aa15
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="persistence-and-the-orchestration-engine"></a><span data-ttu-id="e9219-102">永続性とオーケストレーション エンジン</span><span class="sxs-lookup"><span data-stu-id="e9219-102">Persistence and the Orchestration Engine</span></span>
<span data-ttu-id="e9219-103">状態の永続化、その管理および復元は、オーケストレーション エンジンのさまざまな基本的な機能の基盤を形成します。</span><span class="sxs-lookup"><span data-stu-id="e9219-103">State persistence, its management and restoration form the basis of a lot of fundamental functionalities of the orchestration engine.</span></span> <span data-ttu-id="e9219-104">特に、永続化は、以下が正しく機能するために重要です。</span><span class="sxs-lookup"><span data-stu-id="e9219-104">In particular, persistence is critical to the correct functioning of:</span></span>  
  
-   <span data-ttu-id="e9219-105">退避と復元</span><span class="sxs-lookup"><span data-stu-id="e9219-105">Dehydration and rehydration</span></span>  
  
-   <span data-ttu-id="e9219-106">マシンに依存しない実行と復元</span><span class="sxs-lookup"><span data-stu-id="e9219-106">Machine agnostic execution and rehydration</span></span>  
  
-   <span data-ttu-id="e9219-107">補正モデル</span><span class="sxs-lookup"><span data-stu-id="e9219-107">Compensation model</span></span>  
  
-   <span data-ttu-id="e9219-108">制御されたシステム シャットダウン</span><span class="sxs-lookup"><span data-stu-id="e9219-108">Controlled System Shutdown</span></span>  
  
-   <span data-ttu-id="e9219-109">復旧</span><span class="sxs-lookup"><span data-stu-id="e9219-109">Recovery</span></span>  
  
 <span data-ttu-id="e9219-110">オーケストレーション エンジンは、さまざまな場所で実行しているオーケストレーション インスタンスの全体の状態を固定記憶装置に保存します。これにより、後でインスタンスをメモリ上に完全に復元できます。</span><span class="sxs-lookup"><span data-stu-id="e9219-110">The orchestration engine saves to persistent storage the entire state of a running orchestration instance at various points, so that the instance can later be completely restored in memory.</span></span> <span data-ttu-id="e9219-111">次の状態が保存されます。</span><span class="sxs-lookup"><span data-stu-id="e9219-111">The state includes:</span></span>  
  
-   <span data-ttu-id="e9219-112">エンジン内部の状態 (現在の進行状況を含む)。</span><span class="sxs-lookup"><span data-stu-id="e9219-112">The internal state of the engine, including its current progress.</span></span>  
  
-   <span data-ttu-id="e9219-113">状態情報が保存され、オーケストレーションによって使用されている .NET コンポーネントの状態。</span><span class="sxs-lookup"><span data-stu-id="e9219-113">The state of any .NET components that maintain state information and are being used by the orchestration.</span></span>  
  
-   <span data-ttu-id="e9219-114">メッセージと変数値。</span><span class="sxs-lookup"><span data-stu-id="e9219-114">Message and variable values.</span></span>  
  
## <a name="persistence-points"></a><span data-ttu-id="e9219-115">永続化ポイント</span><span class="sxs-lookup"><span data-stu-id="e9219-115">Persistence Points</span></span>  
 <span data-ttu-id="e9219-116">オーケストレーション エンジンは、さまざまな場所で実行しているオーケストレーション インスタンスの状態を保存します。</span><span class="sxs-lookup"><span data-stu-id="e9219-116">The orchestration engine saves the state of a running orchestration instance at various points.</span></span> <span data-ttu-id="e9219-117">オーケストレーション インスタンスの復元、制御されたシャットダウンからの開始、または予期しないシャットダウンからの復元が必要となった場合は、最後の永続化ポイントからオーケストレーション インスタンスが実行されます。これは、障害などが発生したことを意識させずに実行されます。</span><span class="sxs-lookup"><span data-stu-id="e9219-117">If it needs to rehydrate the orchestration instance, start up from a controlled shutdown, or recover from an unexpected shutdown, it will run the orchestration instance from the last persistence point, as though nothing else had occurred.</span></span> <span data-ttu-id="e9219-118">たとえば、メッセージは受信されたが、状態を保存する前に予期しないシャットダウンが発生した場合、このエンジンは、メッセージの受信が完了したことを記録しないため、再起動時に再度メッセージが受信されます。</span><span class="sxs-lookup"><span data-stu-id="e9219-118">For example, if a message is received but there is an unexpected shutdown before state can be saved, the engine will not record that it has received the message, and will receive it again upon restarting.</span></span> <span data-ttu-id="e9219-119">このエンジンは、次の状況でオーケストレーションの状態を保存します。</span><span class="sxs-lookup"><span data-stu-id="e9219-119">The engine will save the state of an orchestration in the following circumstances:</span></span>  
  
-   <span data-ttu-id="e9219-120">トランザクション スコープの最後に到達する。</span><span class="sxs-lookup"><span data-stu-id="e9219-120">The end of a transactional scope is reached.</span></span>  
  
    -   <span data-ttu-id="e9219-121">このエンジンは、トランザクション スコープの最後に状態を保存します。これにより、オーケストレーションを再開するポイントが明確に定義され、必要に応じて補正を正しく行うことができます。</span><span class="sxs-lookup"><span data-stu-id="e9219-121">The engine saves state at the end of a transactional scope so that the point at which the orchestration should resume is defined unambiguously, and so that compensation can be carried out correctly if necessary.</span></span>  
  
    -   <span data-ttu-id="e9219-122">オーケストレーションは、永続化処理が成功すると、スコープの最後から実行を続けます。それ以外の場合は、適切な例外ハンドラーが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="e9219-122">The orchestration will continue to run from the end of the scope if persistence was successful; otherwise, the appropriate exception handler will be invoked.</span></span>  
  
    -   <span data-ttu-id="e9219-123">スコープがトランザクションでアトミックの場合、エンジンは、コミット時にアトミックのスコープの最後の状態を保存します。</span><span class="sxs-lookup"><span data-stu-id="e9219-123">If the scope is transactional and atomic, the engine will save state at the end of the atomic scope when it commits.</span></span>  
  
    -   <span data-ttu-id="e9219-124">スコープがトランザクションで長時間実行されている場合、エンジンは、新しいトランザクションを生成し、スコープが完了するときに実行時のすべての状態を保存します。</span><span class="sxs-lookup"><span data-stu-id="e9219-124">If the scope is transactional and long-running, the engine will generate a new transaction and persist the complete state of the runtime when the scope completes.</span></span>  
  
-   <span data-ttu-id="e9219-125">デバッグのブレークポイントに到達する。</span><span class="sxs-lookup"><span data-stu-id="e9219-125">A debugging breakpoint is reached.</span></span>  
  
-   <span data-ttu-id="e9219-126">メッセージが送信される。</span><span class="sxs-lookup"><span data-stu-id="e9219-126">A message is sent.</span></span> <span data-ttu-id="e9219-127">ただし、メッセージがアトミック トランザクション スコープ内部から送信される場合だけは、例外となります。</span><span class="sxs-lookup"><span data-stu-id="e9219-127">The only exception to this is when a message is sent from within an atomic transaction scope.</span></span>  
  
-   <span data-ttu-id="e9219-128">オーケストレーションが別のオーケストレーションを非同期的に、起動と同様、**オーケストレーションの開始**図形です。</span><span class="sxs-lookup"><span data-stu-id="e9219-128">The orchestration starts another orchestration asynchronously, as with the **Start Orchestration** shape.</span></span>  
  
-   <span data-ttu-id="e9219-129">オーケストレーション インスタンスが中断される。</span><span class="sxs-lookup"><span data-stu-id="e9219-129">The orchestration instance is suspended.</span></span>  
  
-   <span data-ttu-id="e9219-130">表示されたら、オーケストレーション エンジンがシャット ダウンする、しようと制御情報だけでなく、実行中のすべてのオーケストレーション インスタンスの現在の状態を保存できるように、もう一度起動されたときに実行を再開できます。</span><span class="sxs-lookup"><span data-stu-id="e9219-130">When the orchestration engine is asked to shut down, it will try to save control information as well as the current state of all running orchestration instances, so that it can resume running them when it is started again.</span></span> <span data-ttu-id="e9219-131">エンジンが現在の状態の保存に失敗した場合、シャットダウン前の最後の永続化ポイントからオーケストレーション インスタンスが再開されます。</span><span class="sxs-lookup"><span data-stu-id="e9219-131">If the engine is unsuccessful in saving the current state, the engine will resume the orchestration instance from the last persistence point that occurred before the shutdown.</span></span> <span data-ttu-id="e9219-132">これは、制御された条件下でのシステム シャットダウンおよび異常終了に適用されます。</span><span class="sxs-lookup"><span data-stu-id="e9219-132">This applies to the system shutdown in controlled condition as well as abnormal termination.</span></span>  
  
-   <span data-ttu-id="e9219-133">インスタンスの退避が必要であるとエンジンが判断する。</span><span class="sxs-lookup"><span data-stu-id="e9219-133">The engine determines that the instance should be dehydrated.</span></span>  
  
-   <span data-ttu-id="e9219-134">オーケストレーション インスタンスが完了する。</span><span class="sxs-lookup"><span data-stu-id="e9219-134">The orchestration instance is finished.</span></span>  
  
## <a name="serialization"></a><span data-ttu-id="e9219-135">シリアル化</span><span class="sxs-lookup"><span data-stu-id="e9219-135">Serialization</span></span>  
 <span data-ttu-id="e9219-136">直接的または (他のオブジェクトを介して) 間接的 にオーケストレーションが参照するすべてのオブジェクト インスタンスは、オーケストレーションの状態を保存するためにシリアル化に対応する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e9219-136">All object instances that your orchestration refers to directly or indirectly (as through other objects) must be serializable for your orchestration state to be persisted.</span></span> <span data-ttu-id="e9219-137">ただし、これには次の 2 つの例外があります。</span><span class="sxs-lookup"><span data-stu-id="e9219-137">There are two exceptions:</span></span>  
  
-   <span data-ttu-id="e9219-138">シリアル化できないオブジェクトをアトミック トランザクション内部で宣言できます。</span><span class="sxs-lookup"><span data-stu-id="e9219-138">You can have a nonserializable object declared inside an atomic transaction.</span></span> <span data-ttu-id="e9219-139">アトミックのスコープが永続化ポイントを含まないので、この処理を実行できます。</span><span class="sxs-lookup"><span data-stu-id="e9219-139">You can do this because atomic scopes do not contain persistence points.</span></span>  
  
-   <span data-ttu-id="e9219-140">System.Xml.XmlDocument は、シリアル化可能なクラスではありませんが、例外として扱われ、どこでも使用できます。</span><span class="sxs-lookup"><span data-stu-id="e9219-140">System.Xml.XmlDocument is not a serializable class; it is handled as a special case and can be used anywhere.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="e9219-141">.NET オブジェクトを保存するには、シリアル化可能としてマークする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e9219-141">In order for a .NET object to be persisted, it must be marked as serializable.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e9219-142">COM オブジェクトは、標準の .NET シリアル化手順で保存できません。</span><span class="sxs-lookup"><span data-stu-id="e9219-142">COM objects cannot be persisted using standard .NET serialization procedures.</span></span> <span data-ttu-id="e9219-143">アトミック トランザクションの外部で COM オブジェクトを呼び出す場合は、.NET シリアル化可能で、COM オブジェクトの状態を保存および復元する方法が組み込まれている .NET オブジェクトに、COM オブジェクトをラップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e9219-143">If you want to call a COM object outside of an atomic transaction, you must wrap the COM object in a .NET object that is .NET serializable and knows how to persist and restore the state of the COM object.</span></span>  
  
## <a name="system-shutdown"></a><span data-ttu-id="e9219-144">システム シャットダウン</span><span class="sxs-lookup"><span data-stu-id="e9219-144">System Shutdown</span></span>  
 <span data-ttu-id="e9219-145">表示されたら、オーケストレーション エンジンがシャット ダウンする、しようと制御情報だけでなく、実行中のすべてのオーケストレーション インスタンスの現在の状態を保存できるように、もう一度起動されたときに実行を再開できます。</span><span class="sxs-lookup"><span data-stu-id="e9219-145">When the orchestration engine is asked to shut down, it will try to save control information as well as the current state of all running orchestration instances, so that it can resume running them when it is started again.</span></span> <span data-ttu-id="e9219-146">エンジンが現在の状態の保存に失敗した場合、シャットダウン前の最後の永続化ポイントからオーケストレーション インスタンスが再開されます。</span><span class="sxs-lookup"><span data-stu-id="e9219-146">If the engine is unsuccessful in saving the current state, the engine will resume the orchestration instance from the last persistence point that occurred before the shutdown.</span></span> <span data-ttu-id="e9219-147">これは、制御された条件下でのシステム シャットダウンおよび異常終了に適用されます。</span><span class="sxs-lookup"><span data-stu-id="e9219-147">This applies to the system shutdown in controlled condition as well as abnormal termination.</span></span>  
  
## <a name="recovery"></a><span data-ttu-id="e9219-148">復旧</span><span class="sxs-lookup"><span data-stu-id="e9219-148">Recovery</span></span>  
 <span data-ttu-id="e9219-149">オーケストレーション エンジンは、オーケストレーション インスタンスの状態情報を固定記憶装置に定期的に保存します。また、システムのシャットダウン時の状態も保存します。</span><span class="sxs-lookup"><span data-stu-id="e9219-149">The engine regularly saves to persistent storage the state information of an orchestration instance, and it also saves state in the event of a system shutdown.</span></span>  
  
 <span data-ttu-id="e9219-150">オーケストレーション インスタンスが何らかの理由で異常終了した場合、最後に保存した状態からインスタンスを復旧できます。このため、中断がなかったかのように、インスタンスの実行を続けることができます。</span><span class="sxs-lookup"><span data-stu-id="e9219-150">When an orchestration instance fails abnormally for whatever reason, the instance can be recovered from the last persisted state, and it can continue to run as if there were no interruption.</span></span> <span data-ttu-id="e9219-151">これは、インスタンスを実行している元のサーバーが何らかの理由で利用できなくなった場合に有効です。その場合、インスタンスの実行を別のコンピューターで再開するだけです。</span><span class="sxs-lookup"><span data-stu-id="e9219-151">This is true even if the original server that the instance ran on goes out of service for some reason; the instance can simply resume running on a separate machine.</span></span> <span data-ttu-id="e9219-152">このマルチサーバーの復旧モデルを使用すると、クラスタリングが不要になります。</span><span class="sxs-lookup"><span data-stu-id="e9219-152">Because of this multi-server recovery model, you no longer need clustering.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9219-153">参照</span><span class="sxs-lookup"><span data-stu-id="e9219-153">See Also</span></span>  
 [<span data-ttu-id="e9219-154">オーケストレーションの退避と復元</span><span class="sxs-lookup"><span data-stu-id="e9219-154">Orchestration Dehydration and Rehydration</span></span>](../core/orchestration-dehydration-and-rehydration.md)