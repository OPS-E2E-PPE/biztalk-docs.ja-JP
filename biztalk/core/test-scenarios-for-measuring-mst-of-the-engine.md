---
title: エンジンの MST を測定するためのテスト シナリオ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e54667b9-7262-43c8-a013-9242eb062daf
caps.latest.revision: 28
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4fe9fd977563553e62d10675ee35caa673cf0c8e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998923"
---
# <a name="test-scenarios-for-measuring-mst-of-the-engine"></a><span data-ttu-id="aecfd-102">エンジンの MST を測定するためのテスト シナリオ</span><span class="sxs-lookup"><span data-stu-id="aecfd-102">Test Scenarios for Measuring MST of the Engine</span></span>
<span data-ttu-id="aecfd-103">このセクションでは、BizTalk システムを次の 3 つの負荷レベルで起動したときの効率性を測定するために実装したテスト シナリオについて説明します。</span><span class="sxs-lookup"><span data-stu-id="aecfd-103">This section describes a test scenario that was implemented to measure the effect of driving a BizTalk system at three different levels of load:</span></span>  
  
- <span data-ttu-id="aecfd-104">[維持可能なロード テスト](../core/sustainable-load-test.md)します。</span><span class="sxs-lookup"><span data-stu-id="aecfd-104">[Sustainable Load Test](../core/sustainable-load-test.md).</span></span> <span data-ttu-id="aecfd-105">維持可能なロードは、トピックに記載されているこれらのテストのために、[維持可能なパフォーマンスとは何ですか?](../core/what-is-sustainable-performance.md)します。</span><span class="sxs-lookup"><span data-stu-id="aecfd-105">For purposes of these tests, sustainable load is described in the topic [What Is Sustainable Performance?](../core/what-is-sustainable-performance.md).</span></span>  
  
- <span data-ttu-id="aecfd-106">[ロード テストをオーバー ドライブ](../core/overdrive-load-test.md)します。</span><span class="sxs-lookup"><span data-stu-id="aecfd-106">[Overdrive Load Test](../core/overdrive-load-test.md).</span></span> <span data-ttu-id="aecfd-107">オーバー ドライブ ロードは、MST を上回るを一貫性のある負荷として定義されます。</span><span class="sxs-lookup"><span data-stu-id="aecfd-107">Overdrive load is defined as a consistent load that exceeds MST.</span></span>  
  
- <span data-ttu-id="aecfd-108">[フラッド ゲート ロード テスト](../core/floodgate-load-test.md)します。</span><span class="sxs-lookup"><span data-stu-id="aecfd-108">[Floodgate Load Test](../core/floodgate-load-test.md).</span></span> <span data-ttu-id="aecfd-109">フラッド ゲート ロードは、断続的なピーク負荷の MST を超える負荷が低いとして定義されます。</span><span class="sxs-lookup"><span data-stu-id="aecfd-109">Floodgate load is defined as low load with intermittent peaks of load that exceed MST.</span></span>  
  
  <span data-ttu-id="aecfd-110">このトピックでは、テスト ハードウェアの構成、テスト シナリオ、および各テスト結果について説明します。</span><span class="sxs-lookup"><span data-stu-id="aecfd-110">This topic describes the test hardware configuration, the test scenarios, and discusses the findings of each of these tests.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="aecfd-111">読者は、このセクションに含まれる情報が発行日の時点で扱われた問題に関するマイクロソフトの現在の見解を示していることに注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aecfd-111">Readers should be aware that the information contained in this section represents the current view of Microsoft on the issues discussed as of the date of publication.</span></span> <span data-ttu-id="aecfd-112">市場の状況とテクノロジの変化に対応する必要があるため、マイクロソフトでは、発行日以降に示された情報の正確性は保証できません。</span><span class="sxs-lookup"><span data-stu-id="aecfd-112">Because we must respond to changing market conditions and technologies, Microsoft cannot guarantee the accuracy of any information presented after the date of publication.</span></span>  
  
## <a name="test-system-configuration"></a><span data-ttu-id="aecfd-113">テスト システム構成</span><span class="sxs-lookup"><span data-stu-id="aecfd-113">Test System Configuration</span></span>  
 <span data-ttu-id="aecfd-114">このテスト シナリオで使用するハードウェアを次に示します。</span><span class="sxs-lookup"><span data-stu-id="aecfd-114">The following hardware was used for this test scenario:</span></span>  
  
- <span data-ttu-id="aecfd-115">**6 つの BizTalk Server**します。</span><span class="sxs-lookup"><span data-stu-id="aecfd-115">**Six BizTalk Servers**.</span></span> <span data-ttu-id="aecfd-116">それぞれデュアル 3 GHz プロセッサおよび 2 GB RAM を搭載。</span><span class="sxs-lookup"><span data-stu-id="aecfd-116">Each equipped with dual 3GHz processors and 2GB of RAM.</span></span> <span data-ttu-id="aecfd-117">各サーバーはローカル ディスクを使用しています。</span><span class="sxs-lookup"><span data-stu-id="aecfd-117">Each server is using local disks.</span></span> <span data-ttu-id="aecfd-118">2 台の BizTalk Servers に受信ホストのインスタンス、2 台に送信ホストのインスタンス、2 台にオーケストレーションの処理に使用するホストのインスタンスを構成します。</span><span class="sxs-lookup"><span data-stu-id="aecfd-118">Two of the BizTalk Servers are configured with an instance of the receiving host, two are configured with an instance of the sending host, and two are configured with an instance of the host used for processing orchestrations.</span></span>  
  
- <span data-ttu-id="aecfd-119">**マスター メッセージ ボックス データベースと非メッセージ ボックス データベースの 1 つの SQL Server**します。</span><span class="sxs-lookup"><span data-stu-id="aecfd-119">**One SQL Server for the master MessageBox database and the non-MessageBox databases**.</span></span> <span data-ttu-id="aecfd-120">8 個の 2 GHz プロセッサと 4 GB RAM を搭載。</span><span class="sxs-lookup"><span data-stu-id="aecfd-120">Equipped with eight 2GHz processors and 4 GB of RAM.</span></span> <span data-ttu-id="aecfd-121">このサーバーはファイバー経由で高速 SAN ディスク サブシステムに接続されています。</span><span class="sxs-lookup"><span data-stu-id="aecfd-121">This server is connected to a fast SAN disk subsystem via fiber.</span></span> <span data-ttu-id="aecfd-122">メッセージの公開は無効にしてあります。</span><span class="sxs-lookup"><span data-stu-id="aecfd-122">Message publication is disabled.</span></span>  
  
- <span data-ttu-id="aecfd-123">**次の 3 つの SQL Server のメッセージ ボックス データベースに公開される**します。</span><span class="sxs-lookup"><span data-stu-id="aecfd-123">**Three SQL Servers for the Messagebox databases that are being published to**.</span></span> <span data-ttu-id="aecfd-124">4 個の 2 GHz プロセッサと 4 GB RAM を搭載。</span><span class="sxs-lookup"><span data-stu-id="aecfd-124">Equipped with four 2GHz processors and 4GB of RAM.</span></span> <span data-ttu-id="aecfd-125">これらのサーバーは、それぞれファイバー経由で高速 SAN ディスク サブシステムに接続されています。</span><span class="sxs-lookup"><span data-stu-id="aecfd-125">These servers are each connected to a fast SAN disk subsystem via fiber.</span></span> <span data-ttu-id="aecfd-126">メッセージ ボックス データベースのデータおよびトランザクション ログ ファイルは、独立したストレージ エリア ネットワーク (SAN) に論理単位数 (LUN) として格納されています。</span><span class="sxs-lookup"><span data-stu-id="aecfd-126">The data and transaction log files for the MessageBox database are on separate storage area network (SAN) logical unit numbers (LUNs).</span></span>  
  
- <span data-ttu-id="aecfd-127">**ロード ドライバー クライアント コンピューター**します。</span><span class="sxs-lookup"><span data-stu-id="aecfd-127">**Load driver client machine**.</span></span> <span data-ttu-id="aecfd-128">デュアル 3 GHz プロセッサおよび 2 GB RAM を搭載。</span><span class="sxs-lookup"><span data-stu-id="aecfd-128">Equipped with dual 3GHz processors and 2GB of RAM.</span></span> <span data-ttu-id="aecfd-129">このサーバーは、BizTalk システムをテストするための負荷を生成するときに使用します。</span><span class="sxs-lookup"><span data-stu-id="aecfd-129">This server was used to generate the load for testing the BizTalk system.</span></span>  
  
  <span data-ttu-id="aecfd-130">ロード テストで使用するトポロジを次の図に示します。</span><span class="sxs-lookup"><span data-stu-id="aecfd-130">The topology used for the load tests is illustrated below.</span></span>  
  
  <span data-ttu-id="aecfd-131">**ロード テストに使用されるトポロジ**</span><span class="sxs-lookup"><span data-stu-id="aecfd-131">**Topology used for load tests**</span></span>  
  
  <span data-ttu-id="aecfd-132">![BizTalk Server のロード テストのハードウェア トポロジ](../core/media/bts06-msttopology.gif "BTS06_MSTTopology")</span><span class="sxs-lookup"><span data-stu-id="aecfd-132">![Hardware topology for BizTalk Server load testing](../core/media/bts06-msttopology.gif "BTS06_MSTTopology")</span></span>  
  
## <a name="the-test-scenario"></a><span data-ttu-id="aecfd-133">テスト シナリオ</span><span class="sxs-lookup"><span data-stu-id="aecfd-133">The Test Scenario</span></span>  
 <span data-ttu-id="aecfd-134">テスト シナリオは非常に単純です。</span><span class="sxs-lookup"><span data-stu-id="aecfd-134">The test scenario is very simple.</span></span> <span data-ttu-id="aecfd-135">負荷生成ツール LoadGen 2007 をロード ドライバー サーバーにインストールし、ファイル アダプターによって監視される共有に、ファイルのコピーを送信します。</span><span class="sxs-lookup"><span data-stu-id="aecfd-135">The load generation tool, LoadGen 2007, was installed on the load driver server and was used to send copies of a file to shares monitored by the file adapter.</span></span> <span data-ttu-id="aecfd-136">負荷生成ツールにより、入力ファイル インスタンスのコピーがファイル共有に均等に配布されます。</span><span class="sxs-lookup"><span data-stu-id="aecfd-136">The load generation tool distributes copies of the input file instance evenly across the file shares.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="aecfd-137">ダウンロード[LoadGen](https://www.microsoft.com/download/details.aspx?id=14925)します。</span><span class="sxs-lookup"><span data-stu-id="aecfd-137">Download [LoadGen](https://www.microsoft.com/download/details.aspx?id=14925).</span></span> <span data-ttu-id="aecfd-138">このツールの以前のバージョン、BizTalk Server 2004 負荷生成ツールがダウンロードできる[ http://go.microsoft.com/fwlink/?linkid=108999](http://go.microsoft.com/fwlink/?linkid=108999)します。</span><span class="sxs-lookup"><span data-stu-id="aecfd-138">The previous version of this tool, the BizTalk Server 2004 Load Generation Tool is available for download at [http://go.microsoft.com/fwlink/?linkid=108999](http://go.microsoft.com/fwlink/?linkid=108999).</span></span> <span data-ttu-id="aecfd-139">MSMQ アダプターでの LoadGen の使用方法の詳細については、次を参照してください。 [MSMQ での LoadGen 2007 を使用して](../core/using-loadgen-2007-with-msmq.md)します。</span><span class="sxs-lookup"><span data-stu-id="aecfd-139">For information about using LoadGen with the MSMQ adapter, see [Using LoadGen 2007 with MSMQ](../core/using-loadgen-2007-with-msmq.md).</span></span>  
  
 <span data-ttu-id="aecfd-140">BizTalk ファイル アダプターは、ファイル共有を監視してメッセージをメッセージ ボックスに公開するように構成されています。</span><span class="sxs-lookup"><span data-stu-id="aecfd-140">The BizTalk File adapter is configured to monitor the file shares and publish the messages into the MessageBox.</span></span> <span data-ttu-id="aecfd-141">受信図形と送信図形のみを含んでいる簡単なオーケストレーションで、公開されたメッセージをサブスクライブします。</span><span class="sxs-lookup"><span data-stu-id="aecfd-141">A simple orchestration that contains only a receive shape and a send shape subscribes to the published message.</span></span> <span data-ttu-id="aecfd-142">オーケストレーションによってメッセージ ボックスに公開されたメッセージは、ファイル送信ポートで取得されて共通の共有に送信され、SAN で定義されます。</span><span class="sxs-lookup"><span data-stu-id="aecfd-142">Messages that are published back into the MessageBox by the orchestration are picked up by a file send port and sent to a common share, defined on the SAN.</span></span> <span data-ttu-id="aecfd-143">出力 SAN 共有に到着したファイルは、テストの実行中にファイルがこの共有に蓄積されるのを回避するために、直ちに削除されます。</span><span class="sxs-lookup"><span data-stu-id="aecfd-143">Files arriving on the output SAN share are immediately deleted in order to avoid file buildup on that share during long test runs.</span></span>  
  
 <span data-ttu-id="aecfd-144">シナリオには、受信場所、オーケストレーション、送信ポート、および追跡用にそれぞれ 1 つずつ合計 4 つのホストが定義されました。</span><span class="sxs-lookup"><span data-stu-id="aecfd-144">Four hosts were defined for the scenario, one each for the receive location, the orchestrations, the send port, and for tracking.</span></span> <span data-ttu-id="aecfd-145">エンジン バックログの動作を観察するために、テストの実行中は追跡をすべて無効にします。</span><span class="sxs-lookup"><span data-stu-id="aecfd-145">For the purposes of observing engine backlog behavior, tracking is completely turned off during the test runs.</span></span> <span data-ttu-id="aecfd-146">追跡は既定でパイプラインとオーケストレーションでのみ有効になっているため、BizTalk 管理では使用するオーケストレーションとパイプラインに対して追跡を明示的に無効にします。</span><span class="sxs-lookup"><span data-stu-id="aecfd-146">Tracking is only enabled for pipelines and orchestrations by default so tracking was explicitly turned off in the BizTalk Administrator for the orchestration and pipeline that was used.</span></span>  
  
 <span data-ttu-id="aecfd-147">これらのテストでは、追跡を無効にして主要なメッセージ ボックスの動作を分離するため、追跡ホストのインスタンスは作成されません。</span><span class="sxs-lookup"><span data-stu-id="aecfd-147">No instances of the tracking host were created since tracking was turned off to isolate core MessageBox behavior for these tests.</span></span>  
  
 <span data-ttu-id="aecfd-148">使用するスキーマは単純で、テストに使用したインスタンス ファイルのサイズはすべて 10 KB です。</span><span class="sxs-lookup"><span data-stu-id="aecfd-148">A simple schema was used and the instance files used for the test were all 10KB in size.</span></span> <span data-ttu-id="aecfd-149">受信ドキュメントには XMLReceive パイプラインを使用しています。テスト シナリオを単純にし、メッセージ ボックスの動作の観察に重点を置くため、マッピング コンポーネントや送信コンポーネントを使用していません。</span><span class="sxs-lookup"><span data-stu-id="aecfd-149">The XMLReceive pipeline was used for inbound documents and no mapping components or outbound components were used in order to keep the test scenario simple and focus observations on the behavior of the MessageBox.</span></span>  
  
## <a name="parameters-measured-in-the-test"></a><span data-ttu-id="aecfd-150">テストで測定するパラメーター</span><span class="sxs-lookup"><span data-stu-id="aecfd-150">Parameters Measured in the Test</span></span>  
 <span data-ttu-id="aecfd-151">このテストで測定するパラメーターは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="aecfd-151">The parameters measured in this test are as follows:</span></span>  
  
 <span data-ttu-id="aecfd-152">**測定するプライマリ テスト パラメーター**</span><span class="sxs-lookup"><span data-stu-id="aecfd-152">**Primary test parameters measured**</span></span>  
  
 <span data-ttu-id="aecfd-153">以下のパラメーターは、MST を測定するときに使用するプライマリ インジケーターです。</span><span class="sxs-lookup"><span data-stu-id="aecfd-153">The following parameters are the primary indicators used when measuring MST:</span></span>  
  
- <span data-ttu-id="aecfd-154">メッセージ ボックス バックログによって測定される、**スプール サイズ**カウンターで利用できる、 **Counters**パフォーマンス オブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="aecfd-154">The MessageBox backlog as measured by the **Spool Size** counter that is available with the **BizTalk:MessageBox:General Counters** performance object.</span></span> <span data-ttu-id="aecfd-155">メッセージ ボックス バックログは持続性を示す重要なインジケーターです。</span><span class="sxs-lookup"><span data-stu-id="aecfd-155">Messagebox backlog is a key indicator of sustainability.</span></span> <span data-ttu-id="aecfd-156">メッセージ ボックス バックログが無限に増え続けると、必ず問題が発生します。</span><span class="sxs-lookup"><span data-stu-id="aecfd-156">Clearly, MessageBox backlog cannot continue to grow indefinitely without eventually running into problems.</span></span> <span data-ttu-id="aecfd-157">そのため、メッセージ ボックス データベース バックログの深さを長期間監視して、持続性を評価します。</span><span class="sxs-lookup"><span data-stu-id="aecfd-157">So, the depth of the MessageBox database backlog, monitored over time, is used to evaluate sustainability.</span></span>  
  
   <span data-ttu-id="aecfd-158">という名前のメッセージ ボックス テーブル**スプール**システムで各メッセージのレコードが含まれています (アクティブかまたは収集ガベージを待機しています)。</span><span class="sxs-lookup"><span data-stu-id="aecfd-158">The MessageBox table named **spool** contains a record for each message in the system (active or waiting to be garbage collected).</span></span> <span data-ttu-id="aecfd-159">このテーブル内の行数や 1 秒間に受信されるメッセージ数を監視しながら、システム負荷を増やすと簡単に維持可能な最大スループットを測定できます。</span><span class="sxs-lookup"><span data-stu-id="aecfd-159">Monitoring the number of rows in this table, and the number of messages received per second, while increasing system load provides an easy way to measure the maximum sustainable throughput.</span></span> <span data-ttu-id="aecfd-160">この測定値と呼ばれることも、**テーブルの深さのスプール**または**スプールの深さ**します。</span><span class="sxs-lookup"><span data-stu-id="aecfd-160">This measurement is also referred to as the **spool table depth** or **spool depth**.</span></span>  
  
- <span data-ttu-id="aecfd-161">測定した 1 秒あたりに受信されたドキュメントの数、**受信/秒をドキュメント**カウンターで利用できる、 **BizTalk: メッセージング**パフォーマンス オブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="aecfd-161">The number of documents received per second as measured by the **Documents received/Sec** counter that is available with the **BizTalk:Messaging** performance object.</span></span>  
  
  <span data-ttu-id="aecfd-162">**測定するセカンダリ テスト パラメーター**</span><span class="sxs-lookup"><span data-stu-id="aecfd-162">**Secondary test parameters measured**</span></span>  
  
  <span data-ttu-id="aecfd-163">次のパラメーターは、MST を測定するときに評価されるセカンダリ インジケーターです。</span><span class="sxs-lookup"><span data-stu-id="aecfd-163">The following parameters are secondary indicators that can be evaluated when measuring MST.</span></span> <span data-ttu-id="aecfd-164">これらのパラメーターは、スプールの深さや 1 秒あたりの受信ドキュメント数というプライマリ インジケーターに影響を与える場合があります。</span><span class="sxs-lookup"><span data-stu-id="aecfd-164">These parameters may impact the primary indicators of spool depth and the number of documents received per second.</span></span>  
  
- <span data-ttu-id="aecfd-165">物理ディスクのアイドル状態、メッセージ ボックス データとトランザクションのファイル ディスクによって測定される時間、 **% アイドル時間**カウンターで使用可能な**LogicalDisk**パフォーマンス オブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="aecfd-165">The physical disk idle time for the MessageBox data and transaction file disk as measured by the **%Idle Time** counter available with the **LogicalDisk** performance object.</span></span>  
  
- <span data-ttu-id="aecfd-166">によって測定されるメッセージ ボックス サーバーの CPU 使用率 (%)、 **% Processor Time**カウンターで使用可能な**プロセッサ**パフォーマンス オブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="aecfd-166">The CPU utilization (%) for the MessageBox server as measured by the **%Processor Time** counter available with the **Processor** performance object.</span></span>  
  
- <span data-ttu-id="aecfd-167">メッセージ ボックス データベースで 1 秒あたりのロック タイムアウトはデータベースによって測定される、 **Lock timeouts/sec**カウンターで使用可能な**SQLServer:Locks**パフォーマンス オブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="aecfd-167">The lock timeouts per second on the MessageBox database as measured by the **Lock Timeouts/sec** counter available with the **SQLServer:Locks** performance object.</span></span>  
  
- <span data-ttu-id="aecfd-168">削除されたメッセージに関連付けられたメッセージ ボックス テーブルをクリーンアップする SQL エージェント ジョブの直前のジョブ実行時間 (秒単位)。</span><span class="sxs-lookup"><span data-stu-id="aecfd-168">The time in seconds for the most recent run of the SQL agent job that cleans up message box tables associated with removed messages.</span></span> <span data-ttu-id="aecfd-169">計測されるかによって、 **MsgBox Msg Cleanup(Purge Jobs)** カウンターで使用可能な**Counters**パフォーマンス オブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="aecfd-169">This is measured by the **MsgBox Msg Cleanup(Purge Jobs)** counter available with the **BizTalk:MessageBox:General Counters** performance object.</span></span>  
  
- <span data-ttu-id="aecfd-170">削除されたメッセージ部分に関連付けられたメッセージ ボックス テーブルをクリーンアップする SQL エージェント ジョブの直前のジョブ実行時間 (秒単位)。</span><span class="sxs-lookup"><span data-stu-id="aecfd-170">The time in seconds for the most recent run of the SQL agent job which cleans up message box tables associated with removed message parts.</span></span> <span data-ttu-id="aecfd-171">計測されるかによって、 **MsgBox パーツ Cleanup(Purge Jobs)** カウンターで使用可能な**Counters**パフォーマンス オブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="aecfd-171">This is measured by the **MsgBox Parts Cleanup(Purge Jobs)** counter available with the **BizTalk:MessageBox:General Counters** performance object.</span></span>  
  
  <span data-ttu-id="aecfd-172">維持可能な最大スループットを特定するテストを行う最には、スプール テーブルが無制限に拡大し始める時点まで入力負荷を増やします。</span><span class="sxs-lookup"><span data-stu-id="aecfd-172">When testing to determine the maximum sustainable throughput, input load was increased up to the point that the spool table started to grow indefinitely.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="aecfd-173">負荷をいくら生成してもスプール テーブルが無制限に拡大しない場合、システムで最も低速な部分は処理/送信側ではなく、受信側であるということになります。</span><span class="sxs-lookup"><span data-stu-id="aecfd-173">If you are unable to generate enough load to cause the spool table to grow indefinitely, it simply means that the slowest part of your system is on the receive side, rather than the processing/send side.</span></span>  
  

## <a name="next"></a><span data-ttu-id="aecfd-174">Next</span><span class="sxs-lookup"><span data-stu-id="aecfd-174">Next</span></span>
  
-   [<span data-ttu-id="aecfd-175">Microsoft BizTalk LoadGen 2007 ツールを使用</span><span class="sxs-lookup"><span data-stu-id="aecfd-175">Using the Microsoft BizTalk LoadGen 2007 Tool</span></span>](../core/using-the-microsoft-biztalk-loadgen-2007-tool.md)  
  
-   [<span data-ttu-id="aecfd-176">維持可能なロード テスト</span><span class="sxs-lookup"><span data-stu-id="aecfd-176">Sustainable Load Test</span></span>](../core/sustainable-load-test.md)  
  
-   [<span data-ttu-id="aecfd-177">オーバードライブ ロード テスト</span><span class="sxs-lookup"><span data-stu-id="aecfd-177">Overdrive Load Test</span></span>](../core/overdrive-load-test.md)  
  
-   [<span data-ttu-id="aecfd-178">フラッドゲート ロード テスト</span><span class="sxs-lookup"><span data-stu-id="aecfd-178">Floodgate Load Test</span></span>](../core/floodgate-load-test.md)