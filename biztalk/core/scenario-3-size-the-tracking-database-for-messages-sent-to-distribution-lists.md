---
title: 'シナリオ 3: メッセージは、同報リストに出力を送信の追跡データベースのサイズ変更 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Tracking database, database size
ms.assetid: bc6e0da0-46d1-42d6-8ec9-29a28719fbb3
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dca1722e24e0c76c85699ea00fcf6ffc120b2e14
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="scenario-3-sizing-the-tracking-database--for-messages-sent-out-to-distribution-lists"></a>シナリオ 3: 同報リストに送信されるメッセージの追跡データベースのサイズ変更
次の図では、オーケストレーションによって変更されたメッセージが、同報リストを通じて複数の送信ポートに送られています。  
  
 ![複数のポートに、オーケストレーションでメッセージ](../core/media/biztalk-server-message-orch-multiple-ports.gif "BizTalk_Server_message_orch_multiple_ports")  
  
 **オーケストレーション処理の適用し、複数のポートに送信する BizTalk Server メッセージ**  
  
 このシナリオに関するファクトの一部を次に示します。  
  
-   メッセージのサイズは、10 K です。  
  
-   プロパティは昇格しません。  
  
-   1 年に受け取るメッセージ数は、350 万件です。  
  
-   追跡は、すべてのイベントに対して有効になっています。 このシナリオには次に示す 5 つのイベントがあります。  
  
    -   メッセージ M0 の受信  
  
    -   受信ポートからのメッセージ M1 の出力  
  
    -   送信ポートによるメッセージ M3 の出力  
  
    -   送信ポートによるメッセージ M4 の出力  
  
    -   送信ポートによるメッセージ M5 の出力  
  
 この情報を適用する数式には、次。  
  
```  
[(5*252 bytes) + (10*182 bytes) + (0*5(40 bytes + 0) * 3,500,000]/1024/1024  
[(1620 + 1820 + 0) * 3,500,000]/1024/1024 = 10280.61 MB ~ 10.04 GB per year  
```  
  
## <a name="messages-in-an-orchestration-that-are-sent-out-to-a-distribution-list-with-a-single-promoted-property"></a>同報リストに送信されるオーケストレーション内のメッセージ (プロパティを 1 つ昇格した場合)  
 前述のシナリオについて、サイズが約 10 バイトのプロパティを 1 つ昇格させてみましょう。 次のような式のようになりました。  
  
```  
[((5*150 bytes) + (10*230 bytes) + (1*5(52 bytes + 10 bytes)) * 3,500,000]/1024/1024  
[(750 + 2300 + 260) * 3,500,000]/1024/1024 = 11048 MB ~ 10.79 GB per year  
```  
  
 サイズが 20 バイトのプロパティを追加で昇格する場合、式は次のようになります。  
  
```  
[((5*150 bytes) + (10*230 bytes) + ((1*5(52 bytes + 10 bytes) + (1*5(52 bytes + 20 bytes)) * 3,500,000]/1024/1024  
[(750 + 2300 + 670) * 3,500,000]/1024/1024 = 12417 MB ~ 12.13 GB per year  
```  
  
## <a name="messages-in-an-orchestration-that-are-sent-out-to-a-distribution-list-with-message-body-tracking-activated"></a>同報リストに送信されるオーケストレーション内のメッセージ (メッセージ本文の追跡を有効にした場合)  
 この例でメッセージの追跡を有効にした場合、式は次のようになります。  
  
```  
[3,500,000 * 6 * 5KB]/1024 = 102539.06 MB ~ 100.14 GB per year  
  
```  
  
## <a name="see-also"></a>参照  
 [追跡データベースのサイズをメッセージ変数を使用](../core/using-message-variables-to-size-the-tracking-database.md)   
 [メッセージ本文を追跡する追跡データベースのサイズ変更](../core/sizing-the-tracking-database-to-track-message-bodies.md)   
 [シナリオ 1: 単純な BizTalk メッセージの追跡データベースのサイズ変更](../core/scenario-1-sizing-the-tracking-database-for-simple-biztalk-messages.md)   
 [シナリオ 2: オーケストレーションでメッセージの追跡データベースのサイズ変更](../core/scenario-2-sizing-the-tracking-database-for-messages-in-orchestrations.md)   
 [シナリオ 4: すべてのメッセージの追跡データベースのサイズ変更](../core/scenario-4-sizing-the-tracking-database-for-all-messages.md)