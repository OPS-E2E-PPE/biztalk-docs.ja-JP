---
title: "アーカイブ データベースでパーティション ビューの作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- databases, partitioning
- partitioning
- Archive database [BAM], partitioning
ms.assetid: f9ef7480-2e37-4477-92c8-b5686ae9b54b
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 42adf8f614f124c9b17597a44cdaaba9d7ed4f93
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="creating-a-partitioned-view-in-the-archiving-database"></a><span data-ttu-id="9d59d-102">アーカイブ データベースでのパーティション ビューの作成</span><span class="sxs-lookup"><span data-stu-id="9d59d-102">Creating a Partitioned View in the Archiving Database</span></span>
<span data-ttu-id="9d59d-103">BAM データ保守パッケージ (BAM_DM_`<activity name>`) を実行すると、BAM プライマリ インポート データベースの各パーティションが BAM アーカイブ データベースの個別のテーブルにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="9d59d-103">When you run the BAM data maintenance package (BAM_DM_`<activity name>`) BAM copies each partition in the BAM Primary Import database to a separate table in the BAM Archive database.</span></span> <span data-ttu-id="9d59d-104">アーカイブ データベースを接続解除した後、クエリを実行するために再接続する場合、クエリでデータを検索するのが困難になります。</span><span class="sxs-lookup"><span data-stu-id="9d59d-104">If you detach the archive database and reattach it for querying, it will be difficult to locate the data for your query.</span></span>  
  
 <span data-ttu-id="9d59d-105">データの検索を容易にするために、BAM アーカイブ データベースでパーティション ビューを作成できます。</span><span class="sxs-lookup"><span data-stu-id="9d59d-105">You can create partitioned views in the BAM Archive database to facilitate locating the data.</span></span> <span data-ttu-id="9d59d-106">BAM では最大 253 のパーティションをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="9d59d-106">BAM supports up to 253 partitions.</span></span> <span data-ttu-id="9d59d-107">BAM によってアクティビティごとに 1 つの BAM データ保守 DTS パッケージが生成され、アクティビティ データが BAM アーカイブ データベースにコピーされ、BAM プライマリ インポート データベースから削除されます。</span><span class="sxs-lookup"><span data-stu-id="9d59d-107">For each activity, BAM generates one BAM data maintenance DTS package, which copies the activity data to the BAM Archive database and then removes it from the BAM Primary Import database.</span></span> <span data-ttu-id="9d59d-108">データをコピーした後、次のバックアップの前にアーカイブ データベースに障害が発生すると、データは失われます。</span><span class="sxs-lookup"><span data-stu-id="9d59d-108">If the archive database fails after the data is copied but before the next backup, data is lost.</span></span>  
  
 <span data-ttu-id="9d59d-109">データ損失を防ぐための対策として、アーカイブ パッケージを 1 つ作成し、最初にすべてのアクティビティの古いデータをコピーします。その後、BAM アーカイブ データベースをバックアップして、最後に BAM プライマリ インポート データベースからコピーしたパーティションを削除します。</span><span class="sxs-lookup"><span data-stu-id="9d59d-109">The solution to prevent lost data is to have a single archiving package, which first copies the old data from all activities, then backs up the BAM Archive database, and finally drops the partitions that were copied from the BAM Primary Import database.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="9d59d-110">前提条件</span><span class="sxs-lookup"><span data-stu-id="9d59d-110">Prerequisites</span></span>  
 <span data-ttu-id="9d59d-111">ここで示す手順を実行するには、BizTalk Server Administrators グループのメンバーとしてログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9d59d-111">You must be logged on as a member of the BizTalk Server Administrators group to perform this procedure.</span></span>  
  
### <a name="to-create-a-partitioned-view-in-the-bam-archive-database-in-sql-server-2008-sp1-or-sql-server-2008-r2"></a><span data-ttu-id="9d59d-112">SQL Server 2008 SP1 または SQL Server 2008 R2 で BAM アーカイブ データベースにパーティションを区切ったビューを作成するには</span><span class="sxs-lookup"><span data-stu-id="9d59d-112">To create a partitioned view in the BAM Archive database in SQL Server 2008 SP1 or SQL Server 2008 R2</span></span>  
  
1.  <span data-ttu-id="9d59d-113">SQL Server Management Studio を開きます。</span><span class="sxs-lookup"><span data-stu-id="9d59d-113">Open SQL Server Management Studio.</span></span>  
  
2.  <span data-ttu-id="9d59d-114">BAM アーカイブ データベースを選択し、クリックして**新しいクエリ**です。</span><span class="sxs-lookup"><span data-stu-id="9d59d-114">Select the BAM Archive database, and then click **New Query**.</span></span>  
  
3.  <span data-ttu-id="9d59d-115">**クエリ** メニューのをポイント**結果に** をクリックし、**結果をテキスト**です。</span><span class="sxs-lookup"><span data-stu-id="9d59d-115">On the **Query** menu, point to **Results To** and then click **Results to Text**.</span></span>  
  
4.  <span data-ttu-id="9d59d-116">次の SQL スクリプトをクエリ ウィンドウにコピーします。</span><span class="sxs-lookup"><span data-stu-id="9d59d-116">Copy the following SQL script into the query pane.</span></span> <span data-ttu-id="9d59d-117">置き換える\<アクティビティ名\>アクティビティ名、および置換`<view type>`いずれかで**インスタンス**のインスタンスを表示または**リレーションシップ**リレーションシップ ビューの場合。</span><span class="sxs-lookup"><span data-stu-id="9d59d-117">Replace \<activity name\> with your activity name, and replace `<view type>` with either **Instances** for instance view or **Relationships** for relationship view.</span></span>  
  
    ```  
    set nocount on  
  
    declare @activityName as nvarchar(128)  
    declare @viewType as nvarchar(50)  
    set @activityName = N'<activity name>'-- Substitute your activity name here  
    set @viewType = N'<view type>'-- Substitute the view type here, either "Instances" or "Relationships"  
  
    declare @tableName nvarchar(128)  
    declare @viewName nvarchar(128)  
    declare @isFirstTable bit  
    declare @scriptLine nvarchar(300)  
  
    set @viewName = N'bam_' + @activityName + '_' + @viewType + 'View'  
    select N'SELECT Name FROM sysobjects where name = N''' + @viewName + ''' and type = ''V'''   
     + char(13) + char(10) + 'IF @@ROWCOUNT > 0 DROP VIEW ' + @viewName   
     + char(13) + char(10) + 'GO'  
  
    select 'CREATE VIEW ' +  @viewName + ' AS ' + char(13) + char(10)  
  
    declare instance_cursor cursor local for  
    select name from sysobjects   
    where name like N'bam_' + @activityName + '_' + @viewType + '_%' and type = 'U'  
  
    SET @isFirstTable = 1  
    OPEN instance_cursor  
    FETCH NEXT FROM instance_cursor INTO @tableName  
  
    WHILE @@fetch_status = 0   
    BEGIN  
  
    if @isFirstTable = 1  
    BEGIN  
    SET @scriptLine = N'SELECT * FROM [' + @tableName + ']'  
    SET @isFirstTable = 0  
    END  
    ELSE  
    SET @scriptLine = N'UNION ALL SELECT * FROM [' + @tableName + ']'  
  
    SELECT @scriptLine  
  
    FETCH NEXT FROM instance_cursor INTO @tableName  
    END  
    CLOSE instance_cursor  
    DEALLOCATE instance_cursor  
  
    select 'GO'  
    set nocount off  
    ```  
  
5.  <span data-ttu-id="9d59d-118">クエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="9d59d-118">Execute the query.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d59d-119">参照</span><span class="sxs-lookup"><span data-stu-id="9d59d-119">See Also</span></span>  
 <span data-ttu-id="9d59d-120">[BAM DTS パッケージ](../core/bam-dts-packages.md) </span><span class="sxs-lookup"><span data-stu-id="9d59d-120">[BAM DTS Packages](../core/bam-dts-packages.md) </span></span>  
 [<span data-ttu-id="9d59d-121">バックアップ方法、BAM 分析および Tracking Analysis Server データベース</span><span class="sxs-lookup"><span data-stu-id="9d59d-121">How to Back Up the BAM Analysis and Tracking Analysis Server Databases</span></span>](../core/how-to-back-up-the-bam-analysis-and-tracking-analysis-server-databases.md)