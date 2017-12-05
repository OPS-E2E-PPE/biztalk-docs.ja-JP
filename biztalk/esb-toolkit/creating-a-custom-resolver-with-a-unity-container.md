---
title: "Unity コンテナーとカスタム競合回避モジュールを作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d6f95f5e-64dd-4cc6-802f-0c5fd6a01c91
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ef4a96542bcf2a7deae4911c6ee81fa846d0766f
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="creating-a-custom-resolver-with-a-unity-container"></a>Unity コンテナーとカスタム競合回避モジュールを作成します。
使用してカスタム競合回避モジュールを作成することができます、 [Unity Application Block](http://go.microsoft.com/fwlink/?LinkId=188286) (Unity) ([http://go.microsoft.com/fwlink/?LinkId=188286](http://go.microsoft.com/fwlink/?LinkId=188286)) 解決ロジックとメタデータのソースの実行時の依存関係挿入します。
  
 **ファクト プロバイダー**  
  
 ファクトのプロバイダーを実装するクラスのインスタンスである、 **IFactProvider**インターフェイスです。 このインターフェイスは、という名前のメソッドの 3 つの異なるオーバー ロードを公開**RegisterFact**です。 このメソッドは、メッセージで、競合回避モジュールの構成、および場合によっては、パイプライン コンテキストを受け取るし、オブジェクトを返します。 このオブジェクトが何らかの方法で、入力から抽出された情報、何らかの形式の計算がある可能性がありますか外部ソースから参照可能性があります。 ファクト プロバイダーによって返される各オブジェクトをファクトとして参照できますされ、通常、ファクト トランスレーターが後で使用できる解決コンテナーによってリストに追加されます。  
  
 Unity の競合回避モジュールは、0 個以上のファクト プロバイダーを追加したりできる 1 つの構成の変更では、いつでも削除でがあります。  
  
 次のコードは、ファクトのプロバイダーに含まれているロジックの例です。 このコードは、ESB の ItineraryStaticFactProvider.cs ファイルにも見つかりません。Resolver.Itinerary.Facts プロジェクトです。 行程静的競合回避モジュールに競合回避モジュールの接続文字列から名前と、日程のバージョンを収集するコンポーネントです。  
  
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
  
 **翻訳者のファクト**  
  
 ファクト翻訳者を実装するクラスのインスタンスである、 **IFactTranslator**インターフェイスです。 このインターフェイスはという単一のメソッドを公開**TranslateFact**です。 このメソッドはファクトとファクト トランスレータを使用して競合回避モジュールによって後で返される競合回避モジュールのディクショナリの一覧を格納しているオブジェクト配列で使用します。 ファクト トランスレーターは、有意義な方法でファクト プロバイダーによって提供されるファクトの処理との競合回避モジュールのディクショナリを作成します。  
  
 Unity の競合回避モジュールは、0 個以上のファクト翻訳を追加したりできる 1 つの構成の変更では、いつでも削除でがあります。  
  
 次のコードは、ファクト変換プログラムに含まれているロジックの例です。 このコードは、ESB の ItineraryStaticFactTranslator.cs ファイルにも見つかりません。Resolver.Itinerary.Facts プロジェクトです。 行程静的競合回避モジュールに名前や、必要に応じて、バージョンによって、日程の日程 XML を収集するためのデータベース クエリを実行するコンポーネントです。  
  
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
  
 実装するクラスが、解決コンテナーには、 **IResolveContainer**インターフェイスです。 通常も実装、 **IResolveProvider**インターフェイスです。 **IResolveContainer**インターフェイスという単一のメソッドを公開する**初期化**内を取得、 **IUnityContainer**です。 このメソッドに渡されたコンテナーで、すべての依存関係が含まれます (クラスのインスタンスは、 **IFactProvider**と**IFactTranslator**、および必要なその他のすべての種類) に必要なその処理を完了する競合回避モジュール。  
  
 次のコードの実装の例は、 **IResolveContainer**インターフェイスです。 このコードは、ESB の StaticItineraryResolveContainer.cs ファイルにも見つかりません。Resolver.Itinerary プロジェクトです。  
  
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
  
 実装では、解決のコンテナーで、**解決**メソッドを**IResolveProvider**すべてのファクトのプロバイダーと、Unity にファクト トランスレーターを反復処理する必要があるインターフェイスそれぞれの処理を実行するを許可するコンテナーです。  
  
 次のコードは、解決のコンテナーに含まれているロジックの例です。 このコードは、ESB の StaticItineraryResolveContainer.cs ファイルにも見つかりません。Resolver.Itinerary プロジェクトです。  
  
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
  
 **カスタム Unity 競合回避モジュールを構成します。**  
  
 カスタム Unity 競合回避モジュールを構成するには、同じ構成手順を適用としてカスタム競合回避モジュール; を作成するときにただし、いくつか追加の構成は、競合回避モジュールを構成するコンポーネントを正しく登録に含める必要があります。  
  
 最初に、競合回避モジュール宣言の下、Esb.config ファイル、 **resolverConfig**ノードは、次の 2 つのプロパティを追加する必要があります。  
  
-   **unitySectionName**です。 このプロパティには、Unity アプリケーション ブロック; の構成を含む構成ファイルで構成セクションの名前が含まれています。このプロパティの値は、既定では、 **esb.resolver**です。  
  
-   **unityContainerName**です。 このプロパティには、Unity に固有の構成、カスタム競合回避モジュールで定義されている Unity コンテナーの名前が含まれています。  
  
 次の XML に必要な構成の例は、**リゾルバー**ノード。  
  
```xml  
<resolver name="ITINERARY-STATIC" type="Microsoft.Practices.ESB.Resolver.Unity.ResolveProvider, Microsoft.Practices.ESB.Resolver.Unity, Version=2.0.0.0, Culture=neutral, PublicKeyToken=c62dd63c784d6e22">  
     <resolverConfig>  
          <add name="unitySectionName" value="esb.resolver" />  
          <add name="unityContainerName" value="ITINERARY" />  
     </resolverConfig>  
</resolver>  
```  
  
 次の XML は、必要な構成の例、 **esb.resolver**ノード。  
  
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
  
 詳細についてで必要な構成は、 **esb.resolvers**  ノードを参照してください[Unity アプリケーション ブロックのソース スキーマ](http://go.microsoft.com/fwlink/?LinkId=188288)([http://go.microsoft.com/fwlink/?LinkId = 188288](http://go.microsoft.com/fwlink/?LinkId=188288)) MSDN のです。  
  
 **カスタム Unity 競合回避モジュールを作成します。**  
  
 **カスタム Unity リゾルバーを作成するには**  
  
1.  (省略可能)アセンブリまたはアセンブリを実装するクラスを作成、 **IFactProvider**インターフェイスし、が含まれています、 **RegisterFact**発生する可能性への解決に必要な情報を提供するメソッド。  
  
2.  (省略可能)アセンブリまたはアセンブリを実装するクラスを作成、 **IFactTranslator**インターフェイスし、が含まれています、 **TranslateFact**キー/値ペア内に指定されたファクトを変換する方法、競合回避モジュールのディクショナリ。  
  
3.  実装するクラスを持つアセンブリを作成、 **IResolveContainer**と**IResolveProvider**とインターフェイスが含まれています、**解決**を検証する方法、競合回避モジュールの構成、ファクト プロバイダーからすべてのファクトを収集し、任意の特殊な処理を実行はファクト トランスレータを使用してそれを変換および翻訳済みのファクトのインスタンスを返します、**ディクショナリ**クラス。  
  
4.  Esb.config ファイルを使用して構成を追加して、競合回避モジュールを登録、 **\<リゾルバー\>** としてルート モニカーを格納する要素、**名前**属性と完全にアセンブリの修飾名として、**型**属性。  
  
5.  この競合回避モジュールの Esb.config ファイルを Unity に固有の構成を追加します。  
  
6.  (省略可能)ルート モニカーとクエリ パラメーターを定義するスキーマを作成し、ESB で保存します。Schemas.Resolvers フォルダーです。 名前が既存の ESB 名前付け規則; に従う必要があります。つまり、"_Resolution.xsd"が付いたルート モニカーの名前を使用する必要があります。  
  
7.  (省略可能)新しいスキーマからクラスを生成し、カスタム競合回避モジュールのアセンブリに保存します。 これにより、カスタム競合回避モジュールに型指定されたパラメーターが公開されます。  
  
8.  グローバル アセンブリ キャッシュ内のすべてのアセンブリを登録します。