---
title: "ビジネス プロセス管理ソリューションでの処理を中断 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- processing, pausing
- process management solution tutorial, pausing processing
ms.assetid: 23ce7617-f705-4b7d-8447-221dec9fb196
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 78b98eae8ee9cbb43354c1cfc48710c70969a929
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="interrupt-handling-in-the-business-process-management-solution"></a>ビジネス プロセス管理ソリューションでの処理を中断します。
このセクションでは、ビジネス プロセス管理ソリューションで使用される割り込み処理のメカニズムについて説明します。 割り込みメカニズムを使用すると、注文の更新時または取り消し時に注文処理を停止できます。  
  
## <a name="interrupt-handling"></a>割り込み処理  
 処理ステージを実装しているオーケストレーションは、オーケストレーションを呼び出す**CheckInterrupt**プロセスの他の部分から割り込み要求をテストします。 **CheckInterrupt**オーケストレーションから成る、**リッスン**図形です。 1 つの分岐、**リッスン**図形では、現在の順序と同じ関連付け ID を持つメッセージを確認します。 このようなメッセージがある場合、 **CheckInterrupt**オーケストレーションが受信確認メッセージを送信し、実行、**スロー**図形です。 のブランチを**リッスン**図形に実行されます左から右、右の分岐に遅延が表示されます。 遅延時間がゼロ (0) であることに注意してください。  
  
 組み合わせ、**リッスン**図形、受信分岐、および遅延分岐により、オーケストレーションにメッセージを確認します。 割り込みメッセージがある場合、左の分岐が実行されます。 メッセージがない場合は、右側の分岐が実行し、呼び出し元のオーケストレーションに返します。 割り込みメッセージは、いつでも送信できます。 **CheckInterrupt**オーケストレーションは、場合によっては、ある可能性があります待つ割り込みメッセージのみを実行します。  
  
 **OrderManager**を呼び出して、割り込みを設定、 **Interrupter**オーケストレーションです。 **Interrupter**割り込みメッセージを送信するオーケストレーション、 **InterruptPort**し、応答を待機します。 オーケストレーションを使用して、**タイムアウト**囲んでいるプロパティ**スコープ**図形を応答が受信されない場合、ループを再開します。 このオーケストレーションは、応答を受信する前にスコープがタイムアウトする限り、割り込みメッセージの送信を続けます。 タイムアウトは、要求がサブスクリプションと合致したが、応答する時間がないことを示します。 ループ終了、応答がある場合、またはへのサブスクリプションが存在しない場合、 **InterruptPort**です。  
  
 要求-応答-完了パターン、 **OrderManager**処理ステージでの使用は、割り込み処理の重要な部分です。 **OrderManager**の応答を待機: 受信確認 — はステージからは、ステージの操作を続行する前に実行が開始されたことを認識します。 これにより、ステージを開始する前に割り込みを受信することを防止します。 これにより、また、 **OrderManager**割り込みに対するサブスクリプションがない場合、ステージが完了したことを確認します。  
  
## <a name="see-also"></a>参照  
 [ビジネス プロセス管理ソリューションでの処理](../core/processing-in-the-business-process-management-solution.md)   
 [プロセス マネージャのロジック](../core/process-manager-logic.md)   
 [ExceptionHandler オーケストレーション](../core/the-exceptionhandler-orchestration.md)