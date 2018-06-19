---
title: Wcf-netnamedpipe アダプタとは何ですか。 | Microsoft Docs
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
ms.openlocfilehash: 43c73a670139690c4a27d4784c6ad23225492f17
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22289250"
---
# <a name="what-is-the-wcf-netnamedpipe-adapter"></a>Wcf-netnamedpipe アダプタとは何ですか。
WCF-NetNamedPipe アダプタは、サービスとクライアントの両方が WCF ベースである環境において、同一コンピュータ上でのプロセス間通信を可能にします。 このアダプタからは、SOAP の信頼性機能とトランザクション機能にフル アクセスできます。 このアダプタでは名前付きパイプ トランスポートが使用され、メッセージではバイナリ エンコードが使用されます。 コンピュータ間通信ではこのアダプタを使用できません。  
  
 次の表に、WCF-NetNamedPipe アダプタの特性をまとめます。  
  
|Description|特性|  
|-----------------|--------------------|  
|相互運用性レベル|.NET プロファイル|  
|[メッセージ エンコード]|Binary|  
|[境界]|プロセス間|  
|トランスポート プロトコル|名前付きパイプ|  
|[セキュリティ モード]|なしおよびトランスポート|  
|クライアント認証のメカニズム|トランスポート セキュリティとメッセージ セキュリティ|  
|WS-ReliableMessaging のサポート|不可|  
|WS-AtomicTransaction のサポート|はい|  
|一方向メッセージングのサポート|はい|  
|双方向メッセージングのサポート|はい|  
|受信アダプタのホストの種類|インプロセス|  
|送信アダプタのホストの種類|インプロセス|  
  
 WCF-NetNamedPipe アダプタは、受信アダプタと送信アダプタの 2 つのアダプタで構成されます。  
  
 **Wcf-netnamedpipe 受信アダプター**  
  
 WCF-NetNamedPipe 受信アダプタは、名前付きパイプ トランスポート経由で WCF サービス要求を受信するのに使用します。 WCF-NetNamedPipe 受信アダプタを使用する受信場所は、一方向または要求 - 応答 (双方向) として構成できます。  
  
 **Wcf-netnamedpipe 送信アダプター**  
  
 WCF-NetNamedPipe 送信アダプタは、名前付きパイプ トランスポート経由で型宣言が不要なコントラクトを使用して WCF サービスを呼び出すのに使用します。  
  
 WCF の詳細については、受信し送信アダプターを参照してください[WCF アダプタは何ですか?](../core/what-are-the-wcf-adapters.md)です。  
  
## <a name="see-also"></a>参照  
 [Wcf-netnamedpipe アダプタを構成します。](../core/configuring-the-wcf-netnamedpipe-adapter.md)   
 [WCF アダプタ](../core/wcf-adapters.md)