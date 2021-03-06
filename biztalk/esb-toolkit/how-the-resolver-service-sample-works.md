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
# <a name="how-the-resolver-service-sample-works"></a>リゾルバー サービス サンプルのしくみ
リゾルバー サービス サンプルでは、リゾルバー サービスのインスタンスを作成し、指定したメッセージを処理するために渡します。 リゾルバー サービス サンプルのクライアント アプリケーションでは、競合回避モジュールの複数の要求が含まれていて、リゾルバー サービスにこれらの要求を送信します ResolverList.xml ファイルへのパスとして最初のパラメーターを使用します。 たとえば、サンプルで使用される XPATH 要求は、次のように。  
  
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
>  実際の内容、 **\<コンテンツ\>** 要素に上記の一覧で、行をラップするために使用する空白文字が含まれていません。  
  
 要求には内の競合回避モジュールの構成の接続文字列が含まれている上記の一覧を示しています、 **\<コンテンツ\>** 要素。 **\<本文\>** 要素には、メッセージ本文が含まれています。  
  
 リゾルバー サービスの使用、 **ResolverMgr**接続文字列での競合回避モジュールの型によって定義された、適切な競合回避モジュールの具体的なインスタンスをインスタンス化するクラス。 XPATH の要求の場合、XPATH の競合回避モジュールになります。  
  
 次に、フレームワークがのインスタンスを作成、 **ResolveProvider** ESB という名前のクラス。要求を処理する Resolver.XPath します。 クライアント アプリケーションでは、\Source\Samples\ResolverService\Output をという名前のフォルダーに、リゾルバー サービスから応答メッセージを書き込みます。 次のリストは、応答の内容を示しています。  
  
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