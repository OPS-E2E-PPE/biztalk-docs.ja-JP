---
title: MQSeries アダプターを使用したメッセージの配信を順序付けられた |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, ordered delivery
- MQSeries adapters, ordered delivery
ms.assetid: 517ff2a4-7315-43b5-8d4b-7494adf141e4
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8442d5f23f7259d9f13f7f60034d0ca871537e50
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65262630"
---
# <a name="ordered-delivery-of-messages-with-the-mqseries-adapter"></a><span data-ttu-id="ae18e-102">MQSeries アダプターを使用したメッセージの配信を順序付け</span><span class="sxs-lookup"><span data-stu-id="ae18e-102">Ordered Delivery of Messages with the MQSeries Adapter</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="ae18e-103">提供、**順次配送**オプションの静的送信ポート。</span><span class="sxs-lookup"><span data-stu-id="ae18e-103">provides an **Ordered Delivery** option for static send ports.</span></span> <span data-ttu-id="ae18e-104">設定、**順次配送**オプションへの送信ポートで**True**により、BizTalk Server が BizTalk メッセージ ボックス データベースに公開されることと同じ順序で送信ポートにメッセージを配信します。</span><span class="sxs-lookup"><span data-stu-id="ae18e-104">Setting the **Ordered Delivery** option on a send port to **True** ensures that BizTalk Server delivers messages to the send port in the same order that they are published to the BizTalk MessageBox database.</span></span> <span data-ttu-id="ae18e-105">エンド ツー エンドの順次配送を実現するには、次の条件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="ae18e-105">To provide end-to-end ordered delivery the following conditions must be met:</span></span>  
  
-   <span data-ttu-id="ae18e-106">メッセージは、BizTalk Server に送信するメッセージの順序を保持できるアダプターで受信されなければなりません。</span><span class="sxs-lookup"><span data-stu-id="ae18e-106">Messages must be received with an adapter that preserves the order of the messages when submitting them to BizTalk Server.</span></span> <span data-ttu-id="ae18e-107">など MQSeries 受信アダプタでメッセージを受信するときに、受信場所が構成オプションを使用して**停止順序**または**注文 Suspend**します。</span><span class="sxs-lookup"><span data-stu-id="ae18e-107">For example, when receiving messages with the MQSeries receive adapter, the receive location should be configured with the option **Order with Stop** or **Order with Suspend**.</span></span>  
  
-   <span data-ttu-id="ae18e-108">これらのメッセージを持つ送信ポートをサブスクライブする必要があります、**順次配送**オプションを**True**します。</span><span class="sxs-lookup"><span data-stu-id="ae18e-108">You must subscribe to these messages with a send port that has the **Ordered Delivery** option to **True**.</span></span>  
  
-   <span data-ttu-id="ae18e-109">プロセスがメッセージをオーケストレーションのインスタンスが 1 つだけを使用する必要がありますにオーケストレーションを使用する場合、オーケストレーションを構成して、シーケンシャルなコンボイを使用する必要がある、**順次配送**のプロパティ、オーケストレーションの受信ポートに設定する必要があります**True**します。</span><span class="sxs-lookup"><span data-stu-id="ae18e-109">If an orchestration is used to process the messages, only a single instance of the orchestration should be used, the orchestration should be configured to use a sequential convoy, and the **Ordered Delivery** property of the orchestration's receive port should be set to **True**.</span></span>  
  
## <a name="using-the-mqseries-adapter-for-ordered-delivery-of-messages"></a><span data-ttu-id="ae18e-110">メッセージの順次配送の MQSeries アダプタの使用</span><span class="sxs-lookup"><span data-stu-id="ae18e-110">Using the MQSeries Adapter for Ordered Delivery of Messages</span></span>  
 <span data-ttu-id="ae18e-111">MQSeries 受信アダプタは BizTalk Server に送信するメッセージの順序を保持するサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="ae18e-111">The MQSeries receive adapter provides support for preserving the order of messages when submitting them to BizTalk Server.</span></span> <span data-ttu-id="ae18e-112">エンド ツー エンドの順序で構成されている送信ポートでメッセージが処理された場合、MQSeries アダプターでメッセージを受信すると、BizTalk Server を経由してメッセージの配信を実現できる、**順次配送**オプションに設定**True**します。</span><span class="sxs-lookup"><span data-stu-id="ae18e-112">End-to-end ordered delivery of messages through BizTalk Server can be achieved when receiving messages with the MQSeries adapter if the messages are processed by a send port that is configured with the **Ordered Delivery** option set to **True**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae18e-113">参照</span><span class="sxs-lookup"><span data-stu-id="ae18e-113">See Also</span></span>  
 <span data-ttu-id="ae18e-114">[メッセージの配信を順序付け](../core/ordered-delivery-of-messages.md) </span><span class="sxs-lookup"><span data-stu-id="ae18e-114">[Ordered Delivery of Messages](../core/ordered-delivery-of-messages.md) </span></span>  
 [<span data-ttu-id="ae18e-115">アダプター受信場所と送信ポートを MQSeries を構成する方法</span><span class="sxs-lookup"><span data-stu-id="ae18e-115">How to Configure MQSeries Adapter Receive Locations and Send Ports</span></span>](../core/how-to-configure-mqseries-adapter-receive-locations-and-send-ports.md)