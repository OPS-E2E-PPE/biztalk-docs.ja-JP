---
title: "SWIFT 送信アダプターのアーキテクチャ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e52a5a21-0aa1-4cd9-a2a4-f9df425913a0
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9d772203c980495c5aa62266beb060693c1a8ad8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="swift-send-adapter-architecture"></a>SWIFT 送信アダプターのアーキテクチャ
一般に、BizTalk Server 送信アダプターは BizTalk サービス プロセス Btsntsvc.exe でホストされます。 これは、BizTalk Server が、アダプターの有効期間を管理することを意味します。  
  
 SWIFT ネットワークへのメッセージ送信の 2 つの方法: 同期 (ExchangeRequest) と非同期 (このリリースでは実装されていません)。 BizTalk Server で、送信アダプターは、BizTalk メッセージング エンジンと対話する次の通信パターンをサポートする必要があります。  
  
-   応答を送信請求-SWIFT ネットワークとのプリミティブと呼ばれる、対でメッセージを交換します。 SWIFT に送信されたメッセージは、これは、ビジネス、受信確認またはエラー応答があります。 メッセージ ボックスには、応答メッセージが送信されます。 この操作モードは、リアルタイムの通信に使用されます。  
  
-   一方向送信 — 1 つの方法で構成されている場合、アダプターはストアと転送モードで動作します。 メッセージは、受信者ではなく、事前に構成されたキューに送信されます。 送信者は、プッシュまたはプル モードでキューにセッションを開くことによって、応答を取得できます。  
  
> [!NOTE]
>  アダプターを作成する方法では、動作方法に影響します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [SWIFT 送信アダプター URI](../../adapters-and-accelerators/fileact-interact/swift-send-adapter-uri.md)  
  
-   [SWIFT 送信アダプターの動的送信](../../adapters-and-accelerators/fileact-interact/swift-send-adapter-dynamic-send.md)  
  
-   [SWIFT 送信アダプターの初期化](../../adapters-and-accelerators/fileact-interact/swift-send-adapter-initialization.md)  
  
-   [SWIFT 送信アダプター同期モード](../../adapters-and-accelerators/fileact-interact/swift-send-adapter-synchronous-mode.md)  
  
-   [SWIFT 送信アダプターの終了](../../adapters-and-accelerators/fileact-interact/swift-send-adapter-termination.md)