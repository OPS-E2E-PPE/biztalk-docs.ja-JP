---
title: Wcf-netnamedpipe アダプターとは何ですか。 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF-NetNamedPipe adapters, about WCF-NetNamedPipe adapters
ms.assetid: b9f84256-e49d-4ee2-b0fa-d3f692ade1d4
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 01672c8babf30c99b8ba4d31069c836a46b18630
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65242745"
---
# <a name="what-is-the-wcf-netnamedpipe-adapter"></a>Wcf-netnamedpipe アダプターとは何ですか。
Wcf-netnamedpipe アダプターは、環境でサービスとクライアントの両方が WCF ベースで同じコンピューター上のプロセス間通信を提供します。 SOAP の信頼性とトランザクションの機能へのフル アクセスを提供します。 アダプターが、名前付きパイプ トランスポートを使用し、メッセージはバイナリ エンコードします。 このアダプターは、コンピュータ間通信で使用することはできません。  
  
 次の表では、Wcf-netnamedpipe アダプタの特性をまとめたものです。  
  
|説明|特性|  
|-----------------|--------------------|  
|相互運用性レベル|.NET プロファイル|  
|[メッセージ エンコード]|Binary|  
|[境界]|プロセス間|  
|トランスポート プロトコル|名前付きパイプ|  
|[セキュリティ モード]|[なし] とトランスポート|  
|クライアント認証のメカニズム|トランスポート セキュリティとメッセージ セキュリティ|  
|WS-ReliableMessaging のサポート|いいえ|  
|WS-AtomicTransaction のサポート|はい|  
|一方向メッセージングのサポート|はい|  
|双方向メッセージングのサポート|はい|  
|受信アダプタのホストの種類|インプロセス|  
|送信アダプタのホストの種類|インプロセス|  
  
 Wcf-netnamedpipe アダプターは、2 つのアダプターで構成されます-受信アダプタと送信アダプター。  
  
 **Wcf-netnamedpipe 受信アダプター**  
  
 使用して、Wcf-netnamedpipe 受信アダプタは、名前付きパイプ トランスポート経由で WCF サービス要求を受信します。 Wcf-netnamedpipe 受信アダプタを使用する受信場所は、一方向として構成できますまたは要求-応答 (双方向)。  
  
 **Wcf-netnamedpipe 送信アダプター**  
  
 Wcf-netnamedpipe 送信アダプターを使用して、名前付きパイプ トランスポート経由で型宣言不要なコントラクトを介して WCF サービスを呼び出します。  
  
 WCF の詳細については、受信し送信アダプターを参照してください[WCF アダプタは何ですか?](../core/what-are-the-wcf-adapters.md)します。  
  
## <a name="see-also"></a>参照  
 [Wcf-netnamedpipe アダプターの構成](../core/configuring-the-wcf-netnamedpipe-adapter.md)   
 [WCF アダプター](../core/wcf-adapters.md)