---
redirect_url: /biztalk/core/troubleshooting-tibco-rendezvous/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: cce9ad685bc4b0bc8a0d97e0645573c5e2db1cf5
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25975568"
---
# <a name="using-event-tracing-for-windows"></a><span data-ttu-id="31231-101">Windows イベント トレーシングの使用</span><span class="sxs-lookup"><span data-stu-id="31231-101">Using Event Tracing for Windows</span></span>
<span data-ttu-id="31231-102">Microsoft BizTalk Adapter for TIBCO Rendezvous は、エラー、警告、および情報メッセージを Windows イベント ビューアーに記録します。</span><span class="sxs-lookup"><span data-stu-id="31231-102">Microsoft BizTalk Adapter for TIBCO Rendezvous logs error, warning, and information messages to the Windows Event Viewer.</span></span> <span data-ttu-id="31231-103">追加のトレーシング メッセージを表示するには、Windows イベント トレーシング (ETW) ツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="31231-103">You can see additional tracing messages by using the Event Tracing for Windows (ETW) tool.</span></span> <span data-ttu-id="31231-104">ETW をアクティブにすると、メッセージ受信用の \*.etl ファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="31231-104">When ETW is activated, it creates an \*.etl file to receive the messages.</span></span> <span data-ttu-id="31231-105">このファイルはバイナリ形式であり、読み取るには変換する必要があります。</span><span class="sxs-lookup"><span data-stu-id="31231-105">This file is in binary format and must be converted to be read.</span></span> <span data-ttu-id="31231-106">これを行うには、解釈に利用できるコンシューマー アプリケーションが必要、 \*.etl ファイル、tracerpt.exe や tracedmp.exe などです。</span><span class="sxs-lookup"><span data-stu-id="31231-106">To do this, you must have a consumer application available to interpret the \*.etl file, for example, tracerpt.exe or tracedmp.exe.</span></span> <span data-ttu-id="31231-107">たとえば、tracerpt.exe アプリケーションに変換されます、 \*.etl ファイルを 2 つのテキスト ファイル: summary.txt と dumpfile.csv です。</span><span class="sxs-lookup"><span data-stu-id="31231-107">For example, the tracerpt.exe application will convert the \*.etl file into two text files: summary.txt and dumpfile.csv.</span></span>  
  
## <a name="etw-components"></a><span data-ttu-id="31231-108">ETW コンポーネント</span><span class="sxs-lookup"><span data-stu-id="31231-108">ETW Components</span></span>  
 <span data-ttu-id="31231-109">Windows イベント トレーシングには 3 つのコンポーネントがあります。</span><span class="sxs-lookup"><span data-stu-id="31231-109">Event Tracing for Windows has three components:</span></span>  
  
-   <span data-ttu-id="31231-110">**コント ローラー アプリケーション**: をアクティブにし、(たとえば、tracelog.exe または logman.exe) プロバイダーが非アクティブ化します。</span><span class="sxs-lookup"><span data-stu-id="31231-110">**Controller application**: Activates and deactivates a provider (for example, tracelog.exe or logman.exe).</span></span>  
  
     <span data-ttu-id="31231-111">PATH 環境変数を、tracelog.exe の場所を指すように設定します。</span><span class="sxs-lookup"><span data-stu-id="31231-111">You set your PATH environment variable to point to the location of tracelog.exe.</span></span> <span data-ttu-id="31231-112">これにより、BTATIBCO RendezvousTrace の呼び出しが、システムの tracelog.exe を見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="31231-112">This makes sure that BTATIBCO RendezvousTrace calls can locate tracelog.exe in the system.</span></span> <span data-ttu-id="31231-113">既定では、BTATIBCO RendezvousTrace は現在のパスを検索します。</span><span class="sxs-lookup"><span data-stu-id="31231-113">By default, BTATIBCO RendezvousTrace searches the current path.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="31231-114">tracelog.exe は Microsoft SDK に含まれており、Microsoft BizTalk Adapter for TIBCO Rendezvous で提供されるコマンドと互換性があります。</span><span class="sxs-lookup"><span data-stu-id="31231-114">tracelog.exe is available from the Microsoft SDK and is compatible with the commands provided by Microsoft BizTalk Adapter for TIBCO Rendezvous.</span></span> <span data-ttu-id="31231-115">logman.exe の使い方については、logman のマニュアルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="31231-115">To use logman.exe, see the logman documentation.</span></span>  
  
-   <span data-ttu-id="31231-116">**コンシューマー アプリケーション**: 記録されたイベントの読み取り。</span><span class="sxs-lookup"><span data-stu-id="31231-116">**Consumer application**: Reads logged events.</span></span>  
  
     <span data-ttu-id="31231-117">コンシュマー アプリケーションで etl ファイルのイベントを読み取るには、Event Tracing for Windows によるダンプ処理でファイルを生成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="31231-117">For the consumer application to be able to read the event in the etl file, Event Tracing for Windows must dump them into that file.</span></span> <span data-ttu-id="31231-118">通常、この作業は、コントローラーがトレーシングを非アクティブ化するときに行われます。</span><span class="sxs-lookup"><span data-stu-id="31231-118">Typically this is done when the controller deactivates the tracing.</span></span>  
  
     <span data-ttu-id="31231-119">コント ローラーにコンシューマー アプリケーションを使用して、トレースを非アクティブ化せず、リアル タイム オプションを使用してトレースをアクティブ化する必要があります\<リアルタイム\>-rt を = です。</span><span class="sxs-lookup"><span data-stu-id="31231-119">To use the consumer application without deactivating the trace, the controller must activate the trace with the real time option, \<Real time\> = -rt.</span></span>  
  
-   <span data-ttu-id="31231-120">**プロバイダー**: イベントを提供します。</span><span class="sxs-lookup"><span data-stu-id="31231-120">**Provider**: Provides the event.</span></span>  
  
     <span data-ttu-id="31231-121">BizTalk Adapter for TIBCO Rendezvous には 3 つの異なるプロバイダーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="31231-121">BizTalk Adapter for TIBCO Rendezvous includes three different providers.</span></span> <span data-ttu-id="31231-122">これらは Windows Management Instrumentation (WMI) に登録されます。</span><span class="sxs-lookup"><span data-stu-id="31231-122">They are registered in Windows Management Instrumentation (WMI).</span></span> <span data-ttu-id="31231-123">root\WMI\EventTrace パス内で登録プロバイダーを検索するには、WMI CIM Studio などのツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="31231-123">To find the registered providers in the root\WMI\EventTrace path, you can use tools such as WMI CIM Studio.</span></span>  
  
 <span data-ttu-id="31231-124">BizTalk Adapter for TIBCO Rendezvous には 3 つのプロバイダーがあります。</span><span class="sxs-lookup"><span data-stu-id="31231-124">BizTalk Adapter for TIBCO Rendezvous has three providers.</span></span> <span data-ttu-id="31231-125">そのため、異なる種類のメッセージを記録できます。</span><span class="sxs-lookup"><span data-stu-id="31231-125">This lets you log different kinds of messages:</span></span>  
  
-   <span data-ttu-id="31231-126">**受信元ログ プロバイダー**:\<トレース要素\>スイッチが **-受信者**です。</span><span class="sxs-lookup"><span data-stu-id="31231-126">**Receiver Logging Provider**: The \<Trace element\> switch is **-receiver**.</span></span>  
  
-   <span data-ttu-id="31231-127">使用して **-受信者**を実行時にアダプターによって受信されたログからすべてのメッセージを取得します。</span><span class="sxs-lookup"><span data-stu-id="31231-127">Use **-receiver** to get any messages from the log that were received by the adapter at runtime.</span></span>  
  
-   <span data-ttu-id="31231-128">**送信元ログ プロバイダー**:\<トレース要素\>スイッチが **-トランスミッター**です。</span><span class="sxs-lookup"><span data-stu-id="31231-128">**Transmitter Logging Provider**: the \<Trace element\> switch is **-transmitter**.</span></span>  
  
     <span data-ttu-id="31231-129">使用して **-トランスミッター**を実行時にアダプターによって送信されたログからすべてのメッセージを取得します。</span><span class="sxs-lookup"><span data-stu-id="31231-129">Use **-transmitter** to get any messages from the log that were transmitted by the adapter at run time.</span></span>  
  
-   <span data-ttu-id="31231-130">**管理ログ プロバイダー —**、\<トレース要素\>スイッチが **-管理**です。</span><span class="sxs-lookup"><span data-stu-id="31231-130">**Management Logging Provider—** the \<Trace element\> switch is **-management**.</span></span>  
  
     <span data-ttu-id="31231-131">使用して **-管理**サーバー システムの参照中に生成されたログからすべてのメッセージを取得します。</span><span class="sxs-lookup"><span data-stu-id="31231-131">Use **-management**to get any messages from the log that were generated during browsing of the server system.</span></span>  
  
## <a name="btatibcorvtrace-command"></a><span data-ttu-id="31231-132">BTATIBCORVTrace コマンド</span><span class="sxs-lookup"><span data-stu-id="31231-132">BTATIBCORVTrace Command</span></span>  
 <span data-ttu-id="31231-133">ETW を使用するには、BizTalk Adapter for TIBCO Rendezvous コマンドである BTATIBCORVTrace.cmd を実行します。</span><span class="sxs-lookup"><span data-stu-id="31231-133">To use ETW, run the BizTalk Adapter for TIBCO Rendezvous command, BTATIBCORVTrace.cmd.</span></span> <span data-ttu-id="31231-134">このコマンドは次のように使用します。</span><span class="sxs-lookup"><span data-stu-id="31231-134">You use this command as follows:</span></span>  
  
```  
BTATIBCORVTrace <Trace element> -start [-cir <MB>|   
-seq <MB>] [-rt] logfile  
BTATIBCORVTrace <Trace element> -stop  
```  
  
 <span data-ttu-id="31231-135">場所: **\<トレース要素\>** プロバイダーの種類は、(必須)。</span><span class="sxs-lookup"><span data-stu-id="31231-135">Where: **\<Trace element\>** (required) is the kind of provider.</span></span>  
  
 <span data-ttu-id="31231-136">そのオプションは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="31231-136">Its options are as follows:</span></span>  
  
-   <span data-ttu-id="31231-137">**送信機能**</span><span class="sxs-lookup"><span data-stu-id="31231-137">**-transmitter**</span></span>  
  
-   <span data-ttu-id="31231-138">**-受信機**</span><span class="sxs-lookup"><span data-stu-id="31231-138">**-receiver**</span></span>  
  
-   <span data-ttu-id="31231-139">**-管理**</span><span class="sxs-lookup"><span data-stu-id="31231-139">**-management**</span></span>  
  
-   <span data-ttu-id="31231-140">**-開始、停止**: プロバイダーをアクティブまたは非アクティブです。</span><span class="sxs-lookup"><span data-stu-id="31231-140">**-start, -stop**: Activate or deactivate the provider.</span></span>  
  
-   <span data-ttu-id="31231-141">**-cir \<MB\>**: ファイルのサイズおよび種類です。</span><span class="sxs-lookup"><span data-stu-id="31231-141">**-cir \<MB\>**: Size and kind of file.</span></span> <span data-ttu-id="31231-142">**-cir**循環ファイルです。</span><span class="sxs-lookup"><span data-stu-id="31231-142">**-cir** is a circular file.</span></span> <span data-ttu-id="31231-143">**\<MB\>**: サイズ (メガバイト単位)。</span><span class="sxs-lookup"><span data-stu-id="31231-143">**\<MB\>**: Size in megabytes.</span></span>  
  
-   <span data-ttu-id="31231-144">**-seq \<MB\>**: ファイルのサイズおよび種類です。</span><span class="sxs-lookup"><span data-stu-id="31231-144">**-seq \<MB\>**: Size and kind of file.</span></span> <span data-ttu-id="31231-145">**-seq**シーケンシャル ファイルです。</span><span class="sxs-lookup"><span data-stu-id="31231-145">**-seq** is a sequential file.</span></span> <span data-ttu-id="31231-146">**\<MB\>**: サイズ (メガバイト単位)。</span><span class="sxs-lookup"><span data-stu-id="31231-146">**\<MB\>**: Size in megabytes.</span></span>  
  
-   <span data-ttu-id="31231-147">**-rt**: リアル タイム モードに設定します。</span><span class="sxs-lookup"><span data-stu-id="31231-147">**-rt**: Set the real time mode on.</span></span>  
  
-   <span data-ttu-id="31231-148">**Logfile**: ログ ファイルの名前 (既定では c:\rtlog.etl) です。</span><span class="sxs-lookup"><span data-stu-id="31231-148">**Logfile**: Name of the log file (c:\rtlog.etl is the default).</span></span>  
  
 <span data-ttu-id="31231-149">例:</span><span class="sxs-lookup"><span data-stu-id="31231-149">For example:</span></span>  
  
```  
BTATIBCORVTrace -transmitter -start -cir 10 -rt c:\log\mylog.etl  
BTATIBCORVTrace -transmitter -stop  
```  
  
## <a name="see-also"></a><span data-ttu-id="31231-150">参照</span><span class="sxs-lookup"><span data-stu-id="31231-150">See Also</span></span>  
 [<span data-ttu-id="31231-151">TIBCO Rendezvous のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="31231-151">Troubleshooting TIBCO Rendezvous</span></span>](../core/troubleshooting-tibco-rendezvous.md)