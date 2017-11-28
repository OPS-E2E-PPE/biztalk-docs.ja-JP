---
title: "ビジネス プロセス管理ソリューションを理解する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- process management solutions, resources
- process management solutions, applications
- process management solution tutorial, background information
- process management solutions, about process management solutions
- applications, process management solutions
ms.assetid: fa6ad8d2-08d7-4770-9394-835f99bfd146
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9759f6521297377b204f0695a511de40d22a830d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="understanding-the-business-process-management-solution"></a><span data-ttu-id="c6120-102">ビジネス プロセス管理ソリューションについて</span><span class="sxs-lookup"><span data-stu-id="c6120-102">Understanding the Business Process Management Solution</span></span>
<span data-ttu-id="c6120-103">このセクションで説明するソリューションは、ビジネス プロセス管理アプリケーションを実装する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="c6120-103">The solution described in this section presents one way to implement a business process management application.</span></span> <span data-ttu-id="c6120-104">理想的なビジネス プロセス マネージャでは、ソリューションの各部分が、ビジネス ルール、特定のバックエンド システムとの通信、応答メッセージの送信などのビジネス プロセスを表し、プロセスを支えるインフラストラクチャと分離されています。</span><span class="sxs-lookup"><span data-stu-id="c6120-104">In an ideal business process manager, the parts of the solution representing the business process—the business rules, communicating with specific backend systems, sending response messages—are separate from the infrastructure supporting the process.</span></span>  
  
 <span data-ttu-id="c6120-105">この "Southridge Video のケーブル サービス注文システム" ソリューションでは、ビジネス プロセスが一連のステージに分割されています。</span><span class="sxs-lookup"><span data-stu-id="c6120-105">In this solution, a cable service ordering system for Southridge Video, the business process is broken into a series of stages.</span></span> <span data-ttu-id="c6120-106">これらのステージに対する操作は、ビジネス ルールやバックエンド システムについて何ら知識のない注文マネージャによって指示されます。</span><span class="sxs-lookup"><span data-stu-id="c6120-106">An order manager, which knows nothing about the business rules and backend systems, directs the operation of the stages.</span></span> <span data-ttu-id="c6120-107">注文マネージャは、注文ブローカから注文を受け取ります。注文ブローカは複数の異なる注文マネージャに注文を送信できます。</span><span class="sxs-lookup"><span data-stu-id="c6120-107">The order manager receives orders from an order broker, which can direct orders to several different order managers.</span></span>  
  
 <span data-ttu-id="c6120-108">このソリューションでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の機能を広く利用し、特にアプリケーションの各部を調整するためにアプリケーション内部のメッセージを使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="c6120-108">The solution makes extensive use of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] features and shows, among other things, the use of messages internal to the application for coordinating parts of the application.</span></span>  
  
## <a name="reader-guidance"></a><span data-ttu-id="c6120-109">対象読者</span><span class="sxs-lookup"><span data-stu-id="c6120-109">Reader Guidance</span></span>  
 <span data-ttu-id="c6120-110">このドキュメントが慣れていることを前提と[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]と Microsoft[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="c6120-110">This document assumes that you are familiar with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="c6120-111">また、エンタープライズ アプリケーション統合と Web サービスの基本的な概念についても理解していることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="c6120-111">It also assumes that you understand basic concepts about enterprise application integration and Web services.</span></span>  
  
 <span data-ttu-id="c6120-112">さらに、開発者向けのマニュアルを読み、理解するためには、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] を使用してアプリケーションを構築する方法や、プロジェクトの作成、参照の設定、BizTalk ソリューションのデバッグおよびテストなどのタスクについても精通している必要があります。</span><span class="sxs-lookup"><span data-stu-id="c6120-112">In addition, to read and follow the developer documentation, you should be familiar with how to build applications by using [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] and with performing the following tasks: creating projects, setting references, and debugging and testing BizTalk solutions.</span></span>  
  
## <a name="ordering-cable-service-from-southridge-video"></a><span data-ttu-id="c6120-113">Southridge Video のケーブル サービスの注文</span><span class="sxs-lookup"><span data-stu-id="c6120-113">Ordering Cable Service from Southridge Video</span></span>  
 <span data-ttu-id="c6120-114">ビジネス プロセス管理ソリューションは、Southridge Video のケーブル サービス注文システムを実装します。</span><span class="sxs-lookup"><span data-stu-id="c6120-114">The business process management solution implements a cable service ordering system for Southridge Video.</span></span> <span data-ttu-id="c6120-115">顧客がコール センターに電話すると、顧客サービス担当者が注文を受け、注文システムに入力します。</span><span class="sxs-lookup"><span data-stu-id="c6120-115">Customers phone into a call center where a customer service representative takes the order and enters it into the order system.</span></span> <span data-ttu-id="c6120-116">次の図では、システムにおける注文の全体的な流れを示しています。</span><span class="sxs-lookup"><span data-stu-id="c6120-116">The following diagram shows the general flow of an order through the system:</span></span>  
  
 <span data-ttu-id="c6120-117">![ビジネス プロセス管理ソリューションのワークフロー](../core/media/business-process-manager-solution-work-flow.gif "Business_Process_Manager_Solution_Work_Flow")</span><span class="sxs-lookup"><span data-stu-id="c6120-117">![Business Process Management Solution Work Flow](../core/media/business-process-manager-solution-work-flow.gif "Business_Process_Manager_Solution_Work_Flow")</span></span>  
  
 <span data-ttu-id="c6120-118">注文は、注文ブローカに送られ、そこから注文マネージャに送信されます。</span><span class="sxs-lookup"><span data-stu-id="c6120-118">Orders go to the order broker, which sends the order on to the order manager.</span></span> <span data-ttu-id="c6120-119">注文マネージャは正しい順序で処理ステージを実行し、注文を処理します。</span><span class="sxs-lookup"><span data-stu-id="c6120-119">The order manager runs the processing stages in the proper sequence to process the order.</span></span> <span data-ttu-id="c6120-120">特定の種類のエラーはオペレーション センターに送られ、修正され、再送信されること、およびソリューションでは SQL Server テーブルに各注文の履歴が記録されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="c6120-120">Notice that some kinds of errors go to an operations center for correction and resubmission, and that the solution records the history of each order in a SQL Server table.</span></span>  
  
 <span data-ttu-id="c6120-121">次の図では、注文を処理する手順の概要を示しています。</span><span class="sxs-lookup"><span data-stu-id="c6120-121">The following diagram shows the broad outline of the steps in processing an order.</span></span>  
  
 <span data-ttu-id="c6120-122">![ビジネス プロセス管理ソリューションのシーケンス](../core/media/business-process-manager-solution-sequence.gif "Business_Process_Manager_Solution_Sequence")</span><span class="sxs-lookup"><span data-stu-id="c6120-122">![Business Process Management Solution Sequence](../core/media/business-process-manager-solution-sequence.gif "Business_Process_Manager_Solution_Sequence")</span></span>  
  
 <span data-ttu-id="c6120-123">注文は更新される場合や取り消される場合があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="c6120-123">Notice that an order can be updated as well as canceled.</span></span>  
  
## <a name="business-requirements"></a><span data-ttu-id="c6120-124">ビジネス要件</span><span class="sxs-lookup"><span data-stu-id="c6120-124">Business Requirements</span></span>  
 <span data-ttu-id="c6120-125">ビジネス プロセス管理ソリューションは、ケーブル サービス業者である Southridge Video の注文システムの例を示します。</span><span class="sxs-lookup"><span data-stu-id="c6120-125">The business process management solution is an example of an order system for Southridge Video, a cable service provider.</span></span> <span data-ttu-id="c6120-126">Microsoft BizTalk Server にプロセス マネージャ パターンを実装する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="c6120-126">It shows one way to implement the process manager pattern in Microsoft BizTalk Server.</span></span> <span data-ttu-id="c6120-127">このソリューションでは、オーケストレーションを使用して、ビジネス プロセスを実行する 2 つのサテライト オーケストレーションを介した注文の流れを管理します。</span><span class="sxs-lookup"><span data-stu-id="c6120-127">The solution uses an orchestration to manage the flow of orders through two satellite orchestrations that implement the business process.</span></span> <span data-ttu-id="c6120-128">この構造は、ソリューションの次のようなビジネス要件に基づいています。</span><span class="sxs-lookup"><span data-stu-id="c6120-128">This structure comes out of the solution's business requirements which include the following:</span></span>  
  
-   <span data-ttu-id="c6120-129">ビジネス プロセスのバージョン管理を行う。</span><span class="sxs-lookup"><span data-stu-id="c6120-129">Ability to version the business process</span></span>  
  
-   <span data-ttu-id="c6120-130">長期にわたる注文を処理する。</span><span class="sxs-lookup"><span data-stu-id="c6120-130">Process long-running orders</span></span>  
  
-   <span data-ttu-id="c6120-131">処理中の注文を変更またはキャンセルする (注文に対する補足処理)。</span><span class="sxs-lookup"><span data-stu-id="c6120-131">Modify or cancel orders that are still being processed (supplement in-flight orders)</span></span>  
  
-   <span data-ttu-id="c6120-132">保留注文を避ける。</span><span class="sxs-lookup"><span data-stu-id="c6120-132">Avoid suspended orders</span></span>  
  
-   <span data-ttu-id="c6120-133">プロセス全体で注文を追跡する。</span><span class="sxs-lookup"><span data-stu-id="c6120-133">Track orders through the entire process</span></span>  
  
-   <span data-ttu-id="c6120-134">注文を一括処理する。</span><span class="sxs-lookup"><span data-stu-id="c6120-134">Batch order processing</span></span>  
  
-   <span data-ttu-id="c6120-135">リモート データ センターからの注文を受け付ける。</span><span class="sxs-lookup"><span data-stu-id="c6120-135">Accept orders from remote data centers</span></span>  
  
-   <span data-ttu-id="c6120-136">複数のグループが注文処理の各部分を処理できる。</span><span class="sxs-lookup"><span data-stu-id="c6120-136">Allowing different groups to handle parts of the order processing</span></span>  
  
-   <span data-ttu-id="c6120-137">BizTalk グループを追加してアプリケーションを拡張する。</span><span class="sxs-lookup"><span data-stu-id="c6120-137">Scale the application by adding BizTalk groups</span></span>  
  
-   <span data-ttu-id="c6120-138">リモート処理により、注文マネージャをアプリケーション サーバーとして公開する。</span><span class="sxs-lookup"><span data-stu-id="c6120-138">Expose, by remoting, the order manager as an application server</span></span>  
  
 <span data-ttu-id="c6120-139">Southridge Video のビジネス要件では、注文ブローカ、プロセス マネージャ、およびビジネス プロセスの 3 つの部分による構造になります。</span><span class="sxs-lookup"><span data-stu-id="c6120-139">The business requirements of Southridge Video produce a three-part structure: an order broker, a process manager, and the business process itself.</span></span> <span data-ttu-id="c6120-140">Southridge Video には、アプリケーションに関与する IT グループが 2 つあります。</span><span class="sxs-lookup"><span data-stu-id="c6120-140">Southridge Videohas two separate IT groups involved in the application.</span></span> <span data-ttu-id="c6120-141">メッセージング グループは、企業メッセージング インフラストラクチャを管理し、そのインフラストラクチャにアプリケーションを接続するためのコンポーネントを提供します。</span><span class="sxs-lookup"><span data-stu-id="c6120-141">A messaging group maintains the corporate messaging infrastructure and provides the components for connecting applications to that infrastructure.</span></span> <span data-ttu-id="c6120-142">もう一方のグループは、特定のビジネス プロセスのアプリケーションを作成し、管理します。</span><span class="sxs-lookup"><span data-stu-id="c6120-142">Another group writes and maintains applications for specific business processes.</span></span> <span data-ttu-id="c6120-143">したがって、注文ブローカは、独立したグループで管理できるように、注文プロセス マネージャおよびプロセス ステージから分離します。</span><span class="sxs-lookup"><span data-stu-id="c6120-143">Thus, the order broker is separate from the order process manager and process stages so that it can be maintained by a separate group.</span></span> <span data-ttu-id="c6120-144">注文ブローカは独立したコンポーネントであるため、複数のプロセス マネージャへの注文を仲介できるように拡張することもできます。</span><span class="sxs-lookup"><span data-stu-id="c6120-144">Because it is a separate component, the order broker can also be extended to broker orders to multiple process managers.</span></span> <span data-ttu-id="c6120-145">プロセス マネージャを追加すると、VIP サービスなどの新しいビジネス ラインをサポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="c6120-145">A process manager might be added to support a new business line, such as VIP service.</span></span>  
  
 <span data-ttu-id="c6120-146">Southridge Video の注文は、長期プロセスです。ケーブル注文が完了するまでに要する時間は、1 分から 1 年までさまざまです。</span><span class="sxs-lookup"><span data-stu-id="c6120-146">Southridge Video orders are long running processes: a cable order may take anywhere from a minute to a year to complete.</span></span> <span data-ttu-id="c6120-147">BizTalk オーケストレーションのインスタンスは完了するまで実行される必要があるため、オーケストレーション インスタンスの有効期間は最長で 1 年になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="c6120-147">Because an instance of a BizTalk orchestration must run to completion, this means that an orchestration instance could have a lifetime of up to a year.</span></span>  
  
 <span data-ttu-id="c6120-148">Southridge Video は、注文処理中にアプリケーション コンポーネントを変更できるような、長期プロセスに対応したアーキテクチャを必要としています。</span><span class="sxs-lookup"><span data-stu-id="c6120-148">Southridge Video needs an architecture for long running processes that allows for application components to change during order processing.</span></span> <span data-ttu-id="c6120-149">このため、最新のプロセス コンポーネントを使用して注文を完了できるように、Southridge では注文処理を複数のステージに分割しました。</span><span class="sxs-lookup"><span data-stu-id="c6120-149">Thus, Southridge divides order processing into multiple stages so that an order can complete using the newest process components.</span></span> <span data-ttu-id="c6120-150">ビジネス プロセスにおいてステージの境界を決定する方法については、次を参照してください。[ビジネス プロセス管理ソリューションで一部の設計原則](../core/some-design-principles-in-the-business-process-management-solution.md)です。</span><span class="sxs-lookup"><span data-stu-id="c6120-150">For information about how to determine stage boundaries in a business process, see [Some Design Principles in the Business Process Management Solution](../core/some-design-principles-in-the-business-process-management-solution.md).</span></span>  
  
 <span data-ttu-id="c6120-151">注文の処理時間が長いことも、処理中の注文の変更が必要になる要因です。</span><span class="sxs-lookup"><span data-stu-id="c6120-151">The long processing time for an order also, in part, determines the need to change in-flight orders.</span></span> <span data-ttu-id="c6120-152">注文の変更は、ソリューションに広範な割り込みシステムが組み込まれている理由の 1 つです。</span><span class="sxs-lookup"><span data-stu-id="c6120-152">Modifying orders is one of the reasons that the solution includes an extensive system of interrupts.</span></span> <span data-ttu-id="c6120-153">割り込みシステムを組み込むと、完了していない注文を簡単に変更またはキャンセルできます。</span><span class="sxs-lookup"><span data-stu-id="c6120-153">This interrupt system simplifies making order changes or cancellations before they are complete.</span></span> <span data-ttu-id="c6120-154">ソリューションでは、割り込みを処理するためのソリューションの各機能間の通信に .NET メッセージを使用します。</span><span class="sxs-lookup"><span data-stu-id="c6120-154">The solution uses .NET messages to communicate between functional parts of the solution to handle interruptions.</span></span>  
  
 <span data-ttu-id="c6120-155">システムには、いくつもの外部依存関係があるため、エラー後に再試行される操作もあります。</span><span class="sxs-lookup"><span data-stu-id="c6120-155">Because the system has numerous external dependencies, certain operations can be retried after failure.</span></span> <span data-ttu-id="c6120-156">たとえば、バックエンド システムを使用できず、それに対する要求がタイムアウトになると、ソリューションでは、適切な時間待機し、要求を再度実行します。</span><span class="sxs-lookup"><span data-stu-id="c6120-156">For example, if a backend system is unavailable and a request to it times out, the solution waits an appropriate interval and retries the request.</span></span> <span data-ttu-id="c6120-157">外部システムへの接続はカスタム コードによるため、ソリューションのその部分ではオブジェクト メソッドを再試行できるように、.NET リフレクションを広範に使用します。</span><span class="sxs-lookup"><span data-stu-id="c6120-157">Because connections to external systems are through custom code, this portion of the solution makes extensive use of .NET reflection to allow object methods to be retried.</span></span>  
  
 <span data-ttu-id="c6120-158">このソリューションでは、基になっている実際の会社と同じように、オペレーション グループの担当者が注文処理に関する問題を処理できることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="c6120-158">The solution assumes, like the real-life company it is based on, that problems with order processing can be handled by people in an operations group.</span></span> <span data-ttu-id="c6120-159">同様に、顧客サービス担当者に返される注文エラーもあります。顧客サービス担当者は、その注文をキャンセルするか、修正して再送信します。</span><span class="sxs-lookup"><span data-stu-id="c6120-159">Similarly, some kind of order errors will be referred back to a customer service representative who may cancel or correct and re-submit the order.</span></span>  
  
## <a name="business-process-management-solution-resources"></a><span data-ttu-id="c6120-160">ビジネス プロセス管理ソリューションのリソース</span><span class="sxs-lookup"><span data-stu-id="c6120-160">Business Process Management Solution Resources</span></span>  
 <span data-ttu-id="c6120-161">ビジネス プロセス管理ソリューションの詳細については、次のドキュメントをお読みください。</span><span class="sxs-lookup"><span data-stu-id="c6120-161">Read the following documents for additional information about the business process management solution.</span></span>  
  
### <a name="business-process-management-solution-resources"></a><span data-ttu-id="c6120-162">ビジネス プロセス管理ソリューションのリソース</span><span class="sxs-lookup"><span data-stu-id="c6120-162">Business Process Management Solution Resources</span></span>  
  
-   [<span data-ttu-id="c6120-163">ビジネス プロセス管理ソリューションの開発</span><span class="sxs-lookup"><span data-stu-id="c6120-163">Developing a Business Process Management Solution</span></span>](../core/developing-a-business-process-management-solution.md)  
  
     <span data-ttu-id="c6120-164">開発者やソフトウェア設計者は、このガイドを使用して、ビジネス プロセス管理アプリケーションの構築と実行に必要なすべてのコード、パターン、アーキテクチャ、およびパフォーマンス デザインを記述できます。</span><span class="sxs-lookup"><span data-stu-id="c6120-164">Developers and Software Architects can use this guide to document all code, patterns, architecture, and performance design issues required to build and run the business process management application.</span></span>  
  
-   [<span data-ttu-id="c6120-165">ビジネス プロセス管理ソリューションの展開</span><span class="sxs-lookup"><span data-stu-id="c6120-165">Deploying the Business Process Management Solution</span></span>](../core/deploying-the-business-process-management-solution.md)  
  
     <span data-ttu-id="c6120-166">BizTalk Server の一般知識を持っている IT プロフェッショナルは、このガイドを使用してビジネス プロセス管理アプリケーションを構築し、実行できます。</span><span class="sxs-lookup"><span data-stu-id="c6120-166">The IT professional with a general understanding of BizTalk Server can use this guide to build and run the Business Process Management application.</span></span> <span data-ttu-id="c6120-167">このガイドは、ユーザーが、分散環境でのアプリケーションの機能に関する一般的な知識を持っていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="c6120-167">The guide assumes a general understanding of how the application works in a distributed environment.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6120-168">参照</span><span class="sxs-lookup"><span data-stu-id="c6120-168">See Also</span></span>  
 [<span data-ttu-id="c6120-169">ビジネス プロセス管理ソリューション</span><span class="sxs-lookup"><span data-stu-id="c6120-169">Business Process Management Solution</span></span>](../core/business-process-management-solution.md)