---
title: "スケール アウトされた送信ホスト |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "25"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 50659e267731caafe4bad6dabe89944cb16c0c98
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="scaled-out-sending-hosts"></a><span data-ttu-id="3b83c-102">送信ホストのスケールアウト</span><span class="sxs-lookup"><span data-stu-id="3b83c-102">Scaled-Out Sending Hosts</span></span>
<span data-ttu-id="3b83c-103">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の送信機能に高い可用性を確保するには、送信ホストをスケールアウトします。</span><span class="sxs-lookup"><span data-stu-id="3b83c-103">A scaled-out sending host makes sure that the sending functionality in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is highly available.</span></span> <span data-ttu-id="3b83c-104">メッセージを送信するためのホストにコンピューターを追加し、複数の送信ホスト インスタンスを実行することによって冗長性と可用性を高めることができます。</span><span class="sxs-lookup"><span data-stu-id="3b83c-104">If you add multiple computers to a host for sending messages, you can run multiple sending host instances for redundancy and high availability.</span></span>  
  
 <span data-ttu-id="3b83c-105">次の図は、送信ホストのインスタンスを実行する 2 台のコンピューターを使用して、送信ホストの高可用性を実現した [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 環境を示しています。</span><span class="sxs-lookup"><span data-stu-id="3b83c-105">The following figure shows a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] deployment that provides high availability for the sending host by having two computers that are running instances of the sending host.</span></span> <span data-ttu-id="3b83c-106">この図に示されている受信ホストおよび処理ホストの可用性は高くないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="3b83c-106">Note that in this figure the receiving and processing hosts are not highly available.</span></span>  
  
 <span data-ttu-id="3b83c-107">![スケーリング &#45; ホストの送信が](../core/media/tdi-ha-scalesend.gif "TDI_HA_ScaleSend")</span><span class="sxs-lookup"><span data-stu-id="3b83c-107">![Scaled&#45;Out Sending Host](../core/media/tdi-ha-scalesend.gif "TDI_HA_ScaleSend")</span></span>  
  
## <a name="high-availability-for-sending-hosts"></a><span data-ttu-id="3b83c-108">送信ホストの高可用性</span><span class="sxs-lookup"><span data-stu-id="3b83c-108">High Availability for Sending Hosts</span></span>  
 <span data-ttu-id="3b83c-109">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の送信機能は、ホストとデータを完全に切り離して捉えることができるという意味で処理機能に似ています。</span><span class="sxs-lookup"><span data-stu-id="3b83c-109">Sending functionality in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is similar to processing functionality in the sense that neither of these activities requires any association between host and data.</span></span> <span data-ttu-id="3b83c-110">処理の対象となるメッセージをメッセージ ボックス データベースから取得する処理ホスト インスタンスと同様に、送信ホスト インスタンスも、送信するメッセージをメッセージ ボックス データベースから取得します。</span><span class="sxs-lookup"><span data-stu-id="3b83c-110">Just as any processing host instance can retrieve messages from the MessageBox database and process them, any sending host instance can retrieve messages from the MessageBox database and send them.</span></span> <span data-ttu-id="3b83c-111">したがって、送信ホストの高可用性を実現する際は、処理ホストの高可用性を実現するときと同じ手法を使用できることになります。</span><span class="sxs-lookup"><span data-stu-id="3b83c-111">Therefore, providing high availability for the sending hosts means that you use the same techniques as for providing high availability for the processing hosts.</span></span>  
  
## <a name="scaling-the-biztalk-server-send-adapters"></a><span data-ttu-id="3b83c-112">BizTalk Server 送信アダプターの拡張</span><span class="sxs-lookup"><span data-stu-id="3b83c-112">Scaling the BizTalk Server Send Adapters</span></span>  
  
### <a name="high-availability-for-the-msmq-send-adapter"></a><span data-ttu-id="3b83c-113">MSMQ 送信アダプターの高可用性</span><span class="sxs-lookup"><span data-stu-id="3b83c-113">High Availability for the MSMQ Send Adapter</span></span>  
 <span data-ttu-id="3b83c-114">MSMQ 送信アダプターの高可用性を確保するためには、MSMQ サービスをクラスター化し、このクラスター化した MSMQ サービスと同じグループとなるように BizTalk ホストをクラスター化して構成します。さらに、MSMQ 送信ハンドラーが、このクラスター化された BizTalk ホストで実行されるように構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3b83c-114">To provide high availability for the MSMQ send adapter you should cluster the MSMQ service, cluster a BizTalk host in the same group as the clustered MSMQ service, and configure the MSMQ send handler to run in this clustered BizTalk host.</span></span> <span data-ttu-id="3b83c-115">MSMQ アダプターによって開始されたトランザクションの送信の一貫性を確保するは、これを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="3b83c-115">This should be done to ensure the consistency of transactional sends initiated by the MSMQ adapter.</span></span> <span data-ttu-id="3b83c-116">詳細については、次を参照してください。[化されたクラスター化されたホストでアダプター ハンドラーの実行に関する考慮事項](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md)です。</span><span class="sxs-lookup"><span data-stu-id="3b83c-116">For more information see [Considerations for Running Adapter Handlers within a Clustered Host](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md).</span></span>  
  
### <a name="high-availability-for-the-windows-sharepoint-services-send-adapter"></a><span data-ttu-id="3b83c-117">Windows SharePoint Services 送信アダプターの高可用性</span><span class="sxs-lookup"><span data-stu-id="3b83c-117">High Availability for the Windows SharePoint Services Send Adapter</span></span>  
 <span data-ttu-id="3b83c-118">Windows SharePoint Services 送信アダプターに高可用性を確保するには、送信ホストに複数のコンピューターを追加し、各ホスト コンピューターの送信ポートで、同じドキュメント ライブラリが参照されるように構成します。</span><span class="sxs-lookup"><span data-stu-id="3b83c-118">To provide high availability for the Windows SharePoint Services send adapter, add multiple computers to the send host with the send port on each host computer referencing the same document library.</span></span> <span data-ttu-id="3b83c-119">Windows SharePoint Services アダプターは、SharePoint コンピューターに BizTalk がインストールされている Windows SharePoint Services web サービスを呼び出すことによって SharePoint にメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="3b83c-119">The Windows SharePoint Services adapter sends messages to SharePoint by calling into the Windows SharePoint Services web service installed by BizTalk on the SharePoint machine.</span></span> <span data-ttu-id="3b83c-120">BizTalk Server は、SharePoint の NLB 環境を指す HTTP URL に同じメッセージをプッシュする複数のホスト インスタンスで、同じ送信ポートを実行することによって、SharePoint 受信アダプターの高可用性を提供します。</span><span class="sxs-lookup"><span data-stu-id="3b83c-120">BizTalk Server provides high availability for the SharePoint send adapter by letting you run the same send ports on multiple host instances that push messages to the same HTTP URL pointing to a SharePoint NLB installation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b83c-121">参照</span><span class="sxs-lookup"><span data-stu-id="3b83c-121">See Also</span></span>  
 <span data-ttu-id="3b83c-122">[BizTalk ホストの高可用性を実現します。](../core/providing-high-availability-for-biztalk-hosts.md) </span><span class="sxs-lookup"><span data-stu-id="3b83c-122">[Providing High Availability for BizTalk Hosts](../core/providing-high-availability-for-biztalk-hosts.md) </span></span>  
 [<span data-ttu-id="3b83c-123">クラスター化されたホストでのアダプター ハンドラーの実行に関する注意点</span><span class="sxs-lookup"><span data-stu-id="3b83c-123">Considerations for Running Adapter Handlers within a Clustered Host</span></span>](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md)