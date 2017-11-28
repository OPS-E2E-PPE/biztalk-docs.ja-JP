---
title: "手順 3: 挿入の通知にフィルターを追加する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 53a1e9ef-a179-42a7-b4ae-b1170181053b
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 97fc32fe7dd657bb45edca91fda0eddaa537b32a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-3-add-a-filter-for-insert-notifications"></a><span data-ttu-id="ba2f0-102">手順 3: 挿入の通知にフィルターを追加します。</span><span class="sxs-lookup"><span data-stu-id="ba2f0-102">Step 3: Add a Filter for Insert Notifications</span></span>
<span data-ttu-id="ba2f0-103">![手順 3 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-3of3.gif "Step_3of3")</span><span class="sxs-lookup"><span data-stu-id="ba2f0-103">![Step 3 of 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-3of3.gif "Step_3of3")</span></span>  
  
 <span data-ttu-id="ba2f0-104">**所要時間:** 5 分</span><span class="sxs-lookup"><span data-stu-id="ba2f0-104">**Time to complete:** 5 minutes</span></span>  
  
 <span data-ttu-id="ba2f0-105">**目標:**ここでは、挿入操作の通知メッセージのフィルター処理するオーケストレーションに判断図形を追加します。</span><span class="sxs-lookup"><span data-stu-id="ba2f0-105">**Objective:** In this step, you add a Decide shape to the orchestration to filter for notification messages for Insert operation.</span></span> <span data-ttu-id="ba2f0-106">オーケストレーションでの後続の操作は、通知を受け取りましたが Insert 型の場合にのみ実行されます。</span><span class="sxs-lookup"><span data-stu-id="ba2f0-106">Subsequent operations in the orchestration are performed only if the notification received is of Insert type.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="ba2f0-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="ba2f0-107">Prerequisites</span></span>  
 <span data-ttu-id="ba2f0-108">完了する必要があります[手順 2: 通知メッセージから通知の種類を抽出](../../adapters-and-accelerators/adapter-sql/step-2-extract-notification-type-from-notification-message.md)です。</span><span class="sxs-lookup"><span data-stu-id="ba2f0-108">You must have completed [Step 2: Extract Notification Type from Notification Message](../../adapters-and-accelerators/adapter-sql/step-2-extract-notification-type-from-notification-message.md).</span></span>  
  
### <a name="to-filter-for-notification-messages"></a><span data-ttu-id="ba2f0-109">通知メッセージのフィルター処理するには</span><span class="sxs-lookup"><span data-stu-id="ba2f0-109">To filter for notification messages</span></span>  
  
1.  <span data-ttu-id="ba2f0-110">追加、**判断**、オーケストレーションに図形の後に、**式**図形です。</span><span class="sxs-lookup"><span data-stu-id="ba2f0-110">Add a **Decide** shape to the orchestration, after the **Expression** shape.</span></span> <span data-ttu-id="ba2f0-111">ツールボックスからドラッグして、**判断**図形を区分線のすぐ下に、**式**図形です。</span><span class="sxs-lookup"><span data-stu-id="ba2f0-111">From the Toolbox, drag the **Decide** shape onto the connecting line directly below the **Expression** shape.</span></span>  
  
     <span data-ttu-id="ba2f0-112">**判断**用に分岐を表示する図形が展開され、**場合**ステートメント**(Rule_1)**の分岐および、 **Else**ステートメントです。</span><span class="sxs-lookup"><span data-stu-id="ba2f0-112">The **Decide** shape expands to show a branch for the **If** statement **(Rule_1)** and a branch for the **Else** statement.</span></span>  
  
2.  <span data-ttu-id="ba2f0-113">デザイン サーフェイスを右クリックし、**判断**図形をクリックして**プロパティ ウィンドウ**します。</span><span class="sxs-lookup"><span data-stu-id="ba2f0-113">On the design surface, right-click the **Decide** shape, and then click **Properties Window**.</span></span>  
  
3.  <span data-ttu-id="ba2f0-114">**プロパティ**のウィンドウ、**判断**図形、**名前**プロパティで、「`CheckNotification`です。</span><span class="sxs-lookup"><span data-stu-id="ba2f0-114">In the **Properties** pane for the **Decide** shape, in the **Name** property, type `CheckNotification`.</span></span>  
  
4.  <span data-ttu-id="ba2f0-115">デザイン サーフェイスを右クリックし、 **rule_1**図形 (内の**判断**図形)、をクリックして**プロパティ ウィンドウ**します。</span><span class="sxs-lookup"><span data-stu-id="ba2f0-115">On the design surface, right-click the **Rule_1** shape (inside of the **Decide** shape), and then click **Properties Window**.</span></span>  
  
5.  <span data-ttu-id="ba2f0-116">**プロパティ**ウィンドウ**[rule_1]**で、**名前**プロパティで、「**挿入**です。</span><span class="sxs-lookup"><span data-stu-id="ba2f0-116">In the **Properties** pane for **Rule_1**, in the **Name** property, type **Insert**.</span></span>  
  
6.  <span data-ttu-id="ba2f0-117">右クリックし、**挿入**図形をクリックして**ブール式の編集**です。</span><span class="sxs-lookup"><span data-stu-id="ba2f0-117">Right-click the **Insert** shape, and then click **Edit Boolean Expression**.</span></span>  
  
7.  <span data-ttu-id="ba2f0-118">BizTalk 式エディターで、次に入力します。</span><span class="sxs-lookup"><span data-stu-id="ba2f0-118">In the BizTalk Expression Editor, type the following:</span></span>  
  
    ```  
    NotificationType.Equals("Insert")  
    ```  
  
     <span data-ttu-id="ba2f0-119">この状態通知の場合にのみ、後続の操作を実行するオーケストレーションの値、 **NotificationType**変数が**挿入**です。</span><span class="sxs-lookup"><span data-stu-id="ba2f0-119">This condition tells the orchestration to perform subsequent operations only if the value in the **NotificationType** variable is **Insert**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ba2f0-120">この変数を追加した[手順 2: 通知メッセージから通知の種類を抽出](../../adapters-and-accelerators/adapter-sql/step-2-extract-notification-type-from-notification-message.md)通知の種類を SQL Server データベースから受信した通知メッセージから抽出します。</span><span class="sxs-lookup"><span data-stu-id="ba2f0-120">You added this variable in [Step 2: Extract Notification Type from Notification Message](../../adapters-and-accelerators/adapter-sql/step-2-extract-notification-type-from-notification-message.md) to extract the type of notification from the notification message received from the SQL Server database.</span></span>  
  
8.  <span data-ttu-id="ba2f0-121">次の図は、進行中のオーケストレーション、**判断**図形が含まれています。</span><span class="sxs-lookup"><span data-stu-id="ba2f0-121">The following figure shows the in-progress orchestration with the **Decide** shape included.</span></span>  
  
     <span data-ttu-id="ba2f0-122">![判断図形をオーケストレーションに追加](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-03-add-filter-orch.gif "sql_adap_tut_03_add_filter_orch")</span><span class="sxs-lookup"><span data-stu-id="ba2f0-122">![Add a Decide shape to the orchestration](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-03-add-filter-orch.gif "sql_adap_tut_03_add_filter_orch")</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="ba2f0-123">でしただけは何ですか。</span><span class="sxs-lookup"><span data-stu-id="ba2f0-123">What did I just do?</span></span>  
 <span data-ttu-id="ba2f0-124">この手順で追加した、**判断**図形を受信する通知が挿入操作の場合にのみ、後続の操作を実行する通知メッセージをフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="ba2f0-124">In this step, you added a **Decide** shape to filter the notification messages to perform subsequent operations only if the notification received is for Insert operations.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="ba2f0-125">次の手順</span><span class="sxs-lookup"><span data-stu-id="ba2f0-125">Next Steps</span></span>  
 <span data-ttu-id="ba2f0-126">次の手順で追加する Employee テーブルでのストアド プロシージャを UPDATE_EMPLOYE を呼び出すためのオーケストレーション図形」の説明に従って[レッスン 3: 追加された新しい従業員を選択するストアド プロシージャを実行して](../../adapters-and-accelerators/adapter-sql/lesson-3-execute-a-stored-procedure-to-select-new-employees-added.md)です。</span><span class="sxs-lookup"><span data-stu-id="ba2f0-126">In the next step, you add orchestration shapes to invoke the UPDATE_EMPLOYE stored procedure on the Employee table, as described in [Lesson 3: Execute a Stored Procedure to Select New Employees Added](../../adapters-and-accelerators/adapter-sql/lesson-3-execute-a-stored-procedure-to-select-new-employees-added.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba2f0-127">参照</span><span class="sxs-lookup"><span data-stu-id="ba2f0-127">See Also</span></span>  
 <span data-ttu-id="ba2f0-128">[手順 2: 通知メッセージからの通知の種類を抽出します。](../../adapters-and-accelerators/adapter-sql/step-2-extract-notification-type-from-notification-message.md) </span><span class="sxs-lookup"><span data-stu-id="ba2f0-128">[Step 2: Extract Notification Type from Notification Message](../../adapters-and-accelerators/adapter-sql/step-2-extract-notification-type-from-notification-message.md) </span></span>  
 [<span data-ttu-id="ba2f0-129">レッスン 2: 表示され、通知をフィルター処理</span><span class="sxs-lookup"><span data-stu-id="ba2f0-129">Lesson 2: Receive and Filter Notifications</span></span>](../../adapters-and-accelerators/adapter-sql/lesson-2-receive-and-filter-notifications.md)