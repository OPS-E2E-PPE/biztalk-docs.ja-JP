---
title: データベースの復元 |Microsoft Docs
description: SQL エージェント ジョブ, を使用して、UpdateDatabase.vbs と UpdateRegistry.vbs スクリプトの実行など、BizTalk Server データベースを復元する手順を参照してください。 また、BizTalk 管理コンソールで、SQL Server インスタンス名の更新を含む、データベースの復元後の対処方法を参照してください。
ms.custom: ''
ms.date: 09/30/18
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0176932a-6b3d-4502-975b-a76296189092
caps.latest.revision: 52
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c318511902b31ffbe3fab4e055bdbf097d0f6865
ms.sourcegitcommit: 51ce182c5b71d3999a3920dd884bc9ec8334a899
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2018
ms.locfileid: "48575685"
---
# <a name="how-to-restore-your-databases"></a><span data-ttu-id="7baa2-104">データベースを復元する方法</span><span class="sxs-lookup"><span data-stu-id="7baa2-104">How to Restore Your Databases</span></span>
<span data-ttu-id="7baa2-105">データベース間のトランザクション状態の一貫性を保証するには、すべてのデータベースを同じマークに復元する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7baa2-105">You must restore all databases to the same mark to ensure a consistent transactional state among the databases.</span></span> <span data-ttu-id="7baa2-106">参照してください[マークされたトランザクション、完全バックアップ、バックアップとログ バックアップ](../core/marked-transactions-full-backups-and-log-backups.md)します。</span><span class="sxs-lookup"><span data-stu-id="7baa2-106">See [Marked Transactions, Full Backups, and Log Backups](../core/marked-transactions-full-backups-and-log-backups.md).</span></span>  
  
 <span data-ttu-id="7baa2-107">送信先システムにあるサーバーが 1 つだけの場合は、(最新のセットを除く) すべてのログのバックアップ セットが復元されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="7baa2-107">If there is only one server in the destination system, make sure that all of the log backup sets (except for the most recent set) have been restored.</span></span> <span data-ttu-id="7baa2-108">参照してください[バックアップを復元の履歴を表示する](../core/viewing-the-history-of-restored-backups.md)します。</span><span class="sxs-lookup"><span data-stu-id="7baa2-108">See [Viewing the History of Restored Backups](../core/viewing-the-history-of-restored-backups.md).</span></span> <span data-ttu-id="7baa2-109">すべてのログ バックアップ セットの復元が完了していない場合、復元ジョブが現在実行中でなければ、ジョブを実行します (必要に応じて手動で)。</span><span class="sxs-lookup"><span data-stu-id="7baa2-109">If all the log backup sets have not been restored, and the restore job is not currently running, run the restore job (manually if necessary).</span></span> <span data-ttu-id="7baa2-110">復元できる未処理のバックアップ セットがある場合は、ジョブにまで処理すべて復元します。</span><span class="sxs-lookup"><span data-stu-id="7baa2-110">If there are outstanding backup sets that can be restored, the job processes them until they are all restored.</span></span>  
  
 <span data-ttu-id="7baa2-111">送信先システムに複数のサーバーがある場合は、すべてのサーバーの復元を同じバックアップ セットで行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="7baa2-111">If there are multiple servers in the destination system, all servers must be restored to the same backup set.</span></span> <span data-ttu-id="7baa2-112">各サーバーで復元の履歴を表示し、設定が復元された最新のログ バックアップが、すべてのサーバーで同じであるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="7baa2-112">View the restore history on each server and make sure that the most recent log backup set restored is the same on all servers.</span></span> <span data-ttu-id="7baa2-113">同一の最新ログ バックアップ セットで復元されていないサーバーがある場合は、そのサーバーに対する復元ジョブを手動で実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7baa2-113">If it is not, you must manually run the restore job on each server that needs the most recent log backup set restored.</span></span>  
  
 <span data-ttu-id="7baa2-114">すべてのサーバーが同じバックアップ セットになったら、最後のセットは手動で復元できます。</span><span class="sxs-lookup"><span data-stu-id="7baa2-114">After all of the servers are on the same backup set, the final set can be manually restored.</span></span>  
  
 <span data-ttu-id="7baa2-115">adm_BackupHistory テーブルは、ソース システムのログ配布プロセスの中心的な履歴ポイントです。</span><span class="sxs-lookup"><span data-stu-id="7baa2-115">The adm_BackupHistory table is the central history point for the log shipping process for the source system.</span></span> <span data-ttu-id="7baa2-116">実行されたバックアップ作業はすべてこのテーブルに記録されます。</span><span class="sxs-lookup"><span data-stu-id="7baa2-116">All backup work performed is recorded to this table.</span></span> <span data-ttu-id="7baa2-117">送信先システムにあるすべてのサーバーは、復元作業の実行に必要な情報を受け取るためにこのテーブルから読み取ります。</span><span class="sxs-lookup"><span data-stu-id="7baa2-117">All servers in your destination system read from this table to receive the information needed to perform their restore work.</span></span>  
  
> [!NOTE]
>  - <span data-ttu-id="7baa2-118">BAM プライマリ インポート データベースをバックアップから復元する場合は、BAM プライマリよりも古いバックアップを使用して BAM アーカイブ、BAM スター スキーマ、および BAM 分析データベースも復元する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7baa2-118">If you restore the BAM Primary Import database from a backup, then you should also restore the BAM Archive, BAM Star Schema, and BAM Analysis databases by using a backup older than the BAM Primary backup.</span></span> <span data-ttu-id="7baa2-119">参照してください[のバックアップと復元 BAM](../core/backing-up-and-restoring-bam.md)します。</span><span class="sxs-lookup"><span data-stu-id="7baa2-119">See [Backing Up and Restoring BAM](../core/backing-up-and-restoring-bam.md).</span></span>  
>  - <span data-ttu-id="7baa2-120">送信元データベースの完全バックアップまたはログ バックアップを BizTalk Server のバックアップ ジョブで使用した保存場所から移動する場合は、LogFileLocation または DBFileLocation の値として、送信先システムが完全/ログ バックアップ ファイルを読み取るための新しい場所を設定します。これにより、送信先システムにある bts_LogShippingDatabases テーブルで、送信元データベースに関連付けられた行が更新されます。</span><span class="sxs-lookup"><span data-stu-id="7baa2-120">If you move the full or log backups for a source database from the location in which the Backup BizTalk Server job put them, you should update the associated row for that database in the bts_LogShippingDatabases table on the destination system by setting the LogFileLocation or DBFileLocation to the new location where the destination system should read the full/log backup files.</span></span> <span data-ttu-id="7baa2-121">bts_ConfigureBtsLogShipping ストアド プロシージャを実行すると、このテーブルに値が入力されます。</span><span class="sxs-lookup"><span data-stu-id="7baa2-121">This table is populated when you run the bts_ConfigureBtsLogShipping stored procedure.</span></span> <span data-ttu-id="7baa2-122">これらの列は既定で Null に設定されます。この値は、adm_BackupHistory テーブルに記録されている場所から送信先システムがバックアップ ファイルを読み取ることを意味します。</span><span class="sxs-lookup"><span data-stu-id="7baa2-122">By default, these columns are set to null, which indicates that the destination system should read the backup files from the location stored in the adm_BackupHistory table.</span></span>  
>  - <span data-ttu-id="7baa2-123">バックアップ ファイルのコピーは、常に安全な場所に保管してください。</span><span class="sxs-lookup"><span data-stu-id="7baa2-123">Always keep a copy of your backup files in a secure location.</span></span> <span data-ttu-id="7baa2-124">ログ バックアップがあっても、バックアップ ファイルがなければデータベースを復元することはできません。</span><span class="sxs-lookup"><span data-stu-id="7baa2-124">Even if you have log backups, you cannot restore your databases without the backup files.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="7baa2-125">前提条件</span><span class="sxs-lookup"><span data-stu-id="7baa2-125">Prerequisites</span></span>  
 <span data-ttu-id="7baa2-126">SQL Server ロールの sysadmin に属するアカウントを使用して、SQL Server にログインします。</span><span class="sxs-lookup"><span data-stu-id="7baa2-126">Log in to SQL Server using an account that is a member of the sysadmin SQL Server role.</span></span>  
  
## <a name="restore-your-databases"></a><span data-ttu-id="7baa2-127">データベースを復元します。</span><span class="sxs-lookup"><span data-stu-id="7baa2-127">Restore your databases</span></span>  
  
1. <span data-ttu-id="7baa2-128">送信先システムで開く**SQL Server Management Studio**、し、SQL Server に接続します。</span><span class="sxs-lookup"><span data-stu-id="7baa2-128">On the destination system, open **SQL Server Management Studio**, and connect to your SQL Server.</span></span>  
  
2. <span data-ttu-id="7baa2-129">**[SQL Server エージェント]** を展開し、**[ジョブ]** を展開します。</span><span class="sxs-lookup"><span data-stu-id="7baa2-129">Expand **SQL Server Agent**, and expand **Jobs**.</span></span> <span data-ttu-id="7baa2-130">次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="7baa2-130">Do the following:</span></span>  
  
   1. <span data-ttu-id="7baa2-131">右クリックし、 **BTS ログの配布 - バックアップ履歴の取得**ジョブし、選択**を無効にする**します。</span><span class="sxs-lookup"><span data-stu-id="7baa2-131">Right-click the **BTS Log Shipping - Get Backup History** job and select **Disable**.</span></span> <span data-ttu-id="7baa2-132">状態が [成功] に変わります。</span><span class="sxs-lookup"><span data-stu-id="7baa2-132">The status changes to Success.</span></span>  
  
   2. <span data-ttu-id="7baa2-133">右クリックし、 **BTS ログの配布 - データベースの復元**ジョブし、選択**を無効にする**します。</span><span class="sxs-lookup"><span data-stu-id="7baa2-133">Right-click the **BTS Log Shipping - Restore Databases** job and select **Disable**.</span></span> <span data-ttu-id="7baa2-134">状態が [成功] に変わります。</span><span class="sxs-lookup"><span data-stu-id="7baa2-134">The status changes to Success.</span></span>  
  
   3. <span data-ttu-id="7baa2-135">右クリックし、 **BTS ログの配布 - マークまで復元**選択**ステップでジョブを開始**します。</span><span class="sxs-lookup"><span data-stu-id="7baa2-135">Right-click the **BTS Log Shipping - Restore To Mark** and select **Start Job at Step**.</span></span> <span data-ttu-id="7baa2-136">選択**ステップ ID 1**選択**開始**します。</span><span class="sxs-lookup"><span data-stu-id="7baa2-136">Select **Step ID 1** and select **Start**.</span></span>  
  
       <span data-ttu-id="7baa2-137">状態が変わると**成功**、BizTalk Server データベースと SQL Server エージェント ジョブが送信先システムに復元されます。</span><span class="sxs-lookup"><span data-stu-id="7baa2-137">When the status changes to **Success**, the SQL Server Agent jobs and BizTalk Server databases are restored to the destination system.</span></span>  
  
   > [!IMPORTANT]
   >  <span data-ttu-id="7baa2-138">場合、**状態**エラー原因を特定する [メッセージ] フィールドに、リンクを選択します。</span><span class="sxs-lookup"><span data-stu-id="7baa2-138">If the **Status** is Error, select the link in the Message field to determine the cause.</span></span> <span data-ttu-id="7baa2-139">これらのジョブを続行するには、状態が [成功] になっていることが必要です。</span><span class="sxs-lookup"><span data-stu-id="7baa2-139">These jobs should have a Success status before continuing.</span></span>  
  
3. <span data-ttu-id="7baa2-140">SampleUpdateInfo.xml ファイルを編集する BizTalk Server でコマンド プロンプトを開きに移動します。</span><span class="sxs-lookup"><span data-stu-id="7baa2-140">On the BizTalk Server where you edited the SampleUpdateInfo.xml file, open a command prompt, and go to:</span></span>  
  
    <span data-ttu-id="7baa2-141">32 ビット コンピューター: `%SystemDrive%\Program Files\Microsoft BizTalk Server <version>\Schema\Restore`</span><span class="sxs-lookup"><span data-stu-id="7baa2-141">32-bit computer: `%SystemDrive%\Program Files\Microsoft BizTalk Server <version>\Schema\Restore`</span></span>  
  
    <span data-ttu-id="7baa2-142">64 ビット コンピューター: `%SystemDrive%\Program Files (x86)\Microsoft BizTalk Server <version>\Bins32\Schema\Restore`</span><span class="sxs-lookup"><span data-stu-id="7baa2-142">64-bit computer: `%SystemDrive%\Program Files (x86)\Microsoft BizTalk Server <version>\Bins32\Schema\Restore`</span></span>  
  
4. <span data-ttu-id="7baa2-143">コマンド プロンプトで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="7baa2-143">At the command prompt, type:</span></span>  
  
    `cscript UpdateDatabase.vbs SampleUpdateInfo.xml`  
  
    <span data-ttu-id="7baa2-144">このスクリプトにより、他のデータベースの場所に関する情報を格納しているテーブルがすべて更新されます。</span><span class="sxs-lookup"><span data-stu-id="7baa2-144">This script updates all tables that store information about the location of other databases.</span></span>  
  
   > [!IMPORTANT]
   >  - <span data-ttu-id="7baa2-145">UpdateDatabase.vbs を実行**1 つ**BizTalk グループ内のサーバー。</span><span class="sxs-lookup"><span data-stu-id="7baa2-145">Run UpdateDatabase.vbs on **one** server in the BizTalk group.</span></span>  
   >  - <span data-ttu-id="7baa2-146">64 ビット コンピューターの場合は、UpdateDatabase.vbs を 64 ビット コマンド プロンプトから実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7baa2-146">On 64-bit computers, you must run UpdateDatabase.vbs from a 64-bit command prompt.</span></span> <span data-ttu-id="7baa2-147">64 ビット コンピューターにおける既定のコマンド プロンプトは、64 ビット コマンド プロンプト (%SystemDrive%\windows\System32\cmd.exe) であることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="7baa2-147">Note that the default command prompt on 64-bit computers is a 64-bit command prompt and is located at %SystemDrive%\windows\System32\cmd.exe.</span></span>  
   >  - <span data-ttu-id="7baa2-148">BizTalk の EDI エンジンが必要としない SampleUpdateInfo.xml 独自の変更のいずれかのデータベースを復元します。</span><span class="sxs-lookup"><span data-stu-id="7baa2-148">The BizTalk EDI engine does not require any of its own modifications to SampleUpdateInfo.xml when restoring databases.</span></span>  <span data-ttu-id="7baa2-149">これは、EDI テーブルにアクセスする、BizTalkDTADb データベースへの接続に依存します。</span><span class="sxs-lookup"><span data-stu-id="7baa2-149">It relies on connectivity to the BizTalkDTADb database to access the EDI tables.</span></span>  
  
5. <span data-ttu-id="7baa2-150">編集した SampleUpdateInfo.xml ファイルを次のフォルダーにコピー**すべて**この BizTalk グループに BizTalk Server を実行しているコンピューター。</span><span class="sxs-lookup"><span data-stu-id="7baa2-150">Copy the edited SampleUpdateInfo.xml file to the following folder on **every** computer running BizTalk Server in this BizTalk group:</span></span>  
  
    <span data-ttu-id="7baa2-151">32 ビット コンピューター: コピー `%SystemDrive%\Program Files\Microsoft BizTalk Server <version>\Schema\Restore`</span><span class="sxs-lookup"><span data-stu-id="7baa2-151">32-bit computer: Copy to `%SystemDrive%\Program Files\Microsoft BizTalk Server <version>\Schema\Restore`</span></span>  
  
    <span data-ttu-id="7baa2-152">64 ビット コンピューター: コピー `%SystemDrive%\Program Files (x86)\Microsoft BizTalk Server <version>\Bins32\Schema\Restore`</span><span class="sxs-lookup"><span data-stu-id="7baa2-152">64-bit computer: Copy to `%SystemDrive%\Program Files (x86)\Microsoft BizTalk Server <version>\Bins32\Schema\Restore`</span></span>  
  
6. <span data-ttu-id="7baa2-153">**各**BizTalk Server グループ内のコンピューターが、コマンド プロンプトを開きに移動します。</span><span class="sxs-lookup"><span data-stu-id="7baa2-153">On **each** computer in the BizTalk Server group, open a command prompt, and go to:</span></span>  
  
    <span data-ttu-id="7baa2-154">32 ビット コンピューター: `%SystemDrive%\Program Files\Microsoft BizTalk Server <version>\Schema\Restore`</span><span class="sxs-lookup"><span data-stu-id="7baa2-154">32-bit computer: `%SystemDrive%\Program Files\Microsoft BizTalk Server <version>\Schema\Restore`</span></span>  
  
    <span data-ttu-id="7baa2-155">64 ビット コンピューター: `%SystemDrive%\Program Files (x86)Microsoft BizTalk Server <version>\Bins32\Schema\Restore`</span><span class="sxs-lookup"><span data-stu-id="7baa2-155">64-bit computer: `%SystemDrive%\Program Files (x86)Microsoft BizTalk Server <version>\Bins32\Schema\Restore`</span></span>  
  
7. <span data-ttu-id="7baa2-156">コマンド プロンプトで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="7baa2-156">At the command prompt, type:</span></span>  
  
    `cscript UpdateRegistry.vbs SampleUpdateInfo.xml`  
  
    <span data-ttu-id="7baa2-157">このスクリプトにより、他のデータベースの場所に関する情報を格納しているすべてのレジストリ エントリが更新されます。</span><span class="sxs-lookup"><span data-stu-id="7baa2-157">This script updates all registry entries that store information about the location of other databases.</span></span>  
  
   > [!IMPORTANT]
   >  - <span data-ttu-id="7baa2-158">UpdateRegistry.vbs を実行**すべて**BizTalk グループ内のサーバー。</span><span class="sxs-lookup"><span data-stu-id="7baa2-158">Run UpdateRegistry.vbs on **every** server in the BizTalk group.</span></span>  
   >  - <span data-ttu-id="7baa2-159">64 ビット コンピューターの場合は、UpdateRegistry.vbs を 64 ビット コマンド プロンプトから実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7baa2-159">On 64-bit computers, you must run UpdateRegistry.vbs from a 64-bit command prompt.</span></span>  <span data-ttu-id="7baa2-160">64 ビット コンピューターにおける既定のコマンド プロンプトは、64 ビット コマンド プロンプト (%SystemDrive%\windows\System32\cmd.exe) であることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="7baa2-160">Note that the default command prompt on 64-bit computers is a 64-bit command prompt and is located at %SystemDrive%\windows\System32\cmd.exe.</span></span>  
  
8. <span data-ttu-id="7baa2-161">すべての BizTalk Server サービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="7baa2-161">Restart all the BizTalk Server services.</span></span> <span data-ttu-id="7baa2-162">参照してください[Services を開始、停止、一時停止、再開、または BizTalk Server を再起動する方法](../core/how-to-start-stop-pause-resume-or-restart-biztalk-server-services.md)します。</span><span class="sxs-lookup"><span data-stu-id="7baa2-162">See [How to Start, Stop, Pause, Resume, or Restart BizTalk Server Services](../core/how-to-start-stop-pause-resume-or-restart-biztalk-server-services.md).</span></span>  
  
9. <span data-ttu-id="7baa2-163">データベースを復元した後で、Windows Management Instrumentation サービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="7baa2-163">After restoring your databases, restart the Windows Management Instrumentation service:</span></span>  
  
    1.  <span data-ttu-id="7baa2-164">開いている**services.msc**します。</span><span class="sxs-lookup"><span data-stu-id="7baa2-164">Open **services.msc**.</span></span>  
  
    2.  <span data-ttu-id="7baa2-165">右クリックして**Windows Management Instrumentation**、し、**再起動**します。</span><span class="sxs-lookup"><span data-stu-id="7baa2-165">Right-click **Windows Management Instrumentation**, and then select **Restart**.</span></span>  
  
10. <span data-ttu-id="7baa2-166">開いている**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="7baa2-166">Open **BizTalk Server Administration**.</span></span> <span data-ttu-id="7baa2-167">次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="7baa2-167">Do the following:</span></span>  
  
    1. <span data-ttu-id="7baa2-168">右クリックし、 **BizTalk グループ**選択**削除**します。</span><span class="sxs-lookup"><span data-stu-id="7baa2-168">Right-click the **BizTalk Group** and select **Remove**.</span></span>  
  
    2. <span data-ttu-id="7baa2-169">右クリック**BizTalk Server 管理**選択**既存グループへの接続**します。</span><span class="sxs-lookup"><span data-stu-id="7baa2-169">Right-click **BizTalk Server Administration** and select **Connect to Existing Group**.</span></span>  
  
    3. <span data-ttu-id="7baa2-170">**SQL Server 名**、BizTalk 管理データベースをホストする SQL Server インスタンスの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="7baa2-170">In **SQL Server name**, select the name of the SQL Server instance that hosts the BizTalk Management database.</span></span> <span data-ttu-id="7baa2-171">SQL Server インスタンスを選択すると、BizTalk Server コンピューターに BizTalk Server データベースが自動的に検出します。</span><span class="sxs-lookup"><span data-stu-id="7baa2-171">When you select the SQL Server instance, BizTalk Server automatically detects the BizTalk Server databases on that computer.</span></span>  
  
    4. <span data-ttu-id="7baa2-172">**データベース名**、BizTalk 管理データベースを選択します (**BizTalkMgmtDb**既定で)、し、 **OK**。</span><span class="sxs-lookup"><span data-stu-id="7baa2-172">In **Database name**, select your BizTalk Management database (**BizTalkMgmtDb** by default), and then select **OK**.</span></span>  
  
       <span data-ttu-id="7baa2-173">BizTalk Server 管理コンソールでは、管理コンソールに、BizTalk グループを追加します。</span><span class="sxs-lookup"><span data-stu-id="7baa2-173">The BizTalk Server Administration console adds the BizTalk group to the Administration console.</span></span>  
  
       <span data-ttu-id="7baa2-174">BizTalk Server では、今すぐが復元され、実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7baa2-174">Your BizTalk Server is now restored and should be running.</span></span> <span data-ttu-id="7baa2-175">次に、新しい移行先サーバーへのバックアップの書き込みを開始する BizTalk Server のバックアップ ジョブを構成します。</span><span class="sxs-lookup"><span data-stu-id="7baa2-175">Next, configure the Backup BizTalk Server job to start writing backups to a new destination server.</span></span> <span data-ttu-id="7baa2-176">また、新しい送信先システムの再構成も必要です。</span><span class="sxs-lookup"><span data-stu-id="7baa2-176">You should also reconfigure a new destination system.</span></span>  

## <a name="important"></a><span data-ttu-id="7baa2-177">重要</span><span class="sxs-lookup"><span data-stu-id="7baa2-177">Important</span></span>

- <span data-ttu-id="7baa2-178">データベースを復元した後、ルール エンジンを使用する場合、BizTalk Server グループのすべてのサーバーでは、ルール エンジン更新サービスを再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7baa2-178">If you're using the Rules Engine, after restoring the databases, you must restart the Rule Engine Update Service on every server in the BizTalk Server group.</span></span> <span data-ttu-id="7baa2-179">参照してください[Services を開始、停止、一時停止、再開、または BizTalk Server を再起動する方法](../core/how-to-start-stop-pause-resume-or-restart-biztalk-server-services.md)します。</span><span class="sxs-lookup"><span data-stu-id="7baa2-179">See [How to Start, Stop, Pause, Resume, or Restart BizTalk Server Services](../core/how-to-start-stop-pause-resume-or-restart-biztalk-server-services.md).</span></span>  
- <span data-ttu-id="7baa2-180">BAM を使用している場合は、BAM データベースを復元する時間がようになりました。</span><span class="sxs-lookup"><span data-stu-id="7baa2-180">If you're using BAM, now is the time to restore the BAM databases.</span></span> <span data-ttu-id="7baa2-181">参照してください[のバックアップと復元 BAM](../core/backing-up-and-restoring-bam.md)します。</span><span class="sxs-lookup"><span data-stu-id="7baa2-181">See [Backing Up and Restoring BAM](../core/backing-up-and-restoring-bam.md).</span></span>  
- <span data-ttu-id="7baa2-182">データベースを移動する、BizTalk EDI または RosettaNet アクセラレータを使用している場合は、いくつかの SQL ポートは、BizTalk データベースに対してセットアップにする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7baa2-182">If you're moving databases and you're using BizTalk EDI or the RosettaNet accelerator, then some SQL ports may be setup against the BizTalk databases.</span></span> <span data-ttu-id="7baa2-183">バインドのエクスポート、古いデータベース リンクでは、検索し、データベースへのリンクを適宜置換します。</span><span class="sxs-lookup"><span data-stu-id="7baa2-183">Export the bindings, search for the old database links, and replace the database links accordingly.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="7baa2-184">次の手順</span><span class="sxs-lookup"><span data-stu-id="7baa2-184">Next Steps</span></span>  
 [<span data-ttu-id="7baa2-185">バックアップおよび BAM を復元します。</span><span class="sxs-lookup"><span data-stu-id="7baa2-185">Backing Up and Restoring BAM</span></span>](../core/backing-up-and-restoring-bam.md)  
  
## <a name="see-also"></a><span data-ttu-id="7baa2-186">参照</span><span class="sxs-lookup"><span data-stu-id="7baa2-186">See Also</span></span>  
 <span data-ttu-id="7baa2-187">[バックアップ BizTalk Server ジョブを構成します。](../core/how-to-configure-the-backup-biztalk-server-job.md) </span><span class="sxs-lookup"><span data-stu-id="7baa2-187">[Configure the Backup BizTalk Server Job](../core/how-to-configure-the-backup-biztalk-server-job.md) </span></span>  
 [<span data-ttu-id="7baa2-188">ログ配布用に送信先システムを構成する</span><span class="sxs-lookup"><span data-stu-id="7baa2-188">Configure the Destination System for Log Shipping</span></span>](../core/how-to-configure-the-destination-system-for-log-shipping.md)
