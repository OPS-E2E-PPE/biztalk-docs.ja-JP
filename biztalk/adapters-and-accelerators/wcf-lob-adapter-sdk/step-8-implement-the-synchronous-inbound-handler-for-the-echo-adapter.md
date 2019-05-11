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
# <a name="step-8-implement-the-synchronous-inbound-handler-for-the-echo-adapter"></a><span data-ttu-id="c773e-102">手順 8:エコー アダプターの同期受信ハンドラーを実装します。</span><span class="sxs-lookup"><span data-stu-id="c773e-102">Step 8: Implement the Synchronous Inbound Handler for the Echo Adapter</span></span>
<span data-ttu-id="c773e-103">![手順 9 の 8](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-8of9.gif "Step_8of9")</span><span class="sxs-lookup"><span data-stu-id="c773e-103">![Step 8 of 9](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-8of9.gif "Step_8of9")</span></span>  
  
 <span data-ttu-id="c773e-104">**所要時間:** 45 分</span><span class="sxs-lookup"><span data-stu-id="c773e-104">**Time to complete:** 45 minutes</span></span>  
  
 <span data-ttu-id="c773e-105">この手順では、エコー アダプターの受信機能を実装します。</span><span class="sxs-lookup"><span data-stu-id="c773e-105">In this step, you implement the inbound capability of the echo adapter.</span></span> <span data-ttu-id="c773e-106">この機能により、データまたは対象システムからイベントをリッスンするアダプター。</span><span class="sxs-lookup"><span data-stu-id="c773e-106">This capability allows the adapter to listen for data or events from the target system.</span></span> <span data-ttu-id="c773e-107">に従って、 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]、のみを実装する必要があります、`Microsoft.ServiceModel.Channels.Common.IInboundHandler`アダプターが受信機能をサポートする場合にインターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="c773e-107">According to the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], you only need to implement the `Microsoft.ServiceModel.Channels.Common.IInboundHandler` interface, when your adapter supports inbound capability.</span></span> <span data-ttu-id="c773e-108">[!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)] EchoAdpterInboundHandler を要求する派生クラスが自動的に生成されます。</span><span class="sxs-lookup"><span data-stu-id="c773e-108">The [!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)] automatically generates the derived class called EchoAdpterInboundHandler for you.</span></span>  
  
 <span data-ttu-id="c773e-109">次のセクションでは、このインターフェイスを実装する方法について理解を深めるために EchoAdpterInboundHandler クラスを更新します。</span><span class="sxs-lookup"><span data-stu-id="c773e-109">In the following section, you update the EchoAdpterInboundHandler class to get a better understanding on how to implement this interface.</span></span> <span data-ttu-id="c773e-110">この手順を完了すると、エコー アダプターの受信ハンドラーを作業があります。</span><span class="sxs-lookup"><span data-stu-id="c773e-110">When you complete this step, you have a working inbound handler for the echo adapter.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="c773e-111">前提条件</span><span class="sxs-lookup"><span data-stu-id="c773e-111">Prerequisites</span></span>  
 <span data-ttu-id="c773e-112">この手順を開始する前にする必要がありますが正常に完了して[手順 7。エコー アダプターの同期送信ハンドラーを実装する](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-7-implement-the-synchronous-outbound-handler-for-the-echo-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="c773e-112">Before you begin this step, you must have successfully completed [Step 7: Implement the Synchronous Outbound Handler for the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-7-implement-the-synchronous-outbound-handler-for-the-echo-adapter.md).</span></span> <span data-ttu-id="c773e-113">基本的な知識`Microsoft.ServiceModel.Channels.Common.IInboundHandler`も便利です。</span><span class="sxs-lookup"><span data-stu-id="c773e-113">A basic familiarity with `Microsoft.ServiceModel.Channels.Common.IInboundHandler` is also helpful.</span></span>  
  
## <a name="the-iinboundhandler-interface"></a><span data-ttu-id="c773e-114">IInboundHandler インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c773e-114">The IInboundHandler Interface</span></span>  
 <span data-ttu-id="c773e-115">`Microsoft.ServiceModel.Channels.Common.IInboundHandler`として定義されます。</span><span class="sxs-lookup"><span data-stu-id="c773e-115">The `Microsoft.ServiceModel.Channels.Common.IInboundHandler` is defined as:</span></span>  
  
```  
public interface IInboundHandler : IConnectionHandler, IDisposable  
{  
          void StartListener(string[] actions, TimeSpan timeout);  
          void StopListener(TimeSpan timeout);  
          bool TryReceive(TimeSpan timeout, out Message message, out IInboundReply reply);  
          bool WaitForMessage(TimeSpan timeout);  
}  
```  
  
 <span data-ttu-id="c773e-116">メソッドの説明は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c773e-116">The method descriptions are:</span></span>  
  
|<span data-ttu-id="c773e-117">方法</span><span class="sxs-lookup"><span data-stu-id="c773e-117">Method</span></span>|<span data-ttu-id="c773e-118">説明</span><span class="sxs-lookup"><span data-stu-id="c773e-118">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="c773e-119">StartListener</span><span class="sxs-lookup"><span data-stu-id="c773e-119">StartListener</span></span>|<span data-ttu-id="c773e-120">指定された Ws-addressing アクションを含むメッセージをリッスンを開始します。</span><span class="sxs-lookup"><span data-stu-id="c773e-120">Starts listening to messages with the provided WS-Addressing Actions.</span></span> <span data-ttu-id="c773e-121">すべてをリッスンし、指定されていない場合や、既定のアクション。</span><span class="sxs-lookup"><span data-stu-id="c773e-121">If none is specified, it listens to all or the default actions.</span></span>|  
|<span data-ttu-id="c773e-122">StopListener</span><span class="sxs-lookup"><span data-stu-id="c773e-122">StopListener</span></span>|<span data-ttu-id="c773e-123">リッスンを停止します。</span><span class="sxs-lookup"><span data-stu-id="c773e-123">Stops listening.</span></span>|  
|<span data-ttu-id="c773e-124">TryReceive</span><span class="sxs-lookup"><span data-stu-id="c773e-124">TryReceive</span></span>|<span data-ttu-id="c773e-125">ターゲット システムから受信メッセージを受信しようとします。</span><span class="sxs-lookup"><span data-stu-id="c773e-125">Tries to receive an inbound message from the target system.</span></span>|  
|<span data-ttu-id="c773e-126">WaitForMessage</span><span class="sxs-lookup"><span data-stu-id="c773e-126">WaitForMessage</span></span>|<span data-ttu-id="c773e-127">ターゲット システムから受信 WCF メッセージを待ちます。</span><span class="sxs-lookup"><span data-stu-id="c773e-127">Waits for an inbound WCF message from the target system.</span></span>|  
  
 <span data-ttu-id="c773e-128">各メソッドのパラメーターの説明について詳しくは、ドキュメントを参照して、`Microsoft.ServiceModel.Channels.Common.IInboundHandler`インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="c773e-128">For more details on the description for each method parameters, see the documentation on the `Microsoft.ServiceModel.Channels.Common.IInboundHandler` interface.</span></span>  
  
## <a name="implementing-the-echoadpterinboundhandler"></a><span data-ttu-id="c773e-129">EchoAdpterInboundHandler を実装します。</span><span class="sxs-lookup"><span data-stu-id="c773e-129">Implementing the EchoAdpterInboundHandler</span></span>  
 <span data-ttu-id="c773e-130">エコー アダプターを使用して、`System.IO.FileSystemWatcher`ターゲット システムをシミュレートします。</span><span class="sxs-lookup"><span data-stu-id="c773e-130">The echo adapter uses the `System.IO.FileSystemWatcher` to simulate the target system.</span></span> <span data-ttu-id="c773e-131">内の各メソッドを実装する、次に、 `Microsoft.ServiceModel.Channels.Common.IInboundHandler` StartListener、StopListener、TryReceive、WaitForMessage インターフェイスします。</span><span class="sxs-lookup"><span data-stu-id="c773e-131">In the following, you implement each method within the `Microsoft.ServiceModel.Channels.Common.IInboundHandler` interface, StartListener, StopListener, TryReceive and WaitForMessage.</span></span>  
  
#### <a name="to-implement-iinboundhandler-interface-in-the-echoadpterinboundhandler-class"></a><span data-ttu-id="c773e-132">EchoAdpterInboundHandler クラスで IInboundHandler インターフェイスを実装するには</span><span class="sxs-lookup"><span data-stu-id="c773e-132">To implement IInboundHandler interface in the EchoAdpterInboundHandler class</span></span>  
  
1.  <span data-ttu-id="c773e-133">ソリューション エクスプ ローラーで、 **EchoAdapterInboundHandler.cs**ファイル。</span><span class="sxs-lookup"><span data-stu-id="c773e-133">In Solution Explorer, double-click the **EchoAdapterInboundHandler.cs** file.</span></span>  
  
2.  <span data-ttu-id="c773e-134">Visual Studio エディターでは、using ディレクティブの既存のセットに次の行を追加します。</span><span class="sxs-lookup"><span data-stu-id="c773e-134">In the Visual Studio editor, add the following lines to the existing set of using directives.</span></span>  
  
    ```csharp  
    using System.IO;  
    using System.ServiceModel.Channels;  
    using System.Xml;  
    using System.Diagnostics;  
    ```  
  
3.  <span data-ttu-id="c773e-135">今すぐ EchoAdapterInboundHandler クラスにクラス レベルの変数を追加します。</span><span class="sxs-lookup"><span data-stu-id="c773e-135">Now add class level variables to the EchoAdapterInboundHandler class.</span></span> <span data-ttu-id="c773e-136">これらの変数は、ファイル システム ファイルのアクティビティの監視に使用されます。</span><span class="sxs-lookup"><span data-stu-id="c773e-136">These variables are used to monitor the file system for file activity.</span></span> <span data-ttu-id="c773e-137">コンス トラクターの前に、クラス宣言の下にコピーします。</span><span class="sxs-lookup"><span data-stu-id="c773e-137">Copy the declarations below into the class before the constructor.</span></span>  
  
    ```csharp  
    private Queue<Message> inboundQueue;  
    private FileSystemWatcher inboundWatcher;  
    private Object inboundQueueSynchronizationLock;  
    private string path;  
    private string filter;  
    ```  
  
4.  <span data-ttu-id="c773e-138">EchoAdapterInboundHandler コンス トラクター メソッド内では、インフラストラクチャを監視するファイルを初期化するために、監視のパスとフィルターをキャプチャして、次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="c773e-138">Inside the EchoAdapterInboundHandler constructor method, add the following code to initialize the file watching infrastructure and to capture the monitoring path and filter.</span></span>  
  
    ```csharp  
    inboundWatcher = null;  
    inboundQueueSynchronizationLock = new Object();  
    path = connection.ConnectionFactory.Adapter.InboundFileSystemWatcherFolder;  
    filter = connection.ConnectionFactory.Adapter.InboundFileFilter;  
    ```  
  
5.  <span data-ttu-id="c773e-139">次のコードを追加、 **StartListener**メソッド。</span><span class="sxs-lookup"><span data-stu-id="c773e-139">Now add the following code to the **StartListener** method.</span></span> <span data-ttu-id="c773e-140">コードでは、パラメーターを確認し、ファイルのアクティビティの監視を開始するためのロジックを実装します。</span><span class="sxs-lookup"><span data-stu-id="c773e-140">The code implements logic to verify parameters and start monitoring for file activity.</span></span>  
  
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
  
6.  <span data-ttu-id="c773e-141">実装を追加することで引き続き、 **StopListener**メソッド。</span><span class="sxs-lookup"><span data-stu-id="c773e-141">Continue by adding an implementation for the **StopListener** method.</span></span>  
  
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
  
7.  <span data-ttu-id="c773e-142">今すぐ実装を提供、 **TryReveive**メソッド。</span><span class="sxs-lookup"><span data-stu-id="c773e-142">Now provide an implementation for the **TryReveive** method.</span></span> <span data-ttu-id="c773e-143">このメソッドは、最新のファイルを取得します。 1 つが使用可能な場合は、内部キューからメッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="c773e-143">This method retrieves the most recent file receive message from the internal queue if one is available.</span></span>  
  
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
  
8.  <span data-ttu-id="c773e-144">実装を追加することで引き続き、 **WaitForMessage**メソッド。</span><span class="sxs-lookup"><span data-stu-id="c773e-144">Continue by adding an implementation for the **WaitForMessage** method.</span></span>  
  
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
  
9. <span data-ttu-id="c773e-145">今すぐファイル ウォッチャーにコールバックを指定します。</span><span class="sxs-lookup"><span data-stu-id="c773e-145">Now supply the callback for the file watcher.</span></span> <span data-ttu-id="c773e-146">これを行うには、新しいメソッドを追加**FileMonitor_Created**を**EchoAdapterInboundAdapter**クラス。</span><span class="sxs-lookup"><span data-stu-id="c773e-146">To do so, add the new method **FileMonitor_Created** to the **EchoAdapterInboundAdapter** class.</span></span>  
  
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
  
10. <span data-ttu-id="c773e-147">削除する必要がありますので、 **NotImplementedException**内部によってスローされた例外**EchoAdapterInboundReply**クラス。</span><span class="sxs-lookup"><span data-stu-id="c773e-147">Now you must remove the **NotImplementedException** exceptions thrown by the internal **EchoAdapterInboundReply** class.</span></span> <span data-ttu-id="c773e-148">これを行うには、次のステートメントを削除、**中止**と**応答**メソッド。</span><span class="sxs-lookup"><span data-stu-id="c773e-148">To do this, delete the following statement from the **Abort** and **Reply** methods.</span></span>  
  
    ```csharp  
    throw new NotImplementedException("The method or operation is not implemented.");  
    ```  
  
     <span data-ttu-id="c773e-149">**中止**と**応答**メソッドは、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="c773e-149">Your **Abort** and **Reply** methods should be similar to the following.</span></span>  
  
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
  
11. <span data-ttu-id="c773e-150">受信ハンドラーの実装を完了するには、次のクラスを追加**EchoAdapterOutboundHandler.cs**します。</span><span class="sxs-lookup"><span data-stu-id="c773e-150">To complete the implementation for the inbound handler, add the following class to **EchoAdapterOutboundHandler.cs**.</span></span> <span data-ttu-id="c773e-151">このクラスは、受信ハンドラーの実装のタイムアウトのサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="c773e-151">This class provides timeout support for the inbound handler implementation.</span></span>  
  
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
  
12. <span data-ttu-id="c773e-152">Visual Studio での**ファイル** メニューのをクリックして**すべて保存**します。</span><span class="sxs-lookup"><span data-stu-id="c773e-152">In Visual Studio, on the **File** menu, click **Save All**.</span></span>  
  
13. <span data-ttu-id="c773e-153">**[ビルド]** メニューの **[ソリューションのビルド]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c773e-153">On the **Build** menu, click **Build Solution**.</span></span> <span data-ttu-id="c773e-154">これは、エラーなしでコンパイルする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c773e-154">It should compile without errors.</span></span> <span data-ttu-id="c773e-155">そうでない場合は、上記のすべての手順に従っていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c773e-155">If not, ensure that you have followed every step above.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c773e-156">これで作業が保存されました。</span><span class="sxs-lookup"><span data-stu-id="c773e-156">You saved your work.</span></span> <span data-ttu-id="c773e-157">安全にこの時点で Visual Studio を閉じて、次の手順に進むまたは[手順 9。ビルドおよび配置エコー アダプター](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-9-build-and-deploy-the-echo-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="c773e-157">You can safely close Visual Studio at this time or go to the next step, [Step 9: Build and Deploy the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-9-build-and-deploy-the-echo-adapter.md).</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="c773e-158">でしただけ何か。</span><span class="sxs-lookup"><span data-stu-id="c773e-158">What Did I Just Do?</span></span>  
 <span data-ttu-id="c773e-159">エコー アダプターのチュートリアルのこの手順では、受信ハンドラーの実装を提供します。</span><span class="sxs-lookup"><span data-stu-id="c773e-159">In this step of the Echo Adapter tutorial, you provided an implementation for the Inbound Handler.</span></span> <span data-ttu-id="c773e-160">この実装は、ファイルを使用してエコー アダプターの機能の監視を提供、 **FileSystemWatcher** .NET Framework のクラス。</span><span class="sxs-lookup"><span data-stu-id="c773e-160">This implementation provides file watching capabilities for the Echo Adapter using the **FileSystemWatcher** class of the .NET Framework.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="c773e-161">次の手順</span><span class="sxs-lookup"><span data-stu-id="c773e-161">Next Steps</span></span>  
 <span data-ttu-id="c773e-162">次の手順では、アダプターをデプロイします。</span><span class="sxs-lookup"><span data-stu-id="c773e-162">In the next step, you deploy the adapter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c773e-163">参照</span><span class="sxs-lookup"><span data-stu-id="c773e-163">See Also</span></span>  
 <span data-ttu-id="c773e-164">[手順 9:ビルドおよびエコー アダプターの展開](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-9-build-and-deploy-the-echo-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="c773e-164">[Step 9: Build and Deploy the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-9-build-and-deploy-the-echo-adapter.md) </span></span>  
 [<span data-ttu-id="c773e-165">手順 7:エコー アダプターの同期送信ハンドラーを実装する</span><span class="sxs-lookup"><span data-stu-id="c773e-165">Step 7: Implement the Synchronous Outbound Handler for the Echo Adapter</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-7-implement-the-synchronous-outbound-handler-for-the-echo-adapter.md)