---
title: クラスター フェールオーバーのシナリオの構成のレビューと SQL Server のテスト |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5dbeb383-5b38-4467-acf8-2a5b244e5fa9
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 86d3b3c91fc4b2fc027ef11ff2f9a0253727eea1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65291226"
---
# <a name="reviewing-and-testing-sql-server-cluster-configuration-for-failover-scenarios"></a><span data-ttu-id="c36e9-102">レビューとテスト フェールオーバーのシナリオに SQL Server クラスターの構成</span><span class="sxs-lookup"><span data-stu-id="c36e9-102">Reviewing and Testing SQL Server Cluster Configuration for Failover Scenarios</span></span>
<span data-ttu-id="c36e9-103">Windows クラスタ リングと SQL Server を使用すると、1 つまたは複数の SQL Server インスタンスを「アクティブ」で実行されて、クラスターの各ノードのアクティブ/アクティブ モードで SQL Server を実行できます。</span><span class="sxs-lookup"><span data-stu-id="c36e9-103">Windows Clustering and SQL Server allow you to run SQL Server in Active/Active mode where each node of the cluster is “active” and running one or more SQL Server instances.</span></span> <span data-ttu-id="c36e9-104">これは、ようにすると、たとえば、1 つのノードとその他のすべてのメッセージ ボックス データベースが[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]他のノード上のデータベース。</span><span class="sxs-lookup"><span data-stu-id="c36e9-104">This would allow you, for example, to have the MessageBox database on one node and all other [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases on the other node.</span></span> <span data-ttu-id="c36e9-105">これにより、クラスターのハードウェア使用率を最大化することができます。</span><span class="sxs-lookup"><span data-stu-id="c36e9-105">This allows you to maximize cluster hardware usage.</span></span>  
  
 <span data-ttu-id="c36e9-106">ただし、この構成を使用する場合、各ノードが SQL Server クラスター ノードのフェールオーバー中ですべての SQL Server インスタンスの負荷を処理できる同時にことを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c36e9-106">If you use this configuration, however, you must verify that each node can simultaneously handle the load of all SQL Server instances during a SQL Server cluster node failover.</span></span>  
  
## <a name="evaluating-failover-for-an-activeactive-cluster"></a><span data-ttu-id="c36e9-107">アクティブ/アクティブ クラスターのフェールオーバーを評価します。</span><span class="sxs-lookup"><span data-stu-id="c36e9-107">Evaluating Failover for an Active/Active Cluster</span></span>  
 <span data-ttu-id="c36e9-108">1 つのノードが SQL Server クラスター ノードのフェールオーバーが発生した場合、すべての SQL Server インスタンスの負荷を処理できることを確認するときの考慮事項は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c36e9-108">Considerations when verifying that a single node can handle the load of all SQL Server instances in the event of a SQL Server cluster node failover include:</span></span>  
  
- <span data-ttu-id="c36e9-109">フェールオーバー ノードには十分な CPU リソースがありますか。</span><span class="sxs-lookup"><span data-stu-id="c36e9-109">Does the failover node have sufficient CPU resources?</span></span>  
  
- <span data-ttu-id="c36e9-110">フェールオーバー ノードに十分なメモリがあるでしょうか。</span><span class="sxs-lookup"><span data-stu-id="c36e9-110">Does the failover node have sufficient memory?</span></span>  
  
- <span data-ttu-id="c36e9-111">十分なネットワーク帯域幅はありますか。</span><span class="sxs-lookup"><span data-stu-id="c36e9-111">Is there sufficient network bandwidth?</span></span>  
  
- <span data-ttu-id="c36e9-112">フェールオーバー ノードでより大きなディスク I/O の競合を処理できますか。</span><span class="sxs-lookup"><span data-stu-id="c36e9-112">Can the failover node handle the increased disk I/O contention?</span></span>  
  
  <span data-ttu-id="c36e9-113">フェールオーバーをテストするときに、次のシナリオを評価する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c36e9-113">The following scenarios should be evaluated when testing failover:</span></span>  
  
- <span data-ttu-id="c36e9-114">アクティブ サーバー上の電源障害</span><span class="sxs-lookup"><span data-stu-id="c36e9-114">Power failure on the active server</span></span>  
  
- <span data-ttu-id="c36e9-115">パッシブのサーバーで電源障害</span><span class="sxs-lookup"><span data-stu-id="c36e9-115">Power failure on the passive server</span></span>  
  
- <span data-ttu-id="c36e9-116">ディスクの接続の切断</span><span class="sxs-lookup"><span data-stu-id="c36e9-116">Loss of disk connection</span></span>  
  
- <span data-ttu-id="c36e9-117">アクティブなノードでパブリック ネットワーク接続を解除</span><span class="sxs-lookup"><span data-stu-id="c36e9-117">Broken public network connection on the Active node</span></span>  
  
- <span data-ttu-id="c36e9-118">アクティブなノードでプライベート ネットワーク接続を解除</span><span class="sxs-lookup"><span data-stu-id="c36e9-118">Broken private network connection on the Active node</span></span>  
  
- <span data-ttu-id="c36e9-119">パッシブ ノードでパブリック ネットワーク接続を解除</span><span class="sxs-lookup"><span data-stu-id="c36e9-119">Broken public network connection on the Passive node</span></span>  
  
- <span data-ttu-id="c36e9-120">パッシブ ノードでのプライベート ネットワーク接続の解除</span><span class="sxs-lookup"><span data-stu-id="c36e9-120">Broken private network connection on the Passive node</span></span>  
  
- <span data-ttu-id="c36e9-121">失敗した SQL Server サービス</span><span class="sxs-lookup"><span data-stu-id="c36e9-121">Failed SQL Server service</span></span>  
  
- <span data-ttu-id="c36e9-122">失敗した SQL Server エージェント サービス</span><span class="sxs-lookup"><span data-stu-id="c36e9-122">Failed SQL Server Agent service</span></span>  
  
## <a name="using-an-activeactivepassive-cluster"></a><span data-ttu-id="c36e9-123">アクティブ/アクティブ/パッシブ クラスターの使用</span><span class="sxs-lookup"><span data-stu-id="c36e9-123">Using an Active/Active/Passive Cluster</span></span>  
 <span data-ttu-id="c36e9-124">1 つのノードはフェールオーバー シナリオでは、すべての SQL Server インスタンスを処理できないと判断した場合の代替では、アクティブ/アクティブ/パッシブのクラスタ リング モデルを使用します。</span><span class="sxs-lookup"><span data-stu-id="c36e9-124">If you determine that one node cannot handle all SQL Server instances in a failover scenario, an alternative is to use an Active/Active/Passive clustering model.</span></span> <span data-ttu-id="c36e9-125">アクティブ/アクティブ/パッシブ クラスタ リング モデルでは、常にある 1 つのパッシブ ノードのフェールオーバーのシナリオに使用できる可能性が大幅に高まります。</span><span class="sxs-lookup"><span data-stu-id="c36e9-125">The Active/Active/Passive clustering model greatly increases the likelihood that there will always be one Passive node available for failover scenarios.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c36e9-126">参照</span><span class="sxs-lookup"><span data-stu-id="c36e9-126">See Also</span></span>  
 [<span data-ttu-id="c36e9-127">チェックリスト:SQL Server の構成</span><span class="sxs-lookup"><span data-stu-id="c36e9-127">Checklist: Configuring SQL Server</span></span>](~/technical-guides/checklist-configuring-sql-server.md)