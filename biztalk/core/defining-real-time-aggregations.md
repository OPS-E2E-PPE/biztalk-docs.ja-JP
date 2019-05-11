---
title: リアルタイム集計の定義 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- real-time data, aggregating
- aggregations [BAM], real-time data
ms.assetid: cb3d7124-1663-4af2-9540-4171cc51568a
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4b585ba7f07ba6cd0f36a3fe2e68b92c50f4e206
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389699"
---
# <a name="defining-real-time-aggregations"></a>リアルタイム集計の定義
場合によっては、多次元集計の特定のスライスは時間を区別するためにリアルタイムで使用できるようにします。 たとえば、使い捨ての製品を販売しているお客様のビジネスとをリアルタイムで使用できる配信のさまざまな段階での製品の数量の集計します。 同時に、必要なその他の集計、年齢などの一般的な顧客がビジネス インテリジェンス分析の月の最後にのみです。  
  
-   使用して、**ピボット テーブル**ツールバーで、該当する場合は、リアルタイム集計 (RTA) として選択したピボット テーブルをマークします。 ピボット テーブルに含まれるデータの種類には、リアルタイムで表示する必要があるかどうかが決まります。 たとえば、Web 注文を 1 時間ごとに追跡するレポートは、毎日の売上合計を追跡するレポートをリアルタイムで表示しない場合は、リアルタイムで表示する必要があります。  
  
     ![](../core/media/ebiz-sdk-sample-bam12.gif "ebiz_sdk_sample_bam12")  
RTA ボタン  
  
> [!IMPORTANT]
>  同じ BAM アクティビティを使用する RTA を複数定義しないでください。 そのような RTA を複数定義した場合、BAM データをアーカイブしたときに RTA データが不正確になります。  
  
 ピボット テーブルの詳細については、Excel のオンライン ヘルプを参照してください。 ピボット テーブルを作成した後は、ライブ BAM データを表示できます。  
  
## <a name="see-also"></a>参照  
 [ライブ BAM データの表示](../core/viewing-live-bam-data.md)   
 [進捗ディメンション](../core/progress-dimension.md)   
 [データ ディメンション](../core/data-dimension.md)   
 [時間ディメンション](../core/time-dimension.md)   
 [数値範囲ディメンション](../core/numeric-range-dimension.md)   
 [ディメンションの定義](../core/defining-dimensions.md)