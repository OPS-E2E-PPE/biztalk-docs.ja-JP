---
title: サーバーのシナリオ アーキテクチャのテスト |Microsoft ドキュメント
ms.custom: ''
ms.date: 2015-12-09
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1e3afb57-c3ff-4314-9605-cf9fe936e63f
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 49a51244b7033c6cebc978a39ad37dd5732fa38d
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
ms.locfileid: "26010851"
---
# <a name="test-scenario-server-architecture"></a><span data-ttu-id="1cfd4-102">テスト シナリオのサーバーのアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="1cfd4-102">Test Scenario Server Architecture</span></span>
<span data-ttu-id="1cfd4-103">このトピックでは、ロード テスト中にサーバーと、ロード テストの実行対象となる、個別のサーバーのアーキテクチャ間のメッセージ フローの概要を示します。</span><span class="sxs-lookup"><span data-stu-id="1cfd4-103">This topic provides an overview of the flow of messages between servers during load testing and the distinct server architectures against which the load test was performed.</span></span>  
  
## <a name="overview-of-message-flow-during-load-testing"></a><span data-ttu-id="1cfd4-104">ロード テスト中にメッセージ フローの概要</span><span class="sxs-lookup"><span data-stu-id="1cfd4-104">Overview of Message Flow During Load Testing</span></span>  
 <span data-ttu-id="1cfd4-105">次の図は、ロード テスト中にサーバー間でメッセージのフローとすべてのテスト シナリオに使用されるサーバー アーキテクチャのジェネリックの概要を説明します。</span><span class="sxs-lookup"><span data-stu-id="1cfd4-105">The following diagram provides a generic overview of the server architecture used for all test scenarios and the flow of messages between servers during a load test.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1cfd4-106">各テストされた個別のサーバー アーキテクチャは、セクションで説明**基準サーバー アーキテクチャ**です。</span><span class="sxs-lookup"><span data-stu-id="1cfd4-106">Each distinct server architecture that was tested is described in the section **Baseline Server Architecture**.</span></span>  
  
 <span data-ttu-id="1cfd4-107">次の図は、メッセージ フローの概要を示します。</span><span class="sxs-lookup"><span data-stu-id="1cfd4-107">The following figure provides an overview of the message flow.</span></span> <span data-ttu-id="1cfd4-108">図の番号は、以下の図に示す手順に対応します。</span><span class="sxs-lookup"><span data-stu-id="1cfd4-108">The numbers in the figure correspond to the steps listed below the figure.</span></span>  
  
 <span data-ttu-id="1cfd4-109">![メッセージ フローの概要](../technical-guides/media/archmsgflow.gif "ArchMsgFlow")</span><span class="sxs-lookup"><span data-stu-id="1cfd4-109">![Message Flow Overview](../technical-guides/media/archmsgflow.gif "ArchMsgFlow")</span></span>  
<span data-ttu-id="1cfd4-110">メッセージ フローの概要</span><span class="sxs-lookup"><span data-stu-id="1cfd4-110">Message Flow Overview</span></span>  
  
1.  <span data-ttu-id="1cfd4-111">ロード テストがロード エージェント コント ローラー コンピューターで開始される**VSTS_TestController**:</span><span class="sxs-lookup"><span data-stu-id="1cfd4-111">Load testing is initiated by the Load Agent Controller computer **VSTS_TestController**:</span></span>  
  
    -   <span data-ttu-id="1cfd4-112">上の Visual Studio 2008 プロジェクト**VSTS_TestController**を実行します。</span><span class="sxs-lookup"><span data-stu-id="1cfd4-112">A Visual Studio 2008 project on **VSTS_TestController** is executed.</span></span> <span data-ttu-id="1cfd4-113">プロジェクトは、指定された BizUnit XML 構成ファイルを読み込みます、および BizUnit 構成ファイルで定義されているステップの実行を開始する BizUnit クラスのインスタンスを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="1cfd4-113">The project loads an instance of the BizUnit class, loads the specified BizUnit XML configuration file, and begins executing the steps defined in the BizUnit configuration file.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="1cfd4-114">BizUnit によって使用される XML 構成ファイルの詳細についてを参照してください「の定義のテストを使用して、XML 構成ファイル」に[http://go.microsoft.com/fwlink/?LinkId=143432](http://go.microsoft.com/fwlink/?LinkId=143432)です。</span><span class="sxs-lookup"><span data-stu-id="1cfd4-114">For more information about the XML configuration file used by BizUnit, see the topic “Defining Tests Using an XML Configuration File” at [http://go.microsoft.com/fwlink/?LinkId=143432](http://go.microsoft.com/fwlink/?LinkId=143432).</span></span>  
  
    -   <span data-ttu-id="1cfd4-115">「準備」テストの実行に準備メッセージを送信を開始するように求めるダイアログ ボックスを表示するコマンドを実行するテストのセットアップ手順を完了すると、BizUnit プロジェクト」の手順のいずれか、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境。</span><span class="sxs-lookup"><span data-stu-id="1cfd4-115">After completing the Test Setup steps, one of the steps in the BizUnit project executes a command that displays a dialog box which prompts you to start a “priming” test run to submit priming messages to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment.</span></span>  
  
    -   <span data-ttu-id="1cfd4-116">準備メッセージは、別の Visual Studio 2008 のテスト プロジェクトから送信された**VSTS_TestController**です。</span><span class="sxs-lookup"><span data-stu-id="1cfd4-116">Priming messages are submitted from a separate Visual Studio 2008 Test project on **VSTS_TestController**.</span></span> <span data-ttu-id="1cfd4-117">"ウォーム アップする"テスト環境システム キャッシュを初期化することによって、準備メッセージが送信されます。</span><span class="sxs-lookup"><span data-stu-id="1cfd4-117">Priming messages are sent to “warm up” the test environment by initializing system caches.</span></span>  
  
    -   <span data-ttu-id="1cfd4-118">すべての事前通知メッセージが処理されます。BizUnit インスタンスは、メインのテスト実行でテストされているすべてのコンピューターのパフォーマンス モニター カウンターを読み込んで、メインのテストの実行用のメッセージを送信する入力を求められる ダイアログ ボックスを表示するコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="1cfd4-118">After all priming messages have been processed; the BizUnit instance loads Performance Monitor counters for all computers being tested in the main test run and executes a command to display a dialog box which prompts you to submit messages for the main test run.</span></span>  
  
    -   <span data-ttu-id="1cfd4-119">Visual Studio 2008 のロード テスト プロジェクトに**VSTS_TestController**メイン テストの実行のメッセージを送信するロード テスト エージェント コンピューターに指示します。</span><span class="sxs-lookup"><span data-stu-id="1cfd4-119">The Visual Studio 2008 Load Test project on **VSTS_TestController** directs the Load Test Agent computers to submit messages for the main test run.</span></span>  
  
2.  <span data-ttu-id="1cfd4-120">テストがロード テスト エージェント コンピューターである送信メッセージに、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ロード テスト コント ローラー コンピューターに Visual Studio 2008 のロード テスト プロジェクトの app.config ファイルで指定されているコンピューター (**VSTS_TestController**)。</span><span class="sxs-lookup"><span data-stu-id="1cfd4-120">The Load Test Agent computers submit test messages to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computers specified in the app.config file of the Visual Studio 2008 Load Test project on the Load Test Controller computer (**VSTS_TestController**).</span></span>  
  
3.  <span data-ttu-id="1cfd4-121">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]コンピューターには、ロード テスト エージェント コンピューターによって送信されるメッセージが表示される、このロード テストの 2 つの方法でメッセージが受信された要求-応答の受信場所。</span><span class="sxs-lookup"><span data-stu-id="1cfd4-121">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computers receive the messages submitted by the Load Test Agent computers, for this load test the messages were received by a two way request-response receive location.</span></span>  
  
    -   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="1cfd4-122">メッセージ ボックス データベースにメッセージを公開します。</span><span class="sxs-lookup"><span data-stu-id="1cfd4-122"> publishes the message to the MessageBox database.</span></span>  
  
    -   <span data-ttu-id="1cfd4-123">メッセージは、オーケストレーションによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="1cfd4-123">The messages are consumed by an orchestration.</span></span>  
  
    -   <span data-ttu-id="1cfd4-124">オーケストレーションは、送信請求-応答送信ポート、ダウン ストリームの電卓サービスを呼び出す 2 つの方法にバインドされます。</span><span class="sxs-lookup"><span data-stu-id="1cfd4-124">The orchestration is bound to a two way solicit-response send port which invokes the downstream calculator service.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="1cfd4-125">ダウン ストリームの電卓サービスがで説明されている Windows Communication Foundation サンプルに基づいて[http://go.microsoft.com/fwlink/?LinkId=141762](http://go.microsoft.com/fwlink/?LinkId=141762)です。</span><span class="sxs-lookup"><span data-stu-id="1cfd4-125">The downstream calculator service is based upon Windows Communication Foundation samples described at [http://go.microsoft.com/fwlink/?LinkId=141762](http://go.microsoft.com/fwlink/?LinkId=141762).</span></span> <span data-ttu-id="1cfd4-126">Windows Communication Foundation サンプルはダウンロード[http://go.microsoft.com/fwlink/?LinkId=87352](http://go.microsoft.com/fwlink/?LinkId=87352)です。</span><span class="sxs-lookup"><span data-stu-id="1cfd4-126">The Windows Communication Foundation samples are available for download at [http://go.microsoft.com/fwlink/?LinkId=87352](http://go.microsoft.com/fwlink/?LinkId=87352).</span></span>  
  
4.  <span data-ttu-id="1cfd4-127">電卓サービスからの要求を消費する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]に応答を返します、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]送信請求-応答送信ポート。</span><span class="sxs-lookup"><span data-stu-id="1cfd4-127">The calculator service consumes the request from [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and returns a response to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] solicit-response send port.</span></span>  
  
5.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="1cfd4-128">応答を処理し、メッセージ ボックス データベースへの応答メッセージが引き続き発生します。</span><span class="sxs-lookup"><span data-stu-id="1cfd4-128"> processes the response and persists the response message to the MessageBox database.</span></span> <span data-ttu-id="1cfd4-129">その後、電卓の web サービスからの応答メッセージを BizTalk 要求-応答ポートでメッセージ ボックス データベースから取得され、応答メッセージは、ロード テスト エージェント コンピューターに配信されます。</span><span class="sxs-lookup"><span data-stu-id="1cfd4-129">Then the response message from the Calculator web service is retrieved from the MessageBox database by the BizTalk request-response port, and a response message is delivered back to the Load Test Agent computers.</span></span>  
  
## <a name="baseline-server-architecture"></a><span data-ttu-id="1cfd4-130">ベースライン サーバー アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="1cfd4-130">Baseline Server Architecture</span></span>  
 <span data-ttu-id="1cfd4-131">Hyper-v の役割がインストールされていない、ベースライン サーバー アーキテクチャの両方と[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ホスト オペレーティング システムにインストールされた SQL Server とします。</span><span class="sxs-lookup"><span data-stu-id="1cfd4-131">For the Baseline Server architecture, the Hyper-V role was not installed and Both [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and SQL Server were installed on to the host operating system.</span></span> <span data-ttu-id="1cfd4-132">これは、「ベースライン」パフォーマンス メトリックを確立するために、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]物理ハードウェア環境のソリューションです。</span><span class="sxs-lookup"><span data-stu-id="1cfd4-132">This was done to establish “baseline” performance metrics of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] solution on a physical hardware environment.</span></span>  
  
 <span data-ttu-id="1cfd4-133">次の図に、物理[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]および基準サーバー アーキテクチャの SQL Server 層です。</span><span class="sxs-lookup"><span data-stu-id="1cfd4-133">The following figure depicts the physical [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and SQL Server tiers for the Baseline Server Architecture.</span></span>  
  
 <span data-ttu-id="1cfd4-134">![物理 BizTalk & #47。物理 SQL](../technical-guides/media/archphysicalbts-physicalsql.gif "ArchPhysicalBTS_PhysicalSQL")</span><span class="sxs-lookup"><span data-stu-id="1cfd4-134">![Physical BizTalk &#47; Physical SQL](../technical-guides/media/archphysicalbts-physicalsql.gif "ArchPhysicalBTS_PhysicalSQL")</span></span>  
<span data-ttu-id="1cfd4-135">物理的な BizTalk Server/物理 SQL Server (ベースライン)</span><span class="sxs-lookup"><span data-stu-id="1cfd4-135">Physical BizTalk Server / Physical SQL Server (Baseline)</span></span>  
  
-   <span data-ttu-id="1cfd4-136">**BizTalk Server** 2 - 次のように構成されている BizTalk Server コンピューター。</span><span class="sxs-lookup"><span data-stu-id="1cfd4-136">**BizTalk Server** - 2 BizTalk Server computers configured as follows:</span></span>  
  
    -   <span data-ttu-id="1cfd4-137">1 つ[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を使用してコンピューター **6** GB の RAM と**8**プロセッサ コアを使用できます。</span><span class="sxs-lookup"><span data-stu-id="1cfd4-137">One [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computer with **6** GB RAM and **8** processor cores available.</span></span>  
  
    -   <span data-ttu-id="1cfd4-138">1 つ[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を使用してコンピューター **3** GB の RAM と**4**プロセッサ コアを使用できます。</span><span class="sxs-lookup"><span data-stu-id="1cfd4-138">One [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computer with **3** GB RAM and **4** processor cores available.</span></span>  
  
    -   <span data-ttu-id="1cfd4-139">6 + 3 の合計 = **9** GB RAM と 8 + 4 = **12**プロセッサ コアの利用可能な[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="1cfd4-139">Total of 6 + 3 = **9** GB RAM available and 8 + 4 = **12** processor cores available for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="1cfd4-140">**SQL Server** -次のように構成されている SQL Server コンピューターが 1 台。</span><span class="sxs-lookup"><span data-stu-id="1cfd4-140">**SQL Server** - 1 SQL Server computer configured as follows:</span></span>  
  
    -   <span data-ttu-id="1cfd4-141">**8** GB の RAM が使用できます。</span><span class="sxs-lookup"><span data-stu-id="1cfd4-141">**8** GB RAM available.</span></span>  
  
    -   <span data-ttu-id="1cfd4-142">**4**プロセッサ コアを使用できます。</span><span class="sxs-lookup"><span data-stu-id="1cfd4-142">**4** processor cores available.</span></span>  
  
## <a name="virtual-biztalk-server--physical-sql-server"></a><span data-ttu-id="1cfd4-143">BizTalk Server の仮想/物理 SQL Server</span><span class="sxs-lookup"><span data-stu-id="1cfd4-143">Virtual BizTalk Server / Physical SQL Server</span></span>  
 <span data-ttu-id="1cfd4-144">次の図では、仮想[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]と物理[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]階層。</span><span class="sxs-lookup"><span data-stu-id="1cfd4-144">The following figure depicts the virtual [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and physical [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] tiers.</span></span>  
  
 <span data-ttu-id="1cfd4-145">![仮想 BizTalk & #47。物理 SQL](../technical-guides/media/archvirtualbts-physicalsql.gif "ArchVirtualBTS_PhysicalSQL")</span><span class="sxs-lookup"><span data-stu-id="1cfd4-145">![Virtual BizTalk &#47; Physical SQL](../technical-guides/media/archvirtualbts-physicalsql.gif "ArchVirtualBTS_PhysicalSQL")</span></span>  
<span data-ttu-id="1cfd4-146">BizTalk Server の仮想/物理 SQL Server</span><span class="sxs-lookup"><span data-stu-id="1cfd4-146">Virtual BizTalk Server / Physical SQL Server</span></span>  
  
 <span data-ttu-id="1cfd4-147">このシナリオでは、ロード テストがに対して実行された[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]HYPER-V 仮想マシンと物理ハードウェア上で実行されている SQL Server で実行されています。</span><span class="sxs-lookup"><span data-stu-id="1cfd4-147">For this scenario, the load test was performed against [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] running on Hyper-V virtual machines and SQL Server running on physical hardware.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1cfd4-148">次に示すメモリおよびプロセッサのコアの割り当てが HYPER-V 仮想マシンまたは物理ハードウェア上で特定のコンピューターが実行しているかどうかをされている唯一の違いの各非基準シナリオと同じです。</span><span class="sxs-lookup"><span data-stu-id="1cfd4-148">The allocation of RAM and processor cores described below was identical for each non-baseline scenarios, the only difference being whether certain computers are running on a Hyper-V virtual machine or on physical hardware.</span></span>  
  
-   <span data-ttu-id="1cfd4-149">**BizTalk Server** - 3[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]次のように構成されている s コンピューター。</span><span class="sxs-lookup"><span data-stu-id="1cfd4-149">**BizTalk Server** - 3 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]s computers configured as follows:</span></span>  
  
    -   <span data-ttu-id="1cfd4-150">3 GB の RAM がそれぞれに割り当てられている[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]3 x 3 の合計を使用してコンピューター = **9** GB の RAM が使用できる[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="1cfd4-150">3 GB RAM allocated to each [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computer with a total of 3 x 3 = **9** GB RAM available for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
    -   <span data-ttu-id="1cfd4-151">4 コア プロセッサがそれぞれに割り当てられている[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]3 行 x 4 の合計を使用してコンピューター = **12**プロセッサ コアの利用可能な[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="1cfd4-151">4 processor cores allocated to each [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computer with a total of 3 x 4 = **12** processor cores available for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="1cfd4-152">**SQL Server** -次のように構成されている SQL Server コンピューターが 1 台。</span><span class="sxs-lookup"><span data-stu-id="1cfd4-152">**SQL Server** - 1 SQL Server computer configured as follows:</span></span>  
  
    -   <span data-ttu-id="1cfd4-153">**8** GB の RAM が使用できます。</span><span class="sxs-lookup"><span data-stu-id="1cfd4-153">**8** GB RAM available.</span></span>  
  
    -   <span data-ttu-id="1cfd4-154">**4**プロセッサ コアを使用できます。</span><span class="sxs-lookup"><span data-stu-id="1cfd4-154">**4** processor cores available.</span></span>  
  
## <a name="virtual-biztalk-server--virtual-sql-server"></a><span data-ttu-id="1cfd4-155">BizTalk Server の仮想/仮想 SQL Server</span><span class="sxs-lookup"><span data-stu-id="1cfd4-155">Virtual BizTalk Server / Virtual SQL Server</span></span>  
 <span data-ttu-id="1cfd4-156">次の図仮想[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]コンピューターをホストしているコンピューターと別の HYPER-V で仮想 SQL Server コンピューター。</span><span class="sxs-lookup"><span data-stu-id="1cfd4-156">The following figure depicts a virtual [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computer and a virtual SQL Server computer on separate Hyper-V host computers.</span></span>  
  
 <span data-ttu-id="1cfd4-157">![仮想 BizTalk & #47。仮想 SQL](../technical-guides/media/archvirtualbts-virtualsql.gif "ArchVirtualBTS_VirtualSQL")</span><span class="sxs-lookup"><span data-stu-id="1cfd4-157">![Virtual BizTalk &#47; Virtual SQL](../technical-guides/media/archvirtualbts-virtualsql.gif "ArchVirtualBTS_VirtualSQL")</span></span>  
<span data-ttu-id="1cfd4-158">BizTalk Server の仮想/仮想 SQL Server</span><span class="sxs-lookup"><span data-stu-id="1cfd4-158">Virtual BizTalk Server / Virtual SQL Server</span></span>  
  
 <span data-ttu-id="1cfd4-159">このシナリオでは、ロード テストがに対して実行された[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]HYPER-V 仮想マシンで実行されていると[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]HYPER-V 仮想マシンで実行します。</span><span class="sxs-lookup"><span data-stu-id="1cfd4-159">For this scenario, the load test was performed against [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] running on Hyper-V virtual machines and [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] running on a Hyper-V virtual machine.</span></span> <span data-ttu-id="1cfd4-160">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] HYPER-V 仮想マシンと[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]HYPER-V 仮想マシンが別の HYPER-V ホスト コンピューターで実行されました。</span><span class="sxs-lookup"><span data-stu-id="1cfd4-160">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Hyper-V virtual machines and the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Hyper-V virtual machine were run on separate Hyper-V host computers.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1cfd4-161">このシナリオでメモリおよびプロセッサ コアの割り当ては、割り当てメモリおよびプロセッサ コアのと同じ、 **BizTalk Server の仮想/物理 SQL Server**シナリオ、されていることが唯一の違い[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]されました物理ハードウェアではなく、HYPER-V 仮想マシン上で実行するように構成します。</span><span class="sxs-lookup"><span data-stu-id="1cfd4-161">The allocation of RAM and processor cores for this scenario is identical to the allocation of RAM and processor cores for the **Virtual BizTalk Server / Physical SQL Server** scenario, the only difference being that [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] was configured to run on a Hyper-V virtual machine rather than physical hardware.</span></span>  
  
## <a name="consolidated-environment"></a><span data-ttu-id="1cfd4-162">統合環境</span><span class="sxs-lookup"><span data-stu-id="1cfd4-162">Consolidated Environment</span></span>  
 <span data-ttu-id="1cfd4-163">次の図仮想[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]コンピューターと仮想 SQL Server コンピューターが 1 つの HYPER-V ホスト コンピューターに統合します。</span><span class="sxs-lookup"><span data-stu-id="1cfd4-163">The following figure depicts virtual [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computers and a virtual SQL Server computer consolidated on one Hyper-V host computer.</span></span>  
  
 <span data-ttu-id="1cfd4-164">![仮想 BizTalk & #47。仮想 SQL & #47。統合](../technical-guides/media/archvirtualbts-virtualsql-consolidated.gif "ArchVirtualBTS_VirtualSQL_Consolidated")</span><span class="sxs-lookup"><span data-stu-id="1cfd4-164">![Virtual BizTalk &#47; Virtual SQL &#47; Consolidated](../technical-guides/media/archvirtualbts-virtualsql-consolidated.gif "ArchVirtualBTS_VirtualSQL_Consolidated")</span></span>  
<span data-ttu-id="1cfd4-165">統合環境</span><span class="sxs-lookup"><span data-stu-id="1cfd4-165">Consolidated Environment</span></span>  
  
 <span data-ttu-id="1cfd4-166">このシナリオでは、ロード テストがに対して実行された[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]HYPER-V 仮想マシンで実行されていると[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]HYPER-V 仮想マシンで実行します。</span><span class="sxs-lookup"><span data-stu-id="1cfd4-166">For this scenario, the load test was performed against [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] running on Hyper-V virtual machines and [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] running on a Hyper-V virtual machine.</span></span> <span data-ttu-id="1cfd4-167">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] HYPER-V 仮想マシンと[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]HYPER-V 仮想マシンがすべて、同じ HYPER-V ホスト コンピューターで実行します。</span><span class="sxs-lookup"><span data-stu-id="1cfd4-167">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Hyper-V virtual machines and the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Hyper-V virtual machine were all run on the same Hyper-V host computer.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1cfd4-168">このシナリオでメモリおよびプロセッサ コアの割り当ては、割り当てメモリおよびプロセッサ コアのと同じ、**仮想の BizTalk Server/仮想 SQL Server**シナリオ、唯一の違いを両方、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]HYPER-V 仮想マシンと[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]HYPER-V 仮想マシンが同じ HYPER-V ホスト コンピューターで実行するように構成します。</span><span class="sxs-lookup"><span data-stu-id="1cfd4-168">The allocation of RAM and processor cores for this scenario is identical to the allocation of RAM and processor cores for the **Virtual BizTalk Server / Virtual SQL Server** scenario, the only difference being that both the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Hyper-V virtual machines and [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Hyper-V virtual machines were configured to run on the same Hyper-V host computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1cfd4-169">参照</span><span class="sxs-lookup"><span data-stu-id="1cfd4-169">See Also</span></span>  
 [<span data-ttu-id="1cfd4-170">テスト シナリオの概要</span><span class="sxs-lookup"><span data-stu-id="1cfd4-170">Test Scenario Overview</span></span>](../technical-guides/test-scenario-overview.md)