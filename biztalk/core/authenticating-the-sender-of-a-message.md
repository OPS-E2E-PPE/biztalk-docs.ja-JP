---
title: メッセージの送信者の認証 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- parties, authenticating
- authenticating, authentication required
- messages, authenticating
- security, authenticating
- digital signatures, authenticating
- security, messages
- MessageBox database, authenticating
- authenticating, authentication trust
- messages, message flow
- authenticating, security
- authenticating, party resolution
- authenticating, digital signatures
- authenticating, messages
ms.assetid: 813a2fb9-0346-4129-9cc5-1713f72a491e
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 52b0e69a2799bf5b119093e4ac82773014e979b1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37019088"
---
# <a name="authenticating-the-sender-of-a-message"></a><span data-ttu-id="b981b-102">メッセージの送信者の認証</span><span class="sxs-lookup"><span data-stu-id="b981b-102">Authenticating the Sender of a Message</span></span>
<span data-ttu-id="b981b-103">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、さまざまなメカニズムを使用して、パーティまたはプロセスが本物であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="b981b-103">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] uses different mechanisms to verify that a party is who they claim to be, or that a process is what it claims to be.</span></span> <span data-ttu-id="b981b-104">さらに、プロセスでメッセージの元の送信者の情報を BizTalk Server に中継できるようにするかどうか、また BizTalk Server でパーティをパートナーとして認識するかどうかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="b981b-104">Furthermore, you can specify whether the process can relay to BizTalk Server who the original sender of the message is, and whether BizTalk Server recognizes the party as a partner.</span></span>  
  
 <span data-ttu-id="b981b-105">次の図に、メッセージの送信者の認証および承認に使用できる BizTalk Server のセキュリティ機能を示します。</span><span class="sxs-lookup"><span data-stu-id="b981b-105">The following figure shows the security features in BizTalk Server that enable you to authenticate and authorize the sender of a message.</span></span>  
  
 <span data-ttu-id="b981b-106">![セキュリティで保護されたメッセージのセキュリティ機能](../core/media/ebiz-plan-secoverview.gif "ebiz_plan_secoverview")</span><span class="sxs-lookup"><span data-stu-id="b981b-106">![Security features for secure messages](../core/media/ebiz-plan-secoverview.gif "ebiz_plan_secoverview")</span></span>  
<span data-ttu-id="b981b-107">メッセージ送信の認証および承認に使用する BizTalk Server のセキュリティ機能</span><span class="sxs-lookup"><span data-stu-id="b981b-107">The security features that BizTalk Server uses to authenticate and authorize the send of a message</span></span>  
  
 <span data-ttu-id="b981b-108">メッセージの送信者の認証に使用できる機能は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="b981b-108">The features that enable you to authenticate the sender of a message are:</span></span>  
  
- <span data-ttu-id="b981b-109">**デジタル署名を検証します。**</span><span class="sxs-lookup"><span data-stu-id="b981b-109">**Digital Signature Validation.**</span></span> <span data-ttu-id="b981b-110">: メッセージがデジタル署名されている場合、その署名を使用して送信者の ID を確認します。</span><span class="sxs-lookup"><span data-stu-id="b981b-110">If the message has a digital signature, BizTalk Server uses it to verify the identity of the sender.</span></span> <span data-ttu-id="b981b-111">デジタル署名の検証を構成する方法の詳細については、次を参照してください。[署名付きメッセージの受信用の BizTalk Server を構成する方法](../core/how-to-configure-biztalk-server-for-receiving-signed-messages.md)します。</span><span class="sxs-lookup"><span data-stu-id="b981b-111">For more information about how to configure digital signature validation, see [How to Configure BizTalk Server for Receiving Signed Messages](../core/how-to-configure-biztalk-server-for-receiving-signed-messages.md).</span></span>  
  
- <span data-ttu-id="b981b-112">**パーティの解決。**</span><span class="sxs-lookup"><span data-stu-id="b981b-112">**Party Resolution.**</span></span> <span data-ttu-id="b981b-113">: メッセージ ボックス データベースに挿入されたすべてのメッセージには、発信元が BizTalk Server の内外にかかわらず、パーティ ID (PID) が設定されています。PID は、デジタル証明書か Windows アカウントのいずれかを PID にマッピングすることで決定されます。</span><span class="sxs-lookup"><span data-stu-id="b981b-113">All messages inserted into the MessageBox database, whether originating inside or outside of BizTalk Server, carry a Party ID (PID) that is determined through either the mapping of a digital certificate or a Windows Account to a PID.</span></span> <span data-ttu-id="b981b-114">パーティの解決コンポーネントを構成する方法の詳細については、次を参照してください。[パーティの解決用の証明書を使用して](../core/using-certificates-for-party-resolution.md)します。</span><span class="sxs-lookup"><span data-stu-id="b981b-114">For more information about how to configure party resolution component, see [Using Certificates for Party Resolution](../core/using-certificates-for-party-resolution.md).</span></span>  
  
- <span data-ttu-id="b981b-115">**認証が必要です。**</span><span class="sxs-lookup"><span data-stu-id="b981b-115">**Authentication required.**</span></span> <span data-ttu-id="b981b-116">: 送信ポートでメッセージの送信者を特定できない場合、BizTalk ホストでは、そのメッセージを "Guest" メッセージとして受け取るか、完全に無視することができます。</span><span class="sxs-lookup"><span data-stu-id="b981b-116">If the receive port is not able to determine the sender of the message, a BizTalk Host can either accept it as a "guest" message, or disregard it altogether.</span></span> <span data-ttu-id="b981b-117">不明なパーティは処理されないか、追跡データベースに保存されないため、この機能を使用するとサービスの拒否攻撃からシステムを保護できます。</span><span class="sxs-lookup"><span data-stu-id="b981b-117">This feature enables you to protect your system from Denial of Service attacks, as messages from unknown parties will not be processed or stored in the tracking database.</span></span> <span data-ttu-id="b981b-118">受信ポートの認証オプションの詳細については、次を参照してください。[受信ポートの認証オプションを構成する方法](../core/how-to-configure-authentication-options-for-a-receive-port.md)します。</span><span class="sxs-lookup"><span data-stu-id="b981b-118">For more information about the authentication options for receive ports, see [How to Configure Authentication Options for a Receive Port](../core/how-to-configure-authentication-options-for-a-receive-port.md).</span></span>  
  
- <span data-ttu-id="b981b-119">**信頼されている認証**</span><span class="sxs-lookup"><span data-stu-id="b981b-119">**Authentication Trust.**</span></span> <span data-ttu-id="b981b-120">: 認証が信頼済みに設定されていないホストからメッセージを受信した場合、メッセージ ボックス データベースではメッセージの PID が Guest ID で上書きされ、SSID がホスト インスタンスを実行しているサービス アカウントで上書きされます。</span><span class="sxs-lookup"><span data-stu-id="b981b-120">If the MessageBox database receives a message from a host that you did not identify as authentication trusted, the MessageBox database will overwrite the PID with the guest ID, and the SSID with the service account that the host instance is running as.</span></span> <span data-ttu-id="b981b-121">BizTalk Server では、認証が信頼済みであると確認されたホストは、メッセージ ボックス データベースへキュー送信するときに、メッセージの送信者がこのホスト以外のエンティティであると示すことができます。</span><span class="sxs-lookup"><span data-stu-id="b981b-121">BizTalk Server enables hosts identified as authentication trusted to indicate that the sender of a message that the trusted host is queuing to the MessageBox database is an entity other than the trusted host itself.</span></span> <span data-ttu-id="b981b-122">信頼済み認証の主な目的は、パイプラインで PID を解決して認証や送信パーティの解決で使用されるサービスにその PID を渡せるようにすることと、オーケストレーション アクションの認証で使用されるサービスに送信者の Windows セキュリティ ID (SSID) を転送できるようにすることです。</span><span class="sxs-lookup"><span data-stu-id="b981b-122">The primary purposes of authentication trust are to enable pipelines to resolve to a PID and pass that PID along to consuming services for use in authorization and outbound party resolution, and to enable the transmission of the sender Windows Security ID (SSID) along to consuming services for use in orchestration action authorization.</span></span> <span data-ttu-id="b981b-123">信頼済み認証ホストの詳細については、次を参照してください。[ホスト プロパティを変更する方法](../core/how-to-modify-host-properties.md)します。</span><span class="sxs-lookup"><span data-stu-id="b981b-123">For more information about authentication trusted host, see [How to Modify Host Properties](../core/how-to-modify-host-properties.md).</span></span> <span data-ttu-id="b981b-124">BizTalk Server オーケストレーションをパーティの解決と組み合わせて使用する方法の詳細については、次を参照してください。 [PartyResolution (BizTalk Server サンプル)](../core/partyresolution-biztalk-server-sample.md)します。</span><span class="sxs-lookup"><span data-stu-id="b981b-124">For more information about how to use BizTalk Server orchestrations in conjunction with party resolution, see [PartyResolution (BizTalk Server Sample)](../core/partyresolution-biztalk-server-sample.md).</span></span>  
  
  <span data-ttu-id="b981b-125">このメッセージの送信元、メッセージの元の送信者、またはメッセージの受信者や参照者を把握する必要があるかどうかに応じて、図に示された機能の一部またはすべてを使用できます。</span><span class="sxs-lookup"><span data-stu-id="b981b-125">Depending upon whether you need to know from whom you received this message, the original sender of the message, or the recipient or viewer of your message, you can use some or all of the features shown in the figure.</span></span>  
  
  <span data-ttu-id="b981b-126">メッセージが確かにこちらから送信されていることと、送信中に他のユーザーから読み取られていないことをパートナー側で認識することが重要な場合は、次の方法を使用して、特定の受信者や受信アプリケーションのみがメッセージを受信できるようにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b981b-126">If it is important for your partners to know with certainty that messages are from you and that nobody else can read them while they are in transit, you should consider using the following techniques to help ensure that only the specified recipients and recipient applications receive the messages:</span></span>  
  
- <span data-ttu-id="b981b-127">送信メッセージにデジタル署名を使用して、パートナー側でメッセージの送信者がこちらであることを確認できるようにする。</span><span class="sxs-lookup"><span data-stu-id="b981b-127">Use digital signatures for outbound messages so that your partner can verify that you are the sender of the message.</span></span>  
  
- <span data-ttu-id="b981b-128">送信メッセージを暗号化して、送信中のメッセージを承認されていないパーティに参照されないようにする。</span><span class="sxs-lookup"><span data-stu-id="b981b-128">Encrypt outbound messages to help ensure that unauthorized parties cannot view the message while it is in transit.</span></span>  
  
  <span data-ttu-id="b981b-129">会社にメッセージを送信したユーザーを特定することと、送信中にメッセージが他のユーザーから読み取られていないことを確認することが重要な場合は、次の方法を使用して、特定の受信者や受信アプリケーションのみがメッセージを受信できるようにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b981b-129">If it is important to determine who sent your company a message and that nobody else read it while it was in transit, you should consider using the following techniques to help ensure that only the specified recipients and recipient applications receive the messages:</span></span>  
  
- <span data-ttu-id="b981b-130">デジタル署名付きのメッセージのみを受信許可して、メッセージの送信者を確認できるようにする。</span><span class="sxs-lookup"><span data-stu-id="b981b-130">Make sure BizTalk Server only accepts messages with digital signatures so that you know who sent the message.</span></span>  
  
- <span data-ttu-id="b981b-131">パートナーに公開キー証明書を送信して、パートナーから BizTalk Server に送信するメッセージが暗号化されるようにする。</span><span class="sxs-lookup"><span data-stu-id="b981b-131">Make sure you send your partners the public key certificate for encrypting the messages they send to BizTalk Server.</span></span> <span data-ttu-id="b981b-132">暗号化を使用することで、送信中のメッセージが承認されていないパーティに参照されないようにできます。</span><span class="sxs-lookup"><span data-stu-id="b981b-132">By using encryption, you can help ensure that unauthorized parties cannot view the message while it is in transit.</span></span>  
  
- <span data-ttu-id="b981b-133">受信ポートの認証要求プロパティを使用して、メッセージが既知のパーティから送信されていることを確認する。</span><span class="sxs-lookup"><span data-stu-id="b981b-133">Use the authentication required property in the receive port to ensure the message is from a known party.</span></span>  
  
  <span data-ttu-id="b981b-134">複数のホストでメッセージが処理されると、メッセージの元の送信者がわからなくなる場合があります。</span><span class="sxs-lookup"><span data-stu-id="b981b-134">After more than one host processes the message, it may not be clear who the original sender of the message is.</span></span> <span data-ttu-id="b981b-135">メッセージを送受信するためのアクセス権限を許可する場合など、元の送信者の ID を確認する必要がある場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ではセキュリティ メカニズムを利用することにより、多数のホストを経由して元の送信者の ID を伝達し、その ID を基に下流のホストへのアクセスを検証することができます。</span><span class="sxs-lookup"><span data-stu-id="b981b-135">In cases where you must know the identity of the original sender, for example, when granting access to send or receive a message, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] provides a security mechanism for propagating the identity of the original sender through many hosts in order to validate access to downstream hosts based on that identity.</span></span> <span data-ttu-id="b981b-136">BizTalk Server では、このときに "信頼されている認証" のプロセスが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="b981b-136">In BizTalk Server, this calls process Authentication trust.</span></span> <span data-ttu-id="b981b-137">詳細については、次を参照してください。[認証メッセージの間でプロセスの](../core/authentication-of-messages-between-processes.md)します。</span><span class="sxs-lookup"><span data-stu-id="b981b-137">For more information, see [Authentication of Messages Between Processes](../core/authentication-of-messages-between-processes.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b981b-138">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="b981b-138">In This Section</span></span>  
  
-   [<span data-ttu-id="b981b-139">受信メッセージの認証</span><span class="sxs-lookup"><span data-stu-id="b981b-139">Inbound Message Authentication</span></span>](../core/inbound-message-authentication.md)  
  
-   [<span data-ttu-id="b981b-140">プロセス間のメッセージの認証</span><span class="sxs-lookup"><span data-stu-id="b981b-140">Authentication of Messages Between Processes</span></span>](../core/authentication-of-messages-between-processes.md)  
  
-   [<span data-ttu-id="b981b-141">送信メッセージの保護</span><span class="sxs-lookup"><span data-stu-id="b981b-141">Outbound Message Protection</span></span>](../core/outbound-message-protection.md)