---
title: メッセージの送信者の認証 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- parties, authenticating
- authenticating, authentication required
- messages, authenticating
- security, authenticating
- digital signatures, authenticating
- security, messages
- MessageBox database, authenticating
- authenticating, authentication trust
- messages, message flow
- authenticating, security
- authenticating, party resolution
- authenticating, digital signatures
- authenticating, messages
ms.assetid: 813a2fb9-0346-4129-9cc5-1713f72a491e
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6e0f5a4cb539581102fdc599130fdf82819b425d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358782"
---
# <a name="authenticating-the-sender-of-a-message"></a>メッセージの送信者の認証
Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、さまざまなメカニズムを使用して、パーティまたはプロセスが本物であることを確認します。 さらに、プロセスでメッセージの元の送信者の情報を BizTalk Server に中継できるようにするかどうか、また BizTalk Server でパーティをパートナーとして認識するかどうかを指定できます。  
  
 次の図に、メッセージの送信者の認証および承認に使用できる BizTalk Server のセキュリティ機能を示します。  
  
 ![セキュリティで保護されたメッセージのセキュリティ機能](../core/media/ebiz-plan-secoverview.gif "ebiz_plan_secoverview")  
メッセージ送信の認証および承認に使用する BizTalk Server のセキュリティ機能  
  
 メッセージの送信者の認証に使用できる機能は次のとおりです。  
  
- **デジタル署名を検証します。** : メッセージがデジタル署名されている場合、その署名を使用して送信者の ID を確認します。 デジタル署名の検証を構成する方法の詳細については、次を参照してください。[署名付きメッセージの受信用の BizTalk Server を構成する方法](../core/how-to-configure-biztalk-server-for-receiving-signed-messages.md)します。  
  
- **パーティの解決。** : メッセージ ボックス データベースに挿入されたすべてのメッセージには、発信元が BizTalk Server の内外にかかわらず、パーティ ID (PID) が設定されています。PID は、デジタル証明書か Windows アカウントのいずれかを PID にマッピングすることで決定されます。 パーティの解決コンポーネントを構成する方法の詳細については、次を参照してください。[パーティの解決用の証明書を使用して](../core/using-certificates-for-party-resolution.md)します。  
  
- **認証が必要です。** : 送信ポートでメッセージの送信者を特定できない場合、BizTalk ホストでは、そのメッセージを "Guest" メッセージとして受け取るか、完全に無視することができます。 不明なパーティは処理されないか、追跡データベースに保存されないため、この機能を使用するとサービスの拒否攻撃からシステムを保護できます。 受信ポートの認証オプションの詳細については、次を参照してください。[受信ポートの認証オプションを構成する方法](../core/how-to-configure-authentication-options-for-a-receive-port.md)します。  
  
- **信頼されている認証** : 認証が信頼済みに設定されていないホストからメッセージを受信した場合、メッセージ ボックス データベースではメッセージの PID が Guest ID で上書きされ、SSID がホスト インスタンスを実行しているサービス アカウントで上書きされます。 BizTalk Server では、認証が信頼済みであると確認されたホストは、メッセージ ボックス データベースへキュー送信するときに、メッセージの送信者がこのホスト以外のエンティティであると示すことができます。 信頼済み認証の主な目的は、パイプラインで PID を解決して認証や送信パーティの解決で使用されるサービスにその PID を渡せるようにすることと、オーケストレーション アクションの認証で使用されるサービスに送信者の Windows セキュリティ ID (SSID) を転送できるようにすることです。 信頼済み認証ホストの詳細については、次を参照してください。[ホスト プロパティを変更する方法](../core/how-to-modify-host-properties.md)します。 BizTalk Server オーケストレーションをパーティの解決と組み合わせて使用する方法の詳細については、次を参照してください。 [PartyResolution (BizTalk Server サンプル)](../core/partyresolution-biztalk-server-sample.md)します。  
  
  このメッセージの送信元、メッセージの元の送信者、またはメッセージの受信者や参照者を把握する必要があるかどうかに応じて、図に示された機能の一部またはすべてを使用できます。  
  
  メッセージが確かにこちらから送信されていることと、送信中に他のユーザーから読み取られていないことをパートナー側で認識することが重要な場合は、次の方法を使用して、特定の受信者や受信アプリケーションのみがメッセージを受信できるようにすることをお勧めします。  
  
- 送信メッセージにデジタル署名を使用して、パートナー側でメッセージの送信者がこちらであることを確認できるようにする。  
  
- 送信メッセージを暗号化して、送信中のメッセージを承認されていないパーティに参照されないようにする。  
  
  会社にメッセージを送信したユーザーを特定することと、送信中にメッセージが他のユーザーから読み取られていないことを確認することが重要な場合は、次の方法を使用して、特定の受信者や受信アプリケーションのみがメッセージを受信できるようにすることをお勧めします。  
  
- デジタル署名付きのメッセージのみを受信許可して、メッセージの送信者を確認できるようにする。  
  
- パートナーに公開キー証明書を送信して、パートナーから BizTalk Server に送信するメッセージが暗号化されるようにする。 暗号化を使用することで、送信中のメッセージが承認されていないパーティに参照されないようにできます。  
  
- 受信ポートの認証要求プロパティを使用して、メッセージが既知のパーティから送信されていることを確認する。  
  
  複数のホストでメッセージが処理されると、メッセージの元の送信者がわからなくなる場合があります。 メッセージを送受信するためのアクセス権限を許可する場合など、元の送信者の ID を確認する必要がある場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ではセキュリティ メカニズムを利用することにより、多数のホストを経由して元の送信者の ID を伝達し、その ID を基に下流のホストへのアクセスを検証することができます。 BizTalk Server では、このときに "信頼されている認証" のプロセスが呼び出されます。 詳細については、次を参照してください。[認証メッセージの間でプロセスの](../core/authentication-of-messages-between-processes.md)します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [受信メッセージの認証](../core/inbound-message-authentication.md)  
  
-   [プロセス間のメッセージの認証](../core/authentication-of-messages-between-processes.md)  
  
-   [送信メッセージの保護](../core/outbound-message-protection.md)