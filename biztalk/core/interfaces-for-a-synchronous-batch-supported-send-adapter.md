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
ms.openlocfilehash: 091b735604a0b38044498f712de63ad9eac1c057
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65331609"
---
# <a name="interfaces-for-a-synchronous-batch-supported-send-adapter"></a>同期のバッチでサポートされている送信アダプター用のインターフェイス
バッチ対応アダプターでは、同期または非同期にメッセージを送信し、トランザクション送信操作を実行することがあります。 メッセージのバッチを送信するには、送信アダプターは、次のインターフェイスを実装する必要があります。  
  
- **IBTTransport**  
  
- **IBaseComponent**  
  
- **IBTTransportControl**  
  
- **IPersistPropertyBag**  
  
- **IBTBatchTransmitter**  
  
- **IBTTransmitterBatch**  
  
  同期バッチの送信では、メッセージング エンジンがアダプターからバッチを取得し、そのバッチに送信するメッセージを追加します。 メッセージング エンジンは、各メッセージをバッチに追加およびを呼び出すときにのみ、メッセージを送信します、**完了**batch でのメソッド。 アダプターは返します`True`の**bDeleteMessage**同期的に送信するメッセージごとにします。 アダプターで、メッセージ ポインターではなく、メッセージ データを保存する必要があります、 **TransmitMessage**実装します。 これは、メッセージ ポインターが後に無効になっているため`True`が返されますとを使用せず、後で使用するためにキャッシュします。  
  
  次の図は、送信アダプターのバッチでサポートされている同期の作成に関連するオブジェクトの相互作用を示しています。  
  
  ![](../core/media/ebiz-sdk-devadapter6.gif "ebiz_sdk_devadapter6")  
  同期的にメッセージを送信するためのワークフロー  
  
## <a name="see-also"></a>参照  
 [アダプター変数](../core/adapter-variables.md)   
 [送信アダプターの開発](../core/developing-a-send-adapter.md)   
 [インスタンス化し、送信アダプターの初期化](../core/instantiating-and-initializing-a-send-adapter.md)   
 [送信アダプターの同期用のインターフェイス](../core/interfaces-for-a-synchronous-send-adapter.md)   
 [送信アダプターの非同期インターフェイス](../core/interfaces-for-an-asynchronous-send-adapter.md)   
 [バッチ処理に対応の非同期送信アダプター用のインターフェイス](../core/interfaces-for-an-asynchronous-batch-supported-send-adapter.md)   
 [Batch でサポートされているトランザクションの非同期送信アダプター用のインターフェイス](../core/interfaces-for-a-transactional-asynchronous-batch-supported-send-adapter.md)   
 [送信請求 - 応答送信アダプター用のインターフェイス](../core/interfaces-for-a-solicit-response-send-adapter.md)