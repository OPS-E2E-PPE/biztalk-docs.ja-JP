---
title: シナリオ 1:単純な BizTalk メッセージの追跡データベースのサイズ調整 |Microsoft Docs
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
ms.openlocfilehash: e559869bfb62439bb5f83a97b528ecf6960e123f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65308620"
---
# <a name="scenario-1-sizing-the-tracking-database--for-simple-biztalk-messages"></a>シナリオ 1:単純な BizTalk メッセージの追跡データベースのサイズ調整
次の図に、単純な BizTalk Server メッセージは BizTalk Server との間メッセージのすべての変換を実行せずに渡します。  
  
 ![単純な BizTalk Server メッセージ&#45;変換なし](../core/media/simple-bts-message.gif "Simple_BTS_Message")  
  
 **単純な BizTalk Server メッセージ - 変換なし**  
  
 前のセクションで、数式を適用する前に、このシナリオの詳細については、いくつかファクトを収集する必要があります。 この例で、次使用します。  
  
- メッセージ サイズは、5 K です。  
  
- プロパティは昇格なし。  
  
- 1 年間に受信したメッセージの数は、350万です。  
  
- すべてのイベントの追跡がオンになっているとします。 このシナリオには、4 つのイベントがあります。 イベントは次のとおりです。  
  
  -   メッセージ M0 の受信  
  
  -   受信ポートからメッセージ M1 の出力  
  
  -   送信パイプラインによるメッセージ M1 の受信  
  
  -   送信パイプラインによるメッセージ M2 の出力  
  
- このシナリオでは、2 つの追加メッセージが作成されます。 メッセージ M0 は受信メッセージを BizTalk Server によって作成されませんが。 メッセージ M1 は受信ポートから出力メッセージと M2 は送信ポートから出力します。 M1 と M2 は、BizTalk Server によって作成されます。  
  
  式にこの情報を適用することで、次は。  
  
```  
[(5*252 bytes) + (10*182 bytes) + (0*5(40 bytes + 0) * 3,500,000]/1024/1024  
[(1620 + 1820 + 0) * 3,500,000]/1024/1024 = 10280.61 MB ~ 10.04 GB per year  
```  
  
## <a name="messages-with-a-single-promoted-property"></a>1 つの昇格させたプロパティを持つメッセージ  
 この例で、シナリオに 1 つのファクトを追加してみましょう。 元のメッセージのサイズが約 10 バイト、1 つのフィールドを昇格するには。 昇格させたフィールドの最大サイズは 256 文字、つまり約 256 バイト (512 バイト Unicode 文字の場合) です。  
  
 この追加のファクトをこれで、式は次のようです。  
  
```  
[(2*150 bytes) + (4*230 bytes) + (1*2(52 bytes + 10 bytes)) * 3,500,000]/1024/1024  
[(300 + 920 + 124) * 3,500,000]/1024/1024 = 4486 MB ~ 4.38 GB per year  
```  
  
 サイズが 10 バイトである追加のフィールドを昇格する場合、式は次のようになります。  
  
```  
[(2*150 bytes) + (4*230 bytes) + ((1*2*(52 bytes + 10 bytes) + (1*2*(52 bytes + 10 bytes)) * 3,500,000]/1024/1024  
[(300 + 920 + 248) * 3,500,000]/1024/1024 = 4899 MB ~ 4.78 GB per year  
```  
  
 ご覧のとおり、このシナリオでは、1 つの 10 バイト プロパティを昇格する場合、追加の 333.79 MB が追加されます ~ BizTalk 追跡データベースのサイズを 1 年あたり 0.33 GB。  
  
 10 バイトの 2 つのプロパティの昇格は追加 667.58 MB の追加約 0.65 GB、BizTalk 追跡データベースのサイズを 1 年あたり追加の空き領域。  
  
## <a name="messages-with-message-body-tracking-activated"></a>メッセージがメッセージ本文の追跡をアクティブ化  
 この例でも仮定メッセージ本文の追跡をアクティブ化する予定です。 前のセクションに示すように、メッセージ追跡用に 2 番目の式を追加する必要があります。 式は、この例では、次のようになります。  
  
```  
[3,500,000 * 4 * 5KB]/1024 = 68359.375 MB ~ 66.75 GB per year  
  
```  
  
 2 つの式の結果を追加すると、BizTalk 追跡データベースが、1 年あたり約 54.48 GB をことに拡張されますを推定できます。  
  
## <a name="see-also"></a>参照  
 [追跡データベースのサイズにメッセージ変数を使用します。](../core/using-message-variables-to-size-the-tracking-database.md)   
 [メッセージ本文を追跡する追跡データベースのサイズ調整](../core/sizing-the-tracking-database-to-track-message-bodies.md)   
 [シナリオ 2: オーケストレーション内のメッセージの追跡データベースのサイズ調整](../core/scenario-2-sizing-the-tracking-database-for-messages-in-orchestrations.md)   
 [シナリオ 4:すべてのメッセージの追跡データベースのサイズ調整](../core/scenario-4-sizing-the-tracking-database-for-all-messages.md)   
 [シナリオ 3:配布リストに送信されるメッセージの追跡データベースのサイズ調整](../core/scenario-3-size-the-tracking-database-for-messages-sent-to-distribution-lists.md)