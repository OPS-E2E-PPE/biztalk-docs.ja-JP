---
title: WCF-WSHttp アダプタについて | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF-WSHttp adapters, about WCF-WSHttp adapters
ms.assetid: 183a19e3-10b1-403f-b274-34a441e774d1
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eb5d244dcfe26cf10bc4ae10c63374eef0824444
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22289338"
---
# <a name="what-is-the-wcf-wshttp-adapter"></a>WCF-WSHttp アダプタについて
WCF-WSHttp アダプタを使用すると、テキストまたは Message Transmission Optimization Mechanism (MTOM) エンコードによる HTTP または HTTPS トランスポートを使用して、次世代 Web サービス標準を理解できるサービスおよびクライアントとコンピュータ間通信を実行できます。 WCF-WSHttp アダプタにより、SOAP セキュリティ、信頼性、およびトランザクションの各機能にフル アクセスできます。  
  
 次の表に、WCF-WSHttp アダプタの特性をまとめます。  
  
|Description|特性|  
|-----------------|--------------------|  
|相互運用性レベル|WS-Profile|  
|[メッセージ エンコード]|テキストまたは MTOM|  
|[境界]|コンピュータ間|  
|トランスポート プロトコル|HTTP または HTTPS|  
|[セキュリティ モード]|None、Message、Transport、および TransportWithMessageCredential|  
|クライアント認証のメカニズム|トランスポート セキュリティとメッセージ セキュリティ|  
|WS-ReliableMessaging のサポート|不可|  
|WS-AtomicTransaction のサポート|はい|  
|一方向メッセージングのサポート|はい|  
|双方向メッセージングのサポート|はい|  
|受信アダプタのホストの種類|分離されます。|  
|送信アダプタのホストの種類|インプロセス|  
  
 WCF-WSHttp アダプタは、受信アダプタと送信アダプタの 2 つのアダプタで構成されます。  
  
 **Wcf-wshttp 受信アダプター**  
  
 WCF-WSHttp 受信アダプタを使用すると、HTTP プロトコルまたは HTTPS プロトコルを介して WCF サービス要求を受信できます。 WCF-WSHttp 受信アダプタを使用する受信場所は、一方向または要求 - 応答 (双方向) として構成できます。  
  
 **Wcf-wshttp 送信アダプター**  
  
 WCF-WSHttp 送信アダプタを使用すると、HTTP プロトコルまたは HTTPS プロトコルを使用して、型宣言が不要なコントラクトを介して WCF サービスを呼び出すことができます。  
  
 WCF の詳細については、受信し送信アダプターを参照してください[WCF アダプタは何ですか?](../core/what-are-the-wcf-adapters.md)です。  
  
## <a name="see-also"></a>参照  
 [Wcf-wshttp アダプタを構成します。](../core/configuring-the-wcf-wshttp-adapter.md)   
 [WCF アダプタ](../core/wcf-adapters.md)