---
title: 'フェーズ 3: 評価の準備中 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d153ed62-f2cc-4080-8912-c98ecdd329f5
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 890047f6a13352d89d33d9514883dc20eacd4001
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22301842"
---
# <a name="phase-3-preparing-for-the-assessment"></a><span data-ttu-id="49742-102">フェーズ 3: が評価用に準備します。</span><span class="sxs-lookup"><span data-stu-id="49742-102">Phase 3: Preparing for the Assessment</span></span>
<span data-ttu-id="49742-103">パフォーマンス評価の段階できますと考えるのスコープのフェーズに「方法」"what"と計画フェーズの準備の「ときです」</span><span class="sxs-lookup"><span data-stu-id="49742-103">The Prepare phase of a performance assessment can be thought of as the “how” to the Scope phase’s “what” and the Plan phase’s “when.”</span></span> <span data-ttu-id="49742-104">この時点でパフォーマンス評価はすべての利害関係者必要があります、ラボを実行するため、活動、およびプランのスコープによって、合意しています。</span><span class="sxs-lookup"><span data-stu-id="49742-104">At this point in the performance assessment, all stakeholders should have agreed upon the scope of the engagement and the plans for conducting the lab.</span></span> <span data-ttu-id="49742-105">ここで、プランを実行し、パフォーマンス ラボの実行用に準備する手順を実行のパフォーマンス評価の準備フェーズになります。</span><span class="sxs-lookup"><span data-stu-id="49742-105">It is in the Prepare phase of the performance assessment where the plans are executed and steps are taken to get ready for execution of the performance lab.</span></span>  
  
 <span data-ttu-id="49742-106">このトピックでは、BizTalk Server のパフォーマンス評価の準備フェーズのさまざまな側面について説明します。</span><span class="sxs-lookup"><span data-stu-id="49742-106">This topic describes the various aspects of the Prepare phase of a BizTalk Server performance assessment.</span></span>  
  
## <a name="detailed-design-of-the-solution-platform"></a><span data-ttu-id="49742-107">ソリューション プラットフォームの詳細な設計</span><span class="sxs-lookup"><span data-stu-id="49742-107">Detailed design of the solution platform</span></span>  
 <span data-ttu-id="49742-108">詳細なソリューションの設計では、コミュニケーションを促進し、前提条件、機敏性とすべてのアクティビティの有効性が向上を回避できます。</span><span class="sxs-lookup"><span data-stu-id="49742-108">A detailed solution design facilitates communications and avoids assumptions, which will improve the agility and effectiveness of all activities.</span></span> <span data-ttu-id="49742-109">次の要素完全に文書化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="49742-109">You should fully document the following elements:</span></span>  
  
-   <span data-ttu-id="49742-110">**BizTalk Server データベースおよび複数のコンピューターでの分散方法**-SQL Server のパフォーマンスは、BizTalk Server の全体的なパフォーマンスで重要な要因の 1 つです。</span><span class="sxs-lookup"><span data-stu-id="49742-110">**BizTalk Server databases and how they will be distributed across computers** - SQL Server performance is one of the key factors in overall BizTalk Server performance.</span></span> <span data-ttu-id="49742-111">SQL Server には、リソースの制約が発生していますが、これはメッセージを処理する BizTalk Server の機能が影響します。</span><span class="sxs-lookup"><span data-stu-id="49742-111">If SQL Server is experiencing resource constraints, this will impact the ability of BizTalk Server to process messages.</span></span> <span data-ttu-id="49742-112">BizTalk データベースのパフォーマンスに影響を与える主な要因は、上でホストされているディスクの速度です。</span><span class="sxs-lookup"><span data-stu-id="49742-112">The main factor that influences BizTalk database performance is the speed of disks that they are hosted on.</span></span> <span data-ttu-id="49742-113">各 BizTalk のトランザクション ログとデータベース ファイルの分離を別々 のドライブまたは SAN LUN にデータベースが表示非常に BizTalk Server の全体的なパフォーマンスを向上させる。</span><span class="sxs-lookup"><span data-stu-id="49742-113">Separating the transaction log and database files for each BizTalk database onto separate drives or SAN LUN’s has been shown to remarkably improve the overall performance of BizTalk Server.</span></span> <span data-ttu-id="49742-114">そのため、これが簡単にアクセスできるように、この情報を記録することが重要です。</span><span class="sxs-lookup"><span data-stu-id="49742-114">Therefore, it is important that this information be recorded in an easily accessible manner.</span></span> <span data-ttu-id="49742-115">実稼働環境で使用される値は、詳細なソリューションの設計で文書化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="49742-115">The values that will be used in the production environment should be documented in the detailed solution design.</span></span> <span data-ttu-id="49742-116">次の表は、この実行方法の例を示します。</span><span class="sxs-lookup"><span data-stu-id="49742-116">The following table provides an example of how this can be done.</span></span>  
  
    |<span data-ttu-id="49742-117">BizTalk データベース</span><span class="sxs-lookup"><span data-stu-id="49742-117">BizTalk Database</span></span>|<span data-ttu-id="49742-118">ボリューム名</span><span class="sxs-lookup"><span data-stu-id="49742-118">Volume Name</span></span>|<span data-ttu-id="49742-119">[ファイル]</span><span class="sxs-lookup"><span data-stu-id="49742-119">Files</span></span>|<span data-ttu-id="49742-120">LUN # または ml _ #</span><span class="sxs-lookup"><span data-stu-id="49742-120">LUN# or ML_#</span></span>|<span data-ttu-id="49742-121">物理的な LUN のサイズ (GB)</span><span class="sxs-lookup"><span data-stu-id="49742-121">Physical LUN Size (GB)</span></span>|  
    |----------------------|-----------------|-----------|---------------------|------------------------------|  
    |<span data-ttu-id="49742-122">メッセージ ボックス</span><span class="sxs-lookup"><span data-stu-id="49742-122">MessageBox</span></span>|<span data-ttu-id="49742-123">Data_TempDb_1</span><span class="sxs-lookup"><span data-stu-id="49742-123">Data_TempDb_1</span></span>|<span data-ttu-id="49742-124">TEMPDB、マスターおよび MSDB のデータ ファイル</span><span class="sxs-lookup"><span data-stu-id="49742-124">TEMPDB,  MASTER, and MSDB data files</span></span>|<span data-ttu-id="49742-125">1</span><span class="sxs-lookup"><span data-stu-id="49742-125">1</span></span>|<span data-ttu-id="49742-126">134</span><span class="sxs-lookup"><span data-stu-id="49742-126">134</span></span>|  
    ||<span data-ttu-id="49742-127">Logs_TempDb_1</span><span class="sxs-lookup"><span data-stu-id="49742-127">Logs_TempDb_1</span></span>|<span data-ttu-id="49742-128">TEMPDB、マスターおよび MSDB のトランザクション ログ ファイル</span><span class="sxs-lookup"><span data-stu-id="49742-128">TEMPDB,  MASTER, and MSDB transaction log files</span></span>|<span data-ttu-id="49742-129">2</span><span class="sxs-lookup"><span data-stu-id="49742-129">2</span></span>|<span data-ttu-id="49742-130">134</span><span class="sxs-lookup"><span data-stu-id="49742-130">134</span></span>|  
    ||<span data-ttu-id="49742-131">Data_BtsMsgBox</span><span class="sxs-lookup"><span data-stu-id="49742-131">Data_BtsMsgBox</span></span>|<span data-ttu-id="49742-132">BizTalkMsgBoxDb データ ファイル</span><span class="sxs-lookup"><span data-stu-id="49742-132">BizTalkMsgBoxDb data file</span></span>|<span data-ttu-id="49742-133">3</span><span class="sxs-lookup"><span data-stu-id="49742-133">3</span></span>|<span data-ttu-id="49742-134">134</span><span class="sxs-lookup"><span data-stu-id="49742-134">134</span></span>|  
    ||<span data-ttu-id="49742-135">Logs_BtsMsgBox</span><span class="sxs-lookup"><span data-stu-id="49742-135">Logs_BtsMsgBox</span></span>|<span data-ttu-id="49742-136">BizTalkMsgBoxDb トランザクション ログ ファイル</span><span class="sxs-lookup"><span data-stu-id="49742-136">BizTalkMsgBoxDb transaction log file</span></span>|<span data-ttu-id="49742-137">4</span><span class="sxs-lookup"><span data-stu-id="49742-137">4</span></span>|<span data-ttu-id="49742-138">134</span><span class="sxs-lookup"><span data-stu-id="49742-138">134</span></span>|  
    |<span data-ttu-id="49742-139">BAM</span><span class="sxs-lookup"><span data-stu-id="49742-139">BAM</span></span>|<span data-ttu-id="49742-140">Data_TempDb_2</span><span class="sxs-lookup"><span data-stu-id="49742-140">Data_TempDb_2</span></span>|<span data-ttu-id="49742-141">TEMPDB、マスターおよび MSDB のデータ ファイル</span><span class="sxs-lookup"><span data-stu-id="49742-141">TEMPDB, MASTER, and MSDB data files</span></span>|<span data-ttu-id="49742-142">5</span><span class="sxs-lookup"><span data-stu-id="49742-142">5</span></span>|<span data-ttu-id="49742-143">67</span><span class="sxs-lookup"><span data-stu-id="49742-143">67</span></span>|  
    ||<span data-ttu-id="49742-144">Logs_TempDb_2</span><span class="sxs-lookup"><span data-stu-id="49742-144">Logs_TempDb_2</span></span>|<span data-ttu-id="49742-145">TEMPDB、マスターおよび MSDB のトランザクション ログ ファイル</span><span class="sxs-lookup"><span data-stu-id="49742-145">TEMPDB, MASTER, and MSDB transaction log files</span></span>|<span data-ttu-id="49742-146">6</span><span class="sxs-lookup"><span data-stu-id="49742-146">6</span></span>|<span data-ttu-id="49742-147">67</span><span class="sxs-lookup"><span data-stu-id="49742-147">67</span></span>|  
    ||<span data-ttu-id="49742-148">Data_BAM</span><span class="sxs-lookup"><span data-stu-id="49742-148">Data_BAM</span></span>|<span data-ttu-id="49742-149">BAMPrimaryImport のデータ ファイル</span><span class="sxs-lookup"><span data-stu-id="49742-149">BAMPrimaryImport data file</span></span>|<span data-ttu-id="49742-150">7</span><span class="sxs-lookup"><span data-stu-id="49742-150">7</span></span>|<span data-ttu-id="49742-151">134</span><span class="sxs-lookup"><span data-stu-id="49742-151">134</span></span>|  
    ||<span data-ttu-id="49742-152">Logs_BAM</span><span class="sxs-lookup"><span data-stu-id="49742-152">Logs_BAM</span></span>|<span data-ttu-id="49742-153">BAMPrimaryImport のトランザクション ログ ファイル</span><span class="sxs-lookup"><span data-stu-id="49742-153">BAMPrimaryImport transaction log file</span></span>|<span data-ttu-id="49742-154">8</span><span class="sxs-lookup"><span data-stu-id="49742-154">8</span></span>|<span data-ttu-id="49742-155">134</span><span class="sxs-lookup"><span data-stu-id="49742-155">134</span></span>|  
    |<span data-ttu-id="49742-156">BizTalk 追跡、管理、シングル サインオンおよびルール エンジン データベース</span><span class="sxs-lookup"><span data-stu-id="49742-156">BizTalk Tracking, Management, Single Sign-On, and Rule Engine databases</span></span>|<span data-ttu-id="49742-157">Data_TempDb_3</span><span class="sxs-lookup"><span data-stu-id="49742-157">Data_TempDb_3</span></span>|<span data-ttu-id="49742-158">TEMPDB、MASTER、MSDB、BizTalkDTADb、BizTalkMgmtDb、ENTSSO、および BizTalkRuleEngineDb のデータ ファイル</span><span class="sxs-lookup"><span data-stu-id="49742-158">TEMPDB,  MASTER, MSDB, BizTalkDTADb, BizTalkMgmtDb, ENTSSO, and BizTalkRuleEngineDb data files</span></span>|<span data-ttu-id="49742-159">9</span><span class="sxs-lookup"><span data-stu-id="49742-159">9</span></span>|<span data-ttu-id="49742-160">67</span><span class="sxs-lookup"><span data-stu-id="49742-160">67</span></span>|  
    ||<span data-ttu-id="49742-161">Logs_TempDb_3</span><span class="sxs-lookup"><span data-stu-id="49742-161">Logs_TempDb_3</span></span>|<span data-ttu-id="49742-162">TEMPDB、MASTER、MSDB、BizTalkDTADb、BizTalkMgmtDb、ENTSSO、および BizTalkRuleEngineDb のトランザクション ログ ファイル</span><span class="sxs-lookup"><span data-stu-id="49742-162">TEMPDB,  MASTER, MSDB, BizTalkDTADb, BizTalkMgmtDb, ENTSSO, and BizTalkRuleEngineDb transaction log files</span></span>|<span data-ttu-id="49742-163">10</span><span class="sxs-lookup"><span data-stu-id="49742-163">10</span></span>|<span data-ttu-id="49742-164">67</span><span class="sxs-lookup"><span data-stu-id="49742-164">67</span></span>|  
  
-   <span data-ttu-id="49742-165">**BizTalk ホストの設計と各ホストおよびそのインスタンスの説明。**</span><span class="sxs-lookup"><span data-stu-id="49742-165">**BizTalk Host design and descriptions of each host and their instances.**</span></span>  
  
-   <span data-ttu-id="49742-166">**各オーケストレーションの説明です。**</span><span class="sxs-lookup"><span data-stu-id="49742-166">**Description of each orchestration.**</span></span>  
  
-   <span data-ttu-id="49742-167">**各パイプラインの説明です。**</span><span class="sxs-lookup"><span data-stu-id="49742-167">**Description of each pipeline.**</span></span>  
  
-   <span data-ttu-id="49742-168">**.NET アセンブリなどのカスタム コンポーネント、COM + コンポーネントの説明です。**</span><span class="sxs-lookup"><span data-stu-id="49742-168">**Description of custom components such as .NET assemblies and COM+ components.**</span></span>  
  
## <a name="detailed-architecture-diagram"></a><span data-ttu-id="49742-169">詳細なアーキテクチャ ダイアグラム</span><span class="sxs-lookup"><span data-stu-id="49742-169">Detailed architecture diagram</span></span>  
 <span data-ttu-id="49742-170">次の図は、パフォーマンスの評価のために使用できるアーキテクチャの図を示しています。</span><span class="sxs-lookup"><span data-stu-id="49742-170">The following diagram illustrates an architecture diagram that could be used for a performance assessment.</span></span>  
  
 <span data-ttu-id="49742-171">![BizTalk アーキテクチャ図](../technical-guides/media/architecturediagram.gif "ArchitectureDiagram")</span><span class="sxs-lookup"><span data-stu-id="49742-171">![BizTalk Architecture Diagram](../technical-guides/media/architecturediagram.gif "ArchitectureDiagram")</span></span>  
<span data-ttu-id="49742-172">BizTalk アーキテクチャ図</span><span class="sxs-lookup"><span data-stu-id="49742-172">BizTalk Architecture Diagram</span></span>  
  
## <a name="message-flow-diagrams"></a><span data-ttu-id="49742-173">メッセージ フロー図</span><span class="sxs-lookup"><span data-stu-id="49742-173">Message flow diagrams</span></span>  
 <span data-ttu-id="49742-174">メッセージを処理中に発生することにどのようななってに関する混乱または false の前提条件を防ぐために役立つ詳細なメッセージのフロー チャートを作成します。</span><span class="sxs-lookup"><span data-stu-id="49742-174">Create detailed message flow diagrams to help prevent confusion or false assumptions regarding what is supposed to be happening to messages during processing.</span></span>  
  
 <span data-ttu-id="49742-175">を検討するとき、BizTalk ソリューションに関する包括的なシステムのメッセージ フローと考える傾向があります。</span><span class="sxs-lookup"><span data-stu-id="49742-175">When thinking about a BizTalk solution holistically, we tend to think of the message flow through the system.</span></span> <span data-ttu-id="49742-176">このメッセージの流れパースペクティブは、パフォーマンス、フローのすべての部分は、潜在的なボトルネックと見なされる必要があるためにテストを実施する際に特に重要です。</span><span class="sxs-lookup"><span data-stu-id="49742-176">This Message Flow perspective is especially important when doing performance testing because all parts of the flow must be considered as potential bottlenecks.</span></span> <span data-ttu-id="49742-177">メッセージ フロー図を持つ、混乱を防止またはメッセージを各テスト中に発生することにどのようななってに関する誤った想定を実行します。</span><span class="sxs-lookup"><span data-stu-id="49742-177">Having a message flow diagram prevents any confusion or false assumptions regarding what is supposed to be happening to messages during each test run.</span></span>  
  
 <span data-ttu-id="49742-178">次の例では、単純なの Visio 図形を使用して作成された背景に関係なく、プロジェクトのすべてのユーザーにすばやく理解できるシステムにメッセージを取得する方法、ソリューションのどの部分と対話し、メッセージを最後にした後、メッセージが入る場所処理しています。</span><span class="sxs-lookup"><span data-stu-id="49742-178">In the following example, created using simple Visio shapes, everyone on the project regardless of background can quickly understand how a message gets into the system, what parts of the solutions interact with the message, and finally where the message lands after processing.</span></span>  
  
 <span data-ttu-id="49742-179">![Message Flow Diagram](../technical-guides/media/11c5afac-5c1b-42a5-8947-7c6d0ca4e2df.gif "11c5afac-5c1b-42a5-8947-7c6d0ca4e2df")</span><span class="sxs-lookup"><span data-stu-id="49742-179">![Message Flow Diagram](../technical-guides/media/11c5afac-5c1b-42a5-8947-7c6d0ca4e2df.gif "11c5afac-5c1b-42a5-8947-7c6d0ca4e2df")</span></span>  
<span data-ttu-id="49742-180">メッセージ フロー図</span><span class="sxs-lookup"><span data-stu-id="49742-180">Message Flow Diagram</span></span>  
  
 <span data-ttu-id="49742-181">メッセージのフロー チャートを作成するときに、次の詳細を検討してください。</span><span class="sxs-lookup"><span data-stu-id="49742-181">The following details should be considered when creating the message flow diagrams:</span></span>  
  
-   <span data-ttu-id="49742-182">すべての結果として得られるメッセージが送信され、すべての関連する処理が完了するまで、受信場所に到着した時点からのメッセージの種類ごとのライフ サイクルについて説明します。</span><span class="sxs-lookup"><span data-stu-id="49742-182">Describe the lifecycle of each type of message from the time it arrives at a receive location until all resulting messages are sent and all related processing is completed.</span></span>  
  
-   <span data-ttu-id="49742-183">エラー条件の処理がどのように変化するかについて説明します。</span><span class="sxs-lookup"><span data-stu-id="49742-183">Describe how processing changes for error conditions.</span></span>  
  
-   <span data-ttu-id="49742-184">詳細についてには、相関関係、配信通知、および受信確認が含まれます。</span><span class="sxs-lookup"><span data-stu-id="49742-184">Include details about correlation, delivery notifications, and acknowledgements.</span></span>  
  
-   <span data-ttu-id="49742-185">外部システムへの依存度に関する詳細が含まれます。</span><span class="sxs-lookup"><span data-stu-id="49742-185">Include details about dependence on external systems.</span></span>  
  
-   <span data-ttu-id="49742-186">待機時間とスループットに関するパフォーマンスの要件の情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="49742-186">Include performance requirement information regarding latency and throughput.</span></span>  
  
## <a name="third-party-software-details"></a><span data-ttu-id="49742-187">サード パーティ製ソフトウェアの詳細</span><span class="sxs-lookup"><span data-stu-id="49742-187">Third-party software details</span></span>  
 <span data-ttu-id="49742-188">詳細なソリューション設計の一部として使用されるすべての Microsoft 以外のソフトウェアを完全に記載されています。</span><span class="sxs-lookup"><span data-stu-id="49742-188">All non-Microsoft software that is used should be fully documented as part of the detailed solution design.</span></span>  
  
## <a name="detailed-lab-hardware-stack"></a><span data-ttu-id="49742-189">詳細なラボ ハードウェア スタック</span><span class="sxs-lookup"><span data-stu-id="49742-189">Detailed lab hardware stack</span></span>  
 <span data-ttu-id="49742-190">以前に作成した高度なハードウェア図上の構築、次のハードウェア情報を完全に記述します。</span><span class="sxs-lookup"><span data-stu-id="49742-190">Building on the previously created high-level hardware diagram, the following hardware information should be fully documented:</span></span>  
  
-   <span data-ttu-id="49742-191">[プロセッサ]</span><span class="sxs-lookup"><span data-stu-id="49742-191">Processors</span></span>  
  
    -   <span data-ttu-id="49742-192">型</span><span class="sxs-lookup"><span data-stu-id="49742-192">Type</span></span>  
  
    -   <span data-ttu-id="49742-193">速度</span><span class="sxs-lookup"><span data-stu-id="49742-193">Speed</span></span>  
  
    -   <span data-ttu-id="49742-194">コアの数</span><span class="sxs-lookup"><span data-stu-id="49742-194">Number of cores</span></span>  
  
    -   <span data-ttu-id="49742-195">ハイパースレッディングが有効</span><span class="sxs-lookup"><span data-stu-id="49742-195">Hyperthreading</span></span>  
  
-   <span data-ttu-id="49742-196">[メモリ]</span><span class="sxs-lookup"><span data-stu-id="49742-196">Memory</span></span>  
  
    -   <span data-ttu-id="49742-197">Amount</span><span class="sxs-lookup"><span data-stu-id="49742-197">Amount</span></span>  
  
    -   <span data-ttu-id="49742-198">速度</span><span class="sxs-lookup"><span data-stu-id="49742-198">Speed</span></span>  
  
    -   <span data-ttu-id="49742-199">パリティ</span><span class="sxs-lookup"><span data-stu-id="49742-199">Parity</span></span>  
  
-   <span data-ttu-id="49742-200">ネットワーク</span><span class="sxs-lookup"><span data-stu-id="49742-200">Network</span></span>  
  
    -   <span data-ttu-id="49742-201">ネットワーク インターフェイス カード (Nic) の数</span><span class="sxs-lookup"><span data-stu-id="49742-201">Number of network interface cards (NICs)</span></span>  
  
    -   <span data-ttu-id="49742-202">ネットワークの速度</span><span class="sxs-lookup"><span data-stu-id="49742-202">Speed of network</span></span>  
  
-   <span data-ttu-id="49742-203">SAN</span><span class="sxs-lookup"><span data-stu-id="49742-203">SAN</span></span>  
  
    -   <span data-ttu-id="49742-204">各コンピューターでの SAN カードの数</span><span class="sxs-lookup"><span data-stu-id="49742-204">Number of SAN cards in each computer</span></span>  
  
    -   <span data-ttu-id="49742-205">各コンピューターと各 LUN の目的の論理ユニット番号 (Lun) の数</span><span class="sxs-lookup"><span data-stu-id="49742-205">Number of logical unit numbers (LUNs) for each computer and purpose for each LUN</span></span>  
  
    -   <span data-ttu-id="49742-206">記憶域の速度のネットワーク (SAN) カード</span><span class="sxs-lookup"><span data-stu-id="49742-206">Speed of storage area network (SAN) Cards</span></span>  
  
    -   <span data-ttu-id="49742-207">SAN 構成の詳細をカードします。</span><span class="sxs-lookup"><span data-stu-id="49742-207">SAN card configuration details</span></span>  
  
    -   <span data-ttu-id="49742-208">SAN ディスクの割り当て、書式設定、およびパーティション分割</span><span class="sxs-lookup"><span data-stu-id="49742-208">SAN disk allocation, formatting, and partitioning</span></span>  
  
-   <span data-ttu-id="49742-209">[ディスク]</span><span class="sxs-lookup"><span data-stu-id="49742-209">Disk</span></span>  
  
    -   <span data-ttu-id="49742-210">各コンピューターのローカル ディスクの詳細</span><span class="sxs-lookup"><span data-stu-id="49742-210">Local disk details for each computer</span></span>  
  
    -   <span data-ttu-id="49742-211">ローカル ディスクの使用の書式設定</span><span class="sxs-lookup"><span data-stu-id="49742-211">Formatting used for local disks</span></span>  
  
    -   <span data-ttu-id="49742-212">ローカル ディスクのパーティション分割の詳細</span><span class="sxs-lookup"><span data-stu-id="49742-212">Partitioning details for local disks</span></span>  
  
-   <span data-ttu-id="49742-213">Cache</span><span class="sxs-lookup"><span data-stu-id="49742-213">Cache</span></span>  
  
    -   <span data-ttu-id="49742-214">L2 キャッシュの容量</span><span class="sxs-lookup"><span data-stu-id="49742-214">L2 Cache amount</span></span>  
  
    -   <span data-ttu-id="49742-215">L3 キャッシュ容量</span><span class="sxs-lookup"><span data-stu-id="49742-215">L3 Cache amount</span></span>  
  
## <a name="detailed-lab-software-stack"></a><span data-ttu-id="49742-216">詳細なラボ ソフトウェア スタック</span><span class="sxs-lookup"><span data-stu-id="49742-216">Detailed lab software stack</span></span>  
 <span data-ttu-id="49742-217">次のソフトウェアの情報を文書化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="49742-217">The following software information should be documented:</span></span>  
  
-   <span data-ttu-id="49742-218">特定のオペレーティング システムのバージョン、エディション、およびアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="49742-218">Specific operating system versions, editions, and architecture</span></span>  
  
-   <span data-ttu-id="49742-219">特定のオペレーティング システムの機能</span><span class="sxs-lookup"><span data-stu-id="49742-219">Specific operating system features</span></span>  
  
-   <span data-ttu-id="49742-220">各コンピューターにインストールされている特定のソフトウェア</span><span class="sxs-lookup"><span data-stu-id="49742-220">Specific software installed on each computer</span></span>  
  
-   <span data-ttu-id="49742-221">特定のドライバー</span><span class="sxs-lookup"><span data-stu-id="49742-221">Specific drivers</span></span>  
  
-   <span data-ttu-id="49742-222">サービス パックおよびその他の更新プログラム</span><span class="sxs-lookup"><span data-stu-id="49742-222">Service Packs and other updates</span></span>  
  
-   <span data-ttu-id="49742-223">既定値と異なっている場合に使用されるすべてのソフトウェアとオペレーティング システムの機能の構成値</span><span class="sxs-lookup"><span data-stu-id="49742-223">Configuration values for all software and operating system features used if they vary from default values</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49742-224">参照</span><span class="sxs-lookup"><span data-stu-id="49742-224">See Also</span></span>  
 [<span data-ttu-id="49742-225">パフォーマンス評価の段階</span><span class="sxs-lookup"><span data-stu-id="49742-225">Phases of a Performance Assessment</span></span>](../technical-guides/phases-of-a-performance-assessment.md)