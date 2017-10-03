---
title: "メッセージ セキュリティの計画 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- planning, security
- security, messages
- security, planning
- messages, security
ms.assetid: c0f93515-a822-425c-9155-270a179d6b61
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5826db8480d378342ee30993f67bbd60e27751d0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="planning-message-security"></a><span data-ttu-id="6eb00-102">メッセージ セキュリティの計画</span><span class="sxs-lookup"><span data-stu-id="6eb00-102">Planning Message Security</span></span>
<span data-ttu-id="6eb00-103">企業内のセキュリティ ポリシーに基づいて、次の表に示す項目を検討し、BizTalk Server 環境に実装する必要があるセキュリティのレベルを決定します。</span><span class="sxs-lookup"><span data-stu-id="6eb00-103">Based on the security policies in your company, you may want to consider the questions in the following table to determine the level of security that you must implement in your BizTalk Server environment.</span></span> <span data-ttu-id="6eb00-104">この項目に対する解答によって、メッセージングに必要なセキュリティ機能が決まります。</span><span class="sxs-lookup"><span data-stu-id="6eb00-104">The answers to these questions will determine the security features that you need for messaging.</span></span>  
  
|<span data-ttu-id="6eb00-105">質問</span><span class="sxs-lookup"><span data-stu-id="6eb00-105">Question</span></span>|<span data-ttu-id="6eb00-106">BizTalk Server のセキュリティ機能</span><span class="sxs-lookup"><span data-stu-id="6eb00-106">BizTalk Server Security Feature</span></span>|  
|--------------|-------------------------------------|  
|<span data-ttu-id="6eb00-107">**メッセージを受信するとき**</span><span class="sxs-lookup"><span data-stu-id="6eb00-107">**When receiving a message:**</span></span>||  
|<span data-ttu-id="6eb00-108">メッセージの送信者をどのように特定するか</span><span class="sxs-lookup"><span data-stu-id="6eb00-108">How do you determine the identity of the sender of the message?</span></span>|<span data-ttu-id="6eb00-109">BizTalk パイプラインのパーティの解決コンポーネントと、署名証明書または Windows セキュリティ ID (SID) を使用すると、メッセージの送信者を明確に識別できます。</span><span class="sxs-lookup"><span data-stu-id="6eb00-109">You can use the party resolution component in the BizTalk pipeline and the signing certificate or Windows Security ID (SID) to identify the sender of a message positively.</span></span> <span data-ttu-id="6eb00-110">詳細については、次を参照してください。[受信メッセージの認証](../core/inbound-message-authentication.md)です。</span><span class="sxs-lookup"><span data-stu-id="6eb00-110">For more information, see [Inbound Message Authentication](../core/inbound-message-authentication.md).</span></span>|  
|<span data-ttu-id="6eb00-111">メッセージ送信元パーティが既存かどうか</span><span class="sxs-lookup"><span data-stu-id="6eb00-111">Do you know the party that sent you the message?</span></span>|<span data-ttu-id="6eb00-112">BizTalk パイプラインのパーティの解決コンポーネントを使用すると、メッセージ送信元パーティがシステム内に既に存在する取引先かどうかを特定できます。</span><span class="sxs-lookup"><span data-stu-id="6eb00-112">You can use the party resolution component in the BizTalk pipeline to determine whether the party that sent you the message is a trading partner already in your system.</span></span> <span data-ttu-id="6eb00-113">詳細については、次を参照してください。[受信メッセージの認証](../core/inbound-message-authentication.md)です。</span><span class="sxs-lookup"><span data-stu-id="6eb00-113">For more information, see [Inbound Message Authentication](../core/inbound-message-authentication.md).</span></span>|  
|<span data-ttu-id="6eb00-114">不明なパーティからのメッセージを受信するかどうか</span><span class="sxs-lookup"><span data-stu-id="6eb00-114">Do you want to avoid receiving messages from parties you do not know?</span></span>|<span data-ttu-id="6eb00-115">ポートで認証を必須とする機能を使用すると、既知のパーティからのメッセージのみを BizTalk サーバーで処理するように指定できます。</span><span class="sxs-lookup"><span data-stu-id="6eb00-115">You can use the authentication required feature in the port to require that BizTalk server processes only the messages from parties that you know.</span></span> <span data-ttu-id="6eb00-116">詳細については、次を参照してください。[受信メッセージの認証](../core/inbound-message-authentication.md)です。</span><span class="sxs-lookup"><span data-stu-id="6eb00-116">For more information, see [Inbound Message Authentication](../core/inbound-message-authentication.md).</span></span>|  
|<span data-ttu-id="6eb00-117">**メッセージの送信。**</span><span class="sxs-lookup"><span data-stu-id="6eb00-117">**When sending a message:**</span></span>||  
|<span data-ttu-id="6eb00-118">送信するメッセージのプライバシーをどのように確保するか</span><span class="sxs-lookup"><span data-stu-id="6eb00-118">How do you ensure the privacy of outgoing messages?</span></span>|<span data-ttu-id="6eb00-119">メッセージを暗号化すると、意図したパーティのみがメッセージを読めるようにできます。</span><span class="sxs-lookup"><span data-stu-id="6eb00-119">You can encrypt the message to ensure that only the intended party can read the message.</span></span> <span data-ttu-id="6eb00-120">詳細については、次を参照してください。[送信のメッセージ保護](../core/outbound-message-protection.md)です。</span><span class="sxs-lookup"><span data-stu-id="6eb00-120">For more information, see [Outbound Message Protection](../core/outbound-message-protection.md).</span></span>|  
|<span data-ttu-id="6eb00-121">送信中に、悪意のあるユーザーによるメッセージの改ざんをどのように防ぐか</span><span class="sxs-lookup"><span data-stu-id="6eb00-121">How do you prevent malicious users from tampering with the message during transmission?</span></span>|<span data-ttu-id="6eb00-122">デジタル署名を使用すると、メッセージの整合性を確保できます。</span><span class="sxs-lookup"><span data-stu-id="6eb00-122">You can use digital signatures to ensure the integrity of the message.</span></span> <span data-ttu-id="6eb00-123">詳細については、次を参照してください。[送信のメッセージ保護](../core/outbound-message-protection.md)です。</span><span class="sxs-lookup"><span data-stu-id="6eb00-123">For more information, see [Outbound Message Protection](../core/outbound-message-protection.md).</span></span>|  
  
## <a name="in-this-section"></a><span data-ttu-id="6eb00-124">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="6eb00-124">In This Section</span></span>  
  
-   [<span data-ttu-id="6eb00-125">メッセージを送受信するためのセキュリティ</span><span class="sxs-lookup"><span data-stu-id="6eb00-125">Security for Sending and Receiving Messages</span></span>](../core/security-for-sending-and-receiving-messages.md)  
  
-   [<span data-ttu-id="6eb00-126">暗号化と証明書の署名</span><span class="sxs-lookup"><span data-stu-id="6eb00-126">Encryption and Signing Certificates</span></span>](../core/encryption-and-signing-certificates.md)  
  
-   [<span data-ttu-id="6eb00-127">メッセージの送信者の認証</span><span class="sxs-lookup"><span data-stu-id="6eb00-127">Authenticating the Sender of a Message</span></span>](../core/authenticating-the-sender-of-a-message.md)  
  
-   [<span data-ttu-id="6eb00-128">メッセージの受信者の承認</span><span class="sxs-lookup"><span data-stu-id="6eb00-128">Authorizing the Receiver of a Message</span></span>](../core/authorizing-the-receiver-of-a-message.md)