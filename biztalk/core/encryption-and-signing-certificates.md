---
title: "暗号化と証明書の署名 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- certificates, security
- security, certificates
- security, messages
- certificates, encryption
- encryption certificates, messages
- messages, encryption
- messages, certificates
- security, encryption
ms.assetid: 3c3f9de5-4156-4133-8d5e-c30b142b6d61
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 633484a6c5599b9323bfd7798f621b27a501ce6b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="encryption-and-signing-certificates"></a><span data-ttu-id="031a8-102">暗号化と証明書の署名</span><span class="sxs-lookup"><span data-stu-id="031a8-102">Encryption and Signing Certificates</span></span>
<span data-ttu-id="031a8-103">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のセキュリティ保護は、証明書に大きく依存します。</span><span class="sxs-lookup"><span data-stu-id="031a8-103">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] relies heavily on the security provided by certificates.</span></span> <span data-ttu-id="031a8-104">BizTalk Server では、暗号化証明書や署名証明書を使用することで、信頼できるデータを送受信でき、処理するデータの安全性を確保できます。</span><span class="sxs-lookup"><span data-stu-id="031a8-104">By using certificates for encryption and digital signatures, BizTalk Server can send and receive data that can be trusted, and can help ensure that the data it processes is secure.</span></span> <span data-ttu-id="031a8-105">暗号化とデジタル署名には、どちらも公開キー証明書と秘密キー証明書を使用します。</span><span class="sxs-lookup"><span data-stu-id="031a8-105">For both encryption and digital signatures, there is a public key certificate and a private key certificate.</span></span> <span data-ttu-id="031a8-106">暗号化を使用する場合、メッセージの送信者は受信者の公開キー証明書を使用してメッセージを暗号化し、メッセージの受信者 (BizTalk Server) は秘密キーを使用してメッセージを解読します。</span><span class="sxs-lookup"><span data-stu-id="031a8-106">For encryption, the sender of the message uses the receiver's public key certificate to encrypt the message, while the receiver of the message (BizTalk Server) uses its private key to decrypt the message.</span></span> <span data-ttu-id="031a8-107">デジタル署名を使用する場合、メッセージの送信者は公開キー証明書を使用してメッセージに署名し、メッセージの受信者 (BizTalk Server) は送信者の公開キー証明書を使用して署名を確認します。</span><span class="sxs-lookup"><span data-stu-id="031a8-107">For digital signatures, the sender of the message uses a private key certificate to sign the message, and the receiver of the message (BizTalk Server) uses the public key certificate of the sender to verify the signature.</span></span>  
  
 <span data-ttu-id="031a8-108">BizTalk Server では、受信メッセージのデジタル署名の確認と送信メッセージの暗号化に公開キー証明書を使用し、</span><span class="sxs-lookup"><span data-stu-id="031a8-108">BizTalk Server uses public key certificates to verify the digital signatures of inbound messages and for encrypting outbound messages.</span></span> <span data-ttu-id="031a8-109">受信メッセージの解読と送信メッセージの署名に秘密キー証明書を使用します。</span><span class="sxs-lookup"><span data-stu-id="031a8-109">BizTalk Server uses private key certificates for decrypting inbound messages and signing outbound messages.</span></span>  
  
 <span data-ttu-id="031a8-110">BizTalk Server で使用する証明書は、BizTalk エクスプローラーおよび BizTalk Server 管理コンソールで構成できます。</span><span class="sxs-lookup"><span data-stu-id="031a8-110">You configure the certificates BizTalk Server uses in BizTalk Explorer and in the BizTalk Administration Console.</span></span>  
  
 <span data-ttu-id="031a8-111">デジタル証明書の詳細については、Microsoft TechNet Web サイトを参照してください。 [http://go.microsoft.com/fwlink/?LinkId=60508](http://go.microsoft.com/fwlink/?LinkId=60508)です。</span><span class="sxs-lookup"><span data-stu-id="031a8-111">For more information about digital certificates, see the Microsoft TechNet Web site at [http://go.microsoft.com/fwlink/?LinkId=60508](http://go.microsoft.com/fwlink/?LinkId=60508).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="031a8-112">S/MIME (Secure Multipurpose Internet Mail Extensions) メッセージの処理中に、BizTalk Server エンジンで証明書の失効一覧 (CRL) を確認し、証明書が期限切れではないことと、ルート証明機関 (CA) にさかのぼって証明書が有効であることを確認することもできます。</span><span class="sxs-lookup"><span data-stu-id="031a8-112">While processing Secure Multipurpose Internet Mail Extensions (S/MIME) messages, you can choose to have the BizTalk Server engine check the Certificate Revocation List (CRL) to ensure that a certificate has not expired and that it is trusted down to a Root Certificate Authority (CA).</span></span> <span data-ttu-id="031a8-113">確認は、パイプラインでメッセージが処理されている間に MIME/SMIME デコーダ コンポーネントで行われます。</span><span class="sxs-lookup"><span data-stu-id="031a8-113">This verification occurs while the pipeline processes the message, in the MIME/SMIME decoder component.</span></span> <span data-ttu-id="031a8-114">設定する方法の詳細についての**失効リストを確認**プロパティを参照してください[- MIME/SMIME デコーダー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-mime-smime-decoder-pipeline-component.md)です。</span><span class="sxs-lookup"><span data-stu-id="031a8-114">For more information about how to set **Check Revocation List** property, see [How to Configure the MIME-SMIME Decoder Pipeline Component](../core/how-to-configure-the-mime-smime-decoder-pipeline-component.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="031a8-115">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="031a8-115">In This Section</span></span>  
  
-   [<span data-ttu-id="031a8-116">BizTalk Server で使用される証明書ストア</span><span class="sxs-lookup"><span data-stu-id="031a8-116">Certificate Stores that BizTalk Server Uses</span></span>](../core/certificate-stores-that-biztalk-server-uses.md)  
  
-   [<span data-ttu-id="031a8-117">BizTalk Server が署名されたメッセージで使用する証明書</span><span class="sxs-lookup"><span data-stu-id="031a8-117">Certificates that BizTalk Server Uses for Signed Messages</span></span>](../core/certificates-that-biztalk-server-uses-for-signed-messages.md)  
  
-   [<span data-ttu-id="031a8-118">BizTalk Server は暗号化されたメッセージを使用する証明書</span><span class="sxs-lookup"><span data-stu-id="031a8-118">Certificates that BizTalk Server Uses for Encrypted Messages</span></span>](../core/certificates-that-biztalk-server-uses-for-encrypted-messages.md)