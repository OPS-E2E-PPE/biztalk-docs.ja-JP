---
title: BAM イベント バス サービスのインスタンスを作成する |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 454bdde7-45a6-41ab-9196-f662273f0f2b
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: daf847afc8f5c1d284a8266d70006a0f43508ed9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984003"
---
# <a name="creating-instances-of-the-bam-event-bus-service"></a><span data-ttu-id="fa77b-102">BAM イベント バス サービスのインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="fa77b-102">Creating Instances of the BAM Event Bus Service</span></span>
<span data-ttu-id="fa77b-103">BAM イベント バス サービスは、BizTalk アプリケーション ホスト内で実行されます。</span><span class="sxs-lookup"><span data-stu-id="fa77b-103">The BAM Event Bus Service runs inside a BizTalk application host.</span></span> <span data-ttu-id="fa77b-104">既定のホストを使用して BAM イベント バス サービスをホストするか、新しいホストを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="fa77b-104">You can use the default host to host the BAM Event Bus Service, or you can create a new host.</span></span> <span data-ttu-id="fa77b-105">あるホストが BAM イベント バス サービスをホストする場合、そのホスト用に作成する新しいインスタンスも BAM イベント バス サービスをホストします。</span><span class="sxs-lookup"><span data-stu-id="fa77b-105">If a host hosts the BAM Event Bus service, any new instances you create for that host also hosts the service.</span></span>  
  
 <span data-ttu-id="fa77b-106">既定のホストについては、次を参照してください。[ホスト](../core/hosts.md)します。</span><span class="sxs-lookup"><span data-stu-id="fa77b-106">For information about the default host, see [Hosts](../core/hosts.md).</span></span>  
  
 <span data-ttu-id="fa77b-107">ホストを作成する方法の詳細については、次を参照してください。[新しいホストを作成する方法](../core/how-to-create-a-new-host.md)します。</span><span class="sxs-lookup"><span data-stu-id="fa77b-107">For information about creating hosts, see [How to Create a New Host](../core/how-to-create-a-new-host.md).</span></span>  
  
 <span data-ttu-id="fa77b-108">ホスト インスタンスを作成する方法の詳細については、次を参照してください。[ホスト インスタンスを追加する方法](../core/how-to-add-a-host-instance.md)します。</span><span class="sxs-lookup"><span data-stu-id="fa77b-108">For information about creating host instances, see [How to Add a Host Instance](../core/how-to-add-a-host-instance.md).</span></span>  
  
 <span data-ttu-id="fa77b-109">ホストおよびホスト インスタンス作成および構成については、次を参照してください。 [BizTalk ホストの管理およびホスト インスタンス](../core/managing-biztalk-hosts-and-host-instances.md)します。</span><span class="sxs-lookup"><span data-stu-id="fa77b-109">For information about creating and configuring hosts and host instances, see [Managing BizTalk Hosts and Host Instances](../core/managing-biztalk-hosts-and-host-instances.md).</span></span>  
  
### <a name="to-create-the-host-that-hosts-the-bam-event-bus-service"></a><span data-ttu-id="fa77b-110">BAM イベント バス サービスをホストするホストを作成するには</span><span class="sxs-lookup"><span data-stu-id="fa77b-110">To create the host that hosts the BAM Event Bus Service</span></span>  
  
1. <span data-ttu-id="fa77b-111">クリックして**開始**、 をポイント**すべてのプログラム**、 をクリックして**Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]、順にクリックします**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="fa77b-111">Click **Start**, point to **All Programs**, click **Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="fa77b-112">BizTalk 管理コンソール ウィンドウで、 **BizTalk Server 管理**ノード、展開、 **Biztalk グループ**ノードを展開し、**プラットフォームの設定**ノード、を右クリックし、**ホスト**ノードの **新規**、 をクリックし、**ホスト**。</span><span class="sxs-lookup"><span data-stu-id="fa77b-112">In the BizTalk Administration Console window, expand the **BizTalk Server Administration** node, expand the **Biztalk Group** node and expand the **Platform Settings** node, right-click the **Hosts** node, select **New**, and then click **Host**.</span></span>  
  
3. <span data-ttu-id="fa77b-113">**ホストのプロパティ** ダイアログ ボックスで、**名前**ボックスに、ホストのわかりやすい名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="fa77b-113">In the **Host Properties** dialog box, in the **Name** box, type a descriptive name for the host.</span></span>  
  
4. <span data-ttu-id="fa77b-114">**全般**] タブで、[、**ホストの追跡を許可する**チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="fa77b-114">On the **General** tab, select the **Allow Host Tracking** check box.</span></span>  
  
    <span data-ttu-id="fa77b-115">新しい子ノードが表示されます、**ホスト**ノードを新しいホストの名前。</span><span class="sxs-lookup"><span data-stu-id="fa77b-115">A new child node appears under the **Hosts** node with the name of the new host.</span></span>  
  
5. <span data-ttu-id="fa77b-116">**Windows グループ**ボックスをクリックして、このホストを割り当てる Windows グループの名前を入力**OK**します。</span><span class="sxs-lookup"><span data-stu-id="fa77b-116">In the **Windows group** box, type the name of the Windows group to assign this host, and then click **OK**.</span></span>  
  
    <span data-ttu-id="fa77b-117">新しい子ノードが表示されます、**ホスト**ノードを新しいホストの名前。</span><span class="sxs-lookup"><span data-stu-id="fa77b-117">A new child node appears under the **Hosts** node with the name of the new host.</span></span>  
  
### <a name="to-create-a-new-host-instance-of-the-host"></a><span data-ttu-id="fa77b-118">ホストの新しいホスト インスタンスを作成するには</span><span class="sxs-lookup"><span data-stu-id="fa77b-118">To create a new host instance of the host</span></span>  
  
1.  <span data-ttu-id="fa77b-119">右クリックし、**ホスト インスタンス**ノードの [**新規**、] をクリックし、**ホスト インスタンス**。</span><span class="sxs-lookup"><span data-stu-id="fa77b-119">Right-click the **Host Instance** node, select **New**, and then click **Host Instance**.</span></span>  
  
2.  <span data-ttu-id="fa77b-120">ホスト インスタンスの実行、および順にクリックしますが、サーバーを選択して**OK**します。</span><span class="sxs-lookup"><span data-stu-id="fa77b-120">Select a server where the host instance will run, and then click **OK**.</span></span>  
  
### <a name="to-add-hosting-tracking-to-the-host"></a><span data-ttu-id="fa77b-121">ホストの追跡をホストに追加するには</span><span class="sxs-lookup"><span data-stu-id="fa77b-121">To add hosting tracking to the host</span></span>  
  
1.  <span data-ttu-id="fa77b-122">Reconfigure、およびクリックするホストを右クリックして**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="fa77b-122">Right-click the host you want to reconfigure, and then click **Properties** .</span></span>  
  
2.  <span data-ttu-id="fa77b-123">**全般**] タブで [**ホストの追跡を許可する**、順にクリックします**OK**。</span><span class="sxs-lookup"><span data-stu-id="fa77b-123">On the **General** tab, select **Allow Host Tracking**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="fa77b-124">そのホストのすべてのインスタンスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="fa77b-124">Restart all instances of that host.</span></span>  
  
### <a name="to-remove-hosting-tracking-from-the-host"></a><span data-ttu-id="fa77b-125">ホストからホストの追跡を削除するには</span><span class="sxs-lookup"><span data-stu-id="fa77b-125">To remove hosting tracking from the host</span></span>  
  
1.  <span data-ttu-id="fa77b-126">ホストの追跡を削除するホストを右クリックし、をクリックし、**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="fa77b-126">Right-click the host from which you want to remove host tracking, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="fa77b-127">クリア、**を許可するホストの追跡**チェック ボックスをオンにして**OK**。</span><span class="sxs-lookup"><span data-stu-id="fa77b-127">Clear the **Allow Host tracking** check box, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="fa77b-128">そのホストのインスタンスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="fa77b-128">Restart instances of that host.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa77b-129">参照</span><span class="sxs-lookup"><span data-stu-id="fa77b-129">See Also</span></span>  
 <span data-ttu-id="fa77b-130">[BAM イベント バス サービスの管理](../core/managing-the-bam-event-bus-service.md) </span><span class="sxs-lookup"><span data-stu-id="fa77b-130">[Managing the BAM Event Bus Service](../core/managing-the-bam-event-bus-service.md) </span></span>  
 <span data-ttu-id="fa77b-131">[BAM のセキュリティに関する推奨事項](../core/bam-security-recommendations.md) </span><span class="sxs-lookup"><span data-stu-id="fa77b-131">[BAM Security Recommendations](../core/bam-security-recommendations.md) </span></span>  
 [<span data-ttu-id="fa77b-132">ビジネス アクティビティの監視 (BAM)</span><span class="sxs-lookup"><span data-stu-id="fa77b-132">Business Activity Monitoring (BAM)</span></span>](../core/business-activity-monitoring-bam.md)