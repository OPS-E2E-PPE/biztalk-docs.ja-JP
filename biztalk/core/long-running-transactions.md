---
title: 実行時間の長いトランザクション |Microsoft ドキュメント
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
ms.openlocfilehash: 86c419c79b9de6287a0361dfe4e2e6b9dc555153
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262778"
---
# <a name="long-running-transactions"></a>長時間トランザクション
長時間トランザクションは、BizTalk オーケストレーションでよく使用される重要なコンストラクターです。 スコープ ベースのカスタム補正、スコープ ベースのカスタム例外処理、およびトランザクションの入れ子に対応した機能があり、各機能を活用することで、堅牢なトランザクション アーキテクチャをきわめて柔軟に設計することができます。  
  
 長時間トランザクションは、トランザクションの実行が長時間にわたる可能性があり、かつ完全な ACID プロパティを必要としない場合 (つまり、必ずしも他のトランザクションからデータを分離する必要がない場合) に使用します。 長時間トランザクションは、長時間にわたって非アクティブになる可能性があります。多くの場合、その原因は外部メッセージの到着の待機にあります。  
  
 長時間トランザクションには一貫性と持続性はありますが、原子性と分離性はありません。 長時間トランザクション内のデータはロックされないため、他のプロセスやアプリケーションによって変更されることがあります。 長時間にわたってロックをかけるのは実際的ではないため、状態の更新に関する分離プロパティは保持されません。  
  
 長時間トランザクションのコミットは、アトミックのトランザクションのコミットとは異なります。 結果に関して分散調整が暗黙の前提になることはありません (長時間トランザクションは単一のオーケストレーション インスタンス内にのみ存在します)。 代わりに、実行時間の長いトランザクションは、最後のステートメントが完了した時点でコミットされたと見なされます。 トランザクションが中断された場合、状態の "自動" ロールバックは行われません。 これは、例外処理および補正処理を使ったプログラムによって実現できます。  
  
 スコープでは、変数、メッセージ、および .NET コンポーネントを宣言することによってスコープ固有の状態を定義できます。 長時間トランザクションは、そのトランザクション固有のスコープやその外側のスコープの状態情報、およびオーケストレーション内でグローバルに定義されている状態情報にアクセスできます。 囲んでいない任意のスコープの状態情報へのアクセスはありません。  
  
## <a name="nesting"></a>入れ子  
 長時間トランザクションには、アトミックのトランザクションや他の長時間トランザクションを含めることができます。 入れ子の深さは任意です。 たとえば、1 つのトランザクションに他の 2 つの長時間トランザクションを含め、そのそれぞれにアトミック トランザクションを含めることができます。  
  
 入れ子は、トランザクション全体の 1 つ以上のコンポーネントをアトミックにすると同時に、トランザクション全体を長時間トランザクションにする必要がある場合に特に役立ちます。 注文書の受け取りと調達を例に考えてみます。 注文書はいつ届くかわからず、注文調達の各種手順が発生するまでに時間がかかる可能性のある状況であっても、プロセス全体を 1 つのトランザクションとして扱うことが望ましい場合があります。 この場合、トランザクション全体は明らかに長時間トランザクションにする必要がありますが、領収書発行などの個々の手順はアトミックにする必要があるケースも考えられます。  
  
> [!NOTE]
>  トランザクションでないスコープまたはオーケストレーション内でトランザクション スコープを入れ子にすることはできません。 外側のスコープまたはオーケストレーションがトランザクションでないと状態が管理されないため、内側のスコープの状態管理を適切に処理する必要があります。  
  
> [!NOTE]
>  同期トランザクションに他のトランザクションや同期スコープを含めることはできません。  
  
## <a name="compensation"></a>[補正]  
 長時間トランザクションでは、トランザクションのアクティビティをコミット後に補正するために呼び出される補正ブロックを指定できるようになっています。 可能であれば単純にトランザクションを元に戻したり、何らかの方法でトランザクションの影響を緩和する他の関数 (通知など) を実行したりすることができます。 独自の補正コードを追加しなければ、ランタイム エンジンにより既定で内側のトランザクション (長時間トランザクションとアトミックのトランザクションの両方) の補正ブロックが逆順に呼び出されます。つまり、最後にコミットされたトランザクションの補正ブロックが最初に呼び出され、最初にコミットされたトランザクションの補正ブロックが最後に呼び出されます。  
  
> [!NOTE]
>  補正の対象となるのは、正常にコミットされたトランザクションのみです。  
  
## <a name="fault-tolerance"></a>フォールト トレランス  
 トランザクションでは、内部エラー (コンピューターの障害やソフトウェア エラーなど) と外部エラー (取り消しメッセージなど) の両方の修復に対応するフォールト トレランスがサポートされています。 長時間トランザクション内の部分的な更新は ACID トランザクションであるため、トランザクション エラーが発生した場合、自動的にはロールバックされません。  
  
 エラーが発生すると、長時間トランザクションの例外コード ブロックが呼び出されます。 例外コード ブロックには、トランザクションの実行時に発生したエラーを処理するために記述する一連のエラー ハンドラーが含まれています。 メッセージ、変数、およびオブジェクトの最後に認識された状態に基づいてエラーを処理することができます。  
  
 通常は、例外発生時に例外ハンドラーでオーケストレーションの状態を評価し、その状態に基づいて必要なアクションを実行し、入れ子になっているトランザクションの補正を呼び出すことをお勧めします。  
  
 長時間トランザクションの実行は、エラーが発生した時点で中止されます。 エラーが発生したトランザクションを再開することはできません。  
  
## <a name="see-also"></a>参照  
 [実行時間の長いトランザクションの使用シナリオ](../core/scenarios-using-long-running-transactions.md)   
 [アトミック トランザクション](../core/atomic-transactions.md)   
 [トランザクションを使用して、例外の処理](../core/using-transactions-and-handling-exceptions.md)