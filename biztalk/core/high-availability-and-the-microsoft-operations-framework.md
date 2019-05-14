---
title: 高可用性と Microsoft Operations Framework |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 54d8bae3-b241-4371-b8fc-a9cbdca6b495
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ba63d822a6edf76cd9673a4c1cdffcddf3697055
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65344323"
---
# <a name="high-availability-and-the-microsoft-operations-framework"></a><span data-ttu-id="53162-102">高可用性と Microsoft Operations Framework</span><span class="sxs-lookup"><span data-stu-id="53162-102">High Availability and the Microsoft Operations Framework</span></span>
<span data-ttu-id="53162-103">計画と Microsoft BizTalk Server の高可用性ソリューションの実装に、Microsoft Operations Framework (MOF) プロセス モデルを適用すると、適切なプロセスが、リリース ライフ サイクルのさまざまな段階であることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="53162-103">Applying the Microsoft Operations Framework (MOF) process model to the planning and implementation of a highly available Microsoft BizTalk Server solution can help you make sure that you have appropriate processes at the different stages of the release life cycle.</span></span> <span data-ttu-id="53162-104">すべてのライフ サイクルの段階で今後の見通しで高可用性に影響を行うことができます、インストール、メンテナンス、場所と簡単に環境で可用性の問題のトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="53162-104">By looking ahead at all the life cycle stages where high availability surfaces, you can make the installation, maintenance, and troubleshooting of availability issues in your environment easier.</span></span>  
  
 <span data-ttu-id="53162-105">このセクションには、高可用性のタスクを検討してください。 ある MOF プロセスに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="53162-105">This section contains information about the MOF processes where you have to consider high-availability tasks.</span></span>  
  
## <a name="microsoft-operations-framework-process-model"></a><span data-ttu-id="53162-106">Microsoft Operations Framework のプロセス モデル</span><span class="sxs-lookup"><span data-stu-id="53162-106">Microsoft Operations Framework Process Model</span></span>  
 <span data-ttu-id="53162-107">[Microsoft Operations Framework (MOF)](https://technet.microsoft.com/solutionaccelerators/dd320379.aspx)により、ミッション クリティカルなシステムの信頼性、可用性、保守性、および Microsoft 製品とテクノロジの管理の容易性を実現するために組織のガイダンスを提供します.</span><span class="sxs-lookup"><span data-stu-id="53162-107">The [Microsoft Operations Framework (MOF)](https://technet.microsoft.com/solutionaccelerators/dd320379.aspx) provides guidance that enables organizations to achieve mission-critical system reliability, availability, supportability, and manageability of Microsoft products and technologies.</span></span> <span data-ttu-id="53162-108">MOF は、ホワイト ペーパー、運用ガイド、アセスメント ツール、ベスト プラクティス、テンプレート、サポート ツール、およびサービスの形式での運用のガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="53162-108">MOF provides operational guidance in the form of white papers, operations guides, assessment tools, best practices, case studies, templates, support tools, and services.</span></span> <span data-ttu-id="53162-109">このガイダンスは、複雑な分散、および異種 IT 環境に関連する人、プロセス、テクノロジ、および管理の問題に対処します。</span><span class="sxs-lookup"><span data-stu-id="53162-109">This guidance addresses the people, process, technology, and management issues pertaining to complex, distributed, and heterogeneous IT environments.</span></span> 
  
 <span data-ttu-id="53162-110">MOF プロセス モデルにより、企業にできます。</span><span class="sxs-lookup"><span data-stu-id="53162-110">The MOF process model enables companies to:</span></span>  
  
- <span data-ttu-id="53162-111">サービス ソリューション全体で一貫性のある IT サービス管理を容易になります。</span><span class="sxs-lookup"><span data-stu-id="53162-111">Facilitate consistent IT service management across service solutions.</span></span>  
  
- <span data-ttu-id="53162-112">IT 関数、プロセス、およびプロシージャの構造体を確立します。</span><span class="sxs-lookup"><span data-stu-id="53162-112">Establish a structure for IT functions, processes, and procedures.</span></span>  
  
- <span data-ttu-id="53162-113">ライフ サイクル アプローチを表します。</span><span class="sxs-lookup"><span data-stu-id="53162-113">Represent a life-cycle approach.</span></span>  
  
  <span data-ttu-id="53162-114">MOF プロセス モデルの中心となるには運用プロセスおよび手順は、サービス管理機能 (Smf) という名前の 4 つの象限にその除算をします。</span><span class="sxs-lookup"><span data-stu-id="53162-114">Central to the MOF process model is its division into four quadrants of operational processes and procedures, named service management functions (SMFs).</span></span> <span data-ttu-id="53162-115">Smf は、基礎レベルのベスト プラクティスと運用と、IT 環境を維持するための規範ガイダンスを示します。</span><span class="sxs-lookup"><span data-stu-id="53162-115">The SMFs are the foundation-level best practices and prescriptive guidance for operating and maintaining an IT environment.</span></span>  
  
  <span data-ttu-id="53162-116">次の図は、高可用性を考慮すべきある MOF プロセスを示します。</span><span class="sxs-lookup"><span data-stu-id="53162-116">The following figure shows the MOF processes where you have to consider high availability.</span></span>  
  
  <span data-ttu-id="53162-117">![MOF プロセス](../core/media/tdi-highava-mof.gif "TDI_HighAva_MOF")</span><span class="sxs-lookup"><span data-stu-id="53162-117">![MOF Processes](../core/media/tdi-highava-mof.gif "TDI_HighAva_MOF")</span></span>  
  
## <a name="changing-quadrant"></a><span data-ttu-id="53162-118">変更領域</span><span class="sxs-lookup"><span data-stu-id="53162-118">Changing Quadrant</span></span>  
 <span data-ttu-id="53162-119">変更の作業領域には、特定、確認、承認、および管理された IT 環境に変更を組み込むに必要なサービス管理機能 (Smf) が含まれています。</span><span class="sxs-lookup"><span data-stu-id="53162-119">The changing quadrant includes the service management functions (SMFs) required to identify, review, approve, and incorporate change into a managed IT environment.</span></span> <span data-ttu-id="53162-120">これには、ソフトウェア、ハードウェア、ドキュメント、役割と責任、およびも特定のプロセスと手順の変更の変更が含まれます。</span><span class="sxs-lookup"><span data-stu-id="53162-120">This includes changes in software, hardware, documentation, roles and responsibilities, and also specific process and procedural changes.</span></span>  
  
### <a name="change-management"></a><span data-ttu-id="53162-121">変更管理</span><span class="sxs-lookup"><span data-stu-id="53162-121">Change Management</span></span>  
 <span data-ttu-id="53162-122">変更管理では、テクノロジ、システム、アプリケーション、ハードウェア、ツール、ドキュメント、およびプロセスの変更を担当し、役割と責任も変更します。</span><span class="sxs-lookup"><span data-stu-id="53162-122">Change management is responsible for changes in technology, systems, applications, hardware, tools, documentation, and processes, and also changes in roles and responsibilities.</span></span>  
  
 <span data-ttu-id="53162-123">BizTalk Server の実装の設計の一部として、変更管理プロセス中には、次の操作を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="53162-123">During the change management process, as part of designing your BizTalk Server implementation, you can do the following:</span></span>  
  
-   <span data-ttu-id="53162-124">サービス レベル アグリーメント、パートナーや顧客に、一定レベルの可用性、アップタイム、および負荷処理の機能が必要かどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="53162-124">Determine whether the service level agreement with your partners or customers requires a certain level of availability, uptime, and load-processing capabilities.</span></span>  
  
-   <span data-ttu-id="53162-125">ビジネス ニーズに合わせて、BizTalk Server データベースの最適なクラスター構成を確認します。</span><span class="sxs-lookup"><span data-stu-id="53162-125">Determine the best cluster configuration for the BizTalk Server databases for your business needs.</span></span> <span data-ttu-id="53162-126">実行時の環境では、BizTalk 管理データベース、メッセージ ボックス データベース、追跡分析サービス データベース、BAM 分析データベース、BAM スター スキーマ データベース、BAM プライマリ インポート データベース、および BAM アーカイブ データベースへの書き込み処理が行われます。</span><span class="sxs-lookup"><span data-stu-id="53162-126">The run-time processes write to the BizTalk Management database, MessageBox databases, Tracking Analysis Services database, BAM Analysis database, BAM Star Schema database, BAM Primary Import database, and BAM Archive database.</span></span> <span data-ttu-id="53162-127">したがって、これらのデータベースを障害から保護することが特に重要となります。当然、どのデータベースをクラスター化するかという判断において、より高い優先順位が付けられることになります。</span><span class="sxs-lookup"><span data-stu-id="53162-127">Therefore, these databases are especially important if a disaster occurs, and must have greater priority when determining what databases to cluster.</span></span> <span data-ttu-id="53162-128">その他のデータベースに対する書き込みは、ユーザーまたはツールによってのみ行われます。</span><span class="sxs-lookup"><span data-stu-id="53162-128">Only users or tools write to the other databases.</span></span> <span data-ttu-id="53162-129">メッセージ ボックス データベースの場合、アクティブ/アクティブ/アクティブ/パッシブ 4 台のサーバーのクラスターを最小限に抑えるために必要なハードウェアを検討できます。</span><span class="sxs-lookup"><span data-stu-id="53162-129">For the MessageBox databases, you can consider an active/active/active/passive four-server cluster to minimize the hardware needed.</span></span>  
  
-   <span data-ttu-id="53162-130">または別のエンタープライズ シングル サインオン サーバー上にマスター シークレットを手動で復元するかどうかは、シナリオにとってはマスター シークレット サーバーをクラスター化するかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="53162-130">Determine whether to cluster the master secret server, or if manually restoring the master secret on another Enterprise Single Sign-On server is satisfactory for your scenario.</span></span> <span data-ttu-id="53162-131">このソリューションは、高可用性ではありません。</span><span class="sxs-lookup"><span data-stu-id="53162-131">This solution is available, but not highly available.</span></span>  
  
-   <span data-ttu-id="53162-132">ホストと、予期されるメッセージ負荷を処理して、高可用性を実現に必要なホスト インスタンスの数を決定します。</span><span class="sxs-lookup"><span data-stu-id="53162-132">Determine the number of hosts and host instances that you will need to process your expected message load and to provide high availability.</span></span>  
  
-   <span data-ttu-id="53162-133">変更管理プロセスにかかわる人々 のリストを作成します。</span><span class="sxs-lookup"><span data-stu-id="53162-133">Create a list of the people that will be involved in the change-management process.</span></span> <span data-ttu-id="53162-134">この一覧が含まれますが、ドメイン管理者、データベース管理者、インフラストラクチャ管理者、BizTalk Server 管理者、および IT 運用スタッフに制限はありません。</span><span class="sxs-lookup"><span data-stu-id="53162-134">This list will include, but is not limited to, the domain administrator, database administrator, infrastructure administrator, BizTalk Server administrator, and IT operations staff.</span></span>  
  
### <a name="configuration-management"></a><span data-ttu-id="53162-135">構成管理</span><span class="sxs-lookup"><span data-stu-id="53162-135">Configuration Management</span></span>  
 <span data-ttu-id="53162-136">構成管理を識別する、制御、およびソフトウェア、ハードウェア、ドキュメント、プロセス、手順、および変更管理の制御下で、IT 環境の他のすべてのコンポーネントのすべてのバージョンを追跡する責任を負います。</span><span class="sxs-lookup"><span data-stu-id="53162-136">Configuration management is responsible for identifying, controlling, and tracking all versions of software, hardware, documentation, processes, procedures, and all other components of the IT environment under the control of change management.</span></span>  
  
 <span data-ttu-id="53162-137">構成管理プロセスでは、詳細な計画をどのように BizTalk Server の高可用性ソリューションを実装しようとを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="53162-137">During the configuration management process, you must create a detailed plan for how you are going to implement your highly available solution for BizTalk Server.</span></span> <span data-ttu-id="53162-138">ソリューションを作成する際に、手順を文書化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="53162-138">You must also document the steps that you took to create your solution.</span></span> <span data-ttu-id="53162-139">高レベルでの手順は。</span><span class="sxs-lookup"><span data-stu-id="53162-139">At a high level, the steps are:</span></span>  
  
-   <span data-ttu-id="53162-140">ドメイン コント ローラーは、ドメイン グループと BizTalk Server 環境で使用するアカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="53162-140">The domain controller creates the domain groups and accounts that you will use in your BizTalk Server environment.</span></span>  
  
-   <span data-ttu-id="53162-141">インフラストラクチャ管理者は、BizTalk Server データベース用の Windows クラスターと、マスター シークレット サーバーの Windows クラスターを作成します。</span><span class="sxs-lookup"><span data-stu-id="53162-141">The infrastructure administrator creates the Windows cluster for the BizTalk Server databases and the Windows cluster for the master secret server.</span></span>  
  
-   <span data-ttu-id="53162-142">データベース管理者は、インストールして、BizTalk Server データベース用の Windows クラスターで Microsoft SQL Server を構成します。</span><span class="sxs-lookup"><span data-stu-id="53162-142">The database administrator installs and configures Microsoft SQL Server on the Windows cluster for the BizTalk Server databases.</span></span>  
  
-   <span data-ttu-id="53162-143">BizTalk Server 管理者は、マスター シークレット サーバー クラスターを構成します。</span><span class="sxs-lookup"><span data-stu-id="53162-143">The BizTalk Server administrator configures the master secret server cluster.</span></span>  
  
-   <span data-ttu-id="53162-144">BizTalk Server 管理者は、インストールし、受信、および送信サーバーで行う処理は、BizTalk Server を構成します。</span><span class="sxs-lookup"><span data-stu-id="53162-144">The BizTalk Server administrator installs and configures BizTalk Server on the processing, receiving, and sending servers.</span></span>  
  
-   <span data-ttu-id="53162-145">BizTalk Server 管理者は、ホストを作成し、高可用性を提供する、または容量、またはその両方を増やすには、適切なサーバーにホスト インスタンスをインストールします。</span><span class="sxs-lookup"><span data-stu-id="53162-145">The BizTalk Server administrator creates the hosts and installs the host instances on the appropriate servers to provide high availability or to increase capacity, or both.</span></span>  
  
## <a name="operating-quadrant"></a><span data-ttu-id="53162-146">運用領域</span><span class="sxs-lookup"><span data-stu-id="53162-146">Operating Quadrant</span></span>  
 <span data-ttu-id="53162-147">運用作業領域には、監視、制御、管理、およびサービス ソリューションを毎日の管理を実現し、定義済みパラメーター内のサービス レベルを維持するために必要な Smf が含まれています。</span><span class="sxs-lookup"><span data-stu-id="53162-147">The operating quadrant includes the SMFs required to monitor, control, manage, and administer service solutions daily to achieve and maintain service levels within predetermined parameters.</span></span>  
  
### <a name="job-scheduling"></a><span data-ttu-id="53162-148">ジョブのスケジュール設定</span><span class="sxs-lookup"><span data-stu-id="53162-148">Job Scheduling</span></span>  
 <span data-ttu-id="53162-149">ジョブのスケジュール設定は、ジョブの継続的な組織は、し、サービス レベル契約の要件を満たすために使用してシステムのスループットを最大化に最も効率的な順序で処理します。</span><span class="sxs-lookup"><span data-stu-id="53162-149">Job scheduling involves the continuous organization of jobs and processes in the most efficient sequence, maximizing system throughput and use to meet service level agreement requirements.</span></span>  
  
 <span data-ttu-id="53162-150">メッセージの負荷が低いときに (たとえば、夜)、ビジネスの潜在的な影響を最小限にするタイミングで、スケジュールされた更新プログラムなど、計画されたダウンタイムをスケジュールすることを確認します。</span><span class="sxs-lookup"><span data-stu-id="53162-150">Make sure that you schedule planned downtime, such as scheduled updates, at times when the message load is low (for example, late at night) to minimize the potential effect on your business.</span></span>  
  
## <a name="supporting-quadrant"></a><span data-ttu-id="53162-151">サポート領域</span><span class="sxs-lookup"><span data-stu-id="53162-151">Supporting Quadrant</span></span>  
 <span data-ttu-id="53162-152">サポートの作業領域には、識別、割り当て、診断、追跡、およびインシデント、問題、およびサービス レベル契約に含まれている承認済みの要件内の要求を解決するために必要な Smf が含まれています。</span><span class="sxs-lookup"><span data-stu-id="53162-152">The supporting quadrant includes the SMFs required to identify, assign, diagnose, track, and resolve incidents, problems, and requests within the approved requirements that are contained in the service level agreements.</span></span>  
  
## <a name="optimizing-quadrant"></a><span data-ttu-id="53162-153">最適化領域</span><span class="sxs-lookup"><span data-stu-id="53162-153">Optimizing Quadrant</span></span>  
 <span data-ttu-id="53162-154">最適化の作業領域には、IT コストを維持またはサービス レベルを向上することによってビジネスと IT の配置を維持するために貢献する Smf が含まれています。</span><span class="sxs-lookup"><span data-stu-id="53162-154">The optimizing quadrant includes the SMFs that contribute to maintaining business and IT alignment by focusing on decreasing IT costs while maintaining or improving service levels.</span></span> <span data-ttu-id="53162-155">これには、障害やインシデントの確認、コスト構造、スタッフ、可用性とパフォーマンスの分析、および容量の予測の調査が含まれます。</span><span class="sxs-lookup"><span data-stu-id="53162-155">This includes review of outages and incidents, examination of cost structures, staff assessments, availability and performance analysis, and capacity forecasting.</span></span>  
  
### <a name="service-level-management"></a><span data-ttu-id="53162-156">サービス レベル管理</span><span class="sxs-lookup"><span data-stu-id="53162-156">Service Level Management</span></span>  
 <span data-ttu-id="53162-157">サービス レベル管理の目的を維持し、ながら絶えず調整およびサービス レベルの要件を監視、IT サービスの品質を継続的な改善です。</span><span class="sxs-lookup"><span data-stu-id="53162-157">The goal of service level management is to maintain and continuously improve the quality of IT service, through a constant cycle of negotiating and monitoring service level requirements.</span></span> <span data-ttu-id="53162-158">成功したサービス レベル管理の機能では、サービス、ユーザーの生産性の高いレベルおよび理想的には、提供されるサービスの全体的なコストの削減の品質で、改善が発生します。</span><span class="sxs-lookup"><span data-stu-id="53162-158">The successful service level management function causes an improvement in quality of service, greater levels of customer productivity, and ideally, a reduction in the overall cost of services provided.</span></span>  
  
 <span data-ttu-id="53162-159">サービス レベル管理プロセス中には、次の操作を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="53162-159">During the service level management process, you can do the following:</span></span>  
  
-   <span data-ttu-id="53162-160">現在の環境が、サービス レベル契約の要件を満たす方法を評価します。</span><span class="sxs-lookup"><span data-stu-id="53162-160">Evaluate how the current environment satisfies your service level agreement requirements.</span></span>  
  
-   <span data-ttu-id="53162-161">処理、受信、または要件を満たすメッセージを送信するための新しいサーバーの追加をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="53162-161">Recommend the addition of new servers for processing, receiving, or sending messages to meet the requirements.</span></span>  
  
-   <span data-ttu-id="53162-162">必要に応じて、サービス レベル アグリーメントで可用性の要件を満たすためにもともと軽減されたしない障害点の高可用性ソリューションの作成をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="53162-162">If necessary, recommend creating highly available solutions for points of failure that were not originally mitigated to meet the availability requirements in the service level agreement.</span></span>  
  
### <a name="availability-management"></a><span data-ttu-id="53162-163">可用性管理</span><span class="sxs-lookup"><span data-stu-id="53162-163">Availability Management</span></span>  
 <span data-ttu-id="53162-164">可用性管理の 1 つの目的では、するたびに、お客様に特定の IT サービスを使用できるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="53162-164">The single goal of availability management is to make sure that your customers can use a particular IT service whenever they want.</span></span>  
  
 <span data-ttu-id="53162-165">可用性管理プロセスでは、修正したり、できるだけ早くハードウェアを交換するためにハードウェア障害が発生したときに、IT 担当者を通知するためのメカニズムとサーバーの負荷が IT 担当者に通知するためのメカニズムを確立することができます。特定のしきい値より大きい。</span><span class="sxs-lookup"><span data-stu-id="53162-165">For the availability management process, you can establish mechanisms for notifying IT personnel when a hardware failure occurs so that they can fix or replace the hardware as quickly as possible, and mechanisms for notifying IT personnel when the server load is larger than a particular threshold.</span></span>  
  
### <a name="service-continuity-management"></a><span data-ttu-id="53162-166">サービス継続性管理</span><span class="sxs-lookup"><span data-stu-id="53162-166">Service Continuity Management</span></span>  
 <span data-ttu-id="53162-167">サービス継続性の管理機能では、通常可用性ソリューションが失敗した場合、指定した IT サービスが顧客に値を提供ことを確認します。</span><span class="sxs-lookup"><span data-stu-id="53162-167">The objective of the service continuity management function is to make sure that a specified IT service provides value to the customer if regular-availability solutions fail.</span></span>  
  
 <span data-ttu-id="53162-168">サービスの継続性機能の中にも計画または計画外のダウンタイムが発生すると、期待されるサービスを顧客に提供を続行することを確認するために実装するには、どのような高可用性構成を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="53162-168">During the service continuity function you must examine what high-availability configuration to implement to make sure that you continue providing your customers with the services they expect even when a planned or unplanned downtime occurs.</span></span> <span data-ttu-id="53162-169">計画外のダウンタイムには、ハードウェア障害や自然な性質があります。</span><span class="sxs-lookup"><span data-stu-id="53162-169">Examples of unplanned downtime are hardware failures or acts of nature.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53162-170">参照</span><span class="sxs-lookup"><span data-stu-id="53162-170">See Also</span></span>  
 [<span data-ttu-id="53162-171">BizTalk Server の高可用性を実現するサンプル シナリオ</span><span class="sxs-lookup"><span data-stu-id="53162-171">Sample BizTalk Server High Availability Scenarios</span></span>](../core/sample-biztalk-server-high-availability-scenarios.md)