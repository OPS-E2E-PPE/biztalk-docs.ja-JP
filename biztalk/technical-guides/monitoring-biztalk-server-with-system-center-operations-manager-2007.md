---
title: System Center Operations Manager 2007 による BizTalk Server の監視 |Microsoft Docs
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
ms.openlocfilehash: f8005fa8287b7156374445b1a596a2c4bc21709c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65379481"
---
# <a name="monitoring-biztalk-server-with-system-center-operations-manager-2007"></a><span data-ttu-id="7af1e-102">System Center Operations Manager 2007 による BizTalk Server の監視</span><span class="sxs-lookup"><span data-stu-id="7af1e-102">Monitoring BizTalk Server with System Center Operations Manager 2007</span></span>
<span data-ttu-id="7af1e-103">BizTalk アプリケーションと Microsoft System Center Operations Manager (Operations Manager) でインフラストラクチャの監視は、推奨される監視アプローチです。</span><span class="sxs-lookup"><span data-stu-id="7af1e-103">Monitoring your BizTalk applications and infrastructure with Microsoft System Center Operations Manager (Operations Manager) is the preferred monitoring approach.</span></span> <span data-ttu-id="7af1e-104">Operations Manager 用の Microsoft BizTalk Server 管理パックの提供を実行するコンピューターの監視を主体的かつ[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="7af1e-104">The Microsoft BizTalk Server management packs for Operations Manager provide proactive and reactive monitoring of computers running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="7af1e-105">これらの管理パックの提供を包括的な自動監視を許可するルールを組み込み、カスタマイズ可能な多数の[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="7af1e-105">These management packs provide dozens of built-in, customizable rules to allow for comprehensive and automated monitoring of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
 <span data-ttu-id="7af1e-106">次の BizTalk Server 管理パックは Operations Manager で使用できます。</span><span class="sxs-lookup"><span data-stu-id="7af1e-106">The following BizTalk Server management pack is available for use with Operations Manager:</span></span>  
  
- <span data-ttu-id="7af1e-107">[BizTalk Server 2010 の監視管理パック](ttp://go.microsoft.com/fwlink/?LinkId=210666)(ttp://go.microsoft.com/fwlink/?LinkId=210666)。</span><span class="sxs-lookup"><span data-stu-id="7af1e-107">[BizTalk Server 2010 Monitoring Management Pack](ttp://go.microsoft.com/fwlink/?LinkId=210666) (ttp://go.microsoft.com/fwlink/?LinkId=210666).</span></span>  
  
  <span data-ttu-id="7af1e-108">操作ガイドのこのセクションには、背景情報については、ベスト プラクティス、チェックリスト、および Operations Manager に基づく監視戦略の実装で支援するために使用できる手順が含まれています。</span><span class="sxs-lookup"><span data-stu-id="7af1e-108">This section of the operations guide includes background information, best practices, checklists, and procedures that you can use to assist in implementing a monitoring strategy based on Operations Manager.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7af1e-109">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="7af1e-109">In This Section</span></span>  
  
-   [<span data-ttu-id="7af1e-110">Operations Manager 2007 による監視のベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="7af1e-110">Best Practices for Monitoring with Operations Manager 2007</span></span>](../technical-guides/best-practices-for-monitoring-with-operations-manager-2007.md)  
  
-   [<span data-ttu-id="7af1e-111">パフォーマンスしきい値ルールを使用した調整の監視</span><span class="sxs-lookup"><span data-stu-id="7af1e-111">Monitoring Throttling Using Performance Threshold Rules</span></span>](../technical-guides/monitoring-throttling-using-performance-threshold-rules.md)  
  
-   [<span data-ttu-id="7af1e-112">SQL Server の監視</span><span class="sxs-lookup"><span data-stu-id="7af1e-112">Monitoring SQL Servers</span></span>](../technical-guides/monitoring-sql-servers.md)  
  
-   [<span data-ttu-id="7af1e-113">アプリケーションとホスト インスタンスの監視</span><span class="sxs-lookup"><span data-stu-id="7af1e-113">Monitoring Applications and Host Instances</span></span>](../technical-guides/monitoring-applications-and-host-instances.md)