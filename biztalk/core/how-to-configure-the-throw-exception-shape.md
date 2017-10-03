---
title: "例外のスロー図形を構成する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Throw Exception shape [Orchestration Designer]
- orchestrations, errors
- Orchestration Designer, errors
ms.assetid: d3190f1b-db5e-4988-bff6-f7a276760ece
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 07d156572484ba4fbe71533252ce4fe956136699
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-the-throw-exception-shape"></a>例外のスロー図形を構成する方法
使用して、オーケストレーションで例外をスローすることが明示的に、**例外のスロー**図形です。 スローが実行されると、ランタイム エンジンは、スローされた例外の種類を処理できる例外ハンドラーのうち最も近くにある例外ハンドラーを探します。  
  
 最初に現在のオーケストレーションを囲んでいるスコープを検索し、そのスコープに関連付けられている例外ハンドラーを検討して、スローされた例外の種類に適したハンドラーを特定します。  
  
 適切な例外ハンドラーを検出できない場合は、現在のオーケストレーションを呼び出したオーケストレーションから、現在のオーケストレーションへの呼び出しポイントを含むスコープを探します。 この検索は、現在の例外を処理できる例外ハンドラーが見つかるまで継続されます。  
  
 例外に完全に一致するのは、スローされた例外のランタイム型と同じクラスか、その基本クラスとなっている例外クラスです。  
  
 一致する例外ハンドラーが見つかると、その例外ハンドラーの最初のステートメントに制御が移ります。  
  
 一致する例外ハンドラーの検索に失敗した場合は、オーケストレーションが停止します。 トランザクションを使用すると、そのような場合の影響を最小限に抑えることができます。  
  
## <a name="procedure"></a>手順  
  
#### <a name="to-configure-a-throw-exception-shape"></a>例外のスロー図形を構成するには  
  
-   [プロパティ] ウィンドウで、使用可能なオブジェクトの種類を選択からスローする、**例外オブジェクト**ドロップダウン リスト。  
  
    > [!NOTE]
    >  一般的な例外を選択して、**例外のスロー**場合にのみ、図形、**例外のスロー**図形が例外ハンドラー内にあり、現在の例外ハンドラーでキャッチされた例外を再スローします。 一般的な例外を使用する場合、コンパイル時に、エラーが表示されます、**例外のスロー**他のコンテキスト内の図形です。  
  
## <a name="see-also"></a>参照  
 [例外](../core/exceptions.md)