---
title: 'レッスン 3: 追加された新しい従業員を選択するストアド プロシージャの実行 |Microsoft Docs'
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
ms.openlocfilehash: 3021a5e3ead821a0f3c8d0372d48ae469a834c1c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001859"
---
# <a name="lesson-3-execute-a-stored-procedure-to-select-new-employees-added"></a><span data-ttu-id="98fc5-102">レッスン 3: 追加された新しい従業員を選択するストアド プロシージャを実行します。</span><span class="sxs-lookup"><span data-stu-id="98fc5-102">Lesson 3: Execute a Stored Procedure to Select New Employees Added</span></span>
<span data-ttu-id="98fc5-103">このレッスンでは、タスクを理解することが実行される前に、これらのタスクが必要な理由をまず理解する必要があります。</span><span class="sxs-lookup"><span data-stu-id="98fc5-103">Before understanding the tasks performed in this lesson, you must first understand why these tasks are required.</span></span> <span data-ttu-id="98fc5-104">**従業員**ような方法で、新しい従業員を追加するレコードを挿入するテーブルが定義されているが、**状態**列は、新しい従業員が追加されるたびに、常に「0」に設定します。</span><span class="sxs-lookup"><span data-stu-id="98fc5-104">The **Employee** table to which the records are inserted to add a new employee is defined in such a way that a **Status** column is always set to “0” every time a new employee is added.</span></span> <span data-ttu-id="98fc5-105">これは、新しく追加された従業員に対してクエリを実行し、通知を受け取ることも、この列を使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="98fc5-105">This is done so that you can use this column to query for newly added employees and also get notifications.</span></span> <span data-ttu-id="98fc5-106">SQL Server で次の SQL ステートメントを実行してこのクエリは。</span><span class="sxs-lookup"><span data-stu-id="98fc5-106">In SQL Server, you would query this by running the following SQL statement:</span></span>  
  
```  
SELECT Employee_ID, Name, Designation FROM Employee WHERE Status = 0  
```  
  
 <span data-ttu-id="98fc5-107">更新する必要がある従業員を追加の一覧を新しく受信後、**状態**「1」を同じクエリを実行して、次回の新しい従業員を追加するために列が表示されないレコードの古い従業員もします。</span><span class="sxs-lookup"><span data-stu-id="98fc5-107">After receiving the list of newly added employees, you must also update the **Status** column to “1” so that the next time new employees are added and you run the same query, you do not get records for old employees as well.</span></span> <span data-ttu-id="98fc5-108">上記の Select ステートメントは、新しく追加された従業員のみを更新するかどうかを確認する、**従業員**表の次の SQL ステートメントを使用します。</span><span class="sxs-lookup"><span data-stu-id="98fc5-108">To make sure that the above Select statement gives only the newly added employees, you will update the **Employee** table using the following SQL statement:</span></span>  
  
```  
UPDATE Employee SET Status = 1 WHERE Status = 0  
```  
  
 <span data-ttu-id="98fc5-109">そのため、**状態**古い従業員を対象の列は、新しい従業員が「0」は常に「1」に設定されます</span><span class="sxs-lookup"><span data-stu-id="98fc5-109">So, the **Status** column for the old employees is set to “1” while new employees will always be “0.”</span></span>  
  
 <span data-ttu-id="98fc5-110">このレッスンでは、ストアド プロシージャを実行する**UPDATE_EMPLOYEE**、さらに、Select および Update ステートメントを実行します。</span><span class="sxs-lookup"><span data-stu-id="98fc5-110">In this lesson, you will execute a stored procedure, **UPDATE_EMPLOYEE**, which in turn executes the Select and Update statements.</span></span> <span data-ttu-id="98fc5-111">このレッスンを完了したら、後に、オーケストレーションは、次を操作します。</span><span class="sxs-lookup"><span data-stu-id="98fc5-111">After you have finished this lesson, your orchestration will do the following:</span></span>  
  
1. <span data-ttu-id="98fc5-112">変更の通知を受け取る、**従業員**テーブル。</span><span class="sxs-lookup"><span data-stu-id="98fc5-112">Receives notification for any changes to the **Employee** table.</span></span>  
  
2. <span data-ttu-id="98fc5-113">受信した通知メッセージから通知の種類を抽出します。</span><span class="sxs-lookup"><span data-stu-id="98fc5-113">Extracts the type of notification from the notification message received.</span></span>  
  
3. <span data-ttu-id="98fc5-114">通知メッセージの挿入操作の場合、オーケストレーションの実行、 **UPDATE_EMPLOYEE**ストアド プロシージャ。</span><span class="sxs-lookup"><span data-stu-id="98fc5-114">If the notification message is for an Insert operation, the orchestration executes the **UPDATE_EMPLOYEE** stored procedure.</span></span>  
  
4. <span data-ttu-id="98fc5-115">ストアド プロシージャで新たに入力されたレコードの読み取り、**従業員**テーブル。</span><span class="sxs-lookup"><span data-stu-id="98fc5-115">The stored procedure reads the newly entered records in the **Employee** table.</span></span> <span data-ttu-id="98fc5-116">ストアド プロシージャのもの設定、新しいレコードを読んだら、**状態**「1」にそれらのレコードの列</span><span class="sxs-lookup"><span data-stu-id="98fc5-116">After reading the new records, the stored procedure also sets the **Status** column for those records to “1.”</span></span>  
  
   <span data-ttu-id="98fc5-117">これでストアド プロシージャを実行する必要がある理由がわかります。</span><span class="sxs-lookup"><span data-stu-id="98fc5-117">Now you know why you need to execute the stored procedure.</span></span> <span data-ttu-id="98fc5-118">これは、オーケストレーションの一部として実行する方法について検討する必要があります。</span><span class="sxs-lookup"><span data-stu-id="98fc5-118">You now need to think about how to execute this as part of the orchestration.</span></span> <span data-ttu-id="98fc5-119">オーケストレーションに必要な要求メッセージを**UPDATE_EMPLOYEE**ストアド プロシージャ。</span><span class="sxs-lookup"><span data-stu-id="98fc5-119">The orchestration needs a request message for the **UPDATE_EMPLOYEE** stored procedure.</span></span> <span data-ttu-id="98fc5-120">このチュートリアルでは、その場でメッセージが作成され、オーケストレーションに提供するカスタム クラス ライブラリを作成します。</span><span class="sxs-lookup"><span data-stu-id="98fc5-120">In this tutorial, you will create a custom class library that will create the message on the fly and then provide it to the orchestration.</span></span> <span data-ttu-id="98fc5-121">オーケストレーションはメッセージを受信後 SQL アダプターを使用して SQL Server にメッセージを送信し、応答を受信します。</span><span class="sxs-lookup"><span data-stu-id="98fc5-121">After the orchestration receives the message, it will send the message to the SQL Server using the SQL adapter and receive the response.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="98fc5-122">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="98fc5-122">In This Section</span></span>  
  
-   [<span data-ttu-id="98fc5-123">手順 1: UPDATE_EMPLOYEE ストアド プロシージャの要求メッセージを作成する</span><span class="sxs-lookup"><span data-stu-id="98fc5-123">Step 1: Create the Request Message for UPDATE_EMPLOYEE Stored Procedure</span></span>](../../adapters-and-accelerators/adapter-sql/step-1-create-the-request-message-for-update-employee-stored-procedure.md)  
  
-   [<span data-ttu-id="98fc5-124">手順 2: SQL Server に要求メッセージを送信し、応答を受信する</span><span class="sxs-lookup"><span data-stu-id="98fc5-124">Step 2: Send the Request Message to SQL Server and Receive Response</span></span>](../../adapters-and-accelerators/adapter-sql/step-2-send-the-request-message-to-sql-server-and-receive-response.md)