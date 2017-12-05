---
title: "Windows5 のイベントの追跡の使用 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 60a317dabd31bc1a6f37645c6b3fb2ce25d6de43
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="using-event-tracing-for-windows"></a><span data-ttu-id="2dad4-102">Windows イベント トレーシングの使用</span><span class="sxs-lookup"><span data-stu-id="2dad4-102">Using Event Tracing for Windows</span></span>
<span data-ttu-id="2dad4-103">Microsoft BizTalk Adapter for PeopleSoft Enterprise は、エラー、警告、および情報メッセージを、Windows イベント ビューアーに記録します。</span><span class="sxs-lookup"><span data-stu-id="2dad4-103">Microsoft BizTalk Adapter for PeopleSoft Enterprise logs error, warning, and information messages to the Windows Event Viewer.</span></span> <span data-ttu-id="2dad4-104">追加のトレーシング メッセージを表示するには、Windows イベント トレーシング (ETW) ツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="2dad4-104">You can see additional tracing messages by using the Event Tracing for Windows (ETW) tool.</span></span> <span data-ttu-id="2dad4-105">ETW が有効である場合、このメッセージを受信する *.etl ファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="2dad4-105">When ETW is enabled, it creates an *.etl file to receive the messages.</span></span> <span data-ttu-id="2dad4-106">ファイルはバイナリ形式で、読み取るに変換する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2dad4-106">The file is in binary format and must be converted to be read.</span></span> <span data-ttu-id="2dad4-107">これを行うには解釈に利用できるコンシューマー アプリケーションが必要、 \*.etl ファイルです。 たとえば、tracerpt.exe や tracedmp.exe です。</span><span class="sxs-lookup"><span data-stu-id="2dad4-107">To do this you must have a consumer application available to interpret the \*.etl file; for example, tracerpt.exe or tracedmp.exe.</span></span>  
  
## <a name="etw-components"></a><span data-ttu-id="2dad4-108">ETW コンポーネント</span><span class="sxs-lookup"><span data-stu-id="2dad4-108">ETW Components</span></span>  
 <span data-ttu-id="2dad4-109">Windows イベント トレーシングには 3 つのコンポーネントがあります。</span><span class="sxs-lookup"><span data-stu-id="2dad4-109">Event Tracing for Windows has three components:</span></span>  
  
-   <span data-ttu-id="2dad4-110">**コント ローラー アプリケーション**: をアクティブにし、(たとえば、tracelog.exe または logman.exe) プロバイダーが非アクティブ化します。</span><span class="sxs-lookup"><span data-stu-id="2dad4-110">**Controller application**: Activates and deactivates a provider (for example, tracelog.exe or logman.exe).</span></span>  
  
     <span data-ttu-id="2dad4-111">PATH 環境変数を、tracelog.exe の場所を指すように設定します。</span><span class="sxs-lookup"><span data-stu-id="2dad4-111">You set your PATH environment variable to point to the location of tracelog.exe.</span></span> <span data-ttu-id="2dad4-112">こうことを確認する`BTAPeopleSoftTrace`呼び出しは、システムの tracelog.exe を見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="2dad4-112">This makes sure that `BTAPeopleSoftTrace` calls can locate tracelog.exe in the system.</span></span> <span data-ttu-id="2dad4-113">既定では、BTAPeopleSoftTrace は現在のパスを検索します。</span><span class="sxs-lookup"><span data-stu-id="2dad4-113">By default, BTAPeopleSoftTrace searches the current path.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2dad4-114">tracelog.exe は Microsoft SDK に含まれており、BizTalk Adapter for PeopleSoft Enterprise で提供されるコマンドと互換性があります。</span><span class="sxs-lookup"><span data-stu-id="2dad4-114">tracelog.exe is available from the Microsoft SDK and is compatible with the commands provided by BizTalk Adapter for PeopleSoft Enterprise.</span></span> <span data-ttu-id="2dad4-115">logman.exe の使い方については、logman のマニュアルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2dad4-115">To use logman.exe, see the logman documentation.</span></span>  
  
-   <span data-ttu-id="2dad4-116">**コンシューマー アプリケーション**: 記録されたイベントの読み取り。</span><span class="sxs-lookup"><span data-stu-id="2dad4-116">**Consumer application**: Reads logged events.</span></span>  
  
     <span data-ttu-id="2dad4-117">コンシューマー アプリケーションで .etl ファイル内のイベントを読み取るには、Windows イベント トレーシングでそれらのイベントを .etl ファイルにダンプする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2dad4-117">For the consumer application to be able to read the event in the .etl file, Event Tracing for Windows must dump them into that file.</span></span> <span data-ttu-id="2dad4-118">通常、この作業は、コントローラーがトレーシングを非アクティブ化するときに行われます。</span><span class="sxs-lookup"><span data-stu-id="2dad4-118">Typically this is done when the controller deactivates the tracing.</span></span>  
  
     <span data-ttu-id="2dad4-119">コント ローラーにコンシューマーを使用して、トレースを非アクティブ化せず、リアル タイム オプションを使用してトレースをアクティブ化する必要があります\<リアルタイム\>-rt を = です。</span><span class="sxs-lookup"><span data-stu-id="2dad4-119">To use the consumer without deactivating the trace, the controller must activate the trace with the real time option, \<Real time\> = -rt.</span></span>  
  
-   <span data-ttu-id="2dad4-120">**プロバイダー:**イベントを提供します。</span><span class="sxs-lookup"><span data-stu-id="2dad4-120">**Provider:** Provides the event.</span></span>  
  
     <span data-ttu-id="2dad4-121">BizTalk Adapter for PeopleSoft Enterprise には、5 種類のプロバイダーがあります。</span><span class="sxs-lookup"><span data-stu-id="2dad4-121">BizTalk Adapter for PeopleSoft Enterprise has five different providers.</span></span> <span data-ttu-id="2dad4-122">これらは Windows Management Instrumentation (WMI) に登録されます。</span><span class="sxs-lookup"><span data-stu-id="2dad4-122">They are registered in Windows Management Instrumentation (WMI).</span></span> <span data-ttu-id="2dad4-123">登録されているプロバイダーが見つかりません、 **root \wmi\eventtrace**パス、WMI CIM Studio などのツールを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="2dad4-123">To find the registered providers in the **root\WMI\EventTrace** path, you can use tools such as WMI CIM Studio.</span></span>  
  
 <span data-ttu-id="2dad4-124">BizTalk Adapter for PeopleSoft Enterprise には、5 つのプロバイダーが用意されており、種類の異なるメッセージをログに記録できます。</span><span class="sxs-lookup"><span data-stu-id="2dad4-124">BizTalk Adapter for PeopleSoft Enterprise has five providers, allowing you to log different kinds of messages:</span></span>  
  
-   <span data-ttu-id="2dad4-125">**受信元ログ プロバイダー**:\<トレース要素\>スイッチが**-受信者**です。</span><span class="sxs-lookup"><span data-stu-id="2dad4-125">**Receiver Logging Provider**: The \<Trace element\> switch is **-receiver**.</span></span>  
  
-   <span data-ttu-id="2dad4-126">**受信元 CastDetails プロバイダー**:\<トレース要素\>スイッチが**- castDetailsReceive**です。</span><span class="sxs-lookup"><span data-stu-id="2dad4-126">**Receiver CastDetails Provider**: The \<Trace element\> switch is **-castDetailsReceive**.</span></span>  
  
-   <span data-ttu-id="2dad4-127">**送信元ログ プロバイダー**:\<トレース要素\>スイッチが**-トランスミッター**です。</span><span class="sxs-lookup"><span data-stu-id="2dad4-127">**Transmitter Logging Provider**: The \<Trace element\> switch is **-transmitter**.</span></span>  
  
-   <span data-ttu-id="2dad4-128">**送信元 CastDetails プロバイダー**:\<トレース要素\>スイッチが**- castDetailsTransmit**です。</span><span class="sxs-lookup"><span data-stu-id="2dad4-128">**Transmitter CastDetails Provider**: The \<Trace element\> switch is **-castDetailsTransmit**.</span></span>  
  
-   <span data-ttu-id="2dad4-129">**管理ログ プロバイダー**:\<トレース要素\>スイッチが**-管理**です。</span><span class="sxs-lookup"><span data-stu-id="2dad4-129">**Management Logging Provider**: The \<Trace element\> switch is **-management**.</span></span>  
  
## <a name="btapeoplesofttrace-command"></a><span data-ttu-id="2dad4-130">BTAPeopleSoftTrace コマンド</span><span class="sxs-lookup"><span data-stu-id="2dad4-130">BTAPeopleSoftTrace Command</span></span>  
 <span data-ttu-id="2dad4-131">ETW を使用して、アダプターのコマンドを実行する**BTAPeopleSoftTrace.cmd**です。</span><span class="sxs-lookup"><span data-stu-id="2dad4-131">To use ETW, run the adapter command, **BTAPeopleSoftTrace.cmd**.</span></span> <span data-ttu-id="2dad4-132">このコマンドは次のように使用します。</span><span class="sxs-lookup"><span data-stu-id="2dad4-132">You use this command as follows:</span></span>  
  
```  
BTAPeopleSoftTrace <Trace element> -start [-cir <MB>|   
    -seq <MB>] [-rt] logfile  
BTAPeopleSoftTrace <Trace element> -stop  
```  
  
 <span data-ttu-id="2dad4-133">各要素の説明は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="2dad4-133">Where:</span></span>  
  
-   <span data-ttu-id="2dad4-134">\<Trace 要素\>プロバイダーの種類は、(必須)。</span><span class="sxs-lookup"><span data-stu-id="2dad4-134">\<Trace element\> (required) is the kind of provider.</span></span>  
  
     <span data-ttu-id="2dad4-135">オプションは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="2dad4-135">Options are as follows:</span></span>  
  
    -   <span data-ttu-id="2dad4-136">**-castDetailsTransmit**</span><span class="sxs-lookup"><span data-stu-id="2dad4-136">**-castDetailsTransmit**</span></span>  
  
    -   <span data-ttu-id="2dad4-137">**送信機能**</span><span class="sxs-lookup"><span data-stu-id="2dad4-137">**-transmitter**</span></span>  
  
    -   <span data-ttu-id="2dad4-138">**-castDetailsReceive**</span><span class="sxs-lookup"><span data-stu-id="2dad4-138">**-castDetailsReceive**</span></span>  
  
    -   <span data-ttu-id="2dad4-139">**-受信機**</span><span class="sxs-lookup"><span data-stu-id="2dad4-139">**-receiver**</span></span>  
  
    -   <span data-ttu-id="2dad4-140">**-管理**</span><span class="sxs-lookup"><span data-stu-id="2dad4-140">**-management**</span></span>  
  
    -   <span data-ttu-id="2dad4-141">**-開始、停止**: プロバイダーをアクティブまたは非アクティブです。</span><span class="sxs-lookup"><span data-stu-id="2dad4-141">**-start, -stop**: Activate or deactivate the provider.</span></span>  
  
-   <span data-ttu-id="2dad4-142">**-cir \<MB\>**: ファイルのサイズおよび種類です。</span><span class="sxs-lookup"><span data-stu-id="2dad4-142">**-cir \<MB\>**: Size and kind of file.</span></span> <span data-ttu-id="2dad4-143">-cir は循環ファイルです。</span><span class="sxs-lookup"><span data-stu-id="2dad4-143">-cir is a circular file.</span></span> <span data-ttu-id="2dad4-144">\<MB\>: サイズ (メガバイト単位)。</span><span class="sxs-lookup"><span data-stu-id="2dad4-144">\<MB\>: Size in megabytes.</span></span>  
  
-   <span data-ttu-id="2dad4-145">**-seq \<MB\>**: ファイルのサイズおよび種類です。</span><span class="sxs-lookup"><span data-stu-id="2dad4-145">**-seq \<MB\>**: Size and kind of file.</span></span> <span data-ttu-id="2dad4-146">-seq はシーケンシャル ファイルです。</span><span class="sxs-lookup"><span data-stu-id="2dad4-146">-seq is a sequential file.</span></span> <span data-ttu-id="2dad4-147">\<MB\>: サイズ (メガバイト単位)。</span><span class="sxs-lookup"><span data-stu-id="2dad4-147">\<MB\>: Size in megabytes.</span></span>  
  
-   <span data-ttu-id="2dad4-148">**-rt**: リアル タイム モードに設定します。</span><span class="sxs-lookup"><span data-stu-id="2dad4-148">**-rt**: Set the real time mode on.</span></span>  
  
-   <span data-ttu-id="2dad4-149">**Logfile**: (既定では C:\rtlog.etl) ログ ファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="2dad4-149">**Logfile**: Name of the log file (C:\rtlog.etl is the default).</span></span>  
  
 <span data-ttu-id="2dad4-150">例:</span><span class="sxs-lookup"><span data-stu-id="2dad4-150">For example:</span></span>  
  
```  
BTAPeopleSoftTrace -transmitter -start -cir 10 -rt C:\log\mylog.etl  
BTAPeopleSoftTrace -transmitter -stop  
```  
  
## <a name="see-also"></a><span data-ttu-id="2dad4-151">参照</span><span class="sxs-lookup"><span data-stu-id="2dad4-151">See Also</span></span>  
 [<span data-ttu-id="2dad4-152">PeopleSoft のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="2dad4-152">Troubleshooting PeopleSoft</span></span>](../core/troubleshooting-peoplesoft.md)