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
ms.openlocfilehash: f5056092886ad9d73d3db3dcc910038bc7dcd6e4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37024136"
---
# <a name="interfaces-for-a-solicit-response-send-adapter"></a>送信請求 - 応答送信アダプター用のインターフェイス
送信アダプターが受信サーバーに応答メッセージを送信するアダプターと同じバッチ メカニズムを使用します。  
  
> [!NOTE]
>  送信請求 - 応答アダプターではメッセージを非同期で処理することをお勧めします。 同期的に処理した場合、メッセージが重複する危険性があります。  
  
 送信アダプターが送信請求 - 応答モードで動作するには、アダプターに次のインターフェイスを実装する必要があります。  
  
- **IBTTransport**  
  
- **IBaseComponent**  
  
- **IBTTransportControl**  
  
- **IPersistPropertyBag**  
  
- **IBTTransmitter**  
  
- **IBTTransmitterBatch**と**IBTBatchTransmitter** (送信バッチ処理が必要な場合)  
  
- **IBTBatchCallBack**  
  
  オブジェクト間では次の対話処理が行われます。  
  
1. 送信アダプターは、送信請求メッセージを送信した後、送信先のサーバーから応答メッセージを受け取ります。 その後、トランスポート プロキシからバッチを取得します。  
  
2. アダプターのバッチに呼び出すことによって、応答メッセージを追加する**ibttransportproxy::submitresponsemessage**します。  
  
3. アダプターが呼び出すことによって、バッチを送信する**ibttransportproxy::done**へのポインターを渡してその**IBTBatchComplete**メッセージング エンジンからコールバック インターフェイス。  
  
4. メッセージング エンジンがアダプターの**ibtbatchcallback::batchcomplete**送信操作の結果を通知するトランスポート プロキシを使用してコールバック メソッド。  
  
   送信請求 - 応答送信アダプターを作成するときの、オブジェクト間の対話処理を次に示します。  
  
   ![](../core/media/ebiz-sdk-devadapter13.gif "ebiz_sdk_devadapter13")  
   送信請求 - 応答送信アダプターにおける対話処理  
  
## <a name="see-also"></a>参照  
 [アダプター変数](../core/adapter-variables.md)   
 [送信アダプターの開発](../core/developing-a-send-adapter.md)   
 [インスタンス化し、送信アダプターの初期化](../core/instantiating-and-initializing-a-send-adapter.md)   
 [送信アダプターの同期用のインターフェイス](../core/interfaces-for-a-synchronous-send-adapter.md)   
 [送信アダプターの非同期インターフェイス](../core/interfaces-for-an-asynchronous-send-adapter.md)   
 [同期のバッチでサポートされている送信アダプター用のインターフェイス](../core/interfaces-for-a-synchronous-batch-supported-send-adapter.md)   
 [バッチ処理に対応の非同期送信アダプター用のインターフェイス](../core/interfaces-for-an-asynchronous-batch-supported-send-adapter.md)   
 [バッチ処理に対応したトランザクションとしての非同期送信アダプター用のインターフェイス](../core/interfaces-for-a-transactional-asynchronous-batch-supported-send-adapter.md)