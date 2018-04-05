---
title: 'シナリオ 1: 単純な BizTalk メッセージの追跡データベースのサイズ変更 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Tracking database, database size
ms.assetid: 5b8fed48-d9c9-4d1f-a320-d3e23b8b1ec9
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7b9c99c99485e34f95c6f6a75b86170d73678518
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="scenario-1-sizing-the-tracking-database--for-simple-biztalk-messages"></a>シナリオ 1: 単純な BizTalk メッセージの追跡データベースのサイズ変更
次の図は、BizTalk Server が、メッセージを一切変換せずに単純に送受信するようすを示したものです。  
  
 ![単純な BizTalk Server メッセージ &#45;変換なし](../core/media/simple-bts-message.gif "Simple_BTS_Message")  
  
 **単純な BizTalk Server メッセージ - 変換なし**  
  
 このシナリオについて前セクションの式を適用する前に、いくつかのファクトを収集しておく必要があります。 この例では、次のファクトを使用します。  
  
-   メッセージのサイズは、5 K です。  
  
-   プロパティの昇格は行われません。  
  
-   1 年に受け取るメッセージ数は、350 万件です。  
  
-   追跡は、すべてのイベントに対して有効になっています。 このシナリオには、次の 4 つのイベントがあります。 イベントは次のとおりです。  
  
    -   メッセージ M0 の受信  
  
    -   受信ポートからのメッセージ M1 の出力  
  
    -   送信パイプラインによるメッセージ M1 の受信  
  
    -   送信パイプラインからのメッセージ M2 の出力  
  
-   このシナリオでは、2 つの追加メッセージが作成されます。 メッセージ M0 は受信メッセージであり、BizTalk Server によって作成されるものではありません。 M1 は受信ポートからの出力メッセージです。M2 は送信ポートからの出力メッセージです。 M1 と M2 は BizTalk Server によって作成されます。  
  
 この情報を式に適用すると、結果は次のようになります。  
  
```  
[(5*252 bytes) + (10*182 bytes) + (0*5(40 bytes + 0) * 3,500,000]/1024/1024  
[(1620 + 1820 + 0) * 3,500,000]/1024/1024 = 10280.61 MB ~ 10.04 GB per year  
```  
  
## <a name="messages-with-a-single-promoted-property"></a>メッセージのプロパティを 1 つ昇格させた場合  
 この例のシナリオに、もう 1 つファクトを追加してみることにします。 元のメッセージのフィールド (サイズは約 10 バイト) を 1 つ昇格させます。 昇格後のフィールドの最大サイズは 256 文字、つまり約 256 バイトです (Unicode 文字の場合は 512 バイト)。  
  
 このファクトを追加した場合、式は次のようになります。  
  
```  
[(2*150 bytes) + (4*230 bytes) + (1*2(52 bytes + 10 bytes)) * 3,500,000]/1024/1024  
[(300 + 920 + 124) * 3,500,000]/1024/1024 = 4486 MB ~ 4.38 GB per year  
```  
  
 サイズが 10 バイトのフィールドをさらにもう 1 つ昇格させた場合、式は次のようになります。  
  
```  
[(2*150 bytes) + (4*230 bytes) + ((1*2*(52 bytes + 10 bytes) + (1*2*(52 bytes + 10 bytes)) * 3,500,000]/1024/1024  
[(300 + 920 + 248) * 3,500,000]/1024/1024 = 4899 MB ~ 4.78 GB per year  
```  
  
 この結果から、このシナリオでは、単一の 10 バイト プロパティを昇格させた場合、BizTalk 追跡データベースのサイズに加え、1 年あたり 333.79 MB (約 0.33 GB) が追加で必要になることがわかります。  
  
 同様に、10 バイトのプロパティを 2 つ昇格させた場合は、BizTalk 追跡データベースのサイズに加え、1 年あたり 667.58 MB (約 0.65 GB) の容量が追加で必要になります。  
  
## <a name="messages-with-message-body-tracking-activated"></a>メッセージ本文の追跡を有効にした場合  
 この例で、さらに、メッセージ本文の追跡を有効にした場合を想定してみましょう。 メッセージ追跡用に、前のセクションで取り上げたもう 1 つの式を追加する必要があります。 この場合は、次のような式になります。  
  
```  
[3,500,000 * 4 * 5KB]/1024 = 68359.375 MB ~ 66.75 GB per year  
  
```  
  
 2 つの式の結果を加算することにより、BizTalk 追跡データベースのサイズは、年間で約 54.48 GB ～ 54.88 GB 増加すると見積もることができます。  
  
## <a name="see-also"></a>参照  
 [追跡データベースのサイズをメッセージ変数を使用](../core/using-message-variables-to-size-the-tracking-database.md)   
 [メッセージ本文を追跡する追跡データベースのサイズ変更](../core/sizing-the-tracking-database-to-track-message-bodies.md)   
 [シナリオ 2: オーケストレーションでメッセージの追跡データベースのサイズ変更](../core/scenario-2-sizing-the-tracking-database-for-messages-in-orchestrations.md)   
 [シナリオ 4: すべてのメッセージの追跡データベースのサイズ変更](../core/scenario-4-sizing-the-tracking-database-for-all-messages.md)   
 [シナリオ 3: 同報リストに送信されるメッセージの追跡データベースのサイズ変更](../core/scenario-3-size-the-tracking-database-for-messages-sent-to-distribution-lists.md)