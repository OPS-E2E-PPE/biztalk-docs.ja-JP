---
title: "データ ディメンション |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Data dimension [BAM]
- aggregations [BAM], data dimensions
ms.assetid: 07b5e56a-4fd5-4c88-a98a-758e514d0621
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b7138cf31a9cb86a9ba949142129ac5c906754b1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="data-dimension"></a>データ ディメンション
行と列に使用する BAM アクティビティ内のテキスト項目の値をデータ ディメンションを定義できます。 たとえば、製品という名前のデータ ディメンションを使用して、次のテーブルを作成できます。  
  
|Product|Count|  
|-------------|-----------|  
|テニス ラケット|100|  
|サッカー ボール|200|  
  
 また、BAM ビュー ウィザードで複数のデータ ディメンションを定義できます。 たとえば、という名前のデータ ディメンションを定義する**場所**のレベルを持つ**状態**と**市区町村**次の表の作成に使用できます。  
  
|||||  
|-|-|-|-|  
||California||Washington|  
||Los Angeles|San Francisco|Seattle|  
|テニス ラケット|50|20|30|  
|サッカー ボール|130|50|20|  
  
 このテーブルでは、製品ディメンションは行として使用され、場所ディメンションは列として使用されています。  
  
## <a name="see-also"></a>参照  
 [時間ディメンション](../core/time-dimension.md)   
 [進捗ディメンション](../core/progress-dimension.md)   
 [数値範囲ディメンション](../core/numeric-range-dimension.md)   
 [ディメンションの定義](../core/defining-dimensions.md)