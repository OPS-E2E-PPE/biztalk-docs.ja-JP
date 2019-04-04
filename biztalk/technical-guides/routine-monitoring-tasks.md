---
title: タスクの監視ルーチン |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c2f9f56a-c839-4108-933d-69b00a1e3817
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d500e79cdf20c6a1914708976101715c2f00ae69
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001659"
---
# <a name="routine-monitoring-tasks"></a><span data-ttu-id="cccd0-102">定期的な監視タスク</span><span class="sxs-lookup"><span data-stu-id="cccd0-102">Routine Monitoring Tasks</span></span>
<span data-ttu-id="cccd0-103">定期的なスケジュールごとに次の監視タスクを実行する際に役立つを管理することで、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アプリケーションとインフラストラクチャを運用できる状態です。</span><span class="sxs-lookup"><span data-stu-id="cccd0-103">Performing the following monitoring tasks on a regularly scheduled basis will assist you in keeping your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] applications and infrastructure operationally ready.</span></span>  
  
## <a name="daily-monitoring-tasks"></a><span data-ttu-id="cccd0-104">毎日の監視タスク</span><span class="sxs-lookup"><span data-stu-id="cccd0-104">Daily Monitoring Tasks</span></span>  
  
- <span data-ttu-id="cccd0-105">すべてのオープン アラートを確認する。</span><span class="sxs-lookup"><span data-stu-id="cccd0-105">Review all open alerts.</span></span>  
  
- <span data-ttu-id="cccd0-106">使用して、**グループ ハブ**ページで、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールをオーケストレーション、ポート、およびメッセージのエラーを調査します。</span><span class="sxs-lookup"><span data-stu-id="cccd0-106">Use the **Group Hub** page in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console to investigate orchestration, port, and message failures.</span></span> <span data-ttu-id="cccd0-107">**グループ ハブ**ページがメッセージ ボックス データベース内のデータにアクセスする、システムの現在のリアルタイムの状態へのアクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="cccd0-107">The **Group Hub** page provides access to the current real-time state of the system, accessing data in the MessageBox database.</span></span> <span data-ttu-id="cccd0-108">オーケストレーション、ポート、メッセージングなどのすべてのサービス インスタンスと、それに関連するメッセージを表示できます。</span><span class="sxs-lookup"><span data-stu-id="cccd0-108">You can view all service instances such as orchestrations, ports, and messaging, along with their associated messages.</span></span> <span data-ttu-id="cccd0-109">使用して、**グループ ハブ**ページは次のアクティビティを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="cccd0-109">Using the **Group Hub** page you can perform the following activities:</span></span>  
  
  - <span data-ttu-id="cccd0-110">現在実行中のオーケストレーションなどのサービス インスタンスとメッセージング、およびその関連するメッセージを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cccd0-110">See currently running service instances, such as orchestrations and messaging, and their associated messages.</span></span>  
  
  - <span data-ttu-id="cccd0-111">現在のデータおよびシステムのリアルタイムの状態について、メッセージ ボックス データベースを調べます。</span><span class="sxs-lookup"><span data-stu-id="cccd0-111">Look into the MessageBox database for a view of the current data and the real-time state of the system.</span></span>  
  
  - <span data-ttu-id="cccd0-112">サービス インスタンスを中断、終了、および再開します。</span><span class="sxs-lookup"><span data-stu-id="cccd0-112">Suspend, terminate, and resume service instances.</span></span>  
  
    <span data-ttu-id="cccd0-113">使用しての詳細については、**グループ ハブ**ページを参照してください[ http://go.microsoft.com/fwlink/?LinkId=155281](http://go.microsoft.com/fwlink/?LinkId=155281)します。</span><span class="sxs-lookup"><span data-stu-id="cccd0-113">For more information about using the **Group Hub** page, see [http://go.microsoft.com/fwlink/?LinkId=155281](http://go.microsoft.com/fwlink/?LinkId=155281).</span></span>  
  
- <span data-ttu-id="cccd0-114">警告を見直す (省略可)。</span><span class="sxs-lookup"><span data-stu-id="cccd0-114">Review warnings (optional).</span></span>  
  
  <span data-ttu-id="cccd0-115">詳細については、[チェックリスト: 毎日のメンテナンス チェックを実行する](../technical-guides/checklist-performing-daily-maintenance-checks.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cccd0-115">For more information, see [Checklist: Performing Daily Maintenance Checks](../technical-guides/checklist-performing-daily-maintenance-checks.md).</span></span>  
  
## <a name="weekly-monitoring-tasks"></a><span data-ttu-id="cccd0-116">週単位の監視タスク</span><span class="sxs-lookup"><span data-stu-id="cccd0-116">Weekly Monitoring Tasks</span></span>  
  
- <span data-ttu-id="cccd0-117">1 週間あたり 1 回以上のイベント ログを確認します。</span><span class="sxs-lookup"><span data-stu-id="cccd0-117">Review the event logs at least once per week.</span></span> <span data-ttu-id="cccd0-118">このタスクの理由は、DBNetLib エラーが検出漏れなどの問題を防ぐためです。</span><span class="sxs-lookup"><span data-stu-id="cccd0-118">The reason for this task is to prevent issues, such as DBNetLib errors going undetected.</span></span> <span data-ttu-id="cccd0-119">非常に低待機時間システムがない限り、サービスの中断が気付かない場合があります。</span><span class="sxs-lookup"><span data-stu-id="cccd0-119">Service interruption might go unnoticed unless you have a very low latency system.</span></span> <span data-ttu-id="cccd0-120">ただし、これらのエラーのいくつか (例が多すぎるホストまたはメッセージ ボックス SQL ボックスなどのパフォーマンスの問題の数の BizTalk Server サーバー) の問題が大きくを示すことができます。</span><span class="sxs-lookup"><span data-stu-id="cccd0-120">However, some of these errors can indicate a bigger issue (for example, too many hosts or BizTalk Server servers for the number of message boxes, performance issues on the SQL box, etc).</span></span>  
  
  <span data-ttu-id="cccd0-121">詳細については、[チェックリスト: 毎週のメンテナンス チェックを実行する](../technical-guides/checklist-performing-weekly-maintenance-checks.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cccd0-121">For more information, see [Checklist: Performing Weekly Maintenance Checks](../technical-guides/checklist-performing-weekly-maintenance-checks.md).</span></span>  
  
## <a name="as-needed-tasks"></a><span data-ttu-id="cccd0-122">必要に応じてタスク</span><span class="sxs-lookup"><span data-stu-id="cccd0-122">As-Needed Tasks</span></span>  
  
- <span data-ttu-id="cccd0-123">監視をカスタマイズする規則を変更する、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アプリケーションとインフラストラクチャ。</span><span class="sxs-lookup"><span data-stu-id="cccd0-123">Modify the rules to customize the monitoring of your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] applications and infrastructure.</span></span>  
  
- <span data-ttu-id="cccd0-124">ログのパフォーマンス分析ツール (PAL) を実行します。</span><span class="sxs-lookup"><span data-stu-id="cccd0-124">Run the Performance Analysis of Logs tool (PAL).</span></span> <span data-ttu-id="cccd0-125">場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]デプロイがかなり高く (たとえば、新しい取引先パートナーは、定期的に追加されていない新しいコードが展開されていない)、実行する Perfmon および PAL 四半期に 1 回またはごとの 6 か月です。</span><span class="sxs-lookup"><span data-stu-id="cccd0-125">If your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] deployment is fairly constant (for example, new trading partners aren't added routinely, new code is not deployed), you might run Perfmon and PAL once a quarter or even every six months.</span></span> <span data-ttu-id="cccd0-126">場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]配置の変更より頻繁にすることもパフォーマンス モニターを実行して、PAL の数を基準と比較するか月ごと。</span><span class="sxs-lookup"><span data-stu-id="cccd0-126">If your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] deployment changes more frequently, you may want to run Perfmon and PAL every couple of months to compare against a baseline.</span></span> <span data-ttu-id="cccd0-127">PAL の詳細については、[パフォーマンス分析のログ (PAL) ツールを使用して](../technical-guides/using-the-performance-analysis-of-logs-pal-tool.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cccd0-127">For more information on PAL, see [Using the Performance Analysis of Logs (PAL) Tool](../technical-guides/using-the-performance-analysis-of-logs-pal-tool.md).</span></span>  
  
- <span data-ttu-id="cccd0-128">実行のパフォーマンス モニターで変更の数によっては四半期に 1 回または回 6 か月に、すべての数か月に発生する、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]展開します。</span><span class="sxs-lookup"><span data-stu-id="cccd0-128">Run Perfmon every few months, to once a quarter or even every six months depending on the number of changes occur in your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] deployment.</span></span>  
  
- <span data-ttu-id="cccd0-129">BizTalk Server のベスト プラクティス アナライザーを実行するときに、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]配置の変更 (新しいアプリケーションの追加など) や、新しいホストの作成。</span><span class="sxs-lookup"><span data-stu-id="cccd0-129">Run BizTalk Server Best Practices Analyzer when the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] deployment changes (for example, the addition of new applications or creation of new hosts).</span></span> <span data-ttu-id="cccd0-130">BizTalk Server ベスト プラクティス アナライザーでダウンロードできます[ http://go.microsoft.com/fwlink/?LinkId=83317](http://go.microsoft.com/fwlink/?LinkId=83317)します。</span><span class="sxs-lookup"><span data-stu-id="cccd0-130">You can download the BizTalk Server Best Practices Analyzer at [http://go.microsoft.com/fwlink/?LinkId=83317](http://go.microsoft.com/fwlink/?LinkId=83317).</span></span>  
  
- <span data-ttu-id="cccd0-131">実行、 [BizTalk MsgBoxViewer ツール](http://go.microsoft.com/fwlink/?LinkId=151930)(http://go.microsoft.com/fwlink/?LinkId=151930)します。</span><span class="sxs-lookup"><span data-stu-id="cccd0-131">Run the [BizTalk MsgBoxViewer tool](http://go.microsoft.com/fwlink/?LinkId=151930) (http://go.microsoft.com/fwlink/?LinkId=151930).</span></span> <span data-ttu-id="cccd0-132">このツールは、BizTalk メッセージ ボックスとその他のデータベースを分析し、その他の情報がデータベースに関連している場合、警告を含む、HTML レポートが生成されます。</span><span class="sxs-lookup"><span data-stu-id="cccd0-132">This tool analyzes the BizTalk MessageBox and other databases and generates an HTML report containing warnings, if any, and other information related to the databases.</span></span>  
  
  > [!TIP]  
  >  <span data-ttu-id="cccd0-133">後で使用できるレポートを保存することもできます。</span><span class="sxs-lookup"><span data-stu-id="cccd0-133">You can also save the reports for later use.</span></span> <span data-ttu-id="cccd0-134">これらのレポートは、BizTalk アプリケーションの問題のトラブルシューティングを行う便利な可能性があります。</span><span class="sxs-lookup"><span data-stu-id="cccd0-134">These reports might be useful when troubleshooting issues with the BizTalk application.</span></span>  
  
  > [!NOTE]  
  >  <span data-ttu-id="cccd0-135">、Microsoft では、このツールの使用はサポートされていないと、Microsoft はこのプログラムの適合性に関する保証をいたしません。</span><span class="sxs-lookup"><span data-stu-id="cccd0-135">Use of this tool is not supported by Microsoft, and Microsoft makes no guarantees about the suitability of this programs.</span></span> <span data-ttu-id="cccd0-136">このプログラムは、ユーザー自身の責任で使用してください。</span><span class="sxs-lookup"><span data-stu-id="cccd0-136">Use of this program is entirely at your own risk.</span></span>  
  
- <span data-ttu-id="cccd0-137">実行、[ターミネータ ツール](http://go.microsoft.com/fwlink/?LinkId=151931)(http://go.microsoft.com/fwlink/?LinkId=151931)します。</span><span class="sxs-lookup"><span data-stu-id="cccd0-137">Run the [Terminator tool](http://go.microsoft.com/fwlink/?LinkId=151931) (http://go.microsoft.com/fwlink/?LinkId=151931).</span></span> <span data-ttu-id="cccd0-138">このツールでは、簡単に BizTalk MsgBoxViewer ツールによって特定された問題を解決することができます。</span><span class="sxs-lookup"><span data-stu-id="cccd0-138">This tool enables users to easily resolve any issues identified by the BizTalk MsgBoxViewer tool.</span></span> <span data-ttu-id="cccd0-139">BizTalk MsgBoxViewer ツールを使用して、終端記号のツールを統合する方法の詳細については、[BizTalk MsgBoxViewer によって特定された問題を解決するには BizTalk 終端記号のを使用して](http://go.microsoft.com/fwlink/?LinkId=151932)(http://go.microsoft.com/fwlink/?LinkId=151932)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cccd0-139">For more information about how the Terminator tool integrates with the BizTalk MsgBoxViewer tool, see [Using BizTalk Terminator to resolve issues identified by BizTalk MsgBoxViewer](http://go.microsoft.com/fwlink/?LinkId=151932)(http://go.microsoft.com/fwlink/?LinkId=151932).</span></span>  
  
  > [!NOTE]  
  >  <span data-ttu-id="cccd0-140">、Microsoft では、このツールの使用はサポートされていないと、Microsoft はこのプログラムの適合性に関する保証をいたしません。</span><span class="sxs-lookup"><span data-stu-id="cccd0-140">Use of this tool is not supported by Microsoft, and Microsoft makes no guarantees about the suitability of this programs.</span></span> <span data-ttu-id="cccd0-141">このプログラムは、ユーザー自身の責任で使用してください。</span><span class="sxs-lookup"><span data-stu-id="cccd0-141">Use of this program is entirely at your own risk.</span></span>  
  
## <a name="annual-monitoring-tasks"></a><span data-ttu-id="cccd0-142">年間の監視タスク</span><span class="sxs-lookup"><span data-stu-id="cccd0-142">Annual Monitoring Tasks</span></span>  
  
- <span data-ttu-id="cccd0-143">監視の有効性を確認して、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アプリケーションとインフラストラクチャ。</span><span class="sxs-lookup"><span data-stu-id="cccd0-143">Review the effectiveness of the monitoring of your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] applications and infrastructure.</span></span>  
  
- <span data-ttu-id="cccd0-144">監視に必要な変更を加えるための計画を作成します。</span><span class="sxs-lookup"><span data-stu-id="cccd0-144">Create a plan to make any needed changes in monitoring.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cccd0-145">参照</span><span class="sxs-lookup"><span data-stu-id="cccd0-145">See Also</span></span>  
 [<span data-ttu-id="cccd0-146">定期メンテナンスのチェックリスト</span><span class="sxs-lookup"><span data-stu-id="cccd0-146">Routine Maintenance Checklists</span></span>](../technical-guides/routine-maintenance-checklists.md)