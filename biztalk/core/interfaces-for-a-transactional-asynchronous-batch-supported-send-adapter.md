---
title: Batch でサポートされているトランザクションの非同期送信アダプター用のインターフェイス |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e5b2dbdf-e6ba-4b58-a0a5-fc78feaf5c35
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e911445cd0f92bbe863f10b8335aee0bf64630bd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65381856"
---
# <a name="interfaces-for-a-transactional-asynchronous-batch-supported-send-adapter"></a>Batch でサポートされているトランザクションの非同期送信アダプター用のインターフェイス
送信アダプターは、作成し、メッセージのトランザクション送信が必要な場合は、トランザクションを制御できます。 トランザクション送信をサポートするために、アダプターは、次のインターフェイスを実装する必要があります。  
  
- **IBTTransport**  
  
- **IBaseComponent**  
  
- **IBTTransportControl**  
  
- **IPersistPropertyBag**  
  
- **IBTBatchTransmitter**  
  
- **IBTTransmitterBatch**  
  
- **IBTBatchCallBack**  
  
  アダプターは、MSDTC トランザクションを作成しへの呼び出しでは、そのオブジェクトへのポインターを返します、 **BeginBatch**のメソッド、 **IBTTransmitterBatch**インターフェイス。 メッセージング エンジンは、送信アダプターに送信メッセージのポストバックがバッチを取得するには、このメソッドを呼び出します。 使用して、トランザクションの結果をメッセージング エンジンに通知アダプターが送信操作が完了し、コミットまたはトランザクションをロールバック、ときに、 **DTCCommitConfirm**のメソッド、 **IBTDTCCommitConfirm**インターフェイス。  
  
  トランザクション送信操作を実行するときに、次の図は、トランスポート プロキシと送信アダプター間のやり取りを示します。  
  
  ![](../core/media/ebiz-sdk-devadapter8.gif "ebiz_sdk_devadapter8")  
  トランザクション メッセージを非同期的に送信するためのワークフロー  
  
## <a name="see-also"></a>参照  
 [アダプター変数](../core/adapter-variables.md)   
 [送信アダプターの開発](../core/developing-a-send-adapter.md)   
 [インスタンス化し、送信アダプターの初期化](../core/instantiating-and-initializing-a-send-adapter.md)   
 [送信アダプターの同期用のインターフェイス](../core/interfaces-for-a-synchronous-send-adapter.md)   
 [送信アダプターの非同期インターフェイス](../core/interfaces-for-an-asynchronous-send-adapter.md)   
 [同期のバッチでサポートされている送信アダプター用のインターフェイス](../core/interfaces-for-a-synchronous-batch-supported-send-adapter.md)   
 [バッチ処理に対応の非同期送信アダプター用のインターフェイス](../core/interfaces-for-an-asynchronous-batch-supported-send-adapter.md)   
 [送信請求 - 応答送信アダプター用のインターフェイス](../core/interfaces-for-a-solicit-response-send-adapter.md)