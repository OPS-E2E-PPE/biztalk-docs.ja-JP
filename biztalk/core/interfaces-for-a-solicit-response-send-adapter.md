---
title: 送信アダプターの送信請求応答用のインターフェイス |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c54650e8-dbfb-4c66-843b-0b82c8183dd4
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3958629596a11bbfcb6ae109c36ab0237a780542
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65381869"
---
# <a name="interfaces-for-a-solicit-response-send-adapter"></a>送信アダプターの送信請求応答用のインターフェイス
送信アダプターが受信サーバーに応答メッセージを送信するアダプターと同じバッチ メカニズムを使用します。  
  
> [!NOTE]
>  メッセージの処理を非同期的に送信請求-応答アダプターをお勧めします。 同期的にメッセージの処理、メッセージの重複のリスクがあります。  
  
 送信請求-応答モードで動作する次のインターフェイスを実装するアダプターの必要性を送信するには。  
  
- **IBTTransport**  
  
- **IBaseComponent**  
  
- **IBTTransportControl**  
  
- **IPersistPropertyBag**  
  
- **IBTTransmitter**  
  
- **IBTTransmitterBatch**と**IBTBatchTransmitter** (送信バッチ処理が必要な場合)  
  
- **IBTBatchCallBack**  
  
  オブジェクトの相互作用するための手順は次のとおりです。  
  
1. アダプターは、送信請求メッセージを送信した後に戻す応答メッセージを受信送信先のサーバーから。 トランスポート プロキシからバッチを取得します。  
  
2. アダプターのバッチに呼び出すことによって、応答メッセージを追加する**ibttransportproxy::submitresponsemessage**します。  
  
3. アダプターが呼び出すことによって、バッチを送信する**ibttransportproxy::done**へのポインターを渡してその**IBTBatchComplete**メッセージング エンジンからコールバック インターフェイス。  
  
4. メッセージング エンジンがアダプターの**ibtbatchcallback::batchcomplete**送信操作の結果を通知するトランスポート プロキシを使用してコールバック メソッド。  
  
   次の図は、送信アダプターの送信請求-応答の作成に関連するオブジェクトの相互作用を示しています。  
  
   ![](../core/media/ebiz-sdk-devadapter13.gif "ebiz_sdk_devadapter13")  
   送信請求-応答送信アダプターにおける対話  
  
## <a name="see-also"></a>参照  
 [アダプター変数](../core/adapter-variables.md)   
 [送信アダプターの開発](../core/developing-a-send-adapter.md)   
 [インスタンス化し、送信アダプターの初期化](../core/instantiating-and-initializing-a-send-adapter.md)   
 [送信アダプターの同期用のインターフェイス](../core/interfaces-for-a-synchronous-send-adapter.md)   
 [送信アダプターの非同期インターフェイス](../core/interfaces-for-an-asynchronous-send-adapter.md)   
 [同期のバッチでサポートされている送信アダプター用のインターフェイス](../core/interfaces-for-a-synchronous-batch-supported-send-adapter.md)   
 [バッチ処理に対応の非同期送信アダプター用のインターフェイス](../core/interfaces-for-an-asynchronous-batch-supported-send-adapter.md)   
 [バッチ処理に対応したトランザクションとしての非同期送信アダプター用のインターフェイス](../core/interfaces-for-a-transactional-asynchronous-batch-supported-send-adapter.md)