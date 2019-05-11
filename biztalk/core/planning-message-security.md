---
title: メッセージ セキュリティの計画 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- planning, security
- security, messages
- security, planning
- messages, security
ms.assetid: c0f93515-a822-425c-9155-270a179d6b61
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 847c53e7e07b4985f5cf2ad1756e3343c335348b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395632"
---
# <a name="planning-message-security"></a><span data-ttu-id="a70c9-102">メッセージ セキュリティの計画</span><span class="sxs-lookup"><span data-stu-id="a70c9-102">Planning Message Security</span></span>
<span data-ttu-id="a70c9-103">社内のセキュリティ ポリシーに基づいて、BizTalk Server 環境で実装する必要があるセキュリティのレベルを決定する次の表に、質問を考慮することがあります。</span><span class="sxs-lookup"><span data-stu-id="a70c9-103">Based on the security policies in your company, you may want to consider the questions in the following table to determine the level of security that you must implement in your BizTalk Server environment.</span></span> <span data-ttu-id="a70c9-104">これらの質問に対する回答には、メッセージングに必要なセキュリティ機能が決まります。</span><span class="sxs-lookup"><span data-stu-id="a70c9-104">The answers to these questions will determine the security features that you need for messaging.</span></span>  
  
|<span data-ttu-id="a70c9-105">質問</span><span class="sxs-lookup"><span data-stu-id="a70c9-105">Question</span></span>|<span data-ttu-id="a70c9-106">BizTalk Server のセキュリティ機能</span><span class="sxs-lookup"><span data-stu-id="a70c9-106">BizTalk Server Security Feature</span></span>|  
|--------------|-------------------------------------|  
|<span data-ttu-id="a70c9-107">**メッセージの受信時**</span><span class="sxs-lookup"><span data-stu-id="a70c9-107">**When receiving a message:**</span></span>||  
|<span data-ttu-id="a70c9-108">メッセージの送信者の id を確認するにはどうするでしょうか。</span><span class="sxs-lookup"><span data-stu-id="a70c9-108">How do you determine the identity of the sender of the message?</span></span>|<span data-ttu-id="a70c9-109">BizTalk パイプラインと署名証明書または Windows セキュリティ ID (SID) で、パーティの解決コンポーネントは、メッセージの送信者を明確に識別するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="a70c9-109">You can use the party resolution component in the BizTalk pipeline and the signing certificate or Windows Security ID (SID) to identify the sender of a message positively.</span></span> <span data-ttu-id="a70c9-110">詳細については、次を参照してください。[受信メッセージの認証](../core/inbound-message-authentication.md)します。</span><span class="sxs-lookup"><span data-stu-id="a70c9-110">For more information, see [Inbound Message Authentication](../core/inbound-message-authentication.md).</span></span>|  
|<span data-ttu-id="a70c9-111">メッセージを送信したパーティをご存知ですか。</span><span class="sxs-lookup"><span data-stu-id="a70c9-111">Do you know the party that sent you the message?</span></span>|<span data-ttu-id="a70c9-112">BizTalk パイプラインのパーティの解決コンポーネントを使用すると、メッセージを送信したパーティがシステムに既に取引先であるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="a70c9-112">You can use the party resolution component in the BizTalk pipeline to determine whether the party that sent you the message is a trading partner already in your system.</span></span> <span data-ttu-id="a70c9-113">詳細については、次を参照してください。[受信メッセージの認証](../core/inbound-message-authentication.md)します。</span><span class="sxs-lookup"><span data-stu-id="a70c9-113">For more information, see [Inbound Message Authentication](../core/inbound-message-authentication.md).</span></span>|  
|<span data-ttu-id="a70c9-114">不明なパーティからメッセージを受信しないようにしますか。</span><span class="sxs-lookup"><span data-stu-id="a70c9-114">Do you want to avoid receiving messages from parties you do not know?</span></span>|<span data-ttu-id="a70c9-115">ポートの認証の必要な機能を使用すると、BizTalk server がわかっているパーティからのメッセージのみを処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a70c9-115">You can use the authentication required feature in the port to require that BizTalk server processes only the messages from parties that you know.</span></span> <span data-ttu-id="a70c9-116">詳細については、次を参照してください。[受信メッセージの認証](../core/inbound-message-authentication.md)します。</span><span class="sxs-lookup"><span data-stu-id="a70c9-116">For more information, see [Inbound Message Authentication](../core/inbound-message-authentication.md).</span></span>|  
|<span data-ttu-id="a70c9-117">**メッセージの送信。**</span><span class="sxs-lookup"><span data-stu-id="a70c9-117">**When sending a message:**</span></span>||  
|<span data-ttu-id="a70c9-118">送信メッセージのプライバシーを確保するにはどうするでしょうか。</span><span class="sxs-lookup"><span data-stu-id="a70c9-118">How do you ensure the privacy of outgoing messages?</span></span>|<span data-ttu-id="a70c9-119">意図したパーティのみがメッセージに読み取ることができることを確認するメッセージを暗号化することができます。</span><span class="sxs-lookup"><span data-stu-id="a70c9-119">You can encrypt the message to ensure that only the intended party can read the message.</span></span> <span data-ttu-id="a70c9-120">詳細については、次を参照してください。[送信メッセージの保護](../core/outbound-message-protection.md)します。</span><span class="sxs-lookup"><span data-stu-id="a70c9-120">For more information, see [Outbound Message Protection](../core/outbound-message-protection.md).</span></span>|  
|<span data-ttu-id="a70c9-121">転送中に、メッセージの改ざんから悪意のあるユーザーを防ぐためにします。</span><span class="sxs-lookup"><span data-stu-id="a70c9-121">How do you prevent malicious users from tampering with the message during transmission?</span></span>|<span data-ttu-id="a70c9-122">デジタル署名を使用して、メッセージの整合性を確保することができます。</span><span class="sxs-lookup"><span data-stu-id="a70c9-122">You can use digital signatures to ensure the integrity of the message.</span></span> <span data-ttu-id="a70c9-123">詳細については、次を参照してください。[送信メッセージの保護](../core/outbound-message-protection.md)します。</span><span class="sxs-lookup"><span data-stu-id="a70c9-123">For more information, see [Outbound Message Protection](../core/outbound-message-protection.md).</span></span>|  
  
## <a name="in-this-section"></a><span data-ttu-id="a70c9-124">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="a70c9-124">In This Section</span></span>  
  
-   [<span data-ttu-id="a70c9-125">メッセージを送受信する際のセキュリティ</span><span class="sxs-lookup"><span data-stu-id="a70c9-125">Security for Sending and Receiving Messages</span></span>](../core/security-for-sending-and-receiving-messages.md)  
  
-   [<span data-ttu-id="a70c9-126">暗号化証明書および署名証明書</span><span class="sxs-lookup"><span data-stu-id="a70c9-126">Encryption and Signing Certificates</span></span>](../core/encryption-and-signing-certificates.md)  
  
-   [<span data-ttu-id="a70c9-127">メッセージの送信者の認証</span><span class="sxs-lookup"><span data-stu-id="a70c9-127">Authenticating the Sender of a Message</span></span>](../core/authenticating-the-sender-of-a-message.md)  
  
-   [<span data-ttu-id="a70c9-128">メッセージの受信者の承認</span><span class="sxs-lookup"><span data-stu-id="a70c9-128">Authorizing the Receiver of a Message</span></span>](../core/authorizing-the-receiver-of-a-message.md)