---
title: 送信メッセージの保護 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- processing, outbound messages
- outbound messages
- security, messages
- authenticating, warnings
- messages, outbound
ms.assetid: 839d3b44-bb44-454b-817c-67b7c8cd74c9
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c451fd13e780c6530fcad7848b11528af3bc1968
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393438"
---
# <a name="outbound-message-protection"></a>送信メッセージの保護
次の図は、送信メッセージが承認されていないパーティによって読み取られることを防ぐために使用する BizTalk Server のセキュリティ機能を示します。  
  
 ![送信メッセージの保護のセキュリティ機能](../core/media/ebiz-plan-secoverview-auth-outbound.gif "ebiz_plan_secoverview_auth_outbound")  
BizTalk Server のセキュリティ機能では、送信メッセージを保護します。  
  
 ときに[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安全に、メッセージを送信して、受信側パーティがメッセージの送信者を判断できることを確保しやすく、次の手順を要するメッセージを送信します。  
  
1.  送信パイプラインには、すべての送信メッセージに署名するように構成されているエンコード コンポーネント (S/MIME) などが含まれる場合、BizTalk グループの署名証明書は、するには、ホスト インスタンス サービス アカウントの個人用証明書ストアから取得されます。パイプラインが実行されていると、メッセージの署名証明書に関連付けられている秘密キーを使用します。  
  
2.  その他のユーザーの証明書ストア、およびメッセージから公開キー証明書を取得する暗号化証明書の拇印を使用する場合は、送信パイプラインには、すべての送信メッセージを暗号化するように構成されているエンコード コンポーネント (S/MIME) などが含まれています、その証明書を使用して暗号化されます。  
  
> [!IMPORTANT]
>  すべての送信パイプラインの 1 つの署名証明書を使用して、BizTalk 環境では、送信パイプラインは、ホストの場合は、各ホスト インスタンスのサービス アカウントの証明書ストアにこの署名証明書があることを確認する必要があります。実行中です。  
  
 署名付きメッセージを送信する方法の詳細については、次を参照してください。[署名付きメッセージの送信用の BizTalk Server を構成する方法](../core/how-to-configure-biztalk-server-for-sending-signed-messages.md)します。  
  
## <a name="see-also"></a>参照  
 [受信メッセージの認証](../core/inbound-message-authentication.md)   
 [プロセス間のメッセージの認証](../core/authentication-of-messages-between-processes.md)   
 [メッセージの送信者の認証](../core/authenticating-the-sender-of-a-message.md)   
 [メッセージの受信者の承認](../core/authorizing-the-receiver-of-a-message.md)   
 [BizTalk Server で署名付きメッセージに使用する証明書](../core/certificates-that-biztalk-server-uses-for-signed-messages.md)