---
title: "ホスト制限によるリソース使用率の最適化 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- host throttling
- performance, host throttling
ms.assetid: 823b431d-707d-4201-9a6e-4a879e767b66
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8fa30cb66371ef519741658dec47e08f6f92e871
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="optimizing-resource-usage-through-host-throttling"></a>ホスト制限によるリソース使用の最適化
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]それぞれのメモリ、ディスク、および BizTalk server と BizTalk Server データベースを含む SQL server で使用できる CPU リソースの重要な部分が使用できる、いくつかの別の Microsoft テクノロジを利用します。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]リソース使用の競合を最小化に使用可能なリソースの使用を管理するためにスロット リング機構を採用しています。 このトピックでは、このメカニズムの設計について説明します。 調整値を調整する方法については、次を参照してください。[設定ダッシュ ボードの BizTalk Server のパフォーマンス チューニング](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md)です。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [ホストの制限とは?](../core/what-is-host-throttling.md)  
  
-   [BizTalk Server がホスト制限を実装する方法](../core/how-biztalk-server-implements-host-throttling.md)  
  
-   [ホスト制限パフォーマンス カウンター](../core/host-throttling-performance-counters.md)  
  
-   [設計の推奨事項の調整](../core/throttling-design-recommendations.md)