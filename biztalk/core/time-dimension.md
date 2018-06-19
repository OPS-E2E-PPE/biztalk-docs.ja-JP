---
title: 時間ディメンション |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Time dimension [BAM]
- aggregations [BAM], Time dimension
ms.assetid: 8f83b758-09a1-4efb-ae0e-32753f56c4e4
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 418afdc5b7507aba9a564628341c10495b2a740a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22279450"
---
# <a name="time-dimension"></a>時間ディメンション
時間ディメンションを使用すると、時間を基準として集計を作成できます。 たとえば、時間ディメンションを使用して、次のテーブルを作成できます。  
  
|年|Month|Count|  
|----------|-----------|-----------|  
|2003|January|120|  
||February|230|  
||March|350|  
||April|280|  
  
 時間ディメンションは、他のディメンションと組み合わせて使用できます。 たとえば、行に時間ディメンションを使用し、列にデータ ディメンションを使用して、次のテーブルを作成できます。  
  
|||テニス ラケット|サッカー ボール|  
|------|------|---------------------|------------------|  
||January|50|70|  
||February|120|110|  
||March|300|50|  
||April|220|60|  
  
## <a name="see-also"></a>参照  
 [数値範囲ディメンション](../core/numeric-range-dimension.md)   
 [進捗ディメンション](../core/progress-dimension.md)   
 [データ ディメンション](../core/data-dimension.md)   
 [ディメンションの定義](../core/defining-dimensions.md)