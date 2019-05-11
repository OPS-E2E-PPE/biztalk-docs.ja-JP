---
title: 受信アダプターの要求-応答の同期用のインターフェイス |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d0c60832-52b5-4d2c-81ec-94c46c375b15
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1dcf63c64298c40152f0b7f01c764f514fde6f37
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65382001"
---
# <a name="interfaces-for-a-synchronous-request-response-receive-adapter"></a>要求 - 応答の同期受信アダプター用のインターフェイス
すべての受信要求-応答モードで動作する次のインターフェイスを実装するためにアダプターが必要。  
  
- **IBTTransport**  
  
- **IBTTransportControl** (標準アダプターのみ)  
  
- **IBTTransportConfig**  
  
- **IBaseComponent**  
  
- **IPersistPropertyBag**  
  
- **IBTBatchCallBack**  
  
- **IBTTransmitter**  
  
  要求-応答プロトコルをサポートする受信アダプター (たとえば、HTTP 受信アダプター) の要求メッセージを送信するときに、次の操作を実行します。  
  
1. 受信アダプターでは、着信要求メッセージを受信します。 呼び出すことによって、トランスポート プロキシからバッチを取得、 **GetBatch**のメソッド、 **IBTTransportProxy**インターフェイス。 この呼び出しで渡しますコールバック ポインターの実装に、 **IBTBatchCallBack.BatchComplete**メソッド。  
  
2. アダプターがバッチに呼び出すことで要求メッセージを追加、 **SubmitRequestMessage**のメソッド、 **IBTTransportBatch**各要求メッセージに対して 1 回のインターフェイス。  
  
3. アダプターが呼び出すすべてのメッセージが追加されたときに、**完了**のメソッド、 **IBTTransportBatch**インターフェイスで、トランスポート プロキシを経由してメッセージング エンジンにバッチが送信されます。  
  
4. メッセージング エンジンがアダプターを呼び出すバッチが処理された後**IBTBatchCallBack.BatchComplete**トランスポート プロキシを使用してコールバック メソッド。 送信の状態は、バッチ内の各メッセージに対応する HRESULT 値の配列としてアダプターに渡されます。 パイプラインまたはオーケストレーションでバッチが失敗した場合は、応答としてアダプターに SOAP エラー メッセージが返されます。  
  
5. 受信要求メッセージには、オーケストレーションのサブスクライバーがあります。 呼び出して、アダプターに、メッセージング エンジンがアダプターにトランスポート プロキシを経由の応答メッセージを送信、オーケストレーションが完了するし、要求メッセージが処理された、 **TransmitMessage** からメソッド**IBTTransmitter**インターフェイス。  
  
6. アダプターは、応答メッセージを送信し、元のメッセージをメッセージ ボックス データベースから削除します。  
  
   次の図は、受信アダプターの同期要求-応答の作成に関連するオブジェクトの相互作用を示しています。  
  
   ![](../core/media/ebiz-sdk-devadapter3.gif "ebiz_sdk_devadapter3")  
   同期メッセージを送信する受信アダプターのワークフロー  
  
## <a name="see-also"></a>参照  
 [アダプター変数](../core/adapter-variables.md)   
 [開発、受信アダプター](../core/developing-a-receive-adapter.md)   
 [インスタンス化と初期化、アダプターの受信](../core/instantiating-and-initializing-a-receive-adapter.md)   
 [受信アダプターをインプロセスで用のインターフェイス](../core/interfaces-for-an-in-process-receive-adapter.md)   
 [インターフェイスの分離受信アダプター](../core/interfaces-for-an-isolated-receive-adapter.md)   
 [受信アダプターのバッチ サポート用のインターフェイス](../core/interfaces-for-a-batch-supported-receive-adapter.md)   
 [バッチ処理に対応したトランザクション受信アダプター用のインターフェイス](../core/interfaces-for-a-transactional-batch-supported-receive-adapter.md)