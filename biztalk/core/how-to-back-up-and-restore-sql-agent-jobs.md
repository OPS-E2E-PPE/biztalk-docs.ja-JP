---
title: "バックアップおよび SQL エージェント ジョブを復元する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f82fc5a5-5ea5-476c-bed1-c5d41a50e673
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 253055f9a45dfdb9864d4d5202661e750d28b1b1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-back-up-and-restore-sql-agent-jobs"></a><span data-ttu-id="d1a53-102">SQL エージェント ジョブのバックアップ方法と復元方法</span><span class="sxs-lookup"><span data-stu-id="d1a53-102">How to Back Up and Restore SQL Agent Jobs</span></span>
<span data-ttu-id="d1a53-103">このトピックでは、SQL Server エージェント ジョブをバックアップおよび復元する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d1a53-103">This topic describes how to back up and restore SQL Server Agent Jobs.</span></span> <span data-ttu-id="d1a53-104">SQL ジョブを構成してからバックアップすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d1a53-104">You should back up your SQL jobs after you configure them.</span></span>  
  
## <a name="biztalk-server-jobs"></a><span data-ttu-id="d1a53-105">BizTalk Server のジョブ</span><span class="sxs-lookup"><span data-stu-id="d1a53-105">BizTalk Server Jobs</span></span>  
 <span data-ttu-id="d1a53-106">以下の SQL Server エージェント ジョブが BizTalk Server と関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="d1a53-106">The following SQL Server Agent jobs are associated with BizTalk Server.</span></span> <span data-ttu-id="d1a53-107">各サーバーにインストールされるジョブは、インストールされて構成されている機能によって異なります。</span><span class="sxs-lookup"><span data-stu-id="d1a53-107">The jobs installed on each server are different depending on which features are installed and configured.</span></span> <span data-ttu-id="d1a53-108">これらのジョブのほとんどは、BizTalk Server のセットアップ中に作成されます。</span><span class="sxs-lookup"><span data-stu-id="d1a53-108">Most of these jobs are created during BizTalk Server setup.</span></span> <span data-ttu-id="d1a53-109">ログ配布の構成を行う際に作成されるものもあります。</span><span class="sxs-lookup"><span data-stu-id="d1a53-109">Several are created when configuring log shipping.</span></span>  
  
-   <span data-ttu-id="d1a53-110">BizTalk Server のバックアップ (BizTalkMgmtDb)</span><span class="sxs-lookup"><span data-stu-id="d1a53-110">Backup BizTalk Server (BizTalkMgmtDb)</span></span>  
  
-   <span data-ttu-id="d1a53-111">CleanupBTFExpiredEntriesJob_BizTalkMgmtDb</span><span class="sxs-lookup"><span data-stu-id="d1a53-111">CleanupBTFExpiredEntriesJob_BizTalkMgmtDb</span></span>  
  
-   <span data-ttu-id="d1a53-112">DTA Purge and Archive (BizTalkDTADb)</span><span class="sxs-lookup"><span data-stu-id="d1a53-112">DTA Purge and Archive (BizTalkDTADb)</span></span>  
  
-   <span data-ttu-id="d1a53-113">MessageBox_DeadProcesses_Cleanup_BizTalkMsgBoxDb</span><span class="sxs-lookup"><span data-stu-id="d1a53-113">MessageBox_DeadProcesses_Cleanup_BizTalkMsgBoxDb</span></span>  
  
-   <span data-ttu-id="d1a53-114">MessageBox_Message_Cleanup_BizTalkMsgBoxDb</span><span class="sxs-lookup"><span data-stu-id="d1a53-114">MessageBox_Message_Cleanup_BizTalkMsgBoxDb</span></span>  
  
-   <span data-ttu-id="d1a53-115">MessageBox_Message_ManageRefCountLog_BizTalkMsgBoxDb</span><span class="sxs-lookup"><span data-stu-id="d1a53-115">MessageBox_Message_ManageRefCountLog_BizTalkMsgBoxDb</span></span>  
  
-   <span data-ttu-id="d1a53-116">MessageBox_Parts_Cleanup_BizTalkMsgBoxDb</span><span class="sxs-lookup"><span data-stu-id="d1a53-116">MessageBox_Parts_Cleanup_BizTalkMsgBoxDb</span></span>  
  
-   <span data-ttu-id="d1a53-117">MessageBox_UpdateStats_BizTalkMsgBoxDb</span><span class="sxs-lookup"><span data-stu-id="d1a53-117">MessageBox_UpdateStats_BizTalkMsgBoxDb</span></span>  
  
-   <span data-ttu-id="d1a53-118">Operations_OperateOnInstances_OnMaster_BizTalkMsgBoxDb</span><span class="sxs-lookup"><span data-stu-id="d1a53-118">Operations_OperateOnInstances_OnMaster_BizTalkMsgBoxDb</span></span>  
  
-   <span data-ttu-id="d1a53-119">PurgeSubscriptionsJob_BizTalkMsgBoxDb</span><span class="sxs-lookup"><span data-stu-id="d1a53-119">PurgeSubscriptionsJob_BizTalkMsgBoxDb</span></span>  
  
-   <span data-ttu-id="d1a53-120">Rules_Database_Cleanup_BizTalkRuleEngineDb</span><span class="sxs-lookup"><span data-stu-id="d1a53-120">Rules_Database_Cleanup_BizTalkRuleEngineDb</span></span>  
  
-   <span data-ttu-id="d1a53-121">TrackedMessages_Copy_BizTalkMsgBoxDb</span><span class="sxs-lookup"><span data-stu-id="d1a53-121">TrackedMessages_Copy_BizTalkMsgBoxDb</span></span>  
  
-   <span data-ttu-id="d1a53-122">BTS ログの配布 - バックアップ履歴の取得</span><span class="sxs-lookup"><span data-stu-id="d1a53-122">BTS Log Shipping Get Backup History</span></span>  
  
-   <span data-ttu-id="d1a53-123">BTS ログの配布 - データベースの復元</span><span class="sxs-lookup"><span data-stu-id="d1a53-123">BTS Log Shipping Restore Database</span></span>  
  
-   <span data-ttu-id="d1a53-124">BTS ログの配布 - マークまで復元</span><span class="sxs-lookup"><span data-stu-id="d1a53-124">BTS Log Shipping Restore To Mark</span></span>  
  
## <a name="back-up-a-job-using-a-script"></a><span data-ttu-id="d1a53-125">スクリプトを使用してジョブをバックアップします。</span><span class="sxs-lookup"><span data-stu-id="d1a53-125">Back up a job using a script</span></span>  
  
1.  <span data-ttu-id="d1a53-126">開いている**SQL Server Management Studio**です。</span><span class="sxs-lookup"><span data-stu-id="d1a53-126">Open **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="d1a53-127">**[SQL Server エージェント]** を展開し、**[ジョブ]** を展開します。</span><span class="sxs-lookup"><span data-stu-id="d1a53-127">Expand **SQL Server Agent**, and expand **Jobs**.</span></span>  
  
3.  <span data-ttu-id="d1a53-128">では、バックアップ スクリプトを作成し、選択するジョブを右クリックして**ジョブをスクリプト**です。</span><span class="sxs-lookup"><span data-stu-id="d1a53-128">Right-click the job you want to create a backup script for, and then select **Script Job as**.</span></span>  
  
4.  <span data-ttu-id="d1a53-129">選択**Create**または**Drop**選択してから、**新しいクエリ エディター ウィンドウ**、**ファイル**、または**クリップボード**スクリプトの保存先を選択します。</span><span class="sxs-lookup"><span data-stu-id="d1a53-129">Select **CREATE To** or **DROP To**, then select **New Query Editor Window**, **File**, or **Clipboard** to select a destination for the script.</span></span> <span data-ttu-id="d1a53-130">通常、変換先は、ファイルが、 **.sql**拡張機能です。</span><span class="sxs-lookup"><span data-stu-id="d1a53-130">Typically, the destination is a file with a **.sql** extension.</span></span>  
  
5.  <span data-ttu-id="d1a53-131">スクリプトを作成する各ジョブについて、手順 3. から繰り返します。</span><span class="sxs-lookup"><span data-stu-id="d1a53-131">Repeat this procedure from Step 3 for each job you want to script.</span></span> <span data-ttu-id="d1a53-132">BizTalk Server 関連ジョブの一覧を参照して、どのジョブのスクリプトを作成するかを判断してください。</span><span class="sxs-lookup"><span data-stu-id="d1a53-132">Refer to the list of BizTalk Server related jobs to determine which jobs you need to script.</span></span>  
  
     <span data-ttu-id="d1a53-133">バックアップするには、少なくとも、 **Backup BizTalk Server (BizTalkMgmtDb)**ジョブを構成後します。</span><span class="sxs-lookup"><span data-stu-id="d1a53-133">At a minimum, you should back up the **Backup BizTalk Server (BizTalkMgmtDb)** job after it is configured.</span></span>  
  
## <a name="restore-a-job-from-a-script"></a><span data-ttu-id="d1a53-134">スクリプトからジョブを復元します。</span><span class="sxs-lookup"><span data-stu-id="d1a53-134">Restore a job from a script</span></span>  
  
1.  <span data-ttu-id="d1a53-135">開いている**SQL Server Management Studio**です。</span><span class="sxs-lookup"><span data-stu-id="d1a53-135">Open **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="d1a53-136">**ファイル**] メニューの [**開く**スクリプト化されたジョブを含むファイルです。</span><span class="sxs-lookup"><span data-stu-id="d1a53-136">On the **File** menu, **Open** the file containing the scripted job.</span></span>  
  
3.  <span data-ttu-id="d1a53-137">スクリプトを実行してジョブを作成します。</span><span class="sxs-lookup"><span data-stu-id="d1a53-137">Execute the script to create the job.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="d1a53-138">次の手順</span><span class="sxs-lookup"><span data-stu-id="d1a53-138">Next Steps</span></span>  
 [<span data-ttu-id="d1a53-139">バックアップおよび SQL Server ログインを復元する方法</span><span class="sxs-lookup"><span data-stu-id="d1a53-139">How to Back Up and Restore SQL Server Logins</span></span>](../core/how-to-back-up-and-restore-sql-server-logins.md)