---
title: "インストールの既知の問題 |Microsoft ドキュメント"
description: "既知の問題と一般的な問題と解決策をインストールすると、BizTalk Server の構成"
ms.custom: 
ms.date: 11/30/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e4d0e707-6b9e-49e1-9f17-19b3bac1229e
caps.latest.revision: "27"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 90217a4e80df6f017b451dd7c40f6a1dfe3898ac
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="troubleshoot-biztalk-server-setup"></a><span data-ttu-id="1a737-103">BizTalk Server のセットアップをトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="1a737-103">Troubleshoot BizTalk Server Setup</span></span>

## <a name="introduction"></a><span data-ttu-id="1a737-104">概要</span><span class="sxs-lookup"><span data-stu-id="1a737-104">Introduction</span></span>  
 <span data-ttu-id="1a737-105">このトラブルシューティング ガイドには、BizTalk Server のインストール中に発生する可能性の最も一般的な問題と同様に既知の問題が一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="1a737-105">This Troubleshooting Guide lists  known issues as well as the most common problems you may encounter while installing BizTalk Server.</span></span> <span data-ttu-id="1a737-106">このガイドでは、Windows Server ロゴ プログラムの BizTalk Server の認定に関する詳細を提供するカスタム アクションも含まれます。</span><span class="sxs-lookup"><span data-stu-id="1a737-106">This guide also includes Custom actions which provides details about BizTalk Server certification for the Windows Server logo program.</span></span>  <span data-ttu-id="1a737-107">BizTalk Server セットアップ操作時に実行することが可能なカスタム動作の一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="1a737-107">It provides you a list of custom actions that might be performed during BizTalk Server Setup operation.</span></span>  
  
## <a name="review-install-steps"></a><span data-ttu-id="1a737-108">インストール手順を確認します。</span><span class="sxs-lookup"><span data-stu-id="1a737-108">Review install steps</span></span>  
<span data-ttu-id="1a737-109">BizTalk Server のセットアップに関する問題の大半は、BizTalk Server をインストールする前に BizTalk Server コンピューターを正しく準備していなかったか、以前にインストールした BizTalk Server が完全にアンインストールされていない状態で新しいインストールを実行したことが原因です。</span><span class="sxs-lookup"><span data-stu-id="1a737-109">The majority of BizTalk Server setup problems occur because the BizTalk Server computer was not properly prepared before BizTalk Server was installed, or a previous installation of BizTalk Server was not fully uninstalled before a new installation was attempted.</span></span>  
  
<span data-ttu-id="1a737-110">2 つのチェックリスト、下のコンピューターが BizTalk Server をサポートするために正しく構成されていることを確認する、BizTalk Server インストール ガイドで検索することもできます。 これを確認してください。</span><span class="sxs-lookup"><span data-stu-id="1a737-110">Review the two checklists below, which you can also find in the BizTalk Server Installation Guides, to ensure that your computer(s) are properly configured to support BizTalk Server.</span></span> <span data-ttu-id="1a737-111">この情報を確認した後もセットアップが正常に完了しない場合は、このドキュメントの残りの部分に示すトラブルシューティングのヒントを参考にしてください。</span><span class="sxs-lookup"><span data-stu-id="1a737-111">If, after reviewing this information, your setup still does not succeed, the troubleshooting tips in the rest of this document may be useful.</span></span>  
  
1. <span data-ttu-id="1a737-112">前提条件のソフトウェアとプログラムをインストールします。</span><span class="sxs-lookup"><span data-stu-id="1a737-112">Install prerequisite software and programs:</span></span>

    * [<span data-ttu-id="1a737-113">BizTalk Server 2016</span><span class="sxs-lookup"><span data-stu-id="1a737-113">BizTalk Server 2016</span></span>](set-up-and-install-prerequisites-for-biztalk-server-2016.md)
    * [<span data-ttu-id="1a737-114">BizTalk Server 2013 R2 & 2013</span><span class="sxs-lookup"><span data-stu-id="1a737-114">BizTalk Server 2013 R2 & 2013</span></span>](prepare-your-computer-for-installation.md)

2. <span data-ttu-id="1a737-115">インストールし、BizTalk Server を構成します。</span><span class="sxs-lookup"><span data-stu-id="1a737-115">Install and configure BizTalk Server:</span></span>  

    1. <span data-ttu-id="1a737-116">BizTalk Server のインストール: [BizTalk 2016](install-biztalk-server-2016.md) 、 [BizTalk 2013 R2/2013](install-biztalk-server-2013-and-2013-r2.md)</span><span class="sxs-lookup"><span data-stu-id="1a737-116">Install BizTalk Server: [BizTalk 2016](install-biztalk-server-2016.md) , [BizTalk 2013 R2 / 2013](install-biztalk-server-2013-and-2013-r2.md)</span></span>  
    2. <span data-ttu-id="1a737-117">[構成](configure-biztalk-server.md)BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="1a737-117">[Configure](configure-biztalk-server.md) BizTalk Server</span></span>
    3. [<span data-ttu-id="1a737-118">インストール後の構成手順</span><span class="sxs-lookup"><span data-stu-id="1a737-118">Post-configuration steps</span></span>](post-configuration-steps-to-optimize-your-environment.md)
  
## <a name="some-edias2-artifacts-are-still-active-after-unconfiguring"></a><span data-ttu-id="1a737-119">一部の edi/as2 アイテムが構成解除した後アクティブな</span><span class="sxs-lookup"><span data-stu-id="1a737-119">Some EDI/AS2 artifacts are still active after unconfiguring</span></span>  
  
<span data-ttu-id="1a737-120">**問題**</span><span class="sxs-lookup"><span data-stu-id="1a737-120">**Problem**</span></span>  
 <span data-ttu-id="1a737-121">後は、BizTalk Server EDI に関連する一部の BizTalk Server アイテムの BizTalk edi/as2 機能の構成を解除して、AS2 処理を BizTalk グループ構成のコンテキストでアクティブにすることができます。</span><span class="sxs-lookup"><span data-stu-id="1a737-121">After you unconfigure the BizTalk EDI/AS2 feature of BizTalk Server, some BizTalk Server artifacts related to EDI and AS2 processing will still be active in the context of the BizTalk group configuration.</span></span> <span data-ttu-id="1a737-122">これらのアイテムには、EDI パイプライン、AS2 パイプライン、バッチ処理オーケストレーションなどがあります。</span><span class="sxs-lookup"><span data-stu-id="1a737-122">These artifacts will include EDI and AS2 pipelines and the batching orchestration.</span></span> <span data-ttu-id="1a737-123">このため、BizTalk EDI/AS2 機能を構成解除した後でも、基本的な EDI 処理および AS2 処理を実行できます。</span><span class="sxs-lookup"><span data-stu-id="1a737-123">As a result, you will still be able to perform basic EDI and AS2 processing even after unconfiguring the BizTalk EDI/AS2 feature.</span></span>  
  
<span data-ttu-id="1a737-124">**原因** </span><span class="sxs-lookup"><span data-stu-id="1a737-124">**Cause** </span></span>  
 <span data-ttu-id="1a737-125">EDI 処理および AS2 処理に関連付けられているアクティブなポートがあります。</span><span class="sxs-lookup"><span data-stu-id="1a737-125">There are active ports associated with EDI and AS2 processing.</span></span> <span data-ttu-id="1a737-126">一部のアイテムは、これらのポートがアクティブである間は、引き続き機能します。</span><span class="sxs-lookup"><span data-stu-id="1a737-126">Some artifacts will continue to function while these ports remain active.</span></span>  
  
<span data-ttu-id="1a737-127">**解決策**</span><span class="sxs-lookup"><span data-stu-id="1a737-127">**Resolution**</span></span>  
 <span data-ttu-id="1a737-128">すべての EDI/AS2 アイテムを無効にするには、EDI 処理および AS2 処理に関連付けられているポートを無効化、停止、または削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1a737-128">To disable all EDI/AS2 artifacts, you should disable, stop, or delete the ports associated with EDI and AS2 processing.</span></span>  
  
## <a name="after-renaming-biztalk-or-sql-server-computer-the-configuration-wizard-fails"></a><span data-ttu-id="1a737-129">BizTalk または SQL Server コンピューターの名前を変更するには、後に、構成ウィザードが失敗します。</span><span class="sxs-lookup"><span data-stu-id="1a737-129">After renaming BizTalk or SQL Server computer, the Configuration Wizard fails</span></span>  
  
<span data-ttu-id="1a737-130">**問題**</span><span class="sxs-lookup"><span data-stu-id="1a737-130">**Problem**</span></span>  
 <span data-ttu-id="1a737-131">この問題は、次のようにさまざまなケースで生じることがあります。</span><span class="sxs-lookup"><span data-stu-id="1a737-131">This problem may manifest itself in several ways:</span></span>  
  
-   <span data-ttu-id="1a737-132">構成マネージャーは概要ページを正しく読み込むことができましたが、機能を構成しようとすると、画面に機能オプションが表示されません。</span><span class="sxs-lookup"><span data-stu-id="1a737-132">The configuration manager will load the Overview page correctly, but when attempting to configure a feature, the feature options do not display on the screen.</span></span>  
  
-   <span data-ttu-id="1a737-133">構成ウィザードが SQL Server に接続できません。</span><span class="sxs-lookup"><span data-stu-id="1a737-133">The configuration wizard cannot connect to the SQL Server.</span></span>  
  
-   <span data-ttu-id="1a737-134">すべての構成を解除しようとすると、一部の機能は解除されますが、すべての機能は解除されません。</span><span class="sxs-lookup"><span data-stu-id="1a737-134">Attempting to Unconfigure All unconfigures some features, but not all.</span></span>  
  
<span data-ttu-id="1a737-135">**原因** </span><span class="sxs-lookup"><span data-stu-id="1a737-135">**Cause** </span></span>  
 <span data-ttu-id="1a737-136">BizTalk Server の構成では、コンピューターのネットワーク名を格納します。</span><span class="sxs-lookup"><span data-stu-id="1a737-136">The BizTalk Server configuration stores the computer network name.</span></span> <span data-ttu-id="1a737-137">コンピューターの名前が変更されると、configuration manager との構成ウィザードを使うことにより、BizTalk Server を検索することはできません。</span><span class="sxs-lookup"><span data-stu-id="1a737-137">When the computer is renamed, the configuration manager and configuration wizard cannot locate the BizTalk Server.</span></span> <span data-ttu-id="1a737-138">BizTalk Server を構成した後に SQL Server コンピューターの名前を変更する場合も、同様の問題が発生します。</span><span class="sxs-lookup"><span data-stu-id="1a737-138">A similar problem will occur if the SQL Server computer is renamed after BizTalk Server is configured.</span></span>  
  
<span data-ttu-id="1a737-139">**解決策**</span><span class="sxs-lookup"><span data-stu-id="1a737-139">**Resolution**</span></span>  
 <span data-ttu-id="1a737-140">BizTalk Server コンピューターまたは SQL Server コンピューターの名前を変更しないでください。</span><span class="sxs-lookup"><span data-stu-id="1a737-140">Do not rename the BizTalk Server computer or the SQL Server computer.</span></span> <span data-ttu-id="1a737-141">サーバーの名前を変更すると、コンピューターの名前が変更される前に、すべての BizTalk 機能の構成が解除されます。</span><span class="sxs-lookup"><span data-stu-id="1a737-141">If a server must be renamed, unconfigure all BizTalk features before renaming the computer.</span></span> <span data-ttu-id="1a737-142">コンピューターの名前を変更してから、BizTalk Server の機能を再構成してください。</span><span class="sxs-lookup"><span data-stu-id="1a737-142">After renaming the computer, reconfigure BizTalk Server features.</span></span>  
  
## <a name="business-rules-configuration-wizard-fails"></a><span data-ttu-id="1a737-143">ビジネス ルール構成ウィザードが失敗します。</span><span class="sxs-lookup"><span data-stu-id="1a737-143">Business Rules Configuration Wizard fails</span></span>  
  
<span data-ttu-id="1a737-144">**問題**</span><span class="sxs-lookup"><span data-stu-id="1a737-144">**Problem**</span></span>  
  
-   <span data-ttu-id="1a737-145">ビジネス ルール構成ウィザードが、"一部のコンポーネントの構成に失敗しました。それらのコンポーネントにはどの設定も適用されませんでした。" というエラーによって失敗します。</span><span class="sxs-lookup"><span data-stu-id="1a737-145">The Business Rules Configuration Wizard fails with the error “Configuration failed for some components and no settings were applied for those components.”</span></span>  
  
-   <span data-ttu-id="1a737-146">BizTalk Server コンピューターにビジネス ルール エンジンが既に正常に構成されている場合、ルール エンジン更新サービスの開始は失敗し、手動で開始することはできません。</span><span class="sxs-lookup"><span data-stu-id="1a737-146">On BizTalk Server computers for which the Business Rules Engine has already been successfully configured, the Rules Engine Update service fails to start and cannot be started manually.</span></span>  
  
<span data-ttu-id="1a737-147">この問題が発生した場合は、BizTalk Server コンピューターのアプリケーション ログに次のようなエラーが生成されることがあります。</span><span class="sxs-lookup"><span data-stu-id="1a737-147">When this problem occurs, an error similar to the following may be generated in the BizTalk Server computer Application log:</span></span>  
  
```  
Service could not be started. : System.Net.Sockets.SocketException (10061): No connection could be made because the target machine actively refused it ::1:3132  
  
```  
  
<span data-ttu-id="1a737-148">**原因** </span><span class="sxs-lookup"><span data-stu-id="1a737-148">**Cause** </span></span>  
 <span data-ttu-id="1a737-149">マイクロソフト マルウェア対応センターは 2010 年 3 月 9 日、SettingsModifier:Win32/PossibleHostsFileHijack からの脅威の可能性に対処するために、更新されたシグネチャ ファイルを公開しました。</span><span class="sxs-lookup"><span data-stu-id="1a737-149">The Microsoft Malware Protection Center released an updated signature file on March 9th, 2010 to address a possible threat from SettingsModifier:Win32/PossibleHostsFileHijack.</span></span> <span data-ttu-id="1a737-150">この更新されたシグネチャ ファイルにより、SettingsModifier:Win32/PossibleHostsFileHijack からの脅威を緩和するために、Windows Defender などのソフトウェアでローカル HOSTS ファイルが更新されます。</span><span class="sxs-lookup"><span data-stu-id="1a737-150">This updated signature file can cause Microsoft Malware Detection software such as Windows Defender to update the local HOSTS file to mitigate threats from SettingsModifier:Win32/PossibleHostsFileHijack.</span></span> <span data-ttu-id="1a737-151">これらの変更の結果、BizTalk Server ルール エンジン更新サービスが正常に開始できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="1a737-151">As a result of these changes, the BizTalk Server Rules Engine Update service may fail to start.</span></span>  
  
<span data-ttu-id="1a737-152">**解決策**</span><span class="sxs-lookup"><span data-stu-id="1a737-152">**Resolution**</span></span>  
 <span data-ttu-id="1a737-153">ローカル HOSTS ファイルを更新して次の行を追加してください。</span><span class="sxs-lookup"><span data-stu-id="1a737-153">Update the local HOSTS file to include the following line:</span></span>  
  
```  
127.0.0.1         localhost  
```  
  
 <span data-ttu-id="1a737-154">HOSTS ファイルは %systemroot%\drivers\etc\ ディレクトリにあります。</span><span class="sxs-lookup"><span data-stu-id="1a737-154">The HOSTS file is located in the %systemroot%\drivers\etc\ directory.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1a737-155">Microsoft Malware Protection Center 署名からことがある脅威のアドレスを更新表示[SettingsModifier:Win32/公開しました](http://go.microsoft.com/fwlink/?LinkId=146221)です。</span><span class="sxs-lookup"><span data-stu-id="1a737-155">See the Microsoft Malware Protection Center signature update that addresses a possible threat from [SettingsModifier:Win32/PossibleHostsFileHijack](http://go.microsoft.com/fwlink/?LinkId=146221).</span></span>  
  
## <a name="configuration-logging"></a><span data-ttu-id="1a737-156">構成のログ記録</span><span class="sxs-lookup"><span data-stu-id="1a737-156">Configuration Logging</span></span>  
 <span data-ttu-id="1a737-157">構成プログラムでは、構成ログ ファイルが既定では BizTalk Server を実行しているコンピューターの一時ディレクトリに格納する詳細な情報が書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="1a737-157">The configuration program writes detailed information to a configuration log file which by default is located in the temp directory of the computer running BizTalk Server.</span></span> <span data-ttu-id="1a737-158">TEMP 環境変数によって指定されているフォルダーを確認するには、そのコンピューターでコマンド プロンプトを開き、次のコマンドを入力して、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="1a737-158">To determine the folder that is specified by the TEMP environment variable open a command prompt on this computer, type the following command, and then press ENTER:</span></span>  
  
 <span data-ttu-id="1a737-159">**エコー %temp%**</span><span class="sxs-lookup"><span data-stu-id="1a737-159">**echo %TEMP%**</span></span>  
  
 <span data-ttu-id="1a737-160">構成ログ ファイルの内容は、実行された構成手順の概要と、構成処理中に発生した疑いのあるエラーに関する診断情報です。</span><span class="sxs-lookup"><span data-stu-id="1a737-160">The configuration log file contains a summary of the configuration steps performed, as well as diagnostic information about any failures that may occur during the configuration process.</span></span> <span data-ttu-id="1a737-161">構成エラーが発生した場合メモ帳などのテキスト エディターでは、構成ログを開くし、エラーの考えられる原因のログ ファイルを確認します。</span><span class="sxs-lookup"><span data-stu-id="1a737-161">If a configuration error occurs, open the configuration log in a text editor such as Notepad and check the log file for possible causes of the error.</span></span>  
  
## <a name="troubleshooting-tools"></a><span data-ttu-id="1a737-162">トラブルシューティング ツール</span><span class="sxs-lookup"><span data-stu-id="1a737-162">Troubleshooting Tools</span></span>  
 <span data-ttu-id="1a737-163">SQL Server プロファイラー、Filemon、または Regmon を使用して、構成エラーに関する追加情報を収集します。</span><span class="sxs-lookup"><span data-stu-id="1a737-163">Use SQL Server Profiler, Filemon, or Regmon to gather additional information about configuration failures.</span></span> <span data-ttu-id="1a737-164">参照してください[トラブルシューティングに使用するには、ツールとユーティリティ](../core/tools-and-utilities-to-use-for-troubleshooting.md)です。</span><span class="sxs-lookup"><span data-stu-id="1a737-164">See [Tools and Utilities to use for Troubleshooting](../core/tools-and-utilities-to-use-for-troubleshooting.md).</span></span>  
  
### <a name="configuration-fails-when-biztalk-and-sql-are-installed-on-separate-computers"></a><span data-ttu-id="1a737-165">BizTalk と SQL が別々 のコンピューターにインストールすると、構成が失敗します。</span><span class="sxs-lookup"><span data-stu-id="1a737-165">Configuration fails when BizTalk and SQL are installed on separate computers</span></span>  
  
<span data-ttu-id="1a737-166">**問題**</span><span class="sxs-lookup"><span data-stu-id="1a737-166">**Problem**</span></span>  
 <span data-ttu-id="1a737-167">エンタープライズ シングル サインオン (SSO) コンポーネントを構成しようとすると、次のようなエラーが発生して構成が失敗します。</span><span class="sxs-lookup"><span data-stu-id="1a737-167">Configuration fails with errors similar to the following when attempting to configure the Enterprise Single Sign-On (SSO) component:</span></span>  
  
```
An error occurred while attempting to access the SSO database.  
Function: FieldInfoCreate  
```
  
 <span data-ttu-id="1a737-168">-または-</span><span class="sxs-lookup"><span data-stu-id="1a737-168">-or-</span></span>  
  
```Failed to enable the Single Sign-On (SSO) Service (error code 0X800706BA)```  
  
<span data-ttu-id="1a737-169">**原因**  </span><span class="sxs-lookup"><span data-stu-id="1a737-169">**Cause**  </span></span>  
 <span data-ttu-id="1a737-170">BizTalk Server と SQL Server が別々 のコンピューターにインストールされているし、構成の操作が Microsoft 分散トランザクション コーディネーター (MSDTC) トランザクションのコンテキストで実行される、MSDTC 機能は、上で公開する必要がある場合、これらのコンピューター間のネットワーク。</span><span class="sxs-lookup"><span data-stu-id="1a737-170">If BizTalk Server and SQL Server are installed on different computers, then the configuration operations are performed under the context of a Microsoft Distributed Transaction Coordinator (MSDTC) transaction and MSDTC functionality must be available over the network between these computers.</span></span> <span data-ttu-id="1a737-171">BizTalk Server と SQL Server を実行しているコンピューター間のネットワークで MSDTC 機能を使用できない場合は、このエラーは発生します。</span><span class="sxs-lookup"><span data-stu-id="1a737-171">If MSDTC functionality is not available over the network between the computers running BizTalk Server and SQL Server, then this error can occur.</span></span>  
  
<span data-ttu-id="1a737-172">**解決策**  </span><span class="sxs-lookup"><span data-stu-id="1a737-172">**Resolution**  </span></span>  
<span data-ttu-id="1a737-173">使用して[MSDTC の問題のトラブルシューティング](https://support.microsoft.com/help/306843/how-to-troubleshoot-ms-dtc-firewall-issues)を BizTalk Server と SQL Server を実行しているコンピューター間のネットワークで MSDTC 機能を確認します。</span><span class="sxs-lookup"><span data-stu-id="1a737-173">Use [Troubleshooting Problems with MSDTC](https://support.microsoft.com/help/306843/how-to-troubleshoot-ms-dtc-firewall-issues) to ensure MSDTC functionality over the network between the computers running BizTalk Server and SQL Server.</span></span>  
  
### <a name="antivirus-software-interferes-with-configuration-and-causes-configuration-failures"></a><span data-ttu-id="1a737-174">ウイルス対策ソフトウェアの干渉によって構成エラーが発生する</span><span class="sxs-lookup"><span data-stu-id="1a737-174">Antivirus software interferes with configuration and causes configuration failures</span></span>  
  
<span data-ttu-id="1a737-175">**問題** </span><span class="sxs-lookup"><span data-stu-id="1a737-175">**Problem** </span></span>  
 <span data-ttu-id="1a737-176">ウイルス対策ソフトウェアが、構成プログラムがウイルスであると誤って判断ときに、BizTalk Server の構成が失敗します。</span><span class="sxs-lookup"><span data-stu-id="1a737-176">BizTalk Server configuration fails when antivirus software incorrectly determines that the configuration program is a virus.</span></span>  
  
<span data-ttu-id="1a737-177">**原因**</span><span class="sxs-lookup"><span data-stu-id="1a737-177">**Cause**</span></span>  
 <span data-ttu-id="1a737-178">正当な (ウイルスではない) プログラムとして、BizTalk Server 構成プログラムを含めるにウイルス対策ソフトウェアが更新されていません。</span><span class="sxs-lookup"><span data-stu-id="1a737-178">The antivirus software has not been updated to include the BizTalk Server configuration program as a legitimate (non-virus) program.</span></span>  
  
<span data-ttu-id="1a737-179">**解決策**</span><span class="sxs-lookup"><span data-stu-id="1a737-179">**Resolution**</span></span>  
 <span data-ttu-id="1a737-180">構成プログラムの実行中に一時的にウイルス対策ソフトウェアを無効にするか、または正当な (ウイルスではない) プログラムとして、BizTalk Server 構成プログラムを認識するには、ウイルス対策プログラムを構成します。</span><span class="sxs-lookup"><span data-stu-id="1a737-180">Configure the antivirus program to recognize the BizTalk Server configuration program as a legitimate (non-virus) program or else temporarily disable the antivirus software while the configuration program is running.</span></span>  
  
### <a name="configuration-fails-with-a-file-or-assembly-name-filenamedll-or-one-of-its-dependencies-was-not-found-error"></a><span data-ttu-id="1a737-181">"ファイルまたはアセンブリ名 'FileName.dll'、またはその依存関係の 1 つが見つかりませんでした" というエラーによって構成が失敗する</span><span class="sxs-lookup"><span data-stu-id="1a737-181">Configuration fails with a "File or assembly name FileName.dll, or one of its dependencies, was not found" error</span></span>  
  
<span data-ttu-id="1a737-182">**問題**</span><span class="sxs-lookup"><span data-stu-id="1a737-182">**Problem**</span></span>  
 <span data-ttu-id="1a737-183">構成プロセスで次のようなエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1a737-183">An error similar to the following is displayed during the configuration process:</span></span>  
  
 <span data-ttu-id="1a737-184">BizTalk システム アセンブリ"C:\Program \microsoft\biztalk Server 20xx\Microsoft.BizTalk.DefaultPipelines.dll 配置に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="1a737-184">Failed to deploy BizTalk system assembly "C:\Program Files\Microsoft\BizTalk Server 20xx\Microsoft.BizTalk.DefaultPipelines.dll.</span></span> <span data-ttu-id="1a737-185">特定できない例外: ファイルまたはアセンブリ名 filename.dll、またはその依存関係の 1 つが見つかりませんでした"。</span><span class="sxs-lookup"><span data-stu-id="1a737-185">Unspecified exception: File or assembly name FileName .dll, or one of its dependencies, was not found."</span></span>  
  
<span data-ttu-id="1a737-186">**原因**</span><span class="sxs-lookup"><span data-stu-id="1a737-186">**Cause**</span></span>  
 <span data-ttu-id="1a737-187">このエラーは、アカウントがネットワーク サービスの一時フォルダーに BizTalk Server を実行しているコンピューター上のアクセス許可を記述する場合に発生することができます。</span><span class="sxs-lookup"><span data-stu-id="1a737-187">This error can occur if the Network Service account does not have write permissions to the temp folder on the computer running BizTalk Server.</span></span> <span data-ttu-id="1a737-188">構成時に、BizTalk Server 構成は、.NET アセンブリを BizTalk 管理データベースに展開するのに Windows Management Instrumentation (WMI) を使用します。</span><span class="sxs-lookup"><span data-stu-id="1a737-188">During configuration, BizTalk Server configuration uses Windows Management Instrumentation (WMI) to deploy .NET assemblies to the BizTalk Management database.</span></span> <span data-ttu-id="1a737-189">WMI は、BizTalk 管理データベースにこれらのアセンブリの展開中に、Network Service アカウントを偽装しますします。 そのため、Network Service アカウント必要がありますが書き込みアクセスを BizTalk Server を実行しているコンピューター上の一時フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="1a737-189">WMI impersonates the Network Service account while deploying these assemblies to the BizTalk Management database and so the Network Service account must have write access to the temp folder on the computer running BizTalk Server.</span></span>  
  
<span data-ttu-id="1a737-190">**解決策**</span><span class="sxs-lookup"><span data-stu-id="1a737-190">**Resolution**</span></span>  
 <span data-ttu-id="1a737-191">ネットワーク サービス アカウントの BizTalk Server を実行しているコンピューター上の一時フォルダーへの書き込みアクセスを付与し、構成プログラムを再実行します。</span><span class="sxs-lookup"><span data-stu-id="1a737-191">Grant the Network Service account write access to the temp folder on the computer running BizTalk Server and run the configuration program again.</span></span> <span data-ttu-id="1a737-192">TEMP 環境変数で指定されているフォルダーを特定するのには、コンピューターでコマンド プロンプトを開き、次のコマンドを入力およびし、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="1a737-192">To determine the folder that is specified by the TEMP environment variable, open a command prompt on the computer, type the following command, and then press ENTER:</span></span>  
  
```  
echo %TEMP%  
```  
  
### <a name="configuration-fails-if-a-sql-server-database-file-that-has-the-same-name-as-the-specified-database-already-exists-in-the-sql-server-data-folder"></a><span data-ttu-id="1a737-193">指定したデータベースと同じ名前の SQL Server データベース ファイルが SQL Server のデータ フォルダーに既に存在していると構成が失敗する</span><span class="sxs-lookup"><span data-stu-id="1a737-193">Configuration fails if a SQL Server database file that has the same name as the specified database already exists in the SQL Server data folder</span></span>  
  
#### <a name="problem"></a><span data-ttu-id="1a737-194">問題</span><span class="sxs-lookup"><span data-stu-id="1a737-194">Problem</span></span>  
 <span data-ttu-id="1a737-195">次のようなエラーが発生して構成が失敗します。</span><span class="sxs-lookup"><span data-stu-id="1a737-195">Configuration fails with an error similar to the following:</span></span>  
  
```
Failed to set up BAM database(s)  
  
Cannot open database requested in login 'BAMPrimaryImport'  
  
Logon fails. Logon failed for user '*BizTalk\BizTalkUser*'  
```
  
<span data-ttu-id="1a737-196">**原因**</span><span class="sxs-lookup"><span data-stu-id="1a737-196">**Cause**</span></span>  
 <span data-ttu-id="1a737-197">.Mdf ファイルの場合、このエラーが発生する可能性がまたは .ldf ファイルが同じ名前の .mdf ファイルまたは .ldf ファイルを作成しようとして、BizTalk Server 構成プログラムを持つ SQL Server を実行しているコンピューターの \MSSQL\data フォルダーに既に存在します。</span><span class="sxs-lookup"><span data-stu-id="1a737-197">This error can occur if an .mdf file or an .ldf file already exists in the \MSSQL\data folder of the computer running SQL Server that has the same name as the .mdf file or the .ldf file that the BizTalk Server configuration program is trying to create.</span></span> <span data-ttu-id="1a737-198">データベースに対して作成される .mdf ファイルおよび .ldf ファイルの名前は、BizTalk Server 構成プログラムに .mdf 拡張子と .ldf 拡張子を追加で指定されているデータベースの名前から派生します。</span><span class="sxs-lookup"><span data-stu-id="1a737-198">The names of the .mdf file and the .ldf file that are created for the databases are derived from the name of the database that is specified in the BizTalk Server configuration program with an .mdf and an .ldf extension appended.</span></span>  
  
<span data-ttu-id="1a737-199">**解決策**</span><span class="sxs-lookup"><span data-stu-id="1a737-199">**Resolution**</span></span>  
 <span data-ttu-id="1a737-200">この問題を解決するには、以下のいずれかの方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="1a737-200">To resolve this behavior, use one of the following methods:</span></span>  
  
-   <span data-ttu-id="1a737-201">現在作成しているデータベースの名前と一致する名前を持つ .mdf ファイルや .ldf ファイルを削除します。</span><span class="sxs-lookup"><span data-stu-id="1a737-201">Delete any .mdf files or .ldf files that have names that match the names of any databases that you are creating.</span></span>  
  
-   <span data-ttu-id="1a737-202">SQL Server の \Program Files\Microsoft SQL Server\MSSQL\data フォルダーに既に存在する .mdf ファイルや .ldf ファイルの名前と一致しないデータベース名を選択します。</span><span class="sxs-lookup"><span data-stu-id="1a737-202">Choose database names that do not match the names of any .mdf files or .ldf files that already exist in the \Program Files\Microsoft SQL Server\MSSQL\data folder of your SQL server.</span></span>  
  
### <a name="configuration-fails-on-a-domain-controller-when-specifying-local-accounts"></a><span data-ttu-id="1a737-203">ドメイン コントローラーでローカル アカウントを指定すると構成が失敗する</span><span class="sxs-lookup"><span data-stu-id="1a737-203">Configuration fails on a domain controller when specifying local accounts</span></span>  
  
<span data-ttu-id="1a737-204">**問題**</span><span class="sxs-lookup"><span data-stu-id="1a737-204">**Problem**</span></span>  
 <span data-ttu-id="1a737-205">ドメイン コント ローラーで、BizTalk Server 構成プログラムを実行するときに構成はローカル グループ (たとえば、BizTalk ホスト ユーザー グループ) を指定した場合、BizTalkServerApplication ホストか BizTalkIsolatedHost ホストのいずれかの失敗します。</span><span class="sxs-lookup"><span data-stu-id="1a737-205">When running the BizTalk Server configuration program on a domain controller, configuration fails if you specified a local group (for example, BizTalk Host Users Group) for either the BizTalkServerApplication host or the BizTalkIsolatedHost host.</span></span>  
  
<span data-ttu-id="1a737-206">**原因**</span><span class="sxs-lookup"><span data-stu-id="1a737-206">**Cause**</span></span>  
 <span data-ttu-id="1a737-207">ドメイン コントローラーでは、ローカル Windows グループが自動的にドメイン Windows グループとして処理されます (ドメイン コントローラーにはローカル Windows グループのようなものは存在しません)。</span><span class="sxs-lookup"><span data-stu-id="1a737-207">A domain controller automatically treats a local Windows group as a domain Windows group (there is no such thing as local Windows group on a domain controller).</span></span> <span data-ttu-id="1a737-208">構成プログラムの実行中に、ホストのローカル Windows グループを指定した場合、グループ用の SQL Server ログオンを作成しようとするときの構成は失敗します。</span><span class="sxs-lookup"><span data-stu-id="1a737-208">If you specified a local Windows group for the host while running the configuration program, configuration will fail when trying to create a SQL Server logon for the group.</span></span> <span data-ttu-id="1a737-209">サーバーがドメイン コントローラーに設定されていると、構成プログラムのローカル Windows グループ オプションが無効になりません。</span><span class="sxs-lookup"><span data-stu-id="1a737-209">The configuration program does not disable the local Windows group option when the server is a domain controller.</span></span>  
  
<span data-ttu-id="1a737-210">**解決策**</span><span class="sxs-lookup"><span data-stu-id="1a737-210">**Resolution**</span></span>  
 <span data-ttu-id="1a737-211">構成中に作成されるホストに対してはドメイン グループを指定します。</span><span class="sxs-lookup"><span data-stu-id="1a737-211">Specify domain groups for the hosts that are created during configuration.</span></span>  
  
### <a name="configuration-fails-to-create-sql-server-analysis-database-if-the-sql-server-has-been-renamed"></a><span data-ttu-id="1a737-212">SQL サーバーの名前が変更されていると構成プログラムが SQL Server 分析データベースの作成に失敗する</span><span class="sxs-lookup"><span data-stu-id="1a737-212">Configuration fails to create SQL Server Analysis database if the SQL server has been renamed</span></span>  
  
<span data-ttu-id="1a737-213">**問題**</span><span class="sxs-lookup"><span data-stu-id="1a737-213">**Problem**</span></span>  
 <span data-ttu-id="1a737-214">SQL Server 分析サーバーをインストールしたコンピューターの名前を変更した場合、新しい SQL Server 分析データベースを作成しようとすると構成プログラムが失敗して、次のようなエラーが生成されます。</span><span class="sxs-lookup"><span data-stu-id="1a737-214">If you have renamed the computer on which you installed SQL Server Analysis Server, the configuration program fails when it tries to create the new SQL Server Analysis database and an error similar to the following is generated:</span></span>  

```  
 Cannot connect to the repository.  
  
 Analysis server: <machine name\>  
  
 Error:  
  
 '\\\\<machine name\>\MsOLAPRepository$\msmdrep.mdb' is not a valid path.  
  
 Make sure that you correctly spell the path name and that you are  
  
 connected to the server on which the file resides.  
```
  
<span data-ttu-id="1a737-215">**原因**</span><span class="sxs-lookup"><span data-stu-id="1a737-215">**Cause**</span></span>  
 <span data-ttu-id="1a737-216">SQL Server 分析サーバーをインストールしたコンピューターの新しい名前を構成プログラムが特定できません。</span><span class="sxs-lookup"><span data-stu-id="1a737-216">The configuration program is unable to determine the new name of the computer on which you installed SQL Server Analysis Server.</span></span>  
  
<span data-ttu-id="1a737-217">**解決策**</span><span class="sxs-lookup"><span data-stu-id="1a737-217">**Resolution**</span></span>  
 <span data-ttu-id="1a737-218">以下の手順を手動で実行し、分析サーバーを新しいコンピューター名で更新します。</span><span class="sxs-lookup"><span data-stu-id="1a737-218">Perform the following manual steps to update Analysis Server with the new computer name:</span></span>  
  
1.  <span data-ttu-id="1a737-219">SQL Server で開きます**Microsoft SQL Server** **Analysis Services**、順にクリック**分析マネージャー**です。</span><span class="sxs-lookup"><span data-stu-id="1a737-219">On the SQL Server, open **Microsoft SQL Server**, select **Analysis Services**, and then click **Analysis Manager**.</span></span>  
  
2.  <span data-ttu-id="1a737-220">**分析マネージャー**ナビゲーション ペインをダブルクリックして、 **Analysis Servers**ノードを展開します。</span><span class="sxs-lookup"><span data-stu-id="1a737-220">In the **Analysis Manager** navigation panel, double-click the **Analysis Servers** node to expand it.</span></span>  
  
3.  <span data-ttu-id="1a737-221">クリックして、編集するリポジトリ接続文字列を使用してサーバーを右クリックして**リポジトリ接続文字列の編集**です。</span><span class="sxs-lookup"><span data-stu-id="1a737-221">Right-click the server with the repository connection string you want to edit, and then select **Edit Repository Connection String**.</span></span>  
  
4.  <span data-ttu-id="1a737-222">**リポジトリ接続文字列の編集** ダイアログ ボックスで、この文字列内でサーバー名を確認しが正しくない場合、新しいコンピューター名を更新します。</span><span class="sxs-lookup"><span data-stu-id="1a737-222">In the **Edit Repository Connection String** dialog box, verify the server name in this string and update it to the new computer name if it is incorrect.</span></span>  
  
5.  <span data-ttu-id="1a737-223">次の場所に移動します。 <*インストール ディレクトリ*> \Program Files\Microsoft Analysis services \bin です。</span><span class="sxs-lookup"><span data-stu-id="1a737-223">Navigate to the following location: <*installation directory*>\Program Files\Microsoft Analysis Services\Bin.</span></span>  
  
6.  <span data-ttu-id="1a737-224">右クリックし、 **Bin**フォルダー、およびクリック**共有とセキュリティ**です。</span><span class="sxs-lookup"><span data-stu-id="1a737-224">Right-click the **Bin** folder, and then click **Sharing and Security**.</span></span> <span data-ttu-id="1a737-225">**Bin のプロパティ** ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1a737-225">The **Bin Properties** dialog box appears.</span></span>  
  
7.  <span data-ttu-id="1a737-226">**Bin のプロパティ**ダイアログ ボックスで、をクリックして、**共有**タブをすべてのオンライン分析処理 (OLAP) 管理者が完全なアクセス許可をこのフォルダーにあることを確認します。</span><span class="sxs-lookup"><span data-stu-id="1a737-226">In the **Bin Properties** dialog box, click the **Sharing** tab to verify that all Online Analytical Processing (OLAP) administrators have full permissions to this folder.</span></span>  
  
### <a name="artifacts-disappear-from-configuration-database-on-redeployment-of-assemblies-from-visual-studio"></a><span data-ttu-id="1a737-227">Visual Studio からアセンブリを再展開構成データベースからアイテムが表示されなくなります</span><span class="sxs-lookup"><span data-stu-id="1a737-227">Artifacts disappear from Configuration Database on redeployment of assemblies from Visual Studio</span></span>  
  
<span data-ttu-id="1a737-228">**問題**</span><span class="sxs-lookup"><span data-stu-id="1a737-228">**Problem**</span></span>  
 <span data-ttu-id="1a737-229">ときに、BizTalk Server プロジェクトを再展開、Visual Studio 内のプロジェクト レベルで再デプロイするプロジェクトの参照は、BizTalk Server MMC が更新されたときに表示されなくに表示されるプロジェクト内に含まれるすべての成果物です。</span><span class="sxs-lookup"><span data-stu-id="1a737-229">When a BizTalk Server project is redeployed at the project level within Visual Studio, all artifacts contained within the project that reference the project being redeployed will appear to vanish when the BizTalk Server MMC is refreshed.</span></span>  
  
<span data-ttu-id="1a737-230">**原因**</span><span class="sxs-lookup"><span data-stu-id="1a737-230">**Cause**</span></span>  
 <span data-ttu-id="1a737-231">この問題の原因を示すために、ユーザーが Maps プロジェクトを再展開しようとしているサンプル BizTalk Server ソリューションに基づく例について考えてみます。</span><span class="sxs-lookup"><span data-stu-id="1a737-231">To illustrate the cause of this problem, consider the following example based on a sample BizTalk Server solution where a user wants to redeploy the Maps project.</span></span> <span data-ttu-id="1a737-232">プロジェクトをコンパイルすると個々のアセンブリが生成されます。</span><span class="sxs-lookup"><span data-stu-id="1a737-232">Note that compiling projects yields individual assemblies.</span></span> <span data-ttu-id="1a737-233">次の図は、ユーザーが再展開を行う前のソリューションの状態を示しています。</span><span class="sxs-lookup"><span data-stu-id="1a737-233">The following figure indicates the state of the solution before the user does a redeployment.</span></span> <span data-ttu-id="1a737-234">アイテム間の関係は次のようになっています。</span><span class="sxs-lookup"><span data-stu-id="1a737-234">The relationships among the artifacts are as follows:</span></span>  
  
-   <span data-ttu-id="1a737-235">Orch1、Orch2、Maps、Pipelines、および Schemas はプロジェクトです。</span><span class="sxs-lookup"><span data-stu-id="1a737-235">Orch1, Orch2, Maps, Pipelines, and Schemas are projects.</span></span>  
  
-   <span data-ttu-id="1a737-236">Orch1 は Maps を参照し、Maps は Schemas を参照しています。</span><span class="sxs-lookup"><span data-stu-id="1a737-236">Orch1 references Maps, which in turn references Schemas.</span></span>  
  
-   <span data-ttu-id="1a737-237">Orch2 は Schemas を参照しています。</span><span class="sxs-lookup"><span data-stu-id="1a737-237">Orch2 references Schemas.</span></span>  
  
-   <span data-ttu-id="1a737-238">Pipelines は Schemas を参照しています。</span><span class="sxs-lookup"><span data-stu-id="1a737-238">Pipelines references Schemas.</span></span>  
  
![bcd_ExistingBizTalkServerSolutionc](../install-and-config-guides/media/bcd_ExistingBizTalkServerSolutionc.gif)  
  
<span data-ttu-id="1a737-240">ユーザーが Visual Studio の既定のプロジェクト設定を使用して Maps プロジェクトを再展開すると、次の図のように、Orch1、Orch2、および Pipeline の各アイテムが消えてしまいます。</span><span class="sxs-lookup"><span data-stu-id="1a737-240">If the user redeploys the Maps project using the default Visual Studio project settings, the Orch1, Orch2, and Pipeline artifacts vanish, as shown in the following figure.</span></span>  
  
![bcd_BizTalkSolutionWLostArtifactsc](../install-and-config-guides/media/bcd_BizTalkSolutionWLostArtifactsc.gif)  
  
 <span data-ttu-id="1a737-242">Maps の再展開は、現在展開されている Maps.dll アセンブリの展開を解除して、新しい Maps.dll ファイルを展開する、2 段階のプロセスです。</span><span class="sxs-lookup"><span data-stu-id="1a737-242">Redeploying Maps is a two-step process of undeploying the currently deployed Maps.dll assembly, and then deploying the new Maps.dll file.</span></span> <span data-ttu-id="1a737-243">Visual Studio は、再展開プロセスの一部として自動的にこれらの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="1a737-243">Visual Studio performs these steps automatically as part of the redeployment process.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1a737-244">前の文は厳密には正しくありません。というのも、これらの手順は Visual Studio で常に行われるものなので、正しく行われているかどうかを意識することはありません。</span><span class="sxs-lookup"><span data-stu-id="1a737-244">The preceding sentence is not strictly correct because these are steps that Visual Studio always does so there is no notion of it being the proper way.</span></span>  
  
 <span data-ttu-id="1a737-245">重要な点は、BizTalk Server アセンブリを展開解除するために Visual Studio すべてのアセンブリをアセンブリに依存している展開フラグが設定されている展開を解除します。</span><span class="sxs-lookup"><span data-stu-id="1a737-245">The key point is that in order to undeploy a BizTalk Server assembly, Visual Studio has to undeploy all assemblies that are dependent upon that assembly that have the deploy flag set.</span></span> <span data-ttu-id="1a737-246">この例で言うと、再展開の最初の展開解除の手順を実行するには、BizTalk Server が Orch1.dll (Maps.dll に依存している) の展開を解除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1a737-246">In our example, to perform the first undeployment step of the redeployment, BizTalk Server needs to undeploy Orch1.dll (which depends on Maps.dll).</span></span> <span data-ttu-id="1a737-247">Maps.dll の展開を解除する、Visual Studio の展開も解除 Schemas.dll (展開フラグの設定があると仮定)。</span><span class="sxs-lookup"><span data-stu-id="1a737-247">During the undeployment of Maps.dll, Visual Studio also undeploys Schemas.dll (assuming it has the deploy flag set).</span></span> <span data-ttu-id="1a737-248">Schemas.dll の展開を解除するには、Orch2.dll と Pipelines.dll (いずれも Schemas.dll に依存している) の展開を解除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1a737-248">In order to undeploy Schemas.dll, Visual Studio needs to undeploy Orch2.dll and Pipelines.dll (both of which depend on Schemas.dll).</span></span>  
  
 <span data-ttu-id="1a737-249">問題がある点で、Visual Studio は Maps.dll とそれが依存するアセンブリを再配置。 この場合は Schemas.dll します。</span><span class="sxs-lookup"><span data-stu-id="1a737-249">A problem exists in that Visual Studio redeploys only Maps.dll and the assemblies that it depends upon: in this case, Schemas.dll.</span></span> <span data-ttu-id="1a737-250">そのため、ユーザーが BizTalk Server MMC を更新すると、Orch1、Orch2、および Pipeline の各アセンブリが消えたように見えますが、Maps.dll と Schemas.dll は引き続き表示されます。</span><span class="sxs-lookup"><span data-stu-id="1a737-250">So when the user refreshes the BizTalk Server MMC, the Orch1, Orch2, and Pipeline assemblies seem to have vanished, but Maps.dll and Schemas.dll are still visible.</span></span>  
  
<span data-ttu-id="1a737-251">**解決策**</span><span class="sxs-lookup"><span data-stu-id="1a737-251">**Resolution**</span></span>  
 <span data-ttu-id="1a737-252">メイン プロジェクト (他のプロジェクトを参照しているプロジェクト) に対して次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="1a737-252">For the main project (that references other projects) do the following:</span></span>  
  
1.  <span data-ttu-id="1a737-253">ソリューション エクスプローラーで、ソリューション ノードを右クリックします。</span><span class="sxs-lookup"><span data-stu-id="1a737-253">In Solution Explorer, right-click the solution node.</span></span>  
  
2.  <span data-ttu-id="1a737-254">をクリックして**プロパティ**を開くには、**ソリューション プロパティ ページ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="1a737-254">Click **Properties** to open the **Solution Property Pages** dialog box.</span></span>  
  
3.  <span data-ttu-id="1a737-255">をクリックして**構成プロパティ**、クリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="1a737-255">Click **Configuration Properties**, and then click **Configuration**.</span></span>  
  
4.  <span data-ttu-id="1a737-256">クリア、**展開**参照プロジェクトのチェック ボックスです。</span><span class="sxs-lookup"><span data-stu-id="1a737-256">Clear the **Deploy** check box for the referenced project.</span></span>  
  
5.  <span data-ttu-id="1a737-257">ソリューション エクスプローラーで、新しいソリューション レベルの展開を実行します。</span><span class="sxs-lookup"><span data-stu-id="1a737-257">In Solution Explorer, execute a new solution-level deployment.</span></span> <span data-ttu-id="1a737-258">これを行うには、ソリューション ノードを右クリックし、をクリックして**ソリューションの配置**です。</span><span class="sxs-lookup"><span data-stu-id="1a737-258">To do this, right-click the solution node and then click **Deploy Solution**.</span></span>  
  
### <a name="supported-virtual-directory-types"></a><span data-ttu-id="1a737-259">サポートされている仮想ディレクトリのタイプ</span><span class="sxs-lookup"><span data-stu-id="1a737-259">Supported Virtual Directory Types</span></span>  
 <span data-ttu-id="1a737-260">関連付けられている仮想ディレクトリが型の場合にのみエクスポート操作は成功 MSI のエクスポートを実行しようと、オーケストレーションから Web サービスを参照する、ときに**IIsWebVirtualDir**または**IIsWebDirectory**.</span><span class="sxs-lookup"><span data-stu-id="1a737-260">When referencing Web services from an orchestration and attempting to do an MSI export, the export operation will succeed only if the associated virtual directories are of type **IIsWebVirtualDir** or **IIsWebDirectory**.</span></span> <span data-ttu-id="1a737-261">**IIsWebVirtualDir**と**IIsWebDirectory** IIS メタベースに表示するノード型です。</span><span class="sxs-lookup"><span data-stu-id="1a737-261">**IIsWebVirtualDir** and **IIsWebDirectory** are the node types that appear in the IIS metabase.</span></span> <span data-ttu-id="1a737-262">**IIsWebVirtualDir**の仮想ディレクトリ、**パス**絶対ファイル フォルダーを指すプロパティです。</span><span class="sxs-lookup"><span data-stu-id="1a737-262">**IIsWebVirtualDir** is a virtual directory with a **Path** property that points to an absolute file folder.</span></span> <span data-ttu-id="1a737-263">**IIsWebDirectory**なしの仮想ディレクトリ、**パス**プロパティ別のサブフォルダーでは通常、相対ファイル フォルダーを参照および**IIsWebVirtualDir**または**IIsWebDirectory**ノード。</span><span class="sxs-lookup"><span data-stu-id="1a737-263">**IIsWebDirectory** is a virtual directory without a **Path** property and thus refers to a relative file folder, typically a subfolder of another **IIsWebVirtualDir** or **IIsWebDirectory** node.</span></span> <span data-ttu-id="1a737-264">メタベース階層でフォルダーを表すものとしてはこの 2 つのタイプが一般的です。</span><span class="sxs-lookup"><span data-stu-id="1a737-264">These two types are the ones typically seen in the metabase hierarchy to describe folders.</span></span>  
  
 <span data-ttu-id="1a737-265">型の仮想ディレクトリ**IIsConfigObject**はサポートされていませんし、MSI のエクスポートはここでは失敗します。</span><span class="sxs-lookup"><span data-stu-id="1a737-265">Virtual directories of type **IIsConfigObject** are not supported and the MSI export will fail in this case.</span></span> <span data-ttu-id="1a737-266">**IIsConfigObject**が BizTalk Server が正しく処理されないか、有効なノード型では予期しないメタベース ノード タイプか、正しく作成されていない (およびしたがって無効な) メタベース エントリを示す値。</span><span class="sxs-lookup"><span data-stu-id="1a737-266">**IIsConfigObject** is an unexpected metabase node type that is either a valid node type that BizTalk Server is not handling properly or an indication of an improperly created (and thus invalid) metabase entry.</span></span> <span data-ttu-id="1a737-267">このような状況では、BizTalk Server によって、次のようなエラー メッセージが示されます。 種類 IIsConfigObject の予期しないディレクトリ エントリ"IIS://LM/W3SVC/1/ROOT/BadVdir/"です。</span><span class="sxs-lookup"><span data-stu-id="1a737-267">In this situation BizTalk Server will display an error message something like the following: Unexpected directory entry " IIS://LM/W3SVC/1/ROOT/BadVdir/" of type IIsConfigObject.</span></span>  
  
### <a name="unable-to-view-group-information-after-removing-stale-logons"></a><span data-ttu-id="1a737-268">古いログオンを削除するとグループ情報を表示できなくなる</span><span class="sxs-lookup"><span data-stu-id="1a737-268">Unable to view Group information after removing stale logons</span></span>  
  
<span data-ttu-id="1a737-269">**問題**</span><span class="sxs-lookup"><span data-stu-id="1a737-269">**Problem**</span></span>  
 <span data-ttu-id="1a737-270">構成中に古いログオンを見つけて削除すると、グループ情報を表示できなくなる場合があります。</span><span class="sxs-lookup"><span data-stu-id="1a737-270">If, during configuration, you encounter and delete stale logons, you may not be able to view Group information.</span></span>  
  
<span data-ttu-id="1a737-271">**原因**</span><span class="sxs-lookup"><span data-stu-id="1a737-271">**Cause**</span></span>  
 <span data-ttu-id="1a737-272">これは既知の構成の問題です。</span><span class="sxs-lookup"><span data-stu-id="1a737-272">This is a known configuration issue.</span></span>  
  
<span data-ttu-id="1a737-273">**解決策**</span><span class="sxs-lookup"><span data-stu-id="1a737-273">**Resolution**</span></span>  
 <span data-ttu-id="1a737-274">Host Windows グループのログオンを削除して再構成すると解決する場合があります。</span><span class="sxs-lookup"><span data-stu-id="1a737-274">It may help to delete the Host Windows group logons and then reconfigure.</span></span> <span data-ttu-id="1a737-275">それでもグループ情報を表示できない場合は、マイクロソフト製品サポートにご連絡ください。</span><span class="sxs-lookup"><span data-stu-id="1a737-275">If the Group information is still not available, contact Microsoft Product Support.</span></span>  
  
### <a name="cannot-change-computer-name-after-biztalk-server-is-installed"></a><span data-ttu-id="1a737-276">BizTalk Server のインストール後にコンピューター名を変更できない</span><span class="sxs-lookup"><span data-stu-id="1a737-276">Cannot change computer name after BizTalk Server is installed</span></span>  
  
<span data-ttu-id="1a737-277">**問題**</span><span class="sxs-lookup"><span data-stu-id="1a737-277">**Problem**</span></span>  
 <span data-ttu-id="1a737-278">BizTalk Server を実行しているコンピューター上のコンピューター名を変更して、(リブート)、コンピューターでは、エラー メッセージを再起動するときに発生します。</span><span class="sxs-lookup"><span data-stu-id="1a737-278">When you change the computer name on a computer running BizTalk Server, and you restart (reboot) the computer, error messages may occur.</span></span>  
  
<span data-ttu-id="1a737-279">**原因**</span><span class="sxs-lookup"><span data-stu-id="1a737-279">**Cause**</span></span>  
 <span data-ttu-id="1a737-280">SQL Server は、BizTalk Server が BizTalk Server をインストールおよび構成したら、コンピューター名の変更をサポートしていないため、コンピューター名の変更をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="1a737-280">SQL Server does not support changing the computer name, so BizTalk Server does not support changing the computer name once BizTalk Server is installed and configured.</span></span>  
  
<span data-ttu-id="1a737-281">**解決策**</span><span class="sxs-lookup"><span data-stu-id="1a737-281">**Resolution**</span></span>  
 <span data-ttu-id="1a737-282">BizTalk Server のインストール後はコンピューター名を変更しないことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="1a737-282">We recommend that you do not change computer names after you install BizTalk Server.</span></span>  
  
### <a name="known-issues-with-enterprise-single-sign-on"></a><span data-ttu-id="1a737-283">エンタープライズ シングル サインオンに関する既知の問題</span><span class="sxs-lookup"><span data-stu-id="1a737-283">Known Issues with Enterprise Single Sign-On</span></span>  
 <span data-ttu-id="1a737-284">ここでは、エンタープライズ シングル サインオン (SSO) に関係する可能性があるセットアップと構成の問題について説明します。</span><span class="sxs-lookup"><span data-stu-id="1a737-284">This section describes setup and configuration problems that may be related to Enterprise Single Sign-On (SSO).</span></span>  
  
##### <a name="entsso-service-fails-to-start"></a><span data-ttu-id="1a737-285">ENTSSO サービスを開始できません。</span><span class="sxs-lookup"><span data-stu-id="1a737-285">ENTSSO Service fails to start</span></span>  
  
<span data-ttu-id="1a737-286">**問題**</span><span class="sxs-lookup"><span data-stu-id="1a737-286">**Problem**</span></span>  
 <span data-ttu-id="1a737-287">ENTSSO サービスを開始できません。</span><span class="sxs-lookup"><span data-stu-id="1a737-287">The ENTSSO service fails to start.</span></span>  
  
<span data-ttu-id="1a737-288">**原因**</span><span class="sxs-lookup"><span data-stu-id="1a737-288">**Cause**</span></span>  
 <span data-ttu-id="1a737-289">ENTSSO サービスが有効な SSO 管理者アカウントで実行されていない場合、サービスを開始できません。</span><span class="sxs-lookup"><span data-stu-id="1a737-289">If the ENTSSO service is not running under a valid SSO Administrator account, it will fail to start.</span></span>  
  
<span data-ttu-id="1a737-290">**解決策**</span><span class="sxs-lookup"><span data-stu-id="1a737-290">**Resolution**</span></span>  
 <span data-ttu-id="1a737-291">有効な SSO 管理者アカウントを ENTSSO サービスに指定して、サービス コントロール マネージャー (SCM) スナップインからサービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="1a737-291">Specify a valid SSO administrator account for the ENTSSO Service and restart the service from Services Control Manager (SCM) snap-in.</span></span>  
  
##### <a name="biztalk-services-dependent-on-the-enterprise-single-sign-on-service-entsso-fail-to-start-after-a-reboot"></a><span data-ttu-id="1a737-292">再起動後、エンタープライズ シングル サインオン サービス (ENTSSO) に依存する BizTalk Services が起動しない</span><span class="sxs-lookup"><span data-stu-id="1a737-292">BizTalk Services dependent on the Enterprise Single Sign-On Service (ENTSSO) fail to start after a reboot</span></span>  
  
<span data-ttu-id="1a737-293">**問題**</span><span class="sxs-lookup"><span data-stu-id="1a737-293">**Problem**</span></span>  
 <span data-ttu-id="1a737-294">BTSSvc$BizTalkServerApplication はエンタープライズ シングル サインオン サービス (ENTSSO) と依存関係があり、リブート後の起動中にタイムアウトすることがあります。</span><span class="sxs-lookup"><span data-stu-id="1a737-294">BTSSvc$BizTalkServerApplication has a dependency on the Enterprise Single Sign-On Service (ENTSSO) and may timeout during start up after a reboot.</span></span>  
  
<span data-ttu-id="1a737-295">**原因**</span><span class="sxs-lookup"><span data-stu-id="1a737-295">**Cause**</span></span>  
 <span data-ttu-id="1a737-296">エンタープライズ シングル サインオン サービスは、起動に約 3 分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="1a737-296">The Enterprise Single Sign-On Service may take around 3 minutes to start.</span></span>  
  
<span data-ttu-id="1a737-297">**解決策**</span><span class="sxs-lookup"><span data-stu-id="1a737-297">**Resolution**</span></span>  
 <span data-ttu-id="1a737-298">"BizTalk Service BizTalk グループ: BizTalkServerApplication" サービスを、スタートアップ オプションの種類を [自動 (遅延スタート)] として構成します。</span><span class="sxs-lookup"><span data-stu-id="1a737-298">Configure the “BizTalk Service BizTalk Group: BizTalkServerApplication” service with the Automatic (Delayed Start) startup type option.</span></span> <span data-ttu-id="1a737-299">これにより、すべての自動サービスのスタートアップ ルーチン完了後に、このサービスが開始されます。</span><span class="sxs-lookup"><span data-stu-id="1a737-299">This will initiate the start of the service after all Automatic services have completed their startup routines.</span></span>  
  
##### <a name="cannot-access-an-affiliate-application"></a><span data-ttu-id="1a737-300">関連アプリケーションにアクセスできない</span><span class="sxs-lookup"><span data-stu-id="1a737-300">Cannot access an affiliate application</span></span>  
  
<span data-ttu-id="1a737-301">**問題**</span><span class="sxs-lookup"><span data-stu-id="1a737-301">**Problem**</span></span>  
 <span data-ttu-id="1a737-302">関連するアプリケーションの管理者アカウントが有効でない場合、エンタープライズ シングル サインオン サービスはこの関連アプリケーションを無効にします。</span><span class="sxs-lookup"><span data-stu-id="1a737-302">The Enterprise Single Sign-On service disables an affiliate application if the application administrator account associated with it is not valid.</span></span>  
  
<span data-ttu-id="1a737-303">**原因**</span><span class="sxs-lookup"><span data-stu-id="1a737-303">**Cause**</span></span>  
 <span data-ttu-id="1a737-304">SSO アプリケーションの管理者アカウントが無効です。</span><span class="sxs-lookup"><span data-stu-id="1a737-304">The SSO application administrator account is not valid.</span></span>  
  
<span data-ttu-id="1a737-305">**解決策**</span><span class="sxs-lookup"><span data-stu-id="1a737-305">**Resolution**</span></span>  
 <span data-ttu-id="1a737-306">関連アプリケーションを作成する前に、SSO アプリケーションの管理者アカウントが有効なことを確認します。</span><span class="sxs-lookup"><span data-stu-id="1a737-306">Ensure that the SSO application administrator account is valid before you create an affiliate application.</span></span> <span data-ttu-id="1a737-307">関連アプリケーションを使用するには、そのアプリケーションを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1a737-307">You must then enable the affiliate application to use the application.</span></span>  
  
##### <a name="rpc-error-occurs-when-connecting-to-a-client-computer"></a><span data-ttu-id="1a737-308">クライアント コンピューターに接続するときに、RPC エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="1a737-308">RPC error occurs when connecting to a client computer</span></span>  
  
<span data-ttu-id="1a737-309">**問題**</span><span class="sxs-lookup"><span data-stu-id="1a737-309">**Problem**</span></span>  
 <span data-ttu-id="1a737-310">などのコマンドを実行すると**ssomanage-displayapp** *< applicationname\>*コンピューター、情報を取得するリモート SSO サーバーに接続しようとしましたここで、が表示されたら、。次のエラー: エラー: 0x800706BA: RPC サーバーは使用できません。</span><span class="sxs-lookup"><span data-stu-id="1a737-310">When you run a command such as **ssomanage -displayapp** *<applicationname\>*, where the computer attempt to connect to a remote SSO Server to retrieve the information, you receive the following error: ERROR: 0x800706BA: The RPC server is unavailable.</span></span>  
  
<span data-ttu-id="1a737-311">**原因**</span><span class="sxs-lookup"><span data-stu-id="1a737-311">**Cause**</span></span>  
 <span data-ttu-id="1a737-312">このエラーは、間違ったサーバー情報を指定した場合、またはリモート サーバーで SSO サービスを利用できない場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="1a737-312">This error occurs when you specify the wrong server information, or when the SSO Service is not available on the remote server.</span></span>  
  
<span data-ttu-id="1a737-313">**解決策**</span><span class="sxs-lookup"><span data-stu-id="1a737-313">**Resolution**</span></span>  
  
-   <span data-ttu-id="1a737-314">手順に従います[SSO Server を設定](../core/how-to-set-the-sso-server.md)正しい SSO サーバーに接続しているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="1a737-314">Follow the steps in [Set the SSO Server](../core/how-to-set-the-sso-server.md) to make sure you are connected to the correct SSO Server.</span></span>  
  
-   <span data-ttu-id="1a737-315">接続先の SSO サーバーで SSO サービスが有効になっており、実行されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="1a737-315">Make sure the SSO Service is enabled and running in the SSO Server to which you are connecting.</span></span>  
  
##### <a name="master-secret-is-missing-or-corrupt"></a><span data-ttu-id="1a737-316">マスター シークレットが見つからないか破損しています</span><span class="sxs-lookup"><span data-stu-id="1a737-316">Master Secret is missing or corrupt</span></span>  
  
<span data-ttu-id="1a737-317">**問題**</span><span class="sxs-lookup"><span data-stu-id="1a737-317">**Problem**</span></span>  
 <span data-ttu-id="1a737-318">マスター シークレットがない、または破損しています。</span><span class="sxs-lookup"><span data-stu-id="1a737-318">The master secret is missing or corrupt.</span></span> <span data-ttu-id="1a737-319">この問題は、主に構成中に発生します。</span><span class="sxs-lookup"><span data-stu-id="1a737-319">It normally generates during configuration.</span></span> <span data-ttu-id="1a737-320">シークレットがない場合、エンタープライズ シングル サインオン サービスが開始されるときに、以下のいずれかのメッセージがイベント ログに表示されます。</span><span class="sxs-lookup"><span data-stu-id="1a737-320">If the secret is missing, one of the following messages will display in the event log as the Enterprise Single Sign-On service starts.</span></span>  
  
```
MessageId=10520  
Severity=Warning  
SSO_WARN_NO_SECRETS  
MessageId=10565  
Severity=Error  
SSO_ERROR_SECRET_VALIDATE_FAILED  
MessageId=10521  
Severity=Error  
SSO_ERROR_SECRETS_NOT_LOADED  
```

<span data-ttu-id="1a737-321">**原因**</span><span class="sxs-lookup"><span data-stu-id="1a737-321">**Cause**</span></span>  
 <span data-ttu-id="1a737-322">この問題は、あるサービス アカウントでエンタープライズ シングル サインオン サービス (SSO) を実行中にシークレットを生成した後で、サービス アカウントが変更された場合に発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1a737-322">This problem can occur if a secret is generated while the Enterprise Single Sign-On service (SSO) was running under one service account, and then the service account was changed.</span></span> <span data-ttu-id="1a737-323">シークレットは、暗号化された形式でレジストリに保存されます。暗号化には、(ENTSSO を実行する) サービス アカウントの ID を基にしたキーが使用されます。</span><span class="sxs-lookup"><span data-stu-id="1a737-323">The secret is stored in the registry in encrypted form, and is encrypted using a key based on the identity of the service account (which ENTSSO runs under).</span></span>  
  
<span data-ttu-id="1a737-324">**解決策**</span><span class="sxs-lookup"><span data-stu-id="1a737-324">**Resolution**</span></span>  
 <span data-ttu-id="1a737-325">ENTSSO を実行しているサービス アカウントを、マスター シークレット作成時の元のサービス アカウントに変更します。</span><span class="sxs-lookup"><span data-stu-id="1a737-325">Change the service account ENTSSO is running under to the original service account when the master secret was created.</span></span>  
  
1.  <span data-ttu-id="1a737-326">マスター シークレットをバックアップします。</span><span class="sxs-lookup"><span data-stu-id="1a737-326">Back up the master secret.</span></span> <span data-ttu-id="1a737-327">参照してください[マスター シークレットをバックアップ](../core/how-to-back-up-the-master-secret.md)です。</span><span class="sxs-lookup"><span data-stu-id="1a737-327">See [Back Up the Master Secret](../core/how-to-back-up-the-master-secret.md).</span></span>  
  
2.  <span data-ttu-id="1a737-328">エンタープライズ シングル サインオン サービスを停止します。</span><span class="sxs-lookup"><span data-stu-id="1a737-328">Stop Enterprise Single Sign-On Services.</span></span>  
  
3.  <span data-ttu-id="1a737-329">サービス アカウントを変更します。</span><span class="sxs-lookup"><span data-stu-id="1a737-329">Change the service account.</span></span>  
  
4.  <span data-ttu-id="1a737-330">SSO を再起動します。破損したシークレットに関するイベント ログのエラーは一切無視します。</span><span class="sxs-lookup"><span data-stu-id="1a737-330">Restart SSO and ignore any event log errors about a corrupted secret.</span></span>  
  
5.  <span data-ttu-id="1a737-331">マスター シークレットを復元します。</span><span class="sxs-lookup"><span data-stu-id="1a737-331">Restore the master secret.</span></span> <span data-ttu-id="1a737-332">参照してください[マスター シークレットを復元](../core/how-to-restore-the-master-secret.md)です。</span><span class="sxs-lookup"><span data-stu-id="1a737-332">See [Restore the Master Secret](../core/how-to-restore-the-master-secret.md).</span></span>  
  
### <a name="custom-action"></a><span data-ttu-id="1a737-333">カスタム アクション</span><span class="sxs-lookup"><span data-stu-id="1a737-333">Custom Action</span></span>  
 <span data-ttu-id="1a737-334">このトピックでは、Windows Server ロゴ プログラムの BizTalk Server の認定に関する詳細を提供します。</span><span class="sxs-lookup"><span data-stu-id="1a737-334">This topic provides details about BizTalk Server certification for the Windows Server logo program.</span></span> <span data-ttu-id="1a737-335">BizTalk Server セットアップ操作時に次のカスタム動作を実行することが可能です。</span><span class="sxs-lookup"><span data-stu-id="1a737-335">The following custom actions might be performed during BizTalk Server Setup operations.</span></span>  
  
|<span data-ttu-id="1a737-336">カスタム アクション</span><span class="sxs-lookup"><span data-stu-id="1a737-336">Custom action</span></span>|<span data-ttu-id="1a737-337">Description</span><span class="sxs-lookup"><span data-stu-id="1a737-337">Description</span></span>|  
|-------------------|-----------------|  
|<span data-ttu-id="1a737-338">ReadComplusData</span><span class="sxs-lookup"><span data-stu-id="1a737-338">ReadComplusData</span></span>|<span data-ttu-id="1a737-339">カスタム COM+ テーブルを読み取り、XML ドキュメントを作成して、Complus_XML_Data プロパティに保存します。</span><span class="sxs-lookup"><span data-stu-id="1a737-339">Reads custom COM+ tables, creates XML document, and saves it in the Complus_XML_Data property.</span></span>|  
|<span data-ttu-id="1a737-340">SchedXmlConfig</span><span class="sxs-lookup"><span data-stu-id="1a737-340">SchedXmlConfig</span></span>|<span data-ttu-id="1a737-341">RFID データを持つコンピューターを構成するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="1a737-341">Used for configuring machines having RFID data.</span></span>|  
|<span data-ttu-id="1a737-342">CheckBaseEDI</span><span class="sxs-lookup"><span data-stu-id="1a737-342">CheckBaseEDI</span></span>|<span data-ttu-id="1a737-343">古いバージョンの EDI の存在を確認します。</span><span class="sxs-lookup"><span data-stu-id="1a737-343">Checks the presence of an old version of EDI</span></span>|  
|<span data-ttu-id="1a737-344">CheckMQSeries</span><span class="sxs-lookup"><span data-stu-id="1a737-344">CheckMQSeries</span></span>|<span data-ttu-id="1a737-345">MQSeries の存在を確認します。</span><span class="sxs-lookup"><span data-stu-id="1a737-345">Checks the presence of MQSeries</span></span>|  
|<span data-ttu-id="1a737-346">CheckNET30Vista</span><span class="sxs-lookup"><span data-stu-id="1a737-346">CheckNET30Vista</span></span>|<span data-ttu-id="1a737-347">WCF の存在を確認します。</span><span class="sxs-lookup"><span data-stu-id="1a737-347">Checks the presence of WCF</span></span>|  
|<span data-ttu-id="1a737-348">CheckWSSV3SP1</span><span class="sxs-lookup"><span data-stu-id="1a737-348">CheckWSSV3SP1</span></span>|<span data-ttu-id="1a737-349">Windows SharePoint Services 3.0 SP1 の存在を確認します。</span><span class="sxs-lookup"><span data-stu-id="1a737-349">Checks the presence of Windows SharePoint Services 3.0 SP1.</span></span>|  
|<span data-ttu-id="1a737-350">CheckWSSV4</span><span class="sxs-lookup"><span data-stu-id="1a737-350">CheckWSSV4</span></span>|<span data-ttu-id="1a737-351">Windows SharePoint Services 4 の存在を確認します。</span><span class="sxs-lookup"><span data-stu-id="1a737-351">Checks the presence of Windows SharePoint Services 4</span></span>|  
|<span data-ttu-id="1a737-352">GetFrameworkPath</span><span class="sxs-lookup"><span data-stu-id="1a737-352">GetFrameworkPath</span></span>|<span data-ttu-id="1a737-353">Microsoft .NET Framework 4 および 2.0 のインストール パスを保持するインストーラーのプロパティをインストーラーに設定します。</span><span class="sxs-lookup"><span data-stu-id="1a737-353">Sets installer properties in the installer that holds installation path to Microsoft .Net framework 4 and 2.0.</span></span>|  
|<span data-ttu-id="1a737-354">Set_BAMClientExcelDir</span><span class="sxs-lookup"><span data-stu-id="1a737-354">Set_BAMClientExcelDir</span></span>|<span data-ttu-id="1a737-355">Microsoft Office ライブラリ パスを保持するプロパティをインストーラーに設定するための Excel アプリケーション オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="1a737-355">Creates an Excel application object for setting a property to hold the Microsoft Office library path in the installer.</span></span>|  
|<span data-ttu-id="1a737-356">Set_CurrentUser</span><span class="sxs-lookup"><span data-stu-id="1a737-356">Set_CurrentUser</span></span>|<span data-ttu-id="1a737-357">現在のユーザーのドメイン\ユーザー名の情報を設定します。</span><span class="sxs-lookup"><span data-stu-id="1a737-357">Sets domain\username information of the current user</span></span>|  
|<span data-ttu-id="1a737-358">ViewInstallGuide</span><span class="sxs-lookup"><span data-stu-id="1a737-358">ViewInstallGuide</span></span>|<span data-ttu-id="1a737-359">インストール ソース ディレクトリから BizTalk Server インストール ガイドを起動します。</span><span class="sxs-lookup"><span data-stu-id="1a737-359">Launches the BizTalk Server installation guide from the installation source directory.</span></span>|  
|<span data-ttu-id="1a737-360">CA_CheckSTSLanguage</span><span class="sxs-lookup"><span data-stu-id="1a737-360">CA_CheckSTSLanguage</span></span>|<span data-ttu-id="1a737-361">WSS に設定されている言語と BizTalk に設定されている言語が同じである場合に、STS_Language_Property プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="1a737-361">Sets STS_Language_Property property when the language set for WSS and BizTalk are same.</span></span>|  
|<span data-ttu-id="1a737-362">CA_CleanupRegistry</span><span class="sxs-lookup"><span data-stu-id="1a737-362">CA_CleanupRegistry</span></span>|<span data-ttu-id="1a737-363">BizTalk Server をアンインストールすると、BizTalk Server 構成時に作成されたレジストリ エントリがクリーンアップされます。</span><span class="sxs-lookup"><span data-stu-id="1a737-363">When you uninstall BizTalk Server, it cleans the registry entries that were created during BizTalk Server configuration.</span></span>|  
|<span data-ttu-id="1a737-364">CA_CleanupRegistry_OldProducts</span><span class="sxs-lookup"><span data-stu-id="1a737-364">CA_CleanupRegistry_OldProducts</span></span>|<span data-ttu-id="1a737-365">古いバージョンの BizTalk Server に属し、BizTalk Server の新しいインストールに必要でないレジストリ エントリをクリーンアップします。</span><span class="sxs-lookup"><span data-stu-id="1a737-365">Cleans the registry entries that belong to an older version of BizTalk Server and are not required for a fresh installation of BizTalk Server.</span></span>|  
|<span data-ttu-id="1a737-366">CA_RemovePatches</span><span class="sxs-lookup"><span data-stu-id="1a737-366">CA_RemovePatches</span></span>|<span data-ttu-id="1a737-367">BizTalk Server のアンインストール時に Microsoft BizTalk Server 更新プログラムを削除します。</span><span class="sxs-lookup"><span data-stu-id="1a737-367">Removes Microsoft BizTalk Server updates when you uninstall BizTalk Server.</span></span>|  
|<span data-ttu-id="1a737-368">CA_ResolveWellKnownNames</span><span class="sxs-lookup"><span data-stu-id="1a737-368">CA_ResolveWellKnownNames</span></span>|<span data-ttu-id="1a737-369">既知の名前を持つインストーラーのプロパティを作成し、作成したプロパティに対応する SID を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="1a737-369">Creates installer properties with well-known names and assigns them their corresponding SID.</span></span>|  
|<span data-ttu-id="1a737-370">CA_SaveTargetVSVersionToRegistry</span><span class="sxs-lookup"><span data-stu-id="1a737-370">CA_SaveTargetVSVersionToRegistry</span></span>|<span data-ttu-id="1a737-371">サポートされている Visual Studio のバージョンの値を TargetVSVersion_Property プロパティに設定します。</span><span class="sxs-lookup"><span data-stu-id="1a737-371">Sets a TargetVSVersion_Property property to the value of a supported version of Visual Studio.</span></span>|  
|<span data-ttu-id="1a737-372">CA_StopServices</span><span class="sxs-lookup"><span data-stu-id="1a737-372">CA_StopServices</span></span>|<span data-ttu-id="1a737-373">IISAdmin サービス、ルール エンジン更新プログラム サービス、および EDI サブシステム サービスを停止します。</span><span class="sxs-lookup"><span data-stu-id="1a737-373">Stops IISAdmin, Rules Engine Update and EDI Subsystem services.</span></span>|  
|<span data-ttu-id="1a737-374">CleanupUsersKeys</span><span class="sxs-lookup"><span data-stu-id="1a737-374">CleanupUsersKeys</span></span>|<span data-ttu-id="1a737-375">HKEY_CURRENT_USER レジストリ キーから BizTalk Server 関連エントリを削除します。</span><span class="sxs-lookup"><span data-stu-id="1a737-375">Removes BizTalk Server related entries from the HKEY_CURRENT_USER registry key.</span></span>|  
|<span data-ttu-id="1a737-376">DevEnvRunning</span><span class="sxs-lookup"><span data-stu-id="1a737-376">DevEnvRunning</span></span>|<span data-ttu-id="1a737-377">Visual Studio が実行中かどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="1a737-377">Checks whether Visual Studio is running</span></span>|  
|<span data-ttu-id="1a737-378">ValidateINSTALLDIR</span><span class="sxs-lookup"><span data-stu-id="1a737-378">ValidateINSTALLDIR</span></span>|<span data-ttu-id="1a737-379">BizTalk Server のインストール ディレクトリ形式を確認します。</span><span class="sxs-lookup"><span data-stu-id="1a737-379">Validates BizTalk Server installation directory format</span></span>|  
|<span data-ttu-id="1a737-380">StartHostInstances</span><span class="sxs-lookup"><span data-stu-id="1a737-380">StartHostInstances</span></span>|<span data-ttu-id="1a737-381">BizTalk Server ホスト インスタンスを開始します。</span><span class="sxs-lookup"><span data-stu-id="1a737-381">Starts BizTalk Server Host Instances.</span></span>|  
|<span data-ttu-id="1a737-382">StopHostInstances</span><span class="sxs-lookup"><span data-stu-id="1a737-382">StopHostInstances</span></span>|<span data-ttu-id="1a737-383">BizTalk Server ホスト インスタンスを停止します。</span><span class="sxs-lookup"><span data-stu-id="1a737-383">Stops BizTalk Server Host Instances.</span></span>|  
|<span data-ttu-id="1a737-384">MQSUnConfig</span><span class="sxs-lookup"><span data-stu-id="1a737-384">MQSUnConfig</span></span>|<span data-ttu-id="1a737-385">MQSeries エージェントの構成を解除するために MQSeries 構成ウィザードを起動します。</span><span class="sxs-lookup"><span data-stu-id="1a737-385">Launches MQSeries Configuration wizard for un-configuring MQSeries agent.</span></span>|  
|<span data-ttu-id="1a737-386">LaunchConfigFmk</span><span class="sxs-lookup"><span data-stu-id="1a737-386">LaunchConfigFmk</span></span>|<span data-ttu-id="1a737-387">BizTalk Server 構成ウィザードを起動します。</span><span class="sxs-lookup"><span data-stu-id="1a737-387">Launches BizTalk Server Configuration Wizard</span></span>|  
|<span data-ttu-id="1a737-388">CHKASPNET</span><span class="sxs-lookup"><span data-stu-id="1a737-388">CHKASPNET</span></span>|<span data-ttu-id="1a737-389">ASP.NET のインストール状態を確認します。</span><span class="sxs-lookup"><span data-stu-id="1a737-389">Checks the install state of ASP.NET</span></span>|  
|<span data-ttu-id="1a737-390">CHKIIS</span><span class="sxs-lookup"><span data-stu-id="1a737-390">CHKIIS</span></span>|<span data-ttu-id="1a737-391">IIS のインストール状態を確認します。</span><span class="sxs-lookup"><span data-stu-id="1a737-391">Checks the install state of IIS</span></span>|  
|<span data-ttu-id="1a737-392">TBExpired</span><span class="sxs-lookup"><span data-stu-id="1a737-392">TBExpired</span></span>|<span data-ttu-id="1a737-393">BizTalk Server の TimeBomb の有効期限が終了しているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="1a737-393">Checks if the BizTalk Server TimeBomb has expired</span></span>|  
|<span data-ttu-id="1a737-394">BrandSKU</span><span class="sxs-lookup"><span data-stu-id="1a737-394">BrandSKU</span></span>|<span data-ttu-id="1a737-395">SKU のインストールに依存する BizTalk Server の timebomb の値を更新します。</span><span class="sxs-lookup"><span data-stu-id="1a737-395">Updates the value of BizTalk Server timebomb which depends on SKU installation.</span></span>|  
|<span data-ttu-id="1a737-396">CA_ERROR</span><span class="sxs-lookup"><span data-stu-id="1a737-396">CA_ERROR</span></span>|<span data-ttu-id="1a737-397">インストール エラーを返します。</span><span class="sxs-lookup"><span data-stu-id="1a737-397">Returns installation failure</span></span>|  
|<span data-ttu-id="1a737-398">InstallComplus</span><span class="sxs-lookup"><span data-stu-id="1a737-398">InstallComplus</span></span>|<span data-ttu-id="1a737-399">Complus アプリケーションとコンポーネントをインストールします。</span><span class="sxs-lookup"><span data-stu-id="1a737-399">Installs Complus applications and components.</span></span>|  
|<span data-ttu-id="1a737-400">BAM_Add_Perf_Silent</span><span class="sxs-lookup"><span data-stu-id="1a737-400">BAM_Add_Perf_Silent</span></span>|<span data-ttu-id="1a737-401">BAM のパフォーマンス カウンターをインストールします。</span><span class="sxs-lookup"><span data-stu-id="1a737-401">Installs performance counters for BAM</span></span>|  
|<span data-ttu-id="1a737-402">RegsvcsApplicationDeployment</span><span class="sxs-lookup"><span data-stu-id="1a737-402">RegsvcsApplicationDeployment</span></span>|<span data-ttu-id="1a737-403">BizTalk 展開 COM+ アプリケーション DLL に対して Regsvcs.exe (.NET サービス インストール ツール) を実行します。</span><span class="sxs-lookup"><span data-stu-id="1a737-403">Runs Regsvcs.exe (.NET Services Installation Tool) on BizTalk Deployment COM+ application DLLs</span></span>|  
|<span data-ttu-id="1a737-404">RegsvcsDeployment</span><span class="sxs-lookup"><span data-stu-id="1a737-404">RegsvcsDeployment</span></span>|<span data-ttu-id="1a737-405">DLL に対して Regsvcs.exe を実行します。</span><span class="sxs-lookup"><span data-stu-id="1a737-405">Runs Regsvcs.exe on DLLs</span></span>|  
|<span data-ttu-id="1a737-406">RegsvcsMQSAdapter</span><span class="sxs-lookup"><span data-stu-id="1a737-406">RegsvcsMQSAdapter</span></span>|<span data-ttu-id="1a737-407">DLL に対して Regsvcs.exe を実行します。</span><span class="sxs-lookup"><span data-stu-id="1a737-407">Runs Regsvcs.exe on DLLs</span></span>|  
|<span data-ttu-id="1a737-408">RegsvcsSQLAdapter</span><span class="sxs-lookup"><span data-stu-id="1a737-408">RegsvcsSQLAdapter</span></span>|<span data-ttu-id="1a737-409">DLL に対して Regsvcs.exe を実行します。</span><span class="sxs-lookup"><span data-stu-id="1a737-409">Runs Regsvcs.exe on DLLs</span></span>|  
|<span data-ttu-id="1a737-410">WMI_Add_MSBTS_Silent</span><span class="sxs-lookup"><span data-stu-id="1a737-410">WMI_Add_MSBTS_Silent</span></span>|<span data-ttu-id="1a737-411">BizTalk Server の名前空間とクラスを WMI に登録します。</span><span class="sxs-lookup"><span data-stu-id="1a737-411">Registers BizTalk Server namespace and classes to WMI.</span></span>|  
|<span data-ttu-id="1a737-412">LaunchConfigFmk_SlashUP</span><span class="sxs-lookup"><span data-stu-id="1a737-412">LaunchConfigFmk_SlashUP</span></span>|<span data-ttu-id="1a737-413">BizTalk Server の構成を解除します。</span><span class="sxs-lookup"><span data-stu-id="1a737-413">Un-configures BizTalk Server</span></span>|  
|<span data-ttu-id="1a737-414">CleanupComplus</span><span class="sxs-lookup"><span data-stu-id="1a737-414">CleanupComplus</span></span>|<span data-ttu-id="1a737-415">Complus アプリケーションとコンポーネントをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="1a737-415">Uninstalls Complus Applications and components.</span></span>|  
|<span data-ttu-id="1a737-416">RemoveSKU</span><span class="sxs-lookup"><span data-stu-id="1a737-416">RemoveSKU</span></span>|<span data-ttu-id="1a737-417">BizTalk Server TimeBomb データを削除します。</span><span class="sxs-lookup"><span data-stu-id="1a737-417">Removes BizTalk Server TimeBomb data.</span></span>|  
|<span data-ttu-id="1a737-418">BAM_Remove_Perf</span><span class="sxs-lookup"><span data-stu-id="1a737-418">BAM_Remove_Perf</span></span>|<span data-ttu-id="1a737-419">BAM のパフォーマンス カウンターをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="1a737-419">Uninstalls performance counters for BAM.</span></span>|  
|<span data-ttu-id="1a737-420">LoadBTSCounters</span><span class="sxs-lookup"><span data-stu-id="1a737-420">LoadBTSCounters</span></span>|<span data-ttu-id="1a737-421">BizTalk Server パフォーマンス カウンターを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="1a737-421">Loads BizTalk Server performance counters.</span></span>|  
|<span data-ttu-id="1a737-422">RegisterBtprojExtn</span><span class="sxs-lookup"><span data-stu-id="1a737-422">RegisterBtprojExtn</span></span>|<span data-ttu-id="1a737-423">BizTalk プロジェクト ファイル (.btproj) の拡張子を登録します。</span><span class="sxs-lookup"><span data-stu-id="1a737-423">Registers BizTalk project file (.btproj) extension.</span></span>|  
|<span data-ttu-id="1a737-424">UnRegisterBtprojExtn</span><span class="sxs-lookup"><span data-stu-id="1a737-424">UnRegisterBtprojExtn</span></span>|<span data-ttu-id="1a737-425">BizTalk プロジェクト ファイル (.btproj) の拡張子を登録解除します。</span><span class="sxs-lookup"><span data-stu-id="1a737-425">Un-registers BizTalk project file (.btproj) extension.</span></span>|  
|<span data-ttu-id="1a737-426">UnRegsvcsApplicationDeployment</span><span class="sxs-lookup"><span data-stu-id="1a737-426">UnRegsvcsApplicationDeployment</span></span>|<span data-ttu-id="1a737-427">BizTalk Server のアンインストール時に、特定の DLL に対して Regsvcs.exe を実行します。</span><span class="sxs-lookup"><span data-stu-id="1a737-427">Runs Regsvcs.exe on certain DLLs when you uninstall BizTalk Server</span></span>|  
|<span data-ttu-id="1a737-428">UnRegsvcsDeployment</span><span class="sxs-lookup"><span data-stu-id="1a737-428">UnRegsvcsDeployment</span></span>|<span data-ttu-id="1a737-429">BizTalk Server のアンインストール時に、特定の DLL に対して Regsvcs.exe を実行します。</span><span class="sxs-lookup"><span data-stu-id="1a737-429">Runs Regsvcs.exe on certain DLLs when you uninstall BizTalk Server</span></span>|  
|<span data-ttu-id="1a737-430">UnRegsvcsMQSAdapter</span><span class="sxs-lookup"><span data-stu-id="1a737-430">UnRegsvcsMQSAdapter</span></span>|<span data-ttu-id="1a737-431">BizTalk Server のアンインストール時に、特定の DLL に対して Regsvcs.exe を実行します。</span><span class="sxs-lookup"><span data-stu-id="1a737-431">Runs Regsvcs.exe on certain DLLs when you uninstall BizTalk Server</span></span>|  
|<span data-ttu-id="1a737-432">UnRegsvcsSQLAdapter</span><span class="sxs-lookup"><span data-stu-id="1a737-432">UnRegsvcsSQLAdapter</span></span>|<span data-ttu-id="1a737-433">BizTalk Server のアンインストール時に、特定の DLL に対して Regsvcs.exe を実行します。</span><span class="sxs-lookup"><span data-stu-id="1a737-433">Runs Regsvcs.exe on certain DLLs when you uninstall BizTalk Server</span></span>|  
|<span data-ttu-id="1a737-434">UnloadBTSCounters</span><span class="sxs-lookup"><span data-stu-id="1a737-434">UnloadBTSCounters</span></span>|<span data-ttu-id="1a737-435">BizTalk Server パフォーマンス カウンターをアンロードします。</span><span class="sxs-lookup"><span data-stu-id="1a737-435">Unloads BizTalk Server performance counters.</span></span>|  
|<span data-ttu-id="1a737-436">WMI_Remove_MSBTS</span><span class="sxs-lookup"><span data-stu-id="1a737-436">WMI_Remove_MSBTS</span></span>|<span data-ttu-id="1a737-437">WMI から BizTalk Server 名前空間を削除します。</span><span class="sxs-lookup"><span data-stu-id="1a737-437">Removes BizTalk Server namespace from WMI.</span></span>|  
|<span data-ttu-id="1a737-438">RegisterComsvcs</span><span class="sxs-lookup"><span data-stu-id="1a737-438">RegisterComsvcs</span></span>|<span data-ttu-id="1a737-439">comsvcs.dll に対して regsvr32.exe をサイレント実行します。</span><span class="sxs-lookup"><span data-stu-id="1a737-439">Runs regsvr32.exe on comsvcs.dll silently.</span></span>|  
|<span data-ttu-id="1a737-440">DevenvSetupUninstall</span><span class="sxs-lookup"><span data-stu-id="1a737-440">DevenvSetupUninstall</span></span>|<span data-ttu-id="1a737-441">DevEnv.exe /Setup/resetskippkgs を実行します。</span><span class="sxs-lookup"><span data-stu-id="1a737-441">Runs DevEnv.exe /Setup/resetskippkgs.</span></span>|  
|<span data-ttu-id="1a737-442">RollbackComplus</span><span class="sxs-lookup"><span data-stu-id="1a737-442">RollbackComplus</span></span>|<span data-ttu-id="1a737-443">Complus アプリケーションとコンポーネントのインストールをロールバックします。</span><span class="sxs-lookup"><span data-stu-id="1a737-443">Rollbacks the installation of Complus applications and components.</span></span>|  
|<span data-ttu-id="1a737-444">ResRegsvcsMQSAdapter</span><span class="sxs-lookup"><span data-stu-id="1a737-444">ResRegsvcsMQSAdapter</span></span>|<span data-ttu-id="1a737-445">指定されたバイナリで regsvcs.exe を実行します。</span><span class="sxs-lookup"><span data-stu-id="1a737-445">Runs regsvcs.exe on a given binary</span></span>|  
|<span data-ttu-id="1a737-446">ResRegsvcsSQLAdapter</span><span class="sxs-lookup"><span data-stu-id="1a737-446">ResRegsvcsSQLAdapter</span></span>|<span data-ttu-id="1a737-447">指定されたバイナリで regsvcs.exe を実行します。</span><span class="sxs-lookup"><span data-stu-id="1a737-447">Runs regsvcs.exe on a given binary</span></span>|  
|<span data-ttu-id="1a737-448">RestoreRegsvcsApplicationDeployment</span><span class="sxs-lookup"><span data-stu-id="1a737-448">RestoreRegsvcsApplicationDeployment</span></span>|<span data-ttu-id="1a737-449">フレームワークのパスを Microsoft.BizTalk.ApplicationDeployment.Engine.dll に付加します。</span><span class="sxs-lookup"><span data-stu-id="1a737-449">Appends the path of framework with Microsoft.BizTalk.ApplicationDeployment.Engine.dll.</span></span>|  
|<span data-ttu-id="1a737-450">RestoreRegsvcsDeployment</span><span class="sxs-lookup"><span data-stu-id="1a737-450">RestoreRegsvcsDeployment</span></span>|<span data-ttu-id="1a737-451">フレームワークのパスを Microsoft.BizTalk.ApplicationDeployment.Engine.dll に付加します。</span><span class="sxs-lookup"><span data-stu-id="1a737-451">Appends the path of framework with Microsoft.BizTalk.ApplicationDeployment.Engine.dll.</span></span>|  
|<span data-ttu-id="1a737-452">BrandSKURollback</span><span class="sxs-lookup"><span data-stu-id="1a737-452">BrandSKURollback</span></span>|<span data-ttu-id="1a737-453">インストール エラーが発生した場合、登録した SKU 情報をロールバックします。</span><span class="sxs-lookup"><span data-stu-id="1a737-453">Rollbacks registered SKU information if installation failure occurs.</span></span>|  
|<span data-ttu-id="1a737-454">CA_RestartServices_rollback</span><span class="sxs-lookup"><span data-stu-id="1a737-454">CA_RestartServices_rollback</span></span>|<span data-ttu-id="1a737-455">停止したサービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="1a737-455">Restarts the stopped services.</span></span>|  
|<span data-ttu-id="1a737-456">RemoveSKURollback</span><span class="sxs-lookup"><span data-stu-id="1a737-456">RemoveSKURollback</span></span>|<span data-ttu-id="1a737-457">レジストリの SKU 値を更新します。</span><span class="sxs-lookup"><span data-stu-id="1a737-457">Updates the SKU values from the registry.</span></span>|  
|<span data-ttu-id="1a737-458">BAM_Res_Perf_Silent</span><span class="sxs-lookup"><span data-stu-id="1a737-458">BAM_Res_Perf_Silent</span></span>|<span data-ttu-id="1a737-459">サイレント インストール時に、Microsoft.BizTalk.Bam.EventObservation.dll を BAM パフォーマンス カウンター DLL として登録します。</span><span class="sxs-lookup"><span data-stu-id="1a737-459">Registers Microsoft.BizTalk.Bam.EventObservation.dll as the BAM performance counter DLLs during silent installation.</span></span>|  
|<span data-ttu-id="1a737-460">BAM_Rollback_Perf</span><span class="sxs-lookup"><span data-stu-id="1a737-460">BAM_Rollback_Perf</span></span>|<span data-ttu-id="1a737-461">BAM パフォーマンス カウンター DLL としての Microsoft.BizTalk.Bam.EventObservation.dll の登録を解除します。</span><span class="sxs-lookup"><span data-stu-id="1a737-461">Unregisters  Microsoft.BizTalk.Bam.EventObservation.dll as the BAM performance counter DLL</span></span>|  
|<span data-ttu-id="1a737-462">RBKRegsvcsMQSAdapter</span><span class="sxs-lookup"><span data-stu-id="1a737-462">RBKRegsvcsMQSAdapter</span></span>|<span data-ttu-id="1a737-463">指定されたバイナリに対して regsvcs.exe を実行します。</span><span class="sxs-lookup"><span data-stu-id="1a737-463">Runs regsvcs.exe on a given binary.</span></span>|  
|<span data-ttu-id="1a737-464">RBKRegsvcsSQLAdapter</span><span class="sxs-lookup"><span data-stu-id="1a737-464">RBKRegsvcsSQLAdapter</span></span>|<span data-ttu-id="1a737-465">指定されたバイナリに対して regsvcs.exe を実行します。</span><span class="sxs-lookup"><span data-stu-id="1a737-465">Runs regsvcs.exe on a given binary.</span></span>|  
|<span data-ttu-id="1a737-466">RestoreBTSCounters</span><span class="sxs-lookup"><span data-stu-id="1a737-466">RestoreBTSCounters</span></span>|<span data-ttu-id="1a737-467">パフォーマンス カウンターの .ini ファイル名を使用してプロパティを復元します。</span><span class="sxs-lookup"><span data-stu-id="1a737-467">Restores the property with the performance counter .ini file name.</span></span>|  
|<span data-ttu-id="1a737-468">RollbackBTSCounters</span><span class="sxs-lookup"><span data-stu-id="1a737-468">RollbackBTSCounters</span></span>|<span data-ttu-id="1a737-469">unlodctr BTSSvc.3.0 コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="1a737-469">Runs command unlodctr BTSSvc.3.0.</span></span>|  
|<span data-ttu-id="1a737-470">RollbackRegsvcsApplicationDeployment</span><span class="sxs-lookup"><span data-stu-id="1a737-470">RollbackRegsvcsApplicationDeployment</span></span>|<span data-ttu-id="1a737-471">[FrameworkPath] 設定 (& m); #124[INSTALLDIR]失敗したインストール シナリオの Microsoft.BizTalk.ApplicationDeployment.Engine.dll します。</span><span class="sxs-lookup"><span data-stu-id="1a737-471">Sets up [FrameworkPath]&#124;[INSTALLDIR]Microsoft.BizTalk.ApplicationDeployment.Engine.dll for the failed installation scenarios.</span></span>|  
|<span data-ttu-id="1a737-472">RollbackRegsvcsDeployment</span><span class="sxs-lookup"><span data-stu-id="1a737-472">RollbackRegsvcsDeployment</span></span>|<span data-ttu-id="1a737-473">アンインストール/ロールバック シナリオで regsvcs.exe を起動します。</span><span class="sxs-lookup"><span data-stu-id="1a737-473">Invokes regsvcs.exe during uninstall/rollback scenarios.</span></span>|  
|<span data-ttu-id="1a737-474">WMI_Restore_MSBTS_Silent</span><span class="sxs-lookup"><span data-stu-id="1a737-474">WMI_Restore_MSBTS_Silent</span></span>|<span data-ttu-id="1a737-475">mofcomp を呼び出して WMI スキーマを登録します。</span><span class="sxs-lookup"><span data-stu-id="1a737-475">Calls mofcomp to register WMI schemas</span></span>|  
|<span data-ttu-id="1a737-476">WMI_Rollback_MSBTS</span><span class="sxs-lookup"><span data-stu-id="1a737-476">WMI_Rollback_MSBTS</span></span>|<span data-ttu-id="1a737-477">WMI から BizTalk Server 名前空間を削除します。</span><span class="sxs-lookup"><span data-stu-id="1a737-477">Removes BizTalk Server namespace from WMI.</span></span>|  
|<span data-ttu-id="1a737-478">CA_RestartServices_commit</span><span class="sxs-lookup"><span data-stu-id="1a737-478">CA_RestartServices_commit</span></span>|<span data-ttu-id="1a737-479">停止したサービスを再開します。</span><span class="sxs-lookup"><span data-stu-id="1a737-479">Restarts the stopped services</span></span>|  
|<span data-ttu-id="1a737-480">DevenvSetup</span><span class="sxs-lookup"><span data-stu-id="1a737-480">DevenvSetup</span></span>|<span data-ttu-id="1a737-481">BizTalk Server のインストール プロセスおよびアンインストール プロセスの両方で DevEnv.exe /Setup /resetskippkgs を実行します。</span><span class="sxs-lookup"><span data-stu-id="1a737-481">Runs DevEnv.exe /Setup /resetskippkgs both during BizTalk Server install/uninstall process.</span></span>|  
|<span data-ttu-id="1a737-482">ExecXmlConfig</span><span class="sxs-lookup"><span data-stu-id="1a737-482">ExecXmlConfig</span></span>|<span data-ttu-id="1a737-483">RFID 関連データの machine.config で構成を変更するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="1a737-483">Used to make configuration changes to machine.config for RFID related data.</span></span>|  
|<span data-ttu-id="1a737-484">ExecXmlConfigRollback</span><span class="sxs-lookup"><span data-stu-id="1a737-484">ExecXmlConfigRollback</span></span>|<span data-ttu-id="1a737-485">RFID 関連データの machine.config で構成を変更するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="1a737-485">Used to make configuration changes to machine.config for RFID related data.</span></span>|  
  
#### <a name="running-biztalk-components"></a><span data-ttu-id="1a737-486">BizTalk コンポーネントの実行</span><span class="sxs-lookup"><span data-stu-id="1a737-486">Running BizTalk Components</span></span>  
 <span data-ttu-id="1a737-487">次の表は、管理者特権または使用可能な最高の特権を使用して実行する必要のある BizTalk コンポーネントの一覧です。</span><span class="sxs-lookup"><span data-stu-id="1a737-487">The following table lists BizTalk components that must be run using administrative privileges or with highest available privilege.</span></span>  
  
|<span data-ttu-id="1a737-488">フォルダー パス</span><span class="sxs-lookup"><span data-stu-id="1a737-488">Folder path</span></span>|<span data-ttu-id="1a737-489">ファイル名</span><span class="sxs-lookup"><span data-stu-id="1a737-489">File name</span></span>|<span data-ttu-id="1a737-490">ユーザー特権</span><span class="sxs-lookup"><span data-stu-id="1a737-490">User privileges</span></span>|  
|-----------------|---------------|---------------------|  
|<span data-ttu-id="1a737-491">\Program files (x86) \Common Files\Microsoft shared\Help 9\Microsoft Document エクスプ ローラー 2008</span><span class="sxs-lookup"><span data-stu-id="1a737-491">\Program Files (x86)\Common Files\Microsoft shared\Help 9\Microsoft Document Explorer 2008</span></span>|<span data-ttu-id="1a737-492">Install.exe</span><span class="sxs-lookup"><span data-stu-id="1a737-492">Install.exe</span></span>|<span data-ttu-id="1a737-493">使用可能な最高の特権</span><span class="sxs-lookup"><span data-stu-id="1a737-493">Highest available privilege</span></span>|  
|<span data-ttu-id="1a737-494">\Program files (x86) \Microsoft BizTalk Server*バージョン*</span><span class="sxs-lookup"><span data-stu-id="1a737-494">\Program Files (x86)\Microsoft BizTalk Server *your version*</span></span>|<span data-ttu-id="1a737-495">BTSHatApp.exe</span><span class="sxs-lookup"><span data-stu-id="1a737-495">BTSHatApp.exe</span></span>|<span data-ttu-id="1a737-496">使用可能な最高の特権</span><span class="sxs-lookup"><span data-stu-id="1a737-496">Highest available privilege</span></span>|  
|<span data-ttu-id="1a737-497">\Program files (x86) \Microsoft BizTalk Server*バージョン*</span><span class="sxs-lookup"><span data-stu-id="1a737-497">\Program Files (x86)\Microsoft BizTalk Server *your version*</span></span>|<span data-ttu-id="1a737-498">BTSMMCLauncher.exe</span><span class="sxs-lookup"><span data-stu-id="1a737-498">BTSMMCLauncher.exe</span></span>|<span data-ttu-id="1a737-499">使用可能な最高の特権</span><span class="sxs-lookup"><span data-stu-id="1a737-499">Highest available privilege</span></span>|  
|<span data-ttu-id="1a737-500">\Program files (x86) \Microsoft BizTalk Server*バージョン*</span><span class="sxs-lookup"><span data-stu-id="1a737-500">\Program Files (x86)\Microsoft BizTalk Server *your version*</span></span>|<span data-ttu-id="1a737-501">BtsWcfServicePublishingWizard.exe</span><span class="sxs-lookup"><span data-stu-id="1a737-501">BtsWcfServicePublishingWizard.exe</span></span>|<span data-ttu-id="1a737-502">使用可能な最高の特権</span><span class="sxs-lookup"><span data-stu-id="1a737-502">Highest available privilege</span></span>|  
|<span data-ttu-id="1a737-503">\Program files (x86) \Microsoft BizTalk Server*バージョン*</span><span class="sxs-lookup"><span data-stu-id="1a737-503">\Program Files (x86)\Microsoft BizTalk Server *your version*</span></span>|<span data-ttu-id="1a737-504">BTSWebSvcWiz.exe</span><span class="sxs-lookup"><span data-stu-id="1a737-504">BTSWebSvcWiz.exe</span></span>|<span data-ttu-id="1a737-505">使用可能な最高の特権</span><span class="sxs-lookup"><span data-stu-id="1a737-505">Highest available privilege</span></span>|  
|<span data-ttu-id="1a737-506">\Program files (x86) \Microsoft BizTalk Server*バージョン*</span><span class="sxs-lookup"><span data-stu-id="1a737-506">\Program Files (x86)\Microsoft BizTalk Server *your version*</span></span>|<span data-ttu-id="1a737-507">Configuration.exe</span><span class="sxs-lookup"><span data-stu-id="1a737-507">Configuration.exe</span></span>|<span data-ttu-id="1a737-508">使用可能な最高の特権</span><span class="sxs-lookup"><span data-stu-id="1a737-508">Highest available privilege</span></span>|  
|<span data-ttu-id="1a737-509">\Program files (x86) \Microsoft BizTalk Server*バージョン*</span><span class="sxs-lookup"><span data-stu-id="1a737-509">\Program Files (x86)\Microsoft BizTalk Server *your version*</span></span>|<span data-ttu-id="1a737-510">REDeployWiz.exe</span><span class="sxs-lookup"><span data-stu-id="1a737-510">REDeployWiz.exe</span></span>|<span data-ttu-id="1a737-511">使用可能な最高の特権</span><span class="sxs-lookup"><span data-stu-id="1a737-511">Highest available privilege</span></span>|  
|<span data-ttu-id="1a737-512">\Program files (x86) \Microsoft BizTalk Server*バージョン*</span><span class="sxs-lookup"><span data-stu-id="1a737-512">\Program Files (x86)\Microsoft BizTalk Server *your version*</span></span>|<span data-ttu-id="1a737-513">Setup.exe</span><span class="sxs-lookup"><span data-stu-id="1a737-513">Setup.exe</span></span>|<span data-ttu-id="1a737-514">管理者特権</span><span class="sxs-lookup"><span data-stu-id="1a737-514">Administrative privilege</span></span>|  
|<span data-ttu-id="1a737-515">\Program files (x86) \Microsoft BizTalk Server*バージョン*\XSD Schema\EDI</span><span class="sxs-lookup"><span data-stu-id="1a737-515">\Program Files (x86)\Microsoft BizTalk Server *your version*\XSD Schema\EDI</span></span>|<span data-ttu-id="1a737-516">MicrosoftEdiXSDTemplates.exe</span><span class="sxs-lookup"><span data-stu-id="1a737-516">MicrosoftEdiXSDTemplates.exe</span></span>|<span data-ttu-id="1a737-517">自己展開形式 .exe ファイル</span><span class="sxs-lookup"><span data-stu-id="1a737-517">Self-extracting .exe file.</span></span>|  
|<span data-ttu-id="1a737-518">\Program files (x86) \Microsoft UDDI Services\config</span><span class="sxs-lookup"><span data-stu-id="1a737-518">\Program Files (x86)\Microsoft UDDI Services\config</span></span>|<span data-ttu-id="1a737-519">Configuration .exe</span><span class="sxs-lookup"><span data-stu-id="1a737-519">Configuration .exe</span></span>|<span data-ttu-id="1a737-520">管理者特権</span><span class="sxs-lookup"><span data-stu-id="1a737-520">Administrative privilege</span></span>|  
|<span data-ttu-id="1a737-521">\Program Files\ Microsoft BizTalk rfid \bin</span><span class="sxs-lookup"><span data-stu-id="1a737-521">\Program Files\ Microsoft BizTalk RFID\bin</span></span>|<span data-ttu-id="1a737-522">BTSMMCLauncher.exe</span><span class="sxs-lookup"><span data-stu-id="1a737-522">BTSMMCLauncher.exe</span></span>|<span data-ttu-id="1a737-523">使用可能な最高の特権</span><span class="sxs-lookup"><span data-stu-id="1a737-523">Highest available privilege</span></span>|  
|<span data-ttu-id="1a737-524">\Program Files\Microsoft BizTalk RFID\BREConfi 再構成</span><span class="sxs-lookup"><span data-stu-id="1a737-524">\Program Files\Microsoft BizTalk RFID\BREConfi guration</span></span>|<span data-ttu-id="1a737-525">Configuration .exe</span><span class="sxs-lookup"><span data-stu-id="1a737-525">Configuration .exe</span></span>|<span data-ttu-id="1a737-526">管理者特権</span><span class="sxs-lookup"><span data-stu-id="1a737-526">Administrative privilege</span></span>|  
