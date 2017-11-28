---
title: "診断トレースと Oracle E-business Suite アダプターでメッセージのログ記録 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c0d6be2a-cbd0-4c9c-be6f-9631063346e2
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a4aaadb9eb84fa5415b31673d922e11a56fa7136
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="diagnostic-tracing-and-message-logging-in-the-oracle-e-business-suite-adapter"></a><span data-ttu-id="00f20-102">診断トレースと Oracle E-business Suite アダプターでメッセージのログ記録</span><span class="sxs-lookup"><span data-stu-id="00f20-102">Diagnostic Tracing and Message Logging in the Oracle E-Business Suite adapter</span></span>
<span data-ttu-id="00f20-103">診断トレースは、効果的にアダプターを使用するときに発生する可能性がある問題を診断するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="00f20-103">Diagnostic tracing helps to effectively diagnose problems that you might encounter when using the adapters.</span></span> <span data-ttu-id="00f20-104">このトピックではサポートされてトレースの次の 3 種類に関する情報を提供する[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="00f20-104">This topic provides information about the following three types of tracing supported with [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]:</span></span>  
  
-   <span data-ttu-id="00f20-105">クライアント識別子を使用して oracle サーバー側のトレース</span><span class="sxs-lookup"><span data-stu-id="00f20-105">Oracle server-side tracing using a client identifier</span></span>
  
-   <span data-ttu-id="00f20-106">アダプターのクライアントとアダプター間での WCF トレース</span><span class="sxs-lookup"><span data-stu-id="00f20-106">WCF tracing between the adapter client and the adapter</span></span>
  
-   <span data-ttu-id="00f20-107">アダプター内で WCF トレース</span><span class="sxs-lookup"><span data-stu-id="00f20-107">WCF tracing within the adapter</span></span>
 
## <a name="oracle-server-side-tracing-using-a-client-identifier"></a><span data-ttu-id="00f20-108">Oracle サーバー側トレースを使用して、クライアント識別子</span><span class="sxs-lookup"><span data-stu-id="00f20-108">Oracle server side tracing using a client identifier</span></span>  
 <span data-ttu-id="00f20-109">Oracle では、Oracle データベースでのクライアント アプリケーションによって実行される操作のサーバー側トレースを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="00f20-109">Oracle allows you to perform server-side tracing for the operations performed by client applications on the Oracle database.</span></span> <span data-ttu-id="00f20-110">クライアント アプリケーションからの要求は、別のデータベース セッションにルーティングすることができます、いるため、要求の発生元を追跡するが困難になります。</span><span class="sxs-lookup"><span data-stu-id="00f20-110">Because requests from client applications can be routed to different database sessions, it becomes difficult to trace the origin of the request.</span></span> <span data-ttu-id="00f20-111">ただし、Oracle では、クライアント識別子を使用してエンド ツー エンドのアプリケーションのトレースが容易になります。</span><span class="sxs-lookup"><span data-stu-id="00f20-111">However, Oracle facilitates end-to-end application tracing using client identifiers.</span></span> 
 
 <span data-ttu-id="00f20-112">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]公開、 `OracleConnectionClientId` Oracle への接続にアダプターによって使用される接続のデザイン時にクライアント識別子を指定できるようにするプロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="00f20-112">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] exposes the `OracleConnectionClientId` binding property that allows you to specify the client identifier at the design time for the connection used by the adapter to connect to Oracle.</span></span> <span data-ttu-id="00f20-113">アダプター クライアント識別子では、Oracle、上のアダプターのクライアントによって実行される操作のトレースを選択的に役立つし、フィルター処理して、クライアント識別子に基づく Oracle サーバーのトレースを表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="00f20-113">The adapter client identifier helps you in selective tracing of the operations performed by the adapter client on Oracle, and also allows you to filter and view the Oracle server traces based on the client identifier.</span></span> <span data-ttu-id="00f20-114">Oracle ではクライアント識別子のトレースを有効にする方法については、次を参照してください。 [http://go.microsoft.com/fwlink/p/?LinkId=135746](http://go.microsoft.com/fwlink/p/?LinkId=135746)です。</span><span class="sxs-lookup"><span data-stu-id="00f20-114">For information about how you can enable tracing for client identifiers in Oracle, see [http://go.microsoft.com/fwlink/p/?LinkId=135746](http://go.microsoft.com/fwlink/p/?LinkId=135746).</span></span>  
  
## <a name="wcf-tracing-between-the-adapter-client-and-the-adapter"></a><span data-ttu-id="00f20-115">アダプターのクライアントとアダプター間での WCF トレース</span><span class="sxs-lookup"><span data-stu-id="00f20-115">WCF tracing between the adapter client and the adapter</span></span>  
 <span data-ttu-id="00f20-116">アダプターのクライアントは、アダプターのクライアントとアダプター間のトレースの問題への WCF トレースを有効にできます。</span><span class="sxs-lookup"><span data-stu-id="00f20-116">Adapter clients can enable WCF tracing to trace issues between the adapter client and the adapter.</span></span> <span data-ttu-id="00f20-117">WCF トレースは、WCF サービス モデルを使用して、アダプターのクライアントから取得し、シリアル化の問題の診断に役立つは入力 XML の追跡に使用します。</span><span class="sxs-lookup"><span data-stu-id="00f20-117">WCF tracing is used to trace the input XML that comes from the adapter client by using the WCF service model and is useful in diagnosing serialization issues.</span></span> <span data-ttu-id="00f20-118">WCF トレースは、WCF チャネル モデルまたはアダプターのクライアントに、アダプターからの出力メッセージには使用されません。</span><span class="sxs-lookup"><span data-stu-id="00f20-118">WCF tracing is not used for the WCF channel model or for output messages from the adapter to the adapter client.</span></span> <span data-ttu-id="00f20-119">それぞれの構成ファイルの抜粋を追加することで、BizTalk アプリケーションと WCF サービス モデルのアプリケーションの WCF トレースをアクティブにできます。</span><span class="sxs-lookup"><span data-stu-id="00f20-119">You can activate WCF tracing for BizTalk applications and WCF service model applications by adding an excerpt to the respective configuration files.</span></span> <span data-ttu-id="00f20-120">また、デザイン時と実行時の両方でトレースを有効にできます。</span><span class="sxs-lookup"><span data-stu-id="00f20-120">Also, you can enable tracing both at design-time and run-time.</span></span>  
  
-   <span data-ttu-id="00f20-121">**デザイン時にトレース**です。</span><span class="sxs-lookup"><span data-stu-id="00f20-121">**Tracing at design-time**.</span></span> <span data-ttu-id="00f20-122">デザイン時機能を使用することは、 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="00f20-122">For the design-time experience, you may use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], or the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span></span> <span data-ttu-id="00f20-123">これらすべてのツールを使用できる[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="00f20-123">All these tools can be used from [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="00f20-124">そのため、デザイン時の操作のトレースを有効にする必要がありますに追加する抜粋にある devenv.exe.config ファイル*\<インストール ドライブ >*: \Program Files\Microsoft Visual Studio  *\<バージョン >*\Common7\IDE です。</span><span class="sxs-lookup"><span data-stu-id="00f20-124">So, to enable tracing for the design-time experience, you must add the excerpt to the devenv.exe.config file located in *\<installation drive>*:\Program Files\Microsoft Visual Studio *\<version>*\Common7\IDE.</span></span>  
  
-   <span data-ttu-id="00f20-125">**実行時にトレース**です。</span><span class="sxs-lookup"><span data-stu-id="00f20-125">**Tracing at run-time**.</span></span> <span data-ttu-id="00f20-126">実行時のトレースを使用しているアプリケーションによっては抜粋を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="00f20-126">For run-time tracing, you must add the excerpt depending on the application you are using.</span></span>  
  
    -   <span data-ttu-id="00f20-127">[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]アプリケーションに BizTalk 構成ファイルで、通常 BTSNTSvc.exe.config の抜粋を追加する必要があります。[!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)]、このファイルは通常 \<インストール ドライブ >: \Program Files\Microsoft[!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="00f20-127">For a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] applications, you must add the excerpt to the BizTalk configuration file, typically BTSNTSvc.exe.config. For [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)], this file is available typically under \<installation drive>:\Program Files\Microsoft [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)].</span></span>  
  
    -   <span data-ttu-id="00f20-128">WCF サービス モデル .NET アプリケーションのプロジェクトの app.config ファイルの抜粋を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="00f20-128">For a WCF service model .NET application, you must add the excerpt to the app.config file of your project.</span></span>  
  
 <span data-ttu-id="00f20-129">WCF トレースを有効にするには、内で次の抜粋を追加、`<configuration>`タグ。</span><span class="sxs-lookup"><span data-stu-id="00f20-129">To enable WCF tracing, add the following excerpt within the `<configuration>` tag:</span></span>  
  
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
  
 <span data-ttu-id="00f20-130">これは、C:\log\WCFTrace.svclog に WCF トレースを保存します。</span><span class="sxs-lookup"><span data-stu-id="00f20-130">This saves the WCF traces to C:\log\WCFTrace.svclog.</span></span> <span data-ttu-id="00f20-131">[WCF トレース](https://msdn.microsoft.com/library/ms730342.aspx)詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="00f20-131">[WCF tracing](https://msdn.microsoft.com/library/ms730342.aspx) provides more information.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="00f20-132">トレースを有効にする場合に発生することが重要なビジネス データを公開するための潜在的なセキュリティ上の脅威を軽減することを確認してください。</span><span class="sxs-lookup"><span data-stu-id="00f20-132">Make sure you mitigate potential security threats of exposing sensitive business data that can be caused when enabling tracing.</span></span> <span data-ttu-id="00f20-133">推奨事項については、次を参照してください。、[メッセージとインスタンス データ追跡のベスト プラクティス](../../core/best-practices-for-message-and-instance-data-tracking.md)です。</span><span class="sxs-lookup"><span data-stu-id="00f20-133">For recommendations, see the [Best Practices for Message and Instance Data Tracking](../../core/best-practices-for-message-and-instance-data-tracking.md).</span></span>  
  
## <a name="wcf-tracing-within-the-adapter"></a><span data-ttu-id="00f20-134">アダプター内で WCF トレース</span><span class="sxs-lookup"><span data-stu-id="00f20-134">WCF tracing within the adapter</span></span>  
 <span data-ttu-id="00f20-135">アダプターは、エラー、警告、および情報メッセージなど、トレース ファイルに有用な情報のさまざまなカテゴリをログオンします。</span><span class="sxs-lookup"><span data-stu-id="00f20-135">The adapters log different categories of useful information to the trace file such as errors, warnings, and information messages.</span></span> <span data-ttu-id="00f20-136">このような情報は、アダプター内のプロセス フローを理解し、アダプターに関する問題の診断に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="00f20-136">Such information is useful in understanding the process flow within the adapter and diagnosing issues with the adapter.</span></span> <span data-ttu-id="00f20-137">アクティブ化することができます、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]とアダプターが BizTalk アプリケーションと WCF サービスの抜粋をそれぞれの構成ファイルに追加することによってモデル アプリケーション用にトレースされます。</span><span class="sxs-lookup"><span data-stu-id="00f20-137">You can activate the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] and adapter tracing for BizTalk applications and WCF service model applications by adding an excerpt to the respective configuration files.</span></span> <span data-ttu-id="00f20-138">また、デザイン時と実行時の両方でトレースを有効にできます。</span><span class="sxs-lookup"><span data-stu-id="00f20-138">Also, you can enable tracing both at design-time and run-time.</span></span>  
  
-   <span data-ttu-id="00f20-139">**デザイン時にトレース**です。</span><span class="sxs-lookup"><span data-stu-id="00f20-139">**Tracing at design-time**.</span></span> <span data-ttu-id="00f20-140">デザイン時機能を使用することは、 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="00f20-140">For the design-time experience, you may use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], or the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span></span> <span data-ttu-id="00f20-141">これらすべてのツールを使用できる[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="00f20-141">All these tools can be used from [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="00f20-142">そのため、デザイン時の操作のトレースを有効にする必要がありますに追加する抜粋にある devenv.exe.config ファイル*\<インストール ドライブ >*: \Program Files\Microsoft Visual Studio  *\<バージョン >*\Common7\IDE です。</span><span class="sxs-lookup"><span data-stu-id="00f20-142">So, to enable tracing for the design-time experience, you must add the excerpt to the devenv.exe.config file located in *\<installation drive>*:\Program Files\Microsoft Visual Studio *\<version>*\Common7\IDE.</span></span>  
  
-   <span data-ttu-id="00f20-143">**実行時にトレース**です。</span><span class="sxs-lookup"><span data-stu-id="00f20-143">**Tracing at run-time**.</span></span> <span data-ttu-id="00f20-144">実行時のトレースを使用しているアプリケーションによっては抜粋を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="00f20-144">For run-time tracing, you must add the excerpt depending on the application you are using.</span></span>  
  
    -   <span data-ttu-id="00f20-145">[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]アプリケーションに BizTalk 構成ファイルで、通常 BTSNTSvc.exe.config の抜粋を追加する必要があります。[!INCLUDE[btsbiztalkserver2006r2](../../includes/btsbiztalkserver2006r2-md.md)]、このファイルは通常 \<インストール ドライブ >: \Program Files\Microsoft[!INCLUDE[btsBizTalkServer2006](../../includes/btsbiztalkserver2006-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="00f20-145">For a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] applications, you must add the excerpt to the BizTalk configuration file, typically BTSNTSvc.exe.config. For [!INCLUDE[btsbiztalkserver2006r2](../../includes/btsbiztalkserver2006r2-md.md)], this file is available typically under \<installation drive>:\Program Files\Microsoft [!INCLUDE[btsBizTalkServer2006](../../includes/btsbiztalkserver2006-md.md)].</span></span> <span data-ttu-id="00f20-146">[!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)]、このファイルは通常 \<インストール ドライブ >: \Program Files\Microsoft[!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="00f20-146">For [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)], this file is available typically under \<installation drive>:\Program Files\Microsoft [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)].</span></span>  
  
    -   <span data-ttu-id="00f20-147">WCF サービス モデル .NET アプリケーションのプロジェクトの app.config ファイルの抜粋を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="00f20-147">For a WCF service model .NET application, you must add the excerpt to the app.config file of your project.</span></span>  
  
 <span data-ttu-id="00f20-148">有効にする[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]とアダプターのトレース、内で次の抜粋を追加、`<configuration>`タグ。</span><span class="sxs-lookup"><span data-stu-id="00f20-148">To enable [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] and adapter tracing, add the following excerpt within the `<configuration>` tag:</span></span>  
  
```  
<system.diagnostics>  
    <sources>  
      <source name="Microsoft.ServiceModel.Channels" switchValue="Error">  
        <listeners>  
          <add name="xml" />  
        </listeners>  
      </source>  
      <source name="Microsoft.Adapters.OracleEBS" switchValue="Information">  
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
  
 <span data-ttu-id="00f20-149">これは、C:\log\AdapterTrace.svclog に WCF トレースを保存します。</span><span class="sxs-lookup"><span data-stu-id="00f20-149">This saves the WCF traces to C:\log\AdapterTrace.svclog.</span></span>  
  
## <a name="viewing-the-traces"></a><span data-ttu-id="00f20-150">トレースの表示</span><span class="sxs-lookup"><span data-stu-id="00f20-150">Viewing the traces</span></span>  
 <span data-ttu-id="00f20-151">Windows Communication Foundation (WCF) サービス トレース ビューアー ツールを使用するには、トレースを表示します。</span><span class="sxs-lookup"><span data-stu-id="00f20-151">You can use the Windows Communication Foundation (WCF) Service Trace Viewer tool to view the traces.</span></span> <span data-ttu-id="00f20-152">[サービス トレース ビューアーを使用して相関トレースの表示とトラブルシューティング](https://msdn.microsoft.com/library/aa751795.aspx)このツールの詳細を提供します。</span><span class="sxs-lookup"><span data-stu-id="00f20-152">[Using Service Trace Viewer for Viewing Correlated Traces and Troubleshooting](https://msdn.microsoft.com/library/aa751795.aspx) provides more details on this tool.</span></span>  
  
## <a name="configuring-tracking-for-biztalk-applications"></a><span data-ttu-id="00f20-153">BizTalk アプリケーションの追跡の構成</span><span class="sxs-lookup"><span data-stu-id="00f20-153">Configuring tracking for BizTalk applications</span></span>  
 <span data-ttu-id="00f20-154">BizTalk Server 管理コンソールでは、受信ポートと送信ポートなどの項目に対してさまざまな追跡オプションを構成できます。</span><span class="sxs-lookup"><span data-stu-id="00f20-154">The BizTalk Server Administration console lets you configure various tracking options for items such as send ports and receive ports.</span></span> <span data-ttu-id="00f20-155">追跡構成設定を使用すると、着信および発信のイベント データ、メッセージのプロパティ、メッセージ本文、およびオーケストレーションを追跡します。</span><span class="sxs-lookup"><span data-stu-id="00f20-155">The tracking configuration settings enable you to track inbound and outbound event data, message properties, message bodies, and orchestrations.</span></span> <span data-ttu-id="00f20-156">BizTalk アプリケーションの追跡の構成の詳細については、次を参照してください。[管理し、成果物を追跡](../../core/managing-artifacts.md)です。</span><span class="sxs-lookup"><span data-stu-id="00f20-156">For more information about configuring tracking for BizTalk applications, see [Managing and tracking your artifacts](../../core/managing-artifacts.md).</span></span>  
  
 <span data-ttu-id="00f20-157">グループ ハブを使用することもできます。[メッセージとインスタンス データの履歴を表示](../../core/viewing-tracked-message-and-instance-data.md)、などのベスト プラクティスは、追跡クエリ、および詳細を保存します。</span><span class="sxs-lookup"><span data-stu-id="00f20-157">You can also use Group Hub to [view tracked message and instance data](../../core/viewing-tracked-message-and-instance-data.md), including best practices, saving tracking queries, and more.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="00f20-158">参照</span><span class="sxs-lookup"><span data-stu-id="00f20-158">See Also</span></span>  
[<span data-ttu-id="00f20-159">アダプターのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="00f20-159">Troubleshooting the adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/troubleshooting-the-oracle-ebs-adapter.md)