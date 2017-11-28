---
title: "メッセージを送受信するためのセキュリティ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, receiving
- messages, sending
- messages, processing
- security, messages
- security, message processing
- messages, security
ms.assetid: 9bcd01e4-245a-4f4c-b65c-89d7cd3d1b68
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e1328eb98cbf94b85cda16eda431da197c6d0126
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="security-for-sending-and-receiving-messages"></a><span data-ttu-id="91d69-102">メッセージを送受信する際のセキュリティ</span><span class="sxs-lookup"><span data-stu-id="91d69-102">Security for Sending and Receiving Messages</span></span>
<span data-ttu-id="91d69-103">次の図に、BizTalk Server でメッセージが受信および処理され、別のアプリケーションやパートナーに送信されるときの状況を示します。</span><span class="sxs-lookup"><span data-stu-id="91d69-103">The following figure shows what happens to a message as BizTalk Server receives it, processes it, and sends it to another application or partner.</span></span>  
  
 <span data-ttu-id="91d69-104">![セキュリティで保護されたメッセージのセキュリティ機能](../core/media/ebiz-plan-secoverview.gif "ebiz_plan_secoverview")</span><span class="sxs-lookup"><span data-stu-id="91d69-104">![Security features for secure messages](../core/media/ebiz-plan-secoverview.gif "ebiz_plan_secoverview")</span></span>  
<span data-ttu-id="91d69-105">メッセージの有効期間全体で使用されるセキュリティ機能</span><span class="sxs-lookup"><span data-stu-id="91d69-105">Security features used throughout the lifetime of a message</span></span>  
  
1.  <span data-ttu-id="91d69-106">アダプタの受信場所でメッセージが受信されます。</span><span class="sxs-lookup"><span data-stu-id="91d69-106">The receive location for the adapter receives the message.</span></span> <span data-ttu-id="91d69-107">プロトコルに応じて、アダプタではプロトコル レベルの送信者の認証が行われ、メッセージの送信者を表す Widnows ユーザー アカウントが識別されます。</span><span class="sxs-lookup"><span data-stu-id="91d69-107">Depending on the protocol, the adapter does protocol-level authentication of the sender to identify a Windows user account that represents the sender of the message.</span></span>  
  
2.  <span data-ttu-id="91d69-108">次に、アダプタからパイプラインにメッセージが渡されます。アダプタで認証が行われていない場合、メッセージ レベルでの認証が行われます。</span><span class="sxs-lookup"><span data-stu-id="91d69-108">The adapter then passes the message to the pipeline, where message-level authentication takes place if it has not already happened in the adapter.</span></span>  
  
    1.  <span data-ttu-id="91d69-109">デコード ステージでは、パイプラインでメッセージが解読され、メッセージに添付された証明書、またはローカル コンピュータの "ほかの人" 証明書ストアに構成された証明書を使用して、署名の有効性が確認されます。</span><span class="sxs-lookup"><span data-stu-id="91d69-109">In the Decode stage, the pipeline decrypts the message and verifies the validity of the signature with the certificate attached to the message, or the one configured in the Other People certificate store of the local computer.</span></span> <span data-ttu-id="91d69-110">パイプラインで署名が検証された後、デコード コンポーネントでは、信頼済みのルート証明機関 (CA) までさかのぼって証明書チェーンが検証されます。</span><span class="sxs-lookup"><span data-stu-id="91d69-110">After the pipeline validates the signature, the decoding component validates the certificate chain up to a trusted root Certificate Authority (CA).</span></span> <span data-ttu-id="91d69-111">S/MIME メッセージをデコードするようにパイプラインを構成し、送信者が S/MIME を使用してメッセージを暗号化している場合は、MIME/SMIME デコーダでメッセージの署名が確認され、証明書を使用して送信者が識別されます。</span><span class="sxs-lookup"><span data-stu-id="91d69-111">If you configure the pipeline to decode S/MIME messages, and the sender encrypted the message using S/MIME, the MIME/SMIME decoder verifies the signature of the message, and uses the certificate to identify the sender.</span></span> <span data-ttu-id="91d69-112">MIME/SMIME デコーダー パイプライン コンポーネントを使用する方法の詳細については、次を参照してください。[メッセージのセキュリティを実装する](../core/implementing-message-security.md)です。</span><span class="sxs-lookup"><span data-stu-id="91d69-112">For more information about how to use MIME/SMIME decoder pipeline components, see [Implementing Message Security](../core/implementing-message-security.md).</span></span>  
  
    2.  <span data-ttu-id="91d69-113">パーティの解決ステージでは、証明書情報とプロトコル レベルの認証で取得された送信者のセキュリティ ID (SSID) を使用して、メッセージの送信者がシステムで認識されたパーティであるかどうかが確認されます。</span><span class="sxs-lookup"><span data-stu-id="91d69-113">In the Party Resolution stage, BizTalk Server uses the certificate information and the Sender Security ID (SSID) obtained from protocol-level authentication to determine whether the sender of the message is a recognized party in the system.</span></span> <span data-ttu-id="91d69-114">送信者の SSID は、アダプタで認証されたユーザーの修飾名です。</span><span class="sxs-lookup"><span data-stu-id="91d69-114">The Sender SSID is the qualified name of the user authenticated by the adapter.</span></span> <span data-ttu-id="91d69-115">たとえば、Windows 認証を使用する HTTP アダプタでメッセージが受信された場合、送信者の SSID は domain\username になります。</span><span class="sxs-lookup"><span data-stu-id="91d69-115">For example.</span></span> <span data-ttu-id="91d69-116">メッセージにはパーティ ID (PID) が割り当てられますが、これは認識済みパーティのパーティ IDか、Guest ID になります。</span><span class="sxs-lookup"><span data-stu-id="91d69-116">If BizTalk Server receives the message by way of the HTTP adapter using Windows authentication, then the sender SSID is domain\username.</span></span> <span data-ttu-id="91d69-117">BizTalk Server では、認識されたパーティのパーティ ID または guest ID のいずれかであると、メッセージをパーティ ID (PID) を割り当てます</span><span class="sxs-lookup"><span data-stu-id="91d69-117">BizTalk Server assigns a Party ID (PID) to the message, which is either the party ID of a recognized party, or a guest ID.</span></span> <span data-ttu-id="91d69-118">パーティの解決コンポーネントを使用する方法の詳細については、次を参照してください。[パーティの解決用の証明書を使用して](../core/using-certificates-for-party-resolution.md)です。</span><span class="sxs-lookup"><span data-stu-id="91d69-118">For more information about how to use party resolution component, see [Using Certificates for Party Resolution](../core/using-certificates-for-party-resolution.md).</span></span>  
  
    3.  <span data-ttu-id="91d69-119">送信者を認証してシステムの既知のパーティに解決するように受信ポートを構成したときに、メッセージ送信者の PID が見つからない場合は、受信ポートの構成に従ってメッセージが削除されるか中断されます。</span><span class="sxs-lookup"><span data-stu-id="91d69-119">If you configured the receiving port to require the sender to be authenticated to a known party in the system, and BizTalk Server is not able to find a PID for the sender of the message, then BizTalk Server drops or suspends the message depending on the configuration of the receive port.</span></span> <span data-ttu-id="91d69-120">この機能により、サービスの拒否攻撃が緩和されます。</span><span class="sxs-lookup"><span data-stu-id="91d69-120">BizTalk Server provides this feature to mitigate Denial of Service attacks.</span></span> <span data-ttu-id="91d69-121">受信ポートの認証オプションの詳細については、次を参照してください。[受信ポートの認証オプションを構成する方法](../core/how-to-configure-authentication-options-for-a-receive-port.md)です。</span><span class="sxs-lookup"><span data-stu-id="91d69-121">For more information about the authentication options for receive ports, see [How to Configure Authentication Options for a Receive Port](../core/how-to-configure-authentication-options-for-a-receive-port.md).</span></span>  
  
3.  <span data-ttu-id="91d69-122">パイプラインでメッセージが認証された後、メッセージ ボックス データベースにメッセージが送信されます。</span><span class="sxs-lookup"><span data-stu-id="91d69-122">After the pipeline authenticates the message, it sends the message to the MessageBox database.</span></span>  
  
    1.  <span data-ttu-id="91d69-123">パイプラインが実行されているキュー送信ホストが信頼済みの認証ホストとして識別されなかった場合、メッセージ ボックス データベースではメッセージの PID が Guest ID で上書きされ、SSID がキュー送信ホスト インスタンスを実行しているサービス アカウントで上書きされます。</span><span class="sxs-lookup"><span data-stu-id="91d69-123">If you did not identify the enqueuing host (on which the pipeline is running) as an authentication trusted host, the MessageBox database overwrites the PID with the guest ID, and the SSID with the service account that the enqueuing host instance is running as.</span></span> <span data-ttu-id="91d69-124">信頼済み認証ホストの詳細については、次を参照してください。[認証メッセージの間でプロセスの](../core/authentication-of-messages-between-processes.md)します。</span><span class="sxs-lookup"><span data-stu-id="91d69-124">For more information about authentication trusted host, see [Authentication of Messages Between Processes](../core/authentication-of-messages-between-processes.md).</span></span> <span data-ttu-id="91d69-125">信頼済み認証ホストを構成する方法の詳細については、次を参照してください。[ホストのプロパティを変更する方法](../core/how-to-modify-host-properties.md)です。</span><span class="sxs-lookup"><span data-stu-id="91d69-125">For more information about how to configure authentication trusted host, see [How to Modify Host Properties](../core/how-to-modify-host-properties.md).</span></span>  
  
    2.  <span data-ttu-id="91d69-126">パイプラインが実行されているホストが信頼されている認証として指定されている場合、メッセージ ボックス データベースでは PID および SSID が信頼されます。下流のプロセスでこの情報を使用して、メッセージの元の送信者の認証や承認を行えるように、情報はメッセージのコンテキストに残されます。</span><span class="sxs-lookup"><span data-stu-id="91d69-126">If the host on which the pipeline is running is marked as authentication trusted, the MessageBox database trusts the PID and SSID, and leaves this information in the context of the message so that downstream processes can use this information to authenticate and/or authorize the original sender of the message.</span></span>  
  
    3.  <span data-ttu-id="91d69-127">BizTalk Server で受信認証が構成されている場合、メッセージ ボックス データベースでは、メッセージにサブスクライブされたホストにメッセージを受信する権限があるかどうか確認されます。</span><span class="sxs-lookup"><span data-stu-id="91d69-127">If BizTalk Server requires receive authorization, the MessageBox database verifies that the hosts subscribed to the message have authorization to receive it.</span></span> <span data-ttu-id="91d69-128">詳細については、承認を受け取るを参照してください[メッセージの受信者の承認](../core/authorizing-the-receiver-of-a-message.md)です。</span><span class="sxs-lookup"><span data-stu-id="91d69-128">For more information about receive authorization, see [Authorizing the Receiver of a Message](../core/authorizing-the-receiver-of-a-message.md).</span></span>  
  
4.  <span data-ttu-id="91d69-129">メッセージが処理された後、エンコード ステージにおいて、送信パイプラインではメッセージの暗号化やデジタル署名の追加が行われます。</span><span class="sxs-lookup"><span data-stu-id="91d69-129">After BizTalk Server processes the message, the outbound pipeline encrypts and/or digitally signs the message in the encode stage.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91d69-130">参照</span><span class="sxs-lookup"><span data-stu-id="91d69-130">See Also</span></span>  
 <span data-ttu-id="91d69-131">[メッセージ セキュリティを実装します。](../core/implementing-message-security.md) </span><span class="sxs-lookup"><span data-stu-id="91d69-131">[Implementing Message Security](../core/implementing-message-security.md) </span></span>  
 [<span data-ttu-id="91d69-132">メッセージ セキュリティの計画</span><span class="sxs-lookup"><span data-stu-id="91d69-132">Planning Message Security</span></span>](../core/planning-message-security.md)