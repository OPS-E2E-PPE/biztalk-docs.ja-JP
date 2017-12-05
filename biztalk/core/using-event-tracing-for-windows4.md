---
title: "Windows4 のイベントの追跡の使用 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ETW
- BTAJDEEnterpriseOneTrace command
- Event Tracing for Windows
ms.assetid: 5f07d317-5ae2-4d1e-a343-941f3079dc4b
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e98340654df792b8ec58014d4804394b5a6c6099
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="using-event-tracing-for-windows"></a><span data-ttu-id="56064-102">Windows イベント トレーシングの使用</span><span class="sxs-lookup"><span data-stu-id="56064-102">Using Event Tracing for Windows</span></span>
<span data-ttu-id="56064-103">Microsoft BizTalk Adapter for JD Edwards EnterpriseOne は、エラー、警告、および情報メッセージを Windows イベント ビューアーに記録します。</span><span class="sxs-lookup"><span data-stu-id="56064-103">Microsoft BizTalk Adapter for JD Edwards EnterpriseOne logs error, warning, and information messages to the Windows Event Viewer.</span></span> <span data-ttu-id="56064-104">その他のトレース メッセージを表示するには、Event Tracing for Windows (ETW) ツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="56064-104">You can view additional tracing messages by using the Event Tracing for Windows (ETW) tool.</span></span> <span data-ttu-id="56064-105">ETW をアクティブにすると、メッセージ受信用の *.etl ファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="56064-105">When ETW is activated, it creates an *.etl file to receive the messages.</span></span> <span data-ttu-id="56064-106">このファイルはバイナリ形式であり、読み取るには変換する必要があります。</span><span class="sxs-lookup"><span data-stu-id="56064-106">This file is in binary format and must be converted to be read.</span></span> <span data-ttu-id="56064-107">これを行うには、解釈に利用できるコンシューマー アプリケーションが必要、 \*.etl ファイルです。 たとえば、tracerpt.exe や tracedmp.ex です。</span><span class="sxs-lookup"><span data-stu-id="56064-107">To do this, you must have a consumer application available to interpret the \*.etl file; for example, tracerpt.exe or tracedmp.ex.</span></span> <span data-ttu-id="56064-108">Tracept.exe アプリケーションに変換、\*を 2 つのテキスト ファイルに .etl: summary.txt と dumpfile.csv です。</span><span class="sxs-lookup"><span data-stu-id="56064-108">The tracept.exe application converts the \*.etl into two text files: summary.txt and dumpfile.csv.</span></span>  
  
## <a name="etw-components"></a><span data-ttu-id="56064-109">ETW コンポーネント</span><span class="sxs-lookup"><span data-stu-id="56064-109">ETW Components</span></span>  
 <span data-ttu-id="56064-110">Windows イベント トレーシングには 3 つのコンポーネントがあります。</span><span class="sxs-lookup"><span data-stu-id="56064-110">Event Tracing for Windows has three components:</span></span>  
  
-   <span data-ttu-id="56064-111">**コント ローラー アプリケーション**です。</span><span class="sxs-lookup"><span data-stu-id="56064-111">**Controller application**.</span></span> <span data-ttu-id="56064-112">プロバイダー (たとえば、tracelog.exe や logman.exe) のアクティブ化と非アクティブ化を行います。</span><span class="sxs-lookup"><span data-stu-id="56064-112">Activates and deactivates a provider (for example, tracelog.exe or logman.exe).</span></span>  
  
     <span data-ttu-id="56064-113">PATH 環境変数を、tracelog.exe の場所を指すように設定します。</span><span class="sxs-lookup"><span data-stu-id="56064-113">You set your PATH environment variable to point to the location of tracelog.exe.</span></span> <span data-ttu-id="56064-114">これにより、BTAJDEEnterpriseOneTrace の呼び出しが、システムの tracelog.exe を見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="56064-114">This ensures that BTAJDEEnterpriseOneTrace calls can locate tracelog.exe in your system.</span></span> <span data-ttu-id="56064-115">既定では、BTAJDEEnterpriseOneTrace は現在のパスを検索します。</span><span class="sxs-lookup"><span data-stu-id="56064-115">By default, BTAJDEEnterpriseOneTrace searches the current path.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="56064-116">tracelog.exe は Microsoft SDK から使用でき、BizTalk Adapter for JD Edwards EnterpriseOne で提供されているコマンドと互換性があります。</span><span class="sxs-lookup"><span data-stu-id="56064-116">tracelog.exe is available from the Microsoft SDK and is compatible with the commands provided by  BizTalk Adapter  for JD Edwards EnterpriseOne.</span></span> <span data-ttu-id="56064-117">Logman.exe を使用するのには、logman のマニュアルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="56064-117">To use logman.exe, refer to the logman documentation.</span></span>  
  
-   <span data-ttu-id="56064-118">**コンシューマー アプリケーション**です。</span><span class="sxs-lookup"><span data-stu-id="56064-118">**Consumer application**.</span></span> <span data-ttu-id="56064-119">記録されたイベントを読み取ります。</span><span class="sxs-lookup"><span data-stu-id="56064-119">Reads logged events.</span></span> <span data-ttu-id="56064-120">コンシュマー アプリケーションで etl ファイルのイベントを読み取るには、Event Tracing for Windows によるダンプ処理でファイルを生成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="56064-120">For the consumer application to be able to read the event in the etl file, Event Tracing for Windows must dump them into that file.</span></span> <span data-ttu-id="56064-121">通常、これはトレースが非アクティブ化されたときに実行されます。</span><span class="sxs-lookup"><span data-stu-id="56064-121">Normally this is done when the controller deactivates the tracing.</span></span>  
  
     <span data-ttu-id="56064-122">コント ローラーにコンシューマー アプリケーションを使用して、トレースを非アクティブ化せず、リアルタイムのオプションを使用してトレースをアクティブ化する必要があります**\<リアルタイム\>=-rt**です。</span><span class="sxs-lookup"><span data-stu-id="56064-122">To use the consumer application without deactivating the trace, the controller must activate the trace with the real-time option, **\<Real time\> = -rt**.</span></span>  
  
-   <span data-ttu-id="56064-123">**プロバイダー**です。</span><span class="sxs-lookup"><span data-stu-id="56064-123">**Provider**.</span></span> <span data-ttu-id="56064-124">イベントを提供するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="56064-124">Used to provide the event.</span></span> <span data-ttu-id="56064-125">BizTalk Adapter for JD Edwards EnterpriseOne には 3 種類のプロバイダーが用意されています。</span><span class="sxs-lookup"><span data-stu-id="56064-125">BizTalk Adapter for JD Edwards EnterpriseOne includes three different providers.</span></span> <span data-ttu-id="56064-126">これらは Windows Management Instrumentation (WMI) に登録されます。</span><span class="sxs-lookup"><span data-stu-id="56064-126">They are registered in Windows Management Instrumentation (WMI).</span></span> <span data-ttu-id="56064-127">root\WMI\EventTrace パス内で登録プロバイダーを検索するには、WMI CIM Studio などのツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="56064-127">To find the registered providers in the root\WMI\EventTrace path, you can use tools such as WMI CIM Studio.</span></span>  
  
 <span data-ttu-id="56064-128">BizTalk Adapter for JD Edwards EnterpriseOne には 3 つのプロバイダーがあり、異なる種類のメッセージを記録できます。</span><span class="sxs-lookup"><span data-stu-id="56064-128">BizTalk Adapter  for JD Edwards EnterpriseOne contains three providers, allowing you to log different kinds of messages:</span></span>  
  
-   <span data-ttu-id="56064-129">**受信元ログ プロバイダー**:\<トレース要素\>スイッチが**-受信者**です。</span><span class="sxs-lookup"><span data-stu-id="56064-129">**Receiver Logging Provider**: The \<Trace element\> switch is **-receiver**.</span></span> <span data-ttu-id="56064-130">使用して**-受信者**を実行時にアダプターによって受信されたログからすべてのメッセージを取得します。</span><span class="sxs-lookup"><span data-stu-id="56064-130">Use **-receiver** to get any messages from the log that were received by the adapter at run time.</span></span>  
  
-   <span data-ttu-id="56064-131">**送信元ログ プロバイダー**:\<トレース要素\>スイッチが**-トランスミッター**です。</span><span class="sxs-lookup"><span data-stu-id="56064-131">**Transmitter Logging Provider**: The \<Trace element\> switch is **-transmitter**.</span></span> <span data-ttu-id="56064-132">使用して**-トランスミッター**を実行時にアダプターによって送信されたログからすべてのメッセージを取得します。</span><span class="sxs-lookup"><span data-stu-id="56064-132">Use **-transmitter** to get any messages from the log that were transmitted by the adapter at run time.</span></span>  
  
-   <span data-ttu-id="56064-133">**管理ログ プロバイダー**:\<トレース要素\>スイッチが**-管理**使用**-管理**生成されたログからすべてのメッセージを取得するにはサーバー システムの参照中にです。</span><span class="sxs-lookup"><span data-stu-id="56064-133">**Management Logging Provider**: The \<Trace element\> switch is **-management** Use **-management** to get any messages from the log that were generated during browsing of the server system.</span></span>  
  
### <a name="btajdeenterpriseonetrace-command"></a><span data-ttu-id="56064-134">BTAJDEEnterpriseOneTrace コマンド</span><span class="sxs-lookup"><span data-stu-id="56064-134">BTAJDEEnterpriseOneTrace Command</span></span>  
 <span data-ttu-id="56064-135">ETW を使用して、BizTalk Adapter for JD Edwards EnterpriseOne のコマンドを実行する**BTAJDEEnterpriseOneTrace.cmd**です。</span><span class="sxs-lookup"><span data-stu-id="56064-135">To use ETW, run the BizTalk Adapter for JD Edwards EnterpriseOne command, **BTAJDEEnterpriseOneTrace.cmd**.</span></span> <span data-ttu-id="56064-136">このコマンドは次のように使用します。</span><span class="sxs-lookup"><span data-stu-id="56064-136">You use this command as follows:</span></span>  
  
```  
BTAJDEEnterpriseOneTrace <Trace element> -start [-cir <MB>|   
-seq <MB>] [-rt] logfile  
BTAJDEEnterpriseOneTrace <Trace element> -stop  
  
```  
  
 <span data-ttu-id="56064-137">場所: **\<トレース要素\>**プロバイダーの種類は、(必須)。</span><span class="sxs-lookup"><span data-stu-id="56064-137">Where: **\<Trace element\>** (required) is the kind of provider.</span></span>  
  
 <span data-ttu-id="56064-138">そのオプションは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="56064-138">Its options are:</span></span>  
  
-   <span data-ttu-id="56064-139">**送信機能**</span><span class="sxs-lookup"><span data-stu-id="56064-139">**-transmitter**</span></span>  
  
-   <span data-ttu-id="56064-140">**-受信機**</span><span class="sxs-lookup"><span data-stu-id="56064-140">**-receiver**</span></span>  
  
-   <span data-ttu-id="56064-141">**-管理**</span><span class="sxs-lookup"><span data-stu-id="56064-141">**-management**</span></span>  
  
-   <span data-ttu-id="56064-142">**-開始、停止**: プロバイダーをアクティブまたは非アクティブです。</span><span class="sxs-lookup"><span data-stu-id="56064-142">**-start, -stop**: Activate or deactivate the provider.</span></span>  
  
-   <span data-ttu-id="56064-143">**-cir \<MB\>**: ファイルのサイズおよび種類です。</span><span class="sxs-lookup"><span data-stu-id="56064-143">**-cir \<MB\>**: Size and kind of file.</span></span> <span data-ttu-id="56064-144">-cir は循環ファイルです。</span><span class="sxs-lookup"><span data-stu-id="56064-144">-cir is a circular file.</span></span> <span data-ttu-id="56064-145">\<MB\>: サイズはメガ単位です。</span><span class="sxs-lookup"><span data-stu-id="56064-145">\<MB\>: Size in meg.</span></span>  
  
-   <span data-ttu-id="56064-146">**-seq \<MB\>**: ファイルのサイズおよび種類です。</span><span class="sxs-lookup"><span data-stu-id="56064-146">**-seq \<MB\>**: Size and kind of file.</span></span> <span data-ttu-id="56064-147">-seq はシーケンシャル ファイルです。</span><span class="sxs-lookup"><span data-stu-id="56064-147">-seq is a sequential file.</span></span> <span data-ttu-id="56064-148">\<MB\>: サイズはメガ単位です。</span><span class="sxs-lookup"><span data-stu-id="56064-148">\<MB\>: Size in meg.</span></span>  
  
-   <span data-ttu-id="56064-149">**-rt**: リアル タイム モードに設定します。</span><span class="sxs-lookup"><span data-stu-id="56064-149">**-rt**: Set the real time mode on.</span></span>  
  
-   <span data-ttu-id="56064-150">**Logfile**: ログ ファイルの名前 (既定では c:\rtlog.etl) です。</span><span class="sxs-lookup"><span data-stu-id="56064-150">**Logfile**: Name of the log file (c:\rtlog.etl is the default).</span></span>  
  
 <span data-ttu-id="56064-151">例:</span><span class="sxs-lookup"><span data-stu-id="56064-151">For example:</span></span>  
  
```  
BTAJDEEnterpriseOneTrace -transmitter -start -cir 10 -rt c:\log\mylog.etl  
BTAJDEEnterpriseOneTrace -transmitter -stop  
```  
  
## <a name="see-also"></a><span data-ttu-id="56064-152">参照</span><span class="sxs-lookup"><span data-stu-id="56064-152">See Also</span></span>  
 [<span data-ttu-id="56064-153">JD Edwards EnterpriseOne のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="56064-153">Troubleshooting JD Edwards EnterpriseOne</span></span>](../core/troubleshooting-jd-edwards-enterpriseone.md)