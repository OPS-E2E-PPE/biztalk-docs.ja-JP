---
title: "TIBCO Rendezvous から BizTalk Server を使用してメッセージを受信する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, receiving
- receiving messages
- memory use
ms.assetid: 4eee9c3a-2966-4d5f-ba49-201bb488458c
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4ac81f269e19526f5466e8c12115d617b8171da3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="using-biztalk-server-from-tibco-rendezvous-to-receive-messages"></a><span data-ttu-id="cbf45-102">TIBCO Rendezvous から BizTalk Server を使用してメッセージを受信する</span><span class="sxs-lookup"><span data-stu-id="cbf45-102">Using BizTalk Server from TIBCO Rendezvous to Receive Messages</span></span>
<span data-ttu-id="cbf45-103">Microsoft BizTalk Adapter for TIBCO Rendezvous は、複数のスレッドのキューからイベントをディスパッチします。</span><span class="sxs-lookup"><span data-stu-id="cbf45-103">Microsoft BizTalk Adapter for TIBCO Rendezvous dispatches events from a queue on multiple threads.</span></span> <span data-ttu-id="cbf45-104">BizTalk Server の受信場所は、1 つの TIBCO Rendezvous イベント キューおよびそのディスパッチャー スレッドのプールと関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="cbf45-104">A BizTalk Server receive location is associated with one TIBCO Rendezvous event queue and its pool of dispatcher threads.</span></span>  
  
## <a name="memory-use-and-errors"></a><span data-ttu-id="cbf45-105">メモリの使用とエラー</span><span class="sxs-lookup"><span data-stu-id="cbf45-105">Memory Use and Errors</span></span>  
 <span data-ttu-id="cbf45-106">イベントの処理中、アダプターは使用されるリソースを監視します。</span><span class="sxs-lookup"><span data-stu-id="cbf45-106">While processing events, the adapter keeps an eye on used resources.</span></span> <span data-ttu-id="cbf45-107">メモリの使用量が上限 Watermark を超えると、アダプターはメモリ使用量が下限 Watermark に達するまでイベントのディスパッチを停止します。</span><span class="sxs-lookup"><span data-stu-id="cbf45-107">If memory use goes above the high-watermark, the adapter stops dispatching events until it reaches the low-watermark memory consumption.</span></span> <span data-ttu-id="cbf45-108">これにより TIBCO Rendezvous メッセージが未証明メッセージとして失われる場合があることに注意してください (TIBCO RV コンシューマーは 60 秒経過したらメッセージをキューから削除します)。</span><span class="sxs-lookup"><span data-stu-id="cbf45-108">Note that this might result in TIBCO Rendezvous messages being missed for non certified messages (a TIBCO RV consumer has 60 seconds to remove messages from a queue).</span></span> <span data-ttu-id="cbf45-109">このデータ損失はエラーとして報告されます。</span><span class="sxs-lookup"><span data-stu-id="cbf45-109">This data loss is reported as an error.</span></span> <span data-ttu-id="cbf45-110">アダプターが TIBCO Rendezvous のシステム通知 NO_MEMORY メッセージを受け取ったら、メッセージは既に失われています。</span><span class="sxs-lookup"><span data-stu-id="cbf45-110">If the adapter receives a TIBCO Rendezvous system advisory NO_MEMORY message, messages have already been lost.</span></span>  
  
 <span data-ttu-id="cbf45-111">BizTalk Adapter for TIBCO Rendezvous は状態を保持しており、状態に応じて異なるタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="cbf45-111">BizTalk Adapter for TIBCO Rendezvous maintains a state, and it executes tasks differently based on that state.</span></span> <span data-ttu-id="cbf45-112">BizTalk メッセージ エンジンがエラーを報告し、アダプターが証明されたリスナーとして構成されている場合、アダプターは TIBCO Rendezvous にエラーを報告してメッセージを再送信できるようにします。</span><span class="sxs-lookup"><span data-stu-id="cbf45-112">If the BizTalk Message Engine reports an error, and the adapter is configured to be a certified listener, it reports the error to TIBCO Rendezvous so that it can resubmit the message.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbf45-113">参照</span><span class="sxs-lookup"><span data-stu-id="cbf45-113">See Also</span></span>  
 <span data-ttu-id="cbf45-114">[TIBCO Rendezvous の概念](../core/tibco-rendezvous-concepts.md) </span><span class="sxs-lookup"><span data-stu-id="cbf45-114">[TIBCO Rendezvous Concepts](../core/tibco-rendezvous-concepts.md) </span></span>  
 [<span data-ttu-id="cbf45-115">作成元の TIBCO Rendezvous 受信ハンドラー</span><span class="sxs-lookup"><span data-stu-id="cbf45-115">Creating TIBCO Rendezvous Receive Handlers</span></span>](../core/creating-tibco-rendezvous-receive-handlers.md)