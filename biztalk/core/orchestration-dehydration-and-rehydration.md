---
title: "オーケストレーションの退避と復元 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 57d7c0bf-a707-4ebd-afab-e75dd80c3c34
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 23ec36d960173c9ce912bb89a38b1df9590f84e5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="orchestration-dehydration-and-rehydration"></a><span data-ttu-id="f99d4-102">オーケストレーションの退避と復元</span><span class="sxs-lookup"><span data-stu-id="f99d4-102">Orchestration Dehydration and Rehydration</span></span>
<span data-ttu-id="f99d4-103">長時間実行される多くのビジネス プロセスを同時に実行している場合、メモリとパフォーマンスで問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f99d4-103">When many long-running business processes are running at the same time, memory and performance are potential issues.</span></span> <span data-ttu-id="f99d4-104">オーケストレーション エンジンでは、オーケストレーション インスタンスを "退避" および "復元" することで、これらの問題に対処します。</span><span class="sxs-lookup"><span data-stu-id="f99d4-104">The orchestration engine addresses these issues by "dehydrating" and "rehydrating" orchestration instances.</span></span>  
  
 <span data-ttu-id="f99d4-105">退避とは、オーケストレーションの状態を SQL Server データベースにシリアル化するプロセスのことです。</span><span class="sxs-lookup"><span data-stu-id="f99d4-105">Dehydration is the process of serializing the state of an orchestration into a SQL Server database.</span></span> <span data-ttu-id="f99d4-106">復元では、このプロセスの逆: データベースからオーケストレーションの前回の実行状態を逆シリアル化します。</span><span class="sxs-lookup"><span data-stu-id="f99d4-106">Rehydration is the reverse of this process: deserializing the last running state of an orchestration from the database.</span></span> <span data-ttu-id="f99d4-107">退避は、メモリ内で一度にインスタンス化する必要があるオーケストレーションの数を減らすことによって、システム リソースの使用を最小限に抑えるために使用します。</span><span class="sxs-lookup"><span data-stu-id="f99d4-107">Dehydration is used to minimize the use of system resources by reducing the number of orchestrations that have to be instantiated in memory at one time.</span></span>  
  
## <a name="dehydration"></a><span data-ttu-id="f99d4-108">退避</span><span class="sxs-lookup"><span data-stu-id="f99d4-108">Dehydration</span></span>  
 <span data-ttu-id="f99d4-109">オーケストレーション エンジンは、オーケストレーション インスタンスが長い時間アイドル状態かどうかを判断できます。</span><span class="sxs-lookup"><span data-stu-id="f99d4-109">The orchestration engine might determine that an orchestration instance has been idle for a relatively long period of time.</span></span> <span data-ttu-id="f99d4-110">エンジンは、しきい値を計算して、発生するさまざまなアクションの待機時間を決めます。しきい値を超えた場合、インスタンスが退避されます。</span><span class="sxs-lookup"><span data-stu-id="f99d4-110">It calculates thresholds to determine how long it will wait for various actions to take place, and if those thresholds are exceeded, it dehydrates the instance.</span></span> <span data-ttu-id="f99d4-111">退避は、次の環境で発生します。</span><span class="sxs-lookup"><span data-stu-id="f99d4-111">This can occur under the following circumstances:</span></span>  
  
-   <span data-ttu-id="f99d4-112">オーケストレーションがメッセージの受信を待機しているときに、エンジンで設定されたしきい値の待機時間を過ぎた場合。</span><span class="sxs-lookup"><span data-stu-id="f99d4-112">When the orchestration is waiting to receive a message, and the wait is longer than a threshold determined by the engine.</span></span>  
  
-   <span data-ttu-id="f99d4-113">オーケストレーションは、「リッスンしている場合」、メッセージのように使用するときに、**リッスン**形状、およびいない分岐は、エンジンによって設定されたしきい値の前にトリガーします。</span><span class="sxs-lookup"><span data-stu-id="f99d4-113">When the orchestration is "listening" for a message, as it does when you use a **Listen** shape, and no branch is triggered before a threshold determined by the engine.</span></span> <span data-ttu-id="f99d4-114">唯一の例外は、ときに、**リッスン**図形には、アクティブ化が含まれている受信します。</span><span class="sxs-lookup"><span data-stu-id="f99d4-114">The only exception to this is when the **Listen** shape contains an activation receive.</span></span>  
  
-   <span data-ttu-id="f99d4-115">オーケストレーションの遅延がエンジンで設定されたしきい値を超えた場合。</span><span class="sxs-lookup"><span data-stu-id="f99d4-115">When a delay in the orchestration is longer than a threshold determined by the engine.</span></span>  
  
 <span data-ttu-id="f99d4-116">エンジンは、状態を保存することでインスタンスを退避し、インスタンスに必要なメモリを解放します。</span><span class="sxs-lookup"><span data-stu-id="f99d4-116">The engine dehydrates the instance by saving the state, and frees up the memory required by the instance.</span></span> <span data-ttu-id="f99d4-117">休止しているオーケストレーション インスタンスを退避することにより、多数の長時間実行されるビジネス プロセスを単一のコンピューターで同時に実行できるようになります。</span><span class="sxs-lookup"><span data-stu-id="f99d4-117">By dehydrating dormant orchestration instances, the engine makes it possible for a large number of long-running business processes to run concurrently on the same computer.</span></span>  
  
 <span data-ttu-id="f99d4-118">BizTalk Server には、退避の動作を構成するために設定できるプロパティが 12 個あります。</span><span class="sxs-lookup"><span data-stu-id="f99d4-118">You can set 12 properties to configure how dehydration works in BizTalk Server.</span></span> <span data-ttu-id="f99d4-119">このセクションのトピックを一覧表示し、これらのプロパティとその既定値を記述し、退避の動作に影響を与えるさまざまな値について説明します。</span><span class="sxs-lookup"><span data-stu-id="f99d4-119">The topics in this section list and describe these properties and their default values, and discuss how various values affect dehydration behavior.</span></span>  
  
## <a name="rehydration"></a><span data-ttu-id="f99d4-120">復元</span><span class="sxs-lookup"><span data-stu-id="f99d4-120">Rehydration</span></span>  
 <span data-ttu-id="f99d4-121">オーケストレーション エンジンは、メッセージの受信または遅延図形で指定されているタイムアウトの経過により、オーケストレーション インスタンスの復元を実行できます。</span><span class="sxs-lookup"><span data-stu-id="f99d4-121">The orchestration engine can be triggered to rehydrate an orchestration instance by the receipt of a message or by the expiration of a time-out specified in a Delay shape.</span></span> <span data-ttu-id="f99d4-122">保存されているオーケストレーション インスタンスをメモリに読み込みます、その状態を復元し、ところ、ポイントから実行します。</span><span class="sxs-lookup"><span data-stu-id="f99d4-122">It then loads the saved orchestration instance into memory, restores its state, and runs it from the point where it left off.</span></span> <span data-ttu-id="f99d4-123">詳細については、オーケストレーションに図形を使用して、次を参照してください。[オーケストレーション図形](../core/orchestration-shapes.md)です。</span><span class="sxs-lookup"><span data-stu-id="f99d4-123">For more information about using shapes in orchestrations, see [Orchestration Shapes](../core/orchestration-shapes.md).</span></span>  
  
 <span data-ttu-id="f99d4-124">オーケストレーションは、複数のサーバーで実行するように構成できます。</span><span class="sxs-lookup"><span data-stu-id="f99d4-124">An orchestration can be configured to run on more than one server.</span></span> <span data-ttu-id="f99d4-125">退避されたオーケストレーション インスタンスは、これらのサーバーのどれにでも復元できます。</span><span class="sxs-lookup"><span data-stu-id="f99d4-125">After an orchestration instance has been dehydrated, it can be rehydrated on any of these servers.</span></span> <span data-ttu-id="f99d4-126">いずれかのサーバーが停止した場合、エンジンは引き続き別のサーバーでオーケストレーションを実行し、以前の状態を継続します。</span><span class="sxs-lookup"><span data-stu-id="f99d4-126">If one server goes down, the engine continues to run the orchestration on a different server, continuing from its previous state.</span></span> <span data-ttu-id="f99d4-127">また、エンジンは、この機能を利用して、サーバー間の負荷分散も実装します。</span><span class="sxs-lookup"><span data-stu-id="f99d4-127">The engine also takes advantage of this feature to implement load balancing across servers.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f99d4-128">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="f99d4-128">In This Section</span></span>  
  
-   [<span data-ttu-id="f99d4-129">BizTalk Server 2004 からの退避ポリシーの変更</span><span class="sxs-lookup"><span data-stu-id="f99d4-129">Changes in Dehydration Policy from BizTalk Server 2004</span></span>](../core/changes-in-dehydration-policy-from-biztalk-server-2004.md)  
  
-   [<span data-ttu-id="f99d4-130">既定の退避プロパティ</span><span class="sxs-lookup"><span data-stu-id="f99d4-130">Dehydration Default Properties</span></span>](../core/dehydration-default-properties.md)  
  
-   [<span data-ttu-id="f99d4-131">退避を計算する方法</span><span class="sxs-lookup"><span data-stu-id="f99d4-131">How to Calculate Dehydration</span></span>](../core/how-to-calculate-dehydration.md)  
  
-   [<span data-ttu-id="f99d4-132">退避の計算のサンプル</span><span class="sxs-lookup"><span data-stu-id="f99d4-132">Sample Dehydration Calculation</span></span>](../core/sample-dehydration-calculation.md)  
  
-   [<span data-ttu-id="f99d4-133">オーケストレーションの退避のパフォーマンス カウンター</span><span class="sxs-lookup"><span data-stu-id="f99d4-133">Orchestration Dehydration Performance Counters</span></span>](../core/orchestration-dehydration-performance-counters.md)  
  
-   [<span data-ttu-id="f99d4-134">BTSNTSvc.exe.config ファイル</span><span class="sxs-lookup"><span data-stu-id="f99d4-134">BTSNTSvc.exe.config File</span></span>](../core/btsntsvc-exe-config-file.md)  
  
-   [<span data-ttu-id="f99d4-135">退避の動作に影響を与える他のアクティビティ</span><span class="sxs-lookup"><span data-stu-id="f99d4-135">Other Activities That Can Affect Dehydration Behavior</span></span>](../core/other-activities-that-can-affect-dehydration-behavior.md)