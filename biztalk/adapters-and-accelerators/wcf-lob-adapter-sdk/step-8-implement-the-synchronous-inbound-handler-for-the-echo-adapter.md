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
# <a name="step-8-implement-the-synchronous-inbound-handler-for-the-echo-adapter"></a><span data-ttu-id="c79f2-102">手順 8: エコー アダプターの同期受信ハンドラーを実装します。</span><span class="sxs-lookup"><span data-stu-id="c79f2-102">Step 8: Implement the Synchronous Inbound Handler for the Echo Adapter</span></span>
<span data-ttu-id="c79f2-103">![手順 9 の 8](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-8of9.gif "Step_8of9")</span><span class="sxs-lookup"><span data-stu-id="c79f2-103">![Step 8 of 9](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-8of9.gif "Step_8of9")</span></span>  
  
 <span data-ttu-id="c79f2-104">**所要時間:** 45 分</span><span class="sxs-lookup"><span data-stu-id="c79f2-104">**Time to complete:** 45 minutes</span></span>  
  
 <span data-ttu-id="c79f2-105">この手順では、エコー アダプターの受信機能を実装します。</span><span class="sxs-lookup"><span data-stu-id="c79f2-105">In this step, you implement the inbound capability of the echo adapter.</span></span> <span data-ttu-id="c79f2-106">この機能により、データまたは対象システムからのイベントをリッスンするアダプター。</span><span class="sxs-lookup"><span data-stu-id="c79f2-106">This capability allows the adapter to listen for data or events from the target system.</span></span> <span data-ttu-id="c79f2-107">よると、 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]、のみを実装する必要があります、`Microsoft.ServiceModel.Channels.Common.IInboundHandler`アダプターは、受信機能をサポートしている場合は、インターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="c79f2-107">According to the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], you only need to implement the `Microsoft.ServiceModel.Channels.Common.IInboundHandler` interface, when your adapter supports inbound capability.</span></span> <span data-ttu-id="c79f2-108">[!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)] EchoAdpterInboundHandler を要求する派生クラスが自動的に生成されます。</span><span class="sxs-lookup"><span data-stu-id="c79f2-108">The [!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)] automatically generates the derived class called EchoAdpterInboundHandler for you.</span></span>  
  
 <span data-ttu-id="c79f2-109">次のセクションでは、このインターフェイスを実装する方法について理解を深めるために EchoAdpterInboundHandler クラスを更新します。</span><span class="sxs-lookup"><span data-stu-id="c79f2-109">In the following section, you update the EchoAdpterInboundHandler class to get a better understanding on how to implement this interface.</span></span> <span data-ttu-id="c79f2-110">この手順を完了したときに、エコー アダプターの作業の受信ハンドラーを持ちます。</span><span class="sxs-lookup"><span data-stu-id="c79f2-110">When you complete this step, you have a working inbound handler for the echo adapter.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="c79f2-111">前提条件</span><span class="sxs-lookup"><span data-stu-id="c79f2-111">Prerequisites</span></span>  
 <span data-ttu-id="c79f2-112">この手順を開始する前にする必要がありますが正常に完了しました[手順 7: エコー アダプターの同期送信ハンドラーの実装](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-7-implement-the-synchronous-outbound-handler-for-the-echo-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="c79f2-112">Before you begin this step, you must have successfully completed [Step 7: Implement the Synchronous Outbound Handler for the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-7-implement-the-synchronous-outbound-handler-for-the-echo-adapter.md).</span></span> <span data-ttu-id="c79f2-113">基礎知識`Microsoft.ServiceModel.Channels.Common.IInboundHandler`も便利です。</span><span class="sxs-lookup"><span data-stu-id="c79f2-113">A basic familiarity with `Microsoft.ServiceModel.Channels.Common.IInboundHandler` is also helpful.</span></span>  
  
## <a name="the-iinboundhandler-interface"></a><span data-ttu-id="c79f2-114">IInboundHandler インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c79f2-114">The IInboundHandler Interface</span></span>  
 <span data-ttu-id="c79f2-115">`Microsoft.ServiceModel.Channels.Common.IInboundHandler`として定義されます。</span><span class="sxs-lookup"><span data-stu-id="c79f2-115">The `Microsoft.ServiceModel.Channels.Common.IInboundHandler` is defined as:</span></span>  
  
```  
public interface IInboundHandler : IConnectionHandler, IDisposable  
{  
          void StartListener(string[] actions, TimeSpan timeout);  
          void StopListener(TimeSpan timeout);  
          bool TryReceive(TimeSpan timeout, out Message message, out IInboundReply reply);  
          bool WaitForMessage(TimeSpan timeout);  
}  
```  
  
 <span data-ttu-id="c79f2-116">メソッドの説明は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c79f2-116">The method descriptions are:</span></span>  
  
|<span data-ttu-id="c79f2-117">方法</span><span class="sxs-lookup"><span data-stu-id="c79f2-117">Method</span></span>|<span data-ttu-id="c79f2-118">Description</span><span class="sxs-lookup"><span data-stu-id="c79f2-118">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="c79f2-119">StartListener</span><span class="sxs-lookup"><span data-stu-id="c79f2-119">StartListener</span></span>|<span data-ttu-id="c79f2-120">指定された Ws-addressing アクションがあるメッセージのリッスンを開始します。</span><span class="sxs-lookup"><span data-stu-id="c79f2-120">Starts listening to messages with the provided WS-Addressing Actions.</span></span> <span data-ttu-id="c79f2-121">すべてをリッスンが指定されていない場合や、既定の操作です。</span><span class="sxs-lookup"><span data-stu-id="c79f2-121">If none is specified, it listens to all or the default actions.</span></span>|  
|<span data-ttu-id="c79f2-122">StopListener</span><span class="sxs-lookup"><span data-stu-id="c79f2-122">StopListener</span></span>|<span data-ttu-id="c79f2-123">待機を停止します。</span><span class="sxs-lookup"><span data-stu-id="c79f2-123">Stops listening.</span></span>|  
|<span data-ttu-id="c79f2-124">TryReceive</span><span class="sxs-lookup"><span data-stu-id="c79f2-124">TryReceive</span></span>|<span data-ttu-id="c79f2-125">対象システムから受信メッセージを受信しようとしています。</span><span class="sxs-lookup"><span data-stu-id="c79f2-125">Tries to receive an inbound message from the target system.</span></span>|  
|<span data-ttu-id="c79f2-126">WaitForMessage</span><span class="sxs-lookup"><span data-stu-id="c79f2-126">WaitForMessage</span></span>|<span data-ttu-id="c79f2-127">対象システムから受信 WCF メッセージを待機します。</span><span class="sxs-lookup"><span data-stu-id="c79f2-127">Waits for an inbound WCF message from the target system.</span></span>|  
  
 <span data-ttu-id="c79f2-128">各メソッドのパラメーターの説明の詳細については、ドキュメントを参照して、`Microsoft.ServiceModel.Channels.Common.IInboundHandler`インターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="c79f2-128">For more details on the description for each method parameters, see the documentation on the `Microsoft.ServiceModel.Channels.Common.IInboundHandler` interface.</span></span>  
  
## <a name="implementing-the-echoadpterinboundhandler"></a><span data-ttu-id="c79f2-129">EchoAdpterInboundHandler を実装します。</span><span class="sxs-lookup"><span data-stu-id="c79f2-129">Implementing the EchoAdpterInboundHandler</span></span>  
 <span data-ttu-id="c79f2-130">エコー アダプターを使用して、`System.IO.FileSystemWatcher`をターゲット システムをシミュレートします。</span><span class="sxs-lookup"><span data-stu-id="c79f2-130">The echo adapter uses the `System.IO.FileSystemWatcher` to simulate the target system.</span></span> <span data-ttu-id="c79f2-131">内の各メソッドを実装する次の場合、 `Microsoft.ServiceModel.Channels.Common.IInboundHandler` StartListener、StopListener、TryReceive および WaitForMessage、インターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="c79f2-131">In the following, you implement each method within the `Microsoft.ServiceModel.Channels.Common.IInboundHandler` interface, StartListener, StopListener, TryReceive and WaitForMessage.</span></span>  
  
#### <a name="to-implement-iinboundhandler-interface-in-the-echoadpterinboundhandler-class"></a><span data-ttu-id="c79f2-132">インターフェイスを実装する IInboundHandler EchoAdpterInboundHandler クラス</span><span class="sxs-lookup"><span data-stu-id="c79f2-132">To implement IInboundHandler interface in the EchoAdpterInboundHandler class</span></span>  
  
1.  <span data-ttu-id="c79f2-133">ソリューション エクスプ ローラーで、 **EchoAdapterInboundHandler.cs**ファイル。</span><span class="sxs-lookup"><span data-stu-id="c79f2-133">In Solution Explorer, double-click the **EchoAdapterInboundHandler.cs** file.</span></span>  
  
2.  <span data-ttu-id="c79f2-134">Visual Studio エディターでは、ディレクティブを使用する既存のセットに次の行を追加します。</span><span class="sxs-lookup"><span data-stu-id="c79f2-134">In the Visual Studio editor, add the following lines to the existing set of using directives.</span></span>  
  
    ```csharp  
    using System.IO;  
    using System.ServiceModel.Channels;  
    using System.Xml;  
    using System.Diagnostics;  
    ```  
  
3.  <span data-ttu-id="c79f2-135">今すぐ EchoAdapterInboundHandler クラスをクラス レベルの変数を追加します。</span><span class="sxs-lookup"><span data-stu-id="c79f2-135">Now add class level variables to the EchoAdapterInboundHandler class.</span></span> <span data-ttu-id="c79f2-136">これらの変数は、ファイル システム ファイルの活動で監視に使用されます。</span><span class="sxs-lookup"><span data-stu-id="c79f2-136">These variables are used to monitor the file system for file activity.</span></span> <span data-ttu-id="c79f2-137">コンス トラクターは、前に、クラス宣言の下にコピーします。</span><span class="sxs-lookup"><span data-stu-id="c79f2-137">Copy the declarations below into the class before the constructor.</span></span>  
  
    ```csharp  
    private Queue<Message> inboundQueue;  
    private FileSystemWatcher inboundWatcher;  
    private Object inboundQueueSynchronizationLock;  
    private string path;  
    private string filter;  
    ```  
  
4.  <span data-ttu-id="c79f2-138">EchoAdapterInboundHandler コンス トラクター メソッドの内部インフラストラクチャを監視するファイルを初期化するために、フィルターと監視のパスをキャプチャして、次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="c79f2-138">Inside the EchoAdapterInboundHandler constructor method, add the following code to initialize the file watching infrastructure and to capture the monitoring path and filter.</span></span>  
  
    ```csharp  
    inboundWatcher = null;  
    inboundQueueSynchronizationLock = new Object();  
    path = connection.ConnectionFactory.Adapter.InboundFileSystemWatcherFolder;  
    filter = connection.ConnectionFactory.Adapter.InboundFileFilter;  
    ```  
  
5.  <span data-ttu-id="c79f2-139">次のコードを追加、 **StartListener**メソッドです。</span><span class="sxs-lookup"><span data-stu-id="c79f2-139">Now add the following code to the **StartListener** method.</span></span> <span data-ttu-id="c79f2-140">コードでは、パラメーターを確認し、ファイルのアクティビティの監視を開始するためのロジックを実装します。</span><span class="sxs-lookup"><span data-stu-id="c79f2-140">The code implements logic to verify parameters and start monitoring for file activity.</span></span>  
  
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
  
6.  <span data-ttu-id="c79f2-141">実装を追加することにより続行、 **StopListener**メソッドです。</span><span class="sxs-lookup"><span data-stu-id="c79f2-141">Continue by adding an implementation for the **StopListener** method.</span></span>  
  
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
  
7.  <span data-ttu-id="c79f2-142">実装を提供するようになりました、 **TryReveive**メソッドです。</span><span class="sxs-lookup"><span data-stu-id="c79f2-142">Now provide an implementation for the **TryReveive** method.</span></span> <span data-ttu-id="c79f2-143">このメソッドは、最新のファイルを取得します。 1 つが利用可能な場合は、内部キューからメッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="c79f2-143">This method retrieves the most recent file receive message from the internal queue if one is available.</span></span>  
  
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
  
8.  <span data-ttu-id="c79f2-144">実装を追加することにより続行、 **WaitForMessage**メソッドです。</span><span class="sxs-lookup"><span data-stu-id="c79f2-144">Continue by adding an implementation for the **WaitForMessage** method.</span></span>  
  
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
  
9. <span data-ttu-id="c79f2-145">これで、ファイルの監視のコールバックを指定します。</span><span class="sxs-lookup"><span data-stu-id="c79f2-145">Now supply the callback for the file watcher.</span></span> <span data-ttu-id="c79f2-146">新しいメソッドを追加するには、 **FileMonitor_Created**を**EchoAdapterInboundAdapter**クラスです。</span><span class="sxs-lookup"><span data-stu-id="c79f2-146">To do so, add the new method **FileMonitor_Created** to the **EchoAdapterInboundAdapter** class.</span></span>  
  
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
  
10. <span data-ttu-id="c79f2-147">これで、削除する必要があります、 **NotImplementedException**内部によってスローされた例外**EchoAdapterInboundReply**クラスです。</span><span class="sxs-lookup"><span data-stu-id="c79f2-147">Now you must remove the **NotImplementedException** exceptions thrown by the internal **EchoAdapterInboundReply** class.</span></span> <span data-ttu-id="c79f2-148">これを行うには、次のステートメントを削除、**中止**と**返信**メソッドです。</span><span class="sxs-lookup"><span data-stu-id="c79f2-148">To do this, delete the following statement from the **Abort** and **Reply** methods.</span></span>  
  
    ```csharp  
    throw new NotImplementedException("The method or operation is not implemented.");  
    ```  
  
     <span data-ttu-id="c79f2-149">**中止**と**返信**メソッドは、次のようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c79f2-149">Your **Abort** and **Reply** methods should be similar to the following.</span></span>  
  
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
  
11. <span data-ttu-id="c79f2-150">完了するには、受信ハンドラーの実装を次のクラスを追加**EchoAdapterOutboundHandler.cs**です。</span><span class="sxs-lookup"><span data-stu-id="c79f2-150">To complete the implementation for the inbound handler, add the following class to **EchoAdapterOutboundHandler.cs**.</span></span> <span data-ttu-id="c79f2-151">このクラスは、受信ハンドラーの実装のタイムアウトのサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="c79f2-151">This class provides timeout support for the inbound handler implementation.</span></span>  
  
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
  
12. <span data-ttu-id="c79f2-152">Visual Studio での**ファイル** メニューのをクリックして**すべて保存**です。</span><span class="sxs-lookup"><span data-stu-id="c79f2-152">In Visual Studio, on the **File** menu, click **Save All**.</span></span>  
  
13. <span data-ttu-id="c79f2-153">**[ビルド]** メニューの **[ソリューションのビルド]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c79f2-153">On the **Build** menu, click **Build Solution**.</span></span> <span data-ttu-id="c79f2-154">これは、エラーなしでコンパイルする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c79f2-154">It should compile without errors.</span></span> <span data-ttu-id="c79f2-155">以外の場合は、上記のすべてのステップに従っていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c79f2-155">If not, ensure that you have followed every step above.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c79f2-156">これで作業が保存されました。</span><span class="sxs-lookup"><span data-stu-id="c79f2-156">You saved your work.</span></span> <span data-ttu-id="c79f2-157">安全にこの時点で Visual Studio を終了したり、次の手順に進みます[手順 9: ビルドし、配置エコー アダプター](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-9-build-and-deploy-the-echo-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="c79f2-157">You can safely close Visual Studio at this time or go to the next step, [Step 9: Build and Deploy the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-9-build-and-deploy-the-echo-adapter.md).</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="c79f2-158">でしただけは何ですか。</span><span class="sxs-lookup"><span data-stu-id="c79f2-158">What Did I Just Do?</span></span>  
 <span data-ttu-id="c79f2-159">エコー アダプター チュートリアルのこのステップでは、受信ハンドラーの実装を提供します。</span><span class="sxs-lookup"><span data-stu-id="c79f2-159">In this step of the Echo Adapter tutorial, you provided an implementation for the Inbound Handler.</span></span> <span data-ttu-id="c79f2-160">この実装を使用してエコー アダプターの機能を見てファイルを提供する、 **FileSystemWatcher** .NET Framework のクラスです。</span><span class="sxs-lookup"><span data-stu-id="c79f2-160">This implementation provides file watching capabilities for the Echo Adapter using the **FileSystemWatcher** class of the .NET Framework.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="c79f2-161">次の手順</span><span class="sxs-lookup"><span data-stu-id="c79f2-161">Next Steps</span></span>  
 <span data-ttu-id="c79f2-162">次の手順では、アダプターを展開します。</span><span class="sxs-lookup"><span data-stu-id="c79f2-162">In the next step, you deploy the adapter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c79f2-163">参照</span><span class="sxs-lookup"><span data-stu-id="c79f2-163">See Also</span></span>  
 <span data-ttu-id="c79f2-164">[手順 9: ビルドをエコー アダプターの展開](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-9-build-and-deploy-the-echo-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="c79f2-164">[Step 9: Build and Deploy the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-9-build-and-deploy-the-echo-adapter.md) </span></span>  
 [<span data-ttu-id="c79f2-165">手順 7: エコー アダプターの同期送信ハンドラーを実装します。</span><span class="sxs-lookup"><span data-stu-id="c79f2-165">Step 7: Implement the Synchronous Outbound Handler for the Echo Adapter</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-7-implement-the-synchronous-outbound-handler-for-the-echo-adapter.md)