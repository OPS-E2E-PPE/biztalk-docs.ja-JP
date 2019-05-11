---
title: BizTalk Server のセキュリティ機能 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d1473ef87ccab6d035799f37a44b341e58a27a04
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65279945"
---
# <a name="security-features-in-biztalk-server"></a><span data-ttu-id="dc1d4-102">BizTalk Server のセキュリティ機能</span><span class="sxs-lookup"><span data-stu-id="dc1d4-102">Security Features in BizTalk Server</span></span>
<span data-ttu-id="dc1d4-103">Microsoft® BizTalk® Server には、イントラネット内およびインターネット経由の両方で、ドキュメントを送受信するための標準のゲートウェイが用意されています。</span><span class="sxs-lookup"><span data-stu-id="dc1d4-103">Microsoft® BizTalk® Server provides a standard gateway for sending and receiving documents both within an intranet and through the Internet.</span></span> <span data-ttu-id="dc1d4-104">BizTalk Server で送受信されるメッセージには、ビジネス上重要な内容が含まれることがあります。そのため、メッセージの転送時と BizTalk Server での処理および保存時の両方で、メッセージとそれに含まれる情報をセキュリティで保護する方法を検討することが重要です。</span><span class="sxs-lookup"><span data-stu-id="dc1d4-104">Due to the possible business-critical nature of the messages sent to and from BizTalk Server, it is important to consider measures to help secure these messages and the information they contain both as they are in transit and while BizTalk Server processes and stores them.</span></span> <span data-ttu-id="dc1d4-105">このセクションでは、BizTalk Server のセキュリティ機能と使い方にセキュリティ保護するデータと環境に関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="dc1d4-105">This section provides information about the BizTalk Server security features, and how you can use them to help secure your data and environment.</span></span>  
  
 <span data-ttu-id="dc1d4-106">BizTalk Server では、次の方法を使用して、受信メッセージと送信メッセージ、およびランタイムと構成情報をセキュリティで保護し、その他のアプリケーションやシステムと安全に統合します。</span><span class="sxs-lookup"><span data-stu-id="dc1d4-106">BizTalk Server uses the following measures to help secure inbound and outbound messages, to help secure the runtime and configuration information, and to help integrate securely with other applications and systems:</span></span>  
  
 <span data-ttu-id="dc1d4-107">**メッセージ セキュリティ**</span><span class="sxs-lookup"><span data-stu-id="dc1d4-107">**Message security**</span></span>  
  
- <span data-ttu-id="dc1d4-108">メッセージの送信者の認証 :</span><span class="sxs-lookup"><span data-stu-id="dc1d4-108">Authenticating the sender of a message.</span></span> <span data-ttu-id="dc1d4-109">BizTalk Server では、証明書の情報、または Windows 統合セキュリティを使用してメッセージの送信者を認証し、その ID を検証できます。</span><span class="sxs-lookup"><span data-stu-id="dc1d4-109">BizTalk Server can authenticate the sender of a message (either by using the certificate information or Windows integrated Security) in order to validate the identity of the sender of the message.</span></span> <span data-ttu-id="dc1d4-110">詳細については、次を参照してください。[受信メッセージの認証](../core/inbound-message-authentication.md)します。</span><span class="sxs-lookup"><span data-stu-id="dc1d4-110">For more information, see [Inbound Message Authentication](../core/inbound-message-authentication.md).</span></span>  
  
- <span data-ttu-id="dc1d4-111">メッセージの受信者の承認 :</span><span class="sxs-lookup"><span data-stu-id="dc1d4-111">Authorizing of the receiver of a message.</span></span> <span data-ttu-id="dc1d4-112">BizTalk Server では、メッセージの受信後に、メッセージを受信する権限を持つプロセスおよびユーザーを決定できます。</span><span class="sxs-lookup"><span data-stu-id="dc1d4-112">After BizTalk Server receives the message, BizTalk Server can determine what processes and users have permissions to receive the message.</span></span> <span data-ttu-id="dc1d4-113">詳細については、次を参照してください。[メッセージの受信者の承認](../core/authorizing-the-receiver-of-a-message.md)します。</span><span class="sxs-lookup"><span data-stu-id="dc1d4-113">For more information, see [Authorizing the Receiver of a Message](../core/authorizing-the-receiver-of-a-message.md).</span></span>  
  
  <span data-ttu-id="dc1d4-114">**ランタイムと構成のセキュリティ**</span><span class="sxs-lookup"><span data-stu-id="dc1d4-114">**Runtime and configuration security**</span></span>  
  
- <span data-ttu-id="dc1d4-115">**アクセス制御とデータのセキュリティ保護します。**</span><span class="sxs-lookup"><span data-stu-id="dc1d4-115">**Access control and securing data.**</span></span> <span data-ttu-id="dc1d4-116">BizTalk Server では、アクセス制御を使用して、BizTalk Server プロセスに適切な制限が適用されているかどうか、また、ビジネスで重要な情報へのアクセスが制御されているかどうかが確認されます。</span><span class="sxs-lookup"><span data-stu-id="dc1d4-116">BizTalk Server uses access control to ensure that BizTalk Server processes have appropriate limits and that access to business critical information is controlled.</span></span> <span data-ttu-id="dc1d4-117">つまり、ユーザーおよびアカウントが、タスクを実行するための最小限のユーザー権限を持っているかどうかが確認されます。</span><span class="sxs-lookup"><span data-stu-id="dc1d4-117">In other words, BizTalk Server ensures that users and accounts have the least user rights possible to enable them to do their tasks.</span></span> <span data-ttu-id="dc1d4-118">詳細については、次を参照してください。[アクセス制御とデータ セキュリティ](../core/access-control-and-data-security.md)します。</span><span class="sxs-lookup"><span data-stu-id="dc1d4-118">For more information, see [Access Control and Data Security](../core/access-control-and-data-security.md).</span></span>  
  
  <span data-ttu-id="dc1d4-119">**統合セキュリティ**</span><span class="sxs-lookup"><span data-stu-id="dc1d4-119">**Integrated security**</span></span>  
  
- <span data-ttu-id="dc1d4-120">エンタープライズ シングル サインオン :</span><span class="sxs-lookup"><span data-stu-id="dc1d4-120">Enterprise Single Sign-On.</span></span> <span data-ttu-id="dc1d4-121">BizTalk Server では、エンタープライズ シングル サインオン (SSO) を使用して、アダプタ、送信場所および受信場所で必要とされる秘匿性の高い構成情報が暗号化されているかどうかが確認されます。これにより、情報は安全に保存および送信されます。</span><span class="sxs-lookup"><span data-stu-id="dc1d4-121">BizTalk Server uses Enterprise Single Sign-On (SSO) to ensure that it encrypts the sensitive configuration information that the adapters, send, and receive locations require, thus helping to ensure that BizTalk Server stores and transmit this information in a secure manner.</span></span> <span data-ttu-id="dc1d4-122">詳細については、次を参照してください。[を使用して SSO](../core/using-sso.md)します。</span><span class="sxs-lookup"><span data-stu-id="dc1d4-122">For more information, see [Using SSO](../core/using-sso.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc1d4-123">参照</span><span class="sxs-lookup"><span data-stu-id="dc1d4-123">See Also</span></span>  
 <span data-ttu-id="dc1d4-124">[BizTalk Server のシステム アーキテクチャの設計](../core/designing-the-system-architectures-for-biztalk-server.md) </span><span class="sxs-lookup"><span data-stu-id="dc1d4-124">[Designing the System Architectures for BizTalk Server](../core/designing-the-system-architectures-for-biztalk-server.md) </span></span>  
 <span data-ttu-id="dc1d4-125">[エンタープライズ シングル サインオンを実装します。](../core/implementing-enterprise-single-sign-on.md) </span><span class="sxs-lookup"><span data-stu-id="dc1d4-125">[Implementing Enterprise Single Sign-On](../core/implementing-enterprise-single-sign-on.md) </span></span>  
 <span data-ttu-id="dc1d4-126">[メッセージ セキュリティの計画](../core/planning-message-security.md) </span><span class="sxs-lookup"><span data-stu-id="dc1d4-126">[Planning Message Security](../core/planning-message-security.md) </span></span>  
 [<span data-ttu-id="dc1d4-127">アクセス制御とデータ セキュリティ</span><span class="sxs-lookup"><span data-stu-id="dc1d4-127">Access Control and Data Security</span></span>](../core/access-control-and-data-security.md)   
