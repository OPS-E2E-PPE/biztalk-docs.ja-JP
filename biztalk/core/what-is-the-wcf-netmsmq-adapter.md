---
title: "WCF-NetMsmq アダプタについて | Microsoft Docs"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: WCF-NetMsmq adapters, about WCF-NetMsmq adapters
ms.assetid: 506c5e2d-6cbe-4788-8e37-49d009dc559a
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1008cc7178c38532f1781890080eacf4b5dfb56c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="what-is-the-wcf-netmsmq-adapter"></a>WCF-NetMsmq アダプタについて
WCF-NetMsmq アダプタは、サービスとクライアントの両方が WCF ベースである環境でキュー テクノロジを使用して、接続が切断されたコンピュータ間の通信を実現します。 このアダプタはメッセージ キュー (MSMQ) トランスポートを使用し、メッセージではバイナリ エンコードを使用します。  
  
 次の表に、WCF-NetMsmq アダプタの特性をまとめます。  
  
|Description|特性|  
|-----------------|--------------------|  
|相互運用性レベル|.NET プロファイル|  
|[メッセージ エンコード]|Binary|  
|[境界]|コンピュータ間|  
|トランスポート プロトコル|MSMQ (MSMQ)|  
|[セキュリティ モード]|なし、メッセージ、トランスポート、および両方|  
|クライアント認証のメカニズム|トランスポート セキュリティとメッセージ セキュリティ|  
|WS-ReliableMessaging のサポート|適用なし|  
|WS-AtomicTransaction のサポート|はい|  
|一方向メッセージングのサポート|はい|  
|双方向メッセージングのサポート|不可|  
|受信アダプタのホストの種類|インプロセス|  
|送信アダプタのホストの種類|インプロセス|  
  
> [!NOTE]
>  WCF-NetMsmq 受信アダプタによるメッセージの抽出元のキューを事前に作成しておく必要があります。 キュー内のメッセージは WCF ベースである必要があります。それ以外の場合、これらのメッセージは配信不能キューに送信されます。  
  
 WCF-NetMsmq アダプタは、2 つのアダプタ (受信アダプタと送信アダプタ) で構成されます。  
  
 **Wcf-netmsmq 受信アダプター**  
  
 WCF-NetMsmq 受信アダプタは、MSMQ 経由で WCF サービス要求を受信するために使用します。 WCF-NetMsmq 受信アダプタを使用する受信場所は、一方向の受信場所としてのみ構成できます。  
  
 **Wcf-netmsmq 送信アダプター**  
  
 WCF-NetMsmq 送信アダプタは、MSMQ 経由で型宣言が不要なコントラクトを使用して WCF サービスを呼び出すために使用します。  
  
 WCF の詳細については、受信し送信アダプターを参照してください[WCF アダプタは何ですか?](../core/what-are-the-wcf-adapters.md)です。  
  
## <a name="see-also"></a>参照  
 [Wcf-netmsmq アダプタを構成します。](../core/configuring-the-wcf-netmsmq-adapter.md)   
 [WCF アダプタ](../core/wcf-adapters.md)