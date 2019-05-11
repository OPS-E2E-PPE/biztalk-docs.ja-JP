---
title: ホスト |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- host instances, servers
- hosts, isolated
- host instances, relationships
- hosts, in-process hosts
- servers, hosts
- hosts, host instances
- hosts, relationships
- In-Process BizTalk Host groups
- hosts, about hosts
- hosts, untrusted
- host instances, hosts
- hosts, servers
- hosts
- servers, host instances
- Isolated Host Users group
- hosts, trusted
ms.assetid: d96537e0-e679-407a-8870-34a663acfed9
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9785e734579c88a790f2a07a292fef476be5d6d7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387530"
---
# <a name="hosts"></a><span data-ttu-id="17b76-102">Hosts</span><span class="sxs-lookup"><span data-stu-id="17b76-102">Hosts</span></span>
<span data-ttu-id="17b76-103">BizTalk ホスト オブジェクトとは、0 個以上のランタイム プロセスの論理セットであり、サービスやパイプラインなどの各種アイテムを展開する場所です。</span><span class="sxs-lookup"><span data-stu-id="17b76-103">The BizTalk Host object represents a logical set of zero or more runtime processes in which you can deploy services, pipelines, and other artifacts.</span></span> <span data-ttu-id="17b76-104">ホスト オブジェクトは、展開されたアイテムが物理的に実行されるランタイム インスタンス (0 個以上) の集合でもあります。</span><span class="sxs-lookup"><span data-stu-id="17b76-104">The Host object also represents a collection of runtime instances (zero or more) where the deployed items physically run.</span></span>  
  
 <span data-ttu-id="17b76-105">ホスト (論理コンテナー) を作成した後、そのホストに対し、物理的な BizTalk Server (ホスト インスタンス) を追加できます。</span><span class="sxs-lookup"><span data-stu-id="17b76-105">After you create a host (a logical container), you can add physical BizTalk servers (host instances) to the host.</span></span> <span data-ttu-id="17b76-106">BizTalk Server を 2 回以上同じホストに追加することはできません。</span><span class="sxs-lookup"><span data-stu-id="17b76-106">You cannot add a BizTalk server to the same host more than once.</span></span> <span data-ttu-id="17b76-107">1 つのホスト インスタンスを複数のホストに追加できます。</span><span class="sxs-lookup"><span data-stu-id="17b76-107">A single host instance can be added to multiple hosts.</span></span>  
  
 <span data-ttu-id="17b76-108">項目-アダプター ハンドラー、受信場所 (パイプラインを含む)、およびオーケストレーションに含まれる BizTalk ホストは、次の関数を実行できます。</span><span class="sxs-lookup"><span data-stu-id="17b76-108">Items—such as adapter handlers, receive locations (including pipelines), and orchestrations—contained in BizTalk hosts can perform the following functions:</span></span>  
  
- <span data-ttu-id="17b76-109">**受信**します。</span><span class="sxs-lookup"><span data-stu-id="17b76-109">**Receiving**.</span></span> <span data-ttu-id="17b76-110">受信場所から取得された後のメッセージに対して初期処理を実行します。</span><span class="sxs-lookup"><span data-stu-id="17b76-110">These items do the initial processing of messages after they are picked up in a receive location.</span></span> <span data-ttu-id="17b76-111">受信機能 (受信場所やパイプラインなど) をつかさどるホストはセキュリティの処理境界として機能し、メッセージのデコードや復号化は、そのホスト内のパイプラインで行われます。</span><span class="sxs-lookup"><span data-stu-id="17b76-111">When a host contains a receiving item, such as a receive location or pipeline, it acts as a security boundary, and the message decoding and decrypting occurs in a pipeline within the host.</span></span>  
  
- <span data-ttu-id="17b76-112">**送信**します。</span><span class="sxs-lookup"><span data-stu-id="17b76-112">**Sending**.</span></span> <span data-ttu-id="17b76-113">送信ポートに送られる前のメッセージに対して最終処理を実行します。</span><span class="sxs-lookup"><span data-stu-id="17b76-113">These items do the final processing of messages before they are sent out to the send port.</span></span> <span data-ttu-id="17b76-114">送信機能 (送信ポートやパイプラインなど) をつかさどるホストはセキュリティの処理境界として機能し、メッセージの署名や暗号化は、そのホスト内のパイプラインで行われます。</span><span class="sxs-lookup"><span data-stu-id="17b76-114">When a host contains a sending item, such as a send port or pipeline, the host acts as a security boundary, and the message signing and encryption occurs in a pipeline within the host.</span></span>  
  
- <span data-ttu-id="17b76-115">**処理**します。</span><span class="sxs-lookup"><span data-stu-id="17b76-115">**Processing**.</span></span> <span data-ttu-id="17b76-116">オーケストレーションの命令に基づいてメッセージを処理します。</span><span class="sxs-lookup"><span data-stu-id="17b76-116">These items process messages based on the instructions in an orchestration.</span></span>  
  
  <span data-ttu-id="17b76-117">1 つの BizTalk ホストに、メッセージの受信、送信、および処理の機能をすべて割り当てることもできます。</span><span class="sxs-lookup"><span data-stu-id="17b76-117">One BizTalk Host can contain items that receive, send, and process messages.</span></span> <span data-ttu-id="17b76-118">ただし、セキュリティの処理境界を設け、管理を容易にするには、機能ごとに異なるホストを作成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="17b76-118">It is recommended that you create different hosts for each function to create security boundaries and facilitate management.</span></span> <span data-ttu-id="17b76-119">特に、処理と送受信には異なるホストを使用し、信頼済みのアイテムとそうでないアイテムを分離してください。</span><span class="sxs-lookup"><span data-stu-id="17b76-119">In particular, it is recommended that you use different hosts for processing and for receive/send, and that you separate trusted and non-trusted items.</span></span>  
  
  <span data-ttu-id="17b76-120">次の図に、サーバー、ホスト、およびホスト インスタンスの関係を示します。</span><span class="sxs-lookup"><span data-stu-id="17b76-120">The following figure shows the relationship between servers, hosts, and host instances.</span></span>  
  
  <span data-ttu-id="17b76-121">![ホスト、ホスト インスタンス、およびサーバーの関係](../core/media/ebiz-ops-adm01.gif "ebiz_ops_adm01")</span><span class="sxs-lookup"><span data-stu-id="17b76-121">![Hosts, host instances, and server relationships](../core/media/ebiz-ops-adm01.gif "ebiz_ops_adm01")</span></span>  
  <span data-ttu-id="17b76-122">ホスト、ホスト インスタンス、およびサーバー間のリレーションシップ</span><span class="sxs-lookup"><span data-stu-id="17b76-122">Relationship between hosts, host instances, and servers</span></span>  
  
  <span data-ttu-id="17b76-123">ホスト インスタンスの詳細については、次を参照してください。[ホスト インスタンス](../core/host-instances.md)します。</span><span class="sxs-lookup"><span data-stu-id="17b76-123">For more information about Host Instances, see [Host Instances](../core/host-instances.md).</span></span>  
  
  <span data-ttu-id="17b76-124">物理的な構成とホストされているアダプターの種類に基づきはホストの 2 つの種類があります。 インプロセス ホストと分離ホスト。</span><span class="sxs-lookup"><span data-stu-id="17b76-124">Based on the physical configuration and type of adapter hosted, there are two types of hosts: in-process hosts and isolated hosts.</span></span>  
  
## <a name="in-process-hosts"></a><span data-ttu-id="17b76-125">インプロセス ホスト</span><span class="sxs-lookup"><span data-stu-id="17b76-125">In-process Hosts</span></span>  
 <span data-ttu-id="17b76-126">インプロセス ホストとは、管理者が Windows Management Instrumentation (WMI) および BizTalk 管理コンソールを使用して作成や削除を行い、完全に管理するサービス インスタンスです。</span><span class="sxs-lookup"><span data-stu-id="17b76-126">In-process hosts represent service instances that an administrator creates, deletes, and fully controls with Windows Management Instrumentation (WMI) and the BizTalk Administration Console.</span></span>  
  
 <span data-ttu-id="17b76-127">インプロセス ホストの特性は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="17b76-127">In-process hosts have the following characteristics:</span></span>  
  
- <span data-ttu-id="17b76-128">インプロセス ホストには任意のオーケストレーションを参加させることができます。</span><span class="sxs-lookup"><span data-stu-id="17b76-128">You can enlist any orchestration into an in-process host.</span></span>  
  
- <span data-ttu-id="17b76-129">インプロセス ホストは送信ハンドラーをホストできます。</span><span class="sxs-lookup"><span data-stu-id="17b76-129">An in-process host can host any send handler.</span></span>  
  
- <span data-ttu-id="17b76-130">インプロセス ホストでは、SOAP および HTTP を除く任意の受信ハンドラーをホストできます。</span><span class="sxs-lookup"><span data-stu-id="17b76-130">An in-process host can host any of the receive handlers except for SOAP and HTTP:</span></span>  
  
  -   <span data-ttu-id="17b76-131">FILE</span><span class="sxs-lookup"><span data-stu-id="17b76-131">FILE</span></span>  
  
  -   <span data-ttu-id="17b76-132">FTP</span><span class="sxs-lookup"><span data-stu-id="17b76-132">FTP</span></span>  
  
  -   <span data-ttu-id="17b76-133">MQSeries</span><span class="sxs-lookup"><span data-stu-id="17b76-133">MQSeries</span></span>  
  
  -   <span data-ttu-id="17b76-134">MSMQ (MSMQ)</span><span class="sxs-lookup"><span data-stu-id="17b76-134">MSMQ</span></span>  
  
  -   <span data-ttu-id="17b76-135">POP3</span><span class="sxs-lookup"><span data-stu-id="17b76-135">POP3</span></span>  
  
  -   <span data-ttu-id="17b76-136">SQL</span><span class="sxs-lookup"><span data-stu-id="17b76-136">SQL</span></span>  
  
  -   <span data-ttu-id="17b76-137">Windows SharePoint Services</span><span class="sxs-lookup"><span data-stu-id="17b76-137">Windows SharePoint Services</span></span>  
  
- <span data-ttu-id="17b76-138">作成する最初のインプロセス ホストを[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]デプロイが、**既定ホスト**し、それを削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="17b76-138">The first in-process host you create in a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] deployment is the **default host** and you cannot delete it.</span></span> <span data-ttu-id="17b76-139">BizTalk メッセージ キュー アダプターでは、静的なハンドラー構成に既定のホストを使用します。</span><span class="sxs-lookup"><span data-stu-id="17b76-139">The BizTalk Message Queuing adapter uses the default host for static handler configuration.</span></span> <span data-ttu-id="17b76-140">アダプターを追加すると、既定のホストの送受信ポートが自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="17b76-140">Adding an adapter automatically creates receive and send ports for the default host.</span></span>  
  
## <a name="isolated-hosts"></a><span data-ttu-id="17b76-141">分離ホスト</span><span class="sxs-lookup"><span data-stu-id="17b76-141">Isolated Hosts</span></span>  
 <span data-ttu-id="17b76-142">分離ホストとは、ソリューション開発者がプログラムによって作成、削除、および管理を行うサービス インスタンスです。</span><span class="sxs-lookup"><span data-stu-id="17b76-142">Isolated hosts represent service instances that a solutions developer programmatically creates, deletes, and controls.</span></span> <span data-ttu-id="17b76-143">管理者は WMI および BizTalk 管理コンソールを使用して、これらのホストを設定します (たとえば、ホスト サービス アカウントや信頼されている認証を設定します)。</span><span class="sxs-lookup"><span data-stu-id="17b76-143">An administrator uses WMI and the BizTalk Administration Console to configure these hosts (for example, to configure the host service account and authentication trust).</span></span>  
  
 <span data-ttu-id="17b76-144">分離ホストは主に、通常の BizTalk Server ランタイム プロセスの外部で実行する必要があるアダプターをホストします。</span><span class="sxs-lookup"><span data-stu-id="17b76-144">Isolated hosts primarily host adapters that must run outside of the normal BizTalk Server runtime process.</span></span> <span data-ttu-id="17b76-145">たとえば、分離ホストを使用して、ISAPI 拡張や ASP.NET などの外部プロセス用のアダプターをホストします。</span><span class="sxs-lookup"><span data-stu-id="17b76-145">For example, you use isolated hosts to host adapters for external processes such as ISAPI extensions and ASP.NET.</span></span>  
  
 <span data-ttu-id="17b76-146">分離ホストの特性は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="17b76-146">Isolated hosts have the following characteristics:</span></span>  
  
-   <span data-ttu-id="17b76-147">分離ホストには、オーケストレーションを参加させることができません。</span><span class="sxs-lookup"><span data-stu-id="17b76-147">You cannot enlist orchestrations into an isolated host.</span></span>  
  
-   <span data-ttu-id="17b76-148">分離ホストは送信ハンドラーをホストできません。</span><span class="sxs-lookup"><span data-stu-id="17b76-148">An isolated host cannot host send handlers.</span></span>  
  
-   <span data-ttu-id="17b76-149">分離ホストは、HTTP/S アダプターおよび SOAP アダプター (分離タイプ アダプター) に関連付けられている受信ハンドラーのみをホストできます。</span><span class="sxs-lookup"><span data-stu-id="17b76-149">An isolated host can host only the receive handlers associated with HTTP/S and SOAP adapters (the isolated-type adapters).</span></span>  
  
-   <span data-ttu-id="17b76-150">分離ホストは追跡機能をホストできません。</span><span class="sxs-lookup"><span data-stu-id="17b76-150">An isolated host cannot host tracking.</span></span>  
  
-   <span data-ttu-id="17b76-151">分離ホストは既定のホストとして使用できません。</span><span class="sxs-lookup"><span data-stu-id="17b76-151">An isolated host cannot be the default host.</span></span>  
  
-   <span data-ttu-id="17b76-152">分離ホストの状態は常に**状態を確認できない**します。</span><span class="sxs-lookup"><span data-stu-id="17b76-152">The status of an isolated host is always **Status Unavailable**.</span></span> <span data-ttu-id="17b76-153">これは、BizTalk Server から外部プロセスの状態情報にアクセスできないからです。</span><span class="sxs-lookup"><span data-stu-id="17b76-153">BizTalk Server does not access the status information for external processes.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="17b76-154">ホスト インスタンスは、同じセキュリティ設定 (信頼済みの認証) を共有している限り、同じサービス アカウントを共有できます。</span><span class="sxs-lookup"><span data-stu-id="17b76-154">Host instances can share the same service account as long as they share the same security configuration (authentication trust).</span></span>  
  
## <a name="trusted-and-untrusted-hosts"></a><span data-ttu-id="17b76-155">信頼済みのホストと信頼されていないホスト</span><span class="sxs-lookup"><span data-stu-id="17b76-155">Trusted and Untrusted Hosts</span></span>  
 <span data-ttu-id="17b76-156">BizTalk Server では、認証が信頼済みであると確認されたホストは、メッセージ ボックス データベースへキュー送信するときに、メッセージの送信者がこのホスト以外のエンティティであると示すことができます。</span><span class="sxs-lookup"><span data-stu-id="17b76-156">BizTalk Server enables hosts identified as authentication trusted to indicate that the sender of a message that the trusted host is queuing to the MessageBox database is an entity other than the trusted host itself.</span></span> <span data-ttu-id="17b76-157">信頼済み認証の主な目的は、パイプラインが製品 ID (PID) を解決し、認証や送信側の解決に使用されるサービスにその PID を渡して、オーケストレーション アクションの認証に使用されるサービスに送信者の Windows セキュリティ ID (SSID) を送信できるようにすることです。</span><span class="sxs-lookup"><span data-stu-id="17b76-157">The primary purposes of authentication trust are to enable pipelines to resolve to a Product ID (PID) and pass that PID along to consuming services for use in authorization and outbound party resolution, and to enable the transmission of the sender Windows Security ID (SSID) along to consuming services for use in orchestration action authorization.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17b76-158">参照</span><span class="sxs-lookup"><span data-stu-id="17b76-158">See Also</span></span>  
 <span data-ttu-id="17b76-159">[ホスト インスタンス](../core/host-instances.md) </span><span class="sxs-lookup"><span data-stu-id="17b76-159">[Host Instances](../core/host-instances.md) </span></span>  
 [<span data-ttu-id="17b76-160">BizTalk ホストとホスト インスタンスの管理</span><span class="sxs-lookup"><span data-stu-id="17b76-160">Managing BizTalk Hosts and Host Instances</span></span>](../core/managing-biztalk-hosts-and-host-instances.md)  
 [<span data-ttu-id="17b76-161">エンティティ</span><span class="sxs-lookup"><span data-stu-id="17b76-161">Entities</span></span>](../core/entities.md)