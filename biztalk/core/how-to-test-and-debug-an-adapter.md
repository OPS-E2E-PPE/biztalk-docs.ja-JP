---
title: テスト アダプターをデバッグする方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cf6563ea-b4ea-4617-b3da-d31250d002ab
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c6d3806dc78fa09031339ab548d64149202d6dc3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65383738"
---
# <a name="how-to-test-and-debug-an-adapter"></a><span data-ttu-id="60bc1-102">テスト アダプターをデバッグする方法</span><span class="sxs-lookup"><span data-stu-id="60bc1-102">How to Test and Debug an Adapter</span></span>
<span data-ttu-id="60bc1-103">多くの場合、実行時の問題をデバッグすると、多角的なアプローチが必要です。</span><span class="sxs-lookup"><span data-stu-id="60bc1-103">Debugging run-time problems often requires a multifaceted approach.</span></span> <span data-ttu-id="60bc1-104">ソフトウェア トレース、パフォーマンス カウンター、イベント ログ エントリ、Windows Management Instrumentation (WMI) イベント、および問題やソフトウェアのバグの原因を特定するソース コードのデバッグなどの複数のソースからデータを収集する必要があります。</span><span class="sxs-lookup"><span data-stu-id="60bc1-104">Data must be gathered from multiple sources such as software tracing, performance counters, event log entries, Windows Management Instrumentation (WMI) events, and debugging source code to determine the cause of problems or software bugs.</span></span>  
  
 <span data-ttu-id="60bc1-105">ため、受信し、送信アダプターは、デバッガーは、アダプターをデバッグする BtsNtSvc.exe プロセスに接続する必要がある、BizTalk サービスのアドレス空間で実行します。</span><span class="sxs-lookup"><span data-stu-id="60bc1-105">Because receive and send adapters run in the address space of the BizTalk service the debugger needs to be attached to the BtsNtSvc.exe process to debug an adapter.</span></span> <span data-ttu-id="60bc1-106">ただし、分離受信アダプター、デバッガーは、アダプターをホストするプロセスにアタッチする必要があります。</span><span class="sxs-lookup"><span data-stu-id="60bc1-106">However for isolated receive adapters, the debugger needs to be attached to the process that hosts the adapter.</span></span>  
  
 <span data-ttu-id="60bc1-107">アダプターの実行時のコードは、トラブルシューティングのためのランタイム診断をキャプチャするコードのトレースとインストルメント化する必要です。</span><span class="sxs-lookup"><span data-stu-id="60bc1-107">The adapter run-time code should be instrumented with tracing code to capture run-time diagnostics for troubleshooting.</span></span> <span data-ttu-id="60bc1-108">Microsoft Enterprise Instrumentation Framework (EIF) を使用して、これを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="60bc1-108">You can do this by using the Microsoft Enterprise Instrumentation Framework (EIF).</span></span> <span data-ttu-id="60bc1-109">通常は、重要度の異なるレベルのトレース ステートメントを追加すると便利などのトレース エラー状態のみのエラーと警告のトレース、および最後に、エラー、警告、および情報ステートメントのトレースします。</span><span class="sxs-lookup"><span data-stu-id="60bc1-109">Typically it is useful to add trace statements for different levels of severity, for example, tracing for error conditions only, tracing for errors and warnings, and finally tracing for errors, warnings, and informational statements.</span></span> <span data-ttu-id="60bc1-110">さらより複雑なアダプターには、互いから分離して追跡する必要がある個々 のサブシステムがあります。</span><span class="sxs-lookup"><span data-stu-id="60bc1-110">Further, more complex adapters may have separate subsystems that need to be traced in isolation from each other.</span></span> <span data-ttu-id="60bc1-111">ネットワーク サブシステムとコア サブシステム; アダプターが、があります。すべてのサブシステムのトレースを有効にすると一部のシナリオで過剰な「ノイズ」が生成される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="60bc1-111">For example, an adapter may have a network subsubsystem and a core subsystem; enabling tracing for all subsystems may generate an excessive amount of "noise" in some scenarios.</span></span>  
  
 <span data-ttu-id="60bc1-112">アダプターの実行時の動作に関する詳細情報を提供する実行時に速度や値をキャプチャするパフォーマンス カウンターを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="60bc1-112">Performance counters should be added to capture rates and values at run time to give more information about the run-time behavior of the adapter.</span></span> <span data-ttu-id="60bc1-113">たとえば、アダプターでは、1 秒あたりに送信されたメッセージの料金と同様に、エンドポイントごとに送信されるメッセージの実際の数のパフォーマンス カウンターを発行できます。</span><span class="sxs-lookup"><span data-stu-id="60bc1-113">For example, an adapter might publish performance counters for the raw numbers of messages sent on a per-endpoint basis as well as the rate of messages sent per second.</span></span>  
  
 <span data-ttu-id="60bc1-114">WMI イベントは、重大なエラー シナリオによっては便利な場合もあります。</span><span class="sxs-lookup"><span data-stu-id="60bc1-114">WMI events may also be useful for some critical error scenarios.</span></span>  <span data-ttu-id="60bc1-115">インスタンス、アダプター数、受信場所をシャット ダウンの原因となる重大なエラー WMI イベントを発生させる場合は、そのイベントをリッスンし、適切なアクションを実行する管理者を許可します。</span><span class="sxs-lookup"><span data-stu-id="60bc1-115">For instance if an adapter hits a critical error that causes it to shut down a receive location, firing a WMI event allows an administrator to listen on that event and take appropriate action.</span></span>  
  
## <a name="adapter-testing"></a><span data-ttu-id="60bc1-116">アダプターのテスト</span><span class="sxs-lookup"><span data-stu-id="60bc1-116">Adapter Testing</span></span>  
 <span data-ttu-id="60bc1-117">BizTalk Server のカスタム アダプターを開発する場合は、エンタープライズ ソフトウェアの品質を開発する必要がありますに注意してください。</span><span class="sxs-lookup"><span data-stu-id="60bc1-117">When you develop a custom adapter for BizTalk Server, remember that it should be developed to enterprise software quality.</span></span> <span data-ttu-id="60bc1-118">これは、アダプターを出荷する前に徹底的にテストする必要があることを意味します。</span><span class="sxs-lookup"><span data-stu-id="60bc1-118">This means that you need to test the adapter thoroughly before shipping it.</span></span> <span data-ttu-id="60bc1-119">完全に詳述されませんアダプターのテスト方法、中にこのセクションでは実行する必要があるものの概要を把握します。</span><span class="sxs-lookup"><span data-stu-id="60bc1-119">While it does not completely detail how adapters should be tested, this section gives an idea of what needs to be done.</span></span> <span data-ttu-id="60bc1-120">一般に、3 つのカテゴリをカバー アダプターなどの実行時のコードをテストする必要があります。 機能テスト、ストレス テスト、およびパフォーマンスをテストします。</span><span class="sxs-lookup"><span data-stu-id="60bc1-120">In general the testing of run-time code such as adapters should cover three broad categories: functional testing, stress testing, and performance testing.</span></span>  
  
### <a name="function-testing"></a><span data-ttu-id="60bc1-121">機能テスト</span><span class="sxs-lookup"><span data-stu-id="60bc1-121">Function Testing</span></span>  
 <span data-ttu-id="60bc1-122">ポジティブ テストとネガティブ テストの両方を含む、その機能のすべての順列には、アダプターをテストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="60bc1-122">The adapter should be tested for all permutations of its functionality, including both positive tests and negative tests.</span></span> <span data-ttu-id="60bc1-123">ポジティブ テストが含まれますが、次のシナリオに限定されません。</span><span class="sxs-lookup"><span data-stu-id="60bc1-123">Positive tests should include but not be limited to the following scenarios:</span></span>  
  
- <span data-ttu-id="60bc1-124">メッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="60bc1-124">Receive a message(s)</span></span>  
  
- <span data-ttu-id="60bc1-125">メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="60bc1-125">Transmit a message(s)</span></span>  
  
- <span data-ttu-id="60bc1-126">動的ポートを使用してメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="60bc1-126">Transmit a message using a dynamic port</span></span>  
  
- <span data-ttu-id="60bc1-127">受信場所を無効にします。</span><span class="sxs-lookup"><span data-stu-id="60bc1-127">Disable receive locations</span></span>  
  
- <span data-ttu-id="60bc1-128">更新の構成</span><span class="sxs-lookup"><span data-stu-id="60bc1-128">Update configuration</span></span>  
  
- <span data-ttu-id="60bc1-129">受信し、送信アダプタの両方について、windows サービスが作業していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="60bc1-129">Ensure service windows are working for both receive and send adapters</span></span>  
  
- <span data-ttu-id="60bc1-130">トランザクション アダプターのトランザクションの整合性を確認します。</span><span class="sxs-lookup"><span data-stu-id="60bc1-130">Ensure transactional integrity for transacted adapters</span></span>  
  
  <span data-ttu-id="60bc1-131">ネガティブ テストする必要がありますが含まれますに限定されません。</span><span class="sxs-lookup"><span data-stu-id="60bc1-131">Negative tests should include but not be limited to:</span></span>  
  
- <span data-ttu-id="60bc1-132">問題のあるメッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="60bc1-132">Receive a bad message(s)</span></span>  
  
- <span data-ttu-id="60bc1-133">混在するバッチのメッセージ、正常なメッセージと問題のある受信します。</span><span class="sxs-lookup"><span data-stu-id="60bc1-133">Receive a mixed batch of messages, some good and some bad</span></span>  
  
- <span data-ttu-id="60bc1-134">エラーを送信します。</span><span class="sxs-lookup"><span data-stu-id="60bc1-134">Transmit failure</span></span>  
  
- <span data-ttu-id="60bc1-135">再試行の成功</span><span class="sxs-lookup"><span data-stu-id="60bc1-135">Retry successful</span></span>  
  
- <span data-ttu-id="60bc1-136">再試行の失敗、成功した次のトランスポートへ移動</span><span class="sxs-lookup"><span data-stu-id="60bc1-136">Retry fails, move to next transport successful</span></span>  
  
- <span data-ttu-id="60bc1-137">次のトランスポートへの移行が失敗した場合、メッセージを中断</span><span class="sxs-lookup"><span data-stu-id="60bc1-137">Move to next transport fails, suspend message</span></span>  
  
- <span data-ttu-id="60bc1-138">メッセージの混在バッチを送信します。</span><span class="sxs-lookup"><span data-stu-id="60bc1-138">Transmit a mixed batch of messages</span></span>  
  
- <span data-ttu-id="60bc1-139">データベースのフェールオーバー</span><span class="sxs-lookup"><span data-stu-id="60bc1-139">Database failover</span></span>  
  
### <a name="stress-testing"></a><span data-ttu-id="60bc1-140">ストレス テスト</span><span class="sxs-lookup"><span data-stu-id="60bc1-140">Stress Testing</span></span>  
 <span data-ttu-id="60bc1-141">アダプターは、実行時コンポーネントは、そのため、実行時ソフトウェアの厳しい要件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="60bc1-141">Adapters are run-time components and as such should meet the stringent requirements for run-time software.</span></span> <span data-ttu-id="60bc1-142">通常、ストレス テストは実行時間が一定の負荷のシナリオを実行することによって。</span><span class="sxs-lookup"><span data-stu-id="60bc1-142">Typically stress testing is carried out by running scenarios under load for a period of time.</span></span> <span data-ttu-id="60bc1-143">さらに高負荷と低負荷の平均時間故障間隔テスト実行するか、アダプターが測定期間の負荷の下で実行するため。</span><span class="sxs-lookup"><span data-stu-id="60bc1-143">Further high-stress and low-stress mean time between failure tests should be performed, whereby the adapter is run under load for a measured time period.</span></span>  
  
 <span data-ttu-id="60bc1-144">大まかなガイドラインとしてこれらのテスト実行されている可能性、アダプターで約 72 時間の高い負荷で、アダプターを経由してメッセージの数によって、周囲に 80 ~ 90% の CPU 使用率。</span><span class="sxs-lookup"><span data-stu-id="60bc1-144">Some rough guidelines for these tests might be running the adapter at high stress for around 72 hours, where the number of messages through the adapter causes the CPU utilization to be around of 80 to 90 percent.</span></span> <span data-ttu-id="60bc1-145">低負荷、CPU 使用率が約 120 時間の約 30 ~ 40% になります。</span><span class="sxs-lookup"><span data-stu-id="60bc1-145">For low stress, the CPU utilization would be around 30 to 40 percent for around 120 hours.</span></span>  
  
### <a name="performance-testing"></a><span data-ttu-id="60bc1-146">パフォーマンス テスト</span><span class="sxs-lookup"><span data-stu-id="60bc1-146">Performance Testing</span></span>  
 <span data-ttu-id="60bc1-147">パフォーマンスを考慮して、アダプターを開発する必要があります。</span><span class="sxs-lookup"><span data-stu-id="60bc1-147">Adapters should be developed with performance in mind.</span></span> <span data-ttu-id="60bc1-148">アダプターをリリースする前に、そのパフォーマンスを検証する必要があります。</span><span class="sxs-lookup"><span data-stu-id="60bc1-148">Before releasing an adapter you should validate its performance.</span></span> <span data-ttu-id="60bc1-149">そのパフォーマンスがスケール アップとスケール アウト; ことを確認することが重要個以上の Cpu を追加する潜在顧客パフォーマンスが向上するようコンピューターを追加します。</span><span class="sxs-lookup"><span data-stu-id="60bc1-149">It is important to ensure that its performance scales up and scales out; that is, adding more CPUs leads to a performance increase as does adding more computers.</span></span> <span data-ttu-id="60bc1-150">コードのプロファイリングは、パフォーマンス ボトルネックの解消に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="60bc1-150">Profiling the code can help to eliminate performance bottlenecks.</span></span>