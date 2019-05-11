---
title: 暗号化と証明書の署名 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ee36208b232609c5a73ede9a933f692a0681827f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65349548"
---
# <a name="encryption-and-signing-certificates"></a><span data-ttu-id="229a4-102">暗号化および署名証明書</span><span class="sxs-lookup"><span data-stu-id="229a4-102">Encryption and Signing Certificates</span></span>
<span data-ttu-id="229a4-103">Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]は、証明書のセキュリティに大きく依存します。</span><span class="sxs-lookup"><span data-stu-id="229a4-103">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] relies heavily on the security provided by certificates.</span></span> <span data-ttu-id="229a4-104">暗号化とデジタル署名の証明書を使用して BizTalk Server はことができます、信頼できるし、処理するデータが安全であることを確認に役立つデータを送受信します。</span><span class="sxs-lookup"><span data-stu-id="229a4-104">By using certificates for encryption and digital signatures, BizTalk Server can send and receive data that can be trusted, and can help ensure that the data it processes is secure.</span></span> <span data-ttu-id="229a4-105">暗号化とデジタル署名の両方の公開キー証明書と秘密キー証明書があります。</span><span class="sxs-lookup"><span data-stu-id="229a4-105">For both encryption and digital signatures, there is a public key certificate and a private key certificate.</span></span> <span data-ttu-id="229a4-106">暗号化は、メッセージの送信者は受信者の公開キー証明書を使用して、(BizTalk Server) のメッセージの受信者、メッセージの解読にその秘密キーを使用しますが、メッセージを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="229a4-106">For encryption, the sender of the message uses the receiver's public key certificate to encrypt the message, while the receiver of the message (BizTalk Server) uses its private key to decrypt the message.</span></span> <span data-ttu-id="229a4-107">デジタル署名は、メッセージの送信者が、メッセージの署名に秘密キー証明書を使用し、(BizTalk Server) のメッセージの受信者が送信者の公開キー証明書を使用して署名を検証します。</span><span class="sxs-lookup"><span data-stu-id="229a4-107">For digital signatures, the sender of the message uses a private key certificate to sign the message, and the receiver of the message (BizTalk Server) uses the public key certificate of the sender to verify the signature.</span></span>  
  
 <span data-ttu-id="229a4-108">BizTalk Server では、公開キー証明書を使用して、受信メッセージの送信メッセージの暗号化とデジタル署名を検証します。</span><span class="sxs-lookup"><span data-stu-id="229a4-108">BizTalk Server uses public key certificates to verify the digital signatures of inbound messages and for encrypting outbound messages.</span></span> <span data-ttu-id="229a4-109">BizTalk Server では、受信メッセージの解読と送信メッセージの署名を秘密キー証明書を使用します。</span><span class="sxs-lookup"><span data-stu-id="229a4-109">BizTalk Server uses private key certificates for decrypting inbound messages and signing outbound messages.</span></span>  
  
 <span data-ttu-id="229a4-110">BizTalk エクスプ ローラーで、BizTalk 管理コンソールでは、BizTalk Server を使用して証明書を構成します。</span><span class="sxs-lookup"><span data-stu-id="229a4-110">You configure the certificates BizTalk Server uses in BizTalk Explorer and in the BizTalk Administration Console.</span></span>  
  
 <span data-ttu-id="229a4-111">デジタル証明書の詳細については、Microsoft TechNet Web サイトを参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=60508](http://go.microsoft.com/fwlink/?LinkId=60508)します。</span><span class="sxs-lookup"><span data-stu-id="229a4-111">For more information about digital certificates, see the Microsoft TechNet Web site at [http://go.microsoft.com/fwlink/?LinkId=60508](http://go.microsoft.com/fwlink/?LinkId=60508).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="229a4-112">Secure Multipurpose Internet Mail Extensions (S/MIME) メッセージを処理中には、証明書の有効期限が切れていないことと、ルートまで信頼されていることを確認する証明書失効リスト (CRL) を確認してください。 BizTalk Server エンジンを選択できます。証明書機関 (CA)。</span><span class="sxs-lookup"><span data-stu-id="229a4-112">While processing Secure Multipurpose Internet Mail Extensions (S/MIME) messages, you can choose to have the BizTalk Server engine check the Certificate Revocation List (CRL) to ensure that a certificate has not expired and that it is trusted down to a Root Certificate Authority (CA).</span></span> <span data-ttu-id="229a4-113">この検証では、パイプラインは、MIME/SMIME デコーダー コンポーネントで、メッセージの処理中に発生します。</span><span class="sxs-lookup"><span data-stu-id="229a4-113">This verification occurs while the pipeline processes the message, in the MIME/SMIME decoder component.</span></span> <span data-ttu-id="229a4-114">設定する方法の詳細についての**失効リストを確認**プロパティを参照してください[MIME-SMIME デコーダー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-mime-smime-decoder-pipeline-component.md)します。</span><span class="sxs-lookup"><span data-stu-id="229a4-114">For more information about how to set **Check Revocation List** property, see [How to Configure the MIME-SMIME Decoder Pipeline Component](../core/how-to-configure-the-mime-smime-decoder-pipeline-component.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="229a4-115">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="229a4-115">In This Section</span></span>  
  
-   [<span data-ttu-id="229a4-116">BizTalk Server で使用される証明書ストア</span><span class="sxs-lookup"><span data-stu-id="229a4-116">Certificate Stores that BizTalk Server Uses</span></span>](../core/certificate-stores-that-biztalk-server-uses.md)  
  
-   [<span data-ttu-id="229a4-117">BizTalk Server で署名付きメッセージに使用する証明書</span><span class="sxs-lookup"><span data-stu-id="229a4-117">Certificates that BizTalk Server Uses for Signed Messages</span></span>](../core/certificates-that-biztalk-server-uses-for-signed-messages.md)  
  
-   [<span data-ttu-id="229a4-118">BizTalk Server で暗号化されたメッセージに使用する証明書</span><span class="sxs-lookup"><span data-stu-id="229a4-118">Certificates that BizTalk Server Uses for Encrypted Messages</span></span>](../core/certificates-that-biztalk-server-uses-for-encrypted-messages.md)