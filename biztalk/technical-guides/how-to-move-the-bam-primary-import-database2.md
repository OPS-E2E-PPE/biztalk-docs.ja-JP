---
title: BAM プライマリ インポートの Database2 を移動する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bc4f2656-2faa-4503-9551-05e1b6eceb1a
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fe36c4a8b9aa6d081ebde854e6a4c57f9492df67
ms.sourcegitcommit: 53b16fe6c1b1707ecf233dbd05f780653eb19419
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/01/2018
ms.locfileid: "50753210"
---
# <a name="how-to-move-the-bam-primary-import-database"></a><span data-ttu-id="67114-102">BAM プライマリ インポート データベースを移動する方法</span><span class="sxs-lookup"><span data-stu-id="67114-102">How to Move the BAM Primary Import Database</span></span>
<span data-ttu-id="67114-103">ここでは、BAM プライマリ インポート データベースを他のサーバーに移動する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="67114-103">You can use this procedure to move the BAM Primary Import database to another server.</span></span> <span data-ttu-id="67114-104">エンド ツー エンドのシナリオの観点から BAM プライマリ インポート データベースの移動にも 2 つの主要な手順が含まれます。</span><span class="sxs-lookup"><span data-stu-id="67114-104">From an end-to-end scenario perspective, moving the BAM Primary Import database involves two major steps:</span></span>  
  
-   [<span data-ttu-id="67114-105">BAM プライマリ インポート データベースを移動します。</span><span class="sxs-lookup"><span data-stu-id="67114-105">Moving the BAM Primary Import Database</span></span>](../technical-guides/how-to-move-the-bam-primary-import-database2.md#BKMK_MovingBAMPI)  
  
-   [<span data-ttu-id="67114-106">新しい BAM プライマリ インポート データベースへの参照を更新しています</span><span class="sxs-lookup"><span data-stu-id="67114-106">Updating References to the New BAM Primary Import Database</span></span>](../technical-guides/how-to-move-the-bam-primary-import-database2.md#BKMK_BAMPIRef)  
  
## <a name="prerequisites"></a><span data-ttu-id="67114-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="67114-107">Prerequisites</span></span>  
 <span data-ttu-id="67114-108">この手順を実行するには、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] sysadmin 固定サーバー ロールのメンバーであるアカウントを使用してログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="67114-108">You must be logged on with an account that is a member of the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] sysadmin fixed server role to perform this procedure.</span></span>  
  
##  <a name="BKMK_MovingBAMPI"></a> <span data-ttu-id="67114-109">BAM プライマリ インポート データベースを移動します。</span><span class="sxs-lookup"><span data-stu-id="67114-109">Moving the BAM Primary Import Database</span></span>  
 <span data-ttu-id="67114-110">BAM プライマリ インポート データベースを移動する次の手順で、手順に従います。</span><span class="sxs-lookup"><span data-stu-id="67114-110">Perform the steps in the following procedure to move the BAM Primary Import database.</span></span>  
  
#### <a name="to-move-the-bam-primary-import-database"></a><span data-ttu-id="67114-111">BAM プライマリ インポート データベースを移動するには</span><span class="sxs-lookup"><span data-stu-id="67114-111">To move the BAM Primary Import database</span></span>  
  
1. <span data-ttu-id="67114-112">すべての BAM キューブ更新およびデータ保守 SSIS パッケージを停止するか、BAM プライマリ インポート データベースを復元するまで実行を防ぐ。</span><span class="sxs-lookup"><span data-stu-id="67114-112">Stop any BAM cube update and data maintenance SSIS packages, or prevent them from running until you have restored the BAM Primary Import database.</span></span>  
  
2. <span data-ttu-id="67114-113">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] サービスをすべて停止します。</span><span class="sxs-lookup"><span data-stu-id="67114-113">Stop all [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] services.</span></span> <span data-ttu-id="67114-114">詳細については、トピックを参照してください。[方法を開始、停止、一時停止、再開、または BizTalk Server サービスを再起動](http://go.microsoft.com/fwlink/?LinkId=154394)(<http://go.microsoft.com/fwlink/?LinkId=154394>) で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。</span><span class="sxs-lookup"><span data-stu-id="67114-114">For more information, see the topic [How To Start, Stop, Pause, Resume, or Restart BizTalk Server Services](http://go.microsoft.com/fwlink/?LinkId=154394) (<http://go.microsoft.com/fwlink/?LinkId=154394>) in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help.</span></span>  
  
3. <span data-ttu-id="67114-115">IIS サービスを停止します。</span><span class="sxs-lookup"><span data-stu-id="67114-115">Stop the IIS service.</span></span>  
  
4. <span data-ttu-id="67114-116">BAM 警告 Notification service を停止します。</span><span class="sxs-lookup"><span data-stu-id="67114-116">Stop the BAM Alerts Notification service:</span></span>  
  
   1.  <span data-ttu-id="67114-117">をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリックします**OK**。</span><span class="sxs-lookup"><span data-stu-id="67114-117">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
   2.  <span data-ttu-id="67114-118">コマンド プロンプトで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="67114-118">At the command prompt, type:</span></span>  
  
        <span data-ttu-id="67114-119">**net stop NS$ BamAlerts**</span><span class="sxs-lookup"><span data-stu-id="67114-119">**Net stop NS$BamAlerts**</span></span>  
  
5. <span data-ttu-id="67114-120">BAM プライマリをバックアップするには、古いサーバー上のデータベースをインポートします。</span><span class="sxs-lookup"><span data-stu-id="67114-120">Back up the BAM Primary import database on the old server.</span></span> <span data-ttu-id="67114-121">データベースをバックアップする方法については次の手順については、データベースのバックアップの手順については、[方法:、データベースのバックアップ (SQL Server Management Studio)](http://go.microsoft.com/fwlink/?LinkId=156510) (<http://go.microsoft.com/fwlink/?LinkId=156510>) で[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]オンライン ブックの「します。</span><span class="sxs-lookup"><span data-stu-id="67114-121">For instructions on backing up a database, follow the instructions on how to back up a database at [How to: Back Up a Database (SQL Server Management Studio)](http://go.microsoft.com/fwlink/?LinkId=156510) (<http://go.microsoft.com/fwlink/?LinkId=156510>) in [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Books Online.</span></span>  
  
6. <span data-ttu-id="67114-122">BAM プライマリ インポート データベースのコピーを新しい[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]コンピューター。</span><span class="sxs-lookup"><span data-stu-id="67114-122">Copy the BAM Primary Import database to the new [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] computer.</span></span>  
  
7. <span data-ttu-id="67114-123">新しいサーバーで、BAM プライマリ インポート データベースを復元します。</span><span class="sxs-lookup"><span data-stu-id="67114-123">Restore the BAM Primary import database on the new server.</span></span> <span data-ttu-id="67114-124">データベースを復元する方法の指示に従って、データベースを復元する手順についての[方法: データベースのバックアップ (SQL Server Management Studio) 復元](http://go.microsoft.com/fwlink/?LinkId=156511)(<http://go.microsoft.com/fwlink/?LinkId=156511>) で[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]オンライン ブックの「します。</span><span class="sxs-lookup"><span data-stu-id="67114-124">For instructions on restoring the database, follow the instructions on how to restore a database at [How to: Restore a Database Backup (SQL Server Management Studio)](http://go.microsoft.com/fwlink/?LinkId=156511) (<http://go.microsoft.com/fwlink/?LinkId=156511>) in [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Books Online.</span></span>  
  
   > [!NOTE]  
   >  <span data-ttu-id="67114-125">BAM プライマリ インポート データベースをバックアップから復元する場合は、BAM プライマリよりも古いバックアップを使用して BAM アーカイブ、BAM スター スキーマ、および BAM 分析データベースも復元する必要があります。</span><span class="sxs-lookup"><span data-stu-id="67114-125">If you restore the BAM Primary Import database from a backup, then you should also restore the BAM Archive, BAM Star Schema, and BAM Analysis databases by using a backup older than the BAM Primary backup.</span></span>  
  
##  <a name="BKMK_BAMPIRef"></a> <span data-ttu-id="67114-126">新しい BAM プライマリ インポート データベースへの参照を更新しています</span><span class="sxs-lookup"><span data-stu-id="67114-126">Updating References to the New BAM Primary Import Database</span></span>  
 <span data-ttu-id="67114-127">データベースを移動した後は、新しい BAM プライマリ インポート データベースへのすべての参照を更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="67114-127">After you have moved the database, you must update all the references to the new BAM Primary Import Database.</span></span> <span data-ttu-id="67114-128">次の参照を更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="67114-128">The following references must be updated:</span></span>  
  
-   <span data-ttu-id="67114-129">新しいサーバー名では、すべての BizTalk データベースを更新します。</span><span class="sxs-lookup"><span data-stu-id="67114-129">Update all the BizTalk databases with the new server name.</span></span> <span data-ttu-id="67114-130">UpdateDatabase.vbs のスクリプトを使用して行うことができます。</span><span class="sxs-lookup"><span data-stu-id="67114-130">You can do so by using the UpdateDatabase.vbs script.</span></span> <span data-ttu-id="67114-131">参照してください[BizTalk データベースを新しいサーバー名で更新する](../technical-guides/how-to-move-the-bam-primary-import-database2.md#BKMK_UpdateDB)します。</span><span class="sxs-lookup"><span data-stu-id="67114-131">See [To update BizTalk Databases with the new server name](../technical-guides/how-to-move-the-bam-primary-import-database2.md#BKMK_UpdateDB).</span></span>  
  
-   <span data-ttu-id="67114-132">BAM ポータルの Web.config ファイルを更新します。</span><span class="sxs-lookup"><span data-stu-id="67114-132">Update the Web.config file for the BAM portal.</span></span> <span data-ttu-id="67114-133">参照してください[BAM ポータルの Web.config ファイルを更新する](../technical-guides/how-to-move-the-bam-primary-import-database2.md#BKMK_Config)します。</span><span class="sxs-lookup"><span data-stu-id="67114-133">See [To update the Web.config file for the BAM portal](../technical-guides/how-to-move-the-bam-primary-import-database2.md#BKMK_Config).</span></span>  
  
-   <span data-ttu-id="67114-134">すべての BAM ライブ データの Microsoft Excel ファイルで BAM プライマリ インポート データベースへの参照を更新します。</span><span class="sxs-lookup"><span data-stu-id="67114-134">Update the reference to the BAM Primary Import Database in all BAM Livedata Microsoft Excel files.</span></span> <span data-ttu-id="67114-135">参照してください[BAM ライブ データの Microsoft Excel ファイル内の参照を更新する](../technical-guides/how-to-move-the-bam-primary-import-database2.md#BKMK_UpdateExcel)します。</span><span class="sxs-lookup"><span data-stu-id="67114-135">See [To update reference in BAM Livedata Microsoft Excel files](../technical-guides/how-to-move-the-bam-primary-import-database2.md#BKMK_UpdateExcel).</span></span>  
  
-   <span data-ttu-id="67114-136">すべての BAM analysis の SSIS パッケージで新しいサーバーおよびデータベース名を更新します。</span><span class="sxs-lookup"><span data-stu-id="67114-136">Update the new server and database names in all BAM analysis SSIS packages.</span></span> <span data-ttu-id="67114-137">参照してください[サーバーとすべての BAM SSIS パッケージ内のデータベース名を更新する](../technical-guides/how-to-move-the-bam-primary-import-database2.md#BKMK_UpdatePckg)します。</span><span class="sxs-lookup"><span data-stu-id="67114-137">See [To update server and database names in all BAM SSIS packages](../technical-guides/how-to-move-the-bam-primary-import-database2.md#BKMK_UpdatePckg).</span></span>  
  
-   <span data-ttu-id="67114-138">サーバーとデータベースの新しい名前のデータ ソースのすべての OLAP キューブを更新します。</span><span class="sxs-lookup"><span data-stu-id="67114-138">Update the new server and database names in data sources for all OLAP cubes.</span></span> <span data-ttu-id="67114-139">参照してください[サーバーおよびすべての OLAP キューブのデータ ソース内のデータベース名を更新する](../technical-guides/how-to-move-the-bam-primary-import-database2.md#BKMK_UpdateDSOLAP)します。</span><span class="sxs-lookup"><span data-stu-id="67114-139">See [To update server and database names in data sources for all OLAP cubes](../technical-guides/how-to-move-the-bam-primary-import-database2.md#BKMK_UpdateDSOLAP).</span></span>  
  
###  <a name="BKMK_UpdateDB"></a> <span data-ttu-id="67114-140">BizTalk データベースを新しいサーバー名で更新するには</span><span class="sxs-lookup"><span data-stu-id="67114-140">To update BizTalk Databases with the new server name</span></span>  
  
1. <span data-ttu-id="67114-141">BizTalk Server を実行するコンピューター上には、次のフォルダーを参照してください。</span><span class="sxs-lookup"><span data-stu-id="67114-141">On a computer running BizTalk Server, browse to the following folder:</span></span>  
  
   - <span data-ttu-id="67114-142">場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]64 ビット バージョンの Windows Server にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="67114-142">If [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is installed on a 64-bit version of Windows Server:</span></span>  
  
      <span data-ttu-id="67114-143">**%ProgramFiles(x86)%\Microsoft BizTalk Server 2010\bins32\Schema\Restore**</span><span class="sxs-lookup"><span data-stu-id="67114-143">**%ProgramFiles(x86)%\Microsoft BizTalk Server 2010\bins32\Schema\Restore**</span></span>  
  
   - <span data-ttu-id="67114-144">場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]32 ビット バージョンの Windows Server にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="67114-144">If [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is installed on a 32-bit version of Windows Server:</span></span>  
  
      <span data-ttu-id="67114-145">**%ProgramFiles%\Microsoft BizTalk Server 2010\Schema\Restore**</span><span class="sxs-lookup"><span data-stu-id="67114-145">**%ProgramFiles%\Microsoft BizTalk Server 2010\Schema\Restore**</span></span>  
  
2. <span data-ttu-id="67114-146">右クリック**SampleUpdateInfo.xml**、 をクリックし、**編集**します。</span><span class="sxs-lookup"><span data-stu-id="67114-146">Right-click **SampleUpdateInfo.xml**, and then click **Edit**.</span></span>  
  
3. <span data-ttu-id="67114-147">BizTalkMgmtDb、OldPrimaryImportDatabase、PrimaryImportDatabase、ArchivingDatabase、AnalysisDatabase、StarSchemaDatabase、および Alert を除いて、すべてのデータベース セクションをコメント アウトします。</span><span class="sxs-lookup"><span data-stu-id="67114-147">Comment out all of the database sections except for the BizTalkMgmtDb, OldPrimaryImportDatabase, PrimaryImportDatabase, ArchivingDatabase, AnalysisDatabase, StarSchemaDatabase, and Alert.</span></span>  
  
4. <span data-ttu-id="67114-148">`OldPrimaryImportDatabase` 、ファイルのセクションの`ServerName`プロパティ、置き換える**SourceServer**データベースが存在する既存のサーバーの名前に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="67114-148">In the `OldPrimaryImportDatabase` section of the file, for the `ServerName` property, replace **SourceServer** with the name of existing server where the database resides.</span></span>  
  
5. <span data-ttu-id="67114-149">`PrimaryImportDatabase` 、ファイルのセクションの`ServerName`プロパティ、置き換える**DestinationServer**を BAM プライマリ インポート データベースを移動するサーバーの名前</span><span class="sxs-lookup"><span data-stu-id="67114-149">In the `PrimaryImportDatabase` section of the file, for the `ServerName` property, replace **DestinationServer** with the name of the server where you have moved the BAM Primary Import database</span></span>  
  
6. <span data-ttu-id="67114-150">BizTalkMgmtDb、ArchivingDatabase、AnalysisDatabase、StarSchemaDatabase、および警告のセクションでは、設定"SourceServer"と"Destination Server"既存のサーバーの名前にこれらのデータベースが存在します。</span><span class="sxs-lookup"><span data-stu-id="67114-150">For the BizTalkMgmtDb, ArchivingDatabase, AnalysisDatabase, StarSchemaDatabase, and Alert sections, set the "SourceServer" and "Destination Server" to the name of the existing server where those databases reside.</span></span>  
  
   > [!IMPORTANT]
   >  <span data-ttu-id="67114-151">送信元システムおよび送信先システムの名前は、引用符で囲んでください。</span><span class="sxs-lookup"><span data-stu-id="67114-151">Include the quotation marks around the name of the source and destination systems.</span></span>  
   > 
   > [!NOTE]
   >  <span data-ttu-id="67114-152">いずれかの [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] データベースの名前を変更した場合、それに応じてデータベース名も更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="67114-152">If you renamed any of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases, you must also update the database names as appropriate.</span></span>  
  
7. <span data-ttu-id="67114-153">ファイルの編集を終了したら、このファイルを保存して閉じます。</span><span class="sxs-lookup"><span data-stu-id="67114-153">When you are finished editing the file, save it and exit.</span></span>  
  
8. <span data-ttu-id="67114-154">をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリックします**OK**。</span><span class="sxs-lookup"><span data-stu-id="67114-154">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
9. <span data-ttu-id="67114-155">コマンド プロンプトで、次のディレクトリに移動します</span><span class="sxs-lookup"><span data-stu-id="67114-155">At the command prompt, navigate to the following directory:</span></span>  
  
   - <span data-ttu-id="67114-156">場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]64 ビット バージョンの Windows Server にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="67114-156">If [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is installed on a 64-bit version of Windows Server:</span></span>  
  
      <span data-ttu-id="67114-157">**%ProgramFiles(x86)%\Microsoft BizTalk Server 2010\Schema\Restore**</span><span class="sxs-lookup"><span data-stu-id="67114-157">**%ProgramFiles(x86)%\Microsoft BizTalk Server 2010\Schema\Restore**</span></span>  
  
   - <span data-ttu-id="67114-158">場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]32 ビット バージョンの Windows Server にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="67114-158">If [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is installed on a 32-bit version of Windows Server:</span></span>  
  
      <span data-ttu-id="67114-159">**%ProgramFiles%\Microsoft BizTalk Server 2010\Schema\Restore**</span><span class="sxs-lookup"><span data-stu-id="67114-159">**%ProgramFiles%\Microsoft BizTalk Server 2010\Schema\Restore**</span></span>  
  
10. <span data-ttu-id="67114-160">コマンド プロンプトで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="67114-160">At the command prompt, type:</span></span>  
  
     <span data-ttu-id="67114-161">**cscript UpdateDatabase.vbs SampleUpdateInfo.xml**</span><span class="sxs-lookup"><span data-stu-id="67114-161">**cscript UpdateDatabase.vbs SampleUpdateInfo.xml**</span></span>  
  
###  <a name="BKMK_Config"></a> <span data-ttu-id="67114-162">BAM ポータルの Web.config ファイルを更新するには</span><span class="sxs-lookup"><span data-stu-id="67114-162">To update the Web.config file for the BAM portal</span></span>  
  
1.  <span data-ttu-id="67114-163">BizTalk Server を実行するコンピューター上で Web.config ファイルを更新 **\<ドライブ\>: BizTalk Server 2010\BAMPortal\BAMManagementService\Web.Config \Program Files\Microsoft** します。Web.config の次のセクションでサーバーとデータベースの名前を更新します。</span><span class="sxs-lookup"><span data-stu-id="67114-163">On a computer running BizTalk Server, update the Web.config files under **\<drive\>:\Program Files\Microsoft BizTalk Server 2010\BAMPortal\BAMManagementService\Web.Config**. Update the server and database names in the following section in the Web.config:</span></span>  
  
    ```  
    <appSettings>  
      <add key="BamServer" value="<ServerName>" />  
      <add key="BamDatabase" value="<DatabaseName>" />  
    </appSettings>  
    ```  
  
2.  <span data-ttu-id="67114-164">BizTalk Server を実行するコンピューター上で Web.config ファイルを更新 **\<ドライブ\>: BizTalk Server 2010\BAMPortal\BAMQueryService\Web.Config \Program Files\Microsoft** します。Web.config の次のセクションでサーバーとデータベースの名前を更新します。</span><span class="sxs-lookup"><span data-stu-id="67114-164">On a computer running BizTalk Server, update the Web.config files under **\<drive\>:\Program Files\Microsoft BizTalk Server 2010\BAMPortal\BAMQueryService\Web.Config**. Update the server and database names in the following section in the Web.config:</span></span>  
  
    ```  
    <appSettings>  
      <add key="BamServer" value="<ServerName>" />  
      <add key="BamDatabase" value="<DatabaseName>" />  
      <add key="MaxResultRows" value="2000" />  
    </appSettings>  
    ```  
  
3.  <span data-ttu-id="67114-165">保存して、ファイルを閉じます。</span><span class="sxs-lookup"><span data-stu-id="67114-165">Save and close the files.</span></span>  
  
###  <a name="BKMK_UpdateExcel"></a> <span data-ttu-id="67114-166">BAM ライブ データの Microsoft Excel ファイル内の参照を更新するには</span><span class="sxs-lookup"><span data-stu-id="67114-166">To update reference in BAM Livedata Microsoft Excel files</span></span>  
  
1. <span data-ttu-id="67114-167">Excel ライブ データ ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="67114-167">Open the Excel live data file.</span></span> <span data-ttu-id="67114-168">ファイル名の末尾は _LiveData.xls となっています。</span><span class="sxs-lookup"><span data-stu-id="67114-168">The file name ends with _LiveData.xls.</span></span>  
  
2. <span data-ttu-id="67114-169">**BAM**  メニューのをクリックして**BAM データベースの接続**します。</span><span class="sxs-lookup"><span data-stu-id="67114-169">On the **BAM** menu, click **BAM DB Connection**.</span></span>  
  
3. <span data-ttu-id="67114-170">**BAM データベースの選択** ダイアログ ボックスに、入力、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]コンピューターおよび BAMPrimaryImport データベース、およびクリックして **[ok]**。</span><span class="sxs-lookup"><span data-stu-id="67114-170">In the **Select BAM Database** dialog box, enter the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] computer and the BAMPrimaryImport database, and then click **OK**.</span></span>  
  
4. <span data-ttu-id="67114-171">**ファイル** メニューのをクリックして**閉じて Microsoft Excel へ戻る**します。</span><span class="sxs-lookup"><span data-stu-id="67114-171">On the **File** menu, click **Close and Return to Microsoft Excel**.</span></span>  
  
5. <span data-ttu-id="67114-172">**[ファイル]** メニューの **[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="67114-172">On the **File** menu, click **Save**.</span></span>  
  
###  <a name="BKMK_UpdatePckg"></a> <span data-ttu-id="67114-173">サーバーとすべての BAM SSIS パッケージ内のデータベース名を更新するには</span><span class="sxs-lookup"><span data-stu-id="67114-173">To update server and database names in all BAM SSIS packages</span></span>  
  
1.  <span data-ttu-id="67114-174">すべての BAM 分析 SSIS パッケージには「bam_an _」または「bam_dm _」プレフィックスでサーバーとデータベースの名前を更新します。</span><span class="sxs-lookup"><span data-stu-id="67114-174">Update the server and database names in all BAM analysis SSIS packages, which are prefixed with "BAM_AN_" or "BAM_DM_".</span></span> <span data-ttu-id="67114-175">これを行うには、次のようにクリックします**開始**、 をクリック**すべてのプログラム**、 をクリック**Microsoft SQL Server 2008 R2**または**Microsoft SQL Server 2008 SP1**、順にクリックします。**SQL Server Business Intelligence Development Studio**します。</span><span class="sxs-lookup"><span data-stu-id="67114-175">To do so, click **Start**, click **All Programs**, click **Microsoft SQL Server 2008 R2** or **Microsoft SQL Server 2008 SP1**, and then click **SQL Server Business Intelligence Development Studio**.</span></span>  
  
2.  <span data-ttu-id="67114-176">SQL Server Business Intelligence Development Studio で、プロジェクトを新規作成します。</span><span class="sxs-lookup"><span data-stu-id="67114-176">In SQL Server Business Intelligence Development Studio, create a new project.</span></span> <span data-ttu-id="67114-177">をクリックして**ファイル**、 をクリックして**新規**、クリックして**プロジェクト**です。</span><span class="sxs-lookup"><span data-stu-id="67114-177">Click **File**, click **New**, and then click **Project**.</span></span>  
  
3.  <span data-ttu-id="67114-178">**新しいプロジェクト**] ダイアログ ボックスで、**プロジェクトの種類**ボックスで、[**ビジネス インテリジェンス プロジェクト**します。</span><span class="sxs-lookup"><span data-stu-id="67114-178">In the **New Project** dialog box, in the **Project Types** box, click **Business Intelligence Projects**.</span></span> <span data-ttu-id="67114-179">右側のウィンドウでの**テンプレート**ボックスで、 **Integration Services プロジェクト**、順にクリックします**OK**。</span><span class="sxs-lookup"><span data-stu-id="67114-179">In the right pane, in the **Templates** box, click **Integration Services Project**, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="67114-180">**Integration Services プロジェクト** ダイアログ ボックスで、ソリューション エクスプ ローラーで右クリックして**SSIS パッケージ**、順にクリックします**既存パッケージの追加**します。</span><span class="sxs-lookup"><span data-stu-id="67114-180">In the **Integration Services Project** dialog box, in Solution Explorer, right-click **SSIS Packages**, and then click **Add Existing Package**.</span></span>  
  
5.  <span data-ttu-id="67114-181">**既存パッケージのコピーの追加** ダイアログ ボックスで、 **Server**ドロップダウン リスト ボックスで、bam_an _ を含むサーバーを選択します。\*と bam_dm _\*パッケージ。</span><span class="sxs-lookup"><span data-stu-id="67114-181">In the **Add Copy of Existing Package** dialog box, in the **Server** drop-down list box, select the server that contains the BAM_AN_\* and BAM_DM_\* packages.</span></span>  
  
6.  <span data-ttu-id="67114-182">**パッケージ パス**、省略記号ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="67114-182">In **Package Path**, click the ellipses button.</span></span>  
  
7.  <span data-ttu-id="67114-183">**SSIS パッケージ** ダイアログ ボックスで、更新、 をクリックするパッケージを選択**ok**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="67114-183">In the **SSIS Package** dialog box, select the package you want to update, click **OK**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="67114-184">これで、パッケージがソリューション エクスプローラにリストされました。</span><span class="sxs-lookup"><span data-stu-id="67114-184">The package is now listed in Solution Explorer.</span></span>  
  
8.  <span data-ttu-id="67114-185">ソリューション エクスプ ローラーで、前の手順で追加したパッケージをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="67114-185">In Solution Explorer, double-click the package you added in the previous step.</span></span> <span data-ttu-id="67114-186">**接続マネージャー** (画面の下半分に利用可能) タブで、データ ソース番号 1 (BAMPrimaryImport データベース) をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="67114-186">In **Connection Managers** tab (available towards the lower half of the screen), double-click data source number 1 (BAMPrimaryImport database).</span></span>  
  
9. <span data-ttu-id="67114-187">**接続マネージャー**  ダイアログ ボックスで、**サーバー名**ボックスに、サーバーの名前を入力し、 をクリックし、 **OK**します。</span><span class="sxs-lookup"><span data-stu-id="67114-187">In the **Connection Manager** dialog box, in the **Server name** box, enter the name of the server, and then click **OK**.</span></span>  
  
10. <span data-ttu-id="67114-188">をクリックして、**パッケージ エクスプ ローラー**  タブで、ダブルクリックして、**変数**フォルダー、しの値を更新、 **PrimaryImportDatabase**と**PrimaryImportServer**変数。</span><span class="sxs-lookup"><span data-stu-id="67114-188">Click the **Package Explorer** tab, double-click the **Variables** folder, and then update the values for the **PrimaryImportDatabase** and **PrimaryImportServer** variables.</span></span> <span data-ttu-id="67114-189">新しいサーバーやデータベースを指定する値を更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="67114-189">You must update the values to point to the new server and database.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="67114-190">すべてのパッケージを更新するには、手順 4 ~ 10 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="67114-190">Repeat step 4 through 10 for all the packages that you want to update.</span></span>  
  
11. <span data-ttu-id="67114-191">クリックしてから**ファイル** メニューをクリック**すべて保存**します。</span><span class="sxs-lookup"><span data-stu-id="67114-191">Click then **File** menu, and then click **Save All**.</span></span>  
  
12. <span data-ttu-id="67114-192">SQL Server Management Studio を起動します。</span><span class="sxs-lookup"><span data-stu-id="67114-192">Start the SQL Server Management Studio.</span></span> <span data-ttu-id="67114-193">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして**Microsoft SQL Server 2008 R2**または**Microsoft SQL Server 2008 SP1**順にクリックします**SQL Server Management Studio**します。</span><span class="sxs-lookup"><span data-stu-id="67114-193">Click **Start**, click **All Programs**, click **Microsoft SQL Server 2008 R2** or **Microsoft SQL Server 2008 SP1**, and then click **SQL Server Management Studio**.</span></span>  
  
13. <span data-ttu-id="67114-194">**サーバーへの接続** ダイアログ ボックスから、**サーバー**型のドロップダウン リスト、選択**Integration Services**。</span><span class="sxs-lookup"><span data-stu-id="67114-194">In the **Connect to Server** dialog box, from the **Server** type drop-down list, select **Integration Services**.</span></span>  
  
14. <span data-ttu-id="67114-195">サーバー名とサーバー をクリックして接続する資格情報を指定**OK**します。</span><span class="sxs-lookup"><span data-stu-id="67114-195">Specify the server name and credentials to connect to the server and click **OK**.</span></span>  
  
15. <span data-ttu-id="67114-196">**オブジェクト エクスプ ローラー**、展開**Integration Services**、展開**格納されたパッケージ**、 をクリックし、 **MSDB**します。</span><span class="sxs-lookup"><span data-stu-id="67114-196">In the **Object Explorer**, expand **Integration Services**, expand **Stored Packages**, and then click **MSDB**.</span></span>  
  
16. <span data-ttu-id="67114-197">**オブジェクト エクスプ ローラーの詳細** タブで、先ほど更新したパッケージを右クリックし、をクリックし、**パッケージのインポート**します。</span><span class="sxs-lookup"><span data-stu-id="67114-197">In the **Object Explorer Details** tab, right-click the package that you updated earlier and then click **Import Package**.</span></span>  
  
17. <span data-ttu-id="67114-198">**パッケージのインポート** ダイアログ ボックスから、**パッケージの場所**ドロップダウン リストで、**ファイル システム**します。</span><span class="sxs-lookup"><span data-stu-id="67114-198">In the **Import Package** dialog box, from the **Package location** drop-down list, select **File System**.</span></span>  
  
18. <span data-ttu-id="67114-199">**パッケージ パス**で、保存したプロジェクトに移動し、.dtsx ファイルをクリックして、インポートするパッケージを選択**オープン**します。</span><span class="sxs-lookup"><span data-stu-id="67114-199">In **Package Path**, navigate to your saved project, select the .dtsx file for the package you want to import, and then click **Open**.</span></span>  
  
19. <span data-ttu-id="67114-200">自動的に、ボックスに入力して [パッケージ名] ボックス内をクリックします。</span><span class="sxs-lookup"><span data-stu-id="67114-200">Click inside the Package Name box to automatically populate the box.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="67114-201">すべてのパッケージを更新するには、手順 16 ~ 19 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="67114-201">Repeat step 16 through 19 for all the packages that you want to update.</span></span>  
  
20. <span data-ttu-id="67114-202">をクリックして **[ok]**、順にクリック**はい**を上書きします。</span><span class="sxs-lookup"><span data-stu-id="67114-202">Click **OK**, and then click **Yes** to overwrite.</span></span>  
  
21. <span data-ttu-id="67114-203">すべての BAM キューブ更新およびデータ保守 SSIS パッケージを有効にします。</span><span class="sxs-lookup"><span data-stu-id="67114-203">Enable any BAM cube update and data maintenance SSIS packages.</span></span>  
  
###  <a name="BKMK_UpdateDSOLAP"></a> <span data-ttu-id="67114-204">サーバーおよびすべての OLAP キューブのデータ ソース内のデータベース名を更新するには</span><span class="sxs-lookup"><span data-stu-id="67114-204">To update server and database names in data sources for all OLAP cubes</span></span>  
  
1. <span data-ttu-id="67114-205">すべての OLAP キューブのデータ ソースのサーバーおよびデータベース名を更新します。</span><span class="sxs-lookup"><span data-stu-id="67114-205">Update the server and database names in data sources for all OLAP cubes.</span></span> <span data-ttu-id="67114-206">これを行うには、次のようにクリックします**開始**、 をクリック**すべてのプログラム**、 をクリック**Microsoft SQL Server 2008 R2**または**Microsoft SQL Server 2008 SP1**、順にクリックします。**SQL Server Management Studio**します。</span><span class="sxs-lookup"><span data-stu-id="67114-206">To do so, click **Start**, click **All Programs**, click **Microsoft SQL Server 2008 R2** or **Microsoft SQL Server 2008 SP1**, and then click **SQL Server Management Studio**.</span></span>  
  
2. <span data-ttu-id="67114-207">**サーバーへの接続** ダイアログ ボックスの**サーバーの種類**ドロップダウン リストを**Analysis Services**認証方法を選択して、サーバー名を指定 (および資格情報の入力が必要な場合)、をクリックし、 **Connect**します。</span><span class="sxs-lookup"><span data-stu-id="67114-207">In the **Connect to Server** dialog box, for the **Server type** drop-down list select **Analysis Services**, provide the server name, select an authentication method (and provide credentials if required), and then click **Connect**.</span></span>  
  
3. <span data-ttu-id="67114-208">オブジェクト エクスプ ローラーで、**データベース**、展開**BAMAnalysis**、展開**データソース**、データ ソースをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="67114-208">In the Object Explorer, expand **Databases**, expand **BAMAnalysis**, expand **Data Sources**, and then double-click a data source.</span></span>  
  
4. <span data-ttu-id="67114-209">**データ ソースのプロパティ** ダイアログ ボックスで、省略記号ボタンをクリックします **(...)。** に対して、**接続文字列**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="67114-209">In the **Data Source Properties** dialog box, click the ellipsis button **(…)** against the **Connection String** property.</span></span>  
  
5. <span data-ttu-id="67114-210">**接続マネージャー**  ダイアログ ボックスで、**サーバー名**ボックスを BAMPrimaryImport データベースをホストするサーバーの名前を入力し、をクリックして**OK**順にクリックします**Ok**します。</span><span class="sxs-lookup"><span data-stu-id="67114-210">In the **Connection Manager** dialog box, in the **Server name** box, enter the name of the server hosting the BAMPrimaryImport database, click **OK**, and then click **OK**.</span></span>  
  
6. <span data-ttu-id="67114-211">すべて開始[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]サービス。</span><span class="sxs-lookup"><span data-stu-id="67114-211">Start all [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] services.</span></span> <span data-ttu-id="67114-212">詳細については、トピックを参照してください。[方法を開始、停止、一時停止、再開、または BizTalk Server サービスを再起動](http://go.microsoft.com/fwlink/?LinkId=154394)(<http://go.microsoft.com/fwlink/?LinkId=154394>) で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。</span><span class="sxs-lookup"><span data-stu-id="67114-212">For more information, see the topic [How To Start, Stop, Pause, Resume, or Restart BizTalk Server Services](http://go.microsoft.com/fwlink/?LinkId=154394) (<http://go.microsoft.com/fwlink/?LinkId=154394>) in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help.</span></span>  
  
7. <span data-ttu-id="67114-213">IIS サービスを開始します。</span><span class="sxs-lookup"><span data-stu-id="67114-213">Start the IIS service.</span></span>  
  
8. <span data-ttu-id="67114-214">BAM 警告 Notification service を開始します。</span><span class="sxs-lookup"><span data-stu-id="67114-214">Start the BAM Alerts Notification service:</span></span>  
  
   1.  <span data-ttu-id="67114-215">をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリックします**OK**。</span><span class="sxs-lookup"><span data-stu-id="67114-215">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
   2.  <span data-ttu-id="67114-216">コマンド プロンプトで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="67114-216">At the command prompt, type:</span></span>  
  
        <span data-ttu-id="67114-217">**Net start NS$ BamAlerts**</span><span class="sxs-lookup"><span data-stu-id="67114-217">**Net start NS$BamAlerts**</span></span>  
  
9. <span data-ttu-id="67114-218">すべての不完全なトレース インスタンスを解決します。</span><span class="sxs-lookup"><span data-stu-id="67114-218">Resolve any incomplete trace instances.</span></span>  <span data-ttu-id="67114-219">不完全な BAM アクティビティ インスタンスの解決方法の詳細については、[不完全なアクティビティ インスタンスの解決方法](http://go.microsoft.com/fwlink/?LinkId=151475)(http://go.microsoft.com/fwlink/?LinkId=151475)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="67114-219">For information about resolving incomplete BAM activity instances, see [How to Resolve Incomplete Activity Instances](http://go.microsoft.com/fwlink/?LinkId=151475) (http://go.microsoft.com/fwlink/?LinkId=151475).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67114-220">参照</span><span class="sxs-lookup"><span data-stu-id="67114-220">See Also</span></span>  
 [<span data-ttu-id="67114-221">データベースの移動</span><span class="sxs-lookup"><span data-stu-id="67114-221">Moving Databases</span></span>](../technical-guides/moving-databases.md)