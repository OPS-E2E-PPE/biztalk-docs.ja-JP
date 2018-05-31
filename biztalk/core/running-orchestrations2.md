---
title: Orchestrations2 を実行している |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- strong name keys, creating
- orchestrations
- creating strong name keys
- compiling orchestrations
- host instances, stopping and restarting
- deployment, orchestrations
- orchestrations, compiling
- orchestrations, deploying
- stopping host instances
- restarting host instances
ms.assetid: a098d552-d302-44f6-9af9-d77d16549fd3
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 47496b875297e6c16141780979fda933f3968c6b
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25973216"
---
# <a name="running-orchestrations"></a><span data-ttu-id="4a4cb-102">オーケストレーションの実行</span><span class="sxs-lookup"><span data-stu-id="4a4cb-102">Running Orchestrations</span></span>
<span data-ttu-id="4a4cb-103">次の手順では、オーケストレーションのビルド、展開、バインド、および開始の方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4a4cb-103">The following procedures describe how to build, deploy, bind, and start an orchestration.</span></span>  
  
## <a name="creating-a-strong-name-key"></a><span data-ttu-id="4a4cb-104">厳密な名前キーを作成します。</span><span class="sxs-lookup"><span data-stu-id="4a4cb-104">Creating a Strong Name Key</span></span>  
  
#### <a name="to-create-a-strong-name-key"></a><span data-ttu-id="4a4cb-105">厳密な名前のキーを作成するには</span><span class="sxs-lookup"><span data-stu-id="4a4cb-105">To create a strong name key</span></span>  
  
1.  <span data-ttu-id="4a4cb-106">開く、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]コマンド プロンプトです。</span><span class="sxs-lookup"><span data-stu-id="4a4cb-106">Open a [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Command Prompt.</span></span>  
  
2.  <span data-ttu-id="4a4cb-107">既存のプロジェクトのディレクトリに移動し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="4a4cb-107">Change directories to an existing project and press ENTER.</span></span>  
  
     <span data-ttu-id="4a4cb-108">例:</span><span class="sxs-lookup"><span data-stu-id="4a4cb-108">For example:</span></span>  
  
     <span data-ttu-id="4a4cb-109">**\<ドライブ\>: \Adapter_Install\biztalk\my_project**</span><span class="sxs-lookup"><span data-stu-id="4a4cb-109">**\<drive\>:\Adapter_Install\biztalk\my_project**</span></span>  
  
3.  <span data-ttu-id="4a4cb-110">コマンド プロンプトで以下を入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="4a4cb-110">Type the following at the command prompt and press ENTER:</span></span>  
  
     `sn -k SSOSchedule.snk`  
  
## <a name="compiling-and-deploying-an-orchestration"></a><span data-ttu-id="4a4cb-111">オーケストレーションのコンパイルおよび展開</span><span class="sxs-lookup"><span data-stu-id="4a4cb-111">Compiling and Deploying an Orchestration</span></span>  
  
#### <a name="to-compile-and-deploy-an-orchestration"></a><span data-ttu-id="4a4cb-112">オーケストレーションをコンパイルおよび展開するには</span><span class="sxs-lookup"><span data-stu-id="4a4cb-112">To compile and deploy an orchestration</span></span>  
  
1.  <span data-ttu-id="4a4cb-113">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ソリューション エクスプ ローラーを右クリックし、 **[ssoschedule]** プロジェクト、および選択**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="4a4cb-113">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Solution Explorer, right-click the **SSOSchedule** project, and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="4a4cb-114">をクリックして**共通プロパティ**を展開し、**アセンブリ**ノード。</span><span class="sxs-lookup"><span data-stu-id="4a4cb-114">Click **Common Properties**, and expand the **Assembly** node.</span></span>  
  
3.  <span data-ttu-id="4a4cb-115">SSOSchedule.snk のパスを入力、**アセンブリ キー ファイル**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="4a4cb-115">Enter the path to SSOSchedule.snk in the **Assembly Key File** text box.</span></span>  
  
4.  <span data-ttu-id="4a4cb-116">Configuration properties \deployment\server がドット (.) または、コンピューター名であることを確認し、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="4a4cb-116">Verify that Configuration Properties\Deployment\Server is a dot (.) or your computer name, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="4a4cb-117">ソリューション エクスプ ローラーで右クリック **[ssoschedule]**、順にクリック**リビルド**です。</span><span class="sxs-lookup"><span data-stu-id="4a4cb-117">In Solution Explorer, right-click **SSOSchedule**, and then click **Rebuild**.</span></span>  
  
6.  <span data-ttu-id="4a4cb-118">右クリック **[ssoschedule]**、クリックして**展開**です。</span><span class="sxs-lookup"><span data-stu-id="4a4cb-118">Right-click **SSOSchedule**, and then click **Deploy**.</span></span>  
  
## <a name="starting-the-orchestration"></a><span data-ttu-id="4a4cb-119">オーケストレーションの開始</span><span class="sxs-lookup"><span data-stu-id="4a4cb-119">Starting the Orchestration</span></span>  
  
#### <a name="to-start-the-orchestration"></a><span data-ttu-id="4a4cb-120">オーケストレーションを開始するには</span><span class="sxs-lookup"><span data-stu-id="4a4cb-120">To start the orchestration</span></span>  
  
1.  <span data-ttu-id="4a4cb-121">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]、順にクリック**BizTalk Server 管理コンソールです。**</span><span class="sxs-lookup"><span data-stu-id="4a4cb-121">Click **Start**, point to **All Programs**, point to **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)], and then click **BizTalk Server Administration.**</span></span>  
  
2.  <span data-ttu-id="4a4cb-122">BizTalk Server 管理コンソールで、展開**BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開**アプリケーション**、目的の展開クリックしてアプリケーションでは、**オーケストレーション**です。</span><span class="sxs-lookup"><span data-stu-id="4a4cb-122">In the BizTalk Server Administration Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, expand the desired application, and then click **Orchestrations**.</span></span>  
  
3.  <span data-ttu-id="4a4cb-123">詳細ウィンドウで、オーケストレーションを右クリックし、をクリックして**開始**です。</span><span class="sxs-lookup"><span data-stu-id="4a4cb-123">In the details pane, right-click the orchestration and click **Start**.</span></span>  
  
## <a name="stopping-and-restarting-a-host-instance"></a><span data-ttu-id="4a4cb-124">停止して、ホスト インスタンスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="4a4cb-124">Stopping and Restarting a Host Instance</span></span>  
 <span data-ttu-id="4a4cb-125">サンプルを配置した後は、ホスト インスタンスを再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4a4cb-125">After you deploy the sample, you must restart the host instance.</span></span>  
  
#### <a name="to-stop-and-restart-a-host-instance"></a><span data-ttu-id="4a4cb-126">ホスト インスタンスを停止して再起動するには</span><span class="sxs-lookup"><span data-stu-id="4a4cb-126">To stop and restart a host instance</span></span>  
  
1.  <span data-ttu-id="4a4cb-127">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]、順にクリック**BizTalk Server 管理コンソールです。**</span><span class="sxs-lookup"><span data-stu-id="4a4cb-127">Click **Start**, point to **All Programs**, point to **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)], and then click **BizTalk Server Administration.**</span></span>  
  
2.  <span data-ttu-id="4a4cb-128">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、 **BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開**プラットフォームの設定**をクリックして**ホスト インスタンスの**します。</span><span class="sxs-lookup"><span data-stu-id="4a4cb-128">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Platform Settings**, and then click **Host Instances**.</span></span>  
  
3.  <span data-ttu-id="4a4cb-129">右側のウィンドウで、ホスト インスタンス (たとえば、コンピューター名) を右クリックし、をクリックして**停止**です。</span><span class="sxs-lookup"><span data-stu-id="4a4cb-129">In the right pane, right-click the host instance (for example, the computer name), and click **Stop**.</span></span>  
  
     <span data-ttu-id="4a4cb-130">ホスト インスタンスの状態に変わる**Stopped**です。</span><span class="sxs-lookup"><span data-stu-id="4a4cb-130">The status of the host instance changes to **Stopped**.</span></span>  
  
4.  <span data-ttu-id="4a4cb-131">右側のウィンドウでホスト インスタンスを右クリックし、をクリックして**開始**です。</span><span class="sxs-lookup"><span data-stu-id="4a4cb-131">In the right pane, right-click the host instance and click **Start**.</span></span>  
  
     <span data-ttu-id="4a4cb-132">ホスト インスタンスの状態に変わる**開始待ち**です。</span><span class="sxs-lookup"><span data-stu-id="4a4cb-132">The status of the host instance changes to **Start pending**.</span></span>  
  
     <span data-ttu-id="4a4cb-133">状態を変更する**を実行している** をクリック**更新**、または、ホスト インスタンスを右クリックし、をクリックして**更新**です。</span><span class="sxs-lookup"><span data-stu-id="4a4cb-133">To change the status to **Running** and click **Refresh**, or right-click the host instance and then click **Refresh**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a4cb-134">参照</span><span class="sxs-lookup"><span data-stu-id="4a4cb-134">See Also</span></span>  
 [<span data-ttu-id="4a4cb-135">アダプターのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="4a4cb-135">Secure the adapter</span></span>](../core/security-in-biztalk-adapter-for-peoplesoft-enterprise.md)