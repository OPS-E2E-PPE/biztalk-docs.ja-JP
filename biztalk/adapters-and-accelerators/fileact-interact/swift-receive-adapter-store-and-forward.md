---
title: SWIFT 受信アダプターのストア アンド フォワード |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 11eeb335-366b-4b29-9078-de9396b258ca
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1744f86cc10bfe37b1a4c7814c31e6e2e8812507
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65364381"
---
# <a name="swift-receive-adapter-store-and-forward"></a>SWIFT 受信アダプターのストア アンド フォワード
受信アダプターは、SWIFT ストア アンド フォワード (SnF) キューからメッセージを受信します。 キューからメッセージを受信するには、アダプターは SnF キューでセッションを開く必要があります。 キューを開くには、キューとのセッションを確立する専用のクライアント プロセスが必要です。 設計では、このプロセスは、COM + のアウト プロセス コンポーネントとして実装されます。  
  
## <a name="push-session-store-and-forward-sequence"></a>セッション ストア アンド フォワードのシーケンスをプッシュします。  
 次の一覧には、ストア アンド フォワードのシーケンスがについて説明します。  
  
1.  メッセージを処理するサーバー アプリケーションを起動します。  
  
2.  サーバー プロセスは、入力プリミティブとして、Sw:HandleInitRequest で最初の SwCallback 中に必要なセキュリティ コンテキストを開きます。  
  
3.  サーバーは、Sw:CryptoMode と Sw:FACryptoMode 高度な設定のいずれかまたは両方 Sw:HandleInitRequest に応答します。  
  
     サーバーは、受信要求の処理を開始する準備ができました。  
  
4.  キューからメッセージの配信を開始するには、クライアント プロセスは、プッシュ セッションを開始します。 アダプターの構成 (プッシュ モード) に基づいて、受信アダプターは、プッシュ モードでキューを取得する SnFQueueManager.exe と呼ばれるクライアント プロセスを生成します。  
  
5.  (内 Sw:ExchangeSnFRequest) Sw:AcquireSnFRequest 入力プリミティブとして、SwCall() が実行されます。 この要求が示されるキューと、セッションを開始 (かどうか、SwSec:AuthorisationContext が必要な RBAC ロール)。  
  
6.  "Accepted"で、Sw:AcquireStatus で応答した直後に SWIFTNet SnF は、取得で指定されているサーバーにメッセージを送信を開始します。 受信アダプターがまだ開始されていない場合、メッセージは、例外を取得します。 (いるため、受信アダプターが既に開始することが重要) です。  
  
7.  SWIFTNet SnF (最大ウィンドウ サイズ) のメッセージ数のプッシュを開始します。  
  
8.  すべてのメッセージが受信確認 (ある場合)、新しいメッセージがプッシュされます。  
  
9. クライアント プロセス (SnFQueueManager.exe) は、そのジョブで実行され、終了するようになりました。 プロセスは、オープンなセキュリティ コンテキストをクリーンアップする SwSec:DestroyContextRequest を発行します。 Sw:TermRequest 後、プロセスを終了します。  
  
### <a name="message-correlation"></a>メッセージの関連付け  
 RequestRef フィールドは保持され、応答メッセージに戻り、受信アダプターによって代わりに使用します。 これにより、受信メッセージと応答メッセージの間のエンド ツー エンドの相関関係  
  
### <a name="duplicate-processing"></a>重複した処理  
 FileAct 要求、およびアダプターのインスタンスを受信している場合は、参照先の転送が正常に完了既にか、または失敗したかを確認して適切なアクションを実行する必要がありますを可能な複製のインジケーターのノードでは、メッセージを受け取ります。 ファイル転送が既にが発生した場合、アダプターは、"Duplicate"として転送状態を更新し、それ以外の場合、更新し、「受理します」  
  
### <a name="acknowledgments"></a>受信確認  
 FileAct 要求の受信確認を送信者に要求している場合、アダプターはファイル転送の完了イベントをチェックし、ファイルのダイジェスト値を確認した後、受信確認を生成します。 アダプターは、BizTalk を取得し、送信者に送信する送信アダプターに受信確認メッセージを送信します。  
  
## <a name="see-also"></a>参照  
 [SWIFT 受信アダプターのアーキテクチャ](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-architecture.md)   
 [SWIFT 受信アダプターの URI](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-uri.md)   
 [SWIFT 受信アダプターの初期化](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-initialization.md)   
 [SWIFT 受信アダプター セキュリティ コンテキスト](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-security-context.md)   
 [SWIFT 受信アダプターの同期および遅延モード](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-synchronous-and-deferred-modes.md)