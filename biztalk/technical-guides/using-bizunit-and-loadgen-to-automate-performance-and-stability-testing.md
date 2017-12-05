---
title: "パフォーマンスと安定性テストを自動化するための BizUnit および LoadGen を使用して |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 73c2a97a-6256-4010-8374-433017cb15d4
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e84fcd29af6b698713623fbca556d988e037d8c1
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="using-bizunit-and-loadgen-to-automate-performance-and-stability-testing"></a><span data-ttu-id="69554-102">パフォーマンスと安定性テストを自動化するための BizUnit および LoadGen を使用します。</span><span class="sxs-lookup"><span data-stu-id="69554-102">Using BizUnit and LoadGen to Automate Performance and Stability Testing</span></span>
<span data-ttu-id="69554-103">このトピックでは、パフォーマンスと安定性は、BizTalk Server ソリューションのテストを自動化するための BizUnit で Microsoft BizTalk LoadGen 2007 ツールを使用する方法に関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="69554-103">This topic provides information about how to use the Microsoft BizTalk LoadGen 2007 tool with BizUnit to automate performance and stability testing of a BizTalk Server solution.</span></span>  
  
## <a name="biztalk-server-performance-testing-step-by-step"></a><span data-ttu-id="69554-104">BizTalk Server のパフォーマンス テスト、詳細な手順</span><span class="sxs-lookup"><span data-stu-id="69554-104">BizTalk Server performance testing, step-by-step</span></span>  
 <span data-ttu-id="69554-105">BizTalk Server のパフォーマンス テストを自動化する方法を調査する前にどのような手順は、パフォーマンス テストで通常実行されるかを理解すると便利です。</span><span class="sxs-lookup"><span data-stu-id="69554-105">Before investigating how to automate BizTalk Server performance testing, it is useful to know what steps are typically performed in a performance test.</span></span> <span data-ttu-id="69554-106">次の手順には、プロセスのテスト「標準」BizTalk Server のパフォーマンスの代表者がいます。</span><span class="sxs-lookup"><span data-stu-id="69554-106">The following steps are representative of a “typical” BizTalk Server performance testing process:</span></span>  
  
1.  <span data-ttu-id="69554-107">結果とデータを収集、たとえば、イベント ログ、トレース ログ、パフォーマンス モニターのデータを格納するテストの結果ディレクトリを作成します。</span><span class="sxs-lookup"><span data-stu-id="69554-107">Create a test results directory to store results and data collected, for example, event logs, trace logs, Performance Monitor data.</span></span>  
  
2.  <span data-ttu-id="69554-108">テスト環境内のすべてのサーバー上のイベント ログをオフにします。</span><span class="sxs-lookup"><span data-stu-id="69554-108">Clear the event logs on all servers within the test environment.</span></span>  
  
3.  <span data-ttu-id="69554-109">すべての BizTalk ホスト インスタンスを停止します。</span><span class="sxs-lookup"><span data-stu-id="69554-109">Stop all BizTalk host instances.</span></span>  
  
4.  <span data-ttu-id="69554-110">SOAP および HTTP 受信アダプター ハンドラーなど、BizTalk 分離ホストを実行しているすべての IIS インスタンスを停止します。</span><span class="sxs-lookup"><span data-stu-id="69554-110">Stop any IIS instances that are running isolated BizTalk hosts such as the SOAP and HTTP receive adapter handlers.</span></span>  
  
5.  <span data-ttu-id="69554-111">BizTalk Server を実行しているコンピューターで使用される SQL Server のすべてのインスタンスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="69554-111">Restart all instances of SQL Server used by the computers running BizTalk Server.</span></span>  
  
6.  <span data-ttu-id="69554-112">以前のテスト実行から残されたデータがないことを確認するメッセージ ボックス データベースをクリーンアップします。</span><span class="sxs-lookup"><span data-stu-id="69554-112">Clean up the MessageBox database to ensure that there is no leftover data from previous tests runs.</span></span> <span data-ttu-id="69554-113">これは、機能は、残されたデータは、テスト結果をゆがめる可能性がありますので重要です。</span><span class="sxs-lookup"><span data-stu-id="69554-113">This is important because any leftover data could skew test results.</span></span>  
  
7.  <span data-ttu-id="69554-114">BizTalk ホスト インスタンスを起動します。</span><span class="sxs-lookup"><span data-stu-id="69554-114">Start the BizTalk host instances.</span></span>  
  
8.  <span data-ttu-id="69554-115">テスト環境のすべてのサーバーでは、関連するパフォーマンス モニター カウンターを開始します。</span><span class="sxs-lookup"><span data-stu-id="69554-115">Start the relevant Performance Monitor counters on all servers in the test environment.</span></span>  
  
9. <span data-ttu-id="69554-116">システム キャッシュを初期化するためにシステムで「準備」のメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="69554-116">Send “priming” messages through the system to initialize the system caches.</span></span>  
  
10. <span data-ttu-id="69554-117">準備メッセージが処理された後は、SQL Server のテスト結果のデータベースにテストの開始時刻を追跡します。</span><span class="sxs-lookup"><span data-stu-id="69554-117">After the priming messages have been processed, track the test start time in a SQL Server test results database.</span></span>  
  
11. <span data-ttu-id="69554-118">すべての LoadGen のテスト エージェントを起動して、パフォーマンス テストを開始します。</span><span class="sxs-lookup"><span data-stu-id="69554-118">Start the performance test by starting all of the LoadGen test agents.</span></span>  
  
12. <span data-ttu-id="69554-119">テストが完了するまで待機 – 多くの場合、これ行う体系的にホスト キューの長さなどのパフォーマンス モニター カウンターの値を測定します。</span><span class="sxs-lookup"><span data-stu-id="69554-119">Wait for the test to complete – often this can be done systematically by measuring the value of a Performance Monitor counter such as host queue length.</span></span>  
  
13. <span data-ttu-id="69554-120">結果のデータベースを SQL テストにおけるテスト終了時間を追跡します。</span><span class="sxs-lookup"><span data-stu-id="69554-120">Track test end time in a SQL test results database.</span></span>  
  
14. <span data-ttu-id="69554-121">テスト環境のすべてのサーバー上には、関連するパフォーマンス モニター カウンターを停止します。</span><span class="sxs-lookup"><span data-stu-id="69554-121">Stop the relevant Performance Monitor counters on all servers in the test environment.</span></span>  
  
15. <span data-ttu-id="69554-122">先ほど作成したテストの結果ディレクトリへのテスト データを保存します。</span><span class="sxs-lookup"><span data-stu-id="69554-122">Save the test data to the test results directory that was created earlier.</span></span>  
  
16. <span data-ttu-id="69554-123">次のテストの実行のために必要なクリーンアップを実行します。</span><span class="sxs-lookup"><span data-stu-id="69554-123">Perform any necessary cleanup for the next test run.</span></span>  
  
 <span data-ttu-id="69554-124">上記の手順のいずれかの各は、BizUnit を使用して自動化できます。</span><span class="sxs-lookup"><span data-stu-id="69554-124">Each and every one of the steps just listed can be automated using BizUnit.</span></span> <span data-ttu-id="69554-125">BizUnit は、既存のテスト ステップ資産を利用するなど、迅速かつ簡単に生成できます、自動化されたパフォーマンス テスト、BizTalk Server ソリューションをします。</span><span class="sxs-lookup"><span data-stu-id="69554-125">By utilizing the existing test step assets that BizUnit provides, you can quickly and easily generate an automated performance test for a BizTalk Server solution.</span></span> <span data-ttu-id="69554-126">パフォーマンスのための BizUnit を使用してテストを自動化することの主な利点の 1 つは、つまり、結果の分析の準備ができて毎朝夜間: テストを実行する柔軟性です。</span><span class="sxs-lookup"><span data-stu-id="69554-126">One of the primary benefits of automating performance testing by using BizUnit is the flexibility to run tests overnight – meaning that the results are ready for analysis in the morning.</span></span> <span data-ttu-id="69554-127">これにより、プロジェクト チームでのパフォーマンス テストの負荷が大幅に減少します。</span><span class="sxs-lookup"><span data-stu-id="69554-127">This greatly reduces the burden of performance testing on a project team.</span></span>  
  
## <a name="the-microsoft-biztalk-loadgen-2007-tool"></a><span data-ttu-id="69554-128">Microsoft BizTalk LoadGen 2007 ツール</span><span class="sxs-lookup"><span data-stu-id="69554-128">The Microsoft BizTalk LoadGen 2007 tool</span></span>  
 <span data-ttu-id="69554-129">BizTalk LoadGen 2007 ツール (LoadGen) は、ロード テストのストレスおよびパフォーマンスのテストをチームで BizTalk Server 2006 製品グループによって開発されたツールです。</span><span class="sxs-lookup"><span data-stu-id="69554-129">The BizTalk LoadGen 2007 tool (LoadGen) is a load testing tool that was developed by the Stress and Performance Testing team in the BizTalk Server 2006 product group.</span></span> <span data-ttu-id="69554-130">LoadGen は、すばやく、簡単かつ確実に実稼働レベルのメッセージのボリュームをシミュレートするロード テストを定義するように設計されました。</span><span class="sxs-lookup"><span data-stu-id="69554-130">LoadGen was designed to quickly, easily, and reliably define load tests that simulate production level message volumes.</span></span> <span data-ttu-id="69554-131">LoadGen は、マルチ スレッド、構成に基づく、複数のトランスポートをサポートします。</span><span class="sxs-lookup"><span data-stu-id="69554-131">LoadGen is multi-threaded, configuration-driven, and supports multiple transports.</span></span> <span data-ttu-id="69554-132">製品の BizTalk グループを毎日; LoadGen を使用します。したがって、高度な確実なツールがある、持続性のある目的のために合わせてとさまざまな BizTalk シナリオをシミュレートすることができます。</span><span class="sxs-lookup"><span data-stu-id="69554-132">The BizTalk product group uses LoadGen on a daily basis; therefore you can have a high degree of confidence that the tool is durable, fit for the purpose, and able to simulate a wide variety of BizTalk scenarios.</span></span>  
  
 <span data-ttu-id="69554-133">LoadGen は 3 つの層で構成されているモジュール形式デザイン:**プレゼンテーション**、 **framework**と**コンポーネント**です。</span><span class="sxs-lookup"><span data-stu-id="69554-133">LoadGen employs a modular design that consists of three layers: **presentation**, **framework** and **component**.</span></span> <span data-ttu-id="69554-134">プレゼンテーション層は、コマンド ライン ドライバーを促進するために、フレームワークで構成されます。</span><span class="sxs-lookup"><span data-stu-id="69554-134">The presentation layer consists of a command-line driver, which is responsible for driving the framework.</span></span> <span data-ttu-id="69554-135">Framework レイヤーは、構成ファイルを読み取ります、その中に指定されたコンポーネントを実行します。</span><span class="sxs-lookup"><span data-stu-id="69554-135">The framework layer reads a configuration file and then executes the components specified therein.</span></span> <span data-ttu-id="69554-136">コンポーネントの層は、3 種類のコンポーネントで構成されます:**ジェネレーターを読み込めません**、**作成者をメッセージ**と**コント ローラーのスロットル**です。</span><span class="sxs-lookup"><span data-stu-id="69554-136">The component layer consists of three types of components: **load generators**, **message creators** and **throttle controllers**.</span></span> <span data-ttu-id="69554-137">これらの各コンポーネントは、独自に作成して、シナリオのニーズに対応する LoadGen に接続できるように、拡張できます。</span><span class="sxs-lookup"><span data-stu-id="69554-137">Each of these components is extensible, so you can create your own and plug them into LoadGen to address the needs of your scenario.</span></span> <span data-ttu-id="69554-138">LoadGen は、BizTalk Server の製品グループによって開発された、ために、ボックスのコンポーネントがほとんどのロード テスト要件を満たすことがあります。</span><span class="sxs-lookup"><span data-stu-id="69554-138">Because LoadGen was developed by the BizTalk Server product group, you should find that the out-of-the-box components will fulfill most of your load testing requirements.</span></span> <span data-ttu-id="69554-139">これらの各コンポーネントについてより詳細には、ここで説明します。</span><span class="sxs-lookup"><span data-stu-id="69554-139">Each of these components is described in greater detail here.</span></span>  
  
-   <span data-ttu-id="69554-140">**ジェネレーターを読み込めません**特定のトランスポート経由でメッセージを送信する役割を担当します。</span><span class="sxs-lookup"><span data-stu-id="69554-140">**Load generators** are responsible for transmitting messages via a particular transport.</span></span> <span data-ttu-id="69554-141">次のトランスポートは、ロード ジェネレーターが用意されています。</span><span class="sxs-lookup"><span data-stu-id="69554-141">Load generators are provided for the following transports:</span></span>  
  
    -   <span data-ttu-id="69554-142">ファイル</span><span class="sxs-lookup"><span data-stu-id="69554-142">File</span></span>  
  
    -   <span data-ttu-id="69554-143">HTTP</span><span class="sxs-lookup"><span data-stu-id="69554-143">HTTP</span></span>  
  
    -   <span data-ttu-id="69554-144">MQSeries</span><span class="sxs-lookup"><span data-stu-id="69554-144">MQSeries</span></span>  
  
    -   <span data-ttu-id="69554-145">MSMQLarge</span><span class="sxs-lookup"><span data-stu-id="69554-145">MSMQLarge</span></span>  
  
    -   <span data-ttu-id="69554-146">MSMQ (MSMQ)</span><span class="sxs-lookup"><span data-stu-id="69554-146">MSMQ</span></span>  
  
    -   <span data-ttu-id="69554-147">SOAP</span><span class="sxs-lookup"><span data-stu-id="69554-147">SOAP</span></span>  
  
    -   <span data-ttu-id="69554-148">Web Services Enhancements (WSE)</span><span class="sxs-lookup"><span data-stu-id="69554-148">Web Services Enhancements (WSE)</span></span>  
  
    -   <span data-ttu-id="69554-149">Windows SharePoint Services (WSS)</span><span class="sxs-lookup"><span data-stu-id="69554-149">Windows SharePoint Services (WSS)</span></span>  
  
    -   <span data-ttu-id="69554-150">Windows Communication Foundation (WCF)</span><span class="sxs-lookup"><span data-stu-id="69554-150">Windows Communication Foundation (WCF)</span></span>  
  
-   <span data-ttu-id="69554-151">**メッセージの作成者**固有のデータを含むメッセージを生成する必要がある場合に使用できるオプションのコンポーネントは、します。</span><span class="sxs-lookup"><span data-stu-id="69554-151">**Message creators** are an optional component that can be used when you need to generate messages that contain unique data.</span></span> <span data-ttu-id="69554-152">作成元のメッセージを使用して作成; の 2 つのモードのいずれか同期および非同期です。</span><span class="sxs-lookup"><span data-stu-id="69554-152">Message creators use one of two modes of creation; synchronous and asynchronous.</span></span> <span data-ttu-id="69554-153">同期メッセージの作成モードを指定すると場合、LoadGen は、シングル スレッドのみを使用して、各メッセージに一意のペイロードが含まれていることを確認するメッセージを作成します。</span><span class="sxs-lookup"><span data-stu-id="69554-153">If the synchronous message creation mode is specified, LoadGen uses only a single thread to create messages to ensure that each message contains a unique payload.</span></span> <span data-ttu-id="69554-154">同期モードでは、各メッセージ内で一意のデータを保証、中にこのモードにはスケーラビリティが制限されます。</span><span class="sxs-lookup"><span data-stu-id="69554-154">While the synchronous mode guarantees unique data within each message, this mode also limits scalability.</span></span> <span data-ttu-id="69554-155">LoadGen は、複数の実行スレッドを使用して非同期メッセージ作成者も用意されています。これにより、LoadGen を (ためより多くのスレッドを作成することでは単に) ターゲット メッセージ レートを満たすようになります。</span><span class="sxs-lookup"><span data-stu-id="69554-155">LoadGen also provides asynchronous message creators that use multiple execution threads; this enables LoadGen to meet the target message rate (because it can simply create more threads).</span></span> <span data-ttu-id="69554-156">非同期モードでは、ランダムにデータを変更する各メッセージのメッセージの作成者を構成することがあります。</span><span class="sxs-lookup"><span data-stu-id="69554-156">In asynchronous mode, the message creator may be configured to randomly modify data for each individual message.</span></span> <span data-ttu-id="69554-157">ただし、複数のスレッドを使用しているためとは限りませんが、テスト中に生成されたすべてのメッセージが一意のペイロードに含まれます。</span><span class="sxs-lookup"><span data-stu-id="69554-157">However, because it uses multiple threads, it does not guarantee that all message generated during the test will contain a unique payload.</span></span>  
  
-   <span data-ttu-id="69554-158">**コント ローラーのスロットル**によってテストの実行中にロード ジェネレーターを制御するメッセージが、安定した速度で送信されることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="69554-158">**Throttle controllers** ensure that messages are transmitted at a steady rate by governing the load generators while the test is running.</span></span> <span data-ttu-id="69554-159">LoadGen も公開カスタム制限など、条件に基づいてメッセージのフローを制御できます。</span><span class="sxs-lookup"><span data-stu-id="69554-159">LoadGen also exposes custom throttling, which enables you to control the flow of messages based on criteria including:</span></span>  
  
    -   <span data-ttu-id="69554-160">フォルダー内のファイルの数</span><span class="sxs-lookup"><span data-stu-id="69554-160">Number of files in a folder</span></span>  
  
    -   <span data-ttu-id="69554-161">データベース テーブル内の行の数</span><span class="sxs-lookup"><span data-stu-id="69554-161">Number of rows in a database table</span></span>  
  
    -   <span data-ttu-id="69554-162">MSMQ または MQSeries メッセージ キューの深さ</span><span class="sxs-lookup"><span data-stu-id="69554-162">Depth of an MSMQ or MQSeries message queue</span></span>  
  
 <span data-ttu-id="69554-163">Microsoft [BizTalk LoadGen 2007 ツール](http://go.microsoft.com/fwlink/?LinkId=59841)ダウンロードは[http://go.microsoft.com/fwlink/?LinkId=59841](http://go.microsoft.com/fwlink/?LinkId=59841) (http://go.microsoft.com/fwlink/?LinkId=59841)。</span><span class="sxs-lookup"><span data-stu-id="69554-163">The Microsoft [BizTalk LoadGen 2007 tool](http://go.microsoft.com/fwlink/?LinkId=59841) is available for download at [http://go.microsoft.com/fwlink/?LinkId=59841](http://go.microsoft.com/fwlink/?LinkId=59841) (http://go.microsoft.com/fwlink/?LinkId=59841).</span></span>  
  
### <a name="sample-loadgen-configuration-file"></a><span data-ttu-id="69554-164">LoadGen 構成ファイルのサンプル</span><span class="sxs-lookup"><span data-stu-id="69554-164">Sample LoadGen configuration file</span></span>  
 <span data-ttu-id="69554-165">LoadGen のすべての構成情報については、xml ファイルに格納されます。</span><span class="sxs-lookup"><span data-stu-id="69554-165">All LoadGen configuration information is stored in an xml file.</span></span> <span data-ttu-id="69554-166">LoadGen 構成ファイルが含まれています、 \<CommonSection\> LoadGen シナリオでの LoadGen のすべてのタスクの既定の設定を構成する要素。</span><span class="sxs-lookup"><span data-stu-id="69554-166">The LoadGen configuration file contains a \<CommonSection\> element that configures the default settings for all LoadGen tasks in the LoadGen scenario.</span></span> <span data-ttu-id="69554-167">1 つまたは複数が、LoadGen 構成ファイルに含めることもできます\<セクション\>LoadGen の特定のタスクの構成設定を提供する要素。</span><span class="sxs-lookup"><span data-stu-id="69554-167">The LoadGen configuration file can also contain one or more \<Section\> elements that provide configuration settings for a specific LoadGen task.</span></span> <span data-ttu-id="69554-168">内のエントリ、\<セクション\>要素で指定された既定の値を置き換える、 \<CommonSection\>要素。</span><span class="sxs-lookup"><span data-stu-id="69554-168">Entries in a \<Section\> element supersede any default values specified in the \<CommonSection\> element.</span></span>  
  
 <span data-ttu-id="69554-169">これに続くサンプル LoadGen 構成ファイルでは、少し変更したバージョンの \ConfigFiles\ConsoleConfigFiles、LoadGen インストール ディレクトリのサブディレクトリに含まれている FileToFileLG.xml サンプル構成ファイルが。</span><span class="sxs-lookup"><span data-stu-id="69554-169">The sample LoadGen configuration file that follows is a slightly modified version of the FileToFileLG.xml sample configuration file that is included in the \ConfigFiles\ConsoleConfigFiles subdirectory of the LoadGen installation directory.</span></span> <span data-ttu-id="69554-170">このテストは、25 のメッセージを送信\<LotSizePerInterval\> 200 ミリ秒ごと\<SleepInterval\>、負荷ジェネレーターあたりのスレッド数 5 \<NumThreadsperSection\>負荷は停止されます5000 のメッセージの後にテスト\<NumFiles\>送信されました。</span><span class="sxs-lookup"><span data-stu-id="69554-170">This test sends 25 messages \<LotSizePerInterval\> every 200 milliseconds \<SleepInterval\>, 5 threads per load generator \<NumThreadsperSection\>and will stop the load test after 5000 messages \<NumFiles\> have been sent.</span></span>  
  
 <span data-ttu-id="69554-171">ファイルの制限コント ローラーがで指定された、 \<ThrottleController\>セクションです。</span><span class="sxs-lookup"><span data-stu-id="69554-171">The file throttle controller is specified in the \<ThrottleController\> section.</span></span> <span data-ttu-id="69554-172">値は、 \<ThresholdRange\> 1000-2000、つまり C:\Scenarios\FileToFile\Receive (パラメーター) ファイルの場所が 1000 未満または 2000 では複数のファイル、制限コント ローラーは、ファイルを制限する場合に設定されています。ジェネレーターと拡大/縮小を必要に応じて読み込みます。</span><span class="sxs-lookup"><span data-stu-id="69554-172">The value for \<ThresholdRange\> is set to 1000-2000, which means that if the file location C:\Scenarios\FileToFile\Receive (Parameters) has less than 1000 or more than 2000 files, the throttle controller will throttle the file generator and increase/decrease load as appropriate.</span></span> <span data-ttu-id="69554-173">ファイルの場所にファイルの数になります 1000 ミリ秒ごとにチェック\<SleepInterval\>です。</span><span class="sxs-lookup"><span data-stu-id="69554-173">The number of files in the file location will be checked every 1000 milliseconds \<SleepInterval\>.</span></span> <span data-ttu-id="69554-174">\<FileSection\>要素ロード ジェネレーターによって送信されるメッセージのプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="69554-174">The \<FileSection\> element defines the properties for the messages to be sent by the load generators.</span></span> <span data-ttu-id="69554-175">FileToFileLG.xml ファイル\<SrcFilePath\> filedrop C:\Scenarios\FileToFile\Receive に LoadGen をコピーする\<DstFilePath >。</span><span class="sxs-lookup"><span data-stu-id="69554-175">The FileToFileLG.xml file \<SrcFilePath\> will be copied by LoadGen to the filedrop C:\Scenarios\FileToFile\Receive \<DstFilePath>.</span></span> <span data-ttu-id="69554-176">指定された既定のトランスポートはこのため、ファイル トランスポートはここで使用、\<トランスポート名\>内の要素、 \<CommonSection\>要素。</span><span class="sxs-lookup"><span data-stu-id="69554-176">The file transport is used here because this is the default transport specified in the \<Transport Name\> element within the \<CommonSection\> element.</span></span>  
  
```  
<LoadGenFramework>  
   <CommonSection>  
      <LoadGenVersion>2</LoadGenVersion>  
      <OptimizeLimitFileSize>204800</OptimizeLimitFileSize>  
      <NumThreadsPerSection>5</NumThreadsPerSection>  
      <SleepInterval>200</SleepInterval>  
      <LotSizePerInterval>25</LotSizePerInterval>  
      <RetryInterval>10000</RetryInterval>  
      <StopMode Mode="Files">  
         <NumFiles>5000</NumFiles>  
      </StopMode>  
      <Transport Name="FILE">  
         <Assembly>FileTransport.dll/FileTransport.FileTransport</Assembly>  
      </Transport>  
      <ThrottleController Mode="Custom">  
         <Monitor Name="File">  
            <Assembly>FileMonitor.dll/DropLocationFileMonitor.DropLocationFileMonitor</Assembly>  
            <ThresholdRange>1000-2000</ThresholdRange>  
            <SleepInterval>1000</SleepInterval>  
            <Parameters>C:\Scenarios\FileToFile\Receive</Parameters>  
         </Monitor>  
         <ThrottleCondition>File</ThrottleCondition>  
      </ThrottleController>  
   </CommonSection>  
   <Section Name="FileSection">  
      <SrcFilePath>C:\LoadGen\ConfigFiles\ConsoleConfigFiles\FileToFileLG.xml</SrcFilePath>  
      <DstLocation>  
         <Parameters>  
            <DstFilePath>C:\Scenarios\FileToFile\Receive</DstFilePath>  
         </Parameters>  
      </DstLocation>  
   </Section>  
</LoadGenFramework>  
```  
  
### <a name="using-bizunit-to-drive-loadgen"></a><span data-ttu-id="69554-177">BizUnit をドライブ LoadGen を使用しました。</span><span class="sxs-lookup"><span data-stu-id="69554-177">Using BizUnit to drive LoadGen</span></span>  
 <span data-ttu-id="69554-178">BizUnit は、 **LoadGenExecuteStep**が自動のパフォーマンスと安定性のテストを容易になります。</span><span class="sxs-lookup"><span data-stu-id="69554-178">BizUnit provides the **LoadGenExecuteStep** to facilitate automated performance and stability testing.</span></span> <span data-ttu-id="69554-179">**TestExecution**を使用するサンプルのための BizUnit 構成ファイルのステージ**LoadGenExecuteStep**次のコード例に示します。</span><span class="sxs-lookup"><span data-stu-id="69554-179">The **TestExecution** stage of a sample BizUnit configuration file that uses **LoadGenExecuteStep** is shown in the following code example.</span></span> <span data-ttu-id="69554-180">この手順が LoadGen 構成ファイルの場所である 1 つの構成パラメーターを受け入れることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="69554-180">Note that this step accepts a single configuration parameter, which is the location of the LoadGen configuration file.</span></span>  
  
```  
<TestCase testName="Test_LoadGen">  
   <TestSetup>  
   </TestSetup>  
   <TestExecution>  
      <TestStep assemblyPath="" typeName="BizUnit.LoadGenExecuteStep, BizUnit.LoadGenSteps">  
         <LoadGenTestConfig>..\..\..\PerfGuideFiletoFile.xml</LoadGenTestConfig>  
      </TestStep>  
   </TestExecution>  
   <!-- Test cleanup: test cases should always leave the system in the state they found it -->  
   <TestCleanup>  
   </TestCleanup>  
</TestCase>  
```  
  
 <span data-ttu-id="69554-181">このトピックの残りの部分では、パフォーマンスの LoadGen のテストを自動化するための BizUnit テスト ケースの構成ファイルについて説明します。</span><span class="sxs-lookup"><span data-stu-id="69554-181">The remainder of this topic describes the configuration file for a BizUnit test case that automates performance testing with LoadGen.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="69554-182">この構成ファイルは、BizUnit とパフォーマンス テストの一部として LoadGen を簡単に統合するテンプレートとして使用できます。</span><span class="sxs-lookup"><span data-stu-id="69554-182">This configuration file can be used as a template to quickly integrate BizUnit and LoadGen as part of your performance testing.</span></span> <span data-ttu-id="69554-183">このテスト_ケースを実行する前に、環境の構成ファイルをカスタマイズする必要があります。</span><span class="sxs-lookup"><span data-stu-id="69554-183">Before running this test case, you will need to customize the configuration file for your environment.</span></span> <span data-ttu-id="69554-184">カスタマイズする必要がある構成ファイルのセクションでは、それに応じて示されます。</span><span class="sxs-lookup"><span data-stu-id="69554-184">Sections of the configuration file that must be customized are indicated accordingly.</span></span>  
  
 <span data-ttu-id="69554-185">まず始めの値を指定、 **testName** BizTalk ソリューションを適切なパラメーターです。</span><span class="sxs-lookup"><span data-stu-id="69554-185">To begin with, specify a value for the **testName** parameter that is appropriate for the BizTalk solution.</span></span>  
  
```  
<TestCase testName="Performance-Guide-Sample-Loadgen-Test">  
```  
  
 <span data-ttu-id="69554-186">コンテキストの変数を追加、 **TestSetup**段階です。</span><span class="sxs-lookup"><span data-stu-id="69554-186">Then add context variables to the **TestSetup** stage.</span></span> <span data-ttu-id="69554-187">これらのコンテキスト変数は、テスト_ケースの全期間にわたって参照されます。</span><span class="sxs-lookup"><span data-stu-id="69554-187">These context variables will be referenced throughout the duration of the test case.</span></span> <span data-ttu-id="69554-188">この構成ファイルを使用する指定された値を変更**TestCaseResultsDir** (C:\Dev Work\Perf ガイド Demos\PerfResults\\) および**マシン**(BIZTALKADMIN01) 一致するように、環境。</span><span class="sxs-lookup"><span data-stu-id="69554-188">To use this configuration file, modify the values specified for **TestCaseResultsDir** (C:\Dev Work\Perf Guide Demos\PerfResults\\) and **Machine** (BIZTALKADMIN01) to match your environment.</span></span>  
  
```  
<TestSetup>  
   <!-- Context property: name of test run -->  
   <TestStep assemblyPath="" typeName="BizUnit.ContextManipulatorStep">  
      <ContextItem contextKey="TestRunName">  
         <ItemTest takeFromCtx="BizUnitTestCaseName"></ItemTest>  
         <ItemTest>_%DateTime%</ItemTest>  
      </ContextItem>  
   </TestStep>  
   <!-- Context property: name of test directory to store results -->  
   <TestStep assemblyPath="" typeName="BizUnit.ContextManipulatorStep">  
      <ContextItem contextKey="TestCaseResultsDir">  
         <ItemTest>C:\Dev Work\Perf Guide Demos\PerfResults\</ItemTest>  
         <ItemTest takeFromCtx="TestRunName"></ItemTest>  
      </ContextItem>  
   </TestStep>  
   <!-- Context property: perfmon log file -->  
   <TestStep assemblyPath="" typeName="BizUnit.ContextManipulatorStep">  
      <ContextItem contextKey="PerfMonFilePath">  
         <ItemTest takeFromCtx="TestCaseResultsDir"></ItemTest>  
         <ItemTest>\PerfCounters.blg</ItemTest>  
      </ContextItem>  
   </TestStep>  
   <!-- Context property: destintation for app event log on test computer -->  
   <TestStep assemblyPath="" typeName="BizUnit.ContextManipulatorStep">  
      <ContextItem contextKey="DestPath- BIZTALKADMIN01-AppEventLog">  
         <ItemTest takeFromCtx="TestCaseResultsDir"></ItemTest>  
         <ItemTest> BIZTALKADMIN01_ApplicationLog.evt</ItemTest>  
      </ContextItem>  
   </TestStep>  
   <!-- Clear the application event log on test computer -->  
   <TestStep assemblyPath="" typeName="BizUnit.EventLogClearStep">  
      <Machine>BIZTALKADMIN01</Machine>  
      <EventLog>Application</EventLog>  
   </TestStep>  
   <!-- Create the directory to save all the test results -->  
   <TestStep assemblyPath="" typeName="BizUnit.CreateDirectory">  
      <DirectoryName takeFromCtx="TestCaseResultsDir" ></DirectoryName>  
   </TestStep>  
</TestSetup>  
```  
  
 <span data-ttu-id="69554-189">完了した後、 **TestSetup**段階では、入力、 **TestExecution**段階です。</span><span class="sxs-lookup"><span data-stu-id="69554-189">After completing the **TestSetup** stage, we enter the **TestExecution** stage.</span></span> <span data-ttu-id="69554-190">最初の手順では、BizTalk ホスト インスタンスを停止します。</span><span class="sxs-lookup"><span data-stu-id="69554-190">The first step is to stop the BizTalk host instances.</span></span> <span data-ttu-id="69554-191">個別の**BizUnit.HostConductorStep**セクションは、個別のホスト インスタンスごとに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="69554-191">A separate **BizUnit.HostConductorStep** section must be added for each distinct host instance.</span></span> <span data-ttu-id="69554-192">環境内をこの構成ファイルを使用している場合は、適切な値を入力する必要があります**HostInstanceName**、**サーバー**、**ログオン**、および**パスワード**です。</span><span class="sxs-lookup"><span data-stu-id="69554-192">If you are using this configuration file in your environment, you will also need to enter the appropriate values for **HostInstanceName**, **Server**, **Logon**, and **Password**.</span></span>  
  
```  
<TestExecution>  
   <!-- Step 1: Stop BizTalk Hosts -->  
   <TestStep assemblyPath="" typeName="BizUnit.HostConductorStep, BizUnit.BizTalkSteps">  
      <Action>stop</Action>  
      <HostInstanceName>BizTalkServerApplication</HostInstanceName>  
      <Server>BizTalkAdmin01</Server>  
      <Logon>ServerName\Administrator</Logon>  
      <PassWord>Pass@word1</PassWord>  
      <GrantLogOnAsService>true</GrantLogOnAsService>  
   </TestStep>  
```  
  
 <span data-ttu-id="69554-193">すべてのホスト インスタンスを停止した後、bts_CleanupMsgBox を使用して、BizTalk メッセージ ボックス データベースをクリーンアップおストアド プロシージャです。</span><span class="sxs-lookup"><span data-stu-id="69554-193">After stopping all of the host instances, we clean up the BizTalk MessageBox database using the bts_CleanupMsgBox stored procedure.</span></span> <span data-ttu-id="69554-194">この手順を使用するには、値を変更する必要があります**ConnectionString**環境に合わせてです。</span><span class="sxs-lookup"><span data-stu-id="69554-194">To use this step you must modify the value for **ConnectionString** to match your environment.</span></span>  
  
```  
<!-- Step 2: Clean Up MessageBox -->  
<TestStep assemblyPath="" typeName="BizUnit.DBExecuteNonQueryStep">  
   <DelayBeforeExecution>1</DelayBeforeExecution>  
   <ConnectionString>Persist Security Info=False;Integrated Security=SSPI;database=BizTalkMsgBoxDb;server=BIZTALKADMIN01;Connect Timeout=30</ConnectionString>  
   <SQLQuery>  
      <RawSQLQuery>[dbo].[bts_CleanupMsgbox]</RawSQLQuery>  
   </SQLQuery>  
</TestStep>  
```  
  
 <span data-ttu-id="69554-195">手順 3 の**TestExecution**段階、テンプレート ファイルで指定されているパフォーマンス モニター (PerfMon) カウンターの開始。</span><span class="sxs-lookup"><span data-stu-id="69554-195">Step 3 of the **TestExecution** stage starts Performance Monitor (PerfMon) counters that are specified in a template file.</span></span> <span data-ttu-id="69554-196">テンプレート ファイルの例がサンプルの下に一覧表示**BizUnit.PerfmonCountersStep**以下です。</span><span class="sxs-lookup"><span data-stu-id="69554-196">A sample template file is listed underneath the sample **BizUnit.PerfmonCountersStep** below.</span></span> <span data-ttu-id="69554-197">テンプレート ファイルを使用するには、指定された値を変更する必要があります**CountersListFilePath**環境に合わせてです。</span><span class="sxs-lookup"><span data-stu-id="69554-197">To use the template file, you must modify the value specified for **CountersListFilePath** to match your environment.</span></span> <span data-ttu-id="69554-198">サンプル パフォーマンス モニター カウンター テンプレート ファイルを変更して監視したり、自分のシナリオに無関係なものをすべて削除したいパフォーマンス モニターのカウンターが含まれます。</span><span class="sxs-lookup"><span data-stu-id="69554-198">Modify the sample performance monitor counter template file to include any PerfMon counters that you would like to monitor or remove any that are not relevant to your scenario.</span></span>  
  
```  
<!-- Step 3: Start Perfmon counters -->  
<TestStep assemblyPath="" typeName="BizUnit.PerfmonCountersStep">  
   <PerfmonAction>Start</PerfmonAction>  
   <CounterSetName>PerfGuidePerfmonCounters</CounterSetName>  
   <CountersListFilePath>C:\Dev Work\Perf Guide Demos\Test_06_PerfCounters.txt</CountersListFilePath>  
   <SampleInterval>5</SampleInterval>  
   <PerfmonLogFilePath takeFromCtx="PerfMonFilePath"></PerfmonLogFilePath>  
</TestStep>  
```  
  
 <span data-ttu-id="69554-199">**サンプル パフォーマンス モニター カウンター テンプレート ファイル (Test_06_PerfCounters.txt、BizUnit.PerfmonCountersStep によって参照される):**</span><span class="sxs-lookup"><span data-stu-id="69554-199">**Sample Performance Monitor counter template file (Test_06_PerfCounters.txt referenced by the BizUnit.PerfmonCountersStep):**</span></span>  
  
```  
\Processor(*)\*  
\Process(*)\*  
\Memory\*  
\PhysicalDisk(*)\*  
\System\Context Switches/sec  
\System\Processor Queue Length  
\BizTalk:FILE Receive Adapter(*)\*  
\BizTalk:File Send Adapter(*)\*  
\BizTalk:FTP Receive Adapter(*)\*  
\BizTalk:FTP Send Adapter(*)\*  
\BizTalk:HTTP Receive Adapter(*)\*  
\BizTalk:HTTP Send Adapter(*)\*  
\BizTalk:Message Agent(*)\*  
\BizTalk:Messaging(*)\*  
\BizTalk:Message Box:General Counters(*)\*  
\BizTalk:Message Box:Host Counters(*)\*  
\BizTalk:Messaging Latency(*)\*  
\BizTalk:SOAP Receive Adapter(*)\*  
\BizTalk:SOAP Send Adapter(*)\*  
\BizTalk:TDDS(*)\*  
\XLANG/s Orchestrations(*)\*  
```  
  
 <span data-ttu-id="69554-200">ここでは、BizTalk Server ホスト インスタンスを開始します。</span><span class="sxs-lookup"><span data-stu-id="69554-200">Now we start the BizTalk Server host instances.</span></span> <span data-ttu-id="69554-201">個別の**BizUnit.HostConductorStep**セクションは、個別のホスト インスタンスごとに追加する必要があります (distinct を含むホストの複数のインスタンスのサーバーにわたる)。</span><span class="sxs-lookup"><span data-stu-id="69554-201">A separate **BizUnit.HostConductorStep** section must be added for each distinct host instance (distinct includes multiple instances of a host across servers).</span></span> <span data-ttu-id="69554-202">環境内をこの構成ファイルを使用している場合は、適切な値を入力する必要があります**HostInstanceName**、**サーバー**、**ログオン**、および**パスワード**です。</span><span class="sxs-lookup"><span data-stu-id="69554-202">If you are using this configuration file in your environment, you will also need to enter the appropriate values for **HostInstanceName**, **Server**, **Logon**, and **Password**.</span></span>  
  
```  
<!-- Step 4: Start BizTalk Hosts -->  
<TestStep assemblyPath="" typeName="BizUnit.BizTalkSteps.HostConductorStep, BizUnit.BizTalkSteps, Version=3.0.0.0, Culture=neutral, PublicKeyToken=7eb7d82981ae5162">  
   <Action>start</Action>  
   <HostInstanceName>BizTalkServerApplication</HostInstanceName>  
   <Server>BizTalkAdmin01</Server>  
   <Logon>ServerName\Administrator</Logon>  
   <PassWord>Pass@word1</PassWord>  
   <GrantLogOnAsService>true</GrantLogOnAsService>  
</TestStep>  
```  
  
 <span data-ttu-id="69554-203">手順 5"primes"システム BizTalk Server を使用するいくつかのメッセージを送信することによって**BizUnit.LoadGenExecuteStep**; の値を変更、 **LoadGenTestConfig**環境と一致するパラメーターです。</span><span class="sxs-lookup"><span data-stu-id="69554-203">Step 5 “primes” the system by sending a couple of messages to BizTalk Server using **BizUnit.LoadGenExecuteStep**; change the value of the **LoadGenTestConfig** parameter to match your environment.</span></span>  
  
```  
<!-- Step 5: Send Priming messages -->  
<TestStep assemblyPath="" typeName="BizUnit.LoadGenExecuteStep, BizUnit.LoadGenSteps">  
   <LoadGenTestConfig>C:\Program Files\LoadGen\ConfigFiles\ConsoleConfigFiles\PerfGuideFiletoFile.xml</LoadGenTestConfig>  
</TestStep>  
```  
  
 <span data-ttu-id="69554-204">手順 6 LoadGen 構成ファイルをメモリに書き込みますテストが完了すると、テスト結果のデータベースに記述し、できます。</span><span class="sxs-lookup"><span data-stu-id="69554-204">Step 6 writes the LoadGen configuration file to memory so that it can then be written to the test results database when the test is complete.</span></span>  
  
```  
  
      <!-- Step 6: Read loadgen file into context variable -->  
<TestStep assemblyPath="" typeName="BizUnit.FileReadAndLoadToContext">  
   <FilePath>C:\Program Files\LoadGen\ConfigFiles\ConsoleConfigFiles\PerfGuideFiletoFile.xml</FilePath>  
   <ContextPropertyName>LoadGenFileContent</ContextPropertyName>  
</TestStep>  
```  
  
 <span data-ttu-id="69554-205">これでテスト結果データベースにテストの開始時刻を記述します。</span><span class="sxs-lookup"><span data-stu-id="69554-205">Now we write the test start time to a test results database.</span></span> <span data-ttu-id="69554-206">変更、 **ConnectionString**と**RawSQLQuery**環境と一致するパラメーターです。</span><span class="sxs-lookup"><span data-stu-id="69554-206">Modify the **ConnectionString** and **RawSQLQuery** parameters to match your environment.</span></span>  
  
```  
<!-- Step 7: Update test results DB with test start time -->  
<TestStep assemblyPath="" typeName="BizUnit.DBExecuteNonQueryStep">  
   <DelayBeforeExecution>1</DelayBeforeExecution>  
   <ConnectionString>Persist Security Info=False;Integrated Security=SSPI;database=TestResults;server=BizTalkAdmin01;Connect Timeout=30</ConnectionString>  
   <SQLQuery>  
      <RawSQLQuery>INSERT INTO tblPerformanceResults (Test_ID, StartTime,LoadGenFile) VALUES ('{0}',GetDate(),'{1}' )</RawSQLQuery>  
      <SQLQueryParams>  
         <SQLQueryParam takeFromCtx="TestRunName"></SQLQueryParam>  
         <SQLQueryParam takeFromCtx="LoadGenFileContent"></SQLQueryParam>  
      </SQLQueryParams>  
   </SQLQuery>  
</TestStep>  
```  
  
 <span data-ttu-id="69554-207">手順 8 がある場所の実際のパフォーマンス テストを使用して開始**BizUnit.LoadGenExecuteStep**です。</span><span class="sxs-lookup"><span data-stu-id="69554-207">Step 8 is where the actual performance test is initiated using **BizUnit.LoadGenExecuteStep**.</span></span> <span data-ttu-id="69554-208">この手順は、手順 5 で使用された同じ LoadGen 構成ファイルを指定し、任意の有効な LoadGen 構成ファイルを次を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="69554-208">This step specifies the same LoadGen configuration file that was used in step 5, but you can specify any valid LoadGen configuration file here.</span></span> <span data-ttu-id="69554-209">**BizUnit.DelayStep**の時間を開始、システム経由でやり取りされるメッセージを許可する、5 秒の遅延を強制する手順 9. で使用します。</span><span class="sxs-lookup"><span data-stu-id="69554-209">**BizUnit.DelayStep** is used in step 9 to impose a 5-second delay to allow time for messages to start flowing through the system.</span></span> <span data-ttu-id="69554-210">使用してホスト キューの長さを計算**BizUnit.PerMonCounterMonitorStep**です。</span><span class="sxs-lookup"><span data-stu-id="69554-210">Host queue length is calculated using **BizUnit.PerMonCounterMonitorStep**.</span></span> <span data-ttu-id="69554-211">このパラメーターには、手順 10 で指定されている 1 の値に達すると、テストが終了します。</span><span class="sxs-lookup"><span data-stu-id="69554-211">When this parameter reaches a value of 1 as specified in step 10, the test is concluded.</span></span> <span data-ttu-id="69554-212">値を変更、 **InstanceName**と**サーバー**ホスト インスタンスと、環境内を監視するサーバーの名前に一致するパラメーターです。</span><span class="sxs-lookup"><span data-stu-id="69554-212">Change the values for the **InstanceName** and **Server** parameters to match the name of the host instance and server that you would like to monitor in your environment.</span></span>  
  
```  
<!-- Step 8: LoadGen: Load actual perf test -->  
<TestStep assemblyPath="" typeName="BizUnit.LoadGenSteps.LoadGenExecuteStep, BizUnit.LoadGenSteps , Version=3.0.0.0, Culture=neutral, PublicKeyToken=7eb7d82981ae5162">  
   <LoadGenTestConfig>C:\Program Files\LoadGen\ConfigFiles\ConsoleConfigFiles\PerfGuideFiletoFile.xml</LoadGenTestConfig>  
</TestStep>  
<!-- Step 9: Delay for 5 secs to allow msgs to start flowing -->  
<TestStep assemblyPath="" typeName="BizUnit.DelayStep">  
   <Delay>5000</Delay>  
</TestStep>  
<!-- Step 10: Wait for Orch Host Queue depth to reach one -->  
<TestStep assemblyPath="" typeName="BizUnit.PerfMonCounterMonitorStep">  
   <CategoryName>BizTalk:Message Box:Host Counters</CategoryName>  
   <CounterName>Host Queue - Length</CounterName>  
   <InstanceName>BizTalkServerApplication:biztalkmsgboxdb:BizTalkAdmin01</InstanceName>  
   <Server>BizTalkAdmin01</Server>  
   <CounterTargetValue>1</CounterTargetValue>  
</TestStep>  
```  
  
 <span data-ttu-id="69554-213">使用して、テストの終了時に**BizUnit.DBExecuteNonQueryStep**をテスト結果のデータベースを更新します。</span><span class="sxs-lookup"><span data-stu-id="69554-213">At the conclusion of the test we use **BizUnit.DBExecuteNonQueryStep** to update the test results database.</span></span> <span data-ttu-id="69554-214">このステップの完了が、終了によって示される、テスト実行のステージの終わりを示す\</TestExecution\>タグ。</span><span class="sxs-lookup"><span data-stu-id="69554-214">Completion of this step signifies the end of the test execution stage, as indicated by the closing \</TestExecution\> tag.</span></span> <span data-ttu-id="69554-215">ここでも、変更する必要があります、 **ConnectionString**と**RawSQLQuery**環境と一致するパラメーターです。</span><span class="sxs-lookup"><span data-stu-id="69554-215">Again, you must modify the **ConnectionString** and **RawSQLQuery** parameters to match your environment.</span></span>  
  
```  
   <!-- Step 11: Update test results DB with test stop time -->  
   <TestStep assemblyPath="" typeName="BizUnit.DBExecuteNonQueryStep">  
      <DelayBeforeExecution>1</DelayBeforeExecution>  
      <ConnectionString>Persist Security Info=False;Integrated Security=SSPI;database=TestResults;server=BIZTALKADMIN01;Connect Timeout=30</ConnectionString>  
      <SQLQuery>  
         <RawSQLQuery>UPDATE tblPerformanceResults SET EndTime = GetDate() WHERE Test_ID = '{0}'</RawSQLQuery>  
         <SQLQueryParams>  
            <SQLQueryParam takeFromCtx="TestRunName"></SQLQueryParam>  
         </SQLQueryParams>  
      </SQLQuery>  
   </TestStep>  
</TestExecution>  
```  
  
 <span data-ttu-id="69554-216">実行のステージの終了時に、テスト クリーンアップ ステージを入力します。</span><span class="sxs-lookup"><span data-stu-id="69554-216">Upon concluding the execution stage we enter the test cleanup stage.</span></span> <span data-ttu-id="69554-217">このステージで使用**BizUnit.PerfmonCountersStep**前 (手順 3) で開始されたパフォーマンス モニター カウンターを停止します。</span><span class="sxs-lookup"><span data-stu-id="69554-217">This stage uses **BizUnit.PerfmonCountersStep** to stop the Performance Monitor counters that were started earlier (in Step 3).</span></span>  
  
```  
<TestCleanup>  
      <!-- Return system to state prior to test -->  
      <!-- Stop perfmon counters -->  
      <TestStep assemblyPath="" typeName="BizUnit.PerfmonCountersStep" failOnError="false">  
         <PerfmonAction>Stop</PerfmonAction>  
         <CounterSetName>PerfGuidePerfmonCounters</CounterSetName>  
      </TestStep>  
   </TestCleanup>  
</TestCase>  
```  
  
 <span data-ttu-id="69554-218">この例では、BizUnit を結合してで LoadGen をパフォーマンス テストを自動化する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="69554-218">This example illustrated how BizUnit can be combined with LoadGen to automate performance testing.</span></span> <span data-ttu-id="69554-219">ロード テストのための BizUnit 構成ファイルで説明されているは、機能テストと同じ方法で、Visual Studio のテスト ツールから実行できます。</span><span class="sxs-lookup"><span data-stu-id="69554-219">The load test described by the BizUnit configuration file can be executed from Visual Studio’s testing tools in the same manner as the functional testing.</span></span> <span data-ttu-id="69554-220">この手法を採用するには、一元的に管理、管理、およびパフォーマンスのテストにデータを収集することができます。</span><span class="sxs-lookup"><span data-stu-id="69554-220">Adopting this approach enables you to centrally manage, administer, and collect data for your performance testing.</span></span>  
  
 <span data-ttu-id="69554-221">BizUnit と LoadGen を使用して、自動化された方法で、通常の業務時間中に分析のための十分なテスト結果を提供する営業時間外の中に発生する複数のテストの実行をスケジュールする非常に簡単です。</span><span class="sxs-lookup"><span data-stu-id="69554-221">By using BizUnit and LoadGen in an automated approach, it is very easy to schedule multiple test runs to occur during off hours, which will provide ample test results for analysis during normal working hours.</span></span> <span data-ttu-id="69554-222">パフォーマンス テストを自動化するときに、予期される運用メッセージ ボリュームのことを通じて、システム負荷が異なるモデルを例にすること (75%、100%、125%) のさまざまな程度をシミュレート LoadGen スクリプトの使用を検討します。</span><span class="sxs-lookup"><span data-stu-id="69554-222">When automating performance testing, consider using LoadGen scripts that model different loads through the system, for example you may wish to simulate varying degrees (75%, 100% and 125%) of the expected production message volume.</span></span> <span data-ttu-id="69554-223">ロード テストを実行するときは、オーバー ロードまたは"無効な day"シナリオをテストする特に重要です。</span><span class="sxs-lookup"><span data-stu-id="69554-223">When performing load testing, it is especially important to test the overload or “bad day” scenario.</span></span> <span data-ttu-id="69554-224">システムを実稼働環境に配置する、前に、BizTalk Server 環境内の各テスト・ケースの最大スループット (MST) を知っておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="69554-224">Before placing the system into production, you should know what the maximum sustainable throughput (MST) is for each test case in the BizTalk Server environment.</span></span> <span data-ttu-id="69554-225">維持可能な最大のパフォーマンスに関する詳細については、次を参照してください。[維持可能なパフォーマンスは何ですか。](http://go.microsoft.com/fwlink/?LinkID=132304)</span><span class="sxs-lookup"><span data-stu-id="69554-225">For more information about maximum sustainable performance, see [What Is Sustainable Performance?](http://go.microsoft.com/fwlink/?LinkID=132304)</span></span> <span data-ttu-id="69554-226">(http://go.microsoft.com/fwlink/?LinkID=132304)、BizTalk Server 2009 マニュアルを参照します。</span><span class="sxs-lookup"><span data-stu-id="69554-226">(http://go.microsoft.com/fwlink/?LinkID=132304) in the BizTalk Server 2009 documentation.</span></span>  
  
### <a name="the-complete-bizunit-loadgen-sample-configuration-file"></a><span data-ttu-id="69554-227">完了のための BizUnit LoadGen サンプル構成ファイル</span><span class="sxs-lookup"><span data-stu-id="69554-227">The complete BizUnit LoadGen sample configuration file</span></span>  
 <span data-ttu-id="69554-228">次の一覧には、前出 BizUnit 構成ファイルの内容全体が含まれています。</span><span class="sxs-lookup"><span data-stu-id="69554-228">The following list contains the entire contents of the BizUnit configuration file referenced earlier.</span></span>  
  
```  
<TestCase testName="Performance-Guide-Sample-Loadgen-Test">  
   <TestSetup>  
      <!-- Context property: name of test run -->  
      <TestStep assemblyPath="" typeName="BizUnit.ContextManipulatorStep">  
         <ContextItem contextKey="TestRunName">  
            <ItemTest takeFromCtx="BizUnitTestCaseName"></ItemTest>  
            <ItemTest>_%DateTime%</ItemTest>  
         </ContextItem>  
      </TestStep>  
      <!-- Context property: name of test directory to store results -->  
      <TestStep assemblyPath="" typeName="BizUnit.ContextManipulatorStep">  
         <ContextItem contextKey="TestCaseResultsDir">  
            <ItemTest>C:\Dev Work\Perf Guide Demos\PerfResults\</ItemTest>  
            <ItemTest takeFromCtx="TestRunName"></ItemTest>  
         </ContextItem>  
      </TestStep>  
      <!-- Context property: perfmon log file -->  
      <TestStep assemblyPath="" typeName="BizUnit.ContextManipulatorStep">  
         <ContextItem contextKey="PerfMonFilePath">  
            <ItemTest takeFromCtx="TestCaseResultsDir"></ItemTest>  
            <ItemTest>\PerfCounters.blg</ItemTest>  
         </ContextItem>  
      </TestStep>  
      <!-- Context property: destintation for app event log on BTSSVR-001 -->  
      <TestStep assemblyPath="" typeName="BizUnit.ContextManipulatorStep">  
         <ContextItem contextKey="DestPath-BTSSVR-001-AppEventLog">  
            <ItemTest takeFromCtx="TestCaseResultsDir"></ItemTest>  
            <ItemTest>BTSSVR-001_ApplicationLog.evt</ItemTest>  
         </ContextItem>  
      </TestStep>  
      <!-- Clear the application event log on BTSSVR-001 -->  
      <TestStep assemblyPath="" typeName="BizUnit.EventLogClearStep">  
         <Machine>BIZTALKADMIN01</Machine>  
         <EventLog>Application</EventLog>  
      </TestStep>  
      <!-- Create the directory to save all the test results -->  
      <TestStep assemblyPath="" typeName="BizUnit.CreateDirectory">  
         <DirectoryName takeFromCtx="TestCaseResultsDir" ></DirectoryName>  
      </TestStep>  
   </TestSetup>  
  
   <TestExecution>  
      <!-- Step 1: Stop BizTalk Hosts -->  
      <TestStep assemblyPath="" typeName="BizUnit.HostConductorStep, BizUnit.BizTalkSteps">  
         <Action>stop</Action>  
         <HostInstanceName>BizTalkServerApplication</HostInstanceName>  
         <Server>BizTalkAdmin01</Server>  
         <Logon>ServerName\Administrator</Logon>  
         <PassWord>Pass@word1</PassWord>  
         <GrantLogOnAsService>true</GrantLogOnAsService>  
      </TestStep>  
      <!-- Step 2: Clean Up MessageBox -->  
      <TestStep assemblyPath="" typeName="BizUnit.DBExecuteNonQueryStep">  
         <DelayBeforeExecution>1</DelayBeforeExecution>  
         <ConnectionString>Persist Security Info=False;Integrated Security=SSPI;database=BizTalkMsgBoxDb;server=BIZTALKADMIN01;Connect Timeout=30</ConnectionString>  
         <SQLQuery>  
            <RawSQLQuery>[dbo].[bts_CleanupMsgbox]</RawSQLQuery>  
         </SQLQuery>  
      </TestStep>  
      <!-- Step 3: Start Perfmon counters -->  
      <TestStep assemblyPath="" typeName="BizUnit.PerfmonCountersStep">  
         <PerfmonAction>Start</PerfmonAction>  
         <CounterSetName>PerfGuidePerfmonCounters</CounterSetName>  
         <CountersListFilePath>C:\Dev Work\Perf Guide Demos\Test_06_PerfCounters.txt</CountersListFilePath>  
         <SampleInterval>5</SampleInterval>  
         <PerfmonLogFilePath takeFromCtx="PerfMonFilePath"></PerfmonLogFilePath>  
      </TestStep>  
      <!-- Step 4: Start BizTalk Hosts -->  
      <TestStep assemblyPath="" typeName="BizUnit.BizTalkSteps.HostConductorStep, BizUnit.BizTalkSteps, Version=3.0.0.0, Culture=neutral, PublicKeyToken=7eb7d82981ae5162">  
         <Action>start</Action>  
         <HostInstanceName>BizTalkServerApplication</HostInstanceName>  
         <Server>BizTalkAdmin01</Server>  
         <Logon>ServerName\Administrator</Logon>  
         <PassWord>Pass@word1</PassWord>  
         <GrantLogOnAsService>true</GrantLogOnAsService>  
      </TestStep>  
      <!-- Step 5: Send Priming messages -->  
      <TestStep assemblyPath="" typeName="BizUnit.LoadGenExecuteStep, BizUnit.LoadGenSteps">  
         <LoadGenTestConfig>C:\Program Files\LoadGen\ConfigFiles\ConsoleConfigFiles\PerfGuideFiletoFile.xml</LoadGenTestConfig>  
      </TestStep>  
      <!-- Step 6: Read loadgen file into context variable -->  
      <TestStep assemblyPath="" typeName="BizUnit.FileReadAndLoadToContext">  
         <FilePath>C:\Program Files\LoadGen\ConfigFiles\ConsoleConfigFiles\PerfGuideFiletoFile.xml</FilePath>  
         <ContextPropertyName>LoadGenFileContent</ContextPropertyName>  
      </TestStep>  
      <!-- Step 7: Update test results DB with test start time -->  
      <TestStep assemblyPath="" typeName="BizUnit.DBExecuteNonQueryStep">  
         <DelayBeforeExecution>1</DelayBeforeExecution>  
         <ConnectionString>Persist Security Info=False;Integrated Security=SSPI;database=TestResults;server=BizTalkAdmin01;Connect Timeout=30</ConnectionString>  
         <SQLQuery>  
            <RawSQLQuery>INSERT INTO tblPerformanceResults (Test_ID, StartTime,LoadGenFile) VALUES ('{0}',GetDate(),'{1}' )</RawSQLQuery>  
            <SQLQueryParams>  
               <SQLQueryParam takeFromCtx="TestRunName"></SQLQueryParam>  
               <SQLQueryParam takeFromCtx="LoadGenFileContent"></SQLQueryParam>  
            </SQLQueryParams>  
         </SQLQuery>  
      </TestStep>  
      <!-- Step 8: LoadGen: Load actual perf test -->  
      <TestStep assemblyPath="" typeName="BizUnit.LoadGenSteps.LoadGenExecuteStep, BizUnit.LoadGenSteps , Version=3.0.0.0, Culture=neutral, PublicKeyToken=7eb7d82981ae5162">  
        <LoadGenTestConfig>C:\Program Files\LoadGen\ConfigFiles\ConsoleConfigFiles\PerfGuideFiletoFile.xml</LoadGenTestConfig>  
      </TestStep>  
      <!-- Step 9: Delay for 5 secs to allow msgs to start flowing -->  
      <TestStep assemblyPath="" typeName="BizUnit.DelayStep">  
         <Delay>5000</Delay>  
      </TestStep>  
      <!-- Step 10: Wait for Orch Host Queue depth to reach one -->  
      <TestStep assemblyPath="" typeName="BizUnit.PerfMonCounterMonitorStep">  
         <CategoryName>BizTalk:Message Box:Host Counters</CategoryName>  
         <CounterName>Host Queue - Length</CounterName>  
         <InstanceName>BizTalkServerApplication:biztalkmsgboxdb:BizTalkAdmin01</InstanceName>  
         <Server>BizTalkAdmin01</Server>  
         <CounterTargetValue>1</CounterTargetValue>  
      </TestStep>  
      <!-- Step 11: Update test results DB with test stop time -->  
      <TestStep assemblyPath="" typeName="BizUnit.DBExecuteNonQueryStep">  
         <DelayBeforeExecution>1</DelayBeforeExecution>  
         <ConnectionString>Persist Security Info=False;Integrated Security=SSPI;database=TestResults;server=BIZTALKADMIN01;Connect Timeout=30</ConnectionString>  
         <SQLQuery>  
            <RawSQLQuery>UPDATE tblPerformanceResults SET EndTime = GetDate() WHERE Test_ID = '{0}'</RawSQLQuery>  
            <SQLQueryParams>  
               <SQLQueryParam takeFromCtx="TestRunName"></SQLQueryParam>  
            </SQLQueryParams>  
         </SQLQuery>  
      </TestStep>  
   </TestExecution>  
  
   <TestCleanup>  
      <!-- Return system to state prior to test -->  
      <!-- Stop perfmon counters -->  
      <TestStep assemblyPath="" typeName="BizUnit.PerfmonCountersStep" failOnError="false">  
         <PerfmonAction>Stop</PerfmonAction>  
         <CounterSetName>PerfGuidePerfmonCounters</CounterSetName>  
      </TestStep>  
   </TestCleanup>  
</TestCase>  
```  
  
## <a name="see-also"></a><span data-ttu-id="69554-229">参照</span><span class="sxs-lookup"><span data-stu-id="69554-229">See Also</span></span>  
 [<span data-ttu-id="69554-230">自動テストを容易にするための BizUnit の使用</span><span class="sxs-lookup"><span data-stu-id="69554-230">Using BizUnit to Facilitate Automated Testing</span></span>](../technical-guides/using-bizunit-to-facilitate-automated-testing.md)