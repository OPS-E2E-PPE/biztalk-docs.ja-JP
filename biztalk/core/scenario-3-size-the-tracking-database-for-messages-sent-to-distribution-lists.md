---
title: 'シナリオ 3: 配布リストにメッセージが出力を送信の追跡データベースのサイズ調整 |Microsoft Docs'
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
ms.openlocfilehash: b757f262077bbd4185cda312f479d08ef7a3229c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65308499"
---
# <a name="scenario-3-sizing-the-tracking-database--for-messages-sent-out-to-distribution-lists"></a>シナリオ 3: 配布リストに送信されるメッセージの追跡データベースのサイズ調整
次の図では、オーケストレーション処理の適用し、オーケストレーション内で変更が、同報リストを通じて複数の送信ポートに送信し、メッセージがあります。  
  
 ![複数のポートにオーケストレーションでメッセージを](../core/media/biztalk-server-message-orch-multiple-ports.gif "BizTalk_Server_message_orch_multiple_ports")  
  
 **オーケストレーション処理の適用し、複数のポートに送信するメッセージを BizTalk Server**  
  
 このシナリオに関するファクトの一部を次に示します。  
  
- メッセージ サイズは、10 K です。  
  
- 任意のプロパティは昇格しません。  
  
- 1 年間に受信したメッセージの数は、350万です。  
  
- すべてのイベントの追跡がオンになっているとします。 このシナリオには、5 つのイベントがあります。  
  
  -   メッセージ M0 の受信  
  
  -   受信ポートからメッセージ M1 の出力  
  
  -   送信ポートによるメッセージ M3 の出力  
  
  -   送信ポートによるメッセージ M4 の出力  
  
  -   送信ポートによるメッセージ M5 の出力  
  
  式にこの情報を適用するには、次の。  
  
```  
[(5*252 bytes) + (10*182 bytes) + (0*5(40 bytes + 0) * 3,500,000]/1024/1024  
[(1620 + 1820 + 0) * 3,500,000]/1024/1024 = 10280.61 MB ~ 10.04 GB per year  
```  
  
## <a name="messages-in-an-orchestration-that-are-sent-out-to-a-distribution-list-with-a-single-promoted-property"></a>オーケストレーション内の 1 つ昇格させたプロパティを使用して、配布リストに送信されるメッセージ  
 この例では、前述のシナリオで行ったようは、1 つのプロパティ、サイズ、約 10 バイトみましょうを昇格させます。 これで、式のようになります。  
  
```  
[((5*150 bytes) + (10*230 bytes) + (1*5(52 bytes + 10 bytes)) * 3,500,000]/1024/1024  
[(750 + 2300 + 260) * 3,500,000]/1024/1024 = 11048 MB ~ 10.79 GB per year  
```  
  
 サイズの 20 バイトである追加のプロパティを昇格する場合、式を今すぐようになります。  
  
```  
[((5*150 bytes) + (10*230 bytes) + ((1*5(52 bytes + 10 bytes) + (1*5(52 bytes + 20 bytes)) * 3,500,000]/1024/1024  
[(750 + 2300 + 670) * 3,500,000]/1024/1024 = 12417 MB ~ 12.13 GB per year  
```  
  
## <a name="messages-in-an-orchestration-that-are-sent-out-to-a-distribution-list-with-message-body-tracking-activated"></a>送信されるオーケストレーション内のメッセージの配布リストをメッセージ本文の追跡とアクティブ化  
 メッセージの追跡する場合、式は次の例を次のようになります。  
  
```  
[3,500,000 * 6 * 5KB]/1024 = 102539.06 MB ~ 100.14 GB per year  
  
```  
  
## <a name="see-also"></a>参照  
 [追跡データベースのサイズにメッセージ変数を使用します。](../core/using-message-variables-to-size-the-tracking-database.md)   
 [メッセージ本文を追跡する追跡データベースのサイズ調整](../core/sizing-the-tracking-database-to-track-message-bodies.md)   
 [シナリオ 1: 単純な BizTalk メッセージの追跡データベースのサイズ調整](../core/scenario-1-sizing-the-tracking-database-for-simple-biztalk-messages.md)   
 [シナリオ 2: オーケストレーション内のメッセージの追跡データベースのサイズ調整](../core/scenario-2-sizing-the-tracking-database-for-messages-in-orchestrations.md)   
 [シナリオ 4:すべてのメッセージの追跡データベースのサイズ調整](../core/scenario-4-sizing-the-tracking-database-for-all-messages.md)