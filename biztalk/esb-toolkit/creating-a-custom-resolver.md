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
# <a name="creating-a-custom-resolver"></a>カスタム競合回避モジュールを作成します。
リゾルバーとアダプターのプロバイダー フレームワーク実装[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]ディスパッチャーをという名前のパイプライン コンポーネントと ItineraryReceive および ItinerarySend という名前のパイプラインを使用します。  
  
 ディスパッチャー パイプライン コンポーネントには 4 つのプロパティ:**検証、Enabled、エンドポイント、** と**MapName**します。 **エンドポイント**プロパティは、次のように値を持つ接続文字列の競合回避モジュールを含めることができます、 **UDDI:\\ \\**  (ルートを使用する解像度の種類を表しますモニカー)。  
  
```  
UDDI:\\serverUrl=http://localhost/uddi;serviceName=OrderPurchaseToOrderPost;serviceProvider=Microsoft.Practices.ESB  
```  
  
 サポートされているその他のモニカーを含める**XPATH:\\\\の静的な:\\\\、** と**BRE:\\\\**します。 各モニカーの型を実装する特定のクラスを使用して、 **IResolveProvider**インターフェイス。 モニカーの他の種類の独自のカスタム リゾルバーを作成し、動的解決のシステムで使用するためを登録できます。  
  
 モニカーは、競合回避モジュールの接続文字列に相当します。 個別のスキーマは、パラメーターとそのルート モニカーを定義します。 競合回避モジュールは、競合回避モジュールの接続文字列を検証し、結果を使用してクエリを実行し、設定、**ディクショナリ**ルーティング、変換、スケジュールの選択、またはに固有の他の何らかの目的のために使用できるオブジェクト、サービス。  
  
## <a name="resolver-configuration"></a>競合回避モジュールの構成  
 Esb.config 構成ファイルですべての競合回避モジュールを登録する必要があります。 次の XML では、構成ファイルの内容の例を示します。  
  
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
  
 **ResolverConfig**競合回避モジュールの各ノードの下のセクションでは、特定の環境で動作する、競合回避モジュールが必要な追加のプロパティを構成することができます。 リゾルバー構成へのアクセスには、型のパラメーターを受け取るコンス トラクターを公開する必要があります**Microsoft.Practices.ESB.Configuration.Resolver**します。 競合回避モジュールの実装で構成しプロパティを使用して、 **ReadResolverConfigByKey**のメソッド、 **ResolverConfigHelper**クラスは、これを行うには、パラメーターに渡す最初に、コンス トラクターに渡され、問題の名前、値渡すします。 名前と値のペアが指定されていない場合、 **resolverConfig**ノードで、既定のパラメーターなしコンス トラクターは、競合回避モジュールをインスタンス化に使用されます。  
  
 2 つ Universal Description, Discovery, and Integration (UDDI) 3 競合回避モジュールは、構成で定義されている: 3 の UDDI および UDDI 3-SOASOFTWARE します。 同じ基になるアセンブリを使用して、これらの競合回避モジュールの両方が、別の UDDI 3.0 に準拠したレジストリの別の Uniform Resource Identifier (URI) 形式とセキュリティ要件をサポートするためのさまざまな構成を提供します。 既にサポートされているもの以外の UDDI 3.0 に準拠したレジストリの追加のモニカーを構成する必要がある場合は、次の構成プロパティを使用できます。  
  
- **cacheTimeoutValue**  
  
- **cacheName**  
  
- **publisherKey**  
  
- **useUddiAuth**  
  
- **baseUri**  
  
- **inquireUriSuffix**  
  
- **securityUriSuffix**  
  
- **securityMode**します。 有効な値は、列挙体を参照してください。 [System.ServiceModel.BasicHttpSecurityMode](http://go.microsoft.com/fwlink/?LinkID=188284&clcid=0x409) ([http://go.microsoft.com/fwlink/?LinkID=188284&clcid=0x409](http://go.microsoft.com/fwlink/?LinkID=188284&clcid=0x409))。 既定値は**TransportCredentialOnly**します。  
  
- **credentialType**します。 有効な値は、列挙体を参照してください。 [System.ServiceModel.HttpClientCredentialType](http://go.microsoft.com/fwlink/?LinkId=188285) ([http://go.microsoft.com/fwlink/?LinkId=188285](http://go.microsoft.com/fwlink/?LinkId=188285))。 既定値は**Windows**します。  
  
- **username**  
  
- **password**  
  
  Unity Application Block の依存関係の注入機能に依存している競合回避モジュールを作成する場合は、追加の構成が必要です。 詳細については、次を参照してください。 [Unity コンテナーでのカスタム競合回避モジュールを作成する](../esb-toolkit/creating-a-custom-resolver-with-a-unity-container.md)します。  
  
## <a name="the-iresolveprovider-interface"></a>IResolveProvider インターフェイス  
 すべての競合回避モジュールを実装する必要があります、 **IResolveProvider**インターフェイス。 **IResolveProvider** Microsoft.Practices.ESB.Resolver のプロジェクトにあるインターフェイスの 3 つのオーバー ロードから成る、**解決**のインスタンスを返すメソッド、 **ディクショナリ**解像度のファクト具体的な競合回避モジュールのクラスのインスタンスによって提供されるを保持しているクラス。 次のコード例では、これらのメソッド オーバー ロードのシグネチャを示します。  
  
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
  
 **解決**Microsoft.Practices.ESB.Resolver のプロジェクト構造もに格納されている名前/値ペアを定義、**ディクショナリ**インスタンス。 **解決**構造がいくつかのプロパティを公開します。 最も関連する次の表を一覧表示します。 **CreateResolverDictionary**のメソッド、 **ResolutionHelper**空の文字列値を持つ、最も使用されているキーを格納している競合回避モジュール ディクショナリを生成するクラスを使用できます。 **ディクショナリ**インスタンスの具象実装を通じてカスタム競合回避モジュールの名前/値ペアの追加をサポートする、**リゾルバー**クラス。  
  
|プロパティ|データ型|データ型|データ型|  
|--------------|---------------|---------------|---------------|  
|**TransformType**|String|**ActionField**|String|  
|**成功**|ブール値|**EpmRRCorrelationTokenField**|String|  
|**TransportNamespace**|String|**InboundTransportLocationField**|String|  
|**TransportType**|String|**InterchangeIDField**|String|  
|**TransportLocation**|String|**ReceiveLocationNameField**|String|  
|**操作**|String|**ReceivePortNameField**|String|  
|**MessageExchangePattern**|String|**InboundTransportTypeField**|String|  
|**EndpointConfig**|String|**IsRequestResponseField**|String|  
|**TargetNamespace**|String|**DocumentSpecStrongNameField**|String|  
|**FixJaxRPC**|ブール値|**DocumentSpecNameField**|String|  
|**WindowUserField**|String|**[MessageType]**|String|  
|**CacheTimeout**|String|**OutboundTransportCLSID**|String|  
|**MethodNameField**|String|||  
  
## <a name="creating-a-custom-resolver"></a>カスタム競合回避モジュールを作成します。  
 、実行時にパイプラインが競合回避モジュールの接続文字列を取得し、マネージャー、競合回避モジュールを呼び出し (のインスタンス、 **ResolverMgr**クラス)。 競合回避モジュール マネージャーは、解析し、設定、および、競合回避モジュールの接続文字列を検証します。 これは、次の手順で。  
  
- 判断するために、接続文字列を解析**リゾルバー**を読み込んでおく型。  
  
- (キーは、ルート モニカー、UDDI など)、構成ファイルで定義されているモニカーには、この型と一致します。  
  
- このモニカーの競合回避モジュールのアセンブリ名を読み取ります。  
  
- 指定したアセンブリが読み込まれます。  
  
  動的解決メカニズムの実装が読み込まれたすべてのキャッシュ、 **IResolveProvider**構成情報とアセンブリの読み込み時に、いくつかの受信メッセージを使用して、同じの繰り返しの読み取りを回避するためにインターフェイス競合回避モジュール。  
  
  競合回避モジュールのマネージャーが最後に、実行、**解決**の具象メソッド**IResolveProvider**実装を返しますが、設定された**ディクショナリ**インスタンス。  
  
  **カスタム競合回避モジュールを作成するには**  
  
1.  実装するクラスを使用してアセンブリを作成、 **IResolveProvider**インターフェイスし、が含まれています、**解決**のインスタンスとの競合回避モジュールのファクトを返すメソッド、**ディクショナリ**クラス。  
  
2.  追加、Esb.config ファイルを使用して構成することによって、競合回避モジュールを登録、 **\<競合回避モジュール\>** としてルート モニカーを含む要素、**名前**属性と完全にアセンブリの修飾名として、**型**属性。  
  
3.  (省略可能)ルート モニカーと、クエリ パラメーターを定義するスキーマを作成し、ESB で保存します。Schemas.Resolvers フォルダーです。 名前が既存の ESB 名前付け規則; に従う必要があります。これは、"_Resolution.xsd"を付加するルート モニカーの名前を使用することを意味します。  
  
4.  (省略可能)新しいスキーマからクラスを生成し、カスタム競合回避モジュールのアセンブリに保存します。 これは、カスタムの競合回避モジュールに型指定されたパラメーターを公開します。  
  
5.  グローバル アセンブリ キャッシュに新しいアセンブリを登録します。