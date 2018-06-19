---
title: 'シナリオ 2: オーケストレーションでメッセージの追跡データベースのサイズ変更 |Microsoft ドキュメント'
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
ms.openlocfilehash: 62ea6e463dfb3a44e2628f57b632634d7a9bd212
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269834"
---
# <a name="scenario-2-sizing-the-tracking-database--for-messages-in-orchestrations"></a>シナリオ 2: オーケストレーションでメッセージの追跡データベースのサイズ変更
オーケストレーションを含む例を見てみましょう。 次の図は、ビジネス プロセス全体を示しています。 このシナリオでは、メッセージが BizTalk Server に格納され、オーケストレーションを通じて送信されます。メッセージは、オーケストレーション内で変更され、送信ポートを通じて送信されます。  
  
 ![BizTalk Server メッセージ プロセス](../core/media/biztalk-server-message-process.gif "BizTalk_Server_Message_Process")  
  
 **BizTalk Server メッセージ プロセス**  
  
 このシナリオに関するファクトの一部を次に示します。  
  
-   メッセージのサイズは、5 K です。  
  
-   私たちは任意のプロパティを昇格しません。  
  
-   1 年間に受信メッセージの数は、350万件です。  
  
-   追跡は、すべてのイベントに対して有効になっています。 このシナリオには、次の 6 つのイベントがあります。  
  
    -   メッセージ M0 の受信  
  
    -   受信ポートからのメッセージ M1 の出力  
  
    -   オーケストレーションによるメッセージ M1 の受信  
  
    -   オーケストレーションからのメッセージ M2 の出力  
  
    -   送信ポートによるメッセージ M2 の受信  
  
    -   送信パイプラインからのメッセージ M3 の出力  
  
-   このシナリオでは、3 つの追加メッセージが作成されます。 メッセージ M0 は受信メッセージであり、BizTalk Server によって作成されるものではありません。 メッセージ M1 は、受信ポートからの出力メッセージです。メッセージ M2 は、オーケストレーションからの出力メッセージです。メッセージ M3 は、転送ポートからの出力メッセージです。  
  
 式にこの情報を適用するには、次の結果が得られます。  
  
```  
[(3*150 bytes) + (6*230 bytes) + (0*0(52 bytes + 0) * 3,500,000]/1024/1024  
[(450 + 1380 + 0) * 3,500,000]/1024/1024 = 6108 MB ~ 5.96 GB per year  
```  
  
## <a name="messages-in-orchestrations-with-a-single-promoted-property"></a>オーケストレーション内のメッセージ (プロパティを 1 つ昇格した場合)  
 前述の例のように、このシナリオのフィールドを 1 つ昇格してみましょう。 昇格させるプロパティのサイズは、約 10 バイトです。 次のような式のようになりました。  
  
```  
[((3*150 bytes) + (6*230 bytes) + (1*3*(52 bytes + 10 bytes)) * 3,500,000]/1024/1024  
[(450 + 1380 + 186) * 3,500,000]/1024/1024 = 6729 MB ~ 6.57 GB per year  
```  
  
 サイズの 20 バイトである追加のプロパティを昇格させる必要がある場合、数式は次のようになります。  
  
```  
[(3*150 bytes) + (6*230 bytes) + ((1*3*(52 bytes + 10 bytes) + (1*3*(52 bytes + 20 bytes)) * 3,500,000]/1024/1024  
[(450 + 1380 + 372) * 3,500,000]/1024/1024 = 7350 MB ~ 7.18 GB per year  
```  
  
## <a name="messages-in-orchestrations-with-message-body-tracking-activated"></a>オーケストレーション内のメッセージ (メッセージ本文の追跡を有効にした場合)  
 メッセージの追跡を行う場合、必要な追加領域の計算結果は、前述のシナリオの結果 (1 年ごとに 50.1 GB) と同じです。  
  
## <a name="see-also"></a>参照  
 [追跡データベースのサイズをメッセージ変数を使用](../core/using-message-variables-to-size-the-tracking-database.md)   
 [メッセージ本文を追跡する追跡データベースのサイズ変更](../core/sizing-the-tracking-database-to-track-message-bodies.md)   
 [シナリオ 1: 単純な BizTalk メッセージの追跡データベースのサイズ変更](../core/scenario-1-sizing-the-tracking-database-for-simple-biztalk-messages.md)   
 [シナリオ 4: すべてのメッセージの追跡データベースのサイズ変更](../core/scenario-4-sizing-the-tracking-database-for-all-messages.md)   
 [シナリオ 3: 同報リストに送信されるメッセージの追跡データベースのサイズ変更](../core/scenario-3-size-the-tracking-database-for-messages-sent-to-distribution-lists.md)