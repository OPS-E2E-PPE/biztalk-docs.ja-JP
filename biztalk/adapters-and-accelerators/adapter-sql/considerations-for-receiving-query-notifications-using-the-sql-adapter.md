---
title: SQL アダプタ使用クエリ通知の受信に関する考慮事項 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0142f385-3d55-41a7-a50e-dda94b96d0a4
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 21b3cc0056bf8105618aac7a9c47056d3e493c49
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004347"
---
# <a name="considerations-for-receiving-query-notifications-using-the-sql-adapter"></a><span data-ttu-id="cb279-102">SQL アダプタ使用クエリ通知の受信に関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="cb279-102">Considerations for Receiving Query Notifications Using the SQL adapter</span></span>
<span data-ttu-id="cb279-103">このトピックではいくつかの考慮事項とベスト プラクティスを使用しているときに考慮する、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]を SQL Server データベースからクエリ通知を受信します。</span><span class="sxs-lookup"><span data-stu-id="cb279-103">This topic provides some considerations and best practices to keep in mind while using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] to receive query notifications from a SQL Server database.</span></span>  
  
## <a name="considerations-while-using-the-adapter-to-receive-notifications"></a><span data-ttu-id="cb279-104">アダプターを使用して通知を受信する場合の考慮事項</span><span class="sxs-lookup"><span data-stu-id="cb279-104">Considerations While Using the Adapter to Receive Notifications</span></span>  
 <span data-ttu-id="cb279-105">使用しているときに、次を考慮する必要があります、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]クエリ通知を受信します。</span><span class="sxs-lookup"><span data-stu-id="cb279-105">You must consider the following while using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] to receive query notifications:</span></span>  
  
- <span data-ttu-id="cb279-106">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] 、SQL Server からクエリ通知を受信し、通知をアダプター クライアントに単に渡します。</span><span class="sxs-lookup"><span data-stu-id="cb279-106">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] receives the query notification from SQL Server, and then simply passes on the notification to the adapter clients.</span></span> <span data-ttu-id="cb279-107">アダプターは、さまざまな操作を通知する間隔と区別しません (つまり、アダプターはありませんすべての情報、特定の通知は、挿入操作または更新操作かどうか)。</span><span class="sxs-lookup"><span data-stu-id="cb279-107">The adapter does not distinguish between the notifications for different operations (i.e., the adapter does not have any information whether a particular notification is for an Insert operation or an Update operation).</span></span>  
  
- <span data-ttu-id="cb279-108">操作の通知メッセージは、その操作によって影響を受けたレコードの数の影響を受けません。</span><span class="sxs-lookup"><span data-stu-id="cb279-108">The notification message for an operation is not affected by the number of records affected by that operation.</span></span> <span data-ttu-id="cb279-109">たとえば、アダプター クライアントで挿入、更新、または SQL Server データベースのテーブルで削除されたレコードの数に関係なく 1 つだけの通知メッセージを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="cb279-109">For example, regardless of the number of records inserted, updated, or deleted in a SQL Server database table, the adapter client receives only one notification message.</span></span>  
  
- <span data-ttu-id="cb279-110">アダプターのクライアント アプリケーションが SQL Server から受信した通知の型を解釈するためのロジックを含めることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="cb279-110">We recommend that the adapter client application contain the logic to interpret the type of notification received from SQL Server.</span></span> <span data-ttu-id="cb279-111">情報を抽出することで、通知の種類を決定できます、 **\<情報\>** 受信した通知メッセージの要素。</span><span class="sxs-lookup"><span data-stu-id="cb279-111">The notification type can be determined by extracting the information from, the **\<Info\>** element of the received notification message.</span></span> <span data-ttu-id="cb279-112">挿入操作では受信した通知メッセージの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="cb279-112">Here’s an example of a notification message received for an Insert operation:</span></span>  
  
  ```  
  <Notification xmlns="http://schemas.microsoft.com/Sql/2008/05/Notification/">  
    <Info>Insert</Info>  
    <Source>Data</Source>  
    <Type>Change</Type>  
  </Notification>  
  ```  
  
   <span data-ttu-id="cb279-113">内の値に注意してください、 **\<情報\>** 要素。</span><span class="sxs-lookup"><span data-stu-id="cb279-113">Notice the value within the **\<Info\>** element.</span></span> <span data-ttu-id="cb279-114">この値は、通知メッセージを受信した操作について説明します。</span><span class="sxs-lookup"><span data-stu-id="cb279-114">This value provides information on the operation for which the notification message was received.</span></span> <span data-ttu-id="cb279-115">アプリケーション内で値を抽出するための機能があります、 **\<情報\>** 要素し、値に基づき、後続のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="cb279-115">Your application should have the functionality to extract the value within the **\<Info\>** element and then based on the value, perform subsequent tasks.</span></span> <span data-ttu-id="cb279-116">トピック[BizTalk Server を使用して SQL の特定のタスクを実行するプロセスの通知メッセージ](../../adapters-and-accelerators/adapter-sql/process-notification-messages-to-complete-specific-tasks-in-sql-using-biztalk.md)が内の値を抽出する方法について説明されています、 **\<情報\>** 要素.</span><span class="sxs-lookup"><span data-stu-id="cb279-116">The topic [Process Notification Messages to complete Specific Tasks in SQL using BizTalk Server](../../adapters-and-accelerators/adapter-sql/process-notification-messages-to-complete-specific-tasks-in-sql-using-biztalk.md) has instructions on how to extract the value within the **\<Info\>** element.</span></span> <span data-ttu-id="cb279-117">同様のタスクを実行する詳細なチュートリアルはでも[チュートリアル 2: 従業員 - 発注プロセス SQL アダプターを使用して](../../adapters-and-accelerators/adapter-sql/tutorial-2-employee-purchase-order-process-using-the-sql-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="cb279-117">A detailed tutorial that performs similar tasks is also available at [Tutorial 2: Employee - Purchase Order Process using the SQL adapter](../../adapters-and-accelerators/adapter-sql/tutorial-2-employee-purchase-order-process-using-the-sql-adapter.md).</span></span>  
  
- <span data-ttu-id="cb279-118">理想的には、クライアント アプリケーションが特定のレコードの通知を受け取った後そのレコードが更新されますできるように、追加の通知が受信されていません。</span><span class="sxs-lookup"><span data-stu-id="cb279-118">Ideally, after the client application receives a notification for a specific record, that record should be updated so that additional notifications are not received.</span></span> <span data-ttu-id="cb279-119">たとえば、**従業員**を持つテーブルを**状態**列。</span><span class="sxs-lookup"><span data-stu-id="cb279-119">For example, consider an **Employee** table that has a **Status** column.</span></span> <span data-ttu-id="cb279-120">すべての新しいレコードに挿入されるため、**従業員**テーブル内の値、**状態**列は常に、次のように、テーブルになりますが、「0」。</span><span class="sxs-lookup"><span data-stu-id="cb279-120">For all new records inserted into the **Employee** table, the value in the **Status** column is always “0” so the table will look like the following:</span></span>  
  
  |<span data-ttu-id="cb279-121">従業員の名前</span><span class="sxs-lookup"><span data-stu-id="cb279-121">Employee Name</span></span>|<span data-ttu-id="cb279-122">状態</span><span class="sxs-lookup"><span data-stu-id="cb279-122">Status</span></span>|  
  |-------------------|------------|  
  |<span data-ttu-id="cb279-123">John</span><span class="sxs-lookup"><span data-stu-id="cb279-123">John</span></span>|<span data-ttu-id="cb279-124">0</span><span class="sxs-lookup"><span data-stu-id="cb279-124">0</span></span>|  
  
   <span data-ttu-id="cb279-125">アダプターのクライアントを設定する新しく挿入されたレコードの通知を受信する、 **NotificatonStatement**としてプロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="cb279-125">To receive notifications for the newly inserted record, the adapter client will set the **NotificatonStatement** binding property as:</span></span>  
  
  ```  
  SELECT Employee_ID, Name FROM dbo.Employee WHERE Status=0  
  ```  
  
  > [!NOTE]
  >  <span data-ttu-id="cb279-126">具体的には、これで示すように、ステートメント内の列名の SELECT ステートメントを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cb279-126">You must specifically specify the column names in the statement as shown in this SELECT statement.</span></span> <span data-ttu-id="cb279-127">また、スキーマ名とテーブル名を必ず指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cb279-127">Also, you must always specify the table name along with the schema name.</span></span> <span data-ttu-id="cb279-128">たとえば、dbo です。従業員。</span><span class="sxs-lookup"><span data-stu-id="cb279-128">For example, dbo.Employee.</span></span>  
  
   <span data-ttu-id="cb279-129">クライアント アプリケーション通知を受信するには後の値をリセットする必要があります、**状態**「1」を列 notification ステートメントがもう一度レコードで動作しないようにします。</span><span class="sxs-lookup"><span data-stu-id="cb279-129">After receiving the notification, the client application must reset the value of the **Status** column to “1” so that the notification statement does not operate on the record again.</span></span> <span data-ttu-id="cb279-130">これを実現する、クライアント アプリケーションは、の更新操作を実行する必要があります、**従業員**テーブル。</span><span class="sxs-lookup"><span data-stu-id="cb279-130">To achieve this, the client application must perform an Update operation on the **Employee** table.</span></span> <span data-ttu-id="cb279-131">更新操作の後で同じ記録、**従業員**テーブルは、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="cb279-131">After the Update operation, the same record in the **Employee** table will look like the following:</span></span>  
  
  |<span data-ttu-id="cb279-132">従業員の名前</span><span class="sxs-lookup"><span data-stu-id="cb279-132">Employee Name</span></span>|<span data-ttu-id="cb279-133">状態</span><span class="sxs-lookup"><span data-stu-id="cb279-133">Status</span></span>|  
  |-------------------|------------|  
  |<span data-ttu-id="cb279-134">John</span><span class="sxs-lookup"><span data-stu-id="cb279-134">John</span></span>|<span data-ttu-id="cb279-135">1</span><span class="sxs-lookup"><span data-stu-id="cb279-135">1</span></span>|  
  
   <span data-ttu-id="cb279-136">更新操作では、通知をアダプターのクライアントに送信もう一度興味深いことに、プロセス全体がもう一度繰り返されますと、そのため、クライアント アプリケーションでは、必要なロジックをこのような不要な通知を破棄する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cb279-136">Interestingly, the Update operation will again send a notification to the adapter client and the whole process will be repeated again, therefore, the client application must have the required logic to discard such unwanted notifications.</span></span>  
  
- <span data-ttu-id="cb279-137">場合、 **NotifyOnListenerStart**プロパティのバインドは、アダプターのクライアント受信場所を開始するたびに通知メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="cb279-137">If the **NotifyOnListenerStart** binding property is true, the adapter client will receive a notification message every time the receive location starts.</span></span> <span data-ttu-id="cb279-138">バインド プロパティを使用し、通知メッセージを解釈する方法の詳細については、次を参照してください。[受信クエリ通知した後、受信場所のブレーク ダウンでは、BizTalk Server を使用して SQL](../../adapters-and-accelerators/adapter-sql/receive-query-notifications-after-a-sql-receive-location-stops-in-biztalk.md)します。</span><span class="sxs-lookup"><span data-stu-id="cb279-138">For more information on how to use the binding property and interpret the notification message, see [Receive Query Notifications After a Receive Location Breakdown in SQL using BizTalk Server](../../adapters-and-accelerators/adapter-sql/receive-query-notifications-after-a-sql-receive-location-stops-in-biztalk.md).</span></span>  
  
## <a name="typical-orchestration-for-receiving-notifications"></a><span data-ttu-id="cb279-139">通知を受信するための一般的なオーケストレーション</span><span class="sxs-lookup"><span data-stu-id="cb279-139">Typical Orchestration for Receiving Notifications</span></span>  
 <span data-ttu-id="cb279-140">このセクションを使用して通知を受信するための一般的なオーケストレーション フローの概要、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="cb279-140">This section outlines the typical orchestration flow for receiving notifications using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
1. <span data-ttu-id="cb279-141">オーケストレーションを行う必要があります最初に行うことは、受信した通知の種類を決定するなど。</span><span class="sxs-lookup"><span data-stu-id="cb279-141">The first thing that the orchestration must do is to determine the type of notification received, including:</span></span>  
  
   - <span data-ttu-id="cb279-142">後に、通知を受信したかどうか、受信場所を再起動します。</span><span class="sxs-lookup"><span data-stu-id="cb279-142">Whether the notification was received after a receive location restarts.</span></span>  
  
   - <span data-ttu-id="cb279-143">Insert などのデータベース テーブルで操作の通知を受信したかどうかは、更新、または削除します。</span><span class="sxs-lookup"><span data-stu-id="cb279-143">Whether the notification was received for an operation on a database table, such as Insert, Update, or Delete.</span></span>  
  
     <span data-ttu-id="cb279-144">オーケストレーションを含める必要があります、**式**図形、およびを受信したメッセージの種類を決定する xpath クエリ内で。</span><span class="sxs-lookup"><span data-stu-id="cb279-144">The orchestration must include an **Expression** shape, and within that, an xpath query to decide what kind of message is received.</span></span>  
  
2. <span data-ttu-id="cb279-145">通知の種類が決定されますと、オーケストレーションが受信した通知の種類に基づいて特定のアクションを実行するための判断ブロックを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="cb279-145">After the notification type is determined, the orchestration must include a decision block to perform specific actions based on the type of notification received.</span></span> <span data-ttu-id="cb279-146">これを実現するオーケストレーションを含める必要があります、**判断**、図形が含まれていますが、**ルール**ブロックと**Else**ブロック。</span><span class="sxs-lookup"><span data-stu-id="cb279-146">To achieve this, the orchestration must include a **Decide** shape, which includes a **Rule** block and an **Else** block:</span></span>  
  
   -   <span data-ttu-id="cb279-147">内で、**ルール**ブロックする条件を指定して、条件が満たされる場合は、特定の操作を実行するオーケストレーション図形を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="cb279-147">Within the **Rule** block, you must specify the condition and then include orchestration shapes to perform certain operations if the condition is met.</span></span>  
  
   -   <span data-ttu-id="cb279-148">内で、 **Else**ブロック、条件の場合は、特定の操作を実行するオーケストレーション図形を含める必要があります*いない*満たします。</span><span class="sxs-lookup"><span data-stu-id="cb279-148">Within the **Else** block, you must include orchestration shapes to perform certain operations if the condition is *not* met.</span></span>  
  
   <span data-ttu-id="cb279-149">上記の要件の詳細については、後述[BizTalk Server を使用して SQL の特定のタスクを実行するプロセスの通知メッセージ](../../adapters-and-accelerators/adapter-sql/process-notification-messages-to-complete-specific-tasks-in-sql-using-biztalk.md)します。</span><span class="sxs-lookup"><span data-stu-id="cb279-149">Details of the preceding requirements are described in [Process Notification Messages to complete Specific Tasks in SQL using BizTalk Server](../../adapters-and-accelerators/adapter-sql/process-notification-messages-to-complete-specific-tasks-in-sql-using-biztalk.md).</span></span> <span data-ttu-id="cb279-150">詳細なチュートリアルについても記載されて[チュートリアル 2: 従業員 - 発注プロセス SQL アダプターを使用して](../../adapters-and-accelerators/adapter-sql/tutorial-2-employee-purchase-order-process-using-the-sql-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="cb279-150">A detailed tutorial is also available in [Tutorial 2: Employee - Purchase Order Process using the SQL adapter](../../adapters-and-accelerators/adapter-sql/tutorial-2-employee-purchase-order-process-using-the-sql-adapter.md).</span></span>