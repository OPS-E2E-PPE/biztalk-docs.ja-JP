---
title: "WCF-NetTcp アダプタについて | Microsoft Docs"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: WCF-NetTcp adapters, about WCF-NetTcp adapters
ms.assetid: 94dc24df-19a1-4701-9012-59d05b0c8abd
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a741d3a4d7b7bcc80405d0fc25e37a31860523b9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="what-is-the-wcf-nettcp-adapter"></a>WCF-NetTcp アダプタについて
WCF-NetTcp アダプタは、サービスとクライアントの両方が WCF ベースである環境において、コンピュータ間またはプロセス間の接続通信を実現します。 このアダプタからは、SOAP セキュリティ、信頼性、およびトランザクションの各機能にフル アクセスできます。 このアダプタは、TCP トランスポートを使用し、メッセージではバイナリ エンコードを使用します。  
  
 次の表に、WCF-NetTcp アダプタの特性をまとめます。  
  
|Description|特性|  
|-----------------|--------------------|  
|相互運用性レベル|.NET プロファイル|  
|[メッセージ エンコード]|Binary|  
|[境界]|コンピュータ間またはプロセス間|  
|トランスポート プロトコル|TCP|  
|[セキュリティ モード]|None、Message、Transport、および TransportWithMessageCredential|  
|クライアント認証のメカニズム|トランスポート セキュリティとメッセージ セキュリティ|  
|WS-ReliableMessaging のサポート|不可|  
|WS-AtomicTransaction のサポート|はい|  
|一方向メッセージングのサポート|はい|  
|双方向メッセージングのサポート|はい|  
|受信アダプタのホストの種類|インプロセス|  
|送信アダプタのホストの種類|インプロセス|  
  
 WCF-NetTcp アダプタは、2 つのアダプタ (受信アダプタと送信アダプタ) で構成されます。  
  
 **Wcf-nettcp 受信アダプター**  
  
 WCF-NetTcp 受信アダプタを使用すると、TCP プロトコルを介して WCF サービス要求を受信できます。 WCF-NetTcp 受信アダプタを使用する受信場所は、一方向または要求 - 応答 (双方向) として構成できます。  
  
 **Wcf-nettcp 送信アダプター**  
  
 WCF-NetTcp 送信アダプタを使用すると、TCP プロトコルを使用して、型宣言が不要なコントラクトを介して WCF サービスを呼び出すことができます。  
  
 WCF の詳細については、受信し送信アダプターを参照してください[WCF アダプタは何ですか?](../core/what-are-the-wcf-adapters.md)です。  
  
## <a name="see-also"></a>参照  
 [Wcf-nettcp アダプターを構成します。](../core/configuring-the-wcf-nettcp-adapter.md)   
 [WCF アダプタ](../core/wcf-adapters.md)