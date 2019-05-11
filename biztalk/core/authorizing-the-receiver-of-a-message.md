---
title: メッセージの受信者の承認 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security, messages
- messages, receive authorization
- receive authorization
- messages, security
ms.assetid: c0cdb3ef-ee8e-40a1-9362-13cd26495951
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3ca2b0b6474421bc474cf30ae8c8817bc5f8e10d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358752"
---
# <a name="authorizing-the-receiver-of-a-message"></a>メッセージの受信者の承認
Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]プロセスとメッセージの受信を承認するパーティを制限することができます。  
  
 次の図は、メッセージの受信者を承認するために使用する BizTalk Server のセキュリティ機能を示します。  
  
 ![メッセージの受信者を承認するセキュリティ機能](../core/media/ebiz-plan-secoverview-authz.gif "ebiz_plan_secoverview_authz")  
BizTalk Server のセキュリティ機能は、メッセージの受信者を承認するために使用します。  
  
 (承認) を送信するメッセージを受信するのにためのアクセス許可を持っているユーザーを確立するために、次のセキュリティ メカニズムを使用できます。  
  
-   **復号化します。** パーティの公開キー証明書メッセージの暗号化に BizTalk Server に送信する BizTalk Server にメッセージを送信するようにしてください。 BizTalk Server では、秘密キー証明書を使用して、メッセージの暗号化を解除します。  
  
-   **承認が表示されます。** コントロールの特定のメッセージを受信できるは、BizTalk Server 環境内でホストするには、このメソッドを使用することができます。  
  
-   **暗号化。** によって指定された関係者から公開キー証明書を使用して、BizTalk がメッセージを暗号化するときに、意図したパーティのみがメッセージを読み取ることがあることを確認できます。  
  
## <a name="receive-authorization"></a>受信認証  
 受信認証は、受信できるホスト コントロールを使用することができます (サブスクライブ) の特定のメッセージ。 BizTalk Server メッセージの述語のサブスクリプションのプロパティと一致するように証明書情報を使用して: メッセージ ボックス データベースのみをそのメッセージの復号化証明書を持つホストに必要な承認としてマークされたメッセージをルーティングします。 プロセスを示すためには、次のシナリオを検討してください。  
  
- **暗号化されていないメッセージのルーティング。** BizTalk Server では、暗号化されていない送信者がメッセージを受信したときに、BizTalk がメッセージをルーティングする方法に関して、解読の制限はありません。 ホストとホストなしの両方の受信認証証明書を構成には、メッセージが表示されることができます。  
  
- **暗号化されたメッセージをルーティングするには。** 暗号化されたメッセージが到着すると、受信パイプラインは、メッセージを解読するデコード コンポーネントを含める必要があります。 解読され、BizTalk メッセージ ボックス データベースのサブスクリプション メカニズムで証拠として、メッセージを復号化するために使用する証明書の拇印を使用して、その証明書で構成されているホストのみを受信した後に、BizTalk Server がメッセージをルーティングするときに、メッセージ。  
  
  する場合を使用する承認の受信、メッセージの受信を承認するホストのプロパティに解読証明書の拇印を指定する必要があります。 詳細については、承認を受信を参照してください。[ホスト プロパティを変更する方法](../core/how-to-modify-host-properties.md)します。  
  
## <a name="see-also"></a>参照  
 [受信メッセージの認証](../core/inbound-message-authentication.md)   
 [プロセス間のメッセージの認証](../core/authentication-of-messages-between-processes.md)   
 [送信メッセージの保護](../core/outbound-message-protection.md)   
 [メッセージの送信者の認証](../core/authenticating-the-sender-of-a-message.md)   
 [メッセージ セキュリティの計画](../core/planning-message-security.md)