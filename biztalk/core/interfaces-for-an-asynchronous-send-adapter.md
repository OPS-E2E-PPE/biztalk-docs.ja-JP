---
title: "送信アダプターの非同期インターフェイス |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6a214716-8f39-400d-a111-ba1b92a284b4
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: db156f5a95a088ae706bb2b1c801d8dee89cdece
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="interfaces-for-an-asynchronous-send-adapter"></a>非同期送信アダプター用のインターフェイス
一度に 1 つのメッセージを送信するアダプターは、同期的または非同期的にメッセージを送信できます。 アダプターは、送信操作中にトランスポート プロキシ スレッドをブロックせずに、個々のスレッドを使用する場合、メッセージを非同期的に送信します。 メッセージを非同期的に送信できるようにするには、アダプターに次のインターフェイスを実装する必要があります。  
  
-   **IBTTransport**  
  
-   **IBaseComponent**  
  
-   **IBTTransportControl**  
  
-   **IPersistPropertyBag**  
  
-   **IBTTransmitter**  
  
 送信アダプターは、メッセージ エンジンの要求時にメッセージをサーバーから送信するとき、次の順序でアクションを実行します。  
  
1.  メッセージング エンジンは、トランスポート プロキシを使用して呼び出すことによって、送信メッセージを送信アダプターに渡す、 **TransmitMessage**のメソッド、 **IBTTransmitter**インターフェイスです。  
  
2.  アダプターを直ちに返します**TransmitMessage**いくつかの内部のキュー、および返しますに送信されるメッセージを保存した後`False`の**bDeleteMessage**です。 これにより、メッセージが非同期で送信されることがメッセージング エンジンに伝えられます。  
  
3.  アダプターは、その独自のスレッド プールを使用してメッセージを送信します。  
  
4.  送信操作が完了すると、アダプターは元のメッセージをメッセージ ボックス データベースから削除します。 使用して、メッセージング エンジンからバッチを取得、 **IBTTransportBatch.GetBatch**トランスポート プロキシとし、呼び出しメソッド**DeleteMessage**です。  
  
     非同期送信アダプターを作成するときの、オブジェクト間の対話処理を次に示します。  
  
     ![](../core/media/ebiz-sdk-devadapter5.gif "ebiz_sdk_devadapter5")  
メッセージの非同期送信のワークフロー  
  
> [!NOTE]
>  アダプターでは現在処理中のメッセージ数を保持することをお勧めします。 アダプターをブロックする必要があります、 **Terminate**メソッド メッセージの数が 0 に到達するまでです。 送信アダプターの場合は、処理されているメッセージを適切に処理する必要があります。 つまり、非同期で正常に送信されたメッセージは、アダプターのプライベート アプリケーション メッセージ キューから削除して、メッセージが 2 回送信されるのを防ぐ必要があります。 一般的に、 **Terminate**が呼び出された、メッセージング エンジンによって、要求は受け付けられませんアダプターから新しいメッセージを公開します。 送信請求 - 応答の組み合わせに関連する応答メッセージの場合は例外です。  
  
## <a name="see-also"></a>参照  
 [アダプタの変数](../core/adapter-variables.md)   
 [送信アダプターの開発](../core/developing-a-send-adapter.md)   
 [インスタンス化して、送信アダプターの初期化](../core/instantiating-and-initializing-a-send-adapter.md)   
 [送信アダプターの同期用のインターフェイス](../core/interfaces-for-a-synchronous-send-adapter.md)   
 [同期のバッチでサポートされている送信アダプター用のインターフェイス](../core/interfaces-for-a-synchronous-batch-supported-send-adapter.md)   
 [サポートされるバッチの非同期送信アダプター用のインターフェイス](../core/interfaces-for-an-asynchronous-batch-supported-send-adapter.md)   
 [バッチでサポートされているトランザクションの非同期送信アダプター用のインターフェイス](../core/interfaces-for-a-transactional-asynchronous-batch-supported-send-adapter.md)   
 [送信アダプターの送信請求-応答のインターフェイス](../core/interfaces-for-a-solicit-response-send-adapter.md)