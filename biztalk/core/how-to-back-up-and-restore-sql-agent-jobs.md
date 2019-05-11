---
title: バックアップおよび SQL エージェント ジョブを復元する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f82fc5a5-5ea5-476c-bed1-c5d41a50e673
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ea39b09736904a6ba9ef7d19dc20e833b1d1f351
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65342487"
---
# <a name="how-to-back-up-and-restore-sql-agent-jobs"></a><span data-ttu-id="105b9-102">バックアップおよび SQL エージェント ジョブを復元する方法</span><span class="sxs-lookup"><span data-stu-id="105b9-102">How to Back Up and Restore SQL Agent Jobs</span></span>
<span data-ttu-id="105b9-103">このトピックでは、バックアップおよび SQL Server エージェント ジョブを復元する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="105b9-103">This topic describes how to back up and restore SQL Server Agent Jobs.</span></span> <span data-ttu-id="105b9-104">それらを構成した後は、SQL ジョブをバックアップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="105b9-104">You should back up your SQL jobs after you configure them.</span></span>  
  
## <a name="biztalk-server-jobs"></a><span data-ttu-id="105b9-105">BizTalk Server ジョブ</span><span class="sxs-lookup"><span data-stu-id="105b9-105">BizTalk Server Jobs</span></span>  
 <span data-ttu-id="105b9-106">次の SQL Server エージェント ジョブは、BizTalk Server に関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="105b9-106">The following SQL Server Agent jobs are associated with BizTalk Server.</span></span> <span data-ttu-id="105b9-107">各サーバーにインストールされているジョブは、どの機能がインストールされ、構成によって異なります。</span><span class="sxs-lookup"><span data-stu-id="105b9-107">The jobs installed on each server are different depending on which features are installed and configured.</span></span> <span data-ttu-id="105b9-108">これらのジョブのほとんどは、BizTalk Server のセットアップ中に作成されます。</span><span class="sxs-lookup"><span data-stu-id="105b9-108">Most of these jobs are created during BizTalk Server setup.</span></span> <span data-ttu-id="105b9-109">ログ配布を構成するときにいくつか作成されます。</span><span class="sxs-lookup"><span data-stu-id="105b9-109">Several are created when configuring log shipping.</span></span>  
  
-   <span data-ttu-id="105b9-110">BizTalk Server (BizTalkMgmtDb) のバックアップします。</span><span class="sxs-lookup"><span data-stu-id="105b9-110">Backup BizTalk Server (BizTalkMgmtDb)</span></span>  
  
-   <span data-ttu-id="105b9-111">CleanupBTFExpiredEntriesJob_BizTalkMgmtDb</span><span class="sxs-lookup"><span data-stu-id="105b9-111">CleanupBTFExpiredEntriesJob_BizTalkMgmtDb</span></span>  
  
-   <span data-ttu-id="105b9-112">DTA Purge and Archive (BizTalkDTADb)</span><span class="sxs-lookup"><span data-stu-id="105b9-112">DTA Purge and Archive (BizTalkDTADb)</span></span>  
  
-   <span data-ttu-id="105b9-113">MessageBox_DeadProcesses_Cleanup_BizTalkMsgBoxDb</span><span class="sxs-lookup"><span data-stu-id="105b9-113">MessageBox_DeadProcesses_Cleanup_BizTalkMsgBoxDb</span></span>  
  
-   <span data-ttu-id="105b9-114">MessageBox_Message_Cleanup_BizTalkMsgBoxDb</span><span class="sxs-lookup"><span data-stu-id="105b9-114">MessageBox_Message_Cleanup_BizTalkMsgBoxDb</span></span>  
  
-   <span data-ttu-id="105b9-115">MessageBox_Message_ManageRefCountLog_BizTalkMsgBoxDb</span><span class="sxs-lookup"><span data-stu-id="105b9-115">MessageBox_Message_ManageRefCountLog_BizTalkMsgBoxDb</span></span>  
  
-   <span data-ttu-id="105b9-116">MessageBox_Parts_Cleanup_BizTalkMsgBoxDb</span><span class="sxs-lookup"><span data-stu-id="105b9-116">MessageBox_Parts_Cleanup_BizTalkMsgBoxDb</span></span>  
  
-   <span data-ttu-id="105b9-117">MessageBox_UpdateStats_BizTalkMsgBoxDb</span><span class="sxs-lookup"><span data-stu-id="105b9-117">MessageBox_UpdateStats_BizTalkMsgBoxDb</span></span>  
  
-   <span data-ttu-id="105b9-118">Operations_OperateOnInstances_OnMaster_BizTalkMsgBoxDb</span><span class="sxs-lookup"><span data-stu-id="105b9-118">Operations_OperateOnInstances_OnMaster_BizTalkMsgBoxDb</span></span>  
  
-   <span data-ttu-id="105b9-119">PurgeSubscriptionsJob_BizTalkMsgBoxDb</span><span class="sxs-lookup"><span data-stu-id="105b9-119">PurgeSubscriptionsJob_BizTalkMsgBoxDb</span></span>  
  
-   <span data-ttu-id="105b9-120">Rules_Database_Cleanup_BizTalkRuleEngineDb</span><span class="sxs-lookup"><span data-stu-id="105b9-120">Rules_Database_Cleanup_BizTalkRuleEngineDb</span></span>  
  
-   <span data-ttu-id="105b9-121">TrackedMessages_Copy_BizTalkMsgBoxDb</span><span class="sxs-lookup"><span data-stu-id="105b9-121">TrackedMessages_Copy_BizTalkMsgBoxDb</span></span>  
  
-   <span data-ttu-id="105b9-122">BTS ログの配布のバックアップ履歴の取得</span><span class="sxs-lookup"><span data-stu-id="105b9-122">BTS Log Shipping Get Backup History</span></span>  
  
-   <span data-ttu-id="105b9-123">BTS ログの配布の復元データベース</span><span class="sxs-lookup"><span data-stu-id="105b9-123">BTS Log Shipping Restore Database</span></span>  
  
-   <span data-ttu-id="105b9-124">BTS ログのマークまで復元の配布</span><span class="sxs-lookup"><span data-stu-id="105b9-124">BTS Log Shipping Restore To Mark</span></span>  
  
## <a name="back-up-a-job-using-a-script"></a><span data-ttu-id="105b9-125">スクリプトを使用してジョブをバックアップします。</span><span class="sxs-lookup"><span data-stu-id="105b9-125">Back up a job using a script</span></span>  
  
1.  <span data-ttu-id="105b9-126">**SQL Server Management Studio** を開きます。</span><span class="sxs-lookup"><span data-stu-id="105b9-126">Open **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="105b9-127">展開**SQL Server エージェント**、展開と**ジョブ**します。</span><span class="sxs-lookup"><span data-stu-id="105b9-127">Expand **SQL Server Agent**, and expand **Jobs**.</span></span>  
  
3.  <span data-ttu-id="105b9-128">バックアップ スクリプトを作成し、選択するジョブを右クリックして**ジョブをスクリプト化**します。</span><span class="sxs-lookup"><span data-stu-id="105b9-128">Right-click the job you want to create a backup script for, and then select **Script Job as**.</span></span>  
  
4.  <span data-ttu-id="105b9-129">選択**Create**または**Drop**を選択し、**新しいクエリ エディター ウィンドウ**、**ファイル**、または**クリップボード**スクリプトの宛先を選択します。</span><span class="sxs-lookup"><span data-stu-id="105b9-129">Select **CREATE To** or **DROP To**, then select **New Query Editor Window**, **File**, or **Clipboard** to select a destination for the script.</span></span> <span data-ttu-id="105b9-130">コピー先のファイルは、通常、 **.sql**拡張機能。</span><span class="sxs-lookup"><span data-stu-id="105b9-130">Typically, the destination is a file with a **.sql** extension.</span></span>  
  
5.  <span data-ttu-id="105b9-131">各ジョブのスクリプトを作成するには、手順 3. からこの手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="105b9-131">Repeat this procedure from Step 3 for each job you want to script.</span></span> <span data-ttu-id="105b9-132">一覧を参照してください。 BizTalk Server に関連するどのジョブを確認するジョブをスクリプトする必要があります。</span><span class="sxs-lookup"><span data-stu-id="105b9-132">Refer to the list of BizTalk Server related jobs to determine which jobs you need to script.</span></span>  
  
     <span data-ttu-id="105b9-133">少なくともをバックアップする必要があります、 **BizTalk Server のバックアップ (BizTalkMgmtDb)** ジョブの構成が完了後します。</span><span class="sxs-lookup"><span data-stu-id="105b9-133">At a minimum, you should back up the **Backup BizTalk Server (BizTalkMgmtDb)** job after it is configured.</span></span>  
  
## <a name="restore-a-job-from-a-script"></a><span data-ttu-id="105b9-134">スクリプトからジョブを復元します。</span><span class="sxs-lookup"><span data-stu-id="105b9-134">Restore a job from a script</span></span>  
  
1.  <span data-ttu-id="105b9-135">**SQL Server Management Studio** を開きます。</span><span class="sxs-lookup"><span data-stu-id="105b9-135">Open **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="105b9-136">**ファイル**] メニューの [**オープン**スクリプト化されたジョブを含むファイル。</span><span class="sxs-lookup"><span data-stu-id="105b9-136">On the **File** menu, **Open** the file containing the scripted job.</span></span>  
  
3.  <span data-ttu-id="105b9-137">ジョブを作成するスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="105b9-137">Execute the script to create the job.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="105b9-138">次の手順</span><span class="sxs-lookup"><span data-stu-id="105b9-138">Next Steps</span></span>  
 [<span data-ttu-id="105b9-139">バックアップおよび SQL Server ログインを復元する方法</span><span class="sxs-lookup"><span data-stu-id="105b9-139">How to Back Up and Restore SQL Server Logins</span></span>](../core/how-to-back-up-and-restore-sql-server-logins.md)