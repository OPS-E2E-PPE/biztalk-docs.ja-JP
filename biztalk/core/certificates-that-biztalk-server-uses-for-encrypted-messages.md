---
title: "暗号化されたメッセージを BizTalk Server で使用される証明書 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, message flow [encrypted messages]
- encrypted messages
- messages, encryption
ms.assetid: 44b06488-4ecd-436d-af3d-b95e285ecb3e
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7f2dbd51506da7b505f66b3001b8bdc6fa0a58ac
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="certificates-that-biztalk-server-uses-for-encrypted-messages"></a><span data-ttu-id="55a6f-102">BizTalk Server で暗号化されたメッセージに使用する証明書</span><span class="sxs-lookup"><span data-stu-id="55a6f-102">Certificates that BizTalk Server Uses for Encrypted Messages</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="55a6f-103"> では、S/MIME (Secure Multipurpose Internet Mail Extensions) を使用した公開キーによる送信メッセージの暗号化と、受信メッセージの解読がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="55a6f-103"> supports public key encryption of outbound messages and decryption of inbound messages based on Secure Multipurpose Internet Mail Extensions (S/MIME).</span></span> <span data-ttu-id="55a6f-104">送信メッセージの暗号化には S/MIME バージョン 3 が使用され、受信メッセージの解読には S/MIME バージョン 2 と 3 が使用されます。</span><span class="sxs-lookup"><span data-stu-id="55a6f-104">BizTalk Server uses S/MIME version 3 for encryption of outbound messages, and S/MIME versions 2 and 3 for decryption of inbound messages.</span></span>  
  
-   <span data-ttu-id="55a6f-105">BizTalk Server では、RSA および Diffie Hellman 暗号化証明書がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="55a6f-105">BizTalk Server supports RSA and Diffie Hellman encryption certificates.</span></span>  
  
-   <span data-ttu-id="55a6f-106">また、DES (Data Encryption Standard)、3DES、および RC2 暗号化アルゴリズムがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="55a6f-106">BizTalk Server supports Data Encryption Standard (DES), 3DES, and RC2 encryption algorithms.</span></span>  
  
 <span data-ttu-id="55a6f-107">暗号化されたメッセージが BizTalk Server で受信されたときのメッセージ フローを次に示します。</span><span class="sxs-lookup"><span data-stu-id="55a6f-107">The following figure shows the message flow when BizTalk Server receives an encrypted message.</span></span>  
  
 <span data-ttu-id="55a6f-108">![暗号化されたメッセージを受信するときに、メッセージ フロー](../core/media/bpi-sp-msgsec-inboundencryption.gif "BPI_SP_MSGSEC_InboundEncryption")</span><span class="sxs-lookup"><span data-stu-id="55a6f-108">![Message flow when receiving an encrypted message](../core/media/bpi-sp-msgsec-inboundencryption.gif "BPI_SP_MSGSEC_InboundEncryption")</span></span>  
  
 <span data-ttu-id="55a6f-109">暗号化されたメッセージが BizTalk Server で受信されたときのメッセージ フローは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="55a6f-109">The message flow when BizTalk Server receives an encrypted message is as follows:</span></span>  
  
1.  <span data-ttu-id="55a6f-110">パートナーから BizTalk Server にメッセージが送信されます。</span><span class="sxs-lookup"><span data-stu-id="55a6f-110">A partner sends a message to BizTalk Server.</span></span> <span data-ttu-id="55a6f-111">パートナーは BizTalk Server の公開キーを使用してメッセージを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="55a6f-111">The partner encrypts the message with the BizTalk Server public key.</span></span>  
  
2.  <span data-ttu-id="55a6f-112">対応する BizTalk Server 受信ハンドラーでメッセージが受信されます。</span><span class="sxs-lookup"><span data-stu-id="55a6f-112">The appropriate BizTalk Server receive handler receives the message.</span></span>  
  
3.  <span data-ttu-id="55a6f-113">受信パイプラインの実行中に、MIME/SMIME デコーダー パイプライン コンポーネントで、BizTalk Server の秘密キーを使用してメッセージが解読されます。</span><span class="sxs-lookup"><span data-stu-id="55a6f-113">During the receive pipeline execution, the MIME/SMIME Decoder pipeline component decrypts the message by using the BizTalk Server private key.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="55a6f-114">IIS 7.0 コンピューターで正常にパイプラインの復号化は、IIS アプリケーション プールのアカウントおよび受信ハンドラーに関連付けられているホスト インスタンスによって使用されるアカウントは、同じであると、このアカウントがのメンバーであることを確認、 \<machineName\>\IIS_WPG グループ。</span><span class="sxs-lookup"><span data-stu-id="55a6f-114">For pipeline decryption to succeed on an IIS 7.0 computer, ensure that the account for the IIS application pool and the account used by the host instance associated with the receive handler are the same and that this account is a member of the \<machineName\>\IIS_WPG group.</span></span> <span data-ttu-id="55a6f-115">IIS の設定の詳細については、プロセス IIS 7.0 は、「id [IIS アクセス許可の問題を解決するためのガイドライン](../core/guidelines-for-resolving-iis-permissions-problems.md)です。</span><span class="sxs-lookup"><span data-stu-id="55a6f-115">For more information on setting IIS process identity for IIS 7.0 see [Guidelines for Resolving IIS Permissions Problems](../core/guidelines-for-resolving-iis-permissions-problems.md).</span></span> <span data-ttu-id="55a6f-116">これらのプロセスは同じアカウントで実行する必要があります。これは、アカウント プロファイルが読み込まれ、それに続いてパイプラインで解読を実行するのに必要なレジストリ キーが読み込まれるようにするためです。</span><span class="sxs-lookup"><span data-stu-id="55a6f-116">These processes must run under the same account to ensure that the account profile is loaded which in turns loads the registry keys required to perform decryption in the pipeline.</span></span> <span data-ttu-id="55a6f-117">IIS 7.0 では、パフォーマンス上の理由のため、関連する w3wp.exe プロセスの開始時にアカウント プロファイルが読み込まれません。したがって、BizTalk がアカウント プロファイルとレジストリ キーを読み込むように BizTalk ホスト インスタンスを同じアカウントで構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="55a6f-117">For performance reasons, IIS 7.0 does not load the account profile when starting the associated w3wp.exe process so the BizTalk host instance must be configured with the same account so that BizTalk will load the account profile and registry keys.</span></span>  
  
4.  <span data-ttu-id="55a6f-118">追加処理が実行されます。</span><span class="sxs-lookup"><span data-stu-id="55a6f-118">Additional processing occurs.</span></span>  
  
 <span data-ttu-id="55a6f-119">次の図に、暗号化されたメッセージが BizTalk Server から送信されたときのメッセージ フローを示します。</span><span class="sxs-lookup"><span data-stu-id="55a6f-119">The following figure shows the message flow when BizTalk Server sends an encrypted message.</span></span>  
  
 <span data-ttu-id="55a6f-120">![暗号化されたメッセージを送信するときに、メッセージ フロー](../core/media/bpi-sp-msgsec-outboundencryption.gif "BPI_SP_MSGSEC_OutboundEncryption")</span><span class="sxs-lookup"><span data-stu-id="55a6f-120">![Message flow when sending an encrypted message](../core/media/bpi-sp-msgsec-outboundencryption.gif "BPI_SP_MSGSEC_OutboundEncryption")</span></span>  
  
 <span data-ttu-id="55a6f-121">暗号化されたメッセージが BizTalk Server からパートナーに送信されたときのメッセージ フローは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="55a6f-121">The message flow when BizTalk Server sends an encrypted message to a partner is as follows:</span></span>  
  
1.  <span data-ttu-id="55a6f-122">対応する BizTalk Server 送信ハンドラーからパートナーにメッセージが送信されます。</span><span class="sxs-lookup"><span data-stu-id="55a6f-122">The appropriate BizTalk Server send handler sends a message to the partner.</span></span>  
  
2.  <span data-ttu-id="55a6f-123">送信パイプラインの実行中に、MIME/SMIME エンコーダー パイプライン コンポーネントで、パートナーの公開キーを使用してメッセージが暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="55a6f-123">During the send pipeline execution, the MIME/SMIME Encoder pipeline component encrypts the message by using the partner's public key.</span></span>  
  
3.  <span data-ttu-id="55a6f-124">パートナーが BizTalk Server からメッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="55a6f-124">The partner receives the message from BizTalk Server.</span></span> <span data-ttu-id="55a6f-125">パートナーは秘密キーを使用してメッセージを解読します。</span><span class="sxs-lookup"><span data-stu-id="55a6f-125">The partner uses its private key to decrypt the message.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55a6f-126">参照</span><span class="sxs-lookup"><span data-stu-id="55a6f-126">See Also</span></span>  
 <span data-ttu-id="55a6f-127">[BizTalk Server が署名されたメッセージで使用する証明書](../core/certificates-that-biztalk-server-uses-for-signed-messages.md) </span><span class="sxs-lookup"><span data-stu-id="55a6f-127">[Certificates that BizTalk Server Uses for Signed Messages](../core/certificates-that-biztalk-server-uses-for-signed-messages.md) </span></span>  
 <span data-ttu-id="55a6f-128">[BizTalk Server で使用される証明書ストア](../core/certificate-stores-that-biztalk-server-uses.md) </span><span class="sxs-lookup"><span data-stu-id="55a6f-128">[Certificate Stores that BizTalk Server Uses](../core/certificate-stores-that-biztalk-server-uses.md) </span></span>  
 <span data-ttu-id="55a6f-129">[暗号化と証明書の署名](../core/encryption-and-signing-certificates.md) </span><span class="sxs-lookup"><span data-stu-id="55a6f-129">[Encryption and Signing Certificates](../core/encryption-and-signing-certificates.md) </span></span>  
 [<span data-ttu-id="55a6f-130">暗号化されたメッセージの送受信</span><span class="sxs-lookup"><span data-stu-id="55a6f-130">Sending and Receiving Encrypted Messages</span></span>](../core/sending-and-receiving-encrypted-messages.md)