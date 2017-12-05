---
title: "不完全なアクティビティ インスタンスを削除する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7060578c-6267-487b-8530-efa18f9431ce
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2809fd4fcc1d94a96b158ffa46c3e217084a905d
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-remove-incomplete-activity-instances"></a><span data-ttu-id="8f668-102">不完全なアクティビティ インスタンスを削除する方法</span><span class="sxs-lookup"><span data-stu-id="8f668-102">How to Remove Incomplete Activity Instances</span></span>
<span data-ttu-id="8f668-103">BAM 定義ファイルを展開すると、定義ファイルで定義された各アクティビティに対し、5 個のテーブルが BAM プライマリ インポート データベースに作成されます。</span><span class="sxs-lookup"><span data-stu-id="8f668-103">When a BAM definition file is deployed, five tables are created in the BAM Primary Import database for each activity defined in the definition file.</span></span> <span data-ttu-id="8f668-104">作成されるテーブルは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="8f668-104">These tables are:</span></span>  
  
-   <span data-ttu-id="8f668-105">bam_`ActivityName`_Active</span><span class="sxs-lookup"><span data-stu-id="8f668-105">bam_`ActivityName`_Active</span></span>  
  
-   <span data-ttu-id="8f668-106">bam_`ActivityName`_Completed</span><span class="sxs-lookup"><span data-stu-id="8f668-106">bam_`ActivityName`_Completed</span></span>  
  
-   <span data-ttu-id="8f668-107">bam_`ActivityName`_ActiveRelationships</span><span class="sxs-lookup"><span data-stu-id="8f668-107">bam_`ActivityName`_ActiveRelationships</span></span>  
  
-   <span data-ttu-id="8f668-108">bam_`ActivityName`_CompletedRelationships</span><span class="sxs-lookup"><span data-stu-id="8f668-108">bam_`ActivityName`_CompletedRelationships</span></span>  
  
-   <span data-ttu-id="8f668-109">bam_`ActivityName`_Continuations</span><span class="sxs-lookup"><span data-stu-id="8f668-109">bam_`ActivityName`_Continuations</span></span>  
  
 <span data-ttu-id="8f668-110">`ActivityName` は、ユーザーが定義したアクティビティの名前になります。</span><span class="sxs-lookup"><span data-stu-id="8f668-110">Where `ActivityName` is the name of the activity that the user has defined.</span></span>  
  
 <span data-ttu-id="8f668-111">通常の実行では、不完全なデータは bam_`ActivityName`_Active テーブルに残ります。</span><span class="sxs-lookup"><span data-stu-id="8f668-111">During normal execution, incomplete data remains in the bam_`ActivityName`_Active table.</span></span> <span data-ttu-id="8f668-112">データにリレーションシップおよび参照があるかどうかは、データがあります、bam で\_`ActivityName`_ActiveRelationships テーブル。</span><span class="sxs-lookup"><span data-stu-id="8f668-112">If the data has relations and references, then there will be data in the bam\_`ActivityName`_ActiveRelationships table.</span></span>  
  
 <span data-ttu-id="8f668-113">Continuation を使用したアクティビティの追跡時には、アクティビティが不完全な状態で BAM データベースに残される場合があります。</span><span class="sxs-lookup"><span data-stu-id="8f668-113">During the tracking of activities that use continuations, there may be instances in which an activity is left in an incomplete state in the BAM databases.</span></span> <span data-ttu-id="8f668-114">このトピックの最後に示すストアド プロシージャ作成スクリプトを使用すると、不完全なレコードを削除するストアド プロシージャを作成できます。</span><span class="sxs-lookup"><span data-stu-id="8f668-114">You can use the stored procedure creation script at the end of this topic to create a stored procedure that will purge the incomplete records.</span></span>  
  
 <span data-ttu-id="8f668-115">ストアド プロシージャを作成するには、スクリプトをコピーしてから、SQL Server Management を使用して BAM プライマリ インポート データベースに対しスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="8f668-115">To create the stored procedure, copy the script and execute it against the BAM Primary Import database by using SQL Server Management.</span></span> <span data-ttu-id="8f668-116">スクリプトは、という名前のストアド プロシージャを生成**RemoveDanglingInstances**データベースにします。</span><span class="sxs-lookup"><span data-stu-id="8f668-116">The script will generate a stored procedure named **RemoveDanglingInstances** in the database.</span></span>  
  
### <a name="to-create-the-removedanglinginstances-stored-procedure"></a><span data-ttu-id="8f668-117">RemoveDanglingInstances ストアド プロシージャを作成するには</span><span class="sxs-lookup"><span data-stu-id="8f668-117">To create the RemoveDanglingInstances stored procedure</span></span>  
  
1.  <span data-ttu-id="8f668-118">をクリックして**開始**、 をクリックして**すべてのプログラム**をクリックして**Microsoft SQL Server 2008 SP1**または**Microsoft SQL Server 2008 R2**をクリックして**SQL Server Management Studio**です。</span><span class="sxs-lookup"><span data-stu-id="8f668-118">Click **Start**, click **All Programs**, click **Microsoft SQL Server 2008 SP1** or **Microsoft SQL Server 2008 R2**, and then click **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="8f668-119">**サーバーへの接続**ダイアログ ボックスでは、SQL server および適切な認証方法を選択し、をクリックして**接続**です。</span><span class="sxs-lookup"><span data-stu-id="8f668-119">In the **Connect to Server** dialog box, select the SQL server and the appropriate authentication method, and then click **Connect**.</span></span>  
  
3.  <span data-ttu-id="8f668-120">サーバー名を展開し、**データベース**、BAM プライマリ インポート データベースを選択します。</span><span class="sxs-lookup"><span data-stu-id="8f668-120">Expand the server name, expand **Databases**, and then select the BAM Primary Import database.</span></span>  
  
4.  <span data-ttu-id="8f668-121">**[新しいクエリ]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8f668-121">Click **New Query**.</span></span>  
  
5.  <span data-ttu-id="8f668-122">ストアド プロシージャ作成スクリプトをコピーし、右側のペインに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="8f668-122">Copy the stored procedure creation script and paste it into the right pane.</span></span>  
  
6.  <span data-ttu-id="8f668-123">をクリックして**Execute**スクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="8f668-123">Click **Execute** to run the script.</span></span> <span data-ttu-id="8f668-124">結果として得られるストアド プロシージャは、dbo としてストアド プロシージャの一覧で表示できます。RemoveDanglingInstances です。</span><span class="sxs-lookup"><span data-stu-id="8f668-124">The resulting stored procedure can be viewed in the list of stored procedures as dbo.RemoveDanglingInstances.</span></span>  
  
### <a name="to-remove-incomplete-activity-instances"></a><span data-ttu-id="8f668-125">不完全なアクティビティ インスタンスを削除するには</span><span class="sxs-lookup"><span data-stu-id="8f668-125">To remove incomplete activity instances</span></span>  
  
1.  <span data-ttu-id="8f668-126">をクリックして**開始**、 をクリックして**すべてのプログラム**をクリックして**Microsoft SQL Server 2008 SP1**または**Microsoft SQL Server 2008 R2**をクリックして**SQL Server Management Studio**です。</span><span class="sxs-lookup"><span data-stu-id="8f668-126">Click **Start**, click **All Programs**, click **Microsoft SQL Server 2008 SP1** or **Microsoft SQL Server 2008 R2**, and then click **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="8f668-127">**サーバーへの接続**ダイアログ ボックスでは、SQL server および適切な認証方法を選択し、をクリックして**接続**です。</span><span class="sxs-lookup"><span data-stu-id="8f668-127">In the **Connect to Server** dialog box, select the SQL server and the appropriate authentication method, and then click **Connect**.</span></span>  
  
3.  <span data-ttu-id="8f668-128">サーバー名を展開し、**データベース**、BAM プライマリ インポート データベースを選択します。</span><span class="sxs-lookup"><span data-stu-id="8f668-128">Expand the server name, expand **Databases**, and then select the BAM Primary Import database.</span></span>  
  
4.  <span data-ttu-id="8f668-129">**[新しいクエリ]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8f668-129">Click **New Query**.</span></span>  
  
5.  <span data-ttu-id="8f668-130">右側のウィンドウで次のように入力します。`exec RemoveDanglingInstances`および実行する削除操作に適切なパラメーターです。</span><span class="sxs-lookup"><span data-stu-id="8f668-130">In the right pane, type `exec RemoveDanglingInstances` and the appropriate parameters for the remove operation you are performing.</span></span> <span data-ttu-id="8f668-131">たとえば、注文書アクティビティの不完全なインスタンスをすべて削除するには、「`exec RemoveDanglingInstances @ActivityName = 'PurchaseOrder'`」と入力します。</span><span class="sxs-lookup"><span data-stu-id="8f668-131">For example, to remove all incomplete instances of the Purchase Order activity, type `exec RemoveDanglingInstances @ActivityName = 'PurchaseOrder'`.</span></span>  
  
6.  <span data-ttu-id="8f668-132">をクリックして**Execute**スクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="8f668-132">Click **Execute** to run the script.</span></span>  
  
## <a name="removedanglinginstances-usage-examples"></a><span data-ttu-id="8f668-133">RemoveDanglingInstances の使用例</span><span class="sxs-lookup"><span data-stu-id="8f668-133">RemoveDanglingInstances Usage Examples</span></span>  
 <span data-ttu-id="8f668-134">ストアド プロシージャには、4 つのパラメーターが表示されることができます。</span><span class="sxs-lookup"><span data-stu-id="8f668-134">The stored procedure can receive four parameters:</span></span>  
  
|<span data-ttu-id="8f668-135">パラメーター</span><span class="sxs-lookup"><span data-stu-id="8f668-135">Parameter</span></span>|<span data-ttu-id="8f668-136">Description</span><span class="sxs-lookup"><span data-stu-id="8f668-136">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8f668-137">@ActivityName nvarchar(128)</span><span class="sxs-lookup"><span data-stu-id="8f668-137">@ActivityName nvarchar(128)</span></span>|<span data-ttu-id="8f668-138">削除する不完全なアクティビティ インスタンスの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="8f668-138">Specifies the name of the incomplete activity instance to remove.</span></span>|  
|<span data-ttu-id="8f668-139">@ActivityId nvarchar(128)</span><span class="sxs-lookup"><span data-stu-id="8f668-139">@ActivityId nvarchar(128)</span></span>|<span data-ttu-id="8f668-140">(省略可能) 指定したインスタンス識別子を持つ未解決のインスタンスだけをストアド プロシージャで削除するように指定します。</span><span class="sxs-lookup"><span data-stu-id="8f668-140">(Optional) Specifies that the stored procedure remove only the dangling instance with the specified instance identifier.</span></span>|  
|<span data-ttu-id="8f668-141">@DateThresholddatetime</span><span class="sxs-lookup"><span data-stu-id="8f668-141">@DateThreshold datetime</span></span>|<span data-ttu-id="8f668-142">(省略可能)すべてのアクティブなインスタンスされている古いアクティブなテーブルにあることを指定します (等しくないと古い、古いのみ)、指定された日付よりも削除されます。</span><span class="sxs-lookup"><span data-stu-id="8f668-142">(Optional) Specifies that all the active instances in the active table that are older (not equal to and older, only older) than the given date are removed.</span></span>|  
|<span data-ttu-id="8f668-143">@NewTableExtensionnvarchar (30)</span><span class="sxs-lookup"><span data-stu-id="8f668-143">@NewTableExtension nvarchar(30)</span></span>|<span data-ttu-id="8f668-144">(省略可能) ストアド プロシージャで、指定された拡張子を既存のアクティビティ テーブルに連結して新しいテーブルを 3 つ作成するように指定します。</span><span class="sxs-lookup"><span data-stu-id="8f668-144">(Optional) Specifies that the stored procedure creates three new tables by concatenating the supplied extension to the existing activity tables.</span></span><br /><br /> <span data-ttu-id="8f668-145">結果のテーブルになります。</span><span class="sxs-lookup"><span data-stu-id="8f668-145">The resulting tables will be:</span></span><br /><br /> <span data-ttu-id="8f668-146">bam_ActivityName_Active_\<拡張機能\></span><span class="sxs-lookup"><span data-stu-id="8f668-146">bam_ActivityName_Active_\<Extension\></span></span><br /><br /> <span data-ttu-id="8f668-147">bam_ActivityName_ActiveRelationships_\<拡張機能\></span><span class="sxs-lookup"><span data-stu-id="8f668-147">bam_ActivityName_ActiveRelationships_\<Extension\></span></span><br /><br /> <span data-ttu-id="8f668-148">bam_ActivityName_Continuations_\<拡張機能\></span><span class="sxs-lookup"><span data-stu-id="8f668-148">bam_ActivityName_Continuations_\<Extension\></span></span><br /><br /> <span data-ttu-id="8f668-149">不完全なインスタンスは、データベースから削除される代わりに、これらの新しいテーブルに移動されます。</span><span class="sxs-lookup"><span data-stu-id="8f668-149">The incomplete instances are moved to the new tables rather than being purged from the database.</span></span><br /><br /> <span data-ttu-id="8f668-150">これらのテーブルが既に存在する場合は、再利用されます。存在しない場合は作成されます。</span><span class="sxs-lookup"><span data-stu-id="8f668-150">If the tables already exist, the stored procedure reuses them; otherwise they are created.</span></span> <span data-ttu-id="8f668-151">**重要:**ストアド プロシージャ、テーブルが既に存在しない場合、これらのスキーマが作成された場合に使用されるものと一致する前提としています。</span><span class="sxs-lookup"><span data-stu-id="8f668-151">**Important:**  If the tables already exist, the stored procedure assumes that their schemas match the ones that would be used if they were created.</span></span> <span data-ttu-id="8f668-152">スキーマが一致しない場合は、ストアド プロシージャはレコードを挿入できず、削除操作が失敗します。</span><span class="sxs-lookup"><span data-stu-id="8f668-152">If a schema does not match, the stored procedure will fail to insert the records and the remove operation will fail.</span></span>|  
  
 `exec RemoveDanglingInstances @ActivityName = 'PurchaseOrder'`  
  
 <span data-ttu-id="8f668-153">アクティブ テーブル、アクティブ リレーションシップ テーブル、および Continuation テーブルにある PurchaseOrder アクティビティのアクティブなインスタンスをすべて削除します。</span><span class="sxs-lookup"><span data-stu-id="8f668-153">Removes all active instances of the 'PurchaseOrder' activity in the active, active relationships, and continuations tables.</span></span>  
  
 `exec RemoveDanglingInstances @ActivityName = 'PurchaseOrder', @ActivityId = 'PO220567'`  
  
 <span data-ttu-id="8f668-154">PurchaseOrder アクティビティのアクティブ テーブル、アクティブ リレーションシップ テーブル、および Continuation テーブルから、アクティビティ ID が PO220567 であるアクティビティ インスタンスだけを削除します。</span><span class="sxs-lookup"><span data-stu-id="8f668-154">Removes only the activity instance that has an Activity ID of 'PO220567' from the active, active relationships, and continuations tables for the 'PurchaseOrder' activity.</span></span>  
  
 `exec RemoveDanglingInstances @ActivityName = 'PurchaseOrder', @DateThreshold='2005-02-02 19:27:03:533'`  
  
 <span data-ttu-id="8f668-155">PurchaseOrder アクティビティのアクティブ テーブル、アクティブ リレーションシップ テーブル、および Continuation テーブルから、LastModified の日時が 2005 年 2 月 2 日午後 7:27:03.533 よりも古いアクティビティ インスタンスをすべて削除します。</span><span class="sxs-lookup"><span data-stu-id="8f668-155">Removes all the activity instances that have a LastModified time that is older than Feb 2nd, 2005 7:27:03.533 PM from the active, active relationships, and continuations tables for the 'PurchaseOrder' activity.</span></span>  
  
 `exec RemoveDanglingInstances @ActivityName = 'PurchaseOrder', @ActivityId = 'PO220567', @DateThreshold='2005-02-02 19:27:03:533'`  
  
 <span data-ttu-id="8f668-156">LastModified 列が 2005 年 2 月 2 日午後 7:27:03.533 よりも古い場合にのみ、アクティビティ ID が PO220567 であるアクティビティ インスタンスを削除します。</span><span class="sxs-lookup"><span data-stu-id="8f668-156">Removes the activity instance whose activity ID is PO220567 only if its LastModified column is older than Feb 2nd, 2005 7:27:03.533 PM.</span></span>  
  
 `exec RemoveDanglingInstances @ActivityName = 'PurchaseOrder', @DateThreshold='2005-02-02 19:27:03:533', @NewTableExtension=N'Dangling'`  
  
 <span data-ttu-id="8f668-157">データベース内に次のテーブルを作成します。</span><span class="sxs-lookup"><span data-stu-id="8f668-157">Creates the following tables in the database:</span></span>  
  
 <span data-ttu-id="8f668-158">bam_PurchaseOrder_Active_Dangling</span><span class="sxs-lookup"><span data-stu-id="8f668-158">bam_PurchaseOrder_Active_Dangling</span></span>  
  
 <span data-ttu-id="8f668-159">bam_PurchaseOrder_ActiveRelationships_Dangling</span><span class="sxs-lookup"><span data-stu-id="8f668-159">bam_PurchaseOrder_ActiveRelationships_Dangling</span></span>  
  
 <span data-ttu-id="8f668-160">bam_PurchaseOrder_Continuations_Dangling</span><span class="sxs-lookup"><span data-stu-id="8f668-160">bam_PurchaseOrder_Continuations_Dangling</span></span>  
  
 <span data-ttu-id="8f668-161">ストアド プロシージャは、PurchaseOrder アクティビティのアクティブ テーブル、アクティブ リレーションシップ テーブル、および Continuation テーブルから、2005 年 2 月 2 日午後 7:27:03.533 よりも古い不完全なアクティビティ インスタンスをすべてコピーし、新しく作成されたテーブルに挿入します。</span><span class="sxs-lookup"><span data-stu-id="8f668-161">The stored procedure copies all incomplete activity instances that are older than Feb 2nd, 2005 7:27:03.533 PM from the active, active relationships, and continuations tables for the 'PurchaseOrder' activity, and inserts them into the newly created tables.</span></span> <span data-ttu-id="8f668-162">次に、コピー済みのアクティビティ インスタンスが、アクティブ テーブル、アクティブ リレーションシップ テーブル、および Continuation テーブルから削除されます。</span><span class="sxs-lookup"><span data-stu-id="8f668-162">The copied activity instances are then removed from the active, active relationships, and continuations tables.</span></span>  
  
## <a name="stored-procedure-creation-script"></a><span data-ttu-id="8f668-163">ストアド プロシージャ作成スクリプト</span><span class="sxs-lookup"><span data-stu-id="8f668-163">Stored Procedure Creation Script</span></span>  
  
```  
EXEC sp_stored_procedures @sp_name = 'RemoveDanglingInstances'  
IF @@ROWCOUNT > 0 DROP PROCEDURE RemoveDanglingInstances  
GO  
  
CREATE PROCEDURE RemoveDanglingInstances  
    @ActivityName nvarchar(128),  
    @ActivityId nvarchar(128) = NULL,  
    @DateThreshold datetime = NULL,  
    @NewTableExtension nvarchar(30) = NULL  
AS  
    DECLARE @QueryString nvarchar(4000)  
    DECLARE @ActiveTableName sysname  
    DECLARE @ActiveRelationshipsTableName sysname  
    DECLARE @ContinuationsTableName sysname  
    DECLARE @DanglingActiveTableName sysname  
    DECLARE @DanglingActiveRelationshipsTableName sysname  
    DECLARE @DanglingContinuationsTableName sysname  
  
    SET @ActiveTableName = 'bam_' + @ActivityName + '_Active'  
    SET @ActiveRelationshipsTableName = 'bam_' + @ActivityName + '_ActiveRelationships'  
    SET @ContinuationsTableName = 'bam_' + @ActivityName + '_Continuations'  
  
    SET TRANSACTION ISOLATION LEVEL READ COMMITTED  
    BEGIN TRAN  
  
    DECLARE @LockActivity nvarchar(128)  
    SELECT @LockActivity = ActivityName  
    FROM bam_Metadata_Activities WITH (XLOCK)  
    WHERE ActivityName = @ActivityName  
  
    EXEC sp_tables @table_name = #DanglingActivities  
    IF @@ROWCOUNT > 0 DROP TABLE #DanglingActivities  
  
    CREATE TABLE #DanglingActivities(ActivityID nvarchar(128) PRIMARY KEY)  
  
    SET @QueryString = N'INSERT INTO #DanglingActivities (ActivityID) SELECT ActivityID FROM [bam_' + @ActivityName + '_Active]'  
  
    IF (@DateThreshold is not NULL) OR (@ActivityId is not NULL)  
    BEGIN  
        SET @QueryString = @QueryString + ' WHERE'  
    END  
  
    IF (@DateThreshold is not NULL)  
    BEGIN  
        SET @QueryString = @QueryString + ' LastModified < N''' + CONVERT(nvarchar(50), @DateThreshold, 109) + ''''  
        IF (@ActivityId is not NULL)  
        BEGIN  
            SET @QueryString = @QueryString + ' AND'  
        END  
    END  
  
    IF (@ActivityId is not NULL)  
    BEGIN  
        SET @QueryString = @QueryString + ' ActivityID = N''' + @ActivityId + ''''  
    END  
  
    EXEC sp_executesql @QueryString  
    SELECT * FROM #DanglingActivities  
  
    SET @QueryString = N''  
  
    -- If the user gave a table extension, the dangling instances will be inserted  
    -- into that table.   
    IF (isnull(@NewTableExtension, '') <> '')  
    BEGIN  
        SET @DanglingActiveTableName = @ActiveTableName + '_' + @NewTableExtension  
        SET @DanglingActiveRelationshipsTableName = @ActiveRelationshipsTableName + '_' + @NewTableExtension  
        SET @DanglingContinuationsTableName = @ContinuationsTableName + '_' + @NewTableExtension  
  
        -- If the table for the dangling instances exists then insert into it  
        -- If the table does not exist, then create the dangling instances table  
        -- and then insert into it. SELECT INTO will do that.  
        EXEC sp_tables @table_name = @DanglingActiveTableName  
        IF @@ROWCOUNT > 0  
        BEGIN  
            SET @QueryString = N'INSERT INTO ' + '[' + @DanglingActiveTableName + '] SELECT active.* FROM [' + @ActiveTableName + '] active INNER JOIN #DanglingActivities dangling ON active.ActivityID = dangling.ActivityID'  
            EXEC sp_executesql @QueryString  
        END  
        ELSE  
        BEGIN  
            SET @QueryString = N'SELECT active.* INTO [' + @DanglingActiveTableName + '] FROM [' + @ActiveTableName + '] active INNER JOIN #DanglingActivities dangling ON active.ActivityID = dangling.ActivityID'  
            EXEC sp_executesql @QueryString  
        END  
  
        -- Now do what you did for the Active Instances table for the   
        -- ActiveRelationships table  
        EXEC sp_tables @table_name = @DanglingActiveRelationshipsTableName  
        IF @@ROWCOUNT > 0  
        BEGIN  
            SET @QueryString = N'INSERT INTO ' + '[' + @DanglingActiveRelationshipsTableName + '] SELECT active.* FROM [' + @ActiveRelationshipsTableName + '] active INNER JOIN #DanglingActivities dangling ON active.ActivityID = dangling.ActivityID'  
            EXEC sp_executesql @QueryString  
        END  
        ELSE  
        BEGIN  
            SET @QueryString = N'SELECT active.* INTO [' + @DanglingActiveRelationshipsTableName + '] FROM [' + @ActiveRelationshipsTableName + '] active INNER JOIN #DanglingActivities dangling ON active.ActivityID = dangling.ActivityID'  
            EXEC sp_executesql @QueryString  
        END  
  
        -- And finally for the continuations table  
        EXEC sp_tables @table_name = @DanglingContinuationsTableName  
        IF @@ROWCOUNT > 0  
        BEGIN  
            SET @QueryString = N'INSERT INTO ' + '[' + @DanglingContinuationsTableName + '] SELECT active.* FROM [' + @ContinuationsTableName + '] active INNER JOIN #DanglingActivities dangling ON active.ParentActivityID = dangling.ActivityID'  
            EXEC sp_executesql @QueryString  
        END  
        ELSE  
        BEGIN  
            SET @QueryString = N'SELECT active.* INTO [' + @DanglingContinuationsTableName + '] FROM [' + @ContinuationsTableName + '] active INNER JOIN #DanglingActivities dangling ON active.ParentActivityID = dangling.ActivityID'  
            EXEC sp_executesql @QueryString  
        END  
    END  
  
    -- Remove the dangling instances from the Active Instances Table  
    SET @QueryString = 'DELETE FROM [' + @ActiveTableName + '] FROM [' + @ActiveTableName + '] active INNER JOIN #DanglingActivities dangling ON active.ActivityID = dangling.ActivityID '  
    EXEC sp_executesql @QueryString  
  
    SET @QueryString = 'DELETE FROM [' + @ActiveRelationshipsTableName + '] FROM [' + @ActiveRelationshipsTableName + '] active INNER JOIN #DanglingActivities dangling ON active.ActivityID = dangling.ActivityID '  
    EXEC sp_executesql @QueryString  
  
    SET @QueryString = 'DELETE FROM [' + @ContinuationsTableName + '] FROM [' + @ContinuationsTableName + '] active INNER JOIN #DanglingActivities dangling ON active.ParentActivityID = dangling.ActivityID '  
    EXEC sp_executesql @QueryString  
  
    DROP TABLE #DanglingActivities  
  
    COMMIT TRAN      
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="8f668-164">参照</span><span class="sxs-lookup"><span data-stu-id="8f668-164">See Also</span></span>  
 [<span data-ttu-id="8f668-165">BAM データベースの管理</span><span class="sxs-lookup"><span data-stu-id="8f668-165">Managing BAM Databases</span></span>](../core/managing-bam-databases.md)