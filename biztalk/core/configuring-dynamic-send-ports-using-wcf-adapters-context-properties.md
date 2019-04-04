---
title: WCF アダプター コンテキスト プロパティによる動的送信ポートの構成 |Microsoft Docs
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
ms.openlocfilehash: ca781dc1d101e3eef0976229b3d1b986c2f4498d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36995275"
---
# <a name="configuring-dynamic-send-ports-using-wcf-adapters-context-properties"></a>WCF アダプタ コンテキスト プロパティによる動的送信ポートの構成
WCF アダプタ用の動的送信ポートを構成することができます。 URI、アクション、およびバインド、受信メッセージのプロパティから決定されで指定された可能性があります、**式**図形、Wcf-nettcp アダプターを次に示すようにします。  
  
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
  
- 複数のアダプターにマップできるアドレスが存在します。 たとえば、「 http://」または「 https://」で始まるアドレスは、HTTP アダプタだけでなく、WCF-BasicHttp アダプタ、WCF-WsHttp アダプタ、または WCF-Custom アダプタでも処理することができます。 別の例として、上のサンプル コードでは、どちらも「net.tcp://」で始まるアドレスを使用していますが、2 番目のサンプル コードではカスタム バインドを使用するので、アドレスの処理には、WCF-Custom アダプタを使用する必要があります。 そのため、正しいアダプターを識別するために行う必要があります、省略可能な**Microsoft.XLANGs.BaseTypes.TransportType**フィールドに、**式**図形を使用するアダプターとします。  
  
  > [!NOTE]
  >  アドレスの先頭で http:// または https:// 、しを指定しない場合、 **Microsoft.XLANGs.BaseTypes.TransportType**フィールドで、既定では、BizTalk エンジンを使用して、HTTP アダプター。  
  
- **WCF です。BindingType**名前によってバインディングを識別します。 次のいずれかを指定できます。  
  
  - basicHttpBinding  
  
  - customBinding  
  
  - netMsmqBinding  
  
  - netNamedPipeBinding  
  
  - netTcpBinding  
  
  - wsFederationHttpBinding  
  
  - wsHttpBinding  
  
    上の一覧は、拡張できます。 たとえば、FtpBinding などの独自のバインドを一覧に追加できます。  
  
- **WCF です。BindingConfiguration**のバインドの種類のバインド構成を指定します。 このプロパティは、コンピュータの構成ファイルに登録されているバインドを受け取ります。 WCF 構成ファイルのバインド構成で使用される形式と同じ形式の XML 構成ファイルも受け取ります。  
  
- 追加の WCF プロパティの指定が必要になる場合があります。 入力**WCF**式エディターで IntelliSense 機能がすべての利用可能なコンテキスト プロパティを一覧する必要があります。 WCF コンテキスト プロパティの詳細については、[WCF アダプター プロパティ スキーマおよびプロパティ](../core/wcf-adapters-property-schema-and-properties.md)を参照してください。  
  
  上記の例は、構成する方法を示す**WCF です。アクション**1 つのアクションを使用します。 複数アクションのマッピング シナリオの場合、WCF アダプタは、動的送信ポートでの複数アクションのマッピングの使用をサポートしていません。 設定できるは、実際のアクションだけ、 **WCF です。アクション**コンテキスト プロパティの上に示すようにします。  
  
## <a name="see-also"></a>参照  
 [送信アダプターの wcf SOAP アクションの指定](../core/specifying-soap-actions-for-wcf-send-adapters.md)   
 [動的ポートに値を割り当てる式を使用する方法](../core/how-to-use-expressions-to-assign-values-to-dynamic-ports.md)   
 [ポートのバインド](../core/port-bindings.md)