---
title: 監視するためのベスト プラクティス |Microsoft Docs
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
ms.openlocfilehash: 9bfb2b5575fe46c1104ddc6b852695fb777275ef
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981659"
---
# <a name="best-practices-for-monitoring"></a><span data-ttu-id="9e2dd-102">監視するためのベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="9e2dd-102">Best Practices for Monitoring</span></span>
<span data-ttu-id="9e2dd-103">このトピックでは、Microsoft BizTalk Server 環境とアプリケーションを監視するためのベスト プラクティスを提供します。</span><span class="sxs-lookup"><span data-stu-id="9e2dd-103">This topic provides best practices for monitoring your Microsoft BizTalk Server environment and applications.</span></span>  
  
 <span data-ttu-id="9e2dd-104">**作成して BizTalk アプリケーションとインフラストラクチャの監視の計画を実装し、**</span><span class="sxs-lookup"><span data-stu-id="9e2dd-104">**Create and then implement a monitoring plan for your BizTalk applications and infrastructure**</span></span>  
  
- <span data-ttu-id="9e2dd-105">このガイドに詳細な監視ソリューションの監視に関するトピックを読み取ります。</span><span class="sxs-lookup"><span data-stu-id="9e2dd-105">Read the monitoring topics in this guide to ensure a more complete monitoring solution.</span></span> <span data-ttu-id="9e2dd-106">考慮すべき要素を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="9e2dd-106">Factors to consider include the following:</span></span>  
  
  -   <span data-ttu-id="9e2dd-107">毎週、月単位、および必要な監視のタスクとして、毎日を実行するユーザーはでしょうか。</span><span class="sxs-lookup"><span data-stu-id="9e2dd-107">Who will perform the daily, weekly, monthly, and as needed monitoring tasks?</span></span>  
  
  -   <span data-ttu-id="9e2dd-108">イベント、保留メッセージ、またはその他のシステムまたはアプリケーション エラーのだれかが通知されますか。</span><span class="sxs-lookup"><span data-stu-id="9e2dd-108">Is someone notified of events, suspended messages, or other system or application failures?</span></span>  
  
  -   <span data-ttu-id="9e2dd-109">「予期される」例外がフィルター選択された、または特定の優先順位の低いは?</span><span class="sxs-lookup"><span data-stu-id="9e2dd-109">Are "expected" exceptions filtered or given a lower priority?</span></span>  
  
  -   <span data-ttu-id="9e2dd-110">すべてのホスト インスタンスの監視が引き続き実行されていることを確認するか?</span><span class="sxs-lookup"><span data-stu-id="9e2dd-110">Are all host instances monitored to ensure they continue running?</span></span>  
  
  -   <span data-ttu-id="9e2dd-111">すべてのカスタム サービス、カスタムのイベント ログ、および監視のカスタム データベースか?</span><span class="sxs-lookup"><span data-stu-id="9e2dd-111">Are all custom services, custom event logs, and custom databases monitored?</span></span>  
  
  -   <span data-ttu-id="9e2dd-112">SQL Server コンピューターと BizTalk Server の SQL エージェント ジョブの監視対象ですか。</span><span class="sxs-lookup"><span data-stu-id="9e2dd-112">Are the SQL Server computers and the BizTalk Server SQL agent jobs monitored?</span></span>  
  
  <span data-ttu-id="9e2dd-113">**など、監視アプリケーションのインストール可能であれば、 [!INCLUDE[opsmgr_short](../includes/opsmgr-short-md.md)] BizTalk Server アプリケーションとインフラストラクチャの監視を自動化するには**</span><span class="sxs-lookup"><span data-stu-id="9e2dd-113">**If possible, install a monitoring application such as [!INCLUDE[opsmgr_short](../includes/opsmgr-short-md.md)] in order to automate the monitoring of your BizTalk Server applications and infrastructure**</span></span>  
  
- <span data-ttu-id="9e2dd-114">BizTalk Server 管理パックには、BizTalk Server の数百の組み込みの規則を提供するために、自動監視に対して推奨されるアプローチは、Microsoft System Center Operations Manager を使用します。</span><span class="sxs-lookup"><span data-stu-id="9e2dd-114">Using Microsoft System Center Operations Manager is the preferred approach for automated monitoring because the BizTalk Server management packs provide hundreds of built-in rules for BizTalk Server.</span></span>  
  
   <span data-ttu-id="9e2dd-115">詳細については、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9e2dd-115">For more information, see the following resources:</span></span>  
  
  -   <span data-ttu-id="9e2dd-116">[System Center Operations Manager 2007 用 Microsoft BizTalk Server 管理パック](http://go.microsoft.com/fwlink/?LinkID=190339)(http://go.microsoft.com/fwlink/?LinkID=190339)します。</span><span class="sxs-lookup"><span data-stu-id="9e2dd-116">[Microsoft BizTalk Server Management Pack for System Center Operations Manager 2007](http://go.microsoft.com/fwlink/?LinkID=190339) (http://go.microsoft.com/fwlink/?LinkID=190339).</span></span>  
  
  -   <span data-ttu-id="9e2dd-117">[Operations Manager 2007 で管理パックをインポートする方法](http://go.microsoft.com/fwlink/?LinkID=98348)(http://go.microsoft.com/fwlink/?LinkID=98348)</span><span class="sxs-lookup"><span data-stu-id="9e2dd-117">[How to Import a Management Pack in Operations Manager 2007](http://go.microsoft.com/fwlink/?LinkID=98348) (http://go.microsoft.com/fwlink/?LinkID=98348)</span></span>  
  
  -   [<span data-ttu-id="9e2dd-118">カスタマイズした監視用に BizTalk Server データベースをマークする方法</span><span class="sxs-lookup"><span data-stu-id="9e2dd-118">How to Mark BizTalk Server Databases for Customized Monitoring</span></span>](../technical-guides/how-to-mark-biztalk-server-databases-for-customized-monitoring.md)  
  
  <span data-ttu-id="9e2dd-119">**BizTalk Server のベスト プラクティス アナライザーを実行します。**</span><span class="sxs-lookup"><span data-stu-id="9e2dd-119">**Run the BizTalk Server Best Practices Analyzer**</span></span>  
  
- <span data-ttu-id="9e2dd-120">BizTalk Server のベスト プラクティス アナライザーは、BizTalk Server の展開を調べ、問題に関連するベスト プラクティス基準の一覧が生成されます。</span><span class="sxs-lookup"><span data-stu-id="9e2dd-120">The BizTalk Server Best Practices Analyzer examines a BizTalk Server deployment and generates a list of issues pertaining to best practices standards.</span></span> <span data-ttu-id="9e2dd-121">ツールは、Windows Management Instrumentation (WMI) クラス、SQL Server データベース、およびレジストリ エントリなど、さまざまな情報のソースからデータを収集することにより構成レベルの検証を実行します。</span><span class="sxs-lookup"><span data-stu-id="9e2dd-121">The tool performs configuration-level verification by gathering data from different information sources, such as Windows Management Instrumentation (WMI) classes, SQL Server databases, and registry entries.</span></span> <span data-ttu-id="9e2dd-122">データは、展開構成を評価するが使用されます。</span><span class="sxs-lookup"><span data-stu-id="9e2dd-122">The data is then used to evaluate the deployment configuration.</span></span> <span data-ttu-id="9e2dd-123">ツールとレポートのみ、任意のシステム設定は変更されませんを読み取って自己調整ツールではありません。</span><span class="sxs-lookup"><span data-stu-id="9e2dd-123">The tool reads and reports only and does not modify any system settings, and is not a self-tuning tool.</span></span>  
  
   <span data-ttu-id="9e2dd-124">BizTalk Server ベスト プラクティス アナライザーでダウンロードできます[ http://go.microsoft.com/fwlink/?LinkId=83317 ](http://go.microsoft.com/fwlink/?LinkId=83317) (http://go.microsoft.com/fwlink/?LinkId=83317)します。</span><span class="sxs-lookup"><span data-stu-id="9e2dd-124">You can download the BizTalk Server Best Practices Analyzer at [http://go.microsoft.com/fwlink/?LinkId=83317](http://go.microsoft.com/fwlink/?LinkId=83317) (http://go.microsoft.com/fwlink/?LinkId=83317).</span></span>  
  
  <span data-ttu-id="9e2dd-125">**ログのパフォーマンス分析ツール (PAL) の実行します。**</span><span class="sxs-lookup"><span data-stu-id="9e2dd-125">**Run the Performance Analysis of Logs tool (PAL)**</span></span>  
  
- <span data-ttu-id="9e2dd-126">PAL はから無償でダウンロードとして入手できます[ https://github.com/clinthuffman/PAL](https://github.com/clinthuffman/PAL)します。</span><span class="sxs-lookup"><span data-stu-id="9e2dd-126">PAL is available as a free download at [https://github.com/clinthuffman/PAL](https://github.com/clinthuffman/PAL).</span></span> <span data-ttu-id="9e2dd-127">インストールに関する重要なは、次を参照してください。[パフォーマンス分析のログ (PAL) ツールを使用して](../technical-guides/using-the-performance-analysis-of-logs-pal-tool.md)します。</span><span class="sxs-lookup"><span data-stu-id="9e2dd-127">For important installation information, see [Using the Performance Analysis of Logs (PAL) Tool](../technical-guides/using-the-performance-analysis-of-logs-pal-tool.md).</span></span>  
  
  <span data-ttu-id="9e2dd-128">**Log Parser を実行します。**</span><span class="sxs-lookup"><span data-stu-id="9e2dd-128">**Run Log Parser**</span></span>  
  
- <span data-ttu-id="9e2dd-129">Log Parser は強力な多目的ツールなど、イベント ログ、レジストリ、ファイル システム、およびアクティブ Windows® オペレーティング システムの主要なデータ ソースに加え、ログ ファイル、XML ファイルおよび CSV ファイルなどのテキスト ベースのデータへの汎用クエリ アクセスを提供します。Directory® します。</span><span class="sxs-lookup"><span data-stu-id="9e2dd-129">Log Parser is a powerful, versatile tool that provides universal query access to text-based data such as log files, XML files and CSV files, as well as key data sources on the Windows® operating system such as the Event Log, the Registry, the file system, and Active Directory®.</span></span> <span data-ttu-id="9e2dd-130">このツールを使用して大量のログ情報を照会する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9e2dd-130">You may want to use this tool to query a significant amount of logging information.</span></span> <span data-ttu-id="9e2dd-131">Log Parser ツールをダウンロードします。 [http://go.microsoft.com/fwlink/?LinkID=85574](http://go.microsoft.com/fwlink/?LinkID=85574)</span><span class="sxs-lookup"><span data-stu-id="9e2dd-131">You can download the Log Parser tool at [http://go.microsoft.com/fwlink/?LinkID=85574](http://go.microsoft.com/fwlink/?LinkID=85574)</span></span>  
  
  <span data-ttu-id="9e2dd-132">**BizTalk MsgBoxViewer ツールを実行します。**</span><span class="sxs-lookup"><span data-stu-id="9e2dd-132">**Run the BizTalk MsgBoxViewer Tool**</span></span>  
  
  <span data-ttu-id="9e2dd-133">実行、 [BizTalk MsgBoxViewer ツール](http://go.microsoft.com/fwlink/?LinkId=151930)から使用可能な[ http://go.microsoft.com/fwlink/?LinkId=151930](http://go.microsoft.com/fwlink/?LinkId=151930)します。</span><span class="sxs-lookup"><span data-stu-id="9e2dd-133">Run the [BizTalk MsgBoxViewer tool](http://go.microsoft.com/fwlink/?LinkId=151930) available from [http://go.microsoft.com/fwlink/?LinkId=151930](http://go.microsoft.com/fwlink/?LinkId=151930).</span></span> <span data-ttu-id="9e2dd-134">このツールは、BizTalk メッセージ ボックスとその他のデータベースを分析し、その他の情報がデータベースに関連している場合、警告を含む、HTML レポートが生成されます。</span><span class="sxs-lookup"><span data-stu-id="9e2dd-134">This tool analyzes the BizTalk MessageBox and other databases and generates an HTML report containing warnings, if any, and other information related to the databases.</span></span> <span data-ttu-id="9e2dd-135">後で使用できるレポートを保存することもできます。</span><span class="sxs-lookup"><span data-stu-id="9e2dd-135">You can also save the reports for later use.</span></span> <span data-ttu-id="9e2dd-136">これらのレポートは、BizTalk アプリケーションの問題のトラブルシューティングを行う便利な可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9e2dd-136">These reports might be useful when troubleshooting issues with the BizTalk application.</span></span>  
  
  <span data-ttu-id="9e2dd-137">BizTalk MsgBoxViewer ツールでは、すべての問題を識別する場合は、実行、[ターミネータ ツール](http://go.microsoft.com/fwlink/?LinkId=151931)でご利用いただけます[ http://go.microsoft.com/fwlink/?LinkId=151931](http://go.microsoft.com/fwlink/?LinkId=151931)します。</span><span class="sxs-lookup"><span data-stu-id="9e2dd-137">If the BizTalk MsgBoxViewer tool identifies any issues, run the [Terminator tool](http://go.microsoft.com/fwlink/?LinkId=151931) available at [http://go.microsoft.com/fwlink/?LinkId=151931](http://go.microsoft.com/fwlink/?LinkId=151931).</span></span> <span data-ttu-id="9e2dd-138">このツールでは、簡単に BizTalk MsgBoxViewer ツールによって特定された問題を解決することができます。</span><span class="sxs-lookup"><span data-stu-id="9e2dd-138">This tool enables users to easily resolve any issues identified by the BizTalk MsgBoxViewer tool.</span></span> <span data-ttu-id="9e2dd-139">BizTalk MsgBoxViewer ツールを使用して、終端記号のツールを統合する方法の詳細については、次を参照してください。 [BizTalk MsgBoxViewer によって特定された問題を解決するには BizTalk 終端記号のを使用して](http://go.microsoft.com/fwlink/?LinkId=151932)(http://go.microsoft.com/fwlink/?LinkId=151932)します。</span><span class="sxs-lookup"><span data-stu-id="9e2dd-139">For more information about how the Terminator tool integrates with the BizTalk MsgBoxViewer tool, see [Using BizTalk Terminator to resolve issues identified by BizTalk MsgBoxViewer](http://go.microsoft.com/fwlink/?LinkId=151932) (http://go.microsoft.com/fwlink/?LinkId=151932).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9e2dd-140">、Microsoft では、これらのツールの使用はサポートされていないと、Microsoft がこれらのプログラムの適合性に関する保証をいたしません。</span><span class="sxs-lookup"><span data-stu-id="9e2dd-140">Use of these tools is not supported by Microsoft, and Microsoft makes no guarantees about the suitability of these programs.</span></span> <span data-ttu-id="9e2dd-141">これらのプログラムは、ユーザー自身の責任で使用してください。</span><span class="sxs-lookup"><span data-stu-id="9e2dd-141">Use of these programs is entirely at your own risk.</span></span>  
  
 <span data-ttu-id="9e2dd-142">**優先度を監視します。**</span><span class="sxs-lookup"><span data-stu-id="9e2dd-142">**Make monitoring a priority**</span></span>  
  
-   <span data-ttu-id="9e2dd-143">BizTalk Server アプリケーションとインフラストラクチャの一貫性のある監視、正常な環境を維持するために不可欠です。</span><span class="sxs-lookup"><span data-stu-id="9e2dd-143">Consistent monitoring of BizTalk Server applications and infrastructure is essential to maintaining a healthy environment.</span></span>  
  
-   <span data-ttu-id="9e2dd-144">定期的に評価し、時間の経過と共に、BizTalk Server アプリケーションとインフラストラクチャの変更として、監視ツールを調整します。</span><span class="sxs-lookup"><span data-stu-id="9e2dd-144">Regularly evaluate and adjust your monitoring tools over time and as your BizTalk Server applications and infrastructure change.</span></span>