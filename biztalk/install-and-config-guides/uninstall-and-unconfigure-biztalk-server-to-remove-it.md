---
title: アンインストールし、それを削除する BizTalk Server の構成を解除 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e9ea8757-ca49-421b-bf7b-89344201398a
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: df844f6fce54b7be266a068561638b512a687924
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401462"
---
# <a name="uninstall-and-unconfigure-biztalk-server-to-remove-it"></a><span data-ttu-id="2ef6b-102">アンインストールし、それを削除する BizTalk Server の構成を解除</span><span class="sxs-lookup"><span data-stu-id="2ef6b-102">Uninstall and unconfigure BizTalk Server to remove it</span></span>
<span data-ttu-id="2ef6b-103">アンインストールし、構成解除[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="2ef6b-103">Uninstall and unconfigure [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> 
  
##  <a name="BKMK_BeforeYouBegin"></a> <span data-ttu-id="2ef6b-104">はじめに</span><span class="sxs-lookup"><span data-stu-id="2ef6b-104">Before You Begin</span></span>  
  
- <span data-ttu-id="2ef6b-105">解除する必要があります、アンインストールする前に、構成[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="2ef6b-105">Before you uninstall, you must un-configure [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
- <span data-ttu-id="2ef6b-106">このトピックでは、さまざまなジョブ、パッケージ、および削除するデータベースを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="2ef6b-106">This topic lists the different jobs, packages, and databases to be deleted.</span></span> <span data-ttu-id="2ef6b-107">表示名は、既定の名前です。</span><span class="sxs-lookup"><span data-stu-id="2ef6b-107">The names listed are the default names.</span></span> <span data-ttu-id="2ef6b-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境に既定以外の名前を使用することがあります。</span><span class="sxs-lookup"><span data-stu-id="2ef6b-108">Your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment may be using non-default names.</span></span>  
  
- <span data-ttu-id="2ef6b-109">表示されている順序で手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="2ef6b-109">Complete the steps in the order listed.</span></span> <span data-ttu-id="2ef6b-110">それ以外の場合、アンインストールは完了しません。</span><span class="sxs-lookup"><span data-stu-id="2ef6b-110">Otherwise, the uninstall is not complete.</span></span>  
  
##  <a name="BKMK_Unconfigure"></a> <span data-ttu-id="2ef6b-111">BizTalk Server の構成を解除</span><span class="sxs-lookup"><span data-stu-id="2ef6b-111">Un-configure BizTalk Server</span></span>  
  
1. <span data-ttu-id="2ef6b-112">右クリック**[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]構成**、選び**管理者として実行**します。</span><span class="sxs-lookup"><span data-stu-id="2ef6b-112">Right-click **[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Configuration**, and select **Run as Administrator**.</span></span>  
  
2. <span data-ttu-id="2ef6b-113">構成では、次のように選択します。**機能の構成解除**します。</span><span class="sxs-lookup"><span data-stu-id="2ef6b-113">In the Configuration, select **Unconfigure Features**.</span></span>  
  
3. <span data-ttu-id="2ef6b-114">この構成を解除すると、選択する機能の選択**OK**します。</span><span class="sxs-lookup"><span data-stu-id="2ef6b-114">Select the features you want to unconfigure, and select **OK**.</span></span> <span data-ttu-id="2ef6b-115">続行するように求められたら、選択**はい**します。</span><span class="sxs-lookup"><span data-stu-id="2ef6b-115">If prompted to proceed, select **Yes**.</span></span> <span data-ttu-id="2ef6b-116">コンピューターからすべてのものを削除するには、すべての機能を選択できます。</span><span class="sxs-lookup"><span data-stu-id="2ef6b-116">To  remove everything from the computer, you can select all the features.</span></span>  
  
4. <span data-ttu-id="2ef6b-117">選択**次**、し、ウィザードを続行します。</span><span class="sxs-lookup"><span data-stu-id="2ef6b-117">Select **Next**, and continue through the wizard.</span></span>  
  
   <span data-ttu-id="2ef6b-118">ような一時フォルダーには、ログ ファイルが生成されます。C:\Users\username\AppData\Local\Temp\ConfigLog(8-29-2016 0h37m59s).log.</span><span class="sxs-lookup"><span data-stu-id="2ef6b-118">A log file is generated in a temp folder, similar to: C:\Users\username\AppData\Local\Temp\ConfigLog(8-29-2016 0h37m59s).log.</span></span>  
  
##  <a name="BKMK_Uninstall"></a> <span data-ttu-id="2ef6b-119">BizTalk Server ランタイム コンポーネントをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="2ef6b-119">Uninstall BizTalk Server Runtime Components</span></span>  
  
1. <span data-ttu-id="2ef6b-120">開いている**プログラムと機能**します。</span><span class="sxs-lookup"><span data-stu-id="2ef6b-120">Open **Programs and Features**.</span></span>  
  
2. <span data-ttu-id="2ef6b-121">選択、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]リストから、バージョンと**アンインストール**します。</span><span class="sxs-lookup"><span data-stu-id="2ef6b-121">Select  your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] version from the list, and  **Uninstall**.</span></span>  
  
3. <span data-ttu-id="2ef6b-122">**削除**し、ウィザードを続行します。</span><span class="sxs-lookup"><span data-stu-id="2ef6b-122">**Remove** it, and continue through the wizard.</span></span>  
  
   <span data-ttu-id="2ef6b-123">ような一時フォルダーには、ログ ファイルが生成されます。C:\Users\\*username*\AppData\Local\Setup(083016 xxxxxx).htm</span><span class="sxs-lookup"><span data-stu-id="2ef6b-123">A log file is generated in a temp folder, similar to: C:\Users\\*username*\AppData\Local\Setup(083016 xxxxxx).htm</span></span>  
  
##  <a name="BKMK_UninstallSSO"></a> <span data-ttu-id="2ef6b-124">エンタープライズ シングル サインオンのアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="2ef6b-124">Uninstall Enterprise Single Sign-On</span></span>  
  
1. <span data-ttu-id="2ef6b-125">開いている**プログラムと機能**します。</span><span class="sxs-lookup"><span data-stu-id="2ef6b-125">Open **Programs and Features**.</span></span>  
  
2. <span data-ttu-id="2ef6b-126">選択**Microsoft エンタープライズ シングル サインオン**リストから、および**アンインストール**します。</span><span class="sxs-lookup"><span data-stu-id="2ef6b-126">Select **Microsoft Enterprise Single Sign-On** from the list, and **Uninstall**.</span></span>  
  
3. <span data-ttu-id="2ef6b-127">**削除**し、ウィザードを続行します。</span><span class="sxs-lookup"><span data-stu-id="2ef6b-127">**Remove** it, and continue through the wizard.</span></span>  
  
   <span data-ttu-id="2ef6b-128">ような一時フォルダーには、ログ ファイルが生成されます。C:\Users\\*username*\AppData\Local\Setup(083016 xxxxxx).htm</span><span class="sxs-lookup"><span data-stu-id="2ef6b-128">A log file is generated in a temp folder, similar to: C:\Users\\*username*\AppData\Local\Setup(083016 xxxxxx).htm</span></span>  
  
##  <a name="BKMK_RemoveRemaining"></a> <span data-ttu-id="2ef6b-129">SQL ジョブ、データベース、およびパッケージを削除します。</span><span class="sxs-lookup"><span data-stu-id="2ef6b-129">Delete SQL jobs, databases, and packages</span></span>  
  
#### <a name="delete-sql-server-agent-jobs"></a><span data-ttu-id="2ef6b-130">SQL Server エージェント ジョブを削除します。</span><span class="sxs-lookup"><span data-stu-id="2ef6b-130">Delete SQL Server agent jobs</span></span>  
  
1.  <span data-ttu-id="2ef6b-131">開いている**SQL Server Management Studio**管理者として。</span><span class="sxs-lookup"><span data-stu-id="2ef6b-131">Open **SQL Server Management Studio** as Administrator.</span></span>  
  
2.  <span data-ttu-id="2ef6b-132">**SQL Server Management Studio**への接続**データベース エンジン**、展開**SQL Server エージェント**、展開と**ジョブ**します。</span><span class="sxs-lookup"><span data-stu-id="2ef6b-132">In **SQL Server Management Studio**, connect to **Database Engine**, expand **SQL Server Agent**, and expand  **Jobs**.</span></span>  
  
3.  <span data-ttu-id="2ef6b-133">次のジョブを削除 (ジョブを右クリックし、選択**削除**)。</span><span class="sxs-lookup"><span data-stu-id="2ef6b-133">Delete the following jobs (right-click the job, and select **Delete**):</span></span>  
  
    -   <span data-ttu-id="2ef6b-134">BizTalk Server (BizTalkMgmtDb) のバックアップします。</span><span class="sxs-lookup"><span data-stu-id="2ef6b-134">Backup BizTalk Server (BizTalkMgmtDb)</span></span>  
  
    -   <span data-ttu-id="2ef6b-135">CleanupBTFExpiredEntriesJob_BizTalkMgmtDb</span><span class="sxs-lookup"><span data-stu-id="2ef6b-135">CleanupBTFExpiredEntriesJob_BizTalkMgmtDb</span></span>  
  
    -   <span data-ttu-id="2ef6b-136">DTA Purge and Archive (BizTalkDTADb)</span><span class="sxs-lookup"><span data-stu-id="2ef6b-136">DTA Purge and Archive (BizTalkDTADb)</span></span>  
  
    -   <span data-ttu-id="2ef6b-137">MessageBox_DeadProcesses_Cleanup_BizTalkMsgBoxDb</span><span class="sxs-lookup"><span data-stu-id="2ef6b-137">MessageBox_DeadProcesses_Cleanup_BizTalkMsgBoxDb</span></span>  
  
    -   <span data-ttu-id="2ef6b-138">MessageBox_Message_Cleanup_BizTalkMsgBoxDb</span><span class="sxs-lookup"><span data-stu-id="2ef6b-138">MessageBox_Message_Cleanup_BizTalkMsgBoxDb</span></span>  
  
    -   <span data-ttu-id="2ef6b-139">MessageBox_Message_ManageRefCountLog_BizTalkMsgBoxDb</span><span class="sxs-lookup"><span data-stu-id="2ef6b-139">MessageBox_Message_ManageRefCountLog_BizTalkMsgBoxDb</span></span>  
  
    -   <span data-ttu-id="2ef6b-140">MessageBox_Parts_Cleanup_BizTalkMsgBoxDb</span><span class="sxs-lookup"><span data-stu-id="2ef6b-140">MessageBox_Parts_Cleanup_BizTalkMsgBoxDb</span></span>  
  
    -   <span data-ttu-id="2ef6b-141">MessageBox_UpdateStats_BizTalkMsgBoxDb</span><span class="sxs-lookup"><span data-stu-id="2ef6b-141">MessageBox_UpdateStats_BizTalkMsgBoxDb</span></span>  
  
    -   <span data-ttu-id="2ef6b-142">BizTalk Server (BizTalkMgmtDb) の監視します。</span><span class="sxs-lookup"><span data-stu-id="2ef6b-142">Monitor BizTalk Server (BizTalkMgmtDb)</span></span>  
  
    -   <span data-ttu-id="2ef6b-143">Operations_OperateOnInstances_OnMaster_BizTalkMsgBoxDb</span><span class="sxs-lookup"><span data-stu-id="2ef6b-143">Operations_OperateOnInstances_OnMaster_BizTalkMsgBoxDb</span></span>  
  
    -   <span data-ttu-id="2ef6b-144">PurgeSubscriptionsJob_BizTalkMsgBoxDb</span><span class="sxs-lookup"><span data-stu-id="2ef6b-144">PurgeSubscriptionsJob_BizTalkMsgBoxDb</span></span>  
  
    -   <span data-ttu-id="2ef6b-145">Rules_Database_Cleanup_BizTalkRuleEngineDb</span><span class="sxs-lookup"><span data-stu-id="2ef6b-145">Rules_Database_Cleanup_BizTalkRuleEngineDb</span></span>  
  
    -   <span data-ttu-id="2ef6b-146">TrackedMessages_Copy_BizTalkMsgBoxDb</span><span class="sxs-lookup"><span data-stu-id="2ef6b-146">TrackedMessages_Copy_BizTalkMsgBoxDb</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="2ef6b-147">BAM を展開した場合、bam _ を削除する必要がありますも\<*キューブ名*\>_\<*ビュー名*\>ジョブ。</span><span class="sxs-lookup"><span data-stu-id="2ef6b-147">If you deployed BAM, you may also need to remove the bam_\<*Cube Name*\>_\<*View Name*\> job.</span></span>  
  
#### <a name="delete-biztalk-server-databases"></a><span data-ttu-id="2ef6b-148">BizTalk Server データベースを削除します。</span><span class="sxs-lookup"><span data-stu-id="2ef6b-148">Delete BizTalk Server databases</span></span>  
  
1.  <span data-ttu-id="2ef6b-149">**オブジェクト エクスプ ローラー**、展開**データベース**します。</span><span class="sxs-lookup"><span data-stu-id="2ef6b-149">In **Object Explorer**, expand **Databases**.</span></span>  
  
2.  <span data-ttu-id="2ef6b-150">次のデータベースの削除 (データベースを右クリックして**削除**)。</span><span class="sxs-lookup"><span data-stu-id="2ef6b-150">Delete the following databases (right-click the database, and select **Delete**):</span></span>  
  
    -   <span data-ttu-id="2ef6b-151">BAMArchive</span><span class="sxs-lookup"><span data-stu-id="2ef6b-151">BAMArchive</span></span>  
  
    -   <span data-ttu-id="2ef6b-152">BAMPrimaryImport</span><span class="sxs-lookup"><span data-stu-id="2ef6b-152">BAMPrimaryImport</span></span>  
  
    -   <span data-ttu-id="2ef6b-153">BAMStarSchema</span><span class="sxs-lookup"><span data-stu-id="2ef6b-153">BAMStarSchema</span></span>  
  
    -   <span data-ttu-id="2ef6b-154">BizTalkDTADb</span><span class="sxs-lookup"><span data-stu-id="2ef6b-154">BizTalkDTADb</span></span>  
  
    -   <span data-ttu-id="2ef6b-155">BizTalkMgmtDb</span><span class="sxs-lookup"><span data-stu-id="2ef6b-155">BizTalkMgmtDb</span></span>  
  
    -   <span data-ttu-id="2ef6b-156">BizTalkMsgBoxDb</span><span class="sxs-lookup"><span data-stu-id="2ef6b-156">BizTalkMsgBoxDb</span></span>  
  
    -   <span data-ttu-id="2ef6b-157">BizTalkRuleEngineDb</span><span class="sxs-lookup"><span data-stu-id="2ef6b-157">BizTalkRuleEngineDb</span></span>  
  
    -   <span data-ttu-id="2ef6b-158">SSODB</span><span class="sxs-lookup"><span data-stu-id="2ef6b-158">SSODB</span></span>  
  
#### <a name="remove-sql-server-integration-services-packages"></a><span data-ttu-id="2ef6b-159">SQL Server Integration Services パッケージを削除します。</span><span class="sxs-lookup"><span data-stu-id="2ef6b-159">Remove SQL Server Integration Services packages</span></span>  
  
1.  <span data-ttu-id="2ef6b-160">**オブジェクト エクスプ ローラー**、**接続**に**Integration Services**します。</span><span class="sxs-lookup"><span data-stu-id="2ef6b-160">In **Object Explorer**,  **Connect** to **Integration Services**.</span></span>  
  
2.  <span data-ttu-id="2ef6b-161">展開**格納されたパッケージ**、展開と**MSDB**します。</span><span class="sxs-lookup"><span data-stu-id="2ef6b-161">Expand **Stored Packages**, and expand **MSDB**.</span></span>  
  
3.  <span data-ttu-id="2ef6b-162">次のプレフィックスを持つパッケージを削除する (パッケージを右クリックして**削除**)。</span><span class="sxs-lookup"><span data-stu-id="2ef6b-162">Delete the packages with the following prefixes (right-click the package, and select **Delete**):</span></span>  
  
    -   <span data-ttu-id="2ef6b-163">Bam_an _\<*キューブ名*\></span><span class="sxs-lookup"><span data-stu-id="2ef6b-163">BAM_AN_\<*Cube Name*\></span></span>  
  
    -   <span data-ttu-id="2ef6b-164">Bam_dm _\<*ビュー名*\></span><span class="sxs-lookup"><span data-stu-id="2ef6b-164">BAM_DM_\<*View Name*\></span></span>  
  
