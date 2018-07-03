---
title: Windows5 のイベント追跡の使用 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ETW
- events, Event Tracing for Windows
- controller application
- ETW components
- consumer application
- Provider
- Event Tracing for Windows
- Event Tracing for Windows, components
- BTAPeopleSoftTrace command
ms.assetid: 330ef84b-5e2a-4b79-85a9-72271eb489d2
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f0fa744d7182f6238d71765afac2411b60974b5c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37000035"
---
# <a name="using-event-tracing-for-windows"></a><span data-ttu-id="c99b7-102">イベント トレーシング Windows の使用</span><span class="sxs-lookup"><span data-stu-id="c99b7-102">Using Event Tracing for Windows</span></span>
<span data-ttu-id="c99b7-103">Microsoft BizTalk Adapter for PeopleSoft Enterprise は、エラー、警告、および情報メッセージを、Windows イベント ビューアーに記録します。</span><span class="sxs-lookup"><span data-stu-id="c99b7-103">Microsoft BizTalk Adapter for PeopleSoft Enterprise logs error, warning, and information messages to the Windows Event Viewer.</span></span> <span data-ttu-id="c99b7-104">追加のトレーシング メッセージを表示するには、Windows イベント トレーシング (ETW) ツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="c99b7-104">You can see additional tracing messages by using the Event Tracing for Windows (ETW) tool.</span></span> <span data-ttu-id="c99b7-105">ETW が有効である場合、このメッセージを受信する \*.etl ファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="c99b7-105">When ETW is enabled, it creates an \*.etl file to receive the messages.</span></span> <span data-ttu-id="c99b7-106">ファイルはバイナリ形式では、読み取るには変換する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c99b7-106">The file is in binary format and must be converted to be read.</span></span> <span data-ttu-id="c99b7-107">これを行うには解釈に利用できるコンシューマー アプリケーションが必要、 \*.etl ファイル; tracerpt.exe や tracedmp.exe などです。</span><span class="sxs-lookup"><span data-stu-id="c99b7-107">To do this you must have a consumer application available to interpret the \*.etl file; for example, tracerpt.exe or tracedmp.exe.</span></span>  
  
## <a name="etw-components"></a><span data-ttu-id="c99b7-108">ETW コンポーネント</span><span class="sxs-lookup"><span data-stu-id="c99b7-108">ETW Components</span></span>  
 <span data-ttu-id="c99b7-109">Windows イベント トレーシングには 3 つのコンポーネントがあります。</span><span class="sxs-lookup"><span data-stu-id="c99b7-109">Event Tracing for Windows has three components:</span></span>  
  
- <span data-ttu-id="c99b7-110">**コント ローラー アプリケーション**: をアクティブにし、(たとえば、tracelog.exe または logman.exe) のプロバイダーを非アクティブにします。</span><span class="sxs-lookup"><span data-stu-id="c99b7-110">**Controller application**: Activates and deactivates a provider (for example, tracelog.exe or logman.exe).</span></span>  
  
   <span data-ttu-id="c99b7-111">PATH 環境変数を、tracelog.exe の場所を指すように設定します。</span><span class="sxs-lookup"><span data-stu-id="c99b7-111">You set your PATH environment variable to point to the location of tracelog.exe.</span></span> <span data-ttu-id="c99b7-112">ため`BTAPeopleSoftTrace`呼び出しは、システムの tracelog.exe を見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="c99b7-112">This makes sure that `BTAPeopleSoftTrace` calls can locate tracelog.exe in the system.</span></span> <span data-ttu-id="c99b7-113">既定では、BTAPeopleSoftTrace は現在のパスを検索します。</span><span class="sxs-lookup"><span data-stu-id="c99b7-113">By default, BTAPeopleSoftTrace searches the current path.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="c99b7-114">tracelog.exe は Microsoft SDK に含まれており、BizTalk Adapter for PeopleSoft Enterprise で提供されるコマンドと互換性があります。</span><span class="sxs-lookup"><span data-stu-id="c99b7-114">tracelog.exe is available from the Microsoft SDK and is compatible with the commands provided by BizTalk Adapter for PeopleSoft Enterprise.</span></span> <span data-ttu-id="c99b7-115">logman.exe の使い方については、logman のマニュアルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c99b7-115">To use logman.exe, see the logman documentation.</span></span>  
  
- <span data-ttu-id="c99b7-116">**コンシューマー アプリケーション**: 記録されたイベントの読み取り。</span><span class="sxs-lookup"><span data-stu-id="c99b7-116">**Consumer application**: Reads logged events.</span></span>  
  
   <span data-ttu-id="c99b7-117">コンシューマー アプリケーションで .etl ファイル内のイベントを読み取るには、Windows イベント トレーシングでそれらのイベントを .etl ファイルにダンプする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c99b7-117">For the consumer application to be able to read the event in the .etl file, Event Tracing for Windows must dump them into that file.</span></span> <span data-ttu-id="c99b7-118">通常、この作業は、コントローラーがトレーシングを非アクティブ化するときに行われます。</span><span class="sxs-lookup"><span data-stu-id="c99b7-118">Typically this is done when the controller deactivates the tracing.</span></span>  
  
   <span data-ttu-id="c99b7-119">コンシューマーを使用して、トレースを非アクティブ化せず、リアルタイム オプションでは、トレースで、コント ローラーによってアクティブ化する必要があります\<リアルタイム\>-rt を = です。</span><span class="sxs-lookup"><span data-stu-id="c99b7-119">To use the consumer without deactivating the trace, the controller must activate the trace with the real time option, \<Real time\> = -rt.</span></span>  
  
- <span data-ttu-id="c99b7-120">**プロバイダー:** イベントを提供します。</span><span class="sxs-lookup"><span data-stu-id="c99b7-120">**Provider:** Provides the event.</span></span>  
  
   <span data-ttu-id="c99b7-121">BizTalk Adapter for PeopleSoft Enterprise には、5 種類のプロバイダーがあります。</span><span class="sxs-lookup"><span data-stu-id="c99b7-121">BizTalk Adapter for PeopleSoft Enterprise has five different providers.</span></span> <span data-ttu-id="c99b7-122">これらは Windows Management Instrumentation (WMI) に登録されます。</span><span class="sxs-lookup"><span data-stu-id="c99b7-122">They are registered in Windows Management Instrumentation (WMI).</span></span> <span data-ttu-id="c99b7-123">登録されているプロバイダーを検索する、 **root \wmi\eventtrace**パス、WMI CIM Studio などのツールを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="c99b7-123">To find the registered providers in the **root\WMI\EventTrace** path, you can use tools such as WMI CIM Studio.</span></span>  
  
  <span data-ttu-id="c99b7-124">BizTalk Adapter for PeopleSoft Enterprise には、5 つのプロバイダーが用意されており、種類の異なるメッセージをログに記録できます。</span><span class="sxs-lookup"><span data-stu-id="c99b7-124">BizTalk Adapter for PeopleSoft Enterprise has five providers, allowing you to log different kinds of messages:</span></span>  
  
- <span data-ttu-id="c99b7-125">**受信側のログ記録プロバイダー**: \<Trace 要素\>スイッチが **-受信者**します。</span><span class="sxs-lookup"><span data-stu-id="c99b7-125">**Receiver Logging Provider**: The \<Trace element\> switch is **-receiver**.</span></span>  
  
- <span data-ttu-id="c99b7-126">**受信元 CastDetails プロバイダー**: \<Trace 要素\>スイッチが **- castDetailsReceive**します。</span><span class="sxs-lookup"><span data-stu-id="c99b7-126">**Receiver CastDetails Provider**: The \<Trace element\> switch is **-castDetailsReceive**.</span></span>  
  
- <span data-ttu-id="c99b7-127">**送信元ログ プロバイダー**: \<Trace 要素\>スイッチが **-送信機**します。</span><span class="sxs-lookup"><span data-stu-id="c99b7-127">**Transmitter Logging Provider**: The \<Trace element\> switch is **-transmitter**.</span></span>  
  
- <span data-ttu-id="c99b7-128">**送信元 CastDetails プロバイダー**: \<Trace 要素\>スイッチが **- castDetailsTransmit**します。</span><span class="sxs-lookup"><span data-stu-id="c99b7-128">**Transmitter CastDetails Provider**: The \<Trace element\> switch is **-castDetailsTransmit**.</span></span>  
  
- <span data-ttu-id="c99b7-129">**管理ログ プロバイダー**: \<Trace 要素\>スイッチが **-管理**します。</span><span class="sxs-lookup"><span data-stu-id="c99b7-129">**Management Logging Provider**: The \<Trace element\> switch is **-management**.</span></span>  
  
## <a name="btapeoplesofttrace-command"></a><span data-ttu-id="c99b7-130">BTAPeopleSoftTrace コマンド</span><span class="sxs-lookup"><span data-stu-id="c99b7-130">BTAPeopleSoftTrace Command</span></span>  
 <span data-ttu-id="c99b7-131">ETW を使用して、アダプターのコマンドを実行する**BTAPeopleSoftTrace.cmd**します。</span><span class="sxs-lookup"><span data-stu-id="c99b7-131">To use ETW, run the adapter command, **BTAPeopleSoftTrace.cmd**.</span></span> <span data-ttu-id="c99b7-132">このコマンドは次のように使用します。</span><span class="sxs-lookup"><span data-stu-id="c99b7-132">You use this command as follows:</span></span>  
  
```  
BTAPeopleSoftTrace <Trace element> -start [-cir <MB>|   
    -seq <MB>] [-rt] logfile  
BTAPeopleSoftTrace <Trace element> -stop  
```  
  
 <span data-ttu-id="c99b7-133">各要素の説明は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c99b7-133">Where:</span></span>  
  
- <span data-ttu-id="c99b7-134">\<Trace 要素\>プロバイダーの種類は、(必須)。</span><span class="sxs-lookup"><span data-stu-id="c99b7-134">\<Trace element\> (required) is the kind of provider.</span></span>  
  
   <span data-ttu-id="c99b7-135">オプションは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c99b7-135">Options are as follows:</span></span>  
  
  -   <span data-ttu-id="c99b7-136">**-castDetailsTransmit**</span><span class="sxs-lookup"><span data-stu-id="c99b7-136">**-castDetailsTransmit**</span></span>  
  
  -   <span data-ttu-id="c99b7-137">**-送信機**</span><span class="sxs-lookup"><span data-stu-id="c99b7-137">**-transmitter**</span></span>  
  
  -   <span data-ttu-id="c99b7-138">**-castDetailsReceive**</span><span class="sxs-lookup"><span data-stu-id="c99b7-138">**-castDetailsReceive**</span></span>  
  
  -   <span data-ttu-id="c99b7-139">**-受信機**</span><span class="sxs-lookup"><span data-stu-id="c99b7-139">**-receiver**</span></span>  
  
  -   <span data-ttu-id="c99b7-140">**-管理**</span><span class="sxs-lookup"><span data-stu-id="c99b7-140">**-management**</span></span>  
  
  -   <span data-ttu-id="c99b7-141">**-開始、停止**: プロバイダーをアクティブまたは非アクティブです。</span><span class="sxs-lookup"><span data-stu-id="c99b7-141">**-start, -stop**: Activate or deactivate the provider.</span></span>  
  
- <span data-ttu-id="c99b7-142">**-cir \<MB\>**: ファイルのサイズおよび種類。</span><span class="sxs-lookup"><span data-stu-id="c99b7-142">**-cir \<MB\>**: Size and kind of file.</span></span> <span data-ttu-id="c99b7-143">-cir は循環ファイルです。</span><span class="sxs-lookup"><span data-stu-id="c99b7-143">-cir is a circular file.</span></span> <span data-ttu-id="c99b7-144">\<MB\>: サイズ (メガバイト単位)。</span><span class="sxs-lookup"><span data-stu-id="c99b7-144">\<MB\>: Size in megabytes.</span></span>  
  
- <span data-ttu-id="c99b7-145">**-seq \<MB\>**: ファイルのサイズおよび種類。</span><span class="sxs-lookup"><span data-stu-id="c99b7-145">**-seq \<MB\>**: Size and kind of file.</span></span> <span data-ttu-id="c99b7-146">-seq はシーケンシャル ファイルです。</span><span class="sxs-lookup"><span data-stu-id="c99b7-146">-seq is a sequential file.</span></span> <span data-ttu-id="c99b7-147">\<MB\>: サイズ (メガバイト単位)。</span><span class="sxs-lookup"><span data-stu-id="c99b7-147">\<MB\>: Size in megabytes.</span></span>  
  
- <span data-ttu-id="c99b7-148">**-rt**: のリアル タイム モードに設定します。</span><span class="sxs-lookup"><span data-stu-id="c99b7-148">**-rt**: Set the real time mode on.</span></span>  
  
- <span data-ttu-id="c99b7-149">**ログ ファイル**: (既定では C:\rtlog.etl) ログ ファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="c99b7-149">**Logfile**: Name of the log file (C:\rtlog.etl is the default).</span></span>  
  
  <span data-ttu-id="c99b7-150">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="c99b7-150">For example:</span></span>  
  
```  
BTAPeopleSoftTrace -transmitter -start -cir 10 -rt C:\log\mylog.etl  
BTAPeopleSoftTrace -transmitter -stop  
```  
  
## <a name="see-also"></a><span data-ttu-id="c99b7-151">参照</span><span class="sxs-lookup"><span data-stu-id="c99b7-151">See Also</span></span>  
 [<span data-ttu-id="c99b7-152">PeopleSoft のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="c99b7-152">Troubleshooting PeopleSoft</span></span>](../core/troubleshooting-peoplesoft.md)