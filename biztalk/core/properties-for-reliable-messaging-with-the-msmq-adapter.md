---
title: MSMQ アダプターを使用した信頼性の高いメッセージング用のプロパティ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 54a33fdd3ced15230d2b0c1417d1f5398678f183
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398493"
---
# <a name="properties-for-reliable-messaging-with-the-msmq-adapter"></a><span data-ttu-id="491e9-102">MSMQ アダプターを使用した信頼性の高いメッセージング用のプロパティ</span><span class="sxs-lookup"><span data-stu-id="491e9-102">Properties for Reliable Messaging with the MSMQ Adapter</span></span>
<span data-ttu-id="491e9-103">MSMQ アダプターを構成する方法での MSMQ アダプターでメッセージを送受信の信頼性を向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="491e9-103">You can improve the reliability of sending and receiving messages with the MSMQ adapter by the way you configure the MSMQ adapter.</span></span> <span data-ttu-id="491e9-104">このトピックでは、いくつかの構成プロパティを信頼性の高いメッセージングの使用について説明します。</span><span class="sxs-lookup"><span data-stu-id="491e9-104">This topic discusses using several configuration properties for reliable messaging.</span></span>  
  
## <a name="running-msmq-adapter-handlers-within-a-clustered-biztalk-host"></a><span data-ttu-id="491e9-105">クラスター化された BizTalk ホストで MSMQ アダプター ハンドラーの実行</span><span class="sxs-lookup"><span data-stu-id="491e9-105">Running MSMQ Adapter Handlers Within a Clustered BizTalk Host</span></span>  
 <span data-ttu-id="491e9-106">高可用性を実現方法の 1 つの異なる BizTalk server で複数のホスト インスタンスでアダプター ハンドラーを同時に実行することです。</span><span class="sxs-lookup"><span data-stu-id="491e9-106">One approach to high availability is to run adapter handlers in multiple host instances on different BizTalk servers simultaneously.</span></span> <span data-ttu-id="491e9-107">MSMQ はリモート トランザクション読み取りをサポートしないと、MSMQ 送信ハンドラーは、MSMQ サービスをローカルで実行中のインスタンスへの依存関係を維持するため、このアプローチは、MSMQ アダプター ハンドラーの推奨されません。</span><span class="sxs-lookup"><span data-stu-id="491e9-107">This approach is not recommended for the MSMQ adapter handlers, because MSMQ does not support remote transacted reads and because the MSMQ send handler maintains a dependency on the locally running instance of the MSMQ service.</span></span> <span data-ttu-id="491e9-108">高可用性は、MSMQ 送信ハンドラーと受信ハンドラーには、BizTalk ホストのクラスター化されたインスタンスで MSMQ アダプター ハンドラーを実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="491e9-108">To provide high availability for the MSMQ send and receive handlers it is recommended that you run the MSMQ adapter handlers in a clustered instance of a BizTalk Host.</span></span> <span data-ttu-id="491e9-109">詳細については、次を参照してください。[されたクラスター化されたホストでアダプター ハンドラーの実行に関する考慮事項](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md)します。</span><span class="sxs-lookup"><span data-stu-id="491e9-109">For more information, see [Considerations for Running Adapter Handlers within a Clustered Host](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md).</span></span>  
  
## <a name="queue-failure-and-the-dead-letter-queue"></a><span data-ttu-id="491e9-110">キューのエラーと配信不能キュー</span><span class="sxs-lookup"><span data-stu-id="491e9-110">Queue Failure and the Dead Letter Queue</span></span>  
 <span data-ttu-id="491e9-111">メッセージを正常に送信するには後、はありませんエラー後続のメッセージの受信キューが無効または削除された場合です。</span><span class="sxs-lookup"><span data-stu-id="491e9-111">After successfully sending a message, there is no error for subsequent messages if the receiving queue is disabled or deleted.</span></span> <span data-ttu-id="491e9-112">このような状況では、メッセージの損失を発生させる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="491e9-112">This situation could cause loss of messages.</span></span>  
  
 <span data-ttu-id="491e9-113">設定、**配信不能キューを使用して**構成プロパティを**True**メッセージの損失を防ぎます。</span><span class="sxs-lookup"><span data-stu-id="491e9-113">Setting the **Use Dead Letter Queue** configuration property to **True** prevents you from losing messages.</span></span> <span data-ttu-id="491e9-114">プロパティが`True`(既定)、キューを受信しないメッセージは配信不能キューに入ります。</span><span class="sxs-lookup"><span data-stu-id="491e9-114">When the property is `True` (the default), messages that the queue does not receive go into the dead letter queue.</span></span>  
  
## <a name="impersonation-and-remote-queues"></a><span data-ttu-id="491e9-115">権限借用とリモート キュー</span><span class="sxs-lookup"><span data-stu-id="491e9-115">Impersonation and Remote Queues</span></span>  
 <span data-ttu-id="491e9-116">設定する必要も、**を使用して、配信不能キュー**構成プロパティを**True**リモート キューを使用するとします。</span><span class="sxs-lookup"><span data-stu-id="491e9-116">You also have to set the **Use Dead Letter Queue** configuration property to **True** when you use remote queues.</span></span> <span data-ttu-id="491e9-117">MSMQ アダプタでは、リモート キューを使用するアクセス許可がないユーザーを偽装する場合は、メッセージが失われる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="491e9-117">If the adapter for MSMQ impersonates a user without permission to use the remote queue, the message could be lost.</span></span>  
  
 <span data-ttu-id="491e9-118">プロパティが**True**ローカルまたはリモート コンピューターのいずれかで、メッセージが配信不能キューには、権限を借用したユーザーには、リモート キューを使用するアクセス許可はありません。</span><span class="sxs-lookup"><span data-stu-id="491e9-118">When the property is **True** and the impersonated user does not have permission to use the remote queue, the message goes to the dead letter queue on either the local or remote computer.</span></span> <span data-ttu-id="491e9-119">トランザクション送信では、メッセージは、ローカル コンピューターの配信不能キューに移動します。</span><span class="sxs-lookup"><span data-stu-id="491e9-119">In a transactional send, the message goes to the dead letter queue on the local computer.</span></span> <span data-ttu-id="491e9-120">トランザクション以外の送信、メッセージは、リモート コンピューターの配信不能キューに移動します。</span><span class="sxs-lookup"><span data-stu-id="491e9-120">In a non-transactional send, the message goes to the dead letter queue on the remote computer.</span></span>  
  
## <a name="recoverable-and-use-journal-queue-properties"></a><span data-ttu-id="491e9-121">回復可能なジャーナル キューのプロパティを使用して、</span><span class="sxs-lookup"><span data-stu-id="491e9-121">Recoverable and Use Journal Queue Properties</span></span>  
 <span data-ttu-id="491e9-122">両方の**回復可能な**と**ジャーナル キューを使用して**プロパティが送信されたメッセージのコピーを保存します。</span><span class="sxs-lookup"><span data-stu-id="491e9-122">Both the **Recoverable** and **Use Journal Queue** properties save copies of sent messages.</span></span> <span data-ttu-id="491e9-123">これらのプロパティの詳細については、次を参照してください。 [、MSMQ 受信場所を構成する方法](../core/how-to-configure-an-msmq-receive-location.md)と[MSMQ 送信ポートを構成する方法](../core/how-to-configure-an-msmq-send-port.md)します。</span><span class="sxs-lookup"><span data-stu-id="491e9-123">For more information about these properties, see [How to Configure an MSMQ Receive Location](../core/how-to-configure-an-msmq-receive-location.md) and [How to Configure an MSMQ Send Port](../core/how-to-configure-an-msmq-send-port.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="491e9-124">参照</span><span class="sxs-lookup"><span data-stu-id="491e9-124">See Also</span></span>  
 <span data-ttu-id="491e9-125">[MSMQ アダプターを使用した信頼性の高いメッセージング](../core/reliable-messaging-with-the-msmq-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="491e9-125">[Reliable Messaging with the MSMQ Adapter](../core/reliable-messaging-with-the-msmq-adapter.md) </span></span>  
 [<span data-ttu-id="491e9-126">クラスター化されたホストでのアダプター ハンドラーの実行に関する注意点</span><span class="sxs-lookup"><span data-stu-id="491e9-126">Considerations for Running Adapter Handlers within a Clustered Host</span></span>](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md)