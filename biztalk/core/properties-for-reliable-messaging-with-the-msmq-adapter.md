---
title: "MSMQ アダプターで信頼できるメッセージング プロパティ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MSMQ adapters, properties
- queues, MSMQ adapters
- MSMQ adapters, dead letters
- queues, failures [MSMQ adapters]
- MSMQ adapters, impersonation
- MSMQ adapters, remote queues
- queues
- reliability, MSMQ adapters
- impersonation, MSMQ adapters
- MSMQ adapters, queue failures
- clustering, MSMQ adapters
- queues, remote
- MSMQ adapters, reliability
- MSMQ adapters, clustering
ms.assetid: 34bfe028-b2aa-4816-a437-3679d19dffb2
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 49aebf12c86ae72d5dcb224d078c62afefcb8f46
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="properties-for-reliable-messaging-with-the-msmq-adapter"></a><span data-ttu-id="bd31d-102">MSMQ アダプターで信頼できるメッセージのプロパティ</span><span class="sxs-lookup"><span data-stu-id="bd31d-102">Properties for Reliable Messaging with the MSMQ Adapter</span></span>
<span data-ttu-id="bd31d-103">MSMQ アダプターを適切に構成することにより、MSMQ アダプターを使用したメッセージの送受信の信頼性を向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="bd31d-103">You can improve the reliability of sending and receiving messages with the MSMQ adapter by the way you configure the MSMQ adapter.</span></span> <span data-ttu-id="bd31d-104">このトピックでは、信頼性の高いメッセージングを実現できる、いくつかの構成プロパティの使用について説明します。</span><span class="sxs-lookup"><span data-stu-id="bd31d-104">This topic discusses using several configuration properties for reliable messaging.</span></span>  
  
## <a name="running-msmq-adapter-handlers-within-a-clustered-biztalk-host"></a><span data-ttu-id="bd31d-105">クラスター化された BizTalk ホストでの MSMQ アダプター ハンドラーの実行</span><span class="sxs-lookup"><span data-stu-id="bd31d-105">Running MSMQ Adapter Handlers Within a Clustered BizTalk Host</span></span>  
 <span data-ttu-id="bd31d-106">高可用性を実現するための方法として、異なる BizTalk サーバーの複数のホスト インスタンスで、アダプター ハンドラーを同時に実行できます。</span><span class="sxs-lookup"><span data-stu-id="bd31d-106">One approach to high availability is to run adapter handlers in multiple host instances on different BizTalk servers simultaneously.</span></span> <span data-ttu-id="bd31d-107">この方法は、MSMQ アダプター ハンドラーには使用しないことをお勧めします。この理由として、MSMQ ではリモートのトランザクションの読み込みがサポートされていないこと、および MSMQ 送信ハンドラーの動作が、ローカルで実行されている MSMQ サービスのインスタンスに常に依存していることが挙げられます。</span><span class="sxs-lookup"><span data-stu-id="bd31d-107">This approach is not recommended for the MSMQ adapter handlers, because MSMQ does not support remote transacted reads and because the MSMQ send handler maintains a dependency on the locally running instance of the MSMQ service.</span></span> <span data-ttu-id="bd31d-108">MSMQ 送信ハンドラーおよび受信ハンドラーの高可用性を実現するには、MSMQ アダプター ハンドラーを BizTalk ホストのクラスター化されたインスタンスで実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="bd31d-108">To provide high availability for the MSMQ send and receive handlers it is recommended that you run the MSMQ adapter handlers in a clustered instance of a BizTalk Host.</span></span> <span data-ttu-id="bd31d-109">詳細については、次を参照してください。[化されたクラスター化されたホストでアダプター ハンドラーの実行に関する考慮事項](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md)です。</span><span class="sxs-lookup"><span data-stu-id="bd31d-109">For more information, see [Considerations for Running Adapter Handlers within a Clustered Host](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md).</span></span>  
  
## <a name="queue-failure-and-the-dead-letter-queue"></a><span data-ttu-id="bd31d-110">キューのエラーと配信不能メッセージ キュー</span><span class="sxs-lookup"><span data-stu-id="bd31d-110">Queue Failure and the Dead Letter Queue</span></span>  
 <span data-ttu-id="bd31d-111">メッセージを正常に送信した後、受信キューが無効化または削除された場合、後続のメッセージにエラーは発生しません。</span><span class="sxs-lookup"><span data-stu-id="bd31d-111">After successfully sending a message, there is no error for subsequent messages if the receiving queue is disabled or deleted.</span></span> <span data-ttu-id="bd31d-112">この状況で、メッセージの損失が発生する場合があります。</span><span class="sxs-lookup"><span data-stu-id="bd31d-112">This situation could cause loss of messages.</span></span>  
  
 <span data-ttu-id="bd31d-113">設定、**使用する配信不能キュー**構成プロパティを**True**メッセージの損失を防ぎます。</span><span class="sxs-lookup"><span data-stu-id="bd31d-113">Setting the **Use Dead Letter Queue** configuration property to **True** prevents you from losing messages.</span></span> <span data-ttu-id="bd31d-114">`True` (既定値) に設定した場合、キューで受信されないメッセージが配信不能メッセージ キューに格納されます。</span><span class="sxs-lookup"><span data-stu-id="bd31d-114">When the property is `True` (the default), messages that the queue does not receive go into the dead letter queue.</span></span>  
  
## <a name="impersonation-and-remote-queues"></a><span data-ttu-id="bd31d-115">権限借用とリモート キュー</span><span class="sxs-lookup"><span data-stu-id="bd31d-115">Impersonation and Remote Queues</span></span>  
 <span data-ttu-id="bd31d-116">設定する必要も、**配信不能キューを使用して**構成プロパティを**True**リモート キューを使用するとします。</span><span class="sxs-lookup"><span data-stu-id="bd31d-116">You also have to set the **Use Dead Letter Queue** configuration property to **True** when you use remote queues.</span></span> <span data-ttu-id="bd31d-117">MSMQ のアダプターによって、リモート キューを使用するアクセス許可がないユーザーの権限が借用された場合、メッセージが失われる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="bd31d-117">If the adapter for MSMQ impersonates a user without permission to use the remote queue, the message could be lost.</span></span>  
  
 <span data-ttu-id="bd31d-118">このプロパティが**True**メッセージは配信不能キューにローカルまたはリモート コンピューターのいずれか、権限を借用したユーザーには、リモート キューを使用するアクセス許可がありません。</span><span class="sxs-lookup"><span data-stu-id="bd31d-118">When the property is **True** and the impersonated user does not have permission to use the remote queue, the message goes to the dead letter queue on either the local or remote computer.</span></span> <span data-ttu-id="bd31d-119">トランザクション送信では、メッセージはローカル コンピューターの配信不能メッセージ キューに格納されます。</span><span class="sxs-lookup"><span data-stu-id="bd31d-119">In a transactional send, the message goes to the dead letter queue on the local computer.</span></span> <span data-ttu-id="bd31d-120">トランザクション以外の送信では、メッセージはリモート コンピューターの配信不能メッセージ キューに格納されます。</span><span class="sxs-lookup"><span data-stu-id="bd31d-120">In a non-transactional send, the message goes to the dead letter queue on the remote computer.</span></span>  
  
## <a name="recoverable-and-use-journal-queue-properties"></a><span data-ttu-id="bd31d-121">"回復可能" プロパティと "ジャーナル キューの使用" プロパティ</span><span class="sxs-lookup"><span data-stu-id="bd31d-121">Recoverable and Use Journal Queue Properties</span></span>  
 <span data-ttu-id="bd31d-122">両方の**回復可能な**と**使用ジャーナル キュー**プロパティが送信されたメッセージのコピーを保存します。</span><span class="sxs-lookup"><span data-stu-id="bd31d-122">Both the **Recoverable** and **Use Journal Queue** properties save copies of sent messages.</span></span> <span data-ttu-id="bd31d-123">これらのプロパティの詳細については、次を参照してください。 [、MSMQ 受信場所を構成する方法](../core/how-to-configure-an-msmq-receive-location.md)と[MSMQ 送信ポートを構成する方法](../core/how-to-configure-an-msmq-send-port.md)です。</span><span class="sxs-lookup"><span data-stu-id="bd31d-123">For more information about these properties, see [How to Configure an MSMQ Receive Location](../core/how-to-configure-an-msmq-receive-location.md) and [How to Configure an MSMQ Send Port](../core/how-to-configure-an-msmq-send-port.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd31d-124">参照</span><span class="sxs-lookup"><span data-stu-id="bd31d-124">See Also</span></span>  
 <span data-ttu-id="bd31d-125">[MSMQ アダプターで信頼できるメッセージング](../core/reliable-messaging-with-the-msmq-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="bd31d-125">[Reliable Messaging with the MSMQ Adapter](../core/reliable-messaging-with-the-msmq-adapter.md) </span></span>  
 [<span data-ttu-id="bd31d-126">クラスター化されたホストでアダプター ハンドラーの実行に関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="bd31d-126">Considerations for Running Adapter Handlers within a Clustered Host</span></span>](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md)