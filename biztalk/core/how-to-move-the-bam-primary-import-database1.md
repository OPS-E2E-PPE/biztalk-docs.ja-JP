---
title: BAM プライマリ インポート データベース 1 に移動する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- migrating, Primary Import database [BAM]
- Primary Import database [BAM], migrating
ms.assetid: fab13fea-5c35-4a9f-977d-cc45545c54b2
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6a63c556bfb95f4b22a3256540d3ecb336a17f7f
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25972664"
---
# <a name="how-to-move-the-bam-primary-import-database"></a><span data-ttu-id="93de4-102">BAM プライマリ インポート データベースを移動する方法</span><span class="sxs-lookup"><span data-stu-id="93de4-102">How to Move the BAM Primary Import Database</span></span>
<span data-ttu-id="93de4-103">ここでは、BAM プライマリ インポート データベースを他のサーバーに移動する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="93de4-103">You can use this procedure to move the BAM Primary Import database to another server.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="93de4-104">前提条件</span><span class="sxs-lookup"><span data-stu-id="93de4-104">Prerequisites</span></span>  
 <span data-ttu-id="93de4-105">この手順を実行するには、SQL Server sysadmin 固定サーバーの役割のメンバーであるアカウントを使用してログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="93de4-105">You must be logged on with an account that is a member of the SQL Server sysadmin fixed server role to perform this procedure.</span></span>  
  
### <a name="to-move-the-bam-primary-import-database"></a><span data-ttu-id="93de4-106">BAM プライマリ インポート データベースを移動するには</span><span class="sxs-lookup"><span data-stu-id="93de4-106">To move the BAM Primary Import database</span></span>  
  
1.  <span data-ttu-id="93de4-107">BizTalk Server サービスをすべて停止します。</span><span class="sxs-lookup"><span data-stu-id="93de4-107">Stop all BizTalk Server services.</span></span> <span data-ttu-id="93de4-108">詳細については、次を参照してください。[開始、停止、一時停止、再開、または BizTalk Server サービスを再起動する方法](../core/how-to-start-stop-pause-resume-or-restart-biztalk-server-services.md)です。</span><span class="sxs-lookup"><span data-stu-id="93de4-108">For more information, see [How to Start, Stop, Pause, Resume, or Restart BizTalk Server Services](../core/how-to-start-stop-pause-resume-or-restart-biztalk-server-services.md).</span></span>  
  
2.  <span data-ttu-id="93de4-109">IIS サービスを停止します。</span><span class="sxs-lookup"><span data-stu-id="93de4-109">Stop the IIS service.</span></span>  
  
3.  <span data-ttu-id="93de4-110">BAM 警告の Notification Services を停止します。</span><span class="sxs-lookup"><span data-stu-id="93de4-110">Stop the BAM Alerts Notification Service:</span></span>  
  
    1.  <span data-ttu-id="93de4-111">をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリック**ok**です。</span><span class="sxs-lookup"><span data-stu-id="93de4-111">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
    2.  <span data-ttu-id="93de4-112">コマンド プロンプトで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="93de4-112">At the command prompt, type:</span></span>  
  
        ```  
        Net stop NS$BamAlerts  
        ```  
  
4.  <span data-ttu-id="93de4-113">SQL Server Books Online に記載されている手順に従い、古いサーバーの BAM プライマリ インポート データベースをバックアップします。</span><span class="sxs-lookup"><span data-stu-id="93de4-113">Follow the instructions in SQL Server Books Online to back up the BAM Primary Import database on the old server.</span></span>  
  
5.  <span data-ttu-id="93de4-114">BAM プライマリ インポート データベースを新しい SQL サーバーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="93de4-114">Copy the BAM Primary Import database to the new SQL Server.</span></span>  
  
6.  <span data-ttu-id="93de4-115">SQL Server Books Online に記載されている手順に従い、新しいサーバーに BAM プライマリ インポート データベースを復元します。</span><span class="sxs-lookup"><span data-stu-id="93de4-115">Follow the instructions in SQL Server Books Online to restore the BAM Primary Import database on the new server.</span></span>  
  
7.  <span data-ttu-id="93de4-116">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] が動作しているコンピューターで、次のフォルダーを参照します。</span><span class="sxs-lookup"><span data-stu-id="93de4-116">On a computer running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], browse to the following folder:</span></span>  
  
     [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="93de4-117">Schema\Restore</span><span class="sxs-lookup"><span data-stu-id="93de4-117">Schema\Restore</span></span>  
  
8.  <span data-ttu-id="93de4-118">右クリック**SampleUpdateInfo.xml**、クリックして**編集**です。</span><span class="sxs-lookup"><span data-stu-id="93de4-118">Right-click **SampleUpdateInfo.xml**, and then click **Edit**.</span></span>  
  
9. <span data-ttu-id="93de4-119">ファイルのプライマリ インポート データベース セクションで置き換えます **"SourceServer"** ソース システムと、置換の名前を持つ **"DestinationServer"** 送信先システムの名前に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="93de4-119">In the Primary Import Database section of the file, replace **"SourceServer"** with the name of the source system, and then replace **"DestinationServer"** with the name of the destination system.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="93de4-120">送信元システムおよび送信先システムの名前は、引用符で囲んでください。</span><span class="sxs-lookup"><span data-stu-id="93de4-120">Include the quotation marks around the name of the source and destination systems.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="93de4-121">いずれかの BizTalk Server データベースの名前を変更した場合、それに応じてデータベース名も更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="93de4-121">If you renamed any of the BizTalk Server databases, you must also update the database names as appropriate.</span></span>  
  
10. <span data-ttu-id="93de4-122">xml ファイルの次の行のコメント化を解除します。</span><span class="sxs-lookup"><span data-stu-id="93de4-122">Uncomment the following lines in the xml file:</span></span>  
  
    ```  
    - <UpdateConfiguration>  
      <MessageBoxDB oldDBName="BizTalkMsgboxDb" oldDBServer="Server01" newDBName="BizTalkMsgboxDb" newDBServer="Server01" IsMaster="1" />   
      <TrackingDB oldDBName="BizTalkDTADb" oldDBServer="Server01" newDBName="BizTalkDTADb" newDBServer="Server01" />   
      <ManagementDB oldDBName="BizTalkMgmtDb" oldDBServer="Server01" newDBName="BizTalkMgmtDb" newDBServer="Server01" />   
    - <BAM>  
    - <DeploymentUnit Name="OldPrimaryImportDatabase">  
      <Property Name="ServerName">Server01</Property>   
      <Property Name="DatabaseName">BAMPrimaryImport</Property>   
      </DeploymentUnit>  
    - <DeploymentUnit Name="PrimaryImportDatabase">  
      <Property Name="ServerName">Server02</Property>   
      <Property Name="DatabaseName">BAMPrimaryImport</Property>   
      </DeploymentUnit>  
    - <DeploymentUnit Name="ArchivingDatabase">  
      <Property Name="ServerName">Server01</Property>   
      <Property Name="DatabaseName">BAMArchive</Property>   
      </DeploymentUnit>  
    - <DeploymentUnit Name="AnalysisDatabase">  
      <Property Name="ServerName">Server01</Property>   
      <Property Name="DatabaseName">BAMAnalysis</Property>   
      </DeploymentUnit>  
    - <DeploymentUnit Name="StarSchemaDatabase">  
      <Property Name="ServerName">Server01</Property>   
      <Property Name="DatabaseName">BAMStarSchema</Property>   
      </DeploymentUnit>  
    - <DeploymentUnit Name="Alert">  
      <Property Name="DBServer">Server01</Property>   
      <Property Name="InstanceDatabaseName">BAMAlerts</Property>   
      </DeploymentUnit>  
      </BAM>  
    - <OtherDatabases>  
      <Database Name="SSO" oldDBName="SSODB" oldDBServer="Server01" newDBName="SSODB" newDBServer="Server01" />   
      </OtherDatabases>  
      </UpdateConfiguration>  
    ```  
  
11. <span data-ttu-id="93de4-123">ファイルの編集を終了したら、このファイルを保存して閉じます。</span><span class="sxs-lookup"><span data-stu-id="93de4-123">When you are finished editing the file, save it and exit.</span></span>  
  
12. <span data-ttu-id="93de4-124">をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリック**ok**です。</span><span class="sxs-lookup"><span data-stu-id="93de4-124">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
13. <span data-ttu-id="93de4-125">コマンド プロンプトで、次のディレクトリに移動します</span><span class="sxs-lookup"><span data-stu-id="93de4-125">At the command prompt, navigate to the following directory:</span></span>  
  
     [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="93de4-126">Schema\Restore</span><span class="sxs-lookup"><span data-stu-id="93de4-126">Schema\Restore</span></span>  
  
14. <span data-ttu-id="93de4-127">コマンド プロンプトで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="93de4-127">At the command prompt, type:</span></span>  
  
     <span data-ttu-id="93de4-128">**cscript UpdateDatabase.vbs SampleUpdateInfo.xml**</span><span class="sxs-lookup"><span data-stu-id="93de4-128">**cscript UpdateDatabase.vbs SampleUpdateInfo.xml**</span></span>  
  
15. <span data-ttu-id="93de4-129">すべての BAM ライブ データの Microsoft Excel ファイルで BAM プライマリ インポート データベースへの参照を更新します。</span><span class="sxs-lookup"><span data-stu-id="93de4-129">Update the reference to BAM Primary Import Database in all BAM Livedata Microsoft Excel files.</span></span> <span data-ttu-id="93de4-130">各ファイルで次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="93de4-130">For each file:</span></span>  
  
    1.  <span data-ttu-id="93de4-131">Excel ライブ データ ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="93de4-131">Open the Excel live data file.</span></span> <span data-ttu-id="93de4-132">ファイル名の末尾は _LiveData.xls となっています。</span><span class="sxs-lookup"><span data-stu-id="93de4-132">The file name ends with _LiveData.xls.</span></span>  
  
    2.  <span data-ttu-id="93de4-133">**BAM**  メニューをクリックして**BAM データベースの接続**です。</span><span class="sxs-lookup"><span data-stu-id="93de4-133">On the **BAM** menu, click **BAM DB Connection**.</span></span>  
  
    3.  <span data-ttu-id="93de4-134">**[BAM データベース**] ダイアログ ボックスでは、SQL Server および BAMPrimaryImport データベースを入力し、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="93de4-134">In the **Select BAM Database** dialog box, enter the SQL Server and BAMPrimaryImport database, and then click **OK**.</span></span>  
  
    4.  <span data-ttu-id="93de4-135">**ファイル** メニューのをクリックして**閉じて Microsoft Excel へ戻る**です。</span><span class="sxs-lookup"><span data-stu-id="93de4-135">On the **File** menu, click **Close and Return to Microsoft Excel**.</span></span>  
  
    5.  <span data-ttu-id="93de4-136">**[ファイル]** メニューの **[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="93de4-136">On the **File** menu, click **Save**.</span></span>  
  
16. <span data-ttu-id="93de4-137">次の手順を実行して、すべての BAM 分析 DTS パッケージのサーバー名およびデータベース名を更新します。名前は "BAM_AN_" または "BAM_DM_" で始まります。</span><span class="sxs-lookup"><span data-stu-id="93de4-137">Update the server and database names in all BAM analysis DTS packages, which are prefixed with "BAM_AN_" or "BAM_DM_" by following these steps:</span></span>  
  
    1.  <span data-ttu-id="93de4-138">BAM をホストするサーバーで、SQL Server Enterprise Manager を開きます。</span><span class="sxs-lookup"><span data-stu-id="93de4-138">On the server hosting BAM, open SQL Server Enterprise Manager.</span></span>  
  
    2.  <span data-ttu-id="93de4-139">開く、**データ変換サービス**フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="93de4-139">Open the **Data Transformation Services** folder.</span></span>  
  
    3.  <span data-ttu-id="93de4-140">開く、**ローカル パッケージ**フォルダー、DTS パッケージを開きます。</span><span class="sxs-lookup"><span data-stu-id="93de4-140">Open the **Local Packages** folder, and then open the DTS packages.</span></span>  
  
    4.  <span data-ttu-id="93de4-141">**パッケージ** メニューのをクリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="93de4-141">On the **Package** menu, click **Properties**.</span></span>  
  
    5.  <span data-ttu-id="93de4-142">**グローバル変数** タブで、プライマリ インポート サーバーおよびデータベースの値を更新します。</span><span class="sxs-lookup"><span data-stu-id="93de4-142">On the **Global Variables** tab, update the values for the primary import server and database.</span></span>  
  
    6.  <span data-ttu-id="93de4-143">新しいサーバーおよびデータベースに対応するように、次の行を変更します。</span><span class="sxs-lookup"><span data-stu-id="93de4-143">Change the following lines to match your new server and database:</span></span>  
  
         <span data-ttu-id="93de4-144">PrimaryImportServer ="*\<ServerName\>*"</span><span class="sxs-lookup"><span data-stu-id="93de4-144">PrimaryImportServer= "*\<ServerName\>*"</span></span>  
  
         <span data-ttu-id="93de4-145">PrimaryImportDatabase ="*\<DatabaseName\>*"</span><span class="sxs-lookup"><span data-stu-id="93de4-145">PrimaryImportDatabase = "*\<DatabaseName\>*"</span></span>  
  
17. <span data-ttu-id="93de4-146">BizTalk Server サービスをすべて開始します。</span><span class="sxs-lookup"><span data-stu-id="93de4-146">Start all BizTalk Server services.</span></span> <span data-ttu-id="93de4-147">詳細については、次を参照してください。[開始、停止、一時停止、再開、または BizTalk Server サービスを再起動する方法](../core/how-to-start-stop-pause-resume-or-restart-biztalk-server-services.md)です。</span><span class="sxs-lookup"><span data-stu-id="93de4-147">For more information, see [How to Start, Stop, Pause, Resume, or Restart BizTalk Server Services](../core/how-to-start-stop-pause-resume-or-restart-biztalk-server-services.md).</span></span>  
  
18. <span data-ttu-id="93de4-148">IIS サービスを開始します。</span><span class="sxs-lookup"><span data-stu-id="93de4-148">Start the IIS service.</span></span>  
  
19. <span data-ttu-id="93de4-149">BAM 警告の Notification Services を開始します。</span><span class="sxs-lookup"><span data-stu-id="93de4-149">Start the BAM Alerts Notification Service:</span></span>  
  
    1.  <span data-ttu-id="93de4-150">をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリック**ok**です。</span><span class="sxs-lookup"><span data-stu-id="93de4-150">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
    2.  <span data-ttu-id="93de4-151">コマンド プロンプトで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="93de4-151">At the command prompt, type:</span></span>  
  
        ```  
        Net start NS$BamAlerts  
        ```  
  
## <a name="see-also"></a><span data-ttu-id="93de4-152">参照</span><span class="sxs-lookup"><span data-stu-id="93de4-152">See Also</span></span>  
 [<span data-ttu-id="93de4-153">BizTalk Server データベースの移動</span><span class="sxs-lookup"><span data-stu-id="93de4-153">Moving BizTalk Server Databases</span></span>](../core/moving-biztalk-server-databases.md)