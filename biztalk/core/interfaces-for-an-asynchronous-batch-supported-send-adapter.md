---
title: 送信アダプターのバッチでサポートされている非同期用のインターフェイス |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d38b8b87-508a-499b-86b2-846938050b44
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4af0a5c116c19c4cb1fa728cc016144594f42f13
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257330"
---
# <a name="interfaces-for-an-asynchronous-batch-supported-send-adapter"></a>バッチ処理に対応した非同期送信アダプター用のインターフェイス
バッチ対応アダプターでは、同期的または非同期的にメッセージを送信し、トランザクション送信を実行できます。 メッセージのバッチを送信するには、送信アダプターに次のインターフェイスを実装する必要があります。  
  
-   **IBTTransport**  
  
-   **IBaseComponent**  
  
-   **IBTTransportControl**  
  
-   **IPersistPropertyBag**  
  
-   **IBTBatchTransmitter**  
  
-   **IBTTransmitterBatch**  
  
 バッチの非同期送信では、メッセージング エンジンがアダプターからバッチを取得し、そのバッチに送信するメッセージを追加します。 メッセージング エンジンを呼び出すと、メッセージの送信、**実行**バッチのメソッドです。 アダプターは、非同期送信する各メッセージに対して `False` を返します。 アダプターはアダプターのプロキシからバッチを取得し、正常に送信されたメッセージを削除します。  
  
 バッチ処理に対応した非同期送信アダプターを作成するときの、オブジェクト間の対話処理を次に示します。  
  
 ![](../core/media/ebiz-sdk-devadapter7.gif "ebiz_sdk_devadapter7")  
メッセージの非同期送信のワークフロー  
  
## <a name="see-also"></a>参照  
 [アダプタの変数](../core/adapter-variables.md)   
 [送信アダプターの開発](../core/developing-a-send-adapter.md)   
 [インスタンス化して、送信アダプターの初期化](../core/instantiating-and-initializing-a-send-adapter.md)   
 [送信アダプターの同期用のインターフェイス](../core/interfaces-for-a-synchronous-send-adapter.md)   
 [送信アダプターの非同期インターフェイス](../core/interfaces-for-an-asynchronous-send-adapter.md)   
 [同期のバッチでサポートされている送信アダプター用のインターフェイス](../core/interfaces-for-a-synchronous-batch-supported-send-adapter.md)   
 [バッチでサポートされているトランザクションの非同期送信アダプター用のインターフェイス](../core/interfaces-for-a-transactional-asynchronous-batch-supported-send-adapter.md)   
 [送信アダプターの送信請求-応答のインターフェイス](../core/interfaces-for-a-solicit-response-send-adapter.md)