---
title: '手順 3: 構成し、アプリケーションを起動します |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e4252470-805e-404f-80d5-df8d1ff3af63
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9f932ca1f3570f080de239dd90c52d9a5f5db721
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988203"
---
# <a name="step-3-configure-and-start-the-application"></a><span data-ttu-id="71927-102">手順 3: 構成し、アプリケーションを起動します</span><span class="sxs-lookup"><span data-stu-id="71927-102">Step 3: Configure and Start the Application</span></span>
<span data-ttu-id="71927-103">![手順 4 の 3](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-3of4.gif "Step_3of4")</span><span class="sxs-lookup"><span data-stu-id="71927-103">![Step 3 of 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-3of4.gif "Step_3of4")</span></span>  
  
 <span data-ttu-id="71927-104">**所要時間:** 10 分</span><span class="sxs-lookup"><span data-stu-id="71927-104">**Time to complete:** 10 minutes</span></span>  
  
 <span data-ttu-id="71927-105">**目標:** この手順で構成し、SampleApplication アプリケーションを起動します。</span><span class="sxs-lookup"><span data-stu-id="71927-105">**Objective:** In this step, you configure and start the SampleApplication application.</span></span> <span data-ttu-id="71927-106">作成した論理アイテムを関連付ける SampleApplication アプリケーションを構成するときに[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]物理対応します。</span><span class="sxs-lookup"><span data-stu-id="71927-106">When you configure the SampleApplication application, you associate the logical artifacts you created in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] with their physical counterparts.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="71927-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="71927-107">Prerequisites</span></span>  
 <span data-ttu-id="71927-108">完了する必要があります[手順 2: ポートを構成する](../../adapters-and-accelerators/adapter-sql/step-2-configure-the-ports.md)します。</span><span class="sxs-lookup"><span data-stu-id="71927-108">You must have completed [Step 2: Configure the Ports](../../adapters-and-accelerators/adapter-sql/step-2-configure-the-ports.md).</span></span>  
  
### <a name="to-configure-and-start-the-application"></a><span data-ttu-id="71927-109">構成して、アプリケーションを起動するには</span><span class="sxs-lookup"><span data-stu-id="71927-109">To configure and start the application</span></span>  
  
1. <span data-ttu-id="71927-110">開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="71927-110">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2. <span data-ttu-id="71927-111">左側にあるコンソール ツリーで [ **BizTalk Server 管理**を右クリックして**BizTalk グループ**、] をクリックし、**更新**します。</span><span class="sxs-lookup"><span data-stu-id="71927-111">In the console tree on the left hand side, expand **BizTalk Server Administration**, right-click **BizTalk Group**, and then click **Refresh**.</span></span>  
  
3. <span data-ttu-id="71927-112">展開**BizTalk グループ**、展開**アプリケーション**、右クリックして**SampleApplication**、順にクリックします**構成**します。</span><span class="sxs-lookup"><span data-stu-id="71927-112">Expand **BizTalk Group**, expand **Applications**, right-click **SampleApplication**, and then click **Configure**.</span></span>  
  
4. <span data-ttu-id="71927-113">**アプリケーションの構成** ダイアログ ボックスで、 **EmployeeOrch**  タブで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="71927-113">In the **Configure Application** dialog box, on the **EmployeeOrch** tab, do the following:</span></span>  
  
   1.  <span data-ttu-id="71927-114">**ホスト**ドロップダウン リストで、 **BizTalkServerApplication**します。</span><span class="sxs-lookup"><span data-stu-id="71927-114">For **Host** drop-down list, select **BizTalkServerApplication**.</span></span>  
  
   2.  <span data-ttu-id="71927-115">セルをダブルクリックして**ReceiveNotification**選択**NotifyReceivePort**ドロップダウン リストから。</span><span class="sxs-lookup"><span data-stu-id="71927-115">Double-click the cell across **ReceiveNotification** and select **NotifyReceivePort** from the drop-down list.</span></span>  
  
   3.  <span data-ttu-id="71927-116">セルをダブルクリックして**SQLOutboundPort**選択**SQLOutboundPort**ドロップダウン リストから。</span><span class="sxs-lookup"><span data-stu-id="71927-116">Double-click the cell across **SQLOutboundPort** and select **SQLOutboundPort** from the drop-down list.</span></span>  
  
   4.  <span data-ttu-id="71927-117">セルをダブルクリックして**SaveResponsePort**選択**EmailResponse**ドロップダウン リストから。</span><span class="sxs-lookup"><span data-stu-id="71927-117">Double-click the cell across **SaveResponsePort** and select **EmailResponse** from the drop-down list.</span></span>  
  
5. <span data-ttu-id="71927-118">次の図は、構成されたアプリケーションを示します。</span><span class="sxs-lookup"><span data-stu-id="71927-118">The following figure shows a configured application.</span></span>  
  
    <span data-ttu-id="71927-119">![アプリケーションが構成されている](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-011-configure-app.gif "sql_adap_tut_011_configure_app")</span><span class="sxs-lookup"><span data-stu-id="71927-119">![Configured application](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-011-configure-app.gif "sql_adap_tut_011_configure_app")</span></span>  
  
6. <span data-ttu-id="71927-120">**アプリケーションの構成**ダイアログ ボックスで、をクリックして**OK**します。</span><span class="sxs-lookup"><span data-stu-id="71927-120">In the **Configure Application** dialog box, click **OK**.</span></span>  
  
7. <span data-ttu-id="71927-121">コンソール ツリーで、右クリック**SampleApplication**、 をクリックし、**開始**します。</span><span class="sxs-lookup"><span data-stu-id="71927-121">In the console tree, right-click **SampleApplication**, and then click **Start**.</span></span>  
  
8. <span data-ttu-id="71927-122">コンソール ツリーで、クリックして**アプリケーション**します。</span><span class="sxs-lookup"><span data-stu-id="71927-122">In the console tree, click **Applications**.</span></span>  
  
9. <span data-ttu-id="71927-123">アプリケーションの詳細ペインでいることを確認、**状態**の**SampleApplication**は**開始**します。</span><span class="sxs-lookup"><span data-stu-id="71927-123">In the Applications details pane, check that the **Status** of **SampleApplication** is **Started**.</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="71927-124">でしただけ何か。</span><span class="sxs-lookup"><span data-stu-id="71927-124">What did I just do?</span></span>  
 <span data-ttu-id="71927-125">構成を SampleApplication アプリケーションを開始します。</span><span class="sxs-lookup"><span data-stu-id="71927-125">You configured and started the SampleApplication application</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="71927-126">次の手順</span><span class="sxs-lookup"><span data-stu-id="71927-126">Next Steps</span></span>  
 <span data-ttu-id="71927-127">新しく加わる従業員を挿入して、アプリケーションをテストする、**従業員**」の説明に従って、テーブル[手順 4: アプリケーションをテストする](../../adapters-and-accelerators/adapter-sql/step-4-test-the-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="71927-127">You test the application by inserting new employees in the **Employee** table, as described in [Step 4: Test the Application](../../adapters-and-accelerators/adapter-sql/step-4-test-the-application.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71927-128">参照</span><span class="sxs-lookup"><span data-stu-id="71927-128">See Also</span></span>  
 <span data-ttu-id="71927-129">[手順 2: ポートを構成します。](../../adapters-and-accelerators/adapter-sql/step-2-configure-the-ports.md) </span><span class="sxs-lookup"><span data-stu-id="71927-129">[Step 2: Configure the Ports](../../adapters-and-accelerators/adapter-sql/step-2-configure-the-ports.md) </span></span>  
 <span data-ttu-id="71927-130">[手順 4: アプリケーションをテストします。](../../adapters-and-accelerators/adapter-sql/step-4-test-the-application.md) </span><span class="sxs-lookup"><span data-stu-id="71927-130">[Step 4: Test the Application](../../adapters-and-accelerators/adapter-sql/step-4-test-the-application.md) </span></span>  
 [<span data-ttu-id="71927-131">レッスン 5: ソリューションを展開する</span><span class="sxs-lookup"><span data-stu-id="71927-131">Lesson 5: Deploy the Solution</span></span>](../../adapters-and-accelerators/adapter-sql/lesson-5-deploy-the-solution.md)