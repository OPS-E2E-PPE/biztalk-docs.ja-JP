---
title: アダプターを終了する方法 |Microsoft Docs
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
ms.openlocfilehash: ce8e6fcf862ba52c1ae742ff48ff985ef801c0b3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65383760"
---
# <a name="how-to-terminate-an-adapter"></a><span data-ttu-id="0b482-102">アダプターを終了する方法</span><span class="sxs-lookup"><span data-stu-id="0b482-102">How to Terminate an Adapter</span></span>
<span data-ttu-id="0b482-103">次のトピックでは、アダプターの適切なシャット ダウン時にガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="0b482-103">The following topics provide guidance on the proper shutdown of an adapter.</span></span>  
  
## <a name="terminating-an-adapter"></a><span data-ttu-id="0b482-104">アダプターの終了</span><span class="sxs-lookup"><span data-stu-id="0b482-104">Terminating an Adapter</span></span>  
 <span data-ttu-id="0b482-105">メッセージング エンジンがシャット ダウン時に呼び出す**IBTTransportControl**.**終了**各インプロセス アダプター。</span><span class="sxs-lookup"><span data-stu-id="0b482-105">When the Messaging Engine is shutting down it calls **IBTTransportControl**.**Terminate** on each in-process adapter.</span></span> <span data-ttu-id="0b482-106">このメソッドが返された後に、BizTalk Server は、アダプターを破棄します。</span><span class="sxs-lookup"><span data-stu-id="0b482-106">After this method returns BizTalk Server will destroy the adapter.</span></span> <span data-ttu-id="0b482-107">ネイティブ アダプターが、すぐに、マネージ アダプターをまったく発生この場合は、.NET ガベージ コレクション プロセス関係するためです。</span><span class="sxs-lookup"><span data-stu-id="0b482-107">For native adapters this occurs immediately, but for managed adapters exactly when this occurs is less deterministic due to the .NET garbage-collection process.</span></span> <span data-ttu-id="0b482-108">アダプターをブロックする必要があります**Terminate**に必要な操作を破棄する準備ができるまで、クリーンアップ作業します。</span><span class="sxs-lookup"><span data-stu-id="0b482-108">The adapter should block in **Terminate** and do any necessary cleanup work until it is ready to be destroyed.</span></span>  
  
## <a name="terminating-isolated-receive-adapters"></a><span data-ttu-id="0b482-109">受信アダプターの分離を終了しています</span><span class="sxs-lookup"><span data-stu-id="0b482-109">Terminating Isolated Receive Adapters</span></span>  
 <span data-ttu-id="0b482-110">分離受信アダプターはありません**Terminate**での BizTalk サービスがホストされていないために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="0b482-110">Isolated receive adapters do not have **Terminate** called on them because they are not hosted in the BizTalk service.</span></span> <span data-ttu-id="0b482-111">代わりに、呼び出す必要がある**IBTTransportProxy**.**TerminateIsolatedReceiver**シャット ダウンしようとしていることをメッセージング エンジンに通知します。</span><span class="sxs-lookup"><span data-stu-id="0b482-111">Instead, they should call **IBTTransportProxy**.**TerminateIsolatedReceiver** to notify the Messaging Engine that they are about to shut down.</span></span>  
  
## <a name="clean-up-com-objects-by-using-marshalreleasecomobject"></a><span data-ttu-id="0b482-112">Marshal.ReleaseComObject を使用した COM オブジェクトをクリーンアップします。</span><span class="sxs-lookup"><span data-stu-id="0b482-112">Clean Up COM Objects by Using Marshal.ReleaseComObject</span></span>  
 <span data-ttu-id="0b482-113">COM オブジェクトを使用するマネージ コードを記述する場合、共通言語ランタイム (CLR) は、COM オブジェクトへの参照を保持するプロキシ オブジェクトを生成します。</span><span class="sxs-lookup"><span data-stu-id="0b482-113">When writing managed code that uses COM objects, the common language runtime (CLR) generates proxy objects that hold the references to the COM objects.</span></span> <span data-ttu-id="0b482-114">プロキシ オブジェクトは管理対象のオブジェクトであるため、ガベージ コレクションの通常の規則が適用されます。</span><span class="sxs-lookup"><span data-stu-id="0b482-114">The proxy objects are managed objects and are subject to the usual rules of garbage collection.</span></span> <span data-ttu-id="0b482-115">ガベージ コレクターでは、.NET ランタイムで、割り当て、および、COM オブジェクトを認識しないことのメモリしか参照せずに、問題が発生します。</span><span class="sxs-lookup"><span data-stu-id="0b482-115">A problem arises in that the garbage collector only sees memory that the .NET runtimes allocated, and is not aware of the COM object.</span></span> <span data-ttu-id="0b482-116">プロキシ オブジェクトは、小さいために、CLR のガベージ コレクターは、認識しないため、大きい COM オブジェクトはメモリに残り可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0b482-116">Because the proxy objects are small, a large COM object might be left in memory because the CLR garbage collector is not aware of it.</span></span>  
  
 <span data-ttu-id="0b482-117">この問題を避けるためを明示的に解放基になる COM オブジェクトを終了すると、特に**IBTTransportBatch**オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="0b482-117">To avoid this problem, explicitly release underlying COM objects when you are finished with them, particularly any **IBTTransportBatch** objects.</span></span> <span data-ttu-id="0b482-118">呼び出すことによって、これを行う**マーシャ リング**.**ReleaseComObject**します。</span><span class="sxs-lookup"><span data-stu-id="0b482-118">You do this by calling **Marshal**.**ReleaseComObject**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0b482-119">**ReleaseComObject**残っている参照の数を返し、この戻り値が 0 の場合にのみ、COM オブジェクトを解放します。</span><span class="sxs-lookup"><span data-stu-id="0b482-119">**ReleaseComObject** returns the number of remaining references and only releases the COM object when this returned value is zero.</span></span> <span data-ttu-id="0b482-120">多くの場合、 **ReleaseComObject**は、オブジェクトが解放されることを確認するループで呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="0b482-120">Often **ReleaseComObject** is called in a loop to ensure that the object is released.</span></span> <span data-ttu-id="0b482-121">完了後を呼び出す必要があります**SuppressFinalize**このオブジェクトの最終処理を何もないためです。</span><span class="sxs-lookup"><span data-stu-id="0b482-121">After that is complete, you should call **SuppressFinalize** on this object because there is nothing to finalize.</span></span> <span data-ttu-id="0b482-122">最後の 1 つの手順では、実際に COM オブジェクトであるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="0b482-122">One last step is to check whether this really is a COM object.</span></span>  
  
 <span data-ttu-id="0b482-123">次のコードは、上記のプロセスを示しています。</span><span class="sxs-lookup"><span data-stu-id="0b482-123">The following code shows the process descrjbed above:</span></span>  
  
```  
if (Marshal.IsComObject (batch))  
(  
While (0 <Marshal.ReleaseComObject(batch)  
;  
GC.SuppressFinalize (batch);  
  
```  
  
 <span data-ttu-id="0b482-124">明示的に解放する、 **IBTTransportBatch**から返されるオブジェクト**GetBatch**パフォーマンスを大幅に改善を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="0b482-124">Explicitly releasing the **IBTTransportBatch** object returned from **GetBatch** can make a significant improvement to performance.</span></span>  
  
## <a name="always-use-terminate-when-closing-an-adapter"></a><span data-ttu-id="0b482-125">アダプターを閉じるとき、常に使用が終了します。</span><span class="sxs-lookup"><span data-stu-id="0b482-125">Always Use Terminate When Closing an Adapter</span></span>  
 <span data-ttu-id="0b482-126">BizTalk server のアダプターとして、コードを認識する、というインターフェイスを実装する必要があります**IBTTransportControl**します。</span><span class="sxs-lookup"><span data-stu-id="0b482-126">For BizTalk Server to recognize your code as an adapter, you must implement an interface called **IBTTransportControl**.</span></span> <span data-ttu-id="0b482-127">このインターフェイスは、BizTalk Server のアダプターと通信して次のように定義されているを定義します。</span><span class="sxs-lookup"><span data-stu-id="0b482-127">This interface defines how BizTalk Server communicates with your adapter, and is defined as follows:</span></span>  
  
```  
public interface IBTTransportControl   
{  
void Initialize(IBTTransportProxy transportProxy);  
void Terminate();  
}  
```  
  
 <span data-ttu-id="0b482-128">インターフェイスには、2 つのメソッドが含まれています。**初期化**と**Terminate**します。</span><span class="sxs-lookup"><span data-stu-id="0b482-128">The interface contains two methods, **Initialize** and **Terminate**.</span></span>  
  
### <a name="initialize"></a><span data-ttu-id="0b482-129">[初期化]</span><span class="sxs-lookup"><span data-stu-id="0b482-129">Initialize</span></span>  
 <span data-ttu-id="0b482-130">BizTalk Server によって、**初期化**後に、アダプター アセンブリを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="0b482-130">BizTalk Server calls the **Initialize** method after it loads the adapter assembly.</span></span> <span data-ttu-id="0b482-131">これは、アダプターにトランスポート プロキシ (BizTalk Server にメインのハンドル) を渡す。</span><span class="sxs-lookup"><span data-stu-id="0b482-131">It does this to pass the transport proxy (the main handle to BizTalk Server) to the adapter.</span></span> <span data-ttu-id="0b482-132">実装**初期化**単に、トランスポート プロキシをメンバー変数に格納します。</span><span class="sxs-lookup"><span data-stu-id="0b482-132">The implementation of **Initialize** simply stores the transport proxy in a member variable.</span></span>  
  
### <a name="terminate"></a><span data-ttu-id="0b482-133">終了</span><span class="sxs-lookup"><span data-stu-id="0b482-133">Terminate</span></span>  
 <span data-ttu-id="0b482-134">BizTalk Server によって、 **Terminate**メソッドのすべてのバッチの実行を終了する時間をアダプターを提供するサービスのシャット ダウンします。</span><span class="sxs-lookup"><span data-stu-id="0b482-134">BizTalk Server calls the **Terminate** method on service shutdown to give the adapter time to finish the execution of all batches.</span></span> <span data-ttu-id="0b482-135">これにより、実装、 **Terminate**メソッドをさらに複雑にします。</span><span class="sxs-lookup"><span data-stu-id="0b482-135">This makes the implementation of the **Terminate** method much more involved.</span></span>  
  
 <span data-ttu-id="0b482-136">アダプターから返しません、 **Terminate**が任意の保留中の作業が完了するまでの呼び出し。</span><span class="sxs-lookup"><span data-stu-id="0b482-136">The adapter should not return from a **Terminate** call until any pending work it has is complete.</span></span> <span data-ttu-id="0b482-137">BizTalk Server を呼び出すと**Terminate**の現在のすべてのタスクを停止し、新規を起動しないように、アダプターしてください。</span><span class="sxs-lookup"><span data-stu-id="0b482-137">When BizTalk Server calls **Terminate**, the adapter should try to stop all its current tasks and not start any new ones.</span></span>  
  
 <span data-ttu-id="0b482-138">**Terminate**と呼びますアダプターが永続的にブロック場合、サービスのシャット ダウンの一環として、サービス コントロール マネージャーがプロセスを終了**Terminate**します。</span><span class="sxs-lookup"><span data-stu-id="0b482-138">Because **Terminate** is called as part of the service shutdown, the service control manager ends the process if the adapter perpetually blocks in **Terminate**.</span></span> <span data-ttu-id="0b482-139">ここでは、BizTalk Server サービスの停止時にサービス コントロール マネージャーから警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0b482-139">In this case, you see the warning from the service control manager as it stops the BizTalk Server service.</span></span> <span data-ttu-id="0b482-140">可能であれば、このような処理の途中でアダプターを終了しないでください。</span><span class="sxs-lookup"><span data-stu-id="0b482-140">If possible, avoid terminating the adapter prematurely like this.</span></span> <span data-ttu-id="0b482-141">場合は、アダプターは、終了プロセスが適切に処理しないと、プロセスがシャット ダウンを開始すると実行中のスレッドがまだ、シャット ダウン時に BizTalk Server からアクセス違反随時表示があります。</span><span class="sxs-lookup"><span data-stu-id="0b482-141">If the adapter does not handle the termination process appropriately, and still has threads running when the process starts to shut down, then you may occasionally see an access violation from BizTalk Server on shutdown.</span></span>  
  
 <span data-ttu-id="0b482-142">BizTalk Server へのインターフェイスの非同期性質上、負荷がある多くのバッチしたがってスレッドが実行中に高くなります。</span><span class="sxs-lookup"><span data-stu-id="0b482-142">Because of the asynchronous nature of the interface to BizTalk Server, it is likely that under load there will be many batches and therefore threads still being executed.</span></span> <span data-ttu-id="0b482-143">**Terminate**続行する前に、アダプターが正常に実行 BizTalk Server のすべてのバッチの終了を待機する呼び出しを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0b482-143">The **Terminate** call should be implemented to wait on the conclusion of every batch the adapter has successfully executed on BizTalk Server before proceeding.</span></span> <span data-ttu-id="0b482-144">バッチの終了がによって通知、 **BatchComplete** BizTalk Server からのコールバック。</span><span class="sxs-lookup"><span data-stu-id="0b482-144">The conclusion of the batch is signaled by the **BatchComplete** callback from BizTalk Server.</span></span> <span data-ttu-id="0b482-145">**Terminate**で呼び出しを待機する必要があります保留中の各**BatchComplete**発生します。</span><span class="sxs-lookup"><span data-stu-id="0b482-145">The **Terminate** call should wait on every pending **BatchComplete** to happen.</span></span> <span data-ttu-id="0b482-146">ただし、バッチの実行は成功である必要があります。</span><span class="sxs-lookup"><span data-stu-id="0b482-146">However, the execution of the batch must be successful.</span></span> <span data-ttu-id="0b482-147">呼び出しは、 **IBTTransportBatch**::**完了**失敗する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0b482-147">That is, the call to **IBTTransportBatch**::**Done** must not fail.</span></span> <span data-ttu-id="0b482-148">場合に呼び出し**IBTTransportBatch**::**完了**失敗すると、バッチ コールバックはありません。</span><span class="sxs-lookup"><span data-stu-id="0b482-148">If the call to **IBTTransportBatch**::**Done** fails, there is no batch callback.</span></span>  
  
 <span data-ttu-id="0b482-149">アダプターに同期コードを追加する必要があることを理解できれば、実装は非常に簡単です。</span><span class="sxs-lookup"><span data-stu-id="0b482-149">After you realize that you have to add synchronization code to your adapter, the implementation is fairly straightforward.</span></span>  
  
 <span data-ttu-id="0b482-150">備えた複合同期オブジェクトを実装する 1 つの簡単な方法は、**入力**と**のままに**ワーカー スレッドのメソッドと**終了**メソッド中にブロックする、スレッドとは、保護された実行内であります。</span><span class="sxs-lookup"><span data-stu-id="0b482-150">One simple approach is to implement a compound synchronization object with **enter** and **leave** methods for the worker threads and a **terminate** method that blocks while a thread is still within the protected execution.</span></span> <span data-ttu-id="0b482-151">(ちなみに、ソリューションは、使い慣れた複数リーダー、単一のライターの構造とよく似ています、ワーカー スレッド見なすことができますのリーダーとして、**終了**メソッドをライターとします)。</span><span class="sxs-lookup"><span data-stu-id="0b482-151">(Incidentally, the solution is very similar to the familiar multiple-reader, single-writer structure where the worker threads can be thought of as readers and the **terminate** method as the writer.)</span></span>  
  
 <span data-ttu-id="0b482-152">**終了**メソッドを次に示します。</span><span class="sxs-lookup"><span data-stu-id="0b482-152">The **terminate** method is as follows:</span></span>  
  
```  
void terminate ()  
{  
this.control.Terminate();  
}  
```  
  
 <span data-ttu-id="0b482-153">各ワーカー スレッド。</span><span class="sxs-lookup"><span data-stu-id="0b482-153">For each worker thread:</span></span>  
  
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
  
 <span data-ttu-id="0b482-154">BizTalk Server からのコールバック。</span><span class="sxs-lookup"><span data-stu-id="0b482-154">In the callback from BizTalk Server:</span></span>  
  
```  
batchComplete (…)  
{  
//  the callback from BizTalk Server  
//  process results  
this.control.Leave();  
}  
```  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="0b482-155">ベース アダプター サンプルでは、ここで説明した同期メカニズムを示すサンプル コード ControlledTermination.cs が付属しています。</span><span class="sxs-lookup"><span data-stu-id="0b482-155">ships with sample code ControlledTermination.cs in the Base Adapter sample, showing the synchronization mechanism described here.</span></span>