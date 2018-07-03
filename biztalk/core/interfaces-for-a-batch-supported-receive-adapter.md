---
title: 受信アダプターのバッチ サポート用のインターフェイス |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fa6ee780-189c-41e3-9ab0-6b869e791c0a
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9b009a3ff5b7ac8aa8f449c7b2c58ad95ededec8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973187"
---
# <a name="interfaces-for-a-batch-supported-receive-adapter"></a>バッチ処理に対応した受信アダプター用のインターフェイス
受信アダプターでは、常にメッセージがバッチ単位で送信されます。 バッチとは、送信以外のアクションに使用できるデータベース操作の集まりです。 たとえば受信アダプターでは、同じバッチ内で 1 つのメッセージ セットを送信し、別のメッセージ セットを中断し、さらに別のメッセージ セットを削除するという操作を実行できます。 このようにさまざまな操作を 1 つのバッチにまとめ、必要なデータベースのラウンド トリップ回数を最小限に抑えることで、パフォーマンスを最適化できます。バッチの使用を強くお勧めします。  
  
 インプロセス受信アダプターと分離受信アダプターでサーバーにメッセージのバッチを送信するには、アダプターに次のインターフェイスを実装する必要があります。  
  
- **IBTTransport**  
  
- **IBTTransportControl** (インプロセス アダプターのみ)  
  
- **IBTTransportConfig**  
  
- **IBaseComponent**  
  
- **IPersistPropertyBag**  
  
- **IBTBatchCallBack**  
  
  受信アダプターは、メッセージをサーバーに送信するとき、次の順序でアクションを実行します。  
  
1. 受信アダプターを呼び出すことによって、トランスポート プロキシからバッチを取得します、 **GetBatch**のメソッド、 **IBTTransportProxy**インターフェイス。 呼び出しで**GetBatch**へのポインターを渡しますその**IBTBatchCallback**インターフェイスの実装。  
  
2. アダプターを追加しますメッセージを 1 つずつバッチに呼び出すことによって、 **SubmitMessage**のメソッド、 **IBTTransportBatch**インターフェイス。 これは、送信請求-応答のメッセージなどの双方向の操作の場合、 **SubmitResponseMessage**応答メッセージを送信するこの同じインターフェイスのメソッドが呼び出されます。  
  
3. アダプターが呼び出すすべてのメッセージがバッチに追加されていますが、ときに、**完了**のメソッド、 **IBTTransportBatch**インターフェイスをトランスポート プロキシにバッチを送信します。 ため、受信アダプターは本質的に非同期で、アダプターがすぐに新しいバッチを取得し、呼び出した後、他のメッセージを送信を開始**完了**します。  
  
4. メッセージング エンジンがアダプターを呼び出すバッチが処理された後**BatchComplete**トランスポート プロキシを使用して、実際の呼び出しにコールバック メソッド。 配列の**BTBatchOperationStatus**アダプターに渡される送信の状態を格納しているオブジェクトします。 各オブジェクトは操作の種類を表し、操作の全体的な状態と、操作の対象メッセージごとの状態を格納しています。 アダプターは、バッチ処理の状態を分析するため、次の順序でアクションを実行する必要があります。  
  
   1.  バッチの全体的な状態 HRESULT 値がパラメーターとして渡されるチェック、 **BatchComplete**メソッド。 値が失敗となっている場合は、バッチの中の少なくとも 1 つの操作が正常に実行されていないことを示します。 したがって、バッチ全体の送信が 1 つのエンティティの失敗として扱われます。 この場合アダプターは、問題のあるメッセージを特定し、それ以外の問題のないメッセージをバッチとして再送信する必要があります。  
  
        バッチの全体的な状態が成功となっている場合は、トランスポート プロキシに送信されたすべてのメッセージがディスクに保存されたことを示します。 ただしこれは、パイプラインですべてのメッセージが正常に処理されたことを示すものではなく、 パイプラインでエラーとなったメッセージが中断されている可能性もあります。 パイプラインでエラーとなったメッセージがあっても、データはディスクに書き込まれているので、バッチの全体的な状態は成功となります。  
  
   2.  `operationStatus` パラメーターで、操作の種類ごとに状態を確認します。 状態の場合**S_OK**、この操作の送信が成功したおよびさらに、状態を確認する必要はありません。 状態が 設定されている場合**BTS_S_EPM_MESSAGE_SUSPENDED**中断されたメッセージの一部です。 **BTS_S_EPM_SECURITY_CHECK_FAILED**いくつかのメッセージで認証が失敗したことを示す受信ポートの認証-必須します。 場合**E_FAIL**が返されます、または HRESULT の値は、この操作に失敗しましたのメッセージ送信を 0 未満です。  
  
   3.  それぞれの操作の種類の中で、メッセージごとに状態を確認します。 送信操作の種類の各メッセージの状態に設定**S_OK**送信が成功した場合。 **BTS_S_EPM_MESSAGE_SUSPENDED**メッセージが中断されたかどうかに返されます。 **BTS_S_EPM_SECURITY_CHECK_FAILED**メッセージが認証を必要とする受信ポートでの認証に失敗したかどうかに返されます。 **E_BTS_NO_SUBSCRIPTION**場合は、パブリッシュされたメッセージに対するサブスクライバーがないです。 場合**E_FAIL**が返されます、または HRESULT の値は、失敗、メッセージの送信を 0 未満です。  
  
   4.  返すメッセージを保留する可能性があります、アダプターによって**E_FAIL**または HRESULT が失敗しています。  
  
5. **BatchComplete**メソッドは、いずれかを返す必要があります**S_OK**または**E_FAIL**実行の結果を示します。 場合、 **BatchComplete**メソッドを返します。 **E_FAIL**または任意の負の値の HRESULT トランスポート プロキシは、エラーを記録します。  
  
   バッチ処理に対応した受信アダプターを作成するときの、オブジェクト間の対話処理を次に示します。  
  
   ![](../core/media/ebiz-sdk-devadapter1.gif "ebiz_sdk_devadapter1")  
   メッセージのバッチを送信する受信アダプターのワークフロー  
  
## <a name="see-also"></a>参照  
 [アダプター変数](../core/adapter-variables.md)   
 [開発、受信アダプター](../core/developing-a-receive-adapter.md)   
 [インスタンス化と初期化、アダプターの受信](../core/instantiating-and-initializing-a-receive-adapter.md)   
 [受信アダプターをインプロセスで用のインターフェイス](../core/interfaces-for-an-in-process-receive-adapter.md)   
 [インターフェイスの分離受信アダプター](../core/interfaces-for-an-isolated-receive-adapter.md)   
 [受信アダプターのバッチでサポートされているトランザクション パブリケーション用のインターフェイス](../core/interfaces-for-a-transactional-batch-supported-receive-adapter.md)   
 [要求 - 応答の同期受信アダプター用のインターフェイス](../core/interfaces-for-a-synchronous-request-response-receive-adapter.md)