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
# <a name="adapter-design-issues"></a><span data-ttu-id="9bd96-102">アダプターのデザインの問題点</span><span class="sxs-lookup"><span data-stu-id="9bd96-102">Adapter Design Issues</span></span>
<span data-ttu-id="9bd96-103">アダプターの構成は、ユーザーがデザイン時構成の変更を行ったときに、シングル サインオン (SSO) データベースに格納されます。</span><span class="sxs-lookup"><span data-stu-id="9bd96-103">Adapter configuration is stored in the Single Sign-On (SSO) database when the user makes configuration changes during design time.</span></span> <span data-ttu-id="9bd96-104">実行時に、メッセージング エンジンは、アダプターの構成を取得し、アダプターに配信します。</span><span class="sxs-lookup"><span data-stu-id="9bd96-104">At run time the Messaging Engine retrieves the adapter's configuration and delivers it to the adapter.</span></span> <span data-ttu-id="9bd96-105">4 種類の構成情報は、アダプターに配信されます。</span><span class="sxs-lookup"><span data-stu-id="9bd96-105">Four types of configuration information are delivered to adapters:</span></span>  
  
-   <span data-ttu-id="9bd96-106">受信ハンドラーの構成</span><span class="sxs-lookup"><span data-stu-id="9bd96-106">Receive handler configuration</span></span>  
  
-   <span data-ttu-id="9bd96-107">受信場所 (エンドポイント) の構成</span><span class="sxs-lookup"><span data-stu-id="9bd96-107">Receive location (endpoint) configuration</span></span>  
  
-   <span data-ttu-id="9bd96-108">送信ハンドラーの構成</span><span class="sxs-lookup"><span data-stu-id="9bd96-108">Send handler configuration</span></span>  
  
-   <span data-ttu-id="9bd96-109">送信場所 (エンドポイント) の構成</span><span class="sxs-lookup"><span data-stu-id="9bd96-109">Send location (endpoint) configuration</span></span>  
  
## <a name="receive-and-send-handler-configuration"></a><span data-ttu-id="9bd96-110">受信し、送信ハンドラーの構成</span><span class="sxs-lookup"><span data-stu-id="9bd96-110">Receive and Send Handler Configuration</span></span>  
 <span data-ttu-id="9bd96-111">アダプターのハンドラー構成は省略可能な実装でアダプターに配信**IPersistPropertyBag**.**ロード**インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="9bd96-111">An adapter's handler configuration is delivered to the adapter on its implementation of the optional **IPersistPropertyBag**.**Load** interface.</span></span> <span data-ttu-id="9bd96-112">ハンドラーの構成は、BizTalk サービスが開始した後、アダプター ハンドラーの構成が変更された場合、アダプターは更新されませんので、1 回だけ配信されます。</span><span class="sxs-lookup"><span data-stu-id="9bd96-112">The handler configuration is delivered only once, so if the adapter handler configuration is changed after the BizTalk service has started the adapter is not updated.</span></span> <span data-ttu-id="9bd96-113">一般的なモデルは、アダプター ハンドラーの構成を既定の構成として扱うにはエンドポイント構成は、エンドポイントごとにハンドラー構成をオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="9bd96-113">The common model is for the adapter to treat the handler configuration as the default configuration; endpoint configuration overrides the handler configuration on a per-endpoint basis.</span></span>  
  
 <span data-ttu-id="9bd96-114">次のコード フラグメントでは、構成の解析を示します。</span><span class="sxs-lookup"><span data-stu-id="9bd96-114">The following code fragment demonstrates parsing the configuration.</span></span> <span data-ttu-id="9bd96-115">渡されたプロパティは、アダプターの構成、**ロード**文字列プロパティで呼び出す**AdapterConfig**します。</span><span class="sxs-lookup"><span data-stu-id="9bd96-115">The adapter's configuration is in the property passed in to the **Load** call in the string property **AdapterConfig**.</span></span> <span data-ttu-id="9bd96-116">このプロパティの値には、アダプターの構成を表す XML ドキュメントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="9bd96-116">This property value contains an XML document representing the adapter's configuration.</span></span> <span data-ttu-id="9bd96-117">アダプターは、ドキュメント オブジェクト モデル (DOM) または XML リーダーにこの構成を読み込むし、XPath を使用して、個々 のプロパティを取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9bd96-117">The adapter needs to load this configuration into a document object model (DOM) or an XML reader and use XPath to retrieve the individual properties.</span></span>  
  
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
  
## <a name="receive-location-configuration"></a><span data-ttu-id="9bd96-118">受信場所の構成</span><span class="sxs-lookup"><span data-stu-id="9bd96-118">Receive Location Configuration</span></span>  
 <span data-ttu-id="9bd96-119">受信場所の実装でアダプターに構成情報が配信される**IBTTransportConfig**します。</span><span class="sxs-lookup"><span data-stu-id="9bd96-119">Receive location configuration information is delivered to an adapter on its implementation of **IBTTransportConfig**.</span></span> <span data-ttu-id="9bd96-120">このインターフェイスには、3 つのメソッドが含まれています。 **AddReceiveEndpoint**、 **UpdateEndpointConfig**、および**RemoveReceiveEndpoint**します。</span><span class="sxs-lookup"><span data-stu-id="9bd96-120">This interface contains the three methods **AddReceiveEndpoint**, **UpdateEndpointConfig**, and **RemoveReceiveEndpoint**.</span></span> <span data-ttu-id="9bd96-121">メッセージング エンジンでは、そのメッセージを受信するでリッスンする必要のあるエンドポイントのアダプターに通知します。</span><span class="sxs-lookup"><span data-stu-id="9bd96-121">The Messaging Engine notifies the adapter of which endpoints it needs to listen on to receive messages.</span></span> <span data-ttu-id="9bd96-122">個々 のエンドポイント構成が変更されたときに、アダプターはそのエンドポイントの変更の通知します。</span><span class="sxs-lookup"><span data-stu-id="9bd96-122">When the configuration for an individual endpoint is changed the adapter is notified of the change for that endpoint.</span></span> <span data-ttu-id="9bd96-123">これは、ハンドラーの構成が変更されたときに、アダプターは通知されないという事実とは対照的です。</span><span class="sxs-lookup"><span data-stu-id="9bd96-123">This is in contrast to the fact that when handler configuration changes the adapter is not notified.</span></span> <span data-ttu-id="9bd96-124">同様に、アダプターは BizTalk Server を追加またはアクティブまたは非アクティブになる windows のサービスとしてのエンドポイントを削除するために、windows サービスを処理する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="9bd96-124">Similarly, the adapter does not need to handle service windows because BizTalk Server adds or removes endpoints as service windows become active or inactive.</span></span>  
  
### <a name="addreceiveendpoint"></a><span data-ttu-id="9bd96-125">AddReceiveEndpoint</span><span class="sxs-lookup"><span data-stu-id="9bd96-125">AddReceiveEndpoint</span></span>  
 <span data-ttu-id="9bd96-126">アダプターが、エンジンの呼び出しのエンドポイントでリッスンを開始する必要がある場合**IBTTransportConfig.AddReceiveEndpoint**受信場所の URI をそのエンドポイントのアダプターの構成を含むプロパティ バッグを渡すとそのエンドポイントの BizTalk Server に固有の構成を含む 2 つ目のプロパティ バッグ。</span><span class="sxs-lookup"><span data-stu-id="9bd96-126">When an adapter needs to begin listening on an endpoint, the engine calls **IBTTransportConfig.AddReceiveEndpoint** passing in the receive location's URI, a property bag containing the adapter's configuration for that endpoint, and a second property bag containing BizTalk Server-specific configuration for that endpoint.</span></span> <span data-ttu-id="9bd96-127">アダプターは、BizTalk Server のシステム プロパティとしてメッセージ コンテキストに URI を書き込む必要があります**InboundTransportLocation**します。</span><span class="sxs-lookup"><span data-stu-id="9bd96-127">The adapter needs to write the URI to the message context as the BizTalk Server system property **InboundTransportLocation**.</span></span>  
  
 <span data-ttu-id="9bd96-128">アダプターのプロパティ バッグからの受信場所のプロパティの読み取りは、ハンドラーの構成を上記の説明を読む場合と同じです。</span><span class="sxs-lookup"><span data-stu-id="9bd96-128">Reading the receive location properties from the adapter's property bag is the same as reading the handler configuration as detailed above.</span></span> <span data-ttu-id="9bd96-129">アダプターに渡された BizTalk Server 構成には、1 つのプロパティが含まれています。 **TwoWayReceivePort**、ポートが一方向または双方向であるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="9bd96-129">The BizTalk Server configuration passed into the adapter contains a single property, **TwoWayReceivePort**, which indicates whether the port is one-way or two-way.</span></span> <span data-ttu-id="9bd96-130">次のコード フラグメントでは、受信ポートが BizTalk Server のプロパティ バッグから一方向または双方向がある場合に評価する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="9bd96-130">The following code fragment illustrates how to evaluate if the receive port is one-way or two-way from the BizTalk Server property bag:</span></span>  
  
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
  
### <a name="updateendpointconfig"></a><span data-ttu-id="9bd96-131">UpdateEndpointConfig</span><span class="sxs-lookup"><span data-stu-id="9bd96-131">UpdateEndpointConfig</span></span>  
 <span data-ttu-id="9bd96-132">アクティブな構成が表示されたら、場所が変更された場合、エンジンは、 **UpdateEndpointConfig**に異なる構成を使用する必要があることをアダプターに通知する API。</span><span class="sxs-lookup"><span data-stu-id="9bd96-132">When the configuration of an active receive location is changed, the engine uses the **UpdateEndpointConfig** API to notify the adapter that it needs to use a different configuration.</span></span> <span data-ttu-id="9bd96-133">すべての構成は、BizTalk Server に固有の構成を含め、アダプターに配信されます。</span><span class="sxs-lookup"><span data-stu-id="9bd96-133">All of the configuration is delivered to the adapter, including the BizTalk Server-specific configuration.</span></span>  
  
### <a name="removereceiveendpoint"></a><span data-ttu-id="9bd96-134">RemoveReceiveEndpoint</span><span class="sxs-lookup"><span data-stu-id="9bd96-134">RemoveReceiveEndpoint</span></span>  
 <span data-ttu-id="9bd96-135">受信場所がアクティブでなくなったときに、アダプターがで通知されます**RemoveReceiveEndpoint**します。</span><span class="sxs-lookup"><span data-stu-id="9bd96-135">When a receive location is no longer active, the adapter is notified through **RemoveReceiveEndpoint**.</span></span> <span data-ttu-id="9bd96-136">アダプターから返された後**RemoveReceiveEndpoint**その URI を使用してエンジンにメッセージを送信することは許可されなくします。</span><span class="sxs-lookup"><span data-stu-id="9bd96-136">After the adapter returns from **RemoveReceiveEndpoint** it is no longer allowed to use that URI to submit messages into the engine.</span></span>  
  
## <a name="send-port-configuration"></a><span data-ttu-id="9bd96-137">送信ポートの構成</span><span class="sxs-lookup"><span data-stu-id="9bd96-137">Send Port Configuration</span></span>  
 <span data-ttu-id="9bd96-138">メッセージング エンジンは、アダプターにメッセージを配信する前に、アダプターの名前空間内のメッセージ コンテキストに送信ポートの構成を書き込みます。</span><span class="sxs-lookup"><span data-stu-id="9bd96-138">The Messaging Engine writes the configuration for the send port to the message context in the adapter’s namespace before delivering the message to the adapter.</span></span> <span data-ttu-id="9bd96-139">読み取って、メッセージの送信の制御を使用して、その後の構成を検証するアダプターの役目です。</span><span class="sxs-lookup"><span data-stu-id="9bd96-139">It is the adapters’ responsibility to read and validate the configuration, which it subsequently uses to control the transmission of the message.</span></span> <span data-ttu-id="9bd96-140">送信アダプターは、バッチ処理をサポートするメッセージを送信、宛ての異なる送信ポートは同じバッチでアダプターが「混在」バッチ処理する必要があるため。</span><span class="sxs-lookup"><span data-stu-id="9bd96-140">For send adapters that support batched sends, messages destined for different send ports may be in the same batch, so the adapter needs to handle these "mixed" batches.</span></span>  
  
 <span data-ttu-id="9bd96-141">次のコード フラグメントを読み取る方法を示しています、 **OutboundTransportLocation**は送信ポートの URI。</span><span class="sxs-lookup"><span data-stu-id="9bd96-141">The following code fragment illustrates how to read the **OutboundTransportLocation** that is the URI for the send port.</span></span> <span data-ttu-id="9bd96-142">アダプターの構成を含む XML blob の読み取りし、個々 のプロパティを読み取る方法も示します。</span><span class="sxs-lookup"><span data-stu-id="9bd96-142">It also shows how to read the XML blob containing the adapter's configuration and then read the individual properties.</span></span>  
  
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
  
 <span data-ttu-id="9bd96-143">**実装のヒン ト:** 一般にアダプターを使用する必要があります、 **OutboundTransportLocation**メッセージ コンテキスト プロパティにメッセージを送信するアドレスを確認します。</span><span class="sxs-lookup"><span data-stu-id="9bd96-143">**Implementation Tip:** Adapters should in general use the **OutboundTransportLocation** message context property to determine the address to send the message to.</span></span> <span data-ttu-id="9bd96-144">アダプターは、この手順を実行して静的へのハンドルの送信と動的送信一貫しています。</span><span class="sxs-lookup"><span data-stu-id="9bd96-144">By doing this the adapter can handle transmissions to both static and dynamic sends consistently.</span></span> <span data-ttu-id="9bd96-145">これには、運用環境のバインド ファイル内のアドレスの変更も簡単になります。</span><span class="sxs-lookup"><span data-stu-id="9bd96-145">This also simplifies the modification of addresses in production binding files.</span></span>  
  
## <a name="xsd"></a><span data-ttu-id="9bd96-146">[XSD]</span><span class="sxs-lookup"><span data-stu-id="9bd96-146">XSD</span></span>  
 <span data-ttu-id="9bd96-147">SDK ファイル アダプターのサンプルに含まれる 4 つの XSD ファイル アダプターの構成を主にハンドル。ReceiveHandler.xsd、ReceiveLocation.xsd、TransmitLocation.xsd、および TransmitHandler.xsd です。</span><span class="sxs-lookup"><span data-stu-id="9bd96-147">Four XSD files included in the SDK File Adapter sample primarily handle adapter configuration: ReceiveHandler.xsd, ReceiveLocation.xsd, TransmitLocation.xsd, and TransmitHandler.xsd.</span></span>  
  
 <span data-ttu-id="9bd96-148">次のトピックでは、これらの各ファイルについて説明し、変更する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9bd96-148">The following topics discuss each of these files and describe how you can modify them.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9bd96-149">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="9bd96-149">In This Section</span></span>  
  
-   [<span data-ttu-id="9bd96-150">アダプターの構成情報の検証</span><span class="sxs-lookup"><span data-stu-id="9bd96-150">Validating the Adapter Configuration</span></span>](../core/validating-the-adapter-configuration.md)  
  
-   [<span data-ttu-id="9bd96-151">アダプターの登録</span><span class="sxs-lookup"><span data-stu-id="9bd96-151">Registering an Adapter</span></span>](../core/registering-an-adapter.md)  
  
-   [<span data-ttu-id="9bd96-152">アダプター フレームワーク構成スキーマの拡張機能</span><span class="sxs-lookup"><span data-stu-id="9bd96-152">Adapter Framework Configuration Schema Extensions</span></span>](../core/adapter-framework-configuration-schema-extensions.md)  
  
-   [<span data-ttu-id="9bd96-153">サポートされているアダプターの XSD 要素の型</span><span class="sxs-lookup"><span data-stu-id="9bd96-153">Supported Adapter XSD Element Types</span></span>](../core/supported-adapter-xsd-element-types.md)  
  
-   [<span data-ttu-id="9bd96-154">アダプターの XSD Element-Attribute コンストラクター</span><span class="sxs-lookup"><span data-stu-id="9bd96-154">Adapter XSD Element-Attribute Constructs</span></span>](../core/adapter-xsd-element-attribute-constructs.md)  
  
-   [<span data-ttu-id="9bd96-155">アダプターの XSD Data Type-Facet コンストラクター</span><span class="sxs-lookup"><span data-stu-id="9bd96-155">Adapter XSD Data Type-Facet Constructs</span></span>](../core/adapter-xsd-data-type-facet-constructs.md)  
  
-   [<span data-ttu-id="9bd96-156">アダプターの詳細構成コンポーネント</span><span class="sxs-lookup"><span data-stu-id="9bd96-156">Advanced Configuration Components for Adapters</span></span>](../core/advanced-configuration-components-for-adapters.md)