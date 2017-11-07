---
title: "バックアップの BizTalk Server のジョブを構成する |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/02/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 026622c9-fcb4-4db0-af48-1379feb30372
caps.latest.revision: "42"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 67765cfacc7753d649c14677c5399e9c2c7b1e39
ms.sourcegitcommit: 6095645d541bf84f39ff5f342f782284c22e875b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/06/2017
---
# <a name="configure-the-backup-biztalk-server-job"></a><span data-ttu-id="ad26d-102">バックアップの BizTalk Server のジョブを構成します。</span><span class="sxs-lookup"><span data-stu-id="ad26d-102">Configure the Backup BizTalk Server Job</span></span>
<span data-ttu-id="ad26d-103">BizTalk Server のバックアップ ジョブを構成するための手順を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="ad26d-103">Lists the steps necessary to configure the Backup BizTalk Server job.</span></span>  

## <a name="overview"></a><span data-ttu-id="ad26d-104">概要</span><span class="sxs-lookup"><span data-stu-id="ad26d-104">Overview</span></span>
<span data-ttu-id="ad26d-105">インストールし、BizTalk Server を構成した後は、バックアップを構成する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データをバックアップするジョブです。</span><span class="sxs-lookup"><span data-stu-id="ad26d-105">After you install and configure BizTalk Server, configure the Backup [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] job to back up your data.</span></span> <span data-ttu-id="ad26d-106">**Backup BizTalk Server (BizTalkMgmtDb)**ジョブには、次の手順が含まれています。</span><span class="sxs-lookup"><span data-stu-id="ad26d-106">The **Backup BizTalk Server (BizTalkMgmtDb)** job includes the following steps:</span></span>

-   <span data-ttu-id="ad26d-107">手順 1 –**セット圧縮オプション**: を有効にするか、バックアップ中に圧縮を無効にします。</span><span class="sxs-lookup"><span data-stu-id="ad26d-107">Step 1 – **Set Compression Option**: Enable or disable compression during backup</span></span>

-   <span data-ttu-id="ad26d-108">手順 2 – **BackupFull**: 完全なデータベース、BizTalk Server データベースのバックアップの実行</span><span class="sxs-lookup"><span data-stu-id="ad26d-108">Step 2 – **BackupFull**: Runs full database backups of the BizTalk Server databases</span></span>

-   <span data-ttu-id="ad26d-109">手順 3 – **MarkAndBackUpLog**: BizTalk Server データベースのログ バックアップ</span><span class="sxs-lookup"><span data-stu-id="ad26d-109">Step 3 – **MarkAndBackUpLog**: Backs up the BizTalk Server database logs</span></span>

-   <span data-ttu-id="ad26d-110">手順 4 –**バックアップ履歴をクリア**: バックアップ履歴が保持される期間を選択</span><span class="sxs-lookup"><span data-stu-id="ad26d-110">Step 4 – **Clear Backup History**: Choose how long the backup history is kept</span></span>

<span data-ttu-id="ad26d-111">このジョブを構成するのには、する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ad26d-111">To configure this job, you'll need to:</span></span>  
  
-   <span data-ttu-id="ad26d-112">プライマリ サーバーと移行先の SQL Server とその他のバックアップ オプションを確認します。</span><span class="sxs-lookup"><span data-stu-id="ad26d-112">Identify the primary and destination SQL Servers and other backup options</span></span>
  
-   <span data-ttu-id="ad26d-113">データベースをバックアップし、このアカウントの SQL Server ログインを作成する Windows ユーザー アカウントを選択します。</span><span class="sxs-lookup"><span data-stu-id="ad26d-113">Choose a Windows user account to back up your databases and create a SQL Server login for this account</span></span>
  
-   <span data-ttu-id="ad26d-114">SQL Server ログインを BizTalk Server データベース内の BTS_BACKUP_USERS データベース ロールにマップします。</span><span class="sxs-lookup"><span data-stu-id="ad26d-114">Map SQL Server logins to the BTS_BACKUP_USERS database role in the BizTalk Server databases</span></span>
  
-   <span data-ttu-id="ad26d-115">すべてのノードで MSDTC サービスをアクティブにします。</span><span class="sxs-lookup"><span data-stu-id="ad26d-115">Ensure MSDTC service is active on all nodes.</span></span> <span data-ttu-id="ad26d-116">それ以外の場合、失敗したソース ノードと送信先ノードの間のリンク サーバーを追加します。</span><span class="sxs-lookup"><span data-stu-id="ad26d-116">Else, adding a linked server between the source node and the destination node fails</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="ad26d-117">アンインストールの準備</span><span class="sxs-lookup"><span data-stu-id="ad26d-117">Before you begin</span></span>  
  
-   <span data-ttu-id="ad26d-118">特定の構成およびバックアップ操作には、sysadmin SQL Server ロールのメンバーシップが必要とします。</span><span class="sxs-lookup"><span data-stu-id="ad26d-118">Certain configuration and backup operations require membership in the sysadmin SQL Server role.</span></span> <span data-ttu-id="ad26d-119">バックアップするには、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース、プライマリ サーバーが SQL Server の sysadmin サーバー ロールのメンバーであるアカウントでサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ad26d-119">To back up your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases, you must be signed in the primary server with an account that is a member of the SQL Server sysadmin Server role.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="ad26d-120">構成では、BTS_BACKUP_USERS データベース ロールを追加します。</span><span class="sxs-lookup"><span data-stu-id="ad26d-120"> configuration adds the BTS_BACKUP_USERS database role.</span></span> <span data-ttu-id="ad26d-121">データベースをバックアップに使用するユーザー アカウントには、プライマリ サーバーを除く、バックアップには、関連するすべての SQL Server のシステム管理者 (sysadmin SQL Server ロール) のアクセス許可は不要です。</span><span class="sxs-lookup"><span data-stu-id="ad26d-121">The user account you use to back up your databases does not require System Administrator (sysadmin SQL Server role) permissions on all the SQL Servers that may be involved in a backup, except for the primary server.</span></span>  
  
-   <span data-ttu-id="ad26d-122">実行に使用するサインイン アカウントを決める、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベースのバックアップ。</span><span class="sxs-lookup"><span data-stu-id="ad26d-122">Decide which sign in account you use to run your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] database backups.</span></span> <span data-ttu-id="ad26d-123">ローカル アカウントを使用できます。複数のアカウントを使用できますが、通常は、この目的に限定した専用の Windows ドメイン ユーザー アカウントを 1 つ作成する方が簡単で安全です。</span><span class="sxs-lookup"><span data-stu-id="ad26d-123">You can use a local account, and you can use more than one account, but it is generally simpler and more secure to create one dedicated Windows domain user account specifically for this purpose.</span></span> <span data-ttu-id="ad26d-124">このユーザー用の SQL Server ログオン アカウントを構成し、バックアップ プロセスに参加するすべての SQL Server について、プライマリ (送信元) サーバーかセカンダリ (送信先) サーバーかにかかわらず、ユーザーを SQL Server ログインにマップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ad26d-124">You must configure a SQL Server logon account for this user, and the user must be mapped to a SQL Server login for all of the SQL Servers that participate in the backup process, either as primary (source) or secondary (destination) servers.</span></span> <span data-ttu-id="ad26d-125">各 BizTalk BTS_BACKUP_USERS データベース ロールにこのユーザーを割り当てる、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]をバックアップするデータベースします。</span><span class="sxs-lookup"><span data-stu-id="ad26d-125">Assign this user to the BizTalk BTS_BACKUP_USERS database role for each of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases you back up.</span></span>  
  
-   <span data-ttu-id="ad26d-126">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のバックアップ ジョブでは、期限切れのバックアップ ファイルが削除されないので、ディスク領域を節約するにはこれらのバックアップ ファイルを手動で管理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ad26d-126">The Backup [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] job does not delete outdated backup files, so you need to manually manage those backup files to conserve disk space.</span></span> <span data-ttu-id="ad26d-127">データベースの完全バックアップを新規作成した後で、プライマリ ディスクの領域を再利用できるように、期限切れのバックアップ ファイルをアーカイブ ストレージ デバイスに移動します。</span><span class="sxs-lookup"><span data-stu-id="ad26d-127">After you have created a new full backup of your databases, you should move the outdated backup files onto an archival storage device to reclaim space on the primary disk.</span></span> <span data-ttu-id="ad26d-128">参照してください、 [SSIS パッケージ](http://www.biztalkbill.com/2015/05/26/ssis-packages-to-help-management-biztalk-server-environments/)をこれらのファイルを管理します。</span><span class="sxs-lookup"><span data-stu-id="ad26d-128">See the [SSIS packages](http://www.biztalkbill.com/2015/05/26/ssis-packages-to-help-management-biztalk-server-environments/) to manage these files.</span></span>  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="ad26d-129">BizTalk 追跡データベースに直接追跡データは書き込まれませんなくメッセージ ボックス データベースにデータをキャッシュしてから、BizTalk 追跡データベースに移動します。</span><span class="sxs-lookup"><span data-stu-id="ad26d-129"> does not write tracking data directly to the BizTalk Tracking database; rather it caches the data in the MessageBox database, and then moves it to the BizTalk Tracking database.</span></span> <span data-ttu-id="ad26d-130">メッセージ ボックス データの損失が発生した場合は、追跡データも一部が失われている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ad26d-130">If MessageBox data loss occurs, some tracking data may also be lost.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="ad26d-131">前提条件</span><span class="sxs-lookup"><span data-stu-id="ad26d-131">Prerequisites</span></span>  
* <span data-ttu-id="ad26d-132">SQL Server の sysadmin SQL Server ロールのメンバーであるアカウントを使用してにサインインします。</span><span class="sxs-lookup"><span data-stu-id="ad26d-132">Sign in to SQL Server using an account that is a member of the sysadmin SQL Server role.</span></span>  
  
* <span data-ttu-id="ad26d-133">SQL Server エージェント サービスは、SQL Server の各インスタンス上にユーザー ログインがマップされたドメイン アカウントまたはローカル アカウントで実行されるように構成します。ローカル アカウントも使用できますが、ドメイン アカウントの使用をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ad26d-133">Configure the SQL Server Agent service to run under a domain account (recommended, although local accounts can be used), with a mapped user login on each instance of SQL Server.</span></span>  
  
## <a name="configure-the-job"></a><span data-ttu-id="ad26d-134">ジョブを構成します。</span><span class="sxs-lookup"><span data-stu-id="ad26d-134">Configure the job</span></span>  
  
1.  <span data-ttu-id="ad26d-135">BizTalk 管理データベースをホストする SQL Server で開く**SQL Server Management Studio**に接続し、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="ad26d-135">On the SQL Server that hosts the BizTalk Management database, open **SQL Server Management Studio**, and connect to your [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)].</span></span>  
  
2.  <span data-ttu-id="ad26d-136">**[SQL Server エージェント]** を展開し、**[ジョブ]** を展開します。</span><span class="sxs-lookup"><span data-stu-id="ad26d-136">Expand **SQL Server Agent**, and expand **Jobs**.</span></span>  
  
3.  <span data-ttu-id="ad26d-137">右クリック**Backup BizTalk Server (BizTalkMgmtDb)**選択**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="ad26d-137">Right-click **Backup BizTalk Server (BizTalkMgmtDb)** and select **Properties**.</span></span> <span data-ttu-id="ad26d-138">ジョブのプロパティで選択**手順**です。</span><span class="sxs-lookup"><span data-stu-id="ad26d-138">In the job properties, select **Steps**.</span></span>  
  
4.  <span data-ttu-id="ad26d-139">選択、 **Set Compression Option**ステップ、および選択**編集**:</span><span class="sxs-lookup"><span data-stu-id="ad26d-139">Select the **Set Compression Option** step, and select **Edit**:</span></span>  

    <span data-ttu-id="ad26d-140">このステップでは、`sp_SetBackupCompression`ストアド プロシージャに値を設定する BizTalk 管理データベース (BizTalkMgmtDb) で、`adm_BackupSettings`テーブル。</span><span class="sxs-lookup"><span data-stu-id="ad26d-140">This step calls the `sp_SetBackupCompression` stored procedure in the BizTalk management database (BizTalkMgmtDb) to set the value on the `adm_BackupSettings` table.</span></span> <span data-ttu-id="ad26d-141">ストアド プロシージャが 1 つのパラメーター:  **@bCompression**です。</span><span class="sxs-lookup"><span data-stu-id="ad26d-141">The stored procedure has one parameter: **@bCompression**.</span></span> <span data-ttu-id="ad26d-142">既定では、その設定は**0** (バックアップの圧縮がオフ)。</span><span class="sxs-lookup"><span data-stu-id="ad26d-142">By default, it is set to **0** (backup compression is off).</span></span> <span data-ttu-id="ad26d-143">圧縮を適用する値に変更**1**:</span><span class="sxs-lookup"><span data-stu-id="ad26d-143">To apply compression, change the value to **1**:</span></span>  
  
    ```  
    exec [dbo].[sp_SetBackupCompression] @bCompression = 1 /*0 - Do not use Compression, 1 - Use Compression */  
    ```  
  
     <span data-ttu-id="ad26d-144">**[ OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ad26d-144">Select **OK**.</span></span>  
  
5.  <span data-ttu-id="ad26d-145">選択、 **BackupFull**ステップ、および選択**編集**です。</span><span class="sxs-lookup"><span data-stu-id="ad26d-145">Select the **BackupFull** step, and select **Edit**.</span></span> <span data-ttu-id="ad26d-146">**コマンド**ボックスで、パラメーター値を更新します。</span><span class="sxs-lookup"><span data-stu-id="ad26d-146">In the **Command** box, update the parameter values:</span></span>  
  
    1. <span data-ttu-id="ad26d-147">**頻度**: 既定値は**d** (毎日) です。 これは推奨される設定です。</span><span class="sxs-lookup"><span data-stu-id="ad26d-147">**Frequency**: The default is **d** (daily); which is the recommended setting.</span></span> <span data-ttu-id="ad26d-148">その他の値を含める**h** (1 時間ごと)、 **w** (毎週)、 **m** (毎月)、または**y** (毎年)。</span><span class="sxs-lookup"><span data-stu-id="ad26d-148">Other values include **h** (hourly), **w** (weekly), **m** (monthly), or **y** (yearly).</span></span>  
  
    2. <span data-ttu-id="ad26d-149">**名前**: 既定値は**BTS**です。</span><span class="sxs-lookup"><span data-stu-id="ad26d-149">**Name**: The default is **BTS**.</span></span> <span data-ttu-id="ad26d-150">この名前は、バックアップ ファイル名の一部として使用されます。</span><span class="sxs-lookup"><span data-stu-id="ad26d-150">The name is used as part of the backup file name.</span></span>  
  
    3. <span data-ttu-id="ad26d-151">**バックアップ ファイルの場所**: 置換 '*\<先のパス >*' 完全なパス (パスは、単一引用符を含める必要があります) へのバックアップを作成するフォルダー、コンピューター、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース。</span><span class="sxs-lookup"><span data-stu-id="ad26d-151">**Location of backup files**: Replace '*\<destination path>*' with the full path (the path must include the single quotes) to the computer and folder where you want to back up the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases.</span></span>  

        > [!IMPORTANT]
        >  - <span data-ttu-id="ad26d-152">ローカルのパスを入力するかどうかは、ターゲット システム上の同じフォルダーにすべてのファイルを手動でコピーする必要があるされるたびにバックアップ[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ジョブを新しいファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="ad26d-152">If you enter a local path, then you have to manually copy all the files to the same folder on the destination system whenever the Backup [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] job creates new files.</span></span>  
        >   
        >      <span data-ttu-id="ad26d-153">リモート パスを指定するには、UNC 共有をように入力\\ \\  *\<ServerName >*\\*\<SharedDrive >* \\、ここで *\<ServerName >* 、ファイル サーバーの名前を指定し、  *\<SharedDrive >*共有ドライブまたはフォルダーの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="ad26d-153">To specify a remote path, enter a UNC share such as \\\\*\<ServerName>*\\*\<SharedDrive>*\\, where *\<ServerName>* is the name of the server where you want the files, and *\<SharedDrive>* is name of the shared drive or folder.</span></span>  
        >   
        >      <span data-ttu-id="ad26d-154">ネットワーク経由でデータをバックアップする場合は、ネットワークの影響を受けます。</span><span class="sxs-lookup"><span data-stu-id="ad26d-154">Backing up data over a network is subject to any network issues.</span></span> <span data-ttu-id="ad26d-155">リモートの場所を使用する場合は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のバックアップ ジョブの完了時にバックアップが成功したかどうか確認します。</span><span class="sxs-lookup"><span data-stu-id="ad26d-155">When using a remote location, verify the backup succeeded when the Backup [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] job finishes.</span></span>  
        > - <span data-ttu-id="ad26d-156">データ損失の可能性を回避するには、バックアップ ディスクを、データベースのデータ ディスクおよびログ ディスクとは異なるディスクに構成します。</span><span class="sxs-lookup"><span data-stu-id="ad26d-156">To avoid potential data loss, configure the backup disk to be a different disk than the database data and log disks.</span></span> <span data-ttu-id="ad26d-157">これは、データやログのディスクに障害が発生した場合にバックアップにアクセスするために必須です。</span><span class="sxs-lookup"><span data-stu-id="ad26d-157">This is necessary so you can access the backups if the data or log disk fails.</span></span>  

    4. <span data-ttu-id="ad26d-158">省略可。</span><span class="sxs-lookup"><span data-stu-id="ad26d-158">Optional.</span></span> <span data-ttu-id="ad26d-159">**部分バックアップ障害の後に完全バックアップの force** (@ForceFullBackupAfterPartialSetFailure): 既定値は**0**します。</span><span class="sxs-lookup"><span data-stu-id="ad26d-159">**Force full backup after partial backup failures** (@ForceFullBackupAfterPartialSetFailure): The default is **0**.</span></span> <span data-ttu-id="ad26d-160">ログのバックアップに失敗した場合、次の完全バックアップの間隔に到達するまで、完全バックアップは実行されませんでした。</span><span class="sxs-lookup"><span data-stu-id="ad26d-160">If a log backup fails, no full backups are ran until the next full backup frequency interval is reached.</span></span> <span data-ttu-id="ad26d-161">置き換える**1**ログ バックアップの失敗が発生するたびに、完全バックアップが実行された場合。</span><span class="sxs-lookup"><span data-stu-id="ad26d-161">Replace with **1** if you want a full backup ran whenever a log backup failure occurs.</span></span>
    
    5. <span data-ttu-id="ad26d-162">省略可。</span><span class="sxs-lookup"><span data-stu-id="ad26d-162">Optional.</span></span> <span data-ttu-id="ad26d-163">**バックアップ プロセスの実行のローカル時刻を 1 時間**: 既定値は NULL です。</span><span class="sxs-lookup"><span data-stu-id="ad26d-163">**Local time hour for the backup process to run**: The default is NULL.</span></span> <span data-ttu-id="ad26d-164">バックアップ ジョブに関連付けられていないのタイム ゾーン、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]時刻 (0000) のコンピューター、および午前 0 時 (utc) で実行されます。</span><span class="sxs-lookup"><span data-stu-id="ad26d-164">The backup job is not associated with the time zone of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computer, and runs at midnight UTC time (0000).</span></span> <span data-ttu-id="ad26d-165">する場合のタイム ゾーンでの特定の時間にバックアップ、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]コンピューター、整数値 0 (深夜) から 23 (11 PM) として入力のローカル時刻の時間、 **BackupHour**パラメーター。</span><span class="sxs-lookup"><span data-stu-id="ad26d-165">If you want to backup at a specific hour in the time zone of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computer, enter an integer value from 0 (midnight) to 23 (11 PM) as the local time hour for the **BackupHour** parameter.</span></span> 

    6. <span data-ttu-id="ad26d-166">省略可。</span><span class="sxs-lookup"><span data-stu-id="ad26d-166">Optional.</span></span> <span data-ttu-id="ad26d-167">**ローカル時刻を使用して**(@UseLocalTime): ローカル時刻を使用する手順を示します。</span><span class="sxs-lookup"><span data-stu-id="ad26d-167">**Use local time** (@UseLocalTime): Tells the procedure to use local time.</span></span> <span data-ttu-id="ad26d-168">既定値は 0 であり、現在の UTC 時刻 – GETUTCDATE() – 2007-05-04 01:34:11.933 を使用します。</span><span class="sxs-lookup"><span data-stu-id="ad26d-168">The default value is 0, and uses current UTC time – GETUTCDATE() – 2007-05-04 01:34:11.933.</span></span> <span data-ttu-id="ad26d-169">かどうか 1 に設定を使用してローカル時刻 – GETDATE() – 2007-05-03 18:34:11.933</span><span class="sxs-lookup"><span data-stu-id="ad26d-169">If set to 1, then it uses local time – GETDATE() – 2007-05-03 18:34:11.933</span></span>
  
    <span data-ttu-id="ad26d-170">次の例では、毎日のバックアップが午前 2 は、作成され、m:\ ドライブに格納されています。</span><span class="sxs-lookup"><span data-stu-id="ad26d-170">In the following example, daily backups are created at 2am, and stored in the m:\ drive:</span></span>  
  
    ```  
    exec [dbo].[sp_BackupAllFull_Schedule]   
    'd' /* Frequency */,   
    'BTS' /* Name */,   
    'm:\BizTalkBackups' /* location of backup files */,   
    0 /* 0 (default) or 1 ForceFullBackupAfterPartialSetFailure */,   
    '2' /* local time hour for the backup process to run */  
    ```  
  
     <span data-ttu-id="ad26d-171">**[ OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ad26d-171">Select **OK**.</span></span>  
  
6.  <span data-ttu-id="ad26d-172">選択、 **MarkAndBackupLog**ステップ、および選択**編集**です。</span><span class="sxs-lookup"><span data-stu-id="ad26d-172">Select the **MarkAndBackupLog** step, and select **Edit**.</span></span> <span data-ttu-id="ad26d-173">**コマンド**ボックスで、パラメーター値を更新します。</span><span class="sxs-lookup"><span data-stu-id="ad26d-173">In the **Command** box, update the parameter values:</span></span>  
  
    1.  <span data-ttu-id="ad26d-174">**@MarkName**: これは、バックアップ ファイルの名前付け規則の一部: <Server Name>  _<Database Name> **_ログ_**< Log Mark Name >_<Timestamp></span><span class="sxs-lookup"><span data-stu-id="ad26d-174">**@MarkName**: This is part of the naming convention for backup files: <Server Name>_<Database Name>**_Log_**< Log Mark Name >_<Timestamp></span></span>  
    
    2.  <span data-ttu-id="ad26d-175">**@BackupPath**: 完全な宛先 (単一引用符を含む)、コンピューターおよびフォルダー パスに格納する、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース ログ。</span><span class="sxs-lookup"><span data-stu-id="ad26d-175">**@BackupPath**: Full destination path (including single quotes) to the computer and folder where you want to store the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] database logs.</span></span> <span data-ttu-id="ad26d-176">*\<先のパス >*ローカル パスまたは別のサーバーへの UNC パスになる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ad26d-176">The *\<destination path>* may be local or a UNC path to another server.</span></span>  
  
     <span data-ttu-id="ad26d-177">MarkAndBackupLog ステップで、バックアップのログをマークした後、バックアップします。</span><span class="sxs-lookup"><span data-stu-id="ad26d-177">The MarkAndBackupLog step marks the logs for backup, and then backs them up.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="ad26d-178">回避する**データ損失の可能性**および**パフォーマンスを向上させる**、 *\<先のパス >*別のコンピューター、またはハード ドライブに設定する必要があります元のデータベース ログを格納するために使用されると異なる。</span><span class="sxs-lookup"><span data-stu-id="ad26d-178">To avoid **potential data loss** and for **performance improvement**, the *\<destination path>* should be set to a different computer, or hard drive, different from what is used to store the original database logs.</span></span>  
  
     <span data-ttu-id="ad26d-179">**[ OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ad26d-179">Select **OK**.</span></span>  
  
7.  <span data-ttu-id="ad26d-180">選択、 **Clear Backup History**ステップ、および選択**編集**です。</span><span class="sxs-lookup"><span data-stu-id="ad26d-180">Select the **Clear Backup History** step, and select **Edit**.</span></span> <span data-ttu-id="ad26d-181">**コマンド**ボックスで、パラメーター値を更新します。</span><span class="sxs-lookup"><span data-stu-id="ad26d-181">In the **Command** box, update the parameter values:</span></span>  
  
    1.  <span data-ttu-id="ad26d-182">**@DaysToKeep**: 既定値は**14 日間**です。</span><span class="sxs-lookup"><span data-stu-id="ad26d-182">**@DaysToKeep**: Default value is **14 days**.</span></span> <span data-ttu-id="ad26d-183">バックアップ履歴が保持される期間決定、`Adm_BackupHistory`テーブル。</span><span class="sxs-lookup"><span data-stu-id="ad26d-183">Determines how long the backup history is kept in the `Adm_BackupHistory` table.</span></span> <span data-ttu-id="ad26d-184">管理は、定期的にバックアップ履歴の消去、`Adm_BackupHistory`適切なサイズにテーブルです。</span><span class="sxs-lookup"><span data-stu-id="ad26d-184">Periodically clearing the backup history helps maintain the `Adm_BackupHistory` table to an appropriate size.</span></span> 
    
    2.  <span data-ttu-id="ad26d-185">省略可。</span><span class="sxs-lookup"><span data-stu-id="ad26d-185">Optional.</span></span> <span data-ttu-id="ad26d-186">**@UseLocalTime**: ローカル時刻を使用する手順を説明します。</span><span class="sxs-lookup"><span data-stu-id="ad26d-186">**@UseLocalTime**: Tells the procedure to use local time.</span></span> <span data-ttu-id="ad26d-187">既定値は 0 です。</span><span class="sxs-lookup"><span data-stu-id="ad26d-187">The default value is 0.</span></span> <span data-ttu-id="ad26d-188">現在の UTC 時刻 – GETUTCDATE() – 2007-05-04 01:34:11.933 を使用します。</span><span class="sxs-lookup"><span data-stu-id="ad26d-188">It uses current UTC time – GETUTCDATE() – 2007-05-04 01:34:11.933.</span></span> <span data-ttu-id="ad26d-189">かどうか 1 に設定を使用してローカル時刻 – GETDATE() – 2007-05-03 18:34:11.933</span><span class="sxs-lookup"><span data-stu-id="ad26d-189">If set to 1, then it uses local time – GETDATE() – 2007-05-03 18:34:11.933</span></span>
  
    ```  
    exec [dbo].[sp_DeleteBackupHistory] @DaysToKeep=14, @UseLocalTime =1 
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="ad26d-190">この手順**しない**バックアップ ファイルの保存先のパスから削除します。</span><span class="sxs-lookup"><span data-stu-id="ad26d-190">This step **does not** delete backup files from the destination path.</span></span>  
    
     <span data-ttu-id="ad26d-191">選択**OK**してすべてのプロパティ ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="ad26d-191">Select **OK** and close all property windows.</span></span>  
  
8.  <span data-ttu-id="ad26d-192">省略可。</span><span class="sxs-lookup"><span data-stu-id="ad26d-192">Optional.</span></span> <span data-ttu-id="ad26d-193">バックアップのスケジュールを変更します。</span><span class="sxs-lookup"><span data-stu-id="ad26d-193">Change the backup schedule.</span></span> <span data-ttu-id="ad26d-194">参照してください[バックアップの BizTalk Server のジョブをスケジュールする方法](../core/how-to-schedule-the-backup-biztalk-server-job.md)です。</span><span class="sxs-lookup"><span data-stu-id="ad26d-194">See [How to Schedule the Backup BizTalk Server Job](../core/how-to-schedule-the-backup-biztalk-server-job.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ad26d-195">バックアップ[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ジョブが初めて構成することを実行します。</span><span class="sxs-lookup"><span data-stu-id="ad26d-195">The Backup [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] job runs the first time you configure it.</span></span> <span data-ttu-id="ad26d-196">既定では、後続の実行、バックアップ[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ジョブは 1 日に 1 回完全バックアップを完了して、15 分ごとにログ バックアップを完了します。</span><span class="sxs-lookup"><span data-stu-id="ad26d-196">By default, on subsequent runs, the Backup [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] job completes a full backup once a day, and completes log backups every 15 minutes.</span></span>  
  
9. <span data-ttu-id="ad26d-197">右クリックし、 **Backup BizTalk Server**ジョブ、および選択**を有効にする**です。</span><span class="sxs-lookup"><span data-stu-id="ad26d-197">Right-click the **Backup BizTalk Server** job, and select **Enable**.</span></span> <span data-ttu-id="ad26d-198">状態に変更する必要があります**成功**です。</span><span class="sxs-lookup"><span data-stu-id="ad26d-198">The status should change to **Success**.</span></span>  
  
## <a name="spforcefullbackup-stored-procedure"></a><span data-ttu-id="ad26d-199">sp_ForceFullBackup ストアド プロシージャ</span><span class="sxs-lookup"><span data-stu-id="ad26d-199">sp_ForceFullBackup stored procedure</span></span>  
  
<span data-ttu-id="ad26d-200">**Sp_ForceFullBackup**ストアド プロシージャ、 **BizTalkMgmtDb**データベースは、アドホックのデータとログ ファイルの完全バックアップを実行するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="ad26d-200">The **sp_ForceFullBackup** stored procedure in the **BizTalkMgmtDb** database can be used to run an ad-hoc full backup of the data and log files.</span></span> <span data-ttu-id="ad26d-201">ストアド プロシージャで、adm_ForceFullBackup テーブルの値を 1 にして更新します。</span><span class="sxs-lookup"><span data-stu-id="ad26d-201">The stored procedure updates the adm_ForceFullBackup table with a value 1.</span></span> <span data-ttu-id="ad26d-202">次回のバックアップ[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ジョブを実行すると、データベースの完全バックアップ セットを作成します。</span><span class="sxs-lookup"><span data-stu-id="ad26d-202">The next time the Backup [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] job is ran, a full database backup set is created.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="ad26d-203">次の手順</span><span class="sxs-lookup"><span data-stu-id="ad26d-203">Next Steps</span></span>  
 <span data-ttu-id="ad26d-204">[ログ配布用に送信先システムを構成する方法](../core/how-to-configure-the-destination-system-for-log-shipping.md) </span><span class="sxs-lookup"><span data-stu-id="ad26d-204">[How to Configure the Destination System for Log Shipping](../core/how-to-configure-the-destination-system-for-log-shipping.md) </span></span>  
 [<span data-ttu-id="ad26d-205">バックアップの BizTalk Server のジョブをスケジュールする方法</span><span class="sxs-lookup"><span data-stu-id="ad26d-205">How to Schedule the Backup BizTalk Server Job</span></span>](../core/how-to-schedule-the-backup-biztalk-server-job.md)
