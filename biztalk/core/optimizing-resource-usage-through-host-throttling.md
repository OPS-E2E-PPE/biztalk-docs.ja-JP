---
title: ホスト制限によるリソース使用率の最適化 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- host throttling
- performance, host throttling
ms.assetid: 823b431d-707d-4201-9a6e-4a879e767b66
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8fa30cb66371ef519741658dec47e08f6f92e871
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22263610"
---
# <a name="optimizing-resource-usage-through-host-throttling"></a><span data-ttu-id="694f5-102">ホスト制限によるリソース使用の最適化</span><span class="sxs-lookup"><span data-stu-id="694f5-102">Optimizing Resource Usage Through Host Throttling</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="694f5-103">それぞれのメモリ、ディスク、および BizTalk server と BizTalk Server データベースを含む SQL server で使用できる CPU リソースの重要な部分が使用できる、いくつかの別の Microsoft テクノロジを利用します。</span><span class="sxs-lookup"><span data-stu-id="694f5-103"> makes use of several different Microsoft technologies, each of which can consume a significant portion of the memory, disk, and CPU resources available on the BizTalk server and the SQL server that contains the BizTalk Server databases.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="694f5-104">リソース使用の競合を最小化に使用可能なリソースの使用を管理するためにスロット リング機構を採用しています。</span><span class="sxs-lookup"><span data-stu-id="694f5-104"> employs a throttling mechanism to help manage the use of available resources to minimize resource use contention.</span></span> <span data-ttu-id="694f5-105">このトピックでは、このメカニズムの設計について説明します。</span><span class="sxs-lookup"><span data-stu-id="694f5-105">This topic discusses the design of this mechanism.</span></span> <span data-ttu-id="694f5-106">調整値を調整する方法については、次を参照してください。[設定ダッシュ ボードの BizTalk Server のパフォーマンス チューニング](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md)です。</span><span class="sxs-lookup"><span data-stu-id="694f5-106">For information on how to adjust the throttling values, see [Using Settings Dashboard for BizTalk Server Performance Tuning](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="694f5-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="694f5-107">In This Section</span></span>  
  
-   [<span data-ttu-id="694f5-108">ホストの制限とは?</span><span class="sxs-lookup"><span data-stu-id="694f5-108">What Is Host Throttling?</span></span>](../core/what-is-host-throttling.md)  
  
-   [<span data-ttu-id="694f5-109">BizTalk Server がホスト制限を実装する方法</span><span class="sxs-lookup"><span data-stu-id="694f5-109">How BizTalk Server Implements Host Throttling</span></span>](../core/how-biztalk-server-implements-host-throttling.md)  
  
-   [<span data-ttu-id="694f5-110">ホスト制限パフォーマンス カウンター</span><span class="sxs-lookup"><span data-stu-id="694f5-110">Host Throttling Performance Counters</span></span>](../core/host-throttling-performance-counters.md)  
  
-   [<span data-ttu-id="694f5-111">設計の推奨事項の調整</span><span class="sxs-lookup"><span data-stu-id="694f5-111">Throttling Design Recommendations</span></span>](../core/throttling-design-recommendations.md)