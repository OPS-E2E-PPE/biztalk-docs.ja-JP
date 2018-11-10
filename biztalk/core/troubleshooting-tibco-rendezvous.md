---
title: TIBCO Rendezvous のトラブルシューティング |Microsoft Docs
description: Troubl を Windows イベント トレーシングの使用の BizTalk Server で TIBCO Rendezvous esdhoot Microsoft BizTalk Adapter を =
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5b7bc3ab-16fa-4e91-8730-9431473b2fb4
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 30c9f80b2d5426c6a967f9fe57d923971d1fa305
ms.sourcegitcommit: 53b16fe6c1b1707ecf233dbd05f780653eb19419
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/01/2018
ms.locfileid: "50752398"
---
# <a name="troubleshoot-tibco-rendezvous"></a><span data-ttu-id="bef46-103">TIBCO Rendezvous をトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="bef46-103">Troubleshoot TIBCO Rendezvous</span></span>
  
## <a name="use-event-tracing-for-windows"></a><span data-ttu-id="bef46-104">Windows のイベント トレーシングを使用します。</span><span class="sxs-lookup"><span data-stu-id="bef46-104">Use Event Tracing for Windows</span></span>
<span data-ttu-id="bef46-105">Microsoft BizTalk Adapter for TIBCO Rendezvous は、エラー、警告、および情報メッセージを Windows イベント ビューアーに記録します。</span><span class="sxs-lookup"><span data-stu-id="bef46-105">Microsoft BizTalk Adapter for TIBCO Rendezvous logs error, warning, and information messages to the Windows Event Viewer.</span></span> <span data-ttu-id="bef46-106">追加のトレーシング メッセージを表示するには、Windows イベント トレーシング (ETW) ツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="bef46-106">You can see additional tracing messages by using the Event Tracing for Windows (ETW) tool.</span></span> <span data-ttu-id="bef46-107">ETW をアクティブになると作成、 \*.etl ファイル メッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="bef46-107">When ETW is activated, it creates an \*.etl file to receive the messages.</span></span> <span data-ttu-id="bef46-108">このファイルはバイナリ形式であり、読み取るには変換する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bef46-108">This file is in binary format and must be converted to be read.</span></span> <span data-ttu-id="bef46-109">これを行うには、解釈に利用できるコンシューマー アプリケーションが必要、 \*.etl ファイル、tracerpt.exe や tracedmp.exe などです。</span><span class="sxs-lookup"><span data-stu-id="bef46-109">To do this, you must have a consumer application available to interpret the \*.etl file, for example, tracerpt.exe or tracedmp.exe.</span></span> <span data-ttu-id="bef46-110">たとえば、tracerpt.exe アプリケーションは変換、 \*.etl ファイルを 2 つのテキスト ファイル: summary.txt と dumpfile.csv です。</span><span class="sxs-lookup"><span data-stu-id="bef46-110">For example, the tracerpt.exe application will convert the \*.etl file into two text files: summary.txt and dumpfile.csv.</span></span>  
  
## <a name="etw-components"></a><span data-ttu-id="bef46-111">ETW コンポーネント</span><span class="sxs-lookup"><span data-stu-id="bef46-111">ETW Components</span></span>  
 <span data-ttu-id="bef46-112">Windows イベント トレーシングには 3 つのコンポーネントがあります。</span><span class="sxs-lookup"><span data-stu-id="bef46-112">Event Tracing for Windows has three components:</span></span>  
  
-   <span data-ttu-id="bef46-113">**コント ローラー アプリケーション**: をアクティブにし、(たとえば、tracelog.exe または logman.exe) のプロバイダーを非アクティブにします。</span><span class="sxs-lookup"><span data-stu-id="bef46-113">**Controller application**: Activates and deactivates a provider (for example, tracelog.exe or logman.exe).</span></span>  
  
     <span data-ttu-id="bef46-114">PATH 環境変数を、tracelog.exe の場所を指すように設定します。</span><span class="sxs-lookup"><span data-stu-id="bef46-114">You set your PATH environment variable to point to the location of tracelog.exe.</span></span> <span data-ttu-id="bef46-115">これにより、BTATIBCO RendezvousTrace の呼び出しが、システムの tracelog.exe を見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="bef46-115">This makes sure that BTATIBCO RendezvousTrace calls can locate tracelog.exe in the system.</span></span> <span data-ttu-id="bef46-116">既定では、BTATIBCO RendezvousTrace は現在のパスを検索します。</span><span class="sxs-lookup"><span data-stu-id="bef46-116">By default, BTATIBCO RendezvousTrace searches the current path.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bef46-117">tracelog.exe は Microsoft SDK に含まれており、Microsoft BizTalk Adapter for TIBCO Rendezvous で提供されるコマンドと互換性があります。</span><span class="sxs-lookup"><span data-stu-id="bef46-117">tracelog.exe is available from the Microsoft SDK and is compatible with the commands provided by Microsoft BizTalk Adapter for TIBCO Rendezvous.</span></span> <span data-ttu-id="bef46-118">logman.exe の使い方については、logman のマニュアルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="bef46-118">To use logman.exe, see the logman documentation.</span></span>  
  
- <span data-ttu-id="bef46-119">**コンシューマー アプリケーション**: 記録されたイベントの読み取り。</span><span class="sxs-lookup"><span data-stu-id="bef46-119">**Consumer application**: Reads logged events.</span></span>  
  
   <span data-ttu-id="bef46-120">コンシュマー アプリケーションで etl ファイルのイベントを読み取るには、Event Tracing for Windows によるダンプ処理でファイルを生成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bef46-120">For the consumer application to be able to read the event in the etl file, Event Tracing for Windows must dump them into that file.</span></span> <span data-ttu-id="bef46-121">通常、この作業は、コントローラーがトレーシングを非アクティブ化するときに行われます。</span><span class="sxs-lookup"><span data-stu-id="bef46-121">Typically this is done when the controller deactivates the tracing.</span></span>  
  
   <span data-ttu-id="bef46-122">コンシューマー アプリケーションを使用して、トレースを非アクティブ化せず、リアルタイム オプションでは、トレースで、コント ローラーによってアクティブ化する必要があります\<リアルタイム\>-rt を = です。</span><span class="sxs-lookup"><span data-stu-id="bef46-122">To use the consumer application without deactivating the trace, the controller must activate the trace with the real time option, \<Real time\> = -rt.</span></span>  
  
- <span data-ttu-id="bef46-123">**プロバイダー**: イベントを提供します。</span><span class="sxs-lookup"><span data-stu-id="bef46-123">**Provider**: Provides the event.</span></span>  
  
   <span data-ttu-id="bef46-124">BizTalk Adapter for TIBCO Rendezvous には 3 つの異なるプロバイダーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="bef46-124">BizTalk Adapter for TIBCO Rendezvous includes three different providers.</span></span> <span data-ttu-id="bef46-125">これらは Windows Management Instrumentation (WMI) に登録されます。</span><span class="sxs-lookup"><span data-stu-id="bef46-125">They are registered in Windows Management Instrumentation (WMI).</span></span> <span data-ttu-id="bef46-126">root\WMI\EventTrace パス内で登録プロバイダーを検索するには、WMI CIM Studio などのツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="bef46-126">To find the registered providers in the root\WMI\EventTrace path, you can use tools such as WMI CIM Studio.</span></span>  
  
  <span data-ttu-id="bef46-127">BizTalk Adapter for TIBCO Rendezvous には 3 つのプロバイダーがあります。</span><span class="sxs-lookup"><span data-stu-id="bef46-127">BizTalk Adapter for TIBCO Rendezvous has three providers.</span></span> <span data-ttu-id="bef46-128">そのため、異なる種類のメッセージを記録できます。</span><span class="sxs-lookup"><span data-stu-id="bef46-128">This lets you log different kinds of messages:</span></span>  
  
- <span data-ttu-id="bef46-129">**受信側のログ記録プロバイダー**: \<Trace 要素\>スイッチが **-受信者**します。</span><span class="sxs-lookup"><span data-stu-id="bef46-129">**Receiver Logging Provider**: The \<Trace element\> switch is **-receiver**.</span></span>  
  
- <span data-ttu-id="bef46-130">使用 **-受信者**実行時にアダプターで受信されたログからすべてのメッセージを取得します。</span><span class="sxs-lookup"><span data-stu-id="bef46-130">Use **-receiver** to get any messages from the log that were received by the adapter at runtime.</span></span>  
  
- <span data-ttu-id="bef46-131">**送信元ログ プロバイダー**: \<Trace 要素\>スイッチが **-送信機**します。</span><span class="sxs-lookup"><span data-stu-id="bef46-131">**Transmitter Logging Provider**: the \<Trace element\> switch is **-transmitter**.</span></span>  
  
   <span data-ttu-id="bef46-132">使用 **-送信機**実行時にアダプターによって送信されたログからすべてのメッセージを取得します。</span><span class="sxs-lookup"><span data-stu-id="bef46-132">Use **-transmitter** to get any messages from the log that were transmitted by the adapter at run time.</span></span>  
  
- <span data-ttu-id="bef46-133"><strong>管理ログ プロバイダー —</strong>、 \<Trace 要素\>スイッチが **-管理**します。</span><span class="sxs-lookup"><span data-stu-id="bef46-133"><strong>Management Logging Provider—</strong>the \<Trace element\> switch is **-management**.</span></span>  
  
   <span data-ttu-id="bef46-134">使用 **-管理**サーバー システムの参照中に生成されたログからすべてのメッセージを取得します。</span><span class="sxs-lookup"><span data-stu-id="bef46-134">Use **-management**to get any messages from the log that were generated during browsing of the server system.</span></span>  
  
## <a name="btatibcorvtrace-command"></a><span data-ttu-id="bef46-135">BTATIBCORVTrace コマンド</span><span class="sxs-lookup"><span data-stu-id="bef46-135">BTATIBCORVTrace Command</span></span>  
 <span data-ttu-id="bef46-136">ETW を使用するには、BizTalk Adapter for TIBCO Rendezvous コマンド BTATIBCORVTrace.cmd を実行します。</span><span class="sxs-lookup"><span data-stu-id="bef46-136">To use ETW, run the BizTalk Adapter for TIBCO Rendezvous command, BTATIBCORVTrace.cmd.</span></span> <span data-ttu-id="bef46-137">このコマンドは次のように使用します。</span><span class="sxs-lookup"><span data-stu-id="bef46-137">You use this command as follows:</span></span>  
  
```  
BTATIBCORVTrace <Trace element> -start [-cir <MB>|   
-seq <MB>] [-rt] logfile  
BTATIBCORVTrace <Trace element> -stop  
```  
  
 <span data-ttu-id="bef46-138">場所:  **\<Trace 要素\>** プロバイダーの種類は、(必須)。</span><span class="sxs-lookup"><span data-stu-id="bef46-138">Where: **\<Trace element\>** (required) is the kind of provider.</span></span>  
  
 <span data-ttu-id="bef46-139">そのオプションは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="bef46-139">Its options are as follows:</span></span>  
  
- <span data-ttu-id="bef46-140">**-送信機**</span><span class="sxs-lookup"><span data-stu-id="bef46-140">**-transmitter**</span></span>  
  
- <span data-ttu-id="bef46-141">**-受信機**</span><span class="sxs-lookup"><span data-stu-id="bef46-141">**-receiver**</span></span>  
  
- <span data-ttu-id="bef46-142">**-管理**</span><span class="sxs-lookup"><span data-stu-id="bef46-142">**-management**</span></span>  
  
- <span data-ttu-id="bef46-143">**-開始、停止**: プロバイダーをアクティブまたは非アクティブです。</span><span class="sxs-lookup"><span data-stu-id="bef46-143">**-start, -stop**: Activate or deactivate the provider.</span></span>  
  
- <span data-ttu-id="bef46-144">**-cir \<MB\>**: ファイルのサイズおよび種類。</span><span class="sxs-lookup"><span data-stu-id="bef46-144">**-cir \<MB\>**: Size and kind of file.</span></span> <span data-ttu-id="bef46-145">**-cir**は循環ファイルです。</span><span class="sxs-lookup"><span data-stu-id="bef46-145">**-cir** is a circular file.</span></span> <span data-ttu-id="bef46-146">**\<MB\>**: サイズ (メガバイト単位)。</span><span class="sxs-lookup"><span data-stu-id="bef46-146">**\<MB\>**: Size in megabytes.</span></span>  
  
- <span data-ttu-id="bef46-147">**-seq \<MB\>**: ファイルのサイズおよび種類。</span><span class="sxs-lookup"><span data-stu-id="bef46-147">**-seq \<MB\>**: Size and kind of file.</span></span> <span data-ttu-id="bef46-148">**-seq**はシーケンシャル ファイルです。</span><span class="sxs-lookup"><span data-stu-id="bef46-148">**-seq** is a sequential file.</span></span> <span data-ttu-id="bef46-149">**\<MB\>**: サイズ (メガバイト単位)。</span><span class="sxs-lookup"><span data-stu-id="bef46-149">**\<MB\>**: Size in megabytes.</span></span>  
  
- <span data-ttu-id="bef46-150">**-rt**: のリアル タイム モードに設定します。</span><span class="sxs-lookup"><span data-stu-id="bef46-150">**-rt**: Set the real time mode on.</span></span>  
  
- <span data-ttu-id="bef46-151">**ログ ファイル**: ログ ファイルの名前 (既定では c:\rtlog.etl) です。</span><span class="sxs-lookup"><span data-stu-id="bef46-151">**Logfile**: Name of the log file (c:\rtlog.etl is the default).</span></span>  
  
  <span data-ttu-id="bef46-152">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="bef46-152">For example:</span></span>  
  
```  
BTATIBCORVTrace -transmitter -start -cir 10 -rt c:\log\mylog.etl  
BTATIBCORVTrace -transmitter -stop  
```  
## <a name="see-more"></a><span data-ttu-id="bef46-153">詳細情報</span><span class="sxs-lookup"><span data-stu-id="bef46-153">See more</span></span>
[<span data-ttu-id="bef46-154">例外処理</span><span class="sxs-lookup"><span data-stu-id="bef46-154">Handle exceptions</span></span>](../core/using-biztalk-server-exception-handling4.md)  
[<span data-ttu-id="bef46-155">Security</span><span class="sxs-lookup"><span data-stu-id="bef46-155">Security</span></span>](../core/security-in-biztalk-adapter-for-tibco-rendezvous.md)  
[<span data-ttu-id="bef46-156">アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="bef46-156">Architecture</span></span>](../core/architecture-of-biztalk-adapter-for-tibco-rendezvous.md)