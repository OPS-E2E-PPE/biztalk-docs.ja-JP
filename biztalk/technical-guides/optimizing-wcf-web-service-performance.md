---
title: WCF Web サービスのパフォーマンスを最適化する |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 93947cef-469c-4126-85a5-06456fa37443
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 413642931fcf9580ade280c2e7b3472599859d8d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22299418"
---
# <a name="optimizing-wcf-web-service-performance"></a><span data-ttu-id="58db2-102">WCF Web サービスのパフォーマンスを最適化します。</span><span class="sxs-lookup"><span data-stu-id="58db2-102">Optimizing WCF Web Service Performance</span></span>
<span data-ttu-id="58db2-103">WCF サービスは、パフォーマンスに影響するための多数の構成パラメーターを公開します。</span><span class="sxs-lookup"><span data-stu-id="58db2-103">WCF services expose numerous configuration parameters that affect performance.</span></span> <span data-ttu-id="58db2-104">このトピックでは、WCF サービスのパフォーマンスを向上させるためにこれらの構成パラメーターの最適な値の設定の一般的なガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="58db2-104">This topic provides general guidance for setting optimal values for these configuration parameters to improve performance of WCF services.</span></span>  
  
## <a name="implement-servicethrottling-behavior-for-backend-wcf-services"></a><span data-ttu-id="58db2-105">バックエンド WCF サービスの serviceThrottling 動作を実装します。</span><span class="sxs-lookup"><span data-stu-id="58db2-105">Implement serviceThrottling behavior for backend WCF services</span></span>  
 <span data-ttu-id="58db2-106">バックエンド WCF サービスの serviceThrottling 動作を実装します。</span><span class="sxs-lookup"><span data-stu-id="58db2-106">Implement serviceThrottling behavior for backend WCF services.</span></span> <span data-ttu-id="58db2-107">サービスの調整では、リソースの割り当てを適用して、バックエンド WCF サーバーの負荷を均等にできます。</span><span class="sxs-lookup"><span data-stu-id="58db2-107">Service throttling allows you to even out the load on your backend WCF servers and to enforce resource allocation.</span></span> <span data-ttu-id="58db2-108">バックエンド WCF サービスの serviceThrottling 動作がの値を変更することによって構成されて、 **maxConcurrentCalls**、 **maxConcurrentSessions**、および**maxConcurrentInstances** WCF サービスの構成ファイル内のパラメーターです。</span><span class="sxs-lookup"><span data-stu-id="58db2-108">serviceThrottling behavior for backend WCF services is configured by modifying the values for the **maxConcurrentCalls**, **maxConcurrentSessions**, and **maxConcurrentInstances** parameters in the config file for the WCF service.</span></span> <span data-ttu-id="58db2-109">設定**maxConcurrentCalls**、 **maxConcurrentSessions**、および**maxConcurrentInstances** 16 より大きい値に \* Cpu または CPU の数のコアです。</span><span class="sxs-lookup"><span data-stu-id="58db2-109">Set **maxConcurrentCalls**, **maxConcurrentSessions**, and **maxConcurrentInstances** to a value greater than 16 \* the number of CPUs or CPU cores.</span></span> <span data-ttu-id="58db2-110">たとえば、8 の CPU コアを備えたコンピューターで次のように設定します**maxConcurrentCalls**、 **maxConcurrentSessions**、および**maxConcurrentInstances** 128 (16 \* 8 = 128) より大きい値に。次のようにします。</span><span class="sxs-lookup"><span data-stu-id="58db2-110">For example, on a computer with 8 CPU cores, set **maxConcurrentCalls**, **maxConcurrentSessions**, and **maxConcurrentInstances** to a value greater than 128 (16 \* 8 = 128) as follows:</span></span>  
  
```  
<serviceThrottling  
maxConcurrentCalls="200"  
maxConcurrentSessions="200"  
maxConcurrentInstances="200" />  
```  
  
## <a name="increase-the-default-values-for-the-nettcpbindinglistenbacklog-and-nettcpbindingmaxconnections-properties-in-the-backend-wcf-service-webconfig-file"></a><span data-ttu-id="58db2-111">バックエンド WCF サービスの web.config ファイルで NetTcpBinding.ListenBacklog および NetTcpBinding.MaxConnections プロパティの既定値を増やす</span><span class="sxs-lookup"><span data-stu-id="58db2-111">Increase the default values for the NetTcpBinding.ListenBacklog and NetTcpBinding.MaxConnections properties in the backend WCF service web.config file</span></span>  
 <span data-ttu-id="58db2-112">**NetTcpBinding.ListenBacklog**プロパティ保留可能なキューに置かれた接続要求の最大数を制御する Web サービスです。</span><span class="sxs-lookup"><span data-stu-id="58db2-112">The **NetTcpBinding.ListenBacklog** property controls the maximum number of queued connection requests that can be pending for a Web service.</span></span> <span data-ttu-id="58db2-113">**NetTcpBinding.MaxConnections**プロパティは、クライアントでの後続の再利用のためにプールできる接続の最大数と、サーバー上でディスパッチを保留できる接続の最大数を制御します。</span><span class="sxs-lookup"><span data-stu-id="58db2-113">The **NetTcpBinding.MaxConnections** property controls the maximum number of connections to be pooled for subsequent reuse on the client and the maximum number of connections allowed to be pending dispatch on the server.</span></span> <span data-ttu-id="58db2-114">これらの各プロパティは、既定値のドキュメントを高スループットを必要とするシナリオを処理するために特別に、最適でない可能性のある 10 を使用します。</span><span class="sxs-lookup"><span data-stu-id="58db2-114">Each of these properties uses a default value of 10 which may be suboptimal, especially for document processing scenarios that require high throughput.</span></span>  
  
 <span data-ttu-id="58db2-115">実装している WCF サービスを使用する高スループット、ドキュメント処理のシナリオでこれらのプロパティの既定値を増やすことを検討、 **netTcpBinding**クラスをバインドします。</span><span class="sxs-lookup"><span data-stu-id="58db2-115">Consider increasing the default value of these properties for high-throughput, document-processing scenarios that use WCF services which implement the **netTcpBinding** binding class.</span></span>  
  
 <span data-ttu-id="58db2-116">次の例では、両方の**listenBacklog**と**maxConnections**パラメーターは、「200」の値に設定されます。</span><span class="sxs-lookup"><span data-stu-id="58db2-116">In the following example, both the **listenBacklog** and **maxConnections** parameters are set to a value of “200”.</span></span>  
  
```  
<netTcpBinding>  
   <binding name="netTcpBinding"  
      closeTimeout="00:10:00"  
      openTimeout="00:10:00"  
      receiveTimeout="00:10:00"  
      sendTimeout="00:10:00"  
      transactionFlow="false"  
      transferMode="Buffered"  
      transactionProtocol="OleTransactions"  
      hostNameComparisonMode="StrongWildcard"  
      listenBacklog="200"  
      maxBufferPoolSize="1048576"  
      maxBufferSize="10485760"  
      maxConnections="200"  
      maxReceivedMessageSize="10485760">  
      <readerQuotas  
         maxDepth="32"  
         maxStringContentLength="8192"  
         maxArrayLength="16384"  
         maxBytesPerRead="4096"  
         maxNameTableCharCount="16384" />  
      <reliableSession  
         ordered="true"  
         inactivityTimeout="00:10:00"  
         enabled="false" />  
      <security mode="None">  
         <transport clientCredentialType="Windows" protectionLevel="EncryptAndSign" />  
         <message clientCredentialType="Windows" />  
      </security>  
   </binding>  
</netTcpBinding>  
```  
  
 <span data-ttu-id="58db2-117">NetTcpBinding.ListenBacklog プロパティの詳細については、次を参照してください。 [NetTcpBinding.ListenBacklog プロパティ](http://go.microsoft.com/fwlink/?LinkId=157752)(http://go.microsoft.com/fwlink/?LinkId=157752) MSDN のです。</span><span class="sxs-lookup"><span data-stu-id="58db2-117">For more information about the NetTcpBinding.ListenBacklog property, see [NetTcpBinding.ListenBacklog Property](http://go.microsoft.com/fwlink/?LinkId=157752) (http://go.microsoft.com/fwlink/?LinkId=157752) on MSDN.</span></span>  
  
 <span data-ttu-id="58db2-118">NetTcpBinding.MaxConnections プロパティの詳細については、次を参照してください。 [NetTcpBinding.MaxConnections プロパティ](http://go.microsoft.com/fwlink/?LinkID=157751)(http://go.microsoft.com/fwlink/?LinkID=157751) MSDN のです。</span><span class="sxs-lookup"><span data-stu-id="58db2-118">For more information about the NetTcpBinding.MaxConnections property, see [NetTcpBinding.MaxConnections Property](http://go.microsoft.com/fwlink/?LinkID=157751) (http://go.microsoft.com/fwlink/?LinkID=157751) on MSDN.</span></span>  
  
## <a name="eliminate-aspnet-httpmodules-that-are-not-required-to-run-wcf-web-services"></a><span data-ttu-id="58db2-119">WCF Web サービスを実行する必要はありません ASP.NET httpModules を排除します。</span><span class="sxs-lookup"><span data-stu-id="58db2-119">Eliminate ASP.NET httpModules that are not required to run WCF Web services</span></span>  
 <span data-ttu-id="58db2-120">既定では、いくつかの ASP.NET httpModules は、要求パイプラインとクラシックまたは統合パイプライン IIS 7.5 または 7.0 の IIS 6.0 で定義されます。</span><span class="sxs-lookup"><span data-stu-id="58db2-120">By default, several ASP.NET httpModules are defined in the Request Pipeline in IIS 6.0 and in the Classic or Integrated Pipeline in IIS 7.5/7.0.</span></span> <span data-ttu-id="58db2-121">これらのコンポーネントは、途中受信し、すべての着信要求を処理します。</span><span class="sxs-lookup"><span data-stu-id="58db2-121">These components intercept and process all incoming requests.</span></span> <span data-ttu-id="58db2-122">既定のモジュールは、64 ビットの ASP の %windir%\Microsoft.NET\Framework64\v2.0.50727\CONFIG フォルダーと 32 ビット ASP.NET アプリケーションに対して %windir%\Microsoft.NET\Framework\v2.0.50727\CONFIG フォルダーに含まれる、web.config ファイルで定義されます。NET アプリケーションを次のスニペットで示すようにします。</span><span class="sxs-lookup"><span data-stu-id="58db2-122">The default modules are defined in the web.config file contained in the %windir%\Microsoft.NET\Framework\v2.0.50727\CONFIG folder for 32-bit ASP.NET applications and in the %windir%\Microsoft.NET\Framework64\v2.0.50727\CONFIG folder for 64-bit ASP.NET applications, as shown by the following snippet.</span></span>  
  
```  
<httpModules>  
<add name="OutputCache" type="System.Web.Caching.OutputCacheModule"/>  
<add name="Session" type="System.Web.SessionState.SessionStateModule"/>  
<add name="WindowsAuthentication" type="System.Web.Security.WindowsAuthenticationModule"/>  
<add name="FormsAuthentication" type="System.Web.Security.FormsAuthenticationModule"/>  
<add name="PassportAuthentication" type="System.Web.Security.PassportAuthenticationModule"/>  
<add name="RoleManager" type="System.Web.Security.RoleManagerModule"/>  
<add name="UrlAuthorization" type="System.Web.Security.UrlAuthorizationModule"/>  
<add name="FileAuthorization" type="System.Web.Security.FileAuthorizationModule"/>  
<add name="AnonymousIdentification" type="System.Web.Security.AnonymousIdentificationModule"/>  
<add name="Profile" type="System.Web.Profile.ProfileModule"/>  
<add name="ErrorHandlerModule" type="System.Web.Mobile.ErrorHandlerModule, System.Web.Mobile, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a"/>  
<add name="ServiceModel" type="System.ServiceModel.Activation.HttpModule, System.ServiceModel, Version=3.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"/>  
</httpModules>  
```  
  
 <span data-ttu-id="58db2-123">ほとんどのシナリオでは、これらのモジュールのすべてをロードする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="58db2-123">In most scenarios it is not necessary to load all of these modules.</span></span> <span data-ttu-id="58db2-124">したがって、可能であれば WCF Web サービスを実行するときに、次の Httpmodule を排除することでパフォーマンスを向上させる。</span><span class="sxs-lookup"><span data-stu-id="58db2-124">Therefore, it is possible to improve performance by eliminating the following httpModules when running WCF Web services:</span></span>  
  
-   <span data-ttu-id="58db2-125">Session</span><span class="sxs-lookup"><span data-stu-id="58db2-125">Session</span></span>  
  
-   <span data-ttu-id="58db2-126">WindowsAuthentication</span><span class="sxs-lookup"><span data-stu-id="58db2-126">WindowsAuthentication</span></span>  
  
-   <span data-ttu-id="58db2-127">FormsAuthentication</span><span class="sxs-lookup"><span data-stu-id="58db2-127">FormsAuthentication</span></span>  
  
-   <span data-ttu-id="58db2-128">PassportAuthentication</span><span class="sxs-lookup"><span data-stu-id="58db2-128">PassportAuthentication</span></span>  
  
-   <span data-ttu-id="58db2-129">RoleManager</span><span class="sxs-lookup"><span data-stu-id="58db2-129">RoleManager</span></span>  
  
-   <span data-ttu-id="58db2-130">AnonymousIdentification</span><span class="sxs-lookup"><span data-stu-id="58db2-130">AnonymousIdentification</span></span>  
  
-   <span data-ttu-id="58db2-131">プロファイル</span><span class="sxs-lookup"><span data-stu-id="58db2-131">Profile</span></span>  
  
## <a name="use-the-wcf-modulehandler-registration-tool-to-configure-wcf-moduleshandlers-and-improve-scalability-of-iis-7570-hosted-wcf-services"></a><span data-ttu-id="58db2-132">ハンドラーの登録ツールを WCF モジュール/ハンドラーを構成し、IIS 7.5 または 7.0 のスケーラビリティを向上させるには、WCF サービスがホストされている/WCF モジュールを使用します。</span><span class="sxs-lookup"><span data-stu-id="58db2-132">Use the WCF Module/Handler Registration tool to configure WCF modules/handlers and improve scalability of IIS 7.5/7.0 hosted WCF services</span></span>  
 <span data-ttu-id="58db2-133">WCF モジュールまたはハンドラーの登録ツールがダウンロード[http://go.microsoft.com/fwlink/?LinkId=157593](http://go.microsoft.com/fwlink/?LinkId=157593) (http://go.microsoft.com/fwlink/?LinkId=157593)。</span><span class="sxs-lookup"><span data-stu-id="58db2-133">The WCF Module/Handler Registration Tool is available for download at [http://go.microsoft.com/fwlink/?LinkId=157593](http://go.microsoft.com/fwlink/?LinkId=157593) (http://go.microsoft.com/fwlink/?LinkId=157593).</span></span> <span data-ttu-id="58db2-134">このユーティリティを使用して、インストール、リスト、または、次の WCF モジュールを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="58db2-134">This utility can be used to install, list, or configure the following WCF modules:</span></span>  
  
-   <span data-ttu-id="58db2-135">WCF 同期 HTTP モジュールとハンドラー</span><span class="sxs-lookup"><span data-stu-id="58db2-135">WCF Synchronous HTTP module and handler</span></span>  
  
-   <span data-ttu-id="58db2-136">WCF の非同期 HTTP モジュールとハンドラー</span><span class="sxs-lookup"><span data-stu-id="58db2-136">WCF Asynchronous HTTP module and handler</span></span>  
  
-   <span data-ttu-id="58db2-137">WCF HTTP モジュールとハンドラー</span><span class="sxs-lookup"><span data-stu-id="58db2-137">WCF HTTP module and handler</span></span>  
  
 <span data-ttu-id="58db2-138">詳細については、ハンドラーを使用して、非同期 WCF HTTP モジュール/IIS 7.5 または 7.0 のスケーラビリティを向上させるには、WCF サービスがホストされている、Wenlong Dong のブログを参照してください[Orcas SP1 の改善: 非同期 WCF HTTP モジュールとハンドラーより優れた IIS7 用サーバーのスケーラビリティ](http://go.microsoft.com/fwlink/?LinkId=157428)(http://go.microsoft.com/fwlink/?LinkId=157428)。</span><span class="sxs-lookup"><span data-stu-id="58db2-138">For more information about using the asynchronous WCF HTTP modules/handlers to improve the scalability of IIS 7.5/7.0 hosted WCF services, see Wenlong Dong’s blog [Orcas SP1 Improvement: Asynchronous WCF HTTP Module/Handler for IIS7 for Better Server Scalability](http://go.microsoft.com/fwlink/?LinkId=157428) (http://go.microsoft.com/fwlink/?LinkId=157428).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58db2-139">参照</span><span class="sxs-lookup"><span data-stu-id="58db2-139">See Also</span></span>  
 [<span data-ttu-id="58db2-140">BizTalk Server WCF アダプターのパフォーマンスを最適化します。</span><span class="sxs-lookup"><span data-stu-id="58db2-140">Optimizing BizTalk Server WCF Adapter Performance</span></span>](../technical-guides/optimizing-biztalk-server-wcf-adapter-performance.md)