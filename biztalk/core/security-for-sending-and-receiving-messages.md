---
title: "メッセージを送受信するためのセキュリティ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, receiving
- messages, sending
- messages, processing
- security, messages
- security, message processing
- messages, security
ms.assetid: 9bcd01e4-245a-4f4c-b65c-89d7cd3d1b68
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e1328eb98cbf94b85cda16eda431da197c6d0126
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="security-for-sending-and-receiving-messages"></a>メッセージを送受信する際のセキュリティ
次の図に、BizTalk Server でメッセージが受信および処理され、別のアプリケーションやパートナーに送信されるときの状況を示します。  
  
 ![セキュリティで保護されたメッセージのセキュリティ機能](../core/media/ebiz-plan-secoverview.gif "ebiz_plan_secoverview")  
メッセージの有効期間全体で使用されるセキュリティ機能  
  
1.  アダプタの受信場所でメッセージが受信されます。 プロトコルに応じて、アダプタではプロトコル レベルの送信者の認証が行われ、メッセージの送信者を表す Widnows ユーザー アカウントが識別されます。  
  
2.  次に、アダプタからパイプラインにメッセージが渡されます。アダプタで認証が行われていない場合、メッセージ レベルでの認証が行われます。  
  
    1.  デコード ステージでは、パイプラインでメッセージが解読され、メッセージに添付された証明書、またはローカル コンピュータの "ほかの人" 証明書ストアに構成された証明書を使用して、署名の有効性が確認されます。 パイプラインで署名が検証された後、デコード コンポーネントでは、信頼済みのルート証明機関 (CA) までさかのぼって証明書チェーンが検証されます。 S/MIME メッセージをデコードするようにパイプラインを構成し、送信者が S/MIME を使用してメッセージを暗号化している場合は、MIME/SMIME デコーダでメッセージの署名が確認され、証明書を使用して送信者が識別されます。 MIME/SMIME デコーダー パイプライン コンポーネントを使用する方法の詳細については、次を参照してください。[メッセージのセキュリティを実装する](../core/implementing-message-security.md)です。  
  
    2.  パーティの解決ステージでは、証明書情報とプロトコル レベルの認証で取得された送信者のセキュリティ ID (SSID) を使用して、メッセージの送信者がシステムで認識されたパーティであるかどうかが確認されます。 送信者の SSID は、アダプタで認証されたユーザーの修飾名です。 たとえば、Windows 認証を使用する HTTP アダプタでメッセージが受信された場合、送信者の SSID は domain\username になります。 メッセージにはパーティ ID (PID) が割り当てられますが、これは認識済みパーティのパーティ IDか、Guest ID になります。 BizTalk Server では、認識されたパーティのパーティ ID または guest ID のいずれかであると、メッセージをパーティ ID (PID) を割り当てます パーティの解決コンポーネントを使用する方法の詳細については、次を参照してください。[パーティの解決用の証明書を使用して](../core/using-certificates-for-party-resolution.md)です。  
  
    3.  送信者を認証してシステムの既知のパーティに解決するように受信ポートを構成したときに、メッセージ送信者の PID が見つからない場合は、受信ポートの構成に従ってメッセージが削除されるか中断されます。 この機能により、サービスの拒否攻撃が緩和されます。 受信ポートの認証オプションの詳細については、次を参照してください。[受信ポートの認証オプションを構成する方法](../core/how-to-configure-authentication-options-for-a-receive-port.md)です。  
  
3.  パイプラインでメッセージが認証された後、メッセージ ボックス データベースにメッセージが送信されます。  
  
    1.  パイプラインが実行されているキュー送信ホストが信頼済みの認証ホストとして識別されなかった場合、メッセージ ボックス データベースではメッセージの PID が Guest ID で上書きされ、SSID がキュー送信ホスト インスタンスを実行しているサービス アカウントで上書きされます。 信頼済み認証ホストの詳細については、次を参照してください。[認証メッセージの間でプロセスの](../core/authentication-of-messages-between-processes.md)します。 信頼済み認証ホストを構成する方法の詳細については、次を参照してください。[ホストのプロパティを変更する方法](../core/how-to-modify-host-properties.md)です。  
  
    2.  パイプラインが実行されているホストが信頼されている認証として指定されている場合、メッセージ ボックス データベースでは PID および SSID が信頼されます。下流のプロセスでこの情報を使用して、メッセージの元の送信者の認証や承認を行えるように、情報はメッセージのコンテキストに残されます。  
  
    3.  BizTalk Server で受信認証が構成されている場合、メッセージ ボックス データベースでは、メッセージにサブスクライブされたホストにメッセージを受信する権限があるかどうか確認されます。 詳細については、承認を受け取るを参照してください[メッセージの受信者の承認](../core/authorizing-the-receiver-of-a-message.md)です。  
  
4.  メッセージが処理された後、エンコード ステージにおいて、送信パイプラインではメッセージの暗号化やデジタル署名の追加が行われます。  
  
## <a name="see-also"></a>参照  
 [メッセージ セキュリティを実装します。](../core/implementing-message-security.md)   
 [メッセージ セキュリティの計画](../core/planning-message-security.md)