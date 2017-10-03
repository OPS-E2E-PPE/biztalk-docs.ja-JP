---
title: "WCF アダプター コンテキスト プロパティを使用して動的送信ポートの構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF services, send ports
- send ports, WCF services
- dynamic send ports, WCF services
- send ports, dynamic
ms.assetid: 2a7e2cd2-fa2d-45da-bb8e-eb8bab21bfa3
caps.latest.revision: "19"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2bca34afa85c8764215f47d1272c115354889fa5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-dynamic-send-ports-using-wcf-adapters-context-properties"></a>WCF アダプタ コンテキスト プロパティによる動的送信ポートの構成
WCF アダプタ用の動的送信ポートを構成することができます。 URI、アクション、およびバインドのプロパティを受信メッセージから決定されで指定して可能性があります、**式**図形を次の Wcf-nettcp アダプタで示すようにします。  
  
```  
MessageOut=MessageIn;  
MessageOut(WCF.Action)="http://tempuri.org/IReceiveMessage/ReceiveMessage";  
MessageOut(WCF.SecurityMode)="Transport";  
MessageOut(WCF.TransportClientCredentialType)="Windows";  
DynamicSendPort(Microsoft.XLANGs.BaseTypes.Address)="net.tcp://localhost:8001/netTcp";  
DynamicSendPort(Microsoft.XLANGs.BaseTypes.TransportType)="WCF-NetTcp";  
```  
  
 次のコードで WCF コンテキスト プロパティを指定する方法の例を示します、**式**Wcf-custom アダプターの図形。  
  
```  
MessageOut=MessageIn;  
MessageOut(WCF.BindingType)="customBinding";  
MessageOut(WCF.Action)="http://tempuri.org/IReceiveMessage/ReceiveMessage";  
MessageOut(WCF.BindingConfiguration)=@"<binding name=""customBinding""><binaryMessageEncoding /><tcpTransport /></binding>";  
DynamicSendPort(Microsoft.XLANGs.BaseTypes.Address)="net.tcp://localhost:8001/customNetTcp";  
DynamicSendPort(Microsoft.XLANGs.BaseTypes.TransportType)="WCF-Custom";  
```  
  
 WCF コンテキスト プロパティを指定する際の考慮事項を次に示します。  
  
-   複数のアダプターにマップできるアドレスが存在します。 たとえば、「http://」または「https://」で始まるアドレスは、HTTP アダプタだけでなく、WCF-BasicHttp アダプタ、WCF-WsHttp アダプタ、または WCF-Custom アダプタでも処理することができます。 別の例として、上のサンプル コードでは、どちらも「net.tcp://」で始まるアドレスを使用していますが、2 番目のサンプル コードではカスタム バインドを使用するので、アドレスの処理には、WCF-Custom アダプタを使用する必要があります。 そのため、正しいアダプターを識別する必要があります構成する、省略可能な**Microsoft.XLANGs.BaseTypes.TransportType**フィールドで、**式**図形のアダプターを使用するとします。  
  
    > [!NOTE]
    >  アドレスの先頭で http:// または https://、しを指定しない場合、 **Microsoft.XLANGs.BaseTypes.TransportType**フィールドで、既定では、BizTalk エンジンを使用して、HTTP アダプター。  
  
-   **WCF です。BindingType**名前でバインドを識別します。 次のいずれかを指定できます。  
  
    -   basicHttpBinding  
  
    -   customBinding  
  
    -   netMsmqBinding  
  
    -   netNamedPipeBinding  
  
    -   netTcpBinding  
  
    -   wsFederationHttpBinding  
  
    -   wsHttpBinding  
  
     上の一覧は、拡張できます。 たとえば、FtpBinding などの独自のバインドを一覧に追加できます。  
  
-   **WCF です。BindingConfiguration**バインドの種類のバインド構成を指定します。 このプロパティは、コンピュータの構成ファイルに登録されているバインドを受け取ります。 WCF 構成ファイルのバインド構成で使用される形式と同じ形式の XML 構成ファイルも受け取ります。  
  
-   追加の WCF プロパティの指定が必要になる場合があります。 入力**WCF**式エディターで IntelliSense 機能がすべての利用可能なコンテキスト プロパティを一覧する必要があります。 WCF コンテキスト プロパティの詳細については、次を参照してください。 [WCF アダプター プロパティ スキーマおよびプロパティ](../core/wcf-adapters-property-schema-and-properties.md)です。  
  
 前の例を構成する方法を示して**WCF です。アクション**単一の操作でします。 複数アクションのマッピング シナリオの場合、WCF アダプタは、動的送信ポートでの複数アクションのマッピングの使用をサポートしていません。 設定できるは、実際のアクションだけ、 **WCF です。アクション**コンテキスト プロパティとしての上に表示します。  
  
## <a name="see-also"></a>参照  
 [送信アダプタの WCF の SOAP アクションの指定](../core/specifying-soap-actions-for-wcf-send-adapters.md)   
 [動的ポートに値を代入する式を使用する方法](../core/how-to-use-expressions-to-assign-values-to-dynamic-ports.md)   
 [ポートのバインド](../core/port-bindings.md)