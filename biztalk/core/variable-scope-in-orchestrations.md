---
title: オーケストレーションにおける変数のスコープ |Microsoft Docs
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
ms.openlocfilehash: ebe6e3e4116a2b5c250e642d5bc78d828b07656c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65292576"
---
# <a name="variable-scope-in-orchestrations"></a>オーケストレーションにおける変数のスコープ
可視性と変数と、例外ハンドラーや補正ブロックをも含め、オーケストレーション内のさまざまな場所でオーケストレーション パラメーターの状態を理解するために、いくつかの重要なポイントがあります。  
  
-   オーケストレーション パラメーターは、その補正ブロックのようにも、オーケストレーションの本文全体で表示されます。  
  
-   およびすべての例外ハンドラーと補正ブロックのスコープの本体で、スコープ レベルの変数が表示されます。 例外のハンドラー内で、変数と見なされる初期化されていない前に、または本文に、初期化された後に、特定のハンドラーの原因となった例外がかどうか実施不確定ではないためです。 このため、スコープで変数を宣言し、本文内で初期化し、例外ハンドラーでそこから読み取ることができませんまたはコンパイラ エラーが表示されます。 実行時間の長いトランザクションの場合、その回避策が存在します。 次の例では、succeeded() 演算子を使用して、適切なランタイムの動作を確保する方法を示しています。  
  
    > [!NOTE]
    >  次のコードは、;、論理的なプロセスを説明する擬似コードこのコードは、オーケストレーションの式図形内で使用できません。  
  
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
  
-   補正ブロック内では、すべての変数には、スコープの本体がコミットされたときの値が想定しています。 スコープの補正ブロックが本体内の完了直後後に実行されないことに注意してください。介在するコードは常にします。 介在するコードのいくつかの外側のスコープの変数が更新され、補正ブロックが実行する場合、補正ブロック内でこれらの更新プログラムが表示されません。 代わりに、変数は、一時的にその報酬を所有するスコープがコミット時に保持していた値に戻ります。  
  
-   トランザクションは、ループ内で入れ子になっている、ときに、ループが実行される回数だけ、トランザクションが補正されます。 各イテレーションの補正ブロック内では、外側のスコープの変数には、トランザクションのコミットのイテレーション時の値が想定しています。  
  
-   外側のスコープの変数にすべての更新が行われたか、補正ブロックが完了したら、内側のスコープの補正ブロック内でのオーケストレーション パラメーターは表示されません。 つまり、補正ブロックを使用して、外側のスコープの変数の値を直接変更できません。  
  
## <a name="see-also"></a>参照  
 [XLANG-s データ型](../core/xlang-s-data-types.md)