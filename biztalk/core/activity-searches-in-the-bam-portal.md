---
title: BAM ポータルでのアクティビティの検索 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b97f9577d43552ad51766ccc4178bb2d73fb7107
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65361585"
---
# <a name="activity-searches-in-the-bam-portal"></a>BAM ポータルでのアクティビティの検索
アクティビティの検索を使用し、これに基づいて、BAM ビューで、その編集や、アラートを作成できるように、これらのアクティビティを表示して、追跡対象の値に基づいて、使用可能な項目を指定した条件に一致するアクティビティを検索する BAM データに対して検索を実行することができます。  
  
## <a name="parts-of-the-query-builder"></a>クエリ ビルダーのパーツ  
 アクティビティの検索のクエリを作成するには、関心のあるデータを抽出するブール型の比較を作成する対象となるビジネス データ項目を選択します。 BAM ビューを選択して開始する、**マイ ビュー**ポータルのフレーム。 選択したビューからクエリを構築するためのアクティビティを選択します。  
  
 ![](../core/media/bamportalviewschooser.gif "BAMPortalViewsChooser")  
  
 アクティビティを選択したら、ポータルのコンテンツ フレームには、クエリ ビルダー、列の選択、および結果のボックスが表示されます。 既存のクエリを開くか、新しいゲートウェイを作成することができます。  
  
 ![](../core/media/activitysearchquerybuilder.gif "ActivitySearchQueryBuilder")  
  
 ビジネス データ項目を選択して開始する新しいクエリを作成する、**ビジネス データ**ドロップダウン リスト。  
  
 ![](../core/media/activitysearchquerybuilderbusinessdatadropdown.gif "ActivitySearchQueryBuilderBusinessDataDropdown")  
  
 次に、演算子のドロップダウン リストで、比較演算子を選択します。 比較演算子を使用すると、クエリの結果を絞り込むことができます。  
  
 ![](../core/media/activitysearchcomparisonoperatordropdown.gif "ActivitySearchComparisonOperatorDropDown")  
  
 値のドロップダウン リストは、ビジネス データ項目によって表されるデータの種類に基づく状況依存します。 許可されているデータ変更の種類として、ユーザー インターフェイス (UI) を変更します。  
  
 使用したクエリの句を結合することができますとまたは OR 演算子をクリックしてより複雑なクエリを形成する、**追加**ボタンをクリックします。  
  
 ![](../core/media/activitysearchjoiningclauses.gif "ActivitySearchJoiningClauses")  
  
> [!NOTE]
>  句をグループ化することはできません。 クエリは、参加させる個々 の句の単純な文字列や演算子。  
  
 次の表では、日付と時刻のフィールドについて説明します。  
  
|演算子|説明|  
|--------------|-----------------|  
|**で**|完全一致を指定します。 ブール値に等しい (=) の操作と同じです。 **注:** 選択した場合、**で**演算子をポータルは既定値として午前 0 時を使用ない時刻の部分で日付を指定します。 場合は、意図でない場合を使用して、**以前**または**以降**目的の結果を取得する演算子。|  
|**以前**|指定した日付より前に、のトランザクションのみが一致することを指定します。 ブール値に相当より小さいまたは等しい (≤) 操作。|  
|**以降**|指定した日付以降のトランザクションのみが一致することを指定します。 ブール値より大きいまたは等しい (≥) 操作と同じです。|  
|**[指定日付より前]**|指定した日付より前に、のトランザクションのみが一致することを指定します。 ブール値 (<) の操作よりも小さいと等価です。|  
|**After**|指定日付より後のトランザクションのみが一致することを指定します。 ブール型の大なり (>) 演算子と同じです。|  
|**最後に**|期間を指定する前に発生したトランザクションのみが一致することを指定します。 期間は、秒、分、時間、または日数で指定できます。|  
|**最後の前に**|指定した期間の前に発生したトランザクションのみが一致することを指定します。 期間は、秒、分、時間、または日数で指定できます。|  
|**空です。**|対象のビジネス データ項目が含まれていないデータに (データ フィールドの値は NULL) のトランザクションのみが返されることを指定します。|  
|**空でないです。**|ビジネス データ項目が (データ フィールドの値が NULL でない) データが含まれますトランザクションのみが返されることを指定します。|  
  
 次の表では、数値フィールドおよび期間フィールドについて説明します。 数値フィールドには、数量や金額などのデータが含まれます。 期間フィールドでは、期間を指定します。  
  
|演算子|説明|  
|--------------|-----------------|  
|**[等しい]**|完全一致を指定します。 ブール値に等しい (=) の操作と同じです。|  
|**より大きい**|完全一致を指定します。 ブール型の値より大きい (>) 操作と同じです。|  
|**[次の値以上]**|完全一致を指定します。 ブール型の値より大きいまたは等しい (≥) 操作と同じです。|  
|**より小さい**|完全一致を指定します。 ブール値より小さい (<) 演算子と同じです。|  
|**[次の値以下]**|完全一致を指定します。 小なりに相当よりまたは等しい (≤) 操作。|  
|**等しくないです。**|完全一致を指定します。 いない Equals (≠) 操作と同じです。|  
|**空です。**|対象のビジネス データ項目が含まれていないデータに (データ フィールドの値は NULL) のトランザクションのみが返されることを指定します。|  
|**空でないです。**|ビジネス データ項目が (データ フィールドの値が NULL でない) データが含まれますトランザクションのみが返されることを指定します。|  
  
 次の表では、テキスト フィールドについて説明します。  
  
|演算子|説明|  
|--------------|-----------------|  
|**正確には**|完全一致を指定します。 ブール値に等しい (=) の操作と同じです。|  
|**[値を含む]**|ビジネス データ項目のテキストに指定した値が含まれているを指定します。 これにより、データの部分的な一致を行うことができます。|  
|**[次を含まない]**|ビジネス データ項目のテキストに指定した値が含まれていないことを指定します。|  
|**空です。**|対象のビジネス データ項目が含まれていないデータに (データ フィールドの値は NULL) のトランザクションのみが返されることを指定します。|  
|**空でないです。**|ビジネス データ項目が (データ フィールドの値が NULL でない) データが含まれますトランザクションのみが返されることを指定します。|  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [アクティビティの検索でクエリを作成する方法](../core/how-to-create-a-query-in-activity-search.md)  
  
-   [アラートを設定する方法](../core/how-to-set-an-alert.md)  
  
-   [アクティビティの検索の結果を表示する方法](../core/how-to-view-the-results-of-an-activity-search.md)  
  
## <a name="see-also"></a>参照  
 [BAM ポータル](../core/bam-portal.md)