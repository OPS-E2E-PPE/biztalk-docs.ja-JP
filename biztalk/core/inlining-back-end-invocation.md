---
title: "バック エンド呼び出しのインライン展開 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MessageBox database, performance
- service solution tutorial, performance
- performance, in-line invocation
- Inline Invocation of Back-End Processes [service solutions], performance
- performance, MessageBox database
ms.assetid: 991d080f-a4cc-4f14-bab3-3b8b74636daf
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a7300429e9f74abc7bc10569c653bdaa0a4c13b1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="inlining-back-end-invocation"></a><span data-ttu-id="6e5d2-102">バック エンド呼び出しのインライン展開</span><span class="sxs-lookup"><span data-stu-id="6e5d2-102">Inlining Back-end Invocation</span></span>
<span data-ttu-id="6e5d2-103">完全ソリューションのインライン呼び出しバージョンでは、処理時間の短縮が可能になります。</span><span class="sxs-lookup"><span data-stu-id="6e5d2-103">The inline call version, of the full solutions, provides the fastest processing times.</span></span> <span data-ttu-id="6e5d2-104">インライン バージョンでは、メッセージ ボックス データベースにおいてバックエンド システムに対する要求および応答メッセージを維持するオーバーヘッドがありません。</span><span class="sxs-lookup"><span data-stu-id="6e5d2-104">The inline version eliminates the overhead of persisting the request and response messages to and from the backend systems in the MessageBox database.</span></span> <span data-ttu-id="6e5d2-105">アダプタ バージョンでは、メッセージは送信オーケストレーションからメッセージ ボックスに送信されます。</span><span class="sxs-lookup"><span data-stu-id="6e5d2-105">In the adapter version, the message goes from the sending orchestration to the MessageBox.</span></span> <span data-ttu-id="6e5d2-106">アダプタを実行するホストがメッセージを受け取ってバックエンド プロセスに送信しますが、このとき、メッセージがメッセージ ボックスに再度送信されます。</span><span class="sxs-lookup"><span data-stu-id="6e5d2-106">The host running the adapter picks up the message, and sends the message to the back-end process by again posting it to the message box.</span></span>  
  
 <span data-ttu-id="6e5d2-107">インライン化の効率性は、オーケストレーションをバックエンド システムのトランスポート プロトコルに直接バインドするコストに反映されます。</span><span class="sxs-lookup"><span data-stu-id="6e5d2-107">The efficiency of inlining comes at a cost of binding the orchestration directly to the transport protocols of the back-end systems.</span></span> <span data-ttu-id="6e5d2-108">インライン バージョンでは、論理ポート経由の通信ではなく、オーケストレーションが 3 つのカスタム アセンブリを介してバックエンド システムを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="6e5d2-108">In the inline version, rather than communicating through logical ports, the orchestration calls the back-end systems through three custom assemblies.</span></span> <span data-ttu-id="6e5d2-109">バックエンド システムのトランスポートが変更された場合、アセンブリを再記述して再コンパイルする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e5d2-109">If a back-end system transport changes, an assembly must be rewritten and recompiled.</span></span> <span data-ttu-id="6e5d2-110">次の表では、アセンブリとその機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="6e5d2-110">The following table describes the assemblies and their function:</span></span>  
  
|<span data-ttu-id="6e5d2-111">アセンブリ名</span><span class="sxs-lookup"><span data-stu-id="6e5d2-111">Assembly Name</span></span>|<span data-ttu-id="6e5d2-112">バックエンド接続</span><span class="sxs-lookup"><span data-stu-id="6e5d2-112">Back-end Connection</span></span>|  
|-------------------|--------------------------|  
|<span data-ttu-id="6e5d2-113">Microsoft.Samples.BizTalk.WoodgroveBank.PaymentTrackerCall</span><span class="sxs-lookup"><span data-stu-id="6e5d2-113">Microsoft.Samples.BizTalk.WoodgroveBank.PaymentTrackerCall</span></span>|<span data-ttu-id="6e5d2-114">MQSeries を使用して**取得**と**put**メッセージ関数。</span><span class="sxs-lookup"><span data-stu-id="6e5d2-114">Uses MQSeries **get** and **put** message functions.</span></span>|  
|<span data-ttu-id="6e5d2-115">Microsoft.Samples.BizTalk.WoodgroveBank.PendingTransactionsCall</span><span class="sxs-lookup"><span data-stu-id="6e5d2-115">Microsoft.Samples.BizTalk.WoodgroveBank.PendingTransactionsCall</span></span>|<span data-ttu-id="6e5d2-116">トランザクション システム用の Web サービスを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="6e5d2-116">Invokes the Web service for the transaction system.</span></span>|  
|<span data-ttu-id="6e5d2-117">Microsoft.Samples.BizTalk.WoodgroveBank.SAPCall</span><span class="sxs-lookup"><span data-stu-id="6e5d2-117">Microsoft.Samples.BizTalk.WoodgroveBank.SAPCall</span></span>|<span data-ttu-id="6e5d2-118">SAP をシミュレートする Web サービスを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="6e5d2-118">Calls the web services simulating SAP.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6e5d2-119">参照</span><span class="sxs-lookup"><span data-stu-id="6e5d2-119">See Also</span></span>  
 <span data-ttu-id="6e5d2-120">[指向ソリューションのサービスの実装の要点](../core/implementation-highlights-of-the-service-oriented-solution.md) </span><span class="sxs-lookup"><span data-stu-id="6e5d2-120">[Implementation Highlights of the Service Oriented Solution](../core/implementation-highlights-of-the-service-oriented-solution.md) </span></span>  
 <span data-ttu-id="6e5d2-121">[指向ソリューションのサービスの開発](../core/developing-a-service-oriented-solution.md) </span><span class="sxs-lookup"><span data-stu-id="6e5d2-121">[Developing a Service Oriented Solution](../core/developing-a-service-oriented-solution.md) </span></span>  
 <span data-ttu-id="6e5d2-122">[指向ソリューションのパターンのサービスの変換](../core/translating-the-patterns-of-the-service-oriented-solution.md) </span><span class="sxs-lookup"><span data-stu-id="6e5d2-122">[Translating the Patterns of the Service Oriented Solution](../core/translating-the-patterns-of-the-service-oriented-solution.md) </span></span>  
 [<span data-ttu-id="6e5d2-123">BAM によるソリューションを指向サービスを監視します。</span><span class="sxs-lookup"><span data-stu-id="6e5d2-123">Monitoring the Service Oriented Solution with BAM</span></span>](../core/monitoring-the-service-oriented-solution-with-bam.md)