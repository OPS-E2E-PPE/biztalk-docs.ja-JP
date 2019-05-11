---
title: 手順 8:エコー アダプターの同期受信ハンドラーを実装する |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 723eac73-40c4-41b4-aca1-dd7451d25bfe
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e3a692493b39b51499a2a42adfcbd485dd4cfc0e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65363147"
---
# <a name="step-8-implement-the-synchronous-inbound-handler-for-the-echo-adapter"></a>手順 8:エコー アダプターの同期受信ハンドラーを実装します。
![手順 9 の 8](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-8of9.gif "Step_8of9")  
  
 **所要時間:** 45 分  
  
 この手順では、エコー アダプターの受信機能を実装します。 この機能により、データまたは対象システムからイベントをリッスンするアダプター。 に従って、 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]、のみを実装する必要があります、`Microsoft.ServiceModel.Channels.Common.IInboundHandler`アダプターが受信機能をサポートする場合にインターフェイスです。 [!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)] EchoAdpterInboundHandler を要求する派生クラスが自動的に生成されます。  
  
 次のセクションでは、このインターフェイスを実装する方法について理解を深めるために EchoAdpterInboundHandler クラスを更新します。 この手順を完了すると、エコー アダプターの受信ハンドラーを作業があります。  
  
## <a name="prerequisites"></a>前提条件  
 この手順を開始する前にする必要がありますが正常に完了して[手順 7。エコー アダプターの同期送信ハンドラーを実装する](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-7-implement-the-synchronous-outbound-handler-for-the-echo-adapter.md)します。 基本的な知識`Microsoft.ServiceModel.Channels.Common.IInboundHandler`も便利です。  
  
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
  
|方法|説明|  
|------------|-----------------|  
|StartListener|指定された Ws-addressing アクションを含むメッセージをリッスンを開始します。 すべてをリッスンし、指定されていない場合や、既定のアクション。|  
|StopListener|リッスンを停止します。|  
|TryReceive|ターゲット システムから受信メッセージを受信しようとします。|  
|WaitForMessage|ターゲット システムから受信 WCF メッセージを待ちます。|  
  
 各メソッドのパラメーターの説明について詳しくは、ドキュメントを参照して、`Microsoft.ServiceModel.Channels.Common.IInboundHandler`インターフェイス。  
  
## <a name="implementing-the-echoadpterinboundhandler"></a>EchoAdpterInboundHandler を実装します。  
 エコー アダプターを使用して、`System.IO.FileSystemWatcher`ターゲット システムをシミュレートします。 内の各メソッドを実装する、次に、 `Microsoft.ServiceModel.Channels.Common.IInboundHandler` StartListener、StopListener、TryReceive、WaitForMessage インターフェイスします。  
  
#### <a name="to-implement-iinboundhandler-interface-in-the-echoadpterinboundhandler-class"></a>EchoAdpterInboundHandler クラスで IInboundHandler インターフェイスを実装するには  
  
1.  ソリューション エクスプ ローラーで、 **EchoAdapterInboundHandler.cs**ファイル。  
  
2.  Visual Studio エディターでは、using ディレクティブの既存のセットに次の行を追加します。  
  
    ```csharp  
    using System.IO;  
    using System.ServiceModel.Channels;  
    using System.Xml;  
    using System.Diagnostics;  
    ```  
  
3.  今すぐ EchoAdapterInboundHandler クラスにクラス レベルの変数を追加します。 これらの変数は、ファイル システム ファイルのアクティビティの監視に使用されます。 コンス トラクターの前に、クラス宣言の下にコピーします。  
  
    ```csharp  
    private Queue<Message> inboundQueue;  
    private FileSystemWatcher inboundWatcher;  
    private Object inboundQueueSynchronizationLock;  
    private string path;  
    private string filter;  
    ```  
  
4.  EchoAdapterInboundHandler コンス トラクター メソッド内では、インフラストラクチャを監視するファイルを初期化するために、監視のパスとフィルターをキャプチャして、次のコードを追加します。  
  
    ```csharp  
    inboundWatcher = null;  
    inboundQueueSynchronizationLock = new Object();  
    path = connection.ConnectionFactory.Adapter.InboundFileSystemWatcherFolder;  
    filter = connection.ConnectionFactory.Adapter.InboundFileFilter;  
    ```  
  
5.  次のコードを追加、 **StartListener**メソッド。 コードでは、パラメーターを確認し、ファイルのアクティビティの監視を開始するためのロジックを実装します。  
  
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
  
6.  実装を追加することで引き続き、 **StopListener**メソッド。  
  
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
  
7.  今すぐ実装を提供、 **TryReveive**メソッド。 このメソッドは、最新のファイルを取得します。 1 つが使用可能な場合は、内部キューからメッセージを受信します。  
  
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
  
8.  実装を追加することで引き続き、 **WaitForMessage**メソッド。  
  
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
  
9. 今すぐファイル ウォッチャーにコールバックを指定します。 これを行うには、新しいメソッドを追加**FileMonitor_Created**を**EchoAdapterInboundAdapter**クラス。  
  
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
  
10. 削除する必要がありますので、 **NotImplementedException**内部によってスローされた例外**EchoAdapterInboundReply**クラス。 これを行うには、次のステートメントを削除、**中止**と**応答**メソッド。  
  
    ```csharp  
    throw new NotImplementedException("The method or operation is not implemented.");  
    ```  
  
     **中止**と**応答**メソッドは、次のようになります。  
  
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
  
11. 受信ハンドラーの実装を完了するには、次のクラスを追加**EchoAdapterOutboundHandler.cs**します。 このクラスは、受信ハンドラーの実装のタイムアウトのサポートを提供します。  
  
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
  
12. Visual Studio での**ファイル** メニューのをクリックして**すべて保存**します。  
  
13. **[ビルド]** メニューの **[ソリューションのビルド]** をクリックします。 これは、エラーなしでコンパイルする必要があります。 そうでない場合は、上記のすべての手順に従っていることを確認します。  
  
> [!NOTE]
>  これで作業が保存されました。 安全にこの時点で Visual Studio を閉じて、次の手順に進むまたは[手順 9。ビルドおよび配置エコー アダプター](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-9-build-and-deploy-the-echo-adapter.md)します。  
  
## <a name="what-did-i-just-do"></a>でしただけ何か。  
 エコー アダプターのチュートリアルのこの手順では、受信ハンドラーの実装を提供します。 この実装は、ファイルを使用してエコー アダプターの機能の監視を提供、 **FileSystemWatcher** .NET Framework のクラス。  
  
## <a name="next-steps"></a>次の手順  
 次の手順では、アダプターをデプロイします。  
  
## <a name="see-also"></a>参照  
 [手順 9:ビルドおよびエコー アダプターの展開](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-9-build-and-deploy-the-echo-adapter.md)   
 [手順 7:エコー アダプターの同期送信ハンドラーを実装する](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-7-implement-the-synchronous-outbound-handler-for-the-echo-adapter.md)