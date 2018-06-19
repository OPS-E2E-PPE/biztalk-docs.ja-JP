---
title: '手順 4: アプリケーションのテスト |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 488b13fa-7a71-4430-bbf5-dbf47ba55562
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 347c2bcf459d7e9ce7b1fb9efc07579be81d989d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22223034"
---
# <a name="step-4-test-the-application"></a><span data-ttu-id="41c0e-102">手順 4: アプリケーションをテストします。</span><span class="sxs-lookup"><span data-stu-id="41c0e-102">Step 4: Test the Application</span></span>
<span data-ttu-id="41c0e-103">![4 のステップ 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-4of4.gif "Step_4of4")</span><span class="sxs-lookup"><span data-stu-id="41c0e-103">![Step 4 of 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-4of4.gif "Step_4of4")</span></span>  
  
 <span data-ttu-id="41c0e-104">**所要時間:** 10 分</span><span class="sxs-lookup"><span data-stu-id="41c0e-104">**Time to complete:** 10 minutes</span></span>  
  
 <span data-ttu-id="41c0e-105">**目標:** 内のレコードを挿入することで、アプリケーションをテストするこの手順で、**従業員**のテーブル、 **ADAPTER_SAMPLES**データベース。</span><span class="sxs-lookup"><span data-stu-id="41c0e-105">**Objective:** In this step, you test the application by inserting a record in the **Employee** table of the **ADAPTER_SAMPLES** database.</span></span> <span data-ttu-id="41c0e-106">オーケストレーションはへの変更の通知を受け取る場合は、アプリケーションが正しく機能する、**従業員**テーブル。</span><span class="sxs-lookup"><span data-stu-id="41c0e-106">If the application is working properly, the orchestration receives a notification for changes to the **Employee** table.</span></span> <span data-ttu-id="41c0e-107">オーケストレーションは、受信した通知の種類を抽出します。</span><span class="sxs-lookup"><span data-stu-id="41c0e-107">The orchestration then extracts the type of notification received.</span></span> <span data-ttu-id="41c0e-108">オーケストレーションが実行される挿入操作の通知がある場合、 **UPDATE_EMPLOYEE**ストアド プロシージャと、応答を受信します。</span><span class="sxs-lookup"><span data-stu-id="41c0e-108">If the notification is for an Insert operation, the orchestration executes the **UPDATE_EMPLOYEE** stored procedure and receives a response.</span></span> <span data-ttu-id="41c0e-109">オーケストレーションの値を抽出する**Employee_ID**と**名前**応答からし、それらに挿入、 **Purchase_Order**テーブル。</span><span class="sxs-lookup"><span data-stu-id="41c0e-109">The orchestration extracts the values of **Employee_ID** and **Name** from the response and inserts them into the **Purchase_Order** table.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="41c0e-110">前提条件</span><span class="sxs-lookup"><span data-stu-id="41c0e-110">Prerequisites</span></span>  
 <span data-ttu-id="41c0e-111">この手順を始める前に、次を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="41c0e-111">Before starting with this step, you must ensure the following:</span></span>  
  
-   <span data-ttu-id="41c0e-112">要求メッセージを呼び出し、 **UPDATE_EMPLOYEE**ストアド プロシージャは C:\TestLocation\CreateEmployeeMessage に使用します。</span><span class="sxs-lookup"><span data-stu-id="41c0e-112">A request message to invoke the **UPDATE_EMPLOYEE** stored procedure is available at C:\TestLocation\CreateEmployeeMessage.</span></span> <span data-ttu-id="41c0e-113">要求メッセージは、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="41c0e-113">The request message looks like the following:</span></span>  
  
    ```  
    <UPDATE_EMPLOYEE xmlns="http://schemas.microsoft.com/Sql/2008/05/TypedProcedures/dbo" />  
    ```  
  
-   <span data-ttu-id="41c0e-114">に対して、挿入操作を呼び出すための要求メッセージ、 **Purchase_Order**テーブルは C:\TestLocation\CreatePOMessage に使用します。</span><span class="sxs-lookup"><span data-stu-id="41c0e-114">A request message to invoke the Insert operation on the **Purchase_Order** table is available at C:\TestLocation\CreatePOMessage.</span></span> <span data-ttu-id="41c0e-115">要求メッセージは、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="41c0e-115">The request message looks like the following:</span></span>  
  
    ```  
    <Insert xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/dbo/Purchase_Order">  
      <Rows>  
        <Purchase_Order xmlns="http://schemas.microsoft.com/Sql/2008/05/Types/Tables/dbo">  
          <Employee_ID>10</Employee_ID><Employee_Name>Employee_Name</Employee_Name>  
        </Purchase_Order>  
      </Rows>  
    </Insert>  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="41c0e-116">値、 **Employee_ID**と**Employee_Name**フィールドは、プレース ホルダーです。</span><span class="sxs-lookup"><span data-stu-id="41c0e-116">The values for the **Employee_ID** and **Employee_Name** fields are placeholders.</span></span> <span data-ttu-id="41c0e-117">実行時にオーケストレーションでは、実際の値が挿入されます。</span><span class="sxs-lookup"><span data-stu-id="41c0e-117">The actual values are inserted by the orchestration at run-time.</span></span>  
  
-   <span data-ttu-id="41c0e-118">完了する必要があります[手順 3: 構成し、アプリケーションを起動](../../adapters-and-accelerators/adapter-sql/step-3-configure-and-start-the-application.md)です。</span><span class="sxs-lookup"><span data-stu-id="41c0e-118">You must have completed [Step 3: Configure and Start the Application](../../adapters-and-accelerators/adapter-sql/step-3-configure-and-start-the-application.md).</span></span>  
  
### <a name="to-test-the-application"></a><span data-ttu-id="41c0e-119">アプリケーションをテストするには</span><span class="sxs-lookup"><span data-stu-id="41c0e-119">To test the application</span></span>  
  
1.  <span data-ttu-id="41c0e-120">内のレコードを挿入、**従業員**テーブル。</span><span class="sxs-lookup"><span data-stu-id="41c0e-120">Insert a record in the **Employee** table.</span></span> <span data-ttu-id="41c0e-121">SQL Server Management Studio から次のステートメントを実行して、これを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="41c0e-121">You can do so by running the following statement from SQL Server Management Studio.</span></span>  
  
    ```  
    INSERT INTO [ADAPTER_SAMPLES].[dbo].[Employee] ([Name] ,[Designation] ,[Salary])  
    VALUES('John Smith' ,'Manager' ,500000)  
    ```  
  
2.  <span data-ttu-id="41c0e-122">チェック、**従業員**データベース内のテーブルです。</span><span class="sxs-lookup"><span data-stu-id="41c0e-122">Check the **Employee** table in the database.</span></span> <span data-ttu-id="41c0e-123">によって、新しいレコードが追加されていることを確認は、**ステータス**列が「0」を返します。</span><span class="sxs-lookup"><span data-stu-id="41c0e-123">You will notice that the new record is added by the **Status** column is “0.”</span></span>  
  
3.  <span data-ttu-id="41c0e-124">更新を保持、**従業員**レコードの表にします。</span><span class="sxs-lookup"><span data-stu-id="41c0e-124">Keep refreshing the **Employee** table records.</span></span> <span data-ttu-id="41c0e-125">表示になります、**ステータス**新しいレコードの列は、現在「1」に設定</span><span class="sxs-lookup"><span data-stu-id="41c0e-125">You will notice that the **Status** column for the new record is now set to “1.”</span></span>  
  
4.  <span data-ttu-id="41c0e-126">チェック、 **Purchase_Order**テーブル。</span><span class="sxs-lookup"><span data-stu-id="41c0e-126">Check the **Purchase_Order** table.</span></span> <span data-ttu-id="41c0e-127">同じ従業員名の指定、レコード、Insert ステートメントに示されているがテーブルに追加することがわかります。</span><span class="sxs-lookup"><span data-stu-id="41c0e-127">You will notice that a record with the same employee name and designation, as you provided in the Insert statement, is added to the table.</span></span>  
  
5.  <span data-ttu-id="41c0e-128">SMTP ポート構成では、電子メールのエイリアスを指定した場合も、挿入操作の応答メッセージに電子メールが送信されます。</span><span class="sxs-lookup"><span data-stu-id="41c0e-128">If you provided your e-mail alias in the SMTP port configuration, you will also receive an e-mail with the response message for the Insert operation.</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="41c0e-129">でしただけは何ですか。</span><span class="sxs-lookup"><span data-stu-id="41c0e-129">What did I just do?</span></span>  
 <span data-ttu-id="41c0e-130">内のレコードを挿入することで、SampleApplication アプリケーションをテスト、**従業員**テーブル。</span><span class="sxs-lookup"><span data-stu-id="41c0e-130">Tested the SampleApplication application by inserting a record in the **Employee** table.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="41c0e-131">次の手順</span><span class="sxs-lookup"><span data-stu-id="41c0e-131">Next Steps</span></span>  
 <span data-ttu-id="41c0e-132">テストが成功した場合、ソリューションに問題ありません。</span><span class="sxs-lookup"><span data-stu-id="41c0e-132">If the test worked, congratulations!</span></span> <span data-ttu-id="41c0e-133">完了して、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]チュートリアルです。</span><span class="sxs-lookup"><span data-stu-id="41c0e-133">You have completed the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] tutorial.</span></span>  
  
 <span data-ttu-id="41c0e-134">テストが成功しなかった場合は、必要なオブジェクトをすべて追加しているかどうかと、プロパティを正しく設定しているかどうかを確認してください。</span><span class="sxs-lookup"><span data-stu-id="41c0e-134">If the test did not work, carefully check your work to make sure that you added all of the necessary objects and set their properties correctly.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41c0e-135">参照</span><span class="sxs-lookup"><span data-stu-id="41c0e-135">See Also</span></span>  
 <span data-ttu-id="41c0e-136">[手順 3: を構成し、アプリケーションを起動](../../adapters-and-accelerators/adapter-sql/step-3-configure-and-start-the-application.md) </span><span class="sxs-lookup"><span data-stu-id="41c0e-136">[Step 3: Configure and Start the Application](../../adapters-and-accelerators/adapter-sql/step-3-configure-and-start-the-application.md) </span></span>  
 [<span data-ttu-id="41c0e-137">レッスン 5: ソリューションを配置します。</span><span class="sxs-lookup"><span data-stu-id="41c0e-137">Lesson 5: Deploy the Solution</span></span>](../../adapters-and-accelerators/adapter-sql/lesson-5-deploy-the-solution.md)