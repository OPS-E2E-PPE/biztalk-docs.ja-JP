---
title: "集計データをリアルタイムに照会 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- queries [BAM], real-time data
- BAM, real-time data
ms.assetid: f60a34a1-ac64-47c7-8f83-1bc301170590
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2b71c3adbcbe5aaaea4d9fa4bf25b2aa4191c580
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="querying-real-time-aggregated-data"></a>リアルタイム集計データに対するクエリの実行
BAM プライマリ インポート データベースで動的に作成された SQL ビューでは、リアルタイム集計 (RTA) データに対してクエリを実行できます。  
  
 クエリでのビューの名前は次のようになります。  
  
 **bam _\<**  *ViewName*  **\>_\<**  *RTAName*  **\>_RTAView**  
  
 場所  
  
 **\<***ViewName*  **\>**  BAM 定義 XML 内の View 要素の Name 属性は、関連する Microsoft Excel ウィザードに入力されたビュー名と同じです。  
  
 **\<***RTAName*  **\>** は一意である BAM が生成される BAM 定義 XML 内の RealTimeAggregation 要素の Name 属性に基づいて、ビュー名。  
  
 リアルタイム集計データに対してクエリを実行する際は、次の条件に特に注意してください。  
  
-   特定の期間 (既定では 1 日) にわたって集計を継続するようにリアルタイム集計を設定する必要がありますが、データ量が増えすぎないようにします。 また、OLAP キューブ内で古い集計データが利用可能になっている必要があります。  
  
-   RTA に対するクエリでは、RTA データ用のオンライン ウィンドウに表示される時間ディメンションに関してフィルター処理を行う必要があります。 これは、BAM では RTA のデータ保守が BAM データのタイムスタンプに基づいて行われ、最適化されてチャンク内のデータが削除されるためです。 したがって、Transact-SQL コマンド "`select *`" を送信するだけでは、結果が予期せず変動する場合があります。  
  
-   DirectEventStream を使用してアクティビティ データを BAM に送信する場合、リアルタイム集計データは、呼び出し元アプリケーションのトランザクションが実行されると直ちに表示され、待機時間がありません。  
  
-   BufferedEventStream を使用してアクティビティ データを BAM に送信する場合、RTA データは数秒後にクエリとして表示されます。待機時間は、BAM Event Bus サービスと、BAM プライマリ インポート データベースをホストする SQL サーバーの負荷によって異なります。  
  
-   BAM では、トリガーを使用してアクティビティ データ ストレージ レコードの変更や挿入に関する同期が行われているテーブルに基づいて、リアルタイムの集計を行います。 詳細については、次を参照してください。[アクティビティ データのストレージ](../core/activity-data-storage.md)です。 リアルタイム集計はパフォーマンスに大きな影響を与える可能性があります。 詳細については、次を参照してください。[リアルタイム集計](../core/real-time-aggregations.md)です。  
  
## <a name="see-also"></a>参照  
 [スケジュールされているクエリを実行する集計データ](../core/querying-scheduled-aggregated-data.md)   
 [BAM データのクエリ](../core/querying-bam-data.md)