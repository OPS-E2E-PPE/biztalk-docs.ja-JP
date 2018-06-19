---
title: 可用性テストを実行して |Microsoft ドキュメント
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
ms.openlocfilehash: e6f0d9b1cb7b38ab8a1173ee227a8202812048f0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22298306"
---
# <a name="performing-availability-testing"></a><span data-ttu-id="2c381-102">可用性テストを実行します。</span><span class="sxs-lookup"><span data-stu-id="2c381-102">Performing Availability Testing</span></span>
<span data-ttu-id="2c381-103">災害復旧をさまざまなレベルのネットワーク カードのエラー) などの小規模な障害から実稼働サーバーの消失までの範囲の障害から復旧できることを確認するには、システムをテストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2c381-103">You should test your system for disaster recovery to verify its ability to recover from various levels of failure, ranging from small-scale failures (such as a network card failure) to the loss of a production server.</span></span> <span data-ttu-id="2c381-104">災害復旧のテストと、次の手順を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="2c381-104">Your disaster recovery testing should include the following steps:</span></span>  
  
-   <span data-ttu-id="2c381-105">**個々 のハードウェア コンポーネントに障害をテストします。**</span><span class="sxs-lookup"><span data-stu-id="2c381-105">**Test individual hardware component failure.**</span></span>  
  
     <span data-ttu-id="2c381-106">ネットワークまたはディスクなど、個々 のハードウェア コンポーネントの障害から復旧するシステムの機能をテストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2c381-106">You should test the ability of the system to recover from an individual hardware component failure, such as a network or disk.</span></span>  
  
-   <span data-ttu-id="2c381-107">**1 つの BizTalk server のエラーをテストします。**</span><span class="sxs-lookup"><span data-stu-id="2c381-107">**Test single BizTalk server failure.**</span></span>  
  
     <span data-ttu-id="2c381-108">ほとんどの[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]実稼働環境、ホストの処理が実行されている複数のコンピューター間で分散されている[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]1 つの BizTalk グループにします。</span><span class="sxs-lookup"><span data-stu-id="2c381-108">In most [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] production environments, host processing is spread out among multiple computers running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] in a single BizTalk group.</span></span> <span data-ttu-id="2c381-109">ホストのイベントの処理を続行する、BizTalk グループの機能は、グループ内のサーバーのいずれかが失敗する場合</span><span class="sxs-lookup"><span data-stu-id="2c381-109">What is the ability of the BizTalk group to continue host processing in the event one of the servers in the group fails?</span></span>  
  
-   <span data-ttu-id="2c381-110">**クラスター ノードのフェールオーバーをテストします。**</span><span class="sxs-lookup"><span data-stu-id="2c381-110">**Test cluster node failover.**</span></span>  
  
     <span data-ttu-id="2c381-111">高可用性を実現する、Windows クラスタ リングが使用されるかどうか、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベースまたは BizTalk ホスト、クラスター ノードのフェールオーバー機能を確認してください。</span><span class="sxs-lookup"><span data-stu-id="2c381-111">If Windows Clustering is used to provide high availability for the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases or BizTalk Hosts, you should verify cluster node failover functionality.</span></span> <span data-ttu-id="2c381-112">Windows クラスタ リングを使用して、高い可用性を実現する方法の詳細について[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を参照してください[チェックリスト: フォールト トレランスと負荷分散と高可用性の実現](../technical-guides/checklist-providing-high-availability-with-fault-tolerance-or-load-balancing.md)です。</span><span class="sxs-lookup"><span data-stu-id="2c381-112">For more information about using Windows Clustering to provide high availability for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], see [Checklist: Providing High Availability with Fault Tolerance or Load Balancing](../technical-guides/checklist-providing-high-availability-with-fault-tolerance-or-load-balancing.md).</span></span>  
  
-   <span data-ttu-id="2c381-113">**ログ配布を使用して BizTalk Server データベースの復旧をテストします。**</span><span class="sxs-lookup"><span data-stu-id="2c381-113">**Test recovery of BizTalk Server databases using log shipping.**</span></span>  
  
     <span data-ttu-id="2c381-114">回復をことを確認する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース。</span><span class="sxs-lookup"><span data-stu-id="2c381-114">You should verify the recovery of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases.</span></span> <span data-ttu-id="2c381-115">バックアップおよび復元するログ配布の使用の詳細については[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベースを参照してください[新機能は、BizTalk Server ログ配布しますか?](../technical-guides/what-is-biztalk-server-log-shipping.md)このガイドでまたは[ログ配布](http://go.microsoft.com/fwlink/?LinkID=153450)(http://go.microsoft.com/fwlink/?LinkID=153450)。</span><span class="sxs-lookup"><span data-stu-id="2c381-115">For more information about using log shipping to back up and restore [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases, see [What Is BizTalk Server Log Shipping?](../technical-guides/what-is-biztalk-server-log-shipping.md) in this guide or [Log Shipping](http://go.microsoft.com/fwlink/?LinkID=153450) (http://go.microsoft.com/fwlink/?LinkID=153450).</span></span>  
  
     <span data-ttu-id="2c381-116">可用性を高めるために従う必要のある手順のチェックリストについては、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 、災害復旧を使用して環境を参照してください[チェックリスト: 可用性と災害復旧を増やす](../technical-guides/checklist-increasing-availability-with-disaster-recovery.md)です。</span><span class="sxs-lookup"><span data-stu-id="2c381-116">For a checklist of steps that you should follow to increase the availability of a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment using disaster recovery, see [Checklist: Increasing Availability with Disaster Recovery](../technical-guides/checklist-increasing-availability-with-disaster-recovery.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c381-117">参照</span><span class="sxs-lookup"><span data-stu-id="2c381-117">See Also</span></span>  
 [<span data-ttu-id="2c381-118">BizTalk Server の可用性の向上</span><span class="sxs-lookup"><span data-stu-id="2c381-118">Increasing Availability for BizTalk Server</span></span>](../technical-guides/increasing-availability-for-biztalk-server.md)