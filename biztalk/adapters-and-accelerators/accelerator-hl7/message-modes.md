---
title: メッセージ モード |Microsoft Docs
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
ms.openlocfilehash: a0480d4742076b0c99b29a6f34054cf713e09bf2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65303767"
---
# <a name="message-modes"></a>メッセージ モード
すべての HL7 メッセージの基になる 2 つの基本的な概念があります。 これらの概念はアドレス データを交換する独立したシステムの相互作用し、分散医療システム内で時間の経過と共に相互運用性の要件をサポートする構造を提供する、さまざまな方法です。 以下に示す概念は、HL7 デザインの背後にある基になるテーマを定義します。  
  
- **メッセージ モード**します。 情報交換の 3 つの基本的な目的の認識: (interrogative) 情報を要求する (宣言型)、情報をブロードキャストして、システム操作の実行 (命令型) を要求します。 それぞれの目的は、その特定の要件とメッセージ フローのパターン。  
  
- **受信確認モード**します。 疎と緊密をサポートする必要性には、メッセージングのスタイルが結合されています。 HL7 の受信確認のモードでは、受信者からの応答を必要とするか、メッセージ配信を保証するために、基になるネットワークを有効にする、送信元アプリケーションが有効にします。  
  
- **ローカリゼーション**します。 メッセージの仕様にサイト固有の資料を紹介するエンティティを許可することで特定のローカルの要件をサポートするために必要です。  
  
- **進化**します。 Standard のバージョン間の相互運用性を有効にすると、多くのインターフェイスと、多くのアプリケーションのサイトをサポートするために必要です。 これにより、すべてのインターフェイスを同時にアップグレードを必要とするのではなく、ステージ インターフェイスのアップグレードにエンティティができます。  
  
  Microsoft BizTalk Accelerator for HL7 の次の関数 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 上記の要件をサポートします。  
  
- HL7 の受信確認モード。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] アプリケーションの受信確認を元のメッセージの送信者に渡すことによって、元の受信確認のモードをサポートしています。  
  
- さまざまなメッセージング モード。 これにより、複数の送信先へのブロードキャストと関連付けられているクエリの応答にクエリを連結します。  
  
- などの XML エンコーディングをパイプで区切られた複数のバージョンのサポート。  
  
- さまざまな環境を有効にする HL7 バージョンとアップグレードの間のマッピング。  
  
- オーケストレーション内でのローカライズ (カスタマイズ)。  
  
- デバッグと新しいインターフェイスの評価をサポートするツールです。  
  
## <a name="see-also"></a>参照  
 [HL7 メッセージの処理](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md)   
 [HL7 2.X スキーマの使用](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)   
 [HL7 2. XML スキーマの使用](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-xml-schemas.md)   
 [メッセージの種類とイベント](../../adapters-and-accelerators/accelerator-hl7/message-types-and-events.md)   
 [HL7 メッセージング](../../adapters-and-accelerators/accelerator-hl7/hl7-messaging.md)