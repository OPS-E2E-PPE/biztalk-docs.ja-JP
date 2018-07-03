---
title: バックアップ BizTalk Server ジョブの構成 |Microsoft Docs
description: ''
ms.custom: ''
ms.date: 11/22/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 026622c9-fcb4-4db0-af48-1379feb30372
caps.latest.revision: 42
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 64a6222ffbabad54d8908a7d8da5517786d9a0cc
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981091"
---
# <a name="configure-the-backup-biztalk-server-job"></a><span data-ttu-id="da5b2-102">バックアップ BizTalk Server ジョブを構成します。</span><span class="sxs-lookup"><span data-stu-id="da5b2-102">Configure the Backup BizTalk Server Job</span></span>
<span data-ttu-id="da5b2-103">インストールして、BizTalk Server を構成した後は、バックアップを構成する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データをバックアップするジョブ。</span><span class="sxs-lookup"><span data-stu-id="da5b2-103">After you install and configure BizTalk Server, configure the Backup [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] job to back up your data.</span></span> 

<span data-ttu-id="da5b2-104">**以降で[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]Feature Pack 2**データベースをバックアップしてファイルを Azure blob ストレージ アカウントにログインします。</span><span class="sxs-lookup"><span data-stu-id="da5b2-104">**Starting with [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] Feature Pack 2**, you can backup your databases and log files to an Azure blob storage account.</span></span> 


## <a name="overview"></a><span data-ttu-id="da5b2-105">概要</span><span class="sxs-lookup"><span data-stu-id="da5b2-105">Overview</span></span>
<span data-ttu-id="da5b2-106">**BizTalk Server のバックアップ (BizTalkMgmtDb)** ジョブには、次の手順が含まれています。</span><span class="sxs-lookup"><span data-stu-id="da5b2-106">The **Backup BizTalk Server (BizTalkMgmtDb)** job includes the following steps:</span></span>

-   <span data-ttu-id="da5b2-107">手順 1 –**圧縮オプションのセット**: を有効にするか、バックアップ中に圧縮を無効にします。</span><span class="sxs-lookup"><span data-stu-id="da5b2-107">Step 1 – **Set Compression Option**: Enable or disable compression during backup</span></span>

-   <span data-ttu-id="da5b2-108">手順 2 – **BackupFull**: 完全なデータベース、BizTalk Server データベースのバックアップの実行</span><span class="sxs-lookup"><span data-stu-id="da5b2-108">Step 2 – **BackupFull**: Runs full database backups of the BizTalk Server databases</span></span>

-   <span data-ttu-id="da5b2-109">手順 3 – **MarkAndBackUpLog**: BizTalk Server データベースのログをバックアップします。</span><span class="sxs-lookup"><span data-stu-id="da5b2-109">Step 3 – **MarkAndBackUpLog**: Backs up the BizTalk Server database logs</span></span>

-   <span data-ttu-id="da5b2-110">手順 4 –**バックアップ履歴を消去する**: バックアップの履歴が保持される期間を選択</span><span class="sxs-lookup"><span data-stu-id="da5b2-110">Step 4 – **Clear Backup History**: Choose how long the backup history is kept</span></span>

<span data-ttu-id="da5b2-111">このジョブを構成するには、する必要があります。</span><span class="sxs-lookup"><span data-stu-id="da5b2-111">To configure this job, you'll need to:</span></span>  
  
-   <span data-ttu-id="da5b2-112">プライマリ サーバーと移行先の SQL サーバーとその他のバックアップ オプション</span><span class="sxs-lookup"><span data-stu-id="da5b2-112">Identify the primary and destination SQL Servers and other backup options</span></span>
  
-   <span data-ttu-id="da5b2-113">データベースをバックアップする Windows ユーザー アカウントを選択し、このアカウントの SQL Server ログインを作成</span><span class="sxs-lookup"><span data-stu-id="da5b2-113">Choose a Windows user account to back up your databases, and create a SQL Server login for this account</span></span>
  
-   <span data-ttu-id="da5b2-114">SQL Server ログインを BizTalk Server データベース内の BTS_BACKUP_USERS データベース ロールにマップします。</span><span class="sxs-lookup"><span data-stu-id="da5b2-114">Map SQL Server logins to the BTS_BACKUP_USERS database role in the BizTalk Server databases</span></span>
  
-   <span data-ttu-id="da5b2-115">すべてのノードで MSDTC サービスをアクティブにします。</span><span class="sxs-lookup"><span data-stu-id="da5b2-115">Ensure MSDTC service is active on all nodes.</span></span> <span data-ttu-id="da5b2-116">それ以外の場合、ソース ノードと宛先ノードの間のリンク サーバーの追加は失敗します。</span><span class="sxs-lookup"><span data-stu-id="da5b2-116">Otherwise, adding a linked server between the source node and the destination node fails.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="da5b2-117">アンインストールの準備</span><span class="sxs-lookup"><span data-stu-id="da5b2-117">Before you begin</span></span>  
  
- <span data-ttu-id="da5b2-118">特定の構成およびバックアップ操作には、sysadmin SQL Server ロールのメンバーシップが必要とします。</span><span class="sxs-lookup"><span data-stu-id="da5b2-118">Certain configuration and backup operations require membership in the sysadmin SQL Server role.</span></span> <span data-ttu-id="da5b2-119">バックアップするため、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベースが SQL Server の sysadmin サーバー ロールのメンバーであるアカウントを使用して、プライマリ サーバーにサインインします。</span><span class="sxs-lookup"><span data-stu-id="da5b2-119">To back up your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases, sign in the primary server with an account that is a member of the SQL Server sysadmin Server role.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="da5b2-120"> 構成では、BTS_BACKUP_USERS データベース ロールに追加します。</span><span class="sxs-lookup"><span data-stu-id="da5b2-120"> configuration adds the BTS_BACKUP_USERS database role.</span></span> <span data-ttu-id="da5b2-121">データベース バックアップに使用するユーザー アカウントでは、プライマリ サーバーを除いて、バックアップに関係するすべての SQL Server のシステム管理者 (sysadmin SQL Server ロール) のアクセス許可は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="da5b2-121">The user account you use to back up your databases does not require System Administrator (sysadmin SQL Server role) permissions on all the SQL Servers that may be involved in a backup, except for the primary server.</span></span>  
  
- <span data-ttu-id="da5b2-122">実行に使用するサインイン アカウントを決定する、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベースのバックアップ。</span><span class="sxs-lookup"><span data-stu-id="da5b2-122">Decide which sign in account you use to run your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] database backups.</span></span> <span data-ttu-id="da5b2-123">ローカル アカウントを使用して、1 つ以上のアカウントを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="da5b2-123">You can use a local account, and you can use more than one account.</span></span> <span data-ttu-id="da5b2-124">一般に簡素化され、この用途専用で専用の 1 つの Windows ドメイン ユーザー アカウントを作成した方が安全です。</span><span class="sxs-lookup"><span data-stu-id="da5b2-124">But it is generally simpler and more secure to create one dedicated Windows domain user account specifically for this purpose.</span></span> <span data-ttu-id="da5b2-125">このユーザー用の SQL Server ログオン アカウントを構成し、バックアップ プロセスに参加するすべての SQL Server について、プライマリ (送信元) サーバーかセカンダリ (送信先) サーバーかにかかわらず、ユーザーを SQL Server ログインにマップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="da5b2-125">You must configure a SQL Server logon account for this user, and the user must be mapped to a SQL Server login for all of the SQL Servers that participate in the backup process, either as primary (source) or secondary (destination) servers.</span></span> <span data-ttu-id="da5b2-126">各 BizTalk BTS_BACKUP_USERS データベース ロールにこのユーザーを割り当てる、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]をバックアップするデータベースします。</span><span class="sxs-lookup"><span data-stu-id="da5b2-126">Assign this user to the BizTalk BTS_BACKUP_USERS database role for each of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases you back up.</span></span>  
  
- <span data-ttu-id="da5b2-127">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のバックアップ ジョブでは、期限切れのバックアップ ファイルが削除されないので、ディスク領域を節約するにはこれらのバックアップ ファイルを手動で管理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="da5b2-127">The Backup [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] job does not delete outdated backup files, so you need to manually manage those backup files to conserve disk space.</span></span> <span data-ttu-id="da5b2-128">データベースの完全バックアップを新規作成した後で、プライマリ ディスクの領域を再利用できるように、期限切れのバックアップ ファイルをアーカイブ ストレージ デバイスに移動します。</span><span class="sxs-lookup"><span data-stu-id="da5b2-128">After you have created a new full backup of your databases, you should move the outdated backup files onto an archival storage device to reclaim space on the primary disk.</span></span> <span data-ttu-id="da5b2-129">参照してください、 [SSIS パッケージ](http://www.biztalkbill.com/2015/05/26/ssis-packages-to-help-management-biztalk-server-environments/)これらのファイルを管理します。</span><span class="sxs-lookup"><span data-stu-id="da5b2-129">See the [SSIS packages](http://www.biztalkbill.com/2015/05/26/ssis-packages-to-help-management-biztalk-server-environments/) to manage these files.</span></span>  
  
- [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="da5b2-130"> BizTalk 追跡データベースに直接追跡データを書き込みませんなく、メッセージ ボックス データベースにデータをキャッシュしてから、BizTalk 追跡データベースに移動します。</span><span class="sxs-lookup"><span data-stu-id="da5b2-130"> does not write tracking data directly to the BizTalk Tracking database; rather it caches the data in the MessageBox database, and then moves it to the BizTalk Tracking database.</span></span> <span data-ttu-id="da5b2-131">メッセージ ボックス データの損失が発生した場合は、追跡データも一部が失われている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="da5b2-131">If MessageBox data loss occurs, some tracking data may also be lost.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="da5b2-132">前提条件</span><span class="sxs-lookup"><span data-stu-id="da5b2-132">Prerequisites</span></span>  
* <span data-ttu-id="da5b2-133">SQL Server の sysadmin SQL Server ロールのメンバーであるアカウントを使用してにサインインします。</span><span class="sxs-lookup"><span data-stu-id="da5b2-133">Sign in to SQL Server using an account that is a member of the sysadmin SQL Server role.</span></span>  
  
* <span data-ttu-id="da5b2-134">SQL Server エージェント サービスは、SQL Server の各インスタンス上にユーザー ログインがマップされたドメイン アカウントまたはローカル アカウントで実行されるように構成します。ローカル アカウントも使用できますが、ドメイン アカウントの使用をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="da5b2-134">Configure the SQL Server Agent service to run under a domain account (recommended, although local accounts can be used), with a mapped user login on each instance of SQL Server.</span></span>  

* <span data-ttu-id="da5b2-135">Azure blob ストレージ アカウントを使用する必要が、 [general purpose ストレージ アカウント](https://docs.microsoft.com/azure/storage/common/storage-create-storage-account#create-a-storage-account)、blob ストレージ アカウント内のコンテナーを[共有アクセス署名](https://docs.microsoft.com/sql/relational-databases/backup-restore/sql-server-backup-to-url#SAS)(SAS) と[SQL 資格情報SAS を使って](https://docs.microsoft.com/sql/relational-databases/backup-restore/sql-server-backup-to-url#credential)します。</span><span class="sxs-lookup"><span data-stu-id="da5b2-135">To use an Azure blob storage account, you need a [general purpose storage account](https://docs.microsoft.com/azure/storage/common/storage-create-storage-account#create-a-storage-account), a container within your blob storage account, a [shared access signature](https://docs.microsoft.com/sql/relational-databases/backup-restore/sql-server-backup-to-url#SAS) (SAS), and a [SQL credential using the SAS](https://docs.microsoft.com/sql/relational-databases/backup-restore/sql-server-backup-to-url#credential).</span></span> <span data-ttu-id="da5b2-136">作成されると、blob サービス エンドポイントの URL、https:// ようなものであるがある<em>yourstorageaccount</em>.blob.core.windows.net/*containername*します。</span><span class="sxs-lookup"><span data-stu-id="da5b2-136">Once created, have your blob service endpoint URL ready, which is something like https://<em>yourstorageaccount</em>.blob.core.windows.net/*containername*.</span></span> 

    > [!TIP]
    > <span data-ttu-id="da5b2-137">既存の blob ストレージ アカウントの SAS を使用して構成していない場合、 [SAS PowerShell スクリプト](https://docs.microsoft.com/sql/relational-databases/backup-restore/sql-server-backup-to-url#SAS)およびコンテナーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="da5b2-137">If you don't have an existing blob storage account configured with a SAS, then the [SAS PowerShell script](https://docs.microsoft.com/sql/relational-databases/backup-restore/sql-server-backup-to-url#SAS) can create it, and the container.</span></span> <span data-ttu-id="da5b2-138">[SQL Server Backup to URL](https://docs.microsoft.com/sql/relational-databases/backup-restore/sql-server-backup-to-url)概要についてと具体的な手順を提供します。</span><span class="sxs-lookup"><span data-stu-id="da5b2-138">[SQL Server Backup to URL](https://docs.microsoft.com/sql/relational-databases/backup-restore/sql-server-backup-to-url) provides an overview, and the specific steps.</span></span>
  
## <a name="configure-the-job"></a><span data-ttu-id="da5b2-139">ジョブを構成します。</span><span class="sxs-lookup"><span data-stu-id="da5b2-139">Configure the job</span></span>  
  
1. <span data-ttu-id="da5b2-140">BizTalk 管理データベースをホストする SQL Server で開きます**SQL Server Management Studio**に接続して、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="da5b2-140">On the SQL Server that hosts the BizTalk Management database, open **SQL Server Management Studio**, and connect to your [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)].</span></span>  
  
2. <span data-ttu-id="da5b2-141">**[SQL Server エージェント]** を展開し、**[ジョブ]** を展開します。</span><span class="sxs-lookup"><span data-stu-id="da5b2-141">Expand **SQL Server Agent**, and expand **Jobs**.</span></span>  
  
3. <span data-ttu-id="da5b2-142">右クリック**BizTalk Server のバックアップ (BizTalkMgmtDb)** 選択**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="da5b2-142">Right-click **Backup BizTalk Server (BizTalkMgmtDb)** and select **Properties**.</span></span> <span data-ttu-id="da5b2-143">ジョブのプロパティで選択**手順**します。</span><span class="sxs-lookup"><span data-stu-id="da5b2-143">In the job properties, select **Steps**.</span></span>  
  
4. <span data-ttu-id="da5b2-144">選択、 **Set Compression Option**手順、および選択**編集**:</span><span class="sxs-lookup"><span data-stu-id="da5b2-144">Select the **Set Compression Option** step, and select **Edit**:</span></span>  

   <span data-ttu-id="da5b2-145">このステップでは、`sp_SetBackupCompression`で値を設定する BizTalk 管理データベース (BizTalkMgmtDb) にストアド プロシージャ、`adm_BackupSettings`テーブル。</span><span class="sxs-lookup"><span data-stu-id="da5b2-145">This step calls the `sp_SetBackupCompression` stored procedure in the BizTalk management database (BizTalkMgmtDb) to set the value on the `adm_BackupSettings` table.</span></span> <span data-ttu-id="da5b2-146">ストアド プロシージャが 1 つのパラメーター:  <strong>@bCompression</strong>します。</span><span class="sxs-lookup"><span data-stu-id="da5b2-146">The stored procedure has one parameter: <strong>@bCompression</strong>.</span></span> <span data-ttu-id="da5b2-147">既定では、設定が**0** (バックアップの圧縮はオフ)。</span><span class="sxs-lookup"><span data-stu-id="da5b2-147">By default, it is set to **0** (backup compression is off).</span></span> <span data-ttu-id="da5b2-148">圧縮を適用する値に変更**1**:</span><span class="sxs-lookup"><span data-stu-id="da5b2-148">To apply compression, change the value to **1**:</span></span>  
  
   ```  
   exec [dbo].[sp_SetBackupCompression] @bCompression = 1 /*0 - Do not use Compression, 1 - Use Compression */  
   ```  
  
    <span data-ttu-id="da5b2-149">**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="da5b2-149">Select **OK**.</span></span>  
  
5. <span data-ttu-id="da5b2-150">選択、 **BackupFull**手順、および選択**編集**します。</span><span class="sxs-lookup"><span data-stu-id="da5b2-150">Select the **BackupFull** step, and select **Edit**.</span></span> <span data-ttu-id="da5b2-151">**コマンド**ボックスに、パラメーター値を更新します。</span><span class="sxs-lookup"><span data-stu-id="da5b2-151">In the **Command** box, update the parameter values:</span></span>  
  
   1. <span data-ttu-id="da5b2-152">**頻度**: 既定値は**d** (毎日) です。 これは推奨の設定。</span><span class="sxs-lookup"><span data-stu-id="da5b2-152">**Frequency**: The default is **d** (daily); which is the recommended setting.</span></span> <span data-ttu-id="da5b2-153">その他の値が含まれます**h** (時間)、 **w** (毎週)、 **m** (毎月)、または**y** (年単位)。</span><span class="sxs-lookup"><span data-stu-id="da5b2-153">Other values include **h** (hourly), **w** (weekly), **m** (monthly), or **y** (yearly).</span></span>  
  
   2. <span data-ttu-id="da5b2-154">**名前**: 既定値は**BTS**します。</span><span class="sxs-lookup"><span data-stu-id="da5b2-154">**Name**: The default is **BTS**.</span></span> <span data-ttu-id="da5b2-155">この名前は、バックアップ ファイル名の一部として使用されます。</span><span class="sxs-lookup"><span data-stu-id="da5b2-155">The name is used as part of the backup file name.</span></span>  
  
   3. <span data-ttu-id="da5b2-156">**バックアップ ファイルの場所**: 置換 '*\<宛先パス\>*' をコンピューターと、をバックアップするフォルダーに完全パス(パスは、単一引用符を含める必要があります)で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース、または Azure blob storage アカウントに blob サービス エンドポイントの URL。</span><span class="sxs-lookup"><span data-stu-id="da5b2-156">**Location of backup files**: Replace '*\<destination path\>*' with the full path (the path must include the single quotes) to the computer and folder where you want to back up the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases, or the blob service endpoint URL to an Azure blob storage account.</span></span>  

      > [!IMPORTANT]
      > - <span data-ttu-id="da5b2-157">ローカル パスを入力するかどうかは、ターゲット システム上の同じフォルダーにすべてのファイルを手動でコピーする必要があるたびに、バックアップ[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ジョブには、新しいファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="da5b2-157">If you enter a local path, then you have to manually copy all the files to the same folder on the destination system whenever the Backup [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] job creates new files.</span></span>  
      > 
      >      <span data-ttu-id="da5b2-158">リモート パスを使用するには、UNC 共有をなど入力\\ \\  *\<ServerName\>*\\*\<SharedDrive\>* \\ここで、 *\<ServerName\>* 、ファイル サーバーの名前を指定し、 *\<SharedDrive\>* 共有ドライブまたはフォルダーの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="da5b2-158">To use a remote path, enter a UNC share such as \\\\*\<ServerName\>*\\*\<SharedDrive\>*\\, where *\<ServerName\>* is the name of the server where you want the files, and *\<SharedDrive\>* is name of the shared drive or folder.</span></span>  
      > 
      >      <span data-ttu-id="da5b2-159">ネットワーク経由でデータをバックアップする場合は、ネットワークの影響を受けます。</span><span class="sxs-lookup"><span data-stu-id="da5b2-159">Backing up data over a network is subject to any network issues.</span></span> <span data-ttu-id="da5b2-160">リモートの場所を使用する場合は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のバックアップ ジョブの完了時にバックアップが成功したかどうか確認します。</span><span class="sxs-lookup"><span data-stu-id="da5b2-160">When using a remote location, verify the backup succeeded when the Backup [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] job finishes.</span></span>  
      > - <span data-ttu-id="da5b2-161">データ損失の可能性を回避するには、バックアップ ディスクを、データベースのデータ ディスクおよびログ ディスクとは異なるディスクに構成します。</span><span class="sxs-lookup"><span data-stu-id="da5b2-161">To avoid potential data loss, configure the backup disk to be a different disk than the database data and log disks.</span></span> <span data-ttu-id="da5b2-162">これは、データやログのディスクに障害が発生した場合にバックアップにアクセスするために必須です。</span><span class="sxs-lookup"><span data-stu-id="da5b2-162">This is necessary so you can access the backups if the data or log disk fails.</span></span>  
      > - <span data-ttu-id="da5b2-163">Azure blob アカウントへのバックアップの入力と、 **Blob service エンドポイント**で、blob サービスのプロパティに示されている URL と、コンテナー名、 [Azure portal](https://portal.azure.com)。</span><span class="sxs-lookup"><span data-stu-id="da5b2-163">When backing up to an Azure blob account, enter the **Blob service endpoint** URL and the container name, which are listed in your blob service properties in the [Azure portal](https://portal.azure.com).</span></span>

   4. <span data-ttu-id="da5b2-164">任意。</span><span class="sxs-lookup"><span data-stu-id="da5b2-164">Optional.</span></span> <span data-ttu-id="da5b2-165">**部分バックアップに失敗した後、完全バックアップを強制**(@ForceFullBackupAfterPartialSetFailure): 既定値は**0**します。</span><span class="sxs-lookup"><span data-stu-id="da5b2-165">**Force full backup after partial backup failures** (@ForceFullBackupAfterPartialSetFailure): The default is **0**.</span></span> <span data-ttu-id="da5b2-166">ログ バックアップに失敗した場合、次の完全バックアップ間隔に達するまで、完全バックアップは実行しません。</span><span class="sxs-lookup"><span data-stu-id="da5b2-166">If a log backup fails, no full backups are ran until the next full backup frequency interval is reached.</span></span> <span data-ttu-id="da5b2-167">置き換える**1**ログ バックアップの失敗が発生するたびに、完全バックアップが実行された場合。</span><span class="sxs-lookup"><span data-stu-id="da5b2-167">Replace with **1** if you want a full backup ran whenever a log backup failure occurs.</span></span>
    
   5. <span data-ttu-id="da5b2-168">任意。</span><span class="sxs-lookup"><span data-stu-id="da5b2-168">Optional.</span></span> <span data-ttu-id="da5b2-169">**バックアップ プロセスの実行をローカル時刻に 1 時間**(@BackupHour): 既定値は**NULL**します。</span><span class="sxs-lookup"><span data-stu-id="da5b2-169">**Local time hour for the backup process to run** (@BackupHour): The default is **NULL**.</span></span> <span data-ttu-id="da5b2-170">バックアップ ジョブのタイム ゾーンに関連付けられていない、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]コンピューター、および実行時の午前 0 時 (utc) 時刻 (0000)。</span><span class="sxs-lookup"><span data-stu-id="da5b2-170">The backup job is not associated with the time zone of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computer, and runs at midnight UTC time (0000).</span></span> <span data-ttu-id="da5b2-171">する場合、特定の時間のタイム ゾーンでのバックアップ、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]コンピューターが現地時間として整数値を 0 (深夜) から 23 (11 PM) に入力します。</span><span class="sxs-lookup"><span data-stu-id="da5b2-171">If you want to backup at a specific hour in the time zone of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computer, enter an integer value from 0 (midnight) to 23 (11 PM) as the local time hour.</span></span> 

   6. <span data-ttu-id="da5b2-172">任意。</span><span class="sxs-lookup"><span data-stu-id="da5b2-172">Optional.</span></span> <span data-ttu-id="da5b2-173">**ローカル時刻を使用して、** (@UseLocalTime): ローカル時刻を使用する手順を示します。</span><span class="sxs-lookup"><span data-stu-id="da5b2-173">**Use local time** (@UseLocalTime): Tells the procedure to use local time.</span></span> <span data-ttu-id="da5b2-174">既定値は**0**、現在の UTC 時刻 – GETUTCDATE() – 2007-05-04 01:34:11.933 を使用しています。</span><span class="sxs-lookup"><span data-stu-id="da5b2-174">The default value is **0**, and uses current UTC time – GETUTCDATE() – 2007-05-04 01:34:11.933.</span></span> <span data-ttu-id="da5b2-175">場合設定**1**、現地時刻 – GETDATE() – 2007-05-03 18:34:11.933 を使用して、</span><span class="sxs-lookup"><span data-stu-id="da5b2-175">If set to **1**, then it uses local time – GETDATE() – 2007-05-03 18:34:11.933</span></span>
  
   <span data-ttu-id="da5b2-176">次の例では、毎日のバックアップが午前 2 時に作成され、m:\ ドライブに格納されています。</span><span class="sxs-lookup"><span data-stu-id="da5b2-176">In the following example, daily backups are created at 2am, and stored in the m:\ drive:</span></span>  
  
   ```  
   exec [dbo].[sp_BackupAllFull_Schedule]   
   'd' /* Frequency */,   
   'BTS' /* Name */,   
   'm:\BizTalkBackups' /* location of backup files */,   
   '0' /* 0 (default) or 1 ForceFullBackupAfterPartialSetFailure */,   
   '2' /* local time hour for the backup process to run */  
   ```  

   <span data-ttu-id="da5b2-177">次の例では、毎週のバックアップは UTC 時刻で午前 0 時に作成され、Azure blob アカウントに格納されています。</span><span class="sxs-lookup"><span data-stu-id="da5b2-177">In the following example, weekly backups are created at midnight UTC time, and stored in your Azure blob account:</span></span> 

   ```  
   exec [dbo].[sp_BackupAllFull_Schedule]   
   'w' /* Frequency */,   
   'BTS' /* Name */,   
   'http://yourstorageaccount.blob.core.windows.net/yourcontainer/' /* location of backup files */,   
   '1' /* 0 (default) or 1 ForceFullBackupAfterPartialSetFailure */
   ```  

    <span data-ttu-id="da5b2-178">**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="da5b2-178">Select **OK**.</span></span>  
  
6. <span data-ttu-id="da5b2-179">選択、 **MarkAndBackupLog**手順、および選択**編集**します。</span><span class="sxs-lookup"><span data-stu-id="da5b2-179">Select the **MarkAndBackupLog** step, and select **Edit**.</span></span> <span data-ttu-id="da5b2-180">**コマンド**ボックスに、パラメーター値を更新します。</span><span class="sxs-lookup"><span data-stu-id="da5b2-180">In the **Command** box, update the parameter values:</span></span>  
  
   1. <span data-ttu-id="da5b2-181"><strong>@MarkName</strong>: これは、バックアップ ファイルの名前付け規則の一部:\<サーバー名\>\_\<データベース名\>**\_ログ\_** \<ログ マーク名\> \_\<タイムスタンプ\></span><span class="sxs-lookup"><span data-stu-id="da5b2-181"><strong>@MarkName</strong>: This is part of the naming convention for backup files: \<Server Name\>\_\<Database Name\>**\_Log\_**\< Log Mark Name \>\_\<Timestamp\></span></span>  
    
   2. <span data-ttu-id="da5b2-182"><strong>@BackupPath</strong>: コンピューターに格納するフォルダー完全な宛先パス (単一引用符を含む)、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース ログ、または Azure blob ストレージ アカウントとコンテナー。</span><span class="sxs-lookup"><span data-stu-id="da5b2-182"><strong>@BackupPath</strong>: Full destination path (including single quotes) to the computer and folder to store the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] database logs, or the Azure blob storage account and container.</span></span> <span data-ttu-id="da5b2-183">*\<宛先パス\>* ローカルまたは別のサーバーへの UNC パスにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="da5b2-183">The *\<destination path\>* can also be local or a UNC path to another server.</span></span>  
  
      <span data-ttu-id="da5b2-184">MarkAndBackupLog ステップで、バックアップのログをマークした後、バックアップします。</span><span class="sxs-lookup"><span data-stu-id="da5b2-184">The MarkAndBackupLog step marks the logs for backup, and then backs them up.</span></span>  
  
   > [!IMPORTANT]
   >  <span data-ttu-id="da5b2-185">回避するために**データ損失の可能性**および**パフォーマンスの向上**、 *\<宛先パス\>* 別のコンピューターに設定する必要がありますまたは、ハード ドライブ、元のデータベース ログの格納で使用したものと異なる。</span><span class="sxs-lookup"><span data-stu-id="da5b2-185">To avoid **potential data loss** and for **performance improvement**, the *\<destination path\>* should be set to a different computer, or hard drive, different from what is used to store the original database logs.</span></span>  
  
    <span data-ttu-id="da5b2-186">**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="da5b2-186">Select **OK**.</span></span>  
  
7. <span data-ttu-id="da5b2-187">選択、 **Clear Backup History**手順、および選択**編集**します。</span><span class="sxs-lookup"><span data-stu-id="da5b2-187">Select the **Clear Backup History** step, and select **Edit**.</span></span> <span data-ttu-id="da5b2-188">**コマンド**ボックスに、パラメーター値を更新します。</span><span class="sxs-lookup"><span data-stu-id="da5b2-188">In the **Command** box, update the parameter values:</span></span>  
  
   1. <span data-ttu-id="da5b2-189"><strong>@DaysToKeep</strong>: 既定値は**14 日間**します。</span><span class="sxs-lookup"><span data-stu-id="da5b2-189"><strong>@DaysToKeep</strong>: Default value is **14 days**.</span></span> <span data-ttu-id="da5b2-190">バックアップ履歴が保持される期間決定、`Adm_BackupHistory`テーブル。</span><span class="sxs-lookup"><span data-stu-id="da5b2-190">Determines how long the backup history is kept in the `Adm_BackupHistory` table.</span></span> <span data-ttu-id="da5b2-191">定期的にバックアップ履歴の消去維持、`Adm_BackupHistory`テーブルに適切なサイズ。</span><span class="sxs-lookup"><span data-stu-id="da5b2-191">Periodically clearing the backup history helps maintain the `Adm_BackupHistory` table to an appropriate size.</span></span> 
    
   2. <span data-ttu-id="da5b2-192">任意。</span><span class="sxs-lookup"><span data-stu-id="da5b2-192">Optional.</span></span> <span data-ttu-id="da5b2-193"><strong>@UseLocalTime</strong>: ローカル時刻を使用する手順を伝えます。</span><span class="sxs-lookup"><span data-stu-id="da5b2-193"><strong>@UseLocalTime</strong>: Tells the procedure to use local time.</span></span> <span data-ttu-id="da5b2-194">既定値は 0 です。</span><span class="sxs-lookup"><span data-stu-id="da5b2-194">The default value is 0.</span></span> <span data-ttu-id="da5b2-195">現在の UTC 時刻 – GETUTCDATE() – 2007-05-04 01:34:11.933 を使用します。</span><span class="sxs-lookup"><span data-stu-id="da5b2-195">It uses current UTC time – GETUTCDATE() – 2007-05-04 01:34:11.933.</span></span> <span data-ttu-id="da5b2-196">かどうか 1 に設定すると、次を使用してローカル時刻 – GETDATE() – 2007-05-03 18:34:11.933</span><span class="sxs-lookup"><span data-stu-id="da5b2-196">If set to 1, then it uses local time – GETDATE() – 2007-05-03 18:34:11.933</span></span>
  
   ```  
   exec [dbo].[sp_DeleteBackupHistory] @DaysToKeep=14, @UseLocalTime =1 
   ```  
  
   > [!NOTE]
   >  <span data-ttu-id="da5b2-197">この手順**しない**デプロイ先のパスからバックアップ ファイルを削除します。</span><span class="sxs-lookup"><span data-stu-id="da5b2-197">This step **does not** delete backup files from the destination path.</span></span>  
    
    <span data-ttu-id="da5b2-198">選択**OK**してすべてのプロパティ ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="da5b2-198">Select **OK** and close all property windows.</span></span>  
  
8. <span data-ttu-id="da5b2-199">任意。</span><span class="sxs-lookup"><span data-stu-id="da5b2-199">Optional.</span></span> <span data-ttu-id="da5b2-200">バックアップのスケジュールを変更します。</span><span class="sxs-lookup"><span data-stu-id="da5b2-200">Change the backup schedule.</span></span> <span data-ttu-id="da5b2-201">参照してください[バックアップ BizTalk Server のジョブをスケジュールする方法](../core/how-to-schedule-the-backup-biztalk-server-job.md)します。</span><span class="sxs-lookup"><span data-stu-id="da5b2-201">See [How to Schedule the Backup BizTalk Server Job](../core/how-to-schedule-the-backup-biztalk-server-job.md).</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="da5b2-202">バックアップ[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ジョブが初めて構成することを実行します。</span><span class="sxs-lookup"><span data-stu-id="da5b2-202">The Backup [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] job runs the first time you configure it.</span></span> <span data-ttu-id="da5b2-203">既定では、その後の実行、バックアップ[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ジョブは 1 日に 1 回完全バックアップを完了して、15 分ごとにログ バックアップを完了します。</span><span class="sxs-lookup"><span data-stu-id="da5b2-203">By default, on subsequent runs, the Backup [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] job completes a full backup once a day, and completes log backups every 15 minutes.</span></span>  
  
9. <span data-ttu-id="da5b2-204">右クリックし、 **Backup BizTalk Server**ジョブ、および選択**を有効にする**します。</span><span class="sxs-lookup"><span data-stu-id="da5b2-204">Right-click the **Backup BizTalk Server** job, and select **Enable**.</span></span> <span data-ttu-id="da5b2-205">状態に変更する必要があります**成功**します。</span><span class="sxs-lookup"><span data-stu-id="da5b2-205">The status should change to **Success**.</span></span>  

## <a name="execute-backupsetupallprocssql-and-logshippingdestinationlogicsql"></a><span data-ttu-id="da5b2-206">Backup_Setup_All_Procs.sql および LogShipping_Destination_Logic.sql を実行します。</span><span class="sxs-lookup"><span data-stu-id="da5b2-206">Execute Backup_Setup_All_Procs.sql and LogShipping_Destination_Logic.sql</span></span>

<span data-ttu-id="da5b2-207">**[!INCLUDE[bts2016_md](../includes/bts2016-md.md)] Feature Pack 2 (FP2)** で Backup_Setup_All_Procs.sql および LogShipping_Destination_Logic.sql スクリプト`\Program Files (x86)\Microsoft BizTalk Server *your version*\Schema`します。</span><span class="sxs-lookup"><span data-stu-id="da5b2-207">**[!INCLUDE[bts2016_md](../includes/bts2016-md.md)] Feature Pack 2 (FP2)** used the Backup_Setup_All_Procs.sql and LogShipping_Destination_Logic.sql scripts in `\Program Files (x86)\Microsoft BizTalk Server *your version*\Schema`.</span></span> 

<span data-ttu-id="da5b2-208">BizTalk Server のバックアップ ジョブが既に構成されているし、切り替えたい場合 (ディスク) ではなく blob に Azure を使用しも、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="da5b2-208">If your Backup BizTalk Server job is already configured, and you want to switch to using Azure blob (instead of a disk), then also do the following:</span></span> 

1. <span data-ttu-id="da5b2-209">SQL Server では、実行、`Backup_Setup_All_Procs.sql`が BizTalk Server のバックアップ ジョブによってバックアップされているすべてのカスタム データベースに対してスクリプト。</span><span class="sxs-lookup"><span data-stu-id="da5b2-209">On the SQL Server, execute the `Backup_Setup_All_Procs.sql` script against all custom databases that are being backed up by the Backup BizTalk Server job.</span></span> <span data-ttu-id="da5b2-210">既定では、FP2 自動的に更新プログラムの BizTalk データベースすべてのカスタム データベースは更新されません (これらのデータベースで、 `adm_OtherBackupDatabases` BizTalkMgmtDb 内のテーブル)。</span><span class="sxs-lookup"><span data-stu-id="da5b2-210">By default, FP2 automatically updates BizTalk databases; it does not update any custom databases (those databases in the `adm_OtherBackupDatabases` table in BizTalkMgmtDb).</span></span>

    <span data-ttu-id="da5b2-211">[バックアップをカスタム データベース](how-to-back-up-custom-databases.md)カスタム データベース詳細が示されます。</span><span class="sxs-lookup"><span data-stu-id="da5b2-211">[Back Up Custom Databases](how-to-back-up-custom-databases.md) provides more details on custom databases.</span></span> 

2. <span data-ttu-id="da5b2-212">**使用する場合[ログ配布](log-shipping.md)**、SQL Server 内で、送信先システムで LogShipping_Destination_Logic.sql スクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="da5b2-212">**If you use [log shipping](log-shipping.md)**, execute the LogShipping_Destination_Logic.sql script on the destination system within SQL Server.</span></span> <span data-ttu-id="da5b2-213">使用しない場合は、ログ配布、し、このスクリプトを実行しないでください。</span><span class="sxs-lookup"><span data-stu-id="da5b2-213">If you don't use log shipping, then do not execute this script.</span></span>

    <span data-ttu-id="da5b2-214">[ログ配布の送信先システムを構成する](how-to-configure-the-destination-system-for-log-shipping.md)送信先システムで詳細を提供します。</span><span class="sxs-lookup"><span data-stu-id="da5b2-214">[Configure the Destination System for Log Shipping](how-to-configure-the-destination-system-for-log-shipping.md) provides more details on the destination system.</span></span>

## <a name="spforcefullbackup-stored-procedure"></a><span data-ttu-id="da5b2-215">sp_ForceFullBackup ストアド プロシージャ</span><span class="sxs-lookup"><span data-stu-id="da5b2-215">sp_ForceFullBackup stored procedure</span></span>  
  
<span data-ttu-id="da5b2-216">**Sp_ForceFullBackup**ストアド プロシージャ、 **BizTalkMgmtDb**データベースは、アドホックのデータとログ ファイルの完全バックアップを実行するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="da5b2-216">The **sp_ForceFullBackup** stored procedure in the **BizTalkMgmtDb** database can be used to run an ad-hoc full backup of the data and log files.</span></span> <span data-ttu-id="da5b2-217">ストアド プロシージャで、adm_ForceFullBackup テーブルの値を 1 にして更新します。</span><span class="sxs-lookup"><span data-stu-id="da5b2-217">The stored procedure updates the adm_ForceFullBackup table with a value 1.</span></span> <span data-ttu-id="da5b2-218">次回のバックアップ[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ジョブが実行されると、データベースの完全バックアップ セットが作成されます。</span><span class="sxs-lookup"><span data-stu-id="da5b2-218">The next time the Backup [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] job is ran, a full database backup set is created.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="da5b2-219">次の手順</span><span class="sxs-lookup"><span data-stu-id="da5b2-219">Next Steps</span></span>  
 <span data-ttu-id="da5b2-220">[ログ配布用の送信先システムを構成します。](../core/how-to-configure-the-destination-system-for-log-shipping.md) </span><span class="sxs-lookup"><span data-stu-id="da5b2-220">[Configure the Destination System for Log Shipping](../core/how-to-configure-the-destination-system-for-log-shipping.md) </span></span>  
 [<span data-ttu-id="da5b2-221">BizTalk Server のバックアップ ジョブのスケジュールを設定する</span><span class="sxs-lookup"><span data-stu-id="da5b2-221">Schedule the Backup BizTalk Server Job</span></span>](../core/how-to-schedule-the-backup-biztalk-server-job.md)  
 [<span data-ttu-id="da5b2-222">Azure ストレージ アカウント</span><span class="sxs-lookup"><span data-stu-id="da5b2-222">Azure storage accounts</span></span>](https://docs.microsoft.com/azure/storage/common/storage-create-storage-account)  
 [<span data-ttu-id="da5b2-223">SQL Server Backup to URL</span><span class="sxs-lookup"><span data-stu-id="da5b2-223">SQL Server Backup to URL</span></span>](https://docs.microsoft.com/sql/relational-databases/backup-restore/sql-server-backup-to-url)
