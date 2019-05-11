---
title: SWIFT 送信アダプターのアーキテクチャ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e52a5a21-0aa1-4cd9-a2a4-f9df425913a0
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a4347680cf4fa1434e72e80c74debe0ca2de8d47
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65364182"
---
# <a name="swift-send-adapter-architecture"></a>SWIFT 送信アダプターのアーキテクチャ
一般に、BizTalk Server 送信アダプターは、BizTalk サービス プロセス Btsntsvc.exe でホストされます。 これは、BizTalk Server がアダプターの有効期間を管理することを意味します。  
  
 SWIFT ネットワークへのメッセージ送信の 2 つの方法: 同期 (ExchangeRequest) と非同期 (このリリースでは実装されていません)。 BizTalk Server で、送信アダプターは、BizTalk メッセージング エンジンと対話する次の通信パターンをサポートする必要があります。  
  
-   応答の送信請求-SWIFT ネットワークと、プリミティブと呼ばれる、ペアで交換されるメッセージ。 SWIFT へ送信されたメッセージは、これは、ビジネス、受信確認またはエラー応答があります。 応答メッセージは、メッセージ ボックスに送信されます。 この操作モードでは、リアルタイム通信に使用されます。  
  
-   一方向の送信: 1 つの方法で構成されている場合、アダプターは、ストアと転送モードで動作します。 メッセージは、事前構成済みのキューの受信者とは対照的に送信されます。 送信者は、プッシュまたはプル モードでのキューでセッションを開いて、応答を取得できます。  
  
> [!NOTE]
>  アダプターを作成する方法は、動作方法に影響します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [SWIFT 送信アダプターの URI](../../adapters-and-accelerators/fileact-interact/swift-send-adapter-uri.md)  
  
-   [SWIFT 送信アダプターの動的送信](../../adapters-and-accelerators/fileact-interact/swift-send-adapter-dynamic-send.md)  
  
-   [SWIFT 送信アダプターの初期化](../../adapters-and-accelerators/fileact-interact/swift-send-adapter-initialization.md)  
  
-   [SWIFT 送信アダプターの同期モード](../../adapters-and-accelerators/fileact-interact/swift-send-adapter-synchronous-mode.md)  
  
-   [SWIFT 送信アダプターの終了](../../adapters-and-accelerators/fileact-interact/swift-send-adapter-termination.md)