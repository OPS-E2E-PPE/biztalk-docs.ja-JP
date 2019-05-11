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
ms.openlocfilehash: 040b1921228608deddb3e950613f447d984121c9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65266205"
---
# <a name="known-issues-in-installation-configuration-and-deployment"></a><span data-ttu-id="a9c03-102">インストール、構成、および展開に関する既知の問題</span><span class="sxs-lookup"><span data-stu-id="a9c03-102">Known Issues in Installation, Configuration, and Deployment</span></span>
## <a name="some-biztalk-edias2-artifacts-are-still-active-after-unconfiguring"></a><span data-ttu-id="a9c03-103">構成解除した後、一部の BizTalk edi/as2 アイテムがまだアクティブ</span><span class="sxs-lookup"><span data-stu-id="a9c03-103">Some BizTalk EDI/AS2 Artifacts Are Still Active After Unconfiguring</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="a9c03-104">問題</span><span class="sxs-lookup"><span data-stu-id="a9c03-104">Problem</span></span>  
 <span data-ttu-id="a9c03-105">BizTalk edi/as2 機能を構成解除した後[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、EDI および AS2 処理に関連する一部の BizTalk Server アイテムを BizTalk グループの構成のコンテキストでアクティブにすることができます。</span><span class="sxs-lookup"><span data-stu-id="a9c03-105">After you unconfigure the BizTalk EDI/AS2 feature of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], some BizTalk Server artifacts related to EDI and AS2 processing will still be active in the context of the BizTalk group configuration.</span></span> <span data-ttu-id="a9c03-106">これらの成果物には、EDI および AS2 のパイプラインとバッチ処理オーケストレーションが含まれます。</span><span class="sxs-lookup"><span data-stu-id="a9c03-106">These artifacts will include EDI and AS2 pipelines and the batching orchestration.</span></span> <span data-ttu-id="a9c03-107">その結果、BizTalk edi/as2 機能を構成解除した後でも、基本的な EDI および AS2 処理を実行することができます。</span><span class="sxs-lookup"><span data-stu-id="a9c03-107">As a result, you will still be able to perform basic EDI and AS2 processing even after unconfiguring the BizTalk EDI/AS2 feature.</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="a9c03-108">原因</span><span class="sxs-lookup"><span data-stu-id="a9c03-108">Cause</span></span>  
 <span data-ttu-id="a9c03-109">EDI および AS2 処理に関連付けられているアクティブなポートがあります。</span><span class="sxs-lookup"><span data-stu-id="a9c03-109">There are active ports associated with EDI and AS2 processing.</span></span> <span data-ttu-id="a9c03-110">一部のアイテムは引き続きこれらのポートをアクティブにしたままに機能します。</span><span class="sxs-lookup"><span data-stu-id="a9c03-110">Some artifacts will continue to function while these ports remain active.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="a9c03-111">解決策</span><span class="sxs-lookup"><span data-stu-id="a9c03-111">Resolution</span></span>  
 <span data-ttu-id="a9c03-112">すべての edi/as2 アイテムを無効にするを無効にし、停止、または EDI および AS2 処理に関連付けられているポートを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a9c03-112">To disable all EDI/AS2 artifacts, you should disable, stop, or delete the ports associated with EDI and AS2 processing.</span></span>  
  
## <a name="if-the-biztalk-server-computer-or-sql-server-computer-is-renamed-after-biztalk-server-configuration-the-configuration-wizard-will-fail"></a><span data-ttu-id="a9c03-113">BizTalk Server の構成後、BizTalk Server コンピューターまたは SQL Server コンピューターの名前が変更、構成ウィザードが失敗します。</span><span class="sxs-lookup"><span data-stu-id="a9c03-113">If the BizTalk Server Computer or SQL Server Computer Is Renamed After BizTalk Server Configuration, the Configuration Wizard Will Fail</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="a9c03-114">問題</span><span class="sxs-lookup"><span data-stu-id="a9c03-114">Problem</span></span>  
 <span data-ttu-id="a9c03-115">この問題は、いくつかの方法で問題を発生可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a9c03-115">This problem may manifest itself in several ways:</span></span>  
  
-   <span data-ttu-id="a9c03-116">BizTalk Server の構成が [概要] ページを正しく読み込むが、画面に機能を構成しようとしています。 機能のオプションは表示されません。</span><span class="sxs-lookup"><span data-stu-id="a9c03-116">The BizTalk Server Configuration will load the Overview page correctly, but when attempting to configure a feature the feature options do not display on the screen.</span></span>  
  
-   <span data-ttu-id="a9c03-117">構成ウィザードは、SQL Server に接続できません。</span><span class="sxs-lookup"><span data-stu-id="a9c03-117">The configuration wizard cannot connect to the SQL Server.</span></span>  
  
-   <span data-ttu-id="a9c03-118">すべてではなく、一部の機能の構成を解除するすべての構成を解除しようとしています。</span><span class="sxs-lookup"><span data-stu-id="a9c03-118">Attempting to Unconfigure All unconfigures some features, but not all.</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="a9c03-119">原因</span><span class="sxs-lookup"><span data-stu-id="a9c03-119">Cause</span></span>  
 <span data-ttu-id="a9c03-120">BizTalk Server の構成では、コンピューターのネットワーク名を格納します。</span><span class="sxs-lookup"><span data-stu-id="a9c03-120">The BizTalk Server configuration stores the computer network name.</span></span> <span data-ttu-id="a9c03-121">コンピューターの名前変更は、BizTalk Server の構成と構成ウィザードは、BizTalk Server を特定できなくなります。</span><span class="sxs-lookup"><span data-stu-id="a9c03-121">When the computer is renamed the BizTalk Server Configuration and configuration wizard cannot locate the BizTalk Server.</span></span> <span data-ttu-id="a9c03-122">SQL Server コンピューターの名前が変更された後、BizTalk Server が構成されている場合、同様の問題が発生します。</span><span class="sxs-lookup"><span data-stu-id="a9c03-122">A similar problem will occur if the SQL Server computer is renamed after BizTalk Server is configured.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="a9c03-123">解決策</span><span class="sxs-lookup"><span data-stu-id="a9c03-123">Resolution</span></span>  
 <span data-ttu-id="a9c03-124">BizTalk Server コンピューター、または SQL Server コンピューターに名前を変更できません。</span><span class="sxs-lookup"><span data-stu-id="a9c03-124">Do not rename the BizTalk Server computer or the SQL Server computer.</span></span> <span data-ttu-id="a9c03-125">場合は、サーバーの名前を変更する必要があります、コンピューターの名前を変更する前にすべての BizTalk 機能の構成を解除します。</span><span class="sxs-lookup"><span data-stu-id="a9c03-125">If a server must be renamed, unconfigure all BizTalk Features before renaming the computer.</span></span> <span data-ttu-id="a9c03-126">コンピューターの名前を変更するには後、は、BizTalk Server の機能を再構成します。</span><span class="sxs-lookup"><span data-stu-id="a9c03-126">After renaming the computer, reconfigure BizTalk Server features.</span></span>  
  
## <a name="the-biztalk-server-business-rules-configuration-wizard-fails"></a><span data-ttu-id="a9c03-127">BizTalk Server ビジネス ルール構成ウィザードが失敗しました。</span><span class="sxs-lookup"><span data-stu-id="a9c03-127">The BizTalk Server Business Rules Configuration Wizard Fails</span></span>  
  
### <a name="problem"></a><span data-ttu-id="a9c03-128">問題</span><span class="sxs-lookup"><span data-stu-id="a9c03-128">Problem</span></span>  
  
- <span data-ttu-id="a9c03-129">ビジネス ルールの構成ウィザードは、「一部のコンポーネントの構成に失敗しましたし、それらのコンポーネントの設定は適用されませんでした」エラーで失敗します。</span><span class="sxs-lookup"><span data-stu-id="a9c03-129">The Business Rules Configuration Wizard fails with the error “Configuration failed for some components and no settings were applied for those components”.</span></span>  
  
- <span data-ttu-id="a9c03-130">対象のビジネス ルール エンジンが既に正常に構成されて、BizTalk サーバー コンピューターには、ルール エンジン更新サービスは開始に失敗し、手動で開始することはできません。</span><span class="sxs-lookup"><span data-stu-id="a9c03-130">On BizTalk Server computers for which the Business Rules Engine has already been successfully configured, the Rules Engine Update service fails to start and cannot be started manually.</span></span>  
  
  <span data-ttu-id="a9c03-131">この問題が発生したときに、BizTalk Server コンピューターのアプリケーション ログには、次のようなエラーを生成可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a9c03-131">When this problem occurs, an error similar to the following may be generated in the BizTalk Server computer Application log:</span></span>  
  
```  
Service could not be started. : System.Net.Sockets.SocketException (10061): No connection could be made because the target machine actively refused it ::1:3132  
  
```  
  
### <a name="cause"></a><span data-ttu-id="a9c03-132">原因</span><span class="sxs-lookup"><span data-stu-id="a9c03-132">Cause</span></span>  
 <span data-ttu-id="a9c03-133">Microsoft マルウェア プロテクション センター SettingsModifier:Win32 から潜在的な脅威に対処するための更新されたシグネチャ ファイルをリリースする/公開しました。</span><span class="sxs-lookup"><span data-stu-id="a9c03-133">The Microsoft Malware Protection Center released an updated signature file to address a possible threat from SettingsModifier:Win32/PossibleHostsFileHijack.</span></span> <span data-ttu-id="a9c03-134">この更新されたシグネチャ ファイル SettingsModifier:Win32 からの脅威を軽減するためにローカルの HOSTS ファイルを更新する Windows Defender などの Microsoft マルウェア検出ソフトウェアが発生することができます/公開しました。</span><span class="sxs-lookup"><span data-stu-id="a9c03-134">This updated signature file can cause Microsoft Malware Detection software such as Windows Defender to update the local HOSTS file to mitigate threats from SettingsModifier:Win32/PossibleHostsFileHijack.</span></span> <span data-ttu-id="a9c03-135">これらの変更の結果として、BizTalk Server ルール エンジン更新サービスを開始する失敗します。</span><span class="sxs-lookup"><span data-stu-id="a9c03-135">As a result of these changes, the BizTalk Server Rules Engine Update service may fail to start.</span></span>  
  
### <a name="resolution"></a><span data-ttu-id="a9c03-136">解決策</span><span class="sxs-lookup"><span data-stu-id="a9c03-136">Resolution</span></span>  
 <span data-ttu-id="a9c03-137">ローカルの HOSTS ファイルに含める、次の行を更新します。</span><span class="sxs-lookup"><span data-stu-id="a9c03-137">Update the local HOSTS file to include the following line:</span></span>  
  
```  
127.0.0.1         localhost  
```  
  
 <span data-ttu-id="a9c03-138">HOSTS ファイルは %systemroot%\drivers\etc\ ディレクトリ内にあります。</span><span class="sxs-lookup"><span data-stu-id="a9c03-138">The HOSTS file is located in the %systemroot%\drivers\etc\ directory.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a9c03-139">SettingsModifier:Win32 から可能な脅威に対処する Microsoft マルウェア プロテクション センターの署名の更新の詳細については/に移動して、公開しました[ http://go.microsoft.com/fwlink/?LinkId=146221](http://go.microsoft.com/fwlink/?LinkId=146221)します。</span><span class="sxs-lookup"><span data-stu-id="a9c03-139">For more information about the Microsoft Malware Protection Center signature update that addresses a possible threat from SettingsModifier:Win32/PossibleHostsFileHijack, go to [http://go.microsoft.com/fwlink/?LinkId=146221](http://go.microsoft.com/fwlink/?LinkId=146221).</span></span>  
  
## <a name="enlistment-of-an-orchestration-fails-if-referenced-assemblies-are-missing-from-the-gacmgmt-db"></a><span data-ttu-id="a9c03-140">オーケストレーションが失敗した場合、参照アセンブリが見つからない Gac/mgmt DB からの参加</span><span class="sxs-lookup"><span data-stu-id="a9c03-140">Enlistment of an Orchestration Fails if Referenced Assemblies are Missing from the GAC/Mgmt DB</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="a9c03-141">問題</span><span class="sxs-lookup"><span data-stu-id="a9c03-141">Problem</span></span>  
 <span data-ttu-id="a9c03-142">場合、オーケストレーションの参加が失敗した参照 (C#オーケストレーションに参照されるアセンブリ) Gac/mgmt db にはないです。</span><span class="sxs-lookup"><span data-stu-id="a9c03-142">Enlistment of an orchestration fails if references (C# assemblies which are referenced to orchestrations) are missing from the GAC/Mgmt db.</span></span> <span data-ttu-id="a9c03-143">再展開時に、既存の状態に基づいてオーケストレーションを参加させる必要があります。</span><span class="sxs-lookup"><span data-stu-id="a9c03-143">During re-deployment, there may be a need to enlist the orchestration based on its existing state.</span></span> <span data-ttu-id="a9c03-144">参照が不足している場合、展開も失敗します。</span><span class="sxs-lookup"><span data-stu-id="a9c03-144">If references are missing then the deployment also fails.</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="a9c03-145">原因</span><span class="sxs-lookup"><span data-stu-id="a9c03-145">Cause</span></span>  
 <span data-ttu-id="a9c03-146">Gac/mgmt db に参照されたアセンブリが表示されません。</span><span class="sxs-lookup"><span data-stu-id="a9c03-146">Referenced assemblies are missing from GAC/Mgmt db.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="a9c03-147">解決策</span><span class="sxs-lookup"><span data-stu-id="a9c03-147">Resolution</span></span>  
 <span data-ttu-id="a9c03-148">参照されたアセンブリを GAC に追加または Mgmt db に格納されますしたり、オーケストレーションの参加中にアクセスできるように、リソースとして追加します。</span><span class="sxs-lookup"><span data-stu-id="a9c03-148">Add the referenced assemblies in GAC or add them as resources, so that they are stored in Mgmt db and are accessible during enlistment of orchestration.</span></span>  

## <a name="community-blog-biztalk-2013-r2-bugs-issues-quirks"></a><span data-ttu-id="a9c03-149">コミュニティのブログ:BizTalk 2013 R2 のバグ、問題、変わった現象</span><span class="sxs-lookup"><span data-stu-id="a9c03-149">Community blog: BizTalk 2013 R2 bugs, issues & quirks</span></span>

[<span data-ttu-id="a9c03-150">BizTalk Server 2013 R2 の既知のバグ、問題、変わった現象</span><span class="sxs-lookup"><span data-stu-id="a9c03-150">BizTalk Server 2013 R2 known bugs, issues, quirks</span></span>](https://cdijkgraaf.wordpress.com/2016/08/12/biztalk-2013-r2-known-bugs-issues-quirks/)
  
## <a name="additional-configuration-topics"></a><span data-ttu-id="a9c03-151">構成に関するその他のトピック</span><span class="sxs-lookup"><span data-stu-id="a9c03-151">Additional Configuration Topics</span></span>  
  
 [<span data-ttu-id="a9c03-152">BizTalk Server の構成</span><span class="sxs-lookup"><span data-stu-id="a9c03-152">Configure BizTalk Server</span></span>](../install-and-config-guides/configure-biztalk-server.md)  
  
 [<span data-ttu-id="a9c03-153">Azure VM での BizTalk Server の構成</span><span class="sxs-lookup"><span data-stu-id="a9c03-153">Configuring BizTalk Server on an Azure VM</span></span>](http://msdn.microsoft.com/library/azure/jj248689.aspx)  
  
  [<span data-ttu-id="a9c03-154">BizTalk Server のクラスター構成</span><span class="sxs-lookup"><span data-stu-id="a9c03-154">Configure BizTalk Server in a Cluster</span></span>](../install-and-config-guides/configure-biztalk-server-in-a-cluster.md)
  
 [<span data-ttu-id="a9c03-155">BizTalk Server の展開をセキュリティで保護します。</span><span class="sxs-lookup"><span data-stu-id="a9c03-155">Securing Your BizTalk Server Deployment</span></span>](../install-and-config-guides/securing-your-biztalk-server-deployment.md)  
  