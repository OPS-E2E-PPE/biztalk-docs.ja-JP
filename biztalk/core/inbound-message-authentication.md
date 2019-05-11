---
title: 受信メッセージの認証 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, authenticating
- processing, inbound messages
- messages, inbound
- processing, security
- security, messages
- inbound messages
ms.assetid: 34c06283-667d-4498-8544-dea6e87f276f
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d3b9a7812b7466145a0861112948633dae8442a0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65332099"
---
# <a name="inbound-message-authentication"></a>受信メッセージの認証
BizTalk Server では、メッセージの送信者の id を検証するには、(を使用するか、証明書の情報または Windows 統合セキュリティ) メッセージの送信者を認証できます。 セキュリティ機能を次に示します[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ことは、受信メッセージの認証に使用することができます。  
  
 ![認証の受信メッセージのセキュリティ機能](../core/media/ebiz-plan-secoverview-auth-inbound.gif "ebiz_plan_secoverview_auth_inbound")  
BizTalk Server のセキュリティ機能は、受信メッセージの認証に使用します。  
  
 BizTalk Server では、暗号化および署名されたメッセージを受信、送信元パーティが認識されていることを確認するには、次の手順がかかります。  
  
1.  BizTalk Server の受信場所でメッセージが到着すると、受信ハンドラー、送信プロセスから送信者の Windows セキュリティ ID (SSID) を取得しようとします。 受信場所は、リスナー、署名付きメッセージの認証が既に場合に対応する SSID をダウン ストリームを渡します。 クライアント側の証明書の情報を取得できます (たとえば、BizTalk メッセージ キューまたは HTTP アダプター) によって、BizTalk Server の受信場所がその証明書情報を取得し、受信パイプラインで後でパーティ解決のため、一緒に渡す場合. 受信ハンドラーでは、SSID を取得できない場合は、このフィールドは空白になります。  
  
     受信ハンドラーは、受信パイプラインでメッセージが復号化された、デジタル署名を検証すると、およびパイプラインがパーティの解決コンポーネントを持つ場合に、パーティの解決が行わにメッセージを送信します。 送信側が受信メッセージの署名証明書を使用する場合、MIME/SMIME デコーダー コンポーネントは、アダプターから取得した証明書情報を上書きします。  
  
2.  送信者には、メッセージが暗号化されている場合、MIME/SMIME デコーダーは、ホスト インスタンス サービス アカウントの個人用証明書ストアから復号化証明書を取得し、プライベート キーを使用して、メッセージを復号化します。  
  
     送信者には、メッセージが署名されている場合、MIME/SMIME デコーダーは、ペイロード ハッシュ署名を検証する改ざん、および証明書ストアから証明書を取得するを確認することにより、デジタル署名を認証します。 署名者の公開キーがメッセージ自体にある場合、MIME/SMIME デコーダーは、証明書ストアから証明書を取得しませんが、メッセージに付属する公開キーを使用します。  
  
3.  通常、パイプラインの最終処理の手順では、パーティの解決です。 BizTalk エクスプ ローラーまたは BizTalk Server 管理コンソールを使用してパーティを作成することができます、パーティに署名証明書をマップ パーティ エイリアスを作成または。 BizTalk エクスプ ローラーで定義するすべてのパーティでは、一意なパーティ id (PID) があります。 BizTalk Server では、PID を取得し、メッセージ コンテキストに配置します。 BizTalk は、次のメソッドのいずれかによって、PID を取得します。  
  
    1.  送信者がメッセージに署名または受信ハンドラーは、クライアント側の証明書を取得することが証明書を使用してパーティを解決するオプションを選択した場合は、BizTalk は、対応する署名またはクライアント側の証明書を参照する場合、PID です。 メッセージの受信を開始する前に、プロパティとして、証明書で、パーティを構成する必要があります。 詳細については、パーティを構成するを参照してください方法[パーティの解決用の証明書を使用して](../core/using-certificates-for-party-resolution.md)。  
  
    2.  送信者がメッセージで、署名証明書を使用しなかった、送信者のセキュリティ ID (SSID) を使用してパーティを解決するオプションを選択する場合は、パーティの解決コンポーネントは、PID を検索する SSID を使用します。 メッセージの受信を開始する前に、SSID をエイリアスとして使用するパーティを構成する必要があります。 パーティの解決コンポーネントの詳細については、次を参照してください。[パーティの解決パイプライン コンポーネント](../core/party-resolution-pipeline-component.md)します。  
  
        > [!NOTE]
        >  BizTalk Server では、パーティのエイリアスを定義するときに実際の Windows SID ではなく、アカウント名を使用します。  
  
    3.  パーティを解決できない場合、パイプラインは、PID をゲストに設定します。  
  
4.  受信ポートを認証必須であり、BizTalk Server で有効な PID を取得し、既知のパーティに解決されるようにマークした場合、メッセージはメッセージ ボックス データベースにキューに格納します。 SSID が空、または PID が guest ID、BizTalk Server は、メッセージを破棄するか、または (Authentication Required プロパティの構成) によっては保留キューに送信します。 不明なパーティから大量のメッセージの受信の悪影響を最小限にとどめる方法として Authentication Required プロパティを使用できます。 受信ポートの認証オプションの詳細については、次を参照してください。[受信ポートの認証オプションを構成する方法](../core/how-to-configure-authentication-options-for-a-receive-port.md)します。  
  
## <a name="see-also"></a>参照  
 [プロセス間のメッセージの認証](../core/authentication-of-messages-between-processes.md)   
 [送信メッセージの保護](../core/outbound-message-protection.md)   
 [メッセージの送信者の認証](../core/authenticating-the-sender-of-a-message.md)   
 [メッセージの受信者の承認](../core/authorizing-the-receiver-of-a-message.md)   
 [署名付きメッセージを受信するための BizTalk Server を構成する方法](../core/how-to-configure-biztalk-server-for-receiving-signed-messages.md)   
 [BizTalk Server で署名付きメッセージに使用する証明書](../core/certificates-that-biztalk-server-uses-for-signed-messages.md)