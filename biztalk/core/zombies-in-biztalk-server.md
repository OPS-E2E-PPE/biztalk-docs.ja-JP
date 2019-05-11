---
title: BizTalk Server のゾンビ |Microsoft Docs
description: BizTalk Server のゾンビ メッセージの一般的な原因
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
ms.openlocfilehash: cc41a06c15738c63812ddd9320c7ebbfe9c52d7f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65320809"
---
# <a name="zombies-in-biztalk-server"></a><span data-ttu-id="98bbf-103">BizTalk Server のゾンビ</span><span class="sxs-lookup"><span data-stu-id="98bbf-103">Zombies in BizTalk Server</span></span>

## <a name="what-is-a-zombie"></a><span data-ttu-id="98bbf-104">ゾンビとは何ですか。</span><span class="sxs-lookup"><span data-stu-id="98bbf-104">What is a zombie?</span></span>  
  
-   <span data-ttu-id="98bbf-105">ゾンビ メッセージは、メッセージ ボックス データベースから実行中のオーケストレーションにルーティングされますが、"インフライト"であったメッセージ、オーケストレーションが終了しました。</span><span class="sxs-lookup"><span data-stu-id="98bbf-105">A zombie message is a message that was routed to a running orchestration from the messagebox and was "in flight" when the orchestration ended.</span></span> <span data-ttu-id="98bbf-106">"インフライト"でメッセージは、ですが、サービス インスタンスにルーティングされているし、サービス インスタンス宛てのメッセージ ボックス キューはメッセージです。</span><span class="sxs-lookup"><span data-stu-id="98bbf-106">An "in flight" message is a message that has been routed to a service instance and so is in a messagebox queue destined for the service instance.</span></span> <span data-ttu-id="98bbf-107">メッセージをサブスクライブするオーケストレーション インスタンスが利用できなくできます、ため、メッセージが中断され、"中断 (再開不可)"の ServiceInstance/状態値でマークされました。</span><span class="sxs-lookup"><span data-stu-id="98bbf-107">Since the message can no longer be consumed by the subscribing orchestration instance, the message is suspended and marked with a ServiceInstance/State value of "Suspended (Non-resumable)".</span></span>  
  
-   <span data-ttu-id="98bbf-108">ゾンビ サービス インスタンスは、まだ"インフライト"で、メッセージ ボックスからオーケストレーション インスタンスにルーティングされるメッセージがされたときに終了したオーケストレーションのインスタンスです。</span><span class="sxs-lookup"><span data-stu-id="98bbf-108">A zombie service instance is an instance of an orchestration which has completed while a message that was routed to the orchestration instance from the messagebox was still "in flight".</span></span> <span data-ttu-id="98bbf-109">オーケストレーション インスタンスが終了したため、"インフライト"でメッセージを使用してためが中断され ServiceInstance/状態値が「中断 (再開不可)」とマークされています。</span><span class="sxs-lookup"><span data-stu-id="98bbf-109">Since the orchestration instance has ended, it cannot consume the "in flight" messages and so is suspended and marked with a ServiceInstance/State value of "Suspended (Non-resumable)".</span></span>  
  
## <a name="typical-causes"></a><span data-ttu-id="98bbf-110">一般的な原因</span><span class="sxs-lookup"><span data-stu-id="98bbf-110">Typical causes</span></span>
<span data-ttu-id="98bbf-111">ゾンビの発生は、通常、次のカテゴリのいずれかに分類されます。</span><span class="sxs-lookup"><span data-stu-id="98bbf-111">The occurrence of zombies typically falls into one of the following categories:</span></span>  
  
1. <span data-ttu-id="98bbf-112">**終了コントロール メッセージ**– オーケストレーション エンジンは、特定のオーケストレーション インスタンスで現在実行されているすべての処理を取り消すコントロール メッセージの使用を許可します。</span><span class="sxs-lookup"><span data-stu-id="98bbf-112">**Terminate control messages** – The orchestration engine allows the use of control messages to cancel all currently running work in a specific orchestration instance.</span></span> <span data-ttu-id="98bbf-113">コントロール メッセージでは、実行中のオーケストレーションがすぐに停止し、ためゾンビ インスタンスが予期しません。</span><span class="sxs-lookup"><span data-stu-id="98bbf-113">Since the control message immediately halts the running orchestration, zombie instances are not unexpected.</span></span> <span data-ttu-id="98bbf-114">さまざまなヒューマン ワークフロー関連の設計は、その他の設計と同様にこのメカニズムを使用する傾向があります。</span><span class="sxs-lookup"><span data-stu-id="98bbf-114">A number of Human Workflow related designs tend to use this mechanism as well as some other designs.</span></span>  
  
2. <span data-ttu-id="98bbf-115">**並列待機受信**– n 個のメッセージの 1 のこのシナリオでは、サービス インスタンスが待機して特定のメッセージを受信したときに何らかの処理を終了します。</span><span class="sxs-lookup"><span data-stu-id="98bbf-115">**Parallel listen receives** – In this scenario the service instance waits for 1 of n messages and when it receives certain messages it does some work and terminates.</span></span> <span data-ttu-id="98bbf-116">サービス インスタンスの終了と同様、並列分岐でメッセージを受信すると、ゾンビが作成されます。</span><span class="sxs-lookup"><span data-stu-id="98bbf-116">If messages are received on a parallel branch just as the service instance is terminating, zombies are created.</span></span>  
  
3. <span data-ttu-id="98bbf-117">**非確定的なエンドポイントを持つシーケンシャルなコンボイ**– 何らかの種類のシステム設計要件を満たすために、特定の種類のすべてのメッセージを処理するために、このシナリオではマスター オーケストレーション スケジュールが設計されています。</span><span class="sxs-lookup"><span data-stu-id="98bbf-117">**Sequential convoys with non-deterministic endpoints** – In this scenario, a master orchestration schedule is designed to handle all messages of a certain type in order to meet some type of system design requirement.</span></span> <span data-ttu-id="98bbf-118">これらの設計要件には、順次配送、リソース ディスペンサー、およびバッチ処理を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="98bbf-118">These design requirements may include ordered delivery, resource dispenser, and batching.</span></span> <span data-ttu-id="98bbf-119">このシナリオでは、傾向、しばらくを定義するが、受信、およびその他の後に一部のコンストラクトを while ループをことを示すためにいくつかの変数を設定する遅延図形を持つ 1 つの分岐で、リッスンを囲むループを停止する必要があります。</span><span class="sxs-lookup"><span data-stu-id="98bbf-119">For this scenario, the tendency is to define a while loop surrounding a listen with one branch having a receive and the other having a delay shape followed by some construct which sets some variable to indicate that the while loop should stop.</span></span> <span data-ttu-id="98bbf-120">遅延が発生する可能性が、メッセージが引き続き配信されるため、非決定的です。</span><span class="sxs-lookup"><span data-stu-id="98bbf-120">This is non-deterministic since the delay could be triggered, but a message could still be delivered.</span></span> <span data-ttu-id="98bbf-121">このような非決定論的なエンドポイントは、ゾンビを生成しやすくします。</span><span class="sxs-lookup"><span data-stu-id="98bbf-121">Non-deterministic endpoints like this are prone to generating zombies.</span></span>  
  
   <span data-ttu-id="98bbf-122">ゾンビ サービス インスタンスが中断されると、次のエラー メッセージが生成されます。</span><span class="sxs-lookup"><span data-stu-id="98bbf-122">When a zombie service instance is suspended,  the following error message is generated:</span></span>  
  
`0xC0C01B4C The instance completed without consuming all of its messages. The instance and its unconsumed messages have been suspended.`  
  
 <span data-ttu-id="98bbf-123">使用することができます、 [BizTalk 終端記号](https://www.microsoft.com/download/details.aspx?id=2846)ゾンビを削除します。</span><span class="sxs-lookup"><span data-stu-id="98bbf-123">You can use the [BizTalk Terminator](https://www.microsoft.com/download/details.aspx?id=2846) to help remove zombies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98bbf-124">参照</span><span class="sxs-lookup"><span data-stu-id="98bbf-124">See Also</span></span>  
 <span data-ttu-id="98bbf-125">**中断されたサービス インスタンスを削除します。** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="98bbf-125">**Removing Suspended Service Instances** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>