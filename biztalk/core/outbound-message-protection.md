---
title: "送信メッセージの保護 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- processing, outbound messages
- outbound messages
- security, messages
- authenticating, warnings
- messages, outbound
ms.assetid: 839d3b44-bb44-454b-817c-67b7c8cd74c9
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7adbbae776edee8a4f563e2cd48ee035acc3fd7d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="outbound-message-protection"></a><span data-ttu-id="cdfaa-102">送信メッセージの保護</span><span class="sxs-lookup"><span data-stu-id="cdfaa-102">Outbound Message Protection</span></span>
<span data-ttu-id="cdfaa-103">次の図に、承認されていないパーティに送信メッセージを読み取られないようにするための BizTalk Server のセキュリティ機能を示します。</span><span class="sxs-lookup"><span data-stu-id="cdfaa-103">The following figure shows the security features in BizTalk Server that you use to help protect outbound messages from being read by unauthorized parties.</span></span>  
  
 <span data-ttu-id="cdfaa-104">![送信メッセージの保護に関するセキュリティ機能](../core/media/ebiz-plan-secoverview-auth-outbound.gif "ebiz_plan_secoverview_auth_outbound")</span><span class="sxs-lookup"><span data-stu-id="cdfaa-104">![Security features protecting outbound messages](../core/media/ebiz-plan-secoverview-auth-outbound.gif "ebiz_plan_secoverview_auth_outbound")</span></span>  
<span data-ttu-id="cdfaa-105">送信メッセージの保護に使用される BizTalk Server のセキュリティ機能</span><span class="sxs-lookup"><span data-stu-id="cdfaa-105">Security features BizTalk Server uses to protect outbound messages.</span></span>  
  
 <span data-ttu-id="cdfaa-106">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] からメッセージが送信されると、次の手順でメッセージが安全に送信され、受信側パーティではメッセージの送信者が確認されます。</span><span class="sxs-lookup"><span data-stu-id="cdfaa-106">When [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] sends a message, it takes the following steps to help ensure that it sends the message securely, and that the receiving party can determine the message sender:</span></span>  
  
1.  <span data-ttu-id="cdfaa-107">すべての送信メッセージに署名するように構成されているエンコード コンポーネント (S/MIME など) が送信パイプラインに含まれている場合、パイプラインが実行されているホスト インスタンス サービス アカウントの個人証明書ストアから BizTalk グループの署名証明書が取得されます。その後、メッセージは証明書に関連付けられた秘密キーを使用して署名されます。</span><span class="sxs-lookup"><span data-stu-id="cdfaa-107">If the send pipeline contains an encoding component (such as S/MIME) that is configured to sign all outbound messages, the signing certificate for the BizTalk group is retrieved from the personal certificate store for the host instance service account under which the pipeline is running, and the message is signed using the private key associated with the certificate.</span></span>  
  
2.  <span data-ttu-id="cdfaa-108">すべての送信メッセージを暗号化するように構成されているエンコード コンポーネント (S/MIME など) が送信パイプラインに含まれている場合、暗号化証明書の拇印を使用して "その他のユーザー" 証明書ストアから公開キー証明書が取得され、メッセージはその証明書を使用して暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="cdfaa-108">If the send pipeline contains an encoding component (such as S/MIME) that is configured to encrypt all outbound messages, the encryption certificate thumbprint is used to retrieve the public key certificate from the Other People certificate store, and the message is encrypted using that certificate.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="cdfaa-109">BizTalk 環境ではすべての送信パイプラインで 1 つの署名証明書を使用しますが、この署名証明書が、送信パイプラインが実行されているホストの各ホスト インスタンスのサービス アカウントに設定された証明書ストアで使用できることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cdfaa-109">Although you use one signing certificate for all the send pipelines in your BizTalk environment, you must ensure this signing certificate is available in the certificate store of the service account of each host instance of the hosts where the send pipelines are running.</span></span>  
  
 <span data-ttu-id="cdfaa-110">署名付きメッセージを送信する方法の詳細については、次を参照してください。[署名付きメッセージを送信する、BizTalk Server を構成する方法](../core/how-to-configure-biztalk-server-for-sending-signed-messages.md)です。</span><span class="sxs-lookup"><span data-stu-id="cdfaa-110">For more information about how to send signed messages, see [How to Configure BizTalk Server for Sending Signed Messages](../core/how-to-configure-biztalk-server-for-sending-signed-messages.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cdfaa-111">参照</span><span class="sxs-lookup"><span data-stu-id="cdfaa-111">See Also</span></span>  
 <span data-ttu-id="cdfaa-112">[受信メッセージの認証](../core/inbound-message-authentication.md) </span><span class="sxs-lookup"><span data-stu-id="cdfaa-112">[Inbound Message Authentication](../core/inbound-message-authentication.md) </span></span>  
 <span data-ttu-id="cdfaa-113">[プロセス間でメッセージの認証](../core/authentication-of-messages-between-processes.md) </span><span class="sxs-lookup"><span data-stu-id="cdfaa-113">[Authentication of Messages Between Processes](../core/authentication-of-messages-between-processes.md) </span></span>  
 <span data-ttu-id="cdfaa-114">[メッセージの送信者の認証](../core/authenticating-the-sender-of-a-message.md) </span><span class="sxs-lookup"><span data-stu-id="cdfaa-114">[Authenticating the Sender of a Message](../core/authenticating-the-sender-of-a-message.md) </span></span>  
 <span data-ttu-id="cdfaa-115">[メッセージの受信者の承認](../core/authorizing-the-receiver-of-a-message.md) </span><span class="sxs-lookup"><span data-stu-id="cdfaa-115">[Authorizing the Receiver of a Message](../core/authorizing-the-receiver-of-a-message.md) </span></span>  
 [<span data-ttu-id="cdfaa-116">BizTalk Server が署名されたメッセージで使用する証明書</span><span class="sxs-lookup"><span data-stu-id="cdfaa-116">Certificates that BizTalk Server Uses for Signed Messages</span></span>](../core/certificates-that-biztalk-server-uses-for-signed-messages.md)