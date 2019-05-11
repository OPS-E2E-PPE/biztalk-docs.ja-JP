---
title: TIBCO Rendezvous のメッセージ コンテキスト プロパティが表示される |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7f47e2a0-6ac8-404a-bc0a-c7739911af74
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e330926c6f362ea5a84ad7b4b9291a5f2f310eee
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65528324"
---
# <a name="biztalk-server-message-context-properties-receive-handlers"></a>BizTalk Server メッセージ コンテキストのプロパティ (受信ハンドラー)
メッセージ ペイロードに加えて、メッセージを構成する補足情報には、実行時に BizTalk Server オーケストレーションからアクセスできなければなりません。  
  
## <a name="tibco-rv-message-information-promoted-as-message-context-properties"></a>メッセージ コンテキストのプロパティとして昇格される TIBCO RV メッセージ情報  
 次の表は、この補足情報。  
  
|データ ID|型|ルーティング可能|受信場所|  
|-------------------------|----------|--------------|----------------------|  
|送信サブジェクト [null]|string|はい|オーケストレーションにこのメッセージが送信されて、件名に指示します。|  
|返信サブジェクト [null]|string|はい|求められた場合に、送信者が送信される応答を期待する場所をオーケストレーションに指示します。|  
|[読み取り専用] フィールドの数|unsigned int|いいえ|上位レベル メッセージ内のフィールドの数。 TIBCO rv さん。 によって指定されるプロパティ|  
|CM 送信者名 [読み取り専用]|string|はい|送信者の CM 送信者名です。|  
|CM シーケンス番号 [読み取り専用]|long|いいえ|送信元の TIBCO トランスポート オブジェクトによって割り当てられたシーケンス番号。|  
|CM タイム リミット [読み取り専用]|double|いいえ|送信元のプログラムがメッセージの配信の認定を受けるには、その CM トランスポートを不要になった期待される時間制限。|  
  
## <a name="see-also"></a>参照  
 [TIBCO Rendezvous でのメッセージ マッピング](../core/message-mapping-in-tibco-rendezvous.md)   
 [TIBCO Rendezvous 受信ハンドラーの作成](../core/creating-tibco-rendezvous-receive-handlers.md)