---
title: 手順 1:通知を受信するオーケストレーション図形の追加 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4e4c6fa5-81b7-4928-84d5-39533535f862
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 981ab324745840a4ba15e7d552af3f9ff965e3fa
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65367803"
---
# <a name="step-1-add-orchestration-shapes-to-receive-notification"></a><span data-ttu-id="c59de-102">手順 1:通知を受信するオーケストレーション図形を追加します。</span><span class="sxs-lookup"><span data-stu-id="c59de-102">Step 1: Add Orchestration Shapes to Receive Notification</span></span>
<span data-ttu-id="c59de-103">![ステップ 1/3](../../adapters-and-accelerators/adapter-oracle-database/media/step-1of3.gif "Step_1of3")</span><span class="sxs-lookup"><span data-stu-id="c59de-103">![Step 1 of 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-1of3.gif "Step_1of3")</span></span>  
  
 <span data-ttu-id="c59de-104">**所要時間:** 5 分</span><span class="sxs-lookup"><span data-stu-id="c59de-104">**Time to complete:** 5 minutes</span></span>  
  
 <span data-ttu-id="c59de-105">**目標:** この手順への変更の通知を受信するオーケストレーション図形を追加、**従業員**テーブル。</span><span class="sxs-lookup"><span data-stu-id="c59de-105">**Objective:** In this step, you add orchestration shapes to receive notification for changes to the **Employee** table.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="c59de-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="c59de-106">Prerequisites</span></span>  
 <span data-ttu-id="c59de-107">」の手順を完了する必要があります[レッスン 1。スキーマを生成し、メッセージを作成する](../../adapters-and-accelerators/adapter-sql/lesson-1-generate-schemas-and-create-messages.md)します。</span><span class="sxs-lookup"><span data-stu-id="c59de-107">You must have completed the steps in [Lesson 1: Generate Schemas and Create Messages](../../adapters-and-accelerators/adapter-sql/lesson-1-generate-schemas-and-create-messages.md).</span></span>  
  
### <a name="to-receive-notification-messages"></a><span data-ttu-id="c59de-108">通知メッセージを受信するには</span><span class="sxs-lookup"><span data-stu-id="c59de-108">To receive notification messages</span></span>  
  
1.  <span data-ttu-id="c59de-109">BizTalk オーケストレーションを開いて**EmployeeOrch.odx**で追加した[手順 2。BizTalk オーケストレーションのメッセージを作成する](../../adapters-and-accelerators/adapter-sql/step-2-create-messages-for-biztalk-orchestrations.md)します。</span><span class="sxs-lookup"><span data-stu-id="c59de-109">Open the BizTalk orchestration, **EmployeeOrch.odx**, you added in [Step 2: Create Messages for BizTalk Orchestrations](../../adapters-and-accelerators/adapter-sql/step-2-create-messages-for-biztalk-orchestrations.md).</span></span>  
  
2.  <span data-ttu-id="c59de-110">追加、**受信**オーケストレーションへの図形。</span><span class="sxs-lookup"><span data-stu-id="c59de-110">Add a **Receive** shape to the orchestration.</span></span> <span data-ttu-id="c59de-111">オーケストレーション ツールボックスからドラッグして、**受信**図形をオーケストレーション デザイン画面との間の領域にドロップ、**開始**(緑色の円) と**エンド**図形 (赤色の八角形)。</span><span class="sxs-lookup"><span data-stu-id="c59de-111">From the orchestration Toolbox, drag the **Receive** shape to the orchestration design surface, and drop it into the space indicated between the **Begin** (green circle) and **End** (red octagon) shapes.</span></span>  
  
    |<span data-ttu-id="c59de-112">このプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="c59de-112">Set this property</span></span>|<span data-ttu-id="c59de-113">この値を</span><span class="sxs-lookup"><span data-stu-id="c59de-113">To this value</span></span>|  
    |-----------------------|-------------------|  
    |<span data-ttu-id="c59de-114">**Activate**</span><span class="sxs-lookup"><span data-stu-id="c59de-114">**Activate**</span></span>|<span data-ttu-id="c59de-115">True</span><span class="sxs-lookup"><span data-stu-id="c59de-115">True</span></span>|  
    |<span data-ttu-id="c59de-116">**メッセージ**</span><span class="sxs-lookup"><span data-stu-id="c59de-116">**Message**</span></span>|<span data-ttu-id="c59de-117">NotifyReceive</span><span class="sxs-lookup"><span data-stu-id="c59de-117">NotifyReceive</span></span>|  
    |<span data-ttu-id="c59de-118">**名前**</span><span class="sxs-lookup"><span data-stu-id="c59de-118">**Name**</span></span>|<span data-ttu-id="c59de-119">ReceiveNotification</span><span class="sxs-lookup"><span data-stu-id="c59de-119">ReceiveNotification</span></span>|  
  
3.  <span data-ttu-id="c59de-120">追加、一方向受信ポートをオーケストレーションにします。</span><span class="sxs-lookup"><span data-stu-id="c59de-120">Add a one-way receive port to the orchestration.</span></span> <span data-ttu-id="c59de-121">SQL Server データベースから通知メッセージを受信するのににはこのポートを使用します。</span><span class="sxs-lookup"><span data-stu-id="c59de-121">You will use this port to receive notification messages from the SQL Server database.</span></span> <span data-ttu-id="c59de-122">次のポートのプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="c59de-122">Set the following properties for the port.</span></span>  
  
    |<span data-ttu-id="c59de-123">このプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="c59de-123">Set this property</span></span>|<span data-ttu-id="c59de-124">この値を</span><span class="sxs-lookup"><span data-stu-id="c59de-124">To this value</span></span>|  
    |-----------------------|-------------------|  
    |<span data-ttu-id="c59de-125">**通信方向**</span><span class="sxs-lookup"><span data-stu-id="c59de-125">**Communication Direction**</span></span>|<span data-ttu-id="c59de-126">Receive</span><span class="sxs-lookup"><span data-stu-id="c59de-126">Receive</span></span>|  
    |<span data-ttu-id="c59de-127">**通信方式**</span><span class="sxs-lookup"><span data-stu-id="c59de-127">**Communication Pattern**</span></span>|<span data-ttu-id="c59de-128">一方向</span><span class="sxs-lookup"><span data-stu-id="c59de-128">One-Way</span></span>|  
    |<span data-ttu-id="c59de-129">**[Identifier]**</span><span class="sxs-lookup"><span data-stu-id="c59de-129">**Identifier**</span></span>|<span data-ttu-id="c59de-130">ReceiveNotification</span><span class="sxs-lookup"><span data-stu-id="c59de-130">ReceiveNotification</span></span>|  
  
     <span data-ttu-id="c59de-131">また、変更操作名に Operation_1**通知**します。</span><span class="sxs-lookup"><span data-stu-id="c59de-131">Also, change the operation name from Operation_1 to **Notification**.</span></span>  
  
4.  <span data-ttu-id="c59de-132">接続、 **ReceiveNotification**ポートを**ReceiveNotification**アクション図形。</span><span class="sxs-lookup"><span data-stu-id="c59de-132">Connect the **ReceiveNotification** port to the **ReceiveNotification** action shape.</span></span> <span data-ttu-id="c59de-133">オーケストレーション デザイナのデザイン画面で、アクション図形の緑、対応するポート ハンドルのために、緑色の矢印ハンドルをドラッグします。</span><span class="sxs-lookup"><span data-stu-id="c59de-133">In Orchestration Designer, on the design surface, drag the green arrow-shaped handle for the port to the corresponding green handle of the action shape.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c59de-134">この手順では、ドラッグ アンド ドロップを使用するポートをアクション図形に接続します。</span><span class="sxs-lookup"><span data-stu-id="c59de-134">In this step, you use the drag-and-drop method to connect ports to action shapes.</span></span> <span data-ttu-id="c59de-135">アクション図形の操作のプロパティは、アクション図形をポートに接続するのに代わりに使用できます。</span><span class="sxs-lookup"><span data-stu-id="c59de-135">You could instead use the operation property of an action shape to connect the action shape to a port.</span></span>  
  
5.  <span data-ttu-id="c59de-136">次の図は、実行中のオーケストレーションを示します。</span><span class="sxs-lookup"><span data-stu-id="c59de-136">The following figure shows the in-progress orchestration.</span></span>  
  
     <span data-ttu-id="c59de-137">![通知メッセージを受信するオーケストレーション](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-01-receive-notification-orch.gif "sql_adap_tut_01_receive_notification_orch")</span><span class="sxs-lookup"><span data-stu-id="c59de-137">![Orchestration to receive notification messages](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-01-receive-notification-orch.gif "sql_adap_tut_01_receive_notification_orch")</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="c59de-138">でしただけ何か。</span><span class="sxs-lookup"><span data-stu-id="c59de-138">What did I just do?</span></span>  
 <span data-ttu-id="c59de-139">この手順では、オーケストレーション図形を追加し、受信ポート、SQL Server データベースから通知を受信します。</span><span class="sxs-lookup"><span data-stu-id="c59de-139">In this step, you added orchestration shapes and receive port to receive notification from the SQL Server database.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="c59de-140">次の手順</span><span class="sxs-lookup"><span data-stu-id="c59de-140">Next Steps</span></span>  
 <span data-ttu-id="c59de-141">式図形を追加する」の説明に従って、SQL Server データベースから受信した通知の種類を抽出するオーケストレーションに[手順 2。通知の種類を通知メッセージから抽出](../../adapters-and-accelerators/adapter-sql/step-2-extract-notification-type-from-notification-message.md)します。</span><span class="sxs-lookup"><span data-stu-id="c59de-141">You add an expression shape to the orchestration to extract the type of notification received from the SQL Server database, as described in [Step 2: Extract Notification Type from Notification Message](../../adapters-and-accelerators/adapter-sql/step-2-extract-notification-type-from-notification-message.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c59de-142">参照</span><span class="sxs-lookup"><span data-stu-id="c59de-142">See Also</span></span>  
 <span data-ttu-id="c59de-143">[手順 2:通知メッセージからの通知の種類を抽出します。](../../adapters-and-accelerators/adapter-sql/step-2-extract-notification-type-from-notification-message.md) </span><span class="sxs-lookup"><span data-stu-id="c59de-143">[Step 2: Extract Notification Type from Notification Message](../../adapters-and-accelerators/adapter-sql/step-2-extract-notification-type-from-notification-message.md) </span></span>  
 [<span data-ttu-id="c59de-144">レッスン 2:通知を受信してフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="c59de-144">Lesson 2: Receive and Filter Notifications</span></span>](../../adapters-and-accelerators/adapter-sql/lesson-2-receive-and-filter-notifications.md)