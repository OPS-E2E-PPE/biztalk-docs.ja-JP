---
title: メッセージの受信者の承認 |Microsoft Docs
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
ms.openlocfilehash: 3ca2b0b6474421bc474cf30ae8c8817bc5f8e10d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358752"
---
# <a name="authorizing-the-receiver-of-a-message"></a><span data-ttu-id="18df6-102">メッセージの受信者の承認</span><span class="sxs-lookup"><span data-stu-id="18df6-102">Authorizing the Receiver of a Message</span></span>
<span data-ttu-id="18df6-103">Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]プロセスとメッセージの受信を承認するパーティを制限することができます。</span><span class="sxs-lookup"><span data-stu-id="18df6-103">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] enables you to limit the processes and parties that you authorize to receive messages.</span></span>  
  
 <span data-ttu-id="18df6-104">次の図は、メッセージの受信者を承認するために使用する BizTalk Server のセキュリティ機能を示します。</span><span class="sxs-lookup"><span data-stu-id="18df6-104">The following figure shows the security features in BizTalk Server that you use to authorize the receiver of a message.</span></span>  
  
 <span data-ttu-id="18df6-105">![メッセージの受信者を承認するセキュリティ機能](../core/media/ebiz-plan-secoverview-authz.gif "ebiz_plan_secoverview_authz")</span><span class="sxs-lookup"><span data-stu-id="18df6-105">![Security features authorizing the message receiver](../core/media/ebiz-plan-secoverview-authz.gif "ebiz_plan_secoverview_authz")</span></span>  
<span data-ttu-id="18df6-106">BizTalk Server のセキュリティ機能は、メッセージの受信者を承認するために使用します。</span><span class="sxs-lookup"><span data-stu-id="18df6-106">Security features BizTalk Server uses to authorize the receiver of a message.</span></span>  
  
 <span data-ttu-id="18df6-107">(承認) を送信するメッセージを受信するのにためのアクセス許可を持っているユーザーを確立するために、次のセキュリティ メカニズムを使用できます。</span><span class="sxs-lookup"><span data-stu-id="18df6-107">You can use the following security mechanisms to establish who has permission (authorization) to receive the messages that you send:</span></span>  
  
-   <span data-ttu-id="18df6-108">**復号化します。**</span><span class="sxs-lookup"><span data-stu-id="18df6-108">**Decryption.**</span></span> <span data-ttu-id="18df6-109">パーティの公開キー証明書メッセージの暗号化に BizTalk Server に送信する BizTalk Server にメッセージを送信するようにしてください。</span><span class="sxs-lookup"><span data-stu-id="18df6-109">Make sure the parties that send messages to BizTalk Server have the public key certificate for encrypting messages they send to BizTalk Server.</span></span> <span data-ttu-id="18df6-110">BizTalk Server では、秘密キー証明書を使用して、メッセージの暗号化を解除します。</span><span class="sxs-lookup"><span data-stu-id="18df6-110">BizTalk Server uses the private key certificate to decrypt the message.</span></span>  
  
-   <span data-ttu-id="18df6-111">**承認が表示されます。**</span><span class="sxs-lookup"><span data-stu-id="18df6-111">**Receive Authorization.**</span></span> <span data-ttu-id="18df6-112">コントロールの特定のメッセージを受信できるは、BizTalk Server 環境内でホストするには、このメソッドを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="18df6-112">You can use this method to control which hosts within the BizTalk Server environment can receive a given message.</span></span>  
  
-   <span data-ttu-id="18df6-113">**暗号化。**</span><span class="sxs-lookup"><span data-stu-id="18df6-113">**Encryption.**</span></span> <span data-ttu-id="18df6-114">によって指定された関係者から公開キー証明書を使用して、BizTalk がメッセージを暗号化するときに、意図したパーティのみがメッセージを読み取ることがあることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="18df6-114">By using the public key certificate from a given party when BizTalk encrypts a message, you can ensure that only the intended party is able to read the message.</span></span>  
  
## <a name="receive-authorization"></a><span data-ttu-id="18df6-115">受信認証</span><span class="sxs-lookup"><span data-stu-id="18df6-115">Receive Authorization</span></span>  
 <span data-ttu-id="18df6-116">受信認証は、受信できるホスト コントロールを使用することができます (サブスクライブ) の特定のメッセージ。</span><span class="sxs-lookup"><span data-stu-id="18df6-116">Receive authorization is the method you can use to control which hosts can receive (subscribe for) a given message.</span></span> <span data-ttu-id="18df6-117">BizTalk Server メッセージの述語のサブスクリプションのプロパティと一致するように証明書情報を使用して: メッセージ ボックス データベースのみをそのメッセージの復号化証明書を持つホストに必要な承認としてマークされたメッセージをルーティングします。</span><span class="sxs-lookup"><span data-stu-id="18df6-117">BizTalk Server uses the certificate information as a subscription property to match predicates on the message: the MessageBox database only routes messages marked as authorization required to the hosts that have the decryption certificate for that message.</span></span> <span data-ttu-id="18df6-118">プロセスを示すためには、次のシナリオを検討してください。</span><span class="sxs-lookup"><span data-stu-id="18df6-118">To illustrate the process, consider the following scenarios:</span></span>  
  
- <span data-ttu-id="18df6-119">**暗号化されていないメッセージのルーティング。** BizTalk Server では、暗号化されていない送信者がメッセージを受信したときに、BizTalk がメッセージをルーティングする方法に関して、解読の制限はありません。</span><span class="sxs-lookup"><span data-stu-id="18df6-119">**Routing an un-encrypted message:** When BizTalk Server receives a message that the sender did not encrypt, there is no decryption limitation as to how BizTalk routes the message.</span></span> <span data-ttu-id="18df6-120">ホストとホストなしの両方の受信認証証明書を構成には、メッセージが表示されることができます。</span><span class="sxs-lookup"><span data-stu-id="18df6-120">Both hosts with and hosts without receive authorization certificates configured can receive the message.</span></span>  
  
- <span data-ttu-id="18df6-121">**暗号化されたメッセージをルーティングするには。** 暗号化されたメッセージが到着すると、受信パイプラインは、メッセージを解読するデコード コンポーネントを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="18df6-121">**Routing an encrypted message:** When an encrypted message arrives, the receiving pipeline must contain a decoding component that decrypts the message.</span></span> <span data-ttu-id="18df6-122">解読され、BizTalk メッセージ ボックス データベースのサブスクリプション メカニズムで証拠として、メッセージを復号化するために使用する証明書の拇印を使用して、その証明書で構成されているホストのみを受信した後に、BizTalk Server がメッセージをルーティングするときに、メッセージ。</span><span class="sxs-lookup"><span data-stu-id="18df6-122">When BizTalk Server routes a message after it is decrypted, BizTalk uses the certificate thumbprint used to decrypt the message as evidence in the MessageBox database subscription mechanism, and only those hosts configured with that certificate receive the message.</span></span>  
  
  <span data-ttu-id="18df6-123">する場合を使用する承認の受信、メッセージの受信を承認するホストのプロパティに解読証明書の拇印を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="18df6-123">If you want to use receive authorization, you must provide the thumbprint of the decryption certificate in the properties of the host that you want to authorize to receive the message.</span></span> <span data-ttu-id="18df6-124">詳細については、承認を受信を参照してください。[ホスト プロパティを変更する方法](../core/how-to-modify-host-properties.md)します。</span><span class="sxs-lookup"><span data-stu-id="18df6-124">For more information about receive authorization, see [How to Modify Host Properties](../core/how-to-modify-host-properties.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18df6-125">参照</span><span class="sxs-lookup"><span data-stu-id="18df6-125">See Also</span></span>  
 <span data-ttu-id="18df6-126">[受信メッセージの認証](../core/inbound-message-authentication.md) </span><span class="sxs-lookup"><span data-stu-id="18df6-126">[Inbound Message Authentication](../core/inbound-message-authentication.md) </span></span>  
 <span data-ttu-id="18df6-127">[プロセス間のメッセージの認証](../core/authentication-of-messages-between-processes.md) </span><span class="sxs-lookup"><span data-stu-id="18df6-127">[Authentication of Messages Between Processes](../core/authentication-of-messages-between-processes.md) </span></span>  
 <span data-ttu-id="18df6-128">[送信メッセージの保護](../core/outbound-message-protection.md) </span><span class="sxs-lookup"><span data-stu-id="18df6-128">[Outbound Message Protection](../core/outbound-message-protection.md) </span></span>  
 <span data-ttu-id="18df6-129">[メッセージの送信者の認証](../core/authenticating-the-sender-of-a-message.md) </span><span class="sxs-lookup"><span data-stu-id="18df6-129">[Authenticating the Sender of a Message](../core/authenticating-the-sender-of-a-message.md) </span></span>  
 [<span data-ttu-id="18df6-130">メッセージ セキュリティの計画</span><span class="sxs-lookup"><span data-stu-id="18df6-130">Planning Message Security</span></span>](../core/planning-message-security.md)