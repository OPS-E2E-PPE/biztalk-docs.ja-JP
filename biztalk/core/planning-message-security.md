---
title: "メッセージ セキュリティの計画 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- planning, security
- security, messages
- security, planning
- messages, security
ms.assetid: c0f93515-a822-425c-9155-270a179d6b61
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5826db8480d378342ee30993f67bbd60e27751d0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="planning-message-security"></a>メッセージ セキュリティの計画
企業内のセキュリティ ポリシーに基づいて、次の表に示す項目を検討し、BizTalk Server 環境に実装する必要があるセキュリティのレベルを決定します。 この項目に対する解答によって、メッセージングに必要なセキュリティ機能が決まります。  
  
|質問|BizTalk Server のセキュリティ機能|  
|--------------|-------------------------------------|  
|**メッセージを受信するとき**||  
|メッセージの送信者をどのように特定するか|BizTalk パイプラインのパーティの解決コンポーネントと、署名証明書または Windows セキュリティ ID (SID) を使用すると、メッセージの送信者を明確に識別できます。 詳細については、次を参照してください。[受信メッセージの認証](../core/inbound-message-authentication.md)です。|  
|メッセージ送信元パーティが既存かどうか|BizTalk パイプラインのパーティの解決コンポーネントを使用すると、メッセージ送信元パーティがシステム内に既に存在する取引先かどうかを特定できます。 詳細については、次を参照してください。[受信メッセージの認証](../core/inbound-message-authentication.md)です。|  
|不明なパーティからのメッセージを受信するかどうか|ポートで認証を必須とする機能を使用すると、既知のパーティからのメッセージのみを BizTalk サーバーで処理するように指定できます。 詳細については、次を参照してください。[受信メッセージの認証](../core/inbound-message-authentication.md)です。|  
|**メッセージの送信。**||  
|送信するメッセージのプライバシーをどのように確保するか|メッセージを暗号化すると、意図したパーティのみがメッセージを読めるようにできます。 詳細については、次を参照してください。[送信のメッセージ保護](../core/outbound-message-protection.md)です。|  
|送信中に、悪意のあるユーザーによるメッセージの改ざんをどのように防ぐか|デジタル署名を使用すると、メッセージの整合性を確保できます。 詳細については、次を参照してください。[送信のメッセージ保護](../core/outbound-message-protection.md)です。|  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [メッセージを送受信するためのセキュリティ](../core/security-for-sending-and-receiving-messages.md)  
  
-   [暗号化と証明書の署名](../core/encryption-and-signing-certificates.md)  
  
-   [メッセージの送信者の認証](../core/authenticating-the-sender-of-a-message.md)  
  
-   [メッセージの受信者の承認](../core/authorizing-the-receiver-of-a-message.md)