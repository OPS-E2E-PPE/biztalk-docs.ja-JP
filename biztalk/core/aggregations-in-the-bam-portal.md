---
title: BAM ポータルでの集計 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BAM portal, pivot tables
- BAM, data analysis
- pivot tables [BAM portal]
- BAM portal, charts
- data, analysis [BAM]
- data, OLAP cubes
- aggregations [BAM], BAM portal
- charts, BAM portal
- BAM portal, aggregations
ms.assetid: 1c689563-714b-4573-9c18-a5b0efe97fb8
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 14496535f12171be1d391ebe88312a9730c36953
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36986947"
---
# <a name="aggregations-in-the-bam-portal"></a>BAM ポータルでの集計
集計とは、OLAP キューブで分析処理を行う際に使用できる事前計算されたデータのテーブルです。 集計を使用すると、多次元データベースを効率的にクエリできるようになります。 Excel 用の BAM アドインを使用して監視モデル (ビジネス データの概要定義) を作成および展開すると、集計が作成されます。この集計を使用すると、主要業績評価指数 (KPI) と関連のあるデータのコレクションを迅速に評価することができます。  
  
## <a name="types-of-aggregations"></a>集計の種類  
 集計には、スケジュール済みの集計とリアルタイム集計があります。 スケジュール済みの集計は OLAP キューブであり、指定した時刻のビジネス データのスナップショットを表します。 リアルタイム集計では、指定したトリガー ポイントに基づいてビジネス データを表示でき、KPI に達した直後に BAM システムから通知が送信されるようにできます。  
  
## <a name="pivottable-view"></a>ピボットテーブル ビュー  
 ピボットテーブル ビュー領域には、Excel 用の BAM アドインを使用してデザインしたピボットテーブル レポートが表示されます。 Office Web コンポーネントでは、ニーズに合った最適なデータのビューを表示するピボット テーブル レポートを操作できます.  
  
> [!NOTE]
>  リアルタイム集計 (RTA) と事前計算済みの集計 (OLAP 実装) のどちらを使用した場合でも、アクティビティのマイルストーンに達したときに、そのマイルストーンが進捗ディメンションで使用されていなければ、ピボットテーブル レポートを表示しても、一部の行に空のデータが含まれることがあります。 また、進捗ディメンションのコンテキストで時間ディメンションが使用され、"確認済み" または "受信" マイルストーンに固定されている場合は、空のデータが設定された行が含まれることがあります。 この場合、アクティビティ インスタンスが受信され、受信マイルストーンがトリガーされます。ただし、アクティビティでは、確認済みマイルストーンがトリガーされていないため、時間ディメンションの行に 0 が表示されます。  このような状況を回避するには、時間ディメンションを受信マイルストーンまでリンクします。  
  
 ![](../core/media/aggregationpivottabletotal.gif "AggregationPivotTableTotal")  
  
 BAM ポータルでピボットテーブル レポートを変更する際に Office Web コンポーネントを使用する場合は、次の点に注意してください。  
  
- Excel のピボットテーブル レポートには、タイム スライス ディメンションを設定できるページ フィールドが含まれています。 BAM ポータルで使用される Office Web コンポーネントでは、ページのフィールドは含まれません。 Excel のピボットテーブル レポートで、ディメンションにページ フィールドを使用している場合、BAM ポータルのピボットテーブル レポートではページ フィールドのデータは表示されません。  
  
- Office Web コンポーネントは、BAM ポータルのコンテンツ フレームにデータを表示します。 このフレームの領域の制限により、フィールドの一覧から列の領域にディメンションを追加すると、ピボットテーブル レポートでは、ディメンション名の一部または全体が表示されなくなることがあります。  
  
  ピボット テーブルの詳細についてを参照してください「ピボット テーブルの用語集」 [ http://go.microsoft.com/fwlink/?LinkId=55416](http://go.microsoft.com/fwlink/?LinkId=55416)します。  
  
## <a name="chart-view"></a>グラフ ビュー  
 グラフ ビュー領域に表示される集計はグラフィカル インターフェイスで操作できます。 Office Web コンポーネントを使用すると、グラフ ビューを使用して集計の詳細を操作し、必要に応じてレポートに表示されるデータを調整することができます。 グラフ フィールドの一覧からデータ項目をドラッグ アンド ドロップして集計を調整すると、その集計のピボットテーブル レポートでは調整内容が自動的に反映されます。 また、ピボットテーブル レポートをドリルスルーして、新しい集計ビューに警告を作成することができます。  
  
 ![](../core/media/aggregationchartview.gif "AggregationChartView")  
  
## <a name="more"></a>もっとその  
  
-   [アラートを設定する方法](../core/how-to-set-an-alert.md)  
  
-   [アクティビティの検索の結果を表示する方法](../core/how-to-view-the-results-of-an-activity-search.md)  
  
-   [集計を変更する方法](../core/how-to-modify-an-aggregation.md)  
  
## <a name="see-also"></a>参照  
 [集計について](../core/what-is-an-aggregation.md)