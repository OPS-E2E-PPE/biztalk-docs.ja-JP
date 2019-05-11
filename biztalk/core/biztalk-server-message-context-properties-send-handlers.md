---
title: BizTalk Server メッセージ コンテキスト プロパティ (送信ハンドラー) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a065ba89-9fdb-47dc-9021-fb95cf347cdc
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4396f3404b885d4b2069eae2b6e9be882401e664
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358145"
---
# <a name="biztalk-server-message-context-properties-send-handlers"></a>BizTalk Server メッセージ コンテキスト プロパティ (送信ハンドラー)
BizTalk Server オーケストレーションの実行時には、メッセージ ペイロードに加えて、メッセージに含まれる補足情報にもアクセスできる必要があります。  
  
## <a name="tibco-rv-message-information-promoted-as-message-context-properties"></a>メッセージ コンテキストのプロパティとして昇格される TIBCO RV メッセージ情報  
  
|データ ID|型|ルーティング可能|送信場所|  
|-------------------------|----------|--------------|-------------------|  
|送信サブジェクト|string|はい|オーケストレーションにより TIBCO Rendezvous 送信サブジェクトが指定されます。 既定値は Null です。 既定のサブジェクトがポート構成で指定されていない場合は必須です。|  
|返信サブジェクト|string|はい|必要に応じて、オーケストレーションにより返信メッセージのサブジェクトが指定されます。 既定値は Null です。|  
  
## <a name="getting-a-tibco-reply"></a>TIBCO の返信の取得  
 **質問:** 方法は BizTalk Adapter for TIBCO Rendezvous を読み取り操作して、オーケストレーション内で返信サブジェクト応答の送信サブジェクトとして使用できるようにしますか。 BizTalk Adapter for TIBCO Rendezvous では Rendezvous からの受信メッセージのメッセージ コンテキストにどのようにアクセスしますか。  
  
 **回答:** 返信サブジェクトは、着信メッセージのコンテキストで設定され、オーケストレーションで読み取ることができます。 最終的にオーケストレーションで返信を作成する場合は、その値を使用して返信メッセージの送信サブジェクトを設定できます。  
  
1. BizTalk Server プロジェクトで、<install_directory>\TibcoRV\bin\Microsoft.BizTalk.Adapters.TibRV.Properties.dll への参照を追加します。  
  
2. オーケストレーション (受信 Rendezvous メッセージを渡す受信図形と、返信を送信する送信図形の間の場所) 内で、作成した返信に次の例のような処理を実行するメッセージの構築/割り当て図形 (または式図形) を追加します。  
  
   ```  
   OutgoingMsg(Rendezvous.SendSubject) = IncomingMsg  
   (Rendezvous.ReplySubject);  
   ```  
   ## <a name="management-assembly"></a>アセンブリの管理
   TIBCO Rendezvous はメタデータ リポジトリを備えておらず、Microsoft BizTalk Adapter for TIBCO Rendezvous 管理アセンブリは参照機能またはスキーマ生成機能を備えていません。 したがって、ユーザーがスキーマを BizTalk Server に提供する必要があります。 詳細については、次を参照してください。[インストール、スキーマ、および制限事項](../core/installing-biztalk-adapter-for-tibco-rendezvous.md)します。
  
   BizTalk Adapter for TIBCO Rendezvous には定義済みの型のスキーマが含まれます。 アダプターは、一部の特定のデータ型 (配列) のメッセージを生成するときに、これらの型を使用します。

  
## <a name="see-also"></a>参照  
 [TIBCO Rendezvous での送信ハンドラーのデータ型マッピング](../core/data-type-mapping-for-send-handlers-in-tibco-rendezvous.md)   
 [TIBCO Rendezvous 送信ハンドラーの作成](../core/creating-tibco-rendezvous-send-handlers.md)