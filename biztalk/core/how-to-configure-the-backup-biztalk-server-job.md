---
title: "バックアップの BizTalk Server ジョブを構成する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Tracking database, backing up
- backing up, Tracking database
- backing up, user accounts
- backing up, MessageBox database
- databases, backing up
- MessageBox database, backing up
- backing up, databases
- backing up, prerequisites
- configuring, backup jobs
- backing up, warnings
- backing up, backup jobs
- user accounts, backing up
- backing up, configuring
ms.assetid: 026622c9-fcb4-4db0-af48-1379feb30372
caps.latest.revision: "42"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 488e76c3d29c58107e85ad58ed4fad50de671315
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-the-backup-biztalk-server-job"></a><span data-ttu-id="2b195-102">BizTalk Server のバックアップ ジョブを構成する方法</span><span class="sxs-lookup"><span data-stu-id="2b195-102">How to Configure the Backup BizTalk Server Job</span></span>
<span data-ttu-id="2b195-103">このトピックでは、BizTalk Server のバックアップ ジョブを構成するために必要な手順を説明します。</span><span class="sxs-lookup"><span data-stu-id="2b195-103">This topic lists the steps necessary to configure the Backup BizTalk Server job.</span></span>  
  
 <span data-ttu-id="2b195-104">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] をバックアップする前に、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のバックアップ ジョブを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2b195-104">You must configure the Backup [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] job before you can back up [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="2b195-105">バックアップを構成するには、次のタスクのほとんどまたはすべてを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2b195-105">To configure the backup, you need to perform most or all of the following tasks:</span></span>  
  
-   <span data-ttu-id="2b195-106">SQL Server エージェントを編集**Backup BizTalk Server (BizTalkMgmtDb)**ジョブをプライマリ サーバーと移行先の SQL Server とその他のバックアップ オプションを識別します。</span><span class="sxs-lookup"><span data-stu-id="2b195-106">Edit the SQL Server Agent **Backup BizTalk Server (BizTalkMgmtDb)** job to identify the primary and destination SQL Servers and other backup options.</span></span>  
  
-   <span data-ttu-id="2b195-107">データベースのバックアップに使用する Windows ユーザー アカウントを選択し、このアカウントの SQL Server ログインを作成します。</span><span class="sxs-lookup"><span data-stu-id="2b195-107">Choose a Windows user account to back up your databases and create a SQL Server login for this account.</span></span>  
  
-   <span data-ttu-id="2b195-108">BizTalk Server データベースの BTS_BACKUP_USERS データベース ロールには、SQL Server ログインをマップします。</span><span class="sxs-lookup"><span data-stu-id="2b195-108">Map SQL Server logins to the BTS_BACKUP_USERS database role in the BizTalk Server databases.</span></span>  
  
-   <span data-ttu-id="2b195-109">すべてのノードで MSDTC サービスをアクティブにします。</span><span class="sxs-lookup"><span data-stu-id="2b195-109">Ensure MSDTC service is active on all nodes.</span></span> <span data-ttu-id="2b195-110">それ以外の場合、ソース ノードと送信先ノード間のリンク サーバーの追加は失敗します。</span><span class="sxs-lookup"><span data-stu-id="2b195-110">Else, adding a linked server between the source node and the destination node fails.</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="2b195-111">アンインストールの準備</span><span class="sxs-lookup"><span data-stu-id="2b195-111">Before you begin</span></span>  
  
-   <span data-ttu-id="2b195-112">この操作のような特定の構成およびバックアップ操作には、sysadmin SQL Server ロールのメンバーシップが必要です。</span><span class="sxs-lookup"><span data-stu-id="2b195-112">Certain configuration and backup operations such as this one require membership in the sysadmin SQL Server role.</span></span> <span data-ttu-id="2b195-113">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] データベースをバックアップするには、プライマリ サーバー上の SQL Server の sysadmin サーバー ロールに属するアカウントでプライマリ サーバーにログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2b195-113">To back up your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases, you must be logged on at the primary server with an account that is a member of the SQL Server sysadmin Server role on the primary server.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="2b195-114"> 構成には BTS_BACKUP_USERS という名前のデータベース ロールが追加されているため、データベースのバックアップに使用するユーザー アカウントは、プライマリ サーバーを除いて、バックアップに関係するすべての SQL Server 上でのシステム管理者 (sysadmin SQL Server ロール) のアクセス許可を必要としません。</span><span class="sxs-lookup"><span data-stu-id="2b195-114"> configuration adds a database role named BTS_BACKUP_USERS so that the user account you use to back up your databases does not require System Administrator (sysadmin SQL Server role) permissions on all of the SQL Servers that may be involved in a backup, except for the primary server.</span></span>  
  
-   <span data-ttu-id="2b195-115">実行に使用するログイン アカウントを決定する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベースのバックアップ。</span><span class="sxs-lookup"><span data-stu-id="2b195-115">You need to decide which login account you use to perform your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] database backups.</span></span> <span data-ttu-id="2b195-116">ローカル アカウントを使用できます。複数のアカウントを使用できますが、通常は、この目的に限定した専用の Windows ドメイン ユーザー アカウントを 1 つ作成する方が簡単で安全です。</span><span class="sxs-lookup"><span data-stu-id="2b195-116">You can use a local account, and you can use more than one account, but it is generally simpler and more secure to create one dedicated Windows domain user account specifically for this purpose.</span></span> <span data-ttu-id="2b195-117">このユーザー用の SQL Server ログオン アカウントを構成し、バックアップ プロセスに参加するすべての SQL Server について、プライマリ (送信元) サーバーかセカンダリ (送信先) サーバーかにかかわらず、ユーザーを SQL Server ログインにマップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2b195-117">You must configure a SQL Server logon account for this user, and the user must be mapped to a SQL Server login for all of the SQL Servers that participate in the backup process, either as primary (source) or secondary (destination) servers.</span></span> <span data-ttu-id="2b195-118">各 BizTalk BTS_BACKUP_USERS データベース ロールにこのユーザーを割り当てる、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]をバックアップするデータベースします。</span><span class="sxs-lookup"><span data-stu-id="2b195-118">Assign this user to the BizTalk BTS_BACKUP_USERS database role for each of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases you back up.</span></span>  
  
-   <span data-ttu-id="2b195-119">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のバックアップ ジョブでは、期限切れのバックアップ ファイルが削除されないので、ディスク領域を節約するにはこれらのバックアップ ファイルを手動で管理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2b195-119">The Backup [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] job does not delete outdated backup files, so you need to manually manage those backup files to conserve disk space.</span></span> <span data-ttu-id="2b195-120">データベースの完全バックアップを新規作成した後で、プライマリ ディスクの領域を再利用できるように、期限切れのバックアップ ファイルをアーカイブ ストレージ デバイスに移動します。</span><span class="sxs-lookup"><span data-stu-id="2b195-120">After you have created a new full backup of your databases, you should move the outdated backup files onto an archival storage device to reclaim space on the primary disk.</span></span> <span data-ttu-id="2b195-121">"BizTalk Bill"は、ダウンロード可能な[SSIS パッケージ](http://www.biztalkbill.com/2015/05/26/ssis-packages-to-help-management-biztalk-server-environments/)をこれらのファイルを管理します。</span><span class="sxs-lookup"><span data-stu-id="2b195-121">"BizTalk Bill" has downloadable [SSIS packages](http://www.biztalkbill.com/2015/05/26/ssis-packages-to-help-management-biztalk-server-environments/) to manage these files.</span></span>  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="2b195-122"> は、追跡データを BizTalk 追跡データベースに直接書き込むのではなく、メッセージボックス データベースにデータをキャッシュしてから、BizTalk 追跡データベースに移動します。</span><span class="sxs-lookup"><span data-stu-id="2b195-122"> does not write tracking data directly to the BizTalk Tracking database; rather it caches the data in the MessageBox database and then moves it to the BizTalk Tracking database.</span></span> <span data-ttu-id="2b195-123">メッセージ ボックス データの損失が発生した場合は、追跡データも一部が失われている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2b195-123">If MessageBox data loss occurs, some tracking data may also be lost.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="2b195-124">前提条件</span><span class="sxs-lookup"><span data-stu-id="2b195-124">Prerequisites</span></span>  
* <span data-ttu-id="2b195-125">SQL Server の sysadmin SQL Server ロールのメンバーであるアカウントを使用してにサインインします。</span><span class="sxs-lookup"><span data-stu-id="2b195-125">Sign in to SQL Server using an account that is a member of the sysadmin SQL Server role.</span></span>  
  
* <span data-ttu-id="2b195-126">SQL Server エージェント サービスは、SQL Server の各インスタンス上にユーザー ログインがマップされたドメイン アカウントまたはローカル アカウントで実行されるように構成します。ローカル アカウントも使用できますが、ドメイン アカウントの使用をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2b195-126">Configure the SQL Server Agent service to run under a domain account (recommended, although local accounts can be used), with a mapped user login on each instance of SQL Server.</span></span>  
  
## <a name="configure-the-backup-biztalk-server-job"></a><span data-ttu-id="2b195-127">BizTalk Server のバックアップ ジョブを構成します。</span><span class="sxs-lookup"><span data-stu-id="2b195-127">Configure the Backup BizTalk Server job</span></span>  
  
1.  <span data-ttu-id="2b195-128">BizTalk 管理データベースをホストする SQL Server で開く**SQL Server Management Studio**に接続し、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="2b195-128">On the SQL Server that hosts the BizTalk Management database, open **SQL Server Management Studio**, and connect to your [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)].</span></span>  
  
2.  <span data-ttu-id="2b195-129">**[SQL Server エージェント]** を展開し、**[ジョブ]** を展開します。</span><span class="sxs-lookup"><span data-stu-id="2b195-129">Expand **SQL Server Agent**, and expand **Jobs**.</span></span>  
  
3.  <span data-ttu-id="2b195-130">右クリック**Backup BizTalk Server (BizTalkMgmtDb)**選択**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="2b195-130">Right-click **Backup BizTalk Server (BizTalkMgmtDb)** and select **Properties**.</span></span> <span data-ttu-id="2b195-131">ジョブのプロパティで選択**手順**です。</span><span class="sxs-lookup"><span data-stu-id="2b195-131">In the job properties, select **Steps**.</span></span>  
  
4.  <span data-ttu-id="2b195-132">選択、 **Set Compression Option**  を選択**編集**です。</span><span class="sxs-lookup"><span data-stu-id="2b195-132">Select the **Set Compression Option** step and select **Edit**.</span></span> <span data-ttu-id="2b195-133">**コマンド**ボックスで、値を 1 に変更します。</span><span class="sxs-lookup"><span data-stu-id="2b195-133">In the **Command** box, change the value to 1:</span></span>  
  
    ```  
    exec [dbo].[sp_SetBackupCompression] @bCompression = 1 /*0 - Do not use Compression, 1 - Use Compression */  
    ```  
  
     <span data-ttu-id="2b195-134">[ **OK**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="2b195-134">Select **OK**.</span></span>  
  
5.  <span data-ttu-id="2b195-135">選択、 **BackupFull**  を選択**編集**です。</span><span class="sxs-lookup"><span data-stu-id="2b195-135">Select the **BackupFull** step and select **Edit**.</span></span> <span data-ttu-id="2b195-136">**コマンド**ボックスで、パラメーターの値を編集します。</span><span class="sxs-lookup"><span data-stu-id="2b195-136">In the **Command** box, edit the parameter values:</span></span>  
  
    1.  <span data-ttu-id="2b195-137">**頻度**: 既定値は**d** (毎日) です。</span><span class="sxs-lookup"><span data-stu-id="2b195-137">**Frequency**: The default is **d** (daily).</span></span> <span data-ttu-id="2b195-138">この設定をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2b195-138">This is the recommended setting.</span></span> <span data-ttu-id="2b195-139">その他の値を含める**h** (1 時間ごと)、 **w** (毎週)、 **m** (毎月)、または**y** (毎年)。</span><span class="sxs-lookup"><span data-stu-id="2b195-139">Other values include **h** (hourly), **w** (weekly), **m** (monthly), or **y** (yearly).</span></span>  
  
    2.  <span data-ttu-id="2b195-140">**名前**: 既定値は**BTS**です。</span><span class="sxs-lookup"><span data-stu-id="2b195-140">**Name**: The default is **BTS**.</span></span> <span data-ttu-id="2b195-141">この名前は、バックアップ ファイル名の一部として使用されます。</span><span class="sxs-lookup"><span data-stu-id="2b195-141">The name is used as part of the backup file name.</span></span>  
  
    3.  <span data-ttu-id="2b195-142">**バックアップ ファイルの場所**: 置換 '*\<先のパス >*' 完全なパス (パスは、単一引用符を含める必要があります) へのバックアップを作成するフォルダー、コンピューター、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース。</span><span class="sxs-lookup"><span data-stu-id="2b195-142">**Location of backup files**: Replace '*\<destination path>*' with the full path (the path must include the single quotes) to the computer and folder where you want to back up the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases.</span></span>  
  
        > [!IMPORTANT]
        >  -   <span data-ttu-id="2b195-143">ローカル パスを指定した場合は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のバックアップ ジョブでファイルが新規作成されるたびに、すべてのファイルを送信先システムの同じフォルダーに手動でコピーする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2b195-143">If you specify a local path, then you have to manually copy all the files to the same folder on the destination system whenever the Backup [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] job creates new files.</span></span>  
        >   
        >      <span data-ttu-id="2b195-144">リモート パスを指定するには、UNC 共有をように入力\\ \\  *\<ServerName >*\\*\<SharedDrive >* \\、ここで *\<ServerName >* 、ファイル サーバーの名前を指定し、  *\<SharedDrive >*共有ドライブまたはフォルダーの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="2b195-144">To specify a remote path, enter a UNC share such as \\\\*\<ServerName>*\\*\<SharedDrive>*\\, where *\<ServerName>* is the name of the server where you want the files, and *\<SharedDrive>* is name of the shared drive or folder.</span></span>  
        >   
        >      <span data-ttu-id="2b195-145">ネットワーク経由でデータをバックアップする場合は、ネットワークの影響を受けます。</span><span class="sxs-lookup"><span data-stu-id="2b195-145">Backing up data over a network is subject to any network issues.</span></span> <span data-ttu-id="2b195-146">リモートの場所を使用する場合は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のバックアップ ジョブの完了時にバックアップが成功したかどうか確認します。</span><span class="sxs-lookup"><span data-stu-id="2b195-146">When using a remote location, verify the backup succeeded when the Backup [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] job finishes.</span></span>  
        > -   <span data-ttu-id="2b195-147">データ損失の可能性を回避するには、バックアップ ディスクを、データベースのデータ ディスクおよびログ ディスクとは異なるディスクに構成します。</span><span class="sxs-lookup"><span data-stu-id="2b195-147">To avoid potential data loss, configure the backup disk to be a different disk than the database data and log disks.</span></span> <span data-ttu-id="2b195-148">これは、データやログのディスクに障害が発生した場合にバックアップにアクセスするために必須です。</span><span class="sxs-lookup"><span data-stu-id="2b195-148">This is necessary so you can access the backups if the data or log disk fails.</span></span>  
  
    4.  <span data-ttu-id="2b195-149">**部分バックアップ障害の後に完全バックアップの force**: 既定値は**0**が指定されていないときにすることを意味する場合、ログ バックアップは失敗し、[次へ] の完全バックアップの間隔に達するまで完全バックアップは実行されません。</span><span class="sxs-lookup"><span data-stu-id="2b195-149">**Force full backup after partial backup failures**: The default is **0** when not specified, which means that if a log backup fails, no full backups are done until the next full backup frequency interval is reached.</span></span> <span data-ttu-id="2b195-150">置き換える**1**完全バックアップをログ バックアップの失敗が発生するたびに行う場合します。</span><span class="sxs-lookup"><span data-stu-id="2b195-150">Replace with **1** if you want a full backup to be made whenever a log backup failure occurs.</span></span>  
  
    5.  <span data-ttu-id="2b195-151">**バックアップ プロセスの実行のローカル時刻を 1 時間**: 既定値は NULL 指定しない場合、つまり、そのバックアップ ジョブに関連付けられていないのタイム ゾーン、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]タイム (0000) のコンピューターとそのための午前 0 時 (utc) で実行されます。</span><span class="sxs-lookup"><span data-stu-id="2b195-151">**Local time hour for the backup process to run**: The default is NULL when not specified, which means that backup job is not associated with the time zone of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computer and therefore runs at midnight UTC time (0000).</span></span> <span data-ttu-id="2b195-152">特定の時刻のタイム ゾーンで実行するバックアップを作成する場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]コンピューター、整数値 0 (深夜) から 23 (11 PM) として入力のローカル時刻の時間、 **BackupHour**パラメーター。</span><span class="sxs-lookup"><span data-stu-id="2b195-152">If you want to backup to run at a particular hour in the time zone of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computer, enter an integer value from 0 (midnight) to 23 (11 PM) as the local time hour for the **BackupHour** parameter.</span></span>  
  
     <span data-ttu-id="2b195-153">次の例では、毎日のバックアップが午前 2 時に作成され、ドライブ m:\ に保存されます。</span><span class="sxs-lookup"><span data-stu-id="2b195-153">In the following example, daily backups are created at 2am and stored in the m:\ drive:</span></span>  
  
    ```  
    exec [dbo].[sp_BackupAllFull_Schedule]   
    'd' /* Frequency */,   
    'BTS' /* Name */,   
    'm:\BizTalkBackups' /* location of backup files */,   
    0 /* 0 (default) or 1 ForceFullBackupAfterPartialSetFailure */,   
    '2' /* local time hour for the backup process to run */  
    ```  
  
     <span data-ttu-id="2b195-154">[ **OK**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="2b195-154">Select **OK**.</span></span>  
  
6.  <span data-ttu-id="2b195-155">選択、 **MarkAndBackupLog**  を選択**編集**です。</span><span class="sxs-lookup"><span data-stu-id="2b195-155">Select the **MarkAndBackupLog** step and select **Edit**.</span></span> <span data-ttu-id="2b195-156">**コマンド**ボックスで、置き換える**'***\<先のパス >***'**への完全パス (単一引用符を含む) で、コンピューターおよび保存するフォルダー、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース ログ。</span><span class="sxs-lookup"><span data-stu-id="2b195-156">In the **Command** box, replace **'***\<destination path>***'** with the full path (including single quotes) to the computer and folder where you want to store the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] database logs.</span></span> <span data-ttu-id="2b195-157">*\<先のパス >*ローカル パスまたは別のサーバーへの UNC パスになる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2b195-157">The *\<destination path>* may be local or a UNC path to another server.</span></span>  
  
     <span data-ttu-id="2b195-158">MarkAndBackupLog ステップで、バックアップのログをマークした後、バックアップします。</span><span class="sxs-lookup"><span data-stu-id="2b195-158">The MarkAndBackupLog step marks the logs for backup, and then backs them up.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="2b195-159">データ損失の可能性を回避する、 *\<先のパス >*元のデータベースのログを使用するコンピューターとは異なるデータベース ログを格納するコンピューターを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2b195-159">To avoid potential data loss, the *\<destination path>* should specify a computer to store the database logs that is different from the computer with the original database logs.</span></span>  
  
     <span data-ttu-id="2b195-160">[ **OK**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="2b195-160">Select **OK**.</span></span>  
  
7.  <span data-ttu-id="2b195-161">選択、 **Clear Backup History**  を選択**編集**です。</span><span class="sxs-lookup"><span data-stu-id="2b195-161">Select the **Clear Backup History** step and select **Edit**.</span></span> <span data-ttu-id="2b195-162">**コマンド**ボックスで、変更**DaysToKeep =***\<番号 >*バックアップ履歴を保持する日数を指定します。</span><span class="sxs-lookup"><span data-stu-id="2b195-162">In the **Command** box, change **DaysToKeep=***\<number>* to the number of days you want to keep the backup history:</span></span>  
  
    ```  
    exec [dbo].[sp_DeleteBackupHistory] @DaysToKeep=14  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="2b195-163">**DaysToKeep**バックアップ履歴が保持される期間、Adm_BackupHistory テーブルにパラメーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="2b195-163">The **DaysToKeep** parameter specifies how long the backup history is kept in the Adm_BackupHistory table.</span></span> <span data-ttu-id="2b195-164">定期的にバックアップ履歴を消去すると、Adm_BackupHistory テーブルを適切なサイズで維持することができます。</span><span class="sxs-lookup"><span data-stu-id="2b195-164">Periodically clearing the backup history helps to maintain the Adm_BackupHistory table at an appropriate size.</span></span> <span data-ttu-id="2b195-165">既定値、 **DaysToKeep**パラメーターが 14 日間です。</span><span class="sxs-lookup"><span data-stu-id="2b195-165">The default value for the **DaysToKeep** parameter is 14 days.</span></span>  
  
     <span data-ttu-id="2b195-166">選択**OK**してすべてのプロパティ ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="2b195-166">Select **OK** and close all property windows.</span></span>  
  
8.  <span data-ttu-id="2b195-167">省略可。</span><span class="sxs-lookup"><span data-stu-id="2b195-167">Optional.</span></span> <span data-ttu-id="2b195-168">バックアップのスケジュールを変更します。</span><span class="sxs-lookup"><span data-stu-id="2b195-168">Change the backup schedule.</span></span> <span data-ttu-id="2b195-169">参照してください[バックアップの BizTalk Server のジョブをスケジュールする方法](../core/how-to-schedule-the-backup-biztalk-server-job.md)です。</span><span class="sxs-lookup"><span data-stu-id="2b195-169">See [How to Schedule the Backup BizTalk Server Job](../core/how-to-schedule-the-backup-biztalk-server-job.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2b195-170">バックアップ[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ジョブが初めて構成することを実行します。</span><span class="sxs-lookup"><span data-stu-id="2b195-170">The Backup [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] job runs the first time you configure it.</span></span> <span data-ttu-id="2b195-171">既定でそれ以降は、Backup [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] により完全バックアップが 1 日 1 回実行され、ログ バックアップが 15 分ごとに実行されます。</span><span class="sxs-lookup"><span data-stu-id="2b195-171">By default, on subsequent runs, the Backup [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] job performs a full backup once a day and performs log backups every 15 minutes.</span></span>  
  
9. <span data-ttu-id="2b195-172">右クリックし、 **Backup BizTalk Server**のジョブし、選択**を有効にする**です。</span><span class="sxs-lookup"><span data-stu-id="2b195-172">Right-click the **Backup BizTalk Server** job and select **Enable**.</span></span> <span data-ttu-id="2b195-173">状態に変更する必要があります**成功**です。</span><span class="sxs-lookup"><span data-stu-id="2b195-173">The status should change to **Success**.</span></span>  
  
## <a name="spforcefullbackup-stored-procedure"></a><span data-ttu-id="2b195-174">sp_ForceFullBackup ストアド プロシージャ</span><span class="sxs-lookup"><span data-stu-id="2b195-174">sp_ForceFullBackup stored procedure</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2b195-175">BizTalkMgmtDb データベースの sp_ForceFullBackup ストアド プロシージャを使用すれば、データ ファイルとログ ファイルの完全バックアップを随時実行できます。</span><span class="sxs-lookup"><span data-stu-id="2b195-175">The sp_ForceFullBackup stored procedure in the BizTalkMgmtDb database can be used to help perform an ad-hoc full backup of the data and log files.</span></span> <span data-ttu-id="2b195-176">ストアド プロシージャで、adm_ForceFullBackup テーブルの値を 1 にして更新します。</span><span class="sxs-lookup"><span data-stu-id="2b195-176">The stored procedure updates the adm_ForceFullBackup table with a value 1.</span></span> <span data-ttu-id="2b195-177">次回のバックアップ[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ジョブを実行すると、データベースの完全バックアップ セットを作成します。</span><span class="sxs-lookup"><span data-stu-id="2b195-177">The next time the Backup [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] job is ran, a full database backup set is created.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="2b195-178">次の手順</span><span class="sxs-lookup"><span data-stu-id="2b195-178">Next Steps</span></span>  
 [<span data-ttu-id="2b195-179">ログ配布用に送信先システムを構成する方法</span><span class="sxs-lookup"><span data-stu-id="2b195-179">How to Configure the Destination System for Log Shipping</span></span>](../core/how-to-configure-the-destination-system-for-log-shipping.md)  
  
## <a name="see-also"></a><span data-ttu-id="2b195-180">参照</span><span class="sxs-lookup"><span data-stu-id="2b195-180">See Also</span></span>  
 [<span data-ttu-id="2b195-181">バックアップの BizTalk Server のジョブをスケジュールする方法</span><span class="sxs-lookup"><span data-stu-id="2b195-181">How to Schedule the Backup BizTalk Server Job</span></span>](../core/how-to-schedule-the-backup-biztalk-server-job.md)