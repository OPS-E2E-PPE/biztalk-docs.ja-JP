---
title: ログ配布用に送信先システムを構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 2015-12-03
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- backing up, log shipping
- system failures, preventing
- log shipping
- databases, backing up
- backing up, databases
- system failures, backing up
- backing up, system failures
ms.assetid: 7b4425f5-b105-4fb2-a503-94ca1e75ad55
caps.latest.revision: 54
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 58951da7a59b041ef97b2b93e5153cc27d517b0e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65340860"
---
# <a name="how-to-configure-the-destination-system-for-log-shipping"></a><span data-ttu-id="d00cc-102">ログ配布用に送信先システムを構成する方法</span><span class="sxs-lookup"><span data-stu-id="d00cc-102">How to Configure the Destination System for Log Shipping</span></span>
<span data-ttu-id="d00cc-103">ログ配布は、システム障害が発生した場合、ダウンタイムを短縮するスタンバイ サーバーの機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="d00cc-103">Log shipping provides standby server capabilities to reduce downtime in the event of a system failure.</span></span> <span data-ttu-id="d00cc-104">ログ配布を使用すると、ソース システムから送信先システムにトランザクション ログを自動的に送信できます。</span><span class="sxs-lookup"><span data-stu-id="d00cc-104">Log shipping allows you to automatically send transaction logs from the source system to the destination system.</span></span> <span data-ttu-id="d00cc-105">送信先システムでトランザクション ログの復元、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース; ソース データベースと密接に同期を維持することです。</span><span class="sxs-lookup"><span data-stu-id="d00cc-105">At the destination system, the transaction logs are restored to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases; keeping them closely synchronized with the source databases.</span></span>  
  
 <span data-ttu-id="d00cc-106">ログ配布は、1 台のサーバーと分散型サーバー環境の両方で機能します。</span><span class="sxs-lookup"><span data-stu-id="d00cc-106">Log shipping works in both single server and distributed server environments.</span></span> <span data-ttu-id="d00cc-107">サーバーまたはライブ データが含まれているサーバーのグループは、ソース (またはプライマリ) と呼ばれるはシステム。</span><span class="sxs-lookup"><span data-stu-id="d00cc-107">The server or group of servers that contain live data is known as the source (or primary) system.</span></span> <span data-ttu-id="d00cc-108">サーバーまたはデータベースのバックアップ ソースで生成されたファイル (またはプライマリ) システムの復元に使用されるサーバーのグループが先 (またはセカンダリ) と呼ばれるシステム。</span><span class="sxs-lookup"><span data-stu-id="d00cc-108">The server or group of servers that are used to restore the database backups produced by the source (or primary) system is known as the destination (or secondary) system.</span></span>  
  
 <span data-ttu-id="d00cc-109">[ログ配布について](https://docs.microsoft.com/sql/database-engine/log-shipping/about-log-shipping-sql-server)ドキュメントを sql には、特定の詳細情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="d00cc-109">[About Log Shipping](https://docs.microsoft.com/sql/database-engine/log-shipping/about-log-shipping-sql-server) in the SQL documentation provides specific details.</span></span>  
  
 <span data-ttu-id="d00cc-110">次の手順を使用すると、1 つのソース システムの 1 つのサーバーで構成されるターゲット システムを作成します。</span><span class="sxs-lookup"><span data-stu-id="d00cc-110">You can use the following steps to create a destination system that consists of one server for a single source system.</span></span> <span data-ttu-id="d00cc-111">送信先システムに複数のサーバーが含まれている場合は、各送信先サーバーで手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="d00cc-111">If the destination system contains multiple servers, repeat the steps on each destination server.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="d00cc-112">常に安全な場所にバックアップ ファイルのコピーを保持します。</span><span class="sxs-lookup"><span data-stu-id="d00cc-112">Always keep a copy of your backup files in a secure location.</span></span> <span data-ttu-id="d00cc-113">ログ バックアップがある場合でもバックアップ ファイルがない場合、データベースを復元することはできません。</span><span class="sxs-lookup"><span data-stu-id="d00cc-113">Even if you have log backups, you cannot restore your databases without the backup files.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="d00cc-114">前提条件</span><span class="sxs-lookup"><span data-stu-id="d00cc-114">Prerequisites</span></span>  
* <span data-ttu-id="d00cc-115">メンバーとしてサインイン、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理者グループ。</span><span class="sxs-lookup"><span data-stu-id="d00cc-115">Sign in as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
* <span data-ttu-id="d00cc-116">送信元と送信先システムで同じバージョンの SQL Server を使用します。</span><span class="sxs-lookup"><span data-stu-id="d00cc-116">Use the same version of SQL Server on the source and destination systems.</span></span> <span data-ttu-id="d00cc-117">SQL Server は、元とコピー先のシステムで、同じ相対的場所にインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d00cc-117">SQL Server must be installed in the same relative location on the source and destination systems.</span></span>  
  
* <span data-ttu-id="d00cc-118">SQL トランザクション ログのディレクトリ (します。LDF ファイル)、ソース システムする必要がありますも、送信先システムに存在します。</span><span class="sxs-lookup"><span data-stu-id="d00cc-118">The directory for SQL transaction log (.LDF files) on the source system must also exist on the destination system.</span></span> <span data-ttu-id="d00cc-119">送信先システムでこのディレクトリでない場合は、同じ名前と、ソース システム上とアクセス許可を持つ、ディレクトリを作成します。</span><span class="sxs-lookup"><span data-stu-id="d00cc-119">If this directory is not on the destination system, create the directory with the same name and permissions as on the source system.</span></span>  
  
### <a name="configure-the-destination-system-for-log-shipping"></a><span data-ttu-id="d00cc-120">ログ配布用に送信先システムを構成します。</span><span class="sxs-lookup"><span data-stu-id="d00cc-120">Configure the destination system for log shipping</span></span>  
  
1. <span data-ttu-id="d00cc-121">送信先システムで開く**SQL Server Management Studio**、し、SQL Server に接続します。</span><span class="sxs-lookup"><span data-stu-id="d00cc-121">On the destination system, open **SQL Server Management Studio**, and connect to your SQL Server.</span></span> <span data-ttu-id="d00cc-122">選択**マスター**から利用可能なデータベースです。</span><span class="sxs-lookup"><span data-stu-id="d00cc-122">Select **master** from Available Databases.</span></span>  
  
2. <span data-ttu-id="d00cc-123">**ファイル**] メニューの [**オープン**次の SQL スクリプト。</span><span class="sxs-lookup"><span data-stu-id="d00cc-123">On the **File** menu, **Open** the following SQL script:</span></span>  
  
   ```    
   %SystemDrive%\Program Files\Microsoft BizTalk Server <version>\Schema\LogShipping_Destination_Schema.sql  
   ```  
  
3. <span data-ttu-id="d00cc-124">**クエリ**メニューの  **Execute**します。</span><span class="sxs-lookup"><span data-stu-id="d00cc-124">On the **Query** menu, select **Execute**.</span></span>  
  
    <span data-ttu-id="d00cc-125">*LogShipping_Destination_Schema*され、送信先システムでソース データベースの復元に使用するテーブルを再作成します。</span><span class="sxs-lookup"><span data-stu-id="d00cc-125">The *LogShipping_Destination_Schema* drops and recreates the tables used for restoring the source databases on the destination system.</span></span> <span data-ttu-id="d00cc-126">データベース復旧中、ソース システムの BizTalkMgmtDb データベースからインポートされたバックアップ履歴のコピーの一覧を格納するテーブルが含まれ、SQL Server エージェント ジョブに関する情報を構成するソース データベースに対して実行します。</span><span class="sxs-lookup"><span data-stu-id="d00cc-126">This includes tables to store the list of databases being recovered, copies of the backup history imported from the source system's BizTalkMgmtDb database, and information about SQL Server Agent jobs configured to run against the source databases.</span></span>  
  
4. <span data-ttu-id="d00cc-127">**ファイル**] メニューの [**オープン**次の SQL スクリプト。</span><span class="sxs-lookup"><span data-stu-id="d00cc-127">On the **File** menu, **Open** the following SQL script:</span></span>  
  
   ```    
   %SystemDrive%\Program Files\Microsoft BizTalk Server <version>\Schema\LogShipping_Destination_Logic.sql  
   ```  
  
5. <span data-ttu-id="d00cc-128">**クエリ**メニューの  **Execute**します。</span><span class="sxs-lookup"><span data-stu-id="d00cc-128">On the **Query** menu, select **Execute**.</span></span>  
  
6. <span data-ttu-id="d00cc-129">送信先システムとして指定したコンピューターまたはコンピューターで開く**SQL Server Management Studio**し、SQL Server に接続します。</span><span class="sxs-lookup"><span data-stu-id="d00cc-129">On the computer or computers you have identified as the destination system, open **SQL Server Management Studio** and connect to the SQL Server.</span></span>  
  
7. <span data-ttu-id="d00cc-130">選択**新しいクエリ**します。</span><span class="sxs-lookup"><span data-stu-id="d00cc-130">Select **New Query**.</span></span> <span data-ttu-id="d00cc-131">クエリ ウィンドウで、次のコマンドを貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="d00cc-131">In the query window, paste the following command:</span></span>  
  
   ```  
   exec bts_ConfigureBizTalkLogShipping @nvcDescription = '<MyLogShippingSolution>',  
   @nvcMgmtDatabaseName = '<BizTalkServerManagementDatabaseName>',  
   @nvcMgmtServerName = '<BizTalkServerManagementDatabaseServer>',  
   @SourceServerName = null, -- null indicates that this destination server restores all databases  
   @fLinkServers = 1 -- 1 automatically links the server to the management database  
   ```  
  
    <span data-ttu-id="d00cc-132">そうしたら：</span><span class="sxs-lookup"><span data-stu-id="d00cc-132">Then:</span></span>  
  
   1.  <span data-ttu-id="d00cc-133">送信先システムで有効にする **[Ad Hoc Distributed Queries](https://docs.microsoft.com/sql/database-engine/configure-windows/server-configuration-options-sql-server)** します。</span><span class="sxs-lookup"><span data-stu-id="d00cc-133">On the destination system, enable **[Ad Hoc Distributed Queries](https://docs.microsoft.com/sql/database-engine/configure-windows/server-configuration-options-sql-server)**.</span></span>  
  
   2.  <span data-ttu-id="d00cc-134">クエリ ウィンドウに、 *\<MyLogShippingSolution\>* わかりやすい説明を単一引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="d00cc-134">In the query window, replace *\<MyLogShippingSolution\>* with a meaningful description, surrounded by single quotes.</span></span>  
  
   3.  <span data-ttu-id="d00cc-135">クエリ ウィンドウに、 *\<BizTalkServerManagementDatabaseName\>* と *\<BizTalkServerManagementDatabaseServer\>* で名前と、単一引用符で囲まれたソース BizTalk 管理データベースの場所。</span><span class="sxs-lookup"><span data-stu-id="d00cc-135">In the query window, replace *\<BizTalkServerManagementDatabaseName\>* and *\<BizTalkServerManagementDatabaseServer\>* with the name and location of your source BizTalk Management database, surrounded by single quotes.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="d00cc-136">1 つ以上のソース サーバーがある場合は、独自の移行先サーバーに各送信元サーバーを復元できます。</span><span class="sxs-lookup"><span data-stu-id="d00cc-136">If you have more than one source server, you can restore each source server to its own destination server.</span></span> <span data-ttu-id="d00cc-137">各送信先サーバーでの **@SourceServerName = null**パラメーター、置換*null*適切なソース サーバーの名前を単一引用符で囲みます (たとえば、  **@SourceServerName = 'MySourceServer'** )。</span><span class="sxs-lookup"><span data-stu-id="d00cc-137">On each destination server, in the **@SourceServerName = null** parameter, replace *null* with the name of the appropriate source server, surrounded by single quotes (for example, **@SourceServerName = 'MySourceServer',**).</span></span>  
  
8. <span data-ttu-id="d00cc-138">**クエリ**メニューの  **Execute**します。</span><span class="sxs-lookup"><span data-stu-id="d00cc-138">On the **Query** menu, select **Execute**.</span></span>  
  
   > [!IMPORTANT]
   >  <span data-ttu-id="d00cc-139">クエリに失敗した場合、クエリの問題を修正した後に、送信先システムを再構成するには、この手順の手順 1 から始める必要があります。</span><span class="sxs-lookup"><span data-stu-id="d00cc-139">If the query fails, after you fix the problem with the query, you must start over from step 1 of this procedure to reconfigure the destination system.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="d00cc-140">送信先システムで、復元ジョブは、ソース データベース サーバーに存在していた、同じ場所に復元された各データベースのログとデータ ファイルを再作成しようとします。</span><span class="sxs-lookup"><span data-stu-id="d00cc-140">The restore jobs on the destination system attempt to recreate the log and data files for each restored database in the same location as they existed on the source database server.</span></span>  
  
9. <span data-ttu-id="d00cc-141">送信先システムで**SQL Server Management Studio**、展開**SQL Server エージェント**、展開と**ジョブ**します。</span><span class="sxs-lookup"><span data-stu-id="d00cc-141">On the destination system in **SQL Server Management Studio**, expand **SQL Server Agent**, and expand **Jobs**.</span></span>  
  
     <span data-ttu-id="d00cc-142">詳細ペインでは、3 つの新しいジョブがあります。</span><span class="sxs-lookup"><span data-stu-id="d00cc-142">In the details pane, there are three new jobs:</span></span>  
  
   - <span data-ttu-id="d00cc-143">**BTS ログの配布のバックアップ履歴の取得**</span><span class="sxs-lookup"><span data-stu-id="d00cc-143">**BTS Log Shipping Get Backup History**</span></span>  
  
      <span data-ttu-id="d00cc-144">この BizTalk ジョブは、元のバックアップ履歴レコードを送信先に移動します。</span><span class="sxs-lookup"><span data-stu-id="d00cc-144">This BizTalk job moves backup history records from the source to the destination.</span></span> <span data-ttu-id="d00cc-145">なるは、既定では 1 分ごとに実行する予定です。</span><span class="sxs-lookup"><span data-stu-id="d00cc-145">It is scheduled by default to run every minute.</span></span> <span data-ttu-id="d00cc-146">先に、ソースから履歴レコードを移動するためにできる限り頻繁にこのジョブが実行されます。</span><span class="sxs-lookup"><span data-stu-id="d00cc-146">This job runs as frequently as possible in order to move history records from the source to the destination.</span></span> <span data-ttu-id="d00cc-147">ソース システムにシステムに障害が発生した場合は、送信先システムとして識別されるサーバーは、既にインポートされている履歴レコードを処理し続けます。</span><span class="sxs-lookup"><span data-stu-id="d00cc-147">In the event of a system failure to the source system, the server that you identified as the destination system continues to process the history records that have already been imported.</span></span>  
  
   - <span data-ttu-id="d00cc-148">**BTS Server のログ配布データベースの復元**</span><span class="sxs-lookup"><span data-stu-id="d00cc-148">**BTS Server Log Shipping Restore Databases**</span></span>  
  
      <span data-ttu-id="d00cc-149">この BizTalk ジョブは、移行先サーバーに、ソースとして指定したデータベースのバックアップ ファイルを復元します。</span><span class="sxs-lookup"><span data-stu-id="d00cc-149">This BizTalk job restores backup files for the given databases for the source to the destination server.</span></span> <span data-ttu-id="d00cc-150">なるは、既定では 1 分ごとに実行する予定です。</span><span class="sxs-lookup"><span data-stu-id="d00cc-150">It is scheduled by default to run every minute.</span></span> <span data-ttu-id="d00cc-151">このジョブは、復元するバックアップ ファイルがある限り、完了することがなく継続的に実行されます。</span><span class="sxs-lookup"><span data-stu-id="d00cc-151">This job runs continuously without completing as long as there are backup files to restore.</span></span> <span data-ttu-id="d00cc-152">追加の予防措置としてジョブを実行できますこのので、さらにタスクが完了したことを確認します。</span><span class="sxs-lookup"><span data-stu-id="d00cc-152">As an extra precaution, you can run this job an additional time to ensure that it is complete.</span></span>  
  
   - <span data-ttu-id="d00cc-153">**BTS ログのマークまで復元の配布**</span><span class="sxs-lookup"><span data-stu-id="d00cc-153">**BTS Log Shipping Restore To Mark**</span></span>  
  
      <span data-ttu-id="d00cc-154">この BizTalk ジョブは、最後のログ バックアップ内のマークまでにすべてのデータベースを復元します。</span><span class="sxs-lookup"><span data-stu-id="d00cc-154">This BizTalk job restores all of the databases to a mark in the last log backup.</span></span> <span data-ttu-id="d00cc-155">これによりはすべて、データベースのトランザクション上一貫性のある状態であります。</span><span class="sxs-lookup"><span data-stu-id="d00cc-155">This ensures that all of the databases are in a transactionally consistent state.</span></span> <span data-ttu-id="d00cc-156">さらに、このジョブがソース システムになっていた送信先システムで SQL Server エージェント ジョブのすべての演算子を作成します再します。</span><span class="sxs-lookup"><span data-stu-id="d00cc-156">In addition, this job re-creates all of the SQL Server Agent jobs on the destination system that had been on the source system.</span></span>  
  
     > [!IMPORTANT]
     >  <span data-ttu-id="d00cc-157">失敗しないことを確認します。 これらのジョブを監視する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d00cc-157">You should monitor these jobs to ensure that they do not fail.</span></span>  
  
10. <span data-ttu-id="d00cc-158">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]で、次のフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="d00cc-158">On the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], go to the following folder:</span></span>  
  
     <span data-ttu-id="d00cc-159">32 ビット コンピューター: %SystemDrive%\Program files \microsoft BizTalk Server\<バージョン\>\Schema\Restore</span><span class="sxs-lookup"><span data-stu-id="d00cc-159">32-bit computer: %SystemDrive%\Program Files\Microsoft BizTalk Server \<version\>\Schema\Restore</span></span>  
  
     <span data-ttu-id="d00cc-160">64 ビット コンピューター: %SystemDrive%\Program Files (x86) \Microsoft BizTalk Server\<バージョン\>\Bins32\Schema\Restore</span><span class="sxs-lookup"><span data-stu-id="d00cc-160">64-bit computer: %SystemDrive%\Program Files (x86)\Microsoft BizTalk Server \<version\>\Bins32\Schema\Restore</span></span>  
  
11. <span data-ttu-id="d00cc-161">右クリック**SampleUpdateInfo.xml**、選び**編集**します。</span><span class="sxs-lookup"><span data-stu-id="d00cc-161">Right-click **SampleUpdateInfo.xml**, and select **Edit**.</span></span> <span data-ttu-id="d00cc-162">次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="d00cc-162">Do the following:</span></span>  
  
    -   <span data-ttu-id="d00cc-163">すべてのインスタンスを置き換える **"SourceServer"** ソース システムの名前に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="d00cc-163">Replace all instances of **"SourceServer"** with the name of the source system.</span></span>  
  
    -   <span data-ttu-id="d00cc-164">すべてのインスタンスを置き換える **"DestinationServer"** 送信先システムの名前に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="d00cc-164">Replace all instances of **"DestinationServer"** with the name of the destination system.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="d00cc-165">送信元システムおよび送信先システムの名前は、引用符で囲んでください。</span><span class="sxs-lookup"><span data-stu-id="d00cc-165">Include the quotation marks around the name of the source and destination systems.</span></span>  
    > 
    > [!NOTE]
    >  <span data-ttu-id="d00cc-166">いずれかの名前を変更した場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース、XML ファイル内のデータベース名を更新することも必要があります。</span><span class="sxs-lookup"><span data-stu-id="d00cc-166">If you renamed any of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases, you must also update the database names within the XML file.</span></span>  
    > 
    > [!NOTE]
    >  <span data-ttu-id="d00cc-167">BAM を構成している場合は、次の行を追加する必要があります、 **OtherDatabases**のセクション、 **SampleUpdateInfo.xml** BAMAlertsApplication、BAMAlertsNSMain データベースのファイル。</span><span class="sxs-lookup"><span data-stu-id="d00cc-167">If you have configured BAM, you must add the following lines in the **OtherDatabases** section of the **SampleUpdateInfo.xml** file for the BAMAlertsApplication and BAMAlertsNSMain databases:</span></span>   
    > `<Database Name="BAM Alerts Application DB" oldDBName="BAMAlertsApplication" oldDBServer="SourceServer" newDBName=" BAMAlertsApplication" newDBServer="DestinationServer"/>`  
    > `<Database Name="BAM Alerts Instance DB" oldDBName="BAMAlertsNSMain" oldDBServer="SourceServer" newDBName="BAMAlertsNSMain" newDBServer="DestinationServer"/>`  
    > 
    >  <span data-ttu-id="d00cc-168">これら 2 つのデータベースの既定の名前を変更した場合は、実際のデータベース名を使用してください。</span><span class="sxs-lookup"><span data-stu-id="d00cc-168">If you changed the default name for these two databases, please use the actual database names.</span></span>  
  
12. <span data-ttu-id="d00cc-169">複数のメッセージ ボックス データベースがある場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]システムは、リストに別の MessageBoxDB 行を追加し、設定**IsMaster =「0」** マスター以外のデータベースにします。</span><span class="sxs-lookup"><span data-stu-id="d00cc-169">If you have more than one MessageBox database in your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] system, add another MessageBoxDB line to the list, and then set **IsMaster="0"** for the non-master databases.</span></span>  
  
13. <span data-ttu-id="d00cc-170">BAM またはルール エンジンを使用している場合は、必要に応じてこれらの行をコメント解除します。</span><span class="sxs-lookup"><span data-stu-id="d00cc-170">If you are using BAM or the Rules Engine, uncomment these lines as appropriate.</span></span>  
  
14. <span data-ttu-id="d00cc-171">すべてのカスタム データベースがあれば、下に追加、 **\<OtherDatabases\>** セクション。</span><span class="sxs-lookup"><span data-stu-id="d00cc-171">If you have any custom databases, add them under the **\<OtherDatabases\>** section.</span></span> <span data-ttu-id="d00cc-172">参照してください[カスタム データベースをバックアップする方法](../core/how-to-back-up-custom-databases.md)します。</span><span class="sxs-lookup"><span data-stu-id="d00cc-172">See [How to Back Up Custom Databases](../core/how-to-back-up-custom-databases.md).</span></span>  
  
15. <span data-ttu-id="d00cc-173">ファイルの編集を終了したら、ファイルを保存して閉じます。</span><span class="sxs-lookup"><span data-stu-id="d00cc-173">When you are finished editing the file, save it, and exit.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="d00cc-174">次の手順</span><span class="sxs-lookup"><span data-stu-id="d00cc-174">Next Steps</span></span>  
 [<span data-ttu-id="d00cc-175">データベースを復元する方法</span><span class="sxs-lookup"><span data-stu-id="d00cc-175">How to Restore Your Databases</span></span>](../core/how-to-restore-your-databases.md)  
  
## <a name="see-also"></a><span data-ttu-id="d00cc-176">参照</span><span class="sxs-lookup"><span data-stu-id="d00cc-176">See Also</span></span>  
 <span data-ttu-id="d00cc-177">[バックアップ BizTalk Server ジョブを構成する方法](../core/how-to-configure-the-backup-biztalk-server-job.md) </span><span class="sxs-lookup"><span data-stu-id="d00cc-177">[How to Configure the Backup BizTalk Server Job](../core/how-to-configure-the-backup-biztalk-server-job.md) </span></span>  
 <span data-ttu-id="d00cc-178">[バックアップ BizTalk Server のジョブをスケジュールする方法](../core/how-to-schedule-the-backup-biztalk-server-job.md) </span><span class="sxs-lookup"><span data-stu-id="d00cc-178">[How to Schedule the Backup BizTalk Server Job](../core/how-to-schedule-the-backup-biztalk-server-job.md) </span></span>  
 [<span data-ttu-id="d00cc-179">カスタム データベースをバックアップする方法</span><span class="sxs-lookup"><span data-stu-id="d00cc-179">How to Back Up Custom Databases</span></span>](../core/how-to-back-up-custom-databases.md)