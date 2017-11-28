---
title: "DBNETLIB 例外の回避 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5fbee0cf-d249-4d98-8d16-168ded32f9f1
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: decd258c5f4c965c79d9821c82671c6997ac9e3d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="avoiding-dbnetlib-exceptions"></a><span data-ttu-id="35992-102">DBNETLIB 例外の回避</span><span class="sxs-lookup"><span data-stu-id="35992-102">Avoiding DBNETLIB Exceptions</span></span>
<span data-ttu-id="35992-103">BizTalk Server ランタイムがメッセージ ボックス データベースまたは管理データベースのいずれかと通信できない場合、DBNetLib (データベース ネットワーク ライブラリ) エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="35992-103">DBNetLib (Database Network Library) errors occur when the BizTalk Server runtime is unable to communicate with either the MessageBox or Management databases.</span></span> <span data-ttu-id="35992-104">このエラーが発生すると、例外をキャッチする BizTalk Server ランタイム インスタンスがシャットダウンし、データベースが使用可能かどうかの確認が 1 分ごとに反復されます。</span><span class="sxs-lookup"><span data-stu-id="35992-104">When this occurs, the BizTalk Server runtime instance that catches the exception shuts down and then cycles every minute to check to see if the database is available.</span></span>  
  
 <span data-ttu-id="35992-105">DBNetLib エラーの最も一般的な原因は、(多数あると考えられる) メッセージ ボックス データベース サーバーの 1 つが極端なビジー状態になったときに、そのサーバーへの通信がなおも試みられ、DBNetLib 例外の原因となるタイムアウトが発生することです。</span><span class="sxs-lookup"><span data-stu-id="35992-105">The most common cause of a DBNetLib error is when one of the (possibly many) MessageBox database servers becomes extremely busy and further attempts to communicate with it result in a timeout, which causes a DBNetLib exception.</span></span>  
  
 <span data-ttu-id="35992-106">メッセージ ボックス データベースが単にビジー状態になる以外にも、メッセージ ボックス データベースをホストする BizTalk データベース サーバーが I/O (入力/出力) バインドであるときに、実稼働環境で DBNetLib エラーが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="35992-106">In addition to the case where the MessageBox database is simply very busy, the DBNetLib error can occur in a production environment when BizTalk database servers hosting one of more MessageBox databases become I/O (Input/Output) bound.</span></span>  
  
 <span data-ttu-id="35992-107">ここでは、DBNetLib エラーが誘発される条件と、それらのエラーを回避するための推奨事項について説明します。</span><span class="sxs-lookup"><span data-stu-id="35992-107">This topic describes conditions that can lead to DBNetLib errors and recommendations for avoiding these errors.</span></span>  
  
## <a name="cause-and-resolution-for-the-dbnetlib-error"></a><span data-ttu-id="35992-108">DBNetLib エラーの原因と解決方法</span><span class="sxs-lookup"><span data-stu-id="35992-108">Cause and Resolution for the DBNetLib error</span></span>  
  
### <a name="symptoms-of-a-dbnetlib-error"></a><span data-ttu-id="35992-109">DBNetLib エラーの現象</span><span class="sxs-lookup"><span data-stu-id="35992-109">Symptoms of a DBNetLib error</span></span>  
 <span data-ttu-id="35992-110">Microsoft BizTalk Server ホスト インスタンスが終了して自動的に再起動し、BizTalk Server アプリケーション ログに、以下のようなエラーが書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="35992-110">A Microsoft BizTalk Server host instance terminates and then restarts itself, and errors that are similar to the following are written to the BizTalk Server Application log:</span></span>  
  
```  
Event Type:Warning  
Event Source:BizTalk Server <version>  
Event Category:BizTalk Server <version>   
Event ID:5410  
Computer:BIZTALKSERVER  
Description:  
An error occurred that requires the BizTalk service to terminate. The most common causes are the following:  
 1) An unexpected out of memory error.  
 OR  
 2) An inability to connect or a loss of connectivity to one of the BizTalk databases.   
 The service will shutdown and auto-restart in 1 minute. If the problematic database remains unavailable, this cycle will repeat.  
  
 Error message: [DBNETLIB][ConnectionWrite (send()).]General network error. Check your network documentation.  
 Error source:    
  
 BizTalk host name: BizTalkHost  
 Windows service name: BTSSvc$BizTalkHost   
  
---------------------------------------------------------  
Event Type:Error  
Event Source:BizTalk Server <version>  
Event Category:BizTalk Server <version>   
Event ID:6913  
Computer:BIZTALKSERVER  
Description:  
An attempt to connect to "BizTalkMsgBoxDb" SQL Server database on server "SQLSERVER " failed.  
 Error: "[DBNETLIB][ConnectionWrite (send()).]General network error. Check your network documentation."  
```  
  
### <a name="biztalk-database-servers-hosting-messagebox-databases-becoming-io-bound"></a><span data-ttu-id="35992-111">メッセージ ボックス データベースをホストする BizTalk データベース サーバーが I/O バインドになる</span><span class="sxs-lookup"><span data-stu-id="35992-111">BizTalk database servers hosting MessageBox databases becoming I/O bound</span></span>  
 <span data-ttu-id="35992-112">BizTalk サーバーは、メッセージ ボックス データベースをホストするデータベース サーバーと直接通信し、機能します。</span><span class="sxs-lookup"><span data-stu-id="35992-112">BizTalk servers communicate and act directly with the database servers hosting the MessageBox databases.</span></span> <span data-ttu-id="35992-113">メッセージ ボックス データベースをホストするデータベース サーバーは、使用率が高くなり I/O (入力/出力) バインドの状態になると、応答を返さなくなる場合があります。</span><span class="sxs-lookup"><span data-stu-id="35992-113">If any of the database servers hosting the MessageBox databases get too consumed and gets into an I/O (Input/Output) bound situation, then it might become unresponsive.</span></span> <span data-ttu-id="35992-114">その結果、BizTalk サーバーの 1 つが、応答しないデータベース サーバーの 1 つとの接続を失って、DBNetLib エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="35992-114">One of the BizTalk servers might in turn lose connectivity with one of those database servers, and a DBNetLib error will occur.</span></span>  
  
 <span data-ttu-id="35992-115">マイクロソフトでのテストによると、使用率が高いデータベース サーバーの物理ディスクの "% Idle Time" が低下し続け、10% を下回ると I/O バインドになることがわかっています。</span><span class="sxs-lookup"><span data-stu-id="35992-115">Our tests show that a highly consumed database server becomes I/O bound when its physical disk’s "%Idle time" continues to drop and reaches below 10%.</span></span> <span data-ttu-id="35992-116">"% Idle Time" がこのレベルを下回るまで低下し続けている場合、データベース サーバーが応答しない状態に近づいていることを示しています。</span><span class="sxs-lookup"><span data-stu-id="35992-116">If the “%Idle time” continues to drop below that level, then this is an indication that your database server is likely to become unresponsive.</span></span>  
  
#### <a name="cause"></a><span data-ttu-id="35992-117">原因</span><span class="sxs-lookup"><span data-stu-id="35992-117">Cause</span></span>  
 <span data-ttu-id="35992-118">メッセージ ボックス データベースをホストするデータベース サーバーが I/O バインドになる原因はいくつかあります。次に、その一部を示します。</span><span class="sxs-lookup"><span data-stu-id="35992-118">There are several reasons that can cause the database servers hosting the MessageBox databases to become I/O bound, some of these are the following:</span></span>  
  
-   <span data-ttu-id="35992-119">メッセージ ボックス データベースをホストするデータベース コンピューターが、メモリ容量やプロセッサの数が少ない、プロセッサが低速など、仕様の低いハードウェアの制約を受けている場合。</span><span class="sxs-lookup"><span data-stu-id="35992-119">If the database machine hosting the MessageBox database is bound by low hardware specifications such as: low memory, number and speed of processors etc.</span></span>  
  
-   <span data-ttu-id="35992-120">メッセージ ボックス データベースをホストするデータベース コンピューターの物理ディスクを、使用率が高い他のデータベースと共有している場合。</span><span class="sxs-lookup"><span data-stu-id="35992-120">If the physical disk on the database machine hosting a MessageBox database is being shared by other highly consumed databases.</span></span> <span data-ttu-id="35992-121">(メッセージ ボックスを含む) 複数のデータベースの使用率が同時に高くなると、物理ディスクが I/O バインドになる場合があります。</span><span class="sxs-lookup"><span data-stu-id="35992-121">In cases when several databases (including the MessageBox) are being highly consumed at the same time, the physical disk can get into an I/O bound situation.</span></span>  
  
     <span data-ttu-id="35992-122">以下に、このような状況の例を示します。</span><span class="sxs-lookup"><span data-stu-id="35992-122">An example of such a situation is the following:</span></span>  
  
     <span data-ttu-id="35992-123">マイクロソフトでのテストによると、BizTalkDTADb データベースか BAM データベース、またはその両方をホストするデータベース サーバーで、物理ディスクの % Disk Read Time と % Disk Write Time が高いパーセンテージを示す場合があることがわかっています。</span><span class="sxs-lookup"><span data-stu-id="35992-123">Our tests show that the database server hosting the BizTalkDTADb and/or BAM databases sometimes consume high percentages of a physical disk’s %Disk Read and Write Times.</span></span> <span data-ttu-id="35992-124">メッセージ ボックス データベースをホストするデータベース サーバーのディスクを、BizTalkDTADb、BAM など、使用率が高い他のデータベースと共有しているとき、2 つのデータベースの使用率が同時に高くなった場合、データベース サーバーの物理ディスクが I/O バインドになり、応答を返さなくなる場合があります。</span><span class="sxs-lookup"><span data-stu-id="35992-124">When the database server disk that hosts a MessageBox database is being shared by another highly consumed database such as BizTalkDTADb or BAM, and if both databases are highly consumed simultaneously, they might cause the database server physical disk to become I/O bound and then unresponsive.</span></span>  
  
-   <span data-ttu-id="35992-125">BizTalkDTADb と 1 つ以上のメッセージ ボックス データベースがデータベース サーバーの同一の物理ディスクを共有している場合は、アーカイブと削除を頻繁に実行しないと、ディスクが I/O バインドになる場合があります。</span><span class="sxs-lookup"><span data-stu-id="35992-125">If BizTalkDTADb and one or more of the MessageBox databases are sharing the same physical disk on the database server, if archiving and purging is not being run frequently, the disk might become I/O bound.</span></span>  
  
#### <a name="resolution"></a><span data-ttu-id="35992-126">解決策</span><span class="sxs-lookup"><span data-stu-id="35992-126">Resolution</span></span>  
 <span data-ttu-id="35992-127">BizTalk メッセージ ボックスをホストするデータベース サーバーが、使用率が高まって応答を返さなくなる状況を回避します。</span><span class="sxs-lookup"><span data-stu-id="35992-127">Ensure the database server(s) hosting the BizTalk MessageBox(s) do not get into a situation where they become highly consumed and possibly unresponsive.</span></span>  
  
 <span data-ttu-id="35992-128">次に、サーバーのディスクの使用率が高まる主な原因の一部を、問題緩和の推奨事項と共に示します。</span><span class="sxs-lookup"><span data-stu-id="35992-128">Some of the primary causes of a server disk becoming highly consumed are listed below along with recommendations on how to mitigate this problem.</span></span>  
  
##### <a name="low-hardware-specs"></a><span data-ttu-id="35992-129">低いハードウェア仕様</span><span class="sxs-lookup"><span data-stu-id="35992-129">Low Hardware Specs</span></span>  
 <span data-ttu-id="35992-130">マイクロソフトでのテストによると、処理しようとしている負荷がハードウェアの仕様を上回るときに、サーバーの使用率が高まることがわかっています。</span><span class="sxs-lookup"><span data-stu-id="35992-130">Our tests show that the server starts getting more consumed when its hardware specifications cannot keep up with the amount of load it’s trying to process.</span></span> <span data-ttu-id="35992-131">ハードウェア仕様が低いと、データベースで発生するアクティビティの量によっては、システムにすぐに負荷がかかります。</span><span class="sxs-lookup"><span data-stu-id="35992-131">With lower hardware specs, the system gets overwhelmed quickly by the amount of activities happening on the databases.</span></span> <span data-ttu-id="35992-132">その結果、サーバーの % Disk Read Time と % Disk Write Time が安定せずに増加し続け、ディスクの % Idle Time が 10% を下回るまで減少し続けて、データベース サーバーが応答しなくなる場合があります。</span><span class="sxs-lookup"><span data-stu-id="35992-132">This might cause the server’s %Disk Read and Write Times to continue increasing without stabilizing, also the disk’s %Idle time to continue to decrease and become lower than 10%, and this might cause your database server to become unresponsive.</span></span>  
  
 <span data-ttu-id="35992-133">高負荷時にデータベース サーバーが応答しなくなることが判明した場合、BizTalk 展開のアクティビティの量と負荷に応じて、CPU やメモリの増設、SAN への接続などで、データベース サーバーをアップグレードすることを検討してください。</span><span class="sxs-lookup"><span data-stu-id="35992-133">Depending on the amount of activities and load you have on your BizTalk deployment, if you find that you are getting unresponsive database servers during to high loads, you should consider upgrading the following parts in your database servers: number of CPUs, memory, and connecting to a SAN.</span></span> <span data-ttu-id="35992-134">また、ハードウェアのうち、アップグレードを必要とするボトルネックが、(メモリ、CPU の数など) どの部分かを調査するため、適切な診断を行ってください。</span><span class="sxs-lookup"><span data-stu-id="35992-134">Of course, you should do the proper diagnosis to figure out which part (memory, number of CPUs etc.) is the bottleneck that needs to be upgraded in your hardware.</span></span>  
  
##### <a name="sharing-one-server-or-disk-for-more-than-one-group-of-biztalk-databases"></a><span data-ttu-id="35992-135">複数の BizTalk データベース グループによる 1 つのサーバーまたは 1 枚のディスクの共有</span><span class="sxs-lookup"><span data-stu-id="35992-135">Sharing one server or disk for more than one group of BizTalk databases</span></span>  
 <span data-ttu-id="35992-136">既に説明したとおり、BizTalk 追跡 (BizTalkDTADb) データベース、BAM データベースなど、メッセージ ボックス以外のデータベースは、サーバーの物理ディスクのサイクルを多く消費する場合があります。</span><span class="sxs-lookup"><span data-stu-id="35992-136">As mentioned previously, databases other than MessageBoxes, such as the BizTalk Tracking (BizTalkDTADb) database and BAM databases, might consume high cycles on a server’s physical disk.</span></span> <span data-ttu-id="35992-137">つまり、これらのデータベースがメッセージ ボックス データベースと同一の物理ディスクを共有する場合、ディスクが停止し、応答しなくなることがあるので、結果的に BizTalk サーバーがメッセージ ボックス データベースへの接続を失い、DBNetLib が発生します。</span><span class="sxs-lookup"><span data-stu-id="35992-137">So, if those databases happen to share the same physical disk with the MessageBox databases, then they might choke the disk and make it unresponsive, which again might cause BizTalk servers to loose connectivity with the MessageBox databases and thus hit DBNetLib.</span></span>  
  
 <span data-ttu-id="35992-138">サーバーの物理ディスクの使用率を上昇させることが予測されるデータベースは、BizTalk メッセージ ボックスから切り離し、別の物理ディスクに分ける (または、別のサーバーに分ける) ことを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="35992-138">It is highly recommended that you separate any database expected to have high consumption of the server’s physical disk from the BizTalk MessageBox(s), so they share different physical disks (or separate them on different servers).</span></span> <span data-ttu-id="35992-139">BizTalkDTADb データベースおよび BAM データベースを、メッセージ ボックスとは別の独自のドライブやサーバーに配置すること、およびメッセージ ボックス データベースが複数ある場合は、1 つずつ独自のディスクに配置することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="35992-139">It is recommended that you separate the BizTalkDTADb and BAM databases on their own separate drives/servers from the MessageBox(s), and it is also recommended to have each MessageBox database (in the case there is more than one) on it’s own disk.</span></span>  
  
##### <a name="archiving-and-purging"></a><span data-ttu-id="35992-140">アーカイブと削除</span><span class="sxs-lookup"><span data-stu-id="35992-140">Archiving and Purging</span></span>  
 <span data-ttu-id="35992-141">BizTalkDTADb データベースとメッセージ ボックス データベースが同一サーバーの同一ディスクを共有している場合、BizTalkDTADb データベースは、アーカイブと削除を定期的に行わない限り、無制限にサイズが増加します。</span><span class="sxs-lookup"><span data-stu-id="35992-141">In the case when you have BizTalkDTADb and MessageBox databases sharing the same disk on the same server, you must archive and purge your BizTalkDTADb databases regularly, otherwise they will grow indefinitely.</span></span>  
  
 <span data-ttu-id="35992-142">テストの結果、アーカイブと削除を定期的に行うことが推奨されますが、通常よりも高い負荷がかかる場合は、アーカイブと削除の実行頻度を増やすことを検討してください。</span><span class="sxs-lookup"><span data-stu-id="35992-142">Testing indicates that it is good practice to archive and purge periodically, but if you run under higher loads than normal then you might want to consider archiving and purging more frequently.</span></span> <span data-ttu-id="35992-143">BizTalkDTADb データベース サイズの増加を定期的にメンテナンスしないと、最終的にアーカイブと削除を実行したときに時間が非常にかかるうえ、実行中はデータベース サーバーの使用可能なリソースのほとんどが消費される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="35992-143">If the BizTalkDTADb database growth is not maintained regularly, then when these actions are finally performed they may take considerable time and consume most of the available database server resources while they are running.</span></span>