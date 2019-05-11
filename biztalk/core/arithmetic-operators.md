---
title: 算術演算子 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d73e153c-aac1-4cea-92d8-af4a1bea6e6a
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d9e56d48f6c49107923541d5095fe0b1019f6afa
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65528822"
---
# <a name="arithmetic-operators"></a>算術演算子
ビジネス ルール フレームワークでは、加算、減算、乗算、除算、および残りの部分 (剰余) 演算子でビジネス ルールの作成に使用がサポートしています。 次の表では、算術演算子について説明します。  
  
|算術演算子|説明|  
|-------------------------|-----------------|  
|**[追加]**|加算演算子 (arg1 arg2 に追加) を表します。|  
|**減算**|減算演算子 (arg1 arg2 減算) を表します。|  
|**乗算**|乗算演算子 (arg1 arg2 を掛けた値) を表します。|  
|**Divide**|除算演算子 (arg1 arg2 で除算) を表します。|  
|**残りの部分**|剰余演算子を表します (arg1 arg2 剰余)。|  
  
 オペランドがさまざまな種類で、長い方の型に変換する、小さい方のオペランド型の数値の自動昇格が発生します。 たとえば場合、**追加**の最初のオペランドと演算子を使用**int**型と 2 番目のオペランドの**長い**型では、最初のオペランドの型に変換されます**長い**実行する前に、**追加**操作。 ルール エンジンは、両方のオペランドを共通の型に昇格できる場合にも二重の昇格をサポートします。 たとえば場合、**追加**の最初のオペランドと演算子が使用される**int**型と 2 番目のオペランドの**uint** に両方のオペランドの型の型が変換されます**長い**実行する前に、**追加**操作。  
  
## <a name="to-use-a-logical-operator-in-a-business-rule"></a>ビジネス ルールで論理演算子を使用するには  
 ビジネス ルールで論理演算子を使用するのにには、次の手順を使用します。  
  
1.  [ファクト エクスプ ローラー] ウィンドウ、**ボキャブラリ**タブ。  
  
2.  展開**ボキャブラリ**、展開**関数**、展開**バージョン 1.0 - 公開済み**、し、ドラッグ、**追加/削除/乗算/分割/残りの部分**条件ペイン/アクション ウィンドウにします。  
  
3.  演算子の左辺と右辺の値を指定します。  
  
## <a name="see-also"></a>参照  
 [論理演算子](../core/logical-operators.md)