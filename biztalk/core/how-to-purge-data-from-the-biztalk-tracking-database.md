---
title: "BizTalk 追跡データベースからデータを削除する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Tracking database, purging
- purging
- DTA Purge and Archive job, purging data
- purging, DTA Purge and Archive job
ms.assetid: cdf12866-442d-4c1f-b10f-ebf8d665d521
caps.latest.revision: "27"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 01c56629aaa0934010ba79637b4e4a134bf29f26
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-purge-data-from-the-biztalk-tracking-database"></a><span data-ttu-id="ccf22-102">BizTalk 追跡データベースからデータを削除する方法</span><span class="sxs-lookup"><span data-stu-id="ccf22-102">How to Purge Data from the BizTalk Tracking Database</span></span>
<span data-ttu-id="ccf22-103">BizTalk 追跡 (BizTalkDTADb) データベースからデータを削除すると、DTA Purge and Archive ジョブにより、メッセージおよびサービス インスタンスの情報、オーケストレーション イベントの情報、ルール エンジン追跡データなど、さまざまな種類の追跡情報が BizTalk 追跡 (BizTalkDTADb) データベースから削除されます。</span><span class="sxs-lookup"><span data-stu-id="ccf22-103">When you purge data from the BizTalk Tracking (BizTalkDTADb) database, the DTA Purge and Archive job purges different types of tracking information such as message and service instance information, orchestration event information, and rules engine tracking data from the BizTalk Tracking (BizTalkDTADb) database.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ccf22-104">BizTalk 追跡 (BizTalkDTADb) データベースは、この手順を使用してもアーカイブされません。</span><span class="sxs-lookup"><span data-stu-id="ccf22-104">The BizTalk Tracking (BizTalkDTADb) database is not archived using this procedure.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="ccf22-105">追跡が有効になっていない状態で例外がキャッチされてオーケストレーションで処理されると、開始状態の孤立した追跡インスタンスおよび例外情報が、BizTalk 追跡 (BizTalkDTADb) データベースに挿入される場合があります。</span><span class="sxs-lookup"><span data-stu-id="ccf22-105">If an exception is caught and handled in an orchestration without tracking turned on, an orphaned tracking instance with a Started state and exception information may be inserted into the BizTalk Tracking (BizTalkDTADb) database.</span></span> <span data-ttu-id="ccf22-106">このレコードは、データベースを削除した後も残ります。</span><span class="sxs-lookup"><span data-stu-id="ccf22-106">This record will remain after purging the database.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="ccf22-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="ccf22-107">Prerequisites</span></span>  
 <span data-ttu-id="ccf22-108">この手順を実行するには、SQL Server sysadmin 固定サーバーの役割のメンバーであるアカウントを使用してログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ccf22-108">You must be logged on with an account that is a member of the SQL Server sysadmin fixed server role to perform this procedure.</span></span>  
  
### <a name="to-purge-data-from-the-biztalk-tracking-database"></a><span data-ttu-id="ccf22-109">BizTalk 追跡データベースからデータを削除するには</span><span class="sxs-lookup"><span data-stu-id="ccf22-109">To purge data from the BizTalk Tracking database</span></span>  
  
1.  <span data-ttu-id="ccf22-110">をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして**Microsoft SQL Server 2008 SP2**、順にクリック**SQL Server Management Studio**です。</span><span class="sxs-lookup"><span data-stu-id="ccf22-110">Click **Start**, click **All Programs**, click **Microsoft SQL Server 2008 SP2**, and then click **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="ccf22-111">**サーバーへの接続**ダイアログ ボックスでは、BizTalk 追跡 (BizTalkDTADb) データベースが存在する SQL Server および適切な認証の種類の名前を指定し、をクリックして**接続**にSQL Server に接続します。</span><span class="sxs-lookup"><span data-stu-id="ccf22-111">In the **Connect to Server** dialog box, specify the name of the SQL Server where the BizTalk Tracking (BizTalkDTADb) database resides and the appropriate authentication type, and then click **Connect** to connect to the SQL Server.</span></span>  
  
3.  <span data-ttu-id="ccf22-112">**Microsoft SQL Server Management Studio**をダブルクリックして**SQL Server エージェント**、クリックして**ジョブ**です。</span><span class="sxs-lookup"><span data-stu-id="ccf22-112">In **Microsoft SQL Server Management Studio**, double-click **SQL Server Agent**, and then click **Jobs**.</span></span>  
  
4.  <span data-ttu-id="ccf22-113">**オブジェクト エクスプ ローラーの詳細** ウィンドウを右クリックして**DTA Purge and Archive (BizTalkDTADb)**、クリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="ccf22-113">In the **Object Explorer Details** pane, right-click **DTA Purge and Archive (BizTalkDTADb)**, and then click **Properties**.</span></span>  
  
5.  <span data-ttu-id="ccf22-114">**ジョブのプロパティ - DTA Purge and Archive (BizTalkDTADb)**ダイアログ ボックスで、**ページの選択**をクリックして**手順**です。</span><span class="sxs-lookup"><span data-stu-id="ccf22-114">In the **Job Properties - DTA Purge and Archive (BizTalkDTADb)** dialog box, under **Select a page**, click **Steps**.</span></span>  
  
6.  <span data-ttu-id="ccf22-115">**ジョブ ステップの一覧**、 をクリックして**、アーカイブし、削除**、クリックして**編集**です。</span><span class="sxs-lookup"><span data-stu-id="ccf22-115">In the **Job step list**, click **Archive and Purge**, and then click **Edit**.</span></span>  
  
7.  <span data-ttu-id="ccf22-116">**ジョブ ステップのプロパティ - Archive and Purge**  ダイアログ ボックスで、**全般** ページの 、**コマンド**ボックスで、変更**exec dtasp_BackupAndPurgeTrackingDatabase**に**exec dtasp_PurgeTrackingDatabase**です。</span><span class="sxs-lookup"><span data-stu-id="ccf22-116">In the **Job Step Properties - Archive and Purge** dialog box, on the **General** page, in the **Command** box, change **exec dtasp_BackupAndPurgeTrackingDatabase** to **exec dtasp_PurgeTrackingDatabase**.</span></span>  
  
    > [!CAUTION]
    >  <span data-ttu-id="ccf22-117">**Exec dtasp_PurgeTrackingDatabase**ストアド プロシージャでは、BizTalk 追跡 (BizTalkDTADb) データベースはアーカイブされません。</span><span class="sxs-lookup"><span data-stu-id="ccf22-117">The **exec dtasp_PurgeTrackingDatabase** stored procedure does not archive the BizTalk Tracking (BizTalkDTADb) database.</span></span> <span data-ttu-id="ccf22-118">このオプションを使用する前に、アーカイブ済みの追跡データが不要であることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="ccf22-118">Before using this option, be certain that you no longer require archived tracking data.</span></span>  
  
8.  <span data-ttu-id="ccf22-119">**コマンド**ボックスで、必要に応じて、次のパラメーターを編集し、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="ccf22-119">In the **Command** box, edit the following parameters as appropriate, and then click **OK**.</span></span>  
  
    -   <span data-ttu-id="ccf22-120">@nHourstinyint — (live 時間) よりも古いインスタンスに完了した + (live 日) は、関連付けられているすべてのデータと共に削除されます。</span><span class="sxs-lookup"><span data-stu-id="ccf22-120">@nHours tinyint — Any completed instance older than (live hours) + (live days) will be deleted along with all associated data.</span></span>  
  
    -   <span data-ttu-id="ccf22-121">@nDaystinyint — (live 時間) よりも古いインスタンスに完了した + (live 日) は、関連付けられているすべてのデータと共に削除されます。</span><span class="sxs-lookup"><span data-stu-id="ccf22-121">@nDays tinyint — Any completed instance older than (live hours) + (live days) will be deleted along with all associated data.</span></span> <span data-ttu-id="ccf22-122">既定の間隔は 1 日です。</span><span class="sxs-lookup"><span data-stu-id="ccf22-122">Default interval is 1 day.</span></span>  
  
    -   <span data-ttu-id="ccf22-123">@nHardDaystinyint — この日数より古いすべてのデータは、データが完全でない場合でも、削除されます。</span><span class="sxs-lookup"><span data-stu-id="ccf22-123">@nHardDays tinyint — All data older than this day will be deleted, even if the data is incomplete.</span></span> <span data-ttu-id="ccf22-124">HardDeleteDays に指定する間隔は、データの有効期間よりも大きい値にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ccf22-124">The time interval specified for HardDeleteDays should be greater than the live window of data.</span></span> <span data-ttu-id="ccf22-125">データの有効期間は、BizTalk 追跡データベース (BizTalkDTADb) でデータを追跡する間隔になります。</span><span class="sxs-lookup"><span data-stu-id="ccf22-125">The live window of data is the interval of time for which you want to maintain tracking data in the BizTalk Tracking (BizTalkDTADb) database.</span></span> <span data-ttu-id="ccf22-126">この間隔より古いデータは、次のアーカイブ時にアーカイブしてから削除できます。</span><span class="sxs-lookup"><span data-stu-id="ccf22-126">Anything older than this interval is eligible to be archived at the next archive and then purged.</span></span>  
  
    -   <span data-ttu-id="ccf22-127">@dtLastBackup-これを設定して**GetUTCDate()**を BizTalk 追跡 (BizTalkDTADb) データベースからデータを消去します。</span><span class="sxs-lookup"><span data-stu-id="ccf22-127">@dtLastBackup — Set this to **GetUTCDate()** to purge data from the BizTalk Tracking (BizTalkDTADb) database.</span></span> <span data-ttu-id="ccf22-128">設定すると**NULL**データは、データベースから削除されません。</span><span class="sxs-lookup"><span data-stu-id="ccf22-128">When set to **NULL**, data is not purged from the database.</span></span>  
  
     <span data-ttu-id="ccf22-129">編集したスクリプトは、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="ccf22-129">Your edited script should look similar to this:</span></span>  
  
    ```  
    declare @dtLastBackup datetime set @dtLastBackup = GetUTCDate() exec dtasp_PurgeTrackingDatabase 1, 0, 1, @dtLastBackup  
    ```  
  
9. <span data-ttu-id="ccf22-130">**ジョブのプロパティ - DTA Purge and Archive (BizTalkDTADb)**ダイアログ ボックスで、**ページの選択**、 をクリックして**全般**を選択、**有効**チェック ボックスをクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="ccf22-130">On the **Job Properties - DTA Purge and Archive (BizTalkDTADb)** dialog box, under **Select a page**, click **General**, select the **Enabled** check box, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ccf22-131">参照</span><span class="sxs-lookup"><span data-stu-id="ccf22-131">See Also</span></span>  
 [<span data-ttu-id="ccf22-132">BizTalk 追跡データベースのアーカイブおよび削除</span><span class="sxs-lookup"><span data-stu-id="ccf22-132">Archiving and Purging the BizTalk Tracking Database</span></span>](../core/archiving-and-purging-the-biztalk-tracking-database.md)