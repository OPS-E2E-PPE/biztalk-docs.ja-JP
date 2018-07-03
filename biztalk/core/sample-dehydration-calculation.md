---
title: 退避の計算のサンプル |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4da41d0d-10ee-4f64-97d1-3cfa9da153f7
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 77701083272da9e09c21cb05daf3c4e9764b604c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36993043"
---
# <a name="sample-dehydration-calculation"></a>退避の計算のサンプル
次に示す例は、BizTalk が退避するかどうかをプライベート バイトを使用して計算するサンプルです。 ここでは、既定の構成値と、いくつかの実行時値の例を使用します。  
  
 退避プロパティとしては次の値を想定します。  
  
- **TimeBlocked** = 60 (秒単位でブロック時間の例である場合)  
  
- **WaitingHistory** = 90 (秒単位で待機している履歴を例)  
  
- **ActualPrivateBytes** = 250 (プライベート バイトの値の例)  
  
- **OptimalUsage** = 50 (既定の構成値)  
  
- **MaximalUsage** = 350 (既定の構成値)  
  
  以降、 **ActualPrivateBytes**間**OptimalUsage**と**MaximalUsage**アルファとして計算されます。  
  
```  
alpha(private) = (350 – 250) / 350 – 50)  
alpha(private) = 100 / 300  
alpha(private) = 0.33  
```  
  
 計算し、 **TestThreshold**次のようにします。  
  
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