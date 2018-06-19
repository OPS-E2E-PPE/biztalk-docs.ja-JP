---
title: MSMQ アダプターでメッセージの配信を順序付け |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, ordered delivery
- MSMQ adapters, ordered delivery
ms.assetid: e8dafc76-e894-4120-9cea-d014d635850e
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ac842fcd1e9b386fa885844f3a797504ed7c4c3d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22263586"
---
# <a name="ordered-delivery-of-messages-with-the-msmq-adapter"></a><span data-ttu-id="0d409-102">MSMQ アダプターでメッセージの配信を順序付け</span><span class="sxs-lookup"><span data-stu-id="0d409-102">Ordered Delivery of Messages with the MSMQ Adapter</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="0d409-103">提供、**順次配送**オプション静的送信ポート。</span><span class="sxs-lookup"><span data-stu-id="0d409-103"> provides an **Ordered Delivery** option for static send ports.</span></span> <span data-ttu-id="0d409-104">設定、**順次配送**オプションで、送信ポートを**True** BizTalk Server がメッセージ ボックス データベースにパブリッシュされる順序と同じ順序で送信ポートにメッセージを配信することを確認します。</span><span class="sxs-lookup"><span data-stu-id="0d409-104">Setting the **Ordered Delivery** option on a send port to **True** ensures that BizTalk Server delivers messages to the send port in the same order that they are published to the MessageBox database.</span></span> <span data-ttu-id="0d409-105">エンド ツー エンドの順次配送を実現するには、次の条件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="0d409-105">To provide end-to-end ordered delivery the following conditions must be met:</span></span>  
  
-   <span data-ttu-id="0d409-106">メッセージは、BizTalk Server に送信するメッセージの順序を保持できるアダプターで受信されなければなりません。</span><span class="sxs-lookup"><span data-stu-id="0d409-106">Messages must be received with an adapter that preserves the order of the messages when submitting them to BizTalk Server.</span></span>  
  
-   <span data-ttu-id="0d409-107">持つ送信ポートでこれらのメッセージをサブスクライブする必要があります、**順次配送**オプションを**True**です。</span><span class="sxs-lookup"><span data-stu-id="0d409-107">You must subscribe to these messages with a send port that has the **Ordered Delivery** option to **True**.</span></span>  
  
-   <span data-ttu-id="0d409-108">シーケンシャルなコンボイを使用するオーケストレーションを構成する必要があります、オーケストレーションがメッセージをオーケストレーションのインスタンスが 1 つだけを使用する必要がありますプロセスに使用されている場合、**順次配送**のプロパティ、オーケストレーションの受信ポートに設定する必要があります**True**です。</span><span class="sxs-lookup"><span data-stu-id="0d409-108">If an orchestration is used to process the messages, only a single instance of the orchestration should be used, the orchestration should be configured to use a sequential convoy, and the **Ordered Delivery** property of the orchestration's receive port should be set to **True**.</span></span>  
  
## <a name="using-the-msmq-adapter-for-ordered-delivery-of-messages"></a><span data-ttu-id="0d409-109">メッセージの順次配送を目的とした MSMQ アダプタの使用</span><span class="sxs-lookup"><span data-stu-id="0d409-109">Using the MSMQ Adapter for Ordered Delivery of Messages</span></span>  
 <span data-ttu-id="0d409-110">MSMQ 受信アダプタでは、BizTalk Server に送信するメッセージの順序を保持する機能がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="0d409-110">The MSMQ receive adapter provides support for preserving the order of messages when submitting them to BizTalk Server.</span></span> <span data-ttu-id="0d409-111">エンド ツー エンドのメッセージが構成されている送信ポートによって処理される場合、MSMQ アダプターでメッセージを受信すると、BizTalk Server を経由してメッセージの配信を実現できますが順序付け、**順次配送**にセットのオプション**True**です。</span><span class="sxs-lookup"><span data-stu-id="0d409-111">End-to-end ordered delivery of messages through BizTalk Server can be achieved when receiving messages with the MSMQ adapter if the messages are processed by a send port that is configured with the **Ordered Delivery** option set to **True**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d409-112">参照</span><span class="sxs-lookup"><span data-stu-id="0d409-112">See Also</span></span>  
 <span data-ttu-id="0d409-113">[メッセージの配信を順序付け](../core/ordered-delivery-of-messages.md) </span><span class="sxs-lookup"><span data-stu-id="0d409-113">[Ordered Delivery of Messages](../core/ordered-delivery-of-messages.md) </span></span>  
 [<span data-ttu-id="0d409-114">MSMQ 受信場所を構成する方法</span><span class="sxs-lookup"><span data-stu-id="0d409-114">How to Configure an MSMQ Receive Location</span></span>](../core/how-to-configure-an-msmq-receive-location.md)