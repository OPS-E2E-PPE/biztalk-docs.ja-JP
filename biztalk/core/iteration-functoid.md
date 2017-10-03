---
title: "繰り返し Functoid |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Iteration functoids
- Greater Than or Equal To functoids
- And functoids
- Less Than or Equal To functoids
ms.assetid: 24d8911d-2282-4b07-910c-eb2e846dc1f9
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a491b8829f23296e77ba5a89d12985e8ccd32783
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="iteration-functoid"></a>繰り返し Functoid
**イテレーション**ループの現在のレコードのインデックス構造体の最初のレコードでは、2 番目のレコードでは、2 の場合は 1 から開始され、functoid の出力。  
  
 次に示します、**イテレーション**functoid と組み合わせて使用、**より大きいまたは等しい**functoid、**以下に**functoid、および**と**の該当するショートカットを作成する functoid、**の**ループします。  
  
 ![繰り返し functoid の使用方法を示すマップ](../core/media/iterationfunctoid.gif "iterationfunctoid")  
繰り返し Functoid のマップ  
  
 あると想定、**より大きいまたは等しい**functoid またはテストのより大きい値を 2 に等しいかどうかと、**以下に**functoid をテスト 4 小さい値です。 その場合は、**と**functoid が返されます**true** 2、3、および 4 のレコードに対してのみです。 したがって、出力インスタンスには 2、3、および 4 つの入力インスタンス メッセージを記録します。  
  
## <a name="see-also"></a>参照  
 [繰り返し Functoid をマップに追加する方法](../core/how-to-add-iteration-functoids-to-a-map.md)   
 [高度な Functoid](../core/advanced-functoids.md)   
 [インデックス Functoid](../core/index-functoid.md)   
 [ループ Functoid](../core/looping-functoid.md)   
 [レコード カウント Functoid](../core/record-count-functoid.md)