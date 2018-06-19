---
title: BizTalk Server のゾンビ |Microsoft ドキュメント
description: BizTalk Server でゾンビ メッセージの一般的な原因
ms.custom: ''
ms.date: 03/23/2016
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0c684891-e984-442f-b5fd-de5f7cf32b44
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9764522d2ff5265b6f28f2f125cb33b2982a7605
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22290546"
---
# <a name="zombies-in-biztalk-server"></a><span data-ttu-id="303c4-103">BizTalk Server のゾンビ</span><span class="sxs-lookup"><span data-stu-id="303c4-103">Zombies in BizTalk Server</span></span>

## <a name="what-is-a-zombie"></a><span data-ttu-id="303c4-104">ゾンビとは</span><span class="sxs-lookup"><span data-stu-id="303c4-104">What is a zombie?</span></span>  
  
-   <span data-ttu-id="303c4-105">ゾンビ メッセージとは、メッセージ ボックスから実行中のオーケストレーションに渡され、オーケストレーションの終了時に "インフライト" であったメッセージのことです。</span><span class="sxs-lookup"><span data-stu-id="303c4-105">A zombie message is a message that was routed to a running orchestration from the messagebox and was "in flight" when the orchestration ended.</span></span> <span data-ttu-id="303c4-106">"インフライト" メッセージとは、サービス インスタンスに回送され、そのサービス インスタンス宛てのメッセージ ボックス キューに入っているメッセージのことです。</span><span class="sxs-lookup"><span data-stu-id="303c4-106">An "in flight" message is a message that has been routed to a service instance and so is in a messagebox queue destined for the service instance.</span></span> <span data-ttu-id="303c4-107">このメッセージは、サブスクライブを行なうオーケストレーション インスタンスによって処理されません。そのため、メッセージが中断され、メッセージの ServiceInstance/状態値が "中断 (再開不可)" になります。</span><span class="sxs-lookup"><span data-stu-id="303c4-107">Since the message can no longer be consumed by the subscribing orchestration instance, the message is suspended and marked with a ServiceInstance/State value of "Suspended (Non-resumable)".</span></span>  
  
-   <span data-ttu-id="303c4-108">ゾンビ サービス インスタンスとは、メッセージ ボックスからオーケストレーション インスタンスに回送されたメッセージがまだ "インフライト" であったときに終了したオーケストレーション インスタンスのことです。</span><span class="sxs-lookup"><span data-stu-id="303c4-108">A zombie service instance is an instance of an orchestration which has completed while a message that was routed to the orchestration instance from the messagebox was still "in flight".</span></span> <span data-ttu-id="303c4-109">オーケストレーション インスタンスが既に終了しているため、"インフライト" メッセージは処理されません。そのため、メッセージが中断され、メッセージの ServiceInstance/状態値が "中断 (再開不可)" になります。</span><span class="sxs-lookup"><span data-stu-id="303c4-109">Since the orchestration instance has ended, it cannot consume the "in flight" messages and so is suspended and marked with a ServiceInstance/State value of "Suspended (Non-resumable)".</span></span>  
  
## <a name="typical-causes"></a><span data-ttu-id="303c4-110">一般的な原因</span><span class="sxs-lookup"><span data-stu-id="303c4-110">Typical causes</span></span>
<span data-ttu-id="303c4-111">ゾンビの発生は一般的に、次のカテゴリのいずれかに分類されます。</span><span class="sxs-lookup"><span data-stu-id="303c4-111">The occurrence of zombies typically falls into one of the following categories:</span></span>  
  
1.  <span data-ttu-id="303c4-112">**終了コントロール メッセージ**– オーケストレーション エンジンは、特定のオーケストレーション インスタンスで現在実行されているすべての処理を取り消すコントロール メッセージの使用を許可します。</span><span class="sxs-lookup"><span data-stu-id="303c4-112">**Terminate control messages** – The orchestration engine allows the use of control messages to cancel all currently running work in a specific orchestration instance.</span></span> <span data-ttu-id="303c4-113">コントロール メッセージを使用すると、実行中のオーケストレーションが直ちに終了するため、ゾンビ インスタンスが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="303c4-113">Since the control message immediately halts the running orchestration, zombie instances are not unexpected.</span></span> <span data-ttu-id="303c4-114">このメカニズムは、ヒューマン ワークフロー関連の設計で頻繁に使用される傾向があります。また、その他の設計でも使用される場合があります。</span><span class="sxs-lookup"><span data-stu-id="303c4-114">A number of Human Workflow related designs tend to use this mechanism as well as some other designs.</span></span>  
  
2.  <span data-ttu-id="303c4-115">**並列待機受信**– このシナリオでは、サービス インスタンスが待機の n 個のメッセージの 1 と特定のメッセージを受信したときに何らかの処理を終了します。</span><span class="sxs-lookup"><span data-stu-id="303c4-115">**Parallel listen receives** – In this scenario the service instance waits for 1 of n messages and when it receives certain messages it does some work and terminates.</span></span> <span data-ttu-id="303c4-116">サービス インスタンスの終了時に並列分岐でメッセージが受信された場合、ゾンビが発生します。</span><span class="sxs-lookup"><span data-stu-id="303c4-116">If messages are received on a parallel branch just as the service instance is terminating, zombies are created.</span></span>  
  
3.  <span data-ttu-id="303c4-117">**非決定的なエンドポイントを含むシーケンシャルなコンボイ**– このシナリオでは、何らかの種類のシステム設計要件を満たすために、特定の種類のすべてのメッセージを処理するマスター オーケストレーション スケジュールが設計されています。</span><span class="sxs-lookup"><span data-stu-id="303c4-117">**Sequential convoys with non-deterministic endpoints** – In this scenario, a master orchestration schedule is designed to handle all messages of a certain type in order to meet some type of system design requirement.</span></span> <span data-ttu-id="303c4-118">こうした設計要件の例として、順次配送、リソース ディスペンサー、バッチ処理などがあります。</span><span class="sxs-lookup"><span data-stu-id="303c4-118">These design requirements may include ordered delivery, resource dispenser, and batching.</span></span> <span data-ttu-id="303c4-119">このシナリオでは、傾向が while の定義を受信と、他の while ループをことを示すためにいくつかの変数を設定するか、コンストラクト続けて遅延図形を持つ 1 つの分岐でリッスンを囲むループを停止する必要があります。</span><span class="sxs-lookup"><span data-stu-id="303c4-119">For this scenario, the tendency is to define a while loop surrounding a listen with one branch having a receive and the other having a delay shape followed by some construct which sets some variable to indicate that the while loop should stop.</span></span> <span data-ttu-id="303c4-120">これは非決定的です。なぜなら、メッセージが配信可能な場合でも遅延が発生する可能性があるからです。</span><span class="sxs-lookup"><span data-stu-id="303c4-120">This is non-deterministic since the delay could be triggered, but a message could still be delivered.</span></span> <span data-ttu-id="303c4-121">このような非決定的なエンドポイントでは、ゾンビが発生する可能性が高くなります。</span><span class="sxs-lookup"><span data-stu-id="303c4-121">Non-deterministic endpoints like this are prone to generating zombies.</span></span>  
  
 <span data-ttu-id="303c4-122">ゾンビ サービス インスタンスが中断されると、次のエラー メッセージが生成されます。</span><span class="sxs-lookup"><span data-stu-id="303c4-122">When a zombie service instance is suspended,  the following error message is generated:</span></span>  
  
`0xC0C01B4C The instance completed without consuming all of its messages. The instance and its unconsumed messages have been suspended.`  
  
 <span data-ttu-id="303c4-123">使用することができます、 [BizTalk 終端記号](https://www.microsoft.com/download/details.aspx?id=2846)ゾンビを削除します。</span><span class="sxs-lookup"><span data-stu-id="303c4-123">You can use the [BizTalk Terminator](https://www.microsoft.com/download/details.aspx?id=2846) to help remove zombies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="303c4-124">参照</span><span class="sxs-lookup"><span data-stu-id="303c4-124">See Also</span></span>  
 <span data-ttu-id="303c4-125">**中断されたサービス インスタンスを削除する**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="303c4-125">**Removing Suspended Service Instances** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>