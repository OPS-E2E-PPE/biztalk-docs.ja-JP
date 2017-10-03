---
title: "受信ホストをクラスタ リング |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 93544f39-836f-4a4f-9587-230bfa3a9d4e
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 876cdb5f3740e5f06d00a536e1459c64ac886d89
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="clustering-receiving-hosts"></a><span data-ttu-id="2178e-102">受信ホストをクラスタ リング</span><span class="sxs-lookup"><span data-stu-id="2178e-102">Clustering Receiving Hosts</span></span>
[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]<span data-ttu-id="2178e-103">BizTalk ホスト内のクラスター リソースとして構成できるようにする機能を提供する[!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)]クラスター グループ。</span><span class="sxs-lookup"><span data-stu-id="2178e-103"> provides functionality that allows you to configure a BizTalk Host as a clustered resource within a [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] cluster group.</span></span> <span data-ttu-id="2178e-104">ホスト クラスターのサポートをサポートする受信高可用性を統合 BizTalk アダプターを複数のホスト インスタンスで、同時が実行されない、FTP 受信ハンドラーなど、特定の状況では、POP3 受信ハンドラーに提供されます。</span><span class="sxs-lookup"><span data-stu-id="2178e-104">Host cluster support is provided to support high availability for integrated BizTalk receive adapters that should not be run in multiple host instances simultaneously, such as the FTP receive handler or, under certain circumstances, the POP3 receive handler.</span></span> <span data-ttu-id="2178e-105">MSMQ サービスのクラスター化が必要となるような状況でも、MSMQ アダプターによって送受信されたメッセージについて、トランザクションの一貫性を確実に保つことができます。</span><span class="sxs-lookup"><span data-stu-id="2178e-105">Host cluster support is also provided to ensure transactional consistency for messages sent or received by the MSMQ adapter in scenarios that require that the MSMQ service is clustered.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2178e-106">ホスト クラスタ リングはでのみ使用可能な[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]Enterprise Edition。</span><span class="sxs-lookup"><span data-stu-id="2178e-106">Host clustering is available only with [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] Enterprise Edition.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2178e-107">前に、クラスター化できるは、BizTalk ホストを構成には、少なくとも 2 つ[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]のメンバーとして、BizTalk グループ内のコンピューター、[!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)]クラスター。</span><span class="sxs-lookup"><span data-stu-id="2178e-107">Before you can cluster a BizTalk Host you must have configured at least two [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computers in a BizTalk group as members of a [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] cluster.</span></span> <span data-ttu-id="2178e-108">構成の詳細については、[!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)]クラスターは、「 [、、Windows Server 2008 のクラスタ リング ドキュメント、ホワイト ペーパーは、web キャスト グループ](http://go.microsoft.com/fwlink/?LinkId=156818)(http://go.microsoft.com/fwlink/?LinkId=156818).</span><span class="sxs-lookup"><span data-stu-id="2178e-108">For more information about configuring a [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] cluster, see [Windows Server 2008 Clustering Documents, Whitepapers, Webcasts, Groups](http://go.microsoft.com/fwlink/?LinkId=156818) (http://go.microsoft.com/fwlink/?LinkId=156818).</span></span>  
  
 <span data-ttu-id="2178e-109">BizTalk ホストのクラスター サポートを統合 BizTalk アダプターのうち 5 つの高可用性を実現する使用可能な: FTP アダプター、MSMQ アダプター、POP3 アダプター、SQL アダプターおよび SAP アダプター。</span><span class="sxs-lookup"><span data-stu-id="2178e-109">BizTalk Host cluster support is available to provide high availability for five of the integrated BizTalk adapters: the FTP adapter, the MSMQ adapter, the POP3 adapter, the SQL adapter, and the SAP adapter.</span></span> <span data-ttu-id="2178e-110">また、順次配送の目的でアダプターの単一インスタンスを実行する場合に、ホスト クラスター サポートを利用して高い可用性を実現できます。</span><span class="sxs-lookup"><span data-stu-id="2178e-110">Host cluster support is also provided so that there is high availability for running a single instance of an adapter for purposes of ordered delivery.</span></span>  
  
 <span data-ttu-id="2178e-111">すべての BizTalk アダプター ハンドラーは、クラスター化されたホストで実行できますが、以下の説明に従って以外のクラスター ホストでアダプター ハンドラーの実行からの利点はありません。</span><span class="sxs-lookup"><span data-stu-id="2178e-111">All of the BizTalk adapter handlers can be run in a clustered host, but there is no benefit from running adapter handlers in a clustered host except as described below.</span></span> <span data-ttu-id="2178e-112">処理の要件には、以下のセクションで説明するシナリオのいずれかが含まれている場合は、クラスター化されたホストでアダプター ハンドラーを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2178e-112">If your processing requirements include any of the scenarios described in the section below, then you should run adapter handlers in a clustered host.</span></span> <span data-ttu-id="2178e-113">設定の詳細な手順について[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]クラスターを参照してください[Improving Fault Tolerance in Windows Server 2008 フェールオーバー クラスターまたは Windows Server 2003 サーバー クラスターを使用して BizTalk Server](http://go.microsoft.com/fwlink/?LinkId=156819) (http://go.microsoft.com/fwlink/?LinkId=156819)。</span><span class="sxs-lookup"><span data-stu-id="2178e-113">For detailed steps of setting up [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] clusters, see [Improving Fault Tolerance in BizTalk Server by Using a Windows Server 2008 Failover Cluster or Windows Server 2003 Server Cluster](http://go.microsoft.com/fwlink/?LinkId=156819) (http://go.microsoft.com/fwlink/?LinkId=156819).</span></span>  
  
## <a name="scenarios-for-running-adapter-handlers-in-clustered-hosts"></a><span data-ttu-id="2178e-114">クラスター化されたホストでアダプター ハンドラーを実行するためのシナリオ</span><span class="sxs-lookup"><span data-stu-id="2178e-114">Scenarios for Running Adapter Handlers in Clustered Hosts</span></span>  
 <span data-ttu-id="2178e-115">処理の要件には、以下に示すシナリオのいずれかが含まれている場合は、クラスター化されたホストでアダプター ハンドラーを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2178e-115">If your processing requirements include any of the scenarios listed below, then you should run adapter handlers in a clustered host.</span></span>  
  
-   <span data-ttu-id="2178e-116">クラスター化された BizTalk ホストで FTP アダプターの受信ハンドラーを実行する</span><span class="sxs-lookup"><span data-stu-id="2178e-116">Running the FTP adapter receive handler within a clustered BizTalk host</span></span>  
  
-   <span data-ttu-id="2178e-117">クラスター化された BizTalk ホストで MSMQ アダプター ハンドラーを実行する</span><span class="sxs-lookup"><span data-stu-id="2178e-117">Running MSMQ adapter handlers within a clustered BizTalk host</span></span>  
  
-   <span data-ttu-id="2178e-118">クラスター化された BizTalk ホストで POP3 アダプターの受信ハンドラーを実行する</span><span class="sxs-lookup"><span data-stu-id="2178e-118">Running the POP3 adapter receive handler within a clustered BizTalk host</span></span>  
  
-   <span data-ttu-id="2178e-119">クラスター化された BizTalk ホストで順次配送をサポートする受信アダプターを実行する</span><span class="sxs-lookup"><span data-stu-id="2178e-119">Running a receive adapter that supports ordered delivery with a clustered BizTalk host</span></span>  
  
 <span data-ttu-id="2178e-120">これらのシナリオの詳細については、次を参照してください。[化されたクラスター化されたホストでアダプター ハンドラーの実行に関する考慮事項](http://go.microsoft.com/fwlink/?LinkId=151284)(http://go.microsoft.com/fwlink/?LinkId=151284)。</span><span class="sxs-lookup"><span data-stu-id="2178e-120">For more information about these scenarios, see [Considerations for Running Adapter Handlers within a Clustered Host](http://go.microsoft.com/fwlink/?LinkId=151284) (http://go.microsoft.com/fwlink/?LinkId=151284).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2178e-121">参照</span><span class="sxs-lookup"><span data-stu-id="2178e-121">See Also</span></span>  
 <span data-ttu-id="2178e-122">[スケール アウト受信ホスト](../technical-guides/scaling-out-receiving-hosts.md) </span><span class="sxs-lookup"><span data-stu-id="2178e-122">[Scaling Out Receiving Hosts](../technical-guides/scaling-out-receiving-hosts.md) </span></span>  
 <span data-ttu-id="2178e-123">[スケール アウト処理の各ホスト](../technical-guides/scaling-out-processing-hosts.md) </span><span class="sxs-lookup"><span data-stu-id="2178e-123">[Scaling Out Processing Hosts](../technical-guides/scaling-out-processing-hosts.md) </span></span>  
 [<span data-ttu-id="2178e-124">スケール アウト送信ホスト</span><span class="sxs-lookup"><span data-stu-id="2178e-124">Scaling Out Sending Hosts</span></span>](../technical-guides/scaling-out-sending-hosts.md)