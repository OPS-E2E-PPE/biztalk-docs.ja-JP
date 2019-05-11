---
title: 送信アダプターの非同期インターフェイス |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6a214716-8f39-400d-a111-ba1b92a284b4
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9d8f87fe34d75f0e511568fa0e91088a1b7608a7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65331504"
---
# <a name="interfaces-for-an-asynchronous-send-adapter"></a>送信アダプターの非同期インターフェイス
一度に 1 つのメッセージを送信アダプターは、同期的または非同期的にメッセージを送信できます。 アダプターは、トランスポート プロキシ スレッドをブロックしませんが、送信操作を実行中にではなく別のスレッドを使用するとき、メッセージを非同期的に送信します。 メッセージを非同期的に送信できるようにするには、アダプターは、次のインターフェイスを実装する必要があります。  
  
- **IBTTransport**  
  
- **IBaseComponent**  
  
- **IBTTransportControl**  
  
- **IPersistPropertyBag**  
  
- **IBTTransmitter**  
  
  次の手順では、一連のメッセージング エンジンの要求でサーバーからメッセージを送信する送信アダプターを実行するアクションについて説明します。  
  
1.  メッセージング エンジンはトランスポート プロキシを使用して呼び出すことによって、送信アダプター、送信メッセージを渡す、 **TransmitMessage**のメソッド、 **IBTTransmitter**インターフェイス。  
  
2.  アダプターを直ちに返します**TransmitMessage**をいくつかの内部キューを返す送信されるメッセージを格納した後`False`の**bDeleteMessage**します。 これにより、非同期的に、メッセージが送信される、メッセージング エンジン。  
  
3.  アダプターは、独自のスレッド プールを使用してメッセージを送信します。  
  
4.  送信操作の完了後、アダプターはメッセージ ボックス データベースから元のメッセージを削除します。 使用して、メッセージング エンジンからバッチを取得、 **IBTTransportBatch.GetBatch**トランスポート プロキシにし、呼び出しメソッド**DeleteMessage**します。  
  
     次の図では、非同期送信アダプターの作成に関連するオブジェクトの相互作用を示します。  
  
     ![](../core/media/ebiz-sdk-devadapter5.gif "ebiz_sdk_devadapter5")  
非同期的にメッセージを送信するためのワークフロー  
  
> [!NOTE]
>  アダプターが現在処理されているメッセージの数を保持することをお勧めします。 アダプターをブロックする必要があります、 **Terminate**メソッド メッセージの数が 0 に到達するまでです。 送信アダプターの場合は、処理されているメッセージを適切に処理する必要があります。 つまり、正常に非同期的に配信されたメッセージをメッセージが 2 回送信されることを防ぐために、アダプターのプライベート アプリケーション メッセージ キューから削除する必要があります。 一般的に、 **Terminate**と呼ばれますが、アダプターからの新しいメッセージを公開する要求を受け入れません、メッセージング エンジンによって。 この例外は、送信請求-応答の組み合わせに関連する応答メッセージです。  
  
## <a name="see-also"></a>参照  
 [アダプター変数](../core/adapter-variables.md)   
 [送信アダプターの開発](../core/developing-a-send-adapter.md)   
 [インスタンス化し、送信アダプターの初期化](../core/instantiating-and-initializing-a-send-adapter.md)   
 [送信アダプターの同期用のインターフェイス](../core/interfaces-for-a-synchronous-send-adapter.md)   
 [同期のバッチでサポートされている送信アダプター用のインターフェイス](../core/interfaces-for-a-synchronous-batch-supported-send-adapter.md)   
 [バッチ処理に対応の非同期送信アダプター用のインターフェイス](../core/interfaces-for-an-asynchronous-batch-supported-send-adapter.md)   
 [Batch でサポートされているトランザクションの非同期送信アダプター用のインターフェイス](../core/interfaces-for-a-transactional-asynchronous-batch-supported-send-adapter.md)   
 [送信請求 - 応答送信アダプター用のインターフェイス](../core/interfaces-for-a-solicit-response-send-adapter.md)