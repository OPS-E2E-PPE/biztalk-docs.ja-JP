---
title: ディメンションの定義 |Microsoft Docs
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
ms.openlocfilehash: be3c55298b58d2d5ca51652ed9911c901235863e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013659"
---
# <a name="defining-dimensions"></a>ディメンションの定義
Microsoft Excel では、ディメンションをカテゴリとして定義し、それによってテーブルのデータを分析に使用できるようにレベル分けします。 たとえば、場所データのディメンションの場合、市や都道府県、国/地域などのレベルが考えられます。 BAM ビュー ウィザードで BAM ビューを作成すると、次の 1 つ以上の種類のディメンションを追加できます。  
  
- [進捗ディメンション](../core/progress-dimension.md)  
  
- [データ ディメンション](../core/data-dimension.md)  
  
- [時間ディメンション](../core/time-dimension.md)  
  
- [数値範囲ディメンション](../core/numeric-range-dimension.md)  
  
  ![](../core/media/bam-olap-cube.gif "bam_olap_cube")  
  事前に計算された集計データ  
  
  新しいディメンションは BAM ビュー ウィザードで追加します。 ディメンションを追加するには、先にウィザードを使用してビジネス アクティビティ ビューを作成する必要があります。 詳細については、ウィザードを使用して、次を参照してください。[ビジネス アクティビティの定義および Excel でのビュー](../core/defining-business-activities-and-views-in-excel.md)します。  
  
### <a name="to-add-new-dimensions"></a>新しいディメンションを追加するには  
  
1.  BAM ビュー ウィザードで、**次**が表示されるまで、**新しい BAM ビュー: 集計ディメンションおよび集計メジャー**ページ。 クリックして**新しいディメンションの**します。  
  
2.  ディメンションの名前を入力します。  
  
3.  一覧からディメンションの種類を選択します。  
  
4.  選択したディメンションの種類に基づいて、適切なデータを入力し、順にクリックします**OK**します。  
  
## <a name="see-also"></a>参照  
 [進捗ディメンション](../core/progress-dimension.md)