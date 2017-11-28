---
title: "BAM プライマリ インポート データベース名および接続文字列への参照を更新する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- restoring [BAM], connection strings
- Primary Import database [BAM], updating references
- connection strings, restoring
- connection strings, BAM
- restoring, BAM
- restoring [BAM], Primary Import database
- restoring [BAM], updating references
- Primary Import database [BAM], restoring
- BAM, restoring
- restoring, connection strings
ms.assetid: e3c58db0-f14f-429a-813c-bae29f6950d3
caps.latest.revision: "25"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b56264155ed9f739669da1cb6f646adac0f9db55
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-update-references-to-the-bam-primary-import-database-name-and-connection-string"></a><span data-ttu-id="321b3-102">BAM プライマリ インポート データベース名および接続文字列への参照を更新する方法</span><span class="sxs-lookup"><span data-stu-id="321b3-102">How to Update References to the BAM Primary Import Database Name and Connection String</span></span>
<span data-ttu-id="321b3-103">BAMPrimaryImport データベースをバックアップしておくと、システムまたはデータに障害が発生したときに、別のコンピューターにバックアップを復元し、その名前を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="321b3-103">If you backed up your BAMPrimaryImport database in the event of a system or data failure, you can restore that backup to a different computer and rename the backup.</span></span>  
  
 <span data-ttu-id="321b3-104">BAM イベント バス サービスでは、イベント データをメッセージ ボックス データベースから BAMPrimaryImport データベースに移動します。</span><span class="sxs-lookup"><span data-stu-id="321b3-104">The BAM Event Bus service moves event data from the MessageBox database to the BAMPrimaryImport database.</span></span> <span data-ttu-id="321b3-105">BAM イベント バス サービスには、予期しない障害が発生した場合にデータを失わずに復旧して再起動するためのフォールト トレランス ロジックが含まれています。</span><span class="sxs-lookup"><span data-stu-id="321b3-105">The BAM Event Bus service includes fault tolerance logic that enables it to recover and restart from an unexpected failure without losing any data.</span></span> <span data-ttu-id="321b3-106">BAM イベント バス サービスの詳細については、次を参照してください。 [BAM イベント バス サービスを管理する](../core/managing-the-bam-event-bus-service.md)です。</span><span class="sxs-lookup"><span data-stu-id="321b3-106">For more information about the BAM Event Bus service, see [Managing the BAM Event Bus Service](../core/managing-the-bam-event-bus-service.md).</span></span>  
  
 <span data-ttu-id="321b3-107">BAMPrimaryImport データベースを復元する」の手順を実行[、データベースを復元する方法](../core/how-to-restore-your-databases.md)です。</span><span class="sxs-lookup"><span data-stu-id="321b3-107">To restore the BAMPrimaryImport database, perform the steps in [How to Restore Your Databases](../core/how-to-restore-your-databases.md).</span></span> <span data-ttu-id="321b3-108">これらの手順を実行したうえで、次の手順を実行します (詳細な手順については後述)。</span><span class="sxs-lookup"><span data-stu-id="321b3-108">In addition, you must perform these general steps, which are followed by a procedure that describes the steps in detail:</span></span>  
  
-   <span data-ttu-id="321b3-109">すべての BAM DTS パッケージで、SQL 接続 1 の参照先が新しいデータベース名になるように更新します。</span><span class="sxs-lookup"><span data-stu-id="321b3-109">Update the SQL Connection 1 in all BAM DTS packages to refer to the new database name.</span></span>  
  
-   <span data-ttu-id="321b3-110">新しいデータベース名で web.config ファイルを更新します。</span><span class="sxs-lookup"><span data-stu-id="321b3-110">Update the web.config file with the new database name.</span></span>  
  
-   <span data-ttu-id="321b3-111">すべての BAM ライブ データの Microsoft Excel ファイルで BAMPrimaryImport データベースへの参照を更新します。</span><span class="sxs-lookup"><span data-stu-id="321b3-111">Update the reference to BAMPrimaryImport database in all BAM Livedata Microsoft Excel files.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="321b3-112">前提条件</span><span class="sxs-lookup"><span data-stu-id="321b3-112">Prerequisites</span></span>  
 <span data-ttu-id="321b3-113">ここで示す手順を実行するには、BizTalk Server Administrators グループのメンバーとしてログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="321b3-113">You must be logged on as a member of the BizTalk Server Administrators group to perform this procedure.</span></span>  
  
### <a name="to-update-references-to-the-bamprimaryimport-database-name-and-connection-string"></a><span data-ttu-id="321b3-114">BAMPrimaryImport データベース名および接続文字列への参照を更新するには</span><span class="sxs-lookup"><span data-stu-id="321b3-114">To update references to the BAMPrimaryImport database name and connection string</span></span>  
  
1.  <span data-ttu-id="321b3-115">すべての BAM キューブ更新およびデータ変換サービス (DTS) パッケージを停止するか、BAMPrimaryImport データベースの復元が完了するまで実行されないように措置を講じます。</span><span class="sxs-lookup"><span data-stu-id="321b3-115">Stop any BAM cube update and data maintenance Data Transformation Services (DTS) packages, or prevent them from running until you have restored the BAMPrimaryImport database.</span></span>  
  
2.  <span data-ttu-id="321b3-116">(を BAM イベント バス サービスを含む)、BizTalk アプリケーション サービスを停止するため、データベースに多くのデータをインポートするのには試行されません。</span><span class="sxs-lookup"><span data-stu-id="321b3-116">Stop the BizTalk Application service (which includes the BAM Event Bus service) so it does not try to import more data into the database.</span></span>  
  
    1.  <span data-ttu-id="321b3-117">をクリックして**開始**、 をクリックして**実行**、し、入力**services.msc**です。</span><span class="sxs-lookup"><span data-stu-id="321b3-117">Click **Start**, click **Run**, and then type **services.msc**.</span></span>  
  
    2.  <span data-ttu-id="321b3-118">右クリックし、 **BizTalk Service BizTalk Group: BizTalkServerApplication**サービスを提供し、クリックして**停止**です。</span><span class="sxs-lookup"><span data-stu-id="321b3-118">Right-click the **BizTalk Service BizTalk Group: BizTalkServerApplication** service and then click **Stop**.</span></span>  
  
3.  <span data-ttu-id="321b3-119">」の手順を実行する、BAMPrimaryImport データベースを復元[、データベースを復元する方法](../core/how-to-restore-your-databases.md)です。</span><span class="sxs-lookup"><span data-stu-id="321b3-119">Restore the BAMPrimaryImport database, performing the steps in [How to Restore Your Databases](../core/how-to-restore-your-databases.md).</span></span>  
  
4.  <span data-ttu-id="321b3-120">次の Web.Config ファイルを更新します。</span><span class="sxs-lookup"><span data-stu-id="321b3-120">Update the following Web.Config files:</span></span>  
  
    -   [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="321b3-121">BAMPortal\BamManagementService\Web.Config.</span><span class="sxs-lookup"><span data-stu-id="321b3-121">BAMPortal\BamManagementService\Web.Config.</span></span>  
  
         <span data-ttu-id="321b3-122">置換、  *\<ServerName >* 、新しいサーバー名の文字列と *\<DatabaseName >*で新しいデータベースの名前。</span><span class="sxs-lookup"><span data-stu-id="321b3-122">Replace the *\<ServerName>* string with the new server name and *\<DatabaseName>* with the new database name.</span></span> <span data-ttu-id="321b3-123">次の接続文字列を更新します。</span><span class="sxs-lookup"><span data-stu-id="321b3-123">Update the following connection strings:</span></span>  
  
         <span data-ttu-id="321b3-124">\<appSettings ></span><span class="sxs-lookup"><span data-stu-id="321b3-124">\<appSettings></span></span>  
  
         <span data-ttu-id="321b3-125">< キーを追加"BamServer"の値を = ="*\<ServerName >*"/\></span><span class="sxs-lookup"><span data-stu-id="321b3-125"><add key="BamServer" value="*\<ServerName>*" /\></span></span>  
  
         <span data-ttu-id="321b3-126">< キーを追加"BamDatabase"の値を = ="*\<DatabaseName >*"/\></span><span class="sxs-lookup"><span data-stu-id="321b3-126"><add key="BamDatabase" value="*\<DatabaseName>*" /\></span></span>  
  
         <span data-ttu-id="321b3-127">\<キーを追加"MaxResultRows"の値を = =「2000」/></span><span class="sxs-lookup"><span data-stu-id="321b3-127">\<add key="MaxResultRows" value="2000" /></span></span>  
  
         <span data-ttu-id="321b3-128">\</appSettings ></span><span class="sxs-lookup"><span data-stu-id="321b3-128">\</appSettings></span></span>  
  
    -   [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="321b3-129">BAMPortal\BamQueryService\Web.Config.</span><span class="sxs-lookup"><span data-stu-id="321b3-129">BAMPortal\BamQueryService\Web.Config.</span></span>  
  
         <span data-ttu-id="321b3-130">置換、  *\<ServerName >* 、新しいサーバー名の文字列と *\<DatabaseName >*で新しいデータベースの名前。</span><span class="sxs-lookup"><span data-stu-id="321b3-130">Replace the *\<ServerName>* string with the new server name and *\<DatabaseName>* with the new database name.</span></span> <span data-ttu-id="321b3-131">次の接続文字列を更新します。</span><span class="sxs-lookup"><span data-stu-id="321b3-131">Update the following connection strings:</span></span>  
  
         <span data-ttu-id="321b3-132">\<appSettings ></span><span class="sxs-lookup"><span data-stu-id="321b3-132">\<appSettings></span></span>  
  
         <span data-ttu-id="321b3-133">< キーを追加"BamServer"の値を = ="*\<ServerName >*"/\></span><span class="sxs-lookup"><span data-stu-id="321b3-133"><add key="BamServer" value="*\<ServerName>*" /\></span></span>  
  
         <add key="BamDatabase" value="*<DatabaseName>*" />  
  
         <add key="MaxResultRows" value="2000" />  
  
         </appSettings>  
  
5.  <span data-ttu-id="321b3-134">をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリック**ok**です。</span><span class="sxs-lookup"><span data-stu-id="321b3-134">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="321b3-135">次のディレクトリに移動: [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]schema \restore です。</span><span class="sxs-lookup"><span data-stu-id="321b3-135">Navigate to the following directory: [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Schema\Restore.</span></span>  
  
7.  <span data-ttu-id="321b3-136">右クリック**SampleUpdateInfo.xml**、クリックして**編集**です。</span><span class="sxs-lookup"><span data-stu-id="321b3-136">Right-click **SampleUpdateInfo.xml**, and then click **Edit**.</span></span>  
  
    1.  <span data-ttu-id="321b3-137">BizTalkMgmtDb、OldPrimaryImportDatabase、PrimaryImportDatabase、ArchivingDatabase、AnalysisDatabase、StarSchemaDatabase、および Alert を除いて、すべてのデータベース セクションをコメント アウトします。</span><span class="sxs-lookup"><span data-stu-id="321b3-137">Comment out all of the database sections except for the BizTalkMgmtDb, OldPrimaryImportDatabase, PrimaryImportDatabase, ArchivingDatabase, AnalysisDatabase, StarSchemaDatabase, and Alert.</span></span>  
  
    2.  <span data-ttu-id="321b3-138">BizTalkMgmtDb、OldPrimaryImportDatabase、PrimaryImportDatabase、ArchivingDatabase、AnalysisDatabase、StarSchemaDatabase、および警告のセクションでは、設定、 **"SourceServer"**と**"Destination Server"**それらのデータベースが存在する既存のサーバーの名前にします。</span><span class="sxs-lookup"><span data-stu-id="321b3-138">For the BizTalkMgmtDb, OldPrimaryImportDatabase, PrimaryImportDatabase, ArchivingDatabase, AnalysisDatabase, StarSchemaDatabase, and Alert sections, set the **"SourceServer"** and **"Destination Server"** to the name of the existing server where those databases reside.</span></span>  
  
    3.  <span data-ttu-id="321b3-139">Primaryimportdatabase について、次のように設定します。、 **"SourceServer"** 、BAM プライマリ インポート データベースを移動したサーバーの名前にします。</span><span class="sxs-lookup"><span data-stu-id="321b3-139">For PrimaryImportDatabase, set the **"SourceServer"** to the name of the server where you have moved the BAM Primary Import database.</span></span>  
  
        > [!IMPORTANT]
        >  <span data-ttu-id="321b3-140">送信元システムおよび送信先システムの名前は、引用符で囲んでください。</span><span class="sxs-lookup"><span data-stu-id="321b3-140">Include the quotation marks around the name of the source and destination systems.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="321b3-141">いずれかの BizTalk Server データベースの名前を変更した場合、それに応じてデータベース名も更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="321b3-141">If you renamed any of the BizTalk Server databases, you must also update the database names as appropriate.</span></span>  
  
    4.  <span data-ttu-id="321b3-142">ファイルの編集を終了したら、このファイルを保存して閉じます。</span><span class="sxs-lookup"><span data-stu-id="321b3-142">When you are finished editing the file, save it and exit.</span></span>  
  
8.  <span data-ttu-id="321b3-143">コマンド プロンプトで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="321b3-143">At the command prompt, type:</span></span>  
  
     <span data-ttu-id="321b3-144">**cscript UpdateDatabase.vbs SampleUpdateInfo.xml**</span><span class="sxs-lookup"><span data-stu-id="321b3-144">**cscript UpdateDatabase.vbs SampleUpdateInfo.xml**</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="321b3-145">UpdateDatabase.vbs の実行は、1 度のみしか必要ありません。</span><span class="sxs-lookup"><span data-stu-id="321b3-145">You only need to run UpdateDatabase.vbs once.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="321b3-146">64 ビット コンピューターの場合は、UpdateDatabase.vbs を 64 ビット コマンド プロンプトから実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="321b3-146">On 64-bit computers, you must run UpdateDatabase.vbs from a 64-bit command prompt.</span></span>  
  
9. <span data-ttu-id="321b3-147">コマンド プロンプトで、次のディレクトリに移動します</span><span class="sxs-lookup"><span data-stu-id="321b3-147">At the command prompt, navigate to the following directory:</span></span>  
  
     [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="321b3-148">追跡</span><span class="sxs-lookup"><span data-stu-id="321b3-148">Tracking</span></span>  
  
10. <span data-ttu-id="321b3-149">コマンド プロンプトで、bm.exe.config を編集して、key="DefaultServer" の値を新しいサーバー名に変更し、ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="321b3-149">At the command prompt, edit bm.exe.config, change the value of key="DefaultServer" to the new server name, and then save the file.</span></span>  
  
11. <span data-ttu-id="321b3-150">すべての BAM ライブ データの Microsoft Excel ファイルで BAMPrimaryImport データベースへの参照を更新します。</span><span class="sxs-lookup"><span data-stu-id="321b3-150">Update the reference to BAMPrimaryImport database in all BAM Livedata Microsoft Excel files.</span></span> <span data-ttu-id="321b3-151">各ファイルで次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="321b3-151">For each file:</span></span>  
  
    1.  <span data-ttu-id="321b3-152">Excel ライブ データ ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="321b3-152">Open the Excel live data file.</span></span> <span data-ttu-id="321b3-153">ファイル名の末尾は _LiveData.xls となっています。</span><span class="sxs-lookup"><span data-stu-id="321b3-153">The file name ends with _LiveData.xls.</span></span>  
  
    2.  <span data-ttu-id="321b3-154">**BAM**  メニューをクリックして**BAM データベースの接続**です。</span><span class="sxs-lookup"><span data-stu-id="321b3-154">On the **BAM** menu, click **BAM DB Connection**.</span></span>  
  
    3.  <span data-ttu-id="321b3-155">**[BAM データベース**] ダイアログ ボックスでは、SQL Server および BAMPrimaryImport データベースを入力し、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="321b3-155">In the **Select BAM Database** dialog box, enter the SQL Server and BAMPrimaryImport database, and then click **OK**.</span></span>  
  
    4.  <span data-ttu-id="321b3-156">**ファイル** メニューのをクリックして**閉じて Microsoft Excel へ戻る**です。</span><span class="sxs-lookup"><span data-stu-id="321b3-156">On the **File** menu, click **Close and Return to Microsoft Excel**.</span></span>  
  
    5.  <span data-ttu-id="321b3-157">**[ファイル]** メニューの **[保存]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="321b3-157">On the **File** menu, click **Save**.</span></span>  
  
12. <span data-ttu-id="321b3-158">BizTalk Server アプリケーション サービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="321b3-158">Restart the BizTalk Application service.</span></span>  
  
    1.  <span data-ttu-id="321b3-159">をクリックして**開始**、 をクリックして**実行**、し、入力**services.msc**です。</span><span class="sxs-lookup"><span data-stu-id="321b3-159">Click **Start**, click **Run**, and then type **services.msc**.</span></span>  
  
    2.  <span data-ttu-id="321b3-160">右クリックし、 **BizTalk Service BizTalk Group: BizTalkServerApplication**サービスを提供し、クリックして**開始**です。</span><span class="sxs-lookup"><span data-stu-id="321b3-160">Right-click the **BizTalk Service BizTalk Group: BizTalkServerApplication** service and then click **Start**.</span></span>  
  
13. <span data-ttu-id="321b3-161">すべての BAM キューブ更新およびデータ保守 DTS パッケージを有効にします。</span><span class="sxs-lookup"><span data-stu-id="321b3-161">Enable any BAM cube update and data maintenance DTS packages.</span></span>  
  
14. <span data-ttu-id="321b3-162">不完全なアクティビティ インスタンスを解決するには、次を参照してください。[不完全なアクティビティ インスタンスの解決方法](../core/how-to-resolve-incomplete-activity-instances.md)です。</span><span class="sxs-lookup"><span data-stu-id="321b3-162">To resolve any incomplete trace instances, see [How to Resolve Incomplete Activity Instances](../core/how-to-resolve-incomplete-activity-instances.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="321b3-163">参照</span><span class="sxs-lookup"><span data-stu-id="321b3-163">See Also</span></span>  
 [<span data-ttu-id="321b3-164">バックアップおよび BAM を復元します。</span><span class="sxs-lookup"><span data-stu-id="321b3-164">Backing Up and Restoring BAM</span></span>](../core/backing-up-and-restoring-bam.md)