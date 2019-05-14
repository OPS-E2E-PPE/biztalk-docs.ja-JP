---
title: プロセス間のメッセージの認証 |Microsoft Docs
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
ms.openlocfilehash: 0491946d3e8398fa56914b9f9ff4aaa89edb9228
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358764"
---
# <a name="authentication-of-messages-between-processes"></a>プロセス間のメッセージの認証
次の図は、BizTalk server の別の BizTalk ホスト間でメッセージを認証に使用できるセキュリティ機能を示します。  
  
 ![メッセージを認証するセキュリティ機能](../core/media/ebiz-plan-secoverview-auth-process.gif "ebiz_plan_secoverview_auth_process")  
BizTalk Server のセキュリティ機能は、プロセス間でメッセージの認証に使用します。  
  
 メッセージ ボックス データベースは、メッセージに一致するサブスクリプションを確認して、これを送信する準備ができて、BizTalk Server でメッセージを受信し、復号化、メッセージの検証し、には、有効なパーティ ID (PID) と、メッセージの送信者を識別する証明書、します。その他のホストをさらに処理するメッセージ。  
  
 メッセージは、別の 1 つのプロセスからフロー、承認、パーティの解決、送信者に関連するビジネス ロジックの下流のプロセスにメッセージの元の送信者の id を渡す必要が多くの場合。 ただし、すべてのホストのセキュリティまたは信頼メカニズムを使用せずには、この情報のフローを有効にするは大幅に増加するすべてのユーザーがオブジェクトし、コードを検証する必要が (たとえば、オーケストレーション、アダプタ、パイプライン コンポーネント、functoid) が信頼できます.  
  
 ユーザー オブジェクトとコードの信頼のレベルを区別するための手段を提供するには、BizTalk Server は、ホストのプロパティとして、信頼済み認証を提供します。 メッセージ ボックス データベースが信頼された認証として設定されていないホストからメッセージを受信したときに、メッセージ ボックス データベースは、PID で guest ID で上書きし、として実行しているホスト インスタンス サービス アカウントを持つ、SSID を上書きします。 認証が信頼済みとしてマークされたホストは、BizTalk により、すべての送信者 SID (SSID) を指定するホストとメッセージ ボックス データベースにキューにメッセージに任意のパーティ ID (PID)。  
  
 ホストが信頼されているとサポートされないを指定すると、ユーザー オブジェクトとコード信頼したり、信頼されていないセキュリティ境界を定義できます。 つまり、ユーザー オブジェクトと信頼されている認証に設定されているホストに展開されたコードをユーザー オブジェクトとコードが信頼されている認証に設定されていないホストに展開するよりも信頼性を向上する必要があります。 信頼済み認証ホストを構成する方法の詳細については、次を参照してください。[ホスト プロパティを変更する方法](../core/how-to-modify-host-properties.md)します。  
  
 メッセージ ボックス データベースでは、メッセージを受信したときに、BizTalk Server はメッセージ ボックス データベースにメッセージを送信したホスト インスタンスの信頼済み認証を強制する、次の手順を実行します。  
  
1.  まず、メッセージ ボックス データベースは、メッセージを送信したホストが SSID が信頼済みホストのホスト インスタンス サービス アカウントのことを確認して信頼された認証として設定されているかどうかを決定します。  
  
2.  場合は、ホスト、メッセージ ボックス データベースにメッセージを送信するが、信頼されている認証、メッセージ ボックス データベースは"現状有姿のメッセージ コンテキストに SSID と PID を残します空でない限り、します。 SSID が空の場合、メッセージ ボックス データベースを設定します、SID の呼び出し元のプロセスでは、ホスト SID (HSID)) とも呼ばれます。 ゲスト id PID として設定されます、PID が空の場合  
  
3.  HSID と PID が送信して、MessageBox データベースにメッセージが認証、SSID が信頼済みとして設定されていないホストが設定されている場合は、これらのフィールドが既に読み込まれているかどうかに関係なく、ゲストに設定されます。  
  
> [!IMPORTANT]
>  SSID と PID は、メッセージの元の送信者の下流のプロセスを実行する場合に、信頼された認証として、メッセージが通過するすべてのホストを設定する必要があります。 さらに、場合 SSID と PID がで受信したメッセージは受信し、送信メッセージをオーケストレーションの作成に使用するなどの受信メッセージする必要があります明示的にプロパティとして追加されます、これらをフローするためにメッセージを送信するid。  
  
> [!IMPORTANT]
>  認証が信頼済みパイプラインが実行されているホストを構成した場合、BizTalk Server は、パイプライン、信頼された環境を考慮します。 そのため、認証が信頼済みであるホストで実行されている BizTalk パイプラインに含まれているすべてのカスタム コンポーネントが信頼されてもことを確認することが非常に重要です。  
  
> [!NOTE]
>  認証が信頼済みであるホストと信頼されている認証ではないホストを同じサービス アカウントを使用することはできません。  
  
## <a name="see-also"></a>参照  
 [受信メッセージの認証](../core/inbound-message-authentication.md)   
 [送信メッセージの保護](../core/outbound-message-protection.md)   
 [メッセージの送信者の認証](../core/authenticating-the-sender-of-a-message.md)   
 [メッセージの受信者の承認](../core/authorizing-the-receiver-of-a-message.md)