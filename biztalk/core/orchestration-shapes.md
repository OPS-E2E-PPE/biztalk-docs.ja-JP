---
title: "オーケストレーション図形 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Delay shape [Orchestration Designer]
- Loop shape [Orchestration Designer]
- Throw Exception shape [Orchestration Designer]
- Expression shape [Orchestration Designer]
- Decide shape [Orchestration Designer]
- Receive shape [Orchestration Designer]
- Compensate shape [Orchestration Designer]
- orchestrations, shapes
- Suspend shape [Orchestration Designer]
- Send shape [Orchestration Designer]
- Group shape [Orchestration Designer]
- Listen shape [Orchestration Designer]
- shapes, about shapes
- Construct Message shape [Orchestration Designer]
- Parallel Actions shape [Orchestration Designer]
- Call Rules shape [Orchestration Designer]
- Start Orchestration shape [Orchestration Designer]
- Transform shape [Orchestration Designer]
- Message Assignment shape [Orchestration Designer]
- Role Link shape [Orchestration Designer]
- Call Orchestration shape [Orchestration Designer]
- Port shape [Orchestration Designer]
- shapes
- Scope shape [Orchestration Designer]
- Terminate shape [Orchestration Designer]
- Orchestration Designer, shapes
- Insufficient Configuration Smart Tag [Orchestration Designer]
ms.assetid: a1d03baa-a267-499d-94fc-700b3e959458
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 181656208b757c595feb9d19ee786fe91f1b78f8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="orchestration-shapes"></a><span data-ttu-id="f8c80-102">オーケストレーション図形</span><span class="sxs-lookup"><span data-stu-id="f8c80-102">Orchestration Shapes</span></span>
<span data-ttu-id="f8c80-103">オーケストレーション デザイナーは、オーケストレーションを作成するためのビジュアル ツールです。</span><span class="sxs-lookup"><span data-stu-id="f8c80-103">Orchestration Designer is a visual tool for creating orchestrations.</span></span> <span data-ttu-id="f8c80-104">このツールで提供されている複数の図形を、基になる操作の視覚的な表現としてデザイン画面に配置することで、オーケストレーションを効率よくデザインし実装できます。</span><span class="sxs-lookup"><span data-stu-id="f8c80-104">It provides several shapes that you can place on the design surface as visual representations of underlying actions, and they can help you to efficiently design and implement an orchestration.</span></span>  
  
 <span data-ttu-id="f8c80-105">**不十分な構成アクション**</span><span class="sxs-lookup"><span data-stu-id="f8c80-105">**Insufficient Configuration Action**</span></span>  
  
 ![](../core/media/ebiz-orch-insufficconfig.gif "ebiz_orch_insufficconfig")  
  
> [!NOTE]
>  <span data-ttu-id="f8c80-106">オーケストレーション デザイナーでは、関連付けられた図形が完全に構成されていないことが検出された場合に、不十分な構成の操作が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f8c80-106">The Insufficient Configuration Action is displayed in the Orchestration designer when the Orchestration Designer detects that the associated shape is not completely configured.</span></span> <span data-ttu-id="f8c80-107">オーケストレーション内の図形が完全に構成されていないと、関連付けられたオーケストレーションはコンパイルされません。</span><span class="sxs-lookup"><span data-stu-id="f8c80-107">If a shape in an Orchestration is not completely configured then the associated Orchestration will not compile.</span></span>  
  
 <span data-ttu-id="f8c80-108">次の表では、使用できる図形の一覧を示し、各図形の機能を簡単に説明します。</span><span class="sxs-lookup"><span data-stu-id="f8c80-108">The following table lists the available shapes, along with a brief description of the function of each shape.</span></span>  
  
|<span data-ttu-id="f8c80-109">図形</span><span class="sxs-lookup"><span data-stu-id="f8c80-109">Shape</span></span>|<span data-ttu-id="f8c80-110">図形の名前</span><span class="sxs-lookup"><span data-stu-id="f8c80-110">Shape Name</span></span>|<span data-ttu-id="f8c80-111">用途</span><span class="sxs-lookup"><span data-stu-id="f8c80-111">Purpose</span></span>|  
|-----------|----------------|-------------|  
|![](../core/media/ebiz-orch-callorchestrat.gif "ebiz_orch_callorchestrat")|<span data-ttu-id="f8c80-112">**オーケストレーションを呼び出し**</span><span class="sxs-lookup"><span data-stu-id="f8c80-112">**Call Orchestration**</span></span>|<span data-ttu-id="f8c80-113">オーケストレーションで、別のオーケストレーションを同期的に呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="f8c80-113">Enables your orchestration to call another orchestration synchronously.</span></span>|  
|![](../core/media/ebiz-orch-call-rules.gif "ebiz_orch_call_rules")|<span data-ttu-id="f8c80-114">**呼び出し規則**</span><span class="sxs-lookup"><span data-stu-id="f8c80-114">**Call Rules**</span></span>|<span data-ttu-id="f8c80-115">オーケストレーションで実行されるビジネス ルール ポリシーを構成できます。</span><span class="sxs-lookup"><span data-stu-id="f8c80-115">Enables you to configure a Business Rules policy to be executed in your orchestration.</span></span>|  
|![](../core/media/ebiz-orch-compensate.gif "ebiz_orch_compensate")|<span data-ttu-id="f8c80-116">**補正**</span><span class="sxs-lookup"><span data-stu-id="f8c80-116">**Compensate**</span></span>|<span data-ttu-id="f8c80-117">エラー発生時に、オーケストレーションで既に実行された操作を元に戻したり補正したりするためのコードを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="f8c80-117">Enables you to call code to undo or compensate for operations already performed by the orchestration when an error occurs.</span></span>|  
|![](../core/media/ebiz-orch-constructmsg.gif "ebiz_orch_constructmsg")|<span data-ttu-id="f8c80-118">**メッセージの構築**</span><span class="sxs-lookup"><span data-stu-id="f8c80-118">**Construct Message**</span></span>|<span data-ttu-id="f8c80-119">メッセージを構築できます。</span><span class="sxs-lookup"><span data-stu-id="f8c80-119">Enables you to construct a message.</span></span>|  
|![](../core/media/ebiz-orch-decide.gif "ebiz_orch_decide")|<span data-ttu-id="f8c80-120">**決定**</span><span class="sxs-lookup"><span data-stu-id="f8c80-120">**Decide**</span></span>|<span data-ttu-id="f8c80-121">オーケストレーション内で条件に応じて分岐できます。</span><span class="sxs-lookup"><span data-stu-id="f8c80-121">Enables you to conditionally branch in your orchestration.</span></span>|  
|![](../core/media/ebiz-orch-delay.gif "ebiz_orch_delay")|<span data-ttu-id="f8c80-122">**遅延**</span><span class="sxs-lookup"><span data-stu-id="f8c80-122">**Delay**</span></span>|<span data-ttu-id="f8c80-123">タイムアウト間隔に基づいてオーケストレーションの遅延を設定できます。</span><span class="sxs-lookup"><span data-stu-id="f8c80-123">Enables you to build delays in your orchestration based on a time-out interval.</span></span>|  
|![](../core/media/ebiz-orch-assign.gif "ebiz_orch_assign")|<span data-ttu-id="f8c80-124">**[式]**</span><span class="sxs-lookup"><span data-stu-id="f8c80-124">**Expression**</span></span>|<span data-ttu-id="f8c80-125">変数に値を割り当てるか、.NET を呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="f8c80-125">Enables you to assign values to variables or make .NET calls.</span></span>|  
|![](../core/media/ebiz-orch-group.gif "ebiz_orch_group")|<span data-ttu-id="f8c80-126">**[グループ]**</span><span class="sxs-lookup"><span data-stu-id="f8c80-126">**Group**</span></span>|<span data-ttu-id="f8c80-127">視覚的にわかりやすくなるように、折りたたみと展開が可能な 1 つの単位に操作をグループ化できます。</span><span class="sxs-lookup"><span data-stu-id="f8c80-127">Enables you to group operations into a single collapsible and expandable unit for visual convenience.</span></span>|  
|![](../core/media/ebiz-orch-listen.gif "ebiz_orch_listen")|<span data-ttu-id="f8c80-128">**リッスン**</span><span class="sxs-lookup"><span data-stu-id="f8c80-128">**Listen**</span></span>|<span data-ttu-id="f8c80-129">受信したメッセージやタイムアウト期間の終了などの条件に応じてオーケストレーションを分岐できます。</span><span class="sxs-lookup"><span data-stu-id="f8c80-129">Enables your orchestration to conditionally branch depending on messages received or the expiration of a timeout period.</span></span>|  
|![](../core/media/ebiz-orch-loop.gif "ebiz_orch_loop")|<span data-ttu-id="f8c80-130">**ループ**</span><span class="sxs-lookup"><span data-stu-id="f8c80-130">**Loop**</span></span>|<span data-ttu-id="f8c80-131">条件が満たされるまでオーケストレーションをループできます。</span><span class="sxs-lookup"><span data-stu-id="f8c80-131">Enables your orchestration to loop until a condition is met.</span></span>|  
|![](../core/media/ebiz-orch-assign.gif "ebiz_orch_assign")|<span data-ttu-id="f8c80-132">**メッセージの割り当て**</span><span class="sxs-lookup"><span data-stu-id="f8c80-132">**Message Assignment**</span></span>|<span data-ttu-id="f8c80-133">メッセージの値を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="f8c80-133">Enables you to assign message values.</span></span>|  
|![](../core/media/ebiz-orch-paralactions.gif "ebiz_orch_paralactions")|<span data-ttu-id="f8c80-134">**並列アクション**</span><span class="sxs-lookup"><span data-stu-id="f8c80-134">**Parallel Actions**</span></span>|<span data-ttu-id="f8c80-135">オーケストレーション内で複数の操作を互いに独立して実行できます。</span><span class="sxs-lookup"><span data-stu-id="f8c80-135">Enables your orchestration to perform two or more operations independently of each other.</span></span>|  
|![](../core/media/ebiz-orch-port.gif "ebiz_orch_port")|<span data-ttu-id="f8c80-136">**[ポート]**</span><span class="sxs-lookup"><span data-stu-id="f8c80-136">**Port**</span></span>|<span data-ttu-id="f8c80-137">メッセージの送信先と送信方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="f8c80-137">Defines where and how messages are transmitted.</span></span>|  
|![](../core/media/ebiz-orch-receive.gif "ebiz_orch_receive")|<span data-ttu-id="f8c80-138">**受信**</span><span class="sxs-lookup"><span data-stu-id="f8c80-138">**Receive**</span></span>|<span data-ttu-id="f8c80-139">オーケストレーションでメッセージを受信できます。</span><span class="sxs-lookup"><span data-stu-id="f8c80-139">Enables you to receive a message in your orchestration.</span></span>|  
|![](../core/media/ebiz-orch-rolelink.gif "ebiz_orch_rolelink")|<span data-ttu-id="f8c80-140">**ロール リンク**</span><span class="sxs-lookup"><span data-stu-id="f8c80-140">**Role Link**</span></span>|<span data-ttu-id="f8c80-141">複数の異なるトランスポートやエンドポイントを通じて同じ論理パートナーと通信するためのポートのコレクションを作成できます。</span><span class="sxs-lookup"><span data-stu-id="f8c80-141">Enables you to create a collection of ports that communicate with the same logical partner, perhaps through different transports or endpoints.</span></span>|  
|![](../core/media/ebiz-orch-scope.gif "ebiz_orch_scope")|<span data-ttu-id="f8c80-142">**スコープ**</span><span class="sxs-lookup"><span data-stu-id="f8c80-142">**Scope**</span></span>|<span data-ttu-id="f8c80-143">トランザクションおよび例外処理のフレームワークを提供します。</span><span class="sxs-lookup"><span data-stu-id="f8c80-143">Provides a framework for transactions and exception handling.</span></span>|  
|![](../core/media/ebiz-orch-send.gif "ebiz_orch_send")|<span data-ttu-id="f8c80-144">**送信**</span><span class="sxs-lookup"><span data-stu-id="f8c80-144">**Send**</span></span>|<span data-ttu-id="f8c80-145">オーケストレーションからメッセージを送信できます。</span><span class="sxs-lookup"><span data-stu-id="f8c80-145">Enables you to send a message from your orchestration.</span></span>|  
|![](../core/media/ebiz-orch-strtorchestrat.gif "ebiz_orch_strtorchestrat")|<span data-ttu-id="f8c80-146">**オーケストレーションを開始します。**</span><span class="sxs-lookup"><span data-stu-id="f8c80-146">**Start Orchestration**</span></span>|<span data-ttu-id="f8c80-147">オーケストレーションで、別のオーケストレーションを非同期的に呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="f8c80-147">Enables your orchestration to call another orchestration asynchronously.</span></span>|  
|![](../core/media/ebiz-orch-suspend.gif "ebiz_orch_suspend")|<span data-ttu-id="f8c80-148">**[中断]**</span><span class="sxs-lookup"><span data-stu-id="f8c80-148">**Suspend**</span></span>|<span data-ttu-id="f8c80-149">エラー発生時にオーケストレーションの操作を中断して介入できるようにします。</span><span class="sxs-lookup"><span data-stu-id="f8c80-149">Suspends the operation of your orchestration to enable intervention in the event of some error condition.</span></span>|  
|![](../core/media/ebiz-orch-terminate.gif "ebiz_orch_terminate")|<span data-ttu-id="f8c80-150">**終了**</span><span class="sxs-lookup"><span data-stu-id="f8c80-150">**Terminate**</span></span>|<span data-ttu-id="f8c80-151">エラー発生時にオーケストレーションの操作を直ちに終了できます。</span><span class="sxs-lookup"><span data-stu-id="f8c80-151">Enables you to immediately end the operation of your orchestration in the event of some error condition.</span></span>|  
|![](../core/media/ebiz-orch-throwexcept.gif "ebiz_orch_throwexcept")|<span data-ttu-id="f8c80-152">**例外をスローします。**</span><span class="sxs-lookup"><span data-stu-id="f8c80-152">**Throw Exception**</span></span>|<span data-ttu-id="f8c80-153">エラーが発生した場合に例外を明示的にスローできます。</span><span class="sxs-lookup"><span data-stu-id="f8c80-153">Enables you to explicitly throw an exception in the event of an error.</span></span>|  
|![](../core/media/ebiz-orch-transform.gif "ebiz_orch_transform")|<span data-ttu-id="f8c80-154">**変換**</span><span class="sxs-lookup"><span data-stu-id="f8c80-154">**Transform**</span></span>|<span data-ttu-id="f8c80-155">既存のメッセージから新しいメッセージにフィールドをマップできます。</span><span class="sxs-lookup"><span data-stu-id="f8c80-155">Enables you to map the fields from existing messages into new messages.</span></span>|