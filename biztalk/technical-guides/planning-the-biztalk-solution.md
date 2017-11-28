---
title: "BizTalk ソリューションの計画 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 30d56a04-966a-46b1-861d-f5be4e58b7d2
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 74b7cbe23a6fc818428478859ea021d4fbf38546
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="planning-the-biztalk-solution"></a><span data-ttu-id="71351-102">BizTalk ソリューションの計画</span><span class="sxs-lookup"><span data-stu-id="71351-102">Planning the BizTalk Solution</span></span>
<span data-ttu-id="71351-103">主な設計目標の 1 つ[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]できるだけ多くの処理シナリオに対応するために最大限の柔軟性を提供することです。</span><span class="sxs-lookup"><span data-stu-id="71351-103">One of the primary design goals of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is to provide maximum flexibility for accommodating as many processing scenarios as possible.</span></span> <span data-ttu-id="71351-104">この柔軟のための機能を最大限に使用で利用できるようにする方法を決定する主に、BizTalk ソリューションの開発者が直面する課題の 1 つは[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]最適なビジネス ニーズに対応します。</span><span class="sxs-lookup"><span data-stu-id="71351-104">Because of this great flexibility, one of the primary challenges facing developers of a BizTalk solution is to determine how to make best use of the features available in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to best meet their business needs.</span></span> <span data-ttu-id="71351-105">計画、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]以下にまとめますフェーズに分けることができます。</span><span class="sxs-lookup"><span data-stu-id="71351-105">Planning the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] can be broken down into distinct phases which are summarized below.</span></span>  
  
## <a name="scoping-the-solution"></a><span data-ttu-id="71351-106">ソリューションのスコープ</span><span class="sxs-lookup"><span data-stu-id="71351-106">Scoping the Solution</span></span>  
  
### <a name="performance-considerations"></a><span data-ttu-id="71351-107">パフォーマンスに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="71351-107">Performance Considerations</span></span>  
 <span data-ttu-id="71351-108">BizTalk ソリューションを限定するときは、次を考慮してください。</span><span class="sxs-lookup"><span data-stu-id="71351-108">Consider the following when scoping your BizTalk solution:</span></span>  
  
-   <span data-ttu-id="71351-109">どのアダプターやアクセラレータが必要ですか。</span><span class="sxs-lookup"><span data-stu-id="71351-109">Which adapters and/or accelerators are required?</span></span>  
  
-   <span data-ttu-id="71351-110">ソリューションのオーケストレーションを実装するための要件とは</span><span class="sxs-lookup"><span data-stu-id="71351-110">What are the requirements for implementing orchestrations in the solution?</span></span>  
  
-   <span data-ttu-id="71351-111">ドキュメントのスループットの要件: ソリューションの最大スループット要件は何ですか?</span><span class="sxs-lookup"><span data-stu-id="71351-111">Document throughput requirements: What are the maximum sustainable throughput requirements for the solution?</span></span>  
  
-   <span data-ttu-id="71351-112">待機時間の要件: 応答は、ソリューションである必要な送信請求-応答と要求-応答のシナリオのですか?</span><span class="sxs-lookup"><span data-stu-id="71351-112">Latency requirements: How responsive does the solution need to be for solicit-response and request-response scenarios?</span></span>  
  
-   <span data-ttu-id="71351-113">ソリューションは、ピーク時のドキュメントの読み込みの期間からどの程度回復しますか。</span><span class="sxs-lookup"><span data-stu-id="71351-113">How well does the solution recover from periods of peak document load?</span></span>  
  
-   <span data-ttu-id="71351-114">ソリューションの高可用性の要件とは</span><span class="sxs-lookup"><span data-stu-id="71351-114">What are the high availability requirements of the solution?</span></span>  
  
-   <span data-ttu-id="71351-115">ソリューションのドキュメント追跡の要件とは</span><span class="sxs-lookup"><span data-stu-id="71351-115">What are the document tracking requirements of the solution?</span></span>  
  
-   <span data-ttu-id="71351-116">リモートの Web サービスやその他のシステムなど、依存するアプリケーションのパフォーマンス特性を挙げてください。</span><span class="sxs-lookup"><span data-stu-id="71351-116">What are the performance characteristics of any dependent applications such as a remote Web service or other system?</span></span> <span data-ttu-id="71351-117">依存するアプリケーションを必要な負荷で保持しない場合、システム全体のパフォーマンスが低下するそれに応じて。</span><span class="sxs-lookup"><span data-stu-id="71351-117">If dependent applications do not keep up with the required load then the overall system performance will be degraded accordingly.</span></span>  
  
-   <span data-ttu-id="71351-118">BizTalk アプリケーションが消費しているデータベースに関連していない[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]しますか?</span><span class="sxs-lookup"><span data-stu-id="71351-118">Would the BizTalk application be consuming databases not related to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]?</span></span> <span data-ttu-id="71351-119">たとえば、BizTalk アプリケーションには、SQL アダプターを使用して SQL Server データベースのテーブルが使用して場合、は、テーブル効率的に構成しますか。</span><span class="sxs-lookup"><span data-stu-id="71351-119">For example, if the BizTalk application is consuming tables in a SQL Server database using the SQL adapter, are the tables efficiently configured?</span></span>  
  
### <a name="hardware-considerations"></a><span data-ttu-id="71351-120">ハードウェアについての注意事項</span><span class="sxs-lookup"><span data-stu-id="71351-120">Hardware Considerations</span></span>  
 <span data-ttu-id="71351-121">ソリューションを限定するときは、次のハードウェアの高度なダイアグラムを作成します。</span><span class="sxs-lookup"><span data-stu-id="71351-121">When scoping the solution, create a high-level hardware diagram that includes the following:</span></span>  
  
-   <span data-ttu-id="71351-122">(X86、x64、および IA64) などのコンピューターのアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="71351-122">Computer architecture (such as x86, x64, and IA64)</span></span>  
  
-   <span data-ttu-id="71351-123">(種類、速度、数、コア、ハイパー スレッドの使用など) の CPU 要件</span><span class="sxs-lookup"><span data-stu-id="71351-123">CPU requirements (such as type, speed, number, cores, and use of hyperthreading)</span></span>  
  
-   <span data-ttu-id="71351-124">各コンピューターの RAM の要件</span><span class="sxs-lookup"><span data-stu-id="71351-124">RAM requirements for each computer</span></span>  
  
-   <span data-ttu-id="71351-125">ローカル ディスク ストレージ (型、サイズ、速度)</span><span class="sxs-lookup"><span data-stu-id="71351-125">Local disk storage (type, size, speed)</span></span>  
  
-   <span data-ttu-id="71351-126">SAN (記憶域の要件: LUN の数SAN カードの種類)</span><span class="sxs-lookup"><span data-stu-id="71351-126">SAN (storage requirements: number of LUNS; SAN card type)</span></span>  
  
-   <span data-ttu-id="71351-127">ネットワーク カード (1 ギガビットと 100 メガ ビット (Mbps) は、各コンピューターの数 (1 Gbps) です)。</span><span class="sxs-lookup"><span data-stu-id="71351-127">Network cards (number in each computer, 100 megabits (Mbps) versus 1 Gigabit (1 Gbps).)</span></span>  
  
-   <span data-ttu-id="71351-128">ファイアウォールをソリューションに展開するにはどうされますか。</span><span class="sxs-lookup"><span data-stu-id="71351-128">How will firewalls be deployed in the solution?</span></span>  
  
-   <span data-ttu-id="71351-129">ハードウェアのネットワーク負荷分散が使用されますか。</span><span class="sxs-lookup"><span data-stu-id="71351-129">Will Network Load Balancing hardware be used?</span></span>  
  
-   <span data-ttu-id="71351-130">クラスター化する特定のコンピューターとは</span><span class="sxs-lookup"><span data-stu-id="71351-130">Are specific computers to be clustered?</span></span>  
  
-   <span data-ttu-id="71351-131">Microsoft HYPER-V Server またはその他の仮想化製品に関連する仮想環境を使用するか。</span><span class="sxs-lookup"><span data-stu-id="71351-131">Would you be using a virtual environment involving Microsoft Hyper-V Server or any other virtualization products?</span></span>  
  
## <a name="planning-the-solution"></a><span data-ttu-id="71351-132">ソリューションの計画</span><span class="sxs-lookup"><span data-stu-id="71351-132">Planning the Solution</span></span>  
  
### <a name="solution-milestones-timeline"></a><span data-ttu-id="71351-133">ソリューションのマイルス トーンのタイムライン</span><span class="sxs-lookup"><span data-stu-id="71351-133">Solution Milestones Timeline</span></span>  
 <span data-ttu-id="71351-134">BizTalk ソリューションの特定の側面を完了するためのマイルス トーンをスケジュールを作成します。</span><span class="sxs-lookup"><span data-stu-id="71351-134">Create a schedule with milestones for completing specific aspects of your BizTalk solution.</span></span> <span data-ttu-id="71351-135">特定のマイルス トーンを設定するソリューションとなる可能性が高くなりますが、適切なタイミングで完了しました。</span><span class="sxs-lookup"><span data-stu-id="71351-135">Setting specific milestones will increase the likelihood that the solution will be completed in a timely manner.</span></span>  
  
### <a name="non-microsoft-software-considerations"></a><span data-ttu-id="71351-136">Microsoft 以外のソフトウェアの考慮事項</span><span class="sxs-lookup"><span data-stu-id="71351-136">Non-Microsoft Software Considerations</span></span>  
 <span data-ttu-id="71351-137">Microsoft 以外のソフトウェアが、ソリューションで使用する場合は、次を考慮します。</span><span class="sxs-lookup"><span data-stu-id="71351-137">Consider the following when non-Microsoft software will be used with the solution:</span></span>  
  
-   <span data-ttu-id="71351-138">ソフトウェアまたはハードウェアは必要のある方法の決定を取得します。</span><span class="sxs-lookup"><span data-stu-id="71351-138">Determine how the software or hardware required be obtained.</span></span>  
  
-   <span data-ttu-id="71351-139">容量計画を作成し、サイズ変更する Microsoft 以外のソフトウェアを確実には、ソリューション内のボトルネックにはなりません。</span><span class="sxs-lookup"><span data-stu-id="71351-139">Plan for capacity and sizing to ensure that non-Microsoft software does not become a bottleneck in your solution.</span></span>  
  
-   <span data-ttu-id="71351-140">必要な Microsoft 以外のソフトウェアをインストールするためのアクションのプランを決定します。</span><span class="sxs-lookup"><span data-stu-id="71351-140">Determine a plan of action for installing required non-Microsoft software.</span></span>  
  
-   <span data-ttu-id="71351-141">アクションを構成し、必要な Microsoft 以外のソフトウェアを最適化するためのプランを作成します。</span><span class="sxs-lookup"><span data-stu-id="71351-141">Create a plan of action for configuring and optimizing required non-Microsoft software.</span></span>  
  
## <a name="preparing-for-the-solution"></a><span data-ttu-id="71351-142">ソリューションの準備をしています</span><span class="sxs-lookup"><span data-stu-id="71351-142">Preparing for the Solution</span></span>  
 <span data-ttu-id="71351-143">準備フェーズでは、次の要素を含めます。</span><span class="sxs-lookup"><span data-stu-id="71351-143">Include the following elements in your preparation phase:</span></span>  
  
### <a name="detailed-design-of-the-solution-platform"></a><span data-ttu-id="71351-144">ソリューション プラットフォームの詳細な設計</span><span class="sxs-lookup"><span data-stu-id="71351-144">Detailed Design of the Solution Platform</span></span>  
 <span data-ttu-id="71351-145">詳細なソリューションの設計では、コミュニケーションを促進し、前提条件、機敏性とすべてのアクティビティの有効性が向上を回避できます。</span><span class="sxs-lookup"><span data-stu-id="71351-145">A detailed solution design facilitates communications and avoids assumptions, which will improve the agility and effectiveness of all activities.</span></span> <span data-ttu-id="71351-146">次の要素完全に文書化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="71351-146">You should fully document the following elements:</span></span>  
  
-   <span data-ttu-id="71351-147">BizTalk Server データベースと複数のコンピューターでの分散方法。</span><span class="sxs-lookup"><span data-stu-id="71351-147">BizTalk Server databases and how they will be distributed across computers.</span></span>  
  
-   <span data-ttu-id="71351-148">BizTalk ホストの設計と各ホストおよびそのインスタンスの説明。</span><span class="sxs-lookup"><span data-stu-id="71351-148">BizTalk Host design and descriptions of each host and their instances.</span></span>  
  
-   <span data-ttu-id="71351-149">各オーケストレーションの説明です。</span><span class="sxs-lookup"><span data-stu-id="71351-149">Description of each orchestration.</span></span>  
  
-   <span data-ttu-id="71351-150">各パイプラインの説明です。</span><span class="sxs-lookup"><span data-stu-id="71351-150">Description of each pipeline.</span></span>  
  
-   <span data-ttu-id="71351-151">.NET アセンブリなどのカスタム コンポーネント、COM + コンポーネントの説明です。</span><span class="sxs-lookup"><span data-stu-id="71351-151">Description of custom components such as .NET assemblies and COM+ components.</span></span>  
  
 <span data-ttu-id="71351-152">**メッセージ フロー図**</span><span class="sxs-lookup"><span data-stu-id="71351-152">**Message Flow Diagrams**</span></span>  
  
 <span data-ttu-id="71351-153">メッセージを処理中に発生することにどのようななってに関する混乱や false 前提条件を回避するための詳細なメッセージ フロー図を作成します。</span><span class="sxs-lookup"><span data-stu-id="71351-153">Create detailed message flow diagrams to help avoid any confusion or false assumptions regarding what is supposed to be happening to messages during processing.</span></span> <span data-ttu-id="71351-154">メッセージのフロー チャートを作成するときに、次の詳細を検討してください。</span><span class="sxs-lookup"><span data-stu-id="71351-154">The following details should be considered when creating the message flow diagrams:</span></span>  
  
-   <span data-ttu-id="71351-155">すべての結果として得られるメッセージが送信され、すべての関連する処理が完了するまで、受信場所に到着した時点からのメッセージの種類ごとのライフ サイクルについて説明します。</span><span class="sxs-lookup"><span data-stu-id="71351-155">Describe the lifecycle of each type of message from the time it arrives at a receive location until all resulting messages are sent and all related processing is completed.</span></span>  
  
-   <span data-ttu-id="71351-156">エラー条件の処理がどのように変化するかについて説明します。</span><span class="sxs-lookup"><span data-stu-id="71351-156">Describe how processing changes for error conditions.</span></span>  
  
-   <span data-ttu-id="71351-157">詳細についてには、相関関係、配信通知、および受信確認が含まれます。</span><span class="sxs-lookup"><span data-stu-id="71351-157">Include details about correlation, delivery notifications, and acknowledgements.</span></span>  
  
-   <span data-ttu-id="71351-158">待機時間とスループットに関するパフォーマンスの要件の情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="71351-158">Include performance requirement information regarding latency and throughput.</span></span>  
  
 <span data-ttu-id="71351-159">**Microsoft 以外のソフトウェアの詳細**</span><span class="sxs-lookup"><span data-stu-id="71351-159">**Non-Microsoft Software Details**</span></span>  
  
 <span data-ttu-id="71351-160">詳細なソリューション設計の一部として使用されるすべての Microsoft 以外のソフトウェアを完全に記載されています。</span><span class="sxs-lookup"><span data-stu-id="71351-160">All non-Microsoft software that is used should be fully documented as part of the detailed solution design.</span></span>  
  
 <span data-ttu-id="71351-161">**詳細なハードウェア スタック**</span><span class="sxs-lookup"><span data-stu-id="71351-161">**Detailed Hardware Stack**</span></span>  
  
 <span data-ttu-id="71351-162">以前に作成した高レベルのハードウェア図上の構築、次のハードウェア情報を完全に記述します。</span><span class="sxs-lookup"><span data-stu-id="71351-162">Building on the previously created high level hardware diagram, the following hardware information should be fully documented:</span></span>  
  
-   <span data-ttu-id="71351-163">[プロセッサ]</span><span class="sxs-lookup"><span data-stu-id="71351-163">Processors</span></span>  
  
    -   <span data-ttu-id="71351-164">型</span><span class="sxs-lookup"><span data-stu-id="71351-164">Type</span></span>  
  
    -   <span data-ttu-id="71351-165">速度</span><span class="sxs-lookup"><span data-stu-id="71351-165">Speed</span></span>  
  
    -   <span data-ttu-id="71351-166">コアの数</span><span class="sxs-lookup"><span data-stu-id="71351-166">Number of cores</span></span>  
  
    -   <span data-ttu-id="71351-167">ハイパースレッディングが有効</span><span class="sxs-lookup"><span data-stu-id="71351-167">Hyperthreading</span></span>  
  
-   <span data-ttu-id="71351-168">[メモリ]</span><span class="sxs-lookup"><span data-stu-id="71351-168">Memory</span></span>  
  
    -   <span data-ttu-id="71351-169">Amount</span><span class="sxs-lookup"><span data-stu-id="71351-169">Amount</span></span>  
  
    -   <span data-ttu-id="71351-170">速度</span><span class="sxs-lookup"><span data-stu-id="71351-170">Speed</span></span>  
  
    -   <span data-ttu-id="71351-171">パリティ</span><span class="sxs-lookup"><span data-stu-id="71351-171">Parity</span></span>  
  
-   <span data-ttu-id="71351-172">ネットワーク</span><span class="sxs-lookup"><span data-stu-id="71351-172">Network</span></span>  
  
    -   <span data-ttu-id="71351-173">ネットワーク インターフェイス カード (Nic) の数</span><span class="sxs-lookup"><span data-stu-id="71351-173">Number of network interface cards (NICs)</span></span>  
  
    -   <span data-ttu-id="71351-174">ネットワークの速度</span><span class="sxs-lookup"><span data-stu-id="71351-174">Speed of network</span></span>  
  
-   <span data-ttu-id="71351-175">SAN</span><span class="sxs-lookup"><span data-stu-id="71351-175">SAN</span></span>  
  
    -   <span data-ttu-id="71351-176">各コンピューターでの SAN カードの数</span><span class="sxs-lookup"><span data-stu-id="71351-176">Number of SAN cards in each computer</span></span>  
  
    -   <span data-ttu-id="71351-177">各コンピューターと各 LUN の目的の論理ユニット番号 (Lun) の数</span><span class="sxs-lookup"><span data-stu-id="71351-177">Number of logical unit numbers (LUNs) for each computer and purpose for each LUN</span></span>  
  
    -   <span data-ttu-id="71351-178">記憶域の速度のネットワーク (SAN) カード</span><span class="sxs-lookup"><span data-stu-id="71351-178">Speed of storage area network (SAN) Cards</span></span>  
  
    -   <span data-ttu-id="71351-179">SAN 構成の詳細をカードします。</span><span class="sxs-lookup"><span data-stu-id="71351-179">SAN card configuration details</span></span>  
  
    -   <span data-ttu-id="71351-180">SAN ディスクの割り当て、書式設定、およびパーティション分割</span><span class="sxs-lookup"><span data-stu-id="71351-180">SAN disk allocation, formatting, and partitioning</span></span>  
  
-   <span data-ttu-id="71351-181">[ディスク]</span><span class="sxs-lookup"><span data-stu-id="71351-181">Disk</span></span>  
  
    -   <span data-ttu-id="71351-182">各コンピューターのローカル ディスクの詳細</span><span class="sxs-lookup"><span data-stu-id="71351-182">Local disk details for each computer</span></span>  
  
    -   <span data-ttu-id="71351-183">ローカル ディスクの使用の書式設定</span><span class="sxs-lookup"><span data-stu-id="71351-183">Formatting used for local disks</span></span>  
  
    -   <span data-ttu-id="71351-184">ローカル ディスクのパーティション分割の詳細</span><span class="sxs-lookup"><span data-stu-id="71351-184">Partitioning details for local disks</span></span>  
  
-   <span data-ttu-id="71351-185">Cache</span><span class="sxs-lookup"><span data-stu-id="71351-185">Cache</span></span>  
  
    -   <span data-ttu-id="71351-186">L2 キャッシュの容量</span><span class="sxs-lookup"><span data-stu-id="71351-186">L2 Cache amount</span></span>  
  
    -   <span data-ttu-id="71351-187">L3 キャッシュ容量</span><span class="sxs-lookup"><span data-stu-id="71351-187">L3 Cache amount</span></span>  
  
 <span data-ttu-id="71351-188">**詳細なソフトウェア スタック**</span><span class="sxs-lookup"><span data-stu-id="71351-188">**Detailed Software Stack**</span></span>  
  
 <span data-ttu-id="71351-189">次のソフトウェアの情報を文書化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="71351-189">The following software information should be documented:</span></span>  
  
-   <span data-ttu-id="71351-190">特定のオペレーティング システムのバージョン、エディション、およびアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="71351-190">Specific operating system versions, editions, and architecture</span></span>  
  
-   <span data-ttu-id="71351-191">特定のオペレーティング システムの機能</span><span class="sxs-lookup"><span data-stu-id="71351-191">Specific operating system features</span></span>  
  
-   <span data-ttu-id="71351-192">各コンピューターにインストールされている特定のソフトウェア</span><span class="sxs-lookup"><span data-stu-id="71351-192">Specific software installed on each computer</span></span>  
  
-   <span data-ttu-id="71351-193">特定のドライバー</span><span class="sxs-lookup"><span data-stu-id="71351-193">Specific drivers</span></span>  
  
-   <span data-ttu-id="71351-194">サービス パックおよびその他の更新プログラム</span><span class="sxs-lookup"><span data-stu-id="71351-194">Service Packs and other updates</span></span>  
  
-   <span data-ttu-id="71351-195">既定値と異なっている場合に使用されるすべてのソフトウェアとオペレーティング システムの機能の構成値</span><span class="sxs-lookup"><span data-stu-id="71351-195">Configuration values for all software and operating system features used if they vary from default values</span></span>  
  
## <a name="building-out-the-environment-for-the-solution"></a><span data-ttu-id="71351-196">ソリューションの環境の構築</span><span class="sxs-lookup"><span data-stu-id="71351-196">Building Out the Environment for the Solution</span></span>  
 <span data-ttu-id="71351-197">インストール手順の詳細な[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]と必要な依存関係のソフトウェアをダウンロードできる BizTalk Server のインストール ガイドで見つかること[BizTalk Server 2010 ドキュメント](http://go.microsoft.com/fwlink/?LinkId=183138)(http://go.microsoft.com/fwlink/ しますか。LinkId = 183138)。</span><span class="sxs-lookup"><span data-stu-id="71351-197">Detailed instructions for installing [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and the required dependency software can be found in the BizTalk Server Installation Guides available for download at [BizTalk Server 2010 Documentation](http://go.microsoft.com/fwlink/?LinkId=183138) (http://go.microsoft.com/fwlink/?LinkId=183138).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71351-198">参照</span><span class="sxs-lookup"><span data-stu-id="71351-198">See Also</span></span>  
 [<span data-ttu-id="71351-199">BizTalk Server 層の計画</span><span class="sxs-lookup"><span data-stu-id="71351-199">Planning the BizTalk Server Tier</span></span>](../technical-guides/planning-the-biztalk-server-tier.md)