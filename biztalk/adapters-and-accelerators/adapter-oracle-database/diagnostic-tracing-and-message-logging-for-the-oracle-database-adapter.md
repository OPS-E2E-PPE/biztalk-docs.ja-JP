---
title: "診断トレースとメッセージ ログ、Oracle データベース アダプターの |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- tracing
- message logging
- tracing, within the adapter
- tracing, between the adapter client and the adapter
ms.assetid: 971d34e4-5609-42c6-85b9-d9b1989fc47d
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 126ab9336d90fa85f03e310eca0a9bdebb442792
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="diagnostic-tracing-and-message-logging-for-the-oracle-database-adapter"></a><span data-ttu-id="388d3-102">診断トレースと Oracle データベース アダプターのメッセージ ログ</span><span class="sxs-lookup"><span data-stu-id="388d3-102">Diagnostic tracing and message logging for the Oracle Database adapter</span></span>
<span data-ttu-id="388d3-103">診断トレースは、効果的にアダプターを使用するときに発生する可能性がある問題を診断するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="388d3-103">Diagnostic tracing helps to effectively diagnose problems that you might encounter when using the adapters.</span></span> <span data-ttu-id="388d3-104">このトピックは次の 2 種類のでサポートされているトレースに関する情報を提供[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="388d3-104">This topic provides information about the following two types of tracing supported with [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]:</span></span>  
  
-   <span data-ttu-id="388d3-105">アダプターのクライアントとアダプター間での WCF トレース</span><span class="sxs-lookup"><span data-stu-id="388d3-105">WCF tracing between the adapter client and the adapter</span></span>  
  
-   <span data-ttu-id="388d3-106">アダプター内で WCF トレース</span><span class="sxs-lookup"><span data-stu-id="388d3-106">WCF tracing within the adapter</span></span>  
  
## <a name="wcf-tracing-between-the-adapter-client-and-the-adapter"></a><span data-ttu-id="388d3-107">アダプターのクライアントとアダプター間での WCF トレース</span><span class="sxs-lookup"><span data-stu-id="388d3-107">WCF Tracing Between the Adapter Client and the Adapter</span></span>  
 <span data-ttu-id="388d3-108">アダプターのクライアントは、アダプターのクライアントとアダプター間のトレースの問題への WCF トレースを有効にできます。</span><span class="sxs-lookup"><span data-stu-id="388d3-108">Adapter clients can enable WCF tracing to trace issues between the adapter client and the adapter.</span></span> <span data-ttu-id="388d3-109">WCF トレースは、WCF サービス モデルを使用して、アダプターのクライアントから取得し、シリアル化の問題の診断に役立つは入力 XML の追跡に使用します。</span><span class="sxs-lookup"><span data-stu-id="388d3-109">WCF tracing is used to trace the input XML that comes from the adapter client by using the WCF service model, and is useful in diagnosing serialization issues.</span></span> <span data-ttu-id="388d3-110">WCF トレースは、WCF チャネル モデルまたはアダプターのクライアントに、アダプターからの出力メッセージには使用されません。</span><span class="sxs-lookup"><span data-stu-id="388d3-110">WCF tracing is not used for the WCF channel model or for output messages from the adapter to the adapter client.</span></span> <span data-ttu-id="388d3-111">それぞれの構成ファイルの抜粋を追加することで、BizTalk アプリケーションと WCF サービス モデルのアプリケーションの WCF トレースをアクティブにできます。</span><span class="sxs-lookup"><span data-stu-id="388d3-111">You can activate WCF tracing for BizTalk applications and WCF service model applications by adding an excerpt to the respective configuration files.</span></span> <span data-ttu-id="388d3-112">また、デザイン時と実行時の両方でトレースを有効にできます。</span><span class="sxs-lookup"><span data-stu-id="388d3-112">Also, you can enable tracing both at design-time and run-time.</span></span>  
  
-   <span data-ttu-id="388d3-113">**デザイン時にトレース**です。</span><span class="sxs-lookup"><span data-stu-id="388d3-113">**Tracing at design-time**.</span></span> <span data-ttu-id="388d3-114">デザイン時機能を使用することは、 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="388d3-114">For the design-time experience, you may use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], or the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span></span> <span data-ttu-id="388d3-115">これらすべてのツールを使用できる[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="388d3-115">All these tools can be used from [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="388d3-116">そのため、デザイン時の操作のトレースを有効にする必要がありますに追加する抜粋にある devenv.exe.config ファイル*\<インストール ドライブ >*: \Program Files\Microsoft Visual Studio  *\<バージョン >*\Common7\IDE です。</span><span class="sxs-lookup"><span data-stu-id="388d3-116">So, to enable tracing for the design-time experience, you must add the excerpt to the devenv.exe.config file located in *\<installation drive>*:\Program Files\Microsoft Visual Studio *\<version>*\Common7\IDE.</span></span>  
  
-   <span data-ttu-id="388d3-117">**実行時にトレース**です。</span><span class="sxs-lookup"><span data-stu-id="388d3-117">**Tracing at run-time**.</span></span> <span data-ttu-id="388d3-118">実行時のトレースを使用しているアプリケーションによっては抜粋を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="388d3-118">For run-time tracing, you must add the excerpt depending on the application you are using.</span></span>  
  
    -   <span data-ttu-id="388d3-119">[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]アプリケーションに BizTalk 構成ファイルで、通常 BTSNTSvc.exe.config の抜粋を追加する必要があります。[!INCLUDE[prague](../../includes/prague-md.md)]、このファイルは通常 \<インストール ドライブ >: \Program Files\Microsoft[!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="388d3-119">For a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] applications, you must add the excerpt to the BizTalk configuration file, typically BTSNTSvc.exe.config. For [!INCLUDE[prague](../../includes/prague-md.md)], this file is available typically under \<installation drive>:\Program Files\Microsoft [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)].</span></span>  
  
    -   <span data-ttu-id="388d3-120">WCF サービス モデル .NET アプリケーションのプロジェクトの app.config ファイルの抜粋を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="388d3-120">For a WCF service model .NET application, you must add the excerpt to the app.config file of your project.</span></span>  
  
 <span data-ttu-id="388d3-121">WCF トレースを有効にするには、内で次の抜粋を追加、`<configuration>`タグ。</span><span class="sxs-lookup"><span data-stu-id="388d3-121">To enable WCF tracing, add the following excerpt within the `<configuration>` tag.</span></span>  
  
```  
\<system.diagnostics>  
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
  \</system.diagnostics>  
  \<system.serviceModel>  
    <diagnostics>  
      <messageLogging   
           logEntireMessage="true"   
           logMalformedMessages="false"  
           logMessagesAtServiceLevel="true"   
           logMessagesAtTransportLevel="false"/>  
    </diagnostics>      
  \</system.serviceModel>  
```  
  
 <span data-ttu-id="388d3-122">これは、C:\log\WCFTrace.svclog に WCF トレースを保存します。</span><span class="sxs-lookup"><span data-stu-id="388d3-122">This saves the WCF traces to C:\log\WCFTrace.svclog.</span></span> <span data-ttu-id="388d3-123">[WCF トレース](https://msdn.microsoft.com/library/ms730342.aspx)適切な詳細を提供します。</span><span class="sxs-lookup"><span data-stu-id="388d3-123">[WCF Tracing](https://msdn.microsoft.com/library/ms730342.aspx) provides more good information.</span></span>
  
> [!IMPORTANT]
>  <span data-ttu-id="388d3-124">トレースを有効にすると、機密のビジネス データを公開するための潜在的なセキュリティ上の脅威を軽減することを確認してください。</span><span class="sxs-lookup"><span data-stu-id="388d3-124">Make sure you mitigate potential security threats of exposing sensitive business data by enabling tracing.</span></span> <span data-ttu-id="388d3-125">推奨事項については、次を参照してください[ベスト プラクティス、Oracle データベース アダプターをセキュリティで保護するには。](../../adapters-and-accelerators/adapter-oracle-database/best-practices-to-secure-the-oracle-database-adapter.md)</span><span class="sxs-lookup"><span data-stu-id="388d3-125">For recommendations, see [Best practices to secure the Oracle Database adapter](../../adapters-and-accelerators/adapter-oracle-database/best-practices-to-secure-the-oracle-database-adapter.md)</span></span>
  
## <a name="wcf-tracing-within-the-adapter"></a><span data-ttu-id="388d3-126">アダプター内で WCF トレース</span><span class="sxs-lookup"><span data-stu-id="388d3-126">WCF tracing within the adapter</span></span>  
 <span data-ttu-id="388d3-127">アダプターは、エラー、警告、および情報メッセージなど、トレース ファイルに有用な情報のさまざまなカテゴリをログオンします。</span><span class="sxs-lookup"><span data-stu-id="388d3-127">The adapters log different categories of useful information to the trace file such as errors, warnings, and information messages.</span></span> <span data-ttu-id="388d3-128">このような情報は、アダプター内のプロセス フローを理解し、アダプターに関する問題の診断に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="388d3-128">Such information is useful in understanding the process flow within the adapter and diagnosing issues with the adapter.</span></span> <span data-ttu-id="388d3-129">アクティブ化することができます、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]とアダプターが BizTalk アプリケーションと WCF サービスの抜粋をそれぞれの構成ファイルに追加することによってモデル アプリケーション用にトレースされます。</span><span class="sxs-lookup"><span data-stu-id="388d3-129">You can activate the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] and adapter tracing for BizTalk applications and WCF service model applications by adding an excerpt to the respective configuration files.</span></span> <span data-ttu-id="388d3-130">また、デザイン時と実行時の両方でトレースを有効にできます。</span><span class="sxs-lookup"><span data-stu-id="388d3-130">Also, you can enable tracing both at design-time and run-time.</span></span>  
  
-   <span data-ttu-id="388d3-131">**デザイン時にトレース**です。</span><span class="sxs-lookup"><span data-stu-id="388d3-131">**Tracing at design-time**.</span></span> <span data-ttu-id="388d3-132">デザイン時機能を使用することは、 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="388d3-132">For the design-time experience, you may use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], or the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span></span> <span data-ttu-id="388d3-133">これらすべてのツールを使用できる[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="388d3-133">All these tools can be used from [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="388d3-134">そのため、デザイン時の操作のトレースを有効にする必要がありますに追加する抜粋にある devenv.exe.config ファイル*\<インストール ドライブ >*: \Program Files\Microsoft Visual Studio  *\<バージョン >*\Common7\IDE です。</span><span class="sxs-lookup"><span data-stu-id="388d3-134">So, to enable tracing for the design-time experience, you must add the excerpt to the devenv.exe.config file located in *\<installation drive>*:\Program Files\Microsoft Visual Studio *\<version>*\Common7\IDE.</span></span>  
  
-   <span data-ttu-id="388d3-135">**実行時にトレース**です。</span><span class="sxs-lookup"><span data-stu-id="388d3-135">**Tracing at run-time**.</span></span> <span data-ttu-id="388d3-136">実行時のトレースを使用しているアプリケーションによっては抜粋を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="388d3-136">For run-time tracing, you must add the excerpt depending on the application you are using.</span></span>  
  
    -   <span data-ttu-id="388d3-137">[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]アプリケーションに BizTalk 構成ファイルで、通常 BTSNTSvc.exe.config の抜粋を追加する必要があります。[!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)]、このファイルは通常 \<インストール ドライブ >: \Program Files\Microsoft[!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="388d3-137">For a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] applications, you must add the excerpt to the BizTalk configuration file, typically BTSNTSvc.exe.config. For [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)], this file is available typically under \<installation drive>:\Program Files\Microsoft [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)].</span></span>  
  
    -   <span data-ttu-id="388d3-138">WCF サービス モデル .NET アプリケーションのプロジェクトの app.config ファイルの抜粋を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="388d3-138">For a WCF service model .NET application, you must add the excerpt to the app.config file of your project.</span></span>  
  
 <span data-ttu-id="388d3-139">有効にする[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]とアダプターのトレース、内で次の抜粋を追加、`<configuration>`タグ。</span><span class="sxs-lookup"><span data-stu-id="388d3-139">To enable [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] and adapter tracing, add the following excerpt within the `<configuration>` tag:</span></span>  
  
```  
\<system.diagnostics>  
    <sources>  
      <source name="Microsoft.ServiceModel.Channels" switchValue="Error">  
        <listeners>  
          <add name="xml" />  
        </listeners>  
      </source>  
      <source name=" Microsoft.Adapters.OracleDB" switchValue="Information">  
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
  \</system.diagnostics>  
```  
  
 <span data-ttu-id="388d3-140">これは、C:\log\AdapterTrace.svclog に WCF トレースを保存します。</span><span class="sxs-lookup"><span data-stu-id="388d3-140">This saves the WCF traces to C:\log\AdapterTrace.svclog.</span></span>  
  
## <a name="viewing-the-traces"></a><span data-ttu-id="388d3-141">トレースの表示</span><span class="sxs-lookup"><span data-stu-id="388d3-141">Viewing the traces</span></span>  
 <span data-ttu-id="388d3-142">Windows Communication Foundation (WCF) サービス トレース ビューアー ツールを使用するには、トレースを表示します。</span><span class="sxs-lookup"><span data-stu-id="388d3-142">You can use the Windows Communication Foundation (WCF) Service Trace Viewer tool to view the traces.</span></span> <span data-ttu-id="388d3-143">参照してください[相関トレースの表示は、サービス トレース ビューアーを使用して、トラブルシューティング](https://msdn.microsoft.com/library/aa751795.aspx)です。</span><span class="sxs-lookup"><span data-stu-id="388d3-143">See [Using Service Trace Viewer for Viewing Correlated Traces and Troubleshooting](https://msdn.microsoft.com/library/aa751795.aspx).</span></span>
  
## <a name="configuring-tracking-for-biztalk-applications"></a><span data-ttu-id="388d3-144">BizTalk アプリケーションの追跡の構成</span><span class="sxs-lookup"><span data-stu-id="388d3-144">Configuring Tracking for BizTalk Applications</span></span>  
 <span data-ttu-id="388d3-145">BizTalk Server 管理コンソールでは、受信ポートと送信ポートなどの項目に対してさまざまな追跡オプションを構成できます。</span><span class="sxs-lookup"><span data-stu-id="388d3-145">The BizTalk Server Administration console lets you configure various tracking options for items such as send ports and receive ports.</span></span> <span data-ttu-id="388d3-146">追跡構成設定を使用すると、着信および発信のイベント データ、メッセージのプロパティ、メッセージ本文、およびオーケストレーションを追跡します。</span><span class="sxs-lookup"><span data-stu-id="388d3-146">The tracking configuration settings enable you to track inbound and outbound event data, message properties, message bodies, and orchestrations.</span></span> <span data-ttu-id="388d3-147">[成果物の管理](../../core/managing-artifacts.md)詳細な情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="388d3-147">[Managing Artifacts](../../core/managing-artifacts.md) includes more info.</span></span> 

  
## <a name="see-also"></a><span data-ttu-id="388d3-148">参照</span><span class="sxs-lookup"><span data-stu-id="388d3-148">See Also</span></span>  
[<span data-ttu-id="388d3-149">Oracle データベース アダプターをトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="388d3-149">Troubleshoot the Oracle Database adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-database/troubleshoot-the-oracle-database-adapter.md)