---
title: Windows Server の Cluster2 を BizTalk Server をインストールするための考慮事項 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Configure Your Server Wizard
- installing, Windows Server cluster
- BizTalk Server Configuration Wizard
- Windows Server cluster, warnings
- high availability, Windows Server cluster
- clustering, Windows Server cluster
- domain groups
- Windows Server cluster, Configure Your Server Wizard
- Network DTC access
- MSDTC
ms.assetid: 4daea7c6-7d26-440c-a2a0-fa018a25b2b3
caps.latest.revision: 26
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 96902a81fdd61b7c7d10f9bb2fc275dd18d23b72
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37000798"
---
# <a name="considerations-for-installing-biztalk-server-on-a-windows-server-cluster"></a><span data-ttu-id="2f057-102">BizTalk Server を Windows Server クラスターにインストールする際の考慮事項</span><span class="sxs-lookup"><span data-stu-id="2f057-102">Considerations for Installing BizTalk Server on a Windows Server Cluster</span></span>
<span data-ttu-id="2f057-103">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を Windows Server クラスターにインストールする場合は特別な注意が必要です。</span><span class="sxs-lookup"><span data-stu-id="2f057-103">Special considerations must be made when installing [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] on a Windows Server cluster.</span></span> <span data-ttu-id="2f057-104">このトピックでは、これらの注意事項について説明します。</span><span class="sxs-lookup"><span data-stu-id="2f057-104">This topic lists these considerations.</span></span>  
  
## <a name="a-non-clustered-biztalk-host-instance-should-not-be-run-on-a-windows-server-cluster-where-the-enterprise-sso-service-is-clustered"></a><span data-ttu-id="2f057-105">エンタープライズ SSO サービスがクラスター化されている Windows Server クラスターでは、クラスター化されていない BizTalk ホスト インスタンスを実行しない</span><span class="sxs-lookup"><span data-stu-id="2f057-105">A non-clustered BizTalk host instance should not be run on a Windows Server cluster where the Enterprise SSO service is clustered</span></span>  
 <span data-ttu-id="2f057-106">エンタープライズ シングル サインオンのマスター シークレット サーバーを、アクティブ/パッシブ構成でクラスター化することは、マスター シークレット サーバーの高可用性を実現する上で適切な手段と言えます。</span><span class="sxs-lookup"><span data-stu-id="2f057-106">It is a recommended practice to cluster the Enterprise Single Sign-On Master Secret Server in an active/passive configuration to provide high availability for the master secret server.</span></span> <span data-ttu-id="2f057-107">エンタープライズ SSO サービスのクラスター化されていない BizTalk ホスト インスタンスとクラスター化されたインスタンスを同じクラスター ノードで実行している場合、クラスター化されたエンタープライズ SSO サービスがクラスター内の別のノードに移動されると、BizTalk ホスト インスタンスは失敗します。</span><span class="sxs-lookup"><span data-stu-id="2f057-107">If a non-clustered BizTalk host instance and a clustered instance of the Enterprise SSO service are running on the same cluster node, the BizTalk host instance will fail if the clustered Enterprise SSO service is moved to a different node in the cluster.</span></span> <span data-ttu-id="2f057-108">BizTalk ホストでは、エンタープライズ SSO サービスのローカルで実行されているインスタンスに対する依存関係を維持します。</span><span class="sxs-lookup"><span data-stu-id="2f057-108">BizTalk Hosts maintain a dependency on a locally running instance of the Enterprise SSO service.</span></span> <span data-ttu-id="2f057-109">したがって、エンタープライズ SSO サービスはクラスター化リソースとして構成する場合、同じクラスター グループのクラスター化リソースとして、クラスター ノードで実行されているすべての BizTalk ホストを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2f057-109">Therefore if the Enterprise SSO service is configured as a clustered resource, then any BizTalk Hosts running on the cluster nodes must be configured as a clustered resource in the same cluster group.</span></span>  
  
## <a name="configure-the-microsoft-distributed-transaction-coordinator-msdtc-as-a-clustered-resource-before-installing-biztalk-server-on-a-cluster"></a><span data-ttu-id="2f057-110">BizTalk Server をクラスター上にインストールする前に Microsoft 分散トランザクション コーディネーター (MSDTC) をクラスター化リソースとして構成する</span><span class="sxs-lookup"><span data-stu-id="2f057-110">Configure the Microsoft Distributed Transaction Coordinator (MSDTC) as a clustered resource before installing BizTalk Server on a cluster</span></span>  
 <span data-ttu-id="2f057-111">BizTalk Server を Windows Server クラスターにインストールする場合は、先に Microsoft 分散トランザクション コーディネーターをクラスター化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2f057-111">If you plan to install BizTalk Server on a Windows Server cluster, you must cluster the Microsoft Distributed Transaction Coordinator first.</span></span>  
  
 <span data-ttu-id="2f057-112">Windows Server 2008 フェールオーバー クラスターで MSDTC をクラスターに」の手順に従います[チェックリスト: Windows Server 2008 フェールオーバー クラスターでの MS DTC リソースの作成](http://go.microsoft.com/fwlink/?LinkID=129677)</span><span class="sxs-lookup"><span data-stu-id="2f057-112">To cluster MSDTC on a Windows Server 2008 failover cluster, follow the steps outlined in [Checklist: Creating an MS DTC Resource in a Windows Server 2008 Failover Cluster](http://go.microsoft.com/fwlink/?LinkID=129677)</span></span>  
  
## <a name="network-dtc-access-must-be-enabled-on-all-biztalk-servers-and-on-the-sql-server-before-installing-or-configuring-biztalk-server"></a><span data-ttu-id="2f057-113">BizTalk Server をインストールまたは構成する前に、すべての BizTalk Server および SQL Server でネットワーク DTC アクセスを有効にしておく必要がある</span><span class="sxs-lookup"><span data-stu-id="2f057-113">Network DTC access must be enabled on all BizTalk Servers and on the SQL Server before installing or configuring BizTalk Server</span></span>  
 <span data-ttu-id="2f057-114">BizTalk Server データベースをホストする SQL Server と各クラスター ノードで、ネットワーク DTC アクセスを有効にするに記載されている手順に従います[Web サーバーで MSDTC を有効にする方法](http://go.microsoft.com/fwlink/?LinkId=189701)(<http://go.microsoft.com/fwlink/?LinkId=189701>)。</span><span class="sxs-lookup"><span data-stu-id="2f057-114">To enable network DTC access on each cluster node as well as on the SQL Server that will host the BizTalk Server databases, follow the steps outlined in [How to Enable MSDTC on a Web Server](http://go.microsoft.com/fwlink/?LinkId=189701) (<http://go.microsoft.com/fwlink/?LinkId=189701>).</span></span> <span data-ttu-id="2f057-115">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のトランザクション機能に対応できるように、ネットワーク DTC アクセスを有効にしておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="2f057-115">Network DTC access must be enabled to accommodate transactional support for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="2f057-116">このサポート技術情報の資料に記載された手順を実行した後、すべてのサーバーを再起動することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2f057-116">We recommend that you restart each server after completing the steps in this Knowledge Base article.</span></span>  
  
## <a name="you-must-manually-create-domain-groups-in-active-directory-before-you-configure-biztalk-server"></a><span data-ttu-id="2f057-117">BizTalk Server を構成する前に、Active Directory にドメイン グループを手動で作成しておく必要がある</span><span class="sxs-lookup"><span data-stu-id="2f057-117">You must manually create domain groups in Active Directory before you configure BizTalk Server</span></span>  
 <span data-ttu-id="2f057-118">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を複数のコンピューターにインストールする場合は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 構成ウィザードでドメイン グループおよびユーザー アカウントを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2f057-118">If you install [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] on multiple computers, you must specify domain groups and user accounts in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Configuration Wizard.</span></span> <span data-ttu-id="2f057-119">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の構成にドメイン グループを使用する場合は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を構成する前に、グループを手動で作成しておくことが必要です。</span><span class="sxs-lookup"><span data-stu-id="2f057-119">If you use domain groups for your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] configuration, you must manually create the groups before you configure [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>