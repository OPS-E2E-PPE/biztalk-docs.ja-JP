---
title: "TIBCO Enterprise Message Service アダプタ機能 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ede748ce-3f28-4942-b2bd-e38e5f1b0f54
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ce63950ea9fca42969a7d8574fec76f438ed5f8f
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2017
---
# <a name="tibco-ems-adapter-features"></a><span data-ttu-id="65559-102">TIBCO EMS アダプターの機能</span><span class="sxs-lookup"><span data-stu-id="65559-102">TIBCO EMS Adapter Features</span></span>
<span data-ttu-id="65559-103">Microsoft BizTalk Adapter for TIBCO Enterprise Message Service (EMS) により、BizTalk Server と TIBCO SDK を使用して、TIBCO EMS によって管理されているキューおよびトピックに対して公開とサブスクライブを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="65559-103">Microsoft BizTalk Adapter for TIBCO Enterprise Message Service (EMS) enables you to publish and subscribe to queues and topics managed by TIBCO EMS, using BizTalk Server and the TIBCO SDK.</span></span> <span data-ttu-id="65559-104">このアダプターは、TIBCO EMS メッセージを迅速で簡単に、信頼できる方法で統合します。</span><span class="sxs-lookup"><span data-stu-id="65559-104">The adapter integrates TIBCO EMS messages in a fast, easy, and reliable way.</span></span> <span data-ttu-id="65559-105">TIBCO EMS サービスと Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 間で XML データ形式を交換することで、密接に統合された信頼性の高いアプリケーション インフラストラクチャが構築されます。</span><span class="sxs-lookup"><span data-stu-id="65559-105">It exchanges XML data formats between TIBCO EMS servers and Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to provide a tightly integrated and reliable application infrastructure.</span></span> <span data-ttu-id="65559-106">送信用と受信用のアダプター統合操作により、XML スキーマを使用したエンドツーエンドのビジネス プロセス管理が提供されます。</span><span class="sxs-lookup"><span data-stu-id="65559-106">It provides transmit and receive adapter integration operations providing end-to-end business-process management using XML schemas.</span></span>  
  
## <a name="data-validation"></a><span data-ttu-id="65559-107">データの検証</span><span class="sxs-lookup"><span data-stu-id="65559-107">Data Validation</span></span>  
 <span data-ttu-id="65559-108">BizTalk Adapter for TIBCO EMS は、密接に統合されたネイティブ アダプターとして BizTalk Server ホストとインプロセスで実行され、構成時にポート構成を検証します。</span><span class="sxs-lookup"><span data-stu-id="65559-108">BizTalk Adapter for TIBCO EMS runs in-process with the BizTalk Server host as a native, tightly integrated adapter and validates port configuration at the time of configuration.</span></span> <span data-ttu-id="65559-109">有効な名前、有効な番号、有効な範囲など、最大限のデータが検証されます。</span><span class="sxs-lookup"><span data-stu-id="65559-109">It validates the data as much as possible--for example, valid name, valid number, valid in range.</span></span> <span data-ttu-id="65559-110">接続は試行されません。</span><span class="sxs-lookup"><span data-stu-id="65559-110">It does not try to make a connection.</span></span> <span data-ttu-id="65559-111">そのため、ホスト、ポート送信先、ユーザー、およびパスワードは、実行時に呼び出されるまで検証されず、その時点でエラーが記録されます。</span><span class="sxs-lookup"><span data-stu-id="65559-111">Therefore, the host, port destination, user, and password are not validated until there is a run-time call, in which case an error is logged.</span></span>  
  
## <a name="message-delivery"></a><span data-ttu-id="65559-112">メッセージ配信</span><span class="sxs-lookup"><span data-stu-id="65559-112">Message Delivery</span></span>  
 <span data-ttu-id="65559-113">BizTalk Adapter for TIBCO EMS は、メッセージの 1 回限りの配信を保証します。</span><span class="sxs-lookup"><span data-stu-id="65559-113">BizTalk Adapter for TIBCO EMS guarantees one-time-only delivery of messages.</span></span> <span data-ttu-id="65559-114">EMS に到達しないメッセージは、中断時に再試行可能としてマークされます。</span><span class="sxs-lookup"><span data-stu-id="65559-114">Messages that do not reach EMS are marked as retryable when suspended.</span></span> <span data-ttu-id="65559-115">これには、いくつかの例外があります。たとえば、実行時に無効なポート構成が存在する場合などです。</span><span class="sxs-lookup"><span data-stu-id="65559-115">There can be some exceptions to this, for example, when an invalid port configuration exists at the time of execution.</span></span>  
  
 <span data-ttu-id="65559-116">アダプターは、テキスト EMS メッセージの種類を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="65559-116">The adapter accepts text EMS message types.</span></span>  <span data-ttu-id="65559-117">アダプターは、EMS への送信メッセージのトランザクションをサポートし、トランザクションのサポートはによって制御されます[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="65559-117">The adapter supports transactions for messages going to EMS, and the transaction support is controlled by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="65559-118">BizTalk Adapter for TIBCO EMS と EMS サーバー間の接続は、セキュリティで保護されません。</span><span class="sxs-lookup"><span data-stu-id="65559-118">The connection between BizTalk Adapter for TIBCO EMS and the EMS server is not secure.</span></span> <span data-ttu-id="65559-119">セキュリティは、提供された TIBCO EMS SDK でサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="65559-119">It is not supported by the provided TIBCO EMS SDK.</span></span>  
  
 <span data-ttu-id="65559-120">このアダプターは、すべての標準 JMS プロパティと EMS 拡張機能をサポートします。</span><span class="sxs-lookup"><span data-stu-id="65559-120">The adapter supports all standard JMS properties and EMS extensions.</span></span> <span data-ttu-id="65559-121">これらのプロパティは、オーケストレーションで使用できるように BizTalk メッセージのコンテキストに配置されます。</span><span class="sxs-lookup"><span data-stu-id="65559-121">These properties are put in the BizTalk message context to be available to an orchestration.</span></span>  
  
## <a name="general-adapter-features"></a><span data-ttu-id="65559-122">全般的なアダプターの機能</span><span class="sxs-lookup"><span data-stu-id="65559-122">General Adapter Features</span></span>  
 <span data-ttu-id="65559-123">BizTalk Adapter for TIBCO EMS は、TIBCO EMS システムと BizTalk Server 間で、ビジネス データをリアルタイムで交換する手段を提供します。</span><span class="sxs-lookup"><span data-stu-id="65559-123">BizTalk Adapter for TIBCO EMS provides a means to exchange real-time business data between TIBCO EMS systems and BizTalk Server.</span></span> <span data-ttu-id="65559-124">このアダプターにより、XML アプリケーションと TIBCO EMS 間の対話が可能になります。</span><span class="sxs-lookup"><span data-stu-id="65559-124">The adapter allows for interaction between an XML application and TIBCO EMS.</span></span> <span data-ttu-id="65559-125">TIBCO EMS で、XML アプリケーションの受信および送信の処理を実行できます。</span><span class="sxs-lookup"><span data-stu-id="65559-125">It enables XML applications for inbound and outbound processing with TIBCO EMS.</span></span>  
  
 <span data-ttu-id="65559-126">アダプターは、次のいずれかの方法で、BizTalk Server アプリケーションと TIBCO EMS 間の通信を可能にする XML メッセージを受け入れます。</span><span class="sxs-lookup"><span data-stu-id="65559-126">The adapter accepts XML messages to enable BizTalk Server applications to communicate with TIBCO EMS using one of the following:</span></span>  
  
-   <span data-ttu-id="65559-127">静的な一方向の送信ポートを使用して、TIBCO EMS にメッセージを送信するアダプターを送信します。</span><span class="sxs-lookup"><span data-stu-id="65559-127">Transmit Adapter, which uses a Static One-Way Send port to send a message to TIBCO EMS.</span></span>  
  
-   <span data-ttu-id="65559-128">受信アダプター: 静的な一方向受信ポートを使用して、TIBCO EMS からメッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="65559-128">Receive Adapter, which uses a Static One-Way Receive port to receive messages from TIBCO EMS.</span></span>  
  
### <a name="transmit-adapter-architecture-send--static-one-way"></a><span data-ttu-id="65559-129">送信アダプターのアーキテクチャ: 送信-静的な一方向</span><span class="sxs-lookup"><span data-stu-id="65559-129">Transmit Adapter Architecture: Send – Static One-Way</span></span>  
 <span data-ttu-id="65559-130">一方向送信の場合、メッセージがキューまたはトピックに送信されるように送信ポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="65559-130">In the one-way send scenario, the send port is configured to send messages to a queue/topic.</span></span> <span data-ttu-id="65559-131">BizTalk Adapter for TIBCO Enterprise Message Service は、指定されたキューまたはトピックに、TIBCO EMS サーバーへの要求を転送します。</span><span class="sxs-lookup"><span data-stu-id="65559-131">BizTalk Adapter for TIBCO Enterprise Message Service forwards the request to the TIBCO EMS server on the specified queue/topic.</span></span> <span data-ttu-id="65559-132">TIBCO EMS システムへのメッセージの送信には、TIBCO EMS 通信プロトコルが使用されます。</span><span class="sxs-lookup"><span data-stu-id="65559-132">The adapter sends the message to the TIBCO EMS system using TIBCO EMS communication protocol.</span></span> <span data-ttu-id="65559-133">TIBCO EMS システムは、要求を受信して、ビジネス ロジックを実行します。</span><span class="sxs-lookup"><span data-stu-id="65559-133">The TIBCO EMS system receives the requests and executes the business logic.</span></span> <span data-ttu-id="65559-134">TIBCO EMS への呼び出しを作成するには、TIBCO EMS サーバーにアクセスするための構成情報をアダプターに提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="65559-134">To make calls into TIBCO EMS, you must provide the adapter with the configuration information to access the TIBCO EMS server.</span></span>  
  
 <span data-ttu-id="65559-135">次の図に、このアダプターの一方向送信操作を示します。</span><span class="sxs-lookup"><span data-stu-id="65559-135">The following image shows the adapter's one-way send operation.</span></span>  
  
 ![](../core/media/tibcoems-architecture-send.gif "TIBCOEMS_architecture_send")  
  
### <a name="receive-adapter-architecture-receive--static-one-way"></a><span data-ttu-id="65559-136">静的な一方向: 受信アダプターのアーキテクチャが表示されます。</span><span class="sxs-lookup"><span data-stu-id="65559-136">Receive Adapter Architecture: Receive – Static One-Way</span></span>  
 <span data-ttu-id="65559-137">一方向受信の場合、EMS キューまたはトピックのメッセージを受信するように受信場所を構成します。</span><span class="sxs-lookup"><span data-stu-id="65559-137">In the one-way receive scenario, the receive location is configured to receive messages on an EMS queue/topic.</span></span> <span data-ttu-id="65559-138">BizTalk Adapter for TIBCO EMS は、指定されたキューまたはトピックのメッセージを待ち受け、受信したメッセージを BizTalk Server に送信します。</span><span class="sxs-lookup"><span data-stu-id="65559-138">BizTalk Adapter for TIBCO EMS listens for messages on a specified queue/topic and submits the received messages to BizTalk Server.</span></span>  
  
 <span data-ttu-id="65559-139">次の図に、このアダプターの一方向受信操作を示します。</span><span class="sxs-lookup"><span data-stu-id="65559-139">The following image shows the adapter's one-way receive operation.</span></span>  
  
 ![](../core/media/tibcoems-architecture-receive.gif "TIBCOEMS_architecture_receive")  
  
## <a name="see-also"></a><span data-ttu-id="65559-140">参照</span><span class="sxs-lookup"><span data-stu-id="65559-140">See Also</span></span>  
 <span data-ttu-id="65559-141">[アプリケーションの開発](../core/developing-applications5.md) </span><span class="sxs-lookup"><span data-stu-id="65559-141">[Developing Applications](../core/developing-applications5.md) </span></span>  
 [<span data-ttu-id="65559-142">作業の開始</span><span class="sxs-lookup"><span data-stu-id="65559-142">Getting Started</span></span>](../core/getting-started-with-biztalk-adapter-for-tibco-enterprise-message-service.md)