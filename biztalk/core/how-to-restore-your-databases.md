---
title: データベースの復元 |Microsoft Docs
description: SQL エージェント ジョブ, を使用して、UpdateDatabase.vbs と UpdateRegistry.vbs スクリプトの実行など、BizTalk Server データベースを復元する手順を参照してください。 また、BizTalk 管理コンソールで、SQL Server インスタンス名の更新を含む、データベースの復元後の対処方法を参照してください。
ms.custom: ''
ms.date: 04/22/19
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
ms.openlocfilehash: e3213b22cb82d807b392e43d09b64a24cbc519cf
ms.sourcegitcommit: 5c3994bc9ccd688f3df74e2a49f84ada4baf5dfd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "60164512"
---
# <a name="restore-your-databases---biztalk-server"></a><span data-ttu-id="a986d-104">BizTalk Server のデータベースを復元します。</span><span class="sxs-lookup"><span data-stu-id="a986d-104">Restore your databases - BizTalk Server</span></span>
<span data-ttu-id="a986d-105">データベース間のトランザクション状態の一貫性を保証するには、すべてのデータベースを同じマークに復元する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a986d-105">You must restore all databases to the same mark to ensure a consistent transactional state among the databases.</span></span> <span data-ttu-id="a986d-106">参照してください[マークされたトランザクション、完全バックアップ、バックアップとログ バックアップ](../core/marked-transactions-full-backups-and-log-backups.md)します。</span><span class="sxs-lookup"><span data-stu-id="a986d-106">See [Marked Transactions, Full Backups, and Log Backups](../core/marked-transactions-full-backups-and-log-backups.md).</span></span>  
  
 <span data-ttu-id="a986d-107">送信先システムに 1 つのサーバーがある場合は、すべての (最新のセット) を除くログのバックアップ セットが復元されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="a986d-107">If there is only one server in the destination system, make sure that all of the log backup sets (except for the most recent set) have been restored.</span></span> <span data-ttu-id="a986d-108">参照してください[バックアップを復元の履歴を表示する](../core/viewing-the-history-of-restored-backups.md)します。</span><span class="sxs-lookup"><span data-stu-id="a986d-108">See [Viewing the History of Restored Backups](../core/viewing-the-history-of-restored-backups.md).</span></span> <span data-ttu-id="a986d-109">すべてのログ バックアップ セットが復元されていないか、復元ジョブが実行されていない場合は、(手動で必要な場合)、復元ジョブを実行します。</span><span class="sxs-lookup"><span data-stu-id="a986d-109">If all the log backup sets have not been restored, and the restore job is not currently running, run the restore job (manually if necessary).</span></span> <span data-ttu-id="a986d-110">復元できる未処理のバックアップ セットがある場合は、ジョブにまで処理すべて復元します。</span><span class="sxs-lookup"><span data-stu-id="a986d-110">If there are outstanding backup sets that can be restored, the job processes them until they are all restored.</span></span>  
  
 <span data-ttu-id="a986d-111">送信先システムに複数のサーバーがある場合、同じバックアップ セットへのすべてのサーバーを復元する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a986d-111">If there are multiple servers in the destination system, all servers must be restored to the same backup set.</span></span> <span data-ttu-id="a986d-112">各サーバーで復元の履歴を表示し、設定が復元された最新のログ バックアップが、すべてのサーバーで同じであるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="a986d-112">View the restore history on each server and make sure that the most recent log backup set restored is the same on all servers.</span></span> <span data-ttu-id="a986d-113">そうでない場合は、復元された最新のログ バックアップ セットが必要な各サーバーで復元ジョブを手動で実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a986d-113">If it is not, you must manually run the restore job on each server that needs the most recent log backup set restored.</span></span>  
  
 <span data-ttu-id="a986d-114">同じバックアップ セット上のすべてのサーバーに配置されて、最終的なセットを手動で復元できます。</span><span class="sxs-lookup"><span data-stu-id="a986d-114">After all of the servers are on the same backup set, the final set can be manually restored.</span></span>  
  
 <span data-ttu-id="a986d-115">Adm_BackupHistory テーブルは、ソース システムのログ配布プロセスの中心的な履歴ポイントです。</span><span class="sxs-lookup"><span data-stu-id="a986d-115">The adm_BackupHistory table is the central history point for the log shipping process for the source system.</span></span> <span data-ttu-id="a986d-116">すべてのバックアップ実行される作業は、このテーブルに記録されます。</span><span class="sxs-lookup"><span data-stu-id="a986d-116">All backup work performed is recorded to this table.</span></span> <span data-ttu-id="a986d-117">送信先システムにあるすべてのサーバーは、復元作業を実行するための情報を受信するには、このテーブルから読み取ります。</span><span class="sxs-lookup"><span data-stu-id="a986d-117">All servers in your destination system read from this table to receive the information needed to perform their restore work.</span></span>  

## <a name="before-you-begin"></a><span data-ttu-id="a986d-118">アンインストールの準備</span><span class="sxs-lookup"><span data-stu-id="a986d-118">Before you begin</span></span>

- <span data-ttu-id="a986d-119">BAM プライマリ インポート データベースをバックアップから復元する場合は、BAM プライマリよりも古いバックアップを使用して BAM アーカイブ、BAM スター スキーマ、および BAM 分析データベースも復元する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a986d-119">If you restore the BAM Primary Import database from a backup, then you should also restore the BAM Archive, BAM Star Schema, and BAM Analysis databases by using a backup older than the BAM Primary backup.</span></span> <span data-ttu-id="a986d-120">参照してください[のバックアップと復元 BAM](../core/backing-up-and-restoring-bam.md)します。</span><span class="sxs-lookup"><span data-stu-id="a986d-120">See [Backing Up and Restoring BAM](../core/backing-up-and-restoring-bam.md).</span></span>  
- <span data-ttu-id="a986d-121">完全な移動、BizTalk Server のバックアップ ジョブがそれらに配置する場所からのソース データベースのバックアップ ログに記録するかを設定して送信先システムで bts_LogShippingDatabases テーブルでは、そのデータベースに関連付けられている行を更新する必要があります、LogFileLocation または dbfilelocation の値として、送信先システムが完全/ログ バックアップ ファイルを読み取る新しい場所にします。</span><span class="sxs-lookup"><span data-stu-id="a986d-121">If you move the full or log backups for a source database from the location in which the Backup BizTalk Server job put them, you should update the associated row for that database in the bts_LogShippingDatabases table on the destination system by setting the LogFileLocation or DBFileLocation to the new location where the destination system should read the full/log backup files.</span></span> <span data-ttu-id="a986d-122">Bts_ConfigureBtsLogShipping ストアド プロシージャを実行すると、このテーブルが設定されます。</span><span class="sxs-lookup"><span data-stu-id="a986d-122">This table is populated when you run the bts_ConfigureBtsLogShipping stored procedure.</span></span> <span data-ttu-id="a986d-123">既定では、これらの列は、送信先システムが、adm_BackupHistory テーブルに格納されている場所から、バックアップ ファイルを読み取ることを示します null に設定されます。</span><span class="sxs-lookup"><span data-stu-id="a986d-123">By default, these columns are set to null, which indicates that the destination system should read the backup files from the location stored in the adm_BackupHistory table.</span></span>  
- <span data-ttu-id="a986d-124">常に安全な場所にバックアップ ファイルのコピーを保持します。</span><span class="sxs-lookup"><span data-stu-id="a986d-124">Always keep a copy of your backup files in a secure location.</span></span> <span data-ttu-id="a986d-125">ログ バックアップがある場合でもバックアップ ファイルがない場合、データベースを復元することはできません。</span><span class="sxs-lookup"><span data-stu-id="a986d-125">Even if you have log backups, you cannot restore your databases without the backup files.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="a986d-126">前提条件</span><span class="sxs-lookup"><span data-stu-id="a986d-126">Prerequisites</span></span>  
<span data-ttu-id="a986d-127">SQL Server の sysadmin SQL Server ロールのメンバーであるアカウントを使用してにサインインします。</span><span class="sxs-lookup"><span data-stu-id="a986d-127">Sign in to SQL Server using an account that is a member of the sysadmin SQL Server role.</span></span>  
  
## <a name="restore-your-databases"></a><span data-ttu-id="a986d-128">データベースを復元します。</span><span class="sxs-lookup"><span data-stu-id="a986d-128">Restore your databases</span></span>  
  
1. <span data-ttu-id="a986d-129">送信先システムで開く**SQL Server Management Studio**、し、SQL Server に接続します。</span><span class="sxs-lookup"><span data-stu-id="a986d-129">On the destination system, open **SQL Server Management Studio**, and connect to your SQL Server.</span></span>  
  
2. <span data-ttu-id="a986d-130">展開**SQL Server エージェント**、展開と**ジョブ**します。</span><span class="sxs-lookup"><span data-stu-id="a986d-130">Expand **SQL Server Agent**, and expand **Jobs**.</span></span> <span data-ttu-id="a986d-131">次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="a986d-131">Do the following:</span></span>  
  
   1. <span data-ttu-id="a986d-132">右クリックし、 **BTS ログの配布 - バックアップ履歴の取得**ジョブし、選択**を無効にする**します。</span><span class="sxs-lookup"><span data-stu-id="a986d-132">Right-click the **BTS Log Shipping - Get Backup History** job and select **Disable**.</span></span> <span data-ttu-id="a986d-133">成功状態を変更します。</span><span class="sxs-lookup"><span data-stu-id="a986d-133">The status changes to Success.</span></span>  
  
   2. <span data-ttu-id="a986d-134">右クリックし、 **BTS ログの配布 - データベースの復元**ジョブし、選択**を無効にする**します。</span><span class="sxs-lookup"><span data-stu-id="a986d-134">Right-click the **BTS Log Shipping - Restore Databases** job and select **Disable**.</span></span> <span data-ttu-id="a986d-135">成功状態を変更します。</span><span class="sxs-lookup"><span data-stu-id="a986d-135">The status changes to Success.</span></span>  
  
   3. <span data-ttu-id="a986d-136">右クリックし、 **BTS ログの配布 - マークまで復元**選択**ステップでジョブを開始**します。</span><span class="sxs-lookup"><span data-stu-id="a986d-136">Right-click the **BTS Log Shipping - Restore To Mark** and select **Start Job at Step**.</span></span> <span data-ttu-id="a986d-137">選択**ステップ ID 1**選択**開始**します。</span><span class="sxs-lookup"><span data-stu-id="a986d-137">Select **Step ID 1** and select **Start**.</span></span>  
  
       <span data-ttu-id="a986d-138">状態が変わると**成功**、BizTalk Server データベースと SQL Server エージェント ジョブが送信先システムに復元されます。</span><span class="sxs-lookup"><span data-stu-id="a986d-138">When the status changes to **Success**, the SQL Server Agent jobs and BizTalk Server databases are restored to the destination system.</span></span>  
  
   > [!IMPORTANT]
   >  <span data-ttu-id="a986d-139">場合、**状態**エラー原因を特定する [メッセージ] フィールドに、リンクを選択します。</span><span class="sxs-lookup"><span data-stu-id="a986d-139">If the **Status** is Error, select the link in the Message field to determine the cause.</span></span> <span data-ttu-id="a986d-140">これらのジョブは、続行する前に、成功の状態が必要です。</span><span class="sxs-lookup"><span data-stu-id="a986d-140">These jobs should have a Success status before continuing.</span></span>  
  
3. <span data-ttu-id="a986d-141">SampleUpdateInfo.xml ファイルを編集する BizTalk Server でコマンド プロンプトを開きに移動します。</span><span class="sxs-lookup"><span data-stu-id="a986d-141">On the BizTalk Server where you edited the SampleUpdateInfo.xml file, open a command prompt, and go to:</span></span>  
  
    <span data-ttu-id="a986d-142">32 ビット コンピューター: `%SystemDrive%\Program Files\Microsoft BizTalk Server <version>\Schema\Restore`</span><span class="sxs-lookup"><span data-stu-id="a986d-142">32-bit computer: `%SystemDrive%\Program Files\Microsoft BizTalk Server <version>\Schema\Restore`</span></span>  
  
    <span data-ttu-id="a986d-143">64 ビット コンピューター: `%SystemDrive%\Program Files (x86)\Microsoft BizTalk Server <version>\Bins32\Schema\Restore`</span><span class="sxs-lookup"><span data-stu-id="a986d-143">64-bit computer: `%SystemDrive%\Program Files (x86)\Microsoft BizTalk Server <version>\Bins32\Schema\Restore`</span></span>  
  
4. <span data-ttu-id="a986d-144">コマンド プロンプトで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="a986d-144">At the command prompt, type:</span></span>
  
    `cscript UpdateDatabase.vbs SampleUpdateInfo.xml`

    > [!NOTE]
    > <span data-ttu-id="a986d-145">SQL Server 2016 環境を使用する場合は、UpdateDatabase.vbs で MSOLEDBSQL を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a986d-145">When using a SQL Server 2016 environment, you may need to use MSOLEDBSQL in UpdateDatabase.vbs.</span></span> <span data-ttu-id="a986d-146">UpdateDatabase.vbs に移動`conn.Provider = "SQLOLEDB"`します。</span><span class="sxs-lookup"><span data-stu-id="a986d-146">In UpdateDatabase.vbs, go to `conn.Provider = "SQLOLEDB"`.</span></span> <span data-ttu-id="a986d-147">変更`SQLOLEDB`に`MSOLEDBSQL`します。</span><span class="sxs-lookup"><span data-stu-id="a986d-147">Change `SQLOLEDB` to `MSOLEDBSQL`.</span></span> <span data-ttu-id="a986d-148">それ以外の場合、スクリプトがエラーで失敗可能性があります:`SQL Server: Invalid connection string attribute`します。</span><span class="sxs-lookup"><span data-stu-id="a986d-148">Otherwise, the script may fail with error: `SQL Server: Invalid connection string attribute`.</span></span>
    > 
    > <span data-ttu-id="a986d-149">[ダウンロード MSOLEDBSQL](https://www.microsoft.com/download/details.aspx?id=56730)します。</span><span class="sxs-lookup"><span data-stu-id="a986d-149">[Download MSOLEDBSQL](https://www.microsoft.com/download/details.aspx?id=56730).</span></span>
    > 
    > <span data-ttu-id="a986d-150">このスクリプトでは、他のデータベースの場所に関する情報を格納するすべてのテーブルを更新します。</span><span class="sxs-lookup"><span data-stu-id="a986d-150">This script updates all tables that store information about the location of other databases.</span></span>
  
    > [!IMPORTANT]
    >  - <span data-ttu-id="a986d-151">UpdateDatabase.vbs を実行**1 つ**BizTalk グループ内のサーバー。</span><span class="sxs-lookup"><span data-stu-id="a986d-151">Run UpdateDatabase.vbs on **one** server in the BizTalk group.</span></span>  
    >  - <span data-ttu-id="a986d-152">を 64 ビット コンピューターで UpdateDatabase.vbs を 64 ビット コマンド プロンプトから実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a986d-152">On 64-bit computers, you must run UpdateDatabase.vbs from a 64-bit command prompt.</span></span> <span data-ttu-id="a986d-153">64 ビット コンピューターで既定のコマンド プロンプトは 64 ビット コマンド プロンプトでは、%systemdrive%\windows\system32\cmd.exe にあることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="a986d-153">Note that the default command prompt on 64-bit computers is a 64-bit command prompt, and is located at %SystemDrive%\windows\System32\cmd.exe.</span></span>  
    >  - <span data-ttu-id="a986d-154">データベースを復元するときに SampleUpdateInfo.xml 独自の変更のいずれかの BizTalk の EDI エンジンは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="a986d-154">The BizTalk EDI engine doesn't require any of its own modifications to SampleUpdateInfo.xml when restoring databases.</span></span>  <span data-ttu-id="a986d-155">これは、EDI テーブルにアクセスする、BizTalkDTADb データベースへの接続に依存します。</span><span class="sxs-lookup"><span data-stu-id="a986d-155">It relies on connectivity to the BizTalkDTADb database to access the EDI tables.</span></span>  
  
5. <span data-ttu-id="a986d-156">編集した SampleUpdateInfo.xml ファイルを次のフォルダーにコピー**すべて**この BizTalk グループに BizTalk Server を実行しているコンピューター。</span><span class="sxs-lookup"><span data-stu-id="a986d-156">Copy the edited SampleUpdateInfo.xml file to the following folder on **every** computer running BizTalk Server in this BizTalk group:</span></span>  
  
    <span data-ttu-id="a986d-157">32 ビット コンピューター:コピーするには `%SystemDrive%\Program Files\Microsoft BizTalk Server <version>\Schema\Restore`</span><span class="sxs-lookup"><span data-stu-id="a986d-157">32-bit computer: Copy to `%SystemDrive%\Program Files\Microsoft BizTalk Server <version>\Schema\Restore`</span></span>  
  
    <span data-ttu-id="a986d-158">64 ビット コンピューター:コピーするには `%SystemDrive%\Program Files (x86)\Microsoft BizTalk Server <version>\Bins32\Schema\Restore`</span><span class="sxs-lookup"><span data-stu-id="a986d-158">64-bit computer: Copy to `%SystemDrive%\Program Files (x86)\Microsoft BizTalk Server <version>\Bins32\Schema\Restore`</span></span>  
  
6. <span data-ttu-id="a986d-159">**各**BizTalk Server グループ内のコンピューターが、コマンド プロンプトを開きに移動します。</span><span class="sxs-lookup"><span data-stu-id="a986d-159">On **each** computer in the BizTalk Server group, open a command prompt, and go to:</span></span>  
  
    <span data-ttu-id="a986d-160">32 ビット コンピューター: `%SystemDrive%\Program Files\Microsoft BizTalk Server <version>\Schema\Restore`</span><span class="sxs-lookup"><span data-stu-id="a986d-160">32-bit computer: `%SystemDrive%\Program Files\Microsoft BizTalk Server <version>\Schema\Restore`</span></span>  
  
    <span data-ttu-id="a986d-161">64 ビット コンピューター: `%SystemDrive%\Program Files (x86)Microsoft BizTalk Server <version>\Bins32\Schema\Restore`</span><span class="sxs-lookup"><span data-stu-id="a986d-161">64-bit computer: `%SystemDrive%\Program Files (x86)Microsoft BizTalk Server <version>\Bins32\Schema\Restore`</span></span>  
  
7. <span data-ttu-id="a986d-162">コマンド プロンプトで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="a986d-162">At the command prompt, type:</span></span>  
  
    `cscript UpdateRegistry.vbs SampleUpdateInfo.xml`  
  
    <span data-ttu-id="a986d-163">このスクリプトでは、他のデータベースの場所に関する情報を格納するすべてのレジストリ エントリを更新します。</span><span class="sxs-lookup"><span data-stu-id="a986d-163">This script updates all registry entries that store information about the location of other databases.</span></span>  
  
   > [!IMPORTANT]
   >  - <span data-ttu-id="a986d-164">UpdateRegistry.vbs を実行**すべて**BizTalk グループ内のサーバー。</span><span class="sxs-lookup"><span data-stu-id="a986d-164">Run UpdateRegistry.vbs on **every** server in the BizTalk group.</span></span>  
   >  - <span data-ttu-id="a986d-165">64 ビット コンピューターでは、64 ビット コマンド プロンプトから UpdateRegistry.vbs を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a986d-165">On 64-bit computers, you must run UpdateRegistry.vbs from a 64-bit command prompt.</span></span>  <span data-ttu-id="a986d-166">64 ビット コンピューターで既定のコマンド プロンプトは 64 ビット コマンド プロンプトには、%systemdrive%\windows\system32\cmd.exe にあることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="a986d-166">Note that the default command prompt on 64-bit computers is a 64-bit command prompt and is located at %SystemDrive%\windows\System32\cmd.exe.</span></span>  
  
8. <span data-ttu-id="a986d-167">すべての BizTalk Server サービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="a986d-167">Restart all the BizTalk Server services.</span></span> <span data-ttu-id="a986d-168">参照してください[Services を開始、停止、一時停止、再開、または BizTalk Server を再起動する方法](../core/how-to-start-stop-pause-resume-or-restart-biztalk-server-services.md)します。</span><span class="sxs-lookup"><span data-stu-id="a986d-168">See [How to Start, Stop, Pause, Resume, or Restart BizTalk Server Services](../core/how-to-start-stop-pause-resume-or-restart-biztalk-server-services.md).</span></span>  
  
9. <span data-ttu-id="a986d-169">データベースを復元した後、Windows Management Instrumentation サービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="a986d-169">After restoring your databases, restart the Windows Management Instrumentation service:</span></span>  
  
    1.  <span data-ttu-id="a986d-170">開いている**services.msc**します。</span><span class="sxs-lookup"><span data-stu-id="a986d-170">Open **services.msc**.</span></span>  
  
    2.  <span data-ttu-id="a986d-171">右クリックして**Windows Management Instrumentation**、し、**再起動**します。</span><span class="sxs-lookup"><span data-stu-id="a986d-171">Right-click **Windows Management Instrumentation**, and then select **Restart**.</span></span>  
  
10. <span data-ttu-id="a986d-172">開いている**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="a986d-172">Open **BizTalk Server Administration**.</span></span> <span data-ttu-id="a986d-173">次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="a986d-173">Do the following:</span></span>  
  
    1. <span data-ttu-id="a986d-174">右クリックし、 **BizTalk グループ**選択**削除**します。</span><span class="sxs-lookup"><span data-stu-id="a986d-174">Right-click the **BizTalk Group** and select **Remove**.</span></span>  
  
    2. <span data-ttu-id="a986d-175">右クリック**BizTalk Server 管理**選択**既存グループへの接続**します。</span><span class="sxs-lookup"><span data-stu-id="a986d-175">Right-click **BizTalk Server Administration** and select **Connect to Existing Group**.</span></span>  
  
    3. <span data-ttu-id="a986d-176">**SQL Server 名**、BizTalk 管理データベースをホストする SQL Server インスタンスの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="a986d-176">In **SQL Server name**, select the name of the SQL Server instance that hosts the BizTalk Management database.</span></span> <span data-ttu-id="a986d-177">SQL Server インスタンスを選択すると、BizTalk Server コンピューターに BizTalk Server データベースが自動的に検出します。</span><span class="sxs-lookup"><span data-stu-id="a986d-177">When you select the SQL Server instance, BizTalk Server automatically detects the BizTalk Server databases on that computer.</span></span>  
  
    4. <span data-ttu-id="a986d-178">**データベース名**、BizTalk 管理データベースを選択します (**BizTalkMgmtDb**既定で)、し、 **OK**。</span><span class="sxs-lookup"><span data-stu-id="a986d-178">In **Database name**, select your BizTalk Management database (**BizTalkMgmtDb** by default), and then select **OK**.</span></span>  
  
       <span data-ttu-id="a986d-179">BizTalk Server 管理コンソールでは、管理コンソールに、BizTalk グループを追加します。</span><span class="sxs-lookup"><span data-stu-id="a986d-179">The BizTalk Server Administration console adds the BizTalk group to the Administration console.</span></span>  
  
       <span data-ttu-id="a986d-180">BizTalk Server では、今すぐが復元され、実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a986d-180">Your BizTalk Server is now restored and should be running.</span></span> <span data-ttu-id="a986d-181">次に、新しい移行先サーバーへのバックアップの書き込みを開始する BizTalk Server のバックアップ ジョブを構成します。</span><span class="sxs-lookup"><span data-stu-id="a986d-181">Next, configure the Backup BizTalk Server job to start writing backups to a new destination server.</span></span> <span data-ttu-id="a986d-182">新しい送信先システムを再構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a986d-182">You should also reconfigure a new destination system.</span></span>  

## <a name="important"></a><span data-ttu-id="a986d-183">重要</span><span class="sxs-lookup"><span data-stu-id="a986d-183">Important</span></span>

- <span data-ttu-id="a986d-184">データベースを復元した後、ルール エンジンを使用する場合、BizTalk Server グループのすべてのサーバーでは、ルール エンジン更新サービスを再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a986d-184">If you're using the Rules Engine, after restoring the databases, you must restart the Rule Engine Update Service on every server in the BizTalk Server group.</span></span> <span data-ttu-id="a986d-185">参照してください[Services を開始、停止、一時停止、再開、または BizTalk Server を再起動する方法](../core/how-to-start-stop-pause-resume-or-restart-biztalk-server-services.md)します。</span><span class="sxs-lookup"><span data-stu-id="a986d-185">See [How to Start, Stop, Pause, Resume, or Restart BizTalk Server Services](../core/how-to-start-stop-pause-resume-or-restart-biztalk-server-services.md).</span></span>  
- <span data-ttu-id="a986d-186">BAM を使用している場合は、BAM データベースを復元する時間がようになりました。</span><span class="sxs-lookup"><span data-stu-id="a986d-186">If you're using BAM, now is the time to restore the BAM databases.</span></span> <span data-ttu-id="a986d-187">参照してください[のバックアップと復元 BAM](../core/backing-up-and-restoring-bam.md)します。</span><span class="sxs-lookup"><span data-stu-id="a986d-187">See [Backing Up and Restoring BAM](../core/backing-up-and-restoring-bam.md).</span></span>  
- <span data-ttu-id="a986d-188">データベースを移動する、BizTalk EDI または RosettaNet アクセラレータを使用している場合は、いくつかの SQL ポートは、BizTalk データベースに対してセットアップにする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a986d-188">If you're moving databases and you're using BizTalk EDI or the RosettaNet accelerator, then some SQL ports may be setup against the BizTalk databases.</span></span> <span data-ttu-id="a986d-189">バインドのエクスポート、古いデータベース リンクでは、検索し、データベースへのリンクを適宜置換します。</span><span class="sxs-lookup"><span data-stu-id="a986d-189">Export the bindings, search for the old database links, and replace the database links accordingly.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="a986d-190">次の手順</span><span class="sxs-lookup"><span data-stu-id="a986d-190">Next Steps</span></span>  
 [<span data-ttu-id="a986d-191">BAM のバックアップと復元</span><span class="sxs-lookup"><span data-stu-id="a986d-191">Backing Up and Restoring BAM</span></span>](../core/backing-up-and-restoring-bam.md)  
  
## <a name="see-also"></a><span data-ttu-id="a986d-192">参照</span><span class="sxs-lookup"><span data-stu-id="a986d-192">See Also</span></span>  

 <span data-ttu-id="a986d-193">[バックアップ BizTalk Server ジョブを構成します。](../core/how-to-configure-the-backup-biztalk-server-job.md) </span><span class="sxs-lookup"><span data-stu-id="a986d-193">[Configure the Backup BizTalk Server Job](../core/how-to-configure-the-backup-biztalk-server-job.md) </span></span>  
 [<span data-ttu-id="a986d-194">ログ配布用に送信先システムを構成する</span><span class="sxs-lookup"><span data-stu-id="a986d-194">Configure the Destination System for Log Shipping</span></span>](../core/how-to-configure-the-destination-system-for-log-shipping.md)

