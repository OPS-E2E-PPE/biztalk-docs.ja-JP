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
ms.openlocfilehash: 025d83e8a7bd6c5a3c324bd5dae8354ac43321ed
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393906"
---
# <a name="sample-dehydration-calculation"></a>退避の計算のサンプル
プライベート (バイト単位) を使用していない、または BizTalk が退避を決定する、サンプルの計算の例を示します。 既定の構成値、およびいくつかの例の実行時値を使用します。  
  
 次の退避プロパティの値があるとします。  
  
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
  
 最後に、かどうかを退避するかどうかを確認します。  
  
```  
Dehydrate = (90 == -1 OR 90 > 600 OR 60 > (2 * 600))  
Dehydrate = false  
```  
  
 この例を使用して、オーケストレーションができないこと退避この時点で確認できます。