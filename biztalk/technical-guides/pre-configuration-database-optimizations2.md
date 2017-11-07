---
title: "事前構成データベース Optimizations2 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8c525c3a-249c-4694-b287-a8c35a6aa524
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2f863ae780dd99a7f0aa7d9acc3884f860686c86
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2017
---
# <a name="pre-configuration-database-optimizations"></a><span data-ttu-id="6ebc5-102">事前構成データベースの最適化</span><span class="sxs-lookup"><span data-stu-id="6ebc5-102">Pre-Configuration Database Optimizations</span></span>
<span data-ttu-id="6ebc5-103">SQL Server が BizTalk Server 環境で再生される重要な役割、ためことが最も重要 SQL Server では、パフォーマンスを最適に構成されているチューニングできることです。</span><span class="sxs-lookup"><span data-stu-id="6ebc5-103">Because of the critical role that SQL Server plays in any BizTalk Server environment, it is of paramount importance that SQL Server be configured/tuned for optimal performance.</span></span> <span data-ttu-id="6ebc5-104">SQL Server が正しく実行するチューニングされなかった場合は、BizTalk Server で使用するデータベースがボトルネックになり、BizTalk Server 環境の全体的なパフォーマンスが低下します。</span><span class="sxs-lookup"><span data-stu-id="6ebc5-104">If SQL Server is not tuned to perform well, then the databases used by BizTalk Server will become a bottleneck and the overall performance of the BizTalk Server environment will suffer.</span></span> <span data-ttu-id="6ebc5-105">このトピックでは、BizTalk Server をインストールして、BizTalk Server データベースを構成する前に従う必要があります複数の SQL Server パフォーマンス最適化機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="6ebc5-105">This topic describes several SQL Server performance optimizations that should be followed before installing BizTalk Server and configuring the BizTalk Server databases.</span></span>  
  
## <a name="set-ntfs-file-allocation-unit"></a><span data-ttu-id="6ebc5-106">NTFS ファイル アロケーション ユニットを設定します。</span><span class="sxs-lookup"><span data-stu-id="6ebc5-106">Set NTFS File Allocation Unit</span></span>  
 <span data-ttu-id="6ebc5-107">SQL Server では、そのデータを格納する**エクステント**、物理的に連続する 8 つの 8 K ページ、または 64 KB のコレクションであります。</span><span class="sxs-lookup"><span data-stu-id="6ebc5-107">SQL Server stores its data in **Extents**, which are collections of eight physically contiguous 8K pages, or 64 KB.</span></span> <span data-ttu-id="6ebc5-108">そのため、ディスクのパフォーマンスを最適化するために、NTFS アロケーション ユニット サイズ 64 KB をに従って設定、「ディスク構成のベスト プラクティス」で[デプロイメント前 I/O のベスト プラクティス](https://msdn.microsoft.com/library/cc966412.aspx)です。</span><span class="sxs-lookup"><span data-stu-id="6ebc5-108">Therefore, to optimize disk performance, set the NTFS Allocation Unit size to 64KB as described in the “Disk Configuration Best Practices” at  [Predeployment I/O Best Practices](https://msdn.microsoft.com/library/cc966412.aspx).</span></span>  
  
## <a name="considerations-for-the-version-and-edition-of-sql-server"></a><span data-ttu-id="6ebc5-109">バージョンおよびエディションの SQL Server に関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="6ebc5-109">Considerations for the version and edition of SQL Server</span></span>  
 <span data-ttu-id="6ebc5-110">さまざまなバージョンおよびエディションの[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]のパフォーマンスに影響を与えるさまざまな機能を提供、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境。</span><span class="sxs-lookup"><span data-stu-id="6ebc5-110">Various versions and editions of [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] provide different features that can affect the performance of your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment.</span></span> <span data-ttu-id="6ebc5-111">などの状況で負荷の高いの 32 ビット バージョンで利用可能なデータベース ロック数[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]過ぎる可能性のある、これは、BizTalk ソリューションのパフォーマンスを低下させます。</span><span class="sxs-lookup"><span data-stu-id="6ebc5-111">For example, under high-load conditions, the number of database locks that are available for the 32-bit version of [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] might be exceeded, which is detrimental to the performance of the BizTalk solution.</span></span> <span data-ttu-id="6ebc5-112">テスト環境でロックの範囲外"エラーが発生した場合、64 ビット バージョンの SQL Server にメッセージ ボックス データベースを格納していることを検討してください。</span><span class="sxs-lookup"><span data-stu-id="6ebc5-112">Consider housing your MessageBox database on a 64-bit version of SQL Server if you are experiencing "out of lock" errors in your test environment.</span></span> <span data-ttu-id="6ebc5-113">64 ビット バージョンの SQL Server では、使用できるロックの数が大幅に増えます。</span><span class="sxs-lookup"><span data-stu-id="6ebc5-113">The number of available locks is significantly higher on the 64-bit version of SQL Server.</span></span>  
  
 <span data-ttu-id="6ebc5-114">BizTalk 環境に必要なデータベース エンジンの機能を決定する場合は、次の表を検討してください。</span><span class="sxs-lookup"><span data-stu-id="6ebc5-114">Consider the following table when deciding on the database engine features that you will need for your BizTalk environment.</span></span> <span data-ttu-id="6ebc5-115">大規模なクラスタ リングが必要なエンタープライズ レベルのソリューションをサポート、BizTalk Server のログ配布のサポート、または Analysis Services がサポートしてホストする SQL Server Enterprise Edition が必要があります、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]データベース。</span><span class="sxs-lookup"><span data-stu-id="6ebc5-115">For large scale, enterprise-level solutions that require clustering support, BizTalk Server log shipping support, or Analysis Services support, then you need SQL Server Enterprise Edition to host the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] databases.</span></span>   

 <span data-ttu-id="6ebc5-116">SQL Server のエディションでサポートされる機能の完全な一覧を参照してください。 [SQL Server のエディションとサポートされる機能](https://docs.microsoft.com/sql/sql-server/editions-and-components-of-sql-server-2016)します。</span><span class="sxs-lookup"><span data-stu-id="6ebc5-116">For a complete list of the features supported by the SQL Server editions, see [SQL Server Editions and supported features](https://docs.microsoft.com/sql/sql-server/editions-and-components-of-sql-server-2016).</span></span>
  
## <a name="database-planning-considerations"></a><span data-ttu-id="6ebc5-117">データベースの計画に関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="6ebc5-117">Database planning considerations</span></span>  
 <span data-ttu-id="6ebc5-118">(たとえば、高速な SAN ディスクまたは高速の SCSI ディスクなど) の高速記憶域上にある SQL Server データベースをホストすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6ebc5-118">We recommend that you host your SQL Server databases on fast storage (for example, fast SAN disks or fast SCSI disks).</span></span> <span data-ttu-id="6ebc5-119">RAID 5 ではなく RAID 10 (1 + 0) は、raid 5 は、書き込みに遅いのでお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6ebc5-119">We recommend RAID 10 (1+0) instead of RAID 5 since raid 5 is slower at writing.</span></span> <span data-ttu-id="6ebc5-120">新しい SAN ディスクに非常に大きなメモリ キャッシュ、があるは、このような場合、raid 選択重要ではないためです。</span><span class="sxs-lookup"><span data-stu-id="6ebc5-120">Newer SAN disks have very large memory caches, so in these cases the raid selection is not as important.</span></span> <span data-ttu-id="6ebc5-121">パフォーマンスを向上させるには、データベースおよびログ ファイルが別々 の物理ディスクに配置できます。</span><span class="sxs-lookup"><span data-stu-id="6ebc5-121">To increase performance, databases and their log files can reside on different physical disks.</span></span>  
  
 <span data-ttu-id="6ebc5-122">記憶域エリア ネットワーク (SAN) を使用する場合に、ホスト バス アダプター (HBA) のキューの深さをチューニングも検討します。</span><span class="sxs-lookup"><span data-stu-id="6ebc5-122">Also consider tuning the host bus adapter (HBA) queue depth if using a storage area network (SAN).</span></span> <span data-ttu-id="6ebc5-123">I/O のスループットに影響する可能性が大幅にあり、外のボックスの値は SQL Server の不十分であることができます。</span><span class="sxs-lookup"><span data-stu-id="6ebc5-123">This can significantly impact I/O throughput and out-of-the box values can be insufficient for SQL Server.</span></span> <span data-ttu-id="6ebc5-124">テストが最適な値を確認する必要がない場合は、特定の仕入先推奨事項の適切な開始点として通常 64 のキューの深さは受け入れられます</span><span class="sxs-lookup"><span data-stu-id="6ebc5-124">Testing is required to determine optimal value, although queue depth of 64 is generally accepted as a good starting point in the absence of any specific vendor recommendations</span></span>  
  
## <a name="install-the-latest-service-pack-and-cumulative-updates-for-sql-server"></a><span data-ttu-id="6ebc5-125">SQL Server の最新の service pack と累積的な更新プログラムをインストールします。</span><span class="sxs-lookup"><span data-stu-id="6ebc5-125">Install the latest service pack and cumulative updates for SQL Server</span></span>  
 <span data-ttu-id="6ebc5-126">SQL Server と .NET Framework の最新のサービス パックの最新のサービス パックと最新の累積的更新プログラムをインストールします。</span><span class="sxs-lookup"><span data-stu-id="6ebc5-126">Install the latest service packs and the latest cumulative updates for SQL Server as well as the latest .NET Framework service packs.</span></span>  
  
## <a name="install-sql-service-packs-and-cumulative-updates-on-both-biztalk-server-and-sql-server"></a><span data-ttu-id="6ebc5-127">BizTalk Server と SQL Server の両方で SQL サービス パックと累積更新プログラムをインストールします。</span><span class="sxs-lookup"><span data-stu-id="6ebc5-127">Install SQL Service Packs and cumulative updates on both BizTalk Server and SQL Server</span></span>  
 <span data-ttu-id="6ebc5-128">SQL Server のサービス パックまたは累積的更新プログラムをインストールするときにもインストール service pack または累積更新プログラム、BizTalk Server コンピューター。</span><span class="sxs-lookup"><span data-stu-id="6ebc5-128">When installing service packs or cumulative updates for SQL Server, also install the service pack or cumulative update on the BizTalk Server computer.</span></span> <span data-ttu-id="6ebc5-129">BizTalk Server では、SQL Server サービス パックおよび累積的な更新プログラムによって更新される SQL クライアント コンポーネントを使用します。</span><span class="sxs-lookup"><span data-stu-id="6ebc5-129">BizTalk Server uses SQL Client components that are updated by SQL Server service packs and cumulative updates.</span></span>  
  
## <a name="consider-using-a-fast-solid-state-drive-ssd-to-house-the-sql-server-tembdb"></a><span data-ttu-id="6ebc5-130">SQL Server tembdb を格納するに高速ソリッド ステート ドライブ (SSD) を使用してください。</span><span class="sxs-lookup"><span data-stu-id="6ebc5-130">Consider using a fast solid state drive (SSD) to house the SQL Server tembdb</span></span>  
 <span data-ttu-id="6ebc5-131">TempDB を格納する 1 つまたは複数の実線状態ディスク (SSD) ドライブを使用してください。</span><span class="sxs-lookup"><span data-stu-id="6ebc5-131">Consider using one or more Solid State Disk (SSD) drives to house the TempDB.</span></span> <span data-ttu-id="6ebc5-132">SSD ドライブは、従来のハード ドライブ上の大幅なパフォーマンスの利点があり、主流市場を入力するように価格で迅速に削除します。</span><span class="sxs-lookup"><span data-stu-id="6ebc5-132">SSD drives offer significant performance advantages over traditional hard drives and are quickly dropping in price as they enter mainstream markets.</span></span> <span data-ttu-id="6ebc5-133">TempDB のパフォーマンスは多くの場合、全体の重要な要因であるため[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]パフォーマンス、ドライブの初期コストをかけるは多くの場合、すばやくによって削減全体的な増加[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]特にエンタープライズ アプリケーションの実行時のパフォーマンス対象の[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]パフォーマンスが重要です。</span><span class="sxs-lookup"><span data-stu-id="6ebc5-133">Because TempDB performance is often a key factor for overall [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] performance, the added initial cost of the drives will often be quickly recouped by the overall increased [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] performance, especially when running enterprise applications for which [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] performance is critical.</span></span>  
  
## <a name="consider-implementing-the-sql-server-2008-r2-data-collector-and-management-data-warehouse"></a><span data-ttu-id="6ebc5-134">SQL Server 2008 R2 のデータ コレクターと管理データ ウェアハウスを実装することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="6ebc5-134">Consider implementing the SQL Server 2008 R2 Data Collector and Management Data Warehouse</span></span>  
 <span data-ttu-id="6ebc5-135">SQL Server 2008 R2 は、新しいの使用に対応環境/データベースのパフォーマンスを収集するには、データ コレクターや管理データ ウェアハウスに関連したテストと傾向分析のためのデータ。</span><span class="sxs-lookup"><span data-stu-id="6ebc5-135">SQL Server 2008 R2 accommodates the use of the new Data Collector and Management Data Warehouse to collect environment/database performance related data for test and trend analysis.</span></span> <span data-ttu-id="6ebc5-136">データ コレクターは、指定の管理データ ウェアハウスに収集されたすべてのデータを保持します。</span><span class="sxs-lookup"><span data-stu-id="6ebc5-136">The Data Collector persists all collected data to the specified Management Data Warehouse.</span></span> <span data-ttu-id="6ebc5-137">これはパフォーマンスの最適化ではありませんは、パフォーマンスの問題の分析に役立つこれになります。</span><span class="sxs-lookup"><span data-stu-id="6ebc5-137">While this is not a performance optimization this will be useful for analysis of any performance issues.</span></span>  
  
## <a name="grant-the-account-which-is-used-for-sql-server-the-windows-lock-pages-in-memory-privilege"></a><span data-ttu-id="6ebc5-138">Windows Lock Pages Memory 特権 In SQL Server に使用されるアカウントに付与します。</span><span class="sxs-lookup"><span data-stu-id="6ebc5-138">Grant the account which is used for SQL Server the Windows Lock Pages In Memory privilege</span></span>  
 <span data-ttu-id="6ebc5-139">Windows Lock Pages in Memory 特権を SQL Server サービス アカウントを付与します。</span><span class="sxs-lookup"><span data-stu-id="6ebc5-139">Grant the Windows Lock Pages in Memory privilege to the SQL Server service account.</span></span> <span data-ttu-id="6ebc5-140">これは、物理メモリにバッファー プールに割り当てられているメモリをロックすることにより、SQL Server プロセスのバッファー プール メモリのページングから Windows オペレーティング システムを防ぐために行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ebc5-140">This should be done to prevent the Windows operating system from paging out the buffer pool memory of the SQL Server process by locking memory that is allocated for the buffer pool in physical memory.</span></span>  
  
 <span data-ttu-id="6ebc5-141">Windows のポリシーで、ラボ環境で**Lock Pages in Memory**オプションが既定で有効にします。</span><span class="sxs-lookup"><span data-stu-id="6ebc5-141">In our lab environment, the Windows policy **Lock Pages in Memory** option was enabled by default.</span></span> <span data-ttu-id="6ebc5-142">参照してください[Lock Pages in Memory オプションを有効にする](https://docs.microsoft.com/sql/database-engine/configure-windows/enable-the-lock-pages-in-memory-option-windows)です。</span><span class="sxs-lookup"><span data-stu-id="6ebc5-142">See [Enable the Lock Pages in Memory Option](https://docs.microsoft.com/sql/database-engine/configure-windows/enable-the-lock-pages-in-memory-option-windows).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="6ebc5-143">SQL Server サービス アカウントの Windows Lock Pages in Memory 特権を付与するときに、いくつかの制限が適用されます。</span><span class="sxs-lookup"><span data-stu-id="6ebc5-143">Certain limitations apply when granting the SQL Server service account the Windows Lock Pages in Memory privilege.</span></span> <span data-ttu-id="6ebc5-144">次を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6ebc5-144">See the following:</span></span> 
>   
> - [<span data-ttu-id="6ebc5-145">バッファー プール拡張</span><span class="sxs-lookup"><span data-stu-id="6ebc5-145">Buffer Pool Extension</span></span>](https://docs.microsoft.com/sql/database-engine/configure-windows/buffer-pool-extension)  
> - [<span data-ttu-id="6ebc5-146">Lock Pages in Memory オプションを有効にします。</span><span class="sxs-lookup"><span data-stu-id="6ebc5-146">Enable the Lock Pages in Memory Option </span></span>](https://docs.microsoft.com/sql/database-engine/configure-windows/enable-the-lock-pages-in-memory-option-windows)  
  
## <a name="grant-the-semanagevolumename-right-to-the-sql-server-service-account"></a><span data-ttu-id="6ebc5-147">SQL Server サービス アカウントの権限を SE_MANAGE_VOLUME_NAME を与える</span><span class="sxs-lookup"><span data-stu-id="6ebc5-147">Grant the SE_MANAGE_VOLUME_NAME right to the SQL Server Service Account</span></span>  
 <span data-ttu-id="6ebc5-148">SQL Server サービスを実行しているアカウントは、' ボリュームの保守タスクを実行する ' Windows 特権を持つことを確認またはグループに属していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="6ebc5-148">Ensure the account running the SQL Server service has the ‘Perform Volume Maintenance Tasks’ Windows privilege or ensure it belongs to a group that does.</span></span> <span data-ttu-id="6ebc5-149">これによって、ファイルの瞬時初期化の確保最適なパフォーマンス、データベースの自動拡張する場合。</span><span class="sxs-lookup"><span data-stu-id="6ebc5-149">This will allow instant file Initialization ensuring optimum performance if a database has to Auto-grow.</span></span>  
  
## <a name="set-min-and-max-server-memory"></a><span data-ttu-id="6ebc5-150">Min および Max Server Memory を設定します。</span><span class="sxs-lookup"><span data-stu-id="6ebc5-150">Set Min and Max Server Memory</span></span>  
 <span data-ttu-id="6ebc5-151">ホストする SQL Server を実行するコンピューター、BizTalk Server データベースは、SQL Server を実行する専用必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ebc5-151">The computers running SQL Server that host the BizTalk Server databases should be dedicated to running SQL Server.</span></span> <span data-ttu-id="6ebc5-152">'Min server memory' と各 SQL Server インスタンス上の 'max server memory' オプションが設定を固定するメモリ量を指定することが推奨をホストする SQL Server を実行するコンピューターの BizTalk Server データベースは専用 SQL Server を実行して、SQL Server に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="6ebc5-152">When the computers running SQL Server that host the BizTalk Server databases are dedicated to running SQL Server, we recommend that the 'min server memory' and 'max server memory' options on each SQL Server instance are set to specify the fixed amount of memory to allocate to SQL Server.</span></span> <span data-ttu-id="6ebc5-153">この場合、する必要があります"min server memory"と"max server memory"、同じ値に設定 (SQL Server が使用される物理メモリの最大量に等しい)。</span><span class="sxs-lookup"><span data-stu-id="6ebc5-153">In this case, you should set the “min server memory” and “max server memory” to the same value (equal to the maximum amount of physical memory that SQL Server will use).</span></span> <span data-ttu-id="6ebc5-154">これが減少それ以外の場合にこれらの値を動的に管理する SQL Server で使用されるオーバーヘッドです。</span><span class="sxs-lookup"><span data-stu-id="6ebc5-154">This will reduce overhead that would otherwise be used by SQL Server dynamically managing these values.</span></span> <span data-ttu-id="6ebc5-155">SQL Server に割り当てるメモリの固定量を指定する SQL Server を実行する各コンピューターで、次の T-SQL コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="6ebc5-155">Run the following T-SQL commands on each computer running SQL Server to specify the fixed amount of memory to allocate to SQL Server:</span></span>  
  
```  
sp_configure ‘Max Server memory (MB)’,(max size in MB)  
sp_configure ‘Min Server memory (MB)’,(min size in MB)  
```  
  
 <span data-ttu-id="6ebc5-156">SQL Server のメモリの量を設定すると、前に、合計物理メモリから Windows Server に必要なメモリを差し引くことで適切なメモリ設定を決定します。</span><span class="sxs-lookup"><span data-stu-id="6ebc5-156">Before you set the amount of memory for SQL Server, determine the appropriate memory setting by subtracting the memory required for Windows Server from the total physical memory.</span></span> <span data-ttu-id="6ebc5-157">これは、SQL Server に割り当てるメモリの最大量です。</span><span class="sxs-lookup"><span data-stu-id="6ebc5-157">This is the maximum amount of memory you can assign to SQL Server.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6ebc5-158">ホストする SQL Server を実行するコンピューターの BizTalk Server データベースもホストする場合、エンタープライズ シングル サインオン マスター シークレット サーバー、したい場合があります、エンタープライズ シングル サインオンを実行するための十分なメモリがあることを確認するには、この値を調整するにはサービス。</span><span class="sxs-lookup"><span data-stu-id="6ebc5-158">If the computers running SQL Server that host the BizTalk Server databases also host the Enterprise Single Sign-On Master Secret Server, then you may need to adjust this value to ensure that there is sufficient memory available to run the Enterprise Single Sign-On Service.</span></span> <span data-ttu-id="6ebc5-159">マスター シークレット サーバーの高可用性を実現する SQL Server クラスターでクラスター化されたエンタープライズ シングル サインオン サービスのインスタンスを実行することは珍しくの実習ではないです。</span><span class="sxs-lookup"><span data-stu-id="6ebc5-159">It is not an uncommon practice to run a clustered instance of the Enterprise Single Sign-On service on a SQL Server cluster to provide high availability for the Master Secret Server.</span></span> <span data-ttu-id="6ebc5-160">参照してください[マスター シークレット サーバーをクラスタ リング](../technical-guides/clustering-the-master-secret-server.md)</span><span class="sxs-lookup"><span data-stu-id="6ebc5-160">See [Clustering the Master Secret Server](../technical-guides/clustering-the-master-secret-server.md)</span></span>  
  
## <a name="split-the-tempdb-database-into-multiple-data-files-of-equal-size-on-each-sql-server-instance-used-by-biztalk-server"></a><span data-ttu-id="6ebc5-161">Tempdb データベースを同じサイズの BizTalk Server で使用される各 SQL Server インスタンス上の複数のデータ ファイルに分割します。</span><span class="sxs-lookup"><span data-stu-id="6ebc5-161">Split the tempdb database into multiple data files of equal size on each SQL Server instance used by BizTalk Server</span></span>  
 <span data-ttu-id="6ebc5-162">SQL Server で使用される比例アルゴリズムは、データ ファイルのサイズに基づいているために、ことを確認するための tempdb データ ファイルと同じサイズのことが重要です。</span><span class="sxs-lookup"><span data-stu-id="6ebc5-162">Ensuring that the data files used for the tempdb are of equal size is critical because the proportional fill algorithm used by SQL Server is based on the size of the data files.</span></span> <span data-ttu-id="6ebc5-163">サイズの異なるデータ ファイルが作成する場合、比例アルゴリズムは、それによってが無意味に複数のデータ ファイルを作成するすべてのファイル間での割り当てを展開するのではなく、GAM の割り当ての最大のファイルを使用します。</span><span class="sxs-lookup"><span data-stu-id="6ebc5-163">If data files are created with unequal sizes, the proportional fill algorithm will use the largest file more for GAM allocations rather than spreading the allocations between all the files, thereby defeating the purpose of creating multiple data files.</span></span> <span data-ttu-id="6ebc5-164">最適な数の tempdb データ ファイルは、ラッチの競合が tempdb での程度によって異なります。</span><span class="sxs-lookup"><span data-stu-id="6ebc5-164">The optimal number of tempdb data files depends on the degree of latch contention seen in tempdb.</span></span> <span data-ttu-id="6ebc5-165">一般的な則としてデータ ファイルの数は、ここで、Cpu の数は 8 プロセッサ コアと Cpu の数以下する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ebc5-165">As a general rule of thumb, the number of data files should be equal to number of processor cores/CPUs where number of CPUs is 8 or less.</span></span> <span data-ttu-id="6ebc5-166">8 個を超える cpu を搭載したサーバーでは、Cpu の数の半分のデータ ファイルの作成 (ここでも、のみがあるラッチの競合)。</span><span class="sxs-lookup"><span data-stu-id="6ebc5-166">For servers with more than 8 CPUs, create data files for half the number of CPUs (again, only you have latch contention).</span></span>  
  
 <span data-ttu-id="6ebc5-167">このラボ環境では、次のスクリプトを使用して、ファイル サイズが 100 MB の増加に 1024 MB のそれぞれが 8 の TempDB データ ファイルと 100 MB の増加に 512 MB のログ ファイルを作成しました。</span><span class="sxs-lookup"><span data-stu-id="6ebc5-167">In our lab environment, we used the script below to create 8 TempDB data files each of which had a file size of 1024 MB with 100 MB growth and a log file of 512 MB with 100 MB growth.</span></span> <span data-ttu-id="6ebc5-168">データ ファイルが: %m: ドライブに移動され、ログ ファイルは、i: ドライブに移動されます。</span><span class="sxs-lookup"><span data-stu-id="6ebc5-168">The data files are moved to drive H: and log file are moved to drive I:.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="6ebc5-169">このスクリプトは、提供「としては、」デモまたは演習目的でのみ、向けし、各自の責任で使用されます。</span><span class="sxs-lookup"><span data-stu-id="6ebc5-169">This script is provided “as is,” is intended for demo or educational purposes only, and is to be used at your own risk.</span></span> <span data-ttu-id="6ebc5-170">、Microsoft では、このスクリプトの使用はサポートされていないと、Microsoft がこのスクリプトの適合性に関して保証を行いません。</span><span class="sxs-lookup"><span data-stu-id="6ebc5-170">Use of this script is not supported by Microsoft, and Microsoft makes no guarantees about the suitability of this script.</span></span>  
  
```  
--<<<<<<<<<<----------------------------------------------------------------->>>>>>>>>>--  
-- Use of included script samples are subject to the terms specified at   
-- http://www.microsoft.com/info/cpyright.htm  
--<<<<<<<<<<----------------------------------------------------------------->>>>>>>>>>--  
--***Instructions***  
-- 1. If running the script from a remote server, change the context in SSMS to target instance  
-- 2. Enable SQLCMD mode (add & click toolbar button or toggle by clicking Query > SQLCMD Mode)  
-- 3. Commence execution of scripts (recommend running statements discretely to more easily remedy potential problems)  
-- 4. Examine servername & temp configuration  
-- 5. If necessary, 1) Replace instance name in path to reflect target instance *all throughout script*  
      --            2) Modify root drives to reflect drives designated for data & log (folder creation *and* ALTER DB statements)  
-- 6. Resume script execution  
-- 7. If necessary, create new folders  
-- 8. Modify/Add data & log files   
-- 9. Recycle SQL service using sqlservermanager10.msc  
--10. Examine results & if appropriate, delete original tempdb data log files   
 --(if they were "moved", the original files aren't automatically deleted)  
  
--<<<<<<<<<<----------------------------------------------------------------->>>>>>>>>>--  
--1. If running the script from a remote server, change the context in SSMS to target instance  
--2. Enable SQLCMD mode (add & click toolbar button or toggle by clicking Query > SQLCMD Mode)  
--3. Commence execution of scripts (recommend running statements discretely to more easily remedy potential problems)  
--4. Examine servername & temp configuration  
SELECT @@SERVERNAME  
EXEC dbo.sp_helpdb tempdb  
--tempdev   1   C:\tempdb.mdf   PRIMARY  8192 KB  Unlimited  10%  data only  
--templog   2   C:\templog.ldf  NULL      512 KB  Unlimited  10%  log only  
GO  
--5. If necessary, 1) Replace instance name in path to reflect target instance *all throughout script*  
     --            2) Modify root drives to reflect drives designated for data & log (folder creation *and* ALTER DB statements)  
--6. Resume script execution  
--7. If necessary, create new folders  
--!!md H:\MSSQL10.<instance>  
--!!md H:\MSSQL10.<instance>\MSSQL  
--!!md H:\MSSQL10.<instance>\MSSQL\DATA  
GO  
-- 8. Modify/Add data & log files   
 --note: even if the out-of-box mdf is already where it needs to be,   
   --the first command is necessary to modify size & filegrowth  
ALTER DATABASE tempdb MODIFY FILE (NAME = tempdev  , FILENAME = 'H:\tempdb.mdf'   , SIZE = 1024MB , FILEGROWTH = 100MB)  
ALTER DATABASE tempdb ADD FILE    (NAME = tempdat2 , FILENAME = 'H:\tempdat2.ndf' , SIZE = 1024MB , FILEGROWTH = 100MB)  
ALTER DATABASE tempdb ADD FILE    (NAME = tempdat3 , FILENAME = 'H:\tempdat3.ndf' , SIZE = 1024MB , FILEGROWTH = 100MB)  
ALTER DATABASE tempdb ADD FILE    (NAME = tempdat4 , FILENAME = 'H:\tempdat4.ndf' , SIZE = 1024MB , FILEGROWTH = 100MB)  
ALTER DATABASE tempdb ADD FILE    (NAME = tempdat5 , FILENAME = 'H:\tempdat5.ndf' , SIZE = 1024MB , FILEGROWTH = 100MB)  
ALTER DATABASE tempdb ADD FILE    (NAME = tempdat6 , FILENAME = 'H:\tempdat6.ndf' , SIZE = 1024MB , FILEGROWTH = 100MB)  
ALTER DATABASE tempdb ADD FILE    (NAME = tempdat7 , FILENAME = 'H:\tempdat7.ndf' , SIZE = 1024MB , FILEGROWTH = 100MB)  
ALTER DATABASE tempdb ADD FILE    (NAME = tempdat8 , FILENAME = 'H:\tempdat8.ndf' , SIZE = 1024MB , FILEGROWTH = 100MB)  
GO  
ALTER DATABASE tempdb MODIFY FILE (NAME = templog , FILENAME = 'I:\templog.ldf', SIZE =  512MB , FILEGROWTH = 100MB)  
GO  
--8b. Modify log file:  modify drive & instance name to reflect designated destination for tempdb log   
--!!md I:\MSSQL10.<instance>  
--!!md I:\MSSQL10.<instance>\MSSQL  
--!!md I:\MSSQL10.<instance>\MSSQL\DATA  
GO  
-- 9. Recycle SQL service in SQL Server Services node of sqlservermanager10.msc  
    --note, if running script from a UNC share, SSMS will report an error,   
      --but SQL Server Configuration Manager will open if its location is in %path%  
!!sqlservermanager10.msc  
  
--10. Examine results & if appropriate, delete original tempdb data log files   
 --(if they were "moved", the original files aren't automatically deleted)  
EXEC dbo.sp_helpdb tempdb  
--!!del C:\tempdb.mdf     
--!!del C:\templog.ldf  
GO  
  
```  
  
 <span data-ttu-id="6ebc5-171">SQL Server 2008 の利用状況モニターまたはで説明されている SQL Server 2005 Performance Dashboard Reports を使用して[SQL Server のパフォーマンスの監視](../technical-guides/monitoring-sql-server-performance.md)ラッチの競合の問題を特定します。</span><span class="sxs-lookup"><span data-stu-id="6ebc5-171">Use the SQL Server 2008 Activity Monitor or the SQL Server 2005 Performance Dashboard Reports described in [Monitoring SQL Server Performance](../technical-guides/monitoring-sql-server-performance.md) to identify problems with latch contention.</span></span>  
  
## <a name="manually-set-sql-server-process-affinity"></a><span data-ttu-id="6ebc5-172">SQL Server プロセスの関係を手動で設定します。</span><span class="sxs-lookup"><span data-stu-id="6ebc5-172">Manually set SQL Server Process Affinity</span></span>  
 <span data-ttu-id="6ebc5-173">プロセス関係オプションは、16 個以上の Cpu を持つ非 NUMA コンピューターで実行されている、エンタープライズ レベルのハイエンドの SQL Server 環境のパフォーマンスが向上を提供できます。</span><span class="sxs-lookup"><span data-stu-id="6ebc5-173">The Process Affinity option can provide performance enhancements in high-end, enterprise-level SQL Server environments that are running on non-NUMA computers with 16 or more CPUs.</span></span> <span data-ttu-id="6ebc5-174">これは、メッセージ ボックス データベース内の共有のテーブルでの競合がある高スループットの BizTalk 環境で特に当てはまります。</span><span class="sxs-lookup"><span data-stu-id="6ebc5-174">This is especially true in high-throughput BizTalk environments where you have contention on shared tables in the MessageBox database.</span></span> <span data-ttu-id="6ebc5-175">このラボ環境で使用された SQL Server コンピューターを選択して NUMA 対応インポートされなかったが、パフォーマンスを最適化するために、16 コア、ために、次のコマンドを使用して、プロセス関係の設定に。</span><span class="sxs-lookup"><span data-stu-id="6ebc5-175">Because the SQL Server computers that were used in our lab environment were not NUMA-enabled and had 16 cores, to optimize performance, we used the commands below to set process affinity:</span></span>  
  
 <span data-ttu-id="6ebc5-176">**0 から 15 に SQL Server プロセスの関係を手動で設定するには**</span><span class="sxs-lookup"><span data-stu-id="6ebc5-176">**To manually set the SQL Server Process Affinity from 0 to 15**</span></span>  
  
```  
ALTER SERVER CONFIGURATION  
SET PROCESS AFFINITY CPU = 0 to 15  
```  
  
 <span data-ttu-id="6ebc5-177">詳細については、次を参照してください。 [ALTER SERVER CONFIGURATION (TRANSACT-SQL)](https://docs.microsoft.com/sql/t-sql/statements/alter-server-configuration-transact-sql)です。</span><span class="sxs-lookup"><span data-stu-id="6ebc5-177">For more information, see [ALTER SERVER CONFIGURATION (Transact-SQL)](https://docs.microsoft.com/sql/t-sql/statements/alter-server-configuration-transact-sql).</span></span>
  
## <a name="configure-msdtc"></a><span data-ttu-id="6ebc5-178">MSDTC を構成します。</span><span class="sxs-lookup"><span data-stu-id="6ebc5-178">Configure MSDTC</span></span>  
 <span data-ttu-id="6ebc5-179">SQL Server と BizTalk Server の間でトランザクションを容易にするため、Microsoft 分散トランザクション コーディネーター (MS DTC) を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ebc5-179">To facilitate transactions between SQL Server and BizTalk Server, you must enable Microsoft Distributed Transaction Coordinator (MS DTC).</span></span> <span data-ttu-id="6ebc5-180">SQL Server で MSDTC を構成するには、トピックを参照して[オペレーティング システムのパフォーマンスを向上させるための一般的なガイドライン](../technical-guides/general-guidelines-for-improving-operating-system-performance.md)です。</span><span class="sxs-lookup"><span data-stu-id="6ebc5-180">To configure MSDTC on SQL Server, see the topic [General Guidelines for Improving Operating System Performance](../technical-guides/general-guidelines-for-improving-operating-system-performance.md).</span></span>  
  
## <a name="enable-trace-flag-t1118-as-a-startup-parameter-for-all-instances-of-sql-server"></a><span data-ttu-id="6ebc5-181">SQL Server のすべてのインスタンスの起動時のパラメーターとしてトレース フラグ-t1118 を実装を有効にします。</span><span class="sxs-lookup"><span data-stu-id="6ebc5-181">Enable Trace Flag T1118 as a startup parameter for all instances of SQL Server</span></span>  
 <span data-ttu-id="6ebc5-182">トレースを実装するフラグ –-t1118 を実装では、ほとんどすべての単一のページ割り当てを削除することで、SQL Server インスタンス間での競合を減らすことができます。</span><span class="sxs-lookup"><span data-stu-id="6ebc5-182">Implementing Trace Flag –T1118 helps reduce contention across the SQL Server instances by removing almost all single page allocations.</span></span> <span data-ttu-id="6ebc5-183">詳細については、次を参照してください。 [KB 328551: PRB: tempdb データベースの同時実行制御の機能強化](https://support.microsoft.com/help/328551/concurrency-enhancements-for-the-tempdb-database)です。</span><span class="sxs-lookup"><span data-stu-id="6ebc5-183">For more information, see [KB 328551: PRB: Concurrency enhancements for the tempdb database](https://support.microsoft.com/help/328551/concurrency-enhancements-for-the-tempdb-database).</span></span>
  
## <a name="do-not-change-default-sql-server-settings-for-max-degree-of-parallelism-sql-server-statistics-or-database-index-rebuilds-and-defragmentation"></a><span data-ttu-id="6ebc5-184">Max degree of parallelism、SQL Server 統計情報、またはデータベースのインデックス再構築と最適化の既定の SQL Server 設定を変更しません。</span><span class="sxs-lookup"><span data-stu-id="6ebc5-184">Do not change default SQL Server settings for max degree of parallelism, SQL Server statistics, or database index rebuilds and defragmentation</span></span>  
 <span data-ttu-id="6ebc5-185">SQL Server インスタンスには、BizTalk Server データベースを格納する場合、は、変更すべき特定の SQL Server の設定です。</span><span class="sxs-lookup"><span data-stu-id="6ebc5-185">If a SQL Server instance will house BizTalk Server databases, then there are certain SQL Server settings that should not be changed.</span></span> <span data-ttu-id="6ebc5-186">具体的には、SQL Server max degree of parallelism、メッセージ ボックス データベース、およびデータベースのインデックスの設定 SQL Server の統計を再構築し、最適化は変更できません。</span><span class="sxs-lookup"><span data-stu-id="6ebc5-186">Specifically, the SQL Server max degree of parallelism, the SQL Server statistics on the MessageBox database, and the settings for the database index rebuilds and defragmentation should not be modified.</span></span> <span data-ttu-id="6ebc5-187">参照してください[が変更されない SQL Server の設定](../technical-guides/sql-server-settings-that-should-not-be-changed.md)です。</span><span class="sxs-lookup"><span data-stu-id="6ebc5-187">See [SQL Server Settings That Should Not Be Changed](../technical-guides/sql-server-settings-that-should-not-be-changed.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="6ebc5-188">参照</span><span class="sxs-lookup"><span data-stu-id="6ebc5-188">See Also</span></span>  
 [<span data-ttu-id="6ebc5-189">データベース パフォーマンスの最適化</span><span class="sxs-lookup"><span data-stu-id="6ebc5-189">Optimizing Database Performance</span></span>](../technical-guides/optimizing-database-performance.md)
