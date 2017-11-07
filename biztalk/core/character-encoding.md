---
title: "文字エン コード |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0a0c21c8-3318-4533-9734-89302527cb67
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 319ddd649e47e053fe2896d577f28b72602593e3
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2017
---
# <a name="character-encoding"></a><span data-ttu-id="b7153-102">Character Encoding</span><span class="sxs-lookup"><span data-stu-id="b7153-102">Character Encoding</span></span>
<span data-ttu-id="b7153-103">TIBCO Enterprise Message Service (EMS) は、TIBCO EMS 用の BizTalk アダプタで EMS に送信されるメッセージでのさまざまな文字エンコードをサポートします。</span><span class="sxs-lookup"><span data-stu-id="b7153-103">TIBCO Enterprise Message Service (EMS) supports different character encoding in the messages transmitted to EMS by BizTalk Adapter for TIBCO EMS.</span></span> <span data-ttu-id="b7153-104">メッセージは、既定の UTF-8 エンコードを使用してエンコードされます。</span><span class="sxs-lookup"><span data-stu-id="b7153-104">Messages are encoded using the default UTF-8 encoding.</span></span> <span data-ttu-id="b7153-105">メッセージを受信すると、アダプターはメッセージのエンコードを判断し、該当する文字列を UTF-8 に変換した後で [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] にメッセージを渡します。</span><span class="sxs-lookup"><span data-stu-id="b7153-105">When receiving messages, the adapter determines the encoding of the message and converts the appropriate strings to UTF-8 before providing the message to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="b7153-106">すべての文字変換に Microsoft .NET Framework のクラスが使用されます。そのため、アダプタは Microsoft .NET Framework に用意されている文字変換をサポートします。</span><span class="sxs-lookup"><span data-stu-id="b7153-106">All character conversions use the Microsoft .NET Framework classes; therefore the adapter supports the character conversions provided by this same framework.</span></span>  
  
## <a name="running-in-a-clustered-environment"></a><span data-ttu-id="b7153-107">クラスタ環境での実行</span><span class="sxs-lookup"><span data-stu-id="b7153-107">Running in a Clustered Environment</span></span>  
 <span data-ttu-id="b7153-108">キューに公開されたメッセージは、EMS サーバーにあらかじめ定義された順序で、コンシューマーによって処理されます。このとき、クラスター化された [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 環境内で 1 つのアダプターのみがメッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="b7153-108">Messages published to queues are consumed by the consumers in an order pre-determined by the EMS server—only one adapter in the clustered [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment receives the message.</span></span> <span data-ttu-id="b7153-109">キューとして構成することができます*排他*です。</span><span class="sxs-lookup"><span data-stu-id="b7153-109">The queue can be configured as *exclusive*.</span></span> <span data-ttu-id="b7153-110">これは、キューのメッセージ処理に対して最初に登録したアダプタのみが、メッセージを受信することを意味します。</span><span class="sxs-lookup"><span data-stu-id="b7153-110">This means that only the first adapter that registers itself for message consumption on the queue receives the messages.</span></span> <span data-ttu-id="b7153-111">EMS サーバーは、排他的コンシューマがメッセージの受信を確認しない場合にのみ、他のコンシューマにメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="b7153-111">The EMS server only sends messages to the other consumers if the exclusive consumer does not acknowledge message reception.</span></span> <span data-ttu-id="b7153-112">排他的なキューは EMS 構成で構成され、クライアントでは構成できません。</span><span class="sxs-lookup"><span data-stu-id="b7153-112">Exclusive queue configuration is performed in the EMS configuration and is not client configurable.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b7153-113">トピックのサブスクリプションについて: ためのすべてのアダプター、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]グループが同じように構成されている、すべてのメッセージのサブスクライブされたおよびそれぞれのトピック サブスクリプションはメッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="b7153-113">Regarding subscriptions to topics: because all adapters in a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] group are configured identically, they are all subscribed for the message, and each topic subscription receives the message.</span></span>  
  
## <a name="transaction-support"></a><span data-ttu-id="b7153-114">トランザクションのサポート</span><span class="sxs-lookup"><span data-stu-id="b7153-114">Transaction Support</span></span>  
 <span data-ttu-id="b7153-115">アダプタは、オーケストレーションの送信ポートで必要になったときに、トランザクションに対するサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="b7153-115">The adapter provides support for transactions when required by the orchestration send ports.</span></span> <span data-ttu-id="b7153-116">アダプターがメッセージを待機している間は、EMS サーバーでのトランザクションのサポートは行われません。ただし、メッセージが [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に正常に送信された後は、EMS からのすべてのメッセージの受信がアダプターによって確認されます。</span><span class="sxs-lookup"><span data-stu-id="b7153-116">There is no transaction support with the EMS server when the adapter is listening for messages; however, the adapter acknowledges reception of all messages from EMS after successful message submission to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="b7153-117">EMS は、未確認のメッセージをアダプタに再送します。</span><span class="sxs-lookup"><span data-stu-id="b7153-117">EMS resends unacknowledged messages to the adapter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7153-118">参照</span><span class="sxs-lookup"><span data-stu-id="b7153-118">See Also</span></span>  
 <span data-ttu-id="b7153-119">[BizTalk Adapter for TIBCO EMS のセキュリティ](../core/security-in-biztalk-adapter-for-tibco-ems.md) </span><span class="sxs-lookup"><span data-stu-id="b7153-119">[Security in BizTalk Adapter for TIBCO EMS](../core/security-in-biztalk-adapter-for-tibco-ems.md) </span></span>  
 [<span data-ttu-id="b7153-120">作業の開始</span><span class="sxs-lookup"><span data-stu-id="b7153-120">Getting Started</span></span>](../core/getting-started-with-biztalk-adapter-for-tibco-enterprise-message-service.md)