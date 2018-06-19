---
title: AS2 送信コンポーネント |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 35113732-fe32-4776-be25-971ec66c365c
caps.latest.revision: 22
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e1dbee64dc2e3484e85e6d8e41ce31a77713ffec
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22231970"
---
# <a name="as2-send-components"></a><span data-ttu-id="3830f-102">AS2 送信コンポーネント</span><span class="sxs-lookup"><span data-stu-id="3830f-102">AS2 Send Components</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="3830f-103"> は、いくつかのコンポーネントを使用して AS2 メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="3830f-103"> uses several components to send AS2 messages.</span></span>  
  
## <a name="as2-send-pipelines"></a><span data-ttu-id="3830f-104">AS2 送信パイプライン</span><span class="sxs-lookup"><span data-stu-id="3830f-104">AS2 Send Pipelines</span></span>  
 <span data-ttu-id="3830f-105">AS2 送信処理の大部分は、次の AS2 送信パイプラインで実行されます。</span><span class="sxs-lookup"><span data-stu-id="3830f-105">Most AS2 send processing is performed in the following AS2 send pipelines.</span></span> <span data-ttu-id="3830f-106">これらのパイプラインは、\Program Files\Microsoft BizTalk Server 20xx\Pipeline Components の `Microsoft.BizTalk.Edi.EdiIntPipelines.dll` にインストールされています。</span><span class="sxs-lookup"><span data-stu-id="3830f-106">These pipelines are installed in `Microsoft.BizTalk.Edi.EdiIntPipelines.dll` in \Program Files\Microsoft BizTalk Server 20xx\Pipeline Components.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3830f-107">AS2 送信パイプラインは、32 ビットの BizTalk ホスト プロセスでのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="3830f-107">The AS2 Send pipeline is only supported in a 32-bit BizTalk Host process.</span></span>  
  
 <span data-ttu-id="3830f-108">**AS2EDISend パイプライン**</span><span class="sxs-lookup"><span data-stu-id="3830f-108">**AS2EDISend Pipeline**</span></span>  
  
 <span data-ttu-id="3830f-109">このパイプラインでは、EDI メッセージを生成し、AS2 経由で送信します。</span><span class="sxs-lookup"><span data-stu-id="3830f-109">This pipeline generates and sends EDI messages over AS2.</span></span> <span data-ttu-id="3830f-110">パイプラインは、次のパイプライン コンポーネントで構成されます。</span><span class="sxs-lookup"><span data-stu-id="3830f-110">The pipeline consists of the following pipeline components:</span></span>  
  
-   <span data-ttu-id="3830f-111">EDI アセンブラー</span><span class="sxs-lookup"><span data-stu-id="3830f-111">EDI Assembler</span></span>  
  
-   <span data-ttu-id="3830f-112">AS2 エンコーダー</span><span class="sxs-lookup"><span data-stu-id="3830f-112">AS2 Encoder</span></span>  
  
 <span data-ttu-id="3830f-113">このパイプラインは、MDN を生成して AS2 経由で送信するためには使用されません。これは、MDN を EDI アセンブラーで処理する必要がないためです。</span><span class="sxs-lookup"><span data-stu-id="3830f-113">This pipeline is not used to generate and send MDNs over AS2, because the MDN does not need to be processed by the EDI Assembler.</span></span> <span data-ttu-id="3830f-114">MDN の送信には AS2SendPipeline を使用します。</span><span class="sxs-lookup"><span data-stu-id="3830f-114">Use the AS2SendPipeline to send MDNs.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3830f-115">オーケストレーションからの AS2EDISend パイプラインの実行はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="3830f-115">Running the AS2EDISend pipeline from an orchestration is not supported.</span></span>  
  
 <span data-ttu-id="3830f-116">**AS2Send パイプライン**</span><span class="sxs-lookup"><span data-stu-id="3830f-116">**AS2Send Pipeline**</span></span>  
  
 <span data-ttu-id="3830f-117">このパイプラインでは、メッセージが EDI でエンコードされていない場合に、AS2 経由でメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="3830f-117">This pipeline sends messages over AS2 when the messages are not encoded in EDI.</span></span> <span data-ttu-id="3830f-118">また、AS2 経由で MDN を送信します。</span><span class="sxs-lookup"><span data-stu-id="3830f-118">It also sends MDNs over AS2.</span></span> <span data-ttu-id="3830f-119">パイプラインは、次のパイプライン コンポーネントで構成されます。</span><span class="sxs-lookup"><span data-stu-id="3830f-119">The pipeline consists of the following pipeline components:</span></span>  
  
-   <span data-ttu-id="3830f-120">AS2 エンコーダー。</span><span class="sxs-lookup"><span data-stu-id="3830f-120">AS2 Encoder.</span></span>  
  
 <span data-ttu-id="3830f-121">AS2 経由で送信するメッセージが EDI メッセージでも XML メッセージでもない場合は、それらのメッセージを処理するために、カスタマイズされた AS2Send パイプラインを作成できます。</span><span class="sxs-lookup"><span data-stu-id="3830f-121">If the messages to be sent over AS2 are neither EDI nor XML messages, you can create a customized AS2Send pipeline to handle these messages.</span></span> <span data-ttu-id="3830f-122">このパイプラインには、メッセージを EDIINT/AS2 にエンコードする前に BizTalk Server の中間 XML を他の形式に変換する、カスタマイズされたアセンブラーが必要です。</span><span class="sxs-lookup"><span data-stu-id="3830f-122">This pipeline must have a customized assembler to convert the intermediate XML in BizTalk Server into the other format before encoding the message in EDIINT/AS2.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3830f-123">オーケストレーションからの AS2Send パイプラインの実行はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="3830f-123">Running the AS2Send pipeline from an orchestration is not supported.</span></span>  
  
## <a name="as2-send-pipeline-components"></a><span data-ttu-id="3830f-124">AS2 送信パイプラインのコンポーネント</span><span class="sxs-lookup"><span data-stu-id="3830f-124">AS2 Send Pipeline Components</span></span>  
 <span data-ttu-id="3830f-125">AS2 送信パイプラインでは、次のパイプライン コンポーネントが使用されます。</span><span class="sxs-lookup"><span data-stu-id="3830f-125">The AS2 send pipelines use the following pipeline components.</span></span> <span data-ttu-id="3830f-126">これらのコンポーネントがインストールされている`Microsoft.BizTalk.EdiInt.PipelineComponents.dll`\Program Files\Microsoft BizTalk Server 20xx \pipeline Components に\\です。</span><span class="sxs-lookup"><span data-stu-id="3830f-126">These components are installed in `Microsoft.BizTalk.EdiInt.PipelineComponents.dll` in \Program Files\Microsoft BizTalk Server 20xx\Pipeline Components\\.</span></span>  
  
 <span data-ttu-id="3830f-127">**EDI アセンブラー**</span><span class="sxs-lookup"><span data-stu-id="3830f-127">**EDI Assembler**</span></span>  
  
 <span data-ttu-id="3830f-128">EDIINT 送信パイプラインでは、EDI アセンブラーによって EDI インターチェンジがシリアル化されます。</span><span class="sxs-lookup"><span data-stu-id="3830f-128">In the EDIINT send pipelines, the EDI Assembler serializes the EDI interchange.</span></span>  
  
 <span data-ttu-id="3830f-129">**AS2 エンコーダー**</span><span class="sxs-lookup"><span data-stu-id="3830f-129">**AS2 Encoder**</span></span>  
  
 <span data-ttu-id="3830f-130">AS2 エンコーダーは、AS2 送信パイプラインのエンコード ステージに含まれています。</span><span class="sxs-lookup"><span data-stu-id="3830f-130">The AS2 Encoder is included in the encode stage of the AS2 send pipelines.</span></span> <span data-ttu-id="3830f-131">これは、BizTalk の S/MIME パイプライン コンポーネントを使用して、AS2 メッセージと MDN メッセージに S/MIME エンコード機能を付加します。</span><span class="sxs-lookup"><span data-stu-id="3830f-131">It uses the BizTalk S/MIME pipeline component to provide S/MIME encoding functionality to AS2 and MDN messages.</span></span> <span data-ttu-id="3830f-132">AS2 エンコーダーは次の処理を実行します。</span><span class="sxs-lookup"><span data-stu-id="3830f-132">The AS2 Encoder does the following:</span></span>  
  
-   <span data-ttu-id="3830f-133">AS2/HTTP ヘッダーを適用します。</span><span class="sxs-lookup"><span data-stu-id="3830f-133">Applies AS2/HTTP headers</span></span>  
  
-   <span data-ttu-id="3830f-134">送信メッセージに署名します (有効になっている場合)。</span><span class="sxs-lookup"><span data-stu-id="3830f-134">Signs outgoing messages, if enabled</span></span>  
  
-   <span data-ttu-id="3830f-135">送信メッセージを暗号化します (有効になっている場合。EDI/AS2 のみで MDN は対象外)。</span><span class="sxs-lookup"><span data-stu-id="3830f-135">Encrypts outgoing messages, if enabled (for EDI/AS2, not MDN)</span></span>  
  
-   <span data-ttu-id="3830f-136">メッセージを圧縮します (有効になっている場合。EDI/AS2 のみで MDN は対象外)。</span><span class="sxs-lookup"><span data-stu-id="3830f-136">Compresses the message, if enabled (for EDI/AS2, not MDN)</span></span>  
  
-   <span data-ttu-id="3830f-137">ペイロードをワイヤ形式に保存する場合、**送信のデコードされた AS2 メッセージに対して有効な NRR**プロパティが選択され、メッセージをワイヤ形式に保存する場合、**エンコードされた送信の AS2 メッセージに対して有効な NRR**プロパティが選択されています。</span><span class="sxs-lookup"><span data-stu-id="3830f-137">Stores the payload in wire format if the **NRR enabled for outbound decoded AS2 messages** property is selected, and stores the message in wire format if the **NRR enabled for outbound encoded AS2 messages** property is selected</span></span>  
  
-   <span data-ttu-id="3830f-138">MIC 値を計算し、データ ストアに保存します。</span><span class="sxs-lookup"><span data-stu-id="3830f-138">Computes the MIC value and stores it in the data store</span></span>  
  
-   <span data-ttu-id="3830f-139">受信の否認不可データベース内でレコードの更新および関連付けを行います。</span><span class="sxs-lookup"><span data-stu-id="3830f-139">Updates and correlates records in the non-repudiation receipt database</span></span>  
  
-   <span data-ttu-id="3830f-140">AS2Receive 受信パイプラインの AS2 デコーダーによって生成された MDN をルーティングするパススルー パイプラインとして機能します (MDN メッセージの場合)。</span><span class="sxs-lookup"><span data-stu-id="3830f-140">For MDN messages, acts as a passthrough pipeline, routing the MDN generated by the AS2 Decoder in the AS2Receive receive pipeline.</span></span> <span data-ttu-id="3830f-141">構成設定で要求されている場合、AS2 エンコーダーが MDN に署名します。</span><span class="sxs-lookup"><span data-stu-id="3830f-141">If required by the configuration settings, the AS2 Encoder will sign the MDN.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3830f-142">AS2 メッセージでは 8 ビット エンコードが使用されます。</span><span class="sxs-lookup"><span data-stu-id="3830f-142">Eight-bit encoding is used on AS2 messages.</span></span> <span data-ttu-id="3830f-143">Base64 エンコードは、AS2 メッセージと MDN の署名にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="3830f-143">Base64 encoding is only applied to signatures in AS2 messages and MDNs.</span></span>  
  
## <a name="http-adapter"></a><span data-ttu-id="3830f-144">HTTP アダプター</span><span class="sxs-lookup"><span data-stu-id="3830f-144">HTTP Adapter</span></span>  
 <span data-ttu-id="3830f-145">EDIINT AS2 処理に使用される送信ポートは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の HTTP アダプターを使用します。</span><span class="sxs-lookup"><span data-stu-id="3830f-145">The send ports used for EDIINT AS2 processing use the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] HTTP Adapter.</span></span> <span data-ttu-id="3830f-146">この HTTP アダプターは、一方向の送信と送信請求 - 応答送信の両方で構成されます。</span><span class="sxs-lookup"><span data-stu-id="3830f-146">The HTTP Adapter is configured in both one-way and solicit-response transmission.</span></span>  
  
## <a name="non-repudiation-database"></a><span data-ttu-id="3830f-147">否認不可データベース</span><span class="sxs-lookup"><span data-stu-id="3830f-147">Non-Repudiation Database</span></span>  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="3830f-148"> は、否認不可データベース (BizTalkDTADb データベースの EdiMessageContent テーブル) を使用して次の処理を実行します。</span><span class="sxs-lookup"><span data-stu-id="3830f-148"> uses the non-repudiation database (the EdiMessageContent table of the BizTalkDTADb database) to do the following:</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3830f-149">EdiMessageContent テーブルは、否認不可ストレージ アグリーメントのプロパティの 1 つがチェックされる場合にのみ BizTalkDTADb データベース内に存在します。</span><span class="sxs-lookup"><span data-stu-id="3830f-149">The EdiMessageContent table exists in the BizTalkDTADb database only if one of the non-repudiation storage agreement properties are checked.</span></span>  
  
-   <span data-ttu-id="3830f-150">署名付き MDN を否認不可記録を提供します。</span><span class="sxs-lookup"><span data-stu-id="3830f-150">Provide a non-repudiation trail for signed MDN</span></span>  
  
-   <span data-ttu-id="3830f-151">受信 MDN と送信メッセージを関連付ける</span><span class="sxs-lookup"><span data-stu-id="3830f-151">Correlate an outbound message with its incoming MDN</span></span>  
  
-   <span data-ttu-id="3830f-152">さまざまな状態の変更を経由してメッセージを保存します。</span><span class="sxs-lookup"><span data-stu-id="3830f-152">Store messages through various state changes</span></span>  
  
-   <span data-ttu-id="3830f-153">エラー コードの HTTP 応答および NDN への関連付け</span><span class="sxs-lookup"><span data-stu-id="3830f-153">Associate error codes with HTTP Response and MDN</span></span>  
  
-   <span data-ttu-id="3830f-154">フィルター条件に基づいてレコードを表示します。</span><span class="sxs-lookup"><span data-stu-id="3830f-154">Display records based on filter criteria</span></span>  
  
-   <span data-ttu-id="3830f-155">マークされたレコードをアーカイブします。</span><span class="sxs-lookup"><span data-stu-id="3830f-155">Archive marked records</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="3830f-156">否認不可データベースに格納されているメッセージの認証と整合性を確保するには、データベースに格納されるすべてのメッセージ (元の AS2 メッセージと MDN の両方) にデジタル署名を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3830f-156">To ensure authentication and integrity of messages stored in the non-repudiation database, digital signatures should be used on all messages that will be stored in the database, both original AS2 messages and MDNs.</span></span> <span data-ttu-id="3830f-157">詳細については、表示のセクション 9.1 [「Mime-based Secure ピア ツー ピア Business Data Interchange Using HTTP, Applicability Statement 2 (AS2)」、RFC 1430](http://go.microsoft.com/fwlink/?LinkID=184212) ([http://go.microsoft.com/fwlink/?LinkID=184212](http://go.microsoft.com/fwlink/?LinkID=184212))。</span><span class="sxs-lookup"><span data-stu-id="3830f-157">For more information, see section 9.1 of [RFC 1430, "MIME-Based Secure Peer-to-Peer Business Data Interchange Using HTTP, Applicability Statement 2 (AS2)"](http://go.microsoft.com/fwlink/?LinkID=184212) ([http://go.microsoft.com/fwlink/?LinkID=184212](http://go.microsoft.com/fwlink/?LinkID=184212)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3830f-158">参照</span><span class="sxs-lookup"><span data-stu-id="3830f-158">See Also</span></span>  
 [<span data-ttu-id="3830f-159">BizTalk Server が AS2 メッセージを送信する方法</span><span class="sxs-lookup"><span data-stu-id="3830f-159">How BizTalk Server Sends AS2 Messages</span></span>](../core/how-biztalk-server-sends-as2-messages.md)