---
title: "手順 3: を構成し、アプリケーションを起動 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e4252470-805e-404f-80d5-df8d1ff3af63
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 96f26035094ee6e39b672b480525747f8aaf4ede
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-3-configure-and-start-the-application"></a><span data-ttu-id="a6cf6-102">手順 3: を構成し、アプリケーションを起動</span><span class="sxs-lookup"><span data-stu-id="a6cf6-102">Step 3: Configure and Start the Application</span></span>
<span data-ttu-id="a6cf6-103">![手順 4 の 3](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-3of4.gif "Step_3of4")</span><span class="sxs-lookup"><span data-stu-id="a6cf6-103">![Step 3 of 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-3of4.gif "Step_3of4")</span></span>  
  
 <span data-ttu-id="a6cf6-104">**所要時間:** 10 分</span><span class="sxs-lookup"><span data-stu-id="a6cf6-104">**Time to complete:** 10 minutes</span></span>  
  
 <span data-ttu-id="a6cf6-105">**目標:**この手順で構成して SampleApplication アプリケーションを起動します。</span><span class="sxs-lookup"><span data-stu-id="a6cf6-105">**Objective:** In this step, you configure and start the SampleApplication application.</span></span> <span data-ttu-id="a6cf6-106">作成した論理アイテムに関連付ける SampleApplication アプリケーションを構成するときに[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]物理対応するとします。</span><span class="sxs-lookup"><span data-stu-id="a6cf6-106">When you configure the SampleApplication application, you associate the logical artifacts you created in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] with their physical counterparts.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="a6cf6-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="a6cf6-107">Prerequisites</span></span>  
 <span data-ttu-id="a6cf6-108">完了する必要があります[手順 2: ポートを構成する](../../adapters-and-accelerators/adapter-sql/step-2-configure-the-ports.md)です。</span><span class="sxs-lookup"><span data-stu-id="a6cf6-108">You must have completed [Step 2: Configure the Ports](../../adapters-and-accelerators/adapter-sql/step-2-configure-the-ports.md).</span></span>  
  
### <a name="to-configure-and-start-the-application"></a><span data-ttu-id="a6cf6-109">構成し、アプリケーションの起動</span><span class="sxs-lookup"><span data-stu-id="a6cf6-109">To configure and start the application</span></span>  
  
1.  <span data-ttu-id="a6cf6-110">開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="a6cf6-110">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="a6cf6-111">コンソール ツリーで、左側で、展開**BizTalk Server 管理コンソール**を右クリックして**BizTalk グループ**、順にクリック**更新**です。</span><span class="sxs-lookup"><span data-stu-id="a6cf6-111">In the console tree on the left hand side, expand **BizTalk Server Administration**, right-click **BizTalk Group**, and then click **Refresh**.</span></span>  
  
3.  <span data-ttu-id="a6cf6-112">展開**BizTalk グループ**、展開**アプリケーション**を右クリックして**SampleApplication**をクリックし、**構成**です。</span><span class="sxs-lookup"><span data-stu-id="a6cf6-112">Expand **BizTalk Group**, expand **Applications**, right-click **SampleApplication**, and then click **Configure**.</span></span>  
  
4.  <span data-ttu-id="a6cf6-113">**アプリケーションの構成** ダイアログ ボックスで、 **EmployeeOrch**  タブで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="a6cf6-113">In the **Configure Application** dialog box, on the **EmployeeOrch** tab, do the following:</span></span>  
  
    1.  <span data-ttu-id="a6cf6-114">**ホスト**ドロップダウン リストで、 **BizTalkServerApplication**です。</span><span class="sxs-lookup"><span data-stu-id="a6cf6-114">For **Host** drop-down list, select **BizTalkServerApplication**.</span></span>  
  
    2.  <span data-ttu-id="a6cf6-115">全体でセルをダブルクリックして**ReceiveNotification**選択**NotifyReceivePort**ドロップダウン リストからです。</span><span class="sxs-lookup"><span data-stu-id="a6cf6-115">Double-click the cell across **ReceiveNotification** and select **NotifyReceivePort** from the drop-down list.</span></span>  
  
    3.  <span data-ttu-id="a6cf6-116">全体でセルをダブルクリックして**SQLOutboundPort**選択**SQLOutboundPort**ドロップダウン リストからです。</span><span class="sxs-lookup"><span data-stu-id="a6cf6-116">Double-click the cell across **SQLOutboundPort** and select **SQLOutboundPort** from the drop-down list.</span></span>  
  
    4.  <span data-ttu-id="a6cf6-117">全体でセルをダブルクリックして**SaveResponsePort**選択**EmailResponse**ドロップダウン リストからです。</span><span class="sxs-lookup"><span data-stu-id="a6cf6-117">Double-click the cell across **SaveResponsePort** and select **EmailResponse** from the drop-down list.</span></span>  
  
5.  <span data-ttu-id="a6cf6-118">次の図は、構成されたアプリケーションを示します。</span><span class="sxs-lookup"><span data-stu-id="a6cf6-118">The following figure shows a configured application.</span></span>  
  
     <span data-ttu-id="a6cf6-119">![アプリケーションの構成](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-011-configure-app.gif "sql_adap_tut_011_configure_app")</span><span class="sxs-lookup"><span data-stu-id="a6cf6-119">![Configured application](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-011-configure-app.gif "sql_adap_tut_011_configure_app")</span></span>  
  
6.  <span data-ttu-id="a6cf6-120">**アプリケーションの構成**ダイアログ ボックスで、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="a6cf6-120">In the **Configure Application** dialog box, click **OK**.</span></span>  
  
7.  <span data-ttu-id="a6cf6-121">コンソール ツリーを右クリックして**SampleApplication**、クリックして**開始**です。</span><span class="sxs-lookup"><span data-stu-id="a6cf6-121">In the console tree, right-click **SampleApplication**, and then click **Start**.</span></span>  
  
8.  <span data-ttu-id="a6cf6-122">コンソール ツリーでクリックして**アプリケーション**です。</span><span class="sxs-lookup"><span data-stu-id="a6cf6-122">In the console tree, click **Applications**.</span></span>  
  
9. <span data-ttu-id="a6cf6-123">アプリケーションの詳細ウィンドウで、ことを確認、**ステータス**の**SampleApplication**は**Started**です。</span><span class="sxs-lookup"><span data-stu-id="a6cf6-123">In the Applications details pane, check that the **Status** of **SampleApplication** is **Started**.</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="a6cf6-124">でしただけは何ですか。</span><span class="sxs-lookup"><span data-stu-id="a6cf6-124">What did I just do?</span></span>  
 <span data-ttu-id="a6cf6-125">構成および SampleApplication アプリケーションを開始します。</span><span class="sxs-lookup"><span data-stu-id="a6cf6-125">You configured and started the SampleApplication application</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="a6cf6-126">次の手順</span><span class="sxs-lookup"><span data-stu-id="a6cf6-126">Next Steps</span></span>  
 <span data-ttu-id="a6cf6-127">新しい従業員を挿入することで、アプリケーションをテストする、**従業員**」の説明に従っての表に、[手順 4: アプリケーションをテストする](../../adapters-and-accelerators/adapter-sql/step-4-test-the-application.md)です。</span><span class="sxs-lookup"><span data-stu-id="a6cf6-127">You test the application by inserting new employees in the **Employee** table, as described in [Step 4: Test the Application](../../adapters-and-accelerators/adapter-sql/step-4-test-the-application.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6cf6-128">参照</span><span class="sxs-lookup"><span data-stu-id="a6cf6-128">See Also</span></span>  
 <span data-ttu-id="a6cf6-129">[手順 2: ポートを構成します。](../../adapters-and-accelerators/adapter-sql/step-2-configure-the-ports.md) </span><span class="sxs-lookup"><span data-stu-id="a6cf6-129">[Step 2: Configure the Ports](../../adapters-and-accelerators/adapter-sql/step-2-configure-the-ports.md) </span></span>  
 <span data-ttu-id="a6cf6-130">[手順 4: アプリケーションをテストします。](../../adapters-and-accelerators/adapter-sql/step-4-test-the-application.md) </span><span class="sxs-lookup"><span data-stu-id="a6cf6-130">[Step 4: Test the Application](../../adapters-and-accelerators/adapter-sql/step-4-test-the-application.md) </span></span>  
 [<span data-ttu-id="a6cf6-131">レッスン 5: ソリューションを配置します。</span><span class="sxs-lookup"><span data-stu-id="a6cf6-131">Lesson 5: Deploy the Solution</span></span>](../../adapters-and-accelerators/adapter-sql/lesson-5-deploy-the-solution.md)