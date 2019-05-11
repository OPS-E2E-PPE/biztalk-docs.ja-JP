---
title: 手順 3:挿入通知用のフィルターの追加 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 53a1e9ef-a179-42a7-b4ae-b1170181053b
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e49f4f914771a26618dd92126b49143492d627b8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65367925"
---
# <a name="step-3-add-a-filter-for-insert-notifications"></a><span data-ttu-id="faed4-102">手順 3:挿入通知用のフィルターを追加します。</span><span class="sxs-lookup"><span data-stu-id="faed4-102">Step 3: Add a Filter for Insert Notifications</span></span>
<span data-ttu-id="faed4-103">![ステップ 3/3](../../adapters-and-accelerators/adapter-oracle-database/media/step-3of3.gif "Step_3of3")</span><span class="sxs-lookup"><span data-stu-id="faed4-103">![Step 3 of 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-3of3.gif "Step_3of3")</span></span>  
  
 <span data-ttu-id="faed4-104">**所要時間:** 5 分</span><span class="sxs-lookup"><span data-stu-id="faed4-104">**Time to complete:** 5 minutes</span></span>  
  
 <span data-ttu-id="faed4-105">**目標:** この手順では、挿入操作の通知メッセージのフィルター処理するオーケストレーションに判断図形を追加します。</span><span class="sxs-lookup"><span data-stu-id="faed4-105">**Objective:** In this step, you add a Decide shape to the orchestration to filter for notification messages for Insert operation.</span></span> <span data-ttu-id="faed4-106">オーケストレーション内の後続の操作は、受信した通知が挿入の型の場合にのみ実行されます。</span><span class="sxs-lookup"><span data-stu-id="faed4-106">Subsequent operations in the orchestration are performed only if the notification received is of Insert type.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="faed4-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="faed4-107">Prerequisites</span></span>  
 <span data-ttu-id="faed4-108">完了する必要があります[手順 2。通知の種類を通知メッセージから抽出](../../adapters-and-accelerators/adapter-sql/step-2-extract-notification-type-from-notification-message.md)します。</span><span class="sxs-lookup"><span data-stu-id="faed4-108">You must have completed [Step 2: Extract Notification Type from Notification Message](../../adapters-and-accelerators/adapter-sql/step-2-extract-notification-type-from-notification-message.md).</span></span>  
  
### <a name="to-filter-for-notification-messages"></a><span data-ttu-id="faed4-109">通知メッセージのフィルター処理するには</span><span class="sxs-lookup"><span data-stu-id="faed4-109">To filter for notification messages</span></span>  
  
1.  <span data-ttu-id="faed4-110">追加、**判断**、オーケストレーションに図形の後に、**式**図形。</span><span class="sxs-lookup"><span data-stu-id="faed4-110">Add a **Decide** shape to the orchestration, after the **Expression** shape.</span></span> <span data-ttu-id="faed4-111">ツールボックスからドラッグして、**判断**図形を区分線のすぐ下に、**式**図形。</span><span class="sxs-lookup"><span data-stu-id="faed4-111">From the Toolbox, drag the **Decide** shape onto the connecting line directly below the **Expression** shape.</span></span>  
  
     <span data-ttu-id="faed4-112">**判断**図形の分岐が表示が展開、**場合**ステートメント **([rule_1])** の分岐および、 **Else**ステートメント。</span><span class="sxs-lookup"><span data-stu-id="faed4-112">The **Decide** shape expands to show a branch for the **If** statement **(Rule_1)** and a branch for the **Else** statement.</span></span>  
  
2.  <span data-ttu-id="faed4-113">デザイン サーフェイスを右クリックし、**判断**図形をクリックして**プロパティ ウィンドウ**します。</span><span class="sxs-lookup"><span data-stu-id="faed4-113">On the design surface, right-click the **Decide** shape, and then click **Properties Window**.</span></span>  
  
3.  <span data-ttu-id="faed4-114">**プロパティ**のウィンドウ、**判断**図形、**名前**プロパティに「`CheckNotification`します。</span><span class="sxs-lookup"><span data-stu-id="faed4-114">In the **Properties** pane for the **Decide** shape, in the **Name** property, type `CheckNotification`.</span></span>  
  
4.  <span data-ttu-id="faed4-115">デザイン サーフェイスを右クリックし、 **rule_1**図形 (内の**判断**図形) を順にクリックします**プロパティ ウィンドウ**します。</span><span class="sxs-lookup"><span data-stu-id="faed4-115">On the design surface, right-click the **Rule_1** shape (inside of the **Decide** shape), and then click **Properties Window**.</span></span>  
  
5.  <span data-ttu-id="faed4-116">**プロパティ**ウィンドウ **[rule_1]** で、**名前**プロパティに「**挿入**します。</span><span class="sxs-lookup"><span data-stu-id="faed4-116">In the **Properties** pane for **Rule_1**, in the **Name** property, type **Insert**.</span></span>  
  
6.  <span data-ttu-id="faed4-117">右クリックし、**挿入**図形をクリックして**ブール式の編集**します。</span><span class="sxs-lookup"><span data-stu-id="faed4-117">Right-click the **Insert** shape, and then click **Edit Boolean Expression**.</span></span>  
  
7.  <span data-ttu-id="faed4-118">BizTalk 式エディターでは、次を入力します。</span><span class="sxs-lookup"><span data-stu-id="faed4-118">In the BizTalk Expression Editor, type the following:</span></span>  
  
    ```  
    NotificationType.Equals("Insert")  
    ```  
  
     <span data-ttu-id="faed4-119">この条件は場合にのみ後続の操作を実行するオーケストレーション内の値、 **NotificationType**変数が**挿入**します。</span><span class="sxs-lookup"><span data-stu-id="faed4-119">This condition tells the orchestration to perform subsequent operations only if the value in the **NotificationType** variable is **Insert**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="faed4-120">この変数を追加した[手順 2。通知の種類を通知メッセージから抽出](../../adapters-and-accelerators/adapter-sql/step-2-extract-notification-type-from-notification-message.md)を SQL Server データベースから受信した通知メッセージから通知の種類を抽出します。</span><span class="sxs-lookup"><span data-stu-id="faed4-120">You added this variable in [Step 2: Extract Notification Type from Notification Message](../../adapters-and-accelerators/adapter-sql/step-2-extract-notification-type-from-notification-message.md) to extract the type of notification from the notification message received from the SQL Server database.</span></span>  
  
8.  <span data-ttu-id="faed4-121">次の図は、進行中のオーケストレーション、**判断**図形が含まれています。</span><span class="sxs-lookup"><span data-stu-id="faed4-121">The following figure shows the in-progress orchestration with the **Decide** shape included.</span></span>  
  
     <span data-ttu-id="faed4-122">![判断図形をオーケストレーションに追加](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-03-add-filter-orch.gif "sql_adap_tut_03_add_filter_orch")</span><span class="sxs-lookup"><span data-stu-id="faed4-122">![Add a Decide shape to the orchestration](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-03-add-filter-orch.gif "sql_adap_tut_03_add_filter_orch")</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="faed4-123">でしただけ何か。</span><span class="sxs-lookup"><span data-stu-id="faed4-123">What did I just do?</span></span>  
 <span data-ttu-id="faed4-124">この手順で追加した、**判断**図形を受信した通知が挿入操作の場合にのみ後続の操作を実行する通知メッセージをフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="faed4-124">In this step, you added a **Decide** shape to filter the notification messages to perform subsequent operations only if the notification received is for Insert operations.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="faed4-125">次の手順</span><span class="sxs-lookup"><span data-stu-id="faed4-125">Next Steps</span></span>  
 <span data-ttu-id="faed4-126">次の手順で追加するオーケストレーション図形を UPDATE_EMPLOYE を呼び出すストアド プロシージャを使用、従業員テーブルを」の説明に従って[レッスン 3。追加された新しい従業員を選択するストアド プロシージャの実行](../../adapters-and-accelerators/adapter-sql/lesson-3-execute-a-stored-procedure-to-select-new-employees-added.md)します。</span><span class="sxs-lookup"><span data-stu-id="faed4-126">In the next step, you add orchestration shapes to invoke the UPDATE_EMPLOYE stored procedure on the Employee table, as described in [Lesson 3: Execute a Stored Procedure to Select New Employees Added](../../adapters-and-accelerators/adapter-sql/lesson-3-execute-a-stored-procedure-to-select-new-employees-added.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="faed4-127">参照</span><span class="sxs-lookup"><span data-stu-id="faed4-127">See Also</span></span>  
 <span data-ttu-id="faed4-128">[手順 2:通知メッセージからの通知の種類を抽出します。](../../adapters-and-accelerators/adapter-sql/step-2-extract-notification-type-from-notification-message.md) </span><span class="sxs-lookup"><span data-stu-id="faed4-128">[Step 2: Extract Notification Type from Notification Message](../../adapters-and-accelerators/adapter-sql/step-2-extract-notification-type-from-notification-message.md) </span></span>  
 [<span data-ttu-id="faed4-129">レッスン 2:通知を受信してフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="faed4-129">Lesson 2: Receive and Filter Notifications</span></span>](../../adapters-and-accelerators/adapter-sql/lesson-2-receive-and-filter-notifications.md)