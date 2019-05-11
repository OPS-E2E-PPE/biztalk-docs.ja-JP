---
title: クエリ、リアルタイム集計データ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- queries [BAM], real-time data
- BAM, real-time data
ms.assetid: f60a34a1-ac64-47c7-8f83-1bc301170590
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 72ee6612fc99d9411f0fb26c91c5d8ad6041edf1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398291"
---
# <a name="querying-real-time-aggregated-data"></a>リアルタイム集計データに対するクエリの実行
リアルタイム集計 (RTA) データは、BAM プライマリ インポート データベースに動的に作成された SQL ビューにクエリで使用できます。  
  
 クエリでのビューの名前は次のようになります。  
  
 **bam_\<** *ViewName* **\>_\<** *RTAName* **\>_RTAView**  
  
 場所  
  
 **\<** *ViewName* **\>** は、BAM 定義 XML 内の View 要素の Name 属性、関連する Microsoft Excel ウィザードに入力されたビューの名前と同じです。  
  
 **\<** *RTAName* **\>** BAM で固有に生成される BAM 定義 XML 内の RealTimeAggregation 要素の Name 属性に基づいてビューの名前。  
  
 リアルタイム集計データを照会するときに、次の条件を確認する必要があります。  
  
-   一定の期間 (既定値は 1 日) の集計を保持することはありませんが非常に大きくと、リアルタイム集計を構成する必要があります。 古い集計は、代わりに、OLAP キューブで使用可能なにする必要があります。  
  
-   RTA に対するクエリは、RTA データ用のオンライン時間帯内となる時間ディメンションでフィルター処理を含める必要があります。 これは、BAM データを実行するためのチャンク単位で、データをドロップする BAM でのタイムスタンプに基づく Rta のメンテナンスは最適化されています。 したがって TRANSACT-SQL コマンドを単純に送信する場合は、"`select *`"、結果に予期しない影響が及びます。  
  
-   DirectEventStream を使用して bam アクティビティ データを送信する場合は、リアルタイム集計データには、待機時間がありません: 即座に認識と呼び出し元のアプリケーションでトランザクションがコミットされます。  
  
-   BufferedEventStream を使用して bam アクティビティ データを送信する場合、RTA データ表示されますクエリの数秒後、BAM イベント バス サービスと、BAM プライマリ インポート データベースをホストする SQL server の負荷によって異なります。  
  
-   BAM では、変更または挿入トリガーを使用してアクティビティ データ ストレージ レコードとの同期に保持されているテーブルでリアルタイムの集計を行います。 詳細については、次を参照してください。[アクティビティ データのストレージ](../core/activity-data-storage.md)します。 そのため、リアルタイム集計では、パフォーマンスに大きな影響をことができます。 詳細については、次を参照してください。[リアルタイム集計](../core/real-time-aggregations.md)します。  
  
## <a name="see-also"></a>参照  
 [スケジュールされたクエリを実行する集計データ](../core/querying-scheduled-aggregated-data.md)   
 [BAM データのクエリ](../core/querying-bam-data.md)