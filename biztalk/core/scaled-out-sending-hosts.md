---
title: スケール アウトされた送信ホスト |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- hosts, sending
- FTP adapters, high availability
- EDI adapters, high availability
- hosts, high availability
- hosts, availability
- Windows SharePoint Services adapters, high availability
- scaling, hosts
- hosts, clustering
- scaling, adapters
- high availability, hosts
- clustering, hosts
- MSMQ adapters, high availability
- hosts, planning
- hosts, scaling
- adapters, scaling
ms.assetid: a3d79e0b-8c1e-471c-88e2-623600dfd81a
caps.latest.revision: 25
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 80fcc73aa4d0f2d65a097bd47d06fc75305abdc3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65309066"
---
# <a name="scaled-out-sending-hosts"></a><span data-ttu-id="715d0-102">スケール アウトされた送信ホスト</span><span class="sxs-lookup"><span data-stu-id="715d0-102">Scaled-Out Sending Hosts</span></span>
<span data-ttu-id="715d0-103">スケール アウトされた送信ホストにより、送信機能に[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]は高可用性。</span><span class="sxs-lookup"><span data-stu-id="715d0-103">A scaled-out sending host makes sure that the sending functionality in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is highly available.</span></span> <span data-ttu-id="715d0-104">メッセージを送信するために、ホストを複数のコンピューターを追加する場合は、冗長性と高可用性のための複数の送信元ホスト インスタンスを実行できます。</span><span class="sxs-lookup"><span data-stu-id="715d0-104">If you add multiple computers to a host for sending messages, you can run multiple sending host instances for redundancy and high availability.</span></span>  
  
 <span data-ttu-id="715d0-105">次に示します、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]展開を送信ホストのインスタンスを実行する 2 台のコンピューターを使用して、送信ホストの高可用性を実現します。</span><span class="sxs-lookup"><span data-stu-id="715d0-105">The following figure shows a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] deployment that provides high availability for the sending host by having two computers that are running instances of the sending host.</span></span> <span data-ttu-id="715d0-106">この図では、受信および処理ホストができないこと高可用性に注意してください。</span><span class="sxs-lookup"><span data-stu-id="715d0-106">Note that in this figure the receiving and processing hosts are not highly available.</span></span>  
  
 <span data-ttu-id="715d0-107">![スケール&#45;ホストの送信が](../core/media/tdi-ha-scalesend.gif "TDI_HA_ScaleSend")</span><span class="sxs-lookup"><span data-stu-id="715d0-107">![Scaled&#45;Out Sending Host](../core/media/tdi-ha-scalesend.gif "TDI_HA_ScaleSend")</span></span>  
  
## <a name="high-availability-for-sending-hosts"></a><span data-ttu-id="715d0-108">送信ホストの高可用性</span><span class="sxs-lookup"><span data-stu-id="715d0-108">High Availability for Sending Hosts</span></span>  
 <span data-ttu-id="715d0-109">送信機能[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]はどちらもこれらのアクティビティのホストとデータの関連付けが必要であるという意味で処理機能に似ています。</span><span class="sxs-lookup"><span data-stu-id="715d0-109">Sending functionality in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is similar to processing functionality in the sense that neither of these activities requires any association between host and data.</span></span> <span data-ttu-id="715d0-110">処理ホスト インスタンスでは、メッセージ ボックス データベースからメッセージを取得でき、それらを処理することと同様、送信ホスト インスタンスもはメッセージ ボックス データベースからメッセージを取得し、送ります。</span><span class="sxs-lookup"><span data-stu-id="715d0-110">Just as any processing host instance can retrieve messages from the MessageBox database and process them, any sending host instance can retrieve messages from the MessageBox database and send them.</span></span> <span data-ttu-id="715d0-111">そのため、送信ホストの高可用性を実現するには、処理ホストの高可用性を実現する場合と同じ手法を使用することを意味します。</span><span class="sxs-lookup"><span data-stu-id="715d0-111">Therefore, providing high availability for the sending hosts means that you use the same techniques as for providing high availability for the processing hosts.</span></span>  
  
## <a name="scaling-the-biztalk-server-send-adapters"></a><span data-ttu-id="715d0-112">BizTalk Server 送信アダプターの拡張</span><span class="sxs-lookup"><span data-stu-id="715d0-112">Scaling the BizTalk Server Send Adapters</span></span>  
  
### <a name="high-availability-for-the-msmq-send-adapter"></a><span data-ttu-id="715d0-113">送信アダプター、MSMQ 用の高可用性</span><span class="sxs-lookup"><span data-stu-id="715d0-113">High Availability for the MSMQ Send Adapter</span></span>  
 <span data-ttu-id="715d0-114">MSMQ サービスをクラスター化、クラスターのクラスター化された MSMQ サービスと同じグループ内の BizTalk ホストおよび構成する必要があります、MSMQ 送信アダプターの高可用性を実現するには、MSMQ の送信ハンドラーをこのクラスター化された BizTalk ホストで実行します。</span><span class="sxs-lookup"><span data-stu-id="715d0-114">To provide high availability for the MSMQ send adapter you should cluster the MSMQ service, cluster a BizTalk host in the same group as the clustered MSMQ service, and configure the MSMQ send handler to run in this clustered BizTalk host.</span></span> <span data-ttu-id="715d0-115">これは、MSMQ アダプターによって開始されたトランザクションの送信の一貫性を確保する実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="715d0-115">This should be done to ensure the consistency of transactional sends initiated by the MSMQ adapter.</span></span> <span data-ttu-id="715d0-116">詳細については、次を参照してください。[されたクラスター化されたホストでアダプター ハンドラーの実行に関する考慮事項](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md)します。</span><span class="sxs-lookup"><span data-stu-id="715d0-116">For more information see [Considerations for Running Adapter Handlers within a Clustered Host](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md).</span></span>  
  
### <a name="high-availability-for-the-windows-sharepoint-services-send-adapter"></a><span data-ttu-id="715d0-117">送信アダプター、Windows SharePoint Services の高可用性</span><span class="sxs-lookup"><span data-stu-id="715d0-117">High Availability for the Windows SharePoint Services Send Adapter</span></span>  
 <span data-ttu-id="715d0-118">Windows SharePoint Services 送信アダプターの高可用性を実現するには、同じドキュメント ライブラリを参照する各ホスト コンピューター上の送信ポートで送信ホストに複数のコンピューターを追加します。</span><span class="sxs-lookup"><span data-stu-id="715d0-118">To provide high availability for the Windows SharePoint Services send adapter, add multiple computers to the send host with the send port on each host computer referencing the same document library.</span></span> <span data-ttu-id="715d0-119">Windows SharePoint Services アダプターは、SharePoint コンピューターに BizTalk によってインストールされた Windows SharePoint Services web サービスを呼び出すことによって、SharePoint にメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="715d0-119">The Windows SharePoint Services adapter sends messages to SharePoint by calling into the Windows SharePoint Services web service installed by BizTalk on the SharePoint machine.</span></span> <span data-ttu-id="715d0-120">BizTalk Server は、SharePoint の NLB 環境を指す HTTP URL を同じメッセージをプッシュする複数のホスト インスタンスで同じ送信ポートを実行することによって、SharePoint 受信アダプターの高可用性を提供します。</span><span class="sxs-lookup"><span data-stu-id="715d0-120">BizTalk Server provides high availability for the SharePoint send adapter by letting you run the same send ports on multiple host instances that push messages to the same HTTP URL pointing to a SharePoint NLB installation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="715d0-121">参照</span><span class="sxs-lookup"><span data-stu-id="715d0-121">See Also</span></span>  
 <span data-ttu-id="715d0-122">[BizTalk ホストの高可用性を実現します。](../core/providing-high-availability-for-biztalk-hosts.md) </span><span class="sxs-lookup"><span data-stu-id="715d0-122">[Providing High Availability for BizTalk Hosts](../core/providing-high-availability-for-biztalk-hosts.md) </span></span>  
 [<span data-ttu-id="715d0-123">クラスター化されたホストでのアダプター ハンドラーの実行に関する注意点</span><span class="sxs-lookup"><span data-stu-id="715d0-123">Considerations for Running Adapter Handlers within a Clustered Host</span></span>](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md)