---
title: "メッセージのライフ サイクル |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, MessageBox database
- messages, orchestrations
- messages, host instances
- messages, receive locations
- send ports, about send ports
- processing, messages
- messages, processing
- host instances, about host instances
- receive locations, about receive locations
- hosts, about hosts
- messages, lifecycle
- MessageBox database, about MessageBox database
- receive ports, about receive ports
- send port groups, about send port groups
- messages, hosts
- messages, send port groups
- messages, receive ports
- orchestrations, about orchestrations
- messages, send ports
ms.assetid: d2374f86-9b5f-404f-ba7b-9cab69873fa8
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e05aca3ec819fb8615552c5ed57114032d7ea60b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="lifecycle-of-a-message"></a><span data-ttu-id="6997f-102">メッセージのライフサイクル</span><span class="sxs-lookup"><span data-stu-id="6997f-102">Lifecycle of a Message</span></span>
<span data-ttu-id="6997f-103">次の図は、メッセージングという観点から捉えた BizTalk Server アーキテクチャの概要を示しています。</span><span class="sxs-lookup"><span data-stu-id="6997f-103">The following figure provides a high-level overview of the BizTalk Server architecture from a messaging perspective.</span></span>  
  
 <span data-ttu-id="6997f-104">![BizTalk Server メッセージング アーキテクチャ](../core/media/arch-messaging-01.gif "arch_messaging_01")</span><span class="sxs-lookup"><span data-stu-id="6997f-104">![BizTalk Server messaging architecture](../core/media/arch-messaging-01.gif "arch_messaging_01")</span></span>  
  
 <span data-ttu-id="6997f-105">この簡単な図でいえば、メッセージは特定の受信ポートの定義された受信場所を介して受信されます。</span><span class="sxs-lookup"><span data-stu-id="6997f-105">In this simplified view, a message is received through a receive location defined in a given receive port.</span></span> <span data-ttu-id="6997f-106">このメッセージは、受信場所によって処理され、BizTalk Server で永続化およびルーティングを行うメインのメカニズムであるメッセージ ボックス データベースに公開されます。</span><span class="sxs-lookup"><span data-stu-id="6997f-106">This message is processed by the receive location and then published to the MessageBox database, the main persistence and routing mechanism for BizTalk Server.</span></span> <span data-ttu-id="6997f-107">メッセージ ボックスはアクティブなサブスクリプションを評価し、一致するサブスクリプションのあるオーケストレーションおよび送信ポートにメッセージをルーティングします。</span><span class="sxs-lookup"><span data-stu-id="6997f-107">The MessageBox evaluates active subscriptions and routes the message to those orchestrations and send ports with matching subscriptions.</span></span> <span data-ttu-id="6997f-108">メッセージがオーケストレーションによって処理され、メッセージ ボックスを経由して送信ポートにメッセージが公開されて、そこから最終的な送信先に転送される場合もあります。</span><span class="sxs-lookup"><span data-stu-id="6997f-108">Orchestrations may process the message and publish messages through the MessageBox to a send port where it is pushed out to its final destination.</span></span>  
  
 <span data-ttu-id="6997f-109">BizTalk Server メッセージ処理に関連する主要なコンポーネントは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6997f-109">The following are key components involved in BizTalk Server message processing.</span></span>  
  
## <a name="receive-ports-and-receive-locations"></a><span data-ttu-id="6997f-110">受信ポートと受信場所</span><span class="sxs-lookup"><span data-stu-id="6997f-110">Receive Ports and Receive Locations</span></span>  
 <span data-ttu-id="6997f-111">A*受信ポート*は、1 つのコレクションまたは以上の受信場所を BizTalk Server に特定のエントリ ポイントを定義します。</span><span class="sxs-lookup"><span data-stu-id="6997f-111">A *receive port* is a collection of one or more receive locations that define specific entry points into BizTalk Server.</span></span> <span data-ttu-id="6997f-112">A*受信場所*単一のエンドポイント (URL) の構成は、メッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="6997f-112">A *receive location* is the configuration of a single endpoint (URL) to receive messages.</span></span> <span data-ttu-id="6997f-113">受信場所には、受信アダプターと受信パイプラインの両方に関する設定情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="6997f-113">The location contains configuration information for both a receive adapter and a receive pipeline.</span></span> <span data-ttu-id="6997f-114">*アダプター*は、メッセージの受信のトランスポートおよび通信の一部を担当します。</span><span class="sxs-lookup"><span data-stu-id="6997f-114">The *adapter* is responsible for the transport and communications part of receiving a message.</span></span> <span data-ttu-id="6997f-115">たとえば、ファイル アダプターや SOAP アダプターなどがあり、それぞれさまざまな種類のソースからメッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="6997f-115">Examples include the File adapter and SOAP adapter, each of which receives messages from different types of sources.</span></span> <span data-ttu-id="6997f-116">受信パイプラインは、メッセージ ボックスにメッセージを公開する準備を行います。</span><span class="sxs-lookup"><span data-stu-id="6997f-116">The receive pipeline is responsible for preparing the message for publishing into the MessageBox.</span></span> <span data-ttu-id="6997f-117">A*パイプライン*する一連の暗号化/暗号化解除などのメッセージを特定の処理、解析、または検証を提供する各シーケンスで実行されるコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="6997f-117">A *pipeline* is a series of components that are executed in sequence, each providing specific processing to a message such as decryption/encryption, parsing, or validation.</span></span> <span data-ttu-id="6997f-118">パイプラインの詳細については、受信ポート、および受信場所を参照してください[成果物](../core/artifacts.md)です。</span><span class="sxs-lookup"><span data-stu-id="6997f-118">For more information about pipelines, receive ports, and receive locations, see [Artifacts](../core/artifacts.md).</span></span>  
  
## <a name="send-ports-and-send-port-groups"></a><span data-ttu-id="6997f-119">送信ポートと送信ポート グループ</span><span class="sxs-lookup"><span data-stu-id="6997f-119">Send Ports and Send Port Groups</span></span>  
 <span data-ttu-id="6997f-120">A*送信ポート*は、送信パイプラインと送信アダプターの組み合わせです。</span><span class="sxs-lookup"><span data-stu-id="6997f-120">A *send port* is the combination of a send pipeline and a send adapter.</span></span> <span data-ttu-id="6997f-121">送信ポート グループは送信ポートの集まりであり、電子メール配信リストのように機能します。</span><span class="sxs-lookup"><span data-stu-id="6997f-121">A send port group is a collection of send ports and works much like an e-mail distribution list.</span></span> <span data-ttu-id="6997f-122">送信ポート グループに送信されたメッセージは、そのグループ内のすべての送信ポートに送信されます。</span><span class="sxs-lookup"><span data-stu-id="6997f-122">A message sent to a send port group will be sent to all send ports in that group.</span></span> <span data-ttu-id="6997f-123">送信パイプラインを使用して、BizTalk Server から受信したメッセージを、他のサービスに送信する準備を行います。</span><span class="sxs-lookup"><span data-stu-id="6997f-123">The send pipeline is used to prepare a message coming from BizTalk Server for transmission to another service.</span></span> <span data-ttu-id="6997f-124">送信アダプターは、SOAP や FTP のような特定のプロトコルを使用して、実際にメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="6997f-124">The send adapter is responsible for actually sending the message using a specific protocol such as SOAP, or FTP.</span></span> <span data-ttu-id="6997f-125">送信ポートおよび送信ポート グループの詳細については、次を参照してください。[成果物](../core/artifacts.md)です。</span><span class="sxs-lookup"><span data-stu-id="6997f-125">For more information on send ports and send port groups, see [Artifacts](../core/artifacts.md).</span></span>  
  
## <a name="orchestrations"></a><span data-ttu-id="6997f-126">オーケストレーション</span><span class="sxs-lookup"><span data-stu-id="6997f-126">Orchestrations</span></span>  
 <span data-ttu-id="6997f-127">オーケストレーションは、メッセージ ボックスを使用してメッセージをサブスクライブ (受信) および公開 (送信) できます。</span><span class="sxs-lookup"><span data-stu-id="6997f-127">Orchestrations can subscribe to (receive) and publish (send) messages through the MessageBox.</span></span> <span data-ttu-id="6997f-128">また、オーケストレーションは新しいメッセージを構築することもできます。</span><span class="sxs-lookup"><span data-stu-id="6997f-128">In addition, orchestrations can construct new messages.</span></span> <span data-ttu-id="6997f-129">メッセージは、前述のサブスクリプションおよびルーティング機構を使用して受信されます。</span><span class="sxs-lookup"><span data-stu-id="6997f-129">Messages are received using the subscription and routing mechanism already discussed.</span></span> <span data-ttu-id="6997f-130">オーケストレーションに対応するサブスクリプションが到着すると、新しいインスタンスがアクティブ化され、メッセージが配信されます。インスタンス サブスクリプションの場合は、必要に応じてインスタンスが復元されてメッセージが配信されます。</span><span class="sxs-lookup"><span data-stu-id="6997f-130">When subscriptions are filled for orchestrations, a new instance is activated and the message is delivered, or in the case of instance subscriptions, the instance is rehydrated if necessary and the message is then delivered.</span></span> <span data-ttu-id="6997f-131">オーケストレーションから送信されたメッセージに公開されたメッセージ ボックスに同様の適切なプロパティの受信場所で到着したメッセージがルーティングで使用するデータベースに挿入されるとします。</span><span class="sxs-lookup"><span data-stu-id="6997f-131">When messages are sent from an orchestration, they are published to the MessageBox in the same manner as a message arriving at a receive location with the appropriate properties is inserted into the database for use in routing.</span></span> <span data-ttu-id="6997f-132">オーケストレーションの詳細については、次を参照してください。[成果物](../core/artifacts.md)です。</span><span class="sxs-lookup"><span data-stu-id="6997f-132">For more information about orchestrations, see [Artifacts](../core/artifacts.md).</span></span>  
  
## <a name="messagebox-database"></a><span data-ttu-id="6997f-133">メッセージ ボックス データベース</span><span class="sxs-lookup"><span data-stu-id="6997f-133">MessageBox Database</span></span>  
 <span data-ttu-id="6997f-134">BizTalk Server の公開/サブスクライブ エンジンの中心となるのは、メッセージ ボックス データベースです。</span><span class="sxs-lookup"><span data-stu-id="6997f-134">The heart of the publish/subscribe engine in BizTalk Server is the MessageBox database.</span></span> <span data-ttu-id="6997f-135">2 つのコンポーネントのメッセージ ボックス データベースから成る: 1 つまたは複数の Microsoft SQL Server データベースとメッセージ エージェントです。</span><span class="sxs-lookup"><span data-stu-id="6997f-135">The MessageBox is made up of two components: one or more Microsoft SQL Server databases and the Message Agent.</span></span> <span data-ttu-id="6997f-136">SQL Server データベースは、メッセージ、メッセージ プロパティ、サブスクリプション、オーケストレーションの状態、追跡データ、ルーティングのためのホスト キューなどの多くの要素に永続的なストアを提供します。</span><span class="sxs-lookup"><span data-stu-id="6997f-136">The SQL Server database provides the persistence store for many things including messages, message properties, subscriptions, orchestration states, tracking data, and host queues for routing.</span></span> <span data-ttu-id="6997f-137">メッセージ ボックス データベースの詳細については、次を参照してください。 [、メッセージ ボックス データベース](../core/the-messagebox-database.md)です。</span><span class="sxs-lookup"><span data-stu-id="6997f-137">For more information about the MessageBox database, see [The MessageBox Database](../core/the-messagebox-database.md).</span></span>  
  
## <a name="hosts-and-host-instances"></a><span data-ttu-id="6997f-138">ホストとホスト インスタンス</span><span class="sxs-lookup"><span data-stu-id="6997f-138">Hosts and Host Instances</span></span>  
 <span data-ttu-id="6997f-139">A*ホスト*はポートやオーケストレーションなどの BizTalk Server アイテムを実行する Microsoft Windows プロセスの論理表現が送信されます。</span><span class="sxs-lookup"><span data-stu-id="6997f-139">A *host* is a logical representation of a Microsoft Windows process that executes BizTalk Server artifacts such as send ports and orchestrations.</span></span> <span data-ttu-id="6997f-140">A*ホスト インスタンス*特定のサーバー上のホストの物理的な表現です。</span><span class="sxs-lookup"><span data-stu-id="6997f-140">A *host instance* is the physical representation of a host on a specific server.</span></span> <span data-ttu-id="6997f-141">ホストには、インプロセス ホストと分離ホストがあります。インプロセス ホストとは、BizTalk Server が所有、管理していることを意味します。分離ホストとは、BizTalk Server が制御していないプロセスで BizTalk Server コードが実行されることを意味します。</span><span class="sxs-lookup"><span data-stu-id="6997f-141">A host can be either an in-process host, which means it is owned and managed by BizTalk Server, or an isolated host, which means that the BizTalk Server code is running in a process that is not controlled by BizTalk Server.</span></span> <span data-ttu-id="6997f-142">分離ホストの代表的な例として、インターネット インフォメーション サービス (IIS) があります。このサービスでは、HTTP アダプターと SOAP アダプターの受信機能をホストします。</span><span class="sxs-lookup"><span data-stu-id="6997f-142">A good example of an isolated host is Internet Information Services (IIS), which hosts the receive functionality of the HTTP and SOAP adapters.</span></span> <span data-ttu-id="6997f-143">ホストは BizTalk Server グループ全体、すなわち設定、メッセージ ボックス、ポートなどを共有する BizTalk Server の集まりに対して定義されます。</span><span class="sxs-lookup"><span data-stu-id="6997f-143">Hosts are defined for an entire BizTalk Server group; a collection of BizTalk Servers that share configuration, MessageBoxes, ports, and so on.</span></span> <span data-ttu-id="6997f-144">ホストとホスト インスタンスの詳細については、次を参照してください。[エンティティ](../core/entities.md)です。</span><span class="sxs-lookup"><span data-stu-id="6997f-144">For more information about hosts and host instances, see [Entities](../core/entities.md).</span></span>  
  
## <a name="saving-a-message-body"></a><span data-ttu-id="6997f-145">メッセージ本文の保存</span><span class="sxs-lookup"><span data-stu-id="6997f-145">Saving a Message Body</span></span>  
 <span data-ttu-id="6997f-146">メッセージ本文を保存する方法は 3 つあります。</span><span class="sxs-lookup"><span data-stu-id="6997f-146">There are three ways to save a message body.</span></span>  
  
### <a name="from-the-admin-mmc-group-hub-page-queries"></a><span data-ttu-id="6997f-147">管理 MMC の [グループ ハブ] ページのクエリから</span><span class="sxs-lookup"><span data-stu-id="6997f-147">From the Admin MMC group hub page queries</span></span>  
 <span data-ttu-id="6997f-148">この方法は、メッセージ ボックス データベース内のメッセージ専用です。</span><span class="sxs-lookup"><span data-stu-id="6997f-148">This method is for messages in the MessageBox database only.</span></span>  
  
-   <span data-ttu-id="6997f-149">サービス インスタンスを表示します。</span><span class="sxs-lookup"><span data-stu-id="6997f-149">View a Service Instance.</span></span>  
  
-   <span data-ttu-id="6997f-150">開く、**サービス インスタンスの詳細** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="6997f-150">Open the **Service Instance Details** dialog box.</span></span>  
  
-   <span data-ttu-id="6997f-151">クリックして、**メッセージ タブ**をこのインスタンスに関連付けられているメッセージの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="6997f-151">Click the **Messages Tab** to view the list of messages associated with this instance.</span></span>  
  
-   <span data-ttu-id="6997f-152">いずれかのメッセージを右クリックし、をクリックして**保存**です。</span><span class="sxs-lookup"><span data-stu-id="6997f-152">Either right-click the message, and then click **Save**.</span></span>  
  
     <span data-ttu-id="6997f-153">-または-</span><span class="sxs-lookup"><span data-stu-id="6997f-153">-or-</span></span>  
  
-   <span data-ttu-id="6997f-154">メッセージをダブルクリックして開くことで、**メッセージ ビューアー**、 をクリック**保存**です。</span><span class="sxs-lookup"><span data-stu-id="6997f-154">Double-click the message to open it in the **Message Viewer**, and click **Save**.</span></span>  
  
### <a name="from-the-operations-om"></a><span data-ttu-id="6997f-155">操作オブジェクト モデルから</span><span class="sxs-lookup"><span data-stu-id="6997f-155">From the Operations OM</span></span>  
  
-   <span data-ttu-id="6997f-156">使用して**GetInstance**サービス インスタンス オブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="6997f-156">Use **GetInstance** to retrieve a Service Instance object.</span></span>  
  
-   <span data-ttu-id="6997f-157">使用して**Instance.Messages [**サービス インスタンスで現在参照されているすべてのメッセージを列挙します。</span><span class="sxs-lookup"><span data-stu-id="6997f-157">Use **Instance.Messages [ ]** to enumerate all messages which the service instance currently references.</span></span>  
  
-   <span data-ttu-id="6997f-158">メソッドを使用し、メッセージ オブジェクトなど**Message.BodyPart**と**Message.Context**にアクセスし、保存します。</span><span class="sxs-lookup"><span data-stu-id="6997f-158">Use methods on the message object such as **Message.BodyPart [ ]** and **Message.Context [  ]** to access and save it.</span></span>  
  
### <a name="from-the-dta"></a><span data-ttu-id="6997f-159">DTA から</span><span class="sxs-lookup"><span data-stu-id="6997f-159">From the DTA</span></span>  
  
-   <span data-ttu-id="6997f-160">使用して、DTA からメッセージを取得、 **GetTrackedInstance**と**GetTrackedmessage** API 呼び出し。</span><span class="sxs-lookup"><span data-stu-id="6997f-160">Retrieve messages from the DTA using the **GetTrackedInstance** and **GetTrackedmessage** API calls.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6997f-161">参照</span><span class="sxs-lookup"><span data-stu-id="6997f-161">See Also</span></span>  
 [<span data-ttu-id="6997f-162">ランタイム アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="6997f-162">Runtime Architecture</span></span>](../core/runtime-architecture.md)