---
title: 'チュートリアル 2: 従業員 - 発注プロセス SQL アダプタの使用 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: eeb4dd1e-209a-47eb-9c0e-a138e02f0ff2
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4d14008611bfb22bf39e446e72ecb3bba4571761
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010779"
---
# <a name="tutorial-2-employee---purchase-order-process-using-the-sql-adapter"></a><span data-ttu-id="1780e-102">チュートリアル 2: 従業員 - 発注プロセス SQL アダプタの使用</span><span class="sxs-lookup"><span data-stu-id="1780e-102">Tutorial 2: Employee - Purchase Order Process using the SQL adapter</span></span>
<span data-ttu-id="1780e-103">このチュートリアルで、機器を配置する購買部門が毎回新しい従業員が組織に加わったを注文プロセスを自動化しています。</span><span class="sxs-lookup"><span data-stu-id="1780e-103">In this tutorial, you are automating the process where the Purchases department that places an equipment order every time a new employee joins the organization.</span></span> <span data-ttu-id="1780e-104">従業員の詳細と発注書の詳細の両方で管理**従業員**と**Purchase_Order**それぞれ、SQL Server データベース内のテーブルします。</span><span class="sxs-lookup"><span data-stu-id="1780e-104">Both employee details and purchase order details are maintained in **Employee** and **Purchase_Order** tables respectively, in a SQL Server database.</span></span> <span data-ttu-id="1780e-105">購買部門は、SQL Server データベースで Purchase_Order テーブルを更新することを電子メールを送信して通知されます。</span><span class="sxs-lookup"><span data-stu-id="1780e-105">The Purchases department is informed by updating the Purchase_Order table in the SQL Server database and by sending an e-mail.</span></span> <span data-ttu-id="1780e-106">プロセスでは、次の操作が行われます。</span><span class="sxs-lookup"><span data-stu-id="1780e-106">Within the process, the following actions occur:</span></span>  
  
1. <span data-ttu-id="1780e-107">アダプターは受信するたびに通知、**従業員**テーブルを更新します。</span><span class="sxs-lookup"><span data-stu-id="1780e-107">The adapter receives a notification each time the **Employee** table is updated.</span></span> <span data-ttu-id="1780e-108">次に、アダプターは、BizTalk オーケストレーションに、通知を送信します。</span><span class="sxs-lookup"><span data-stu-id="1780e-108">The adapter then sends a notification to the BizTalk orchestration.</span></span>  
  
2. <span data-ttu-id="1780e-109">BizTalk オーケストレーションが、通知が用に新しいレコードが挿入されるかどうかを判定、**従業員**テーブル。</span><span class="sxs-lookup"><span data-stu-id="1780e-109">The BizTalk orchestration figures out whether the notification is for a new record inserted into the **Employee** table.</span></span> <span data-ttu-id="1780e-110">通知の上の他の操作の場合、**従業員**テーブル、オーケストレーションの操作は実行されません。</span><span class="sxs-lookup"><span data-stu-id="1780e-110">If the notification is for any other operation on the **Employee** table, the orchestration does not perform any operation.</span></span>  
  
3. <span data-ttu-id="1780e-111">場合は、通知が挿入操作では、**従業員**新しい従業員レコードが追加された、オーケストレーションを使用してのことを通知する、テーブル、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]新しいレコードの詳細を確認します。</span><span class="sxs-lookup"><span data-stu-id="1780e-111">If the notification is for an Insert operation on the **Employee** table, notifying that a new employee record was added, the orchestration uses the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] to read the details of the new record.</span></span>  
  
4. <span data-ttu-id="1780e-112">オーケストレーションでは、新しい追加された従業員レコードの詳細を含む応答を受信します。</span><span class="sxs-lookup"><span data-stu-id="1780e-112">The orchestration receives a response that contains the details of the new added employee record.</span></span> <span data-ttu-id="1780e-113">オーケストレーションのマップ、 **Employee_ID**と**指定**挿入操作の要求メッセージに対する応答でフィールドに、 **Purchase_Order**テーブル。</span><span class="sxs-lookup"><span data-stu-id="1780e-113">The orchestration maps the **Employee_ID** and **Designation** fields in the response to the request message for the Insert operation on the **Purchase_Order** table.</span></span>  
  
5. <span data-ttu-id="1780e-114">次にオーケストレーションを使用して、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] 、挿入操作を実行する、 **Purchase_Order**テーブル。</span><span class="sxs-lookup"><span data-stu-id="1780e-114">The orchestration then uses the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] to perform an Insert operation on the **Purchase_Order** table.</span></span> <span data-ttu-id="1780e-115">挿入操作の応答は、購買部門に電子メールとして送信されます。</span><span class="sxs-lookup"><span data-stu-id="1780e-115">The response for the Insert operation is sent to the Purchases department as an e-mail.</span></span>  
  
## <a name="about-the-database-objects-used-in-this-sample"></a><span data-ttu-id="1780e-116">このサンプルで使用されるデータベース オブジェクトについて</span><span class="sxs-lookup"><span data-stu-id="1780e-116">About the Database Objects Used in this Sample</span></span>  
 <span data-ttu-id="1780e-117">このチュートリアルでは、サンプルに付属する SQL スクリプトによって作成されたデータベース オブジェクトを使用します。</span><span class="sxs-lookup"><span data-stu-id="1780e-117">This tutorial uses the database objects created by the SQL script shipped with the samples.</span></span> <span data-ttu-id="1780e-118">スクリプトとサンプルの詳細については、[アダプタ サンプル](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1780e-118">For more information about the script and the samples, see [Adapter Samples](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md).</span></span> <span data-ttu-id="1780e-119">このチュートリアルで使用するデータベース オブジェクトは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1780e-119">The database objects that you will use in this tutorial are:</span></span>  
  
- <span data-ttu-id="1780e-120">**ADAPTER_SAMPLES**データベース。</span><span class="sxs-lookup"><span data-stu-id="1780e-120">**ADAPTER_SAMPLES** database.</span></span>  
  
- <span data-ttu-id="1780e-121">**従業員**と**Purchase_Order**テーブル。</span><span class="sxs-lookup"><span data-stu-id="1780e-121">**Employee** and **Purchase_Order** tables.</span></span>  
  
- <span data-ttu-id="1780e-122">**UPDATE_EMPLOYEE**ストアド プロシージャ。</span><span class="sxs-lookup"><span data-stu-id="1780e-122">**UPDATE_EMPLOYEE** stored procedure.</span></span>  
  
  <span data-ttu-id="1780e-123">このサンプルで提供される SQL スクリプトを実行するときに、これらすべてのデータベース オブジェクトが作成されます。</span><span class="sxs-lookup"><span data-stu-id="1780e-123">All these database objects are created when you run the SQL script provided with the sample.</span></span> <span data-ttu-id="1780e-124">チュートリアルを開始する前に、スクリプトを実行することを確認します。</span><span class="sxs-lookup"><span data-stu-id="1780e-124">Make sure you run the script before you start with the tutorial.</span></span>  
  
## <a name="sample-based-on-this-tutorial"></a><span data-ttu-id="1780e-125">このチュートリアルに基づくサンプル</span><span class="sxs-lookup"><span data-stu-id="1780e-125">Sample Based on This Tutorial</span></span>  
 <span data-ttu-id="1780e-126">サンプルについては、 **Employee_PurchaseOrder**でも提供するは、このチュートリアルに基づいて、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="1780e-126">A sample, **Employee_PurchaseOrder**, which is based on this tutorial is also provided with the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="1780e-127">詳細については、[アダプタ サンプル](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1780e-127">For more information, see [Adapter Samples](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md).</span></span>  
  
 <span data-ttu-id="1780e-128">アダプターを使用して BizTalk プロジェクトを作成する方法を理解するには、完全にチュートリアルを読み進めるし、参照としてサンプルを見ることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="1780e-128">We recommend that you go through the tutorial completely to understand how to create BizTalk projects using the adapter, and then look at the sample as a reference.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1780e-129">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="1780e-129">In This Section</span></span>  
  
-   [<span data-ttu-id="1780e-130">レッスン 1: スキーマを生成してメッセージを作成する</span><span class="sxs-lookup"><span data-stu-id="1780e-130">Lesson 1: Generate Schemas and Create Messages</span></span>](../../adapters-and-accelerators/adapter-sql/lesson-1-generate-schemas-and-create-messages.md)  
  
-   [<span data-ttu-id="1780e-131">レッスン 2: 通知を受信してフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="1780e-131">Lesson 2: Receive and Filter Notifications</span></span>](../../adapters-and-accelerators/adapter-sql/lesson-2-receive-and-filter-notifications.md)  
  
-   [<span data-ttu-id="1780e-132">レッスン 3: ストアド プロシージャを実行して、追加された新しい従業員を選択する</span><span class="sxs-lookup"><span data-stu-id="1780e-132">Lesson 3: Execute a Stored Procedure to Select New Employees Added</span></span>](../../adapters-and-accelerators/adapter-sql/lesson-3-execute-a-stored-procedure-to-select-new-employees-added.md)  
  
-   [<span data-ttu-id="1780e-133">レッスン 4: 注文テーブルに対して挿入操作を実行する</span><span class="sxs-lookup"><span data-stu-id="1780e-133">Lesson 4: Perform an Insert Operation on the Purchase Order Table</span></span>](../../adapters-and-accelerators/adapter-sql/lesson-4-perform-an-insert-operation-on-the-purchase-order-table.md)  
  
-   [<span data-ttu-id="1780e-134">レッスン 5: ソリューションを展開する</span><span class="sxs-lookup"><span data-stu-id="1780e-134">Lesson 5: Deploy the Solution</span></span>](../../adapters-and-accelerators/adapter-sql/lesson-5-deploy-the-solution.md)