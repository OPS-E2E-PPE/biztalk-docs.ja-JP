---
title: メッセージのライフ サイクル |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 305dc48db684a1e0f0ba37232b672e6ffb63406a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65329674"
---
# <a name="lifecycle-of-a-message"></a><span data-ttu-id="bedd4-102">メッセージのライフ サイクル</span><span class="sxs-lookup"><span data-stu-id="bedd4-102">Lifecycle of a Message</span></span>
<span data-ttu-id="bedd4-103">次の図では、メッセージングの観点から、BizTalk Server アーキテクチャの概要を示します。</span><span class="sxs-lookup"><span data-stu-id="bedd4-103">The following figure provides a high-level overview of the BizTalk Server architecture from a messaging perspective.</span></span>  
  
 <span data-ttu-id="bedd4-104">![BizTalk Server メッセージング アーキテクチャ](../core/media/arch-messaging-01.gif "arch_messaging_01")</span><span class="sxs-lookup"><span data-stu-id="bedd4-104">![BizTalk Server messaging architecture](../core/media/arch-messaging-01.gif "arch_messaging_01")</span></span>  
  
 <span data-ttu-id="bedd4-105">この簡略化されたビューでメッセージが特定の受信ポートで定義されている受信場所を介して受信されます。</span><span class="sxs-lookup"><span data-stu-id="bedd4-105">In this simplified view, a message is received through a receive location defined in a given receive port.</span></span> <span data-ttu-id="bedd4-106">このメッセージは受信場所で処理され、メッセージ ボックス データベースでは、メインの永続化および BizTalk Server のルーティング メカニズムにパブリッシュします。</span><span class="sxs-lookup"><span data-stu-id="bedd4-106">This message is processed by the receive location and then published to the MessageBox database, the main persistence and routing mechanism for BizTalk Server.</span></span> <span data-ttu-id="bedd4-107">メッセージ ボックスは、アクティブなサブスクリプションの評価しそのオーケストレーションにメッセージをルーティングし、サブスクリプションに一致するポートを送信します。</span><span class="sxs-lookup"><span data-stu-id="bedd4-107">The MessageBox evaluates active subscriptions and routes the message to those orchestrations and send ports with matching subscriptions.</span></span> <span data-ttu-id="bedd4-108">オーケストレーションはメッセージを処理し、プッシュは最終的な送信先に送信ポートにメッセージ ボックスを経由してメッセージを発行する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="bedd4-108">Orchestrations may process the message and publish messages through the MessageBox to a send port where it is pushed out to its final destination.</span></span>  
  
 <span data-ttu-id="bedd4-109">BizTalk Server メッセージの処理に関連する主要なコンポーネントを次に示します。</span><span class="sxs-lookup"><span data-stu-id="bedd4-109">The following are key components involved in BizTalk Server message processing.</span></span>  
  
## <a name="receive-ports-and-receive-locations"></a><span data-ttu-id="bedd4-110">受信ポートと受信場所</span><span class="sxs-lookup"><span data-stu-id="bedd4-110">Receive Ports and Receive Locations</span></span>  
 <span data-ttu-id="bedd4-111">A*受信ポート*いずれかのコレクションまたは以上の受信場所を BizTalk Server への特定のエントリ ポイントを定義します。</span><span class="sxs-lookup"><span data-stu-id="bedd4-111">A *receive port* is a collection of one or more receive locations that define specific entry points into BizTalk Server.</span></span> <span data-ttu-id="bedd4-112">A*受信場所*メッセージを受信する 1 つのエンドポイント (URL) の構成を示します。</span><span class="sxs-lookup"><span data-stu-id="bedd4-112">A *receive location* is the configuration of a single endpoint (URL) to receive messages.</span></span> <span data-ttu-id="bedd4-113">場所には、受信アダプターと受信パイプラインの両方の構成情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="bedd4-113">The location contains configuration information for both a receive adapter and a receive pipeline.</span></span> <span data-ttu-id="bedd4-114">*アダプター*のメッセージの受信トランスポートおよび通信の一部を担当します。</span><span class="sxs-lookup"><span data-stu-id="bedd4-114">The *adapter* is responsible for the transport and communications part of receiving a message.</span></span> <span data-ttu-id="bedd4-115">例には、ファイル アダプターと SOAP アダプタは、さまざまな種類のソースからメッセージを受信する各が含まれます。</span><span class="sxs-lookup"><span data-stu-id="bedd4-115">Examples include the File adapter and SOAP adapter, each of which receives messages from different types of sources.</span></span> <span data-ttu-id="bedd4-116">受信パイプラインは、メッセージをメッセージ ボックス データベースへの発行の準備を行います。</span><span class="sxs-lookup"><span data-stu-id="bedd4-116">The receive pipeline is responsible for preparing the message for publishing into the MessageBox.</span></span> <span data-ttu-id="bedd4-117">A*パイプライン*一連の暗号化/暗号化解除などのメッセージを特定の処理、解析、または検証を提供するそれぞれのシーケンスで実行されるコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="bedd4-117">A *pipeline* is a series of components that are executed in sequence, each providing specific processing to a message such as decryption/encryption, parsing, or validation.</span></span> <span data-ttu-id="bedd4-118">パイプラインの詳細については、受信ポート、および受信場所を参照してください[成果物](../core/artifacts.md)します。</span><span class="sxs-lookup"><span data-stu-id="bedd4-118">For more information about pipelines, receive ports, and receive locations, see [Artifacts](../core/artifacts.md).</span></span>  
  
## <a name="send-ports-and-send-port-groups"></a><span data-ttu-id="bedd4-119">送信ポートと送信ポート グループ</span><span class="sxs-lookup"><span data-stu-id="bedd4-119">Send Ports and Send Port Groups</span></span>  
 <span data-ttu-id="bedd4-120">A*送信ポート*送信パイプラインと送信アダプタの組み合わせです。</span><span class="sxs-lookup"><span data-stu-id="bedd4-120">A *send port* is the combination of a send pipeline and a send adapter.</span></span> <span data-ttu-id="bedd4-121">送信ポート グループを送信ポートのコレクションは、電子メール配布リストと同様に機能します。</span><span class="sxs-lookup"><span data-stu-id="bedd4-121">A send port group is a collection of send ports and works much like an e-mail distribution list.</span></span> <span data-ttu-id="bedd4-122">送信ポート グループに送信されるメッセージは、そのグループ内のすべての送信ポートに送信されます。</span><span class="sxs-lookup"><span data-stu-id="bedd4-122">A message sent to a send port group will be sent to all send ports in that group.</span></span> <span data-ttu-id="bedd4-123">別のサービスに転送の BizTalk Server から受信メッセージを準備するには、送信パイプラインを使用します。</span><span class="sxs-lookup"><span data-stu-id="bedd4-123">The send pipeline is used to prepare a message coming from BizTalk Server for transmission to another service.</span></span> <span data-ttu-id="bedd4-124">送信アダプターは、実際には、SOAP や FTP などの特定のプロトコルを使用してメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="bedd4-124">The send adapter is responsible for actually sending the message using a specific protocol such as SOAP, or FTP.</span></span> <span data-ttu-id="bedd4-125">送信ポートおよび送信ポート グループの詳細については、次を参照してください。[成果物](../core/artifacts.md)します。</span><span class="sxs-lookup"><span data-stu-id="bedd4-125">For more information on send ports and send port groups, see [Artifacts](../core/artifacts.md).</span></span>  
  
## <a name="orchestrations"></a><span data-ttu-id="bedd4-126">オーケストレーション</span><span class="sxs-lookup"><span data-stu-id="bedd4-126">Orchestrations</span></span>  
 <span data-ttu-id="bedd4-127">オーケストレーションのサブスクライブ (受信) することができ、メッセージ ボックス データベースを介して (送信) メッセージを発行します。</span><span class="sxs-lookup"><span data-stu-id="bedd4-127">Orchestrations can subscribe to (receive) and publish (send) messages through the MessageBox.</span></span> <span data-ttu-id="bedd4-128">さらに、オーケストレーションは、新しいメッセージを構築することができます。</span><span class="sxs-lookup"><span data-stu-id="bedd4-128">In addition, orchestrations can construct new messages.</span></span> <span data-ttu-id="bedd4-129">メッセージを受信する、サブスクリプションを使用して、ルーティング機構について説明します。</span><span class="sxs-lookup"><span data-stu-id="bedd4-129">Messages are received using the subscription and routing mechanism already discussed.</span></span> <span data-ttu-id="bedd4-130">オーケストレーションのサブスクリプションがいっぱいになるの新しいインスタンスがアクティブ化し、メッセージを配信すると、必要に応じてインスタンスのサブスクリプションの場合、インスタンスがリハイド レートや、メッセージが配信されます。</span><span class="sxs-lookup"><span data-stu-id="bedd4-130">When subscriptions are filled for orchestrations, a new instance is activated and the message is delivered, or in the case of instance subscriptions, the instance is rehydrated if necessary and the message is then delivered.</span></span> <span data-ttu-id="bedd4-131">オーケストレーションから送信されたメッセージに発行されます、メッセージ ボックスに同様に、適切なプロパティを持つ受信場所に到着するメッセージがルーティングで使用するためのデータベースに挿入されるとします。</span><span class="sxs-lookup"><span data-stu-id="bedd4-131">When messages are sent from an orchestration, they are published to the MessageBox in the same manner as a message arriving at a receive location with the appropriate properties is inserted into the database for use in routing.</span></span> <span data-ttu-id="bedd4-132">オーケストレーションの詳細については、次を参照してください。[成果物](../core/artifacts.md)します。</span><span class="sxs-lookup"><span data-stu-id="bedd4-132">For more information about orchestrations, see [Artifacts](../core/artifacts.md).</span></span>  
  
## <a name="messagebox-database"></a><span data-ttu-id="bedd4-133">メッセージ ボックス データベース</span><span class="sxs-lookup"><span data-stu-id="bedd4-133">MessageBox Database</span></span>  
 <span data-ttu-id="bedd4-134">BizTalk Server での発行/サブスクライブ エンジンの中核は、メッセージ ボックス データベースです。</span><span class="sxs-lookup"><span data-stu-id="bedd4-134">The heart of the publish/subscribe engine in BizTalk Server is the MessageBox database.</span></span> <span data-ttu-id="bedd4-135">2 つのコンポーネントのメッセージ ボックス データベースから成る: 1 つまたは複数の Microsoft SQL Server データベースとメッセージ エージェント。</span><span class="sxs-lookup"><span data-stu-id="bedd4-135">The MessageBox is made up of two components: one or more Microsoft SQL Server databases and the Message Agent.</span></span> <span data-ttu-id="bedd4-136">SQL Server データベースでは、多くのメッセージ、メッセージのプロパティ、サブスクリプション、オーケストレーションの状態、追跡データ、ルーティングのためのホスト キューなどの永続化ストアを提供します。</span><span class="sxs-lookup"><span data-stu-id="bedd4-136">The SQL Server database provides the persistence store for many things including messages, message properties, subscriptions, orchestration states, tracking data, and host queues for routing.</span></span> <span data-ttu-id="bedd4-137">メッセージ ボックス データベースの詳細については、次を参照してください。 [、メッセージ ボックス データベース](../core/the-messagebox-database.md)します。</span><span class="sxs-lookup"><span data-stu-id="bedd4-137">For more information about the MessageBox database, see [The MessageBox Database](../core/the-messagebox-database.md).</span></span>  
  
## <a name="hosts-and-host-instances"></a><span data-ttu-id="bedd4-138">ホストとホスト インスタンス</span><span class="sxs-lookup"><span data-stu-id="bedd4-138">Hosts and Host Instances</span></span>  
 <span data-ttu-id="bedd4-139">A*ホスト*などの BizTalk Server アイテムを実行する Microsoft Windows プロセスの論理表現として送信ポートやオーケストレーションです。</span><span class="sxs-lookup"><span data-stu-id="bedd4-139">A *host* is a logical representation of a Microsoft Windows process that executes BizTalk Server artifacts such as send ports and orchestrations.</span></span> <span data-ttu-id="bedd4-140">A*ホスト インスタンス*特定のサーバー上のホストの物理表現です。</span><span class="sxs-lookup"><span data-stu-id="bedd4-140">A *host instance* is the physical representation of a host on a specific server.</span></span> <span data-ttu-id="bedd4-141">ホストが所有し、BizTalk Server によって管理されていることを意味のインプロセス ホスト、または分離ホストで、BizTalk Server によって制御されていないプロセスで BizTalk Server コードが実行されていることを意味のいずれかを使用できます。</span><span class="sxs-lookup"><span data-stu-id="bedd4-141">A host can be either an in-process host, which means it is owned and managed by BizTalk Server, or an isolated host, which means that the BizTalk Server code is running in a process that is not controlled by BizTalk Server.</span></span> <span data-ttu-id="bedd4-142">分離ホストの良い例では、HTTP および SOAP アダプターの受信機能をホストするインターネット インフォメーション サービス (IIS) です。</span><span class="sxs-lookup"><span data-stu-id="bedd4-142">A good example of an isolated host is Internet Information Services (IIS), which hosts the receive functionality of the HTTP and SOAP adapters.</span></span> <span data-ttu-id="bedd4-143">。 BizTalk Server グループ全体のホストが定義されています。構成、メッセージ ボックス、ポート、およびなどを共有する BizTalk サーバーのコレクション。</span><span class="sxs-lookup"><span data-stu-id="bedd4-143">Hosts are defined for an entire BizTalk Server group; a collection of BizTalk Servers that share configuration, MessageBoxes, ports, and so on.</span></span> <span data-ttu-id="bedd4-144">ホストとホスト インスタンスの詳細については、次を参照してください。[エンティティ](../core/entities.md)します。</span><span class="sxs-lookup"><span data-stu-id="bedd4-144">For more information about hosts and host instances, see [Entities](../core/entities.md).</span></span>  
  
## <a name="saving-a-message-body"></a><span data-ttu-id="bedd4-145">メッセージ本文を保存しています</span><span class="sxs-lookup"><span data-stu-id="bedd4-145">Saving a Message Body</span></span>  
 <span data-ttu-id="bedd4-146">メッセージ本文を保存する 3 つの方法はあります。</span><span class="sxs-lookup"><span data-stu-id="bedd4-146">There are three ways to save a message body.</span></span>  
  
### <a name="from-the-admin-mmc-group-hub-page-queries"></a><span data-ttu-id="bedd4-147">管理 MMC のグループ ハブ ページのクエリから</span><span class="sxs-lookup"><span data-stu-id="bedd4-147">From the Admin MMC group hub page queries</span></span>  
 <span data-ttu-id="bedd4-148">この方法は、メッセージ ボックス データベースにのみメッセージです。</span><span class="sxs-lookup"><span data-stu-id="bedd4-148">This method is for messages in the MessageBox database only.</span></span>  
  
-   <span data-ttu-id="bedd4-149">サービス インスタンスを表示します。</span><span class="sxs-lookup"><span data-stu-id="bedd4-149">View a Service Instance.</span></span>  
  
-   <span data-ttu-id="bedd4-150">開く、**サービス インスタンスの詳細** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="bedd4-150">Open the **Service Instance Details** dialog box.</span></span>  
  
-   <span data-ttu-id="bedd4-151">をクリックして、**メッセージ タブ**このインスタンスに関連付けられたメッセージの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="bedd4-151">Click the **Messages Tab** to view the list of messages associated with this instance.</span></span>  
  
-   <span data-ttu-id="bedd4-152">メッセージを右クリックし、をクリックし、**保存**します。</span><span class="sxs-lookup"><span data-stu-id="bedd4-152">Either right-click the message, and then click **Save**.</span></span>  
  
     <span data-ttu-id="bedd4-153">- または -</span><span class="sxs-lookup"><span data-stu-id="bedd4-153">-or-</span></span>  
  
-   <span data-ttu-id="bedd4-154">メッセージをダブルクリックして開くことで、**メッセージ ビューアー**、 をクリック**保存**します。</span><span class="sxs-lookup"><span data-stu-id="bedd4-154">Double-click the message to open it in the **Message Viewer**, and click **Save**.</span></span>  
  
### <a name="from-the-operations-om"></a><span data-ttu-id="bedd4-155">Operations オブジェクト モデルから</span><span class="sxs-lookup"><span data-stu-id="bedd4-155">From the Operations OM</span></span>  
  
-   <span data-ttu-id="bedd4-156">使用**GetInstance**サービス インスタンス オブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="bedd4-156">Use **GetInstance** to retrieve a Service Instance object.</span></span>  
  
-   <span data-ttu-id="bedd4-157">使用**Instance.Messages**サービス インスタンスで現在参照されているすべてのメッセージを列挙します。</span><span class="sxs-lookup"><span data-stu-id="bedd4-157">Use **Instance.Messages [ ]** to enumerate all messages which the service instance currently references.</span></span>  
  
-   <span data-ttu-id="bedd4-158">など、メッセージ オブジェクトでメソッドを使用して**Message.BodyPart**と**Message.Context**をアクセスし、保存します。</span><span class="sxs-lookup"><span data-stu-id="bedd4-158">Use methods on the message object such as **Message.BodyPart [ ]** and **Message.Context [  ]** to access and save it.</span></span>  
  
### <a name="from-the-dta"></a><span data-ttu-id="bedd4-159">DTA から</span><span class="sxs-lookup"><span data-stu-id="bedd4-159">From the DTA</span></span>  
  
-   <span data-ttu-id="bedd4-160">使用して、DTA からメッセージを取得、 **GetTrackedInstance**と**GetTrackedmessage** API 呼び出し。</span><span class="sxs-lookup"><span data-stu-id="bedd4-160">Retrieve messages from the DTA using the **GetTrackedInstance** and **GetTrackedmessage** API calls.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bedd4-161">参照</span><span class="sxs-lookup"><span data-stu-id="bedd4-161">See Also</span></span>  
 [<span data-ttu-id="bedd4-162">ランタイム アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="bedd4-162">Runtime Architecture</span></span>](../core/runtime-architecture.md)