---
title: 暗号化されたメッセージを BizTalk Server で使用する証明書 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, message flow [encrypted messages]
- encrypted messages
- messages, encryption
ms.assetid: 44b06488-4ecd-436d-af3d-b95e285ecb3e
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b96e47a84e94067cf197fd8614ef789af0a012ba
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358008"
---
# <a name="certificates-that-biztalk-server-uses-for-encrypted-messages"></a><span data-ttu-id="ecaff-102">BizTalk Server は、暗号化されたメッセージで使用する証明書</span><span class="sxs-lookup"><span data-stu-id="ecaff-102">Certificates that BizTalk Server Uses for Encrypted Messages</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="ecaff-103">送信メッセージの公開キーの暗号化と Secure Multipurpose Internet Mail Extensions (S/MIME) に基づいて、受信メッセージの解読をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="ecaff-103">supports public key encryption of outbound messages and decryption of inbound messages based on Secure Multipurpose Internet Mail Extensions (S/MIME).</span></span> <span data-ttu-id="ecaff-104">BizTalk Server では、S/MIME バージョン 3 の送信メッセージの暗号化と S/MIME バージョン 2 および 3 の受信メッセージを復号化を使用します。</span><span class="sxs-lookup"><span data-stu-id="ecaff-104">BizTalk Server uses S/MIME version 3 for encryption of outbound messages, and S/MIME versions 2 and 3 for decryption of inbound messages.</span></span>  
  
- <span data-ttu-id="ecaff-105">BizTalk Server では、RSA および Diffie Hellman 暗号化証明書をサポートします。</span><span class="sxs-lookup"><span data-stu-id="ecaff-105">BizTalk Server supports RSA and Diffie Hellman encryption certificates.</span></span>  
  
- <span data-ttu-id="ecaff-106">BizTalk Server には、データ暗号化標準 (DES)、3 des、および RC2 暗号化アルゴリズムがサポートしています。</span><span class="sxs-lookup"><span data-stu-id="ecaff-106">BizTalk Server supports Data Encryption Standard (DES), 3DES, and RC2 encryption algorithms.</span></span>  
  
  <span data-ttu-id="ecaff-107">次の図は、BizTalk Server は暗号化されたメッセージを受信すると、メッセージ フローを示します。</span><span class="sxs-lookup"><span data-stu-id="ecaff-107">The following figure shows the message flow when BizTalk Server receives an encrypted message.</span></span>  
  
  <span data-ttu-id="ecaff-108">![暗号化されたメッセージを受信するときに、メッセージ フロー](../core/media/bpi-sp-msgsec-inboundencryption.gif "BPI_SP_MSGSEC_InboundEncryption")</span><span class="sxs-lookup"><span data-stu-id="ecaff-108">![Message flow when receiving an encrypted message](../core/media/bpi-sp-msgsec-inboundencryption.gif "BPI_SP_MSGSEC_InboundEncryption")</span></span>  
  
  <span data-ttu-id="ecaff-109">BizTalk Server は暗号化されたメッセージを受信するときのメッセージ フローは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="ecaff-109">The message flow when BizTalk Server receives an encrypted message is as follows:</span></span>  
  
1. <span data-ttu-id="ecaff-110">パートナーから BizTalk Server にメッセージが送信されます。</span><span class="sxs-lookup"><span data-stu-id="ecaff-110">A partner sends a message to BizTalk Server.</span></span> <span data-ttu-id="ecaff-111">パートナーは、BizTalk Server の公開キーで、メッセージを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="ecaff-111">The partner encrypts the message with the BizTalk Server public key.</span></span>  
  
2. <span data-ttu-id="ecaff-112">対応する BizTalk Server 受信ハンドラーでメッセージが受信されます。</span><span class="sxs-lookup"><span data-stu-id="ecaff-112">The appropriate BizTalk Server receive handler receives the message.</span></span>  
  
3. <span data-ttu-id="ecaff-113">受信パイプラインの実行中には、MIME/SMIME デコーダー パイプライン コンポーネントは、BizTalk Server 秘密キーを使用してメッセージを解読します。</span><span class="sxs-lookup"><span data-stu-id="ecaff-113">During the receive pipeline execution, the MIME/SMIME Decoder pipeline component decrypts the message by using the BizTalk Server private key.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="ecaff-114">IIS 7.0 コンピューターで成功するパイプラインの復号化は、IIS アプリケーション プール アカウントと受信ハンドラーに関連付けられているホスト インスタンスによって使用されるアカウントは、同じであると、このアカウントがのメンバーであることを確認、 \<machineName\>\IIS_WPG グループ。</span><span class="sxs-lookup"><span data-stu-id="ecaff-114">For pipeline decryption to succeed on an IIS 7.0 computer, ensure that the account for the IIS application pool and the account used by the host instance associated with the receive handler are the same and that this account is a member of the \<machineName\>\IIS_WPG group.</span></span> <span data-ttu-id="ecaff-115">IIS の設定の詳細については、プロセス id の IIS 7.0 を参照してください[IIS アクセス許可の問題を解決するためのガイドライン](../core/guidelines-for-resolving-iis-permissions-problems.md)します。</span><span class="sxs-lookup"><span data-stu-id="ecaff-115">For more information on setting IIS process identity for IIS 7.0 see [Guidelines for Resolving IIS Permissions Problems](../core/guidelines-for-resolving-iis-permissions-problems.md).</span></span> <span data-ttu-id="ecaff-116">これらのプロセスは同じアカウントで実行する必要があります。これは、アカウント プロファイルが読み込まれ、それに続いてパイプラインで解読を実行するのに必要なレジストリ キーが読み込まれるようにするためです。</span><span class="sxs-lookup"><span data-stu-id="ecaff-116">These processes must run under the same account to ensure that the account profile is loaded which in turns loads the registry keys required to perform decryption in the pipeline.</span></span> <span data-ttu-id="ecaff-117">パフォーマンス上の理由は、BizTalk がアカウント プロファイルとレジストリ キーを読み込むように、同じアカウントで、BizTalk ホスト インスタンスを構成する必要がありますので、関連する w3wp.exe プロセスを開始するときに、IIS 7.0 は、アカウントのプロファイルを読み込みません。</span><span class="sxs-lookup"><span data-stu-id="ecaff-117">For performance reasons, IIS 7.0 does not load the account profile when starting the associated w3wp.exe process so the BizTalk host instance must be configured with the same account so that BizTalk will load the account profile and registry keys.</span></span>  
  
4. <span data-ttu-id="ecaff-118">追加処理が実行されます。</span><span class="sxs-lookup"><span data-stu-id="ecaff-118">Additional processing occurs.</span></span>  
  
   <span data-ttu-id="ecaff-119">次の図は、BizTalk Server は、暗号化されたメッセージを送信するときに、メッセージ フローを示します。</span><span class="sxs-lookup"><span data-stu-id="ecaff-119">The following figure shows the message flow when BizTalk Server sends an encrypted message.</span></span>  
  
   <span data-ttu-id="ecaff-120">![暗号化されたメッセージを送信するときに、メッセージ フロー](../core/media/bpi-sp-msgsec-outboundencryption.gif "BPI_SP_MSGSEC_OutboundEncryption")</span><span class="sxs-lookup"><span data-stu-id="ecaff-120">![Message flow when sending an encrypted message](../core/media/bpi-sp-msgsec-outboundencryption.gif "BPI_SP_MSGSEC_OutboundEncryption")</span></span>  
  
   <span data-ttu-id="ecaff-121">BizTalk Server は、パートナーに暗号化されたメッセージを送信するときのメッセージ フローは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="ecaff-121">The message flow when BizTalk Server sends an encrypted message to a partner is as follows:</span></span>  
  
5. <span data-ttu-id="ecaff-122">対応する BizTalk Server 送信ハンドラーからパートナーにメッセージが送信されます。</span><span class="sxs-lookup"><span data-stu-id="ecaff-122">The appropriate BizTalk Server send handler sends a message to the partner.</span></span>  
  
6. <span data-ttu-id="ecaff-123">送信パイプラインの実行中には、MIME/SMIME エンコーダー パイプライン コンポーネントは、パートナーの公開キーを使用して、メッセージを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="ecaff-123">During the send pipeline execution, the MIME/SMIME Encoder pipeline component encrypts the message by using the partner's public key.</span></span>  
  
7. <span data-ttu-id="ecaff-124">パートナーが BizTalk Server からメッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="ecaff-124">The partner receives the message from BizTalk Server.</span></span> <span data-ttu-id="ecaff-125">パートナーは、メッセージの解読にその秘密キーを使用します。</span><span class="sxs-lookup"><span data-stu-id="ecaff-125">The partner uses its private key to decrypt the message.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ecaff-126">参照</span><span class="sxs-lookup"><span data-stu-id="ecaff-126">See Also</span></span>  
 <span data-ttu-id="ecaff-127">[BizTalk Server は、署名付きメッセージで使用する証明書](../core/certificates-that-biztalk-server-uses-for-signed-messages.md) </span><span class="sxs-lookup"><span data-stu-id="ecaff-127">[Certificates that BizTalk Server Uses for Signed Messages](../core/certificates-that-biztalk-server-uses-for-signed-messages.md) </span></span>  
 <span data-ttu-id="ecaff-128">[BizTalk Server で使用される証明書ストア](../core/certificate-stores-that-biztalk-server-uses.md) </span><span class="sxs-lookup"><span data-stu-id="ecaff-128">[Certificate Stores that BizTalk Server Uses](../core/certificate-stores-that-biztalk-server-uses.md) </span></span>  
 <span data-ttu-id="ecaff-129">[暗号化および署名証明書](../core/encryption-and-signing-certificates.md) </span><span class="sxs-lookup"><span data-stu-id="ecaff-129">[Encryption and Signing Certificates](../core/encryption-and-signing-certificates.md) </span></span>  
 [<span data-ttu-id="ecaff-130">暗号化されたメッセージの送受信</span><span class="sxs-lookup"><span data-stu-id="ecaff-130">Sending and Receiving Encrypted Messages</span></span>](../core/sending-and-receiving-encrypted-messages.md)