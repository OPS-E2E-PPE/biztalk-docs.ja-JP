---
title: "退避の計算をサンプル |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4da41d0d-10ee-4f64-97d1-3cfa9da153f7
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0ff231b630a5848494c45cd8d4d05f89e764eb41
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="sample-dehydration-calculation"></a>退避の計算のサンプル
次に示す例は、BizTalk が退避するかどうかをプライベート バイトを使用して計算するサンプルです。 ここでは、既定の構成値と、いくつかの実行時値の例を使用します。  
  
 退避プロパティとしては次の値を想定します。  
  
-   **TimeBlocked** = 60 (秒単位でブロックされる例時間)  
  
-   **WaitingHistory** = 90 (秒単位で待機している履歴を例)  
  
-   **ActualPrivateBytes** = 250 (プライベート バイトの値の例)  
  
-   **OptimalUsage** = 50 (既定の構成値)  
  
-   **MaximalUsage** = 350 (既定の構成値)  
  
 以降、 **ActualPrivateBytes**間**OptimalUsage**と**MaximalUsage**、としてアルファが計算されます。  
  
```  
alpha(private) = (350 – 250) / 350 – 50)  
alpha(private) = 100 / 300  
alpha(private) = 0.33  
```  
  
 計算するし、 **TestThreshold**次のようにします。  
  
```  
TestThreshold = 1 + (0.33 * (1800 – 1))  
TestThreshold = 1 + 599.66  
TestThreshold = 600.66  
```  
  
 最後に、退避するかどうかを判断します。  
  
```  
Dehydrate = (90 == -1 OR 90 > 600 OR 60 > (2 * 600))  
Dehydrate = false  
```  
  
 この例を使用すると、オーケストレーションはこの時点では退避されないと判断できます。