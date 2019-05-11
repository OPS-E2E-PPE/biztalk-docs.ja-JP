---
title: 'シナリオ 2: オーケストレーション内のメッセージの追跡データベースのサイズ調整 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Tracking database, database size
ms.assetid: d1cfb8b9-d4e2-4069-8db3-18f72358652b
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2e3a62df0431611c294a123835d7cc2faddca474
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65308612"
---
# <a name="scenario-2-sizing-the-tracking-database--for-messages-in-orchestrations"></a>シナリオ 2: オーケストレーション内のメッセージの追跡データベースのサイズ調整
オーケストレーションを含む例を見てみましょう。 次の図は、ビジネス プロセス全体を表示します。 このシナリオでメッセージが BizTalk Server に、オーケストレーションを通じて送信されますが、オーケストレーション内で変更および送信ポート経由送信されます。  
  
 ![BizTalk Server メッセージ プロセス](../core/media/biztalk-server-message-process.gif "BizTalk_Server_Message_Process")  
  
 **BizTalk Server メッセージ プロセス**  
  
 このシナリオに関するファクトの一部を次に示します。  
  
- メッセージ サイズは、5 K です。  
  
- 私たちは任意のプロパティを昇格しません。  
  
- 1 年間に受信メッセージの数は、350万です。  
  
- すべてのイベントの追跡がオンになっているとします。 このシナリオには、6 つのイベントがあります。  
  
  -   メッセージ M0 の受信  
  
  -   受信ポートからメッセージ M1 の出力  
  
  -   オーケストレーションによるメッセージ M1 の受信  
  
  -   オーケストレーションからのメッセージ M2 の出力  
  
  -   送信ポートによるメッセージ M2 の受信  
  
  -   送信パイプラインによるメッセージ M3 の出力  
  
- このシナリオでは、3 つの追加メッセージが作成されます。 メッセージ M0 は受信メッセージを BizTalk Server によって作成されませんが。 M1、M2 の受信ポートから出力メッセージは、メッセージがオーケストレーションからの出力メッセージと M3 は送信ポートから出力メッセージです。  
  
  式にこの情報を適用するには、次の結果が得られます。  
  
```  
[(3*150 bytes) + (6*230 bytes) + (0*0(52 bytes + 0) * 3,500,000]/1024/1024  
[(450 + 1380 + 0) * 3,500,000]/1024/1024 = 6108 MB ~ 5.96 GB per year  
```  
  
## <a name="messages-in-orchestrations-with-a-single-promoted-property"></a>1 つ昇格させたプロパティを使用してオーケストレーション内のメッセージ  
 これで、先ほどの例のように、このシナリオの 1 つのフィールドを昇格させてみましょう。 昇格させたプロパティは、約 10 バイトです。 これで、式のようになります。  
  
```  
[((3*150 bytes) + (6*230 bytes) + (1*3*(52 bytes + 10 bytes)) * 3,500,000]/1024/1024  
[(450 + 1380 + 186) * 3,500,000]/1024/1024 = 6729 MB ~ 6.57 GB per year  
```  
  
 サイズの 20 バイトである追加のプロパティを昇格させる必要がある場合、数式はこれのようになります。  
  
```  
[(3*150 bytes) + (6*230 bytes) + ((1*3*(52 bytes + 10 bytes) + (1*3*(52 bytes + 20 bytes)) * 3,500,000]/1024/1024  
[(450 + 1380 + 372) * 3,500,000]/1024/1024 = 7350 MB ~ 7.18 GB per year  
```  
  
## <a name="messages-in-orchestrations-with-message-body-tracking-activated"></a>メッセージ本文の追跡でオーケストレーション内のメッセージがアクティブ化  
 メッセージの追跡する場合は、必要な追加の領域の計算結果と同じです、結果、前述のシナリオまたは 50.1 GB で 1 年間。  
  
## <a name="see-also"></a>参照  
 [追跡データベースのサイズにメッセージ変数を使用します。](../core/using-message-variables-to-size-the-tracking-database.md)   
 [メッセージ本文を追跡する追跡データベースのサイズ調整](../core/sizing-the-tracking-database-to-track-message-bodies.md)   
 [シナリオ 1: 単純な BizTalk メッセージの追跡データベースのサイズ調整](../core/scenario-1-sizing-the-tracking-database-for-simple-biztalk-messages.md)   
 [シナリオ 4:すべてのメッセージの追跡データベースのサイズ調整](../core/scenario-4-sizing-the-tracking-database-for-all-messages.md)   
 [シナリオ 3:配布リストに送信されるメッセージの追跡データベースのサイズ調整](../core/scenario-3-size-the-tracking-database-for-messages-sent-to-distribution-lists.md)