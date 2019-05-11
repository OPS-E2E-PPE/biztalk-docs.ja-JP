---
title: BTARN 受信パイプライン |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BTARN, receive pipelines
- RNMimeDecoder component
- ReceiveMessageNonRepudiate component
- RNDAsm component
- receive pipelines, message flow
- RNPartyRes component
- receive pipelines, BTARN
- MessageUpdater component
- messages, message flow
ms.assetid: 811f2a6a-ddd2-49cc-a00b-4c9d0110a0d1
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 53a9b9dd410a6a136b37ef506c9bc975f563a11a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65284922"
---
# <a name="btarn-receive-pipeline"></a><span data-ttu-id="8c399-102">BTARN 受信パイプライン</span><span class="sxs-lookup"><span data-stu-id="8c399-102">BTARN Receive Pipeline</span></span>
<span data-ttu-id="8c399-103">Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] RNIFReceive パイプライン (RNIFReceive.btp) と RosettaNet Implementation Framework (RNIF) メッセージの受信を実行します。</span><span class="sxs-lookup"><span data-stu-id="8c399-103">Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] performs RosettaNet Implementation Framework (RNIF) message reception with the RNIFReceive pipeline (RNIFReceive.btp).</span></span> <span data-ttu-id="8c399-104">受信パイプラインには、次のコンポーネントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="8c399-104">The receive pipeline includes the following components:</span></span>  
  
-   <span data-ttu-id="8c399-105">ReceiveMessageNonRepudiate</span><span class="sxs-lookup"><span data-stu-id="8c399-105">ReceiveMessageNonRepudiate</span></span>  
  
-   <span data-ttu-id="8c399-106">RNMimeDecoder (MIME プリプロセッサ/デコーダー)</span><span class="sxs-lookup"><span data-stu-id="8c399-106">RNMimeDecoder (MIME Preprocessor/Decoder)</span></span>  
  
-   <span data-ttu-id="8c399-107">RNDAsm (XML 逆アセンブラ)</span><span class="sxs-lookup"><span data-stu-id="8c399-107">RNDAsm (XML Disassembler)</span></span>  
  
-   <span data-ttu-id="8c399-108">RNPartyRes (Party Resolution コンポーネント)</span><span class="sxs-lookup"><span data-stu-id="8c399-108">RNPartyRes (Party Resolution component)</span></span>  
  
-   <span data-ttu-id="8c399-109">MessageUpdater</span><span class="sxs-lookup"><span data-stu-id="8c399-109">MessageUpdater</span></span>  
  
## <a name="receivemessagenonrepudiate"></a><span data-ttu-id="8c399-110">ReceiveMessageNonRepudiate</span><span class="sxs-lookup"><span data-stu-id="8c399-110">ReceiveMessageNonRepudiate</span></span>  
 <span data-ttu-id="8c399-111">このコンポーネントは、受信したメッセージを MessageStorageIn テーブルに格納します。</span><span class="sxs-lookup"><span data-stu-id="8c399-111">This component stores the received message in the MessageStorageIn table.</span></span> <span data-ttu-id="8c399-112">このコンポーネントは、RNIF 規格で必要な否認不可処理を実行します。</span><span class="sxs-lookup"><span data-stu-id="8c399-112">This component performs the non-repudiation processing required by the RNIF standards.</span></span>  
  
## <a name="rnmimedecoder"></a><span data-ttu-id="8c399-113">RNMimeDecoder</span><span class="sxs-lookup"><span data-stu-id="8c399-113">RNMimeDecoder</span></span>  
 <span data-ttu-id="8c399-114">このコンポーネントは、上のネイティブ BizTalk Server MIME プリプロセッサ/デコーダーに基づいています。</span><span class="sxs-lookup"><span data-stu-id="8c399-114">This component is based on the native BizTalk Server MIME Preprocessor/Decoder.</span></span> <span data-ttu-id="8c399-115">RNMimeDecoder は、RNIF 処理のため、次の機能を追加します。</span><span class="sxs-lookup"><span data-stu-id="8c399-115">RNMimeDecoder adds the following functionality for RNIF processing:</span></span>  
  
- <span data-ttu-id="8c399-116">RNIF 2.01 では、存在する場合に、service content と添付ファイルを解読します。</span><span class="sxs-lookup"><span data-stu-id="8c399-116">For RNIF 2.01, decrypts the service content and attachments, if they are present.</span></span>  
  
- <span data-ttu-id="8c399-117">RNIF 1.1 では、8 バイト ヘッダーとペイロードの末尾にデタッチされた署名ヘッダーを処理します。</span><span class="sxs-lookup"><span data-stu-id="8c399-117">For RNIF 1.1, handles the 8-byte header and the detached signature header at the end of the payload.</span></span>  
  
  <span data-ttu-id="8c399-118">詳細については、ネイティブ[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]プリプロセッサ/デコーダの場合、BizTalk Server ヘルプの「MIME/SMIME デコーダー パイプライン コンポーネント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8c399-118">For more information about the native [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] preprocessor/decoder, see "MIME/SMIME Decoder Pipeline Component" in BizTalk Server Help.</span></span>  
  
## <a name="rndasm"></a><span data-ttu-id="8c399-119">RNDAsm</span><span class="sxs-lookup"><span data-stu-id="8c399-119">RNDAsm</span></span>  
 <span data-ttu-id="8c399-120">このコンポーネントは、ネイティブの BizTalk Server XML 逆アセンブラーに基づいています。</span><span class="sxs-lookup"><span data-stu-id="8c399-120">This component is based on the native BizTalk Server XML Disassembler.</span></span> <span data-ttu-id="8c399-121">RNDAsm は、RNIF 処理のため、次の機能を追加します。</span><span class="sxs-lookup"><span data-stu-id="8c399-121">RNDAsm adds the following functionality for RNIF processing:</span></span>  
  
- <span data-ttu-id="8c399-122">受信ドキュメントに DOCTYPE ヘッダーがある場合は、このコンポーネントはそこから、名前空間を生成し、受信ドキュメント内のすべてのノードをその名前空間に移動します。</span><span class="sxs-lookup"><span data-stu-id="8c399-122">If an incoming document has a DOCTYPE header, this component generates a namespace from it and moves all nodes in the incoming document to that namespace.</span></span>  
  
- <span data-ttu-id="8c399-123">受信メッセージが、重複しているし、メッセージが重複している場合は、エラー メッセージを生成するかどうかを確認するメッセージの関連付けを実行します。</span><span class="sxs-lookup"><span data-stu-id="8c399-123">Performs message correlation to determine whether an incoming message is a duplicate, and generates an error message if the message is a duplicate.</span></span>  
  
- <span data-ttu-id="8c399-124">メッセージの追加部分として添付ファイルを格納します。</span><span class="sxs-lookup"><span data-stu-id="8c399-124">Stores attachments as additional parts of the message.</span></span>  
  
- <span data-ttu-id="8c399-125">メッセージのプロパティを昇格させます。</span><span class="sxs-lookup"><span data-stu-id="8c399-125">Promotes message properties.</span></span>  
  
  <span data-ttu-id="8c399-126">詳細については、ネイティブ[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]逆アセンブラー、BizTalk Server ヘルプの「XML 逆アセンブラー パイプライン コンポーネント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8c399-126">For more information about the native [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Disassembler, see "XML Disassembler Pipeline Component" in BizTalk Server Help.</span></span>  
  
## <a name="rnpartyres"></a><span data-ttu-id="8c399-127">RNPartyRes</span><span class="sxs-lookup"><span data-stu-id="8c399-127">RNPartyRes</span></span>  
 <span data-ttu-id="8c399-128">このコンポーネントは、ネイティブの BizTalk Server パーティの解決コンポーネントに基づいています。</span><span class="sxs-lookup"><span data-stu-id="8c399-128">This component is based on the native BizTalk Server Party Resolution component.</span></span> <span data-ttu-id="8c399-129">RNPartyRes は、RNIF 処理のため、次の機能を追加します。</span><span class="sxs-lookup"><span data-stu-id="8c399-129">RNPartyRes adds the following functionality for RNIF processing:</span></span>  
  
- <span data-ttu-id="8c399-130">受信メッセージが BizTalk パーティに署名されている場合は、送信者の証明書をマップします。</span><span class="sxs-lookup"><span data-stu-id="8c399-130">Maps the sender certificate if the incoming message is signed to a BizTalk party.</span></span> <span data-ttu-id="8c399-131">受信メッセージが署名されていない、取引先アグリーメントが許可されている場合は、このコンポーネントを取得します、送信側パーティは Delivery header から RNIF 2.01 Service header について RNIF 1.1。</span><span class="sxs-lookup"><span data-stu-id="8c399-131">If the incoming message is not signed, and the trading partner agreement allows for it, this component retrieves the sender party from the Delivery header for RNIF 2.01 or the Service header for RNIF 1.1.</span></span>  
  
- <span data-ttu-id="8c399-132">送信者が存在して、送信者がホーム組織と取引先パートナー契約を持つことを検証します。</span><span class="sxs-lookup"><span data-stu-id="8c399-132">Validates that the sender exists and that the sender has a trading partner agreement with the home organization.</span></span>  
  
  <span data-ttu-id="8c399-133">詳細については、ネイティブ[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]party resolution コンポーネントを BizTalk Server ヘルプの「パーティの解決パイプライン コンポーネント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8c399-133">For more information about the native [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] party resolution component, see "Party Resolution Pipeline Component" in BizTalk Server Help.</span></span>  
  
## <a name="messageupdater"></a><span data-ttu-id="8c399-134">MessageUpdater</span><span class="sxs-lookup"><span data-stu-id="8c399-134">MessageUpdater</span></span>  
 <span data-ttu-id="8c399-135">このコンポーネントは、RNIF 処理のため、次の機能を追加します。</span><span class="sxs-lookup"><span data-stu-id="8c399-135">This component adds the following functionality for RNIF processing:</span></span>  
  
-   <span data-ttu-id="8c399-136">PIP コード、PIP バージョン、送信元パーティ、送信先パーティ、および Message Tracking ID、ReceiveMessageNonRepudiate コンポーネントによって保存されたワイヤ メッセージの詳細を含む MessageStorageIn テーブルを更新します。</span><span class="sxs-lookup"><span data-stu-id="8c399-136">Updates the MessageStorageIn table with details about the PIP Code, PIP Version, Source Party, Destination Party, and Message Tracking ID of the wire message that was stored by the ReceiveMessageNonRepudiate component.</span></span>  
  
-   <span data-ttu-id="8c399-137">PIP に否認不可が必要としない場合は、削除、設定のレコードをマーク`ToBePurged = True`します。</span><span class="sxs-lookup"><span data-stu-id="8c399-137">If the PIP does not require non-repudiation, marks the record for deletion, setting `ToBePurged = True`.</span></span>  
  
## <a name="message-flow"></a><span data-ttu-id="8c399-138">メッセージ フロー</span><span class="sxs-lookup"><span data-stu-id="8c399-138">Message Flow</span></span>  
 <span data-ttu-id="8c399-139">メッセージ フローは、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]受信パイプラインは、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="8c399-139">The message flow through the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] receive pipeline is as follows:</span></span>  
  
1. <span data-ttu-id="8c399-140">HTTP アダプターでは、RNIF 1.1 オブジェクトまたは HTTP POST を介して RNIF 2.01 ビジネス メッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="8c399-140">The HTTP adapter receives an RNIF 1.1 object or an RNIF 2.01 business message through HTTP POST.</span></span>  
  
2. <span data-ttu-id="8c399-141">アダプターが正常にメッセージを受け取る場合、アダプターは RosettaNet オブジェクトまたはビジネス メッセージを抽出し、受信パイプラインにルーティングします。</span><span class="sxs-lookup"><span data-stu-id="8c399-141">If the adapter successfully receives the message, the adapter extracts the RosettaNet object or business message, and routes it to the receive pipeline.</span></span>  
  
3. <span data-ttu-id="8c399-142">オブジェクトまたはビジネス メッセージが署名されている場合、MIME プリプロセッサ/デコーダーは、署名を削除します。</span><span class="sxs-lookup"><span data-stu-id="8c399-142">If the object or business message is signed, the MIME Preprocessor/Decoder removes the signature.</span></span>  
  
4. <span data-ttu-id="8c399-143">署名が有効な場合、逆アセンブラーは preamble を読み取ります。</span><span class="sxs-lookup"><span data-stu-id="8c399-143">If the signature is valid, the disassembler reads the preamble.</span></span>  
  
5. <span data-ttu-id="8c399-144">メッセージがアクション メッセージで否認不可が必要な場合 (、**発信元とコンテンツの否認**プロセス構成設定の設定が`True`)、デコーダーを計算してダイジェストを維持します。</span><span class="sxs-lookup"><span data-stu-id="8c399-144">If the message is an action message, and non-repudiation is required (the **Non-Repudiation of Origin and Content** setting in the process configuration settings is `True`), the Decoder calculates and persists the digest.</span></span>  
  
6. <span data-ttu-id="8c399-145">逆アセンブラーは、(メッセージ (MSG) ガイドラインとグローバル変数の preamble スキーマ) を持つ preamble を検証します。</span><span class="sxs-lookup"><span data-stu-id="8c399-145">The disassembler validates the preamble (with message (MSG) guidelines and the preamble schema in the global variables).</span></span>  
  
7. <span data-ttu-id="8c399-146">RNIF 2.01 では、逆アセンブラーは delivery header を読み取りし、ヘッダー、MSG ガイドラインと delivery header スキーマを使用して、グローバル変数を検証します。</span><span class="sxs-lookup"><span data-stu-id="8c399-146">For RNIF 2.01, the disassembler reads the delivery header, and validates the header using the MSG guidelines and the delivery header schema in the global variables.</span></span>  
  
8. <span data-ttu-id="8c399-147">RNIF 2.01 では、逆アセンブラーは delivery header からパートナー情報を抽出し、パートナーに属していることを確認する署名します。</span><span class="sxs-lookup"><span data-stu-id="8c399-147">For RNIF 2.01, the disassembler extracts the partner information from the delivery header, and examines the signature to verify that it belongs to the partner.</span></span>  
  
9. <span data-ttu-id="8c399-148">RNIF 2.01 では、ペイロードが暗号化されている場合、デコーダーによってペイロード コンテナーが解読します。</span><span class="sxs-lookup"><span data-stu-id="8c399-148">For RNIF 2.01, if the payload is encrypted, the decoder decrypts the payload container.</span></span>  
  
10. <span data-ttu-id="8c399-149">逆アセンブラーでは、サービスのヘッダーを読み取りおよびグローバル変数で、MSG ガイドラインと、サービス ヘッダー スキーマを使用して、ヘッダーを検証します。</span><span class="sxs-lookup"><span data-stu-id="8c399-149">The disassembler reads the service header, and validates the header using the MSG guidelines and the service header schema in the global variables.</span></span>  
  
11. <span data-ttu-id="8c399-150">RNIF 1.1 での逆アセンブラーは service header からパートナー情報を抽出し、パートナーに属していることを確認する署名します。</span><span class="sxs-lookup"><span data-stu-id="8c399-150">For RNIF 1.1, the disassembler extracts the partner information from the service header, and examines the signature to verify that it belongs to the partner.</span></span>  
  
12. <span data-ttu-id="8c399-151">逆アセンブラーは、PIP のパートナーが承認されているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="8c399-151">The disassembler checks whether the partner is authorized for the PIP.</span></span> <span data-ttu-id="8c399-152">いない場合は、逆アセンブラーは HTTP 403 ステータス メッセージでは、HTTP POST を返信する場合は、必要に応じて、エラーを送信します。</span><span class="sxs-lookup"><span data-stu-id="8c399-152">If not, the disassembler will reply an HTTP POST with an HTTP 403 status message, if necessary, and post an error.</span></span>  
  
13. <span data-ttu-id="8c399-153">メッセージが署名されたアクション メッセージの場合と**発信元とコンテンツの否認**に設定されている`True`、ReceiveMessageNonRepudiate コンポーネントには、MessageStorageIn テーブルに元のメッセージが引き続き発生します。</span><span class="sxs-lookup"><span data-stu-id="8c399-153">If the message is a signed action message and **Non-Repudiation of Origin and Content** is set to `True`, the ReceiveMessageNonRepudiate component persists the original message in the MessageStorageIn table.</span></span>  
  
14. <span data-ttu-id="8c399-154">メッセージが署名されたシグナル メッセージの場合と**否認不可のために必要な**に設定されている`True`、ReceiveMessageNonRepudiate コンポーネントはシグナル メッセージを MessageStorageIn テーブルを永続化します。</span><span class="sxs-lookup"><span data-stu-id="8c399-154">If the message is a signed signal message and **Non-Repudiation Required** is set to `True`, the ReceiveMessageNonRepudiate component persists the signal message in the MessageStorageIn table.</span></span>  
  
15. <span data-ttu-id="8c399-155">メッセージは、否認不可用 MessageStorageIn テーブルで永続化された、MessageUpdater はメッセージのプロセス構成のプロパティを持つ MessageStorageIn テーブルを更新します。</span><span class="sxs-lookup"><span data-stu-id="8c399-155">If the message was persisted in the MessageStorageIn table for non-repudiation, the MessageUpdater updates the MessageStorageIn table with properties of the process configuration of the message.</span></span>  
  
16. <span data-ttu-id="8c399-156">メッセージのアクションが以前に処理されたメッセージの重複アクション メッセージでは場合[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]はエラーを送信します。</span><span class="sxs-lookup"><span data-stu-id="8c399-156">If the message is an action message that is a duplicate of a previously processed action message, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] will post an error.</span></span>  
  
17. <span data-ttu-id="8c399-157">RNIF 2.01 では、デコーダーは、アクション メッセージが暗号化され、HTTP 同期と PIP 同期の要件の間で一致がある場合に、ペイロードを解読します。</span><span class="sxs-lookup"><span data-stu-id="8c399-157">For RNIF 2.01, the decoder will decrypt the payload if the action message is encrypted and there is a match between the HTTP synchronicity and PIP synchronicity requirements.</span></span>  
  
18. <span data-ttu-id="8c399-158">逆アセンブラーは、サービスのコンテンツを読み取って、MSG ガイドラインとスキーマを使用して検証します。</span><span class="sxs-lookup"><span data-stu-id="8c399-158">The disassembler reads the service content, and validates it using the MSG guidelines and the schema.</span></span>  
  
19. <span data-ttu-id="8c399-159">RNIF 2.01 では、逆アセンブラーは、マニフェストが有効で、コンテンツ ID が存在することを確認します。</span><span class="sxs-lookup"><span data-stu-id="8c399-159">For RNIF 2.01, the disassembler verifies that the manifest is valid and the content ID is present.</span></span>  
  
20. <span data-ttu-id="8c399-160">RNIF 2.01 では、逆アセンブラーはすべての添付ファイルを読み取ります。</span><span class="sxs-lookup"><span data-stu-id="8c399-160">For RNIF 2.01, the disassembler will read any attachments.</span></span>  
  
21. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] <span data-ttu-id="8c399-161">RosettaNet ヘッダー、service content、およびパブリック プロセスへの添付ファイルをルーティングします。</span><span class="sxs-lookup"><span data-stu-id="8c399-161">routes the RosettaNet headers, service content, and attachments to the public process.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c399-162">参照</span><span class="sxs-lookup"><span data-stu-id="8c399-162">See Also</span></span>  
 [<span data-ttu-id="8c399-163">BTARN でのメッセージ処理</span><span class="sxs-lookup"><span data-stu-id="8c399-163">Message Processing in BTARN</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/message-processing-in-btarn.md)