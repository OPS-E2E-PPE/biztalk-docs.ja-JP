---
title: Orchestrations2 を実行している |。Microsoft Docs
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
ms.openlocfilehash: c43c0694397f024b692012f7e2846e6ff38bbd14
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65254517"
---
# <a name="running-orchestrations"></a><span data-ttu-id="894a0-102">オーケストレーションの実行</span><span class="sxs-lookup"><span data-stu-id="894a0-102">Running Orchestrations</span></span>
<span data-ttu-id="894a0-103">次の手順では、構築、展開、バインド、およびオーケストレーションを開始する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="894a0-103">The following procedures describe how to build, deploy, bind, and start an orchestration.</span></span>  
  
## <a name="creating-a-strong-name-key"></a><span data-ttu-id="894a0-104">厳密な名前キーを作成します。</span><span class="sxs-lookup"><span data-stu-id="894a0-104">Creating a Strong Name Key</span></span>  
  
#### <a name="to-create-a-strong-name-key"></a><span data-ttu-id="894a0-105">厳密な名前キーを作成するには</span><span class="sxs-lookup"><span data-stu-id="894a0-105">To create a strong name key</span></span>  
  
1. <span data-ttu-id="894a0-106">開く、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]コマンド プロンプト。</span><span class="sxs-lookup"><span data-stu-id="894a0-106">Open a [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Command Prompt.</span></span>  
  
2. <span data-ttu-id="894a0-107">既存のプロジェクトにディレクトリを変更し、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="894a0-107">Change directories to an existing project and press ENTER.</span></span>  
  
    <span data-ttu-id="894a0-108">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="894a0-108">For example:</span></span>  
  
    <span data-ttu-id="894a0-109">**\<drive\>:\Adapter_Install\biztalk\my_project**</span><span class="sxs-lookup"><span data-stu-id="894a0-109">**\<drive\>:\Adapter_Install\biztalk\my_project**</span></span>  
  
3. <span data-ttu-id="894a0-110">コマンド プロンプトで、次を入力し、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="894a0-110">Type the following at the command prompt and press ENTER:</span></span>  
  
    `sn -k SSOSchedule.snk`  
  
## <a name="compiling-and-deploying-an-orchestration"></a><span data-ttu-id="894a0-111">コンパイルして、オーケストレーションの展開</span><span class="sxs-lookup"><span data-stu-id="894a0-111">Compiling and Deploying an Orchestration</span></span>  
  
#### <a name="to-compile-and-deploy-an-orchestration"></a><span data-ttu-id="894a0-112">コンパイルして、オーケストレーションを展開するには</span><span class="sxs-lookup"><span data-stu-id="894a0-112">To compile and deploy an orchestration</span></span>  
  
1. <span data-ttu-id="894a0-113">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ソリューション エクスプ ローラーを右クリックし、 **[ssoschedule]** 順に選択して、**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="894a0-113">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Solution Explorer, right-click the **SSOSchedule** project, and select **Properties**.</span></span>  
  
2. <span data-ttu-id="894a0-114">クリックして**共通プロパティ**、展開、**アセンブリ**ノード。</span><span class="sxs-lookup"><span data-stu-id="894a0-114">Click **Common Properties**, and expand the **Assembly** node.</span></span>  
  
3. <span data-ttu-id="894a0-115">SSOSchedule.snk のパスを入力、**アセンブリ キー ファイル**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="894a0-115">Enter the path to SSOSchedule.snk in the **Assembly Key File** text box.</span></span>  
  
4. <span data-ttu-id="894a0-116">Configuration properties \deployment\server がドット (.) または、コンピューター名であることを確認し、をクリックし、 **OK**します。</span><span class="sxs-lookup"><span data-stu-id="894a0-116">Verify that Configuration Properties\Deployment\Server is a dot (.) or your computer name, and then click **OK**.</span></span>  
  
5. <span data-ttu-id="894a0-117">ソリューション エクスプ ローラーで右クリック**ssoschedule**、 をクリックし、**リビルド**します。</span><span class="sxs-lookup"><span data-stu-id="894a0-117">In Solution Explorer, right-click **SSOSchedule**, and then click **Rebuild**.</span></span>  
  
6. <span data-ttu-id="894a0-118">右クリック**ssoschedule**、 をクリックし、**デプロイ**します。</span><span class="sxs-lookup"><span data-stu-id="894a0-118">Right-click **SSOSchedule**, and then click **Deploy**.</span></span>  
  
## <a name="starting-the-orchestration"></a><span data-ttu-id="894a0-119">オーケストレーションの開始</span><span class="sxs-lookup"><span data-stu-id="894a0-119">Starting the Orchestration</span></span>  
  
#### <a name="to-start-the-orchestration"></a><span data-ttu-id="894a0-120">オーケストレーションを開始するには</span><span class="sxs-lookup"><span data-stu-id="894a0-120">To start the orchestration</span></span>  
  
1. <span data-ttu-id="894a0-121">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]、順にクリックします**BizTalk Server 管理コンソール。**</span><span class="sxs-lookup"><span data-stu-id="894a0-121">Click **Start**, point to **All Programs**, point to **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)], and then click **BizTalk Server Administration.**</span></span>  
  
2. <span data-ttu-id="894a0-122">BizTalk Server 管理コンソールで  **BizTalk Server 管理**、展開**BizTalk グループ**、展開**アプリケーション**、必要な展開アプリケーション、およびクリック**オーケストレーション**します。</span><span class="sxs-lookup"><span data-stu-id="894a0-122">In the BizTalk Server Administration Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, expand the desired application, and then click **Orchestrations**.</span></span>  
  
3. <span data-ttu-id="894a0-123">詳細ペインで、オーケストレーションを右クリックし、をクリックして**開始**します。</span><span class="sxs-lookup"><span data-stu-id="894a0-123">In the details pane, right-click the orchestration and click **Start**.</span></span>  
  
## <a name="stopping-and-restarting-a-host-instance"></a><span data-ttu-id="894a0-124">停止して、ホスト インスタンスの再起動</span><span class="sxs-lookup"><span data-stu-id="894a0-124">Stopping and Restarting a Host Instance</span></span>  
 <span data-ttu-id="894a0-125">サンプルをデプロイした後は、ホスト インスタンスを再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="894a0-125">After you deploy the sample, you must restart the host instance.</span></span>  
  
#### <a name="to-stop-and-restart-a-host-instance"></a><span data-ttu-id="894a0-126">停止して、ホスト インスタンスを再起動するには</span><span class="sxs-lookup"><span data-stu-id="894a0-126">To stop and restart a host instance</span></span>  
  
1. <span data-ttu-id="894a0-127">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]、順にクリックします**BizTalk Server 管理コンソール。**</span><span class="sxs-lookup"><span data-stu-id="894a0-127">Click **Start**, point to **All Programs**, point to **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)], and then click **BizTalk Server Administration.**</span></span>  
  
2. <span data-ttu-id="894a0-128">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、 **BizTalk Server 管理**、展開**BizTalk グループ**、展開**プラットフォームの設定**順にクリックします**ホスト インスタンスの**します。</span><span class="sxs-lookup"><span data-stu-id="894a0-128">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Platform Settings**, and then click **Host Instances**.</span></span>  
  
3. <span data-ttu-id="894a0-129">右側のウィンドウでホスト インスタンス (たとえば、コンピューター名) を右クリックし、をクリックして**停止**します。</span><span class="sxs-lookup"><span data-stu-id="894a0-129">In the right pane, right-click the host instance (for example, the computer name), and click **Stop**.</span></span>  
  
    <span data-ttu-id="894a0-130">ホスト インスタンスの状態に変わる**Stopped**します。</span><span class="sxs-lookup"><span data-stu-id="894a0-130">The status of the host instance changes to **Stopped**.</span></span>  
  
4. <span data-ttu-id="894a0-131">右側のウィンドウで、ホスト インスタンスを右クリックし、をクリックして**開始**します。</span><span class="sxs-lookup"><span data-stu-id="894a0-131">In the right pane, right-click the host instance and click **Start**.</span></span>  
  
    <span data-ttu-id="894a0-132">ホスト インスタンスの状態に変わる**開始待ち**します。</span><span class="sxs-lookup"><span data-stu-id="894a0-132">The status of the host instance changes to **Start pending**.</span></span>  
  
    <span data-ttu-id="894a0-133">状態を変更する**を実行している** をクリック**更新**、またはホスト インスタンスを右クリックし、をクリックし、**更新**します。</span><span class="sxs-lookup"><span data-stu-id="894a0-133">To change the status to **Running** and click **Refresh**, or right-click the host instance and then click **Refresh**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="894a0-134">参照</span><span class="sxs-lookup"><span data-stu-id="894a0-134">See Also</span></span>  
 [<span data-ttu-id="894a0-135">アダプターのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="894a0-135">Secure the adapter</span></span>](../core/security-in-biztalk-adapter-for-peoplesoft-enterprise.md)