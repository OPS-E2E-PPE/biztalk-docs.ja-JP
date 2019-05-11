---
title: 実行時間の長いトランザクション |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- long-running transactions, about long-running transactions
- atomic transactions, long-running transactions
- long-running transactions, orchestrations
- long-running transactions, nesting
- scopes, examples
- orchestrations, transactions
- compensations, long-running transactions
- compensations, customizing
- transactions, long-running
- transactions, compensation blocks
- long-running transactions
- long-running transactions, timeouts
- compensations, examples
- fault tolerance, long-running transactions
- transactions, examples
- orchestrations, long-running transactions
- transactions, atomic
- transactions, fault tolerance
- scopes, long-running transactions
- long-running transactions, fault tolerance
- transactions, nesting
- examples, scopes
ms.assetid: 4bf4d0c8-903a-411f-963b-bd4cfdfc2958
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 99fb048c158b758e125d82f50ce2771bf0ede94f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65330389"
---
# <a name="long-running-transactions"></a>長時間トランザクション
実行時間の長いトランザクションとは、BizTalk オーケストレーションでの重要な一般的に使用の構成要素です。 スコープ ベースのカスタム補正、スコープに基づくカスタム例外処理、およびすべての柔軟で堅牢なトランザクション アーキテクチャの設計、トランザクションを入れ子に機能するための機能を提供します。  
  
 トランザクションが長時間にわたって実行する必要があり、完全な ACID プロパティを必要としないときに、実行時間の長いトランザクションを使用する (つまり、する必要はありません他のトランザクションからデータの分離を保証するために)。 長期間続いた場合、外部メッセージが到着するを待つためには、多くの場合、実行時間の長いトランザクションがあります。  
  
 実行時間の長いトランザクションの一貫性と持続性がいない原子性と分離を持ちます。 実行時間の長いトランザクション内でデータがロックされていません。他のプロセスやアプリケーションを変更できます。 ロックを保持する時間が長くなるが実用的でないために、状態の更新に関する分離プロパティは保持されません。  
  
 実行時間の長いトランザクションのコミットメントは、アトミック トランザクションのコミットメントと異なります。 (1 つのオーケストレーション インスタンス内でのみ実行時間の長いトランザクションが存在する) 結果に関して分散調整の暗黙的な前提はありません。 代わりに、実行時間の長いトランザクションは、その最後のステートメントが完了した時点でコミットされたと見なされます。 トランザクションが中断された場合、状態の「自動」ロールバックはありません。 この操作は、例外処理および補正ハンドラーを使用してプログラムによって実現できます。  
  
 スコープは、変数、メッセージ、および .NET コンポーネントを宣言することで、独自の状態を定義できます。 実行時間の長いトランザクションでは、独自のスコープ、任意のスコープを囲む、および、オーケストレーション内でグローバルに定義されているすべての状態情報の状態情報へのアクセス権を持ちます。 囲んでいない任意のスコープの状態情報へのアクセスはありません。  
  
## <a name="nesting"></a>入れ子  
 実行時間の長いトランザクションはアトミックのトランザクションやその他の実行時間の長いトランザクションに含めることができます。 これらは、任意の深さに入れ子にできます。 たとえば、トランザクションには、それぞれのアトミック トランザクションを含めることがあります、その他の 2 つの実行時間の長いトランザクションが含まれます。  
  
 入れ子が 1 つの場合に特に役立ちますか、トランザクション全体の複数のコンポーネントはトランザクション全体が長期間実行する必要がありますにアトミックである必要があります。 受け取りと調達、注文書の使用例を検討してください。 注文書は、いつでも関係なく着信できると、注文のさまざまな手順が発生する時間をかかる場合がありますが、プロセス全体をトランザクションとして処理します。 全体的なトランザクションここで明確にする必要がある実行時間の長いが、領収など、個々 のステップがアトミックである必要があります。  
  
> [!NOTE]
>  スコープまたはトランザクションでないオーケストレーション内でトランザクション スコープを入れ子にすることはできません。 外側のスコープまたはオーケストレーションがトランザクションでない状態が管理されない、ように、内側のスコープの状態管理を適切に処理する必要があります。  
  
> [!NOTE]
>  同期トランザクションや同期スコープを他のトランザクションを含めることはできません。  
  
## <a name="compensation"></a>補正  
 実行時間の長いトランザクションはコミット後のトランザクションのアクティビティを補正するために呼び出される補正ブロックを指定できます。 可能であれば、トランザクションを元に戻す、何らかの方法でトランザクションの影響を軽減できます通知など、他の機能を実行またはその可能性がありますだけです。 独自の補正コードを追加しない場合、ランタイム エンジンが既定では呼び出し実行時間の長いと、アトミックの内側のトランザクションの補正ブロック逆の順序で最後にコミットされたトランザクションを開始および終了した後、最初のトランザクションのコミットします。  
  
> [!NOTE]
>  補正は、正常にコミットされたトランザクションでのみ実行できます。  
  
## <a name="fault-tolerance"></a>フォールト トレランス  
 トランザクションは、内部エラー (コンピューターの障害やソフトウェア障害) などと外部エラー (取り消しメッセージなど) の両方からの復旧のフォールト トレランスをサポートします。 実行時間の長いトランザクション内での部分的な更新プログラムはロールバックされません自動的にトランザクションに失敗した場合、ACID トランザクションのようにします。  
  
 実行時間の長いトランザクションの例外コード ブロックは、障害が発生したときに呼び出されます。 例外コード ブロックには、一連エラー ハンドラーを記述すると、トランザクションの実行時に発生するエラーの処理にはが含まれています。 メッセージ、変数、およびエラーを処理内のオブジェクトの最後の既知の状態を利用できます。  
  
 例外が発生した時にオーケストレーションの状態の評価をその状態に基づいて必要なアクションを実行し、入れ子になったトランザクションの補正を呼び出す例外ハンドラーは通常します。  
  
 エラーが発生した場合は、実行時間の長いトランザクションの実行が中断されます。 エラーが発生した後に再開できません。  
  
## <a name="see-also"></a>参照  
 [実行時間の長いトランザクションの使用シナリオ](../core/scenarios-using-long-running-transactions.md)   
 [アトミック トランザクション](../core/atomic-transactions.md)   
 [トランザクションの使用と例外の処理](../core/using-transactions-and-handling-exceptions.md)