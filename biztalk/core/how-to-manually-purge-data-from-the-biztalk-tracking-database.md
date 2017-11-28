---
title: "BizTalk 追跡データベースからデータを手動で削除する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Tracking database, purging
- purging, manually
- purging, warnings
ms.assetid: f350d850-5034-4166-940c-8d10b7b445fb
caps.latest.revision: "22"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 75cc2fa6a7e4f6318818534f6b3f99323f1d8ddf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-manually-purge-data-from-the-biztalk-tracking-database"></a><span data-ttu-id="aff4d-102">BizTalk 追跡データベースから手動でデータを削除する方法</span><span class="sxs-lookup"><span data-stu-id="aff4d-102">How to Manually Purge Data from the BizTalk Tracking Database</span></span>
<span data-ttu-id="aff4d-103">SQL Server エージェント ジョブである DTA Archive and Purge では、データベースの連続的な削除および格納された追跡データの圧縮により、BizTalk 追跡 (BizTalkDTADb) データベースから手動でデータを削除する必要性が低減されます。</span><span class="sxs-lookup"><span data-stu-id="aff4d-103">The DTA Archive and Purge SQL Server Agent job reduces the need to manually purge data from the BizTalk Tracking (BizTalkDTADb) database due to continuous purging of the database and compaction of stored tracking data.</span></span> <span data-ttu-id="aff4d-104">BizTalk 追跡 (BizTalkDTADb) データベースのサイズが、パフォーマンスが低下するほど大幅に大きくなり、DTA Archive and Purge ジョブがデータベース サイズの増大に対応できなくなった場合には、手動でデータを削除することが必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="aff4d-104">You might need to manually purge data if your BizTalk Tracking (BizTalkDTADb) database has grown so much that sustained performance degradation is occurring and the DTA Archive and Purge job is unable to keep up with the database growth.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="aff4d-105">ここで示す手順を実行すると、完了時刻に関係なく、完了したインスタンスのすべての追跡データが BizTalk 追跡 (BizTalkDTADb) データベースから削除されます。</span><span class="sxs-lookup"><span data-stu-id="aff4d-105">Performing this procedure deletes all tracking data for completed instances from the BizTalk Tracking (BizTalkDTADb) database regardless of completion time.</span></span> <span data-ttu-id="aff4d-106">この手順を実行する前に、BizTalk 追跡 (BizTalkDTADb) データベースを、他の [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] データベースとは別にアーカイブする必要があります。</span><span class="sxs-lookup"><span data-stu-id="aff4d-106">Before performing this procedure, you should archive the BizTalk Tracking (BizTalkDTADb) database separately from the other [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="aff4d-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="aff4d-107">Prerequisites</span></span>  
 <span data-ttu-id="aff4d-108">この手順を実行するには、SQL Server sysadmin 固定サーバーの役割のメンバーであるアカウントを使用してログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="aff4d-108">You must be logged on with an account that is a member of the SQL Server sysadmin fixed server role to perform this procedure.</span></span>  
  
### <a name="to-manually-purge-data-from-the-biztalk-tracking-database"></a><span data-ttu-id="aff4d-109">BizTalk 追跡データベースからデータを手動で削除するには</span><span class="sxs-lookup"><span data-stu-id="aff4d-109">To manually purge data from the BizTalk Tracking database</span></span>  
  
1.  <span data-ttu-id="aff4d-110">BizTalk Server データベースをバックアップします。</span><span class="sxs-lookup"><span data-stu-id="aff4d-110">Backup your BizTalk Server databases.</span></span>  
  
2.  <span data-ttu-id="aff4d-111">BizTalk 追跡 (BizTalkDTADb) データベースをアーカイブします。</span><span class="sxs-lookup"><span data-stu-id="aff4d-111">Archive the BizTalk Tracking (BizTalkDTADb) database.</span></span>  
  
3.  <span data-ttu-id="aff4d-112">サービス コンソールを開きます。</span><span class="sxs-lookup"><span data-stu-id="aff4d-112">Open the Services console.</span></span> <span data-ttu-id="aff4d-113">をクリックして**開始**、 をクリックして**実行**、し、入力**services.msc**です。</span><span class="sxs-lookup"><span data-stu-id="aff4d-113">Click **Start**, click **Run**, and then type **services.msc**.</span></span> <span data-ttu-id="aff4d-114">場合、**ユーザー アカウント制御**ダイアログが表示されたら、をクリックして**続行**です。</span><span class="sxs-lookup"><span data-stu-id="aff4d-114">If a **User Account Control** dialog is displayed, click **Continue**.</span></span>  
  
4.  <span data-ttu-id="aff4d-115">サービス コンソールが表示されたら、次の各サービスを検索して停止します。</span><span class="sxs-lookup"><span data-stu-id="aff4d-115">When the Services console appears, locate and then stop each of the following services.</span></span> <span data-ttu-id="aff4d-116">サービスを停止するには、サービス行を右クリックし、 **Services**  ウィンドウで、クリックして**停止**です。</span><span class="sxs-lookup"><span data-stu-id="aff4d-116">To stop a service, right-click the service row in the **Services** pane, and then click **Stop**.</span></span>  
  
    -   <span data-ttu-id="aff4d-117">BizTalkServiceBizTalkGroup: BizTalkServerApplication</span><span class="sxs-lookup"><span data-stu-id="aff4d-117">BizTalkServiceBizTalkGroup : BizTalkServerApplication</span></span>  
  
    -   <span data-ttu-id="aff4d-118">エンタープライズ シングル サインオン サービス</span><span class="sxs-lookup"><span data-stu-id="aff4d-118">Enterprise Single Sign-On Service</span></span>  
  
         <span data-ttu-id="aff4d-119">場合 BizTalkServiceBizTalkGroup: BizTalkServerApplication サービスが実行されている、エンタープライズ シングル サインオン サービスをシャット ダウンしようとすると、**その他のサービスの停止**ダイアログが表示されます。</span><span class="sxs-lookup"><span data-stu-id="aff4d-119">If the BizTalkServiceBizTalkGroup : BizTalkServerApplication service is running when you try to shut down the Enterprise Singe Sign-On Service, a **Stop Other Services** dialog will be displayed.</span></span> <span data-ttu-id="aff4d-120">**[はい]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="aff4d-120">Click **Yes**.</span></span>  
  
    -   <span data-ttu-id="aff4d-121">ルール エンジン更新サービス</span><span class="sxs-lookup"><span data-stu-id="aff4d-121">Rule Engine Update Service</span></span>  
  
5.  <span data-ttu-id="aff4d-122">をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="aff4d-122">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span> <span data-ttu-id="aff4d-123">場合、**ユーザー アカウント制御**ダイアログが表示されます、示されているアクションが、をクリックしてであることを確認**続行**です。</span><span class="sxs-lookup"><span data-stu-id="aff4d-123">If a **User Account Control** dialog is displayed, verify that the action described is what you want, and then click **Continue**.</span></span>  
  
6.  <span data-ttu-id="aff4d-124">**BizTalk Server 管理コンソール**ウィンドウの左側にある [エクスプ ローラー] ペインで、ダブルクリック**BizTalk グループ**を下の一覧を展開するをダブルクリックし、**プラットフォーム設定**、クリックして**ホスト インスタンス**です。</span><span class="sxs-lookup"><span data-stu-id="aff4d-124">In the **BizTalk Server Administration Console** in the explorer pane on the left side of the window, double-click **BizTalk Group** to expand the list below it, then double-click **Platform Settings**, and then click **Host Instances**.</span></span> <span data-ttu-id="aff4d-125">これは、ホスト インスタンスの一覧が表示されます (、**ホスト インスタンス**ペイン) に関連するプロパティは、画面の右側にあるとします。</span><span class="sxs-lookup"><span data-stu-id="aff4d-125">This will display a list of host instances (the **Host Instances** pane) and related properties, on the right side of the screen.</span></span>  
  
7.  <span data-ttu-id="aff4d-126">**ホスト インスタンス** ウィンドウでは、各実行中のホスト インスタンスを右クリックし、をクリックして**停止**です。</span><span class="sxs-lookup"><span data-stu-id="aff4d-126">In the **Host Instances** pane, right-click each running host instance, and then click **Stop**.</span></span>  
  
8.  <span data-ttu-id="aff4d-127">をクリックして**開始**には、**実行**、型**cmd**、順にクリック**[ok]**です。</span><span class="sxs-lookup"><span data-stu-id="aff4d-127">Click **Start**, go to **Run**, type **cmd**, and then click **OK**.</span></span>  
  
9. <span data-ttu-id="aff4d-128">コマンド プロンプトで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="aff4d-128">At the command prompt, type:</span></span>  
  
     <span data-ttu-id="aff4d-129">**net stop iisadmin/y**</span><span class="sxs-lookup"><span data-stu-id="aff4d-129">**net stop iisadmin /y**</span></span>  
  
     <span data-ttu-id="aff4d-130">これで、IIS Admin Service とこのサービスが依存しているすべてのサービスが 1 つずつ停止され、データの削除中に新しいデータが BizTalkDTADb に書き込まれるのを防止できます。</span><span class="sxs-lookup"><span data-stu-id="aff4d-130">This stops the IIS Admin Service and all dependent services, one-by-one and prevents new data from being written to the BizTalkDTADb while data is being purged.</span></span> <span data-ttu-id="aff4d-131">各サービスが停止されるたびに、サービスの一覧を書き留めておいてください。</span><span class="sxs-lookup"><span data-stu-id="aff4d-131">Write down the list of services as each one is stopped.</span></span> <span data-ttu-id="aff4d-132">このサービスの一覧は、後で IIS を再起動するときに必要になります。</span><span class="sxs-lookup"><span data-stu-id="aff4d-132">You will need to use this list of services later when you restart IIS.</span></span>  
  
     <span data-ttu-id="aff4d-133">このコマンドを発行した後に表示される出力の例を次に示します (コンピューターに表示される依存サービスは異なる場合があります)。</span><span class="sxs-lookup"><span data-stu-id="aff4d-133">Below is an example of the output you will see after issuing this command (the dependent services listed on your computer may vary):</span></span>  
  
    ```  
    The following services are dependent on the IIS Admin Service service. Stopping the IIS Admin Service service will also stop these services.  
    World Wide Web Publishing Service  
    HTTP SSL  
    ```  
  
10. <span data-ttu-id="aff4d-134">をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして**Microsoft SQL Server 2008 SP2**、順にクリック**SQL Server Management Studio**です。</span><span class="sxs-lookup"><span data-stu-id="aff4d-134">Click **Start**, click **All Programs**, click **Microsoft SQL Server 2008 SP2**, and then click **SQL Server Management Studio**.</span></span>  
  
11. <span data-ttu-id="aff4d-135">**サーバーへの接続**ダイアログ ボックスでは、BizTalk 追跡 (BizTalkDTADb) データベースが存在する SQL Server および適切な認証の種類の名前を指定し、をクリックして**接続**に適切な SQL Server に接続します。</span><span class="sxs-lookup"><span data-stu-id="aff4d-135">In the **Connect to Server** dialog box, specify the name of the SQL Server where the BizTalk Tracking (BizTalkDTADb) database resides and the appropriate authentication type, and then click **Connect** to connect to the appropriate SQL Server.</span></span>  
  
12. <span data-ttu-id="aff4d-136">**Microsoft SQL Server Management Studio**をダブルクリックして**データベース**をダブルクリックして、 **BizTalkDTADb**データベースをダブルクリックして**プログラミング**、クリックして**Stored Procedures**です。</span><span class="sxs-lookup"><span data-stu-id="aff4d-136">In **Microsoft SQL Server Management Studio**, double-click **Databases**, double-click the **BizTalkDTADb** database, double-click **Programmability**, and then click **Stored Procedures**.</span></span>  
  
13. <span data-ttu-id="aff4d-137">**オブジェクト エクスプ ローラーの詳細** ウィンドウを右クリックして**dtasp_purgeallcompletedtrackingdata**、クリックして**ストアド プロシージャの実行**です。</span><span class="sxs-lookup"><span data-stu-id="aff4d-137">In the **Object Explorer Details** pane, right-click **dtasp_PurgeAllCompletedTrackingData**, and then click **Execute Stored Procedure**.</span></span>  
  
14. <span data-ttu-id="aff4d-138">**プロシージャの実行**ダイアログ ボックスで、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="aff4d-138">In the **Execute Procedure** dialog box, click **OK**.</span></span>  
  
     <span data-ttu-id="aff4d-139">このストアド プロシージャにより、完了時刻に関係なく、完了したインスタンスに関連付けられたすべての追跡データが削除されます。</span><span class="sxs-lookup"><span data-stu-id="aff4d-139">This stored procedure deletes all tracking data associated with completed instances regardless of their completion time.</span></span>  
  
15. <span data-ttu-id="aff4d-140">[サービス] を開きます。</span><span class="sxs-lookup"><span data-stu-id="aff4d-140">Open Services.</span></span> <span data-ttu-id="aff4d-141">をクリックして**開始**、 をクリックして**実行**、し、入力**services.msc**です。</span><span class="sxs-lookup"><span data-stu-id="aff4d-141">Click **Start**, click **Run**, and then type **services.msc**.</span></span> <span data-ttu-id="aff4d-142">場合、**ユーザー アカウント制御**ダイアログが表示されます、示されているアクションが、をクリックしてであることを確認**続行**です。</span><span class="sxs-lookup"><span data-stu-id="aff4d-142">If a **User Account Control** dialog is displayed, verify that the action described is what you want, and then click **Continue**.</span></span>  
  
16. <span data-ttu-id="aff4d-143">次のサービスのそれぞれを右クリックし、をクリックして**開始**:</span><span class="sxs-lookup"><span data-stu-id="aff4d-143">Right-click each of the following services, and then click **Start**:</span></span>  
  
    -   <span data-ttu-id="aff4d-144">BizTalkServiceBizTalkGroup: BizTalkServerApplication</span><span class="sxs-lookup"><span data-stu-id="aff4d-144">BizTalkServiceBizTalkGroup : BizTalkServerApplication</span></span>  
  
    -   <span data-ttu-id="aff4d-145">エンタープライズ シングル サインオン サービス</span><span class="sxs-lookup"><span data-stu-id="aff4d-145">Enterprise Single Sign-On Service</span></span>  
  
    -   <span data-ttu-id="aff4d-146">ルール エンジン更新サービス</span><span class="sxs-lookup"><span data-stu-id="aff4d-146">Rule Engine Update Service</span></span>  
  
17. <span data-ttu-id="aff4d-147">をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="aff4d-147">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
18. <span data-ttu-id="aff4d-148">**BizTalk Server 管理コンソール**をダブルクリックして、 **BizTalk グループ**をダブルクリックして**プラットフォームの設定**、クリックして**ホストインスタンス**です。</span><span class="sxs-lookup"><span data-stu-id="aff4d-148">In the **BizTalk Server Administration Console**, double-click the **BizTalk Group**, double-click **Platform Settings**, and then click **Host Instances**.</span></span>  
  
19. <span data-ttu-id="aff4d-149">**オブジェクト エクスプ ローラーの詳細** ウィンドウでは、停止しているホスト インスタンスごとを右クリックし、をクリックして**開始**です。</span><span class="sxs-lookup"><span data-stu-id="aff4d-149">In the **Object Explorer Details** pane, right-click each stopped host instance, and then click **Start**.</span></span>  
  
20. <span data-ttu-id="aff4d-150">上記の手順 8. の説明に従って、コマンド プロンプトを起動します。</span><span class="sxs-lookup"><span data-stu-id="aff4d-150">Start a command prompt, as described in step 8 above.</span></span>  
  
21. <span data-ttu-id="aff4d-151">コマンド プロンプトでは、手順 4. で、各 IIS サービスを停止するを再起動します。</span><span class="sxs-lookup"><span data-stu-id="aff4d-151">At the command prompt, restart each of the IIS services that you stopped in step 4.</span></span> <span data-ttu-id="aff4d-152">型:</span><span class="sxs-lookup"><span data-stu-id="aff4d-152">Type:</span></span>  
  
     <span data-ttu-id="aff4d-153">**net start**  *\<IISserviceName >*</span><span class="sxs-lookup"><span data-stu-id="aff4d-153">**net start** *\<IISserviceName>*</span></span>  
  
     <span data-ttu-id="aff4d-154">ここで *\<IISserviceName >*を再起動する IIS サービスの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="aff4d-154">Where *\<IISserviceName>* is the name of the IIS service you want to restart.</span></span> <span data-ttu-id="aff4d-155">各 IIS サービスに対してこのコマンドを繰り返し実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aff4d-155">You must repeat this command for each of the IIS services.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aff4d-156">参照</span><span class="sxs-lookup"><span data-stu-id="aff4d-156">See Also</span></span>  
 <span data-ttu-id="aff4d-157">[アーカイブおよび BizTalk 追跡データベースの削除](../core/archiving-and-purging-the-biztalk-tracking-database.md) </span><span class="sxs-lookup"><span data-stu-id="aff4d-157">[Archiving and Purging the BizTalk Tracking Database](../core/archiving-and-purging-the-biztalk-tracking-database.md) </span></span>  
 <span data-ttu-id="aff4d-158">[バックアップおよび BizTalk Server データベースを復元します。](../core/backing-up-and-restoring-biztalk-server-databases.md) </span><span class="sxs-lookup"><span data-stu-id="aff4d-158">[Backing Up and Restoring BizTalk Server Databases](../core/backing-up-and-restoring-biztalk-server-databases.md) </span></span>  
 [<span data-ttu-id="aff4d-159">開始、停止、一時停止、再開、または BizTalk Server サービスを再開する方法</span><span class="sxs-lookup"><span data-stu-id="aff4d-159">How to Start, Stop, Pause, Resume, or Restart BizTalk Server Services</span></span>](../core/how-to-start-stop-pause-resume-or-restart-biztalk-server-services.md)