---
title: "BizTalk Server のメッセージ コンテキスト プロパティが (受信ハンドラー) |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- message context properties
- receive handlers, message context properties
ms.assetid: 7f47e2a0-6ac8-404a-bc0a-c7739911af74
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8a60896a8e1cace909a160c1dc942e63e9258d85
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="biztalk-server-message-context-properties-receive-handlers"></a>BizTalk Server のメッセージ コンテキスト プロパティが (受信ハンドラー)
メッセージ ペイロードに加えて、メッセージを構成する補足情報に BizTalk Server オーケストレーションから実行時にアクセスできる必要があります。  
  
## <a name="tibco-rv-message-information-promoted-as-message-context-properties"></a>メッセージ コンテキストのプロパティとして昇格される TIBCO RV メッセージ情報  
 次の表に、この補足情報を示します。  
  
|データ ID|型|ルーティング可能|受信場所|  
|-------------------------|----------|--------------|----------------------|  
|送信サブジェクト [null]|string|はい|このメッセージの送信先サブジェクトをオーケストレーションに伝えます。|  
|応答サブジェクト [null]|string|はい|送信者が応答の送信先として期待する場所 (そのような場所が期待される場合) をオーケストレーションに伝えます。|  
|フィールド数 [読み取り専用]|unsigned int|不可|上位レベル メッセージ内のフィールドの数。 TIBCO RV によって指定されるプロパティです。|  
|CM 送信者名 [読み取り専用]|string|はい|送信者の CM 通信者名。|  
|CM シーケンス番号 [読み取り専用]|long|不可|送信元の TIBCO トランスポート オブジェクトによって割り当てられたシーケンス番号。|  
|CM タイム リミット [読み取り専用]|double|不可|送信元プログラムがその CM トランスポートによるメッセージ配信の認証を期待しなくなるまでのタイム リミット。|  
  
## <a name="see-also"></a>参照  
 [TIBCO Rendezvous のメッセージ マッピング](../core/message-mapping-in-tibco-rendezvous.md)   
 [作成元の TIBCO Rendezvous 受信ハンドラー](../core/creating-tibco-rendezvous-receive-handlers.md)