---
title: BizTalk Server 2013 および 2013 R2 のインストール後のステップ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c3b47843-9da5-4144-8b84-135494b8ab43
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cae3a9705e776d8f01e5659341378240eb2fcde1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394001"
---
# <a name="post-installation-steps-for-biztalk-server-2013-and-2013-r2"></a><span data-ttu-id="44c43-102">BizTalk Server 2013 および 2003 R2 のインストール後の手順</span><span class="sxs-lookup"><span data-stu-id="44c43-102">Post-installation Steps for BizTalk Server 2013 and 2013 R2</span></span>
  
##  <a name="BKMK_NamedPipes"></a> <span data-ttu-id="44c43-103">有効にする TCP/IP および名前付きパイプ</span><span class="sxs-lookup"><span data-stu-id="44c43-103">Enable TCP/IP and Named Pipes</span></span>  
  
1. <span data-ttu-id="44c43-104">**[SQL Server 構成マネージャー]** を開きます。</span><span class="sxs-lookup"><span data-stu-id="44c43-104">Open **SQL Server Configuration Manager**.</span></span>  
  
2. <span data-ttu-id="44c43-105">展開**SQL Server ネットワーク構成**、選び**MSSQLSERVER のプロトコル**します。</span><span class="sxs-lookup"><span data-stu-id="44c43-105">Expand **SQL Server Network Configuration**, and select **Protocols for MSSQLSERVER**.</span></span>  
  
3. <span data-ttu-id="44c43-106">いることを確認両方**TCP/IP**と**名前付きパイプ**を有効にします。</span><span class="sxs-lookup"><span data-stu-id="44c43-106">Verify that both **TCP/IP** and **Named Pipes** are enabled.</span></span> <span data-ttu-id="44c43-107">有効な場合は、次の手順に進みます。</span><span class="sxs-lookup"><span data-stu-id="44c43-107">If enabled, proceed to the next step.</span></span>  
  
    <span data-ttu-id="44c43-108">有効になっていない: 場合</span><span class="sxs-lookup"><span data-stu-id="44c43-108">If not enabled:</span></span>  
  
   -   <span data-ttu-id="44c43-109">プロトコルを右クリックし、**を有効にする**します。</span><span class="sxs-lookup"><span data-stu-id="44c43-109">Right-click the protocol, and then click **Enable**.</span></span>  
  
   -   <span data-ttu-id="44c43-110">必要に応じて、他のプロトコルを有効にするを繰り返します。</span><span class="sxs-lookup"><span data-stu-id="44c43-110">Repeat to enable the other protocol if necessary.</span></span>  
  
   -   <span data-ttu-id="44c43-111">左側のウィンドウで次のようにクリックします。 **SQL Server サービス**します。</span><span class="sxs-lookup"><span data-stu-id="44c43-111">In the left-hand pane, click **SQL Server Services**.</span></span>  
  
   -   <span data-ttu-id="44c43-112">右側のウィンドウで右クリックして**SQL Server (MSSQLSERVER)**、 をクリック**停止**します。</span><span class="sxs-lookup"><span data-stu-id="44c43-112">In the right-hand pane, right-click **SQL Server (MSSQLSERVER)**, and click **Stop**.</span></span>  
  
   -   <span data-ttu-id="44c43-113">右クリックし、サービスが停止したら、 **SQL Server (MSSQLSERVER)**、 をクリック**開始**します。</span><span class="sxs-lookup"><span data-stu-id="44c43-113">When the service has stopped, right-click **SQL Server (MSSQLSERVER)**, and click **Start**.</span></span>  
  
   > [!IMPORTANT]
   >  <span data-ttu-id="44c43-114">使用する場合[!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)]、 **NS$ BAMAlerts**サービスを停止する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="44c43-114">If you are using [!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)], the **NS$BAMAlerts** service may be stopped.</span></span> <span data-ttu-id="44c43-115">サービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="44c43-115">Restart the service.</span></span>  
  
4. <span data-ttu-id="44c43-116">閉じる、 **Configuration Manager**します。</span><span class="sxs-lookup"><span data-stu-id="44c43-116">Close the **Configuration Manager**.</span></span>  
  
##  <a name="BKMK_DTC"></a> <span data-ttu-id="44c43-117">ローカル ホスト サーバー上の DTC を有効にします。</span><span class="sxs-lookup"><span data-stu-id="44c43-117">Enable DTC on the Local Host Server</span></span>  
  
1. <span data-ttu-id="44c43-118">コンポーネント サービスを開きます。</span><span class="sxs-lookup"><span data-stu-id="44c43-118">Open Component Services:</span></span>  
  
    <span data-ttu-id="44c43-119">**[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]**:Windows の選択 ボタン、および種類**コンポーネント サービス**します。</span><span class="sxs-lookup"><span data-stu-id="44c43-119">**[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]** : Select the Windows button, and type **Component Services**.</span></span> <span data-ttu-id="44c43-120">結果ウィンドウで次のように選択します。**コンポーネント サービス**します。</span><span class="sxs-lookup"><span data-stu-id="44c43-120">In the Results window, select **Component Services**.</span></span>  
  
    <span data-ttu-id="44c43-121">**Windows 8.1**:Windows の選択 ボタン、および種類**管理ツール**します。</span><span class="sxs-lookup"><span data-stu-id="44c43-121">**Windows 8.1**: Select the Windows button, and type **Administrative Tools**.</span></span> <span data-ttu-id="44c43-122">[検索] ウィンドウで、次のように選択します。**設定**します。</span><span class="sxs-lookup"><span data-stu-id="44c43-122">In the Search window, select **Settings**.</span></span> <span data-ttu-id="44c43-123">結果ウィンドウで次のようにクリックします。**管理ツール**します。</span><span class="sxs-lookup"><span data-stu-id="44c43-123">In the Results window, click **Administrative Tools**.</span></span> <span data-ttu-id="44c43-124">ダブルクリック**コンポーネント サービス**します。</span><span class="sxs-lookup"><span data-stu-id="44c43-124">Double-click **Component Services**.</span></span>  
  
    <span data-ttu-id="44c43-125">**Windows 7 SP1**:**[スタート]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="44c43-125">**Windows 7 SP1**: Select **Start**.</span></span> <span data-ttu-id="44c43-126">**検索**テキスト ボックスに「**コンポーネント サービス** をクリックして開きます。</span><span class="sxs-lookup"><span data-stu-id="44c43-126">In the **Search** text box, type **Component Services**, and click it to open.</span></span>  
  
2. <span data-ttu-id="44c43-127">コンソール ツリーで、**[コンポーネント サービス]**、**[コンピューター]**、**[マイ コンピューター]**、**[分散トランザクション コーディネーター]** の順に展開し、**[ローカル DTC]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="44c43-127">In the console tree, expand **Component Services**, expand **Computers**, expand **My Computer**, expand **Distributed Transaction Coordinator**, and then click **Local DTC**.</span></span>  
  
3. <span data-ttu-id="44c43-128">右クリック**ローカル DTC**選択**プロパティ**を開く、**ローカル DTC のプロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="44c43-128">Right-click **Local DTC** and select **Properties** to open the **Local DTC Properties**.</span></span>  
  
4. <span data-ttu-id="44c43-129">**[セキュリティ]** タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="44c43-129">Select the **Security** tab.</span></span>  
  
5. <span data-ttu-id="44c43-130">次のオプションがオンになってを確認します。</span><span class="sxs-lookup"><span data-stu-id="44c43-130">Confirm the following options are checked:</span></span>  
  
   - <span data-ttu-id="44c43-131">**ネットワーク DTC アクセス**</span><span class="sxs-lookup"><span data-stu-id="44c43-131">**Network DTC Access**</span></span>  
  
   - <span data-ttu-id="44c43-132">**受信を許可する**</span><span class="sxs-lookup"><span data-stu-id="44c43-132">**Allow Inbound**</span></span>  
  
   - <span data-ttu-id="44c43-133">**送信を許可する**</span><span class="sxs-lookup"><span data-stu-id="44c43-133">**Allow Outbound**</span></span>  
  
   - <span data-ttu-id="44c43-134">**認証を必要としない**</span><span class="sxs-lookup"><span data-stu-id="44c43-134">**No Authentication Required**</span></span>  
  
     <span data-ttu-id="44c43-135">追加の設定が必要な場合、「[MSDTC を使用した問題のトラブルシューティング](../core/troubleshooting-problems-with-msdtc.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="44c43-135">For additional settings that may be needed, see [Troubleshooting Problems with MSDTC](../core/troubleshooting-problems-with-msdtc.md).</span></span>  
  
6. <span data-ttu-id="44c43-136">選択**OK**を閉じる、**ローカル DTC のプロパティ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="44c43-136">Select **OK** to close the **Local DTC Properties** dialog box.</span></span> <span data-ttu-id="44c43-137">求められた場合は、MSDTC サービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="44c43-137">Restart the MSDTC service if prompted.</span></span>  
  
7. <span data-ttu-id="44c43-138">**[コンポーネント サービス]** を閉じます。</span><span class="sxs-lookup"><span data-stu-id="44c43-138">Close **Component Services**.</span></span>  
  
##  <a name="BKMK_Firewall"></a> <span data-ttu-id="44c43-139">DTC を有効にするための Windows ファイアウォールを構成します。</span><span class="sxs-lookup"><span data-stu-id="44c43-139">Configure Windows Firewall to Enable DTC</span></span>  
  
1. <span data-ttu-id="44c43-140">開いている**Windows ファイアウォール**:</span><span class="sxs-lookup"><span data-stu-id="44c43-140">Open **Windows Firewall**:</span></span>  
  
    <span data-ttu-id="44c43-141">**[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]**:Windows をクリックします ボタン、および種類**Windows ファイアウォール**します。</span><span class="sxs-lookup"><span data-stu-id="44c43-141">**[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]** : Click the Windows button, and type **Windows Firewall**.</span></span> <span data-ttu-id="44c43-142">結果ウィンドウで次のようにクリックします。 **Windows ファイアウォール**します。</span><span class="sxs-lookup"><span data-stu-id="44c43-142">In the Results window, click **Windows Firewall**.</span></span>  
  
    <span data-ttu-id="44c43-143">**Windows 8.1**:Windows をクリックします ボタン、および種類**Windows ファイアウォール**します。</span><span class="sxs-lookup"><span data-stu-id="44c43-143">**Windows 8.1**: Click the Windows button, and type **Windows Firewall**.</span></span> <span data-ttu-id="44c43-144">[検索] ウィンドウで、次のようにクリックします。**設定**します。</span><span class="sxs-lookup"><span data-stu-id="44c43-144">In the Search window, click **Settings**.</span></span> <span data-ttu-id="44c43-145">結果ウィンドウで次のようにクリックします。 **Windows ファイアウォール**します。</span><span class="sxs-lookup"><span data-stu-id="44c43-145">In the Results window, click **Windows Firewall**.</span></span>  
  
    <span data-ttu-id="44c43-146">**Windows 7 SP1**:クリックして**開始**します。</span><span class="sxs-lookup"><span data-stu-id="44c43-146">**Windows 7 SP1**: Click **Start**.</span></span> <span data-ttu-id="44c43-147">**検索**テキスト ボックスに「 **Windows ファイアウォール** をクリックして開きます。</span><span class="sxs-lookup"><span data-stu-id="44c43-147">In the **Search** text box, type **Windows Firewall**, and click it to open.</span></span>  
  
2. <span data-ttu-id="44c43-148">クリックして**詳細設定** をクリック**受信の規則**します。</span><span class="sxs-lookup"><span data-stu-id="44c43-148">Click **Advanced Settings** and click **Inbound Rules**.</span></span>  
  
3. <span data-ttu-id="44c43-149">**受信の規則**ウィンドウで、右クリックして**分散トランザクション コーディネーター** \* (必要に応じて)、順にクリックします**規則の有効化**します。</span><span class="sxs-lookup"><span data-stu-id="44c43-149">In the **Inbound Rules** pane, right-click **Distributed Transaction Coordinator** \* (as appropriate), and then click **Enable Rule**.</span></span>  
  
4. <span data-ttu-id="44c43-150">クリックして**送信の規則**します。</span><span class="sxs-lookup"><span data-stu-id="44c43-150">Click **Outbound Rules**.</span></span>  
  
5. <span data-ttu-id="44c43-151">**送信の規則**ウィンドウで、右クリックして**分散トランザクション コーディネーター** \* (必要に応じて)、順にクリックします**規則の有効化**します。</span><span class="sxs-lookup"><span data-stu-id="44c43-151">In the **Outbound Rules** pane, right-click **Distributed Transaction Coordinator** \* (as appropriate), and then click **Enable Rule**.</span></span>  
  
6. <span data-ttu-id="44c43-152">**コントロール パネルの **、アイコンをリストに、ビューを変更しをダブルクリックします**管理ツール**します。</span><span class="sxs-lookup"><span data-stu-id="44c43-152">On the **Control Panel**, change the view to list by icons, and then double-click **Administrative Tools**.</span></span>  
  
7. <span data-ttu-id="44c43-153">ダブルクリック**サービス**します。</span><span class="sxs-lookup"><span data-stu-id="44c43-153">Double-click **Services**.</span></span>  
  
8. <span data-ttu-id="44c43-154">右クリックして**COM + システム アプリケーション**、 をクリックして**再起動**、し、サービスを再起動するまで待ちます。</span><span class="sxs-lookup"><span data-stu-id="44c43-154">Right-click **COM+ System Application**, click **Restart**, and wait for the service to restart.</span></span>  
  
9. <span data-ttu-id="44c43-155">**[分散トランザクション コーディネーター]** サービスを右クリックして再起動します。</span><span class="sxs-lookup"><span data-stu-id="44c43-155">Right-click and restart the **Distributed Transaction Coordinator** service.</span></span>  
  
10. <span data-ttu-id="44c43-156">**[SQL Server (MSSQLSERVER)]** サービスを右クリックして再起動します。</span><span class="sxs-lookup"><span data-stu-id="44c43-156">Right-click and restart the **SQL Server (MSSQLSERVER)** service.</span></span>  
  
11. <span data-ttu-id="44c43-157">**[サービス (ローカル)]** を閉じ、**[管理ツール]** を閉じます。</span><span class="sxs-lookup"><span data-stu-id="44c43-157">Close **Services (Local)**, and then close **Administrative Tools**.</span></span>  
  
##  <a name="BKMK_SQLAgent"></a> <span data-ttu-id="44c43-158">SQL エージェント ジョブを構成します。</span><span class="sxs-lookup"><span data-stu-id="44c43-158">Configure SQL Agent Jobs</span></span>  
  
|            <span data-ttu-id="44c43-159">[ジョブ]</span><span class="sxs-lookup"><span data-stu-id="44c43-159">Job</span></span>            |                                                                                                                                                                                                                                                                                                                     <span data-ttu-id="44c43-160">説明</span><span class="sxs-lookup"><span data-stu-id="44c43-160">Description</span></span>                                                                                                                                                                                                                                                                                                                     |                                                                                                                                                                                                 <span data-ttu-id="44c43-161">理由を構成します。</span><span class="sxs-lookup"><span data-stu-id="44c43-161">Why configure</span></span>                                                                                                                                                                                                  |
|---------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="44c43-162">**BizTalk Server をバックアップします。**</span><span class="sxs-lookup"><span data-stu-id="44c43-162">**Backup BizTalk Server**</span></span> |                                     <span data-ttu-id="44c43-163">この SQL エージェント ジョブのバックアップ、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベースとログ ファイル。</span><span class="sxs-lookup"><span data-stu-id="44c43-163">This SQL Agent job backs up the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases and the log files.</span></span> <span data-ttu-id="44c43-164">ジョブを構成するときは、頻度とファイルの場所などのパラメーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="44c43-164">When configuring the job, you determine parameters like frequency and file location.</span></span><br /><br /> <span data-ttu-id="44c43-165">次のリンクでは、SQL エージェント ジョブとそのパラメーターについて説明します。</span><span class="sxs-lookup"><span data-stu-id="44c43-165">The following links describe the SQL Agent job and its parameters:</span></span><br /><br /> <span data-ttu-id="44c43-166">[バックアップおよび BizTalk Server データベースを復元します。](http://msdn.microsoft.com/library/aa561125\(v=bts.80\).aspx)</span><span class="sxs-lookup"><span data-stu-id="44c43-166">[Backing Up and Restoring BizTalk Server Databases](http://msdn.microsoft.com/library/aa561125\(v=bts.80\).aspx)</span></span><br /><br /> <span data-ttu-id="44c43-167">[BizTalk Server のバックアップ ジョブを構成する方法](http://msdn.microsoft.com/library/aa546765\(v=bts.80\).aspx)</span><span class="sxs-lookup"><span data-stu-id="44c43-167">[How to Configure the Backup BizTalk Server Job](http://msdn.microsoft.com/library/aa546765\(v=bts.80\).aspx)</span></span>                                      | <span data-ttu-id="44c43-168">この SQL エージェント ジョブには、パフォーマンスを向上させることができます、トランザクション ログも切り捨てます。</span><span class="sxs-lookup"><span data-stu-id="44c43-168">This SQL Agent job also truncates the transaction logs, which helps improve performance.</span></span><br /><br /> <span data-ttu-id="44c43-169">**Backup BizTalk Server**ジョブが削除または古いなど、バックアップ ファイルを削除してされません。</span><span class="sxs-lookup"><span data-stu-id="44c43-169">The **Backup BizTalk Server** job does not remove or delete backup files, including older files.</span></span> <span data-ttu-id="44c43-170">バックアップ ファイルを削除するを参照してください["Backup BizTalk Server"ジョブ失敗時に、バックアップ ファイルは、Microsoft BizTalk Server データベース サーバーでの時間の経過と共に蓄積](http://support.microsoft.com/kb/982546)します。</span><span class="sxs-lookup"><span data-stu-id="44c43-170">To delete backup files, refer to [The "Backup BizTalk Server" job fails when backup files accumulate over time in the Microsoft BizTalk Server database server](http://support.microsoft.com/kb/982546).</span></span> |
| <span data-ttu-id="44c43-171">**DTA Purge and Archive**</span><span class="sxs-lookup"><span data-stu-id="44c43-171">**DTA Purge and Archive**</span></span> | <span data-ttu-id="44c43-172">この SQL エージェント ジョブの切り捨てし、アーカイブ、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]追跡データベース (BizTalkDTADb)。</span><span class="sxs-lookup"><span data-stu-id="44c43-172">This SQL Agent job truncates and archives the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Tracking database (BizTalkDTADb).</span></span> <span data-ttu-id="44c43-173">完了したインスタンスを保持する日数などのパラメーターを決定するジョブを構成するときに、すべてのデータを保持する日数。</span><span class="sxs-lookup"><span data-stu-id="44c43-173">When configuring the job, you determine parameters like how many days to keep completed instances and how many to days to keep all data.</span></span><br /><br /> <span data-ttu-id="44c43-174">次のリンクでは、SQL エージェント ジョブとそのパラメーターについて説明します。</span><span class="sxs-lookup"><span data-stu-id="44c43-174">The following links describe the SQL Agent job and its parameters:</span></span><br /><br /> <span data-ttu-id="44c43-175">[BizTalk 追跡データベースのアーカイブおよび削除](http://msdn.microsoft.com/library/aa560754\(v=bts.80\).aspx)</span><span class="sxs-lookup"><span data-stu-id="44c43-175">[Archiving and Purging the BizTalk Tracking Database](http://msdn.microsoft.com/library/aa560754\(v=bts.80\).aspx)</span></span><br /><br /> <span data-ttu-id="44c43-176">[構成の DTA Purge and Archive ジョブをする方法](http://msdn.microsoft.com/library/aa558715\(v=bts.80\).aspx)</span><span class="sxs-lookup"><span data-stu-id="44c43-176">[How to Configure the DTA Purge and Archive Job](http://msdn.microsoft.com/library/aa558715\(v=bts.80\).aspx)</span></span> |              <span data-ttu-id="44c43-177">この SQL エージェント ジョブは、追跡ホストの管理と追跡イベントを削除して、パフォーマンスを直接影響します。</span><span class="sxs-lookup"><span data-stu-id="44c43-177">This SQL Agent job directly impacts performance by maintaining the Tracking host and purging tracking events.</span></span><br /><br /> <span data-ttu-id="44c43-178">パフォーマンスに関するトピックは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="44c43-178">Performance topics include:</span></span><br /><br /> [<span data-ttu-id="44c43-179">保守および BizTalk Server データベースをトラブルシューティングする方法</span><span class="sxs-lookup"><span data-stu-id="44c43-179">How to maintain and troubleshoot BizTalk Server databases</span></span>](http://support.microsoft.com/kb/952555)<br /><br /> <span data-ttu-id="44c43-180">[追跡データベースのサイズに関するガイドライン](http://msdn.microsoft.com/library/aa559162\(v=bts.80\).aspx)</span><span class="sxs-lookup"><span data-stu-id="44c43-180">[Tracking Database Sizing Guidelines](http://msdn.microsoft.com/library/aa559162\(v=bts.80\).aspx)</span></span>              |
  
 <span data-ttu-id="44c43-181">**その他**</span><span class="sxs-lookup"><span data-stu-id="44c43-181">**Additional**</span></span>  
  
- <span data-ttu-id="44c43-182">ときに[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]がインストールされている場合、いくつかの SQL エージェント ジョブが自動的に作成、ように、次のリンクで説明されています。</span><span class="sxs-lookup"><span data-stu-id="44c43-182">When [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is installed, several SQL Agent jobs are automatically created, as described in the following links:</span></span>  
  
   [<span data-ttu-id="44c43-183">BizTalk Server で SQL Server エージェント ジョブの説明</span><span class="sxs-lookup"><span data-stu-id="44c43-183">Description of the SQL Server Agent jobs in BizTalk Server</span></span>](http://support.microsoft.com/kb/919776)  
  
   <span data-ttu-id="44c43-184">[データベース構造とジョブ](http://msdn.microsoft.com/library/aa561960\(v=bts.80\).aspx)</span><span class="sxs-lookup"><span data-stu-id="44c43-184">[Database Structure and Jobs](http://msdn.microsoft.com/library/aa561960\(v=bts.80\).aspx)</span></span>  
  
##  <a name="BKMK_InstallCU"></a> <span data-ttu-id="44c43-185">累積的な更新プログラムをインストールします。</span><span class="sxs-lookup"><span data-stu-id="44c43-185">Install Cumulative Updates</span></span>  
 <span data-ttu-id="44c43-186">インストールした後[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、いずれかがインストール[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Windows 更新プログラムに累積的更新プログラムが一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="44c43-186">After you install [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], install any [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] cumulative updates listed in Windows Update.</span></span> <span data-ttu-id="44c43-187">利用可能なサービス パックおよび累積的な更新プログラムの一覧は、[KB 文書 2555976](http://support.microsoft.com/kb/2555976) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="44c43-187">[KB article 2555976](http://support.microsoft.com/kb/2555976) lists available service packs and cumulative updates.</span></span>  
  
## <a name="next"></a><span data-ttu-id="44c43-188">Next</span><span class="sxs-lookup"><span data-stu-id="44c43-188">Next</span></span>  
[<span data-ttu-id="44c43-189">BizTalk Server の構成</span><span class="sxs-lookup"><span data-stu-id="44c43-189">Configure BizTalk Server</span></span>](../install-and-config-guides/configure-biztalk-server.md)
  
## <a name="see-also"></a><span data-ttu-id="44c43-190">参照</span><span class="sxs-lookup"><span data-stu-id="44c43-190">See Also</span></span>  
 [<span data-ttu-id="44c43-191">付録 a:サイレント インストール</span><span class="sxs-lookup"><span data-stu-id="44c43-191">Appendix A: Silent Installation</span></span>](../install-and-config-guides/appendix-a-silent-installation.md) 
 
[<span data-ttu-id="44c43-192">付録 b:Microsoft SharePoint アダプターをインストールします。</span><span class="sxs-lookup"><span data-stu-id="44c43-192">Appendix B: Install the Microsoft SharePoint Adapter</span></span>](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md)  

[<span data-ttu-id="44c43-193">付録 c:再頒布可能 CAB ファイル</span><span class="sxs-lookup"><span data-stu-id="44c43-193">Appendix C: Redistributable CAB Files</span></span>](../install-and-config-guides/appendix-c-redistributable-cab-files.md)  

[<span data-ttu-id="44c43-194">付録 d:SMTP サーバーを作成します。</span><span class="sxs-lookup"><span data-stu-id="44c43-194">Appendix D: Create the SMTP Server</span></span>](../install-and-config-guides/appendix-d-create-the-smtp-server.md)

[<span data-ttu-id="44c43-195">アンインストールし、それを削除する BizTalk Server の構成を解除</span><span class="sxs-lookup"><span data-stu-id="44c43-195">Uninstall and unconfigure BizTalk Server to remove it</span></span>](../install-and-config-guides/uninstall-and-unconfigure-biztalk-server-to-remove-it.md)
