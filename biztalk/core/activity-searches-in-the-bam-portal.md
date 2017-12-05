---
title: "BAM ポータルでのアクティビティの検索 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- activities [BAM], searching
- queries [BAM], field descriptions
- Query Builder [BAM portal], creating queries
- queries [BAM], activity searches
- Query Builder [BAM portal], about Query Builder
- Query Builder [BAM portal], activity searches
- Query Builder [BAM portal]
- Query Builder [BAM portal], field descriptions
- BAM portal, Query Builder
- BAM portal, activity searches
ms.assetid: 60ab8deb-ebe2-4959-97fd-261ff64d500c
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 723848f61294cc710bd2292758383cf674093265
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="activity-searches-in-the-bam-portal"></a>BAM ポータルでのアクティビティの検索
アクティビティの検索では、BAM データが検索され、追跡する値および BAM ビューで使用可能な項目に基づいて指定した条件に一致するアクティビティを見つけることができます。また、アクティビティを編集したり、アクティビティに基づいて警告を作成できるように、アクティビティを表示することもできます。  
  
## <a name="parts-of-the-query-builder"></a>クエリ ビルダーでの操作  
 アクティビティを検索するためのクエリを作成するには、ビジネス データの項目を選択します。これらの項目は、必要なデータを取得するために、ブール値の比較演算の対象として使用されます。 BAM ビューを選択して、起動する、**マイ ビュー**ポータルのフレームです。 選択したビューから、作成するクエリの対象となるアクティビティを選択します。  
  
 ![](../core/media/bamportalviewschooser.gif "BAMPortalViewsChooser")  
  
 アクティビティを選択すると、ポータルのコンテンツ フレームには、[クエリ]、[列の選択]、および [結果] ボックスが表示されます。 既存のクエリを開くか、新しいクエリを作成することができます。  
  
 ![](../core/media/activitysearchquerybuilder.gif "ActivitySearchQueryBuilder")  
  
 ビジネス データ項目を選択して開始する新しいクエリを構築する、**ビジネス データ**ドロップダウン リスト。  
  
 ![](../core/media/activitysearchquerybuilderbusinessdatadropdown.gif "ActivitySearchQueryBuilderBusinessDataDropdown")  
  
 次に、[演算子] ボックスの一覧で比較演算子を選択します。 比較演算子を使用すると、クエリの結果を絞り込むことができます。  
  
 ![](../core/media/activitysearchcomparisonoperatordropdown.gif "ActivitySearchComparisonOperatorDropDown")  
  
 [値] ボックスの一覧は、ビジネス データ項目が表すデータの種類に基づき、状況に応じて変化します。 ユーザー インターフェイス (UI) は、許可されたデータ変更の種類によって変わります。  
  
 使用してクエリの句を結合してまたは OR 演算子をクリックしてより複雑なクエリを作成する、**追加**ボタンをクリックします。  
  
 ![](../core/media/activitysearchjoiningclauses.gif "ActivitySearchJoiningClauses")  
  
> [!NOTE]
>  句をグループ化することはできません。 クエリは、個別の句を AND 演算子または OR 演算子で結合した単純な文字列です。  
  
 次の表では、日付と時刻のフィールドについて説明します。  
  
|演算子|Description|  
|--------------|-----------------|  
|**At**|完全一致を指定します。 ブール値の "=" (等号) 演算子と同じです。 **注:**を選択した場合、**で**演算子し、ポータルは、既定値として午前 0 時を使用して時刻部分と日付を指定します。 ユーザーの意図でない場合場合を使用して、**以前**または**以降の**オペレーターは、目的の結果を取得します。|  
|**以前**|指定した日付以前のトランザクションのみが一致するように指定します。 ブール値の "≤" (以下) 演算子と同じです。|  
|**以降**|指定した日付以降のトランザクションのみが一致するように指定します。 ブール値の "≥" (以上) 演算子と同じです。|  
|**[指定日付より前]**|指定した日付より前のトランザクションのみが一致するように指定します。 ブール値の "<" (より小さい) 演算子と同じです。|  
|**After**|指定した日付より後のトランザクションのみが一致するように指定します。 ブール値より大きい (>) 操作に相当します。|  
|**最後に**|指定した過去の期間に発生したトランザクションのみが一致するように指定します。 期間は、秒、分、時間、または日数で指定できます。|  
|**最後の前に**|指定した期間より前に発生したトランザクションのみが一致するように指定します。 期間は、秒、分、時間、または日数で指定できます。|  
|**空です。**|ビジネス データ項目にデータが含まれていない (データ フィールドの値が NULL の) トランザクションのみが返されるように指定します。|  
|**空でないです。**|ビジネス データ項目にデータが含まれている (データ フィールドの値が NULL ではない) トランザクションのみが返されるように指定します。|  
  
 次の表では、数値フィールドおよび期間フィールドについて説明します。 数値フィールドには、数量や金額などのデータが含まれます。 期間フィールドでは、期間を指定します。  
  
|演算子|Description|  
|--------------|-----------------|  
|**[等しい]**|完全一致を指定します。 ブール値の "=" (等号) 演算子と同じです。|  
|**より大きい**|完全一致を指定します。 ブール値の ">" (より大きい) 演算子と同じです。|  
|**[次の値以上]**|完全一致を指定します。 ブール型の値より大きいまたは等しい (≥) 操作に相当します。|  
|**より小さい**|完全一致を指定します。 ブール値より小さい (<) 操作に相当します。|  
|**[次の値以下]**|完全一致を指定します。 "≤" (以下) 演算子と同じです。|  
|**等しくないです。**|完全一致を指定します。 ブール値の "≠" (不等号) 演算子と同じです。|  
|**空です。**|ビジネス データ項目にデータが含まれていない (データ フィールドの値が NULL の) トランザクションのみが返されるように指定します。|  
|**空でないです。**|ビジネス データ項目にデータが含まれている (データ フィールドの値が NULL ではない) トランザクションのみが返されるように指定します。|  
  
 次の表では、テキスト フィールドについて説明します。  
  
|演算子|Description|  
|--------------|-----------------|  
|**正確には**|完全一致を指定します。 ブール値の "=" (等号) 演算子と同じです。|  
|**[値を含む]**|指定した値がビジネス データ項目のテキストに含まれるように指定します。 これにより、データの部分的な一致を指定できます。|  
|**[次を含まない]**|指定した値がビジネス データ項目のテキストに含まれないように指定します。|  
|**空です。**|ビジネス データ項目にデータが含まれていない (データ フィールドの値が NULL の) トランザクションのみが返されるように指定します。|  
|**空でないです。**|ビジネス データ項目にデータが含まれている (データ フィールドの値が NULL ではない) トランザクションのみが返されるように指定します。|  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [アクティビティの検索でクエリを作成する方法](../core/how-to-create-a-query-in-activity-search.md)  
  
-   [警告を設定する方法](../core/how-to-set-an-alert.md)  
  
-   [アクティビティの検索の結果を表示する方法](../core/how-to-view-the-results-of-an-activity-search.md)  
  
## <a name="see-also"></a>参照  
 [BAM ポータル](../core/bam-portal.md)