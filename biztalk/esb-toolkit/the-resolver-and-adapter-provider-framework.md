---
title: ESB リゾルバーとアダプターのプロバイダー フレームワーク |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fb7ea42e-b32c-40a8-b36b-c349f56f6edd
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 95134a1f806398f14a5596149eb605e2de20cac2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37002803"
---
# <a name="the-resolver-and-adapter-provider-framework"></a><span data-ttu-id="bb972-102">リゾルバーとアダプターのプロバイダー フレームワーク</span><span class="sxs-lookup"><span data-stu-id="bb972-102">The Resolver and Adapter Provider Framework</span></span>
<span data-ttu-id="bb972-103">リゾルバーとアダプターのプロバイダー フレームワークは、スケジュール、変換、およびエンドポイントの解決とルーティングをサポートします。</span><span class="sxs-lookup"><span data-stu-id="bb972-103">The Resolver and Adapter Provider Framework supports itinerary, transformation, and endpoint resolution and routing.</span></span> <span data-ttu-id="bb972-104">フレームワークを動的にエンドポイントを解決および送信アダプターのプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="bb972-104">The framework can dynamically resolve endpoints and set outbound adapter properties.</span></span> <span data-ttu-id="bb972-105">競合回避モジュールの後にコンポーネント (たとえば、送信の Web サービス エンドポイントを検索する Universal Description, Discovery, and Integration [UDDI] を使用して) エンドポイントの解決、アダプター プロバイダーのコンポーネントが登録済みの BizTalk Server の特定のプロパティを設定アダプター。</span><span class="sxs-lookup"><span data-stu-id="bb972-105">After a resolver component resolves an endpoint (for example, using Universal Description, Discovery, and Integration [UDDI] to look up an outbound Web service endpoint), an adapter provider component sets specific properties of registered BizTalk Server adapters.</span></span> <span data-ttu-id="bb972-106">たとえば、Wcf-basichttp アダプターのプロバイダーは BizTalk 固有のメッセージ エンドポイントが、特定の BizTalk アダプターを使用する URI のコンテキスト プロパティの設定を行いますFTP アダプターのプロバイダーは、FTP アダプターに固有のプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="bb972-106">For example, the WCF-BasicHttp adapter provider is responsible for setting the BizTalk-specific message context properties for the endpoint URI that will use the specific BizTalk adapter; the FTP adapter provider is responsible for setting the properties specific to the FTP adapter.</span></span>  
  
 <span data-ttu-id="bb972-107">リゾルバーとアダプターのプロバイダー フレームワークの 1 つの目的は、解決とか、メッセージ レベルで、BizTalk オーケストレーションを使用しなくても、またはオーケストレーション レベルでのルーティングをサポートするためにです。</span><span class="sxs-lookup"><span data-stu-id="bb972-107">One goal of the Resolver and Adapter Provider Framework is to support resolution and routing at either the messaging level, without requiring the use of BizTalk orchestrations, or at the orchestration level.</span></span> <span data-ttu-id="bb972-108">どちらの場合は、プラグ可能なフレームワークは、簡単な開発、展開、および新しいリゾルバーとアダプター プロバイダーの登録を提供します。</span><span class="sxs-lookup"><span data-stu-id="bb972-108">In both cases, the pluggable framework provides easy development, deployment, and registration of new resolvers and adapter providers.</span></span> <span data-ttu-id="bb972-109">リゾルバーとアダプターのプロバイダーをすべて明確に定義されたインターフェイスを実装して、要求時に読み込まれた構成ファイルでの登録の過程で、実行時に。</span><span class="sxs-lookup"><span data-stu-id="bb972-109">All resolvers and adapter providers implement well-defined interfaces and are demand-loaded at run time through registration in the configuration files.</span></span>  
  
 <span data-ttu-id="bb972-110">ESB ディスパッチャーおよび ESB ディスパッチャー逆アセンブル パイプライン コンポーネントは、競合回避モジュール マネージャーに SOAP ヘッダーの旅程またはパイプラインの構成のいずれかから接続文字列を渡すことによって、リゾルバーとアダプターのプロバイダー フレームワークを使用します。</span><span class="sxs-lookup"><span data-stu-id="bb972-110">Both the ESB Dispatcher and ESB Dispatcher Disassemble pipeline components use the Resolver and Adapter Provider Framework by passing the connection string from either the itinerary SOAP header or the pipeline configuration to the Resolver Manager.</span></span>  
  
 <span data-ttu-id="bb972-111">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]構成に登録されているすべてのリゾルバーとアダプター プロバイダーの詳細が含まれています。</span><span class="sxs-lookup"><span data-stu-id="bb972-111">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] configuration contains details of all registered resolvers and adapter providers.</span></span> <span data-ttu-id="bb972-112">実行時、競合回避モジュールのマネージャー、およびアダプター マネージャーの構成ファイルから、登録済みのリゾルバーとアダプター プロバイダーの詳細を読みで、適切なアセンブリを読み込むし、BizTalk ホスト レベルのキャッシュに格納します。</span><span class="sxs-lookup"><span data-stu-id="bb972-112">At run time, the resolver managers and adapter managers read details of the registered resolvers and adapter providers from the configuration files, load the appropriate assemblies, and store them in a BizTalk host–level cache.</span></span> <span data-ttu-id="bb972-113">このキャッシュの手法は、繰り返しの構成ファイルの読み取りとすべての送信メッセージに対してアセンブリの読み込みの要件を削除します。</span><span class="sxs-lookup"><span data-stu-id="bb972-113">This caching technique removes the requirement for repeated reading of configuration files and loading of assemblies for every submitted message.</span></span>  
  
 <span data-ttu-id="bb972-114">リゾルバーとアダプターのプロバイダー フレームワークの動作とカスタム競合回避モジュールとアダプターのプロバイダーを作成して拡張する方法を表示する方法の詳細については[を変更して、BizTalk ESB Toolkit の拡張](../esb-toolkit/modifying-and-extending-the-biztalk-esb-toolkit.md)します。</span><span class="sxs-lookup"><span data-stu-id="bb972-114">For more information about how the Resolver and Adapter Provider Framework works and how you can extend it by creating custom resolvers and adapter providers, see [Modifying and Extending the BizTalk ESB Toolkit](../esb-toolkit/modifying-and-extending-the-biztalk-esb-toolkit.md).</span></span>  
  
## <a name="supported-resolution-mechanisms-resolvers"></a><span data-ttu-id="bb972-115">サポートされている解決メカニズム (競合回避モジュール)</span><span class="sxs-lookup"><span data-stu-id="bb972-115">Supported Resolution Mechanisms (Resolvers)</span></span>  
 <span data-ttu-id="bb972-116">BizTalk ESB Toolkit には、次の競合回避モジュールが含まれています:**静的、UDDI、UDDI3、XPATH、BRE、BRI、日程表、日程静的**と**LDAP**します。</span><span class="sxs-lookup"><span data-stu-id="bb972-116">The BizTalk ESB Toolkit includes the following resolvers: **STATIC, UDDI, UDDI3, XPATH, BRE, BRI, ITINERARY, ITINERARY-STATIC** and **LDAP**.</span></span>  
  
 <span data-ttu-id="bb972-117">競合回避モジュールの接続文字列から成る常に、**モニカー** (など**BRE**) 後に":\\\\"と接続または処理の詳細。</span><span class="sxs-lookup"><span data-stu-id="bb972-117">A resolver's connection string always consists of a **moniker** (such as **BRE**) followed by ":\\\\" and the connection or processing details.</span></span> <span data-ttu-id="bb972-118">モニカーでは、構成ファイルに関連付けられている競合回避モジュールの定義と一致します。</span><span class="sxs-lookup"><span data-stu-id="bb972-118">The moniker matches the definition of the associated resolver in the configuration file.</span></span> <span data-ttu-id="bb972-119">各接続文字列に関連付けられているプロパティは一意であると、すべてのプロパティが必要です。</span><span class="sxs-lookup"><span data-stu-id="bb972-119">The properties associated with each connection string are unique, and not all properties are required.</span></span> <span data-ttu-id="bb972-120">競合回避モジュールの各スキーマは、ESB で確認できます。Resolvers.Schemas プロジェクトです。</span><span class="sxs-lookup"><span data-stu-id="bb972-120">The schema for each of the resolvers can be found in the ESB.Resolvers.Schemas project.</span></span>  
  
 <span data-ttu-id="bb972-121">接続文字列の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="bb972-121">The following are examples of connection strings:</span></span>  
  
- <span data-ttu-id="bb972-122">**静的**</span><span class="sxs-lookup"><span data-stu-id="bb972-122">**STATIC**</span></span>  
  
   <span data-ttu-id="bb972-123">STATIC:\\\TransportType=;</span><span class="sxs-lookup"><span data-stu-id="bb972-123">STATIC:\\\TransportType=;</span></span>  
  
   <span data-ttu-id="bb972-124">TransportLocation =<http://localhost/ESB.CanadianServices/SubmitPOService.asmx>;</span><span class="sxs-lookup"><span data-stu-id="bb972-124">TransportLocation=<http://localhost/ESB.CanadianServices/SubmitPOService.asmx>;</span></span>  
  
   <span data-ttu-id="bb972-125">アクション = です。</span><span class="sxs-lookup"><span data-stu-id="bb972-125">Action=;</span></span>  
  
   <span data-ttu-id="bb972-126">EndPointConfig = です。</span><span class="sxs-lookup"><span data-stu-id="bb972-126">EndPointConfig=;</span></span>  
  
   <span data-ttu-id="bb972-127">JaxRpcResponse = false。</span><span class="sxs-lookup"><span data-stu-id="bb972-127">JaxRpcResponse=false;</span></span>  
  
   <span data-ttu-id="bb972-128">MessageExchangePattern = です。</span><span class="sxs-lookup"><span data-stu-id="bb972-128">MessageExchangePattern=;</span></span>  
  
   <span data-ttu-id="bb972-129">TargetNamespace=<http://globalbank.esb.dynamicresolution.com/canadianservices/>;</span><span class="sxs-lookup"><span data-stu-id="bb972-129">TargetNamespace=<http://globalbank.esb.dynamicresolution.com/canadianservices/>;</span></span>  
  
   <span data-ttu-id="bb972-130">TransformType=;</span><span class="sxs-lookup"><span data-stu-id="bb972-130">TransformType=;</span></span>  
  
- <span data-ttu-id="bb972-131">**UDDI**</span><span class="sxs-lookup"><span data-stu-id="bb972-131">**UDDI**</span></span>  
  
   <span data-ttu-id="bb972-132">UDDI:\\\serverUrl=<http://localhost:9901/rmengine>;</span><span class="sxs-lookup"><span data-stu-id="bb972-132">UDDI:\\\serverUrl=<http://localhost:9901/rmengine>;</span></span>  
  
   <span data-ttu-id="bb972-133">serviceName = OrderPurchaseWebService;</span><span class="sxs-lookup"><span data-stu-id="bb972-133">serviceName=OrderPurchaseWebService;</span></span>  
  
   <span data-ttu-id="bb972-134">serviceProvider Microsoft プラクティス ESB を =</span><span class="sxs-lookup"><span data-stu-id="bb972-134">serviceProvider=Microsoft Practices ESB</span></span>  
  
- <span data-ttu-id="bb972-135">**[XPath]**</span><span class="sxs-lookup"><span data-stu-id="bb972-135">**XPATH**</span></span>  
  
   <span data-ttu-id="bb972-136">XPATH:\\\TransportType=;</span><span class="sxs-lookup"><span data-stu-id="bb972-136">XPATH:\\\TransportType=;</span></span>  
  
   `TransportLocation=/*[local-name()='OrderDoc' and namespace-uri()='http://globalbank.esb.dynamicresolution.com/northamericanservices/']/*[local-name()='ID' and namespace-uri()='http://globalbank.esb.dynamicresolution.com/northamericanservices/'];`  
  
   <span data-ttu-id="bb972-137">アクション = です。</span><span class="sxs-lookup"><span data-stu-id="bb972-137">Action=;</span></span>  
  
   <span data-ttu-id="bb972-138">EndPointConfig = です。</span><span class="sxs-lookup"><span data-stu-id="bb972-138">EndPointConfig=;</span></span>  
  
   <span data-ttu-id="bb972-139">JaxRpcResponse = です。</span><span class="sxs-lookup"><span data-stu-id="bb972-139">JaxRpcResponse=;</span></span>  
  
   <span data-ttu-id="bb972-140">MessageExchangePattern = です。</span><span class="sxs-lookup"><span data-stu-id="bb972-140">MessageExchangePattern=;</span></span>  
  
   `TargetNamespace=/*[local-name()='OrderDoc' and namespace-uri()='http://globalbank.esb.dynamicresolution.com/northamericanservices/']/*[local-name()='customerName' and namespace-uri()='http://globalbank.esb.dynamicresolution.com/northamericanservices/'];`  
  
   <span data-ttu-id="bb972-141">TransformType=;</span><span class="sxs-lookup"><span data-stu-id="bb972-141">TransformType=;</span></span>  

- <span data-ttu-id="bb972-142">**BRE**</span><span class="sxs-lookup"><span data-stu-id="bb972-142">**BRE**</span></span>  
  
   <span data-ttu-id="bb972-143">BRE:\\\policy=GetCanadaEndPoint;</span><span class="sxs-lookup"><span data-stu-id="bb972-143">BRE:\\\policy=GetCanadaEndPoint;</span></span>  
  
   <span data-ttu-id="bb972-144">バージョン = です。</span><span class="sxs-lookup"><span data-stu-id="bb972-144">version=;</span></span>  
  
   <span data-ttu-id="bb972-145">useMsg=;</span><span class="sxs-lookup"><span data-stu-id="bb972-145">useMsg=;</span></span>  
  
- <span data-ttu-id="bb972-146">**BRI**</span><span class="sxs-lookup"><span data-stu-id="bb972-146">**BRI**</span></span>  
  
   <span data-ttu-id="bb972-147">BRI:\\\policy=ResolveItinerary;</span><span class="sxs-lookup"><span data-stu-id="bb972-147">BRI:\\\policy=ResolveItinerary;</span></span>  
  
   <span data-ttu-id="bb972-148">バージョン = です。</span><span class="sxs-lookup"><span data-stu-id="bb972-148">version=;</span></span>  
  
   <span data-ttu-id="bb972-149">useMsg=;</span><span class="sxs-lookup"><span data-stu-id="bb972-149">useMsg=;</span></span>  
  
- <span data-ttu-id="bb972-150">**旅行プラン**</span><span class="sxs-lookup"><span data-stu-id="bb972-150">**ITINERARY**</span></span>  
  
   <span data-ttu-id="bb972-151">ITINERARY:\\\name=TwoWayTestItinerary;</span><span class="sxs-lookup"><span data-stu-id="bb972-151">ITINERARY:\\\name=TwoWayTestItinerary;</span></span>  
  
   <span data-ttu-id="bb972-152">バージョン = です。</span><span class="sxs-lookup"><span data-stu-id="bb972-152">version=;</span></span>  
  
- <span data-ttu-id="bb972-153">**ITINERARY-STATIC**</span><span class="sxs-lookup"><span data-stu-id="bb972-153">**ITINERARY-STATIC**</span></span>  
  
   <span data-ttu-id="bb972-154">ITINERARY-STATIC:\\\name=TwoWayTestItinerary;</span><span class="sxs-lookup"><span data-stu-id="bb972-154">ITINERARY-STATIC:\\\name=TwoWayTestItinerary;</span></span>  
  
   <span data-ttu-id="bb972-155">バージョン = です。</span><span class="sxs-lookup"><span data-stu-id="bb972-155">version=;</span></span>  
  
- <span data-ttu-id="bb972-156">**LDAP**</span><span class="sxs-lookup"><span data-stu-id="bb972-156">**LDAP**</span></span>  
  
   <span data-ttu-id="bb972-157">LDAP:\\\TransportType=SMTP;</span><span class="sxs-lookup"><span data-stu-id="bb972-157">LDAP:\\\TransportType=SMTP;</span></span>  
  
   <span data-ttu-id="bb972-158">TransportLocation={mail}</span><span class="sxs-lookup"><span data-stu-id="bb972-158">TransportLocation={mail}</span></span>  
  
   <span data-ttu-id="bb972-159">フィルター = (&(objectClass=User) (| (userPrincipalName =yourname@domain.com)));</span><span class="sxs-lookup"><span data-stu-id="bb972-159">Filter=(&(objectClass=User)(|(userPrincipalName=yourname@domain.com)));</span></span>  
  
   <span data-ttu-id="bb972-160">SearchRoot = です。</span><span class="sxs-lookup"><span data-stu-id="bb972-160">SearchRoot=;</span></span>  
  
   <span data-ttu-id="bb972-161">SearchScope サブツリー; を =</span><span class="sxs-lookup"><span data-stu-id="bb972-161">SearchScope=Subtree;</span></span>  
  
   <span data-ttu-id="bb972-162">EndpointConfig サブジェクトを = = {メール} への旅行プランのテスト メッセージ (& a)</span><span class="sxs-lookup"><span data-stu-id="bb972-162">EndpointConfig=Subject=Itinerary Test Message to {mail}&</span></span> 
  
   <span data-ttu-id="bb972-163">SMTPAuthenticate = 0 (& a)</span><span class="sxs-lookup"><span data-stu-id="bb972-163">SMTPAuthenticate=0&</span></span>
  
   <span data-ttu-id="bb972-164">SMTPHost 127.0.0.1 を = (& a)</span><span class="sxs-lookup"><span data-stu-id="bb972-164">SMTPHost=127.0.0.1&</span></span>
  
   <span data-ttu-id="bb972-165">=test@globalbank.com(& A)</span><span class="sxs-lookup"><span data-stu-id="bb972-165">From=test@globalbank.com&</span></span>
  
   <span data-ttu-id="bb972-166">DeliveryReceipt = false (& a)</span><span class="sxs-lookup"><span data-stu-id="bb972-166">DeliveryReceipt=false&</span></span>
  
   <span data-ttu-id="bb972-167">MessagePartsAttachments = 0 (& a)</span><span class="sxs-lookup"><span data-stu-id="bb972-167">MessagePartsAttachments=0&</span></span>
  
   <span data-ttu-id="bb972-168">ReadReceipt = false。</span><span class="sxs-lookup"><span data-stu-id="bb972-168">ReadReceipt=false;</span></span>  
  
   <span data-ttu-id="bb972-169">ThrowErrorIfNotFound = false。</span><span class="sxs-lookup"><span data-stu-id="bb972-169">ThrowErrorIfNotFound=false;</span></span>  
  
   <span data-ttu-id="bb972-170">アクション = です。</span><span class="sxs-lookup"><span data-stu-id="bb972-170">Action=;</span></span>  
  
   <span data-ttu-id="bb972-171">JaxRpcResponse = false。</span><span class="sxs-lookup"><span data-stu-id="bb972-171">JaxRpcResponse=false;</span></span>  
  
   <span data-ttu-id="bb972-172">MessageExchangePattern = です。</span><span class="sxs-lookup"><span data-stu-id="bb972-172">MessageExchangePattern=;</span></span>  
  
   <span data-ttu-id="bb972-173">TargetNamespace = です。</span><span class="sxs-lookup"><span data-stu-id="bb972-173">TargetNamespace=;</span></span>  
  
   <span data-ttu-id="bb972-174">TransformType=;</span><span class="sxs-lookup"><span data-stu-id="bb972-174">TransformType=;</span></span>  
  
  <span data-ttu-id="bb972-175">接続文字列内のすべての属性は必須です。</span><span class="sxs-lookup"><span data-stu-id="bb972-175">Not all attributes in the connection string are mandatory.</span></span> <span data-ttu-id="bb972-176">さらに、 **EndPointConfig**は特別な属性の競合回避モジュールは設定し、返します。</span><span class="sxs-lookup"><span data-stu-id="bb972-176">In addition, **EndPointConfig** is a special attribute that any resolver can populate and return.</span></span> <span data-ttu-id="bb972-177">必要に応じて、競合回避モジュールは、BizTalk メッセージのコンテキストは書き込み可能にすると、さらに、特定の BizTalk アダプター コンテキスト プロパティに対応する名前/値ペアを格納できます。</span><span class="sxs-lookup"><span data-stu-id="bb972-177">Optionally, the resolver can store the name/value pairs that correspond to specific BizTalk Adapter Context properties, which it can, in turn, write to the context of the BizTalk message.</span></span>  
  
  <span data-ttu-id="bb972-178">ここで、 **ResolverDictionary**アダプター マネージャーにし、解決プロセス、パスから解決されたすべてのプロパティを含むインスタンスが返されます。</span><span class="sxs-lookup"><span data-stu-id="bb972-178">In this case, the **ResolverDictionary** instance that contains all the resolved properties returned from the resolution process then passes to the adapter manager.</span></span> <span data-ttu-id="bb972-179">ディクショナリは、アダプター マネージャーは、すべてのアダプター固有およびエンドポイント固有 BizTalk コンテキストにメッセージのプロパティを設定する特定のアダプター プロバイダーに渡します。</span><span class="sxs-lookup"><span data-stu-id="bb972-179">The adapter manager passes the dictionary to the specific adapter provider that will set all the adapter-specific and endpoint-specific BizTalk Context properties for the message.</span></span> <span data-ttu-id="bb972-180">競合回避モジュールを探して、 **EndPointConfig**プロパティは、それぞれのアダプターのプロパティに対応する名前/値ペアを抽出し、メッセージにこれらの値を設定します。</span><span class="sxs-lookup"><span data-stu-id="bb972-180">The resolvers look for the **EndPointConfig** property, extract the name/value pairs that correspond to their respective adapter properties, and then set these values on the message.</span></span>  
  
## <a name="supported-adapter-providers"></a><span data-ttu-id="bb972-181">サポートされているアダプターのプロバイダー</span><span class="sxs-lookup"><span data-stu-id="bb972-181">Supported Adapter Providers</span></span>  
 <span data-ttu-id="bb972-182">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]次の組み込みのアダプターのプロバイダーが含まれています:**ファイル、FTP、SMTP、MQSeries、Wcf-basichttp、Wcf-wshttp、** と**Wcf-custom**します。</span><span class="sxs-lookup"><span data-stu-id="bb972-182">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] includes the following built-in adapter providers: **FILE, FTP, SMTP,MQSeries, WCF-BasicHttp, WCF-WSHttp,** and **WCF-Custom**.</span></span> <span data-ttu-id="bb972-183">各アダプター プロバイダーの名前は、BizTalk Server では、関連付けられているアダプター (トランスポートの種類) の名前と同じです。</span><span class="sxs-lookup"><span data-stu-id="bb972-183">The name of each adapter provider is identical to the name of the associated adapter (transport type) in BizTalk Server.</span></span>  
  
 <span data-ttu-id="bb972-184">リゾルバーとアダプターのプロバイダー フレームワークの主な利点を作成し、エンドポイント情報とカスタム アダプター プロバイダーが登録済みの BizTalk アダプターの特定のプロパティの設定を解決するのには独自のカスタム リゾルバーを登録して拡張できます。</span><span class="sxs-lookup"><span data-stu-id="bb972-184">A major advantage of the Resolver and Adapter Provider Framework is that you can extend it by creating and registering your own custom resolvers to resolve endpoint information and custom adapter providers to set specific properties of registered BizTalk adapters.</span></span> <span data-ttu-id="bb972-185">詳細については、次を参照してください。[を変更すると、BizTalk ESB Toolkit の拡張](../esb-toolkit/modifying-and-extending-the-biztalk-esb-toolkit.md)します。</span><span class="sxs-lookup"><span data-stu-id="bb972-185">For more information, see [Modifying and Extending the BizTalk ESB Toolkit](../esb-toolkit/modifying-and-extending-the-biztalk-esb-toolkit.md).</span></span>
