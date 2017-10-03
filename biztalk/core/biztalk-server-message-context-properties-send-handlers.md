---
title: "BizTalk Server のメッセージ コンテキスト プロパティ (送信ハンドラー) |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- message context properties, BizTalk Server
- reply subjects
- send handlers, BizTalk Server message context properties
- replies
ms.assetid: a065ba89-9fdb-47dc-9021-fb95cf347cdc
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9c8e5ddb1feb02a015fdebd62d183d1b8442fe5e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="biztalk-server-message-context-properties-send-handlers"></a>BizTalk Server のメッセージ コンテキスト プロパティ (送信ハンドラー)
BizTalk Server オーケストレーションの実行時には、メッセージ ペイロードに加えて、メッセージに含まれる補足情報にもアクセスできる必要があります。  
  
## <a name="tibco-rv-message-information-promoted-as-message-context-properties"></a>メッセージ コンテキストのプロパティとして昇格される TIBCO RV メッセージ情報  
  
|データ ID|型|ルーティング可能|送信場所|  
|-------------------------|----------|--------------|-------------------|  
|送信サブジェクト|string|はい|オーケストレーションにより TIBCO Rendezvous 送信サブジェクトが指定されます。 既定値は Null です。 既定のサブジェクトがポート構成で指定されていない場合は必須です。|  
|返信サブジェクト|string|はい|必要に応じて、オーケストレーションにより返信メッセージのサブジェクトが指定されます。 既定値は Null です。|  
  
## <a name="getting-a-tibco-reply"></a>TIBCO の返信の取得  
 **質問:** TIBCO Rendezvous の読み取りおよび応答の送信サブジェクトとして使用できるように、オーケストレーション内の返信サブジェクトを操作については、BizTalk アダプターにはどのしますか? BizTalk Adapter for TIBCO Rendezvous では Rendezvous からの受信メッセージのメッセージ コンテキストにどのようにアクセスしますか。  
  
 **回答:**返信サブジェクトが、受信メッセージのコンテキストで値が入力され、オーケストレーションで読み取ることができます。 最終的にオーケストレーションで返信を作成する場合は、その値を使用して返信メッセージの送信サブジェクトを設定できます。  
  
1.  BizTalk Server プロジェクトで、<install_directory>\TibcoRV\bin\Microsoft.BizTalk.Adapters.TibRV.Properties.dll への参照を追加します。  
  
2.  オーケストレーション (受信 Rendezvous メッセージを渡す受信図形と、返信を送信する送信図形の間の場所) 内で、作成した返信に次の例のような処理を実行するメッセージの構築/割り当て図形 (または式図形) を追加します。  
  
    ```  
    OutgoingMsg(Rendezvous.SendSubject) = IncomingMsg  
    (Rendezvous.ReplySubject);  
    ```  
  
## <a name="see-also"></a>参照  
 [TIBCO Rendezvous での送信ハンドラーのデータ型マッピング](../core/data-type-mapping-for-send-handlers-in-tibco-rendezvous.md)   
 [TIBCO Rendezvous 送信ハンドラーを作成します。](../core/creating-tibco-rendezvous-send-handlers.md)