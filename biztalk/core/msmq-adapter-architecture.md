---
title: "MSMQ アダプターのアーキテクチャ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- architecture, MSMQ adapters
- MSMQ adapters, architecture
ms.assetid: acecc2a4-0670-487e-be39-28a24c8c3f16
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bd314b6f835568b6336121478268b84381a288ff
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="msmq-adapter-architecture"></a>MSMQ アダプターのアーキテクチャ
MSMQ アダプターを使用すると、Microsoft メッセージ キュー (MSMQ) の機能を利用できます。MSMQ の機能は MSMQ アダプターを使用しない限り、BizTalk Server で使用することはできません。  
  
## <a name="adapter-structure"></a>アダプターの構造  
 MSMQ アダプターは、他の BizTalk アダプターと同じ構造で、アダプター フレームワークを使用します。 このアダプターは、デザイン時コンポーネントと実行時コンポーネントで構成されています。 実行時コンポーネントには、メッセージ トランスポートを実装する要素が含まれています。  
  
 デザイン時コンポーネントを使用すると、アダプターのプロパティを送受信用に構成できます。  
  
 実行時コンポーネントは、デザイン時に定義されたキューにメッセージを送信したり、指定されたキューからメッセージを受信できます。 アダプター ランタイムは、BizTalk Server アプリケーションと同じプロセスで実行され、分離ホストでは実行されません。  
  
 すべてのメッセージ処理は、リモート キューの場合でも、ローカルのメッセージ キュー サービスに依存します。 リモート キューの場合、アダプターはローカルのメッセージ キュー サービスにメッセージを送信します。 その次に、そのメッセージをリモート キューに送信します。  
  
 送信の完全な一覧については、構成プロパティを受信したりを参照してください[MSMQ 送信ポートを構成する方法](../core/how-to-configure-an-msmq-send-port.md)と[、MSMQ 受信場所を構成する方法](../core/how-to-configure-an-msmq-receive-location.md)です。  
  
 メッセージ キューの詳細については、Microsoft TechNet ライブラリで次のトピックを参照してください。  
  
-   **メッセージ キューの設計ガイド**で[http://go.microsoft.com/fwlink/?LinkId=137080](http://go.microsoft.com/fwlink/?LinkId=137080)です。  
  
-   **メッセージ キューの操作ガイド**で[http://go.microsoft.com/fwlink/?LinkId=137079](http://go.microsoft.com/fwlink/?LinkId=137079)です。  
  
-   **メッセージ キューのトラブルシューティング ガイド**で[http://go.microsoft.com/fwlink/?LinkId=137081](http://go.microsoft.com/fwlink/?LinkId=137081)です。  
  
-   **メッセージ キューのテクニカル リファレンス**で[http://go.microsoft.com/fwlink/?LinkId=137082](http://go.microsoft.com/fwlink/?LinkId=137082)です。  
  
## <a name="see-also"></a>参照  
 [MSMQ アダプターとは何ですか。](../core/what-is-the-msmq-adapter.md)