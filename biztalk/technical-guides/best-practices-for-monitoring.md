---
title: 監視するためのベスト プラクティス |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d5b180e2-bdd3-4081-9531-d96be7dabe1a
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 51b3d4761c32123db53ea35daf91d0f13d9a2488
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
ms.locfileid: "26008531"
---
# <a name="best-practices-for-monitoring"></a><span data-ttu-id="551ac-102">監視のベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="551ac-102">Best Practices for Monitoring</span></span>
<span data-ttu-id="551ac-103">このトピックでは、Microsoft BizTalk Server 環境とアプリケーションの監視のベスト プラクティスを説明します。</span><span class="sxs-lookup"><span data-stu-id="551ac-103">This topic provides best practices for monitoring your Microsoft BizTalk Server environment and applications.</span></span>  
  
 <span data-ttu-id="551ac-104">**作成し、BizTalk アプリケーションとインフラストラクチャの監視の計画を実装**</span><span class="sxs-lookup"><span data-stu-id="551ac-104">**Create and then implement a monitoring plan for your BizTalk applications and infrastructure**</span></span>  
  
-   <span data-ttu-id="551ac-105">詳細な監視ソリューションを確認するには、このガイドの監視のトピックを参照します。</span><span class="sxs-lookup"><span data-stu-id="551ac-105">Read the monitoring topics in this guide to ensure a more complete monitoring solution.</span></span> <span data-ttu-id="551ac-106">考慮すべき要因を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="551ac-106">Factors to consider include the following:</span></span>  
  
    -   <span data-ttu-id="551ac-107">毎週、月単位、および必要な監視タスクとして、毎日、誰が実行しますか。</span><span class="sxs-lookup"><span data-stu-id="551ac-107">Who will perform the daily, weekly, monthly, and as needed monitoring tasks?</span></span>  
  
    -   <span data-ttu-id="551ac-108">イベント、中断されたメッセージ、またはその他のシステムまたはアプリケーション エラーの通知を受けるユーザーですか。</span><span class="sxs-lookup"><span data-stu-id="551ac-108">Is someone notified of events, suspended messages, or other system or application failures?</span></span>  
  
    -   <span data-ttu-id="551ac-109">「予期される」例外フィルター選択されたまたは特定の優先順位が低いか。</span><span class="sxs-lookup"><span data-stu-id="551ac-109">Are "expected" exceptions filtered or given a lower priority?</span></span>  
  
    -   <span data-ttu-id="551ac-110">すべてのホスト インスタンスの実行を継続するように監視されますか。</span><span class="sxs-lookup"><span data-stu-id="551ac-110">Are all host instances monitored to ensure they continue running?</span></span>  
  
    -   <span data-ttu-id="551ac-111">すべてのカスタム サービス、カスタム イベント ログ、および監視のカスタム データベースとは</span><span class="sxs-lookup"><span data-stu-id="551ac-111">Are all custom services, custom event logs, and custom databases monitored?</span></span>  
  
    -   <span data-ttu-id="551ac-112">SQL Server コンピューターと、BizTalk Server の SQL エージェント ジョブの監視をされますか。</span><span class="sxs-lookup"><span data-stu-id="551ac-112">Are the SQL Server computers and the BizTalk Server SQL agent jobs monitored?</span></span>  
  
 <span data-ttu-id="551ac-113">**など、監視のアプリケーションのインストール可能であれば、 [!INCLUDE[opsmgr_short](../includes/opsmgr-short-md.md)] BizTalk Server アプリケーションとインフラストラクチャの監視を自動化するのには**</span><span class="sxs-lookup"><span data-stu-id="551ac-113">**If possible, install a monitoring application such as [!INCLUDE[opsmgr_short](../includes/opsmgr-short-md.md)] in order to automate the monitoring of your BizTalk Server applications and infrastructure**</span></span>  
  
-   <span data-ttu-id="551ac-114">Microsoft System Center Operations Manager を使用するは、BizTalk Server 管理パックでは、BizTalk Server の何百もの組み込みの規則のために、自動監視の推奨されるアプローチです。</span><span class="sxs-lookup"><span data-stu-id="551ac-114">Using Microsoft System Center Operations Manager is the preferred approach for automated monitoring because the BizTalk Server management packs provide hundreds of built-in rules for BizTalk Server.</span></span>  
  
     <span data-ttu-id="551ac-115">詳細については、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="551ac-115">For more information, see the following resources:</span></span>  
  
    -   <span data-ttu-id="551ac-116">[System Center Operations Manager 2007 用 Microsoft BizTalk Server 管理パック](http://go.microsoft.com/fwlink/?LinkID=190339)(http://go.microsoft.com/fwlink/?LinkID=190339)。</span><span class="sxs-lookup"><span data-stu-id="551ac-116">[Microsoft BizTalk Server Management Pack for System Center Operations Manager 2007](http://go.microsoft.com/fwlink/?LinkID=190339) (http://go.microsoft.com/fwlink/?LinkID=190339).</span></span>  
  
    -   <span data-ttu-id="551ac-117">[Operations Manager 2007 で管理パックをインポートする方法](http://go.microsoft.com/fwlink/?LinkID=98348)(http://go.microsoft.com/fwlink/?LinkID=98348)</span><span class="sxs-lookup"><span data-stu-id="551ac-117">[How to Import a Management Pack in Operations Manager 2007](http://go.microsoft.com/fwlink/?LinkID=98348) (http://go.microsoft.com/fwlink/?LinkID=98348)</span></span>  
  
    -   [<span data-ttu-id="551ac-118">カスタマイズした監視用に BizTalk Server データベースをマークする方法</span><span class="sxs-lookup"><span data-stu-id="551ac-118">How to Mark BizTalk Server Databases for Customized Monitoring</span></span>](../technical-guides/how-to-mark-biztalk-server-databases-for-customized-monitoring.md)  
  
 <span data-ttu-id="551ac-119">**BizTalk Server のベスト プラクティス アナライザーを実行します。**</span><span class="sxs-lookup"><span data-stu-id="551ac-119">**Run the BizTalk Server Best Practices Analyzer**</span></span>  
  
-   <span data-ttu-id="551ac-120">BizTalk Server のベスト プラクティス アナライザーは、BizTalk Server の展開を調査し、ベスト プラクティスの標準に関連する問題の一覧を生成します。</span><span class="sxs-lookup"><span data-stu-id="551ac-120">The BizTalk Server Best Practices Analyzer examines a BizTalk Server deployment and generates a list of issues pertaining to best practices standards.</span></span> <span data-ttu-id="551ac-121">このツールは、Windows Management Instrumentation (WMI) クラス、SQL Server データベース、およびレジストリ エントリなど、さまざまな情報のソースからデータを収集することによって構成レベルの検証を実行します。</span><span class="sxs-lookup"><span data-stu-id="551ac-121">The tool performs configuration-level verification by gathering data from different information sources, such as Windows Management Instrumentation (WMI) classes, SQL Server databases, and registry entries.</span></span> <span data-ttu-id="551ac-122">データは展開構成の評価に使用されます。</span><span class="sxs-lookup"><span data-stu-id="551ac-122">The data is then used to evaluate the deployment configuration.</span></span> <span data-ttu-id="551ac-123">ツールを読み取りますをレポートのみ、そのシステム設定を変更しませんし、自己調整ツールではありません。</span><span class="sxs-lookup"><span data-stu-id="551ac-123">The tool reads and reports only and does not modify any system settings, and is not a self-tuning tool.</span></span>  
  
     <span data-ttu-id="551ac-124">BizTalk Server ベスト プラクティス アナライザーでダウンロードできます[http://go.microsoft.com/fwlink/?LinkId=83317](http://go.microsoft.com/fwlink/?LinkId=83317) (http://go.microsoft.com/fwlink/?LinkId=83317)。</span><span class="sxs-lookup"><span data-stu-id="551ac-124">You can download the BizTalk Server Best Practices Analyzer at [http://go.microsoft.com/fwlink/?LinkId=83317](http://go.microsoft.com/fwlink/?LinkId=83317) (http://go.microsoft.com/fwlink/?LinkId=83317).</span></span>  
  
 <span data-ttu-id="551ac-125">**ログのパフォーマンス分析ツール (PAL) の実行します。**</span><span class="sxs-lookup"><span data-stu-id="551ac-125">**Run the Performance Analysis of Logs tool (PAL)**</span></span>  
  
-   <span data-ttu-id="551ac-126">PAL はから無償でダウンロードとして入手できます[https://github.com/clinthuffman/PAL](https://github.com/clinthuffman/PAL)です。</span><span class="sxs-lookup"><span data-stu-id="551ac-126">PAL is available as a free download at [https://github.com/clinthuffman/PAL](https://github.com/clinthuffman/PAL).</span></span> <span data-ttu-id="551ac-127">インストールに関する重要な情報を参照してください。[パフォーマンス分析のログ (PAL) のツールを使用して](../technical-guides/using-the-performance-analysis-of-logs-pal-tool.md)です。</span><span class="sxs-lookup"><span data-stu-id="551ac-127">For important installation information, see [Using the Performance Analysis of Logs (PAL) Tool](../technical-guides/using-the-performance-analysis-of-logs-pal-tool.md).</span></span>  
  
 <span data-ttu-id="551ac-128">**ログ パーサーを実行します。**</span><span class="sxs-lookup"><span data-stu-id="551ac-128">**Run Log Parser**</span></span>  
  
-   <span data-ttu-id="551ac-129">ログ パーサーは、強力な用途の広いツールなど、イベント ログ、レジストリ、ファイル システム、およびアクティブ Windows® オペレーティング システムでキーのデータ ソースに加え、ログ ファイル、XML ファイルおよび CSV ファイルなどのテキスト ベースのデータにユニバーサル クエリ アクセスを提供します。Directory® です。</span><span class="sxs-lookup"><span data-stu-id="551ac-129">Log Parser is a powerful, versatile tool that provides universal query access to text-based data such as log files, XML files and CSV files, as well as key data sources on the Windows® operating system such as the Event Log, the Registry, the file system, and Active Directory®.</span></span> <span data-ttu-id="551ac-130">このツールを使用して大量のログ情報のクエリを実行する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="551ac-130">You may want to use this tool to query a significant amount of logging information.</span></span> <span data-ttu-id="551ac-131">Log Parser ツールをダウンロードする[http://go.microsoft.com/fwlink/?LinkID=85574](http://go.microsoft.com/fwlink/?LinkID=85574)</span><span class="sxs-lookup"><span data-stu-id="551ac-131">You can download the Log Parser tool at [http://go.microsoft.com/fwlink/?LinkID=85574](http://go.microsoft.com/fwlink/?LinkID=85574)</span></span>  
  
 <span data-ttu-id="551ac-132">**BizTalk MsgBoxViewer ツールを実行します。**</span><span class="sxs-lookup"><span data-stu-id="551ac-132">**Run the BizTalk MsgBoxViewer Tool**</span></span>  
  
 <span data-ttu-id="551ac-133">実行、 [BizTalk MsgBoxViewer ツール](http://go.microsoft.com/fwlink/?LinkId=151930)から使用可能な[http://go.microsoft.com/fwlink/?LinkId=151930](http://go.microsoft.com/fwlink/?LinkId=151930)です。</span><span class="sxs-lookup"><span data-stu-id="551ac-133">Run the [BizTalk MsgBoxViewer tool](http://go.microsoft.com/fwlink/?LinkId=151930) available from [http://go.microsoft.com/fwlink/?LinkId=151930](http://go.microsoft.com/fwlink/?LinkId=151930).</span></span> <span data-ttu-id="551ac-134">このツールでは、BizTalk メッセージ ボックス データベースとその他のデータベースを分析し、その他の情報がデータベースに関連している場合、警告を含む HTML レポートを生成します。</span><span class="sxs-lookup"><span data-stu-id="551ac-134">This tool analyzes the BizTalk MessageBox and other databases and generates an HTML report containing warnings, if any, and other information related to the databases.</span></span> <span data-ttu-id="551ac-135">後で使用できるレポートを保存することもできます。</span><span class="sxs-lookup"><span data-stu-id="551ac-135">You can also save the reports for later use.</span></span> <span data-ttu-id="551ac-136">これらのレポートは、BizTalk アプリケーションの問題のトラブルシューティングを行うときに役立ちます可能性があります。</span><span class="sxs-lookup"><span data-stu-id="551ac-136">These reports might be useful when troubleshooting issues with the BizTalk application.</span></span>  
  
 <span data-ttu-id="551ac-137">BizTalk MsgBoxViewer ツールは、すべての問題を示している場合は、実行、[ターミネータ ツール](http://go.microsoft.com/fwlink/?LinkId=151931)いただけます[http://go.microsoft.com/fwlink/?LinkId=151931](http://go.microsoft.com/fwlink/?LinkId=151931)です。</span><span class="sxs-lookup"><span data-stu-id="551ac-137">If the BizTalk MsgBoxViewer tool identifies any issues, run the [Terminator tool](http://go.microsoft.com/fwlink/?LinkId=151931) available at [http://go.microsoft.com/fwlink/?LinkId=151931](http://go.microsoft.com/fwlink/?LinkId=151931).</span></span> <span data-ttu-id="551ac-138">このツールでは、簡単に BizTalk MsgBoxViewer ツールによって識別される問題を解決することができます。</span><span class="sxs-lookup"><span data-stu-id="551ac-138">This tool enables users to easily resolve any issues identified by the BizTalk MsgBoxViewer tool.</span></span> <span data-ttu-id="551ac-139">ターミネータ ツールが、BizTalk MsgBoxViewer ツールと統合する方法の詳細については、次を参照してください。 [BizTalk MsgBoxViewer によって特定された問題を解決するには BizTalk のターミネータを使用して](http://go.microsoft.com/fwlink/?LinkId=151932)(http://go.microsoft.com/fwlink/?LinkId=151932)。</span><span class="sxs-lookup"><span data-stu-id="551ac-139">For more information about how the Terminator tool integrates with the BizTalk MsgBoxViewer tool, see [Using BizTalk Terminator to resolve issues identified by BizTalk MsgBoxViewer](http://go.microsoft.com/fwlink/?LinkId=151932) (http://go.microsoft.com/fwlink/?LinkId=151932).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="551ac-140">Microsoft では、これらのツールの使用はサポートされていないと、Microsoft がこれらのプログラムの適合性に関して保証を行いません。</span><span class="sxs-lookup"><span data-stu-id="551ac-140">Use of these tools is not supported by Microsoft, and Microsoft makes no guarantees about the suitability of these programs.</span></span> <span data-ttu-id="551ac-141">これらのプログラムは、ユーザー自身の責任で使用してください。</span><span class="sxs-lookup"><span data-stu-id="551ac-141">Use of these programs is entirely at your own risk.</span></span>  
  
 <span data-ttu-id="551ac-142">**優先度を監視します。**</span><span class="sxs-lookup"><span data-stu-id="551ac-142">**Make monitoring a priority**</span></span>  
  
-   <span data-ttu-id="551ac-143">BizTalk Server アプリケーションとインフラストラクチャの一貫した監視は、正常な環境を維持するために不可欠です。</span><span class="sxs-lookup"><span data-stu-id="551ac-143">Consistent monitoring of BizTalk Server applications and infrastructure is essential to maintaining a healthy environment.</span></span>  
  
-   <span data-ttu-id="551ac-144">定期的に評価し、時間が経過し、BizTalk Server アプリケーションとインフラストラクチャの変更として、監視ツールを調整します。</span><span class="sxs-lookup"><span data-stu-id="551ac-144">Regularly evaluate and adjust your monitoring tools over time and as your BizTalk Server applications and infrastructure change.</span></span>