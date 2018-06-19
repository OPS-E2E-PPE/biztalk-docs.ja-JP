---
title: アダプターのデザインに関する問題 |Microsoft ドキュメント
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
ms.openlocfilehash: 79c6228db8342f3d1ad2628d4e4caf418efd9b29
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22226562"
---
# <a name="adapter-design-issues"></a><span data-ttu-id="5fc29-102">アダプターのデザインの問題点</span><span class="sxs-lookup"><span data-stu-id="5fc29-102">Adapter Design Issues</span></span>
<span data-ttu-id="5fc29-103">アダプターの構成は、ユーザーがデザイン時に構成を変更すると、シングル サインオン (SSO) データベースに格納されます。</span><span class="sxs-lookup"><span data-stu-id="5fc29-103">Adapter configuration is stored in the Single Sign-On (SSO) database when the user makes configuration changes during design time.</span></span> <span data-ttu-id="5fc29-104">実行時に、メッセージング エンジンはアダプターの構成を取得し、その構成をアダプターに送信します。</span><span class="sxs-lookup"><span data-stu-id="5fc29-104">At run time the Messaging Engine retrieves the adapter's configuration and delivers it to the adapter.</span></span> <span data-ttu-id="5fc29-105">アダプターには、次の 4 種類の構成情報が送信されます。</span><span class="sxs-lookup"><span data-stu-id="5fc29-105">Four types of configuration information are delivered to adapters:</span></span>  
  
-   <span data-ttu-id="5fc29-106">受信ハンドラーの構成</span><span class="sxs-lookup"><span data-stu-id="5fc29-106">Receive handler configuration</span></span>  
  
-   <span data-ttu-id="5fc29-107">受信場所 (エンドポイント) の構成</span><span class="sxs-lookup"><span data-stu-id="5fc29-107">Receive location (endpoint) configuration</span></span>  
  
-   <span data-ttu-id="5fc29-108">送信ハンドラーの構成</span><span class="sxs-lookup"><span data-stu-id="5fc29-108">Send handler configuration</span></span>  
  
-   <span data-ttu-id="5fc29-109">送信場所 (エンドポイント) の構成</span><span class="sxs-lookup"><span data-stu-id="5fc29-109">Send location (endpoint) configuration</span></span>  
  
## <a name="receive-and-send-handler-configuration"></a><span data-ttu-id="5fc29-110">受信し、送信ハンドラーの構成</span><span class="sxs-lookup"><span data-stu-id="5fc29-110">Receive and Send Handler Configuration</span></span>  
 <span data-ttu-id="5fc29-111">アダプターのハンドラー構成は省略可能なの実装でアダプターに送信**IPersistPropertyBag**.**ロード**インターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="5fc29-111">An adapter's handler configuration is delivered to the adapter on its implementation of the optional **IPersistPropertyBag**.**Load** interface.</span></span> <span data-ttu-id="5fc29-112">ハンドラー構成は一度しか送信されないため、アダプダのハンドラー構成が BizTalk サービスの開始後に変更された場合、アダプターは更新されません。</span><span class="sxs-lookup"><span data-stu-id="5fc29-112">The handler configuration is delivered only once, so if the adapter handler configuration is changed after the BizTalk service has started the adapter is not updated.</span></span> <span data-ttu-id="5fc29-113">一般的なモデルでは、アダプターはハンドラー構成を既定の構成として処理します。エンドポイント構成は、エンドポイントごとにハンドラー構成をオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="5fc29-113">The common model is for the adapter to treat the handler configuration as the default configuration; endpoint configuration overrides the handler configuration on a per-endpoint basis.</span></span>  
  
 <span data-ttu-id="5fc29-114">次のコードは、構成の解析例を示します。</span><span class="sxs-lookup"><span data-stu-id="5fc29-114">The following code fragment demonstrates parsing the configuration.</span></span> <span data-ttu-id="5fc29-115">渡されたプロパティでは、アダプターの構成、**ロード**文字列プロパティで呼び出して**AdapterConfig**です。</span><span class="sxs-lookup"><span data-stu-id="5fc29-115">The adapter's configuration is in the property passed in to the **Load** call in the string property **AdapterConfig**.</span></span> <span data-ttu-id="5fc29-116">このプロパティ値には、アダプターの構成を表す XML ドキュメントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="5fc29-116">This property value contains an XML document representing the adapter's configuration.</span></span> <span data-ttu-id="5fc29-117">アダプターはこの構成をドキュメント オブジェクト モデル (DOM) または XML リーダーに読み込み、XPath を使用して個々のプロパティを取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5fc29-117">The adapter needs to load this configuration into a document object model (DOM) or an XML reader and use XPath to retrieve the individual properties.</span></span>  
  
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
  
## <a name="receive-location-configuration"></a><span data-ttu-id="5fc29-118">受信場所の構成</span><span class="sxs-lookup"><span data-stu-id="5fc29-118">Receive Location Configuration</span></span>  
 <span data-ttu-id="5fc29-119">受信場所の構成情報がの実装でアダプターに配信される**IBTTransportConfig**です。</span><span class="sxs-lookup"><span data-stu-id="5fc29-119">Receive location configuration information is delivered to an adapter on its implementation of **IBTTransportConfig**.</span></span> <span data-ttu-id="5fc29-120">このインターフェイスには、3 つのメソッドが含まれています。 **AddReceiveEndpoint**、 **UpdateEndpointConfig**、および**RemoveReceiveEndpoint**です。</span><span class="sxs-lookup"><span data-stu-id="5fc29-120">This interface contains the three methods **AddReceiveEndpoint**, **UpdateEndpointConfig**, and **RemoveReceiveEndpoint**.</span></span> <span data-ttu-id="5fc29-121">メッセージング エンジンは、メッセージを受信するために受信待ちする必要があるエンドポイントをアダプターに通知します。</span><span class="sxs-lookup"><span data-stu-id="5fc29-121">The Messaging Engine notifies the adapter of which endpoints it needs to listen on to receive messages.</span></span> <span data-ttu-id="5fc29-122">個々のエンドポイントの構成が変更されると、アダプターはそのエンドポイントの変更について通知を受けます。</span><span class="sxs-lookup"><span data-stu-id="5fc29-122">When the configuration for an individual endpoint is changed the adapter is notified of the change for that endpoint.</span></span> <span data-ttu-id="5fc29-123">これは、ハンドラーの構成が変更されてもアダプターは通知を受けないのとは対照的です。</span><span class="sxs-lookup"><span data-stu-id="5fc29-123">This is in contrast to the fact that when handler configuration changes the adapter is not notified.</span></span> <span data-ttu-id="5fc29-124">同様に、BizTalk Server はサービス ウィンドウがアクティブまたは非アクティブになるとエンドポイントを追加、削除するため、アダプターはサービス ウィンドウを処理する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="5fc29-124">Similarly, the adapter does not need to handle service windows because BizTalk Server adds or removes endpoints as service windows become active or inactive.</span></span>  
  
### <a name="addreceiveendpoint"></a><span data-ttu-id="5fc29-125">AddReceiveEndpoint</span><span class="sxs-lookup"><span data-stu-id="5fc29-125">AddReceiveEndpoint</span></span>  
 <span data-ttu-id="5fc29-126">アダプターが、エンドポイントでは、エンジンの呼び出しで待機を開始する必要がある場合**IBTTransportConfig.AddReceiveEndpoint**受信場所の URI の場合、そのエンドポイントのアダプターの構成を含むプロパティ バッグに渡すとそのエンドポイントの BizTalk Server 固有の構成を含む 2 つ目のプロパティ バッグ。</span><span class="sxs-lookup"><span data-stu-id="5fc29-126">When an adapter needs to begin listening on an endpoint, the engine calls **IBTTransportConfig.AddReceiveEndpoint** passing in the receive location's URI, a property bag containing the adapter's configuration for that endpoint, and a second property bag containing BizTalk Server-specific configuration for that endpoint.</span></span> <span data-ttu-id="5fc29-127">アダプターは、BizTalk Server システムのプロパティとしてメッセージ コンテキストに URI を書き込む必要があります**InboundTransportLocation**です。</span><span class="sxs-lookup"><span data-stu-id="5fc29-127">The adapter needs to write the URI to the message context as the BizTalk Server system property **InboundTransportLocation**.</span></span>  
  
 <span data-ttu-id="5fc29-128">アダプターのプロパティ バッグから受信場所のプロパティを読み取るのは、上記で説明したハンドラー構成を読み取るのと同じことです。</span><span class="sxs-lookup"><span data-stu-id="5fc29-128">Reading the receive location properties from the adapter's property bag is the same as reading the handler configuration as detailed above.</span></span> <span data-ttu-id="5fc29-129">アダプターに渡された BizTalk Server の構成には、1 つのプロパティが含まれています。 **TwoWayReceivePort**、ポートが一方向または双方向かどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="5fc29-129">The BizTalk Server configuration passed into the adapter contains a single property, **TwoWayReceivePort**, which indicates whether the port is one-way or two-way.</span></span> <span data-ttu-id="5fc29-130">次のコードは、受信ポートが一方向と双方向のどちらであるかを BizTalk Server のプロパティ バッグから評価する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="5fc29-130">The following code fragment illustrates how to evaluate if the receive port is one-way or two-way from the BizTalk Server property bag:</span></span>  
  
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
  
### <a name="updateendpointconfig"></a><span data-ttu-id="5fc29-131">UpdateEndpointConfig</span><span class="sxs-lookup"><span data-stu-id="5fc29-131">UpdateEndpointConfig</span></span>  
 <span data-ttu-id="5fc29-132">場所が変更される、エンジンを使用してアクティブな構成が表示されたら、 **UpdateEndpointConfig** API に別の構成を使用する必要があることをアダプターに通知します。</span><span class="sxs-lookup"><span data-stu-id="5fc29-132">When the configuration of an active receive location is changed, the engine uses the **UpdateEndpointConfig** API to notify the adapter that it needs to use a different configuration.</span></span> <span data-ttu-id="5fc29-133">BizTalk Server 固有の構成を含め、すべての構成がアダプターに送信されます。</span><span class="sxs-lookup"><span data-stu-id="5fc29-133">All of the configuration is delivered to the adapter, including the BizTalk Server-specific configuration.</span></span>  
  
### <a name="removereceiveendpoint"></a><span data-ttu-id="5fc29-134">RemoveReceiveEndpoint</span><span class="sxs-lookup"><span data-stu-id="5fc29-134">RemoveReceiveEndpoint</span></span>  
 <span data-ttu-id="5fc29-135">アダプターを介して通知受信場所がアクティブでなくなったときに**RemoveReceiveEndpoint**です。</span><span class="sxs-lookup"><span data-stu-id="5fc29-135">When a receive location is no longer active, the adapter is notified through **RemoveReceiveEndpoint**.</span></span> <span data-ttu-id="5fc29-136">アダプターから返された後**RemoveReceiveEndpoint**その URI を使用してエンジンにメッセージを送信するには使用できなくします。</span><span class="sxs-lookup"><span data-stu-id="5fc29-136">After the adapter returns from **RemoveReceiveEndpoint** it is no longer allowed to use that URI to submit messages into the engine.</span></span>  
  
## <a name="send-port-configuration"></a><span data-ttu-id="5fc29-137">送信ポートの構成</span><span class="sxs-lookup"><span data-stu-id="5fc29-137">Send Port Configuration</span></span>  
 <span data-ttu-id="5fc29-138">メッセージング エンジンは送信ポートの構成をアダプターのメッセージ内のメッセージ コンテキストに書き込んでから、メッセージをアダプターに送信します。</span><span class="sxs-lookup"><span data-stu-id="5fc29-138">The Messaging Engine writes the configuration for the send port to the message context in the adapter’s namespace before delivering the message to the adapter.</span></span> <span data-ttu-id="5fc29-139">アダプターは、構成の読み取りや検証を実行した後に、その構成を使用してメッセージの送信を制御します。</span><span class="sxs-lookup"><span data-stu-id="5fc29-139">It is the adapters’ responsibility to read and validate the configuration, which it subsequently uses to control the transmission of the message.</span></span> <span data-ttu-id="5fc29-140">バッチ化された送信をサポートする送信アダプターの場合は、別の送信ポートを宛先とするメッセージが同じバッチ内に存在する可能性があるため、アダプターはこれらの "混在" バッチを処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5fc29-140">For send adapters that support batched sends, messages destined for different send ports may be in the same batch, so the adapter needs to handle these "mixed" batches.</span></span>  
  
 <span data-ttu-id="5fc29-141">次のコード フラグメントを読み取る方法を示しています、 **OutboundTransportLocation**送信ポートの URI はします。</span><span class="sxs-lookup"><span data-stu-id="5fc29-141">The following code fragment illustrates how to read the **OutboundTransportLocation** that is the URI for the send port.</span></span> <span data-ttu-id="5fc29-142">また、アダプターの構成を含む XML BLOB を読み取ってから、個々のプロパティを読み取る方法も示します。</span><span class="sxs-lookup"><span data-stu-id="5fc29-142">It also shows how to read the XML blob containing the adapter's configuration and then read the individual properties.</span></span>  
  
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
  
 <span data-ttu-id="5fc29-143">**実装のヒン ト:** アダプターは一般に使用する必要があります、 **OutboundTransportLocation**メッセージ コンテキスト プロパティをメッセージを送信するアドレスを決定します。</span><span class="sxs-lookup"><span data-stu-id="5fc29-143">**Implementation Tip:** Adapters should in general use the **OutboundTransportLocation** message context property to determine the address to send the message to.</span></span> <span data-ttu-id="5fc29-144">この方法を実行すると、静的送信と動的送信に対する送信を一貫して処理できます。</span><span class="sxs-lookup"><span data-stu-id="5fc29-144">By doing this the adapter can handle transmissions to both static and dynamic sends consistently.</span></span> <span data-ttu-id="5fc29-145">また、この方法を使用すると、実稼動のバインド ファイルのアドレスを簡単に変更できます。</span><span class="sxs-lookup"><span data-stu-id="5fc29-145">This also simplifies the modification of addresses in production binding files.</span></span>  
  
## <a name="xsd"></a><span data-ttu-id="5fc29-146">[XSD]</span><span class="sxs-lookup"><span data-stu-id="5fc29-146">XSD</span></span>  
 <span data-ttu-id="5fc29-147">SDK ファイル アダプターのサンプルに含まれる 4 つの XSD ファイル ハンドル アダプター構成では、主に: ReceiveHandler.xsd、ReceiveLocation.xsd、TransmitLocation.xsd、および TransmitHandler.xsd です。</span><span class="sxs-lookup"><span data-stu-id="5fc29-147">Four XSD files included in the SDK File Adapter sample primarily handle adapter configuration: ReceiveHandler.xsd, ReceiveLocation.xsd, TransmitLocation.xsd, and TransmitHandler.xsd.</span></span>  
  
 <span data-ttu-id="5fc29-148">次のトピックでは、これらの各ファイルと、それらのファイルの変更方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5fc29-148">The following topics discuss each of these files and describe how you can modify them.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5fc29-149">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="5fc29-149">In This Section</span></span>  
  
-   [<span data-ttu-id="5fc29-150">アダプター構成の検証</span><span class="sxs-lookup"><span data-stu-id="5fc29-150">Validating the Adapter Configuration</span></span>](../core/validating-the-adapter-configuration.md)  
  
-   [<span data-ttu-id="5fc29-151">アダプターの登録</span><span class="sxs-lookup"><span data-stu-id="5fc29-151">Registering an Adapter</span></span>](../core/registering-an-adapter.md)  
  
-   [<span data-ttu-id="5fc29-152">アダプター フレームワーク構成スキーマの拡張機能</span><span class="sxs-lookup"><span data-stu-id="5fc29-152">Adapter Framework Configuration Schema Extensions</span></span>](../core/adapter-framework-configuration-schema-extensions.md)  
  
-   [<span data-ttu-id="5fc29-153">サポートされているアダプターの XSD 要素の型</span><span class="sxs-lookup"><span data-stu-id="5fc29-153">Supported Adapter XSD Element Types</span></span>](../core/supported-adapter-xsd-element-types.md)  
  
-   [<span data-ttu-id="5fc29-154">アダプターの XSD Element-attribute コンス トラクター</span><span class="sxs-lookup"><span data-stu-id="5fc29-154">Adapter XSD Element-Attribute Constructs</span></span>](../core/adapter-xsd-element-attribute-constructs.md)  
  
-   [<span data-ttu-id="5fc29-155">アダプターの XSD Data Type-facet コンス トラクター</span><span class="sxs-lookup"><span data-stu-id="5fc29-155">Adapter XSD Data Type-Facet Constructs</span></span>](../core/adapter-xsd-data-type-facet-constructs.md)  
  
-   [<span data-ttu-id="5fc29-156">アダプターの高度な構成コンポーネント</span><span class="sxs-lookup"><span data-stu-id="5fc29-156">Advanced Configuration Components for Adapters</span></span>](../core/advanced-configuration-components-for-adapters.md)