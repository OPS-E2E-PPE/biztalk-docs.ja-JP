---
title: アダプターの受信要求-応答の同期用のインターフェイス |Microsoft ドキュメント
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
ms.openlocfilehash: 9abd84bab5da623c2dff61c6e07a5898110588af
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257810"
---
# <a name="interfaces-for-a-synchronous-request-response-receive-adapter"></a>要求 - 応答の同期受信アダプター用のインターフェイス
すべての受信アダプターが要求 - 応答モードで動作するには、アダプターに次のインターフェイスを実装する必要があります。  
  
-   **IBTTransport**  
  
-   **IBTTransportControl** (標準アダプターのみ)  
  
-   **IBTTransportConfig**  
  
-   **IBaseComponent**  
  
-   **IPersistPropertyBag**  
  
-   **IBTBatchCallBack**  
  
-   **IBTTransmitter**  
  
 要求 - 応答プロトコルをサポートする受信アダプター (HTTP 受信アダプターなど) は、要求メッセージの送信時に、次の処理を実行します。  
  
1.  受信アダプターが、受信要求メッセージを受信します。 呼び出して、トランスポート プロキシからバッチを取得、 **GetBatch**のメソッド、 **IBTTransportProxy**インターフェイスです。 この呼び出しで、アダプターはでコールバック ポインターに渡すの実装、 **IBTBatchCallBack.BatchComplete**メソッドです。  
  
2.  呼び出して、アダプターがバッチに要求メッセージを追加、 **SubmitRequestMessage**のメソッド、 **IBTTransportBatch**要求メッセージごとに 1 回のインターフェイスです。  
  
3.  アダプターが呼び出すすべてのメッセージが追加されると、**完了**のメソッド、 **IBTTransportBatch**インターフェイスで、トランスポート プロキシを経由してメッセージング エンジンにバッチを送信します。  
  
4.  メッセージング エンジンがアダプターを呼び出すバッチが処理された後**IBTBatchCallBack.BatchComplete**コールバック メソッドは、トランスポート プロキシを使用します。 送信の状態が、バッチの各メッセージに対応する HRESULT 値の配列として、アダプターに渡されます。 パイプラインまたはオーケストレーションでバッチが失敗すると、SOAP エラー メッセージが応答としてアダプターに返されます。  
  
5.  受信要求メッセージには、オーケストレーションのサブスクライバーが含まれる場合があります。 呼び出して、アダプターに、メッセージング エンジンがアダプターにトランスポート プロキシを経由応答メッセージを送信、オーケストレーションが完了するし、要求メッセージが処理されて、 **TransmitMessage** からメソッド**IBTTransmitter**インターフェイスです。  
  
6.  アダプターは応答メッセージを送信し、元のメッセージをメッセージ ボックス データベースから削除します。  
  
 要求 - 応答の同期受信アダプターを作成するときの、オブジェクト間の対話処理を次に示します。  
  
 ![](../core/media/ebiz-sdk-devadapter3.gif "ebiz_sdk_devadapter3")  
同期メッセージを送信する受信アダプターのワークフロー  
  
## <a name="see-also"></a>参照  
 [アダプタの変数](../core/adapter-variables.md)   
 [開発、受信アダプター](../core/developing-a-receive-adapter.md)   
 [インスタンス化と初期化、アダプターの受信](../core/instantiating-and-initializing-a-receive-adapter.md)   
 [受信アダプターをインプロセスで用のインターフェイス](../core/interfaces-for-an-in-process-receive-adapter.md)   
 [受信アダプターの分離用のインターフェイス](../core/interfaces-for-an-isolated-receive-adapter.md)   
 [受信アダプターのバッチ サポート用のインターフェイス](../core/interfaces-for-a-batch-supported-receive-adapter.md)   
 [受信アダプターのバッチでサポートされているトランザクション パブリケーション用のインターフェイス](../core/interfaces-for-a-transactional-batch-supported-receive-adapter.md)