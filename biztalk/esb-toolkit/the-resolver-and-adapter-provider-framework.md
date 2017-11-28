---
title: "競合回避モジュールとアダプターのプロバイダー フレームワーク |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fb7ea42e-b32c-40a8-b36b-c349f56f6edd
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 717e7919b3f822ba582ea3c1e50f251eea18a06b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="the-resolver-and-adapter-provider-framework"></a><span data-ttu-id="f7274-102">競合回避モジュールとアダプターのプロバイダー フレームワーク</span><span class="sxs-lookup"><span data-stu-id="f7274-102">The Resolver and Adapter Provider Framework</span></span>
<span data-ttu-id="f7274-103">競合回避モジュールとアダプターのプロバイダー フレームワークは、行程、変換、およびエンドポイントの解像度とルーティングをサポートします。</span><span class="sxs-lookup"><span data-stu-id="f7274-103">The Resolver and Adapter Provider Framework supports itinerary, transformation, and endpoint resolution and routing.</span></span> <span data-ttu-id="f7274-104">フレームワークを動的にエンドポイントを解決および送信アダプターのプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="f7274-104">The framework can dynamically resolve endpoints and set outbound adapter properties.</span></span> <span data-ttu-id="f7274-105">コンポーネントが、エンドポイントを解決する競合回避モジュールの後に、アダプター プロバイダーのコンポーネント セットの特定のプロパティが登録されている (たとえば、送信の Web サービス エンドポイントを検索する Universal Description, Discovery, and Integration [UDDI] を使用して)、 [!INCLUDE[prague](../includes/prague-md.md)]アダプター。</span><span class="sxs-lookup"><span data-stu-id="f7274-105">After a resolver component resolves an endpoint (for example, using Universal Description, Discovery, and Integration [UDDI] to look up an outbound Web service endpoint), an adapter provider component sets specific properties of registered [!INCLUDE[prague](../includes/prague-md.md)] adapters.</span></span> <span data-ttu-id="f7274-106">たとえば、Wcf-basichttp アダプター プロバイダーは、BizTalk 固有のメッセージに、エンドポイント、特定の BizTalk アダプターを使用する URI のコンテキスト プロパティを設定します。FTP アダプター プロバイダーは、FTP アダプターに固有のプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="f7274-106">For example, the WCF-BasicHttp adapter provider is responsible for setting the BizTalk-specific message context properties for the endpoint URI that will use the specific BizTalk adapter; the FTP adapter provider is responsible for setting the properties specific to the FTP adapter.</span></span>  
  
 <span data-ttu-id="f7274-107">競合回避モジュールとアダプターのプロバイダー フレームワークの 1 つの目標は、解像度と、メッセージ レベルでの BizTalk オーケストレーションの使用を必要とせず、またはオーケストレーション レベルのルーティングをサポートします。</span><span class="sxs-lookup"><span data-stu-id="f7274-107">One goal of the Resolver and Adapter Provider Framework is to support resolution and routing at either the messaging level, without requiring the use of BizTalk orchestrations, or at the orchestration level.</span></span> <span data-ttu-id="f7274-108">どちらの場合は、プラグ可能なフレームワークは、容易に開発、配置、および新しい競合回避モジュールとアダプター プロバイダーの登録を提供します。</span><span class="sxs-lookup"><span data-stu-id="f7274-108">In both cases, the pluggable framework provides easy development, deployment, and registration of new resolvers and adapter providers.</span></span> <span data-ttu-id="f7274-109">すべての競合回避モジュールとアダプター プロバイダー適切に定義されたインターフェイスを実装および要求時に読み込まれた構成ファイルに登録を介して実行時にします。</span><span class="sxs-lookup"><span data-stu-id="f7274-109">All resolvers and adapter providers implement well-defined interfaces and are demand-loaded at run time through registration in the configuration files.</span></span>  
  
 <span data-ttu-id="f7274-110">ESB ディスパッチャーおよび ESB ディスパッチャーの逆アセンブル パイプライン コンポーネントは、競合回避モジュール マネージャーに行程 SOAP ヘッダーまたはパイプラインの構成のいずれかから接続文字列を渡すことによって、競合回避モジュールとアダプターのプロバイダー フレームワークを使用します。</span><span class="sxs-lookup"><span data-stu-id="f7274-110">Both the ESB Dispatcher and ESB Dispatcher Disassemble pipeline components use the Resolver and Adapter Provider Framework by passing the connection string from either the itinerary SOAP header or the pipeline configuration to the Resolver Manager.</span></span>  
  
 <span data-ttu-id="f7274-111">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]構成に登録されているすべての競合回避モジュールとアダプター プロバイダーの詳細情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="f7274-111">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] configuration contains details of all registered resolvers and adapter providers.</span></span> <span data-ttu-id="f7274-112">実行時、競合回避モジュールのマネージャー、およびアダプター マネージャーの構成ファイルから、登録されている競合回避モジュールとアダプター プロバイダーの詳細を読みで、適切なアセンブリを読み込んで BizTalk ホスト レベルのキャッシュに格納します。</span><span class="sxs-lookup"><span data-stu-id="f7274-112">At run time, the resolver managers and adapter managers read details of the registered resolvers and adapter providers from the configuration files, load the appropriate assemblies, and store them in a BizTalk host–level cache.</span></span> <span data-ttu-id="f7274-113">このキャッシュの手法では、繰り返しの構成ファイルの読み取りおよび送信されたメッセージごとにアセンブリの読み込みを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="f7274-113">This caching technique removes the requirement for repeated reading of configuration files and loading of assemblies for every submitted message.</span></span>  
  
 <span data-ttu-id="f7274-114">競合回避モジュールおよびアダプター プロバイダーのフレームワークの動作の仕組みとカスタム競合回避モジュールと、アダプターのプロバイダーを作成して拡張する方法を表示する方法の詳細については[変更および拡張 BizTalk ESB Toolkit](../esb-toolkit/modifying-and-extending-the-biztalk-esb-toolkit.md)です。</span><span class="sxs-lookup"><span data-stu-id="f7274-114">For more information about how the Resolver and Adapter Provider Framework works and how you can extend it by creating custom resolvers and adapter providers, see [Modifying and Extending the BizTalk ESB Toolkit](../esb-toolkit/modifying-and-extending-the-biztalk-esb-toolkit.md).</span></span>  
  
## <a name="supported-resolution-mechanisms-resolvers"></a><span data-ttu-id="f7274-115">サポートされている解決メカニズム (競合回避モジュール)</span><span class="sxs-lookup"><span data-stu-id="f7274-115">Supported Resolution Mechanisms (Resolvers)</span></span>  
 <span data-ttu-id="f7274-116">BizTalk ESB Toolkit には、次の競合回避モジュールが含まれています:**静的、UDDI、UDDI3、XPATH、BRE、BRI、行程、行程静的**と**LDAP**です。</span><span class="sxs-lookup"><span data-stu-id="f7274-116">The BizTalk ESB Toolkit includes the following resolvers: **STATIC, UDDI, UDDI3, XPATH, BRE, BRI, ITINERARY, ITINERARY-STATIC** and **LDAP**.</span></span>  
  
 <span data-ttu-id="f7274-117">競合回避モジュールの接続文字列が常に構成される、**モニカー** (など**BRE**) 後に":\\\\"との接続や処理の詳細。</span><span class="sxs-lookup"><span data-stu-id="f7274-117">A resolver's connection string always consists of a **moniker** (such as **BRE**) followed by ":\\\\" and the connection or processing details.</span></span> <span data-ttu-id="f7274-118">モニカーでは、構成ファイルに関連付けられている競合回避モジュールの定義と一致します。</span><span class="sxs-lookup"><span data-stu-id="f7274-118">The moniker matches the definition of the associated resolver in the configuration file.</span></span> <span data-ttu-id="f7274-119">各接続文字列に関連付けられているプロパティは、一意、およびすべてのプロパティが必要です。</span><span class="sxs-lookup"><span data-stu-id="f7274-119">The properties associated with each connection string are unique, and not all properties are required.</span></span> <span data-ttu-id="f7274-120">競合回避モジュールの各スキーマは、ESB に含まれています。Resolvers.Schemas プロジェクトです。</span><span class="sxs-lookup"><span data-stu-id="f7274-120">The schema for each of the resolvers can be found in the ESB.Resolvers.Schemas project.</span></span>  
  
 <span data-ttu-id="f7274-121">接続文字列の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="f7274-121">The following are examples of connection strings:</span></span>  
  
-   <span data-ttu-id="f7274-122">**静的**</span><span class="sxs-lookup"><span data-stu-id="f7274-122">**STATIC**</span></span>  
  
     <span data-ttu-id="f7274-123">静的:\\\TransportType= です。</span><span class="sxs-lookup"><span data-stu-id="f7274-123">STATIC:\\\TransportType=;</span></span>  
  
     <span data-ttu-id="f7274-124">TransportLocation http://localhost/ESB.CanadianServices/SubmitPOService.asmx; を =</span><span class="sxs-lookup"><span data-stu-id="f7274-124">TransportLocation=http://localhost/ESB.CanadianServices/SubmitPOService.asmx;</span></span>  
  
     <span data-ttu-id="f7274-125">アクション = です。</span><span class="sxs-lookup"><span data-stu-id="f7274-125">Action=;</span></span>  
  
     <span data-ttu-id="f7274-126">EndPointConfig = です。</span><span class="sxs-lookup"><span data-stu-id="f7274-126">EndPointConfig=;</span></span>  
  
     <span data-ttu-id="f7274-127">JaxRpcResponse = false。</span><span class="sxs-lookup"><span data-stu-id="f7274-127">JaxRpcResponse=false;</span></span>  
  
     <span data-ttu-id="f7274-128">MessageExchangePattern = です。</span><span class="sxs-lookup"><span data-stu-id="f7274-128">MessageExchangePattern=;</span></span>  
  
     <span data-ttu-id="f7274-129">TargetNamespace = http://globalbank.esb.dynamicresolution.com/canadianservices/;</span><span class="sxs-lookup"><span data-stu-id="f7274-129">TargetNamespace=http://globalbank.esb.dynamicresolution.com/canadianservices/;</span></span>  
  
     <span data-ttu-id="f7274-130">TransformType = です。</span><span class="sxs-lookup"><span data-stu-id="f7274-130">TransformType=;</span></span>  
  
-   <span data-ttu-id="f7274-131">**UDDI**</span><span class="sxs-lookup"><span data-stu-id="f7274-131">**UDDI**</span></span>  
  
     <span data-ttu-id="f7274-132">UDDI:\\\serverUrl= http://localhost: 9901/rmengine です。</span><span class="sxs-lookup"><span data-stu-id="f7274-132">UDDI:\\\serverUrl=http://localhost:9901/rmengine;</span></span>  
  
     <span data-ttu-id="f7274-133">serviceName = OrderPurchaseWebService です。</span><span class="sxs-lookup"><span data-stu-id="f7274-133">serviceName=OrderPurchaseWebService;</span></span>  
  
     <span data-ttu-id="f7274-134">serviceProvider Microsoft プラクティス ESB を =</span><span class="sxs-lookup"><span data-stu-id="f7274-134">serviceProvider=Microsoft Practices ESB</span></span>  
  
-   <span data-ttu-id="f7274-135">**[XPath]**</span><span class="sxs-lookup"><span data-stu-id="f7274-135">**XPATH**</span></span>  
  
     <span data-ttu-id="f7274-136">\\\TransportType= です。</span><span class="sxs-lookup"><span data-stu-id="f7274-136">\\\TransportType=;</span></span>  
  
     <span data-ttu-id="f7274-137">TransportLocation =/*[ローカル名 () 'OrderDoc' and namespace-uri() = = 'http://globalbank.esb.dynamicresolution.com/northamericanservices/']/*[ローカル名 () 'ID' and namespace-uri() = = 'http://globalbank.esb.dynamicresolution.com/northamericanservices/']。</span><span class="sxs-lookup"><span data-stu-id="f7274-137">TransportLocation=/*[local-name()='OrderDoc' and namespace-uri()='http://globalbank.esb.dynamicresolution.com/northamericanservices/']/*[local-name()='ID' and namespace-uri()='http://globalbank.esb.dynamicresolution.com/northamericanservices/'];</span></span>  
  
     <span data-ttu-id="f7274-138">アクション = です。</span><span class="sxs-lookup"><span data-stu-id="f7274-138">Action=;</span></span>  
  
     <span data-ttu-id="f7274-139">EndPointConfig = です。</span><span class="sxs-lookup"><span data-stu-id="f7274-139">EndPointConfig=;</span></span>  
  
     <span data-ttu-id="f7274-140">JaxRpcResponse = です。</span><span class="sxs-lookup"><span data-stu-id="f7274-140">JaxRpcResponse=;</span></span>  
  
     <span data-ttu-id="f7274-141">MessageExchangePattern = です。</span><span class="sxs-lookup"><span data-stu-id="f7274-141">MessageExchangePattern=;</span></span>  
  
     <span data-ttu-id="f7274-142">TargetNamespace =/*[ローカル名 () = 'OrderDoc' and namespace-uri() = 'http://globalbank.esb.dynamicresolution.com/northamericanservices/']/*[ローカル名 () 'customerName' と名前空間 uri () = ='http://globalbank.esb.dynamicresolution.com/northamericanservices/']。</span><span class="sxs-lookup"><span data-stu-id="f7274-142">TargetNamespace=/*[local-name()='OrderDoc' and namespace-uri()='http://globalbank.esb.dynamicresolution.com/northamericanservices/']/*[local-name()='customerName' and namespace-uri()='http://globalbank.esb.dynamicresolution.com/northamericanservices/'];</span></span>  
  
     <span data-ttu-id="f7274-143">TransformType = です。</span><span class="sxs-lookup"><span data-stu-id="f7274-143">TransformType=;</span></span>  
  
-   <span data-ttu-id="f7274-144">**BRE**</span><span class="sxs-lookup"><span data-stu-id="f7274-144">**BRE**</span></span>  
  
     <span data-ttu-id="f7274-145">BRE:\\\policy=GetCanadaEndPoint です。</span><span class="sxs-lookup"><span data-stu-id="f7274-145">BRE:\\\policy=GetCanadaEndPoint;</span></span>  
  
     <span data-ttu-id="f7274-146">バージョン = です。</span><span class="sxs-lookup"><span data-stu-id="f7274-146">version=;</span></span>  
  
     <span data-ttu-id="f7274-147">useMsg = です。</span><span class="sxs-lookup"><span data-stu-id="f7274-147">useMsg=;</span></span>  
  
-   <span data-ttu-id="f7274-148">**BRI**</span><span class="sxs-lookup"><span data-stu-id="f7274-148">**BRI**</span></span>  
  
     <span data-ttu-id="f7274-149">BRI:\\\policy=ResolveItinerary です。</span><span class="sxs-lookup"><span data-stu-id="f7274-149">BRI:\\\policy=ResolveItinerary;</span></span>  
  
     <span data-ttu-id="f7274-150">バージョン = です。</span><span class="sxs-lookup"><span data-stu-id="f7274-150">version=;</span></span>  
  
     <span data-ttu-id="f7274-151">useMsg = です。</span><span class="sxs-lookup"><span data-stu-id="f7274-151">useMsg=;</span></span>  
  
-   <span data-ttu-id="f7274-152">**行程**</span><span class="sxs-lookup"><span data-stu-id="f7274-152">**ITINERARY**</span></span>  
  
     <span data-ttu-id="f7274-153">行程:\\\name=TwoWayTestItinerary です。</span><span class="sxs-lookup"><span data-stu-id="f7274-153">ITINERARY:\\\name=TwoWayTestItinerary;</span></span>  
  
     <span data-ttu-id="f7274-154">バージョン = です。</span><span class="sxs-lookup"><span data-stu-id="f7274-154">version=;</span></span>  
  
-   <span data-ttu-id="f7274-155">**行程静的**</span><span class="sxs-lookup"><span data-stu-id="f7274-155">**ITINERARY-STATIC**</span></span>  
  
     <span data-ttu-id="f7274-156">行程静的:\\\name=TwoWayTestItinerary です。</span><span class="sxs-lookup"><span data-stu-id="f7274-156">ITINERARY-STATIC:\\\name=TwoWayTestItinerary;</span></span>  
  
     <span data-ttu-id="f7274-157">バージョン = です。</span><span class="sxs-lookup"><span data-stu-id="f7274-157">version=;</span></span>  
  
-   <span data-ttu-id="f7274-158">**LDAP**</span><span class="sxs-lookup"><span data-stu-id="f7274-158">**LDAP**</span></span>  
  
     <span data-ttu-id="f7274-159">LDAP:\\\TransportType=SMTP です。</span><span class="sxs-lookup"><span data-stu-id="f7274-159">LDAP:\\\TransportType=SMTP;</span></span>  
  
     <span data-ttu-id="f7274-160">TransportLocation = {メール}</span><span class="sxs-lookup"><span data-stu-id="f7274-160">TransportLocation={mail}</span></span>  
  
     <span data-ttu-id="f7274-161">フィルター = (&amp;(objectClass = ユーザー) (&#124; (userPrincipalName =yourname@domain.com))) です。</span><span class="sxs-lookup"><span data-stu-id="f7274-161">Filter=(&amp;(objectClass=User)(&#124;(userPrincipalName=yourname@domain.com)));</span></span>  
  
     <span data-ttu-id="f7274-162">SearchRoot = です。</span><span class="sxs-lookup"><span data-stu-id="f7274-162">SearchRoot=;</span></span>  
  
     <span data-ttu-id="f7274-163">SearchScope サブツリー; を =</span><span class="sxs-lookup"><span data-stu-id="f7274-163">SearchScope=Subtree;</span></span>  
  
     <span data-ttu-id="f7274-164">EndpointConfig サブジェクトを = {メール} 行程テスト メッセージを =&amp;</span><span class="sxs-lookup"><span data-stu-id="f7274-164">EndpointConfig=Subject=Itinerary Test Message to {mail}&amp;</span></span>  
  
     <span data-ttu-id="f7274-165">SMTPAuthenticate 0 を =&amp;</span><span class="sxs-lookup"><span data-stu-id="f7274-165">SMTPAuthenticate=0&amp;</span></span>  
  
     <span data-ttu-id="f7274-166">Smtphost の各 127.0.0.1 を =&amp;</span><span class="sxs-lookup"><span data-stu-id="f7274-166">SMTPHost=127.0.0.1&amp;</span></span>  
  
     <span data-ttu-id="f7274-167">From =test@globalbank.com&amp;</span><span class="sxs-lookup"><span data-stu-id="f7274-167">From=test@globalbank.com&amp;</span></span>  
  
     <span data-ttu-id="f7274-168">DeliveryReceipt = false&amp;</span><span class="sxs-lookup"><span data-stu-id="f7274-168">DeliveryReceipt=false&amp;</span></span>  
  
     <span data-ttu-id="f7274-169">MessagePartsAttachments 0 を =&amp;</span><span class="sxs-lookup"><span data-stu-id="f7274-169">MessagePartsAttachments=0&amp;</span></span>  
  
     <span data-ttu-id="f7274-170">ReadReceipt = false。</span><span class="sxs-lookup"><span data-stu-id="f7274-170">ReadReceipt=false;</span></span>  
  
     <span data-ttu-id="f7274-171">ThrowErrorIfNotFound = false。</span><span class="sxs-lookup"><span data-stu-id="f7274-171">ThrowErrorIfNotFound=false;</span></span>  
  
     <span data-ttu-id="f7274-172">アクション = です。</span><span class="sxs-lookup"><span data-stu-id="f7274-172">Action=;</span></span>  
  
     <span data-ttu-id="f7274-173">JaxRpcResponse = false。</span><span class="sxs-lookup"><span data-stu-id="f7274-173">JaxRpcResponse=false;</span></span>  
  
     <span data-ttu-id="f7274-174">MessageExchangePattern = です。</span><span class="sxs-lookup"><span data-stu-id="f7274-174">MessageExchangePattern=;</span></span>  
  
     <span data-ttu-id="f7274-175">TargetNamespace = です。</span><span class="sxs-lookup"><span data-stu-id="f7274-175">TargetNamespace=;</span></span>  
  
     <span data-ttu-id="f7274-176">TransformType = です。</span><span class="sxs-lookup"><span data-stu-id="f7274-176">TransformType=;</span></span>  
  
 <span data-ttu-id="f7274-177">接続文字列内のすべての属性が必須です。</span><span class="sxs-lookup"><span data-stu-id="f7274-177">Not all attributes in the connection string are mandatory.</span></span> <span data-ttu-id="f7274-178">さらに、 **EndPointConfig**任意リゾルバーの設定し、を返すことができますを特別な属性です。</span><span class="sxs-lookup"><span data-stu-id="f7274-178">In addition, **EndPointConfig** is a special attribute that any resolver can populate and return.</span></span> <span data-ttu-id="f7274-179">必要に応じて、競合回避モジュールは、BizTalk メッセージのコンテキストには書き込み可能にすると、さらに、特定の BizTalk アダプター コンテキスト プロパティに対応する名前/値ペアを格納できます。</span><span class="sxs-lookup"><span data-stu-id="f7274-179">Optionally, the resolver can store the name/value pairs that correspond to specific BizTalk Adapter Context properties, which it can, in turn, write to the context of the BizTalk message.</span></span>  
  
 <span data-ttu-id="f7274-180">ここで、 **ResolverDictionary**アダプター マネージャーにし、解決プロセス、パスから解決済みのすべてのプロパティを格納するインスタンスが返されます。</span><span class="sxs-lookup"><span data-stu-id="f7274-180">In this case, the **ResolverDictionary** instance that contains all the resolved properties returned from the resolution process then passes to the adapter manager.</span></span> <span data-ttu-id="f7274-181">アダプター マネージャーは、すべてのアダプター特有であり、エンドポイント固有 BizTalk コンテキストにメッセージのプロパティを設定する特定のアダプター プロバイダー ディクショナリを渡します。</span><span class="sxs-lookup"><span data-stu-id="f7274-181">The adapter manager passes the dictionary to the specific adapter provider that will set all the adapter-specific and endpoint-specific BizTalk Context properties for the message.</span></span> <span data-ttu-id="f7274-182">競合回避モジュールを探して、 **EndPointConfig**プロパティは、それぞれのアダプター プロパティに対応する名前/値ペアを抽出し、メッセージにこれらの値を設定します。</span><span class="sxs-lookup"><span data-stu-id="f7274-182">The resolvers look for the **EndPointConfig** property, extract the name/value pairs that correspond to their respective adapter properties, and then set these values on the message.</span></span>  
  
## <a name="supported-adapter-providers"></a><span data-ttu-id="f7274-183">サポートされているアダプター プロバイダー</span><span class="sxs-lookup"><span data-stu-id="f7274-183">Supported Adapter Providers</span></span>  
 <span data-ttu-id="f7274-184">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]は、次の組み込みアダプター プロバイダーが含まれています:**ファイル、FTP、SMTP、MQSeries、Wcf-basichttp、Wcf-wshttp、**と**Wcf-custom**です。</span><span class="sxs-lookup"><span data-stu-id="f7274-184">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] includes the following built-in adapter providers: **FILE, FTP, SMTP,MQSeries, WCF-BasicHttp, WCF-WSHttp,** and **WCF-Custom**.</span></span> <span data-ttu-id="f7274-185">各アダプター プロバイダーの名前は、BizTalk Server では、関連付けられたアダプター (トランスポートの種類) の名前と同じです。</span><span class="sxs-lookup"><span data-stu-id="f7274-185">The name of each adapter provider is identical to the name of the associated adapter (transport type) in BizTalk Server.</span></span>  
  
 <span data-ttu-id="f7274-186">競合回避モジュールとアダプターのプロバイダー フレームワークの主要な利点を拡張することによって作成、およびエンドポイント情報と登録済みの BizTalk アダプターの特定のプロパティを設定するプロバイダーをカスタム アダプターを解決するのには、独自のカスタム リゾルバーを登録します。</span><span class="sxs-lookup"><span data-stu-id="f7274-186">A major advantage of the Resolver and Adapter Provider Framework is that you can extend it by creating and registering your own custom resolvers to resolve endpoint information and custom adapter providers to set specific properties of registered BizTalk adapters.</span></span> <span data-ttu-id="f7274-187">詳細については、次を参照してください。[変更および拡張 BizTalk ESB Toolkit](../esb-toolkit/modifying-and-extending-the-biztalk-esb-toolkit.md)です。</span><span class="sxs-lookup"><span data-stu-id="f7274-187">For more information, see [Modifying and Extending the BizTalk ESB Toolkit](../esb-toolkit/modifying-and-extending-the-biztalk-esb-toolkit.md).</span></span>