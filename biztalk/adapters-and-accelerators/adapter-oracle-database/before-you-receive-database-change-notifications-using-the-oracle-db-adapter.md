---
title: 受信データベース変更通知を使用して、Oracle Database アダプターに関する考慮事項 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 206439b9-0408-4fbb-80e3-cfda2f5a89a5
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9d7237037794168ffb136c95734582b3df95db48
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37015195"
---
# <a name="considerations-for-receiving-database-change-notifications-using-the-oracle-database-adapter"></a><span data-ttu-id="6cd23-102">受信データベース変更通知を使用して、Oracle Database アダプターに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="6cd23-102">Considerations for Receiving Database Change Notifications Using the Oracle Database adapter</span></span>
<span data-ttu-id="6cd23-103">このトピックではいくつかの考慮事項とベスト プラクティスを使用しているときに点に注意する必要があります[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]Oracle データベースからデータベースの通知を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="6cd23-103">This topic provides some considerations and best practices that you must keep in mind while using the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] to receive database notifications from an Oracle database.</span></span>  
  
## <a name="considerations-while-using-the-adapter-to-receive-notifications"></a><span data-ttu-id="6cd23-104">アダプターを使用して通知を受信する場合の考慮事項</span><span class="sxs-lookup"><span data-stu-id="6cd23-104">Considerations While Using the Adapter to Receive Notifications</span></span>  
 <span data-ttu-id="6cd23-105">使用しているときに、次を考慮する必要があります、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]クエリ通知を受信します。</span><span class="sxs-lookup"><span data-stu-id="6cd23-105">You must consider the following while using the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] to receive query notifications.</span></span>  
  
- <span data-ttu-id="6cd23-106">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]アダプター クライアントに、Oracle データベースから受信すると、通知を渡すだけです。</span><span class="sxs-lookup"><span data-stu-id="6cd23-106">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] simply passes on the notification, which it receives from the Oracle database, to the adapter clients.</span></span> <span data-ttu-id="6cd23-107">アダプターは区別されません、さまざまな操作の通知など、挿入操作または更新操作の特定の通知があるのか、アダプターはすべての情報をありません。</span><span class="sxs-lookup"><span data-stu-id="6cd23-107">The adapter does not distinguish between the notifications for different operations, i.e., the adapter does not have any information whether a particular notification is for an Insert operation or an Update operation.</span></span>  
  
- <span data-ttu-id="6cd23-108">操作の通知メッセージは、その操作によって影響を受けたレコードの数の影響を受けません。</span><span class="sxs-lookup"><span data-stu-id="6cd23-108">The notification message for an operation is not affected by the number of records affected by that operation.</span></span> <span data-ttu-id="6cd23-109">たとえば、アダプター クライアントで、Oracle データベース テーブルに挿入されたレコードの数に関係なく 1 つだけの通知メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6cd23-109">For example, irrespective of the number of records inserted in an Oracle database table, the adapter clients receive only one notification message.</span></span>  
  
- <span data-ttu-id="6cd23-110">アダプターのクライアント アプリケーションが Oracle データベースから受信した通知の種類を解釈するためのロジックを含めることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6cd23-110">We recommend that the adapter client application contain the logic to interpret the kind of notification received from the Oracle database.</span></span> <span data-ttu-id="6cd23-111">アダプターのクライアント アプリケーションを内の情報を抽出することによって行うことができます、 **\<情報\>** 受信した通知メッセージの要素。</span><span class="sxs-lookup"><span data-stu-id="6cd23-111">The adapter client applications can do so by extracting the information in the **\<Info\>** element of the received notification message.</span></span> <span data-ttu-id="6cd23-112">挿入操作では受信した通知メッセージの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="6cd23-112">Here’s an example of a notification message received for an Insert operation.</span></span>  
  
  ```  
  <?xml version="1.0" encoding="utf-8" ?>   
  <Notification xmlns="http://Microsoft.LobServices.OracleDB/2007/03/Notification/">  
    <Details>  
      <NotificationDetails>  
        <ResourceName>SCOTT.ACCOUNTACTIVITY</ResourceName>   
        <Info>1</Info>   
        <QueryId>0</QueryId>   
      </NotificationDetails>  
    </Details>  
    <Info>Insert</Info>   
    <ResourceNames>  
      <string xmlns="http://schemas.microsoft.com/2003/10/Serialization/Arrays">SCOTT.ACCOUNTACTIVITY</string>   
    </ResourceNames>  
    <Source>Data</Source>   
    <Type>Change</Type>   
  </Notification>  
  
  ```  
  
   <span data-ttu-id="6cd23-113">内の値に注意してください、 **\<情報\>** 要素。</span><span class="sxs-lookup"><span data-stu-id="6cd23-113">Notice the value within the **\<Info\>** element.</span></span> <span data-ttu-id="6cd23-114">この値は、通知メッセージを受信した操作について説明します。</span><span class="sxs-lookup"><span data-stu-id="6cd23-114">This value provides information on the operation for which the notification message was received.</span></span> <span data-ttu-id="6cd23-115">アプリケーション内で値を抽出するための機能があります、 **\<情報\>** 要素し、値に基づき、後続のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="6cd23-115">Your application should have the functionality to extract the value within the **\<Info\>** element and then based on the value, perform subsequent tasks.</span></span> <span data-ttu-id="6cd23-116">トピック[通知メッセージが Oracle データベースで特定のタスクを完了する処理](../../adapters-and-accelerators/adapter-oracle-database/process-notification-messages-to-run-specific-tasks-in-oracle-db-using-biztalk.md)が内の値を抽出する方法について説明されています、 **\<情報\>** 要素。</span><span class="sxs-lookup"><span data-stu-id="6cd23-116">The topic [Processing Notification Messages to complete Specific Tasks in Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/process-notification-messages-to-run-specific-tasks-in-oracle-db-using-biztalk.md) has instructions on how to extract the value within the **\<Info\>** element.</span></span>  
  
- <span data-ttu-id="6cd23-117">理想的には、クライアント アプリケーションが通知を受信した後を同じレコードの後続の通知がないように、通知を受け取る既にレコードを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6cd23-117">Ideally, after the client application receives a notification, it should update the record for which the notification is already received so that the subsequent notifications are not for the same record.</span></span> <span data-ttu-id="6cd23-118">たとえば、 **ACCOUNTACTIVITY**を持つテーブルを**処理**列。</span><span class="sxs-lookup"><span data-stu-id="6cd23-118">For example, consider an **ACCOUNTACTIVITY** table that has a **Processed** column.</span></span> <span data-ttu-id="6cd23-119">すべての新しいレコードに挿入されるため、 **ACCOUNTACTIVITY**テーブル内の値、**処理**列は常に ' n '。</span><span class="sxs-lookup"><span data-stu-id="6cd23-119">For all new records inserted into the **ACCOUNTACTIVITY** table, the value in the **Processed** column is always ‘n’.</span></span> <span data-ttu-id="6cd23-120">内のレコード挿入操作の後など、 **ACCOUNTACTIVITY**テーブルは、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="6cd23-120">For example, after an insert operation, the records in the **ACCOUNTACTIVITY** table will look like the following:</span></span>  
  
  |<span data-ttu-id="6cd23-121">アカウントのトランザクション ID</span><span class="sxs-lookup"><span data-stu-id="6cd23-121">Account Transaction ID</span></span>|<span data-ttu-id="6cd23-122">処理済み</span><span class="sxs-lookup"><span data-stu-id="6cd23-122">Processed</span></span>|  
  |----------------------------|---------------|  
  |<span data-ttu-id="6cd23-123">10001</span><span class="sxs-lookup"><span data-stu-id="6cd23-123">10001</span></span>|<span data-ttu-id="6cd23-124">n</span><span class="sxs-lookup"><span data-stu-id="6cd23-124">n</span></span>|  
  
   <span data-ttu-id="6cd23-125">アダプターのクライアントを設定する、新しく挿入されたレコードの通知を受信する、 **NotificationStatement**としてプロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="6cd23-125">To get notifications for the newly inserted record, the adapter client will set the **NotificationStatement** binding property as:</span></span>  
  
  ```  
  SELECT * FROM SCOTT.ACCOUNTACTIVITY WHERE PROCESSED = ‘n’  
  ```  
  
   <span data-ttu-id="6cd23-126">その後、通知を受信するには、クライアント アプリケーションする必要がありますの値を設定、**処理**'y' の列が既にの通知を受け取ったレコードでは、notification ステートメントが動作しないようにします。</span><span class="sxs-lookup"><span data-stu-id="6cd23-126">After, receiving the notification, the client application must set the value of the **Processed** column to ‘y’ so that the notification statement does not operate on the record that was already notified for.</span></span> <span data-ttu-id="6cd23-127">そのため、これを実現する、クライアント アプリケーションする必要があります、更新操作を実行で、 **ACCOUNTACTIVITY**テーブル。</span><span class="sxs-lookup"><span data-stu-id="6cd23-127">So, to achieve this, the client application must perform an Update operation on the **ACCOUNTACTIVITY** table.</span></span> <span data-ttu-id="6cd23-128">更新操作の後で同じ記録、 **ACCOUNTACTIVITY**テーブルは、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="6cd23-128">After the Update operation, the same record in the **ACCOUNTACTIVITY** table will look like the following:</span></span>  
  
  |<span data-ttu-id="6cd23-129">アカウントのトランザクション ID</span><span class="sxs-lookup"><span data-stu-id="6cd23-129">Account Transaction ID</span></span>|<span data-ttu-id="6cd23-130">処理済み</span><span class="sxs-lookup"><span data-stu-id="6cd23-130">Processed</span></span>|  
  |----------------------------|---------------|  
  |<span data-ttu-id="6cd23-131">10001</span><span class="sxs-lookup"><span data-stu-id="6cd23-131">10001</span></span>|<span data-ttu-id="6cd23-132">y</span><span class="sxs-lookup"><span data-stu-id="6cd23-132">y</span></span>|  
  
   <span data-ttu-id="6cd23-133">興味深いことに、更新操作では、通知をアダプターのクライアントに送信もう一度と、プロセス全体がもう一度繰り返されます。</span><span class="sxs-lookup"><span data-stu-id="6cd23-133">Interestingly, the Update operation will again send a notification to the adapter client and the whole process will be repeated again.</span></span> <span data-ttu-id="6cd23-134">そのため、クライアント アプリケーションには、このような不要な通知を破棄する必要なロジックが必要です。</span><span class="sxs-lookup"><span data-stu-id="6cd23-134">So, the client application must have the required logic to discard such unwanted notifications.</span></span>  
  
- <span data-ttu-id="6cd23-135">場合、 **NotifyOnListenerStart**プロパティのバインドは、アダプターは通知を送信アダプターのクライアントに受信場所を開始するたびにします。</span><span class="sxs-lookup"><span data-stu-id="6cd23-135">If the **NotifyOnListenerStart** binding property is true, the adapter will send a notification to the adapter client every time the receive location starts.</span></span> <span data-ttu-id="6cd23-136">バインド プロパティを使用し、通知メッセージを解釈する方法の詳細については、次を参照してください。[受信 Oracle データベース変更通知した後、受信場所のブレーク ダウン](../../adapters-and-accelerators/adapter-oracle-database/receive-oracle-database-change-notifications-after-a-receive-location-breakdown.md)します。</span><span class="sxs-lookup"><span data-stu-id="6cd23-136">For more information on how to use the binding property and interpret the notification message, see [Receiving Oracle Database Change Notifications After a Receive Location Breakdown](../../adapters-and-accelerators/adapter-oracle-database/receive-oracle-database-change-notifications-after-a-receive-location-breakdown.md).</span></span>  
  
## <a name="typical-orchestration-for-receiving-notifications"></a><span data-ttu-id="6cd23-137">通知を受信するための一般的なオーケストレーション</span><span class="sxs-lookup"><span data-stu-id="6cd23-137">Typical Orchestration for Receiving Notifications</span></span>  
 <span data-ttu-id="6cd23-138">このセクションを使用して通知を受信するための一般的なオーケストレーション フローの概要、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="6cd23-138">This section outlines the typical orchestration flow for receiving notifications using the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span>  
  
1. <span data-ttu-id="6cd23-139">オーケストレーションを行う必要があります最初に行うことでは、受信した通知の種類を確認します。</span><span class="sxs-lookup"><span data-stu-id="6cd23-139">The first thing that the orchestration must do is to check the kind of notification received.</span></span> <span data-ttu-id="6cd23-140">確認事項は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6cd23-140">The things to check for are:</span></span>  
  
   - <span data-ttu-id="6cd23-141">かどうか、通知を受信場所の再起動を受信しました。</span><span class="sxs-lookup"><span data-stu-id="6cd23-141">Whether the notification was received for the receive location restart.</span></span>  
  
   - <span data-ttu-id="6cd23-142">Insert などのデータベース テーブルで操作の通知を受信したかどうかは、更新、または削除します。</span><span class="sxs-lookup"><span data-stu-id="6cd23-142">Whether the notification was received for an operation on a database table, such as Insert, Update, or Delete.</span></span>  
  
     <span data-ttu-id="6cd23-143">オーケストレーションを含める必要があります、**式**図形内でメッセージの種類を決定する、xpath クエリを受信したとします。</span><span class="sxs-lookup"><span data-stu-id="6cd23-143">The orchestration must include an **Expression** shape, and within that an xpath query, to decide what kind of message is received.</span></span>  
  
2. <span data-ttu-id="6cd23-144">通知の種類を使用した後、オーケストレーションは受信した通知の種類に基づいて特定のアクションを実行するための判断ブロックを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="6cd23-144">After the notification type is available, the orchestration must include a decision block to perform specific actions based on the type of notification received.</span></span> <span data-ttu-id="6cd23-145">これを実現するオーケストレーションを含める必要があります、**判断**図形。</span><span class="sxs-lookup"><span data-stu-id="6cd23-145">To achieve this, the orchestration must include a **Decide** shape.</span></span> <span data-ttu-id="6cd23-146">**判断**図形から成る、**ルール**ブロックと**Else**ブロックします。</span><span class="sxs-lookup"><span data-stu-id="6cd23-146">The **Decide** shape consists of a **Rule** block and an **Else** block.</span></span> <span data-ttu-id="6cd23-147">内で、**ルール**ブロックする条件を指定して、条件が満たされる場合は、特定の操作を実行するオーケストレーション図形を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="6cd23-147">Within the **Rule** block, you must specify the condition and then include orchestration shapes to perform certain operations if the condition is met.</span></span> <span data-ttu-id="6cd23-148">内で、 **Else**ブロック、条件の場合は、特定の操作を実行するオーケストレーション図形を含める必要があります*いない*満たします。</span><span class="sxs-lookup"><span data-stu-id="6cd23-148">Within the **Else** block, you must include orchestration shapes to perform certain operations if the condition is *not* met.</span></span>  
  
   <span data-ttu-id="6cd23-149">前述の推奨事項がで詳しく説明されている[通知メッセージが BizTalk Server を使用して Oracle データベースで特定のタスクを完了する処理](../../adapters-and-accelerators/adapter-oracle-database/process-notification-messages-to-run-specific-tasks-in-oracle-db-using-biztalk.md)します。</span><span class="sxs-lookup"><span data-stu-id="6cd23-149">The preceding recommendations are described in detail in [Processing Notification Messages to complete Specific Tasks in Oracle Database using BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/process-notification-messages-to-run-specific-tasks-in-oracle-db-using-biztalk.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6cd23-150">参照</span><span class="sxs-lookup"><span data-stu-id="6cd23-150">See Also</span></span>  
 [<span data-ttu-id="6cd23-151">BizTalk Server を使用して Oracle データベースの変更通知を受け取る</span><span class="sxs-lookup"><span data-stu-id="6cd23-151">Receiving Oracle Database Change Notifications Using BizTalk Server</span></span>](../../adapters-and-accelerators/adapter-oracle-database/receive-oracle-database-change-notifications-using-biztalk-server.md)