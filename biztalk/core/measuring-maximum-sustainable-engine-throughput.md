---
title: 維持可能な最大のエンジン スループットの測定 |Microsoft Docs
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
ms.openlocfilehash: ffbdbb3955a4b595f4a3a0486174f0f3a7005a4d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65325581"
---
# <a name="measuring-maximum-sustainable-engine-throughput"></a><span data-ttu-id="c0db6-102">維持可能な最大のエンジン スループットの測定</span><span class="sxs-lookup"><span data-stu-id="c0db6-102">Measuring Maximum Sustainable Engine Throughput</span></span>
<span data-ttu-id="c0db6-103">BizTalk Server システムを計画する際の主要な検討事項の 1 つとして、システムの維持可能な最大スループット (MST: maximum sustainable throughput) を調べる必要があります。 </span><span class="sxs-lookup"><span data-stu-id="c0db6-103">One of the primary considerations when planning a BizTalk Server system should be to determine the maximum sustainable throughput (MST) of the system.</span></span> <span data-ttu-id="c0db6-104">BizTalk Server システムの MST は、BizTalk システムが実稼働環境で処理を維持できるメッセージ トラフィックの最大負荷として測定されます。</span><span class="sxs-lookup"><span data-stu-id="c0db6-104">The MST of a BizTalk Server system is measured as the highest load of message traffic that the BizTalk system can handle indefinitely in production.</span></span> <span data-ttu-id="c0db6-105">負荷が MST を超えると、メッセージがメッセージ ボックス データベース中のバックログとなり、メッセージ配信に遅延が生じる可能性があるので、MST の測定は重要です。</span><span class="sxs-lookup"><span data-stu-id="c0db6-105">This is important because as load exceeds MST, messages are backlogged in the MessageBox database and message delivery may be delayed.</span></span> <span data-ttu-id="c0db6-106">通常のテストの一環として BizTalk Server システムの MST を算出すると、システムのスケールを調整して、実稼動環境での極端なオーバーロードを避けることができます。</span><span class="sxs-lookup"><span data-stu-id="c0db6-106">If you calculate the MST of your BizTalk Server system as part of normal testing then you can scale your system to avoid extended overload scenarios in production.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c0db6-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="c0db6-107">In This Section</span></span>  
  
-   [<span data-ttu-id="c0db6-108">維持可能な最大パフォーマンスに影響を及ぼす要因</span><span class="sxs-lookup"><span data-stu-id="c0db6-108">Factors that Affect Maximum Sustainable Performance</span></span>](../core/factors-that-affect-maximum-sustainable-performance.md)  
  
-   [<span data-ttu-id="c0db6-109">エンジンの MST を測定するためのテスト シナリオ</span><span class="sxs-lookup"><span data-stu-id="c0db6-109">Test Scenarios for Measuring MST of the Engine</span></span>](../core/test-scenarios-for-measuring-mst-of-the-engine.md)  
  
-   [<span data-ttu-id="c0db6-110">エンジンのパフォーマンスをテストする際の推奨事項</span><span class="sxs-lookup"><span data-stu-id="c0db6-110">Recommendations When Testing Engine Performance</span></span>](../core/recommendations-when-testing-engine-performance.md)