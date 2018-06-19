---
title: プロセス間でメッセージの認証 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- PID
- security, warnings
- processing, messages
- processing, security
- messages, processing
- security, messages
- MessageBox database, authenticating
- SSID
- authenticating, warnings
ms.assetid: fa746ee3-fc22-4e63-a5cc-8bc0cbeb536b
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1c54fb463353ed6551dcbf5764fae05e63fdb778
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22231306"
---
# <a name="authentication-of-messages-between-processes"></a>プロセス間でメッセージの認証
次の図に、BizTalk ホスト間でメッセージの認証に使用できる BizTalk Server のセキュリティ機能を示します。  
  
 ![メッセージを認証するセキュリティ機能](../core/media/ebiz-plan-secoverview-auth-process.gif "ebiz_plan_secoverview_auth_process")  
BizTalk Server でプロセス間のメッセージ認証に使用されるセキュリティ機能  
  
 BizTalk Server で、メッセージが受信、解読、検証され、メッセージの送信者を識別する有効なパーティ ID (PID) と証明書が取得されると、メッセージ ボックス データベースでは、メッセージに一致するサブスクリプションを確認して後続の処理用にメッセージを他のホストに送信する準備ができたことになります。  
  
 メッセージがプロセス間で受け渡される際には、承認、パーティの解決、送信者に関連するビジネス ロジックでの使用などの目的で、下流のプロセスにメッセージの元の送信者 ID を渡す必要が生じる場合があります。 しかし、すべてのホストに対し、セキュリティまたは信頼メカニズムを使用せずにこの情報を送信することを許可すると、すべてのユーザー オブジェクトとコード (オーケストレーション、アダプタ、パイプライン コンポーネント、Functoid など) について信頼性を検証する必要があり、負荷が非常に大きくなります。  
  
 BizTalk Server では、ユーザー オブジェクトやコードの信頼性レベルを区別する方法として、ホストのプロパティとして提供されている "信頼されている認証" を使用できます。 認証が信頼済みに設定されていないホストからメッセージを受信した場合、メッセージ ボックス データベースではメッセージの PID が Guest ID で上書きされ、SSID がホスト インスタンスを実行しているサービス アカウントで上書きされます。 認証が信頼済みに設定されているホストでは、メッセージ ボックス データベースにキュー送信するメッセージに任意の送信者 SID (SSID) および任意のパーティ ID (PID) を指定できます。  
  
 信頼済みのホストとそうでないホストを区別することで、ユーザー オブジェクトとコードを信頼できるかどうかのセキュリティ処理境界を定義できます。 つまり、認証が信頼済みに設定されているホストに展開されるユーザー オブジェクトとコードは、認証が信頼済みに設定されていないホストに展開されるユーザー オブジェクトとコードより信頼できます。 信頼済み認証ホストを構成する方法の詳細については、次を参照してください。[ホストのプロパティを変更する方法](../core/how-to-modify-host-properties.md)です。  
  
 メッセージ ボックス データベースがメッセージを受信すると、BizTalk Server では以下の手順が実行され、メッセージ ボックス データベースにメッセージを送信したホスト インスタンスの認証が信頼済みであることが保証されます。  
  
1.  最初に、メッセージ ボックス データベースで、メッセージを送信したホストの認証が信頼済みに設定されているかどうかが判定されます。これは、そのホストの SSID が信頼済みホストのホスト インスタンス サービス アカウントの SSID であるかどうかを確認することで行われます。  
  
2.  メッセージ ボックス データベースにメッセージを送信したホストの認証が信頼済みに設定されている場合、メッセージ コンテキストの SSID と PID は、空でない限りそのまま残されます。 SSID が空の場合、メッセージ ボックス データベースでは、呼び出したプロセスの SID (ホスト SID (HSID)) が SSID として使用されます。 PID が空の場合は、Guest ID が PID として設定されます。  
  
3.  メッセージ ボックス データベースにメッセージを送信したホストの認証が信頼済みに設定されていない場合は、SSID と PID が既に設定されているかどうかに関係なく、SSID には HSID が設定され、PID には Guest ID が設定されます。  
  
> [!IMPORTANT]
>  下流のプロセスでメッセージの元の送信者の SSID と PID が必要な場合は、メッセージが通過するすべてのホストの認証を信頼済みに設定する必要があります。 また、オーケストレーションで受信したメッセージを送信メッセージの作成に使用する場合などは、受信メッセージの SSID と PID を送信メッセージのプロパティとして明示的に追加し、下流のプロセスに渡されるようにする必要があります。  
  
> [!IMPORTANT]
>  パイプラインが実行されているホストに対し認証を信頼済みとして構成した場合、BizTalk Server でそのパイプラインは信頼済みの環境と見なされます。 そのため、認証が信頼済みとなっているホストで実行されている BizTalk パイプラインについては、含まれるすべてのカスタム コンポーネントが信頼済みかどうかを確認することが非常に重要です。  
  
> [!NOTE]
>  認証が信頼済みであるホストと信頼されている認証されていないホストで同じサービス アカウントを使用することはできません。  
  
## <a name="see-also"></a>参照  
 [受信メッセージの認証](../core/inbound-message-authentication.md)   
 [送信メッセージの保護](../core/outbound-message-protection.md)   
 [メッセージの送信者の認証](../core/authenticating-the-sender-of-a-message.md)   
 [メッセージの受信者の承認](../core/authorizing-the-receiver-of-a-message.md)