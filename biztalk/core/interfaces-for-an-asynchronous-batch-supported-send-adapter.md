---
title: 送信アダプターのバッチ処理に対応する非同期のインターフェイス |Microsoft Docs
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
ms.openlocfilehash: 07890cb81bb76a665f98d7f489b4775c01f436b3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65381798"
---
# <a name="interfaces-for-an-asynchronous-batch-supported-send-adapter"></a>バッチ処理に対応の非同期送信アダプター用のインターフェイス
バッチ対応アダプターでは、同期または非同期にメッセージを送信し、トランザクション送信を実行することがあります。 メッセージのバッチを送信するには、送信アダプターは、次のインターフェイスを実装する必要があります。  
  
- **IBTTransport**  
  
- **IBaseComponent**  
  
- **IBTTransportControl**  
  
- **IPersistPropertyBag**  
  
- **IBTBatchTransmitter**  
  
- **IBTTransmitterBatch**  
  
  非同期バッチ送信では、メッセージング エンジンがアダプターからバッチを取得し、そのバッチに送信するメッセージを追加します。 メッセージング エンジンを呼び出すと、メッセージの送信、**完了**batch でのメソッド。 アダプターは返します`False`非同期的に送信するメッセージごとにします。 アダプターは、アダプターのプロキシからバッチを取得し、正常に送信されたメッセージを削除します。  
  
  次の図は、送信アダプターのバッチでサポートされている非同期作成に関連するオブジェクトの相互作用を示しています。  
  
  ![](../core/media/ebiz-sdk-devadapter7.gif "ebiz_sdk_devadapter7")  
  非同期的にメッセージを送信するためのワークフロー  
  
## <a name="see-also"></a>参照  
 [アダプター変数](../core/adapter-variables.md)   
 [送信アダプターの開発](../core/developing-a-send-adapter.md)   
 [インスタンス化し、送信アダプターの初期化](../core/instantiating-and-initializing-a-send-adapter.md)   
 [送信アダプターの同期用のインターフェイス](../core/interfaces-for-a-synchronous-send-adapter.md)   
 [送信アダプターの非同期インターフェイス](../core/interfaces-for-an-asynchronous-send-adapter.md)   
 [同期のバッチでサポートされている送信アダプター用のインターフェイス](../core/interfaces-for-a-synchronous-batch-supported-send-adapter.md)   
 [Batch でサポートされているトランザクションの非同期送信アダプター用のインターフェイス](../core/interfaces-for-a-transactional-asynchronous-batch-supported-send-adapter.md)   
 [送信請求 - 応答送信アダプター用のインターフェイス](../core/interfaces-for-a-solicit-response-send-adapter.md)