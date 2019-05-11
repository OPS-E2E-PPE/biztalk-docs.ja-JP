---
title: 例外のスロー図形を構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Throw Exception shape [Orchestration Designer]
- orchestrations, errors
- Orchestration Designer, errors
ms.assetid: d3190f1b-db5e-4988-bff6-f7a276760ece
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ee24b5a6fab36e7a865f26a04e8c040141835735
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385935"
---
# <a name="how-to-configure-the-throw-exception-shape"></a>例外のスロー図形を構成する方法
使用して、オーケストレーションで例外をスローすることが明示的に、**例外のスロー**図形。 スローが実行されると、ランタイム エンジンは、スローされる例外の種類を処理できる最も近い例外ハンドラーが検索されます。  
  
 最初に、外側のスコープ、現在のオーケストレーションが検索されがスローされた例外の種類に対応するハンドラーを見つけるには、スコープの関連付けられている例外ハンドラーと見なされます。  
  
 適切な例外ハンドラーが見つからない場合、現在のオーケストレーションを呼び出したオーケストレーションを現在のオーケストレーションへの呼び出しのポイントを囲むスコープが検索されます。 この検索は、現在の例外を処理できる例外ハンドラーが見つかるまで続けられます。  
  
 例外の完全に一致すると、同じクラスの例外クラス、スローされる例外の実行時の型の基本クラス。  
  
 一致する例外ハンドラーが見つかると後、は、例外ハンドラーの最初のステートメントに制御が移ります。  
  
 一致する例外ハンドラーの検索に失敗した場合、オーケストレーションを停止します。 トランザクションは、このような出来事の影響を最小限に抑えるのに役立ちます。  
  
## <a name="procedure"></a>手順  
  
#### <a name="to-configure-a-throw-exception-shape"></a>例外のスロー図形を構成するには  
  
-   [プロパティ] ウィンドウからスローに使用可能なオブジェクトの種類を選択します。、**例外オブジェクト**ドロップダウン リスト。  
  
    > [!NOTE]
    >  一般的な例外の選択、**例外のスロー**場合にのみ、図形、**例外のスロー**図形が例外ハンドラー内にあり、現在の例外ハンドラーでキャッチされた例外を再スローします。 一般的な例外を使用する場合、コンパイル時にエラーが表示されます、**例外のスロー**他のコンテキストでの図形。  
  
## <a name="see-also"></a>参照  
 [例外](../core/exceptions.md)