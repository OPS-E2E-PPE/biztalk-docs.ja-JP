---
title: AS2 受信コンポーネント |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bdab87fd-15b9-4e3c-a4d7-984693262293
caps.latest.revision: 26
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0c919a54a307a234237dd4086a0abf2a2c0c2fd8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22232554"
---
# <a name="as2-receive-components"></a><span data-ttu-id="2da6d-102">AS2 の受信コンポーネント</span><span class="sxs-lookup"><span data-stu-id="2da6d-102">AS2 Receive Components</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="2da6d-103"> では、AS2 メッセージの受信にいくつかのコンポーネントが使用されます。</span><span class="sxs-lookup"><span data-stu-id="2da6d-103"> uses several components to receive AS2 messages.</span></span>  
  
## <a name="as2-receive-pipelines"></a><span data-ttu-id="2da6d-104">AS2 受信パイプライン</span><span class="sxs-lookup"><span data-stu-id="2da6d-104">AS2 Receive Pipelines</span></span>  
 <span data-ttu-id="2da6d-105">AS2 受信処理の大部分は、次の AS2 受信パイプラインで実行されます。</span><span class="sxs-lookup"><span data-stu-id="2da6d-105">Most AS2 receive processing is performed in the following AS2 receive pipelines.</span></span> <span data-ttu-id="2da6d-106">これらのパイプラインがインストールされている`Microsoft.BizTalk.EdiInt.PipelineComponents.dll`\Program Files\Microsoft BizTalk Server 20xx \pipeline Components に\\です。</span><span class="sxs-lookup"><span data-stu-id="2da6d-106">These pipelines are installed in `Microsoft.BizTalk.EdiInt.PipelineComponents.dll` in \Program Files\Microsoft BizTalk Server 20xx\Pipeline Components\\.</span></span>  
  
 <span data-ttu-id="2da6d-107">**AS2EdiReceive パイプライン**</span><span class="sxs-lookup"><span data-stu-id="2da6d-107">**AS2EdiReceive Pipeline**</span></span>  
  
 <span data-ttu-id="2da6d-108">このパイプラインは、MDN を含む AS2 経由で受信した EDI メッセージを処理します。</span><span class="sxs-lookup"><span data-stu-id="2da6d-108">This pipeline processes EDI messages received over AS2, including MDNs.</span></span> <span data-ttu-id="2da6d-109">パイプラインは、次のパイプライン コンポーネントで構成されます。</span><span class="sxs-lookup"><span data-stu-id="2da6d-109">The pipeline consists of the following pipeline components:</span></span>  
  
-   <span data-ttu-id="2da6d-110">AS2 デコーダー</span><span class="sxs-lookup"><span data-stu-id="2da6d-110">AS2 Decoder</span></span>  
  
-   <span data-ttu-id="2da6d-111">EDI 逆アセンブラー</span><span class="sxs-lookup"><span data-stu-id="2da6d-111">EDI Disassembler</span></span>  
  
-   <span data-ttu-id="2da6d-112">BatchMarker です。</span><span class="sxs-lookup"><span data-stu-id="2da6d-112">BatchMarker.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2da6d-113">AS2EdiReceive パイプラインを使用する場合、BizTalk Application Users グループに、BizTalk 分離ホスト インスタンス プロセスが実行されているユーザー アカウントを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2da6d-113">When using the AS2EdiReceive pipeline, you must add the user account that the BizTalk Isolated Host Instance process is running under to the BizTalk Application Users group.</span></span> <span data-ttu-id="2da6d-114">AS2EdiReceive パイプラインは、BizTalk 分離ホスト インスタンス プロセスで実行されます。</span><span class="sxs-lookup"><span data-stu-id="2da6d-114">The AS2EdiReceive pipeline executes in the BizTalk Isolated Host Instance process.</span></span> <span data-ttu-id="2da6d-115">AS2EdiReceive パイプラインは、BizTalk Application Users グループに属しているユーザーのみが使用できる SSO ストアにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="2da6d-115">The AS2EdiReceive pipeline accesses the SSO store, which requires that the user is in the BizTalk Application Users group.</span></span>  
  
 <span data-ttu-id="2da6d-116">**AS2Receive パイプライン**</span><span class="sxs-lookup"><span data-stu-id="2da6d-116">**AS2Receive Pipeline**</span></span>  
  
 <span data-ttu-id="2da6d-117">このパイプラインは、メッセージが EDI でエンコードされていない場合に、AS2 経由で受信したメッセージを処理します。</span><span class="sxs-lookup"><span data-stu-id="2da6d-117">This pipeline processes messages received over AS2 when the messages are not encoded in EDI.</span></span> <span data-ttu-id="2da6d-118">これらのメッセージは、バイナリ メッセージとして扱われます。</span><span class="sxs-lookup"><span data-stu-id="2da6d-118">These messages are treated as binary messages.</span></span> <span data-ttu-id="2da6d-119">このパイプラインは、AS2 経由で受信した MDN も処理します。</span><span class="sxs-lookup"><span data-stu-id="2da6d-119">The pipeline also processes MDNs received over AS2.</span></span> <span data-ttu-id="2da6d-120">パイプラインは、次のパイプライン コンポーネントで構成されます。</span><span class="sxs-lookup"><span data-stu-id="2da6d-120">The pipeline consists of the following pipeline components:</span></span>  
  
-   <span data-ttu-id="2da6d-121">AS2 デコーダー</span><span class="sxs-lookup"><span data-stu-id="2da6d-121">AS2 Decoder</span></span>  
  
-   <span data-ttu-id="2da6d-122">AS2 逆アセンブラー</span><span class="sxs-lookup"><span data-stu-id="2da6d-122">AS2 Disassembler.</span></span>  
  
## <a name="as2-receive-pipeline-components"></a><span data-ttu-id="2da6d-123">AS2 受信パイプライン コンポーネント</span><span class="sxs-lookup"><span data-stu-id="2da6d-123">AS2 Receive Pipeline Components</span></span>  
 <span data-ttu-id="2da6d-124">AS2 受信パイプラインでは、次のパイプライン コンポーネントが使用されます。</span><span class="sxs-lookup"><span data-stu-id="2da6d-124">The AS2 receive pipelines use the following pipeline components.</span></span> <span data-ttu-id="2da6d-125">これらのコンポーネントがインストールされている`Microsoft.BizTalk.EdiInt.PipelineComponents.dll`\Program Files\Microsoft BizTalk Server 20xx \pipeline Components に\\です。</span><span class="sxs-lookup"><span data-stu-id="2da6d-125">These components are installed in `Microsoft.BizTalk.EdiInt.PipelineComponents.dll` in \Program Files\Microsoft BizTalk Server 20xx\Pipeline Components\\.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2da6d-126">AS2 受信パイプラインは、32 ビットの BizTalk ホスト プロセスでのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="2da6d-126">The AS2 Receive pipeline is only supported in a 32-bit BizTalk Host process.</span></span>  
  
 <span data-ttu-id="2da6d-127">**AS2 デコーダー**</span><span class="sxs-lookup"><span data-stu-id="2da6d-127">**AS2 Decoder**</span></span>  
  
 <span data-ttu-id="2da6d-128">AS2 デコーダーは、AS2EDIReceivePipeline 受信パイプラインおよび AS2Receive 受信パイプラインの両方のデコード ステージに含まれています。</span><span class="sxs-lookup"><span data-stu-id="2da6d-128">The AS2 Decoder is included in the decode stage of both the AS2EDIReceivePipeline and AS2Receive receive pipelines.</span></span> <span data-ttu-id="2da6d-129">このデコーダーは、BizTalk の S/MIME パイプライン コンポーネントを使用して、AS2 メッセージと MDN メッセージに S/MIME デコード機能を付加します。</span><span class="sxs-lookup"><span data-stu-id="2da6d-129">It uses the BizTalk S/MIME Pipeline Component to provide S/MIME decoding functionality to AS2 and MDN messages.</span></span>  
  
-   <span data-ttu-id="2da6d-130">AS2/HTTP ヘッダーを処理します。</span><span class="sxs-lookup"><span data-stu-id="2da6d-130">Processes AS2/HTTP headers</span></span>  
  
-   <span data-ttu-id="2da6d-131">メッセージが署名付きの場合は署名を検証します。</span><span class="sxs-lookup"><span data-stu-id="2da6d-131">Verifies the signature, if the message was signed</span></span>  
  
-   <span data-ttu-id="2da6d-132">メッセージが暗号化されている場合はメッセージを解読します (MDN ではなく EDI/AS2 メッセージの場合)。</span><span class="sxs-lookup"><span data-stu-id="2da6d-132">Decrypts the messages, if the message was encrypted (for an EDI/AS2 message, not an MDN)</span></span>  
  
-   <span data-ttu-id="2da6d-133">メッセージが圧縮されている場合はメッセージを圧縮解除します。</span><span class="sxs-lookup"><span data-stu-id="2da6d-133">Decompresses the message, if the message was compressed</span></span>  
  
-   <span data-ttu-id="2da6d-134">受信した MDN を元の送信メッセージと照合して調整します。</span><span class="sxs-lookup"><span data-stu-id="2da6d-134">Reconciles a received MDN with the original outbound message</span></span>  
  
-   <span data-ttu-id="2da6d-135">否認不可データベース内でレコードの更新および関連付けを行います。</span><span class="sxs-lookup"><span data-stu-id="2da6d-135">Updates and correlates records in the non-repudiation database</span></span>  
  
-   <span data-ttu-id="2da6d-136">AS2 状態レポートのレコードを書き込みます。</span><span class="sxs-lookup"><span data-stu-id="2da6d-136">Writes records for AS2 status reporting</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2da6d-137">AS2 メッセージの受信側の処理中にエラーが発生した場合、AS2 デコーダーはそれ以降のダウンストリーム メッセージ処理を停止します (たとえば、EDI 逆アセンブラーはインターチェンジを解析しません)。</span><span class="sxs-lookup"><span data-stu-id="2da6d-137">If an error occurs during receive-side processing of an AS2 message, the AS2 Decoder will stop further downstream message processing (for example, the EDI disassembler will not parse the interchange).</span></span> <span data-ttu-id="2da6d-138">その場合でも、AS2 逆アセンブラーまたは EDI 逆アセンブラーは MDN を生成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2da6d-138">However, the AS2 Disassembler or EDI Disassembler must still generate the MDN.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2da6d-139">AS2 メッセージでは 8 ビット エンコードが使用されます。</span><span class="sxs-lookup"><span data-stu-id="2da6d-139">Eight-bit encoding is used on AS2 messages.</span></span> <span data-ttu-id="2da6d-140">Base64 エンコードは、AS2 メッセージと MDN の署名にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="2da6d-140">Base64 encoding is only applied to signatures in AS2 messages and MDNs.</span></span>  
  
 <span data-ttu-id="2da6d-141">**AS2 逆アセンブラー**</span><span class="sxs-lookup"><span data-stu-id="2da6d-141">**AS2 Disassembler**</span></span>  
  
 <span data-ttu-id="2da6d-142">AS2Receive 受信パイプラインでは、AS2 逆アセンブラーは次の処理を実行します。</span><span class="sxs-lookup"><span data-stu-id="2da6d-142">In the AS2Receive receive pipeline, the AS2 Disassembler does the following:</span></span>  
  
-   <span data-ttu-id="2da6d-143">MDN が必要かどうか、MDN が同期または非同期のどちらである必要があるかを決定します。</span><span class="sxs-lookup"><span data-stu-id="2da6d-143">Determines whether an MDN is required, and whether the MDN should be synchronous or asynchronous.</span></span>  
  
-   <span data-ttu-id="2da6d-144">AS2 MDN を生成します。</span><span class="sxs-lookup"><span data-stu-id="2da6d-144">Generates an AS2 MDN.</span></span>  
  
-   <span data-ttu-id="2da6d-145">MDN が同期の場合は `EdiIntAS.IsAS2AsynchronousMDN` プロパティを False に設定し、非同期の場合は True に設定します。</span><span class="sxs-lookup"><span data-stu-id="2da6d-145">If the MDN is synchronous, sets the `EdiIntAS.IsAS2AsynchronousMDN` property to False; if asynchronous, sets the property to True.</span></span>  
  
-   <span data-ttu-id="2da6d-146">MDN に関連付けのトークンとプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="2da6d-146">Sets the correlation tokens and properties on the MDN.</span></span>  
  
 <span data-ttu-id="2da6d-147">**EDI 逆アセンブラー**</span><span class="sxs-lookup"><span data-stu-id="2da6d-147">**EDI Disassembler**</span></span>  
  
 <span data-ttu-id="2da6d-148">AS2EDIReceivePipeline では、EDI 逆アセンブラーは EDI メッセージを処理するために中間 XML メッセージに解析します。</span><span class="sxs-lookup"><span data-stu-id="2da6d-148">In the AS2EDIReceivePipeline, the EDI Disassembler will parse the EDI message into intermediate XML message(s) for processing.</span></span> <span data-ttu-id="2da6d-149">詳細については、次を参照してください。 [「EDI 逆アセンブラーの動作](../core/how-the-edi-disassembler-works.md)です。</span><span class="sxs-lookup"><span data-stu-id="2da6d-149">For more information, see [How the EDI Disassembler Works](../core/how-the-edi-disassembler-works.md).</span></span>  
  
 <span data-ttu-id="2da6d-150">**BatchMarker**</span><span class="sxs-lookup"><span data-stu-id="2da6d-150">**BatchMarker**</span></span>  
  
 <span data-ttu-id="2da6d-151">AS2EDIReceivePipeline では、BatchMarker パイプライン コンポーネントは、バッチ処理されたインターチェンジの処理に必要な AgreementPartIdForSend および ToBeBatched の各コンテキスト プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="2da6d-151">In the AS2EDIReceivePipeline, the BatchMarker pipeline component sets the AgreementPartIdForSend and ToBeBatched context properties that are required for processing a batched interchange.</span></span> <span data-ttu-id="2da6d-152">このコンポーネントは、AS2EDIReceive パイプラインの最後のステージ (アグリーメントの解決) に含まれています。</span><span class="sxs-lookup"><span data-stu-id="2da6d-152">This component is included in the last stage (agreement resolution) of the AS2EDIReceive pipeline.</span></span> <span data-ttu-id="2da6d-153">EDI メッセージをバッチ処理するすべてのパイプラインに BatchMarker パイプライン コンポーネントが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="2da6d-153">All pipelines that will batch EDI messages should include the BatchMarker pipeline component.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2da6d-154">BatchMarker パイプライン コンポーネントは、EDI 以外のメッセージの処理に使用する AS2Receive パイプラインには含まれていません。</span><span class="sxs-lookup"><span data-stu-id="2da6d-154">The BatchMarker pipeline component is not included in the AS2Receive pipeline that is used to process non-EDI messages.</span></span> <span data-ttu-id="2da6d-155">ただし、EDI 逆アセンブラーを含まないカスタム受信パイプラインに BatchMarker コンポーネントを含めることはできます。</span><span class="sxs-lookup"><span data-stu-id="2da6d-155">However, you can include the BatchMarker component in a custom receive pipeline that does not include the EDI Dissassembler.</span></span> <span data-ttu-id="2da6d-156">詳細についてを参照してください「の処理非 EDI メッセージ BatchMarker コンポーネントで」[バッチ EDI インターチェンジをアセンブル](../core/assembling-a-batched-edi-interchange.md)です。</span><span class="sxs-lookup"><span data-stu-id="2da6d-156">For more information, see "Processing Non-EDI Messages in the BatchMarker Component" in [Assembling a Batched EDI Interchange](../core/assembling-a-batched-edi-interchange.md).</span></span>  
  
## <a name="http-adapter"></a><span data-ttu-id="2da6d-157">HTTP アダプター</span><span class="sxs-lookup"><span data-stu-id="2da6d-157">HTTP Adapter</span></span>  
 <span data-ttu-id="2da6d-158">AS2 処理に使用される受信ポートと受信場所では、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の HTTP アダプターが使用されます。</span><span class="sxs-lookup"><span data-stu-id="2da6d-158">The receive ports and locations used for AS2 processing use the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] HTTP Adapter.</span></span> <span data-ttu-id="2da6d-159">この HTTP アダプターは、一方向の送信と要求 - 応答の送信のいずれかに構成されます。</span><span class="sxs-lookup"><span data-stu-id="2da6d-159">The HTTP Adapter is configured for either one-way and request-response transmission.</span></span>  
  
## <a name="non-repudiation-database"></a><span data-ttu-id="2da6d-160">否認不可データベース</span><span class="sxs-lookup"><span data-stu-id="2da6d-160">Non-Repudiation Database</span></span>  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="2da6d-161"> は、否認不可データベース (BizTalkDTADb データベースの EdiMessageContent テーブル) を使用して次の処理を実行します。</span><span class="sxs-lookup"><span data-stu-id="2da6d-161"> uses the non-repudiation database (the EdiMessageContent table of the BizTalkDTADb database) to do the following:</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2da6d-162">EdiMessageContent テーブルは、否認不可ストレージ アグリーメントのプロパティの 1 つがチェックされている場合にのみ BizTalkDTADb データベース内に存在します。</span><span class="sxs-lookup"><span data-stu-id="2da6d-162">The EdiMessageContent table exists in the BizTalkDTADb database only if one of the non-repudiation storage agreement properties has been checked.</span></span>  
  
-   <span data-ttu-id="2da6d-163">署名付き MDN の否認不可記録の提供</span><span class="sxs-lookup"><span data-stu-id="2da6d-163">Provides a non-repudiation trail for signed MDN</span></span>  
  
-   <span data-ttu-id="2da6d-164">送信メッセージと受信 MDN の関連付け</span><span class="sxs-lookup"><span data-stu-id="2da6d-164">Correlates an outbound message with its incoming MDN</span></span>  
  
-   <span data-ttu-id="2da6d-165">さまざまな状態変更によるメッセージの保存</span><span class="sxs-lookup"><span data-stu-id="2da6d-165">Stores messages through various state changes</span></span>  
  
-   <span data-ttu-id="2da6d-166">HTTP 応答と MDN の関連付けられたエラー コード</span><span class="sxs-lookup"><span data-stu-id="2da6d-166">Associates error codes with HTTP Response and MDN</span></span>  
  
-   <span data-ttu-id="2da6d-167">フィルター条件に基づくレコードの表示</span><span class="sxs-lookup"><span data-stu-id="2da6d-167">Displays records based on filter criteria</span></span>  
  
-   <span data-ttu-id="2da6d-168">マークされたレコードのアーカイブ</span><span class="sxs-lookup"><span data-stu-id="2da6d-168">Archives marked records.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="2da6d-169">否認不可受信データベースに格納されているメッセージの認証と整合性を確保するには、データベースに格納されるすべてのメッセージ (元の AS2 メッセージと MDN の両方) にデジタル署名を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2da6d-169">To ensure authentication and integrity of messages stored in the non-repudiation receipt database, digital signatures should be used on all messages that will be stored in the database, both original AS2 messages and MDNs.</span></span> <span data-ttu-id="2da6d-170">詳細については、表示のセクション 9.1 [「Mime-based Secure ピア ツー ピア Business Data Interchange Using HTTP, Applicability Statement 2 (AS2)」、RFC 1430](http://go.microsoft.com/fwlink/?LinkID=184212) ([http://go.microsoft.com/fwlink/?LinkID=184212](http://go.microsoft.com/fwlink/?LinkID=184212))。</span><span class="sxs-lookup"><span data-stu-id="2da6d-170">For more information, see section 9.1 of [RFC 1430, "MIME-Based Secure Peer-to-Peer Business Data Interchange Using HTTP, Applicability Statement 2 (AS2)"](http://go.microsoft.com/fwlink/?LinkID=184212) ([http://go.microsoft.com/fwlink/?LinkID=184212](http://go.microsoft.com/fwlink/?LinkID=184212)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2da6d-171">参照</span><span class="sxs-lookup"><span data-stu-id="2da6d-171">See Also</span></span>  
 [<span data-ttu-id="2da6d-172">BizTalk Server が AS2 メッセージを受信する方法</span><span class="sxs-lookup"><span data-stu-id="2da6d-172">How BizTalk Server Receives AS2 Messages</span></span>](../core/how-biztalk-server-receives-as2-messages.md)