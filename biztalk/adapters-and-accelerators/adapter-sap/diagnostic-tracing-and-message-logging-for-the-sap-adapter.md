---
title: "診断トレースとメッセージ ログを SAP アダプターの |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- tracing, between the adapter client and adapter
- tracing, within the adapter
- tracing, between the adapter and the LOB application
- troubleshooting, tracing and logging
ms.assetid: 5c60af54-896d-4873-acbf-32fbcd051ee2
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: beb5565141521c08e295a9d5cee88406c16df7de
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="diagnostic-tracing-and-message-logging-for-the-sap-adapter"></a><span data-ttu-id="6445a-102">診断トレースと SAP アダプターのメッセージ ログ</span><span class="sxs-lookup"><span data-stu-id="6445a-102">Diagnostic Tracing and Message Logging for the SAP adapter</span></span>
<span data-ttu-id="6445a-103">診断トレースは、効果的にアダプターを使用するときに発生する可能性がある問題を診断するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="6445a-103">Diagnostic tracing helps to effectively diagnose problems that you might encounter when using the adapters.</span></span> <span data-ttu-id="6445a-104">アダプターのクライアントは、3 つのレベルでの診断のトレースをアクティブ化できます。</span><span class="sxs-lookup"><span data-stu-id="6445a-104">Adapter clients can activate diagnostic tracing at three levels:</span></span>  
  
-   <span data-ttu-id="6445a-105">アダプターのクライアントとアダプター間で</span><span class="sxs-lookup"><span data-stu-id="6445a-105">Between the adapter client and the adapter</span></span>  
  
-   <span data-ttu-id="6445a-106">アダプター内</span><span class="sxs-lookup"><span data-stu-id="6445a-106">Within the adapter</span></span>  
  
-   <span data-ttu-id="6445a-107">アダプターと基幹業務 (LOB) アプリケーションの間</span><span class="sxs-lookup"><span data-stu-id="6445a-107">Between the adapter and the line-of-business (LOB) application</span></span>  
  
 <span data-ttu-id="6445a-108">このセクションでは、これらのレベルでトレースをアクティブ化に関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="6445a-108">This section provides information about activating tracing at these levels.</span></span>  
  
## <a name="tracing-between-the-adapter-client-and-the-adapter"></a><span data-ttu-id="6445a-109">アダプターのクライアントとアダプター間でのトレース</span><span class="sxs-lookup"><span data-stu-id="6445a-109">Tracing Between the Adapter Client and the Adapter</span></span>  
 <span data-ttu-id="6445a-110">アダプターのクライアントは、アダプターのクライアントとアダプター間のトレースの問題への WCF トレースを有効にできます。</span><span class="sxs-lookup"><span data-stu-id="6445a-110">Adapter clients can enable WCF tracing to trace issues between the adapter client and the adapter.</span></span> <span data-ttu-id="6445a-111">WCF トレースは、WCF サービス モデルを使用して、アダプターのクライアントから取得し、シリアル化の問題の診断に役立つは入力 XML の追跡に使用します。</span><span class="sxs-lookup"><span data-stu-id="6445a-111">WCF tracing is used to trace the input XML that comes from the adapter client by using the WCF service model and is useful in diagnosing serialization issues.</span></span> <span data-ttu-id="6445a-112">WCF トレースは、WCF チャネル モデルまたはアダプターのクライアントに、アダプターからの出力メッセージには使用されません。</span><span class="sxs-lookup"><span data-stu-id="6445a-112">WCF tracing is not used for the WCF channel model or for output messages from the adapter to the adapter client.</span></span> <span data-ttu-id="6445a-113">それぞれの構成ファイルの抜粋を追加することで、BizTalk アプリケーションと WCF サービス モデルのアプリケーションの WCF トレースをアクティブにできます。</span><span class="sxs-lookup"><span data-stu-id="6445a-113">You can activate WCF tracing for BizTalk applications and WCF service model applications by adding an excerpt to the respective configuration files.</span></span> <span data-ttu-id="6445a-114">また、デザイン時と実行時の両方でトレースを有効にできます。</span><span class="sxs-lookup"><span data-stu-id="6445a-114">Also, you can enable tracing both at design-time and run-time.</span></span>  
  
-   <span data-ttu-id="6445a-115">**デザイン時にトレース**です。</span><span class="sxs-lookup"><span data-stu-id="6445a-115">**Tracing at design-time**.</span></span> <span data-ttu-id="6445a-116">デザイン時機能を使用することは、 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="6445a-116">For the design-time experience, you may use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], or the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span></span> <span data-ttu-id="6445a-117">これらすべてのツールを使用できる[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="6445a-117">All these tools can be used from [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="6445a-118">そのため、デザイン時の操作のトレースを有効にする必要がありますに追加する抜粋にある devenv.exe.config ファイル*\<インストール ドライブ\>*: \Program Files\Microsoft Visual Studio *\<バージョン\>*\Common7\IDE です。</span><span class="sxs-lookup"><span data-stu-id="6445a-118">So, to enable tracing for the design-time experience, you must add the excerpt to the devenv.exe.config file located in *\<installation drive\>*:\Program Files\Microsoft Visual Studio *\<version\>*\Common7\IDE.</span></span>  
  
-   <span data-ttu-id="6445a-119">**実行時にトレース**です。</span><span class="sxs-lookup"><span data-stu-id="6445a-119">**Tracing at run-time**.</span></span> <span data-ttu-id="6445a-120">実行時のトレースを使用しているアプリケーションによっては抜粋を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6445a-120">For run-time tracing, you must add the excerpt depending on the application you are using.</span></span>  
  
    -   <span data-ttu-id="6445a-121">[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]アプリケーションに BizTalk 構成ファイルで、通常 BTSNTSvc.exe.config の抜粋を追加する必要があります。BizTalk Server のこのファイルは通常 \<インストール ドライブ\>: \Program Files\Microsoft BizTalk Server です。</span><span class="sxs-lookup"><span data-stu-id="6445a-121">For a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] applications, you must add the excerpt to the BizTalk configuration file, typically BTSNTSvc.exe.config. For BizTalk Server, this file is available typically under \<installation drive\>:\Program Files\Microsoft BizTalk Server.</span></span>  
  
    -   <span data-ttu-id="6445a-122">WCF サービス モデル .NET アプリケーションのプロジェクトの app.config ファイルの抜粋を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6445a-122">For a WCF service model .NET application, you must add the excerpt to the app.config file of your project.</span></span>  
  
 <span data-ttu-id="6445a-123">WCF トレースを有効にするには、内で次の抜粋を追加、`<configuration>`タグ。</span><span class="sxs-lookup"><span data-stu-id="6445a-123">To enable WCF tracing, add the following excerpt within the `<configuration>` tag.</span></span>  
  
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
  
 <span data-ttu-id="6445a-124">これは、C:\log\WCFTrace.svclog に WCF トレースを保存します。</span><span class="sxs-lookup"><span data-stu-id="6445a-124">This saves the WCF traces to C:\log\WCFTrace.svclog.</span></span> <span data-ttu-id="6445a-125">WCF トレースの詳細については、次を参照してください。[トレース](https://msdn.microsoft.com/library/ms730342.aspx)です。</span><span class="sxs-lookup"><span data-stu-id="6445a-125">For more information about WCF tracing, see [Tracing](https://msdn.microsoft.com/library/ms730342.aspx).</span></span> 
  
> [!IMPORTANT]
>  <span data-ttu-id="6445a-126">トレースを有効にすると、機密のビジネス データを公開するための潜在的なセキュリティ上の脅威を軽減することを確認してください。</span><span class="sxs-lookup"><span data-stu-id="6445a-126">Make sure you mitigate potential security threats of exposing sensitive business data by enabling tracing.</span></span> <span data-ttu-id="6445a-127">推奨事項を参照してください[ベスト プラクティス、SAP アダプターをセキュリティで保護する](../../adapters-and-accelerators/adapter-sap/best-practices-to-secure-the-sap-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="6445a-127">For recommendations see [Best practices to secure the SAP adapter](../../adapters-and-accelerators/adapter-sap/best-practices-to-secure-the-sap-adapter.md).</span></span>  
  
## <a name="tracing-within-the-adapter"></a><span data-ttu-id="6445a-128">アダプターのトレース</span><span class="sxs-lookup"><span data-stu-id="6445a-128">Tracing Within the Adapter</span></span>  
 <span data-ttu-id="6445a-129">アダプターは、エラー、警告、および情報メッセージなど、トレース ファイルに有用な情報のさまざまなカテゴリをログオンします。</span><span class="sxs-lookup"><span data-stu-id="6445a-129">The adapters log different categories of useful information to the trace file such as errors, warnings, and information messages.</span></span> <span data-ttu-id="6445a-130">このような情報は、アダプター内のプロセス フローを理解し、アダプターに関する問題の診断に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="6445a-130">Such information is useful in understanding the process flow within the adapter and diagnosing issues with the adapter.</span></span> <span data-ttu-id="6445a-131">アクティブ化することができます、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]とアダプターが BizTalk アプリケーションと WCF サービスの抜粋をそれぞれの構成ファイルに追加することによってモデル アプリケーション用にトレースされます。</span><span class="sxs-lookup"><span data-stu-id="6445a-131">You can activate the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] and adapter tracing for BizTalk applications and WCF service model applications by adding an excerpt to the respective configuration files.</span></span> <span data-ttu-id="6445a-132">また、デザイン時と実行時の両方でトレースを有効にできます。</span><span class="sxs-lookup"><span data-stu-id="6445a-132">Also, you can enable tracing both at design-time and run-time.</span></span>  
  
-   <span data-ttu-id="6445a-133">**デザイン時にトレース**です。</span><span class="sxs-lookup"><span data-stu-id="6445a-133">**Tracing at design-time**.</span></span> <span data-ttu-id="6445a-134">デザイン時機能を使用することは、 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="6445a-134">For the design-time experience, you may use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], or the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span></span> <span data-ttu-id="6445a-135">これらすべてのツールを使用できる[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="6445a-135">All these tools can be used from [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="6445a-136">そのため、デザイン時の操作のトレースを有効にする必要がありますに追加する抜粋にある devenv.exe.config ファイル*\<インストール ドライブ\>*: \Program Files\Microsoft Visual Studio *\<バージョン\>*\Common7\IDE です。</span><span class="sxs-lookup"><span data-stu-id="6445a-136">So, to enable tracing for the design-time experience, you must add the excerpt to the devenv.exe.config file located in *\<installation drive\>*:\Program Files\Microsoft Visual Studio *\<version\>*\Common7\IDE.</span></span>  
  
-   <span data-ttu-id="6445a-137">**実行時にトレース**です。</span><span class="sxs-lookup"><span data-stu-id="6445a-137">**Tracing at run-time**.</span></span> <span data-ttu-id="6445a-138">実行時のトレースを使用しているアプリケーションによっては抜粋を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6445a-138">For run-time tracing, you must add the excerpt depending on the application you are using.</span></span>  
  
    -   <span data-ttu-id="6445a-139">[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]アプリケーションに BizTalk 構成ファイルで、通常 BTSNTSvc.exe.config の抜粋を追加する必要があります。BizTalk Server のこのファイルは通常 \<インストール ドライブ\>: \Program Files\Microsoft BizTalk Server です。</span><span class="sxs-lookup"><span data-stu-id="6445a-139">For a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] applications, you must add the excerpt to the BizTalk configuration file, typically BTSNTSvc.exe.config. For BizTalk Server, this file is available typically under \<installation drive\>:\Program Files\Microsoft BizTalk Server.</span></span>  
  
    -   <span data-ttu-id="6445a-140">WCF サービス モデル .NET アプリケーションのプロジェクトの app.config ファイルの抜粋を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6445a-140">For a WCF service model .NET application, you must add the excerpt to the app.config file of your project.</span></span>  
  
 <span data-ttu-id="6445a-141">有効にする[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]とアダプターのトレース、内で次の抜粋を追加、`<configuration>`タグ。</span><span class="sxs-lookup"><span data-stu-id="6445a-141">To enable [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] and adapter tracing, add the following excerpt within the `<configuration>` tag.</span></span>  
  
```  
<system.diagnostics>  
    <sources>  
      <source name="Microsoft.ServiceModel.Channels" switchValue="Error">  
        <listeners>  
          <add name="xml" />  
        </listeners>  
      </source>  
      <source name="Microsoft.Adapters.SAP" switchValue="Information">  
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
  
 <span data-ttu-id="6445a-142">これは、C:\log\AdapterTrace.svclog に WCF トレースを保存します。</span><span class="sxs-lookup"><span data-stu-id="6445a-142">This saves the WCF traces to C:\log\AdapterTrace.svclog.</span></span>  
  
## <a name="tracing-between-the-adapter-and-the-lob-application"></a><span data-ttu-id="6445a-143">アダプターと LOB アプリケーション間でのトレース</span><span class="sxs-lookup"><span data-stu-id="6445a-143">Tracing Between the Adapter and the LOB Application</span></span>  
 <span data-ttu-id="6445a-144">診断と思われる問題アダプターと、LOB アプリケーション間の通信のトレースを有効にする必要があります、LOB アプリケーションに関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="6445a-144">To diagnose issues that you suspect are related to the LOB application, you must enable tracing for communication between the adapter and the LOB application.</span></span> <span data-ttu-id="6445a-145">アダプターは、この情報にアクセスする (クライアントとサーバー側) をトレース LOB によっても異なります。</span><span class="sxs-lookup"><span data-stu-id="6445a-145">Adapters also depend on LOB tracing (client/server side) to access this information.</span></span> <span data-ttu-id="6445a-146">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]アダプター クライアントが接続 URI の"RfcSdkTrace"パラメーターを指定することで、SAP システム内のトレースを有効にできるようにします。</span><span class="sxs-lookup"><span data-stu-id="6445a-146">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] enables adapter clients to turn on tracing within the SAP system by specifying the "RfcSdkTrace" parameter in the connection URI.</span></span> <span data-ttu-id="6445a-147">RFC SDK SAP システム内のトレース情報のフローを有効にするには、このパラメーターを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6445a-147">You must specify this parameter to enable the RFC SDK to trace information flow within the SAP system.</span></span> <span data-ttu-id="6445a-148">接続 URI の詳細については、次を参照してください。 [SAP システム接続 URI を作成する](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md)です。</span><span class="sxs-lookup"><span data-stu-id="6445a-148">For more information about the connection URI, see [Create the SAP system connection URI](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md).</span></span>  
  
 <span data-ttu-id="6445a-149">さらに、RFC SDK トレースのレベルに設定した RFC_TRACE 環境変数を作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="6445a-149">Additionally, you can also create an RFC_TRACE environment variable that sets the level of tracing for the RFC SDK.</span></span> <span data-ttu-id="6445a-150">RFC_TRACE が SAP で定義されている環境変数であるし、RFC SDK を使用しています。</span><span class="sxs-lookup"><span data-stu-id="6445a-150">RFC_TRACE is an environment variable defined by SAP and is used by the RFC SDK.</span></span> <span data-ttu-id="6445a-151">この変数は定義されていないか、0 に設定されている、RFC SDK トレース レベルが最低限のものです。</span><span class="sxs-lookup"><span data-stu-id="6445a-151">If this variable is not defined or is set to 0, the RFC SDK tracing level is bare minimum.</span></span> <span data-ttu-id="6445a-152">変数が 1 または 2 に設定されている場合は、トレース レベルの詳細になります。</span><span class="sxs-lookup"><span data-stu-id="6445a-152">If the variable is set to 1 or 2, the tracing level is more detailed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6445a-153">RFC_TRACE 環境変数が設定されているかに関係なく、RFC SDK トレースが有効になっている*のみ*"RfcSdkTrace"パラメーターに設定されている場合、接続 URI の場合は true です。</span><span class="sxs-lookup"><span data-stu-id="6445a-153">Irrespective of whether the RFC_TRACE environment variable is set, the RFC SDK tracing is enabled *only* if the "RfcSdkTrace" parameter is set to true in the connection URI.</span></span> <span data-ttu-id="6445a-154">この環境変数の値は、RFC SDK トレースのレベルのみを制御します。</span><span class="sxs-lookup"><span data-stu-id="6445a-154">The value of this environment variable solely governs the level of RFC SDK tracing.</span></span> <span data-ttu-id="6445a-155">RfcSdkTrace が設定されている場合は true、メッセージをアダプターと、SAP システムの間でのトレースがコンピューターに"system32"フォルダーにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="6445a-155">If RfcSdkTrace is set to true, the message traces between the adapter and the SAP system are copied to the “system32” folder on your computer.</span></span> <span data-ttu-id="6445a-156">他の場所に、RFC SDK トレースを保存するには、RFC_TRACE_DIR 環境変数を設定することができます。</span><span class="sxs-lookup"><span data-stu-id="6445a-156">To save the RFC SDK traces to some other location, you can set the RFC_TRACE_DIR environment variable.</span></span> <span data-ttu-id="6445a-157">これらの環境変数の詳細については、SAP のマニュアルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6445a-157">For more information about these environment variables refer to the SAP documentation.</span></span>  
  
## <a name="viewing-the-traces"></a><span data-ttu-id="6445a-158">トレースの表示</span><span class="sxs-lookup"><span data-stu-id="6445a-158">Viewing the Traces</span></span>  
 <span data-ttu-id="6445a-159">Windows Communication Foundation (WCF) サービス トレース ビューアー ツールを使用するには、トレースを表示します。</span><span class="sxs-lookup"><span data-stu-id="6445a-159">You can use the Windows Communication Foundation (WCF) Service Trace Viewer tool to view the traces.</span></span> <span data-ttu-id="6445a-160">ツールの詳細については、次を参照してください。[相関トレースの表示とトラブル サービス トレース ビューアーを使用して](https://msdn.microsoft.com/library/aa751795.aspx)です。</span><span class="sxs-lookup"><span data-stu-id="6445a-160">For more information about the tool, see [Using Service Trace Viewer for Viewing Correlated Traces and Troubles](https://msdn.microsoft.com/library/aa751795.aspx).</span></span>
  
## <a name="configuring-tracking-for-biztalk-applications"></a><span data-ttu-id="6445a-161">BizTalk アプリケーションの追跡の構成</span><span class="sxs-lookup"><span data-stu-id="6445a-161">Configuring Tracking for BizTalk Applications</span></span>  
 <span data-ttu-id="6445a-162">BizTalk Server 管理コンソールでは、受信ポートと送信ポートなどの項目に対してさまざまな追跡オプションを構成できます。</span><span class="sxs-lookup"><span data-stu-id="6445a-162">The BizTalk Server Administration console lets you configure various tracking options for items such as send ports and receive ports.</span></span> <span data-ttu-id="6445a-163">追跡構成設定を使用すると、着信および発信のイベント データ、メッセージのプロパティ、メッセージ本文、およびオーケストレーションを追跡します。</span><span class="sxs-lookup"><span data-stu-id="6445a-163">The tracking configuration settings enable you to track inbound and outbound event data, message properties, message bodies, and orchestrations.</span></span> <span data-ttu-id="6445a-164">BizTalk アプリケーションの追跡の構成の詳細については、次を参照してください。、[成果物の管理](../../core/managing-artifacts.md)です。</span><span class="sxs-lookup"><span data-stu-id="6445a-164">For more information about configuring tracking for BizTalk applications, see the [Managing Artifacts](../../core/managing-artifacts.md).</span></span>
  
 <span data-ttu-id="6445a-165">また、履歴および追跡したデータを表示するのに状態と動作状況の追跡 (HAT) を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="6445a-165">You can also use Health and Activity Tracking (HAT) to view historical or tracked data.</span></span> <span data-ttu-id="6445a-166">詳細については、次を参照してください。[履歴の表示と追跡データ](../../core/viewing-historical-and-tracked-data.md)です。</span><span class="sxs-lookup"><span data-stu-id="6445a-166">For more information, see [Viewing Historical and Tracked Data](../../core/viewing-historical-and-tracked-data.md).</span></span>
 
## <a name="see-also"></a><span data-ttu-id="6445a-167">参照</span><span class="sxs-lookup"><span data-stu-id="6445a-167">See Also</span></span>  
[<span data-ttu-id="6445a-168">SAP アダプターをトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="6445a-168">Troubleshoot the SAP adapter</span></span>](../../adapters-and-accelerators/adapter-sap/troubleshoot-the-sap-adapter.md)