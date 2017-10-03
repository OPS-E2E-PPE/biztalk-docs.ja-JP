---
title: "System Center Operations Manager 2007 での BizTalk Server の監視 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4cee8275-bbd0-435f-ac54-07f582190538
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 06ebfbc9f895525b44174c0e947f5700d54b324f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="monitoring-biztalk-server-with-system-center-operations-manager-2007"></a><span data-ttu-id="1a183-102">System Center Operations Manager 2007 での BizTalk Server の監視</span><span class="sxs-lookup"><span data-stu-id="1a183-102">Monitoring BizTalk Server with System Center Operations Manager 2007</span></span>
<span data-ttu-id="1a183-103">BizTalk アプリケーションと Microsoft System Center Operations Manager (Operations Manager) とインフラストラクチャの監視は、推奨される監視アプローチです。</span><span class="sxs-lookup"><span data-stu-id="1a183-103">Monitoring your BizTalk applications and infrastructure with Microsoft System Center Operations Manager (Operations Manager) is the preferred monitoring approach.</span></span> <span data-ttu-id="1a183-104">Microsoft [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] Operations Manager 用管理パックを主体的および対応が実行しているコンピューターの監視提供[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="1a183-104">The Microsoft [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] management packs for Operations Manager provide proactive and reactive monitoring of computers running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="1a183-105">これらの管理パックが数十個の包括的かつ自動的に監視できるように、組み込み、カスタマイズ可能な規則を提供[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="1a183-105">These management packs provide dozens of built-in, customizable rules to allow for comprehensive and automated monitoring of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
 <span data-ttu-id="1a183-106">次の BizTalk Server 管理パックは Operations Manager で使用可能です。</span><span class="sxs-lookup"><span data-stu-id="1a183-106">The following BizTalk Server management pack is available for use with Operations Manager:</span></span>  
  
-   <span data-ttu-id="1a183-107">[BizTalk Server 2010 の監視管理パック](ttp://go.microsoft.com/fwlink/?LinkId=210666)(ttp://go.microsoft.com/fwlink/?LinkId=210666)。</span><span class="sxs-lookup"><span data-stu-id="1a183-107">[BizTalk Server 2010 Monitoring Management Pack](ttp://go.microsoft.com/fwlink/?LinkId=210666) (ttp://go.microsoft.com/fwlink/?LinkId=210666).</span></span>  
  
 <span data-ttu-id="1a183-108">操作ガイドのこのセクションには、背景情報については、ベスト プラクティス、チェックリスト、および Operations Manager に基づく監視戦略を実装する際に支援するために使用できる手順が含まれています。</span><span class="sxs-lookup"><span data-stu-id="1a183-108">This section of the operations guide includes background information, best practices, checklists, and procedures that you can use to assist in implementing a monitoring strategy based on Operations Manager.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1a183-109">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="1a183-109">In This Section</span></span>  
  
-   [<span data-ttu-id="1a183-110">Operations Manager 2007 で監視のベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="1a183-110">Best Practices for Monitoring with Operations Manager 2007</span></span>](../technical-guides/best-practices-for-monitoring-with-operations-manager-2007.md)  
  
-   [<span data-ttu-id="1a183-111">パフォーマンスしきい値ルールの調整の監視</span><span class="sxs-lookup"><span data-stu-id="1a183-111">Monitoring Throttling Using Performance Threshold Rules</span></span>](../technical-guides/monitoring-throttling-using-performance-threshold-rules.md)  
  
-   [<span data-ttu-id="1a183-112">SQL サーバーの監視</span><span class="sxs-lookup"><span data-stu-id="1a183-112">Monitoring SQL Servers</span></span>](../technical-guides/monitoring-sql-servers.md)  
  
-   [<span data-ttu-id="1a183-113">アプリケーションとホスト インスタンスの監視</span><span class="sxs-lookup"><span data-stu-id="1a183-113">Monitoring Applications and Host Instances</span></span>](../technical-guides/monitoring-applications-and-host-instances.md)