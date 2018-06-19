---
title: WCF アダプター コンテキスト プロパティを使用して動的送信ポートの構成 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF services, send ports
- send ports, WCF services
- dynamic send ports, WCF services
- send ports, dynamic
ms.assetid: 2a7e2cd2-fa2d-45da-bb8e-eb8bab21bfa3
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2bca34afa85c8764215f47d1272c115354889fa5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22233354"
---
# <a name="configuring-dynamic-send-ports-using-wcf-adapters-context-properties"></a><span data-ttu-id="50224-102">WCF アダプタ コンテキスト プロパティによる動的送信ポートの構成</span><span class="sxs-lookup"><span data-stu-id="50224-102">Configuring Dynamic Send Ports Using WCF Adapters Context Properties</span></span>
<span data-ttu-id="50224-103">WCF アダプタ用の動的送信ポートを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="50224-103">You can configure dynamic send ports for WCF adapters.</span></span> <span data-ttu-id="50224-104">URI、アクション、およびバインドのプロパティを受信メッセージから決定されで指定して可能性があります、**式**図形を次の Wcf-nettcp アダプタで示すようにします。</span><span class="sxs-lookup"><span data-stu-id="50224-104">The URI, action, and binding might be determined from a property on an incoming message, and then specified in the **Expression** shape, as shown in the following WCF-NetTcp adapter:</span></span>  
  
```  
MessageOut=MessageIn;  
MessageOut(WCF.Action)="http://tempuri.org/IReceiveMessage/ReceiveMessage";  
MessageOut(WCF.SecurityMode)="Transport";  
MessageOut(WCF.TransportClientCredentialType)="Windows";  
DynamicSendPort(Microsoft.XLANGs.BaseTypes.Address)="net.tcp://localhost:8001/netTcp";  
DynamicSendPort(Microsoft.XLANGs.BaseTypes.TransportType)="WCF-NetTcp";  
```  
  
 <span data-ttu-id="50224-105">次のコードで WCF コンテキスト プロパティを指定する方法の例を示します、**式**Wcf-custom アダプターの図形。</span><span class="sxs-lookup"><span data-stu-id="50224-105">The following code shows an example of how to specify the WCF context properties in the **Expression** shape for a WCF-Custom adapter:</span></span>  
  
```  
MessageOut=MessageIn;  
MessageOut(WCF.BindingType)="customBinding";  
MessageOut(WCF.Action)="http://tempuri.org/IReceiveMessage/ReceiveMessage";  
MessageOut(WCF.BindingConfiguration)=@"<binding name=""customBinding""><binaryMessageEncoding /><tcpTransport /></binding>";  
DynamicSendPort(Microsoft.XLANGs.BaseTypes.Address)="net.tcp://localhost:8001/customNetTcp";  
DynamicSendPort(Microsoft.XLANGs.BaseTypes.TransportType)="WCF-Custom";  
```  
  
 <span data-ttu-id="50224-106">WCF コンテキスト プロパティを指定する際の考慮事項を次に示します。</span><span class="sxs-lookup"><span data-stu-id="50224-106">Considerations when specifying WCF context properties are as follows:</span></span>  
  
-   <span data-ttu-id="50224-107">複数のアダプターにマップできるアドレスが存在します。</span><span class="sxs-lookup"><span data-stu-id="50224-107">There are addresses that can be mapped to multiple adapters.</span></span> <span data-ttu-id="50224-108">たとえば、 http:// または https:// で始まるアドレスは、HTTP アダプタだけでなく、WCF-BasicHttp アダプタ、WCF-WsHttp アダプタ、または WCF-Custom アダプタでも処理することができます。</span><span class="sxs-lookup"><span data-stu-id="50224-108">For example, an address that starts with http:// or https:// can be handled by the HTTP adapter as well as by the WCF-BasicHttp, WCF-WsHttp, or WCF-Custom adapters.</span></span> <span data-ttu-id="50224-109">別の例として、上のサンプル コードでは、どちらも「net.tcp://」で始まるアドレスを使用していますが、2 番目のサンプル コードではカスタム バインドを使用するので、アドレスの処理には、WCF-Custom アダプタを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="50224-109">For another example, in the above sample code, both of them are using the address starts with net.tcp://, yet because the second sample code uses custom binding, WCF-Custom adapter should be used to handle the address.</span></span> <span data-ttu-id="50224-110">そのため、正しいアダプターを識別する必要があります構成する、省略可能な**Microsoft.XLANGs.BaseTypes.TransportType**フィールドで、**式**図形のアダプターを使用するとします。</span><span class="sxs-lookup"><span data-stu-id="50224-110">Therefore, to identify the correct adapter, you must configure the optional **Microsoft.XLANGs.BaseTypes.TransportType** field in an **Expression** shape with the adapter that you want to use.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="50224-111">アドレスの先頭で http:// または https:// 、しを指定しない場合、 **Microsoft.XLANGs.BaseTypes.TransportType**フィールドで、既定では、BizTalk エンジンを使用して、HTTP アダプター。</span><span class="sxs-lookup"><span data-stu-id="50224-111">If the address starts with http:// or https://, and if you do not specify the **Microsoft.XLANGs.BaseTypes.TransportType** field, by default, the BizTalk engine will use the HTTP adapter.</span></span>  
  
-   <span data-ttu-id="50224-112">**WCF です。BindingType**名前でバインドを識別します。</span><span class="sxs-lookup"><span data-stu-id="50224-112">The **WCF.BindingType** identifies the binding by name.</span></span> <span data-ttu-id="50224-113">次のいずれかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="50224-113">It can be one of the following:</span></span>  
  
    -   <span data-ttu-id="50224-114">basicHttpBinding</span><span class="sxs-lookup"><span data-stu-id="50224-114">basicHttpBinding</span></span>  
  
    -   <span data-ttu-id="50224-115">customBinding</span><span class="sxs-lookup"><span data-stu-id="50224-115">customBinding</span></span>  
  
    -   <span data-ttu-id="50224-116">netMsmqBinding</span><span class="sxs-lookup"><span data-stu-id="50224-116">netMsmqBinding</span></span>  
  
    -   <span data-ttu-id="50224-117">netNamedPipeBinding</span><span class="sxs-lookup"><span data-stu-id="50224-117">netNamedPipeBinding</span></span>  
  
    -   <span data-ttu-id="50224-118">netTcpBinding</span><span class="sxs-lookup"><span data-stu-id="50224-118">netTcpBinding</span></span>  
  
    -   <span data-ttu-id="50224-119">wsFederationHttpBinding</span><span class="sxs-lookup"><span data-stu-id="50224-119">wsFederationHttpBinding</span></span>  
  
    -   <span data-ttu-id="50224-120">wsHttpBinding</span><span class="sxs-lookup"><span data-stu-id="50224-120">wsHttpBinding</span></span>  
  
     <span data-ttu-id="50224-121">上の一覧は、拡張できます。</span><span class="sxs-lookup"><span data-stu-id="50224-121">The above list can be extended.</span></span> <span data-ttu-id="50224-122">たとえば、FtpBinding などの独自のバインドを一覧に追加できます。</span><span class="sxs-lookup"><span data-stu-id="50224-122">For example, you can add your own binding to it such as FtpBinding.</span></span>  
  
-   <span data-ttu-id="50224-123">**WCF です。BindingConfiguration**バインドの種類のバインド構成を指定します。</span><span class="sxs-lookup"><span data-stu-id="50224-123">The **WCF.BindingConfiguration** specifies the binding configuration for the binding type.</span></span> <span data-ttu-id="50224-124">このプロパティは、コンピュータの構成ファイルに登録されているバインドを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="50224-124">It takes any binding that are registered in the machine configuration file.</span></span> <span data-ttu-id="50224-125">WCF 構成ファイルのバインド構成で使用される形式と同じ形式の XML 構成ファイルも受け取ります。</span><span class="sxs-lookup"><span data-stu-id="50224-125">It also takes the XML configuration in the same format as used in the binding configuration in the WCF configuration file.</span></span>  
  
-   <span data-ttu-id="50224-126">追加の WCF プロパティの指定が必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="50224-126">You may need to specify additional WCF properties.</span></span> <span data-ttu-id="50224-127">入力**WCF**式エディターで IntelliSense 機能がすべての利用可能なコンテキスト プロパティを一覧する必要があります。</span><span class="sxs-lookup"><span data-stu-id="50224-127">You can type **WCF** in the Expression Editor, and the IntelliSense feature should list all the available context properties.</span></span> <span data-ttu-id="50224-128">WCF コンテキスト プロパティの詳細については、次を参照してください。 [WCF アダプター プロパティ スキーマおよびプロパティ](../core/wcf-adapters-property-schema-and-properties.md)です。</span><span class="sxs-lookup"><span data-stu-id="50224-128">For more information about WCF context properties, see [WCF Adapters Property Schema and Properties](../core/wcf-adapters-property-schema-and-properties.md).</span></span>  
  
 <span data-ttu-id="50224-129">前の例を構成する方法を示して**WCF です。アクション**単一の操作でします。</span><span class="sxs-lookup"><span data-stu-id="50224-129">The preceding examples show how to configure **WCF.Action** with a single action.</span></span> <span data-ttu-id="50224-130">複数アクションのマッピング シナリオの場合、WCF アダプタは、動的送信ポートでの複数アクションのマッピングの使用をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="50224-130">For multiple actions mapping scenarios, WCF adapter do not support using multiple actions mapping with dynamic send ports.</span></span> <span data-ttu-id="50224-131">設定できるは、実際のアクションだけ、 **WCF です。アクション**コンテキスト プロパティとしての上に表示します。</span><span class="sxs-lookup"><span data-stu-id="50224-131">You can just set the actual action in the **WCF.Action** context property as showing in above.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50224-132">参照</span><span class="sxs-lookup"><span data-stu-id="50224-132">See Also</span></span>  
 <span data-ttu-id="50224-133">[送信アダプタの WCF の SOAP アクションの指定](../core/specifying-soap-actions-for-wcf-send-adapters.md) </span><span class="sxs-lookup"><span data-stu-id="50224-133">[Specifying SOAP Actions for WCF Send Adapters](../core/specifying-soap-actions-for-wcf-send-adapters.md) </span></span>  
 <span data-ttu-id="50224-134">[動的ポートに値を代入する式を使用する方法](../core/how-to-use-expressions-to-assign-values-to-dynamic-ports.md) </span><span class="sxs-lookup"><span data-stu-id="50224-134">[How to Use Expressions to Assign Values to Dynamic Ports](../core/how-to-use-expressions-to-assign-values-to-dynamic-ports.md) </span></span>  
 [<span data-ttu-id="50224-135">ポートのバインド</span><span class="sxs-lookup"><span data-stu-id="50224-135">Port Bindings</span></span>](../core/port-bindings.md)