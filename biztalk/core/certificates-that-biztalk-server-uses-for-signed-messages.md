---
title: BizTalk Server で使用する証明書の署名付きメッセージ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, signed messages
- messages, message flow [digital signatures]
- S/MIME messages
- signed messages
- digital signatures, message flow
- messages, certificates
ms.assetid: 0b521e11-73ef-424f-9e6a-4fb42dc263ff
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1cc45411d19bc23a2985dbd60fc68bc8de58594c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979851"
---
# <a name="certificates-that-biztalk-server-uses-for-signed-messages"></a><span data-ttu-id="23063-102">BizTalk Server で署名付きメッセージに使用する証明書</span><span class="sxs-lookup"><span data-stu-id="23063-102">Certificates that BizTalk Server Uses for Signed Messages</span></span>
<span data-ttu-id="23063-103">BizTalk Server では、送信メッセージへの署名と、S/MIME (Secure Multipurpose Internet Mail Extensions) 受信メッセージに対する署名の確認がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="23063-103">BizTalk Server supports signing outbound messages and signature verification for inbound Secure Multipurpose Internet Mail Extensions (S/MIME) messages.</span></span> <span data-ttu-id="23063-104">送信メッセージへの署名と受信メッセージの署名の確認には、S/MIME バージョン 2 および 3 が使用されます。</span><span class="sxs-lookup"><span data-stu-id="23063-104">BizTalk Server uses S/MIME versions 2 and 3 to sign outbound messages and to validate the signature of inbound messages.</span></span> <span data-ttu-id="23063-105">同様に、BizTalk Server の構成では、パートナーへの送信メッセージが署名され暗号化されるように指定できます。</span><span class="sxs-lookup"><span data-stu-id="23063-105">Similarly, you can configure BizTalk Server to sign and then encrypt the messages it sends to its partners.</span></span>  
  
- <span data-ttu-id="23063-106">BizTalk Server では、デジタル署名の検証に SHA-1 署名アルゴリズムと MD5 署名アルゴリズムを使用できます。</span><span class="sxs-lookup"><span data-stu-id="23063-106">BizTalk Server supports the SHA-1 and MD5 signing algorithms for verifying digital signatures.</span></span> <span data-ttu-id="23063-107">送信メッセージへの署名には、SHA-1 署名アルゴリズムが使用されます。</span><span class="sxs-lookup"><span data-stu-id="23063-107">BizTalk Server uses the SHA-1 signing algorithm to sign outbound messages.</span></span>  
  
- <span data-ttu-id="23063-108">BizTalk Server でサポートされる署名キーのキー交換システムは、RSA (Rivest-Shamir-Adleman) アルゴリズムと DSS (Digital Signature Standard) です。</span><span class="sxs-lookup"><span data-stu-id="23063-108">The key exchange systems supported by BizTalk Server for signature keys are the Rivest-Shamir-Adleman (RSA) algorithms and the Digital Signature Standard (DSS).</span></span> <span data-ttu-id="23063-109">BizTalk Server では、署名キーに対する AES (Advanced Encryption Standard) 交換システムの使用はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="23063-109">BizTalk Server does not support the Advanced Encryption Standard (AES) exchange system for signature keys.</span></span>  
  
- <span data-ttu-id="23063-110">BizTalk Server でサポートされる署名証明書は x.509 バージョン 3 です。</span><span class="sxs-lookup"><span data-stu-id="23063-110">The signing certificate supported by BizTalk Server is x.509 version 3.</span></span>  
  
  <span data-ttu-id="23063-111">次の図は、デジタル署名されたメッセージを BizTalk Server で受信し、BizTalk Server 環境内で署名を適宜使用してパートナーの ID をパーティに解決するときのメッセージ フローです。</span><span class="sxs-lookup"><span data-stu-id="23063-111">The following figure shows the message flow when BizTalk Server receives a digitally signed message and optionally uses the signature to resolve the partner identity to a party in the BizTalk Server environment.</span></span>  
  
  <span data-ttu-id="23063-112">![署名付きメッセージを送信するときに、メッセージ フロー](../core/media/6fd1674d-5a21-4272-83ca-608d7b400de7.gif "6fd1674d-5a21-4272-83ca-608d7b400de7")</span><span class="sxs-lookup"><span data-stu-id="23063-112">![Message flow when sending a signed message](../core/media/6fd1674d-5a21-4272-83ca-608d7b400de7.gif "6fd1674d-5a21-4272-83ca-608d7b400de7")</span></span>  
  
  <span data-ttu-id="23063-113">デジタル署名されたメッセージを BizTalk Server で受信するときのメッセージ フローは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="23063-113">The message flow when BizTalk Server receives a digitally signed message is as follows:</span></span>  
  
1. <span data-ttu-id="23063-114">パートナーから BizTalk Server にメッセージが送信されます。</span><span class="sxs-lookup"><span data-stu-id="23063-114">A partner sends a message to BizTalk Server.</span></span> <span data-ttu-id="23063-115">パートナーは秘密キー証明書を使用してメッセージに署名します。</span><span class="sxs-lookup"><span data-stu-id="23063-115">The partner signs the message with its private key certificate.</span></span>  
  
2. <span data-ttu-id="23063-116">対応する BizTalk Server 受信ハンドラーでメッセージが受信されます。</span><span class="sxs-lookup"><span data-stu-id="23063-116">The appropriate BizTalk Server receive handler receives the message.</span></span>  
  
3. <span data-ttu-id="23063-117">受信パイプラインの実行中に、MIME/SMIME デコーダ パイプライン コンポーネントで、パートナーの公開キーを使用してデジタル署名が検証されます。</span><span class="sxs-lookup"><span data-stu-id="23063-117">During the execution of the receive pipeline, the MIME/SMIME Decoder pipeline component verifies the digital signature by using the partner's public key.</span></span>  
  
4. <span data-ttu-id="23063-118">パーティの解決コンポーネントが構成されている場合は、受信パイプラインのパーティの解決コンポーネントの実行中に、BizTalk Server システム内でパートナーの公開キー証明書を基にパーティが識別されます。</span><span class="sxs-lookup"><span data-stu-id="23063-118">If party resolution component is configured, the partner's public key certificate is used to identify the party in the BizTalk Server system during the execution of the receive pipeline party resolution component.</span></span>  
  
5. <span data-ttu-id="23063-119">追加処理が実行されます。</span><span class="sxs-lookup"><span data-stu-id="23063-119">Additional processing occurs.</span></span>  
  
   <span data-ttu-id="23063-120">次の図は、デジタル署名されたメッセージを BizTalk Server から送信するときのメッセージ フローです。</span><span class="sxs-lookup"><span data-stu-id="23063-120">The following figure shows the message flow when BizTalk Server sends a digitally signed message.</span></span>  
  
   <span data-ttu-id="23063-121">![](../core/media/bts-bpi-sp-msgsec-outboundsigning-r2c.gif "bts_BPI_SP_MSGSEC_OutboundSigning_R2c")</span><span class="sxs-lookup"><span data-stu-id="23063-121">![](../core/media/bts-bpi-sp-msgsec-outboundsigning-r2c.gif "bts_BPI_SP_MSGSEC_OutboundSigning_R2c")</span></span>  
  
   <span data-ttu-id="23063-122">デジタル署名されたメッセージを BizTalk Server からパートナーに送信するときのメッセージ フローは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="23063-122">The message flow when BizTalk Server sends a digitally signed message to a partner is as follows:</span></span>  
  
6. <span data-ttu-id="23063-123">対応する BizTalk Server 送信ハンドラーからパートナーにメッセージが送信されます。</span><span class="sxs-lookup"><span data-stu-id="23063-123">The appropriate BizTalk Server send handler sends a message to the partner.</span></span>  
  
7. <span data-ttu-id="23063-124">送信パイプラインの実行中に、MIME/SMIME エンコーダ パイプライン コンポーネントで、BizTalk Server の秘密キーを使用してメッセージが署名されます。</span><span class="sxs-lookup"><span data-stu-id="23063-124">During the execution of the send pipeline, the MIME/SMIME Encoder pipeline component signs the message by using the BizTalk Server private key.</span></span>  
  
8. <span data-ttu-id="23063-125">パートナーが BizTalk Server からメッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="23063-125">The partner receives the message from BizTalk Server.</span></span> <span data-ttu-id="23063-126">パートナーは BizTalk Server の公開キーを使用してデジタル署名を検証します。</span><span class="sxs-lookup"><span data-stu-id="23063-126">The partner uses the BizTalk Server public key to verify the digital signature.</span></span>  
  
   <span data-ttu-id="23063-127">BizTalk Server は、証明機関 (CA) 信頼チェーンの検証と確認することにより、証明書の証明書の有効期限が切れていない受信署名付きメッセージに関連付けられている証明書の有効性を確認します。</span><span class="sxs-lookup"><span data-stu-id="23063-127">BizTalk Server verifies the validity of the certificates associated with the incoming signed messages by validating the certification authority (CA) trust chain for the certificate and by verifying that the certificate has not expired.</span></span> <span data-ttu-id="23063-128">証明機関 (CA) の信頼チェーンの検証プロセスでは、ルート証明機関まで証明書の信頼チェーンをたどって検証が行われます。</span><span class="sxs-lookup"><span data-stu-id="23063-128">The process of validating the CA trust chain involves traversing the chain of trust on certificates until a root certification authority is reached.</span></span> <span data-ttu-id="23063-129">これにより、メッセージの署名に使用された証明書が確実に、認識されている当事者からのものであることが検証されます。</span><span class="sxs-lookup"><span data-stu-id="23063-129">This validates that the certificate used to sign a message is indeed from the identified party.</span></span> <span data-ttu-id="23063-130">この検証は、実行時、すべての署名付きメッセージに対して個別に行われます。</span><span class="sxs-lookup"><span data-stu-id="23063-130">This validation occurs at runtime for each and every signed message.</span></span>  
  
   <span data-ttu-id="23063-131">さらに、BizTalk Server では、証明機関が署名またはメッセージの暗号化に使用する証明書を失効していないことを確認できます。</span><span class="sxs-lookup"><span data-stu-id="23063-131">In addition, BizTalk Server can verify that the certification authority has not revoked the certificate used to sign or encrypt the message.</span></span> <span data-ttu-id="23063-132">これには、証明機関から証明書の失効一覧 (CRL) をダウンロードし、エクスプローラーを使用して CRL をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="23063-132">To do this, you must download the certificate revocation list (CRL) from the certification authority and install it using Windows Explorer.</span></span> <span data-ttu-id="23063-133">証明書を検証する方法の詳細については、[MIME-SMIME デコーダー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-mime-smime-decoder-pipeline-component.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="23063-133">For more information about how to validate a certificate, see [How to Configure the MIME-SMIME Decoder Pipeline Component](../core/how-to-configure-the-mime-smime-decoder-pipeline-component.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23063-134">参照</span><span class="sxs-lookup"><span data-stu-id="23063-134">See Also</span></span>  
 <span data-ttu-id="23063-135">[BizTalk Server は、暗号化されたメッセージで使用する証明書](../core/certificates-that-biztalk-server-uses-for-encrypted-messages.md) </span><span class="sxs-lookup"><span data-stu-id="23063-135">[Certificates that BizTalk Server Uses for Encrypted Messages](../core/certificates-that-biztalk-server-uses-for-encrypted-messages.md) </span></span>  
 <span data-ttu-id="23063-136">[BizTalk Server で使用される証明書ストア](../core/certificate-stores-that-biztalk-server-uses.md) </span><span class="sxs-lookup"><span data-stu-id="23063-136">[Certificate Stores that BizTalk Server Uses](../core/certificate-stores-that-biztalk-server-uses.md) </span></span>  
 <span data-ttu-id="23063-137">[暗号化および署名証明書](../core/encryption-and-signing-certificates.md) </span><span class="sxs-lookup"><span data-stu-id="23063-137">[Encryption and Signing Certificates](../core/encryption-and-signing-certificates.md) </span></span>  
 [<span data-ttu-id="23063-138">署名付きメッセージの送受信</span><span class="sxs-lookup"><span data-stu-id="23063-138">Sending and Receiving Signed Messages</span></span>](../core/sending-and-receiving-signed-messages.md)