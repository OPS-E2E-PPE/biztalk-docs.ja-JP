---
title: Wcf-nettcp アダプターとは何ですか。 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF-NetTcp adapters, about WCF-NetTcp adapters
ms.assetid: 94dc24df-19a1-4701-9012-59d05b0c8abd
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: da209ab45dbb9458cd6be0d2e988fac7ea9270f9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65242846"
---
# <a name="what-is-the-wcf-nettcp-adapter"></a>Wcf-nettcp アダプターとは何ですか。
Wcf-nettcp アダプターは、環境でサービスとクライアントの両方が WCF ベースで接続されているコンピュータ間またはプロセス間の通信を提供します。 このアダプタからは、SOAP セキュリティ、信頼性、およびトランザクションの各機能にフル アクセスできます。 このアダプタは、TCP トランスポートを使用し、メッセージではバイナリ エンコードを使用します。  
  
 次の表では、Wcf-nettcp アダプタの特性をまとめたものです。  
  
|説明|特性|  
|-----------------|--------------------|  
|相互運用性レベル|.NET プロファイル|  
|[メッセージ エンコード]|Binary|  
|[境界]|コンピュータ間またはプロセス間|  
|トランスポート プロトコル|TCP|  
|[セキュリティ モード]|None、メッセージ、トランスポート、および TransportWithMessageCredential します。|  
|クライアント認証のメカニズム|トランスポート セキュリティとメッセージ セキュリティ|  
|WS-ReliableMessaging のサポート|いいえ|  
|WS-AtomicTransaction のサポート|はい|  
|一方向メッセージングのサポート|はい|  
|双方向メッセージングのサポート|はい|  
|受信アダプタのホストの種類|インプロセス|  
|送信アダプタのホストの種類|インプロセス|  
  
 Wcf-nettcp アダプターは、2 つのアダプターで構成されます-受信アダプタと送信アダプター。  
  
 **Wcf-nettcp 受信アダプター**  
  
 WCF-NetTcp を使用する受信アダプタは、TCP プロトコルを介して WCF サービス要求を受信します。 Wcf-nettcp 受信アダプタを使用する受信場所は、一方向として構成できますまたは要求-応答 (双方向)。  
  
 **Wcf-nettcp 送信アダプター**  
  
 Wcf-nettcp 送信アダプターを使用して、TCP プロトコルを使用して、型宣言不要なコントラクトを介して WCF サービスを呼び出します。  
  
 WCF の詳細については、受信し送信アダプターを参照してください[WCF アダプタは何ですか?](../core/what-are-the-wcf-adapters.md)します。  
  
## <a name="see-also"></a>参照  
 [Wcf-nettcp アダプターを構成します。](../core/configuring-the-wcf-nettcp-adapter.md)   
 [WCF アダプター](../core/wcf-adapters.md)