---
title: BAM インターセプター パフォーマンス カウンター |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b9b64ae1-4d94-4c3c-add1-fa020713be5c
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 989316edff34463905c7547db815b3daaf4d4a46
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22230498"
---
# <a name="bam-interceptor-performance-counters"></a>BAM インターセプタのパフォーマンス カウンタ
パフォーマンス カウンタにより、BAM インターセプタによって実行される作業の特定の側面を監視できます。 パフォーマンス カウンターは、サーバー パフォーマンスに関する問題を特定してトラブルシューティングする際に役立ちます。  
  
 次の表に、BAM インターセプタで利用できるパフォーマンス カウンタを示します。 パフォーマンス カウンタのカテゴリは "BAM インターセプタ" です。  
  
|カウンター|Description|  
|-------------|-----------------|  
|Avg. Failed BAM Events/Flush Avg|プライマリ インポート データベースへのデータ フラッシュ中に発生したエラー BAM イベントの平均数です。|  
|Successful BAM Events/Flush|プライマリ インポート データベースへのデータ フラッシュ中に発生した正常 BAM イベントの平均数です。 トランザクションがロールバックされる場合、これらのイベントはデータベースに保存されないことがあります。|  
|Avg. Extraction sec/BAM Event|BAM イベントの抽出にかかった時間の平均値です。|  
|Avg. Flush sec/BAM Event|BAM イベントのフラッシュにかかった時間の平均値です。|  
|Total Failed BAM Events During Flush|データ フラッシュ中に発生したエラー BAM イベントの合計数です。|  
|Total Successful BAM Events During Flush|プライマリ インポート データベースにフラッシュされた正常 BAM イベントの合計数です。 トランザクションがロールバックされる場合、これらのイベントはデータベースに保存されないことがあります。|  
  
## <a name="see-also"></a>参照  
 [BAM パフォーマンス カウンター](../core/bam-performance-counters.md)