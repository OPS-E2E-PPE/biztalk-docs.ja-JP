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
ms.openlocfilehash: dc579995821a97dc588b2221f8a7dd2e9cd1e136
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36993019"
---
# <a name="interfaces-for-an-asynchronous-batch-supported-send-adapter"></a>バッチ処理に対応した非同期送信アダプター用のインターフェイス
バッチ対応アダプターでは、同期的または非同期的にメッセージを送信し、トランザクション送信を実行できます。 メッセージのバッチを送信するには、送信アダプターに次のインターフェイスを実装する必要があります。  
  
- **IBTTransport**  
  
- **IBaseComponent**  
  
- **IBTTransportControl**  
  
- **IPersistPropertyBag**  
  
- **IBTBatchTransmitter**  
  
- **IBTTransmitterBatch**  
  
  バッチの非同期送信では、メッセージング エンジンがアダプターからバッチを取得し、そのバッチに送信するメッセージを追加します。 メッセージング エンジンを呼び出すと、メッセージの送信、**完了**batch でのメソッド。 アダプターは、非同期送信する各メッセージに対して `False` を返します。 アダプターはアダプターのプロキシからバッチを取得し、正常に送信されたメッセージを削除します。  
  
  バッチ処理に対応した非同期送信アダプターを作成するときの、オブジェクト間の対話処理を次に示します。  
  
  ![](../core/media/ebiz-sdk-devadapter7.gif "ebiz_sdk_devadapter7")  
  メッセージの非同期送信のワークフロー  
  
## <a name="see-also"></a>参照  
 [アダプター変数](../core/adapter-variables.md)   
 [送信アダプターの開発](../core/developing-a-send-adapter.md)   
 [インスタンス化し、送信アダプターの初期化](../core/instantiating-and-initializing-a-send-adapter.md)   
 [送信アダプターの同期用のインターフェイス](../core/interfaces-for-a-synchronous-send-adapter.md)   
 [送信アダプターの非同期インターフェイス](../core/interfaces-for-an-asynchronous-send-adapter.md)   
 [同期のバッチでサポートされている送信アダプター用のインターフェイス](../core/interfaces-for-a-synchronous-batch-supported-send-adapter.md)   
 [Batch でサポートされているトランザクションの非同期送信アダプター用のインターフェイス](../core/interfaces-for-a-transactional-asynchronous-batch-supported-send-adapter.md)   
 [送信請求 - 応答送信アダプター用のインターフェイス](../core/interfaces-for-a-solicit-response-send-adapter.md)