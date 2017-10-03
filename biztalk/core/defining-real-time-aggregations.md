---
title: "リアルタイム集計の定義 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- real-time data, aggregating
- aggregations [BAM], real-time data
ms.assetid: cb3d7124-1663-4af2-9540-4171cc51568a
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b2b2df32149f67a002a5a6281b6f1abd848523a6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="defining-real-time-aggregations"></a>リアルタイム集計の定義
場合によっては、多次元集計の特定のスライスはので時間を区別することをリアルタイムで使用することです。 たとえば、生鮮食料品を販売する業者では、配送の各段階での製品数量の集計をリアルタイムで利用できるようにする必要があります。 同時に、代表的な顧客の年齢などの他の集計を、ビジネス インテリジェンス分析のために月末にのみ実行する必要がある場合もあります。  
  
-   使用して、**ピボット テーブル**ツールバーで、該当する場合は、リアルタイム集計 (RTA) として選択した PivotTable をマークします。 ピボットテーブルに格納されたデータの種類によって、データをリアルタイムで表示する必要があるかどうかが決まります。 たとえば、1 時間ごとに Web 注文を追跡するレポートであればリアルタイムで表示する必要がありますが、1 日の販売総数を追跡するレポートであればリアルタイムで表示する必要はありません。  
  
     ![](../core/media/ebiz-sdk-sample-bam12.gif "ebiz_sdk_sample_bam12")  
[RTA] ボタン  
  
> [!IMPORTANT]
>  同じ BAM アクティビティを使用する RTA を複数定義しないでください。 そのような RTA を複数定義した場合、BAM データをアーカイブしたときに RTA データが不正確になります。  
  
 ピボットテーブルの詳細については、Excel のオンライン ヘルプを参照してください。 ピボットテーブルを作成すると、ライブ BAM データを表示できます。  
  
## <a name="see-also"></a>参照  
 [ライブ BAM データの表示](../core/viewing-live-bam-data.md)   
 [進捗ディメンション](../core/progress-dimension.md)   
 [データ ディメンション](../core/data-dimension.md)   
 [時間ディメンション](../core/time-dimension.md)   
 [数値範囲ディメンション](../core/numeric-range-dimension.md)   
 [ディメンションの定義](../core/defining-dimensions.md)