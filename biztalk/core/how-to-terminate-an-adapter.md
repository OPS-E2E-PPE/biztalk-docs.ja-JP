---
title: アダプターを終了する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: dfba2b61-b89f-41cd-a014-4e96daec6516
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dd2621e15803dd5f6e8f449de530e84df1bc1b9d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22255994"
---
# <a name="how-to-terminate-an-adapter"></a><span data-ttu-id="f2945-102">アダプターを終了する方法</span><span class="sxs-lookup"><span data-stu-id="f2945-102">How to Terminate an Adapter</span></span>
<span data-ttu-id="f2945-103">ここでは、アダプターの適切なシャットダウンに関するガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="f2945-103">The following topics provide guidance on the proper shutdown of an adapter.</span></span>  
  
## <a name="terminating-an-adapter"></a><span data-ttu-id="f2945-104">アダプターの終了</span><span class="sxs-lookup"><span data-stu-id="f2945-104">Terminating an Adapter</span></span>  
 <span data-ttu-id="f2945-105">メッセージング エンジンがシャット ダウンとが呼び出されて**IBTTransportControl**.**終了**各インプロセス アダプターでします。</span><span class="sxs-lookup"><span data-stu-id="f2945-105">When the Messaging Engine is shutting down it calls **IBTTransportControl**.**Terminate** on each in-process adapter.</span></span> <span data-ttu-id="f2945-106">このメソッドから制御が戻ると、BizTalk Server はアダプターを破棄します。</span><span class="sxs-lookup"><span data-stu-id="f2945-106">After this method returns BizTalk Server will destroy the adapter.</span></span> <span data-ttu-id="f2945-107">この処理は、ネイティブ アダプターの場合は直ちに発生しますが、マネージ アダプターの場合は .NET のガベージ コレクション プロセスが関係するため正確なタイミングを特定できません。</span><span class="sxs-lookup"><span data-stu-id="f2945-107">For native adapters this occurs immediately, but for managed adapters exactly when this occurs is less deterministic due to the .NET garbage-collection process.</span></span> <span data-ttu-id="f2945-108">アダプターをブロックする必要があります**Terminate**に必要なは、クリーンアップ作業が破棄する準備完了になるまでです。</span><span class="sxs-lookup"><span data-stu-id="f2945-108">The adapter should block in **Terminate** and do any necessary cleanup work until it is ready to be destroyed.</span></span>  
  
## <a name="terminating-isolated-receive-adapters"></a><span data-ttu-id="f2945-109">分離受信アダプターの終了</span><span class="sxs-lookup"><span data-stu-id="f2945-109">Terminating Isolated Receive Adapters</span></span>  
 <span data-ttu-id="f2945-110">分離受信アダプターはありません**Terminate**されません、BizTalk サービスでホストされているために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="f2945-110">Isolated receive adapters do not have **Terminate** called on them because they are not hosted in the BizTalk service.</span></span> <span data-ttu-id="f2945-111">代わりを呼び出すことによって**IBTTransportProxy**.**TerminateIsolatedReceiver**にメッセージング エンジンをシャット ダウンしようとしていることを通知します。</span><span class="sxs-lookup"><span data-stu-id="f2945-111">Instead, they should call **IBTTransportProxy**.**TerminateIsolatedReceiver** to notify the Messaging Engine that they are about to shut down.</span></span>  
  
## <a name="clean-up-com-objects-by-using-marshalreleasecomobject"></a><span data-ttu-id="f2945-112">Marshal.ReleaseComObject を使用した COM オブジェクトのクリーンアップ</span><span class="sxs-lookup"><span data-stu-id="f2945-112">Clean Up COM Objects by Using Marshal.ReleaseComObject</span></span>  
 <span data-ttu-id="f2945-113">COM オブジェクトを使用するマネージ コードを記述すると、共通言語ランタイム (CLR) により、COM オブジェクトへの参照を保持するプロキシ オブジェクトが生成されます。</span><span class="sxs-lookup"><span data-stu-id="f2945-113">When writing managed code that uses COM objects, the common language runtime (CLR) generates proxy objects that hold the references to the COM objects.</span></span> <span data-ttu-id="f2945-114">このプロキシ オブジェクトはマネージ オブジェクトであり、ガベージ コレクションの通常のルールが適用されます。</span><span class="sxs-lookup"><span data-stu-id="f2945-114">The proxy objects are managed objects and are subject to the usual rules of garbage collection.</span></span> <span data-ttu-id="f2945-115">ガベージ コレクターは .NET ランタイムが割り当てたメモリしか参照せず、COM オブジェクトを認識しないことから、1 つの問題が発生します。</span><span class="sxs-lookup"><span data-stu-id="f2945-115">A problem arises in that the garbage collector only sees memory that the .NET runtimes allocated, and is not aware of the COM object.</span></span> <span data-ttu-id="f2945-116">それは、プロキシ オブジェクトは小さいため、大きい COM オブジェクトが CLR ガベージ コレクターで認識されずにメモリ内に残される可能性があるという点です。</span><span class="sxs-lookup"><span data-stu-id="f2945-116">Because the proxy objects are small, a large COM object might be left in memory because the CLR garbage collector is not aware of it.</span></span>  
  
 <span data-ttu-id="f2945-117">この問題を避けるためには、明示的に解放基になる COM オブジェクトが終了したら、特に**IBTTransportBatch**オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="f2945-117">To avoid this problem, explicitly release underlying COM objects when you are finished with them, particularly any **IBTTransportBatch** objects.</span></span> <span data-ttu-id="f2945-118">呼び出すことによって、これを行う**マーシャ リング**.**ReleaseComObject**です。</span><span class="sxs-lookup"><span data-stu-id="f2945-118">You do this by calling **Marshal**.**ReleaseComObject**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f2945-119">**ReleaseComObject**残っている参照の数を返し、これは、値が 0 で返されるときにのみ、COM オブジェクトを解放します。</span><span class="sxs-lookup"><span data-stu-id="f2945-119">**ReleaseComObject** returns the number of remaining references and only releases the COM object when this returned value is zero.</span></span> <span data-ttu-id="f2945-120">多くの場合、 **ReleaseComObject**はオブジェクトが解放されることを確認するループで呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="f2945-120">Often **ReleaseComObject** is called in a loop to ensure that the object is released.</span></span> <span data-ttu-id="f2945-121">完了後を呼び出す必要があります**SuppressFinalize**このオブジェクトの最終処理する項目がないためです。</span><span class="sxs-lookup"><span data-stu-id="f2945-121">After that is complete, you should call **SuppressFinalize** on this object because there is nothing to finalize.</span></span> <span data-ttu-id="f2945-122">最後の手順として、このオブジェクトが間違いなく COM オブジェクトであるかどうかの確認も行います。</span><span class="sxs-lookup"><span data-stu-id="f2945-122">One last step is to check whether this really is a COM object.</span></span>  
  
 <span data-ttu-id="f2945-123">上記のプロセスのコードを次に示します。</span><span class="sxs-lookup"><span data-stu-id="f2945-123">The following code shows the process descrjbed above:</span></span>  
  
```  
if (Marshal.IsComObject (batch))  
(  
While (0 <Marshal.ReleaseComObject(batch)  
;  
GC.SuppressFinalize (batch);  
  
```  
  
 <span data-ttu-id="f2945-124">明示的に解放する、 **IBTTransportBatch**から返されたオブジェクト**GetBatch**パフォーマンスを大幅に向上を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="f2945-124">Explicitly releasing the **IBTTransportBatch** object returned from **GetBatch** can make a significant improvement to performance.</span></span>  
  
## <a name="always-use-terminate-when-closing-an-adapter"></a><span data-ttu-id="f2945-125">アダプターを閉じるときに常に Terminate を使用</span><span class="sxs-lookup"><span data-stu-id="f2945-125">Always Use Terminate When Closing an Adapter</span></span>  
 <span data-ttu-id="f2945-126">BizTalk server アダプターとして、コードを認識するようと呼ばれるインターフェイスを実装する必要があります**IBTTransportControl**です。</span><span class="sxs-lookup"><span data-stu-id="f2945-126">For BizTalk Server to recognize your code as an adapter, you must implement an interface called **IBTTransportControl**.</span></span> <span data-ttu-id="f2945-127">このインターフェイスは、BizTalk Server がアダプターとどのように通信するかを定義するもので、次のように定義されます。</span><span class="sxs-lookup"><span data-stu-id="f2945-127">This interface defines how BizTalk Server communicates with your adapter, and is defined as follows:</span></span>  
  
```  
public interface IBTTransportControl   
{  
void Initialize(IBTTransportProxy transportProxy);  
void Terminate();  
}  
```  
  
 <span data-ttu-id="f2945-128">インターフェイスには、2 つのメソッドが含まれています。**初期化**と**Terminate**です。</span><span class="sxs-lookup"><span data-stu-id="f2945-128">The interface contains two methods, **Initialize** and **Terminate**.</span></span>  
  
### <a name="initialize"></a><span data-ttu-id="f2945-129">[初期化]</span><span class="sxs-lookup"><span data-stu-id="f2945-129">Initialize</span></span>  
 <span data-ttu-id="f2945-130">BizTalk Server を呼び出す、**初期化**メソッド、アダプター アセンブリを読み込んだ後にします。</span><span class="sxs-lookup"><span data-stu-id="f2945-130">BizTalk Server calls the **Initialize** method after it loads the adapter assembly.</span></span> <span data-ttu-id="f2945-131">この呼び出しは、アダプターにトランスポート プロキシ (BizTalk Server に対する主要なハンドル) を渡すために行われます。</span><span class="sxs-lookup"><span data-stu-id="f2945-131">It does this to pass the transport proxy (the main handle to BizTalk Server) to the adapter.</span></span> <span data-ttu-id="f2945-132">実装**初期化**だけで、トランスポート プロキシをメンバー変数に格納します。</span><span class="sxs-lookup"><span data-stu-id="f2945-132">The implementation of **Initialize** simply stores the transport proxy in a member variable.</span></span>  
  
### <a name="terminate"></a><span data-ttu-id="f2945-133">終了</span><span class="sxs-lookup"><span data-stu-id="f2945-133">Terminate</span></span>  
 <span data-ttu-id="f2945-134">BizTalk Server を呼び出す、 **Terminate**サービスのシャット ダウンして、すべてのバッチの実行を終了する時間をアダプターのメソッドです。</span><span class="sxs-lookup"><span data-stu-id="f2945-134">BizTalk Server calls the **Terminate** method on service shutdown to give the adapter time to finish the execution of all batches.</span></span> <span data-ttu-id="f2945-135">これによりの実装、 **Terminate**メソッドをさらに複雑です。</span><span class="sxs-lookup"><span data-stu-id="f2945-135">This makes the implementation of the **Terminate** method much more involved.</span></span>  
  
 <span data-ttu-id="f2945-136">アダプターはから返されません、 **Terminate**がすべて保留中の作業が完了するまでの呼び出しです。</span><span class="sxs-lookup"><span data-stu-id="f2945-136">The adapter should not return from a **Terminate** call until any pending work it has is complete.</span></span> <span data-ttu-id="f2945-137">BizTalk Server から呼び出されると**Terminate**アダプターがその現在のすべてのタスクを停止し、新しいタスクを開始できませんを試行します。</span><span class="sxs-lookup"><span data-stu-id="f2945-137">When BizTalk Server calls **Terminate**, the adapter should try to stop all its current tasks and not start any new ones.</span></span>  
  
 <span data-ttu-id="f2945-138">**Terminate**が呼び出された場合は、アダプターが永続的にブロック サービスのシャット ダウンの一部として、サービス コントロール マネージャーが、プロセスを終了**Terminate**です。</span><span class="sxs-lookup"><span data-stu-id="f2945-138">Because **Terminate** is called as part of the service shutdown, the service control manager ends the process if the adapter perpetually blocks in **Terminate**.</span></span> <span data-ttu-id="f2945-139">この場合は、BizTalk Server サービスの停止時にサービス コントロール マネージャーからの警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f2945-139">In this case, you see the warning from the service control manager as it stops the BizTalk Server service.</span></span> <span data-ttu-id="f2945-140">このようにアダプターを途中で終了するのはできるだけ避けてください。</span><span class="sxs-lookup"><span data-stu-id="f2945-140">If possible, avoid terminating the adapter prematurely like this.</span></span> <span data-ttu-id="f2945-141">アダプターが終了プロセスを適切に処理せず、プロセスがシャットダウンを開始した時点でまだ実行中のスレッドがあると、シャットダウン時に BizTalk Server でアクセス違反が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="f2945-141">If the adapter does not handle the termination process appropriately, and still has threads running when the process starts to shut down, then you may occasionally see an access violation from BizTalk Server on shutdown.</span></span>  
  
 <span data-ttu-id="f2945-142">BizTalk Server のインターフェイスは非同期であるため、高負荷状況であっても多数のバッチが実行中 (したがって、多数のスレッドが実行中) の可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f2945-142">Because of the asynchronous nature of the interface to BizTalk Server, it is likely that under load there will be many batches and therefore threads still being executed.</span></span> <span data-ttu-id="f2945-143">**Terminate**アダプターが正常に実行される BizTalk Server で続行する前にすべてのバッチの終了を待機する呼び出しを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f2945-143">The **Terminate** call should be implemented to wait on the conclusion of every batch the adapter has successfully executed on BizTalk Server before proceeding.</span></span> <span data-ttu-id="f2945-144">によってバッチの終了が通知される、 **BatchComplete** BizTalk Server からのコールバック。</span><span class="sxs-lookup"><span data-stu-id="f2945-144">The conclusion of the batch is signaled by the **BatchComplete** callback from BizTalk Server.</span></span> <span data-ttu-id="f2945-145">**Terminate**呼び出しが待機する保留中の各**BatchComplete**が発生します。</span><span class="sxs-lookup"><span data-stu-id="f2945-145">The **Terminate** call should wait on every pending **BatchComplete** to happen.</span></span> <span data-ttu-id="f2945-146">ただし、バッチは正常に実行されなければなりません。</span><span class="sxs-lookup"><span data-stu-id="f2945-146">However, the execution of the batch must be successful.</span></span> <span data-ttu-id="f2945-147">呼び出しは、 **IBTTransportBatch**::**完了**しないことが必要があります。</span><span class="sxs-lookup"><span data-stu-id="f2945-147">That is, the call to **IBTTransportBatch**::**Done** must not fail.</span></span> <span data-ttu-id="f2945-148">場合への呼び出し**IBTTransportBatch**::**完了**失敗すると、バッチ コールバックはありません。</span><span class="sxs-lookup"><span data-stu-id="f2945-148">If the call to **IBTTransportBatch**::**Done** fails, there is no batch callback.</span></span>  
  
 <span data-ttu-id="f2945-149">アダプターに同期コードを追加する必要のあることを理解できれば、その実装は簡単です。</span><span class="sxs-lookup"><span data-stu-id="f2945-149">After you realize that you have to add synchronization code to your adapter, the implementation is fairly straightforward.</span></span>  
  
 <span data-ttu-id="f2945-150">備えた複合同期オブジェクトを実装するのには、簡単な方法の 1 つ**入力**と**のままにして**、ワーカー スレッドのためのメソッドと**終了**メソッド中にブロックする、スレッドは、保護対象の実行中にまだです。</span><span class="sxs-lookup"><span data-stu-id="f2945-150">One simple approach is to implement a compound synchronization object with **enter** and **leave** methods for the worker threads and a **terminate** method that blocks while a thread is still within the protected execution.</span></span> <span data-ttu-id="f2945-151">(ちなみに、ソリューションは、使い慣れた複数リーダー/単一ライター構造とよく似ていますここで、ワーカー スレッドのことができますと考えるのリーダーと**終了**メソッドをライターとして)。</span><span class="sxs-lookup"><span data-stu-id="f2945-151">(Incidentally, the solution is very similar to the familiar multiple-reader, single-writer structure where the worker threads can be thought of as readers and the **terminate** method as the writer.)</span></span>  
  
 <span data-ttu-id="f2945-152">**終了**メソッドを次に示します。</span><span class="sxs-lookup"><span data-stu-id="f2945-152">The **terminate** method is as follows:</span></span>  
  
```  
void terminate ()  
{  
this.control.Terminate();  
}  
```  
  
 <span data-ttu-id="f2945-153">各ワーカー スレッドについて、次のように記述します。</span><span class="sxs-lookup"><span data-stu-id="f2945-153">For each worker thread:</span></span>  
  
```  
If (!this.control.Enter())  
return; // we can’t enter because Terminate has been called  
try  
{  
//  create and fill batch  
batch.Done();  
}  
catch (Exception)  
{  
//  we are not expecting a callback  
This.control.Leave();  
}  
```  
  
 <span data-ttu-id="f2945-154">BizTalk Server からのコールバック</span><span class="sxs-lookup"><span data-stu-id="f2945-154">In the callback from BizTalk Server:</span></span>  
  
```  
batchComplete (…)  
{  
//  the callback from BizTalk Server  
//  process results  
this.control.Leave();  
}  
```  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="f2945-155"> に付属しているベース アダプターのサンプルには、ここで説明した同期メカニズムを示したサンプル コード ControlledTermination.cs が含まれています。</span><span class="sxs-lookup"><span data-stu-id="f2945-155"> ships with sample code ControlledTermination.cs in the Base Adapter sample, showing the synchronization mechanism described here.</span></span>