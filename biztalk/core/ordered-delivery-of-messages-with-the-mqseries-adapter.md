---
title: MQSeries アダプタでメッセージの配信を順序付け |Microsoft ドキュメント
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
ms.openlocfilehash: 8f8b602adf93152f6af1e5dbbc576180d570a4ef
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22264530"
---
# <a name="ordered-delivery-of-messages-with-the-mqseries-adapter"></a><span data-ttu-id="ccb45-102">MQSeries アダプタを使用したメッセージの順次配送</span><span class="sxs-lookup"><span data-stu-id="ccb45-102">Ordered Delivery of Messages with the MQSeries Adapter</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="ccb45-103">提供、**順次配送**オプション静的送信ポート。</span><span class="sxs-lookup"><span data-stu-id="ccb45-103"> provides an **Ordered Delivery** option for static send ports.</span></span> <span data-ttu-id="ccb45-104">設定、**順次配送**オプションで、送信ポートを**True** BizTalk Server が BizTalk メッセージ ボックス データベースにパブリッシュされる順序と同じ順序で送信ポートにメッセージを配信することを確認します。</span><span class="sxs-lookup"><span data-stu-id="ccb45-104">Setting the **Ordered Delivery** option on a send port to **True** ensures that BizTalk Server delivers messages to the send port in the same order that they are published to the BizTalk MessageBox database.</span></span> <span data-ttu-id="ccb45-105">エンド ツー エンドの順次配送を実現するには、次の条件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="ccb45-105">To provide end-to-end ordered delivery the following conditions must be met:</span></span>  
  
-   <span data-ttu-id="ccb45-106">メッセージは、BizTalk Server に送信するメッセージの順序を保持できるアダプターで受信されなければなりません。</span><span class="sxs-lookup"><span data-stu-id="ccb45-106">Messages must be received with an adapter that preserves the order of the messages when submitting them to BizTalk Server.</span></span> <span data-ttu-id="ccb45-107">たとえば、MQSeries 受信アダプタでメッセージを受信するときに、受信場所を構成オプション**が停止すると注文**または**中断の順序**です。</span><span class="sxs-lookup"><span data-stu-id="ccb45-107">For example, when receiving messages with the MQSeries receive adapter, the receive location should be configured with the option **Order with Stop** or **Order with Suspend**.</span></span>  
  
-   <span data-ttu-id="ccb45-108">持つ送信ポートでこれらのメッセージをサブスクライブする必要があります、**順次配送**オプションを**True**です。</span><span class="sxs-lookup"><span data-stu-id="ccb45-108">You must subscribe to these messages with a send port that has the **Ordered Delivery** option to **True**.</span></span>  
  
-   <span data-ttu-id="ccb45-109">シーケンシャルなコンボイを使用するオーケストレーションを構成する必要があります、オーケストレーションがメッセージをオーケストレーションのインスタンスが 1 つだけを使用する必要がありますプロセスに使用されている場合、**順次配送**のプロパティ、オーケストレーションの受信ポートに設定する必要があります**True**です。</span><span class="sxs-lookup"><span data-stu-id="ccb45-109">If an orchestration is used to process the messages, only a single instance of the orchestration should be used, the orchestration should be configured to use a sequential convoy, and the **Ordered Delivery** property of the orchestration's receive port should be set to **True**.</span></span>  
  
## <a name="using-the-mqseries-adapter-for-ordered-delivery-of-messages"></a><span data-ttu-id="ccb45-110">メッセージの順次配送を目的とした MQSeries アダプタの使用</span><span class="sxs-lookup"><span data-stu-id="ccb45-110">Using the MQSeries Adapter for Ordered Delivery of Messages</span></span>  
 <span data-ttu-id="ccb45-111">MQSeries 受信アダプタでは、BizTalk Server に送信するメッセージの順序を保持する機能がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="ccb45-111">The MQSeries receive adapter provides support for preserving the order of messages when submitting them to BizTalk Server.</span></span> <span data-ttu-id="ccb45-112">エンド ツー エンドのメッセージが構成されている送信ポートによって処理される場合、MQSeries アダプターでメッセージを受信すると、BizTalk Server を経由してメッセージの配信を実現できますが順序付け、**順次配送**オプションに設定**True**です。</span><span class="sxs-lookup"><span data-stu-id="ccb45-112">End-to-end ordered delivery of messages through BizTalk Server can be achieved when receiving messages with the MQSeries adapter if the messages are processed by a send port that is configured with the **Ordered Delivery** option set to **True**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ccb45-113">参照</span><span class="sxs-lookup"><span data-stu-id="ccb45-113">See Also</span></span>  
 <span data-ttu-id="ccb45-114">[メッセージの配信を順序付け](../core/ordered-delivery-of-messages.md) </span><span class="sxs-lookup"><span data-stu-id="ccb45-114">[Ordered Delivery of Messages](../core/ordered-delivery-of-messages.md) </span></span>  
 [<span data-ttu-id="ccb45-115">アダプター受信場所と送信ポートを MQSeries を構成する方法</span><span class="sxs-lookup"><span data-stu-id="ccb45-115">How to Configure MQSeries Adapter Receive Locations and Send Ports</span></span>](../core/how-to-configure-mqseries-adapter-receive-locations-and-send-ports.md)