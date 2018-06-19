---
title: 維持可能な最大のエンジン スループットの測定 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- maximum sustainable throughput (MST)
- maximum sustainable throughput (MST), about maximum sustainable throughput (MST)
- performance, maximum sustainable thoughput (MST)
ms.assetid: d83f734f-1a44-4da0-a755-45ba204cadaf
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a5507aca58669ed5c81034ba91e16d1183e07188
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262330"
---
# <a name="measuring-maximum-sustainable-engine-throughput"></a><span data-ttu-id="e3b43-102">維持可能な最大エンジン スループットの測定</span><span class="sxs-lookup"><span data-stu-id="e3b43-102">Measuring Maximum Sustainable Engine Throughput</span></span>
<span data-ttu-id="e3b43-103">BizTalk Server システムを計画する際の主要な検討事項の 1 つとして、システムの維持可能な最大スループット (MST: maximum sustainable throughput) を調べる必要があります。 </span><span class="sxs-lookup"><span data-stu-id="e3b43-103">One of the primary considerations when planning a BizTalk Server system should be to determine the maximum sustainable throughput (MST) of the system.</span></span> <span data-ttu-id="e3b43-104">BizTalk Server システムの MST は、BizTalk システムが実稼働環境で処理を維持できるメッセージ トラフィックの最大負荷として測定されます。</span><span class="sxs-lookup"><span data-stu-id="e3b43-104">The MST of a BizTalk Server system is measured as the highest load of message traffic that the BizTalk system can handle indefinitely in production.</span></span> <span data-ttu-id="e3b43-105">負荷が MST を超えると、メッセージがメッセージ ボックス データベース中のバックログとなり、メッセージ配信に遅延が生じる可能性があるので、MST の測定は重要です。</span><span class="sxs-lookup"><span data-stu-id="e3b43-105">This is important because as load exceeds MST, messages are backlogged in the MessageBox database and message delivery may be delayed.</span></span> <span data-ttu-id="e3b43-106">通常のテストの一環として BizTalk Server システムの MST を算出すると、システムのスケールを調整して、実稼動環境での極端なオーバーロードを避けることができます。</span><span class="sxs-lookup"><span data-stu-id="e3b43-106">If you calculate the MST of your BizTalk Server system as part of normal testing then you can scale your system to avoid extended overload scenarios in production.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e3b43-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="e3b43-107">In This Section</span></span>  
  
-   [<span data-ttu-id="e3b43-108">維持可能な最大のパフォーマンスに影響する要因</span><span class="sxs-lookup"><span data-stu-id="e3b43-108">Factors that Affect Maximum Sustainable Performance</span></span>](../core/factors-that-affect-maximum-sustainable-performance.md)  
  
-   [<span data-ttu-id="e3b43-109">エンジンの MST を測定するためのシナリオをテストします。</span><span class="sxs-lookup"><span data-stu-id="e3b43-109">Test Scenarios for Measuring MST of the Engine</span></span>](../core/test-scenarios-for-measuring-mst-of-the-engine.md)  
  
-   [<span data-ttu-id="e3b43-110">エンジンのパフォーマンスをテストする場合の推奨事項</span><span class="sxs-lookup"><span data-stu-id="e3b43-110">Recommendations When Testing Engine Performance</span></span>](../core/recommendations-when-testing-engine-performance.md)