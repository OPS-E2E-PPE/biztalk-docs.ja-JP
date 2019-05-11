---
title: リゾルバー サービス サンプルのしくみ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 33b5f886-ec54-4b2b-b09d-fb4c47ad43a5
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2d07fbe42cf1253f5976227211f59ff66809fb70
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65279036"
---
# <a name="how-the-resolver-service-sample-works"></a><span data-ttu-id="e4f46-102">リゾルバー サービス サンプルのしくみ</span><span class="sxs-lookup"><span data-stu-id="e4f46-102">How the Resolver Service Sample Works</span></span>
<span data-ttu-id="e4f46-103">リゾルバー サービス サンプルでは、リゾルバー サービスのインスタンスを作成し、指定したメッセージを処理するために渡します。</span><span class="sxs-lookup"><span data-stu-id="e4f46-103">The Resolver Service sample instantiates the Resolver service and passes the message you specify to it for processing.</span></span> <span data-ttu-id="e4f46-104">リゾルバー サービス サンプルのクライアント アプリケーションでは、競合回避モジュールの複数の要求が含まれていて、リゾルバー サービスにこれらの要求を送信します ResolverList.xml ファイルへのパスとして最初のパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="e4f46-104">The Resolver Service sample client application uses the first parameter as the path to the ResolverList.xml file, which contains multiple resolver requests, and sends these requests to the Resolver service.</span></span> <span data-ttu-id="e4f46-105">たとえば、サンプルで使用される XPATH 要求は、次のように。</span><span class="sxs-lookup"><span data-stu-id="e4f46-105">For example, the following is the XPATH request used in the sample.</span></span>  
  
```  
  
//XPATH  
<Resolver>  
  <name>XPATHWithFILE</name>   
  <Content>![CDATA[XPATH:\\TransportLocation=/*[local-name()='OrderDoc'   
    and namespace-uri()='http://globalbank.esb.dynamicresolution.com/  
    northamericanservices/']/*[local-name()='ID' and namespace-  
    uri()='http://globalbank.esb.dynamicresolution.com/  
    northamericanservices/'];TargetNamespace=;  
    MessageExchangePattern=;EndpointConfig=;JaxRpcResponse=;TransportType=;  
    Action=;TransformType=]]  
  </Content>   
  <body>  
    ![CDATA[   
    <ns0:OrderDoc xmlns:ns0="http://globalbank.esb.dynamicresolution.com/northamericanservices/">  
      <ns0:customerName>Microsoft</ns0:customerName>  
  
<ns0:ID>FILE://C:\Projects\Microsoft.Practices.ESB\Source\Samples  
    \DynamicResolution\Test\Filedrop\OUt\%MessageID%.xml</ns0:ID>   
      <ns0:requestType>10</ns0:requestType>   
    </ns0:OrderDoc>  
    ]]   
  </body>  
</Resolver>  
```  
  
> [!NOTE]
>  <span data-ttu-id="e4f46-106">実際の内容、 **\<コンテンツ\>** 要素に上記の一覧で、行をラップするために使用する空白文字が含まれていません。</span><span class="sxs-lookup"><span data-stu-id="e4f46-106">The actual content of the **\<Content\>** element does not contain the white space characters used to wrap the lines in the preceding listing.</span></span>  
  
 <span data-ttu-id="e4f46-107">要求には内の競合回避モジュールの構成の接続文字列が含まれている上記の一覧を示しています、 **\<コンテンツ\>** 要素。</span><span class="sxs-lookup"><span data-stu-id="e4f46-107">The preceding listing shows that the request contains the resolver configuration connection string within a **\<Content\>** element.</span></span> <span data-ttu-id="e4f46-108">**\<本文\>** 要素には、メッセージ本文が含まれています。</span><span class="sxs-lookup"><span data-stu-id="e4f46-108">The **\<body\>** element contains the message body.</span></span>  
  
 <span data-ttu-id="e4f46-109">リゾルバー サービスの使用、 **ResolverMgr**接続文字列での競合回避モジュールの型によって定義された、適切な競合回避モジュールの具体的なインスタンスをインスタンス化するクラス。</span><span class="sxs-lookup"><span data-stu-id="e4f46-109">The Resolver service uses the **ResolverMgr** class to instantiate a concrete instance of the appropriate resolver, defined by the resolver type in the connection string.</span></span> <span data-ttu-id="e4f46-110">XPATH の要求の場合、XPATH の競合回避モジュールになります。</span><span class="sxs-lookup"><span data-stu-id="e4f46-110">In the case of the XPATH request, this is the XPATH resolver.</span></span>  
  
 <span data-ttu-id="e4f46-111">次に、フレームワークがのインスタンスを作成、 **ResolveProvider** ESB という名前のクラス。要求を処理する Resolver.XPath します。</span><span class="sxs-lookup"><span data-stu-id="e4f46-111">Next, the framework creates an instance of the **ResolveProvider** class named ESB.Resolver.XPath to process the request.</span></span> <span data-ttu-id="e4f46-112">クライアント アプリケーションでは、\Source\Samples\ResolverService\Output をという名前のフォルダーに、リゾルバー サービスから応答メッセージを書き込みます。</span><span class="sxs-lookup"><span data-stu-id="e4f46-112">The client application writes the response message from the Resolver service into the folder named \Source\Samples\ResolverService\Output.</span></span> <span data-ttu-id="e4f46-113">次のリストは、応答の内容を示しています。</span><span class="sxs-lookup"><span data-stu-id="e4f46-113">The following listing shows the contents of the response.</span></span>  
  
```  
  
//XPATH  
Resolver.Action =   
Resolver.ActionField =   
Resolver.DocumentSpecName =   
Resolver.DocumentSpecStrongName =   
Resolver.EndpointConfig =   
Resolver.EpmRRCorrelationToken =   
Resolver.FixJaxRpc = False  
Resolver.InboundTransportLocation =   
Resolver.InboundTransportType =   
Resolver.InterchangeId =   
Resolver.IsRequestResponse =   
Resolver.MessageExchangePattern =   
Resolver.MessageType =   
Resolver.MethodName =   
Resolver.OutboundTransportCLSID =   
Resolver.ReceiveLocationName =   
Resolver.ReceivePortName =   
Resolver.Success = False  
Resolver.TargetNamespace =   
Resolver.TransformType =   
Resolver.TransportLocation = FILE://C:\Projects\Microsoft.  
    Practices.ESB\Source\Samples  
\DynamicResolution\Test\Filedrop\OUt\%MessageID%.xml  
Resolver.TransportNamespace =   
Resolver.TransportType = FILE  
Resolver.WindowUserField =  
```