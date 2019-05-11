---
title: 送信メッセージの保護 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- processing, outbound messages
- outbound messages
- security, messages
- authenticating, warnings
- messages, outbound
ms.assetid: 839d3b44-bb44-454b-817c-67b7c8cd74c9
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c451fd13e780c6530fcad7848b11528af3bc1968
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393438"
---
# <a name="outbound-message-protection"></a><span data-ttu-id="d7ec4-102">送信メッセージの保護</span><span class="sxs-lookup"><span data-stu-id="d7ec4-102">Outbound Message Protection</span></span>
<span data-ttu-id="d7ec4-103">次の図は、送信メッセージが承認されていないパーティによって読み取られることを防ぐために使用する BizTalk Server のセキュリティ機能を示します。</span><span class="sxs-lookup"><span data-stu-id="d7ec4-103">The following figure shows the security features in BizTalk Server that you use to help protect outbound messages from being read by unauthorized parties.</span></span>  
  
 <span data-ttu-id="d7ec4-104">![送信メッセージの保護のセキュリティ機能](../core/media/ebiz-plan-secoverview-auth-outbound.gif "ebiz_plan_secoverview_auth_outbound")</span><span class="sxs-lookup"><span data-stu-id="d7ec4-104">![Security features protecting outbound messages](../core/media/ebiz-plan-secoverview-auth-outbound.gif "ebiz_plan_secoverview_auth_outbound")</span></span>  
<span data-ttu-id="d7ec4-105">BizTalk Server のセキュリティ機能では、送信メッセージを保護します。</span><span class="sxs-lookup"><span data-stu-id="d7ec4-105">Security features BizTalk Server uses to protect outbound messages.</span></span>  
  
 <span data-ttu-id="d7ec4-106">ときに[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安全に、メッセージを送信して、受信側パーティがメッセージの送信者を判断できることを確保しやすく、次の手順を要するメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="d7ec4-106">When [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] sends a message, it takes the following steps to help ensure that it sends the message securely, and that the receiving party can determine the message sender:</span></span>  
  
1.  <span data-ttu-id="d7ec4-107">送信パイプラインには、すべての送信メッセージに署名するように構成されているエンコード コンポーネント (S/MIME) などが含まれる場合、BizTalk グループの署名証明書は、するには、ホスト インスタンス サービス アカウントの個人用証明書ストアから取得されます。パイプラインが実行されていると、メッセージの署名証明書に関連付けられている秘密キーを使用します。</span><span class="sxs-lookup"><span data-stu-id="d7ec4-107">If the send pipeline contains an encoding component (such as S/MIME) that is configured to sign all outbound messages, the signing certificate for the BizTalk group is retrieved from the personal certificate store for the host instance service account under which the pipeline is running, and the message is signed using the private key associated with the certificate.</span></span>  
  
2.  <span data-ttu-id="d7ec4-108">その他のユーザーの証明書ストア、およびメッセージから公開キー証明書を取得する暗号化証明書の拇印を使用する場合は、送信パイプラインには、すべての送信メッセージを暗号化するように構成されているエンコード コンポーネント (S/MIME) などが含まれています、その証明書を使用して暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="d7ec4-108">If the send pipeline contains an encoding component (such as S/MIME) that is configured to encrypt all outbound messages, the encryption certificate thumbprint is used to retrieve the public key certificate from the Other People certificate store, and the message is encrypted using that certificate.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="d7ec4-109">すべての送信パイプラインの 1 つの署名証明書を使用して、BizTalk 環境では、送信パイプラインは、ホストの場合は、各ホスト インスタンスのサービス アカウントの証明書ストアにこの署名証明書があることを確認する必要があります。実行中です。</span><span class="sxs-lookup"><span data-stu-id="d7ec4-109">Although you use one signing certificate for all the send pipelines in your BizTalk environment, you must ensure this signing certificate is available in the certificate store of the service account of each host instance of the hosts where the send pipelines are running.</span></span>  
  
 <span data-ttu-id="d7ec4-110">署名付きメッセージを送信する方法の詳細については、次を参照してください。[署名付きメッセージの送信用の BizTalk Server を構成する方法](../core/how-to-configure-biztalk-server-for-sending-signed-messages.md)します。</span><span class="sxs-lookup"><span data-stu-id="d7ec4-110">For more information about how to send signed messages, see [How to Configure BizTalk Server for Sending Signed Messages](../core/how-to-configure-biztalk-server-for-sending-signed-messages.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7ec4-111">参照</span><span class="sxs-lookup"><span data-stu-id="d7ec4-111">See Also</span></span>  
 <span data-ttu-id="d7ec4-112">[受信メッセージの認証](../core/inbound-message-authentication.md) </span><span class="sxs-lookup"><span data-stu-id="d7ec4-112">[Inbound Message Authentication](../core/inbound-message-authentication.md) </span></span>  
 <span data-ttu-id="d7ec4-113">[プロセス間のメッセージの認証](../core/authentication-of-messages-between-processes.md) </span><span class="sxs-lookup"><span data-stu-id="d7ec4-113">[Authentication of Messages Between Processes](../core/authentication-of-messages-between-processes.md) </span></span>  
 <span data-ttu-id="d7ec4-114">[メッセージの送信者の認証](../core/authenticating-the-sender-of-a-message.md) </span><span class="sxs-lookup"><span data-stu-id="d7ec4-114">[Authenticating the Sender of a Message](../core/authenticating-the-sender-of-a-message.md) </span></span>  
 <span data-ttu-id="d7ec4-115">[メッセージの受信者の承認](../core/authorizing-the-receiver-of-a-message.md) </span><span class="sxs-lookup"><span data-stu-id="d7ec4-115">[Authorizing the Receiver of a Message](../core/authorizing-the-receiver-of-a-message.md) </span></span>  
 [<span data-ttu-id="d7ec4-116">BizTalk Server で署名付きメッセージに使用する証明書</span><span class="sxs-lookup"><span data-stu-id="d7ec4-116">Certificates that BizTalk Server Uses for Signed Messages</span></span>](../core/certificates-that-biztalk-server-uses-for-signed-messages.md)