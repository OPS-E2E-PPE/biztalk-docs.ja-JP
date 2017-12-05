---
title: "Windows 2 のイベントの追跡の使用 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ETW
- Event Tracing for Windows
ms.assetid: 88b91b74-2b2e-40e0-a3e9-1ebd6367abe8
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3c5f610d75048b250fc90aba7f723cee39c4f2e1
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="using-event-tracing-for-windows"></a><span data-ttu-id="e1cf6-102">Windows イベント トレーシングの使用</span><span class="sxs-lookup"><span data-stu-id="e1cf6-102">Using Event Tracing for Windows</span></span>
<span data-ttu-id="e1cf6-103">Microsoft BizTalk Adapter for JD Edwards OneWorld ではエラー、警告、および情報のメッセージを Windows イベント ビューアーに記録します。</span><span class="sxs-lookup"><span data-stu-id="e1cf6-103">Microsoft BizTalk Adapter for JD Edwards OneWorld logs error, warning, and information messages to the Windows Event Viewer.</span></span> <span data-ttu-id="e1cf6-104">その他のトレース メッセージを表示するには、Event Tracing for Windows (ETW) ツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="e1cf6-104">You can view additional tracing messages by using the Event Tracing for Windows (ETW) tool.</span></span> <span data-ttu-id="e1cf6-105">ETW をアクティブにすると、メッセージ受信用の *.etl ファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="e1cf6-105">When ETW is activated, it creates an *.etl file to receive the messages.</span></span> <span data-ttu-id="e1cf6-106">このファイルはバイナリ形式であり、読み取るには変換する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e1cf6-106">This file is in binary format and must be converted to be read.</span></span> <span data-ttu-id="e1cf6-107">これを行うには、解釈に利用できるコンシューマー アプリケーションが必要、 \*.etl ファイル: tracerpt.exe や tracedmp.exe などです。</span><span class="sxs-lookup"><span data-stu-id="e1cf6-107">To do this, you must have a consumer application available to interpret the \*.etl file: for example, tracerpt.exe or tracedmp.exe.</span></span>  
  
## <a name="etw-components"></a><span data-ttu-id="e1cf6-108">ETW コンポーネント</span><span class="sxs-lookup"><span data-stu-id="e1cf6-108">ETW Components</span></span>  
 <span data-ttu-id="e1cf6-109">Windows イベント トレーシングには 3 つのコンポーネントがあります。</span><span class="sxs-lookup"><span data-stu-id="e1cf6-109">Event Tracing for Windows has three components:</span></span>  
  
-   <span data-ttu-id="e1cf6-110">**コント ローラー アプリケーションです。**</span><span class="sxs-lookup"><span data-stu-id="e1cf6-110">**Controller application.**</span></span> <span data-ttu-id="e1cf6-111">プロバイダー (たとえば、tracelog.exe や logman.exe) のアクティブ化と非アクティブ化を行います。</span><span class="sxs-lookup"><span data-stu-id="e1cf6-111">Activates and deactivates a provider (for example, tracelog.exe or logman.exe).</span></span>  
  
     <span data-ttu-id="e1cf6-112">PATH 環境変数を、tracelog.exe の場所を指すように設定します。</span><span class="sxs-lookup"><span data-stu-id="e1cf6-112">You set your PATH environment variable to point to the location of tracelog.exe.</span></span> <span data-ttu-id="e1cf6-113">これにより、BTAJDEdwardsOneWorldTrace の呼び出しが、システムの tracelog.exe を見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="e1cf6-113">This ensures that BTAJDEdwardsOneWorldTrace calls can locate tracelog.exe in your system.</span></span> <span data-ttu-id="e1cf6-114">既定では、BTAJDEdwardsOneWorldTrace は現在のパスを検索します。</span><span class="sxs-lookup"><span data-stu-id="e1cf6-114">By default, BTAJDEdwardsOneWorldTrace searches the current path.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e1cf6-115">tracelog.exe は Microsoft SDK に含まれており、BizTalk Adapter for JD Edwards OneWorld で提供されるコマンドと互換性があります。</span><span class="sxs-lookup"><span data-stu-id="e1cf6-115">tracelog.exe is available from the Microsoft SDK and is compatible with the commands provided by BizTalk Adapter for JD Edwards OneWorld.</span></span> <span data-ttu-id="e1cf6-116">logman.exe を使用するには、logman のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e1cf6-116">To use logman.exe refer to the logman documentation.</span></span>  
  
-   <span data-ttu-id="e1cf6-117">**コンシューマー アプリケーションです。**</span><span class="sxs-lookup"><span data-stu-id="e1cf6-117">**Consumer application.**</span></span> <span data-ttu-id="e1cf6-118">記録されたイベントを読み取ります。</span><span class="sxs-lookup"><span data-stu-id="e1cf6-118">Reads logged events.</span></span>  
  
     <span data-ttu-id="e1cf6-119">コンシューマー アプリケーションで .etl ファイル内のイベントを読み取るには、Windows イベント トレーシングでそれらのイベントを .etl ファイルにダンプする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e1cf6-119">For the consumer application to be able to read the event in the .etl file, Event Tracing for Windows must dump them into that file.</span></span> <span data-ttu-id="e1cf6-120">通常、これはトレースが非アクティブ化されたときに実行されます。</span><span class="sxs-lookup"><span data-stu-id="e1cf6-120">Normally this is done when the controller deactivates the tracing.</span></span>  
  
     <span data-ttu-id="e1cf6-121">コント ローラーにコンシューマー アプリケーションを使用して、トレースを非アクティブ化せず、リアルタイムのオプションを使用してトレースをアクティブ化する必要があります**\<リアルタイム\>=-rt**です。</span><span class="sxs-lookup"><span data-stu-id="e1cf6-121">To use the consumer application without deactivating the trace, the controller must activate the trace with the real-time option, **\<Real time\> = -rt**.</span></span>  
  
-   <span data-ttu-id="e1cf6-122">**プロバイダー。**</span><span class="sxs-lookup"><span data-stu-id="e1cf6-122">**Provider.**</span></span> <span data-ttu-id="e1cf6-123">イベントを提供します。</span><span class="sxs-lookup"><span data-stu-id="e1cf6-123">Provides the event.</span></span>  
  
 <span data-ttu-id="e1cf6-124">BizTalk Adapter for JD Edwards OneWorld には 5 つの異なるプロバイダーがあります。</span><span class="sxs-lookup"><span data-stu-id="e1cf6-124">BizTalk Adapter for JD Edwards OneWorld includes five different providers.</span></span> <span data-ttu-id="e1cf6-125">これらは Windows Management Instrumentation (WMI) に登録されます。</span><span class="sxs-lookup"><span data-stu-id="e1cf6-125">They are registered in Windows Management Instrumentation (WMI).</span></span> <span data-ttu-id="e1cf6-126">root\WMI\EventTrace パス内で登録プロバイダーを検索するには、WMI CIM Studio などのツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="e1cf6-126">To find the registered providers in the root\WMI\EventTrace path, you can use tools such as WMI CIM Studio.</span></span>  
  
 <span data-ttu-id="e1cf6-127">BizTalk Adapter for JD Edwards OneWorld には 5 つのプロバイダーがあり、さまざまな種類のメッセージを記録できます。</span><span class="sxs-lookup"><span data-stu-id="e1cf6-127">BizTalk Adapter for JD Edwards OneWorld has five providers, allowing you to log different kinds of messages:</span></span>  
  
-   <span data-ttu-id="e1cf6-128">**受信元ログ プロバイダーです。**</span><span class="sxs-lookup"><span data-stu-id="e1cf6-128">**Receiver Logging Provider.**</span></span> <span data-ttu-id="e1cf6-129">\<トレース要素\>スイッチが**-受信者**です。</span><span class="sxs-lookup"><span data-stu-id="e1cf6-129">The \<Trace element\> switch is **-receiver**.</span></span>  
  
-   <span data-ttu-id="e1cf6-130">**受信元 CastDetails プロバイダー。**</span><span class="sxs-lookup"><span data-stu-id="e1cf6-130">**Receiver CastDetails Provider.**</span></span> <span data-ttu-id="e1cf6-131">\<トレース要素\>スイッチが**- castDetailsReceive**です。</span><span class="sxs-lookup"><span data-stu-id="e1cf6-131">The \<Trace element\> switch is **-castDetailsReceive**.</span></span>  
  
-   <span data-ttu-id="e1cf6-132">**送信元ログ プロバイダーです。**</span><span class="sxs-lookup"><span data-stu-id="e1cf6-132">**Transmitter Logging Provider.**</span></span> <span data-ttu-id="e1cf6-133">\<トレース要素\>スイッチが**-トランスミッター**です。</span><span class="sxs-lookup"><span data-stu-id="e1cf6-133">The \<Trace element\> switch is **-transmitter**.</span></span>  
  
-   <span data-ttu-id="e1cf6-134">**送信元 CastDetails プロバイダー。**</span><span class="sxs-lookup"><span data-stu-id="e1cf6-134">**Transmitter CastDetails Provider.**</span></span> <span data-ttu-id="e1cf6-135">\<トレース要素\>スイッチが**- castDetailsTransmit**です。</span><span class="sxs-lookup"><span data-stu-id="e1cf6-135">The \<Trace element\> switch is **-castDetailsTransmit**.</span></span>  
  
-   <span data-ttu-id="e1cf6-136">**管理ログ プロバイダーです。**</span><span class="sxs-lookup"><span data-stu-id="e1cf6-136">**Management Logging Provider.**</span></span> <span data-ttu-id="e1cf6-137">\<トレース要素\>スイッチが**-管理**です。</span><span class="sxs-lookup"><span data-stu-id="e1cf6-137">The \<Trace element\> switch is **-management**.</span></span>  
  
 <span data-ttu-id="e1cf6-138">BTAJDEOneWorldTrace コマンド</span><span class="sxs-lookup"><span data-stu-id="e1cf6-138">BTAJDEOneWorldTrace Command</span></span>  
  
 <span data-ttu-id="e1cf6-139">ETW を使用するには、BizTalk Adapter for JD Edwards OneWorld コマンドである BTAJDEOneWorldTrace.cmd を実行します。</span><span class="sxs-lookup"><span data-stu-id="e1cf6-139">To use ETW, run the BizTalk Adapter for JD Edwards OneWorld command, BTAJDEOneWorldTrace.cmd.</span></span> <span data-ttu-id="e1cf6-140">このコマンドは次のように使用します。</span><span class="sxs-lookup"><span data-stu-id="e1cf6-140">You use this command as follows:</span></span>  
  
```  
BTAJDEOneWorldTrace <Trace element> -start [-cir <MB>|   
      -seq <MB>] [-rt] logfile  
BTAJDEOneWorldTrace <Trace element> -stop  
```  
  
 <span data-ttu-id="e1cf6-141">各要素の説明は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e1cf6-141">Where:</span></span>  
  
-   <span data-ttu-id="e1cf6-142">**\<Trace 要素\>**プロバイダーの種類は、(必須)。</span><span class="sxs-lookup"><span data-stu-id="e1cf6-142">**\<Trace element\>** (required) is the kind of provider.</span></span>  
  
-   <span data-ttu-id="e1cf6-143">そのオプションは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e1cf6-143">Its options are:</span></span>  
  
    -   <span data-ttu-id="e1cf6-144">**-castDetailsTransmit**</span><span class="sxs-lookup"><span data-stu-id="e1cf6-144">**-castDetailsTransmit**</span></span>  
  
    -   <span data-ttu-id="e1cf6-145">**送信機能**</span><span class="sxs-lookup"><span data-stu-id="e1cf6-145">**-transmitter**</span></span>  
  
    -   <span data-ttu-id="e1cf6-146">**-castDetailsReceive**</span><span class="sxs-lookup"><span data-stu-id="e1cf6-146">**-castDetailsReceive**</span></span>  
  
    -   <span data-ttu-id="e1cf6-147">**-受信機**</span><span class="sxs-lookup"><span data-stu-id="e1cf6-147">**-receiver**</span></span>  
  
    -   <span data-ttu-id="e1cf6-148">**-管理**</span><span class="sxs-lookup"><span data-stu-id="e1cf6-148">**-management**</span></span>  
  
    -   <span data-ttu-id="e1cf6-149">**-開始、停止**: プロバイダーをアクティブまたは非アクティブです。</span><span class="sxs-lookup"><span data-stu-id="e1cf6-149">**-start, -stop**: Activate or deactivate the provider.</span></span>  
  
    -   <span data-ttu-id="e1cf6-150">**-cir \<MB\>**: ファイルのサイズおよび種類です。</span><span class="sxs-lookup"><span data-stu-id="e1cf6-150">**-cir \<MB\>**: Size and kind of file.</span></span> <span data-ttu-id="e1cf6-151">-cir は循環ファイルです。</span><span class="sxs-lookup"><span data-stu-id="e1cf6-151">-cir is a circular file.</span></span> <span data-ttu-id="e1cf6-152">\<MB\>: サイズはメガ単位です。</span><span class="sxs-lookup"><span data-stu-id="e1cf6-152">\<MB\>: Size in meg.</span></span>  
  
    -   <span data-ttu-id="e1cf6-153">**-seq \<MB\>**: ファイルのサイズおよび種類です。</span><span class="sxs-lookup"><span data-stu-id="e1cf6-153">**-seq \<MB\>**: Size and kind of file.</span></span> <span data-ttu-id="e1cf6-154">-seq はシーケンシャル ファイルです。</span><span class="sxs-lookup"><span data-stu-id="e1cf6-154">-seq is a sequential file.</span></span> <span data-ttu-id="e1cf6-155">\<MB\>: サイズはメガ単位です。</span><span class="sxs-lookup"><span data-stu-id="e1cf6-155">\<MB\>: Size in meg.</span></span>  
  
    -   <span data-ttu-id="e1cf6-156">**-rt**: リアル タイム モードに設定します。</span><span class="sxs-lookup"><span data-stu-id="e1cf6-156">**-rt**: Set the real time mode on.</span></span>  
  
    -   <span data-ttu-id="e1cf6-157">**Logfile**: ログ ファイルの名前 (既定では c:\rtlog.etl) です。</span><span class="sxs-lookup"><span data-stu-id="e1cf6-157">**Logfile**: Name of the log file (c:\rtlog.etl is the default).</span></span>  
  
 <span data-ttu-id="e1cf6-158">例:</span><span class="sxs-lookup"><span data-stu-id="e1cf6-158">For example:</span></span>  
  
```  
BTAJDEOneWorldTrace -transmitter -start -cir 10 -rt c:\log\mylog.etl  
BTAJDEOneWorldTrace -transmitter -stop  
```  
  
## <a name="see-also"></a><span data-ttu-id="e1cf6-159">参照</span><span class="sxs-lookup"><span data-stu-id="e1cf6-159">See Also</span></span>  
 [<span data-ttu-id="e1cf6-160">JD Edwards OneWorld のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="e1cf6-160">Troubleshooting JD Edwards OneWorld</span></span>](../core/troubleshooting-jd-edwards-oneworld.md)