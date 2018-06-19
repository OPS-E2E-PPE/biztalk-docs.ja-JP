---
title: 送信アダプターのバッチでサポートされている同期用のインターフェイス |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2b191c41-ca4f-4d2b-bd15-a93ad87a743d
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3ab61fd6624468e0464cfe0c648fcc868bd20005
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257674"
---
# <a name="interfaces-for-a-synchronous-batch-supported-send-adapter"></a>バッチ処理に対応した同期送信アダプター用のインターフェイス
バッチ対応アダプターでは、同期的または非同期的にメッセージを送信し、トランザクション送信操作を実行できます。 メッセージのバッチを送信するには、送信アダプターに次のインターフェイスを実装する必要があります。  
  
-   **IBTTransport**  
  
-   **IBaseComponent**  
  
-   **IBTTransportControl**  
  
-   **IPersistPropertyBag**  
  
-   **IBTBatchTransmitter**  
  
-   **IBTTransmitterBatch**  
  
 バッチの同期送信では、メッセージング エンジンがアダプターからバッチを取得し、そのバッチに送信するメッセージを追加します。 メッセージング エンジンは、各メッセージのバッチを追加しを呼び出すときにのみ、メッセージを送信、**完了**バッチのメソッドです。 アダプターを返します`True`の**bDeleteMessage**同期的に送信する各メッセージにします。 アダプターは、メッセージ ポインターではなく、メッセージ データに保存してその**TransmitMessage**実装します。 この理由は、`True` が返されるとメッセージ ポインターは無効になり、使用できなくなるか、後で使用するためにキャッシュできなくなるためです。  
  
 バッチ処理に対応した同期送信アダプターを作成するときの、オブジェクト間の対話処理を次に示します。  
  
 ![](../core/media/ebiz-sdk-devadapter6.gif "ebiz_sdk_devadapter6")  
メッセージの同期送信のワークフロー  
  
## <a name="see-also"></a>参照  
 [アダプタの変数](../core/adapter-variables.md)   
 [送信アダプターの開発](../core/developing-a-send-adapter.md)   
 [インスタンス化して、送信アダプターの初期化](../core/instantiating-and-initializing-a-send-adapter.md)   
 [送信アダプターの同期用のインターフェイス](../core/interfaces-for-a-synchronous-send-adapter.md)   
 [送信アダプターの非同期インターフェイス](../core/interfaces-for-an-asynchronous-send-adapter.md)   
 [サポートされるバッチの非同期送信アダプター用のインターフェイス](../core/interfaces-for-an-asynchronous-batch-supported-send-adapter.md)   
 [バッチでサポートされているトランザクションの非同期送信アダプター用のインターフェイス](../core/interfaces-for-a-transactional-asynchronous-batch-supported-send-adapter.md)   
 [送信アダプターの送信請求-応答のインターフェイス](../core/interfaces-for-a-solicit-response-send-adapter.md)