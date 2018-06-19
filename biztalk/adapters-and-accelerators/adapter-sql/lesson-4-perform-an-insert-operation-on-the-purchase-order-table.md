---
title: 'レッスン 4: Purchase Order テーブルで挿入操作の実行 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 66fc64c5-a3da-4014-8545-f34e6577bd73
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1c966e3c10f18424b2cfb1fde0235caedbb5f58f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222690"
---
# <a name="lesson-4-perform-an-insert-operation-on-the-purchase-order-table"></a><span data-ttu-id="cff4f-102">レッスン 4: Purchase Order テーブルで挿入操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="cff4f-102">Lesson 4: Perform an Insert Operation on the Purchase Order Table</span></span>
<span data-ttu-id="cff4f-103">[レッスン 3: 追加された新しい従業員を選択するストアド プロシージャの実行](../../adapters-and-accelerators/adapter-sql/lesson-3-execute-a-stored-procedure-to-select-new-employees-added.md)、実行する、 **UPDATE_EMPLOYEE**ストアド プロシージャとの詳細を含む応答メッセージを受信して、新しく従業員のレコードを挿入します。</span><span class="sxs-lookup"><span data-stu-id="cff4f-103">In [Lesson 3: Execute a Stored Procedure to Select New Employees Added](../../adapters-and-accelerators/adapter-sql/lesson-3-execute-a-stored-procedure-to-select-new-employees-added.md), you executed the **UPDATE_EMPLOYEE** stored procedure and received a response message that contains the details of the newly inserted employee record.</span></span> <span data-ttu-id="cff4f-104">このレッスンでは、前のレッスンで作成し、オーケストレーションを更新する、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="cff4f-104">In this lesson, you will build on the previous lesson and update the orchestration to perform the following steps:</span></span>  
  
1.  <span data-ttu-id="cff4f-105">挿入操作を実行するメッセージの構築、オーケストレーション内で、 **Purchase_Order**テーブル。</span><span class="sxs-lookup"><span data-stu-id="cff4f-105">Within the orchestration, you build the message to perform an Insert operation on the **Purchase_Order** table.</span></span> <span data-ttu-id="cff4f-106">この手順はのような[手順 1: UPDATE_EMPLOYEE ストアド プロシージャ用の要求メッセージを作成する](../../adapters-and-accelerators/adapter-sql/step-1-create-the-request-message-for-update-employee-stored-procedure.md)です。</span><span class="sxs-lookup"><span data-stu-id="cff4f-106">This step is similar to [Step 1: Create the Request Message for UPDATE_EMPLOYEE Stored Procedure](../../adapters-and-accelerators/adapter-sql/step-1-create-the-request-message-for-update-employee-stored-procedure.md).</span></span>  
  
2.  <span data-ttu-id="cff4f-107">応答メッセージをマップする要求メッセージを構築した後、 **UPDATE_EMPLOYEE**でストアド プロシージャの挿入操作の要求メッセージを**Purchase_Order**テーブル。</span><span class="sxs-lookup"><span data-stu-id="cff4f-107">After you build the request message, you map the response message of the **UPDATE_EMPLOYEE** stored procedure to the request message for the Insert operation on the **Purchase_Order** table.</span></span> <span data-ttu-id="cff4f-108">メッセージをマップすることによって、挿入操作の要求メッセージに応答メッセージから受信した値を渡します。</span><span class="sxs-lookup"><span data-stu-id="cff4f-108">By mapping the messages, you pass the values received from the response messages to the request message for Insert operation.</span></span>  
  
3.  <span data-ttu-id="cff4f-109">内のレコードを挿入するメッセージを送信する、 **Purchase_Order**テーブルが表示され、応答を受信します。</span><span class="sxs-lookup"><span data-stu-id="cff4f-109">You send the message to insert a record in the **Purchase_Order** table and receive a response.</span></span>  
  
4.  <span data-ttu-id="cff4f-110">送信ポートに応答を送信します。</span><span class="sxs-lookup"><span data-stu-id="cff4f-110">You send the response to a send port.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="cff4f-111">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="cff4f-111">In This Section</span></span>  
  
-   [<span data-ttu-id="cff4f-112">手順 1: Purchase_Order テーブルに対する挿入操作の要求メッセージを作成します。</span><span class="sxs-lookup"><span data-stu-id="cff4f-112">Step 1: Create the Request Message for Insert Operation on Purchase_Order Table</span></span>](../../adapters-and-accelerators/adapter-sql/step-1-create-the-request-message-for-insert-operation-on-purchase-order-table.md)  
  
-   [<span data-ttu-id="cff4f-113">手順 2: マップ操作の要求メッセージを挿入する UPDATE_EMPLOYEE 応答メッセージ</span><span class="sxs-lookup"><span data-stu-id="cff4f-113">Step 2: Map the UPDATE_EMPLOYEE Response Message to Insert Operation Request Message</span></span>](../../adapters-and-accelerators/adapter-sql/step-2-map-update_employee-response-to-insert-operation-request.md)  
  
-   [<span data-ttu-id="cff4f-114">手順 3: レコードを挿入し、応答を受信する要求メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="cff4f-114">Step 3: Send the Request Message to Insert Records and Receive a Response</span></span>](../../adapters-and-accelerators/adapter-sql/step-3-send-the-request-message-to-insert-records-and-receive-a-response.md)  
  
-   [<span data-ttu-id="cff4f-115">手順 4: プロジェクトをビルドします</span><span class="sxs-lookup"><span data-stu-id="cff4f-115">Step 4: Build the Project</span></span>](../../adapters-and-accelerators/adapter-sql/step-4-build-the-project.md)