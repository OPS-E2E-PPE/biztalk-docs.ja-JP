---
title: BTARN 受信パイプライン |Microsoft ドキュメント
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
ms.openlocfilehash: db4bc69348cfb99b5e7cebb07c65e05a0513cd0e
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
ms.locfileid: "26005627"
---
# <a name="btarn-receive-pipeline"></a><span data-ttu-id="8a39c-102">BTARN 受信パイプライン</span><span class="sxs-lookup"><span data-stu-id="8a39c-102">BTARN Receive Pipeline</span></span>
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]<span data-ttu-id="8a39c-103">[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] RosettaNet Implementation Framework (RNIF) メッセージの受信、RNIFReceive パイプライン (RNIFReceive.btp) を実行します。</span><span class="sxs-lookup"><span data-stu-id="8a39c-103"> [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] performs RosettaNet Implementation Framework (RNIF) message reception with the RNIFReceive pipeline (RNIFReceive.btp).</span></span> <span data-ttu-id="8a39c-104">受信パイプラインには、以下のコンポーネントが含まれます。</span><span class="sxs-lookup"><span data-stu-id="8a39c-104">The receive pipeline includes the following components:</span></span>  
  
-   <span data-ttu-id="8a39c-105">ReceiveMessageNonRepudiate</span><span class="sxs-lookup"><span data-stu-id="8a39c-105">ReceiveMessageNonRepudiate</span></span>  
  
-   <span data-ttu-id="8a39c-106">RNMimeDecoder (MIME プリプロセッサ/デコーダー)</span><span class="sxs-lookup"><span data-stu-id="8a39c-106">RNMimeDecoder (MIME Preprocessor/Decoder)</span></span>  
  
-   <span data-ttu-id="8a39c-107">RNDAsm (XML 逆アセンブラ)</span><span class="sxs-lookup"><span data-stu-id="8a39c-107">RNDAsm (XML Disassembler)</span></span>  
  
-   <span data-ttu-id="8a39c-108">RNPartyRes (Party Resolution コンポーネント)</span><span class="sxs-lookup"><span data-stu-id="8a39c-108">RNPartyRes (Party Resolution component)</span></span>  
  
-   <span data-ttu-id="8a39c-109">MessageUpdater</span><span class="sxs-lookup"><span data-stu-id="8a39c-109">MessageUpdater</span></span>  
  
## <a name="receivemessagenonrepudiate"></a><span data-ttu-id="8a39c-110">ReceiveMessageNonRepudiate</span><span class="sxs-lookup"><span data-stu-id="8a39c-110">ReceiveMessageNonRepudiate</span></span>  
 <span data-ttu-id="8a39c-111">このコンポーネントは、受信メッセージを MessageStorageIn テーブルに保存します。</span><span class="sxs-lookup"><span data-stu-id="8a39c-111">This component stores the received message in the MessageStorageIn table.</span></span> <span data-ttu-id="8a39c-112">このコンポーネントは、RNIF 規格に必要な否認不可処理を実行します。</span><span class="sxs-lookup"><span data-stu-id="8a39c-112">This component performs the non-repudiation processing required by the RNIF standards.</span></span>  
  
## <a name="rnmimedecoder"></a><span data-ttu-id="8a39c-113">RNMimeDecoder</span><span class="sxs-lookup"><span data-stu-id="8a39c-113">RNMimeDecoder</span></span>  
 <span data-ttu-id="8a39c-114">このコンポーネントは、上のネイティブ BizTalk Server MIME プリプロセッサ/デコーダーに基づいています。</span><span class="sxs-lookup"><span data-stu-id="8a39c-114">This component is based on the native BizTalk Server MIME Preprocessor/Decoder.</span></span> <span data-ttu-id="8a39c-115">RNMimeDecoder は、RNIF 処理のための以下の機能を備えています。</span><span class="sxs-lookup"><span data-stu-id="8a39c-115">RNMimeDecoder adds the following functionality for RNIF processing:</span></span>  
  
-   <span data-ttu-id="8a39c-116">RNIF 2.01 の場合、Service Content と添付ファイル (存在する場合) を暗号化解除します。</span><span class="sxs-lookup"><span data-stu-id="8a39c-116">For RNIF 2.01, decrypts the service content and attachments, if they are present.</span></span>  
  
-   <span data-ttu-id="8a39c-117">RNIF 1.1 の場合、ペイロードの末尾にある 8 バイト ヘッダーとデタッチされた署名ヘッダーを処理します。</span><span class="sxs-lookup"><span data-stu-id="8a39c-117">For RNIF 1.1, handles the 8-byte header and the detached signature header at the end of the payload.</span></span>  
  
 <span data-ttu-id="8a39c-118">詳細については、ネイティブ[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]プリプロセッサ/デコーダー、BizTalk Server ヘルプの「MIME/SMIME デコーダー パイプライン コンポーネント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8a39c-118">For more information about the native [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] preprocessor/decoder, see "MIME/SMIME Decoder Pipeline Component" in BizTalk Server Help.</span></span>  
  
## <a name="rndasm"></a><span data-ttu-id="8a39c-119">RNDAsm</span><span class="sxs-lookup"><span data-stu-id="8a39c-119">RNDAsm</span></span>  
 <span data-ttu-id="8a39c-120">このコンポーネントは、ネイティブの BizTalk Server XML 逆アセンブラーに基づいています。</span><span class="sxs-lookup"><span data-stu-id="8a39c-120">This component is based on the native BizTalk Server XML Disassembler.</span></span> <span data-ttu-id="8a39c-121">RNDAsm は、RNIF 処理のための以下の機能を備えています。</span><span class="sxs-lookup"><span data-stu-id="8a39c-121">RNDAsm adds the following functionality for RNIF processing:</span></span>  
  
-   <span data-ttu-id="8a39c-122">受信ドキュメントに DOCTYPE ヘッダーがある場合、このコンポーネントはヘッダーから名前空間を生成し、受信ドキュメントのすべてのノードを名前空間に移動します。</span><span class="sxs-lookup"><span data-stu-id="8a39c-122">If an incoming document has a DOCTYPE header, this component generates a namespace from it and moves all nodes in the incoming document to that namespace.</span></span>  
  
-   <span data-ttu-id="8a39c-123">メッセージの相関を確認して、着信メッセージが重複しているかどうかを判断し、メッセージが重複している場合は、エラー メッセージを生成します。</span><span class="sxs-lookup"><span data-stu-id="8a39c-123">Performs message correlation to determine whether an incoming message is a duplicate, and generates an error message if the message is a duplicate.</span></span>  
  
-   <span data-ttu-id="8a39c-124">添付ファイルをメッセージの追加部分として保存します。</span><span class="sxs-lookup"><span data-stu-id="8a39c-124">Stores attachments as additional parts of the message.</span></span>  
  
-   <span data-ttu-id="8a39c-125">メッセージ プロパティを昇格します。</span><span class="sxs-lookup"><span data-stu-id="8a39c-125">Promotes message properties.</span></span>  
  
 <span data-ttu-id="8a39c-126">詳細については、ネイティブ[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]逆アセンブラー、BizTalk Server ヘルプの「XML 逆アセンブラー パイプライン コンポーネント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8a39c-126">For more information about the native [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Disassembler, see "XML Disassembler Pipeline Component" in BizTalk Server Help.</span></span>  
  
## <a name="rnpartyres"></a><span data-ttu-id="8a39c-127">RNPartyRes</span><span class="sxs-lookup"><span data-stu-id="8a39c-127">RNPartyRes</span></span>  
 <span data-ttu-id="8a39c-128">このコンポーネントは、ネイティブの BizTalk Server パーティの解決コンポーネントに基づいています。</span><span class="sxs-lookup"><span data-stu-id="8a39c-128">This component is based on the native BizTalk Server Party Resolution component.</span></span> <span data-ttu-id="8a39c-129">RNPartyRes は、RNIF 処理のための以下の機能を備えています。</span><span class="sxs-lookup"><span data-stu-id="8a39c-129">RNPartyRes adds the following functionality for RNIF processing:</span></span>  
  
-   <span data-ttu-id="8a39c-130">着信メッセージが BizTalk パーティに対して署名されている場合は、送信者の証明書をマップします。</span><span class="sxs-lookup"><span data-stu-id="8a39c-130">Maps the sender certificate if the incoming message is signed to a BizTalk party.</span></span> <span data-ttu-id="8a39c-131">着信メッセージに署名がなく、取引先アグリーメントでそれが許可されている場合、このコンポーネントは RNIF 2.01 については Delivery ヘッダーから、RNIF 1.1 については Service ヘッダーから送信者のパーティを取得します。</span><span class="sxs-lookup"><span data-stu-id="8a39c-131">If the incoming message is not signed, and the trading partner agreement allows for it, this component retrieves the sender party from the Delivery header for RNIF 2.01 or the Service header for RNIF 1.1.</span></span>  
  
-   <span data-ttu-id="8a39c-132">送信者が存在し、送信者がホーム組織との取引先アグリーメントを持っているかどうかを検証します。</span><span class="sxs-lookup"><span data-stu-id="8a39c-132">Validates that the sender exists and that the sender has a trading partner agreement with the home organization.</span></span>  
  
 <span data-ttu-id="8a39c-133">詳細については、ネイティブ[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]party resolution コンポーネント、BizTalk Server ヘルプの「パーティの解決パイプライン コンポーネント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8a39c-133">For more information about the native [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] party resolution component, see "Party Resolution Pipeline Component" in BizTalk Server Help.</span></span>  
  
## <a name="messageupdater"></a><span data-ttu-id="8a39c-134">MessageUpdater</span><span class="sxs-lookup"><span data-stu-id="8a39c-134">MessageUpdater</span></span>  
 <span data-ttu-id="8a39c-135">このコンポーネントは、RNIF 処理のための以下の機能を備えています。</span><span class="sxs-lookup"><span data-stu-id="8a39c-135">This component adds the following functionality for RNIF processing:</span></span>  
  
-   <span data-ttu-id="8a39c-136">PIP コード、PIP バージョン、送信元パーティ、送信先パーティ、ReceiveMessageNonRepudiate コンポーネントによって保存されたワイヤ メッセージの Message Tracking ID の詳細情報を使用して MessageStorageIn テーブルを更新します。</span><span class="sxs-lookup"><span data-stu-id="8a39c-136">Updates the MessageStorageIn table with details about the PIP Code, PIP Version, Source Party, Destination Party, and Message Tracking ID of the wire message that was stored by the ReceiveMessageNonRepudiate component.</span></span>  
  
-   <span data-ttu-id="8a39c-137">PIP が否認不可を必要としない場合、`ToBePurged = True` を設定してレコードに削除のマークを付けます。</span><span class="sxs-lookup"><span data-stu-id="8a39c-137">If the PIP does not require non-repudiation, marks the record for deletion, setting `ToBePurged = True`.</span></span>  
  
## <a name="message-flow"></a><span data-ttu-id="8a39c-138">メッセージ フロー</span><span class="sxs-lookup"><span data-stu-id="8a39c-138">Message Flow</span></span>  
 <span data-ttu-id="8a39c-139">[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 受信パイプラインを経由するメッセージ フローは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="8a39c-139">The message flow through the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] receive pipeline is as follows:</span></span>  
  
1.  <span data-ttu-id="8a39c-140">HTTP アダプターは HTTP POST を使用して RNIF 1.1 オブジェクトまたは RNIF 2.01 ビジネス メッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="8a39c-140">The HTTP adapter receives an RNIF 1.1 object or an RNIF 2.01 business message through HTTP POST.</span></span>  
  
2.  <span data-ttu-id="8a39c-141">メッセージを正常に受信すると、アダプターは RosettaNet オブジェクトまたはビジネス メッセージを抽出し、受信パイプラインにルーティングします。</span><span class="sxs-lookup"><span data-stu-id="8a39c-141">If the adapter successfully receives the message, the adapter extracts the RosettaNet object or business message, and routes it to the receive pipeline.</span></span>  
  
3.  <span data-ttu-id="8a39c-142">オブジェクトまたはビジネス メッセージに署名がある場合、MIME プリプロセッサ/デコーダーが署名を削除します。</span><span class="sxs-lookup"><span data-stu-id="8a39c-142">If the object or business message is signed, the MIME Preprocessor/Decoder removes the signature.</span></span>  
  
4.  <span data-ttu-id="8a39c-143">署名が有効な場合、逆アセンブラーは Preamble を読み取ります。</span><span class="sxs-lookup"><span data-stu-id="8a39c-143">If the signature is valid, the disassembler reads the preamble.</span></span>  
  
5.  <span data-ttu-id="8a39c-144">メッセージがアクション メッセージで否認不可が必要な場合 (、**発信元とコンテンツの否認**プロセス構成設定の設定が`True`)、デコーダーを計算し、ダイジェストが引き続き発生します。</span><span class="sxs-lookup"><span data-stu-id="8a39c-144">If the message is an action message, and non-repudiation is required (the **Non-Repudiation of Origin and Content** setting in the process configuration settings is `True`), the Decoder calculates and persists the digest.</span></span>  
  
6.  <span data-ttu-id="8a39c-145">逆アセンブラーは、メッセージ (MSG) ガイドラインとグローバル変数の Preamble スキーマを使用して Preamble を検証します。</span><span class="sxs-lookup"><span data-stu-id="8a39c-145">The disassembler validates the preamble (with message (MSG) guidelines and the preamble schema in the global variables).</span></span>  
  
7.  <span data-ttu-id="8a39c-146">RNIF 2.01 では、逆アセンブラーは Delivery Header を読み取り、メッセージ ガイドラインとグローバル変数の Delivery Header スキーマを使用してヘッダーを検証します。</span><span class="sxs-lookup"><span data-stu-id="8a39c-146">For RNIF 2.01, the disassembler reads the delivery header, and validates the header using the MSG guidelines and the delivery header schema in the global variables.</span></span>  
  
8.  <span data-ttu-id="8a39c-147">RNIF 2.01 では、逆アセンブラーは Delivery Header からパートナー情報を抽出し、署名がパートナーに属しているかどうかを検証します。</span><span class="sxs-lookup"><span data-stu-id="8a39c-147">For RNIF 2.01, the disassembler extracts the partner information from the delivery header, and examines the signature to verify that it belongs to the partner.</span></span>  
  
9. <span data-ttu-id="8a39c-148">RNIF 2.01 でペイロードが暗号化されている場合、デコーダーによってペイロード コンテナーの暗号化が解除されます。</span><span class="sxs-lookup"><span data-stu-id="8a39c-148">For RNIF 2.01, if the payload is encrypted, the decoder decrypts the payload container.</span></span>  
  
10. <span data-ttu-id="8a39c-149">逆アセンブラーは Service Header を読み取り、MSG ガイドラインとグローバル変数の Service Header スキーマを使用してヘッダーを検証します。</span><span class="sxs-lookup"><span data-stu-id="8a39c-149">The disassembler reads the service header, and validates the header using the MSG guidelines and the service header schema in the global variables.</span></span>  
  
11. <span data-ttu-id="8a39c-150">RNIF 1.1 では、逆アセンブラーは Service Header からパートナー情報を抽出し、署名がパートナーに属しているかどうかを検証します。</span><span class="sxs-lookup"><span data-stu-id="8a39c-150">For RNIF 1.1, the disassembler extracts the partner information from the service header, and examines the signature to verify that it belongs to the partner.</span></span>  
  
12. <span data-ttu-id="8a39c-151">逆アセンブラーは、パートナーが PIP に承認されているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="8a39c-151">The disassembler checks whether the partner is authorized for the PIP.</span></span> <span data-ttu-id="8a39c-152">承認されていない場合、逆アセンブラーは HTTP POST に HTTP 403 ステータス メッセージを返し、必要に応じてエラーを送信します。</span><span class="sxs-lookup"><span data-stu-id="8a39c-152">If not, the disassembler will reply an HTTP POST with an HTTP 403 status message, if necessary, and post an error.</span></span>  
  
13. <span data-ttu-id="8a39c-153">メッセージが署名されたアクション メッセージの場合と**発信元とコンテンツの否認**に設定されている`True`、ReceiveMessageNonRepudiate コンポーネント MessageStorageIn テーブルに元のメッセージが引き続き発生します。</span><span class="sxs-lookup"><span data-stu-id="8a39c-153">If the message is a signed action message and **Non-Repudiation of Origin and Content** is set to `True`, the ReceiveMessageNonRepudiate component persists the original message in the MessageStorageIn table.</span></span>  
  
14. <span data-ttu-id="8a39c-154">メッセージが署名されたシグナル メッセージの場合と**否認不可のために必要な**に設定されている`True`、ReceiveMessageNonRepudiate コンポーネント MessageStorageIn テーブルにシグナル メッセージが引き続き発生します。</span><span class="sxs-lookup"><span data-stu-id="8a39c-154">If the message is a signed signal message and **Non-Repudiation Required** is set to `True`, the ReceiveMessageNonRepudiate component persists the signal message in the MessageStorageIn table.</span></span>  
  
15. <span data-ttu-id="8a39c-155">メッセージが否認不可の MessageStorageIn テーブルに保存されている場合、MessageUpdater はメッセージのプロセス構成のプロパティを使用して MessageStorageIn テーブルを更新します。</span><span class="sxs-lookup"><span data-stu-id="8a39c-155">If the message was persisted in the MessageStorageIn table for non-repudiation, the MessageUpdater updates the MessageStorageIn table with properties of the process configuration of the message.</span></span>  
  
16. <span data-ttu-id="8a39c-156">メッセージが以前に処理されたアクション メッセージの重複アクション メッセージの場合、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] はエラーを送信します。</span><span class="sxs-lookup"><span data-stu-id="8a39c-156">If the message is an action message that is a duplicate of a previously processed action message, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] will post an error.</span></span>  
  
17. <span data-ttu-id="8a39c-157">RNIF 2.01 では、アクション メッセージが暗号化され、HTTP 同期と PIP 同期の要件が一致している場合、デコーダーによってペイロードの暗号化が解除されます。</span><span class="sxs-lookup"><span data-stu-id="8a39c-157">For RNIF 2.01, the decoder will decrypt the payload if the action message is encrypted and there is a match between the HTTP synchronicity and PIP synchronicity requirements.</span></span>  
  
18. <span data-ttu-id="8a39c-158">逆アセンブラーは Service Content を読み取り、MSG ガイドラインとスキーマを使用して検証します。</span><span class="sxs-lookup"><span data-stu-id="8a39c-158">The disassembler reads the service content, and validates it using the MSG guidelines and the schema.</span></span>  
  
19. <span data-ttu-id="8a39c-159">RNIF 2.01 では、マニフェストが有効でコンテンツ ID が存在することが逆アセンブラーによって検証されます。</span><span class="sxs-lookup"><span data-stu-id="8a39c-159">For RNIF 2.01, the disassembler verifies that the manifest is valid and the content ID is present.</span></span>  
  
20. <span data-ttu-id="8a39c-160">RNIF 2.01 では、逆アセンブラーはすべての添付ファイルを読み取ります。</span><span class="sxs-lookup"><span data-stu-id="8a39c-160">For RNIF 2.01, the disassembler will read any attachments.</span></span>  
  
21. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="8a39c-161"> は、RosettaNet ヘッダー、Service Content、およびパブリック プロセスへの添付ファイルをルーティングします。</span><span class="sxs-lookup"><span data-stu-id="8a39c-161"> routes the RosettaNet headers, service content, and attachments to the public process.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a39c-162">参照</span><span class="sxs-lookup"><span data-stu-id="8a39c-162">See Also</span></span>  
 [<span data-ttu-id="8a39c-163">BTARN でのメッセージ処理</span><span class="sxs-lookup"><span data-stu-id="8a39c-163">Message Processing in BTARN</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/message-processing-in-btarn.md)