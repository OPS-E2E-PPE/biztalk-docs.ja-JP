---
title: BAM イベント バス サービスの管理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MessageBox database, migrating data
- Primary Import database [BAM], migrating data
- migrating, data [BAM]
- managing [BAM], Event Bus Service
- Event Bus Service [BAM], managing
- Tracking Data Decode Service (TDDS)
ms.assetid: 556e7fe2-4a7d-46f6-8e55-f41be4e666dc
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2c9c2851ed6e4c126475ad21f65999a131b24629
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65329065"
---
# <a name="managing-the-bam-event-bus-service"></a><span data-ttu-id="66514-102">BAM イベント バス サービスの管理</span><span class="sxs-lookup"><span data-stu-id="66514-102">Managing the BAM Event Bus Service</span></span>
<span data-ttu-id="66514-103">BAM イベント バス サービスとも呼ばれる、Tracking Data Decode Service (TDDS) は、ソース データベースに格納されている追跡データ (ストリーム) を処理し、そのデータを簡単に、後でクエリを実行するように保持します。</span><span class="sxs-lookup"><span data-stu-id="66514-103">The BAM Event Bus Service, also known as the Tracking Data Decode Service (TDDS), processes tracking data (streams) stored in a source database and persists that data in such a way that it is easy to query it at a later date.</span></span>  
  
 <span data-ttu-id="66514-104">BAM イベント バス サービスは、BAM プライマリ インポート データベースへのビジネス インテリジェンス データと BizTalk 稼働状況の監視データを DTA データベースに移動します。</span><span class="sxs-lookup"><span data-stu-id="66514-104">The BAM Event Bus service moves Business intelligence data to the BAM Primary Import database and BizTalk Health Monitoring data to the DTA database.</span></span> <span data-ttu-id="66514-105">BAM イベント バス サービスは、BizTalk サービス内のサブサービスとして実行されます。</span><span class="sxs-lookup"><span data-stu-id="66514-105">The BAM Event Bus service runs as a sub-service within the BizTalk service.</span></span>  
  
 <span data-ttu-id="66514-106">実行中に、イベント データを収集し、アプリケーションの状態と同じデータベース内のデータを一時的に保存して Microsoft BizTalk® Server などのトランザクション アプリケーションのアクティビティを監視する — たとえば、メッセージ ボックス データベース。</span><span class="sxs-lookup"><span data-stu-id="66514-106">You monitor the activities of a transactional application, such as Microsoft BizTalk® Server, by collecting event data during execution, and then temporarily storing the data in the same database as the application state—for example, the MessageBox database.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="66514-107">同じコンピューター上の別の BizTalk グループの追跡をホストする 1 つ以上のアプリケーション インスタンスを作成しないでください。</span><span class="sxs-lookup"><span data-stu-id="66514-107">Avoid creating more than one application instance that hosts tracking for different BizTalk Groups on the same computer.</span></span> <span data-ttu-id="66514-108">すべての BizTalk グループが同じで表示されるため、BizTalk 管理コンソールで、またはイベント ログには、どの BizTalk グループに属しているイベントを区別することはできません異なる BizTalk グループを追跡するインスタンスが同じコンピューターに存在する場合名前。</span><span class="sxs-lookup"><span data-stu-id="66514-108">If instances that track different BizTalk Groups exist on the same computer, you will not be able to distinguish which events belong to which BizTalk Groups in the BizTalk Administration Console or in the event log because all BizTalk Groups are displayed with the same name.</span></span>  
  
 <span data-ttu-id="66514-109">BAM イベント バス サービスは、イベント データを読み取る、それをデコードし、データを簡単にクエリできる、Microsoft SQL Server™ データベースに格納します。</span><span class="sxs-lookup"><span data-stu-id="66514-109">The BAM Event Bus service reads the event data, decodes it, and then stores it in a Microsoft SQL Server™ database, where you can easily query the data.</span></span>  
  
 <span data-ttu-id="66514-110">BAM イベント バス サービスには次の利点があります。</span><span class="sxs-lookup"><span data-stu-id="66514-110">The BAM Event Bus service provides the following advantages:</span></span>  
  
- <span data-ttu-id="66514-111">イベント データ、アプリケーションの状態を常に一致して、コミットされていない進行状況は公開されません。</span><span class="sxs-lookup"><span data-stu-id="66514-111">Event data always matches the state of the application, and it never exposes uncommitted progress.</span></span>  
  
- <span data-ttu-id="66514-112">イベント データには、アプリケーションの状態の変化と同じローカル トランザクションに少数のレコードとしてが保存されるため、実行中のアプリケーションのパフォーマンスに影響は最小限です。</span><span class="sxs-lookup"><span data-stu-id="66514-112">Performance impact on the running application is minimal because the event data saves as few records in the same local transaction as the application state change.</span></span>  
  
- <span data-ttu-id="66514-113">アプリケーションの状態の記憶域を SQL Server が実行のパフォーマンスをさらに最適化されています。</span><span class="sxs-lookup"><span data-stu-id="66514-113">SQL Server storage for the application state is further optimized for execution performance.</span></span> <span data-ttu-id="66514-114">データは TDDS によってデコードし、別のデータベース、BAM プライマリ インポート データベースまたは DTA データベースのいずれかに格納されています。</span><span class="sxs-lookup"><span data-stu-id="66514-114">The data is decoded by TDDS and stored in a separate database, either the BAM Primary import database or the DTA database.</span></span> <span data-ttu-id="66514-115">レポートが生成されるデータは、データベースから問い合わせが実行されは、アプリケーションの状態を格納するメッセージ ボックス データベースに影響します。</span><span class="sxs-lookup"><span data-stu-id="66514-115">When reports are generated the data is queried from the database and does impact the Message Box database, which stores the application state.</span></span>  
  
- <span data-ttu-id="66514-116">クエリを実行できる形式でイベント データを格納する作業は、アプリケーション サーバーとデータベースでは行われません。</span><span class="sxs-lookup"><span data-stu-id="66514-116">The work to store the event data in a form that you can query is not done in the application servers and databases.</span></span> <span data-ttu-id="66514-117">BAM イベント バス サービスと転送先 SQL Server データベースを実行するマシンにオフロードします。</span><span class="sxs-lookup"><span data-stu-id="66514-117">It is offloaded to the machines that run the BAM Event Bus service and the Destination SQL Server database.</span></span>  
  
- <span data-ttu-id="66514-118">イベント データは、TDDS クエリ処理を高速化できる、短い待機時間で処理されます。</span><span class="sxs-lookup"><span data-stu-id="66514-118">Event data is processed with low latency which allows TDDS queries process faster.</span></span> <span data-ttu-id="66514-119">BAM イベント バス サービスでは、最小の待機時間を実現するためのリソースを調整します。</span><span class="sxs-lookup"><span data-stu-id="66514-119">The BAM Event Bus services coordinate their resources to achieve the minimum possible latency.</span></span>  
  
  <span data-ttu-id="66514-120">BAM イベント バス サーバーでは、構成情報を格納する中央データベースへの接続を使用して、リソースを調整します。</span><span class="sxs-lookup"><span data-stu-id="66514-120">The BAM Event Bus server coordinates its resources by using a connection to a central database, which contains the configuration information.</span></span> <span data-ttu-id="66514-121">1 分ごとに、アクティブな各 BAM イベント バス サービスは、中央のデータベースは、その時点で BAM イベント バス サービスの状態を格納するメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="66514-121">Every minute, each active BAM Event Bus service sends a message to the central database, which contains the state of the BAM Event Bus service at that point in time.</span></span>  
  
  <span data-ttu-id="66514-122">このメッセージは、ハートビート メッセージと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="66514-122">This message is referred to as a heartbeat message.</span></span> <span data-ttu-id="66514-123">各 BAM イベント バス サービスは、新しい作業を行う必要があるのも確認します。</span><span class="sxs-lookup"><span data-stu-id="66514-123">Each BAM Event Bus service also checks for new work that needs to be done.</span></span> <span data-ttu-id="66514-124">たとえば、BAM イベント バス サービスは、所有されていない追加されているメッセージ ボックス データベースなどのセッションをチェックします。</span><span class="sxs-lookup"><span data-stu-id="66514-124">For example, the BAM Event Bus service checks for sessions that are not owned, such as a MessageBox database that has been added.</span></span>  
  
  <span data-ttu-id="66514-125">BAM イベント バス セッションとは、クエリを実行できる形式でイベント データを格納する出力先データベースに、メッセージ ボックスなど、ソース データベースからイベント データの移動です。</span><span class="sxs-lookup"><span data-stu-id="66514-125">The BAM Event Bus session is the movement of the event data from the source database, such as the MessageBox, to the destination database that contains the event data in a format that you can query.</span></span> <span data-ttu-id="66514-126">同じ BAM イベント バス サービスでは、1 つまたは複数のセッションを処理できます。</span><span class="sxs-lookup"><span data-stu-id="66514-126">The same BAM Event Bus service can process one or more sessions.</span></span>  
  
  <span data-ttu-id="66514-127">次の図は、BAM イベント バス サーバー プールを構成する BAM イベント バス サーバーのグループを示しています。</span><span class="sxs-lookup"><span data-stu-id="66514-127">The following figure shows a group of BAM Event Bus servers, which make up a BAM Event Bus server pool.</span></span>  
  
  <span data-ttu-id="66514-128">![](../core/media/ebiz-bam-admin-evntbuspool.gif "ebiz_bam_admin_evntbuspool")</span><span class="sxs-lookup"><span data-stu-id="66514-128">![](../core/media/ebiz-bam-admin-evntbuspool.gif "ebiz_bam_admin_evntbuspool")</span></span>  
  <span data-ttu-id="66514-129">BAM イベント バス サーバー プールの図</span><span class="sxs-lookup"><span data-stu-id="66514-129">Diagram of a BAM Event Bus server pool</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="66514-130">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="66514-130">In This Section</span></span>  
  
-   [<span data-ttu-id="66514-131">BAM パフォーマンス カウンター</span><span class="sxs-lookup"><span data-stu-id="66514-131">BAM Performance Counters</span></span>](../core/bam-performance-counters.md)  
  
-   [<span data-ttu-id="66514-132">BAM イベント バス サービスのストアド プロシージャ</span><span class="sxs-lookup"><span data-stu-id="66514-132">BAM Event Bus Service Stored Procedures</span></span>](../core/bam-event-bus-service-stored-procedures.md)  
  
-   [<span data-ttu-id="66514-133">BAM イベント バス サービス サーバーのフェールオーバー</span><span class="sxs-lookup"><span data-stu-id="66514-133">BAM Event Bus Service Server Failover</span></span>](../core/bam-event-bus-service-server-failover.md)  
  
-   [<span data-ttu-id="66514-134">BAM イベント バス サービスのインスタンスの作成</span><span class="sxs-lookup"><span data-stu-id="66514-134">Creating Instances of the BAM Event Bus Service</span></span>](../core/creating-instances-of-the-bam-event-bus-service.md)