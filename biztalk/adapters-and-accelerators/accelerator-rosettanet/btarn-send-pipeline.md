---
title: BTARN 送信パイプライン |Microsoft ドキュメント
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
ms.openlocfilehash: f566b37cc43f8aca2f0a36143d10d809c008d5cd
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
ms.locfileid: "26007523"
---
# <a name="btarn-send-pipeline"></a><span data-ttu-id="fe78c-102">BTARN 送信パイプライン</span><span class="sxs-lookup"><span data-stu-id="fe78c-102">BTARN Send Pipeline</span></span>
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]<span data-ttu-id="fe78c-103">[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] RNIFSend パイプライン (RNIFSend.btp) で転送するための RosettaNet Implementation Framework (RNIF) メッセージを作成します。</span><span class="sxs-lookup"><span data-stu-id="fe78c-103"> [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] prepares a RosettaNet Implementation Framework (RNIF) message for transmission in the RNIFSend pipeline (RNIFSend.btp).</span></span> <span data-ttu-id="fe78c-104">送信パイプラインには、次のものが組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="fe78c-104">The send pipeline includes the following:</span></span>  
  
-   <span data-ttu-id="fe78c-105">XML プリプロセッサ</span><span class="sxs-lookup"><span data-stu-id="fe78c-105">XML preprocessor</span></span>  
  
-   <span data-ttu-id="fe78c-106">XML アセンブラー</span><span class="sxs-lookup"><span data-stu-id="fe78c-106">XML assembler</span></span>  
  
-   <span data-ttu-id="fe78c-107">MIME/SMIME (Multipurpose Internet Mail Extensions/SecureMultipurpose Internet Mail Extensions) エンコーダー</span><span class="sxs-lookup"><span data-stu-id="fe78c-107">Multipurpose Internet Mail Extensions/Secure Multipurpose Internet Mail Extensions (MIME/SMIME) encoder</span></span>  
  
## <a name="xml-preprocessor"></a><span data-ttu-id="fe78c-108">XML プリプロセッサ</span><span class="sxs-lookup"><span data-stu-id="fe78c-108">XML Preprocessor</span></span>  
 <span data-ttu-id="fe78c-109">XML プリプロセッサは、メッセージに DOCTYPE ヘッダーを追加します。</span><span class="sxs-lookup"><span data-stu-id="fe78c-109">The XML preprocessor adds a DOCTYPE header to the message.</span></span> <span data-ttu-id="fe78c-110">このヘッダーは、メッセージに関連付けるドキュメント型定義 (DTD) スキーマを指定します。</span><span class="sxs-lookup"><span data-stu-id="fe78c-110">The header identifies the document type definition (DTD) schema associated with the message.</span></span> <span data-ttu-id="fe78c-111">RNIF 仕様には、RNIF 送信のための DOCTYPE ヘッダーが必要です。</span><span class="sxs-lookup"><span data-stu-id="fe78c-111">The RNIF specification requires the presence of a DOCTYPE header for RNIF transmission.</span></span>  
  
## <a name="xml-assembler"></a><span data-ttu-id="fe78c-112">XML アセンブラー</span><span class="sxs-lookup"><span data-stu-id="fe78c-112">XML Assembler</span></span>  
 <span data-ttu-id="fe78c-113">XML アセンブラーは、BizTalk Server の XML アセンブラに基づいています。</span><span class="sxs-lookup"><span data-stu-id="fe78c-113">The XML assembler is based on the BizTalk Server XML assembler.</span></span> <span data-ttu-id="fe78c-114">XML アセンブラーは、メッセージ コンテキストからエンベロープとドキュメントにプロパティを転送します。</span><span class="sxs-lookup"><span data-stu-id="fe78c-114">It transfers properties from the message context back into envelopes and documents.</span></span> <span data-ttu-id="fe78c-115">そして、XML 部分および添付ファイルからメッセージを構築します。</span><span class="sxs-lookup"><span data-stu-id="fe78c-115">It assembles the message from its XML parts and attachments.</span></span> <span data-ttu-id="fe78c-116">メッセージの検証は実行しません。</span><span class="sxs-lookup"><span data-stu-id="fe78c-116">It does not perform message validation.</span></span>  
  
 <span data-ttu-id="fe78c-117">詳細については、ネイティブの[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]XML アセンブラー、BizTalk Server ヘルプの「XML アセンブラー パイプライン コンポーネント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fe78c-117">For more information about the native [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] XML assembler, see "XML Assembler Pipeline Component" in BizTalk Server Help.</span></span>  
  
## <a name="mimesmime-encoder"></a><span data-ttu-id="fe78c-118">MIME/SMIME エンコーダ</span><span class="sxs-lookup"><span data-stu-id="fe78c-118">MIME/SMIME Encoder</span></span>  
 <span data-ttu-id="fe78c-119">MIME/SMIME エンコーダーは、BizTalk Server MIME/SMIME エンコーダに基づいています。</span><span class="sxs-lookup"><span data-stu-id="fe78c-119">The MIME/SMIME encoder is based on the BizTalk Server MIME/SMIME Encoder.</span></span> <span data-ttu-id="fe78c-120">取引先アグリーメント、および BizTalk Server の MIME/SMIME エンコーダの設定でプロトコルの設定に応じて、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]エンコーダーは、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="fe78c-120">Depending on the protocol settings in the trading partner agreement, and the settings of the BizTalk Server MIME/SMIME Encoder, the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] encoder performs the following:</span></span>  
  
-   <span data-ttu-id="fe78c-121">RNIF 1.1 メッセージに必要な 8 バイトのバイナリ ヘッダーをメッセージに追加します。</span><span class="sxs-lookup"><span data-stu-id="fe78c-121">Adds an 8-byte binary header to the message, as required for RNIF 1.1 messages.</span></span>  
  
-   <span data-ttu-id="fe78c-122">メッセージ部分をエンコードし、ダイジェストを計算します。</span><span class="sxs-lookup"><span data-stu-id="fe78c-122">Encodes the message parts, and calculates the digest.</span></span>  
  
-   <span data-ttu-id="fe78c-123">ペイロード (Service Content と添付ファイル) またはペイロード コンテナー (Service Content、Service Header、および添付ファイル) を暗号化します。</span><span class="sxs-lookup"><span data-stu-id="fe78c-123">Encrypts the payload (service content plus attachments), or the payload container (service content plus service header plus attachments).</span></span> <span data-ttu-id="fe78c-124">設定した場合、**すべてのポートをエンコード**の設定、**プロトコル**を取引先アグリーメントのタブ`False`、エンコーダはペイロードのみを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="fe78c-124">If you have set the **Encode all ports** setting on the **Protocol** tab of the trading partner agreement to `False`, the encoder will encrypt only the payload.</span></span> <span data-ttu-id="fe78c-125">設定した場合、**すべてのポートをエンコード**設定`True`、エンコーダはペイロード コンテナーを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="fe78c-125">If you have set the **Encode all ports** setting to `True`, the encoder will encrypt the payload container.</span></span>  
  
 <span data-ttu-id="fe78c-126">詳細については、ネイティブ[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]MIME/SMIME エンコーダー、BizTalk Server ヘルプの「MIME/SMIME エンコーダー パイプライン コンポーネント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fe78c-126">For more information about the native [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] MIME/SMIME Encoder, see "MIME/SMIME Encoder Pipeline Component" in BizTalk Server Help.</span></span>  
  
## <a name="message-flow"></a><span data-ttu-id="fe78c-127">メッセージ フロー</span><span class="sxs-lookup"><span data-stu-id="fe78c-127">Message Flow</span></span>  
 <span data-ttu-id="fe78c-128">[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 送信パイプラインを経由するメッセージ フローは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="fe78c-128">The message flow through the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] send pipeline is as follows:</span></span>  
  
1.  <span data-ttu-id="fe78c-129">設定した場合、**すべての部分のエンコード**を取引先アグリーメントの設定`True`、MIME/SMIME エンコーダはすべてのメッセージ部分をエンコードします。</span><span class="sxs-lookup"><span data-stu-id="fe78c-129">If you have set the **Encode all parts** setting of the trading partner agreement to `True`, the MIME/SMIME encoder will encode all message parts.</span></span> <span data-ttu-id="fe78c-130">アグリーメントの `Encoding` プロパティに設定されているエンコード方式が使用されます。</span><span class="sxs-lookup"><span data-stu-id="fe78c-130">It will use the encoding method set in the `Encoding` property of the agreement.</span></span>  
  
2.  <span data-ttu-id="fe78c-131">RNIF 2.01 では、メッセージがアクション メッセージで添付ファイルがある場合、エンコーダーは各添付ファイルに対して次の処理を実行します。</span><span class="sxs-lookup"><span data-stu-id="fe78c-131">For RNIF 2.01, if the message is an action message and there is an attachment, the encoder will do the following for each attachment:</span></span>  
  
    1.  <span data-ttu-id="fe78c-132">添付ファイルがバイナリの場合は、エンコーダーがエンコードします。</span><span class="sxs-lookup"><span data-stu-id="fe78c-132">If the attachment is binary, the encoder will encode it.</span></span>  
  
    2.  <span data-ttu-id="fe78c-133">エンコーダーは、添付ファイルのコンテンツ ID を生成します。</span><span class="sxs-lookup"><span data-stu-id="fe78c-133">The encoder will generate a content ID for the attachment.</span></span>  
  
    3.  <span data-ttu-id="fe78c-134">エンコーダーは、添付ファイルの MIME 部分を作成します。</span><span class="sxs-lookup"><span data-stu-id="fe78c-134">The encoder will create a MIME part for the attachment.</span></span>  
  
3.  <span data-ttu-id="fe78c-135">RNIF 2.01 で、パイプラインはメッセージ部分を暗号化し、設定に応じて RNIF メッセージを作成する**永続的な機密性の必要性が**(として、プロセス構成設定で設定)。</span><span class="sxs-lookup"><span data-stu-id="fe78c-135">For RNIF 2.01, the pipeline will encrypt message parts and build the RNIF message depending on the setting of **Is Persistent Confidentiality Required** (as set in the process configuration settings):</span></span>  
  
    1.  <span data-ttu-id="fe78c-136">設定した場合**永続的な機密性の必要性が**に**ペイロード**エンコーダーは service content と添付ファイルを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="fe78c-136">If you have set **Is Persistent Confidentiality Required** to **Payload**, the encoder will encrypt the service content and the attachments.</span></span> <span data-ttu-id="fe78c-137">次に、アセンブラーは Service Header、Delivery Header、および Preamble を追加して RNIF メッセージを完成します。</span><span class="sxs-lookup"><span data-stu-id="fe78c-137">The assembler will then add the service header, delivery header, and preamble to construct the final RNIF message.</span></span>  
  
    2.  <span data-ttu-id="fe78c-138">設定した場合**永続的な機密性の必要性が**に**ペイロード コンテナー**エンコーダーは service header、service content と添付ファイルを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="fe78c-138">If you have set **Is Persistent Confidentiality Required** to **Payload Container**, the encoder will encrypt the service header, service content, and the attachments.</span></span> <span data-ttu-id="fe78c-139">次に、アセンブラーは Delivery Header と Preamble を追加して RNIF メッセージを完成します。</span><span class="sxs-lookup"><span data-stu-id="fe78c-139">The assembler will then add the delivery header and preamble to construct the final RNIF message.</span></span>  
  
    3.  <span data-ttu-id="fe78c-140">設定した場合**永続的な機密性の必要性が**に**None**アセンブラーは service content と添付ファイルを (なしに、service header、delivery header、および preamble が追加されます暗号化) をクリックし、最後の RNIF メッセージを構築するためにします。</span><span class="sxs-lookup"><span data-stu-id="fe78c-140">If you have set **Is Persistent Confidentiality Required** to **None**, the assembler will add the service header, delivery header, and preamble to the service content and the attachments (without encryption) to construct the final RNIF message.</span></span>  
  
4.  <span data-ttu-id="fe78c-141">RNIF 1.1 では、アセンブラーは暗号化せずに RNIF メッセージを完成します。</span><span class="sxs-lookup"><span data-stu-id="fe78c-141">For RNIF 1.1, the assembler will construct the final RNIF message without encryption.</span></span>  
  
5.  <span data-ttu-id="fe78c-142">次の場合、エンコーダーはメッセージに署名します。</span><span class="sxs-lookup"><span data-stu-id="fe78c-142">The encoder will sign the message in the following case:</span></span>  
  
    1.  <span data-ttu-id="fe78c-143">メッセージがシグナル メッセージでは、および**否認不可のために必要な**プロパティ、プロセス構成設定が`True`です。</span><span class="sxs-lookup"><span data-stu-id="fe78c-143">The message is a signal message, and the **Non-Repudiation Required** property (in the process configuration settings) is `True`.</span></span>  
  
    2.  <span data-ttu-id="fe78c-144">メッセージがアクション メッセージでは、および**発信元とコンテンツの否認**プロパティ、プロセス構成設定が`True`です。</span><span class="sxs-lookup"><span data-stu-id="fe78c-144">The message is an action message, and the **Non-Repudiation of Origin and Content** property (in the process configuration settings) is `True`.</span></span>  
  
6.  <span data-ttu-id="fe78c-145">RNIF 2.01 では、エンコーダーは MIME メッセージの最初の本文部分のダイジェストを計算して、保持します。</span><span class="sxs-lookup"><span data-stu-id="fe78c-145">For RNIF 2.01, the encoder will calculate the digest on the first body part of the MIME message, and persist the digest.</span></span> <span data-ttu-id="fe78c-146">エンコーダーは取引先アグリーメント (SHA-1 または MD5) の `Digest` メソッド プロパティのメソッド セットを使用してダイジェストを計算します。</span><span class="sxs-lookup"><span data-stu-id="fe78c-146">It will calculate the digest using the method set in the `Digest` method property in the trading partner agreement (SHA-1 or MD5).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe78c-147">参照</span><span class="sxs-lookup"><span data-stu-id="fe78c-147">See Also</span></span>  
 [<span data-ttu-id="fe78c-148">BTARN でのメッセージ処理</span><span class="sxs-lookup"><span data-stu-id="fe78c-148">Message Processing in BTARN</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/message-processing-in-btarn.md)