---
title: BAM プライマリ インポート データベースの名前と接続文字列を更新 |Microsoft ドキュメント
ms.custom: ''
ms.date: 02/01/2018
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e3c58db0-f14f-429a-813c-bae29f6950d3
caps.latest.revision: 25
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 91792b66fa82be633123501f651d9a34784915ce
ms.sourcegitcommit: c670558deccec266f90ae7ed042dba1105b15596
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2018
ms.locfileid: "28956652"
---
# <a name="update-references-to-the-bam-primary-import-database-name-and-connection-string"></a><span data-ttu-id="7410f-102">BAM プライマリ インポート データベース名および接続文字列への参照を更新します。</span><span class="sxs-lookup"><span data-stu-id="7410f-102">Update References to the BAM Primary Import Database Name and Connection String</span></span>
<span data-ttu-id="7410f-103">BAMPrimaryImport データベースをバックアップしておくと、システムまたはデータに障害が発生したときに、別のコンピューターにバックアップを復元し、その名前を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="7410f-103">If you backed up your BAMPrimaryImport database in the event of a system or data failure, you can restore that backup to a different computer and rename the backup.</span></span>  
  
 <span data-ttu-id="7410f-104">BAM イベント バス サービスでは、イベント データをメッセージ ボックス データベースから BAMPrimaryImport データベースに移動します。</span><span class="sxs-lookup"><span data-stu-id="7410f-104">The BAM Event Bus service moves event data from the MessageBox database to the BAMPrimaryImport database.</span></span> <span data-ttu-id="7410f-105">BAM イベント バス サービスには、予期しない障害が発生した場合にデータを失わずに復旧して再起動するためのフォールト トレランス ロジックが含まれています。</span><span class="sxs-lookup"><span data-stu-id="7410f-105">The BAM Event Bus service includes fault tolerance logic that enables it to recover and restart from an unexpected failure without losing any data.</span></span> <span data-ttu-id="7410f-106">BAM イベント バス サービスの詳細については、次を参照してください。 [BAM イベント バス サービスを管理する](../core/managing-the-bam-event-bus-service.md)です。</span><span class="sxs-lookup"><span data-stu-id="7410f-106">For more information about the BAM Event Bus service, see [Managing the BAM Event Bus Service](../core/managing-the-bam-event-bus-service.md).</span></span>  
  
 <span data-ttu-id="7410f-107">BAMPrimaryImport データベースを復元する」の手順を実行[、データベースを復元する方法](../core/how-to-restore-your-databases.md)です。</span><span class="sxs-lookup"><span data-stu-id="7410f-107">To restore the BAMPrimaryImport database, perform the steps in [How to Restore Your Databases](../core/how-to-restore-your-databases.md).</span></span> <span data-ttu-id="7410f-108">これらの手順を実行したうえで、次の手順を実行します (詳細な手順については後述)。</span><span class="sxs-lookup"><span data-stu-id="7410f-108">In addition, you must perform these general steps, which are followed by a procedure that describes the steps in detail:</span></span>  
  
-   <span data-ttu-id="7410f-109">すべての BAM DTS パッケージで、SQL 接続 1 の参照先が新しいデータベース名になるように更新します。</span><span class="sxs-lookup"><span data-stu-id="7410f-109">Update the SQL Connection 1 in all BAM DTS packages to refer to the new database name.</span></span>  
  
-   <span data-ttu-id="7410f-110">新しいデータベース名で web.config ファイルを更新します。</span><span class="sxs-lookup"><span data-stu-id="7410f-110">Update the web.config file with the new database name.</span></span>  
  
-   <span data-ttu-id="7410f-111">すべての BAM ライブ データの Microsoft Excel ファイルで BAMPrimaryImport データベースへの参照を更新します。</span><span class="sxs-lookup"><span data-stu-id="7410f-111">Update the reference to BAMPrimaryImport database in all BAM Livedata Microsoft Excel files.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="7410f-112">前提条件</span><span class="sxs-lookup"><span data-stu-id="7410f-112">Prerequisites</span></span>  
<span data-ttu-id="7410f-113">BizTalk Server 管理者グループのメンバーとしてサインインします。</span><span class="sxs-lookup"><span data-stu-id="7410f-113">Sign in as a member of the BizTalk Server Administrators group.</span></span>  
  
## <a name="update-the-references"></a><span data-ttu-id="7410f-114">参照を更新します。</span><span class="sxs-lookup"><span data-stu-id="7410f-114">Update the references</span></span>  
  
1.  <span data-ttu-id="7410f-115">すべての BAM キューブ更新およびデータ変換サービス (DTS) パッケージを停止するか、BAMPrimaryImport データベースの復元が完了するまで実行されないように措置を講じます。</span><span class="sxs-lookup"><span data-stu-id="7410f-115">Stop any BAM cube update and data maintenance Data Transformation Services (DTS) packages, or prevent them from running until you have restored the BAMPrimaryImport database.</span></span>  
  
2.  <span data-ttu-id="7410f-116">BizTalk アプリケーション サービス (を BAM イベント バス サービスを含む) を停止するためより多くのデータをデータベースにインポートするのには試行されません。</span><span class="sxs-lookup"><span data-stu-id="7410f-116">Stop the BizTalk Application service (which includes the BAM Event Bus service) so it does not try to import more data into the database.</span></span>  
  
    1.  <span data-ttu-id="7410f-117">**開始**メニューで、「 **services.msc**、開き**Services**です。</span><span class="sxs-lookup"><span data-stu-id="7410f-117">From the **Start** menu, type **services.msc**, and open **Services**.</span></span>  
  
    2.  <span data-ttu-id="7410f-118">右クリックし、 **BizTalk Service BizTalk Group: BizTalkServerApplication**サービス、し**停止**です。</span><span class="sxs-lookup"><span data-stu-id="7410f-118">Right-click the **BizTalk Service BizTalk Group: BizTalkServerApplication** service, and then **Stop**.</span></span>  
  
3.  <span data-ttu-id="7410f-119">BAMPrimaryImport データベースの復元 (ステップの[、データベースを復元する方法](../core/how-to-restore-your-databases.md))。</span><span class="sxs-lookup"><span data-stu-id="7410f-119">Restore the BAMPrimaryImport database (steps in [How to Restore Your Databases](../core/how-to-restore-your-databases.md)).</span></span>  
  
4.  <span data-ttu-id="7410f-120">次の Web.Config ファイルを更新します。</span><span class="sxs-lookup"><span data-stu-id="7410f-120">Update the following Web.Config files:</span></span>  
  
    -   [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="7410f-121">\BAMPortal\BamManagementService\Web.Config です。</span><span class="sxs-lookup"><span data-stu-id="7410f-121">\BAMPortal\BamManagementService\Web.Config.</span></span>  
  
         <span data-ttu-id="7410f-122">置換、  *\<ServerName\>*  、新しいサーバーの名前を持つ文字列と *\<DatabaseName\>* で新しいデータベースの名前。</span><span class="sxs-lookup"><span data-stu-id="7410f-122">Replace the *\<ServerName\>* string with the new server name, and *\<DatabaseName\>* with the new database name.</span></span> <span data-ttu-id="7410f-123">次の接続文字列を更新します。</span><span class="sxs-lookup"><span data-stu-id="7410f-123">Update the following connection strings:</span></span>  
  
         <span data-ttu-id="7410f-124">\<appSettings\></span><span class="sxs-lookup"><span data-stu-id="7410f-124">\<appSettings\></span></span>  
  
         <span data-ttu-id="7410f-125"><add key="BamServer" value="*\<ServerName\>*" /\></span><span class="sxs-lookup"><span data-stu-id="7410f-125"><add key="BamServer" value="*\<ServerName\>*" /\></span></span>  
  
         <span data-ttu-id="7410f-126"><add key="BamDatabase" value="*\<DatabaseName\>*" /\></span><span class="sxs-lookup"><span data-stu-id="7410f-126"><add key="BamDatabase" value="*\<DatabaseName\>*" /\></span></span>  
  
         <span data-ttu-id="7410f-127">\<add key="MaxResultRows" value="2000" /\></span><span class="sxs-lookup"><span data-stu-id="7410f-127">\<add key="MaxResultRows" value="2000" /\></span></span>  
  
         <span data-ttu-id="7410f-128">\</appSettings\></span><span class="sxs-lookup"><span data-stu-id="7410f-128">\</appSettings\></span></span>  
  
    -   [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="7410f-129">\BAMPortal\BamQueryService\Web.Config.</span><span class="sxs-lookup"><span data-stu-id="7410f-129">\BAMPortal\BamQueryService\Web.Config.</span></span>  
  
         <span data-ttu-id="7410f-130">置換、  *\<ServerName\>*  、新しいサーバー名の文字列と *\<DatabaseName\>* で新しいデータベースの名前。</span><span class="sxs-lookup"><span data-stu-id="7410f-130">Replace the *\<ServerName\>* string with the new server name and *\<DatabaseName\>* with the new database name.</span></span> <span data-ttu-id="7410f-131">次の接続文字列を更新します。</span><span class="sxs-lookup"><span data-stu-id="7410f-131">Update the following connection strings:</span></span>  
  
         <span data-ttu-id="7410f-132">\<appSettings\></span><span class="sxs-lookup"><span data-stu-id="7410f-132">\<appSettings\></span></span>  
  
         <span data-ttu-id="7410f-133">\<キーを追加"BamServer"の値を = ="*\<ServerName\>*"/\></span><span class="sxs-lookup"><span data-stu-id="7410f-133">\<add key="BamServer" value="*\<ServerName\>*" /\></span></span>  
  
         <span data-ttu-id="7410f-134">\<add key="BamDatabase" value="*\<DatabaseName\>*" /\></span><span class="sxs-lookup"><span data-stu-id="7410f-134">\<add key="BamDatabase" value="*\<DatabaseName\>*" /\></span></span>  
  
         <span data-ttu-id="7410f-135">\<add key="MaxResultRows" value="2000" /\></span><span class="sxs-lookup"><span data-stu-id="7410f-135">\<add key="MaxResultRows" value="2000" /\></span></span>  
  
         <span data-ttu-id="7410f-136">\</appSettings\></span><span class="sxs-lookup"><span data-stu-id="7410f-136">\</appSettings\></span></span>  
  
5.  <span data-ttu-id="7410f-137">コマンド プロンプトを開きます ([スタート] メニュー > コマンド プロンプト) を次のディレクトリに移動: [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\Schema\Restore です。</span><span class="sxs-lookup"><span data-stu-id="7410f-137">Open a command prompt (Start menu > Command Prompt), and navigate to the following directory: [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\Schema\Restore.</span></span>  
  
6.  <span data-ttu-id="7410f-138">右クリック**SampleUpdateInfo.xml**、および**編集**です。</span><span class="sxs-lookup"><span data-stu-id="7410f-138">Right-click **SampleUpdateInfo.xml**, and **Edit**.</span></span>  
  
    1.  <span data-ttu-id="7410f-139">すべてのデータベース セクションでは、OldPrimaryImportDatabase、PrimaryImportDatabase、ArchivingDatabase、AnalysisDatabase、StarSchemaDatabase、およびアラートを除くコメントします。</span><span class="sxs-lookup"><span data-stu-id="7410f-139">Comment out all of the database sections except for the  OldPrimaryImportDatabase, PrimaryImportDatabase, ArchivingDatabase, AnalysisDatabase, StarSchemaDatabase, and Alert.</span></span> 
    2.  <span data-ttu-id="7410f-140">OldPrimaryImportDatabase、PrimaryImportDatabase、ArchivingDatabase、AnalysisDatabase、StarSchemaDatabase、および警告のセクションでは、設定、 **SourceServer**と**移行先サーバー**に、これらのデータベースが存在する既存のサーバーの名前です。</span><span class="sxs-lookup"><span data-stu-id="7410f-140">For the OldPrimaryImportDatabase, PrimaryImportDatabase, ArchivingDatabase, AnalysisDatabase, StarSchemaDatabase, and Alert sections, set the **SourceServer** and **Destination Server** to the name of the existing server where those databases reside.</span></span>  
  
    3.  <span data-ttu-id="7410f-141">PrimaryImportDatabase、設定、 **"SourceServer"** BAM プライマリ インポート データベースを移動したサーバーの名前にします。</span><span class="sxs-lookup"><span data-stu-id="7410f-141">For PrimaryImportDatabase, set the **"SourceServer"** to the name of the server where you have moved the BAM Primary Import database.</span></span>  
  
        > [!IMPORTANT]
        >  <span data-ttu-id="7410f-142">送信元システムおよび送信先システムの名前は、引用符で囲んでください。</span><span class="sxs-lookup"><span data-stu-id="7410f-142">Include the quotation marks around the name of the source and destination systems.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="7410f-143">BizTalk Server データベースの名前を変更した場合は、データベース名も更新することを確認します。</span><span class="sxs-lookup"><span data-stu-id="7410f-143">If you renamed any of the BizTalk Server databases, be sure to also update the database names.</span></span>  
  
    4.  <span data-ttu-id="7410f-144">ファイルの編集を終了したら、ファイルを保存して閉じます。</span><span class="sxs-lookup"><span data-stu-id="7410f-144">When you are finished editing the file, save it, and exit.</span></span>  
  
7.  <span data-ttu-id="7410f-145">コマンド プロンプトで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="7410f-145">At the command prompt, type:</span></span>  
  
     <span data-ttu-id="7410f-146">**cscript UpdateDatabase.vbs SampleUpdateInfo.xml**</span><span class="sxs-lookup"><span data-stu-id="7410f-146">**cscript UpdateDatabase.vbs SampleUpdateInfo.xml**</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7410f-147">UpdateDatabase.vbs を一度だけ実行します。</span><span class="sxs-lookup"><span data-stu-id="7410f-147">Only run UpdateDatabase.vbs once.</span></span>  
    > 
    >  <span data-ttu-id="7410f-148">64 ビット コンピューターでは、64 ビット コマンド プロンプトから UpdateDatabase.vbs を実行します。</span><span class="sxs-lookup"><span data-stu-id="7410f-148">On 64-bit computers, run UpdateDatabase.vbs from a 64-bit command prompt.</span></span>  
  
8. <span data-ttu-id="7410f-149">コマンド プロンプトで、次のディレクトリに移動します</span><span class="sxs-lookup"><span data-stu-id="7410f-149">At the command prompt, navigate to the following directory:</span></span>  
  
     [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="7410f-150">\Tracking</span><span class="sxs-lookup"><span data-stu-id="7410f-150">\Tracking</span></span>  
  
9. <span data-ttu-id="7410f-151">コマンド プロンプトで、bm.exe.config を編集して、key="DefaultServer" の値を新しいサーバー名に変更し、ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="7410f-151">At the command prompt, edit bm.exe.config, change the value of key="DefaultServer" to the new server name, and then save the file.</span></span>  
  
10. <span data-ttu-id="7410f-152">すべての BAM ライブ データの Microsoft Excel ファイルで BAMPrimaryImport データベースへの参照を更新します。</span><span class="sxs-lookup"><span data-stu-id="7410f-152">Update the reference to BAMPrimaryImport database in all BAM Livedata Microsoft Excel files.</span></span> <span data-ttu-id="7410f-153">各ファイルで次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="7410f-153">For each file:</span></span>  
  
    1.  <span data-ttu-id="7410f-154">Excel ライブ データ ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="7410f-154">Open the Excel live data file.</span></span> <span data-ttu-id="7410f-155">ファイル名の末尾は _LiveData.xls となっています。</span><span class="sxs-lookup"><span data-stu-id="7410f-155">The file name ends with _LiveData.xls.</span></span>  
  
    2.  <span data-ttu-id="7410f-156">**BAM**  メニューのをクリックして **BAM データベースの接続**します。</span><span class="sxs-lookup"><span data-stu-id="7410f-156">On the **BAM** menu, click **BAM DB Connection**.</span></span>  
  
    3.  <span data-ttu-id="7410f-157">**[BAM データベースの** ] ダイアログ ボックスでは、SQL Server および BAMPrimaryImport データベースを入力し、をクリックして **OK**します。</span><span class="sxs-lookup"><span data-stu-id="7410f-157">In the **Select BAM Database** dialog box, enter the SQL Server and BAMPrimaryImport database, and then click **OK**.</span></span>  
  
    4.  <span data-ttu-id="7410f-158">**ファイル**  メニューのをクリックして **を閉じるし、Microsoft Excel へ戻る**します。</span><span class="sxs-lookup"><span data-stu-id="7410f-158">On the **File** menu, click **Close and Return to Microsoft Excel**.</span></span>  
  
    5.  <span data-ttu-id="7410f-159">**[ファイル]** メニューの **[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7410f-159">On the **File** menu, click **Save**.</span></span>  
  
11. <span data-ttu-id="7410f-160">BizTalk Server アプリケーション サービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="7410f-160">Restart the BizTalk Application service.</span></span>  
  
    1.  <span data-ttu-id="7410f-161">開いている **services.msc**します。</span><span class="sxs-lookup"><span data-stu-id="7410f-161">Open **services.msc**.</span></span>  
  
    2.  <span data-ttu-id="7410f-162">右クリックし、 **BizTalk Service BizTalk Group: BizTalkServerApplication**サービス、し**開始**です。</span><span class="sxs-lookup"><span data-stu-id="7410f-162">Right-click the **BizTalk Service BizTalk Group: BizTalkServerApplication** service, and then **Start**.</span></span>  
  
12. <span data-ttu-id="7410f-163">すべての BAM キューブ更新およびデータ保守 DTS パッケージを有効にします。</span><span class="sxs-lookup"><span data-stu-id="7410f-163">Enable any BAM cube update and data maintenance DTS packages.</span></span>  
  
13. <span data-ttu-id="7410f-164">不完全なアクティビティ インスタンスを解決するには、次を参照してください。[不完全なアクティビティのインスタンスを解決するには](../core/how-to-resolve-incomplete-activity-instances.md)します。</span><span class="sxs-lookup"><span data-stu-id="7410f-164">To resolve any incomplete trace instances, see [Resolve Incomplete Activity Instances](../core/how-to-resolve-incomplete-activity-instances.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7410f-165">参照</span><span class="sxs-lookup"><span data-stu-id="7410f-165">See Also</span></span>  
 [<span data-ttu-id="7410f-166">BAM のバックアップと復元</span><span class="sxs-lookup"><span data-stu-id="7410f-166">Backing Up and Restoring BAM</span></span>](../core/backing-up-and-restoring-bam.md)
