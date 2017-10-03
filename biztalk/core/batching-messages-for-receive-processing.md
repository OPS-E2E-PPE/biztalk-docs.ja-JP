---
title: "受信処理用メッセージをバッチ処理 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 32bf0b70-e9d1-4fab-9c74-160e51390700
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ef14179c1af460afc516b7fa331ee30a758219c3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="batching-messages-for-receive-processing"></a>受信処理用メッセージのバッチ処理
## <a name="batch-callbacks"></a>バッチ コールバック  
 受信アダプターによってメッセージング エンジンに送信されるバッチは、非同期に処理されます。 したがって、成功または失敗が通知されるように、また、必要なクリーンアップ処理が実行されるように、受信アダプターにはコールバックを受信アダプターの状態に関連付けるメカニズムが必要です。 コールバックのセマンティクスは柔軟なので、アダプターには、3 つの方法のうちの 1 つまたはそれらの方法の組み合わせを使用できます。 これらの設定は、次のとおりです。  
  
-   実装するオブジェクトの同じインスタンスに対してすべてのコールバックが行われます**IBTBatchCallBack**です。  
  
-   新しいバッチの要求時にエンジンに渡される Cookie を使用して、コールバックをアダプターの状態に関連付けます。  
  
-   実装する各バッチに対して異なるコールバック オブジェクトが**IBTBatchCallBack**です。 各オブジェクトが、独自のプライベート状態を保持します。  
  
 バッチが処理されたときに、アダプターがコールバックの実装で**IBTBatchCallBack.BatchComplete**です。 このバッチの全体的な状態は、最初のパラメーターである HRESULT 値によって示されます。 この値がゼロ以上の場合、エンジンにデータの所有権があり、受信アダプターがそのデータを回線から自由に削除できるという意味で、バッチは成功です。 負の状態は、バッチが失敗したことを示します:、バッチ内の操作が成功しなかったし、アダプターは、エラーを処理します。  
  
 バッチが失敗した場合、アダプターはどの操作のどの項目が失敗したのかを認識する必要があります。 たとえば、アダプターが 1 つのバッチを使用してディスクから 20 ファイルを読み取り、それらを [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に送信したとします。 10 番目のファイルが破損している場合、アダプターは、その 1 つのファイルを中断し、残りの 19 を再送信する必要があります。 この情報は、2 番目と 3 番目のパラメーターのアダプターに提供:`opCount` (操作数) short 型のおよび`operationStatus`btbatchoperationstatus[] 型がであります。  
  
> [!NOTE]
>  1 つのバッチ オブジェクトで 1 つのメッセージを複数回送信しないでください。 同じメッセージ オブジェクトを同じバッチで複数回送信すると、エンジンでエラーが発生します。  
  
 操作の種類の数が、バッチ操作数を示します (のサイズ、 **BTBatchOperationStatus**配列)。 操作の状態配列内の各要素は、バッチに含まれている操作の種類に対応しています。 使用して、 **BTBatchOperationStatus**配列、アダプターは項目を特定の操作を確認して失敗を判断できます、 **BTBatchOperationStatus.MessageStatus**負の HRESULT の配列エラーを示す値です。 上記のシナリオのアダプターは、19 メッセージを送信し 1 メッセージを保留する新しいバッチを作成します。  
  
 次のコードでは、アダプターが新しいバッチをトランスポート プロキシを使用してエンジンに要求し、Cookie を利用して 1 つのメッセージをエンジンに送信する方法を示しています。 メッセージング エンジンの呼び出し、 **BatchComplete**メソッドのバッチ全体の処理が完了すると、バッチ コールバックとしては、メッセージを送信します。  
  
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
            Int32                         status,   
            Int16                         opCount,   
            BTBatchOperationStatus[]      operationStatus,   
            System.Object                 callbackCookie)  
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
            IBaseMessage                  msg,   
            string                        fileName)  
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
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] SDK には、ファイル アダプター、HTTP アダプター、MSMQ アダプター、およびトランザクション アダプターのサンプルが用意されています。 これらのアダプターはすべて BaseAdapter と呼ばれる共通のビルド ブロックに基づいて作成されています。 バージョン 1.0.1 の BaseAdapter には、操作の状態を解析し、新しいバッチを再作成して送信するための関連コードがすべて含まれています。  
  
## <a name="race-condition"></a>競合状態  
 エラーを解決するタスクと、送信されたバッチの最終結果を決定するタスクは単純に見えますが、実際には、これらのタスクは次に示す異なるスレッドの情報に基づいています。  
  
-   アダプターによって渡された情報に基づいてエラーを処理する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アダプターの**BatchComplete**コールバック メソッド。 このコールバックはアダプターのスレッドで実行されます。  
  
-   **DTCCommitConfirm**では、メソッド、 **IBTDTCCommitConfirm**オブジェクト。 インスタンス、 **IBTDTCCommitConfirm**バッチによってオブジェクトが返される**ibttransportbatch::done**呼び出します。 このインスタンスと同じスレッドが、 **ibttransportbatch::done**呼び出すには、これは、アダプターのコールバック スレッドと異なる。  
  
 アダプターがすべての呼び出しに対して**ibttransportbatch::done**メッセージング エンジンはコールバック メソッドに対応する呼び出し**BatchComplete**の結果を報告する個別のスレッドで、バッチ送信します。 **BatchComplete**アダプター ニーズをコミットまたはロールバック、トランザクションがかどうかに基づくバッチが成功または失敗します。 どちらの場合、アダプターは呼び出す必要があります、 **DTCCommitConfirm**トランザクションの状態を報告します。  
  
 競合状態が存在するアダプターの実装の**BatchComplete**あると想定できます、 **IBTDTCCommitConfirm**によって返されるオブジェクト**ibttransportbatch::done**は常に利用可能な場合に**BatchComplete**を実行します。 ただし、 **BatchComplete**個別のメッセージング エンジン スレッドで前であってもに、呼び出すことができます**ibttransportbatch::done**を返します。 可能であればをアダプターがアクセスしようとしたときに、 **IBTDTCCommitConfirm**オブジェクトの一部として、 **BatchComplete**実装では、その呼び出し元スレッドを不要になったため、アクセス違反があります。存在しています。 この状態を回避するには、次の解決方法を使用します。  
  
 次の例では、イベントを使用してこの問題を解決します。 この例では、イベントを使用するプロパティを通じてインターフェイス ポインターにアクセスします。 get の処理は、必ず set が完了した後で行われます。  
  
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
 バッチの状態コード全体は、バッチの結果を示します。 操作の状態からは、個々のメッセージ項目の送信の状態コードが得られます。 バッチが失敗するのにはさまざまな理由があります。 セキュリティ関連のエラーがある可能性があります、メッセージが送信されているエンジンがシャット ダウンしているときにします。 (通常、エンジンのシャット ダウン時に、新しい作業を受け入れませんはインプロセスで作業を完了できます。)次の表に、バッチの状態または操作の状態のいずれかで返される共通の HRESULT 値をいくつか示します。 また、それらの値が成功コードなのか失敗コードなのかも示します。 これらのコードの適切な処理に記載されている複数の完全[アダプターの障害を処理する方法](../core/how-to-handle-adapter-failures.md)です。  
  
|コード (BTTransportProxy クラスで定義)|成功コード/失敗コード|Description|  
|----------------------------------------------------|---------------------------|-----------------|  
|BTS_S_EPM_SECURITY_CHECK_FAILED|Success|セキュリティ チェックを行うようにポートが構成されたので、認証に失敗したメッセージは削除されます。 アダプターでは、この状態コードを返すバッチを保留しないようにする必要があります。|  
|BTS_S_EPM_MESSAGE_SUSPENDED|Success|1 つ以上のメッセージが保留され、エンジンにデータの所有権があることを示します。 これは、メッセージ エンジンがメッセージの送信を受け入れたという点で、成功コードです。|  
|E_BTS_URL_DISALLOWED|失敗|無効なメッセージが送信された**InboundTransportLocation**です。|  
  
## <a name="batch-operations"></a>バッチ操作  
 次の表は、メンバー メソッドとの操作、 **IBTTransportBatch**所定のバッチに作業を追加するアダプターを使用するオブジェクトします。  
  
|メソッド名|操作の種類|Description|  
|-----------------|--------------------|-----------------|  
|**SubmitMessage**|送信|メッセージをエンジンに送信します。|  
|**SubmitResponseMessage**|送信|応答メッセージをエンジンに送信します。 これは、送信請求 - 応答の組み合わせの応答メッセージです。|  
|**DeleteMessage**|DELETE|アダプターが非ブロッキング送信を使用して回線上で正常に送信したメッセージを削除します。 ブロッキング送信を使用するアダプターがメッセージング エンジンは削除ため、アダプターの代わりに、アダプターが返された場合、このメソッドを呼び出す必要はありません`true`から**TransmitMesssage**です。|  
|**MoveToSuspendQ**|MoveToSuspendQ|メッセージを保留キューに移動します。|  
|**再実行してください。**|Resubmit|後でメッセージの送信を再試行するように要求します。 一般に、送信の試行が失敗した後にこのメソッドを呼び出します。|  
|**MoveToNextTransport**|MoveToNextTransport|メッセージをバックアップ トランスポートを使用して送信することを要求します。 通常、すべての試行回数が完了した後にこのメソッドを呼び出します。 バックアップ トランスポートが存在しない場合、このメソッドは失敗します。|  
|**SubmitRequestMessage**|SubmitRequest|要求メッセージを送信します。 これは、要求 - 応答の組み合わせの要求メッセージです。|  
|**CancelRequestForResponse**|CancelRequestForResponse|エンジンに、アダプターが要求 - 応答の組み合わせの応答メッセージを待機しなくなったことを通知します。|  
|**Clear**|NA|バッチからすべての作業を削除します。|  
|**完成です**|NA|メッセージのバッチをエンジンに送信して処理します。|  
  
## <a name="batch-management"></a>バッチ管理  
 バッチは、メッセージ エンジンでネイティブ コードで実装されます。 そのため、マネージ コードで記述されたアダプターは、バッチのランタイム呼び出し可能ラッパー (RCW) を、バッチの処理の終了後に解放する必要があります。 これは、マネージ コードの中で使用して、 **Marshal.ReleaseComObject** API です。 While この API を呼び出す必要がありますに注意して返される参照カウントがゼロになるまでループします。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は、バッチ内でメッセージを同期して処理します。 多数のバッチが同時に処理されることがあるので、アプリケーション ドメイン内でバッチ サイズを調整することによって、アダプターで何らかの最適化を行うことになる場合があります。 たとえば、FTP サイトですべてのファイルを処理する場合が考えられます (何らかの制限に該当するまで)。 SAP の場合は、1 つのストリームを多数のメッセージにし、後でそれらを 1 つのバッチとして送信することがあります。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に操作を渡すためにアダプターによって使用されるバッチは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] がアダプターに提供するメッセージの一覧と正確に対応している必要はありません。 つまり、送信するとトランザクションを行うと、再送信操作を分割する必要があります**MoveToNextTransport**と**MoveToSuspendQ**別々 のバッチにします。 多くのアダプターでは、その後の処理のために、複数のエンドポイントへ送信されたメッセージのバッチを別々のメッセージ一覧に振り分けます。  
  
 注意が必要なのは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] には、トランザクションに関連付けられた規則以外に、バッチ処理されているメッセージに関連付けられる規則がないことです。 バッチ処理は、アダプターが [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に対する送受信メッセージをまとめるための実装固有の方法にすぎません。  
  
 アダプターは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] から渡された複数の小さなバッチのメッセージを、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] への応答として 1 つの大きなバッチにまとめることができます。 この処理では、非常に小さな多数のメッセージを処理するトランザクション アダプターで大幅な最適化が行われる場合があります。 この最適化により、"メッセージごとの総トランザクション数" の比率が最小になります。  
  
 通常、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、5 ～ 10 メッセージの送信側バッチが生成されます。 それらのメッセージが小さい場合、アダプターは削除のトランザクション バッチを [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に送信する前に、100 メッセージ以上を 1 つのバッチにする場合があります。 このような最適化を実装するのは困難です。メッセージがアダプター メモリにとどまらないようにする一方で、基準値を満たすまで無期限に待機する必要があるためです。  
  
 バッチ処理の重要度は [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の MQSeries などの高スループットのアダプターのパフォーマンス数値に表れます。 これらのアダプターでは、1 回のメッセージの送信で少なくとも 2 回、そのメッセージが受信されます。 既定では、受信アダプターでは 100 メッセージのバッチを使用し、送信アダプターでは、提供された既定の [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] バッチを使用します。  
  
## <a name="transactional-batches"></a>トランザクション バッチ  
 トランザクション オブジェクトを作成して [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に渡すアダプターを記述する場合、次の操作を実行するコードを記述する必要があります。  
  
-   バッチ操作の最終結果として、トランザクションのコミットまたは終了のいずれかを決定します。 これは、メッセージ キュー (MSMQ) のキューへの書き込みやトランザクション データベース操作など、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に依存しない特定のトランザクションに含まれている他のトランザクション分岐に依存する場合があります。  
  
-   通知[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を呼び出して最終結果の**IBTDTCCommitConfirm.DTCCommitConfirm**メソッドです。 `true` が返された場合は、トランザクションのコミットが成功したことを示し、`false` が返された場合は、トランザクションが失敗してロールバックしたことを示します。  
  
 アダプターは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] にトランザクションの最終結果を知らせて内部の追跡データを維持する必要があります。 通知は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を呼び出して結果の**DTCCommitConfirm**です。 アダプターがこの呼び出しを行わない場合、重大なメモリ リークが発生して、操作が正常に完了した場合にも MSDTC トランザクションがタイムアウトして失敗することがあります。