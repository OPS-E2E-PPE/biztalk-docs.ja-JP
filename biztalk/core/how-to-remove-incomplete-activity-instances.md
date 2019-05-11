---
title: 不完全なアクティビティ インスタンスの削除 |Microsoft Docs
description: BizTalk Server で BAM プライマリ インポート データベースから不完全なインスタンスを削除するカスタムの RemoveDanglingInstances SQL スクリプトを実行します。
ms.custom: ''
ms.date: 01/18/2018
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7060578c-6267-487b-8530-efa18f9431ce
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bebb8d3899c34dcde7a5d5c3059434d23202929a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65334975"
---
# <a name="remove-incomplete-activity-instances"></a><span data-ttu-id="9bf13-103">不完全なアクティビティ インスタンスを削除します。</span><span class="sxs-lookup"><span data-stu-id="9bf13-103">Remove Incomplete Activity Instances</span></span>
<span data-ttu-id="9bf13-104">BAM 定義ファイルを展開するときは、5 つのテーブルが、定義ファイルで定義されている各アクティビティを BAM プライマリ インポート データベースに作成されます。</span><span class="sxs-lookup"><span data-stu-id="9bf13-104">When a BAM definition file is deployed, five tables are created in the BAM Primary Import database for each activity defined in the definition file.</span></span> <span data-ttu-id="9bf13-105">これらのテーブルは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="9bf13-105">These tables are:</span></span>  
  
- <span data-ttu-id="9bf13-106">bam _`ActivityName`(_a)</span><span class="sxs-lookup"><span data-stu-id="9bf13-106">bam_`ActivityName`_Active</span></span>  
  
- <span data-ttu-id="9bf13-107">bam _`ActivityName`_Completed</span><span class="sxs-lookup"><span data-stu-id="9bf13-107">bam_`ActivityName`_Completed</span></span>  
  
- <span data-ttu-id="9bf13-108">bam _`ActivityName`_ActiveRelationships</span><span class="sxs-lookup"><span data-stu-id="9bf13-108">bam_`ActivityName`_ActiveRelationships</span></span>  
  
- <span data-ttu-id="9bf13-109">bam _`ActivityName`_CompletedRelationships</span><span class="sxs-lookup"><span data-stu-id="9bf13-109">bam_`ActivityName`_CompletedRelationships</span></span>  
  
- <span data-ttu-id="9bf13-110">bam _`ActivityName`_Continuations</span><span class="sxs-lookup"><span data-stu-id="9bf13-110">bam_`ActivityName`_Continuations</span></span>  
  
  <span data-ttu-id="9bf13-111">場所`ActivityName`ユーザーが定義したアクティビティの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="9bf13-111">Where `ActivityName` is the name of the activity that the user has defined.</span></span>  
  
  <span data-ttu-id="9bf13-112">不完全なデータが、bam _ には、通常の実行中に`ActivityName`*アクティブ テーブル。データにリレーションシップおよび参照がある場合はデータには、bam\\*`ActivityName`_ActiveRelationships テーブル。</span><span class="sxs-lookup"><span data-stu-id="9bf13-112">During normal execution, incomplete data remains in the bam_`ActivityName`*Active table. If the data has relations and references, then there will be data in the bam\\*`ActivityName`_ActiveRelationships table.</span></span>  
  
  <span data-ttu-id="9bf13-113">継続を使用してアクティビティの追跡、中には、BAM データベースの状態が未完了の活動は左側のインスタンスが可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9bf13-113">During the tracking of activities that use continuations, there may be instances in which an activity is left in an incomplete state in the BAM databases.</span></span> <span data-ttu-id="9bf13-114">このトピックの最後に、ストアド プロシージャ作成スクリプトを使用するには、不完全なレコードを削除するストアド プロシージャを作成します。</span><span class="sxs-lookup"><span data-stu-id="9bf13-114">You can use the stored procedure creation script at the end of this topic to create a stored procedure that will purge the incomplete records.</span></span>  
  
  <span data-ttu-id="9bf13-115">ストアド プロシージャを作成するには、スクリプトをコピーし、SQL Server の管理を使用して BAM プライマリ インポート データベースに対して実行します。</span><span class="sxs-lookup"><span data-stu-id="9bf13-115">To create the stored procedure, copy the script and execute it against the BAM Primary Import database by using SQL Server Management.</span></span> <span data-ttu-id="9bf13-116">スクリプトでは、という名前のストアド プロシージャを生成します。 **RemoveDanglingInstances**データベースにします。</span><span class="sxs-lookup"><span data-stu-id="9bf13-116">The script will generate a stored procedure named **RemoveDanglingInstances** in the database.</span></span>  
  
## <a name="create-the-removedanglinginstances-stored-procedure"></a><span data-ttu-id="9bf13-117">RemoveDanglingInstances ストアド プロシージャを作成します。</span><span class="sxs-lookup"><span data-stu-id="9bf13-117">Create the RemoveDanglingInstances stored procedure</span></span>  
  
1.  <span data-ttu-id="9bf13-118">開いている**SQL Server Management Studio**、SQL server に接続します。</span><span class="sxs-lookup"><span data-stu-id="9bf13-118">Open **SQL Server Management Studio**, and connect to the SQL server.</span></span>
  
2.  <span data-ttu-id="9bf13-119">サーバー名を展開し、**データベース**、BAM プライマリ インポート データベースを選択します。</span><span class="sxs-lookup"><span data-stu-id="9bf13-119">Expand the server name, expand **Databases**, and then select the BAM Primary Import database.</span></span>  
  
3.  <span data-ttu-id="9bf13-120">**[新しいクエリ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9bf13-120">Click **New Query**.</span></span>  
  
4.  <span data-ttu-id="9bf13-121">ストアド プロシージャ作成スクリプトをコピーし、クエリ ペインに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="9bf13-121">Copy the stored procedure creation script, and paste it into the query pane.</span></span>  
  
5.  <span data-ttu-id="9bf13-122">**実行**スクリプト。</span><span class="sxs-lookup"><span data-stu-id="9bf13-122">**Execute** the script.</span></span> <span data-ttu-id="9bf13-123">作成されたストアド プロシージャは、dbo としてストアド プロシージャの一覧で表示できます。RemoveDanglingInstances します。</span><span class="sxs-lookup"><span data-stu-id="9bf13-123">The resulting stored procedure can be viewed in the list of stored procedures as dbo.RemoveDanglingInstances.</span></span>  
  
## <a name="remove-incomplete-activity-instances"></a><span data-ttu-id="9bf13-124">不完全なアクティビティ インスタンスを削除します。</span><span class="sxs-lookup"><span data-stu-id="9bf13-124">Remove incomplete activity instances</span></span>  
  
1.  <span data-ttu-id="9bf13-125">開いている**SQL Server Management Studio**、SQL server に接続します。</span><span class="sxs-lookup"><span data-stu-id="9bf13-125">Open **SQL Server Management Studio**, and connect to the SQL server.</span></span>
  
2.  <span data-ttu-id="9bf13-126">サーバー名を展開し、**データベース**、BAM プライマリ インポート データベースを選択します。</span><span class="sxs-lookup"><span data-stu-id="9bf13-126">Expand the server name, expand **Databases**, and then select the BAM Primary Import database.</span></span>  
  
3.  <span data-ttu-id="9bf13-127">**[新しいクエリ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9bf13-127">Click **New Query**.</span></span>  
  
4.  <span data-ttu-id="9bf13-128">クエリ ウィンドウで次のように入力します。`exec RemoveDanglingInstances`と削除の操作を実行するための適切なパラメーター。</span><span class="sxs-lookup"><span data-stu-id="9bf13-128">In the query pane, type `exec RemoveDanglingInstances` and the appropriate parameters for the remove operation you are performing.</span></span> <span data-ttu-id="9bf13-129">たとえば、発注アクティビティのすべての不完全なインスタンスを削除する次のように入力します。`exec RemoveDanglingInstances @ActivityName = 'PurchaseOrder'`します。</span><span class="sxs-lookup"><span data-stu-id="9bf13-129">For example, to remove all incomplete instances of the Purchase Order activity, type `exec RemoveDanglingInstances @ActivityName = 'PurchaseOrder'`.</span></span>  
  
5.  <span data-ttu-id="9bf13-130">**実行**スクリプト。</span><span class="sxs-lookup"><span data-stu-id="9bf13-130">**Execute** the script.</span></span>  
  
## <a name="removedanglinginstances-usage-examples"></a><span data-ttu-id="9bf13-131">RemoveDanglingInstances の使用例</span><span class="sxs-lookup"><span data-stu-id="9bf13-131">RemoveDanglingInstances Usage Examples</span></span>  
 <span data-ttu-id="9bf13-132">ストアド プロシージャには、4 つのパラメーターが表示されることができます。</span><span class="sxs-lookup"><span data-stu-id="9bf13-132">The stored procedure can receive four parameters:</span></span>  
  
|<span data-ttu-id="9bf13-133">パラメーター</span><span class="sxs-lookup"><span data-stu-id="9bf13-133">Parameter</span></span>|<span data-ttu-id="9bf13-134">説明</span><span class="sxs-lookup"><span data-stu-id="9bf13-134">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9bf13-135">@ActivityName nvarchar(128)</span><span class="sxs-lookup"><span data-stu-id="9bf13-135">@ActivityName nvarchar(128)</span></span>|<span data-ttu-id="9bf13-136">削除する不完全なアクティビティ インスタンスの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="9bf13-136">Specifies the name of the incomplete activity instance to remove.</span></span>|  
|<span data-ttu-id="9bf13-137">@ActivityId nvarchar(128)</span><span class="sxs-lookup"><span data-stu-id="9bf13-137">@ActivityId nvarchar(128)</span></span>|<span data-ttu-id="9bf13-138">(省略可能)ストアド プロシージャが指定されたインスタンス識別子を持つ未解決のインスタンスのみを削除することを指定します。</span><span class="sxs-lookup"><span data-stu-id="9bf13-138">(Optional) Specifies that the stored procedure remove only the dangling instance with the specified instance identifier.</span></span>|  
|<span data-ttu-id="9bf13-139">@DateThreshold datetime</span><span class="sxs-lookup"><span data-stu-id="9bf13-139">@DateThreshold datetime</span></span>|<span data-ttu-id="9bf13-140">(省略可能)古いアクティブなテーブルですべてのアクティブなインスタンスのことを指定します (等しくないと古い、古いのみ)、指定された日付よりも削除されます。</span><span class="sxs-lookup"><span data-stu-id="9bf13-140">(Optional) Specifies that all the active instances in the active table that are older (not equal to and older, only older) than the given date are removed.</span></span>|  
|<span data-ttu-id="9bf13-141">@NewTableExtension nvarchar(30)</span><span class="sxs-lookup"><span data-stu-id="9bf13-141">@NewTableExtension nvarchar(30)</span></span>|<span data-ttu-id="9bf13-142">(省略可能)ストアド プロシージャが既存のアクティビティ テーブルに、指定された拡張子を連結して 3 つの新しいテーブルを作成することを指定します。</span><span class="sxs-lookup"><span data-stu-id="9bf13-142">(Optional) Specifies that the stored procedure creates three new tables by concatenating the supplied extension to the existing activity tables.</span></span><br /><br /> <span data-ttu-id="9bf13-143">結果のテーブルになります。</span><span class="sxs-lookup"><span data-stu-id="9bf13-143">The resulting tables will be:</span></span><br /><br /> <span data-ttu-id="9bf13-144">bam_ActivityName_Active_\<拡張機能\></span><span class="sxs-lookup"><span data-stu-id="9bf13-144">bam_ActivityName_Active_\<Extension\></span></span><br /><br /> <span data-ttu-id="9bf13-145">bam_ActivityName_ActiveRelationships_\<拡張機能\></span><span class="sxs-lookup"><span data-stu-id="9bf13-145">bam_ActivityName_ActiveRelationships_\<Extension\></span></span><br /><br /> <span data-ttu-id="9bf13-146">bam_ActivityName_Continuations_\<拡張機能\></span><span class="sxs-lookup"><span data-stu-id="9bf13-146">bam_ActivityName_Continuations_\<Extension\></span></span><br /><br /> <span data-ttu-id="9bf13-147">不完全なインスタンスは、データベースから削除されるのではなく、新しいテーブルに移動されます。</span><span class="sxs-lookup"><span data-stu-id="9bf13-147">The incomplete instances are moved to the new tables rather than being purged from the database.</span></span><br /><br /> <span data-ttu-id="9bf13-148">ストアド プロシージャを再利用には、テーブルが既に存在する場合それ以外の場合に作成されます。</span><span class="sxs-lookup"><span data-stu-id="9bf13-148">If the tables already exist, the stored procedure reuses them; otherwise they are created.</span></span> <span data-ttu-id="9bf13-149">**重要:** テーブルが既に存在する場合、ストアド プロシージャでは、そのスキーマが作成された場合に使用されるものと一致する前提としています。</span><span class="sxs-lookup"><span data-stu-id="9bf13-149">**Important:**  If the tables already exist, the stored procedure assumes that their schemas match the ones that would be used if they were created.</span></span> <span data-ttu-id="9bf13-150">スキーマが一致しない場合、レコードを挿入するストアド プロシージャは失敗し、削除操作は失敗します。</span><span class="sxs-lookup"><span data-stu-id="9bf13-150">If a schema does not match, the stored procedure will fail to insert the records and the remove operation will fail.</span></span>|  
  
 `exec RemoveDanglingInstances @ActivityName = 'PurchaseOrder'`  
  
 <span data-ttu-id="9bf13-151">アクティブなので PurchaseOrder アクティビティのすべてのアクティブなインスタンスを削除します。 アクティブなリレーションシップ、および continuation テーブル。</span><span class="sxs-lookup"><span data-stu-id="9bf13-151">Removes all active instances of the 'PurchaseOrder' activity in the active, active relationships, and continuations tables.</span></span>  
  
 `exec RemoveDanglingInstances @ActivityName = 'PurchaseOrder', @ActivityId = 'PO220567'`  
  
 <span data-ttu-id="9bf13-152">アクティブでは、アクティビティ ID が PO220567 のあるアクティビティ インスタンスのみを削除します。 アクティブなリレーションシップ、および continuation テーブル PurchaseOrder アクティビティ。</span><span class="sxs-lookup"><span data-stu-id="9bf13-152">Removes only the activity instance that has an Activity ID of 'PO220567' from the active, active relationships, and continuations tables for the 'PurchaseOrder' activity.</span></span>  
  
 `exec RemoveDanglingInstances @ActivityName = 'PurchaseOrder', @DateThreshold='2005-02-02 19:27:03:533'`  
  
 <span data-ttu-id="9bf13-153">2005 年 2 月 2日よりも古い LastModified 時刻があるすべてのアクティビティ インスタンスを削除します。 アクティブ、から日午後 7:27:03.533 アクティブなリレーションシップ、および continuation テーブル PurchaseOrder アクティビティ。</span><span class="sxs-lookup"><span data-stu-id="9bf13-153">Removes all the activity instances that have a LastModified time that is older than Feb 2nd, 2005 7:27:03.533 PM from the active, active relationships, and continuations tables for the 'PurchaseOrder' activity.</span></span>  
  
 `exec RemoveDanglingInstances @ActivityName = 'PurchaseOrder', @ActivityId = 'PO220567', @DateThreshold='2005-02-02 19:27:03:533'`  
  
 <span data-ttu-id="9bf13-154">LastModified 列が 2005 年 2 月 2日よりも古い場合にのみ、アクティビティ ID が po220567 であるアクティビティ インスタンスの削除日午後 7:27:03.533 します。</span><span class="sxs-lookup"><span data-stu-id="9bf13-154">Removes the activity instance whose activity ID is PO220567 only if its LastModified column is older than Feb 2nd, 2005 7:27:03.533 PM.</span></span>  
  
 `exec RemoveDanglingInstances @ActivityName = 'PurchaseOrder', @DateThreshold='2005-02-02 19:27:03:533', @NewTableExtension=N'Dangling'`  
  
 <span data-ttu-id="9bf13-155">データベースには、次の表を作成します。</span><span class="sxs-lookup"><span data-stu-id="9bf13-155">Creates the following tables in the database:</span></span>  
  
 <span data-ttu-id="9bf13-156">bam_PurchaseOrder_Active_Dangling</span><span class="sxs-lookup"><span data-stu-id="9bf13-156">bam_PurchaseOrder_Active_Dangling</span></span>  
  
 <span data-ttu-id="9bf13-157">bam_PurchaseOrder_ActiveRelationships_Dangling</span><span class="sxs-lookup"><span data-stu-id="9bf13-157">bam_PurchaseOrder_ActiveRelationships_Dangling</span></span>  
  
 <span data-ttu-id="9bf13-158">bam_PurchaseOrder_Continuations_Dangling</span><span class="sxs-lookup"><span data-stu-id="9bf13-158">bam_PurchaseOrder_Continuations_Dangling</span></span>  
  
 <span data-ttu-id="9bf13-159">ストアド プロシージャは、2005 年 2 月 2日よりも古いすべての不完全なアクティビティ インスタンスのコピーから、使用中のアクティブなリレーションシップでは、日午後 7:27:03.533 および継続タスク、PurchaseOrder アクティビティのテーブルし、新しく作成されたテーブルに挿入します。</span><span class="sxs-lookup"><span data-stu-id="9bf13-159">The stored procedure copies all incomplete activity instances that are older than Feb 2nd, 2005 7:27:03.533 PM from the active, active relationships, and continuations tables for the 'PurchaseOrder' activity, and inserts them into the newly created tables.</span></span> <span data-ttu-id="9bf13-160">コピー アクティビティのインスタンス、アクティブなから削除されるアクティブなリレーションシップ、および continuation テーブル。</span><span class="sxs-lookup"><span data-stu-id="9bf13-160">The copied activity instances are then removed from the active, active relationships, and continuations tables.</span></span>  
  
## <a name="stored-procedure-creation-script"></a><span data-ttu-id="9bf13-161">ストアド プロシージャ作成スクリプト</span><span class="sxs-lookup"><span data-stu-id="9bf13-161">Stored Procedure Creation Script</span></span>  
  
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

## <a name="another-method-of-resolving-incomplete-instances"></a><span data-ttu-id="9bf13-162">不完全なインスタンスを解決する別の方法</span><span class="sxs-lookup"><span data-stu-id="9bf13-162">Another method of resolving incomplete instances</span></span>
<span data-ttu-id="9bf13-163">BAMPrimaryImport データベースからの不完全なアクティビティ インスタンスは、SQL クエリを使用しても解決できます。</span><span class="sxs-lookup"><span data-stu-id="9bf13-163">You can also resolve incomplete activity instances from the BAMPrimaryImport database by using a SQL query.</span></span> <span data-ttu-id="9bf13-164">参照してください[不完全なアクティビティ インスタンスを解決する](how-to-resolve-incomplete-activity-instances.md)します。</span><span class="sxs-lookup"><span data-stu-id="9bf13-164">See [Resolve incomplete activity instances](how-to-resolve-incomplete-activity-instances.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="9bf13-165">参照</span><span class="sxs-lookup"><span data-stu-id="9bf13-165">See Also</span></span>  
 [<span data-ttu-id="9bf13-166">BAM データベースの管理</span><span class="sxs-lookup"><span data-stu-id="9bf13-166">Managing BAM Databases</span></span>](../core/managing-bam-databases.md)
