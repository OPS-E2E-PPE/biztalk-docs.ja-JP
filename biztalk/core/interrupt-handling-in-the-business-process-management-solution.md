---
title: 割り込み、ビジネス プロセス管理ソリューションでの処理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- processing, pausing
- process management solution tutorial, pausing processing
ms.assetid: 23ce7617-f705-4b7d-8447-221dec9fb196
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9e064c86c5546bac55eb564db12ec43d3f1c16d5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65331386"
---
# <a name="interrupt-handling-in-the-business-process-management-solution"></a>ビジネス プロセス管理ソリューションでの処理を中断します。
このセクションでは、割り込み処理のビジネス プロセス管理ソリューションで使用される機構について説明します。 割り込みメカニズムを使用するには、注文、注文が更新または取り消されたときの処理を停止することができます。  
  
## <a name="interrupt-handling"></a>割り込み処理  
 処理ステージを実装するオーケストレーションは、オーケストレーションを呼び出す**CheckInterrupt**プロセスの他の部分から割り込み要求をテストします。 **CheckInterrupt**オーケストレーションから成る、**リッスン**図形。 1 つの分岐、**リッスン**図形が、現在の順序と同じ相関関係 ID を持つメッセージを確認します。 このようなメッセージがある場合、 **CheckInterrupt**オーケストレーションが受信確認メッセージを送信し、実行、**スロー**図形。 にブランチを**リッスン**図形が実行されて左から右、右の分岐に遅延が表示されます。 遅延は、ゼロ (0) であることを確認します。  
  
 組み合わせ、**リッスン**図形、受信分岐、および遅延分岐は、オーケストレーションがメッセージを確認します。 割り込みメッセージがある場合、左の分岐を実行します。 メッセージがない場合、右の分岐は実行し、呼び出し元オーケストレーションに返します。 中断メッセージは、いつでも送信できます。 **CheckInterrupt**オーケストレーションは、場合によっては、する可能性がありますを待つ割り込みメッセージのみを実行します。  
  
 **OrderManager**割り込みを呼び出すことによって設定、 **Interrupter**オーケストレーションします。 **Interrupter**割り込みメッセージを送信するオーケストレーション、 **InterruptPort**し返信を待ちます。 オーケストレーションを使用して、**タイムアウト**を囲むプロパティ**スコープ**図形を応答が受信されない場合、ループを再開します。 オーケストレーションは、応答を受信する前にスコープがタイムアウトする限り、割り込みメッセージを送信し続けます。 タイムアウトは、応答する時間がありませんでしたが、要求に一致するサブスクリプションをことを示します。 ループの終了、返信がある場合、またはサブスクリプションがない場合、 **InterruptPort**します。  
  
 要求-応答-完了パターン、 **OrderManager**処理ステージでの使用は、割り込み処理の重要な部分です。 **OrderManager**の応答を待機: 受信確認 — の段階からは、ステージで、続行する前に実行が開始されたことを認識します。 これは、段階を開始する前に、割り込みを受信できないことが保証されます。 これにより、 **OrderManager**割り込みに対するサブスクリプションがない場合は、ステージが完了したことを確認します。  
  
## <a name="see-also"></a>参照  
 [ビジネス プロセス管理ソリューションでの処理](../core/processing-in-the-business-process-management-solution.md)   
 [プロセス マネージャのロジック](../core/process-manager-logic.md)   
 [ExceptionHandler オーケストレーション](../core/the-exceptionhandler-orchestration.md)