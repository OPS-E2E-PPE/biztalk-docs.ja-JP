---
title: メッセージの受信者の承認 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security, messages
- messages, receive authorization
- receive authorization
- messages, security
ms.assetid: c0cdb3ef-ee8e-40a1-9362-13cd26495951
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7317cd9c54568edd2c49df026790ee7a1e70fb2e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22230746"
---
# <a name="authorizing-the-receiver-of-a-message"></a><span data-ttu-id="f8f61-102">メッセージの受信者の承認</span><span class="sxs-lookup"><span data-stu-id="f8f61-102">Authorizing the Receiver of a Message</span></span>
<span data-ttu-id="f8f61-103">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、メッセージの受信を承認する対象のプロセスとパーティを制限できます。</span><span class="sxs-lookup"><span data-stu-id="f8f61-103">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] enables you to limit the processes and parties that you authorize to receive messages.</span></span>  
  
 <span data-ttu-id="f8f61-104">メッセージの受信者を承認するために使用する BizTalk Server のセキュリティ機能を次に示します。</span><span class="sxs-lookup"><span data-stu-id="f8f61-104">The following figure shows the security features in BizTalk Server that you use to authorize the receiver of a message.</span></span>  
  
 <span data-ttu-id="f8f61-105">![メッセージの受信者を承認するセキュリティ機能](../core/media/ebiz-plan-secoverview-authz.gif "ebiz_plan_secoverview_authz")</span><span class="sxs-lookup"><span data-stu-id="f8f61-105">![Security features authorizing the message receiver](../core/media/ebiz-plan-secoverview-authz.gif "ebiz_plan_secoverview_authz")</span></span>  
<span data-ttu-id="f8f61-106">メッセージの受信者の承認で使用する BizTalk Server のセキュリティ機能</span><span class="sxs-lookup"><span data-stu-id="f8f61-106">Security features BizTalk Server uses to authorize the receiver of a message.</span></span>  
  
 <span data-ttu-id="f8f61-107">以下のセキュリティ メカニズムを使用して、送信したメッセージの受信を許可 (承認) する対象を設定できます。</span><span class="sxs-lookup"><span data-stu-id="f8f61-107">You can use the following security mechanisms to establish who has permission (authorization) to receive the messages that you send:</span></span>  
  
-   <span data-ttu-id="f8f61-108">**復号化します。**</span><span class="sxs-lookup"><span data-stu-id="f8f61-108">**Decryption.**</span></span> <span data-ttu-id="f8f61-109">パーティの公開キー証明書のメッセージの暗号化に BizTalk Server に送信する BizTalk Server にメッセージを送信するようにしてください。</span><span class="sxs-lookup"><span data-stu-id="f8f61-109">Make sure the parties that send messages to BizTalk Server have the public key certificate for encrypting messages they send to BizTalk Server.</span></span> <span data-ttu-id="f8f61-110">BizTalk Server では、秘密キー証明書を使用してメッセージを解読します。</span><span class="sxs-lookup"><span data-stu-id="f8f61-110">BizTalk Server uses the private key certificate to decrypt the message.</span></span>  
  
-   <span data-ttu-id="f8f61-111">**承認が表示されます。**</span><span class="sxs-lookup"><span data-stu-id="f8f61-111">**Receive Authorization.**</span></span> <span data-ttu-id="f8f61-112">特定のメッセージを受信できるは、BizTalk Server 環境内でホストを制御するには、この方法を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="f8f61-112">You can use this method to control which hosts within the BizTalk Server environment can receive a given message.</span></span>  
  
-   <span data-ttu-id="f8f61-113">**暗号化します。**</span><span class="sxs-lookup"><span data-stu-id="f8f61-113">**Encryption.**</span></span> <span data-ttu-id="f8f61-114">BizTalk がメッセージを暗号化するときに特定のパーティの公開キー証明書を使用するように設定することで、意図したパーティのみがメッセージを読み取ることができるようにできます。</span><span class="sxs-lookup"><span data-stu-id="f8f61-114">By using the public key certificate from a given party when BizTalk encrypts a message, you can ensure that only the intended party is able to read the message.</span></span>  
  
## <a name="receive-authorization"></a><span data-ttu-id="f8f61-115">受信認証</span><span class="sxs-lookup"><span data-stu-id="f8f61-115">Receive Authorization</span></span>  
 <span data-ttu-id="f8f61-116">受信認証は、指定したメッセージを受信 (サブスクライブ) できるホストの制御に使用します。</span><span class="sxs-lookup"><span data-stu-id="f8f61-116">Receive authorization is the method you can use to control which hosts can receive (subscribe for) a given message.</span></span> <span data-ttu-id="f8f61-117">一致するように、サブスクリプションのプロパティがメッセージの述語として BizTalk Server は、証明書情報を使用して: メッセージ ボックス データベースだけをそのメッセージの暗号化解除証明書を持つホストに必要な承認とマークされたメッセージをルーティングします。</span><span class="sxs-lookup"><span data-stu-id="f8f61-117">BizTalk Server uses the certificate information as a subscription property to match predicates on the message: the MessageBox database only routes messages marked as authorization required to the hosts that have the decryption certificate for that message.</span></span> <span data-ttu-id="f8f61-118">次のシナリオを使用してプロセスを説明します。</span><span class="sxs-lookup"><span data-stu-id="f8f61-118">To illustrate the process, consider the following scenarios:</span></span>  
  
-   <span data-ttu-id="f8f61-119">**暗号化されていないメッセージのルーティング:** ときの BizTalk Server は、送信者が暗号化されていないメッセージを受け取り、BizTalk がメッセージをルーティングする方法についての復号化の制限はありません。</span><span class="sxs-lookup"><span data-stu-id="f8f61-119">**Routing an un-encrypted message:** When BizTalk Server receives a message that the sender did not encrypt, there is no decryption limitation as to how BizTalk routes the message.</span></span> <span data-ttu-id="f8f61-120">受信認証証明書が構成されているホストと受信承認証明書が構成されていないホストの両方でメッセージを受信できます。</span><span class="sxs-lookup"><span data-stu-id="f8f61-120">Both hosts with and hosts without receive authorization certificates configured can receive the message.</span></span>  
  
-   <span data-ttu-id="f8f61-121">**暗号化されたメッセージのルーティング:** 暗号化されたメッセージが到着すると、受信パイプラインは、メッセージを解読するデコード コンポーネントを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="f8f61-121">**Routing an encrypted message:** When an encrypted message arrives, the receiving pipeline must contain a decoding component that decrypts the message.</span></span> <span data-ttu-id="f8f61-122">BizTalk Server でメッセージが解読されルーティングされるときに、メッセージ ボックス データベースのサブスクリプション メカニズムでは、メッセージの解読に使用された証明書の拇印が証拠として使用されます。この証明書が構成されているホストのみがメッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="f8f61-122">When BizTalk Server routes a message after it is decrypted, BizTalk uses the certificate thumbprint used to decrypt the message as evidence in the MessageBox database subscription mechanism, and only those hosts configured with that certificate receive the message.</span></span>  
  
 <span data-ttu-id="f8f61-123">受信認証を使用する場合は、メッセージの受信を承認するホストのプロパティに解読証明書の拇印を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f8f61-123">If you want to use receive authorization, you must provide the thumbprint of the decryption certificate in the properties of the host that you want to authorize to receive the message.</span></span> <span data-ttu-id="f8f61-124">詳細については、承認を受け取るを参照してください[ホストのプロパティを変更する方法](../core/how-to-modify-host-properties.md)です。</span><span class="sxs-lookup"><span data-stu-id="f8f61-124">For more information about receive authorization, see [How to Modify Host Properties](../core/how-to-modify-host-properties.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8f61-125">参照</span><span class="sxs-lookup"><span data-stu-id="f8f61-125">See Also</span></span>  
 <span data-ttu-id="f8f61-126">[受信メッセージの認証](../core/inbound-message-authentication.md) </span><span class="sxs-lookup"><span data-stu-id="f8f61-126">[Inbound Message Authentication](../core/inbound-message-authentication.md) </span></span>  
 <span data-ttu-id="f8f61-127">[プロセス間でメッセージの認証](../core/authentication-of-messages-between-processes.md) </span><span class="sxs-lookup"><span data-stu-id="f8f61-127">[Authentication of Messages Between Processes](../core/authentication-of-messages-between-processes.md) </span></span>  
 <span data-ttu-id="f8f61-128">[送信メッセージの保護](../core/outbound-message-protection.md) </span><span class="sxs-lookup"><span data-stu-id="f8f61-128">[Outbound Message Protection](../core/outbound-message-protection.md) </span></span>  
 <span data-ttu-id="f8f61-129">[メッセージの送信者の認証](../core/authenticating-the-sender-of-a-message.md) </span><span class="sxs-lookup"><span data-stu-id="f8f61-129">[Authenticating the Sender of a Message](../core/authenticating-the-sender-of-a-message.md) </span></span>  
 [<span data-ttu-id="f8f61-130">メッセージ セキュリティの計画</span><span class="sxs-lookup"><span data-stu-id="f8f61-130">Planning Message Security</span></span>](../core/planning-message-security.md)