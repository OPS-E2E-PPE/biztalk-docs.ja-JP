---
title: "不完全なアクティビティ インスタンスの削除 |Microsoft ドキュメント"
description: "BizTalk Server で BAM プライマリ インポート データベースから不完全なインスタンスを削除するカスタム RemoveDanglingInstances SQL スクリプトを実行します。"
ms.custom: 
ms.date: 01/18/2018
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
ms.openlocfilehash: 542d92b838b1638a2d018c6325d4c40467545c42
ms.sourcegitcommit: 9e7a7dc5544d30d4523c0b3cdaa59f4890e7a4e9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/19/2018
---
# <a name="remove-incomplete-activity-instances"></a><span data-ttu-id="e9b0d-103">不完全なアクティビティ インスタンスを削除します。</span><span class="sxs-lookup"><span data-stu-id="e9b0d-103">Remove Incomplete Activity Instances</span></span>
<span data-ttu-id="e9b0d-104">BAM 定義ファイルを展開すると、定義ファイルで定義された各アクティビティに対し、5 個のテーブルが BAM プライマリ インポート データベースに作成されます。</span><span class="sxs-lookup"><span data-stu-id="e9b0d-104">When a BAM definition file is deployed, five tables are created in the BAM Primary Import database for each activity defined in the definition file.</span></span> <span data-ttu-id="e9b0d-105">作成されるテーブルは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e9b0d-105">These tables are:</span></span>  
  
-   <span data-ttu-id="e9b0d-106">bam_`ActivityName`_Active</span><span class="sxs-lookup"><span data-stu-id="e9b0d-106">bam_`ActivityName`_Active</span></span>  
  
-   <span data-ttu-id="e9b0d-107">bam_`ActivityName`_Completed</span><span class="sxs-lookup"><span data-stu-id="e9b0d-107">bam_`ActivityName`_Completed</span></span>  
  
-   <span data-ttu-id="e9b0d-108">bam_`ActivityName`_ActiveRelationships</span><span class="sxs-lookup"><span data-stu-id="e9b0d-108">bam_`ActivityName`_ActiveRelationships</span></span>  
  
-   <span data-ttu-id="e9b0d-109">bam_`ActivityName`_CompletedRelationships</span><span class="sxs-lookup"><span data-stu-id="e9b0d-109">bam_`ActivityName`_CompletedRelationships</span></span>  
  
-   <span data-ttu-id="e9b0d-110">bam_`ActivityName`_Continuations</span><span class="sxs-lookup"><span data-stu-id="e9b0d-110">bam_`ActivityName`_Continuations</span></span>  
  
 <span data-ttu-id="e9b0d-111">`ActivityName` は、ユーザーが定義したアクティビティの名前になります。</span><span class="sxs-lookup"><span data-stu-id="e9b0d-111">Where `ActivityName` is the name of the activity that the user has defined.</span></span>  
  
 <span data-ttu-id="e9b0d-112">通常の実行では、不完全なデータは bam_`ActivityName`_Active テーブルに残ります。</span><span class="sxs-lookup"><span data-stu-id="e9b0d-112">During normal execution, incomplete data remains in the bam_`ActivityName`_Active table.</span></span> <span data-ttu-id="e9b0d-113">データにリレーションシップおよび参照があるかどうかは、データがあります、bam で\_`ActivityName`_ActiveRelationships テーブルです。</span><span class="sxs-lookup"><span data-stu-id="e9b0d-113">If the data has relations and references, then there will be data in the bam\_`ActivityName`_ActiveRelationships table.</span></span>  
  
 <span data-ttu-id="e9b0d-114">Continuation を使用したアクティビティの追跡時には、アクティビティが不完全な状態で BAM データベースに残される場合があります。</span><span class="sxs-lookup"><span data-stu-id="e9b0d-114">During the tracking of activities that use continuations, there may be instances in which an activity is left in an incomplete state in the BAM databases.</span></span> <span data-ttu-id="e9b0d-115">このトピックの最後に示すストアド プロシージャ作成スクリプトを使用すると、不完全なレコードを削除するストアド プロシージャを作成できます。</span><span class="sxs-lookup"><span data-stu-id="e9b0d-115">You can use the stored procedure creation script at the end of this topic to create a stored procedure that will purge the incomplete records.</span></span>  
  
 <span data-ttu-id="e9b0d-116">ストアド プロシージャを作成するには、スクリプトをコピーしてから、SQL Server Management を使用して BAM プライマリ インポート データベースに対しスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="e9b0d-116">To create the stored procedure, copy the script and execute it against the BAM Primary Import database by using SQL Server Management.</span></span> <span data-ttu-id="e9b0d-117">このスクリプトはという名前のストアド プロシージャを生成 **RemoveDanglingInstances** データベースにします。</span><span class="sxs-lookup"><span data-stu-id="e9b0d-117">The script will generate a stored procedure named **RemoveDanglingInstances** in the database.</span></span>  
  
## <a name="create-the-removedanglinginstances-stored-procedure"></a><span data-ttu-id="e9b0d-118">RemoveDanglingInstances ストアド プロシージャを作成します。</span><span class="sxs-lookup"><span data-stu-id="e9b0d-118">Create the RemoveDanglingInstances stored procedure</span></span>  
  
1.  <span data-ttu-id="e9b0d-119">開いている**SQL Server Management Studio**、SQL server に接続します。</span><span class="sxs-lookup"><span data-stu-id="e9b0d-119">Open **SQL Server Management Studio**, and connect to the SQL server.</span></span>
  
2.  <span data-ttu-id="e9b0d-120">サーバー名を展開し、 **データベース**, 、BAM プライマリ インポート データベースを選択します。</span><span class="sxs-lookup"><span data-stu-id="e9b0d-120">Expand the server name, expand **Databases**, and then select the BAM Primary Import database.</span></span>  
  
3.  <span data-ttu-id="e9b0d-121">**[新しいクエリ]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e9b0d-121">Click **New Query**.</span></span>  
  
4.  <span data-ttu-id="e9b0d-122">ストアド プロシージャ作成スクリプトをコピーし、クエリ ペインに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="e9b0d-122">Copy the stored procedure creation script, and paste it into the query pane.</span></span>  
  
5.  <span data-ttu-id="e9b0d-123">**実行**スクリプト。</span><span class="sxs-lookup"><span data-stu-id="e9b0d-123">**Execute** the script.</span></span> <span data-ttu-id="e9b0d-124">作成されたストアド プロシージャは、dbo としてストアド プロシージャの一覧で表示できます。RemoveDanglingInstances します。</span><span class="sxs-lookup"><span data-stu-id="e9b0d-124">The resulting stored procedure can be viewed in the list of stored procedures as dbo.RemoveDanglingInstances.</span></span>  
  
## <a name="remove-incomplete-activity-instances"></a><span data-ttu-id="e9b0d-125">不完全なアクティビティ インスタンスを削除します。</span><span class="sxs-lookup"><span data-stu-id="e9b0d-125">Remove incomplete activity instances</span></span>  
  
1.  <span data-ttu-id="e9b0d-126">開いている**SQL Server Management Studio**、SQL server に接続します。</span><span class="sxs-lookup"><span data-stu-id="e9b0d-126">Open **SQL Server Management Studio**, and connect to the SQL server.</span></span>
  
2.  <span data-ttu-id="e9b0d-127">サーバー名を展開し、 **データベース**, 、BAM プライマリ インポート データベースを選択します。</span><span class="sxs-lookup"><span data-stu-id="e9b0d-127">Expand the server name, expand **Databases**, and then select the BAM Primary Import database.</span></span>  
  
3.  <span data-ttu-id="e9b0d-128">**[新しいクエリ]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e9b0d-128">Click **New Query**.</span></span>  
  
4.  <span data-ttu-id="e9b0d-129">クエリ ウィンドウで、次のように入力します。`exec RemoveDanglingInstances`および実行する削除操作に適切なパラメーターです。</span><span class="sxs-lookup"><span data-stu-id="e9b0d-129">In the query pane, type `exec RemoveDanglingInstances` and the appropriate parameters for the remove operation you are performing.</span></span> <span data-ttu-id="e9b0d-130">たとえば、注文書アクティビティの不完全なインスタンスをすべて削除するには、「`exec RemoveDanglingInstances @ActivityName = 'PurchaseOrder'`」と入力します。</span><span class="sxs-lookup"><span data-stu-id="e9b0d-130">For example, to remove all incomplete instances of the Purchase Order activity, type `exec RemoveDanglingInstances @ActivityName = 'PurchaseOrder'`.</span></span>  
  
5.  <span data-ttu-id="e9b0d-131">**実行**スクリプト。</span><span class="sxs-lookup"><span data-stu-id="e9b0d-131">**Execute** the script.</span></span>  
  
## <a name="removedanglinginstances-usage-examples"></a><span data-ttu-id="e9b0d-132">RemoveDanglingInstances の使用例</span><span class="sxs-lookup"><span data-stu-id="e9b0d-132">RemoveDanglingInstances Usage Examples</span></span>  
 <span data-ttu-id="e9b0d-133">ストアド プロシージャには、4 つのパラメーターが表示されることができます。</span><span class="sxs-lookup"><span data-stu-id="e9b0d-133">The stored procedure can receive four parameters:</span></span>  
  
|<span data-ttu-id="e9b0d-134">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e9b0d-134">Parameter</span></span>|<span data-ttu-id="e9b0d-135">Description</span><span class="sxs-lookup"><span data-stu-id="e9b0d-135">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e9b0d-136">@ActivityName nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="e9b0d-136">@ActivityName nvarchar(128)</span></span>|<span data-ttu-id="e9b0d-137">削除する不完全なアクティビティ インスタンスの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="e9b0d-137">Specifies the name of the incomplete activity instance to remove.</span></span>|  
|<span data-ttu-id="e9b0d-138">@ActivityId nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="e9b0d-138">@ActivityId nvarchar(128)</span></span>|<span data-ttu-id="e9b0d-139">(省略可能) 指定したインスタンス識別子を持つ未解決のインスタンスだけをストアド プロシージャで削除するように指定します。</span><span class="sxs-lookup"><span data-stu-id="e9b0d-139">(Optional) Specifies that the stored procedure remove only the dangling instance with the specified instance identifier.</span></span>|  
|<span data-ttu-id="e9b0d-140">@DateThreshold datetime</span><span class="sxs-lookup"><span data-stu-id="e9b0d-140">@DateThreshold datetime</span></span>|<span data-ttu-id="e9b0d-141">(省略可能)古いアクティブなテーブルでのアクティブなすべてのインスタンスを指定します (等しくないと古い、古いのみ)、指定された日付よりも削除されます。</span><span class="sxs-lookup"><span data-stu-id="e9b0d-141">(Optional) Specifies that all the active instances in the active table that are older (not equal to and older, only older) than the given date are removed.</span></span>|  
|<span data-ttu-id="e9b0d-142">@NewTableExtension nvarchar (30)</span><span class="sxs-lookup"><span data-stu-id="e9b0d-142">@NewTableExtension nvarchar(30)</span></span>|<span data-ttu-id="e9b0d-143">(省略可能) ストアド プロシージャで、指定された拡張子を既存のアクティビティ テーブルに連結して新しいテーブルを 3 つ作成するように指定します。</span><span class="sxs-lookup"><span data-stu-id="e9b0d-143">(Optional) Specifies that the stored procedure creates three new tables by concatenating the supplied extension to the existing activity tables.</span></span><br /><br /> <span data-ttu-id="e9b0d-144">結果のテーブルになります。</span><span class="sxs-lookup"><span data-stu-id="e9b0d-144">The resulting tables will be:</span></span><br /><br /> <span data-ttu-id="e9b0d-145">bam_ActivityName_Active_\<拡張機能\></span><span class="sxs-lookup"><span data-stu-id="e9b0d-145">bam_ActivityName_Active_\<Extension\></span></span><br /><br /> <span data-ttu-id="e9b0d-146">bam_ActivityName_ActiveRelationships_\<拡張機能\></span><span class="sxs-lookup"><span data-stu-id="e9b0d-146">bam_ActivityName_ActiveRelationships_\<Extension\></span></span><br /><br /> <span data-ttu-id="e9b0d-147">bam_ActivityName_Continuations_\<Extension\></span><span class="sxs-lookup"><span data-stu-id="e9b0d-147">bam_ActivityName_Continuations_\<Extension\></span></span><br /><br /> <span data-ttu-id="e9b0d-148">不完全なインスタンスは、データベースから削除される代わりに、これらの新しいテーブルに移動されます。</span><span class="sxs-lookup"><span data-stu-id="e9b0d-148">The incomplete instances are moved to the new tables rather than being purged from the database.</span></span><br /><br /> <span data-ttu-id="e9b0d-149">これらのテーブルが既に存在する場合は、再利用されます。存在しない場合は作成されます。</span><span class="sxs-lookup"><span data-stu-id="e9b0d-149">If the tables already exist, the stored procedure reuses them; otherwise they are created.</span></span> <span data-ttu-id="e9b0d-150">**重要:**  ストアド プロシージャ、テーブルが既に存在しない場合、そのスキーマが作成された場合に使用されるものと一致するいると想定しています。</span><span class="sxs-lookup"><span data-stu-id="e9b0d-150">**Important:**  If the tables already exist, the stored procedure assumes that their schemas match the ones that would be used if they were created.</span></span> <span data-ttu-id="e9b0d-151">スキーマが一致しない場合は、ストアド プロシージャはレコードを挿入できず、削除操作が失敗します。</span><span class="sxs-lookup"><span data-stu-id="e9b0d-151">If a schema does not match, the stored procedure will fail to insert the records and the remove operation will fail.</span></span>|  
  
 `exec RemoveDanglingInstances @ActivityName = 'PurchaseOrder'`  
  
 <span data-ttu-id="e9b0d-152">アクティブ テーブル、アクティブ リレーションシップ テーブル、および Continuation テーブルにある PurchaseOrder アクティビティのアクティブなインスタンスをすべて削除します。</span><span class="sxs-lookup"><span data-stu-id="e9b0d-152">Removes all active instances of the 'PurchaseOrder' activity in the active, active relationships, and continuations tables.</span></span>  
  
 `exec RemoveDanglingInstances @ActivityName = 'PurchaseOrder', @ActivityId = 'PO220567'`  
  
 <span data-ttu-id="e9b0d-153">PurchaseOrder アクティビティのアクティブ テーブル、アクティブ リレーションシップ テーブル、および Continuation テーブルから、アクティビティ ID が PO220567 であるアクティビティ インスタンスだけを削除します。</span><span class="sxs-lookup"><span data-stu-id="e9b0d-153">Removes only the activity instance that has an Activity ID of 'PO220567' from the active, active relationships, and continuations tables for the 'PurchaseOrder' activity.</span></span>  
  
 `exec RemoveDanglingInstances @ActivityName = 'PurchaseOrder', @DateThreshold='2005-02-02 19:27:03:533'`  
  
 <span data-ttu-id="e9b0d-154">PurchaseOrder アクティビティのアクティブ テーブル、アクティブ リレーションシップ テーブル、および Continuation テーブルから、LastModified の日時が 2005 年 2 月 2 日午後 7:27:03.533 よりも古いアクティビティ インスタンスをすべて削除します。</span><span class="sxs-lookup"><span data-stu-id="e9b0d-154">Removes all the activity instances that have a LastModified time that is older than Feb 2nd, 2005 7:27:03.533 PM from the active, active relationships, and continuations tables for the 'PurchaseOrder' activity.</span></span>  
  
 `exec RemoveDanglingInstances @ActivityName = 'PurchaseOrder', @ActivityId = 'PO220567', @DateThreshold='2005-02-02 19:27:03:533'`  
  
 <span data-ttu-id="e9b0d-155">LastModified 列が 2005 年 2 月 2 日午後 7:27:03.533 よりも古い場合にのみ、アクティビティ ID が PO220567 であるアクティビティ インスタンスを削除します。</span><span class="sxs-lookup"><span data-stu-id="e9b0d-155">Removes the activity instance whose activity ID is PO220567 only if its LastModified column is older than Feb 2nd, 2005 7:27:03.533 PM.</span></span>  
  
 `exec RemoveDanglingInstances @ActivityName = 'PurchaseOrder', @DateThreshold='2005-02-02 19:27:03:533', @NewTableExtension=N'Dangling'`  
  
 <span data-ttu-id="e9b0d-156">データベース内に次のテーブルを作成します。</span><span class="sxs-lookup"><span data-stu-id="e9b0d-156">Creates the following tables in the database:</span></span>  
  
 <span data-ttu-id="e9b0d-157">bam_PurchaseOrder_Active_Dangling</span><span class="sxs-lookup"><span data-stu-id="e9b0d-157">bam_PurchaseOrder_Active_Dangling</span></span>  
  
 <span data-ttu-id="e9b0d-158">bam_PurchaseOrder_ActiveRelationships_Dangling</span><span class="sxs-lookup"><span data-stu-id="e9b0d-158">bam_PurchaseOrder_ActiveRelationships_Dangling</span></span>  
  
 <span data-ttu-id="e9b0d-159">bam_PurchaseOrder_Continuations_Dangling</span><span class="sxs-lookup"><span data-stu-id="e9b0d-159">bam_PurchaseOrder_Continuations_Dangling</span></span>  
  
 <span data-ttu-id="e9b0d-160">ストアド プロシージャは、PurchaseOrder アクティビティのアクティブ テーブル、アクティブ リレーションシップ テーブル、および Continuation テーブルから、2005 年 2 月 2 日午後 7:27:03.533 よりも古い不完全なアクティビティ インスタンスをすべてコピーし、新しく作成されたテーブルに挿入します。</span><span class="sxs-lookup"><span data-stu-id="e9b0d-160">The stored procedure copies all incomplete activity instances that are older than Feb 2nd, 2005 7:27:03.533 PM from the active, active relationships, and continuations tables for the 'PurchaseOrder' activity, and inserts them into the newly created tables.</span></span> <span data-ttu-id="e9b0d-161">次に、コピー済みのアクティビティ インスタンスが、アクティブ テーブル、アクティブ リレーションシップ テーブル、および Continuation テーブルから削除されます。</span><span class="sxs-lookup"><span data-stu-id="e9b0d-161">The copied activity instances are then removed from the active, active relationships, and continuations tables.</span></span>  
  
## <a name="stored-procedure-creation-script"></a><span data-ttu-id="e9b0d-162">ストアド プロシージャ作成スクリプト</span><span class="sxs-lookup"><span data-stu-id="e9b0d-162">Stored Procedure Creation Script</span></span>  
  
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

## <a name="another-method-of-resolving-incomplete-instances"></a><span data-ttu-id="e9b0d-163">不完全なインスタンスを解決する別の方法</span><span class="sxs-lookup"><span data-stu-id="e9b0d-163">Another method of resolving incomplete instances</span></span>
<span data-ttu-id="e9b0d-164">BAMPrimaryImport データベースからの不完全なアクティビティ インスタンスは、SQL クエリを使用しても解決できます。</span><span class="sxs-lookup"><span data-stu-id="e9b0d-164">You can also resolve incomplete activity instances from the BAMPrimaryImport database by using a SQL query.</span></span> <span data-ttu-id="e9b0d-165">参照してください[不完全なアクティビティ インスタンスを解決するには](how-to-resolve-incomplete-activity-instances.md)します。</span><span class="sxs-lookup"><span data-stu-id="e9b0d-165">See [Resolve incomplete activity instances](how-to-resolve-incomplete-activity-instances.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e9b0d-166">参照</span><span class="sxs-lookup"><span data-stu-id="e9b0d-166">See Also</span></span>  
 [<span data-ttu-id="e9b0d-167">BAM データベースの管理</span><span class="sxs-lookup"><span data-stu-id="e9b0d-167">Managing BAM Databases</span></span>](../core/managing-bam-databases.md)
