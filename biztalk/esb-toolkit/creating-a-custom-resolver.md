---
title: カスタム競合回避モジュールを作成する |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d2775460-8e04-40be-9557-8278336b031c
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b3752348a5cc9273ad203b78b77b58bde33bd141
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981715"
---
# <a name="creating-a-custom-resolver"></a><span data-ttu-id="7f5cf-102">カスタム競合回避モジュールを作成します。</span><span class="sxs-lookup"><span data-stu-id="7f5cf-102">Creating a Custom Resolver</span></span>
<span data-ttu-id="7f5cf-103">リゾルバーとアダプターのプロバイダー フレームワーク実装[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]ディスパッチャーをという名前のパイプライン コンポーネントと ItineraryReceive および ItinerarySend という名前のパイプラインを使用します。</span><span class="sxs-lookup"><span data-stu-id="7f5cf-103">The Resolver and Adapter Provider Framework implementation in [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] uses a pipeline component named Dispatcher and pipelines named ItineraryReceive and ItinerarySend.</span></span>  
  
 <span data-ttu-id="7f5cf-104">ディスパッチャー パイプライン コンポーネントには 4 つのプロパティ:**検証、Enabled、エンドポイント、** と**MapName**します。</span><span class="sxs-lookup"><span data-stu-id="7f5cf-104">The Dispatcher pipeline component has four properties: **Validate, Enabled, EndPoint,** and **MapName**.</span></span> <span data-ttu-id="7f5cf-105">**エンドポイント**プロパティは、次のように値を持つ接続文字列の競合回避モジュールを含めることができます、 **UDDI:\\ \\**  (ルートを使用する解像度の種類を表しますモニカー)。</span><span class="sxs-lookup"><span data-stu-id="7f5cf-105">The **EndPoint** property can contain resolver connection strings with values such as the following, where **UDDI:\\\\** represents the resolution type to use (the root moniker).</span></span>  
  
```  
UDDI:\\serverUrl=http://localhost/uddi;serviceName=OrderPurchaseToOrderPost;serviceProvider=Microsoft.Practices.ESB  
```  
  
 <span data-ttu-id="7f5cf-106">サポートされているその他のモニカーを含める**XPATH:\\\\の静的な:\\\\、** と**BRE:\\\\**します。</span><span class="sxs-lookup"><span data-stu-id="7f5cf-106">Other supported monikers include **XPATH:\\\\, STATIC:\\\\,** and **BRE:\\\\**.</span></span> <span data-ttu-id="7f5cf-107">各モニカーの型を実装する特定のクラスを使用して、 **IResolveProvider**インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="7f5cf-107">Each moniker type uses a specific class that implements the **IResolveProvider** interface.</span></span> <span data-ttu-id="7f5cf-108">モニカーの他の種類の独自のカスタム リゾルバーを作成し、動的解決のシステムで使用するためを登録できます。</span><span class="sxs-lookup"><span data-stu-id="7f5cf-108">You can create your own custom resolvers for other moniker types and register them for use by the dynamic resolution system.</span></span>  
  
 <span data-ttu-id="7f5cf-109">モニカーは、競合回避モジュールの接続文字列に相当します。</span><span class="sxs-lookup"><span data-stu-id="7f5cf-109">The moniker equates to a resolver connection string.</span></span> <span data-ttu-id="7f5cf-110">個別のスキーマは、パラメーターとそのルート モニカーを定義します。</span><span class="sxs-lookup"><span data-stu-id="7f5cf-110">Individual schemas define the parameters and their root moniker.</span></span> <span data-ttu-id="7f5cf-111">競合回避モジュールは、競合回避モジュールの接続文字列を検証し、結果を使用してクエリを実行し、設定、**ディクショナリ**ルーティング、変換、スケジュールの選択、またはに固有の他の何らかの目的のために使用できるオブジェクト、サービス。</span><span class="sxs-lookup"><span data-stu-id="7f5cf-111">A resolver takes the resolver connection string, validates it, and uses the result to query and populate a **Dictionary** object that can be used for routing, transformation, itinerary selection, or some other purpose specific to your service.</span></span>  
  
## <a name="resolver-configuration"></a><span data-ttu-id="7f5cf-112">競合回避モジュールの構成</span><span class="sxs-lookup"><span data-stu-id="7f5cf-112">Resolver Configuration</span></span>  
 <span data-ttu-id="7f5cf-113">Esb.config 構成ファイルですべての競合回避モジュールを登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7f5cf-113">You must register all resolvers in the Esb.config configuration file.</span></span> <span data-ttu-id="7f5cf-114">次の XML では、構成ファイルの内容の例を示します。</span><span class="sxs-lookup"><span data-stu-id="7f5cf-114">The following XML shows an example of the configuration file content.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
     <configSections>  
          <section name="esb" type="Microsoft.Practices.ESB.Configuration.ESBConfigurationSection, Microsoft.Practices.ESB.Configuration, Version=2.0.0.0, Culture=neutral, PublicKeyToken=c62dd63c784d6e22"/>  
          <!-- Other Section Definitions Here -->  
     </configSections>  
  
     <esb>  
          <resolvers cacheManager= "Resolver Providers Cache Manager"  absoluteExpiration="3600">  
               <resolver name="UDDI" type="Microsoft.Practices.ESB.Resolver.UDDI.ResolveProvider, Microsoft.Practices.ESB.Resolver.UDDI, Version=2.0.0.0, Culture=neutral, PublicKeyToken=c62dd63c784d6e22">  
                    <resolverConfig>  
                         <add name="cacheTimeoutValue" value="120" />  
                         <add name="cacheName" value="UDDI Cache Manager" />  
                    </resolverConfig>  
               </resolver>  
               <resolver name="XPATH" type="Microsoft.Practices.ESB.Resolver.XPATH.ResolveProvider, Microsoft.Practices.ESB.Resolver.XPATH, Version=2.0.0.0, Culture=neutral, PublicKeyToken=c62dd63c784d6e22"/>  
               <!-- Other Resolver Definitions Here -->  
          </resolvers>  
          <!-- Other ESB Configuration Settings Here -->  
     </esb>  
     <!-- Other Configuration Sections Here -->  
</configuration>  
```  
  
 <span data-ttu-id="7f5cf-115">**ResolverConfig**競合回避モジュールの各ノードの下のセクションでは、特定の環境で動作する、競合回避モジュールが必要な追加のプロパティを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="7f5cf-115">The **resolverConfig** section under each resolver node allows you to configure additional properties that your resolver may require to operate in a specific environment.</span></span> <span data-ttu-id="7f5cf-116">リゾルバー構成へのアクセスには、型のパラメーターを受け取るコンス トラクターを公開する必要があります**Microsoft.Practices.ESB.Configuration.Resolver**します。</span><span class="sxs-lookup"><span data-stu-id="7f5cf-116">To have access to the configuration, your resolver must expose a constructor that takes in a parameter of type **Microsoft.Practices.ESB.Configuration.Resolver**.</span></span> <span data-ttu-id="7f5cf-117">競合回避モジュールの実装で構成しプロパティを使用して、 **ReadResolverConfigByKey**のメソッド、 **ResolverConfigHelper**クラスは、これを行うには、パラメーターに渡す最初に、コンス トラクターに渡され、問題の名前、値渡すします。</span><span class="sxs-lookup"><span data-stu-id="7f5cf-117">In your resolver implementation, configuration properties can then be accessed using the **ReadResolverConfigByKey** method of the **ResolverConfigHelper** class; to do this, pass in the parameter originally passed to the constructor, and then pass in the name of the value in question.</span></span> <span data-ttu-id="7f5cf-118">名前と値のペアが指定されていない場合、 **resolverConfig**ノードで、既定のパラメーターなしコンス トラクターは、競合回避モジュールをインスタンス化に使用されます。</span><span class="sxs-lookup"><span data-stu-id="7f5cf-118">If no name-value pairs are specified in the **resolverConfig** node, the default parameterless constructor will be used to instantiate your resolver.</span></span>  
  
 <span data-ttu-id="7f5cf-119">2 つ Universal Description, Discovery, and Integration (UDDI) 3 競合回避モジュールは、構成で定義されている: 3 の UDDI および UDDI 3-SOASOFTWARE します。</span><span class="sxs-lookup"><span data-stu-id="7f5cf-119">Two Universal Description, Discovery, and Integration (UDDI) 3 resolvers have been defined in the configuration: UDDI 3 and UDDI 3-SOASOFTWARE.</span></span> <span data-ttu-id="7f5cf-120">同じ基になるアセンブリを使用して、これらの競合回避モジュールの両方が、別の UDDI 3.0 に準拠したレジストリの別の Uniform Resource Identifier (URI) 形式とセキュリティ要件をサポートするためのさまざまな構成を提供します。</span><span class="sxs-lookup"><span data-stu-id="7f5cf-120">Both of these resolvers use the same underlying assembly, but they provide different configurations for supporting different UDDI 3.0–compliant registries with different Uniform Resource Identifier (URI) formats and security requirements.</span></span> <span data-ttu-id="7f5cf-121">既にサポートされているもの以外の UDDI 3.0 に準拠したレジストリの追加のモニカーを構成する必要がある場合は、次の構成プロパティを使用できます。</span><span class="sxs-lookup"><span data-stu-id="7f5cf-121">If you need to configure an additional moniker for a UDDI 3.0–compliant registry besides those already supported, the following configuration properties can be used:</span></span>  
  
- <span data-ttu-id="7f5cf-122">**cacheTimeoutValue**</span><span class="sxs-lookup"><span data-stu-id="7f5cf-122">**cacheTimeoutValue**</span></span>  
  
- <span data-ttu-id="7f5cf-123">**cacheName**</span><span class="sxs-lookup"><span data-stu-id="7f5cf-123">**cacheName**</span></span>  
  
- <span data-ttu-id="7f5cf-124">**publisherKey**</span><span class="sxs-lookup"><span data-stu-id="7f5cf-124">**publisherKey**</span></span>  
  
- <span data-ttu-id="7f5cf-125">**useUddiAuth**</span><span class="sxs-lookup"><span data-stu-id="7f5cf-125">**useUddiAuth**</span></span>  
  
- <span data-ttu-id="7f5cf-126">**baseUri**</span><span class="sxs-lookup"><span data-stu-id="7f5cf-126">**baseUri**</span></span>  
  
- <span data-ttu-id="7f5cf-127">**inquireUriSuffix**</span><span class="sxs-lookup"><span data-stu-id="7f5cf-127">**inquireUriSuffix**</span></span>  
  
- <span data-ttu-id="7f5cf-128">**securityUriSuffix**</span><span class="sxs-lookup"><span data-stu-id="7f5cf-128">**securityUriSuffix**</span></span>  
  
- <span data-ttu-id="7f5cf-129">**securityMode**します。</span><span class="sxs-lookup"><span data-stu-id="7f5cf-129">**securityMode**.</span></span> <span data-ttu-id="7f5cf-130">有効な値は、列挙体を参照してください。 [System.ServiceModel.BasicHttpSecurityMode](http://go.microsoft.com/fwlink/?LinkID=188284&clcid=0x409) ([http://go.microsoft.com/fwlink/?LinkID=188284&clcid=0x409](http://go.microsoft.com/fwlink/?LinkID=188284&clcid=0x409))。</span><span class="sxs-lookup"><span data-stu-id="7f5cf-130">For valid values, see the enumeration [System.ServiceModel.BasicHttpSecurityMode](http://go.microsoft.com/fwlink/?LinkID=188284&clcid=0x409) ([http://go.microsoft.com/fwlink/?LinkID=188284&clcid=0x409](http://go.microsoft.com/fwlink/?LinkID=188284&clcid=0x409)).</span></span> <span data-ttu-id="7f5cf-131">既定値は**TransportCredentialOnly**します。</span><span class="sxs-lookup"><span data-stu-id="7f5cf-131">The default value is **TransportCredentialOnly**.</span></span>  
  
- <span data-ttu-id="7f5cf-132">**credentialType**します。</span><span class="sxs-lookup"><span data-stu-id="7f5cf-132">**credentialType**.</span></span> <span data-ttu-id="7f5cf-133">有効な値は、列挙体を参照してください。 [System.ServiceModel.HttpClientCredentialType](http://go.microsoft.com/fwlink/?LinkId=188285) ([http://go.microsoft.com/fwlink/?LinkId=188285](http://go.microsoft.com/fwlink/?LinkId=188285))。</span><span class="sxs-lookup"><span data-stu-id="7f5cf-133">For valid values, see the enumeration [System.ServiceModel.HttpClientCredentialType](http://go.microsoft.com/fwlink/?LinkId=188285) ([http://go.microsoft.com/fwlink/?LinkId=188285](http://go.microsoft.com/fwlink/?LinkId=188285)).</span></span> <span data-ttu-id="7f5cf-134">既定値は**Windows**します。</span><span class="sxs-lookup"><span data-stu-id="7f5cf-134">The default value is **Windows**.</span></span>  
  
- <span data-ttu-id="7f5cf-135">**username**</span><span class="sxs-lookup"><span data-stu-id="7f5cf-135">**username**</span></span>  
  
- <span data-ttu-id="7f5cf-136">**password**</span><span class="sxs-lookup"><span data-stu-id="7f5cf-136">**password**</span></span>  
  
  <span data-ttu-id="7f5cf-137">Unity Application Block の依存関係の注入機能に依存している競合回避モジュールを作成する場合は、追加の構成が必要です。</span><span class="sxs-lookup"><span data-stu-id="7f5cf-137">If you want to create a resolver that relies on the dependency injection capabilities of the Unity Application Block, additional configuration is required.</span></span> <span data-ttu-id="7f5cf-138">詳細については、次を参照してください。 [Unity コンテナーでのカスタム競合回避モジュールを作成する](../esb-toolkit/creating-a-custom-resolver-with-a-unity-container.md)します。</span><span class="sxs-lookup"><span data-stu-id="7f5cf-138">For more information, see [Creating a Custom Resolver with a Unity Container](../esb-toolkit/creating-a-custom-resolver-with-a-unity-container.md).</span></span>  
  
## <a name="the-iresolveprovider-interface"></a><span data-ttu-id="7f5cf-139">IResolveProvider インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7f5cf-139">The IResolveProvider Interface</span></span>  
 <span data-ttu-id="7f5cf-140">すべての競合回避モジュールを実装する必要があります、 **IResolveProvider**インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="7f5cf-140">All resolvers must implement the **IResolveProvider** interface.</span></span> <span data-ttu-id="7f5cf-141">**IResolveProvider** Microsoft.Practices.ESB.Resolver のプロジェクトにあるインターフェイスの 3 つのオーバー ロードから成る、**解決**のインスタンスを返すメソッド、 **ディクショナリ**解像度のファクト具体的な競合回避モジュールのクラスのインスタンスによって提供されるを保持しているクラス。</span><span class="sxs-lookup"><span data-stu-id="7f5cf-141">The **IResolveProvider** interface, located in the Microsoft.Practices.ESB.Resolver project, consists of three overloads of the **Resolve** method that return an instance of the **Dictionary** class, which contains resolution facts provided by the instance of concrete resolver class.</span></span> <span data-ttu-id="7f5cf-142">次のコード例では、これらのメソッド オーバー ロードのシグネチャを示します。</span><span class="sxs-lookup"><span data-stu-id="7f5cf-142">The following code example shows the signature of these method overloads.</span></span>  
  
```csharp  
// <summary>  
// This is the main interface that is called from the   
// ResolverMgr class.  
// This interface supports being called from a Microsoft BizTalk   
// Server pipeline component.  
// </summary>  
// <param name="config">Configuration string entered into   
// pipeline component as argument</param>  
// <param name="resolver">Moniker representing the resolver   
// to load</param>.  
// <param name="message">IBaseMessage passed from pipeline</param>.  
// <param name="pipelineContext">IPipelineContext passed from   
// pipeline</param>.  
// <returns>Dictionary object fully populated</returns>.  
        Dictionary<string, string> Resolve(string config, string resolver,  
              IBaseMessage message, IPipelineContext pipelineContext);  
  
// <summary>  
// This is the main interface that is called from the ResolverMgr   
// class.  
// This interface supports being called from a Web service interface.  
// </summary>  
// <param name="config">Configuration string entered into Web   
// service as argument</param>.  
// <param name="resolver">Moniker representing the resolver   
// to load</param>.  
// <param name="message">XML document passed from Web   
// service</param>.  
// <returns>Dictionary object fully populated</returns>.  
        Dictionary<string,string> Resolve(string config, string resolver, System.Xml.XmlDocument message);  
  
// <summary>  
// This is the main interface that is called from the   
// ResolverMgr class.  
// This interface supports being called from an orchestration.  
// </summary>  
// <param name="resolverInfo">Configuration string containing   
// configuration and resolver</param>.  
// <param name="message">XLANGMessage passed from   
// orchestration</param>.  
// <returns>Dictionary object fully populated</returns>.  
        Dictionary<string, string> Resolve(ResolverInfo resolverInfo, XLANGs.BaseTypes.XLANGMessage message);  
```  
  
 <span data-ttu-id="7f5cf-143">**解決**Microsoft.Practices.ESB.Resolver のプロジェクト構造もに格納されている名前/値ペアを定義、**ディクショナリ**インスタンス。</span><span class="sxs-lookup"><span data-stu-id="7f5cf-143">The **Resolution** structure, located in Microsoft.Practices.ESB.Resolver project, also defines the name/value pairs stored in the **Dictionary** instance.</span></span> <span data-ttu-id="7f5cf-144">**解決**構造がいくつかのプロパティを公開します。 最も関連する次の表を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="7f5cf-144">The **Resolution** structure exposes several properties; the following table lists the most relevant of these.</span></span> <span data-ttu-id="7f5cf-145">**CreateResolverDictionary**のメソッド、 **ResolutionHelper**空の文字列値を持つ、最も使用されているキーを格納している競合回避モジュール ディクショナリを生成するクラスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="7f5cf-145">The **CreateResolverDictionary** method of the **ResolutionHelper** class can be used to generate a resolver dictionary that contains the most used keys, with empty string values.</span></span> <span data-ttu-id="7f5cf-146">**ディクショナリ**インスタンスの具象実装を通じてカスタム競合回避モジュールの名前/値ペアの追加をサポートする、**リゾルバー**クラス。</span><span class="sxs-lookup"><span data-stu-id="7f5cf-146">The **Dictionary** instance supports the addition of custom resolver name/value pairs through a concrete implementation of the **Resolver** class.</span></span>  
  
|<span data-ttu-id="7f5cf-147">プロパティ</span><span class="sxs-lookup"><span data-stu-id="7f5cf-147">Property</span></span>|<span data-ttu-id="7f5cf-148">データ型</span><span class="sxs-lookup"><span data-stu-id="7f5cf-148">Data type</span></span>|<span data-ttu-id="7f5cf-149">データ型</span><span class="sxs-lookup"><span data-stu-id="7f5cf-149">Data type</span></span>|<span data-ttu-id="7f5cf-150">データ型</span><span class="sxs-lookup"><span data-stu-id="7f5cf-150">Data type</span></span>|  
|--------------|---------------|---------------|---------------|  
|<span data-ttu-id="7f5cf-151">**TransformType**</span><span class="sxs-lookup"><span data-stu-id="7f5cf-151">**TransformType**</span></span>|<span data-ttu-id="7f5cf-152">String</span><span class="sxs-lookup"><span data-stu-id="7f5cf-152">String</span></span>|<span data-ttu-id="7f5cf-153">**ActionField**</span><span class="sxs-lookup"><span data-stu-id="7f5cf-153">**ActionField**</span></span>|<span data-ttu-id="7f5cf-154">String</span><span class="sxs-lookup"><span data-stu-id="7f5cf-154">String</span></span>|  
|<span data-ttu-id="7f5cf-155">**成功**</span><span class="sxs-lookup"><span data-stu-id="7f5cf-155">**Success**</span></span>|<span data-ttu-id="7f5cf-156">ブール値</span><span class="sxs-lookup"><span data-stu-id="7f5cf-156">Boolean</span></span>|<span data-ttu-id="7f5cf-157">**EpmRRCorrelationTokenField**</span><span class="sxs-lookup"><span data-stu-id="7f5cf-157">**EpmRRCorrelationTokenField**</span></span>|<span data-ttu-id="7f5cf-158">String</span><span class="sxs-lookup"><span data-stu-id="7f5cf-158">String</span></span>|  
|<span data-ttu-id="7f5cf-159">**TransportNamespace**</span><span class="sxs-lookup"><span data-stu-id="7f5cf-159">**TransportNamespace**</span></span>|<span data-ttu-id="7f5cf-160">String</span><span class="sxs-lookup"><span data-stu-id="7f5cf-160">String</span></span>|<span data-ttu-id="7f5cf-161">**InboundTransportLocationField**</span><span class="sxs-lookup"><span data-stu-id="7f5cf-161">**InboundTransportLocationField**</span></span>|<span data-ttu-id="7f5cf-162">String</span><span class="sxs-lookup"><span data-stu-id="7f5cf-162">String</span></span>|  
|<span data-ttu-id="7f5cf-163">**TransportType**</span><span class="sxs-lookup"><span data-stu-id="7f5cf-163">**TransportType**</span></span>|<span data-ttu-id="7f5cf-164">String</span><span class="sxs-lookup"><span data-stu-id="7f5cf-164">String</span></span>|<span data-ttu-id="7f5cf-165">**InterchangeIDField**</span><span class="sxs-lookup"><span data-stu-id="7f5cf-165">**InterchangeIDField**</span></span>|<span data-ttu-id="7f5cf-166">String</span><span class="sxs-lookup"><span data-stu-id="7f5cf-166">String</span></span>|  
|<span data-ttu-id="7f5cf-167">**TransportLocation**</span><span class="sxs-lookup"><span data-stu-id="7f5cf-167">**TransportLocation**</span></span>|<span data-ttu-id="7f5cf-168">String</span><span class="sxs-lookup"><span data-stu-id="7f5cf-168">String</span></span>|<span data-ttu-id="7f5cf-169">**ReceiveLocationNameField**</span><span class="sxs-lookup"><span data-stu-id="7f5cf-169">**ReceiveLocationNameField**</span></span>|<span data-ttu-id="7f5cf-170">String</span><span class="sxs-lookup"><span data-stu-id="7f5cf-170">String</span></span>|  
|<span data-ttu-id="7f5cf-171">**操作**</span><span class="sxs-lookup"><span data-stu-id="7f5cf-171">**Action**</span></span>|<span data-ttu-id="7f5cf-172">String</span><span class="sxs-lookup"><span data-stu-id="7f5cf-172">String</span></span>|<span data-ttu-id="7f5cf-173">**ReceivePortNameField**</span><span class="sxs-lookup"><span data-stu-id="7f5cf-173">**ReceivePortNameField**</span></span>|<span data-ttu-id="7f5cf-174">String</span><span class="sxs-lookup"><span data-stu-id="7f5cf-174">String</span></span>|  
|<span data-ttu-id="7f5cf-175">**MessageExchangePattern**</span><span class="sxs-lookup"><span data-stu-id="7f5cf-175">**MessageExchangePattern**</span></span>|<span data-ttu-id="7f5cf-176">String</span><span class="sxs-lookup"><span data-stu-id="7f5cf-176">String</span></span>|<span data-ttu-id="7f5cf-177">**InboundTransportTypeField**</span><span class="sxs-lookup"><span data-stu-id="7f5cf-177">**InboundTransportTypeField**</span></span>|<span data-ttu-id="7f5cf-178">String</span><span class="sxs-lookup"><span data-stu-id="7f5cf-178">String</span></span>|  
|<span data-ttu-id="7f5cf-179">**EndpointConfig**</span><span class="sxs-lookup"><span data-stu-id="7f5cf-179">**EndpointConfig**</span></span>|<span data-ttu-id="7f5cf-180">String</span><span class="sxs-lookup"><span data-stu-id="7f5cf-180">String</span></span>|<span data-ttu-id="7f5cf-181">**IsRequestResponseField**</span><span class="sxs-lookup"><span data-stu-id="7f5cf-181">**IsRequestResponseField**</span></span>|<span data-ttu-id="7f5cf-182">String</span><span class="sxs-lookup"><span data-stu-id="7f5cf-182">String</span></span>|  
|<span data-ttu-id="7f5cf-183">**TargetNamespace**</span><span class="sxs-lookup"><span data-stu-id="7f5cf-183">**TargetNamespace**</span></span>|<span data-ttu-id="7f5cf-184">String</span><span class="sxs-lookup"><span data-stu-id="7f5cf-184">String</span></span>|<span data-ttu-id="7f5cf-185">**DocumentSpecStrongNameField**</span><span class="sxs-lookup"><span data-stu-id="7f5cf-185">**DocumentSpecStrongNameField**</span></span>|<span data-ttu-id="7f5cf-186">String</span><span class="sxs-lookup"><span data-stu-id="7f5cf-186">String</span></span>|  
|<span data-ttu-id="7f5cf-187">**FixJaxRPC**</span><span class="sxs-lookup"><span data-stu-id="7f5cf-187">**FixJaxRPC**</span></span>|<span data-ttu-id="7f5cf-188">ブール値</span><span class="sxs-lookup"><span data-stu-id="7f5cf-188">Boolean</span></span>|<span data-ttu-id="7f5cf-189">**DocumentSpecNameField**</span><span class="sxs-lookup"><span data-stu-id="7f5cf-189">**DocumentSpecNameField**</span></span>|<span data-ttu-id="7f5cf-190">String</span><span class="sxs-lookup"><span data-stu-id="7f5cf-190">String</span></span>|  
|<span data-ttu-id="7f5cf-191">**WindowUserField**</span><span class="sxs-lookup"><span data-stu-id="7f5cf-191">**WindowUserField**</span></span>|<span data-ttu-id="7f5cf-192">String</span><span class="sxs-lookup"><span data-stu-id="7f5cf-192">String</span></span>|<span data-ttu-id="7f5cf-193">**[MessageType]**</span><span class="sxs-lookup"><span data-stu-id="7f5cf-193">**MessageType**</span></span>|<span data-ttu-id="7f5cf-194">String</span><span class="sxs-lookup"><span data-stu-id="7f5cf-194">String</span></span>|  
|<span data-ttu-id="7f5cf-195">**CacheTimeout**</span><span class="sxs-lookup"><span data-stu-id="7f5cf-195">**CacheTimeout**</span></span>|<span data-ttu-id="7f5cf-196">String</span><span class="sxs-lookup"><span data-stu-id="7f5cf-196">String</span></span>|<span data-ttu-id="7f5cf-197">**OutboundTransportCLSID**</span><span class="sxs-lookup"><span data-stu-id="7f5cf-197">**OutboundTransportCLSID**</span></span>|<span data-ttu-id="7f5cf-198">String</span><span class="sxs-lookup"><span data-stu-id="7f5cf-198">String</span></span>|  
|<span data-ttu-id="7f5cf-199">**MethodNameField**</span><span class="sxs-lookup"><span data-stu-id="7f5cf-199">**MethodNameField**</span></span>|<span data-ttu-id="7f5cf-200">String</span><span class="sxs-lookup"><span data-stu-id="7f5cf-200">String</span></span>|||  
  
## <a name="creating-a-custom-resolver"></a><span data-ttu-id="7f5cf-201">カスタム競合回避モジュールを作成します。</span><span class="sxs-lookup"><span data-stu-id="7f5cf-201">Creating a Custom Resolver</span></span>  
 <span data-ttu-id="7f5cf-202">、実行時にパイプラインが競合回避モジュールの接続文字列を取得し、マネージャー、競合回避モジュールを呼び出し (のインスタンス、 **ResolverMgr**クラス)。</span><span class="sxs-lookup"><span data-stu-id="7f5cf-202">At run time, a pipeline retrieves the resolver connection string and calls the resolver manager (an instance of the **ResolverMgr** class).</span></span> <span data-ttu-id="7f5cf-203">競合回避モジュール マネージャーは、解析し、設定、および、競合回避モジュールの接続文字列を検証します。</span><span class="sxs-lookup"><span data-stu-id="7f5cf-203">The resolver manager parses, populates, and validates the resolver connection string.</span></span> <span data-ttu-id="7f5cf-204">これは、次の手順で。</span><span class="sxs-lookup"><span data-stu-id="7f5cf-204">It does this by doing the following:</span></span>  
  
- <span data-ttu-id="7f5cf-205">判断するために、接続文字列を解析**リゾルバー**を読み込んでおく型。</span><span class="sxs-lookup"><span data-stu-id="7f5cf-205">It parses the connection string to determine which **Resolver** type to load.</span></span>  
  
- <span data-ttu-id="7f5cf-206">(キーは、ルート モニカー、UDDI など)、構成ファイルで定義されているモニカーには、この型と一致します。</span><span class="sxs-lookup"><span data-stu-id="7f5cf-206">It matches this type to a moniker defined in the configuration file (the key is the root moniker, such as UDDI).</span></span>  
  
- <span data-ttu-id="7f5cf-207">このモニカーの競合回避モジュールのアセンブリ名を読み取ります。</span><span class="sxs-lookup"><span data-stu-id="7f5cf-207">It reads the assembly name of the resolver for this moniker.</span></span>  
  
- <span data-ttu-id="7f5cf-208">指定したアセンブリが読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="7f5cf-208">It loads the specified assembly.</span></span>  
  
  <span data-ttu-id="7f5cf-209">動的解決メカニズムの実装が読み込まれたすべてのキャッシュ、 **IResolveProvider**構成情報とアセンブリの読み込み時に、いくつかの受信メッセージを使用して、同じの繰り返しの読み取りを回避するためにインターフェイス競合回避モジュール。</span><span class="sxs-lookup"><span data-stu-id="7f5cf-209">The dynamic resolution mechanism caches all loaded implementations of the **IResolveProvider** interface to avoid repeated reading of configuration information and assembly loading when several incoming messages use the same resolver.</span></span>  
  
  <span data-ttu-id="7f5cf-210">競合回避モジュールのマネージャーが最後に、実行、**解決**の具象メソッド**IResolveProvider**実装を返しますが、設定された**ディクショナリ**インスタンス。</span><span class="sxs-lookup"><span data-stu-id="7f5cf-210">Finally, the resolver manager executes the **Resolve** method of the concrete **IResolveProvider** implementation and returns the populated **Dictionary** instance.</span></span>  
  
  <span data-ttu-id="7f5cf-211">**カスタム競合回避モジュールを作成するには**</span><span class="sxs-lookup"><span data-stu-id="7f5cf-211">**To create a custom resolver**</span></span>  
  
1.  <span data-ttu-id="7f5cf-212">実装するクラスを使用してアセンブリを作成、 **IResolveProvider**インターフェイスし、が含まれています、**解決**のインスタンスとの競合回避モジュールのファクトを返すメソッド、**ディクショナリ**クラス。</span><span class="sxs-lookup"><span data-stu-id="7f5cf-212">Create an assembly with a class that implements the **IResolveProvider** interface and contains a **Resolve** method that returns resolver facts as an instance of the **Dictionary** class.</span></span>  
  
2.  <span data-ttu-id="7f5cf-213">追加、Esb.config ファイルを使用して構成することによって、競合回避モジュールを登録、 **\<競合回避モジュール\>** としてルート モニカーを含む要素、**名前**属性と完全にアセンブリの修飾名として、**型**属性。</span><span class="sxs-lookup"><span data-stu-id="7f5cf-213">Register the resolver by adding it to the Esb.config configuration file using a **\<resolver\>** element that contains the root moniker as the **name** attribute and the fully qualified assembly name as the **type** attribute.</span></span>  
  
3.  <span data-ttu-id="7f5cf-214">(省略可能)ルート モニカーと、クエリ パラメーターを定義するスキーマを作成し、ESB で保存します。Schemas.Resolvers フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="7f5cf-214">(Optional) Create a schema that defines the root moniker and the query parameters, and then save it in the ESB.Schemas.Resolvers folder.</span></span> <span data-ttu-id="7f5cf-215">名前が既存の ESB 名前付け規則; に従う必要があります。これは、"_Resolution.xsd"を付加するルート モニカーの名前を使用することを意味します。</span><span class="sxs-lookup"><span data-stu-id="7f5cf-215">The name should follow existing ESB naming conventions; this means it should use the name of the root moniker appended with "_Resolution.xsd".</span></span>  
  
4.  <span data-ttu-id="7f5cf-216">(省略可能)新しいスキーマからクラスを生成し、カスタム競合回避モジュールのアセンブリに保存します。</span><span class="sxs-lookup"><span data-stu-id="7f5cf-216">(Optional) Generate a class from the new schema and save it in the custom resolver assembly.</span></span> <span data-ttu-id="7f5cf-217">これは、カスタムの競合回避モジュールに型指定されたパラメーターを公開します。</span><span class="sxs-lookup"><span data-stu-id="7f5cf-217">This exposes typed parameters in the custom resolver.</span></span>  
  
5.  <span data-ttu-id="7f5cf-218">グローバル アセンブリ キャッシュに新しいアセンブリを登録します。</span><span class="sxs-lookup"><span data-stu-id="7f5cf-218">Register the new assembly in the global assembly cache.</span></span>