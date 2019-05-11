---
title: メッセージを送受信するためのセキュリティ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, receiving
- messages, sending
- messages, processing
- security, messages
- security, message processing
- messages, security
ms.assetid: 9bcd01e4-245a-4f4c-b65c-89d7cd3d1b68
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0dfaf4b02c674995c2e60c694d439281d6d632ab
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65280435"
---
# <a name="security-for-sending-and-receiving-messages"></a><span data-ttu-id="90a86-102">メッセージを送受信するためのセキュリティ</span><span class="sxs-lookup"><span data-stu-id="90a86-102">Security for Sending and Receiving Messages</span></span>
<span data-ttu-id="90a86-103">BizTalk Server は、それを受信し、処理し、別のアプリケーションまたはパートナーに送信しますメッセージに対する処理を次に示します。</span><span class="sxs-lookup"><span data-stu-id="90a86-103">The following figure shows what happens to a message as BizTalk Server receives it, processes it, and sends it to another application or partner.</span></span>  
  
 <span data-ttu-id="90a86-104">![セキュリティで保護されたメッセージのセキュリティ機能](../core/media/ebiz-plan-secoverview.gif "ebiz_plan_secoverview")</span><span class="sxs-lookup"><span data-stu-id="90a86-104">![Security features for secure messages](../core/media/ebiz-plan-secoverview.gif "ebiz_plan_secoverview")</span></span>  
<span data-ttu-id="90a86-105">メッセージの有効期間全体で使用されるセキュリティ機能</span><span class="sxs-lookup"><span data-stu-id="90a86-105">Security features used throughout the lifetime of a message</span></span>  
  
1.  <span data-ttu-id="90a86-106">アダプターの受信場所は、メッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="90a86-106">The receive location for the adapter receives the message.</span></span> <span data-ttu-id="90a86-107">プロトコルに応じて、アダプターはプロトコル レベルのメッセージの送信者を表す Windows ユーザー アカウントを識別するために送信者の認証。</span><span class="sxs-lookup"><span data-stu-id="90a86-107">Depending on the protocol, the adapter does protocol-level authentication of the sender to identify a Windows user account that represents the sender of the message.</span></span>  
  
2.  <span data-ttu-id="90a86-108">アダプターからメッセージを渡すをパイプラインにメッセージ レベルの認証が行われる場所、アダプターで行われていない場合。</span><span class="sxs-lookup"><span data-stu-id="90a86-108">The adapter then passes the message to the pipeline, where message-level authentication takes place if it has not already happened in the adapter.</span></span>  
  
    1.  <span data-ttu-id="90a86-109">デコード段階では、パイプラインはメッセージを復号化をメッセージに添付された証明書またはローカル コンピューターの他のユーザーの証明書ストアで構成されているいずれかで、署名の有効性を確認します。</span><span class="sxs-lookup"><span data-stu-id="90a86-109">In the Decode stage, the pipeline decrypts the message and verifies the validity of the signature with the certificate attached to the message, or the one configured in the Other People certificate store of the local computer.</span></span> <span data-ttu-id="90a86-110">パイプラインが、署名を検証した後、デコード コンポーネントは、信頼されたルート証明機関 (CA) までの証明書チェーンを検証します。</span><span class="sxs-lookup"><span data-stu-id="90a86-110">After the pipeline validates the signature, the decoding component validates the certificate chain up to a trusted root Certificate Authority (CA).</span></span> <span data-ttu-id="90a86-111">S/MIME メッセージをデコードするパイプラインを構成すると、送信者が S/MIME を使用してメッセージを暗号化、MIME/SMIME デコーダーは、メッセージの署名を検証し、送信者を識別するために、証明書を使用します。</span><span class="sxs-lookup"><span data-stu-id="90a86-111">If you configure the pipeline to decode S/MIME messages, and the sender encrypted the message using S/MIME, the MIME/SMIME decoder verifies the signature of the message, and uses the certificate to identify the sender.</span></span> <span data-ttu-id="90a86-112">MIME/SMIME デコーダー パイプライン コンポーネントを使用する方法の詳細については、次を参照してください。[メッセージ セキュリティを実装する](../core/implementing-message-security.md)します。</span><span class="sxs-lookup"><span data-stu-id="90a86-112">For more information about how to use MIME/SMIME decoder pipeline components, see [Implementing Message Security](../core/implementing-message-security.md).</span></span>  
  
    2.  <span data-ttu-id="90a86-113">パーティの解決ステージでは、BizTalk Server で、証明書情報を使用し、プロトコル レベルの認証システムで、メッセージの送信者が認識されたパーティであるかどうかを確認してから送信者のセキュリティ ID (SSID) を取得します。</span><span class="sxs-lookup"><span data-stu-id="90a86-113">In the Party Resolution stage, BizTalk Server uses the certificate information and the Sender Security ID (SSID) obtained from protocol-level authentication to determine whether the sender of the message is a recognized party in the system.</span></span> <span data-ttu-id="90a86-114">送信者の SSID は、アダプターによって認証されたユーザーの修飾名です。</span><span class="sxs-lookup"><span data-stu-id="90a86-114">The Sender SSID is the qualified name of the user authenticated by the adapter.</span></span> <span data-ttu-id="90a86-115">例えば。</span><span class="sxs-lookup"><span data-stu-id="90a86-115">For example.</span></span> <span data-ttu-id="90a86-116">BizTalk Server では、Windows 認証を使用して、HTTP アダプターを使用してメッセージを受信した場合、送信者の SSID はドメイン \ ユーザー名です。</span><span class="sxs-lookup"><span data-stu-id="90a86-116">If BizTalk Server receives the message by way of the HTTP adapter using Windows authentication, then the sender SSID is domain\username.</span></span> <span data-ttu-id="90a86-117">BizTalk Server が認識されたパーティのパーティ ID または guest ID のいずれかであると、メッセージをパーティ ID (PID) を割り当てます</span><span class="sxs-lookup"><span data-stu-id="90a86-117">BizTalk Server assigns a Party ID (PID) to the message, which is either the party ID of a recognized party, or a guest ID.</span></span> <span data-ttu-id="90a86-118">パーティの解決コンポーネントを使用する方法の詳細については、次を参照してください。[パーティの解決用の証明書を使用して](../core/using-certificates-for-party-resolution.md)します。</span><span class="sxs-lookup"><span data-stu-id="90a86-118">For more information about how to use party resolution component, see [Using Certificates for Party Resolution](../core/using-certificates-for-party-resolution.md).</span></span>  
  
    3.  <span data-ttu-id="90a86-119">かどうか、送信者をシステムでは、既知のパーティに認証を必要とする受信ポートを構成した BizTalk Server は、メッセージの送信者の PID を検索できませんし、BizTalk Server が削除されるかの構成によって、メッセージを保留します 受信ポート。</span><span class="sxs-lookup"><span data-stu-id="90a86-119">If you configured the receiving port to require the sender to be authenticated to a known party in the system, and BizTalk Server is not able to find a PID for the sender of the message, then BizTalk Server drops or suspends the message depending on the configuration of the receive port.</span></span> <span data-ttu-id="90a86-120">BizTalk Server では、サービス拒否攻撃を軽減するには、この機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="90a86-120">BizTalk Server provides this feature to mitigate Denial of Service attacks.</span></span> <span data-ttu-id="90a86-121">受信ポートの認証オプションの詳細については、次を参照してください。[受信ポートの認証オプションを構成する方法](../core/how-to-configure-authentication-options-for-a-receive-port.md)します。</span><span class="sxs-lookup"><span data-stu-id="90a86-121">For more information about the authentication options for receive ports, see [How to Configure Authentication Options for a Receive Port](../core/how-to-configure-authentication-options-for-a-receive-port.md).</span></span>  
  
3.  <span data-ttu-id="90a86-122">メッセージが認証されると、パイプライン、メッセージ ボックス データベースにメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="90a86-122">After the pipeline authenticates the message, it sends the message to the MessageBox database.</span></span>  
  
    1.  <span data-ttu-id="90a86-123">信頼済み認証ホストとして (パイプラインが実行されて) いるキュー送信ホストを特定できなかった場合、メッセージ ボックス データベースには、guest ID でサービス アカウントとして実行しているキュー送信ホストのインスタンスを持つ SSID と PID が上書きされます。</span><span class="sxs-lookup"><span data-stu-id="90a86-123">If you did not identify the enqueuing host (on which the pipeline is running) as an authentication trusted host, the MessageBox database overwrites the PID with the guest ID, and the SSID with the service account that the enqueuing host instance is running as.</span></span> <span data-ttu-id="90a86-124">信頼済み認証ホストの詳細については、次を参照してください。[認証メッセージの間でプロセスの](../core/authentication-of-messages-between-processes.md)します。</span><span class="sxs-lookup"><span data-stu-id="90a86-124">For more information about authentication trusted host, see [Authentication of Messages Between Processes](../core/authentication-of-messages-between-processes.md).</span></span> <span data-ttu-id="90a86-125">信頼済み認証ホストを構成する方法の詳細については、次を参照してください。[ホスト プロパティを変更する方法](../core/how-to-modify-host-properties.md)します。</span><span class="sxs-lookup"><span data-stu-id="90a86-125">For more information about how to configure authentication trusted host, see [How to Modify Host Properties](../core/how-to-modify-host-properties.md).</span></span>  
  
    2.  <span data-ttu-id="90a86-126">メッセージ ボックス データベースが PID および SSID を信頼し、下流のプロセスでこの情報を使用して認証できるように、メッセージのコンテキストでは、この情報を離れる場合は、パイプラインが実行されているホストが信頼された認証としてマークされている、またはメッセージの元の送信者を承認します。</span><span class="sxs-lookup"><span data-stu-id="90a86-126">If the host on which the pipeline is running is marked as authentication trusted, the MessageBox database trusts the PID and SSID, and leaves this information in the context of the message so that downstream processes can use this information to authenticate and/or authorize the original sender of the message.</span></span>  
  
    3.  <span data-ttu-id="90a86-127">BizTalk Server では、受信、認証が必要な場合、メッセージ ボックス データベースは、メッセージをサブスクライブして、ホストにメッセージを受信するための承認があることを確認します。</span><span class="sxs-lookup"><span data-stu-id="90a86-127">If BizTalk Server requires receive authorization, the MessageBox database verifies that the hosts subscribed to the message have authorization to receive it.</span></span> <span data-ttu-id="90a86-128">詳細については、承認を受信を参照してください。[メッセージの受信者の承認](../core/authorizing-the-receiver-of-a-message.md)します。</span><span class="sxs-lookup"><span data-stu-id="90a86-128">For more information about receive authorization, see [Authorizing the Receiver of a Message](../core/authorizing-the-receiver-of-a-message.md).</span></span>  
  
4.  <span data-ttu-id="90a86-129">BizTalk Server がメッセージを処理した後、送信パイプラインの暗号化や、エンコード ステージで、メッセージにデジタル署名します。</span><span class="sxs-lookup"><span data-stu-id="90a86-129">After BizTalk Server processes the message, the outbound pipeline encrypts and/or digitally signs the message in the encode stage.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90a86-130">参照</span><span class="sxs-lookup"><span data-stu-id="90a86-130">See Also</span></span>  
 <span data-ttu-id="90a86-131">[メッセージ セキュリティの実装](../core/implementing-message-security.md) </span><span class="sxs-lookup"><span data-stu-id="90a86-131">[Implementing Message Security](../core/implementing-message-security.md) </span></span>  
 [<span data-ttu-id="90a86-132">メッセージ セキュリティの計画</span><span class="sxs-lookup"><span data-stu-id="90a86-132">Planning Message Security</span></span>](../core/planning-message-security.md)