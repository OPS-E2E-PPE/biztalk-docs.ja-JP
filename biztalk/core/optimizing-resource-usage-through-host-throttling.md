---
title: ホスト制限によるリソース使用率の最適化 |Microsoft Docs
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
ms.openlocfilehash: e1ada7b36453945b676db8aa897d7e0e862d3907
ms.sourcegitcommit: ec7013f5ddcd2da4291ae29ac28f965d89aa277a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/16/2019
ms.locfileid: "22263610"
---
# <a name="optimizing-resource-usage-through-host-throttling"></a><span data-ttu-id="d4f84-102">ホスト制限によるリソース使用の最適化</span><span class="sxs-lookup"><span data-stu-id="d4f84-102">Optimizing Resource Usage Through Host Throttling</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="d4f84-103">それぞれのメモリ、ディスク、および BizTalk server と BizTalk Server データベースを含む SQL server で使用できる CPU リソースのかなりの部分を使用できる、いくつかのさまざまな Microsoft テクノロジを利用します。</span><span class="sxs-lookup"><span data-stu-id="d4f84-103">makes use of several different Microsoft technologies, each of which can consume a significant portion of the memory, disk, and CPU resources available on the BizTalk server and the SQL server that contains the BizTalk Server databases.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="d4f84-104">リソース使用の競合を最小限に抑えるに使用可能なリソースの使用を管理するために調整メカニズムを採用しています。</span><span class="sxs-lookup"><span data-stu-id="d4f84-104">employs a throttling mechanism to help manage the use of available resources to minimize resource use contention.</span></span> <span data-ttu-id="d4f84-105">このトピックでは、このメカニズムの設計について説明します。</span><span class="sxs-lookup"><span data-stu-id="d4f84-105">This topic discusses the design of this mechanism.</span></span> <span data-ttu-id="d4f84-106">制限値を調整する方法については、次を参照してください。[設定ダッシュ ボードの BizTalk Server のパフォーマンス チューニングを使用して](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md)します。</span><span class="sxs-lookup"><span data-stu-id="d4f84-106">For information on how to adjust the throttling values, see [Using Settings Dashboard for BizTalk Server Performance Tuning](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d4f84-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="d4f84-107">In This Section</span></span>  
  
-   [<span data-ttu-id="d4f84-108">ホスト制限とは何ですか?</span><span class="sxs-lookup"><span data-stu-id="d4f84-108">What Is Host Throttling?</span></span>](../core/what-is-host-throttling.md)  
  
-   [<span data-ttu-id="d4f84-109">BizTalk Server のホスト制限の実装方法</span><span class="sxs-lookup"><span data-stu-id="d4f84-109">How BizTalk Server Implements Host Throttling</span></span>](../core/how-biztalk-server-implements-host-throttling.md)  
  
-   [<span data-ttu-id="d4f84-110">ホスト制限パフォーマンス カウンター</span><span class="sxs-lookup"><span data-stu-id="d4f84-110">Host Throttling Performance Counters</span></span>](../core/host-throttling-performance-counters.md)  
  
-   [<span data-ttu-id="d4f84-111">制限の設計時の推奨事項</span><span class="sxs-lookup"><span data-stu-id="d4f84-111">Throttling Design Recommendations</span></span>](../core/throttling-design-recommendations.md)