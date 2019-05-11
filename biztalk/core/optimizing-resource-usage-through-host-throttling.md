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
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65262950"
---
# <a name="optimizing-resource-usage-through-host-throttling"></a>ホスト制限によるリソース使用の最適化
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] それぞれのメモリ、ディスク、および BizTalk server と BizTalk Server データベースを含む SQL server で使用できる CPU リソースのかなりの部分を使用できる、いくつかのさまざまな Microsoft テクノロジを利用します。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] リソース使用の競合を最小限に抑えるに使用可能なリソースの使用を管理するために調整メカニズムを採用しています。 このトピックでは、このメカニズムの設計について説明します。 制限値を調整する方法については、次を参照してください。[設定ダッシュ ボードの BizTalk Server のパフォーマンス チューニングを使用して](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md)します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [ホスト制限とは何ですか?](../core/what-is-host-throttling.md)  
  
-   [BizTalk Server のホスト制限の実装方法](../core/how-biztalk-server-implements-host-throttling.md)  
  
-   [ホスト制限パフォーマンス カウンター](../core/host-throttling-performance-counters.md)  
  
-   [制限の設計時の推奨事項](../core/throttling-design-recommendations.md)