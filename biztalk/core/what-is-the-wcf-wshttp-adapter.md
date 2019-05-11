---
title: Wcf-wshttp アダプターとは何ですか。 | Microsoft Docs
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
ms.openlocfilehash: d3d82d26e03163d856bc4ce9d0cc8d948d07e54a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65242803"
---
# <a name="what-is-the-wcf-wshttp-adapter"></a>Wcf-wshttp アダプターとは何ですか。
Wcf-wshttp アダプターを使用してサービスとクライアントは、テキストまたは Message Transmission Optimization Mechanism (HTTP または HTTPS トランスポートを使用して、次世代 Web サービス標準が理解できると、コンピューター間の通信を行うことができます。MTOM) エンコードです。 Wcf-wshttp アダプタは、SOAP セキュリティ、信頼性、およびトランザクションの各機能へのフル アクセスを提供します。  
  
 次の表では、Wcf-wshttp アダプタの特性をまとめたものです。  
  
|説明|特性|  
|-----------------|--------------------|  
|相互運用性レベル|WS プロファイル|  
|[メッセージ エンコード]|テキストまたは MTOM|  
|[境界]|コンピュータ間|  
|トランスポート プロトコル|HTTP または HTTPS|  
|[セキュリティ モード]|None、メッセージ、トランスポート、および TransportWithMessageCredential します。|  
|クライアント認証のメカニズム|トランスポート セキュリティとメッセージ セキュリティ|  
|WS-ReliableMessaging のサポート|いいえ|  
|WS-AtomicTransaction のサポート|はい|  
|一方向メッセージングのサポート|はい|  
|双方向メッセージングのサポート|はい|  
|受信アダプタのホストの種類|分離されます。|  
|送信アダプタのホストの種類|インプロセス|  
  
 Wcf-wshttp アダプターは、2 つのアダプターで構成されます-受信アダプタと送信アダプター。  
  
 **Wcf-wshttp 受信アダプター**  
  
 Wcf-wshttp を使用する受信アダプタは、HTTP または HTTPS プロトコルを介して WCF サービス要求を受信します。 Wcf-wshttp 受信アダプタを使用する受信場所は、一方向として構成できますまたは要求-応答 (双方向)。  
  
 **Wcf-wshttp 送信アダプター**  
  
 Wcf-wshttp 送信アダプターを使用すると、HTTP または HTTPS プロトコルを使用して、型宣言不要なコントラクトを介して WCF サービスを呼び出します。  
  
 WCF の詳細については、受信し送信アダプターを参照してください[WCF アダプタは何ですか?](../core/what-are-the-wcf-adapters.md)します。  
  
## <a name="see-also"></a>参照  
 [Wcf-wshttp アダプタの構成](../core/configuring-the-wcf-wshttp-adapter.md)   
 [WCF アダプター](../core/wcf-adapters.md)