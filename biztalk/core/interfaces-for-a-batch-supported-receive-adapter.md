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
ms.openlocfilehash: 360a7b4fb3f6842795358ebe40cace7531cd2b6c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65331670"
---
# <a name="interfaces-for-a-batch-supported-receive-adapter"></a>バッチ処理に対応した受信アダプター用のインターフェイス
受信アダプターは、常にバッチ内のメッセージを送信します。 バッチは、送信以外のアクションに使用できるデータベース操作の単位です。 たとえば、受信アダプターことができます 1 つの一連のメッセージを送信、メッセージのさまざまなセットを中断および削除同じバッチ内のメッセージの別のセット。 同じバッチ内でこれらの個別の操作をグループ化の数を最小限に抑えることによってパフォーマンスが最適化データベースのために必要なラウンド トリップと強くお勧めします。  
  
 インプロセスおよび分離には、サーバーにメッセージのバッチを送信する次のインターフェイスを実装するアダプターの必要性が表示されます。  
  
- **IBTTransport**  
  
- **IBTTransportControl** (インプロセス アダプターのみ)  
  
- **IBTTransportConfig**  
  
- **IBaseComponent**  
  
- **IPersistPropertyBag**  
  
- **IBTBatchCallBack**  
  
  次の手順では、一連のサーバーにメッセージを送信する受信アダプターを実行するアクションについて説明します。  
  
1. 受信アダプターを呼び出すことによって、トランスポート プロキシからバッチを取得します、 **GetBatch**のメソッド、 **IBTTransportProxy**インターフェイス。 呼び出しで**GetBatch**へのポインターを渡しますその**IBTBatchCallback**インターフェイスの実装。  
  
2. アダプターを追加しますメッセージを 1 つずつバッチに呼び出すことによって、 **SubmitMessage**のメソッド、 **IBTTransportBatch**インターフェイス。 これは、送信請求-応答のメッセージなどの双方向の操作の場合、 **SubmitResponseMessage**応答メッセージを送信するこの同じインターフェイスのメソッドが呼び出されます。  
  
3. アダプターが呼び出すすべてのメッセージがバッチに追加されていますが、ときに、**完了**のメソッド、 **IBTTransportBatch**インターフェイスをトランスポート プロキシにバッチを送信します。 ため、受信アダプターは本質的に非同期で、アダプターがすぐに新しいバッチを取得し、呼び出した後、他のメッセージを送信を開始**完了**します。  
  
4. メッセージング エンジンがアダプターを呼び出すバッチが処理された後**BatchComplete**トランスポート プロキシを使用して、実際の呼び出しにコールバック メソッド。 配列の**BTBatchOperationStatus**アダプターに渡される送信の状態を格納しているオブジェクトします。 各オブジェクトは、操作の種類に対応し、操作の全体的な状態と操作が実行された各メッセージの状態が含まれています。 次のシーケンスには、アダプターがバッチ処理の状態を分析するために実行する必要がある操作について説明します。  
  
   1.  バッチの全体的な状態 HRESULT 値がパラメーターとして渡されるチェック、 **BatchComplete**メソッド。 エラーがある場合は、少なくとも 1 つのバッチ内の操作が失敗したことを意味します。 そのため 1 つのエンティティとしてバッチ全体の送信に失敗しました。 問題のあるメッセージを検出し、最初にエラーが発生していないもののみをバッチとして再送信アダプターを再試行する必要があります。  
  
        バッチの全体的な状態が成功した場合は意味をトランスポート プロキシに付与されたすべてのメッセージが永続化されたことをディスクにします。 ただし、必ずしも、パイプラインは、すべてのメッセージを正常に処理します。 パイプラインでエラー メッセージが中断された可能性があります。 パイプラインで失敗したメッセージで返されるバッチの全体的な状態が成功した、データが書き込まれたため、ディスクにします。  
  
   2.  各操作の種類の状態を確認、`operationStatus`パラメーター。 状態の場合**S_OK**、この操作の送信が成功したおよびさらに、状態を確認する必要はありません。 状態が 設定されている場合**BTS_S_EPM_MESSAGE_SUSPENDED**中断されたメッセージの一部です。 **BTS_S_EPM_SECURITY_CHECK_FAILED**いくつかのメッセージで認証が失敗したことを示す受信ポートの認証-必須します。 場合**E_FAIL**が返されます、または HRESULT の値は、この操作に失敗しましたのメッセージ送信を 0 未満です。  
  
   3.  操作の種類に対して個別のメッセージの状態を確認します。 送信操作の種類の各メッセージの状態に設定**S_OK**送信が成功した場合。 **BTS_S_EPM_MESSAGE_SUSPENDED**メッセージが中断されたかどうかに返されます。 **BTS_S_EPM_SECURITY_CHECK_FAILED**メッセージが認証を必要とする受信ポートでの認証に失敗したかどうかに返されます。 **E_BTS_NO_SUBSCRIPTION**場合は、パブリッシュされたメッセージに対するサブスクライバーがないです。 場合**E_FAIL**が返されます、または HRESULT の値は、失敗、メッセージの送信を 0 未満です。  
  
   4.  返すメッセージを保留する可能性があります、アダプターによって**E_FAIL**または HRESULT が失敗しています。  
  
5. **BatchComplete**メソッドは、いずれかを返す必要があります**S_OK**または**E_FAIL**実行の結果を示します。 場合、 **BatchComplete**メソッドを返します。 **E_FAIL**または任意の負の値の HRESULT トランスポート プロキシは、エラーを記録します。  
  
   次の図は、受信アダプターのバッチ処理に対応の作成に関連するオブジェクトの相互作用を示しています。  
  
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