---
title: メッセージ変数を使用して、追跡データベースのサイズを |Microsoft ドキュメント
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
ms.openlocfilehash: 5418cdf79499302e6127db7fb66f108825a0d8c0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22287842"
---
# <a name="using-message-variables-to-size-the-tracking-database"></a>メッセージ変数を使用して追跡データベースのサイズを求める方法
Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、BizTalk の追跡 (BizTalkDTADb) データベースのサイズが一定期間経過後にどのくらいのサイズになるかを、各種の変数を使って求めることができます。 これらの変数を次に示します。  
  
-   使用パイプライン数  
  
-   関連するオーケストレーション数  
  
-   生成されたイベント数  
  
-   追跡対象のメッセージ プロパティ数  
  
-   追加的に作成されるメッセージ数  
  
-   指定の期間に受け取ったメッセージの推定数  
  
 BizTalk の追跡データベースのサイズを見積もるための式はそれほど複雑なものではありません。ただし、この式は、BizTalk Server 環境で使用されるすべての受信/送信メッセージ プロセスに対して適用する必要があります。 つまり、個々のメッセージ シナリオに対してこの式を適用し、その結果を総計して初めて、最終的な推定データベース サイズを得ることができます。 このドキュメントでは、次の 2 つのシナリオを想定しています。 シナリオでは、次のとおりです。  
  
1.  メッセージを受信し、そのメッセージを変換して、結果のメッセージを送信する  
  
2.  メッセージを受信し、そのメッセージを使ってビジネス プロセスを実行して、結果のメッセージを送信する  
  
 どちらも、BizTalk Server 環境で想定されるシナリオですが、追跡データの量はシナリオによって異なります。 BizTalk Server 環境で生成される総追跡データは、これらすべてのシナリオを合計した値になります。  
  
 式に用いられている変数には、次のようなものがあります。  
  
|変数|Description|  
|--------------|-----------------|  
|**Nserv**|サービス数 (パイプライン数 + オーケストレーション数)|  
|**イベント**|生成されるメッセージ イベント数|  
|**プロパティ**|追跡対象のメッセージ プロパティ数|  
|**PropSize**|昇格させたプロパティ (フィールド) のサイズ (バイト単位)|  
|**CMsgs**|1 つの受信メッセージにつき追加的に作成されるメッセージ数|  
|**メッセージの最大数**|一定期間における受信メッセージの推定数|  
|**式の MsgSize**|メッセージのサイズ|  
|**MsgNum**|受信メッセージごとに追跡されるメッセージ数|  
  
 式は次のとおりです。  
  
```  
[((Nserv * 150 bytes) + (Events * 230 bytes) + (Properties * CMsgs*(52 bytes + PropSize))) * Msgs]/1024/1024 = Data size in MB  
```  
  
 この式では、メッセージによって生成される追跡データのみが計算されます。オーケストレーション デバッガー用に生成される追跡データは含まれません。 BizTalk の追跡データベースのサイズを見積もるには、各メッセージ プロセスに対してこの式を適用する必要があります。  
  
## <a name="see-also"></a>参照  
 [メッセージ本文を追跡する追跡データベースのサイズ変更](../core/sizing-the-tracking-database-to-track-message-bodies.md)   
 [シナリオ 1: 単純な BizTalk メッセージの追跡データベースのサイズ変更](../core/scenario-1-sizing-the-tracking-database-for-simple-biztalk-messages.md)   
 [シナリオ 2: オーケストレーションでメッセージの追跡データベースのサイズ変更](../core/scenario-2-sizing-the-tracking-database-for-messages-in-orchestrations.md)   
 [シナリオ 4: すべてのメッセージの追跡データベースのサイズ変更](../core/scenario-4-sizing-the-tracking-database-for-all-messages.md)   
 [シナリオ 3: 同報リストに送信されるメッセージの追跡データベースのサイズ変更](../core/scenario-3-size-the-tracking-database-for-messages-sent-to-distribution-lists.md)