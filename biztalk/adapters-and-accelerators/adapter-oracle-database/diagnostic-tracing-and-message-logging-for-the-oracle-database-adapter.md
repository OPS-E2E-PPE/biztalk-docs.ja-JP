---
title: 診断トレースと Oracle データベース アダプターのメッセージのログ記録 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- tracing
- message logging
- tracing, within the adapter
- tracing, between the adapter client and the adapter
ms.assetid: 971d34e4-5609-42c6-85b9-d9b1989fc47d
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c430660b2fce17f31901761a050ce7c5522c8952
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65529288"
---
# <a name="diagnostic-tracing-and-message-logging-for-the-oracle-database-adapter"></a><span data-ttu-id="86eae-102">診断トレースとメッセージ ログの Oracle Database アダプター</span><span class="sxs-lookup"><span data-stu-id="86eae-102">Diagnostic tracing and message logging for the Oracle Database adapter</span></span>
<span data-ttu-id="86eae-103">診断トレースは、効果的にアダプターを使用するときに発生する可能性がある問題を診断するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="86eae-103">Diagnostic tracing helps to effectively diagnose problems that you might encounter when using the adapters.</span></span> <span data-ttu-id="86eae-104">このトピックでは、次の 2 種類のトレースではサポートに関する情報を提供[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="86eae-104">This topic provides information about the following two types of tracing supported with [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]:</span></span>  
  
-   <span data-ttu-id="86eae-105">アダプターのクライアントとアダプター間での WCF トレース</span><span class="sxs-lookup"><span data-stu-id="86eae-105">WCF tracing between the adapter client and the adapter</span></span>  
  
-   <span data-ttu-id="86eae-106">アダプターの WCF トレース</span><span class="sxs-lookup"><span data-stu-id="86eae-106">WCF tracing within the adapter</span></span>  
  
## <a name="wcf-tracing-between-the-adapter-client-and-the-adapter"></a><span data-ttu-id="86eae-107">アダプターのクライアントとアダプター間での WCF トレース</span><span class="sxs-lookup"><span data-stu-id="86eae-107">WCF Tracing Between the Adapter Client and the Adapter</span></span>  
 <span data-ttu-id="86eae-108">アダプター クライアントには、アダプターのクライアントとアダプター間のトレースの問題に WCF トレースが有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="86eae-108">Adapter clients can enable WCF tracing to trace issues between the adapter client and the adapter.</span></span> <span data-ttu-id="86eae-109">WCF トレースを使用して、WCF サービス モデルを使用して、アダプターのクライアントからは、シリアル化の問題の診断に役立つ入力 XML をトレースします。</span><span class="sxs-lookup"><span data-stu-id="86eae-109">WCF tracing is used to trace the input XML that comes from the adapter client by using the WCF service model, and is useful in diagnosing serialization issues.</span></span> <span data-ttu-id="86eae-110">WCF トレースは、WCF チャネル モデルまたはアダプター クライアントにアダプターからの出力メッセージには使用されません。</span><span class="sxs-lookup"><span data-stu-id="86eae-110">WCF tracing is not used for the WCF channel model or for output messages from the adapter to the adapter client.</span></span> <span data-ttu-id="86eae-111">抜粋をそれぞれの構成ファイルに追加することで、BizTalk アプリケーションと WCF サービス モデルのアプリケーションの WCF トレースをアクティブにできます。</span><span class="sxs-lookup"><span data-stu-id="86eae-111">You can activate WCF tracing for BizTalk applications and WCF service model applications by adding an excerpt to the respective configuration files.</span></span> <span data-ttu-id="86eae-112">また、デザイン時と実行時の両方のトレースを有効にできます。</span><span class="sxs-lookup"><span data-stu-id="86eae-112">Also, you can enable tracing both at design-time and run-time.</span></span>  
  
- <span data-ttu-id="86eae-113">**デザイン時トレース**します。</span><span class="sxs-lookup"><span data-stu-id="86eae-113">**Tracing at design-time**.</span></span> <span data-ttu-id="86eae-114">デザイン時動作は、使用することがあります、 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="86eae-114">For the design-time experience, you may use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], or the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span></span> <span data-ttu-id="86eae-115">これらすべてのツールから使用できる[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="86eae-115">All these tools can be used from [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="86eae-116">そのため、デザイン時エクスペリエンスのトレースを有効にする必要がありますに追加する抜粋にある devenv.exe.config ファイル*\<インストール ドライブ\>*: Visual Studio \Program Files\Microsoft *\<バージョン\>* \Common7\IDE です。</span><span class="sxs-lookup"><span data-stu-id="86eae-116">So, to enable tracing for the design-time experience, you must add the excerpt to the devenv.exe.config file located in *\<installation drive\>*:\Program Files\Microsoft Visual Studio *\<version\>* \Common7\IDE.</span></span>  
  
- <span data-ttu-id="86eae-117">**実行時にトレース**します。</span><span class="sxs-lookup"><span data-stu-id="86eae-117">**Tracing at run-time**.</span></span> <span data-ttu-id="86eae-118">実行時のトレースを使用するアプリケーションに応じて抜粋を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="86eae-118">For run-time tracing, you must add the excerpt depending on the application you are using.</span></span>  
  
  - <span data-ttu-id="86eae-119">[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]アプリケーションでは、BizTalk 構成ファイルで、通常は BTSNTSvc.exe.config に抜粋を追加する必要があります。BizTalk server では、このファイルは通常で使用可能な\<インストール ドライブ\>: \Program Files\Microsoft BizTalk Server です。</span><span class="sxs-lookup"><span data-stu-id="86eae-119">For a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] applications, you must add the excerpt to the BizTalk configuration file, typically BTSNTSvc.exe.config. For BizTalk Server, this file is available typically under \<installation drive\>:\Program Files\Microsoft BizTalk Server.</span></span>  
  
  - <span data-ttu-id="86eae-120">WCF サービス モデル .NET アプリケーションのプロジェクトの app.config ファイルに抜粋を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="86eae-120">For a WCF service model .NET application, you must add the excerpt to the app.config file of your project.</span></span>  
  
  <span data-ttu-id="86eae-121">WCF トレースを有効にするには、内で次の抜粋を追加、`<configuration>`タグ。</span><span class="sxs-lookup"><span data-stu-id="86eae-121">To enable WCF tracing, add the following excerpt within the `<configuration>` tag.</span></span>  
  
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
  
 <span data-ttu-id="86eae-122">これにより、WCF トレースが C:\log\WCFTrace.svclog を保存します。</span><span class="sxs-lookup"><span data-stu-id="86eae-122">This saves the WCF traces to C:\log\WCFTrace.svclog.</span></span> <span data-ttu-id="86eae-123">[WCF トレース](https://msdn.microsoft.com/library/ms730342.aspx)適切な情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="86eae-123">[WCF Tracing](https://msdn.microsoft.com/library/ms730342.aspx) provides more good information.</span></span>
  
> [!IMPORTANT]
>  <span data-ttu-id="86eae-124">トレースを有効にすると、機密性の高いビジネス データを公開することの潜在的なセキュリティ脅威を軽減することを確認します。</span><span class="sxs-lookup"><span data-stu-id="86eae-124">Make sure you mitigate potential security threats of exposing sensitive business data by enabling tracing.</span></span> <span data-ttu-id="86eae-125">推奨事項は、次を参照してください[ベスト プラクティス、Oracle Database アダプターをセキュリティで保護するには。](../../adapters-and-accelerators/adapter-oracle-database/best-practices-to-secure-the-oracle-database-adapter.md)</span><span class="sxs-lookup"><span data-stu-id="86eae-125">For recommendations, see [Best practices to secure the Oracle Database adapter](../../adapters-and-accelerators/adapter-oracle-database/best-practices-to-secure-the-oracle-database-adapter.md)</span></span>
  
## <a name="wcf-tracing-within-the-adapter"></a><span data-ttu-id="86eae-126">アダプターの WCF トレース</span><span class="sxs-lookup"><span data-stu-id="86eae-126">WCF tracing within the adapter</span></span>  
 <span data-ttu-id="86eae-127">アダプターは、さまざまなカテゴリの有用な情報をエラー、警告、および情報メッセージなど、トレース ファイルにログインします。</span><span class="sxs-lookup"><span data-stu-id="86eae-127">The adapters log different categories of useful information to the trace file such as errors, warnings, and information messages.</span></span> <span data-ttu-id="86eae-128">このような情報は、アダプターの処理フローを理解し、アダプターに関する問題の診断に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="86eae-128">Such information is useful in understanding the process flow within the adapter and diagnosing issues with the adapter.</span></span> <span data-ttu-id="86eae-129">アクティブ化することができます、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]とアダプターの BizTalk アプリケーションと WCF の抜粋をそれぞれの構成ファイルに追加することでモデルのアプリケーションをサービスのトレースします。</span><span class="sxs-lookup"><span data-stu-id="86eae-129">You can activate the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] and adapter tracing for BizTalk applications and WCF service model applications by adding an excerpt to the respective configuration files.</span></span> <span data-ttu-id="86eae-130">また、デザイン時と実行時の両方のトレースを有効にできます。</span><span class="sxs-lookup"><span data-stu-id="86eae-130">Also, you can enable tracing both at design-time and run-time.</span></span>  
  
- <span data-ttu-id="86eae-131">**デザイン時トレース**します。</span><span class="sxs-lookup"><span data-stu-id="86eae-131">**Tracing at design-time**.</span></span> <span data-ttu-id="86eae-132">デザイン時動作は、使用することがあります、 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="86eae-132">For the design-time experience, you may use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], or the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span></span> <span data-ttu-id="86eae-133">これらすべてのツールから使用できる[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="86eae-133">All these tools can be used from [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="86eae-134">そのため、デザイン時エクスペリエンスのトレースを有効にする必要がありますに追加する抜粋にある devenv.exe.config ファイル*\<インストール ドライブ\>*: Visual Studio \Program Files\Microsoft *\<バージョン\>* \Common7\IDE です。</span><span class="sxs-lookup"><span data-stu-id="86eae-134">So, to enable tracing for the design-time experience, you must add the excerpt to the devenv.exe.config file located in *\<installation drive\>*:\Program Files\Microsoft Visual Studio *\<version\>* \Common7\IDE.</span></span>  
  
- <span data-ttu-id="86eae-135">**実行時にトレース**します。</span><span class="sxs-lookup"><span data-stu-id="86eae-135">**Tracing at run-time**.</span></span> <span data-ttu-id="86eae-136">実行時のトレースを使用するアプリケーションに応じて抜粋を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="86eae-136">For run-time tracing, you must add the excerpt depending on the application you are using.</span></span>  
  
  - <span data-ttu-id="86eae-137">[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]アプリケーションでは、BizTalk 構成ファイルで、通常は BTSNTSvc.exe.config に抜粋を追加する必要があります。BizTalk server では、このファイルは通常で使用可能な\<インストール ドライブ\>: \Program Files\Microsoft BizTalk Server です。</span><span class="sxs-lookup"><span data-stu-id="86eae-137">For a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] applications, you must add the excerpt to the BizTalk configuration file, typically BTSNTSvc.exe.config. For BizTalk Server, this file is available typically under \<installation drive\>:\Program Files\Microsoft BizTalk Server.</span></span>  
  
  - <span data-ttu-id="86eae-138">WCF サービス モデル .NET アプリケーションのプロジェクトの app.config ファイルに抜粋を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="86eae-138">For a WCF service model .NET application, you must add the excerpt to the app.config file of your project.</span></span>  
  
  <span data-ttu-id="86eae-139">有効にする[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]とアダプターのトレース、内の抜粋を次の追加、`<configuration>`タグ。</span><span class="sxs-lookup"><span data-stu-id="86eae-139">To enable [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] and adapter tracing, add the following excerpt within the `<configuration>` tag:</span></span>  
  
```  
<system.diagnostics>  
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
  </system.diagnostics>  
```  
  
 <span data-ttu-id="86eae-140">これにより、WCF トレースが C:\log\AdapterTrace.svclog を保存します。</span><span class="sxs-lookup"><span data-stu-id="86eae-140">This saves the WCF traces to C:\log\AdapterTrace.svclog.</span></span>  
  
## <a name="viewing-the-traces"></a><span data-ttu-id="86eae-141">トレースを表示します。</span><span class="sxs-lookup"><span data-stu-id="86eae-141">Viewing the traces</span></span>  
 <span data-ttu-id="86eae-142">Windows Communication Foundation (WCF) サービス トレース ビューアー ツールを使用するには、トレースを表示します。</span><span class="sxs-lookup"><span data-stu-id="86eae-142">You can use the Windows Communication Foundation (WCF) Service Trace Viewer tool to view the traces.</span></span> <span data-ttu-id="86eae-143">参照してください[相関トレースの表示は、サービス トレース ビューアーを使用して、トラブルシューティング](https://msdn.microsoft.com/library/aa751795.aspx)します。</span><span class="sxs-lookup"><span data-stu-id="86eae-143">See [Using Service Trace Viewer for Viewing Correlated Traces and Troubleshooting](https://msdn.microsoft.com/library/aa751795.aspx).</span></span>
  
## <a name="configuring-tracking-for-biztalk-applications"></a><span data-ttu-id="86eae-144">BizTalk アプリケーションの追跡の構成</span><span class="sxs-lookup"><span data-stu-id="86eae-144">Configuring Tracking for BizTalk Applications</span></span>  
 <span data-ttu-id="86eae-145">BizTalk Server 管理コンソールを使用するポートと受信ポートの送信ポートなどのアイテムのさまざまな追跡オプションを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="86eae-145">The BizTalk Server Administration console lets you configure various tracking options for items such as send ports and receive ports.</span></span> <span data-ttu-id="86eae-146">追跡構成設定を使用すると、受信と送信イベント データ、メッセージのプロパティ、メッセージ本文、およびオーケストレーションを追跡します。</span><span class="sxs-lookup"><span data-stu-id="86eae-146">The tracking configuration settings enable you to track inbound and outbound event data, message properties, message bodies, and orchestrations.</span></span> <span data-ttu-id="86eae-147">[アイテムの管理](../../core/managing-artifacts.md)詳細情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="86eae-147">[Managing Artifacts](../../core/managing-artifacts.md) includes more info.</span></span> 

  
## <a name="see-also"></a><span data-ttu-id="86eae-148">参照</span><span class="sxs-lookup"><span data-stu-id="86eae-148">See Also</span></span>  
[<span data-ttu-id="86eae-149">Oracle データベース アダプターをトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="86eae-149">Troubleshoot the Oracle Database adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-database/troubleshoot-the-oracle-database-adapter.md)