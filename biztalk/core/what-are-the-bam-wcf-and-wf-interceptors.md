---
title: BAM WCF インターセプターと WF インターセプターについて | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 198bfdc9-86ff-4017-b65f-19616deeb9f4
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d3cfa81307220a2685768e2ac13d1a4c922cf944
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65244116"
---
# <a name="what-are-the-bam-wcf-and-wf-interceptors"></a><span data-ttu-id="739a0-103">BAM WCF インターセプターと WF インターセプターについて</span><span class="sxs-lookup"><span data-stu-id="739a0-103">What Are the BAM WCF and WF Interceptors?</span></span>
<span data-ttu-id="739a0-104">ビジネス アクティビティ監視 (BAM) は、ツール、Api、および集計、警告、およびプロファイルを管理して、関連するビジネス指標を監視するイベントを送信する自動化されたプロセスをインストルメント化できるようにするサービスのコレクションです。</span><span class="sxs-lookup"><span data-stu-id="739a0-104">Business Activity Monitoring (BAM) is a collection of tools, APIs, and services that allow you to manage aggregations, alerts, and profiles, and to instrument automated processes to send events to monitor relevant business metrics.</span></span> <span data-ttu-id="739a0-105">これら、ビジネス プロセスのエンド ツー エンドの可視性を提供し、ビジネス プロセスの状態と結果をできるようにします。</span><span class="sxs-lookup"><span data-stu-id="739a0-105">Together, these provide end-to-end visibility into business processes and enable you to stay abreast of business process status and results.</span></span>  
  
 <span data-ttu-id="739a0-106">BAM インターセプターでは、Windows Workflow Foundation (WF)、Windows Communication Foundation (WCF) およびその他のランタイム環境にこれと同じ機能を拡張します。</span><span class="sxs-lookup"><span data-stu-id="739a0-106">BAM interceptors extend this same functionality into Windows Workflow Foundation (WF), Windows Communication Foundation (WCF), and other runtime environments.</span></span> <span data-ttu-id="739a0-107">BAM インターセプタを使用して、WF または WCF ソリューションを再コンパイルしなくても、ビジネス プロセスを追跡できます-統合が構成ファイルで行われます。</span><span class="sxs-lookup"><span data-stu-id="739a0-107">By using a BAM interceptor, you can track your business processes without recompiling your WF or WCF solution—integration is done through a configuration file.</span></span>  
  
 <span data-ttu-id="739a0-108">BAM WF または WCF インターセプターを使用すると、プロジェクトで、次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="739a0-108">By using the BAM WF or WCF interceptor in your project, you can:</span></span>  
  
-   <span data-ttu-id="739a0-109">BAM ポータルを使用して、WF または WCF アプリケーションで実行されているビジネス プロセスに関する情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="739a0-109">Use the BAM portal to view information about the business processes running in your WF or WCF application.</span></span>  
  
-   <span data-ttu-id="739a0-110">アプリケーションに追加のコードを追加せずに BAM 機能を使用します。</span><span class="sxs-lookup"><span data-stu-id="739a0-110">Use BAM functionality without adding additional code to your application.</span></span>  
  
-   <span data-ttu-id="739a0-111">BizTalk Server の使い慣れたツールとユーティリティを使用してソリューションをデプロイします。</span><span class="sxs-lookup"><span data-stu-id="739a0-111">Deploy your solution using familiar BizTalk Server tools and utilities.</span></span>  
  
-   <span data-ttu-id="739a0-112">既存および新規の WF および WCF アプリケーションの既存の BizTalk Server 環境を活用します。</span><span class="sxs-lookup"><span data-stu-id="739a0-112">Leverage your existing BizTalk Server environment for existing and new WF and WCF applications.</span></span>  
  
## <a name="interceptor-components"></a><span data-ttu-id="739a0-113">インターセプター コンポーネント</span><span class="sxs-lookup"><span data-stu-id="739a0-113">Interceptor Components</span></span>  
 <span data-ttu-id="739a0-114">各 BAM インターセプターの中核には、Common Interceptor Foundation、異機種混在環境用のカスタム インターセプターを構築するための基盤を提供するコンポーネントのセットです。</span><span class="sxs-lookup"><span data-stu-id="739a0-114">At the core of each BAM interceptor is the Common Interceptor Foundation, a set of components that provide the foundation for building custom interceptors for heterogeneous environments.</span></span> <span data-ttu-id="739a0-115">Common Interceptor Foundation には、次の共有コンポーネントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="739a0-115">The Common Interceptor Foundation contains the following shared components:</span></span>  
  
-   <span data-ttu-id="739a0-116">**bm.exe**、BAM 展開ユーティリティの拡張のバージョンの拡張を追加、削除、更新、および機能の一覧を含むインターセプター構成を変更します。</span><span class="sxs-lookup"><span data-stu-id="739a0-116">**bm.exe**, an enhanced version of the BAM deployment utility extended to modify interceptor configurations including add, remove, update, and list functionality.</span></span>  
  
-   <span data-ttu-id="739a0-117">**CommonInterceptorConfiguration.xsd**、Common Interceptor Foundation 構成の XML スキーマ。</span><span class="sxs-lookup"><span data-stu-id="739a0-117">**CommonInterceptorConfiguration.xsd**, the Common Interceptor Foundation configuration XML schema.</span></span> <span data-ttu-id="739a0-118">少なくとも、すべてのインターセプター構成は、このスキーマに対して検証する必要があります。</span><span class="sxs-lookup"><span data-stu-id="739a0-118">At minimum, all interceptor configurations must validate against this schema.</span></span>  
  
## <a name="windows-workflow-foundation-wf-interceptor"></a><span data-ttu-id="739a0-119">Windows Workflow Foundation (WF) インターセプター</span><span class="sxs-lookup"><span data-stu-id="739a0-119">Windows Workflow Foundation (WF) Interceptor</span></span>  
 <span data-ttu-id="739a0-120">Windows Workflow Foundation インターセプターでは、新規および既存の WF アプリケーションに BAM 追跡機能を透過的に追加することができます。</span><span class="sxs-lookup"><span data-stu-id="739a0-120">The Windows Workflow Foundation interceptor enables you to transparently add BAM tracking functionality to new and existing WF applications.</span></span> <span data-ttu-id="739a0-121">BAM プライマリ インポート データベースにインターセプター後構成がデプロイされていると、BAM WF インターセプタの読み込みに WF アプリケーションの各インスタンスが構成されて、ワークフローのデータは、コードを追加せずに BAM に書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="739a0-121">After the interceptor configuration has been deployed to the BAM Primary Import database and each instance of the WF application has been configured to load the BAM WF Interceptor, workflow data will be written to BAM with no additional code.</span></span> <span data-ttu-id="739a0-122">WF インターセプターは、次の機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="739a0-122">The WF interceptor provides the following functionality:</span></span>  
  
-   <span data-ttu-id="739a0-123">コードの変更や再コンパイルを必要とせず、既存の WF アプリケーションにプラグインするとき。</span><span class="sxs-lookup"><span data-stu-id="739a0-123">Plugs into existing WF applications without requiring code changes or recompilation.</span></span>  
  
-   <span data-ttu-id="739a0-124">実行時に検出し、変更された構成ファイルのサポートを使用できます。</span><span class="sxs-lookup"><span data-stu-id="739a0-124">Enables run-time detection and support for changed configuration files.</span></span> <span data-ttu-id="739a0-125">古いワークフロー インスタンスは古い構成を使用して完了中に、インターセプター構成ファイルの新しいバージョンが検出された場合に、新しいワークフロー インスタンスで、新しい構成は使用します。</span><span class="sxs-lookup"><span data-stu-id="739a0-125">If a new version of an interceptor configuration file is detected, new workflow instances will use the new configuration while old workflow instances will complete using the old configuration.</span></span>  
  
-   <span data-ttu-id="739a0-126">トランザクションをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="739a0-126">Supports transactions.</span></span> <span data-ttu-id="739a0-127">WF インターセプターは、WF トランザクションとトランザクション上一貫した方法で追跡された項目を保持します。</span><span class="sxs-lookup"><span data-stu-id="739a0-127">The WF interceptor persists tracked items in a transactionally consistent way with WF transactions.</span></span> <span data-ttu-id="739a0-128">追跡された項目は、WF トランザクションとインターセプター トランザクションが正常に完了場合にのみ保存します。</span><span class="sxs-lookup"><span data-stu-id="739a0-128">Tracked items are only persisted when the WF transaction and the interceptor trasaction complete successfully.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="739a0-129">Windows Workflow インターセプターでは、追跡および永続化の両方のサービスの同じ SQL 接続を使用する SharedConnectionWorkflowCommitWorkBatchService はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="739a0-129">The Windows Workflow interceptor does not support SharedConnectionWorkflowCommitWorkBatchService which uses the same SQL connection for both the tracking and persistence services.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="739a0-130">BizTalk Server で、Windows Workflow Foundation (WF) インターセプターは、.NET Framework 4 の新しい WF エンジンとは機能しません。</span><span class="sxs-lookup"><span data-stu-id="739a0-130">In BizTalk Server, the Windows Workflow Foundation (WF) interceptor will not work with the new WF engine in .NET Framework 4.</span></span> <span data-ttu-id="739a0-131">WF インターセプターは引き続き .NET Framework 3.5 SP2 で動作します。</span><span class="sxs-lookup"><span data-stu-id="739a0-131">The WF interceptor will continue to work in .NET Framework 3.5 SP2.</span></span>  
  
## <a name="windows-communication-foundation-wcf-interceptor"></a><span data-ttu-id="739a0-132">Windows Communication Foundation (WCF) インターセプタ</span><span class="sxs-lookup"><span data-stu-id="739a0-132">Windows Communication Foundation (WCF) Interceptor</span></span>  
 <span data-ttu-id="739a0-133">Windows Communication Foundation インターセプターは、WCF アプリケーションに BAM 追跡機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="739a0-133">The Windows Communication Foundation interceptor provides BAM tracking functionality to your WCF applications.</span></span> <span data-ttu-id="739a0-134">次の機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="739a0-134">It provides the following functionality:</span></span>  
  
-   <span data-ttu-id="739a0-135">コードの変更や再コンパイルを必要とせず、既存の WCF アプリケーションにプラグインするとき。</span><span class="sxs-lookup"><span data-stu-id="739a0-135">Plugs into existing WCF applications without requiring code changes or recompilation.</span></span>  
  
-   <span data-ttu-id="739a0-136">WCF サービス呼び出し内に含まれているメッセージを追跡します。</span><span class="sxs-lookup"><span data-stu-id="739a0-136">Tracks messages contained in WCF service calls.</span></span>  
  
-   <span data-ttu-id="739a0-137">WCF サービス呼び出し内のメッセージから情報を追跡します。</span><span class="sxs-lookup"><span data-stu-id="739a0-137">Tracks information from messages in WCF service calls.</span></span>  
  
-   <span data-ttu-id="739a0-138">トランザクションに参加しているクライアントからフローされた、またはトランザクション サービスの呼び出しを内部的に開始します。</span><span class="sxs-lookup"><span data-stu-id="739a0-138">Participates in transactions flowed from the client or initiated internally for transacted service calls.</span></span>