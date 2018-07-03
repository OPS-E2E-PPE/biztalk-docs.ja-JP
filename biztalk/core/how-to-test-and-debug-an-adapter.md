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
ms.openlocfilehash: 5d0c28247b432e69e2501322ccc700033b5aa254
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004035"
---
# <a name="how-to-test-and-debug-an-adapter"></a><span data-ttu-id="901dc-102">アダプターをテストおよびデバッグする方法</span><span class="sxs-lookup"><span data-stu-id="901dc-102">How to Test and Debug an Adapter</span></span>
<span data-ttu-id="901dc-103">実行時の問題のデバッグでは、多くの場合、多角的なアプローチが必要になります。</span><span class="sxs-lookup"><span data-stu-id="901dc-103">Debugging run-time problems often requires a multifaceted approach.</span></span> <span data-ttu-id="901dc-104">問題やソフトウェアのバグの原因を突き止めるには、ソフトウェア トレース、パフォーマンス カウンター、イベント ログのエントリ、Windows Management Instrumentation (WMI) イベント、ソース コードのデバッグなど、さまざまなソースからデータを収集する必要があります。</span><span class="sxs-lookup"><span data-stu-id="901dc-104">Data must be gathered from multiple sources such as software tracing, performance counters, event log entries, Windows Management Instrumentation (WMI) events, and debugging source code to determine the cause of problems or software bugs.</span></span>  
  
 <span data-ttu-id="901dc-105">受信アダプターと送信アダプターは BizTalk サービスのアドレス空間で動作するので、アダプターをデバッグするには、BtsNtSvc.exe のプロセスにデバッガーをアタッチする必要があります。</span><span class="sxs-lookup"><span data-stu-id="901dc-105">Because receive and send adapters run in the address space of the BizTalk service the debugger needs to be attached to the BtsNtSvc.exe process to debug an adapter.</span></span> <span data-ttu-id="901dc-106">ただし、分離受信アダプターの場合は、そのアダプターをホストしているプロセスにデバッガーをアタッチします。</span><span class="sxs-lookup"><span data-stu-id="901dc-106">However for isolated receive adapters, the debugger needs to be attached to the process that hosts the adapter.</span></span>  
  
 <span data-ttu-id="901dc-107">トラブルシューティングで使用する実行時の診断情報を取得するには、アダプターの実行時コードにトレース コードを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="901dc-107">The adapter run-time code should be instrumented with tracing code to capture run-time diagnostics for troubleshooting.</span></span> <span data-ttu-id="901dc-108">これには、Microsoft Enterprise Instrumentation Framework (EIF) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="901dc-108">You can do this by using the Microsoft Enterprise Instrumentation Framework (EIF).</span></span> <span data-ttu-id="901dc-109">一般に、さまざまな重要度のトレース ステートメントを追加すると便利です (エラー状態のみのトレース、エラーと警告のトレース、エラー、警告、および情報ステートメントのトレースなど)。</span><span class="sxs-lookup"><span data-stu-id="901dc-109">Typically it is useful to add trace statements for different levels of severity, for example, tracing for error conditions only, tracing for errors and warnings, and finally tracing for errors, warnings, and informational statements.</span></span> <span data-ttu-id="901dc-110">さらより複雑なアダプターには、互いから分離して追跡する必要がある個々 のサブシステムがあります。</span><span class="sxs-lookup"><span data-stu-id="901dc-110">Further, more complex adapters may have separate subsystems that need to be traced in isolation from each other.</span></span> <span data-ttu-id="901dc-111">たとえば、ネットワーク サブシステムとコア サブシステムを持つアダプターなどがあります。すべてのサブシステムのトレースを有効にすると、場合によっては大量の "ノイズ" が生成されてしまいます。</span><span class="sxs-lookup"><span data-stu-id="901dc-111">For example, an adapter may have a network subsubsystem and a core subsystem; enabling tracing for all subsystems may generate an excessive amount of "noise" in some scenarios.</span></span>  
  
 <span data-ttu-id="901dc-112">アダプターの実行時の動作についてより多くの情報を収集するには、パフォーマンス カウンターを追加して実行時の速度や値を取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="901dc-112">Performance counters should be added to capture rates and values at run time to give more information about the run-time behavior of the adapter.</span></span> <span data-ttu-id="901dc-113">たとえば、送信されたメッセージの実際の数 (エンドポイントごと) やメッセージの送信速度 (メッセージ/秒) などのパフォーマンス カウンターをアダプターで発行できます。</span><span class="sxs-lookup"><span data-stu-id="901dc-113">For example, an adapter might publish performance counters for the raw numbers of messages sent on a per-endpoint basis as well as the rate of messages sent per second.</span></span>  
  
 <span data-ttu-id="901dc-114">重大なエラーのシナリオでは、WMI イベントが役に立つ場合もあります。</span><span class="sxs-lookup"><span data-stu-id="901dc-114">WMI events may also be useful for some critical error scenarios.</span></span>  <span data-ttu-id="901dc-115">たとえば、アダプターで重大なエラーが発生して受信場所がシャットダウンされた場合に WMI イベントが発生するようにしておけば、管理者がそのイベントを受け取って適切な措置をとることができます。</span><span class="sxs-lookup"><span data-stu-id="901dc-115">For instance if an adapter hits a critical error that causes it to shut down a receive location, firing a WMI event allows an administrator to listen on that event and take appropriate action.</span></span>  
  
## <a name="adapter-testing"></a><span data-ttu-id="901dc-116">アダプターのテスト</span><span class="sxs-lookup"><span data-stu-id="901dc-116">Adapter Testing</span></span>  
 <span data-ttu-id="901dc-117">BizTalk Server のカスタム アダプターを開発する際には、エンタープライズ ソフトウェア品質で開発する必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="901dc-117">When you develop a custom adapter for BizTalk Server, remember that it should be developed to enterprise software quality.</span></span> <span data-ttu-id="901dc-118">つまり、アダプターを出荷する前に徹底的なテストを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="901dc-118">This means that you need to test the adapter thoroughly before shipping it.</span></span> <span data-ttu-id="901dc-119">ここでは、アダプターのテストの方法を細かく説明することはできませんが、何をすればよいのかを大まかに説明します。</span><span class="sxs-lookup"><span data-stu-id="901dc-119">While it does not completely detail how adapters should be tested, this section gives an idea of what needs to be done.</span></span> <span data-ttu-id="901dc-120">一般に、3 つのカテゴリをカバー アダプターなどの実行時のコードをテストする必要があります。 機能テスト、ストレス テスト、およびパフォーマンスをテストします。</span><span class="sxs-lookup"><span data-stu-id="901dc-120">In general the testing of run-time code such as adapters should cover three broad categories: functional testing, stress testing, and performance testing.</span></span>  
  
### <a name="function-testing"></a><span data-ttu-id="901dc-121">機能テスト</span><span class="sxs-lookup"><span data-stu-id="901dc-121">Function Testing</span></span>  
 <span data-ttu-id="901dc-122">アダプターの機能のすべての組み合わせをテストする必要があります (ポジティブ テストとネガティブ テストの両方を含む)。</span><span class="sxs-lookup"><span data-stu-id="901dc-122">The adapter should be tested for all permutations of its functionality, including both positive tests and negative tests.</span></span> <span data-ttu-id="901dc-123">ポジティブ テストには少なくとも次のシナリオが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="901dc-123">Positive tests should include but not be limited to the following scenarios:</span></span>  
  
- <span data-ttu-id="901dc-124">メッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="901dc-124">Receive a message(s)</span></span>  
  
- <span data-ttu-id="901dc-125">メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="901dc-125">Transmit a message(s)</span></span>  
  
- <span data-ttu-id="901dc-126">動的ポートによるメッセージの送信</span><span class="sxs-lookup"><span data-stu-id="901dc-126">Transmit a message using a dynamic port</span></span>  
  
- <span data-ttu-id="901dc-127">受信場所を無効にします。</span><span class="sxs-lookup"><span data-stu-id="901dc-127">Disable receive locations</span></span>  
  
- <span data-ttu-id="901dc-128">構成の更新</span><span class="sxs-lookup"><span data-stu-id="901dc-128">Update configuration</span></span>  
  
- <span data-ttu-id="901dc-129">受信アダプターと送信アダプターの両方でサービス時間帯が機能していることの確認</span><span class="sxs-lookup"><span data-stu-id="901dc-129">Ensure service windows are working for both receive and send adapters</span></span>  
  
- <span data-ttu-id="901dc-130">トランザクション アダプターのトランザクション整合性の確認</span><span class="sxs-lookup"><span data-stu-id="901dc-130">Ensure transactional integrity for transacted adapters</span></span>  
  
  <span data-ttu-id="901dc-131">ネガティブ テストには少なくとも次のシナリオが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="901dc-131">Negative tests should include but not be limited to:</span></span>  
  
- <span data-ttu-id="901dc-132">問題のあるメッセージの受信</span><span class="sxs-lookup"><span data-stu-id="901dc-132">Receive a bad message(s)</span></span>  
  
- <span data-ttu-id="901dc-133">正常なメッセージと問題のあるメッセージが混在するバッチの受信</span><span class="sxs-lookup"><span data-stu-id="901dc-133">Receive a mixed batch of messages, some good and some bad</span></span>  
  
- <span data-ttu-id="901dc-134">エラーを送信します。</span><span class="sxs-lookup"><span data-stu-id="901dc-134">Transmit failure</span></span>  
  
- <span data-ttu-id="901dc-135">再試行の成功</span><span class="sxs-lookup"><span data-stu-id="901dc-135">Retry successful</span></span>  
  
- <span data-ttu-id="901dc-136">再試行の失敗、次のトランスポートへの移動の成功</span><span class="sxs-lookup"><span data-stu-id="901dc-136">Retry fails, move to next transport successful</span></span>  
  
- <span data-ttu-id="901dc-137">次のトランスポートへの移動の失敗、メッセージの保留</span><span class="sxs-lookup"><span data-stu-id="901dc-137">Move to next transport fails, suspend message</span></span>  
  
- <span data-ttu-id="901dc-138">メッセージの混在バッチの送信</span><span class="sxs-lookup"><span data-stu-id="901dc-138">Transmit a mixed batch of messages</span></span>  
  
- <span data-ttu-id="901dc-139">データベース フェールオーバー</span><span class="sxs-lookup"><span data-stu-id="901dc-139">Database failover</span></span>  
  
### <a name="stress-testing"></a><span data-ttu-id="901dc-140">ストレス テスト</span><span class="sxs-lookup"><span data-stu-id="901dc-140">Stress Testing</span></span>  
 <span data-ttu-id="901dc-141">アダプターは実行時コンポーネントなので、実行時ソフトウェアの厳しい要件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="901dc-141">Adapters are run-time components and as such should meet the stringent requirements for run-time software.</span></span> <span data-ttu-id="901dc-142">通常、ストレス テストは、負荷状況下で一定の期間シナリオを実行することによって行われます。</span><span class="sxs-lookup"><span data-stu-id="901dc-142">Typically stress testing is carried out by running scenarios under load for a period of time.</span></span> <span data-ttu-id="901dc-143">さらに、アダプターを負荷状況下で一定の期間実行する高負荷と低負荷の平均故障間隔テストを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="901dc-143">Further high-stress and low-stress mean time between failure tests should be performed, whereby the adapter is run under load for a measured time period.</span></span>  
  
 <span data-ttu-id="901dc-144">これらのテストの大まかなガイドラインとしては、アダプターを高負荷 (アダプターを通過するメッセージの数によって CPU の使用率が 80 ～ 90% になる状態) で約 72 時間実行し、</span><span class="sxs-lookup"><span data-stu-id="901dc-144">Some rough guidelines for these tests might be running the adapter at high stress for around 72 hours, where the number of messages through the adapter causes the CPU utilization to be around of 80 to 90 percent.</span></span> <span data-ttu-id="901dc-145">低負荷 (CPU の使用率が 30 ～ 40%) で約 120 時間実行します。</span><span class="sxs-lookup"><span data-stu-id="901dc-145">For low stress, the CPU utilization would be around 30 to 40 percent for around 120 hours.</span></span>  
  
### <a name="performance-testing"></a><span data-ttu-id="901dc-146">パフォーマンス テスト</span><span class="sxs-lookup"><span data-stu-id="901dc-146">Performance Testing</span></span>  
 <span data-ttu-id="901dc-147">アダプターは、パフォーマンスを念頭に置いて開発する必要があります。</span><span class="sxs-lookup"><span data-stu-id="901dc-147">Adapters should be developed with performance in mind.</span></span> <span data-ttu-id="901dc-148">アダプターをリリースする前にパフォーマンスを検証してください。</span><span class="sxs-lookup"><span data-stu-id="901dc-148">Before releasing an adapter you should validate its performance.</span></span> <span data-ttu-id="901dc-149">パフォーマンスのスケール アップとスケール アウトに対応していることが重要です。つまり、CPU を追加した場合も、コンピューターを追加した場合と同様にパフォーマンスが向上するようにします。</span><span class="sxs-lookup"><span data-stu-id="901dc-149">It is important to ensure that its performance scales up and scales out; that is, adding more CPUs leads to a performance increase as does adding more computers.</span></span> <span data-ttu-id="901dc-150">コードのプロファイリングはパフォーマンス ボトルネックの解消に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="901dc-150">Profiling the code can help to eliminate performance bottlenecks.</span></span>