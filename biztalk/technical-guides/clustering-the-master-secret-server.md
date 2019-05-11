---
title: マスター シークレット サーバーをクラスタ リング |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 14aa3622-8462-4ed9-abde-40090d4f96ff
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 50813db21de9505b6c417be8950279fcd62a37cf
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65277197"
---
# <a name="clustering-the-master-secret-server"></a><span data-ttu-id="b2c95-102">マスター シークレット サーバーをクラスタ リング</span><span class="sxs-lookup"><span data-stu-id="b2c95-102">Clustering the Master Secret Server</span></span>
<span data-ttu-id="b2c95-103">BizTalk Server アプリケーション サービスと共にインストールされているエンタープライズ シングル サインオン (SSO) サービスにハード コーディングされた依存関係を維持する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="b2c95-103">The BizTalk Server application service maintains a hard-coded dependency upon the Enterprise Single Sign-On (SSO) service that is installed with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="b2c95-104">SSO サービスは、開始する場合は、マスター シークレット サーバーと通信できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="b2c95-104">The SSO service must be able to communicate with the master secret server to start.</span></span> <span data-ttu-id="b2c95-105">マスター シークレット サーバーのフォールト トレランスを提供するマスタ シークレット サーバーで SSO サービスをクラスター化することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b2c95-105">We recommend that you cluster the SSO service on the master secret server to provide fault tolerance for the master secret server.</span></span> <span data-ttu-id="b2c95-106">詳細については、次を参照してください。[高可用性 SSO インストール オプション](http://go.microsoft.com/fwlink/?LinkId=156838)(<http://go.microsoft.com/fwlink/?LinkId=156838>) BizTalk Server のヘルプ。</span><span class="sxs-lookup"><span data-stu-id="b2c95-106">For more information, see [High-Availability SSO Installation Options](http://go.microsoft.com/fwlink/?LinkId=156838) (<http://go.microsoft.com/fwlink/?LinkId=156838>) in BizTalk Server Help.</span></span>  
  
## <a name="preparing-for-clustering-the-master-secret-server"></a><span data-ttu-id="b2c95-107">マスター シークレット サーバーをクラスター化するための準備</span><span class="sxs-lookup"><span data-stu-id="b2c95-107">Preparing for Clustering the Master Secret Server</span></span>  
  
### <a name="deciding-whether-to-use-a-dedicated-cluster-or-the-sql-server-cluster"></a><span data-ttu-id="b2c95-108">専用のクラスターまたは SQL Server クラスターを使用するかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="b2c95-108">Deciding Whether to Use a Dedicated Cluster or the SQL Server Cluster</span></span>  
 <span data-ttu-id="b2c95-109">ハードウェア クラスタ リングが高くなります。</span><span class="sxs-lookup"><span data-stu-id="b2c95-109">Clustering hardware is expensive.</span></span> <span data-ttu-id="b2c95-110">高可用性ソリューションのハードウェア リソースを減らすためには、マスター シークレット サーバーを追加でクラスター リソースとして、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]データベース クラスター。</span><span class="sxs-lookup"><span data-stu-id="b2c95-110">To reduce the hardware resources for a highly available solution, you can add the master secret server as a cluster resource in your [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] database cluster.</span></span> <span data-ttu-id="b2c95-111">使用する場合、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]データベース クラスターでは、メッセージ ボックス データベースと同じアクティブなノードでマスター シークレット サーバーに配置しないことお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b2c95-111">If you use the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] database cluster, we recommend that you do not put the master secret server on the same active node as the MessageBox database.</span></span> <span data-ttu-id="b2c95-112">メッセージ ボックス データベースは、他のデータベースよりも通常はビジー状態です。</span><span class="sxs-lookup"><span data-stu-id="b2c95-112">The MessageBox database is usually busier than other databases.</span></span> <span data-ttu-id="b2c95-113">マスター シークレット サーバーが多くのハードウェア リソースを使用しない場合でも、メッセージ ボックス データベースのアクティブ ノードから別のアクティブなクラスター ノードに移動することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b2c95-113">Even though the master secret server doesn't consume many hardware resources, it is better to move it to a different active cluster node from the active MessageBox database node.</span></span>  
  
### <a name="clustering-the-sso-database"></a><span data-ttu-id="b2c95-114">SSO データベースをクラスタ リング</span><span class="sxs-lookup"><span data-stu-id="b2c95-114">Clustering the SSO Database</span></span>  
 <span data-ttu-id="b2c95-115">マスター シークレット サーバーは、SSO データベースに依存します。</span><span class="sxs-lookup"><span data-stu-id="b2c95-115">The master secret server depends on the SSO database.</span></span> <span data-ttu-id="b2c95-116">高可用性 SSO をビルドするには、SSO データベースをクラスター化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b2c95-116">To build a high-availability SSO, you must cluster the SSO database.</span></span> <span data-ttu-id="b2c95-117">BizTalk データベースをクラスタ リングの詳細については、次を参照してください。 [、BizTalk Server Databases2 をクラスタ リング](../technical-guides/clustering-the-biztalk-server-databases2.md)します。</span><span class="sxs-lookup"><span data-stu-id="b2c95-117">For more information about clustering BizTalk databases, see [Clustering the BizTalk Server Databases2](../technical-guides/clustering-the-biztalk-server-databases2.md).</span></span>  
  
### <a name="creating-domain-groups-and-accounts"></a><span data-ttu-id="b2c95-118">ドメイン グループおよびアカウントの作成</span><span class="sxs-lookup"><span data-stu-id="b2c95-118">Creating Domain Groups and Accounts</span></span>  
 <span data-ttu-id="b2c95-119">マスター シークレット サーバーをクラスター化する前に、次のドメイン グループおよびアカウントを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b2c95-119">You need to configure the following domain groups and accounts before clustering the master secret server:</span></span>  
  
-   <span data-ttu-id="b2c95-120">SSO 管理者および SSO 関連管理者の名前を持つドメイン グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="b2c95-120">Create domain groups with the names SSO Administrators and SSO Affiliate Administrators.</span></span> <span data-ttu-id="b2c95-121">エンタープライズ SSO サービスのクラスター化されたインスタンスを作成するには、ドメイン グループとして SSO 管理者および SSO 関連管理者のグループを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b2c95-121">To create a clustered instance of the Enterprise SSO service, you must create the SSO Administrators and SSO Affiliate Administrators groups as domain groups.</span></span>  
  
-   <span data-ttu-id="b2c95-122">作成または SSO 管理者のドメイン グループのメンバーであるドメイン アカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="b2c95-122">Create or designate a domain account that is a member of the SSO Administrators domain group.</span></span> <span data-ttu-id="b2c95-123">各ノードで、エンタープライズ SSO サービスは、このドメイン アカウントとしてログオンするように構成されます。</span><span class="sxs-lookup"><span data-stu-id="b2c95-123">The Enterprise SSO service on each node will be configured to log on as this domain account.</span></span> <span data-ttu-id="b2c95-124">このアカウントは、「サービスとしてログオン」権限をクラスター内の各ノードが必要です。</span><span class="sxs-lookup"><span data-stu-id="b2c95-124">This account must have the "Log on as a service" right on each node in the cluster.</span></span> <span data-ttu-id="b2c95-125">このアカウントは、クラスターへのフル コントロール アクセスを付与する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b2c95-125">This account must also be granted Full Control access to the cluster.</span></span>  
  
## <a name="clustering-the-master-secret-server"></a><span data-ttu-id="b2c95-126">マスター シークレット サーバーをクラスタ リング</span><span class="sxs-lookup"><span data-stu-id="b2c95-126">Clustering the Master Secret Server</span></span>  
 <span data-ttu-id="b2c95-127">マスター シークレット サーバーをクラスター化するための基本的な手順を次に示します。</span><span class="sxs-lookup"><span data-stu-id="b2c95-127">Here are the basic steps for clustering the master secret server:</span></span>  
  
1. <span data-ttu-id="b2c95-128">インストールし、クラスター ノードにエンタープライズ SSO を構成します。</span><span class="sxs-lookup"><span data-stu-id="b2c95-128">Install and configure Enterprise SSO on the cluster nodes.</span></span>  
  
2. <span data-ttu-id="b2c95-129">クラスター化されたエンタープライズ SSO リソースと依存するリソースを作成します。</span><span class="sxs-lookup"><span data-stu-id="b2c95-129">Create the clustered Enterprise SSO resource and the dependent resources.</span></span>  
  
3. <span data-ttu-id="b2c95-130">2 番目のクラスター ノードでマスター シークレットを復元します。</span><span class="sxs-lookup"><span data-stu-id="b2c95-130">Restore the master secret on the second cluster node.</span></span> <span data-ttu-id="b2c95-131">マスター シークレット サーバーをクラスターに移動する場合も最初のクラスター ノード上にマスター シークレットを復元する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b2c95-131">If you move the master secret server to the cluster, you must restore the master secret on the first cluster node as well.</span></span>  
  
4. <span data-ttu-id="b2c95-132">オンライン SSO サービスを含むクラスター グループを表示します。</span><span class="sxs-lookup"><span data-stu-id="b2c95-132">Bring the cluster group that contains the SSO service, online.</span></span>  
  
5. <span data-ttu-id="b2c95-133">管理データベースのマスター シークレットの名前を更新します。</span><span class="sxs-lookup"><span data-stu-id="b2c95-133">Update the master secret name in the Management database.</span></span>  
  
   <span data-ttu-id="b2c95-134">マスター シークレット サーバーをクラスタ リングの詳細な手順は、次を参照してください。[マスター シークレット サーバーをクラスター化する方法](http://go.microsoft.com/fwlink/?LinkId=156839)(<http://go.microsoft.com/fwlink/?LinkId=156839>) で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。</span><span class="sxs-lookup"><span data-stu-id="b2c95-134">For detailed steps on clustering the master secret server, see [How to Cluster the Master Secret Server](http://go.microsoft.com/fwlink/?LinkId=156839) (<http://go.microsoft.com/fwlink/?LinkId=156839>) in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2c95-135">参照</span><span class="sxs-lookup"><span data-stu-id="b2c95-135">See Also</span></span>  
 [<span data-ttu-id="b2c95-136">新しいマスター シークレット サーバーを手動で指定する</span><span class="sxs-lookup"><span data-stu-id="b2c95-136">Designating a New Master Secret Server Manually</span></span>](../technical-guides/designating-a-new-master-secret-server-manually.md)