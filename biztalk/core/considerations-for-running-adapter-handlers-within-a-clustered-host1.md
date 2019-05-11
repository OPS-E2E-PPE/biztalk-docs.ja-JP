---
title: クラスター化された Host1 でアダプター ハンドラーの実行に関する考慮事項 |Microsoft Docs
ms.custom: ''
ms.date: 2016-03-17
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- high availability
- receive adapters, clustering
- clustering, POP3 adapters
- FTP adapters, clustering
- clustering, receive adapters
- NLB system
- MSMQ send handler
- MSMQ receive handler
- clustering, FTP adapters
- handlers [adapters], best practices
- hosts, clustering
- MSMQ adapters
- clustering, MSMQ adapters
- adapters, best practices
- adapters, handlers
- POP3 adapters, clustering
- MSMQ adapters, clustering
- clustering
ms.assetid: ee66663c-4f4d-4515-9df1-aacf4fc72be4
caps.latest.revision: 27
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d6ac819e5255a423427e0e8c10235f73ab1ced5f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390394"
---
# <a name="considerations-for-running-adapter-handlers-within-a-clustered-host"></a><span data-ttu-id="3f33b-102">クラスター化されたホストでアダプター ハンドラーの実行に関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="3f33b-102">Considerations for Running Adapter Handlers within a Clustered Host</span></span>
<span data-ttu-id="3f33b-103">BizTalk ホストのクラスターのサポートは、次の統合 BizTalk アダプターの高可用性を実現する使用可能な: FTP アダプター、SFTP アダプター、MSMQ アダプター、および POP3 アダプター。</span><span class="sxs-lookup"><span data-stu-id="3f33b-103">BizTalk host cluster support is available to provide high availability for the following integrated BizTalk adapters: the FTP adapter, the SFTP adapter, the MSMQ adapter, and the POP3 adapter.</span></span> <span data-ttu-id="3f33b-104">また、順次配送の目的でアダプターの単一インスタンスを実行する場合に、ホスト クラスター サポートを利用して高い可用性を実現できます。</span><span class="sxs-lookup"><span data-stu-id="3f33b-104">Host cluster support is also provided so that there is high availability for running a single instance of an adapter for purposes of ordered delivery.</span></span>  
  
 <span data-ttu-id="3f33b-105">すべての BizTalk アダプター ハンドラーは、クラスター化されたホストで実行できますが、以下に示すように、以外のクラスター化されたホストでアダプター ハンドラーを実行するために派生の利点はありません。</span><span class="sxs-lookup"><span data-stu-id="3f33b-105">All of the BizTalk adapter handlers  can be run in a clustered host but there is no benefit derived for running adapter handlers in a clustered host except as described below.</span></span> <span data-ttu-id="3f33b-106">処理の要件では、次に示すシナリオのいずれかが含まれない場合、クラスター化されたホストでアダプター ハンドラーいない実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3f33b-106">If your processing requirements do not include any of the scenarios described below, then you should not run adapter handlers in a clustered host.</span></span>  
  
## <a name="running-the-ftp-or-sftp-adapter-receive-handler-within-a-clustered-biztalk-host"></a><span data-ttu-id="3f33b-107">FTP または SFTP を実行しているアダプターの受信ハンドラーがクラスター化された BizTalk ホスト</span><span class="sxs-lookup"><span data-stu-id="3f33b-107">Running the FTP or SFTP adapter receive handler within a clustered BizTalk host</span></span>  
 <span data-ttu-id="3f33b-108">ほとんどの BizTalk Server が BizTalk で実行する複数のアダプター ハンドラーを作成して、統合アダプター、高可用性を実現できます別のインスタンスをホスト[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]BizTalk グループ内のサーバー。</span><span class="sxs-lookup"><span data-stu-id="3f33b-108">For most of the BizTalk Server integrated adapters, high availability can be achieved by creating multiple adapter handlers to run on BizTalk host instances on different [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] servers within a BizTalk group.</span></span> <span data-ttu-id="3f33b-109">FTP または SFTP アダプターの受信ハンドラーは should not、ただし、複数の BizTalk ホスト インスタンスで同時に実行するように構成します。</span><span class="sxs-lookup"><span data-stu-id="3f33b-109">FTP or SFTP adapter receive handlers should not, however, be configured to run in multiple BizTalk host instances simultaneously.</span></span> <span data-ttu-id="3f33b-110">FTP または SFTP 受信アダプターの使用は、ターゲット システムからファイルを取得する FTP または SFTP プロトコルであるために、この推奨事項が行われます。</span><span class="sxs-lookup"><span data-stu-id="3f33b-110">This recommendation is made because the FTP or SFTP receive adapter uses the FTP or SFTP protocol to retrieve files from the target system.</span></span> <span data-ttu-id="3f33b-111">FTP または SFTP プロトコルでは、同じファイルの複数のコピーが同時に取得がされないようにするファイルをロックしません受信アダプターが FTP または SFTP の複数のインスタンスを実行している場合。</span><span class="sxs-lookup"><span data-stu-id="3f33b-111">The FTP or SFTP protocol does not lock files to ensure that multiple copies of the same file are not retrieved simultaneously when running multiple instances of the FTP or SFTP receive adapter.</span></span>  
  
 <span data-ttu-id="3f33b-112">高可用性の FTP または SFTP 受信アダプターでは、構成する必要がありますを実現するには、FTP または SFTP アダプターがクラスター化された BizTalk ホスト インスタンスで実行するに受信します。</span><span class="sxs-lookup"><span data-stu-id="3f33b-112">To provide high availability for the FTP or SFTP receive adapter, you should configure the FTP or SFTP receive adapter to run in a BizTalk host instance that has been clustered.</span></span>  
  
## <a name="running-msmq-adapter-handlers-within-a-clustered-biztalk-host"></a><span data-ttu-id="3f33b-113">クラスター化された BizTalk ホストで MSMQ アダプター ハンドラーを実行する</span><span class="sxs-lookup"><span data-stu-id="3f33b-113">Running MSMQ adapter handlers within a clustered BizTalk host</span></span>  
 <span data-ttu-id="3f33b-114">MSMQ アダプターの高可用性を確保して、MSMQ アダプターによって送受信されるメッセージのトランザクションの一貫性を確保するには、次の操作を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="3f33b-114">To ensure high availability for the MSMQ adapter and to ensure transactional consistency for messages sent or received by the MSMQ adapter, you should do the following:</span></span>  
  
1. <span data-ttu-id="3f33b-115">Windows クラスタ グループでクラスター化リソースとしてのメッセージ キュー (MSMQ) を構成、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]コンピューター。</span><span class="sxs-lookup"><span data-stu-id="3f33b-115">Configure Message Queuing (MSMQ) as a clustered resource in a Windows cluster group on your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computers.</span></span>  
  
2. <span data-ttu-id="3f33b-116">リソースの依存関係の一覧にクラスター化された BizTalk ホストのクラスター化された MSMQ サービスを追加します。</span><span class="sxs-lookup"><span data-stu-id="3f33b-116">Add the clustered MSMQ service to the list of Resource dependencies for the clustered BizTalk host.</span></span> <span data-ttu-id="3f33b-117">これにより、常にクラスター化された BizTalk ホストのフェールオーバーのシナリオでクラスター化された MSMQ サービスの後に開始されます。</span><span class="sxs-lookup"><span data-stu-id="3f33b-117">This ensures that the clustered BizTalk host always starts after the clustered MSMQ service in failover scenarios.</span></span>  
  
3. <span data-ttu-id="3f33b-118">MSMQ アダプターの送信を構成し、クラスター化された MSMQ リソースと同じクラスター グループ内のクラスター リソースとして構成されている BizTalk ホスト インスタンスでハンドラーを受信します。</span><span class="sxs-lookup"><span data-stu-id="3f33b-118">Configure the MSMQ adapter send and receive handlers in a BizTalk host instance that has been configured as a cluster resource in the same cluster group as the clustered MSMQ resource.</span></span>  
  
   <span data-ttu-id="3f33b-119">次の手順は、次の理由から推奨されます。</span><span class="sxs-lookup"><span data-stu-id="3f33b-119">These steps are recommended for the following reasons:</span></span>  
  
   <span data-ttu-id="3f33b-120">**MSMQ アダプターの受信ハンドラー** – MSMQ 4.0 (Windows Server 2008) より前のバージョンの MSMQ はリモート トランザクション読み取りをサポートしていません。 ローカル トランザクションの読み込みはサポートされています。</span><span class="sxs-lookup"><span data-stu-id="3f33b-120">**MSMQ adapter receive handler** – MSMQ versions prior to MSMQ 4.0 (Windows Server 2008) do not support remote transactional reads; only local transactional reads are supported.</span></span> <span data-ttu-id="3f33b-121">この場合、MSMQ アダプターの受信ハンドラーは、MSMQ アダプターでローカル トランザクションの読み込みを完了するクラスター化されたメッセージ キュー サービスに対してローカルのホスト インスタンスで実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3f33b-121">In this case, the MSMQ adapter receive handler must run in a host instance that is local to the clustered Message Queuing service to complete local transactional reads with the MSMQ adapter.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="3f33b-122">MSMQ アダプターの受信ハンドラーでは、受信ハンドラーのホスト インスタンスがで実行されている同じコンピューター上のメッセージ キュー サービスはローカルの非クラスター化インスタンスが実行されていることが必要です。</span><span class="sxs-lookup"><span data-stu-id="3f33b-122">The MSMQ adapter receive handler requires that a local non-clustered instance of the Message Queuing service is running on the same computer that the receive handler host instance is running on.</span></span>  
  
 <span data-ttu-id="3f33b-123">**MSMQ アダプターの送信ハンドラー** - できる場合は、MSMQ サービスを送信キューが失敗したように、MSMQ アダプター、MSMQ アダプターの送信ハンドラーで使用される発信キューによるトランザクション送信の一貫性を高可用性にする必要があります再開します。</span><span class="sxs-lookup"><span data-stu-id="3f33b-123">**MSMQ adapter send handler** - To ensure the consistency of transactional sends made by the MSMQ adapter, the outgoing queue used by the MSMQ adapter send handler should be highly available so that if the MSMQ service for the outgoing queue fails it can be resumed.</span></span> <span data-ttu-id="3f33b-124">クラスター グループでクラスター化されたメッセージ Queuingresource と MSMQ アダプター ハンドラーの構成と、MSMQ アダプターの送信ハンドラーで使用される発信キューを高可用性になることが確認します。</span><span class="sxs-lookup"><span data-stu-id="3f33b-124">Configuring a clustered Message Queuingresource and the MSMQ adapter handlers in a cluster group will ensure that the outgoing queue used by the MSMQ adapter send handler will be highly available.</span></span> <span data-ttu-id="3f33b-125">メッセージ キュー サービスが失敗したことは、メッセージの損失の可能性が軽減されます。</span><span class="sxs-lookup"><span data-stu-id="3f33b-125">This will mitigate the possibility of message loss in the event that the Message Queuing service fails.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3f33b-126">MSMQ 受信場所が**のみ**BizTalk グループに複数の BizTalk コンピューター上のホストが表示される、MSMQ を実行して高可用性を実現することができますし、リモートの MSMQ サーバー上の MSMQ キューから受信します。</span><span class="sxs-lookup"><span data-stu-id="3f33b-126">If the MSMQ receive location is **only** receiving from MSMQ queues on a remote MSMQ server, then high availability can be achieved by running the MSMQ receive host on multiple BizTalk computers in the BizTalk group.</span></span>  <span data-ttu-id="3f33b-127">MSMQ の高可用性を実現するには、リモート MSMQ サーバーが Windows でフェールオーバー クラスタ リングを使用することを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3f33b-127">To provide high availability for MSMQ, you must ensure the remote MSMQ server is using failover clustering in Windows.</span></span>  <span data-ttu-id="3f33b-128">トランザクション キューを使用して場合リモート MSMQ サーバーが MSMQ 4.0 (Windows Server 2008) を実行する必要がありますまたはそれ以降。</span><span class="sxs-lookup"><span data-stu-id="3f33b-128">If using transactional queues, the remote MSMQ server must be running MSMQ 4.0 (Windows Server 2008) or above.</span></span>  
  
## <a name="running-the-pop3-adapter-receive-handler-within-a-clustered-biztalk-host"></a><span data-ttu-id="3f33b-129">クラスター化された BizTalk ホストで POP3 アダプターの受信ハンドラーを実行する</span><span class="sxs-lookup"><span data-stu-id="3f33b-129">Running the POP3 adapter receive handler within a clustered BizTalk host</span></span>  
 <span data-ttu-id="3f33b-130">POP3 アダプターの受信ハンドラーは、アダプターが読み込みを行う POP3 サーバーが同一のメールボックスに対する複数の同時接続が許可されない限り、クラスター化された BizTalk ホストで実行するように構成する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="3f33b-130">The POP3 adapter receive handler does not need to be configured to run in a clustered BizTalk host unless the POP3 server that the adapter is reading from allows multiple concurrent connections to be made to the same mailbox.</span></span> <span data-ttu-id="3f33b-131">受信ハンドラーを BizTalk ホストで実行するを単一の POP3 アダプターを構成することで、POP3 アダプターの可用性に POP3 アダプターが接続されている POP3 サーバーが高いことをお勧めします。 その後、メールボックスに対する複数の同時接続を許可している場合クラスター化されたインスタンス。</span><span class="sxs-lookup"><span data-stu-id="3f33b-131">If the POP3 server that the POP3 adapter is connected to permits multiple concurrent connections to its mailboxes, then we recommend that you ensure high availability for the POP3 adapter by configuring a single POP3 adapter receive handler to run in a BizTalk host instance that has been clustered.</span></span> <span data-ttu-id="3f33b-132">この推奨事項の同じ電子メール メッセージの複数のコピーが同時に取得がされないようにする受信アダプターが POP3 の複数のインスタンスを実行している場合。</span><span class="sxs-lookup"><span data-stu-id="3f33b-132">This recommendation is made to ensure that multiple copies of the same e-mail message are not retrieved simultaneously when running multiple instances of the POP3 receive adapter.</span></span>  
  
## <a name="running-a-receive-adapter-that-supports-ordered-delivery-with-a-clustered-biztalk-host"></a><span data-ttu-id="3f33b-133">クラスター化された BizTalk ホストで順次配送をサポートする受信アダプターを実行する</span><span class="sxs-lookup"><span data-stu-id="3f33b-133">Running a receive adapter that supports ordered delivery with a clustered BizTalk host</span></span>  
 <span data-ttu-id="3f33b-134">MSMQ および MQSeries 統合アダプターにドキュメントを送信する機能を提供する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]受信した順序で。</span><span class="sxs-lookup"><span data-stu-id="3f33b-134">The MSMQ and MQSeries integrated adapters provide the ability to submit documents to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] in the order that they were received.</span></span> <span data-ttu-id="3f33b-135">この機能を正しく実装では、これらのインスタンスが 1 つだけ受信アダプターである必要があります、特定の時点で実行されています。</span><span class="sxs-lookup"><span data-stu-id="3f33b-135">Correct implementation of this functionality requires that only a single instance of these receive adapters be running at any given time.</span></span> <span data-ttu-id="3f33b-136">これらのアダプターの 1 つのインスタンスの高可用性を実現するには、クラスター化された BizTalk ホスト インスタンスで実行するように構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3f33b-136">To provide high availability for a single instance of these adapters, they should be configured to run in a clustered BizTalk host instance.</span></span>