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
# <a name="measuring-maximum-sustainable-engine-throughput"></a>維持可能な最大のエンジン スループットの測定
BizTalk Server システムを計画する際の主要な検討事項の 1 つとして、システムの維持可能な最大スループット (MST: maximum sustainable throughput) を調べる必要があります。  BizTalk Server システムの MST は、BizTalk システムが実稼働環境で処理を維持できるメッセージ トラフィックの最大負荷として測定されます。 負荷が MST を超えると、メッセージがメッセージ ボックス データベース中のバックログとなり、メッセージ配信に遅延が生じる可能性があるので、MST の測定は重要です。 通常のテストの一環として BizTalk Server システムの MST を算出すると、システムのスケールを調整して、実稼動環境での極端なオーバーロードを避けることができます。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [維持可能な最大パフォーマンスに影響を及ぼす要因](../core/factors-that-affect-maximum-sustainable-performance.md)  
  
-   [エンジンの MST を測定するためのテスト シナリオ](../core/test-scenarios-for-measuring-mst-of-the-engine.md)  
  
-   [エンジンのパフォーマンスをテストする際の推奨事項](../core/recommendations-when-testing-engine-performance.md)