---
title: 診断トレースと SQL アダプターでメッセージのログ記録 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d6599b4d-5650-4592-96af-ee43fb36357d
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5fbcdac66c40a4b1d9c2b35d2f8268a63c8bd0e5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968155"
---
# <a name="diagnostic-tracing-and-message-logging-in-the-sql-adapter"></a><span data-ttu-id="35d95-102">診断トレースと SQL アダプターでメッセージのログ記録</span><span class="sxs-lookup"><span data-stu-id="35d95-102">Diagnostic Tracing and Message Logging in the SQL adapter</span></span>
<span data-ttu-id="35d95-103">診断トレースは、効果的にアダプターを使用するときに発生する可能性がある問題を診断するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="35d95-103">Diagnostic tracing helps to effectively diagnose problems that you might encounter when using the adapters.</span></span> <span data-ttu-id="35d95-104">アダプター クライアントは、2 つのレベルの診断トレースをアクティブ化できます。</span><span class="sxs-lookup"><span data-stu-id="35d95-104">Adapter clients can activate diagnostic tracing at two levels:</span></span>  
  
- <span data-ttu-id="35d95-105">アダプターのクライアントとアダプターの間</span><span class="sxs-lookup"><span data-stu-id="35d95-105">Between the adapter client and the adapter</span></span>  
  
- <span data-ttu-id="35d95-106">アダプター内</span><span class="sxs-lookup"><span data-stu-id="35d95-106">Within the adapter</span></span>  
  
  <span data-ttu-id="35d95-107">このセクションでは、これらのレベルでトレースをアクティブ化についての情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="35d95-107">This section provides information about activating tracing at these levels.</span></span>  
  
## <a name="tracing-between-the-adapter-client-and-the-adapter"></a><span data-ttu-id="35d95-108">アダプターのクライアントと、アダプターのトレース</span><span class="sxs-lookup"><span data-stu-id="35d95-108">Tracing Between the Adapter Client and the Adapter</span></span>  
 <span data-ttu-id="35d95-109">アダプター クライアントには、アダプターのクライアントとアダプター間のトレースの問題に WCF トレースが有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="35d95-109">Adapter clients can enable WCF tracing to trace issues between the adapter client and the adapter.</span></span> <span data-ttu-id="35d95-110">WCF トレースを使用して、WCF サービス モデルを使用して、アダプターのクライアントからは、シリアル化の問題の診断に役立つ入力 XML をトレースします。</span><span class="sxs-lookup"><span data-stu-id="35d95-110">WCF tracing is used to trace the input XML that comes from the adapter client by using the WCF service model and is useful in diagnosing serialization issues.</span></span> <span data-ttu-id="35d95-111">WCF トレースは、WCF チャネル モデルまたはアダプター クライアントにアダプターからの出力メッセージには使用されません。</span><span class="sxs-lookup"><span data-stu-id="35d95-111">WCF tracing is not used for the WCF channel model or for output messages from the adapter to the adapter client.</span></span> <span data-ttu-id="35d95-112">抜粋をそれぞれの構成ファイルに追加することで、BizTalk アプリケーションと WCF サービス モデルのアプリケーションの WCF トレースをアクティブにできます。</span><span class="sxs-lookup"><span data-stu-id="35d95-112">You can activate WCF tracing for BizTalk applications and WCF service model applications by adding an excerpt to the respective configuration files.</span></span> <span data-ttu-id="35d95-113">また、デザイン時に両方のトレースを有効にし、実行時できます。</span><span class="sxs-lookup"><span data-stu-id="35d95-113">Also, you can enable tracing both at design time and run time.</span></span>  
  
- <span data-ttu-id="35d95-114">**デザイン時にトレース**します。</span><span class="sxs-lookup"><span data-stu-id="35d95-114">**Tracing at design time**.</span></span> <span data-ttu-id="35d95-115">デザイン時動作は、使用することがあります、 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="35d95-115">For the design-time experience, you may use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], or the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span></span> <span data-ttu-id="35d95-116">これらすべてのツールから使用できる[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="35d95-116">All these tools can be used from [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="35d95-117">そのため、デザイン時エクスペリエンスのトレースを有効にする必要がありますに追加する抜粋にある devenv.exe.config ファイル*\<インストール ドライブ\>*: Visual Studio \Program Files\Microsoft *\<バージョン\>* \Common7\IDE です。</span><span class="sxs-lookup"><span data-stu-id="35d95-117">So, to enable tracing for the design-time experience, you must add the excerpt to the devenv.exe.config file located in *\<installation drive\>*:\Program Files\Microsoft Visual Studio *\<version\>* \Common7\IDE.</span></span>  
  
- <span data-ttu-id="35d95-118">**実行時にトレース**します。</span><span class="sxs-lookup"><span data-stu-id="35d95-118">**Tracing at run time**.</span></span> <span data-ttu-id="35d95-119">実行時のトレースを使用するアプリケーションに応じて抜粋を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="35d95-119">For run-time tracing, you must add the excerpt depending on the application you are using.</span></span>  
  
  - <span data-ttu-id="35d95-120">[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]アプリケーションでは、BizTalk 構成ファイルで、通常は BTSNTSvc.exe.config に抜粋を追加する必要があります。BizTalk server では、このファイルは通常で使用可能な\<インストール ドライブ\>: \Program Files\Microsoft BizTalk Server です。</span><span class="sxs-lookup"><span data-stu-id="35d95-120">For a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] application, you must add the excerpt to the BizTalk configuration file, typically BTSNTSvc.exe.config. For BizTalk Server, this file is available typically under \<installation drive\>:\Program Files\Microsoft BizTalk Server.</span></span>  
  
  - <span data-ttu-id="35d95-121">WCF サービス モデル .NET アプリケーションのプロジェクトの app.config ファイルに抜粋を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="35d95-121">For a WCF service model .NET application, you must add the excerpt to the app.config file of your project.</span></span>  
  
  <span data-ttu-id="35d95-122">WCF トレースを有効にするには、内で次の抜粋を追加、`<configuration>`タグ。</span><span class="sxs-lookup"><span data-stu-id="35d95-122">To enable WCF tracing, add the following excerpt within the `<configuration>` tag.</span></span>  
  
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
  
 <span data-ttu-id="35d95-123">これにより、WCF トレースが C:\log\WCFTrace.svclog を保存します。</span><span class="sxs-lookup"><span data-stu-id="35d95-123">This saves the WCF traces to C:\log\WCFTrace.svclog.</span></span> <span data-ttu-id="35d95-124">WCF トレースの詳細については、次を参照してください。[トレース](https://msdn.microsoft.com/library/ms730342.aspx)します。</span><span class="sxs-lookup"><span data-stu-id="35d95-124">For more information about WCF tracing, see [Tracing](https://msdn.microsoft.com/library/ms730342.aspx).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="35d95-125">トレースを有効にすると、機密性の高いビジネス データを公開することの潜在的なセキュリティ脅威を軽減することを確認します。</span><span class="sxs-lookup"><span data-stu-id="35d95-125">Make sure you mitigate potential security threats of exposing sensitive business data by enabling tracing.</span></span> <span data-ttu-id="35d95-126">推奨事項を参照してください[ベスト プラクティスは、SQL アダプターをセキュリティで保護する](../../adapters-and-accelerators/adapter-sql/best-practices-to-secure-the-sql-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="35d95-126">For recommendations see [Best practices to secure the SQL adapter](../../adapters-and-accelerators/adapter-sql/best-practices-to-secure-the-sql-adapter.md).</span></span>
  
## <a name="tracing-within-the-adapter"></a><span data-ttu-id="35d95-127">アダプターのトレース</span><span class="sxs-lookup"><span data-stu-id="35d95-127">Tracing Within the Adapter</span></span>  
 <span data-ttu-id="35d95-128">アダプターは、さまざまなカテゴリの有用な情報をエラー、警告、および情報メッセージなど、トレース ファイルにログインします。</span><span class="sxs-lookup"><span data-stu-id="35d95-128">The adapters log different categories of useful information to the trace file such as errors, warnings, and information messages.</span></span> <span data-ttu-id="35d95-129">このような情報は、アダプターの処理フローを理解し、アダプターに関する問題の診断に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="35d95-129">Such information is useful in understanding the process flow within the adapter and diagnosing issues with the adapter.</span></span> <span data-ttu-id="35d95-130">アクティブ化することができます、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]とアダプターの BizTalk アプリケーションと WCF の抜粋をそれぞれの構成ファイルに追加することでモデルのアプリケーションをサービスのトレースします。</span><span class="sxs-lookup"><span data-stu-id="35d95-130">You can activate the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] and adapter tracing for BizTalk applications and WCF service model applications by adding an excerpt to the respective configuration files.</span></span> <span data-ttu-id="35d95-131">また、デザイン時に両方のトレースを有効にし、実行時できます。</span><span class="sxs-lookup"><span data-stu-id="35d95-131">Also, you can enable tracing both at design time and run time.</span></span>  
  
- <span data-ttu-id="35d95-132">**デザイン時にトレース**します。</span><span class="sxs-lookup"><span data-stu-id="35d95-132">**Tracing at design time**.</span></span> <span data-ttu-id="35d95-133">デザイン時動作は、使用することがあります、 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="35d95-133">For the design-time experience, you may use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], or the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span></span> <span data-ttu-id="35d95-134">これらすべてのツールから使用できる[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="35d95-134">All these tools can be used from [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="35d95-135">そのため、デザイン時エクスペリエンスのトレースを有効にする必要がありますに追加する抜粋にある devenv.exe.config ファイル*\<インストール ドライブ\>*: Visual Studio \Program Files\Microsoft *\<バージョン\>* \Common7\IDE です。</span><span class="sxs-lookup"><span data-stu-id="35d95-135">So, to enable tracing for the design-time experience, you must add the excerpt to the devenv.exe.config file located in *\<installation drive\>*:\Program Files\Microsoft Visual Studio *\<version\>* \Common7\IDE.</span></span>  
  
- <span data-ttu-id="35d95-136">**実行時にトレース**します。</span><span class="sxs-lookup"><span data-stu-id="35d95-136">**Tracing at run time**.</span></span> <span data-ttu-id="35d95-137">実行時のトレースを使用するアプリケーションに応じて抜粋を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="35d95-137">For run-time tracing, you must add the excerpt depending on the application you are using.</span></span>  
  
  - <span data-ttu-id="35d95-138">[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]アプリケーションでは、BizTalk 構成ファイルで、通常は BTSNTSvc.exe.config に抜粋を追加する必要があります。BizTalk server では、このファイルは通常で使用可能な\<インストール ドライブ\>: \Program Files\Microsoft BizTalk Server です。</span><span class="sxs-lookup"><span data-stu-id="35d95-138">For a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] application, you must add the excerpt to the BizTalk configuration file, typically BTSNTSvc.exe.config. For BizTalk Server, this file is available typically under \<installation drive\>:\Program Files\Microsoft BizTalk Server.</span></span>  
  
  - <span data-ttu-id="35d95-139">WCF サービス モデル .NET アプリケーションのプロジェクトの app.config ファイルに抜粋を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="35d95-139">For a WCF service model .NET application, you must add the excerpt to the app.config file of your project.</span></span>  
  
  <span data-ttu-id="35d95-140">有効にする[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]とアダプターのトレース、内の抜粋を次の追加、`<configuration>`タグ。</span><span class="sxs-lookup"><span data-stu-id="35d95-140">To enable [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] and adapter tracing, add the following excerpt within the `<configuration>` tag.</span></span>  
  
```  
<system.diagnostics>  
    <sources>  
      <source name="Microsoft.ServiceModel.Channels" switchValue="Error">  
        <listeners>  
          <add name="xml" />  
        </listeners>  
      </source>  
      <source name="Microsoft.Adapters.Sql" switchValue="Information">  
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
  
 <span data-ttu-id="35d95-141">これにより、WCF トレースが C:\log\AdapterTrace.svclog を保存します。</span><span class="sxs-lookup"><span data-stu-id="35d95-141">This saves the WCF traces to C:\log\AdapterTrace.svclog.</span></span>  
  
## <a name="viewing-the-traces"></a><span data-ttu-id="35d95-142">トレースを表示します。</span><span class="sxs-lookup"><span data-stu-id="35d95-142">Viewing the Traces</span></span>  
 <span data-ttu-id="35d95-143">Windows Communication Foundation (WCF) サービス トレース ビューアー ツールを使用するには、トレースを表示します。</span><span class="sxs-lookup"><span data-stu-id="35d95-143">You can use the Windows Communication Foundation (WCF) Service Trace Viewer tool to view the traces.</span></span> <span data-ttu-id="35d95-144">ツールの詳細については、次を参照してください。[相関トレースの表示と問題のサービス トレース ビューアーを使用して](https://msdn.microsoft.com/library/aa751795.aspx)します。</span><span class="sxs-lookup"><span data-stu-id="35d95-144">For more information about the tool, see [Using Service Trace Viewer for Viewing Correlated Traces and Troubles](https://msdn.microsoft.com/library/aa751795.aspx).</span></span>
  
## <a name="configuring-tracking-for-biztalk-applications"></a><span data-ttu-id="35d95-145">BizTalk アプリケーションの追跡の構成</span><span class="sxs-lookup"><span data-stu-id="35d95-145">Configuring Tracking for BizTalk Applications</span></span>  
 <span data-ttu-id="35d95-146">BizTalk Server 管理コンソールを使用するポートと受信ポートの送信ポートなどのアイテムのさまざまな追跡オプションを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="35d95-146">The BizTalk Server Administration console lets you configure various tracking options for items such as send ports and receive ports.</span></span> <span data-ttu-id="35d95-147">追跡構成設定を使用すると、受信と送信イベント データ、メッセージのプロパティ、メッセージ本文、およびオーケストレーションを追跡します。</span><span class="sxs-lookup"><span data-stu-id="35d95-147">The tracking configuration settings enable you to track inbound and outbound event data, message properties, message bodies, and orchestrations.</span></span> <span data-ttu-id="35d95-148">BizTalk アプリケーションの追跡を構成する方法の詳細については、次を参照してください。、[管理成果物](../../core/managing-artifacts.md)します。</span><span class="sxs-lookup"><span data-stu-id="35d95-148">For more information about configuring tracking for BizTalk applications, see the [Managing Artifacts](../../core/managing-artifacts.md).</span></span>
  
 <span data-ttu-id="35d95-149">履歴および追跡したデータを表示するのに状態と動作状況の追跡 (HAT) を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="35d95-149">You can also use Health and Activity Tracking (HAT) to view historical or tracked data.</span></span> <span data-ttu-id="35d95-150">詳細については、次を参照してください。[履歴の表示と追跡データ](../../core/viewing-historical-and-tracked-data.md)します。</span><span class="sxs-lookup"><span data-stu-id="35d95-150">For more information, see [Viewing Historical and Tracked Data](../../core/viewing-historical-and-tracked-data.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="35d95-151">参照</span><span class="sxs-lookup"><span data-stu-id="35d95-151">See Also</span></span>  
 [<span data-ttu-id="35d95-152">SQL アダプターをトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="35d95-152">Troubleshoot the SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/troubleshoot-the-sql-adapter.md)