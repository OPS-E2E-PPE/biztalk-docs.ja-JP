---
title: 既知の問題は、インストール、構成、および展開 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ed1c08eb-d647-4a4a-b9a3-c4d84e8d4b82
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 067d579317f9f034c65fe0f23cbf2f2d7f7b77f6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36982651"
---
# <a name="known-issues-in-installation-configuration-and-deployment"></a><span data-ttu-id="b6770-102">インストール、構成、および展開での既知の問題</span><span class="sxs-lookup"><span data-stu-id="b6770-102">Known Issues in Installation, Configuration, and Deployment</span></span>
## <a name="some-biztalk-edias2-artifacts-are-still-active-after-unconfiguring"></a><span data-ttu-id="b6770-103">一部の BizTalk EDI/AS2 アイテムが構成解除した後もアクティブになっている</span><span class="sxs-lookup"><span data-stu-id="b6770-103">Some BizTalk EDI/AS2 Artifacts Are Still Active After Unconfiguring</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="b6770-104">問題</span><span class="sxs-lookup"><span data-stu-id="b6770-104">Problem</span></span>  
 <span data-ttu-id="b6770-105">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の BizTalk EDI/AS2 機能を構成解除した後、EDI 処理および AS2 処理に関連する一部の BizTalk Server アイテムが、BizTalk グループ構成のコンテキストにおいてアクティブのままとなります。</span><span class="sxs-lookup"><span data-stu-id="b6770-105">After you unconfigure the BizTalk EDI/AS2 feature of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], some BizTalk Server artifacts related to EDI and AS2 processing will still be active in the context of the BizTalk group configuration.</span></span> <span data-ttu-id="b6770-106">これらのアイテムには、EDI パイプライン、AS2 パイプライン、バッチ処理オーケストレーションなどがあります。</span><span class="sxs-lookup"><span data-stu-id="b6770-106">These artifacts will include EDI and AS2 pipelines and the batching orchestration.</span></span> <span data-ttu-id="b6770-107">このため、BizTalk EDI/AS2 機能を構成解除した後でも、基本的な EDI 処理および AS2 処理を実行できます。</span><span class="sxs-lookup"><span data-stu-id="b6770-107">As a result, you will still be able to perform basic EDI and AS2 processing even after unconfiguring the BizTalk EDI/AS2 feature.</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="b6770-108">原因</span><span class="sxs-lookup"><span data-stu-id="b6770-108">Cause</span></span>  
 <span data-ttu-id="b6770-109">EDI 処理および AS2 処理に関連付けられているアクティブなポートがあります。</span><span class="sxs-lookup"><span data-stu-id="b6770-109">There are active ports associated with EDI and AS2 processing.</span></span> <span data-ttu-id="b6770-110">一部のアイテムは、これらのポートがアクティブである間は、引き続き機能します。</span><span class="sxs-lookup"><span data-stu-id="b6770-110">Some artifacts will continue to function while these ports remain active.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="b6770-111">解決方法</span><span class="sxs-lookup"><span data-stu-id="b6770-111">Resolution</span></span>  
 <span data-ttu-id="b6770-112">すべての EDI/AS2 アイテムを無効にするには、EDI 処理および AS2 処理に関連付けられているポートを無効化、停止、または削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b6770-112">To disable all EDI/AS2 artifacts, you should disable, stop, or delete the ports associated with EDI and AS2 processing.</span></span>  
  
## <a name="if-the-biztalk-server-computer-or-sql-server-computer-is-renamed-after-biztalk-server-configuration-the-configuration-wizard-will-fail"></a><span data-ttu-id="b6770-113">BizTalk Server を構成した後に BizTalk Server のコンピューターまたは SQL Server のコンピューターの名前を変更すると、構成ウィザードが失敗する</span><span class="sxs-lookup"><span data-stu-id="b6770-113">If the BizTalk Server Computer or SQL Server Computer Is Renamed After BizTalk Server Configuration, the Configuration Wizard Will Fail</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="b6770-114">問題</span><span class="sxs-lookup"><span data-stu-id="b6770-114">Problem</span></span>  
 <span data-ttu-id="b6770-115">この問題は、次のようにさまざまなケースで生じることがあります。</span><span class="sxs-lookup"><span data-stu-id="b6770-115">This problem may manifest itself in several ways:</span></span>  
  
-   <span data-ttu-id="b6770-116">BizTalk Server 構成で概要ページを正しく読み込むことができましたが、機能を構成しようとすると、画面に機能オプションが表示されません。</span><span class="sxs-lookup"><span data-stu-id="b6770-116">The BizTalk Server Configuration will load the Overview page correctly, but when attempting to configure a feature the feature options do not display on the screen.</span></span>  
  
-   <span data-ttu-id="b6770-117">構成ウィザードが SQL Server に接続できません。</span><span class="sxs-lookup"><span data-stu-id="b6770-117">The configuration wizard cannot connect to the SQL Server.</span></span>  
  
-   <span data-ttu-id="b6770-118">すべての構成を解除しようとすると、一部の機能は解除されますが、すべての機能は解除されません。</span><span class="sxs-lookup"><span data-stu-id="b6770-118">Attempting to Unconfigure All unconfigures some features, but not all.</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="b6770-119">原因</span><span class="sxs-lookup"><span data-stu-id="b6770-119">Cause</span></span>  
 <span data-ttu-id="b6770-120">BizTalk Server の構成では、コンピューターのネットワーク名を格納します。</span><span class="sxs-lookup"><span data-stu-id="b6770-120">The BizTalk Server configuration stores the computer network name.</span></span> <span data-ttu-id="b6770-121">BizTalk Server 構成のコンピューターの名前が変更されると、構成ウィザードは BizTalk Server を特定できなくなります。</span><span class="sxs-lookup"><span data-stu-id="b6770-121">When the computer is renamed the BizTalk Server Configuration and configuration wizard cannot locate the BizTalk Server.</span></span> <span data-ttu-id="b6770-122">BizTalk Server を構成した後に SQL Server コンピューターの名前を変更する場合も、同様の問題が発生します。</span><span class="sxs-lookup"><span data-stu-id="b6770-122">A similar problem will occur if the SQL Server computer is renamed after BizTalk Server is configured.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="b6770-123">解決策</span><span class="sxs-lookup"><span data-stu-id="b6770-123">Resolution</span></span>  
 <span data-ttu-id="b6770-124">BizTalk Server コンピューターまたは SQL Server コンピューターの名前を変更しないでください。</span><span class="sxs-lookup"><span data-stu-id="b6770-124">Do not rename the BizTalk Server computer or the SQL Server computer.</span></span> <span data-ttu-id="b6770-125">サーバーの名前を変更する必要がある場合は、コンピューターの名前を変更する前に、すべての BizTalk 機能の構成を解除します。</span><span class="sxs-lookup"><span data-stu-id="b6770-125">If a server must be renamed, unconfigure all BizTalk Features before renaming the computer.</span></span> <span data-ttu-id="b6770-126">コンピューターの名前を変更してから、BizTalk Server の機能を再構成してください。</span><span class="sxs-lookup"><span data-stu-id="b6770-126">After renaming the computer, reconfigure BizTalk Server features.</span></span>  
  
## <a name="the-biztalk-server-business-rules-configuration-wizard-fails"></a><span data-ttu-id="b6770-127">BizTalk Server のビジネス ルール構成ウィザードが失敗する</span><span class="sxs-lookup"><span data-stu-id="b6770-127">The BizTalk Server Business Rules Configuration Wizard Fails</span></span>  
  
### <a name="problem"></a><span data-ttu-id="b6770-128">Problem</span><span class="sxs-lookup"><span data-stu-id="b6770-128">Problem</span></span>  
  
- <span data-ttu-id="b6770-129">ビジネス ルール構成ウィザードが "一部のコンポーネントの構成に失敗しました。それらのコンポーネントにはどの設定も適用されませんでした" というエラーで失敗します。</span><span class="sxs-lookup"><span data-stu-id="b6770-129">The Business Rules Configuration Wizard fails with the error “Configuration failed for some components and no settings were applied for those components”.</span></span>  
  
- <span data-ttu-id="b6770-130">BizTalk Server コンピューターにビジネス ルール エンジンが既に正常に構成されている場合、ルール エンジン更新サービスの開始は失敗し、手動で開始することはできません。</span><span class="sxs-lookup"><span data-stu-id="b6770-130">On BizTalk Server computers for which the Business Rules Engine has already been successfully configured, the Rules Engine Update service fails to start and cannot be started manually.</span></span>  
  
  <span data-ttu-id="b6770-131">この問題が発生した場合は、BizTalk Server コンピューターのアプリケーション ログに次のようなエラーが生成されることがあります。</span><span class="sxs-lookup"><span data-stu-id="b6770-131">When this problem occurs, an error similar to the following may be generated in the BizTalk Server computer Application log:</span></span>  
  
```  
Service could not be started. : System.Net.Sockets.SocketException (10061): No connection could be made because the target machine actively refused it ::1:3132  
  
```  
  
### <a name="cause"></a><span data-ttu-id="b6770-132">原因</span><span class="sxs-lookup"><span data-stu-id="b6770-132">Cause</span></span>  
 <span data-ttu-id="b6770-133">マイクロソフト マルウェア対応センターは、SettingsModifier:Win32/PossibleHostsFileHijack からの脅威の可能性に対処するために、更新されたシグネチャ ファイルを公開しました。</span><span class="sxs-lookup"><span data-stu-id="b6770-133">The Microsoft Malware Protection Center released an updated signature file to address a possible threat from SettingsModifier:Win32/PossibleHostsFileHijack.</span></span> <span data-ttu-id="b6770-134">この更新されたシグネチャ ファイルにより、SettingsModifier:Win32/PossibleHostsFileHijack からの脅威を緩和するために、Windows Defender などのソフトウェアでローカル HOSTS ファイルが更新されます。</span><span class="sxs-lookup"><span data-stu-id="b6770-134">This updated signature file can cause Microsoft Malware Detection software such as Windows Defender to update the local HOSTS file to mitigate threats from SettingsModifier:Win32/PossibleHostsFileHijack.</span></span> <span data-ttu-id="b6770-135">これらの変更の結果、BizTalk Server ルール エンジン更新サービスが正常に開始できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="b6770-135">As a result of these changes, the BizTalk Server Rules Engine Update service may fail to start.</span></span>  
  
### <a name="resolution"></a><span data-ttu-id="b6770-136">解決策</span><span class="sxs-lookup"><span data-stu-id="b6770-136">Resolution</span></span>  
 <span data-ttu-id="b6770-137">ローカル HOSTS ファイルを更新して次の行を追加してください。</span><span class="sxs-lookup"><span data-stu-id="b6770-137">Update the local HOSTS file to include the following line:</span></span>  
  
```  
127.0.0.1         localhost  
```  
  
 <span data-ttu-id="b6770-138">HOSTS ファイルは %systemroot%\drivers\etc\ ディレクトリにあります。</span><span class="sxs-lookup"><span data-stu-id="b6770-138">The HOSTS file is located in the %systemroot%\drivers\etc\ directory.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b6770-139">SettingsModifier:Win32 から可能な脅威に対処する Microsoft マルウェア プロテクション センターの署名の更新の詳細については/に移動して、公開しました[ http://go.microsoft.com/fwlink/?LinkId=146221](http://go.microsoft.com/fwlink/?LinkId=146221)します。</span><span class="sxs-lookup"><span data-stu-id="b6770-139">For more information about the Microsoft Malware Protection Center signature update that addresses a possible threat from SettingsModifier:Win32/PossibleHostsFileHijack, go to [http://go.microsoft.com/fwlink/?LinkId=146221](http://go.microsoft.com/fwlink/?LinkId=146221).</span></span>  
  
## <a name="enlistment-of-an-orchestration-fails-if-referenced-assemblies-are-missing-from-the-gacmgmt-db"></a><span data-ttu-id="b6770-140">GAC/Mgmt db に参照アセンブリが見つからない場合、オーケストレーションの参加に失敗する</span><span class="sxs-lookup"><span data-stu-id="b6770-140">Enlistment of an Orchestration Fails if Referenced Assemblies are Missing from the GAC/Mgmt DB</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="b6770-141">問題</span><span class="sxs-lookup"><span data-stu-id="b6770-141">Problem</span></span>  
 <span data-ttu-id="b6770-142">GAC/Mgmt db に参照 (オーケストレーションで参照される C# アセンブリ) が見つからない場合、オーケストレーションの参加に失敗します。</span><span class="sxs-lookup"><span data-stu-id="b6770-142">Enlistment of an orchestration fails if references (C# assemblies which are referenced to orchestrations) are missing from the GAC/Mgmt db.</span></span> <span data-ttu-id="b6770-143">再展開中に、既存の状態に基づいたオーケストレーションの参加が必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="b6770-143">During re-deployment, there may be a need to enlist the orchestration based on its existing state.</span></span> <span data-ttu-id="b6770-144">参照が見つからないと、展開も失敗します。</span><span class="sxs-lookup"><span data-stu-id="b6770-144">If references are missing then the deployment also fails.</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="b6770-145">原因</span><span class="sxs-lookup"><span data-stu-id="b6770-145">Cause</span></span>  
 <span data-ttu-id="b6770-146">GAC/Mgmt db に参照アセンブリが見つかりません。</span><span class="sxs-lookup"><span data-stu-id="b6770-146">Referenced assemblies are missing from GAC/Mgmt db.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="b6770-147">解決策</span><span class="sxs-lookup"><span data-stu-id="b6770-147">Resolution</span></span>  
 <span data-ttu-id="b6770-148">オーケストレーションの参加時に Mgmt db に格納された参照アセンブリにアクセスできるように、参照アセンブリを GAC に追加するか、リソースとして追加します。</span><span class="sxs-lookup"><span data-stu-id="b6770-148">Add the referenced assemblies in GAC or add them as resources, so that they are stored in Mgmt db and are accessible during enlistment of orchestration.</span></span>  

## <a name="community-blog-biztalk-2013-r2-bugs-issues--quirks"></a><span data-ttu-id="b6770-149">コミュニティ ブログ: BizTalk 2013 R2 のバグ、問題、変わった現象</span><span class="sxs-lookup"><span data-stu-id="b6770-149">Community blog: BizTalk 2013 R2 bugs, issues & quirks</span></span>

[<span data-ttu-id="b6770-150">BizTalk Server 2013 R2 の既知のバグ、問題、変わった現象</span><span class="sxs-lookup"><span data-stu-id="b6770-150">BizTalk Server 2013 R2 known bugs, issues, quirks</span></span>](https://cdijkgraaf.wordpress.com/2016/08/12/biztalk-2013-r2-known-bugs-issues-quirks/)
  
## <a name="additional-configuration-topics"></a><span data-ttu-id="b6770-151">構成に関するその他のトピック</span><span class="sxs-lookup"><span data-stu-id="b6770-151">Additional Configuration Topics</span></span>  
  
 [<span data-ttu-id="b6770-152">BizTalk Server の構成</span><span class="sxs-lookup"><span data-stu-id="b6770-152">Configure BizTalk Server</span></span>](../install-and-config-guides/configure-biztalk-server.md)  
  
 [<span data-ttu-id="b6770-153">Azure VM での BizTalk Server の構成</span><span class="sxs-lookup"><span data-stu-id="b6770-153">Configuring BizTalk Server on an Azure VM</span></span>](http://msdn.microsoft.com/library/azure/jj248689.aspx)  
  
  [<span data-ttu-id="b6770-154">BizTalk Server のクラスター構成</span><span class="sxs-lookup"><span data-stu-id="b6770-154">Configure BizTalk Server in a Cluster</span></span>](../install-and-config-guides/configure-biztalk-server-in-a-cluster.md)
  
 [<span data-ttu-id="b6770-155">BizTalk Server の安全な展開</span><span class="sxs-lookup"><span data-stu-id="b6770-155">Securing Your BizTalk Server Deployment</span></span>](../install-and-config-guides/securing-your-biztalk-server-deployment.md)  
  