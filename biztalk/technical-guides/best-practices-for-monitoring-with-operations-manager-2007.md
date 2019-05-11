---
title: Operations Manager 2007 で監視するためのベスト プラクティス |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 67a5026c-ef59-498b-9bef-ea0f1c932eae
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: afdc0c4e9d89b83aedf184dc138a3558ef3f5eec
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399312"
---
# <a name="best-practices-for-monitoring-with-operations-manager-2007"></a><span data-ttu-id="25595-102">Operations Manager 2007 で監視するためのベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="25595-102">Best Practices for Monitoring with Operations Manager 2007</span></span>
<span data-ttu-id="25595-103">Operations Manager 2007 を使用してアプリケーションを効果的に監視するには、このトピックに記載のベスト プラクティスに従います。</span><span class="sxs-lookup"><span data-stu-id="25595-103">Adhere to the best practices listed in this topic to effectively monitor your applications using Operations Manager 2007.</span></span>  
  
 <span data-ttu-id="25595-104">**完全なカバレッジの追加の管理パックをインストールします。**</span><span class="sxs-lookup"><span data-stu-id="25595-104">**Install additional management packs for more complete coverage**</span></span>  
  
- <span data-ttu-id="25595-105">Operations Manager 2007 での主要なアプリケーションを監視できるようにする、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境では、次の管理パックをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="25595-105">To help ensure that Operations Manager 2007 monitors the key applications in your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment, you should install the following management packs:</span></span>  
  
  - [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="25595-106">(必須)</span><span class="sxs-lookup"><span data-stu-id="25595-106">(required)</span></span>  
  
  - <span data-ttu-id="25595-107">Windows Server オペレーティング システム (省略可能)</span><span class="sxs-lookup"><span data-stu-id="25595-107">Windows Server Operating System (optional)</span></span>  
  
  - <span data-ttu-id="25595-108">Microsoft Windows Server フェールオーバー クラスター (クラスターが場合に使用される、省略可能)</span><span class="sxs-lookup"><span data-stu-id="25595-108">Microsoft Windows Server Failover Cluster (if clusters are used, optional)</span></span>  
  
  - <span data-ttu-id="25595-109">SQL Server の監視</span><span class="sxs-lookup"><span data-stu-id="25595-109">SQL Server Monitoring</span></span>  
  
  - <span data-ttu-id="25595-110">インターネット インフォメーション サービス 7</span><span class="sxs-lookup"><span data-stu-id="25595-110">Internet Information Services 7</span></span>  
  
  - <span data-ttu-id="25595-111">メッセージ キュー (MSMQ) 5.0 (省略可能)</span><span class="sxs-lookup"><span data-stu-id="25595-111">Message Queuing (MSMQ) 5.0 (optional)</span></span>  
  
  <span data-ttu-id="25595-112">**確認し、日常的にアラートの優先順位を付ける**</span><span class="sxs-lookup"><span data-stu-id="25595-112">**Review and prioritize alerts on a daily basis**</span></span>  
  
- <span data-ttu-id="25595-113">確認して、日常的にアラートの優先順位付けは、適切なタイミングで問題が解決されることを確認するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="25595-113">Reviewing and prioritizing alerts on a daily basis helps to ensure that issues are resolved in a timely manner.</span></span>  
  
  <span data-ttu-id="25595-114">**いることを確認[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]が Operations Manager 2007 サーバーと通信します。**</span><span class="sxs-lookup"><span data-stu-id="25595-114">**Verify that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is communicating with the Operations Manager 2007 server.**</span></span>  
  
- <span data-ttu-id="25595-115">実行しているサーバー間の通信が失敗した場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]と監視のインフラストラクチャでは、アラートが受信できなくします。</span><span class="sxs-lookup"><span data-stu-id="25595-115">If communication fails between the servers running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and the monitoring infrastructure, you will not receive alerts.</span></span>  
  
  <span data-ttu-id="25595-116">**有効にして、必要に応じてルールを無効にします。**</span><span class="sxs-lookup"><span data-stu-id="25595-116">**Enable and disable rules as necessary**</span></span>  
  
- <span data-ttu-id="25595-117">既定のルールの一部で、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理パックが無効になっています。</span><span class="sxs-lookup"><span data-stu-id="25595-117">By default, some of the rules in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] management pack are disabled.</span></span> <span data-ttu-id="25595-118">これらの無効化されたルールは、次の種類: 規則のカスタマイズ、テンプレートとして機能するルールおよび監視のルールを追加しなくて[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]イベント。</span><span class="sxs-lookup"><span data-stu-id="25595-118">These disabled rules are of the following types: rules needing customization, rules that serve as templates, and rules for monitoring additional [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] events.</span></span> <span data-ttu-id="25595-119">確認して、関連するルール[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境が有効にします。</span><span class="sxs-lookup"><span data-stu-id="25595-119">Make sure the relevant rules for your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment are enabled.</span></span>  
  
  <span data-ttu-id="25595-120">**環境内での必要に応じてルールをカスタマイズします。**</span><span class="sxs-lookup"><span data-stu-id="25595-120">**Customize rules as necessary for your environment**</span></span>  
  
- <span data-ttu-id="25595-121">ルールをカスタマイズする必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理パックに合わせて、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]展開します。</span><span class="sxs-lookup"><span data-stu-id="25595-121">You should customize the rules in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] management pack to suit your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] deployment.</span></span> <span data-ttu-id="25595-122">いくつかのルールは、特定のベースの監視のしきい値または時間のしきい値を定義することが必要と[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]展開します。</span><span class="sxs-lookup"><span data-stu-id="25595-122">Some rules require monitoring thresholds or time thresholds that are best defined based on your specific [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] deployment.</span></span>  
  
  <span data-ttu-id="25595-123">**必要に応じて、追加の規則を作成するに含まれるルールに基づいて、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理パック**</span><span class="sxs-lookup"><span data-stu-id="25595-123">**Create additional rules as necessary, based on the rules included in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Management Pack**</span></span>  
  
- <span data-ttu-id="25595-124">など、作成するアイテムのテンプレートとして使用するためのルールが提供されている[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ホスト。</span><span class="sxs-lookup"><span data-stu-id="25595-124">Rules are provided for use as templates for artifacts that you create, such as [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] hosts.</span></span> <span data-ttu-id="25595-125">などの成果物に固有のルールを作成するときに参照としてこれらのテンプレート規則を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="25595-125">You should use these template rules as a reference when creating artifact-specific rules such as:</span></span>  
  
  -   <span data-ttu-id="25595-126">ホストに固有のルールは、たとえば、キューの監視をホストし、調整の監視をホストします。</span><span class="sxs-lookup"><span data-stu-id="25595-126">Host-specific rules, for example, host queue monitoring, and host throttling monitoring</span></span>  
  
  -   <span data-ttu-id="25595-127">メッセージ ボックスに固有のルール</span><span class="sxs-lookup"><span data-stu-id="25595-127">MessageBox-specific rules</span></span>  
  
  -   <span data-ttu-id="25595-128">その他のサード パーティ製コンポーネント、たとえば、MQSeries アダプターの規則</span><span class="sxs-lookup"><span data-stu-id="25595-128">Rules for additional third party components, for example, MQSeries adapter</span></span>  
  
  <span data-ttu-id="25595-129">**すべてを監視、BizTalk Server 関連のコンポーネント**</span><span class="sxs-lookup"><span data-stu-id="25595-129">**Monitor all the BizTalk Server related components**</span></span>  
  
  <span data-ttu-id="25595-130">コンポーネント、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]実行されていることを確認する必要がありますを監視する環境などが、必ずしもに制限はありません。</span><span class="sxs-lookup"><span data-stu-id="25595-130">The components of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment that you should monitor to ensure that they are running include, but are not necessarily limited to:</span></span>  
  
- <span data-ttu-id="25595-131">BizTalk ホスト インスタンス</span><span class="sxs-lookup"><span data-stu-id="25595-131">BizTalk Host instances</span></span>  
  
- [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] <span data-ttu-id="25595-132">インストールされているエージェント ジョブ [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="25595-132">Agent jobs installed with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span></span>  
  
- <span data-ttu-id="25595-133">BizTalk ソリューション用に開発されたカスタム サービス</span><span class="sxs-lookup"><span data-stu-id="25595-133">Any custom services developed for the BizTalk solution</span></span>  
  
- <span data-ttu-id="25595-134">すべてのカスタム データベースの状態は、BizTalk ソリューションの開発</span><span class="sxs-lookup"><span data-stu-id="25595-134">Status of any custom databases developed for the BizTalk solution</span></span>  
  
- <span data-ttu-id="25595-135">関連するすべてのカスタム イベント ログ エントリ、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境</span><span class="sxs-lookup"><span data-stu-id="25595-135">Any custom event log entries relevant to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25595-136">参照</span><span class="sxs-lookup"><span data-stu-id="25595-136">See Also</span></span>  
 [<span data-ttu-id="25595-137">System Center Operations Manager 2007 による BizTalk Server の監視</span><span class="sxs-lookup"><span data-stu-id="25595-137">Monitoring BizTalk Server with System Center Operations Manager 2007</span></span>](../technical-guides/monitoring-biztalk-server-with-system-center-operations-manager-2007.md)