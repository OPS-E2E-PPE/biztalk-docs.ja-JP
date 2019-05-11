---
title: 永続性とオーケストレーション エンジン |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestration engine, persistence
- persistence
- orchestration engine, serialization
ms.assetid: 088230ef-13b3-440b-9875-6449f29dd5c6
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c322c000002360e7637db3971721aa53e9225c5b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65314525"
---
# <a name="persistence-and-the-orchestration-engine"></a><span data-ttu-id="c76c6-102">永続性とオーケストレーション エンジン</span><span class="sxs-lookup"><span data-stu-id="c76c6-102">Persistence and the Orchestration Engine</span></span>
<span data-ttu-id="c76c6-103">状態の永続化、管理および復元は、オーケストレーション エンジンの基本的な機能の多くの基礎を形成します。</span><span class="sxs-lookup"><span data-stu-id="c76c6-103">State persistence, its management and restoration form the basis of a lot of fundamental functionalities of the orchestration engine.</span></span> <span data-ttu-id="c76c6-104">具体的には、永続化が正しく機能するが重要です。</span><span class="sxs-lookup"><span data-stu-id="c76c6-104">In particular, persistence is critical to the correct functioning of:</span></span>  
  
- <span data-ttu-id="c76c6-105">退避と復元</span><span class="sxs-lookup"><span data-stu-id="c76c6-105">Dehydration and rehydration</span></span>  
  
- <span data-ttu-id="c76c6-106">マシンに依存しない実行と復元</span><span class="sxs-lookup"><span data-stu-id="c76c6-106">Machine agnostic execution and rehydration</span></span>  
  
- <span data-ttu-id="c76c6-107">補正モデル</span><span class="sxs-lookup"><span data-stu-id="c76c6-107">Compensation model</span></span>  
  
- <span data-ttu-id="c76c6-108">管理されたシステムのシャット ダウン</span><span class="sxs-lookup"><span data-stu-id="c76c6-108">Controlled System Shutdown</span></span>  
  
- <span data-ttu-id="c76c6-109">復旧</span><span class="sxs-lookup"><span data-stu-id="c76c6-109">Recovery</span></span>  
  
  <span data-ttu-id="c76c6-110">オーケストレーション エンジンは、永続的ストレージに全体の状態を保存さまざまなポイントで実行中のオーケストレーション インスタンスを復元するため、インスタンスは後で完全にメモリ内。</span><span class="sxs-lookup"><span data-stu-id="c76c6-110">The orchestration engine saves to persistent storage the entire state of a running orchestration instance at various points, so that the instance can later be completely restored in memory.</span></span> <span data-ttu-id="c76c6-111">状態は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c76c6-111">The state includes:</span></span>  
  
- <span data-ttu-id="c76c6-112">現在の進行状況を含む、エンジンの内部状態。</span><span class="sxs-lookup"><span data-stu-id="c76c6-112">The internal state of the engine, including its current progress.</span></span>  
  
- <span data-ttu-id="c76c6-113">状態情報を保持し、オーケストレーションで使用されているすべての .NET コンポーネントの状態。</span><span class="sxs-lookup"><span data-stu-id="c76c6-113">The state of any .NET components that maintain state information and are being used by the orchestration.</span></span>  
  
- <span data-ttu-id="c76c6-114">メッセージと変数の値。</span><span class="sxs-lookup"><span data-stu-id="c76c6-114">Message and variable values.</span></span>  
  
## <a name="persistence-points"></a><span data-ttu-id="c76c6-115">永続化ポイント</span><span class="sxs-lookup"><span data-stu-id="c76c6-115">Persistence Points</span></span>  
 <span data-ttu-id="c76c6-116">オーケストレーション エンジンは、さまざまな時点で実行中のオーケストレーション インスタンスの状態を保存します。</span><span class="sxs-lookup"><span data-stu-id="c76c6-116">The orchestration engine saves the state of a running orchestration instance at various points.</span></span> <span data-ttu-id="c76c6-117">オーケストレーション インスタンスにリハイド レートで、制御されたシャット ダウンから起動するか、または予期しないシャット ダウンから回復する必要がある場合、最後の永続性ポイントからオーケストレーション インスタンスを実行して、何が発生した場合と同様にされます。</span><span class="sxs-lookup"><span data-stu-id="c76c6-117">If it needs to rehydrate the orchestration instance, start up from a controlled shutdown, or recover from an unexpected shutdown, it will run the orchestration instance from the last persistence point, as though nothing else had occurred.</span></span> <span data-ttu-id="c76c6-118">たとえば、メッセージを受信する状態を保存する前に、予期しないシャット ダウンがある場合、エンジンは記録されませんが、メッセージを受信し、受信、もう一度再起動時にこと。</span><span class="sxs-lookup"><span data-stu-id="c76c6-118">For example, if a message is received but there is an unexpected shutdown before state can be saved, the engine will not record that it has received the message, and will receive it again upon restarting.</span></span> <span data-ttu-id="c76c6-119">エンジンは、次の状況でオーケストレーションの状態を保存します。</span><span class="sxs-lookup"><span data-stu-id="c76c6-119">The engine will save the state of an orchestration in the following circumstances:</span></span>  
  
-   <span data-ttu-id="c76c6-120">トランザクション スコープの末尾に到達します。</span><span class="sxs-lookup"><span data-stu-id="c76c6-120">The end of a transactional scope is reached.</span></span>  
  
    -   <span data-ttu-id="c76c6-121">エンジンは、補正を実行する正しくに応じてようにし、オーケストレーションを再開するポイントが明確に定義されているように、トランザクション スコープの最後の状態を保存します。</span><span class="sxs-lookup"><span data-stu-id="c76c6-121">The engine saves state at the end of a transactional scope so that the point at which the orchestration should resume is defined unambiguously, and so that compensation can be carried out correctly if necessary.</span></span>  
  
    -   <span data-ttu-id="c76c6-122">永続化が成功した場合、スコープの最後から実行するオーケストレーションが引き続きそれ以外の場合、適切な例外ハンドラーが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="c76c6-122">The orchestration will continue to run from the end of the scope if persistence was successful; otherwise, the appropriate exception handler will be invoked.</span></span>  
  
    -   <span data-ttu-id="c76c6-123">スコープがトランザクションでアトミックの場合、エンジンは、コミット時にアトミックのスコープの最後の状態を保存します。</span><span class="sxs-lookup"><span data-stu-id="c76c6-123">If the scope is transactional and atomic, the engine will save state at the end of the atomic scope when it commits.</span></span>  
  
    -   <span data-ttu-id="c76c6-124">スコープがトランザクションで実行時間の長い場合は、エンジンが新しいトランザクションを生成し、スコープが完了すると、ランタイムの完全な状態を永続化します。</span><span class="sxs-lookup"><span data-stu-id="c76c6-124">If the scope is transactional and long-running, the engine will generate a new transaction and persist the complete state of the runtime when the scope completes.</span></span>  
  
-   <span data-ttu-id="c76c6-125">デバッグのブレークポイントに到達します。</span><span class="sxs-lookup"><span data-stu-id="c76c6-125">A debugging breakpoint is reached.</span></span>  
  
-   <span data-ttu-id="c76c6-126">メッセージが送信されます。</span><span class="sxs-lookup"><span data-stu-id="c76c6-126">A message is sent.</span></span> <span data-ttu-id="c76c6-127">唯一の例外は、アトミック トランザクション スコープ内から送信されたメッセージです。</span><span class="sxs-lookup"><span data-stu-id="c76c6-127">The only exception to this is when a message is sent from within an atomic transaction scope.</span></span>  
  
-   <span data-ttu-id="c76c6-128">オーケストレーションが別のオーケストレーションを非同期的に起動と同様、**オーケストレーションの開始**図形。</span><span class="sxs-lookup"><span data-stu-id="c76c6-128">The orchestration starts another orchestration asynchronously, as with the **Start Orchestration** shape.</span></span>  
  
-   <span data-ttu-id="c76c6-129">オーケストレーション インスタンスが中断されます。</span><span class="sxs-lookup"><span data-stu-id="c76c6-129">The orchestration instance is suspended.</span></span>  
  
-   <span data-ttu-id="c76c6-130">オーケストレーション エンジンがシャット ダウンしようとして、再び開始するときに実行を再開できるように制御情報だけでなく、実行中のすべてのオーケストレーション インスタンスの現在の状態を保存するとは。</span><span class="sxs-lookup"><span data-stu-id="c76c6-130">When the orchestration engine is asked to shut down, it will try to save control information as well as the current state of all running orchestration instances, so that it can resume running them when it is started again.</span></span> <span data-ttu-id="c76c6-131">エンジンが現在の状態の保存に失敗した場合は、シャット ダウンする前に発生した最後の永続性ポイントからオーケストレーション インスタンスが再開されます。</span><span class="sxs-lookup"><span data-stu-id="c76c6-131">If the engine is unsuccessful in saving the current state, the engine will resume the orchestration instance from the last persistence point that occurred before the shutdown.</span></span> <span data-ttu-id="c76c6-132">これは、異常終了と同様に制御された条件下でシステムのシャット ダウンに適用されます。</span><span class="sxs-lookup"><span data-stu-id="c76c6-132">This applies to the system shutdown in controlled condition as well as abnormal termination.</span></span>  
  
-   <span data-ttu-id="c76c6-133">エンジンは、インスタンスが退避があることを決定します。</span><span class="sxs-lookup"><span data-stu-id="c76c6-133">The engine determines that the instance should be dehydrated.</span></span>  
  
-   <span data-ttu-id="c76c6-134">オーケストレーション インスタンスが完了しました。</span><span class="sxs-lookup"><span data-stu-id="c76c6-134">The orchestration instance is finished.</span></span>  
  
## <a name="serialization"></a><span data-ttu-id="c76c6-135">シリアル化</span><span class="sxs-lookup"><span data-stu-id="c76c6-135">Serialization</span></span>  
 <span data-ttu-id="c76c6-136">オーケストレーションが直接または間接的に参照するすべてのオブジェクト インスタンス (別のオブジェクトを同様に)、オーケストレーションの状態を永続化するためにシリアル化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c76c6-136">All object instances that your orchestration refers to directly or indirectly (as through other objects) must be serializable for your orchestration state to be persisted.</span></span> <span data-ttu-id="c76c6-137">2 つの例外があります。</span><span class="sxs-lookup"><span data-stu-id="c76c6-137">There are two exceptions:</span></span>  
  
-   <span data-ttu-id="c76c6-138">シリアル化できないオブジェクトがアトミックのトランザクション内で宣言されていることができます。</span><span class="sxs-lookup"><span data-stu-id="c76c6-138">You can have a nonserializable object declared inside an atomic transaction.</span></span> <span data-ttu-id="c76c6-139">アトミックのスコープに永続化ポイントが含まれていないために、これを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="c76c6-139">You can do this because atomic scopes do not contain persistence points.</span></span>  
  
-   <span data-ttu-id="c76c6-140">System.Xml.XmlDocument はシリアル化可能なクラスではありません。特殊なケースとして処理され、どこでも使用できます。</span><span class="sxs-lookup"><span data-stu-id="c76c6-140">System.Xml.XmlDocument is not a serializable class; it is handled as a special case and can be used anywhere.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="c76c6-141">永続化する .NET オブジェクトの順序である必要がありますマークする必要がシリアル化可能として。</span><span class="sxs-lookup"><span data-stu-id="c76c6-141">In order for a .NET object to be persisted, it must be marked as serializable.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c76c6-142">標準的な .NET シリアル化の手順を使用して、COM オブジェクトを保存できません。</span><span class="sxs-lookup"><span data-stu-id="c76c6-142">COM objects cannot be persisted using standard .NET serialization procedures.</span></span> <span data-ttu-id="c76c6-143">アトミックのトランザクションの外部で COM オブジェクトを呼び出す場合は、シリアル化可能な .NET は、永続化および COM オブジェクトの状態を復元する方法を認識する .NET オブジェクトで COM オブジェクトをラップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c76c6-143">If you want to call a COM object outside of an atomic transaction, you must wrap the COM object in a .NET object that is .NET serializable and knows how to persist and restore the state of the COM object.</span></span>  
  
## <a name="system-shutdown"></a><span data-ttu-id="c76c6-144">システムのシャット ダウン</span><span class="sxs-lookup"><span data-stu-id="c76c6-144">System Shutdown</span></span>  
 <span data-ttu-id="c76c6-145">オーケストレーション エンジンがシャット ダウンしようとして、再び開始するときに実行を再開できるように制御情報だけでなく、実行中のすべてのオーケストレーション インスタンスの現在の状態を保存するとは。</span><span class="sxs-lookup"><span data-stu-id="c76c6-145">When the orchestration engine is asked to shut down, it will try to save control information as well as the current state of all running orchestration instances, so that it can resume running them when it is started again.</span></span> <span data-ttu-id="c76c6-146">エンジンが現在の状態の保存に失敗した場合は、シャット ダウンする前に発生した最後の永続性ポイントからオーケストレーション インスタンスが再開されます。</span><span class="sxs-lookup"><span data-stu-id="c76c6-146">If the engine is unsuccessful in saving the current state, the engine will resume the orchestration instance from the last persistence point that occurred before the shutdown.</span></span> <span data-ttu-id="c76c6-147">これは、異常終了と同様に制御された条件下でシステムのシャット ダウンに適用されます。</span><span class="sxs-lookup"><span data-stu-id="c76c6-147">This applies to the system shutdown in controlled condition as well as abnormal termination.</span></span>  
  
## <a name="recovery"></a><span data-ttu-id="c76c6-148">復旧</span><span class="sxs-lookup"><span data-stu-id="c76c6-148">Recovery</span></span>  
 <span data-ttu-id="c76c6-149">エンジンは定期的に保存します永続的ストレージに、オーケストレーション インスタンスの状態情報と、システムのシャット ダウンが発生した場合の状態も保存します。</span><span class="sxs-lookup"><span data-stu-id="c76c6-149">The engine regularly saves to persistent storage the state information of an orchestration instance, and it also saves state in the event of a system shutdown.</span></span>  
  
 <span data-ttu-id="c76c6-150">オーケストレーション インスタンスには、異常何らかの理由が失敗した場合、インスタンスは、最後の永続化状態から回復できるし、中断がなかったかのように実行を続けることです。</span><span class="sxs-lookup"><span data-stu-id="c76c6-150">When an orchestration instance fails abnormally for whatever reason, the instance can be recovered from the last persisted state, and it can continue to run as if there were no interruption.</span></span> <span data-ttu-id="c76c6-151">これは、インスタンスの実行元のサーバーがいくつかの理由のサービス外になる場合でも当てはまりますインスタンスは、別のコンピューターで実行されている単純に再開できます。</span><span class="sxs-lookup"><span data-stu-id="c76c6-151">This is true even if the original server that the instance ran on goes out of service for some reason; the instance can simply resume running on a separate machine.</span></span> <span data-ttu-id="c76c6-152">このマルチ サーバーの復旧モデルであるためが不要になったクラスター化します。</span><span class="sxs-lookup"><span data-stu-id="c76c6-152">Because of this multi-server recovery model, you no longer need clustering.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c76c6-153">参照</span><span class="sxs-lookup"><span data-stu-id="c76c6-153">See Also</span></span>  
 [<span data-ttu-id="c76c6-154">オーケストレーションの退避と復元</span><span class="sxs-lookup"><span data-stu-id="c76c6-154">Orchestration Dehydration and Rehydration</span></span>](../core/orchestration-dehydration-and-rehydration.md)