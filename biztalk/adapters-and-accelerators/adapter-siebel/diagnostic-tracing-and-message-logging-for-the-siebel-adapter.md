---
title: 診断トレースとメッセージ ログを Siebel アダプターの |Microsoft ドキュメント
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
ms.openlocfilehash: 0f6b27dd6d169c9ea7e5012be3e03329e6888522
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
ms.locfileid: "26006531"
---
# <a name="diagnostic-tracing-and-message-logging-for-the-siebel-adapter"></a><span data-ttu-id="e8e27-102">診断トレースと Siebel アダプターのメッセージ ログ</span><span class="sxs-lookup"><span data-stu-id="e8e27-102">Diagnostic Tracing and Message Logging for the Siebel adapter</span></span>
<span data-ttu-id="e8e27-103">アダプターのクライアントを効果的に診断アダプターを使用するときに発生する問題の診断トレーシングを有効にできます。</span><span class="sxs-lookup"><span data-stu-id="e8e27-103">Adapter clients can enable diagnostic tracing to effectively diagnose problems encountered while using the adapters.</span></span> <span data-ttu-id="e8e27-104">アダプターのクライアントは、次の 3 つの異なるレベルでトレースをアクティブ化できます。</span><span class="sxs-lookup"><span data-stu-id="e8e27-104">Adapter clients can activate tracing at three different levels:</span></span>  
  
-   <span data-ttu-id="e8e27-105">アダプターのクライアントとアダプター間で</span><span class="sxs-lookup"><span data-stu-id="e8e27-105">Between the adapter client and the adapter</span></span>  
  
-   <span data-ttu-id="e8e27-106">アダプター内</span><span class="sxs-lookup"><span data-stu-id="e8e27-106">Within the adapter</span></span>  
  
-   <span data-ttu-id="e8e27-107">アダプターと基幹業務 (LOB) アプリケーションの間</span><span class="sxs-lookup"><span data-stu-id="e8e27-107">Between the adapter and the line-of-business (LOB) application</span></span>  
  
 <span data-ttu-id="e8e27-108">このセクションでは、これらのレベルでトレースをアクティブ化に関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="e8e27-108">This section provides information about activating tracing at these levels.</span></span>  
  
## <a name="tracing-between-the-adapter-client-and-the-adapter"></a><span data-ttu-id="e8e27-109">アダプターのクライアントとアダプター間でのトレース</span><span class="sxs-lookup"><span data-stu-id="e8e27-109">Tracing between the adapter client and the adapter</span></span>  
 <span data-ttu-id="e8e27-110">アダプターのクライアントは、アダプターのクライアントとアダプター間のトレースの問題への WCF トレースを有効にできます。</span><span class="sxs-lookup"><span data-stu-id="e8e27-110">Adapter clients can enable WCF tracing to trace issues between the adapter client and the adapter.</span></span> <span data-ttu-id="e8e27-111">WCF トレースは、アダプターを WCF サービス モデルを使用してクライアントからの入力 Xml の追跡に使用し、シリアル化の問題を診断する際に便利です。</span><span class="sxs-lookup"><span data-stu-id="e8e27-111">WCF tracing is used to trace the input XMLs coming from the adapter client using the WCF service model and is useful in diagnosing serialization issues.</span></span> <span data-ttu-id="e8e27-112">WCF トレースは、WCF チャネル モデルまたはアダプターのクライアントに、アダプターからの出力メッセージには使用されません。</span><span class="sxs-lookup"><span data-stu-id="e8e27-112">WCF tracing is not used for the WCF channel model or for output messages from the adapter to the adapter client.</span></span> <span data-ttu-id="e8e27-113">それぞれの構成ファイルの抜粋を追加することで、BizTalk アプリケーションと WCF サービス モデルのアプリケーションの WCF トレースをアクティブにできます。</span><span class="sxs-lookup"><span data-stu-id="e8e27-113">You can activate WCF tracing for BizTalk applications and WCF service model applications by adding an excerpt to the respective configuration files.</span></span> <span data-ttu-id="e8e27-114">また、デザイン時と実行時の両方でトレースを有効にできます。</span><span class="sxs-lookup"><span data-stu-id="e8e27-114">Also, you can enable tracing both at design-time and run-time.</span></span>  
  
-   <span data-ttu-id="e8e27-115">**デザイン時にトレース**です。</span><span class="sxs-lookup"><span data-stu-id="e8e27-115">**Tracing at design-time**.</span></span> <span data-ttu-id="e8e27-116">デザイン時機能を使用することは、 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="e8e27-116">For the design-time experience, you may use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], or the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span></span> <span data-ttu-id="e8e27-117">これらすべてのツールを使用できる[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="e8e27-117">All these tools can be used from [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="e8e27-118">そのため、デザイン時の操作のトレースを有効にする必要がありますに追加する抜粋にある devenv.exe.config ファイル*\<インストール ドライブ\>*: \Program Files\Microsoft Visual Studio *\<バージョン\>* \Common7\IDE です。</span><span class="sxs-lookup"><span data-stu-id="e8e27-118">So, to enable tracing for the design-time experience, you must add the excerpt to the devenv.exe.config file located in *\<installation drive\>*:\Program Files\Microsoft Visual Studio *\<version\>* \Common7\IDE.</span></span>  
  
-   <span data-ttu-id="e8e27-119">**実行時にトレース**です。</span><span class="sxs-lookup"><span data-stu-id="e8e27-119">**Tracing at run-time**.</span></span> <span data-ttu-id="e8e27-120">実行時のトレースを使用しているアプリケーションによっては抜粋を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e8e27-120">For run-time tracing, you must add the excerpt depending on the application you are using.</span></span>  
  
    -   <span data-ttu-id="e8e27-121">[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]アプリケーションに BizTalk 構成ファイルで、通常 BTSNTSvc.exe.config の抜粋を追加する必要があります。BizTalk Server のこのファイルは通常 \<インストール ドライブ\>: \Program Files\Microsoft BizTalk Server です。</span><span class="sxs-lookup"><span data-stu-id="e8e27-121">For a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] applications, you must add the excerpt to the BizTalk configuration file, typically BTSNTSvc.exe.config. For BizTalk Server, this file is available typically under \<installation drive\>:\Program Files\Microsoft BizTalk Server.</span></span>  
  
    -   <span data-ttu-id="e8e27-122">WCF サービス モデル .NET アプリケーションのプロジェクトの app.config ファイルの抜粋を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e8e27-122">For a WCF service model .NET application, you must add the excerpt to the app.config file of your project.</span></span>  
  
 <span data-ttu-id="e8e27-123">WCF トレースを有効にするには、内で次の抜粋を追加する必要があります、`<configuration>`タグ。</span><span class="sxs-lookup"><span data-stu-id="e8e27-123">To enable WCF tracing, you must add the following excerpt within the `<configuration>` tag:</span></span>
  
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
  
 <span data-ttu-id="e8e27-124">これは、C:\log\WCFTrace.svclog に WCF トレースを保存します。</span><span class="sxs-lookup"><span data-stu-id="e8e27-124">This saves the WCF traces to C:\log\WCFTrace.svclog.</span></span> <span data-ttu-id="e8e27-125">[WCF トレース](https://msdn.microsoft.com/library/ms730342.aspx)詳細な情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="e8e27-125">[WCF tracing](https://msdn.microsoft.com/library/ms730342.aspx) provides more info.</span></span>
  
> [!IMPORTANT]
>  <span data-ttu-id="e8e27-126">トレースを有効にすると、機密のビジネス データを公開するための潜在的なセキュリティ上の脅威を軽減することを確認してください。</span><span class="sxs-lookup"><span data-stu-id="e8e27-126">Make sure you mitigate potential security threats of exposing sensitive business data by enabling tracing.</span></span> <span data-ttu-id="e8e27-127">参照してください[ベスト プラクティス Siebel アダプターをセキュリティで保護するには](../../adapters-and-accelerators/adapter-siebel/best-practices-to-secure-the-siebel-adapter.md)</span><span class="sxs-lookup"><span data-stu-id="e8e27-127">See [Best practices to secure the Siebel adapter](../../adapters-and-accelerators/adapter-siebel/best-practices-to-secure-the-siebel-adapter.md)</span></span> 
  
## <a name="tracing-within-the-adapter"></a><span data-ttu-id="e8e27-128">アダプターのトレース</span><span class="sxs-lookup"><span data-stu-id="e8e27-128">Tracing Within the Adapter</span></span>  
 <span data-ttu-id="e8e27-129">BizTalk Adapter Pack のアダプターは、エラー、警告、および情報など、トレース ファイルに有用な情報のさまざまなカテゴリをログインします。</span><span class="sxs-lookup"><span data-stu-id="e8e27-129">The adapters in the BizTalk Adapter Pack log different categories of useful information to the trace file such as errors, warnings, and information.</span></span> <span data-ttu-id="e8e27-130">このような情報は、アダプター内のプロセス フローを理解し、アダプターに関する問題の診断に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="e8e27-130">Such information is useful in understanding the process flow within the adapter and diagnosing issues with the adapter.</span></span> <span data-ttu-id="e8e27-131">アクティブ化できます[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]とアダプターが BizTalk アプリケーションと WCF サービスの抜粋をそれぞれの構成ファイルに追加することによってモデル アプリケーション用にトレースされます。</span><span class="sxs-lookup"><span data-stu-id="e8e27-131">You can activate [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] and adapter tracing for BizTalk applications and WCF service model applications by adding an excerpt to the respective configuration files.</span></span> <span data-ttu-id="e8e27-132">また、デザイン時と実行時の両方でトレースを有効にできます。</span><span class="sxs-lookup"><span data-stu-id="e8e27-132">Also, you can enable tracing both at design-time and run-time.</span></span>  
  
-   <span data-ttu-id="e8e27-133">**デザイン時にトレース**です。</span><span class="sxs-lookup"><span data-stu-id="e8e27-133">**Tracing at design-time**.</span></span> <span data-ttu-id="e8e27-134">デザイン時機能を使用することは、 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="e8e27-134">For the design-time experience, you may use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], or the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span></span> <span data-ttu-id="e8e27-135">これらすべてのツールを使用できる[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="e8e27-135">All these tools can be used from [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="e8e27-136">そのため、デザイン時の操作のトレースを有効にする必要がありますに追加する抜粋にある devenv.exe.config ファイル*\<インストール ドライブ\>*: \Program Files\Microsoft Visual Studio *\<バージョン\>* \Common7\IDE です。</span><span class="sxs-lookup"><span data-stu-id="e8e27-136">So, to enable tracing for the design-time experience, you must add the excerpt to the devenv.exe.config file located in *\<installation drive\>*:\Program Files\Microsoft Visual Studio *\<version\>* \Common7\IDE.</span></span>  
  
-   <span data-ttu-id="e8e27-137">**実行時にトレース**です。</span><span class="sxs-lookup"><span data-stu-id="e8e27-137">**Tracing at run-time**.</span></span> <span data-ttu-id="e8e27-138">実行時のトレースを使用しているアプリケーションによっては抜粋を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e8e27-138">For run-time tracing, you must add the excerpt depending on the application you are using.</span></span>  
  
    -   <span data-ttu-id="e8e27-139">[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]アプリケーションに BizTalk 構成ファイルで、通常 BTSNTSvc.exe.config の抜粋を追加する必要があります。BizTalk Server のこのファイルは通常 \<インストール ドライブ\>: \Program Files\Microsoft BizTalk Server です。</span><span class="sxs-lookup"><span data-stu-id="e8e27-139">For a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] applications, you must add the excerpt to the BizTalk configuration file, typically BTSNTSvc.exe.config. For BizTalk Server, this file is available typically under \<installation drive\>:\Program Files\Microsoft BizTalk Server.</span></span>  
  
    -   <span data-ttu-id="e8e27-140">WCF サービス モデル .NET アプリケーションのプロジェクトの app.config ファイルの抜粋を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e8e27-140">For a WCF service model .NET application, you must add the excerpt to the app.config file of your project.</span></span>  
  
 <span data-ttu-id="e8e27-141">有効にする[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]とアダプターのトレース、内で次の抜粋を追加する必要があります、`<configuration>`タグ。</span><span class="sxs-lookup"><span data-stu-id="e8e27-141">To enable [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] and adapter tracing, you must add the following excerpt within the `<configuration>` tag:</span></span>  
  
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
  
 <span data-ttu-id="e8e27-142">これでは、WCF トレースを C:\log\AdapterTrace.svclog に保存します。</span><span class="sxs-lookup"><span data-stu-id="e8e27-142">This would save the WCF traces to C:\log\AdapterTrace.svclog.</span></span>  
  
## <a name="tracing-between-the-adapter-and-the-lob-application"></a><span data-ttu-id="e8e27-143">アダプターと LOB アプリケーション間でのトレース</span><span class="sxs-lookup"><span data-stu-id="e8e27-143">Tracing Between the Adapter and the LOB Application</span></span>  
 <span data-ttu-id="e8e27-144">アダプターと LOB アプリケーション内で疑いがある問題を診断する LOB アプリケーション間の通信のトレースを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e8e27-144">You must enable tracing for communication between the adapter and the LOB application to diagnose issues you suspect within the LOB application.</span></span> <span data-ttu-id="e8e27-145">アダプターは、この情報にアクセスする (クライアントとサーバー側) をトレース LOB によっても異なります。</span><span class="sxs-lookup"><span data-stu-id="e8e27-145">Adapters also depend on LOB tracing (client/server side) to get access to this information.</span></span> <span data-ttu-id="e8e27-146">オンにする LOB トレースの詳細については、このドキュメントから除外されます。</span><span class="sxs-lookup"><span data-stu-id="e8e27-146">The specifics of turning on LOB tracing are excluded from this document.</span></span>  
  
 <span data-ttu-id="e8e27-147">さらに、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]バインディング プロパティを提供 (**ログデータ**) に設定した場合どの**True**トレース レベルに設定されている場合と**Verbose**、 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]アダプターと Siebel システム間で情報のフローをログに記録します。</span><span class="sxs-lookup"><span data-stu-id="e8e27-147">Additionally, the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] provides a binding property (**LogData**), which if set to **True** and if the trace level is set to **Verbose**, the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] logs the information flow between the adapter and the Siebel system.</span></span> <span data-ttu-id="e8e27-148">この情報は、同じトレース ファイルでアダプターのトレースと共に記録されます。</span><span class="sxs-lookup"><span data-stu-id="e8e27-148">This information is logged along with the adapter traces in the same trace file.</span></span>  
  
 <span data-ttu-id="e8e27-149">このバインドのプロパティの詳細については、次を参照してください。 [BizTalk Adapter for Siebel のバインド プロパティ読む](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md)です。</span><span class="sxs-lookup"><span data-stu-id="e8e27-149">For more information about this binding property, see [Read about BizTalk Adapter for Siebel Binding Properties](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md).</span></span>  
  
## <a name="viewing-the-traces"></a><span data-ttu-id="e8e27-150">トレースの表示</span><span class="sxs-lookup"><span data-stu-id="e8e27-150">Viewing the Traces</span></span>  
 <span data-ttu-id="e8e27-151">Windows Communication Foundation (WCF) サービス トレース ビューアー ツールを使用するには、トレースを表示します。</span><span class="sxs-lookup"><span data-stu-id="e8e27-151">You can use the Windows Communication Foundation (WCF) Service Trace Viewer tool to view the traces.</span></span> <span data-ttu-id="e8e27-152">ツールの詳細については、次を参照してください。[相関トレースの表示とトラブルシューティング サービス トレース ビューアーを使用して](https://msdn.microsoft.com/library/aa751795.aspx)です。</span><span class="sxs-lookup"><span data-stu-id="e8e27-152">For more information about the tool, see [Using Service Trace Viewer for Viewing Correlated Traces and Troubleshooting](https://msdn.microsoft.com/library/aa751795.aspx).</span></span>  
  
## <a name="configuring-tracking-for-biztalk-applications"></a><span data-ttu-id="e8e27-153">BizTalk アプリケーションの追跡の構成</span><span class="sxs-lookup"><span data-stu-id="e8e27-153">Configuring Tracking for BizTalk Applications</span></span>  
 <span data-ttu-id="e8e27-154">BizTalk 管理コンソールを使用すると、受信ポート、送信ポートなどのさまざまな追跡オプションを構成できます。</span><span class="sxs-lookup"><span data-stu-id="e8e27-154">The BizTalk Administration Console enables you to configure various tracking options for things such as send ports, receive ports.</span></span> <span data-ttu-id="e8e27-155">追跡構成設定を有効にすると、受信/送信イベント データ、メッセージのプロパティ、メッセージ本文、およびオーケストレーションを追跡します。</span><span class="sxs-lookup"><span data-stu-id="e8e27-155">The tracking configuration settings enable you to track inbound/outbound event data, message properties, message bodies, and orchestrations.</span></span> <span data-ttu-id="e8e27-156">BizTalk アプリケーションの追跡の構成の詳細については、次を参照してください。[成果物の管理](../../core/managing-artifacts.md)です。</span><span class="sxs-lookup"><span data-stu-id="e8e27-156">For more information about configuring tracking for BizTalk applications, see [Managing Artifacts](../../core/managing-artifacts.md).</span></span>
  
<span data-ttu-id="e8e27-157">グループ ハブを使用することもできます。[追跡メッセージを表示し、インスタンス データ](../../core/viewing-tracked-message-and-instance-data.md)追跡チェックリストについては、およびベスト プラクティスを含め、します。</span><span class="sxs-lookup"><span data-stu-id="e8e27-157">You can also use Group Hub to [Viewing Tracked Message and Instance Data](../../core/viewing-tracked-message-and-instance-data.md), including a tracking checklist, and best practices.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="e8e27-158">参照</span><span class="sxs-lookup"><span data-stu-id="e8e27-158">See Also</span></span>  
[<span data-ttu-id="e8e27-159">Siebel アダプターをトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="e8e27-159">Troubleshoot the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/troubleshoot-the-siebel-adapter.md)