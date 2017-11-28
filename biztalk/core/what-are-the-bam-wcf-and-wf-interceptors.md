---
title: "BAM WCF インターセプターと WF インターセプターについて | Microsoft Docs"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 198bfdc9-86ff-4017-b65f-19616deeb9f4
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c819d219a9796b485434101ee1c2f2d4be136ae0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="what-are-the-bam-wcf-and-wf-interceptors"></a><span data-ttu-id="9505b-103">BAM WCF インターセプターと WF インターセプターについて</span><span class="sxs-lookup"><span data-stu-id="9505b-103">What Are the BAM WCF and WF Interceptors?</span></span>
<span data-ttu-id="9505b-104">ビジネス アクティビティの監視 (BAM) は、集計、警告、およびプロファイルを管理し、イベント送信の自動プロセスをインストルメント化して関連するビジネス指標を監視するために使用できるツール、API、およびサービスのコレクションです。</span><span class="sxs-lookup"><span data-stu-id="9505b-104">Business Activity Monitoring (BAM) is a collection of tools, APIs, and services that allow you to manage aggregations, alerts, and profiles, and to instrument automated processes to send events to monitor relevant business metrics.</span></span> <span data-ttu-id="9505b-105">これらによって、ビジネス プロセスを詳細に表示できるようになるため、ビジネス プロセスの状態と結果を常に把握できます。</span><span class="sxs-lookup"><span data-stu-id="9505b-105">Together, these provide end-to-end visibility into business processes and enable you to stay abreast of business process status and results.</span></span>  
  
 <span data-ttu-id="9505b-106">BAM インターセプターでは、この同じ機能が Windows Workflow Foundation (WF)、Windows Communication Foundation (WCF) などのランタイムの環境に拡張されます。</span><span class="sxs-lookup"><span data-stu-id="9505b-106">BAM interceptors extend this same functionality into Windows Workflow Foundation (WF), Windows Communication Foundation (WCF), and other runtime environments.</span></span> <span data-ttu-id="9505b-107">BAM インターセプタを使用すると、構成ファイルで統合処理が実行されるため、WF または WCF ソリューションを再コンパイルせずにビジネス プロセスを追跡できます。</span><span class="sxs-lookup"><span data-stu-id="9505b-107">By using a BAM interceptor, you can track your business processes without recompiling your WF or WCF solution—integration is done through a configuration file.</span></span>  
  
 <span data-ttu-id="9505b-108">BAM WF または WCF インターセプターをプロジェクトで使用すると、次の処理を実行できます。</span><span class="sxs-lookup"><span data-stu-id="9505b-108">By using the BAM WF or WCF interceptor in your project, you can:</span></span>  
  
-   <span data-ttu-id="9505b-109">BAM ポータルを使用して、WF または WCF アプリケーションで動作しているビジネス プロセスに関する情報を表示する。</span><span class="sxs-lookup"><span data-stu-id="9505b-109">Use the BAM portal to view information about the business processes running in your WF or WCF application.</span></span>  
  
-   <span data-ttu-id="9505b-110">アプリケーションにコードを追加せずに BAM 機能を使用する。</span><span class="sxs-lookup"><span data-stu-id="9505b-110">Use BAM functionality without adding additional code to your application.</span></span>  
  
-   <span data-ttu-id="9505b-111">使い慣れた BizTalk Server のツールとユーティリティを使用して、ソリューションを展開する。</span><span class="sxs-lookup"><span data-stu-id="9505b-111">Deploy your solution using familiar BizTalk Server tools and utilities.</span></span>  
  
-   <span data-ttu-id="9505b-112">既存および新しい WF および WCF アプリケーションに対して、既存の BizTalk Server 環境を利用する。</span><span class="sxs-lookup"><span data-stu-id="9505b-112">Leverage your existing BizTalk Server environment for existing and new WF and WCF applications.</span></span>  
  
## <a name="interceptor-components"></a><span data-ttu-id="9505b-113">インターセプター コンポーネント</span><span class="sxs-lookup"><span data-stu-id="9505b-113">Interceptor Components</span></span>  
 <span data-ttu-id="9505b-114">各 BAM インターセプターの中核にあるのは、異種混合環境用のカスタム インターセプターを構築するための基盤となるコンポーネントのセットである Common Interceptor Foundation (共通インターセプター基盤) です。</span><span class="sxs-lookup"><span data-stu-id="9505b-114">At the core of each BAM interceptor is the Common Interceptor Foundation, a set of components that provide the foundation for building custom interceptors for heterogeneous environments.</span></span> <span data-ttu-id="9505b-115">Common Interceptor Foundation には、次の共有コンポーネントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="9505b-115">The Common Interceptor Foundation contains the following shared components:</span></span>  
  
-   <span data-ttu-id="9505b-116">**bm.exe**、BAM 展開ユーティリティの拡張のバージョンの拡張を追加、削除、更新、およびリストの機能を含むインターセプター構成を変更します。</span><span class="sxs-lookup"><span data-stu-id="9505b-116">**bm.exe**, an enhanced version of the BAM deployment utility extended to modify interceptor configurations including add, remove, update, and list functionality.</span></span>  
  
-   <span data-ttu-id="9505b-117">**CommonInterceptorConfiguration.xsd**、Common Interceptor Foundation 構成の XML スキーマです。</span><span class="sxs-lookup"><span data-stu-id="9505b-117">**CommonInterceptorConfiguration.xsd**, the Common Interceptor Foundation configuration XML schema.</span></span> <span data-ttu-id="9505b-118">すべてのインターセプター構成は、少なくとも、このスキーマに対して有効でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="9505b-118">At minimum, all interceptor configurations must validate against this schema.</span></span>  
  
## <a name="windows-workflow-foundation-wf-interceptor"></a><span data-ttu-id="9505b-119">Windows Workflow Foundation (WF) インターセプター</span><span class="sxs-lookup"><span data-stu-id="9505b-119">Windows Workflow Foundation (WF) Interceptor</span></span>  
 <span data-ttu-id="9505b-120">Windows Workflow Foundation インターセプターを使用すると、新しい WF アプリケーションおよび既存の WF アプリケーションに BAM 追跡機能を透過的に追加できます。</span><span class="sxs-lookup"><span data-stu-id="9505b-120">The Windows Workflow Foundation interceptor enables you to transparently add BAM tracking functionality to new and existing WF applications.</span></span> <span data-ttu-id="9505b-121">インターセプター構成を BAM プライマリ インポート データベースに展開し、BAM WF インターセプターを読み込むように WF アプリケーションの各インスタンスが構成されると、コードを追加しなくてもワークフロー データが BAM に書き込まれるようになります。</span><span class="sxs-lookup"><span data-stu-id="9505b-121">After the interceptor configuration has been deployed to the BAM Primary Import database and each instance of the WF application has been configured to load the BAM WF Interceptor, workflow data will be written to BAM with no additional code.</span></span> <span data-ttu-id="9505b-122">WF インターセプターには、次の機能があります。</span><span class="sxs-lookup"><span data-stu-id="9505b-122">The WF interceptor provides the following functionality:</span></span>  
  
-   <span data-ttu-id="9505b-123">既存の WF アプリケーションにプラグインするときに、コードの変更や再コンパイルが不要です。</span><span class="sxs-lookup"><span data-stu-id="9505b-123">Plugs into existing WF applications without requiring code changes or recompilation.</span></span>  
  
-   <span data-ttu-id="9505b-124">変更された構成ファイルを実行時に検出し、使用できます。</span><span class="sxs-lookup"><span data-stu-id="9505b-124">Enables run-time detection and support for changed configuration files.</span></span> <span data-ttu-id="9505b-125">新しいバージョンのインターセプト構成ファイルが検出された場合、新しいワークフロー インスタンスは、この新しい構成が使用しますが、古いワークフロー インスタンスは古い構成を使用して完了します。</span><span class="sxs-lookup"><span data-stu-id="9505b-125">If a new version of an interceptor configuration file is detected, new workflow instances will use the new configuration while old workflow instances will complete using the old configuration.</span></span>  
  
-   <span data-ttu-id="9505b-126">トランザクションがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="9505b-126">Supports transactions.</span></span> <span data-ttu-id="9505b-127">WF インターセプターでは、追跡された項目のトランザクション状態が WF トランザクションと同じように保存されます。</span><span class="sxs-lookup"><span data-stu-id="9505b-127">The WF interceptor persists tracked items in a transactionally consistent way with WF transactions.</span></span> <span data-ttu-id="9505b-128">追跡された項目は、WF トランザクションとインターセプター トランザクションが正常に完了した場合にのみ保存されます。</span><span class="sxs-lookup"><span data-stu-id="9505b-128">Tracked items are only persisted when the WF transaction and the interceptor trasaction complete successfully.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9505b-129">Windows Workflow インターセプターでは、追跡サービスと永続化サービスの両方に同じ SQL 接続を使用する SharedConnectionWorkflowCommitWorkBatchService はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="9505b-129">The Windows Workflow interceptor does not support SharedConnectionWorkflowCommitWorkBatchService which uses the same SQL connection for both the tracking and persistence services.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9505b-130">BizTalk Server で、Windows Workflow Foundation (WF) インターセプターは、.NET Framework 4 の新しい WF エンジンとは機能しません。</span><span class="sxs-lookup"><span data-stu-id="9505b-130">In BizTalk Server, the Windows Workflow Foundation (WF) interceptor will not work with the new WF engine in .NET Framework 4.</span></span> <span data-ttu-id="9505b-131">WF インターセプターは、.NET Framework 3.5 SP2 で動作し続けます。</span><span class="sxs-lookup"><span data-stu-id="9505b-131">The WF interceptor will continue to work in .NET Framework 3.5 SP2.</span></span>  
  
## <a name="windows-communication-foundation-wcf-interceptor"></a><span data-ttu-id="9505b-132">WCF (Windows Communication Foundation) インターセプター</span><span class="sxs-lookup"><span data-stu-id="9505b-132">Windows Communication Foundation (WCF) Interceptor</span></span>  
 <span data-ttu-id="9505b-133">Windows Communication Foundation インターセプターを使用すると、WCF アプリケーションで BAM 追跡機能を利用できます。</span><span class="sxs-lookup"><span data-stu-id="9505b-133">The Windows Communication Foundation interceptor provides BAM tracking functionality to your WCF applications.</span></span> <span data-ttu-id="9505b-134">WCF インターセプターには、次の機能があります。</span><span class="sxs-lookup"><span data-stu-id="9505b-134">It provides the following functionality:</span></span>  
  
-   <span data-ttu-id="9505b-135">既存の WCF アプリケーションにプラグインするときに、コードの変更や再コンパイルが不要です。</span><span class="sxs-lookup"><span data-stu-id="9505b-135">Plugs into existing WCF applications without requiring code changes or recompilation.</span></span>  
  
-   <span data-ttu-id="9505b-136">WCF サービス呼び出し内のメッセージを追跡します。</span><span class="sxs-lookup"><span data-stu-id="9505b-136">Tracks messages contained in WCF service calls.</span></span>  
  
-   <span data-ttu-id="9505b-137">WCF サービス呼び出し内のメッセージから情報を追跡します。</span><span class="sxs-lookup"><span data-stu-id="9505b-137">Tracks information from messages in WCF service calls.</span></span>  
  
-   <span data-ttu-id="9505b-138">クライアントからのトランザクション フロー、または実行されたサービス呼び出しのために内部で開始されたトランザクション フローに参加できます。</span><span class="sxs-lookup"><span data-stu-id="9505b-138">Participates in transactions flowed from the client or initiated internally for transacted service calls.</span></span>