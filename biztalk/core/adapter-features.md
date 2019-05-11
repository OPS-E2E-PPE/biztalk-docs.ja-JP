---
title: TIBCO Enterprise Message Service アダプターの機能 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ede748ce-3f28-4942-b2bd-e38e5f1b0f54
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d923f439598f9eaa924924b6c7a628caf62d32e9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65361556"
---
# <a name="tibco-ems-adapter-features"></a><span data-ttu-id="70043-102">TIBCO EMS アダプターの機能</span><span class="sxs-lookup"><span data-stu-id="70043-102">TIBCO EMS Adapter Features</span></span>
<span data-ttu-id="70043-103">Microsoft BizTalk Adapter for TIBCO Enterprise Message Service (EMS) を使用すると、キューおよび BizTalk Server と TIBCO SDK を使用して、TIBCO EMS によって管理されているトピックにパブリッシュおよびサブスクライブできます。</span><span class="sxs-lookup"><span data-stu-id="70043-103">Microsoft BizTalk Adapter for TIBCO Enterprise Message Service (EMS) enables you to publish and subscribe to queues and topics managed by TIBCO EMS, using BizTalk Server and the TIBCO SDK.</span></span> <span data-ttu-id="70043-104">アダプターは、TIBCO EMS メッセージを高速かつ信頼性の高い方法で統合します。</span><span class="sxs-lookup"><span data-stu-id="70043-104">The adapter integrates TIBCO EMS messages in a fast, easy, and reliable way.</span></span> <span data-ttu-id="70043-105">TIBCO EMS サーバーと Microsoft 間の XML データ形式を交換[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]緊密に統合され信頼性の高いアプリケーション インフラストラクチャを提供します。</span><span class="sxs-lookup"><span data-stu-id="70043-105">It exchanges XML data formats between TIBCO EMS servers and Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to provide a tightly integrated and reliable application infrastructure.</span></span> <span data-ttu-id="70043-106">送信と受信アダプター統合操作の XML スキーマを使用してエンド ツー エンドのビジネス プロセス管理を提供します。</span><span class="sxs-lookup"><span data-stu-id="70043-106">It provides transmit and receive adapter integration operations providing end-to-end business-process management using XML schemas.</span></span>  
  
## <a name="data-validation"></a><span data-ttu-id="70043-107">データの検証</span><span class="sxs-lookup"><span data-stu-id="70043-107">Data Validation</span></span>  
 <span data-ttu-id="70043-108">BizTalk Adapter for TIBCO EMS でインプロセスで動作として、ネイティブでは、BizTalk Server ホストでは密接にアダプターを統合し、構成時にポートの構成を検証します。</span><span class="sxs-lookup"><span data-stu-id="70043-108">BizTalk Adapter for TIBCO EMS runs in-process with the BizTalk Server host as a native, tightly integrated adapter and validates port configuration at the time of configuration.</span></span> <span data-ttu-id="70043-109">データ可能な限り - たとえば、有効な名前、有効な番号、有効範囲を検証します。</span><span class="sxs-lookup"><span data-stu-id="70043-109">It validates the data as much as possible--for example, valid name, valid number, valid in range.</span></span> <span data-ttu-id="70043-110">接続を作成するのには行いません。</span><span class="sxs-lookup"><span data-stu-id="70043-110">It does not try to make a connection.</span></span> <span data-ttu-id="70043-111">そのため、ホスト、ポート送信先、ユーザー、およびパスワードは検証されない場合にエラーが記録されます、実行時の呼び出しがあるまで。</span><span class="sxs-lookup"><span data-stu-id="70043-111">Therefore, the host, port destination, user, and password are not validated until there is a run-time call, in which case an error is logged.</span></span>  
  
## <a name="message-delivery"></a><span data-ttu-id="70043-112">メッセージ配信</span><span class="sxs-lookup"><span data-stu-id="70043-112">Message Delivery</span></span>  
 <span data-ttu-id="70043-113">BizTalk Adapter for TIBCO EMS は、メッセージのうちの 1 回限りの配信を保証します。</span><span class="sxs-lookup"><span data-stu-id="70043-113">BizTalk Adapter for TIBCO EMS guarantees one-time-only delivery of messages.</span></span> <span data-ttu-id="70043-114">EMS に到達しないメッセージは、中断時に再試行可能としてマークされます。</span><span class="sxs-lookup"><span data-stu-id="70043-114">Messages that do not reach EMS are marked as retryable when suspended.</span></span> <span data-ttu-id="70043-115">あります、これをいくつかの例外などの実行時に、無効なポートの構成が存在する場合。</span><span class="sxs-lookup"><span data-stu-id="70043-115">There can be some exceptions to this, for example, when an invalid port configuration exists at the time of execution.</span></span>  
  
 <span data-ttu-id="70043-116">アダプターは、テキスト EMS メッセージの種類を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="70043-116">The adapter accepts text EMS message types.</span></span>  <span data-ttu-id="70043-117">アダプターは、EMS への送信メッセージのトランザクションをサポートしているし、トランザクションのサポートはによって制御されます[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="70043-117">The adapter supports transactions for messages going to EMS, and the transaction support is controlled by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="70043-118">BizTalk Adapter for TIBCO EMS と EMS サーバー間の接続は安全ではありません。</span><span class="sxs-lookup"><span data-stu-id="70043-118">The connection between BizTalk Adapter for TIBCO EMS and the EMS server is not secure.</span></span> <span data-ttu-id="70043-119">指定された TIBCO EMS SDK ではサポートされません。</span><span class="sxs-lookup"><span data-stu-id="70043-119">It is not supported by the provided TIBCO EMS SDK.</span></span>  
  
 <span data-ttu-id="70043-120">アダプターは、すべての標準 JMS プロパティと EMS 拡張機能をサポートします。</span><span class="sxs-lookup"><span data-stu-id="70043-120">The adapter supports all standard JMS properties and EMS extensions.</span></span> <span data-ttu-id="70043-121">これらのプロパティは、オーケストレーションに使用する BizTalk メッセージ コンテキストに格納されます。</span><span class="sxs-lookup"><span data-stu-id="70043-121">These properties are put in the BizTalk message context to be available to an orchestration.</span></span>  
  
## <a name="general-adapter-features"></a><span data-ttu-id="70043-122">[全般] アダプターの機能</span><span class="sxs-lookup"><span data-stu-id="70043-122">General Adapter Features</span></span>  
 <span data-ttu-id="70043-123">BizTalk Adapter for TIBCO EMS は、TIBCO EMS システムと BizTalk Server の間のリアルタイムのビジネス データを交換する手段を提供します。</span><span class="sxs-lookup"><span data-stu-id="70043-123">BizTalk Adapter for TIBCO EMS provides a means to exchange real-time business data between TIBCO EMS systems and BizTalk Server.</span></span> <span data-ttu-id="70043-124">アダプタでは、XML アプリケーションと TIBCO EMS 間の対話できます。</span><span class="sxs-lookup"><span data-stu-id="70043-124">The adapter allows for interaction between an XML application and TIBCO EMS.</span></span> <span data-ttu-id="70043-125">TIBCO EMS で受信および送信の処理のための XML アプリケーションに有効にするとします。</span><span class="sxs-lookup"><span data-stu-id="70043-125">It enables XML applications for inbound and outbound processing with TIBCO EMS.</span></span>  
  
 <span data-ttu-id="70043-126">アダプターは、次のいずれかを使用して TIBCO EMS と通信するために BizTalk Server アプリケーションを有効にする XML メッセージを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="70043-126">The adapter accepts XML messages to enable BizTalk Server applications to communicate with TIBCO EMS using one of the following:</span></span>  
  
-   <span data-ttu-id="70043-127">送信アダプター、静的な一方向の送信ポートを使用して、TIBCO EMS にメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="70043-127">Transmit Adapter, which uses a Static One-Way Send port to send a message to TIBCO EMS.</span></span>  
  
-   <span data-ttu-id="70043-128">受信アダプターは、静的な一方向の受信ポートを使用して、TIBCO EMS からメッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="70043-128">Receive Adapter, which uses a Static One-Way Receive port to receive messages from TIBCO EMS.</span></span>  
  
### <a name="transmit-adapter-architecture-send--static-one-way"></a><span data-ttu-id="70043-129">送信アダプターのアーキテクチャ。送信-静的な一方向</span><span class="sxs-lookup"><span data-stu-id="70043-129">Transmit Adapter Architecture: Send – Static One-Way</span></span>  
 <span data-ttu-id="70043-130">一方向の送信では、キュー/トピックにメッセージを送信する送信ポートが構成されています。</span><span class="sxs-lookup"><span data-stu-id="70043-130">In the one-way send scenario, the send port is configured to send messages to a queue/topic.</span></span> <span data-ttu-id="70043-131">BizTalk Adapter for TIBCO Enterprise Message Service は、指定されたキューまたはトピックに TIBCO EMS サーバーへの要求を転送します。</span><span class="sxs-lookup"><span data-stu-id="70043-131">BizTalk Adapter for TIBCO Enterprise Message Service forwards the request to the TIBCO EMS server on the specified queue/topic.</span></span> <span data-ttu-id="70043-132">アダプターは、TIBCO EMS 通信プロトコルを使用して、TIBCO EMS システムにメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="70043-132">The adapter sends the message to the TIBCO EMS system using TIBCO EMS communication protocol.</span></span> <span data-ttu-id="70043-133">TIBCO EMS システムは、要求を受信し、ビジネス ロジックを実行します。</span><span class="sxs-lookup"><span data-stu-id="70043-133">The TIBCO EMS system receives the requests and executes the business logic.</span></span> <span data-ttu-id="70043-134">TIBCO EMS への呼び出しをするためには、TIBCO EMS サーバーへのアクセスの構成情報をアダプターに提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="70043-134">To make calls into TIBCO EMS, you must provide the adapter with the configuration information to access the TIBCO EMS server.</span></span>  
  
 <span data-ttu-id="70043-135">次の図は、アダプターの一方向の送信操作を示します。</span><span class="sxs-lookup"><span data-stu-id="70043-135">The following image shows the adapter's one-way send operation.</span></span>  
  
 <span data-ttu-id="70043-136">![](../core/media/tibcoems-architecture-send.gif "TIBCOEMS_architecture_send")</span><span class="sxs-lookup"><span data-stu-id="70043-136">![](../core/media/tibcoems-architecture-send.gif "TIBCOEMS_architecture_send")</span></span>  
  
### <a name="receive-adapter-architecture-receive--static-one-way"></a><span data-ttu-id="70043-137">受信アダプターのアーキテクチャ。受信-静的な一方向</span><span class="sxs-lookup"><span data-stu-id="70043-137">Receive Adapter Architecture: Receive – Static One-Way</span></span>  
 <span data-ttu-id="70043-138">一方向の受信シナリオでは、EMS キューまたはトピック メッセージを受信する受信場所を構成します。</span><span class="sxs-lookup"><span data-stu-id="70043-138">In the one-way receive scenario, the receive location is configured to receive messages on an EMS queue/topic.</span></span> <span data-ttu-id="70043-139">BizTalk Adapter for TIBCO EMS は、指定されたキューまたはトピックにメッセージをリッスンし、BizTalk Server に受信したメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="70043-139">BizTalk Adapter for TIBCO EMS listens for messages on a specified queue/topic and submits the received messages to BizTalk Server.</span></span>  
  
 <span data-ttu-id="70043-140">次の図は、このアダプターの一方向の受信操作。</span><span class="sxs-lookup"><span data-stu-id="70043-140">The following image shows the adapter's one-way receive operation.</span></span>  
  
 <span data-ttu-id="70043-141">![](../core/media/tibcoems-architecture-receive.gif "TIBCOEMS_architecture_receive")</span><span class="sxs-lookup"><span data-stu-id="70043-141">![](../core/media/tibcoems-architecture-receive.gif "TIBCOEMS_architecture_receive")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70043-142">参照</span><span class="sxs-lookup"><span data-stu-id="70043-142">See Also</span></span>  
 <span data-ttu-id="70043-143">[アプリケーションの開発](../core/developing-applications5.md) </span><span class="sxs-lookup"><span data-stu-id="70043-143">[Developing Applications](../core/developing-applications5.md) </span></span>  
 [<span data-ttu-id="70043-144">作業の開始</span><span class="sxs-lookup"><span data-stu-id="70043-144">Getting Started</span></span>](../core/getting-started-with-biztalk-adapter-for-tibco-enterprise-message-service.md)