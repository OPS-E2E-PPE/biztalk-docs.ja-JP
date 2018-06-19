---
title: モードをメッセージ |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- message modes, about message modes
- messages, message modes
- message modes, HL7 messages
ms.assetid: 2d832b67-6f0e-45e1-95ac-cb80b74a7831
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b09a610d000ae6beaef75b1ed0144d1597d517b8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22205058"
---
# <a name="message-modes"></a>メッセージ モード
HL7 のすべてのメッセージの基になる 2 つの基本的な概念があります。 これらの概念はアドレス データを交換する独立したシステムの相互作用し、分散医療システム内で時間の経過と共に相互運用性の要件をサポートする構造を提供する、さまざまな方法です。 以下に示す概念は、HL7 デザインの背後にある、基になるテーマを定義します。  
  
-   **メッセージ モード**です。 情報交換用の 3 つの基本的な目的の認識: 要求の情報 (interrogative) に情報を (宣言) をブロードキャストして、システムのアクションを実行 (強制) を要求します。 それぞれの目的は、その特定の要件とメッセージ フローのパターン。  
  
-   **受信確認モード**です。 緊密にし、疎をサポートするために必要では、メッセージングのスタイルが結合されています。 HL7 の受信確認応答モードでは、受信側からの応答を必要とするか、メッセージ配信を保証するために、基になるネットワークを有効にする、送信元アプリケーションが有効にします。  
  
-   **ローカリゼーション**です。 メッセージの仕様にサイト固有の情報を紹介するエンティティを許可することで、ローカルの特定の要件をサポートするために必要です。  
  
-   **進化**です。 標準のバージョン間の相互運用性を有効にすると、多くのインターフェイスと多くのアプリケーションのサイトをサポートするために必要です。 これにより、すべてのインターフェイスの同時アップグレードを必要とするのではなく、段階インターフェイスのアップグレードにエンティティです。  
  
 次の関数の[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 上記の要件をサポートします。  
  
-   HL7 受信確認モード。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]アプリケーションの受信確認を元のメッセージの送信者に渡すことによって、元の受信確認モードをサポートしています。  
  
-   さまざまなメッセージング モード。 これにより、複数の送信先にブロードキャストを有効にされ、関連付けられているクエリの応答にクエリを関連付けます。  
  
-   XML エンコーディングのパイプで区切られたなど、複数のバージョンをサポートします。  
  
-   さまざまな環境を有効にする HL7 バージョンとアップグレードの間のマッピング。  
  
-   オーケストレーション内でのローカライズ (カスタマイズ)。  
  
-   デバッグと新しいインターフェイスの評価をサポートするツールです。  
  
## <a name="see-also"></a>参照  
 [HL7 メッセージの処理](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md)   
 [HL7 2.X スキーマの使用](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)   
 [HL7 2. XML スキーマを使用します。](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-xml-schemas.md)   
 [メッセージの種類およびイベント](../../adapters-and-accelerators/accelerator-hl7/message-types-and-events.md)   
 [HL7 メッセージ](../../adapters-and-accelerators/accelerator-hl7/hl7-messaging.md)