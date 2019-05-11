---
title: メッセージを送受信するためのセキュリティ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, receiving
- messages, sending
- messages, processing
- security, messages
- security, message processing
- messages, security
ms.assetid: 9bcd01e4-245a-4f4c-b65c-89d7cd3d1b68
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0dfaf4b02c674995c2e60c694d439281d6d632ab
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65280435"
---
# <a name="security-for-sending-and-receiving-messages"></a>メッセージを送受信するためのセキュリティ
BizTalk Server は、それを受信し、処理し、別のアプリケーションまたはパートナーに送信しますメッセージに対する処理を次に示します。  
  
 ![セキュリティで保護されたメッセージのセキュリティ機能](../core/media/ebiz-plan-secoverview.gif "ebiz_plan_secoverview")  
メッセージの有効期間全体で使用されるセキュリティ機能  
  
1.  アダプターの受信場所は、メッセージを受信します。 プロトコルに応じて、アダプターはプロトコル レベルのメッセージの送信者を表す Windows ユーザー アカウントを識別するために送信者の認証。  
  
2.  アダプターからメッセージを渡すをパイプラインにメッセージ レベルの認証が行われる場所、アダプターで行われていない場合。  
  
    1.  デコード段階では、パイプラインはメッセージを復号化をメッセージに添付された証明書またはローカル コンピューターの他のユーザーの証明書ストアで構成されているいずれかで、署名の有効性を確認します。 パイプラインが、署名を検証した後、デコード コンポーネントは、信頼されたルート証明機関 (CA) までの証明書チェーンを検証します。 S/MIME メッセージをデコードするパイプラインを構成すると、送信者が S/MIME を使用してメッセージを暗号化、MIME/SMIME デコーダーは、メッセージの署名を検証し、送信者を識別するために、証明書を使用します。 MIME/SMIME デコーダー パイプライン コンポーネントを使用する方法の詳細については、次を参照してください。[メッセージ セキュリティを実装する](../core/implementing-message-security.md)します。  
  
    2.  パーティの解決ステージでは、BizTalk Server で、証明書情報を使用し、プロトコル レベルの認証システムで、メッセージの送信者が認識されたパーティであるかどうかを確認してから送信者のセキュリティ ID (SSID) を取得します。 送信者の SSID は、アダプターによって認証されたユーザーの修飾名です。 例えば。 BizTalk Server では、Windows 認証を使用して、HTTP アダプターを使用してメッセージを受信した場合、送信者の SSID はドメイン \ ユーザー名です。 BizTalk Server が認識されたパーティのパーティ ID または guest ID のいずれかであると、メッセージをパーティ ID (PID) を割り当てます パーティの解決コンポーネントを使用する方法の詳細については、次を参照してください。[パーティの解決用の証明書を使用して](../core/using-certificates-for-party-resolution.md)します。  
  
    3.  かどうか、送信者をシステムでは、既知のパーティに認証を必要とする受信ポートを構成した BizTalk Server は、メッセージの送信者の PID を検索できませんし、BizTalk Server が削除されるかの構成によって、メッセージを保留します 受信ポート。 BizTalk Server では、サービス拒否攻撃を軽減するには、この機能を提供します。 受信ポートの認証オプションの詳細については、次を参照してください。[受信ポートの認証オプションを構成する方法](../core/how-to-configure-authentication-options-for-a-receive-port.md)します。  
  
3.  メッセージが認証されると、パイプライン、メッセージ ボックス データベースにメッセージを送信します。  
  
    1.  信頼済み認証ホストとして (パイプラインが実行されて) いるキュー送信ホストを特定できなかった場合、メッセージ ボックス データベースには、guest ID でサービス アカウントとして実行しているキュー送信ホストのインスタンスを持つ SSID と PID が上書きされます。 信頼済み認証ホストの詳細については、次を参照してください。[認証メッセージの間でプロセスの](../core/authentication-of-messages-between-processes.md)します。 信頼済み認証ホストを構成する方法の詳細については、次を参照してください。[ホスト プロパティを変更する方法](../core/how-to-modify-host-properties.md)します。  
  
    2.  メッセージ ボックス データベースが PID および SSID を信頼し、下流のプロセスでこの情報を使用して認証できるように、メッセージのコンテキストでは、この情報を離れる場合は、パイプラインが実行されているホストが信頼された認証としてマークされている、またはメッセージの元の送信者を承認します。  
  
    3.  BizTalk Server では、受信、認証が必要な場合、メッセージ ボックス データベースは、メッセージをサブスクライブして、ホストにメッセージを受信するための承認があることを確認します。 詳細については、承認を受信を参照してください。[メッセージの受信者の承認](../core/authorizing-the-receiver-of-a-message.md)します。  
  
4.  BizTalk Server がメッセージを処理した後、送信パイプラインの暗号化や、エンコード ステージで、メッセージにデジタル署名します。  
  
## <a name="see-also"></a>参照  
 [メッセージ セキュリティの実装](../core/implementing-message-security.md)   
 [メッセージ セキュリティの計画](../core/planning-message-security.md)