---
title: データ ディメンション |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Data dimension [BAM]
- aggregations [BAM], data dimensions
ms.assetid: 07b5e56a-4fd5-4c88-a98a-758e514d0621
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 036491d9f0fdb946c748850b7c25c959854f2098
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65353195"
---
# <a name="data-dimension"></a>データ ディメンション
行または列で使用する BAM アクティビティ内のテキスト項目の値をデータ ディメンションを定義できます。 たとえば、次の表を作成する製品の名前のデータ ディメンションを使用できます。  
  
|製品|Count|  
|-------------|-----------|  
|テニス ラケット|100|  
|サッカー ボール|200|  
  
 また、BAM ビュー ウィザードでは、複数のデータ ディメンションを定義できます。 たとえば、という名前のデータ ディメンションを定義する**場所**レベルが含ま**状態**と**市区町村**次の表を作成するために使用できます。  
  
|||||  
|-|-|-|-|  
||California||Washington|  
||Los Angeles|San Francisco|Seattle|  
|テニス ラケット|50|20|30|  
|サッカー ボール|130|50|20|  
  
 この表で、Product ディメンションは、行として使用され、場所ディメンションは列として使用されました。  
  
## <a name="see-also"></a>参照  
 [時間ディメンション](../core/time-dimension.md)   
 [進捗ディメンション](../core/progress-dimension.md)   
 [数値範囲ディメンション](../core/numeric-range-dimension.md)   
 [ディメンションの定義](../core/defining-dimensions.md)