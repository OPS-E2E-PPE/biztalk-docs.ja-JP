---
title: "Windows3 のイベントの追跡の使用 |Microsoft ドキュメント"
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
- consumer application
- BTATIBCOEMSTrace command
- Event Tracing for Windows
ms.assetid: 71954431-2015-4d50-b69e-500c883b1e04
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 75b2b339c99dcf1b64368c73381d1dbe81e0fb39
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="using-event-tracing-for-windows"></a><span data-ttu-id="d3a67-102">Windows イベント トレーシングの使用</span><span class="sxs-lookup"><span data-stu-id="d3a67-102">Using Event Tracing for Windows</span></span>
<span data-ttu-id="d3a67-103">Microsoft BizTalk Adapter for TIBCO Enterprise Message Service は、エラー メッセージ、警告メッセージ、および情報メッセージを Windows イベント ビューアーに記録します。</span><span class="sxs-lookup"><span data-stu-id="d3a67-103">Microsoft BizTalk Adapter for TIBCO Enterprise Message Service logs error, warning, and information messages to the Windows Event Viewer.</span></span> <span data-ttu-id="d3a67-104">追加のトレーシング メッセージを表示するには、Windows イベント トレーシング (ETW) ツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="d3a67-104">You can see additional tracing messages by using the Event Tracing for Windows (ETW) tool.</span></span> <span data-ttu-id="d3a67-105">ETW をアクティブにすると、メッセージ受信用の *.etl ファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="d3a67-105">When ETW is activated, it creates an *.etl file to receive the messages.</span></span> <span data-ttu-id="d3a67-106">このファイルはバイナリ形式であり、読み取るには変換する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d3a67-106">This file is in binary format and must be converted to be read.</span></span> <span data-ttu-id="d3a67-107">これを行うには、解釈に利用できるコンシューマー アプリケーションが必要、 \*.etl ファイル、tracerpt.exe や tracedmp.exe などです。</span><span class="sxs-lookup"><span data-stu-id="d3a67-107">To do this, you must have a consumer application available to interpret the \*.etl file, for example, tracerpt.exe or tracedmp.exe.</span></span> <span data-ttu-id="d3a67-108">たとえば、tracerpt.exe アプリケーションに変換する、 \*.etl ファイルを 2 つのテキスト ファイル: summary.txt と dumpfile.csv です。</span><span class="sxs-lookup"><span data-stu-id="d3a67-108">For example, the tracerpt.exe application converts the \*.etl file into two text files: summary.txt and dumpfile.csv.</span></span>  
  
## <a name="etw-components"></a><span data-ttu-id="d3a67-109">ETW コンポーネント</span><span class="sxs-lookup"><span data-stu-id="d3a67-109">ETW Components</span></span>  
 <span data-ttu-id="d3a67-110">Windows イベント トレーシングには 3 つのコンポーネントがあります。</span><span class="sxs-lookup"><span data-stu-id="d3a67-110">Event Tracing for Windows has three components:</span></span>  
  
-   <span data-ttu-id="d3a67-111">**コント ローラー アプリケーション**: をアクティブにし、(たとえば、tracelog.exe または logman.exe) プロバイダーが非アクティブ化します。</span><span class="sxs-lookup"><span data-stu-id="d3a67-111">**Controller application**: Activates and deactivates a provider (for example, tracelog.exe or logman.exe).</span></span>  
  
     <span data-ttu-id="d3a67-112">PATH 環境変数を、tracelog.exe の場所を指すように設定します。</span><span class="sxs-lookup"><span data-stu-id="d3a67-112">You set your PATH environment variable to point to the location of tracelog.exe.</span></span> <span data-ttu-id="d3a67-113">これにより、BTATIBCO EMSTrace の呼び出しが、システムの tracelog.exe を見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="d3a67-113">This makes sure that BTATIBCO EMSTrace calls can locate tracelog.exe in the system.</span></span> <span data-ttu-id="d3a67-114">既定では、BTATIBCO EMSTrace は現在のパスを検索します。</span><span class="sxs-lookup"><span data-stu-id="d3a67-114">By default, BTATIBCO EMSTrace searches the current path.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d3a67-115">tracelog.exe は Microsoft SDK に含まれており、Microsoft BizTalk Adapter for TIBCO Enterprise Message Service で提供されるコマンドと互換性があります。</span><span class="sxs-lookup"><span data-stu-id="d3a67-115">tracelog.exe is available from the Microsoft SDK and is compatible with the commands provided by Microsoft BizTalk Adapter for TIBCO Enterprise Message Service.</span></span> <span data-ttu-id="d3a67-116">logman.exe の使い方については、logman のマニュアルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d3a67-116">To use logman.exe, see the logman documentation.</span></span>  
  
-   <span data-ttu-id="d3a67-117">**コンシューマー アプリケーション**: 記録されたイベントの読み取り。</span><span class="sxs-lookup"><span data-stu-id="d3a67-117">**Consumer application**: Reads logged events.</span></span>  
  
     <span data-ttu-id="d3a67-118">コンシュマー アプリケーションで etl ファイルのイベントを読み取るには、Event Tracing for Windows によるダンプ処理でファイルを生成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d3a67-118">For the consumer application to be able to read the event in the etl file, Event Tracing for Windows must dump them into that file.</span></span> <span data-ttu-id="d3a67-119">通常、この作業は、コントローラーがトレーシングを非アクティブ化するときに行われます。</span><span class="sxs-lookup"><span data-stu-id="d3a67-119">Typically this is done when the controller deactivates the tracing.</span></span>  
  
     <span data-ttu-id="d3a67-120">コント ローラーにコンシューマー アプリケーションを使用して、トレースを非アクティブ化せず、リアル タイム オプションを使用してトレースをアクティブ化する必要があります\<リアルタイム\>-rt を = です。</span><span class="sxs-lookup"><span data-stu-id="d3a67-120">To use the consumer application without deactivating the trace, the controller must activate the trace with the real time option, \<Real time\> = -rt.</span></span>  
  
-   <span data-ttu-id="d3a67-121">**プロバイダー**: イベントを提供します。</span><span class="sxs-lookup"><span data-stu-id="d3a67-121">**Provider**: Provides the event.</span></span>  
  
     <span data-ttu-id="d3a67-122">BizTalk Adapter for TIBCO Enterprise Message Service には 3 つの異なるプロバイダーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="d3a67-122">BizTalk Adapter for TIBCO Enterprise Message Service includes three different providers.</span></span> <span data-ttu-id="d3a67-123">これらは Windows Management Instrumentation (WMI) に登録されます。</span><span class="sxs-lookup"><span data-stu-id="d3a67-123">They are registered in Windows Management Instrumentation (WMI).</span></span> <span data-ttu-id="d3a67-124">root\WMI\EventTrace パス内で登録プロバイダーを検索するには、WMI CIM Studio などのツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="d3a67-124">To find the registered providers in the root\WMI\EventTrace path, you can use tools such as WMI CIM Studio.</span></span>  
  
 <span data-ttu-id="d3a67-125">BizTalk Adapter for TIBCO Enterprise Message Service には、さまざまな種類のメッセージをログに記録することを可能にするプロバイダーがあります。</span><span class="sxs-lookup"><span data-stu-id="d3a67-125">BizTalk Adapter for TIBCO Enterprise Message Service has providers that enable you to log different kinds of messages:</span></span>  
  
-   <span data-ttu-id="d3a67-126">**受信元ログ プロバイダー**:\<トレース要素\>スイッチが**-受信者**です。</span><span class="sxs-lookup"><span data-stu-id="d3a67-126">**Receiver Logging Provider**: The \<Trace element\> switch is **-receiver**.</span></span>  
  
     <span data-ttu-id="d3a67-127">使用して**-受信者**実行時にアダプターによって受信されたログからすべてのメッセージを取得します。</span><span class="sxs-lookup"><span data-stu-id="d3a67-127">Use **-receiver** to obtain any messages from the log that were received by the adapter at run time.</span></span>  
  
-   <span data-ttu-id="d3a67-128">**送信元ログ プロバイダー**:\<トレース要素\>スイッチが**-トランスミッター**です。</span><span class="sxs-lookup"><span data-stu-id="d3a67-128">**Transmitter Logging Provider**: the \<Trace element\> switch is **-transmitter**.</span></span>  
  
     <span data-ttu-id="d3a67-129">使用して**-トランスミッター**実行時にアダプターによって送信されたログからすべてのメッセージを取得します。</span><span class="sxs-lookup"><span data-stu-id="d3a67-129">Use **-transmitter**to obtain any messages from the log that were transmitted by the adapter at run time.</span></span>  
  
### <a name="btatibcoemstrace-command"></a><span data-ttu-id="d3a67-130">BTATIBCOEMSTrace コマンド</span><span class="sxs-lookup"><span data-stu-id="d3a67-130">BTATIBCOEMSTrace Command</span></span>  
 <span data-ttu-id="d3a67-131">ETW を使用するには、BizTalk Adapter for TIBCO Enterprise Message Service のコマンド BTATIBCOEMSTrace.cmd を実行します。</span><span class="sxs-lookup"><span data-stu-id="d3a67-131">To use ETW, run the BizTalk Adapter for TIBCO Enterprise Message Service command, BTATIBCOEMSTrace.cmd.</span></span> <span data-ttu-id="d3a67-132">このコマンドは次のように使用します。</span><span class="sxs-lookup"><span data-stu-id="d3a67-132">You use this command as follows:</span></span>  
  
```  
BTATIBCOEMSTrace <Trace element> -start [-cir <MB>|   
    -seq <MB>] [-rt] logfile  
BTA TIBCOEMSTrace <Trace element> -stop  
```  
  
 <span data-ttu-id="d3a67-133">各要素の説明は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d3a67-133">Where:</span></span>  
  
-   <span data-ttu-id="d3a67-134">**\<Trace 要素\>**プロバイダーの種類は、(必須)。</span><span class="sxs-lookup"><span data-stu-id="d3a67-134">**\<Trace element\>** (required) is the kind of provider.</span></span>  
  
 <span data-ttu-id="d3a67-135">そのオプションは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d3a67-135">Its options are as follows:</span></span>  
  
-   <span data-ttu-id="d3a67-136">**送信機能**</span><span class="sxs-lookup"><span data-stu-id="d3a67-136">**-transmitter**</span></span>  
  
-   <span data-ttu-id="d3a67-137">**-受信機**</span><span class="sxs-lookup"><span data-stu-id="d3a67-137">**-receiver**</span></span>  
  
-   <span data-ttu-id="d3a67-138">**-開始、停止**: プロバイダーをアクティブまたは非アクティブです。</span><span class="sxs-lookup"><span data-stu-id="d3a67-138">**-start, -stop**: Activate or deactivate the provider.</span></span>  
  
-   <span data-ttu-id="d3a67-139">**-cir \<MB\>**: ファイルのサイズおよび種類です。</span><span class="sxs-lookup"><span data-stu-id="d3a67-139">**-cir \<MB\>**: Size and kind of file.</span></span> <span data-ttu-id="d3a67-140">**-cir**循環ファイルです。</span><span class="sxs-lookup"><span data-stu-id="d3a67-140">**-cir** is a circular file.</span></span> <span data-ttu-id="d3a67-141">**\<MB\>**: サイズ (メガバイト単位)。</span><span class="sxs-lookup"><span data-stu-id="d3a67-141">**\<MB\>**: Size in megabytes.</span></span>  
  
-   <span data-ttu-id="d3a67-142">**-seq \<MB\>**: ファイルのサイズおよび種類です。</span><span class="sxs-lookup"><span data-stu-id="d3a67-142">**-seq \<MB\>**: Size and kind of file.</span></span> <span data-ttu-id="d3a67-143">**-seq**シーケンシャル ファイルです。</span><span class="sxs-lookup"><span data-stu-id="d3a67-143">**-seq** is a sequential file.</span></span> <span data-ttu-id="d3a67-144">**\<MB\>**: サイズ (メガバイト単位)。</span><span class="sxs-lookup"><span data-stu-id="d3a67-144">**\<MB\>**: Size in megabytes.</span></span>  
  
-   <span data-ttu-id="d3a67-145">**-rt**: リアル タイム モードに設定します。</span><span class="sxs-lookup"><span data-stu-id="d3a67-145">**-rt**: Set the real time mode on.</span></span>  
  
-   <span data-ttu-id="d3a67-146">**Logfile**: ログ ファイルの名前 (既定では c:\rtlog.etl) です。</span><span class="sxs-lookup"><span data-stu-id="d3a67-146">**Logfile**: Name of the log file (c:\rtlog.etl is the default).</span></span>  
  
 <span data-ttu-id="d3a67-147">例:</span><span class="sxs-lookup"><span data-stu-id="d3a67-147">For example:</span></span>  
  
```  
BTATIBCOEMSTrace -transmitter -start -cir 10 -rt c:\log\mylog.etl  
BTATIBCOEMSTrace -transmitter -stop  
```  
  
## <a name="see-also"></a><span data-ttu-id="d3a67-148">参照</span><span class="sxs-lookup"><span data-stu-id="d3a67-148">See Also</span></span>  
 [<span data-ttu-id="d3a67-149">TIBCO Enterprise Message Service のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="d3a67-149">Troubleshooting TIBCO Enterprise Message Service</span></span>](../core/troubleshooting-tibco-enterprise-message-service.md)