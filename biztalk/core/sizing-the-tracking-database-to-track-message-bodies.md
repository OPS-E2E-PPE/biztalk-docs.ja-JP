---
title: メッセージ本文の追跡を追跡データベースのサイズ調整 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9d25a93548cdf98db3a40156bcd0dd0aff4d11b9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401865"
---
# <a name="sizing-the-tracking-database-to-track-message-bodies"></a>メッセージ本文を追跡する追跡データベースのサイズ調整
BizTalk 追跡データベースでメッセージ本文を追跡する場合は、計算でこれらの本文のサイズを考慮する必要があります。 次の式を使用します。  
  
```  
[Msgs * MsgNum * (MsgSize)]/1024 = Data size in MB  
```  
  
 メッセージのサイズと比較したことが重要な場合は、上記の式の MsgSize にメッセージ コンテキストの平均サイズを追加することを検討してください。  
  
 MsgNum 変数は、ポート レベルまたはメッセージ イベントおよびグループ ハブ ページでサービス インスタンスの追跡を使用してオーケストレーション レベルの追跡機能を有効にして決まります。 次の数式を適用すると、各メッセージ プロセスもあります。  
  
## <a name="see-also"></a>参照  
 [追跡データベースのサイズにメッセージ変数を使用します。](../core/using-message-variables-to-size-the-tracking-database.md)   
 [シナリオ 1: 単純な BizTalk メッセージの追跡データベースのサイズ調整](../core/scenario-1-sizing-the-tracking-database-for-simple-biztalk-messages.md)   
 [シナリオ 2: オーケストレーション内のメッセージの追跡データベースのサイズ調整](../core/scenario-2-sizing-the-tracking-database-for-messages-in-orchestrations.md)   
 [シナリオ 4:すべてのメッセージの追跡データベースのサイズ調整](../core/scenario-4-sizing-the-tracking-database-for-all-messages.md)   
 [シナリオ 3:配布リストに送信されるメッセージの追跡データベースのサイズ調整](../core/scenario-3-size-the-tracking-database-for-messages-sent-to-distribution-lists.md)