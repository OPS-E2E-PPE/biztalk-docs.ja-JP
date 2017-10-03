---
title: "メッセージ ボックス データベース |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, MessageBox database
- messages, suspended messages
- MessageBox database, messages
- MessageBox database, about MessageBox database
- MessageBox database, suspended messages
- suspended messages
- MessageBox database
- suspended messages, MessageBox database
ms.assetid: f89eb02c-1b83-4127-8a91-e78fb4a1f96e
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: edf1fb3a89d6e08f6a0183a3242c53c4be890e60
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="the-messagebox-database"></a><span data-ttu-id="d9a30-102">メッセージ ボックス データベース</span><span class="sxs-lookup"><span data-stu-id="d9a30-102">The MessageBox Database</span></span>
<span data-ttu-id="d9a30-103">Microsoft BizTalk Server の公開/サブスクライブ エンジンの中心となるのは、メッセージ ボックス データベースです。</span><span class="sxs-lookup"><span data-stu-id="d9a30-103">The heart of the publish/subscribe engine in Microsoft BizTalk Server is the MessageBox database.</span></span> <span data-ttu-id="d9a30-104">2 つのコンポーネントのメッセージ ボックス データベースから成る: 1 つまたは複数の Microsoft SQL Server データベースとメッセージング エージェントです。</span><span class="sxs-lookup"><span data-stu-id="d9a30-104">The MessageBox is made up of two components: one or more Microsoft SQL Server databases and the Messaging Agent.</span></span> <span data-ttu-id="d9a30-105">メッセージ、メッセージ部分、メッセージ プロパティ、サブスクリプション、オーケストレーションの状態、追跡データ、ルーティングのためのホスト キューなど、その他多くの要素に対して、SQL Server データベースによる永続的なストアが提供されます。</span><span class="sxs-lookup"><span data-stu-id="d9a30-105">The SQL Server database provides the persistence store for many things including messages, message parts, message properties, subscriptions, orchestration state, tracking data, host queues for routing, and others.</span></span> <span data-ttu-id="d9a30-106">BizTalk Server グループには、メッセージの公開先として 1 つまたは複数のメッセージ ボックス データベースを設定できます。メッセージのサブスクライバーは、これらのデータベースからメッセージを抽出します。</span><span class="sxs-lookup"><span data-stu-id="d9a30-106">The BizTalk Server group may have one or more MessageBox databases into which it publishes messages and from which subscribers to those messages extract messages.</span></span>  
  
 <span data-ttu-id="d9a30-107">メッセージのルーティングやサブスクリプション情報の入力に関するロジックの一部は、データベースから提供されます。</span><span class="sxs-lookup"><span data-stu-id="d9a30-107">The database provides some of the logic related to routing messages and fulfilling subscriptions.</span></span> <span data-ttu-id="d9a30-108">ただし、データベース コンポーネントは、メッセージ エージェントによってカプセル化、抽象化されます。BizTalk Server とメッセージ ボックスとのやりとりには、インターフェイスとしてメッセージ エージェントが使用されます。</span><span class="sxs-lookup"><span data-stu-id="d9a30-108">The Message Agent, however, is the component that encapsulates and abstracts the database component and is the interface used by BizTalk Server to interact with the MessageBox.</span></span> <span data-ttu-id="d9a30-109">メッセージ エージェントは、メッセージの公開、サブスクライブ、取得などを行うためのインターフェイスを提供する Component Object Model (COM) コンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="d9a30-109">The Message Agent is a Component Object Model (COM) component that provides interfaces for publishing messages, subscribing to messages, retrieving messages, and so on.</span></span> <span data-ttu-id="d9a30-110">このインターフェイスは、アダプター フレームワークやオーケストレーションなど他の BizTalk Server コンポーネントが、メッセージ ボックスと対話するために使用される唯一のメカニズムです。</span><span class="sxs-lookup"><span data-stu-id="d9a30-110">This interface is the only mechanism used by other BizTalk Server components, including the adapter framework and orchestrations, to interact with the MessageBox.</span></span>  
  
## <a name="the-messagebox-and-the-message"></a><span data-ttu-id="d9a30-111">メッセージ ボックスとメッセージ</span><span class="sxs-lookup"><span data-stu-id="d9a30-111">The MessageBox and the Message</span></span>  
 <span data-ttu-id="d9a30-112">メッセージ ボックス データベースのサブスクリプションは、設定済みの情報とサービス情報のセットです。</span><span class="sxs-lookup"><span data-stu-id="d9a30-112">A MessageBox database subscription is a set of established information and service information.</span></span> <span data-ttu-id="d9a30-113">設定済みの情報 (述語情報) とは、メッセージが満たす必要のある条件です。</span><span class="sxs-lookup"><span data-stu-id="d9a30-113">The established (or predicate) information is the criteria that a message must meet.</span></span> <span data-ttu-id="d9a30-114">サービス情報は、条件を満たしたメッセージに対する処理を表します。</span><span class="sxs-lookup"><span data-stu-id="d9a30-114">The service information is what to do with the message that meets the criteria.</span></span> <span data-ttu-id="d9a30-115">これらの情報はすべてメッセージングおよびオーケストレーション エンジンを呼び出す一連のテーブルに保存されます。</span><span class="sxs-lookup"><span data-stu-id="d9a30-115">All of this information is stored in a set of tables that call the messaging and orchestration engine.</span></span>  
  
 <span data-ttu-id="d9a30-116">BizTalk Server でメッセージを受信すると、パイプラインでメッセージが処理され、メッセージ ボックス データベースにそのメッセージが保存されます。</span><span class="sxs-lookup"><span data-stu-id="d9a30-116">When BizTalk Server receives a message, it processes the message in a pipeline, and places the message in the MessageBox database.</span></span> <span data-ttu-id="d9a30-117">受信メッセージにはコンテキストがあります。</span><span class="sxs-lookup"><span data-stu-id="d9a30-117">The incoming message has a context.</span></span> <span data-ttu-id="d9a30-118">メッセージ コンテキストとは、そのメッセージに関連付けられているプロパティのセットを指します。</span><span class="sxs-lookup"><span data-stu-id="d9a30-118">The message context is a set of properties associated with the message.</span></span> <span data-ttu-id="d9a30-119">メッセージ コンテキストのプロパティには次の 3 種類があります。</span><span class="sxs-lookup"><span data-stu-id="d9a30-119">The three types of message context properties are:</span></span>  
  
-   <span data-ttu-id="d9a30-120">単純な書き込みプロパティ</span><span class="sxs-lookup"><span data-stu-id="d9a30-120">Simple written properties</span></span>  
  
-   <span data-ttu-id="d9a30-121">昇格させたプロパティ</span><span class="sxs-lookup"><span data-stu-id="d9a30-121">Promoted properties</span></span>  
  
-   <span data-ttu-id="d9a30-122">述語プロパティ</span><span class="sxs-lookup"><span data-stu-id="d9a30-122">Predicate properties</span></span>  
  
 <span data-ttu-id="d9a30-123">昇格させたメッセージと述語メッセージのプロパティは、このメッセージをサブスクライブしているビジネス プロセスを示すと共に、そのビジネス プロセスにメッセージを受信するためのアクセス許可があるかどうかも示します。</span><span class="sxs-lookup"><span data-stu-id="d9a30-123">The promoted and predicate message properties indicate the business process that subscribes to this message, and whether the business process has the permissions necessary to receive the message.</span></span>  
  
 <span data-ttu-id="d9a30-124">あるビジネス プロセスがメッセージをサブスクライブしていれば、メッセージ ボックス データベースはそのビジネス プロセスにメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="d9a30-124">If a business process subscribes to the message, the MessageBox database sends the message to the business process.</span></span> <span data-ttu-id="d9a30-125">ビジネス プロセスは、そのメッセージを受信すると、使用可能なホスト インスタンスでメッセージを処理します。</span><span class="sxs-lookup"><span data-stu-id="d9a30-125">When the business process receives the message, it processes the message on an available host instance.</span></span> <span data-ttu-id="d9a30-126">メッセージの処理後、ビジネス プロセスがパイプラインまたは送信ポートをサブスクライブしている場合、そのビジネス プロセスはメッセージ ボックス データベースに返信メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="d9a30-126">After processing the message, if the business process subscribes to a pipeline or send port, the business process sends a return message to the MessageBox database.</span></span>  
  
 <span data-ttu-id="d9a30-127">各 BizTalk ホストに関連付けられているメッセージ ボックスには、作業キューと保留キューがそれぞれ 1 つずつあります。</span><span class="sxs-lookup"><span data-stu-id="d9a30-127">For each BizTalk Host, the associated MessageBox has one work queue and one suspended queue.</span></span> <span data-ttu-id="d9a30-128">さらに、各メッセージ ボックス データベースには、静的状態、動的状態、およびインスタンス状態のテーブルのセットが格納されています。</span><span class="sxs-lookup"><span data-stu-id="d9a30-128">Additionally, each MessageBox database contains a set of tables for static states, dynamic states, and instance state.</span></span> <span data-ttu-id="d9a30-129">BizTalk ホストについては、次を参照してください。[エンティティ](../core/entities.md)です。</span><span class="sxs-lookup"><span data-stu-id="d9a30-129">For information about BizTalk Hosts, see [Entities](../core/entities.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="d9a30-130">ホストが使用不可になった場合、たとえば、ホストからメッセージを受信するメッセージ ボックス データベースが使用できなくなった場合は、他のメッセージ ボックス データベースもすべて使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="d9a30-130">If a host becomes unavailable --for example, the MessageBox database that receives messages from that host becomes unavailable, all other MessageBox databases become unavailable.</span></span>  
  
 <span data-ttu-id="d9a30-131">最初のメッセージ ボックス データベースは、構成ウィザードの実行時に作成されます。</span><span class="sxs-lookup"><span data-stu-id="d9a30-131">You create the first MessageBox database when you run the Configuration Wizard.</span></span> <span data-ttu-id="d9a30-132">構成されたメッセージ ボックス データベースが、マスター メッセージ ボックス データベースになります。</span><span class="sxs-lookup"><span data-stu-id="d9a30-132">The MessageBox database that is configured becomes the master MessageBox database.</span></span> <span data-ttu-id="d9a30-133">マスター メッセージ ボックス データベースは、BizTalk Server 環境内にある他のすべてのメッセージ ボックス データベースのサブスクリプションを評価し、ルーティングします。</span><span class="sxs-lookup"><span data-stu-id="d9a30-133">The master MessageBox database evaluates and routes subscriptions to all other MessageBox databases in the BizTalk Server environment.</span></span> <span data-ttu-id="d9a30-134">マスター メッセージ ボックス データベースのパフォーマンスを向上させる方法については、次を参照してください。[メッセージ ボックス データベースを管理する](../core/managing-messagebox-databases.md)です。</span><span class="sxs-lookup"><span data-stu-id="d9a30-134">For information about improving performance for the master MessageBox database, see [Managing MessageBox Databases](../core/managing-messagebox-databases.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="d9a30-135">メッセージ ボックス データベースに対してフェールオーバー保護を行うには、SQL Server クラスタリングを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d9a30-135">You must use SQL Server clustering to provide failover protection for MessageBox databases.</span></span>  
  
## <a name="suspended-messages-in-the-messagebox-database"></a><span data-ttu-id="d9a30-136">メッセージ ボックス データベース内の保留メッセージ</span><span class="sxs-lookup"><span data-stu-id="d9a30-136">Suspended Messages in the MessageBox Database</span></span>  
 <span data-ttu-id="d9a30-137">BizTalk Server では中断したパイプラインに関連するメッセージがメッセージ ボックス データベースに保存されます。</span><span class="sxs-lookup"><span data-stu-id="d9a30-137">BizTalk Server stores messages associated with suspended pipelines in the MessageBox database.</span></span> <span data-ttu-id="d9a30-138">パイプラインでエラーが発生した場合、BizTalk Server ではそのメッセージのインスタンスが中断されます。</span><span class="sxs-lookup"><span data-stu-id="d9a30-138">If a failure occurs in the pipeline, BizTalk Server suspends the instance of a message.</span></span> <span data-ttu-id="d9a30-139">中断されたサービスのインスタンスには、次の 2 種類があります。</span><span class="sxs-lookup"><span data-stu-id="d9a30-139">There are two types of suspended service instances:</span></span>  
  
-   <span data-ttu-id="d9a30-140">中断された、再開可能なインスタンス。</span><span class="sxs-lookup"><span data-stu-id="d9a30-140">Suspended instances that you can resume.</span></span>  
  
-   <span data-ttu-id="d9a30-141">中断された、再開不可能なインスタンス。</span><span class="sxs-lookup"><span data-stu-id="d9a30-141">Suspended instances that you cannot resume.</span></span> <span data-ttu-id="d9a30-142">たとえば、インスタンスが破壊されている場合などです。</span><span class="sxs-lookup"><span data-stu-id="d9a30-142">For example, if an instance is corrupt.</span></span>  
  
 <span data-ttu-id="d9a30-143">中断の原因によってことができますを BizTalk Server を中断する - たとえば、オーケストレーションを中断図形に到達またはトランスポートがメッセージを配信できなかった場合 BizTalk Server が自動的に削除保留サービスを再開するにはメッセージ ボックス データベースから再開することはできませんのインスタンス。</span><span class="sxs-lookup"><span data-stu-id="d9a30-143">Depending on the cause of the suspension, you may be able to resume services that BizTalk Server suspends -- for example, if an orchestration hits a Suspend shape, or if a transport was unable to deliver a message, BizTalk Server does not automatically remove suspended instances that you cannot resume from the MessageBox database.</span></span> <span data-ttu-id="d9a30-144">サービス インスタンスを保留キューから削除する前に、ディスクに保存することができます。</span><span class="sxs-lookup"><span data-stu-id="d9a30-144">You can choose to save a service instance to disk before removing it from the suspended queue.</span></span>  
  
 <span data-ttu-id="d9a30-145">メッセージ ボックス データベースのバックアップの詳細については、次を参照してください。[をバックアップおよび BizTalk Server データベースの復元](../core/backing-up-and-restoring-biztalk-server.md)です。</span><span class="sxs-lookup"><span data-stu-id="d9a30-145">For information about backing up MessageBox databases, see [Backing Up and Restoring BizTalk Server Databases](../core/backing-up-and-restoring-biztalk-server.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9a30-146">参照</span><span class="sxs-lookup"><span data-stu-id="d9a30-146">See Also</span></span>  
 [<span data-ttu-id="d9a30-147">メッセージング エンジン</span><span class="sxs-lookup"><span data-stu-id="d9a30-147">The Messaging Engine</span></span>](../core/the-messaging-engine.md)