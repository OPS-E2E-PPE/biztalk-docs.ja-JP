---
title: "送信メッセージの保護 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- processing, outbound messages
- outbound messages
- security, messages
- authenticating, warnings
- messages, outbound
ms.assetid: 839d3b44-bb44-454b-817c-67b7c8cd74c9
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7adbbae776edee8a4f563e2cd48ee035acc3fd7d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="outbound-message-protection"></a>送信メッセージの保護
次の図に、承認されていないパーティに送信メッセージを読み取られないようにするための BizTalk Server のセキュリティ機能を示します。  
  
 ![送信メッセージの保護に関するセキュリティ機能](../core/media/ebiz-plan-secoverview-auth-outbound.gif "ebiz_plan_secoverview_auth_outbound")  
送信メッセージの保護に使用される BizTalk Server のセキュリティ機能  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] からメッセージが送信されると、次の手順でメッセージが安全に送信され、受信側パーティではメッセージの送信者が確認されます。  
  
1.  すべての送信メッセージに署名するように構成されているエンコード コンポーネント (S/MIME など) が送信パイプラインに含まれている場合、パイプラインが実行されているホスト インスタンス サービス アカウントの個人証明書ストアから BizTalk グループの署名証明書が取得されます。その後、メッセージは証明書に関連付けられた秘密キーを使用して署名されます。  
  
2.  すべての送信メッセージを暗号化するように構成されているエンコード コンポーネント (S/MIME など) が送信パイプラインに含まれている場合、暗号化証明書の拇印を使用して "その他のユーザー" 証明書ストアから公開キー証明書が取得され、メッセージはその証明書を使用して暗号化されます。  
  
> [!IMPORTANT]
>  BizTalk 環境ではすべての送信パイプラインで 1 つの署名証明書を使用しますが、この署名証明書が、送信パイプラインが実行されているホストの各ホスト インスタンスのサービス アカウントに設定された証明書ストアで使用できることを確認する必要があります。  
  
 署名付きメッセージを送信する方法の詳細については、次を参照してください。[署名付きメッセージを送信する、BizTalk Server を構成する方法](../core/how-to-configure-biztalk-server-for-sending-signed-messages.md)です。  
  
## <a name="see-also"></a>参照  
 [受信メッセージの認証](../core/inbound-message-authentication.md)   
 [プロセス間でメッセージの認証](../core/authentication-of-messages-between-processes.md)   
 [メッセージの送信者の認証](../core/authenticating-the-sender-of-a-message.md)   
 [メッセージの受信者の承認](../core/authorizing-the-receiver-of-a-message.md)   
 [BizTalk Server が署名されたメッセージで使用する証明書](../core/certificates-that-biztalk-server-uses-for-signed-messages.md)