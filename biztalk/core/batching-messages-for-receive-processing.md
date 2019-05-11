---
title: 受信処理用メッセージをバッチ処理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 32bf0b70-e9d1-4fab-9c74-160e51390700
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e60bab7b9f6d41268bd60be0b1f37daf07019af1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358290"
---
# <a name="batching-messages-for-receive-processing"></a>受信処理用メッセージのバッチ処理
## <a name="batch-callbacks"></a>バッチ コールバック  
 によって送信されたバッチの受信アダプターがメッセージング エンジンに非同期的に処理されます。 そのため、アダプターでは、成功または失敗の通知を受け取ることができ、必要なクリーンアップ操作を実行するために、アダプターのいくつかの状態にコールバックを関連付けるメカニズムが必要です。 アダプターが 1 つまたは 3 つのアプローチの組み合わせを使用できるように、コールバックのセマンティクスは柔軟です。 これらの数値は、次のとおりです。  
  
- すべてのコールバックが実装する同じオブジェクト インスタンスで行われた**IBTBatchCallBack**します。  
  
- Cookie は、新しいバッチの要求をアダプターの状態にコールバックを関連付けるために使用する場合に、エンジンに渡されます。  
  
- 実装する各バッチの異なるコールバック オブジェクトがある**IBTBatchCallBack**します。 ここで各オブジェクトは、独自のプライベート状態を保持します。  
  
  実装でアダプターがコールバックに機能して、バッチが処理されると、 **IBTBatchCallBack.BatchComplete**します。 バッチの全体的な状態は、最初のパラメーターでは、HRESULT の状態が表示されます。 この値が 0 以上の場合は、バッチは、エンジンがデータの所有権をアダプターは、ネットワークからそのデータを削除する無料の意味では成功します。 負の状態は、バッチが失敗したことを示します。成功しなかったバッチ内の操作のいずれもと、アダプターは、エラーを処理します。  
  
  バッチが失敗した場合は、アダプターを操作が失敗しました、どの項目を把握する必要があります。 たとえば、アダプターがディスクに送信すると 20 個のファイルを読み取りが[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]1 つのバッチを使用します。 10 番目のファイルが破損している場合、アダプターはその 1 つのファイルを中断し、残りの 19 を再送信する必要があります。 この情報は、2 番目と 3 番目のパラメーターでアダプターに使用可能な —`opCount` (操作数) short 型のおよび`operationStatus`btbatchoperationstatus[] 型のです。  
  
> [!NOTE]
>  1 つのバッチ オブジェクトでする必要がありますしないメッセージを送信した 2 回以上。 同じバッチで複数回、同じメッセージ オブジェクトを送信すると、エンジンのエラーが発生します。  
  
 操作数は、操作の種類の数がバッチにあったことを示します (のサイズ、 **BTBatchOperationStatus**配列)。 操作の状態配列内の各要素は、特定の操作の種類に対応します。 使用して、 **BTBatchOperationStatus**配列、アダプターは、調べることで失敗しました操作内の項目を特定できます、 **BTBatchOperationStatus.MessageStatus**負の値の HRESULT の配列。エラーを示す値。 上記のシナリオでは、アダプターが 19 を含む新しいバッチを作成します。 メッセージを送信し、1 つのメッセージを中断します。  
  
 次のコード フラグメントは、アダプターのトランスポート プロキシを経由して、エンジンから新しいバッチを要求し、クッキーのアプローチを使用してエンジンに 1 つのメッセージを送信、を示します。 メッセージング エンジンの呼び出し、 **BatchComplete**メソッドのバッチ全体の処理が完了すると、バッチ コールバックとしては、メッセージを送信します。  
  
```  
using Microsoft.BizTalk.TransportProxy.Interop;  
using Microsoft.BizTalk.Message.Interop;  
  
public class MyAdapter :   
                  IBTTransport,   
                  IBTTransportConfig,   
                  IBTTransportControl,  
                  IPersistPropertyBag,   
                  IBaseComponent,  
                  IBTBatchCallBack  
{  
      private IBTTransportProxy _tp;  
  
      public void BatchComplete(      
            Int32                         status,   
            Int16                         opCount,   
            BTBatchOperationStatus[]      operationStatus,   
            System.Object                 callbackCookie)  
      {  
            // Use cookie to correlate callback with work done,  
            // in this example the batch is to submit a single  
            // file the name of which will be in the  
            // callbackCookie  
            string fileName = (string)callbackCookie;  
            if ( status >= 0 )  
                  // DeleteFile from disc  
                  File.Delete(fileName);          
            else  
                  // Rename file to fileName.bad  
                  File.Move(fileName, fileName + ".bad");  
      }  
  
      private void SubmitMessage(  
            IBaseMessage                  msg,   
            string                        fileName)  
      {  
            // Note: Pass in the filename as the cookie  
            IBTTransportBatch batch =   
                  _tp.GetBatch(this, (object)fileName);  
  
            // Add msg to batch for submitting   
            batch.SubmitMessage(msg);   
  
            // Process this batch  
            batch.Done(null);  
      }  
}  
```  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] SDK には、次のアダプターのサンプルが含まれています。ファイル、HTTP、MSMQ、およびトランザクション アダプター。 すべてのこれらのアダプターは、BaseAdapter と呼ばれる共通のビルド ブロックの上に構築されます。 バージョン 1.0.1 の BaseAdapter では、すべての操作の状態を解析し、送信する新しいバッチを再構築に関連するコードが含まれます。  
  
## <a name="race-condition"></a>競合状態  
 エラーを解決して、送信されたバッチの最終結果を決定するは、2 つのタスクが、単純に見えますが、異なるスレッドからの情報に依存している実際。  
  
- アダプターによって渡された情報に基づいてエラーを処理する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アダプターの**BatchComplete**コールバック メソッド。 このコールバックはアダプターのスレッドで実行します。  
  
- **DTCCommitConfirm**に、メソッドが、 **IBTDTCCommitConfirm**オブジェクト。 インスタンス、 **IBTDTCCommitConfirm**オブジェクトは、batch によって返される**ibttransportbatch::done**呼び出します。 このインスタンスが同じスレッドでは、 **ibttransportbatch::done**呼び出すには、これは、アダプターのコールバック スレッドと異なる。  
  
  アダプターがすべての呼び出しに対して**ibttransportbatch::done**メッセージング エンジンはコールバック メソッドに対応する呼び出し**BatchComplete**の結果を報告する別のスレッドで、バッチ送信します。 **BatchComplete**アダプターのニーズをコミットまたはロールバック トランザクションかどうかに基づいて、バッチが成功または失敗します。 どちらの場合、アダプターは呼び出す必要がありますし、 **DTCCommitConfirm**トランザクションの状態を報告します。  
  
  競合状態が存在するためのアダプターの実装**BatchComplete**を想定できます、 **IBTDTCCommitConfirm**によって返されるオブジェクト**ibttransportbatch::done**は常に利用可能な場合に**BatchComplete**を実行します。 ただし、 **BatchComplete**前であってもに、、別のメッセージング エンジン スレッドで呼び出すこと**ibttransportbatch::done**を返します。 できるアダプターがアクセスしようとしたときに、 **IBTDTCCommitConfirm**オブジェクトの一部として、 **BatchComplete**の実装を呼び出すスレッドを不要になったため、アクセス違反があります。存在します。 この状況を回避するために、次のソリューションを使用します。  
  
  次の例では、イベントを使用して、問題を解決します。 ここでインターフェイス ポインターは、イベントを使用するプロパティを通じてアクセスされます。 Get では、続行する前に完了するセットが常に待機します。  
  
```  
protected IBTDTCCommitConfirm CommitConfirm  
{  
      set  
      {  
            this.commitConfirm = value;  
            this.commitConfirmEvent.Set();  
      }  
      get  
      {  
            this.commitConfirmEvent.WaitOne();  
            return this.commitConfirm;  
      }  
}  
protected IBTDTCCommitConfirm commitConfirm = null;  
private ManualResetEvent commitConfirmEvent = new ManualResetEvent(false);  
```  
  
## <a name="batch-status-codes"></a>バッチの状態コード  
 バッチの全体的な状態コードでは、バッチの結果を示します。 操作の状態は、個々 のメッセージの送信の状態コードを示します。 バッチは、さまざまな理由で失敗します。 セキュリティ関連のエラーがある可能性があります、メッセージが送信されているエンジンがシャット ダウン時にします。 (通常、エンジンのシャット ダウン時に、新しい作業を受け入れませんが、インプロセスの作業を完了は許可)。次の表では、バッチの状態または操作の状態のいずれかに返される一般的な HRESULT 値を示します。 また、これらは、成功または失敗のコードであるかどうかを示します。 これらのコードの適切な処理はより完全での説明[アダプターの障害を処理する方法](../core/how-to-handle-adapter-failures.md)します。  
  
|コード (BTTransportProxy クラスで定義)|成功/失敗コード|説明|  
|----------------------------------------------------|---------------------------|-----------------|  
|BTS_S_EPM_SECURITY_CHECK_FAILED|成功|セキュリティ チェックを実行し、認証に失敗したメッセージをドロップは、ポートが構成されました。 アダプターは、この状態コードを返すバッチを一時停止する必要があります。|  
|BTS_S_EPM_MESSAGE_SUSPENDED|成功|エンジンがデータの所有権、1 つまたは複数のメッセージが中断されたことを示します。 メッセージング エンジンがメッセージの送信を受け入れたことに成功コードになります。|  
|E_BTS_URL_DISALLOWED|失敗|無効なメッセージが送信された**InboundTransportLocation**します。|  
  
## <a name="batch-operations"></a>バッチ操作  
 次の表は、メンバー メソッドとの操作、 **IBTTransportBatch**特定のバッチに作業を追加するアダプターを使用するオブジェクトします。  
  
|メソッド名|操作の種類|説明|  
|-----------------|--------------------|-----------------|  
|**SubmitMessage**|送信|エンジンにメッセージを送信します。|  
|**SubmitResponseMessage**|送信|応答メッセージをエンジンに送信します。 これは、送信請求-応答の組み合わせで応答メッセージです。|  
|**DeleteMessage**|DELETE|アダプターが非ブロッキング送信を使用してネットワーク経由で正常に送信するメッセージを削除します。 ブロッキング送信を使用するアダプターがメッセージング エンジンが削除されますが、アダプターの代わりに、アダプターが返された場合は、このメソッドを呼び出す必要はありません`true`から**TransmitMesssage**します。|  
|**MoveToSuspendQ**|MoveToSuspendQ|メッセージを保留キューに移動します。|  
|**再送信します。**|再送信します。|要求は後で送信メッセージを再試行する必要があります。 送信の試行が失敗した後、これは通常に呼び出されます。|  
|**MoveToNextTransport**|MoveToNextTransport|要求メッセージをバックアップ トランスポートを使用して送信します。 通常、すべての再試行が終了した後に呼び出されます。 バックアップ トランスポートが存在しない場合、このメソッドは失敗します。|  
|**SubmitRequestMessage**|SubmitRequest|要求メッセージを送信します。 これは、要求-応答の組み合わせで要求メッセージです。|  
|**CancelRequestForResponse**|CancelRequestForResponse|アダプターは、要求-応答の組み合わせで応答メッセージを待機する不要になったことを希望するエンジンに通知します。|  
|**Clear**|NA|バッチのすべての操作をクリアします。|  
|**完成です**|NA|処理エンジンへのメッセージのバッチを送信します。|  
  
## <a name="batch-management"></a>バッチの管理  
 バッチは、メッセージング エンジンでネイティブ コードで実装されます。 そのためマネージ コードで作成されたアダプターはバッチが終了した後、バッチのランタイム呼び出し可能ラッパー (RCW) を解除する必要があります。 これは、マネージ コードの中でを使用して、 **Marshal.ReleaseComObject** API。 しばらくの間でこの API を呼び出す必要がありますに注意してください。 返される参照カウントが 0 になるまでループします。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] バッチ内で同期的にメッセージを処理します。 多数のバッチがアプリケーション ドメイン内のバッチ サイズを調整することによって、アダプターで何らかの最適化の機会を提供することがありますが同時に処理できます。 たとえば、(いくつかの制限に達した) まで、FTP サイト上のすべてのファイルを処理する可能性があります。 SAP の場合、バッチとして送信されるメッセージの数に 1 つのストリームを処理する可能性があります。  
  
 操作を渡すために、アダプターによって使用されるバッチに[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]メッセージの一覧に正確に対応する必要はありませんを[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アダプターを提供します。 つまり、トランザクションの実行が送信する場合、再送信操作を分割する必要があります**MoveToNextTransport**と**MoveToSuspendQ**に別のバッチ。 多くのアダプターは、さらに処理するためのメッセージの個別の一覧に複数のエンドポイントに送信されたメッセージのバッチを並べ替えます。  
  
 ポイントは、(トランザクションに関連付けられているもの) 以外のルールがないことでメッセージのバッチ処理に関連付けられている[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。 単に固有の実装方法の送受信メッセージをチャンクするアダプターのバッチ処理は[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。  
  
 アダプターからのメッセージをバッチできる複数の小さなバッチ[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]が特定のこと、大きなバッチからへの応答[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。 これには、多数の非常に小さいメッセージを処理するトランザクション アダプターで大幅な最適化があります。 「メッセージあたりのトランザクションの合計数」の比率が最小限に抑えます。  
  
 通常[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]5 ~ 10 メッセージの送信側バッチが生成されます。 これらは、非常に小さいメッセージと、アダプターは、最大 100 個のメッセージをバッチ可能性がありますまたは削除のトランザクション バッチを送信する前に詳細にバックアップ[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。 このような最適化は; を実装する簡単ではありません。必ず必要がありますアダプター メモリにメッセージが停止しない取得際限なく待機しているいくつかのしきい値が満たされているのです。  
  
 バッチ処理の重要度のパフォーマンスの数値で確認できます[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]MQSeries などの高スループットのアダプター。 これらのアダプターで少なくとも 2 回、多くの場合、送信されるメッセージが受信されます。 既定では、受信アダプターが 100 件のメッセージのバッチを使用し、送信アダプターは、既定値を使用して[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]バッチが与えられます。  
  
## <a name="transactional-batches"></a>トランザクション バッチ  
 トランザクション オブジェクトを作成しに渡すアダプターを記述するとき[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、実行すると、次のコードの記述を担当することになります。  
  
- バッチ操作の最終結果を決定します。 コミットまたはトランザクションの最後。 他のトランザクション分岐のスコープ内でこの 1 つのトランザクションのない時によって[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]によっては、メッセージ キュー (MSMQ) キューまたはトランザクション データベース操作への書き込みなど。  
  
- 通知[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を呼び出して最終結果の**IBTDTCCommitConfirm.DTCCommitConfirm**メソッド。 返す`true`以外のトランザクションが正常にコミットを意味します。 返す`false`失敗して、トランザクションのロールバックします。  
  
  アダプターに通知する必要があります[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]の内部で維持するために、トランザクションの最終的な結果に関するデータを追跡します。 通知[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]呼び出すことによって、結果の**DTCCommitConfirm**します。 アダプターがこれにもいない場合は大量のメモリ リークが発生して、MSDTC トランザクション タイムアウトし、操作が正常に完了に関係なく失敗します。