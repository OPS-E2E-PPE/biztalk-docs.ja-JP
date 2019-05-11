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
ms.openlocfilehash: 368b2c33ab81a63a870258da4077eb5e68164e53
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65354789"
---
# <a name="considerations-for-installing-biztalk-server-on-a-windows-server-cluster"></a><span data-ttu-id="f4738-102">Windows Server クラスターでの BizTalk Server のインストールに関する注意点</span><span class="sxs-lookup"><span data-stu-id="f4738-102">Considerations for Installing BizTalk Server on a Windows Server Cluster</span></span>
<span data-ttu-id="f4738-103">インストールするときに、特別な考慮事項を行う必要があります[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を Windows Server クラスターにします。</span><span class="sxs-lookup"><span data-stu-id="f4738-103">Special considerations must be made when installing [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] on a Windows Server cluster.</span></span> <span data-ttu-id="f4738-104">このトピックでは、これらの考慮事項を示します。</span><span class="sxs-lookup"><span data-stu-id="f4738-104">This topic lists these considerations.</span></span>  
  
## <a name="a-non-clustered-biztalk-host-instance-should-not-be-run-on-a-windows-server-cluster-where-the-enterprise-sso-service-is-clustered"></a><span data-ttu-id="f4738-105">非クラスター化 BizTalk ホスト インスタンスを実行するか、Windows Server クラスターで、エンタープライズ SSO サービスがクラスター化されました。</span><span class="sxs-lookup"><span data-stu-id="f4738-105">A non-clustered BizTalk host instance should not be run on a Windows Server cluster where the Enterprise SSO service is clustered</span></span>  
 <span data-ttu-id="f4738-106">クラスター、エンタープライズ シングル サインオン マスター シークレット サーバーをアクティブ/パッシブ構成で、マスター シークレット サーバーの高可用性を実現することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f4738-106">It is a recommended practice to cluster the Enterprise Single Sign-On Master Secret Server in an active/passive configuration to provide high availability for the master secret server.</span></span> <span data-ttu-id="f4738-107">非クラスター化 BizTalk ホスト インスタンスとエンタープライズ SSO サービスのクラスター化されたインスタンスを同じクラスター ノードで実行している場合、クラスター化されたエンタープライズ SSO サービスがクラスター内の異なるノードに移動した場合、BizTalk ホスト インスタンスは失敗します。</span><span class="sxs-lookup"><span data-stu-id="f4738-107">If a non-clustered BizTalk host instance and a clustered instance of the Enterprise SSO service are running on the same cluster node, the BizTalk host instance will fail if the clustered Enterprise SSO service is moved to a different node in the cluster.</span></span> <span data-ttu-id="f4738-108">BizTalk ホストは、エンタープライズ SSO サービスのローカルで実行中のインスタンスへの依存関係を維持します。</span><span class="sxs-lookup"><span data-stu-id="f4738-108">BizTalk Hosts maintain a dependency on a locally running instance of the Enterprise SSO service.</span></span> <span data-ttu-id="f4738-109">したがって、エンタープライズ SSO サービスはクラスター化リソースとして構成する場合、同じクラスター グループのクラスター化リソースとして、クラスター ノードで実行されているすべての BizTalk ホストを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f4738-109">Therefore if the Enterprise SSO service is configured as a clustered resource, then any BizTalk Hosts running on the cluster nodes must be configured as a clustered resource in the same cluster group.</span></span>  
  
## <a name="configure-the-microsoft-distributed-transaction-coordinator-msdtc-as-a-clustered-resource-before-installing-biztalk-server-on-a-cluster"></a><span data-ttu-id="f4738-110">クラスター化リソースとしてクラスター上の BizTalk Server をインストールする前に Microsoft 分散トランザクション コーディネーター (MSDTC) を構成します。</span><span class="sxs-lookup"><span data-stu-id="f4738-110">Configure the Microsoft Distributed Transaction Coordinator (MSDTC) as a clustered resource before installing BizTalk Server on a cluster</span></span>  
 <span data-ttu-id="f4738-111">Windows Server クラスターで BizTalk Server をインストールする場合は、まず Microsoft 分散トランザクション コーディネーターをクラスターする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f4738-111">If you plan to install BizTalk Server on a Windows Server cluster, you must cluster the Microsoft Distributed Transaction Coordinator first.</span></span>  
  
 <span data-ttu-id="f4738-112">Windows Server 2008 フェールオーバー クラスターで MSDTC をクラスターに」の手順に従います[チェックリスト。Windows Server 2008 フェールオーバー クラスターでの MS DTC リソースの作成](http://go.microsoft.com/fwlink/?LinkID=129677)</span><span class="sxs-lookup"><span data-stu-id="f4738-112">To cluster MSDTC on a Windows Server 2008 failover cluster, follow the steps outlined in [Checklist: Creating an MS DTC Resource in a Windows Server 2008 Failover Cluster](http://go.microsoft.com/fwlink/?LinkID=129677)</span></span>  
  
## <a name="network-dtc-access-must-be-enabled-on-all-biztalk-servers-and-on-the-sql-server-before-installing-or-configuring-biztalk-server"></a><span data-ttu-id="f4738-113">すべての BizTalk Server と SQL Server のインストールまたは BizTalk Server を構成する前に、ネットワーク DTC アクセスを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f4738-113">Network DTC access must be enabled on all BizTalk Servers and on the SQL Server before installing or configuring BizTalk Server</span></span>  
 <span data-ttu-id="f4738-114">BizTalk Server データベースをホストする SQL Server と各クラスター ノードで、ネットワーク DTC アクセスを有効にするに記載されている手順に従います[Web サーバーで MSDTC を有効にする方法](http://go.microsoft.com/fwlink/?LinkId=189701)(<http://go.microsoft.com/fwlink/?LinkId=189701>)。</span><span class="sxs-lookup"><span data-stu-id="f4738-114">To enable network DTC access on each cluster node as well as on the SQL Server that will host the BizTalk Server databases, follow the steps outlined in [How to Enable MSDTC on a Web Server](http://go.microsoft.com/fwlink/?LinkId=189701) (<http://go.microsoft.com/fwlink/?LinkId=189701>).</span></span> <span data-ttu-id="f4738-115">トランザクションのサポートの対応するために、ネットワーク DTC アクセスを有効にする必要があります[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="f4738-115">Network DTC access must be enabled to accommodate transactional support for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="f4738-116">このサポート技術情報記事の手順を完了した後、各サーバーを再起動することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f4738-116">We recommend that you restart each server after completing the steps in this Knowledge Base article.</span></span>  
  
## <a name="you-must-manually-create-domain-groups-in-active-directory-before-you-configure-biztalk-server"></a><span data-ttu-id="f4738-117">BizTalk Server を構成する前に Active Directory にドメイン グループに作成すること手動である必要があります。</span><span class="sxs-lookup"><span data-stu-id="f4738-117">You must manually create domain groups in Active Directory before you configure BizTalk Server</span></span>  
 <span data-ttu-id="f4738-118">インストールする場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]複数のコンピューターでは、ドメイン グループとユーザー アカウントを指定する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]構成ウィザード。</span><span class="sxs-lookup"><span data-stu-id="f4738-118">If you install [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] on multiple computers, you must specify domain groups and user accounts in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Configuration Wizard.</span></span> <span data-ttu-id="f4738-119">ドメイン グループを使用する場合、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 、構成する必要があります手動でグループを作成して構成する前に[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="f4738-119">If you use domain groups for your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] configuration, you must manually create the groups before you configure [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>