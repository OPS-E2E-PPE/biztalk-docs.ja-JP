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
ms.openlocfilehash: f84b05dfe668e9777fd0d4e3ef5157bf90c59fe0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996035"
---
# <a name="managing-the-bam-event-bus-service"></a><span data-ttu-id="f1d3b-102">BAM イベント バス サービスの管理</span><span class="sxs-lookup"><span data-stu-id="f1d3b-102">Managing the BAM Event Bus Service</span></span>
<span data-ttu-id="f1d3b-103">BAM イベント バス サービスは、Tracking Data Decode Service (TDDS) とも呼ばれており、転送元データベースに格納されている追跡データ (ストリーム) を処理し、そのデータを後で簡単にクエリできるように保存します。</span><span class="sxs-lookup"><span data-stu-id="f1d3b-103">The BAM Event Bus Service, also known as the Tracking Data Decode Service (TDDS), processes tracking data (streams) stored in a source database and persists that data in such a way that it is easy to query it at a later date.</span></span>  
  
 <span data-ttu-id="f1d3b-104">BAM イベント バス サービスは、ビジネス インテリジェンス データを BAM プライマリ インポート データベースに移動し、BizTalk 稼働状況の監視データを DTA データベースに移動します。</span><span class="sxs-lookup"><span data-stu-id="f1d3b-104">The BAM Event Bus service moves Business intelligence data to the BAM Primary Import database and BizTalk Health Monitoring data to the DTA database.</span></span> <span data-ttu-id="f1d3b-105">BAM イベント バス サービスは、BizTalk サービス内のサブサービスとして実行されます。</span><span class="sxs-lookup"><span data-stu-id="f1d3b-105">The BAM Event Bus service runs as a sub-service within the BizTalk service.</span></span>  
  
 <span data-ttu-id="f1d3b-106">実行中に、イベント データを収集し、アプリケーションの状態と同じデータベース内のデータを一時的に保存して Microsoft BizTalk® Server などのトランザクション アプリケーションのアクティビティを監視する — たとえば、メッセージ ボックス データベース。</span><span class="sxs-lookup"><span data-stu-id="f1d3b-106">You monitor the activities of a transactional application, such as Microsoft BizTalk® Server, by collecting event data during execution, and then temporarily storing the data in the same database as the application state—for example, the MessageBox database.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f1d3b-107">異なる BizTalk グループの追跡をホストするアプリケーション インスタンスを、同じコンピューターに複数作成しないでください。</span><span class="sxs-lookup"><span data-stu-id="f1d3b-107">Avoid creating more than one application instance that hosts tracking for different BizTalk Groups on the same computer.</span></span> <span data-ttu-id="f1d3b-108">すべての BizTalk グループが同じで表示されるため、BizTalk 管理コンソールで、またはイベント ログには、どの BizTalk グループに属しているイベントを区別することはできません異なる BizTalk グループを追跡するインスタンスが同じコンピューターに存在する場合名前。</span><span class="sxs-lookup"><span data-stu-id="f1d3b-108">If instances that track different BizTalk Groups exist on the same computer, you will not be able to distinguish which events belong to which BizTalk Groups in the BizTalk Administration Console or in the event log because all BizTalk Groups are displayed with the same name.</span></span>  
  
 <span data-ttu-id="f1d3b-109">BAM イベント バス サービスでは、イベント データを読み取ってデコードしてから、簡単にデータをクエリできる Microsoft SQL Server™ データベースに保存します。</span><span class="sxs-lookup"><span data-stu-id="f1d3b-109">The BAM Event Bus service reads the event data, decodes it, and then stores it in a Microsoft SQL Server™ database, where you can easily query the data.</span></span>  
  
 <span data-ttu-id="f1d3b-110">BAM イベント バス サービスには次の利点があります。</span><span class="sxs-lookup"><span data-stu-id="f1d3b-110">The BAM Event Bus service provides the following advantages:</span></span>  
  
- <span data-ttu-id="f1d3b-111">常にイベント データがアプリケーションの状態に一致します。また、コミットされていない進行状況は公開されません。</span><span class="sxs-lookup"><span data-stu-id="f1d3b-111">Event data always matches the state of the application, and it never exposes uncommitted progress.</span></span>  
  
- <span data-ttu-id="f1d3b-112">イベント データは、アプリケーションの状態が変化するとその状態と同じローカル トランザクションに少数のレコードとして保存されるため、実行中のアプリケーションへの影響を最小限に抑えることができます。</span><span class="sxs-lookup"><span data-stu-id="f1d3b-112">Performance impact on the running application is minimal because the event data saves as few records in the same local transaction as the application state change.</span></span>  
  
- <span data-ttu-id="f1d3b-113">アプリケーションの状態用の SQL Server ストレージは、さらに最適化され、実行パフォーマンスが向上します。</span><span class="sxs-lookup"><span data-stu-id="f1d3b-113">SQL Server storage for the application state is further optimized for execution performance.</span></span> <span data-ttu-id="f1d3b-114">データは TDDS によってデコードされ、個別のデータベース (BAM プライマリ インポート データベースまたは DTA データベースのいずれか) に格納されます。</span><span class="sxs-lookup"><span data-stu-id="f1d3b-114">The data is decoded by TDDS and stored in a separate database, either the BAM Primary import database or the DTA database.</span></span> <span data-ttu-id="f1d3b-115">レポートが生成されると、データはデータベースから照会され、アプリケーションの状態を格納するメッセージ ボックス データベースに影響を与えます。</span><span class="sxs-lookup"><span data-stu-id="f1d3b-115">When reports are generated the data is queried from the database and does impact the Message Box database, which stores the application state.</span></span>  
  
- <span data-ttu-id="f1d3b-116">アプリケーション サーバーおよびデータベースでは、クエリできる形式でイベント データを保存する操作が行われません。</span><span class="sxs-lookup"><span data-stu-id="f1d3b-116">The work to store the event data in a form that you can query is not done in the application servers and databases.</span></span> <span data-ttu-id="f1d3b-117">この操作は、BAM イベント バス サービスと転送先の SQL Server データベースを実行しているコンピューターによって行われます。</span><span class="sxs-lookup"><span data-stu-id="f1d3b-117">It is offloaded to the machines that run the BAM Event Bus service and the Destination SQL Server database.</span></span>  
  
- <span data-ttu-id="f1d3b-118">イベント データは短い待機時間で処理され、TDDS クエリ処理を高速にすることができます。</span><span class="sxs-lookup"><span data-stu-id="f1d3b-118">Event data is processed with low latency which allows TDDS queries process faster.</span></span> <span data-ttu-id="f1d3b-119">BAM イベント バス サービスでは、待機時間を最小限に抑えるためにリソースを調整します。</span><span class="sxs-lookup"><span data-stu-id="f1d3b-119">The BAM Event Bus services coordinate their resources to achieve the minimum possible latency.</span></span>  
  
  <span data-ttu-id="f1d3b-120">BAM イベント バス サーバーでは、構成情報が含まれた中央データベースへの接続を使用することにより、リソースを調整します。</span><span class="sxs-lookup"><span data-stu-id="f1d3b-120">The BAM Event Bus server coordinates its resources by using a connection to a central database, which contains the configuration information.</span></span> <span data-ttu-id="f1d3b-121">1 分ごとに、BAM イベント バス サービスによって中央データベースにメッセージが送信されます。中央データベースには、その時点の BAM イベント バス サービスの状態が格納されます。</span><span class="sxs-lookup"><span data-stu-id="f1d3b-121">Every minute, each active BAM Event Bus service sends a message to the central database, which contains the state of the BAM Event Bus service at that point in time.</span></span>  
  
  <span data-ttu-id="f1d3b-122">このメッセージは、ハートビート メッセージといいます。</span><span class="sxs-lookup"><span data-stu-id="f1d3b-122">This message is referred to as a heartbeat message.</span></span> <span data-ttu-id="f1d3b-123">各 BAM イベント バス サービスでは、次に実行する作業があるかどうかもチェックされます。</span><span class="sxs-lookup"><span data-stu-id="f1d3b-123">Each BAM Event Bus service also checks for new work that needs to be done.</span></span> <span data-ttu-id="f1d3b-124">たとえば、追加されたメッセージ ボックス データベースなど、所有されていないセッションがあるかどうかがチェックされます。</span><span class="sxs-lookup"><span data-stu-id="f1d3b-124">For example, the BAM Event Bus service checks for sessions that are not owned, such as a MessageBox database that has been added.</span></span>  
  
  <span data-ttu-id="f1d3b-125">BAM イベント バス セッションとは、イベント データを、メッセージ ボックス データベースなどの転送元データベースから、クエリできる形式で格納される転送先データベースに移動する処理です。</span><span class="sxs-lookup"><span data-stu-id="f1d3b-125">The BAM Event Bus session is the movement of the event data from the source database, such as the MessageBox, to the destination database that contains the event data in a format that you can query.</span></span> <span data-ttu-id="f1d3b-126">同じ BAM イベント バス サービスで 1 つ以上のセッションを処理できます。</span><span class="sxs-lookup"><span data-stu-id="f1d3b-126">The same BAM Event Bus service can process one or more sessions.</span></span>  
  
  <span data-ttu-id="f1d3b-127">次の図に、BAM イベント バス サーバー プールを構成する BAM イベント バス サーバーのグループを示します。</span><span class="sxs-lookup"><span data-stu-id="f1d3b-127">The following figure shows a group of BAM Event Bus servers, which make up a BAM Event Bus server pool.</span></span>  
  
  <span data-ttu-id="f1d3b-128">![](../core/media/ebiz-bam-admin-evntbuspool.gif "ebiz_bam_admin_evntbuspool")</span><span class="sxs-lookup"><span data-stu-id="f1d3b-128">![](../core/media/ebiz-bam-admin-evntbuspool.gif "ebiz_bam_admin_evntbuspool")</span></span>  
  <span data-ttu-id="f1d3b-129">BAM イベント バス サーバー プールの図</span><span class="sxs-lookup"><span data-stu-id="f1d3b-129">Diagram of a BAM Event Bus server pool</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f1d3b-130">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="f1d3b-130">In This Section</span></span>  
  
-   [<span data-ttu-id="f1d3b-131">BAM パフォーマンス カウンター</span><span class="sxs-lookup"><span data-stu-id="f1d3b-131">BAM Performance Counters</span></span>](../core/bam-performance-counters.md)  
  
-   [<span data-ttu-id="f1d3b-132">BAM イベント バス サービスのストアド プロシージャ</span><span class="sxs-lookup"><span data-stu-id="f1d3b-132">BAM Event Bus Service Stored Procedures</span></span>](../core/bam-event-bus-service-stored-procedures.md)  
  
-   [<span data-ttu-id="f1d3b-133">BAM イベント バス サービス サーバーのフェールオーバー</span><span class="sxs-lookup"><span data-stu-id="f1d3b-133">BAM Event Bus Service Server Failover</span></span>](../core/bam-event-bus-service-server-failover.md)  
  
-   [<span data-ttu-id="f1d3b-134">BAM イベント バス サービスのインスタンスの作成</span><span class="sxs-lookup"><span data-stu-id="f1d3b-134">Creating Instances of the BAM Event Bus Service</span></span>](../core/creating-instances-of-the-bam-event-bus-service.md)