---
title: 文字エン コード |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0a0c21c8-3318-4533-9734-89302527cb67
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7418a6e6d1321450e0156fedc38fb5cb69a260e6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357468"
---
# <a name="character-encoding"></a><span data-ttu-id="17185-102">Character Encoding</span><span class="sxs-lookup"><span data-stu-id="17185-102">Character Encoding</span></span>
<span data-ttu-id="17185-103">TIBCO Enterprise Message Service (EMS) は、TIBCO EMS 用に BizTalk アダプタで EMS に送信されるメッセージで別の文字のエンコードをサポートします。</span><span class="sxs-lookup"><span data-stu-id="17185-103">TIBCO Enterprise Message Service (EMS) supports different character encoding in the messages transmitted to EMS by BizTalk Adapter for TIBCO EMS.</span></span> <span data-ttu-id="17185-104">メッセージは、既定の utf-8 エンコーディングを使用してエンコードされます。</span><span class="sxs-lookup"><span data-stu-id="17185-104">Messages are encoded using the default UTF-8 encoding.</span></span> <span data-ttu-id="17185-105">アダプターがメッセージのエンコードを判断し、メッセージを指定する前に、適切な文字列を utf-8 に変換メッセージを受信するときに[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="17185-105">When receiving messages, the adapter determines the encoding of the message and converts the appropriate strings to UTF-8 before providing the message to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="17185-106">すべての文字変換を使用して、Microsoft .NET Framework クラスです。そのため、アダプターでは、この同じフレームワークによって提供される、文字変換をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="17185-106">All character conversions use the Microsoft .NET Framework classes; therefore the adapter supports the character conversions provided by this same framework.</span></span>  
  
## <a name="running-in-a-clustered-environment"></a><span data-ttu-id="17185-107">クラスター化された環境で実行されています。</span><span class="sxs-lookup"><span data-stu-id="17185-107">Running in a Clustered Environment</span></span>  
 <span data-ttu-id="17185-108">キューに公開されたメッセージは、EMS サーバーで事前定義された順序で、コンシューマーによって使用される-で、クラスター化されたアダプターを 1 つだけ[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境は、メッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="17185-108">Messages published to queues are consumed by the consumers in an order pre-determined by the EMS server—only one adapter in the clustered [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment receives the message.</span></span> <span data-ttu-id="17185-109">キューとして構成できる*排他*します。</span><span class="sxs-lookup"><span data-stu-id="17185-109">The queue can be configured as *exclusive*.</span></span> <span data-ttu-id="17185-110">つまり、キューにメッセージの消費量の自分自身を登録する最初のアダプターのみがメッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="17185-110">This means that only the first adapter that registers itself for message consumption on the queue receives the messages.</span></span> <span data-ttu-id="17185-111">EMS サーバーは、排他的コンシューマがメッセージの受信を確認していない場合のみメッセージと他のコンシューマーに送信します。</span><span class="sxs-lookup"><span data-stu-id="17185-111">The EMS server only sends messages to the other consumers if the exclusive consumer does not acknowledge message reception.</span></span> <span data-ttu-id="17185-112">排他的なキューの構成は EMS 構成で実行され、構成可能なクライアントではありません。</span><span class="sxs-lookup"><span data-stu-id="17185-112">Exclusive queue configuration is performed in the EMS configuration and is not client configurable.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="17185-113">トピックのサブスクリプションについて: ためのすべてのアダプターを[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]グループが同じように構成されている、すべてのメッセージのサブスクライブ、およびそれぞれのトピック サブスクリプションはメッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="17185-113">Regarding subscriptions to topics: because all adapters in a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] group are configured identically, they are all subscribed for the message, and each topic subscription receives the message.</span></span>  
  
## <a name="transaction-support"></a><span data-ttu-id="17185-114">トランザクションのサポート</span><span class="sxs-lookup"><span data-stu-id="17185-114">Transaction Support</span></span>  
 <span data-ttu-id="17185-115">アダプターは、オーケストレーションの送信ポートで必要なときに、トランザクションのサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="17185-115">The adapter provides support for transactions when required by the orchestration send ports.</span></span> <span data-ttu-id="17185-116">アダプターがメッセージをリッスンしている場合、トランザクションのサポート、EMS サーバーではありません。ただし、アダプターでに正常に送信された後、EMS からのすべてのメッセージの受信確認される[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="17185-116">There is no transaction support with the EMS server when the adapter is listening for messages; however, the adapter acknowledges reception of all messages from EMS after successful message submission to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="17185-117">EMS では、アダプターに未確認のメッセージを再送信します。</span><span class="sxs-lookup"><span data-stu-id="17185-117">EMS resends unacknowledged messages to the adapter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17185-118">参照</span><span class="sxs-lookup"><span data-stu-id="17185-118">See Also</span></span>  
 <span data-ttu-id="17185-119">[BizTalk Adapter for TIBCO EMS のセキュリティ](../core/security-in-biztalk-adapter-for-tibco-ems.md) </span><span class="sxs-lookup"><span data-stu-id="17185-119">[Security in BizTalk Adapter for TIBCO EMS](../core/security-in-biztalk-adapter-for-tibco-ems.md) </span></span>  
 [<span data-ttu-id="17185-120">作業の開始</span><span class="sxs-lookup"><span data-stu-id="17185-120">Getting Started</span></span>](../core/getting-started-with-biztalk-adapter-for-tibco-enterprise-message-service.md)