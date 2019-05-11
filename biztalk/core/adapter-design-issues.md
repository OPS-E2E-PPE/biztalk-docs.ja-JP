---
title: アダプターのデザインの問題 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2e5568be-a046-40ff-a94a-eda086457564
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 15c6b99ff1416ace11c11d07dc9b137b5e33a231
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65361584"
---
# <a name="adapter-design-issues"></a>アダプターのデザインの問題点
アダプターの構成は、ユーザーがデザイン時構成の変更を行ったときに、シングル サインオン (SSO) データベースに格納されます。 実行時に、メッセージング エンジンは、アダプターの構成を取得し、アダプターに配信します。 4 種類の構成情報は、アダプターに配信されます。  
  
-   受信ハンドラーの構成  
  
-   受信場所 (エンドポイント) の構成  
  
-   送信ハンドラーの構成  
  
-   送信場所 (エンドポイント) の構成  
  
## <a name="receive-and-send-handler-configuration"></a>受信し、送信ハンドラーの構成  
 アダプターのハンドラー構成は省略可能な実装でアダプターに配信**IPersistPropertyBag**.**ロード**インターフェイス。 ハンドラーの構成は、BizTalk サービスが開始した後、アダプター ハンドラーの構成が変更された場合、アダプターは更新されませんので、1 回だけ配信されます。 一般的なモデルは、アダプター ハンドラーの構成を既定の構成として扱うにはエンドポイント構成は、エンドポイントごとにハンドラー構成をオーバーライドします。  
  
 次のコード フラグメントでは、構成の解析を示します。 渡されたプロパティは、アダプターの構成、**ロード**文字列プロパティで呼び出す**AdapterConfig**します。 このプロパティの値には、アダプターの構成を表す XML ドキュメントが含まれています。 アダプターは、ドキュメント オブジェクト モデル (DOM) または XML リーダーにこの構成を読み込むし、XPath を使用して、個々 のプロパティを取得する必要があります。  
  
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
 受信場所の実装でアダプターに構成情報が配信される**IBTTransportConfig**します。 このインターフェイスには、3 つのメソッドが含まれています。 **AddReceiveEndpoint**、 **UpdateEndpointConfig**、および**RemoveReceiveEndpoint**します。 メッセージング エンジンでは、そのメッセージを受信するでリッスンする必要のあるエンドポイントのアダプターに通知します。 個々 のエンドポイント構成が変更されたときに、アダプターはそのエンドポイントの変更の通知します。 これは、ハンドラーの構成が変更されたときに、アダプターは通知されないという事実とは対照的です。 同様に、アダプターは BizTalk Server を追加またはアクティブまたは非アクティブになる windows のサービスとしてのエンドポイントを削除するために、windows サービスを処理する必要はありません。  
  
### <a name="addreceiveendpoint"></a>AddReceiveEndpoint  
 アダプターが、エンジンの呼び出しのエンドポイントでリッスンを開始する必要がある場合**IBTTransportConfig.AddReceiveEndpoint**受信場所の URI をそのエンドポイントのアダプターの構成を含むプロパティ バッグを渡すとそのエンドポイントの BizTalk Server に固有の構成を含む 2 つ目のプロパティ バッグ。 アダプターは、BizTalk Server のシステム プロパティとしてメッセージ コンテキストに URI を書き込む必要があります**InboundTransportLocation**します。  
  
 アダプターのプロパティ バッグからの受信場所のプロパティの読み取りは、ハンドラーの構成を上記の説明を読む場合と同じです。 アダプターに渡された BizTalk Server 構成には、1 つのプロパティが含まれています。 **TwoWayReceivePort**、ポートが一方向または双方向であるかどうかを示します。 次のコード フラグメントでは、受信ポートが BizTalk Server のプロパティ バッグから一方向または双方向がある場合に評価する方法を示します。  
  
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
 アクティブな構成が表示されたら、場所が変更された場合、エンジンは、 **UpdateEndpointConfig**に異なる構成を使用する必要があることをアダプターに通知する API。 すべての構成は、BizTalk Server に固有の構成を含め、アダプターに配信されます。  
  
### <a name="removereceiveendpoint"></a>RemoveReceiveEndpoint  
 受信場所がアクティブでなくなったときに、アダプターがで通知されます**RemoveReceiveEndpoint**します。 アダプターから返された後**RemoveReceiveEndpoint**その URI を使用してエンジンにメッセージを送信することは許可されなくします。  
  
## <a name="send-port-configuration"></a>送信ポートの構成  
 メッセージング エンジンは、アダプターにメッセージを配信する前に、アダプターの名前空間内のメッセージ コンテキストに送信ポートの構成を書き込みます。 読み取って、メッセージの送信の制御を使用して、その後の構成を検証するアダプターの役目です。 送信アダプターは、バッチ処理をサポートするメッセージを送信、宛ての異なる送信ポートは同じバッチでアダプターが「混在」バッチ処理する必要があるため。  
  
 次のコード フラグメントを読み取る方法を示しています、 **OutboundTransportLocation**は送信ポートの URI。 アダプターの構成を含む XML blob の読み取りし、個々 のプロパティを読み取る方法も示します。  
  
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
  
 **実装のヒン ト:** 一般にアダプターを使用する必要があります、 **OutboundTransportLocation**メッセージ コンテキスト プロパティにメッセージを送信するアドレスを確認します。 アダプターは、この手順を実行して静的へのハンドルの送信と動的送信一貫しています。 これには、運用環境のバインド ファイル内のアドレスの変更も簡単になります。  
  
## <a name="xsd"></a>[XSD]  
 SDK ファイル アダプターのサンプルに含まれる 4 つの XSD ファイル アダプターの構成を主にハンドル。ReceiveHandler.xsd、ReceiveLocation.xsd、TransmitLocation.xsd、および TransmitHandler.xsd です。  
  
 次のトピックでは、これらの各ファイルについて説明し、変更する方法について説明します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [アダプターの構成情報の検証](../core/validating-the-adapter-configuration.md)  
  
-   [アダプターの登録](../core/registering-an-adapter.md)  
  
-   [アダプター フレームワーク構成スキーマの拡張機能](../core/adapter-framework-configuration-schema-extensions.md)  
  
-   [サポートされているアダプターの XSD 要素の型](../core/supported-adapter-xsd-element-types.md)  
  
-   [アダプターの XSD Element-Attribute コンストラクター](../core/adapter-xsd-element-attribute-constructs.md)  
  
-   [アダプターの XSD Data Type-Facet コンストラクター](../core/adapter-xsd-data-type-facet-constructs.md)  
  
-   [アダプターの詳細構成コンポーネント](../core/advanced-configuration-components-for-adapters.md)