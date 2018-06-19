---
title: ディスク、IP アドレスを使用してクラスター グループを作成し、名前を Resource1 する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b361f721-60db-485e-9ce3-48a6871ebd79
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 63310706742ffcc10de5266dda7053da79fc04fe
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249306"
---
# <a name="how-to-create-a-cluster-group-with-a-disk-ip-address-and-name-resource"></a><span data-ttu-id="79a13-102">ディスク、IP アドレス、および名前リソースを使用してクラスター グループを作成する方法</span><span class="sxs-lookup"><span data-stu-id="79a13-102">How to Create a Cluster Group with a Disk, IP Address, and Name Resource</span></span>
<span data-ttu-id="79a13-103">クラスター化された[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]コンポーネントと依存関係に NetBIOS、クラスター化された経由でネットワーク経由でアクセスできる**ネットワーク名**同じクラスター グループにリソースを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="79a13-103">For clustered [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] components and dependencies to be accessible over the network via NetBIOS, a clustered **Network Name** resource must be created in same cluster group.</span></span> <span data-ttu-id="79a13-104">TCP/IP プロトコル経由でアクセスできるようにクラスター化されたネットワーク名リソースの**IP アドレス**も同じクラスター グループにリソースを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="79a13-104">For a clustered Network Name resource to be accessible via the TCP/IP protocol, an **IP Address** resource must be created in the same cluster group as well.</span></span> <span data-ttu-id="79a13-105">いくつか[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]の依存関係も使用する必要はクラスター化された**物理ディスク**リソースを正常に機能します。</span><span class="sxs-lookup"><span data-stu-id="79a13-105">Some [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] dependencies also require the use of a clustered **Physical Disk** resource to function correctly.</span></span> <span data-ttu-id="79a13-106">使用して、クラスター グループを作成する、**物理ディスク**、 **IP アドレス**と**ネットワーク名**リソースに次の手順します。</span><span class="sxs-lookup"><span data-stu-id="79a13-106">To create a cluster group with a **Physical Disk**, **IP Address** and **Network Name** resource follow these steps:</span></span>  
  
### <a name="to-create-a-service-or-application-with-a-physical-disk-ip-address-and-network-name-resource"></a><span data-ttu-id="79a13-107">物理ディスク、IP アドレス、およびネットワーク名リソースを使用してサービスまたはアプリケーションを作成するには</span><span class="sxs-lookup"><span data-stu-id="79a13-107">To create a service or application with a Physical Disk, IP Address, and Network Name resource</span></span>  
  
1.  <span data-ttu-id="79a13-108">Windows では、をクリックして**開始**、**プログラム**、**管理ツール**、し**フェイル オーバー クラスター管理**フェールオーバーを開始するにはクラスター管理プログラムです。</span><span class="sxs-lookup"><span data-stu-id="79a13-108">In Windows, click **Start**, **Programs**, **Administrative Tools**, and then **Failover Cluster Management** to start the Failover Cluster Management program.</span></span>  
  
2.  <span data-ttu-id="79a13-109">フェールオーバー クラスター管理を実行しているクラスター ノードに、すべてのサービスとアプリケーションをフェールオーバーします。</span><span class="sxs-lookup"><span data-stu-id="79a13-109">Fail over all services and applications to the cluster node that you are running Failover Cluster Management on.</span></span> <span data-ttu-id="79a13-110">サービスまたはアプリケーションがフェールオーバーするサービスまたはフェールオーバー クラスター管理の左側のウィンドウでアプリケーションを右クリックして、指す**このサービスまたはアプリケーションを別のノードに移動**をクリックして、移行先ノードを選択します。</span><span class="sxs-lookup"><span data-stu-id="79a13-110">To fail over a service or application, right click the service or application in the left pane of Failover Cluster Management, point to **Move this service or application to another node** and click to select the destination node.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="79a13-111">実行中のクラスター リソースをホストしているクラスター ノードとも呼ばれます、 **active**ノード。</span><span class="sxs-lookup"><span data-stu-id="79a13-111">The cluster node that hosts running cluster resources is also known as the **active** node.</span></span> <span data-ttu-id="79a13-112">実行されていないクラスター リソースをホストしているクラスター ノードとも呼ばれます、**パッシブ**ノード。</span><span class="sxs-lookup"><span data-stu-id="79a13-112">The cluster node that hosts non-running cluster resources is also known as the **passive** node.</span></span>  
  
3.  <span data-ttu-id="79a13-113">左側のペインで右クリック**サービスとアプリケーション**、 をクリックして**サービスまたはアプリケーションを構成**、高可用性ウィザードを起動し、をクリックする**次**.</span><span class="sxs-lookup"><span data-stu-id="79a13-113">In the left-hand pane, right-click **Services and Applications**, click **Configure a Service or Application** to launch the High Availability Wizard, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="79a13-114">クリックして選択**ファイル サーバー**  をクリック**次**です。</span><span class="sxs-lookup"><span data-stu-id="79a13-114">Click to select **File Server** and click **Next**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="79a13-115">選択すると**ファイル サーバー**ディスク リソースを持つクラスター グループを作成する簡単な方法としてこの時点で実行されます。</span><span class="sxs-lookup"><span data-stu-id="79a13-115">Selecting **File Server** at this point is done as a straightforward way to create a cluster group with a disk resource.</span></span>  
  
5.  <span data-ttu-id="79a13-116">**クライアント アクセス ポイント**高可用性ウィザードのページに一意のネットワーク名を入力してください、**名前**ボックスで、たとえば*BizTalkCluster*、利用可能な IP を入力してくださいアドレス**アドレス**、順にクリック**次**です。</span><span class="sxs-lookup"><span data-stu-id="79a13-116">On the **Client Access Point** page of the High Availability Wizard enter a unique network name into the **Name** box, for example *BizTalkCluster*, enter an available IP address under **Address**, and then click **Next**.</span></span>  
  
6.  <span data-ttu-id="79a13-117">**[記憶域の**] ページで、クリックして、使用可能なディスク リソースを選択し、をクリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="79a13-117">On the **Select Storage** page, click to select an available disk resource and then click **Next**.</span></span>  
  
7.  <span data-ttu-id="79a13-118">**確認**ページをクリックして**次**クラスター グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="79a13-118">On the **Confirmation** page click **Next** to create the cluster group.</span></span>  
  
8.  <span data-ttu-id="79a13-119">**概要**ページをクリックして**完了**です。</span><span class="sxs-lookup"><span data-stu-id="79a13-119">On the **Summary** page click **Finish**.</span></span>