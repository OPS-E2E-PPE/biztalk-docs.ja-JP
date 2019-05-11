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
ms.openlocfilehash: 1055a76039420024a5cbfacf8e63094e00b1b8b5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65360245"
---
# <a name="aggregations-in-the-bam-portal"></a>BAM ポータルでの集計
集計は、OLAP キューブで分析処理を使用できる事前計算済みのデータのテーブルです。 集計は、多次元データベースの効率的なクエリを容易になります。 作成して監視モデル (ビジネス データの高度な定義) を展開するときに、主要業績評価指標 (Kpi) に関連データのコレクションをすばやく評価するために使用できる集計を作成するために Excel 用 BAM アドインを使用して、します。  
  
## <a name="types-of-aggregations"></a>集計の種類  
 集計には、リアルタイムまたはスケジュールのいずれかを指定できます。 スケジュール済みの集計は、OLAP キューブは、指定する時点で、ビジネス データのスナップショットを表します。 リアルタイム集計では、指定したトリガー ポイントに基づいて、KPI に達したとすぐにアラートを通知するように BAM システム ビジネス データのビューを許可します。  
  
## <a name="pivottable-view"></a>ピボット テーブル ビュー  
 ピボット テーブル ビュー領域には、Excel 用 BAM アドインを使用して設計すること、ピボット テーブル レポートが表示されます。 Office Web コンポーネントでは、ニーズに合った最適なデータのビューを表示するピボット テーブル レポートを操作できます.  
  
> [!NOTE]
>  ピボット テーブル レポートを表示する場合、アクティビティのマイルス トーンに達したが、進行状況で使用されていない場合、いくつかの行にリアルタイム集計 (Rta) と事前計算済みの集計 (OLAP 実装) の両方で null データを含む可能性があることができます。ディメンションです。 時間ディメンションは、進捗ディメンションのコンテキストで使用しが固定されるマイルス トーン「確認」など、「受信」ではなく null データを持つ行が発生することも ここでアクティビティ インスタンスが受信される受信マイルス トーンがトリガーがアクティビティによって確認済みマイルス トーンをまだトリガーされていないと、0 は、時間ディメンションの行に表示されます。  このような状況を回避するには、受信マイルス トーンまでの時間ディメンションをリンクします。  
  
 ![](../core/media/aggregationpivottabletotal.gif "AggregationPivotTableTotal")  
  
 BAM ポータルで Office Web コンポーネントを使用して、ピボット テーブル レポートを変更するときに、これらの点に留意してください。  
  
- Excel でピボット テーブル レポートには、時間スライス ディメンションを配置できるページ フィールドが含まれます。 BAM ポータルで使用される Office Web コンポーネントでは、ページのフィールドは含まれません。 Excel のピボット テーブル レポートでは、任意のディメンションにページ フィールドを使用している場合、BAM ポータルでピボット テーブル レポートでこのフィールドのデータは表示されません。  
  
- Office Web コンポーネントは、BAM ポータルのコンテンツ フレームにデータを表示します。 このフレームの領域の制限のため列の領域にフィールドの一覧からディメンションを追加と、ビューからディメンション名を部分的または完全に移動するピボット テーブルの表示が発生することができます。  
  
  ピボット テーブルの詳細についてを参照してください「ピボット テーブルの用語集」 [ http://go.microsoft.com/fwlink/?LinkId=55416](http://go.microsoft.com/fwlink/?LinkId=55416)します。  
  
## <a name="chart-view"></a>グラフ ビュー  
 グラフ ビュー領域には、グラフィカルな方法で、集計が表示されます。 Office Web コンポーネントを使用すると、必要に応じて、報告されるデータを調整するグラフの表示を使用して、集計の詳細を操作できます。 ドラッグしてグラフのフィールド リストからデータ項目をドロップする集計を調整すると、集計のピボット テーブル レポートは、変更を反映するように自動的に更新します。 新しい集計ビューにアラートを作成するピボット テーブルをドリルスルーすることができます。  
  
 ![](../core/media/aggregationchartview.gif "AggregationChartView")  
  
## <a name="more"></a>もっとその  
  
-   [アラートを設定する方法](../core/how-to-set-an-alert.md)  
  
-   [アクティビティの検索の結果を表示する方法](../core/how-to-view-the-results-of-an-activity-search.md)  
  
-   [集計を変更する方法](../core/how-to-modify-an-aggregation.md)  
  
## <a name="see-also"></a>参照  
 [集計について](../core/what-is-an-aggregation.md)