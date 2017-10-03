---
title: "受信メッセージの認証 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, authenticating
- processing, inbound messages
- messages, inbound
- processing, security
- security, messages
- inbound messages
ms.assetid: 34c06283-667d-4498-8544-dea6e87f276f
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 49ada514c771f4e6dbf0abad3f23cab54721299d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="inbound-message-authentication"></a>受信メッセージの認証
BizTalk Server では、証明書の情報または Windows 統合セキュリティを使用して、メッセージの送信者を認証し、その ID を検証できます。 次の図に、受信メッセージの認証に使用できる [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のセキュリティ機能を示します。  
  
 ![受信メッセージの認証のセキュリティ機能](../core/media/ebiz-plan-secoverview-auth-inbound.gif "ebiz_plan_secoverview_auth_inbound")  
受信メッセージの認証に使用される BizTalk Server のセキュリティ機能  
  
 暗号化および署名されたメッセージが BizTalk Server で受信されると、送信元パーティが認識済みであることが次の手順で確認されます。  
  
1.  メッセージが BizTalk Server の受信場所で受信されると、受信ハンドラーによって、送信プロセスから送信者の Windows セキュリティ ID (SSID) の取得が試みられます。 また、受信場所から下流の処理に SSID が渡され、リスナーで既に署名付きメッセージが認証されている場合に利用できるよう備えられます。 クライアント側の証明書情報が BizTalk メッセージ キューや HTTP アダプターなどによって取得できる場合は、BizTalk Server の受信場所ではその証明書情報を取得でき、一緒に渡すことができます。情報は、受信パイプラインで後のパーティの解決に使用されます。 受信ハンドラーで SSID を取得できない場合は、このフィールドは空のままになります。  
  
     メッセージは受信ハンドラーによって受信パイプラインに送信されます。受信パイプラインではメッセージの解読と、デジタル署名の検証が行われ、パイプラインにパーティの解決コンポーネントがある場合はパーティの解決が行われます。 受信メッセージに署名証明書が使用されている場合、アダプターから取得された証明書情報は MIME/SMIME デコーダー コンポーネントで上書きされます。  
  
2.  メッセージが暗号化されている場合、MIME/SMIME デコーダーでホスト インスタンス サービス アカウントの個人証明書ストアから解読証明書が取得され、秘密キーを使用してメッセージが解読されます。  
  
     送信者がメッセージに署名している場合、MIME/SMIME デコーダーでデジタル署名が認証されます。認証は、ペイロード ハッシュを検証して改ざんがないかどうかを確認し、証明書ストアから証明書を取得して署名を検証することで行います。 署名者の公開キーがメッセージ自体に含まれている場合、MIME/SMIME デコーダーでは証明書ストアから証明書は取得されず、メッセージに含まれている公開キーが使用されます。  
  
3.  通常、パイプラインの最後の処理手順はパーティの解決です。 BizTalk エクスプローラーまたは BizTalk Server 管理コンソールを使用して、パーティを作成したり、署名証明書にパーティをマップしたり、パーティ エイリアスを作成することができます。 BizTalk エクスプローラーで定義されたすべてのパーティには一意のパーティ識別子 (PID) が割り当てられます。 BizTalk Server では PID が取得され、メッセージ コンテキストに配置されます。 PID は次のいずれかの方法で取得されます。  
  
    1.  送信者がメッセージに署名している、または、受信ハンドラーでクライアント側の証明書を取得できるときに、証明書を使用してパーティを解決するオプションを選択している場合、BizTalk では対応する署名またはクライアント側の証明書を使用して PID を参照します。 メッセージの受信を開始するには、証明書を使用するパーティをプロパティとして構成する必要があります。 詳細については、パーティを構成する方法[パーティの解決用の証明書を使用して](../core/using-certificates-for-party-resolution.md)です。  
  
    2.  送信者がメッセージに署名証明書を使用していないときに、送信者のセキュリティ ID (SSID) を使用してパーティを解決するオプションを選択している場合、パーティの解決コンポーネントでは SSID を使用して PID を参照します。 メッセージの受信を開始するには、SSID をエイリアスとして使用するようにパーティを構成する必要があります。 パーティの解決コンポーネントの詳細については、次を参照してください。[パーティの解決パイプライン コンポーネント](../core/party-resolution-pipeline-component.md)です。  
  
        > [!NOTE]
        >  BizTalk Server では、パーティにエイリアスを定義するときに、実際の Windows SID ではなくアカウント名が使用されます。  
  
    3.  パーティが解決できない場合、パイプラインによって PID が Guest に設定されます。  
  
4.  受信ポートを [Authentication Required] に設定している場合に、BizTalk Server で有効な PID が取得されて既存のパーティに解決されると、メッセージはメッセージ ボックス データベースのキューに送信されます。 SSID が空であるか、PID が Guest ID である場合、[Authentication Required] プロパティの構成に応じて、メッセージは破棄されるか、保留キューに送信されます。 [Authentication Required] プロパティは、未知のパーティから大量のメッセージを受信することによる悪影響を最小限にとどめる方法として使用できます。 受信ポートの認証オプションの詳細については、次を参照してください。[受信ポートの認証オプションを構成する方法](../core/how-to-configure-authentication-options-for-a-receive-port.md)です。  
  
## <a name="see-also"></a>参照  
 [プロセス間でメッセージの認証](../core/authentication-of-messages-between-processes.md)   
 [送信メッセージの保護](../core/outbound-message-protection.md)   
 [メッセージの送信者の認証](../core/authenticating-the-sender-of-a-message.md)   
 [メッセージの受信者の承認](../core/authorizing-the-receiver-of-a-message.md)   
 [署名付きメッセージを受信するための BizTalk Server を構成する方法](../core/how-to-configure-biztalk-server-for-receiving-signed-messages.md)   
 [BizTalk Server が署名されたメッセージで使用する証明書](../core/certificates-that-biztalk-server-uses-for-signed-messages.md)