---
title: 'レッスン 3: 追加された新しい従業員を選択するストアド プロシージャの実行 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ec7897e9-0c77-41b2-8cc2-61745bd3b028
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7af49c026b443fb1ca6a0fb7f35b64cdf1e377f3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222626"
---
# <a name="lesson-3-execute-a-stored-procedure-to-select-new-employees-added"></a><span data-ttu-id="51d09-102">レッスン 3: 追加された新しい従業員を選択するストアド プロシージャを実行します。</span><span class="sxs-lookup"><span data-stu-id="51d09-102">Lesson 3: Execute a Stored Procedure to Select New Employees Added</span></span>
<span data-ttu-id="51d09-103">タスクを理解することは、このレッスンで実行される、前に、これらのタスクが必要な理由をまず理解する必要があります。</span><span class="sxs-lookup"><span data-stu-id="51d09-103">Before understanding the tasks performed in this lesson, you must first understand why these tasks are required.</span></span> <span data-ttu-id="51d09-104">**従業員**ように、新しい従業員を追加するレコードを挿入するテーブルが定義されている、**ステータス**列は、新しい従業員が追加されるたびに、常に「0」に設定します。</span><span class="sxs-lookup"><span data-stu-id="51d09-104">The **Employee** table to which the records are inserted to add a new employee is defined in such a way that a **Status** column is always set to “0” every time a new employee is added.</span></span> <span data-ttu-id="51d09-105">これは、新しく追加した従業員を照会および通知の取得もこの列を使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="51d09-105">This is done so that you can use this column to query for newly added employees and also get notifications.</span></span> <span data-ttu-id="51d09-106">SQL Server で次の SQL ステートメントを実行して、このクエリは。</span><span class="sxs-lookup"><span data-stu-id="51d09-106">In SQL Server, you would query this by running the following SQL statement:</span></span>  
  
```  
SELECT Employee_ID, Name, Designation FROM Employee WHERE Status = 0  
```  
  
 <span data-ttu-id="51d09-107">更新する必要がある従業員を追加の一覧を新しく受信後、**ステータス**「1」を同じクエリを実行して、次回新しい従業員を追加するために列が表示されないレコードの古い従業員もします。</span><span class="sxs-lookup"><span data-stu-id="51d09-107">After receiving the list of newly added employees, you must also update the **Status** column to “1” so that the next time new employees are added and you run the same query, you do not get records for old employees as well.</span></span> <span data-ttu-id="51d09-108">上記の Select ステートメントは、新しく追加した従業員のみ、更新が表示されることを確認する、**従業員**表に、次の SQL ステートメントを使用します。</span><span class="sxs-lookup"><span data-stu-id="51d09-108">To make sure that the above Select statement gives only the newly added employees, you will update the **Employee** table using the following SQL statement:</span></span>  
  
```  
UPDATE Employee SET Status = 1 WHERE Status = 0  
```  
  
 <span data-ttu-id="51d09-109">そのため、**ステータス**古い従業員用の列に設定されている「1」の新しい従業員が「0」は常に、</span><span class="sxs-lookup"><span data-stu-id="51d09-109">So, the **Status** column for the old employees is set to “1” while new employees will always be “0.”</span></span>  
  
 <span data-ttu-id="51d09-110">このレッスンでは、ストアド プロシージャを実行します**UPDATE_EMPLOYEE**、さらに、Select ステートメントおよび Update ステートメントが実行されます。</span><span class="sxs-lookup"><span data-stu-id="51d09-110">In this lesson, you will execute a stored procedure, **UPDATE_EMPLOYEE**, which in turn executes the Select and Update statements.</span></span> <span data-ttu-id="51d09-111">このレッスンを完了したら、後に、オーケストレーションは、次を操作します。</span><span class="sxs-lookup"><span data-stu-id="51d09-111">After you have finished this lesson, your orchestration will do the following:</span></span>  
  
1.  <span data-ttu-id="51d09-112">変更に関する通知を受け取る、**従業員**テーブル。</span><span class="sxs-lookup"><span data-stu-id="51d09-112">Receives notification for any changes to the **Employee** table.</span></span>  
  
2.  <span data-ttu-id="51d09-113">受信した通知メッセージからの通知の種類を抽出します。</span><span class="sxs-lookup"><span data-stu-id="51d09-113">Extracts the type of notification from the notification message received.</span></span>  
  
3.  <span data-ttu-id="51d09-114">オーケストレーションが実行される挿入操作の通知メッセージがある場合、 **UPDATE_EMPLOYEE**ストアド プロシージャです。</span><span class="sxs-lookup"><span data-stu-id="51d09-114">If the notification message is for an Insert operation, the orchestration executes the **UPDATE_EMPLOYEE** stored procedure.</span></span>  
  
4.  <span data-ttu-id="51d09-115">ストアド プロシージャはで新しく入力されたレコードを読み取り、**従業員**テーブル。</span><span class="sxs-lookup"><span data-stu-id="51d09-115">The stored procedure reads the newly entered records in the **Employee** table.</span></span> <span data-ttu-id="51d09-116">ストアド プロシージャの後、新しいレコードを読み取り、設定も、**ステータス**「1」にそれらのレコードの列</span><span class="sxs-lookup"><span data-stu-id="51d09-116">After reading the new records, the stored procedure also sets the **Status** column for those records to “1.”</span></span>  
  
 <span data-ttu-id="51d09-117">今すぐ、ストアド プロシージャの実行が必要な理由がわかります。</span><span class="sxs-lookup"><span data-stu-id="51d09-117">Now you know why you need to execute the stored procedure.</span></span> <span data-ttu-id="51d09-118">これは、オーケストレーションの一部として実行する方法について検討する必要があります。</span><span class="sxs-lookup"><span data-stu-id="51d09-118">You now need to think about how to execute this as part of the orchestration.</span></span> <span data-ttu-id="51d09-119">オーケストレーションに必要な要求メッセージを**UPDATE_EMPLOYEE**ストアド プロシージャです。</span><span class="sxs-lookup"><span data-stu-id="51d09-119">The orchestration needs a request message for the **UPDATE_EMPLOYEE** stored procedure.</span></span> <span data-ttu-id="51d09-120">このチュートリアルでは、実行時に、メッセージが作成され、オーケストレーションに提供するカスタム クラス ライブラリを作成します。</span><span class="sxs-lookup"><span data-stu-id="51d09-120">In this tutorial, you will create a custom class library that will create the message on the fly and then provide it to the orchestration.</span></span> <span data-ttu-id="51d09-121">オーケストレーションは、メッセージを受信した後、SQL アダプターを使用して SQL Server にメッセージを送信され応答を受信します。</span><span class="sxs-lookup"><span data-stu-id="51d09-121">After the orchestration receives the message, it will send the message to the SQL Server using the SQL adapter and receive the response.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="51d09-122">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="51d09-122">In This Section</span></span>  
  
-   [<span data-ttu-id="51d09-123">手順 1: UPDATE_EMPLOYEE の要求メッセージを作成するストアド プロシージャ</span><span class="sxs-lookup"><span data-stu-id="51d09-123">Step 1: Create the Request Message for UPDATE_EMPLOYEE Stored Procedure</span></span>](../../adapters-and-accelerators/adapter-sql/step-1-create-the-request-message-for-update-employee-stored-procedure.md)  
  
-   [<span data-ttu-id="51d09-124">手順 2: SQL Server に要求メッセージを送信し、応答を受信</span><span class="sxs-lookup"><span data-stu-id="51d09-124">Step 2: Send the Request Message to SQL Server and Receive Response</span></span>](../../adapters-and-accelerators/adapter-sql/step-2-send-the-request-message-to-sql-server-and-receive-response.md)