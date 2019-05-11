---
redirect_url: /biztalk/core/troubleshooting-tibco-rendezvous/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: 7f4b5dfc36e6f32401ffe04f2e72751d285ef493
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65247204"
---
# <a name="using-event-tracing-for-windows"></a><span data-ttu-id="a8d57-101">イベント トレーシング Windows の使用</span><span class="sxs-lookup"><span data-stu-id="a8d57-101">Using Event Tracing for Windows</span></span>
<span data-ttu-id="a8d57-102">Microsoft BizTalk Adapter for TIBCO Rendezvous は、エラー、警告、および情報メッセージを Windows イベント ビューアーに記録します。</span><span class="sxs-lookup"><span data-stu-id="a8d57-102">Microsoft BizTalk Adapter for TIBCO Rendezvous logs error, warning, and information messages to the Windows Event Viewer.</span></span> <span data-ttu-id="a8d57-103">Event Tracing for Windows (ETW) ツールを使用して、その他のトレース メッセージを確認できます。</span><span class="sxs-lookup"><span data-stu-id="a8d57-103">You can see additional tracing messages by using the Event Tracing for Windows (ETW) tool.</span></span> <span data-ttu-id="a8d57-104">ETW をアクティブになると、メッセージを受信する \*.etl ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="a8d57-104">When ETW is activated, it creates an \*.etl file to receive the messages.</span></span> <span data-ttu-id="a8d57-105">このファイルはバイナリ形式では、読み取るには変換する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a8d57-105">This file is in binary format and must be converted to be read.</span></span> <span data-ttu-id="a8d57-106">これを行うには、解釈に利用できるコンシューマー アプリケーションが必要、 \*.etl ファイル、tracerpt.exe や tracedmp.exe などです。</span><span class="sxs-lookup"><span data-stu-id="a8d57-106">To do this, you must have a consumer application available to interpret the \*.etl file, for example, tracerpt.exe or tracedmp.exe.</span></span> <span data-ttu-id="a8d57-107">たとえば、tracerpt.exe アプリケーションは変換、 \*.etl ファイルを 2 つのテキスト ファイル: summary.txt と dumpfile.csv です。</span><span class="sxs-lookup"><span data-stu-id="a8d57-107">For example, the tracerpt.exe application will convert the \*.etl file into two text files: summary.txt and dumpfile.csv.</span></span>  
  
## <a name="etw-components"></a><span data-ttu-id="a8d57-108">ETW コンポーネント</span><span class="sxs-lookup"><span data-stu-id="a8d57-108">ETW Components</span></span>  
 <span data-ttu-id="a8d57-109">Windows のイベントのトレースでは、次の 3 つのコンポーネントがあります。</span><span class="sxs-lookup"><span data-stu-id="a8d57-109">Event Tracing for Windows has three components:</span></span>  
  
-   <span data-ttu-id="a8d57-110">**コント ローラー アプリケーション**:アクティブにし、(たとえば、tracelog.exe または logman.exe) のプロバイダーを非アクティブ化されます。</span><span class="sxs-lookup"><span data-stu-id="a8d57-110">**Controller application**: Activates and deactivates a provider (for example, tracelog.exe or logman.exe).</span></span>  
  
     <span data-ttu-id="a8d57-111">Tracelog.exe の場所を PATH 環境変数を設定するとします。</span><span class="sxs-lookup"><span data-stu-id="a8d57-111">You set your PATH environment variable to point to the location of tracelog.exe.</span></span> <span data-ttu-id="a8d57-112">これにより、BTATIBCO RendezvousTrace の呼び出しが、システムの tracelog.exe を見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="a8d57-112">This makes sure that BTATIBCO RendezvousTrace calls can locate tracelog.exe in the system.</span></span> <span data-ttu-id="a8d57-113">既定では、BTATIBCO RendezvousTrace は現在のパスを検索します。</span><span class="sxs-lookup"><span data-stu-id="a8d57-113">By default, BTATIBCO RendezvousTrace searches the current path.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a8d57-114">tracelog.exe は Microsoft SDK と Microsoft BizTalk Adapter for TIBCO Rendezvous コマンドと互換性があります。</span><span class="sxs-lookup"><span data-stu-id="a8d57-114">tracelog.exe is available from the Microsoft SDK and is compatible with the commands provided by Microsoft BizTalk Adapter for TIBCO Rendezvous.</span></span> <span data-ttu-id="a8d57-115">Logman.exe を使用するには、logman のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a8d57-115">To use logman.exe, see the logman documentation.</span></span>  
  
- <span data-ttu-id="a8d57-116">**コンシューマー アプリケーション**:読み取りは、イベントを記録します。</span><span class="sxs-lookup"><span data-stu-id="a8d57-116">**Consumer application**: Reads logged events.</span></span>  
  
   <span data-ttu-id="a8d57-117">Etl ファイル内のイベントを読み取ることができるコンシューマー アプリケーションで Windows のイベントをトレースする必要がありますにダンプ ファイルにします。</span><span class="sxs-lookup"><span data-stu-id="a8d57-117">For the consumer application to be able to read the event in the etl file, Event Tracing for Windows must dump them into that file.</span></span> <span data-ttu-id="a8d57-118">通常、コント ローラーには、トレースが非アクティブ化時にこれを行います。</span><span class="sxs-lookup"><span data-stu-id="a8d57-118">Typically this is done when the controller deactivates the tracing.</span></span>  
  
   <span data-ttu-id="a8d57-119">コンシューマー アプリケーションを使用して、トレースを非アクティブ化せず、リアルタイム オプションでは、トレースで、コント ローラーによってアクティブ化する必要があります\<リアルタイム\>-rt を = です。</span><span class="sxs-lookup"><span data-stu-id="a8d57-119">To use the consumer application without deactivating the trace, the controller must activate the trace with the real time option, \<Real time\> = -rt.</span></span>  
  
- <span data-ttu-id="a8d57-120">**プロバイダー**:イベントを提供します。</span><span class="sxs-lookup"><span data-stu-id="a8d57-120">**Provider**: Provides the event.</span></span>  
  
   <span data-ttu-id="a8d57-121">BizTalk Adapter for TIBCO Rendezvous には、次の 3 つの異なるプロバイダーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="a8d57-121">BizTalk Adapter for TIBCO Rendezvous includes three different providers.</span></span> <span data-ttu-id="a8d57-122">Windows Management Instrumentation (WMI) に登録されています。</span><span class="sxs-lookup"><span data-stu-id="a8d57-122">They are registered in Windows Management Instrumentation (WMI).</span></span> <span data-ttu-id="a8d57-123">Root \wmi\eventtrace パスで登録されているプロバイダーを検索するには、WMI CIM Studio などのツールを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="a8d57-123">To find the registered providers in the root\WMI\EventTrace path, you can use tools such as WMI CIM Studio.</span></span>  
  
  <span data-ttu-id="a8d57-124">BizTalk Adapter for TIBCO Rendezvous は、次の 3 つのプロバイダーがあります。</span><span class="sxs-lookup"><span data-stu-id="a8d57-124">BizTalk Adapter for TIBCO Rendezvous has three providers.</span></span> <span data-ttu-id="a8d57-125">異なる種類のメッセージを記録できます。</span><span class="sxs-lookup"><span data-stu-id="a8d57-125">This lets you log different kinds of messages:</span></span>  
  
- <span data-ttu-id="a8d57-126">**受信元ロギング プロバイダー**:\<Trace 要素\>スイッチが **-受信者**します。</span><span class="sxs-lookup"><span data-stu-id="a8d57-126">**Receiver Logging Provider**: The \<Trace element\> switch is **-receiver**.</span></span>  
  
- <span data-ttu-id="a8d57-127">使用 **-受信者**実行時にアダプターで受信されたログからすべてのメッセージを取得します。</span><span class="sxs-lookup"><span data-stu-id="a8d57-127">Use **-receiver** to get any messages from the log that were received by the adapter at runtime.</span></span>  
  
- <span data-ttu-id="a8d57-128">**送信元ログ プロバイダー**: \<Trace 要素\>スイッチが **-送信機**します。</span><span class="sxs-lookup"><span data-stu-id="a8d57-128">**Transmitter Logging Provider**: the \<Trace element\> switch is **-transmitter**.</span></span>  
  
   <span data-ttu-id="a8d57-129">使用 **-送信機**実行時にアダプターによって送信されたログからすべてのメッセージを取得します。</span><span class="sxs-lookup"><span data-stu-id="a8d57-129">Use **-transmitter** to get any messages from the log that were transmitted by the adapter at run time.</span></span>  
  
- <span data-ttu-id="a8d57-130"><strong>管理ログ プロバイダー —</strong>、 \<Trace 要素\>スイッチが **-管理**します。</span><span class="sxs-lookup"><span data-stu-id="a8d57-130"><strong>Management Logging Provider—</strong>the \<Trace element\> switch is **-management**.</span></span>  
  
   <span data-ttu-id="a8d57-131">使用 **-管理**サーバー システムの参照中に生成されたログからすべてのメッセージを取得します。</span><span class="sxs-lookup"><span data-stu-id="a8d57-131">Use **-management**to get any messages from the log that were generated during browsing of the server system.</span></span>  
  
## <a name="btatibcorvtrace-command"></a><span data-ttu-id="a8d57-132">BTATIBCORVTrace コマンド</span><span class="sxs-lookup"><span data-stu-id="a8d57-132">BTATIBCORVTrace Command</span></span>  
 <span data-ttu-id="a8d57-133">ETW を使用するには、BizTalk Adapter for TIBCO Rendezvous コマンド BTATIBCORVTrace.cmd を実行します。</span><span class="sxs-lookup"><span data-stu-id="a8d57-133">To use ETW, run the BizTalk Adapter for TIBCO Rendezvous command, BTATIBCORVTrace.cmd.</span></span> <span data-ttu-id="a8d57-134">次のように、このコマンドを使用するには。</span><span class="sxs-lookup"><span data-stu-id="a8d57-134">You use this command as follows:</span></span>  
  
```  
BTATIBCORVTrace <Trace element> -start [-cir <MB>|   
-seq <MB>] [-rt] logfile  
BTATIBCORVTrace <Trace element> -stop  
```  
  
 <span data-ttu-id="a8d57-135">各要素の説明は次のとおりです。**\<Trace 要素\>** プロバイダーの種類は、(必須)。</span><span class="sxs-lookup"><span data-stu-id="a8d57-135">Where: **\<Trace element\>** (required) is the kind of provider.</span></span>  
  
 <span data-ttu-id="a8d57-136">そのオプションは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="a8d57-136">Its options are as follows:</span></span>  
  
- <span data-ttu-id="a8d57-137">**-transmitter**</span><span class="sxs-lookup"><span data-stu-id="a8d57-137">**-transmitter**</span></span>  
  
- <span data-ttu-id="a8d57-138">**-受信機**</span><span class="sxs-lookup"><span data-stu-id="a8d57-138">**-receiver**</span></span>  
  
- <span data-ttu-id="a8d57-139">**-management**</span><span class="sxs-lookup"><span data-stu-id="a8d57-139">**-management**</span></span>  
  
- <span data-ttu-id="a8d57-140">**-start, -stop**:アクティブ化またはプロバイダーを非アクティブ化します。</span><span class="sxs-lookup"><span data-stu-id="a8d57-140">**-start, -stop**: Activate or deactivate the provider.</span></span>  
  
- <span data-ttu-id="a8d57-141">**-cir \<MB\>**:サイズとファイルの種類。</span><span class="sxs-lookup"><span data-stu-id="a8d57-141">**-cir \<MB\>**: Size and kind of file.</span></span> <span data-ttu-id="a8d57-142">**-cir**は循環ファイルです。</span><span class="sxs-lookup"><span data-stu-id="a8d57-142">**-cir** is a circular file.</span></span> <span data-ttu-id="a8d57-143">**\<MB\>**:サイズ (メガバイト単位)。</span><span class="sxs-lookup"><span data-stu-id="a8d57-143">**\<MB\>**: Size in megabytes.</span></span>  
  
- <span data-ttu-id="a8d57-144">**-seq \<MB\>**:サイズとファイルの種類。</span><span class="sxs-lookup"><span data-stu-id="a8d57-144">**-seq \<MB\>**: Size and kind of file.</span></span> <span data-ttu-id="a8d57-145">**-seq**はシーケンシャル ファイルです。</span><span class="sxs-lookup"><span data-stu-id="a8d57-145">**-seq** is a sequential file.</span></span> <span data-ttu-id="a8d57-146">**\<MB\>**:サイズ (メガバイト単位)。</span><span class="sxs-lookup"><span data-stu-id="a8d57-146">**\<MB\>**: Size in megabytes.</span></span>  
  
- <span data-ttu-id="a8d57-147">**-rt**:リアルタイムに設定します。</span><span class="sxs-lookup"><span data-stu-id="a8d57-147">**-rt**: Set the real time mode on.</span></span>  
  
- <span data-ttu-id="a8d57-148">**ログ ファイル**:ログ ファイルの名前 (既定では c:\rtlog.etl) です。</span><span class="sxs-lookup"><span data-stu-id="a8d57-148">**Logfile**: Name of the log file (c:\rtlog.etl is the default).</span></span>  
  
  <span data-ttu-id="a8d57-149">例 :</span><span class="sxs-lookup"><span data-stu-id="a8d57-149">For example:</span></span>  
  
```  
BTATIBCORVTrace -transmitter -start -cir 10 -rt c:\log\mylog.etl  
BTATIBCORVTrace -transmitter -stop  
```  
  
## <a name="see-also"></a><span data-ttu-id="a8d57-150">参照</span><span class="sxs-lookup"><span data-stu-id="a8d57-150">See Also</span></span>  
 [<span data-ttu-id="a8d57-151">TIBCO Rendezvous のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="a8d57-151">Troubleshooting TIBCO Rendezvous</span></span>](../core/troubleshooting-tibco-rendezvous.md)