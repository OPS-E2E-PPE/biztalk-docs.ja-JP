---
title: データベースの I/O の競合の監視と軽減 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bd6d3343-3fa3-469a-9772-e94f22fdf558
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ab8c8ca63556281644100e026a278c4141e19077
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65379475"
---
# <a name="monitoring-and-reducing-database-io-contention"></a><span data-ttu-id="4b873-102">監視と、データベース I/O 競合の削減</span><span class="sxs-lookup"><span data-stu-id="4b873-102">Monitoring and Reducing Database I/O Contention</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="4b873-103">パフォーマンスは、多くの場合に実行[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]パフォーマンスで、さらに、ディスク I/O パフォーマンスに基づいて多くの場合は。</span><span class="sxs-lookup"><span data-stu-id="4b873-103">performance is often predicated upon [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] performance, which in turn is often predicated upon disk I/O performance.</span></span> <span data-ttu-id="4b873-104">したがって、する必要がありますを監視し、ディスク I/O を実行しているコンピューターのパフォーマンスを調整[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]その家、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース。</span><span class="sxs-lookup"><span data-stu-id="4b873-104">Therefore, you should monitor and performance-tune disk I/O on the computers running [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] that house the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases.</span></span>  
  
## <a name="monitoring-disk-io"></a><span data-ttu-id="4b873-105">ディスク I/O の監視</span><span class="sxs-lookup"><span data-stu-id="4b873-105">Monitoring Disk I/O</span></span>  
 <span data-ttu-id="4b873-106">データベース処理を要する性質[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ディスク I/O がメッセージ ボックス データベースのボトルネックになることができます簡単に、BizTalk 追跡データベースですこれはディスク I/O でデータベース ファイルのボトルネックをしたことがない場合でも、 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] 。環境。</span><span class="sxs-lookup"><span data-stu-id="4b873-106">Because of the database-intensive nature of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], disk I/O can easily become a bottleneck on the MessageBox and BizTalk Tracking databases; this is true even if disk I/O has not previously been a bottleneck for the database files in your [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] environment.</span></span> <span data-ttu-id="4b873-107">そのため、事前にデータとトランザクション ログ ファイルを格納するディスクのディスク I/O パフォーマンスを測定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="4b873-107">Thus, we recommend that you proactively measure disk I/O performance for the disks that house the data and transaction log files.</span></span> <span data-ttu-id="4b873-108">システム モニターを使用してディスク I/O パフォーマンスを監視する方法の詳細については、次を参照してください。、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]記事["展開前 I/O のベスト プラクティス"](http://go.microsoft.com/fwlink/?LinkId=104829) (<http://go.microsoft.com/fwlink/?LinkId=104829>)。</span><span class="sxs-lookup"><span data-stu-id="4b873-108">For more information about monitoring disk I/O performance using System Monitor, see the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] article ["Predeployment I/O Best Practices"](http://go.microsoft.com/fwlink/?LinkId=104829) (<http://go.microsoft.com/fwlink/?LinkId=104829>).</span></span> <span data-ttu-id="4b873-109">SAN を使用している場合は、ディスク I/O パフォーマンスを測定する SAN ハードウェアの製造元から特定のツールも必要があります。</span><span class="sxs-lookup"><span data-stu-id="4b873-109">If you are using a SAN, you may also need specific tools from the SAN hardware manufacturer to measure disk I/O performance.</span></span>  
  
## <a name="separating-the-messagebox-and-biztalk-tracking-dta-databases-and-log-files"></a><span data-ttu-id="4b873-110">メッセージ ボックス データベースと BizTalk 追跡 (DTA) データベースとログ ファイルの分離</span><span class="sxs-lookup"><span data-stu-id="4b873-110">Separating the MessageBox and BizTalk Tracking (DTA) Databases and Log Files</span></span>  
 <span data-ttu-id="4b873-111">メッセージ ボックス データベースと BizTalk 追跡データベースは、最もアクティブであるために、ディスク I/O の競合に関する問題の可能性を低減する専用のドライブにこれらの各データ ファイルとトランザクション ログ ファイルを配置することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="4b873-111">Since the MessageBox and BizTalk Tracking databases are the most active, we recommend that you place the data files and transaction log files for each of these on dedicated drives to reduce the likelihood of problems with disk I/O contention.</span></span> <span data-ttu-id="4b873-112">たとえば、メッセージ ボックス データベースと BizTalk 追跡データベース ファイルを 4 つのドライブを必要次の各の 1 つのドライブ:</span><span class="sxs-lookup"><span data-stu-id="4b873-112">For example, you would need four drives for the MessageBox and BizTalk Tracking database files; one drive for each of the following:</span></span>  
  
- <span data-ttu-id="4b873-113">メッセージ ボックス データ ファイル</span><span class="sxs-lookup"><span data-stu-id="4b873-113">MessageBox data files</span></span>  
  
- <span data-ttu-id="4b873-114">メッセージ ボックス データベースのトランザクション ログ ファイル</span><span class="sxs-lookup"><span data-stu-id="4b873-114">MessageBox transaction log files</span></span>  
  
- <span data-ttu-id="4b873-115">データ ファイルを BizTalk 追跡</span><span class="sxs-lookup"><span data-stu-id="4b873-115">BizTalk Tracking data files</span></span>  
  
- <span data-ttu-id="4b873-116">トランザクション ログ ファイルを BizTalk 追跡</span><span class="sxs-lookup"><span data-stu-id="4b873-116">BizTalk Tracking transaction log files</span></span>  
  
  <span data-ttu-id="4b873-117">メッセージ ボックス データベースと BizTalk 追跡データベースを分離し、データベース ファイルとトランザクション ログ ファイルの異なる物理ディスクを分離することは、ディスク I/O の競合を減らすためのベスト プラクティスと見なされます。</span><span class="sxs-lookup"><span data-stu-id="4b873-117">Separating the MessageBox and BizTalk Tracking databases and separating the database files and transaction log files on different physical disks are considered best practices for reducing disk I/O contention.</span></span> <span data-ttu-id="4b873-118">できるだけ多くの物理スピンドルにディスク I/O を分散しようとしてください。</span><span class="sxs-lookup"><span data-stu-id="4b873-118">Try to spread the disk I/O across as many physical spindles as possible.</span></span> <span data-ttu-id="4b873-119">ディスクの競合を避ける方法についての詳細については、次を参照してください。[ディスクの競合を回避する方法](http://go.microsoft.com/fwlink/?LinkId=158809)(<http://go.microsoft.com/fwlink/?LinkId=158809>) で、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]パフォーマンスの最適化をガイドします。</span><span class="sxs-lookup"><span data-stu-id="4b873-119">For more information about avoiding disk contention, see [How to Avoid Disk Contention](http://go.microsoft.com/fwlink/?LinkId=158809) (<http://go.microsoft.com/fwlink/?LinkId=158809>) in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Performance Optimization Guide.</span></span>  
  
  <span data-ttu-id="4b873-120">構成した後、ファイルを手動で分離する必要があります[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="4b873-120">You should separate the files manually after configuring [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="4b873-121">詳細については、次を参照してください。、 [BizTalk Server データベースの最適化に関するホワイト ペーパー](http://go.microsoft.com/fwlink/?LinkId=101578) (<http://go.microsoft.com/fwlink/?LinkId=101578>)。</span><span class="sxs-lookup"><span data-stu-id="4b873-121">For more information, see the [BizTalk Server Database Optimization white paper](http://go.microsoft.com/fwlink/?LinkId=101578) (<http://go.microsoft.com/fwlink/?LinkId=101578>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b873-122">参照</span><span class="sxs-lookup"><span data-stu-id="4b873-122">See Also</span></span>  
 [<span data-ttu-id="4b873-123">ログ (PAL) ツールのパフォーマンス分析の使用</span><span class="sxs-lookup"><span data-stu-id="4b873-123">Using the Performance Analysis of Logs (PAL) Tool</span></span>](../technical-guides/using-the-performance-analysis-of-logs-pal-tool.md)