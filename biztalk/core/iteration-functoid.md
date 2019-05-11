---
title: 繰り返し Functoid |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Iteration functoids
- Greater Than or Equal To functoids
- And functoids
- Less Than or Equal To functoids
ms.assetid: 24d8911d-2282-4b07-910c-eb2e846dc1f9
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4074e5555a327ab18e1991727d88011b395ae8e7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65380683"
---
# <a name="iteration-functoid"></a>繰り返し Functoid
**イテレーション**functoid の出力、ループの現在のレコードのインデックスが構造体の最初のレコードでは、2、2 つ目のレコードを 1 から始まる具合です。  
  
 次に示します、**イテレーション**functoid が組み合わさ、**より大きいまたは等しい**functoid、**に等しいまたはそれよりも小さい**functoid、および**と** functoid を作成するのと同じ、**の**ループします。  
  
 ![繰り返し functoid の使用方法を示すマップ](../core/media/iterationfunctoid.gif "iterationfunctoid")  
繰り返し Functoid のマップ  
  
 前提としています、**より大きいまたは等しい**より大きい値または 2 に等しいのテストの functoid と**に等しいまたはそれよりも小さい**functoid をテスト 4 小さい値です。 その場合は、**と**functoid が返されます**true**レコード 2、3、および 4 に対してのみです。 したがって、出力インスタンスには 2 つ、3、および 4 つの入力インスタンス メッセージを記録します。  
  
## <a name="see-also"></a>参照  
 [マップに繰り返し Functoid を追加する方法](../core/how-to-add-iteration-functoids-to-a-map.md)   
 [高度な Functoid](../core/advanced-functoids.md)   
 [インデックス Functoid](../core/index-functoid.md)   
 [ループ Functoid](../core/looping-functoid.md)   
 [レコード カウント Functoid](../core/record-count-functoid.md)