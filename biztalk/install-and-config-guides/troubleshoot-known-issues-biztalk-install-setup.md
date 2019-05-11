---
title: インストールの既知の問題 |Microsoft Docs
description: 既知の問題と一般的な問題と解決策をインストールすると、BizTalk Server の構成
ms.custom: ''
ms.date: 11/30/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e4d0e707-6b9e-49e1-9f17-19b3bac1229e
caps.latest.revision: 27
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5a38d3665e71ebc9e11c133dde49ad070f2aa0e3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397101"
---
# <a name="troubleshoot-biztalk-server-setup"></a><span data-ttu-id="5bc9c-103">BizTalk Server のセットアップをトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-103">Troubleshoot BizTalk Server Setup</span></span>

## <a name="introduction"></a><span data-ttu-id="5bc9c-104">概要</span><span class="sxs-lookup"><span data-stu-id="5bc9c-104">Introduction</span></span>  
 <span data-ttu-id="5bc9c-105">このトラブルシューティング ガイドには、BizTalk Server のインストール中に発生する可能性の最も一般的な問題と同様に既知の問題が一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-105">This Troubleshooting Guide lists  known issues as well as the most common problems you may encounter while installing BizTalk Server.</span></span> <span data-ttu-id="5bc9c-106">このガイドでは、Windows Server ロゴ プログラムの BizTalk Server の認定に関する詳細情報を提供するカスタム動作も含まれています。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-106">This guide also includes Custom actions which provides details about BizTalk Server certification for the Windows Server logo program.</span></span>  <span data-ttu-id="5bc9c-107">これは、BizTalk Server セットアップ操作中に実行することがカスタム アクションの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-107">It provides you a list of custom actions that might be performed during BizTalk Server Setup operation.</span></span>  
  
## <a name="review-install-steps"></a><span data-ttu-id="5bc9c-108">インストールの手順を確認してください。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-108">Review install steps</span></span>  
<span data-ttu-id="5bc9c-109">BizTalk Server コンピューターを正しく準備前に、BizTalk Server がインストールされている場合、または BizTalk Server の以前のインストールが完全にアンインストールされない新しいインストールが試みられる前にあるために、BizTalk Server のセットアップに関する問題の大部分が発生します。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-109">The majority of BizTalk Server setup problems occur because the BizTalk Server computer was not properly prepared before BizTalk Server was installed, or a previous installation of BizTalk Server was not fully uninstalled before a new installation was attempted.</span></span>  
  
<span data-ttu-id="5bc9c-110">2 つのチェックリスト、下のコンピューターが BizTalk Server をサポートするために正しく構成されていることを確認する、BizTalk Server インストール ガイドで検索することもできます。 これを確認します。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-110">Review the two checklists below, which you can also find in the BizTalk Server Installation Guides, to ensure that your computer(s) are properly configured to support BizTalk Server.</span></span> <span data-ttu-id="5bc9c-111">この情報を確認した後、セットアップが成功しない場合、このドキュメントの残りの部分では、トラブルシューティングのヒントが役に立ちます。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-111">If, after reviewing this information, your setup still does not succeed, the troubleshooting tips in the rest of this document may be useful.</span></span>  
  
1. <span data-ttu-id="5bc9c-112">前提条件のソフトウェアとプログラムをインストールします。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-112">Install prerequisite software and programs:</span></span>

    * [<span data-ttu-id="5bc9c-113">BizTalk Server 2016</span><span class="sxs-lookup"><span data-stu-id="5bc9c-113">BizTalk Server 2016</span></span>](set-up-and-install-prerequisites-for-biztalk-server-2016.md)
    * [<span data-ttu-id="5bc9c-114">BizTalk Server 2013 R2 & 2013</span><span class="sxs-lookup"><span data-stu-id="5bc9c-114">BizTalk Server 2013 R2 & 2013</span></span>](prepare-your-computer-for-installation.md)

2. <span data-ttu-id="5bc9c-115">インストールし、BizTalk Server を構成します。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-115">Install and configure BizTalk Server:</span></span>  

    1. <span data-ttu-id="5bc9c-116">BizTalk Server をインストールします。[BizTalk 2016](install-biztalk-server-2016.md) 、 [BizTalk 2013 R2/2013](install-biztalk-server-2013-and-2013-r2.md)</span><span class="sxs-lookup"><span data-stu-id="5bc9c-116">Install BizTalk Server: [BizTalk 2016](install-biztalk-server-2016.md) , [BizTalk 2013 R2 / 2013](install-biztalk-server-2013-and-2013-r2.md)</span></span>  
    2. <span data-ttu-id="5bc9c-117">[構成](configure-biztalk-server.md)BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="5bc9c-117">[Configure](configure-biztalk-server.md) BizTalk Server</span></span>
    3. [<span data-ttu-id="5bc9c-118">構成後の手順</span><span class="sxs-lookup"><span data-stu-id="5bc9c-118">Post-configuration steps</span></span>](post-configuration-steps-to-optimize-your-environment.md)
  
## <a name="some-edias2-artifacts-are-still-active-after-unconfiguring"></a><span data-ttu-id="5bc9c-119">構成解除した後、一部の edi/as2 アイテムがまだアクティブ</span><span class="sxs-lookup"><span data-stu-id="5bc9c-119">Some EDI/AS2 artifacts are still active after unconfiguring</span></span>  
  
<span data-ttu-id="5bc9c-120">**問題**</span><span class="sxs-lookup"><span data-stu-id="5bc9c-120">**Problem**</span></span>  
 <span data-ttu-id="5bc9c-121">BizTalk Server EDI に関連する一部の BizTalk Server アイテムの BizTalk edi/as2 機能の構成を解除すると、AS2 処理を BizTalk グループ構成のコンテキストでアクティブにすることができます。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-121">After you unconfigure the BizTalk EDI/AS2 feature of BizTalk Server, some BizTalk Server artifacts related to EDI and AS2 processing will still be active in the context of the BizTalk group configuration.</span></span> <span data-ttu-id="5bc9c-122">これらの成果物には、EDI および AS2 のパイプラインとバッチ処理オーケストレーションが含まれます。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-122">These artifacts will include EDI and AS2 pipelines and the batching orchestration.</span></span> <span data-ttu-id="5bc9c-123">その結果、BizTalk edi/as2 機能を構成解除した後でも、基本的な EDI および AS2 処理を実行することができます。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-123">As a result, you will still be able to perform basic EDI and AS2 processing even after unconfiguring the BizTalk EDI/AS2 feature.</span></span>  
  
<span data-ttu-id="5bc9c-124">**原因** </span><span class="sxs-lookup"><span data-stu-id="5bc9c-124">**Cause** </span></span>  
 <span data-ttu-id="5bc9c-125">EDI および AS2 処理に関連付けられているアクティブなポートがあります。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-125">There are active ports associated with EDI and AS2 processing.</span></span> <span data-ttu-id="5bc9c-126">一部のアイテムは引き続きこれらのポートをアクティブにしたままに機能します。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-126">Some artifacts will continue to function while these ports remain active.</span></span>  
  
<span data-ttu-id="5bc9c-127">**解決方法**</span><span class="sxs-lookup"><span data-stu-id="5bc9c-127">**Resolution**</span></span>  
 <span data-ttu-id="5bc9c-128">すべての edi/as2 アイテムを無効にするを無効にし、停止、または EDI および AS2 処理に関連付けられているポートを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-128">To disable all EDI/AS2 artifacts, you should disable, stop, or delete the ports associated with EDI and AS2 processing.</span></span>  
  
## <a name="after-renaming-biztalk-or-sql-server-computer-the-configuration-wizard-fails"></a><span data-ttu-id="5bc9c-129">構成ウィザードが失敗した後、BizTalk または SQL Server コンピューターの名前を変更するには、</span><span class="sxs-lookup"><span data-stu-id="5bc9c-129">After renaming BizTalk or SQL Server computer, the Configuration Wizard fails</span></span>  
  
<span data-ttu-id="5bc9c-130">**問題**</span><span class="sxs-lookup"><span data-stu-id="5bc9c-130">**Problem**</span></span>  
 <span data-ttu-id="5bc9c-131">この問題は、いくつかの方法で問題を発生可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-131">This problem may manifest itself in several ways:</span></span>  
  
-   <span data-ttu-id="5bc9c-132">構成マネージャーが [概要] ページを正しく読み込むが、画面に機能を構成しようとすると、機能のオプションは表示されません。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-132">The configuration manager will load the Overview page correctly, but when attempting to configure a feature, the feature options do not display on the screen.</span></span>  
  
-   <span data-ttu-id="5bc9c-133">構成ウィザードは、SQL Server に接続できません。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-133">The configuration wizard cannot connect to the SQL Server.</span></span>  
  
-   <span data-ttu-id="5bc9c-134">すべてではなく、一部の機能の構成を解除するすべての構成を解除しようとしています。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-134">Attempting to Unconfigure All unconfigures some features, but not all.</span></span>  
  
<span data-ttu-id="5bc9c-135">**原因** </span><span class="sxs-lookup"><span data-stu-id="5bc9c-135">**Cause** </span></span>  
 <span data-ttu-id="5bc9c-136">BizTalk Server の構成では、コンピューターのネットワーク名を格納します。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-136">The BizTalk Server configuration stores the computer network name.</span></span> <span data-ttu-id="5bc9c-137">コンピューターの名前変更は、configuration manager との構成ウィザードは、BizTalk Server を特定できなくなります。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-137">When the computer is renamed, the configuration manager and configuration wizard cannot locate the BizTalk Server.</span></span> <span data-ttu-id="5bc9c-138">SQL Server コンピューターの名前が変更された後、BizTalk Server が構成されている場合、同様の問題が発生します。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-138">A similar problem will occur if the SQL Server computer is renamed after BizTalk Server is configured.</span></span>  
  
<span data-ttu-id="5bc9c-139">**解決方法**</span><span class="sxs-lookup"><span data-stu-id="5bc9c-139">**Resolution**</span></span>  
 <span data-ttu-id="5bc9c-140">BizTalk Server コンピューター、または SQL Server コンピューターに名前を変更できません。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-140">Do not rename the BizTalk Server computer or the SQL Server computer.</span></span> <span data-ttu-id="5bc9c-141">場合は、サーバーの名前を変更する必要があります、コンピューターの名前を変更する前にすべての BizTalk 機能の構成を解除します。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-141">If a server must be renamed, unconfigure all BizTalk features before renaming the computer.</span></span> <span data-ttu-id="5bc9c-142">コンピューターの名前を変更するには後、は、BizTalk Server の機能を再構成します。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-142">After renaming the computer, reconfigure BizTalk Server features.</span></span>  
  
## <a name="business-rules-configuration-wizard-fails"></a><span data-ttu-id="5bc9c-143">ビジネス ルール構成ウィザードが失敗しました。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-143">Business Rules Configuration Wizard fails</span></span>  
  
<span data-ttu-id="5bc9c-144">**問題**</span><span class="sxs-lookup"><span data-stu-id="5bc9c-144">**Problem**</span></span>  
  
-   <span data-ttu-id="5bc9c-145">ビジネス ルールの構成ウィザードは、「一部のコンポーネントの構成に失敗しましたし、それらのコンポーネントの設定は適用されませんでした」エラーで失敗します。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-145">The Business Rules Configuration Wizard fails with the error “Configuration failed for some components and no settings were applied for those components.”</span></span>  
  
-   <span data-ttu-id="5bc9c-146">対象のビジネス ルール エンジンが既に正常に構成されて、BizTalk サーバー コンピューターには、ルール エンジン更新サービスは開始に失敗し、手動で開始することはできません。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-146">On BizTalk Server computers for which the Business Rules Engine has already been successfully configured, the Rules Engine Update service fails to start and cannot be started manually.</span></span>  
  
<span data-ttu-id="5bc9c-147">この問題が発生したときに、BizTalk Server コンピューターのアプリケーション ログには、次のようなエラーを生成可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-147">When this problem occurs, an error similar to the following may be generated in the BizTalk Server computer Application log:</span></span>  
  
```  
Service could not be started. : System.Net.Sockets.SocketException (10061): No connection could be made because the target machine actively refused it ::1:3132  
  
```  
  
<span data-ttu-id="5bc9c-148">**原因** </span><span class="sxs-lookup"><span data-stu-id="5bc9c-148">**Cause** </span></span>  
 <span data-ttu-id="5bc9c-149">Microsoft マルウェア プロテクション センターのリリースでは、2010 年 3 月 9 日 SettingsModifier:Win32 から潜在的な脅威に対処する、更新されたシグネチャ ファイル/公開しました。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-149">The Microsoft Malware Protection Center released an updated signature file on March 9th, 2010 to address a possible threat from SettingsModifier:Win32/PossibleHostsFileHijack.</span></span> <span data-ttu-id="5bc9c-150">この更新されたシグネチャ ファイル SettingsModifier:Win32 からの脅威を軽減するためにローカルの HOSTS ファイルを更新する Windows Defender などの Microsoft マルウェア検出ソフトウェアが発生することができます/公開しました。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-150">This updated signature file can cause Microsoft Malware Detection software such as Windows Defender to update the local HOSTS file to mitigate threats from SettingsModifier:Win32/PossibleHostsFileHijack.</span></span> <span data-ttu-id="5bc9c-151">これらの変更の結果として、BizTalk Server ルール エンジン更新サービスを開始する失敗します。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-151">As a result of these changes, the BizTalk Server Rules Engine Update service may fail to start.</span></span>  
  
<span data-ttu-id="5bc9c-152">**解決方法**</span><span class="sxs-lookup"><span data-stu-id="5bc9c-152">**Resolution**</span></span>  
 <span data-ttu-id="5bc9c-153">ローカルの HOSTS ファイルに含める、次の行を更新します。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-153">Update the local HOSTS file to include the following line:</span></span>  
  
```  
127.0.0.1         localhost  
```  
  
 <span data-ttu-id="5bc9c-154">HOSTS ファイルは %systemroot%\drivers\etc\ ディレクトリ内にあります。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-154">The HOSTS file is located in the %systemroot%\drivers\etc\ directory.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5bc9c-155">Microsoft マルウェア プロテクション センター署名をする可能性のある脅威のアドレスを更新を参照してください。 [SettingsModifier:Win32/公開しました](http://go.microsoft.com/fwlink/?LinkId=146221)します。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-155">See the Microsoft Malware Protection Center signature update that addresses a possible threat from [SettingsModifier:Win32/PossibleHostsFileHijack](http://go.microsoft.com/fwlink/?LinkId=146221).</span></span>  
  
## <a name="configuration-logging"></a><span data-ttu-id="5bc9c-156">構成のログ記録</span><span class="sxs-lookup"><span data-stu-id="5bc9c-156">Configuration Logging</span></span>  
 <span data-ttu-id="5bc9c-157">構成プログラムでは、既定では BizTalk Server を実行しているコンピューターの一時ディレクトリに格納されている構成ログ ファイルに詳細な情報を書き込みます。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-157">The configuration program writes detailed information to a configuration log file which by default is located in the temp directory of the computer running BizTalk Server.</span></span> <span data-ttu-id="5bc9c-158">TEMP 環境変数によって指定されているフォルダーを確認するには、そのコンピューターでコマンド プロンプトを開き、次のコマンドを入力して、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-158">To determine the folder that is specified by the TEMP environment variable open a command prompt on this computer, type the following command, and then press ENTER:</span></span>  
  
 <span data-ttu-id="5bc9c-159">**エコー %temp%**</span><span class="sxs-lookup"><span data-stu-id="5bc9c-159">**echo %TEMP%**</span></span>  
  
 <span data-ttu-id="5bc9c-160">構成ログ ファイルの内容は、実行された構成手順の概要と、構成処理中に発生した疑いのあるエラーに関する診断情報です。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-160">The configuration log file contains a summary of the configuration steps performed, as well as diagnostic information about any failures that may occur during the configuration process.</span></span> <span data-ttu-id="5bc9c-161">構成エラーが発生した場合、メモ帳などのテキスト エディターでは、構成ログを開くし、エラーの考えられる原因は、ログ ファイルを確認してください。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-161">If a configuration error occurs, open the configuration log in a text editor such as Notepad and check the log file for possible causes of the error.</span></span>  
  
## <a name="troubleshooting-tools"></a><span data-ttu-id="5bc9c-162">トラブルシューティング ツール</span><span class="sxs-lookup"><span data-stu-id="5bc9c-162">Troubleshooting Tools</span></span>  
 <span data-ttu-id="5bc9c-163">SQL Server プロファイラー、Filemon、または Regmon を使用して、構成エラーに関する追加情報を収集します。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-163">Use SQL Server Profiler, Filemon, or Regmon to gather additional information about configuration failures.</span></span> <span data-ttu-id="5bc9c-164">参照してください[トラブルシューティングに使用するには、ツールとユーティリティ](../core/tools-and-utilities-to-use-for-troubleshooting.md)します。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-164">See [Tools and Utilities to use for Troubleshooting](../core/tools-and-utilities-to-use-for-troubleshooting.md).</span></span>  
  
### <a name="configuration-fails-when-biztalk-and-sql-are-installed-on-separate-computers"></a><span data-ttu-id="5bc9c-165">BizTalk と SQL が別々 のコンピューターにインストールされているときに、構成が失敗します。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-165">Configuration fails when BizTalk and SQL are installed on separate computers</span></span>  
  
<span data-ttu-id="5bc9c-166">**問題**</span><span class="sxs-lookup"><span data-stu-id="5bc9c-166">**Problem**</span></span>  
 <span data-ttu-id="5bc9c-167">エンタープライズ シングル サインオン (SSO) コンポーネントを構成しようとすると、次のようなエラーが発生して構成が失敗します。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-167">Configuration fails with errors similar to the following when attempting to configure the Enterprise Single Sign-On (SSO) component:</span></span>  
  
```
An error occurred while attempting to access the SSO database.  
Function: FieldInfoCreate  
```
  
 <span data-ttu-id="5bc9c-168">- または -</span><span class="sxs-lookup"><span data-stu-id="5bc9c-168">-or-</span></span>  
  
```Failed to enable the Single Sign-On (SSO) Service (error code 0X800706BA)```  
  
<span data-ttu-id="5bc9c-169">**原因**  </span><span class="sxs-lookup"><span data-stu-id="5bc9c-169">**Cause**  </span></span>  
 <span data-ttu-id="5bc9c-170">BizTalk Server と SQL Server が別々 のコンピューターにインストールされている場合は、構成操作が Microsoft 分散トランザクション コーディネーター (MSDTC) トランザクションのコンテキストで実行される MSDTC 機能を利用できる必要があります、これらのコンピューター間のネットワーク。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-170">If BizTalk Server and SQL Server are installed on different computers, then the configuration operations are performed under the context of a Microsoft Distributed Transaction Coordinator (MSDTC) transaction and MSDTC functionality must be available over the network between these computers.</span></span> <span data-ttu-id="5bc9c-171">BizTalk Server と SQL Server を実行しているコンピューター間のネットワークで MSDTC 機能を利用することはできません、このエラーは発生します。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-171">If MSDTC functionality is not available over the network between the computers running BizTalk Server and SQL Server, then this error can occur.</span></span>  
  
<span data-ttu-id="5bc9c-172">**解決方法**  </span><span class="sxs-lookup"><span data-stu-id="5bc9c-172">**Resolution**  </span></span>  
<span data-ttu-id="5bc9c-173">使用[MSDTC を使用した問題のトラブルシューティング](https://support.microsoft.com/help/306843/how-to-troubleshoot-ms-dtc-firewall-issues)に BizTalk Server と SQL Server を実行しているコンピューター間のネットワークで MSDTC 機能を確認します。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-173">Use [Troubleshooting Problems with MSDTC](https://support.microsoft.com/help/306843/how-to-troubleshoot-ms-dtc-firewall-issues) to ensure MSDTC functionality over the network between the computers running BizTalk Server and SQL Server.</span></span>  
  
### <a name="antivirus-software-interferes-with-configuration-and-causes-configuration-failures"></a><span data-ttu-id="5bc9c-174">ウイルス対策ソフトウェアの干渉によって構成エラーが発生する</span><span class="sxs-lookup"><span data-stu-id="5bc9c-174">Antivirus software interferes with configuration and causes configuration failures</span></span>  
  
<span data-ttu-id="5bc9c-175">**問題** </span><span class="sxs-lookup"><span data-stu-id="5bc9c-175">**Problem** </span></span>  
 <span data-ttu-id="5bc9c-176">BizTalk Server の構成は、ウイルス対策ソフトウェアが、構成プログラムがウイルスであると誤って判断するときに失敗します。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-176">BizTalk Server configuration fails when antivirus software incorrectly determines that the configuration program is a virus.</span></span>  
  
<span data-ttu-id="5bc9c-177">**原因**</span><span class="sxs-lookup"><span data-stu-id="5bc9c-177">**Cause**</span></span>  
 <span data-ttu-id="5bc9c-178">正当な (ウイルスではない) プログラムとして、BizTalk Server 構成プログラムを含める、ウイルス対策ソフトウェアが更新されていません。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-178">The antivirus software has not been updated to include the BizTalk Server configuration program as a legitimate (non-virus) program.</span></span>  
  
<span data-ttu-id="5bc9c-179">**解決方法**</span><span class="sxs-lookup"><span data-stu-id="5bc9c-179">**Resolution**</span></span>  
 <span data-ttu-id="5bc9c-180">構成プログラムの実行中に、ウイルス対策ソフトウェアを一時的に無効にするか、正当な (ウイルスではない) プログラムとして、BizTalk Server 構成プログラムを認識するには、ウイルス対策プログラムを構成します。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-180">Configure the antivirus program to recognize the BizTalk Server configuration program as a legitimate (non-virus) program or else temporarily disable the antivirus software while the configuration program is running.</span></span>  
  
### <a name="configuration-fails-with-a-file-or-assembly-name-filenamedll-or-one-of-its-dependencies-was-not-found-error"></a><span data-ttu-id="5bc9c-181">"ファイルまたはアセンブリ名 'FileName.dll'、またはその依存関係の 1 つが見つかりませんでした" というエラーによって構成が失敗する</span><span class="sxs-lookup"><span data-stu-id="5bc9c-181">Configuration fails with a "File or assembly name FileName.dll, or one of its dependencies, was not found" error</span></span>  
  
<span data-ttu-id="5bc9c-182">**問題**</span><span class="sxs-lookup"><span data-stu-id="5bc9c-182">**Problem**</span></span>  
 <span data-ttu-id="5bc9c-183">構成プロセスで次のようなエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-183">An error similar to the following is displayed during the configuration process:</span></span>  
  
 <span data-ttu-id="5bc9c-184">BizTalk システム アセンブリ"C:\Program \microsoft\biztalk Server 20xx\Microsoft.BizTalk.DefaultPipelines.dll 展開に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-184">Failed to deploy BizTalk system assembly "C:\Program Files\Microsoft\BizTalk Server 20xx\Microsoft.BizTalk.DefaultPipelines.dll.</span></span> <span data-ttu-id="5bc9c-185">指定されていない例外:ファイルまたはアセンブリ名 filename.dll、またはその依存関係の 1 つが見つかりませんでした。"</span><span class="sxs-lookup"><span data-stu-id="5bc9c-185">Unspecified exception: File or assembly name FileName .dll, or one of its dependencies, was not found."</span></span>  
  
<span data-ttu-id="5bc9c-186">**原因**</span><span class="sxs-lookup"><span data-stu-id="5bc9c-186">**Cause**</span></span>  
 <span data-ttu-id="5bc9c-187">このエラーは、アカウントがネットワーク サービスの一時フォルダーに BizTalk Server を実行するコンピューターでアクセス許可を記述する場合に発生することができます。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-187">This error can occur if the Network Service account does not have write permissions to the temp folder on the computer running BizTalk Server.</span></span> <span data-ttu-id="5bc9c-188">構成時に、BizTalk Server の構成は、.NET アセンブリを BizTalk 管理データベースに展開するのに Windows Management Instrumentation (WMI) を使用します。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-188">During configuration, BizTalk Server configuration uses Windows Management Instrumentation (WMI) to deploy .NET assemblies to the BizTalk Management database.</span></span> <span data-ttu-id="5bc9c-189">WMI は、これらのアセンブリを BizTalk 管理データベースにデプロイするときに、Network Service アカウントを偽装そのため、ネットワーク サービス アカウントは、BizTalk Server を実行しているコンピューター上の一時フォルダーの書き込みアクセス権がする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-189">WMI impersonates the Network Service account while deploying these assemblies to the BizTalk Management database and so the Network Service account must have write access to the temp folder on the computer running BizTalk Server.</span></span>  
  
<span data-ttu-id="5bc9c-190">**解決方法**</span><span class="sxs-lookup"><span data-stu-id="5bc9c-190">**Resolution**</span></span>  
 <span data-ttu-id="5bc9c-191">ネットワーク サービス アカウントの BizTalk Server を実行しているコンピューター上の一時フォルダーへの書き込みアクセスを付与し、構成プログラムをもう一度実行します。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-191">Grant the Network Service account write access to the temp folder on the computer running BizTalk Server and run the configuration program again.</span></span> <span data-ttu-id="5bc9c-192">TEMP 環境変数で指定されているフォルダーを決定するには、コンピューターでコマンド プロンプトを開き、次のコマンドを入力し、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-192">To determine the folder that is specified by the TEMP environment variable, open a command prompt on the computer, type the following command, and then press ENTER:</span></span>  
  
```  
echo %TEMP%  
```  
  
### <a name="configuration-fails-if-a-sql-server-database-file-that-has-the-same-name-as-the-specified-database-already-exists-in-the-sql-server-data-folder"></a><span data-ttu-id="5bc9c-193">指定したデータベースと同じ名前の SQL Server データベース ファイルが SQL Server のデータ フォルダーに既に存在していると構成が失敗する</span><span class="sxs-lookup"><span data-stu-id="5bc9c-193">Configuration fails if a SQL Server database file that has the same name as the specified database already exists in the SQL Server data folder</span></span>  
  
#### <a name="problem"></a><span data-ttu-id="5bc9c-194">問題</span><span class="sxs-lookup"><span data-stu-id="5bc9c-194">Problem</span></span>  
 <span data-ttu-id="5bc9c-195">次のようなエラーが発生して構成が失敗します。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-195">Configuration fails with an error similar to the following:</span></span>  
  
```
Failed to set up BAM database(s)  
  
Cannot open database requested in login 'BAMPrimaryImport'  
  
Logon fails. Logon failed for user '*BizTalk\BizTalkUser*'  
```
  
<span data-ttu-id="5bc9c-196">**原因**</span><span class="sxs-lookup"><span data-stu-id="5bc9c-196">**Cause**</span></span>  
 <span data-ttu-id="5bc9c-197">このエラーは、.mdf ファイルの場合に発生する可能性がまたは .mdf ファイルまたは .ldf ファイルを作成しようとして、BizTalk Server 構成プログラムと同じ名前を持つ SQL Server を実行しているコンピューターの \MSSQL\data フォルダーに、.ldf ファイルが既に存在します。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-197">This error can occur if an .mdf file or an .ldf file already exists in the \MSSQL\data folder of the computer running SQL Server that has the same name as the .mdf file or the .ldf file that the BizTalk Server configuration program is trying to create.</span></span> <span data-ttu-id="5bc9c-198">データベースに対して作成される .mdf ファイルと .ldf ファイルの名前は、.mdf と .ldf 拡張子を追加すると、BizTalk Server 構成プログラムで指定されているデータベースの名前から派生します。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-198">The names of the .mdf file and the .ldf file that are created for the databases are derived from the name of the database that is specified in the BizTalk Server configuration program with an .mdf and an .ldf extension appended.</span></span>  
  
<span data-ttu-id="5bc9c-199">**解決方法**</span><span class="sxs-lookup"><span data-stu-id="5bc9c-199">**Resolution**</span></span>  
 <span data-ttu-id="5bc9c-200">この問題を解決するには、以下のいずれかの方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-200">To resolve this behavior, use one of the following methods:</span></span>  
  
-   <span data-ttu-id="5bc9c-201">現在作成しているデータベースの名前と一致する名前を持つ .mdf ファイルや .ldf ファイルを削除します。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-201">Delete any .mdf files or .ldf files that have names that match the names of any databases that you are creating.</span></span>  
  
-   <span data-ttu-id="5bc9c-202">SQL Server の \Program Files\Microsoft SQL Server\MSSQL\data フォルダーに既に存在する .mdf ファイルや .ldf ファイルの名前と一致しないデータベース名を選択します。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-202">Choose database names that do not match the names of any .mdf files or .ldf files that already exist in the \Program Files\Microsoft SQL Server\MSSQL\data folder of your SQL server.</span></span>  
  
### <a name="configuration-fails-on-a-domain-controller-when-specifying-local-accounts"></a><span data-ttu-id="5bc9c-203">ドメイン コントローラーでローカル アカウントを指定すると構成が失敗する</span><span class="sxs-lookup"><span data-stu-id="5bc9c-203">Configuration fails on a domain controller when specifying local accounts</span></span>  
  
<span data-ttu-id="5bc9c-204">**問題**</span><span class="sxs-lookup"><span data-stu-id="5bc9c-204">**Problem**</span></span>  
 <span data-ttu-id="5bc9c-205">ドメイン コント ローラーで、BizTalk Server 構成プログラムを実行するときに構成はローカル グループ (たとえば、BizTalk ホスト ユーザー グループ) を指定した場合、BizTalkServerApplication ホストか BizTalkIsolatedHost ホストのいずれかの失敗します。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-205">When running the BizTalk Server configuration program on a domain controller, configuration fails if you specified a local group (for example, BizTalk Host Users Group) for either the BizTalkServerApplication host or the BizTalkIsolatedHost host.</span></span>  
  
<span data-ttu-id="5bc9c-206">**原因**</span><span class="sxs-lookup"><span data-stu-id="5bc9c-206">**Cause**</span></span>  
 <span data-ttu-id="5bc9c-207">ドメイン コントローラーでは、ローカル Windows グループが自動的にドメイン Windows グループとして処理されます (ドメイン コントローラーにはローカル Windows グループのようなものは存在しません)。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-207">A domain controller automatically treats a local Windows group as a domain Windows group (there is no such thing as local Windows group on a domain controller).</span></span> <span data-ttu-id="5bc9c-208">構成プログラムの実行中に、ホストのローカル Windows グループを指定した場合、グループの SQL Server ログオンを作成しようとするときの構成は失敗します。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-208">If you specified a local Windows group for the host while running the configuration program, configuration will fail when trying to create a SQL Server logon for the group.</span></span> <span data-ttu-id="5bc9c-209">サーバーがドメイン コントローラーに設定されていると、構成プログラムのローカル Windows グループ オプションが無効になりません。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-209">The configuration program does not disable the local Windows group option when the server is a domain controller.</span></span>  
  
<span data-ttu-id="5bc9c-210">**解決方法**</span><span class="sxs-lookup"><span data-stu-id="5bc9c-210">**Resolution**</span></span>  
 <span data-ttu-id="5bc9c-211">構成中に作成されるホストに対してはドメイン グループを指定します。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-211">Specify domain groups for the hosts that are created during configuration.</span></span>  
  
### <a name="configuration-fails-to-create-sql-server-analysis-database-if-the-sql-server-has-been-renamed"></a><span data-ttu-id="5bc9c-212">SQL サーバーの名前が変更されていると構成プログラムが SQL Server 分析データベースの作成に失敗する</span><span class="sxs-lookup"><span data-stu-id="5bc9c-212">Configuration fails to create SQL Server Analysis database if the SQL server has been renamed</span></span>  
  
<span data-ttu-id="5bc9c-213">**問題**</span><span class="sxs-lookup"><span data-stu-id="5bc9c-213">**Problem**</span></span>  
 <span data-ttu-id="5bc9c-214">SQL Server 分析サーバーをインストールしたコンピューターの名前を変更した場合、新しい SQL Server 分析データベースを作成しようとすると構成プログラムが失敗して、次のようなエラーが生成されます。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-214">If you have renamed the computer on which you installed SQL Server Analysis Server, the configuration program fails when it tries to create the new SQL Server Analysis database and an error similar to the following is generated:</span></span>  

```  
 Cannot connect to the repository.  
  
 Analysis server: <machine name\>  
  
 Error:  
  
 '\\\\<machine name\>\MsOLAPRepository$\msmdrep.mdb' is not a valid path.  
  
 Make sure that you correctly spell the path name and that you are  
  
 connected to the server on which the file resides.  
```
  
<span data-ttu-id="5bc9c-215">**原因**</span><span class="sxs-lookup"><span data-stu-id="5bc9c-215">**Cause**</span></span>  
 <span data-ttu-id="5bc9c-216">SQL Server 分析サーバーをインストールしたコンピューターの新しい名前を構成プログラムが特定できません。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-216">The configuration program is unable to determine the new name of the computer on which you installed SQL Server Analysis Server.</span></span>  
  
<span data-ttu-id="5bc9c-217">**解決方法**</span><span class="sxs-lookup"><span data-stu-id="5bc9c-217">**Resolution**</span></span>  
 <span data-ttu-id="5bc9c-218">以下の手順を手動で実行し、分析サーバーを新しいコンピューター名で更新します。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-218">Perform the following manual steps to update Analysis Server with the new computer name:</span></span>  
  
1.  <span data-ttu-id="5bc9c-219">SQL Server で開く**Microsoft SQL Server**を選択します**Analysis Services**、 をクリックし、**分析マネージャー**。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-219">On the SQL Server, open **Microsoft SQL Server**, select **Analysis Services**, and then click **Analysis Manager**.</span></span>  
  
2.  <span data-ttu-id="5bc9c-220">**分析マネージャー**ナビゲーション ウィンドウで、ダブルクリックして、**分析サーバー**ノードを展開します。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-220">In the **Analysis Manager** navigation panel, double-click the **Analysis Servers** node to expand it.</span></span>  
  
3.  <span data-ttu-id="5bc9c-221">リポジトリ接続文字列を編集して、選択すると、サーバーを右クリックして**リポジトリ接続文字列の編集**します。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-221">Right-click the server with the repository connection string you want to edit, and then select **Edit Repository Connection String**.</span></span>  
  
4.  <span data-ttu-id="5bc9c-222">**リポジトリ接続文字列の編集** ダイアログ ボックスでこの文字列内のサーバー名を確認しが正しくない場合、新しいコンピューター名を更新します。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-222">In the **Edit Repository Connection String** dialog box, verify the server name in this string and update it to the new computer name if it is incorrect.</span></span>  
  
5.  <span data-ttu-id="5bc9c-223">次の場所に移動します: <*インストール ディレクトリ*> \Program Files\Microsoft Analysis services \bin です。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-223">Navigate to the following location: <*installation directory*>\Program Files\Microsoft Analysis Services\Bin.</span></span>  
  
6.  <span data-ttu-id="5bc9c-224">右クリックし、 **Bin**フォルダー、およびクリック**共有とセキュリティ**します。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-224">Right-click the **Bin** folder, and then click **Sharing and Security**.</span></span> <span data-ttu-id="5bc9c-225">**Bin のプロパティ** ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-225">The **Bin Properties** dialog box appears.</span></span>  
  
7.  <span data-ttu-id="5bc9c-226">**Bin のプロパティ**ダイアログ ボックスで、をクリックして、**共有** タブに、すべてのオンライン分析処理 (OLAP) 管理者が完全なアクセス許可をこのフォルダーにあることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-226">In the **Bin Properties** dialog box, click the **Sharing** tab to verify that all Online Analytical Processing (OLAP) administrators have full permissions to this folder.</span></span>  
  
### <a name="artifacts-disappear-from-configuration-database-on-redeployment-of-assemblies-from-visual-studio"></a><span data-ttu-id="5bc9c-227">Visual Studio からアセンブリを再展開の構成データベースからアイテムが表示されなくなります</span><span class="sxs-lookup"><span data-stu-id="5bc9c-227">Artifacts disappear from Configuration Database on redeployment of assemblies from Visual Studio</span></span>  
  
<span data-ttu-id="5bc9c-228">**問題**</span><span class="sxs-lookup"><span data-stu-id="5bc9c-228">**Problem**</span></span>  
 <span data-ttu-id="5bc9c-229">ときに BizTalk Server プロジェクトを再展開 Visual Studio で、プロジェクト レベルで再デプロイ プロジェクトの参照が消える、BizTalk Server MMC が更新されたときに表示されるプロジェクト内に含まれるすべての成果物。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-229">When a BizTalk Server project is redeployed at the project level within Visual Studio, all artifacts contained within the project that reference the project being redeployed will appear to vanish when the BizTalk Server MMC is refreshed.</span></span>  
  
<span data-ttu-id="5bc9c-230">**原因**</span><span class="sxs-lookup"><span data-stu-id="5bc9c-230">**Cause**</span></span>  
 <span data-ttu-id="5bc9c-231">この問題の原因を示すために、ユーザーが Maps プロジェクトを再展開しようとしているサンプル BizTalk Server ソリューションに基づく例について考えてみます。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-231">To illustrate the cause of this problem, consider the following example based on a sample BizTalk Server solution where a user wants to redeploy the Maps project.</span></span> <span data-ttu-id="5bc9c-232">プロジェクトをコンパイルすると個々のアセンブリが生成されます。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-232">Note that compiling projects yields individual assemblies.</span></span> <span data-ttu-id="5bc9c-233">次の図は、ユーザーが再展開を行う前のソリューションの状態を示しています。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-233">The following figure indicates the state of the solution before the user does a redeployment.</span></span> <span data-ttu-id="5bc9c-234">アイテム間の関係は次のようになっています。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-234">The relationships among the artifacts are as follows:</span></span>  
  
-   <span data-ttu-id="5bc9c-235">Orch1、Orch2、Maps、Pipelines、および Schemas はプロジェクトです。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-235">Orch1, Orch2, Maps, Pipelines, and Schemas are projects.</span></span>  
  
-   <span data-ttu-id="5bc9c-236">Orch1 は Maps を参照し、Maps は Schemas を参照しています。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-236">Orch1 references Maps, which in turn references Schemas.</span></span>  
  
-   <span data-ttu-id="5bc9c-237">Orch2 は Schemas を参照しています。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-237">Orch2 references Schemas.</span></span>  
  
-   <span data-ttu-id="5bc9c-238">Pipelines は Schemas を参照しています。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-238">Pipelines references Schemas.</span></span>  
  
![bcd_ExistingBizTalkServerSolutionc](../install-and-config-guides/media/bcd_ExistingBizTalkServerSolutionc.gif)  
  
<span data-ttu-id="5bc9c-240">ユーザーが Visual Studio の既定のプロジェクト設定を使用して Maps プロジェクトを再展開すると、次の図のように、Orch1、Orch2、および Pipeline の各アイテムが消えてしまいます。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-240">If the user redeploys the Maps project using the default Visual Studio project settings, the Orch1, Orch2, and Pipeline artifacts vanish, as shown in the following figure.</span></span>  
  
![bcd_BizTalkSolutionWLostArtifactsc](../install-and-config-guides/media/bcd_BizTalkSolutionWLostArtifactsc.gif)  
  
 <span data-ttu-id="5bc9c-242">Maps の再展開は、現在展開されている Maps.dll アセンブリの展開を解除して、新しい Maps.dll ファイルを展開する、2 段階のプロセスです。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-242">Redeploying Maps is a two-step process of undeploying the currently deployed Maps.dll assembly, and then deploying the new Maps.dll file.</span></span> <span data-ttu-id="5bc9c-243">Visual Studio は、再デプロイ プロセスの一環として自動的に次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-243">Visual Studio performs these steps automatically as part of the redeployment process.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5bc9c-244">前の文は厳密には正しくありません。というのも、これらの手順は Visual Studio で常に行われるものなので、正しく行われているかどうかを意識することはありません。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-244">The preceding sentence is not strictly correct because these are steps that Visual Studio always does so there is no notion of it being the proper way.</span></span>  
  
 <span data-ttu-id="5bc9c-245">重要なポイントは、BizTalk Server アセンブリの展開を解除するためには Visual Studio が、すべてのアセンブリはそのアセンブリに依存する展開フラグが設定されているを展開解除するには。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-245">The key point is that in order to undeploy a BizTalk Server assembly, Visual Studio has to undeploy all assemblies that are dependent upon that assembly that have the deploy flag set.</span></span> <span data-ttu-id="5bc9c-246">この例で言うと、再展開の最初の展開解除の手順を実行するには、BizTalk Server が Orch1.dll (Maps.dll に依存している) の展開を解除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-246">In our example, to perform the first undeployment step of the redeployment, BizTalk Server needs to undeploy Orch1.dll (which depends on Maps.dll).</span></span> <span data-ttu-id="5bc9c-247">Maps.dll の展開を解除する、Visual Studio には、(展開フラグの設定があると仮定) Schemas.dll も展開解除されます。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-247">During the undeployment of Maps.dll, Visual Studio also undeploys Schemas.dll (assuming it has the deploy flag set).</span></span> <span data-ttu-id="5bc9c-248">Schemas.dll の展開を解除するには、Orch2.dll と Pipelines.dll (いずれも Schemas.dll に依存している) の展開を解除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-248">In order to undeploy Schemas.dll, Visual Studio needs to undeploy Orch2.dll and Pipelines.dll (both of which depend on Schemas.dll).</span></span>  
  
 <span data-ttu-id="5bc9c-249">Visual Studio Maps.dll とそれが依存するアセンブリのみを再デプロイで問題が存在する。 この場合は Schemas.dll します。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-249">A problem exists in that Visual Studio redeploys only Maps.dll and the assemblies that it depends upon: in this case, Schemas.dll.</span></span> <span data-ttu-id="5bc9c-250">そのため、ユーザーが BizTalk Server MMC を更新すると、Orch1、Orch2、および Pipeline の各アセンブリが消えたように見えますが、Maps.dll と Schemas.dll は引き続き表示されます。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-250">So when the user refreshes the BizTalk Server MMC, the Orch1, Orch2, and Pipeline assemblies seem to have vanished, but Maps.dll and Schemas.dll are still visible.</span></span>  
  
<span data-ttu-id="5bc9c-251">**解決方法**</span><span class="sxs-lookup"><span data-stu-id="5bc9c-251">**Resolution**</span></span>  
 <span data-ttu-id="5bc9c-252">メイン プロジェクト (他のプロジェクトを参照しているプロジェクト) に対して次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-252">For the main project (that references other projects) do the following:</span></span>  
  
1.  <span data-ttu-id="5bc9c-253">ソリューション エクスプローラーで、ソリューション ノードを右クリックします。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-253">In Solution Explorer, right-click the solution node.</span></span>  
  
2.  <span data-ttu-id="5bc9c-254">クリックして**プロパティ**を開く、**ソリューション プロパティ ページ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-254">Click **Properties** to open the **Solution Property Pages** dialog box.</span></span>  
  
3.  <span data-ttu-id="5bc9c-255">をクリックして**構成プロパティ**、 をクリックし、**構成**します。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-255">Click **Configuration Properties**, and then click **Configuration**.</span></span>  
  
4.  <span data-ttu-id="5bc9c-256">クリア、**デプロイ**参照先のプロジェクトのチェック ボックス。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-256">Clear the **Deploy** check box for the referenced project.</span></span>  
  
5.  <span data-ttu-id="5bc9c-257">ソリューション エクスプローラーで、新しいソリューション レベルの展開を実行します。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-257">In Solution Explorer, execute a new solution-level deployment.</span></span> <span data-ttu-id="5bc9c-258">これを行うには、ソリューション ノードを右クリックし をクリックし、**ソリューションの配置**します。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-258">To do this, right-click the solution node and then click **Deploy Solution**.</span></span>  
  
### <a name="supported-virtual-directory-types"></a><span data-ttu-id="5bc9c-259">サポートされている仮想ディレクトリのタイプ</span><span class="sxs-lookup"><span data-stu-id="5bc9c-259">Supported Virtual Directory Types</span></span>  
 <span data-ttu-id="5bc9c-260">関連付けられている仮想ディレクトリが型の場合にのみ、エクスポート操作は成功を MSI のエクスポートを実行しようと、オーケストレーションから Web サービスを参照するときに**IIsWebVirtualDir**または**IIsWebDirectory**.</span><span class="sxs-lookup"><span data-stu-id="5bc9c-260">When referencing Web services from an orchestration and attempting to do an MSI export, the export operation will succeed only if the associated virtual directories are of type **IIsWebVirtualDir** or **IIsWebDirectory**.</span></span> <span data-ttu-id="5bc9c-261">**IIsWebVirtualDir**と**IIsWebDirectory**は IIS メタベースに表示されるノードの種類。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-261">**IIsWebVirtualDir** and **IIsWebDirectory** are the node types that appear in the IIS metabase.</span></span> <span data-ttu-id="5bc9c-262">**IIsWebVirtualDir**の仮想ディレクトリ、**パス**絶対ファイル フォルダーを指すプロパティ。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-262">**IIsWebVirtualDir** is a virtual directory with a **Path** property that points to an absolute file folder.</span></span> <span data-ttu-id="5bc9c-263">**IIsWebDirectory**仮想ディレクトリでは、**パス**プロパティ別のサブフォルダーでは通常、相対ファイル フォルダーを参照および**IIsWebVirtualDir**または**IIsWebDirectory**ノード。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-263">**IIsWebDirectory** is a virtual directory without a **Path** property and thus refers to a relative file folder, typically a subfolder of another **IIsWebVirtualDir** or **IIsWebDirectory** node.</span></span> <span data-ttu-id="5bc9c-264">メタベース階層でフォルダーを表すものとしてはこの 2 つのタイプが一般的です。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-264">These two types are the ones typically seen in the metabase hierarchy to describe folders.</span></span>  
  
 <span data-ttu-id="5bc9c-265">型の仮想ディレクトリ**IIsConfigObject**はサポートされていませんし、この場合、MSI のエクスポートは失敗します。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-265">Virtual directories of type **IIsConfigObject** are not supported and the MSI export will fail in this case.</span></span> <span data-ttu-id="5bc9c-266">**IIsConfigObject**が、予期しないメタベース ノード タイプは BizTalk Server が正しく処理されないか、有効なノード型か、正しく作成されていない (およびしたがって無効な) メタベース エントリを示す値。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-266">**IIsConfigObject** is an unexpected metabase node type that is either a valid node type that BizTalk Server is not handling properly or an indication of an improperly created (and thus invalid) metabase entry.</span></span> <span data-ttu-id="5bc9c-267">BizTalk Server ではこのような状況で、次のようなエラー メッセージが表示されます。種類 IIsConfigObject の予期しないディレクトリ エントリ"IIS://LM/W3SVC/1/ROOT/BadVdir/"。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-267">In this situation BizTalk Server will display an error message something like the following: Unexpected directory entry " IIS://LM/W3SVC/1/ROOT/BadVdir/" of type IIsConfigObject.</span></span>  
  
### <a name="unable-to-view-group-information-after-removing-stale-logons"></a><span data-ttu-id="5bc9c-268">古いログオンを削除するとグループ情報を表示できなくなる</span><span class="sxs-lookup"><span data-stu-id="5bc9c-268">Unable to view Group information after removing stale logons</span></span>  
  
<span data-ttu-id="5bc9c-269">**問題**</span><span class="sxs-lookup"><span data-stu-id="5bc9c-269">**Problem**</span></span>  
 <span data-ttu-id="5bc9c-270">構成中に古いログオンを見つけて削除すると、グループ情報を表示できなくなる場合があります。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-270">If, during configuration, you encounter and delete stale logons, you may not be able to view Group information.</span></span>  
  
<span data-ttu-id="5bc9c-271">**原因**</span><span class="sxs-lookup"><span data-stu-id="5bc9c-271">**Cause**</span></span>  
 <span data-ttu-id="5bc9c-272">これは既知の構成の問題です。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-272">This is a known configuration issue.</span></span>  
  
<span data-ttu-id="5bc9c-273">**解決方法**</span><span class="sxs-lookup"><span data-stu-id="5bc9c-273">**Resolution**</span></span>  
 <span data-ttu-id="5bc9c-274">Host Windows グループのログオンを削除して再構成すると解決する場合があります。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-274">It may help to delete the Host Windows group logons and then reconfigure.</span></span> <span data-ttu-id="5bc9c-275">それでもグループ情報を表示できない場合は、マイクロソフト製品サポートにご連絡ください。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-275">If the Group information is still not available, contact Microsoft Product Support.</span></span>  
  
### <a name="cannot-change-computer-name-after-biztalk-server-is-installed"></a><span data-ttu-id="5bc9c-276">BizTalk Server のインストール後にコンピューター名を変更できない</span><span class="sxs-lookup"><span data-stu-id="5bc9c-276">Cannot change computer name after BizTalk Server is installed</span></span>  
  
<span data-ttu-id="5bc9c-277">**問題**</span><span class="sxs-lookup"><span data-stu-id="5bc9c-277">**Problem**</span></span>  
 <span data-ttu-id="5bc9c-278">、BizTalk Server を実行しているコンピューター上のコンピューター名を変更して、(再起動) が、コンピューターでは、エラー メッセージを再起動するときに発生します。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-278">When you change the computer name on a computer running BizTalk Server, and you restart (reboot) the computer, error messages may occur.</span></span>  
  
<span data-ttu-id="5bc9c-279">**原因**</span><span class="sxs-lookup"><span data-stu-id="5bc9c-279">**Cause**</span></span>  
 <span data-ttu-id="5bc9c-280">SQL Server では、BizTalk Server が BizTalk Server をインストールして構成したら、コンピューター名の変更をサポートしていないため、コンピューター名を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-280">SQL Server does not support changing the computer name, so BizTalk Server does not support changing the computer name once BizTalk Server is installed and configured.</span></span>  
  
<span data-ttu-id="5bc9c-281">**解決方法**</span><span class="sxs-lookup"><span data-stu-id="5bc9c-281">**Resolution**</span></span>  
 <span data-ttu-id="5bc9c-282">BizTalk Server のインストール後はコンピューター名を変更しないことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-282">We recommend that you do not change computer names after you install BizTalk Server.</span></span>  
  
### <a name="known-issues-with-enterprise-single-sign-on"></a><span data-ttu-id="5bc9c-283">エンタープライズ シングル サインオンに関する既知の問題</span><span class="sxs-lookup"><span data-stu-id="5bc9c-283">Known Issues with Enterprise Single Sign-On</span></span>  
 <span data-ttu-id="5bc9c-284">このセクションにエンタープライズ シングル サインオン (SSO) 関連するセットアップと構成の問題について説明します。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-284">This section describes setup and configuration problems that may be related to Enterprise Single Sign-On (SSO).</span></span>  
  
##### <a name="entsso-service-fails-to-start"></a><span data-ttu-id="5bc9c-285">ENTSSO サービスを開始できません。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-285">ENTSSO Service fails to start</span></span>  
  
<span data-ttu-id="5bc9c-286">**問題**</span><span class="sxs-lookup"><span data-stu-id="5bc9c-286">**Problem**</span></span>  
 <span data-ttu-id="5bc9c-287">ENTSSO サービスを開始できません。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-287">The ENTSSO service fails to start.</span></span>  
  
<span data-ttu-id="5bc9c-288">**原因**</span><span class="sxs-lookup"><span data-stu-id="5bc9c-288">**Cause**</span></span>  
 <span data-ttu-id="5bc9c-289">ENTSSO サービスが有効な SSO 管理者アカウントで実行されていない場合、サービスを開始できません。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-289">If the ENTSSO service is not running under a valid SSO Administrator account, it will fail to start.</span></span>  
  
<span data-ttu-id="5bc9c-290">**解決方法**</span><span class="sxs-lookup"><span data-stu-id="5bc9c-290">**Resolution**</span></span>  
 <span data-ttu-id="5bc9c-291">有効な SSO 管理者アカウントを ENTSSO サービスに指定して、サービス コントロール マネージャー (SCM) スナップインからサービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-291">Specify a valid SSO administrator account for the ENTSSO Service and restart the service from Services Control Manager (SCM) snap-in.</span></span>  
  
##### <a name="biztalk-services-dependent-on-the-enterprise-single-sign-on-service-entsso-fail-to-start-after-a-reboot"></a><span data-ttu-id="5bc9c-292">エンタープライズ シングル サインオン サービス (ENTSSO) に依存する BizTalk Services は、再起動後に起動しません。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-292">BizTalk Services dependent on the Enterprise Single Sign-On Service (ENTSSO) fail to start after a reboot</span></span>  
  
<span data-ttu-id="5bc9c-293">**問題**</span><span class="sxs-lookup"><span data-stu-id="5bc9c-293">**Problem**</span></span>  
 <span data-ttu-id="5bc9c-294">BTSSvc$BizTalkServerApplication はエンタープライズ シングル サインオン サービス (ENTSSO) と依存関係があり、リブート後の起動中にタイムアウトすることがあります。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-294">BTSSvc$BizTalkServerApplication has a dependency on the Enterprise Single Sign-On Service (ENTSSO) and may timeout during start up after a reboot.</span></span>  
  
<span data-ttu-id="5bc9c-295">**原因**</span><span class="sxs-lookup"><span data-stu-id="5bc9c-295">**Cause**</span></span>  
 <span data-ttu-id="5bc9c-296">エンタープライズ シングル サインオン サービスは、起動に約 3 分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-296">The Enterprise Single Sign-On Service may take around 3 minutes to start.</span></span>  
  
<span data-ttu-id="5bc9c-297">**解決方法**</span><span class="sxs-lookup"><span data-stu-id="5bc9c-297">**Resolution**</span></span>  
 <span data-ttu-id="5bc9c-298">構成の"BizTalk Service BizTalk Group:自動 (遅延開始) のスタートアップの種類のオプションを持つ BizTalkServerApplication"サービス。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-298">Configure the “BizTalk Service BizTalk Group: BizTalkServerApplication” service with the Automatic (Delayed Start) startup type option.</span></span> <span data-ttu-id="5bc9c-299">これにより、すべての自動サービスのスタートアップ ルーチン完了後に、このサービスが開始されます。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-299">This will initiate the start of the service after all Automatic services have completed their startup routines.</span></span>  
  
##### <a name="cannot-access-an-affiliate-application"></a><span data-ttu-id="5bc9c-300">関連アプリケーションにアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-300">Cannot access an affiliate application</span></span>  
  
<span data-ttu-id="5bc9c-301">**問題**</span><span class="sxs-lookup"><span data-stu-id="5bc9c-301">**Problem**</span></span>  
 <span data-ttu-id="5bc9c-302">関連するアプリケーションの管理者アカウントが有効でない場合、エンタープライズ シングル サインオン サービスはこの関連アプリケーションを無効にします。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-302">The Enterprise Single Sign-On service disables an affiliate application if the application administrator account associated with it is not valid.</span></span>  
  
<span data-ttu-id="5bc9c-303">**原因**</span><span class="sxs-lookup"><span data-stu-id="5bc9c-303">**Cause**</span></span>  
 <span data-ttu-id="5bc9c-304">SSO アプリケーションの管理者アカウントが無効です。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-304">The SSO application administrator account is not valid.</span></span>  
  
<span data-ttu-id="5bc9c-305">**解決方法**</span><span class="sxs-lookup"><span data-stu-id="5bc9c-305">**Resolution**</span></span>  
 <span data-ttu-id="5bc9c-306">関連アプリケーションを作成する前に、SSO アプリケーションの管理者アカウントが有効なことを確認します。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-306">Ensure that the SSO application administrator account is valid before you create an affiliate application.</span></span> <span data-ttu-id="5bc9c-307">関連アプリケーションを使用するには、そのアプリケーションを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-307">You must then enable the affiliate application to use the application.</span></span>  
  
##### <a name="rpc-error-occurs-when-connecting-to-a-client-computer"></a><span data-ttu-id="5bc9c-308">RPC エラーは、クライアント コンピューターに接続するときに発生します。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-308">RPC error occurs when connecting to a client computer</span></span>  
  
<span data-ttu-id="5bc9c-309">**問題**</span><span class="sxs-lookup"><span data-stu-id="5bc9c-309">**Problem**</span></span>  
 <span data-ttu-id="5bc9c-310">などのコマンドを実行すると**ssomanage-displayapp** *< applicationname\>* コンピューターは、情報を取得するリモート SSO サーバーに接続しようとしていますが、受信する、次のエラー:ERROR:0x800706BA:RPC サーバーを利用できません。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-310">When you run a command such as **ssomanage -displayapp** *<applicationname\>*, where the computer attempt to connect to a remote SSO Server to retrieve the information, you receive the following error: ERROR: 0x800706BA: The RPC server is unavailable.</span></span>  
  
<span data-ttu-id="5bc9c-311">**原因**</span><span class="sxs-lookup"><span data-stu-id="5bc9c-311">**Cause**</span></span>  
 <span data-ttu-id="5bc9c-312">このエラーは、間違ったサーバー情報を指定する場合、または SSO サービスがリモート サーバーで利用できない場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-312">This error occurs when you specify the wrong server information, or when the SSO Service is not available on the remote server.</span></span>  
  
<span data-ttu-id="5bc9c-313">**解決方法**</span><span class="sxs-lookup"><span data-stu-id="5bc9c-313">**Resolution**</span></span>  
  
-   <span data-ttu-id="5bc9c-314">次の手順では、 [SSO サーバーを設定](../core/how-to-set-the-sso-server.md)正しい SSO サーバーに接続しているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-314">Follow the steps in [Set the SSO Server](../core/how-to-set-the-sso-server.md) to make sure you are connected to the correct SSO Server.</span></span>  
  
-   <span data-ttu-id="5bc9c-315">接続先の SSO サーバーで SSO サービスが有効になっており、実行されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-315">Make sure the SSO Service is enabled and running in the SSO Server to which you are connecting.</span></span>  
  
##### <a name="master-secret-is-missing-or-corrupt"></a><span data-ttu-id="5bc9c-316">マスター シークレットが見つからないか破損しています</span><span class="sxs-lookup"><span data-stu-id="5bc9c-316">Master Secret is missing or corrupt</span></span>  
  
<span data-ttu-id="5bc9c-317">**問題**</span><span class="sxs-lookup"><span data-stu-id="5bc9c-317">**Problem**</span></span>  
 <span data-ttu-id="5bc9c-318">マスター シークレットがない、または破損しています。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-318">The master secret is missing or corrupt.</span></span> <span data-ttu-id="5bc9c-319">この問題は、主に構成中に発生します。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-319">It normally generates during configuration.</span></span> <span data-ttu-id="5bc9c-320">シークレットがない場合、エンタープライズ シングル サインオン サービスが開始されるときに、以下のいずれかのメッセージがイベント ログに表示されます。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-320">If the secret is missing, one of the following messages will display in the event log as the Enterprise Single Sign-On service starts.</span></span>  
  
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

<span data-ttu-id="5bc9c-321">**原因**</span><span class="sxs-lookup"><span data-stu-id="5bc9c-321">**Cause**</span></span>  
 <span data-ttu-id="5bc9c-322">この問題は、あるサービス アカウントでエンタープライズ シングル サインオン サービス (SSO) を実行中にシークレットを生成した後で、サービス アカウントが変更された場合に発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-322">This problem can occur if a secret is generated while the Enterprise Single Sign-On service (SSO) was running under one service account, and then the service account was changed.</span></span> <span data-ttu-id="5bc9c-323">シークレットは、暗号化された形式でレジストリに保存されます。暗号化には、(ENTSSO を実行する) サービス アカウントの ID を基にしたキーが使用されます。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-323">The secret is stored in the registry in encrypted form, and is encrypted using a key based on the identity of the service account (which ENTSSO runs under).</span></span>  
  
<span data-ttu-id="5bc9c-324">**解決方法**</span><span class="sxs-lookup"><span data-stu-id="5bc9c-324">**Resolution**</span></span>  
 <span data-ttu-id="5bc9c-325">ENTSSO を実行しているサービス アカウントを、マスター シークレット作成時の元のサービス アカウントに変更します。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-325">Change the service account ENTSSO is running under to the original service account when the master secret was created.</span></span>  
  
1.  <span data-ttu-id="5bc9c-326">マスター シークレットをバックアップします。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-326">Back up the master secret.</span></span> <span data-ttu-id="5bc9c-327">参照してください[マスター シークレットをバックアップ](../core/how-to-back-up-the-master-secret.md)します。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-327">See [Back Up the Master Secret](../core/how-to-back-up-the-master-secret.md).</span></span>  
  
2.  <span data-ttu-id="5bc9c-328">エンタープライズ シングル サインオン サービスを停止します。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-328">Stop Enterprise Single Sign-On Services.</span></span>  
  
3.  <span data-ttu-id="5bc9c-329">サービス アカウントを変更します。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-329">Change the service account.</span></span>  
  
4.  <span data-ttu-id="5bc9c-330">SSO を再起動します。破損したシークレットに関するイベント ログのエラーは一切無視します。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-330">Restart SSO and ignore any event log errors about a corrupted secret.</span></span>  
  
5.  <span data-ttu-id="5bc9c-331">マスター シークレットを復元します。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-331">Restore the master secret.</span></span> <span data-ttu-id="5bc9c-332">参照してください[マスター シークレットを復元](../core/how-to-restore-the-master-secret.md)します。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-332">See [Restore the Master Secret](../core/how-to-restore-the-master-secret.md).</span></span>  
  
### <a name="custom-action"></a><span data-ttu-id="5bc9c-333">カスタム アクション</span><span class="sxs-lookup"><span data-stu-id="5bc9c-333">Custom Action</span></span>  
 <span data-ttu-id="5bc9c-334">このトピックでは、Windows Server ロゴ プログラムの BizTalk Server の認定に関する詳細情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-334">This topic provides details about BizTalk Server certification for the Windows Server logo program.</span></span> <span data-ttu-id="5bc9c-335">BizTalk Server セットアップ操作中には、次のカスタム アクションを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-335">The following custom actions might be performed during BizTalk Server Setup operations.</span></span>  
  
|<span data-ttu-id="5bc9c-336">カスタム アクション</span><span class="sxs-lookup"><span data-stu-id="5bc9c-336">Custom action</span></span>|<span data-ttu-id="5bc9c-337">説明</span><span class="sxs-lookup"><span data-stu-id="5bc9c-337">Description</span></span>|  
|-------------------|-----------------|  
|<span data-ttu-id="5bc9c-338">ReadComplusData</span><span class="sxs-lookup"><span data-stu-id="5bc9c-338">ReadComplusData</span></span>|<span data-ttu-id="5bc9c-339">カスタム COM + テーブルを読み取って XML ドキュメントを作成して、Complus_XML_Data プロパティに保存します。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-339">Reads custom COM+ tables, creates XML document, and saves it in the Complus_XML_Data property.</span></span>|  
|<span data-ttu-id="5bc9c-340">SchedXmlConfig</span><span class="sxs-lookup"><span data-stu-id="5bc9c-340">SchedXmlConfig</span></span>|<span data-ttu-id="5bc9c-341">RFID データを持つマシンを構成するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-341">Used for configuring machines having RFID data.</span></span>|  
|<span data-ttu-id="5bc9c-342">CheckBaseEDI</span><span class="sxs-lookup"><span data-stu-id="5bc9c-342">CheckBaseEDI</span></span>|<span data-ttu-id="5bc9c-343">古いバージョンの EDI の存在を確認します</span><span class="sxs-lookup"><span data-stu-id="5bc9c-343">Checks the presence of an old version of EDI</span></span>|  
|<span data-ttu-id="5bc9c-344">CheckMQSeries</span><span class="sxs-lookup"><span data-stu-id="5bc9c-344">CheckMQSeries</span></span>|<span data-ttu-id="5bc9c-345">MQSeries の存在を確認します</span><span class="sxs-lookup"><span data-stu-id="5bc9c-345">Checks the presence of MQSeries</span></span>|  
|<span data-ttu-id="5bc9c-346">CheckNET30Vista</span><span class="sxs-lookup"><span data-stu-id="5bc9c-346">CheckNET30Vista</span></span>|<span data-ttu-id="5bc9c-347">WCF の存在を確認します</span><span class="sxs-lookup"><span data-stu-id="5bc9c-347">Checks the presence of WCF</span></span>|  
|<span data-ttu-id="5bc9c-348">CheckWSSV3SP1</span><span class="sxs-lookup"><span data-stu-id="5bc9c-348">CheckWSSV3SP1</span></span>|<span data-ttu-id="5bc9c-349">Windows SharePoint Services 3.0 SP1 の存在を確認します。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-349">Checks the presence of Windows SharePoint Services 3.0 SP1.</span></span>|  
|<span data-ttu-id="5bc9c-350">CheckWSSV4</span><span class="sxs-lookup"><span data-stu-id="5bc9c-350">CheckWSSV4</span></span>|<span data-ttu-id="5bc9c-351">Windows SharePoint Services 4 の存在を確認します</span><span class="sxs-lookup"><span data-stu-id="5bc9c-351">Checks the presence of Windows SharePoint Services 4</span></span>|  
|<span data-ttu-id="5bc9c-352">GetFrameworkPath</span><span class="sxs-lookup"><span data-stu-id="5bc9c-352">GetFrameworkPath</span></span>|<span data-ttu-id="5bc9c-353">Microsoft .Net framework 4 および 2.0 のインストール パスを保持するインストーラーのインストーラーのプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-353">Sets installer properties in the installer that holds installation path to Microsoft .Net framework 4 and 2.0.</span></span>|  
|<span data-ttu-id="5bc9c-354">Set_BAMClientExcelDir</span><span class="sxs-lookup"><span data-stu-id="5bc9c-354">Set_BAMClientExcelDir</span></span>|<span data-ttu-id="5bc9c-355">インストーラーで Microsoft Office ライブラリ パスを保持するプロパティを設定するための Excel アプリケーション オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-355">Creates an Excel application object for setting a property to hold the Microsoft Office library path in the installer.</span></span>|  
|<span data-ttu-id="5bc9c-356">Set_CurrentUser</span><span class="sxs-lookup"><span data-stu-id="5bc9c-356">Set_CurrentUser</span></span>|<span data-ttu-id="5bc9c-357">現在のユーザーのドメイン \ ユーザー名情報を設定します</span><span class="sxs-lookup"><span data-stu-id="5bc9c-357">Sets domain\username information of the current user</span></span>|  
|<span data-ttu-id="5bc9c-358">ViewInstallGuide</span><span class="sxs-lookup"><span data-stu-id="5bc9c-358">ViewInstallGuide</span></span>|<span data-ttu-id="5bc9c-359">インストールのソース ディレクトリから BizTalk Server インストール ガイドを起動します。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-359">Launches the BizTalk Server installation guide from the installation source directory.</span></span>|  
|<span data-ttu-id="5bc9c-360">CA_CheckSTSLanguage</span><span class="sxs-lookup"><span data-stu-id="5bc9c-360">CA_CheckSTSLanguage</span></span>|<span data-ttu-id="5bc9c-361">WSS および BizTalk の言語セットが同じ場合、STS_Language_Property プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-361">Sets STS_Language_Property property when the language set for WSS and BizTalk are same.</span></span>|  
|<span data-ttu-id="5bc9c-362">CA_CleanupRegistry</span><span class="sxs-lookup"><span data-stu-id="5bc9c-362">CA_CleanupRegistry</span></span>|<span data-ttu-id="5bc9c-363">BizTalk Server をアンインストールする場合は、BizTalk Server の構成中に作成されたレジストリ エントリをクリーンアップします。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-363">When you uninstall BizTalk Server, it cleans the registry entries that were created during BizTalk Server configuration.</span></span>|  
|<span data-ttu-id="5bc9c-364">CA_CleanupRegistry_OldProducts</span><span class="sxs-lookup"><span data-stu-id="5bc9c-364">CA_CleanupRegistry_OldProducts</span></span>|<span data-ttu-id="5bc9c-365">以前のバージョンの BizTalk Server に属し、BizTalk Server の新規インストールの必要のないレジストリ エントリをクリーンアップします。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-365">Cleans the registry entries that belong to an older version of BizTalk Server and are not required for a fresh installation of BizTalk Server.</span></span>|  
|<span data-ttu-id="5bc9c-366">CA_RemovePatches</span><span class="sxs-lookup"><span data-stu-id="5bc9c-366">CA_RemovePatches</span></span>|<span data-ttu-id="5bc9c-367">BizTalk Server をアンインストールする場合に、Microsoft BizTalk Server の更新プログラムを削除します。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-367">Removes Microsoft BizTalk Server updates when you uninstall BizTalk Server.</span></span>|  
|<span data-ttu-id="5bc9c-368">CA_ResolveWellKnownNames</span><span class="sxs-lookup"><span data-stu-id="5bc9c-368">CA_ResolveWellKnownNames</span></span>|<span data-ttu-id="5bc9c-369">よく知られている名前を持つインストーラーのプロパティを作成し、それらに対応する SID を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-369">Creates installer properties with well-known names and assigns them their corresponding SID.</span></span>|  
|<span data-ttu-id="5bc9c-370">CA_SaveTargetVSVersionToRegistry</span><span class="sxs-lookup"><span data-stu-id="5bc9c-370">CA_SaveTargetVSVersionToRegistry</span></span>|<span data-ttu-id="5bc9c-371">サポートされているバージョンの Visual Studio の値を TargetVSVersion_Property プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-371">Sets a TargetVSVersion_Property property to the value of a supported version of Visual Studio.</span></span>|  
|<span data-ttu-id="5bc9c-372">CA_StopServices</span><span class="sxs-lookup"><span data-stu-id="5bc9c-372">CA_StopServices</span></span>|<span data-ttu-id="5bc9c-373">IISAdmin、ルール エンジンの更新、および EDI サブシステム サービスを停止します。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-373">Stops IISAdmin, Rules Engine Update and EDI Subsystem services.</span></span>|  
|<span data-ttu-id="5bc9c-374">CleanupUsersKeys</span><span class="sxs-lookup"><span data-stu-id="5bc9c-374">CleanupUsersKeys</span></span>|<span data-ttu-id="5bc9c-375">関連するエントリは HKEY_CURRENT_USER レジストリ キーから BizTalk Server を削除します。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-375">Removes BizTalk Server related entries from the HKEY_CURRENT_USER registry key.</span></span>|  
|<span data-ttu-id="5bc9c-376">DevEnvRunning</span><span class="sxs-lookup"><span data-stu-id="5bc9c-376">DevEnvRunning</span></span>|<span data-ttu-id="5bc9c-377">Visual Studio が実行されているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-377">Checks whether Visual Studio is running</span></span>|  
|<span data-ttu-id="5bc9c-378">ValidateINSTALLDIR</span><span class="sxs-lookup"><span data-stu-id="5bc9c-378">ValidateINSTALLDIR</span></span>|<span data-ttu-id="5bc9c-379">BizTalk Server のインストール ディレクトリ形式を検証します。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-379">Validates BizTalk Server installation directory format</span></span>|  
|<span data-ttu-id="5bc9c-380">StartHostInstances</span><span class="sxs-lookup"><span data-stu-id="5bc9c-380">StartHostInstances</span></span>|<span data-ttu-id="5bc9c-381">BizTalk Server ホスト インスタンスを開始します。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-381">Starts BizTalk Server Host Instances.</span></span>|  
|<span data-ttu-id="5bc9c-382">StopHostInstances</span><span class="sxs-lookup"><span data-stu-id="5bc9c-382">StopHostInstances</span></span>|<span data-ttu-id="5bc9c-383">BizTalk Server ホスト インスタンスを停止します。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-383">Stops BizTalk Server Host Instances.</span></span>|  
|<span data-ttu-id="5bc9c-384">MQSUnConfig</span><span class="sxs-lookup"><span data-stu-id="5bc9c-384">MQSUnConfig</span></span>|<span data-ttu-id="5bc9c-385">構成解除の MQSeries の MQSeries 構成ウィザードを起動エージェント。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-385">Launches MQSeries Configuration wizard for un-configuring MQSeries agent.</span></span>|  
|<span data-ttu-id="5bc9c-386">LaunchConfigFmk</span><span class="sxs-lookup"><span data-stu-id="5bc9c-386">LaunchConfigFmk</span></span>|<span data-ttu-id="5bc9c-387">BizTalk Server 構成ウィザードを起動します。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-387">Launches BizTalk Server Configuration Wizard</span></span>|  
|<span data-ttu-id="5bc9c-388">CHKASPNET</span><span class="sxs-lookup"><span data-stu-id="5bc9c-388">CHKASPNET</span></span>|<span data-ttu-id="5bc9c-389">ASP.NET のインストール状態を確認します。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-389">Checks the install state of ASP.NET</span></span>|  
|<span data-ttu-id="5bc9c-390">CHKIIS</span><span class="sxs-lookup"><span data-stu-id="5bc9c-390">CHKIIS</span></span>|<span data-ttu-id="5bc9c-391">IIS のインストール状態を確認します。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-391">Checks the install state of IIS</span></span>|  
|<span data-ttu-id="5bc9c-392">TBExpired</span><span class="sxs-lookup"><span data-stu-id="5bc9c-392">TBExpired</span></span>|<span data-ttu-id="5bc9c-393">BizTalk Server の TimeBomb の有効期限が切れてを確認します。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-393">Checks if the BizTalk Server TimeBomb has expired</span></span>|  
|<span data-ttu-id="5bc9c-394">BrandSKU</span><span class="sxs-lookup"><span data-stu-id="5bc9c-394">BrandSKU</span></span>|<span data-ttu-id="5bc9c-395">SKU のインストールに依存する BizTalk Server の timebomb の値を更新します。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-395">Updates the value of BizTalk Server timebomb which depends on SKU installation.</span></span>|  
|<span data-ttu-id="5bc9c-396">CA_ERROR</span><span class="sxs-lookup"><span data-stu-id="5bc9c-396">CA_ERROR</span></span>|<span data-ttu-id="5bc9c-397">インストール エラーを返します</span><span class="sxs-lookup"><span data-stu-id="5bc9c-397">Returns installation failure</span></span>|  
|<span data-ttu-id="5bc9c-398">InstallComplus</span><span class="sxs-lookup"><span data-stu-id="5bc9c-398">InstallComplus</span></span>|<span data-ttu-id="5bc9c-399">Complus アプリケーションとコンポーネントをインストールします。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-399">Installs Complus applications and components.</span></span>|  
|<span data-ttu-id="5bc9c-400">BAM_Add_Perf_Silent</span><span class="sxs-lookup"><span data-stu-id="5bc9c-400">BAM_Add_Perf_Silent</span></span>|<span data-ttu-id="5bc9c-401">BAM のパフォーマンス カウンターをインストールします。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-401">Installs performance counters for BAM</span></span>|  
|<span data-ttu-id="5bc9c-402">RegsvcsApplicationDeployment</span><span class="sxs-lookup"><span data-stu-id="5bc9c-402">RegsvcsApplicationDeployment</span></span>|<span data-ttu-id="5bc9c-403">BizTalk 展開 COM + アプリケーション Dll に対して Regsvcs.exe (.NET サービス インストール ツール) を実行します。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-403">Runs Regsvcs.exe (.NET Services Installation Tool) on BizTalk Deployment COM+ application DLLs</span></span>|  
|<span data-ttu-id="5bc9c-404">RegsvcsDeployment</span><span class="sxs-lookup"><span data-stu-id="5bc9c-404">RegsvcsDeployment</span></span>|<span data-ttu-id="5bc9c-405">Dll に対して Regsvcs.exe を実行します。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-405">Runs Regsvcs.exe on DLLs</span></span>|  
|<span data-ttu-id="5bc9c-406">RegsvcsMQSAdapter</span><span class="sxs-lookup"><span data-stu-id="5bc9c-406">RegsvcsMQSAdapter</span></span>|<span data-ttu-id="5bc9c-407">Dll に対して Regsvcs.exe を実行します。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-407">Runs Regsvcs.exe on DLLs</span></span>|  
|<span data-ttu-id="5bc9c-408">RegsvcsSQLAdapter</span><span class="sxs-lookup"><span data-stu-id="5bc9c-408">RegsvcsSQLAdapter</span></span>|<span data-ttu-id="5bc9c-409">Dll に対して Regsvcs.exe を実行します。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-409">Runs Regsvcs.exe on DLLs</span></span>|  
|<span data-ttu-id="5bc9c-410">WMI_Add_MSBTS_Silent</span><span class="sxs-lookup"><span data-stu-id="5bc9c-410">WMI_Add_MSBTS_Silent</span></span>|<span data-ttu-id="5bc9c-411">BizTalk Server の名前空間とクラスを WMI に登録します。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-411">Registers BizTalk Server namespace and classes to WMI.</span></span>|  
|<span data-ttu-id="5bc9c-412">LaunchConfigFmk_SlashUP</span><span class="sxs-lookup"><span data-stu-id="5bc9c-412">LaunchConfigFmk_SlashUP</span></span>|<span data-ttu-id="5bc9c-413">BizTalk Server の構成を解除します</span><span class="sxs-lookup"><span data-stu-id="5bc9c-413">Un-configures BizTalk Server</span></span>|  
|<span data-ttu-id="5bc9c-414">CleanupComplus</span><span class="sxs-lookup"><span data-stu-id="5bc9c-414">CleanupComplus</span></span>|<span data-ttu-id="5bc9c-415">Complus アプリケーションとコンポーネントをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-415">Uninstalls Complus Applications and components.</span></span>|  
|<span data-ttu-id="5bc9c-416">RemoveSKU</span><span class="sxs-lookup"><span data-stu-id="5bc9c-416">RemoveSKU</span></span>|<span data-ttu-id="5bc9c-417">BizTalk Server TimeBomb データを削除します。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-417">Removes BizTalk Server TimeBomb data.</span></span>|  
|<span data-ttu-id="5bc9c-418">BAM_Remove_Perf</span><span class="sxs-lookup"><span data-stu-id="5bc9c-418">BAM_Remove_Perf</span></span>|<span data-ttu-id="5bc9c-419">BAM のパフォーマンス カウンターをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-419">Uninstalls performance counters for BAM.</span></span>|  
|<span data-ttu-id="5bc9c-420">LoadBTSCounters</span><span class="sxs-lookup"><span data-stu-id="5bc9c-420">LoadBTSCounters</span></span>|<span data-ttu-id="5bc9c-421">BizTalk Server パフォーマンス カウンターを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-421">Loads BizTalk Server performance counters.</span></span>|  
|<span data-ttu-id="5bc9c-422">RegisterBtprojExtn</span><span class="sxs-lookup"><span data-stu-id="5bc9c-422">RegisterBtprojExtn</span></span>|<span data-ttu-id="5bc9c-423">BizTalk プロジェクト ファイル (.btproj) の拡張機能を登録します。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-423">Registers BizTalk project file (.btproj) extension.</span></span>|  
|<span data-ttu-id="5bc9c-424">UnRegisterBtprojExtn</span><span class="sxs-lookup"><span data-stu-id="5bc9c-424">UnRegisterBtprojExtn</span></span>|<span data-ttu-id="5bc9c-425">BizTalk プロジェクト ファイル (.btproj) の拡張子を登録を解除します。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-425">Un-registers BizTalk project file (.btproj) extension.</span></span>|  
|<span data-ttu-id="5bc9c-426">UnRegsvcsApplicationDeployment</span><span class="sxs-lookup"><span data-stu-id="5bc9c-426">UnRegsvcsApplicationDeployment</span></span>|<span data-ttu-id="5bc9c-427">BizTalk Server をアンインストールするときに、特定の Dll で Regsvcs.exe を実行します。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-427">Runs Regsvcs.exe on certain DLLs when you uninstall BizTalk Server</span></span>|  
|<span data-ttu-id="5bc9c-428">UnRegsvcsDeployment</span><span class="sxs-lookup"><span data-stu-id="5bc9c-428">UnRegsvcsDeployment</span></span>|<span data-ttu-id="5bc9c-429">BizTalk Server をアンインストールするときに、特定の Dll で Regsvcs.exe を実行します。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-429">Runs Regsvcs.exe on certain DLLs when you uninstall BizTalk Server</span></span>|  
|<span data-ttu-id="5bc9c-430">UnRegsvcsMQSAdapter</span><span class="sxs-lookup"><span data-stu-id="5bc9c-430">UnRegsvcsMQSAdapter</span></span>|<span data-ttu-id="5bc9c-431">BizTalk Server をアンインストールするときに、特定の Dll で Regsvcs.exe を実行します。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-431">Runs Regsvcs.exe on certain DLLs when you uninstall BizTalk Server</span></span>|  
|<span data-ttu-id="5bc9c-432">UnRegsvcsSQLAdapter</span><span class="sxs-lookup"><span data-stu-id="5bc9c-432">UnRegsvcsSQLAdapter</span></span>|<span data-ttu-id="5bc9c-433">BizTalk Server をアンインストールするときに、特定の Dll で Regsvcs.exe を実行します。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-433">Runs Regsvcs.exe on certain DLLs when you uninstall BizTalk Server</span></span>|  
|<span data-ttu-id="5bc9c-434">UnloadBTSCounters</span><span class="sxs-lookup"><span data-stu-id="5bc9c-434">UnloadBTSCounters</span></span>|<span data-ttu-id="5bc9c-435">BizTalk Server パフォーマンス カウンターをアンロードします。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-435">Unloads BizTalk Server performance counters.</span></span>|  
|<span data-ttu-id="5bc9c-436">WMI_Remove_MSBTS</span><span class="sxs-lookup"><span data-stu-id="5bc9c-436">WMI_Remove_MSBTS</span></span>|<span data-ttu-id="5bc9c-437">WMI から BizTalk Server の名前空間を削除します。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-437">Removes BizTalk Server namespace from WMI.</span></span>|  
|<span data-ttu-id="5bc9c-438">RegisterComsvcs</span><span class="sxs-lookup"><span data-stu-id="5bc9c-438">RegisterComsvcs</span></span>|<span data-ttu-id="5bc9c-439">Runs regsvr32.exe on comsvcs.dll silently.</span><span class="sxs-lookup"><span data-stu-id="5bc9c-439">Runs regsvr32.exe on comsvcs.dll silently.</span></span>|  
|<span data-ttu-id="5bc9c-440">DevenvSetupUninstall</span><span class="sxs-lookup"><span data-stu-id="5bc9c-440">DevenvSetupUninstall</span></span>|<span data-ttu-id="5bc9c-441">DevEnv.exe/setup/resetskippkgs を実行します。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-441">Runs DevEnv.exe /Setup/resetskippkgs.</span></span>|  
|<span data-ttu-id="5bc9c-442">RollbackComplus</span><span class="sxs-lookup"><span data-stu-id="5bc9c-442">RollbackComplus</span></span>|<span data-ttu-id="5bc9c-443">ロールバック Complus アプリケーションとコンポーネントをインストールします。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-443">Rollbacks the installation of Complus applications and components.</span></span>|  
|<span data-ttu-id="5bc9c-444">ResRegsvcsMQSAdapter</span><span class="sxs-lookup"><span data-stu-id="5bc9c-444">ResRegsvcsMQSAdapter</span></span>|<span data-ttu-id="5bc9c-445">指定されたバイナリで regsvcs.exe を実行します。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-445">Runs regsvcs.exe on a given binary</span></span>|  
|<span data-ttu-id="5bc9c-446">ResRegsvcsSQLAdapter</span><span class="sxs-lookup"><span data-stu-id="5bc9c-446">ResRegsvcsSQLAdapter</span></span>|<span data-ttu-id="5bc9c-447">指定されたバイナリで regsvcs.exe を実行します。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-447">Runs regsvcs.exe on a given binary</span></span>|  
|<span data-ttu-id="5bc9c-448">RestoreRegsvcsApplicationDeployment</span><span class="sxs-lookup"><span data-stu-id="5bc9c-448">RestoreRegsvcsApplicationDeployment</span></span>|<span data-ttu-id="5bc9c-449">Microsoft.biztalk.applicationdeployment.engine.dll フレームワークのパスを追加します。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-449">Appends the path of framework with Microsoft.BizTalk.ApplicationDeployment.Engine.dll.</span></span>|  
|<span data-ttu-id="5bc9c-450">RestoreRegsvcsDeployment</span><span class="sxs-lookup"><span data-stu-id="5bc9c-450">RestoreRegsvcsDeployment</span></span>|<span data-ttu-id="5bc9c-451">Microsoft.biztalk.applicationdeployment.engine.dll フレームワークのパスを追加します。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-451">Appends the path of framework with Microsoft.BizTalk.ApplicationDeployment.Engine.dll.</span></span>|  
|<span data-ttu-id="5bc9c-452">BrandSKURollback</span><span class="sxs-lookup"><span data-stu-id="5bc9c-452">BrandSKURollback</span></span>|<span data-ttu-id="5bc9c-453">インストール エラーが発生した場合、登録した SKU 情報をロールバックします。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-453">Rollbacks registered SKU information if installation failure occurs.</span></span>|  
|<span data-ttu-id="5bc9c-454">CA_RestartServices_rollback</span><span class="sxs-lookup"><span data-stu-id="5bc9c-454">CA_RestartServices_rollback</span></span>|<span data-ttu-id="5bc9c-455">停止したサービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-455">Restarts the stopped services.</span></span>|  
|<span data-ttu-id="5bc9c-456">RemoveSKURollback</span><span class="sxs-lookup"><span data-stu-id="5bc9c-456">RemoveSKURollback</span></span>|<span data-ttu-id="5bc9c-457">レジストリから SKU 値を更新します。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-457">Updates the SKU values from the registry.</span></span>|  
|<span data-ttu-id="5bc9c-458">BAM_Res_Perf_Silent</span><span class="sxs-lookup"><span data-stu-id="5bc9c-458">BAM_Res_Perf_Silent</span></span>|<span data-ttu-id="5bc9c-459">サイレント インストール時に BAM パフォーマンス カウンター Dll としての Microsoft.BizTalk.Bam.EventObservation.dll を登録します。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-459">Registers Microsoft.BizTalk.Bam.EventObservation.dll as the BAM performance counter DLLs during silent installation.</span></span>|  
|<span data-ttu-id="5bc9c-460">BAM_Rollback_Perf</span><span class="sxs-lookup"><span data-stu-id="5bc9c-460">BAM_Rollback_Perf</span></span>|<span data-ttu-id="5bc9c-461">Microsoft.BizTalk.Bam.EventObservation.dll を BAM パフォーマンス カウンター DLL として登録を解除します</span><span class="sxs-lookup"><span data-stu-id="5bc9c-461">Unregisters  Microsoft.BizTalk.Bam.EventObservation.dll as the BAM performance counter DLL</span></span>|  
|<span data-ttu-id="5bc9c-462">RBKRegsvcsMQSAdapter</span><span class="sxs-lookup"><span data-stu-id="5bc9c-462">RBKRegsvcsMQSAdapter</span></span>|<span data-ttu-id="5bc9c-463">指定されたバイナリでは、regsvcs.exe を実行します。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-463">Runs regsvcs.exe on a given binary.</span></span>|  
|<span data-ttu-id="5bc9c-464">RBKRegsvcsSQLAdapter</span><span class="sxs-lookup"><span data-stu-id="5bc9c-464">RBKRegsvcsSQLAdapter</span></span>|<span data-ttu-id="5bc9c-465">指定されたバイナリでは、regsvcs.exe を実行します。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-465">Runs regsvcs.exe on a given binary.</span></span>|  
|<span data-ttu-id="5bc9c-466">RestoreBTSCounters</span><span class="sxs-lookup"><span data-stu-id="5bc9c-466">RestoreBTSCounters</span></span>|<span data-ttu-id="5bc9c-467">パフォーマンス カウンターの .ini ファイル名のプロパティを復元します。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-467">Restores the property with the performance counter .ini file name.</span></span>|  
|<span data-ttu-id="5bc9c-468">RollbackBTSCounters</span><span class="sxs-lookup"><span data-stu-id="5bc9c-468">RollbackBTSCounters</span></span>|<span data-ttu-id="5bc9c-469">Unlodctr BTSSvc.3.0 コマンドします。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-469">Runs command unlodctr BTSSvc.3.0.</span></span>|  
|<span data-ttu-id="5bc9c-470">RollbackRegsvcsApplicationDeployment</span><span class="sxs-lookup"><span data-stu-id="5bc9c-470">RollbackRegsvcsApplicationDeployment</span></span>|<span data-ttu-id="5bc9c-471">[FrameworkPath] 設定&#124;[失敗したインストール シナリオの INSTALLDIR]Microsoft.BizTalk.ApplicationDeployment.Engine.dll します。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-471">Sets up [FrameworkPath]&#124;[INSTALLDIR]Microsoft.BizTalk.ApplicationDeployment.Engine.dll for the failed installation scenarios.</span></span>|  
|<span data-ttu-id="5bc9c-472">RollbackRegsvcsDeployment</span><span class="sxs-lookup"><span data-stu-id="5bc9c-472">RollbackRegsvcsDeployment</span></span>|<span data-ttu-id="5bc9c-473">アンインストール/ロールバック シナリオで regsvcs.exe を起動します。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-473">Invokes regsvcs.exe during uninstall/rollback scenarios.</span></span>|  
|<span data-ttu-id="5bc9c-474">WMI_Restore_MSBTS_Silent</span><span class="sxs-lookup"><span data-stu-id="5bc9c-474">WMI_Restore_MSBTS_Silent</span></span>|<span data-ttu-id="5bc9c-475">WMI スキーマを登録する mofcomp を呼び出してください。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-475">Calls mofcomp to register WMI schemas</span></span>|  
|<span data-ttu-id="5bc9c-476">WMI_Rollback_MSBTS</span><span class="sxs-lookup"><span data-stu-id="5bc9c-476">WMI_Rollback_MSBTS</span></span>|<span data-ttu-id="5bc9c-477">WMI から BizTalk Server の名前空間を削除します。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-477">Removes BizTalk Server namespace from WMI.</span></span>|  
|<span data-ttu-id="5bc9c-478">CA_RestartServices_commit</span><span class="sxs-lookup"><span data-stu-id="5bc9c-478">CA_RestartServices_commit</span></span>|<span data-ttu-id="5bc9c-479">停止したサービスします。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-479">Restarts the stopped services</span></span>|  
|<span data-ttu-id="5bc9c-480">DevenvSetup</span><span class="sxs-lookup"><span data-stu-id="5bc9c-480">DevenvSetup</span></span>|<span data-ttu-id="5bc9c-481">BizTalk Server の中にインストール/アンインストール プロセスの両方で DevEnv.exe/Setup/resetskippkgs を実行します。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-481">Runs DevEnv.exe /Setup /resetskippkgs both during BizTalk Server install/uninstall process.</span></span>|  
|<span data-ttu-id="5bc9c-482">ExecXmlConfig</span><span class="sxs-lookup"><span data-stu-id="5bc9c-482">ExecXmlConfig</span></span>|<span data-ttu-id="5bc9c-483">RFID の machine.config に構成の変更に使用されるデータに関連します。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-483">Used to make configuration changes to machine.config for RFID related data.</span></span>|  
|<span data-ttu-id="5bc9c-484">ExecXmlConfigRollback</span><span class="sxs-lookup"><span data-stu-id="5bc9c-484">ExecXmlConfigRollback</span></span>|<span data-ttu-id="5bc9c-485">RFID の machine.config に構成の変更に使用されるデータに関連します。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-485">Used to make configuration changes to machine.config for RFID related data.</span></span>|  
  
#### <a name="running-biztalk-components"></a><span data-ttu-id="5bc9c-486">BizTalk コンポーネントの実行</span><span class="sxs-lookup"><span data-stu-id="5bc9c-486">Running BizTalk Components</span></span>  
 <span data-ttu-id="5bc9c-487">次の表に、管理者特権で実行する必要がある BizTalk コンポーネントまたは使用可能な最高です。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-487">The following table lists BizTalk components that must be run using administrative privileges or with highest available privilege.</span></span>  
  
|<span data-ttu-id="5bc9c-488">フォルダーのパス</span><span class="sxs-lookup"><span data-stu-id="5bc9c-488">Folder path</span></span>|<span data-ttu-id="5bc9c-489">ファイル名</span><span class="sxs-lookup"><span data-stu-id="5bc9c-489">File name</span></span>|<span data-ttu-id="5bc9c-490">ユーザー特権</span><span class="sxs-lookup"><span data-stu-id="5bc9c-490">User privileges</span></span>|  
|-----------------|---------------|---------------------|  
|<span data-ttu-id="5bc9c-491">\Program Files (x86)\Common Files\Microsoft shared\Help 9\Microsoft Document Explorer 2008</span><span class="sxs-lookup"><span data-stu-id="5bc9c-491">\Program Files (x86)\Common Files\Microsoft shared\Help 9\Microsoft Document Explorer 2008</span></span>|<span data-ttu-id="5bc9c-492">Install.exe</span><span class="sxs-lookup"><span data-stu-id="5bc9c-492">Install.exe</span></span>|<span data-ttu-id="5bc9c-493">最も高い特権</span><span class="sxs-lookup"><span data-stu-id="5bc9c-493">Highest available privilege</span></span>|  
|<span data-ttu-id="5bc9c-494">\Program files (x86) \Microsoft BizTalk Server*バージョン*</span><span class="sxs-lookup"><span data-stu-id="5bc9c-494">\Program Files (x86)\Microsoft BizTalk Server *your version*</span></span>|<span data-ttu-id="5bc9c-495">BTSHatApp.exe</span><span class="sxs-lookup"><span data-stu-id="5bc9c-495">BTSHatApp.exe</span></span>|<span data-ttu-id="5bc9c-496">最も高い特権</span><span class="sxs-lookup"><span data-stu-id="5bc9c-496">Highest available privilege</span></span>|  
|<span data-ttu-id="5bc9c-497">\Program files (x86) \Microsoft BizTalk Server*バージョン*</span><span class="sxs-lookup"><span data-stu-id="5bc9c-497">\Program Files (x86)\Microsoft BizTalk Server *your version*</span></span>|<span data-ttu-id="5bc9c-498">BTSMMCLauncher.exe</span><span class="sxs-lookup"><span data-stu-id="5bc9c-498">BTSMMCLauncher.exe</span></span>|<span data-ttu-id="5bc9c-499">最も高い特権</span><span class="sxs-lookup"><span data-stu-id="5bc9c-499">Highest available privilege</span></span>|  
|<span data-ttu-id="5bc9c-500">\Program files (x86) \Microsoft BizTalk Server*バージョン*</span><span class="sxs-lookup"><span data-stu-id="5bc9c-500">\Program Files (x86)\Microsoft BizTalk Server *your version*</span></span>|<span data-ttu-id="5bc9c-501">BtsWcfServicePublishingWizard.exe</span><span class="sxs-lookup"><span data-stu-id="5bc9c-501">BtsWcfServicePublishingWizard.exe</span></span>|<span data-ttu-id="5bc9c-502">最も高い特権</span><span class="sxs-lookup"><span data-stu-id="5bc9c-502">Highest available privilege</span></span>|  
|<span data-ttu-id="5bc9c-503">\Program files (x86) \Microsoft BizTalk Server*バージョン*</span><span class="sxs-lookup"><span data-stu-id="5bc9c-503">\Program Files (x86)\Microsoft BizTalk Server *your version*</span></span>|<span data-ttu-id="5bc9c-504">BTSWebSvcWiz.exe</span><span class="sxs-lookup"><span data-stu-id="5bc9c-504">BTSWebSvcWiz.exe</span></span>|<span data-ttu-id="5bc9c-505">最も高い特権</span><span class="sxs-lookup"><span data-stu-id="5bc9c-505">Highest available privilege</span></span>|  
|<span data-ttu-id="5bc9c-506">\Program files (x86) \Microsoft BizTalk Server*バージョン*</span><span class="sxs-lookup"><span data-stu-id="5bc9c-506">\Program Files (x86)\Microsoft BizTalk Server *your version*</span></span>|<span data-ttu-id="5bc9c-507">Configuration.exe</span><span class="sxs-lookup"><span data-stu-id="5bc9c-507">Configuration.exe</span></span>|<span data-ttu-id="5bc9c-508">最も高い特権</span><span class="sxs-lookup"><span data-stu-id="5bc9c-508">Highest available privilege</span></span>|  
|<span data-ttu-id="5bc9c-509">\Program files (x86) \Microsoft BizTalk Server*バージョン*</span><span class="sxs-lookup"><span data-stu-id="5bc9c-509">\Program Files (x86)\Microsoft BizTalk Server *your version*</span></span>|<span data-ttu-id="5bc9c-510">REDeployWiz.exe</span><span class="sxs-lookup"><span data-stu-id="5bc9c-510">REDeployWiz.exe</span></span>|<span data-ttu-id="5bc9c-511">最も高い特権</span><span class="sxs-lookup"><span data-stu-id="5bc9c-511">Highest available privilege</span></span>|  
|<span data-ttu-id="5bc9c-512">\Program files (x86) \Microsoft BizTalk Server*バージョン*</span><span class="sxs-lookup"><span data-stu-id="5bc9c-512">\Program Files (x86)\Microsoft BizTalk Server *your version*</span></span>|<span data-ttu-id="5bc9c-513">Setup.exe</span><span class="sxs-lookup"><span data-stu-id="5bc9c-513">Setup.exe</span></span>|<span data-ttu-id="5bc9c-514">管理者特権</span><span class="sxs-lookup"><span data-stu-id="5bc9c-514">Administrative privilege</span></span>|  
|<span data-ttu-id="5bc9c-515">\Program files (x86) \Microsoft BizTalk Server*バージョン*\XSD Schema\EDI</span><span class="sxs-lookup"><span data-stu-id="5bc9c-515">\Program Files (x86)\Microsoft BizTalk Server *your version*\XSD Schema\EDI</span></span>|<span data-ttu-id="5bc9c-516">MicrosoftEdiXSDTemplates.exe</span><span class="sxs-lookup"><span data-stu-id="5bc9c-516">MicrosoftEdiXSDTemplates.exe</span></span>|<span data-ttu-id="5bc9c-517">自己解凍形式の .exe ファイルです。</span><span class="sxs-lookup"><span data-stu-id="5bc9c-517">Self-extracting .exe file.</span></span>|  
|<span data-ttu-id="5bc9c-518">\Program Files (x86)\Microsoft UDDI Services\config</span><span class="sxs-lookup"><span data-stu-id="5bc9c-518">\Program Files (x86)\Microsoft UDDI Services\config</span></span>|<span data-ttu-id="5bc9c-519">構成の .exe</span><span class="sxs-lookup"><span data-stu-id="5bc9c-519">Configuration .exe</span></span>|<span data-ttu-id="5bc9c-520">管理者特権</span><span class="sxs-lookup"><span data-stu-id="5bc9c-520">Administrative privilege</span></span>|  
|<span data-ttu-id="5bc9c-521">\Program Files\ Microsoft BizTalk RFID\bin</span><span class="sxs-lookup"><span data-stu-id="5bc9c-521">\Program Files\ Microsoft BizTalk RFID\bin</span></span>|<span data-ttu-id="5bc9c-522">BTSMMCLauncher.exe</span><span class="sxs-lookup"><span data-stu-id="5bc9c-522">BTSMMCLauncher.exe</span></span>|<span data-ttu-id="5bc9c-523">最も高い特権</span><span class="sxs-lookup"><span data-stu-id="5bc9c-523">Highest available privilege</span></span>|  
|<span data-ttu-id="5bc9c-524">\Program Files\Microsoft BizTalk RFID\BREConfi 再構成</span><span class="sxs-lookup"><span data-stu-id="5bc9c-524">\Program Files\Microsoft BizTalk RFID\BREConfi guration</span></span>|<span data-ttu-id="5bc9c-525">構成の .exe</span><span class="sxs-lookup"><span data-stu-id="5bc9c-525">Configuration .exe</span></span>|<span data-ttu-id="5bc9c-526">管理者特権</span><span class="sxs-lookup"><span data-stu-id="5bc9c-526">Administrative privilege</span></span>|  
