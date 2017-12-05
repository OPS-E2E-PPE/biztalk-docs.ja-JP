---
title: "マスター シークレット サーバーをクラスター化 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 14aa3622-8462-4ed9-abde-40090d4f96ff
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6f37997582cbd94d8bbb5eaee829eead0af85ad2
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="clustering-the-master-secret-server"></a><span data-ttu-id="69ade-102">マスター シークレット サーバーをクラスタ リング</span><span class="sxs-lookup"><span data-stu-id="69ade-102">Clustering the Master Secret Server</span></span>
<span data-ttu-id="69ade-103">BizTalk Server アプリケーション サービスと共にインストールされているエンタープライズ シングル サインオン (SSO) サービスに依存してハード コーディングされたを保持する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="69ade-103">The BizTalk Server application service maintains a hard-coded dependency upon the Enterprise Single Sign-On (SSO) service that is installed with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="69ade-104">SSO サービスは、開始する場合は、マスター シークレット サーバーと通信できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="69ade-104">The SSO service must be able to communicate with the master secret server to start.</span></span> <span data-ttu-id="69ade-105">マスター シークレット サーバーのフォールト トレランスを提供する、マスター シークレット サーバーで SSO サービスをクラスター化することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="69ade-105">We recommend that you cluster the SSO service on the master secret server to provide fault tolerance for the master secret server.</span></span> <span data-ttu-id="69ade-106">詳細については、次を参照してください。[高可用性 SSO インストール オプション](http://go.microsoft.com/fwlink/?LinkId=156838)(http://go.microsoft.com/fwlink/?LinkId=156838)、BizTalk Server のヘルプ。</span><span class="sxs-lookup"><span data-stu-id="69ade-106">For more information, see [High-Availability SSO Installation Options](http://go.microsoft.com/fwlink/?LinkId=156838) (http://go.microsoft.com/fwlink/?LinkId=156838) in BizTalk Server Help.</span></span>  
  
## <a name="preparing-for-clustering-the-master-secret-server"></a><span data-ttu-id="69ade-107">マスター シークレット サーバーをクラスターの準備</span><span class="sxs-lookup"><span data-stu-id="69ade-107">Preparing for Clustering the Master Secret Server</span></span>  
  
### <a name="deciding-whether-to-use-a-dedicated-cluster-or-the-sql-server-cluster"></a><span data-ttu-id="69ade-108">専用のクラスターまたは SQL Server クラスターを使用するかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="69ade-108">Deciding Whether to Use a Dedicated Cluster or the SQL Server Cluster</span></span>  
 <span data-ttu-id="69ade-109">クラスタ リングのハードウェアが高くなります。</span><span class="sxs-lookup"><span data-stu-id="69ade-109">Clustering hardware is expensive.</span></span> <span data-ttu-id="69ade-110">高可用性ソリューションのハードウェア リソースを減らすためには、クラスター リソースとして、マスター シークレット サーバーを追加することができます、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]データベース クラスター。</span><span class="sxs-lookup"><span data-stu-id="69ade-110">To reduce the hardware resources for a highly available solution, you can add the master secret server as a cluster resource in your [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] database cluster.</span></span> <span data-ttu-id="69ade-111">使用する場合、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]データベース クラスターでは、ことをお勧め、メッセージ ボックス データベースと同じアクティブなノードでマスター シークレット サーバーを配置しないことです。</span><span class="sxs-lookup"><span data-stu-id="69ade-111">If you use the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] database cluster, we recommend that you do not put the master secret server on the same active node as the MessageBox database.</span></span> <span data-ttu-id="69ade-112">メッセージ ボックス データベースは、他のデータベースよりも通常ビジー状態です。</span><span class="sxs-lookup"><span data-stu-id="69ade-112">The MessageBox database is usually busier than other databases.</span></span> <span data-ttu-id="69ade-113">マスター シークレット サーバーが多くのハードウェア リソースを利用していない場合でも、メッセージ ボックス データベースのアクティブ ノードから別のアクティブなクラスター ノードに移動することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="69ade-113">Even though the master secret server doesn't consume many hardware resources, it is better to move it to a different active cluster node from the active MessageBox database node.</span></span>  
  
### <a name="clustering-the-sso-database"></a><span data-ttu-id="69ade-114">SSO データベースをクラスタ リング</span><span class="sxs-lookup"><span data-stu-id="69ade-114">Clustering the SSO Database</span></span>  
 <span data-ttu-id="69ade-115">マスター シークレット サーバーは、SSO データベースに依存します。</span><span class="sxs-lookup"><span data-stu-id="69ade-115">The master secret server depends on the SSO database.</span></span> <span data-ttu-id="69ade-116">高可用性 SSO をビルドするには、SSO データベースをクラスター化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="69ade-116">To build a high-availability SSO, you must cluster the SSO database.</span></span> <span data-ttu-id="69ade-117">BizTalk データベースをクラスタ リングの詳細については、次を参照してください。 [BizTalk Server Databases2 をクラスタ リング](../technical-guides/clustering-the-biztalk-server-databases2.md)です。</span><span class="sxs-lookup"><span data-stu-id="69ade-117">For more information about clustering BizTalk databases, see [Clustering the BizTalk Server Databases2](../technical-guides/clustering-the-biztalk-server-databases2.md).</span></span>  
  
### <a name="creating-domain-groups-and-accounts"></a><span data-ttu-id="69ade-118">ドメイン グループおよびアカウントの作成</span><span class="sxs-lookup"><span data-stu-id="69ade-118">Creating Domain Groups and Accounts</span></span>  
 <span data-ttu-id="69ade-119">マスター シークレット サーバーをクラスター化する前に、次のドメイン グループとアカウントを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="69ade-119">You need to configure the following domain groups and accounts before clustering the master secret server:</span></span>  
  
-   <span data-ttu-id="69ade-120">SSO 管理者と SSO 関連管理者の名前とドメイン グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="69ade-120">Create domain groups with the names SSO Administrators and SSO Affiliate Administrators.</span></span> <span data-ttu-id="69ade-121">エンタープライズ SSO サービスのクラスター化されたインスタンスを作成するには、ドメイン グループとして、SSO 管理者および SSO 関連管理者グループを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="69ade-121">To create a clustered instance of the Enterprise SSO service, you must create the SSO Administrators and SSO Affiliate Administrators groups as domain groups.</span></span>  
  
-   <span data-ttu-id="69ade-122">作成または SSO 管理者のドメイン グループのメンバーであるドメイン アカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="69ade-122">Create or designate a domain account that is a member of the SSO Administrators domain group.</span></span> <span data-ttu-id="69ade-123">各ノードのエンタープライズ SSO サービスは、このドメイン アカウントとしてログオンする構成されます。</span><span class="sxs-lookup"><span data-stu-id="69ade-123">The Enterprise SSO service on each node will be configured to log on as this domain account.</span></span> <span data-ttu-id="69ade-124">このアカウントによっては、クラスター内の各ノードに「サービスとしてログオン」権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="69ade-124">This account must have the "Log on as a service" right on each node in the cluster.</span></span> <span data-ttu-id="69ade-125">このアカウントは、クラスターへのフル コントロール アクセスを付与する必要があります。</span><span class="sxs-lookup"><span data-stu-id="69ade-125">This account must also be granted Full Control access to the cluster.</span></span>  
  
## <a name="clustering-the-master-secret-server"></a><span data-ttu-id="69ade-126">マスター シークレット サーバーをクラスタ リング</span><span class="sxs-lookup"><span data-stu-id="69ade-126">Clustering the Master Secret Server</span></span>  
 <span data-ttu-id="69ade-127">マスター シークレット サーバーをクラスタ リング用の基本的な手順を次に示します。</span><span class="sxs-lookup"><span data-stu-id="69ade-127">Here are the basic steps for clustering the master secret server:</span></span>  
  
1.  <span data-ttu-id="69ade-128">インストールし、クラスター ノードにエンタープライズ SSO を構成します。</span><span class="sxs-lookup"><span data-stu-id="69ade-128">Install and configure Enterprise SSO on the cluster nodes.</span></span>  
  
2.  <span data-ttu-id="69ade-129">クラスター化されたエンタープライズ SSO リソースと依存するリソースを作成します。</span><span class="sxs-lookup"><span data-stu-id="69ade-129">Create the clustered Enterprise SSO resource and the dependent resources.</span></span>  
  
3.  <span data-ttu-id="69ade-130">2 番目のクラスター ノードでマスター シークレットを復元します。</span><span class="sxs-lookup"><span data-stu-id="69ade-130">Restore the master secret on the second cluster node.</span></span> <span data-ttu-id="69ade-131">マスター シークレット サーバーをクラスターに移動する場合も最初のクラスター ノードでマスター シークレットを復元する必要があります。</span><span class="sxs-lookup"><span data-stu-id="69ade-131">If you move the master secret server to the cluster, you must restore the master secret on the first cluster node as well.</span></span>  
  
4.  <span data-ttu-id="69ade-132">オンライン SSO サービスを含むクラスター グループを表示します。</span><span class="sxs-lookup"><span data-stu-id="69ade-132">Bring the cluster group that contains the SSO service, online.</span></span>  
  
5.  <span data-ttu-id="69ade-133">管理データベースにマスター シークレット名を更新します。</span><span class="sxs-lookup"><span data-stu-id="69ade-133">Update the master secret name in the Management database.</span></span>  
  
 <span data-ttu-id="69ade-134">マスター シークレット サーバーをクラスタ リングの詳細な手順については、次を参照してください。[マスター シークレット サーバーをクラスター化する方法](http://go.microsoft.com/fwlink/?LinkId=156839)(http://go.microsoft.com/fwlink/?LinkId=156839) で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。</span><span class="sxs-lookup"><span data-stu-id="69ade-134">For detailed steps on clustering the master secret server, see [How to Cluster the Master Secret Server](http://go.microsoft.com/fwlink/?LinkId=156839) (http://go.microsoft.com/fwlink/?LinkId=156839) in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69ade-135">参照</span><span class="sxs-lookup"><span data-stu-id="69ade-135">See Also</span></span>  
 [<span data-ttu-id="69ade-136">新しいマスター シークレット サーバーを手動で指定する</span><span class="sxs-lookup"><span data-stu-id="69ade-136">Designating a New Master Secret Server Manually</span></span>](../technical-guides/designating-a-new-master-secret-server-manually.md)