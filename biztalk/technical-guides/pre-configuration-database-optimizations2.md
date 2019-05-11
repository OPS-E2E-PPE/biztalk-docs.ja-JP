---
title: データベースの事前構成 Optimizations2 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8c525c3a-249c-4694-b287-a8c35a6aa524
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8b5486c3a18473998a11a98f6741097d2f751128
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399565"
---
# <a name="pre-configuration-database-optimizations"></a><span data-ttu-id="d3709-102">前の構成データベースの最適化</span><span class="sxs-lookup"><span data-stu-id="d3709-102">Pre-Configuration Database Optimizations</span></span>
<span data-ttu-id="d3709-103">ため、BizTalk Server 環境で SQL Server が果たす重要な役割が何よりも重要な SQL Server は、最適なパフォーマンス用に構成されている/調整します。</span><span class="sxs-lookup"><span data-stu-id="d3709-103">Because of the critical role that SQL Server plays in any BizTalk Server environment, it is of paramount importance that SQL Server be configured/tuned for optimal performance.</span></span> <span data-ttu-id="d3709-104">実行する SQL Server は、チューニングしない場合は、BizTalk Server で使用されるデータベースがボトルネックになり、BizTalk Server 環境の全体的なパフォーマンスが低下します。</span><span class="sxs-lookup"><span data-stu-id="d3709-104">If SQL Server is not tuned to perform well, then the databases used by BizTalk Server will become a bottleneck and the overall performance of the BizTalk Server environment will suffer.</span></span> <span data-ttu-id="d3709-105">このトピックでは、BizTalk Server をインストールして、BizTalk Server データベースを構成する前に従う必要がありますをいくつかの SQL Server パフォーマンスの最適化について説明します。</span><span class="sxs-lookup"><span data-stu-id="d3709-105">This topic describes several SQL Server performance optimizations that should be followed before installing BizTalk Server and configuring the BizTalk Server databases.</span></span>  
  
## <a name="set-ntfs-file-allocation-unit"></a><span data-ttu-id="d3709-106">NTFS ファイル アロケーション ユニットを設定します。</span><span class="sxs-lookup"><span data-stu-id="d3709-106">Set NTFS File Allocation Unit</span></span>  
 <span data-ttu-id="d3709-107">SQL Server では、そのデータを格納する**エクステント**、物理的に連続する 8 個の 8 K ページ (64 kb) のコレクションであります。</span><span class="sxs-lookup"><span data-stu-id="d3709-107">SQL Server stores its data in **Extents**, which are collections of eight physically contiguous 8K pages, or 64 KB.</span></span> <span data-ttu-id="d3709-108">そのため、ディスクのパフォーマンスを最適化するために、NTFS アロケーション ユニット サイズ 64 KB を「ディスク構成のベスト プラクティス」で説明されているように設定[展開前 I/O のベスト プラクティス](https://msdn.microsoft.com/library/cc966412.aspx)します。</span><span class="sxs-lookup"><span data-stu-id="d3709-108">Therefore, to optimize disk performance, set the NTFS Allocation Unit size to 64KB as described in the “Disk Configuration Best Practices” at  [Predeployment I/O Best Practices](https://msdn.microsoft.com/library/cc966412.aspx).</span></span>  
  
## <a name="considerations-for-the-version-and-edition-of-sql-server"></a><span data-ttu-id="d3709-109">バージョンおよびエディションの SQL Server に関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="d3709-109">Considerations for the version and edition of SQL Server</span></span>  
 <span data-ttu-id="d3709-110">さまざまなバージョンおよびエディションの[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]のパフォーマンスに影響するさまざまな機能を提供、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境。</span><span class="sxs-lookup"><span data-stu-id="d3709-110">Various versions and editions of [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] provide different features that can affect the performance of your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment.</span></span> <span data-ttu-id="d3709-111">たとえば、条件は負荷の高いの 32 ビット バージョンで利用可能なデータベース ロックの数[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]過ぎる可能性のある、BizTalk ソリューションのパフォーマンスに悪影響は。</span><span class="sxs-lookup"><span data-stu-id="d3709-111">For example, under high-load conditions, the number of database locks that are available for the 32-bit version of [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] might be exceeded, which is detrimental to the performance of the BizTalk solution.</span></span> <span data-ttu-id="d3709-112">テスト環境で"ロック"の範囲外のエラーが発生した場合、64 ビット バージョンの SQL Server でメッセージ ボックス データベースを格納していることを検討してください。</span><span class="sxs-lookup"><span data-stu-id="d3709-112">Consider housing your MessageBox database on a 64-bit version of SQL Server if you are experiencing "out of lock" errors in your test environment.</span></span> <span data-ttu-id="d3709-113">使用可能なロックの数は、64 ビット バージョンの SQL Server で大幅に高くなっています。</span><span class="sxs-lookup"><span data-stu-id="d3709-113">The number of available locks is significantly higher on the 64-bit version of SQL Server.</span></span>  
  
 <span data-ttu-id="d3709-114">BizTalk 環境に必要なデータベース エンジンの機能を決定する場合は、次の表を検討してください。</span><span class="sxs-lookup"><span data-stu-id="d3709-114">Consider the following table when deciding on the database engine features that you will need for your BizTalk environment.</span></span> <span data-ttu-id="d3709-115">大規模なエンタープライズ レベルのソリューションをクラスタ リングを必要とするサポート、BizTalk Server ログ配布のサポート、または Analysis Services がサポートし、ホストする SQL Server Enterprise Edition が必要がある、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]データベース。</span><span class="sxs-lookup"><span data-stu-id="d3709-115">For large scale, enterprise-level solutions that require clustering support, BizTalk Server log shipping support, or Analysis Services support, then you need SQL Server Enterprise Edition to host the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] databases.</span></span>   

 <span data-ttu-id="d3709-116">SQL Server のエディションでサポートされる機能の完全な一覧を参照してください。 [SQL Server のエディションとサポートされる機能](https://docs.microsoft.com/sql/sql-server/editions-and-components-of-sql-server-2016)します。</span><span class="sxs-lookup"><span data-stu-id="d3709-116">For a complete list of the features supported by the SQL Server editions, see [SQL Server Editions and supported features](https://docs.microsoft.com/sql/sql-server/editions-and-components-of-sql-server-2016).</span></span>
  
## <a name="database-planning-considerations"></a><span data-ttu-id="d3709-117">データベースの計画に関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="d3709-117">Database planning considerations</span></span>  
 <span data-ttu-id="d3709-118">高速ストレージ (SAN ディスクを高速または高速な SCSI ディスクなど) 上にある SQL Server データベースをホストすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d3709-118">We recommend that you host your SQL Server databases on fast storage (for example, fast SAN disks or fast SCSI disks).</span></span> <span data-ttu-id="d3709-119">RAID 5 ではなく、RAID 10 (1 + 0) は、raid 5 は書き込みで低速であるためお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d3709-119">We recommend RAID 10 (1+0) instead of RAID 5 since raid 5 is slower at writing.</span></span> <span data-ttu-id="d3709-120">このような場合も raid 選択が重要新しい SAN ディスク非常に大きなメモリ キャッシュがあります。</span><span class="sxs-lookup"><span data-stu-id="d3709-120">Newer SAN disks have very large memory caches, so in these cases the raid selection is not as important.</span></span> <span data-ttu-id="d3709-121">パフォーマンスを向上させるには、データベースおよびログ ファイルが別の物理ディスクに配置できます。</span><span class="sxs-lookup"><span data-stu-id="d3709-121">To increase performance, databases and their log files can reside on different physical disks.</span></span>  
  
 <span data-ttu-id="d3709-122">記憶域エリア ネットワーク (SAN) を使用する場合、ホスト バス アダプター (HBA) のキューの深さのチューニングも検討します。</span><span class="sxs-lookup"><span data-stu-id="d3709-122">Also consider tuning the host bus adapter (HBA) queue depth if using a storage area network (SAN).</span></span> <span data-ttu-id="d3709-123">I/O のスループットに影響する可能性が大幅にし、そのボックス外の値を SQL Server のための十分なできます。</span><span class="sxs-lookup"><span data-stu-id="d3709-123">This can significantly impact I/O throughput and out-of-the box values can be insufficient for SQL Server.</span></span> <span data-ttu-id="d3709-124">テストは、64 のキューの深さがない場合は、特定のベンダーの推奨事項の適切な開始点として使用されますが、最適な値を決定するために必要</span><span class="sxs-lookup"><span data-stu-id="d3709-124">Testing is required to determine optimal value, although queue depth of 64 is generally accepted as a good starting point in the absence of any specific vendor recommendations</span></span>  
  
## <a name="install-the-latest-service-pack-and-cumulative-updates-for-sql-server"></a><span data-ttu-id="d3709-125">SQL Server の最新の service pack と累積的更新プログラムをインストールします。</span><span class="sxs-lookup"><span data-stu-id="d3709-125">Install the latest service pack and cumulative updates for SQL Server</span></span>  
 <span data-ttu-id="d3709-126">SQL Server と .NET Framework の最新のサービス パックには、最新のサービス パックと最新の累積的更新プログラムをインストールします。</span><span class="sxs-lookup"><span data-stu-id="d3709-126">Install the latest service packs and the latest cumulative updates for SQL Server as well as the latest .NET Framework service packs.</span></span>  
  
## <a name="install-sql-service-packs-and-cumulative-updates-on-both-biztalk-server-and-sql-server"></a><span data-ttu-id="d3709-127">BizTalk Server と SQL Server の両方で SQL サービス パックや累積的更新プログラムをインストールします。</span><span class="sxs-lookup"><span data-stu-id="d3709-127">Install SQL Service Packs and cumulative updates on both BizTalk Server and SQL Server</span></span>  
 <span data-ttu-id="d3709-128">SQL Server のサービス パックまたは累積的更新プログラムをインストールするときにも、サービス パックまたは累積更新プログラムをインストール、BizTalk Server コンピューター。</span><span class="sxs-lookup"><span data-stu-id="d3709-128">When installing service packs or cumulative updates for SQL Server, also install the service pack or cumulative update on the BizTalk Server computer.</span></span> <span data-ttu-id="d3709-129">BizTalk Server では、SQL Server サービス パックや累積的更新プログラムによって更新される SQL クライアント コンポーネントを使用します。</span><span class="sxs-lookup"><span data-stu-id="d3709-129">BizTalk Server uses SQL Client components that are updated by SQL Server service packs and cumulative updates.</span></span>  
  
## <a name="consider-using-a-fast-solid-state-drive-ssd-to-house-the-sql-server-tembdb"></a><span data-ttu-id="d3709-130">SQL Server tembdb を格納するための高速なソリッド ステート ドライブ (SSD) の使用を検討します。</span><span class="sxs-lookup"><span data-stu-id="d3709-130">Consider using a fast solid state drive (SSD) to house the SQL Server tembdb</span></span>  
 <span data-ttu-id="d3709-131">TempDB を格納するための 1 つまたは複数のソリッド ステート ディスク (SSD) ドライブを使用してください。</span><span class="sxs-lookup"><span data-stu-id="d3709-131">Consider using one or more Solid State Disk (SSD) drives to house the TempDB.</span></span> <span data-ttu-id="d3709-132">SSD ドライブは、従来のハード ドライブ上の大幅なパフォーマンスの利点を提供し、主流の市場に参入するように価格ですぐに削除します。</span><span class="sxs-lookup"><span data-stu-id="d3709-132">SSD drives offer significant performance advantages over traditional hard drives and are quickly dropping in price as they enter mainstream markets.</span></span> <span data-ttu-id="d3709-133">TempDB のパフォーマンスは全体の重要な要因が多いため[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]パフォーマンス、ドライブの追加の初期コストは多くの場合、すばやくによって削減全体的な増加[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]パフォーマンス、特にエンタープライズ アプリケーションを実行する場合対象の[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]パフォーマンスが重要です。</span><span class="sxs-lookup"><span data-stu-id="d3709-133">Because TempDB performance is often a key factor for overall [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] performance, the added initial cost of the drives will often be quickly recouped by the overall increased [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] performance, especially when running enterprise applications for which [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] performance is critical.</span></span>  
  
## <a name="consider-implementing-the-sql-server-2008-r2-data-collector-and-management-data-warehouse"></a><span data-ttu-id="d3709-134">SQL Server 2008 R2 のデータ コレクターと管理データ ウェアハウスの実装を検討してください。</span><span class="sxs-lookup"><span data-stu-id="d3709-134">Consider implementing the SQL Server 2008 R2 Data Collector and Management Data Warehouse</span></span>  
 <span data-ttu-id="d3709-135">SQL Server 2008 R2 は、新しいの使用に対応環境とデータベースのパフォーマンスを収集するには、データ コレクターや管理データ ウェアハウスに関連したテストと傾向の分析のためのデータ。</span><span class="sxs-lookup"><span data-stu-id="d3709-135">SQL Server 2008 R2 accommodates the use of the new Data Collector and Management Data Warehouse to collect environment/database performance related data for test and trend analysis.</span></span> <span data-ttu-id="d3709-136">データ コレクターは、指定した管理データ ウェアハウスに収集されたすべてのデータを保持します。</span><span class="sxs-lookup"><span data-stu-id="d3709-136">The Data Collector persists all collected data to the specified Management Data Warehouse.</span></span> <span data-ttu-id="d3709-137">これはパフォーマンスの最適化ではありませんこれがパフォーマンスの問題の分析に有用になります。</span><span class="sxs-lookup"><span data-stu-id="d3709-137">While this is not a performance optimization this will be useful for analysis of any performance issues.</span></span>  
  
## <a name="grant-the-account-which-is-used-for-sql-server-the-windows-lock-pages-in-memory-privilege"></a><span data-ttu-id="d3709-138">SQL Server の Windows のロックの Pages In Memory 特権に使用されるアカウントに付与します。</span><span class="sxs-lookup"><span data-stu-id="d3709-138">Grant the account which is used for SQL Server the Windows Lock Pages In Memory privilege</span></span>  
 <span data-ttu-id="d3709-139">Windows Lock Pages in Memory 特権を SQL Server のサービス アカウントを付与します。</span><span class="sxs-lookup"><span data-stu-id="d3709-139">Grant the Windows Lock Pages in Memory privilege to the SQL Server service account.</span></span> <span data-ttu-id="d3709-140">これは、SQL Server プロセスのバッファー プール メモリのページングから物理メモリにバッファー プールに割り当てられたメモリをロックすることにより、Windows オペレーティング システムを防ぐために実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d3709-140">This should be done to prevent the Windows operating system from paging out the buffer pool memory of the SQL Server process by locking memory that is allocated for the buffer pool in physical memory.</span></span>  
  
 <span data-ttu-id="d3709-141">Windows のポリシーで、ラボ環境で**Lock Pages in Memory**オプションが既定で有効にします。</span><span class="sxs-lookup"><span data-stu-id="d3709-141">In our lab environment, the Windows policy **Lock Pages in Memory** option was enabled by default.</span></span> <span data-ttu-id="d3709-142">参照してください[Lock Pages in Memory オプションを有効にする](https://docs.microsoft.com/sql/database-engine/configure-windows/enable-the-lock-pages-in-memory-option-windows)します。</span><span class="sxs-lookup"><span data-stu-id="d3709-142">See [Enable the Lock Pages in Memory Option](https://docs.microsoft.com/sql/database-engine/configure-windows/enable-the-lock-pages-in-memory-option-windows).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="d3709-143">SQL Server のサービス アカウントに Windows Lock Pages in Memory 特権を許可するときに、いくつかの制限が適用されます。</span><span class="sxs-lookup"><span data-stu-id="d3709-143">Certain limitations apply when granting the SQL Server service account the Windows Lock Pages in Memory privilege.</span></span> <span data-ttu-id="d3709-144">次を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d3709-144">See the following:</span></span> 
>   
> - [<span data-ttu-id="d3709-145">バッファー プール拡張</span><span class="sxs-lookup"><span data-stu-id="d3709-145">Buffer Pool Extension</span></span>](https://docs.microsoft.com/sql/database-engine/configure-windows/buffer-pool-extension)  
> - [<span data-ttu-id="d3709-146">Lock Pages in Memory オプションを有効にします。 </span><span class="sxs-lookup"><span data-stu-id="d3709-146">Enable the Lock Pages in Memory Option </span></span>](https://docs.microsoft.com/sql/database-engine/configure-windows/enable-the-lock-pages-in-memory-option-windows)  
  
## <a name="grant-the-semanagevolumename-right-to-the-sql-server-service-account"></a><span data-ttu-id="d3709-147">SQL Server のサービス アカウントの権限を SE_MANAGE_VOLUME_NAME を付与します。</span><span class="sxs-lookup"><span data-stu-id="d3709-147">Grant the SE_MANAGE_VOLUME_NAME right to the SQL Server Service Account</span></span>  
 <span data-ttu-id="d3709-148">SQL Server サービスを実行しているアカウントは、' ボリュームの保守タスクを実行する ' Windows 特権を持つことを確認するか、グループに属していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d3709-148">Ensure the account running the SQL Server service has the ‘Perform Volume Maintenance Tasks’ Windows privilege or ensure it belongs to a group that does.</span></span> <span data-ttu-id="d3709-149">データベースの自動拡張がある場合は、このファイルの瞬時初期化の確保最適なパフォーマンスによりします。</span><span class="sxs-lookup"><span data-stu-id="d3709-149">This will allow instant file Initialization ensuring optimum performance if a database has to Auto-grow.</span></span>  
  
## <a name="set-min-and-max-server-memory"></a><span data-ttu-id="d3709-150">Min と Max Server Memory を設定します。</span><span class="sxs-lookup"><span data-stu-id="d3709-150">Set Min and Max Server Memory</span></span>  
 <span data-ttu-id="d3709-151">ホストする SQL Server を実行するコンピューター、BizTalk Server データベースを SQL Server を実行する専用必要があります。</span><span class="sxs-lookup"><span data-stu-id="d3709-151">The computers running SQL Server that host the BizTalk Server databases should be dedicated to running SQL Server.</span></span> <span data-ttu-id="d3709-152">'Min server memory' と各 SQL Server インスタンス '最大サーバー メモリ' オプションが設定を固定するメモリ量を指定することが推奨をホストする SQL Server を実行するコンピューター、BizTalk Server データベースは専用の SQL Server を実行するときにSQL Server に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="d3709-152">When the computers running SQL Server that host the BizTalk Server databases are dedicated to running SQL Server, we recommend that the 'min server memory' and 'max server memory' options on each SQL Server instance are set to specify the fixed amount of memory to allocate to SQL Server.</span></span> <span data-ttu-id="d3709-153">この場合、する必要があります設定する"min server memory"と"max server memory"を同じ値 (SQL Server を使用する物理メモリの最大量に等しい)。</span><span class="sxs-lookup"><span data-stu-id="d3709-153">In this case, you should set the “min server memory” and “max server memory” to the same value (equal to the maximum amount of physical memory that SQL Server will use).</span></span> <span data-ttu-id="d3709-154">これが減少オーバーヘッドはそれ以外の場合これらの値を動的に管理する SQL Server によって使用されます。</span><span class="sxs-lookup"><span data-stu-id="d3709-154">This will reduce overhead that would otherwise be used by SQL Server dynamically managing these values.</span></span> <span data-ttu-id="d3709-155">SQL Server に割り当てるメモリの固定量を指定する SQL Server を実行している各コンピューターで、次の T-SQL コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="d3709-155">Run the following T-SQL commands on each computer running SQL Server to specify the fixed amount of memory to allocate to SQL Server:</span></span>  
  
```  
sp_configure ‘Max Server memory (MB)’,(max size in MB)  
sp_configure ‘Min Server memory (MB)’,(min size in MB)  
```  
  
 <span data-ttu-id="d3709-156">SQL Server のメモリの量を設定する前に、Windows Server に必要な合計物理メモリからメモリを差し引くことで、適切なメモリ設定を決定します。</span><span class="sxs-lookup"><span data-stu-id="d3709-156">Before you set the amount of memory for SQL Server, determine the appropriate memory setting by subtracting the memory required for Windows Server from the total physical memory.</span></span> <span data-ttu-id="d3709-157">これは、SQL Server に割り当てるメモリの最大量です。</span><span class="sxs-lookup"><span data-stu-id="d3709-157">This is the maximum amount of memory you can assign to SQL Server.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d3709-158">ホストする SQL Server を実行するコンピューター、BizTalk Server データベースも、エンタープライズ シングル サインオン マスター シークレット サーバーをホストし場合エンタープライズ シングル サインオンを実行するための十分なメモリがあることを確認するには、この値を調整するにはサービス。</span><span class="sxs-lookup"><span data-stu-id="d3709-158">If the computers running SQL Server that host the BizTalk Server databases also host the Enterprise Single Sign-On Master Secret Server, then you may need to adjust this value to ensure that there is sufficient memory available to run the Enterprise Single Sign-On Service.</span></span> <span data-ttu-id="d3709-159">マスター シークレット サーバーの高可用性を実現する SQL Server クラスターでエンタープライズ シングル サインオン サービスのクラスター化されたインスタンスを実行するは珍しい方法ではありません。</span><span class="sxs-lookup"><span data-stu-id="d3709-159">It is not an uncommon practice to run a clustered instance of the Enterprise Single Sign-On service on a SQL Server cluster to provide high availability for the Master Secret Server.</span></span> <span data-ttu-id="d3709-160">参照してください[マスター シークレット サーバーをクラスタ リング](../technical-guides/clustering-the-master-secret-server.md)</span><span class="sxs-lookup"><span data-stu-id="d3709-160">See [Clustering the Master Secret Server](../technical-guides/clustering-the-master-secret-server.md)</span></span>  
  
## <a name="split-the-tempdb-database-into-multiple-data-files-of-equal-size-on-each-sql-server-instance-used-by-biztalk-server"></a><span data-ttu-id="d3709-161">Tempdb データベースを BizTalk Server で使用される各 SQL Server インスタンスに等しいサイズの複数のデータ ファイルに分割します。</span><span class="sxs-lookup"><span data-stu-id="d3709-161">Split the tempdb database into multiple data files of equal size on each SQL Server instance used by BizTalk Server</span></span>  
 <span data-ttu-id="d3709-162">SQL Server で使用される、比例書き込みアルゴリズムは、データ ファイルのサイズに基づいているために、tempdb に使用されるデータ ファイルが同じサイズのことが重要です。</span><span class="sxs-lookup"><span data-stu-id="d3709-162">Ensuring that the data files used for the tempdb are of equal size is critical because the proportional fill algorithm used by SQL Server is based on the size of the data files.</span></span> <span data-ttu-id="d3709-163">サイズの異なるデータ ファイルが作成、比例書き込みアルゴリズムは、一番大きいファイルを複数のデータ ファイルを作成する目的にそぐわなくなりますそれによって、すべてのファイル間の割り当てを展開するのではなく、GAM 割り当てを使用します。</span><span class="sxs-lookup"><span data-stu-id="d3709-163">If data files are created with unequal sizes, the proportional fill algorithm will use the largest file more for GAM allocations rather than spreading the allocations between all the files, thereby defeating the purpose of creating multiple data files.</span></span> <span data-ttu-id="d3709-164">Tempdb データ ファイルの最適な数は、tempdb でラッチの競合の程度によって異なります。</span><span class="sxs-lookup"><span data-stu-id="d3709-164">The optimal number of tempdb data files depends on the degree of latch contention seen in tempdb.</span></span> <span data-ttu-id="d3709-165">一般則としてデータ ファイルの数は、Cpu の数が 8 には、プロセッサ コア/Cpu の数と等しく以下する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d3709-165">As a general rule of thumb, the number of data files should be equal to number of processor cores/CPUs where number of CPUs is 8 or less.</span></span> <span data-ttu-id="d3709-166">8 個を超える cpu を搭載したサーバーでは、Cpu の数の半分のデータ ファイルの作成 (ここでも、のみがあるラッチの競合)。</span><span class="sxs-lookup"><span data-stu-id="d3709-166">For servers with more than 8 CPUs, create data files for half the number of CPUs (again, only you have latch contention).</span></span>  
  
 <span data-ttu-id="d3709-167">このラボ環境では、次のスクリプトを使用して、100 MB の増加に 1024 MB のファイル サイズがそれぞれの 8 つの TempDB データ ファイルと 100 MB の増加に 512 MB のログ ファイルを作成しました。</span><span class="sxs-lookup"><span data-stu-id="d3709-167">In our lab environment, we used the script below to create 8 TempDB data files each of which had a file size of 1024 MB with 100 MB growth and a log file of 512 MB with 100 MB growth.</span></span> <span data-ttu-id="d3709-168">データ ファイルはドライブ: %m: に移動し、ログ ファイルは、操作をドライブに移動されます。</span><span class="sxs-lookup"><span data-stu-id="d3709-168">The data files are moved to drive H: and log file are moved to drive I:.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="d3709-169">このスクリプトは、デモまたは教育目的にのみのためのものでは、ご自身の責任で使用される「とは、」です。</span><span class="sxs-lookup"><span data-stu-id="d3709-169">This script is provided “as is,” is intended for demo or educational purposes only, and is to be used at your own risk.</span></span> <span data-ttu-id="d3709-170">、Microsoft では、このスクリプトの使用はサポートされていないと、このスクリプトの適合性に関する Microsoft の保証がありません。</span><span class="sxs-lookup"><span data-stu-id="d3709-170">Use of this script is not supported by Microsoft, and Microsoft makes no guarantees about the suitability of this script.</span></span>  
  
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
  
 <span data-ttu-id="d3709-171">SQL Server 2008 の利用状況モニターまたはで説明されている SQL Server 2005 Performance Dashboard Reports を使用して、 [SQL Server のパフォーマンスの監視](../technical-guides/monitoring-sql-server-performance.md)ラッチの競合の問題を特定します。</span><span class="sxs-lookup"><span data-stu-id="d3709-171">Use the SQL Server 2008 Activity Monitor or the SQL Server 2005 Performance Dashboard Reports described in [Monitoring SQL Server Performance](../technical-guides/monitoring-sql-server-performance.md) to identify problems with latch contention.</span></span>  
  
## <a name="manually-set-sql-server-process-affinity"></a><span data-ttu-id="d3709-172">SQL Server プロセスの関係を手動で設定します。</span><span class="sxs-lookup"><span data-stu-id="d3709-172">Manually set SQL Server Process Affinity</span></span>  
 <span data-ttu-id="d3709-173">プロセス関係オプションは、16 個以上の Cpu を持つ非 NUMA コンピューターで実行されているハイエンドのエンタープライズ レベルの SQL Server 環境のパフォーマンス強化を提供できます。</span><span class="sxs-lookup"><span data-stu-id="d3709-173">The Process Affinity option can provide performance enhancements in high-end, enterprise-level SQL Server environments that are running on non-NUMA computers with 16 or more CPUs.</span></span> <span data-ttu-id="d3709-174">これは、メッセージ ボックス データベース内の共有テーブルでの競合がある高スループットの BizTalk 環境に特に当てはまります。</span><span class="sxs-lookup"><span data-stu-id="d3709-174">This is especially true in high-throughput BizTalk environments where you have contention on shared tables in the MessageBox database.</span></span> <span data-ttu-id="d3709-175">ラボ環境で使用されていた SQL Server コンピューターの NUMA 対応でしたおよび 16 コア、パフォーマンスを最適化する必要があるので、プロセスの関係を設定する次のコマンドを使いました。</span><span class="sxs-lookup"><span data-stu-id="d3709-175">Because the SQL Server computers that were used in our lab environment were not NUMA-enabled and had 16 cores, to optimize performance, we used the commands below to set process affinity:</span></span>  
  
 <span data-ttu-id="d3709-176">**0 から 15 に SQL Server プロセスの関係を手動で設定するには**</span><span class="sxs-lookup"><span data-stu-id="d3709-176">**To manually set the SQL Server Process Affinity from 0 to 15**</span></span>  
  
```  
ALTER SERVER CONFIGURATION  
SET PROCESS AFFINITY CPU = 0 to 15  
```  
  
 <span data-ttu-id="d3709-177">詳細については、次を参照してください。 [ALTER SERVER CONFIGURATION (TRANSACT-SQL)](https://docs.microsoft.com/sql/t-sql/statements/alter-server-configuration-transact-sql)します。</span><span class="sxs-lookup"><span data-stu-id="d3709-177">For more information, see [ALTER SERVER CONFIGURATION (Transact-SQL)](https://docs.microsoft.com/sql/t-sql/statements/alter-server-configuration-transact-sql).</span></span>
  
## <a name="configure-msdtc"></a><span data-ttu-id="d3709-178">MSDTC の構成</span><span class="sxs-lookup"><span data-stu-id="d3709-178">Configure MSDTC</span></span>  
 <span data-ttu-id="d3709-179">SQL Server と BizTalk Server 間のトランザクションを促進するには、Microsoft 分散トランザクション コーディネーター (MS DTC) を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d3709-179">To facilitate transactions between SQL Server and BizTalk Server, you must enable Microsoft Distributed Transaction Coordinator (MS DTC).</span></span> <span data-ttu-id="d3709-180">SQL Server 上で MSDTC を構成するには、トピックを参照して[オペレーティング システムのパフォーマンスを向上させるための一般的なガイドライン](../technical-guides/general-guidelines-for-improving-operating-system-performance.md)します。</span><span class="sxs-lookup"><span data-stu-id="d3709-180">To configure MSDTC on SQL Server, see the topic [General Guidelines for Improving Operating System Performance](../technical-guides/general-guidelines-for-improving-operating-system-performance.md).</span></span>  
  
## <a name="enable-trace-flag-t1118-as-a-startup-parameter-for-all-instances-of-sql-server"></a><span data-ttu-id="d3709-181">SQL Server のすべてのインスタンスの起動時のパラメーターとしてトレース フラグ-t1118 を実装を有効にします。</span><span class="sxs-lookup"><span data-stu-id="d3709-181">Enable Trace Flag T1118 as a startup parameter for all instances of SQL Server</span></span>  
 <span data-ttu-id="d3709-182">トレースを実装する – フラグ-t1118 を実装では、ほぼすべての単一ページの割り当てを削除することで、SQL Server インスタンス間で競合を減らすことができます。</span><span class="sxs-lookup"><span data-stu-id="d3709-182">Implementing Trace Flag –T1118 helps reduce contention across the SQL Server instances by removing almost all single page allocations.</span></span> <span data-ttu-id="d3709-183">詳細については、次を参照してください。 [KB 328551。[PRB]:Tempdb データベースの同時実行制御の強化](https://support.microsoft.com/help/328551/concurrency-enhancements-for-the-tempdb-database)します。</span><span class="sxs-lookup"><span data-stu-id="d3709-183">For more information, see [KB 328551: PRB: Concurrency enhancements for the tempdb database](https://support.microsoft.com/help/328551/concurrency-enhancements-for-the-tempdb-database).</span></span>
  
## <a name="do-not-change-default-sql-server-settings-for-max-degree-of-parallelism-sql-server-statistics-or-database-index-rebuilds-and-defragmentation"></a><span data-ttu-id="d3709-184">Max degree of parallelism、SQL Server の統計、またはデータベースのインデックス再構築と最適化の既定の SQL Server 設定を変更しません。</span><span class="sxs-lookup"><span data-stu-id="d3709-184">Do not change default SQL Server settings for max degree of parallelism, SQL Server statistics, or database index rebuilds and defragmentation</span></span>  
 <span data-ttu-id="d3709-185">SQL Server インスタンスには、BizTalk Server データベースを格納する場合、は、特定の SQL Server 設定を変更しないでください。</span><span class="sxs-lookup"><span data-stu-id="d3709-185">If a SQL Server instance will house BizTalk Server databases, then there are certain SQL Server settings that should not be changed.</span></span> <span data-ttu-id="d3709-186">具体的には、並列処理の最大限度の SQL Server、SQL Server の統計をメッセージ ボックス データベースとデータベースのインデックスの設定を再構築し、最適化を変更しないでください。</span><span class="sxs-lookup"><span data-stu-id="d3709-186">Specifically, the SQL Server max degree of parallelism, the SQL Server statistics on the MessageBox database, and the settings for the database index rebuilds and defragmentation should not be modified.</span></span> <span data-ttu-id="d3709-187">参照してください[SQL Server の設定を変更しないでください](../technical-guides/sql-server-settings-that-should-not-be-changed.md)します。</span><span class="sxs-lookup"><span data-stu-id="d3709-187">See [SQL Server Settings That Should Not Be Changed](../technical-guides/sql-server-settings-that-should-not-be-changed.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d3709-188">参照</span><span class="sxs-lookup"><span data-stu-id="d3709-188">See Also</span></span>  
 [<span data-ttu-id="d3709-189">データベース パフォーマンスの最適化</span><span class="sxs-lookup"><span data-stu-id="d3709-189">Optimizing Database Performance</span></span>](../technical-guides/optimizing-database-performance.md)
