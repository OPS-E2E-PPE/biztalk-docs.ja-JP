---
title: "BizTalk Server のパフォーマンスに関するトラブルシューティング |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: dbf21fb9-1ae1-48b5-a65a-e96839b23945
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 21003c4d3565158945e91371fa760cf97692b472
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="troubleshooting-biztalk-server-performance"></a><span data-ttu-id="a49c5-102">BizTalk Server のパフォーマンスに関するトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="a49c5-102">Troubleshooting BizTalk Server Performance</span></span>
<span data-ttu-id="a49c5-103">ここでは、BizTalk メッセージング エンジンに関連するパフォーマンスの問題を診断および解決するための一般的なガイドラインを示します。</span><span class="sxs-lookup"><span data-stu-id="a49c5-103">This section contains general guidelines for diagnosing and resolving performance problems related to the BizTalk Messaging Engine.</span></span>  
  
## <a name="estimating-document-processing-requirements"></a><span data-ttu-id="a49c5-104">ドキュメント処理要件の見積もり</span><span class="sxs-lookup"><span data-stu-id="a49c5-104">Estimating Document Processing Requirements</span></span>  
 <span data-ttu-id="a49c5-105">ソリューションを実稼動環境に展開する前に、メッセージング エンジンのパフォーマンスを測定するための計画とテストを行います。</span><span class="sxs-lookup"><span data-stu-id="a49c5-105">Plan and test to determine your Messaging Engine performance needs before deploying your solution into a production environment.</span></span> <span data-ttu-id="a49c5-106">これは、BizTalk Server 環境および SQL Server 環境の適切な構築に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="a49c5-106">This will help you build out your BizTalk Server and SQL Server environments appropriately.</span></span>  
  
1.  <span data-ttu-id="a49c5-107">フォールト トレランスまたはバックアップと復旧に伴うオーバーヘッドについて考慮します。</span><span class="sxs-lookup"><span data-stu-id="a49c5-107">Plan for overhead associated with any fault tolerance or backup and recovery needs</span></span>  
  
    -   <span data-ttu-id="a49c5-108">SQL Server のディスクを RAID アレイで構成するか。</span><span class="sxs-lookup"><span data-stu-id="a49c5-108">Will the SQL Server disks be configured as RAID arrays?</span></span>  
  
    -   <span data-ttu-id="a49c5-109">Windows クラスターを BizTalk ホスト、SQL Server、またはエンタープライズ シングル サインオンに使用するか。</span><span class="sxs-lookup"><span data-stu-id="a49c5-109">Will Windows Clustering be used for BizTalk Hosts, SQL Server, or Enterprise Single Sign-On?</span></span> <span data-ttu-id="a49c5-110">詳細については、次を参照してください。[高可用性の計画](../core/planning-for-high-availability3.md)です。</span><span class="sxs-lookup"><span data-stu-id="a49c5-110">For more information see [Planning for High Availability](../core/planning-for-high-availability3.md).</span></span>  
  
    -   <span data-ttu-id="a49c5-111">ネットワーク負荷分散を使用するか。</span><span class="sxs-lookup"><span data-stu-id="a49c5-111">Will Network Load Balancing be used?</span></span>  
  
    -   <span data-ttu-id="a49c5-112">環境のバックアップと復旧の要件は何か。</span><span class="sxs-lookup"><span data-stu-id="a49c5-112">What are the backup and recovery requirements for the environment?</span></span> <span data-ttu-id="a49c5-113">詳細については、次を参照してください。[をバックアップおよび BizTalk Server データベースの復元](../core/backing-up-and-restoring-biztalk-server-databases.md)です。</span><span class="sxs-lookup"><span data-stu-id="a49c5-113">For more information, see [Backing Up and Restoring BizTalk Server Databases](../core/backing-up-and-restoring-biztalk-server-databases.md).</span></span>  
  
2.  <span data-ttu-id="a49c5-114">」のガイドラインに従って[継続的なパフォーマンスの計画](../core/planning-for-sustained-performance.md)計画、テスト、および BizTalk Server と SQL Server 環境を拡張します。</span><span class="sxs-lookup"><span data-stu-id="a49c5-114">Follow the guidelines in [Planning for Sustained Performance](../core/planning-for-sustained-performance.md) to plan, test, and scale your BizTalk Server and SQL Server environment.</span></span>  
  
3.  <span data-ttu-id="a49c5-115">」のガイドラインに従って[パフォーマンス特性の追跡](../core/tracking-performance-characteristics.md)ドキュメント追跡の要件に伴うオーバーヘッドについて計画します。</span><span class="sxs-lookup"><span data-stu-id="a49c5-115">Follow the guidelines in [Tracking Performance Characteristics](../core/tracking-performance-characteristics.md) to plan for overhead associated with document tracking requirements.</span></span>  
  
## <a name="optimizing-an-existing-biztalk-server-environment"></a><span data-ttu-id="a49c5-116">既存の BizTalk Server 環境の最適化</span><span class="sxs-lookup"><span data-stu-id="a49c5-116">Optimizing an Existing BizTalk Server Environment</span></span>  
 <span data-ttu-id="a49c5-117">既存の BizTalk Server 環境を最適化するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="a49c5-117">Follow these steps to optimize an existing BizTalk Server environment:</span></span>  
  
1.  <span data-ttu-id="a49c5-118">」のガイドラインに従って[パフォーマンスのボトルネックを識別する](../core/identifying-performance-bottlenecks.md)に BizTalk Server 環境内のボトルネックを特定します。</span><span class="sxs-lookup"><span data-stu-id="a49c5-118">Follow the guidelines in [Identifying Performance Bottlenecks](../core/identifying-performance-bottlenecks.md) to pinpoint possible bottlenecks in your BizTalk Server environment.</span></span>  
  
2.  <span data-ttu-id="a49c5-119">」のガイドラインに従って[を最適化するリソース使用状況を通じてホスト制限](../core/optimizing-resource-usage-through-host-throttling.md)BizTalk Server 環境のドキュメント スループットを最大化します。</span><span class="sxs-lookup"><span data-stu-id="a49c5-119">Follow the guidelines in [Optimizing Resource Usage Through Host Throttling](../core/optimizing-resource-usage-through-host-throttling.md) to maximize document throughput for the BizTalk Server environment.</span></span>  
  
3.  <span data-ttu-id="a49c5-120">記載されているパラメーターの変更を検討[構成パラメーターに影響を与えるアダプター パフォーマンス](../core/configuration-parameters-that-affect-adapter-performance.md)を特定のシナリオにおけるアダプターのパフォーマンスを最大化します。</span><span class="sxs-lookup"><span data-stu-id="a49c5-120">Consider modifying the parameters documented in [Configuration Parameters that Affect Adapter Performance](../core/configuration-parameters-that-affect-adapter-performance.md) to maximize adapter performance in certain scenarios.</span></span>  
  
4.  <span data-ttu-id="a49c5-121">」のガイドラインに従って[どのように BizTalk Server プロセス サイズの大きいメッセージ](../core/how-biztalk-server-processes-large-messages.md)(100 MB を超える) のサイズの大きいメッセージを処理するときに、メッセージング エンジンのパフォーマンスを最適化するためにします。</span><span class="sxs-lookup"><span data-stu-id="a49c5-121">Follow the guidelines in [How BizTalk Server Processes Large Messages](../core/how-biztalk-server-processes-large-messages.md) to optimize Messaging Engine performance when processing Large Messages (more than 100 MB).</span></span>  
  
5.  <span data-ttu-id="a49c5-122">送信アダプター、受信アダプター、およびオーケストレーションごとに別々のホストとホスト インスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="a49c5-122">Create separate hosts and host instances for send adapters, receive adapters, and orchestrations.</span></span> <span data-ttu-id="a49c5-123">これにより、各アダプターが個別のホスト インスタンスで実行され、あるアダプターが別のアダプターに悪影響を与えることがなくなります。</span><span class="sxs-lookup"><span data-stu-id="a49c5-123">This will give each adapter a separate host instance to run in and will ensure that one adapter does not adversely affect another.</span></span> <span data-ttu-id="a49c5-124">ホストの制限設定はホスト レベルで構成できるので、処理ロジックを異なるホストへ分離することによって、各ホストの処理要件に基づいて制限設定を構成できるようにもなります。</span><span class="sxs-lookup"><span data-stu-id="a49c5-124">Since host throttling settings are configurable at the host level, the separation of processing logic into different hosts will also permit you to configure throttling settings based upon the processing requirements of each host.</span></span>  
  
## <a name="diagnosing-performance-problems-in-an-existing-biztalk-server-environment"></a><span data-ttu-id="a49c5-125">既存の BizTalk Server 環境におけるパフォーマンスの問題の診断</span><span class="sxs-lookup"><span data-stu-id="a49c5-125">Diagnosing Performance Problems in an Existing BizTalk Server Environment</span></span>  
 <span data-ttu-id="a49c5-126">通常、パフォーマンスの問題は、BizTalk Server 環境の次のコンポーネントの 1 つに絞り込むことができます。</span><span class="sxs-lookup"><span data-stu-id="a49c5-126">Typically a performance problem can be narrowed down to one of the following components of a BizTalk Server environment:</span></span>  
  
-   <span data-ttu-id="a49c5-127">受信アダプターまたはそのアダプターにドキュメントを送信しているシステム。</span><span class="sxs-lookup"><span data-stu-id="a49c5-127">A receive adapter or the system that the adapter is receiving documents from.</span></span> <span data-ttu-id="a49c5-128">たとえば、最適ではないレートでドキュメントが HTTP アダプターで受信されている場合、問題は HTTP 受信アダプター、または HTTP アダプターに送信しているクライアントにあります。</span><span class="sxs-lookup"><span data-stu-id="a49c5-128">For example if documents are being received by the HTTP adapter at a suboptimal rate then the problem may be with the HTTP receive adapter or with the client that is posting to the HTTP adapter.</span></span>  
  
-   <span data-ttu-id="a49c5-129">オーケストレーション サービス インスタンス。</span><span class="sxs-lookup"><span data-stu-id="a49c5-129">An orchestration service instance.</span></span>  
  
-   <span data-ttu-id="a49c5-130">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] データベースをホストしている Microsoft SQL Server のパフォーマンス。</span><span class="sxs-lookup"><span data-stu-id="a49c5-130">Performance of the Microsoft SQL server that houses the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases.</span></span>  
  
-   <span data-ttu-id="a49c5-131">送信アダプターまたはそのアダプターからドキュメントを受信しているシステム。</span><span class="sxs-lookup"><span data-stu-id="a49c5-131">A send adapter or the system that the adapter is sending documents to.</span></span> <span data-ttu-id="a49c5-132">たとえば、最適ではないレートでドキュメントが SQL アダプターで送信されている場合、問題は SQL 送信アダプター、または SQL アダプターが更新している [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] を実行しているコンピューターにあります。</span><span class="sxs-lookup"><span data-stu-id="a49c5-132">For example if documents are being sent by the SQL adapter at a suboptimal rate then the problem may be with the SQL send adapter or with the computer running [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] that the SQL adapter is updating.</span></span>  
  
 <span data-ttu-id="a49c5-133">次のガイドラインは、パフォーマンスが低下している [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 環境のコンポーネントの特定に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="a49c5-133">Use the following guidelines to help identify the components of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment that are performing poorly:</span></span>  
  
-   <span data-ttu-id="a49c5-134">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] または [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] イベント ビューアーで生成された警告やエラーをすべてキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="a49c5-134">Capture any warnings or errors generated in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] or [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Event Viewer.</span></span>  
  
-   <span data-ttu-id="a49c5-135">手順に従います[パフォーマンスのボトルネックを識別する](../core/identifying-performance-bottlenecks.md)パフォーマンスのボトルネックの特定に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="a49c5-135">Follow the steps in [Identifying Performance Bottlenecks](../core/identifying-performance-bottlenecks.md) to help identify performance bottlenecks.</span></span>  
  
 <span data-ttu-id="a49c5-136">パフォーマンスの低いコンポーネントを特定したら、以下の該当するガイドラインに従って、問題を解決します。</span><span class="sxs-lookup"><span data-stu-id="a49c5-136">Once the poorly performing component has been identified, follow the appropriate guidelines to help resolve the issue:</span></span>  
  
 <span data-ttu-id="a49c5-137">**送信および受信アダプターに関連するパフォーマンスの問題を解決するためのガイドライン**</span><span class="sxs-lookup"><span data-stu-id="a49c5-137">**Guidelines for resolving performance problems related to send and receive adapters**</span></span>  
  
-   <span data-ttu-id="a49c5-138">参照してください[BizTalk Server アダプターのトラブルシューティング](../core/troubleshooting-biztalk-server-adapters.md)に関する問題のトラブルシューティングに一般的な情報について[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アダプター。</span><span class="sxs-lookup"><span data-stu-id="a49c5-138">See [Troubleshooting BizTalk Server Adapters](../core/troubleshooting-biztalk-server-adapters.md) for general information to troubleshoot problems with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] adapters.</span></span> <span data-ttu-id="a49c5-139">このセクションには、特定のアダプターのログ記録の設定方法についての情報や、ネットワークの問題、MSDTC に関する問題、レジストリに関する問題、ファイル システムに関する問題、および IIS に関する問題の診断に使用できる情報など、一般的なトラブルシューティング情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="a49c5-139">This section contains general troubleshooting information including information about how to set up logging for certain adapters and information that can be used diagnose network problems, problems with MSDTC, problems with the registry, problems with the file system, and problems with IIS.</span></span>  
  
-   <span data-ttu-id="a49c5-140">該当セクションを参照してください[BizTalk Server の依存関係のトラブルシューティング](../core/troubleshooting-biztalk-server-dependencies.md)MSDTC、証明書、エンタープライズ シングル サインオン、に関する問題のトラブルシューティングに一般的な情報について、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="a49c5-140">See the appropriate section of [Troubleshooting BizTalk Server Dependencies](../core/troubleshooting-biztalk-server-dependencies.md) for general information to troubleshoot problems with MSDTC, Certificates, Enterprise Single Sign-On, and [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)].</span></span>  
  
 <span data-ttu-id="a49c5-141">**オーケストレーションに関連するパフォーマンスの問題を解決するためのガイドライン**</span><span class="sxs-lookup"><span data-stu-id="a49c5-141">**Guidelines for resolving performance problems related to orchestrations**</span></span>  
  
-   <span data-ttu-id="a49c5-142">記載されている、BTSNTSvc.exe.config ファイルの適切なセクションを変更[オーケストレーション エンジンの構成](../core/orchestration-engine-configuration.md)です。</span><span class="sxs-lookup"><span data-stu-id="a49c5-142">Modify the appropriate sections of the BTSNTSvc.exe.config file documented in [Orchestration Engine Configuration](../core/orchestration-engine-configuration.md).</span></span>  
  
 <span data-ttu-id="a49c5-143">**SQL Server に関連するパフォーマンスの問題を解決するためのガイドライン**</span><span class="sxs-lookup"><span data-stu-id="a49c5-143">**Guidelines for resolving performance problems related to SQL Server**</span></span>  
  
-   <span data-ttu-id="a49c5-144">SQL Server Profiler を使用すると、SQL Server に送信される Transact-SQL ステートメントや、これらのステートメントで返される SQL Server の結果セットを取得できます。</span><span class="sxs-lookup"><span data-stu-id="a49c5-144">SQL Server Profiler can be used to capture Transact-SQL statements that are sent to SQL Server and the SQL Server result sets from these statements.</span></span> <span data-ttu-id="a49c5-145">BizTalk Server は SQL Server と密接に連携しているので、SQL Server Profile のトレースを分析することで、SQL Server データベースに対する読み取りまたは書き込み時に BizTalk Server で発生する問題を分析するのに役立てることができます。</span><span class="sxs-lookup"><span data-stu-id="a49c5-145">Since BizTalk Server is tightly integrated with SQL Server, the analysis of a SQL Server Profile trace can be a useful tool for analyzing problems that may occur in BizTalk Server when reading from and writing to SQL Server databases.</span></span> <span data-ttu-id="a49c5-146">SQL Server Profiler を使用する方法の詳細については、SQL Server のマニュアルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a49c5-146">For information about how to use SQL Server Profiler see the SQL Server documentation.</span></span>  
  
-   <span data-ttu-id="a49c5-147">SQL Server データベースに対して直接 SQL ステートメントを実行する SQL Server クエリ エディターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="a49c5-147">The SQL Server Query Editor can be used to execute SQL statements directly against SQL Server databases.</span></span> <span data-ttu-id="a49c5-148">この機能は、BizTalk Server データベースに対してクエリを実行するときや、特定のシナリオにおいて BizTalk Server データベースを更新するときに役立つ場合があります。</span><span class="sxs-lookup"><span data-stu-id="a49c5-148">This functionality may be useful for querying the BizTalk Server databases or for updating the BizTalk Server databases in certain scenarios.</span></span> <span data-ttu-id="a49c5-149">クエリ エディターの詳細については、SQL Server のマニュアルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a49c5-149">For more information about Query Editor see the SQL Server documentation.</span></span>  
  
-   <span data-ttu-id="a49c5-150">レビュー [SQL Server のトラブルシューティング](../core/troubleshooting-sql-server.md)の詳細。</span><span class="sxs-lookup"><span data-stu-id="a49c5-150">Review [Troubleshooting SQL Server](../core/troubleshooting-sql-server.md) for additional information.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a49c5-151">参照</span><span class="sxs-lookup"><span data-stu-id="a49c5-151">See Also</span></span>  
 [<span data-ttu-id="a49c5-152">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="a49c5-152">Troubleshooting</span></span>](../core/troubleshooting.md)