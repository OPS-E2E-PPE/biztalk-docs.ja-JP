---
title: "メッセージの受信者の承認 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- security, messages
- messages, receive authorization
- receive authorization
- messages, security
ms.assetid: c0cdb3ef-ee8e-40a1-9362-13cd26495951
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7317cd9c54568edd2c49df026790ee7a1e70fb2e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="authorizing-the-receiver-of-a-message"></a>メッセージの受信者の承認
Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、メッセージの受信を承認する対象のプロセスとパーティを制限できます。  
  
 メッセージの受信者を承認するために使用する BizTalk Server のセキュリティ機能を次に示します。  
  
 ![メッセージの受信者を承認するセキュリティ機能](../core/media/ebiz-plan-secoverview-authz.gif "ebiz_plan_secoverview_authz")  
メッセージの受信者の承認で使用する BizTalk Server のセキュリティ機能  
  
 以下のセキュリティ メカニズムを使用して、送信したメッセージの受信を許可 (承認) する対象を設定できます。  
  
-   **復号化します。** パーティの公開キー証明書のメッセージの暗号化に BizTalk Server に送信する BizTalk Server にメッセージを送信するようにしてください。 BizTalk Server では、秘密キー証明書を使用してメッセージを解読します。  
  
-   **承認が表示されます。** 特定のメッセージを受信できるは、BizTalk Server 環境内でホストを制御するには、この方法を使用することができます。  
  
-   **暗号化します。** BizTalk がメッセージを暗号化するときに特定のパーティの公開キー証明書を使用するように設定することで、意図したパーティのみがメッセージを読み取ることができるようにできます。  
  
## <a name="receive-authorization"></a>受信認証  
 受信認証は、指定したメッセージを受信 (サブスクライブ) できるホストの制御に使用します。 一致するように、サブスクリプションのプロパティがメッセージの述語として BizTalk Server は、証明書情報を使用して: メッセージ ボックス データベースだけをそのメッセージの暗号化解除証明書を持つホストに必要な承認とマークされたメッセージをルーティングします。 次のシナリオを使用してプロセスを説明します。  
  
-   **暗号化されていないメッセージのルーティング:**ときの BizTalk Server は、送信者が暗号化されていないメッセージを受け取り、BizTalk がメッセージをルーティングする方法についての復号化の制限はありません。 受信認証証明書が構成されているホストと受信承認証明書が構成されていないホストの両方でメッセージを受信できます。  
  
-   **暗号化されたメッセージのルーティング:**暗号化されたメッセージが到着すると、受信パイプラインは、メッセージを解読するデコード コンポーネントを含める必要があります。 BizTalk Server でメッセージが解読されルーティングされるときに、メッセージ ボックス データベースのサブスクリプション メカニズムでは、メッセージの解読に使用された証明書の拇印が証拠として使用されます。この証明書が構成されているホストのみがメッセージを受信します。  
  
 受信認証を使用する場合は、メッセージの受信を承認するホストのプロパティに解読証明書の拇印を指定する必要があります。 詳細については、承認を受け取るを参照してください[ホストのプロパティを変更する方法](../core/how-to-modify-host-properties.md)です。  
  
## <a name="see-also"></a>参照  
 [受信メッセージの認証](../core/inbound-message-authentication.md)   
 [プロセス間でメッセージの認証](../core/authentication-of-messages-between-processes.md)   
 [送信メッセージの保護](../core/outbound-message-protection.md)   
 [メッセージの送信者の認証](../core/authenticating-the-sender-of-a-message.md)   
 [メッセージ セキュリティの計画](../core/planning-message-security.md)