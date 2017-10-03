---
title: "数値範囲ディメンション |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- aggregations [BAM], Numeric Range dimension
- Numeric Range dimension [BAM]
ms.assetid: a874ce44-b034-498f-ba58-114028dbef2c
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2fb6d4c21e0a207cfeec3e592569ca0f48f3badf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="numeric-range-dimension"></a>数値範囲ディメンション
数値範囲ディメンションを使用すると、特定の数値範囲のフレンドリ名に基づいて集計を分類できます。 たとえば、ビジネス アナリストは "PO サイズ" という名前の数値範囲ディメンションを定義し、0 ～ 100 ドルの注文には "小"、100 ドルを超え 1,000 ドル以下の注文には "中"、1,000 ドルを超える注文には "大" というように範囲を設定できます。  
  
> [!NOTE]
>  注文額が定義した範囲内にない場合、たとえば 0 ドル未満である場合は、BAM によって "範囲外" という列が自動的に作成され、範囲外のデータはここに追加されます。  
  
> [!NOTE]
>  同じデータ エイリアスを参照する複数の数値範囲ディメンションは作成できません。  
  
## <a name="see-also"></a>参照  
 [ピボット テーブルを使用する方法](../core/how-to-use-the-pivottable.md)   
 [進捗ディメンション](../core/progress-dimension.md)   
 [データ ディメンション](../core/data-dimension.md)   
 [時間ディメンション](../core/time-dimension.md)   
 [ディメンションの定義](../core/defining-dimensions.md)