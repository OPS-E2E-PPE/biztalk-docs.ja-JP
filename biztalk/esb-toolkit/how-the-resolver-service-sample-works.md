---
title: "リゾルバー サービスのサンプルのしくみ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 33b5f886-ec54-4b2b-b09d-fb4c47ad43a5
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: af9f90bf80435b00a0d39e83d2b2293595f6f200
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="how-the-resolver-service-sample-works"></a>リゾルバー サービスのサンプルのしくみ
リゾルバー サービスの例では、リゾルバー サービスのインスタンスを作成し、指定したメッセージを処理するために渡します。 リゾルバー サービスのサンプル クライアント アプリケーションは、競合回避モジュールの複数の要求を含み、リゾルバー サービスに、これらの要求を送信する ResolverList.xml ファイルへのパスとして、最初のパラメーターを使用します。 たとえば、次は、このサンプルで使用される XPATH 要求です。  
  
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
>  実際の内容、 **\<コンテンツ\>**要素に上記のリストで、行をラップするために使用する空白文字が含まれていません。  
  
 要求が、競合回避モジュールの構成の接続文字列内に含まれている前の一覧を示しています、 **\<コンテンツ\>**要素。 **\<本文\>**要素には、メッセージ本文が含まれています。  
  
 リゾルバー サービスの使用、 **ResolverMgr**接続文字列での競合回避モジュールの型によって定義された、適切な競合回避モジュールの具体的なインスタンスをインスタンス化するクラス。 XPATH 要求の場合これは、XPATH の競合回避モジュールです。  
  
 次に、フレームワークがのインスタンスを作成、 **ResolveProvider** ESB という名前のクラスです。要求を処理する Resolver.XPath です。 クライアント アプリケーションでは、\Source\Samples\ResolverService\Output をという名前のフォルダーに、リゾルバー サービスから応答メッセージを書き込みます。 次のリストは、応答の内容を示しています。  
  
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