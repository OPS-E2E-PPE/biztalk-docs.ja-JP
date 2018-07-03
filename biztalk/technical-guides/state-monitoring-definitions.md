---
title: 状態監視の定義 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: aa2c8247-5e25-4624-9f0d-c7fe621ffba2
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 95a15bc55bce7c39bdae67e04ff0a323776a180a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011683"
---
# <a name="state-monitoring-definitions"></a><span data-ttu-id="90b23-102">状態監視の定義</span><span class="sxs-lookup"><span data-stu-id="90b23-102">State Monitoring Definitions</span></span>
<span data-ttu-id="90b23-103">状態監視は、監視対象のコンピューターが特定のアプリケーションの観点から特定の時点で正常な状態でかどうかを質問の回答に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="90b23-103">State monitoring helps answer the question of whether a monitored computer is healthy at a given time from the perspective of a particular application.</span></span> <span data-ttu-id="90b23-104">System Center Operations Manager (SCOM) をユーザーに公開されている別のマネージ エンティティの状態を更新し、状態監視ビューの一部として状態を表示します。</span><span class="sxs-lookup"><span data-stu-id="90b23-104">System Center Operations Manager (SCOM) updates the status of different managed entities exposed to the user and presents the status as part of the state monitoring view.</span></span>  
  
 <span data-ttu-id="90b23-105">理解しておく、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]状態の監視の表示、SCOM の状態監視の背後にある概念を理解する必要があります。</span><span class="sxs-lookup"><span data-stu-id="90b23-105">To understand the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] State Monitoring view, you must understand the concepts behind SCOM state monitoring.</span></span> <span data-ttu-id="90b23-106">状態監視の主要なコンポーネントについて説明するために、次の用語を使用します。</span><span class="sxs-lookup"><span data-stu-id="90b23-106">The following terminology is used to describe the key components of state monitoring:</span></span>  
  
- <span data-ttu-id="90b23-107">**ロール**-サービス探索によって特定された環境で、サーバーが実行するロール。</span><span class="sxs-lookup"><span data-stu-id="90b23-107">**Role** - A role that a server is performing in an environment as determined by service discovery.</span></span> <span data-ttu-id="90b23-108">たとえば、BizTalk の実行時ロールには、ランタイムの成果物と BizTalk Server のインスタンスがカプセル化します。</span><span class="sxs-lookup"><span data-stu-id="90b23-108">For example, the BizTalk run-time role encapsulates the runtime artifacts and instances in BizTalk Server.</span></span>  
  
- <span data-ttu-id="90b23-109">**コンポーネント**-サーバー ロールの全体的な正常性を測定するヘルス ロールアップの一部として使用されるサブ ロール。</span><span class="sxs-lookup"><span data-stu-id="90b23-109">**Component** - A sub-role that is used as part of the health roll-up to measure the overall health of the server role.</span></span> <span data-ttu-id="90b23-110">たとえば、BAM 警告のコンポーネントは、全体的な正常性の状態を示すアラートを生成する使用されます。</span><span class="sxs-lookup"><span data-stu-id="90b23-110">For example, the BAM alert component is used to generate alerts to indicate the status of overall health.</span></span>  
  
- <span data-ttu-id="90b23-111">**インスタンス**-特定のコンピューターがサーバー ロールのインスタンスをホストできます。</span><span class="sxs-lookup"><span data-stu-id="90b23-111">**Instance** - A particular computer may host instance(s) of the server role.</span></span>  
  
  <span data-ttu-id="90b23-112">簡単に言うと、次の点が SCOM の状態監視の重要な原則となります。</span><span class="sxs-lookup"><span data-stu-id="90b23-112">In brief, the following are the important principles of SCOM state monitoring:</span></span>  
  
- <span data-ttu-id="90b23-113">コンピューター グループの正常性は、コンピューター グループに含まれるコンピューターのヘルスから派生します。</span><span class="sxs-lookup"><span data-stu-id="90b23-113">Health of a computer group is derived from the health of the computers that are contained in the computer group.</span></span>  
  
- <span data-ttu-id="90b23-114">コンピューターの状態は、コンピューター上で実行中の (サーバー ロールと呼ばれる) アプリケーションが正常な状態であるかどうか、および稼働状況がホストされているアプリケーションの稼働状況から派生しているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="90b23-114">The status of the computer shows whether applications (referred as server roles) running on the computer are healthy, and the health is derived from the health of the hosted applications.</span></span>  
  
- <span data-ttu-id="90b23-115">アプリケーション レベル (サーバー ロール) では、サーバー ロールの状態は、そのサーバー ロールのすべてのアプリケーション インスタンスの全体の状態になります。</span><span class="sxs-lookup"><span data-stu-id="90b23-115">At the application level (server role), the status of the server role is the overall status of all application instances of that server role.</span></span> <span data-ttu-id="90b23-116">たとえば、オーケストレーションなどの 1 つまたは複数の成果物の正常性は受信場所、ポートを受信しなどの状態と BizTalk アプリケーションの全体的な正常性に影響します。</span><span class="sxs-lookup"><span data-stu-id="90b23-116">For example, health of one or more artifacts like orchestrations, receives locations, receives ports and so on affects the status and overall health of a BizTalk application.</span></span>  
  
- <span data-ttu-id="90b23-117">アプリケーション インスタンス レベル (サーバーの役割インスタンス) では、アプリケーション インスタンスの正常性は (コンポーネントと呼ばれます) のアプリケーション インスタンスのさまざまな領域の正常性から派生します。</span><span class="sxs-lookup"><span data-stu-id="90b23-117">At the application instance level (server role instance), the health of the application instance is derived from the health of different areas of the application instance (known as components).</span></span>  
  
- <span data-ttu-id="90b23-118">SCOM 警告は、コンポーネントの稼働状況に関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="90b23-118">SCOM alerts are associated with the health of a component.</span></span> <span data-ttu-id="90b23-119">コンポーネントの状態は、全体の稼働状況を示す警告がトリガーされると、赤、黄色、または緑に設定されます。</span><span class="sxs-lookup"><span data-stu-id="90b23-119">Status of a component is set to red, yellow, or green when alerts are triggered to indicate overall health.</span></span>  
  
- <span data-ttu-id="90b23-120">コンポーネントの稼働状況は、サーバー ロールの稼働状況に影響を与えます。</span><span class="sxs-lookup"><span data-stu-id="90b23-120">Health of a component contributes to the health of the server role.</span></span>  
  
  <span data-ttu-id="90b23-121">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="90b23-121">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span></span>  
  
- <span data-ttu-id="90b23-122">各 BizTalk Server では、BizTalk Server ロールのインスタンスと見なされます。</span><span class="sxs-lookup"><span data-stu-id="90b23-122">Each BizTalk Server is considered an instance of the BizTalk Server role.</span></span>  
  
- <span data-ttu-id="90b23-123">このため、コンピューターの BizTalk Server ロールは、そのコンピューターのすべての BizTalk Server プロセスのすべてのイベント/アクティビティの結果として計算されます。</span><span class="sxs-lookup"><span data-stu-id="90b23-123">The BizTalk Server role in a computer will therefore be computed as a result of all events/activities of all the BizTalk Server processes in that computer.</span></span>  
  
  <span data-ttu-id="90b23-124">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を含む BizTalk Server アイテムの状態監視管理パックには</span><span class="sxs-lookup"><span data-stu-id="90b23-124">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Management Pack provides state monitoring for BizTalk Server artifacts which includes</span></span>  
  
- <span data-ttu-id="90b23-125">オーケストレーションなどのアプリケーション アイテム。</span><span class="sxs-lookup"><span data-stu-id="90b23-125">Application artifacts such as orchestrations.</span></span> <span data-ttu-id="90b23-126">メッセージング コンポーネントなどの受信ポート、受信場所、および送信ポート。</span><span class="sxs-lookup"><span data-stu-id="90b23-126">Messaging components such as receive ports, receive locations, and send ports.</span></span>  
  
- <span data-ttu-id="90b23-127">サーバーなど、展開の成果物は、これに SSO のインスタンスをホストします。</span><span class="sxs-lookup"><span data-stu-id="90b23-127">Deployment artifacts such as servers, host instances, SSO and so on.</span></span>  
  
  <span data-ttu-id="90b23-128">次の表では、視覚的にすべて BizTalk Server プラットフォームとアプリケーション レベル アーティファクトの正常性状態を表す 3 つの状態を示します。</span><span class="sxs-lookup"><span data-stu-id="90b23-128">The following table lists the three states that visually represent the health status of all BizTalk Server platform and application level artifacts.</span></span> <span data-ttu-id="90b23-129">これにより、重要な問題をすばやく特定するのに役立つマルチサーバー展開の高レベルのビューが SCOM オペレーターに提供されます。</span><span class="sxs-lookup"><span data-stu-id="90b23-129">This provides the SCOM operator a high-level view of a multi-server deployment in order to focus on important problems quickly.</span></span>  
  
|<span data-ttu-id="90b23-130">成果物</span><span class="sxs-lookup"><span data-stu-id="90b23-130">Artifacts</span></span>|<span data-ttu-id="90b23-131">[緑]</span><span class="sxs-lookup"><span data-stu-id="90b23-131">Green</span></span>|<span data-ttu-id="90b23-132">黄</span><span class="sxs-lookup"><span data-stu-id="90b23-132">Yellow</span></span>|<span data-ttu-id="90b23-133">[赤]</span><span class="sxs-lookup"><span data-stu-id="90b23-133">Red</span></span>|  
|---------------|-----------|------------|---------|  
|<span data-ttu-id="90b23-134">アプリケーション レベルのアイテム</span><span class="sxs-lookup"><span data-stu-id="90b23-134">Application level artifacts</span></span>|<span data-ttu-id="90b23-135">実行中の状態です。</span><span class="sxs-lookup"><span data-stu-id="90b23-135">Are in a running state.</span></span>|<span data-ttu-id="90b23-136">インスタンスの 70% 未満に問題が発生します。</span><span class="sxs-lookup"><span data-stu-id="90b23-136">Less than 70% of the   instances are faulted.</span></span>|<span data-ttu-id="90b23-137">エラーが発生したまたは重大なエラーが発生しましたが、インスタンスの 70% を超えるします。</span><span class="sxs-lookup"><span data-stu-id="90b23-137">More than 70% of the instances are faulted or have resulted in critical errors.</span></span>|  
|<span data-ttu-id="90b23-138">展開レベルの成果物</span><span class="sxs-lookup"><span data-stu-id="90b23-138">Deployment level artifacts</span></span>|<span data-ttu-id="90b23-139">実行中の状態です。</span><span class="sxs-lookup"><span data-stu-id="90b23-139">Are in a running state.</span></span>|<span data-ttu-id="90b23-140">適用なし</span><span class="sxs-lookup"><span data-stu-id="90b23-140">Not applicable</span></span>|<span data-ttu-id="90b23-141">実行中の状態ではないか、停止しています。</span><span class="sxs-lookup"><span data-stu-id="90b23-141">Are not in a running state or have stopped.</span></span>|