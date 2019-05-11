---
title: MSMQ アダプターでメッセージの配信を順序付けられた |Microsoft Docs
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
ms.openlocfilehash: 54395febdadb62584d0a8d6422b9fd05ab3821d6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65322273"
---
# <a name="ordered-delivery-of-messages-with-the-msmq-adapter"></a><span data-ttu-id="3be4e-102">MSMQ アダプターでメッセージの配信を順序付け</span><span class="sxs-lookup"><span data-stu-id="3be4e-102">Ordered Delivery of Messages with the MSMQ Adapter</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="3be4e-103">提供、**順次配送**オプションの静的送信ポート。</span><span class="sxs-lookup"><span data-stu-id="3be4e-103">provides an **Ordered Delivery** option for static send ports.</span></span> <span data-ttu-id="3be4e-104">設定、**順次配送**オプションへの送信ポートで**True**により、BizTalk Server がメッセージ ボックス データベースに公開されることと同じ順序で送信ポートにメッセージを配信します。</span><span class="sxs-lookup"><span data-stu-id="3be4e-104">Setting the **Ordered Delivery** option on a send port to **True** ensures that BizTalk Server delivers messages to the send port in the same order that they are published to the MessageBox database.</span></span> <span data-ttu-id="3be4e-105">エンド ツー エンドの順次配送を実現するには、次の条件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="3be4e-105">To provide end-to-end ordered delivery the following conditions must be met:</span></span>  
  
-   <span data-ttu-id="3be4e-106">メッセージは、BizTalk Server に送信するメッセージの順序を保持できるアダプターで受信されなければなりません。</span><span class="sxs-lookup"><span data-stu-id="3be4e-106">Messages must be received with an adapter that preserves the order of the messages when submitting them to BizTalk Server.</span></span>  
  
-   <span data-ttu-id="3be4e-107">これらのメッセージを持つ送信ポートをサブスクライブする必要があります、**順次配送**オプションを**True**します。</span><span class="sxs-lookup"><span data-stu-id="3be4e-107">You must subscribe to these messages with a send port that has the **Ordered Delivery** option to **True**.</span></span>  
  
-   <span data-ttu-id="3be4e-108">プロセスがメッセージをオーケストレーションのインスタンスが 1 つだけを使用する必要がありますにオーケストレーションを使用する場合、オーケストレーションを構成して、シーケンシャルなコンボイを使用する必要がある、**順次配送**のプロパティ、オーケストレーションの受信ポートに設定する必要があります**True**します。</span><span class="sxs-lookup"><span data-stu-id="3be4e-108">If an orchestration is used to process the messages, only a single instance of the orchestration should be used, the orchestration should be configured to use a sequential convoy, and the **Ordered Delivery** property of the orchestration's receive port should be set to **True**.</span></span>  
  
## <a name="using-the-msmq-adapter-for-ordered-delivery-of-messages"></a><span data-ttu-id="3be4e-109">メッセージの順次配送の MSMQ アダプターを使用</span><span class="sxs-lookup"><span data-stu-id="3be4e-109">Using the MSMQ Adapter for Ordered Delivery of Messages</span></span>  
 <span data-ttu-id="3be4e-110">MSMQ 受信アダプターが BizTalk Server に送信するメッセージの順序を保持する機能のサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="3be4e-110">The MSMQ receive adapter provides support for preserving the order of messages when submitting them to BizTalk Server.</span></span> <span data-ttu-id="3be4e-111">エンド ツー エンドの順序で構成されている送信ポートでメッセージが処理された場合、MSMQ アダプターでメッセージを受信すると、BizTalk Server を経由してメッセージの配信を実現できる、**順次配送**に設定するオプション**True**します。</span><span class="sxs-lookup"><span data-stu-id="3be4e-111">End-to-end ordered delivery of messages through BizTalk Server can be achieved when receiving messages with the MSMQ adapter if the messages are processed by a send port that is configured with the **Ordered Delivery** option set to **True**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3be4e-112">参照</span><span class="sxs-lookup"><span data-stu-id="3be4e-112">See Also</span></span>  
 <span data-ttu-id="3be4e-113">[メッセージの配信を順序付け](../core/ordered-delivery-of-messages.md) </span><span class="sxs-lookup"><span data-stu-id="3be4e-113">[Ordered Delivery of Messages](../core/ordered-delivery-of-messages.md) </span></span>  
 [<span data-ttu-id="3be4e-114">MSMQ 受信場所を構成する方法</span><span class="sxs-lookup"><span data-stu-id="3be4e-114">How to Configure an MSMQ Receive Location</span></span>](../core/how-to-configure-an-msmq-receive-location.md)