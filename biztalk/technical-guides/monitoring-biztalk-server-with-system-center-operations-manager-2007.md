---
title: System Center Operations Manager 2007 での BizTalk Server の監視 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4cee8275-bbd0-435f-ac54-07f582190538
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bdaa0f0639bc640e87ff59e3cee0c229319de4ff
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
ms.locfileid: "26009643"
---
# <a name="monitoring-biztalk-server-with-system-center-operations-manager-2007"></a><span data-ttu-id="c0768-102">System Center Operations Manager 2007 での BizTalk Server の監視</span><span class="sxs-lookup"><span data-stu-id="c0768-102">Monitoring BizTalk Server with System Center Operations Manager 2007</span></span>
<span data-ttu-id="c0768-103">BizTalk アプリケーションと Microsoft System Center Operations Manager (Operations Manager) とインフラストラクチャの監視は、推奨される監視アプローチです。</span><span class="sxs-lookup"><span data-stu-id="c0768-103">Monitoring your BizTalk applications and infrastructure with Microsoft System Center Operations Manager (Operations Manager) is the preferred monitoring approach.</span></span> <span data-ttu-id="c0768-104">Operations Manager 用の Microsoft BizTalk Server 管理パックの提供を実行するコンピューターの監視を主体的および対応[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="c0768-104">The Microsoft BizTalk Server management packs for Operations Manager provide proactive and reactive monitoring of computers running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="c0768-105">これらの管理パックが数十個の包括的かつ自動的に監視できるように、組み込み、カスタマイズ可能な規則を提供[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="c0768-105">These management packs provide dozens of built-in, customizable rules to allow for comprehensive and automated monitoring of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
 <span data-ttu-id="c0768-106">次の BizTalk Server 管理パックは Operations Manager で使用可能です。</span><span class="sxs-lookup"><span data-stu-id="c0768-106">The following BizTalk Server management pack is available for use with Operations Manager:</span></span>  
  
-   <span data-ttu-id="c0768-107">[BizTalk Server 2010 の監視管理パック](ttp://go.microsoft.com/fwlink/?LinkId=210666)(ttp://go.microsoft.com/fwlink/?LinkId=210666)。</span><span class="sxs-lookup"><span data-stu-id="c0768-107">[BizTalk Server 2010 Monitoring Management Pack](ttp://go.microsoft.com/fwlink/?LinkId=210666) (ttp://go.microsoft.com/fwlink/?LinkId=210666).</span></span>  
  
 <span data-ttu-id="c0768-108">操作ガイドのこのセクションには、背景情報については、ベスト プラクティス、チェックリスト、および Operations Manager に基づく監視戦略を実装する際に支援するために使用できる手順が含まれています。</span><span class="sxs-lookup"><span data-stu-id="c0768-108">This section of the operations guide includes background information, best practices, checklists, and procedures that you can use to assist in implementing a monitoring strategy based on Operations Manager.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c0768-109">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="c0768-109">In This Section</span></span>  
  
-   [<span data-ttu-id="c0768-110">Operations Manager 2007 による監視のベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="c0768-110">Best Practices for Monitoring with Operations Manager 2007</span></span>](../technical-guides/best-practices-for-monitoring-with-operations-manager-2007.md)  
  
-   [<span data-ttu-id="c0768-111">パフォーマンスしきい値ルールを使用した調整の監視</span><span class="sxs-lookup"><span data-stu-id="c0768-111">Monitoring Throttling Using Performance Threshold Rules</span></span>](../technical-guides/monitoring-throttling-using-performance-threshold-rules.md)  
  
-   [<span data-ttu-id="c0768-112">SQL Server の監視</span><span class="sxs-lookup"><span data-stu-id="c0768-112">Monitoring SQL Servers</span></span>](../technical-guides/monitoring-sql-servers.md)  
  
-   [<span data-ttu-id="c0768-113">アプリケーションとホスト インスタンスの監視</span><span class="sxs-lookup"><span data-stu-id="c0768-113">Monitoring Applications and Host Instances</span></span>](../technical-guides/monitoring-applications-and-host-instances.md)