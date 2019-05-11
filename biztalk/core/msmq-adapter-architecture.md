---
title: MSMQ アダプターのアーキテクチャ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- architecture, MSMQ adapters
- MSMQ adapters, architecture
ms.assetid: acecc2a4-0670-487e-be39-28a24c8c3f16
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1445907a98b6e86ae898015d131b0a5f892351a0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65263643"
---
# <a name="msmq-adapter-architecture"></a>MSMQ アダプターのアーキテクチャ
MSMQ アダプターでは、それ以外の場合、BizTalk Server で使用できるはない Microsoft メッセージ キュー (MSMQ とも呼ばれます) 機能を活用できます。  
  
## <a name="adapter-structure"></a>アダプターの構造  
 MSMQ アダプターは、他の BizTalk アダプターと同じ構造を備え、アダプター フレームワークを使用します。 これについては、デザイン時コンポーネントと実行時コンポーネントの構成されます。 実行時コンポーネントには、さらに、メッセージ トランスポートを実装する要素が含まれています。  
  
 デザイン時コンポーネントを使用して、送信と受信アダプターのプロパティを構成できます。  
  
 実行時コンポーネントでは、デザイン時に定義されたキューにメッセージを送信したり、指定されたキューからメッセージを受信することができます。 アダプター ランタイムは、BizTalk Server アプリケーションと同じプロセスで実行され、分離ホストでは実行されません。  
  
 すべてのメッセージ処理は、ローカル メッセージ キュー サービス、リモート キューにも依存します。 リモート キューの場合、アダプターはメッセージをローカルのメッセージ キュー サービスに渡します。 さらに、リモート キューにメッセージを送信します。  
  
 送信の完全な一覧については、構成プロパティを受信したりを参照してください[MSMQ 送信ポートを構成する方法](../core/how-to-configure-an-msmq-send-port.md)と[、MSMQ 受信場所を構成する方法](../core/how-to-configure-an-msmq-receive-location.md)します。  
  
 メッセージ キューの詳細については、Microsoft TechNet ライブラリには次のトピックを参照してください。  
  
-   **メッセージ キュー設計ガイド**で[ http://go.microsoft.com/fwlink/?LinkId=137080](http://go.microsoft.com/fwlink/?LinkId=137080)します。  
  
-   **メッセージ キュー操作ガイド**で[ http://go.microsoft.com/fwlink/?LinkId=137079](http://go.microsoft.com/fwlink/?LinkId=137079)します。  
  
-   **メッセージ キュー トラブルシューティング ガイド**で[ http://go.microsoft.com/fwlink/?LinkId=137081](http://go.microsoft.com/fwlink/?LinkId=137081)します。  
  
-   **メッセージ キュー テクニカル リファレンス**で[ http://go.microsoft.com/fwlink/?LinkId=137082](http://go.microsoft.com/fwlink/?LinkId=137082)します。  
  
## <a name="see-also"></a>参照  
 [MSMQ アダプターについて](../core/what-is-the-msmq-adapter.md)