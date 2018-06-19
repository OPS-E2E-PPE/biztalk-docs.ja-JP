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
# <a name="measuring-maximum-sustainable-engine-throughput"></a>維持可能な最大エンジン スループットの測定
BizTalk Server システムを計画する際の主要な検討事項の 1 つとして、システムの維持可能な最大スループット (MST: maximum sustainable throughput) を調べる必要があります。  BizTalk Server システムの MST は、BizTalk システムが実稼働環境で処理を維持できるメッセージ トラフィックの最大負荷として測定されます。 負荷が MST を超えると、メッセージがメッセージ ボックス データベース中のバックログとなり、メッセージ配信に遅延が生じる可能性があるので、MST の測定は重要です。 通常のテストの一環として BizTalk Server システムの MST を算出すると、システムのスケールを調整して、実稼動環境での極端なオーバーロードを避けることができます。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [維持可能な最大のパフォーマンスに影響する要因](../core/factors-that-affect-maximum-sustainable-performance.md)  
  
-   [エンジンの MST を測定するためのシナリオをテストします。](../core/test-scenarios-for-measuring-mst-of-the-engine.md)  
  
-   [エンジンのパフォーマンスをテストする場合の推奨事項](../core/recommendations-when-testing-engine-performance.md)