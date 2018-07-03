---
title: 送信アダプターのバッチ処理に対応する同期用のインターフェイス |Microsoft Docs
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
ms.openlocfilehash: d14e278869854535695babc9ff8796a833de7217
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968227"
---
# <a name="interfaces-for-a-synchronous-batch-supported-send-adapter"></a>バッチ処理に対応した同期送信アダプター用のインターフェイス
バッチ対応アダプターでは、同期的または非同期的にメッセージを送信し、トランザクション送信操作を実行できます。 メッセージのバッチを送信するには、送信アダプターに次のインターフェイスを実装する必要があります。  
  
- **IBTTransport**  
  
- **IBaseComponent**  
  
- **IBTTransportControl**  
  
- **IPersistPropertyBag**  
  
- **IBTBatchTransmitter**  
  
- **IBTTransmitterBatch**  
  
  バッチの同期送信では、メッセージング エンジンがアダプターからバッチを取得し、そのバッチに送信するメッセージを追加します。 メッセージング エンジンは、各メッセージをバッチに追加およびを呼び出すときにのみ、メッセージを送信します、**完了**batch でのメソッド。 アダプターは返します`True`の**bDeleteMessage**同期的に送信するメッセージごとにします。 アダプターで、メッセージ ポインターではなく、メッセージ データを保存する必要があります、 **TransmitMessage**実装します。 この理由は、`True` が返されるとメッセージ ポインターは無効になり、使用できなくなるか、後で使用するためにキャッシュできなくなるためです。  
  
  バッチ処理に対応した同期送信アダプターを作成するときの、オブジェクト間の対話処理を次に示します。  
  
  ![](../core/media/ebiz-sdk-devadapter6.gif "ebiz_sdk_devadapter6")  
  メッセージの同期送信のワークフロー  
  
## <a name="see-also"></a>参照  
 [アダプター変数](../core/adapter-variables.md)   
 [送信アダプターの開発](../core/developing-a-send-adapter.md)   
 [インスタンス化し、送信アダプターの初期化](../core/instantiating-and-initializing-a-send-adapter.md)   
 [送信アダプターの同期用のインターフェイス](../core/interfaces-for-a-synchronous-send-adapter.md)   
 [送信アダプターの非同期インターフェイス](../core/interfaces-for-an-asynchronous-send-adapter.md)   
 [バッチ処理に対応の非同期送信アダプター用のインターフェイス](../core/interfaces-for-an-asynchronous-batch-supported-send-adapter.md)   
 [Batch でサポートされているトランザクションの非同期送信アダプター用のインターフェイス](../core/interfaces-for-a-transactional-asynchronous-batch-supported-send-adapter.md)   
 [送信請求 - 応答送信アダプター用のインターフェイス](../core/interfaces-for-a-solicit-response-send-adapter.md)