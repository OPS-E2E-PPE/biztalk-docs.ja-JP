---
title: "手順 8: エコー アダプターの同期受信ハンドラーを実装する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 723eac73-40c4-41b4-aca1-dd7451d25bfe
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: da34bca28f073babac4907b7d408d0642a234e2a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-8-implement-the-synchronous-inbound-handler-for-the-echo-adapter"></a>手順 8: エコー アダプターの同期受信ハンドラーを実装します。
![手順 9 の 8](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-8of9.gif "Step_8of9")  
  
 **所要時間:** 45 分  
  
 この手順では、エコー アダプターの受信機能を実装します。 この機能により、データまたは対象システムからのイベントをリッスンするアダプター。 よると、 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]、のみを実装する必要があります、`Microsoft.ServiceModel.Channels.Common.IInboundHandler`アダプターは、受信機能をサポートしている場合は、インターフェイスです。 [!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)] EchoAdpterInboundHandler を要求する派生クラスが自動的に生成されます。  
  
 次のセクションでは、このインターフェイスを実装する方法について理解を深めるために EchoAdpterInboundHandler クラスを更新します。 この手順を完了したときに、エコー アダプターの作業の受信ハンドラーを持ちます。  
  
## <a name="prerequisites"></a>前提条件  
 この手順を開始する前にする必要がありますが正常に完了しました[手順 7: エコー アダプターの同期送信ハンドラーの実装](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-7-implement-the-synchronous-outbound-handler-for-the-echo-adapter.md)です。 基礎知識`Microsoft.ServiceModel.Channels.Common.IInboundHandler`も便利です。  
  
## <a name="the-iinboundhandler-interface"></a>IInboundHandler インターフェイス  
 `Microsoft.ServiceModel.Channels.Common.IInboundHandler`として定義されます。  
  
```  
public interface IInboundHandler : IConnectionHandler, IDisposable  
{  
          void StartListener(string[] actions, TimeSpan timeout);  
          void StopListener(TimeSpan timeout);  
          bool TryReceive(TimeSpan timeout, out Message message, out IInboundReply reply);  
          bool WaitForMessage(TimeSpan timeout);  
}  
```  
  
 メソッドの説明は次のとおりです。  
  
|方法|Description|  
|------------|-----------------|  
|StartListener|指定された Ws-addressing アクションがあるメッセージのリッスンを開始します。 すべてをリッスンが指定されていない場合や、既定の操作です。|  
|StopListener|待機を停止します。|  
|TryReceive|対象システムから受信メッセージを受信しようとしています。|  
|WaitForMessage|対象システムから受信 WCF メッセージを待機します。|  
  
 各メソッドのパラメーターの説明の詳細については、ドキュメントを参照して、`Microsoft.ServiceModel.Channels.Common.IInboundHandler`インターフェイスです。  
  
## <a name="implementing-the-echoadpterinboundhandler"></a>EchoAdpterInboundHandler を実装します。  
 エコー アダプターを使用して、`System.IO.FileSystemWatcher`をターゲット システムをシミュレートします。 内の各メソッドを実装する次の場合、 `Microsoft.ServiceModel.Channels.Common.IInboundHandler` StartListener、StopListener、TryReceive および WaitForMessage、インターフェイスです。  
  
#### <a name="to-implement-iinboundhandler-interface-in-the-echoadpterinboundhandler-class"></a>インターフェイスを実装する IInboundHandler EchoAdpterInboundHandler クラス  
  
1.  ソリューション エクスプ ローラーで、 **EchoAdapterInboundHandler.cs**ファイル。  
  
2.  Visual Studio エディターでは、ディレクティブを使用する既存のセットに次の行を追加します。  
  
    ```csharp  
    using System.IO;  
    using System.ServiceModel.Channels;  
    using System.Xml;  
    using System.Diagnostics;  
    ```  
  
3.  今すぐ EchoAdapterInboundHandler クラスをクラス レベルの変数を追加します。 これらの変数は、ファイル システム ファイルの活動で監視に使用されます。 コンス トラクターは、前に、クラス宣言の下にコピーします。  
  
    ```csharp  
    private Queue<Message> inboundQueue;  
    private FileSystemWatcher inboundWatcher;  
    private Object inboundQueueSynchronizationLock;  
    private string path;  
    private string filter;  
    ```  
  
4.  EchoAdapterInboundHandler コンス トラクター メソッドの内部インフラストラクチャを監視するファイルを初期化するために、フィルターと監視のパスをキャプチャして、次のコードを追加します。  
  
    ```csharp  
    inboundWatcher = null;  
    inboundQueueSynchronizationLock = new Object();  
    path = connection.ConnectionFactory.Adapter.InboundFileSystemWatcherFolder;  
    filter = connection.ConnectionFactory.Adapter.InboundFileFilter;  
    ```  
  
5.  次のコードを追加、 **StartListener**メソッドです。 コードでは、パラメーターを確認し、ファイルのアクティビティの監視を開始するためのロジックを実装します。  
  
    ```csharp  
    // if no actions are provided, log an error in the trace log  
    // and throw an exception  
    if (actions.Length == 0)  
    {  
        EchoAdapterUtilities.Trace.Trace(TraceEventType.Error, "http://echoadapterv2/startlistener/noactions", "No operation actions were received for listener to do specific processing.", this);  
        throw new AdapterException("Unable to receive any actions for inbound handler to start listening.");  
    }  
  
    inboundQueue = new Queue<Message>();  
    foreach (string action in actions)  
    {  
        // for the OnReceiveEcho action listen for a new file created event  
        if ("Echo/OnReceiveEcho".Equals(action))  
        {  
            if (inboundWatcher == null)  
            {  
                inboundWatcher = new FileSystemWatcher(path);  
                inboundWatcher.Filter = filter;  
                // Begin monitoring  
                inboundWatcher.EnableRaisingEvents = true;  
            }  
            inboundWatcher.Created += new FileSystemEventHandler(FileMonitor_Created);  
            EchoAdapterUtilities.Trace.Trace(TraceEventType.Information, "http://echoadapterv2/startlistener", "Listening for file created event for " + filter + " in path " + path, this);  
        }  
    }  
    ```  
  
6.  実装を追加することにより続行、 **StopListener**メソッドです。  
  
    ```csharp  
    if (inboundWatcher != null)  
    {  
        // End monitoring  
        inboundWatcher.EnableRaisingEvents = false;  
        inboundWatcher = null;  
    }  
    lock (inboundQueueSynchronizationLock)  
    {  
        inboundQueue.Clear();  
        inboundQueue = null;  
    }  
    ```  
  
7.  実装を提供するようになりました、 **TryReveive**メソッドです。 このメソッドは、最新のファイルを取得します。 1 つが利用可能な場合は、内部キューからメッセージを受信します。  
  
    ```csharp  
    reply = new EchoAdapterInboundReply();  
    message = null;  
    TimeoutHelper timeoutHelper = new TimeoutHelper(timeout);  
    while (true)  
    {  
        lock (inboundQueueSynchronizationLock)  
        {  
            if (inboundQueue == null)  
            {  
                //listener has been closed  
                return false;  
            }  
            if (inboundQueue.Count != 0)  
            {  
                message = inboundQueue.Dequeue();  
                if (message != null)  
                {  
                    return true;  
                }  
            }  
        }  
        if (timeoutHelper.IsExpired)  
        {  
            return false;  
        }  
        //wait for sometime, and check again  
        System.Threading.Thread.Sleep(500);  
    }  
    ```  
  
8.  実装を追加することにより続行、 **WaitForMessage**メソッドです。  
  
    ```csharp  
    while (inboundQueue.Count == 0) { };  
    Message msg = inboundQueue.Peek();  
    if (msg != null)  
    {  
        return true;  
    }  
    else  
    {  
        return false;  
    }  
    ```  
  
9. これで、ファイルの監視のコールバックを指定します。 新しいメソッドを追加するには、 **FileMonitor_Created**を**EchoAdapterInboundAdapter**クラスです。  
  
    ```csharp  
    private void FileMonitor_Created(object sender, FileSystemEventArgs e)  
    {  
        lock (inboundQueueSynchronizationLock)  
        {  
            if (e.ChangeType == WatcherChangeTypes.Created)  
            {  
                // wait for file to close - should do this in a better manner  
                System.Threading.Thread.Sleep(500);  
                try  
                {  
                    EchoAdapterUtilities.Trace.Trace(TraceEventType.Information, "http://echoadapterv2/FileMonitorCreated", "File " + e.FullPath + " created.", this);  
                    FileInfo fileInfo = new FileInfo(e.FullPath);  
                    // Create WCF message to send to the inbound service  
                    // that is listening for messages from adapter  
                    String xmlData = String.Format(@"<OnReceiveEcho xmlns=""{0}""><path>{1}</path><length>{2}</length></OnReceiveEcho>", EchoAdapter.SERVICENAMESPACE, e.FullPath, fileInfo.Length);  
                    // set action string  
                    XmlReader reader = XmlReader.Create(new StringReader(xmlData));  
                    // create WCF message  
                    Message requestMessage = Message.CreateMessage(MessageVersion.Default  
                                , "Echo/OnReceiveEcho"  
                                , reader);  
                    requestMessage.Headers.To = new Uri(path);  
                    inboundQueue.Enqueue(requestMessage);  
                }  
                catch (Exception ex)  
                {  
                    String message = String.Format("An exception was thrown while trying to open file {1}.", e.FullPath);  
                    EchoAdapterUtilities.Trace.Trace(System.Diagnostics.TraceEventType.Error, "http://echoadapterv2/FileMonitorCreated", message, this, ex);  
                    throw new AdapterException(message, ex);  
                }  
            }  
        }  
    }  
    ```  
  
10. これで、削除する必要があります、 **NotImplementedException**内部によってスローされた例外**EchoAdapterInboundReply**クラスです。 これを行うには、次のステートメントを削除、**中止**と**返信**メソッドです。  
  
    ```csharp  
    throw new NotImplementedException("The method or operation is not implemented.");  
    ```  
  
     **中止**と**返信**メソッドは、次のようにする必要があります。  
  
    ```csharp  
    /// <summary>  
    /// Abort the inbound reply call  
    /// </summary>  
    public override void Abort()  
    {  
    }  
  
    /// <summary>  
    /// Reply message implemented  
    /// </summary>  
    public override void Reply(System.ServiceModel.Channels.Message message  
        , TimeSpan timeout)  
    {  
    }  
    ```  
  
11. 完了するには、受信ハンドラーの実装を次のクラスを追加**EchoAdapterOutboundHandler.cs**です。 このクラスは、受信ハンドラーの実装のタイムアウトのサポートを提供します。  
  
    ```csharp  
    /// <summary>  
    /// Utility class containing helper functions for measuring timeout   
    /// </summary>  
    class TimeoutHelper  
    {  
        private TimeSpan timeout;  
        private DateTime creationTime;  
        private Boolean isInfinite;  
  
        /// <summary>  
        /// Constructor  
        /// </summary>  
        /// <param name="timeout"></param>  
        public TimeoutHelper(TimeSpan timeout)  
        {  
            this.creationTime = DateTime.Now;  
            this.timeout = timeout;  
            if (timeout.Equals(Infinite)) this.isInfinite = true;  
        }  
  
        /// <summary>  
        /// Value of infinite timespan  
        /// </summary>  
        public static TimeSpan Infinite  
        {  
            get { return TimeSpan.MaxValue; }  
        }  
  
        /// <summary>  
        /// Value indicating remaining timeout  
        /// </summary>  
        public TimeSpan RemainingTimeout  
        {  
            get  
            {  
                if (this.isInfinite) return Infinite;  
                return this.timeout.Subtract(DateTime.Now.Subtract(this.creationTime));  
            }  
        }  
  
        /// <summary>  
        /// Get remaining timeout value and throw an exception if the timeout  
        /// has expired.  
        /// </summary>  
        /// <param name="exceptionMessage"></param>  
        /// <returns></returns>  
        public TimeSpan GetRemainingTimeoutAndThrowIfExpired(String exceptionMessage)  
        {  
            if (this.isInfinite) return Infinite;  
            if (RemainingTimeout < TimeSpan.Zero)  
            {  
                throw new TimeoutException(exceptionMessage);  
            }  
            return RemainingTimeout;  
        }  
  
        /// <summary>  
        /// Throw an exception if the timeout has expired.  
        /// </summary>  
        /// <param name="exceptionMessage"></param>  
        public void ThrowIfTimeoutExpired(String exceptionMessage)  
        {  
            if (RemainingTimeout < TimeSpan.Zero)  
            {  
                throw new TimeoutException(exceptionMessage);  
            }  
  
        }  
  
        /// <summary>  
        /// Value indicating whether timeout has expired.  
        /// </summary>  
        public Boolean IsExpired  
        {  
            get  
            {  
                if (this.isInfinite) return false;  
                return RemainingTimeout < TimeSpan.Zero;  
            }  
        }  
    }  
    ```  
  
12. Visual Studio での**ファイル** メニューのをクリックして**すべて保存**です。  
  
13. **[ビルド]** メニューの **[ソリューションのビルド]**をクリックします。 これは、エラーなしでコンパイルする必要があります。 以外の場合は、上記のすべてのステップに従っていることを確認します。  
  
> [!NOTE]
>  これで作業が保存されました。 安全にこの時点で Visual Studio を終了したり、次の手順に進みます[手順 9: ビルドし、配置エコー アダプター](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-9-build-and-deploy-the-echo-adapter.md)です。  
  
## <a name="what-did-i-just-do"></a>でしただけは何ですか。  
 エコー アダプター チュートリアルのこのステップでは、受信ハンドラーの実装を提供します。 この実装を使用してエコー アダプターの機能を見てファイルを提供する、 **FileSystemWatcher** .NET Framework のクラスです。  
  
## <a name="next-steps"></a>次の手順  
 次の手順では、アダプターを展開します。  
  
## <a name="see-also"></a>参照  
 [手順 9: ビルドをエコー アダプターの展開](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-9-build-and-deploy-the-echo-adapter.md)   
 [手順 7: エコー アダプターの同期送信ハンドラーを実装します。](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-7-implement-the-synchronous-outbound-handler-for-the-echo-adapter.md)