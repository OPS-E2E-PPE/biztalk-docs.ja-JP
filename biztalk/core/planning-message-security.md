---
title: メッセージ セキュリティの計画 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- planning, security
- security, messages
- security, planning
- messages, security
ms.assetid: c0f93515-a822-425c-9155-270a179d6b61
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 847c53e7e07b4985f5cf2ad1756e3343c335348b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395632"
---
# <a name="planning-message-security"></a>メッセージ セキュリティの計画
社内のセキュリティ ポリシーに基づいて、BizTalk Server 環境で実装する必要があるセキュリティのレベルを決定する次の表に、質問を考慮することがあります。 これらの質問に対する回答には、メッセージングに必要なセキュリティ機能が決まります。  
  
|質問|BizTalk Server のセキュリティ機能|  
|--------------|-------------------------------------|  
|**メッセージの受信時**||  
|メッセージの送信者の id を確認するにはどうするでしょうか。|BizTalk パイプラインと署名証明書または Windows セキュリティ ID (SID) で、パーティの解決コンポーネントは、メッセージの送信者を明確に識別するために使用できます。 詳細については、次を参照してください。[受信メッセージの認証](../core/inbound-message-authentication.md)します。|  
|メッセージを送信したパーティをご存知ですか。|BizTalk パイプラインのパーティの解決コンポーネントを使用すると、メッセージを送信したパーティがシステムに既に取引先であるかどうかを確認します。 詳細については、次を参照してください。[受信メッセージの認証](../core/inbound-message-authentication.md)します。|  
|不明なパーティからメッセージを受信しないようにしますか。|ポートの認証の必要な機能を使用すると、BizTalk server がわかっているパーティからのメッセージのみを処理する必要があります。 詳細については、次を参照してください。[受信メッセージの認証](../core/inbound-message-authentication.md)します。|  
|**メッセージの送信。**||  
|送信メッセージのプライバシーを確保するにはどうするでしょうか。|意図したパーティのみがメッセージに読み取ることができることを確認するメッセージを暗号化することができます。 詳細については、次を参照してください。[送信メッセージの保護](../core/outbound-message-protection.md)します。|  
|転送中に、メッセージの改ざんから悪意のあるユーザーを防ぐためにします。|デジタル署名を使用して、メッセージの整合性を確保することができます。 詳細については、次を参照してください。[送信メッセージの保護](../core/outbound-message-protection.md)します。|  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [メッセージを送受信する際のセキュリティ](../core/security-for-sending-and-receiving-messages.md)  
  
-   [暗号化証明書および署名証明書](../core/encryption-and-signing-certificates.md)  
  
-   [メッセージの送信者の認証](../core/authenticating-the-sender-of-a-message.md)  
  
-   [メッセージの受信者の承認](../core/authorizing-the-receiver-of-a-message.md)