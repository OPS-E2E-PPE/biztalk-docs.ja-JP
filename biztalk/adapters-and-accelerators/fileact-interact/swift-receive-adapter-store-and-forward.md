---
title: "SWIFT 受信アダプター ストア アンド フォワード |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 11eeb335-366b-4b29-9078-de9396b258ca
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 315b9bbe6985bbce5ccb44d8d4846b18730f292b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="swift-receive-adapter-store-and-forward"></a>SWIFT 受信アダプター ストア アンド フォワード
受信アダプターは、迅速なストア アンド フォワード (SnF) キューからメッセージを受信します。 キューからメッセージを受信するには、アダプターは SnF キューでセッションを開く必要があります。 キューを開く、キューとのセッションを確立するための専用クライアント処理が必要です。 デザインでは、このプロセスは、COM とアウト プロセス コンポーネントとして実装されます。  
  
## <a name="push-session-store-and-forward-sequence"></a>プッシュ セッション ストアと転送シーケンス  
 次の一覧は、ストア アンド フォワードのシーケンスについて説明します。  
  
1.  メッセージを処理するサーバー アプリケーションを起動します。  
  
2.  サーバー プロセスは、入力プリミティブとして、Sw:HandleInitRequest で最初の SwCallback 中に必要なセキュリティ コンテキストを開きます。  
  
3.  サーバーの応答 Sw:HandleInitRequest Sw:CryptoMode と Sw:FACryptoMode 高度な設定のいずれかまたは両方を使用します。  
  
     サーバーは、受信要求の処理を開始する準備ができました。  
  
4.  キューからメッセージの配信を開始するには、クライアント プロセスは、プッシュ セッションを開始します。 アダプターの構成 (プッシュ モード) に基づいて、受信アダプターは、プッシュ モードでキューを取得する SnFQueueManager.exe を呼び出すクライアント プロセスを生成します。  
  
5.  SwCall() は、入力プリミティブとして Sw:AcquireSnFRequest (Sw:ExchangeSnFRequest) 内で実行されます。 この要求が示されている、キューにセッションを開始 (かどうか、SwSec:AuthorisationContext が必要なの RBAC ロール) です。  
  
6.  「受理」で、Sw:AcquireStatus で応答すること、直後には、SWIFTNet SnF は、取得で指定されているサーバーにメッセージを送信するを起動します。 受信アダプターがまだ開始されていない場合、メッセージは、例外を取得します。 (つまりは受信アダプターが既に開始されている必要が理由) です。  
  
7.  SWIFTNet SnF では、(ウィンドウのサイズ) の最大メッセージ数のプッシュを開始します。  
  
8.  受信確認のメッセージはすべて、新しいメッセージ (存在する場合) がプッシュされます。  
  
9. クライアント プロセス (SnFQueueManager.exe) は、そのジョブが実行し、今すぐ終了できます。 プロセスでは、オープンなセキュリティ コンテキストをクリーンアップする SwSec:DestroyContextRequest を発行します。 Sw:TermRequest 後、プロセスを終了します。  
  
### <a name="message-correlation"></a>メッセージの関連付け  
 RequestRef フィールドは保持され、応答メッセージに戻り、受信アダプターによって代わりに使用します。 これにより、受信メッセージと応答メッセージのエンド ツー エンドの相関関係  
  
### <a name="duplicate-processing"></a>重複した処理  
 FileAct 要求、およびアダプター インスタンスでは、受信する場合は、参照先の転送が既に正常完了したか失敗した場合を確認し、適切な操作にする必要がありますし、可能な複製のインジケーターのノードでは、メッセージを受け取ります。 ファイル転送が既に行われて場合、アダプターは、"Duplicate"として転送状態を更新し、それ以外の場合、更新「受理」として  
  
### <a name="acknowledgments"></a>受信確認  
 送信者は、FileAct 要求の受信確認を要求している場合、アダプターは、ファイル転送の完了イベントを確認し、ファイルのダイジェスト値を確認した後、受信確認を生成します。 アダプターは、受信確認メッセージを送信アダプター選択し、送信者に送信するための BizTalk に送信します。  
  
## <a name="see-also"></a>参照  
 [SWIFT 受信アダプターのアーキテクチャ](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-architecture.md)   
 [SWIFT 受信アダプター URI](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-uri.md)   
 [SWIFT 受信アダプターの初期化](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-initialization.md)   
 [SWIFT 受信アダプター セキュリティ コンテキスト](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-security-context.md)   
 [SWIFT 受信アダプターの同期および遅延モード](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-synchronous-and-deferred-modes.md)