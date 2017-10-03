---
title: "バッチでサポートされているトランザクションの非同期送信アダプター用のインターフェイス |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e5b2dbdf-e6ba-4b58-a0a5-fc78feaf5c35
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 948000883c092c8e247b1d4f41fb2bc7e2280e40
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="interfaces-for-a-transactional-asynchronous-batch-supported-send-adapter"></a>バッチ処理に対応したトランザクションとしての非同期送信アダプター用のインターフェイス
メッセージのトランザクション送信が求められた場合、送信アダプターはトランザクションを作成および制御できます。 トランザクション送信をサポートするには、アダプターに次のインターフェイスを実装する必要があります。  
  
-   **IBTTransport**  
  
-   **IBaseComponent**  
  
-   **IBTTransportControl**  
  
-   **IPersistPropertyBag**  
  
-   **IBTBatchTransmitter**  
  
-   **IBTTransmitterBatch**  
  
-   **IBTBatchCallBack**  
  
 アダプターは MSDTC トランザクションを作成し、呼び出しでは、そのオブジェクトへのポインターを返します、 **BeginBatch**のメソッド、 **IBTTransmitterBatch**インターフェイスです。 メッセージング エンジンはこのメソッドを呼び出して、送信メッセージを送信アダプターに送るときに使用するバッチを取得します。 使用して、トランザクションの結果のメッセージング エンジンに通知、アダプターでは、送信操作が完了すると、コミットまたはとトランザクションをロールバック、ときに、 **DTCCommitConfirm**のメソッド、 **IBTDTCCommitConfirm**インターフェイスです。  
  
 トランザクション送信操作を実行した際の、トランスポート プロキシと送信アダプター間の対話処理を次に示します。  
  
 ![](../core/media/ebiz-sdk-devadapter8.gif "ebiz_sdk_devadapter8")  
トランザクション メッセージの非同期送信のワークフロー  
  
## <a name="see-also"></a>参照  
 [アダプタの変数](../core/adapter-variables.md)   
 [送信アダプターの開発](../core/developing-a-send-adapter.md)   
 [インスタンス化して、送信アダプターの初期化](../core/instantiating-and-initializing-a-send-adapter.md)   
 [送信アダプターの同期用のインターフェイス](../core/interfaces-for-a-synchronous-send-adapter.md)   
 [送信アダプターの非同期インターフェイス](../core/interfaces-for-an-asynchronous-send-adapter.md)   
 [同期のバッチでサポートされている送信アダプター用のインターフェイス](../core/interfaces-for-a-synchronous-batch-supported-send-adapter.md)   
 [サポートされるバッチの非同期送信アダプター用のインターフェイス](../core/interfaces-for-an-asynchronous-batch-supported-send-adapter.md)   
 [送信アダプターの送信請求-応答のインターフェイス](../core/interfaces-for-a-solicit-response-send-adapter.md)