---
title: Unity コンテナーでのカスタム競合回避モジュールの作成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d6f95f5e-64dd-4cc6-802f-0c5fd6a01c91
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b5280108bddeeacd78b9e8f6df0fa908329af8dd
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37012675"
---
# <a name="creating-a-custom-resolver-with-a-unity-container"></a><span data-ttu-id="c0f00-102">Unity コンテナーでのカスタム競合回避モジュールを作成します。</span><span class="sxs-lookup"><span data-stu-id="c0f00-102">Creating a Custom Resolver with a Unity Container</span></span>
<span data-ttu-id="c0f00-103">使用してカスタム競合回避モジュールを作成することができます、 [Unity Application Block](http://go.microsoft.com/fwlink/?LinkId=188286) (Unity) ([http://go.microsoft.com/fwlink/?LinkId=188286](http://go.microsoft.com/fwlink/?LinkId=188286)) の解決ロジックとメタデータのソースの実行時の依存関係の挿入します。</span><span class="sxs-lookup"><span data-stu-id="c0f00-103">You can create a custom resolver using the [Unity Application Block](http://go.microsoft.com/fwlink/?LinkId=188286) (Unity) ([http://go.microsoft.com/fwlink/?LinkId=188286](http://go.microsoft.com/fwlink/?LinkId=188286)) for run-time dependency injection of resolution logic and metadata sources.</span></span>
  
 <span data-ttu-id="c0f00-104">**ファクトのプロバイダー**</span><span class="sxs-lookup"><span data-stu-id="c0f00-104">**Fact Providers**</span></span>  
  
 <span data-ttu-id="c0f00-105">ファクトのプロバイダーを実装するクラスのインスタンスである、 **IFactProvider**インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="c0f00-105">Fact providers are instances of classes that implement the **IFactProvider** interface.</span></span> <span data-ttu-id="c0f00-106">このインターフェイスは、という名前のメソッドの 3 つの異なるオーバー ロードを公開**RegisterFact**します。</span><span class="sxs-lookup"><span data-stu-id="c0f00-106">This interface exposes three different overloads of a method named **RegisterFact**.</span></span> <span data-ttu-id="c0f00-107">このメソッドは、メッセージの競合回避モジュールの構成、および場合によっては、パイプラインのコンテキストを受け取るし、オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="c0f00-107">This method takes in the message, the resolver configuration, and, in some cases, the pipeline context, and returns an object.</span></span> <span data-ttu-id="c0f00-108">このオブジェクトは何らかの方法で、入力から抽出された情報には、何らかの形式の計算がある可能性があります。 またはいくつかの外部ソースから見えるかもしれません。</span><span class="sxs-lookup"><span data-stu-id="c0f00-108">This object may be information extracted from the inputs in some way, it may be a calculation of some form, or it may be looked up from some external source.</span></span> <span data-ttu-id="c0f00-109">ファクト プロバイダーによって返される各オブジェクトをファクトとして参照でき、通常、ファクトの翻訳者によって後で使用できる解決コンテナーによって、一覧に追加されます。</span><span class="sxs-lookup"><span data-stu-id="c0f00-109">Each object returned by a fact provider can be referred to as a fact and is typically added to a list by the resolve container for later use by a fact translator.</span></span>  
  
 <span data-ttu-id="c0f00-110">Unity の競合回避モジュールを追加または 1 つの構成変更をいつでも削除できる 0 個以上のファクトのプロバイダーがあります。</span><span class="sxs-lookup"><span data-stu-id="c0f00-110">A Unity resolver may have zero or more fact providers that can be added or removed at any time with a single configuration change.</span></span>  
  
 <span data-ttu-id="c0f00-111">次のコードは、ファクトのプロバイダーに含まれるロジックの例です。</span><span class="sxs-lookup"><span data-stu-id="c0f00-111">The following code is an example of the logic contained in a fact provider.</span></span> <span data-ttu-id="c0f00-112">このコードは、ESB の ItineraryStaticFactProvider.cs ファイルでもあります。Resolver.Itinerary.Facts プロジェクトです。</span><span class="sxs-lookup"><span data-stu-id="c0f00-112">This code can also be found in the ItineraryStaticFactProvider.cs file of the ESB.Resolver.Itinerary.Facts project.</span></span> <span data-ttu-id="c0f00-113">競合回避モジュールの接続文字列から名前と、スケジュールのバージョンを収集し、日程静的リゾルバーでのコンポーネントになります。</span><span class="sxs-lookup"><span data-stu-id="c0f00-113">It is a component in the ITINERARY-STATIC resolver that gathers the name and version of an itinerary from the resolver connection string.</span></span>  
  
```csharp  
public object RegisterFact(IBaseMessage message, IPipelineContext pipelineContext, Dictionary\<string, string\> resolverContents)  
{  
    return GetItineraryFactFromResolver(resolverContents);  
}  
  
private static object GetItineraryFactFromResolver(Dictionary\<string, string\> resolverContents)  
{              
    if (resolverContents == null)  
        throw new ArgumentNullException("resolverContents");  
  
    ItineraryFact itineraryFact = new ItineraryFact();  
    itineraryFact.Name = ResolverMgr.GetConfigValue(resolverContents, true, "name");  
    string version = ResolverMgr.GetConfigValue(resolverContents, false, "version");  
    if (!string.IsNullOrEmpty(version))  
    {  
        EventLogger.Write(string.Format("Version set with value {0}.", version));  
        itineraryFact.SetVersion(version);  
    }  
    return itineraryFact;  
}  
```  
  
 <span data-ttu-id="c0f00-114">**ファクトの翻訳者**</span><span class="sxs-lookup"><span data-stu-id="c0f00-114">**Fact Translators**</span></span>  
  
 <span data-ttu-id="c0f00-115">ファクトの翻訳者を実装するクラスのインスタンスである、 **IFactTranslator**インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="c0f00-115">Fact translators are instances of classes that implement the **IFactTranslator** interface.</span></span> <span data-ttu-id="c0f00-116">このインターフェイスは、という名前の 1 つのメソッドを公開**TranslateFact**します。</span><span class="sxs-lookup"><span data-stu-id="c0f00-116">This interface exposes a single method named **TranslateFact**.</span></span> <span data-ttu-id="c0f00-117">このメソッドは、一連のファクトとファクト translator を使用して競合回避モジュールによって後で返される競合回避モジュール ディクショナリを格納しているオブジェクト配列で受け取ります。</span><span class="sxs-lookup"><span data-stu-id="c0f00-117">This method takes in an object array that contains a list of facts and the resolver dictionary that will later be returned by the resolver using the fact translator.</span></span> <span data-ttu-id="c0f00-118">ファクトのトランスレーターは、わかりやすい方法でファクト プロバイダーによって提供されるファクトの処理と、競合回避モジュール ディクショナリを担当します。</span><span class="sxs-lookup"><span data-stu-id="c0f00-118">A fact translator is responsible for processing the facts provided by the fact providers in a meaningful way and then populating the resolver dictionary.</span></span>  
  
 <span data-ttu-id="c0f00-119">Unity の競合回避モジュールには、0 個以上のファクト翻訳を追加または 1 つの構成変更をいつでも削除できる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c0f00-119">A Unity resolver may have zero or more fact translators that can be added or removed at any time with a single configuration change.</span></span>  
  
 <span data-ttu-id="c0f00-120">次のコードに含まれるファクト translator ロジックの例に示します。</span><span class="sxs-lookup"><span data-stu-id="c0f00-120">The following code is an example of the logic contained in a fact translator.</span></span> <span data-ttu-id="c0f00-121">このコードは、ESB の ItineraryStaticFactTranslator.cs ファイルでもあります。Resolver.Itinerary.Facts プロジェクトです。</span><span class="sxs-lookup"><span data-stu-id="c0f00-121">This code can also be found in the ItineraryStaticFactTranslator.cs file of the ESB.Resolver.Itinerary.Facts project.</span></span> <span data-ttu-id="c0f00-122">名前と、必要に応じて、バージョンによって、日程の旅行プラン XML を収集するために、データベース クエリを実行するスケジュール静的競合回避モジュール内のコンポーネントになります。</span><span class="sxs-lookup"><span data-stu-id="c0f00-122">It is a component in the ITINERARY-STATIC resolver that performs a database query to gather the itinerary XML for an itinerary by name and, optionally, by version.</span></span>  
  
```csharp  
public void TranslateFact(object[] facts, Dictionary\<string, string\> factDictionary)  
{  
    #region Argument Check  
    if (null == facts) throw new ArgumentNullException("fact");  
    if (null == factDictionary) throw new ArgumentNullException("factDictionary");  
    #endregion  
  
    #region Local Variables  
    Version version = new Version(1, 0);                         
    #endregion  
    try  
    {  
        foreach (object fact in facts)  
        {  
            if (fact is ItineraryFact)  
            {  
                ItineraryFact targetFact = (ItineraryFact)fact;  
                factDictionary.Add(_FactKeyItineraryName, targetFact.Name ?? string.Empty);  
                if (null != targetFact.Version)  
                {  
                    factDictionary.Add(_FactKeyItineraryVersion, targetFact.Version.ToString(2) ?? string.Empty);  
                    version = targetFact.Version;  
                }  
  
                string xml = null;  
  
                if (targetFact.Version != null)  
                {  
                    xml = _repositoryProvider.GetItinerary(targetFact.Name, version.Major, version.Minor);  
                }  
                else  
                {  
                    xml = _repositoryProvider.GetItinerary(targetFact.Name);  
                }  
                if (!string.IsNullOrEmpty(xml))  
                {  
                    factDictionary.Add(_FactKeyItinerary, xml);  
                }  
  
                break;  
            }  
        }  
    }  
    #region Exception Handling  
    catch (System.Exception)  
    {  
        throw;  
    }              
    #endregion  
}  
#endregion  
```  
  
 <span data-ttu-id="c0f00-123">**コンテナーを解決するには**</span><span class="sxs-lookup"><span data-stu-id="c0f00-123">**Resolve Containers**</span></span>  
  
 <span data-ttu-id="c0f00-124">解決するコンテナーを実装するクラスとは、 **IResolveContainer**インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="c0f00-124">A resolve container is a class that implements the **IResolveContainer** interface.</span></span> <span data-ttu-id="c0f00-125">実装して、通常、 **IResolveProvider**インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="c0f00-125">Typically, it also implements the **IResolveProvider** interface.</span></span> <span data-ttu-id="c0f00-126">**IResolveContainer**インターフェイスという単一のメソッドを公開する**初期化**内を取得、 **IUnityContainer**します。</span><span class="sxs-lookup"><span data-stu-id="c0f00-126">The **IResolveContainer** interface exposes a single method named **Initialize** that takes in an **IUnityContainer**.</span></span> <span data-ttu-id="c0f00-127">このメソッドに渡されるコンテナーには、依存関係がすべて含まれます (クラスのインスタンスは、 **IFactProvider**と**IFactTranslator**、および必要なその他のすべての種類) に必要なその処理の完了に競合回避モジュール。</span><span class="sxs-lookup"><span data-stu-id="c0f00-127">The container passed to this method will contain all of the dependencies (that is, instances of the classes **IFactProvider** and **IFactTranslator**, and any other types required) necessary for the resolver to complete its processing.</span></span>  
  
 <span data-ttu-id="c0f00-128">次のコードの実装の例は、 **IResolveContainer**インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="c0f00-128">The following code is an example of an implementation of the **IResolveContainer** interface.</span></span> <span data-ttu-id="c0f00-129">このコードは、ESB の StaticItineraryResolveContainer.cs ファイルでもあります。Resolver.Itinerary プロジェクトです。</span><span class="sxs-lookup"><span data-stu-id="c0f00-129">This code can also be found in the StaticItineraryResolveContainer.cs file of the ESB.Resolver.Itinerary project.</span></span>  
  
```csharp  
#region IResolveContainer Members  
  
private static IUnityContainer Container;  
  
// <summary>  
// This is used by the Unity resolver to initialize the current   
// object with the Unity container.  
// </summary>  
// <param name="container">Unity container used for dependency   
// injection.</param>  
// <remarks>  
// The container used is the ITINERARY container, although this is   
// configurable in Esb.config.  
// </remarks>  
  
public void Initialize(IUnityContainer container)  
{  
  if (container == null)  
    throw new ArgumentNullException("container");  
  
  Container = container;  
}  
#endregion  
```  
  
 <span data-ttu-id="c0f00-130">実装では、解決のコンテナーで、**解決**からメソッド、 **IResolveProvider**すべてのファクトのプロバイダーと、Unity でのファクトの翻訳者を反復処理する必要があるインターフェイスそれぞれの処理を実行するを許可するコンテナーです。</span><span class="sxs-lookup"><span data-stu-id="c0f00-130">In a resolve container, in the implementations of the **Resolve** methods from the **IResolveProvider** interface, it is necessary to iterate through all the fact providers and fact translators in the Unity container to allow each of them to perform their processing.</span></span>  
  
 <span data-ttu-id="c0f00-131">次のコードは、解決のコンテナーに含まれるロジックの例です。</span><span class="sxs-lookup"><span data-stu-id="c0f00-131">The following code is an example of the logic contained in a Resolve container.</span></span> <span data-ttu-id="c0f00-132">このコードは、ESB の StaticItineraryResolveContainer.cs ファイルでもあります。Resolver.Itinerary プロジェクトです。</span><span class="sxs-lookup"><span data-stu-id="c0f00-132">This code can also be found in the StaticItineraryResolveContainer.cs file of the ESB.Resolver.Itinerary project.</span></span>  
  
```csharp  
public Dictionary\<string, string\> Resolve(ResolverInfo resolverInfo,  
    XLANGMessage message)  
{  
    #region Argument Check  
    if (String.IsNullOrEmpty(resolverInfo.Config))  
        throw new ArgumentNullException("resolverInfo.Config");  
    if (String.IsNullOrEmpty(resolverInfo.Resolver))  
        throw new ArgumentNullException("resolverInfo.Resolver");  
    if (null == message)  
        throw new ArgumentNullException("message");  
    #endregion Argument Check  
  
    return ResolveStatic(resolverInfo.Config, resolverInfo.Resolver,  
        (factProvider, resolverContent) =>   
            factProvider.RegisterFact(message, resolverContent)  
     );  
}          
  
private Dictionary\<string, string\> ResolveStatic(string config, string resolver,   
    Func<IFactProvider, Dictionary\<string, string\>, object> RegisterFact)  
{  
    try  
    {  
        EventLogger.Write(string.Format("Received {0} value in ITINERARY STATIC resolver.", config));  
  
        Dictionary\<string, string\> queryParams =  
                ResolverMgr.GetFacts(config, resolver);  
  
        List<object> facts = new List<object>();  
  
        foreach (IFactProvider factProvider in Container.ResolveAll<IFactProvider>())  
        {  
            facts.Add(RegisterFact(factProvider, queryParams));  
        }  
  
        Dictionary\<string, string\> resolverDictionary = new Dictionary\<string, string\>();  
  
        object[] convertedFacts = facts.ToArray();  
  
        foreach (IFactTranslator translator in Container.ResolveAll<IFactTranslator>())  
        {  
            translator.TranslateFact(convertedFacts, resolverDictionary);  
        }  
  
        return resolverDictionary;  
    }  
    catch (System.Exception ex)  
    {  
        EventLogger.Write(MethodInfo.GetCurrentMethod(), ex);  
        throw;  
    }  
}  
```  
  
 <span data-ttu-id="c0f00-133">**Unity のカスタム競合回避モジュールを構成します。**</span><span class="sxs-lookup"><span data-stu-id="c0f00-133">**Configuring a Custom Unity Resolver**</span></span>  
  
 <span data-ttu-id="c0f00-134">カスタム Unity 競合回避モジュールを構成するには、同じの構成手順として適用カスタム競合回避モジュール; を作成するときにただし、競合回避モジュールを構成するコンポーネントを正しく登録するために含める必要があるいくつか追加の構成があります。</span><span class="sxs-lookup"><span data-stu-id="c0f00-134">To configure a custom Unity resolver, the same configuration steps apply as when creating a custom resolver; however, there is some additional configuration that must be included to properly register the components that make up the resolver.</span></span>  
  
 <span data-ttu-id="c0f00-135">最初に、競合回避モジュールの宣言の下の Esb.config ファイルを**resolverConfig**プロパティは、次の 2 つのノードを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c0f00-135">First, in the Esb.config file, under the resolver declaration, a **resolverConfig** node must be added with the following two properties:</span></span>  
  
- <span data-ttu-id="c0f00-136">**unitySectionName**します。</span><span class="sxs-lookup"><span data-stu-id="c0f00-136">**unitySectionName**.</span></span> <span data-ttu-id="c0f00-137">このプロパティには、Unity アプリケーション ブロックの構成を含む構成ファイルで構成セクションの名前が含まれていますこのプロパティの値は、既定では、 **esb.resolver**します。</span><span class="sxs-lookup"><span data-stu-id="c0f00-137">This property contains the name of the configuration section in the configuration file that contains the configuration for the Unity Application Block; by default, the value for this property is **esb.resolver**.</span></span>  
  
- <span data-ttu-id="c0f00-138">**unityContainerName**します。</span><span class="sxs-lookup"><span data-stu-id="c0f00-138">**unityContainerName**.</span></span> <span data-ttu-id="c0f00-139">このプロパティには、カスタム競合回避モジュールに固有の Unity の構成で定義されている Unity コンテナーの名前が含まれています。</span><span class="sxs-lookup"><span data-stu-id="c0f00-139">This property contains the name of the Unity container defined in the Unity configuration specific to your custom resolver.</span></span>  
  
  <span data-ttu-id="c0f00-140">次の XML で必要な構成の例に示します、**リゾルバー**ノード。</span><span class="sxs-lookup"><span data-stu-id="c0f00-140">The following XML is an example of the configuration necessary in the **resolvers** node.</span></span>  
  
```xml  
<resolver name="ITINERARY-STATIC" type="Microsoft.Practices.ESB.Resolver.Unity.ResolveProvider, Microsoft.Practices.ESB.Resolver.Unity, Version=2.0.0.0, Culture=neutral, PublicKeyToken=c62dd63c784d6e22">  
     <resolverConfig>  
          <add name="unitySectionName" value="esb.resolver" />  
          <add name="unityContainerName" value="ITINERARY" />  
     </resolverConfig>  
</resolver>  
```  
  
 <span data-ttu-id="c0f00-141">次の XML の下に必要な構成の例に示します、 **esb.resolver**ノード。</span><span class="sxs-lookup"><span data-stu-id="c0f00-141">The following XML is an example of the configuration necessary under the **esb.resolver** node.</span></span>  
  
```xml  
<typeAliases>  
     <!-- Lifetime manager types -->  
     <typeAlias alias="singleton" type="Microsoft.Practices.Unity.ContainerControlledLifetimeManager, Microsoft.Practices.Unity, Version=1.2.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35" />  
     <!-- std type providers -->  
     <typeAlias alias="string" type="System.String, mscorlib"/>  
     <typeAlias alias="int" type="System.Int32, mscorlib"/>  
     <!-- repository providers -->  
     <typeAlias alias="IRepositoryProvider" type="Microsoft.Practices.ESB.Resolver.Itinerary.Facts.Repository.IRepositoryProvider, Microsoft.Practices.ESB.Resolver.Itinerary.Facts, Version=2.0.0.0, Culture=neutral, PublicKeyToken=c62dd63c784d6e22"/>  
     <typeAlias alias="SqlRepositoryProvider" type="Microsoft.Practices.ESB.Resolver.Itinerary.DataAccess.SqlRepositoryProvider, Microsoft.Practices.ESB.Resolver.Itinerary.DataAccess, Version=2.0.0.0, Culture=neutral, PublicKeyToken=c62dd63c784d6e22"/>  
     <!-- fact providers -->  
     <typeAlias alias="IFactProvider" type="Microsoft.Practices.ESB.Resolver.Facts.IFactProvider, Microsoft.Practices.ESB.Resolver.Facts, Version=2.0.0.0, Culture=neutral, PublicKeyToken=c62dd63c784d6e22"/>  
     <typeAlias alias="IFactTranslator" type="Microsoft.Practices.ESB.Resolver.Facts.IFactTranslator, Microsoft.Practices.ESB.Resolver.Facts, Version=2.0.0.0, Culture=neutral, PublicKeyToken=c62dd63c784d6e22"/>  
     <typeAlias alias="ItineraryFactProvider" type="Microsoft.Practices.ESB.Resolver.Itinerary.Facts.ItineraryFactProvider, Microsoft.Practices.ESB.Resolver.Itinerary.Facts, Version=2.0.0.0, Culture=neutral, PublicKeyToken=c62dd63c784d6e22"/>  
     <typeAlias alias="ItineraryStaticFactProvider" type="Microsoft.Practices.ESB.Resolver.Itinerary.Facts.ItineraryStaticFactProvider, Microsoft.Practices.ESB.Resolver.Itinerary.Facts, Version=2.0.0.0, Culture=neutral, PublicKeyToken=c62dd63c784d6e22"/>  
     <typeAlias alias="ItineraryHeaderFactProvider" type="Microsoft.Practices.ESB.Resolver.Itinerary.Facts.ItineraryHeaderFactProvider, Microsoft.Practices.ESB.Resolver.Itinerary.Facts, Version=2.0.0.0, Culture=neutral, PublicKeyToken=c62dd63c784d6e22"/>  
     <typeAlias alias="ResolutionFactProvider" type="Microsoft.Practices.ESB.Resolver.Itinerary.Facts.ResolutionFactProvider, Microsoft.Practices.ESB.Resolver.Itinerary.Facts, Version=2.0.0.0, Culture=neutral, PublicKeyToken=c62dd63c784d6e22"/>  
     <typeAlias alias="DefaultFactTranslator" type="Microsoft.Practices.ESB.Resolver.Facts.DefaultFactTranslator, Microsoft.Practices.ESB.Resolver.Facts, Version=2.0.0.0, Culture=neutral, PublicKeyToken=c62dd63c784d6e22"/>  
     <typeAlias alias="ItineraryFactTranslator" type="Microsoft.Practices.ESB.Resolver.Itinerary.Facts.ItineraryFactTranslator, Microsoft.Practices.ESB.Resolver.Itinerary.Facts, Version=2.0.0.0, Culture=neutral, PublicKeyToken=c62dd63c784d6e22"/>  
     <!-- resolve providers -->  
     <typeAlias alias="IResolveProvider" type="Microsoft.Practices.ESB.Resolver.IResolveProvider, Microsoft.Practices.ESB.Resolver, Version=2.0.0.0, Culture=neutral, PublicKeyToken=c62dd63c784d6e22"/>  
     <typeAlias alias="ItineraryResolveProvider" type="Microsoft.Practices.ESB.Resolver.Itinerary.BREItineraryResolverContainer,Microsoft.Practices.ESB.Resolver.Itinerary, Version=2.0.0.0, Culture=neutral, PublicKeyToken=c62dd63c784d6e22 "/>  
     <typeAlias alias="StaticItineraryResolveProvider" type="Microsoft.Practices.ESB.Resolver.Itinerary.StaticItineraryResolveContainer,Microsoft.Practices.ESB.Resolver.Itinerary, Version=2.0.0.0, Culture=neutral, PublicKeyToken=c62dd63c784d6e22 "/>  
</typeAliases>  
<containers>  
     <container name="ITINERARY">  
          <types>  
               <type type="IResolveProvider" mapTo="StaticItineraryResolveProvider" />  
               <type type="IRepositoryProvider" mapTo="SqlRepositoryProvider" name="CurrentRepositoryProvider">  
                    <lifetime type="singleton" />  
                    <typeConfig extensionType="Microsoft.Practices.Unity.Configuration.TypeInjectionElement,Microsoft.Practices.Unity.Configuration, Version=1.2.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35">  
                         <constructor>  
                              <param name="connectionStringName" parameterType="string">  
                                   <value value="ItineraryDb"/>  
                              </param>  
                              <param name="cacheManagerName" parameterType="string">  
                                   <value value="Itinerary Cache Manager"/>  
                              </param>  
                              <param name="cacheTimeout" parameterType="string">  
                                   <value value="120" />  
                              </param>  
                         </constructor>  
                    </typeConfig>  
               </type>  
               <type type="IFactProvider" mapTo="ResolutionFactProvider" name="ResolutionFactProvider"  />  
               <type type="IFactProvider" mapTo="ItineraryHeaderFactProvider" name="HeaderFactProvider"  />  
               <type type="IFactProvider" mapTo="ItineraryStaticFactProvider" name="StaticFactProvider"  />  
               <type type="IFactTranslator" mapTo="DefaultFactTranslator" name="DefaultFactTranslator">  
                    <lifetime type="singleton" />  
               </type>  
               <type type="IFactTranslator" mapTo="ItineraryFactTranslator" name="ItineraryFactTranslator">  
                    <lifetime type="singleton" />  
                    <typeConfig extensionType="Microsoft.Practices.Unity.Configuration.TypeInjectionElement,Microsoft.Practices.Unity.Configuration, Version=1.2.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35">  
                         <constructor>  
                              <param name="repositoryProvider" parameterType="IRepositoryProvider">  
                                   <dependency name="CurrentRepositoryProvider"/>  
                              </param>  
                         </constructor>  
                    </typeConfig>  
               </type>  
          </types>  
     </container>  
</containers>  
```  
  
 <span data-ttu-id="c0f00-142">詳細のために必要な構成については、 **esb.resolvers**ノードを参照してください[Unity Application Block の送信元スキーマ](http://go.microsoft.com/fwlink/?LinkId=188288)([ http://go.microsoft.com/fwlink/?LinkId=188288 ](http://go.microsoft.com/fwlink/?LinkId=188288)) msdn です。</span><span class="sxs-lookup"><span data-stu-id="c0f00-142">For detailed information about the configuration that is necessary in the **esb.resolvers** node, see [Source Schema for the Unity Application Block](http://go.microsoft.com/fwlink/?LinkId=188288) ([http://go.microsoft.com/fwlink/?LinkId=188288](http://go.microsoft.com/fwlink/?LinkId=188288)) on MSDN.</span></span>  
  
 <span data-ttu-id="c0f00-143">**Unity のカスタム競合回避モジュールを作成します。**</span><span class="sxs-lookup"><span data-stu-id="c0f00-143">**Creating a Custom Unity Resolver**</span></span>  
  
 <span data-ttu-id="c0f00-144">**カスタム Unity 競合回避モジュールを作成するには**</span><span class="sxs-lookup"><span data-stu-id="c0f00-144">**To create a custom Unity resolver**</span></span>  
  
1.  <span data-ttu-id="c0f00-145">(省略可能)実装するクラスを使用して、アセンブリまたはアセンブリを作成、 **IFactProvider**インターフェイスし、が含まれています、 **RegisterFact**解像度が発生するために必要な情報を提供するメソッド。</span><span class="sxs-lookup"><span data-stu-id="c0f00-145">(Optional) Create an assembly or assemblies with a class that implements the **IFactProvider** interface and contains a **RegisterFact** method that provides information necessary for resolution to occur.</span></span>  
  
2.  <span data-ttu-id="c0f00-146">(省略可能)実装するクラスを使用して、アセンブリまたはアセンブリを作成、 **IFactTranslator**インターフェイスし、が含まれています、 **TranslateFact**キー/値ペア内に指定されたファクトを変換するメソッド、競合回避モジュールのディクショナリ。</span><span class="sxs-lookup"><span data-stu-id="c0f00-146">(Optional) Create an assembly or assemblies with a class that implements the **IFactTranslator** interface and contains a **TranslateFact** method that translates the provided facts to key/value pairs within the resolver dictionary.</span></span>  
  
3.  <span data-ttu-id="c0f00-147">実装するクラスを使用してアセンブリを作成、 **IResolveContainer**と**IResolveProvider**インターフェイスを含む、**解決**を検証するメソッド、競合回避モジュール構成では、ファクト プロバイダーからすべてのファクトを収集し、任意の特殊な処理を実行しますはファクトのトランスレーターを使用してそれを変換およびのインスタンスとして変換されたファクトを返します、**ディクショナリ**クラス。</span><span class="sxs-lookup"><span data-stu-id="c0f00-147">Create an assembly with a class that implements the **IResolveContainer** and **IResolveProvider** interface and that contains a **Resolve** method that validates the resolver configuration, gathers all the facts from the fact providers, performs any specialized processing, translates them using the fact translators, and returns the translated facts as an instance of the **Dictionary** class.</span></span>  
  
4.  <span data-ttu-id="c0f00-148">追加、Esb.config ファイルを使用して構成することによって、競合回避モジュールを登録、 **\<競合回避モジュール\>** としてルート モニカーを含む要素、**名前**属性と完全にアセンブリの修飾名として、**型**属性。</span><span class="sxs-lookup"><span data-stu-id="c0f00-148">Register the resolver by adding it to the Esb.config configuration file using a **\<resolver\>** element that contains the root moniker as the **name** attribute and the fully qualified assembly name as the **type** attribute.</span></span>  
  
5.  <span data-ttu-id="c0f00-149">この競合回避モジュールの Esb.config ファイルを Unity に固有の構成を追加します。</span><span class="sxs-lookup"><span data-stu-id="c0f00-149">Add the Unity-specific configuration to the Esb.config file for this resolver.</span></span>  
  
6.  <span data-ttu-id="c0f00-150">(省略可能)ルート モニカーと、クエリ パラメーターを定義するスキーマを作成し、ESB で保存します。Schemas.Resolvers フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="c0f00-150">(Optional) Create a schema that defines the root moniker and the query parameters, and then save it in the ESB.Schemas.Resolvers folder.</span></span> <span data-ttu-id="c0f00-151">名前が既存の ESB 名前付け規則; に従う必要があります。これは、"_Resolution.xsd"を付加するルート モニカーの名前を使用することを意味します。</span><span class="sxs-lookup"><span data-stu-id="c0f00-151">The name should follow existing ESB naming conventions; this means it should use the name of the root moniker appended with "_Resolution.xsd".</span></span>  
  
7.  <span data-ttu-id="c0f00-152">(省略可能)新しいスキーマからクラスを生成し、カスタム競合回避モジュールのアセンブリに保存します。</span><span class="sxs-lookup"><span data-stu-id="c0f00-152">(Optional) Generate a class from the new schema and save it in the custom resolver assembly.</span></span> <span data-ttu-id="c0f00-153">これにより、カスタムの競合回避モジュールに型指定されたパラメーターを公開します。</span><span class="sxs-lookup"><span data-stu-id="c0f00-153">This will expose typed parameters in the custom resolver.</span></span>  
  
8.  <span data-ttu-id="c0f00-154">グローバル アセンブリ キャッシュ内のすべてのアセンブリを登録します。</span><span class="sxs-lookup"><span data-stu-id="c0f00-154">Register all the assemblies in the global assembly cache.</span></span>