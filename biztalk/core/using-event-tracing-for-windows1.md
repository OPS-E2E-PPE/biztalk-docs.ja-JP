---
title: "Windows1 のイベントの追跡の使用 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ETW
- provider
- Receiver Logging Provider
- Transmitter Logging Provider
- controller application
- Management Logging Provider
- consumer application
- Event Tracing for Windows
- BTATIBCORVTrace command
ms.assetid: 9e0418e2-7938-4202-83b7-555a90348904
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b51ca273e63ce93ee1ce94a66d0d14a97f807767
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="using-event-tracing-for-windows"></a><span data-ttu-id="99755-102">Windows イベント トレーシングの使用</span><span class="sxs-lookup"><span data-stu-id="99755-102">Using Event Tracing for Windows</span></span>
<span data-ttu-id="99755-103">Microsoft BizTalk Adapter for TIBCO Rendezvous は、エラー、警告、および情報メッセージを Windows イベント ビューアーに記録します。</span><span class="sxs-lookup"><span data-stu-id="99755-103">Microsoft BizTalk Adapter for TIBCO Rendezvous logs error, warning, and information messages to the Windows Event Viewer.</span></span> <span data-ttu-id="99755-104">追加のトレーシング メッセージを表示するには、Windows イベント トレーシング (ETW) ツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="99755-104">You can see additional tracing messages by using the Event Tracing for Windows (ETW) tool.</span></span> <span data-ttu-id="99755-105">ETW をアクティブにすると、メッセージ受信用の *.etl ファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="99755-105">When ETW is activated, it creates an *.etl file to receive the messages.</span></span> <span data-ttu-id="99755-106">このファイルはバイナリ形式であり、読み取るには変換する必要があります。</span><span class="sxs-lookup"><span data-stu-id="99755-106">This file is in binary format and must be converted to be read.</span></span> <span data-ttu-id="99755-107">これを行うには、解釈に利用できるコンシューマー アプリケーションが必要、 \*.etl ファイル、tracerpt.exe や tracedmp.exe などです。</span><span class="sxs-lookup"><span data-stu-id="99755-107">To do this, you must have a consumer application available to interpret the \*.etl file, for example, tracerpt.exe or tracedmp.exe.</span></span> <span data-ttu-id="99755-108">たとえば、tracerpt.exe アプリケーションに変換されます、 \*.etl ファイルを 2 つのテキスト ファイル: summary.txt と dumpfile.csv です。</span><span class="sxs-lookup"><span data-stu-id="99755-108">For example, the tracerpt.exe application will convert the \*.etl file into two text files: summary.txt and dumpfile.csv.</span></span>  
  
## <a name="etw-components"></a><span data-ttu-id="99755-109">ETW コンポーネント</span><span class="sxs-lookup"><span data-stu-id="99755-109">ETW Components</span></span>  
 <span data-ttu-id="99755-110">Windows イベント トレーシングには 3 つのコンポーネントがあります。</span><span class="sxs-lookup"><span data-stu-id="99755-110">Event Tracing for Windows has three components:</span></span>  
  
-   <span data-ttu-id="99755-111">**コント ローラー アプリケーション**: をアクティブにし、(たとえば、tracelog.exe または logman.exe) プロバイダーが非アクティブ化します。</span><span class="sxs-lookup"><span data-stu-id="99755-111">**Controller application**: Activates and deactivates a provider (for example, tracelog.exe or logman.exe).</span></span>  
  
     <span data-ttu-id="99755-112">PATH 環境変数を、tracelog.exe の場所を指すように設定します。</span><span class="sxs-lookup"><span data-stu-id="99755-112">You set your PATH environment variable to point to the location of tracelog.exe.</span></span> <span data-ttu-id="99755-113">これにより、BTATIBCO RendezvousTrace の呼び出しが、システムの tracelog.exe を見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="99755-113">This makes sure that BTATIBCO RendezvousTrace calls can locate tracelog.exe in the system.</span></span> <span data-ttu-id="99755-114">既定では、BTATIBCO RendezvousTrace は現在のパスを検索します。</span><span class="sxs-lookup"><span data-stu-id="99755-114">By default, BTATIBCO RendezvousTrace searches the current path.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="99755-115">tracelog.exe は Microsoft SDK に含まれており、Microsoft BizTalk Adapter for TIBCO Rendezvous で提供されるコマンドと互換性があります。</span><span class="sxs-lookup"><span data-stu-id="99755-115">tracelog.exe is available from the Microsoft SDK and is compatible with the commands provided by Microsoft BizTalk Adapter for TIBCO Rendezvous.</span></span> <span data-ttu-id="99755-116">logman.exe の使い方については、logman のマニュアルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="99755-116">To use logman.exe, see the logman documentation.</span></span>  
  
-   <span data-ttu-id="99755-117">**コンシューマー アプリケーション**: 記録されたイベントの読み取り。</span><span class="sxs-lookup"><span data-stu-id="99755-117">**Consumer application**: Reads logged events.</span></span>  
  
     <span data-ttu-id="99755-118">コンシュマー アプリケーションで etl ファイルのイベントを読み取るには、Event Tracing for Windows によるダンプ処理でファイルを生成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="99755-118">For the consumer application to be able to read the event in the etl file, Event Tracing for Windows must dump them into that file.</span></span> <span data-ttu-id="99755-119">通常、この作業は、コントローラーがトレーシングを非アクティブ化するときに行われます。</span><span class="sxs-lookup"><span data-stu-id="99755-119">Typically this is done when the controller deactivates the tracing.</span></span>  
  
     <span data-ttu-id="99755-120">コント ローラーにコンシューマー アプリケーションを使用して、トレースを非アクティブ化せず、リアル タイム オプションを使用してトレースをアクティブ化する必要があります\<リアルタイム > =-rt です。</span><span class="sxs-lookup"><span data-stu-id="99755-120">To use the consumer application without deactivating the trace, the controller must activate the trace with the real time option, \<Real time> = -rt.</span></span>  
  
-   <span data-ttu-id="99755-121">**プロバイダー**: イベントを提供します。</span><span class="sxs-lookup"><span data-stu-id="99755-121">**Provider**: Provides the event.</span></span>  
  
     <span data-ttu-id="99755-122">BizTalk Adapter for TIBCO Rendezvous には 3 つの異なるプロバイダーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="99755-122">BizTalk Adapter for TIBCO Rendezvous includes three different providers.</span></span> <span data-ttu-id="99755-123">これらは Windows Management Instrumentation (WMI) に登録されます。</span><span class="sxs-lookup"><span data-stu-id="99755-123">They are registered in Windows Management Instrumentation (WMI).</span></span> <span data-ttu-id="99755-124">root\WMI\EventTrace パス内で登録プロバイダーを検索するには、WMI CIM Studio などのツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="99755-124">To find the registered providers in the root\WMI\EventTrace path, you can use tools such as WMI CIM Studio.</span></span>  
  
 <span data-ttu-id="99755-125">BizTalk Adapter for TIBCO Rendezvous には 3 つのプロバイダーがあります。</span><span class="sxs-lookup"><span data-stu-id="99755-125">BizTalk Adapter for TIBCO Rendezvous has three providers.</span></span> <span data-ttu-id="99755-126">そのため、異なる種類のメッセージを記録できます。</span><span class="sxs-lookup"><span data-stu-id="99755-126">This lets you log different kinds of messages:</span></span>  
  
-   <span data-ttu-id="99755-127">**受信元ログ プロバイダー**:\<トレース要素 > スイッチは**-受信者**です。</span><span class="sxs-lookup"><span data-stu-id="99755-127">**Receiver Logging Provider**: The \<Trace element> switch is **-receiver**.</span></span>  
  
-   <span data-ttu-id="99755-128">使用して**-受信者**を実行時にアダプターによって受信されたログからすべてのメッセージを取得します。</span><span class="sxs-lookup"><span data-stu-id="99755-128">Use **-receiver** to get any messages from the log that were received by the adapter at runtime.</span></span>  
  
-   <span data-ttu-id="99755-129">**送信元ログ プロバイダー**:\<トレース要素 > スイッチは**-トランスミッター**です。</span><span class="sxs-lookup"><span data-stu-id="99755-129">**Transmitter Logging Provider**: the \<Trace element> switch is **-transmitter**.</span></span>  
  
     <span data-ttu-id="99755-130">使用して**-トランスミッター**を実行時にアダプターによって送信されたログからすべてのメッセージを取得します。</span><span class="sxs-lookup"><span data-stu-id="99755-130">Use **-transmitter** to get any messages from the log that were transmitted by the adapter at run time.</span></span>  
  
-   <span data-ttu-id="99755-131">**管理ログ プロバイダー —**、\<トレース要素 > スイッチは**-管理**です。</span><span class="sxs-lookup"><span data-stu-id="99755-131">**Management Logging Provider—**the \<Trace element> switch is **-management**.</span></span>  
  
     <span data-ttu-id="99755-132">使用して**-管理**サーバー システムの参照中に生成されたログからすべてのメッセージを取得します。</span><span class="sxs-lookup"><span data-stu-id="99755-132">Use **-management**to get any messages from the log that were generated during browsing of the server system.</span></span>  
  
## <a name="btatibcorvtrace-command"></a><span data-ttu-id="99755-133">BTATIBCORVTrace コマンド</span><span class="sxs-lookup"><span data-stu-id="99755-133">BTATIBCORVTrace Command</span></span>  
 <span data-ttu-id="99755-134">ETW を使用するには、BizTalk Adapter for TIBCO Rendezvous コマンドである BTATIBCORVTrace.cmd を実行します。</span><span class="sxs-lookup"><span data-stu-id="99755-134">To use ETW, run the BizTalk Adapter for TIBCO Rendezvous command, BTATIBCORVTrace.cmd.</span></span> <span data-ttu-id="99755-135">このコマンドは次のように使用します。</span><span class="sxs-lookup"><span data-stu-id="99755-135">You use this command as follows:</span></span>  
  
```  
BTATIBCORVTrace <Trace element> -start [-cir <MB>|   
-seq <MB>] [-rt] logfile  
BTATIBCORVTrace <Trace element> -stop  
```  
  
 <span data-ttu-id="99755-136">場所: **\<トレース要素 >**プロバイダーの種類は、(必須)。</span><span class="sxs-lookup"><span data-stu-id="99755-136">Where: **\<Trace element>** (required) is the kind of provider.</span></span>  
  
 <span data-ttu-id="99755-137">そのオプションは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="99755-137">Its options are as follows:</span></span>  
  
-   <span data-ttu-id="99755-138">**送信機能**</span><span class="sxs-lookup"><span data-stu-id="99755-138">**-transmitter**</span></span>  
  
-   <span data-ttu-id="99755-139">**-受信機**</span><span class="sxs-lookup"><span data-stu-id="99755-139">**-receiver**</span></span>  
  
-   <span data-ttu-id="99755-140">**-管理**</span><span class="sxs-lookup"><span data-stu-id="99755-140">**-management**</span></span>  
  
-   <span data-ttu-id="99755-141">**-開始、停止**: プロバイダーをアクティブまたは非アクティブです。</span><span class="sxs-lookup"><span data-stu-id="99755-141">**-start, -stop**: Activate or deactivate the provider.</span></span>  
  
-   <span data-ttu-id="99755-142">**-cir \<MB >**: ファイルのサイズおよび種類です。</span><span class="sxs-lookup"><span data-stu-id="99755-142">**-cir \<MB>**: Size and kind of file.</span></span> <span data-ttu-id="99755-143">**-cir**循環ファイルです。</span><span class="sxs-lookup"><span data-stu-id="99755-143">**-cir** is a circular file.</span></span> <span data-ttu-id="99755-144">**\<MB >**: サイズ (メガバイト単位)。</span><span class="sxs-lookup"><span data-stu-id="99755-144">**\<MB>**: Size in megabytes.</span></span>  
  
-   <span data-ttu-id="99755-145">**-seq \<MB >**: ファイルのサイズおよび種類です。</span><span class="sxs-lookup"><span data-stu-id="99755-145">**-seq \<MB>**: Size and kind of file.</span></span> <span data-ttu-id="99755-146">**-seq**シーケンシャル ファイルです。</span><span class="sxs-lookup"><span data-stu-id="99755-146">**-seq** is a sequential file.</span></span> <span data-ttu-id="99755-147">**\<MB >**: サイズ (メガバイト単位)。</span><span class="sxs-lookup"><span data-stu-id="99755-147">**\<MB>**: Size in megabytes.</span></span>  
  
-   <span data-ttu-id="99755-148">**-rt**: リアル タイム モードに設定します。</span><span class="sxs-lookup"><span data-stu-id="99755-148">**-rt**: Set the real time mode on.</span></span>  
  
-   <span data-ttu-id="99755-149">**Logfile**: ログ ファイルの名前 (既定では c:\rtlog.etl) です。</span><span class="sxs-lookup"><span data-stu-id="99755-149">**Logfile**: Name of the log file (c:\rtlog.etl is the default).</span></span>  
  
 <span data-ttu-id="99755-150">例:</span><span class="sxs-lookup"><span data-stu-id="99755-150">For example:</span></span>  
  
```  
BTATIBCORVTrace -transmitter -start -cir 10 -rt c:\log\mylog.etl  
BTATIBCORVTrace -transmitter -stop  
```  
  
## <a name="see-also"></a><span data-ttu-id="99755-151">参照</span><span class="sxs-lookup"><span data-stu-id="99755-151">See Also</span></span>  
 [<span data-ttu-id="99755-152">TIBCO Rendezvous のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="99755-152">Troubleshooting TIBCO Rendezvous</span></span>](../core/troubleshooting-tibco-rendezvous.md)