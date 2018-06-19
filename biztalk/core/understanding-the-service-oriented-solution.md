---
title: サービス指向ソリューション |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- service solution tutorial, background information
- service solutions, about service solutions
- service solution tutorial, about service solution tutorial
- Service Oriented Architecture (SOA)
ms.assetid: 56a2ad90-74bb-489a-ab1d-900f3bea3d64
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a8be3a1e7a05c2c60f1ab16c6da4df74dddf7adb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22287946"
---
# <a name="understanding-the-service-oriented-solution"></a><span data-ttu-id="cbfca-102">サービス指向ソリューション</span><span class="sxs-lookup"><span data-stu-id="cbfca-102">Understanding the Service Oriented Solution</span></span>
<span data-ttu-id="cbfca-103">サービス指向ソリューションは、サービスとして設計された預金残高を記録するアプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="cbfca-103">The service oriented solution presents a credit balance reporting application designed as a service.</span></span> <span data-ttu-id="cbfca-104">このアプリケーションは、サービスとして公開されている 3 つのバックエンド アプリケーションを使用して、預金残高の必要な情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="cbfca-104">The application, in turn, uses three backend applications, exposed as services themselves, to get the information needed for the credit balance.</span></span>  
  
 <span data-ttu-id="cbfca-105">サービス指向アーキテクチャ (SOA) は、分散システムの構築と部分的に重複するアプローチです。</span><span class="sxs-lookup"><span data-stu-id="cbfca-105">A Service Oriented Architecture (SOA) is an approach that partially overlaps building distributed systems.</span></span> <span data-ttu-id="cbfca-106">サービス指向アプローチには、いくつかの特性があります。</span><span class="sxs-lookup"><span data-stu-id="cbfca-106">A service-oriented approach has several characteristics:</span></span>  
  
-   <span data-ttu-id="cbfca-107">疎結合である。</span><span class="sxs-lookup"><span data-stu-id="cbfca-107">Loosely coupled.</span></span> <span data-ttu-id="cbfca-108">このアプリケーションのビジネス ロジックは、サービスを処理するロジックと区別されています。</span><span class="sxs-lookup"><span data-stu-id="cbfca-108">The application's business logic is separate from the logic of handling the service.</span></span>  
  
-   <span data-ttu-id="cbfca-109">検出可能である。</span><span class="sxs-lookup"><span data-stu-id="cbfca-109">Discoverable.</span></span> <span data-ttu-id="cbfca-110">サービスを検出するアプリケーション用のメカニズムがあります。</span><span class="sxs-lookup"><span data-stu-id="cbfca-110">There should be a mechanism for applications to find the service.</span></span>  
  
-   <span data-ttu-id="cbfca-111">コントラクトを使用する。</span><span class="sxs-lookup"><span data-stu-id="cbfca-111">Contractual.</span></span> <span data-ttu-id="cbfca-112">サービスに対するインターフェイスでは、ユーザーとサービス間のコントラクトを実装します。</span><span class="sxs-lookup"><span data-stu-id="cbfca-112">The interface to the service implements the contract between users and the service.</span></span>  
  
 <span data-ttu-id="cbfca-113">文献では、多くの場合、サービス指向アプローチを Web サービスと同じように扱っています。ただし、必ずしも同義ではありません。</span><span class="sxs-lookup"><span data-stu-id="cbfca-113">Although the literature often treats service oriented approaches as synonymous with web services, they are not necessarily synonyms.</span></span> <span data-ttu-id="cbfca-114">Web サービスは、サービス指向ソリューションを実装する有効な方法ですが、.NET リモート処理などの他の技術を使用しても、サービスを作成することはできます。</span><span class="sxs-lookup"><span data-stu-id="cbfca-114">Web services present an attractive way to implement service oriented solutions, but you can use other technologies, such as .NET remoting, to create services.</span></span>  
  
 <span data-ttu-id="cbfca-115">サービス指向アーキテクチャの詳細についてで「Service Interface」を参照してください。 [http://go.microsoft.com/fwlink/?LinkId=46185](http://go.microsoft.com/fwlink/?LinkId=46185)およびで「Service-Oriented Integration」 [http://go.microsoft.com/fwlink/?LinkId=46186](http://go.microsoft.com/fwlink/?LinkId=46186)です。</span><span class="sxs-lookup"><span data-stu-id="cbfca-115">For more information about service oriented architectures, see "Service Interface" at [http://go.microsoft.com/fwlink/?LinkId=46185](http://go.microsoft.com/fwlink/?LinkId=46185) and "Service-Oriented Integration" at [http://go.microsoft.com/fwlink/?LinkId=46186](http://go.microsoft.com/fwlink/?LinkId=46186).</span></span>  
  
## <a name="reader-guidance"></a><span data-ttu-id="cbfca-116">対象読者</span><span class="sxs-lookup"><span data-stu-id="cbfca-116">Reader Guidance</span></span>  
 <span data-ttu-id="cbfca-117">このソリューションのドキュメントを熟知している前提としています[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]と Microsoft[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="cbfca-117">The documentation for this solution assumes that you are familiar with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="cbfca-118">また、エンタープライズ アプリケーション統合と Web サービスの基本的な概念に精通していることも前提とします。</span><span class="sxs-lookup"><span data-stu-id="cbfca-118">It also assumes that you understand basic concepts about enterprise application integration and web services.</span></span>  
  
 <span data-ttu-id="cbfca-119">さらに、開発者向けのマニュアルを読み、理解するためには、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] を使用してアプリケーションを構築する方法や、プロジェクトの作成、参照の設定、BizTalk ソリューションのデバッグおよびテストなどのタスクについても精通している必要があります。</span><span class="sxs-lookup"><span data-stu-id="cbfca-119">In addition, to read and follow the developer documentation, you should be familiar with how to build applications by using [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] and with performing the following tasks: creating projects, setting references, and debugging and testing BizTalk solutions.</span></span>  
  
## <a name="credit-card-reporting-at-woodgrove-bank"></a><span data-ttu-id="cbfca-120">Woodgrove Bank のクレジット カード記録</span><span class="sxs-lookup"><span data-stu-id="cbfca-120">Credit Card Reporting at Woodgrove Bank</span></span>  
 <span data-ttu-id="cbfca-121">このサービス指向アーキテクチャのソリューションは、クレジット カードの残高を記録する Woodgrove Bank のサービスです。</span><span class="sxs-lookup"><span data-stu-id="cbfca-121">The service oriented architecture solution is a credit card balance reporting service for Woodgrove Bank.</span></span> <span data-ttu-id="cbfca-122">銀行は架空のシナリオではありません-シナリオが実際に展開された顧客アプリケーションに基づきます。</span><span class="sxs-lookup"><span data-stu-id="cbfca-122">Although the bank is fictional, the scenario is not—the scenario is based on an actual, deployed, customer application.</span></span>  
  
 <span data-ttu-id="cbfca-123">このシナリオでは、次の 2 つのソースからクレジット カード残高が要求されます。</span><span class="sxs-lookup"><span data-stu-id="cbfca-123">In the scenario, requests for credit card balances come from two sources:</span></span>  
  
-   <span data-ttu-id="cbfca-124">音声自動応答 (IVR) アプリケーション</span><span class="sxs-lookup"><span data-stu-id="cbfca-124">An Interactive Voice Response (IVR) application.</span></span>  
  
-   <span data-ttu-id="cbfca-125">Web ページやカスタム クライアント アプリケーションなどの対話形式のクライアント</span><span class="sxs-lookup"><span data-stu-id="cbfca-125">An interactive client such as a web page or custom client application.</span></span>  
  
 <span data-ttu-id="cbfca-126">このソリューションでは、IVR アプリケーションからの要求は MQSeries を介して受け取ります。</span><span class="sxs-lookup"><span data-stu-id="cbfca-126">The solution receives requests from the IVR application through MQSeries.</span></span> <span data-ttu-id="cbfca-127">対話形式のクライアントからの要求は、HTTP および SOAP を使用する Web サービスを介して処理されます。</span><span class="sxs-lookup"><span data-stu-id="cbfca-127">It handles requests from the interactive client through a web service using HTTP and SOAP.</span></span>  
  
 <span data-ttu-id="cbfca-128">新しいサービス指向アーキテクチャのアプリケーションは、多くの場合、Web サービスを使用する Web サイトなどの新しいアプリケーションの機能と同様に、古い技術を使用しているレガシ アプリケーションとの連携が必要になります。</span><span class="sxs-lookup"><span data-stu-id="cbfca-128">New service oriented architecture applications often need to work with legacy applications that use older technologies, as well as function with modern applications such as web sites that consume web services.</span></span> <span data-ttu-id="cbfca-129">シナリオでは、この実際の要件をモデル化、IVR アプリケーションは、カスタマー サービスのクライアント アプリケーションの中に、レガシ アプリケーションを表し、最新であります。</span><span class="sxs-lookup"><span data-stu-id="cbfca-129">The scenario models this real world requirement—the IVR application represents a legacy application, while the customer service client application, is the modern one.</span></span>  
  
 <span data-ttu-id="cbfca-130">Woodgrove Bank アプリケーションは、3 つのバックエンド レガシ システムのデータを使用して、要求に応答します。</span><span class="sxs-lookup"><span data-stu-id="cbfca-130">The Woodgrove Bank application uses data from three backend, legacy systems to respond to requests:</span></span>  
  
-   <span data-ttu-id="cbfca-131">全体のクレジット限度額を提供するアプリケーション。</span><span class="sxs-lookup"><span data-stu-id="cbfca-131">An application that provides the overall credit limit.</span></span> <span data-ttu-id="cbfca-132">このアプリケーションは、メインフレーム コンピュータの SAP システムです。</span><span class="sxs-lookup"><span data-stu-id="cbfca-132">This is a SAP system on a mainframe computer.</span></span>  
  
-   <span data-ttu-id="cbfca-133">アカウントの未処理トランザクションの合計額を記録する Pending Transactions システム。</span><span class="sxs-lookup"><span data-stu-id="cbfca-133">A pending transactions system that reports the total amount for transactions pending against the account.</span></span> <span data-ttu-id="cbfca-134">このシステムは、メインフレームまたは AS 400 システムです。</span><span class="sxs-lookup"><span data-stu-id="cbfca-134">This system is a mainframe or AS/400 system.</span></span> <span data-ttu-id="cbfca-135">このソリューションは、Web サービスおよび Microsoft Host Integration Server (HIS) を使用して、メインフレームまたは AS/400 システムと通信します。</span><span class="sxs-lookup"><span data-stu-id="cbfca-135">The solution uses a web service and Microsoft Host Integration Server (HIS) to communicate with the mainframe or AS/400 system.</span></span>  
  
-   <span data-ttu-id="cbfca-136">最新の支払いをシステムに記録する Payment Tracking システム。</span><span class="sxs-lookup"><span data-stu-id="cbfca-136">A payment tracking system that gives the last payment made to the system.</span></span> <span data-ttu-id="cbfca-137">MQSeries を使用して、Payment Tracking システムにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="cbfca-137">The payment tracking system can be reached using MQSeries.</span></span>  
  
 <span data-ttu-id="cbfca-138">レガシ システムからの情報の収集および編集を行った後、このソリューションは、元のアプリケーション (つまり、顧客) に応答を返します。</span><span class="sxs-lookup"><span data-stu-id="cbfca-138">After gathering and compiling the information from the legacy systems, the solution sends the response back to the originating application and, thus, to the customer.</span></span>  
  
## <a name="business-requirements"></a><span data-ttu-id="cbfca-139">ビジネス要件</span><span class="sxs-lookup"><span data-stu-id="cbfca-139">Business Requirements</span></span>  
 <span data-ttu-id="cbfca-140">クレジット記録アプリケーションは、顧客の要求にリアルタイムで応答し、要求をすばやく処理するため、短い待機時間を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cbfca-140">Because the credit reporting application responds in real time to customer requests, it must have low latency in order to handle requests quickly.</span></span> <span data-ttu-id="cbfca-141">また、多くの同時要求にも対応する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cbfca-141">In addition, it must also be able to handle high numbers of simultaneous requests.</span></span> <span data-ttu-id="cbfca-142">このソリューションでは機密情報とパブリック インターフェイスを使用するため、セキュリティが大きな課題です。</span><span class="sxs-lookup"><span data-stu-id="cbfca-142">The solution uses sensitive information and a public interface so that security is significant concern.</span></span> <span data-ttu-id="cbfca-143">最後に、信頼性の高いサービスにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="cbfca-143">Finally, the service needs to be reliable.</span></span>  
  
 <span data-ttu-id="cbfca-144">ソリューションがこれらの要件を満たす方法については、次を参照してください。[サービス指向ソリューションの開発](../core/developing-a-service-oriented-solution.md)です。</span><span class="sxs-lookup"><span data-stu-id="cbfca-144">For information about how the solution meets these requirements, see [Developing a Service Oriented Solution](../core/developing-a-service-oriented-solution.md).</span></span>  
  
## <a name="performance-characteristics"></a><span data-ttu-id="cbfca-145">パフォーマンスの特性</span><span class="sxs-lookup"><span data-stu-id="cbfca-145">Performance Characteristics</span></span>  
 <span data-ttu-id="cbfca-146">ビジネス要件を満たすには、シナリオは、次のパフォーマンス特性を持ちます。</span><span class="sxs-lookup"><span data-stu-id="cbfca-146">To meet the business requirements, the scenario has the following performance characteristics:</span></span>  
  
-   <span data-ttu-id="cbfca-147">維持可能なスループットは 1 秒あたり 40 個の受信要求処理。</span><span class="sxs-lookup"><span data-stu-id="cbfca-147">Sustained throughput of 40 incoming requests per second.</span></span>  
  
-   <span data-ttu-id="cbfca-148">最大スループットは 1 秒あたり 100 個の受信要求処理。</span><span class="sxs-lookup"><span data-stu-id="cbfca-148">Peak throughput of 100 incoming requests per second.</span></span>  
  
-   <span data-ttu-id="cbfca-149">BizTalk Server で送受信する要求の 90%を 1000 ミリ秒未満で処理。</span><span class="sxs-lookup"><span data-stu-id="cbfca-149">90 percent of the requests to be serviced (in and out of BizTalk Server) in under 1000 milliseconds.</span></span>  
  
-   <span data-ttu-id="cbfca-150">BizTalk Server で送受信する要求の 95%を 2000 ミリ秒未満で処理。</span><span class="sxs-lookup"><span data-stu-id="cbfca-150">95 percent of the requests to be serviced (in and out of BizTalk Server) in under 2000 milliseconds.</span></span>  
  
-   <span data-ttu-id="cbfca-151">BizTalk Server で送受信する要求の 100%を 5000 ミリ秒未満で処理。</span><span class="sxs-lookup"><span data-stu-id="cbfca-151">100 percent of the requests to be serviced (in and out of BizTalk Server) in under 5000 milliseconds.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cbfca-152">これらの時間にバックエンド システムの待機時間は含まれません。</span><span class="sxs-lookup"><span data-stu-id="cbfca-152">These times do not include the latency times of the back end systems.</span></span>  
  
## <a name="three-versions-of-the-solution"></a><span data-ttu-id="cbfca-153">ソリューションの 3 つのバージョン</span><span class="sxs-lookup"><span data-stu-id="cbfca-153">Three Versions of the Solution</span></span>  
 <span data-ttu-id="cbfca-154">このソリューションには 3 つのバージョンがあります。</span><span class="sxs-lookup"><span data-stu-id="cbfca-154">There are three versions of the solution:</span></span>  
  
-   <span data-ttu-id="cbfca-155">スタブ バージョンは、すべてのバックエンド システムをソフトウェア スタブに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="cbfca-155">The stub version replaces all of the backend systems with software stubs.</span></span> <span data-ttu-id="cbfca-156">このスタブは、バックエンド システムをシミュレートします。</span><span class="sxs-lookup"><span data-stu-id="cbfca-156">The stubs simulate the backend systems.</span></span> <span data-ttu-id="cbfca-157">このバージョンは、1 台のコンピュータでこのソリューションの展開および実行をすばやく行います。</span><span class="sxs-lookup"><span data-stu-id="cbfca-157">This version provides a quick way to deploy and run the solution on a single computer.</span></span>  
  
-   <span data-ttu-id="cbfca-158">アダプタ バージョンは、BizTalk アダプタを使用して、バックエンド システムに接続します。</span><span class="sxs-lookup"><span data-stu-id="cbfca-158">The adapter version uses BizTalk adapters to connect to the backend systems.</span></span> <span data-ttu-id="cbfca-159">このバージョンは、最初に思いつくこのソリューションの実装方法です。</span><span class="sxs-lookup"><span data-stu-id="cbfca-159">This version is how one might first think to implement the solution.</span></span> <span data-ttu-id="cbfca-160">ただし、アダプタを使用してメッセージをバックエンド システムに送信すると、応答を返す待機時間が長くなります。</span><span class="sxs-lookup"><span data-stu-id="cbfca-160">However, sending messages to the backend systems using the adapters introduces significant latency in getting back responses.</span></span> <span data-ttu-id="cbfca-161">アダプタの待機時間自体は非常に短いのですが、BizTalk Server の分散アーキテクチャでは、アダプタがメッセージ ボックスを使用して、オーケストレーションのホスト インスタンスと通信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cbfca-161">While adapters by themselves could offer very low latency, the distributed architecture of BizTalk Server requires adapters to communicate with the orchestration host instances using the message box.</span></span> <span data-ttu-id="cbfca-162">このため、データベースへのラウンド トリップが発生して、待機時間が影響を受けます。</span><span class="sxs-lookup"><span data-stu-id="cbfca-162">This introduces round trips to the database and affects latency times.</span></span>  
  
-   <span data-ttu-id="cbfca-163">インライン バージョンでは、バックエンド システムと直接通信するインライン コードにアダプタを置き換えます。</span><span class="sxs-lookup"><span data-stu-id="cbfca-163">The inline version replaces the adapters with inline code that communicates directly with the backend systems.</span></span> <span data-ttu-id="cbfca-164">このソリューションのインライン バージョンは、最も短い待機時間で最も高いスループットを実現します。</span><span class="sxs-lookup"><span data-stu-id="cbfca-164">The inline version of the solution has the lowest latency and the highest throughput.</span></span>  
  
 <span data-ttu-id="cbfca-165">この展開ガイドでは、Pending Transactions システムに HIS を使用して接続する各バージョンのシミュレート方法と、このソリューションの 3 つのすべてのバージョンを作成および展開する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="cbfca-165">The deployment guide provides directions for building and deploying all three versions of the solution, as well as providing a way, in each version, to simulate the connection through HIS to the pending transactions system.</span></span> <span data-ttu-id="cbfca-166">構築とソリューションの展開については、次を参照してください。[サービス指向ソリューションの配置](../core/deploying-the-service-oriented-solution.md)です。</span><span class="sxs-lookup"><span data-stu-id="cbfca-166">For information about building and deploying the solution, see [Deploying the Service Oriented Solution](../core/deploying-the-service-oriented-solution.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbfca-167">参照</span><span class="sxs-lookup"><span data-stu-id="cbfca-167">See Also</span></span>  
 [<span data-ttu-id="cbfca-168">サービス指向ソリューション</span><span class="sxs-lookup"><span data-stu-id="cbfca-168">Service Oriented Solution</span></span>](../core/service-oriented-solution.md)