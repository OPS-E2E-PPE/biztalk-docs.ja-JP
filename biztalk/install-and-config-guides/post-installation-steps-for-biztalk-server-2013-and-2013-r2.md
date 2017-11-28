---
title: "BizTalk Server 2013 および 2013 R2 のインストール後の手順 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c3b47843-9da5-4144-8b84-135494b8ab43
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b86d8c4c1e1a22dad349c2cc8c2be5ca4b206b2c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="post-installation-steps-for-biztalk-server-2013-and-2013-r2"></a><span data-ttu-id="3403d-102">BizTalk Server 2013 および 2003 R2 のインストール後の手順</span><span class="sxs-lookup"><span data-stu-id="3403d-102">Post-installation Steps for BizTalk Server 2013 and 2013 R2</span></span>
  
##  <span data-ttu-id="3403d-103"><a name="BKMK_NamedPipes"></a> TCP/IP と名前付きパイプの有効化</span><span class="sxs-lookup"><span data-stu-id="3403d-103"><a name="BKMK_NamedPipes"></a> Enable TCP/IP and Named Pipes</span></span>  
  
1.  <span data-ttu-id="3403d-104">**[SQL Server 構成マネージャー]** を開きます。</span><span class="sxs-lookup"><span data-stu-id="3403d-104">Open **SQL Server Configuration Manager**.</span></span>  
  
2.  <span data-ttu-id="3403d-105">**[SQL Server ネットワークの構成]** を展開し、**[MSSQLSERVER のプロトコル]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3403d-105">Expand **SQL Server Network Configuration**, and select **Protocols for MSSQLSERVER**.</span></span>  
  
4.  <span data-ttu-id="3403d-106">**[TCP/IP]** と **[名前付きパイプ]** の両方が有効であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="3403d-106">Verify that both **TCP/IP** and **Named Pipes** are enabled.</span></span> <span data-ttu-id="3403d-107">有効である場合は、次の手順に進みます。</span><span class="sxs-lookup"><span data-stu-id="3403d-107">If enabled, proceed to the next step.</span></span>  
  
     <span data-ttu-id="3403d-108">有効でない場合:</span><span class="sxs-lookup"><span data-stu-id="3403d-108">If not enabled:</span></span>  
  
    -   <span data-ttu-id="3403d-109">プロトコルを右クリックして **[有効]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3403d-109">Right-click the protocol, and then click **Enable**.</span></span>  
  
    -   <span data-ttu-id="3403d-110">他方のプロトコルも、有効になっていない場合は同じ手順を実行して有効にします。</span><span class="sxs-lookup"><span data-stu-id="3403d-110">Repeat to enable the other protocol if necessary.</span></span>  
  
    -   <span data-ttu-id="3403d-111">左側のウィンドウで、**[SQL Server のサービス]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3403d-111">In the left-hand pane, click **SQL Server Services**.</span></span>  
  
    -   <span data-ttu-id="3403d-112">右側のウィンドウで、**[SQL Server (MSSQLSERVER)]** を右クリックして **[停止]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3403d-112">In the right-hand pane, right-click **SQL Server (MSSQLSERVER)**, and click **Stop**.</span></span>  
  
    -   <span data-ttu-id="3403d-113">サービスが停止したら、**[SQL Server (MSSQLSERVER)]** を右クリックして **[開始]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3403d-113">When the service has stopped, right-click **SQL Server (MSSQLSERVER)**, and click **Start**.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="3403d-114">[!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)] を使用している場合は、**NS$BAMAlerts** サービスが停止する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3403d-114">If you are using [!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)], the **NS$BAMAlerts** service may be stopped.</span></span> <span data-ttu-id="3403d-115">サービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="3403d-115">Restart the service.</span></span>  
  
5.  <span data-ttu-id="3403d-116">**構成マネージャー**を閉じます。</span><span class="sxs-lookup"><span data-stu-id="3403d-116">Close the **Configuration Manager**.</span></span>  
  
##  <span data-ttu-id="3403d-117"><a name="BKMK_DTC"></a> ローカル ホスト サーバー上の DTC の有効化</span><span class="sxs-lookup"><span data-stu-id="3403d-117"><a name="BKMK_DTC"></a> Enable DTC on the Local Host Server</span></span>  
  
1.  <span data-ttu-id="3403d-118">[コンポーネント サービス] を開きます。</span><span class="sxs-lookup"><span data-stu-id="3403d-118">Open Component Services:</span></span>  
  
     <span data-ttu-id="3403d-119">**[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]**: Windows ボタンを選択して「**コンポーネント サービス**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="3403d-119">**[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]** : Select the Windows button, and type **Component Services**.</span></span> <span data-ttu-id="3403d-120">[検索結果] ウィンドウで、[**コンポーネント サービス**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3403d-120">In the Results window, select **Component Services**.</span></span>  
  
     <span data-ttu-id="3403d-121">**Windows 8.1**: Windows ボタンを選択して「**管理ツール**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="3403d-121">**Windows 8.1**: Select the Windows button, and type **Administrative Tools**.</span></span> <span data-ttu-id="3403d-122">[検索] ウィンドウで、[**設定**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3403d-122">In the Search window, select **Settings**.</span></span> <span data-ttu-id="3403d-123">[検索結果] ウィンドウで、**[管理ツール]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3403d-123">In the Results window, click **Administrative Tools**.</span></span> <span data-ttu-id="3403d-124">**[コンポーネント サービス]** をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="3403d-124">Double-click **Component Services**.</span></span>  
  
     <span data-ttu-id="3403d-125">**Windows 7 SP1**: **[スタート]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3403d-125">**Windows 7 SP1**: Select **Start**.</span></span> <span data-ttu-id="3403d-126">**[検索]** テキスト ボックスに「**コンポーネント サービス**」と入力し、クリックして開きます。</span><span class="sxs-lookup"><span data-stu-id="3403d-126">In the **Search** text box, type **Component Services**, and click it to open.</span></span>  
  
2.  <span data-ttu-id="3403d-127">コンソール ツリーで、**[コンポーネント サービス]**、**[コンピューター]**、**[マイ コンピューター]**、**[分散トランザクション コーディネーター]** の順に展開し、**[ローカル DTC]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3403d-127">In the console tree, expand **Component Services**, expand **Computers**, expand **My Computer**, expand **Distributed Transaction Coordinator**, and then click **Local DTC**.</span></span>  
  
3.  <span data-ttu-id="3403d-128">**[ローカル DTC]** を右クリックし、**[プロパティ]** を選択して、**[ローカル DTC のプロパティ]** を開きます。</span><span class="sxs-lookup"><span data-stu-id="3403d-128">Right-click **Local DTC** and select **Properties** to open the **Local DTC Properties**.</span></span>  
  
4.  <span data-ttu-id="3403d-129">**[セキュリティ]** タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="3403d-129">Select the **Security** tab.</span></span>  
  
5.  <span data-ttu-id="3403d-130">次のオプションがオンになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="3403d-130">Confirm the following options are checked:</span></span>  
  
    -   <span data-ttu-id="3403d-131">**ネットワーク DTC アクセス**</span><span class="sxs-lookup"><span data-stu-id="3403d-131">**Network DTC Access**</span></span>  
  
    -   <span data-ttu-id="3403d-132">**受信を許可する**</span><span class="sxs-lookup"><span data-stu-id="3403d-132">**Allow Inbound**</span></span>  
  
    -   <span data-ttu-id="3403d-133">**送信を許可する**</span><span class="sxs-lookup"><span data-stu-id="3403d-133">**Allow Outbound**</span></span>  
  
    -   <span data-ttu-id="3403d-134">**認証を必要としない**</span><span class="sxs-lookup"><span data-stu-id="3403d-134">**No Authentication Required**</span></span>  
  
     <span data-ttu-id="3403d-135">追加の設定が必要な場合、「[MSDTC を使用した問題のトラブルシューティング](../core/troubleshooting-problems-with-msdtc.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3403d-135">For additional settings that may be needed, see [Troubleshooting Problems with MSDTC](../core/troubleshooting-problems-with-msdtc.md).</span></span>  
  
6.  <span data-ttu-id="3403d-136">**[OK]** を選択して **[ローカル DTC のプロパティ]** ダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="3403d-136">Select **OK** to close the **Local DTC Properties** dialog box.</span></span> <span data-ttu-id="3403d-137">MSDTC サービスの再起動が求められたら再起動します。</span><span class="sxs-lookup"><span data-stu-id="3403d-137">Restart the MSDTC service if prompted.</span></span>  
  
7.  <span data-ttu-id="3403d-138">**[コンポーネント サービス]** を閉じます。</span><span class="sxs-lookup"><span data-stu-id="3403d-138">Close **Component Services**.</span></span>  
  
##  <span data-ttu-id="3403d-139"><a name="BKMK_Firewall"></a> Windows ファイアウォールで DTC を有効にする</span><span class="sxs-lookup"><span data-stu-id="3403d-139"><a name="BKMK_Firewall"></a> Configure Windows Firewall to Enable DTC</span></span>  
  
1.  <span data-ttu-id="3403d-140">**[Windows ファイアウォール]** を開きます。</span><span class="sxs-lookup"><span data-stu-id="3403d-140">Open **Windows Firewall**:</span></span>  
  
     <span data-ttu-id="3403d-141">**[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]** : キーボードの Windows ボタンをクリックして「**Windows ファイアウォール**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="3403d-141">**[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]** : Click the Windows button, and type **Windows Firewall**.</span></span> <span data-ttu-id="3403d-142">[検索結果] ウィンドウで、**[Windows ファイアウォール]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3403d-142">In the Results window, click **Windows Firewall**.</span></span>  
  
     <span data-ttu-id="3403d-143">**Windows 8.1**: キーボードの Windows ボタンをクリックして「**Windows ファイアウォール**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="3403d-143">**Windows 8.1**: Click the Windows button, and type **Windows Firewall**.</span></span> <span data-ttu-id="3403d-144">[検索] ウィンドウで、**[設定]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3403d-144">In the Search window, click **Settings**.</span></span> <span data-ttu-id="3403d-145">[検索結果] ウィンドウで、**[Windows ファイアウォール]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3403d-145">In the Results window, click **Windows Firewall**.</span></span>  
  
     <span data-ttu-id="3403d-146">**Windows 7 SP1**: **[スタート]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3403d-146">**Windows 7 SP1**: Click **Start**.</span></span> <span data-ttu-id="3403d-147">**[検索]** テキスト ボックスに「**Windows ファイアウォール**」と入力し、クリックして開きます。</span><span class="sxs-lookup"><span data-stu-id="3403d-147">In the **Search** text box, type **Windows Firewall**, and click it to open.</span></span>  
  
2.  <span data-ttu-id="3403d-148">**[詳細設定]** をクリックして、**[受信の規則]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3403d-148">Click **Advanced Settings** and click **Inbound Rules**.</span></span>  
  
3.  <span data-ttu-id="3403d-149">**[受信の規則]** ウィンドウで、**[分散トランザクション コーディネーター]** \* を右クリックし (必要に応じて)、**[規則の有効化]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3403d-149">In the **Inbound Rules** pane, right-click **Distributed Transaction Coordinator** \* (as appropriate), and then click **Enable Rule**.</span></span>  
  
4.  <span data-ttu-id="3403d-150">**[送信の規則]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3403d-150">Click **Outbound Rules**.</span></span>  
  
5.  <span data-ttu-id="3403d-151">**[送信の規則]** ペインで、**[分散トランザクション コーディネーター]** \* を右クリックして (必要な場合)、**[規則の有効化]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3403d-151">In the **Outbound Rules** pane, right-click **Distributed Transaction Coordinator** \* (as appropriate), and then click **Enable Rule**.</span></span>  
  
6.  <span data-ttu-id="3403d-152">**[コントロール パネル]** で、ビューをアイコンのリストに変更し、**[管理ツール]** をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="3403d-152">On the **Control Panel**, change the view to list by icons, and then double-click **Administrative Tools**.</span></span>  
  
7.  <span data-ttu-id="3403d-153">**[サービス]** をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="3403d-153">Double-click **Services**.</span></span>  
  
8.  <span data-ttu-id="3403d-154">**[COM+ システム アプリケーション]** を右クリックし、**[再起動]** をクリックしてサービスが再起動するのを待ちます。</span><span class="sxs-lookup"><span data-stu-id="3403d-154">Right-click **COM+ System Application**, click **Restart**, and wait for the service to restart.</span></span>  
  
9. <span data-ttu-id="3403d-155">**[分散トランザクション コーディネーター]** サービスを右クリックして再起動します。</span><span class="sxs-lookup"><span data-stu-id="3403d-155">Right-click and restart the **Distributed Transaction Coordinator** service.</span></span>  
  
10. <span data-ttu-id="3403d-156">**[SQL Server (MSSQLSERVER)]** サービスを右クリックして再起動します。</span><span class="sxs-lookup"><span data-stu-id="3403d-156">Right-click and restart the **SQL Server (MSSQLSERVER)** service.</span></span>  
  
11. <span data-ttu-id="3403d-157">**[サービス (ローカル)]** を閉じ、**[管理ツール]** を閉じます。</span><span class="sxs-lookup"><span data-stu-id="3403d-157">Close **Services (Local)**, and then close **Administrative Tools**.</span></span>  
  
##  <span data-ttu-id="3403d-158"><a name="BKMK_SQLAgent"></a> SQL エージェント ジョブを構成する</span><span class="sxs-lookup"><span data-stu-id="3403d-158"><a name="BKMK_SQLAgent"></a> Configure SQL Agent Jobs</span></span>  
  
|<span data-ttu-id="3403d-159">[ジョブ]</span><span class="sxs-lookup"><span data-stu-id="3403d-159">Job</span></span>|<span data-ttu-id="3403d-160">説明</span><span class="sxs-lookup"><span data-stu-id="3403d-160">Description</span></span>|<span data-ttu-id="3403d-161">構成の理由</span><span class="sxs-lookup"><span data-stu-id="3403d-161">Why configure</span></span>|  
|---------|-----------------|-------------------|  
|<span data-ttu-id="3403d-162">**Backup BizTalk Server**</span><span class="sxs-lookup"><span data-stu-id="3403d-162">**Backup BizTalk Server**</span></span>|<span data-ttu-id="3403d-163">この SQL エージェント ジョブでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] データベースとログ ファイルのバックアップを行います。</span><span class="sxs-lookup"><span data-stu-id="3403d-163">This SQL Agent job backs up the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases and the log files.</span></span> <span data-ttu-id="3403d-164">このジョブを構成するときに、回数やファイルの場所などのパラメーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="3403d-164">When configuring the job, you determine parameters like frequency and file location.</span></span><br /><br /> <span data-ttu-id="3403d-165">以下のリンクで、SQL エージェント ジョブとそのパラメーターについて説明しています。</span><span class="sxs-lookup"><span data-stu-id="3403d-165">The following links describe the SQL Agent job and its parameters:</span></span><br /><br /> <span data-ttu-id="3403d-166">[BizTalk Server データベースのバックアップと復元](http://msdn.microsoft.com/library/aa561125\(v=bts.80\).aspx)</span><span class="sxs-lookup"><span data-stu-id="3403d-166">[Backing Up and Restoring BizTalk Server Databases](http://msdn.microsoft.com/library/aa561125\(v=bts.80\).aspx)</span></span><br /><br /> <span data-ttu-id="3403d-167">[BizTalk Server のバックアップ ジョブを構成する方法](http://msdn.microsoft.com/library/aa546765\(v=bts.80\).aspx)</span><span class="sxs-lookup"><span data-stu-id="3403d-167">[How to Configure the Backup BizTalk Server Job](http://msdn.microsoft.com/library/aa546765\(v=bts.80\).aspx)</span></span>|<span data-ttu-id="3403d-168">この SQL エージェント ジョブでは、トランザクション ログの切り捨ても行います。これによりパフォーマンスが向上します。</span><span class="sxs-lookup"><span data-stu-id="3403d-168">This SQL Agent job also truncates the transaction logs, which helps improve performance.</span></span><br /><br /> <span data-ttu-id="3403d-169">**Backup BizTalk Server** ジョブでは、バックアップ ファイルは削除されません。古いファイルも削除されません。</span><span class="sxs-lookup"><span data-stu-id="3403d-169">The **Backup BizTalk Server** job does not remove or delete backup files, including older files.</span></span> <span data-ttu-id="3403d-170">バックアップ ファイルを削除する方法については、「[Microsoft BizTalk Server データベース サーバーでバックアップ ファイルが長期的に蓄積すると、"Backup BizTalk Server" ジョブが失敗する](http://support.microsoft.com/kb/982546)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3403d-170">To delete backup files, refer to [The "Backup BizTalk Server" job fails when backup files accumulate over time in the Microsoft BizTalk Server database server](http://support.microsoft.com/kb/982546).</span></span>|  
|<span data-ttu-id="3403d-171">**DTA Purge and Archive**</span><span class="sxs-lookup"><span data-stu-id="3403d-171">**DTA Purge and Archive**</span></span>|<span data-ttu-id="3403d-172">この SQL エージェント ジョブでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 追跡データベース (BizTalkDTADb) の切り捨てとアーカイブを行います。</span><span class="sxs-lookup"><span data-stu-id="3403d-172">This SQL Agent job truncates and archives the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Tracking database (BizTalkDTADb).</span></span> <span data-ttu-id="3403d-173">このジョブを構成するときに、完了したインスタンスを保持する日数や全データを保持する日数などのパラメーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="3403d-173">When configuring the job, you determine parameters like how many days to keep completed instances and how many to days to keep all data.</span></span><br /><br /> <span data-ttu-id="3403d-174">以下のリンクで、SQL エージェント ジョブとそのパラメーターについて説明しています。</span><span class="sxs-lookup"><span data-stu-id="3403d-174">The following links describe the SQL Agent job and its parameters:</span></span><br /><br /> <span data-ttu-id="3403d-175">[BizTalk 追跡データベースのアーカイブおよび削除](http://msdn.microsoft.com/library/aa560754\(v=bts.80\).aspx)</span><span class="sxs-lookup"><span data-stu-id="3403d-175">[Archiving and Purging the BizTalk Tracking Database](http://msdn.microsoft.com/library/aa560754\(v=bts.80\).aspx)</span></span><br /><br /> <span data-ttu-id="3403d-176">[DTA Purge and Archive ジョブを構成する方法](http://msdn.microsoft.com/library/aa558715\(v=bts.80\).aspx)</span><span class="sxs-lookup"><span data-stu-id="3403d-176">[How to Configure the DTA Purge and Archive Job](http://msdn.microsoft.com/library/aa558715\(v=bts.80\).aspx)</span></span>|<span data-ttu-id="3403d-177">この SQL エージェント ジョブは、追跡ホストを維持し、追跡イベントを削除することで、パフォーマンスに直接影響を及ぼします。</span><span class="sxs-lookup"><span data-stu-id="3403d-177">This SQL Agent job directly impacts performance by maintaining the Tracking host and purging tracking events.</span></span><br /><br /> <span data-ttu-id="3403d-178">次のパフォーマンスに関するトピックがあります。</span><span class="sxs-lookup"><span data-stu-id="3403d-178">Performance topics include:</span></span><br /><br /> [<span data-ttu-id="3403d-179">BizTalk Server データベースのメンテナンスとトラブルシューティングの方法</span><span class="sxs-lookup"><span data-stu-id="3403d-179">How to maintain and troubleshoot BizTalk Server databases</span></span>](http://support.microsoft.com/kb/952555)<br /><br /> <span data-ttu-id="3403d-180">[追跡データベースのサイズに関するガイドライン](http://msdn.microsoft.com/library/aa559162\(v=bts.80\).aspx)</span><span class="sxs-lookup"><span data-stu-id="3403d-180">[Tracking Database Sizing Guidelines](http://msdn.microsoft.com/library/aa559162\(v=bts.80\).aspx)</span></span>|  
  
 <span data-ttu-id="3403d-181">**追加情報**</span><span class="sxs-lookup"><span data-stu-id="3403d-181">**Additional**</span></span>  
  
-   <span data-ttu-id="3403d-182">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] がインストールされると、次のリンクで説明するように、複数の SQL エージェント ジョブが自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="3403d-182">When [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is installed, several SQL Agent jobs are automatically created, as described in the following links:</span></span>  
  
     [<span data-ttu-id="3403d-183">BizTalk Server での SQL Server エージェント ジョブの説明</span><span class="sxs-lookup"><span data-stu-id="3403d-183">Description of the SQL Server Agent jobs in BizTalk Server</span></span>](http://support.microsoft.com/kb/919776)  
  
     <span data-ttu-id="3403d-184">[データベース構造とジョブ](http://msdn.microsoft.com/library/aa561960\(v=bts.80\).aspx)</span><span class="sxs-lookup"><span data-stu-id="3403d-184">[Database Structure and Jobs](http://msdn.microsoft.com/library/aa561960\(v=bts.80\).aspx)</span></span>  
  
##  <span data-ttu-id="3403d-185"><a name="BKMK_InstallCU"></a> 累積的な更新プログラムのインストール</span><span class="sxs-lookup"><span data-stu-id="3403d-185"><a name="BKMK_InstallCU"></a> Install Cumulative Updates</span></span>  
 <span data-ttu-id="3403d-186">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] をインストールした後、Windows Update にあるすべての [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の累積的な更新プログラムをインストールします。</span><span class="sxs-lookup"><span data-stu-id="3403d-186">After you install [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], install any [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] cumulative updates listed in Windows Update.</span></span> <span data-ttu-id="3403d-187">利用可能なサービス パックおよび累積的な更新プログラムの一覧は、[KB 文書 2555976](http://support.microsoft.com/kb/2555976) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="3403d-187">[KB article 2555976](http://support.microsoft.com/kb/2555976) lists available service packs and cumulative updates.</span></span>  
  
## <a name="next"></a><span data-ttu-id="3403d-188">Next</span><span class="sxs-lookup"><span data-stu-id="3403d-188">Next</span></span>  
[<span data-ttu-id="3403d-189">BizTalk Server の構成</span><span class="sxs-lookup"><span data-stu-id="3403d-189">Configure BizTalk Server</span></span>](../install-and-config-guides/configure-biztalk-server.md)
  
## <a name="see-also"></a><span data-ttu-id="3403d-190">参照</span><span class="sxs-lookup"><span data-stu-id="3403d-190">See Also</span></span>  
 [<span data-ttu-id="3403d-191">付録 A: サイレント インストール</span><span class="sxs-lookup"><span data-stu-id="3403d-191">Appendix A: Silent Installation</span></span>](../install-and-config-guides/appendix-a-silent-installation.md) 
 
[<span data-ttu-id="3403d-192">付録 B: Microsoft SharePoint アダプターのインストール</span><span class="sxs-lookup"><span data-stu-id="3403d-192">Appendix B: Install the Microsoft SharePoint Adapter</span></span>](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md)  

[<span data-ttu-id="3403d-193">付録 C: 再配布可能な CAB ファイル</span><span class="sxs-lookup"><span data-stu-id="3403d-193">Appendix C: Redistributable CAB Files</span></span>](../install-and-config-guides/appendix-c-redistributable-cab-files.md)  

[<span data-ttu-id="3403d-194">付録 D: SMTP サーバーの作成</span><span class="sxs-lookup"><span data-stu-id="3403d-194">Appendix D: Create the SMTP Server</span></span>](../install-and-config-guides/appendix-d-create-the-smtp-server.md)

[<span data-ttu-id="3403d-195">BizTalk Server の削除 (アンインストールおよび構成の解除)</span><span class="sxs-lookup"><span data-stu-id="3403d-195">Uninstall and unconfigure BizTalk Server to remove it</span></span>](../install-and-config-guides/uninstall-and-unconfigure-biztalk-server-to-remove-it.md)
