---
title: "BizTalk Server のセキュリティ機能 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BizTalk Server, security
- Master Secret server, security
- security, Master Secret server
- security, runtime
- security, data
- deploying, security
- security, configuring
- runtime, security
- security, security features
- security, messages
- security, access control
- security, about security
- access control
- security, deploying
- data, security
- messages, security
ms.assetid: 5ab15023-fa71-439e-b3aa-420fe28806fa
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 50371f0b0c5d5a56fc9f7c392e4ee8d69e637b47
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="security-features-in-biztalk-server"></a>BizTalk Server のセキュリティ機能
Microsoft® BizTalk® Server には、イントラネット内およびインターネット経由の両方で、ドキュメントを送受信するための標準のゲートウェイが用意されています。 BizTalk Server で送受信されるメッセージには、ビジネス上重要な内容が含まれることがあります。そのため、メッセージの転送時と BizTalk Server での処理および保存時の両方で、メッセージとそれに含まれる情報をセキュリティで保護する方法を検討することが重要です。 このセクションでは、BizTalk Server のセキュリティ機能、および使用方法についてすることができますに保護するに、データと環境情報を提供します。  
  
 BizTalk Server では、次の方法を使用して、受信メッセージと送信メッセージ、およびランタイムと構成情報をセキュリティで保護し、その他のアプリケーションやシステムと安全に統合します。  
  
 **メッセージ セキュリティ**  
  
-   メッセージの送信者の認証 : BizTalk Server では、証明書の情報、または Windows 統合セキュリティを使用してメッセージの送信者を認証し、その ID を検証できます。 詳細については、次を参照してください。[受信メッセージの認証](../core/inbound-message-authentication.md)です。  
  
-   メッセージの受信者の承認 : BizTalk Server では、メッセージの受信後に、メッセージを受信する権限を持つプロセスおよびユーザーを決定できます。 詳細については、次を参照してください。[メッセージの受信者の承認](../core/authorizing-the-receiver-of-a-message.md)です。  
  
 **ランタイムと構成のセキュリティ**  
  
-   **アクセス制御とデータを保護します。** BizTalk Server では、アクセス制御を使用して、BizTalk Server プロセスに適切な制限が適用されているかどうか、また、ビジネスで重要な情報へのアクセスが制御されているかどうかが確認されます。 つまり、ユーザーおよびアカウントが、タスクを実行するための最小限のユーザー権限を持っているかどうかが確認されます。 詳細については、次を参照してください。[アクセス制御とデータ セキュリティ](../core/access-control-and-data-security.md)です。  
  
 **統合セキュリティ**  
  
-   エンタープライズ シングル サインオン : BizTalk Server では、エンタープライズ シングル サインオン (SSO) を使用して、アダプタ、送信場所および受信場所で必要とされる秘匿性の高い構成情報が暗号化されているかどうかが確認されます。これにより、情報は安全に保存および送信されます。 詳細については、次を参照してください。[を使用して SSO](../core/using-sso.md)です。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server のシステム アーキテクチャの設計](../core/designing-the-system-architectures-for-biztalk-server.md)   
 [エンタープライズ シングル サインオンを実装します。](../core/implementing-enterprise-single-sign-on.md)   
 [メッセージ セキュリティの計画](../core/planning-message-security.md)   
 [アクセス制御とデータのセキュリティ](../core/access-control-and-data-security.md)   
