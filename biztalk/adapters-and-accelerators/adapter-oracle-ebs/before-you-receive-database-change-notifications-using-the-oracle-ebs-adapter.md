---
title: Oracle E-business Suite アダプターを使用して通知を変更するデータベースを受信するための考慮事項 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 95bbb19e-8d31-4b27-8cfe-6760e4bb0808
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f3157b8ab7a706203d3b9475de890fb2a8f8dd3a
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25963176"
---
# <a name="considerations-for-receiving-database-change-notifications-using-the-oracle-e-business-suite-adapter"></a><span data-ttu-id="dbb33-102">変更 Oracle E-business Suite アダプターを使用して通知を受信するデータベースに関する注意点</span><span class="sxs-lookup"><span data-stu-id="dbb33-102">Considerations for receiving database change notifications using the Oracle E-Business Suite adapter</span></span>
<span data-ttu-id="dbb33-103">このトピックでは、いくつかの考慮事項とベスト プラクティスを使用しているときに点に注意する必要がある、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] Oracle データベースからデータベースの通知を受信します。</span><span class="sxs-lookup"><span data-stu-id="dbb33-103">This topic provides some considerations and best practices that you must keep in mind while using the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] to receive database notifications from an Oracle database.</span></span>  
  
## <a name="considerations-while-using-the-adapter-to-receive-notifications"></a><span data-ttu-id="dbb33-104">アダプターを使用して通知を受信するときの考慮事項</span><span class="sxs-lookup"><span data-stu-id="dbb33-104">Considerations While Using the Adapter to Receive Notifications</span></span>  
 <span data-ttu-id="dbb33-105">使用しているときに、次を考慮する必要があります、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]クエリ通知を受信します。</span><span class="sxs-lookup"><span data-stu-id="dbb33-105">You must consider the following while using the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] to receive query notifications.</span></span>  
  
-   <span data-ttu-id="dbb33-106">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]アダプター クライアントに、Oracle データベースから受信する通知に渡します。</span><span class="sxs-lookup"><span data-stu-id="dbb33-106">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] simply passes on the notification, which it receives from the Oracle database, to the adapter clients.</span></span> <span data-ttu-id="dbb33-107">アダプターは区別されません、通知のさまざまな操作は、つまり、アダプター情報のない任意の挿入操作または更新操作は、特定の通知するかどうか。</span><span class="sxs-lookup"><span data-stu-id="dbb33-107">The adapter does not distinguish between the notifications for different operations, i.e., the adapter does not have any information whether a particular notification is for an Insert operation or an Update operation.</span></span>  
  
-   <span data-ttu-id="dbb33-108">操作の通知メッセージは、その操作によって影響を受けたレコードの数の影響を受けません。</span><span class="sxs-lookup"><span data-stu-id="dbb33-108">The notification message for an operation is not affected by the number of records affected by that operation.</span></span> <span data-ttu-id="dbb33-109">たとえば、アダプター クライアントに関係なく、Oracle データベース テーブルに挿入されるレコードの数、1 つだけの通知メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="dbb33-109">For example, irrespective of the number of records inserted in an Oracle database table, the adapter clients receive only one notification message.</span></span>  
  
-   <span data-ttu-id="dbb33-110">アダプターのクライアント アプリケーションに Oracle データベースから受信した通知の種類を解釈するためのロジックが含まれていることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="dbb33-110">We recommend that the adapter client application contain the logic to interpret the kind of notification received from the Oracle database.</span></span> <span data-ttu-id="dbb33-111">アダプター クライアント アプリケーションを内の情報を抽出することによって行うことができます、 **\<情報\>** 通知を受信したメッセージの要素。</span><span class="sxs-lookup"><span data-stu-id="dbb33-111">The adapter client applications can do so by extracting the information in the **\<Info\>** element of the received notification message.</span></span> <span data-ttu-id="dbb33-112">挿入操作用に受信した通知メッセージの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="dbb33-112">Here’s an example of a notification message received for an Insert operation.</span></span>  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>   
    <Notification xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/Notification/">  
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
  
     <span data-ttu-id="dbb33-113">内の値に注意してください、 **\<情報\>** 要素。</span><span class="sxs-lookup"><span data-stu-id="dbb33-113">Notice the value within the **\<Info\>** element.</span></span> <span data-ttu-id="dbb33-114">この値は、通知メッセージを受信した操作について説明します。</span><span class="sxs-lookup"><span data-stu-id="dbb33-114">This value provides information on the operation for which the notification message was received.</span></span> <span data-ttu-id="dbb33-115">アプリケーション内の値を抽出する機能を持つ必要があります、 **\<情報\>** 要素し、値に基づいて、後続のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="dbb33-115">Your application should have the functionality to extract the value within the **\<Info\>** element and then based on the value, perform subsequent tasks.</span></span> <span data-ttu-id="dbb33-116">トピック[Oracle E-business Suite で特定のタスクを実行する通知メッセージを処理](../../adapters-and-accelerators/adapter-oracle-ebs/process-notification-messages-to-complete-specific-tasks-in-oracle-ebs.md)内の値を抽出する方法の手順を持つ、 **\<情報\>** 要素.</span><span class="sxs-lookup"><span data-stu-id="dbb33-116">The topic [Process Notification Messages to Complete Specific Tasks in Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/process-notification-messages-to-complete-specific-tasks-in-oracle-ebs.md) has instructions on how to extract the value within the **\<Info\>** element.</span></span>  
  
-   <span data-ttu-id="dbb33-117">理想的には、クライアント アプリケーションは、通知を受信した後を通知を既に受信した同じレコードの後続の通知がされないように、レコードを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dbb33-117">Ideally, after the client application receives a notification, it should update the record for which the notification is already received so that the subsequent notifications are not for the same record.</span></span> <span data-ttu-id="dbb33-118">たとえば、 **ACCOUNTACTIVITY**を持つテーブル、**処理**列です。</span><span class="sxs-lookup"><span data-stu-id="dbb33-118">For example, consider an **ACCOUNTACTIVITY** table that has a **Processed** column.</span></span> <span data-ttu-id="dbb33-119">すべての新しいレコードが挿入されるため、 **ACCOUNTACTIVITY**テーブル内の値、**処理**列は常に 'n' です。</span><span class="sxs-lookup"><span data-stu-id="dbb33-119">For all new records inserted into the **ACCOUNTACTIVITY** table, the value in the **Processed** column is always ‘n’.</span></span> <span data-ttu-id="dbb33-120">内のレコード挿入操作の後など、 **ACCOUNTACTIVITY**テーブルは、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="dbb33-120">For example, after an insert operation, the records in the **ACCOUNTACTIVITY** table will look like the following:</span></span>  
  
    |<span data-ttu-id="dbb33-121">アカウントのトランザクションの ID</span><span class="sxs-lookup"><span data-stu-id="dbb33-121">Account Transaction ID</span></span>|<span data-ttu-id="dbb33-122">処理済み</span><span class="sxs-lookup"><span data-stu-id="dbb33-122">Processed</span></span>|  
    |----------------------------|---------------|  
    |<span data-ttu-id="dbb33-123">10001</span><span class="sxs-lookup"><span data-stu-id="dbb33-123">10001</span></span>|n|  
  
     <span data-ttu-id="dbb33-124">アダプターのクライアントを設定、新しく挿入したレコードの通知を受信する、 **NotificaitonStatement**バインディングとしてのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="dbb33-124">To get notifications for the newly inserted record, the adapter client will set the **NotificaitonStatement** binding property as:</span></span>  
  
    ```  
    SELECT * FROM SCOTT.ACCOUNTACTIVITY WHERE PROCESSED = ‘n’  
    ```  
  
     <span data-ttu-id="dbb33-125">その後、通知を受信するには、クライアント アプリケーションする必要がありますの値を設定、**処理**'y' 列が既にの通知を受け取ったレコードでは、notification ステートメントが動作しないようにします。</span><span class="sxs-lookup"><span data-stu-id="dbb33-125">After, receiving the notification, the client application must set the value of the **Processed** column to ‘y’ so that the notification statement does not operate on the record that was already notified for.</span></span> <span data-ttu-id="dbb33-126">そのため、これを実現する、クライアント アプリケーションする必要があります更新プログラムで操作を実行、 **ACCOUNTACTIVITY**テーブル。</span><span class="sxs-lookup"><span data-stu-id="dbb33-126">So, to achieve this, the client application must perform an Update operation on the **ACCOUNTACTIVITY** table.</span></span> <span data-ttu-id="dbb33-127">内のレコード、同じ更新操作の完了後、 **ACCOUNTACTIVITY**テーブルは、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="dbb33-127">After the Update operation, the same record in the **ACCOUNTACTIVITY** table will look like the following:</span></span>  
  
    |<span data-ttu-id="dbb33-128">アカウントのトランザクションの ID</span><span class="sxs-lookup"><span data-stu-id="dbb33-128">Account Transaction ID</span></span>|<span data-ttu-id="dbb33-129">処理済み</span><span class="sxs-lookup"><span data-stu-id="dbb33-129">Processed</span></span>|  
    |----------------------------|---------------|  
    |<span data-ttu-id="dbb33-130">10001</span><span class="sxs-lookup"><span data-stu-id="dbb33-130">10001</span></span>|<span data-ttu-id="dbb33-131">y</span><span class="sxs-lookup"><span data-stu-id="dbb33-131">y</span></span>|  
  
     <span data-ttu-id="dbb33-132">興味深いことに、更新操作は、アダプターのクライアントに通知を再度送信します。 および、プロセス全体はもう一度繰り返されます。</span><span class="sxs-lookup"><span data-stu-id="dbb33-132">Interestingly, the Update operation will again send a notification to the adapter client and the whole process will be repeated again.</span></span> <span data-ttu-id="dbb33-133">そのため、クライアント アプリケーションには、このような不要な通知を破棄する必要なロジックが必要です。</span><span class="sxs-lookup"><span data-stu-id="dbb33-133">So, the client application must have the required logic to discard such unwanted notifications.</span></span>  
  
-   <span data-ttu-id="dbb33-134">場合、 **NotifyOnListenerStart**プロパティのバインドは、アダプターは通知を送信アダプター クライアントたびに、受信場所を開始します。</span><span class="sxs-lookup"><span data-stu-id="dbb33-134">If the **NotifyOnListenerStart** binding property is true, the adapter will send a notification to the adapter client every time the receive location starts.</span></span> <span data-ttu-id="dbb33-135">バインディング プロパティを使用し、通知メッセージを解釈する方法の詳細については、次を参照してください。[受信 Oracle E-business Suite データベース変更通知後に、受信場所内訳](../../adapters-and-accelerators/adapter-oracle-ebs/receive-oracle-ebs-database-change-notifications-after-a-receive-location-stops.md)です。</span><span class="sxs-lookup"><span data-stu-id="dbb33-135">For more information on how to use the binding property and interpret the notification message, see [Receive Oracle E-Business Suite Database Change Notifications After a Receive Location Breakdown](../../adapters-and-accelerators/adapter-oracle-ebs/receive-oracle-ebs-database-change-notifications-after-a-receive-location-stops.md).</span></span>  
  
## <a name="typical-orchestration-for-receiving-notifications"></a><span data-ttu-id="dbb33-136">通知を受信するための一般的なオーケストレーション</span><span class="sxs-lookup"><span data-stu-id="dbb33-136">Typical Orchestration for Receiving Notifications</span></span>  
 <span data-ttu-id="dbb33-137">このセクションで説明を使用して通知を受信するための一般的なオーケストレーション フロー、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="dbb33-137">This section outlines the typical orchestration flow for receiving notifications using the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span></span>  
  
1.  <span data-ttu-id="dbb33-138">オーケストレーションが行う必要があります最初の手順では、受信した通知の種類を確認します。</span><span class="sxs-lookup"><span data-stu-id="dbb33-138">The first thing that the orchestration must do is to check the kind of notification received.</span></span> <span data-ttu-id="dbb33-139">確認事項は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="dbb33-139">The things to check for are:</span></span>  
  
    -   <span data-ttu-id="dbb33-140">かどうか、受信場所の再起動の通知を受信しました。</span><span class="sxs-lookup"><span data-stu-id="dbb33-140">Whether the notification was received for the receive location restart.</span></span>  
  
    -   <span data-ttu-id="dbb33-141">Insert などのデータベース テーブル上の操作に対して、通知を受信したかどうかは、更新、または削除します。</span><span class="sxs-lookup"><span data-stu-id="dbb33-141">Whether the notification was received for an operation on a database table, such as Insert, Update, or Delete.</span></span>  
  
     <span data-ttu-id="dbb33-142">オーケストレーションを含める必要があります、**式**図形、メッセージの種類を決定する、xpath クエリが受信されるとします。</span><span class="sxs-lookup"><span data-stu-id="dbb33-142">The orchestration must include an **Expression** shape, and within that an xpath query, to decide what kind of message is received.</span></span>  
  
2.  <span data-ttu-id="dbb33-143">通知の種類を使用した後、オーケストレーションは、受信した通知の種類に基づいて特定のアクションを実行する判断ブロックを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="dbb33-143">After the notification type is available, the orchestration must include a decision block to perform specific actions based on the type of notification received.</span></span> <span data-ttu-id="dbb33-144">そのため、オーケストレーションを含める必要があります、**判断**図形です。</span><span class="sxs-lookup"><span data-stu-id="dbb33-144">To achieve this, the orchestration must include a **Decide** shape.</span></span> <span data-ttu-id="dbb33-145">**判断**図形から成る、**ルール**ブロックと**Else**ブロックします。</span><span class="sxs-lookup"><span data-stu-id="dbb33-145">The **Decide** shape consists of a **Rule** block and an **Else** block.</span></span> <span data-ttu-id="dbb33-146">内で、**ルール**ブロック、条件を指定して、条件が満たされた場合、特定の操作を実行するオーケストレーション図形を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="dbb33-146">Within the **Rule** block, you must specify the condition and then include orchestration shapes to perform certain operations if the condition is met.</span></span> <span data-ttu-id="dbb33-147">内で、 **Else**ブロック、条件の場合は、特定の操作を実行するオーケストレーション図形を含める必要があります*されません*満たされています。</span><span class="sxs-lookup"><span data-stu-id="dbb33-147">Within the **Else** block, you must include orchestration shapes to perform certain operations if the condition is *not* met.</span></span>  
  
 <span data-ttu-id="dbb33-148">上記の推奨事項がで詳しく説明されている[Oracle E-business Suite で特定のタスクを実行する通知メッセージを処理](../../adapters-and-accelerators/adapter-oracle-ebs/process-notification-messages-to-complete-specific-tasks-in-oracle-ebs.md)です。</span><span class="sxs-lookup"><span data-stu-id="dbb33-148">The preceding recommendations are described in detail in [Process Notification Messages to Complete Specific Tasks in Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/process-notification-messages-to-complete-specific-tasks-in-oracle-ebs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dbb33-149">参照</span><span class="sxs-lookup"><span data-stu-id="dbb33-149">See Also</span></span>  
 [<span data-ttu-id="dbb33-150">Oracle E-business Suite データベース変更を使用して通知 BizTalk Server の受信します。</span><span class="sxs-lookup"><span data-stu-id="dbb33-150">Receive Oracle E-Business Suite Database Change Notifications using BizTalk Server</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/receive-oracle-ebs-database-change-notifications-using-biztalk-server.md)