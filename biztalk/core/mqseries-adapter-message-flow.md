---
title: MQSeries アダプタのメッセージ フロー |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MQSeries adapters, message flow
ms.assetid: aa5c8523-afd6-4181-9c11-a150857a7790
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5df8549f99d376ea518b160ac1505aaac7feb5fa
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22263546"
---
# <a name="mqseries-adapter-message-flow"></a><span data-ttu-id="bf451-102">MQSeries アダプタのメッセージ フロー</span><span class="sxs-lookup"><span data-stu-id="bf451-102">MQSeries Adapter Message Flow</span></span>
<span data-ttu-id="bf451-103">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] コンピュータから発信されるメッセージは、まず、Windows 上で実行されている MQSeries Server に渡されます。</span><span class="sxs-lookup"><span data-stu-id="bf451-103">A message originating from a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computer is first passed to an MQSeries Server running on Windows.</span></span> <span data-ttu-id="bf451-104">Windows 上で実行されている MQSeries Server は、BizTalk Server が実行されているコンピュータと同じコンピュータでもかまいません。</span><span class="sxs-lookup"><span data-stu-id="bf451-104">MQSeries Server running on Windows can be on the same computer as the one that runs BizTalk Server.</span></span> <span data-ttu-id="bf451-105">メッセージは、MQSeries Server for Windows コンピュータ経由で、UNIX などのオペレーティング システム上の MQSeries Server ホストにルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="bf451-105">The message is routed through the MQSeries Server for Windows computer to an MQSeries Server host on an operating system such as UNIX.</span></span> <span data-ttu-id="bf451-106">その後、アプリケーションは、MQSeries キューからメッセージを取得します。</span><span class="sxs-lookup"><span data-stu-id="bf451-106">An application then retrieves the message from the MQSeries queue.</span></span>  
  
 <span data-ttu-id="bf451-107">アプリケーションから発信されるメッセージは、まず、MQSeries Server 上の MQSeries キューに格納されます。</span><span class="sxs-lookup"><span data-stu-id="bf451-107">A message originating from an application first goes to an MQSeries queue on MQSeries Server.</span></span> <span data-ttu-id="bf451-108">MQSeries Server は、メッセージを MQSeries Server for Windows コンピュータに転送します。</span><span class="sxs-lookup"><span data-stu-id="bf451-108">The MQSeries Server forwards the message to the MQSeries Server for Windows computer.</span></span> <span data-ttu-id="bf451-109">BizTalk Server は、MQSeries Server for Windows コンピュータからメッセージを受信し、そのメッセージを適切なアプリケーションに転送します。</span><span class="sxs-lookup"><span data-stu-id="bf451-109">BizTalk Server receives the message from the MQSeries Server for Windows computer and forwards it to the appropriate application.</span></span>  
  
 <span data-ttu-id="bf451-110">MQSeries アダプタでは、次のメッセージング シナリオをサポートします。</span><span class="sxs-lookup"><span data-stu-id="bf451-110">The MQSeries adapter supports the following messaging scenarios.</span></span>  
  
|<span data-ttu-id="bf451-111">**Scenario**</span><span class="sxs-lookup"><span data-stu-id="bf451-111">**Scenario**</span></span>|<span data-ttu-id="bf451-112">**Description**</span><span class="sxs-lookup"><span data-stu-id="bf451-112">**Description**</span></span>|  
|------------------|---------------------|  
|<span data-ttu-id="bf451-113">Receive</span><span class="sxs-lookup"><span data-stu-id="bf451-113">Receive</span></span>|<span data-ttu-id="bf451-114">アダプタは、MQSeries Server からメッセージを受信します。受信したメッセージは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に渡されます。</span><span class="sxs-lookup"><span data-stu-id="bf451-114">The adapter receives a message from MQSeries Server, which is passed to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>|  
|<span data-ttu-id="bf451-115">送信 (静的な一方向のポート)</span><span class="sxs-lookup"><span data-stu-id="bf451-115">Send (Static One-Way Port)</span></span>|<span data-ttu-id="bf451-116">アダプタは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] から発信されるメッセージをルーティングします。</span><span class="sxs-lookup"><span data-stu-id="bf451-116">The adapter routes a message that originates from [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>|  
|<span data-ttu-id="bf451-117">動的送信</span><span class="sxs-lookup"><span data-stu-id="bf451-117">Dynamic Send</span></span>|<span data-ttu-id="bf451-118">アプリケーションは実行時に送信先アドレス (URI) を選択できます。</span><span class="sxs-lookup"><span data-stu-id="bf451-118">Enables the application to select a destination address (URI) at run time.</span></span>|  
|<span data-ttu-id="bf451-119">動的受信</span><span class="sxs-lookup"><span data-stu-id="bf451-119">Dynamic Receive</span></span>|<span data-ttu-id="bf451-120">により、アプリケーションを設定して、実行時に、発信元アドレス (URI) を選択、 **MQSeries.DynamicReceive**コンテキスト プロパティを**はい**と動的な受信アドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="bf451-120">Enables the application to select a source address (URI) at run time by setting the **MQSeries.DynamicReceive** context property to **Yes** and specifying the dynamic receive address.</span></span>|  
|<span data-ttu-id="bf451-121">Correlation</span><span class="sxs-lookup"><span data-stu-id="bf451-121">Correlation</span></span>|<span data-ttu-id="bf451-122">アダプタからのメッセージは、複数の種類のメッセージを処理できるオーケストレーションの特定のインスタンスに関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="bf451-122">Messages from the adapter are correlated with specific instances of an orchestration that can handle more than one type of message.</span></span><br /><br /> <span data-ttu-id="bf451-123">MQSeries Server は送信請求 - 応答を使用して関連付け識別子を作成できます。または、BizTalk Server が関連付け識別子を作成できます。</span><span class="sxs-lookup"><span data-stu-id="bf451-123">MQSeries Server can create the correlation identifier by using solicit-response, or BizTalk Server can create the correlation identifier.</span></span><br /><br /> <span data-ttu-id="bf451-124">関連付けセットの詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプを参照してください。</span><span class="sxs-lookup"><span data-stu-id="bf451-124">For more information about correlation sets, see [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help.</span></span>|  
  
 <span data-ttu-id="bf451-125">パイプライン、オーケストレーション、コンテンツ ベースのルーティングでのポートおよびアダプタの使用方法の詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプを参照してください。</span><span class="sxs-lookup"><span data-stu-id="bf451-125">For more information about using ports and adapters in pipelines, orchestrations, and content-based routing, see [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help.</span></span> <span data-ttu-id="bf451-126">詳細については、アダプターに関連付け識別子を使用して、次を参照してください。[を相互に関連付けるメッセージを使用して要求/応答](../core/correlating-messages-using-request-reply.md)です。</span><span class="sxs-lookup"><span data-stu-id="bf451-126">For more information about using correlation identifiers in the adapter, see [Correlating Messages Using Request-Reply](../core/correlating-messages-using-request-reply.md).</span></span>  
  
 <span data-ttu-id="bf451-127">アダプターでのフィルタ リングに使用できるヘッダー プロパティについては、次を参照してください。[プロパティに関連する BizTalk Server](../core/properties-related-to-biztalk-server.md)と[MQSeries コンテキスト プロパティ](../core/mqseries-context-properties.md)です。</span><span class="sxs-lookup"><span data-stu-id="bf451-127">For information about the header properties available for filtering in the adapter, see [Properties Related to BizTalk Server](../core/properties-related-to-biztalk-server.md) and [MQSeries Context Properties](../core/mqseries-context-properties.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf451-128">参照</span><span class="sxs-lookup"><span data-stu-id="bf451-128">See Also</span></span>  
 [<span data-ttu-id="bf451-129">MQSeries アダプタの使用</span><span class="sxs-lookup"><span data-stu-id="bf451-129">Using the MQSeries Adapter</span></span>](../core/using-the-mqseries-adapter.md)