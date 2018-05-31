---
title: カスタム競合回避モジュールを作成 |Microsoft ドキュメント
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
ms.openlocfilehash: 57fb0073437c32c8a8f064a4c77f267ee6806858
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25975904"
---
# <a name="creating-a-custom-resolver"></a>カスタム競合回避モジュールを作成します。
競合回避モジュールとアダプターのプロバイダー フレームワーク実装[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]ディスパッチャーをという名前のパイプライン コンポーネントと ItineraryReceive および ItinerarySend という名前のパイプラインを使用します。  
  
 ディスパッチャー パイプライン コンポーネントには 4 つのプロパティ:**検証、Enabled、エンドポイント、** と**MapName**です。 **エンドポイント**プロパティは、次のように値を持つ接続文字列の競合回避モジュールを含めることができます、 **UDDI:\\ \\**  (ルートを使用する解像度の種類を表しますモニカー) です。  
  
```  
UDDI:\\serverUrl=http://localhost/uddi;serviceName=OrderPurchaseToOrderPost;serviceProvider=Microsoft.Practices.ESB  
```  
  
 サポートされているその他のモニカーを含める**XPATH:\\\\、静的:\\\\、** と**BRE:\\\\**です。 各モニカー型を実装する特定のクラスを使用して、 **IResolveProvider**インターフェイスです。 その他のモニカーの種類のカスタム独自競合回避モジュールを作成し、動的解決のシステムで使用するためを登録できます。  
  
 モニカーは、競合回避モジュールの接続文字列に相当します。 個別のスキーマは、パラメーターとそのルート モニカーを定義します。 競合回避モジュールは、競合回避モジュールを接続文字列、検証、および結果を使用してクエリを実行し、設定、**ディクショナリ**ルーティング、変換、itinerary 選択またはに固有の他の何らかの目的のために使用できるオブジェクト、サービス。  
  
## <a name="resolver-configuration"></a>競合回避モジュールの構成  
 Esb.config 構成ファイルでは、すべての競合回避モジュールを登録する必要があります。 次の XML 構成ファイルの内容の例に示します。  
  
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
  
 **ResolverConfig**競合回避モジュールの各ノードの下のセクションでは、追加のプロパティの競合回避モジュールは、特定の環境で動作する必要がありますを構成することができます。 競合回避モジュールが構成へのアクセスは、型のパラメーターは、コンス トラクターを公開する必要があります**Microsoft.Practices.ESB.Configuration.Resolver**です。 実装では、競合回避モジュール、構成プロパティ、アクセスできるを使用して、 **ReadResolverConfigByKey**のメソッド、 **ResolverConfigHelper**クラスですこれを行うには、パラメーターに渡す。最初に、コンス トラクターに渡され、対象の値名受け取るします。 名前と値のペアが指定されていない場合、 **resolverConfig**ノード、既定のパラメーターなしコンス トラクターは、競合回避モジュールをインスタンス化に使用されます。  
  
 2 つ Universal Description, Discovery, and Integration (UDDI) 3 の競合回避モジュールは、構成で定義されている。 3 の UDDI および UDDI 3 SOASOFTWARE です。 同一の基になるアセンブリを使用してこれらの競合回避モジュールの両方が、異なる UDDI 3.0 に準拠したレジストリの異なる (Uniform Resource Identifier) の形式とセキュリティ要件をサポートするためのさまざまな構成を提供します。 既にサポートされているもの以外の UDDI 3.0 に準拠したレジストリの他のモニカーを構成する必要がある場合は、次の構成プロパティを使用できます。  
  
-   **cacheTimeoutValue**  
  
-   **cacheName**  
  
-   **publisherKey**  
  
-   **useUddiAuth**  
  
-   **baseUri**  
  
-   **inquireUriSuffix**  
  
-   **securityUriSuffix**  
  
-   **securityMode**です。 有効な値は、列挙体を参照してください。 [System.ServiceModel.BasicHttpSecurityMode](http://go.microsoft.com/fwlink/?LinkID=188284&clcid=0x409) ([http://go.microsoft.com/fwlink/?LinkID=188284&clcid=0x409](http://go.microsoft.com/fwlink/?LinkID=188284&clcid=0x409))。 既定値は**TransportCredentialOnly**です。  
  
-   **credentialType**です。 有効な値は、列挙体を参照してください。 [System.ServiceModel.HttpClientCredentialType](http://go.microsoft.com/fwlink/?LinkId=188285) ([http://go.microsoft.com/fwlink/?LinkId=188285](http://go.microsoft.com/fwlink/?LinkId=188285))。 既定値は**Windows**です。  
  
-   **ユーザー名**  
  
-   **パスワード**  
  
 Unity アプリケーション ブロックの依存関係の挿入機能に依存するリゾルバーを作成する場合は、追加の構成が必要です。 詳細については、次を参照してください。 [Unity コンテナーとカスタム競合回避モジュールを作成する](../esb-toolkit/creating-a-custom-resolver-with-a-unity-container.md)です。  
  
## <a name="the-iresolveprovider-interface"></a>IResolveProvider インターフェイス  
 すべての競合回避モジュールを実装する必要があります、 **IResolveProvider**インターフェイスです。 **IResolveProvider** Microsoft.Practices.ESB.Resolver プロジェクト内にあるインターフェイスの次の 3 つのオーバー ロードから成る、**解決**のインスタンスを返すメソッド、 **ディクショナリ**クラスは、具体的な競合回避モジュールのクラスのインスタンスによって提供される解像度のファクトが含まれています。 次のコード例は、これらのメソッド オーバー ロードのシグネチャを示しています。  
  
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
  
 **解決**Microsoft.Practices.ESB.Resolver プロジェクト内にある構造もに格納されている名前/値ペアを定義、**ディクショナリ**インスタンス。 **解決**構造がいくつかのプロパティを公開する以外の場合は次の表に、最も関連性を一覧表示します。 **CreateResolverDictionary**のメソッド、 **ResolutionHelper**を空の文字列値を使用して、最も使用されているキーを含むリゾルバー ディクショナリを生成するクラスを使用できます。 **ディクショナリ**インスタンスの具象実装を通じてカスタム競合回避モジュールの名前/値ペアの追加をサポートしている、**リゾルバー**クラスです。  
  
|プロパティ|データ型|データ型|データ型|  
|--------------|---------------|---------------|---------------|  
|**TransformType**|文字列|**ActionField**|文字列|  
|**Success**|ブール値|**EpmRRCorrelationTokenField**|文字列|  
|**TransportNamespace**|文字列|**InboundTransportLocationField**|文字列|  
|**TransportType**|文字列|**InterchangeIDField**|文字列|  
|**TransportLocation**|文字列|**ReceiveLocationNameField**|文字列|  
|**操作**|文字列|**ReceivePortNameField**|文字列|  
|**MessageExchangePattern**|文字列|**InboundTransportTypeField**|文字列|  
|**EndpointConfig**|文字列|**IsRequestResponseField**|文字列|  
|**TargetNamespace**|文字列|**DocumentSpecStrongNameField**|文字列|  
|**FixJaxRPC**|ブール値|**DocumentSpecNameField**|文字列|  
|**WindowUserField**|文字列|**[MessageType]**|文字列|  
|**CacheTimeout**|文字列|**OutboundTransportCLSID**|文字列|  
|**MethodNameField**|文字列|||  
  
## <a name="creating-a-custom-resolver"></a>カスタム競合回避モジュールを作成します。  
 実行時に、パイプラインが競合回避モジュールの接続文字列を取得し、競合回避モジュールのマネージャーを呼び出し (のインスタンス、 **ResolverMgr**クラス)。 競合回避モジュール マネージャーは、解析、設定、および競合回避モジュールの接続文字列を検証します。 これは、次の手順で。  
  
-   決定するため、接続文字列を解析して**リゾルバー**読み込まれる型です。  
  
-   この種類 (キーは、ルート モニカー、UDDI など)、構成ファイルで定義されているモニカーに一致します。  
  
-   これは、このモニカーの競合回避モジュールのアセンブリ名を読み取ります。  
  
-   指定したアセンブリを読み込みます。  
  
 動的解決メカニズムの実装が読み込まれているすべてのキャッシュ、 **IResolveProvider**構成情報、およびアセンブリの読み込み時に、いくつかの受信メッセージを使用して、同じの繰り返される読み取りを回避するインターフェイス競合回避モジュール。  
  
 競合回避モジュール マネージャーが最後に、実行、**解決**、具象型のメソッド**IResolveProvider**実装を返しますが、設定された**ディクショナリ**インスタンス。  
  
 **カスタム競合回避モジュールを作成するには**  
  
1.  実装するクラスを持つアセンブリを作成、 **IResolveProvider**インターフェイスし、が含まれています、**解決**のインスタンスとの競合回避モジュールのファクトを返すメソッド、**ディクショナリ**クラスです。  
  
2.  Esb.config ファイルを使用して構成を追加して、競合回避モジュールを登録、 **\<リゾルバー\>** としてルート モニカーを格納する要素、**名前**属性と完全にアセンブリの修飾名として、**型**属性。  
  
3.  (省略可能)ルート モニカーとクエリ パラメーターを定義するスキーマを作成し、ESB で保存します。Schemas.Resolvers フォルダーです。 名前が既存の ESB 名前付け規則; に従う必要があります。つまり、"_Resolution.xsd"が付いたルート モニカーの名前を使用する必要があります。  
  
4.  (省略可能)新しいスキーマからクラスを生成し、カスタム競合回避モジュールのアセンブリに保存します。 これは、カスタム競合回避モジュールに型指定されたパラメーターを公開します。  
  
5.  グローバル アセンブリ キャッシュに新しいアセンブリを登録します。