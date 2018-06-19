---
title: タスクの監視ルーチン |Microsoft ドキュメント
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
ms.openlocfilehash: d91a49393e2b43c9cf39add35e06c5bd864782e8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22301906"
---
# <a name="routine-monitoring-tasks"></a><span data-ttu-id="105ee-102">日常的な監視タスク</span><span class="sxs-lookup"><span data-stu-id="105ee-102">Routine Monitoring Tasks</span></span>
<span data-ttu-id="105ee-103">定期的なスケジュールに従ってを次の監視タスクを実行することは、支援残して、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アプリケーションとインフラストラクチャを運用できる状態です。</span><span class="sxs-lookup"><span data-stu-id="105ee-103">Performing the following monitoring tasks on a regularly scheduled basis will assist you in keeping your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] applications and infrastructure operationally ready.</span></span>  
  
## <a name="daily-monitoring-tasks"></a><span data-ttu-id="105ee-104">日常的な監視タスク</span><span class="sxs-lookup"><span data-stu-id="105ee-104">Daily Monitoring Tasks</span></span>  
  
-   <span data-ttu-id="105ee-105">すべてのオープン アラートを確認する。</span><span class="sxs-lookup"><span data-stu-id="105ee-105">Review all open alerts.</span></span>  
  
-   <span data-ttu-id="105ee-106">使用して、**グループ ハブ** ページで、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]オーケストレーション、ポート、およびメッセージのエラーを調査するために管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="105ee-106">Use the **Group Hub** page in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console to investigate orchestration, port, and message failures.</span></span> <span data-ttu-id="105ee-107">**グループ ハブ**ページは、メッセージ ボックス データベース内のデータにアクセスする、システムの現在のリアルタイムの状態へのアクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="105ee-107">The **Group Hub** page provides access to the current real-time state of the system, accessing data in the MessageBox database.</span></span> <span data-ttu-id="105ee-108">オーケストレーション、ポート、メッセージングなどのすべてのサービス インスタンスと、それに関連するメッセージを表示できます。</span><span class="sxs-lookup"><span data-stu-id="105ee-108">You can view all service instances such as orchestrations, ports, and messaging, along with their associated messages.</span></span> <span data-ttu-id="105ee-109">使用して、**グループ ハブ**ページは次のアクティビティを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="105ee-109">Using the **Group Hub** page you can perform the following activities:</span></span>  
  
    -   <span data-ttu-id="105ee-110">現在実行中のオーケストレーションなどのサービス インスタンスとメッセージ、および関連付けられているメッセージを参照してください。</span><span class="sxs-lookup"><span data-stu-id="105ee-110">See currently running service instances, such as orchestrations and messaging, and their associated messages.</span></span>  
  
    -   <span data-ttu-id="105ee-111">現在のデータおよびシステムのリアルタイムの状態について、メッセージ ボックス データベースを調べます。</span><span class="sxs-lookup"><span data-stu-id="105ee-111">Look into the MessageBox database for a view of the current data and the real-time state of the system.</span></span>  
  
    -   <span data-ttu-id="105ee-112">サービス インスタンスを中断、終了、および再開します。</span><span class="sxs-lookup"><span data-stu-id="105ee-112">Suspend, terminate, and resume service instances.</span></span>  
  
     <span data-ttu-id="105ee-113">使用しての詳細については、**グループ ハブ** ページを参照してください[http://go.microsoft.com/fwlink/?LinkId=155281](http://go.microsoft.com/fwlink/?LinkId=155281)です。</span><span class="sxs-lookup"><span data-stu-id="105ee-113">For more information about using the **Group Hub** page, see [http://go.microsoft.com/fwlink/?LinkId=155281](http://go.microsoft.com/fwlink/?LinkId=155281).</span></span>  
  
-   <span data-ttu-id="105ee-114">警告を見直す (省略可)。</span><span class="sxs-lookup"><span data-stu-id="105ee-114">Review warnings (optional).</span></span>  
  
 <span data-ttu-id="105ee-115">詳細については、次を参照してください。[チェックリスト: メンテナンスを毎日チェックを実行する](../technical-guides/checklist-performing-daily-maintenance-checks.md)です。</span><span class="sxs-lookup"><span data-stu-id="105ee-115">For more information, see [Checklist: Performing Daily Maintenance Checks](../technical-guides/checklist-performing-daily-maintenance-checks.md).</span></span>  
  
## <a name="weekly-monitoring-tasks"></a><span data-ttu-id="105ee-116">毎週監視タスク</span><span class="sxs-lookup"><span data-stu-id="105ee-116">Weekly Monitoring Tasks</span></span>  
  
-   <span data-ttu-id="105ee-117">毎週 1 回以上のイベント ログを確認します。</span><span class="sxs-lookup"><span data-stu-id="105ee-117">Review the event logs at least once per week.</span></span> <span data-ttu-id="105ee-118">このタスクに対する理由見逃さ DBNetLib エラーなどの問題を回避するためです。</span><span class="sxs-lookup"><span data-stu-id="105ee-118">The reason for this task is to prevent issues, such as DBNetLib errors going undetected.</span></span> <span data-ttu-id="105ee-119">非常に低い待機時間システムがない限り、サービスの中断が気付かない場合があります。</span><span class="sxs-lookup"><span data-stu-id="105ee-119">Service interruption might go unnoticed unless you have a very low latency system.</span></span> <span data-ttu-id="105ee-120">ただし、これらのエラーのいくつか (例が多すぎますホストまたはメッセージ ボックス、SQL ボックスなどのパフォーマンスの問題の数の BizTalk Server サーバー) の問題が大きくを示すことができます。</span><span class="sxs-lookup"><span data-stu-id="105ee-120">However, some of these errors can indicate a bigger issue (for example, too many hosts or BizTalk Server servers for the number of message boxes, performance issues on the SQL box, etc).</span></span>  
  
 <span data-ttu-id="105ee-121">詳細については、次を参照してください。[チェックリスト: 毎週の保守チェックを実行して](../technical-guides/checklist-performing-weekly-maintenance-checks.md)です。</span><span class="sxs-lookup"><span data-stu-id="105ee-121">For more information, see [Checklist: Performing Weekly Maintenance Checks](../technical-guides/checklist-performing-weekly-maintenance-checks.md).</span></span>  
  
## <a name="as-needed-tasks"></a><span data-ttu-id="105ee-122">必要なタスク</span><span class="sxs-lookup"><span data-stu-id="105ee-122">As-Needed Tasks</span></span>  
  
-   <span data-ttu-id="105ee-123">監視をカスタマイズする規則を変更する、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アプリケーションとインフラストラクチャです。</span><span class="sxs-lookup"><span data-stu-id="105ee-123">Modify the rules to customize the monitoring of your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] applications and infrastructure.</span></span>  
  
-   <span data-ttu-id="105ee-124">ログのパフォーマンス分析ツール (PAL) を実行します。</span><span class="sxs-lookup"><span data-stu-id="105ee-124">Run the Performance Analysis of Logs tool (PAL).</span></span> <span data-ttu-id="105ee-125">場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]展開はかなり定数 (たとえば、新しい取引先は日常的に、追加された新しいコードが展開されていない)、可能性がありますを実行するパフォーマンス モニターと PAL 四半期に 1 回ごと、またはでもは 6 か月です。</span><span class="sxs-lookup"><span data-stu-id="105ee-125">If your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] deployment is fairly constant (for example, new trading partners aren't added routinely, new code is not deployed), you might run Perfmon and PAL once a quarter or even every six months.</span></span> <span data-ttu-id="105ee-126">場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]配置の変更より多くの場合は、可能性があるパフォーマンス モニターを実行し、だれか月間、ベースラインと比較する 2 ~ 3 おきです。</span><span class="sxs-lookup"><span data-stu-id="105ee-126">If your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] deployment changes more frequently, you may want to run Perfmon and PAL every couple of months to compare against a baseline.</span></span> <span data-ttu-id="105ee-127">PAL の詳細については、次を参照してください。[パフォーマンス分析のログ (PAL) のツールを使用して](../technical-guides/using-the-performance-analysis-of-logs-pal-tool.md)です。</span><span class="sxs-lookup"><span data-stu-id="105ee-127">For more information on PAL, see [Using the Performance Analysis of Logs (PAL) Tool](../technical-guides/using-the-performance-analysis-of-logs-pal-tool.md).</span></span>  
  
-   <span data-ttu-id="105ee-128">発生するパフォーマンス モニターの実行の数か月ごと、変更の数に基づいて四半期に 1 回ごと、またはでもは 6 か月に、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]展開します。</span><span class="sxs-lookup"><span data-stu-id="105ee-128">Run Perfmon every few months, to once a quarter or even every six months depending on the number of changes occur in your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] deployment.</span></span>  
  
-   <span data-ttu-id="105ee-129">BizTalk Server ベスト プラクティス アナライザーを実行するときに、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]配置の変更 (たとえば、新しいアプリケーションの追加)、または新しいホストを作成します。</span><span class="sxs-lookup"><span data-stu-id="105ee-129">Run BizTalk Server Best Practices Analyzer when the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] deployment changes (for example, the addition of new applications or creation of new hosts).</span></span> <span data-ttu-id="105ee-130">BizTalk Server ベスト プラクティス アナライザーでダウンロードできます[http://go.microsoft.com/fwlink/?LinkId=83317](http://go.microsoft.com/fwlink/?LinkId=83317)です。</span><span class="sxs-lookup"><span data-stu-id="105ee-130">You can download the BizTalk Server Best Practices Analyzer at [http://go.microsoft.com/fwlink/?LinkId=83317](http://go.microsoft.com/fwlink/?LinkId=83317).</span></span>  
  
-   <span data-ttu-id="105ee-131">実行、 [BizTalk MsgBoxViewer ツール](http://go.microsoft.com/fwlink/?LinkId=151930)(http://go.microsoft.com/fwlink/?LinkId=151930)。</span><span class="sxs-lookup"><span data-stu-id="105ee-131">Run the [BizTalk MsgBoxViewer tool](http://go.microsoft.com/fwlink/?LinkId=151930) (http://go.microsoft.com/fwlink/?LinkId=151930).</span></span> <span data-ttu-id="105ee-132">このツールでは、BizTalk メッセージ ボックス データベースとその他のデータベースを分析し、その他の情報がデータベースに関連している場合、警告を含む HTML レポートを生成します。</span><span class="sxs-lookup"><span data-stu-id="105ee-132">This tool analyzes the BizTalk MessageBox and other databases and generates an HTML report containing warnings, if any, and other information related to the databases.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="105ee-133">後で使用できるレポートを保存することもできます。</span><span class="sxs-lookup"><span data-stu-id="105ee-133">You can also save the reports for later use.</span></span> <span data-ttu-id="105ee-134">これらのレポートは、BizTalk アプリケーションの問題のトラブルシューティングを行うときに役立ちます可能性があります。</span><span class="sxs-lookup"><span data-stu-id="105ee-134">These reports might be useful when troubleshooting issues with the BizTalk application.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="105ee-135">、Microsoft では、このツールの使用はサポートされていないと、Microsoft はこのプログラムの適合性に関して保証を行いません。</span><span class="sxs-lookup"><span data-stu-id="105ee-135">Use of this tool is not supported by Microsoft, and Microsoft makes no guarantees about the suitability of this programs.</span></span> <span data-ttu-id="105ee-136">このプログラムは、ユーザー自身の責任で使用してください。</span><span class="sxs-lookup"><span data-stu-id="105ee-136">Use of this program is entirely at your own risk.</span></span>  
  
-   <span data-ttu-id="105ee-137">実行、[ターミネータ ツール](http://go.microsoft.com/fwlink/?LinkId=151931)(http://go.microsoft.com/fwlink/?LinkId=151931)。</span><span class="sxs-lookup"><span data-stu-id="105ee-137">Run the [Terminator tool](http://go.microsoft.com/fwlink/?LinkId=151931) (http://go.microsoft.com/fwlink/?LinkId=151931).</span></span> <span data-ttu-id="105ee-138">このツールでは、簡単に BizTalk MsgBoxViewer ツールによって識別される問題を解決することができます。</span><span class="sxs-lookup"><span data-stu-id="105ee-138">This tool enables users to easily resolve any issues identified by the BizTalk MsgBoxViewer tool.</span></span> <span data-ttu-id="105ee-139">ターミネータ ツールが、BizTalk MsgBoxViewer ツールと統合する方法の詳細については、次を参照してください。 [BizTalk MsgBoxViewer によって特定された問題を解決するには BizTalk のターミネータを使用して](http://go.microsoft.com/fwlink/?LinkId=151932)(http://go.microsoft.com/fwlink/?LinkId=151932)。</span><span class="sxs-lookup"><span data-stu-id="105ee-139">For more information about how the Terminator tool integrates with the BizTalk MsgBoxViewer tool, see [Using BizTalk Terminator to resolve issues identified by BizTalk MsgBoxViewer](http://go.microsoft.com/fwlink/?LinkId=151932)(http://go.microsoft.com/fwlink/?LinkId=151932).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="105ee-140">、Microsoft では、このツールの使用はサポートされていないと、Microsoft はこのプログラムの適合性に関して保証を行いません。</span><span class="sxs-lookup"><span data-stu-id="105ee-140">Use of this tool is not supported by Microsoft, and Microsoft makes no guarantees about the suitability of this programs.</span></span> <span data-ttu-id="105ee-141">このプログラムは、ユーザー自身の責任で使用してください。</span><span class="sxs-lookup"><span data-stu-id="105ee-141">Use of this program is entirely at your own risk.</span></span>  
  
## <a name="annual-monitoring-tasks"></a><span data-ttu-id="105ee-142">年間の監視タスク</span><span class="sxs-lookup"><span data-stu-id="105ee-142">Annual Monitoring Tasks</span></span>  
  
-   <span data-ttu-id="105ee-143">監視の有効性を確認、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アプリケーションとインフラストラクチャです。</span><span class="sxs-lookup"><span data-stu-id="105ee-143">Review the effectiveness of the monitoring of your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] applications and infrastructure.</span></span>  
  
-   <span data-ttu-id="105ee-144">変更を加える必要な監視の計画を作成します。</span><span class="sxs-lookup"><span data-stu-id="105ee-144">Create a plan to make any needed changes in monitoring.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="105ee-145">参照</span><span class="sxs-lookup"><span data-stu-id="105ee-145">See Also</span></span>  
 [<span data-ttu-id="105ee-146">定期的なメンテナンスのチェックリスト</span><span class="sxs-lookup"><span data-stu-id="105ee-146">Routine Maintenance Checklists</span></span>](../technical-guides/routine-maintenance-checklists.md)