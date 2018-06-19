---
title: '手順 2: 通知メッセージからの通知の種類の抽出 |Microsoft ドキュメント'
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
ms.openlocfilehash: 51a4fd5e96c3593d3f47ed3c7dfc1875efca7c52
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22224162"
---
# <a name="step-2-extract-notification-type-from-notification-message"></a><span data-ttu-id="9ed1a-102">手順 2: 通知メッセージからの通知の種類を抽出します。</span><span class="sxs-lookup"><span data-stu-id="9ed1a-102">Step 2: Extract Notification Type from Notification Message</span></span>
<span data-ttu-id="9ed1a-103">![手順 3 の 2](../../adapters-and-accelerators/adapter-oracle-database/media/step-2of3.gif "Step_2of3")</span><span class="sxs-lookup"><span data-stu-id="9ed1a-103">![Step 2 of 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-2of3.gif "Step_2of3")</span></span>  
  
 <span data-ttu-id="9ed1a-104">**所要時間:** 5 分</span><span class="sxs-lookup"><span data-stu-id="9ed1a-104">**Time to complete:** 5 minutes</span></span>  
  
 <span data-ttu-id="9ed1a-105">**目標:** このステップで、SQL Server データベースから受信した通知の種類を抽出する式図形を追加します。</span><span class="sxs-lookup"><span data-stu-id="9ed1a-105">**Objective:** In this step, you add an expression shape to extract the type of notification received from the SQL Server database.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="9ed1a-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="9ed1a-106">Prerequisites</span></span>  
 <span data-ttu-id="9ed1a-107">完了する必要があります[手順 1: 通知を受信するオーケストレーション図形の追加](../../adapters-and-accelerators/adapter-sql/step-1-add-orchestration-shapes-to-receive-notification.md)です。</span><span class="sxs-lookup"><span data-stu-id="9ed1a-107">You must have completed [Step 1: Add Orchestration Shapes to Receive Notification](../../adapters-and-accelerators/adapter-sql/step-1-add-orchestration-shapes-to-receive-notification.md).</span></span>  
  
### <a name="to-extract-the-notification-type-from-the-notification-message"></a><span data-ttu-id="9ed1a-108">通知の種類を通知メッセージから抽出するには</span><span class="sxs-lookup"><span data-stu-id="9ed1a-108">To extract the notification type from the notification message</span></span>  
  
1.  <span data-ttu-id="9ed1a-109">作成した BizTalk オーケストレーションに変数を追加[手順 1: 通知を受信するオーケストレーション図形の追加](../../adapters-and-accelerators/adapter-sql/step-1-add-orchestration-shapes-to-receive-notification.md)です。</span><span class="sxs-lookup"><span data-stu-id="9ed1a-109">Add a variable to the BizTalk orchestration you created in [Step 1: Add Orchestration Shapes to Receive Notification](../../adapters-and-accelerators/adapter-sql/step-1-add-orchestration-shapes-to-receive-notification.md).</span></span>  
  
    1.  <span data-ttu-id="9ed1a-110">オーケストレーション ビューを右クリックして**変数**、クリックして**新しい変数**です。</span><span class="sxs-lookup"><span data-stu-id="9ed1a-110">From the Orchestration View, right-click **Variables**, and then click **New Variable**.</span></span>  
  
    2.  <span data-ttu-id="9ed1a-111">その新しい変数を右クリックして**Variable_1**、 をクリック**プロパティ ウィンドウ**します。</span><span class="sxs-lookup"><span data-stu-id="9ed1a-111">Right-click the new variable, **Variable_1**, and click **Properties Window**.</span></span> <span data-ttu-id="9ed1a-112">変数の次のプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="9ed1a-112">Set the following properties for the variable.</span></span>  
  
        |<span data-ttu-id="9ed1a-113">このプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="9ed1a-113">Set this property</span></span>|<span data-ttu-id="9ed1a-114">この値を</span><span class="sxs-lookup"><span data-stu-id="9ed1a-114">To this value</span></span>|  
        |-----------------------|-------------------|  
        |<span data-ttu-id="9ed1a-115">**[Identifier]**</span><span class="sxs-lookup"><span data-stu-id="9ed1a-115">**Identifier**</span></span>|<span data-ttu-id="9ed1a-116">NotificationType</span><span class="sxs-lookup"><span data-stu-id="9ed1a-116">NotificationType</span></span>|  
        |<span data-ttu-id="9ed1a-117">**型**</span><span class="sxs-lookup"><span data-stu-id="9ed1a-117">**Type**</span></span>|<span data-ttu-id="9ed1a-118">System.String</span><span class="sxs-lookup"><span data-stu-id="9ed1a-118">System.String</span></span>|  
  
2.  <span data-ttu-id="9ed1a-119">追加、**式**を BizTalk オーケストレーションに図形です。</span><span class="sxs-lookup"><span data-stu-id="9ed1a-119">Add an **Expression** shape to the BizTalk orchestration.</span></span> <span data-ttu-id="9ed1a-120">オーケストレーション ツールボックスからドラッグして、**式**図形をオーケストレーション デザイン画面にし、ドロップした後、**受信**図形</span><span class="sxs-lookup"><span data-stu-id="9ed1a-120">From the orchestration Toolbox, drag the **Expression** shape to the orchestration design surface, and drop it after the **Receive** shape</span></span>  
  
     <span data-ttu-id="9ed1a-121">内で、**式**図形、SQL Server から受信した通知メッセージの種類を抽出する xpath クエリを追加します。</span><span class="sxs-lookup"><span data-stu-id="9ed1a-121">Within the **Expression** shape, you will add an xpath query to extract the type of notification message received from SQL Server.</span></span> <span data-ttu-id="9ed1a-122">Xpath クエリを作成する前に、通知メッセージの形式について見てみましょう。</span><span class="sxs-lookup"><span data-stu-id="9ed1a-122">Before creating an xpath query, let us look at the format of a notification message.</span></span> <span data-ttu-id="9ed1a-123">一般的な通知メッセージには、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="9ed1a-123">A typical notification message resembles the following:</span></span>  
  
    ```  
    <Notification xmlns="http://schemas.microsoft.com/Sql/2008/05/Notification/">  
      <Info>Insert</Info>   
      <Source>Data</Source>   
      <Type>Change</Type>   
    </Notification>  
    ```  
  
3.  <span data-ttu-id="9ed1a-124">通知の種類に関する情報は内で使用できる表示のように、`<info>`親内のタグ`<Notification>`タグ。</span><span class="sxs-lookup"><span data-stu-id="9ed1a-124">As you see, the information about the type of the notification is available within the `<info>` tag, within the parent `<Notification>` tag.</span></span> <span data-ttu-id="9ed1a-125">そのため、次の xpath クエリ内での追加、**式**図形。</span><span class="sxs-lookup"><span data-stu-id="9ed1a-125">So, add the following xpath query within the **Expression** shape:</span></span>  
  
    ```  
    NotificationType = xpath(NotifyReceive,"string(/*[local-name()='Notification']/*[local-name()='Info']/text())");  
    ```  
  
     <span data-ttu-id="9ed1a-126">ここでは、 **NotificationType** xpath クエリで抽出された値を格納するために作成する変数です。</span><span class="sxs-lookup"><span data-stu-id="9ed1a-126">Here, **NotificationType** is the variable you created to store the value extracted by the xpath query.</span></span> <span data-ttu-id="9ed1a-127">**NotifyReceive**で作成したメッセージは、[手順 2: BizTalk オーケストレーションのメッセージの作成](../../adapters-and-accelerators/adapter-sql/step-2-create-messages-for-biztalk-orchestrations.md)通知メッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="9ed1a-127">**NotifyReceive** is the message you created in [Step 2: Create Messages for BizTalk Orchestrations](../../adapters-and-accelerators/adapter-sql/step-2-create-messages-for-biztalk-orchestrations.md) to receive notification messages.</span></span>  
  
4.  <span data-ttu-id="9ed1a-128">次の図は、進行中のオーケストレーション、**式**図形が含まれています。</span><span class="sxs-lookup"><span data-stu-id="9ed1a-128">The following figure shows the in-progress orchestration with the **Expression** shape included.</span></span>  
  
     <span data-ttu-id="9ed1a-129">![式図形をオーケストレーションに追加](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-02-add-expression-orch.gif "sql_adap_tut_02_add_expression_orch")</span><span class="sxs-lookup"><span data-stu-id="9ed1a-129">![Add an Expression shape to the orchestration](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-02-add-expression-orch.gif "sql_adap_tut_02_add_expression_orch")</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="9ed1a-130">でしただけは何ですか。</span><span class="sxs-lookup"><span data-stu-id="9ed1a-130">What did I just do?</span></span>  
 <span data-ttu-id="9ed1a-131">この手順で追加した、**式**図形を SQL Server データベースから受信した通知の種類を抽出します。</span><span class="sxs-lookup"><span data-stu-id="9ed1a-131">In this step, you added an **Expression** shape to extract the kind of notification received from the SQL Server database.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="9ed1a-132">次の手順</span><span class="sxs-lookup"><span data-stu-id="9ed1a-132">Next Steps</span></span>  
 <span data-ttu-id="9ed1a-133">判断図形の挿入の通知をフィルター処理を追加する」の説明に従って[手順 3: 挿入の通知用のフィルターの追加](../../adapters-and-accelerators/adapter-sql/step-3-add-a-filter-for-insert-notifications.md)です。</span><span class="sxs-lookup"><span data-stu-id="9ed1a-133">You add a Decide shape to filter for Insert notifications, as described in [Step 3: Add a Filter for Insert Notifications](../../adapters-and-accelerators/adapter-sql/step-3-add-a-filter-for-insert-notifications.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ed1a-134">参照</span><span class="sxs-lookup"><span data-stu-id="9ed1a-134">See Also</span></span>  
 <span data-ttu-id="9ed1a-135">[手順 1: 通知を受信するオーケストレーション図形を追加します。](../../adapters-and-accelerators/adapter-sql/step-1-add-orchestration-shapes-to-receive-notification.md) </span><span class="sxs-lookup"><span data-stu-id="9ed1a-135">[Step 1: Add Orchestration Shapes to Receive Notification](../../adapters-and-accelerators/adapter-sql/step-1-add-orchestration-shapes-to-receive-notification.md) </span></span>  
 <span data-ttu-id="9ed1a-136">[手順 3: 挿入の通知にフィルターを追加します。](../../adapters-and-accelerators/adapter-sql/step-3-add-a-filter-for-insert-notifications.md) </span><span class="sxs-lookup"><span data-stu-id="9ed1a-136">[Step 3: Add a Filter for Insert Notifications](../../adapters-and-accelerators/adapter-sql/step-3-add-a-filter-for-insert-notifications.md) </span></span>  
 [<span data-ttu-id="9ed1a-137">レッスン 2: 表示され、通知をフィルター処理</span><span class="sxs-lookup"><span data-stu-id="9ed1a-137">Lesson 2: Receive and Filter Notifications</span></span>](../../adapters-and-accelerators/adapter-sql/lesson-2-receive-and-filter-notifications.md)