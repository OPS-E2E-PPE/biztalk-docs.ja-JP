---
title: 構成の署名、圧縮、および AS2 トランスポートでの暗号化 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bc3537a7-c065-4a33-a375-29e7902b5ffa
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4a154255cb64fcebafa2ef8164714e46bf5673ba
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007204"
---
# <a name="configuring-signing-compression-and-encryption-in-as2-transport"></a><span data-ttu-id="6166d-102">AS2 トランスポートでの署名、圧縮、および暗号化の構成</span><span class="sxs-lookup"><span data-stu-id="6166d-102">Configuring Signing, Compression, and Encryption in AS2 Transport</span></span>
<span data-ttu-id="6166d-103">デジタル署名、署名の確認、暗号化、および解読は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソール内から構成できます。</span><span class="sxs-lookup"><span data-stu-id="6166d-103">You can configure digital signatures, signature verification, encryption, and decryption from within the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console.</span></span> <span data-ttu-id="6166d-104">この構成では、AS2 パイプラインおよび BizTalk パーティに適切なプロパティを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6166d-104">This configuration requires that you set the appropriate properties for the AS2 pipelines and BizTalk parties.</span></span>  
  
## <a name="using-as2-pipelines"></a><span data-ttu-id="6166d-105">AS2 パイプラインの使用</span><span class="sxs-lookup"><span data-stu-id="6166d-105">Using AS2 Pipelines</span></span>  
 <span data-ttu-id="6166d-106">受信 AS2 メッセージのセキュリティを確保するには、受信場所で AS2 受信パイプライン (AS2EdiReceive または AS2Receive) を使用します。</span><span class="sxs-lookup"><span data-stu-id="6166d-106">To help secure an inbound AS2 message, use an AS2 receive pipeline (AS2EdiReceive or AS2Receive) in your receive location.</span></span> <span data-ttu-id="6166d-107">AS2 デコーダーは AS2 メッセージの暗号化や圧縮解除を行うほか、署名の確認も実行します。</span><span class="sxs-lookup"><span data-stu-id="6166d-107">The AS2 Decoder decrypts, decompresses, and/or performs signature verification on AS2 messages.</span></span> <span data-ttu-id="6166d-108">これは方法の詳細については、の「AS2 デコーダー」セクションを参照してください。 [AS2 の受信コンポーネント](../core/as2-receive-components.md)します。</span><span class="sxs-lookup"><span data-stu-id="6166d-108">For more information on how it does so, see the "AS2 Decoder" section of [AS2 Receive Components](../core/as2-receive-components.md).</span></span>  
  
 <span data-ttu-id="6166d-109">送信 AS2 メッセージのセキュリティを確保するには、送信場所で AS2 送信パイプライン (AS2EdiSend または AS2Send) を使用します。</span><span class="sxs-lookup"><span data-stu-id="6166d-109">To help secure an outbound AS2 message, use an AS2 send pipeline (AS2EdiSend or AS2Send) in your send port.</span></span> <span data-ttu-id="6166d-110">AS2 エンコーダーは、送信 AS2 メッセージの署名、圧縮、および暗号化を行います。</span><span class="sxs-lookup"><span data-stu-id="6166d-110">The AS2 Encoder signs, compresses, and encrypts outbound AS2 messages.</span></span> <span data-ttu-id="6166d-111">これは方法の詳細については、の「AS2 エンコーダー」セクションを参照してください。 [AS2 送信コンポーネント](../core/as2-send-components.md)します。</span><span class="sxs-lookup"><span data-stu-id="6166d-111">For more information on how it does so, see the "AS2 Encoder" section of [AS2 Send Components](../core/as2-send-components.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="6166d-112">メッセージに署名したら、シグネチャ BLOB を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="6166d-112">Once a message has been signed, the signature blob must not be changed.</span></span> <span data-ttu-id="6166d-113">シグネチャ BLOB を変更すると、署名は破損します。</span><span class="sxs-lookup"><span data-stu-id="6166d-113">If changed, the signature would be corrupted.</span></span> <span data-ttu-id="6166d-114">境界ヘッダー、または境界ヘッダーの外側にあるものはすべて変更できますが、境界ヘッダーの内側にあるものは変更できません。</span><span class="sxs-lookup"><span data-stu-id="6166d-114">The boundary header, or anything outside the boundary headers, can be changed, but anything within the boundary headers must not be changed.</span></span>  
  
## <a name="setting-as2-agreement-properties"></a><span data-ttu-id="6166d-115">AS2 アグリーメント プロパティの設定</span><span class="sxs-lookup"><span data-stu-id="6166d-115">Setting AS2 Agreement Properties</span></span>  
 <span data-ttu-id="6166d-116">署名と暗号化処理を構成するには、AS2 アグリーメントのプロパティを次のように設定します。</span><span class="sxs-lookup"><span data-stu-id="6166d-116">You configure signature and encryption processing by setting AS2 agreement properties as follows:</span></span>  
  
- <span data-ttu-id="6166d-117">署名、圧縮、または、送信メッセージを暗号化するを確認、**メッセージに署名する必要があります**、**メッセージを圧縮する**、および**メッセージを暗号化する必要がある**プロパティを**検証**で (送信 AS2 メッセージ) の一方向アグリーメント タブのページ、**アグリーメントのプロパティ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="6166d-117">To sign, compress, and/or encrypt an outbound message, check the **Message should be signed**, **Message should be compressed**, and **Message should be encrypted** properties on the **Validation** page of the one-way agreement tab (for the outgoing AS2 message) in the **Agreement Properties** dialog box.</span></span>  
  
- <span data-ttu-id="6166d-118">送信メッセージへの応答として署名付き MDN を要求するには、確認、 **MDN の要求**と**署名付き MDN を要求**プロパティを**受信確認 (Mdn)** のページ、一方向アグリーメント タブの**アグリーメントのプロパティ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="6166d-118">To request a signed MDN in response to an outbound message, check the **Request MDN** and **Request signed MDN** properties on the **Acknowledgements (MDNs)** page of the one-way agreement tab of the **Agreement Properties** dialog box.</span></span>  
  
- <span data-ttu-id="6166d-119">受信メッセージが署名されている、圧縮の指定や確認、暗号化、**検証および MDN に対してメッセージ ヘッダーの代わりにアグリーメントの設定を使用して**プロパティ、**メッセージに署名する必要があります**プロパティを**メッセージを圧縮する**プロパティ、および**メッセージを暗号化する必要があります**プロパティを**検証**一方向のアグリーメントのページタブ (受信 AS2 メッセージ) に対して、**アグリーメントのプロパティ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="6166d-119">To specify that an inbound message is signed, compressed, and/or encrypted, check the **Use agreement settings for validation and MDN instead of message header** property, the **Message should be signed** property, the **Message should be compressed** property, and the **Message should be encrypted** property on the **Validation** page of the one-way agreement tab (for the incoming AS2 message) in the **Agreement Properties** dialog box.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="6166d-120">ときに、**検証および MDN に対してメッセージ ヘッダーの代わりにアグリーメントの設定を使用して**プロパティが選択されている、受信メッセージのすべてのヘッダー詳細は無視され、アグリーメントの設定に基づいて、メッセージを処理します。</span><span class="sxs-lookup"><span data-stu-id="6166d-120">When the **Use agreement settings for validation and MDN instead of message header** property is selected, all header details of the incoming message are ignored and the message is processed based on the agreement settings.</span></span>  
  
- <span data-ttu-id="6166d-121">選択して、受信メッセージのプロパティがオーバーライドされると、受信メッセージへの応答で、署名付き MDN を指定する、**検証および MDN に対してメッセージ ヘッダーの代わりにアグリーメントの設定を使用して**プロパティ、確認、 **署名付き MDN を要求**プロパティ**受信確認 (Mdn)** のページ、**アグリーメントのプロパティ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="6166d-121">To specify a signed MDN in response to an inbound message, when the inbound message properties are overridden by selecting the **Use agreement settings for validation and MDN instead of message header** property, check the **Request Signed MDN** property on **Acknowledgements (MDNs)** page of the **Agreement Properties** dialog box.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="6166d-122">ときに、**検証および MDN に対してメッセージ ヘッダーの代わりにアグリーメントの設定を使用して**プロパティが選択されている、受信メッセージのすべてのヘッダー詳細は無視され、アグリーメントの設定に基づいて、メッセージを処理します。</span><span class="sxs-lookup"><span data-stu-id="6166d-122">When the **Use agreement settings for validation and MDN instead of message header** property is selected, all header details of the incoming message are ignored and the message is processed based on the agreement settings.</span></span>  
  
- <span data-ttu-id="6166d-123">受信メッセージのプロパティがオーバーライドされていない場合、受信メッセージへの応答で、署名付き MDN を指定する (、**検証および MDN に対してメッセージ ヘッダーの代わりにアグリーメントの設定を使用して**がクリアされます)、メッセージ ヘッダーはありませんが、署名するには、指定を確認、**廃棄通知-オプションのヘッダーが存在しない場合、または受信プロトコルの署名済みヘッダーが省略可能に設定されている場合要求された MDN に署名**プロパティを**受信元 MDN 設定**のページ、**アグリーメントのプロパティ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="6166d-123">To specify a signed MDN in response to an inbound message, when the inbound message properties are not overridden (the **Use agreement settings for validation and MDN instead of message header** is cleared), but the message headers do not specify signing, check the **Sign requested MDN if Disposition-Notification-Option header is not present or if Signed-Receipt-Protocol header is set to optional** property on the **Receiver MDN Settings** page of the **Agreement Properties** dialog box.</span></span>  
  
- <span data-ttu-id="6166d-124">送信 AS2 メッセージの BizTalk グループのプロパティで指定されている別の署名証明書を指定する [**グループ署名証明書を上書き**で、**署名証明書**の一方向アグリーメント タブのページ、**アグリーメントのプロパティ**] ダイアログ ボックス、および署名証明書を指定します。</span><span class="sxs-lookup"><span data-stu-id="6166d-124">To specify a different signing certificate than the one specified in the BizTalk Group properties for outgoing AS2 messages, select **Override Group Signature Certificate** in the **Signature Certificate** page of the one-way agreement tab of the **Agreement Properties** dialog box, and specify a signing certificate.</span></span> <span data-ttu-id="6166d-125">このプロパティを設定するで提供された証明書を使用して、アグリーメントに解決される AS2 メッセージが署名される場合、**署名証明書**ページし、証明書ではなく、BizTalk グループのプロパティの一部として提供します。</span><span class="sxs-lookup"><span data-stu-id="6166d-125">If this property is set, whichever AS2 message that resolves to the agreement will be signed using the certificate provided in the **Signature Certificate** page and not by the certificate provided as part of the BizTalk Group properties.</span></span>  
  
  <span data-ttu-id="6166d-126">パーティのプロパティの設定に関する詳細については、次を参照してください。 [AS2 プロパティを設定する](../core/configuring-as2-properties.md)します。</span><span class="sxs-lookup"><span data-stu-id="6166d-126">For more information about setting up party properties, see [Configuring AS2 Properties](../core/configuring-as2-properties.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6166d-127">参照</span><span class="sxs-lookup"><span data-stu-id="6166d-127">See Also</span></span>  
 <span data-ttu-id="6166d-128">[AS2 セキュリティ](../core/as2-security.md) </span><span class="sxs-lookup"><span data-stu-id="6166d-128">[AS2 Security](../core/as2-security.md) </span></span>  
 <span data-ttu-id="6166d-129">[AS2 の証明書の構成](../core/configuring-certificates-for-as2.md) </span><span class="sxs-lookup"><span data-stu-id="6166d-129">[Configuring Certificates for AS2](../core/configuring-certificates-for-as2.md) </span></span>  
 <span data-ttu-id="6166d-130">[AS2 メッセージ](../core/as2-messages.md) </span><span class="sxs-lookup"><span data-stu-id="6166d-130">[AS2 Messages](../core/as2-messages.md) </span></span>  
 <span data-ttu-id="6166d-131">[AS2 の受信コンポーネント](../core/as2-receive-components.md) </span><span class="sxs-lookup"><span data-stu-id="6166d-131">[AS2 Receive Components](../core/as2-receive-components.md) </span></span>  
 <span data-ttu-id="6166d-132">[AS2 送信コンポーネント](../core/as2-send-components.md) </span><span class="sxs-lookup"><span data-stu-id="6166d-132">[AS2 Send Components](../core/as2-send-components.md) </span></span>  
 [<span data-ttu-id="6166d-133">AS2 プロパティの構成</span><span class="sxs-lookup"><span data-stu-id="6166d-133">Configuring AS2 Properties</span></span>](../core/configuring-as2-properties.md)