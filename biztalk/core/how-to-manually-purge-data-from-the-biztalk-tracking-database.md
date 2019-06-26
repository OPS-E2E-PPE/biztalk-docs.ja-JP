---
title: BizTalk 追跡データベースからデータを手動で削除する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Tracking database, purging
- purging, manually
- purging, warnings
ms.assetid: f350d850-5034-4166-940c-8d10b7b445fb
caps.latest.revision: 22
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e4e4366edf0187ee74391ea144b67878fb51999a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65336685"
---
# <a name="how-to-manually-purge-data-from-the-biztalk-tracking-database"></a><span data-ttu-id="96df5-102">BizTalk 追跡データベースからデータを手動で削除する方法</span><span class="sxs-lookup"><span data-stu-id="96df5-102">How to Manually Purge Data from the BizTalk Tracking Database</span></span>
<span data-ttu-id="96df5-103">DTA Archive and Purge SQL Server エージェント ジョブには、格納された追跡データの圧縮、データベースの連続的な削除のための BizTalk 追跡 (BizTalkDTADb) データベースからデータを手動で削除する必要があます。</span><span class="sxs-lookup"><span data-stu-id="96df5-103">The DTA Archive and Purge SQL Server Agent job reduces the need to manually purge data from the BizTalk Tracking (BizTalkDTADb) database due to continuous purging of the database and compaction of stored tracking data.</span></span> <span data-ttu-id="96df5-104">BizTalk 追跡 (BizTalkDTADb) データベースには、その程度のパフォーマンスが低下が大きくなった場合にデータが発生している削除と、DTA Archive は手動でする必要があり、Purge ジョブで、データベースの成長続けることができます。</span><span class="sxs-lookup"><span data-stu-id="96df5-104">You might need to manually purge data if your BizTalk Tracking (BizTalkDTADb) database has grown so much that sustained performance degradation is occurring and the DTA Archive and Purge job is unable to keep up with the database growth.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="96df5-105">この手順を実行すると、完成したインスタンスのすべての追跡データが完了時間に関係なく、BizTalk 追跡 (BizTalkDTADb) データベースから削除します。</span><span class="sxs-lookup"><span data-stu-id="96df5-105">Performing this procedure deletes all tracking data for completed instances from the BizTalk Tracking (BizTalkDTADb) database regardless of completion time.</span></span> <span data-ttu-id="96df5-106">この手順を実行する前に、他の個別に BizTalk 追跡 (BizTalkDTADb) データベースをアーカイブする必要があります[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース。</span><span class="sxs-lookup"><span data-stu-id="96df5-106">Before performing this procedure, you should archive the BizTalk Tracking (BizTalkDTADb) database separately from the other [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="96df5-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="96df5-107">Prerequisites</span></span>  
 <span data-ttu-id="96df5-108">この手順を実行するには、SQL Server sysadmin 固定サーバーの役割のメンバーであるアカウントを使用してログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="96df5-108">You must be logged on with an account that is a member of the SQL Server sysadmin fixed server role to perform this procedure.</span></span>  
  
### <a name="to-manually-purge-data-from-the-biztalk-tracking-database"></a><span data-ttu-id="96df5-109">BizTalk 追跡データベースからデータを手動で削除するには</span><span class="sxs-lookup"><span data-stu-id="96df5-109">To manually purge data from the BizTalk Tracking database</span></span>  
  
1. <span data-ttu-id="96df5-110">BizTalk Server データベースをバックアップします。</span><span class="sxs-lookup"><span data-stu-id="96df5-110">Backup your BizTalk Server databases.</span></span>  
  
2. <span data-ttu-id="96df5-111">BizTalk 追跡 (BizTalkDTADb) データベースをアーカイブします。</span><span class="sxs-lookup"><span data-stu-id="96df5-111">Archive the BizTalk Tracking (BizTalkDTADb) database.</span></span>  
  
3. <span data-ttu-id="96df5-112">サービス コンソールを開きます。</span><span class="sxs-lookup"><span data-stu-id="96df5-112">Open the Services console.</span></span> <span data-ttu-id="96df5-113">をクリックして**開始**、 をクリックして**実行**、し、入力**services.msc**です。</span><span class="sxs-lookup"><span data-stu-id="96df5-113">Click **Start**, click **Run**, and then type **services.msc**.</span></span> <span data-ttu-id="96df5-114">場合、**ユーザー アカウント制御**ダイアログが表示されたら、クリックして**続行**します。</span><span class="sxs-lookup"><span data-stu-id="96df5-114">If a **User Account Control** dialog is displayed, click **Continue**.</span></span>  
  
4. <span data-ttu-id="96df5-115">サービス コンソールが表示されたらを検索して、次のサービスそれぞれを停止します。</span><span class="sxs-lookup"><span data-stu-id="96df5-115">When the Services console appears, locate and then stop each of the following services.</span></span> <span data-ttu-id="96df5-116">サービスを停止するには、サービス行を右クリックして、**サービス**ペイン、およびクリック**停止**します。</span><span class="sxs-lookup"><span data-stu-id="96df5-116">To stop a service, right-click the service row in the **Services** pane, and then click **Stop**.</span></span>  
  
   -   <span data-ttu-id="96df5-117">ときに BizTalkServiceBizTalkGroup:BizTalkServerApplication</span><span class="sxs-lookup"><span data-stu-id="96df5-117">BizTalkServiceBizTalkGroup : BizTalkServerApplication</span></span>  
  
   -   <span data-ttu-id="96df5-118">エンタープライズ シングル サインオン サービス</span><span class="sxs-lookup"><span data-stu-id="96df5-118">Enterprise Single Sign-On Service</span></span>  
  
        <span data-ttu-id="96df5-119">場合、ときに BizTalkServiceBizTalkGroup:[Biztalkserverapplication] サービスが実行されている、エンタープライズ シングル サインオン サービスをシャット ダウンしようとすると、**その他のサービスの停止**ダイアログが表示されます。</span><span class="sxs-lookup"><span data-stu-id="96df5-119">If the BizTalkServiceBizTalkGroup : BizTalkServerApplication service is running when you try to shut down the Enterprise Singe Sign-On Service, a **Stop Other Services** dialog will be displayed.</span></span> <span data-ttu-id="96df5-120">**[はい]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="96df5-120">Click **Yes**.</span></span>  
  
   -   <span data-ttu-id="96df5-121">ルール エンジン更新サービス</span><span class="sxs-lookup"><span data-stu-id="96df5-121">Rule Engine Update Service</span></span>  
  
5. <span data-ttu-id="96df5-122">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="96df5-122">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span> <span data-ttu-id="96df5-123">場合、**ユーザー アカウント制御**ダイアログが表示されたら、示されているアクションが、クリックしてであることを確認**続行**します。</span><span class="sxs-lookup"><span data-stu-id="96df5-123">If a **User Account Control** dialog is displayed, verify that the action described is what you want, and then click **Continue**.</span></span>  
  
6. <span data-ttu-id="96df5-124">**BizTalk Server 管理コンソール**ウィンドウの左側にある エクスプ ローラー ペインで、ダブルクリック**BizTalk グループ**を下の一覧を展開するをダブルクリックし、**プラットフォーム設定**、 をクリックし、**ホスト インスタンス**します。</span><span class="sxs-lookup"><span data-stu-id="96df5-124">In the **BizTalk Server Administration Console** in the explorer pane on the left side of the window, double-click **BizTalk Group** to expand the list below it, then double-click **Platform Settings**, and then click **Host Instances**.</span></span> <span data-ttu-id="96df5-125">これは、ホスト インスタンスの一覧が表示されます (、**ホスト インスタンス**ウィンドウ) に関連するプロパティは、画面の右側にあるとします。</span><span class="sxs-lookup"><span data-stu-id="96df5-125">This will display a list of host instances (the **Host Instances** pane) and related properties, on the right side of the screen.</span></span>  
  
7. <span data-ttu-id="96df5-126">**ホスト インスタンス**ウィンドウが各実行中のホスト インスタンスを右クリックし、をクリックし、**停止**します。</span><span class="sxs-lookup"><span data-stu-id="96df5-126">In the **Host Instances** pane, right-click each running host instance, and then click **Stop**.</span></span>  
  
8. <span data-ttu-id="96df5-127">をクリックして**開始**に移動して、**実行**、型**cmd**、順にクリックします**OK**。</span><span class="sxs-lookup"><span data-stu-id="96df5-127">Click **Start**, go to **Run**, type **cmd**, and then click **OK**.</span></span>  
  
9. <span data-ttu-id="96df5-128">コマンド プロンプトで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="96df5-128">At the command prompt, type:</span></span>  
  
     <span data-ttu-id="96df5-129">**net stop iisadmin/y**</span><span class="sxs-lookup"><span data-stu-id="96df5-129">**net stop iisadmin /y**</span></span>  
  
     <span data-ttu-id="96df5-130">これにより、IIS 管理サービスと、すべての依存サービスを 1 つずつ停止し、新しいデータがデータが削除されるときに、BizTalkDTADb に書き込まれることを防ぎます。</span><span class="sxs-lookup"><span data-stu-id="96df5-130">This stops the IIS Admin Service and all dependent services, one-by-one and prevents new data from being written to the BizTalkDTADb while data is being purged.</span></span> <span data-ttu-id="96df5-131">各 1 つが停止しているように、サービスの一覧を書き留めます。</span><span class="sxs-lookup"><span data-stu-id="96df5-131">Write down the list of services as each one is stopped.</span></span> <span data-ttu-id="96df5-132">IIS を再起動するときに、この後でサービスの一覧を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="96df5-132">You will need to use this list of services later when you restart IIS.</span></span>  
  
     <span data-ttu-id="96df5-133">(コンピューターに表示される依存サービスが異なる場合があります)、このコマンドを発行後に表示される出力の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="96df5-133">Below is an example of the output you will see after issuing this command (the dependent services listed on your computer may vary):</span></span>  
  
    ```  
    The following services are dependent on the IIS Admin Service service. Stopping the IIS Admin Service service will also stop these services.  
    World Wide Web Publishing Service  
    HTTP SSL  
    ```  
  
10. <span data-ttu-id="96df5-134">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして**Microsoft SQL Server 2008 SP2**、順にクリックします**SQL Server Management Studio**します。</span><span class="sxs-lookup"><span data-stu-id="96df5-134">Click **Start**, click **All Programs**, click **Microsoft SQL Server 2008 SP2**, and then click **SQL Server Management Studio**.</span></span>  
  
11. <span data-ttu-id="96df5-135">**サーバーへの接続**ダイアログ ボックスで、SQL Server が BizTalk 追跡 (BizTalkDTADb) データベースが存在し、適切な認証の種類の名前を指定し、順にクリックします**Connect**に適切な SQL Server に接続します。</span><span class="sxs-lookup"><span data-stu-id="96df5-135">In the **Connect to Server** dialog box, specify the name of the SQL Server where the BizTalk Tracking (BizTalkDTADb) database resides and the appropriate authentication type, and then click **Connect** to connect to the appropriate SQL Server.</span></span>  
  
12. <span data-ttu-id="96df5-136">**Microsoft SQL Server Management Studio**、ダブルクリック**データベース**、ダブルクリック、 **BizTalkDTADb**データベースをダブルクリックします**プログラミング**、 をクリックし、 **Stored Procedures**します。</span><span class="sxs-lookup"><span data-stu-id="96df5-136">In **Microsoft SQL Server Management Studio**, double-click **Databases**, double-click the **BizTalkDTADb** database, double-click **Programmability**, and then click **Stored Procedures**.</span></span>  
  
13. <span data-ttu-id="96df5-137">**オブジェクト エクスプ ローラーの詳細**ウィンドウで、右クリックして **[dtasp_purgeallcompletedtrackingdata]** 、順にクリックします**ストアド プロシージャの実行**します。</span><span class="sxs-lookup"><span data-stu-id="96df5-137">In the **Object Explorer Details** pane, right-click **dtasp_PurgeAllCompletedTrackingData**, and then click **Execute Stored Procedure**.</span></span>  
  
14. <span data-ttu-id="96df5-138">**プロシージャの実行**ダイアログ ボックスで、をクリックして**OK**します。</span><span class="sxs-lookup"><span data-stu-id="96df5-138">In the **Execute Procedure** dialog box, click **OK**.</span></span>  
  
     <span data-ttu-id="96df5-139">このストアド プロシージャは、完了時刻に関係なく完了したインスタンスに関連付けられているすべての追跡データを削除します。</span><span class="sxs-lookup"><span data-stu-id="96df5-139">This stored procedure deletes all tracking data associated with completed instances regardless of their completion time.</span></span>  
  
15. <span data-ttu-id="96df5-140">[サービス] を開きます。</span><span class="sxs-lookup"><span data-stu-id="96df5-140">Open Services.</span></span> <span data-ttu-id="96df5-141">をクリックして**開始**、 をクリックして**実行**、し、入力**services.msc**です。</span><span class="sxs-lookup"><span data-stu-id="96df5-141">Click **Start**, click **Run**, and then type **services.msc**.</span></span> <span data-ttu-id="96df5-142">場合、**ユーザー アカウント制御**ダイアログが表示されたら、示されているアクションが、クリックしてであることを確認**続行**します。</span><span class="sxs-lookup"><span data-stu-id="96df5-142">If a **User Account Control** dialog is displayed, verify that the action described is what you want, and then click **Continue**.</span></span>  
  
16. <span data-ttu-id="96df5-143">次のサービスのそれぞれを右クリックし をクリックし、**開始**:</span><span class="sxs-lookup"><span data-stu-id="96df5-143">Right-click each of the following services, and then click **Start**:</span></span>  
  
    -   <span data-ttu-id="96df5-144">ときに BizTalkServiceBizTalkGroup:BizTalkServerApplication</span><span class="sxs-lookup"><span data-stu-id="96df5-144">BizTalkServiceBizTalkGroup : BizTalkServerApplication</span></span>  
  
    -   <span data-ttu-id="96df5-145">エンタープライズ シングル サインオン サービス</span><span class="sxs-lookup"><span data-stu-id="96df5-145">Enterprise Single Sign-On Service</span></span>  
  
    -   <span data-ttu-id="96df5-146">ルール エンジン更新サービス</span><span class="sxs-lookup"><span data-stu-id="96df5-146">Rule Engine Update Service</span></span>  
  
17. <span data-ttu-id="96df5-147">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="96df5-147">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
18. <span data-ttu-id="96df5-148">**BizTalk Server 管理コンソール**をダブルクリック、 **BizTalk グループ**、ダブルクリックして**プラットフォームの設定**、順にクリックします**ホストインスタンス**します。</span><span class="sxs-lookup"><span data-stu-id="96df5-148">In the **BizTalk Server Administration Console**, double-click the **BizTalk Group**, double-click **Platform Settings**, and then click **Host Instances**.</span></span>  
  
19. <span data-ttu-id="96df5-149">**オブジェクト エクスプ ローラーの詳細**ウィンドウが各停止しているホスト インスタンスを右クリックし、クリックして**開始**します。</span><span class="sxs-lookup"><span data-stu-id="96df5-149">In the **Object Explorer Details** pane, right-click each stopped host instance, and then click **Start**.</span></span>  
  
20. <span data-ttu-id="96df5-150">上記の手順 8. の説明に従って、コマンド プロンプトを起動します。</span><span class="sxs-lookup"><span data-stu-id="96df5-150">Start a command prompt, as described in step 8 above.</span></span>  
  
21. <span data-ttu-id="96df5-151">コマンド プロンプトでは、手順 4. で、各 IIS サービスを停止するを再起動します。</span><span class="sxs-lookup"><span data-stu-id="96df5-151">At the command prompt, restart each of the IIS services that you stopped in step 4.</span></span> <span data-ttu-id="96df5-152">型:</span><span class="sxs-lookup"><span data-stu-id="96df5-152">Type:</span></span>  
  
     <span data-ttu-id="96df5-153">**net start**  *\<IISserviceName\>*</span><span class="sxs-lookup"><span data-stu-id="96df5-153">**net start** *\<IISserviceName\>*</span></span>  
  
     <span data-ttu-id="96df5-154">場所 *\<IISserviceName\>* 再起動する IIS サービスの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="96df5-154">Where *\<IISserviceName\>* is the name of the IIS service you want to restart.</span></span> <span data-ttu-id="96df5-155">各 IIS サービスは、このコマンドを繰り返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="96df5-155">You must repeat this command for each of the IIS services.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96df5-156">参照</span><span class="sxs-lookup"><span data-stu-id="96df5-156">See Also</span></span>  
 <span data-ttu-id="96df5-157">[アーカイブおよび BizTalk 追跡データベースの削除](../core/archiving-and-purging-the-biztalk-tracking-database.md) </span><span class="sxs-lookup"><span data-stu-id="96df5-157">[Archiving and Purging the BizTalk Tracking Database](../core/archiving-and-purging-the-biztalk-tracking-database.md) </span></span>  
 <span data-ttu-id="96df5-158">[バックアップおよび BizTalk Server データベースを復元します。](../core/backing-up-and-restoring-biztalk-server-databases.md) </span><span class="sxs-lookup"><span data-stu-id="96df5-158">[Backing Up and Restoring BizTalk Server Databases](../core/backing-up-and-restoring-biztalk-server-databases.md) </span></span>  
 [<span data-ttu-id="96df5-159">開始、停止、一時停止、再開、または BizTalk Server サービスを再起動する方法</span><span class="sxs-lookup"><span data-stu-id="96df5-159">How to Start, Stop, Pause, Resume, or Restart BizTalk Server Services</span></span>](../core/how-to-start-stop-pause-resume-or-restart-biztalk-server-services.md)