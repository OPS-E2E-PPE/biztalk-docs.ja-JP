---
title: "Orchestrations1 を実行している |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- strong name keys, creating
- orchestrations
- host instances, stopping and restarting
- orchestrations, compiling
- orchestrations, deploying
ms.assetid: b992bdba-630d-4f28-aca8-c568f3c27968
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c215009d6b911831c74ac22b2c03ceae45e74a62
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="running-orchestrations"></a><span data-ttu-id="ff080-102">オーケストレーションの実行</span><span class="sxs-lookup"><span data-stu-id="ff080-102">Running Orchestrations</span></span>
<span data-ttu-id="ff080-103">次の手順では、オーケストレーションのビルド、展開、バインド、および開始の方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ff080-103">The following procedures describe how to build, deploy, bind, and start an orchestration.</span></span>  
  
## <a name="creating-a-strong-name-key"></a><span data-ttu-id="ff080-104">厳密な名前キーを作成します。</span><span class="sxs-lookup"><span data-stu-id="ff080-104">Creating a Strong Name Key</span></span>  
  
#### <a name="to-create-a-strong-name-key"></a><span data-ttu-id="ff080-105">厳密な名前のキーを作成するには</span><span class="sxs-lookup"><span data-stu-id="ff080-105">To create a strong name key</span></span>  
  
1.  <span data-ttu-id="ff080-106">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] コマンド プロンプトを起動します。</span><span class="sxs-lookup"><span data-stu-id="ff080-106">Start a [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Command Prompt.</span></span>  
  
2.  <span data-ttu-id="ff080-107">たとえば、既存のプロジェクトにディレクトリを変更\<ドライブ\>: \Adapter_Install\biztalk2010\my_project です。</span><span class="sxs-lookup"><span data-stu-id="ff080-107">Change directories to an existing project, for example, \<drive\>:\Adapter_Install\biztalk2010\my_project.</span></span>  
  
3.  <span data-ttu-id="ff080-108">コマンド プロンプトで、次を入力し、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="ff080-108">Type the following in the command prompt and press ENTER:</span></span>  
  
     `sn -k SSOSchedule.snk`  
  
## <a name="compiling-and-deploying-an-orchestration"></a><span data-ttu-id="ff080-109">オーケストレーションのコンパイルおよび展開</span><span class="sxs-lookup"><span data-stu-id="ff080-109">Compiling and Deploying an Orchestration</span></span>  
  
#### <a name="to-compile-and-deploy-an-orchestration"></a><span data-ttu-id="ff080-110">オーケストレーションをコンパイルおよび展開するには</span><span class="sxs-lookup"><span data-stu-id="ff080-110">To compile and deploy an orchestration</span></span>  
  
1.  <span data-ttu-id="ff080-111">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ソリューション エクスプ ローラーで、[ssoschedule] プロジェクトを右クリックし、選択**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="ff080-111">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Solution Explorer, right-click the SSOSchedule project, and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="ff080-112">をクリックして**共通プロパティ**を展開し、**アセンブリ**ノード。</span><span class="sxs-lookup"><span data-stu-id="ff080-112">Click **Common Properties**, and expand the **Assembly** node.</span></span>  
  
3.  <span data-ttu-id="ff080-113">SSOSchedule.snk のパスを入力、**アセンブリ キー ファイル**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="ff080-113">Enter the path to SSOSchedule.snk in the **Assembly Key File** text box.</span></span>  
  
4.  <span data-ttu-id="ff080-114">Configuration properties \deployment\server にドット (.) または、コンピューター名が含まれていることを確認し、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="ff080-114">Verify that Configuration Properties\Deployment\Server contains a dot (.) or your computer name, and click **OK**.</span></span>  
  
5.  <span data-ttu-id="ff080-115">ソリューション エクスプ ローラーで右クリック**ssoschedule**、 をクリック**リビルド**です。</span><span class="sxs-lookup"><span data-stu-id="ff080-115">In Solution Explorer, right-click **SSOSchedule**, and click **Rebuild**.</span></span>  
  
6.  <span data-ttu-id="ff080-116">右クリックし、 **ssoschedule**、 をクリック**展開**です。</span><span class="sxs-lookup"><span data-stu-id="ff080-116">Right-click the **SSOSchedule**, and click **Deploy**.</span></span>  
  
## <a name="starting-the-orchestration"></a><span data-ttu-id="ff080-117">オーケストレーションの開始</span><span class="sxs-lookup"><span data-stu-id="ff080-117">Starting the Orchestration</span></span>  
  
#### <a name="to-start-the-orchestration"></a><span data-ttu-id="ff080-118">オーケストレーションを開始するには</span><span class="sxs-lookup"><span data-stu-id="ff080-118">To start the orchestration</span></span>  
  
1.  <span data-ttu-id="ff080-119">BizTalk 管理コンソールで、開始するオーケストレーションを選択します。</span><span class="sxs-lookup"><span data-stu-id="ff080-119">In the BizTalk Administration console, select the orchestration you want to start.</span></span>  
  
2.  <span data-ttu-id="ff080-120">オーケストレーションを右クリックし、をクリックして**開始**です。</span><span class="sxs-lookup"><span data-stu-id="ff080-120">Right-click the orchestration and click **Start**.</span></span>  
  
## <a name="stopping-and-restarting-a-host-instance"></a><span data-ttu-id="ff080-121">停止して、ホスト インスタンスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="ff080-121">Stopping and Restarting a Host Instance</span></span>  
 <span data-ttu-id="ff080-122">サンプルを展開したら、ホスト インスタンスを再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ff080-122">After deploying the sample, you must restart the host instance.</span></span>  
  
#### <a name="to-stop-and-restart-a-host-instance"></a><span data-ttu-id="ff080-123">ホスト インスタンスを停止して再起動するには</span><span class="sxs-lookup"><span data-stu-id="ff080-123">To stop and restart a host instance</span></span>  
  
1.  <span data-ttu-id="ff080-124">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]を選択し、 **BizTalk Server 管理コンソールです。**</span><span class="sxs-lookup"><span data-stu-id="ff080-124">Click **Start**, point to **All Programs**, point to **Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)], and select **BizTalk Server Administration.**</span></span>  
  
2.  <span data-ttu-id="ff080-125">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールをダブルクリックして、 **Microsoft BizTalk Server (ローカル)**  ノードを展開**ホスト**です。</span><span class="sxs-lookup"><span data-stu-id="ff080-125">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, double-click the **Microsoft BizTalk Server (local)** node, and expand **Hosts**.</span></span>  
  
3.  <span data-ttu-id="ff080-126">左側のペインで、 **BizTalkServerApplication**です。</span><span class="sxs-lookup"><span data-stu-id="ff080-126">In the left pane, select the **BizTalkServerApplication**.</span></span>  
  
4.  <span data-ttu-id="ff080-127">右側のウィンドウで、ホスト インスタンス (たとえば、コンピューター名) を右クリックし、をクリックして**停止**です。</span><span class="sxs-lookup"><span data-stu-id="ff080-127">In the right pane, right-click the host instance (for example, the computer name), and click **Stop**.</span></span>  
  
     <span data-ttu-id="ff080-128">ホスト インスタンスの状態に変わる**Stopped**です。</span><span class="sxs-lookup"><span data-stu-id="ff080-128">The status of the host instance changes to **Stopped**.</span></span>  
  
5.  <span data-ttu-id="ff080-129">右側のウィンドウでホスト インスタンスを右クリックし、をクリックして**開始**です。</span><span class="sxs-lookup"><span data-stu-id="ff080-129">In the right pane, right-click the host instance and click **Start**.</span></span>  
  
     <span data-ttu-id="ff080-130">ホスト インスタンスの状態に変わる**開始待ち**です。</span><span class="sxs-lookup"><span data-stu-id="ff080-130">The status of the host instance changes to **Start pending**.</span></span>  
  
     <span data-ttu-id="ff080-131">状態を変更する**を実行している**をクリックして**更新**、またはホスト インスタンスを右クリックし、をクリックして**更新**です。</span><span class="sxs-lookup"><span data-stu-id="ff080-131">To change the status to **Running**, click **Refresh**, or right-click the host instance and then click **Refresh**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff080-132">参照</span><span class="sxs-lookup"><span data-stu-id="ff080-132">See Also</span></span>  
 [<span data-ttu-id="ff080-133">アダプターのセキュリティ</span><span class="sxs-lookup"><span data-stu-id="ff080-133">Security in the adapter</span></span>](../core/security-in-biztalk-adapter-for-jd-edwards-oneworld.md)