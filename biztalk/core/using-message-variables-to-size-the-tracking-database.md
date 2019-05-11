---
title: メッセージ変数を使用して、追跡データベースのサイズを |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- message variables [Tracking database], CMsgs
- message variables [Tracking database], Events
- message variables [Tracking database], Properties
- Tracking database, database size
- message variables [Tracking database], Nserv
- message variables [Tracking database], Msgs
- message variables [Tracking database], PropSize
- message variables [Tracking database]
- message variables [Tracking database], MsgSize
- message variables [Tracking database], MsgNum
- Tracking database, messages
ms.assetid: 2d31ae25-3d16-4002-b5a5-dca25e764ecd
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8ac96e6784ed73dce415c78ff5f559d52be42395
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396833"
---
# <a name="using-message-variables-to-size-the-tracking-database"></a>追跡データベースのサイズにメッセージ変数を使用します。
Microsoft で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、大きさ、BizTalk 追跡 (BizTalkDTADb) データベースになるか、指定した期間にわたって変数の数を使用することができます。 これらの変数は次のとおりです。  
  
- 使用パイプライン数  
  
- 関連するオーケストレーションの数  
  
- 生成されたイベント数  
  
- 追跡メッセージのプロパティの数  
  
- 作成された追加のメッセージの数  
  
- 指定した時間帯で受信したメッセージの推定数  
  
  BizTalk 追跡データベースのサイズの見積もりに使用する数式は容易ですが、中には、BizTalk Server の実装を使用する各メッセージの受信および送信プロセスに適用する必要があります。 つまり、個々 のメッセージ シナリオのこの式を適用し、最終的な推定データベース サイズを取得する結果を追加する必要があります。 このドキュメントでは、2 つのシナリオに注目します。 シナリオでは、次のとおりです。  
  
1. メッセージの受信や、メッセージに変換し、結果のメッセージを送信します。  
  
2. 結果のメッセージを送信し、メッセージを使用してビジネス プロセスを実行しているメッセージを受信します。  
  
   BizTalk Server のインストールに存在するこれら両方のシナリオがあり、各シナリオは、追跡データのさまざまな量を生成します。 BizTalk Server のインストール用に生成されたデータの追跡の合計は、すべてのシナリオの合計です。  
  
   以下は、式で使用されるいくつかの変数です。  
  
|変数|説明|  
|--------------|-----------------|  
|**Nserv**|複数のサービス (パイプラインの数) + オーケストレーション数|  
|**イベント**|生成されたメッセージのイベントの数|  
|**Properties**|追跡メッセージのプロパティの数|  
|**PropSize**|サイズ (バイト単位)、昇格させたプロパティ (フィールド)|  
|**CMsgs**|受信メッセージごとに作成された追加のメッセージの数|  
|**メッセージ数**|特定の期間中に受信メッセージの推定数|  
|**式の MsgSize**|メッセージ サイズ|  
|**MsgNum**|受信メッセージごとに追跡されるメッセージ数|  
  
 式は次のとおりです。  
  
```  
[((Nserv * 150 bytes) + (Events * 230 bytes) + (Properties * CMsgs*(52 bytes + PropSize))) * Msgs]/1024/1024 = Data size in MB  
```  
  
 この式は、メッセージによって生成される追跡データのみを計算し、オーケストレーション デバッガーに対して生成された追跡データは含まれません。 BizTalk 追跡データベースのサイズを推定するには、各メッセージ プロセスには、次の数式を適用する必要があります。  
  
## <a name="see-also"></a>参照  
 [メッセージ本文を追跡する追跡データベースのサイズ調整](../core/sizing-the-tracking-database-to-track-message-bodies.md)   
 [シナリオ 1: 単純な BizTalk メッセージの追跡データベースのサイズ調整](../core/scenario-1-sizing-the-tracking-database-for-simple-biztalk-messages.md)   
 [シナリオ 2: オーケストレーション内のメッセージの追跡データベースのサイズ調整](../core/scenario-2-sizing-the-tracking-database-for-messages-in-orchestrations.md)   
 [シナリオ 4:すべてのメッセージの追跡データベースのサイズ調整](../core/scenario-4-sizing-the-tracking-database-for-all-messages.md)   
 [シナリオ 3:配布リストに送信されるメッセージの追跡データベースのサイズ調整](../core/scenario-3-size-the-tracking-database-for-messages-sent-to-distribution-lists.md)