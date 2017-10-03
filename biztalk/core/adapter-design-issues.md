---
title: "アダプターのデザインに関する問題 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2e5568be-a046-40ff-a94a-eda086457564
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 79c6228db8342f3d1ad2628d4e4caf418efd9b29
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="adapter-design-issues"></a>アダプターのデザインの問題点
アダプターの構成は、ユーザーがデザイン時に構成を変更すると、シングル サインオン (SSO) データベースに格納されます。 実行時に、メッセージング エンジンはアダプターの構成を取得し、その構成をアダプターに送信します。 アダプターには、次の 4 種類の構成情報が送信されます。  
  
-   受信ハンドラーの構成  
  
-   受信場所 (エンドポイント) の構成  
  
-   送信ハンドラーの構成  
  
-   送信場所 (エンドポイント) の構成  
  
## <a name="receive-and-send-handler-configuration"></a>受信し、送信ハンドラーの構成  
 アダプターのハンドラー構成は省略可能なの実装でアダプターに送信**IPersistPropertyBag**.**ロード**インターフェイスです。 ハンドラー構成は一度しか送信されないため、アダプダのハンドラー構成が BizTalk サービスの開始後に変更された場合、アダプターは更新されません。 一般的なモデルでは、アダプターはハンドラー構成を既定の構成として処理します。エンドポイント構成は、エンドポイントごとにハンドラー構成をオーバーライドします。  
  
 次のコードは、構成の解析例を示します。 渡されたプロパティでは、アダプターの構成、**ロード**文字列プロパティで呼び出して**AdapterConfig**です。 このプロパティ値には、アダプターの構成を表す XML ドキュメントが含まれています。 アダプターはこの構成をドキュメント オブジェクト モデル (DOM) または XML リーダーに読み込み、XPath を使用して個々のプロパティを取得する必要があります。  
  
```  
public class MyAdapter : IBTTransport,   
 IBTTransportConfig,   
 IBTTransportControl,  
 IPersistPropertyBag,   
 IBaseComponent  
{  
...  
// Handler configuration properties...  
private int defaultBatchSize = 0;  
private string defaultHeader;  
  
// IPersistPropertyBag.Load() implementation...  
public void Load(IPropertyBag pb, int pErrorLog)  
{  
// The adapter configuration is in the property  
 // “AdapterConfig” in the form of an Xml blob...  
object obj = null;  
pb.Read("AdapterConfig", out obj, 0);  
  
// Create a DOM and load the Xml blob...  
XmlDocument dom = new XmlDocument();  
string adapterConfig = (string)obj;  
dom.LoadXml(adapterConfig);  
  
// XPath the individual properties...  
XmlNode node =   
 document.SelectSingleNode(“/Config/batchSize”);  
defaultBatchSize = int.Parse(node.InnerText);  
  
node = document.SelectSingleNode(“/Config/header”);  
defaultHeader = node.InnerText;  
}  
}  
```  
  
## <a name="receive-location-configuration"></a>受信場所の構成  
 受信場所の構成情報がの実装でアダプターに配信される**IBTTransportConfig**です。 このインターフェイスには、3 つのメソッドが含まれています。 **AddReceiveEndpoint**、 **UpdateEndpointConfig**、および**RemoveReceiveEndpoint**です。 メッセージング エンジンは、メッセージを受信するために受信待ちする必要があるエンドポイントをアダプターに通知します。 個々のエンドポイントの構成が変更されると、アダプターはそのエンドポイントの変更について通知を受けます。 これは、ハンドラーの構成が変更されてもアダプターは通知を受けないのとは対照的です。 同様に、BizTalk Server はサービス ウィンドウがアクティブまたは非アクティブになるとエンドポイントを追加、削除するため、アダプターはサービス ウィンドウを処理する必要はありません。  
  
### <a name="addreceiveendpoint"></a>AddReceiveEndpoint  
 アダプターが、エンドポイントでは、エンジンの呼び出しで待機を開始する必要がある場合**IBTTransportConfig.AddReceiveEndpoint**受信場所の URI の場合、そのエンドポイントのアダプターの構成を含むプロパティ バッグに渡すとそのエンドポイントの BizTalk Server 固有の構成を含む 2 つ目のプロパティ バッグ。 アダプターは、BizTalk Server システムのプロパティとしてメッセージ コンテキストに URI を書き込む必要があります**InboundTransportLocation**です。  
  
 アダプターのプロパティ バッグから受信場所のプロパティを読み取るのは、上記で説明したハンドラー構成を読み取るのと同じことです。 アダプターに渡された BizTalk Server の構成には、1 つのプロパティが含まれています。 **TwoWayReceivePort**、ポートが一方向または双方向かどうかを示します。 次のコードは、受信ポートが一方向と双方向のどちらであるかを BizTalk Server のプロパティ バッグから評価する方法を示しています。  
  
```  
public void AddReceiveEndpoint(  
 string  url,   
 IPropertyBag adapterConfig,   
 IPropertyBag bizTalkConfig )  
{  
...  
  
// The property "TwoWayReceivePort" in the BizTalk Config  
// property bag indicates whether the port is one or two  
 // way...  
  
 // Add receive location to config cache (not shown here)  
  
object obj = null;  
bizTalkConfig.Read("TwoWayReceivePort", out obj, 0);  
  
if ( null != obj )  
this.twoWay = (bool)obj;  
}  
```  
  
### <a name="updateendpointconfig"></a>UpdateEndpointConfig  
 場所が変更される、エンジンを使用してアクティブな構成が表示されたら、 **UpdateEndpointConfig** API に別の構成を使用する必要があることをアダプターに通知します。 BizTalk Server 固有の構成を含め、すべての構成がアダプターに送信されます。  
  
### <a name="removereceiveendpoint"></a>RemoveReceiveEndpoint  
 アダプターを介して通知受信場所がアクティブでなくなったときに**RemoveReceiveEndpoint**です。 アダプターから返された後**RemoveReceiveEndpoint**その URI を使用してエンジンにメッセージを送信するには使用できなくします。  
  
## <a name="send-port-configuration"></a>送信ポートの構成  
 メッセージング エンジンは送信ポートの構成をアダプターのメッセージ内のメッセージ コンテキストに書き込んでから、メッセージをアダプターに送信します。 アダプターは、構成の読み取りや検証を実行した後に、その構成を使用してメッセージの送信を制御します。 バッチ化された送信をサポートする送信アダプターの場合は、別の送信ポートを宛先とするメッセージが同じバッチ内に存在する可能性があるため、アダプターはこれらの "混在" バッチを処理する必要があります。  
  
 次のコード フラグメントを読み取る方法を示しています、 **OutboundTransportLocation**送信ポートの URI はします。 また、アダプターの構成を含む XML BLOB を読み取ってから、個々のプロパティを読み取る方法も示します。  
  
```  
...  
 private static readonly PropertyBase UriProperty =   
 new BTS.OutboundTransportLocation();  
  
 private string propertyNamespace =   
  "http://schemas.mySchemas.com/MyAdapter/myadapter-properties";  
private string uri;  
private string headers;  
private int timeOut = 1000;  
  
private void ReadSendPortConfig(IBaseMessage msg)  
{  
// Read the OutboundTransportLocation,   
 // i.e. the send port uri....  
uri = (string)msg.Context.Read(  
 UriProperty.Name.Name, UriProperty.Name.Namespace);  
  
// Read the adapters configuration Xml blob from   
 // the message...  
XmlDocument locationConfigDom = null;  
object obj = msg.Context.Read(  
 "AdapterConfig", this.propertyNamespace);  
  
// If this is a dynamic send there will not be   
 // any configuration...  
if ( null != obj )  
{  
locationConfigDom = new XmlDocument();  
locationConfigDom.LoadXml((string)obj);  
  
this.headers = Extract(  
 locationConfigDom, "/Config/headers", true);  
  
 this.timeOut = ExtractInt32(  
 locationConfigDom, "/Config/timeOut", true);  
}  
}  
  
 // Helper method to XPath string properties...  
private static string Extract(  
 XmlDocument document, string path, bool required)  
{  
XmlNode node = document.SelectSingleNode(path);  
if (!required && null == node)  
return String.Empty;  
if (null == node)  
throw new ApplicationException(string.Format(  
 "No property was found at {0}", path));  
return node.InnerText;  
}  
  
  // Helper method to XPath int32 properties...  
private static int ExtractInt32(  
 XmlDocument document, string path, bool required)  
{  
string s = Extract(document, path, required);  
return int.Parse(s);  
}   
```  
  
 **実装のヒン ト:**アダプターは一般に使用する必要があります、 **OutboundTransportLocation**メッセージ コンテキスト プロパティをメッセージを送信するアドレスを決定します。 この方法を実行すると、静的送信と動的送信に対する送信を一貫して処理できます。 また、この方法を使用すると、実稼動のバインド ファイルのアドレスを簡単に変更できます。  
  
## <a name="xsd"></a>[XSD]  
 SDK ファイル アダプターのサンプルに含まれる 4 つの XSD ファイル ハンドル アダプター構成では、主に: ReceiveHandler.xsd、ReceiveLocation.xsd、TransmitLocation.xsd、および TransmitHandler.xsd です。  
  
 次のトピックでは、これらの各ファイルと、それらのファイルの変更方法について説明します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [アダプター構成の検証](../core/validating-the-adapter-configuration.md)  
  
-   [アダプターの登録](../core/registering-an-adapter.md)  
  
-   [アダプター フレームワーク構成スキーマの拡張機能](../core/adapter-framework-configuration-schema-extensions.md)  
  
-   [サポートされているアダプターの XSD 要素の型](../core/supported-adapter-xsd-element-types.md)  
  
-   [アダプターの XSD Element-attribute コンス トラクター](../core/adapter-xsd-element-attribute-constructs.md)  
  
-   [アダプターの XSD Data Type-facet コンス トラクター](../core/adapter-xsd-data-type-facet-constructs.md)  
  
-   [アダプターの高度な構成コンポーネント](../core/advanced-configuration-components-for-adapters.md)