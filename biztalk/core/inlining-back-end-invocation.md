---
title: バック エンド呼び出しのインライン化 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MessageBox database, performance
- service solution tutorial, performance
- performance, in-line invocation
- Inline Invocation of Back-End Processes [service solutions], performance
- performance, MessageBox database
ms.assetid: 991d080f-a4cc-4f14-bab3-3b8b74636daf
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dbd4d24cfc1e78a82e2ec3ddd42218390aaee289
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65382162"
---
# <a name="inlining-back-end-invocation"></a><span data-ttu-id="38600-102">バック エンド呼び出しのインライン化</span><span class="sxs-lookup"><span data-stu-id="38600-102">Inlining Back-end Invocation</span></span>
<span data-ttu-id="38600-103">インライン呼び出しバージョンの完全なソリューションの最も高速な処理時間を提供します。</span><span class="sxs-lookup"><span data-stu-id="38600-103">The inline call version, of the full solutions, provides the fastest processing times.</span></span> <span data-ttu-id="38600-104">インライン バージョンでは、要求と応答メッセージを送受信メッセージ ボックス データベース内のバックエンド システムを維持するオーバーヘッドがなくなります。</span><span class="sxs-lookup"><span data-stu-id="38600-104">The inline version eliminates the overhead of persisting the request and response messages to and from the backend systems in the MessageBox database.</span></span> <span data-ttu-id="38600-105">アダプター バージョンでは、メッセージは送信オーケストレーションからメッセージ ボックスに移動します。</span><span class="sxs-lookup"><span data-stu-id="38600-105">In the adapter version, the message goes from the sending orchestration to the MessageBox.</span></span> <span data-ttu-id="38600-106">アダプターを実行しているホストは、メッセージを取得し、もう一度メッセージ ボックスに投稿をバックエンド プロセスにメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="38600-106">The host running the adapter picks up the message, and sends the message to the back-end process by again posting it to the message box.</span></span>  
  
 <span data-ttu-id="38600-107">効率のインライン展開には、オーケストレーションをバックエンド システムのトランスポート プロトコルに直接バインドのコスト。</span><span class="sxs-lookup"><span data-stu-id="38600-107">The efficiency of inlining comes at a cost of binding the orchestration directly to the transport protocols of the back-end systems.</span></span> <span data-ttu-id="38600-108">インライン バージョンではなく論理ポート経由の通信、オーケストレーションは、次の 3 つのカスタム アセンブリを介してバックエンド システムを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="38600-108">In the inline version, rather than communicating through logical ports, the orchestration calls the back-end systems through three custom assemblies.</span></span> <span data-ttu-id="38600-109">バックエンド システムのトランスポートが変更された場合アセンブリを記述し直すし、再コンパイルする必要があります。</span><span class="sxs-lookup"><span data-stu-id="38600-109">If a back-end system transport changes, an assembly must be rewritten and recompiled.</span></span> <span data-ttu-id="38600-110">次の表では、アセンブリとその機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="38600-110">The following table describes the assemblies and their function:</span></span>  
  
|<span data-ttu-id="38600-111">アセンブリ名</span><span class="sxs-lookup"><span data-stu-id="38600-111">Assembly Name</span></span>|<span data-ttu-id="38600-112">バック エンド接続</span><span class="sxs-lookup"><span data-stu-id="38600-112">Back-end Connection</span></span>|  
|-------------------|--------------------------|  
|<span data-ttu-id="38600-113">Microsoft.Samples.BizTalk.WoodgroveBank.PaymentTrackerCall</span><span class="sxs-lookup"><span data-stu-id="38600-113">Microsoft.Samples.BizTalk.WoodgroveBank.PaymentTrackerCall</span></span>|<span data-ttu-id="38600-114">MQSeries を使用して**取得**と**配置**メッセージ関数。</span><span class="sxs-lookup"><span data-stu-id="38600-114">Uses MQSeries **get** and **put** message functions.</span></span>|  
|<span data-ttu-id="38600-115">Microsoft.Samples.BizTalk.WoodgroveBank.PendingTransactionsCall</span><span class="sxs-lookup"><span data-stu-id="38600-115">Microsoft.Samples.BizTalk.WoodgroveBank.PendingTransactionsCall</span></span>|<span data-ttu-id="38600-116">トランザクション システム用の Web サービスを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="38600-116">Invokes the Web service for the transaction system.</span></span>|  
|<span data-ttu-id="38600-117">Microsoft.Samples.BizTalk.WoodgroveBank.SAPCall</span><span class="sxs-lookup"><span data-stu-id="38600-117">Microsoft.Samples.BizTalk.WoodgroveBank.SAPCall</span></span>|<span data-ttu-id="38600-118">SAP をシミュレートする web サービスを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="38600-118">Calls the web services simulating SAP.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="38600-119">参照</span><span class="sxs-lookup"><span data-stu-id="38600-119">See Also</span></span>  
 <span data-ttu-id="38600-120">[サービスの実装の要点指向のソリューション](../core/implementation-highlights-of-the-service-oriented-solution.md) </span><span class="sxs-lookup"><span data-stu-id="38600-120">[Implementation Highlights of the Service Oriented Solution](../core/implementation-highlights-of-the-service-oriented-solution.md) </span></span>  
 <span data-ttu-id="38600-121">[開発、サービス指向ソリューション](../core/developing-a-service-oriented-solution.md) </span><span class="sxs-lookup"><span data-stu-id="38600-121">[Developing a Service Oriented Solution](../core/developing-a-service-oriented-solution.md) </span></span>  
 <span data-ttu-id="38600-122">[指向ソリューションのサービスのパターンの変換](../core/translating-the-patterns-of-the-service-oriented-solution.md) </span><span class="sxs-lookup"><span data-stu-id="38600-122">[Translating the Patterns of the Service Oriented Solution](../core/translating-the-patterns-of-the-service-oriented-solution.md) </span></span>  
 [<span data-ttu-id="38600-123">BAM によるソリューションを指向サービスを監視します。</span><span class="sxs-lookup"><span data-stu-id="38600-123">Monitoring the Service Oriented Solution with BAM</span></span>](../core/monitoring-the-service-oriented-solution-with-bam.md)