---
title: 手順 2:通知の種類を通知メッセージから抽出 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 72f3e805-0f5f-42fa-8fe3-78ccbb375f74
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5cca1b44daa45f5502957fa783cdf5e4e2ebca1e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65367787"
---
# <a name="step-2-extract-notification-type-from-notification-message"></a><span data-ttu-id="c3202-102">手順 2:通知メッセージからの通知の種類を抽出します。</span><span class="sxs-lookup"><span data-stu-id="c3202-102">Step 2: Extract Notification Type from Notification Message</span></span>
<span data-ttu-id="c3202-103">![ステップ 2/3](../../adapters-and-accelerators/adapter-oracle-database/media/step-2of3.gif "Step_2of3")</span><span class="sxs-lookup"><span data-stu-id="c3202-103">![Step 2 of 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-2of3.gif "Step_2of3")</span></span>  
  
 <span data-ttu-id="c3202-104">**所要時間:** 5 分</span><span class="sxs-lookup"><span data-stu-id="c3202-104">**Time to complete:** 5 minutes</span></span>  
  
 <span data-ttu-id="c3202-105">**目標:** この手順では、SQL Server データベースから受信した通知の種類を抽出する式図形を追加します。</span><span class="sxs-lookup"><span data-stu-id="c3202-105">**Objective:** In this step, you add an expression shape to extract the type of notification received from the SQL Server database.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="c3202-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="c3202-106">Prerequisites</span></span>  
 <span data-ttu-id="c3202-107">完了する必要があります[手順 1。通知を受信するオーケストレーション図形を追加](../../adapters-and-accelerators/adapter-sql/step-1-add-orchestration-shapes-to-receive-notification.md)します。</span><span class="sxs-lookup"><span data-stu-id="c3202-107">You must have completed [Step 1: Add Orchestration Shapes to Receive Notification](../../adapters-and-accelerators/adapter-sql/step-1-add-orchestration-shapes-to-receive-notification.md).</span></span>  
  
### <a name="to-extract-the-notification-type-from-the-notification-message"></a><span data-ttu-id="c3202-108">通知の種類を通知メッセージから抽出するには</span><span class="sxs-lookup"><span data-stu-id="c3202-108">To extract the notification type from the notification message</span></span>  
  
1.  <span data-ttu-id="c3202-109">作成した BizTalk オーケストレーションに変数を追加[手順 1。通知を受信するオーケストレーション図形を追加](../../adapters-and-accelerators/adapter-sql/step-1-add-orchestration-shapes-to-receive-notification.md)します。</span><span class="sxs-lookup"><span data-stu-id="c3202-109">Add a variable to the BizTalk orchestration you created in [Step 1: Add Orchestration Shapes to Receive Notification](../../adapters-and-accelerators/adapter-sql/step-1-add-orchestration-shapes-to-receive-notification.md).</span></span>  
  
    1.  <span data-ttu-id="c3202-110">オーケストレーションの種類を右クリックして**変数**、 をクリックし、**新しい変数**します。</span><span class="sxs-lookup"><span data-stu-id="c3202-110">From the Orchestration View, right-click **Variables**, and then click **New Variable**.</span></span>  
  
    2.  <span data-ttu-id="c3202-111">新しい変数を右クリックして**Variable_1**、 をクリック**プロパティ ウィンドウ**します。</span><span class="sxs-lookup"><span data-stu-id="c3202-111">Right-click the new variable, **Variable_1**, and click **Properties Window**.</span></span> <span data-ttu-id="c3202-112">変数の次のプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="c3202-112">Set the following properties for the variable.</span></span>  
  
        |<span data-ttu-id="c3202-113">このプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="c3202-113">Set this property</span></span>|<span data-ttu-id="c3202-114">この値を</span><span class="sxs-lookup"><span data-stu-id="c3202-114">To this value</span></span>|  
        |-----------------------|-------------------|  
        |<span data-ttu-id="c3202-115">**[Identifier]**</span><span class="sxs-lookup"><span data-stu-id="c3202-115">**Identifier**</span></span>|<span data-ttu-id="c3202-116">notificationType</span><span class="sxs-lookup"><span data-stu-id="c3202-116">NotificationType</span></span>|  
        |<span data-ttu-id="c3202-117">**型**</span><span class="sxs-lookup"><span data-stu-id="c3202-117">**Type**</span></span>|<span data-ttu-id="c3202-118">System.String</span><span class="sxs-lookup"><span data-stu-id="c3202-118">System.String</span></span>|  
  
2.  <span data-ttu-id="c3202-119">追加、**式**BizTalk オーケストレーションに図形。</span><span class="sxs-lookup"><span data-stu-id="c3202-119">Add an **Expression** shape to the BizTalk orchestration.</span></span> <span data-ttu-id="c3202-120">オーケストレーション ツールボックスからドラッグして、**式**図形をオーケストレーション デザイン画面と、ドロップした後、**受信**図形</span><span class="sxs-lookup"><span data-stu-id="c3202-120">From the orchestration Toolbox, drag the **Expression** shape to the orchestration design surface, and drop it after the **Receive** shape</span></span>  
  
     <span data-ttu-id="c3202-121">内で、**式**図形、SQL Server から受信した通知メッセージの種類を抽出する xpath クエリを追加します。</span><span class="sxs-lookup"><span data-stu-id="c3202-121">Within the **Expression** shape, you will add an xpath query to extract the type of notification message received from SQL Server.</span></span> <span data-ttu-id="c3202-122">Xpath クエリを作成する前に、通知メッセージの形式について見てみましょう。</span><span class="sxs-lookup"><span data-stu-id="c3202-122">Before creating an xpath query, let us look at the format of a notification message.</span></span> <span data-ttu-id="c3202-123">一般的な通知メッセージには、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="c3202-123">A typical notification message resembles the following:</span></span>  
  
    ```  
    <Notification xmlns="http://schemas.microsoft.com/Sql/2008/05/Notification/">  
      <Info>Insert</Info>   
      <Source>Data</Source>   
      <Type>Change</Type>   
    </Notification>  
    ```  
  
3.  <span data-ttu-id="c3202-124">通知の種類に関する情報は内で使用できるように、`<info>`親内のタグ`<Notification>`タグ。</span><span class="sxs-lookup"><span data-stu-id="c3202-124">As you see, the information about the type of the notification is available within the `<info>` tag, within the parent `<Notification>` tag.</span></span> <span data-ttu-id="c3202-125">そのため、次の xpath クエリ内の追加、**式**図形。</span><span class="sxs-lookup"><span data-stu-id="c3202-125">So, add the following xpath query within the **Expression** shape:</span></span>  
  
    ```  
    NotificationType = xpath(NotifyReceive,"string(/*[local-name()='Notification']/*[local-name()='Info']/text())");  
    ```  
  
     <span data-ttu-id="c3202-126">ここでは、 **NotificationType** xpath クエリによって抽出された値を格納するために作成する変数です。</span><span class="sxs-lookup"><span data-stu-id="c3202-126">Here, **NotificationType** is the variable you created to store the value extracted by the xpath query.</span></span> <span data-ttu-id="c3202-127">**NotifyReceive**で作成したメッセージは、[手順 2。BizTalk オーケストレーションのメッセージを作成する](../../adapters-and-accelerators/adapter-sql/step-2-create-messages-for-biztalk-orchestrations.md)通知メッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="c3202-127">**NotifyReceive** is the message you created in [Step 2: Create Messages for BizTalk Orchestrations](../../adapters-and-accelerators/adapter-sql/step-2-create-messages-for-biztalk-orchestrations.md) to receive notification messages.</span></span>  
  
4.  <span data-ttu-id="c3202-128">次の図は、進行中のオーケストレーション、**式**図形が含まれています。</span><span class="sxs-lookup"><span data-stu-id="c3202-128">The following figure shows the in-progress orchestration with the **Expression** shape included.</span></span>  
  
     <span data-ttu-id="c3202-129">![式図形をオーケストレーションに追加](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-02-add-expression-orch.gif "sql_adap_tut_02_add_expression_orch")</span><span class="sxs-lookup"><span data-stu-id="c3202-129">![Add an Expression shape to the orchestration](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-02-add-expression-orch.gif "sql_adap_tut_02_add_expression_orch")</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="c3202-130">でしただけ何か。</span><span class="sxs-lookup"><span data-stu-id="c3202-130">What did I just do?</span></span>  
 <span data-ttu-id="c3202-131">この手順で追加した、**式**図形を SQL Server データベースから受信した通知の種類を抽出します。</span><span class="sxs-lookup"><span data-stu-id="c3202-131">In this step, you added an **Expression** shape to extract the kind of notification received from the SQL Server database.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="c3202-132">次の手順</span><span class="sxs-lookup"><span data-stu-id="c3202-132">Next Steps</span></span>  
 <span data-ttu-id="c3202-133">判断図形の挿入の通知をフィルター処理を追加する」の説明に従って[手順 3。挿入通知用のフィルターの追加](../../adapters-and-accelerators/adapter-sql/step-3-add-a-filter-for-insert-notifications.md)します。</span><span class="sxs-lookup"><span data-stu-id="c3202-133">You add a Decide shape to filter for Insert notifications, as described in [Step 3: Add a Filter for Insert Notifications](../../adapters-and-accelerators/adapter-sql/step-3-add-a-filter-for-insert-notifications.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3202-134">参照</span><span class="sxs-lookup"><span data-stu-id="c3202-134">See Also</span></span>  
 <span data-ttu-id="c3202-135">[ステップ 1: 通知を受信するオーケストレーション図形を追加します。](../../adapters-and-accelerators/adapter-sql/step-1-add-orchestration-shapes-to-receive-notification.md) </span><span class="sxs-lookup"><span data-stu-id="c3202-135">[Step 1: Add Orchestration Shapes to Receive Notification](../../adapters-and-accelerators/adapter-sql/step-1-add-orchestration-shapes-to-receive-notification.md) </span></span>  
 <span data-ttu-id="c3202-136">[ステップ 3:挿入通知用のフィルターを追加します。](../../adapters-and-accelerators/adapter-sql/step-3-add-a-filter-for-insert-notifications.md) </span><span class="sxs-lookup"><span data-stu-id="c3202-136">[Step 3: Add a Filter for Insert Notifications](../../adapters-and-accelerators/adapter-sql/step-3-add-a-filter-for-insert-notifications.md) </span></span>  
 [<span data-ttu-id="c3202-137">レッスン 2:通知を受信してフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="c3202-137">Lesson 2: Receive and Filter Notifications</span></span>](../../adapters-and-accelerators/adapter-sql/lesson-2-receive-and-filter-notifications.md)