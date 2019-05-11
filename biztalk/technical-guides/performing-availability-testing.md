---
title: 可用性テストの実行 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 10b543dd-ba85-40da-8c6f-485eddb59158
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bcfc2fcad309e492fd97455cf78f62157e3fd8a4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65291297"
---
# <a name="performing-availability-testing"></a><span data-ttu-id="addec-102">可用性テストの実行</span><span class="sxs-lookup"><span data-stu-id="addec-102">Performing Availability Testing</span></span>
<span data-ttu-id="addec-103">ディザスター リカバリー (ネットワーク カードのエラー) などの小規模な障害から実稼働サーバーの損失に至るまで、障害のさまざまなレベルから回復するには、その機能を確認するには、システムをテストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="addec-103">You should test your system for disaster recovery to verify its ability to recover from various levels of failure, ranging from small-scale failures (such as a network card failure) to the loss of a production server.</span></span> <span data-ttu-id="addec-104">ディザスター リカバリーのテストと、次の手順を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="addec-104">Your disaster recovery testing should include the following steps:</span></span>  
  
- <span data-ttu-id="addec-105">**個々 のハードウェア コンポーネントに障害をテストします。**</span><span class="sxs-lookup"><span data-stu-id="addec-105">**Test individual hardware component failure.**</span></span>  
  
   <span data-ttu-id="addec-106">ネットワークやディスクなど、個々 のハードウェア コンポーネントの障害から回復するシステムの能力をテストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="addec-106">You should test the ability of the system to recover from an individual hardware component failure, such as a network or disk.</span></span>  
  
- <span data-ttu-id="addec-107">**1 つの BizTalk server のエラーをテストします。**</span><span class="sxs-lookup"><span data-stu-id="addec-107">**Test single BizTalk server failure.**</span></span>  
  
   <span data-ttu-id="addec-108">ほとんどの[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]運用環境では、ホストの処理が実行されている複数のコンピューター間で分散されている[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]1 つの BizTalk グループ内。</span><span class="sxs-lookup"><span data-stu-id="addec-108">In most [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] production environments, host processing is spread out among multiple computers running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] in a single BizTalk group.</span></span> <span data-ttu-id="addec-109">失敗、グループ内のサーバーのいずれかのホストのイベントの処理を続行する、BizTalk グループの機能は何ですか。</span><span class="sxs-lookup"><span data-stu-id="addec-109">What is the ability of the BizTalk group to continue host processing in the event one of the servers in the group fails?</span></span>  
  
- <span data-ttu-id="addec-110">**クラスター ノードのフェールオーバーをテストします。**</span><span class="sxs-lookup"><span data-stu-id="addec-110">**Test cluster node failover.**</span></span>  
  
   <span data-ttu-id="addec-111">高可用性を実現する Windows のクラスタ リングを使用するかどうか、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベースまたは BizTalk ホストをクラスター ノードのフェールオーバー機能を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="addec-111">If Windows Clustering is used to provide high availability for the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases or BizTalk Hosts, you should verify cluster node failover functionality.</span></span> <span data-ttu-id="addec-112">Windows クラスタ リングを使用して、高い可用性を実現する方法について[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を参照してください[チェックリスト。フォールト トレランスまたは負荷分散と高可用性を実現する](../technical-guides/checklist-providing-high-availability-with-fault-tolerance-or-load-balancing.md)します。</span><span class="sxs-lookup"><span data-stu-id="addec-112">For more information about using Windows Clustering to provide high availability for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], see [Checklist: Providing High Availability with Fault Tolerance or Load Balancing](../technical-guides/checklist-providing-high-availability-with-fault-tolerance-or-load-balancing.md).</span></span>  
  
- <span data-ttu-id="addec-113">**ログ配布を使用して BizTalk Server データベースの回復をテストします。**</span><span class="sxs-lookup"><span data-stu-id="addec-113">**Test recovery of BizTalk Server databases using log shipping.**</span></span>  
  
   <span data-ttu-id="addec-114">回復を確認する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース。</span><span class="sxs-lookup"><span data-stu-id="addec-114">You should verify the recovery of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases.</span></span> <span data-ttu-id="addec-115">ログ配布を使用してバックアップおよび復元する方法の詳細情報の[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベースを参照してください[内容は、BizTalk Server のログ配布しますか?](../technical-guides/what-is-biztalk-server-log-shipping.md)このガイドでまたは[ログ配布](http://go.microsoft.com/fwlink/?LinkID=153450)(<http://go.microsoft.com/fwlink/?LinkID=153450>)。</span><span class="sxs-lookup"><span data-stu-id="addec-115">For more information about using log shipping to back up and restore [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases, see [What Is BizTalk Server Log Shipping?](../technical-guides/what-is-biztalk-server-log-shipping.md) in this guide or [Log Shipping](http://go.microsoft.com/fwlink/?LinkID=153450) (<http://go.microsoft.com/fwlink/?LinkID=153450>).</span></span>  
  
   <span data-ttu-id="addec-116">可用性を高めるために従う必要のある手順のチェックリストについては、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 、ディザスター リカバリーを使用して環境を参照してください[チェックリスト。ディザスター リカバリーによる可用性の向上](../technical-guides/checklist-increasing-availability-with-disaster-recovery.md)します。</span><span class="sxs-lookup"><span data-stu-id="addec-116">For a checklist of steps that you should follow to increase the availability of a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment using disaster recovery, see [Checklist: Increasing Availability with Disaster Recovery](../technical-guides/checklist-increasing-availability-with-disaster-recovery.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="addec-117">参照</span><span class="sxs-lookup"><span data-stu-id="addec-117">See Also</span></span>  
 [<span data-ttu-id="addec-118">BizTalk Server の可用性の向上</span><span class="sxs-lookup"><span data-stu-id="addec-118">Increasing Availability for BizTalk Server</span></span>](../technical-guides/increasing-availability-for-biztalk-server.md)