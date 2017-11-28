---
title: "バックアップの BizTalk Server のジョブを構成する |Microsoft ドキュメント"
description: 
ms.custom: 
ms.date: 11/22/2017
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
ms.openlocfilehash: f1afb4f28584d65401220761dcee626fe63f913b
ms.sourcegitcommit: f4c0d7bc4b617688c643101a34062db90014851a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2017
---
# <a name="configure-the-backup-biztalk-server-job"></a><span data-ttu-id="0cbee-102">バックアップの BizTalk Server のジョブを構成します。</span><span class="sxs-lookup"><span data-stu-id="0cbee-102">Configure the Backup BizTalk Server Job</span></span>
<span data-ttu-id="0cbee-103">インストールし、BizTalk Server を構成した後は、バックアップを構成する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データをバックアップするジョブです。</span><span class="sxs-lookup"><span data-stu-id="0cbee-103">After you install and configure BizTalk Server, configure the Backup [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] job to back up your data.</span></span> 

<span data-ttu-id="0cbee-104">**以降で[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]Feature Pack 2**データベースのバックアップおよび、ログ ファイルを Azure blob ストレージ アカウントにすることができます。</span><span class="sxs-lookup"><span data-stu-id="0cbee-104">**Starting with [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] Feature Pack 2**, you can backup your databases and log files to an Azure blob storage account.</span></span> 


## <a name="overview"></a><span data-ttu-id="0cbee-105">概要</span><span class="sxs-lookup"><span data-stu-id="0cbee-105">Overview</span></span>
<span data-ttu-id="0cbee-106">**Backup BizTalk Server (BizTalkMgmtDb)**ジョブには、次の手順が含まれています。</span><span class="sxs-lookup"><span data-stu-id="0cbee-106">The **Backup BizTalk Server (BizTalkMgmtDb)** job includes the following steps:</span></span>

-   <span data-ttu-id="0cbee-107">手順 1 –**セット圧縮オプション**: を有効にするか、バックアップ中に圧縮を無効にします。</span><span class="sxs-lookup"><span data-stu-id="0cbee-107">Step 1 – **Set Compression Option**: Enable or disable compression during backup</span></span>

-   <span data-ttu-id="0cbee-108">手順 2 – **BackupFull**: 完全なデータベース、BizTalk Server データベースのバックアップの実行</span><span class="sxs-lookup"><span data-stu-id="0cbee-108">Step 2 – **BackupFull**: Runs full database backups of the BizTalk Server databases</span></span>

-   <span data-ttu-id="0cbee-109">手順 3 – **MarkAndBackUpLog**: BizTalk Server データベースのログ バックアップ</span><span class="sxs-lookup"><span data-stu-id="0cbee-109">Step 3 – **MarkAndBackUpLog**: Backs up the BizTalk Server database logs</span></span>

-   <span data-ttu-id="0cbee-110">手順 4 –**バックアップ履歴をクリア**: バックアップ履歴が保持される期間を選択</span><span class="sxs-lookup"><span data-stu-id="0cbee-110">Step 4 – **Clear Backup History**: Choose how long the backup history is kept</span></span>

<span data-ttu-id="0cbee-111">このジョブを構成するのには、する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0cbee-111">To configure this job, you'll need to:</span></span>  
  
-   <span data-ttu-id="0cbee-112">プライマリ サーバーと移行先の SQL Server とその他のバックアップ オプションを確認します。</span><span class="sxs-lookup"><span data-stu-id="0cbee-112">Identify the primary and destination SQL Servers and other backup options</span></span>
  
-   <span data-ttu-id="0cbee-113">データベースをバックアップする Windows ユーザー アカウントを選択し、このアカウントに SQL Server ログインの作成</span><span class="sxs-lookup"><span data-stu-id="0cbee-113">Choose a Windows user account to back up your databases, and create a SQL Server login for this account</span></span>
  
-   <span data-ttu-id="0cbee-114">SQL Server ログインを BizTalk Server データベース内の BTS_BACKUP_USERS データベース ロールにマップします。</span><span class="sxs-lookup"><span data-stu-id="0cbee-114">Map SQL Server logins to the BTS_BACKUP_USERS database role in the BizTalk Server databases</span></span>
  
-   <span data-ttu-id="0cbee-115">すべてのノードで MSDTC サービスをアクティブにします。</span><span class="sxs-lookup"><span data-stu-id="0cbee-115">Ensure MSDTC service is active on all nodes.</span></span> <span data-ttu-id="0cbee-116">それ以外の場合、ソース ノードと送信先ノード間のリンク サーバーの追加は失敗します。</span><span class="sxs-lookup"><span data-stu-id="0cbee-116">Otherwise, adding a linked server between the source node and the destination node fails.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="0cbee-117">アンインストールの準備</span><span class="sxs-lookup"><span data-stu-id="0cbee-117">Before you begin</span></span>  
  
-   <span data-ttu-id="0cbee-118">特定の構成およびバックアップ操作には、sysadmin SQL Server ロールのメンバーシップが必要とします。</span><span class="sxs-lookup"><span data-stu-id="0cbee-118">Certain configuration and backup operations require membership in the sysadmin SQL Server role.</span></span> <span data-ttu-id="0cbee-119">バックアップするには、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベースが SQL Server の sysadmin サーバー ロールのメンバーであるアカウントを使用して、プライマリ サーバーにサインインします。</span><span class="sxs-lookup"><span data-stu-id="0cbee-119">To back up your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases, sign in the primary server with an account that is a member of the SQL Server sysadmin Server role.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="0cbee-120">構成では、BTS_BACKUP_USERS データベース ロールを追加します。</span><span class="sxs-lookup"><span data-stu-id="0cbee-120"> configuration adds the BTS_BACKUP_USERS database role.</span></span> <span data-ttu-id="0cbee-121">データベースをバックアップに使用するユーザー アカウントには、プライマリ サーバーを除く、バックアップには、関連するすべての SQL Server のシステム管理者 (sysadmin SQL Server ロール) のアクセス許可は不要です。</span><span class="sxs-lookup"><span data-stu-id="0cbee-121">The user account you use to back up your databases does not require System Administrator (sysadmin SQL Server role) permissions on all the SQL Servers that may be involved in a backup, except for the primary server.</span></span>  
  
-   <span data-ttu-id="0cbee-122">実行に使用するサインイン アカウントを決める、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベースのバックアップ。</span><span class="sxs-lookup"><span data-stu-id="0cbee-122">Decide which sign in account you use to run your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] database backups.</span></span> <span data-ttu-id="0cbee-123">ローカル アカウントを使用することができ、1 つ以上のアカウントを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="0cbee-123">You can use a local account, and you can use more than one account.</span></span> <span data-ttu-id="0cbee-124">一般に簡素化され、この目的専用の専用の 1 つの Windows ドメイン ユーザー アカウントを作成する方が安全です。</span><span class="sxs-lookup"><span data-stu-id="0cbee-124">But it is generally simpler and more secure to create one dedicated Windows domain user account specifically for this purpose.</span></span> <span data-ttu-id="0cbee-125">このユーザー用の SQL Server ログオン アカウントを構成し、バックアップ プロセスに参加するすべての SQL Server について、プライマリ (送信元) サーバーかセカンダリ (送信先) サーバーかにかかわらず、ユーザーを SQL Server ログインにマップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0cbee-125">You must configure a SQL Server logon account for this user, and the user must be mapped to a SQL Server login for all of the SQL Servers that participate in the backup process, either as primary (source) or secondary (destination) servers.</span></span> <span data-ttu-id="0cbee-126">各 BizTalk BTS_BACKUP_USERS データベース ロールにこのユーザーを割り当てる、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]をバックアップするデータベースします。</span><span class="sxs-lookup"><span data-stu-id="0cbee-126">Assign this user to the BizTalk BTS_BACKUP_USERS database role for each of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases you back up.</span></span>  
  
-   <span data-ttu-id="0cbee-127">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のバックアップ ジョブでは、期限切れのバックアップ ファイルが削除されないので、ディスク領域を節約するにはこれらのバックアップ ファイルを手動で管理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0cbee-127">The Backup [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] job does not delete outdated backup files, so you need to manually manage those backup files to conserve disk space.</span></span> <span data-ttu-id="0cbee-128">データベースの完全バックアップを新規作成した後で、プライマリ ディスクの領域を再利用できるように、期限切れのバックアップ ファイルをアーカイブ ストレージ デバイスに移動します。</span><span class="sxs-lookup"><span data-stu-id="0cbee-128">After you have created a new full backup of your databases, you should move the outdated backup files onto an archival storage device to reclaim space on the primary disk.</span></span> <span data-ttu-id="0cbee-129">参照してください、 [SSIS パッケージ](http://www.biztalkbill.com/2015/05/26/ssis-packages-to-help-management-biztalk-server-environments/)をこれらのファイルを管理します。</span><span class="sxs-lookup"><span data-stu-id="0cbee-129">See the [SSIS packages](http://www.biztalkbill.com/2015/05/26/ssis-packages-to-help-management-biztalk-server-environments/) to manage these files.</span></span>  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="0cbee-130">BizTalk 追跡データベースに直接追跡データは書き込まれませんなくメッセージ ボックス データベースにデータをキャッシュしてから、BizTalk 追跡データベースに移動します。</span><span class="sxs-lookup"><span data-stu-id="0cbee-130"> does not write tracking data directly to the BizTalk Tracking database; rather it caches the data in the MessageBox database, and then moves it to the BizTalk Tracking database.</span></span> <span data-ttu-id="0cbee-131">メッセージ ボックス データの損失が発生した場合は、追跡データも一部が失われている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0cbee-131">If MessageBox data loss occurs, some tracking data may also be lost.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="0cbee-132">前提条件</span><span class="sxs-lookup"><span data-stu-id="0cbee-132">Prerequisites</span></span>  
* <span data-ttu-id="0cbee-133">SQL Server の sysadmin SQL Server ロールのメンバーであるアカウントを使用してにサインインします。</span><span class="sxs-lookup"><span data-stu-id="0cbee-133">Sign in to SQL Server using an account that is a member of the sysadmin SQL Server role.</span></span>  
  
* <span data-ttu-id="0cbee-134">SQL Server エージェント サービスは、SQL Server の各インスタンス上にユーザー ログインがマップされたドメイン アカウントまたはローカル アカウントで実行されるように構成します。ローカル アカウントも使用できますが、ドメイン アカウントの使用をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0cbee-134">Configure the SQL Server Agent service to run under a domain account (recommended, although local accounts can be used), with a mapped user login on each instance of SQL Server.</span></span>  

* <span data-ttu-id="0cbee-135">Azure blob ストレージ アカウントを使用する必要があります、[汎用ストレージ アカウント](https://docs.microsoft.com/azure/storage/common/storage-create-storage-account#create-a-storage-account)、blob ストレージ アカウント内のコンテナー、[共有アクセス署名](https://docs.microsoft.com/sql/relational-databases/backup-restore/sql-server-backup-to-url#SAS)(SAS)、および[SQL 資格情報SAS を使用して](https://docs.microsoft.com/sql/relational-databases/backup-restore/sql-server-backup-to-url#credential)です。</span><span class="sxs-lookup"><span data-stu-id="0cbee-135">To use an Azure blob storage account, you need a [general purpose storage account](https://docs.microsoft.com/azure/storage/common/storage-create-storage-account#create-a-storage-account), a container within your blob storage account, a [shared access signature](https://docs.microsoft.com/sql/relational-databases/backup-restore/sql-server-backup-to-url#SAS) (SAS), and a [SQL credential using the SAS](https://docs.microsoft.com/sql/relational-databases/backup-restore/sql-server-backup-to-url#credential).</span></span> <span data-ttu-id="0cbee-136">作成した後、blob サービス エンドポイントの URL、https:// のようなものであるがある*yourstorageaccount*.blob.core.windows.net/*containername*です。</span><span class="sxs-lookup"><span data-stu-id="0cbee-136">Once created, have your blob service endpoint URL ready, which is something like https://*yourstorageaccount*.blob.core.windows.net/*containername*.</span></span> 

    > [!TIP]
    > <span data-ttu-id="0cbee-137">既存の blob ストレージ アカウント、SAS を使用して構成していない場合、 [SAS PowerShell スクリプト](https://docs.microsoft.com/sql/relational-databases/backup-restore/sql-server-backup-to-url#SAS)およびコンテナーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="0cbee-137">If you don't have an existing blob storage account configured with a SAS, then the [SAS PowerShell script](https://docs.microsoft.com/sql/relational-databases/backup-restore/sql-server-backup-to-url#SAS) can create it, and the container.</span></span> <span data-ttu-id="0cbee-138">[SQL Server Backup to URL](https://docs.microsoft.com/sql/relational-databases/backup-restore/sql-server-backup-to-url)概要については、および特定の手順を示します。</span><span class="sxs-lookup"><span data-stu-id="0cbee-138">[SQL Server Backup to URL](https://docs.microsoft.com/sql/relational-databases/backup-restore/sql-server-backup-to-url) provides an overview, and the specific steps.</span></span>
  
## <a name="configure-the-job"></a><span data-ttu-id="0cbee-139">ジョブを構成します。</span><span class="sxs-lookup"><span data-stu-id="0cbee-139">Configure the job</span></span>  
  
1.  <span data-ttu-id="0cbee-140">BizTalk 管理データベースをホストする SQL Server で開く**SQL Server Management Studio**に接続し、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="0cbee-140">On the SQL Server that hosts the BizTalk Management database, open **SQL Server Management Studio**, and connect to your [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)].</span></span>  
  
2.  <span data-ttu-id="0cbee-141">**[SQL Server エージェント]** を展開し、**[ジョブ]** を展開します。</span><span class="sxs-lookup"><span data-stu-id="0cbee-141">Expand **SQL Server Agent**, and expand **Jobs**.</span></span>  
  
3.  <span data-ttu-id="0cbee-142">右クリック**Backup BizTalk Server (BizTalkMgmtDb)**選択**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="0cbee-142">Right-click **Backup BizTalk Server (BizTalkMgmtDb)** and select **Properties**.</span></span> <span data-ttu-id="0cbee-143">ジョブのプロパティで選択**手順**です。</span><span class="sxs-lookup"><span data-stu-id="0cbee-143">In the job properties, select **Steps**.</span></span>  
  
4.  <span data-ttu-id="0cbee-144">選択、 **Set Compression Option**ステップ、および選択**編集**:</span><span class="sxs-lookup"><span data-stu-id="0cbee-144">Select the **Set Compression Option** step, and select **Edit**:</span></span>  

    <span data-ttu-id="0cbee-145">このステップでは、`sp_SetBackupCompression`ストアド プロシージャに値を設定する BizTalk 管理データベース (BizTalkMgmtDb) で、`adm_BackupSettings`テーブル。</span><span class="sxs-lookup"><span data-stu-id="0cbee-145">This step calls the `sp_SetBackupCompression` stored procedure in the BizTalk management database (BizTalkMgmtDb) to set the value on the `adm_BackupSettings` table.</span></span> <span data-ttu-id="0cbee-146">ストアド プロシージャが 1 つのパラメーター:  **@bCompression**です。</span><span class="sxs-lookup"><span data-stu-id="0cbee-146">The stored procedure has one parameter: **@bCompression**.</span></span> <span data-ttu-id="0cbee-147">既定では、その設定は**0** (バックアップの圧縮がオフ)。</span><span class="sxs-lookup"><span data-stu-id="0cbee-147">By default, it is set to **0** (backup compression is off).</span></span> <span data-ttu-id="0cbee-148">圧縮を適用する値に変更**1**:</span><span class="sxs-lookup"><span data-stu-id="0cbee-148">To apply compression, change the value to **1**:</span></span>  
  
    ```  
    exec [dbo].[sp_SetBackupCompression] @bCompression = 1 /*0 - Do not use Compression, 1 - Use Compression */  
    ```  
  
     <span data-ttu-id="0cbee-149">**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0cbee-149">Select **OK**.</span></span>  
  
5.  <span data-ttu-id="0cbee-150">選択、 **BackupFull**ステップ、および選択**編集**です。</span><span class="sxs-lookup"><span data-stu-id="0cbee-150">Select the **BackupFull** step, and select **Edit**.</span></span> <span data-ttu-id="0cbee-151">**コマンド**ボックスで、パラメーター値を更新します。</span><span class="sxs-lookup"><span data-stu-id="0cbee-151">In the **Command** box, update the parameter values:</span></span>  
  
    1. <span data-ttu-id="0cbee-152">**頻度**: 既定値は**d** (毎日) です。 これは推奨される設定です。</span><span class="sxs-lookup"><span data-stu-id="0cbee-152">**Frequency**: The default is **d** (daily); which is the recommended setting.</span></span> <span data-ttu-id="0cbee-153">その他の値を含める**h** (1 時間ごと)、 **w** (毎週)、 **m** (毎月)、または**y** (毎年)。</span><span class="sxs-lookup"><span data-stu-id="0cbee-153">Other values include **h** (hourly), **w** (weekly), **m** (monthly), or **y** (yearly).</span></span>  
  
    2. <span data-ttu-id="0cbee-154">**名前**: 既定値は**BTS**です。</span><span class="sxs-lookup"><span data-stu-id="0cbee-154">**Name**: The default is **BTS**.</span></span> <span data-ttu-id="0cbee-155">この名前は、バックアップ ファイル名の一部として使用されます。</span><span class="sxs-lookup"><span data-stu-id="0cbee-155">The name is used as part of the backup file name.</span></span>  
  
    3. <span data-ttu-id="0cbee-156">**バックアップ ファイルの場所**: 置換 '*\<先のパス >*' 完全なパス (パスは、単一引用符を含める必要があります) へのバックアップを作成するフォルダー、コンピューター、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース、または Azure blob ストレージ アカウントに blob サービス エンドポイントの URL。</span><span class="sxs-lookup"><span data-stu-id="0cbee-156">**Location of backup files**: Replace '*\<destination path>*' with the full path (the path must include the single quotes) to the computer and folder where you want to back up the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases, or the blob service endpoint URL to an Azure blob storage account.</span></span>  

        > [!IMPORTANT]
        > - <span data-ttu-id="0cbee-157">ローカルのパスを入力するかどうかは、ターゲット システム上の同じフォルダーにすべてのファイルを手動でコピーする必要があるされるたびにバックアップ[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ジョブを新しいファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="0cbee-157">If you enter a local path, then you have to manually copy all the files to the same folder on the destination system whenever the Backup [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] job creates new files.</span></span>  
        >   
        >      <span data-ttu-id="0cbee-158">リモート パスを使用するには、UNC 共有をように入力\\ \\  *\<ServerName >*\\*\<SharedDrive >*\\、ここで *\<ServerName >* 、ファイル サーバーの名前を指定し、  *\<SharedDrive >*共有ドライブまたはフォルダーの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="0cbee-158">To use a remote path, enter a UNC share such as \\\\*\<ServerName>*\\*\<SharedDrive>*\\, where *\<ServerName>* is the name of the server where you want the files, and *\<SharedDrive>* is name of the shared drive or folder.</span></span>  
        >   
        >      <span data-ttu-id="0cbee-159">ネットワーク経由でデータをバックアップする場合は、ネットワークの影響を受けます。</span><span class="sxs-lookup"><span data-stu-id="0cbee-159">Backing up data over a network is subject to any network issues.</span></span> <span data-ttu-id="0cbee-160">リモートの場所を使用する場合は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のバックアップ ジョブの完了時にバックアップが成功したかどうか確認します。</span><span class="sxs-lookup"><span data-stu-id="0cbee-160">When using a remote location, verify the backup succeeded when the Backup [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] job finishes.</span></span>  
        > - <span data-ttu-id="0cbee-161">データ損失の可能性を回避するには、バックアップ ディスクを、データベースのデータ ディスクおよびログ ディスクとは異なるディスクに構成します。</span><span class="sxs-lookup"><span data-stu-id="0cbee-161">To avoid potential data loss, configure the backup disk to be a different disk than the database data and log disks.</span></span> <span data-ttu-id="0cbee-162">これは、データやログのディスクに障害が発生した場合にバックアップにアクセスするために必須です。</span><span class="sxs-lookup"><span data-stu-id="0cbee-162">This is necessary so you can access the backups if the data or log disk fails.</span></span>  
        > - <span data-ttu-id="0cbee-163">Azure blob アカウントへのバックアップの入力と、 **Blob サービスのエンドポイント**、blob サービスのプロパティにリストされている URL とコンテナー名、 [Azure ポータル](https://portal.azure.com)です。</span><span class="sxs-lookup"><span data-stu-id="0cbee-163">When backing up to an Azure blob account, enter the **Blob service endpoint** URL and the container name, which are listed in your blob service properties in the [Azure portal](https://portal.azure.com).</span></span>

    4. <span data-ttu-id="0cbee-164">省略可。</span><span class="sxs-lookup"><span data-stu-id="0cbee-164">Optional.</span></span> <span data-ttu-id="0cbee-165">**部分バックアップ障害の後に完全バックアップの force** (@ForceFullBackupAfterPartialSetFailure): 既定値は**0**します。</span><span class="sxs-lookup"><span data-stu-id="0cbee-165">**Force full backup after partial backup failures** (@ForceFullBackupAfterPartialSetFailure): The default is **0**.</span></span> <span data-ttu-id="0cbee-166">ログのバックアップに失敗した場合、次の完全バックアップの間隔に到達するまで、完全バックアップは実行されませんでした。</span><span class="sxs-lookup"><span data-stu-id="0cbee-166">If a log backup fails, no full backups are ran until the next full backup frequency interval is reached.</span></span> <span data-ttu-id="0cbee-167">置き換える**1**ログ バックアップの失敗が発生するたびに、完全バックアップが実行された場合。</span><span class="sxs-lookup"><span data-stu-id="0cbee-167">Replace with **1** if you want a full backup ran whenever a log backup failure occurs.</span></span>
    
    5. <span data-ttu-id="0cbee-168">省略可。</span><span class="sxs-lookup"><span data-stu-id="0cbee-168">Optional.</span></span> <span data-ttu-id="0cbee-169">**バックアップ プロセスの実行のローカル時刻を 1 時間**(@BackupHour)。 既定値は**NULL**です。</span><span class="sxs-lookup"><span data-stu-id="0cbee-169">**Local time hour for the backup process to run** (@BackupHour): The default is **NULL**.</span></span> <span data-ttu-id="0cbee-170">バックアップ ジョブに関連付けられていないのタイム ゾーン、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]時刻 (0000) のコンピューター、および午前 0 時 (utc) で実行されます。</span><span class="sxs-lookup"><span data-stu-id="0cbee-170">The backup job is not associated with the time zone of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computer, and runs at midnight UTC time (0000).</span></span> <span data-ttu-id="0cbee-171">する場合のタイム ゾーンでの特定の時間にバックアップ、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]コンピューターが現地時間として整数値を 0 (深夜) から 23 (11 PM) に入力します。</span><span class="sxs-lookup"><span data-stu-id="0cbee-171">If you want to backup at a specific hour in the time zone of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computer, enter an integer value from 0 (midnight) to 23 (11 PM) as the local time hour.</span></span> 

    6. <span data-ttu-id="0cbee-172">省略可。</span><span class="sxs-lookup"><span data-stu-id="0cbee-172">Optional.</span></span> <span data-ttu-id="0cbee-173">**ローカル時刻を使用して**(@UseLocalTime): ローカル時刻を使用する手順を示します。</span><span class="sxs-lookup"><span data-stu-id="0cbee-173">**Use local time** (@UseLocalTime): Tells the procedure to use local time.</span></span> <span data-ttu-id="0cbee-174">既定値は**0**、現在の UTC 時刻 – GETUTCDATE() – 2007-05-04 01:34:11.933 を使用しています。</span><span class="sxs-lookup"><span data-stu-id="0cbee-174">The default value is **0**, and uses current UTC time – GETUTCDATE() – 2007-05-04 01:34:11.933.</span></span> <span data-ttu-id="0cbee-175">場合設定**1**、ローカル時刻 – GETDATE() – 2007-05-03 18:34:11.933 を使用して、</span><span class="sxs-lookup"><span data-stu-id="0cbee-175">If set to **1**, then it uses local time – GETDATE() – 2007-05-03 18:34:11.933</span></span>
  
    <span data-ttu-id="0cbee-176">次の例では、毎日のバックアップが午前 2 は、作成され、m:\ ドライブに格納されています。</span><span class="sxs-lookup"><span data-stu-id="0cbee-176">In the following example, daily backups are created at 2am, and stored in the m:\ drive:</span></span>  
  
    ```  
    exec [dbo].[sp_BackupAllFull_Schedule]   
    'd' /* Frequency */,   
    'BTS' /* Name */,   
    'm:\BizTalkBackups' /* location of backup files */,   
    '0' /* 0 (default) or 1 ForceFullBackupAfterPartialSetFailure */,   
    '2' /* local time hour for the backup process to run */  
    ```  

    <span data-ttu-id="0cbee-177">次の例では、毎週のバックアップは UTC 時刻で午前 0 時に作成され、Azure blob アカウントに格納されています。</span><span class="sxs-lookup"><span data-stu-id="0cbee-177">In the following example, weekly backups are created at midnight UTC time, and stored in your Azure blob account:</span></span> 

    ```  
    exec [dbo].[sp_BackupAllFull_Schedule]   
    'w' /* Frequency */,   
    'BTS' /* Name */,   
    'http://yourstorageaccount.blob.core.windows.net/yourcontainer/' /* location of backup files */,   
    '1' /* 0 (default) or 1 ForceFullBackupAfterPartialSetFailure */
    ```  

     <span data-ttu-id="0cbee-178">**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0cbee-178">Select **OK**.</span></span>  
  
6.  <span data-ttu-id="0cbee-179">選択、 **MarkAndBackupLog**ステップ、および選択**編集**です。</span><span class="sxs-lookup"><span data-stu-id="0cbee-179">Select the **MarkAndBackupLog** step, and select **Edit**.</span></span> <span data-ttu-id="0cbee-180">**コマンド**ボックスで、パラメーター値を更新します。</span><span class="sxs-lookup"><span data-stu-id="0cbee-180">In the **Command** box, update the parameter values:</span></span>  
  
    1.  <span data-ttu-id="0cbee-181">**@MarkName**: これは、バックアップ ファイルの名前付け規則の一部: <Server Name>  _<Database Name> **_ログ_**< Log Mark Name >_<Timestamp></span><span class="sxs-lookup"><span data-stu-id="0cbee-181">**@MarkName**: This is part of the naming convention for backup files: <Server Name>_<Database Name>**_Log_**< Log Mark Name >_<Timestamp></span></span>  
    
    2.  <span data-ttu-id="0cbee-182">**@BackupPath**: 完全な宛先 (単一引用符を含む)、コンピューターおよびフォルダー パスに格納する、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 、データベースのログ、または Azure blob ストレージ アカウントとコンテナー。</span><span class="sxs-lookup"><span data-stu-id="0cbee-182">**@BackupPath**: Full destination path (including single quotes) to the computer and folder to store the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] database logs, or the Azure blob storage account and container.</span></span> <span data-ttu-id="0cbee-183">*\<先のパス >*ローカルまたは別のサーバーへの UNC パスにもなります。</span><span class="sxs-lookup"><span data-stu-id="0cbee-183">The *\<destination path>* can also be local or a UNC path to another server.</span></span>  
  
     <span data-ttu-id="0cbee-184">MarkAndBackupLog ステップで、バックアップのログをマークした後、バックアップします。</span><span class="sxs-lookup"><span data-stu-id="0cbee-184">The MarkAndBackupLog step marks the logs for backup, and then backs them up.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="0cbee-185">回避する**データ損失の可能性**および**パフォーマンスを向上させる**、 *\<先のパス >*別のコンピューター、またはハード ドライブに設定する必要があります元のデータベース ログを格納するために使用されると異なる。</span><span class="sxs-lookup"><span data-stu-id="0cbee-185">To avoid **potential data loss** and for **performance improvement**, the *\<destination path>* should be set to a different computer, or hard drive, different from what is used to store the original database logs.</span></span>  
  
     <span data-ttu-id="0cbee-186">**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0cbee-186">Select **OK**.</span></span>  
  
7.  <span data-ttu-id="0cbee-187">選択、 **Clear Backup History**ステップ、および選択**編集**です。</span><span class="sxs-lookup"><span data-stu-id="0cbee-187">Select the **Clear Backup History** step, and select **Edit**.</span></span> <span data-ttu-id="0cbee-188">**コマンド**ボックスで、パラメーター値を更新します。</span><span class="sxs-lookup"><span data-stu-id="0cbee-188">In the **Command** box, update the parameter values:</span></span>  
  
    1.  <span data-ttu-id="0cbee-189">**@DaysToKeep**: 既定値は**14 日間**です。</span><span class="sxs-lookup"><span data-stu-id="0cbee-189">**@DaysToKeep**: Default value is **14 days**.</span></span> <span data-ttu-id="0cbee-190">バックアップ履歴が保持される期間決定、`Adm_BackupHistory`テーブル。</span><span class="sxs-lookup"><span data-stu-id="0cbee-190">Determines how long the backup history is kept in the `Adm_BackupHistory` table.</span></span> <span data-ttu-id="0cbee-191">管理は、定期的にバックアップ履歴の消去、`Adm_BackupHistory`適切なサイズにテーブルです。</span><span class="sxs-lookup"><span data-stu-id="0cbee-191">Periodically clearing the backup history helps maintain the `Adm_BackupHistory` table to an appropriate size.</span></span> 
    
    2.  <span data-ttu-id="0cbee-192">省略可。</span><span class="sxs-lookup"><span data-stu-id="0cbee-192">Optional.</span></span> <span data-ttu-id="0cbee-193">**@UseLocalTime**: ローカル時刻を使用する手順を説明します。</span><span class="sxs-lookup"><span data-stu-id="0cbee-193">**@UseLocalTime**: Tells the procedure to use local time.</span></span> <span data-ttu-id="0cbee-194">既定値は 0 です。</span><span class="sxs-lookup"><span data-stu-id="0cbee-194">The default value is 0.</span></span> <span data-ttu-id="0cbee-195">現在の UTC 時刻 – GETUTCDATE() – 2007-05-04 01:34:11.933 を使用します。</span><span class="sxs-lookup"><span data-stu-id="0cbee-195">It uses current UTC time – GETUTCDATE() – 2007-05-04 01:34:11.933.</span></span> <span data-ttu-id="0cbee-196">かどうか 1 に設定を使用してローカル時刻 – GETDATE() – 2007-05-03 18:34:11.933</span><span class="sxs-lookup"><span data-stu-id="0cbee-196">If set to 1, then it uses local time – GETDATE() – 2007-05-03 18:34:11.933</span></span>
  
    ```  
    exec [dbo].[sp_DeleteBackupHistory] @DaysToKeep=14, @UseLocalTime =1 
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="0cbee-197">この手順**しない**バックアップ ファイルの保存先のパスから削除します。</span><span class="sxs-lookup"><span data-stu-id="0cbee-197">This step **does not** delete backup files from the destination path.</span></span>  
    
     <span data-ttu-id="0cbee-198">選択**OK**してすべてのプロパティ ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="0cbee-198">Select **OK** and close all property windows.</span></span>  
  
8.  <span data-ttu-id="0cbee-199">省略可。</span><span class="sxs-lookup"><span data-stu-id="0cbee-199">Optional.</span></span> <span data-ttu-id="0cbee-200">バックアップのスケジュールを変更します。</span><span class="sxs-lookup"><span data-stu-id="0cbee-200">Change the backup schedule.</span></span> <span data-ttu-id="0cbee-201">参照してください[バックアップの BizTalk Server のジョブをスケジュールする方法](../core/how-to-schedule-the-backup-biztalk-server-job.md)です。</span><span class="sxs-lookup"><span data-stu-id="0cbee-201">See [How to Schedule the Backup BizTalk Server Job](../core/how-to-schedule-the-backup-biztalk-server-job.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0cbee-202">バックアップ[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ジョブが初めて構成することを実行します。</span><span class="sxs-lookup"><span data-stu-id="0cbee-202">The Backup [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] job runs the first time you configure it.</span></span> <span data-ttu-id="0cbee-203">既定では、後続の実行、バックアップ[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ジョブは 1 日に 1 回完全バックアップを完了して、15 分ごとにログ バックアップを完了します。</span><span class="sxs-lookup"><span data-stu-id="0cbee-203">By default, on subsequent runs, the Backup [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] job completes a full backup once a day, and completes log backups every 15 minutes.</span></span>  
  
9. <span data-ttu-id="0cbee-204">右クリックし、 **Backup BizTalk Server**ジョブ、および選択**を有効にする**です。</span><span class="sxs-lookup"><span data-stu-id="0cbee-204">Right-click the **Backup BizTalk Server** job, and select **Enable**.</span></span> <span data-ttu-id="0cbee-205">状態に変更する必要があります**成功**です。</span><span class="sxs-lookup"><span data-stu-id="0cbee-205">The status should change to **Success**.</span></span>  

## <a name="execute-backupsetupallprocssql-and-logshippingdestinationlogicsql"></a><span data-ttu-id="0cbee-206">Backup_Setup_All_Procs.sql および LogShipping_Destination_Logic.sql を実行します。</span><span class="sxs-lookup"><span data-stu-id="0cbee-206">Execute Backup_Setup_All_Procs.sql and LogShipping_Destination_Logic.sql</span></span>

<span data-ttu-id="0cbee-207">**[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]機能パック 2 (FP2)**で Backup_Setup_All_Procs.sql および LogShipping_Destination_Logic.sql スクリプトを使用する`\Program Files (x86)\Microsoft BizTalk Server *your version*\Schema`です。</span><span class="sxs-lookup"><span data-stu-id="0cbee-207">**[!INCLUDE[bts2016_md](../includes/bts2016-md.md)] Feature Pack 2 (FP2)** used the Backup_Setup_All_Procs.sql and LogShipping_Destination_Logic.sql scripts in `\Program Files (x86)\Microsoft BizTalk Server *your version*\Schema`.</span></span> 

<span data-ttu-id="0cbee-208">BizTalk Server のバックアップ ジョブが既に構成されているし、切り替えたい場合は、Azure を使用する (ディスク) ではなく blob も、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="0cbee-208">If your Backup BizTalk Server job is already configured, and you want to switch to using Azure blob (instead of a disk), then also do the following:</span></span> 

1. <span data-ttu-id="0cbee-209">SQL Server を実行、 `Backup_Setup_All_Procs.sql` BizTalk Server のバックアップ ジョブでバックアップされているすべてのカスタム データベースに対してスクリプト。</span><span class="sxs-lookup"><span data-stu-id="0cbee-209">On the SQL Server, execute the `Backup_Setup_All_Procs.sql` script against all custom databases that are being backed up by the Backup BizTalk Server job.</span></span> <span data-ttu-id="0cbee-210">既定では、FP2 自動的に更新プログラムの BizTalk データベースです。カスタム データベースは更新されません (それらのデータベースで、 `adm_OtherBackupDatabases` BizTalkMgmtDb 内のテーブル)。</span><span class="sxs-lookup"><span data-stu-id="0cbee-210">By default, FP2 automatically updates BizTalk databases; it does not update any custom databases (those databases in the `adm_OtherBackupDatabases` table in BizTalkMgmtDb).</span></span>

    <span data-ttu-id="0cbee-211">[バックアップをカスタム データベース](how-to-back-up-custom-databases.md)カスタム データベースの詳細を提供します。</span><span class="sxs-lookup"><span data-stu-id="0cbee-211">[Back Up Custom Databases](how-to-back-up-custom-databases.md) provides more details on custom databases.</span></span> 

2. <span data-ttu-id="0cbee-212">**使用する場合[ログ配布](log-shipping.md)**、SQL Server 内で、送信先システムで LogShipping_Destination_Logic.sql スクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="0cbee-212">**If you use [log shipping](log-shipping.md)**, execute the LogShipping_Destination_Logic.sql script on the destination system within SQL Server.</span></span> <span data-ttu-id="0cbee-213">使用しない場合は、ログ配布、し、このスクリプトを実行しないでください。</span><span class="sxs-lookup"><span data-stu-id="0cbee-213">If you don't use log shipping, then do not execute this script.</span></span>

    <span data-ttu-id="0cbee-214">[ログ配布の送信先システムを構成する](how-to-configure-the-destination-system-for-log-shipping.md)送信先システムで詳細を提供します。</span><span class="sxs-lookup"><span data-stu-id="0cbee-214">[Configure the Destination System for Log Shipping](how-to-configure-the-destination-system-for-log-shipping.md) provides more details on the destination system.</span></span>

## <a name="spforcefullbackup-stored-procedure"></a><span data-ttu-id="0cbee-215">sp_ForceFullBackup ストアド プロシージャ</span><span class="sxs-lookup"><span data-stu-id="0cbee-215">sp_ForceFullBackup stored procedure</span></span>  
  
<span data-ttu-id="0cbee-216">**Sp_ForceFullBackup**ストアド プロシージャ、 **BizTalkMgmtDb**データベースは、アドホックのデータとログ ファイルの完全バックアップを実行するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="0cbee-216">The **sp_ForceFullBackup** stored procedure in the **BizTalkMgmtDb** database can be used to run an ad-hoc full backup of the data and log files.</span></span> <span data-ttu-id="0cbee-217">ストアド プロシージャで、adm_ForceFullBackup テーブルの値を 1 にして更新します。</span><span class="sxs-lookup"><span data-stu-id="0cbee-217">The stored procedure updates the adm_ForceFullBackup table with a value 1.</span></span> <span data-ttu-id="0cbee-218">次回のバックアップ[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ジョブを実行すると、データベースの完全バックアップ セットを作成します。</span><span class="sxs-lookup"><span data-stu-id="0cbee-218">The next time the Backup [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] job is ran, a full database backup set is created.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="0cbee-219">次の手順</span><span class="sxs-lookup"><span data-stu-id="0cbee-219">Next Steps</span></span>  
 <span data-ttu-id="0cbee-220">[ログ配布の送信先システムを構成します。](../core/how-to-configure-the-destination-system-for-log-shipping.md) </span><span class="sxs-lookup"><span data-stu-id="0cbee-220">[Configure the Destination System for Log Shipping](../core/how-to-configure-the-destination-system-for-log-shipping.md) </span></span>  
 [<span data-ttu-id="0cbee-221">BizTalk Server のバックアップ ジョブのスケジュールを設定する</span><span class="sxs-lookup"><span data-stu-id="0cbee-221">Schedule the Backup BizTalk Server Job</span></span>](../core/how-to-schedule-the-backup-biztalk-server-job.md)  
 [<span data-ttu-id="0cbee-222">Azure ストレージ アカウント</span><span class="sxs-lookup"><span data-stu-id="0cbee-222">Azure storage accounts</span></span>](https://docs.microsoft.com/azure/storage/common/storage-create-storage-account)  
 [<span data-ttu-id="0cbee-223">SQL Server Backup to URL</span><span class="sxs-lookup"><span data-stu-id="0cbee-223">SQL Server Backup to URL</span></span>](https://docs.microsoft.com/sql/relational-databases/backup-restore/sql-server-backup-to-url)
