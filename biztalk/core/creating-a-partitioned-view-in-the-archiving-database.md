---
title: アーカイブ データベースでパーティション ビューの作成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- databases, partitioning
- partitioning
- Archive database [BAM], partitioning
ms.assetid: f9ef7480-2e37-4477-92c8-b5686ae9b54b
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c4a1b688356ca665f98903099c1acef293a21e64
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65354097"
---
# <a name="creating-a-partitioned-view-in-the-archiving-database"></a><span data-ttu-id="5fac2-102">アーカイブ データベースでパーティション分割されたビューを作成します。</span><span class="sxs-lookup"><span data-stu-id="5fac2-102">Creating a Partitioned View in the Archiving Database</span></span>
<span data-ttu-id="5fac2-103">BAM データ保守パッケージを実行すると (bam_dm _`<activity name>`) BAM は、各パーティションを BAM プライマリ インポート データベースで BAM アーカイブ データベースに別のテーブルにコピーします。</span><span class="sxs-lookup"><span data-stu-id="5fac2-103">When you run the BAM data maintenance package (BAM_DM_`<activity name>`) BAM copies each partition in the BAM Primary Import database to a separate table in the BAM Archive database.</span></span> <span data-ttu-id="5fac2-104">アーカイブ データベースをデタッチし、クエリを実行するために再接続する場合、クエリのデータを見つけるが難しくなります。</span><span class="sxs-lookup"><span data-stu-id="5fac2-104">If you detach the archive database and reattach it for querying, it will be difficult to locate the data for your query.</span></span>  
  
 <span data-ttu-id="5fac2-105">BAM アーカイブ データベースをデータの検索を容易にするには、パーティション ビューを作成できます。</span><span class="sxs-lookup"><span data-stu-id="5fac2-105">You can create partitioned views in the BAM Archive database to facilitate locating the data.</span></span> <span data-ttu-id="5fac2-106">BAM では、最大 253 のパーティションをサポートします。</span><span class="sxs-lookup"><span data-stu-id="5fac2-106">BAM supports up to 253 partitions.</span></span> <span data-ttu-id="5fac2-107">各アクティビティの場合は、BAM には、1 つ BAM データ保守 DTS パッケージ、BAM アーカイブ データベースにアクティビティ データをコピーし、BAM プライマリ インポート データベースから削除されますが生成されます。</span><span class="sxs-lookup"><span data-stu-id="5fac2-107">For each activity, BAM generates one BAM data maintenance DTS package, which copies the activity data to the BAM Archive database and then removes it from the BAM Primary Import database.</span></span> <span data-ttu-id="5fac2-108">データをコピーした後、アーカイブ データベースが失敗した場合は、次のバックアップの前に、データは失われます。</span><span class="sxs-lookup"><span data-stu-id="5fac2-108">If the archive database fails after the data is copied but before the next backup, data is lost.</span></span>  
  
 <span data-ttu-id="5fac2-109">データの損失を防ぐために解決策は 1 つのアーカイブ パッケージを最初に、すべての活動から古いデータをコピーし、BAM アーカイブ データベースをバックアップし、最後に、BAM プライマリ インポート データベースからコピーされたパーティションを削除します。</span><span class="sxs-lookup"><span data-stu-id="5fac2-109">The solution to prevent lost data is to have a single archiving package, which first copies the old data from all activities, then backs up the BAM Archive database, and finally drops the partitions that were copied from the BAM Primary Import database.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="5fac2-110">前提条件</span><span class="sxs-lookup"><span data-stu-id="5fac2-110">Prerequisites</span></span>  
 <span data-ttu-id="5fac2-111">この手順を実行する BizTalk Server 管理者グループのメンバーとしてログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5fac2-111">You must be logged on as a member of the BizTalk Server Administrators group to perform this procedure.</span></span>  
  
### <a name="to-create-a-partitioned-view-in-the-bam-archive-database-in-sql-server-2008-sp1-or-sql-server-2008-r2"></a><span data-ttu-id="5fac2-112">SQL Server 2008 SP1 または SQL Server 2008 R2 で BAM アーカイブ データベースでパーティション ビューを作成するには</span><span class="sxs-lookup"><span data-stu-id="5fac2-112">To create a partitioned view in the BAM Archive database in SQL Server 2008 SP1 or SQL Server 2008 R2</span></span>  
  
1.  <span data-ttu-id="5fac2-113">SQL Server Management Studio を開きます。</span><span class="sxs-lookup"><span data-stu-id="5fac2-113">Open SQL Server Management Studio.</span></span>  
  
2.  <span data-ttu-id="5fac2-114">BAM アーカイブ データベースを選択し、クリックして**新しいクエリ**します。</span><span class="sxs-lookup"><span data-stu-id="5fac2-114">Select the BAM Archive database, and then click **New Query**.</span></span>  
  
3.  <span data-ttu-id="5fac2-115">**クエリ**メニューで、**結果を** をクリックし、**結果をテキスト**します。</span><span class="sxs-lookup"><span data-stu-id="5fac2-115">On the **Query** menu, point to **Results To** and then click **Results to Text**.</span></span>  
  
4.  <span data-ttu-id="5fac2-116">クエリ ペインには、次の SQL スクリプトをコピーします。</span><span class="sxs-lookup"><span data-stu-id="5fac2-116">Copy the following SQL script into the query pane.</span></span> <span data-ttu-id="5fac2-117">置換\<アクティビティ名\>アクティビティ名、および置換と`<view type>`いずれかで**インスタンス**インスタンス ビューの場合または**リレーションシップ**リレーションシップ ビューの場合。</span><span class="sxs-lookup"><span data-stu-id="5fac2-117">Replace \<activity name\> with your activity name, and replace `<view type>` with either **Instances** for instance view or **Relationships** for relationship view.</span></span>  
  
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
  
5.  <span data-ttu-id="5fac2-118">クエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="5fac2-118">Execute the query.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5fac2-119">参照</span><span class="sxs-lookup"><span data-stu-id="5fac2-119">See Also</span></span>  
 <span data-ttu-id="5fac2-120">[BAM DTS パッケージ](../core/bam-dts-packages.md) </span><span class="sxs-lookup"><span data-stu-id="5fac2-120">[BAM DTS Packages](../core/bam-dts-packages.md) </span></span>  
 [<span data-ttu-id="5fac2-121">BAM 分析および Tracking Analysis Server データベースをバックアップする方法</span><span class="sxs-lookup"><span data-stu-id="5fac2-121">How to Back Up the BAM Analysis and Tracking Analysis Server Databases</span></span>](../core/how-to-back-up-the-bam-analysis-and-tracking-analysis-server-databases.md)