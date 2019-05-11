---
title: ディスク、IP アドレスを使用したクラスター グループを作成し、名前を Resource1 する方法 |Microsoft Docs
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
ms.openlocfilehash: 60b76da3fe031881eea3491469ac0f9d0bfe5c48
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385593"
---
# <a name="how-to-create-a-cluster-group-with-a-disk-ip-address-and-name-resource"></a><span data-ttu-id="2bf56-102">ディスク、IP アドレス、および名前リソースをクラスター グループを作成する方法</span><span class="sxs-lookup"><span data-stu-id="2bf56-102">How to Create a Cluster Group with a Disk, IP Address, and Name Resource</span></span>
<span data-ttu-id="2bf56-103">クラスター化された[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]コンポーネントと依存関係に NetBIOS、クラスター化された経由でネットワーク経由でアクセスできる**ネットワーク名**同じクラスター グループにリソースを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2bf56-103">For clustered [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] components and dependencies to be accessible over the network via NetBIOS, a clustered **Network Name** resource must be created in same cluster group.</span></span> <span data-ttu-id="2bf56-104">TCP/IP プロトコル経由でアクセスできるクラスター化されたネットワーク名リソース、 **IP アドレス**も同じクラスター グループにリソースを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2bf56-104">For a clustered Network Name resource to be accessible via the TCP/IP protocol, an **IP Address** resource must be created in the same cluster group as well.</span></span> <span data-ttu-id="2bf56-105">いくつか[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]依存関係をクラスター化を使用する必要も**物理ディスク**正常に機能するリソース。</span><span class="sxs-lookup"><span data-stu-id="2bf56-105">Some [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] dependencies also require the use of a clustered **Physical Disk** resource to function correctly.</span></span> <span data-ttu-id="2bf56-106">使用してクラスター グループを作成する、**物理ディスク**、 **IP アドレス**と**ネットワーク名**リソースに次の手順します。</span><span class="sxs-lookup"><span data-stu-id="2bf56-106">To create a cluster group with a **Physical Disk**, **IP Address** and **Network Name** resource follow these steps:</span></span>  
  
### <a name="to-create-a-service-or-application-with-a-physical-disk-ip-address-and-network-name-resource"></a><span data-ttu-id="2bf56-107">物理ディスク、IP アドレス、およびネットワーク名リソースにサービスまたはアプリケーションを作成するには</span><span class="sxs-lookup"><span data-stu-id="2bf56-107">To create a service or application with a Physical Disk, IP Address, and Network Name resource</span></span>  
  
1.  <span data-ttu-id="2bf56-108">Windows、 をクリックして**開始**、**プログラム**、**管理ツール**、し**フェールオーバー クラスター管理**フェールオーバーを開始するにはクラスター管理プログラム。</span><span class="sxs-lookup"><span data-stu-id="2bf56-108">In Windows, click **Start**, **Programs**, **Administrative Tools**, and then **Failover Cluster Management** to start the Failover Cluster Management program.</span></span>  
  
2.  <span data-ttu-id="2bf56-109">すべてのサービスとアプリケーションのフェールオーバー クラスター管理を実行しているクラスター ノードをフェールオーバーします。</span><span class="sxs-lookup"><span data-stu-id="2bf56-109">Fail over all services and applications to the cluster node that you are running Failover Cluster Management on.</span></span> <span data-ttu-id="2bf56-110">サービスまたはアプリケーションをフェールオーバーするサービスまたはフェールオーバー クラスター管理の左側のウィンドウでアプリケーションを右クリックをポイントして**このサービスまたはアプリケーションを別のノードに移動**と宛先ノードを選択する をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2bf56-110">To fail over a service or application, right click the service or application in the left pane of Failover Cluster Management, point to **Move this service or application to another node** and click to select the destination node.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2bf56-111">実行中のクラスター リソースをホストするクラスター ノードとも呼ばれますが、 **active**ノード。</span><span class="sxs-lookup"><span data-stu-id="2bf56-111">The cluster node that hosts running cluster resources is also known as the **active** node.</span></span> <span data-ttu-id="2bf56-112">実行されていないクラスター リソースをホストするクラスター ノードとも呼ばれますが、**パッシブ**ノード。</span><span class="sxs-lookup"><span data-stu-id="2bf56-112">The cluster node that hosts non-running cluster resources is also known as the **passive** node.</span></span>  
  
3.  <span data-ttu-id="2bf56-113">左側のウィンドウで右クリック**サービスとアプリケーション**、 をクリックして**サービスまたはアプリケーション構成**を高可用性ウィザードを起動し、順にクリックします**次**.</span><span class="sxs-lookup"><span data-stu-id="2bf56-113">In the left-hand pane, right-click **Services and Applications**, click **Configure a Service or Application** to launch the High Availability Wizard, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="2bf56-114">クリックして選択**ファイル サーバー**  をクリック**次**します。</span><span class="sxs-lookup"><span data-stu-id="2bf56-114">Click to select **File Server** and click **Next**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2bf56-115">選択**ファイル サーバー**ディスク リソースを持つクラスター グループを作成する簡単な方法としてこの時点で実行されます。</span><span class="sxs-lookup"><span data-stu-id="2bf56-115">Selecting **File Server** at this point is done as a straightforward way to create a cluster group with a disk resource.</span></span>  
  
5.  <span data-ttu-id="2bf56-116">**クライアント アクセス ポイント**高可用性ウィザードのページに一意のネットワーク名を入力してください、**名前**ボックスで、たとえば*BizTalkCluster*、使用可能な ip アドレスを入力しますアドレス**アドレス**、順にクリックします**次**します。</span><span class="sxs-lookup"><span data-stu-id="2bf56-116">On the **Client Access Point** page of the High Availability Wizard enter a unique network name into the **Name** box, for example *BizTalkCluster*, enter an available IP address under **Address**, and then click **Next**.</span></span>  
  
6.  <span data-ttu-id="2bf56-117">**[記憶域の**] ページで、クリックして、使用可能なディスク リソースを選択し、クリックして**次**。</span><span class="sxs-lookup"><span data-stu-id="2bf56-117">On the **Select Storage** page, click to select an available disk resource and then click **Next**.</span></span>  
  
7.  <span data-ttu-id="2bf56-118">**確認**ページ クリック **[次へ]** クラスター グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="2bf56-118">On the **Confirmation** page click **Next** to create the cluster group.</span></span>  
  
8.  <span data-ttu-id="2bf56-119">**概要**ページ クリック**完了**。</span><span class="sxs-lookup"><span data-stu-id="2bf56-119">On the **Summary** page click **Finish**.</span></span>