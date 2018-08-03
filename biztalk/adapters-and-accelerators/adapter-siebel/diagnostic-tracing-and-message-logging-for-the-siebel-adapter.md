---
title: 診断トレースとメッセージの Siebel アダプターのログ記録 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- tracing, between the adapter client and the adapter
- logging, troubleshooting
- troubleshooting, tracing and message logging
- tracing, between the adapter and the LOB application
- message logging, troubleshooting
- tracing, troubleshooting
ms.assetid: fd2de692-45b7-45bc-b79c-381f3b1cf592
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5ab369a74058f374ee229eb25d0697dc96f539ed
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994579"
---
# <a name="diagnostic-tracing-and-message-logging-for-the-siebel-adapter"></a><span data-ttu-id="a1701-102">診断トレースとメッセージ ログの Siebel アダプターの</span><span class="sxs-lookup"><span data-stu-id="a1701-102">Diagnostic Tracing and Message Logging for the Siebel adapter</span></span>
<span data-ttu-id="a1701-103">アダプター クライアントには、実質的に、アダプターの使用時に発生する問題を診断する診断トレースが有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="a1701-103">Adapter clients can enable diagnostic tracing to effectively diagnose problems encountered while using the adapters.</span></span> <span data-ttu-id="a1701-104">アダプター クライアントは、次の 3 つの異なるレベルでトレースをアクティブ化できます。</span><span class="sxs-lookup"><span data-stu-id="a1701-104">Adapter clients can activate tracing at three different levels:</span></span>  
  
- <span data-ttu-id="a1701-105">アダプターのクライアントとアダプターの間</span><span class="sxs-lookup"><span data-stu-id="a1701-105">Between the adapter client and the adapter</span></span>  
  
- <span data-ttu-id="a1701-106">アダプター内</span><span class="sxs-lookup"><span data-stu-id="a1701-106">Within the adapter</span></span>  
  
- <span data-ttu-id="a1701-107">アダプターと基幹業務 (LOB) アプリケーションの間</span><span class="sxs-lookup"><span data-stu-id="a1701-107">Between the adapter and the line-of-business (LOB) application</span></span>  
  
  <span data-ttu-id="a1701-108">このセクションでは、これらのレベルでトレースをアクティブ化についての情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="a1701-108">This section provides information about activating tracing at these levels.</span></span>  
  
## <a name="tracing-between-the-adapter-client-and-the-adapter"></a><span data-ttu-id="a1701-109">アダプターのクライアントと、アダプターのトレース</span><span class="sxs-lookup"><span data-stu-id="a1701-109">Tracing between the adapter client and the adapter</span></span>  
 <span data-ttu-id="a1701-110">アダプター クライアントには、アダプターのクライアントとアダプター間のトレースの問題に WCF トレースが有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="a1701-110">Adapter clients can enable WCF tracing to trace issues between the adapter client and the adapter.</span></span> <span data-ttu-id="a1701-111">WCF のトレースはアダプターを WCF サービス モデルを使用してクライアントからの入力 Xml をトレースするために使用し、シリアル化の問題の診断に役立つ。</span><span class="sxs-lookup"><span data-stu-id="a1701-111">WCF tracing is used to trace the input XMLs coming from the adapter client using the WCF service model and is useful in diagnosing serialization issues.</span></span> <span data-ttu-id="a1701-112">WCF トレースは、WCF チャネル モデルまたはアダプター クライアントにアダプターからの出力メッセージには使用されません。</span><span class="sxs-lookup"><span data-stu-id="a1701-112">WCF tracing is not used for the WCF channel model or for output messages from the adapter to the adapter client.</span></span> <span data-ttu-id="a1701-113">抜粋をそれぞれの構成ファイルに追加することで、BizTalk アプリケーションと WCF サービス モデルのアプリケーションの WCF トレースをアクティブにできます。</span><span class="sxs-lookup"><span data-stu-id="a1701-113">You can activate WCF tracing for BizTalk applications and WCF service model applications by adding an excerpt to the respective configuration files.</span></span> <span data-ttu-id="a1701-114">また、デザイン時と実行時の両方のトレースを有効にできます。</span><span class="sxs-lookup"><span data-stu-id="a1701-114">Also, you can enable tracing both at design-time and run-time.</span></span>  
  
- <span data-ttu-id="a1701-115">**デザイン時トレース**します。</span><span class="sxs-lookup"><span data-stu-id="a1701-115">**Tracing at design-time**.</span></span> <span data-ttu-id="a1701-116">デザイン時動作は、使用することがあります、 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="a1701-116">For the design-time experience, you may use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], or the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span></span> <span data-ttu-id="a1701-117">これらすべてのツールから使用できる[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="a1701-117">All these tools can be used from [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="a1701-118">そのため、デザイン時エクスペリエンスのトレースを有効にする必要がありますに追加する抜粋にある devenv.exe.config ファイル*\<インストール ドライブ\>*: Visual Studio \Program Files\Microsoft *\<バージョン\>* \Common7\IDE です。</span><span class="sxs-lookup"><span data-stu-id="a1701-118">So, to enable tracing for the design-time experience, you must add the excerpt to the devenv.exe.config file located in *\<installation drive\>*:\Program Files\Microsoft Visual Studio *\<version\>* \Common7\IDE.</span></span>  
  
- <span data-ttu-id="a1701-119">**実行時にトレース**します。</span><span class="sxs-lookup"><span data-stu-id="a1701-119">**Tracing at run-time**.</span></span> <span data-ttu-id="a1701-120">実行時のトレースを使用するアプリケーションに応じて抜粋を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a1701-120">For run-time tracing, you must add the excerpt depending on the application you are using.</span></span>  
  
  - <span data-ttu-id="a1701-121">[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]アプリケーションでは、BizTalk 構成ファイルで、通常は BTSNTSvc.exe.config に抜粋を追加する必要があります。BizTalk server では、このファイルは通常で使用可能な\<インストール ドライブ\>: \Program Files\Microsoft BizTalk Server です。</span><span class="sxs-lookup"><span data-stu-id="a1701-121">For a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] applications, you must add the excerpt to the BizTalk configuration file, typically BTSNTSvc.exe.config. For BizTalk Server, this file is available typically under \<installation drive\>:\Program Files\Microsoft BizTalk Server.</span></span>  
  
  - <span data-ttu-id="a1701-122">WCF サービス モデル .NET アプリケーションのプロジェクトの app.config ファイルに抜粋を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a1701-122">For a WCF service model .NET application, you must add the excerpt to the app.config file of your project.</span></span>  
  
  <span data-ttu-id="a1701-123">WCF トレースを有効にするには、内の次の抜粋を追加する必要があります、`<configuration>`タグ。</span><span class="sxs-lookup"><span data-stu-id="a1701-123">To enable WCF tracing, you must add the following excerpt within the `<configuration>` tag:</span></span>
  
```  
<system.diagnostics>  
    <sources>  
      <source name ="System.ServiceModel" switchValue="Verbose">  
        <listeners>  
          <add name="xml" />  
        </listeners>  
      </source>  
      <source name ="System.ServiceModel.MessageLogging"   
              switchValue="Verbose, ActivityTracing">          
        <listeners>  
          <add name="xml" />  
        </listeners>  
      </source>  
      <source name ="System.Runtime.Serialization" switchValue="Verbose">  
        <listeners>  
          <add name="xml" />  
        </listeners>  
      </source>  
   </sources>  
   <sharedListeners>  
      <add name="xml" type="System.Diagnostics.XmlWriterTraceListener"                
           traceOutputOptions="LogicalOperationStack"   
           initializeData="C:\log\WCFTrace.svclog" />  
   </sharedListeners>  
   <trace autoflush="true" />  
  </system.diagnostics>  
  <system.serviceModel>  
    <diagnostics>  
      <messageLogging   
           logEntireMessage="true"   
           logMalformedMessages="false"  
           logMessagesAtServiceLevel="true"   
           logMessagesAtTransportLevel="false"/>  
    </diagnostics>      
  </system.serviceModel>  
```  
  
 <span data-ttu-id="a1701-124">これにより、WCF トレースが C:\log\WCFTrace.svclog を保存します。</span><span class="sxs-lookup"><span data-stu-id="a1701-124">This saves the WCF traces to C:\log\WCFTrace.svclog.</span></span> <span data-ttu-id="a1701-125">[WCF トレース](https://msdn.microsoft.com/library/ms730342.aspx)詳細情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="a1701-125">[WCF tracing](https://msdn.microsoft.com/library/ms730342.aspx) provides more info.</span></span>
  
> [!IMPORTANT]
>  <span data-ttu-id="a1701-126">トレースを有効にすると、機密性の高いビジネス データを公開することの潜在的なセキュリティ脅威を軽減することを確認します。</span><span class="sxs-lookup"><span data-stu-id="a1701-126">Make sure you mitigate potential security threats of exposing sensitive business data by enabling tracing.</span></span> <span data-ttu-id="a1701-127">参照してください[ベスト プラクティス、Siebel アダプターをセキュリティで保護するには](../../adapters-and-accelerators/adapter-siebel/best-practices-to-secure-the-siebel-adapter.md)</span><span class="sxs-lookup"><span data-stu-id="a1701-127">See [Best practices to secure the Siebel adapter](../../adapters-and-accelerators/adapter-siebel/best-practices-to-secure-the-siebel-adapter.md)</span></span> 
  
## <a name="tracing-within-the-adapter"></a><span data-ttu-id="a1701-128">アダプターのトレース</span><span class="sxs-lookup"><span data-stu-id="a1701-128">Tracing Within the Adapter</span></span>  
 <span data-ttu-id="a1701-129">BizTalk Adapter Pack アダプターでは、さまざまなカテゴリの有用な情報をエラー、警告、および情報など、トレース ファイルにログインします。</span><span class="sxs-lookup"><span data-stu-id="a1701-129">The adapters in the BizTalk Adapter Pack log different categories of useful information to the trace file such as errors, warnings, and information.</span></span> <span data-ttu-id="a1701-130">このような情報は、アダプターの処理フローを理解し、アダプターに関する問題の診断に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="a1701-130">Such information is useful in understanding the process flow within the adapter and diagnosing issues with the adapter.</span></span> <span data-ttu-id="a1701-131">アクティブ化できます[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]とアダプターの BizTalk アプリケーションと WCF の抜粋をそれぞれの構成ファイルに追加することでモデルのアプリケーションをサービスのトレースします。</span><span class="sxs-lookup"><span data-stu-id="a1701-131">You can activate [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] and adapter tracing for BizTalk applications and WCF service model applications by adding an excerpt to the respective configuration files.</span></span> <span data-ttu-id="a1701-132">また、デザイン時と実行時の両方のトレースを有効にできます。</span><span class="sxs-lookup"><span data-stu-id="a1701-132">Also, you can enable tracing both at design-time and run-time.</span></span>  
  
- <span data-ttu-id="a1701-133">**デザイン時トレース**します。</span><span class="sxs-lookup"><span data-stu-id="a1701-133">**Tracing at design-time**.</span></span> <span data-ttu-id="a1701-134">デザイン時動作は、使用することがあります、 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="a1701-134">For the design-time experience, you may use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], or the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span></span> <span data-ttu-id="a1701-135">これらすべてのツールから使用できる[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="a1701-135">All these tools can be used from [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="a1701-136">そのため、デザイン時エクスペリエンスのトレースを有効にする必要がありますに追加する抜粋にある devenv.exe.config ファイル*\<インストール ドライブ\>*: Visual Studio \Program Files\Microsoft *\<バージョン\>* \Common7\IDE です。</span><span class="sxs-lookup"><span data-stu-id="a1701-136">So, to enable tracing for the design-time experience, you must add the excerpt to the devenv.exe.config file located in *\<installation drive\>*:\Program Files\Microsoft Visual Studio *\<version\>* \Common7\IDE.</span></span>  
  
- <span data-ttu-id="a1701-137">**実行時にトレース**します。</span><span class="sxs-lookup"><span data-stu-id="a1701-137">**Tracing at run-time**.</span></span> <span data-ttu-id="a1701-138">実行時のトレースを使用するアプリケーションに応じて抜粋を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a1701-138">For run-time tracing, you must add the excerpt depending on the application you are using.</span></span>  
  
  - <span data-ttu-id="a1701-139">[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]アプリケーションでは、BizTalk 構成ファイルで、通常は BTSNTSvc.exe.config に抜粋を追加する必要があります。BizTalk server では、このファイルは通常で使用可能な\<インストール ドライブ\>: \Program Files\Microsoft BizTalk Server です。</span><span class="sxs-lookup"><span data-stu-id="a1701-139">For a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] applications, you must add the excerpt to the BizTalk configuration file, typically BTSNTSvc.exe.config. For BizTalk Server, this file is available typically under \<installation drive\>:\Program Files\Microsoft BizTalk Server.</span></span>  
  
  - <span data-ttu-id="a1701-140">WCF サービス モデル .NET アプリケーションのプロジェクトの app.config ファイルに抜粋を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a1701-140">For a WCF service model .NET application, you must add the excerpt to the app.config file of your project.</span></span>  
  
  <span data-ttu-id="a1701-141">有効にする[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]とアダプターのトレース、内の次の抜粋を追加する必要があります、`<configuration>`タグ。</span><span class="sxs-lookup"><span data-stu-id="a1701-141">To enable [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] and adapter tracing, you must add the following excerpt within the `<configuration>` tag:</span></span>  
  
```  
<system.diagnostics>  
    <sources>  
      <source name="Microsoft.ServiceModel.Channels" switchValue="Error">  
        <listeners>  
          <add name="xml" />  
        </listeners>  
      </source>  
      <source name="Microsoft.Adapters.Siebel" switchValue="Information">  
        <listeners>  
          <add name="xml" />  
        </listeners>  
      </source>  
    </sources>  
    <sharedListeners>  
      <add name="xml" type="System.Diagnostics.XmlWriterTraceListener"   
   traceOutputOptions="LogicalOperationStack"   
          initializeData="C:\log\AdapterTrace.svclog" />  
    </sharedListeners>  
    <trace autoflush="true" />  
  </system.diagnostics>  
```  
  
 <span data-ttu-id="a1701-142">これでは、WCF トレースを C:\log\AdapterTrace.svclog に保存します。</span><span class="sxs-lookup"><span data-stu-id="a1701-142">This would save the WCF traces to C:\log\AdapterTrace.svclog.</span></span>  
  
## <a name="tracing-between-the-adapter-and-the-lob-application"></a><span data-ttu-id="a1701-143">アダプターと LOB アプリケーション間でのトレース</span><span class="sxs-lookup"><span data-stu-id="a1701-143">Tracing Between the Adapter and the LOB Application</span></span>  
 <span data-ttu-id="a1701-144">アダプターと LOB アプリケーション内で疑いがある問題を診断する LOB アプリケーション間の通信のトレースを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a1701-144">You must enable tracing for communication between the adapter and the LOB application to diagnose issues you suspect within the LOB application.</span></span> <span data-ttu-id="a1701-145">アダプターは、この情報へのアクセスを取得する (クライアント/サーバー側) のトレース LOB によっても異なります。</span><span class="sxs-lookup"><span data-stu-id="a1701-145">Adapters also depend on LOB tracing (client/server side) to get access to this information.</span></span> <span data-ttu-id="a1701-146">LOB のトレースの有効化の詳細については、このドキュメントから除外されます。</span><span class="sxs-lookup"><span data-stu-id="a1701-146">The specifics of turning on LOB tracing are excluded from this document.</span></span>  
  
 <span data-ttu-id="a1701-147">さらに、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]バインドのプロパティを提供します (**ログデータ**) に設定する場合**True**トレース レベル設定されている場合と**Verbose**、 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]アダプターと Siebel システム間の情報フローのログを記録します。</span><span class="sxs-lookup"><span data-stu-id="a1701-147">Additionally, the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] provides a binding property (**LogData**), which if set to **True** and if the trace level is set to **Verbose**, the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] logs the information flow between the adapter and the Siebel system.</span></span> <span data-ttu-id="a1701-148">この情報は、同じトレース ファイルにアダプターのトレースと共に記録されます。</span><span class="sxs-lookup"><span data-stu-id="a1701-148">This information is logged along with the adapter traces in the same trace file.</span></span>  
  
 <span data-ttu-id="a1701-149">このバインドのプロパティの詳細については、次を参照してください。 [for Siebel のバインド プロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md)します。</span><span class="sxs-lookup"><span data-stu-id="a1701-149">For more information about this binding property, see [Read about BizTalk Adapter for Siebel Binding Properties](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md).</span></span>  
  
## <a name="viewing-the-traces"></a><span data-ttu-id="a1701-150">トレースを表示します。</span><span class="sxs-lookup"><span data-stu-id="a1701-150">Viewing the Traces</span></span>  
 <span data-ttu-id="a1701-151">Windows Communication Foundation (WCF) サービス トレース ビューアー ツールを使用するには、トレースを表示します。</span><span class="sxs-lookup"><span data-stu-id="a1701-151">You can use the Windows Communication Foundation (WCF) Service Trace Viewer tool to view the traces.</span></span> <span data-ttu-id="a1701-152">ツールの詳細については、次を参照してください。[相関トレースの表示とトラブルシューティングのサービス トレース ビューアーを使用して](https://msdn.microsoft.com/library/aa751795.aspx)します。</span><span class="sxs-lookup"><span data-stu-id="a1701-152">For more information about the tool, see [Using Service Trace Viewer for Viewing Correlated Traces and Troubleshooting](https://msdn.microsoft.com/library/aa751795.aspx).</span></span>  
  
## <a name="configuring-tracking-for-biztalk-applications"></a><span data-ttu-id="a1701-153">BizTalk アプリケーションの追跡の構成</span><span class="sxs-lookup"><span data-stu-id="a1701-153">Configuring Tracking for BizTalk Applications</span></span>  
 <span data-ttu-id="a1701-154">BizTalk 管理コンソールでは受信ポートは、送信ポートなどのさまざまな追跡オプションを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="a1701-154">The BizTalk Administration Console enables you to configure various tracking options for things such as send ports, receive ports.</span></span> <span data-ttu-id="a1701-155">追跡の構成設定を使用すると、受信/送信イベント データ、メッセージのプロパティ、メッセージ本文、およびオーケストレーションを追跡します。</span><span class="sxs-lookup"><span data-stu-id="a1701-155">The tracking configuration settings enable you to track inbound/outbound event data, message properties, message bodies, and orchestrations.</span></span> <span data-ttu-id="a1701-156">BizTalk アプリケーションの追跡を構成する方法の詳細については、次を参照してください。[管理成果物](../../core/managing-artifacts.md)します。</span><span class="sxs-lookup"><span data-stu-id="a1701-156">For more information about configuring tracking for BizTalk applications, see [Managing Artifacts](../../core/managing-artifacts.md).</span></span>
  
<span data-ttu-id="a1701-157">グループ ハブを使用することもできます。[追跡メッセージを表示し、インスタンス データ](../../core/viewing-tracked-message-and-instance-data.md)追跡チェックリスト、およびベスト プラクティスなど。</span><span class="sxs-lookup"><span data-stu-id="a1701-157">You can also use Group Hub to [Viewing Tracked Message and Instance Data](../../core/viewing-tracked-message-and-instance-data.md), including a tracking checklist, and best practices.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a1701-158">参照</span><span class="sxs-lookup"><span data-stu-id="a1701-158">See Also</span></span>  
[<span data-ttu-id="a1701-159">Siebel アダプターをトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="a1701-159">Troubleshoot the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/troubleshoot-the-siebel-adapter.md)