---
title: "トランザクション MSMQ アダプターで処理 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MSMQ adapters, transaction handling
- transactions, MSMQ adapters
ms.assetid: 2e5dd0da-3852-48bf-9372-b019ecab23be
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eed4a3b38e4dd328fbbb6099b1bec2c1515b3e5d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="transaction-handling-with-the-msmq-adapter"></a><span data-ttu-id="224eb-102">トランザクション MSMQ アダプターで処理</span><span class="sxs-lookup"><span data-stu-id="224eb-102">Transaction Handling with the MSMQ Adapter</span></span>
<span data-ttu-id="224eb-103">このセクションでは、送受信の際のトランザクションの機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="224eb-103">This section discusses how transactions work in receiving and sending.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="224eb-104">MSMQ アダプターは、リモート キューを使用している場合でも、BizTalk メッセージ ボックス データベースからローカルのメッセージ キューのキューにトランザクションを拡張します。</span><span class="sxs-lookup"><span data-stu-id="224eb-104">For the MSMQ adapter, a transaction extends from the BizTalk MessageBox database to the local Message Queuing queue even if you are using a remote queue.</span></span>  
  
 <span data-ttu-id="224eb-105">MSMQ アダプターを使用した、送信と受信のいずれでも、トランザクションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="224eb-105">You can use transactions on both send and receive with the MSMQ adapter.</span></span> <span data-ttu-id="224eb-106">トランザクションを使用した送信では、アダプターでバッチが完成するまでメッセージが蓄積されます。</span><span class="sxs-lookup"><span data-stu-id="224eb-106">On transacted sends, the adapter accumulates messages until it has a complete batch.</span></span> <span data-ttu-id="224eb-107">その後バッチは、ローカルのメッセージ キュー サービスに単一のトランザクションとして送信されます。</span><span class="sxs-lookup"><span data-stu-id="224eb-107">The adapter then submits the batch to the local Message Queuing service as a single transaction.</span></span> <span data-ttu-id="224eb-108">送信に失敗した場合、バッチは再送信されます。</span><span class="sxs-lookup"><span data-stu-id="224eb-108">If the submission fails, the adapter tries to resubmit the batch.</span></span> <span data-ttu-id="224eb-109">再送信も失敗した場合、セカンダリ トランスポートに移動されます。</span><span class="sxs-lookup"><span data-stu-id="224eb-109">If the resubmission fails, the adapter moves to the secondary transport.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="224eb-110">アダプターはメッセージ キュー 4.0 以降を使用したリモート キューのトランザクション読み込みのみをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="224eb-110">The adapter supports transactional reads of remote queues with Message Queuing 4.0 or later only.</span></span> <span data-ttu-id="224eb-111">このシナリオでは、[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] とリモート メッセージ キュー サーバーの両方でメッセージ キュー 4.0 以降を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="224eb-111">In this scenario both the [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] and the remote Message Queuing server must be running Message Queuing 4.0 or later.</span></span>  
  
 <span data-ttu-id="224eb-112">トランザクションを使用した受信では、アダプターは失敗したメッセージを、失わないように保留します。</span><span class="sxs-lookup"><span data-stu-id="224eb-112">On transacted receives, the adapter suspends failed messages so that it does not lose any one of the messages.</span></span> <span data-ttu-id="224eb-113">受信の間、バッチが完成するまでメッセージがバッチに追加されます。</span><span class="sxs-lookup"><span data-stu-id="224eb-113">During a transacted receive the adapter adds messages to a batch until the batch is complete.</span></span> <span data-ttu-id="224eb-114">その後、バッチが送信されます。</span><span class="sxs-lookup"><span data-stu-id="224eb-114">It then submits the batch:</span></span>  
  
-   <span data-ttu-id="224eb-115">問題が発生せず、サーバーでメッセージを受信した場合、トランザクションはコミットされます。</span><span class="sxs-lookup"><span data-stu-id="224eb-115">If there are no problems and the server receives the messages, the adapter commits the transaction.</span></span>  
  
-   <span data-ttu-id="224eb-116">問題が発生した場合、新しいバッチが現在のトランザクションの一部として作成されます。</span><span class="sxs-lookup"><span data-stu-id="224eb-116">If there are problems, the adapter creates a new batch as part of the current transaction.</span></span> <span data-ttu-id="224eb-117">問題のあるメッセージは新しいバッチに移動されます。</span><span class="sxs-lookup"><span data-stu-id="224eb-117">It then moves any problem messages into the new batch.</span></span> <span data-ttu-id="224eb-118">その後、最初のバッチが再送信され、新しいバッチが保留中のメッセージとして送信されます。</span><span class="sxs-lookup"><span data-stu-id="224eb-118">It then resubmits the first batch and submits the new batch as suspended messages.</span></span> <span data-ttu-id="224eb-119">この再送信で問題が発生しなかった場合、トランザクションはコミットされます。</span><span class="sxs-lookup"><span data-stu-id="224eb-119">The adapter commits the transaction if there are no problems during this resubmission.</span></span>  
  
 <span data-ttu-id="224eb-120">クラスター化された BizTalk ホスト インスタンスで MSMQ アダプターの送信ハンドラーを実行している場合、トランザクションの一貫性を確保するために、MSMQ サービスを同一のクラスター グループにクラスター化してください。</span><span class="sxs-lookup"><span data-stu-id="224eb-120">If you are running an MSMQ adapter send handler in a clustered BizTalk Host instance, you should cluster the MSMQ service in the same cluster group to ensure transactional consistency.</span></span>  
  
 <span data-ttu-id="224eb-121">DCOMCNFG ユーティリティで [ネットワーク DTC アクセス] が無効になっている場合、MSMQ トランザクション リモート受信操作は解読不明のエラー メッセージで失敗します。</span><span class="sxs-lookup"><span data-stu-id="224eb-121">If "Network DTC Access" is disabled in the DCOMCNFG utility, a MSMQ transactional remote receive operation will fail with a cryptic error message.</span></span>  <span data-ttu-id="224eb-122">MSMQ アダプターでトランザクション リモート受信を行うには、[ネットワーク DTC アクセス] を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="224eb-122">To do a transactional remote receive with the MSMQ adapter, "Network DTC Access" must be enabled.</span></span> <span data-ttu-id="224eb-123">詳細についてはあります[http://go.microsoft.com/fwlink/?LinkId=124623](http://go.microsoft.com/fwlink/?LinkId=124623)です。</span><span class="sxs-lookup"><span data-stu-id="224eb-123">More information can be found at [http://go.microsoft.com/fwlink/?LinkId=124623](http://go.microsoft.com/fwlink/?LinkId=124623).</span></span>  
  
 <span data-ttu-id="224eb-124">MSMQ はリモートのトランザクションの読み込みをサポートしていないので、クラスター化された BizTalk ホスト インスタンスで MSMQ アダプターの受信ハンドラーを実行している場合は、ローカルのトランザクションの読み込みをサポートするために、MSMQ サービスを同一のクラスター グループにクラスター化してください。</span><span class="sxs-lookup"><span data-stu-id="224eb-124">If you are running an MSMQ adapter receive handler in a clustered BizTalk Host instance, you should cluster the MSMQ service in the same cluster group to support local transacted reads because MSMQ does not support remote transactional reads.</span></span> <span data-ttu-id="224eb-125">BizTalk ホストのクラスター化されたインスタンスで MSMQ アダプター ハンドラーの実行に関する詳細については、次を参照してください。[クラスター ホストでアダプター ハンドラーの実行に関する考慮事項](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md)です。</span><span class="sxs-lookup"><span data-stu-id="224eb-125">For more information about running MSMQ adapter handlers in a clustered instance of a BizTalk Host, see [Considerations for Running Adapter Handlers within a Clustered Host](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="224eb-126">参照</span><span class="sxs-lookup"><span data-stu-id="224eb-126">See Also</span></span>  
 [<span data-ttu-id="224eb-127">MSMQ アダプターで信頼できるメッセージング</span><span class="sxs-lookup"><span data-stu-id="224eb-127">Reliable Messaging with the MSMQ Adapter</span></span>](../core/reliable-messaging-with-the-msmq-adapter.md)