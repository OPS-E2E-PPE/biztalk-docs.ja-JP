---
title: ディメンションの定義 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- aggregations [BAM], dimensions
- BAM, dimensions
- BAM views, dimensions
- Excel add-in [BAM], creating dimensions
- dimensions [BAM]
ms.assetid: c00e0c45-eef2-42d9-832c-4be08d79203f
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 916e8f29d7f1e48a7bab5f9ad78e65cb78e51802
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22238490"
---
# <a name="defining-dimensions"></a>ディメンションの定義
Microsoft Excel では、ディメンションをカテゴリとして定義し、それによってテーブルのデータを分析に使用できるようにレベル分けします。 たとえば、場所データのディメンションの場合、市や都道府県、国/地域などのレベルが考えられます。 BAM ビュー ウィザードで BAM ビューを作成すると、次の 1 つ以上の種類のディメンションを追加できます。  
  
-   [進捗ディメンション](../core/progress-dimension.md)  
  
-   [データ ディメンション](../core/data-dimension.md)  
  
-   [時間ディメンション](../core/time-dimension.md)  
  
-   [数値範囲ディメンション](../core/numeric-range-dimension.md)  
  
 ![](../core/media/bam-olap-cube.gif "bam_olap_cube")  
事前に計算された集計データ  
  
 新しいディメンションは BAM ビュー ウィザードで追加します。 ディメンションを追加するには、先にウィザードを使用してビジネス アクティビティ ビューを作成する必要があります。 詳細については、ウィザードを使用して、次を参照してください。[ビジネス アクティビティの定義および Excel でビュー](../core/defining-business-activities-and-views-in-excel.md)です。  
  
### <a name="to-add-new-dimensions"></a>新しいディメンションを追加するには  
  
1.  BAM ビュー ウィザードで、をクリックして**次**が表示されるまで、**新しい BAM ビュー: 集計ディメンションおよび集計メジャー**ページ。 をクリックして**新しいディメンションの**します。  
  
2.  ディメンションの名前を入力します。  
  
3.  一覧からディメンションの種類を選択します。  
  
4.  選択したディメンションの種類に基づいて、適切なデータを入力し、をクリックして**OK**です。  
  
## <a name="see-also"></a>参照  
 [進捗ディメンション](../core/progress-dimension.md)