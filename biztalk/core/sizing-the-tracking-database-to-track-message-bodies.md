---
title: "メッセージ本文の追跡に追跡データベースのサイジング |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Tracking database, database size
- message variables [Tracking database], MsgNum
- HAT, ports
- Tracking database, messages
- tracking, orchestrations
- tracking, messages
- HAT, orchestrations
- tracking, ports
ms.assetid: ee75e530-f15d-4ceb-ba67-0b0b24d9df6b
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1b5abc3f2a48f2baea5d158e1a0268a7eede51c2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="sizing-the-tracking-database-to-track-message-bodies"></a>メッセージの本文を追跡するための追跡データベースのサイズ設定
BizTalk 追跡データベースのメッセージ本文を追跡する場合は、メッセージ本文のサイズも考慮する必要があります。 次の式を使用します。  
  
```  
[Msgs * MsgNum * (MsgSize)]/1024 = Data size in MB  
```  
  
 メッセージ コンテキストの平均サイズがメッセージ サイズと比べて非常に大きい場合は、上の式の MsgSize にメッセージ コンテキストの平均サイズを追加することを検討してください。  
  
 [グループ ハブ] ページでメッセージ イベントおよびサービス インスタンスの追跡を使用し、ポート レベルまたはオーケストレーション レベルの追跡機能を有効にすることで、MsgNum 変数が決まります。 この式は、各メッセージ プロセスにも適用する必要があります。  
  
## <a name="see-also"></a>参照  
 [追跡データベースのサイズをメッセージ変数を使用](../core/using-message-variables-to-size-the-tracking-database.md)   
 [シナリオ 1: 単純な BizTalk メッセージの追跡データベースのサイズ変更](../core/scenario-1-sizing-the-tracking-database-for-simple-biztalk-messages.md)   
 [シナリオ 2: オーケストレーションでメッセージの追跡データベースのサイズ変更](../core/scenario-2-sizing-the-tracking-database-for-messages-in-orchestrations.md)   
 [シナリオ 4: すべてのメッセージの追跡データベースのサイズ変更](../core/scenario-4-sizing-the-tracking-database-for-all-messages.md)   
 [シナリオ 3: 同報リストに送信されるメッセージの追跡データベースのサイズ変更](../core/scenario-3-size-the-tracking-database-for-messages-sent-to-distribution-lists.md)