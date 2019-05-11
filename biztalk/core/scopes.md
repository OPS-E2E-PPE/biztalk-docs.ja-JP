---
title: スコープ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- scopes, exception handling
- Scope shape [Orchestration Designer], nesting
- scopes, variables
- scopes, Scope shape [Orchestration Designer]
- Scope shape [Orchestration Designer], exception handling
- scopes, transactions
- scopes, synchronization
- scopes, nesting
- Scope shape [Orchestration Designer], transactions
ms.assetid: 51d81ce4-0034-4415-b6ab-4c952737c1bd
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 67d10fa444b8bf5a427fe48c70655c233f06eef9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395534"
---
# <a name="scopes"></a>スコープ
スコープとは、アクションをグループ化するためのフレームワークです。 トランザクションの実行および例外処理には主に使用します。  
  
 1 つのスコープには、1 つ以上のブロックが含まれます。 本文が含まれるは必要に応じてが追加された任意の数の例外処理ブロック。 スコープの性質によって、オプションの補正ブロックを同様があります。 いくつかのスコープを使用して、例外の処理だけになります、補正は必要ありません。 他のスコープを明示的にトランザクションにして、オプションの補正ハンドラーを作成すると共に、既定の補正ハンドラーが常に使用します。 既定の例外ハンドラーと任意の数の用に作成した追加の例外ハンドラー、トランザクション スコープがあります。  
  
## <a name="synchronized-scopes"></a>同期スコープ  
 スコープを同期または同期されていないことを指定することができます。 スコープを同期することによって内でアクセスがすべての共有データは書き込まれませんにオーケストレーションでの 1 つまたは複数の並列アクションでもないことに書き込まれる、別のアクションが読み取り中にことを確認します。  
  
 アトミック トランザクション スコープは常に同期します。 その例外ハンドラーのいずれかですべてのアクションとして、同期が、同期のスコープ内のすべてのアクションに扱われます。 トランザクション スコープの補正ハンドラーのアクションは同期されません。  
  
> [!CAUTION]
>  実行できることも、デッドロック状態に、プロセスを慎重にデザインしない場合に注意してください。 例: オーケストレーション A での並列の 2 つの分岐が、同じメッセージをアクセス、1 つに送信してこのため、両方を受信する同期のスコープでなければなりません。 2 番目のオーケストレーションはメッセージを受信し、返信します。 オーケストレーション A の送信元のブランチには、受信側の分岐では、前にロックを受信、デッドロックが終了ことができます。  
  
## <a name="nesting-of-scopes"></a>スコープの入れ子  
 入れ子にすることができます**スコープ**他の内部の図形**スコープ**図形。 入れ子スコープの規則は次のとおりです。  
  
-   同期スコープの例外ハンドラーを含む、同期のスコープ内では、トランザクションまたは同期スコープを入れ子にすることはできません。  
  
-   アトミック トランザクション スコープは、その内部に入れ子になった他のトランザクション スコープを持つことはできません。  
  
-   トランザクション スコープは、トランザクションでないスコープまたはオーケストレーション内で入れ子にすることはできません。  
  
-   21 レベルの深さの最大スコープを入れ子にすることができます。  
  
-   **オーケストレーションの呼び出し**図形は、スコープ内に含めることができますが、呼び出されたオーケストレーションが扱われます、トランザクションを入れ子になった他と同じと同じ規則が適用されます。  
  
-   **オーケストレーションを開始**図形はスコープ内に含めることができます。 入れ子に関する制限事項は、開始したオーケストレーションには適用されません。  
  
## <a name="scope-variables"></a>スコープ変数  
 メッセージなどの変数を宣言することができ、相関関係は、スコープ レベルで設定します。 ただし、同じオーケストレーション変数とスコープ変数の名前を使用することはできません。名前の非表示にすることはできません。  
  
## <a name="see-also"></a>参照  
 [トランザクションを使用して、例外の処理](../core/using-transactions-and-handling-exceptions.md)   
 [自動トランザクション](../core/atomic-transactions.md)