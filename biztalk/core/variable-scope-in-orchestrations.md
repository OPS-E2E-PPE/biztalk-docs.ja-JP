---
title: オーケストレーションにおける変数のスコープ |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, variables
ms.assetid: 5856cdca-0ebd-4e16-8739-7bd50753b9f9
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 82803cd7f2b0beb8349e978fdd7b9e453dca31ce
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="variable-scope-in-orchestrations"></a>オーケストレーションにおける変数のスコープ
オーケストレーション内のさまざまな場所で使用されている変数やパラメーターの可視性と状態については、例外ハンドラーや補正ブロックなど、理解しておくべき重要な点がいくつかあります。  
  
-   オーケストレーション パラメーターは、補正ブロックを含め、オーケストレーション本体のどの場所からでも参照できます。  
  
-   スコープ レベルの変数は、該当スコープの本体と、そのすべての例外ハンドラーおよび補正ブロックから参照できます。 例外ハンドラー内では、変数は初期化されていないものとして見なされます。特定のハンドラーを呼び出した例外が、本体で初期化される前に発生したのか、初期化された後に発生したのかが確定しないためです。 したがって、スコープ内で変数を宣言し、本体でそれを初期化した場合、例外ハンドラーからその変数を読み取ることはできません。読み取ろうとした場合は、コンパイラ エラーになります。 長時間実行されるトランザクションの場合は、これを回避する方法があります。 次の例は、succeeded() 演算子を使って、実行時に適切な動作が行われるようにする方法を示しています。  
  
    > [!NOTE]
    >  以下のコードは、論理的なプロセスを説明するための疑似コードです。オーケストレーションの式図形でこのコードを使用することはできません。  
  
    ```  
    scope longrunning transaction L  
    {  
       System.Int32 i;  
       System.Int32 v;  
       body  
       {  
          i = 3;  
          scope longrunning transaction T  
          {  
             body  
             {  
                i = 5;  
             }  
          }  
       }  
       exceptions  
       {  
          catch  
          {  
             if(succeeded(T))  
             {  
                v = i;  // OK to read from it here — no compiler errors!  
             }  
          }  
       }  
    }  
    ```  
  
-   補正ブロック内では、すべての変数は、そのスコープの本体が実行されたときの値が想定されます。 スコープの補正ブロックは、本体の実行が完了した直後に実行されることはない、つまり、常に、介入コードが存在するという点に注意してください。 何らかの介入コードによって外側のスコープの変数が更新された後、補正ブロックが実行された場合、更新の内容は補正ブロックからは見えないことになります。 そのため、変数は、補正ブロックの属するスコープがコミットされたときに保持していた値へと一時的に戻されます。  
  
-   トランザクションがループ内で入れ子になっている場合、トランザクションはループの実行回数と同じだけ補正されます。 各繰り返し処理の補正ブロック内では、外側のスコープの変数は、コミットされたトランザクションの繰り返し処理時に保持していた値が想定されます。  
  
-   外側のスコープに属する変数またはオーケストレーション パラメーターに対して、内側のスコープの補正ブロック内で行った変更は、補正ブロックが完了した後には見えなくなります。 つまり、外側のスコープに属する変数の値を、補正ブロックで直接変更することはできないということになります。  
  
## <a name="see-also"></a>参照  
 [XLANG のデータ型](../core/xlang-s-data-types.md)