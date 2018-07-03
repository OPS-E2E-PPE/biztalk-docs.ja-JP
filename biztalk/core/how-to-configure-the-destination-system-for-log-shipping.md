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
ms.openlocfilehash: 9ee5c7a5d59ce60923fa4ad3ba015f60bc30a0c8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971467"
---
# <a name="how-to-configure-the-destination-system-for-log-shipping"></a><span data-ttu-id="c70d0-102">ログ配布用に送信先システムを構成する方法</span><span class="sxs-lookup"><span data-stu-id="c70d0-102">How to Configure the Destination System for Log Shipping</span></span>
<span data-ttu-id="c70d0-103">ログ配布は、システム障害時のダウンタイムを短縮することを目的とした、スタンバイ サーバーの機能です。</span><span class="sxs-lookup"><span data-stu-id="c70d0-103">Log shipping provides standby server capabilities to reduce downtime in the event of a system failure.</span></span> <span data-ttu-id="c70d0-104">ログ配布を使用すると、送信元システムのトランザクション ログを送信先システムに自動的に送信できます。</span><span class="sxs-lookup"><span data-stu-id="c70d0-104">Log shipping allows you to automatically send transaction logs from the source system to the destination system.</span></span> <span data-ttu-id="c70d0-105">送信先システムでトランザクション ログの復元、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース; ソース データベースと密接に同期を維持することです。</span><span class="sxs-lookup"><span data-stu-id="c70d0-105">At the destination system, the transaction logs are restored to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases; keeping them closely synchronized with the source databases.</span></span>  
  
 <span data-ttu-id="c70d0-106">ログ配布は、単一サーバー環境および分散型サーバー環境の両方で動作します。</span><span class="sxs-lookup"><span data-stu-id="c70d0-106">Log shipping works in both single server and distributed server environments.</span></span> <span data-ttu-id="c70d0-107">ライブ データが格納されたサーバーまたはサーバーのグループを、送信元 (プライマリ) システムと呼びます。</span><span class="sxs-lookup"><span data-stu-id="c70d0-107">The server or group of servers that contain live data is known as the source (or primary) system.</span></span> <span data-ttu-id="c70d0-108">送信元 (プライマリ) システムによって生成されたデータベース バックアップの復元先として使用するサーバーまたはサーバーのグループを、送信先 (セカンダリ) システムと呼びます。</span><span class="sxs-lookup"><span data-stu-id="c70d0-108">The server or group of servers that are used to restore the database backups produced by the source (or primary) system is known as the destination (or secondary) system.</span></span>  
  
 <span data-ttu-id="c70d0-109">[ログ配布について](https://docs.microsoft.com/sql/database-engine/log-shipping/about-log-shipping-sql-server)ドキュメントを sql には、特定の詳細情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="c70d0-109">[About Log Shipping](https://docs.microsoft.com/sql/database-engine/log-shipping/about-log-shipping-sql-server) in the SQL documentation provides specific details.</span></span>  
  
 <span data-ttu-id="c70d0-110">次の手順を使用すれば、1 つの送信元システムに対する 1 サーバーの送信先システムを作成できます。</span><span class="sxs-lookup"><span data-stu-id="c70d0-110">You can use the following steps to create a destination system that consists of one server for a single source system.</span></span> <span data-ttu-id="c70d0-111">送信先システムに複数のサーバーが含まれる場合は、各送信先サーバーに対してこの手順を繰り返してください。</span><span class="sxs-lookup"><span data-stu-id="c70d0-111">If the destination system contains multiple servers, repeat the steps on each destination server.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="c70d0-112">バックアップ ファイルのコピーは、常に安全な場所に保管してください。</span><span class="sxs-lookup"><span data-stu-id="c70d0-112">Always keep a copy of your backup files in a secure location.</span></span> <span data-ttu-id="c70d0-113">ログ バックアップがあっても、バックアップ ファイルがなければデータベースを復元することはできません。</span><span class="sxs-lookup"><span data-stu-id="c70d0-113">Even if you have log backups, you cannot restore your databases without the backup files.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="c70d0-114">前提条件</span><span class="sxs-lookup"><span data-stu-id="c70d0-114">Prerequisites</span></span>  
* <span data-ttu-id="c70d0-115">メンバーとしてサインイン、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理者グループ。</span><span class="sxs-lookup"><span data-stu-id="c70d0-115">Sign in as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
* <span data-ttu-id="c70d0-116">送信元と送信先システムで同じバージョンの SQL Server を使用します。</span><span class="sxs-lookup"><span data-stu-id="c70d0-116">Use the same version of SQL Server on the source and destination systems.</span></span> <span data-ttu-id="c70d0-117">SQL Server は、元とコピー先のシステムで、同じ相対的場所にインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c70d0-117">SQL Server must be installed in the same relative location on the source and destination systems.</span></span>  
  
* <span data-ttu-id="c70d0-118">送信先システムにも、送信元システムの SQL トランザクション ログ (.LDF ファイル) のディレクトリが存在している必要があります。</span><span class="sxs-lookup"><span data-stu-id="c70d0-118">The directory for SQL transaction log (.LDF files) on the source system must also exist on the destination system.</span></span> <span data-ttu-id="c70d0-119">このディレクトリが送信先システムにない場合は、送信元システムと同じ名前およびアクセス許可を持つディレクトリを作成します。</span><span class="sxs-lookup"><span data-stu-id="c70d0-119">If this directory is not on the destination system, create the directory with the same name and permissions as on the source system.</span></span>  
  
### <a name="configure-the-destination-system-for-log-shipping"></a><span data-ttu-id="c70d0-120">ログ配布用に送信先システムを構成します。</span><span class="sxs-lookup"><span data-stu-id="c70d0-120">Configure the destination system for log shipping</span></span>  
  
1. <span data-ttu-id="c70d0-121">送信先システムで開く**SQL Server Management Studio**、し、SQL Server に接続します。</span><span class="sxs-lookup"><span data-stu-id="c70d0-121">On the destination system, open **SQL Server Management Studio**, and connect to your SQL Server.</span></span> <span data-ttu-id="c70d0-122">選択**マスター**から利用可能なデータベースです。</span><span class="sxs-lookup"><span data-stu-id="c70d0-122">Select **master** from Available Databases.</span></span>  
  
2. <span data-ttu-id="c70d0-123">**ファイル**] メニューの [**オープン**次の SQL スクリプト。</span><span class="sxs-lookup"><span data-stu-id="c70d0-123">On the **File** menu, **Open** the following SQL script:</span></span>  
  
   ```    
   %SystemDrive%\Program Files\Microsoft BizTalk Server <version>\Schema\LogShipping_Destination_Schema.sql  
   ```  
  
3. <span data-ttu-id="c70d0-124">**クエリ**メニューの  **Execute**します。</span><span class="sxs-lookup"><span data-stu-id="c70d0-124">On the **Query** menu, select **Execute**.</span></span>  
  
    <span data-ttu-id="c70d0-125">*LogShipping_Destination_Schema*され、送信先システムでソース データベースの復元に使用するテーブルを再作成します。</span><span class="sxs-lookup"><span data-stu-id="c70d0-125">The *LogShipping_Destination_Schema* drops and recreates the tables used for restoring the source databases on the destination system.</span></span> <span data-ttu-id="c70d0-126">これには、復元対象のデータベースの一覧を格納するテーブル、送信元システムの BizTalkMgmtDb データベースからインポートされたバックアップ履歴のコピー、および送信元データベースに対して実行するように構成されている SQL Server エージェント ジョブについての情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="c70d0-126">This includes tables to store the list of databases being recovered, copies of the backup history imported from the source system's BizTalkMgmtDb database, and information about SQL Server Agent jobs configured to run against the source databases.</span></span>  
  
4. <span data-ttu-id="c70d0-127">**ファイル**] メニューの [**オープン**次の SQL スクリプト。</span><span class="sxs-lookup"><span data-stu-id="c70d0-127">On the **File** menu, **Open** the following SQL script:</span></span>  
  
   ```    
   %SystemDrive%\Program Files\Microsoft BizTalk Server <version>\Schema\LogShipping_Destination_Logic.sql  
   ```  
  
5. <span data-ttu-id="c70d0-128">**クエリ**メニューの  **Execute**します。</span><span class="sxs-lookup"><span data-stu-id="c70d0-128">On the **Query** menu, select **Execute**.</span></span>  
  
6. <span data-ttu-id="c70d0-129">送信先システムとして指定したコンピューターまたはコンピューターで開く**SQL Server Management Studio**し、SQL Server に接続します。</span><span class="sxs-lookup"><span data-stu-id="c70d0-129">On the computer or computers you have identified as the destination system, open **SQL Server Management Studio** and connect to the SQL Server.</span></span>  
  
7. <span data-ttu-id="c70d0-130">選択**新しいクエリ**します。</span><span class="sxs-lookup"><span data-stu-id="c70d0-130">Select **New Query**.</span></span> <span data-ttu-id="c70d0-131">クエリ ウィンドウに、次のコマンドを貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="c70d0-131">In the query window, paste the following command:</span></span>  
  
   ```  
   exec bts_ConfigureBizTalkLogShipping @nvcDescription = '<MyLogShippingSolution>',  
   @nvcMgmtDatabaseName = '<BizTalkServerManagementDatabaseName>',  
   @nvcMgmtServerName = '<BizTalkServerManagementDatabaseServer>',  
   @SourceServerName = null, -- null indicates that this destination server restores all databases  
   @fLinkServers = 1 -- 1 automatically links the server to the management database  
   ```  
  
    <span data-ttu-id="c70d0-132">そうしたら：</span><span class="sxs-lookup"><span data-stu-id="c70d0-132">Then:</span></span>  
  
   1.  <span data-ttu-id="c70d0-133">送信先システムで有効にする **[Ad Hoc Distributed Queries](https://docs.microsoft.com/sql/database-engine/configure-windows/server-configuration-options-sql-server)** します。</span><span class="sxs-lookup"><span data-stu-id="c70d0-133">On the destination system, enable **[Ad Hoc Distributed Queries](https://docs.microsoft.com/sql/database-engine/configure-windows/server-configuration-options-sql-server)**.</span></span>  
  
   2.  <span data-ttu-id="c70d0-134">クエリ ウィンドウに、 *\<MyLogShippingSolution\>* わかりやすい説明を単一引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="c70d0-134">In the query window, replace *\<MyLogShippingSolution\>* with a meaningful description, surrounded by single quotes.</span></span>  
  
   3.  <span data-ttu-id="c70d0-135">クエリ ウィンドウに、 *\<BizTalkServerManagementDatabaseName\>* と*\<BizTalkServerManagementDatabaseServer\>* で名前と、単一引用符で囲まれたソース BizTalk 管理データベースの場所。</span><span class="sxs-lookup"><span data-stu-id="c70d0-135">In the query window, replace *\<BizTalkServerManagementDatabaseName\>* and *\<BizTalkServerManagementDatabaseServer\>* with the name and location of your source BizTalk Management database, surrounded by single quotes.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="c70d0-136">複数の送信元サーバーがある場合は、各送信元サーバーをそれぞれ独自の送信先サーバーに復元できます。</span><span class="sxs-lookup"><span data-stu-id="c70d0-136">If you have more than one source server, you can restore each source server to its own destination server.</span></span> <span data-ttu-id="c70d0-137">各送信先サーバーでの **@SourceServerName = null**パラメーター、置換*null*適切なソース サーバーの名前を単一引用符で囲みます (たとえば、  **@SourceServerName = 'MySourceServer'**)。</span><span class="sxs-lookup"><span data-stu-id="c70d0-137">On each destination server, in the **@SourceServerName = null** parameter, replace *null* with the name of the appropriate source server, surrounded by single quotes (for example, **@SourceServerName = 'MySourceServer',**).</span></span>  
  
8. <span data-ttu-id="c70d0-138">**クエリ**メニューの  **Execute**します。</span><span class="sxs-lookup"><span data-stu-id="c70d0-138">On the **Query** menu, select **Execute**.</span></span>  
  
   > [!IMPORTANT]
   >  <span data-ttu-id="c70d0-139">クエリが失敗した場合は、クエリの問題を修正した後で、この手順の手順 1. から開始して、送信先システムを再構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c70d0-139">If the query fails, after you fix the problem with the query, you must start over from step 1 of this procedure to reconfigure the destination system.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="c70d0-140">送信先システムでの復元ジョブは、復元された各データベースに対するログ ファイルおよびデータ ファイルを、送信元データベース サーバーに格納されていたときと同じ場所に再作成しようとします。</span><span class="sxs-lookup"><span data-stu-id="c70d0-140">The restore jobs on the destination system attempt to recreate the log and data files for each restored database in the same location as they existed on the source database server.</span></span>  
  
9. <span data-ttu-id="c70d0-141">送信先システムで**SQL Server Management Studio**、展開**SQL Server エージェント**、展開と**ジョブ**します。</span><span class="sxs-lookup"><span data-stu-id="c70d0-141">On the destination system in **SQL Server Management Studio**, expand **SQL Server Agent**, and expand **Jobs**.</span></span>  
  
     <span data-ttu-id="c70d0-142">詳細ウィンドウに、次の 3 つの新しいジョブが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c70d0-142">In the details pane, there are three new jobs:</span></span>  
  
   - <span data-ttu-id="c70d0-143">**BTS ログの配布のバックアップ履歴の取得**</span><span class="sxs-lookup"><span data-stu-id="c70d0-143">**BTS Log Shipping Get Backup History**</span></span>  
  
      <span data-ttu-id="c70d0-144">この BizTalk ジョブでは、送信元のバックアップ履歴レコードを送信先に移動します。</span><span class="sxs-lookup"><span data-stu-id="c70d0-144">This BizTalk job moves backup history records from the source to the destination.</span></span> <span data-ttu-id="c70d0-145">既定では、ジョブを 1 分おきに実行するスケジュールになります。</span><span class="sxs-lookup"><span data-stu-id="c70d0-145">It is scheduled by default to run every minute.</span></span> <span data-ttu-id="c70d0-146">このジョブは、履歴レコードを送信元から送信先に移動するために、可能な限り頻繁に実行されます。</span><span class="sxs-lookup"><span data-stu-id="c70d0-146">This job runs as frequently as possible in order to move history records from the source to the destination.</span></span> <span data-ttu-id="c70d0-147">送信元システムでシステム障害が発生しても、送信先システムとして指定したサーバーでは、インポート済みの履歴レコードの処理が続行します。</span><span class="sxs-lookup"><span data-stu-id="c70d0-147">In the event of a system failure to the source system, the server that you identified as the destination system continues to process the history records that have already been imported.</span></span>  
  
   - <span data-ttu-id="c70d0-148">**BTS Server のログ配布データベースの復元**</span><span class="sxs-lookup"><span data-stu-id="c70d0-148">**BTS Server Log Shipping Restore Databases**</span></span>  
  
      <span data-ttu-id="c70d0-149">この BizTalk ジョブは、移行元の指定されたデータベースのバックアップ ファイルを移行先サーバーに復元します。</span><span class="sxs-lookup"><span data-stu-id="c70d0-149">This BizTalk job restores backup files for the given databases for the source to the destination server.</span></span> <span data-ttu-id="c70d0-150">既定では、ジョブを 1 分おきに実行するスケジュールになります。</span><span class="sxs-lookup"><span data-stu-id="c70d0-150">It is scheduled by default to run every minute.</span></span> <span data-ttu-id="c70d0-151">このジョブは、復元するバックアップ ファイルがある限り、完了することなく続行されます。</span><span class="sxs-lookup"><span data-stu-id="c70d0-151">This job runs continuously without completing as long as there are backup files to restore.</span></span> <span data-ttu-id="c70d0-152">用心のために、このジョブを 1 回だけ多く実行してジョブが完了していることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="c70d0-152">As an extra precaution, you can run this job an additional time to ensure that it is complete.</span></span>  
  
   - <span data-ttu-id="c70d0-153">**BTS ログのマークまで復元の配布**</span><span class="sxs-lookup"><span data-stu-id="c70d0-153">**BTS Log Shipping Restore To Mark**</span></span>  
  
      <span data-ttu-id="c70d0-154">この BizTalk ジョブは、すべてのデータベースを最新のログ バックアップ内のマークまで復元します。</span><span class="sxs-lookup"><span data-stu-id="c70d0-154">This BizTalk job restores all of the databases to a mark in the last log backup.</span></span> <span data-ttu-id="c70d0-155">これにより、すべてのデータベースでトランザクションの状態の一貫性が確保されます。</span><span class="sxs-lookup"><span data-stu-id="c70d0-155">This ensures that all of the databases are in a transactionally consistent state.</span></span> <span data-ttu-id="c70d0-156">さらに、このジョブでは、送信元システムに存在したすべての SQL Server エージェント ジョブが送信先システムに再作成されます。</span><span class="sxs-lookup"><span data-stu-id="c70d0-156">In addition, this job re-creates all of the SQL Server Agent jobs on the destination system that had been on the source system.</span></span>  
  
     > [!IMPORTANT]
     >  <span data-ttu-id="c70d0-157">これらのジョブが失敗しないように監視する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c70d0-157">You should monitor these jobs to ensure that they do not fail.</span></span>  
  
10. <span data-ttu-id="c70d0-158">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] で、次のフォルダーを開きます。</span><span class="sxs-lookup"><span data-stu-id="c70d0-158">On the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], go to the following folder:</span></span>  
  
     <span data-ttu-id="c70d0-159">32 ビット コンピューター: %SystemDrive%\Program files \microsoft BizTalk Server\<バージョン\>\Schema\Restore</span><span class="sxs-lookup"><span data-stu-id="c70d0-159">32-bit computer: %SystemDrive%\Program Files\Microsoft BizTalk Server \<version\>\Schema\Restore</span></span>  
  
     <span data-ttu-id="c70d0-160">64 ビット コンピューター: %SystemDrive%\Program Files (x86) \Microsoft BizTalk Server\<バージョン\>\Bins32\Schema\Restore</span><span class="sxs-lookup"><span data-stu-id="c70d0-160">64-bit computer: %SystemDrive%\Program Files (x86)\Microsoft BizTalk Server \<version\>\Bins32\Schema\Restore</span></span>  
  
11. <span data-ttu-id="c70d0-161">右クリック**SampleUpdateInfo.xml**、選び**編集**します。</span><span class="sxs-lookup"><span data-stu-id="c70d0-161">Right-click **SampleUpdateInfo.xml**, and select **Edit**.</span></span> <span data-ttu-id="c70d0-162">次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="c70d0-162">Do the following:</span></span>  
  
    -   <span data-ttu-id="c70d0-163">すべてのインスタンスを置き換える **"SourceServer"** ソース システムの名前に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="c70d0-163">Replace all instances of **"SourceServer"** with the name of the source system.</span></span>  
  
    -   <span data-ttu-id="c70d0-164">すべてのインスタンスを置き換える **"DestinationServer"** 送信先システムの名前に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="c70d0-164">Replace all instances of **"DestinationServer"** with the name of the destination system.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="c70d0-165">送信元システムおよび送信先システムの名前は、引用符で囲んでください。</span><span class="sxs-lookup"><span data-stu-id="c70d0-165">Include the quotation marks around the name of the source and destination systems.</span></span>  
    > 
    > [!NOTE]
    >  <span data-ttu-id="c70d0-166">いずれかの [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] データベースの名前を変更した場合、XML ファイル内のデータベース名も更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c70d0-166">If you renamed any of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases, you must also update the database names within the XML file.</span></span>  
    > 
    > [!NOTE]
    >  <span data-ttu-id="c70d0-167">BAM を構成している場合は、次の行を追加する必要があります、 **OtherDatabases**のセクション、 **SampleUpdateInfo.xml** BAMAlertsApplication、BAMAlertsNSMain データベースのファイル。</span><span class="sxs-lookup"><span data-stu-id="c70d0-167">If you have configured BAM, you must add the following lines in the **OtherDatabases** section of the **SampleUpdateInfo.xml** file for the BAMAlertsApplication and BAMAlertsNSMain databases:</span></span>   
    > `<Database Name="BAM Alerts Application DB" oldDBName="BAMAlertsApplication" oldDBServer="SourceServer" newDBName=" BAMAlertsApplication" newDBServer="DestinationServer"/>`  
    > `<Database Name="BAM Alerts Instance DB" oldDBName="BAMAlertsNSMain" oldDBServer="SourceServer" newDBName="BAMAlertsNSMain" newDBServer="DestinationServer"/>`  
    > 
    >  <span data-ttu-id="c70d0-168">これら 2 つのデータベースの既定の名前を変更した場合は、実際のデータベース名を使用してください。</span><span class="sxs-lookup"><span data-stu-id="c70d0-168">If you changed the default name for these two databases, please use the actual database names.</span></span>  
  
12. <span data-ttu-id="c70d0-169">複数のメッセージ ボックス データベースがある場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]システムは、リストに別の MessageBoxDB 行を追加し、設定**IsMaster =「0」** マスター以外のデータベースにします。</span><span class="sxs-lookup"><span data-stu-id="c70d0-169">If you have more than one MessageBox database in your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] system, add another MessageBoxDB line to the list, and then set **IsMaster="0"** for the non-master databases.</span></span>  
  
13. <span data-ttu-id="c70d0-170">BAM またはルール エンジンを使用する場合は、必要に応じてこれらの行をコメント解除してください。</span><span class="sxs-lookup"><span data-stu-id="c70d0-170">If you are using BAM or the Rules Engine, uncomment these lines as appropriate.</span></span>  
  
14. <span data-ttu-id="c70d0-171">すべてのカスタム データベースがあれば、下に追加、 **\<OtherDatabases\>** セクション。</span><span class="sxs-lookup"><span data-stu-id="c70d0-171">If you have any custom databases, add them under the **\<OtherDatabases\>** section.</span></span> <span data-ttu-id="c70d0-172">参照してください[カスタム データベースをバックアップする方法](../core/how-to-back-up-custom-databases.md)します。</span><span class="sxs-lookup"><span data-stu-id="c70d0-172">See [How to Back Up Custom Databases](../core/how-to-back-up-custom-databases.md).</span></span>  
  
15. <span data-ttu-id="c70d0-173">ファイルの編集を終了したら、ファイルを保存して閉じます。</span><span class="sxs-lookup"><span data-stu-id="c70d0-173">When you are finished editing the file, save it, and exit.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="c70d0-174">次の手順</span><span class="sxs-lookup"><span data-stu-id="c70d0-174">Next Steps</span></span>  
 [<span data-ttu-id="c70d0-175">データベースを復元する方法</span><span class="sxs-lookup"><span data-stu-id="c70d0-175">How to Restore Your Databases</span></span>](../core/how-to-restore-your-databases.md)  
  
## <a name="see-also"></a><span data-ttu-id="c70d0-176">参照</span><span class="sxs-lookup"><span data-stu-id="c70d0-176">See Also</span></span>  
 <span data-ttu-id="c70d0-177">[バックアップ BizTalk Server ジョブを構成する方法](../core/how-to-configure-the-backup-biztalk-server-job.md) </span><span class="sxs-lookup"><span data-stu-id="c70d0-177">[How to Configure the Backup BizTalk Server Job](../core/how-to-configure-the-backup-biztalk-server-job.md) </span></span>  
 <span data-ttu-id="c70d0-178">[バックアップ BizTalk Server のジョブをスケジュールする方法](../core/how-to-schedule-the-backup-biztalk-server-job.md) </span><span class="sxs-lookup"><span data-stu-id="c70d0-178">[How to Schedule the Backup BizTalk Server Job](../core/how-to-schedule-the-backup-biztalk-server-job.md) </span></span>  
 [<span data-ttu-id="c70d0-179">カスタム データベースをバックアップする方法</span><span class="sxs-lookup"><span data-stu-id="c70d0-179">How to Back Up Custom Databases</span></span>](../core/how-to-back-up-custom-databases.md)