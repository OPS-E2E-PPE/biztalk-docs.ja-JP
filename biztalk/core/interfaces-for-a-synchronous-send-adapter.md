---
title: 送信アダプターの同期用のインターフェイス |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0e1b397a-3a35-4447-8522-d8a5f39a42d7
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1012b52bf5c6ab564cc219926b97445e43f60dd1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22256914"
---
# <a name="interfaces-for-a-synchronous-send-adapter"></a>同期送信アダプター用のインターフェイス
アダプターは、受信メッセージング エンジンの呼び出し元スレッドをブロックするときに、送信操作を実行しながらメッセージを同期的に送信します。 メッセージを同期的に送信できるようにするには、アダプターに次のインターフェイスを実装する必要があります。  
  
-   **IBTTransport**  
  
-   **IBaseComponent**  
  
-   **IBTTransportControl**  
  
-   **IPersistPropertyBag**  
  
-   **IBTTransmitter**  
  
 同期送信アダプターがブロックしているときにメッセージを送信**TransmitMessage**、返された転送が成功した後、`True.`  
  
 同期送信アダプターを作成するときの、オブジェクト間の対話処理を次に示します。  
  
 ![](../core/media/ebiz-sdk-devadapter4.gif "ebiz_sdk_devadapter4")  
メッセージを同期的に送信するためのワークフロー  
  
## <a name="see-also"></a>参照  
 [アダプタの変数](../core/adapter-variables.md)   
 [送信アダプターの開発](../core/developing-a-send-adapter.md)   
 [インスタンス化して、送信アダプターの初期化](../core/instantiating-and-initializing-a-send-adapter.md)   
 [送信アダプターの非同期インターフェイス](../core/interfaces-for-an-asynchronous-send-adapter.md)   
 [同期のバッチでサポートされている送信アダプター用のインターフェイス](../core/interfaces-for-a-synchronous-batch-supported-send-adapter.md)   
 [サポートされるバッチの非同期送信アダプター用のインターフェイス](../core/interfaces-for-an-asynchronous-batch-supported-send-adapter.md)   
 [バッチでサポートされているトランザクションの非同期送信アダプター用のインターフェイス](../core/interfaces-for-a-transactional-asynchronous-batch-supported-send-adapter.md)   
 [送信アダプターの送信請求-応答のインターフェイス](../core/interfaces-for-a-solicit-response-send-adapter.md)