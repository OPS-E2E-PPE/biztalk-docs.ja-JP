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
# <a name="creating-a-custom-resolver-with-a-unity-container"></a>Unity コンテナーでのカスタム競合回避モジュールを作成します。
使用してカスタム競合回避モジュールを作成することができます、 [Unity Application Block](http://go.microsoft.com/fwlink/?LinkId=188286) (Unity) ([http://go.microsoft.com/fwlink/?LinkId=188286](http://go.microsoft.com/fwlink/?LinkId=188286)) の解決ロジックとメタデータのソースの実行時の依存関係の挿入します。
  
 **ファクトのプロバイダー**  
  
 ファクトのプロバイダーを実装するクラスのインスタンスである、 **IFactProvider**インターフェイス。 このインターフェイスは、という名前のメソッドの 3 つの異なるオーバー ロードを公開**RegisterFact**します。 このメソッドは、メッセージの競合回避モジュールの構成、および場合によっては、パイプラインのコンテキストを受け取るし、オブジェクトを返します。 このオブジェクトは何らかの方法で、入力から抽出された情報には、何らかの形式の計算がある可能性があります。 またはいくつかの外部ソースから見えるかもしれません。 ファクト プロバイダーによって返される各オブジェクトをファクトとして参照でき、通常、ファクトの翻訳者によって後で使用できる解決コンテナーによって、一覧に追加されます。  
  
 Unity の競合回避モジュールを追加または 1 つの構成変更をいつでも削除できる 0 個以上のファクトのプロバイダーがあります。  
  
 次のコードは、ファクトのプロバイダーに含まれるロジックの例です。 このコードは、ESB の ItineraryStaticFactProvider.cs ファイルでもあります。Resolver.Itinerary.Facts プロジェクトです。 競合回避モジュールの接続文字列から名前と、スケジュールのバージョンを収集し、日程静的リゾルバーでのコンポーネントになります。  
  
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
  
 **ファクトの翻訳者**  
  
 ファクトの翻訳者を実装するクラスのインスタンスである、 **IFactTranslator**インターフェイス。 このインターフェイスは、という名前の 1 つのメソッドを公開**TranslateFact**します。 このメソッドは、一連のファクトとファクト translator を使用して競合回避モジュールによって後で返される競合回避モジュール ディクショナリを格納しているオブジェクト配列で受け取ります。 ファクトのトランスレーターは、わかりやすい方法でファクト プロバイダーによって提供されるファクトの処理と、競合回避モジュール ディクショナリを担当します。  
  
 Unity の競合回避モジュールには、0 個以上のファクト翻訳を追加または 1 つの構成変更をいつでも削除できる可能性があります。  
  
 次のコードに含まれるファクト translator ロジックの例に示します。 このコードは、ESB の ItineraryStaticFactTranslator.cs ファイルでもあります。Resolver.Itinerary.Facts プロジェクトです。 名前と、必要に応じて、バージョンによって、日程の旅行プラン XML を収集するために、データベース クエリを実行するスケジュール静的競合回避モジュール内のコンポーネントになります。  
  
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
  
 **コンテナーを解決するには**  
  
 解決するコンテナーを実装するクラスとは、 **IResolveContainer**インターフェイス。 実装して、通常、 **IResolveProvider**インターフェイス。 **IResolveContainer**インターフェイスという単一のメソッドを公開する**初期化**内を取得、 **IUnityContainer**します。 このメソッドに渡されるコンテナーには、依存関係がすべて含まれます (クラスのインスタンスは、 **IFactProvider**と**IFactTranslator**、および必要なその他のすべての種類) に必要なその処理の完了に競合回避モジュール。  
  
 次のコードの実装の例は、 **IResolveContainer**インターフェイス。 このコードは、ESB の StaticItineraryResolveContainer.cs ファイルでもあります。Resolver.Itinerary プロジェクトです。  
  
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
  
 実装では、解決のコンテナーで、**解決**からメソッド、 **IResolveProvider**すべてのファクトのプロバイダーと、Unity でのファクトの翻訳者を反復処理する必要があるインターフェイスそれぞれの処理を実行するを許可するコンテナーです。  
  
 次のコードは、解決のコンテナーに含まれるロジックの例です。 このコードは、ESB の StaticItineraryResolveContainer.cs ファイルでもあります。Resolver.Itinerary プロジェクトです。  
  
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
  
 **Unity のカスタム競合回避モジュールを構成します。**  
  
 カスタム Unity 競合回避モジュールを構成するには、同じの構成手順として適用カスタム競合回避モジュール; を作成するときにただし、競合回避モジュールを構成するコンポーネントを正しく登録するために含める必要があるいくつか追加の構成があります。  
  
 最初に、競合回避モジュールの宣言の下の Esb.config ファイルを**resolverConfig**プロパティは、次の 2 つのノードを追加する必要があります。  
  
- **unitySectionName**します。 このプロパティには、Unity アプリケーション ブロックの構成を含む構成ファイルで構成セクションの名前が含まれていますこのプロパティの値は、既定では、 **esb.resolver**します。  
  
- **unityContainerName**します。 このプロパティには、カスタム競合回避モジュールに固有の Unity の構成で定義されている Unity コンテナーの名前が含まれています。  
  
  次の XML で必要な構成の例に示します、**リゾルバー**ノード。  
  
```xml  
<resolver name="ITINERARY-STATIC" type="Microsoft.Practices.ESB.Resolver.Unity.ResolveProvider, Microsoft.Practices.ESB.Resolver.Unity, Version=2.0.0.0, Culture=neutral, PublicKeyToken=c62dd63c784d6e22">  
     <resolverConfig>  
          <add name="unitySectionName" value="esb.resolver" />  
          <add name="unityContainerName" value="ITINERARY" />  
     </resolverConfig>  
</resolver>  
```  
  
 次の XML の下に必要な構成の例に示します、 **esb.resolver**ノード。  
  
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
  
 詳細のために必要な構成については、 **esb.resolvers**ノードを参照してください[Unity Application Block の送信元スキーマ](http://go.microsoft.com/fwlink/?LinkId=188288)([ http://go.microsoft.com/fwlink/?LinkId=188288 ](http://go.microsoft.com/fwlink/?LinkId=188288)) msdn です。  
  
 **Unity のカスタム競合回避モジュールを作成します。**  
  
 **カスタム Unity 競合回避モジュールを作成するには**  
  
1.  (省略可能)実装するクラスを使用して、アセンブリまたはアセンブリを作成、 **IFactProvider**インターフェイスし、が含まれています、 **RegisterFact**解像度が発生するために必要な情報を提供するメソッド。  
  
2.  (省略可能)実装するクラスを使用して、アセンブリまたはアセンブリを作成、 **IFactTranslator**インターフェイスし、が含まれています、 **TranslateFact**キー/値ペア内に指定されたファクトを変換するメソッド、競合回避モジュールのディクショナリ。  
  
3.  実装するクラスを使用してアセンブリを作成、 **IResolveContainer**と**IResolveProvider**インターフェイスを含む、**解決**を検証するメソッド、競合回避モジュール構成では、ファクト プロバイダーからすべてのファクトを収集し、任意の特殊な処理を実行しますはファクトのトランスレーターを使用してそれを変換およびのインスタンスとして変換されたファクトを返します、**ディクショナリ**クラス。  
  
4.  追加、Esb.config ファイルを使用して構成することによって、競合回避モジュールを登録、 **\<競合回避モジュール\>** としてルート モニカーを含む要素、**名前**属性と完全にアセンブリの修飾名として、**型**属性。  
  
5.  この競合回避モジュールの Esb.config ファイルを Unity に固有の構成を追加します。  
  
6.  (省略可能)ルート モニカーと、クエリ パラメーターを定義するスキーマを作成し、ESB で保存します。Schemas.Resolvers フォルダーです。 名前が既存の ESB 名前付け規則; に従う必要があります。これは、"_Resolution.xsd"を付加するルート モニカーの名前を使用することを意味します。  
  
7.  (省略可能)新しいスキーマからクラスを生成し、カスタム競合回避モジュールのアセンブリに保存します。 これにより、カスタムの競合回避モジュールに型指定されたパラメーターを公開します。  
  
8.  グローバル アセンブリ キャッシュ内のすべてのアセンブリを登録します。