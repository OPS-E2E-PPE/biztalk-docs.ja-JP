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
ms.openlocfilehash: 5ab66d347795a0b8264a8bb6238149ab1b64572b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36990635"
---
# <a name="uninstall-and-unconfigure-biztalk-server-to-remove-it"></a><span data-ttu-id="c7e13-102">BizTalk Server の削除 (アンインストールおよび構成の解除)</span><span class="sxs-lookup"><span data-stu-id="c7e13-102">Uninstall and unconfigure BizTalk Server to remove it</span></span>
<span data-ttu-id="c7e13-103">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のアンインストールおよび構成解除を行います。</span><span class="sxs-lookup"><span data-stu-id="c7e13-103">Uninstall and unconfigure [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> 
  
##  <a name="BKMK_BeforeYouBegin"></a> <span data-ttu-id="c7e13-104">はじめに</span><span class="sxs-lookup"><span data-stu-id="c7e13-104">Before You Begin</span></span>  
  
- <span data-ttu-id="c7e13-105">アンインストールする前に、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の構成を解除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c7e13-105">Before you uninstall, you must un-configure [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
- <span data-ttu-id="c7e13-106">このトピックでは、削除されるジョブ、パッケージ、データベースの名前が記載されています。</span><span class="sxs-lookup"><span data-stu-id="c7e13-106">This topic lists the different jobs, packages, and databases to be deleted.</span></span> <span data-ttu-id="c7e13-107">ここに記載されている名前は、既定の名前です。</span><span class="sxs-lookup"><span data-stu-id="c7e13-107">The names listed are the default names.</span></span> <span data-ttu-id="c7e13-108">お使いの [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 環境では、既定の名前を使用していない場合があります。</span><span class="sxs-lookup"><span data-stu-id="c7e13-108">Your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment may be using non-default names.</span></span>  
  
- <span data-ttu-id="c7e13-109">手順は、ここに示している順序どおりに実行してください。</span><span class="sxs-lookup"><span data-stu-id="c7e13-109">Complete the steps in the order listed.</span></span> <span data-ttu-id="c7e13-110">順序が変わるとアンインストールを完了できません。</span><span class="sxs-lookup"><span data-stu-id="c7e13-110">Otherwise, the uninstall is not complete.</span></span>  
  
##  <a name="BKMK_Unconfigure"></a> <span data-ttu-id="c7e13-111">BizTalk Server の構成解除</span><span class="sxs-lookup"><span data-stu-id="c7e13-111">Un-configure BizTalk Server</span></span>  
  
1. <span data-ttu-id="c7e13-112">**[[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 構成]** を右クリックし、**[管理者として実行]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c7e13-112">Right-click **[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Configuration**, and select **Run as Administrator**.</span></span>  
  
2. <span data-ttu-id="c7e13-113">[構成] で **[機能の構成解除]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c7e13-113">In the Configuration, select **Unconfigure Features**.</span></span>  
  
3. <span data-ttu-id="c7e13-114">構成を解除する機能を選択し、**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c7e13-114">Select the features you want to unconfigure, and select **OK**.</span></span> <span data-ttu-id="c7e13-115">続行を確認するメッセージが表示されたら、**[はい]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c7e13-115">If prompted to proceed, select **Yes**.</span></span> <span data-ttu-id="c7e13-116">コンピューターからすべて削除する場合は、すべての機能を選択できます。</span><span class="sxs-lookup"><span data-stu-id="c7e13-116">To  remove everything from the computer, you can select all the features.</span></span>  
  
4. <span data-ttu-id="c7e13-117">**[次へ]** を選択し、ウィザードを進みます。</span><span class="sxs-lookup"><span data-stu-id="c7e13-117">Select **Next**, and continue through the wizard.</span></span>  
  
   <span data-ttu-id="c7e13-118">C:\Users\ユーザー名\AppData\Local\Temp\ConfigLog(8-29-2016 0h37m59s).log のようなログ ファイルが一時フォルダーに生成されます。</span><span class="sxs-lookup"><span data-stu-id="c7e13-118">A log file is generated in a temp folder, similar to: C:\Users\username\AppData\Local\Temp\ConfigLog(8-29-2016 0h37m59s).log.</span></span>  
  
##  <a name="BKMK_Uninstall"></a> <span data-ttu-id="c7e13-119">BizTalk Server ランタイム コンポーネントのアンインストール</span><span class="sxs-lookup"><span data-stu-id="c7e13-119">Uninstall BizTalk Server Runtime Components</span></span>  
  
1. <span data-ttu-id="c7e13-120">**[プログラムと機能]** を開きます。</span><span class="sxs-lookup"><span data-stu-id="c7e13-120">Open **Programs and Features**.</span></span>  
  
2. <span data-ttu-id="c7e13-121">リストから [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] バージョンを選択し、**アンインストール**します。</span><span class="sxs-lookup"><span data-stu-id="c7e13-121">Select  your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] version from the list, and  **Uninstall**.</span></span>  
  
3. <span data-ttu-id="c7e13-122">**削除**して、ウィザードを進みます。</span><span class="sxs-lookup"><span data-stu-id="c7e13-122">**Remove** it, and continue through the wizard.</span></span>  
  
   <span data-ttu-id="c7e13-123">C:\Users\\*ユーザー名*\AppData\Local\Setup(083016 xxxxxx).htm のようなログ ファイルが一時フォルダーに生成されます。</span><span class="sxs-lookup"><span data-stu-id="c7e13-123">A log file is generated in a temp folder, similar to: C:\Users\\*username*\AppData\Local\Setup(083016 xxxxxx).htm</span></span>  
  
##  <a name="BKMK_UninstallSSO"></a> <span data-ttu-id="c7e13-124">Enterprise Single Sign-On のアンインストール</span><span class="sxs-lookup"><span data-stu-id="c7e13-124">Uninstall Enterprise Single Sign-On</span></span>  
  
1. <span data-ttu-id="c7e13-125">**[プログラムと機能]** を開きます。</span><span class="sxs-lookup"><span data-stu-id="c7e13-125">Open **Programs and Features**.</span></span>  
  
2. <span data-ttu-id="c7e13-126">リストから **[Microsoft Enterprise Single Sign-On]** を選択し、**アンインストール**します。</span><span class="sxs-lookup"><span data-stu-id="c7e13-126">Select **Microsoft Enterprise Single Sign-On** from the list, and **Uninstall**.</span></span>  
  
3. <span data-ttu-id="c7e13-127">**削除**して、ウィザードを進みます。</span><span class="sxs-lookup"><span data-stu-id="c7e13-127">**Remove** it, and continue through the wizard.</span></span>  
  
   <span data-ttu-id="c7e13-128">C:\Users\\*ユーザー名*\AppData\Local\Setup(083016 xxxxxx).htm のようなログ ファイルが一時フォルダーに生成されます。</span><span class="sxs-lookup"><span data-stu-id="c7e13-128">A log file is generated in a temp folder, similar to: C:\Users\\*username*\AppData\Local\Setup(083016 xxxxxx).htm</span></span>  
  
##  <a name="BKMK_RemoveRemaining"></a> <span data-ttu-id="c7e13-129">SQL ジョブ、データベース、およびパッケージを削除する</span><span class="sxs-lookup"><span data-stu-id="c7e13-129">Delete SQL jobs, databases, and packages</span></span>  
  
#### <a name="delete-sql-server-agent-jobs"></a><span data-ttu-id="c7e13-130">SQL Server エージェント ジョブの削除</span><span class="sxs-lookup"><span data-stu-id="c7e13-130">Delete SQL Server agent jobs</span></span>  
  
1.  <span data-ttu-id="c7e13-131">**SQL Server Management Studio** を管理者として開きます。</span><span class="sxs-lookup"><span data-stu-id="c7e13-131">Open **SQL Server Management Studio** as Administrator.</span></span>  
  
2.  <span data-ttu-id="c7e13-132">**SQL Server Management Studio** で、**データベース エンジン**に接続し、**[SQL Server エージェント]**、**[ジョブ]** の順に展開します。</span><span class="sxs-lookup"><span data-stu-id="c7e13-132">In **SQL Server Management Studio**, connect to **Database Engine**, expand **SQL Server Agent**, and expand  **Jobs**.</span></span>  
  
3.  <span data-ttu-id="c7e13-133">次のジョブを削除します (ジョブを右クリックし、**[削除]** を選択します)。</span><span class="sxs-lookup"><span data-stu-id="c7e13-133">Delete the following jobs (right-click the job, and select **Delete**):</span></span>  
  
    -   <span data-ttu-id="c7e13-134">BizTalk Server のバックアップ (BizTalkMgmtDb)</span><span class="sxs-lookup"><span data-stu-id="c7e13-134">Backup BizTalk Server (BizTalkMgmtDb)</span></span>  
  
    -   <span data-ttu-id="c7e13-135">CleanupBTFExpiredEntriesJob_BizTalkMgmtDb</span><span class="sxs-lookup"><span data-stu-id="c7e13-135">CleanupBTFExpiredEntriesJob_BizTalkMgmtDb</span></span>  
  
    -   <span data-ttu-id="c7e13-136">DTA Purge and Archive (BizTalkDTADb)</span><span class="sxs-lookup"><span data-stu-id="c7e13-136">DTA Purge and Archive (BizTalkDTADb)</span></span>  
  
    -   <span data-ttu-id="c7e13-137">MessageBox_DeadProcesses_Cleanup_BizTalkMsgBoxDb</span><span class="sxs-lookup"><span data-stu-id="c7e13-137">MessageBox_DeadProcesses_Cleanup_BizTalkMsgBoxDb</span></span>  
  
    -   <span data-ttu-id="c7e13-138">MessageBox_Message_Cleanup_BizTalkMsgBoxDb</span><span class="sxs-lookup"><span data-stu-id="c7e13-138">MessageBox_Message_Cleanup_BizTalkMsgBoxDb</span></span>  
  
    -   <span data-ttu-id="c7e13-139">MessageBox_Message_ManageRefCountLog_BizTalkMsgBoxDb</span><span class="sxs-lookup"><span data-stu-id="c7e13-139">MessageBox_Message_ManageRefCountLog_BizTalkMsgBoxDb</span></span>  
  
    -   <span data-ttu-id="c7e13-140">MessageBox_Parts_Cleanup_BizTalkMsgBoxDb</span><span class="sxs-lookup"><span data-stu-id="c7e13-140">MessageBox_Parts_Cleanup_BizTalkMsgBoxDb</span></span>  
  
    -   <span data-ttu-id="c7e13-141">MessageBox_UpdateStats_BizTalkMsgBoxDb</span><span class="sxs-lookup"><span data-stu-id="c7e13-141">MessageBox_UpdateStats_BizTalkMsgBoxDb</span></span>  
  
    -   <span data-ttu-id="c7e13-142">BizTalk Server の監視 (BizTalkMgmtDb)</span><span class="sxs-lookup"><span data-stu-id="c7e13-142">Monitor BizTalk Server (BizTalkMgmtDb)</span></span>  
  
    -   <span data-ttu-id="c7e13-143">Operations_OperateOnInstances_OnMaster_BizTalkMsgBoxDb</span><span class="sxs-lookup"><span data-stu-id="c7e13-143">Operations_OperateOnInstances_OnMaster_BizTalkMsgBoxDb</span></span>  
  
    -   <span data-ttu-id="c7e13-144">PurgeSubscriptionsJob_BizTalkMsgBoxDb</span><span class="sxs-lookup"><span data-stu-id="c7e13-144">PurgeSubscriptionsJob_BizTalkMsgBoxDb</span></span>  
  
    -   <span data-ttu-id="c7e13-145">Rules_Database_Cleanup_BizTalkRuleEngineDb</span><span class="sxs-lookup"><span data-stu-id="c7e13-145">Rules_Database_Cleanup_BizTalkRuleEngineDb</span></span>  
  
    -   <span data-ttu-id="c7e13-146">TrackedMessages_Copy_BizTalkMsgBoxDb</span><span class="sxs-lookup"><span data-stu-id="c7e13-146">TrackedMessages_Copy_BizTalkMsgBoxDb</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="c7e13-147">BAM を展開した場合、bam _ を削除する必要がありますも\<*キューブ名*\>_\<*ビュー名*\>ジョブ。</span><span class="sxs-lookup"><span data-stu-id="c7e13-147">If you deployed BAM, you may also need to remove the bam_\<*Cube Name*\>_\<*View Name*\> job.</span></span>  
  
#### <a name="delete-biztalk-server-databases"></a><span data-ttu-id="c7e13-148">BizTalk Server データベースの削除</span><span class="sxs-lookup"><span data-stu-id="c7e13-148">Delete BizTalk Server databases</span></span>  
  
1.  <span data-ttu-id="c7e13-149">**オブジェクト エクスプローラー**で、**[データベース]** を展開します。</span><span class="sxs-lookup"><span data-stu-id="c7e13-149">In **Object Explorer**, expand **Databases**.</span></span>  
  
2.  <span data-ttu-id="c7e13-150">次のデータベースを削除します (データベースを右クリックし、**[削除]** を選択します)。</span><span class="sxs-lookup"><span data-stu-id="c7e13-150">Delete the following databases (right-click the database, and select **Delete**):</span></span>  
  
    -   <span data-ttu-id="c7e13-151">BAMArchive</span><span class="sxs-lookup"><span data-stu-id="c7e13-151">BAMArchive</span></span>  
  
    -   <span data-ttu-id="c7e13-152">BAMPrimaryImport</span><span class="sxs-lookup"><span data-stu-id="c7e13-152">BAMPrimaryImport</span></span>  
  
    -   <span data-ttu-id="c7e13-153">BAMStarSchema</span><span class="sxs-lookup"><span data-stu-id="c7e13-153">BAMStarSchema</span></span>  
  
    -   <span data-ttu-id="c7e13-154">BizTalkDTADb</span><span class="sxs-lookup"><span data-stu-id="c7e13-154">BizTalkDTADb</span></span>  
  
    -   <span data-ttu-id="c7e13-155">BizTalkMgmtDb</span><span class="sxs-lookup"><span data-stu-id="c7e13-155">BizTalkMgmtDb</span></span>  
  
    -   <span data-ttu-id="c7e13-156">BizTalkMsgBoxDb</span><span class="sxs-lookup"><span data-stu-id="c7e13-156">BizTalkMsgBoxDb</span></span>  
  
    -   <span data-ttu-id="c7e13-157">BizTalkRuleEngineDb</span><span class="sxs-lookup"><span data-stu-id="c7e13-157">BizTalkRuleEngineDb</span></span>  
  
    -   <span data-ttu-id="c7e13-158">SSODB</span><span class="sxs-lookup"><span data-stu-id="c7e13-158">SSODB</span></span>  
  
#### <a name="remove-sql-server-integration-services-packages"></a><span data-ttu-id="c7e13-159">SQL Server Integration Services パッケージの削除</span><span class="sxs-lookup"><span data-stu-id="c7e13-159">Remove SQL Server Integration Services packages</span></span>  
  
1.  <span data-ttu-id="c7e13-160">**オブジェクト エクスプローラー**で、**Integration Services** に**接続**します。</span><span class="sxs-lookup"><span data-stu-id="c7e13-160">In **Object Explorer**,  **Connect** to **Integration Services**.</span></span>  
  
2.  <span data-ttu-id="c7e13-161">**[格納されたパッケージ]** を展開し、**[MSDB]** を展開します。</span><span class="sxs-lookup"><span data-stu-id="c7e13-161">Expand **Stored Packages**, and expand **MSDB**.</span></span>  
  
3.  <span data-ttu-id="c7e13-162">次のプレフィックスを持つパッケージを削除します (パッケージを右クリックし、**[削除]** を選択します)。</span><span class="sxs-lookup"><span data-stu-id="c7e13-162">Delete the packages with the following prefixes (right-click the package, and select **Delete**):</span></span>  
  
    -   <span data-ttu-id="c7e13-163">Bam_an _\<*キューブ名*\></span><span class="sxs-lookup"><span data-stu-id="c7e13-163">BAM_AN_\<*Cube Name*\></span></span>  
  
    -   <span data-ttu-id="c7e13-164">Bam_dm _\<*ビュー名*\></span><span class="sxs-lookup"><span data-stu-id="c7e13-164">BAM_DM_\<*View Name*\></span></span>  
  
