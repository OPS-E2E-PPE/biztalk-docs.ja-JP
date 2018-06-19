---
title: データベースを復元する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 2016-05-10
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- backing up, log shipping
- restoring [BAM], Star Schema database, Star Schema database [BAM], restoring
- restoring, 64-bit environments
- Star Schema database [BAM], restoring
- restoring [BAM], Analysis database
- log shipping
- databases, restoring
- Archive database [BAM], restoring
- backing up, restoring
- Analysis database [BAM], restoring
- restoring [BAM], Archive database
- restoring [BAM], Star Schema database
- databases, restoring [64-bit environment]
- Primary Import database [BAM], restoring
- 64-bit environments, restoring databases
- restoring, databases
ms.assetid: 0176932a-6b3d-4502-975b-a76296189092
caps.latest.revision: 52
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6833fff893a692475e97e7722d9d65658eace0d3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22255770"
---
# <a name="how-to-restore-your-databases"></a><span data-ttu-id="7fa15-102">データベースを復元する方法</span><span class="sxs-lookup"><span data-stu-id="7fa15-102">How to Restore Your Databases</span></span>
<span data-ttu-id="7fa15-103">データベース間のトランザクション状態の一貫性を保証するには、すべてのデータベースを同じマークに復元する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7fa15-103">You must restore all databases to the same mark to ensure a consistent transactional state among the databases.</span></span> <span data-ttu-id="7fa15-104">参照してください[マークされたトランザクション、完全バックアップ、およびログ バックアップ](../core/marked-transactions-full-backups-and-log-backups.md)です。</span><span class="sxs-lookup"><span data-stu-id="7fa15-104">See [Marked Transactions, Full Backups, and Log Backups](../core/marked-transactions-full-backups-and-log-backups.md).</span></span>  
  
 <span data-ttu-id="7fa15-105">送信先システムにあるサーバーが 1 つだけの場合は、(最新のセットを除く) すべてのログのバックアップ セットが復元されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="7fa15-105">If there is only one server in the destination system, make sure that all of the log backup sets (except for the most recent set) have been restored.</span></span> <span data-ttu-id="7fa15-106">参照してください[バックアップを復元の履歴を表示する](../core/viewing-the-history-of-restored-backups.md)です。</span><span class="sxs-lookup"><span data-stu-id="7fa15-106">See [Viewing the History of Restored Backups](../core/viewing-the-history-of-restored-backups.md).</span></span> <span data-ttu-id="7fa15-107">すべてのログ バックアップ セットの復元が完了していない場合、復元ジョブが現在実行中でなければ、ジョブを実行します (必要に応じて手動で)。</span><span class="sxs-lookup"><span data-stu-id="7fa15-107">If all the log backup sets have not been restored, and the restore job is not currently running, run the restore job (manually if necessary).</span></span> <span data-ttu-id="7fa15-108">復元できるは保留状態のバックアップ セットがある場合は、ジョブを処理して、復元されるまですべてします。</span><span class="sxs-lookup"><span data-stu-id="7fa15-108">If there are outstanding backup sets that can be restored, the job processes them until they are all restored.</span></span>  
  
 <span data-ttu-id="7fa15-109">送信先システムに複数のサーバーがある場合は、すべてのサーバーの復元を同じバックアップ セットで行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="7fa15-109">If there are multiple servers in the destination system, all servers must be restored to the same backup set.</span></span> <span data-ttu-id="7fa15-110">各サーバーで復元の履歴を表示し、最新のログ バックアップが復元された設定がすべてのサーバーで同じであるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="7fa15-110">View the restore history on each server and make sure that the most recent log backup set restored is the same on all servers.</span></span> <span data-ttu-id="7fa15-111">同一の最新ログ バックアップ セットで復元されていないサーバーがある場合は、そのサーバーに対する復元ジョブを手動で実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7fa15-111">If it is not, you must manually run the restore job on each server that needs the most recent log backup set restored.</span></span>  
  
 <span data-ttu-id="7fa15-112">すべてのサーバーが同じバックアップ セットになったら、最後のセットは手動で復元できます。</span><span class="sxs-lookup"><span data-stu-id="7fa15-112">After all of the servers are on the same backup set, the final set can be manually restored.</span></span>  
  
 <span data-ttu-id="7fa15-113">adm_BackupHistory テーブルは、ソース システムのログ配布プロセスの中心的な履歴ポイントです。</span><span class="sxs-lookup"><span data-stu-id="7fa15-113">The adm_BackupHistory table is the central history point for the log shipping process for the source system.</span></span> <span data-ttu-id="7fa15-114">実行されたバックアップ作業はすべてこのテーブルに記録されます。</span><span class="sxs-lookup"><span data-stu-id="7fa15-114">All backup work performed is recorded to this table.</span></span> <span data-ttu-id="7fa15-115">送信先システムにあるすべてのサーバーは、復元作業の実行に必要な情報を受け取るためにこのテーブルから読み取ります。</span><span class="sxs-lookup"><span data-stu-id="7fa15-115">All servers in your destination system read from this table to receive the information needed to perform their restore work.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7fa15-116">BAM プライマリ インポート データベースをバックアップから復元する場合は、BAM プライマリよりも古いバックアップを使用して BAM アーカイブ、BAM スター スキーマ、および BAM 分析データベースも復元する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7fa15-116">If you restore the BAM Primary Import database from a backup, then you should also restore the BAM Archive, BAM Star Schema, and BAM Analysis databases by using a backup older than the BAM Primary backup.</span></span> <span data-ttu-id="7fa15-117">参照してください[のバックアップと復元 BAM](../core/backing-up-and-restoring-bam.md)です。</span><span class="sxs-lookup"><span data-stu-id="7fa15-117">See [Backing Up and Restoring BAM](../core/backing-up-and-restoring-bam.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7fa15-118">送信元データベースの完全バックアップまたはログ バックアップを [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のバックアップ ジョブで使用した保存場所から移動する場合は、LogFileLocation または DBFileLocation の値として、送信先システムが完全/ログ バックアップ ファイルを読み取るための新しい場所を設定します。これにより、送信先システムにある bts_LogShippingDatabases テーブルで、送信元データベースに関連付けられた行が更新されます。</span><span class="sxs-lookup"><span data-stu-id="7fa15-118">If you move the full or log backups for a source database from the location in which the Backup [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] job put them, you should update the associated row for that database in the bts_LogShippingDatabases table on the destination system by setting the LogFileLocation or DBFileLocation to the new location where the destination system should read the full/log backup files.</span></span> <span data-ttu-id="7fa15-119">bts_ConfigureBtsLogShipping ストアド プロシージャを実行すると、このテーブルに値が入力されます。</span><span class="sxs-lookup"><span data-stu-id="7fa15-119">This table is populated when you run the bts_ConfigureBtsLogShipping stored procedure.</span></span> <span data-ttu-id="7fa15-120">これらの列は既定で Null に設定されます。この値は、adm_BackupHistory テーブルに記録されている場所から送信先システムがバックアップ ファイルを読み取ることを意味します。</span><span class="sxs-lookup"><span data-stu-id="7fa15-120">By default, these columns are set to null, which indicates that the destination system should read the backup files from the location stored in the adm_BackupHistory table.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="7fa15-121">バックアップ ファイルのコピーは、常に安全な場所に保管してください。</span><span class="sxs-lookup"><span data-stu-id="7fa15-121">Always keep a copy of your backup files in a secure location.</span></span> <span data-ttu-id="7fa15-122">ログ バックアップがあっても、バックアップ ファイルがなければデータベースを復元することはできません。</span><span class="sxs-lookup"><span data-stu-id="7fa15-122">Even if you have log backups, you cannot restore your databases without the backup files.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="7fa15-123">前提条件</span><span class="sxs-lookup"><span data-stu-id="7fa15-123">Prerequisites</span></span>  
 <span data-ttu-id="7fa15-124">SQL Server ロールの sysadmin に属するアカウントを使用して、SQL Server にログインします。</span><span class="sxs-lookup"><span data-stu-id="7fa15-124">Log in to SQL Server using an account that is a member of the sysadmin SQL Server role.</span></span>  
  
### <a name="to-restore-your-databases"></a><span data-ttu-id="7fa15-125">データベースを復元するには</span><span class="sxs-lookup"><span data-stu-id="7fa15-125">To restore your databases</span></span>  
  
1.  <span data-ttu-id="7fa15-126">送信先システムで開く**SQL Server Management Studio**に接続し、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="7fa15-126">On the destination system, open **SQL Server Management Studio**, and connect to your [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)].</span></span>  
  
2.  <span data-ttu-id="7fa15-127">**[SQL Server エージェント]** を展開し、**[ジョブ]** を展開します。</span><span class="sxs-lookup"><span data-stu-id="7fa15-127">Expand **SQL Server Agent**, and expand **Jobs**.</span></span> <span data-ttu-id="7fa15-128">次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="7fa15-128">Do the following:</span></span>  
  
    1.  <span data-ttu-id="7fa15-129">右クリックし、 **BTS ログの配布 - バックアップ履歴の取得**のジョブし、選択**を無効にする**です。</span><span class="sxs-lookup"><span data-stu-id="7fa15-129">Right-click the **BTS Log Shipping - Get Backup History** job and select **Disable**.</span></span> <span data-ttu-id="7fa15-130">状態が [成功] に変わります。</span><span class="sxs-lookup"><span data-stu-id="7fa15-130">The status changes to Success.</span></span>  
  
    2.  <span data-ttu-id="7fa15-131">右クリックし、 **BTS ログの配布 - データベースの復元**のジョブし、選択**を無効にする**です。</span><span class="sxs-lookup"><span data-stu-id="7fa15-131">Right-click the **BTS Log Shipping - Restore Databases** job and select **Disable**.</span></span> <span data-ttu-id="7fa15-132">状態が [成功] に変わります。</span><span class="sxs-lookup"><span data-stu-id="7fa15-132">The status changes to Success.</span></span>  
  
    3.  <span data-ttu-id="7fa15-133">右クリックし、 **BTS ログの配布 - マークまで復元**選択**ステップでジョブを開始**です。</span><span class="sxs-lookup"><span data-stu-id="7fa15-133">Right-click the **BTS Log Shipping - Restore To Mark** and select **Start Job at Step**.</span></span> <span data-ttu-id="7fa15-134">選択**ステップ ID 1**選択**開始**です。</span><span class="sxs-lookup"><span data-stu-id="7fa15-134">Select **Step ID 1** and select **Start**.</span></span>  
  
         <span data-ttu-id="7fa15-135">状態が変わると**成功**、SQL Server エージェント ジョブと[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベースは、送信先システムに復元されます。</span><span class="sxs-lookup"><span data-stu-id="7fa15-135">When the status changes to **Success**, the SQL Server Agent jobs and [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases are restored to the destination system.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="7fa15-136">場合、**ステータス**エラー原因を特定して、メッセージ フィールドのリンクを選択します。</span><span class="sxs-lookup"><span data-stu-id="7fa15-136">If the **Status** is Error, select the link in the Message field to determine the cause.</span></span> <span data-ttu-id="7fa15-137">これらのジョブを続行するには、状態が [成功] になっていることが必要です。</span><span class="sxs-lookup"><span data-stu-id="7fa15-137">These jobs should have a Success status before continuing.</span></span>  
  
3.  <span data-ttu-id="7fa15-138">SampleUpdateInfo.xml ファイルを編集した [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] で、コマンド プロンプトを開き、次の場所に移動します。</span><span class="sxs-lookup"><span data-stu-id="7fa15-138">On the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] where you edited the SampleUpdateInfo.xml file, open a command prompt, and go to:</span></span>  
  
     <span data-ttu-id="7fa15-139">32 ビット コンピューター:`%SystemDrive%\Program Files\Microsoft BizTalk Server <version>\Schema\Restore`</span><span class="sxs-lookup"><span data-stu-id="7fa15-139">32-bit computer: `%SystemDrive%\Program Files\Microsoft BizTalk Server <version>\Schema\Restore`</span></span>  
  
     <span data-ttu-id="7fa15-140">64 ビット コンピューター:`%SystemDrive%\Program Files (x86)\Microsoft BizTalk Server <version>\Bins32\Schema\Restore`</span><span class="sxs-lookup"><span data-stu-id="7fa15-140">64-bit computer: `%SystemDrive%\Program Files (x86)\Microsoft BizTalk Server <version>\Bins32\Schema\Restore`</span></span>  
  
4.  <span data-ttu-id="7fa15-141">コマンド プロンプトで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="7fa15-141">At the command prompt, type:</span></span>  
  
     `cscript UpdateDatabase.vbs SampleUpdateInfo.xml`  
  
     <span data-ttu-id="7fa15-142">このスクリプトにより、他のデータベースの場所に関する情報を格納しているテーブルがすべて更新されます。</span><span class="sxs-lookup"><span data-stu-id="7fa15-142">This script updates all tables that store information about the location of other databases.</span></span>  
  
    > [!IMPORTANT]
    >  -   <span data-ttu-id="7fa15-143">UpdateDatabase.vbs を実行**1** BizTalk グループ内のサーバー。</span><span class="sxs-lookup"><span data-stu-id="7fa15-143">Run UpdateDatabase.vbs on **one** server in the BizTalk group.</span></span>  
    > -   <span data-ttu-id="7fa15-144">64 ビット コンピューターの場合は、UpdateDatabase.vbs を 64 ビット コマンド プロンプトから実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7fa15-144">On 64-bit computers, you must run UpdateDatabase.vbs from a 64-bit command prompt.</span></span> <span data-ttu-id="7fa15-145">64 ビット コンピューターにおける既定のコマンド プロンプトは、64 ビット コマンド プロンプト (%SystemDrive%\windows\System32\cmd.exe) であることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="7fa15-145">Note that the default command prompt on 64-bit computers is a 64-bit command prompt and is located at %SystemDrive%\windows\System32\cmd.exe.</span></span>  
    > -   <span data-ttu-id="7fa15-146">BizTalk の EDI エンジンが必要としない SampleUpdateInfo.xml 独自の変更のいずれかのデータベースを復元します。</span><span class="sxs-lookup"><span data-stu-id="7fa15-146">The BizTalk EDI engine does not require any of its own modifications to SampleUpdateInfo.xml when restoring databases.</span></span>  <span data-ttu-id="7fa15-147">これは、EDI テーブルにアクセスする、BizTalkDTADb データベースへの接続に依存します。</span><span class="sxs-lookup"><span data-stu-id="7fa15-147">It relies on connectivity to the BizTalkDTADb database to access the EDI tables.</span></span>  
  
5.  <span data-ttu-id="7fa15-148">編集した SampleUpdateInfo.xml ファイルを次のフォルダーにコピー**すべて**を実行するコンピューター[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]この BizTalk グループに。</span><span class="sxs-lookup"><span data-stu-id="7fa15-148">Copy the edited SampleUpdateInfo.xml file to the following folder on **every** computer running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] in this BizTalk group:</span></span>  
  
     <span data-ttu-id="7fa15-149">32 ビット コンピューター: にコピー`%SystemDrive%\Program Files\Microsoft BizTalk Server <version>\Schema\Restore`</span><span class="sxs-lookup"><span data-stu-id="7fa15-149">32-bit computer: Copy to `%SystemDrive%\Program Files\Microsoft BizTalk Server <version>\Schema\Restore`</span></span>  
  
     <span data-ttu-id="7fa15-150">64 ビット コンピューター: にコピー`%SystemDrive%\Program Files (x86)\Microsoft BizTalk Server <version>\Bins32\Schema\Restore`</span><span class="sxs-lookup"><span data-stu-id="7fa15-150">64-bit computer: Copy to `%SystemDrive%\Program Files (x86)\Microsoft BizTalk Server <version>\Bins32\Schema\Restore`</span></span>  
  
6.  <span data-ttu-id="7fa15-151">**各**内のコンピューター、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]グループ、コマンド プロンプトを開きに移動します。</span><span class="sxs-lookup"><span data-stu-id="7fa15-151">On **each** computer in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] group, open a command prompt, and go to:</span></span>  
  
     <span data-ttu-id="7fa15-152">32 ビット コンピューター:`%SystemDrive%\Program Files\Microsoft BizTalk Server <version>\Schema\Restore`</span><span class="sxs-lookup"><span data-stu-id="7fa15-152">32-bit computer: `%SystemDrive%\Program Files\Microsoft BizTalk Server <version>\Schema\Restore`</span></span>  
  
     <span data-ttu-id="7fa15-153">64 ビット コンピューター:`%SystemDrive%Program Files (x86)Microsoft BizTalk Server <version>Bins32SchemaRestore`</span><span class="sxs-lookup"><span data-stu-id="7fa15-153">64-bit computer: `%SystemDrive%Program Files (x86)Microsoft BizTalk Server <version>Bins32SchemaRestore`</span></span>  
  
7.  <span data-ttu-id="7fa15-154">コマンド プロンプトで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="7fa15-154">At the command prompt, type:</span></span>  
  
     `cscript UpdateRegistry.vbs SampleUpdateInfo.xml`  
  
     <span data-ttu-id="7fa15-155">このスクリプトにより、他のデータベースの場所に関する情報を格納しているすべてのレジストリ エントリが更新されます。</span><span class="sxs-lookup"><span data-stu-id="7fa15-155">This script updates all registry entries that store information about the location of other databases.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="7fa15-156">UpdateRegistry.vbs を実行**すべて**BizTalk グループ内のサーバー。</span><span class="sxs-lookup"><span data-stu-id="7fa15-156">Run UpdateRegistry.vbs on **every** server in the BizTalk group.</span></span>  
    >   
    >  <span data-ttu-id="7fa15-157">64 ビット コンピューターの場合は、UpdateRegistry.vbs を 64 ビット コマンド プロンプトから実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7fa15-157">On 64-bit computers, you must run UpdateRegistry.vbs from a 64-bit command prompt.</span></span>  <span data-ttu-id="7fa15-158">64 ビット コンピューターにおける既定のコマンド プロンプトは、64 ビット コマンド プロンプト (%SystemDrive%\windows\System32\cmd.exe) であることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="7fa15-158">Note that the default command prompt on 64-bit computers is a 64-bit command prompt and is located at %SystemDrive%\windows\System32\cmd.exe.</span></span>  
  
8.  <span data-ttu-id="7fa15-159">すべての [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] サービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="7fa15-159">Restart all the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] services.</span></span> <span data-ttu-id="7fa15-160">参照してください[サービスを開始、停止、一時停止、再開、または BizTalk Server を再起動するのにはどのように](../core/how-to-start-stop-pause-resume-or-restart-biztalk-server-services.md)です。</span><span class="sxs-lookup"><span data-stu-id="7fa15-160">See [How to Start, Stop, Pause, Resume, or Restart BizTalk Server Services](../core/how-to-start-stop-pause-resume-or-restart-biztalk-server-services.md).</span></span>  
  
9. <span data-ttu-id="7fa15-161">データベースを復元した後で、Windows Management Instrumentation サービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="7fa15-161">After restoring your databases, restart the Windows Management Instrumentation service:</span></span>  
  
    1.  <span data-ttu-id="7fa15-162">開いている**services.msc**です。</span><span class="sxs-lookup"><span data-stu-id="7fa15-162">Open **services.msc**.</span></span>  
  
    2.  <span data-ttu-id="7fa15-163">右クリック**Windows Management Instrumentation**、し、**再起動**です。</span><span class="sxs-lookup"><span data-stu-id="7fa15-163">Right-click **Windows Management Instrumentation**, and then select **Restart**.</span></span>  
  
10. <span data-ttu-id="7fa15-164">開いている**BizTalk Server 管理**です。</span><span class="sxs-lookup"><span data-stu-id="7fa15-164">Open **BizTalk Server Administration**.</span></span> <span data-ttu-id="7fa15-165">次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="7fa15-165">Do the following:</span></span>  
  
    1.  <span data-ttu-id="7fa15-166">右クリックし、 **BizTalk グループ**選択**削除**です。</span><span class="sxs-lookup"><span data-stu-id="7fa15-166">Right-click the **BizTalk Group** and select **Remove**.</span></span>  
  
    2.  <span data-ttu-id="7fa15-167">右クリック**BizTalk Server 管理コンソール**選択**既存グループに接続**です。</span><span class="sxs-lookup"><span data-stu-id="7fa15-167">Right-click **BizTalk Server Administration** and select **Connect to Existing Group**.</span></span>  
  
    3.  <span data-ttu-id="7fa15-168">**SQL Server 名**、BizTalk 管理データベースをホストする SQL Server インスタンスの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="7fa15-168">In **SQL Server name**, select the name of the SQL Server instance that hosts the BizTalk Management database.</span></span> <span data-ttu-id="7fa15-169">SQL Server インスタンスを選択すると、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] によって自動的にそのコンピューター上の [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] データベースが検出されます。</span><span class="sxs-lookup"><span data-stu-id="7fa15-169">When you select the SQL Server instance, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] automatically detects the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases on that computer.</span></span>  
  
    4.  <span data-ttu-id="7fa15-170">**データベース名**、BizTalk 管理データベースを選択 (**BizTalkMgmtDb**既定では)、し、 **OK**です。</span><span class="sxs-lookup"><span data-stu-id="7fa15-170">In **Database name**, select your BizTalk Management database (**BizTalkMgmtDb** by default), and then select **OK**.</span></span>  
  
     <span data-ttu-id="7fa15-171">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールによって、管理コンソールに BizTalk グループが追加されます。</span><span class="sxs-lookup"><span data-stu-id="7fa15-171">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console adds the BizTalk group to the Administration console.</span></span>  
  
     <span data-ttu-id="7fa15-172">これで [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] が復元され、動作します。</span><span class="sxs-lookup"><span data-stu-id="7fa15-172">Your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is now restored and should be running.</span></span> <span data-ttu-id="7fa15-173">次に、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のバックアップ ジョブを構成して、バックアップが新しい送信先サーバーに書き込まれるようにします。</span><span class="sxs-lookup"><span data-stu-id="7fa15-173">Next, configure the Backup [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] job to start writing backups to a new destination server.</span></span> <span data-ttu-id="7fa15-174">また、新しい送信先システムの再構成も必要です。</span><span class="sxs-lookup"><span data-stu-id="7fa15-174">You should also reconfigure a new destination system.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="7fa15-175">ルール エンジンを使用する場合は、データベースの復元後に、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] グループの各サーバーでルール エンジン更新サービスを再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7fa15-175">If you are using the Rules Engine, after restoring the databases, you must restart the Rule Engine Update Service on every server in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] group.</span></span> <span data-ttu-id="7fa15-176">参照してください[サービスを開始、停止、一時停止、再開、または BizTalk Server を再起動するのにはどのように](../core/how-to-start-stop-pause-resume-or-restart-biztalk-server-services.md)です。</span><span class="sxs-lookup"><span data-stu-id="7fa15-176">See [How to Start, Stop, Pause, Resume, or Restart BizTalk Server Services](../core/how-to-start-stop-pause-resume-or-restart-biztalk-server-services.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7fa15-177">BAM を使用する場合は、この時点で BAM データベースを復元してください。</span><span class="sxs-lookup"><span data-stu-id="7fa15-177">If you are using BAM, this is the time to restore the BAM databases.</span></span> <span data-ttu-id="7fa15-178">参照してください[のバックアップと復元 BAM](../core/backing-up-and-restoring-bam.md)です。</span><span class="sxs-lookup"><span data-stu-id="7fa15-178">See [Backing Up and Restoring BAM](../core/backing-up-and-restoring-bam.md).</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="7fa15-179">次の手順</span><span class="sxs-lookup"><span data-stu-id="7fa15-179">Next Steps</span></span>  
 [<span data-ttu-id="7fa15-180">バックアップおよび BAM を復元します。</span><span class="sxs-lookup"><span data-stu-id="7fa15-180">Backing Up and Restoring BAM</span></span>](../core/backing-up-and-restoring-bam.md)  
  
## <a name="see-also"></a><span data-ttu-id="7fa15-181">参照</span><span class="sxs-lookup"><span data-stu-id="7fa15-181">See Also</span></span>  
 <span data-ttu-id="7fa15-182">[バックアップの BizTalk Server ジョブを構成する方法](../core/how-to-configure-the-backup-biztalk-server-job.md) </span><span class="sxs-lookup"><span data-stu-id="7fa15-182">[How to Configure the Backup BizTalk Server Job](../core/how-to-configure-the-backup-biztalk-server-job.md) </span></span>  
 [<span data-ttu-id="7fa15-183">ログ配布用に送信先システムを構成する方法</span><span class="sxs-lookup"><span data-stu-id="7fa15-183">How to Configure the Destination System for Log Shipping</span></span>](../core/how-to-configure-the-destination-system-for-log-shipping.md)