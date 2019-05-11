---
title: Wcf-netmsmq アダプターとは何ですか。 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF-NetMsmq adapters, about WCF-NetMsmq adapters
ms.assetid: 506c5e2d-6cbe-4788-8e37-49d009dc559a
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ba6cfcba8858e894b83b5ec45fcd51406db93fcc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65242787"
---
# <a name="what-is-the-wcf-netmsmq-adapter"></a>Wcf-netmsmq アダプターとは何ですか。
Wcf-netmsmq アダプタは、サービスとクライアントの両方が WCF ベースの環境でキュー テクノロジを使用して、切断されているコンピュータ間の通信を提供します。 メッセージ キュー (MSMQ) トランスポートを使用して、メッセージはバイナリ エンコードします。  
  
 次の表では、Wcf-netmsmq アダプタの特性をまとめたものです。  
  
|説明|特性|  
|-----------------|--------------------|  
|相互運用性レベル|.NET プロファイル|  
|[メッセージ エンコード]|Binary|  
|[境界]|コンピュータ間|  
|トランスポート プロトコル|MSMQ (MSMQ)|  
|[セキュリティ モード]|None、メッセージ、トランスポート、および両方。|  
|クライアント認証のメカニズム|トランスポート セキュリティとメッセージ セキュリティ|  
|WS-ReliableMessaging のサポート|適用なし|  
|WS-AtomicTransaction のサポート|はい|  
|一方向メッセージングのサポート|はい|  
|双方向メッセージングのサポート|いいえ|  
|受信アダプタのホストの種類|インプロセス|  
|送信アダプタのホストの種類|インプロセス|  
  
> [!NOTE]
>  Wcf-netmsmq 受信アダプターによるメッセージの抽出を元のキューは、事前に作成する必要があります。 キュー内のメッセージが WCF ベース; にある必要があります。それ以外の場合、これらのメッセージを配信不能キューに送信されます。  
  
 Wcf-netmsmq アダプターは、2 つのアダプターで構成されます-受信アダプタと送信アダプター。  
  
 **Wcf-netmsmq 受信アダプター**  
  
 Wcf-netmsmq を使用する受信アダプターを MSMQ 経由で WCF サービス要求を受信します。 Wcf-netmsmq 受信アダプタを使用する受信場所は、一方向の受信としてのみ構成できます。  
  
 **Wcf-netmsmq 送信アダプター**  
  
 Wcf-netmsmq 送信アダプターを使用して、MSMQ 経由で型宣言不要なコントラクトを介して WCF サービスを呼び出します。  
  
 WCF の詳細については、受信し送信アダプターを参照してください[WCF アダプタは何ですか?](../core/what-are-the-wcf-adapters.md)します。  
  
## <a name="see-also"></a>参照  
 [Wcf-netmsmq アダプターを構成します。](../core/configuring-the-wcf-netmsmq-adapter.md)   
 [WCF アダプター](../core/wcf-adapters.md)