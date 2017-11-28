---
title: "BAM Notification を移動する方法はサービス Databases1 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 89b4938e-ea4a-48d3-80c3-eb9401e28323
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1a5f643d764790b37deaab445290f1230c9ed8ba
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-move-the-bam-notification-services-databases"></a><span data-ttu-id="abf5c-102">BAM Notification Services データベースを移動する方法</span><span class="sxs-lookup"><span data-stu-id="abf5c-102">How to Move the BAM Notification Services Databases</span></span>
<span data-ttu-id="abf5c-103">この手順を使用すると、BAM Notification Services データベースを別のサーバーに移動します。</span><span class="sxs-lookup"><span data-stu-id="abf5c-103">You can use this procedure to move the BAM Notification Services database to another server.</span></span>  <span data-ttu-id="abf5c-104">エンド ツー エンドのシナリオの観点から BAM Notification Services データベースの移動にも 2 つの主要な手順が含まれます。</span><span class="sxs-lookup"><span data-stu-id="abf5c-104">From an end-to-end scenario perspective, moving the BAM Notification Services database involves two major steps:</span></span>  
  
-   [<span data-ttu-id="abf5c-105">BAM Notification Services データベースを移動します。</span><span class="sxs-lookup"><span data-stu-id="abf5c-105">Moving the BAM Notification Services Database</span></span>](../technical-guides/how-to-move-the-bam-notification-services-databases1.md#BKMK_NotiMoveDB)  
  
-   [<span data-ttu-id="abf5c-106">サービスのデータベースを新しい BAM 通知への参照を更新</span><span class="sxs-lookup"><span data-stu-id="abf5c-106">Updating References to the New BAM Notification Services Databases</span></span>](../technical-guides/how-to-move-the-bam-notification-services-databases1.md#BKMK_NotiUpdate)  
  
> [!NOTE]  
>  <span data-ttu-id="abf5c-107">BAM Notification Services Application (BAMAlertsApplication) データベースおよび BAM Notification Services Instance (BAMAlertsNSMain) データベースを一緒に移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="abf5c-107">You must move the BAM Notification Services Application (BAMAlertsApplication) database and the BAM Notification Services Instance (BAMAlertsNSMain) database together.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="abf5c-108">前提条件</span><span class="sxs-lookup"><span data-stu-id="abf5c-108">Prerequisites</span></span>  
 <span data-ttu-id="abf5c-109">この手順を実行するには、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] sysadmin 固定サーバー ロールのメンバーであるアカウントを使用してログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="abf5c-109">You must be logged on with an account that is a member of the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] sysadmin fixed server role to perform this procedure.</span></span>  
  
##  <span data-ttu-id="abf5c-110"><a name="BKMK_NotiMoveDB"></a>BAM Notification Services データベースを移動します。</span><span class="sxs-lookup"><span data-stu-id="abf5c-110"><a name="BKMK_NotiMoveDB"></a> Moving the BAM Notification Services Database</span></span>  
 <span data-ttu-id="abf5c-111">BAM Notification Services データベースを移動する次の手順で、手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="abf5c-111">Perform the steps in the following procedure to move the BAM Notification Services database.</span></span>  
  
#### <a name="to-move-the-bam-notification-services-database"></a><span data-ttu-id="abf5c-112">BAM Notification Services データベースを移動するには</span><span class="sxs-lookup"><span data-stu-id="abf5c-112">To move the BAM Notification Services database</span></span>  
  
1.  <span data-ttu-id="abf5c-113">すべての BAM キューブ更新およびデータ保守 SSIS パッケージを停止するか、BAM Notification Services データベースを復元が完了するまで実行されないように措置を講じます。</span><span class="sxs-lookup"><span data-stu-id="abf5c-113">Stop any BAM cube update and data maintenance SSIS packages, or prevent them from running until you have restored the BAM Notification Services database.</span></span>  
  
2.  <span data-ttu-id="abf5c-114">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] サービスをすべて停止します。</span><span class="sxs-lookup"><span data-stu-id="abf5c-114">Stop all [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] services.</span></span> <span data-ttu-id="abf5c-115">詳細については、トピックを参照してください。[開始方法、停止、一時停止、再開、または BizTalk Server サービスを再起動](http://go.microsoft.com/fwlink/?LinkId=154394)(http://go.microsoft.com/fwlink/?LinkId=154394) で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。</span><span class="sxs-lookup"><span data-stu-id="abf5c-115">For more information, see the topic [How To Start, Stop, Pause, Resume, or Restart BizTalk Server Services](http://go.microsoft.com/fwlink/?LinkId=154394) (http://go.microsoft.com/fwlink/?LinkId=154394) in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help.</span></span>  
  
3.  <span data-ttu-id="abf5c-116">IIS サービスを停止します。</span><span class="sxs-lookup"><span data-stu-id="abf5c-116">Stop the IIS service.</span></span>  
  
4.  <span data-ttu-id="abf5c-117">BAM 警告 Notification service を停止します。</span><span class="sxs-lookup"><span data-stu-id="abf5c-117">Stop the BAM Alerts Notification service:</span></span>  
  
    1.  <span data-ttu-id="abf5c-118">をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリック**ok**です。</span><span class="sxs-lookup"><span data-stu-id="abf5c-118">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
    2.  <span data-ttu-id="abf5c-119">コマンド プロンプトで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="abf5c-119">At the command prompt, type:</span></span>  
  
         <span data-ttu-id="abf5c-120">**Net stop NS$ BamAlerts**</span><span class="sxs-lookup"><span data-stu-id="abf5c-120">**Net stop NS$BamAlerts**</span></span>  
  
5.  <span data-ttu-id="abf5c-121">古いサーバーで、BAM Notification Services データベースをバックアップします。</span><span class="sxs-lookup"><span data-stu-id="abf5c-121">Back up the BAM Notification Services database on the old server.</span></span> <span data-ttu-id="abf5c-122">データベースをバックアップする方法の手順についてに記載された手順に従います[する方法:、データベースのバックアップ (SQL Server Management Studio)](http://go.microsoft.com/fwlink/?LinkId=156510) (http://go.microsoft.com/fwlink/?LinkId=156510) で[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]オンライン ブック、データベースをバックアップする方法です。</span><span class="sxs-lookup"><span data-stu-id="abf5c-122">For instructions on backing up a database, follow the instructions at [How to: Back Up a Database (SQL Server Management Studio)](http://go.microsoft.com/fwlink/?LinkId=156510) (http://go.microsoft.com/fwlink/?LinkId=156510) in [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Books Online on how to back up a database.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="abf5c-123">BAMAlertsApplication データベースと BAMAlertsNSMain データベースのこの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="abf5c-123">Perform this step for both BAMAlertsApplication and BAMAlertsNSMain databases.</span></span>  
  
6.  <span data-ttu-id="abf5c-124">BAM Notification Services データベースに新しいコピー[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]コンピューター。</span><span class="sxs-lookup"><span data-stu-id="abf5c-124">Copy the BAM Notification Services database to the new [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] computer.</span></span>  
  
7.  <span data-ttu-id="abf5c-125">新しいサーバーで、BAM Notification Services データベースを復元します。</span><span class="sxs-lookup"><span data-stu-id="abf5c-125">Restore the BAM Notification Services database on the new server.</span></span> <span data-ttu-id="abf5c-126">データベースを復元する方法について以下に記載された手順[する方法: データベースのバックアップ (SQL Server Management Studio) を復元](http://go.microsoft.com/fwlink/?LinkId=156511)(http://go.microsoft.com/fwlink/?LinkId=156511) で[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]データベースを復元する方法のオンライン ブック。</span><span class="sxs-lookup"><span data-stu-id="abf5c-126">For instructions on restoring the database, follow the instructions at [How to: Restore a Database Backup (SQL Server Management Studio)](http://go.microsoft.com/fwlink/?LinkId=156511) (http://go.microsoft.com/fwlink/?LinkId=156511) in [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Books Online on how to restore a database.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="abf5c-127">BAMAlertsApplication データベースと BAMAlertsNSMain データベースのこの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="abf5c-127">Perform this step for both BAMAlertsApplication and BAMAlertsNSMain databases.</span></span>  
  
##  <span data-ttu-id="abf5c-128"><a name="BKMK_NotiUpdate"></a>サービスのデータベースを新しい BAM 通知への参照を更新</span><span class="sxs-lookup"><span data-stu-id="abf5c-128"><a name="BKMK_NotiUpdate"></a> Updating References to the New BAM Notification Services Databases</span></span>  
 <span data-ttu-id="abf5c-129">データベースを移動した後は、新しい BAM Notification Services データベースに対するすべての参照を更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="abf5c-129">After you have moved the database, you must update all the references to the new BAM Notification Services databases.</span></span> <span data-ttu-id="abf5c-130">次の参照を更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="abf5c-130">The following references must be updated:</span></span>  
  
-   <span data-ttu-id="abf5c-131">新しいデータベースとサーバーの名前で、BAM 構成を更新します。</span><span class="sxs-lookup"><span data-stu-id="abf5c-131">Update the BAM configuration with the new database and server names.</span></span> <span data-ttu-id="abf5c-132">参照してください[BAM 構成を更新する](../technical-guides/how-to-move-the-bam-notification-services-databases1.md#BKMK_NotiUpdateBAMConfig)です。</span><span class="sxs-lookup"><span data-stu-id="abf5c-132">See [To update the BAM configuration](../technical-guides/how-to-move-the-bam-notification-services-databases1.md#BKMK_NotiUpdateBAMConfig).</span></span>  
  
-   <span data-ttu-id="abf5c-133">すべてのコンピューターに、通知サービスを再登録、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]グループ。</span><span class="sxs-lookup"><span data-stu-id="abf5c-133">Re-register the Notification Service on all computers in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] group.</span></span> <span data-ttu-id="abf5c-134">参照してください[Notification Services を登録](../technical-guides/how-to-move-the-bam-notification-services-databases1.md#BKMK_NotiRegister)です。</span><span class="sxs-lookup"><span data-stu-id="abf5c-134">See [Register the Notification Services](../technical-guides/how-to-move-the-bam-notification-services-databases1.md#BKMK_NotiRegister).</span></span>  
  
###  <span data-ttu-id="abf5c-135"><a name="BKMK_NotiUpdateBAMConfig"></a>BAM 構成を更新するには</span><span class="sxs-lookup"><span data-stu-id="abf5c-135"><a name="BKMK_NotiUpdateBAMConfig"></a> To update the BAM configuration</span></span>  
  
1.  <span data-ttu-id="abf5c-136">BAM を復元するときに使用する .xml ファイルのコピーを用意します。</span><span class="sxs-lookup"><span data-stu-id="abf5c-136">Get a copy of the .xml file used for restoring BAM:</span></span>  
  
    1.  <span data-ttu-id="abf5c-137">をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリック**ok**です。</span><span class="sxs-lookup"><span data-stu-id="abf5c-137">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
    2.  <span data-ttu-id="abf5c-138">[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] が動作しているコンピューターで、次のフォルダーを参照します。</span><span class="sxs-lookup"><span data-stu-id="abf5c-138">On a computer running [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)], browse to the following folder:</span></span>  
  
        -   <span data-ttu-id="abf5c-139">場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]が 64 ビット バージョンの Windows Server にインストールされています。</span><span class="sxs-lookup"><span data-stu-id="abf5c-139">If [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is installed on a 64-bit version of Windows Server:</span></span>  
  
             <span data-ttu-id="abf5c-140">**%Programfiles (x86) %\Microsoft BizTalk Server 2010 \tracking**</span><span class="sxs-lookup"><span data-stu-id="abf5c-140">**%ProgramFiles(x86)%\Microsoft BizTalk Server 2010\Tracking**</span></span>  
  
        -   <span data-ttu-id="abf5c-141">場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]が 32 ビット バージョンの Windows Server にインストールされています。</span><span class="sxs-lookup"><span data-stu-id="abf5c-141">If [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is installed on a 32-bit version of Windows Server:</span></span>  
  
             <span data-ttu-id="abf5c-142">**%ProgramFiles%\Microsoft BizTalk Server 2010 \tracking**</span><span class="sxs-lookup"><span data-stu-id="abf5c-142">**%ProgramFiles%\Microsoft BizTalk Server 2010\Tracking**</span></span>  
  
    3.  <span data-ttu-id="abf5c-143">コマンド プロンプトで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="abf5c-143">At the command prompt, type:</span></span>  
  
         <span data-ttu-id="abf5c-144">**Bm.exe get-config –filename:BAMConfiguration.xml-サーバー:\<サーバー名 >-データベース:\<データベース >**</span><span class="sxs-lookup"><span data-stu-id="abf5c-144">**Bm.exe get-config –filename:BAMConfiguration.xml -server:\<servername> -database:\<database>**</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="abf5c-145">このコマンドを実行するときに、サーバーの構成情報の取得元の実際の名前に置き換える<servername>の構成情報の取得元のデータベースの実際の名前を使用して<database>です。</span><span class="sxs-lookup"><span data-stu-id="abf5c-145">When running this command, substitute the actual name of the server from which to get the configuration information for <servername> and substitute the actual name of the database from which to get the configuration information for <database>.</span></span> <span data-ttu-id="abf5c-146">詳細については、BAM 管理 (BM) ユーティリティを使用して、次を参照してください。[インフラストラクチャ管理コマンド](http://go.microsoft.com/fwlink/?LinkId=156516)(http://go.microsoft.com/fwlink/?LinkId=156516) で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。</span><span class="sxs-lookup"><span data-stu-id="abf5c-146">For more information about using the BAM Management (BM) utility, see [Infrastructure Management Commands](http://go.microsoft.com/fwlink/?LinkId=156516) (http://go.microsoft.com/fwlink/?LinkId=156516) in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help.</span></span>  
  
2.  <span data-ttu-id="abf5c-147">BAMConfiguration.xml ファイルを編集し、変更、 **DBServer**内のプロパティ、`<DeploymentUnit Name="Alert">`セクションに新しいサーバーの名前。</span><span class="sxs-lookup"><span data-stu-id="abf5c-147">Edit the BAMConfiguration.xml file and change the **DBServer** properties in the `<DeploymentUnit Name="Alert">` section to the new server name.</span></span>  
  
3.  <span data-ttu-id="abf5c-148">BAMConfiguration.xml ファイルを保存して閉じます。</span><span class="sxs-lookup"><span data-stu-id="abf5c-148">Save and close the BAMConfiguration.xml file.</span></span>  
  
4.  <span data-ttu-id="abf5c-149">をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリック**ok**です。</span><span class="sxs-lookup"><span data-stu-id="abf5c-149">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="abf5c-150">[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] が動作しているコンピューターで、次のフォルダーを参照します。</span><span class="sxs-lookup"><span data-stu-id="abf5c-150">On a computer running [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)], browse to the following folder:</span></span>  
  
    -   <span data-ttu-id="abf5c-151">場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]が 64 ビット バージョンの Windows Server にインストールされています。</span><span class="sxs-lookup"><span data-stu-id="abf5c-151">If [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is installed on a 64-bit version of Windows Server:</span></span>  
  
         <span data-ttu-id="abf5c-152">**%Programfiles (x86) %\Microsoft BizTalk Server 2010 \tracking**</span><span class="sxs-lookup"><span data-stu-id="abf5c-152">**%ProgramFiles(x86)%\Microsoft BizTalk Server 2010\Tracking**</span></span>  
  
    -   <span data-ttu-id="abf5c-153">場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]が 32 ビット バージョンの Windows Server にインストールされています。</span><span class="sxs-lookup"><span data-stu-id="abf5c-153">If [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is installed on a 32-bit version of Windows Server:</span></span>  
  
         <span data-ttu-id="abf5c-154">**%ProgramFiles%\Microsoft BizTalk Server 2010 \tracking**</span><span class="sxs-lookup"><span data-stu-id="abf5c-154">**%ProgramFiles%\Microsoft BizTalk Server 2010\Tracking**</span></span>  
  
6.  <span data-ttu-id="abf5c-155">コマンド プロンプトで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="abf5c-155">At the command prompt, type:</span></span>  
  
     <span data-ttu-id="abf5c-156">**bm.exe 更新-config-FileName:BAMConfiguration.xml**</span><span class="sxs-lookup"><span data-stu-id="abf5c-156">**bm.exe update-config -FileName:BAMConfiguration.xml**</span></span>  
  
###  <span data-ttu-id="abf5c-157"><a name="BKMK_NotiRegister"></a>Notification Services を登録します。</span><span class="sxs-lookup"><span data-stu-id="abf5c-157"><a name="BKMK_NotiRegister"></a> Register the Notification Services</span></span>  
 <span data-ttu-id="abf5c-158">BAM Notification Services データベースを移動した後は、Notification Services (NSservice.exe) を実行している BizTalk Server グループ内のすべてのコンピューターで、通知サービスを再登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="abf5c-158">After you have moved the BAM Notification Services database, you must re-register the Notification Service on all computers in the BizTalk Server group that are running Notification Services (NSservice.exe).</span></span> <span data-ttu-id="abf5c-159">こうして初めて、Notification Services から新しい場所のデータベースに接続できるようになります。</span><span class="sxs-lookup"><span data-stu-id="abf5c-159">This enables Notification Services to connect to the databases in their new location.</span></span> <span data-ttu-id="abf5c-160">Notification Services を登録する方法の手順については、手順 5. ~ 11. を[BAM Notification Services データベースへの参照を更新する方法](http://go.microsoft.com/fwlink/?LinkId=156684)(http://go.microsoft.com/fwlink/?LinkId=156684) で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプします。</span><span class="sxs-lookup"><span data-stu-id="abf5c-160">For instructions on how to register the Notification Services, follow steps 5 through 11 at [How to Update References to the BAM Notification Services Databases](http://go.microsoft.com/fwlink/?LinkId=156684) (http://go.microsoft.com/fwlink/?LinkId=156684) in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help.</span></span>  
  
 <span data-ttu-id="abf5c-161">上記のリンクに記載の手順を実行中に、次に注意してください。</span><span class="sxs-lookup"><span data-stu-id="abf5c-161">Note the following while performing steps mentioned in the preceding link:</span></span>  
  
-   <span data-ttu-id="abf5c-162">手順 5. と 6. 先行リンクには、BAM 構成 XML に、次のプロパティで示されているサーバーで実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="abf5c-162">Steps 5 and 6 in the preceding link must be performed on the servers listed in the BAM configuration XML for the following properties:</span></span>  
  
    ```  
    <DeploymentUnit Name="Alert">  
      <Property Name="GeneratorServerName">Server_Name</Property>  
      <Property Name="ProviderServerName">Server_Name</Property>  
      <Property Name="DistributorServerName">Server_Name</Property>  
    </DeploymentUnit>  
  
    ```  
  
-   <span data-ttu-id="abf5c-163">手順 7 ~ 11 は、BAM ポータルをホストするコンピューターで実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="abf5c-163">Step 7 through 11 must be performed on the computer that hosts the BAM portal.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="abf5c-164">参照</span><span class="sxs-lookup"><span data-stu-id="abf5c-164">See Also</span></span>  
 [<span data-ttu-id="abf5c-165">データベースの移動</span><span class="sxs-lookup"><span data-stu-id="abf5c-165">Moving Databases</span></span>](../technical-guides/moving-databases.md)