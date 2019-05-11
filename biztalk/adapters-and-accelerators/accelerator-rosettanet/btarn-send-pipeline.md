---
title: BTARN 送信パイプライン |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- XML Assembler
- send pipelines, message flow
- DOCTYPE headers
- MIME/SMIME Encoder
- send pipelines, BTARN
- BTARN, send pipelines
- XML Preprocessor
- messages, message flow
ms.assetid: 88562132-0ea4-4b5a-9445-b69f6c84e5ea
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 62c86e810ad185f7497f73c1b4d4d53cffe8f29e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65284872"
---
# <a name="btarn-send-pipeline"></a><span data-ttu-id="c2660-102">BTARN 送信パイプライン</span><span class="sxs-lookup"><span data-stu-id="c2660-102">BTARN Send Pipeline</span></span>
<span data-ttu-id="c2660-103">Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] RNIFSend パイプライン (RNIFSend.btp) で転送するために RosettaNet Implementation Framework (RNIF) メッセージを準備します。</span><span class="sxs-lookup"><span data-stu-id="c2660-103">Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] prepares a RosettaNet Implementation Framework (RNIF) message for transmission in the RNIFSend pipeline (RNIFSend.btp).</span></span> <span data-ttu-id="c2660-104">送信パイプラインは、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c2660-104">The send pipeline includes the following:</span></span>  
  
-   <span data-ttu-id="c2660-105">XML プリプロセッサ</span><span class="sxs-lookup"><span data-stu-id="c2660-105">XML preprocessor</span></span>  
  
-   <span data-ttu-id="c2660-106">XML アセンブラー</span><span class="sxs-lookup"><span data-stu-id="c2660-106">XML assembler</span></span>  
  
-   <span data-ttu-id="c2660-107">Multipurpose Internet Mail Extensions Multipurpose Internet Mail Extensions (MIME/SMIME) エンコーダー</span><span class="sxs-lookup"><span data-stu-id="c2660-107">Multipurpose Internet Mail Extensions/Secure Multipurpose Internet Mail Extensions (MIME/SMIME) encoder</span></span>  
  
## <a name="xml-preprocessor"></a><span data-ttu-id="c2660-108">XML プリプロセッサ</span><span class="sxs-lookup"><span data-stu-id="c2660-108">XML Preprocessor</span></span>  
 <span data-ttu-id="c2660-109">XML プリプロセッサは、メッセージに DOCTYPE ヘッダーを追加します。</span><span class="sxs-lookup"><span data-stu-id="c2660-109">The XML preprocessor adds a DOCTYPE header to the message.</span></span> <span data-ttu-id="c2660-110">ヘッダーは、メッセージに関連付けられているドキュメント型定義 (DTD) スキーマを識別します。</span><span class="sxs-lookup"><span data-stu-id="c2660-110">The header identifies the document type definition (DTD) schema associated with the message.</span></span> <span data-ttu-id="c2660-111">RNIF 仕様では、RNIF 送信の DOCTYPE ヘッダーの存在が必要です。</span><span class="sxs-lookup"><span data-stu-id="c2660-111">The RNIF specification requires the presence of a DOCTYPE header for RNIF transmission.</span></span>  
  
## <a name="xml-assembler"></a><span data-ttu-id="c2660-112">XML アセンブラー</span><span class="sxs-lookup"><span data-stu-id="c2660-112">XML Assembler</span></span>  
 <span data-ttu-id="c2660-113">XML アセンブラーは、BizTalk Server の XML アセンブラに基づいています。</span><span class="sxs-lookup"><span data-stu-id="c2660-113">The XML assembler is based on the BizTalk Server XML assembler.</span></span> <span data-ttu-id="c2660-114">プロパティをメッセージ コンテキストからエンベロープおよびドキュメントに転送します。</span><span class="sxs-lookup"><span data-stu-id="c2660-114">It transfers properties from the message context back into envelopes and documents.</span></span> <span data-ttu-id="c2660-115">XML 部分および添付ファイルからメッセージをアセンブルします。</span><span class="sxs-lookup"><span data-stu-id="c2660-115">It assembles the message from its XML parts and attachments.</span></span> <span data-ttu-id="c2660-116">メッセージの検証は実行されません。</span><span class="sxs-lookup"><span data-stu-id="c2660-116">It does not perform message validation.</span></span>  
  
 <span data-ttu-id="c2660-117">詳細については、ネイティブ[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]XML アセンブラー、BizTalk Server ヘルプの「XML アセンブラー パイプライン コンポーネント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c2660-117">For more information about the native [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] XML assembler, see "XML Assembler Pipeline Component" in BizTalk Server Help.</span></span>  
  
## <a name="mimesmime-encoder"></a><span data-ttu-id="c2660-118">MIME/SMIME エンコーダー</span><span class="sxs-lookup"><span data-stu-id="c2660-118">MIME/SMIME Encoder</span></span>  
 <span data-ttu-id="c2660-119">MIME/SMIME エンコーダーは、BizTalk Server の MIME/SMIME エンコーダに基づいています。</span><span class="sxs-lookup"><span data-stu-id="c2660-119">The MIME/SMIME encoder is based on the BizTalk Server MIME/SMIME Encoder.</span></span> <span data-ttu-id="c2660-120">取引先のパートナー契約と、BizTalk Server の MIME/SMIME エンコーダーの設定のプロトコル設定に応じて、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]エンコーダーは、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="c2660-120">Depending on the protocol settings in the trading partner agreement, and the settings of the BizTalk Server MIME/SMIME Encoder, the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] encoder performs the following:</span></span>  
  
- <span data-ttu-id="c2660-121">RNIF 1.1 メッセージを必要に応じて、メッセージには、8 バイトのバイナリ ヘッダーを追加します。</span><span class="sxs-lookup"><span data-stu-id="c2660-121">Adds an 8-byte binary header to the message, as required for RNIF 1.1 messages.</span></span>  
  
- <span data-ttu-id="c2660-122">メッセージの部分をエンコードし、ダイジェストを計算します。</span><span class="sxs-lookup"><span data-stu-id="c2660-122">Encodes the message parts, and calculates the digest.</span></span>  
  
- <span data-ttu-id="c2660-123">(Service content と添付ファイル) のペイロードまたはペイロード コンテナー (service content とヘッダーのサービスとの添付ファイル) を暗号化します。</span><span class="sxs-lookup"><span data-stu-id="c2660-123">Encrypts the payload (service content plus attachments), or the payload container (service content plus service header plus attachments).</span></span> <span data-ttu-id="c2660-124">設定した場合、**すべてのポートをエンコード**の設定、**プロトコル**を取引先アグリーメントのタブ`False`、エンコーダはペイロードのみを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="c2660-124">If you have set the **Encode all ports** setting on the **Protocol** tab of the trading partner agreement to `False`, the encoder will encrypt only the payload.</span></span> <span data-ttu-id="c2660-125">設定した場合、**すべてのポートをエンコード**設定`True`、エンコーダはペイロード コンテナーを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="c2660-125">If you have set the **Encode all ports** setting to `True`, the encoder will encrypt the payload container.</span></span>  
  
  <span data-ttu-id="c2660-126">詳細については、ネイティブ[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]MIME/SMIME エンコーダーでは、BizTalk Server ヘルプの「MIME/SMIME エンコーダー パイプライン コンポーネント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c2660-126">For more information about the native [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] MIME/SMIME Encoder, see "MIME/SMIME Encoder Pipeline Component" in BizTalk Server Help.</span></span>  
  
## <a name="message-flow"></a><span data-ttu-id="c2660-127">メッセージ フロー</span><span class="sxs-lookup"><span data-stu-id="c2660-127">Message Flow</span></span>  
 <span data-ttu-id="c2660-128">メッセージ フローは、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]送信パイプラインは、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="c2660-128">The message flow through the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] send pipeline is as follows:</span></span>  
  
1.  <span data-ttu-id="c2660-129">設定した場合、**すべての部分のエンコード**を取引先アグリーメントの設定`True`、MIME/SMIME エンコーダはすべてのメッセージ部分をエンコードします。</span><span class="sxs-lookup"><span data-stu-id="c2660-129">If you have set the **Encode all parts** setting of the trading partner agreement to `True`, the MIME/SMIME encoder will encode all message parts.</span></span> <span data-ttu-id="c2660-130">エンコード方式で設定が使用されます、`Encoding`アグリーメントのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="c2660-130">It will use the encoding method set in the `Encoding` property of the agreement.</span></span>  
  
2.  <span data-ttu-id="c2660-131">RNIF 2.01 では、メッセージがアクション メッセージと添付ファイルがある場合、エンコーダーは次の処理添付ファイルごとに。</span><span class="sxs-lookup"><span data-stu-id="c2660-131">For RNIF 2.01, if the message is an action message and there is an attachment, the encoder will do the following for each attachment:</span></span>  
  
    1.  <span data-ttu-id="c2660-132">添付ファイルがバイナリの場合は、エンコーダーによってエンコードされます。</span><span class="sxs-lookup"><span data-stu-id="c2660-132">If the attachment is binary, the encoder will encode it.</span></span>  
  
    2.  <span data-ttu-id="c2660-133">エンコーダーは、添付ファイルのコンテンツ ID が生成されます。</span><span class="sxs-lookup"><span data-stu-id="c2660-133">The encoder will generate a content ID for the attachment.</span></span>  
  
    3.  <span data-ttu-id="c2660-134">エンコーダーでは、添付ファイルの MIME パートを作成します。</span><span class="sxs-lookup"><span data-stu-id="c2660-134">The encoder will create a MIME part for the attachment.</span></span>  
  
3.  <span data-ttu-id="c2660-135">RNIF 2.01 では、パイプラインはメッセージ部分を暗号化しの設定に応じて RNIF メッセージを作成する**永続的な機密性**(として、プロセス構成設定で設定)。</span><span class="sxs-lookup"><span data-stu-id="c2660-135">For RNIF 2.01, the pipeline will encrypt message parts and build the RNIF message depending on the setting of **Is Persistent Confidentiality Required** (as set in the process configuration settings):</span></span>  
  
    1.  <span data-ttu-id="c2660-136">設定した場合**永続的な機密性**に**ペイロード**エンコーダーは service content と添付ファイルを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="c2660-136">If you have set **Is Persistent Confidentiality Required** to **Payload**, the encoder will encrypt the service content and the attachments.</span></span> <span data-ttu-id="c2660-137">アセンブラーは、service header、delivery header、および preamble を RNIF メッセージを完成し追加します。</span><span class="sxs-lookup"><span data-stu-id="c2660-137">The assembler will then add the service header, delivery header, and preamble to construct the final RNIF message.</span></span>  
  
    2.  <span data-ttu-id="c2660-138">設定した場合**永続的な機密性**に**ペイロード コンテナー**エンコーダーは service header、service content と添付ファイルを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="c2660-138">If you have set **Is Persistent Confidentiality Required** to **Payload Container**, the encoder will encrypt the service header, service content, and the attachments.</span></span> <span data-ttu-id="c2660-139">アセンブラーは delivery header と preamble 最後の RNIF メッセージを追加します。</span><span class="sxs-lookup"><span data-stu-id="c2660-139">The assembler will then add the delivery header and preamble to construct the final RNIF message.</span></span>  
  
    3.  <span data-ttu-id="c2660-140">設定した場合**永続的な機密性**に**None**アセンブラーは service content と添付ファイルを含めずに、service header、delivery header、および preamble が追加されます暗号化) をクリックし、最後の RNIF メッセージを構築します。</span><span class="sxs-lookup"><span data-stu-id="c2660-140">If you have set **Is Persistent Confidentiality Required** to **None**, the assembler will add the service header, delivery header, and preamble to the service content and the attachments (without encryption) to construct the final RNIF message.</span></span>  
  
4.  <span data-ttu-id="c2660-141">RNIF 1.1 では、アセンブラーは暗号化なしの最後の RNIF メッセージを構築します。</span><span class="sxs-lookup"><span data-stu-id="c2660-141">For RNIF 1.1, the assembler will construct the final RNIF message without encryption.</span></span>  
  
5.  <span data-ttu-id="c2660-142">エンコーダーは、次の例でメッセージに署名されます。</span><span class="sxs-lookup"><span data-stu-id="c2660-142">The encoder will sign the message in the following case:</span></span>  
  
    1.  <span data-ttu-id="c2660-143">メッセージがシグナル メッセージでは、および**否認不可のために必要な**プロパティ (プロセス構成の設定) では、`True`します。</span><span class="sxs-lookup"><span data-stu-id="c2660-143">The message is a signal message, and the **Non-Repudiation Required** property (in the process configuration settings) is `True`.</span></span>  
  
    2.  <span data-ttu-id="c2660-144">メッセージがアクション メッセージでは、および**発信元とコンテンツの否認**プロパティ (プロセス構成の設定) では、`True`します。</span><span class="sxs-lookup"><span data-stu-id="c2660-144">The message is an action message, and the **Non-Repudiation of Origin and Content** property (in the process configuration settings) is `True`.</span></span>  
  
6.  <span data-ttu-id="c2660-145">RNIF 2.01 では、エンコーダーは、MIME メッセージの最初のボディ部のダイジェストを計算し、ダイジェストを保持します。</span><span class="sxs-lookup"><span data-stu-id="c2660-145">For RNIF 2.01, the encoder will calculate the digest on the first body part of the MIME message, and persist the digest.</span></span> <span data-ttu-id="c2660-146">メソッドのセットを使用してダイジェストを計算には、`Digest`取引先アグリーメント (sha-1 または MD5) のメソッドのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="c2660-146">It will calculate the digest using the method set in the `Digest` method property in the trading partner agreement (SHA-1 or MD5).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2660-147">参照</span><span class="sxs-lookup"><span data-stu-id="c2660-147">See Also</span></span>  
 [<span data-ttu-id="c2660-148">BTARN でのメッセージ処理</span><span class="sxs-lookup"><span data-stu-id="c2660-148">Message Processing in BTARN</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/message-processing-in-btarn.md)