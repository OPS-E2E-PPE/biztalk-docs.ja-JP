---
title: "送信アダプターの交換パターン |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5ad65fb5-640d-4bd2-aabe-946210f58a22
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 997aaa9a92f90f30bdaaeb59cc9cecb0c454496f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="exchange-patterns-for-send-adapters"></a>送信アダプターの交換パターン
送信アダプターには、BizTalk メッセージング エンジンから、回線で送信されるメッセージが配信されます。 配信されたメッセージは、一方向または双方向のメッセージ交換パターンを使用して送信される場合があります。 この双方向のメッセージ交換パターンを処理するアダプターを送信請求 - 応答アダプターと呼びます。  
  
## <a name="blocking-vs-non-blocking-transmissions"></a>Vs をブロックしています。非ブロッキング送信  
 メッセージング エンジンでは、送信アダプターにメッセージを配信するかを使用して、 **IBTTransmitter.TransmitMessage**メソッドまたは**IBTTransmitterBatch.TransmitMessage**かどうかに応じて、メソッドアダプターはバッチ対応です。 どちらのメソッドにも、アダプターがメッセージを送信した方法を示すブール値が返されます。 アダプターが `true` を返した場合、メッセージの送信が既に完了していることを示しています。 この場合、アダプターの代わりにメッセージング エンジンによってメッセージ ボックス データベースからメッセージが削除されます。 アダプターが `false` を返した場合、メッセージの送信は開始されていますが、まだ送信が完了していないことを示します。 この場合、アダプターはアプリケーション キューからメッセージを削除するだけでなく、メッセージの再送信または保留の試行が必要になる送信エラーも処理します。  
  
 返すアダプター`false`つまり、非ブロッキング呼び出しには、 **TransmitMessage**実装コードは、メッセージング エンジンの呼び出し元のスレッドをブロックしません。 アダプターは、送信準備が完了したインメモリ キューにメッセージを追加し、その後、値を返すだけです。 このアダプターには、インメモリ キューの提供とメッセージの送信を行い、その後にエンジンに対して送信結果を通知する独自のスレッド プールが必要です。  
  
 通常、メッセージング エンジンのスレッドの方が、回線でのデータ送信に使用されるスレッドよりも CPU の制約を受けます。 この 2 種類のスレッドを混合して使用すると、パフォーマンスに悪影響を及ぼします。 非ブロッキング送信を使用すると 2 種類のスレッドを切り離せるので、ブロッキング呼び出しのパフォーマンスを大幅に向上させることができます。  
  
 I/O 操作の制約を受ける傾向があるアダプターのスレッド プールを次の図に示します。 BizTalk Server メッセージング エンジンのスレッド プールの方が CPU 処理の制約を受けます。 2 種類のスレッド プールを保持し、同じ種類のスレッドを混合しないことによって、システムのパフォーマンスをこれまでよりも向上させることができます。  
  
 ![](../core/media/io-cpu-bound-threadpools.gif "Io_cpu_bound_threadpools")  
  
 **パフォーマンス ヒント:**最適なパフォーマンスを送信アダプターする必要が非ブロッキングとバッチに注意してください。 BizTalk ファイル アダプターをブロッキング呼び出しを行うバッチ非対応から、非ブロッキング呼び出しを行うバッチ対応に変更すると、パフォーマンスが 3 倍向上します。  
  
 **トラブルシューティングのヒント:**ブロッキング送信ホスト インスタンス全体のパフォーマンスの低下が発生することができます。 場合、アダプターはで過度のブロッキング**TransmitMessage**エンジンのスレッドから他のアダプターにメッセージを配信できなくなります。  
  
## <a name="non-batched-sends"></a>バッチ化されていない送信  
 バッチ対応アダプターを実装する必要があります**IBTTransmitter**詳しく説明したよう[非同期送信アダプター用のインターフェイス](../core/interfaces-for-an-asynchronous-send-adapter.md)です。 アダプターがメッセージング エンジンに送信する必要がある各メッセージの呼び出しに対する**IBTTransmitter.TransmitMessage**です。 次のオブジェクト間の対話処理図は、一般的なメッセージの送信方法の詳細について示しています。その方法は、次に示す手順で構成されています。  
  
1.  エンジンがメッセージをアダプターに配信します。  
  
2.  アダプターが、送信準備のできているインメモリ キューにメッセージを追加します。  
  
3.  アダプターのスレッド プールのスレッドが、キューからメッセージを取り出し、メッセージの構成を読み取って回線でメッセージを送信します。  
  
4.  アダプターが新しいバッチをエンジンから取得します。  
  
5.  アダプターが**DeleteMessage**だけが送信されるメッセージを渡して、バッチにします。  
  
6.  アダプターが**完了**バッチにします。  
  
7.  エンジンは、バッチを処理し、アプリケーション キューからメッセージを削除します。  
  
8.  エンジンはコールバックにアダプターの結果を通知する、 **DeleteMessage**操作します。  
  
 ![](../core/media/deleting-from-message-queue.gif "Deleting_from_message_queue")  
  
 上記のオブジェクト間の対話処理図は、1 通のメッセージをアプリケーション キューから削除するアダプターを示しています。 ただし、一度に 1 通のメッセージを操作するのではなく、すべてのメッセージ操作をアダプターでバッチにするのが理想的です。  
  
## <a name="batched-sends"></a>バッチ化された送信  
 バッチ対応であるアダプターを実装する必要があります**IBTBatchTransmitter**と**IBTTransmitterBatch**詳しく説明したよう[送信アダプター用のインターフェイス](../core/interfaces-for-send-adapters.md)です。 エンジンが、呼び出すことによってアダプターから新しいバッチを取得、エンジンがメッセージを送信するアダプターの場合、 **IBTBatchTransmitter.GetBatch**です。 アダプターを実装する新しいバッチ オブジェクトを返します**IBTTransmitterBatch**です。 エンジンを呼び出してバッチを開始し**IBTTransmitterBatch.BeginBatch**です。 この API には、アダプターがバッチで受け入れるメッセージの最大数をアダプターで指定することができる出力パラメーターがあります。 アダプターは、任意に DTC トランザクションを返すことがあります。 エンジンが呼び出す、 **IBTTransmitterBatch.TransmitMessage**バッチに追加する送信メッセージごとに 1 回です。 その呼び出し回数は、0 より大きく、かつ、アダプターで指定されたバッチの最大サイズ以下です。 アダプターが呼び出すすべてのメッセージがバッチに追加したら、 **IBTTransmitterBatch.Done**です。 この時点で、通常、アダプターはバッチ内のすべてのメッセージをインメモリ キューに追加します。 アダプターは、バッチ非対応のアダプターの場合と同様に、アダプター独自のスレッド プールに含まれている 1 つまたは複数のスレッドからメッセージを送信します。 次に、アダプターは送信結果をエンジンに通知します。  
  
 次のオブジェクト間の対話処理図に、バッチ化された送信アダプターによって 2 通のメッセージが送信されるようすを示します。  
  
 ![](../core/media/batchedsends.gif "BatchedSends")  
  
## <a name="handling-transmission-failures"></a>送信エラーの処理  
 送信エラーの推奨セマンティクスを次の図に示します。 これらのセマンティクスは推奨にすぎず、メッセージング エンジンによって適用されるものではありません。 有効な理由があるが、注意が必要ここでは、次のガイドラインから逸脱したアダプターを開発することができます。 たとえば、アダプターは一般的に、再試行回数分だけ再試行した後、必ずメッセージをバックアップ トランスポートに移動する必要があります。  
  
 さらに一般的なこととして、トランスポートでは、構成されている回数よりも多くの再試行を行う必要がある場合があります。 トランスポート層の回復性は向上しているので、その差がわずかな場合には、対応可能と見なされます。 一般的に、メッセージング エンジンによって公開される API は、可能な場合にはアダプターに最大限の制御を与えるように設計されています。 この制御により、より優れたレベルの応答性を実現できます。  
  
 ![](../core/media/handlingerrors.gif "HandlingErrors")  
  
 アダプターが、システム コンテキスト プロパティをチェックして、メッセージで使用できる再試行回数を決定**RetryCount**です。 アダプターが、 **Resubmit** API 1 回ごとに再試行してください再送信するメッセージに渡します。 また、メッセージのほか、エンジンからアダプターへのメッセージ配信時刻を示すタイム スタンプも渡します。 この値は通常、現在の時刻の値を加えた**RetryInterval**です。 **RetryInterval**システム コンテキスト プロパティの単位は分です。 両方の**RetryCount**と**RetryInterval**メッセージ コンテキストでは、送信ポートで構成されている値。 同一の BizTalk ホストのインスタンスが複数のコンピューター上に配置されているスケールアウト配置を考えてみます。 再試行間隔の有効期限が切れた後でメッセージが配信されると、そのメッセージは実行するように構成されている任意のコンピューター上のいずれかのホスト インスタンスに配信されることがあります。 このような理由から、その後の送信もアダプターの同一インスタンスによって実行される保証がないため、再試行で使用するメッセージに関連付けられているどの状態も、アダプターでは保持しないようにする必要があります。  
  
 アダプターでは、再試行回数が 0 以下になった後は、メッセージをバックアップ トランスポートに移動しようとするだけです。 ポートにバックアップ トランスポートが構成されていない場合、メッセージをバックアップ トランスポートに移動しようとしても失敗します。 この場合、メッセージは保留されます。  
  
 次のコードは、メッセージ コンテキストから再試行回数と再試行間隔を決定し、次にバックアップ トランスポートへの再送信または移動を行う方法を示しています。  
  
```  
using Microsoft.XLANGs.BaseTypes;  
using Microsoft.BizTalk.Message.Interop;  
using Microsoft.BizTalk.TransportProxy.Interop;  
 …  
// RetryCount and RetyInterval are system context properties...  
private static readonly PropertyBase RetryCountProperty =   
 new BTS.RetryCount();  
private static readonly PropertyBase RetryIntervalProperty =   
 new BTS.RetryInterval();  
  
public void HandleRetry(IBaseMessage msg, IBTTransportBatch batch)  
{  
int retryCount = 0;  
int retryInterval = 0;  
  
// Get the RetryCount and RetryInterval off the msg ctx...  
 GetMessageRetryState(msg, out retryCount, out retryInterval);  
  
// If we have retries available resubmit, else move to   
 // backup transport...  
 if ( retryCount > 0 )  
batch.Resubmit(  
 msg, DateTime.Now.AddMinutes(retryInterval));  
else  
batch.MoveToNextTransport(msg);  
}  
  
public void GetMessageRetryState(  
 IBaseMessage msg,   
 out int retryCount,   
 out int retryInterval )  
{  
retryCount = 0;  
retryInterval = 0;  
  
object obj =  msg.Context.Read(  
RetryCountProperty.Name.Name,    
RetryCountProperty.Name.Namespace);   
  
if ( null != obj )  
retryCount = (int)obj;  
  
obj =  msg.Context.Read(  
RetryIntervalProperty.Name.Name,    
RetryIntervalProperty.Name.Namespace);   
  
if ( null != obj )  
retryInterval = (int)obj;  
}  
```  
  
## <a name="throwing-an-exception-from-transmitmessage"></a>TransmitMessage からの例外のスロー  
 アダプターが Api のいずれかで例外をスローするかどうかは**IBTTransmitter.TransmitMessage**、 **IBTTransmitterBatch.TransmitMessage**、 **IBTTransmitterBatch.Done**では、エンジンが送信エラーと関連するメッセージの送信を処理しで詳しく説明されている、メッセージの適切な措置を取ります[アダプターの障害を処理する方法](../core/how-to-handle-adapter-failures.md)です。  
  
 バッチ対応の送信アダプターの場合、TransmitMessage API で例外を送信するとバッチ全体が消去され、既定の送信エラー操作がバッチ内のすべてのメッセージに対して実行されます。  
  
## <a name="solicit-response"></a>[送信請求 - 応答]  
 通常、双方向の送信アダプターでは、一方向の送信と双方向の送信の両方がサポートされます。 送信アダプターを調べることによって、メッセージを一方向または双方向の送信に転送される必要があるかどうかを決定する、 **IsSolicitResponse**メッセージ コンテキストのシステム コンテキスト プロパティです。  
  
 このコード例の一部を次に示します。  
  
```  
private bool portIsTwoWay = false;  
private static readonly PropertyBase IsSolicitResponseProperty= new BTS.IsSolicitResponse();  
  
...  
  
 // Port is one way or two way...  
 object obj =  this.message.Context.Read(  
 IsSolicitResponseProperty.Name.Name,    
 IsSolicitResponseProperty.Name.Namespace);   
  
if ( null != obj )  
 this.portIsTwoWay = (bool)obj;  
```  
  
 アダプターは、送信請求 - 応答送信の間、送信請求メッセージを送信します。 この操作の完了後、アダプターは関連する応答を送信し、最初の送信請求メッセージをメッセージ ボックス データベースから削除するようにメッセージング エンジンに通知します。 アプリケーション キューからメッセージを削除するこの操作は、応答メッセージの送信と同じトランスポート プロキシ バッチ内で実行する必要があります。 これにより、応答の削除および送信における原子性が確保されます。 原子性を完全に維持するには、アダプターは、トランザクション対応リソースへの送信請求メッセージの送信、応答メッセージの送信、および送信請求メッセージの削除がすべて同一の DTC トランザクションのコンテキストに含まれている DTC トランザクションを使用する必要があります。 ここでも、送信請求メッセージを非ブロッキング送信を使用して送信することをお勧めします。  
  
 次のコードは、双方向の送信の主要な側面を示しています。 エンジンを呼び出すと**IBTTransmitter.TransmitMessage**アダプターが、インメモリ キューに送信するメッセージをエンキューします。 アダプターは `false` を返して、非ブロッキング送信を実行していることを示します。 アダプターのスレッド プール (**WorkerThreadThunk**) サービスのメモリ内キューとヘルパー メソッドに渡すメッセージをデキューします。 このメソッドの役割は、送信請求メッセージを送信して応答メッセージを受信することです  (このヘルパー メソッドの実装はこのトピックの対象範囲外です)。応答メッセージはエンジンに送信され、送信請求メッセージはアプリケーション キューから削除されます。  
  
```  
using System.Collections;  
using Microsoft.XLANGs.BaseTypes;  
using Microsoft.BizTalk.Message.Interop;  
using Microsoft.BizTalk.TransportProxy.Interop;  
  
     static private Queue _transmitQueue = new Queue();  
  static private IBTTransportProxy _transportProxy = null;   
// IBTTransmitter...  
 public bool TransmitMessage(IBaseMessage msg)  
{  
// Add message to the transmit queue...  
lock(_transmitQueue.SyncRoot)  
 {  
_transmitQueue.Enqueue(msg);  
 }  
  
 return false;  
}  
  
 // Threadpool worker thread...   
private void WorkerThreadThunk()  
{  
try  
{  
 IBaseMessage solicitMsg = null;  
  
 lock(_transmitQueue.SyncRoot)  
 {  
 solicitMsg =   
 (IBaseMessage)_transmitQueue.Dequeue();  
}  
  
 IBaseMessage responseMsg = SendSolicitResponse(   
 solicitMsg );  
Callback cb = new Callback();  
  
IBTTransportBatch batch = _transportProxy.GetBatch(  
 cb, null);  
batch.SubmitResponseMessage( solicitMsg, responseMsg );  
batch.DeleteMessage( solicitMsg );  
batch.Done(null);  
}  
catch(Exception)  
{  
// Handle failure....  
}  
}  
  
static private IBaseMessage SendSolicitResponse(  
 IBaseMessage solicitMsg )  
{  
// Helper method to send solicit message and receive   
 // response message...  
IBaseMessage responseMsg = null;  
return responseMsg;  
}  
```  
  
## <a name="dynamic-sends"></a>動的送信  
 動的送信ポートには、関連付けられているアダプター構成がありません。 代わりに、動的送信ポートでは、アダプターが動的ポートでメッセージを送信することが必要になる、既定のプロパティのハンドラー構成を使用します。 たとえば、HTTP アダプターでプロキシを使用する場合には、HTTP アダプターで資格情報を指定する必要があります。 アダプターが実行時にキャッシュするハンドラー構成では、ユーザー名、パスワード、およびポートを指定できます。  
  
 動的なメッセージが、経由で送信するのには、トランスポートを決定する、エンジンの**OutboundTransportLocation**アダプターのエイリアスが付いています。 アダプターは、インストール時に 1 つ以上のエイリアスを [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に登録できます。 エンジンは、解析、 **OutboundTransportLocation**一致を見つける実行時にします。 処理のため、アダプターは、 **OutboundTransportLocation**有無にかかわらず、エイリアスが付いています。 次の表に、追加設定なしの BizTalk アダプター用に登録されているエイリアスの例をいくつか示します。  
  
|アダプターのエイリアス|[アダプター]|OutboundTransportLocation の例|  
|-------------------|-------------|---------------------------------------|  
|HTTP://|HTTP|http://www. MyCompany.com/bar|  
|HTTPS://|HTTP|https://www. MyCompany.com/bar|  
|mailto:|SMTP (SMTP)|mailto:A.User@MyCompany.com|  
|FILE://|FILE|FILE://C:\MyCompany \\%MessageID%.xml|