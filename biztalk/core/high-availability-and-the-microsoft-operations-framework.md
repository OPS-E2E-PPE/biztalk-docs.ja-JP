---
title: "高可用性と、Microsoft Operations Framework |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- high availability, managing
- service management functions (SMFs)
- service continuity management
- jobs, scheduling
- MOF, high availability
- change management
- MOF, process model
- high availability, MOF
ms.assetid: 54d8bae3-b241-4371-b8fc-a9cbdca6b495
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8ea715e92f7bfaa2f9d3baf3e82223f95328e3da
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="high-availability-and-the-microsoft-operations-framework"></a><span data-ttu-id="de3a9-102">高可用性と MOF</span><span class="sxs-lookup"><span data-stu-id="de3a9-102">High Availability and the Microsoft Operations Framework</span></span>
<span data-ttu-id="de3a9-103">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に対する高可用性ソリューションを計画および実装する際、MOF (Microsoft Operations Framework) プロセス モデルを適用することにより、リリース ライフ サイクルのさまざまな段階で適切なプロセスを得ることができます。</span><span class="sxs-lookup"><span data-stu-id="de3a9-103">Applying the Microsoft Operations Framework (MOF) process model to the planning and implementation of a highly available Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] solution can help you make sure that you have appropriate processes at the different stages of the release life cycle.</span></span> <span data-ttu-id="de3a9-104">高可用性に影響するすべてのライフ サイクル ステージをあらかじめ把握しておくことにより、可用性の問題に伴うインストール、メンテナンス、およびトラブルシューティングを、より円滑に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="de3a9-104">By looking ahead at all the life cycle stages where high availability surfaces, you can make the installation, maintenance, and troubleshooting of availability issues in your environment easier.</span></span>  
  
 <span data-ttu-id="de3a9-105">このセクションでは、高可用性を実現するために必要な MOF プロセスについて考えていきます。</span><span class="sxs-lookup"><span data-stu-id="de3a9-105">This section contains information about the MOF processes where you have to consider high-availability tasks.</span></span>  
  
## <a name="microsoft-operations-framework-process-model"></a><span data-ttu-id="de3a9-106">MOF プロセス モデル</span><span class="sxs-lookup"><span data-stu-id="de3a9-106">Microsoft Operations Framework Process Model</span></span>  
 <span data-ttu-id="de3a9-107">MOF (Microsoft Operations Framework) とは、Microsoft の製品とテクノロジに基づいたミッション クリティカルなシステムの信頼性、可用性、保守性、および管理容易性を実現するための指針です。</span><span class="sxs-lookup"><span data-stu-id="de3a9-107">The Microsoft Operations Framework (MOF) provides guidance that enables organizations to achieve mission-critical system reliability, availability, supportability, and manageability of Microsoft products and technologies.</span></span> <span data-ttu-id="de3a9-108">運用上の指針は、ホワイト ペーパー、運用ガイド、評価ツール、ベスト プラクティス、ケース スタディ、テンプレート、サポート ツール、およびサービスの形態で提供されます。</span><span class="sxs-lookup"><span data-stu-id="de3a9-108">MOF provides operational guidance in the form of white papers, operations guides, assessment tools, best practices, case studies, templates, support tools, and services.</span></span> <span data-ttu-id="de3a9-109">これにより、分散された複雑な異種混合 IT 環境に伴う、要員、プロセス、技術、および管理の問題の解決を図ります。</span><span class="sxs-lookup"><span data-stu-id="de3a9-109">This guidance addresses the people, process, technology, and management issues pertaining to complex, distributed, and heterogeneous IT environments.</span></span> <span data-ttu-id="de3a9-110">Microsoft Operations Framework の詳細については、次を参照してください。 [http://go.microsoft.com/fwlink/?LinkId=31988](http://go.microsoft.com/fwlink/?LinkId=31988)です。</span><span class="sxs-lookup"><span data-stu-id="de3a9-110">For more information about the Microsoft Operations Framework, see [http://go.microsoft.com/fwlink/?LinkId=31988](http://go.microsoft.com/fwlink/?LinkId=31988).</span></span>  
  
 <span data-ttu-id="de3a9-111">企業にとって、MOF プロセス モデルには次のような利点があります。</span><span class="sxs-lookup"><span data-stu-id="de3a9-111">The MOF process model enables companies to:</span></span>  
  
-   <span data-ttu-id="de3a9-112">サービス ソリューション全体にわたり、一貫した IT サービス管理を円滑に行うことができる。</span><span class="sxs-lookup"><span data-stu-id="de3a9-112">Facilitate consistent IT service management across service solutions.</span></span>  
  
-   <span data-ttu-id="de3a9-113">IT の機能、プロセス、および手順を体系的に捉えることができる。</span><span class="sxs-lookup"><span data-stu-id="de3a9-113">Establish a structure for IT functions, processes, and procedures.</span></span>  
  
-   <span data-ttu-id="de3a9-114">ライフサイクル ベースのアプローチが可能になる。</span><span class="sxs-lookup"><span data-stu-id="de3a9-114">Represent a life-cycle approach.</span></span>  
  
 <span data-ttu-id="de3a9-115">MOF プロセス モデルの大きな特徴は、SMF (Service Management Function) と呼ばれる運用プロセスおよび手順を 4 つの領域に分けることです。</span><span class="sxs-lookup"><span data-stu-id="de3a9-115">Central to the MOF process model is its division into four quadrants of operational processes and procedures, named service management functions (SMFs).</span></span> <span data-ttu-id="de3a9-116">SMF は、IT 環境の運用と保守の基礎となるベスト プラクティスと規範的な指針です。</span><span class="sxs-lookup"><span data-stu-id="de3a9-116">The SMFs are the foundation-level best practices and prescriptive guidance for operating and maintaining an IT environment.</span></span>  
  
 <span data-ttu-id="de3a9-117">次の図は、高可用性を実現する上で考慮する必要のある MOF プロセスを示しています。</span><span class="sxs-lookup"><span data-stu-id="de3a9-117">The following figure shows the MOF processes where you have to consider high availability.</span></span>  
  
 <span data-ttu-id="de3a9-118">![MOF プロセス](../core/media/tdi-highava-mof.gif "TDI_HighAva_MOF")</span><span class="sxs-lookup"><span data-stu-id="de3a9-118">![MOF Processes](../core/media/tdi-highava-mof.gif "TDI_HighAva_MOF")</span></span>  
  
## <a name="changing-quadrant"></a><span data-ttu-id="de3a9-119">変更領域</span><span class="sxs-lookup"><span data-stu-id="de3a9-119">Changing Quadrant</span></span>  
 <span data-ttu-id="de3a9-120">変更領域には、管理対象となる IT 環境への変更を見極め、レビューし、さらに、それを承認して実行に移す、というプロセスに必要な SMF (Service Management Function) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="de3a9-120">The changing quadrant includes the service management functions (SMFs) required to identify, review, approve, and incorporate change into a managed IT environment.</span></span> <span data-ttu-id="de3a9-121">ソフトウェア、ハードウェア、ドキュメント、役割/責任の変更のほか、特定のプロセスや手順に対する変更も含まれます。</span><span class="sxs-lookup"><span data-stu-id="de3a9-121">This includes changes in software, hardware, documentation, roles and responsibilities, and also specific process and procedural changes.</span></span>  
  
### <a name="change-management"></a><span data-ttu-id="de3a9-122">変更管理</span><span class="sxs-lookup"><span data-stu-id="de3a9-122">Change Management</span></span>  
 <span data-ttu-id="de3a9-123">変更管理は、テクノロジ、システム、アプリケーション、ハードウェア、ツール、ドキュメント、プロセスなどにおける変更のほか、役割や責任の変更をつかさどるプロセスです。</span><span class="sxs-lookup"><span data-stu-id="de3a9-123">Change management is responsible for changes in technology, systems, applications, hardware, tools, documentation, and processes, and also changes in roles and responsibilities.</span></span>  
  
 <span data-ttu-id="de3a9-124">BizTalk Server 導入計画の一部として、変更管理プロセスでは次のような作業が考えられます。</span><span class="sxs-lookup"><span data-stu-id="de3a9-124">During the change management process, as part of designing your BizTalk Server implementation, you can do the following:</span></span>  
  
-   <span data-ttu-id="de3a9-125">パートナーまたは顧客とのサービス レベル契約に、一定水準の可用性、アップタイム、負荷処理の機能を約束する項目があるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="de3a9-125">Determine whether the service level agreement with your partners or customers requires a certain level of availability, uptime, and load-processing capabilities.</span></span>  
  
-   <span data-ttu-id="de3a9-126">[!INCLUDE[btsBizTalkServer2000](../includes/btsbiztalkserver2000-md.md)] または [!INCLUDE[btsBizTalkServer2002](../includes/btsbiztalkserver2002-md.md)] から [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] にアップグレードする場合は、[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] におけるハードウェアの最小要件だけでなく、サービス レベル契約という観点からも、既存のハードウェアが、十分にその要件を満たしていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="de3a9-126">If you are upgrading from [!INCLUDE[btsBizTalkServer2000](../includes/btsbiztalkserver2000-md.md)] or [!INCLUDE[btsBizTalkServer2002](../includes/btsbiztalkserver2002-md.md)] to [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)], you must determine whether your existing hardware will satisfy the minimum hardware requirements for [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] and the requirements from the service level agreement.</span></span>  
  
-   <span data-ttu-id="de3a9-127">ビジネス ニーズに合わせて、BizTalk Server データベースの最適なクラスター構成を確認します。</span><span class="sxs-lookup"><span data-stu-id="de3a9-127">Determine the best cluster configuration for the BizTalk Server databases for your business needs.</span></span> <span data-ttu-id="de3a9-128">実行時の環境では、BizTalk 管理データベース、メッセージ ボックス データベース、追跡分析サービス データベース、BAM 分析データベース、BAM スター スキーマ データベース、BAM プライマリ インポート データベース、および BAM アーカイブ データベースへの書き込み処理が行われます。</span><span class="sxs-lookup"><span data-stu-id="de3a9-128">The run-time processes write to the BizTalk Management database, MessageBox databases, Tracking Analysis Services database, BAM Analysis database, BAM Star Schema database, BAM Primary Import database, and BAM Archive database.</span></span> <span data-ttu-id="de3a9-129">したがって、これらのデータベースを障害から保護することが特に重要となります。当然、どのデータベースをクラスター化するかという判断において、より高い優先順位が付けられることになります。</span><span class="sxs-lookup"><span data-stu-id="de3a9-129">Therefore, these databases are especially important if a disaster occurs, and must have greater priority when determining what databases to cluster.</span></span> <span data-ttu-id="de3a9-130">その他のデータベースに対する書き込みは、ユーザーまたはツールによってのみ行われます。</span><span class="sxs-lookup"><span data-stu-id="de3a9-130">Only users or tools write to the other databases.</span></span> <span data-ttu-id="de3a9-131">メッセージ ボックス データベースについては、4 つのサーバー クラスターから成るアクティブ/アクティブ/アクティブ/パッシブ構成によって、必要なハードウェアを最小限に抑えることができます。</span><span class="sxs-lookup"><span data-stu-id="de3a9-131">For the MessageBox databases, you can consider an active/active/active/passive four-server cluster to minimize the hardware needed.</span></span>  
  
-   <span data-ttu-id="de3a9-132">マスター シークレット サーバーをクラスター化すべきかどうかを決めます。あるいは、マスター シークレットを別のエンタープライズ シングル サインオン サーバーに手動で復元するだけで十分かもしれません。</span><span class="sxs-lookup"><span data-stu-id="de3a9-132">Determine whether to cluster the master secret server, or if manually restoring the master secret on another Enterprise Single Sign-On server is satisfactory for your scenario.</span></span> <span data-ttu-id="de3a9-133">ただしこのソリューションで提供できるのは可用性であり、高可用性ではありません。</span><span class="sxs-lookup"><span data-stu-id="de3a9-133">This solution is available, but not highly available.</span></span>  
  
-   <span data-ttu-id="de3a9-134">推定されるメッセージ量を適切に処理し、高可用性の要件を満たすために必要なホスト数およびホスト インスタンス数を確認します。</span><span class="sxs-lookup"><span data-stu-id="de3a9-134">Determine the number of hosts and host instances that you will need to process your expected message load and to provide high availability.</span></span>  
  
-   <span data-ttu-id="de3a9-135">変更管理プロセスにかかわる要員のリストを作成します。</span><span class="sxs-lookup"><span data-stu-id="de3a9-135">Create a list of the people that will be involved in the change-management process.</span></span> <span data-ttu-id="de3a9-136">このリストには、ドメイン管理者、データベース管理者、インフラストラクチャ管理者、BizTalk Server 管理者、IT 運用スタッフなどが含まれます。</span><span class="sxs-lookup"><span data-stu-id="de3a9-136">This list will include, but is not limited to, the domain administrator, database administrator, infrastructure administrator, BizTalk Server administrator, and IT operations staff.</span></span>  
  
### <a name="configuration-management"></a><span data-ttu-id="de3a9-137">構成管理</span><span class="sxs-lookup"><span data-stu-id="de3a9-137">Configuration Management</span></span>  
 <span data-ttu-id="de3a9-138">構成管理は、ソフトウェア、ハードウェア、ドキュメント、プロセス、手順など、変更管理プロセス下にある IT 環境のあらゆる構成要素のバージョンをすべて識別、管理、追跡するプロセスです。</span><span class="sxs-lookup"><span data-stu-id="de3a9-138">Configuration management is responsible for identifying, controlling, and tracking all versions of software, hardware, documentation, processes, procedures, and all other components of the IT environment under the control of change management.</span></span>  
  
 <span data-ttu-id="de3a9-139">構成管理プロセスでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の高可用性ソリューションを具体的にどのように実現するかという詳細な計画を立てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="de3a9-139">During the configuration management process, you must create a detailed plan for how you are going to implement your highly available solution for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="de3a9-140">ソリューションの作成に要した手順を記録しておくことも必要です。</span><span class="sxs-lookup"><span data-stu-id="de3a9-140">You must also document the steps that you took to create your solution.</span></span> <span data-ttu-id="de3a9-141">大まかな手順としては、次のようなことが含まれます。</span><span class="sxs-lookup"><span data-stu-id="de3a9-141">At a high level, the steps are:</span></span>  
  
-   <span data-ttu-id="de3a9-142">ドメイン コントローラーで、BizTalk Server 環境で使用するドメイン グループおよびアカウントを作成する。</span><span class="sxs-lookup"><span data-stu-id="de3a9-142">The domain controller creates the domain groups and accounts that you will use in your BizTalk Server environment.</span></span>  
  
-   <span data-ttu-id="de3a9-143">インフラストラクチャ管理者が、BizTalk Server データベース用およびマスター シークレット サーバー用の Windows クラスターを作成する。</span><span class="sxs-lookup"><span data-stu-id="de3a9-143">The infrastructure administrator creates the Windows cluster for the BizTalk Server databases and the Windows cluster for the master secret server.</span></span>  
  
-   <span data-ttu-id="de3a9-144">データベース管理者が、BizTalk Server データベース用 Windows クラスターに、Microsoft SQL Server をインストールおよび構成する。</span><span class="sxs-lookup"><span data-stu-id="de3a9-144">The database administrator installs and configures Microsoft SQL Server on the Windows cluster for the BizTalk Server databases.</span></span>  
  
-   <span data-ttu-id="de3a9-145">BizTalk Server 管理者が、マスター シークレット サーバー クラスターを構成する。</span><span class="sxs-lookup"><span data-stu-id="de3a9-145">The BizTalk Server administrator configures the master secret server cluster.</span></span>  
  
-   <span data-ttu-id="de3a9-146">BizTalk Server 管理者が、処理サーバー、受信サーバー、および送信サーバーに [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] をインストールおよび構成する。</span><span class="sxs-lookup"><span data-stu-id="de3a9-146">The BizTalk Server administrator installs and configures [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] on the processing, receiving, and sending servers.</span></span>  
  
-   <span data-ttu-id="de3a9-147">BizTalk Server 管理者が、適切なサーバー上にホストを作成し、ホスト インスタンスをインストールすることによって可用性や処理能力の向上を図る。</span><span class="sxs-lookup"><span data-stu-id="de3a9-147">The BizTalk Server administrator creates the hosts and installs the host instances on the appropriate servers to provide high availability or to increase capacity, or both.</span></span>  
  
## <a name="operating-quadrant"></a><span data-ttu-id="de3a9-148">運用領域</span><span class="sxs-lookup"><span data-stu-id="de3a9-148">Operating Quadrant</span></span>  
 <span data-ttu-id="de3a9-149">運用領域には、サービス ソリューションを毎日監視および管理するために必要な SMF が含まれています。これにより、定義済みパラメーター内のサービス レベルを確保、維持します。</span><span class="sxs-lookup"><span data-stu-id="de3a9-149">The operating quadrant includes the SMFs required to monitor, control, manage, and administer service solutions daily to achieve and maintain service levels within predetermined parameters.</span></span>  
  
### <a name="job-scheduling"></a><span data-ttu-id="de3a9-150">ジョブ スケジューリング</span><span class="sxs-lookup"><span data-stu-id="de3a9-150">Job Scheduling</span></span>  
 <span data-ttu-id="de3a9-151">ジョブ スケジューリングには、システムのスループットを最大限に引き出し、サービス レベル契約の要件を満たしながら、ジョブとプロセスの最も効率のよい流れを体系化する作業が含まれます。</span><span class="sxs-lookup"><span data-stu-id="de3a9-151">Job scheduling involves the continuous organization of jobs and processes in the most efficient sequence, maximizing system throughput and use to meet service level agreement requirements.</span></span>  
  
 <span data-ttu-id="de3a9-152">更新プログラムなどのメンテナンス ダウンタイムをスケジューリングする場合は、業務への影響をできるだけ小さくするために、メッセージ処理の負荷が低い時間帯を選ぶようにしてください (夜中など)。</span><span class="sxs-lookup"><span data-stu-id="de3a9-152">Make sure that you schedule planned downtime, such as scheduled updates, at times when the message load is low (for example, late at night) to minimize the potential effect on your business.</span></span>  
  
## <a name="supporting-quadrant"></a><span data-ttu-id="de3a9-153">サポート領域</span><span class="sxs-lookup"><span data-stu-id="de3a9-153">Supporting Quadrant</span></span>  
 <span data-ttu-id="de3a9-154">サポート領域には、インシデントや問題、リクエストなどを、サービス レベル契約の要件を満たす範囲内で処理 (識別、割り当て、診断、追跡、解決) するために必要な SMF が含まれます。</span><span class="sxs-lookup"><span data-stu-id="de3a9-154">The supporting quadrant includes the SMFs required to identify, assign, diagnose, track, and resolve incidents, problems, and requests within the approved requirements that are contained in the service level agreements.</span></span>  
  
## <a name="optimizing-quadrant"></a><span data-ttu-id="de3a9-155">最適化領域</span><span class="sxs-lookup"><span data-stu-id="de3a9-155">Optimizing Quadrant</span></span>  
 <span data-ttu-id="de3a9-156">最適化領域には、サービス レベルを維持または向上させながら IT コストを削減することによって、企業や IT 部門の運営に貢献する SMF が含まれます。</span><span class="sxs-lookup"><span data-stu-id="de3a9-156">The optimizing quadrant includes the SMFs that contribute to maintaining business and IT alignment by focusing on decreasing IT costs while maintaining or improving service levels.</span></span> <span data-ttu-id="de3a9-157">たとえば、障害やインシデントの再検証、コスト体系やスタッフ割り当ての見直し、可用性やパフォーマンスの分析、処理能力予測などがあります。</span><span class="sxs-lookup"><span data-stu-id="de3a9-157">This includes review of outages and incidents, examination of cost structures, staff assessments, availability and performance analysis, and capacity forecasting.</span></span>  
  
### <a name="service-level-management"></a><span data-ttu-id="de3a9-158">サービス レベル管理</span><span class="sxs-lookup"><span data-stu-id="de3a9-158">Service Level Management</span></span>  
 <span data-ttu-id="de3a9-159">サービス レベル管理の目的は、サービス レベルの要件を絶えず調整および監視しながら、IT サービスの品質を維持し、持続的に向上させることです。</span><span class="sxs-lookup"><span data-stu-id="de3a9-159">The goal of service level management is to maintain and continuously improve the quality of IT service, through a constant cycle of negotiating and monitoring service level requirements.</span></span> <span data-ttu-id="de3a9-160">サービス レベル管理がうまく機能すれば、サービス品質の改善や、顧客の生産性向上といった効果が期待できます。サービスにかかる総コストまで削減できれば理想的です。</span><span class="sxs-lookup"><span data-stu-id="de3a9-160">The successful service level management function causes an improvement in quality of service, greater levels of customer productivity, and ideally, a reduction in the overall cost of services provided.</span></span>  
  
 <span data-ttu-id="de3a9-161">サービス レベル管理プロセスには、次のような作業が含まれます。</span><span class="sxs-lookup"><span data-stu-id="de3a9-161">During the service level management process, you can do the following:</span></span>  
  
-   <span data-ttu-id="de3a9-162">現在の環境がサービス レベル契約の要件を満たしているかを実際的な観点から評価します。</span><span class="sxs-lookup"><span data-stu-id="de3a9-162">Evaluate how the current environment satisfies your service level agreement requirements.</span></span>  
  
-   <span data-ttu-id="de3a9-163">要件を満たすためにメッセージの処理、受信、または送信用の新しいサーバーを追加する必要があれば、それを提案します。</span><span class="sxs-lookup"><span data-stu-id="de3a9-163">Recommend the addition of new servers for processing, receiving, or sending messages to meet the requirements.</span></span>  
  
-   <span data-ttu-id="de3a9-164">サービス レベル契約の可用性要件を満たすだけの耐性のない、障害の発生しやすい箇所に対し、必要に応じて高可用性ソリューションの適用を提案します。</span><span class="sxs-lookup"><span data-stu-id="de3a9-164">If necessary, recommend creating highly available solutions for points of failure that were not originally mitigated to meet the availability requirements in the service level agreement.</span></span>  
  
### <a name="availability-management"></a><span data-ttu-id="de3a9-165">可用性管理</span><span class="sxs-lookup"><span data-stu-id="de3a9-165">Availability Management</span></span>  
 <span data-ttu-id="de3a9-166">可用性管理の目的は、顧客が特定の IT サービスを、必要なときにいつでも利用できるようにするという一点につきます。</span><span class="sxs-lookup"><span data-stu-id="de3a9-166">The single goal of availability management is to make sure that your customers can use a particular IT service whenever they want.</span></span>  
  
 <span data-ttu-id="de3a9-167">可用性管理プロセスでは、たとえば、サーバーの負荷が特定のしきい値を上回った場合や、ハードウェア障害が発生し、早急に修理または交換が必要となった場合に、そのことを速やかに IT 担当者に通知するためのメカニズムを構築することなどが考えられます。</span><span class="sxs-lookup"><span data-stu-id="de3a9-167">For the availability management process, you can establish mechanisms for notifying IT personnel when a hardware failure occurs so that they can fix or replace the hardware as quickly as possible, and mechanisms for notifying IT personnel when the server load is larger than a particular threshold.</span></span>  
  
### <a name="service-continuity-management"></a><span data-ttu-id="de3a9-168">サービス継続性管理</span><span class="sxs-lookup"><span data-stu-id="de3a9-168">Service Continuity Management</span></span>  
 <span data-ttu-id="de3a9-169">サービス継続性管理機能の目的は、標準の可用性ソリューションでは対応できないような問題が発生したとしても、特定の IT サービスが顧客に価値を提供できるようにすることです。</span><span class="sxs-lookup"><span data-stu-id="de3a9-169">The objective of the service continuity management function is to make sure that a specified IT service provides value to the customer if regular-availability solutions fail.</span></span>  
  
 <span data-ttu-id="de3a9-170">サービス継続性機能の中に、お客様にも計画または計画外のダウンタイムが発生すると、期待されるサービスを提供し続けることを確認するために実装するには、どのような高可用性構成を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="de3a9-170">During the service continuity function you must examine what high-availability configuration to implement to make sure that you continue providing your customers with the services they expect even when a planned or unplanned downtime occurs.</span></span> <span data-ttu-id="de3a9-171">計画外のダウンタイムには、ハードウェア障害や自然災害などがあります。</span><span class="sxs-lookup"><span data-stu-id="de3a9-171">Examples of unplanned downtime are hardware failures or acts of nature.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de3a9-172">参照</span><span class="sxs-lookup"><span data-stu-id="de3a9-172">See Also</span></span>  
 [<span data-ttu-id="de3a9-173">サンプル BizTalk Server の高可用性のシナリオ</span><span class="sxs-lookup"><span data-stu-id="de3a9-173">Sample BizTalk Server High Availability Scenarios</span></span>](../core/sample-biztalk-server-high-availability-scenarios.md)